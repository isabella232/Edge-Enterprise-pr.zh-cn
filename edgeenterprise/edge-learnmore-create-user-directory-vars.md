---
title: 创建 Microsoft Edge 用户数据目录变量
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 05/01/2020
audience: ITPro
ms.topic: procedural
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解如何创建 Microsoft Edge 用户数据目录变量
ms.openlocfilehash: 284bef9156dc3dff1413f349eebe4e7dac854a98
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979347"
---
# <span data-ttu-id="bf4f8-103">创建 Microsoft Edge 用户数据目录变量</span><span class="sxs-lookup"><span data-stu-id="bf4f8-103">Create Microsoft Edge user data directory variables</span></span>

<span data-ttu-id="bf4f8-104">本文介绍了如何在修改 Microsoft Edge 时使用数据目录变量，而不是使用硬编码路径。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-104">This article explains how you can use data directory variables instead of using hard-coded paths when modifying Microsoft Edge.</span></span>

>[!NOTE]
><span data-ttu-id="bf4f8-105">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="bf4f8-106">路径变量</span><span class="sxs-lookup"><span data-stu-id="bf4f8-106">Path variables</span></span>

<span data-ttu-id="bf4f8-107">用于修改数据目录路径的策略（例如，配置 [UserDataDir](microsoft-edge-policies.md#userdatadir) 或 [DownloadDirectory](microsoft-edge-policies.md#downloaddirectory) 支持变量。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-107">Policies for modifying data directory paths (For example, configuring the [UserDataDir](microsoft-edge-policies.md#userdatadir) or [DownloadDirectory](microsoft-edge-policies.md#downloaddirectory) support variables.</span></span> <span data-ttu-id="bf4f8-108">配置这些策略时，可以使用变量，而不是硬编码路径。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-108">When configuring these policies, you can use variables instead of hard-coded paths.</span></span> <span data-ttu-id="bf4f8-109">例如，将你的配置文件数据存储在 Windows 上的“用户本地应用程序数据”下，而不是存储在默认位置。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-109">For example, to store your profile data under user local application data on Windows instead of the default location.</span></span> <span data-ttu-id="bf4f8-110">将 [UserDataDir](microsoft-edge-policies.md#userdatadir) 策略设置为 **${local_app_data}\Edge\Profile**。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-110">Set the [UserDataDir](microsoft-edge-policies.md#userdatadir) policy to **${local_app_data}\Edge\Profile**.</span></span> <span data-ttu-id="bf4f8-111">在大多数 Windows 10 安装中，此路径会解析为 *C:\Users\\&lt;Current-user&gt;\AppData\Local\Microsoft\Edge\Profile*。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-111">On most Windows 10 installations, this path resolves to *C:\Users\\&lt;Current-user&gt;\AppData\Local\Microsoft\Edge\Profile*.</span></span>

>[!NOTE]
><span data-ttu-id="bf4f8-112">如果未设置，Microsoft Edge 使用默认目录路径。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-112">If left unset, Microsoft Edge uses default directory paths.</span></span> <span data-ttu-id="bf4f8-113">用户可以使用 `--user-data-dir` 命令行标志替代默认设置。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-113">A user can use the `--user-data-dir` command-line flag to override the default.</span></span>

<span data-ttu-id="bf4f8-114">若要查看当前**配置文件路径**，请打开 **“关于版本”** 页（键入“edge://version”）。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-114">To view the current  **Profile path**, open the **About version** page (type "edge://version").</span></span> <span data-ttu-id="bf4f8-115">**配置文件路径**遵循以下格式：*C:\Users\\&lt;Current-user&gt;\AppData\Local\Microsoft\Edge\User Data\Default*。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-115">The **Profile path** follows this format: *C:\Users\\&lt;Current-user&gt;\AppData\Local\Microsoft\Edge\User Data\Default*.</span></span>

### <span data-ttu-id="bf4f8-116">路径变量使用指南</span><span class="sxs-lookup"><span data-stu-id="bf4f8-116">Guidance for using path variables</span></span>

<span data-ttu-id="bf4f8-117">在使用路径变量之前，请查看以下指南。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-117">Review the following guidance before using variables for paths.</span></span>

- <span data-ttu-id="bf4f8-118">涉及 Microsoft Edge 存储不同数据的路径的所有策略均取决于平台。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-118">All policies that involve paths where Microsoft Edge stores different data are platform dependent.</span></span> <span data-ttu-id="bf4f8-119">其中的某些策略仅在特定平台上可用，但其他策略可在所有平台上使用。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-119">Some of these policies are available only on specific platforms, but others can be used on all platforms.</span></span>
- <span data-ttu-id="bf4f8-120">为了避免因应用程序在不同场合从不同位置启动而导致的错误，请确保路径是绝对路径。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-120">To avoid errors caused by applications starting from different locations on different occasions, make sure that paths are absolute.</span></span>
- <span data-ttu-id="bf4f8-121">每个变量在一个路径中只能出现一次。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-121">Every variable can occur only once in a path.</span></span> <span data-ttu-id="bf4f8-122">对于大多数情况，这是使用变量的唯一有意义的方式，因为它们会解析为绝对路径。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-122">For most of them, this is the only meaningful way to use variables, because they resolve to absolute paths.</span></span>
- <span data-ttu-id="bf4f8-123">如果不存在路径，那么几乎所有策略都将创建路径（如有可能，在现有环境中创建）。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-123">Almost all policies will create the path if it doesn't exist (if possible in the existing circumstances).</span></span>
- <span data-ttu-id="bf4f8-124">对某些策略使用网络位置可能会导致意外的结果，因为 Microsoft Edge 的不同版本/渠道处理文件夹结构的方式不同。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-124">Using network locations for some policies can lead to unexpected results due to differences in how different versions/channels of Microsoft Edge handle the folder structure.</span></span>

### <span data-ttu-id="bf4f8-125">支持的路径变量</span><span class="sxs-lookup"><span data-stu-id="bf4f8-125">Supported path variables</span></span>

<span data-ttu-id="bf4f8-126">Microsoft Edge 支持以下路径变量。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-126">Microsoft Edge supports the following path variables.</span></span>

#### <span data-ttu-id="bf4f8-127">所有平台</span><span class="sxs-lookup"><span data-stu-id="bf4f8-127">All platforms</span></span>

| <span data-ttu-id="bf4f8-128">变量</span><span class="sxs-lookup"><span data-stu-id="bf4f8-128">Variable</span></span> | <span data-ttu-id="bf4f8-129">说明</span><span class="sxs-lookup"><span data-stu-id="bf4f8-129">Description</span></span> |
| --- | --- |
| **<span data-ttu-id="bf4f8-130">${user_name}</span><span class="sxs-lookup"><span data-stu-id="bf4f8-130">${user_name}</span></span>** | <span data-ttu-id="bf4f8-131">使用 Microsoft Edge 的用户。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-131">The user who's using Microsoft Edge.</span></span> <span data-ttu-id="bf4f8-132">Microsoft Edge 遵循 SUID（在执行时设置所有者用户 ID）示例：*audreysmall*</span><span class="sxs-lookup"><span data-stu-id="bf4f8-132">Microsoft Edge respects SUIDs (Set owner User ID up on execution) Example: *audreysmall*</span></span> |
| **<span data-ttu-id="bf4f8-133">${machine_name}</span><span class="sxs-lookup"><span data-stu-id="bf4f8-133">${machine_name}</span></span>** | <span data-ttu-id="bf4f8-134">计算机名称，可能包括域名。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-134">The machine name, possibly including the domain name.</span></span> <span data-ttu-id="bf4f8-135">示例：*audreysmall* 或 *audrey.ex.contoso.com*</span><span class="sxs-lookup"><span data-stu-id="bf4f8-135">Example: *audreysmall* or *audrey.ex.contoso.com*</span></span> |

#### <span data-ttu-id="bf4f8-136">仅适用于 Windows</span><span class="sxs-lookup"><span data-stu-id="bf4f8-136">Windows only</span></span>

| <span data-ttu-id="bf4f8-137">变量</span><span class="sxs-lookup"><span data-stu-id="bf4f8-137">Variable</span></span> | <span data-ttu-id="bf4f8-138">说明</span><span class="sxs-lookup"><span data-stu-id="bf4f8-138">Description</span></span> |
| --- | --- |
| **<span data-ttu-id="bf4f8-139">${documents}</span><span class="sxs-lookup"><span data-stu-id="bf4f8-139">${documents}</span></span>** | <span data-ttu-id="bf4f8-140">当前用户的“文档”文件夹。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-140">The Documents folder for the current user.</span></span> <span data-ttu-id="bf4f8-141">示例：*C:\Users\Administrator\Documents*</span><span class="sxs-lookup"><span data-stu-id="bf4f8-141">Example: *C:\Users\Administrator\Documents*</span></span> |
|**<span data-ttu-id="bf4f8-142">${local_app_data}</span><span class="sxs-lookup"><span data-stu-id="bf4f8-142">${local_app_data}</span></span>** | <span data-ttu-id="bf4f8-143">当前用户的“应用程序数据”文件夹。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-143">The Application Data folder for the current user.</span></span> <span data-ttu-id="bf4f8-144">示例：*C:\Users\Administrator\AppData\Local*</span><span class="sxs-lookup"><span data-stu-id="bf4f8-144">Example: *C:\Users\Administrator\AppData\Local*</span></span> |
|**<span data-ttu-id="bf4f8-145">${roaming_app_data}</span><span class="sxs-lookup"><span data-stu-id="bf4f8-145">${roaming_app_data}</span></span>** | <span data-ttu-id="bf4f8-146">当前用户的“漫游应用程序数据”文件夹。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-146">The Roamed Application Data folder for the current user.</span></span> <span data-ttu-id="bf4f8-147">示例：*C:\Users\Administrator\AppData\Roaming*</span><span class="sxs-lookup"><span data-stu-id="bf4f8-147">Example: *C:\Users\Administrator\AppData\Roaming*</span></span> |
| **<span data-ttu-id="bf4f8-148">${profile}</span><span class="sxs-lookup"><span data-stu-id="bf4f8-148">${profile}</span></span>** | <span data-ttu-id="bf4f8-149">当前用户的主文件夹。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-149">The home folder for the current user.</span></span> <span data-ttu-id="bf4f8-150">示例：*C:\Users\Administrator*</span><span class="sxs-lookup"><span data-stu-id="bf4f8-150">Example: *C:\Users\Administrator*</span></span> |
| **<span data-ttu-id="bf4f8-151">${global_app_data}</span><span class="sxs-lookup"><span data-stu-id="bf4f8-151">${global_app_data}</span></span>** | <span data-ttu-id="bf4f8-152">系统范围的“应用程序数据”文件夹。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-152">The system-wide Application Data folder.</span></span> <span data-ttu-id="bf4f8-153">示例：*C:\AppData*</span><span class="sxs-lookup"><span data-stu-id="bf4f8-153">Example: *C:\AppData*</span></span> |
| **<span data-ttu-id="bf4f8-154">${program_files}</span><span class="sxs-lookup"><span data-stu-id="bf4f8-154">${program_files}</span></span>** | <span data-ttu-id="bf4f8-155">当前进程的“程序文件”文件夹。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-155">The Program Files folder for the current process.</span></span> <span data-ttu-id="bf4f8-156">此文件夹取决于它是 32 位还是 64 位进程。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-156">This  folder  depends on whether it's a 32-bit or 64-bit process.</span></span> <span data-ttu-id="bf4f8-157">示例解决方法：*C:\Program Files (x86)*</span><span class="sxs-lookup"><span data-stu-id="bf4f8-157">Example resolution: *C:\Program Files (x86)*</span></span> |
| **<span data-ttu-id="bf4f8-158">${windows}</span><span class="sxs-lookup"><span data-stu-id="bf4f8-158">${windows}</span></span>** | <span data-ttu-id="bf4f8-159">“Windows”文件夹。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-159">The Windows folder.</span></span> <span data-ttu-id="bf4f8-160">示例：*C:\Windows*</span><span class="sxs-lookup"><span data-stu-id="bf4f8-160">Example: *C:\Windows*</span></span> |
| **<span data-ttu-id="bf4f8-161">${client_name)</span><span class="sxs-lookup"><span data-stu-id="bf4f8-161">${client_name)</span></span>** | <span data-ttu-id="bf4f8-162">连接到 RDP 或 Citrix 会话的客户端电脑的名称。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-162">The name of the client PC connected to an RDP or Citrix session.</span></span> <span data-ttu-id="bf4f8-163">如果在本地会话中使用此变量，则此变量为空。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-163">This variable is empty if it's used from a local session.</span></span> <span data-ttu-id="bf4f8-164">如果在路径中使用它，请在它前面加上一定不为空的部分。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-164">If it's used in a path, prefix it with something that's guaranteed not to be empty.</span></span> <span data-ttu-id="bf4f8-165">示例：*对于远程会话，C:\edge_profiles\session_${client_name}* 将解析为 *C:\edge_profiles\session_&lt;ForlocalSessions&gt;* 和 *C:\edge_profiles\session_&lt;SomePCname&gt;*。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-165">Example: *C:\edge_profiles\session_${client_name}* resolves to *C:\edge_profiles\session_&lt;ForlocalSessions&gt;* and *C:\edge_profiles\session_&lt;SomePCname&gt;* for remote sessions.</span></span> |
| **<span data-ttu-id="bf4f8-166">${session_name}</span><span class="sxs-lookup"><span data-stu-id="bf4f8-166">${session_name}</span></span>** | <span data-ttu-id="bf4f8-167">活动会话的名称。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-167">The name of the active session.</span></span> <span data-ttu-id="bf4f8-168">使用此名称可区分使用单个用户配置文件的多个同时连接的远程会话。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-168">Use this name to distinguish multiple simultaneously connected remote sessions that are using a single user profile.</span></span> <span data-ttu-id="bf4f8-169">示例：*用于本地桌面会话的 WinSta0*</span><span class="sxs-lookup"><span data-stu-id="bf4f8-169">Example: *WinSta0 for local desktop sessions*</span></span> |

#### <span data-ttu-id="bf4f8-170">仅 macOS</span><span class="sxs-lookup"><span data-stu-id="bf4f8-170">macOS only</span></span>

| <span data-ttu-id="bf4f8-171">变量</span><span class="sxs-lookup"><span data-stu-id="bf4f8-171">Variable</span></span> | <span data-ttu-id="bf4f8-172">说明</span><span class="sxs-lookup"><span data-stu-id="bf4f8-172">Description</span></span> |
| --- | --- |
| **<span data-ttu-id="bf4f8-173">${users}</span><span class="sxs-lookup"><span data-stu-id="bf4f8-173">${users}</span></span>** | <span data-ttu-id="bf4f8-174">存储用户配置文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-174">The folder where users' profiles are stored.</span></span> <span data-ttu-id="bf4f8-175">示例：*/Users*</span><span class="sxs-lookup"><span data-stu-id="bf4f8-175">Example: */Users*</span></span> |
| **<span data-ttu-id="bf4f8-176">${documents}</span><span class="sxs-lookup"><span data-stu-id="bf4f8-176">${documents}</span></span>** | <span data-ttu-id="bf4f8-177">当前用户的“文档”文件夹。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-177">The Documents folder for the current user.</span></span> <span data-ttu-id="bf4f8-178">示例：*/Users/audreysmall/Documents*</span><span class="sxs-lookup"><span data-stu-id="bf4f8-178">Example: */Users/audreysmall/Documents*</span></span> |

## <span data-ttu-id="bf4f8-179">内容许可证</span><span class="sxs-lookup"><span data-stu-id="bf4f8-179">Content license</span></span>

>[!NOTE]
><span data-ttu-id="bf4f8-180">本页面的某些部分是根据 Chromium.org 创建和共享的作品所做的修改，并根据 [Creative Commons Attribution 4.0 国际许可证](http://creativecommons.org/licenses/by/4.0/)中所述的条款进行使用。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-180">Portions of this page are modifications based on work created and shared by Chromium.org and used according to terms  described in the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).</span></span> <span data-ttu-id="bf4f8-181">可在[此处](https://www.chromium.org/administrators/policy-list-3/user-data-directory-variables)找到原始页面。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-181">The original page can be found [here](https://www.chromium.org/administrators/policy-list-3/user-data-directory-variables).</span></span>
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br/><span data-ttu-id="bf4f8-182">此作品通过 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 国际许可证</a>获得许可。</span><span class="sxs-lookup"><span data-stu-id="bf4f8-182">This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.</span></span>

## <span data-ttu-id="bf4f8-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf4f8-183">See also</span></span>

- [<span data-ttu-id="bf4f8-184">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="bf4f8-184">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)