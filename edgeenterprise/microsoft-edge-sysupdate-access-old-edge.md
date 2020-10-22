---
title: 访问旧版 Microsoft Edge
ms.author: jtkim
author: dan-wesley
manager: srugh
ms.date: 08/17/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解如何访问旧版 Microsoft Edge。
ms.openlocfilehash: e4733d020f3a681ded50e5a087fe086d39362201
ms.sourcegitcommit: f7f7eb69d2298b0f9779a9fd28e3c4e297ef2e05
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125514"
---
# <span data-ttu-id="d1037-103">在安装 Microsoft Edge 的新版本后访问旧版 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d1037-103">Access Microsoft Edge Legacy after installing the new version of Microsoft Edge</span></span>

<span data-ttu-id="d1037-104">了解如何在安装 Microsoft Edge 的新版本后访问旧版 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="d1037-104">Learn how to access Microsoft Edge Legacy after installing the new version of Microsoft Edge.</span></span>

> [!NOTE]
> <span data-ttu-id="d1037-105">本文适用于 Microsoft Edge [Stable 渠道](microsoft-edge-channels.md)。</span><span class="sxs-lookup"><span data-stu-id="d1037-105">This article applies to the Microsoft Edge [Stable channel](microsoft-edge-channels.md).</span></span>

<span data-ttu-id="d1037-106">大多数组织希望将 Microsoft Edge 旧版本替换为新版本，但在某些情况下，用户需要访问这两个版本。</span><span class="sxs-lookup"><span data-stu-id="d1037-106">While most organizations will want to replace Microsoft Edge Legacy with the new version, there are some situations where users will need access to both versions.</span></span> <span data-ttu-id="d1037-107">例如：</span><span class="sxs-lookup"><span data-stu-id="d1037-107">For example:</span></span>

- <span data-ttu-id="d1037-108">有些支持人员在与用户进行互动时，用户使用的是 Microsoft Edge 的其中一个版本或两个版本。</span><span class="sxs-lookup"><span data-stu-id="d1037-108">Helpdesk and support staff who interact with users who are using either or both versions of Microsoft Edge.</span></span>
- <span data-ttu-id="d1037-109">为使用其中一个或两个版本的 Microsoft Edge 的客户提供支持的开发人员。</span><span class="sxs-lookup"><span data-stu-id="d1037-109">Developers who support customers who are using either or both versions of Microsoft Edge.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1037-110">不建议在生产中将 Microsoft Edge 旧版与新版 Microsoft Edge 并排运行。</span><span class="sxs-lookup"><span data-stu-id="d1037-110">Running Microsoft Edge Legacy side-by-side with the new version of Microsoft Edge is not recommended for use in production.</span></span> <span data-ttu-id="d1037-111">此配置只应在需要使用两个浏览器版本进行测试的特定情况下使用。</span><span class="sxs-lookup"><span data-stu-id="d1037-111">This configuration should only be used in specific cases where testing with both browser versions is required.</span></span>
>
> <span data-ttu-id="d1037-112">将于 2021 年 3 月 9 日终止对 Microsoft Edge 旧版桌面应用的支持，取而代之的是新版 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="d1037-112">The Microsoft Edge Legacy desktop app will reach end of support on March 9, 2021 in favor of the new Microsoft Edge.</span></span> <span data-ttu-id="d1037-113">这意味着在该日期之后 Microsoft Edge 旧版将不再接收安全更新。</span><span class="sxs-lookup"><span data-stu-id="d1037-113">This means that Microsoft Edge Legacy will not receive security updates after that date.</span></span> <span data-ttu-id="d1037-114">此更改适用于在 Microsoft Edge 旧版桌面应用中运行的所有体验。</span><span class="sxs-lookup"><span data-stu-id="d1037-114">This change is applicable to all experiences that run in the Microsoft Edge Legacy desktop app.</span></span> <span data-ttu-id="d1037-115">[了解详细信息](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-365-apps-say-farewell-to-internet-explorer-11-and/ba-p/1591666)。</span><span class="sxs-lookup"><span data-stu-id="d1037-115">[Learn more](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-365-apps-say-farewell-to-internet-explorer-11-and/ba-p/1591666).</span></span>

## <span data-ttu-id="d1037-116">开始之前</span><span class="sxs-lookup"><span data-stu-id="d1037-116">Before you begin</span></span>
> [!NOTE]
> <span data-ttu-id="d1037-117">从 Windows 10 版本 20H2 开始，不再包含 Microsoft Edge 旧版。</span><span class="sxs-lookup"><span data-stu-id="d1037-117">Starting with Windows 10 version 20H2 Microsoft Edge Legacy is no longer included.</span></span> <span data-ttu-id="d1037-118">从 Windows 10 该版本开始，不支持并行使用体验。</span><span class="sxs-lookup"><span data-stu-id="d1037-118">Starting with this version of Windows 10 the side-by-side experience is not supported.</span></span>

