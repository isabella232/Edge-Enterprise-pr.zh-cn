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
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641798"
---
# <a name="learn-about-configurable-sites-in-ie-mode"></a><span data-ttu-id="2ab22-103">了解 IE 模式下可配置网站</span><span class="sxs-lookup"><span data-stu-id="2ab22-103">Learn about Configurable sites in IE mode</span></span>

<span data-ttu-id="2ab22-104">本文将介绍 Microsoft Edge 中使用 IE 模式时企业模式网站列表的“可配置网站”功能。</span><span class="sxs-lookup"><span data-stu-id="2ab22-104">This article explains the Configurable sites feature of the Enterprise Mode Site List when using IE mode in Microsoft Edge.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2ab22-105">必备条件</span><span class="sxs-lookup"><span data-stu-id="2ab22-105">Prerequisites</span></span>

- <span data-ttu-id="2ab22-106">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="2ab22-106">Windows updates</span></span>

  - <span data-ttu-id="2ab22-107">Windows 10 版本 1909，Windows Server 版本 1909 – KB4550945 或更高版本</span><span class="sxs-lookup"><span data-stu-id="2ab22-107">Windows 10 version 1909, Windows server version 1909 – KB4550945  or higher</span></span>
  - <span data-ttu-id="2ab22-108">Windows 10 版本1903，Windows Server 版本 1903 – KB4550945 或更高版本</span><span class="sxs-lookup"><span data-stu-id="2ab22-108">Windows 10 version 1903, Windows server version 1903 – KB4550945  or higher</span></span>
  - <span data-ttu-id="2ab22-109">Windows 10 版本 1809、Windows Server 版本 1809 和 Windows Server 2019 - KB4550969 或更高版本</span><span class="sxs-lookup"><span data-stu-id="2ab22-109">Windows 10 version 1809, Windows Server version 1809, and Windows Server 2019 - KB4550969 or higher</span></span>
  - <span data-ttu-id="2ab22-110">Windows 10 版本 1803 – KB4550944 或更高版本</span><span class="sxs-lookup"><span data-stu-id="2ab22-110">Windows 10 version 1803 – KB4550944 or higher</span></span>
  - <span data-ttu-id="2ab22-111">Windows 10 版本1607、Windows Server 2016-KB4556826 或更高版本</span><span class="sxs-lookup"><span data-stu-id="2ab22-111">Windows 10 version 1607, Windows Server 2016 - KB4556826 or higher</span></span>
  - <span data-ttu-id="2ab22-112">Windows 10 初始版本，2015 年 7 月 - KB4550947 或更高版本</span><span class="sxs-lookup"><span data-stu-id="2ab22-112">Windows 10 initial version, July 2015 - KB4550947 or higher</span></span>
  - <span data-ttu-id="2ab22-113">Windows 8.1 – KB4556798 或更高版本</span><span class="sxs-lookup"><span data-stu-id="2ab22-113">Windows 8.1 – KB4556798 or higher</span></span>

- <span data-ttu-id="2ab22-114">Microsoft Edge 版本 83 或更高版本</span><span class="sxs-lookup"><span data-stu-id="2ab22-114">Microsoft Edge version 83 or later</span></span>
- <span data-ttu-id="2ab22-115">使用企业模式网站列表配置的 [IE 模式](./edge-ie-mode.md)</span><span class="sxs-lookup"><span data-stu-id="2ab22-115">[IE mode](./edge-ie-mode.md) configured with Enterprise Mode Site List</span></span>

## <a name="overview"></a><span data-ttu-id="2ab22-116">概述</span><span class="sxs-lookup"><span data-stu-id="2ab22-116">Overview</span></span>

<span data-ttu-id="2ab22-117">在企业模式网站列表中配置需要 IE 模式的网站，可良好适用于具有旧版应用程序的大多数环境。</span><span class="sxs-lookup"><span data-stu-id="2ab22-117">Configuring sites needing IE mode in the Enterprise Mode Site List will work well for most environments with legacy applications.</span></span> <span data-ttu-id="2ab22-118">但是，在某些情况下，此方法不是将网站的子集配置为以 IE 模式打开，而无需在 IE 模式下呈现整个域。</span><span class="sxs-lookup"><span data-stu-id="2ab22-118">However, in some cases this approach isn't the best to configure a subset of sites to open in IE mode without rendering an entire domain in IE mode.</span></span> <span data-ttu-id="2ab22-119">例如，如果你的环境中同时包含运行于单个服务器上的新版和旧版应用程序，你想要灵活地在 IE 模式下呈现旧版应用程序，并在 Microsoft Edge 模式下呈现其余应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ab22-119">For example, when your environment contains both modern and legacy applications running on a single server and you would like the flexibility to render only the legacy applications in IE mode and the remaining applications to render in Microsoft Edge mode.</span></span>

