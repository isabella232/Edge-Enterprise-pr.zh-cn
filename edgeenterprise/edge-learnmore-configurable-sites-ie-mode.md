---
title: IE 模式下 Microsoft Edge 和可配置网站
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: IE 模式下 Microsoft Edge 和可配置网站
ms.openlocfilehash: 0248ecd394acee5773751c0685969e3d40940431
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "11978920"
---
# <a name="learn-about-configurable-sites-in-ie-mode"></a>了解 IE 模式下可配置网站

本文将介绍 Microsoft Edge 中使用 IE 模式时企业模式网站列表的“可配置网站”功能。

## <a name="prerequisites"></a>必备条件

- Windows 更新

  - Windows 10 版本 1909，Windows Server 版本 1909 – KB4550945 或更高版本
  - Windows 10 版本1903，Windows Server 版本 1903 – KB4550945 或更高版本
  - Windows 10 版本 1809、Windows Server 版本 1809 和 Windows Server 2019 - KB4550969 或更高版本
  - Windows 10 版本 1803 – KB4550944 或更高版本
  - Windows 10 版本1607、Windows Server 2016-KB4556826 或更高版本
  - Windows 10 初始版本，2015 年 7 月 - KB4550947 或更高版本
  - Windows 8.1 – KB4556798 或更高版本

- Microsoft Edge 版本 83 或更高版本
- 使用企业模式网站列表配置的 [IE 模式](./edge-ie-mode.md)

## <a name="overview"></a>概述

在企业模式网站列表中配置需要 IE 模式的网站，可良好适用于具有旧版应用程序的大多数环境。 但是，在某些情况下，此方法不是将网站的子集配置为以 IE 模式打开，而无需在 IE 模式下呈现整个域。 例如，如果你的环境中同时包含运行于单个服务器上的新版和旧版应用程序，你想要灵活地在 IE 模式下呈现旧版应用程序，并在 Microsoft Edge 模式下呈现其余应用程序。

就可以使用企业模式网站列表的“可配置网站”来解决。 启用此功能后，Microsoft Edge 将允许具有“可配置”标记的网站参与 IE 模式引擎确定。

## <a name="how-configurable-sites-works"></a>可配置网站的工作方式

### <a name="automatic-switching-from-the-microsoft-edge-engine-to-the-ie-mode-engine"></a>从 Microsoft Edge 引擎自动切换到 IE 模式引擎

若要使用“可配置网站”功能，将需要企业模式网站列表中的一个或多个网站具有 `<open-in>Configurable</open-in>` 选项。

示例：

```
<site-list version="1">
  <site url="app.com">
    <open-in>Configurable</open-in>
  </site>
</site-list>
```

启用“可配置网站”功能时，会产生以下行为：

1. 向可配置网站发出请求时，Microsoft Edge 将发送 HTTP 请求头“`X-InternetExplorerModeConfigurable: 1`”。
2. 可配置网站可能会发送 HTTP 响应头为“`X-InternetExplorerMode: 1`”的重定向响应（例如 HTTP 302），请求 Microsoft Edge 加载 IE 模式下的网站。
3. 重定向的目标（即 **Location** 响应头的值）也必须是**可配置的**或**中立的**网站，否则将忽略 IE 模式响应头。 预期的重定向目标通常与原始 URL 相同。 但是，也可以不必如此。

   > [!NOTE]
   > 重定向响应可能会根据 Microsoft Edge 用于重定向的普通 HTTP 缓存行为进行缓存。

### <a name="switching-back-from-ie-mode-engine-to-microsoft-edge-engine"></a>从 IE 模式引擎切换回 Microsoft Edge 引擎

在 Microsoft Edge 中启用可配置网站会自动启用 IE 模式选项卡中的以下行为：

1. 向可配置网站发出请求时，IE 模式选项卡将同 Microsoft Edge 选项卡发送一样的 HTTP 请求头“`X-InternetExplorerModeConfigurable: 1`”。
2. 可配置网站可能会发送 HTTP 响应头为“`X-InternetExplorerMode: 0`”的重定向响应（例如 HTTP 302），请求导航切换回 Microsoft Edge 模式。
3. 重定向的目标（即 **Location** 响应头的值）也必须是**可配置的**或**中立的**网站，否则将忽略 IE 模式响应头。 预期的重定向目标通常与原始 URL 相同。 但是，也可以不必如此。

   > [!NOTE]
   > 重定向响应可能会根据 Microsoft Edge 用于重定向的普通 HTTP 缓存行为进行缓存。

> [!TIP]
> 两种浏览器引擎均向可配置网站发送相同的“`X-InternetExplorerModeConfigurable: 1`”请求头。 应使用 User-Agent 请求头区分 Microsoft Edge 模式与 IE 模式的请求，避免在网站已加载到正确的引擎中时进行重定向。

## <a name="see-also"></a>另请参阅

- [关于 IE 模式](./edge-ie-mode.md)
- [其他企业模式信息](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)