<span data-ttu-id="d1037-119">本文中的过程适用于已用最新安全更新进行更新的系统。</span><span class="sxs-lookup"><span data-stu-id="d1037-119">The procedures in this article apply to systems that have been updated with the latest security updates.</span></span> <span data-ttu-id="d1037-120">安装 Microsoft Edge 的新版本后，将隐藏旧版本（旧版 Microsoft Edge）。</span><span class="sxs-lookup"><span data-stu-id="d1037-120">When the new version of Microsoft Edge is installed, the old version (Microsoft Edge Legacy) will be hidden.</span></span> <span data-ttu-id="d1037-121">默认情况下，所有尝试启动旧版本的操作都将用户重定向到新安装的 Microsoft Edge 版本。</span><span class="sxs-lookup"><span data-stu-id="d1037-121">By default, all attempts to launch the old version will redirect the user to the newly installed version of Microsoft Edge.</span></span> <span data-ttu-id="d1037-122">本文介绍如何在安装 Microsoft Edge 后继续使用 Microsoft Edge 旧版本。</span><span class="sxs-lookup"><span data-stu-id="d1037-122">This article describes how you can keep using Microsoft Edge Legacy after you install Microsoft Edge.</span></span>

## <span data-ttu-id="d1037-123">快速入门：Microsoft Edge Beta 渠道和 Microsoft Edge 旧版本的并行使用体验</span><span class="sxs-lookup"><span data-stu-id="d1037-123">Quickstart: Side-by-side experience with Microsoft Edge Beta Channel and Microsoft Edge Legacy</span></span>

<span data-ttu-id="d1037-124">在使用本文中的详细说明之前，请考虑执行以下 2 个步骤，让你的用户可并行运行 Microsoft Edge 旧版和 Microsoft Edge [Beta 渠道](microsoft-edge-channels.md)。</span><span class="sxs-lookup"><span data-stu-id="d1037-124">Before using the detailed instructions in this article, consider the following two steps to let your users run Microsoft Edge Legacy and the Microsoft Edge [Beta channel](microsoft-edge-channels.md) side-by-side.</span></span>

