---
title: 计划 Microsoft Edge 部署
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 03/29/2021
audience: ITPro
ms.topic: procedural
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 计划 Microsoft Edge 部署
ms.openlocfilehash: 983fd74bf2150aaffe032fa9defcb0ea5000d316
ms.sourcegitcommit: 93851b83dc11422924646a04a9e0f60ff2554af7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470190"
---
# <a name="plan-your-deployment-of-microsoft-edge"></a><span data-ttu-id="eebb9-103">计划 Microsoft Edge 部署</span><span class="sxs-lookup"><span data-stu-id="eebb9-103">Plan your deployment of Microsoft Edge</span></span>

<span data-ttu-id="eebb9-104">本文介绍在企业环境中部署 Microsoft Edge 的建议做法。</span><span class="sxs-lookup"><span data-stu-id="eebb9-104">This article describes the recommended practices for deploying Microsoft Edge in an enterprise environment.</span></span>

>[!NOTE]
><span data-ttu-id="eebb9-105">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="eebb9-105">This article applies to Microsoft Edge version 77 or later.</span></span>

<span data-ttu-id="eebb9-106">以下部分针对 Microsoft Edge 部署规划提供了具体指导。</span><span class="sxs-lookup"><span data-stu-id="eebb9-106">The following sections provide specific guidance for planning your Microsoft Edge deployment.</span></span>

