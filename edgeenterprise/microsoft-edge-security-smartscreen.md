---
title: 适用于 Microsoft Defender SmartScreen 的 Microsoft Edge 支持
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 适用于 Microsoft Defender SmartScreen 的 Microsoft Edge 支持
ms.openlocfilehash: c09664e6c7785607e40ac53e26c2f377a66f6cef7a6da2b1d53cf15baad29616
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "11727130"
---
# <a name="microsoft-edge-support-for-microsoft-defender-smartscreen"></a>适用于 Microsoft Defender SmartScreen 的 Microsoft Edge 支持

本文介绍使用 Microsoft Defender SmartScreen 的优点，说明了其工作原理，还介绍如何配置此 Microsoft Edge 功能。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

Microsoft Defender SmartScreen 是一项服务，在你浏览 web 时，Microsoft Edge 将使用该服务确保安全。 Microsoft Defender SmartScreen 针对可能从事钓鱼攻击，或尝试通过集中式攻击分发恶意软件的网站提供早期警告系统。 有关详细信息，请观看[视频：Microsoft Edge 上的安全浏览](microsoft-edge-video-security-smartscreen.md)。

> [!NOTE]
> 在 Windows 10 版本 1703 之前，此功能在浏览器中使用时称为 SmartScreen 筛选器，在浏览器之外使用时则称为 Microsoft SmartScreen。

## <a name="the-benefits-of-microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen 的好处

