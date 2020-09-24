---
title: 配置 Microsoft Edge 展台模式
ms.author: aguta
author: aguta
manager: srugh
ms.date: 09/22/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 配置 Microsoft Edge 展台模式
ms.openlocfilehash: d7c9df82079f8343d43ccfd312623e6e01358fa9
ms.sourcegitcommit: 858227653fc89532d1d274735f53280e27b2a8c0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "11072648"
---
# <span data-ttu-id="53d6d-103">配置 Microsoft Edge 展台模式</span><span class="sxs-lookup"><span data-stu-id="53d6d-103">Configure Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="53d6d-104">本文介绍如何配置可以试用的 Microsoft Edge 展台模式选项。</span><span class="sxs-lookup"><span data-stu-id="53d6d-104">This article describes how to configure Microsoft Edge kiosk mode options that you can pilot.</span></span> <span data-ttu-id="53d6d-105">还有一个我们要遵循的功能路线图。</span><span class="sxs-lookup"><span data-stu-id="53d6d-105">There's also a roadmap of features we are targeting.</span></span>

> [!NOTE]
> <span data-ttu-id="53d6d-106">本文适用于 Microsoft Edge 版本 87 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="53d6d-106">This article applies to Microsoft Edge version 87 or later.</span></span>

<span data-ttu-id="53d6d-107">有关旧版 Microsoft Edge 展台模式（版本 45 和更早版本）的信息，请参阅[部署 Microsoft Edge 站台模式](https://aka.ms/edgekioskmode)。</span><span class="sxs-lookup"><span data-stu-id="53d6d-107">For information about Microsoft Edge Legacy kiosk mode (version 45 and earlier) see [Deploy Microsoft Edge kiosk mode](https://aka.ms/edgekioskmode).</span></span>

## <span data-ttu-id="53d6d-108">概述</span><span class="sxs-lookup"><span data-stu-id="53d6d-108">Overview</span></span>

<span data-ttu-id="53d6d-109">Microsoft Edge 展台模式提供两种浏览器锁定体验，因此组织可以创建、管理并为其客户提供最佳体验。</span><span class="sxs-lookup"><span data-stu-id="53d6d-109">Microsoft Edge kiosk mode offers two lockdown experiences of the browser so organizations can create, manage, and provide the best experience for their customers.</span></span> <span data-ttu-id="53d6d-110">提供以下锁定体验：</span><span class="sxs-lookup"><span data-stu-id="53d6d-110">The following lockdown experiences are available:</span></span>  

- <span data-ttu-id="53d6d-111">数字/交互式标牌体验以全屏模式显示特定网站。</span><span class="sxs-lookup"><span data-stu-id="53d6d-111">The Digital/Interactive signage experience displays a specific site in full-screen mode.</span></span>
- <span data-ttu-id="53d6d-112">公开浏览体验运行 Microsoft Edge 的受限多选项卡版本。</span><span class="sxs-lookup"><span data-stu-id="53d6d-112">The public-browsing experience runs a limited multi-tab version of Microsoft Edge.</span></span>

<span data-ttu-id="53d6d-113">这两种体验都在运行 Microsoft Edge InPrivate 会话，以保护用户数据。</span><span class="sxs-lookup"><span data-stu-id="53d6d-113">Both experiences are running a Microsoft Edge InPrivate session, which protects user data.</span></span>

## <span data-ttu-id="53d6d-114">设置 Microsoft Edge 展台模式</span><span class="sxs-lookup"><span data-stu-id="53d6d-114">Set up Microsoft Edge kiosk mode</span></span>  

<span data-ttu-id="53d6d-115">现在可以使用 Microsoft Edge Canary 渠道版本 87 测试一组初始展台模式功能。</span><span class="sxs-lookup"><span data-stu-id="53d6d-115">An initial set of kiosk mode features are now available to test with Microsoft Edge Canary Channel, version 87.</span></span> <span data-ttu-id="53d6d-116">可以从 [Microsoft Edge Insider Channels](https://www.microsoftedgeinsider.com/download) 页面下载 Microsoft Edge Canary。</span><span class="sxs-lookup"><span data-stu-id="53d6d-116">You can download Microsoft Edge Canary from the [Microsoft Edge Insider Channels](https://www.microsoftedgeinsider.com/download) page.</span></span>

### <span data-ttu-id="53d6d-117">展台模式功能</span><span class="sxs-lookup"><span data-stu-id="53d6d-117">Kiosk mode features</span></span>

<span data-ttu-id="53d6d-118">提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="53d6d-118">The following features are available:</span></span>

- <span data-ttu-id="53d6d-119">InPrivate 导航。</span><span class="sxs-lookup"><span data-stu-id="53d6d-119">InPrivate navigation.</span></span> <span data-ttu-id="53d6d-120">通过在会话结束时删除浏览器数据和下载来保护用户数据。</span><span class="sxs-lookup"><span data-stu-id="53d6d-120">Protects user data by deleting browser data and downloads when the session ends.</span></span>
- <span data-ttu-id="53d6d-121">配置退出时删除下载的策略。</span><span class="sxs-lookup"><span data-stu-id="53d6d-121">Policy to configure Delete downloads on exit.</span></span>
- <span data-ttu-id="53d6d-122">在处于非活动状态特定时间段后重置用户会话。</span><span class="sxs-lookup"><span data-stu-id="53d6d-122">Reset user session after a certain period of inactivity.</span></span>
- <span data-ttu-id="53d6d-123">初始锁定功能集。</span><span class="sxs-lookup"><span data-stu-id="53d6d-123">Initial set of lockdown functionality.</span></span> <span data-ttu-id="53d6d-124">提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="53d6d-124">The following functions are available:</span></span>

  - <span data-ttu-id="53d6d-125">鼠标上下文菜单</span><span class="sxs-lookup"><span data-stu-id="53d6d-125">Mouse context menu</span></span>
  - <span data-ttu-id="53d6d-126">F12 开发人员工具</span><span class="sxs-lookup"><span data-stu-id="53d6d-126">F12 Developer Tools</span></span>
  - <span data-ttu-id="53d6d-127">F11 退出全屏（在全屏模式下）</span><span class="sxs-lookup"><span data-stu-id="53d6d-127">F11 Exit full screen (while in full screen mode)</span></span>
  - <span data-ttu-id="53d6d-128">阻止初始 *Edge://* 页面集</span><span class="sxs-lookup"><span data-stu-id="53d6d-128">Blocking of the initial set of *Edge://* pages</span></span>

> [!NOTE]
> <span data-ttu-id="53d6d-129">随着展台模式的发展，将提供更多功能。</span><span class="sxs-lookup"><span data-stu-id="53d6d-129">As kiosk mode evolves, more features will be available.</span></span>

### <span data-ttu-id="53d6d-130">使用展台模式功能</span><span class="sxs-lookup"><span data-stu-id="53d6d-130">Use kiosk mode features</span></span>

<span data-ttu-id="53d6d-131">可使用以下 Windows 10 命令行选项来调用 Microsoft Edge 展台模式功能：</span><span class="sxs-lookup"><span data-stu-id="53d6d-131">You can invoke Microsoft Edge kiosk mode features can be invoked with the following Windows 10 command line options:</span></span>

- <span data-ttu-id="53d6d-132">展台模式数字/交互式标牌：</span><span class="sxs-lookup"><span data-stu-id="53d6d-132">Kiosk mode Digital/Interactive signage:</span></span> `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen`
- <span data-ttu-id="53d6d-133">展台模式公共浏览：</span><span class="sxs-lookup"><span data-stu-id="53d6d-133">Kiosk mode public browsing:</span></span> `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing`

#### <span data-ttu-id="53d6d-134">其他命令行选项</span><span class="sxs-lookup"><span data-stu-id="53d6d-134">Additional command line options</span></span>

- `--no-first-run` <span data-ttu-id="53d6d-135">：禁用首次 Microsoft Edge 运行体验。</span><span class="sxs-lookup"><span data-stu-id="53d6d-135">: Disable the first Microsoft Edge run experience.</span></span>
- `--kiosk-idle-timeout-minutes` <span data-ttu-id="53d6d-136">：更改从上次用户活动到 Microsoft Edge 展台模式重置用户会话前的时间（以分钟为单位）。</span><span class="sxs-lookup"><span data-stu-id="53d6d-136">: Change the time (in minutes) from the last user activity before Microsoft Edge kiosk mode resets the user's session.</span></span> <span data-ttu-id="53d6d-137">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="53d6d-137">The following values are supported:</span></span>

  - <span data-ttu-id="53d6d-138">默认值</span><span class="sxs-lookup"><span data-stu-id="53d6d-138">Default values</span></span>
    - <span data-ttu-id="53d6d-139">全屏 - 已关闭</span><span class="sxs-lookup"><span data-stu-id="53d6d-139">Full screen - turned off</span></span>
    - <span data-ttu-id="53d6d-140">公共浏览 - 5 分钟</span><span class="sxs-lookup"><span data-stu-id="53d6d-140">Public browsing - 5 minutes</span></span>
  - <span data-ttu-id="53d6d-141">允许的值</span><span class="sxs-lookup"><span data-stu-id="53d6d-141">Allowed values</span></span>
    - <span data-ttu-id="53d6d-142">0 - 关闭计时器</span><span class="sxs-lookup"><span data-stu-id="53d6d-142">0 - turns off the timer</span></span>
    - <span data-ttu-id="53d6d-143">1-1440 分钟，用于在空闲计时器上重置</span><span class="sxs-lookup"><span data-stu-id="53d6d-143">1-1440 minutes for reset on idle timer</span></span>

## <span data-ttu-id="53d6d-144">设置具有分配的访问权限的展台模式</span><span class="sxs-lookup"><span data-stu-id="53d6d-144">Set up kiosk mode with assigned access</span></span>

<span data-ttu-id="53d6d-145">具有分配的访问权限的 Microsoft Edge 展台模式可用于测试最新的 [Windows 10 Insider Preview 版本](https://insider.windows.com/)（版本 20215 或更高版本）以及 [Microsoft Edge Dev 渠道](https://www.microsoftedgeinsider.com/download)版本 87.0.644 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="53d6d-145">Microsoft Edge kiosk mode with assigned access is currently available for testing with the latest [Windows 10 Insider Preview Build](https://insider.windows.com/), version 20215 or higher, and with the [Microsoft Edge Dev Channel](https://www.microsoftedgeinsider.com/download), version 87.0.644 or higher.</span></span>

**<span data-ttu-id="53d6d-146">如何获得 Windows 预览体验成员预览版？</span><span class="sxs-lookup"><span data-stu-id="53d6d-146">How do I get the Windows Insiders preview?</span></span>**

<span data-ttu-id="53d6d-147">若要在电脑上安装 Windows 10 Insider Preview 内部版本，请按照[开始使用 Windows 10 Insider Preview 版本](https://docs.microsoft.com/windows-insider/get-started)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="53d6d-147">To install a Windows 10 Insider Preview Build on a PC, follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>

### <span data-ttu-id="53d6d-148">使用 Windows 设置进行配置</span><span class="sxs-lookup"><span data-stu-id="53d6d-148">Configure using Windows Settings</span></span>

<span data-ttu-id="53d6d-149">Windows 设置是设置一个或两个单应用展台设备的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="53d6d-149">Windows Settings is the simplest way to set up one or two single-app kiosk devices.</span></span> <span data-ttu-id="53d6d-150">使用以下步骤设置单应用展台计算机。</span><span class="sxs-lookup"><span data-stu-id="53d6d-150">Use the following steps to set up a single-app kiosk computer.</span></span>

1. <span data-ttu-id="53d6d-151">安装最新的 Windows 10 Insider Preview 版本 20215 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="53d6d-151">Install the latest Windows 10 Insider Preview, version 20215 or higher.</span></span> <span data-ttu-id="53d6d-152">按照[开始使用 Windows 10 Insider Preview 版本](https://docs.microsoft.com/windows-insider/get-started)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="53d6d-152">Follow the instructions in [Getting started with Windows 10 Insider Preview Builds](https://docs.microsoft.com/windows-insider/get-started).</span></span>
2. <span data-ttu-id="53d6d-153">安装最新版本的 [Microsoft Edge Dev 渠道](https://www.microsoftedgeinsider.com/download)，即 87.0.644 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="53d6d-153">Install the latest version of [Microsoft Edge Dev channel](https://www.microsoftedgeinsider.com/download), 87.0.644 or higher.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="53d6d-154">由于需要设备级安装，因此只支持非 Canary 渠道。</span><span class="sxs-lookup"><span data-stu-id="53d6d-154">Because a device level installation is required, only a non-Canary channel is supported.</span></span>

3. <span data-ttu-id="53d6d-155">在展台计算机上，打开“Windows 设置”，然后在搜索字段中键入“展台”。</span><span class="sxs-lookup"><span data-stu-id="53d6d-155">On the kiosk computer, open Windows Settings, and type "kiosk" in the search field.</span></span> <span data-ttu-id="53d6d-156">选择“ **设置展台（分配的访问权限）**”（如下一个屏幕截图所示），以打开用于创建展台的对话框。</span><span class="sxs-lookup"><span data-stu-id="53d6d-156">Select  **Set up a kiosk (assigned access)**, shown in the next screenshot to open the dialog for creating the kiosk.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="设置具有分配的访问权限的展台":::

4. <span data-ttu-id="53d6d-158">在“**设置展台** ”页面上，单击“ **入门**”。</span><span class="sxs-lookup"><span data-stu-id="53d6d-158">On the **Set up a kiosk** page, click **Get started**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="展台页面 - 入门":::

5. <span data-ttu-id="53d6d-160">键入名称以创建新的展台帐户，或从填充的下拉列表中选择现有帐户，然后单击“ **下一步**”。</span><span class="sxs-lookup"><span data-stu-id="53d6d-160">Type a name to create a new kiosk account or choose an existing account from the populated dropdown list and then click **Next**.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="展台模式 - 创建帐户":::

6. <span data-ttu-id="53d6d-162">在“**选择展台应用** ”页面上，选择“**Microsoft Edge**”，然后单击“ **下一步**”。</span><span class="sxs-lookup"><span data-stu-id="53d6d-162">On the **Choose a kiosk app** page, select **Microsoft Edge** and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="53d6d-163">这仅适用于 Microsoft Edge Dev、Beta 和 Stable 渠道。</span><span class="sxs-lookup"><span data-stu-id="53d6d-163">This only applies to Microsoft Edge Dev, Beta, and Stable channels.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="展台模式 - 选择应用":::

7. <span data-ttu-id="53d6d-165">选择以下选项之一，了解 Microsoft Edge 在展台模式下运行时的显示方式：</span><span class="sxs-lookup"><span data-stu-id="53d6d-165">Pick one of the following options for how Microsoft Edge displays when running in kiosk mode:</span></span>

   - <span data-ttu-id="53d6d-166">数字/交互式标牌 - 运行 Microsoft Edge 时以全屏模式显示特定网站。</span><span class="sxs-lookup"><span data-stu-id="53d6d-166">Digital/Interactive signage - Displays a specific site in full-screen mode, running Microsoft Edge.</span></span>
   - <span data-ttu-id="53d6d-167">公共浏览器 - 运行 Microsoft Edge 的受限多选项卡版本。</span><span class="sxs-lookup"><span data-stu-id="53d6d-167">Public browser - Runs a limited multi-tab version of Microsoft Edge.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="展台模式显示 - 全屏数字签名":::

8. <span data-ttu-id="53d6d-169">选择“ **下一步**”。</span><span class="sxs-lookup"><span data-stu-id="53d6d-169">Select **Next**.</span></span>
9. <span data-ttu-id="53d6d-170">键入要在展台启动时加载的 URL。</span><span class="sxs-lookup"><span data-stu-id="53d6d-170">Type the URL to load when the kiosk launches.</span></span>

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="展台模式 - 输入 URL":::

10. <span data-ttu-id="53d6d-172">接受“5 分钟”的空闲时间默认值或提供你自己的值。</span><span class="sxs-lookup"><span data-stu-id="53d6d-172">Accept the default value of 5 minutes for the idle time or provide a value of your own.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="展台模式 - 输入空闲时间":::

11. <span data-ttu-id="53d6d-174">单击“ **下一步**”。</span><span class="sxs-lookup"><span data-stu-id="53d6d-174">Click **Next**.</span></span>
12. <span data-ttu-id="53d6d-175">关闭“ **设置** ”窗口，保存并应用你的选择。</span><span class="sxs-lookup"><span data-stu-id="53d6d-175">Close the **Settings** window to save and apply your choices.</span></span>

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="展台模式 - 完成设置":::

13. <span data-ttu-id="53d6d-177">从展台设备注销并使用本地展台帐户登录，以验证配置情况。</span><span class="sxs-lookup"><span data-stu-id="53d6d-177">Sign off from the kiosk device and sign in with the local kiosk account to validate the configuration.</span></span>

## <span data-ttu-id="53d6d-178">功能限制</span><span class="sxs-lookup"><span data-stu-id="53d6d-178">Functional limitations</span></span>

<span data-ttu-id="53d6d-179">随着展台模式此预览版的发布，我们将继续改进产品和添加新功能。</span><span class="sxs-lookup"><span data-stu-id="53d6d-179">With the release of this preview version of kiosk mode we're continuing work on improving the product and adding new features.</span></span>

<span data-ttu-id="53d6d-180">尽管展台模式当前不支持以下功能，但我们正努力开发以下功能：</span><span class="sxs-lookup"><span data-stu-id="53d6d-180">Although kiosk mode doesn't currently support the following functionality, work is underway on the following features:</span></span>

- <span data-ttu-id="53d6d-181">收藏</span><span class="sxs-lookup"><span data-stu-id="53d6d-181">Collections</span></span>
- <span data-ttu-id="53d6d-182">Extensions</span><span class="sxs-lookup"><span data-stu-id="53d6d-182">Extensions</span></span>
- <span data-ttu-id="53d6d-183">Internet Explorer 模式</span><span class="sxs-lookup"><span data-stu-id="53d6d-183">Internet Explorer mode</span></span>
- <span data-ttu-id="53d6d-184">Windows Defender 应用程序保护 (WDAG)</span><span class="sxs-lookup"><span data-stu-id="53d6d-184">Windows Defender Application Guard (WDAG)</span></span>

## <span data-ttu-id="53d6d-185">路线图</span><span class="sxs-lookup"><span data-stu-id="53d6d-185">Roadmap</span></span>

### <span data-ttu-id="53d6d-186">今年晚些时候 (2020)</span><span class="sxs-lookup"><span data-stu-id="53d6d-186">Later this year (2020)</span></span>

<span data-ttu-id="53d6d-187">我们将添加以下功能：</span><span class="sxs-lookup"><span data-stu-id="53d6d-187">We'll add the following features:</span></span>

- <span data-ttu-id="53d6d-188">“结束会话”按钮</span><span class="sxs-lookup"><span data-stu-id="53d6d-188">End session button</span></span>
- <span data-ttu-id="53d6d-189">只读 URL 地址栏</span><span class="sxs-lookup"><span data-stu-id="53d6d-189">Read only URL address bar</span></span>  
  - <span data-ttu-id="53d6d-190">可通过组策略配置</span><span class="sxs-lookup"><span data-stu-id="53d6d-190">Configurable with group policy</span></span>
  - <span data-ttu-id="53d6d-191">启用后，将阻止用户编辑地址栏 URL 以尝试导航到其他页面。</span><span class="sxs-lookup"><span data-stu-id="53d6d-191">When enabled, users will be prevented from editing the address bar URL to try navigating away to another page.</span></span>

- <span data-ttu-id="53d6d-192">更多锁定功能：</span><span class="sxs-lookup"><span data-stu-id="53d6d-192">More lockdown functions:</span></span>

  - <span data-ttu-id="53d6d-193">其他加速器将被阻止（例如 CTRL+N）</span><span class="sxs-lookup"><span data-stu-id="53d6d-193">Additional accelerators will be blocked (for example, CTRL+N)</span></span>
  - <span data-ttu-id="53d6d-194">“…”设置菜单将仅启用所需选项（例如“打印”、“帮助”、“反馈”和“大声朗读”）</span><span class="sxs-lookup"><span data-stu-id="53d6d-194">The "…" settings menu will enable only required options (for example, Print, Help,  Feedback, and Read aloud)</span></span>
  - <span data-ttu-id="53d6d-195">其他 *edge://* 页面锁定（例如 *edge://settings*）</span><span class="sxs-lookup"><span data-stu-id="53d6d-195">Additional *edge://* pages lockdown (for example, *edge://settings*)</span></span>
  - <span data-ttu-id="53d6d-196">配置打印选项 UI</span><span class="sxs-lookup"><span data-stu-id="53d6d-196">Configure print options UI</span></span>
  - <span data-ttu-id="53d6d-197">仅将文件资源管理器限制为下载文件夹。</span><span class="sxs-lookup"><span data-stu-id="53d6d-197">Limiting file explorer to the download folder only.</span></span>

### <span data-ttu-id="53d6d-198">2021 年初</span><span class="sxs-lookup"><span data-stu-id="53d6d-198">In early 2021</span></span>

<span data-ttu-id="53d6d-199">我们将添加以下支持和功能：</span><span class="sxs-lookup"><span data-stu-id="53d6d-199">We'll add the following support and features:</span></span>

- <span data-ttu-id="53d6d-200">正式发布在 Windows 上具有分配的访问权限单应用的 Microsoft Edge 展台模式。</span><span class="sxs-lookup"><span data-stu-id="53d6d-200">General availability of Microsoft Edge kiosk mode with assigned access single app on Windows.</span></span>
- <span data-ttu-id="53d6d-201">用于与 Microsoft Edge 旧版进行奇偶校验的其他功能。</span><span class="sxs-lookup"><span data-stu-id="53d6d-201">Additional features for parity with Microsoft Edge Legacy.</span></span>
- <span data-ttu-id="53d6d-202">与 Intune 集成，以使用展台模式配置文件 UX 配置设备。</span><span class="sxs-lookup"><span data-stu-id="53d6d-202">Integration with Intune to configure devices using kiosk mode profile UX.</span></span>

## <span data-ttu-id="53d6d-203">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53d6d-203">See also</span></span>

- [<span data-ttu-id="53d6d-204">在 Windows 桌面版中配置展台和数字签名</span><span class="sxs-lookup"><span data-stu-id="53d6d-204">Configure kiosks and digital signs on Windows desktop editions</span></span>](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [<span data-ttu-id="53d6d-205">部署旧版 Microsoft Edge 展台模式</span><span class="sxs-lookup"><span data-stu-id="53d6d-205">Deploy Microsoft Edge Legacy kiosk mode</span></span>](https://aka.ms/edgekioskmode) 
- [<span data-ttu-id="53d6d-206">规划 Microsoft Edge 部署</span><span class="sxs-lookup"><span data-stu-id="53d6d-206">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)
- [<span data-ttu-id="53d6d-207">Microsoft Edge Enterprise 着陆页</span><span class="sxs-lookup"><span data-stu-id="53d6d-207">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)