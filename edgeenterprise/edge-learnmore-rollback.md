---
title: Microsoft Edge 企业版回退
ms.author: v-danwes
author: dan-wesley
manager: srugh
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 如何将 Microsoft Edge 回退到以前的版本
ms.openlocfilehash: 9af0881a079dd3059e567eaadb912b3d929924c4
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979287"
---
# <span data-ttu-id="3e5f2-103">如何将 Microsoft Edge 回退到以前的版本</span><span class="sxs-lookup"><span data-stu-id="3e5f2-103">How to roll back Microsoft Edge to a previous version</span></span>

<span data-ttu-id="3e5f2-104">本文介绍如何使用“回退”功能回退到以前版本的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-104">This article describes how to roll back to a previous version of Microsoft Edge using the rollback feature.</span></span>

>[!NOTE]
><span data-ttu-id="3e5f2-105">本文适用于 Microsoft Edge 版本 86 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-105">This article applies to Microsoft Edge version 86 or later.</span></span>

## <span data-ttu-id="3e5f2-106">回退简介</span><span class="sxs-lookup"><span data-stu-id="3e5f2-106">Introduction to rollback</span></span>

<span data-ttu-id="3e5f2-107">回退可让你将 Microsoft Edge 浏览器版本替换为更早期版本。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-107">Rollback lets you replace your Microsoft Edge browser version with an earlier version.</span></span> <span data-ttu-id="3e5f2-108">此功能旨在为企业部署 Microsoft Edge 提供安全网络。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-108">This feature is designed to be a safety net for enterprises deploying Microsoft Edge.</span></span> <span data-ttu-id="3e5f2-109">它提供了一种解决 Microsoft Edge 问题的方法。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-109">It provides a way to troubleshoot issues with Microsoft Edge.</span></span> <span data-ttu-id="3e5f2-110">回退的优点是能够轻松快速地还原到先前的浏览器版本。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-110">The benefits of rollback are the ability to revert to previous browser version easily and quickly.</span></span> <span data-ttu-id="3e5f2-111">回退会降低 Microsoft Edge 问题对企业运营的潜在影响。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-111">Rollback reduces the potential impact that a Microsoft Edge issue has on business operations.</span></span>

## <span data-ttu-id="3e5f2-112">开始之前</span><span class="sxs-lookup"><span data-stu-id="3e5f2-112">Before you begin</span></span>

<span data-ttu-id="3e5f2-113">请务必了解如何在 Microsoft Edge 环境中安装“回退”功能。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-113">It's important to understand how the rollback feature is installed in a Microsoft Edge environment.</span></span> <span data-ttu-id="3e5f2-114">可使用两种不同方法部署回退：使用 MSI 手动部署或使用 Microsoft Edge 更新和组策略。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-114">You can deploy rollback using two different methods: manually with an MSI or by using Microsoft Edge update and Group Policy.</span></span> <span data-ttu-id="3e5f2-115">我们还鼓励使用多种组策略更顺利地部署回退。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-115">We also  encourage using a selection of Group Policies for a smoother deployment.</span></span>

### <span data-ttu-id="3e5f2-116">建议</span><span class="sxs-lookup"><span data-stu-id="3e5f2-116">Recommendations</span></span>

<span data-ttu-id="3e5f2-117">回退功能旨在临时修复 Microsoft Edge 浏览器更新中可能发现的问题。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-117">The rollback feature is meant to be a temporary fix for issues you might find in a Microsoft Edge browser update.</span></span> <span data-ttu-id="3e5f2-118">我们建议用户安装最新版本的 Microsoft Edge 浏览器，以使用最新安全更新提供的保护。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-118">We recommend that users install the latest version of the Microsoft Edge browser to use the protection provided by the latest security updates.</span></span> <span data-ttu-id="3e5f2-119">回退到较早版本存在遇到已知安全问题的风险。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-119">Rollback to an earlier version risks exposure to known security issues.</span></span>

<span data-ttu-id="3e5f2-120">在暂时回退浏览器版本之前，强烈建议你为组织中的所有用户启用同步。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-120">Before temporarily rolling back your browser version, we also highly recommend that you enable Sync for all the users in your organization.</span></span> <span data-ttu-id="3e5f2-121">如果未启用同步，则会存在永久丢失浏览数据的风险。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-121">If you don't turn on Sync, there's a risk of permanent browsing data loss.</span></span> <span data-ttu-id="3e5f2-122">有关详细信息，请参阅 [Microsoft Edge 同步](microsoft-edge-enterprise-sync.md)。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-122">For more information about Sync, see [Microsoft Edge Sync](microsoft-edge-enterprise-sync.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="3e5f2-123">请仅在必要时使用回退，因为始终存在数据丢失风险。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-123">Only use rollback when necessary, there's always the risk of data loss.</span></span>

