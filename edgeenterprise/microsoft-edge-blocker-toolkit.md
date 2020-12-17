---
title: 可禁止自动传递 Microsoft Edge 的阻止程序工具包
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 12/16/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 可禁止自动传递 Microsoft Edge 的阻止程序工具包
ms.openlocfilehash: 9fb97d2dfec4822f8ce76dc3e37b85118c6572ad
ms.sourcegitcommit: 606282995b466a968bab40c16005a6653323c763
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "11229613"
---
# <span data-ttu-id="641d4-103">可禁止自动传递 Microsoft Edge（基于 Chromium）的阻止程序工具包</span><span class="sxs-lookup"><span data-stu-id="641d4-103">Blocker Toolkit to disable automatic delivery of Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="641d4-104">本文介绍了可用于禁止自动传递和安装 Microsoft Edge 的阻止程序工具包，</span><span class="sxs-lookup"><span data-stu-id="641d4-104">This article describes the Blocker Toolkit for disabling automatic delivery and installation of Microsoft Edge.</span></span>

<span data-ttu-id="641d4-105">本文进行了以下更新：</span><span class="sxs-lookup"><span data-stu-id="641d4-105">The following updates have been made to this article:</span></span>

- <span data-ttu-id="641d4-106">**01/09/2020，** 详细了解可能要求你使用阻止程序Toolkit</span><span class="sxs-lookup"><span data-stu-id="641d4-106">**01/09/2020** with more information about devices that might require you to use the Blocker Toolkit</span></span>
- <span data-ttu-id="641d4-107">**2020 年 2 月 28** 日 从要从此自动更新中排除的设备条件中删除"MDM 托管"</span><span class="sxs-lookup"><span data-stu-id="641d4-107">**2/28/2020** to remove "MDM managed" from the criteria of devices to be excluded from this automatic update</span></span>
- <span data-ttu-id="641d4-108">**2020 年 6 月 30 日** 以反映所有已连接 Windows 更新的设备均在接收此更新 (2020 年 7 月 30 日)  </span><span class="sxs-lookup"><span data-stu-id="641d4-108">**6/30/2020** to reflect that all Windows Update connected devices are in scope to receive this update (effective no sooner than 7/30/2020)</span></span>
- <span data-ttu-id="641d4-109">**2020 年 12 月 10** 日 解释 20H2 之前将忽略阻止程序Toolkit的情况</span><span class="sxs-lookup"><span data-stu-id="641d4-109">**12/10/2020** to explain pre 20H2 situations in which the Blocker Toolkit settings will be ignored</span></span>

> [!NOTE]
> <span data-ttu-id="641d4-110">适用于 Microsoft Edge 稳定渠道。</span><span class="sxs-lookup"><span data-stu-id="641d4-110">This applies to Microsoft Edge Stable channel.</span></span>

## <span data-ttu-id="641d4-111">概述</span><span class="sxs-lookup"><span data-stu-id="641d4-111">Overview</span></span>

<span data-ttu-id="641d4-112">为了帮助客户更安全和保持最新，Microsoft 将 Microsoft Edge（基于 Chromium）分发到运行 Windows 10 版本 1803 和更新版本的 Windows 更新连接设备。</span><span class="sxs-lookup"><span data-stu-id="641d4-112">To help our customers become more secure and up-to-date, Microsoft will distribute Microsoft Edge (Chromium-based) to all Windows Update-connected devices running Windows 10 version 1803 and newer.</span></span> <span data-ttu-id="641d4-113">此过程将于 2020 年 1 月 15 日后启动，届时将提供更多信息。</span><span class="sxs-lookup"><span data-stu-id="641d4-113">This process will start after January 15, 2020 and more information will be available on that date.</span></span>

<span data-ttu-id="641d4-114">阻止程序工具包适用于以下组织：计划在运行 Windows 10 版本 1803 和更高版本的 Winodws 更新连接设备上阻止自动传递 Microsoft Edge（基于 Chromium）。</span><span class="sxs-lookup"><span data-stu-id="641d4-114">The Blocker Toolkit is intended for organizations that would like to block automatic delivery of Microsoft Edge (Chromium-based) to Windows Updated-connected devices running Windows 10 version 1803 and newer.</span></span> <span data-ttu-id="641d4-115">属于 Windows Server Update Services (WSUS) 或适用于企业的 Windows 更新 (WUfB) 的设备将从此自动 Windows 更新中排除，但可能会通过其组织接收新的 (基于 Chromium 的) Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="641d4-115">Devices that are Windows Server Update Services (WSUS) or Windows Update for Business (WUfB) managed will be excluded from this automatic Windows Update, but may receive the new Microsoft Edge (Chromium-based) through their organization.</span></span>

