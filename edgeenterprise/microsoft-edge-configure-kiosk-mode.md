---
title: 配置 Microsoft Edge 展台模式
ms.author: aguta
author: aguta
manager: srugh
ms.date: 03/03/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解展台模式功能以及如何配置 Microsoft Edge 展台模式的选项。
ms.openlocfilehash: 9f2ce26f2c505ba3fc9e2e05b057e5d5df8257fe
ms.sourcegitcommit: 8da3a4de1a14514014b6d7b103ba79f2ace48044
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "11388544"
---
# <a name="configure-microsoft-edge-kiosk-mode"></a><span data-ttu-id="3fc03-103">配置 Microsoft Edge 展台模式</span><span class="sxs-lookup"><span data-stu-id="3fc03-103">Configure Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="3fc03-104">本文介绍如何配置可以试用的 Microsoft Edge 展台模式选项。</span><span class="sxs-lookup"><span data-stu-id="3fc03-104">This article describes how to configure Microsoft Edge kiosk mode options that you can pilot.</span></span> <span data-ttu-id="3fc03-105">还有一个在我们目标之中的功能路线图。</span><span class="sxs-lookup"><span data-stu-id="3fc03-105">There's also a roadmap of features we're targeting.</span></span>

> [!NOTE]
> <span data-ttu-id="3fc03-106">本文适用于 Microsoft Edge 版本 87 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="3fc03-106">This article applies to Microsoft Edge version 87 or later.</span></span>

## <a name="overview"></a><span data-ttu-id="3fc03-107">概述</span><span class="sxs-lookup"><span data-stu-id="3fc03-107">Overview</span></span>

<span data-ttu-id="3fc03-108">Microsoft Edge 展台模式提供两种浏览器锁定体验，因此组织可以创建、管理并为其客户提供最佳体验。</span><span class="sxs-lookup"><span data-stu-id="3fc03-108">Microsoft Edge kiosk mode offers two lockdown experiences of the browser so organizations can create, manage, and provide the best experience for their customers.</span></span> <span data-ttu-id="3fc03-109">提供以下锁定体验：</span><span class="sxs-lookup"><span data-stu-id="3fc03-109">The following lockdown experiences are available:</span></span>  

- <span data-ttu-id="3fc03-110">**数字/交互式标志** 体验 - 以全屏模式显示特定网站。</span><span class="sxs-lookup"><span data-stu-id="3fc03-110">**Digital/Interactive Signage** experience - Displays a specific site in full-screen mode.</span></span>
- <span data-ttu-id="3fc03-111">**公共浏览** 体验 - 运行 Microsoft Edge 的有限多选项卡版本。</span><span class="sxs-lookup"><span data-stu-id="3fc03-111">**Public-Browsing** experience - Runs a limited multi-tab version of Microsoft Edge.</span></span>

<span data-ttu-id="3fc03-112">这两种体验都在运行 Microsoft Edge InPrivate 会话，以保护用户数据。</span><span class="sxs-lookup"><span data-stu-id="3fc03-112">Both experiences are running a Microsoft Edge InPrivate session, which protects user data.</span></span>

## <a name="set-up-microsoft-edge-kiosk-mode"></a><span data-ttu-id="3fc03-113">设置 Microsoft Edge 展台模式</span><span class="sxs-lookup"><span data-stu-id="3fc03-113">Set up Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="3fc03-114">可以使用 Microsoft Edge Stable 渠道版本 87 测试一组初始展台模式功能。</span><span class="sxs-lookup"><span data-stu-id="3fc03-114">An initial set of kiosk mode features is available to test with Microsoft Edge Stable Channel, version 87.</span></span> <span data-ttu-id="3fc03-115">你可以从 [Microsoft Edge (Official Stable 渠道)](https://www.microsoft.com/edge)下载。</span><span class="sxs-lookup"><span data-stu-id="3fc03-115">You can download the latest version from [Microsoft Edge (Official Stable Channel)](https://www.microsoft.com/edge).</span></span>

### <a name="kiosk-mode-supported-features"></a><span data-ttu-id="3fc03-116">展台模式支持的功能</span><span class="sxs-lookup"><span data-stu-id="3fc03-116">Kiosk mode supported features</span></span>

<span data-ttu-id="3fc03-117">下表列出了 Microsoft Edge 和 Microsoft Edge 旧版中的展台模式支持的功能。</span><span class="sxs-lookup"><span data-stu-id="3fc03-117">The following table lists the features supported by kiosk mode in Microsoft Edge and Microsoft Edge Legacy.</span></span> <span data-ttu-id="3fc03-118">比较这两个版本的 Microsoft Edge 支持的功能有何不同，将此表用作指南以转换为 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="3fc03-118">Use this table as a guide to transitioning to Microsoft Edge by comparing how these features are supported in both versions of Microsoft Edge.</span></span>

