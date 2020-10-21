---
title: 从 Internet Explorer 重定向到 Microsoft Edge，以便与现代网站兼容
ms.author: laannade
author: dan-wesley
manager: ratetali
ms.date: 10/19/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 从 Internet Explorer 重定向到 Microsoft Edge，以便与现代网站兼容
ms.openlocfilehash: ce9e8dabdff25cc3ba375746ec82ddd78b6d7694
ms.sourcegitcommit: cf991cc4bd2e70169902cbda9ddc870d70e31ca2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2020
ms.locfileid: "11120517"
---
# <span data-ttu-id="5d158-103">从 Internet Explorer 重定向到 Microsoft Edge，以便与现代网站兼容</span><span class="sxs-lookup"><span data-stu-id="5d158-103">Redirection from Internet Explorer to Microsoft Edge for compatibility with modern web sites</span></span>

> [!NOTE]
> <span data-ttu-id="5d158-104">本文适用于 Microsoft Edge 稳定版本 87 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="5d158-104">This article applies to Microsoft Edge Stable version 87 or later.</span></span>

## <span data-ttu-id="5d158-105">概述</span><span class="sxs-lookup"><span data-stu-id="5d158-105">Overview</span></span>

<span data-ttu-id="5d158-106">许多现代网站的设计与 Internet Explorer 不兼容。</span><span class="sxs-lookup"><span data-stu-id="5d158-106">Many modern websites have designs that are incompatible with Internet Explorer.</span></span> <span data-ttu-id="5d158-107">只要 Internet Explorer 用户访问不兼容的公共网站，就会收到一条消息，告知他们该网站与其浏览器不兼容，需要手动切换到其他浏览器。</span><span class="sxs-lookup"><span data-stu-id="5d158-107">Whenever an Internet Explorer user visits an incompatible public site, they get a message that tells them the site is incompatible with their browser, and they need to manually switch to a different browser.</span></span>

<span data-ttu-id="5d158-108">需要手动切换到另一种浏览器的操作，从 Microsoft Edge 稳定版本 87 开始更改。</span><span class="sxs-lookup"><span data-stu-id="5d158-108">The need to  manually switch to a different browser changes starting with Microsoft Edge Stable version 87.</span></span>

<span data-ttu-id="5d158-109">当用户转到与 Internet Explorer 不兼容的网站时，它们将被自动重定向到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="5d158-109">When a user goes to a site that is incompatible with Internet Explorer, they will be automatically redirected to Microsoft Edge.</span></span> <span data-ttu-id="5d158-110">本文介绍重定向的用户体验，以及用于配置或禁用自动重定向的组策略。</span><span class="sxs-lookup"><span data-stu-id="5d158-110">This article describes the user experience for redirection and the group policies that are used to configure or disable automatic redirection.</span></span>

> [!NOTE]
> <span data-ttu-id="5d158-111">Microsoft 将保留已知与 Internet Explorer 不兼容的所有网站的列表。</span><span class="sxs-lookup"><span data-stu-id="5d158-111">Microsoft maintains a list of all sites that are known to be incompatible with Internet Explorer.</span></span>

## <span data-ttu-id="5d158-112">重定向体验</span><span class="sxs-lookup"><span data-stu-id="5d158-112">Redirection experience</span></span>

<span data-ttu-id="5d158-113">重定向到 Microsoft Edge 后，将在下一屏幕截图中显示一次性对话框。</span><span class="sxs-lookup"><span data-stu-id="5d158-113">On redirection to Microsoft Edge, users are shown the one-time dialog in the next screenshot.</span></span> <span data-ttu-id="5d158-114">此对话框将说明它们被重定向的原因，并提示你同意将浏览数据和首选项从 Internet Explorer 复制到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="5d158-114">This dialog explains why they're getting redirected and prompts for consent to copy their browsing data and preferences from Internet Explorer to Microsoft Edge.</span></span> <span data-ttu-id="5d158-115">将导入以下浏览数据： 收藏夹、密码、搜索引擎、打开选项卡、历史记录、设置、cookie 和主页。</span><span class="sxs-lookup"><span data-stu-id="5d158-115">The following browsing data will be imported: Favorites, Passwords, Search engines, open tabs, History, settings, cookies, and the Home Page.</span></span>

