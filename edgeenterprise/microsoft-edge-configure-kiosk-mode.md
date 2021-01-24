---
title: 配置 Microsoft Edge 展台模式
ms.author: aguta
author: aguta
manager: srugh
ms.date: 01/21/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 配置 Microsoft Edge 展台模式
ms.openlocfilehash: be353a0e13e9234de40296a2e8dcc31b1b800f52
ms.sourcegitcommit: 8a88fd38bdb5e132e89bf17dd2b5fb72f5d1b4b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "11297468"
---
# <span data-ttu-id="2c8d6-103">配置 Microsoft Edge 展台模式</span><span class="sxs-lookup"><span data-stu-id="2c8d6-103">Configure Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="2c8d6-104">本文介绍如何配置可以试用的 Microsoft Edge 展台模式选项。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-104">This article describes how to configure Microsoft Edge kiosk mode options that you can pilot.</span></span> <span data-ttu-id="2c8d6-105">还有一个在我们目标之中的功能路线图。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-105">There's also a roadmap of features we're targeting.</span></span>

> [!NOTE]
> <span data-ttu-id="2c8d6-106">本文适用于 Microsoft Edge 版本 87 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-106">This article applies to Microsoft Edge version 87 or later.</span></span>

## <span data-ttu-id="2c8d6-107">概述</span><span class="sxs-lookup"><span data-stu-id="2c8d6-107">Overview</span></span>

<span data-ttu-id="2c8d6-108">Microsoft Edge 展台模式提供两种浏览器锁定体验，因此组织可以创建、管理并为其客户提供最佳体验。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-108">Microsoft Edge kiosk mode offers two lockdown experiences of the browser so organizations can create, manage, and provide the best experience for their customers.</span></span> <span data-ttu-id="2c8d6-109">提供以下锁定体验：</span><span class="sxs-lookup"><span data-stu-id="2c8d6-109">The following lockdown experiences are available:</span></span>  

- <span data-ttu-id="2c8d6-110">**数字/交互式标志** 体验 - 以全屏模式显示特定网站。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-110">**Digital/Interactive Signage** experience - Displays a specific site in full-screen mode.</span></span>
- <span data-ttu-id="2c8d6-111">**公共浏览** 体验 - 运行 Microsoft Edge 的有限多选项卡版本。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-111">**Public-Browsing** experience - Runs a limited multi-tab version of Microsoft Edge.</span></span>

<span data-ttu-id="2c8d6-112">这两种体验都在运行 Microsoft Edge InPrivate 会话，以保护用户数据。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-112">Both experiences are running a Microsoft Edge InPrivate session, which protects user data.</span></span>

## <span data-ttu-id="2c8d6-113">设置 Microsoft Edge 展台模式</span><span class="sxs-lookup"><span data-stu-id="2c8d6-113">Set up Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="2c8d6-114">可以使用 Microsoft Edge Stable 渠道版本 87 测试一组初始展台模式功能。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-114">An initial set of kiosk mode features is available to test with Microsoft Edge Stable Channel, version 87.</span></span> <span data-ttu-id="2c8d6-115">你可以从 [Microsoft Edge (Official Stable 渠道)](https://www.microsoft.com/edge)下载。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-115">You can download the latest version from [Microsoft Edge (Official Stable Channel)](https://www.microsoft.com/edge).</span></span>

### <span data-ttu-id="2c8d6-116">展台模式支持的功能</span><span class="sxs-lookup"><span data-stu-id="2c8d6-116">Kiosk mode supported features</span></span>

<span data-ttu-id="2c8d6-117">下表列出了展台模式支持的功能。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-117">The following table lists the features supported by kiosk mode.</span></span>

