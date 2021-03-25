---
title: 配置 Microsoft Edge 展台模式
ms.author: aguta
author: aguta
manager: srugh
ms.date: 03/16/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解展台模式功能以及如何配置 Microsoft Edge 展台模式的选项。
ms.openlocfilehash: 9d76bfcaebeaf56e627a401cc4f0375bce9d17a3
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "11448126"
---
# <a name="configure-microsoft-edge-kiosk-mode"></a><span data-ttu-id="e7d8b-103">配置 Microsoft Edge 展台模式</span><span class="sxs-lookup"><span data-stu-id="e7d8b-103">Configure Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="e7d8b-104">本文介绍如何配置可以试用的 Microsoft Edge 展台模式选项。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-104">This article describes how to configure Microsoft Edge kiosk mode options that you can pilot.</span></span> <span data-ttu-id="e7d8b-105">还有一个在我们目标之中的功能路线图。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-105">There's also a roadmap of features we're targeting.</span></span>

> [!NOTE]
> <span data-ttu-id="e7d8b-106">本文适用于 Microsoft Edge 版本 87 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-106">This article applies to Microsoft Edge version 87 or later.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7d8b-107">通过[使用展台模式功能](#use-kiosk-mode-features)中提供的命令行参数调用 Windows 10 Microsoft Edge 展台模式功能。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-107">Invoke Microsoft Edge kiosk mode features on Windows 10 using the command line arguments provided in [Use kiosk mode features](#use-kiosk-mode-features).</span></span>

## <a name="overview"></a><span data-ttu-id="e7d8b-108">概述</span><span class="sxs-lookup"><span data-stu-id="e7d8b-108">Overview</span></span>

<span data-ttu-id="e7d8b-109">Microsoft Edge 展台模式提供两种浏览器锁定体验，因此组织可以创建、管理并为其客户提供最佳体验。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-109">Microsoft Edge kiosk mode offers two lockdown experiences of the browser so organizations can create, manage, and provide the best experience for their customers.</span></span> <span data-ttu-id="e7d8b-110">提供以下锁定体验：</span><span class="sxs-lookup"><span data-stu-id="e7d8b-110">The following lockdown experiences are available:</span></span>  

- <span data-ttu-id="e7d8b-111">**数字/交互式标志** 体验 - 以全屏模式显示特定网站。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-111">**Digital/Interactive Signage** experience - Displays a specific site in full-screen mode.</span></span>
- <span data-ttu-id="e7d8b-112">**公共浏览** 体验 - 运行 Microsoft Edge 的有限多选项卡版本。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-112">**Public-Browsing** experience - Runs a limited multi-tab version of Microsoft Edge.</span></span>

<span data-ttu-id="e7d8b-113">这两种体验都在运行 Microsoft Edge InPrivate 会话，以保护用户数据。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-113">Both experiences are running a Microsoft Edge InPrivate session, which protects user data.</span></span>

## <a name="set-up-microsoft-edge-kiosk-mode"></a><span data-ttu-id="e7d8b-114">设置 Microsoft Edge 展台模式</span><span class="sxs-lookup"><span data-stu-id="e7d8b-114">Set up Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="e7d8b-115">可以使用 Microsoft Edge Stable 渠道版本 87 测试一组初始展台模式功能。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-115">An initial set of kiosk mode features is available to test with Microsoft Edge Stable Channel, version 87.</span></span> <span data-ttu-id="e7d8b-116">你可以从 [Microsoft Edge (Official Stable 渠道)](https://www.microsoft.com/edge)下载。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-116">You can download the latest version from [Microsoft Edge (Official Stable Channel)](https://www.microsoft.com/edge).</span></span>

### <a name="kiosk-mode-supported-features"></a><span data-ttu-id="e7d8b-117">展台模式支持的功能</span><span class="sxs-lookup"><span data-stu-id="e7d8b-117">Kiosk mode supported features</span></span>

<span data-ttu-id="e7d8b-118">下表列出了 Microsoft Edge 和 Microsoft Edge 旧版中的展台模式支持的功能。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-118">The following table lists the features supported by kiosk mode in Microsoft Edge and Microsoft Edge Legacy.</span></span> <span data-ttu-id="e7d8b-119">比较这两个版本的 Microsoft Edge 支持的功能有何不同，将此表用作指南以转换为 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-119">Use this table as a guide to transitioning to Microsoft Edge by comparing how these features are supported in both versions of Microsoft Edge.</span></span>

|<span data-ttu-id="e7d8b-120">功能</span><span class="sxs-lookup"><span data-stu-id="e7d8b-120">Feature</span></span>|<span data-ttu-id="e7d8b-121">数字\交互式标志</span><span class="sxs-lookup"><span data-stu-id="e7d8b-121">Digital\Interactive Signage</span></span>|<span data-ttu-id="e7d8b-122">公共浏览</span><span class="sxs-lookup"><span data-stu-id="e7d8b-122">Public browsing</span></span>|<span data-ttu-id="e7d8b-123">适用于 Microsoft Edge 版本（及更高版本）</span><span class="sxs-lookup"><span data-stu-id="e7d8b-123">Available with Microsoft Edge version (and higher)</span></span>|<span data-ttu-id="e7d8b-124">适用于 Microsoft Edge 旧版</span><span class="sxs-lookup"><span data-stu-id="e7d8b-124">Available with Microsoft Edge Legacy</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="e7d8b-125">InPrivate 导航</span><span class="sxs-lookup"><span data-stu-id="e7d8b-125">InPrivate Navigation</span></span>|<span data-ttu-id="e7d8b-126">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-126">Y</span></span>|<span data-ttu-id="e7d8b-127">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-127">Y</span></span>|<span data-ttu-id="e7d8b-128">89</span><span class="sxs-lookup"><span data-stu-id="e7d8b-128">89</span></span>|<span data-ttu-id="e7d8b-129">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-129">Y</span></span>|
|<span data-ttu-id="e7d8b-130">在处于非活动状态时重置</span><span class="sxs-lookup"><span data-stu-id="e7d8b-130">Reset on inactivity</span></span>|<span data-ttu-id="e7d8b-131">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-131">Y</span></span>|<span data-ttu-id="e7d8b-132">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-132">Y</span></span>|<span data-ttu-id="e7d8b-133">89</span><span class="sxs-lookup"><span data-stu-id="e7d8b-133">89</span></span>|<span data-ttu-id="e7d8b-134">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-134">Y</span></span>|
|<span data-ttu-id="e7d8b-135">[只读地址栏](./microsoft-edge-policies.md#kioskaddressbareditingenabled) (策略)</span><span class="sxs-lookup"><span data-stu-id="e7d8b-135">[Read only address bar](./microsoft-edge-policies.md#kioskaddressbareditingenabled) (policy)</span></span> |<span data-ttu-id="e7d8b-136">N</span><span class="sxs-lookup"><span data-stu-id="e7d8b-136">N</span></span>|<span data-ttu-id="e7d8b-137">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-137">Y</span></span> |<span data-ttu-id="e7d8b-138">89</span><span class="sxs-lookup"><span data-stu-id="e7d8b-138">89</span></span>|<span data-ttu-id="e7d8b-139">N</span><span class="sxs-lookup"><span data-stu-id="e7d8b-139">N</span></span>|
|<span data-ttu-id="e7d8b-140">[退出时删除下载](./microsoft-edge-policies.md#kioskdeletedownloadsonexit)（策略）</span><span class="sxs-lookup"><span data-stu-id="e7d8b-140">[Delete downloads on exit](./microsoft-edge-policies.md#kioskdeletedownloadsonexit) (policy)</span></span>  | <span data-ttu-id="e7d8b-141">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-141">Y</span></span>|<span data-ttu-id="e7d8b-142">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-142">Y</span></span> |<span data-ttu-id="e7d8b-143">89</span><span class="sxs-lookup"><span data-stu-id="e7d8b-143">89</span></span>|<span data-ttu-id="e7d8b-144">N</span><span class="sxs-lookup"><span data-stu-id="e7d8b-144">N</span></span>|
|<span data-ttu-id="e7d8b-145">已阻止 F11（进入/退出全屏）</span><span class="sxs-lookup"><span data-stu-id="e7d8b-145">F11 blocked (enter/exit full-screen)</span></span> | <span data-ttu-id="e7d8b-146">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-146">Y</span></span> | <span data-ttu-id="e7d8b-147">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-147">Y</span></span> | <span data-ttu-id="e7d8b-148">89</span><span class="sxs-lookup"><span data-stu-id="e7d8b-148">89</span></span> |<span data-ttu-id="e7d8b-149">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-149">Y</span></span>|
|<span data-ttu-id="e7d8b-150">已阻止F12（启动开发人员工具）</span><span class="sxs-lookup"><span data-stu-id="e7d8b-150">F12 blocked (launch Developer Tools)</span></span> | <span data-ttu-id="e7d8b-151">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-151">Y</span></span> | <span data-ttu-id="e7d8b-152">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-152">Y</span></span> | <span data-ttu-id="e7d8b-153">89</span><span class="sxs-lookup"><span data-stu-id="e7d8b-153">89</span></span> |<span data-ttu-id="e7d8b-154">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-154">Y</span></span>|
| <span data-ttu-id="e7d8b-155">多选项卡支持</span><span class="sxs-lookup"><span data-stu-id="e7d8b-155">Multi tab support</span></span> | <span data-ttu-id="e7d8b-156">N</span><span class="sxs-lookup"><span data-stu-id="e7d8b-156">N</span></span>| <span data-ttu-id="e7d8b-157">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-157">Y</span></span>| <span data-ttu-id="e7d8b-158">89</span><span class="sxs-lookup"><span data-stu-id="e7d8b-158">89</span></span>|<span data-ttu-id="e7d8b-159">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-159">Y</span></span>|
|<span data-ttu-id="e7d8b-160">[允许 URL 支持](./microsoft-edge-policies.md#urlallowlist)（策略）</span><span class="sxs-lookup"><span data-stu-id="e7d8b-160">[Allow URL support](./microsoft-edge-policies.md#urlallowlist) (policy)</span></span>|<span data-ttu-id="e7d8b-161">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-161">Y</span></span>|<span data-ttu-id="e7d8b-162">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-162">Y</span></span>|<span data-ttu-id="e7d8b-163">89</span><span class="sxs-lookup"><span data-stu-id="e7d8b-163">89</span></span>|<span data-ttu-id="e7d8b-164">N</span><span class="sxs-lookup"><span data-stu-id="e7d8b-164">N</span></span>|
|<span data-ttu-id="e7d8b-165">[阻止 URL 支持](./microsoft-edge-policies.md#urlblocklist)（策略）</span><span class="sxs-lookup"><span data-stu-id="e7d8b-165">[Block URL support](./microsoft-edge-policies.md#urlblocklist) (policy)</span></span>|<span data-ttu-id="e7d8b-166">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-166">Y</span></span>|<span data-ttu-id="e7d8b-167">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-167">Y</span></span>|<span data-ttu-id="e7d8b-168">89</span><span class="sxs-lookup"><span data-stu-id="e7d8b-168">89</span></span>|<span data-ttu-id="e7d8b-169">N</span><span class="sxs-lookup"><span data-stu-id="e7d8b-169">N</span></span>|
|<span data-ttu-id="e7d8b-170">[显示“主页”按钮](./microsoft-edge-policies.md#showhomebutton)（策略）</span><span class="sxs-lookup"><span data-stu-id="e7d8b-170">[Show home button](./microsoft-edge-policies.md#showhomebutton) (policy)</span></span>|<span data-ttu-id="e7d8b-171">N</span><span class="sxs-lookup"><span data-stu-id="e7d8b-171">N</span></span>|<span data-ttu-id="e7d8b-172">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-172">Y</span></span>|<span data-ttu-id="e7d8b-173">89</span><span class="sxs-lookup"><span data-stu-id="e7d8b-173">89</span></span>|<span data-ttu-id="e7d8b-174">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-174">Y</span></span>|
|<span data-ttu-id="e7d8b-175">[管理收藏夹](./microsoft-edge-policies.md#managedfavorites)（策略）</span><span class="sxs-lookup"><span data-stu-id="e7d8b-175">[Manage favorites](./microsoft-edge-policies.md#managedfavorites) (policy)</span></span>|<span data-ttu-id="e7d8b-176">N</span><span class="sxs-lookup"><span data-stu-id="e7d8b-176">N</span></span>|<span data-ttu-id="e7d8b-177">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-177">Y</span></span>|<span data-ttu-id="e7d8b-178">89</span><span class="sxs-lookup"><span data-stu-id="e7d8b-178">89</span></span>|<span data-ttu-id="e7d8b-179">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-179">Y</span></span>|
|<span data-ttu-id="e7d8b-180">[启用打印机](./microsoft-edge-policies.md#printingenabled)（策略）</span><span class="sxs-lookup"><span data-stu-id="e7d8b-180">[Enable printer](./microsoft-edge-policies.md#printingenabled) (policy)</span></span>|<span data-ttu-id="e7d8b-181">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-181">Y</span></span>|<span data-ttu-id="e7d8b-182">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-182">Y</span></span>|<span data-ttu-id="e7d8b-183">89</span><span class="sxs-lookup"><span data-stu-id="e7d8b-183">89</span></span>|<span data-ttu-id="e7d8b-184">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-184">Y</span></span>|
|<span data-ttu-id="e7d8b-185">[配置新标签页页面 URL](./microsoft-edge-policies.md#newtabpagelocation)（策略）</span><span class="sxs-lookup"><span data-stu-id="e7d8b-185">[Configure the new tab page URL](./microsoft-edge-policies.md#newtabpagelocation) (policy)</span></span>|<span data-ttu-id="e7d8b-186">N</span><span class="sxs-lookup"><span data-stu-id="e7d8b-186">N</span></span>|<span data-ttu-id="e7d8b-187">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-187">Y</span></span>||<span data-ttu-id="e7d8b-188">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-188">Y</span></span>|
|<span data-ttu-id="e7d8b-189">结束会话按钮 \*</span><span class="sxs-lookup"><span data-stu-id="e7d8b-189">End session button \*</span></span> | <span data-ttu-id="e7d8b-190">N</span><span class="sxs-lookup"><span data-stu-id="e7d8b-190">N</span></span>| <span data-ttu-id="e7d8b-191">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-191">Y</span></span>| <span data-ttu-id="e7d8b-192">89</span><span class="sxs-lookup"><span data-stu-id="e7d8b-192">89</span></span>|<span data-ttu-id="e7d8b-193">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-193">Y</span></span>|
|<span data-ttu-id="e7d8b-194">所有内部 Microsoft Edge URL 已将被阻止，除了*edge://downloads*和*edge://print*</span><span class="sxs-lookup"><span data-stu-id="e7d8b-194">All internal Microsoft Edge URLs are blocked, except for *edge://downloads* and *edge://print*</span></span> |<span data-ttu-id="e7d8b-195">N</span><span class="sxs-lookup"><span data-stu-id="e7d8b-195">N</span></span>|<span data-ttu-id="e7d8b-196">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-196">Y</span></span>|<span data-ttu-id="e7d8b-197">89</span><span class="sxs-lookup"><span data-stu-id="e7d8b-197">89</span></span>|<span data-ttu-id="e7d8b-198">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-198">Y</span></span>|
| <span data-ttu-id="e7d8b-199">Ctrl+N 阻止 (打开新窗口) \*</span><span class="sxs-lookup"><span data-stu-id="e7d8b-199">CTRL+N blocked (open a new window) \*</span></span> | <span data-ttu-id="e7d8b-200">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-200">Y</span></span> | <span data-ttu-id="e7d8b-201">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-201">Y</span></span> | <span data-ttu-id="e7d8b-202">89</span><span class="sxs-lookup"><span data-stu-id="e7d8b-202">89</span></span> |<span data-ttu-id="e7d8b-203">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-203">Y</span></span>|
| <span data-ttu-id="e7d8b-204">已阻止 Ctrl+T（打开新选项卡）</span><span class="sxs-lookup"><span data-stu-id="e7d8b-204">CTRL+T blocked (open new tab)</span></span> |<span data-ttu-id="e7d8b-205">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-205">Y</span></span> | <span data-ttu-id="e7d8b-206">N</span><span class="sxs-lookup"><span data-stu-id="e7d8b-206">N</span></span> | <span data-ttu-id="e7d8b-207">89</span><span class="sxs-lookup"><span data-stu-id="e7d8b-207">89</span></span> |<span data-ttu-id="e7d8b-208">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-208">Y</span></span>|
|<span data-ttu-id="e7d8b-209">设置和更多 (...) 将仅显示所需的选项</span><span class="sxs-lookup"><span data-stu-id="e7d8b-209">Settings and more (...) will display only the required options</span></span>  |<span data-ttu-id="e7d8b-210">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-210">Y</span></span> |<span data-ttu-id="e7d8b-211">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-211">Y</span></span> |<span data-ttu-id="e7d8b-212">89</span><span class="sxs-lookup"><span data-stu-id="e7d8b-212">89</span></span> |<span data-ttu-id="e7d8b-213">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-213">Y</span></span>|
|<span data-ttu-id="e7d8b-214">限制从浏览器启动其他应用程序</span><span class="sxs-lookup"><span data-stu-id="e7d8b-214">Restrict the launch of other applications from the browser</span></span>|<span data-ttu-id="e7d8b-215">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-215">Y</span></span>|<span data-ttu-id="e7d8b-216">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-216">Y</span></span>|<span data-ttu-id="e7d8b-217">90/91</span><span class="sxs-lookup"><span data-stu-id="e7d8b-217">90/91</span></span>|<span data-ttu-id="e7d8b-218">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-218">Y</span></span>|
|<span data-ttu-id="e7d8b-219">UI 打印设置锁定</span><span class="sxs-lookup"><span data-stu-id="e7d8b-219">UI print settings lockdown</span></span>|<span data-ttu-id="e7d8b-220">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-220">Y</span></span>|<span data-ttu-id="e7d8b-221">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-221">Y</span></span>|<span data-ttu-id="e7d8b-222">90/91</span><span class="sxs-lookup"><span data-stu-id="e7d8b-222">90/91</span></span>|<span data-ttu-id="e7d8b-223">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-223">Y</span></span>|
|<span data-ttu-id="e7d8b-224">[将新标签页页面设置为主页](./microsoft-edge-policies.md#homepageisnewtabpage)（策略）</span><span class="sxs-lookup"><span data-stu-id="e7d8b-224">[Set the new tab page as the home page](./microsoft-edge-policies.md#homepageisnewtabpage) (policy)</span></span>|-|-|<span data-ttu-id="e7d8b-225">TBD</span><span class="sxs-lookup"><span data-stu-id="e7d8b-225">TBD</span></span>|<span data-ttu-id="e7d8b-226">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-226">Y</span></span>|

> [!NOTE]
> <span data-ttu-id="e7d8b-227">后跟“\*”的功能仅在已分配的访问单一应用场景中启用。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-227">Features followed by "\*" are only enabled in an assigned access single app scenario.</span></span>

## <a name="use-kiosk-mode-features"></a><span data-ttu-id="e7d8b-228">使用展台模式功能</span><span class="sxs-lookup"><span data-stu-id="e7d8b-228">Use kiosk mode features</span></span>

<span data-ttu-id="e7d8b-229">对于数字/交互式标牌和公共浏览，可通过以下 Windows 10 命令行选项调用 Microsoft Edge 展台模式功能。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-229">Microsoft Edge kiosk mode features can be invoked with the following Windows 10 command line options for Digital/Interactive signage and Public browsing.</span></span>

### <a name="kiosk-mode-digitalinteractive-signage"></a><span data-ttu-id="e7d8b-230">展台模式数字/交互式标牌</span><span class="sxs-lookup"><span data-stu-id="e7d8b-230">Kiosk mode Digital/Interactive signage</span></span>
 
```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen
```

### <a name="kiosk-mode-public-browsing"></a><span data-ttu-id="e7d8b-231">展台模式公共浏览</span><span class="sxs-lookup"><span data-stu-id="e7d8b-231">Kiosk mode Public browsing</span></span>

```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing
```

### <a name="additional-command-line-options"></a><span data-ttu-id="e7d8b-232">其他命令行选项</span><span class="sxs-lookup"><span data-stu-id="e7d8b-232">Additional command line options</span></span>

- <span data-ttu-id="e7d8b-233">**--no-first-run**：禁用首次 Microsoft Edge 运行体验。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-233">**--no-first-run**: Disable the first Microsoft Edge run experience.</span></span>

   ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --no-first-run
  ```

  ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --no-first-run
  ```

- <span data-ttu-id="e7d8b-234">**--kiosk-idle-timeout-minutes=**：更改从上次用户活动到 Microsoft Edge 展台模式重置用户会话前的时间（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-234">**--kiosk-idle-timeout-minutes=**: Change the time (in minutes) from the last user activity before Microsoft Edge kiosk mode resets the user's session.</span></span> <span data-ttu-id="e7d8b-235">将以下示例中的“值”替换为分钟数。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-235">Replace "value" in the next example with the number of minutes.</span></span>

   ```
   --kiosk-idle-timeout-minutes=value
   ``` 
   <span data-ttu-id="e7d8b-236">支持以下“值”：</span><span class="sxs-lookup"><span data-stu-id="e7d8b-236">The following "values" are supported:</span></span>

     - <span data-ttu-id="e7d8b-237">默认值（分钟）</span><span class="sxs-lookup"><span data-stu-id="e7d8b-237">Default values (in minutes)</span></span>
       - <span data-ttu-id="e7d8b-238">全屏 - 0（关闭）</span><span class="sxs-lookup"><span data-stu-id="e7d8b-238">Full screen - 0 (turned off)</span></span>
       - <span data-ttu-id="e7d8b-239">公共浏览 - 5 分钟</span><span class="sxs-lookup"><span data-stu-id="e7d8b-239">Public browsing - 5 minutes</span></span>
    - <span data-ttu-id="e7d8b-240">允许的值</span><span class="sxs-lookup"><span data-stu-id="e7d8b-240">Allowed values</span></span>
      - <span data-ttu-id="e7d8b-241">0 - 关闭计时器</span><span class="sxs-lookup"><span data-stu-id="e7d8b-241">0 - turns off the timer</span></span>
      - <span data-ttu-id="e7d8b-242">1-1440 分钟，用于在空闲计时器上重置</span><span class="sxs-lookup"><span data-stu-id="e7d8b-242">1-1440 minutes for reset on idle timer</span></span>


    ```
    msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --kiosk-idle-timeout-minutes=1
   ```

   ```
   msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --kiosk-idle-timeout-minutes=1
   ```

## <a name="support-policies-for-kiosk-mode"></a><span data-ttu-id="e7d8b-243">展台模式的支持策略</span><span class="sxs-lookup"><span data-stu-id="e7d8b-243">Support policies for kiosk mode</span></span>

<span data-ttu-id="e7d8b-244">使用下表中列出的任何 Microsoft Edge 策略增强所配置的 Microsoft Edge 展台模式类型的展台体验。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-244">Use any of the Microsoft Edge policies listed in the following table to enhance the kiosk experience for the Microsoft Edge kiosk mode type you configure.</span></span> <span data-ttu-id="e7d8b-245">若要了解有关这些策略的信息，请参阅 [Microsoft Edge – 浏览器策略参考](./microsoft-edge-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-245">To learn more about these policies, see [Microsoft Edge – Browser policy reference](./microsoft-edge-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e7d8b-246">策略配置不限于下表中列出的策略，但应测试其他策略以确保展台模式功能不会受到负面影响。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-246">Policy configuration isn't limited to the policies listed in the following table, however additional policies should be tested to ensure that kiosk mode functionality isn't negatively affected.</span></span>

|<span data-ttu-id="e7d8b-247">组策略</span><span class="sxs-lookup"><span data-stu-id="e7d8b-247">Group policy</span></span>|<span data-ttu-id="e7d8b-248">数字\交互式标志</span><span class="sxs-lookup"><span data-stu-id="e7d8b-248">Digital\Interactive signage</span></span>|<span data-ttu-id="e7d8b-249">公共浏览单应用</span><span class="sxs-lookup"><span data-stu-id="e7d8b-249">Public browsing single-app</span></span>|
|--|--|--|
|[<span data-ttu-id="e7d8b-250">打印</span><span class="sxs-lookup"><span data-stu-id="e7d8b-250">Printing</span></span>](./microsoft-edge-policies.md#printing-policies) | <span data-ttu-id="e7d8b-251">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-251">Y</span></span>|<span data-ttu-id="e7d8b-252">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-252">Y</span></span> |
|[<span data-ttu-id="e7d8b-253">HomePageLocation</span><span class="sxs-lookup"><span data-stu-id="e7d8b-253">HomePageLocation</span></span>](./microsoft-edge-policies.md#homepagelocation) |<span data-ttu-id="e7d8b-254">N</span><span class="sxs-lookup"><span data-stu-id="e7d8b-254">N</span></span> | <span data-ttu-id="e7d8b-255">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-255">Y</span></span>|
|[<span data-ttu-id="e7d8b-256">ShowHomeButton</span><span class="sxs-lookup"><span data-stu-id="e7d8b-256">ShowHomeButton</span></span>](./microsoft-edge-policies.md#showhomebutton) |<span data-ttu-id="e7d8b-257">N</span><span class="sxs-lookup"><span data-stu-id="e7d8b-257">N</span></span> | <span data-ttu-id="e7d8b-258">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-258">Y</span></span>|
|[<span data-ttu-id="e7d8b-259">NewTabPageLocation</span><span class="sxs-lookup"><span data-stu-id="e7d8b-259">NewTabPageLocation</span></span>](./microsoft-edge-policies.md#newtabpagelocation) |<span data-ttu-id="e7d8b-260">N</span><span class="sxs-lookup"><span data-stu-id="e7d8b-260">N</span></span> |<span data-ttu-id="e7d8b-261">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-261">Y</span></span> |
|[<span data-ttu-id="e7d8b-262">FavoritesBarEnabled</span><span class="sxs-lookup"><span data-stu-id="e7d8b-262">FavoritesBarEnabled</span></span>](./microsoft-edge-policies.md#favoritesbarenabled) |<span data-ttu-id="e7d8b-263">N</span><span class="sxs-lookup"><span data-stu-id="e7d8b-263">N</span></span> |<span data-ttu-id="e7d8b-264">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-264">Y</span></span> |
|[<span data-ttu-id="e7d8b-265">URLAllowlist</span><span class="sxs-lookup"><span data-stu-id="e7d8b-265">URLAllowlist</span></span>](./microsoft-edge-policies.md#urlallowlist) |<span data-ttu-id="e7d8b-266">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-266">Y</span></span> |<span data-ttu-id="e7d8b-267">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-267">Y</span></span> |
|[<span data-ttu-id="e7d8b-268">URLBlocklist</span><span class="sxs-lookup"><span data-stu-id="e7d8b-268">URLBlocklist</span></span>](./microsoft-edge-policies.md#urlblocklist) |<span data-ttu-id="e7d8b-269">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-269">Y</span></span> | <span data-ttu-id="e7d8b-270">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-270">Y</span></span>|
|[<span data-ttu-id="e7d8b-271">ManagedSearchEngines</span><span class="sxs-lookup"><span data-stu-id="e7d8b-271">ManagedSearchEngines</span></span>](./microsoft-edge-policies.md#managedsearchengines) |<span data-ttu-id="e7d8b-272">N</span><span class="sxs-lookup"><span data-stu-id="e7d8b-272">N</span></span> | <span data-ttu-id="e7d8b-273">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-273">Y</span></span>|
|[<span data-ttu-id="e7d8b-274">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="e7d8b-274">UserFeedbackAllowed</span></span>](./microsoft-edge-policies.md#userfeedbackallowed) |<span data-ttu-id="e7d8b-275">N</span><span class="sxs-lookup"><span data-stu-id="e7d8b-275">N</span></span> | <span data-ttu-id="e7d8b-276">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-276">Y</span></span>|
|[<span data-ttu-id="e7d8b-277">VerticalTabsAllowed</span><span class="sxs-lookup"><span data-stu-id="e7d8b-277">VerticalTabsAllowed</span></span>](./microsoft-edge-policies.md#verticaltabsallowed) | <span data-ttu-id="e7d8b-278">N</span><span class="sxs-lookup"><span data-stu-id="e7d8b-278">N</span></span>|<span data-ttu-id="e7d8b-279">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-279">Y</span></span> |
|[<span data-ttu-id="e7d8b-280">SmartScreen 设置</span><span class="sxs-lookup"><span data-stu-id="e7d8b-280">SmartScreen settings</span></span>](./microsoft-edge-policies.md#smartscreen-settings-policies) |<span data-ttu-id="e7d8b-281">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-281">Y</span></span> |<span data-ttu-id="e7d8b-282">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-282">Y</span></span> |
|[<span data-ttu-id="e7d8b-283">EdgeCollectionsEnabled</span><span class="sxs-lookup"><span data-stu-id="e7d8b-283">EdgeCollectionsEnabled</span></span>](./microsoft-edge-policies.md#edgecollectionsenabled)|<span data-ttu-id="e7d8b-284">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-284">Y</span></span>|<span data-ttu-id="e7d8b-285">Y</span><span class="sxs-lookup"><span data-stu-id="e7d8b-285">Y</span></span>|

## <a name="microsoft-edge-with-assigned-access"></a><span data-ttu-id="e7d8b-286">Microsoft Edge 与指派访问</span><span class="sxs-lookup"><span data-stu-id="e7d8b-286">Microsoft Edge with assigned access</span></span>

### <a name="single-app-kiosk"></a><span data-ttu-id="e7d8b-287">单应用展台</span><span class="sxs-lookup"><span data-stu-id="e7d8b-287">Single app kiosk</span></span>

<span data-ttu-id="e7d8b-288">Microsoft Edge 当前支持具有以下锁定体验的单应用分配访问权限的相同 Microsoft Edge 旧版展台模式类型的子集：数字/交互式标志和公共浏览。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-288">Microsoft Edge currently supports a subset of the same Microsoft Edge Legacy kiosk mode types for single-app assigned access with the following lockdown experiences: Digital/Interactive signage, and Public-browsing.</span></span>  

<span data-ttu-id="e7d8b-289">目前，在最新的  [Windows 10 Insider Preview 内部版本](https://insider.windows.com/)的版本 20215 或更高版本以及  [Microsoft Edge Beta 渠道](https://www.microsoftedgeinsider.com/download)的版本 89 或更高版本上，可以测试具有已分配访问权限的单应用的 Microsoft Edge 展台模式。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-289">Microsoft Edge kiosk mode with assigned access single app is currently available for testing with the latest [Windows 10 Insider Preview Build](https://insider.windows.com/), version 20215 or higher, and with the [Microsoft Edge Beta Channel](https://www.microsoftedgeinsider.com/download), version 89 or higher.</span></span>

**<span data-ttu-id="e7d8b-290">如何获得 Windows 预览体验成员预览版？</span><span class="sxs-lookup"><span data-stu-id="e7d8b-290">How do I get the Windows Insiders preview?</span></span>**

<span data-ttu-id="e7d8b-291">若要在电脑上安装 Windows 10 Insider Preview 内部版本，请按照 [开始使用 Windows 10 Insider Preview 版本](/windows-insider/get-started)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-291">To install a Windows 10 Insider Preview Build on a PC, follow the instructions in [Getting started with Windows 10 Insider Preview Builds](/windows-insider/get-started).</span></span>

### <a name="multi-app-kiosk"></a><span data-ttu-id="e7d8b-292">多应用展台。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-292">Multi-app kiosk</span></span>

<span data-ttu-id="e7d8b-293">可用 Windows 10 上的[多应用指派访问](/windows/configuration/lock-down-windows-10-to-specific-apps)（相当于旧版 Microsoft Edge 的“普通浏览”展台模式类型）运行 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-293">Microsoft Edge can be run with [multi-app assigned access](/windows/configuration/lock-down-windows-10-to-specific-apps) on Windows 10, which is the equivalent of Microsoft Edge Legacy "Normal browsing" kiosk mode type.</span></span> <span data-ttu-id="e7d8b-294">若要使用多应用分配的访问权限配置 Microsoft Edge，请按照有关[如何设置多应用展台](/windows/configuration/lock-down-windows-10-to-specific-apps)的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-294">To configure Microsoft Edge with multi-app assigned access, follow the instructions on how to [Set up a multi-app kiosk](/windows/configuration/lock-down-windows-10-to-specific-apps).</span></span> <span data-ttu-id="e7d8b-295">（Microsoft Edge Stable 渠道的 AUMID 为 **MSEdge**）。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-295">(The AUMID for the Microsoft Edge Stable channel is **MSEdge**).</span></span>

<span data-ttu-id="e7d8b-296">将 Microsoft Edge 与多应用分配的访问权限一同使用时，可以将 Microsoft Edge 展台配置为使用 [Microsoft Edge 浏览器策略](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies)配置浏览体验，以满足你的独特要求。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-296">When using Microsoft Edge with multi-app assigned access, you can configure Microsoft Edge kiosk to use the[Microsoft Edge browser policies](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies) to configure the browsing experience to meet your unique requirements.</span></span>

### <a name="configure-using-windows-settings"></a><span data-ttu-id="e7d8b-297">使用 Windows 设置进行配置</span><span class="sxs-lookup"><span data-stu-id="e7d8b-297">Configure using Windows Settings</span></span>

<span data-ttu-id="e7d8b-298">Windows 设置是设置一个或两个单应用展台设备的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-298">Windows Settings is the simplest way to set up one or two single-app kiosk devices.</span></span> <span data-ttu-id="e7d8b-299">使用以下步骤设置单应用展台计算机。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-299">Use the following steps to set up a single-app kiosk computer.</span></span>

1. <span data-ttu-id="e7d8b-300">安装最新的 Windows 10 Insider Preview 版本 20215 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-300">Install the latest Windows 10 Insider Preview, version 20215 or higher.</span></span> <span data-ttu-id="e7d8b-301">按照[开始使用 Windows 10 Insider Preview 版本](/windows-insider/get-started)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-301">Follow the instructions in [Getting started with Windows 10 Insider Preview Builds](/windows-insider/get-started).</span></span>
2. <span data-ttu-id="e7d8b-302">若要测试最新功能，可以下载最新的 [Microsoft Edge Beta 渠道](https://www.microsoftedgeinsider.com/download)的 89 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-302">To test the latest features, you can download the latest [Microsoft Edge Beta channel](https://www.microsoftedgeinsider.com/download), version 89 or higher.</span></span>
3. <span data-ttu-id="e7d8b-303">在展台计算机上，打开“Windows 设置”，然后在搜索字段中键入“展台”。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-303">On the kiosk computer, open Windows Settings, and type "kiosk" in the search field.</span></span> <span data-ttu-id="e7d8b-304">选择“ **设置展台（分配的访问权限）**”（如下一个屏幕截图所示），以打开用于创建展台的对话框。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-304">Select  **Set up a kiosk (assigned access)**, shown in the next screenshot to open the dialog for creating the kiosk.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="设置具有分配的访问权限的展台":::

4. <span data-ttu-id="e7d8b-306">在“**设置展台** ”页面上，单击“ **入门**”。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-306">On the **Set up a kiosk** page, click **Get started**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="展台页面 - 入门":::

5. <span data-ttu-id="e7d8b-308">键入名称以创建新的展台帐户，或从填充的下拉列表中选择现有帐户，然后单击“ **下一步**”。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-308">Type a name to create a new kiosk account or choose an existing account from the populated dropdown list and then click **Next**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="展台模式 - 创建帐户":::

6. <span data-ttu-id="e7d8b-310">在“**选择展台应用** ”页面上，选择“**Microsoft Edge**”，然后单击“ **下一步**”。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-310">On the **Choose a kiosk app** page, select **Microsoft Edge** and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e7d8b-311">这仅适用于 Microsoft Edge Dev、Beta 和 Stable 渠道。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-311">This only applies to Microsoft Edge Dev, Beta, and Stable channels.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="展台模式 - 选择应用":::

7. <span data-ttu-id="e7d8b-313">选择以下选项之一，了解 Microsoft Edge 在展台模式下运行时的显示方式：</span><span class="sxs-lookup"><span data-stu-id="e7d8b-313">Pick one of the following options for how Microsoft Edge displays when running in kiosk mode:</span></span>

   - <span data-ttu-id="e7d8b-314">数字/交互式标牌 - 运行 Microsoft Edge 时以全屏模式显示特定网站。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-314">Digital/Interactive signage - Displays a specific site in full-screen mode, running Microsoft Edge.</span></span>
   - <span data-ttu-id="e7d8b-315">公共浏览器 - 运行 Microsoft Edge 的受限多选项卡版本。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-315">Public browser - Runs a limited multi-tab version of Microsoft Edge.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="展台模式显示 - 全屏数字签名":::

8. <span data-ttu-id="e7d8b-317">选择“ **下一步**”。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-317">Select **Next**.</span></span>
9. <span data-ttu-id="e7d8b-318">键入要在展台启动时加载的 URL。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-318">Type the URL to load when the kiosk launches.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="展台模式 - 输入 URL":::

10. <span data-ttu-id="e7d8b-320">接受“5 分钟”的空闲时间默认值或提供你自己的值。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-320">Accept the default value of 5 minutes for the idle time or provide a value of your own.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="展台模式 - 输入空闲时间":::

11. <span data-ttu-id="e7d8b-322">单击“ **下一步**”。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-322">Click **Next**.</span></span>
12. <span data-ttu-id="e7d8b-323">关闭“ **设置** ”窗口，保存并应用你的选择。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-323">Close the **Settings** window to save and apply your choices.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="展台模式 - 完成设置":::

13. <span data-ttu-id="e7d8b-325">从展台设备注销，然后使用本地展台帐户登录以验证配置。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-325">Sign out from the kiosk device and sign in with the local kiosk account to validate the configuration.</span></span>

## <a name="functional-limitations"></a><span data-ttu-id="e7d8b-326">功能限制</span><span class="sxs-lookup"><span data-stu-id="e7d8b-326">Functional limitations</span></span>

<span data-ttu-id="e7d8b-327">随着展台模式此预览版的发布，我们将继续改进产品和添加新功能。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-327">With the release of this preview version of kiosk mode we're continuing work on improving the product and adding new features.</span></span>

<span data-ttu-id="e7d8b-328">目前不支持以下功能，建议关闭：</span><span class="sxs-lookup"><span data-stu-id="e7d8b-328">We currently don't support the following features and recommend that you turn off:</span></span>

- [<span data-ttu-id="e7d8b-329">InPrivateModeAvailability</span><span class="sxs-lookup"><span data-stu-id="e7d8b-329">InPrivateModeAvailability</span></span>](./microsoft-edge-policies.md#inprivatemodeavailability)
- [<span data-ttu-id="e7d8b-330">IsolateOrigins</span><span class="sxs-lookup"><span data-stu-id="e7d8b-330">IsolateOrigins</span></span>](./microsoft-edge-policies.md#isolateorigins)
- [<span data-ttu-id="e7d8b-331">ManagedFavorites</span><span class="sxs-lookup"><span data-stu-id="e7d8b-331">ManagedFavorites</span></span>](./microsoft-edge-policies.md#managedfavorites)
- [<span data-ttu-id="e7d8b-332">EdgeShoppingAssistantEnabled</span><span class="sxs-lookup"><span data-stu-id="e7d8b-332">EdgeShoppingAssistantEnabled</span></span>](./microsoft-edge-policies.md#edgeshoppingassistantenabled)
- [<span data-ttu-id="e7d8b-333">EdgeCollectionsEnabled</span><span class="sxs-lookup"><span data-stu-id="e7d8b-333">EdgeCollectionsEnabled</span></span>](./microsoft-edge-policies.md#edgecollectionsenabled)
- [<span data-ttu-id="e7d8b-334">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="e7d8b-334">UserFeedbackAllowed</span></span>](./microsoft-edge-policies.md#userfeedbackallowed)
- [<span data-ttu-id="e7d8b-335">DefaultPopupsSetting</span><span class="sxs-lookup"><span data-stu-id="e7d8b-335">DefaultPopupsSetting</span></span>](./microsoft-edge-policies.md#defaultpopupssetting)
- [<span data-ttu-id="e7d8b-336">StartupBoostEnabled</span><span class="sxs-lookup"><span data-stu-id="e7d8b-336">StartupBoostEnabled</span></span>](./microsoft-edge-policies.md#startupboostenabled)
- [<span data-ttu-id="e7d8b-337">InternetExplorerIntegrationLevel</span><span class="sxs-lookup"><span data-stu-id="e7d8b-337">InternetExplorerIntegrationLevel</span></span>](./microsoft-edge-policies.md#internetexplorerintegrationlevel)
- [<span data-ttu-id="e7d8b-338">Extensions</span><span class="sxs-lookup"><span data-stu-id="e7d8b-338">Extensions</span></span>](./microsoft-edge-policies.md#extensions-policies)
- [<span data-ttu-id="e7d8b-339">BackgroundModeEnabled</span><span class="sxs-lookup"><span data-stu-id="e7d8b-339">BackgroundModeEnabled</span></span>](./microsoft-edge-policies.md#backgroundmodeenabled)
- [<span data-ttu-id="e7d8b-340">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="e7d8b-340">UserFeedbackAllowed</span></span>](./microsoft-edge-policies.md#userfeedbackallowed)

## <a name="roadmap"></a><span data-ttu-id="e7d8b-341">路线图</span><span class="sxs-lookup"><span data-stu-id="e7d8b-341">Roadmap</span></span>

### <a name="in-early-2021"></a><span data-ttu-id="e7d8b-342">2021 年初</span><span class="sxs-lookup"><span data-stu-id="e7d8b-342">In early 2021</span></span>

<span data-ttu-id="e7d8b-343">我们将添加以下支持和功能：</span><span class="sxs-lookup"><span data-stu-id="e7d8b-343">We'll add the following support and features:</span></span>

- <span data-ttu-id="e7d8b-344">Microsoft Edge 展台模式在 Windows 10 1909 及更高版本上具有分配的访问权限单应用通用。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-344">General availability of Microsoft Edge kiosk mode with assigned access single app on Windows 10 1909 and higher.</span></span>
- <span data-ttu-id="e7d8b-345">用于与 Microsoft Edge 旧版进行奇偶校验的其他功能。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-345">Additional features for parity with Microsoft Edge Legacy.</span></span>
- <span data-ttu-id="e7d8b-346">与 Intune 集成，以使用展台模式配置文件 UX 配置设备。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-346">Integration with Intune to configure devices using kiosk mode profile UX.</span></span>
- <span data-ttu-id="e7d8b-347">限制从浏览器启动其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-347">Restrict the launch of other applications from the browser.</span></span>
- <span data-ttu-id="e7d8b-348">UI 打印设置锁定。</span><span class="sxs-lookup"><span data-stu-id="e7d8b-348">UI print settings lockdown.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7d8b-349">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7d8b-349">See also</span></span>

- [<span data-ttu-id="e7d8b-350">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="e7d8b-350">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="e7d8b-351">规划 Microsoft Edge 部署</span><span class="sxs-lookup"><span data-stu-id="e7d8b-351">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)
- [<span data-ttu-id="e7d8b-352">在 Windows 桌面版中配置展台和数字签名</span><span class="sxs-lookup"><span data-stu-id="e7d8b-352">Configure kiosks and digital signs on Windows desktop editions</span></span>](/windows/configuration/kiosk-methods)
- [<span data-ttu-id="e7d8b-353">规划展台模式转换</span><span class="sxs-lookup"><span data-stu-id="e7d8b-353">Plan your kiosk mode transition</span></span>](microsoft-edge-kiosk-mode-transition-plan.md)