---
title: Microsoft Edge 和 Microsoft Defender 应用程序防护
ms.author: srugh
author: AndreaLBarr
manager: seanlyn
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 对 Microsoft Defender 应用程序防护的支持
ms.openlocfilehash: 6273204cc66fa90b1840f279106b3a26d895ca96
ms.sourcegitcommit: 9088e839e82d80c72460586e9af0610c6ca71b83
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2021
ms.locfileid: "11675959"
---
# <a name="microsoft-edge-support-for-microsoft-defender-application-guard"></a>Microsoft Edge 对 Microsoft Defender 应用程序防护的支持

本文介绍 Microsoft Edge 如何支持 Microsoft Defender 应用程序防护（应用程序防护）。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="overview"></a>概述

企业中的安全架构师必须处理生产力与安全性之间的矛盾。 锁定浏览器并且仅允许加载少数受信任的站点相对简单。 这种方法可改进整体安全状态，但生产力会降低。 如果你为提高生产力而减少限制，则会增加风险。 这很难达到平衡！

在不断变化的威胁形势下，即时了解新出现的威胁变得更加困难。 浏览器仍然是客户端设备上的主要攻击面，因为浏览器的基本任务是让用户访问、下载和打开来自不可信来源的不可信内容。 恶意参与者一直在忙于对浏览器进行新形式的社会工程攻击。 安全事件预防或检测/响应策略不能保证 100% 安全。