- [<span data-ttu-id="eebb9-107">评估浏览器环境和要求</span><span class="sxs-lookup"><span data-stu-id="eebb9-107">Evaluate browser environment and requirements</span></span>](#evaluate-your-existing-browser-environment-and-browser-needs)
- [<span data-ttu-id="eebb9-108">确保 Windows 10 设备准备就绪</span><span class="sxs-lookup"><span data-stu-id="eebb9-108">Make sure Windows 10 devices are ready</span></span>](#make-sure-your-windows-10-devices-are-ready)
- [<span data-ttu-id="eebb9-109">选择部署方法</span><span class="sxs-lookup"><span data-stu-id="eebb9-109">Pick deployment methodology</span></span>](#determine-your-deployment-methodology)
- [<span data-ttu-id="eebb9-110">进行站点发现</span><span class="sxs-lookup"><span data-stu-id="eebb9-110">Do site discovery</span></span>](#do-site-discovery)
- [<span data-ttu-id="eebb9-111">选择渠道策略</span><span class="sxs-lookup"><span data-stu-id="eebb9-111">Pick channel strategy</span></span>](#determine-your-channel-strategy)
- [<span data-ttu-id="eebb9-112">确定和配置策略</span><span class="sxs-lookup"><span data-stu-id="eebb9-112">Identify and configure policies</span></span>](#define-and-configure-policies)
- [<span data-ttu-id="eebb9-113">测试应用兼容性</span><span class="sxs-lookup"><span data-stu-id="eebb9-113">Test App compatibility</span></span>](#do-app-compatibility-testing)
- [<span data-ttu-id="eebb9-114">Microsoft Edge 试点</span><span class="sxs-lookup"><span data-stu-id="eebb9-114">Microsoft Edge pilot</span></span>](#deploy-microsoft-edge-to-a-pilot-group)
- [<span data-ttu-id="eebb9-115">评估试点</span><span class="sxs-lookup"><span data-stu-id="eebb9-115">Evaluate pilot</span></span>](#validate-your-deployment)
- [<span data-ttu-id="eebb9-116">在企业中部署 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="eebb9-116">Deploy Microsoft Edge across the enterprise</span></span>](#broad-deployment-of-microsoft-edge)

## <a name="evaluate-your-existing-browser-environment-and-browser-needs"></a><span data-ttu-id="eebb9-117">评估现有浏览器环境和浏览器需求</span><span class="sxs-lookup"><span data-stu-id="eebb9-117">Evaluate your existing browser environment and browser needs</span></span>

<span data-ttu-id="eebb9-118">请花些时间来了解当前的浏览器状态和项目远景，以确保所有项目利益相关方都保持一致并努力达到相同的结果。</span><span class="sxs-lookup"><span data-stu-id="eebb9-118">Take time to understand your current browser state and project vision to ensure that all project stakeholders are aligned and working towards the same result.</span></span>

<span data-ttu-id="eebb9-119">首先定义当前状态：</span><span class="sxs-lookup"><span data-stu-id="eebb9-119">Start by defining your current state:</span></span>

- <span data-ttu-id="eebb9-120">当前在环境中部署了哪些浏览器？</span><span class="sxs-lookup"><span data-stu-id="eebb9-120">Which browsers are currently deployed in your environment?</span></span>
- <span data-ttu-id="eebb9-121">哪个浏览器被设置为默认浏览器？</span><span class="sxs-lookup"><span data-stu-id="eebb9-121">Which browser is set as the default browser?</span></span>
- <span data-ttu-id="eebb9-122">是否需要将 Internet Explorer 用于某些应用？</span><span class="sxs-lookup"><span data-stu-id="eebb9-122">Do you need to use Internet Explorer for some of your apps?</span></span>
- <span data-ttu-id="eebb9-123">现在你是否使用企业模式站点列表配置 Internet Explorer？</span><span class="sxs-lookup"><span data-stu-id="eebb9-123">Do you use an Enterprise Mode Site List to configure Internet Explorer today?</span></span>
- <span data-ttu-id="eebb9-124">你的环境中支持哪些操作系统平台？</span><span class="sxs-lookup"><span data-stu-id="eebb9-124">What OS platforms are supported in your environment?</span></span> <span data-ttu-id="eebb9-125">（Windows 10、macOS、Windows 7、Windows Server 等）</span><span class="sxs-lookup"><span data-stu-id="eebb9-125">(Windows 10, macOS, Windows 7, Windows Server, etc.)</span></span>
- <span data-ttu-id="eebb9-126">你使用哪些管理工具进行浏览器管理？</span><span class="sxs-lookup"><span data-stu-id="eebb9-126">What management tools do you use for browser management?</span></span>
- <span data-ttu-id="eebb9-127">谁负责浏览器配置和管理？</span><span class="sxs-lookup"><span data-stu-id="eebb9-127">Who is responsible for browser configuration and management?</span></span>
- <span data-ttu-id="eebb9-128">验证浏览器兼容性的过程是什么？</span><span class="sxs-lookup"><span data-stu-id="eebb9-128">What is your process for validating browser compatibility?</span></span>

<span data-ttu-id="eebb9-129">了解当前状态后，你可以确定所需的浏览器部署目标，并考虑以下各项：</span><span class="sxs-lookup"><span data-stu-id="eebb9-129">After you understand the current state, you can determine the desired goals for your browser deployment, taking into account the following:</span></span>

- <span data-ttu-id="eebb9-130">是否要[将 Microsoft Edge 设置为默认浏览器](./edge-default-browser.md)？</span><span class="sxs-lookup"><span data-stu-id="eebb9-130">Do you want to [set Microsoft Edge as your default browser](./edge-default-browser.md)?</span></span>
- <span data-ttu-id="eebb9-131">如何[配置 Microsoft Edge](./configure-microsoft-edge.md)？</span><span class="sxs-lookup"><span data-stu-id="eebb9-131">How will you [configure Microsoft Edge](./configure-microsoft-edge.md)?</span></span>
- <span data-ttu-id="eebb9-132">初始部署过程中配置哪些功能至关重要？</span><span class="sxs-lookup"><span data-stu-id="eebb9-132">What features are critical to configure as part of your initial deployment?</span></span>
- <span data-ttu-id="eebb9-133">解决任何已确定的兼容性或配置问题的过程是什么？</span><span class="sxs-lookup"><span data-stu-id="eebb9-133">What is the process for addressing any identified compatibility or configuration issues?</span></span>

<span data-ttu-id="eebb9-134">你还应了解感兴趣的功能的**先决条件**，例如：</span><span class="sxs-lookup"><span data-stu-id="eebb9-134">You should also understand the **pre-requisites** for features you're interested in, such as:</span></span>

- [<span data-ttu-id="eebb9-135">Windows Defender 应用程序防护</span><span class="sxs-lookup"><span data-stu-id="eebb9-135">Windows Defender Application Guard</span></span>](/windows/security/threat-protection/windows-defender-application-guard/reqs-wd-app-guard)
- [<span data-ttu-id="eebb9-136">Internet Explorer 模式</span><span class="sxs-lookup"><span data-stu-id="eebb9-136">Internet Explorer mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="eebb9-137">身份验证和同步</span><span class="sxs-lookup"><span data-stu-id="eebb9-137">Authentication and sync</span></span>](./microsoft-edge-security-identity.md)

<span data-ttu-id="eebb9-138">考虑这些答案后，就可以计划 Microsoft Edge 部署了。</span><span class="sxs-lookup"><span data-stu-id="eebb9-138">With these answers in mind, you're ready to planning your Microsoft Edge deployment.</span></span>
<!--bookmark -->

## <a name="make-sure-your-windows-10-devices-are-ready"></a><span data-ttu-id="eebb9-139">确保 Windows 10 设备就绪</span><span class="sxs-lookup"><span data-stu-id="eebb9-139">Make sure your Windows 10 devices are ready</span></span>

<span data-ttu-id="eebb9-140">Microsoft Edge 稳定频道需要 2019 年 10 月（或更晚）的最新累积更新 (LCU)。</span><span class="sxs-lookup"><span data-stu-id="eebb9-140">The Edge Stable channel requires the Latest Cumulative Update (LCU) from October 2019 (or later).</span></span> <span data-ttu-id="eebb9-141">如果尝试部署到拥有较早 LCU 的 Windows 10 设备，则安装将失败。</span><span class="sxs-lookup"><span data-stu-id="eebb9-141">If you attempt to deploy to a Windows 10 device that has an older LCU, then the installation will fail.</span></span> <span data-ttu-id="eebb9-142">有关部署 Microsoft Edge 前必须应用的最小 LCU 的详细信息，请参阅[用于支持下一版本 Microsoft Edge 的 Windows 更新](./microsoft-edge-sysupdate-windows-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="eebb9-142">For more details about the minimum LCU that must be applied before deploying Edge, see [Windows updates to support the next version of Microsoft Edge](./microsoft-edge-sysupdate-windows-updates.md).</span></span>

## <a name="determine-your-deployment-methodology"></a><span data-ttu-id="eebb9-143">确定部署方法</span><span class="sxs-lookup"><span data-stu-id="eebb9-143">Determine your deployment methodology</span></span>

<span data-ttu-id="eebb9-144">在知道所需的结束状态后，便可以开始计划如何达到目的。</span><span class="sxs-lookup"><span data-stu-id="eebb9-144">After you know your desired end state, you're ready to start planning how to get there.</span></span> <span data-ttu-id="eebb9-145">部署 Microsoft Edge 的两种主要方法是按角色部署和按站点部署。</span><span class="sxs-lookup"><span data-stu-id="eebb9-145">The two main ways to deploy Microsoft Edge are by role, and by site.</span></span>

### <a name="deploy-to-end-users-by-role"></a><span data-ttu-id="eebb9-146">按角色部署到最终用户</span><span class="sxs-lookup"><span data-stu-id="eebb9-146">Deploy to end users by role</span></span>

<span data-ttu-id="eebb9-147">如果应用兼容性是你主要关注的问题，并且对要测试哪些应用没有牢固的把握，那么可能需要考虑按角色部署到最终用户。</span><span class="sxs-lookup"><span data-stu-id="eebb9-147">If app compatibility is your main concern, and you don't have a firm grasp on which apps to test, you might want to consider deploying to end users by role.</span></span> <span data-ttu-id="eebb9-148">这样，每波分阶段部署都能提供关于可能需要修改配置来解决兼容性问题的应用的反馈和见解。</span><span class="sxs-lookup"><span data-stu-id="eebb9-148">This enables each wave of a phased deployment to provide feedback and insights on apps that might need to have their configuration modified to address compatibility issues.</span></span>

### <a name="deploy-to-end-users-by-site"></a><span data-ttu-id="eebb9-149">按站点部署到最终用户</span><span class="sxs-lookup"><span data-stu-id="eebb9-149">Deploy to end users by site</span></span>

<span data-ttu-id="eebb9-150">如果带宽是你主要关注的问题，你可能需要事先考虑进行应用程序兼容性测试。</span><span class="sxs-lookup"><span data-stu-id="eebb9-150">If bandwidth is your primary concern, you might want to consider doing application compatibility testing up front.</span></span> <span data-ttu-id="eebb9-151">完成测试后，按站点部署到最终用户，以便你可以利用“缓存其他软件传递优化”这一过程。</span><span class="sxs-lookup"><span data-stu-id="eebb9-151">After you finish testing, deploy to end users by site so you can leverage caching other software delivery optimizations.</span></span>

## <a name="do-site-discovery"></a><span data-ttu-id="eebb9-152">进行站点发现</span><span class="sxs-lookup"><span data-stu-id="eebb9-152">Do site discovery</span></span>

<span data-ttu-id="eebb9-153">如果依赖旧版 Web 应用程序，并且计划使用 Internet Explorer 模式（大多数客户都使用），则可能需要进行一些额外的站点发现。</span><span class="sxs-lookup"><span data-stu-id="eebb9-153">If you have a dependency on legacy web applications, and plan to use Internet Explorer mode (which most customers do), then you probably need to do some additional site discovery.</span></span>

### <a name="if-youve-already-deployed-and-configured-the-legacy-version-of-microsoft-edge"></a><span data-ttu-id="eebb9-154">如果已经部署并配置了旧版 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="eebb9-154">If you've already deployed and configured the legacy version of Microsoft Edge</span></span>

<span data-ttu-id="eebb9-155">如果已将企业站点列表配置为适用于旧版 Microsoft Edge，则工作就已经接近完成了！</span><span class="sxs-lookup"><span data-stu-id="eebb9-155">If you've already configured your Enterprise Site List to work for the legacy version of Microsoft Edge, then your work is almost done!</span></span> <span data-ttu-id="eebb9-156">你可能需要添加的一项内容就是中性站点。</span><span class="sxs-lookup"><span data-stu-id="eebb9-156">The one thing you may need to add are neutral sites.</span></span>

<span data-ttu-id="eebb9-157">中性站点通常是提供单一登录 (SSO) 的站点。</span><span class="sxs-lookup"><span data-stu-id="eebb9-157">Neutral sites are typically sites that provide Single Sign-On (SSO).</span></span> <span data-ttu-id="eebb9-158">如果从 Microsoft Edge 中导航到中性站点，则需要保持在 Microsoft Edge 中以进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="eebb9-158">If you navigate to a neutral site from Microsoft Edge, then you want to stay in Microsoft Edge to authenticate.</span></span> <span data-ttu-id="eebb9-159">如果在 Internet Explorer 模式下导航到中性站点，则需要保持在 Internet Explorer 模式中以进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="eebb9-159">If navigate to a neutral site in Internet Explorer mode, then you want to stay in Internet Explorer mode to authenticate.</span></span>

<span data-ttu-id="eebb9-160">标识使用的任何 SSO（或其他中性）站点，并将它们添加到企业站点列表中。</span><span class="sxs-lookup"><span data-stu-id="eebb9-160">Identify any SSO (or other neutral) sites that you use and add these to your Enterprise Site List.</span></span>

### <a name="if-youve-configured-internet-explorer-as-your-default-browser"></a><span data-ttu-id="eebb9-161">如果已将 Internet Explorer 配置为默认浏览器</span><span class="sxs-lookup"><span data-stu-id="eebb9-161">If you've configured Internet Explorer as your default browser</span></span>

<span data-ttu-id="eebb9-162">如果当前仅使用 Internet Explorer，则可能不知道哪些站点已升级到新式 Web 标准，以及哪些仍需要 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="eebb9-162">If you're currently only using Internet Explorer, you might not know which sites have upgraded to modern web standards and which still require Internet Explorer.</span></span> <span data-ttu-id="eebb9-163">你需要查找这些站点并将它们添加到企业站点列表中。</span><span class="sxs-lookup"><span data-stu-id="eebb9-163">You want to find these sites and add them to the Enterprise Site List.</span></span> <span data-ttu-id="eebb9-164">这样，可以仅在需要的站点上使用 Internet Explorer 模式。</span><span class="sxs-lookup"><span data-stu-id="eebb9-164">This lets you use Internet Explorer mode only on the sites that need it.</span></span>

> [!TIP]
> <span data-ttu-id="eebb9-165">使用[企业站点发现](/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery)工具发现可能需要使用 Internet Explorer 模式的站点。</span><span class="sxs-lookup"><span data-stu-id="eebb9-165">Use the [Enterprise Site Discovery](/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery) tools to discover the sites that might need Internet Explorer mode.</span></span> <span data-ttu-id="eebb9-166">通过 Windows 10、Windows 8.1 或 Windows 7 上的 Internet Explorer 11，你可以在运行 Windows Internet Explorer 8 的计算机上收集数据。</span><span class="sxs-lookup"><span data-stu-id="eebb9-166">You can collect collect data on computers running Windows Internet Explorer 8 through Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7.</span></span>

### <a name="analyze-site-discovery-data"></a><span data-ttu-id="eebb9-167">分析站点发现数据</span><span class="sxs-lookup"><span data-stu-id="eebb9-167">Analyze site discovery data</span></span>

<span data-ttu-id="eebb9-168">收集站点数据后，我们建议采用以下 4 步过程来分析数据：</span><span class="sxs-lookup"><span data-stu-id="eebb9-168">After you've collected site data, we recommend the following 4-step process to analyze the data:</span></span>

1. <span data-ttu-id="eebb9-169">依次按域和 URL 对数据进行排序。</span><span class="sxs-lookup"><span data-stu-id="eebb9-169">Sort the data by domain, and then by URL.</span></span>
2. <span data-ttu-id="eebb9-170">定义要为 Internet Explorer 模式配置的“应用”的边界。</span><span class="sxs-lookup"><span data-stu-id="eebb9-170">Define the boundaries of an "app" to configure for Internet Explorer mode.</span></span> <span data-ttu-id="eebb9-171">你需要包含定义该应用的所有站点和 Web 控件。</span><span class="sxs-lookup"><span data-stu-id="eebb9-171">You want to include all the sites and web controls that define the app.</span></span> <span data-ttu-id="eebb9-172">但是，不需要过于广泛地定义应用来包含各种额外的站点和控件。</span><span class="sxs-lookup"><span data-stu-id="eebb9-172">But you don't want to include any extra sites and controls by defining the app too broadly.</span></span> <span data-ttu-id="eebb9-173">某些站点可能像“http://contoso.com/app1”一样简单，而其他站点可能要求定义多个站点和页面。</span><span class="sxs-lookup"><span data-stu-id="eebb9-173">Some sites may be as simple as "http://contoso.com/app1" while others may require you to define multiple sites and pages.</span></span>
3. <span data-ttu-id="eebb9-174">测试应用以验证它是否未在本机工作。</span><span class="sxs-lookup"><span data-stu-id="eebb9-174">Test the app to verify that it doesn't work natively.</span></span> <span data-ttu-id="eebb9-175">许多站点在检测到新式浏览器时将提供新式内容，并且仅在检测到 Internet Explorer 时才提供旧版内容。</span><span class="sxs-lookup"><span data-stu-id="eebb9-175">Many sites will offer modern content when they detect a modern browser, and only offer legacy content when they detect Internet Explorer.</span></span>
4. <span data-ttu-id="eebb9-176">如果应用未通过测试，请将该应用添加到企业站点列表中。</span><span class="sxs-lookup"><span data-stu-id="eebb9-176">Add the app to your Enterprise Site list if it fails testing.</span></span>

   > [!NOTE]
   > <span data-ttu-id="eebb9-177">作为最佳做法，请将构成应用的所有站点归为一组。</span><span class="sxs-lookup"><span data-stu-id="eebb9-177">As a best practice, group all of the sites that comprise an app.</span></span> <span data-ttu-id="eebb9-178">如果所有站点都需要用于完成同一项任务，并且如果这些站点通常一起更新，则充分表明应将它们归组。</span><span class="sxs-lookup"><span data-stu-id="eebb9-178">If the sites all need to be used to accomplish one task, and if they tend to be updated together, that is a good indication that they should be grouped.</span></span> <span data-ttu-id="eebb9-179">这样，当升级应用时，可以更轻松地从 Internet Explorer 模式中删除整个站点并开始将新式浏览器用于该应用。</span><span class="sxs-lookup"><span data-stu-id="eebb9-179">This way, when you upgrade an app, it's easier to remove the entire site from Internet Explorer mode and start using a modern browser for that app.</span></span>

## <a name="determine-your-channel-strategy"></a><span data-ttu-id="eebb9-180">确定渠道策略</span><span class="sxs-lookup"><span data-stu-id="eebb9-180">Determine your channel strategy</span></span>

<span data-ttu-id="eebb9-181">Microsoft Edge 通过[多个渠道](./microsoft-edge-channels.md)进行发布。</span><span class="sxs-lookup"><span data-stu-id="eebb9-181">Microsoft Edge is released in [multiple channels](./microsoft-edge-channels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="eebb9-182">你可以在设备上安装多个渠道</span><span class="sxs-lookup"><span data-stu-id="eebb9-182">You can install more than one channel on a device</span></span>

<span data-ttu-id="eebb9-183">稳定渠道是你将要部署到大多数设备上的渠道。</span><span class="sxs-lookup"><span data-stu-id="eebb9-183">The Stable Channel is what you will want to deploy to most devices.</span></span> <span data-ttu-id="eebb9-184">但是，应该考虑包含多个设备和多个渠道的部署策略。</span><span class="sxs-lookup"><span data-stu-id="eebb9-184">However, you should consider a deployment strategy that includes multiple devices and multiple channels.</span></span>

### <a name="multiple-devices-and-channels"></a><span data-ttu-id="eebb9-185">多个设备和渠道</span><span class="sxs-lookup"><span data-stu-id="eebb9-185">Multiple devices and channels</span></span>

<span data-ttu-id="eebb9-186">我们建议将具有代表性的设备子集配置为使用 Beta 渠道。</span><span class="sxs-lookup"><span data-stu-id="eebb9-186">We recommend having a representative subset of devices configured to use the Beta Channel.</span></span> <span data-ttu-id="eebb9-187">这使你可以预览即将推出的浏览器更改。</span><span class="sxs-lookup"><span data-stu-id="eebb9-187">This lets you preview upcoming changes to the browser.</span></span> <span data-ttu-id="eebb9-188">你可以查看这些更改是否会影响最终用户或应用。</span><span class="sxs-lookup"><span data-stu-id="eebb9-188">You can see if these changes are going to affect your end users or apps.</span></span>

<span data-ttu-id="eebb9-189">你可能还需要为某些角色（如 Web 开发人员）提供 Dev 渠道（或者甚至是 Canary 渠道）。</span><span class="sxs-lookup"><span data-stu-id="eebb9-189">You might also want to make the Dev Channel (or even the Canary Channel) available to some roles, such as web developers.</span></span> <span data-ttu-id="eebb9-190">考虑是想要针对渠道更加流畅且快速变化的某些设备，还是只是让这些渠道可供用户选择安装。</span><span class="sxs-lookup"><span data-stu-id="eebb9-190">Consider whether you would like to target some devices with more fluid and rapidly changing channels, or simply make these channels available for users to opt to install.</span></span>

<span data-ttu-id="eebb9-191">因为可以在设备上安装多个渠道，所以可以针对已选择安装预发布版渠道的用户缓解测试风险。</span><span class="sxs-lookup"><span data-stu-id="eebb9-191">Because it's possible to install multiple channels on a device, you can mitigate the risk of testing for users who have opted to install a pre-release channel.</span></span> <span data-ttu-id="eebb9-192">例如，如果你有一位使用 Beta 渠道的用户，并且出现了问题，那么他们可以切换到稳定渠道，然后继续工作。</span><span class="sxs-lookup"><span data-stu-id="eebb9-192">For example, if you have a user who's using the Beta Channel, and there's a problem, they can switch to the Stable Channel and continue working.</span></span> <span data-ttu-id="eebb9-193">这会取消阻止他们，直到问题得以解决。</span><span class="sxs-lookup"><span data-stu-id="eebb9-193">This unblocks them until the issue can be fixed.</span></span>

> [!NOTE]
> <span data-ttu-id="eebb9-194">如果用户启用了同步，则其配置将跨渠道同步，从而使渠道之间的过渡变得更容易。</span><span class="sxs-lookup"><span data-stu-id="eebb9-194">If the user enabled Sync, then their configuration will sync across channels, making it even easier to transition between channels.</span></span>

## <a name="define-and-configure-policies"></a><span data-ttu-id="eebb9-195">定义和配置策略</span><span class="sxs-lookup"><span data-stu-id="eebb9-195">Define and configure policies</span></span>

<span data-ttu-id="eebb9-196">创建企业站点列表后，我们建议确定和配置打算使用 Microsoft Edge 部署的策略。</span><span class="sxs-lookup"><span data-stu-id="eebb9-196">After you've created your Enterprise Site List, we recommend identifying and configuring the policies that you intend to deploy with Microsoft Edge.</span></span> <span data-ttu-id="eebb9-197">这可确保在执行测试时应用这些策略。</span><span class="sxs-lookup"><span data-stu-id="eebb9-197">This ensures that these policies are applied when you perform your testing.</span></span>

<span data-ttu-id="eebb9-198">首先，考虑希望用户拥有的首次运行体验。</span><span class="sxs-lookup"><span data-stu-id="eebb9-198">First, consider the first-run experience you want your users to have.</span></span> <span data-ttu-id="eebb9-199">如果想要自动导入当前浏览器中的设置，请配置 [AutoImportAtFirstRun](./microsoft-edge-policies.md#autoimportatfirstrun) 策略。</span><span class="sxs-lookup"><span data-stu-id="eebb9-199">If you want to automatically import settings from the current browser, configure the policy for [AutoImportAtFirstRun](./microsoft-edge-policies.md#autoimportatfirstrun).</span></span>

<span data-ttu-id="eebb9-200">对于安全策略，我们建议从 Microsoft Edge 安全基准开始。</span><span class="sxs-lookup"><span data-stu-id="eebb9-200">For security policies, we recommend starting with the Microsoft Edge Security Baseline.</span></span> <span data-ttu-id="eebb9-201">可以使用[推荐的安全配置基准设置](https://techcommunity.microsoft.com/t5/Microsoft-Security-Baselines/Security-baseline-DRAFT-for-Chromium-based-Microsoft-Edge/ba-p/949991)或使用 [Microsoft Intune](/intune/protect/security-baseline-settings-edge) 来应用安全基准。</span><span class="sxs-lookup"><span data-stu-id="eebb9-201">The Security Baseline can be applied using the [recommended security configuration baseline settings](https://techcommunity.microsoft.com/t5/Microsoft-Security-Baselines/Security-baseline-DRAFT-for-Chromium-based-Microsoft-Edge/ba-p/949991) or by using [Microsoft Intune](/intune/protect/security-baseline-settings-edge).</span></span>

<span data-ttu-id="eebb9-202">对于其他策略，我们建议查看 [Microsoft Edge](./microsoft-edge-policies.md) 和 [Microsoft Edge 更新](./microsoft-edge-update-policies.md)的策略配置。</span><span class="sxs-lookup"><span data-stu-id="eebb9-202">For other policies, we recommend reviewing the policy configurations for [Microsoft Edge](./microsoft-edge-policies.md) and [Microsoft Edge Updates](./microsoft-edge-update-policies.md).</span></span>

### <a name="define-your-update-strategy-and-policies"></a><span data-ttu-id="eebb9-203">定义更新策略和策略</span><span class="sxs-lookup"><span data-stu-id="eebb9-203">Define your update strategy and policies</span></span>

<span data-ttu-id="eebb9-204">你还需要确定在部署 Microsoft Edge 后想要如何进行更新：</span><span class="sxs-lookup"><span data-stu-id="eebb9-204">You also want to determine how you want to do updates after you deploy Microsoft Edge:</span></span>

- <span data-ttu-id="eebb9-205">**允许 Microsoft Edge 自行更新**（默认）。</span><span class="sxs-lookup"><span data-stu-id="eebb9-205">**Allow Microsoft Edge to update itself** (default).</span></span> <span data-ttu-id="eebb9-206">如果选择允许 Microsoft Edge 自动更新，则 Microsoft Edge 将按照你部署的渠道所确定的节奏自动更新自身。</span><span class="sxs-lookup"><span data-stu-id="eebb9-206">If you choose to allow automatic updates of Microsoft Edge, then Microsoft Edge will automatically update itself at the pace determined by the channel(s) you deployed.</span></span>
- <span data-ttu-id="eebb9-207">**按照自己的节奏更新 Microsoft Edge**。</span><span class="sxs-lookup"><span data-stu-id="eebb9-207">**Update Microsoft Edge at your own pace**.</span></span> <span data-ttu-id="eebb9-208">如果你希望显式控制部署更新的时间，则可以禁用自动更新并自行部署更新（请参阅[更新策略参考](./microsoft-edge-update-policies.md)）。在禁用自动更新后，你可以使用以下工具之一为每个渠道部署更新：</span><span class="sxs-lookup"><span data-stu-id="eebb9-208">If you prefer to have explicit control over when updates are deployed, you can disable automatic updates and deploy it yourself (see the [Update Policy reference](./microsoft-edge-update-policies.md).) After you disable automatic updates you can deploy updates for each channel using one of the following tools:</span></span>

- [<span data-ttu-id="eebb9-209">Intune</span><span class="sxs-lookup"><span data-stu-id="eebb9-209">Intune</span></span>](/intune/apps/apps-windows-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)
- [<span data-ttu-id="eebb9-210">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="eebb9-210">Configuration Manager</span></span>](./deploy-edge-with-configuration-manager.md)
- <span data-ttu-id="eebb9-211">你选择的部署工具。</span><span class="sxs-lookup"><span data-stu-id="eebb9-211">the deployment tool of your choice.</span></span>

<span data-ttu-id="eebb9-212">无论采用何种更新策略，我们都建议充分利用环形部署策略。</span><span class="sxs-lookup"><span data-stu-id="eebb9-212">Regardless of your update strategy, we recommend leveraging a ringed deployment strategy.</span></span> <span data-ttu-id="eebb9-213">对于自动更新，这意味着要有运行 Beta 渠道的代表性用户样本，以确定关于什么将成为稳定渠道的问题。</span><span class="sxs-lookup"><span data-stu-id="eebb9-213">With automatic updates, this means having a representative sample of users running the Beta Channel, to identify issues with what will become the Stable Channel.</span></span> <span data-ttu-id="eebb9-214">对于手动更新，这可能还包括在发布新的稳定渠道版本后对试点组进行的其他验证。</span><span class="sxs-lookup"><span data-stu-id="eebb9-214">With manual updates, this might also include additional validation of a pilot group after a new Stable Channel build is released.</span></span> <span data-ttu-id="eebb9-215">接下来就是广泛部署。</span><span class="sxs-lookup"><span data-stu-id="eebb9-215">This is followed by broad deployment.</span></span>

>[!NOTE]
><span data-ttu-id="eebb9-216">Microsoft Edge 支持将仅适用于每个渠道中的最新版本的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="eebb9-216">Microsoft Edge support will only apply to the most recent version of Microsoft Edge in each channel</span></span>

## <a name="do-app-compatibility-testing"></a><span data-ttu-id="eebb9-217">执行应用兼容性测试</span><span class="sxs-lookup"><span data-stu-id="eebb9-217">Do app compatibility testing</span></span>

<span data-ttu-id="eebb9-218">Microsoft Edge 的应用程序兼容性相当高 - 因此，Microsoft 提供以下兼容性承诺：</span><span class="sxs-lookup"><span data-stu-id="eebb9-218">Application compatibility for Microsoft Edge is extremely high - so high that Microsoft provides the following compatibility promises:</span></span>

1. <span data-ttu-id="eebb9-219">如果适用于 *Microsoft Edge* 版本 45 和更早版本，则适用于 Microsoft Edge *版本 77 和更高版本*。</span><span class="sxs-lookup"><span data-stu-id="eebb9-219">If it works on Microsoft Edge *version 45 and earlier*, it will work on Microsoft Edge *version 77 and later*.</span></span>
2. <span data-ttu-id="eebb9-220">如果适用于 Internet Explorer，那么将在 Internet Explorer 模式下适用于 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="eebb9-220">If it works on Internet Explorer, it will work on Microsoft Edge in Internet Explorer mode.</span></span>
3. <span data-ttu-id="eebb9-221">如果适用于 Google Chrome，则将适用于 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="eebb9-221">If it works on Google Chrome, it will work on Microsoft Edge.</span></span>

<span data-ttu-id="eebb9-222">如果你有一款应用程序，而我们未在该应用中兑现我们的兼容性承诺，那么我们将坚守承诺，使用 [Microsoft 应用保证](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure)来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="eebb9-222">If you have an application where we don't meet our compatibility promise, then we stand behind the promise to fix it with [Microsoft App Assure](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure).</span></span>

### <a name="internal-line-of-business-app-testing"></a><span data-ttu-id="eebb9-223">内部业务线应用测试</span><span class="sxs-lookup"><span data-stu-id="eebb9-223">Internal line of business app testing</span></span>

<span data-ttu-id="eebb9-224">尽管我们有兼容性承诺，但我们知道许多组织必须验证某些应用程序的合规性或风险管理原因。</span><span class="sxs-lookup"><span data-stu-id="eebb9-224">Despite our compatibility promise, we know that many organizations must validate some applications for their compliance or risk management reasons.</span></span> <span data-ttu-id="eebb9-225">尽管我们希望简单直接地测试应用，但此过程务必要做到严格有序。</span><span class="sxs-lookup"><span data-stu-id="eebb9-225">Even though we expect this to be very straightforward, it's important to be organized and rigorous in app testing.</span></span>

<span data-ttu-id="eebb9-226">有两种方法可以执行应用兼容性测试：</span><span class="sxs-lookup"><span data-stu-id="eebb9-226">There are 2 ways to do app compatibility testing:</span></span>

1. <span data-ttu-id="eebb9-227">实验室测试。</span><span class="sxs-lookup"><span data-stu-id="eebb9-227">Lab testing.</span></span> <span data-ttu-id="eebb9-228">使用特定配置在严格控制的环境中验证应用程序。</span><span class="sxs-lookup"><span data-stu-id="eebb9-228">Applications are validated in a tightly controlled environment with specific configurations.</span></span>
2. <span data-ttu-id="eebb9-229">试验测试。</span><span class="sxs-lookup"><span data-stu-id="eebb9-229">Pilot testing.</span></span> <span data-ttu-id="eebb9-230">少量用户使用他们自己的设备在其日常工作环境中验证应用程序。</span><span class="sxs-lookup"><span data-stu-id="eebb9-230">Applications are validated by a limited number of users in their daily work environment using their own devices.</span></span>

<span data-ttu-id="eebb9-231">选择最适合每个应用的方法来管理风险，无需在兼容性测试方面过度投资。</span><span class="sxs-lookup"><span data-stu-id="eebb9-231">Choose the method that is most appropriate for each app,  to manage risk without over-investing in compatibility testing.</span></span>

### <a name="third-party-app-support"></a><span data-ttu-id="eebb9-232">第三方应用支持</span><span class="sxs-lookup"><span data-stu-id="eebb9-232">Third party app support</span></span>

<span data-ttu-id="eebb9-233">除了自己的业务线应用之外，很多组织还使用由外部来源提供的应用。</span><span class="sxs-lookup"><span data-stu-id="eebb9-233">In addition to their own line of business apps, many organizations use apps provided by external sources.</span></span> <span data-ttu-id="eebb9-234">[准备好使用 Microsoft Edge](deploy-edge-ready-for-edge.md) 文章有一个列表，其中列出了可能已在你的组织中使用的 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="eebb9-234">The [Ready for Microsoft Edge](deploy-edge-ready-for-edge.md) article contains a list of web applications that may be in use within your organization.</span></span> <span data-ttu-id="eebb9-235">此列表提供提供商支持声明链接，在将其产品与 Microsoft Edge 结合使用时可进行查看。</span><span class="sxs-lookup"><span data-stu-id="eebb9-235">This list provides links to provider support statements for their products when used with Microsoft Edge.</span></span>

## <a name="deploy-microsoft-edge-to-a-pilot-group"></a><span data-ttu-id="eebb9-236">将 Microsoft Edge 部署到试点组</span><span class="sxs-lookup"><span data-stu-id="eebb9-236">Deploy Microsoft Edge to a pilot group</span></span>

<span data-ttu-id="eebb9-237">在定义策略并完成初始应用兼容性测试后，即可开始部署到试点组。</span><span class="sxs-lookup"><span data-stu-id="eebb9-237">After you've defined your policies and have finished your initial app compatibility testing, you're ready to deploy to your pilot group.</span></span> <span data-ttu-id="eebb9-238">使用以下工具之一部署到试点组：</span><span class="sxs-lookup"><span data-stu-id="eebb9-238">Deploy to your pilot group using one of the following tools:</span></span>

- <span data-ttu-id="eebb9-239">[适用于 Windows 的 Microsoft Intune](/intune/apps/apps-windows-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json) 或[适用于 macOS 的 Microsoft Intune](/intune/apps/apps-edge-macos?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="eebb9-239">[Microsoft Intune for Windows](/intune/apps/apps-windows-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json), or [Microsoft Intune for macOS](/intune/apps/apps-edge-macos?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)</span></span>
- <span data-ttu-id="eebb9-240">[Configuration Manager](./deploy-edge-with-configuration-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="eebb9-240">[Configuration Manager](./deploy-edge-with-configuration-manager.md).</span></span>
- <span data-ttu-id="eebb9-241">另一个管理工具，下载并部署 [Microsoft Edge 的 MSI 文件](https://www.microsoftedgeinsider.com/enterprise)。</span><span class="sxs-lookup"><span data-stu-id="eebb9-241">Another management tool, download and deploy the [MSI file for Microsoft Edge](https://www.microsoftedgeinsider.com/enterprise).</span></span>

## <a name="validate-your-deployment"></a><span data-ttu-id="eebb9-242">验证你的部署</span><span class="sxs-lookup"><span data-stu-id="eebb9-242">Validate your deployment</span></span>

<span data-ttu-id="eebb9-243">部署试验版后，需要捕获从用户那里获取的所有反馈。</span><span class="sxs-lookup"><span data-stu-id="eebb9-243">After you deploy your pilot, you want to capture all the feedback you get from your users.</span></span>

- <span data-ttu-id="eebb9-244">捕获有关兼容性的反馈。</span><span class="sxs-lookup"><span data-stu-id="eebb9-244">Capture feedback on compatibility.</span></span> <span data-ttu-id="eebb9-245">确定属于企业站点列表并且在站点发现期间未标识的站点。</span><span class="sxs-lookup"><span data-stu-id="eebb9-245">Identify sites that belong on the Enterprise Site List that weren't identified during site discovery.</span></span>
- <span data-ttu-id="eebb9-246">捕获有关策略配置的反馈。</span><span class="sxs-lookup"><span data-stu-id="eebb9-246">Capture feedback on the policy configuration.</span></span> <span data-ttu-id="eebb9-247">确保用户可以在遵循安全指南时使用关键功能并执行其工作。</span><span class="sxs-lookup"><span data-stu-id="eebb9-247">Ensure that users can use key features and do their work while following security guidelines.</span></span>
- <span data-ttu-id="eebb9-248">捕获有关易用性和新功能的反馈。</span><span class="sxs-lookup"><span data-stu-id="eebb9-248">Capture feedback on ease of use and new features.</span></span> <span data-ttu-id="eebb9-249">确定任何应根据用户问题开发和提供培训的领域。</span><span class="sxs-lookup"><span data-stu-id="eebb9-249">Identify any areas where training should be developed and delivered based on user questions.</span></span>

## <a name="broad-deployment-of-microsoft-edge"></a><span data-ttu-id="eebb9-250">Microsoft Edge 的广泛部署</span><span class="sxs-lookup"><span data-stu-id="eebb9-250">Broad deployment of Microsoft Edge</span></span>

<span data-ttu-id="eebb9-251">在完成试验并根据从试验中吸取的经验教训更新部署计划后，就可以向所有用户全面部署 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="eebb9-251">After a finishing the pilot and updating your deployment plan with lessons learned from the pilot, you're ready to do a full deployment of Microsoft Edge to all your users.</span></span>  <span data-ttu-id="eebb9-252">恭喜你！</span><span class="sxs-lookup"><span data-stu-id="eebb9-252">Congratulations!</span></span>

## <a name="see-also"></a><span data-ttu-id="eebb9-253">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eebb9-253">See also</span></span>

- [<span data-ttu-id="eebb9-254">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="eebb9-254">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="eebb9-255">视频 - 部署 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="eebb9-255">Video - Deploy Microsoft Edge</span></span>](microsoft-edge-video-deploy.md)