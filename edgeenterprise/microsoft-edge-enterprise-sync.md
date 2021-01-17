---
title: 配置 Microsoft Edge 同步并排除故障
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 01/14/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 配置 Microsoft Edge 同步并排除故障
ms.openlocfilehash: fa9b9ead6319bceeb95066003a77be7ecf84db46
ms.sourcegitcommit: 68b50c45b2b78acec5a0776ce4ddd11410a4e382
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "11270750"
---
# 配置 Microsoft Edge 同步并排除故障

本文介绍如何配置和使用 Microsoft Edge，以便在所有已登录设备上同步收藏夹、密码和其他浏览器数据。 本文还提供了有关最常见同步问题的故障排除步骤。 其中还包括用于收集故障排除所需日志的推荐工具。

> [!NOTE]
> 除非另有说明，否则本文适用于 Microsoft Edge 版本 77 或更高版本。

## 概述

通过 Microsoft Edge 同步，用户可以访问他们所有已登录设备上的浏览数据。 同步支持的数据包括：

- 收藏夹
- 密码
- 地址等（表单填写）
- 收藏
- “设置”
- 扩展
- 打开选项卡（在 Microsoft Edge 版本 88 中可用）
- 历史记录（在 Microsoft Edge 版本 88 中可用）

用户同意后即可启用同步功能，并且用户可以针对上面列出的每种数据类型打开或关闭同步功能。

> [!NOTE]
> 将上载其他设备连接和配置数据（如设备名称、品牌和型号），以支持同步功能。

## 必备条件

适用于 Azure Active Directory (Azure AD) 帐户的 Microsoft Edge 同步功能可供以下任何订阅使用：

- Azure AD Premium（P1 或 P2）
- M365 商业高级版
- Office 365 E1 及更高版本
- Azure 信息保护 (AIP)（P1 或 P2）
- 所有 EDU 订阅（Microsoft 教育应用版（学生）或 Microsoft 教育应用版（教职员工）、Exchange Online 学生版或教职员工版、O365 A1 或更高版本、M365 A1 或更高版本，或者适用于学生或教职员的 Azure 信息保护 P1 或 P2）

## 同步组策略

你可以使用以下组策略配置和管理 Microsoft Edge 同步：

- [SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled)：完全禁用同步。
- [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled)：禁止保存浏览历史记录和同步。此策略还将禁用打开选项卡同步。
- [AllowDeletingBrowserHistory](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory)：当此策略设置为禁用时，还将禁用历史记录同步。
- [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled)：配置从同步中排除的类型列表。
- [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled)：允许 Active Directory (AD) 配置文件使用本地存储。 有关更多信息，请参阅 [Active Directory (AD) 用户的本地同步](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync)。
- [ForceSync：]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync)默认启用同步，无需用户同意。  

## 配置 Microsoft Edge 同步

Azure 信息保护 (AIP) 服务提供了 Microsoft Edge 同步的配置选项。 为租户启用 AIP 后，无论获得何种许可，所有用户均可同步 Microsoft Edge 数据。 有关如何启用 AIP 的说明，请参阅[此处](https://docs.microsoft.com/azure/information-protection/activate-office365)。

若要限制某一组用户使用同步功能，可为这些用户启用 [AIP 登录控制策略](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true) 。 如果确保所有必需的用户均加入后同步仍不可用，请确保已使用 [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true) PowerShell cmdlet 启用 IPCv3Service。

> [!CAUTION]
> 激活 Azure 信息保护还将允许其他应用程序（如 Microsoft Word 或 Microsoft Outlook）使用 AIP 保护内容。 此外，用于限制 Microsoft Edge 同步的任何载入控制策略也将限制其他应用程序使用 AIP 保护内容。

## Microsoft Edge 和企业状态漫游 (ESR) 

Microsoft Edge 是一个跨平台应用程序，扩展了跨用户的所有设备同步用户数据的范围，并且不再是 Azure AD 企业状态漫游的一部分。 但是，Microsoft Edge 将履行 ESR 的数据保护承诺，例如能够引入你自己的密钥。 有关详细信息，请参阅 [Microsoft Edge 和企业状态漫游](microsoft-edge-enterprise-state-roaming.md)。

## 同步问题故障排除

本部分提供了针对常见同步问题的故障排除步骤。 其中还包括用于收集故障排除所需日志的推荐工具。

### 标识问题与同步问题

在浏览器中维护用户标识的一个常见用例是支持同步。因此，标识问题经常与同步问题混淆。 在开始排除同步故障之前，请了解标识和同步问题的区别。

在将某个问题视为同步问题之前，请检查用户是否已使用有效帐户登录浏览器。

接下来的屏幕截图显示了在 *edge://sync-internals* 中出现在“**Credentials**”下的标识错误示例：

:::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-identity-issue.png" alt-text="标识错误":::

### 常见同步问题

#### 问题：无法访问 M365 或 Azure 信息保护订阅

你是不是以前拥有的 M365 或 Azure 信息保护 (AIP) 订阅已过期，然后替换成了新订阅？ 如果是，则租户 ID 已更改，需要重置服务数据。 请参阅**遇到密码器错误**问题中有关重置数据的说明。

#### 问题：“此帐户无法使用同步功能。”

如果 Azure Active Directory 帐户遇到此错误，或 *edge://sync-internals* 中出现 DISABLED_BY_ADMIN，请按顺序执行下一过程中的步骤，直到问题得到解决。

> [!NOTE]
> 由于此错误的来源通常需要在 Azure Active Directory 租户中更改配置，因此这些故障排除步骤只能由租户管理员执行，而不能由最终用户执行。

1. 验证企业租户是否具有受支持的 M365 订阅。 [此处](https://docs.microsoft.com/azure/information-protection/activate-office365)提供了可用订阅类型的当前列表。 如果租户没有受支持的订阅，他们可以单独购买 Azure 信息保护，也可以升级到受支持的某个订阅。
2. 如果具有受支持的订阅，请验证租户是否具有可用的 Azure 信息保护 (AIP)。 有关检查 AIP 状态以及在必要时激活 AIP 的说明，请参阅[此处](https://docs.microsoft.com/azure/information-protection/activate-office365)。
3. 如果步骤 2 显示 AIP 处于活动状态，但仍无法使用同步功能，请启用企业状态漫游 (ESR)。 有关启用 ESR 的说明，请参阅[此处](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)。 请注意，无需将 ESR 保持启用状态。 如果此步骤修复了问题，可以禁用 ESR。
4. 确认 Azure 信息保护未通过载入策略确定作用域。 你可以使用 [Get-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell 小程序来查看是否启用了作用域功能。 接下来的两个示例显示了一个无作用域配置和一个作用域为特定安全组的配置。

   ```powershell
    PS C:\Work\scripts\PowerShell> Get-AadrmOnboardingControlPolicy
 
    UseRmsUserLicense SecurityGroupObjectId                Scope
    ----------------- ---------------------                -----
                False 
   ```

   ```powershell

    PS C:\Work\scripts\PowerShell> Get-AadrmOnboardingControlPolicy
 
    UseRmsUserLicense SecurityGroupObjectId                Scope
    ----------------- ---------------------                -----
                False f1488a05-8196-40a6-9483-524948b90282   All
   ```


   如果启用了作用域功能，则应该将受影响的用户添加到相应作用域的安全组，或者删除该作用域。 在下面的示例中，载入将 AIP 的作用域设定成了指示的安全组，应该使用 [Set-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell 小程序删除作用域功能。

5. 确认已在租户中启用 IPCv3Service。 [Get-AadrmConfiguration](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmconfiguration?view=azureipps) PowerShell 小程序可显示该服务的状态。

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-scoped-cfg-example.png" alt-text="检查是否已启用 IPCv3Service。":::

6. 如果未能解决问题，请与 [Microsoft Edge 支持人员](https://www.microsoftedgeinsider.com/support)联系。

#### 问题：卡在“正在设置同步...”或“无法连接到同步服务器。 正在重试…”环节

1. 尝试注销，然后再登录。
2. 转到 *edge://sync-internals*。 如果“**Type info**”部分下存在以下错误，请跳到以下问题：**遇到密码器错误**。

   `"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered"`

3. 尝试 ping 服务器终结点。 *edge://sync-internals* 中提供了客户端的服务器终结点。 接下来的屏幕截图显示了“**Environment Info**”下的终结点信息。

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-endpoint-info.png" alt-text="终结点信息":::

4. 如果服务器终结点为空，或者无法对服务器执行 ping 操作且环境中存在防火墙，请确认客户端计算机可以使用必要的服务终结点。

   - Microsoft Edge 同步服务终结点：
     - [https://edge-enterprise.activity.windows.com](https://edge-enterprise.activity.windows.com)
     - [https://edge.activity.windows.com](https://edge.activity.windows.com)
    - Azure 信息保护终结点：
      - [https://api.aadrm.com](https://api.aadrm.com)（适用于大多数租户）
      - [https://api.aadrm.de](https://api.aadrm.de)（适用于德国的租户）
      - [https://api.aadrm.cn](https://api.aadrm.cn)（适用于中国的租户）
   - [Windows 通知服务终结点](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)。

5. 如果仍未能解决问题，请与 [Microsoft Edge 支持人员](https://www.microsoftedgeinsider.com/support)联系。

### 问题：遇到密码器错误

此错误显示在 *edge://sync-internals* 中的“**Type info**”下，并且可能意味着需要重置用户的服务器端数据。 接下来的屏幕截图显示了密码器错误的详细信息示例。

:::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-crypto-error-new.png" alt-text="密码器错误。":::

1. 重新启动 Microsoft Edge 并导航到 *edge://sync-internals*，检查“**AAD Account Key Status**”部分
   - “Last MIP Result”中为“Success”：该密码器错误意味着服务器数据在加密时使用的可能是丢失的密钥。 需要重置数据才能恢复同步。
   - “Last MIP Result”中为“No permissions”：这可能是由 Azure AD 更改或租户订阅更改引起的。 需要重置数据才能恢复同步。
   - 其他错误可能意味着服务器配置问题。
2. 如果需要重置数据，请参阅[重置云中的 Microsoft Edge 数据](edge-learnmore-reset-data-in-cloud.md)。

#### 问题：“管理员已禁用同步。”

确保未设置 [SyncDisabled 策略](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled)。

## 常见问题

### 安全性和服务器/数据合规性

#### 已同步的数据是否已加密？

数据使用 TLS 1.2 或更高版本在传输中加密。 在 Microsoft 的服务中，所有数据类型都会使用 AES128 进行额外的静态加密。 除用于同步已打开标签页和历史记录的数据类型外，所有数据类型都会在离开用户设备之前使用 [Azure 信息保护](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern)策略所管理的密钥进行额外加密。

#### 为什么已打开标签页和历史记录数据没有更多的客户端加密？

为了降低最终用户设备上的资源利用率，系统将基于已打开标签页的漫游数据在服务器端生成历史记录数据。 此过程无法支持此类数据的客户端加密。 若要禁用打开选项卡和历史记录同步，请应用 [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled) 或 [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) 策略。

#### 租户管理员能否使用自己的密钥？

是，可通过  [Azure 信息保护](https://azure.microsoft.com/services/information-protection/)来实现。

#### Microsoft Edge 的同步数据存储在哪里？

Azure AD 帐户的同步数据将根据租户 ID 存储在安全服务器中。 例如，在美国注册的租户的数据存储在位于该地区地理位置的服务器上，并使用与 Office 应用程序相同的存储解决方案。

#### 除了同步至 Microsoft Edge 外，数据是否会离开 Microsoft 云？

否。

#### 企业同步属于哪项服务条款？

Microsoft Edge 同步服务条款已列入 Microsoft 软件许可证，可使用 Microsoft Edge 访问  *edge://terms* 进行查看。 你的 Azure AD 订阅和服务条款最终属于 Microsoft 的[联机服务条款](https://www.microsoft.com/licensing/product-licensing/products)。

#### Microsoft Edge 是否支持政府社区云 (GCC) 高合规性？

目前尚不支持。 对于 GCC 高云中的客户，已禁用 Microsoft Edge 同步。

### 应用同步

#### 为什么并非所有 M365 订阅都支持 Microsoft Edge 同步？

企业同步取决于 [Azure 信息保护](https://azure.microsoft.com/services/information-protection/)，后者并非在所有 M365 订阅中都可用。

#### Microsoft Edge 同步是否基于企业状态漫游？

否。 ESR 可用于启用同步，但 Microsoft Edge 同步不是 ESR 的一部分。 有关详细信息，请参阅 [Microsoft Edge 同步](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-sync)和 [Microsoft Edge 和企业状态漫游](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-state-roaming)。

#### Microsoft Edge 是否支持 Microsoft Edge 和 IE 之间的同步？

尚无支持此同步的计划。 如果你的环境仍需要 IE 来支持旧版应用，请考虑使用我们的[新 IE 模式](https://docs.microsoft.com/deployedge/edge-ie-mode)。

#### Microsoft Edge 是否将与 Microsoft Edge 旧版同步？

否，不会同步。 我们认为连接这两个生态系统将降低 Microsoft Edge 同步的可靠性。 我们会确保将现有数据迁移到 Microsoft Edge。 用户还可以从自己选择的浏览器导入数据，这也意味着 Microsoft Edge 无法与 IE 同步。

### 管理同步

#### 是否可以阻止我的用户与个人租户同步？

无法直接阻止，但你可以使用 [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) 策略确定哪些配置文件可以登录到 Microsoft Edge。

## 另请参阅

- [Microsoft Edge 企业同步](microsoft-edge-enterprise-sync.md)
- [Microsoft Edge 和企业状态漫游](microsoft-edge-enterprise-state-roaming.md)
- [Microsoft Edge 企业版登录页面](https://aka.ms/EdgeEnterprise)