|<span data-ttu-id="2c8d6-118">功能</span><span class="sxs-lookup"><span data-stu-id="2c8d6-118">Feature</span></span>|<span data-ttu-id="2c8d6-119">数字\交互式标志</span><span class="sxs-lookup"><span data-stu-id="2c8d6-119">Digital\Interactive Signage</span></span>|<span data-ttu-id="2c8d6-120">公共浏览</span><span class="sxs-lookup"><span data-stu-id="2c8d6-120">Public browsing</span></span>|<span data-ttu-id="2c8d6-121">适用于 Microsoft Edge 版本 (及更高版本)</span><span class="sxs-lookup"><span data-stu-id="2c8d6-121">Available with Microsoft Edge version (and higher)</span></span>|
|-|-|-|-|
|<span data-ttu-id="2c8d6-122">InPrivate 导航</span><span class="sxs-lookup"><span data-stu-id="2c8d6-122">InPrivate Navigation</span></span>|<span data-ttu-id="2c8d6-123">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-123">Y</span></span>|<span data-ttu-id="2c8d6-124">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-124">Y</span></span>|<span data-ttu-id="2c8d6-125">87</span><span class="sxs-lookup"><span data-stu-id="2c8d6-125">87</span></span>|
|<span data-ttu-id="2c8d6-126">在处于非活动状态时重置</span><span class="sxs-lookup"><span data-stu-id="2c8d6-126">Reset on inactivity</span></span>|<span data-ttu-id="2c8d6-127">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-127">Y</span></span>|<span data-ttu-id="2c8d6-128">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-128">Y</span></span>|<span data-ttu-id="2c8d6-129">87</span><span class="sxs-lookup"><span data-stu-id="2c8d6-129">87</span></span>|
|<span data-ttu-id="2c8d6-130">[只读地址栏](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) (策略)</span><span class="sxs-lookup"><span data-stu-id="2c8d6-130">[Read only address bar](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) (policy)</span></span> |<span data-ttu-id="2c8d6-131">N</span><span class="sxs-lookup"><span data-stu-id="2c8d6-131">N</span></span>|<span data-ttu-id="2c8d6-132">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-132">Y</span></span> |<span data-ttu-id="2c8d6-133">87</span><span class="sxs-lookup"><span data-stu-id="2c8d6-133">87</span></span>|
|<span data-ttu-id="2c8d6-134">[退出时删除下载](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit) (策略)</span><span class="sxs-lookup"><span data-stu-id="2c8d6-134">[Delete downloads on exit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit) (policy)</span></span>  | <span data-ttu-id="2c8d6-135">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-135">Y</span></span>|<span data-ttu-id="2c8d6-136">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-136">Y</span></span> |<span data-ttu-id="2c8d6-137">87</span><span class="sxs-lookup"><span data-stu-id="2c8d6-137">87</span></span>|
|<span data-ttu-id="2c8d6-138">已阻止 F11 (进入/退出全屏)</span><span class="sxs-lookup"><span data-stu-id="2c8d6-138">F11 blocked (enter/exit full-screen)</span></span> | <span data-ttu-id="2c8d6-139">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-139">Y</span></span> | <span data-ttu-id="2c8d6-140">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-140">Y</span></span> | <span data-ttu-id="2c8d6-141">87</span><span class="sxs-lookup"><span data-stu-id="2c8d6-141">87</span></span> |
|<span data-ttu-id="2c8d6-142">已阻止F12 (启动开发人员工具)</span><span class="sxs-lookup"><span data-stu-id="2c8d6-142">F12 blocked (launch Developer Tools)</span></span> | <span data-ttu-id="2c8d6-143">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-143">Y</span></span> | <span data-ttu-id="2c8d6-144">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-144">Y</span></span> | <span data-ttu-id="2c8d6-145">87</span><span class="sxs-lookup"><span data-stu-id="2c8d6-145">87</span></span> |
| <span data-ttu-id="2c8d6-146">多选项卡支持</span><span class="sxs-lookup"><span data-stu-id="2c8d6-146">Multi tab support</span></span> | <span data-ttu-id="2c8d6-147">N</span><span class="sxs-lookup"><span data-stu-id="2c8d6-147">N</span></span>| <span data-ttu-id="2c8d6-148">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-148">Y</span></span>| <span data-ttu-id="2c8d6-149">87</span><span class="sxs-lookup"><span data-stu-id="2c8d6-149">87</span></span>|
|<span data-ttu-id="2c8d6-150">“结束会话”按钮</span><span class="sxs-lookup"><span data-stu-id="2c8d6-150">End session button</span></span> | <span data-ttu-id="2c8d6-151">N</span><span class="sxs-lookup"><span data-stu-id="2c8d6-151">N</span></span>| <span data-ttu-id="2c8d6-152">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-152">Y</span></span>| <span data-ttu-id="2c8d6-153">88</span><span class="sxs-lookup"><span data-stu-id="2c8d6-153">88</span></span>|
|<span data-ttu-id="2c8d6-154">所有内部 Microsoft Edge URL 已将被阻止，除了*edge://downloads*和*edge://print*</span><span class="sxs-lookup"><span data-stu-id="2c8d6-154">All internal Microsoft Edge URLs are blocked, except for *edge://downloads* and *edge://print*</span></span> |<span data-ttu-id="2c8d6-155">N</span><span class="sxs-lookup"><span data-stu-id="2c8d6-155">N</span></span>|<span data-ttu-id="2c8d6-156">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-156">Y</span></span>|<span data-ttu-id="2c8d6-157">88</span><span class="sxs-lookup"><span data-stu-id="2c8d6-157">88</span></span>|
| <span data-ttu-id="2c8d6-158">已阻止 Ctrl+N (打开一个新窗口)</span><span class="sxs-lookup"><span data-stu-id="2c8d6-158">CTRL+N blocked (open a new window)</span></span> | <span data-ttu-id="2c8d6-159">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-159">Y</span></span> | <span data-ttu-id="2c8d6-160">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-160">Y</span></span> | <span data-ttu-id="2c8d6-161">89</span><span class="sxs-lookup"><span data-stu-id="2c8d6-161">89</span></span> |
| <span data-ttu-id="2c8d6-162">已阻止 Ctrl+T (打开新选项卡)</span><span class="sxs-lookup"><span data-stu-id="2c8d6-162">CTRL+T blocked (open new tab)</span></span> | <span data-ttu-id="2c8d6-163">N</span><span class="sxs-lookup"><span data-stu-id="2c8d6-163">N</span></span> | <span data-ttu-id="2c8d6-164">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-164">Y</span></span> | <span data-ttu-id="2c8d6-165">89</span><span class="sxs-lookup"><span data-stu-id="2c8d6-165">89</span></span> |
|<span data-ttu-id="2c8d6-166">设置和更多 (...) 将仅显示所需的选项</span><span class="sxs-lookup"><span data-stu-id="2c8d6-166">Settings and more (...) will display only the required options</span></span>  |<span data-ttu-id="2c8d6-167">N</span><span class="sxs-lookup"><span data-stu-id="2c8d6-167">N</span></span> |<span data-ttu-id="2c8d6-168">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-168">Y</span></span> |<span data-ttu-id="2c8d6-169">89</span><span class="sxs-lookup"><span data-stu-id="2c8d6-169">89</span></span> |

