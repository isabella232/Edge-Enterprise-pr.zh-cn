---
title: Microsoft Edge 企业版回退
ms.author: v-danwes
author: dan-wesley
manager: srugh
ms.date: 09/02/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 如何将 Microsoft Edge 回退到以前的版本
ms.openlocfilehash: 9f659b0bcdd82f54a814c8ad4157521061cdfa7c
ms.sourcegitcommit: 827a47d641c7ddc1d89be5d5fc0615373dec18b0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993702"
---
# <span data-ttu-id="ee499-103">如何将 Microsoft Edge 回退到以前的版本</span><span class="sxs-lookup"><span data-stu-id="ee499-103">How to roll back Microsoft Edge to a previous version</span></span>

<span data-ttu-id="ee499-104">本文介绍如何使用“回退”功能回退到以前版本的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="ee499-104">This article describes how to roll back to a previous version of Microsoft Edge using the rollback feature.</span></span>

>[!NOTE]
><span data-ttu-id="ee499-105">本文适用于 Microsoft Edge 版本 86 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="ee499-105">This article applies to Microsoft Edge version 86 or later.</span></span>

## <span data-ttu-id="ee499-106">回退简介</span><span class="sxs-lookup"><span data-stu-id="ee499-106">Introduction to rollback</span></span>

<span data-ttu-id="ee499-107">回退可让你将 Microsoft Edge 浏览器版本替换为更早期版本。</span><span class="sxs-lookup"><span data-stu-id="ee499-107">Rollback lets you replace your Microsoft Edge browser version with an earlier version.</span></span> <span data-ttu-id="ee499-108">此功能旨在为企业部署 Microsoft Edge 提供安全网络。</span><span class="sxs-lookup"><span data-stu-id="ee499-108">This feature is designed to be a safety net for enterprises deploying Microsoft Edge.</span></span> <span data-ttu-id="ee499-109">它提供了一种解决 Microsoft Edge 问题的方法。</span><span class="sxs-lookup"><span data-stu-id="ee499-109">It provides a way to troubleshoot issues with Microsoft Edge.</span></span> <span data-ttu-id="ee499-110">回退的优点是能够轻松快速地还原到先前的浏览器版本。</span><span class="sxs-lookup"><span data-stu-id="ee499-110">The benefits of rollback are the ability to revert to previous browser version easily and quickly.</span></span> <span data-ttu-id="ee499-111">回退会降低 Microsoft Edge 问题对企业运营的潜在影响。</span><span class="sxs-lookup"><span data-stu-id="ee499-111">Rollback reduces the potential impact that a Microsoft Edge issue has on business operations.</span></span>

## <span data-ttu-id="ee499-112">开始之前</span><span class="sxs-lookup"><span data-stu-id="ee499-112">Before you begin</span></span>

<span data-ttu-id="ee499-113">请务必了解如何在 Microsoft Edge 环境中安装“回退”功能。</span><span class="sxs-lookup"><span data-stu-id="ee499-113">It's important to understand how the rollback feature is installed in a Microsoft Edge environment.</span></span> <span data-ttu-id="ee499-114">可使用两种不同方法部署回退：使用 MSI 手动部署或使用 Microsoft Edge 更新和组策略。</span><span class="sxs-lookup"><span data-stu-id="ee499-114">You can deploy rollback using two different methods: manually with an MSI or by using Microsoft Edge update and Group Policy.</span></span> <span data-ttu-id="ee499-115">我们还鼓励使用多种组策略更顺利地部署回退。</span><span class="sxs-lookup"><span data-stu-id="ee499-115">We also  encourage using a selection of Group Policies for a smoother deployment.</span></span>

### <span data-ttu-id="ee499-116">建议</span><span class="sxs-lookup"><span data-stu-id="ee499-116">Recommendations</span></span>