要考虑的一个关键安全策略是[假设失陷方法](/office365/Enterprise/office-365-monitoring-and-testing#assume-breach-methodology)，这意味着用户接受无论如何努力地抵御攻击，该攻击总会成功一次的观念。 此思维方式要求建立防御机制来遏制损坏，这可确保企业网络和其他资源在这种情况下得到保护。  为 Microsoft Edge 部署应用程序防护符合此策略。

## <a name="about-application-guard"></a>关于应用程序防护

专为 Windows 10 和 Microsoft Edge 设计，应用程序防护使用硬件隔离方法。 这种方法允许在容器中启动不受信任的站点导航。 硬件隔离可帮助企业保护其企业网络和数据，以防用户访问受到威胁或恶意的站点。

企业管理员定义什么是受信任的站点、云资源和内部网络。 不在受信任站点列表中的所有内容都被视为不可信内容。 这些站点与企业网络和用户设备上的数据相隔离。

有关详细信息：

- 观看我们的视频[使用应用程序防护实现 Microsoft Edge 浏览器隔离](microsoft-edge-video-security-application-guard.md)
- 阅读[什么是应用程序防护，以及它是如何工作的？](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview#what-is-application-guard-and-how-does-it-work)

下一个屏幕截图显示应用程序防护的消息示例，它显示用户正在安全空间中浏览。

![应用程序防护安全浏览消息](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-1.png)

## <a name="whats-new"></a>新增功能

新版 Microsoft Edge 浏览器中的应用程序防护支持与 Microsoft Edge 旧版具有同等的功能，并包括多项改进。

### <a name="favorites-synchronizing-from-the-host-to-the-container"></a>从主机同步到容器的收藏夹

我们的一些客户一直要求在“应用程序防护”中实现主机浏览器和容器之间的收藏夹同步。 从 Microsoft Edge 版本 91 开始，用户现在可以选择配置“应用程序防护”以将其收藏夹从主机同步到容器。 这确保了容器上也可显示新的收藏夹。

可通过策略控制此支持。 可以更新 Edge 策略 [ApplicationGuardFavoritesSyncEnabled](/deployedge/microsoft-edge-policies#applicationguardfavoritessyncenabled) 以启用或禁用收藏夹同步。

> [!Note]
> 出于安全原因，收藏夹同步仅可从主机同步到容器，而不无法反过来同步。 为了确保在主机和容器之间有一个统一的收藏夹列表，我们已在容器内禁用了收藏夹管理。

### <a name="identify-network-traffic-originating-from-the-container"></a>标识源自容器的网络流量

多个客户在特定配置中使用 WDAG，他们想要识别来自容器的网络流量。 其中的一些方案包括:

- 若要限制仅访问少数几个不受信任的网站
- 仅允许从容器中访问 Internet

从 Microsoft Edge 版本 91 开始，内置支持对来自“应用程序防护”容器的网络流量进行标记，允许企业使用代理筛选掉流量并应用特定的策略。 可以使用标头来标识哪些流量通过容器或主机使用 [ApplicationGuardTrafficIdentificationEnabled](/deployedge/microsoft-edge-policies#applicationguardtrafficidentificationenabled)。

### <a name="extension-support-inside-the-container"></a>容器内的扩展支持

容器内的扩展支持是客户的首要请求之一。 场景范围从希望在容器内运行广告拦截器以提高浏览器性能，到能够在容器内运行自定义的本地扩展。

从 Microsoft Edge 版本 81 开始，现在支持在容器中安装扩展。 可通过策略控制此支持。 在 [ExtensionInstallForcelist](./microsoft-edge-policies.md#extensioninstallforcelist) 策略中使用的 `updateURL` 应作为中性资源添加到应用程序防护使用的网络隔离策略中。

容器支持的一些示例包括以下场景：

- 强制在主机上安装扩展
- 从主机中删除扩展
- 主机上阻止的扩展

> [!NOTE]
> 也可以从扩展存储区中手动将单个扩展安装在容器内。 手动安装的扩展仅在启用“[允许持久性](/windows/security/threat-protection/microsoft-defender-application-guard/configure-md-app-guard#application-specific-settings)”策略时才保留在容器中。

### <a name="identifying-application-guard-traffic-via-dual-proxy"></a>通过双代理识别应用程序防护流量

一些企业客户正在部署适用于特定用例的应用程序防护，他们需要识别来自 Microsoft Defender 应用程序防护容器的代理级别 web 流量。 从稳定渠道版本 84 开始，Microsoft Edge 将支持双代理来满足这一要求。 可使用 [ApplicationGuardContainerProxy](./microsoft-edge-policies.md#applicationguardcontainerproxy) 策略配置此功能。

下图显示了 Microsoft Edge 双代理的体系结构。

![应用程序防护的双代理体系结构](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-dual-proxy.png)

### <a name="diagnostic-page-for-troubleshooting"></a>用于故障排除的诊断页面

用户的另一个痛点是在报告问题后对设备上的应用程序防护配置进行故障排除。 Microsoft Edge 有一个诊断页面 (`edge://application-guard-internals`)，用于对用户问题进行故障排除。 其中一个诊断功能是可以根据用户设备上的配置检查 URL 信任。

下一个屏幕截图显示了多选项卡诊断页面，用于帮助诊断用户在设备上报告的问题。

![应用程序防护诊断页面](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-2.png)

### <a name="microsoft-edge-updates-in-the-container"></a>容器中的 Microsoft Edge 更新

容器中的 Microsoft Edge 旧版更新是 Windows 操作系统更新周期的一部分。 由于新版本的 Microsoft Edge 更新独立于 Windows 操作系统，因此不再依赖于容器更新。 主机 Microsoft Edge 的频道和版本可在容器内复制。

## <a name="prerequisites"></a>必备条件

以下要求适用于将应用程序防护与 Microsoft Edge 配合使用的设备：

- Windows 10 1809 (RS5) 及更高版本。
- 仅 Windows 客户端 SKU

  > [!NOTE]
  > 应用程序防护仅在 Windows 10 专业版和 Windows 10 企业版 SKU 上受支持。

- [软件要求](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard#software-requirements)中介绍的管理解决方案之一

## <a name="how-to-install-application-guard"></a>如何安装应用程序防护

以下文章提供了使用 Microsoft Edge 安装、配置和测试应用程序防护所需的信息。

- [系统要求](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)
- [安装 Microsoft Defender 应用程序防护](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)
- [配置 Microsoft Defender 组策略设置](/windows/security/threat-protection/microsoft-defender-application-guard/configure-md-app-guard)
- [测试应用程序防护](/windows/security/threat-protection/microsoft-defender-application-guard/test-scenarios-md-app-guard)

## <a name="frequently-asked-questions"></a>常见问题

### <a name="does-application-guard-work-in-ie-mode"></a>应用程序防护是否可在 IE 模式下工作？

IE 模式支持应用程序防护功能，但我们预计不会在 IE 模式下过多地使用此功能。 建议为受信任的内部站点列表部署 IE 模式，而应用程序保护仅针对不受信任的站点。 确保所有 IE 模式的网站或 IP 地址也添加到网络隔离策略中，以便应用程序防护将其视为受信任的资源。

### <a name="do-i-need-to-install-the-application-guard-chrome-extension"></a>是否需要安装应用程序防护 Chrome 扩展？

否，Microsoft Edge 本身支持应用程序防护功能。 实际上，应用程序防护 Chrome 扩展配置在 Microsoft Edge 中不受支持。

### <a name="can-employees-download-documents-from-the-application-guard-edge-session-onto-host-devices"></a>员工是否可以将应用程序防护 Edge 会话中的文档下载到主机设备上？

在 Windows 10 企业版 版本 1803 中，用户可以将文档从独立的应用程序防护容器下载到主机电脑。 此功能由策略管理。

在 Windows 10 企业版 版本 1709 或 Windows 10 Professional 版本 1803 中，无法将文件从独立的应用程序防护容器下载到主计算机。 但是，员工可以使用打印为 PDF 或打印为 XPS 选项并将这些文件保存至主机设备。

### <a name="can-employees-copy-and-paste-between-the-host-device-and-the-application-guard-edge-session"></a>员工是否可以在主机设备与应用程序防护 Edge 会话之间进行复制和粘帖操作？

根据组织的设置，员工可以在隔离容器 (.bmp) 和粘贴图像和文本。

### <a name="why-dont-employees-see-their-favorites-in-the-application-guard-edge-session"></a>为什么员工在应用程序防护边缘会话中看不到他们的收藏夹？

根据组织的设置，收藏夹同步可能已关闭。 若要管理策略，请参阅：Microsoft Edge 和 Microsoft Defender 应用程序防护 |Microsoft Docs。

### <a name="why-arent-employees-able-to-see-their-extensions-in-the-application-guard-edge-session"></a>为什么员工无法查看应用程序防护边缘会话中的扩展？

请确保在应用程序防护配置上启用扩展策略。

### <a name="my-extension-doesnt-seem-to-work-in-edge-application-guard"></a>我的扩展似乎在 Edge 应用程序防护中不起作用？

如果在配置中为 MDAG 启用了扩展策略，请检查扩展是否要求本机邮件处理组件，应用程序防护容器中不支持这些扩展。

### <a name="im-trying-to-watch-playback-video-with-hdr-why-is-the-hdr-option-missing"></a>我尝试观看具有 HDR 的播放视频，为什么缺少 HDR 选项？

为了使 HDR 视频播放在容器中正常工作，需要在应用程序防护中启用 vGPU 硬件加速。

### <a name="are-there-any-other-platform-related-faqs"></a>是否有其他与平台相关的常见问题？

是。 [常见问题 - Microsoft Defender 应用程序防护](/windows/security/threat-protection/microsoft-defender-application-guard/faq-md-app-guard) 

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [Microsoft Defender 高级威胁防护](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [视频：使用应用程序防护实现 Microsoft Edge 浏览器隔离](https://www.youtube.com/watch?v=zQjaRqNXMqw&t=3s)
