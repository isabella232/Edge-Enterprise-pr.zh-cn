---
title: Microsoft Edge 对 Windows 信息保护的支持
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 11/15/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 对 Windows 信息保护的支持
ms.openlocfilehash: 5f3dd297e59014cc01a1e8abd4db444b7a4176fb
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2022
ms.locfileid: "12298290"
---
# <a name="microsoft-edge-support-for-windows-information-protection-wip"></a>Microsoft Edge 对 Windows 信息保护 (WIP) 的支持

本文介绍 Microsoft Edge 对 Windows 信息保护 (WIP) 的支持情况。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 81 或更高版本。

## <a name="overview"></a>概述

Windows 信息保护 (WIP) 是一种 Windows 10 功能，可帮助保护企业数据免遭未经授权的或意外的泄露。 随着远程工作的增长，在工作场所之外共享公司数据会增加风险。 在公司设备上进行个人活动和工作活动时，这种风险就会增加。

Microsoft Edge 支持 WIP 以在用户经常共享和分发内容的 Web 环境中帮助保护内容安全。

### <a name="system-requirements"></a>系统要求

以下要求适用于企业中使用 WIP 的设备：

- Windows 10 版本 1607 或更高版本
- 仅 Windows 客户端 SKU
- [WIP 先决条件](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip#prerequisites)中描述的管理解决方案之一

### <a name="windows-information-protection-benefits"></a>Windows 信息保护的优势

WIP 具有以下优势：

- 个人和公司数据之间的明显分离，而不要求员工切换环境或应用。
- 对于现有业务线应用的其他数据保护，而无需更新应用。
- 允许远程擦除 Intune 移动设备管理 (MDM) 注册的设备上的公司数据而不影响个人数据。 
- 有关跟踪问题以及补救措施（例如针对用户的合规性培训）的审核报告。
- 与现有管理系统进行集成以配置、部署和管理 WIP。 一些示例包括 Microsoft Intune、Microsoft Endpoint Configuration Manager 或当前的移动设备管理 (MDM) 系统。

## <a name="wip-policy-and-protection-modes"></a>WIP 策略和保护模式

使用策略可以配置下表中所述的四种保护模式。 有关详细信息，请参阅 [WIP 保护模式](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip#wip-protection-modes)。

| 模式 | 描述 |
|------|-------------|
| 阻止 | WIP 将查找不恰当的数据共享行为并阻止员工完成该操作。 除了在应用之间共享企业数据或在组织网络之外尝试共享之外，此搜索还可以包括向非企业保护的应用共享企业数据。 |
| 允许覆盖 | WIP 将查找不恰当的数据共享，当员工执行某些视为可能不安全的操作时会向他们发出警告。 但是，此管理模式允许员工覆盖策略并共享数据，同时将该操作记录到审核日志。 |
| 静默 | WIP 将静默运行，同时记录不恰当的数据共享，但不会阻止在“允许覆盖”模式下时本来会针对员工交互而发出的任何内容提示。 像应用不恰当地尝试访问网络资源或 WIP 保护的数据等不被允许的操作仍将受到阻止。 |
| 关闭 | WIP 将处于关闭状态，并且不会帮助保护或审核你的数据。 关闭 WIP 后，系统将尝试解密本地连接的驱动器上的任何 WIP 标记文件。 如果重新打开 WIP 保护，以前的解密和策略信息不会自动重新应用。
 |

## <a name="wip-features-supported-in-microsoft-edge"></a>Microsoft Edge 支持的 WIP 功能

Microsoft Edge 从版本 81 开始支持以下功能：

- 地址栏上的公文包图标将指示工作网站。  
- 从工作位置下载的文件会自动加密。
- 以静默/阻止/覆盖模式将工作文件上传到非工作位置。  
- 以静默/阻止/覆盖模式执行文件拖放操作。
- 以静默/阻止/覆盖模式执行剪贴板操作。
- 从非工作配置文件浏览到工作位置会自动重定向到工作配置文件（与 Azure AD 标识相关联）。
- IE 模式支持完整的 WIP 功能。

## <a name="working-with-wip-in-microsoft-edge"></a>在 Microsoft Edge 中使用 WIP

为 Microsoft Edge 启用 WIP 支持后，用户将在访问工作相关信息时看到这一点。 下一个屏幕截图显示了地址栏中的公文包图标，表明可通过浏览器访问工作相关信息。

 ![标记为“工作”的网站的地址栏指示器](./media/microsoft-edge-security-windows-information-protection/microsoft-edge-wip-notify.png)

Microsoft Edge 让用户能够在未批准的网站中共享受保护的内容。 下一个屏幕截图显示了 Microsoft Edge 提示，允许用户在未批准的网站中使用受保护的内容。

 ![受保护内容覆盖提示](./media/microsoft-edge-security-windows-information-protection/microsoft-edge-wip-override.png)

## <a name="configure-policies-to-support-wip"></a>配置策略以支持 WIP

将 WIP 与 Microsoft Edge 配合使用时，需要存在工作配置文件。

### <a name="ensure-the-presence-of-a-work-profile"></a>确保存在工作配置文件

在已加入混合的计算机上，Microsoft Edge 将自动使用 Azure Active Directory (Azure AD) 帐户登录。 若要确保用户不删除此配置文件（WIP 需要此配置文件），请配置以下策略：

- [NonRemovableProfileEnabled](./microsoft-edge-policies.md#nonremovableprofileenabled)

> [!NOTE]
> 如果你的环境未加入混合，则可以按照以下说明加入混合：[规划加入混合 Azure Active Directory 的实现方式](/azure/active-directory/devices/hybrid-azuread-join-plan)。

如果不能选择加入混合，则可以使用本地的 Active Directory 帐户，允许 Edge 使用用户的域帐户自动创建特殊工作配置文件。 请注意，本地帐户可能不会获得 Azure AD 的所有功能，如云同步、Office NTP 等。

#### <a name="active-directory-ad-accounts"></a>Active Directory (AD) 帐户

对于 AD 帐户，必须配置以下策略，使 Microsoft Edge 自动创建一个特殊工作配置文件。

- [ConfigureOnPremisesAccountAutoSignIn](./microsoft-edge-policies.md#configureonpremisesaccountautosignin)

### <a name="windows-policies-for-wip"></a>适用于 WIP 的 Windows 策略

可使用 Windows 策略配置 WIP。 有关详细信息，请参阅[使用 Microsoft Intune 创建和部署 WIP 策略](/windows/security/information-protection/windows-information-protection/overview-create-wip-policy)

## <a name="frequently-asked-questions"></a>常见问题

### <a name="how-do-i-resolve-error-code--2147024540"></a>如何解决错误代码 - 2147024540？

此错误代码对应于以下 Windows 信息保护错误：*ERROR_EDP_POLICY_DENIES_OPERATION: 请求的操作已被 Windows 信息保护策略阻止。有关详细信息，请联系系统管理员。*

当组织已启用 Windows 信息保护 (WIP) 以仅允许具有已批准应用程序的用户访问公司资源时，Microsoft Edge 显示此错误。 在这种情况下，由于 Microsoft Edge 不在已批准的应用程序列表上，因此管理员必须更新 WIP 策略以授予对 Microsoft Edge 的访问权限。

以下屏幕截图显示了如何使用 Microsoft Intune 将 Microsoft Edge 添加为 WIP允许的应用程序。

 ![将 Microsoft Edge 添加为 WIP 应用的 Intune 对话框](./media/microsoft-edge-security-windows-information-protection/microsoft-edge-wip-exemption.png)

如果没有使用 Microsoft Intune，请下载并应用 [WIP 企业 AppLocker 策略](https://download.microsoft.com/download/8/9/9/8995d820-065c-4ab1-aa2a-9d6dc0cd7ffa/MsEdge%20-%20WIP%20Enterprise%20AppLocker%20Policy%20Files.zip)文件中的策略更新。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise) 
- [使用 Windows 信息保护来保护企业数据](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)