> [!NOTE]
> <span data-ttu-id="2c8d6-170">随着展台模式的发展，将提供更多功能。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-170">As kiosk mode evolves, more features will be available.</span></span>

## <span data-ttu-id="2c8d6-171">使用展台模式功能</span><span class="sxs-lookup"><span data-stu-id="2c8d6-171">Use kiosk mode features</span></span>

<span data-ttu-id="2c8d6-172">可通过以下 Windows 10 命令行选项调用 Microsoft Edge 展台模式功能：</span><span class="sxs-lookup"><span data-stu-id="2c8d6-172">Microsoft Edge kiosk mode features can be invoked with the following Windows 10 command line options:</span></span>

- <span data-ttu-id="2c8d6-173">展台模式数字/交互式标牌：</span><span class="sxs-lookup"><span data-stu-id="2c8d6-173">Kiosk mode Digital/Interactive signage:</span></span> `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen`
- <span data-ttu-id="2c8d6-174">展台模式公共浏览：</span><span class="sxs-lookup"><span data-stu-id="2c8d6-174">Kiosk mode public browsing:</span></span> `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing`

### <span data-ttu-id="2c8d6-175">其他命令行选项</span><span class="sxs-lookup"><span data-stu-id="2c8d6-175">Additional command line options</span></span>