|<span data-ttu-id="3fc03-119">功能</span><span class="sxs-lookup"><span data-stu-id="3fc03-119">Feature</span></span>|<span data-ttu-id="3fc03-120">数字\交互式标志</span><span class="sxs-lookup"><span data-stu-id="3fc03-120">Digital\Interactive Signage</span></span>|<span data-ttu-id="3fc03-121">公共浏览</span><span class="sxs-lookup"><span data-stu-id="3fc03-121">Public browsing</span></span>|<span data-ttu-id="3fc03-122">适用于 Microsoft Edge 版本（及更高版本）</span><span class="sxs-lookup"><span data-stu-id="3fc03-122">Available with Microsoft Edge version (and higher)</span></span>|<span data-ttu-id="3fc03-123">适用于 Microsoft Edge 旧版</span><span class="sxs-lookup"><span data-stu-id="3fc03-123">Available with Microsoft Edge Legacy</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="3fc03-124">InPrivate 导航</span><span class="sxs-lookup"><span data-stu-id="3fc03-124">InPrivate Navigation</span></span>|<span data-ttu-id="3fc03-125">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-125">Y</span></span>|<span data-ttu-id="3fc03-126">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-126">Y</span></span>|<span data-ttu-id="3fc03-127">89</span><span class="sxs-lookup"><span data-stu-id="3fc03-127">89</span></span>|<span data-ttu-id="3fc03-128">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-128">Y</span></span>|
|<span data-ttu-id="3fc03-129">在处于非活动状态时重置</span><span class="sxs-lookup"><span data-stu-id="3fc03-129">Reset on inactivity</span></span>|<span data-ttu-id="3fc03-130">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-130">Y</span></span>|<span data-ttu-id="3fc03-131">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-131">Y</span></span>|<span data-ttu-id="3fc03-132">89</span><span class="sxs-lookup"><span data-stu-id="3fc03-132">89</span></span>|<span data-ttu-id="3fc03-133">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-133">Y</span></span>|
|<span data-ttu-id="3fc03-134">[只读地址栏](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) (策略)</span><span class="sxs-lookup"><span data-stu-id="3fc03-134">[Read only address bar](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) (policy)</span></span> |<span data-ttu-id="3fc03-135">N</span><span class="sxs-lookup"><span data-stu-id="3fc03-135">N</span></span>|<span data-ttu-id="3fc03-136">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-136">Y</span></span> |<span data-ttu-id="3fc03-137">89</span><span class="sxs-lookup"><span data-stu-id="3fc03-137">89</span></span>|<span data-ttu-id="3fc03-138">N</span><span class="sxs-lookup"><span data-stu-id="3fc03-138">N</span></span>|
|<span data-ttu-id="3fc03-139">[退出时删除下载](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit)（策略）</span><span class="sxs-lookup"><span data-stu-id="3fc03-139">[Delete downloads on exit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit) (policy)</span></span>  | <span data-ttu-id="3fc03-140">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-140">Y</span></span>|<span data-ttu-id="3fc03-141">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-141">Y</span></span> |<span data-ttu-id="3fc03-142">89</span><span class="sxs-lookup"><span data-stu-id="3fc03-142">89</span></span>|<span data-ttu-id="3fc03-143">N</span><span class="sxs-lookup"><span data-stu-id="3fc03-143">N</span></span>|
|<span data-ttu-id="3fc03-144">已阻止 F11（进入/退出全屏）</span><span class="sxs-lookup"><span data-stu-id="3fc03-144">F11 blocked (enter/exit full-screen)</span></span> | <span data-ttu-id="3fc03-145">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-145">Y</span></span> | <span data-ttu-id="3fc03-146">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-146">Y</span></span> | <span data-ttu-id="3fc03-147">89</span><span class="sxs-lookup"><span data-stu-id="3fc03-147">89</span></span> |<span data-ttu-id="3fc03-148">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-148">Y</span></span>|
|<span data-ttu-id="3fc03-149">已阻止F12（启动开发人员工具）</span><span class="sxs-lookup"><span data-stu-id="3fc03-149">F12 blocked (launch Developer Tools)</span></span> | <span data-ttu-id="3fc03-150">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-150">Y</span></span> | <span data-ttu-id="3fc03-151">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-151">Y</span></span> | <span data-ttu-id="3fc03-152">89</span><span class="sxs-lookup"><span data-stu-id="3fc03-152">89</span></span> |<span data-ttu-id="3fc03-153">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-153">Y</span></span>|
| <span data-ttu-id="3fc03-154">多选项卡支持</span><span class="sxs-lookup"><span data-stu-id="3fc03-154">Multi tab support</span></span> | <span data-ttu-id="3fc03-155">N</span><span class="sxs-lookup"><span data-stu-id="3fc03-155">N</span></span>| <span data-ttu-id="3fc03-156">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-156">Y</span></span>| <span data-ttu-id="3fc03-157">89</span><span class="sxs-lookup"><span data-stu-id="3fc03-157">89</span></span>|<span data-ttu-id="3fc03-158">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-158">Y</span></span>|
|<span data-ttu-id="3fc03-159">[允许 URL 支持](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlallowlist)（策略）</span><span class="sxs-lookup"><span data-stu-id="3fc03-159">[Allow URL support](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlallowlist) (policy)</span></span>|<span data-ttu-id="3fc03-160">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-160">Y</span></span>|<span data-ttu-id="3fc03-161">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-161">Y</span></span>|<span data-ttu-id="3fc03-162">89</span><span class="sxs-lookup"><span data-stu-id="3fc03-162">89</span></span>|<span data-ttu-id="3fc03-163">N</span><span class="sxs-lookup"><span data-stu-id="3fc03-163">N</span></span>|
|<span data-ttu-id="3fc03-164">[阻止 URL 支持](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlblocklist)（策略）</span><span class="sxs-lookup"><span data-stu-id="3fc03-164">[Block URL support](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlblocklist) (policy)</span></span>|<span data-ttu-id="3fc03-165">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-165">Y</span></span>|<span data-ttu-id="3fc03-166">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-166">Y</span></span>|<span data-ttu-id="3fc03-167">89</span><span class="sxs-lookup"><span data-stu-id="3fc03-167">89</span></span>|<span data-ttu-id="3fc03-168">N</span><span class="sxs-lookup"><span data-stu-id="3fc03-168">N</span></span>|
|<span data-ttu-id="3fc03-169">[显示“主页”按钮](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#showhomebutton)（策略）</span><span class="sxs-lookup"><span data-stu-id="3fc03-169">[Show home button](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#showhomebutton) (policy)</span></span>|<span data-ttu-id="3fc03-170">N</span><span class="sxs-lookup"><span data-stu-id="3fc03-170">N</span></span>|<span data-ttu-id="3fc03-171">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-171">Y</span></span>|<span data-ttu-id="3fc03-172">89</span><span class="sxs-lookup"><span data-stu-id="3fc03-172">89</span></span>|<span data-ttu-id="3fc03-173">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-173">Y</span></span>|
|<span data-ttu-id="3fc03-174">[管理收藏夹](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#managedfavorites)（策略）</span><span class="sxs-lookup"><span data-stu-id="3fc03-174">[Manage favorites](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#managedfavorites) (policy)</span></span>|<span data-ttu-id="3fc03-175">N</span><span class="sxs-lookup"><span data-stu-id="3fc03-175">N</span></span>|<span data-ttu-id="3fc03-176">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-176">Y</span></span>|<span data-ttu-id="3fc03-177">89</span><span class="sxs-lookup"><span data-stu-id="3fc03-177">89</span></span>|<span data-ttu-id="3fc03-178">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-178">Y</span></span>|
|<span data-ttu-id="3fc03-179">[启用打印机](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)（策略）</span><span class="sxs-lookup"><span data-stu-id="3fc03-179">[Enable printer](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled) (policy)</span></span>|<span data-ttu-id="3fc03-180">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-180">Y</span></span>|<span data-ttu-id="3fc03-181">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-181">Y</span></span>|<span data-ttu-id="3fc03-182">89</span><span class="sxs-lookup"><span data-stu-id="3fc03-182">89</span></span>|<span data-ttu-id="3fc03-183">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-183">Y</span></span>|
|<span data-ttu-id="3fc03-184">[配置新标签页页面 URL](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagelocation)（策略）</span><span class="sxs-lookup"><span data-stu-id="3fc03-184">[Configure the new tab page URL](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagelocation) (policy)</span></span>|<span data-ttu-id="3fc03-185">N</span><span class="sxs-lookup"><span data-stu-id="3fc03-185">N</span></span>|<span data-ttu-id="3fc03-186">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-186">Y</span></span>||<span data-ttu-id="3fc03-187">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-187">Y</span></span>|
|<span data-ttu-id="3fc03-188">结束会话按钮 \*</span><span class="sxs-lookup"><span data-stu-id="3fc03-188">End session button \*</span></span> | <span data-ttu-id="3fc03-189">N</span><span class="sxs-lookup"><span data-stu-id="3fc03-189">N</span></span>| <span data-ttu-id="3fc03-190">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-190">Y</span></span>| <span data-ttu-id="3fc03-191">89</span><span class="sxs-lookup"><span data-stu-id="3fc03-191">89</span></span>|<span data-ttu-id="3fc03-192">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-192">Y</span></span>|
|<span data-ttu-id="3fc03-193">所有内部 Microsoft Edge URL 已将被阻止，除了*edge://downloads*和*edge://print*</span><span class="sxs-lookup"><span data-stu-id="3fc03-193">All internal Microsoft Edge URLs are blocked, except for *edge://downloads* and *edge://print*</span></span> |<span data-ttu-id="3fc03-194">N</span><span class="sxs-lookup"><span data-stu-id="3fc03-194">N</span></span>|<span data-ttu-id="3fc03-195">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-195">Y</span></span>|<span data-ttu-id="3fc03-196">89</span><span class="sxs-lookup"><span data-stu-id="3fc03-196">89</span></span>|<span data-ttu-id="3fc03-197">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-197">Y</span></span>|
| <span data-ttu-id="3fc03-198">Ctrl+N 阻止 (打开新窗口) \*</span><span class="sxs-lookup"><span data-stu-id="3fc03-198">CTRL+N blocked (open a new window) \*</span></span> | <span data-ttu-id="3fc03-199">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-199">Y</span></span> | <span data-ttu-id="3fc03-200">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-200">Y</span></span> | <span data-ttu-id="3fc03-201">89</span><span class="sxs-lookup"><span data-stu-id="3fc03-201">89</span></span> |<span data-ttu-id="3fc03-202">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-202">Y</span></span>|
| <span data-ttu-id="3fc03-203">已阻止 Ctrl+T（打开新选项卡）</span><span class="sxs-lookup"><span data-stu-id="3fc03-203">CTRL+T blocked (open new tab)</span></span> |<span data-ttu-id="3fc03-204">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-204">Y</span></span> | <span data-ttu-id="3fc03-205">N</span><span class="sxs-lookup"><span data-stu-id="3fc03-205">N</span></span> | <span data-ttu-id="3fc03-206">89</span><span class="sxs-lookup"><span data-stu-id="3fc03-206">89</span></span> |<span data-ttu-id="3fc03-207">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-207">Y</span></span>|
|<span data-ttu-id="3fc03-208">设置和更多 (...) 将仅显示所需的选项</span><span class="sxs-lookup"><span data-stu-id="3fc03-208">Settings and more (...) will display only the required options</span></span>  |<span data-ttu-id="3fc03-209">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-209">Y</span></span> |<span data-ttu-id="3fc03-210">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-210">Y</span></span> |<span data-ttu-id="3fc03-211">89</span><span class="sxs-lookup"><span data-stu-id="3fc03-211">89</span></span> |<span data-ttu-id="3fc03-212">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-212">Y</span></span>|
|<span data-ttu-id="3fc03-213">限制从浏览器启动其他应用程序</span><span class="sxs-lookup"><span data-stu-id="3fc03-213">Restrict the launch of other applications from the browser</span></span>|<span data-ttu-id="3fc03-214">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-214">Y</span></span>|<span data-ttu-id="3fc03-215">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-215">Y</span></span>|<span data-ttu-id="3fc03-216">90/91</span><span class="sxs-lookup"><span data-stu-id="3fc03-216">90/91</span></span>|<span data-ttu-id="3fc03-217">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-217">Y</span></span>|
|<span data-ttu-id="3fc03-218">UI 打印设置锁定</span><span class="sxs-lookup"><span data-stu-id="3fc03-218">UI print settings lockdown</span></span>|<span data-ttu-id="3fc03-219">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-219">Y</span></span>|<span data-ttu-id="3fc03-220">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-220">Y</span></span>|<span data-ttu-id="3fc03-221">90/91</span><span class="sxs-lookup"><span data-stu-id="3fc03-221">90/91</span></span>|<span data-ttu-id="3fc03-222">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-222">Y</span></span>|
|<span data-ttu-id="3fc03-223">[将新标签页页面设置为主页](https://docs.microsoft.com/deployedge/microsoft-edge-policies#homepageisnewtabpage)（策略）</span><span class="sxs-lookup"><span data-stu-id="3fc03-223">[Set the new tab page as the home page](https://docs.microsoft.com/deployedge/microsoft-edge-policies#homepageisnewtabpage) (policy)</span></span>|-|-|<span data-ttu-id="3fc03-224">TBD</span><span class="sxs-lookup"><span data-stu-id="3fc03-224">TBD</span></span>|<span data-ttu-id="3fc03-225">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-225">Y</span></span>|

> [!NOTE]
> <span data-ttu-id="3fc03-226">后跟“\*”的功能仅在已分配的访问单一应用场景中启用。</span><span class="sxs-lookup"><span data-stu-id="3fc03-226">Features followed by "\*" are only enabled in an assigned access single app scenario.</span></span>

## <a name="use-kiosk-mode-features"></a><span data-ttu-id="3fc03-227">使用展台模式功能</span><span class="sxs-lookup"><span data-stu-id="3fc03-227">Use kiosk mode features</span></span>

<span data-ttu-id="3fc03-228">对于数字/交互式标牌和公共浏览，可通过以下 Windows 10 命令行选项调用 Microsoft Edge 展台模式功能。</span><span class="sxs-lookup"><span data-stu-id="3fc03-228">Microsoft Edge kiosk mode features can be invoked with the following Windows 10 command line options for Digital/Interactive signage and Public browsing.</span></span>

### <a name="kiosk-mode-digitalinteractive-signage"></a><span data-ttu-id="3fc03-229">展台模式数字/交互式标牌</span><span class="sxs-lookup"><span data-stu-id="3fc03-229">Kiosk mode Digital/Interactive signage</span></span>
 
```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen
```

### <a name="kiosk-mode-public-browsing"></a><span data-ttu-id="3fc03-230">展台模式公共浏览</span><span class="sxs-lookup"><span data-stu-id="3fc03-230">Kiosk mode Public browsing</span></span>

```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing
```

### <a name="additional-command-line-options"></a><span data-ttu-id="3fc03-231">其他命令行选项</span><span class="sxs-lookup"><span data-stu-id="3fc03-231">Additional command line options</span></span>

- <span data-ttu-id="3fc03-232">**--no-first-run**：禁用首次 Microsoft Edge 运行体验。</span><span class="sxs-lookup"><span data-stu-id="3fc03-232">**--no-first-run**: Disable the first Microsoft Edge run experience.</span></span>

   ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --no-first-run
  ```

  ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --no-first-run
  ```

- <span data-ttu-id="3fc03-233">**--kiosk-idle-timeout-minutes=**：更改从上次用户活动到 Microsoft Edge 展台模式重置用户会话前的时间（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="3fc03-233">**--kiosk-idle-timeout-minutes=**: Change the time (in minutes) from the last user activity before Microsoft Edge kiosk mode resets the user's session.</span></span> <span data-ttu-id="3fc03-234">将以下示例中的“值”替换为分钟数。</span><span class="sxs-lookup"><span data-stu-id="3fc03-234">Replace "value" in the next example with the number of minutes.</span></span>

   ```
   --kiosk-idle-timeout-minutes=value
   ``` 
   <span data-ttu-id="3fc03-235">支持以下“值”：</span><span class="sxs-lookup"><span data-stu-id="3fc03-235">The following "values" are supported:</span></span>

     - <span data-ttu-id="3fc03-236">默认值（分钟）</span><span class="sxs-lookup"><span data-stu-id="3fc03-236">Default values (in minutes)</span></span>
       - <span data-ttu-id="3fc03-237">全屏 - 0（关闭）</span><span class="sxs-lookup"><span data-stu-id="3fc03-237">Full screen - 0 (turned off)</span></span>
       - <span data-ttu-id="3fc03-238">公共浏览 - 5 分钟</span><span class="sxs-lookup"><span data-stu-id="3fc03-238">Public browsing - 5 minutes</span></span>
    - <span data-ttu-id="3fc03-239">允许的值</span><span class="sxs-lookup"><span data-stu-id="3fc03-239">Allowed values</span></span>
      - <span data-ttu-id="3fc03-240">0 - 关闭计时器</span><span class="sxs-lookup"><span data-stu-id="3fc03-240">0 - turns off the timer</span></span>
      - <span data-ttu-id="3fc03-241">1-1440 分钟，用于在空闲计时器上重置</span><span class="sxs-lookup"><span data-stu-id="3fc03-241">1-1440 minutes for reset on idle timer</span></span>


    ```
    msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --kiosk-idle-timeout-minutes=1
   ```

   ```
   msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --kiosk-idle-timeout-minutes=1
   ```

## <a name="support-policies-for-kiosk-mode"></a><span data-ttu-id="3fc03-242">展台模式的支持策略</span><span class="sxs-lookup"><span data-stu-id="3fc03-242">Support policies for kiosk mode</span></span>

<span data-ttu-id="3fc03-243">使用下表中列出的任何 Microsoft Edge 策略增强所配置的 Microsoft Edge 展台模式类型的展台体验。</span><span class="sxs-lookup"><span data-stu-id="3fc03-243">Use any of the Microsoft Edge policies listed in the following table to enhance the kiosk experience for the Microsoft Edge kiosk mode type you configure.</span></span> <span data-ttu-id="3fc03-244">若要了解有关这些策略的信息，请参阅 [Microsoft Edge – 浏览器策略参考](https://docs.microsoft.com/deployedge/microsoft-edge-policies)。</span><span class="sxs-lookup"><span data-stu-id="3fc03-244">To learn more about these policies, see [Microsoft Edge – Browser policy reference](https://docs.microsoft.com/deployedge/microsoft-edge-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="3fc03-245">策略配置不限于下表中列出的策略，但应测试其他策略以确保展台模式功能不会受到负面影响。</span><span class="sxs-lookup"><span data-stu-id="3fc03-245">Policy configuration isn't limited to the policies listed in the following table, however additional policies should be tested to ensure that kiosk mode functionality isn't negatively affected.</span></span>

|<span data-ttu-id="3fc03-246">组策略</span><span class="sxs-lookup"><span data-stu-id="3fc03-246">Group policy</span></span>|<span data-ttu-id="3fc03-247">数字\交互式标志</span><span class="sxs-lookup"><span data-stu-id="3fc03-247">Digital\Interactive signage</span></span>|<span data-ttu-id="3fc03-248">公共浏览单应用</span><span class="sxs-lookup"><span data-stu-id="3fc03-248">Public browsing single-app</span></span>|
|--|--|--|
|[<span data-ttu-id="3fc03-249">打印</span><span class="sxs-lookup"><span data-stu-id="3fc03-249">Printing</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printing-policies) | <span data-ttu-id="3fc03-250">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-250">Y</span></span>|<span data-ttu-id="3fc03-251">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-251">Y</span></span> |
|[<span data-ttu-id="3fc03-252">HomePageLocation</span><span class="sxs-lookup"><span data-stu-id="3fc03-252">HomePageLocation</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#homepagelocation) |<span data-ttu-id="3fc03-253">N</span><span class="sxs-lookup"><span data-stu-id="3fc03-253">N</span></span> | <span data-ttu-id="3fc03-254">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-254">Y</span></span>|
|[<span data-ttu-id="3fc03-255">ShowHomeButton</span><span class="sxs-lookup"><span data-stu-id="3fc03-255">ShowHomeButton</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#showhomebutton) |<span data-ttu-id="3fc03-256">N</span><span class="sxs-lookup"><span data-stu-id="3fc03-256">N</span></span> | <span data-ttu-id="3fc03-257">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-257">Y</span></span>|
|[<span data-ttu-id="3fc03-258">NewTabPageLocation</span><span class="sxs-lookup"><span data-stu-id="3fc03-258">NewTabPageLocation</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagelocation) |<span data-ttu-id="3fc03-259">N</span><span class="sxs-lookup"><span data-stu-id="3fc03-259">N</span></span> |<span data-ttu-id="3fc03-260">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-260">Y</span></span> |
|[<span data-ttu-id="3fc03-261">FavoritesBarEnabled</span><span class="sxs-lookup"><span data-stu-id="3fc03-261">FavoritesBarEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#favoritesbarenabled) |<span data-ttu-id="3fc03-262">N</span><span class="sxs-lookup"><span data-stu-id="3fc03-262">N</span></span> |<span data-ttu-id="3fc03-263">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-263">Y</span></span> |
|[<span data-ttu-id="3fc03-264">URLAllowlist</span><span class="sxs-lookup"><span data-stu-id="3fc03-264">URLAllowlist</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlallowlist) |<span data-ttu-id="3fc03-265">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-265">Y</span></span> |<span data-ttu-id="3fc03-266">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-266">Y</span></span> |
|[<span data-ttu-id="3fc03-267">URLBlocklist</span><span class="sxs-lookup"><span data-stu-id="3fc03-267">URLBlocklist</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlblocklist) |<span data-ttu-id="3fc03-268">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-268">Y</span></span> | <span data-ttu-id="3fc03-269">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-269">Y</span></span>|
|[<span data-ttu-id="3fc03-270">ManagedSearchEngines</span><span class="sxs-lookup"><span data-stu-id="3fc03-270">ManagedSearchEngines</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#managedsearchengines) |<span data-ttu-id="3fc03-271">N</span><span class="sxs-lookup"><span data-stu-id="3fc03-271">N</span></span> | <span data-ttu-id="3fc03-272">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-272">Y</span></span>|
|[<span data-ttu-id="3fc03-273">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="3fc03-273">UserFeedbackAllowed</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#userfeedbackallowed) |<span data-ttu-id="3fc03-274">N</span><span class="sxs-lookup"><span data-stu-id="3fc03-274">N</span></span> | <span data-ttu-id="3fc03-275">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-275">Y</span></span>|
|[<span data-ttu-id="3fc03-276">VerticalTabsAllowed</span><span class="sxs-lookup"><span data-stu-id="3fc03-276">VerticalTabsAllowed</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#verticaltabsallowed) | <span data-ttu-id="3fc03-277">N</span><span class="sxs-lookup"><span data-stu-id="3fc03-277">N</span></span>|<span data-ttu-id="3fc03-278">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-278">Y</span></span> |
|[<span data-ttu-id="3fc03-279">SmartScreen 设置</span><span class="sxs-lookup"><span data-stu-id="3fc03-279">SmartScreen settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#smartscreen-settings-policies) |<span data-ttu-id="3fc03-280">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-280">Y</span></span> |<span data-ttu-id="3fc03-281">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-281">Y</span></span> |
|[<span data-ttu-id="3fc03-282">EdgeCollectionsEnabled</span><span class="sxs-lookup"><span data-stu-id="3fc03-282">EdgeCollectionsEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#edgecollectionsenabled)|<span data-ttu-id="3fc03-283">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-283">Y</span></span>|<span data-ttu-id="3fc03-284">Y</span><span class="sxs-lookup"><span data-stu-id="3fc03-284">Y</span></span>|

## <a name="microsoft-edge-with-assigned-access"></a><span data-ttu-id="3fc03-285">Microsoft Edge 与指派访问</span><span class="sxs-lookup"><span data-stu-id="3fc03-285">Microsoft Edge with assigned access</span></span>

### <a name="single-app-kiosk"></a><span data-ttu-id="3fc03-286">单应用展台</span><span class="sxs-lookup"><span data-stu-id="3fc03-286">Single app kiosk</span></span>

<span data-ttu-id="3fc03-287">Microsoft Edge 当前支持具有以下锁定体验的单应用分配访问权限的相同 Microsoft Edge 旧版展台模式类型的子集：数字/交互式标志和公共浏览。</span><span class="sxs-lookup"><span data-stu-id="3fc03-287">Microsoft Edge currently supports a subset of the same Microsoft Edge Legacy kiosk mode types for single-app assigned access with the following lockdown experiences: Digital/Interactive signage, and Public-browsing.</span></span>  

<span data-ttu-id="3fc03-288">目前，在最新的  [Windows 10 Insider Preview 内部版本](https://insider.windows.com/)的版本 20215 或更高版本以及  [Microsoft Edge Beta 渠道](https://www.microsoftedgeinsider.com/download)的版本 89 或更高版本上，可以测试具有已分配访问权限的单应用的 Microsoft Edge 展台模式。</span><span class="sxs-lookup"><span data-stu-id="3fc03-288">Microsoft Edge kiosk mode with assigned access single app is currently available for testing with the latest [Windows 10 Insider Preview Build](https://insider.windows.com/), version 20215 or higher, and with the [Microsoft Edge Beta Channel](https://www.microsoftedgeinsider.com/download), version 89 or higher.</span></span>

**<span data-ttu-id="3fc03-289">如何获得 Windows 预览体验成员预览版？</span><span class="sxs-lookup"><span data-stu-id="3fc03-289">How do I get the Windows Insiders preview?</span></span>**

<span data-ttu-id="3fc03-290">若要在电脑上安装 Windows 10 Insider Preview 内部版本，请按照 [开始使用 Windows 10 Insider Preview 版本](https://docs.microsoft.com/windows-insider/get-started)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="3fc03-290">To install a Windows 10 Insider Preview Build on a PC, follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>

### <a name="multi-app-kiosk"></a><span data-ttu-id="3fc03-291">多应用展台。</span><span class="sxs-lookup"><span data-stu-id="3fc03-291">Multi-app kiosk</span></span>

<span data-ttu-id="3fc03-292">可用 Windows 10 上的[多应用指派访问](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)（相当于旧版 Microsoft Edge 的“普通浏览”展台模式类型）运行 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="3fc03-292">Microsoft Edge can be run with [multi-app assigned access](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) on Windows 10, which is the equivalent of Microsoft Edge Legacy "Normal browsing" kiosk mode type.</span></span> <span data-ttu-id="3fc03-293">若要使用多应用分配的访问权限配置 Microsoft Edge，请按照有关[如何设置多应用展台](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="3fc03-293">To configure Microsoft Edge with multi-app assigned access, follow the instructions on how to [Set up a multi-app kiosk](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps).</span></span> <span data-ttu-id="3fc03-294">（Microsoft Edge Stable 渠道的 AUMID 为 **MSEdge**）。</span><span class="sxs-lookup"><span data-stu-id="3fc03-294">(The AUMID for the Microsoft Edge Stable channel is **MSEdge**).</span></span>

<span data-ttu-id="3fc03-295">将 Microsoft Edge 与多应用分配的访问权限一同使用时，可以将 Microsoft Edge 展台配置为使用 [Microsoft Edge 浏览器策略](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies)配置浏览体验，以满足你的独特要求。</span><span class="sxs-lookup"><span data-stu-id="3fc03-295">When using Microsoft Edge with multi-app assigned access, you can configure Microsoft Edge kiosk to use the[Microsoft Edge browser policies](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies) to configure the browsing experience to meet your unique requirements.</span></span>

### <a name="configure-using-windows-settings"></a><span data-ttu-id="3fc03-296">使用 Windows 设置进行配置</span><span class="sxs-lookup"><span data-stu-id="3fc03-296">Configure using Windows Settings</span></span>

<span data-ttu-id="3fc03-297">Windows 设置是设置一个或两个单应用展台设备的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="3fc03-297">Windows Settings is the simplest way to set up one or two single-app kiosk devices.</span></span> <span data-ttu-id="3fc03-298">使用以下步骤设置单应用展台计算机。</span><span class="sxs-lookup"><span data-stu-id="3fc03-298">Use the following steps to set up a single-app kiosk computer.</span></span>

1. <span data-ttu-id="3fc03-299">安装最新的 Windows 10 Insider Preview 版本 20215 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="3fc03-299">Install the latest Windows 10 Insider Preview, version 20215 or higher.</span></span> <span data-ttu-id="3fc03-300">按照[开始使用 Windows 10 Insider Preview 版本](https://docs.microsoft.com/windows-insider/get-started)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="3fc03-300">Follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>
2. <span data-ttu-id="3fc03-301">若要测试最新功能，可以下载最新的 [Microsoft Edge Beta 渠道](https://www.microsoftedgeinsider.com/download)的 89 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="3fc03-301">To test the latest features, you can download the latest [Microsoft Edge Beta channel](https://www.microsoftedgeinsider.com/download), version 89 or higher.</span></span>
3. <span data-ttu-id="3fc03-302">在展台计算机上，打开“Windows 设置”，然后在搜索字段中键入“展台”。</span><span class="sxs-lookup"><span data-stu-id="3fc03-302">On the kiosk computer, open Windows Settings, and type "kiosk" in the search field.</span></span> <span data-ttu-id="3fc03-303">选择“ **设置展台（分配的访问权限）**”（如下一个屏幕截图所示），以打开用于创建展台的对话框。</span><span class="sxs-lookup"><span data-stu-id="3fc03-303">Select  **Set up a kiosk (assigned access)**, shown in the next screenshot to open the dialog for creating the kiosk.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="设置具有分配的访问权限的展台":::

4. <span data-ttu-id="3fc03-305">在“**设置展台** ”页面上，单击“ **入门**”。</span><span class="sxs-lookup"><span data-stu-id="3fc03-305">On the **Set up a kiosk** page, click **Get started**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="展台页面 - 入门":::

5. <span data-ttu-id="3fc03-307">键入名称以创建新的展台帐户，或从填充的下拉列表中选择现有帐户，然后单击“ **下一步**”。</span><span class="sxs-lookup"><span data-stu-id="3fc03-307">Type a name to create a new kiosk account or choose an existing account from the populated dropdown list and then click **Next**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="展台模式 - 创建帐户":::

6. <span data-ttu-id="3fc03-309">在“**选择展台应用** ”页面上，选择“**Microsoft Edge**”，然后单击“ **下一步**”。</span><span class="sxs-lookup"><span data-stu-id="3fc03-309">On the **Choose a kiosk app** page, select **Microsoft Edge** and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3fc03-310">这仅适用于 Microsoft Edge Dev、Beta 和 Stable 渠道。</span><span class="sxs-lookup"><span data-stu-id="3fc03-310">This only applies to Microsoft Edge Dev, Beta, and Stable channels.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="展台模式 - 选择应用":::

7. <span data-ttu-id="3fc03-312">选择以下选项之一，了解 Microsoft Edge 在展台模式下运行时的显示方式：</span><span class="sxs-lookup"><span data-stu-id="3fc03-312">Pick one of the following options for how Microsoft Edge displays when running in kiosk mode:</span></span>

   - <span data-ttu-id="3fc03-313">数字/交互式标牌 - 运行 Microsoft Edge 时以全屏模式显示特定网站。</span><span class="sxs-lookup"><span data-stu-id="3fc03-313">Digital/Interactive signage - Displays a specific site in full-screen mode, running Microsoft Edge.</span></span>
   - <span data-ttu-id="3fc03-314">公共浏览器 - 运行 Microsoft Edge 的受限多选项卡版本。</span><span class="sxs-lookup"><span data-stu-id="3fc03-314">Public browser - Runs a limited multi-tab version of Microsoft Edge.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="展台模式显示 - 全屏数字签名":::

8. <span data-ttu-id="3fc03-316">选择“ **下一步**”。</span><span class="sxs-lookup"><span data-stu-id="3fc03-316">Select **Next**.</span></span>
9. <span data-ttu-id="3fc03-317">键入要在展台启动时加载的 URL。</span><span class="sxs-lookup"><span data-stu-id="3fc03-317">Type the URL to load when the kiosk launches.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="展台模式 - 输入 URL":::

10. <span data-ttu-id="3fc03-319">接受“5 分钟”的空闲时间默认值或提供你自己的值。</span><span class="sxs-lookup"><span data-stu-id="3fc03-319">Accept the default value of 5 minutes for the idle time or provide a value of your own.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="展台模式 - 输入空闲时间":::

11. <span data-ttu-id="3fc03-321">单击“ **下一步**”。</span><span class="sxs-lookup"><span data-stu-id="3fc03-321">Click **Next**.</span></span>
12. <span data-ttu-id="3fc03-322">关闭“ **设置** ”窗口，保存并应用你的选择。</span><span class="sxs-lookup"><span data-stu-id="3fc03-322">Close the **Settings** window to save and apply your choices.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="展台模式 - 完成设置":::

13. <span data-ttu-id="3fc03-324">从展台设备注销，然后使用本地展台帐户登录以验证配置。</span><span class="sxs-lookup"><span data-stu-id="3fc03-324">Sign out from the kiosk device and sign in with the local kiosk account to validate the configuration.</span></span>

## <a name="functional-limitations"></a><span data-ttu-id="3fc03-325">功能限制</span><span class="sxs-lookup"><span data-stu-id="3fc03-325">Functional limitations</span></span>

<span data-ttu-id="3fc03-326">随着展台模式此预览版的发布，我们将继续改进产品和添加新功能。</span><span class="sxs-lookup"><span data-stu-id="3fc03-326">With the release of this preview version of kiosk mode we're continuing work on improving the product and adding new features.</span></span>

<span data-ttu-id="3fc03-327">建议你关闭：</span><span class="sxs-lookup"><span data-stu-id="3fc03-327">We recommend that you turn off:</span></span>

- [<span data-ttu-id="3fc03-328">InPrivateModeAvailability</span><span class="sxs-lookup"><span data-stu-id="3fc03-328">InPrivateModeAvailability</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)
- [<span data-ttu-id="3fc03-329">IsolateOrigins</span><span class="sxs-lookup"><span data-stu-id="3fc03-329">IsolateOrigins</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#isolateorigins)
- [<span data-ttu-id="3fc03-330">ManagedFavorites</span><span class="sxs-lookup"><span data-stu-id="3fc03-330">ManagedFavorites</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#managedfavorites)
- [<span data-ttu-id="3fc03-331">EdgeShoppingAssistantEnabled</span><span class="sxs-lookup"><span data-stu-id="3fc03-331">EdgeShoppingAssistantEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#edgeshoppingassistantenabled)
- [<span data-ttu-id="3fc03-332">EdgeCollectionsEnabled</span><span class="sxs-lookup"><span data-stu-id="3fc03-332">EdgeCollectionsEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#edgecollectionsenabled)
- [<span data-ttu-id="3fc03-333">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="3fc03-333">UserFeedbackAllowed</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#userfeedbackallowed)
- [<span data-ttu-id="3fc03-334">DefaultPopupsSetting</span><span class="sxs-lookup"><span data-stu-id="3fc03-334">DefaultPopupsSetting</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#defaultpopupssetting)
- [<span data-ttu-id="3fc03-335">StartupBoostEnabled</span><span class="sxs-lookup"><span data-stu-id="3fc03-335">StartupBoostEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startupboostenabled)
- [<span data-ttu-id="3fc03-336">InternetExplorerIntegrationLevel</span><span class="sxs-lookup"><span data-stu-id="3fc03-336">InternetExplorerIntegrationLevel</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationlevel)
- [<span data-ttu-id="3fc03-337">Extensions</span><span class="sxs-lookup"><span data-stu-id="3fc03-337">Extensions</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensions-policies)
- [<span data-ttu-id="3fc03-338">BackgroundModeEnabled</span><span class="sxs-lookup"><span data-stu-id="3fc03-338">BackgroundModeEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)

## <a name="roadmap"></a><span data-ttu-id="3fc03-339">路线图</span><span class="sxs-lookup"><span data-stu-id="3fc03-339">Roadmap</span></span>

### <a name="in-early-2021"></a><span data-ttu-id="3fc03-340">2021 年初</span><span class="sxs-lookup"><span data-stu-id="3fc03-340">In early 2021</span></span>

<span data-ttu-id="3fc03-341">我们将添加以下支持和功能：</span><span class="sxs-lookup"><span data-stu-id="3fc03-341">We'll add the following support and features:</span></span>

- <span data-ttu-id="3fc03-342">Microsoft Edge 展台模式在 Windows 10 1909 及更高版本上具有分配的访问权限单应用通用。</span><span class="sxs-lookup"><span data-stu-id="3fc03-342">General availability of Microsoft Edge kiosk mode with assigned access single app on Windows 10 1909 and higher.</span></span>
- <span data-ttu-id="3fc03-343">用于与 Microsoft Edge 旧版进行奇偶校验的其他功能。</span><span class="sxs-lookup"><span data-stu-id="3fc03-343">Additional features for parity with Microsoft Edge Legacy.</span></span>
- <span data-ttu-id="3fc03-344">与 Intune 集成，以使用展台模式配置文件 UX 配置设备。</span><span class="sxs-lookup"><span data-stu-id="3fc03-344">Integration with Intune to configure devices using kiosk mode profile UX.</span></span>
- <span data-ttu-id="3fc03-345">限制从浏览器启动其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="3fc03-345">Restrict the launch of other applications from the browser.</span></span>
- <span data-ttu-id="3fc03-346">UI 打印设置锁定。</span><span class="sxs-lookup"><span data-stu-id="3fc03-346">UI print settings lockdown.</span></span>

## <a name="see-also"></a><span data-ttu-id="3fc03-347">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3fc03-347">See also</span></span>

- [<span data-ttu-id="3fc03-348">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="3fc03-348">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="3fc03-349">规划 Microsoft Edge 部署</span><span class="sxs-lookup"><span data-stu-id="3fc03-349">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)
- [<span data-ttu-id="3fc03-350">在 Windows 桌面版中配置展台和数字签名</span><span class="sxs-lookup"><span data-stu-id="3fc03-350">Configure kiosks and digital signs on Windows desktop editions</span></span>](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [<span data-ttu-id="3fc03-351">规划展台模式转换</span><span class="sxs-lookup"><span data-stu-id="3fc03-351">Plan your kiosk mode transition</span></span>](microsoft-edge-kiosk-mode-transition-plan.md)
