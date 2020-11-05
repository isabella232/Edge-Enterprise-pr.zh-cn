---
title: 有关企业中 Edge 的常见问题
ms.author: jwhit
author: jwhit-MSFT
manager: laurawi
ms.date: 11/04/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 有关在企业中部署 Microsoft Edge 的常见问题
ms.openlocfilehash: e689967cbad950e2969535bad0dd63d5d7081798
ms.sourcegitcommit: 12827458f6217f443128e826c1d18d36d401d03b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2020
ms.locfileid: "11154317"
---
# 有关企业中 Microsoft Edge 的常见问题

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## 我怎么知道我拥有哪个版本的 Microsoft Edge？

在 Microsoft Edge 右上角，单击省略号图标 (**…**)，然后单击**设置**。 选择**关于 Microsoft Edge** 以查看你的 Microsoft Edge 版本。

## Internet Explorer 11 会继续接收更新么？

我们致力于使 Internet Explorer 成为受支持、可靠和安全的浏览器。 Internet Explorer 仍然是 Windows 的组件，并遵循其安装所在操作系统的支持生命周期。 有关详细信息，请参阅[生命周期常见问题解答 - Internet Explorer](https://support.microsoft.com/help/17454/)。 尽管我们会继续支持和更新 Internet Explorer，但最新功能和平台更新将仅在 Microsoft Edge 中提供。

## 在试用新版本时能否同时运行 Microsoft Edge 的当前版本（旧版 Microsoft Edge）？

是的，可以。 2020 年 1 月 15 日之后，Microsoft Edge 的新版本（基于 Chromium）将分发到运行 Windows 10 版本 1803 或更高版本的家庭版和专业版设备。 此更新中排除了加入域的设备。 有关详细信息，请参阅 [Microsoft Edge 更新概述](https://docs.microsoft.com/deployedge/microsoft-edge-blocker-toolkit#overview)。 在试用 Microsoft Edge 的下一版本时，可同时装有旧版 Microsoft Edge。 有关详细信息，请参阅[如何访问旧版本的 Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-access-old-edge)。 此外，每个新的 Microsoft Edge 渠道也都支持同时安装。 有关详细信息，请参阅 [Microsoft Edge 渠道概述](https://docs.microsoft.com/deployedge/microsoft-edge-channels)。

## Microsoft Edge （基于 Chromium）支持 Silverlight 或 Java 这样的 ActiveX 控件或 BHO 么？

否。 Microsoft Edge 不支持 Silverlight 或 Java 这样的 ActiveX 控件或 BHO。 但是，如果在 Internet Explorer 11 上运行使用 ActiveX 控件、BHO 或传统文档模式的 web 应用，则可以将其配置为采用 IE 模式在新 Microsoft Edge 上运行。 有关详细信息，请参阅“[在 Microsoft Edge 上配置 IE 模式](https://docs.microsoft.com/DeployEdge/edge-ie-mode)。

## 是从 Microsoft Edge 的当前版本移植收藏夹，还是必须我自己重新添加？

目前，Microsoft Edge 支持从现有的 Microsoft Edge、Chrome、Internet Explorer 和 Firefox 安装中导入（在 Win10 上）。 导入功能支持以下设置：书签、历史记录、密码和自动填充（支付、地址和一般形式）。 你可以选择从首次运行体验或从浏览器设置进行导入。  

## Stable、Beta、Dev 和 Canary 渠道/版本之间有什么区别？

Microsoft Edge 下一版本的 Stable 渠道是我们提供的最稳定渠道，其中包含多项侧重于企业的功能，可供你在组织内进行[试用和评估](https://aka.ms/EdgeEnterprise)。 通过 Beta 渠道，可通过一组有代表性的用户验证下一个 Stable 版本。 大约每六周更新一次 Stable 和 Beta 渠道。 Dev 和 Canary 渠道将继续分别每周和每日更新一次。 脱机安装程序（MSI 和 PKG 文件）仅适用于 Stable、Beta 和 Dev 渠道。 有关详细信息，请参阅 [Microsoft Edge 渠道概述](https://docs.microsoft.com/deployedge/microsoft-edge-channels)。

## Microsoft Edge 的新版本支持何种扩展？

Microsoft Edge 支持来自 [Microsoft Edge Insider 加载项](https://go.microsoft.com/fwlink/?linkid=2081222)和 [Chrome Web Store](https://go.microsoft.com/fwlink/?linkid=2072338) 的扩展。

## 你是否支持移动设备管理 (MDM) 和 Microsoft Intune？

是。 现已支持使用 Microsoft Intune 和移动设备管理 (MDM) 在 Windows 10 上配置 Microsoft Edge。 有关详细信息，请参阅[使用 Microsoft Intune 配置 Microsoft Edge](configure-edge-with-intune.md) 以及[使用移动设备管理配置 Microsoft Edge](configure-edge-with-mdm.md)。

## WSUS 支持新 Microsoft Edge 的初始部署？

是。 在[Microsoft 更新目录](https://www.catalog.update.microsoft.com/Search.aspx?q=the%20new%20microsoft%20edge%20for%20windows)中，有一些软件包可以用于通过WSUS初始部署的新的 Microsoft Edge。 初始部署后，默认配置自动更新。 有关更多信息，请参阅[ WSUS 中的用于Windows 10的新Microsoft Edge的更新，版本为1809、1903、1909和2004：2020年10月29日](https://support.microsoft.com/help/4584642/update-in-wsus-for-the-new-microsoft-edge)。

可以通过配置管理工具进行手动更新，例如[ConfigMgr](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-edge?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json)。

## 另请参阅

- [Microsoft Edge 文档登录页面](https://docs.microsoft.com/DeployEdge/)
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
