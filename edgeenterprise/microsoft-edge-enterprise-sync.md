---
title: Microsoft Edge Enterprise Sync
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 10/21/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Enterprise Sync
ms.openlocfilehash: e51346d9bab83228c42a84a7a14ee45dc9b463a7
ms.sourcegitcommit: b32d8d64ae65dc5a46e47b7c34b0211097a0cc65
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "11133127"
---
# Microsoft Edge Enterprise Sync

本文介绍如何使用 Microsoft Edge 同步你所有已登录设备上的收藏夹、密码和其他浏览器数据。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## 概述

通过 Microsoft Edge 同步，用户可以访问他们所有已登录设备上的浏览数据。 同步支持的数据包括：

- 收藏夹
- 密码
- 地址等（表单填写）
- 收藏
- “设置”

用户同意后即可启用同步功能，并且用户可以针对上面列出的每种数据类型打开或关闭同步功能。

> [!NOTE]
> 将上载其他设备连接和配置数据（如设备名称、品牌和型号），以支持同步功能。

## 必备条件

适用于 Azure Active Directory (Azure AD) 帐户的 Microsoft Edge 同步功能可供以下任何订阅使用：

- Azure AD Premium (P1 和 P2)
- M365 商业高级版
- Office 365 E1及更高版本
- Azure 信息保护 (AIP) (P1& P2)
- 所有 EDU 订阅（Microsoft 教育应用版（学生）或 Microsoft 教育应用版（教职员工）、Exchange Online 学生版或教职员工版、O365 A1 或更高版本、M365 A1 或更高版本，或者适用于学生或教职员的 Azure 信息保护 P1 或 P2）

## 配置 Microsoft Edge 同步功能

可通过 Azure 信息保护 (AIP) 服务获取 Microsoft Edge 同步的配置选项。 为租户启用 AIP 后，无论获得何种许可，所有用户均可同步 Microsoft Edge 数据。 有关如何启用 AIP 的说明，请参阅[此处](https://docs.microsoft.com/azure/information-protection/activate-office365)。

若要限制某一组用户使用同步功能，可为这些用户启用 [AIP 登录控制策略](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps) 。 如果确保所有必需的用户均加入后同步仍不可用，请确保已使用 [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps) PowerShell cmdlet 启用 IPCv3Service。

> [!CAUTION]
> 激活 Azure 信息保护还将允许其他应用程序（如 Microsoft Word 或 Microsoft Outlook）使用 AIP 保护内容。 此外，用于限制 Microsoft Edge 同步的任何载入控制策略也将限制其他应用程序使用 AIP 保护内容。

## Microsoft Edge 和企业状态漫游

新版 Microsoft Edge 是跨平台应用程序，具有用于跨用户的所有设备同步用户数据的扩展作用域，并且不再是 Azure AD 企业状态漫游的一部分。 但是，新版 Microsoft Edge 将履行 ESR 的数据保护承诺，例如引入你自己的密钥的功能。 有关详细信息，请参阅 [Microsoft Edge 和企业状态漫游](microsoft-edge-enterprise-state-roaming.md)。

## 同步组策略

以下组策略会影响 Microsoft Edge 同步：

- [SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled)：完全禁用同步。
- [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled)：禁止保存浏览历史记录和同步。此策略还将禁用打开标签页同步。
- [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled)：配置从同步中排除的类型列表。
- [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled)：允许 Active Directory (AD) 配置文件使用本地存储。 有关更多信息，请参阅 [Active Directory (AD) 用户的本地同步](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync)。
- [ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync)：默认启用同步，且无需用户同意即可同步。  

## 常见问题

### 安全性和服务器/数据合规性

#### 已同步的数据是否已加密？ 

数据使用 TLS 1.2 或更高版本在传输中加密。 大多数的数据类型在休眠时，都会在 Microsoft 服务中使用 AES256 进行额外的加密。 

#### Microsoft Edge 的同步数据存储在哪里？

Azure AD 帐户的同步数据将根据租户 ID 存储在安全服务器中。 例如，在美国注册的租户的数据存储在位于该地区地理位置的服务器上，并使用与 Office 应用程序相同的存储解决方案。

#### 除了同步至 Microsoft Edge 外，数据是否会离开 Microsoft 云？

否。

#### 租户管理员能否使用自己的密钥？

可以，通过 [Azure 信息保护](https://azure.microsoft.com/services/information-protection/)。

#### 企业同步属于哪项服务条款？

服务条款与 Azure AD 订阅的条款相同。 所有 Azure AD 服务条款最终均属于 Microsoft 的[联机服务条款](https://www.microsoft.com/licensing/product-licensing/products)。

#### Microsoft Edge 是否支持政府社区云 (GCC) 高合规性？

目前尚不支持。 GCC 高合规性是 D 层，而 Microsoft Edge 最多支持 C 层。

### 应用同步

#### 对于决定保留旧版 Microsoft Edge 的企业和教育客户，将会发生什么情况？

当前版本的 Microsoft Edge 浏览器将继续加入 ESR 产品/服务。

#### 为什么需要高级 Azure AD 订阅才能进行同步？

企业同步依赖于 Azure 信息保护，它在所有 Azure AD 层中均不可用。

#### Microsoft Edge 同步是否基于企业状态漫游？

否。 ESR 可用于启用同步，但 Microsoft Edge 同步不是 ESR 的一部分。 有关详细信息，请参阅 [Microsoft Edge 同步](microsoft-edge-enterprise-sync.md)和 [Microsoft Edge 和企业状态漫游](microsoft-edge-enterprise-state-roaming.md)。

#### Microsoft Edge 是否支持 Microsoft Edge 和 IE 之间的同步？

尚无支持此同步的计划。 如果你的环境中仍需要 IE 来支持旧版应用，请考虑使用我们的[新 IE 模式](https://docs.microsoft.com/deployedge/edge-ie-mode)。

#### 新的 Microsoft Edge 浏览器是否将与 Microsoft Edge 旧版同步？

否，不会同步。 我们认为连接这两个生态系统将降低新版 Microsoft Edge 同步的可靠性。 我们会确保将现有数据迁移到新版 Microsoft Edge。 用户还可以从他们选择的浏览器导入数据。 这也意味着新版 Microsoft Edge 浏览器将无法与 IE 同步。

### 管理同步

#### 是否可以阻止我的用户与个人租户同步？

无法直接阻止，但你可以使用 [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) 策略确定哪些配置文件可以登录到 Microsoft Edge。

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 和企业状态漫游](microsoft-edge-enterprise-state-roaming.md)