<span data-ttu-id="ee499-117">回退功能旨在临时修复 Microsoft Edge 浏览器更新中可能发现的问题。</span><span class="sxs-lookup"><span data-stu-id="ee499-117">The rollback feature is meant to be a temporary fix for issues you might find in a Microsoft Edge browser update.</span></span> <span data-ttu-id="ee499-118">我们建议用户安装最新版本的 Microsoft Edge 浏览器，以使用最新安全更新提供的保护。</span><span class="sxs-lookup"><span data-stu-id="ee499-118">We recommend that users install the latest version of the Microsoft Edge browser to use the protection provided by the latest security updates.</span></span> <span data-ttu-id="ee499-119">回退到较早版本存在遇到已知安全问题的风险。</span><span class="sxs-lookup"><span data-stu-id="ee499-119">Rollback to an earlier version risks exposure to known security issues.</span></span>

<span data-ttu-id="ee499-120">在暂时回退浏览器版本之前，强烈建议你为组织中的所有用户启用同步。</span><span class="sxs-lookup"><span data-stu-id="ee499-120">Before temporarily rolling back your browser version, we also highly recommend that you enable Sync for all the users in your organization.</span></span> <span data-ttu-id="ee499-121">如果未启用同步，则会存在永久丢失浏览数据的风险。</span><span class="sxs-lookup"><span data-stu-id="ee499-121">If you don't turn on Sync, there's a risk of permanent browsing data loss.</span></span> <span data-ttu-id="ee499-122">有关详细信息，请参阅 [Microsoft Edge 同步](microsoft-edge-enterprise-sync.md)。</span><span class="sxs-lookup"><span data-stu-id="ee499-122">For more information about Sync, see [Microsoft Edge Sync](microsoft-edge-enterprise-sync.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="ee499-123">请仅在必要时使用回退，因为始终存在数据丢失风险。</span><span class="sxs-lookup"><span data-stu-id="ee499-123">Only use rollback when necessary, there's always the risk of data loss.</span></span>

## <span data-ttu-id="ee499-124">启用通过 MSI 手动回退</span><span class="sxs-lookup"><span data-stu-id="ee499-124">Enable rollback manually with an MSI</span></span>

<span data-ttu-id="ee499-125">请按照以下步骤手动使用 MSI 回退。</span><span class="sxs-lookup"><span data-stu-id="ee499-125">Use the following steps to roll back manually with an MSI.</span></span>

1. <span data-ttu-id="ee499-126">禁用 Microsoft Edge 更新。</span><span class="sxs-lookup"><span data-stu-id="ee499-126">Disable Microsoft Edge Updates.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ee499-127">建议安装最新的管理模板。</span><span class="sxs-lookup"><span data-stu-id="ee499-127">We recommend that you install the most current Administrative templates.</span></span> <span data-ttu-id="ee499-128">有关详细信息，请参阅[下载并安装 Microsoft Edge 管理模板](https://docs.microsoft.com/DeployEdge/configure-microsoft-edge#1-download-and-install-the-microsoft-edge-administrative-template)。</span><span class="sxs-lookup"><span data-stu-id="ee499-128">For more information, see [Download and install the Microsoft Edge administrative template](https://docs.microsoft.com/DeployEdge/configure-microsoft-edge#1-download-and-install-the-microsoft-edge-administrative-template).</span></span>

   - <span data-ttu-id="ee499-129">打开本地组策略编辑器，然后转到“*计算机配置”>“管理模板”>“Microsoft Edge 更新”>“应用程序”>“Microsoft edge”>*。</span><span class="sxs-lookup"><span data-stu-id="ee499-129">Open the local Group Policy Editor and go to *Computer Configuration>Administrative Templates>Microsoft Edge Update>Applications>Microsoft Edge>*.</span></span>
   - <span data-ttu-id="ee499-130">选择“**更新策略替代**”，然后选择“**已启用**”。</span><span class="sxs-lookup"><span data-stu-id="ee499-130">Select **Update policy override** and then select **Enabled**.</span></span>
   - <span data-ttu-id="ee499-131">在“**选项**”下，从“策略”下拉列表中选择“**已禁用更新**”。</span><span class="sxs-lookup"><span data-stu-id="ee499-131">Under **Options**, pick **Update disabled** from the Policy dropdown list.</span></span>

2. <span data-ttu-id="ee499-132">获取 MSI。</span><span class="sxs-lookup"><span data-stu-id="ee499-132">Get the MSI.</span></span>

   - <span data-ttu-id="ee499-133">从[这里](https://www.microsoft.com/edge/business/download)下载您想要回退到的版本的 MSI。</span><span class="sxs-lookup"><span data-stu-id="ee499-133">Download the MSI for the version you want to roll back to [from here](https://www.microsoft.com/edge/business/download).</span></span>
   - <span data-ttu-id="ee499-134">将 MSI 保存到桌面。</span><span class="sxs-lookup"><span data-stu-id="ee499-134">Save the MSI to your desktop.</span></span>

3. <span data-ttu-id="ee499-135">运行回退命令。</span><span class="sxs-lookup"><span data-stu-id="ee499-135">Run the rollback command.</span></span>

   - <span data-ttu-id="ee499-136">使用“**以管理员身份运行**”打开 Windows 命令提示。</span><span class="sxs-lookup"><span data-stu-id="ee499-136">Open the Windows command prompt with **Run as administrator**.</span></span>
   - <span data-ttu-id="ee499-137">键入以下命令，其中：*C:\Users\username\Desktop\test*  是已下载的 MSI 所在路径，FileName 是 .msi 文件的名称：</span><span class="sxs-lookup"><span data-stu-id="ee499-137">Type the following command, where: *C:\Users\username\Desktop\test* is the path to the MSI you downloaded, and FileName is the name of the .msi file:</span></span><br>
 `C:\Users\username\Desktop\test>msiexec /I FileName.msi /qn ALLOWDOWNGRADE=1`<br>
     > [!NOTE]
     > <span data-ttu-id="ee499-138">有关 msiexec 的详细信息，请参阅 [msiexec](https://docs.microsoft.com/windows-server/administration/windows-commands/msiexec)。</span><span class="sxs-lookup"><span data-stu-id="ee499-138">For more information about msiexec, see [msiexec](https://docs.microsoft.com/windows-server/administration/windows-commands/msiexec).</span></span>
   - <span data-ttu-id="ee499-139">关闭并重新打开 Microsoft Edge，验证回退是否成功。</span><span class="sxs-lookup"><span data-stu-id="ee499-139">Close and reopen Microsoft Edge to verify that the rollback worked.</span></span> <span data-ttu-id="ee499-140">在“**设置”和“更多**” (ALT + F) 下，转到 “**设置**”并选择“**关于 Microsoft Edge**”。</span><span class="sxs-lookup"><span data-stu-id="ee499-140">Under **Settings and more** (ALT + F), go to **Settings** and select **About Microsoft Edge**.</span></span>

## <span data-ttu-id="ee499-141">使用 Microsoft Edge 更新和组策略启用回退</span><span class="sxs-lookup"><span data-stu-id="ee499-141">Enable rollback with Microsoft Edge update and Group Policy</span></span>

<span data-ttu-id="ee499-142">按照以下步骤可使用 Microsoft Edge 更新和组策略启用回退。</span><span class="sxs-lookup"><span data-stu-id="ee499-142">Use the following steps to enable rollback with Microsoft Edge update and Group Policy.</span></span>

1. <span data-ttu-id="ee499-143">打开本地组策略编辑器，然后转到“*计算机配置”>“管理模板”>“Microsoft Edge 更新”>“应用程序”>“Microsoft edge”>*。</span><span class="sxs-lookup"><span data-stu-id="ee499-143">Open the local Group Policy Editor and go to *Computer Configuration>Administrative Templates>Microsoft Edge Update>Applications>Microsoft Edge>*.</span></span>
2. <span data-ttu-id="ee499-144">选择“**回退到目标版本**”，然后选择 “**已启用**”。</span><span class="sxs-lookup"><span data-stu-id="ee499-144">Select **Rollback to target version** and then select **Enabled**.</span></span>
3. <span data-ttu-id="ee499-145">选择“**目标版本替代**”，并选择要回退到的浏览器版本。</span><span class="sxs-lookup"><span data-stu-id="ee499-145">Select **Target version override** and pick the browser version you want to roll back to.</span></span>
4. <span data-ttu-id="ee499-146">选择“**更新策略替代**”，然后选择“**已启用**”。</span><span class="sxs-lookup"><span data-stu-id="ee499-146">Select **Update policy override** and then select **Enabled**.</span></span> <span data-ttu-id="ee499-147">在“**选项**”下，从“策略”下拉列表中选择以下选项之一（“**已禁用更新**”除外）：</span><span class="sxs-lookup"><span data-stu-id="ee499-147">Under **Options**, pick one of the following options from the Policy dropdown list (except for **Update disabled**):</span></span>

   - <span data-ttu-id="ee499-148">始终允许更新</span><span class="sxs-lookup"><span data-stu-id="ee499-148">Always allow updates</span></span>
   - <span data-ttu-id="ee499-149">仅自动静默更新</span><span class="sxs-lookup"><span data-stu-id="ee499-149">Automatic silent updates only</span></span>

     > [!NOTE]
     > <span data-ttu-id="ee499-150">若要强制执行组策略更新，请在 Windows 管理员命令提示处`dsregcmd /status`键入（以管理员身份运行）。</span><span class="sxs-lookup"><span data-stu-id="ee499-150">To force a group policy update, type `dsregcmd /status` at the Windows administrator Command Prompt (Run as administrator).</span></span>

5. <span data-ttu-id="ee499-151">单击**确定**保存策略设置。</span><span class="sxs-lookup"><span data-stu-id="ee499-151">Click **OK** to save the policy settings.</span></span> <span data-ttu-id="ee499-152">将在下次 Microsoft Edge 更新检查更新时执行回退。</span><span class="sxs-lookup"><span data-stu-id="ee499-152">Rollback will happen the next time Microsoft Edge Update checks for an update.</span></span> <span data-ttu-id="ee499-153">如果希望更快地进行更新，可以更改 Microsoft Edge 更新轮询间隔或使用 MSI 启用回退。</span><span class="sxs-lookup"><span data-stu-id="ee499-153">If you want the update to happen sooner, you can change the Microsoft Edge Update polling interval or enable rollback using an MSI.</span></span>

### <span data-ttu-id="ee499-154">常见回退错误</span><span class="sxs-lookup"><span data-stu-id="ee499-154">Common rollback errors</span></span>

<span data-ttu-id="ee499-155">以下错误将阻止回退：</span><span class="sxs-lookup"><span data-stu-id="ee499-155">The following errors will prevent rollback:</span></span>

- <span data-ttu-id="ee499-156">输入为不受支持的目标版本</span><span class="sxs-lookup"><span data-stu-id="ee499-156">Input is an unsupported target version</span></span>
- <span data-ttu-id="ee499-157">输入为不存在的目标版本</span><span class="sxs-lookup"><span data-stu-id="ee499-157">Input is a non-existent target version</span></span>
- <span data-ttu-id="ee499-158">输入未正确格式化。</span><span class="sxs-lookup"><span data-stu-id="ee499-158">Input is incorrectly formatted</span></span>

### <span data-ttu-id="ee499-159">推荐的组策略</span><span class="sxs-lookup"><span data-stu-id="ee499-159">Recommended Group Policies</span></span>

<span data-ttu-id="ee499-160">强烈推荐使用回退功能时采用以下组策略和设置。</span><span class="sxs-lookup"><span data-stu-id="ee499-160">The following group policies and settings are highly recommended for using rollback.</span></span>

#### <span data-ttu-id="ee499-161">同步组策略</span><span class="sxs-lookup"><span data-stu-id="ee499-161">Sync Group Policies</span></span>

- <span data-ttu-id="ee499-162">ForceSync.</span><span class="sxs-lookup"><span data-stu-id="ee499-162">ForceSync.</span></span> <span data-ttu-id="ee499-163">将 ForceSync 设置为“启用”。</span><span class="sxs-lookup"><span data-stu-id="ee499-163">Set ForceSync to enabled.</span></span> <span data-ttu-id="ee499-164">此策略将强制启用所有 Azure Active Directory (Azure AD) 用户的同步。</span><span class="sxs-lookup"><span data-stu-id="ee499-164">This policy will force enable Sync on all Azure Active Directory (Azure AD) users.</span></span> <span data-ttu-id="ee499-165">此策略仅适用于 Microsoft Edge 版本 86 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="ee499-165">This policy is only effective for Microsoft Edge versions 86 and later.</span></span>
- <span data-ttu-id="ee499-166">*配置从同步策略中排除的类型列表*允许管理员控制用户可同步哪些数据。</span><span class="sxs-lookup"><span data-stu-id="ee499-166">The *Configure the list of the types that are excluded from synchronization policy* allows admins to control what data can be synced by users.</span></span>

#### <span data-ttu-id="ee499-167">浏览器重新启动组策略</span><span class="sxs-lookup"><span data-stu-id="ee499-167">Browser restart Group Policies</span></span>

<span data-ttu-id="ee499-168">建议启用回退后，对用户强制重启。</span><span class="sxs-lookup"><span data-stu-id="ee499-168">We recommend forcing a restart on users after rollback is enabled.</span></span>

- <span data-ttu-id="ee499-169">启用*通知用户对于挂起的更新，推荐或需要重新启动浏览器*。</span><span class="sxs-lookup"><span data-stu-id="ee499-169">Enable *Notify a user that a browser restart is recommended or required for pending updates*.</span></span> <span data-ttu-id="ee499-170">在“选项”下，选择“**必需**”。</span><span class="sxs-lookup"><span data-stu-id="ee499-170">Under Options, select **Required**.</span></span>
- <span data-ttu-id="ee499-171">启用*设置更新通知时间段，然后设置所需时间（以毫秒为单位）*。</span><span class="sxs-lookup"><span data-stu-id="ee499-171">Enable *Set the time period for update notifications* and then set the desired time in milliseconds.</span></span>

## <span data-ttu-id="ee499-172">快照</span><span class="sxs-lookup"><span data-stu-id="ee499-172">Snapshot</span></span>

<span data-ttu-id="ee499-173">快照是用户数据文件夹的版本标记副本。</span><span class="sxs-lookup"><span data-stu-id="ee499-173">A snapshot is a version stamped copy of the user data folder.</span></span> <span data-ttu-id="ee499-174">在版本升级过程中，将生成以前版本的快照并将其存储在快照文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ee499-174">During a version upgrade, a snapshot of the previous version is made and stored in the snapshot folder.</span></span> <span data-ttu-id="ee499-175">在回退后，版本匹配的快照将被复制到新用户数据文件夹中，并从快照文件夹中删除。</span><span class="sxs-lookup"><span data-stu-id="ee499-175">After rollback occurs, a version matched snapshot will be copied into the new user data folder and deleted from the snapshot folder.</span></span> <span data-ttu-id="ee499-176">如果降级后没有版本匹配的快照可用，回退会依赖同步将用户数据写入到新 Microsoft Edge 版本中。</span><span class="sxs-lookup"><span data-stu-id="ee499-176">If no version matched snapshot is available upon downgrade, rollback will rely on Sync to populate user data into the new Microsoft Edge version.</span></span>

<span data-ttu-id="ee499-177">可借助 [UserDataSnapshotRetentionLimit] 组策略设置在任何给定时间内皆可以保留的快照数的限制。</span><span class="sxs-lookup"><span data-stu-id="ee499-177">The [UserDataSnapshotRetentionLimit] group policy allows you to set a limit for the number of snapshots that can be retained at any given time.</span></span> <span data-ttu-id="ee499-178">默认情况下，保留三个快照。</span><span class="sxs-lookup"><span data-stu-id="ee499-178">By default, three snapshots are kept.</span></span> <span data-ttu-id="ee499-179">您可以将此策略配置为保留 0-5 个快照。</span><span class="sxs-lookup"><span data-stu-id="ee499-179">You can configure this policy to keep from 0-5 snapshots.</span></span>

## <span data-ttu-id="ee499-180">常见问题</span><span class="sxs-lookup"><span data-stu-id="ee499-180">Frequently asked questions</span></span>

### <span data-ttu-id="ee499-181">手动 MSI 回退</span><span class="sxs-lookup"><span data-stu-id="ee499-181">Manual MSI rollback</span></span>

#### <span data-ttu-id="ee499-182">可能发生哪些常见 MSI 故障？</span><span class="sxs-lookup"><span data-stu-id="ee499-182">What generic MSI failures that can happen?</span></span>

1. <span data-ttu-id="ee499-183">如果禁用“安装更新”组策略，则不会发生回退。</span><span class="sxs-lookup"><span data-stu-id="ee499-183">If the Install update group policy is disabled, rollback won't occur.</span></span>

   - <span data-ttu-id="ee499-184">若要使用回退，请确保将“安装”设置为“**启用**”。</span><span class="sxs-lookup"><span data-stu-id="ee499-184">To use rollback, make sure Install is set to **Enabled**.</span></span> <span data-ttu-id="ee499-185">如果禁用此策略，将阻止安装 Microsoft Edge 频道。</span><span class="sxs-lookup"><span data-stu-id="ee499-185">When this policy is disabled, it prevents Microsoft Edge channels from being installed.</span></span> <span data-ttu-id="ee499-186">有关详细信息，请参阅[安装](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#install)。</span><span class="sxs-lookup"><span data-stu-id="ee499-186">For more information, see [Install](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#install).</span></span>

2. <span data-ttu-id="ee499-187">如果启发更新不存在，将阻止 Microsoft Edge 安装，除非已启用*允许 Microsoft Edge 并排浏览体验*。</span><span class="sxs-lookup"><span data-stu-id="ee499-187">If Enlightenment Updates aren't present, Microsoft Edge installations will be blocked unless *Allow Microsoft Edge Side by Side browser experience* is enabled.</span></span>

   - <span data-ttu-id="ee499-188">针对 Windows 版本 1903 和 1909：如果上次更新早于 2019 年 10 月，则可能会存在此问题。</span><span class="sxs-lookup"><span data-stu-id="ee499-188">For Windows versions 1903 and 1909: If your last update was before October 2019, you may have this issue.</span></span>
   - <span data-ttu-id="ee499-189">针对 Windows 版本 1709、1803 和 1809：如果上次更新早于 2019 年 11 月，则可能会存在此问题。</span><span class="sxs-lookup"><span data-stu-id="ee499-189">For Windows versions 1709, 1803, and 1809: If your last update was before November 2019, you may have this issue.</span></span><br>
<span data-ttu-id="ee499-190">有关详细信息，请参阅[用于支持下一版 Microsoft Edge 的 Windows 更新](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-windows-updates)。</span><span class="sxs-lookup"><span data-stu-id="ee499-190">For more information, see [Windows updates to support the next version of Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-windows-updates)</span></span>

#### <span data-ttu-id="ee499-191">使用命令提示但回退没发生后，显示以下错误消息。</span><span class="sxs-lookup"><span data-stu-id="ee499-191">The following error message was shown after using the Command Prompt and rollback didn't occur.</span></span> <span data-ttu-id="ee499-192">究竟是哪里出现错误？</span><span class="sxs-lookup"><span data-stu-id="ee499-192">What's wrong?</span></span>

![回退状态消息](./media/edge-learnmore-rollback/edge-rollback-cmd-flag-error.png)

<span data-ttu-id="ee499-194">*ALLOWDOWNGRADE = 1* 未执行。</span><span class="sxs-lookup"><span data-stu-id="ee499-194">*ALLOWDOWNGRADE=1* was not executed.</span></span>

### <span data-ttu-id="ee499-195">Microsoft Edge 更新和组策略回退</span><span class="sxs-lookup"><span data-stu-id="ee499-195">Microsoft Edge Update and Group Policy rollback</span></span>

#### <span data-ttu-id="ee499-196">我设置了*回退到目标版本*、启用了*更新策略替代*，且输入了*目标版本替代*希望回退到的浏览器版本，但浏览器版本不是我要回退到的版本。</span><span class="sxs-lookup"><span data-stu-id="ee499-196">I set *Rollback to target version*, enabled *Update policy override*, input my desired browser version for *Target version override*, but the browser version wasn't what I expected.</span></span> <span data-ttu-id="ee499-197">究竟是哪里出现错误？</span><span class="sxs-lookup"><span data-stu-id="ee499-197">What's wrong?</span></span>

<span data-ttu-id="ee499-198">以下常见错误会阻止回退：</span><span class="sxs-lookup"><span data-stu-id="ee499-198">Some common errors that prevent rollback are:</span></span>

- <span data-ttu-id="ee499-199">如果未设置回退到目标版本，将不会执行回退。</span><span class="sxs-lookup"><span data-stu-id="ee499-199">If Rollback to target version isn't set, rollback will not be executed.</span></span>
- <span data-ttu-id="ee499-200">目标版本替代设置存在以下问题之一：</span><span class="sxs-lookup"><span data-stu-id="ee499-200">There are one of the following issues with the target version override setting:</span></span>

  - <span data-ttu-id="ee499-201">目标版本替代被设置为不受支持的目标版本。</span><span class="sxs-lookup"><span data-stu-id="ee499-201">Target version override is set to an unsupported target version.</span></span>
  - <span data-ttu-id="ee499-202">目标版本替代被设置为不存在的目标版本。</span><span class="sxs-lookup"><span data-stu-id="ee499-202">Target version override is set to a non-existent target version.</span></span>
  - <span data-ttu-id="ee499-203">目标版本替代输入的格式不正确。</span><span class="sxs-lookup"><span data-stu-id="ee499-203">Target version override input is incorrectly formatted.</span></span>

- <span data-ttu-id="ee499-204">如果将”更新策略替代“设置为“禁用更新”，则 Microsoft Edge 更新不会接受任何更新，并且不会执行回退。</span><span class="sxs-lookup"><span data-stu-id="ee499-204">If Update policy override is set to "Updates disabled", Microsoft Edge Update won't accept any updates and rollback isn't executed.</span></span>

### <span data-ttu-id="ee499-205">我正确设置了所有组策略，但回退未执行。</span><span class="sxs-lookup"><span data-stu-id="ee499-205">I set all the group policies correctly, but rollback didn't execute.</span></span> <span data-ttu-id="ee499-206">发生了什么情况？</span><span class="sxs-lookup"><span data-stu-id="ee499-206">What happened?</span></span>

<span data-ttu-id="ee499-207">Microsoft Edge 更新尚未运行更新检查。</span><span class="sxs-lookup"><span data-stu-id="ee499-207">Microsoft Edge Update hasn't run a check for updates yet.</span></span> <span data-ttu-id="ee499-208">默认情况下，自动更新将每 10 小时检查一次更新。</span><span class="sxs-lookup"><span data-stu-id="ee499-208">By default, auto-update checks for updates every 10 hours.</span></span> <span data-ttu-id="ee499-209">可通过更改 Microsoft Edge 更新的轮询间隔来修复此问题，自动更新检查周期将覆盖组策略。</span><span class="sxs-lookup"><span data-stu-id="ee499-209">You can fix this issue by changing Microsoft Edge Update's polling interval with the Auto-update check period override group policy.</span></span> <span data-ttu-id="ee499-210">有关详细信息，请参阅 [AutoUpdateCheckPeriodMinutes](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#autoupdatecheckperiodminutes) 策略。</span><span class="sxs-lookup"><span data-stu-id="ee499-210">For more information, see the [AutoUpdateCheckPeriodMinutes](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#autoupdatecheckperiodminutes) policy.</span></span>

### <span data-ttu-id="ee499-211">作为 IT 管理员，我按照正确回退的所有步骤进行了操作。</span><span class="sxs-lookup"><span data-stu-id="ee499-211">As an IT admin, I followed all the steps for rollback correctly.</span></span> <span data-ttu-id="ee499-212">“我的用户组”的一部分已回退。</span><span class="sxs-lookup"><span data-stu-id="ee499-212">Only a portion of my user group was rolled back.</span></span> <span data-ttu-id="ee499-213">为什么尚未回退其他用户？</span><span class="sxs-lookup"><span data-stu-id="ee499-213">Why haven't the other users been rolled back yet?</span></span>

<span data-ttu-id="ee499-214">组策略设置尚未同步到所有客户端。</span><span class="sxs-lookup"><span data-stu-id="ee499-214">The group policy setting hasn't synced to all the clients yet.</span></span> <span data-ttu-id="ee499-215">当管理员设置组策略时，客户端不会立即收到这些设置。</span><span class="sxs-lookup"><span data-stu-id="ee499-215">When admins set a group policy, clients don't receive these settings instantaneously.</span></span> <span data-ttu-id="ee499-216">你可以[强制一个远程组策略刷新](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/jj134201(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="ee499-216">You can [Force a Remote Group Policy Refresh](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/jj134201(v=ws.11)).</span></span>


## <span data-ttu-id="ee499-217">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee499-217">See also</span></span>

- [<span data-ttu-id="ee499-218">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="ee499-218">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