- `--no-first-run` <span data-ttu-id="2c8d6-176">：禁用首次 Microsoft Edge 运行体验。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-176">: Disable the first Microsoft Edge run experience.</span></span>
- `--kiosk-idle-timeout-minutes` <span data-ttu-id="2c8d6-177">：更改从上次用户活动到 Microsoft Edge 展台模式重置用户会话前的时间（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-177">: Change the time (in minutes) from the last user activity before Microsoft Edge kiosk mode resets the user's session.</span></span> <span data-ttu-id="2c8d6-178">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="2c8d6-178">The following values are supported:</span></span>

  - <span data-ttu-id="2c8d6-179">默认值</span><span class="sxs-lookup"><span data-stu-id="2c8d6-179">Default values</span></span>
    - <span data-ttu-id="2c8d6-180">全屏 - 已关闭</span><span class="sxs-lookup"><span data-stu-id="2c8d6-180">Full screen - turned off</span></span>
    - <span data-ttu-id="2c8d6-181">公共浏览 - 5 分钟</span><span class="sxs-lookup"><span data-stu-id="2c8d6-181">Public browsing - 5 minutes</span></span>
  - <span data-ttu-id="2c8d6-182">允许的值</span><span class="sxs-lookup"><span data-stu-id="2c8d6-182">Allowed values</span></span>
    - <span data-ttu-id="2c8d6-183">0 - 关闭计时器</span><span class="sxs-lookup"><span data-stu-id="2c8d6-183">0 - turns off the timer</span></span>
    - <span data-ttu-id="2c8d6-184">1-1440 分钟，用于在空闲计时器上重置</span><span class="sxs-lookup"><span data-stu-id="2c8d6-184">1-1440 minutes for reset on idle timer</span></span>

## <span data-ttu-id="2c8d6-185">展台模式的支持策略</span><span class="sxs-lookup"><span data-stu-id="2c8d6-185">Support policies for kiosk mode</span></span>