1. <span data-ttu-id="d1037-125">阻止 [Windows 更新](https://support.microsoft.com/help/12373/windows-update-faq)自动安装 Microsoft Edge 的 Stable 渠道。</span><span class="sxs-lookup"><span data-stu-id="d1037-125">Prevent the automatic install of the Stable Channel of Microsoft Edge by [Windows Update](https://support.microsoft.com/help/12373/windows-update-faq).</span></span>

   > [!TIP]
   > <span data-ttu-id="d1037-126">使用[阻止程序工具包](microsoft-edge-blocker-toolkit.md)禁止自动传递 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="d1037-126">Use the [Blocker Toolkit](microsoft-edge-blocker-toolkit.md) to disable automatic delivery of Microsoft Edge.</span></span>

2. <span data-ttu-id="d1037-127">安装 Microsoft Edge 新版本的 [Beta 渠道](https://www.microsoft.com/edge/business/download)。</span><span class="sxs-lookup"><span data-stu-id="d1037-127">Install the [Beta channel](https://www.microsoft.com/edge/business/download) of the new version of Microsoft Edge.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d1037-128">有关注册表项设置的信息，请阅读[其他信息](#additional-information)。</span><span class="sxs-lookup"><span data-stu-id="d1037-128">Read [Additional information](#additional-information) for information about Registry Key settings.</span></span>

<span data-ttu-id="d1037-129">这种并行解决方案不太复杂，并且需要的管理比本文中所述的详细解决方案更少。</span><span class="sxs-lookup"><span data-stu-id="d1037-129">This side-by-side solution is less complex and requires less management than the detailed solution described in this article.</span></span> <span data-ttu-id="d1037-130">但是，此解决方案意味着你将运行 Beta 渠道，而非 Stable 渠道。</span><span class="sxs-lookup"><span data-stu-id="d1037-130">However, this solution does mean that you'll be running the Beta Channel rather than the Stable Channel.</span></span>

## <span data-ttu-id="d1037-131">Microsoft Edge Stable 渠道和 Microsoft Edge 旧版的并行使用体验</span><span class="sxs-lookup"><span data-stu-id="d1037-131">Side-by-side experience with Microsoft Edge Stable Channel and Microsoft Edge Legacy</span></span>

<span data-ttu-id="d1037-132">在系统级别安装 Microsoft Edge 下一版本的 Stable 渠道将导致隐藏当前版本（Microsoft Edge 旧版本）。</span><span class="sxs-lookup"><span data-stu-id="d1037-132">Installing the Stable Channel of the next version of Microsoft Edge at the system-level will cause the current version (Microsoft Edge Legacy) to be hidden.</span></span> <span data-ttu-id="d1037-133">如果要让用户可在 Windows 中同时看到 Microsoft Edge 的两个版本，可通过将**允许 Microsoft Edge 并行浏览器体验**组策略设置为**已启用**来启用此体验。</span><span class="sxs-lookup"><span data-stu-id="d1037-133">If you want to let your users see both versions of Microsoft Edge side by side in Windows, you can enable this experience by setting the **Allow Microsoft Edge Side by Side browser experience** group policy to **Enabled**.</span></span>

<span data-ttu-id="d1037-134">[此处](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allowsxs)记载了这个组策略</span><span class="sxs-lookup"><span data-stu-id="d1037-134">This group policy is documented [here](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allowsxs)</span></span>

### <span data-ttu-id="d1037-135">若要设置并行浏览器体验策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d1037-135">To set up the side-by-side browser experience policy:</span></span>

1. <span data-ttu-id="d1037-136">从 [Microsoft Edge For Business](https://www.microsoft.com/edge/business/download) 安装策略定义。</span><span class="sxs-lookup"><span data-stu-id="d1037-136">Install the Policy Definitions from [Microsoft Edge for Business](https://www.microsoft.com/edge/business/download).</span></span>

   - <span data-ttu-id="d1037-137">选择要使用的渠道/内部版本和平台，然后单击“获取策略文件”。</span><span class="sxs-lookup"><span data-stu-id="d1037-137">Pick the CHANNEL/BUILD and PLATFORM you want to use, and then click GET POLICY FILES.</span></span>
   - <span data-ttu-id="d1037-138">将压缩文件解压缩。</span><span class="sxs-lookup"><span data-stu-id="d1037-138">Extract the zipped files.</span></span>
   - <span data-ttu-id="d1037-139">将 msedge.admx 和 msedgeupdate.admx 复制到 `C:\Windows\PolicyDefinitions` 目录。</span><span class="sxs-lookup"><span data-stu-id="d1037-139">Copy msedge.admx and msedgeupdate.admx to the `C:\Windows\PolicyDefinitions` directory.</span></span>
   - <span data-ttu-id="d1037-140">将 msedge.adml 和 msedgeupdate.adml（从相应的语言/区域设置目录）复制到 `C:\Windows\PolicyDefinitions\[APPROPRIATE LANGUAGE/LOCALE]` 目录。</span><span class="sxs-lookup"><span data-stu-id="d1037-140">Copy msedge.adml and msedgeupdate.adml (from the appropriate language/locale directory) to the `C:\Windows\PolicyDefinitions\[APPROPRIATE LANGUAGE/LOCALE]` directory.</span></span>

2. <span data-ttu-id="d1037-141">打开组策略编辑器 (gpedit.msc)。</span><span class="sxs-lookup"><span data-stu-id="d1037-141">Open the Group Policy Editor (gpedit.msc).</span></span>
3. <span data-ttu-id="d1037-142">在**计算机配置**下方，转到*管理模板 > Microsoft Edge 更新 > 应用程序*。</span><span class="sxs-lookup"><span data-stu-id="d1037-142">Under **Computer Configuration**, go to *Administrative Templates>Microsoft Edge Update>Applications*.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d1037-143">如果看不到 *Microsoft Edge 更新*文件夹，请验证步骤 1 是否已正确完成。</span><span class="sxs-lookup"><span data-stu-id="d1037-143">If you don't see the *Microsoft Edge Update* folder, verify that step 1 was completed correctly.</span></span>

4. <span data-ttu-id="d1037-144">在**应用程序**下方，双击“允许 Microsoft Edge 并行浏览器体验”。</span><span class="sxs-lookup"><span data-stu-id="d1037-144">Under **Applications**, double-click "Allow Microsoft Edge Side by Side browser experience".</span></span> <span data-ttu-id="d1037-145">请参阅我们的[最佳实践指南](#best-practice-guidance)，然后再继续执行下一步。</span><span class="sxs-lookup"><span data-stu-id="d1037-145">See our [best practice guidance](#best-practice-guidance) before continuing to the next step.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d1037-146">默认情况下，将这个组策略设置为“未配置”，这导致在安装 Microsoft Edge 的新版本后隐藏旧版 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="d1037-146">By default, this group policy is set to "Not configured", which results in Microsoft Edge Legacy being hidden when the new version of Microsoft Edge is installed.</span></span>

5. <span data-ttu-id="d1037-147">选中**已启用**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d1037-147">Select **Enabled** and then click **OK**.</span></span>  

<span data-ttu-id="d1037-148">设置此策略会将以下注册表项设置为“00000001”：</span><span class="sxs-lookup"><span data-stu-id="d1037-148">Setting this policy will set the following Registry Key  to '00000001':</span></span>

- <span data-ttu-id="d1037-149">注册表项：</span><span class="sxs-lookup"><span data-stu-id="d1037-149">Key:</span></span> `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate`
- <span data-ttu-id="d1037-150">值名称：</span><span class="sxs-lookup"><span data-stu-id="d1037-150">Value Name:</span></span> `Allowsxs`
- <span data-ttu-id="d1037-151">值类型：</span><span class="sxs-lookup"><span data-stu-id="d1037-151">Value Type:</span></span> `'REG_DWORD'`

#### <span data-ttu-id="d1037-152">最佳实践指导</span><span class="sxs-lookup"><span data-stu-id="d1037-152">Best practice guidance</span></span>

<span data-ttu-id="d1037-153">为了获得最佳体验，应先启用**允许 Microsoft Edge 并行浏览器体验**，然后再将 Microsoft Edge 的新版本部署到用户的设备。</span><span class="sxs-lookup"><span data-stu-id="d1037-153">For the best experience, the **Allow Microsoft Edge Side by Side browser experience** should be enabled before the new version of Microsoft Edge is deployed to your users' devices.</span></span>

<span data-ttu-id="d1037-154">如果在部署 Microsoft Edge 后才启用该组策略，则有以下这些副作用和所需采取的措施：</span><span class="sxs-lookup"><span data-stu-id="d1037-154">If the group policy is enabled after Microsoft Edge is deployed, there are the following side effects and required actions:</span></span>

1. <span data-ttu-id="d1037-155">直到再次运行 Microsoft Edge 新版本的安装程序后，**允许 Microsoft Edge 并行浏览器体验**才会生效。</span><span class="sxs-lookup"><span data-stu-id="d1037-155">**Allow Microsoft Edge Side by Side browser experience** won't take effect until after the installer for the new version of Microsoft Edge is run again.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d1037-156">可直接运行该安装程序，也可在 Microsoft Edge 的新版本进行更新时自动运行该安装程序。</span><span class="sxs-lookup"><span data-stu-id="d1037-156">The installer can be run directly or automatically when the new version of Microsoft Edge updates.</span></span>

2. <span data-ttu-id="d1037-157">需要将旧版 Microsoft Edge 重新固定到“开始”屏幕或任务栏，因为在部署 Microsoft Edge 的新版本时将迁移固定方式。</span><span class="sxs-lookup"><span data-stu-id="d1037-157">Microsoft Edge Legacy will need to be re-pinned to Start or the Taskbar because the pin is migrated when the new version of Microsoft Edge is deployed.</span></span>
3. <span data-ttu-id="d1037-158">对于旧版 Microsoft Edge 固定到“开始”屏幕或任务栏的网站将迁移到 Microsoft Edge 的新版本。</span><span class="sxs-lookup"><span data-stu-id="d1037-158">Sites that were pinned to Start or the Taskbar for Microsoft Edge Legacy will be migrated to the new version of Microsoft Edge.</span></span>

## <span data-ttu-id="d1037-159">其他信息</span><span class="sxs-lookup"><span data-stu-id="d1037-159">Additional information</span></span>

<span data-ttu-id="d1037-160">在完全更新系统并安装 Microsoft Edge 下一版本的 Stable 渠道后，将设置以下注册表项和值：</span><span class="sxs-lookup"><span data-stu-id="d1037-160">After the systems are fully updated and the Stable channel of the next version of Microsoft Edge is installed, the following registry key and value is set:</span></span>

- <span data-ttu-id="d1037-161">注册表项：</span><span class="sxs-lookup"><span data-stu-id="d1037-161">Key:</span></span> `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\ClientState\{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}`
- <span data-ttu-id="d1037-162">项值：</span><span class="sxs-lookup"><span data-stu-id="d1037-162">Key value:</span></span> `BrowserReplacement`

  > [!IMPORTANT]
  > <span data-ttu-id="d1037-163">每次更新 Microsoft Edge Stable 渠道时，都会覆盖此项。</span><span class="sxs-lookup"><span data-stu-id="d1037-163">This key is over-written every time the Microsoft Edge Stable channel is updated.</span></span> <span data-ttu-id="d1037-164">作为最佳实践，我们建议不要删除此项，以使用户可同时访问 Microsoft Edge 的两个版本。</span><span class="sxs-lookup"><span data-stu-id="d1037-164">As a best practice, we recommend that you DO NOT delete this key to allow users to access both versions of Microsoft Edge.</span></span>

## <span data-ttu-id="d1037-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1037-165">See also</span></span>

- [<span data-ttu-id="d1037-166">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="d1037-166">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="d1037-167">用于支持 Microsoft Edge 的 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="d1037-167">Windows updates to support Microsoft Edge</span></span>](microsoft-edge-sysupdate-windows-updates.md)