<span data-ttu-id="2ab22-120">就可以使用企业模式网站列表的“可配置网站”来解决。</span><span class="sxs-lookup"><span data-stu-id="2ab22-120">The solution is to use the Configurable sites feature of the Enterprise Mode Site List.</span></span> <span data-ttu-id="2ab22-121">启用此功能后，Microsoft Edge 将允许具有“可配置”标记的网站参与 IE 模式引擎确定。</span><span class="sxs-lookup"><span data-stu-id="2ab22-121">When the feature is enabled, Microsoft Edge will allow sites with the "configurable" tag to participate in IE mode engine determination.</span></span>

## <a name="how-configurable-sites-works"></a><span data-ttu-id="2ab22-122">可配置网站的工作方式</span><span class="sxs-lookup"><span data-stu-id="2ab22-122">How Configurable sites works</span></span>

### <a name="automatic-switching-from-the-microsoft-edge-engine-to-the-ie-mode-engine"></a><span data-ttu-id="2ab22-123">从 Microsoft Edge 引擎自动切换到 IE 模式引擎</span><span class="sxs-lookup"><span data-stu-id="2ab22-123">Automatic switching from the Microsoft Edge engine to the IE mode engine</span></span>

<span data-ttu-id="2ab22-124">若要使用“可配置网站”功能，将需要企业模式网站列表中的一个或多个网站具有 `<open-in>Configurable</open-in>` 选项。</span><span class="sxs-lookup"><span data-stu-id="2ab22-124">To use the Configurable sites feature, you'll need one or more sites in the Enterprise Mode Site List to have the `<open-in>Configurable</open-in>` option.</span></span>

<span data-ttu-id="2ab22-125">示例：</span><span class="sxs-lookup"><span data-stu-id="2ab22-125">Example:</span></span>

```
<site-list version="1">
  <site url="app.com">
    <open-in>Configurable</open-in>
  </site>
</site-list>
```

<span data-ttu-id="2ab22-126">启用“可配置网站”功能时，会产生以下行为：</span><span class="sxs-lookup"><span data-stu-id="2ab22-126">When the Configurable sites feature is enabled, the following behavior occurs:</span></span>

1. <span data-ttu-id="2ab22-127">向可配置网站发出请求时，Microsoft Edge 将发送 HTTP 请求头“`X-InternetExplorerModeConfigurable: 1`”。</span><span class="sxs-lookup"><span data-stu-id="2ab22-127">When making a request to a Configurable site, Microsoft Edge will send the HTTP request header "`X-InternetExplorerModeConfigurable: 1`".</span></span>
2. <span data-ttu-id="2ab22-128">可配置网站可能会发送 HTTP 响应头为“`X-InternetExplorerMode: 1`”的重定向响应（例如 HTTP 302），请求 Microsoft Edge 加载 IE 模式下的网站。</span><span class="sxs-lookup"><span data-stu-id="2ab22-128">A Configurable site may send a redirect response (for example, HTTP 302) with the HTTP response header "`X-InternetExplorerMode: 1`" to request that Microsoft Edge loads the site in IE mode.</span></span>
3. <span data-ttu-id="2ab22-129">重定向的目标（即 **Location** 响应头的值）也必须是**可配置的**或**中立的**网站，否则将忽略 IE 模式响应头。</span><span class="sxs-lookup"><span data-stu-id="2ab22-129">The target of the redirect (that is, the value of the **Location** response header) must also be a **Configurable** or **Neutral** site, otherwise the IE mode response header will be ignored.</span></span> <span data-ttu-id="2ab22-130">预期的重定向目标通常与原始 URL 相同。</span><span class="sxs-lookup"><span data-stu-id="2ab22-130">It's expected that the target of the redirect will usually be the same as the original URL.</span></span> <span data-ttu-id="2ab22-131">但是，也可以不必如此。</span><span class="sxs-lookup"><span data-stu-id="2ab22-131">However, it doesn't have to be.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2ab22-132">重定向响应可能会根据 Microsoft Edge 用于重定向的普通 HTTP 缓存行为进行缓存。</span><span class="sxs-lookup"><span data-stu-id="2ab22-132">The redirect response is subject to caching according to Microsoft Edge's normal HTTP caching behavior for redirects.</span></span>

### <a name="switching-back-from-ie-mode-engine-to-microsoft-edge-engine"></a><span data-ttu-id="2ab22-133">从 IE 模式引擎切换回 Microsoft Edge 引擎</span><span class="sxs-lookup"><span data-stu-id="2ab22-133">Switching back from IE mode engine to Microsoft Edge engine</span></span>

<span data-ttu-id="2ab22-134">在 Microsoft Edge 中启用可配置网站会自动启用 IE 模式选项卡中的以下行为：</span><span class="sxs-lookup"><span data-stu-id="2ab22-134">Enabling Configurable sites in Microsoft Edge automatically enables the following behaviors in IE mode tabs:</span></span>

1. <span data-ttu-id="2ab22-135">向可配置网站发出请求时，IE 模式选项卡将同 Microsoft Edge 选项卡发送一样的 HTTP 请求头“`X-InternetExplorerModeConfigurable: 1`”。</span><span class="sxs-lookup"><span data-stu-id="2ab22-135">When making a request to a Configurable site, IE mode tabs will send the HTTP request header "`X-InternetExplorerModeConfigurable: 1`", the same as Microsoft Edge tabs.</span></span>
2. <span data-ttu-id="2ab22-136">可配置网站可能会发送 HTTP 响应头为“`X-InternetExplorerMode: 0`”的重定向响应（例如 HTTP 302），请求导航切换回 Microsoft Edge 模式。</span><span class="sxs-lookup"><span data-stu-id="2ab22-136">A Configurable site might send a redirect response (for example, HTTP 302) with the HTTP response header "`X-InternetExplorerMode: 0`" to request that the navigation switch back to Microsoft Edge mode.</span></span>
3. <span data-ttu-id="2ab22-137">重定向的目标（即 **Location** 响应头的值）也必须是**可配置的**或**中立的**网站，否则将忽略 IE 模式响应头。</span><span class="sxs-lookup"><span data-stu-id="2ab22-137">The target of the redirect (that is, the value of the **Location** response header) must also be a **Configurable** or **Neutral** site, otherwise the IE mode response header will be ignored.</span></span> <span data-ttu-id="2ab22-138">预期的重定向目标通常与原始 URL 相同。</span><span class="sxs-lookup"><span data-stu-id="2ab22-138">It's expected that the target of the redirect will usually be the same as the original URL.</span></span> <span data-ttu-id="2ab22-139">但是，也可以不必如此。</span><span class="sxs-lookup"><span data-stu-id="2ab22-139">However, it doesn't have to be.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2ab22-140">重定向响应可能会根据 Microsoft Edge 用于重定向的普通 HTTP 缓存行为进行缓存。</span><span class="sxs-lookup"><span data-stu-id="2ab22-140">The redirect response is subject to caching according to Microsoft Edge's normal HTTP caching behavior for redirects.</span></span>

> [!TIP]
> <span data-ttu-id="2ab22-141">两种浏览器引擎均向可配置网站发送相同的“`X-InternetExplorerModeConfigurable: 1`”请求头。</span><span class="sxs-lookup"><span data-stu-id="2ab22-141">Both browser engines send the same "`X-InternetExplorerModeConfigurable: 1`" request header to Configurable sites.</span></span> <span data-ttu-id="2ab22-142">应使用 User-Agent 请求头区分 Microsoft Edge 模式与 IE 模式的请求，避免在网站已加载到正确的引擎中时进行重定向。</span><span class="sxs-lookup"><span data-stu-id="2ab22-142">You should use the User-Agent request header to distinguish between requests from Microsoft Edge mode vs. IE mode to avoid redirecting when the site is already loading in the correct engine.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ab22-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ab22-143">See also</span></span>

- [<span data-ttu-id="2ab22-144">关于 IE 模式</span><span class="sxs-lookup"><span data-stu-id="2ab22-144">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="2ab22-145">其他企业模式信息</span><span class="sxs-lookup"><span data-stu-id="2ab22-145">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [<span data-ttu-id="2ab22-146">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="2ab22-146">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)