<span data-ttu-id="2c8d6-186">使用下表中列出的任何 Microsoft Edge 策略增强所配置的 Microsoft Edge 展台模式类型的展台体验。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-186">Use any of the Microsoft Edge policies listed in the following table to enhance the kiosk experience for the Microsoft Edge kiosk mode type you configure.</span></span> <span data-ttu-id="2c8d6-187">若要了解有关这些策略的信息，请参阅 [Microsoft Edge – 浏览器策略参考](https://docs.microsoft.com/deployedge/microsoft-edge-policies)。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-187">To learn more about these policies, see [Microsoft Edge – Browser policy reference](https://docs.microsoft.com/deployedge/microsoft-edge-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="2c8d6-188">策略配置不限于下表中列出的策略，但应测试其他策略以确保展台模式功能不会受到负面影响。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-188">Policy configuration isn't limited to the policies listed in the following table, however additional policies should be tested to ensure that kiosk mode functionality isn't negatively affected.</span></span>

|<span data-ttu-id="2c8d6-189">组策略</span><span class="sxs-lookup"><span data-stu-id="2c8d6-189">Group policy</span></span>|<span data-ttu-id="2c8d6-190">数字\交互式标志</span><span class="sxs-lookup"><span data-stu-id="2c8d6-190">Digital\Interactive signage</span></span>|<span data-ttu-id="2c8d6-191">公共浏览单应用</span><span class="sxs-lookup"><span data-stu-id="2c8d6-191">Public browsing single-app</span></span>|
|--|--|--|
|[<span data-ttu-id="2c8d6-192">打印</span><span class="sxs-lookup"><span data-stu-id="2c8d6-192">Printing</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printing-policies) | <span data-ttu-id="2c8d6-193">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-193">Y</span></span>|<span data-ttu-id="2c8d6-194">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-194">Y</span></span> |
|[<span data-ttu-id="2c8d6-195">HomePageLocation</span><span class="sxs-lookup"><span data-stu-id="2c8d6-195">HomePageLocation</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#homepagelocation) |<span data-ttu-id="2c8d6-196">N</span><span class="sxs-lookup"><span data-stu-id="2c8d6-196">N</span></span> | <span data-ttu-id="2c8d6-197">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-197">Y</span></span>|
|[<span data-ttu-id="2c8d6-198">ShowHomeButton</span><span class="sxs-lookup"><span data-stu-id="2c8d6-198">ShowHomeButton</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#showhomebutton) |<span data-ttu-id="2c8d6-199">N</span><span class="sxs-lookup"><span data-stu-id="2c8d6-199">N</span></span> | <span data-ttu-id="2c8d6-200">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-200">Y</span></span>|
|[<span data-ttu-id="2c8d6-201">NewTabPageLocation</span><span class="sxs-lookup"><span data-stu-id="2c8d6-201">NewTabPageLocation</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagelocation) |<span data-ttu-id="2c8d6-202">N</span><span class="sxs-lookup"><span data-stu-id="2c8d6-202">N</span></span> |<span data-ttu-id="2c8d6-203">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-203">Y</span></span> |
|[<span data-ttu-id="2c8d6-204">FavoritesBarEnabled</span><span class="sxs-lookup"><span data-stu-id="2c8d6-204">FavoritesBarEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#favoritesbarenabled) |<span data-ttu-id="2c8d6-205">N</span><span class="sxs-lookup"><span data-stu-id="2c8d6-205">N</span></span> |<span data-ttu-id="2c8d6-206">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-206">Y</span></span> |
|[<span data-ttu-id="2c8d6-207">URLAllowlist</span><span class="sxs-lookup"><span data-stu-id="2c8d6-207">URLAllowlist</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlallowlist) |<span data-ttu-id="2c8d6-208">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-208">Y</span></span> |<span data-ttu-id="2c8d6-209">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-209">Y</span></span> |
|[<span data-ttu-id="2c8d6-210">URLBlocklist</span><span class="sxs-lookup"><span data-stu-id="2c8d6-210">URLBlocklist</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlblocklist) |<span data-ttu-id="2c8d6-211">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-211">Y</span></span> | <span data-ttu-id="2c8d6-212">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-212">Y</span></span>|
|[<span data-ttu-id="2c8d6-213">ManagedSearchEngines</span><span class="sxs-lookup"><span data-stu-id="2c8d6-213">ManagedSearchEngines</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#managedsearchengines) |<span data-ttu-id="2c8d6-214">N</span><span class="sxs-lookup"><span data-stu-id="2c8d6-214">N</span></span> | <span data-ttu-id="2c8d6-215">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-215">Y</span></span>|
|[<span data-ttu-id="2c8d6-216">UserFeedbackAllowed</span><span class="sxs-lookup"><span data-stu-id="2c8d6-216">UserFeedbackAllowed</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#userfeedbackallowed) |<span data-ttu-id="2c8d6-217">N</span><span class="sxs-lookup"><span data-stu-id="2c8d6-217">N</span></span> | <span data-ttu-id="2c8d6-218">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-218">Y</span></span>|
|[<span data-ttu-id="2c8d6-219">VerticalTabsAllowed</span><span class="sxs-lookup"><span data-stu-id="2c8d6-219">VerticalTabsAllowed</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#verticaltabsallowed) | <span data-ttu-id="2c8d6-220">N</span><span class="sxs-lookup"><span data-stu-id="2c8d6-220">N</span></span>|<span data-ttu-id="2c8d6-221">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-221">Y</span></span> |
|[<span data-ttu-id="2c8d6-222">SmartScreen 设置</span><span class="sxs-lookup"><span data-stu-id="2c8d6-222">SmartScreen settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#smartscreen-settings-policies) |<span data-ttu-id="2c8d6-223">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-223">Y</span></span> |<span data-ttu-id="2c8d6-224">Y</span><span class="sxs-lookup"><span data-stu-id="2c8d6-224">Y</span></span> |

## <span data-ttu-id="2c8d6-225">Microsoft Edge 与指派访问</span><span class="sxs-lookup"><span data-stu-id="2c8d6-225">Microsoft Edge with assigned access</span></span>

### <span data-ttu-id="2c8d6-226">单应用展台</span><span class="sxs-lookup"><span data-stu-id="2c8d6-226">Single app kiosk</span></span>

<span data-ttu-id="2c8d6-227">Microsoft Edge 当前支持具有以下锁定体验的单应用分配访问权限的相同 Microsoft Edge 旧版展台模式类型的子集：数字/交互式标志和公共浏览。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-227">Microsoft Edge currently supports a subset of the same Microsoft Edge Legacy kiosk mode types for single-app assigned access with the following lockdown experiences: Digital/Interactive signage, and Public-browsing.</span></span>  

<span data-ttu-id="2c8d6-228">具有分配的访问权限的展台模式可用于测试最新的  [Windows 10 Insider Preview 版本](https://insider.windows.com/)（版本 20215 或更高版本）以及  [Microsoft Edge Dev 渠道](https://www.microsoftedgeinsider.com/download)版本 87.0.644.4 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-228">Kiosk mode with assigned access is currently available for testing with the latest [Windows 10 Insider Preview Build](https://insider.windows.com/), version 20215 or higher, and with the [Microsoft Edge Dev Channel](https://www.microsoftedgeinsider.com/download), version 87.0.644.4 or higher.</span></span>

**<span data-ttu-id="2c8d6-229">如何获得 Windows 预览体验成员预览版？</span><span class="sxs-lookup"><span data-stu-id="2c8d6-229">How do I get the Windows Insiders preview?</span></span>**

<span data-ttu-id="2c8d6-230">若要在电脑上安装 Windows 10 Insider Preview 内部版本，请按照 [开始使用 Windows 10 Insider Preview 版本](https://docs.microsoft.com/windows-insider/get-started)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-230">To install a Windows 10 Insider Preview Build on a PC, follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>

### <span data-ttu-id="2c8d6-231">多应用展台。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-231">Multi-app kiosk</span></span>

<span data-ttu-id="2c8d6-232">可用 Windows 10 上的[多应用指派访问](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)（相当于旧版 Microsoft Edge 的“普通浏览”展台模式类型）运行 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-232">Microsoft Edge can be run with [multi-app assigned access](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) on Windows 10, which is the equivalent of Microsoft Edge Legacy "Normal browsing" kiosk mode type.</span></span> <span data-ttu-id="2c8d6-233">若要使用多应用分配的访问权限配置 Microsoft Edge，请按照有关[如何设置多应用展台](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-233">To configure Microsoft Edge with multi-app assigned access, follow the instructions on how to [Set up a multi-app kiosk](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps).</span></span> <span data-ttu-id="2c8d6-234">（Microsoft Edge Stable 渠道的 AUMID 为 **MSEdge**）。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-234">(The AUMID for the Microsoft Edge Stable channel is **MSEdge**).</span></span>

<span data-ttu-id="2c8d6-235">将 Microsoft Edge 与多应用分配的访问权限一同使用时，可以将 Microsoft Edge 展台配置为使用 [Microsoft Edge 浏览器策略](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies)配置浏览体验，以满足你的独特要求。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-235">When using Microsoft Edge with multi-app assigned access, you can configure Microsoft Edge kiosk to use the[Microsoft Edge browser policies](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies) to configure the browsing experience to meet your unique requirements.</span></span>

### <span data-ttu-id="2c8d6-236">使用 Windows 设置进行配置</span><span class="sxs-lookup"><span data-stu-id="2c8d6-236">Configure using Windows Settings</span></span>

<span data-ttu-id="2c8d6-237">Windows 设置是设置一个或两个单应用展台设备的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-237">Windows Settings is the simplest way to set up one or two single-app kiosk devices.</span></span> <span data-ttu-id="2c8d6-238">使用以下步骤设置单应用展台计算机。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-238">Use the following steps to set up a single-app kiosk computer.</span></span>

1. <span data-ttu-id="2c8d6-239">安装最新的 Windows 10 Insider Preview 版本 20215 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-239">Install the latest Windows 10 Insider Preview, version 20215 or higher.</span></span> <span data-ttu-id="2c8d6-240">按照[开始使用 Windows 10 Insider Preview 版本](https://docs.microsoft.com/windows-insider/get-started)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-240">Follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>
2. <span data-ttu-id="2c8d6-241">安装最新版本的 [Microsoft Edge Stable 渠道版本](https://www.microsoft.com/edge)的 87 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-241">Install the latest version of [Microsoft Edge Stable channel](https://www.microsoft.com/edge), version 87 or higher.</span></span>  <span data-ttu-id="2c8d6-242">若要测试最新功能，可以下载最新的 [Microsoft Edge 开发人员频道](https://www.microsoftedgeinsider.com/download)的 89 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-242">To test the latest features, you can download the latest [Microsoft Edge Dev channel](https://www.microsoftedgeinsider.com/download), version 89 or higher.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="2c8d6-243">由于需要设备级安装，只支持非 Canary 渠道。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-243">Because a device level installation is required, only a non-Canary channel is supported.</span></span>

3. <span data-ttu-id="2c8d6-244">在展台计算机上，打开“Windows 设置”，然后在搜索字段中键入“展台”。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-244">On the kiosk computer, open Windows Settings, and type "kiosk" in the search field.</span></span> <span data-ttu-id="2c8d6-245">选择“ **设置展台（分配的访问权限）**”（如下一个屏幕截图所示），以打开用于创建展台的对话框。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-245">Select  **Set up a kiosk (assigned access)**, shown in the next screenshot to open the dialog for creating the kiosk.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="设置具有分配的访问权限的展台":::

4. <span data-ttu-id="2c8d6-247">在“**设置展台** ”页面上，单击“ **入门**”。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-247">On the **Set up a kiosk** page, click **Get started**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="展台页面 - 入门":::

5. <span data-ttu-id="2c8d6-249">键入名称以创建新的展台帐户，或从填充的下拉列表中选择现有帐户，然后单击“ **下一步**”。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-249">Type a name to create a new kiosk account or choose an existing account from the populated dropdown list and then click **Next**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="展台模式 - 创建帐户":::

6. <span data-ttu-id="2c8d6-251">在“**选择展台应用** ”页面上，选择“**Microsoft Edge**”，然后单击“ **下一步**”。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-251">On the **Choose a kiosk app** page, select **Microsoft Edge** and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2c8d6-252">这仅适用于 Microsoft Edge Dev、Beta 和 Stable 渠道。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-252">This only applies to Microsoft Edge Dev, Beta, and Stable channels.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="展台模式 - 选择应用":::

7. <span data-ttu-id="2c8d6-254">选择以下选项之一，了解 Microsoft Edge 在展台模式下运行时的显示方式：</span><span class="sxs-lookup"><span data-stu-id="2c8d6-254">Pick one of the following options for how Microsoft Edge displays when running in kiosk mode:</span></span>

   - <span data-ttu-id="2c8d6-255">数字/交互式标牌 - 运行 Microsoft Edge 时以全屏模式显示特定网站。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-255">Digital/Interactive signage - Displays a specific site in full-screen mode, running Microsoft Edge.</span></span>
   - <span data-ttu-id="2c8d6-256">公共浏览器 - 运行 Microsoft Edge 的受限多选项卡版本。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-256">Public browser - Runs a limited multi-tab version of Microsoft Edge.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="展台模式显示 - 全屏数字签名":::

8. <span data-ttu-id="2c8d6-258">选择“ **下一步**”。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-258">Select **Next**.</span></span>
9. <span data-ttu-id="2c8d6-259">键入要在展台启动时加载的 URL。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-259">Type the URL to load when the kiosk launches.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="展台模式 - 输入 URL":::

10. <span data-ttu-id="2c8d6-261">接受“5 分钟”的空闲时间默认值或提供你自己的值。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-261">Accept the default value of 5 minutes for the idle time or provide a value of your own.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="展台模式 - 输入空闲时间":::

11. <span data-ttu-id="2c8d6-263">单击“ **下一步**”。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-263">Click **Next**.</span></span>
12. <span data-ttu-id="2c8d6-264">关闭“ **设置** ”窗口，保存并应用你的选择。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-264">Close the **Settings** window to save and apply your choices.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="展台模式 - 完成设置":::

13. <span data-ttu-id="2c8d6-266">从展台设备注销，然后使用本地展台帐户登录以验证配置。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-266">Sign out from the kiosk device and sign in with the local kiosk account to validate the configuration.</span></span>

## <span data-ttu-id="2c8d6-267">功能限制</span><span class="sxs-lookup"><span data-stu-id="2c8d6-267">Functional limitations</span></span>

<span data-ttu-id="2c8d6-268">随着展台模式此预览版的发布，我们将继续改进产品和添加新功能。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-268">With the release of this preview version of kiosk mode we're continuing work on improving the product and adding new features.</span></span>

<span data-ttu-id="2c8d6-269">建议你关闭：</span><span class="sxs-lookup"><span data-stu-id="2c8d6-269">We recommend that you turn off:</span></span>

- [<span data-ttu-id="2c8d6-270">StartupBoostEnabled</span><span class="sxs-lookup"><span data-stu-id="2c8d6-270">StartupBoostEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startupboostenabled)
- [<span data-ttu-id="2c8d6-271">InternetExplorerIntegrationLevel</span><span class="sxs-lookup"><span data-stu-id="2c8d6-271">InternetExplorerIntegrationLevel</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationlevel)
- [<span data-ttu-id="2c8d6-272">Extensions</span><span class="sxs-lookup"><span data-stu-id="2c8d6-272">Extensions</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensions-policies)
- [<span data-ttu-id="2c8d6-273">BackgroundModeEnabled</span><span class="sxs-lookup"><span data-stu-id="2c8d6-273">BackgroundModeEnabled</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)

## <span data-ttu-id="2c8d6-274">路线图</span><span class="sxs-lookup"><span data-stu-id="2c8d6-274">Roadmap</span></span>

### <span data-ttu-id="2c8d6-275">2021 年初</span><span class="sxs-lookup"><span data-stu-id="2c8d6-275">In early 2021</span></span>

<span data-ttu-id="2c8d6-276">我们将添加以下支持和功能：</span><span class="sxs-lookup"><span data-stu-id="2c8d6-276">We'll add the following support and features:</span></span>

- <span data-ttu-id="2c8d6-277">Microsoft Edge 展台模式在 Windows 10 1909 及更高版本上具有分配的访问权限单应用通用。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-277">General availability of Microsoft Edge kiosk mode with assigned access single app on Windows 10 1909 and higher.</span></span>
- <span data-ttu-id="2c8d6-278">用于与 Microsoft Edge 旧版进行奇偶校验的其他功能。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-278">Additional features for parity with Microsoft Edge Legacy.</span></span>
- <span data-ttu-id="2c8d6-279">与 Intune 集成，以使用展台模式配置文件 UX 配置设备。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-279">Integration with Intune to configure devices using kiosk mode profile UX.</span></span>
- <span data-ttu-id="2c8d6-280">其他键盘快捷方式将被阻止。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-280">Additional keyboard shortcuts will be blocked.</span></span>
- <span data-ttu-id="2c8d6-281">限制从浏览器启动其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="2c8d6-281">Restrict the launch of other applications from the browser.</span></span>

## <span data-ttu-id="2c8d6-282">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c8d6-282">See also</span></span>

- [<span data-ttu-id="2c8d6-283">在 Windows 桌面版中配置展台和数字签名</span><span class="sxs-lookup"><span data-stu-id="2c8d6-283">Configure kiosks and digital signs on Windows desktop editions</span></span>](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [<span data-ttu-id="2c8d6-284">部署旧版 Microsoft Edge 展台模式</span><span class="sxs-lookup"><span data-stu-id="2c8d6-284">Deploy Microsoft Edge Legacy kiosk mode</span></span>](https://aka.ms/edgekioskmode)
- [<span data-ttu-id="2c8d6-285">规划 Microsoft Edge 部署</span><span class="sxs-lookup"><span data-stu-id="2c8d6-285">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)
- [<span data-ttu-id="2c8d6-286">Microsoft Edge Enterprise 着陆页</span><span class="sxs-lookup"><span data-stu-id="2c8d6-286">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