**<span data-ttu-id="641d4-116">请务必注意：</span><span class="sxs-lookup"><span data-stu-id="641d4-116">It's important to note that:</span></span>**

- <span data-ttu-id="641d4-117">阻止程序工具包不会阻止用户从 Internet 下载或外部介质手动安装 Microsoft Edge（基于 Chromium）。</span><span class="sxs-lookup"><span data-stu-id="641d4-117">The Blocker Toolkit will not prevent users from manually installing Microsoft Edge (Chromium-based) from Internet download, or from external media.</span></span>
- <span data-ttu-id="641d4-118">通过适用于企业的 Windows 更新 (WUfB) 管理更新的组织将不会自动收到此更新，也不需要部署阻止程序工具包。</span><span class="sxs-lookup"><span data-stu-id="641d4-118">Organizations with updates managed through Windows Update for Business (WUfB) will not automatically receive this update and do not need to deploy the blocker toolkit.</span></span>
- <span data-ttu-id="641d4-119">通过更新管理解决方案（如 Windows Server Update Services (WSUS) 或 System Center Configuration Manager (SCCM)）管理环境的组织无需部署阻止程序工具包。</span><span class="sxs-lookup"><span data-stu-id="641d4-119">Organizations with environments managed with an update management solution such as Windows Server Update Services (WSUS) or System Center Configuration Manager (SCCM) do not have to deploy the Blocker Toolkit.</span></span> <span data-ttu-id="641d4-120">他们可以使用这些产品在其环境中完全管理通过 Windows 更新网站和 Microsoft 更新网站发布的更新的部署，包括 [WSUS](https://support.microsoft.com/help/4584642/update-in-wsus-for-the-new-microsoft-edge)中新 Microsoft Edge 的更新。</span><span class="sxs-lookup"><span data-stu-id="641d4-120">They can use those products to fully manage deployment of updates released through Windows Update and Microsoft Update, including the [Update in WSUS for the new Microsoft Edge](https://support.microsoft.com/help/4584642/update-in-wsus-for-the-new-microsoft-edge), within their environment.</span></span>
- <span data-ttu-id="641d4-121">此更新是独立更新（不是每月累积更新的一部分），可向企业客户提供灵活性，并使其能够最大程度地控制如何部署此更新。</span><span class="sxs-lookup"><span data-stu-id="641d4-121">This update is a stand-alone update (not part of the monthly cumulative update) to give Enterprise customers flexibility and maximum control over deploying this update.</span></span>
- <span data-ttu-id="641d4-122">新的 Microsoft Edge (Chromium) 包含在 2020 年下半年的 Windows 10 版本 20H2 功能更新中。</span><span class="sxs-lookup"><span data-stu-id="641d4-122">The new Microsoft Edge (Chromium-based) is included as part of the Windows 10, version 20H2 feature update in the second half of 2020.</span></span> <span data-ttu-id="641d4-123">阻止程序工具包不会影响 20H2 的行为或部署。</span><span class="sxs-lookup"><span data-stu-id="641d4-123">The Blocker toolkit does not impact 20H2 behaviors or deployment.</span></span> <span data-ttu-id="641d4-124">了解更多信息，请参阅[此处](https://blogs.windows.com/windowsexperience/2020/06/16/whats-next-for-windows-10-updates/) Windows 10，版本 20H2。 </span><span class="sxs-lookup"><span data-stu-id="641d4-124">See more information about Windows 10, version 20H2 [here](https://blogs.windows.com/windowsexperience/2020/06/16/whats-next-for-windows-10-updates/).</span></span>

<span data-ttu-id="641d4-125">你可以从 [https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe](https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe) 下载阻止程序工具包的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="641d4-125">You can download the Blocker Toolkit executable file from [https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe](https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe).</span></span>

### <span data-ttu-id="641d4-126">工具包组件</span><span class="sxs-lookup"><span data-stu-id="641d4-126">Toolkit components</span></span>

<span data-ttu-id="641d4-127">本工具包包含以下组件：</span><span class="sxs-lookup"><span data-stu-id="641d4-127">This toolkit contains the following components:</span></span>

- <span data-ttu-id="641d4-128">阻止程序脚本可执行文件 (.CMD)</span><span class="sxs-lookup"><span data-stu-id="641d4-128">Executable blocker script (.CMD)</span></span>
- <span data-ttu-id="641d4-129">组策略管理模板（.ADMX 和 .ADML）</span><span class="sxs-lookup"><span data-stu-id="641d4-129">Group Policy Administrative Template (.ADMX and .ADML)</span></span>

### <span data-ttu-id="641d4-130">支持的操作系统</span><span class="sxs-lookup"><span data-stu-id="641d4-130">Supported Operating Systems</span></span>

<span data-ttu-id="641d4-131">Windows 10 版本 1803 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="641d4-131">Windows 10 version 1803 and newer.</span></span>

## <span data-ttu-id="641d4-132">阻止程序脚本</span><span class="sxs-lookup"><span data-stu-id="641d4-132">Blocker script</span></span>

<span data-ttu-id="641d4-133">该脚本可在本地计算机或远程目标计算机上创建注册表项，并将关联的值设置为阻止或取消阻止（具体取决于所使用的命令行选项）Microsoft Edge（基于 Chromium）的自动传递。</span><span class="sxs-lookup"><span data-stu-id="641d4-133">The script creates a registry key and sets the associated value to block or unblock (depending on the command-line option used) automatic delivery of Microsoft Edge (Chromium-based) on either the local machine or a remote target machine.</span></span>

**<span data-ttu-id="641d4-134">注册表项：</span><span class="sxs-lookup"><span data-stu-id="641d4-134">Registry key:</span></span>** `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate`<br>
**<span data-ttu-id="641d4-135">注册表项名称：</span><span class="sxs-lookup"><span data-stu-id="641d4-135">Key value name:</span></span>** `DoNotUpdateToEdgeWithChromium`

| <span data-ttu-id="641d4-136">值</span><span class="sxs-lookup"><span data-stu-id="641d4-136">Value</span></span>                | <span data-ttu-id="641d4-137">结果</span><span class="sxs-lookup"><span data-stu-id="641d4-137">Result</span></span>                         |
|----------------------|--------------------------------|
| *<span data-ttu-id="641d4-138">未定义注册表项</span><span class="sxs-lookup"><span data-stu-id="641d4-138">Key is not defined</span></span>* | <span data-ttu-id="641d4-139">将*不会*阻止分发。</span><span class="sxs-lookup"><span data-stu-id="641d4-139">Distribution is *not* blocked.</span></span> |
| <span data-ttu-id="641d4-140">0</span><span class="sxs-lookup"><span data-stu-id="641d4-140">0</span></span>                    | <span data-ttu-id="641d4-141">将*不会*阻止分发。</span><span class="sxs-lookup"><span data-stu-id="641d4-141">Distribution is *not* blocked.</span></span> |
| <span data-ttu-id="641d4-142">1</span><span class="sxs-lookup"><span data-stu-id="641d4-142">1</span></span>                    | <span data-ttu-id="641d4-143">将阻止分发。</span><span class="sxs-lookup"><span data-stu-id="641d4-143">Distribution is blocked.</span></span>       |

<span data-ttu-id="641d4-144">此脚本具有以下命令行语法：</span><span class="sxs-lookup"><span data-stu-id="641d4-144">The script has the following command-line syntax:</span></span><br>
`EdgeChromium_Blocker.cmd [<machine name>] [/B] [/U] [/H]`

### <span data-ttu-id="641d4-145">计算机名</span><span class="sxs-lookup"><span data-stu-id="641d4-145">Machine name</span></span>

<span data-ttu-id="641d4-146">`<machine name>` 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="641d4-146">The `<machine name>` parameter is optional.</span></span> <span data-ttu-id="641d4-147">如果未指定，则在本地计算机上执行操作。</span><span class="sxs-lookup"><span data-stu-id="641d4-147">If not specified, the action is performed on the local machine.</span></span> <span data-ttu-id="641d4-148">否则，将通过 `REG` 命令的远程注册表功能访问远程计算机。</span><span class="sxs-lookup"><span data-stu-id="641d4-148">Otherwise, the remote machine is accessed through the remote registry capabilities of the `REG` command.</span></span> <span data-ttu-id="641d4-149">如果由于安全权限而导致无法访问远程注册表，或者找不到远程计算机，`REG` 命令将返回一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="641d4-149">If the remote registry can't be accessed due to security permissions or the remote machine can't be found, an error message is returned from the `REG` command.</span></span>

### <span data-ttu-id="641d4-150">开关</span><span class="sxs-lookup"><span data-stu-id="641d4-150">Switches</span></span>

<span data-ttu-id="641d4-151">脚本使用的开关是互斥的，因此将仅对给定命令中的第一个有效开关进行操作。</span><span class="sxs-lookup"><span data-stu-id="641d4-151">Switches used by the script are mutually exclusive and only the first valid switch from a given command is acted on.</span></span> <span data-ttu-id="641d4-152">可在同一台计算机上多次运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="641d4-152">The script can be run multiple times on the same machine.</span></span>

| <span data-ttu-id="641d4-153">开关</span><span class="sxs-lookup"><span data-stu-id="641d4-153">Switch</span></span>       | <span data-ttu-id="641d4-154">描述</span><span class="sxs-lookup"><span data-stu-id="641d4-154">Description</span></span>                              |
|--------------|------------------------------------------|
| `/B`         | <span data-ttu-id="641d4-155">将阻止分发</span><span class="sxs-lookup"><span data-stu-id="641d4-155">Blocks distribution</span></span>                      |
| `/U`         | <span data-ttu-id="641d4-156">将取消阻止分发</span><span class="sxs-lookup"><span data-stu-id="641d4-156">Unblocks distribution</span></span>                    |
| `/H` <span data-ttu-id="641d4-157">或者</span><span class="sxs-lookup"><span data-stu-id="641d4-157">or</span></span> `/?` | <span data-ttu-id="641d4-158">将显示以下摘要帮助：</span><span class="sxs-lookup"><span data-stu-id="641d4-158">Displays the following summary help:</span></span><br>`This tool can be used to remotely block or unblock the delivery of Microsoft Edge (Chromium-based) through Automatic Updates.`<br> `Usage:`<br>`EdgeChromium_Blocker.cmd [<machine name>] [/B][/U][/H]`<br>`B = Block Microsoft Edge (Chromium-based) deployment`<br>`U = Allow Microsoft Edge (Chromium-based) deployment`<br>`H = Help`<br>`Examples:`<br>`EdgeChromium_Blocker.cmd mymachine /B (blocks delivery on machine "mymachine")`<br>`EdgeChromium_Blocker.cmd /U (unblocks delivery on the local machine)`<br> |

## <span data-ttu-id="641d4-159">组策略管理模板（.ADMX 和 .ADML 文件）</span><span class="sxs-lookup"><span data-stu-id="641d4-159">Group Policy Administrative Template (.ADMX and .ADML files)</span></span>

<span data-ttu-id="641d4-160">组策略管理模板（.ADMX 和 .ADML 文件）允许管理员导入新的组策略设置，以阻止或取消阻止将 Microsoft Edge（基于 Chromium）自动传递到他们的组策略环境中，并使用组策略在其环境中的各个系统之间集中执行操作。</span><span class="sxs-lookup"><span data-stu-id="641d4-160">The Group Policy Administrative Template (.ADMX  and .ADML files) allows administrators to import the new Group Policy settings to block or unblock automatic delivery of Microsoft Edge (Chromium-based) into their Group Policy environment, and use Group Policy to centrally execute the action across systems in their environment.</span></span>

<span data-ttu-id="641d4-161">运行 Windows 10 RS3 Enterprise/EDU 和 RS4 及更高版本的用户将在以下路径下看到策略：</span><span class="sxs-lookup"><span data-stu-id="641d4-161">Users running Windows 10 RS3 Enterprise/EDU and RS4 and newer, will see the policy under the following path:</span></span>

```
/Computer Configuration  
  /Administrative Templates
    /Classic Administrative Templates
      /Windows Components
        /Windows Update  
          /Microsoft Edge (Chromium-based) Blockers  
```

<span data-ttu-id="641d4-162">此设置只能用作计算机设置；没有每用户设置。</span><span class="sxs-lookup"><span data-stu-id="641d4-162">This setting is available only as a Computer setting; there is no Per-User setting.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="641d4-163">此注册表设置未存储在策略注册表项中，并且被视为*首选项*。</span><span class="sxs-lookup"><span data-stu-id="641d4-163">This registry setting isn't stored in a policies key and is considered a *preference*.</span></span> <span data-ttu-id="641d4-164">因此，如果实现该设置的组策略对象已被删除或策略设置为**未配置**，该设置将保留。</span><span class="sxs-lookup"><span data-stu-id="641d4-164">Therefore, if the Group Policy Object that implements the setting is ever removed or the policy is set to **Not Configured**, the setting will remain.</span></span> <span data-ttu-id="641d4-165">要通过使用组策略来取消阻止 Microsoft Edge（基于 Chromium）的分发，请将策略设置为**已禁用**。</span><span class="sxs-lookup"><span data-stu-id="641d4-165">To unblock distribution of Microsoft Edge (Chromium-based) by using Group Policy, set the policy to **Disabled**.</span></span>

## <span data-ttu-id="641d4-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="641d4-166">See also</span></span>

- [<span data-ttu-id="641d4-167">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="641d4-167">Microsoft Edge Enterprise landing page</span></span>](https://www.microsoftedgeinsider.com/enterprise)
- [<span data-ttu-id="641d4-168">用于支持 Microsoft Edge 的 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="641d4-168">Windows updates to support Microsoft Edge</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-windows-updates)
- [<span data-ttu-id="641d4-169">如何访问旧版本的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="641d4-169">How to access the old version of Microsoft Edge</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-access-old-edge)