![浏览通知并提示导入数据和首选项。](media/edge-learnmore-neededge/neededge-dialog1.png)

<span data-ttu-id="5d158-117">即使他们没有通过选中“总是导入 Internet Explorer 中的浏览数据和首选项”提供许可，他们也可以单击 **“继续浏览”** 来继续执行会话。</span><span class="sxs-lookup"><span data-stu-id="5d158-117">Even if they don't give their consent by checking "Always bring over my browsing data and preferences from Internet Explorer", they can click **Continue browsing** to continue their session.</span></span>

<span data-ttu-id="5d158-118">最后，下一个屏幕截图中显示的网站不兼容标题会显示在每次重定向地址栏的下方。</span><span class="sxs-lookup"><span data-stu-id="5d158-118">Finally, a website incompatibility banner, shown in the next screenshot, appears below the address bar for every redirection.</span></span>

![有关新式网站的通知，以及将 Microsoft Edge 设置为默认浏览器或浏览 Microsoft Edge 的提示。](media/edge-learnmore-neededge/neededge-banner.png)

<span data-ttu-id="5d158-120">网站兼容性标题：</span><span class="sxs-lookup"><span data-stu-id="5d158-120">The website incompatibility banner:</span></span>

- <span data-ttu-id="5d158-121">鼓励用户切换到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5d158-121">encourages the user to switch to Microsoft Edge</span></span>
- <span data-ttu-id="5d158-122">将 Microsoft Edge 作为默认浏览器</span><span class="sxs-lookup"><span data-stu-id="5d158-122">offers to make Microsoft Edge as the default browser</span></span>
- <span data-ttu-id="5d158-123">为用户提供浏览 Microsoft Edge 的选项</span><span class="sxs-lookup"><span data-stu-id="5d158-123">gives the user the option to explore Microsoft Edge</span></span>

