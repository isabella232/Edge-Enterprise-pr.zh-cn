---
title: 企业网站配置策略
ms.author: shisub
author: shisub
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 为 Internet Explorer 模式配置企业模式网站列表的分步指南。
ms.openlocfilehash: 72de393a5da0b4b0e2950951ae527f6ef870e110
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641808"
---
# <a name="enterprise-site-configuration-strategy"></a><span data-ttu-id="53eb4-103">企业网站配置策略</span><span class="sxs-lookup"><span data-stu-id="53eb4-103">Enterprise site configuration strategy</span></span>

>[!Note]
> <span data-ttu-id="53eb4-104">Internet Explorer 11 桌面应用程序将于 2022 年 6 月 15 日停用并停止支持（若要查看包含内容的列表， [请参阅常见问题解答](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)）。</span><span class="sxs-lookup"><span data-stu-id="53eb4-104">The Internet Explorer 11 desktop application will be retired and go out of support on June 15, 2022 (for a list of what’s in scope, [see the FAQ](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)).</span></span> <span data-ttu-id="53eb4-105">现在使用的 IE11 应用和网站可以在 Microsoft Edge 的 Internet Explorer 模式下打开。</span><span class="sxs-lookup"><span data-stu-id="53eb4-105">The same IE11 apps and sites you use today can open in Microsoft Edge with Internet Explorer mode.</span></span> <span data-ttu-id="53eb4-106">[在此处了解详细信息](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。</span><span class="sxs-lookup"><span data-stu-id="53eb4-106">[Learn more here](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).</span></span>

<span data-ttu-id="53eb4-107">本文介绍对“企业模式网站列表”的更改，以支持针对 Microsoft Edge 版本 77 和更高版本的 Internet Explorer 模式。</span><span class="sxs-lookup"><span data-stu-id="53eb4-107">This article describes changes to the Enterprise Mode Site List to support Internet Explorer mode for Microsoft Edge version 77 and later.</span></span>

<span data-ttu-id="53eb4-108">若要详细了解 Enterprise Mode Site List XML 文件的架构，请参阅[企业模式架构 v.2 指南](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)。</span><span class="sxs-lookup"><span data-stu-id="53eb4-108">For more information on the schema for the Enterprise Mode Site List XML file, see [Enterprise Mode schema v.2 guidance](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>

> [!NOTE]
> <span data-ttu-id="53eb4-109">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="53eb4-109">This article applies to Microsoft Edge version 77 or later.</span></span>
<!--
## Updated schema elements

The following table describes the \<open-in app\> element added to the v.2 of the Enterprise Mode schema:

| **Element** | **Description** |
| --- | --- |
| \<open-in app="**true**"\> | A child element that controls what browser is used for sites. This element is required for sites that need to **open in IE11**.|

**Example:**

``` xml
<site url="contoso.com">

  <open-in app="true">IE11</open-in>

</site>
```

The following table shows the possible values of the \<open-in\> element:

| **Value** | **Description** |
| --- | --- |
| **\<open-in\>IE11\</open-in\>** | Opens the site in IE mode or a full IE11 window. To enable IE mode, see [Configure IE mode policies](./edge-ie-mode-policies.md)|
| **\<open-in app="**true**"\>IE11\</open-in\>** | Opens the site in a full IE11 window |
| **\<open-in\>MSEdge\</open-in\>** | Opens the site in Microsoft Edge |
| **\<open-in\>None or not specified\</open-in\>** | Opens the site in the default browser or in the browser where the user navigated to the site. |
|**\<open-in\>Configurable\</open-in\>** | Allows the site to participate in IE mode engine determination. To learn more, see [Learn about Configurable sites in IE mode](edge-learnmore-configurable-sites-ie-mode.md).  |

>[!NOTE]
> The attribute app=**"true"** is only recognized when associated to _'open-in' IE11_. Adding it to the other 'open-in' elements won't change browser behavior.   -->

## <a name="configuration-strategy"></a><span data-ttu-id="53eb4-110">配置策略</span><span class="sxs-lookup"><span data-stu-id="53eb4-110">Configuration strategy</span></span>

<span data-ttu-id="53eb4-111">以下步骤是适用于 IE 模式的网站配置策略的一部分：</span><span class="sxs-lookup"><span data-stu-id="53eb4-111">The following steps are part of a site configuration strategy for IE mode:</span></span>
1. <span data-ttu-id="53eb4-112">准备网站列表</span><span class="sxs-lookup"><span data-stu-id="53eb4-112">Prepare your site list</span></span>
2. <span data-ttu-id="53eb4-113">配置非特定网站</span><span class="sxs-lookup"><span data-stu-id="53eb4-113">Configure neutral sites</span></span>
3. <span data-ttu-id="53eb4-114">（可选）如有必要，请使用 Cookie 共享</span><span class="sxs-lookup"><span data-stu-id="53eb4-114">(Optional) Use cookie sharing if necessary</span></span>

<!--
Step 1.  – if you don’t have one use Site Discovery Step-by-Step
Step 2 – Neutral sites + sticky mode
        Use more examples and explain sticky mode better
Step 3 – If that doesn’t cover your needs, then use Cookie sharing -->

## <a name="prepare-your-site-list"></a><span data-ttu-id="53eb4-115">准备网站列表</span><span class="sxs-lookup"><span data-stu-id="53eb4-115">Prepare your site list</span></span>

<span data-ttu-id="53eb4-116">如果已有 IE11 或 Microsoft Edge 旧版企业模式网站列表，可重复使用该列表来配置 IE 模式。</span><span class="sxs-lookup"><span data-stu-id="53eb4-116">If you already have an Enterprise Mode site list for IE11 or Microsoft Edge Legacy, you can reuse it to configure IE mode.</span></span>

<span data-ttu-id="53eb4-117">但是，如果你没有网站列表，可以使用"企业网站 [工具](/deployedge/edge-ie-mode-site-discovery) 你的网站列表。</span><span class="sxs-lookup"><span data-stu-id="53eb4-117">However, if you don't have a site list, you can use the [Enterprise Site Discovery tool](/deployedge/edge-ie-mode-site-discovery) to populate your site list.</span></span>

## <a name="configure-neutral-sites"></a><span data-ttu-id="53eb4-118">配置非特定网站</span><span class="sxs-lookup"><span data-stu-id="53eb4-118">Configure neutral sites</span></span>

<span data-ttu-id="53eb4-119">为了使 IE 模式正常工作，需要显式将身份验证/单一登录 （SSO） 服务器配置为非特定站点。</span><span class="sxs-lookup"><span data-stu-id="53eb4-119">In order for IE mode to work properly, authentication / Single Sign-On (SSO) servers will need to be explicitly configured as neutral sites.</span></span> <span data-ttu-id="53eb4-120">否则，IE 模式网页会尝试重定向到 Microsoft Edge，且身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="53eb4-120">Otherwise, IE mode pages will try to redirect to Microsoft Edge, and authentication will fail.</span></span>

<span data-ttu-id="53eb4-121">中性网站使用导航起始浏览器，要么是 Microsoft Edge，要么是 IE 模式。</span><span class="sxs-lookup"><span data-stu-id="53eb4-121">A neutral site will use the browser where the navigation started - either Microsoft Edge or IE mode.</span></span> <span data-ttu-id="53eb4-122">配置中性网站可确保所有使用这些身份验证服务器的应用程序（无论是新式应用程序还是旧应用程序）都能继续正常运行。</span><span class="sxs-lookup"><span data-stu-id="53eb4-122">Configuring neutral sites ensures that all applications using these authentication servers, both modern and legacy, continue to work.</span></span>

<span data-ttu-id="53eb4-123">可以通过在 Enterprise Mode Site List Manager 工具中将*打开方式*下拉列表设置为“无”或直接更新站点列表 XML 来配置中性站点：</span><span class="sxs-lookup"><span data-stu-id="53eb4-123">You can configure neutral sites by setting the *Open In* dropdown to 'None' in the Enterprise Mode Site List Manager tool or by directly updating the site list XML:</span></span>

``` xml
<site url="login.contoso.com">
   
    <open-in>None</open-in>

</site>
```

<span data-ttu-id="53eb4-124">若要识别身份验证服务器，请使用 IE11 开发人员工具检查来自应用程序的网络流量。</span><span class="sxs-lookup"><span data-stu-id="53eb4-124">To identify authentication servers, inspect the network traffic from an application using the IE11 Developer Tools.</span></span> <span data-ttu-id="53eb4-125">如果需要更多时间来识别身份验证服务器，可以配置策略以在 IE 模式下保留所有页面内导航，以允许用户继续其工作流中断。</span><span class="sxs-lookup"><span data-stu-id="53eb4-125">If you need more time to identify your authentication servers, you can configure a policy to keep all in-page navigations in IE mode to allow your users to continue their workflows uninterrupted.</span></span> <span data-ttu-id="53eb4-126">若要尽可能减少不必要的 IE 模式使用，在识别并将身份验证服务器添加到网站列表后，请禁用此设置。</span><span class="sxs-lookup"><span data-stu-id="53eb4-126">To minimize the use of IE mode when unnecessary, disable this setting once you've identified and added your authentication servers to the site list.</span></span> <span data-ttu-id="53eb4-127">有关详细信息，请参阅 [在 IE 模式下保留页面内](/deployedge/edge-learnmore-inpage-nav)。</span><span class="sxs-lookup"><span data-stu-id="53eb4-127">For more information, see [Keep in-page navigation in IE mode](/deployedge/edge-learnmore-inpage-nav).</span></span>

>[!NOTE]
   ><span data-ttu-id="53eb4-128">IE 模式集成不支持企业模式架构 v.1。</span><span class="sxs-lookup"><span data-stu-id="53eb4-128">Enterprise Mode schema v.1 isn't supported for IE mode integration.</span></span> <span data-ttu-id="53eb4-129">如果当前正在将架构 v.1 与 Internet Explorer 11 一起使用，则必须升级到架构 v.2。</span><span class="sxs-lookup"><span data-stu-id="53eb4-129">If you are currently using schema v.1 with Internet Explorer 11, you must upgrade to schema v.2.</span></span> <span data-ttu-id="53eb4-130">有关详细信息，请参阅[企业模式架构 v.2 指南](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)。</span><span class="sxs-lookup"><span data-stu-id="53eb4-130">For more information, see [Enterprise Mode schema v.2 guidance](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>

## <a name="optional-use-cookie-sharing-if-necessary"></a><span data-ttu-id="53eb4-131">（可选）如有必要，请使用 Cookie 共享</span><span class="sxs-lookup"><span data-stu-id="53eb4-131">(Optional) Use cookie sharing if necessary</span></span>

<span data-ttu-id="53eb4-132">默认情况下，Microsoft Edge 和 Internet Explorer 进程不共享会话 Cookie，因此在某些情况下，使用 IE 模式时可能不太方便进行共享。</span><span class="sxs-lookup"><span data-stu-id="53eb4-132">By default, the Microsoft Edge and Internet Explorer processes don't share session cookies, and this lack of sharing can be inconvenient in some cases while using IE mode.</span></span> <span data-ttu-id="53eb4-133">例如，当用户习惯在以前习惯在 IE 模式下重新身份验证，或者当注销 Microsoft Edge 会话时，不会退出关键事务的 Internet Explorer 模式会话。</span><span class="sxs-lookup"><span data-stu-id="53eb4-133">For example, when a user has to reauthenticate in IE mode when previously they are accustomed to doing so or when signing out of a Microsoft Edge session doesn’t sign out of the Internet Explorer mode session for critical transactions.</span></span> <span data-ttu-id="53eb4-134">在这些方案中，可以配置 SSO 设置的特定 Cookie，以便从 Microsoft Edge 发送到 Internet Explorer，以便身份验证体验更加无缝，无需重新身份验证。</span><span class="sxs-lookup"><span data-stu-id="53eb4-134">In these scenarios, you can configure specific cookies set by SSO to be sent from Microsoft Edge to Internet Explorer so the authentication experience becomes more seamless by eliminating the need to reauthenticate.</span></span> <span data-ttu-id="53eb4-135">有关详细信息，请参阅 从 Microsoft Edge [Internet Explorer 的 Cookie 共享](/deployedge/edge-ie-mode-add-guidance-cookieshare)。</span><span class="sxs-lookup"><span data-stu-id="53eb4-135">For more information, see [Cookie sharing from Microsoft Edge to Internet Explorer](/deployedge/edge-ie-mode-add-guidance-cookieshare).</span></span>

## <a name="see-also"></a><span data-ttu-id="53eb4-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53eb4-136">See also</span></span>

- [<span data-ttu-id="53eb4-137">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="53eb4-137">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="53eb4-138">关于 IE 模式</span><span class="sxs-lookup"><span data-stu-id="53eb4-138">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="53eb4-139">其他企业模式信息</span><span class="sxs-lookup"><span data-stu-id="53eb4-139">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