Microsoft Defender SmartScreen 提供了几个优点，下面的列表对此进行了概述。 这些优点在 [Microsoft Defender SmartScreen 文档](/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview#benefits-of-windows-defender-smartscreen)中详细叙述。 优点有：

- 防网络钓鱼和反恶意软件支持
- 基于信誉的 URL 和应用保护
- 操作系统集成
- 改进的启发和诊断数据
- 通过组策略和 Microsoft Intune 进行管理
- 阻止与潜在有害应用程序关联的 URL

## <a name="understand-how-microsoft-defender-smartscreen-works"></a>了解 Microsoft Defender SmartScreen 的工作原理

许多输入会导致 Microsoft Defender SmartScreen 警告。 数据接收自多个来源，包括用户反馈、数据提供商和智能模型。 此数据用于帮助识别潜在的恶意内容。 Microsoft Defender SmartScreen 还检查已下载的应用或应用安装程序是否有恶意。 在这两种情况下，Microsoft Defender SmartScreen 都会警告用户有关可疑内容的信息。

### <a name="site-analysis"></a>站点分析

Microsoft Defender SmartScreen 可通过以下方法确定某站点是否为潜在恶意网站：

- 分析已访问的页面，发现可以行为的迹象。
- 检查已访问站点，以获取所报告的钓鱼网站的动态记录。

如果 Microsoft Defender SmartScreen 确定某个页面是恶意的，将显示一个警告页面，通知用户该站点被报告为不安全。 下一个屏幕截图显示了用户尝试打开恶意网站时出现的 Microsoft Defender SmartScreen 警告页面的示例。

![Microsoft Defender SmartScreen 阻止指向外部网站的链接](media/microsoft-edge-security-smartscreen/microsoft-edge-smartscreen-warning.png)

用户可以选择在警告消息中将网站报告为安全或不安全。 有关详细信息，请参阅“[如何报告网站](/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-set-individual-device#how-users-can-report-websites-as-safe-or-unsafe)”。

### <a name="file-analysis"></a>文件分析

Microsoft Defender SmartScreen 基于许多标准（例如下载流量、下载历史记录、过去的防病毒结果和 URL 信誉）来确定下载的应用或应用安装程序是否有潜在恶意。

- 自动下载信誉已知安全的文件，不发出任何通知。  
- 信誉已知恶意的文件会显示警告，以使用户知道文件不安全，已报告为恶意。 下一个屏幕截图是针对恶意文件的警告示例。

  ![Microsoft Defender SmartScreen 将对具有恶意信誉的文件阻止通知](media/microsoft-edge-security-smartscreen/ms-edge-smartscreen-known-malicious.png)

- 未知文件会显示警告，以使用户知道下载的文件大小未知，并请注意。 下一个屏幕截图是针对未知文件的警告示例。

  ![Microsoft Defender SmartScreen 将会对信誉未知的文件阻止通知](media/microsoft-edge-security-smartscreen/ms-edge-smartscreen-unknown-malicious.png)

并非所有未知程序都是恶意的，未知警告旨在为需要它的用户提供上下文和指导，特别是如果警告是意外的。

  ![保留恶意信誉文件](media/microsoft-edge-security-smartscreen/ms-edge-smartscreen-unknown-malicious-keep.png)

但是用户仍可通过点击 **... | 保留 | 显示更多 | 仍要保留**来下载并运行应用程序。

> [!TIP]
> **仅供企业用户参考。** 默认情况下，Microsoft Defender SmartScreen 允许用户忽视警告。 由于用户交互可能存在风险，因此建议查看以下[推荐的组策略设置](/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-available-settings#recommended-group-policy-and-mdm-settings-for-your-organization)。

你将看到 Microsoft Defender SmartScreen 如何使用[演示网站](https://demo.smartscreen.msft.net/)来响应不同的情况。

## <a name="microsoft-defender-smartscreen-and-user-privacy"></a>Microsoft Defender SmartScreen 和用户隐私

用户使用信誉检查系统浏览 Internet 时，Microsoft Defender SmartScreen 可以保护用户。 Microsoft Edge 将有关 URL 或文件的相关信息传递给 Microsoft Defender SmartScreen 服务以启动信誉检查。 此检查将网站或文件与危险已知的站点和文件动态列表进行比较。 所有 Microsoft Defender SmartScreen 服务请求均可使用 TLS 加密进行。 服务返回信誉检查的结果，可能会导致 Microsoft Edge 显示网站或文件的警告。 这些结果将本地存储在设备上。

Microsoft Defender SmartScreen 服务存储有关信誉检查的数据。 识别到新站点后，该服务将添加到已知的恶意 URL 和文件动态数据库中。 此数据存储在安全的 Microsoft 服务器上，仅用于 Microsoft 安全服务。 此数据绝不会以任何方式用于识别或定位用户。 清除浏览缓存将清除所有本地存储的 Microsoft Defender SmartScreen URL 数据。 清除下载历史记录将删除本地存储的任何有关文件下载的 SmartScreen 数据。

有关 Microsoft Defender SmartScreen 和 Microsoft Edge 上的隐私的详细信息，请阅读 [Microsoft Edge 隐私白皮书](/microsoft-edge/privacy-whitepaper#smartscreen)。

## <a name="microsoft-defender-smartscreen-setup-for-admins"></a>Microsoft Defender SmartScreen 管理员设置

管理员可以使用组策略、Microsoft Intune 或移动设备管理（MDM）设置配置 Microsoft Defender SmartScreen。 根据你设置 Microsoft Defender SmartScreen 的方式，你可以向用户显示一个警告页面并让他们继续使用站点，也可以完全阻止站点。

### <a name="microsoft-defender-smartscreen-set-up-using-group-policy"></a>使用组策略设置 Microsoft Defender SmartScreen

有关 SmartScreen 策略的完整列表，请参阅 [Microsoft Defender SmartScreen 设置](./microsoft-edge-policies.md#smartscreen-settings)

### <a name="microsoft-defender-smartscreen-set-up-using-mdm"></a>使用 MDM 设置 Microsoft Defender SmartScreen

有关详细信息，请参阅：

- [适用于 Microsoft Defender SmartScreen 的 Windows Intune 设置](/mem/intune/protect/endpoint-protection-windows-10#windows-defender-smartscreen-settings)
- [MDM 策略设置](/mem/intune/protect/endpoint-protection-windows-10#windows-defender-smartscreen-settings)

## <a name="microsoft-defender-smartscreen-setup-for-users"></a>Microsoft Defender SmartScreen 用户设置

默认情况下，Microsoft Edge 将启用 Microsoft Defender SmartScreen。 若要关闭 Microsoft Defender SmartScreen，转到 *edge://settings/privacy > Services > Microsoft Defender SmartScreen*。 对于与设备上所有 Microsoft Edge 安装相关的配置文件，此设置相同。 此设置不会跨设备同步。 此设置适用于 InPrivate 浏览和来宾模式。 如果设备由组织设置的组策略管理，此配置将在*edge://settings/privacy*中展现出来。

> [!NOTE]
> 用户可以为单个设备设置 Microsoft Defender SmartScreen，除非配置了组策略或 MDM 来阻止它。 有关更多信息，请参阅[在各个设备上设置并使用 Microsoft Defender SmartScreen ](/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-set-individual-device)。

## <a name="frequently-asked-questions"></a>常见问题

### <a name="how-does-the-reputation-check-system-work"></a>信誉检查系统是如何工作的？

浏览网络时，Microsoft Defender SmartScreen 将网站和下载分类为主要流量、危险或未知。 主要流量是被 Microsoft Defender SmartScreen 确定为可信的网站。 如果转到标记为危险的站点，Microsoft Defender SmartScreen 将立即阻止你访问此站点。 转到未知站点时，Microsoft DefenderSmartScreen 会检查其信誉以确定是否应访问此站点。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge 企业版登录页面](https://aka.ms/EdgeEnterprise)
- [视频：Microsoft Edge 上的安全浏览](microsoft-edge-video-security-smartscreen.md)
- [Microsoft Defender SmartScreen 概述](/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview)
- [威胁防护](/windows/security/threat-protection/index)
- [阻止潜在的有害应用程序](./microsoft-edge-potentially-unwanted-apps.md)