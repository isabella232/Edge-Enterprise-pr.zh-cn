---
title: 可禁止自动传递 Microsoft Edge 的阻止程序工具包
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 06/30/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 可禁止自动传递 Microsoft Edge 的阻止程序工具包
ms.openlocfilehash: 7563d2c94cf91a8434328699e46c75dbcfb77561
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979365"
---
# <span data-ttu-id="efca1-103">可禁止自动传递 Microsoft Edge（基于 Chromium）的阻止程序工具包</span><span class="sxs-lookup"><span data-stu-id="efca1-103">Blocker Toolkit to disable automatic delivery of Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="efca1-104">本文介绍了可用于禁止自动传递和安装 Microsoft Edge 的阻止程序工具包，</span><span class="sxs-lookup"><span data-stu-id="efca1-104">This article describes the Blocker Toolkit for disabling automatic delivery and installation of Microsoft Edge.</span></span> <span data-ttu-id="efca1-105">本文在 **2020 年 1 月 9 日**更新可能需要使用组织程序工具包的设备详细信息，并在 **2020 年 2 月 28 日**从设备条件中删除了“MDM 托管”，以从此自动更新中排除，**2020 年 6 月 30 日** 将反映所有 Windows 更新连接设备都在接收此更新的范围内（最早于 2020 年 7 月 30 日生效）。</span><span class="sxs-lookup"><span data-stu-id="efca1-105">This article was updated on **01/09/2020** with more information about devices that might require you to use the Blocker Toolkit, on **2/28/2020** to remove "MDM managed" from the criteria of devices to be excluded from this automatic update, and on **6/30/2020** to reflect that all Windows Update connected devices are in scope to receive this update (effective no sooner than 7/30/2020).</span></span>

> [!NOTE]
> <span data-ttu-id="efca1-106">适用于 Microsoft Edge 稳定渠道。</span><span class="sxs-lookup"><span data-stu-id="efca1-106">This applies to Microsoft Edge Stable channel.</span></span>

## <span data-ttu-id="efca1-107">概述</span><span class="sxs-lookup"><span data-stu-id="efca1-107">Overview</span></span>

<span data-ttu-id="efca1-108">为了帮助客户更安全和保持最新，Microsoft 将 Microsoft Edge（基于 Chromium）分发到运行 Windows 10 版本 1803 和更新版本的 Windows 更新连接设备。</span><span class="sxs-lookup"><span data-stu-id="efca1-108">To help our customers become more secure and up-to-date, Microsoft will distribute Microsoft Edge (Chromium-based) to all Windows Update-connected devices running Windows 10 version 1803 and newer.</span></span> <span data-ttu-id="efca1-109">此过程将于 2020 年 1 月 15 日后启动，届时将提供更多信息。</span><span class="sxs-lookup"><span data-stu-id="efca1-109">This process will start after January 15, 2020 and more information will be available on that date.</span></span>

<span data-ttu-id="efca1-110">阻止程序工具包适用于以下组织：计划在运行 Windows 10 版本 1803 和更高版本的 Winodws 更新连接设备上阻止自动传递 Microsoft Edge（基于 Chromium）。</span><span class="sxs-lookup"><span data-stu-id="efca1-110">The Blocker Toolkit is intended for organizations that would like to block automatic delivery of Microsoft Edge (Chromium-based) to Windows Updated-connected devices running Windows 10 version 1803 and newer.</span></span>
<span data-ttu-id="efca1-111">受 Windows Server Update Services (WSUS) 或适用于企业的 Windows 更新 (WUfB) 管理的设备将从该自动更新中排除。</span><span class="sxs-lookup"><span data-stu-id="efca1-111">Devices that are Windows Server Update Services (WSUS) or Windows Update for Business (WUfB) managed will be excluded from this automatic update.</span></span>

**<span data-ttu-id="efca1-112">请务必注意：</span><span class="sxs-lookup"><span data-stu-id="efca1-112">It's important to note that:</span></span>**

