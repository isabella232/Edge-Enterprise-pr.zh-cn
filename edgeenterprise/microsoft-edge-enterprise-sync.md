---
title: 配置 Microsoft Edge 企业同步
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 03/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 用于配置 Microsoft Edge 以同步收藏夹、密码和其他浏览器数据的管理员和用户选项。
ms.openlocfilehash: bfaa1db297093d0b0655a8d217aefcd59d11ac5e
ms.sourcegitcommit: 86e0de9b27ad4297a6d5a57c866d7ef4fc7bb0cd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400136"
---
# <a name="configure-microsoft-edge-enterprise-sync"></a>配置 Microsoft Edge 企业同步

本文介绍了管理员如何配置 Microsoft Edge，以便在所有登录设备上同步用户收藏夹、密码和其他浏览器数据。

> [!NOTE]
> 除非另有说明，否则本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="overview"></a>概述

通过 Microsoft Edge 同步，用户可以访问他们所有已登录设备上的浏览数据。 同步支持的数据包括：

- 收藏夹
- 密码
- 地址等（表单填写）
- 收藏
- “设置”
- 扩展
- 打开选项卡（在 Microsoft Edge 版本 88 中可用）
- 历史记录（在 Microsoft Edge 版本 88 中可用）

用户同意后即可启用同步功能，并且用户可以针对上面列出的每种数据类型打开或关闭同步功能。 如果用户遇到同步问题，他们需要依次选择“**设置**” > “**配置文件**” > “**重置同步**”来重置同步。

> [!NOTE]
> 将上载其他设备连接和配置数据（如设备名称、品牌和型号），以支持同步功能。

## <a name="prerequisites"></a>必备条件

适用于 Azure Active Directory (Azure AD) 帐户的 Microsoft Edge 同步功能可供以下任何订阅使用：

- Azure AD Premium（P1 或 P2）
- M365 商业高级版
- Office 365 E1 及更高版本
- Azure 信息保护 (AIP)（P1 或 P2）
- 所有 EDU 订阅（Microsoft 教育应用版（学生）或 Microsoft 教育应用版（教职员工）、Exchange Online 学生版或教职员工版、O365 A1 或更高版本、M365 A1 或更高版本，或者适用于学生或教职员的 Azure 信息保护 P1 或 P2）

## <a name="sync-group-policies"></a>同步组策略

管理员可以使用以下组策略配置和管理 Microsoft Edge 同步：

- [SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled)：完全禁用同步。
- [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled)：禁止保存浏览历史记录和同步。此策略还将禁用打开选项卡同步。
- [AllowDeletingBrowserHistory](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory)：当此策略设置为禁用时，还将禁用历史记录同步。
- [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled)：配置从同步中排除的类型列表。
- [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled)：允许 Active Directory (AD) 配置文件使用本地存储。 有关更多信息，请参阅 [Active Directory (AD) 用户的本地同步](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync)。
- [ForceSync：]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync)默认启用同步，无需用户同意。  

## <a name="configure-microsoft-edge-sync"></a>配置 Microsoft Edge 同步

Azure 信息保护 (AIP) 服务提供了 Microsoft Edge 同步的配置选项。 为租户启用 AIP 后，无论获得何种许可，所有用户均可同步 Microsoft Edge 数据。 有关如何启用 AIP 的说明，请参阅[此处](https://docs.microsoft.com/azure/information-protection/activate-office365)。

若要限制某一组用户使用同步功能，可为这些用户启用 [AIP 登录控制策略](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true) 。 如果确保所有必需的用户均加入后同步仍不可用，请确保已使用 [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true) PowerShell cmdlet 启用 IPCv3Service。

> [!CAUTION]
> 激活 Azure 信息保护还将允许其他应用程序（如 Microsoft Word 或 Microsoft Outlook）使用 AIP 保护内容。 此外，用于限制 Microsoft Edge 同步的任何载入控制策略也将限制其他应用程序使用 AIP 保护内容。

## <a name="microsoft-edge-and-enterprise-state-roaming-esr"></a>Microsoft Edge 和企业状态漫游 (ESR) 

Microsoft Edge 是一个跨平台应用程序，扩展了跨用户的所有设备同步用户数据的范围，并且不再是 Azure AD 企业状态漫游的一部分。 但是，Microsoft Edge 将履行 ESR 的数据保护承诺，例如能够引入你自己的密钥。 有关详细信息，请参阅 [Microsoft Edge 和企业状态漫游](microsoft-edge-enterprise-state-roaming.md)。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge 企业同步](microsoft-edge-enterprise-sync.md)
- [诊断和修复 Microsoft Edge 同步问题](microsoft-edge-troubleshoot-enterprise-sync.md)
- [Microsoft Edge 和企业状态漫游](microsoft-edge-enterprise-state-roaming.md)
- [Microsoft Edge 企业版登录页面](https://aka.ms/EdgeEnterprise)
