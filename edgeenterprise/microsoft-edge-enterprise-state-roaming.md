---
title: Microsoft Edge 和企业状态漫游
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 和企业状态漫游
ms.openlocfilehash: 34ee5bf7970834a2e2211db9e2c0bc6ae99bcd6b
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "11979006"
---
# <a name="microsoft-edge-and-enterprise-state-roaming"></a>Microsoft Edge 和企业状态漫游

本文介绍了为更好地支持跨平台和设备同步，加入企业状态漫游 (ESR) 产品的 Microsoft Edge 进行了哪些更改。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="introduction"></a>简介

通过 Windows 10，[Azure Active Directory (Azure AD)](/azure/active-directory/fundamentals/active-directory-whatis) 用户能够将其用户设置和应用程序设置数据安全地同步到云。 [企业状态漫游 (ESR)](/azure/active-directory/devices/enterprise-state-roaming-overview) 还让用户在不同 Windows 设备上具有统一的体验，并缩短了配置新设备所需的时间。

它的同步解决方案是采用 Chromium 平台的 Microsoft Edge 的一部分，现在已与 Windows 同步框架断开连接。 这会影响到 Microsoft Edge 与 ESR 产品的关系。

> [!IMPORTANT]
> 新版 Microsoft Edge 未加入 ESR 产品。

## <a name="whats-changing-with-microsoft-edge"></a>Microsoft Edge 有何变化？

在新版 Microsoft Edge 中，同步解决方案不会绑定到 Windows 同步生态系统。 这使我们可以在所有平台上提供 Microsoft Edge，例如 Windows 7、Windows 8 .1、iOS、Android 和 macOS。 另外这还使我们可以为 Windows 上的非主要帐户提供同步。 此外，我们还可以使用比 Windows 更频繁且更灵活的发行节奏来交付 Microsoft Edge。 （有关详细信息，请参阅[用于支持下一版 Microsoft Edge 的 Windows 更新](microsoft-edge-sysupdate-windows-updates.md)。 所有这些因素都突出显示了重新评估 Microsoft Edge 加入 ESR 产品的必要性。

ESR 设计为 Windows 产品，其中包含对 Windows 设备中数据的处理方式的承诺，但 Microsoft Edge 同步将不局限于 Windows 设备。 此外，随着数据在这些设备之间漫游，在 ESR 上下文中定义 Microsoft Edge 同步产品会很困难。 为了简化同步的工作和管理方式，以及为了适应突出显示的更改，我们已决定让 Microsoft Edge 退出 ESR 产品。

## <a name="does-this-mean-enterprises-will-lose-the-abilities-they-had-as-part-of-esr"></a>这是否意味着企业不再具备 ESR 所提供的功能？

否。 Microsoft Edge 将继续支持 ESR 产品中提供的大部分功能。

### <a name="unified-experience-across-devices-and-new-device-configuration-time"></a>设备间的统一体验和新的设备配置时间

当用户使用 Azure Active Directory（Azure AD 帐户）登录到自己的 Windows 设备时，Microsoft Edge 将在首次启动新浏览器时隐式继承该标识。

在用户明确同意在新版 Microsoft Edge 中打开同步后，浏览器将同步所有浏览器数据，如收藏夹、密码和历史记录。 这确保了可获得跨设备统一体验，并缩短了个性化设置浏览器所需的时间。

### <a name="separation-of-corporate-and-consumer-data"></a>分离公司和消费者数据

组织拥有其数据的控制权，不会在消费者云帐户中掺混公司数据，也不会在企业云帐户中掺混消费者数据。

### <a name="enhanced-security"></a>增强的安全性

在数据离开用户 Windows 10 设备之前通过使用 Azure 信息保护自动对其加密，并且数据在云中保持静态加密状态。 所有内容在云（命名空间除外）中保持静态加密，例如设置名称。

### <a name="monitoring"></a>监视

我们将通过与 Azure AD 门户集成，控制并显示贵组织中的哪些人在哪些设备中同步设置。 在未来版本中将启用该功能。

### <a name="management"></a>管理

管理员可控制组织中哪些成员能够启用同步。请参阅 [配置 Microsoft Edge 同步](microsoft-edge-enterprise-sync.md#configure-microsoft-edge-sync)和[同步组策略](microsoft-edge-enterprise-sync.md#sync-group-policies)。 此外，用户可以针对每台设备打开/关闭同步，并分别切换每个数据属性以进行同步。

### <a name="key-management"></a>密钥管理

同步功能利用 Azure 信息保护 (AIP)，仅为用户和企业管理员保护同步数据。 AIP 既支持 Microsoft 托管（默认），也引入了你自己的密钥以用于云密钥管理。 贵组织使用的云密钥管理策略对于 Microsoft Edge 是透明的，对同步功能没有任何影响。

> [!IMPORTANT]
> [保留自己的密钥 (HYOK)](/azure/information-protection/configure-adrms-restrictions)，但不支持 Active Directory Rights Management Service。

## <a name="summary-of-sync-attributes"></a>同步属性摘要

以下数据属性将在新版本 Microsoft Edge 首次启动时同步：

- 收藏夹
- 密码
- 表单填写
- 历史记录
- 打开标签页（会话）
- 设置（首选项）
- 扩展

前述属性列表不同于可在 Microsoft Edge 旧版中同步的属性。 （有关 Microsoft Edge 旧版设置的详细信息，请参阅 [Windows 10 漫游设置](/azure/active-directory/devices/enterprise-state-roaming-windows-settings-reference)）。用户可以使用 Microsoft Edge 设置有选择地启用/禁用这些属性。 鉴于两个版本之间属性（如“历史记录”）的不同，系统可能会要求用户再次授予同步许可。

> [!NOTE]
> 与 Microsoft Edge 旧版不同的是，新版 Microsoft Edge 不会使用 Windows 凭据管理器中的密码，因此不会将密码与 Internet Explorer 或其他使用 Windows 凭据管理器的应用程序同步。

## <a name="terms-of-service"></a>服务条款

Microsoft Edge 同步服务条款已列入 Microsoft 软件许可证，可使用 Microsoft Edge 访问 *edge://terms* 进行查看。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 同步](microsoft-edge-enterprise-sync.md)