- <span data-ttu-id="efca1-113">阻止程序工具包不会阻止用户从 Internet 下载或外部介质手动安装 Microsoft Edge（基于 Chromium）。</span><span class="sxs-lookup"><span data-stu-id="efca1-113">The Blocker Toolkit will not prevent users from manually installing Microsoft Edge (Chromium-based) from Internet download, or from external media.</span></span>
- <span data-ttu-id="efca1-114">通过适用于企业的 Windows 更新 (WUfB) 管理更新的组织将不会自动收到此更新，也不需要部署阻止程序工具包。</span><span class="sxs-lookup"><span data-stu-id="efca1-114">Organizations with updates managed through Windows Update for Business (WUfB) will not automatically receive this update and do not need to deploy the blocker toolkit.</span></span>
- <span data-ttu-id="efca1-115">通过更新管理解决方案（如 Windows Server Update Services (WSUS) 或 System Center Configuration Manager (SCCM)）管理环境的组织无需部署阻止程序工具包。</span><span class="sxs-lookup"><span data-stu-id="efca1-115">Organizations with environments managed with an update management solution such as Windows Server Update Services (WSUS) or System Center Configuration Manager (SCCM) do not have to deploy the Blocker Toolkit.</span></span> <span data-ttu-id="efca1-116">组织可以使用这些产品全面管理环境中通过 Windows 更新和 Microsoft 更新发布的更新的部署，包括 Microsoft Edge（基于 Chromium）。</span><span class="sxs-lookup"><span data-stu-id="efca1-116">They can use those products to fully manage deployment of updates released through Windows Update and Microsoft Update, including Microsoft Edge (Chromium-based), within their environment.</span></span>
- <span data-ttu-id="efca1-117">此更新是独立更新（不是每月累积更新的一部分），可向企业客户提供灵活性，并使其能够最大程度地控制如何部署此更新。</span><span class="sxs-lookup"><span data-stu-id="efca1-117">This update is a stand-alone update (not part of the monthly cumulative update) to give Enterprise customers flexibility and maximum control over deploying this update.</span></span>
- <span data-ttu-id="efca1-118">新的 Microsoft Edge（基于Chromium）将在 2020 年下半年作为 Windows 10，版本 20H2 功能更新的一部分。</span><span class="sxs-lookup"><span data-stu-id="efca1-118">The new Microsoft Edge (Chromium-based) will be included as part of the Windows 10, version 20H2 feature update in the second half of 2020.</span></span> <span data-ttu-id="efca1-119">阻止程序工具包不会影响 20H2 的行为或部署。</span><span class="sxs-lookup"><span data-stu-id="efca1-119">The Blocker toolkit does not impact 20H2 behaviors or deployment.</span></span> <span data-ttu-id="efca1-120">了解更多信息，请参阅[此处](https://blogs.windows.com/windowsexperience/2020/06/16/whats-next-for-windows-10-updates/) Windows 10，版本 20H2。 </span><span class="sxs-lookup"><span data-stu-id="efca1-120">See more information about Windows 10, version 20H2 [here](https://blogs.windows.com/windowsexperience/2020/06/16/whats-next-for-windows-10-updates/).</span></span>

<span data-ttu-id="efca1-121">你可以从 [https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe](https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe) 下载阻止程序工具包的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="efca1-121">You can download the Blocker Toolkit executable file from [https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe](https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe).</span></span>

### <span data-ttu-id="efca1-122">工具包组件</span><span class="sxs-lookup"><span data-stu-id="efca1-122">Toolkit components</span></span>

<span data-ttu-id="efca1-123">本工具包包含以下组件：</span><span class="sxs-lookup"><span data-stu-id="efca1-123">This toolkit contains the following components:</span></span>

- <span data-ttu-id="efca1-124">阻止程序脚本可执行文件 (.CMD)</span><span class="sxs-lookup"><span data-stu-id="efca1-124">Executable blocker script (.CMD)</span></span>
- <span data-ttu-id="efca1-125">组策略管理模板（.ADMX 和 .ADML）</span><span class="sxs-lookup"><span data-stu-id="efca1-125">Group Policy Administrative Template (.ADMX and .ADML)</span></span>

### <span data-ttu-id="efca1-126">支持的操作系统</span><span class="sxs-lookup"><span data-stu-id="efca1-126">Supported Operating Systems</span></span>

<span data-ttu-id="efca1-127">Windows 10 版本 1803 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="efca1-127">Windows 10 version 1803 and newer.</span></span>

## <span data-ttu-id="efca1-128">阻止程序脚本</span><span class="sxs-lookup"><span data-stu-id="efca1-128">Blocker script</span></span>

<span data-ttu-id="efca1-129">该脚本可在本地计算机或远程目标计算机上创建注册表项，并将关联的值设置为阻止或取消阻止（具体取决于所使用的命令行选项）Microsoft Edge（基于 Chromium）的自动传递。</span><span class="sxs-lookup"><span data-stu-id="efca1-129">The script creates a registry key and sets the associated value to block or unblock (depending on the command-line option used) automatic delivery of Microsoft Edge (Chromium-based) on either the local machine or a remote target machine.</span></span>

**<span data-ttu-id="efca1-130">注册表项：</span><span class="sxs-lookup"><span data-stu-id="efca1-130">Registry key:</span></span>** `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate`<br>
**<span data-ttu-id="efca1-131">注册表项名称：</span><span class="sxs-lookup"><span data-stu-id="efca1-131">Key value name:</span></span>** `DoNotUpdateToEdgeWithChromium`

| <span data-ttu-id="efca1-132">值</span><span class="sxs-lookup"><span data-stu-id="efca1-132">Value</span></span>                | <span data-ttu-id="efca1-133">结果</span><span class="sxs-lookup"><span data-stu-id="efca1-133">Result</span></span>                         |
|----------------------|--------------------------------|
| *<span data-ttu-id="efca1-134">未定义注册表项</span><span class="sxs-lookup"><span data-stu-id="efca1-134">Key is not defined</span></span>* | <span data-ttu-id="efca1-135">将*不会*阻止分发。</span><span class="sxs-lookup"><span data-stu-id="efca1-135">Distribution is *not* blocked.</span></span> |
| <span data-ttu-id="efca1-136">0</span><span class="sxs-lookup"><span data-stu-id="efca1-136">0</span></span>                    | <span data-ttu-id="efca1-137">将*不会*阻止分发。</span><span class="sxs-lookup"><span data-stu-id="efca1-137">Distribution is *not* blocked.</span></span> |
| <span data-ttu-id="efca1-138">1</span><span class="sxs-lookup"><span data-stu-id="efca1-138">1</span></span>                    | <span data-ttu-id="efca1-139">将阻止分发。</span><span class="sxs-lookup"><span data-stu-id="efca1-139">Distribution is blocked.</span></span>       |

<span data-ttu-id="efca1-140">此脚本具有以下命令行语法：</span><span class="sxs-lookup"><span data-stu-id="efca1-140">The script has the following command-line syntax:</span></span><br>
`EdgeChromium_Blocker.cmd [<machine name>] [/B] [/U] [/H]`

### <span data-ttu-id="efca1-141">计算机名</span><span class="sxs-lookup"><span data-stu-id="efca1-141">Machine name</span></span>

<span data-ttu-id="efca1-142">`<machine name>` 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="efca1-142">The `<machine name>` parameter is optional.</span></span> <span data-ttu-id="efca1-143">如果未指定，则在本地计算机上执行操作。</span><span class="sxs-lookup"><span data-stu-id="efca1-143">If not specified, the action is performed on the local machine.</span></span> <span data-ttu-id="efca1-144">否则，将通过 `REG` 命令的远程注册表功能访问远程计算机。</span><span class="sxs-lookup"><span data-stu-id="efca1-144">Otherwise, the remote machine is accessed through the remote registry capabilities of the `REG` command.</span></span> <span data-ttu-id="efca1-145">如果由于安全权限而导致无法访问远程注册表，或者找不到远程计算机，`REG` 命令将返回一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="efca1-145">If the remote registry can't be accessed due to security permissions or the remote machine can't be found, an error message is returned from the `REG` command.</span></span>

### <span data-ttu-id="efca1-146">开关</span><span class="sxs-lookup"><span data-stu-id="efca1-146">Switches</span></span>

<span data-ttu-id="efca1-147">脚本使用的开关是互斥的，因此将仅对给定命令中的第一个有效开关进行操作。</span><span class="sxs-lookup"><span data-stu-id="efca1-147">Switches used by the script are mutually exclusive and only the first valid switch from a given command is acted on.</span></span> <span data-ttu-id="efca1-148">可在同一台计算机上多次运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="efca1-148">The script can be run multiple times on the same machine.</span></span>

| <span data-ttu-id="efca1-149">开关</span><span class="sxs-lookup"><span data-stu-id="efca1-149">Switch</span></span>       | <span data-ttu-id="efca1-150">描述</span><span class="sxs-lookup"><span data-stu-id="efca1-150">Description</span></span>                              |
|--------------|------------------------------------------|
| `/B`         | <span data-ttu-id="efca1-151">将阻止分发</span><span class="sxs-lookup"><span data-stu-id="efca1-151">Blocks distribution</span></span>                      |
| `/U`         | <span data-ttu-id="efca1-152">将取消阻止分发</span><span class="sxs-lookup"><span data-stu-id="efca1-152">Unblocks distribution</span></span>                    |
| `/H` <span data-ttu-id="efca1-153">或者</span><span class="sxs-lookup"><span data-stu-id="efca1-153">or</span></span> `/?` | <span data-ttu-id="efca1-154">将显示以下摘要帮助：</span><span class="sxs-lookup"><span data-stu-id="efca1-154">Displays the following summary help:</span></span><br>`This tool can be used to remotely block or unblock the delivery of Microsoft Edge (Chromium-based) through Automatic Updates.`<br> `Usage:`<br>`EdgeChromium_Blocker.cmd [<machine name>] [/B][/U][/H]`<br>`B = Block Microsoft Edge (Chromium-based) deployment`<br>`U = Allow Microsoft Edge (Chromium-based) deployment`<br>`H = Help`<br>`Examples:`<br>`EdgeChromium_Blocker.cmd mymachine /B (blocks delivery on machine "mymachine")`<br>`EdgeChromium_Blocker.cmd /U (unblocks delivery on the local machine)`<br> |

## <span data-ttu-id="efca1-155">组策略管理模板（.ADMX 和 .ADML 文件）</span><span class="sxs-lookup"><span data-stu-id="efca1-155">Group Policy Administrative Template (.ADMX and .ADML files)</span></span>

<span data-ttu-id="efca1-156">组策略管理模板（.ADMX 和 .ADML 文件）允许管理员导入新的组策略设置，以阻止或取消阻止将 Microsoft Edge（基于 Chromium）自动传递到他们的组策略环境中，并使用组策略在其环境中的各个系统之间集中执行操作。</span><span class="sxs-lookup"><span data-stu-id="efca1-156">The Group Policy Administrative Template (.ADMX  and .ADML files) allows administrators to import the new Group Policy settings to block or unblock automatic delivery of Microsoft Edge (Chromium-based) into their Group Policy environment, and use Group Policy to centrally execute the action across systems in their environment.</span></span>

<span data-ttu-id="efca1-157">运行 Windows 10 RS3 Enterprise/EDU 和 RS4 及更高版本的用户将在以下路径下看到策略：</span><span class="sxs-lookup"><span data-stu-id="efca1-157">Users running Windows 10 RS3 Enterprise/EDU and RS4 and newer, will see the policy under the following path:</span></span>

```
/Computer Configuration  
  /Administrative Templates
    /Classic Administrative Templates
      /Windows Components
        /Windows Update  
          /Microsoft Edge (Chromium-based) Blockers  
```

<span data-ttu-id="efca1-158">此设置只能用作计算机设置；没有每用户设置。</span><span class="sxs-lookup"><span data-stu-id="efca1-158">This setting is available only as a Computer setting; there is no Per-User setting.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="efca1-159">此注册表设置未存储在策略注册表项中，并且被视为*首选项*。</span><span class="sxs-lookup"><span data-stu-id="efca1-159">This registry setting isn't stored in a policies key and is considered a *preference*.</span></span> <span data-ttu-id="efca1-160">因此，如果实现该设置的组策略对象已被删除或策略设置为**未配置**，该设置将保留。</span><span class="sxs-lookup"><span data-stu-id="efca1-160">Therefore, if the Group Policy Object that implements the setting is ever removed or the policy is set to **Not Configured**, the setting will remain.</span></span> <span data-ttu-id="efca1-161">要通过使用组策略来取消阻止 Microsoft Edge（基于 Chromium）的分发，请将策略设置为**已禁用**。</span><span class="sxs-lookup"><span data-stu-id="efca1-161">To unblock distribution of Microsoft Edge (Chromium-based) by using Group Policy, set the policy to **Disabled**.</span></span>

## <span data-ttu-id="efca1-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="efca1-162">See also</span></span>

- [<span data-ttu-id="efca1-163">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="efca1-163">Microsoft Edge Enterprise landing page</span></span>](https://www.microsoftedgeinsider.com/enterprise)
- [<span data-ttu-id="efca1-164">用于支持 Microsoft Edge 的 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="efca1-164">Windows updates to support Microsoft Edge</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-windows-updates)
- [<span data-ttu-id="efca1-165">如何访问旧版本的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="efca1-165">How to access the old version of Microsoft Edge</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-access-old-edge)