## <span data-ttu-id="3e5f2-124">启用通过 MSI 手动回退</span><span class="sxs-lookup"><span data-stu-id="3e5f2-124">Enable rollback manually with an MSI</span></span>

<span data-ttu-id="3e5f2-125">请按照以下步骤手动使用 MSI 回退。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-125">Use the following steps to roll back manually with an MSI.</span></span>

1. <span data-ttu-id="3e5f2-126">禁用 Microsoft Edge 更新。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-126">Disable Microsoft Edge Updates.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3e5f2-127">建议安装最新的管理模板。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-127">We recommend that you install the most current Administrative templates.</span></span> <span data-ttu-id="3e5f2-128">有关详细信息，请参阅[下载并安装 Microsoft Edge 管理模板](https://docs.microsoft.com/DeployEdge/configure-microsoft-edge#1-download-and-install-the-microsoft-edge-administrative-template)。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-128">For more information, see [Download and install the Microsoft Edge administrative template](https://docs.microsoft.com/DeployEdge/configure-microsoft-edge#1-download-and-install-the-microsoft-edge-administrative-template).</span></span>

   - <span data-ttu-id="3e5f2-129">打开本地组策略编辑器，然后转到“*计算机配置”>“管理模板”>“Microsoft Edge 更新”>“应用程序”>“Microsoft edge”>*。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-129">Open the local Group Policy Editor and go to *Computer Configuration>Administrative Templates>Microsoft Edge Update>Applications>Microsoft Edge>*.</span></span>
   - <span data-ttu-id="3e5f2-130">选择“**更新策略替代**”，然后选择“**已启用**”。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-130">Select **Update policy override** and then select **Enabled**.</span></span>
   - <span data-ttu-id="3e5f2-131">在“**选项**”下，从“策略”下拉列表中选择“**已禁用更新**”。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-131">Under **Options**, pick **Update disabled** from the Policy dropdown list.</span></span>

2. <span data-ttu-id="3e5f2-132">获取 MSI。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-132">Get the MSI.</span></span>

   - <span data-ttu-id="3e5f2-133">从[这里](https://www.microsoft.com/edge/business/download)下载您想要回退到的版本的 MSI。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-133">Download the MSI for the version you want to roll back to [from here](https://www.microsoft.com/edge/business/download).</span></span>
   - <span data-ttu-id="3e5f2-134">将 MSI 保存到桌面。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-134">Save the MSI to your desktop.</span></span>

3. <span data-ttu-id="3e5f2-135">运行回退命令。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-135">Run the rollback command.</span></span>

   - <span data-ttu-id="3e5f2-136">使用“**以管理员身份运行**”打开 Windows 命令提示。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-136">Open the Windows command prompt with **Run as administrator**.</span></span>
   - <span data-ttu-id="3e5f2-137">键入以下命令，其中：*C:\Users\username\Desktop\test*  是已下载的 MSI 所在路径，FileName 是 .msi 文件的名称：</span><span class="sxs-lookup"><span data-stu-id="3e5f2-137">Type the following command, where: *C:\Users\username\Desktop\test* is the path to the MSI you downloaded, and FileName is the name of the .msi file:</span></span><br>
 `C:\Users\username\Desktop\test>msiexec /I FileName.msi /qn ALLOWDOWNGRADE=1`<br>
     > [!NOTE]
     > <span data-ttu-id="3e5f2-138">有关 msiexec 的详细信息，请参阅 [msiexec](https://docs.microsoft.com/windows-server/administration/windows-commands/msiexec)。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-138">For more information about msiexec, see [msiexec](https://docs.microsoft.com/windows-server/administration/windows-commands/msiexec).</span></span>
   - <span data-ttu-id="3e5f2-139">关闭并重新打开 Microsoft Edge，验证回退是否成功。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-139">Close and reopen Microsoft Edge to verify that the rollback worked.</span></span> <span data-ttu-id="3e5f2-140">在“**设置”和“更多**” (ALT + F) 下，转到 “**设置**”并选择“**关于 Microsoft Edge**”。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-140">Under **Settings and more** (ALT + F), go to **Settings** and select **About Microsoft Edge**.</span></span>

## <span data-ttu-id="3e5f2-141">使用 Microsoft Edge 更新和组策略启用回退</span><span class="sxs-lookup"><span data-stu-id="3e5f2-141">Enable rollback with Microsoft Edge update and Group Policy</span></span>

<span data-ttu-id="3e5f2-142">按照以下步骤可使用 Microsoft Edge 更新和组策略启用回退。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-142">Use the following steps to enable rollback with Microsoft Edge update and Group Policy.</span></span>

1. <span data-ttu-id="3e5f2-143">打开本地组策略编辑器，然后转到“*计算机配置”>“管理模板”>“Microsoft Edge 更新”>“应用程序”>“Microsoft edge”>*。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-143">Open the local Group Policy Editor and go to *Computer Configuration>Administrative Templates>Microsoft Edge Update>Applications>Microsoft Edge>*.</span></span>
2. <span data-ttu-id="3e5f2-144">选择“**回退到目标版本**”，然后选择 “**已启用**”。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-144">Select **Rollback to target version** and then select **Enabled**.</span></span>
3. <span data-ttu-id="3e5f2-145">选择“**目标版本替代**”，并选择要回退到的浏览器版本。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-145">Select **Target version override** and pick the browser version you want to roll back to.</span></span>
4. <span data-ttu-id="3e5f2-146">选择“**更新策略替代**”，然后选择“**已启用**”。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-146">Select **Update policy override** and then select **Enabled**.</span></span> <span data-ttu-id="3e5f2-147">在“**选项**”下，从“策略”下拉列表中选择以下选项之一（“**已禁用更新**”除外）：</span><span class="sxs-lookup"><span data-stu-id="3e5f2-147">Under **Options**, pick one of the following options from the Policy dropdown list (except for **Update disabled**):</span></span>

   - <span data-ttu-id="3e5f2-148">始终允许更新</span><span class="sxs-lookup"><span data-stu-id="3e5f2-148">Always allow updates</span></span>
   - <span data-ttu-id="3e5f2-149">仅自动静默更新</span><span class="sxs-lookup"><span data-stu-id="3e5f2-149">Automatic silent updates only</span></span>
   - <span data-ttu-id="3e5f2-150">仅手动更新</span><span class="sxs-lookup"><span data-stu-id="3e5f2-150">Manual updates only</span></span>  

5. <span data-ttu-id="3e5f2-151">将在下次 Microsoft Edge 更新检查更新时执行回退。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-151">Rollback will happen the next time Microsoft Edge Update checks for an update.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3e5f2-152">如果你希望立即回退，则必须更改 Microsoft Edge 更新轮询间隔，或使用 MSI 启用回退。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-152">If you want rollback to happen right away you have to change the Microsoft Edge Update polling interval or enable rollback using an MSI.</span></span>

### <span data-ttu-id="3e5f2-153">常见回退错误</span><span class="sxs-lookup"><span data-stu-id="3e5f2-153">Common rollback errors</span></span>

<span data-ttu-id="3e5f2-154">以下错误将阻止回退：</span><span class="sxs-lookup"><span data-stu-id="3e5f2-154">The following errors will prevent rollback:</span></span>

- <span data-ttu-id="3e5f2-155">输入为不受支持的目标版本</span><span class="sxs-lookup"><span data-stu-id="3e5f2-155">Input is an unsupported target version</span></span>
- <span data-ttu-id="3e5f2-156">输入为不存在的目标版本</span><span class="sxs-lookup"><span data-stu-id="3e5f2-156">Input is a non-existent target version</span></span>
- <span data-ttu-id="3e5f2-157">输入未正确格式化。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-157">Input is incorrectly formatted</span></span>

### <span data-ttu-id="3e5f2-158">推荐的组策略</span><span class="sxs-lookup"><span data-stu-id="3e5f2-158">Recommended Group Policies</span></span>

<span data-ttu-id="3e5f2-159">强烈推荐使用回退功能时采用以下组策略和设置。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-159">The following group policies and settings are highly recommended for using rollback.</span></span>

#### <span data-ttu-id="3e5f2-160">同步组策略</span><span class="sxs-lookup"><span data-stu-id="3e5f2-160">Sync Group Policies</span></span>

- <span data-ttu-id="3e5f2-161">ForceSync.</span><span class="sxs-lookup"><span data-stu-id="3e5f2-161">ForceSync.</span></span> <span data-ttu-id="3e5f2-162">将 ForceSync 设置为“启用”。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-162">Set ForceSync to enabled.</span></span> <span data-ttu-id="3e5f2-163">此策略将强制启用所有 Azure Active Directory (Azure AD) 用户的同步。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-163">This policy will force enable Sync on all Azure Active Directory (Azure AD) users.</span></span> <span data-ttu-id="3e5f2-164">此策略仅适用于 Microsoft Edge 版本 86 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-164">This policy is only effective for Microsoft Edge versions 86 and later.</span></span>
- <span data-ttu-id="3e5f2-165">*配置从同步策略中排除的类型列表*允许管理员控制用户可同步哪些数据。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-165">The *Configure the list of the types that are excluded from synchronization policy* allows admins to control what data can be synced by users.</span></span>

#### <span data-ttu-id="3e5f2-166">浏览器重新启动组策略</span><span class="sxs-lookup"><span data-stu-id="3e5f2-166">Browser restart Group Policies</span></span>

<span data-ttu-id="3e5f2-167">建议启用回退后，对用户强制重启。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-167">We recommend forcing a restart on users after rollback is enabled.</span></span>

- <span data-ttu-id="3e5f2-168">启用*通知用户对于挂起的更新，推荐或需要重新启动浏览器*。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-168">Enable *Notify a user that a browser restart is recommended or required for pending updates*.</span></span> <span data-ttu-id="3e5f2-169">在“选项”下，选择“**必需**”。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-169">Under Options, select **Required**.</span></span>
- <span data-ttu-id="3e5f2-170">启用*设置更新通知时间段，然后设置所需时间（以毫秒为单位）*。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-170">Enable *Set the time period for update notifications* and then set the desired time in milliseconds.</span></span>

## <span data-ttu-id="3e5f2-171">常见问题</span><span class="sxs-lookup"><span data-stu-id="3e5f2-171">Frequently asked questions</span></span>

### <span data-ttu-id="3e5f2-172">手动 MSI 回退</span><span class="sxs-lookup"><span data-stu-id="3e5f2-172">Manual MSI rollback</span></span>

#### <span data-ttu-id="3e5f2-173">可能发生哪些常见 MSI 故障？</span><span class="sxs-lookup"><span data-stu-id="3e5f2-173">What generic MSI failures that can happen?</span></span>

1. <span data-ttu-id="3e5f2-174">如果禁用“安装更新”组策略，则不会发生回退。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-174">If the Install update group policy is disabled, rollback won't occur.</span></span>

   - <span data-ttu-id="3e5f2-175">若要使用回退，请确保将“安装”设置为“**启用**”。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-175">To use rollback, make sure Install is set to **Enabled**.</span></span> <span data-ttu-id="3e5f2-176">如果禁用此策略，将阻止安装 Microsoft Edge 频道。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-176">When this policy is disabled, it prevents Microsoft Edge channels from being installed.</span></span> <span data-ttu-id="3e5f2-177">有关详细信息，请参阅[安装](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#install)。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-177">For more information, see [Install](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#install).</span></span>

2. <span data-ttu-id="3e5f2-178">如果启发更新不存在，将阻止 Microsoft Edge 安装，除非已启用*允许 Microsoft Edge 并排浏览体验*。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-178">If Enlightenment Updates aren't present, Microsoft Edge installations will be blocked unless *Allow Microsoft Edge Side by Side browser experience* is enabled.</span></span>

   - <span data-ttu-id="3e5f2-179">针对 Windows 版本 1903 和 1909：如果上次更新早于 2019 年 10 月，则可能会存在此问题。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-179">For Windows versions 1903 and 1909: If your last update was before October 2019, you may have this issue.</span></span>
   - <span data-ttu-id="3e5f2-180">针对 Windows 版本 1709、1803 和 1809：如果上次更新早于 2019 年 11 月，则可能会存在此问题。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-180">For Windows versions 1709, 1803, and 1809: If your last update was before November 2019, you may have this issue.</span></span><br>
<span data-ttu-id="3e5f2-181">有关详细信息，请参阅[用于支持下一版 Microsoft Edge 的 Windows 更新](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-windows-updates)。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-181">For more information, see [Windows updates to support the next version of Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-windows-updates)</span></span>

#### <span data-ttu-id="3e5f2-182">使用命令提示但回退没发生后，显示以下错误消息。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-182">The following error message was shown after using the Command Prompt and rollback didn't occur.</span></span> <span data-ttu-id="3e5f2-183">究竟是哪里出现错误？</span><span class="sxs-lookup"><span data-stu-id="3e5f2-183">What's wrong?</span></span>

![回退状态消息](./media/edge-learnmore-rollback/edge-rollback-cmd-flag-error.png)

<span data-ttu-id="3e5f2-185">*ALLOWDOWNGRADE = 1* 未执行。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-185">*ALLOWDOWNGRADE=1* was not executed.</span></span>

### <span data-ttu-id="3e5f2-186">Microsoft Edge 更新和组策略回退</span><span class="sxs-lookup"><span data-stu-id="3e5f2-186">Microsoft Edge Update and Group Policy rollback</span></span>

#### <span data-ttu-id="3e5f2-187">我设置了*回退到目标版本*、启用了*更新策略替代*，且输入了*目标版本替代*希望回退到的浏览器版本，但浏览器版本不是我要回退到的版本。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-187">I set *Rollback to target version*, enabled *Update policy override*, input my desired browser version for *Target version override*, but the browser version wasn't what I expected.</span></span> <span data-ttu-id="3e5f2-188">究竟是哪里出现错误？</span><span class="sxs-lookup"><span data-stu-id="3e5f2-188">What's wrong?</span></span>

<span data-ttu-id="3e5f2-189">以下常见错误会阻止回退：</span><span class="sxs-lookup"><span data-stu-id="3e5f2-189">Some common errors that prevent rollback are:</span></span>

- <span data-ttu-id="3e5f2-190">如果未设置回退到目标版本，将不会执行回退。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-190">If Rollback to target version isn't set, rollback will not be executed.</span></span>
- <span data-ttu-id="3e5f2-191">目标版本替代设置存在以下问题之一：</span><span class="sxs-lookup"><span data-stu-id="3e5f2-191">There are one of the following issues with the target version override setting:</span></span>

  - <span data-ttu-id="3e5f2-192">目标版本替代被设置为不受支持的目标版本。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-192">Target version override is set to an unsupported target version.</span></span>
  - <span data-ttu-id="3e5f2-193">目标版本替代被设置为不存在的目标版本。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-193">Target version override is set to a non-existent target version.</span></span>
  - <span data-ttu-id="3e5f2-194">目标版本替代输入的格式不正确。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-194">Target version override input is incorrectly formatted.</span></span>

- <span data-ttu-id="3e5f2-195">如果将”更新策略替代“设置为“禁用更新”，则 Microsoft Edge 更新不会接受任何更新。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-195">If Update policy override is set to "Updates disabled", Microsoft Edge Update won't accept any updates.</span></span> <span data-ttu-id="3e5f2-196">这将导致不执行回退。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-196">This results in rollback not getting executed.</span></span>

### <span data-ttu-id="3e5f2-197">我正确设置了所有组策略，但回退未执行。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-197">I set all the group policies correctly, but rollback didn't execute.</span></span> <span data-ttu-id="3e5f2-198">发生了什么情况？</span><span class="sxs-lookup"><span data-stu-id="3e5f2-198">What happened?</span></span>

<span data-ttu-id="3e5f2-199">Microsoft Edge 更新尚未运行更新检查。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-199">Microsoft Edge Update hasn't run a check for updates yet.</span></span> <span data-ttu-id="3e5f2-200">默认情况下，自动更新将每 10 小时检查一次更新。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-200">By default, auto-update checks for updates every 10 hours.</span></span> <span data-ttu-id="3e5f2-201">可通过更改 Microsoft Edge 更新的轮询间隔来修复此错误，自动更新检查周期将覆盖组策略。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-201">You can fix this by changing Microsoft Edge Update's polling interval with the Auto-update check period override group policy.</span></span> <span data-ttu-id="3e5f2-202">有关详细信息，请参阅 [AutoUpdateCheckPeriodMinutes](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#autoupdatecheckperiodminutes) 策略。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-202">For more information, see the [AutoUpdateCheckPeriodMinutes](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#autoupdatecheckperiodminutes) policy.</span></span>

### <span data-ttu-id="3e5f2-203">作为 IT 管理员，我按照正确回退的所有步骤进行了操作。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-203">As an IT admin, I followed all the steps for rollback correctly.</span></span> <span data-ttu-id="3e5f2-204">“我的用户组”的一部分已回退。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-204">Only a portion of my user group was rolled back.</span></span> <span data-ttu-id="3e5f2-205">为什么尚未回退其他用户？</span><span class="sxs-lookup"><span data-stu-id="3e5f2-205">Why haven't the other users been rolled back yet?</span></span>

<span data-ttu-id="3e5f2-206">组策略设置尚未同步到所有客户端。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-206">The group policy setting hasn't synced to all the clients yet.</span></span> <span data-ttu-id="3e5f2-207">当管理员设置组策略时，客户端不会立即收到这些设置。</span><span class="sxs-lookup"><span data-stu-id="3e5f2-207">When admins set a group policy, clients don't receive these settings instantaneously.</span></span>

<!--
You can update all users' group policy with the  

When admins set all users don't get this setting instantaneously 

GP Update force group policy – link to this 

-->





## <span data-ttu-id="3e5f2-208">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e5f2-208">See also</span></span>

- [<span data-ttu-id="3e5f2-209">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="3e5f2-209">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
