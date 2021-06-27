---
title: 配置 Microsoft Edge 展台模式
ms.author: aguta
author: aguta
manager: srugh
ms.date: 04/26/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解展台模式功能以及如何配置 Microsoft Edge 展台模式的选项。
ms.openlocfilehash: 20cb32c0cd27ad6d7437ed8ae0440560f3ed71b2
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617852"
---
# <a name="configure-microsoft-edge-kiosk-mode"></a><span data-ttu-id="321dc-103">配置 Microsoft Edge 展台模式</span><span class="sxs-lookup"><span data-stu-id="321dc-103">Configure Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="321dc-104">本文介绍如何配置可以试用的 Microsoft Edge 展台模式选项。</span><span class="sxs-lookup"><span data-stu-id="321dc-104">This article describes how to configure Microsoft Edge kiosk mode options that you can pilot.</span></span> <span data-ttu-id="321dc-105">还有一个在我们目标之中的功能路线图。</span><span class="sxs-lookup"><span data-stu-id="321dc-105">There's also a roadmap of features we're targeting.</span></span>

> [!NOTE]
> <span data-ttu-id="321dc-106">本文适用于 Microsoft Edge 版本 87 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="321dc-106">This article applies to Microsoft Edge version 87 or later.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="321dc-107">通过[使用展台模式功能](#use-kiosk-mode-features)中提供的命令行参数调用 Windows 10 Microsoft Edge 展台模式功能。</span><span class="sxs-lookup"><span data-stu-id="321dc-107">Invoke Microsoft Edge kiosk mode features on Windows 10 using the command line arguments provided in [Use kiosk mode features](#use-kiosk-mode-features).</span></span>

## <a name="overview"></a><span data-ttu-id="321dc-108">概述</span><span class="sxs-lookup"><span data-stu-id="321dc-108">Overview</span></span>

<span data-ttu-id="321dc-109">Microsoft Edge 展台模式提供两种浏览器锁定体验，因此组织可以创建、管理并为其客户提供最佳体验。</span><span class="sxs-lookup"><span data-stu-id="321dc-109">Microsoft Edge kiosk mode offers two lockdown experiences of the browser so organizations can create, manage, and provide the best experience for their customers.</span></span> <span data-ttu-id="321dc-110">提供以下锁定体验：</span><span class="sxs-lookup"><span data-stu-id="321dc-110">The following lockdown experiences are available:</span></span>  

- <span data-ttu-id="321dc-111">**数字/交互式标志** 体验 - 以全屏模式显示特定网站。</span><span class="sxs-lookup"><span data-stu-id="321dc-111">**Digital/Interactive Signage** experience - Displays a specific site in full-screen mode.</span></span>
- <span data-ttu-id="321dc-112">**公共浏览** 体验 - 运行 Microsoft Edge 的有限多选项卡版本。</span><span class="sxs-lookup"><span data-stu-id="321dc-112">**Public-Browsing** experience - Runs a limited multi-tab version of Microsoft Edge.</span></span>

<span data-ttu-id="321dc-113">这两种体验都在运行 Microsoft Edge InPrivate 会话，以保护用户数据。</span><span class="sxs-lookup"><span data-stu-id="321dc-113">Both experiences are running a Microsoft Edge InPrivate session, which protects user data.</span></span>

## <a name="set-up-microsoft-edge-kiosk-mode"></a><span data-ttu-id="321dc-114">设置 Microsoft Edge 展台模式</span><span class="sxs-lookup"><span data-stu-id="321dc-114">Set up Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="321dc-115">可以使用 Microsoft Edge Stable 渠道版本 87 测试一组初始展台模式功能。</span><span class="sxs-lookup"><span data-stu-id="321dc-115">An initial set of kiosk mode features is available to test with Microsoft Edge Stable Channel, version 87.</span></span> <span data-ttu-id="321dc-116">你可以从 [Microsoft Edge (Official Stable 渠道)](https://www.microsoft.com/edge)下载。</span><span class="sxs-lookup"><span data-stu-id="321dc-116">You can download the latest version from [Microsoft Edge (Official Stable Channel)](https://www.microsoft.com/edge).</span></span>

### <a name="kiosk-mode-supported-features"></a><span data-ttu-id="321dc-117">展台模式支持的功能</span><span class="sxs-lookup"><span data-stu-id="321dc-117">Kiosk mode supported features</span></span>

<span data-ttu-id="321dc-118">下表列出了 Microsoft Edge 和 Microsoft Edge 旧版中的展台模式支持的功能。</span><span class="sxs-lookup"><span data-stu-id="321dc-118">The following table lists the features supported by kiosk mode in Microsoft Edge and Microsoft Edge Legacy.</span></span> <span data-ttu-id="321dc-119">比较这两个版本的 Microsoft Edge 支持的功能有何不同，将此表用作指南以转换为 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="321dc-119">Use this table as a guide to transitioning to Microsoft Edge by comparing how these features are supported in both versions of Microsoft Edge.</span></span>

|<span data-ttu-id="321dc-120">功能</span><span class="sxs-lookup"><span data-stu-id="321dc-120">Feature</span></span>|<span data-ttu-id="321dc-121">数字\交互式标志</span><span class="sxs-lookup"><span data-stu-id="321dc-121">Digital\Interactive Signage</span></span>|<span data-ttu-id="321dc-122">公共浏览</span><span class="sxs-lookup"><span data-stu-id="321dc-122">Public browsing</span></span>|<span data-ttu-id="321dc-123">适用于 Microsoft Edge 版本（及更高版本）</span><span class="sxs-lookup"><span data-stu-id="321dc-123">Available with Microsoft Edge version (and higher)</span></span>|<span data-ttu-id="321dc-124">适用于 Microsoft Edge 旧版</span><span class="sxs-lookup"><span data-stu-id="321dc-124">Available with Microsoft Edge Legacy</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="321dc-125">InPrivate 导航</span><span class="sxs-lookup"><span data-stu-id="321dc-125">InPrivate Navigation</span></span>|<span data-ttu-id="321dc-126">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-126">Y</span></span>|<span data-ttu-id="321dc-127">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-127">Y</span></span>|<span data-ttu-id="321dc-128">89</span><span class="sxs-lookup"><span data-stu-id="321dc-128">89</span></span>|<span data-ttu-id="321dc-129">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-129">Y</span></span>|
|<span data-ttu-id="321dc-130">在处于非活动状态时重置</span><span class="sxs-lookup"><span data-stu-id="321dc-130">Reset on inactivity</span></span>|<span data-ttu-id="321dc-131">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-131">Y</span></span>|<span data-ttu-id="321dc-132">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-132">Y</span></span>|<span data-ttu-id="321dc-133">89</span><span class="sxs-lookup"><span data-stu-id="321dc-133">89</span></span>|<span data-ttu-id="321dc-134">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-134">Y</span></span>|
|<span data-ttu-id="321dc-135">[只读地址栏](./microsoft-edge-policies.md#kioskaddressbareditingenabled) (策略)</span><span class="sxs-lookup"><span data-stu-id="321dc-135">[Read only address bar](./microsoft-edge-policies.md#kioskaddressbareditingenabled) (policy)</span></span> |<span data-ttu-id="321dc-136">N</span><span class="sxs-lookup"><span data-stu-id="321dc-136">N</span></span>|<span data-ttu-id="321dc-137">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-137">Y</span></span> |<span data-ttu-id="321dc-138">89</span><span class="sxs-lookup"><span data-stu-id="321dc-138">89</span></span>|<span data-ttu-id="321dc-139">N</span><span class="sxs-lookup"><span data-stu-id="321dc-139">N</span></span>|
|<span data-ttu-id="321dc-140">[退出时删除下载](./microsoft-edge-policies.md#kioskdeletedownloadsonexit)（策略）</span><span class="sxs-lookup"><span data-stu-id="321dc-140">[Delete downloads on exit](./microsoft-edge-policies.md#kioskdeletedownloadsonexit) (policy)</span></span>  | <span data-ttu-id="321dc-141">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-141">Y</span></span>|<span data-ttu-id="321dc-142">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-142">Y</span></span> |<span data-ttu-id="321dc-143">89</span><span class="sxs-lookup"><span data-stu-id="321dc-143">89</span></span>|<span data-ttu-id="321dc-144">N</span><span class="sxs-lookup"><span data-stu-id="321dc-144">N</span></span>|
|<span data-ttu-id="321dc-145">已阻止 F11（进入/退出全屏）</span><span class="sxs-lookup"><span data-stu-id="321dc-145">F11 blocked (enter/exit full-screen)</span></span> | <span data-ttu-id="321dc-146">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-146">Y</span></span> | <span data-ttu-id="321dc-147">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-147">Y</span></span> |<span data-ttu-id="321dc-148">89</span><span class="sxs-lookup"><span data-stu-id="321dc-148">89</span></span>|<span data-ttu-id="321dc-149">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-149">Y</span></span>|
|<span data-ttu-id="321dc-150">已阻止F12（启动开发人员工具）</span><span class="sxs-lookup"><span data-stu-id="321dc-150">F12 blocked (launch Developer Tools)</span></span> | <span data-ttu-id="321dc-151">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-151">Y</span></span> | <span data-ttu-id="321dc-152">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-152">Y</span></span> |<span data-ttu-id="321dc-153">89</span><span class="sxs-lookup"><span data-stu-id="321dc-153">89</span></span>|<span data-ttu-id="321dc-154">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-154">Y</span></span>|
| <span data-ttu-id="321dc-155">多选项卡支持</span><span class="sxs-lookup"><span data-stu-id="321dc-155">Multi tab support</span></span> | <span data-ttu-id="321dc-156">N</span><span class="sxs-lookup"><span data-stu-id="321dc-156">N</span></span>| <span data-ttu-id="321dc-157">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-157">Y</span></span>|<span data-ttu-id="321dc-158">89</span><span class="sxs-lookup"><span data-stu-id="321dc-158">89</span></span>|<span data-ttu-id="321dc-159">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-159">Y</span></span>|
|<span data-ttu-id="321dc-160">[允许 URL 支持](./microsoft-edge-policies.md#urlallowlist)（策略）</span><span class="sxs-lookup"><span data-stu-id="321dc-160">[Allow URL support](./microsoft-edge-policies.md#urlallowlist) (policy)</span></span>|<span data-ttu-id="321dc-161">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-161">Y</span></span>|<span data-ttu-id="321dc-162">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-162">Y</span></span>|<span data-ttu-id="321dc-163">89</span><span class="sxs-lookup"><span data-stu-id="321dc-163">89</span></span>|<span data-ttu-id="321dc-164">N</span><span class="sxs-lookup"><span data-stu-id="321dc-164">N</span></span>|
|<span data-ttu-id="321dc-165">[阻止 URL 支持](./microsoft-edge-policies.md#urlblocklist)（策略）</span><span class="sxs-lookup"><span data-stu-id="321dc-165">[Block URL support](./microsoft-edge-policies.md#urlblocklist) (policy)</span></span>|<span data-ttu-id="321dc-166">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-166">Y</span></span>|<span data-ttu-id="321dc-167">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-167">Y</span></span>|<span data-ttu-id="321dc-168">89</span><span class="sxs-lookup"><span data-stu-id="321dc-168">89</span></span>|<span data-ttu-id="321dc-169">N</span><span class="sxs-lookup"><span data-stu-id="321dc-169">N</span></span>|
|<span data-ttu-id="321dc-170">[显示“主页”按钮](./microsoft-edge-policies.md#showhomebutton)（策略）</span><span class="sxs-lookup"><span data-stu-id="321dc-170">[Show home button](./microsoft-edge-policies.md#showhomebutton) (policy)</span></span>|<span data-ttu-id="321dc-171">N</span><span class="sxs-lookup"><span data-stu-id="321dc-171">N</span></span>|<span data-ttu-id="321dc-172">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-172">Y</span></span>|<span data-ttu-id="321dc-173">89</span><span class="sxs-lookup"><span data-stu-id="321dc-173">89</span></span>|<span data-ttu-id="321dc-174">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-174">Y</span></span>|
|<span data-ttu-id="321dc-175">[管理收藏夹](./microsoft-edge-policies.md#managedfavorites)（策略）</span><span class="sxs-lookup"><span data-stu-id="321dc-175">[Manage favorites](./microsoft-edge-policies.md#managedfavorites) (policy)</span></span>|<span data-ttu-id="321dc-176">N</span><span class="sxs-lookup"><span data-stu-id="321dc-176">N</span></span>|<span data-ttu-id="321dc-177">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-177">Y</span></span>|<span data-ttu-id="321dc-178">89</span><span class="sxs-lookup"><span data-stu-id="321dc-178">89</span></span>|<span data-ttu-id="321dc-179">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-179">Y</span></span>|
|<span data-ttu-id="321dc-180">[启用打印机](./microsoft-edge-policies.md#printingenabled)（策略）</span><span class="sxs-lookup"><span data-stu-id="321dc-180">[Enable printer](./microsoft-edge-policies.md#printingenabled) (policy)</span></span>|<span data-ttu-id="321dc-181">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-181">Y</span></span>|<span data-ttu-id="321dc-182">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-182">Y</span></span>|<span data-ttu-id="321dc-183">89</span><span class="sxs-lookup"><span data-stu-id="321dc-183">89</span></span>|<span data-ttu-id="321dc-184">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-184">Y</span></span>|
|<span data-ttu-id="321dc-185">[配置新标签页页面 URL](./microsoft-edge-policies.md#newtabpagelocation)（策略）</span><span class="sxs-lookup"><span data-stu-id="321dc-185">[Configure the new tab page URL](./microsoft-edge-policies.md#newtabpagelocation) (policy)</span></span>|<span data-ttu-id="321dc-186">N</span><span class="sxs-lookup"><span data-stu-id="321dc-186">N</span></span>|<span data-ttu-id="321dc-187">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-187">Y</span></span>|<span data-ttu-id="321dc-188">89</span><span class="sxs-lookup"><span data-stu-id="321dc-188">89</span></span>|<span data-ttu-id="321dc-189">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-189">Y</span></span>|
|<span data-ttu-id="321dc-190">结束会话按钮 \*</span><span class="sxs-lookup"><span data-stu-id="321dc-190">End session button \*</span></span> | <span data-ttu-id="321dc-191">N</span><span class="sxs-lookup"><span data-stu-id="321dc-191">N</span></span>| <span data-ttu-id="321dc-192">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-192">Y</span></span>|<span data-ttu-id="321dc-193">89</span><span class="sxs-lookup"><span data-stu-id="321dc-193">89</span></span>|<span data-ttu-id="321dc-194">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-194">Y</span></span>|
|<span data-ttu-id="321dc-195">所有内部 Microsoft Edge URL 已将被阻止，除了*edge://downloads*和*edge://print*</span><span class="sxs-lookup"><span data-stu-id="321dc-195">All internal Microsoft Edge URLs are blocked, except for *edge://downloads* and *edge://print*</span></span> |<span data-ttu-id="321dc-196">N</span><span class="sxs-lookup"><span data-stu-id="321dc-196">N</span></span>|<span data-ttu-id="321dc-197">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-197">Y</span></span>|<span data-ttu-id="321dc-198">89</span><span class="sxs-lookup"><span data-stu-id="321dc-198">89</span></span>|<span data-ttu-id="321dc-199">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-199">Y</span></span>|
| <span data-ttu-id="321dc-200">Ctrl+N 阻止 (打开新窗口) \*</span><span class="sxs-lookup"><span data-stu-id="321dc-200">CTRL+N blocked (open a new window) \*</span></span> | <span data-ttu-id="321dc-201">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-201">Y</span></span> | <span data-ttu-id="321dc-202">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-202">Y</span></span> |<span data-ttu-id="321dc-203">89</span><span class="sxs-lookup"><span data-stu-id="321dc-203">89</span></span>|<span data-ttu-id="321dc-204">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-204">Y</span></span>|
| <span data-ttu-id="321dc-205">已阻止 Ctrl+T（打开新选项卡）</span><span class="sxs-lookup"><span data-stu-id="321dc-205">CTRL+T blocked (open new tab)</span></span> |<span data-ttu-id="321dc-206">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-206">Y</span></span> | <span data-ttu-id="321dc-207">N</span><span class="sxs-lookup"><span data-stu-id="321dc-207">N</span></span> |<span data-ttu-id="321dc-208">89</span><span class="sxs-lookup"><span data-stu-id="321dc-208">89</span></span>|<span data-ttu-id="321dc-209">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-209">Y</span></span>|
|<span data-ttu-id="321dc-210">设置和更多 (...) 将仅显示所需的选项</span><span class="sxs-lookup"><span data-stu-id="321dc-210">Settings and more (...) will display only the required options</span></span>  |<span data-ttu-id="321dc-211">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-211">Y</span></span> |<span data-ttu-id="321dc-212">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-212">Y</span></span> |<span data-ttu-id="321dc-213">89</span><span class="sxs-lookup"><span data-stu-id="321dc-213">89</span></span>|<span data-ttu-id="321dc-214">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-214">Y</span></span>|
|<span data-ttu-id="321dc-215">限制从浏览器启动其他应用程序</span><span class="sxs-lookup"><span data-stu-id="321dc-215">Restrict the launch of other applications from the browser</span></span>|<span data-ttu-id="321dc-216">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-216">Y</span></span>|<span data-ttu-id="321dc-217">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-217">Y</span></span>|<span data-ttu-id="321dc-218">90</span><span class="sxs-lookup"><span data-stu-id="321dc-218">90</span></span>|<span data-ttu-id="321dc-219">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-219">Y</span></span>|
|<span data-ttu-id="321dc-220">UI 打印设置锁定</span><span class="sxs-lookup"><span data-stu-id="321dc-220">UI print settings lockdown</span></span>|<span data-ttu-id="321dc-221">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-221">Y</span></span>|<span data-ttu-id="321dc-222">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-222">Y</span></span>|<span data-ttu-id="321dc-223">90</span><span class="sxs-lookup"><span data-stu-id="321dc-223">90</span></span>|<span data-ttu-id="321dc-224">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-224">Y</span></span>|
|<span data-ttu-id="321dc-225">[将新标签页设置为主页](./microsoft-edge-policies.md#homepageisnewtabpage)（策略）</span><span class="sxs-lookup"><span data-stu-id="321dc-225">[Set the new tab page as the home page](./microsoft-edge-policies.md#homepageisnewtabpage) (policy)</span></span>|<span data-ttu-id="321dc-226">N</span><span class="sxs-lookup"><span data-stu-id="321dc-226">N</span></span>|<span data-ttu-id="321dc-227">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-227">Y</span></span>|<span data-ttu-id="321dc-228">90</span><span class="sxs-lookup"><span data-stu-id="321dc-228">90</span></span>|<span data-ttu-id="321dc-229">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-229">Y</span></span>|

> [!NOTE]
> <span data-ttu-id="321dc-230">后跟“\*”的功能仅在已分配的访问单一应用场景中启用。</span><span class="sxs-lookup"><span data-stu-id="321dc-230">Features followed by "\*" are only enabled in an assigned access single app scenario.</span></span>

## <a name="use-kiosk-mode-features"></a><span data-ttu-id="321dc-231">使用展台模式功能</span><span class="sxs-lookup"><span data-stu-id="321dc-231">Use kiosk mode features</span></span>

<span data-ttu-id="321dc-232">对于数字/交互式标牌和公共浏览，可通过以下 Windows 10 命令行选项调用 Microsoft Edge 展台模式功能。</span><span class="sxs-lookup"><span data-stu-id="321dc-232">Microsoft Edge kiosk mode features can be invoked with the following Windows 10 command line options for Digital/Interactive signage and Public browsing.</span></span>

### <a name="kiosk-mode-digitalinteractive-signage"></a><span data-ttu-id="321dc-233">展台模式数字/交互式标牌</span><span class="sxs-lookup"><span data-stu-id="321dc-233">Kiosk mode Digital/Interactive signage</span></span>
 
```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen
```

### <a name="kiosk-mode-public-browsing"></a><span data-ttu-id="321dc-234">展台模式公共浏览</span><span class="sxs-lookup"><span data-stu-id="321dc-234">Kiosk mode Public browsing</span></span>

```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing
```

### <a name="additional-command-line-options"></a><span data-ttu-id="321dc-235">其他命令行选项</span><span class="sxs-lookup"><span data-stu-id="321dc-235">Additional command line options</span></span>

- <span data-ttu-id="321dc-236">**--no-first-run**：禁用首次 Microsoft Edge 运行体验。</span><span class="sxs-lookup"><span data-stu-id="321dc-236">**--no-first-run**: Disable the first Microsoft Edge run experience.</span></span>

   ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --no-first-run
  ```

  ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --no-first-run
  ```

- <span data-ttu-id="321dc-237">**--kiosk-idle-timeout-minutes=**：更改从上次用户活动到 Microsoft Edge 展台模式重置用户会话前的时间（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="321dc-237">**--kiosk-idle-timeout-minutes=**: Change the time (in minutes) from the last user activity before Microsoft Edge kiosk mode resets the user's session.</span></span> <span data-ttu-id="321dc-238">将以下示例中的“值”替换为分钟数。</span><span class="sxs-lookup"><span data-stu-id="321dc-238">Replace "value" in the next example with the number of minutes.</span></span>

   ```
   --kiosk-idle-timeout-minutes=value
   ``` 
   <span data-ttu-id="321dc-239">支持以下“值”：</span><span class="sxs-lookup"><span data-stu-id="321dc-239">The following "values" are supported:</span></span>

     - <span data-ttu-id="321dc-240">默认值（分钟）</span><span class="sxs-lookup"><span data-stu-id="321dc-240">Default values (in minutes)</span></span>
       - <span data-ttu-id="321dc-241">全屏 - 0（关闭）</span><span class="sxs-lookup"><span data-stu-id="321dc-241">Full screen - 0 (turned off)</span></span>
       - <span data-ttu-id="321dc-242">公共浏览 - 5 分钟</span><span class="sxs-lookup"><span data-stu-id="321dc-242">Public browsing - 5 minutes</span></span>
    - <span data-ttu-id="321dc-243">允许的值</span><span class="sxs-lookup"><span data-stu-id="321dc-243">Allowed values</span></span>
      - <span data-ttu-id="321dc-244">0 - 关闭计时器</span><span class="sxs-lookup"><span data-stu-id="321dc-244">0 - turns off the timer</span></span>
      - <span data-ttu-id="321dc-245">1-1440 分钟，用于在空闲计时器上重置</span><span class="sxs-lookup"><span data-stu-id="321dc-245">1-1440 minutes for reset on idle timer</span></span>


    ```
    msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --kiosk-idle-timeout-minutes=1
   ```

   ```
   msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --kiosk-idle-timeout-minutes=1
   ```

## <a name="support-policies-for-kiosk-mode"></a><span data-ttu-id="321dc-246">展台模式的支持策略</span><span class="sxs-lookup"><span data-stu-id="321dc-246">Support policies for kiosk mode</span></span>

<span data-ttu-id="321dc-247">使用下表中列出的任何 Microsoft Edge 策略增强所配置的 Microsoft Edge 展台模式类型的展台体验。</span><span class="sxs-lookup"><span data-stu-id="321dc-247">Use any of the Microsoft Edge policies listed in the following table to enhance the kiosk experience for the Microsoft Edge kiosk mode type you configure.</span></span> <span data-ttu-id="321dc-248">若要了解有关这些策略的信息，请参阅 [Microsoft Edge – 浏览器策略参考](./microsoft-edge-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="321dc-248">To learn more about these policies, see [Microsoft Edge – Browser policy reference](./microsoft-edge-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="321dc-249">策略配置不限于下表中列出的策略，但应测试其他策略以确保展台模式功能不会受到负面影响。</span><span class="sxs-lookup"><span data-stu-id="321dc-249">Policy configuration isn't limited to the policies listed in the following table, however additional policies should be tested to ensure that kiosk mode functionality isn't negatively affected.</span></span>

|<span data-ttu-id="321dc-250">组策略</span><span class="sxs-lookup"><span data-stu-id="321dc-250">Group policy</span></span>|<span data-ttu-id="321dc-251">数字\交互式标志</span><span class="sxs-lookup"><span data-stu-id="321dc-251">Digital\Interactive signage</span></span>|<span data-ttu-id="321dc-252">公共浏览单应用</span><span class="sxs-lookup"><span data-stu-id="321dc-252">Public browsing single-app</span></span>|
|--|--|--|
|[<span data-ttu-id="321dc-253">打印</span><span class="sxs-lookup"><span data-stu-id="321dc-253">Printing</span></span>](./microsoft-edge-policies.md#printing-policies) | <span data-ttu-id="321dc-254">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-254">Y</span></span>|<span data-ttu-id="321dc-255">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-255">Y</span></span> |
|[<span data-ttu-id="321dc-256">HomePageLocation</span><span class="sxs-lookup"><span data-stu-id="321dc-256">HomePageLocation</span></span>](./microsoft-edge-policies.md#homepagelocation) |<span data-ttu-id="321dc-257">N</span><span class="sxs-lookup"><span data-stu-id="321dc-257">N</span></span> | <span data-ttu-id="321dc-258">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-258">Y</span></span>|
|[<span data-ttu-id="321dc-259">ShowHomeButton</span><span class="sxs-lookup"><span data-stu-id="321dc-259">ShowHomeButton</span></span>](./microsoft-edge-policies.md#showhomebutton) |<span data-ttu-id="321dc-260">N</span><span class="sxs-lookup"><span data-stu-id="321dc-260">N</span></span> | <span data-ttu-id="321dc-261">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-261">Y</span></span>|
|[<span data-ttu-id="321dc-262">NewTabPageLocation</span><span class="sxs-lookup"><span data-stu-id="321dc-262">NewTabPageLocation</span></span>](./microsoft-edge-policies.md#newtabpagelocation) |<span data-ttu-id="321dc-263">N</span><span class="sxs-lookup"><span data-stu-id="321dc-263">N</span></span> |<span data-ttu-id="321dc-264">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-264">Y</span></span> |
|[<span data-ttu-id="321dc-265">FavoritesBarEnabled</span><span class="sxs-lookup"><span data-stu-id="321dc-265">FavoritesBarEnabled</span></span>](./microsoft-edge-policies.md#favoritesbarenabled) |<span data-ttu-id="321dc-266">N</span><span class="sxs-lookup"><span data-stu-id="321dc-266">N</span></span> |<span data-ttu-id="321dc-267">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-267">Y</span></span> |
|[<span data-ttu-id="321dc-268">URLAllowlist</span><span class="sxs-lookup"><span data-stu-id="321dc-268">URLAllowlist</span></span>](./microsoft-edge-policies.md#urlallowlist) |<span data-ttu-id="321dc-269">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-269">Y</span></span> |<span data-ttu-id="321dc-270">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-270">Y</span></span> |
|[<span data-ttu-id="321dc-271">URLBlocklist</span><span class="sxs-lookup"><span data-stu-id="321dc-271">URLBlocklist</span></span>](./microsoft-edge-policies.md#urlblocklist) |<span data-ttu-id="321dc-272">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-272">Y</span></span> | <span data-ttu-id="321dc-273">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-273">Y</span></span>|
|[<span data-ttu-id="321dc-274">ManagedSearchEngines</span><span class="sxs-lookup"><span data-stu-id="321dc-274">ManagedSearchEngines</span></span>](./microsoft-edge-policies.md#managedsearchengines) |<span data-ttu-id="321dc-275">N</span><span class="sxs-lookup"><span data-stu-id="321dc-275">N</span></span> | <span data-ttu-id="321dc-276">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-276">Y</span></span>|
|[<span data-ttu-id="321dc-277">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="321dc-277">UserFeedbackAllowed</span></span>](./microsoft-edge-policies.md#userfeedbackallowed) |<span data-ttu-id="321dc-278">N</span><span class="sxs-lookup"><span data-stu-id="321dc-278">N</span></span> | <span data-ttu-id="321dc-279">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-279">Y</span></span>|
|[<span data-ttu-id="321dc-280">VerticalTabsAllowed</span><span class="sxs-lookup"><span data-stu-id="321dc-280">VerticalTabsAllowed</span></span>](./microsoft-edge-policies.md#verticaltabsallowed) | <span data-ttu-id="321dc-281">N</span><span class="sxs-lookup"><span data-stu-id="321dc-281">N</span></span>|<span data-ttu-id="321dc-282">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-282">Y</span></span> |
|[<span data-ttu-id="321dc-283">SmartScreen 设置</span><span class="sxs-lookup"><span data-stu-id="321dc-283">SmartScreen settings</span></span>](./microsoft-edge-policies.md#smartscreen-settings-policies) |<span data-ttu-id="321dc-284">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-284">Y</span></span> |<span data-ttu-id="321dc-285">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-285">Y</span></span> |
|[<span data-ttu-id="321dc-286">EdgeCollectionsEnabled</span><span class="sxs-lookup"><span data-stu-id="321dc-286">EdgeCollectionsEnabled</span></span>](./microsoft-edge-policies.md#edgecollectionsenabled)|<span data-ttu-id="321dc-287">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-287">Y</span></span>|<span data-ttu-id="321dc-288">Y</span><span class="sxs-lookup"><span data-stu-id="321dc-288">Y</span></span>|

## <a name="microsoft-edge-with-assigned-access"></a><span data-ttu-id="321dc-289">Microsoft Edge 与指派访问</span><span class="sxs-lookup"><span data-stu-id="321dc-289">Microsoft Edge with assigned access</span></span>

### <a name="single-app-kiosk"></a><span data-ttu-id="321dc-290">单应用展台</span><span class="sxs-lookup"><span data-stu-id="321dc-290">Single app kiosk</span></span>

<span data-ttu-id="321dc-291">Microsoft Edge 版本 90 展台模式提供了广泛的功能列表。</span><span class="sxs-lookup"><span data-stu-id="321dc-291">Microsoft Edge version 90 kiosk mode offers an extensive list of features.</span></span> <span data-ttu-id="321dc-292">请参阅展台模式支持的功能一节。</span><span class="sxs-lookup"><span data-stu-id="321dc-292">See the section of Kiosk mode supported features.</span></span>
<span data-ttu-id="321dc-293">使用以下 Windows 更新，可以通过分配的访问权限单应用配置 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="321dc-293">With the following Windows updates you can configure Microsoft Edge via assigned access single app.</span></span>

|<span data-ttu-id="321dc-294">操作系统</span><span class="sxs-lookup"><span data-stu-id="321dc-294">Operating System</span></span>|<span data-ttu-id="321dc-295">版本</span><span class="sxs-lookup"><span data-stu-id="321dc-295">Version</span></span>|<span data-ttu-id="321dc-296">更新</span><span class="sxs-lookup"><span data-stu-id="321dc-296">Updates</span></span>|
|--|--|--|
|<span data-ttu-id="321dc-297">Windows 10</span><span class="sxs-lookup"><span data-stu-id="321dc-297">Windows 10</span></span> | <span data-ttu-id="321dc-298">2004 或更高版本</span><span class="sxs-lookup"><span data-stu-id="321dc-298">2004 or later</span></span>|[<span data-ttu-id="321dc-299">KB4601382 或更高版本</span><span class="sxs-lookup"><span data-stu-id="321dc-299">KB4601382 or later</span></span>](https://support.microsoft.com/topic/february-24-2021-kb4601382-os-builds-19041-844-and-19042-844-preview-1a7ed2b4-017d-2644-a1e8-dd6bf14cba76) |
|<span data-ttu-id="321dc-300">Windows 10</span><span class="sxs-lookup"><span data-stu-id="321dc-300">Windows 10</span></span>| <span data-ttu-id="321dc-301">1909</span><span class="sxs-lookup"><span data-stu-id="321dc-301">1909</span></span>| [<span data-ttu-id="321dc-302">KB4601380 或更高版本</span><span class="sxs-lookup"><span data-stu-id="321dc-302">KB4601380 or later</span></span>](https://support.microsoft.com/topic/february-16-2021-kb4601380-os-build-18363-1411-preview-2e3c38e1-a947-1033-8006-a30f3806da18)|

<span data-ttu-id="321dc-303">可以通过 [Windows 设置](/deployedge/microsoft-edge-configure-kiosk-mode#configure-using-windows-settings)和 Intune 管理 Microsoft Edge展台模式分配的访问权限单应用。</span><span class="sxs-lookup"><span data-stu-id="321dc-303">You can manage Microsoft Edge kiosk mode assigned access single app via [Windows Settings](/deployedge/microsoft-edge-configure-kiosk-mode#configure-using-windows-settings) and Intune.</span></span>

### <a name="multi-app-kiosk"></a><span data-ttu-id="321dc-304">多应用展台。</span><span class="sxs-lookup"><span data-stu-id="321dc-304">Multi-app kiosk</span></span>

<span data-ttu-id="321dc-305">可用 Windows 10 上的[多应用指派访问](/windows/configuration/lock-down-windows-10-to-specific-apps)（相当于旧版 Microsoft Edge 的“普通浏览”展台模式类型）运行 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="321dc-305">Microsoft Edge can be run with [multi-app assigned access](/windows/configuration/lock-down-windows-10-to-specific-apps) on Windows 10, which is the equivalent of Microsoft Edge Legacy "Normal browsing" kiosk mode type.</span></span> <span data-ttu-id="321dc-306">若要使用多应用分配的访问权限配置 Microsoft Edge，请按照有关[如何设置多应用展台](/windows/configuration/lock-down-windows-10-to-specific-apps)的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="321dc-306">To configure Microsoft Edge with multi-app assigned access, follow the instructions on how to [Set up a multi-app kiosk](/windows/configuration/lock-down-windows-10-to-specific-apps).</span></span> <span data-ttu-id="321dc-307">（Microsoft Edge Stable 渠道的 AUMID 为 **MSEdge**）。</span><span class="sxs-lookup"><span data-stu-id="321dc-307">(The AUMID for the Microsoft Edge Stable channel is **MSEdge**).</span></span>

### <a name="configure-using-windows-settings"></a><span data-ttu-id="321dc-308">使用 Windows 设置进行配置</span><span class="sxs-lookup"><span data-stu-id="321dc-308">Configure using Windows Settings</span></span>

<span data-ttu-id="321dc-309">Windows 设置是设置一个或两个单应用展台设备的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="321dc-309">Windows Settings is the simplest way to set up one or two single-app kiosk devices.</span></span> <span data-ttu-id="321dc-310">使用以下步骤设置单应用展台计算机。</span><span class="sxs-lookup"><span data-stu-id="321dc-310">Use the following steps to set up a single-app kiosk computer.</span></span>

1. <span data-ttu-id="321dc-311">下表中列出了操作系统的最低系统更新。</span><span class="sxs-lookup"><span data-stu-id="321dc-311">The minimum system updates for the operating systems listed in the next table.</span></span>

|<span data-ttu-id="321dc-312">操作系统</span><span class="sxs-lookup"><span data-stu-id="321dc-312">Operating System</span></span>|<span data-ttu-id="321dc-313">版本</span><span class="sxs-lookup"><span data-stu-id="321dc-313">Version</span></span>|<span data-ttu-id="321dc-314">更新</span><span class="sxs-lookup"><span data-stu-id="321dc-314">Updates</span></span>|
|--|--|--|
|<span data-ttu-id="321dc-315">Windows 10</span><span class="sxs-lookup"><span data-stu-id="321dc-315">Windows 10</span></span> | <span data-ttu-id="321dc-316">2004 或更高版本</span><span class="sxs-lookup"><span data-stu-id="321dc-316">2004 or later</span></span>|[<span data-ttu-id="321dc-317">KB4601382 或更高版本</span><span class="sxs-lookup"><span data-stu-id="321dc-317">KB4601382 or later</span></span>](https://support.microsoft.com/topic/february-24-2021-kb4601382-os-builds-19041-844-and-19042-844-preview-1a7ed2b4-017d-2644-a1e8-dd6bf14cba76) |
|<span data-ttu-id="321dc-318">Windows 10</span><span class="sxs-lookup"><span data-stu-id="321dc-318">Windows 10</span></span>| <span data-ttu-id="321dc-319">1909</span><span class="sxs-lookup"><span data-stu-id="321dc-319">1909</span></span>| [<span data-ttu-id="321dc-320">KB4601380 或更高版本</span><span class="sxs-lookup"><span data-stu-id="321dc-320">KB4601380 or later</span></span>](https://support.microsoft.com/topic/february-16-2021-kb4601380-os-build-18363-1411-preview-2e3c38e1-a947-1033-8006-a30f3806da18)|

2. <span data-ttu-id="321dc-321">若要测试最新功能，可以下载最新的 [Microsoft Edge Stable 渠道](https://www.microsoft.com/edge/business/download)的 89 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="321dc-321">To test the latest features, you can download the latest [Microsoft Edge Stable channel](https://www.microsoft.com/edge/business/download), version 89 or higher.</span></span>

3. <span data-ttu-id="321dc-322">在展台计算机上，打开“Windows 设置”，然后在搜索字段中键入“展台”。</span><span class="sxs-lookup"><span data-stu-id="321dc-322">On the kiosk computer, open Windows Settings, and type "kiosk" in the search field.</span></span> <span data-ttu-id="321dc-323">选择“ **设置展台（分配的访问权限）**”（如下一个屏幕截图所示），以打开用于创建展台的对话框。</span><span class="sxs-lookup"><span data-stu-id="321dc-323">Select  **Set up a kiosk (assigned access)**, shown in the next screenshot to open the dialog for creating the kiosk.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="设置具有分配的访问权限的展台":::

4. <span data-ttu-id="321dc-325">在“**设置展台** ”页面上，单击“ **入门**”。</span><span class="sxs-lookup"><span data-stu-id="321dc-325">On the **Set up a kiosk** page, click **Get started**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="展台页面 - 入门":::

5. <span data-ttu-id="321dc-327">键入名称以创建新的展台帐户，或从填充的下拉列表中选择现有帐户，然后单击“ **下一步**”。</span><span class="sxs-lookup"><span data-stu-id="321dc-327">Type a name to create a new kiosk account or choose an existing account from the populated dropdown list and then click **Next**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="展台模式 - 创建帐户":::

6. <span data-ttu-id="321dc-329">在“**选择展台应用** ”页面上，选择“**Microsoft Edge**”，然后单击“ **下一步**”。</span><span class="sxs-lookup"><span data-stu-id="321dc-329">On the **Choose a kiosk app** page, select **Microsoft Edge** and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="321dc-330">这仅适用于 Microsoft Edge Dev、Beta、Stable 渠道。</span><span class="sxs-lookup"><span data-stu-id="321dc-330">This only applies to Microsoft Edge Dev, Beta, and Stable channels.</span></span>

     :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5c-choose-a-kiosk-app.png" alt-text="展台模式显示 - 全屏数字签名":::

7. <span data-ttu-id="321dc-332">选择以下选项之一，了解 Microsoft Edge 在展台模式下运行时的显示方式：</span><span class="sxs-lookup"><span data-stu-id="321dc-332">Pick one of the following options for how Microsoft Edge displays when running in kiosk mode:</span></span>

   - <span data-ttu-id="321dc-333">数字/交互式标牌 - 运行 Microsoft Edge 时以全屏模式显示特定网站。</span><span class="sxs-lookup"><span data-stu-id="321dc-333">Digital/Interactive signage - Displays a specific site in full-screen mode, running Microsoft Edge.</span></span>
   - <span data-ttu-id="321dc-334">公共浏览器 - 运行 Microsoft Edge 的受限多选项卡版本。</span><span class="sxs-lookup"><span data-stu-id="321dc-334">Public browser - Runs a limited multi-tab version of Microsoft Edge.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="如何使用展台 - 全屏数字签名":::

8. <span data-ttu-id="321dc-336">选择“ **下一步**”。</span><span class="sxs-lookup"><span data-stu-id="321dc-336">Select **Next**.</span></span>
9. <span data-ttu-id="321dc-337">键入要在展台启动时加载的 URL。</span><span class="sxs-lookup"><span data-stu-id="321dc-337">Type the URL to load when the kiosk launches.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="展台模式 - 输入 URL":::

10. <span data-ttu-id="321dc-339">接受“5 分钟”的空闲时间默认值或提供你自己的值。</span><span class="sxs-lookup"><span data-stu-id="321dc-339">Accept the default value of 5 minutes for the idle time or provide a value of your own.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="展台模式 - 输入空闲时间":::

11. <span data-ttu-id="321dc-341">单击“ **下一步**”。</span><span class="sxs-lookup"><span data-stu-id="321dc-341">Click **Next**.</span></span>
12. <span data-ttu-id="321dc-342">关闭“ **设置** ”窗口，保存并应用你的选择。</span><span class="sxs-lookup"><span data-stu-id="321dc-342">Close the **Settings** window to save and apply your choices.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="展台模式 - 完成设置":::

13. <span data-ttu-id="321dc-344">从展台设备注销，然后使用本地展台帐户登录以验证配置。</span><span class="sxs-lookup"><span data-stu-id="321dc-344">Sign out from the kiosk device and sign in with the local kiosk account to validate the configuration.</span></span>

## <a name="functional-limitations"></a><span data-ttu-id="321dc-345">功能限制</span><span class="sxs-lookup"><span data-stu-id="321dc-345">Functional limitations</span></span>

<span data-ttu-id="321dc-346">随着展台模式此预览版的发布，我们将继续改进产品和添加新功能。</span><span class="sxs-lookup"><span data-stu-id="321dc-346">With the release of this preview version of kiosk mode we're continuing work on improving the product and adding new features.</span></span>

<span data-ttu-id="321dc-347">目前不支持以下功能，建议关闭：</span><span class="sxs-lookup"><span data-stu-id="321dc-347">We currently don't support the following features and recommend that you turn off:</span></span>

- [<span data-ttu-id="321dc-348">InPrivateModeAvailability</span><span class="sxs-lookup"><span data-stu-id="321dc-348">InPrivateModeAvailability</span></span>](./microsoft-edge-policies.md#inprivatemodeavailability)
- [<span data-ttu-id="321dc-349">IsolateOrigins</span><span class="sxs-lookup"><span data-stu-id="321dc-349">IsolateOrigins</span></span>](./microsoft-edge-policies.md#isolateorigins)
- [<span data-ttu-id="321dc-350">ManagedFavorites</span><span class="sxs-lookup"><span data-stu-id="321dc-350">ManagedFavorites</span></span>](./microsoft-edge-policies.md#managedfavorites)
- [<span data-ttu-id="321dc-351">EdgeShoppingAssistantEnabled</span><span class="sxs-lookup"><span data-stu-id="321dc-351">EdgeShoppingAssistantEnabled</span></span>](./microsoft-edge-policies.md#edgeshoppingassistantenabled)
- [<span data-ttu-id="321dc-352">EdgeCollectionsEnabled</span><span class="sxs-lookup"><span data-stu-id="321dc-352">EdgeCollectionsEnabled</span></span>](./microsoft-edge-policies.md#edgecollectionsenabled)
- [<span data-ttu-id="321dc-353">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="321dc-353">UserFeedbackAllowed</span></span>](./microsoft-edge-policies.md#userfeedbackallowed)
- [<span data-ttu-id="321dc-354">DefaultPopupsSetting</span><span class="sxs-lookup"><span data-stu-id="321dc-354">DefaultPopupsSetting</span></span>](./microsoft-edge-policies.md#defaultpopupssetting)
- [<span data-ttu-id="321dc-355">StartupBoostEnabled</span><span class="sxs-lookup"><span data-stu-id="321dc-355">StartupBoostEnabled</span></span>](./microsoft-edge-policies.md#startupboostenabled)
- [<span data-ttu-id="321dc-356">InternetExplorerIntegrationLevel</span><span class="sxs-lookup"><span data-stu-id="321dc-356">InternetExplorerIntegrationLevel</span></span>](./microsoft-edge-policies.md#internetexplorerintegrationlevel)
- [<span data-ttu-id="321dc-357">Extensions</span><span class="sxs-lookup"><span data-stu-id="321dc-357">Extensions</span></span>](./microsoft-edge-policies.md#extensions-policies)
- [<span data-ttu-id="321dc-358">BackgroundModeEnabled</span><span class="sxs-lookup"><span data-stu-id="321dc-358">BackgroundModeEnabled</span></span>](./microsoft-edge-policies.md#backgroundmodeenabled)
- [<span data-ttu-id="321dc-359">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="321dc-359">UserFeedbackAllowed</span></span>](./microsoft-edge-policies.md#userfeedbackallowed)

## <a name="see-also"></a><span data-ttu-id="321dc-360">另请参阅</span><span class="sxs-lookup"><span data-stu-id="321dc-360">See also</span></span>

- [<span data-ttu-id="321dc-361">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="321dc-361">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="321dc-362">规划 Microsoft Edge 部署</span><span class="sxs-lookup"><span data-stu-id="321dc-362">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)
- [<span data-ttu-id="321dc-363">在 Windows 桌面版中配置展台和数字签名</span><span class="sxs-lookup"><span data-stu-id="321dc-363">Configure kiosks and digital signs on Windows desktop editions</span></span>](/windows/configuration/kiosk-methods)
- [<span data-ttu-id="321dc-364">规划展台模式转换</span><span class="sxs-lookup"><span data-stu-id="321dc-364">Plan your kiosk mode transition</span></span>](microsoft-edge-kiosk-mode-transition-plan.md)