<span data-ttu-id="5d158-124">从 Internet Explorer 将网站重定向到 Microsoft Edge 时，如果没有以前的内容，则会关闭启动加载网站的 Internet Explorer 选项卡。</span><span class="sxs-lookup"><span data-stu-id="5d158-124">When a site is redirected from Internet Explorer to Microsoft Edge, the Internet Explorer tab that started loading the site is closed if it had no prior content.</span></span> <span data-ttu-id="5d158-125">否则，活动选项卡视图将转到 Microsoft [支持](https://support.microsoft.com/office/the-website-you-were-trying-to-reach-doesn-t-work-with-internet-explorer-8f5fc675-cd47-414c-9535-12821ddfc554?ui=en-US&rs=en-US&ad=US) 页面，说明网站重定向到 Microsoft Edge 的原因。</span><span class="sxs-lookup"><span data-stu-id="5d158-125">Otherwise, the active tab view goes to a  Microsoft [support](https://support.microsoft.com/office/the-website-you-were-trying-to-reach-doesn-t-work-with-internet-explorer-8f5fc675-cd47-414c-9535-12821ddfc554?ui=en-US&rs=en-US&ad=US) page that explains why the site was redirected to Microsoft Edge.</span></span>

> [!NOTE]
> <span data-ttu-id="5d158-126">重定向之后，用户可以使用 Internet Explorer 获取不在 Internet Explorer 兼容性列表中的网站。</span><span class="sxs-lookup"><span data-stu-id="5d158-126">After a redirection users can go back to using Internet Explorer for sites that are not on the Internet Explorer incompatibility list.</span></span>  

## <span data-ttu-id="5d158-127">用于配置重定向到 Microsoft Edge 的策略</span><span class="sxs-lookup"><span data-stu-id="5d158-127">Policies to configure redirection to Microsoft Edge</span></span>

> [!NOTE]
> <span data-ttu-id="5d158-128">这些策略将在 2020 年 10 月 26 日发布的 ADMX 文件更新中提供，并且将于 2020 年 11 月 9 日在 Intune 中提供。</span><span class="sxs-lookup"><span data-stu-id="5d158-128">These policies will be available as ADMX file updates by October 26, 2020 and will be available in Intune by November 9, 2020.</span></span>

<span data-ttu-id="5d158-129">必须将三个组策略配置为启用自动重定向到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="5d158-129">Three group policies must be configured to enable automatic redirection to Microsoft Edge.</span></span> <span data-ttu-id="5d158-130">这些策略是：</span><span class="sxs-lookup"><span data-stu-id="5d158-130">These policies are:</span></span>

- <span data-ttu-id="5d158-131">RedirectSitesFromInternetExplorerPreventBHOInstall</span><span class="sxs-lookup"><span data-stu-id="5d158-131">RedirectSitesFromInternetExplorerPreventBHOInstall</span></span>
- <span data-ttu-id="5d158-132">RedirectSitesFromInternetExplorerRedirectMode</span><span class="sxs-lookup"><span data-stu-id="5d158-132">RedirectSitesFromInternetExplorerRedirectMode</span></span>
- <span data-ttu-id="5d158-133">HideInternetExplorerRedirectUXForIncompatibleSitesEnabled</span><span class="sxs-lookup"><span data-stu-id="5d158-133">HideInternetExplorerRedirectUXForIncompatibleSitesEnabled</span></span>

### <span data-ttu-id="5d158-134">策略：RedirectSitesFromInternetExplorerPreventBHOInstall</span><span class="sxs-lookup"><span data-stu-id="5d158-134">Policy: RedirectSitesFromInternetExplorerPreventBHOInstall</span></span>

<span data-ttu-id="5d158-135">从 Internet Explorer 重定向到 Microsoft Edge 需要一个名为 IEtoEdge BHO 的 Internet Explorer 浏览器帮助程序对象 (BHO)。</span><span class="sxs-lookup"><span data-stu-id="5d158-135">Redirection from Internet Explorer to Microsoft Edge requires an Internet Explorer Browser Helper Object (BHO) named "IEtoEdge BHO".</span></span> <span data-ttu-id="5d158-136">**RedirectSitesFromInternetExplorerPreventBHOInstall** 策略控制是否已安装此 BHO。</span><span class="sxs-lookup"><span data-stu-id="5d158-136">The **RedirectSitesFromInternetExplorerPreventBHOInstall** policy controls whether or not this BHO is installed.</span></span>  

- <span data-ttu-id="5d158-137">如果启用此策略，重定向所需的 BHO 将不会安装，并且你的用户将继续看到 Internet Explorer 上某些网站的不兼容消息。</span><span class="sxs-lookup"><span data-stu-id="5d158-137">If you enable this policy, the BHO required for redirection will not be installed and your users will continue to see incompatibility messages for certain websites on Internet Explorer.</span></span> <span data-ttu-id="5d158-138">如果已安装 BHO，则在下一次更新 Microsoft Edge 稳定频道时，会将其卸载。</span><span class="sxs-lookup"><span data-stu-id="5d158-138">If the BHO is already installed, it will be uninstalled the next time the Microsoft Edge Stable channel is updated.</span></span>
- <span data-ttu-id="5d158-139">如果禁用或未配置此策略，将安装 BHO。</span><span class="sxs-lookup"><span data-stu-id="5d158-139">If you disable or don't configure this policy, the BHO will be installed.</span></span> <span data-ttu-id="5d158-140">这是默认行为。</span><span class="sxs-lookup"><span data-stu-id="5d158-140">This is the default behavior.</span></span>

<span data-ttu-id="5d158-141">除了需要 BHO， 还有一个 **RedirectSitesFromInternetExplorerRedirectMode** 依赖，需要设置为“站点列表”或“未配置”。</span><span class="sxs-lookup"><span data-stu-id="5d158-141">In addition to needing the BHO, there is a dependency on the **RedirectSitesFromInternetExplorerRedirectMode**, which needs to be set to "Sitelist" or "Not Configured".</span></span>

### <span data-ttu-id="5d158-142">策略：RedirectSitesFromInternetExplorerRedirectMode</span><span class="sxs-lookup"><span data-stu-id="5d158-142">Policy: RedirectSitesFromInternetExplorerRedirectMode</span></span>

 <span data-ttu-id="5d158-143">此策略对应于 Microsoft Edge **默认浏览器**设置“允许 Internet Explorer 在 Microsoft Edge 中打开网站”。</span><span class="sxs-lookup"><span data-stu-id="5d158-143">This policy corresponds to the Microsoft Edge **Default browser** setting "Let Internet Explorer open sites in Microsoft Edge".</span></span> <span data-ttu-id="5d158-144">可通过 *edge://settings/defaultbrowser* URL 来访问此设置。</span><span class="sxs-lookup"><span data-stu-id="5d158-144">You can access this setting by going to the *edge://settings/defaultbrowser* URL.</span></span>  

- <span data-ttu-id="5d158-145">如果未配置此策略或将其设置为“站点列表”，则 Internet Explorer 会将不兼容的网站重定向到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="5d158-145">If you don't configure this policy or set it to "Sitelist", Internet Explorer will redirect incompatible sites to Microsoft Edge.</span></span> <span data-ttu-id="5d158-146">这是默认行为。</span><span class="sxs-lookup"><span data-stu-id="5d158-146">This is the default behavior.</span></span>
- <span data-ttu-id="5d158-147">如果禁用此策略，不兼容的网站不会重定向到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="5d158-147">If you disable this policy, incompatible sites aren't redirected to Microsoft Edge.</span></span>

> [!NOTE]
> <span data-ttu-id="5d158-148">如果你所在的个人设备并非由组织管理，你将在 **Internet Explorer 兼容性**下看到名为“允许在 Internet Explorer 模式中加载的网站”的另一个设置。</span><span class="sxs-lookup"><span data-stu-id="5d158-148">If you're on a personal device that isn't  managed by your organization, you'll see another setting named "Allow sites to be loaded in Internet Explorer mode" under **Internet Explorer compatibility**.</span></span>
>
><span data-ttu-id="5d158-149">如果你使用加入域或移动设备管理 (MDM) 注册设备，则不会看到此选项。</span><span class="sxs-lookup"><span data-stu-id="5d158-149">If you're on a domain joined or Mobile Device Management (MDM) enrolled device, you won't see this option.</span></span>
>
> <span data-ttu-id="5d158-150">如果想让用户在 Internet Explorer 模式下加载网站，可通过将策略配置[允许 Internet Explorer 模式测试](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allow-internet-explorer-mode-testing)来实现此操作。</span><span class="sxs-lookup"><span data-stu-id="5d158-150">Instead, if you want to let your users load sites in Internet Explorer mode, you can do so by configuring the policy [Allow Internet Explorer mode testing](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allow-internet-explorer-mode-testing).</span></span>

### <span data-ttu-id="5d158-151">策略：HideInternetExplorerRedirectUXForIncompatibleSitesEnabled</span><span class="sxs-lookup"><span data-stu-id="5d158-151">Policy: HideInternetExplorerRedirectUXForIncompatibleSitesEnabled</span></span>

<span data-ttu-id="5d158-152">此策略可将不兼容网站重定向的用户体验配置到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="5d158-152">This policy configures the user experience for incompatible site redirection to Microsoft Edge.</span></span>  

- <span data-ttu-id="5d158-153">如果启用此策略，用户则不会看到一次性重定向对话框和重定向标题。</span><span class="sxs-lookup"><span data-stu-id="5d158-153">If you enable this policy, users never see the one-time redirection dialog and the redirection banner.</span></span> <span data-ttu-id="5d158-154">不导入浏览器数据或用户偏好设置。</span><span class="sxs-lookup"><span data-stu-id="5d158-154">No browser data or user preferences are imported.</span></span>
- <span data-ttu-id="5d158-155">如果禁用或未配置此策略，重定向对话框将显示在第一次重定向中，且对于以重定向开头的会话将显示永久重定向标题。</span><span class="sxs-lookup"><span data-stu-id="5d158-155">If you disable or don't configure this policy, the redirection dialog will be shown on the first redirection and the persistent redirection banner will be shown for sessions that start with a redirection.</span></span>

  > [!NOTE]
  > <span data-ttu-id="5d158-156">每次用户遇到新的重定向时，将导入用户浏览数据。</span><span class="sxs-lookup"><span data-stu-id="5d158-156">User browsing data will be imported every time a user encounters a new redirection.</span></span> <span data-ttu-id="5d158-157">但是，只有用户同意一次性重定向对话框上的导入时才会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="5d158-157">However, this only happens if the user consented to the import on the one-time redirection dialog.</span></span>

## <span data-ttu-id="5d158-158">禁用重定向到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5d158-158">Disable redirection to Microsoft Edge</span></span>

<span data-ttu-id="5d158-159">如果想要在更新到 Microsoft Edge 稳定版本 87 之前禁用重定向，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5d158-159">If you want to disable redirection BEFORE updating to Microsoft Edge Stable version 87, use the following step:</span></span>

1. <span data-ttu-id="5d158-160">将 **RedirectSitesFromInternetExplorerRedirectMode** 策略设为 **“启用”**。</span><span class="sxs-lookup"><span data-stu-id="5d158-160">Set the **RedirectSitesFromInternetExplorerRedirectMode** policy to **Enabled**.</span></span> <span data-ttu-id="5d158-161">策略生效后，此设置将立即停止重定向。</span><span class="sxs-lookup"><span data-stu-id="5d158-161">This setting will stop redirecting as soon as the policy takes effect.</span></span>

<span data-ttu-id="5d158-162">如果想要在更新到 Microsoft Edge 稳定版本 87 之后禁用重定向，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5d158-162">If you want to disable redirection AFTER updating to Microsoft Edge Stable version 87, use the following steps:</span></span>

1. <span data-ttu-id="5d158-163">将 **RedirectSitesFromInternetExplorerRedirectMode** 策略设为 **“禁用”**。</span><span class="sxs-lookup"><span data-stu-id="5d158-163">Set the **RedirectSitesFromInternetExplorerRedirectMode** policy to **Disabled**.</span></span> <span data-ttu-id="5d158-164">策略生效后，此设置将立即停止重定向。</span><span class="sxs-lookup"><span data-stu-id="5d158-164">This setting will stop redirecting as soon as the policy takes effect.</span></span>
2. <span data-ttu-id="5d158-165">将 **RedirectSitesFromInternetExplorerPreventBHOInstall** 策略设为 **“启用”**。</span><span class="sxs-lookup"><span data-stu-id="5d158-165">Set the **RedirectSitesFromInternetExplorerPreventBHOInstall** policy to **Enabled**.</span></span> <span data-ttu-id="5d158-166">策略生效后，将在下一次 Microsoft Edge 更新后卸载 BHO。</span><span class="sxs-lookup"><span data-stu-id="5d158-166">This will uninstall the BHO after the next Microsoft Edge update.</span></span>

## <span data-ttu-id="5d158-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d158-167">See also</span></span>

- [<span data-ttu-id="5d158-168">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="5d158-168">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="5d158-169">Microsoft Edge 策略</span><span class="sxs-lookup"><span data-stu-id="5d158-169">Microsoft Edge Policies</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies)