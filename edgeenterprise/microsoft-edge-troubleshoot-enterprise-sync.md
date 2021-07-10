---
title: 诊断和修复 Microsoft Edge 同步问题
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 管理员可用于排查和修复常见企业同步问题的指南和工具
ms.openlocfilehash: 0aca8c98492aead0673b5738aa5dba85c3a34314
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642228"
---
# <a name="diagnose-and-fix-microsoft-edge-sync-issues"></a>诊断和修复 Microsoft Edge 同步问题

本文针对 Azure Active Directory (Azure AD) 环境中最常遇到的同步问题提供疑难解答指南。 还包括收集故障排除同步问题所需日志的推荐工具。

如果用户跨设备同步浏览器数据出现问题，可以尝试[重置同步](edge-learnmore-reset-data-in-cloud.md)。如果此操作不起作用，管理员或支持人员可以使用以下指南修复同步问题。

> [!NOTE]
> 除非另有说明，否则本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="identity-issues-versus-sync-issues"></a>标识问题与同步问题

在开始之前，了解标识问题和同步问题之间的区别是非常重要的。 在浏览器中维护用户标识的一个常见用例是支持同步。因此，标识问题经常与同步问题混淆。 在开始排除同步故障之前，请了解标识和同步问题的区别。

在将某个问题视为同步问题之前，请检查用户是否已使用有效帐户登录浏览器。

下一个屏幕截图显示了标识错误的示例。 错误为“**最后令牌错误，EDGE_AUTH_ERROR: 3, 54, 3ea**”，它位于**凭据**下的 *edge://sync-internals* 中： 

:::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-identity-issue.png" alt-text="最后令牌错误 EDGE_AUTH_ERROR: 3, 54, 3ea":::

## <a name="common-sync-issues"></a>常见同步问题

### <a name="issue-cant-access-m365-or-azure-information-protection-subscription"></a>问题：无法访问 M365 或 Azure 信息保护订阅

你是不是以前拥有的 M365 或 Azure 信息保护 (AIP) 订阅已过期，然后替换成了新订阅？ 如果是，则租户 ID 已更改，需要重置服务数据。 请参阅**遇到密码器错误**问题中有关重置数据的说明。

### <a name="issue-sync-is-not-available-for-this-account"></a>问题：“此帐户无法使用同步功能。”

如果 Azure Active Directory 帐户遇到此错误，或 *edge://sync-internals* 中出现 DISABLED_BY_ADMIN，请按顺序执行下一过程中的步骤，直到问题得到解决。

> [!NOTE]
> 由于此错误的来源通常需要在 Azure Active Directory 租户中更改配置，因此这些故障排除步骤只能由租户管理员执行，而不能由最终用户执行。

1. 验证企业租户是否具有受支持的 M365 订阅。 [此处](/azure/information-protection/activate-office365)提供了可用订阅类型的当前列表。 如果租户没有受支持的订阅，他们可以单独购买 Azure 信息保护，也可以升级到受支持的某个订阅。
2. 如果具有受支持的订阅，请验证租户是否具有可用的 Azure 信息保护 (AIP)。 有关检查 AIP 状态以及在必要时激活 AIP 的说明，请参阅[此处](/azure/information-protection/activate-office365)。
3. 如果步骤 2 显示 AIP 处于活动状态，但仍无法使用同步功能，请启用企业状态漫游 (ESR)。 有关启用 ESR 的说明，请参阅[此处](/azure/active-directory/devices/enterprise-state-roaming-enable)。 请注意，无需将 ESR 保持启用状态。 如果此步骤修复了问题，可以禁用 ESR。
4. 确认 Azure 信息保护未通过载入策略确定作用域。 可以使用 [Get-AadrmOnboardingControlPolicy](/powershell/module/aadrm/get-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell 小程序查看是否启用了作用域功能。 接下来的两个示例将展示无作用域配置和作用域为特定安全组的配置。

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

   如果启用了作用域功能，则应该将受影响的用户添加到相应作用域的安全组，或者删除该作用域。 在下面的示例中，载入将 AIP 的作用域设定成了指示的安全组，应该使用 [Set-AadrmOnboardingControlPolicy](/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell 小程序删除作用域功能。

5. 确认已在租户中启用 IPCv3Service。 [Get-AadrmConfiguration](/powershell/module/aadrm/get-aadrmconfiguration?view=azureipps) PowerShell 小程序可显示该服务的状态。

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-scoped-cfg-example.png" alt-text="检查是否已启用 IPCv3Service。":::

6. 如果未能解决问题，请与 [Microsoft Edge 支持人员](https://www.microsoftedgeinsider.com/support)联系。

### <a name="issue-stuck-at-setting-up-sync-or-couldnt-connect-to-the-sync-server-retrying"></a>问题：卡在“正在设置同步...”或“无法连接到同步服务器。 正在重试…”环节

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
   - [Windows 通知服务终结点](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)。

5. 如果仍未能解决问题，请与 [Microsoft Edge 支持人员](https://www.microsoftedgeinsider.com/support)联系。

### <a name="issue-cryptographer-error-encountered"></a>问题：遇到密码器错误

此错误显示在 *edge://sync-internals* 中的“**类型信息**”下，它可能意味着需要重置用户的服务器端数据。 以下示例显示加密错误消息：
<br>"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered".

1. 重新启动 Microsoft Edge 并导航到 *edge://sync-internals*，检查“**AAD 账户密钥状态**”部分
   - “Last MIP Result”中为“Success”：该密码器错误意味着服务器数据在加密时使用的可能是丢失的密钥。 需要重置数据才能恢复同步。
   - “Last MIP Result”中为“No permissions”：这可能是由 Azure AD 更改或租户订阅更改引起的。 需要重置数据才能恢复同步。
   - 其他错误可能意味着服务器配置问题。
2. 如果需要重置数据，请参阅[重置云中的 Microsoft Edge 数据](edge-learnmore-reset-data-in-cloud.md)。

### <a name="issue-sync-has-been-turned-off-by-your-administrator"></a>问题：“管理员已禁用同步。”

确保未设置 [SyncDisabled 策略](./microsoft-edge-policies.md#syncdisabled)。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge 企业同步](microsoft-edge-enterprise-sync.md)
- [Microsoft Edge 和企业状态漫游](microsoft-edge-enterprise-state-roaming.md)
- [Microsoft Edge 企业版登录页面](https://aka.ms/EdgeEnterprise)