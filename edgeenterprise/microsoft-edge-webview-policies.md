---
title: Microsoft Edge 浏览器策略文档
ms.author: stmoody
author: brianalt-msft
manager: tahills
ms.date: 10/08/2020
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Microsoft Edge 浏览器支持的所有策略的 Windows 和 Mac 文档
ms.openlocfilehash: 56abadf907dfffec733af2456cc20db36510880b
ms.sourcegitcommit: 4e6188ade942ca6fd599a4ce1c8e0d90d3d03399
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "11105741"
---
# <span data-ttu-id="53974-103">Microsoft Edge WebView2 - 策略</span><span class="sxs-lookup"><span data-stu-id="53974-103">Microsoft Edge WebView2 - Policies</span></span>

<span data-ttu-id="53974-104">最新版本的 Microsoft Edge WebView2 包含以下策略。</span><span class="sxs-lookup"><span data-stu-id="53974-104">The latest version of Microsoft Edge WebView2 includes the following policies.</span></span> <span data-ttu-id="53974-105">可以使用这些策略来配置在你的组织中运行 Microsoft Edge WebView2 的方式。</span><span class="sxs-lookup"><span data-stu-id="53974-105">You can use these policies to configure how Microsoft Edge WebView2 runs in your organization.</span></span>

<span data-ttu-id="53974-106">有关用于控制 Microsoft Edge WebView2 的更新方式和时间的其他策略集的信息，请查看 [Microsoft Edge 更新策略参考](microsoft-edge-update-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="53974-106">For information about an additional set of policies used to control how and when Microsoft Edge WebView2 is updated, check out [Microsoft Edge update policy reference](microsoft-edge-update-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="53974-107">本文适用于 Microsoft Edge 版本 87 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="53974-107">This article applies to Microsoft Edge version 87 or later.</span></span>

## <span data-ttu-id="53974-108">可用策略</span><span class="sxs-lookup"><span data-stu-id="53974-108">Available policies</span></span>
<span data-ttu-id="53974-109">这些表列出了本版本 Microsoft Edge WebView2 中提供的所有组策略。</span><span class="sxs-lookup"><span data-stu-id="53974-109">These tables list all of the group policies available in this release of Microsoft Edge WebView2.</span></span> <span data-ttu-id="53974-110">使用表中的链接获取有关特定策略的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="53974-110">Use the links in the table to get more details about specific policies.</span></span>

|||
|-|-|
|[<span data-ttu-id="53974-111">加载器替代设置</span><span class="sxs-lookup"><span data-stu-id="53974-111">Loader Override Settings</span></span>](#loader-override-settings)|

### [*<span data-ttu-id="53974-112">加载器替代设置</span><span class="sxs-lookup"><span data-stu-id="53974-112">Loader Override Settings</span></span>*](#loader-override-settings-policies)
|<span data-ttu-id="53974-113">策略名称</span><span class="sxs-lookup"><span data-stu-id="53974-113">Policy Name</span></span>|<span data-ttu-id="53974-114">标题</span><span class="sxs-lookup"><span data-stu-id="53974-114">Caption</span></span>|
|-|-|
|[<span data-ttu-id="53974-115">browserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="53974-115">browserExecutableFolder</span></span>](#browserexecutablefolder)|<span data-ttu-id="53974-116">配置浏览器可执行文件文件夹的位置</span><span class="sxs-lookup"><span data-stu-id="53974-116">Configure the location of the browser executable folder</span></span>|
|[<span data-ttu-id="53974-117">releaseChannelPreference</span><span class="sxs-lookup"><span data-stu-id="53974-117">releaseChannelPreference</span></span>](#releasechannelpreference)|<span data-ttu-id="53974-118">设置发布渠道搜索顺序首选项</span><span class="sxs-lookup"><span data-stu-id="53974-118">Set the release channel search order preference</span></span>|




  ## <span data-ttu-id="53974-119">加载器替代设置策略</span><span class="sxs-lookup"><span data-stu-id="53974-119">Loader Override Settings policies</span></span>

  [<span data-ttu-id="53974-120">返回页首</span><span class="sxs-lookup"><span data-stu-id="53974-120">Back to top</span></span>](#microsoft-edge-webview2---policies)

  ### <span data-ttu-id="53974-121">browserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="53974-121">browserExecutableFolder</span></span>
  #### <span data-ttu-id="53974-122">配置浏览器可执行文件文件夹的位置</span><span class="sxs-lookup"><span data-stu-id="53974-122">Configure the location of the browser executable folder</span></span>
  
  
  #### <span data-ttu-id="53974-123">支持的版本：</span><span class="sxs-lookup"><span data-stu-id="53974-123">Supported versions:</span></span>
  - <span data-ttu-id="53974-124">在 87 版或更高版本的 Windows 上</span><span class="sxs-lookup"><span data-stu-id="53974-124">On Windows since 87 or later</span></span>

  #### <span data-ttu-id="53974-125">描述</span><span class="sxs-lookup"><span data-stu-id="53974-125">Description</span></span>
  <span data-ttu-id="53974-126">此策略将 WebView2 应用程序配置为在指定路径中使用 WebView2 Runtime。</span><span class="sxs-lookup"><span data-stu-id="53974-126">This policy configures WebView2 applications to use the WebView2 Runtime in the specified path.</span></span> <span data-ttu-id="53974-127">该文件夹应包含以下文件：msedgewebview2.exe、msedge.dll 等。</span><span class="sxs-lookup"><span data-stu-id="53974-127">The folder should contain the following files: msedgewebview2.exe, msedge.dll, and so on.</span></span>

<span data-ttu-id="53974-128">若要设置文件夹路径的值，请提供值名称和值对。</span><span class="sxs-lookup"><span data-stu-id="53974-128">To set the value for the folder path, provide a Value name and Value pair.</span></span> <span data-ttu-id="53974-129">将值名称设置为 应用程序用户模型 ID 或可执行文件名称。</span><span class="sxs-lookup"><span data-stu-id="53974-129">Set value name to the Application User Model ID or the executable file name.</span></span> <span data-ttu-id="53974-130">可将通配符“\*”用作值名称，以便应用于所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="53974-130">You can use the "\*" wildcard as value name to apply to all applications.</span></span>

  #### <span data-ttu-id="53974-131">支持的功能：</span><span class="sxs-lookup"><span data-stu-id="53974-131">Supported features:</span></span>
  - <span data-ttu-id="53974-132">可以强制：是</span><span class="sxs-lookup"><span data-stu-id="53974-132">Can be mandatory: Yes</span></span>
  - <span data-ttu-id="53974-133">可以推荐：否</span><span class="sxs-lookup"><span data-stu-id="53974-133">Can be recommended: No</span></span>
  - <span data-ttu-id="53974-134">动态策略刷新：是</span><span class="sxs-lookup"><span data-stu-id="53974-134">Dynamic Policy Refresh: Yes</span></span>

  #### <span data-ttu-id="53974-135">数据类型：</span><span class="sxs-lookup"><span data-stu-id="53974-135">Data Type:</span></span>
  - <span data-ttu-id="53974-136">字符串列表</span><span class="sxs-lookup"><span data-stu-id="53974-136">List of strings</span></span>

  #### <span data-ttu-id="53974-137">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="53974-137">Windows information and settings</span></span>
  ##### <span data-ttu-id="53974-138">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="53974-138">Group Policy (ADMX) info</span></span>
  - <span data-ttu-id="53974-139">GP 唯一名称：browserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="53974-139">GP unique name: browserExecutableFolder</span></span>
  - <span data-ttu-id="53974-140">GP 名称：配置浏览器可执行文件文件夹的位置</span><span class="sxs-lookup"><span data-stu-id="53974-140">GP name: Configure the location of the browser executable folder</span></span>
  - <span data-ttu-id="53974-141">GP 路径（强制）：管理模板/Microsoft Edge WebView2/加载器替代设置</span><span class="sxs-lookup"><span data-stu-id="53974-141">GP path (Mandatory): Administrative Templates/Microsoft Edge WebView2/Loader Override Settings</span></span>
  - <span data-ttu-id="53974-142">GP 路径（推荐）：不适用</span><span class="sxs-lookup"><span data-stu-id="53974-142">GP path (Recommended): N/A</span></span>
  - <span data-ttu-id="53974-143">GP ADMX 文件名：MSEdgeWebView2.admx</span><span class="sxs-lookup"><span data-stu-id="53974-143">GP ADMX file name: MSEdgeWebView2.admx</span></span>
  ##### <span data-ttu-id="53974-144">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="53974-144">Windows Registry Settings</span></span>
  - <span data-ttu-id="53974-145">路径（强制）：SOFTWARE\Policies\Microsoft\Edge\WebView2\browserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="53974-145">Path (Mandatory): SOFTWARE\Policies\Microsoft\Edge\WebView2\browserExecutableFolder</span></span>
  - <span data-ttu-id="53974-146">路径（推荐）：不适用</span><span class="sxs-lookup"><span data-stu-id="53974-146">Path (Recommended): N/A</span></span>
  - <span data-ttu-id="53974-147">值名称：REG_SZ 列表</span><span class="sxs-lookup"><span data-stu-id="53974-147">Value Name: list of REG_SZ</span></span>
  - <span data-ttu-id="53974-148">值类型：REG_SZ 列表</span><span class="sxs-lookup"><span data-stu-id="53974-148">Value Type: list of REG_SZ</span></span>
  ##### <span data-ttu-id="53974-149">示例值：</span><span class="sxs-lookup"><span data-stu-id="53974-149">Example value:</span></span>
```
SOFTWARE\Policies\Microsoft\Edge\WebView2\browserExecutableFolder = "Name: *, Value: C:\\Program Files\\Microsoft Edge WebView2 Runtime Redistributable 85.0.541.0 x64"

```


  

  [<span data-ttu-id="53974-150">返回页首</span><span class="sxs-lookup"><span data-stu-id="53974-150">Back to top</span></span>](#microsoft-edge-webview2---policies)

  ### <span data-ttu-id="53974-151">releaseChannelPreference</span><span class="sxs-lookup"><span data-stu-id="53974-151">releaseChannelPreference</span></span>
  #### <span data-ttu-id="53974-152">设置发布渠道搜索顺序首选项</span><span class="sxs-lookup"><span data-stu-id="53974-152">Set the release channel search order preference</span></span>
  
  
  #### <span data-ttu-id="53974-153">支持的版本：</span><span class="sxs-lookup"><span data-stu-id="53974-153">Supported versions:</span></span>
  - <span data-ttu-id="53974-154">在 87 版或更高版本的 Windows 上</span><span class="sxs-lookup"><span data-stu-id="53974-154">On Windows since 87 or later</span></span>

  #### <span data-ttu-id="53974-155">描述</span><span class="sxs-lookup"><span data-stu-id="53974-155">Description</span></span>
  <span data-ttu-id="53974-156">默认渠道搜索顺序是 WebView2 Runtime、Beta、Dev 和未带。</span><span class="sxs-lookup"><span data-stu-id="53974-156">The default channel search order is WebView2 Runtime, Beta, Dev, and Canary.</span></span>

<span data-ttu-id="53974-157">若要反转默认搜索顺序，请将此策略设置为 1。</span><span class="sxs-lookup"><span data-stu-id="53974-157">To reverse the default search order, set this policy to 1.</span></span>

<span data-ttu-id="53974-158">若要设置发布渠道首选项的值，请提供值名称和值对。</span><span class="sxs-lookup"><span data-stu-id="53974-158">To set the value for the release channel preference, provide a Value name and Value pair.</span></span> <span data-ttu-id="53974-159">将值名称设置为 应用程序用户模型 ID 或可执行文件名称。</span><span class="sxs-lookup"><span data-stu-id="53974-159">Set value name to the Application User Model ID or the executable file name.</span></span> <span data-ttu-id="53974-160">可将通配符“\*”用作值名称，以便应用于所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="53974-160">You can use the "\*" wildcard as value name to apply to all applications.</span></span>

  #### <span data-ttu-id="53974-161">支持的功能：</span><span class="sxs-lookup"><span data-stu-id="53974-161">Supported features:</span></span>
  - <span data-ttu-id="53974-162">可以强制：是</span><span class="sxs-lookup"><span data-stu-id="53974-162">Can be mandatory: Yes</span></span>
  - <span data-ttu-id="53974-163">可以推荐：否</span><span class="sxs-lookup"><span data-stu-id="53974-163">Can be recommended: No</span></span>
  - <span data-ttu-id="53974-164">动态策略刷新：是</span><span class="sxs-lookup"><span data-stu-id="53974-164">Dynamic Policy Refresh: Yes</span></span>

  #### <span data-ttu-id="53974-165">数据类型：</span><span class="sxs-lookup"><span data-stu-id="53974-165">Data Type:</span></span>
  - <span data-ttu-id="53974-166">字符串列表</span><span class="sxs-lookup"><span data-stu-id="53974-166">List of strings</span></span>

  #### <span data-ttu-id="53974-167">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="53974-167">Windows information and settings</span></span>
  ##### <span data-ttu-id="53974-168">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="53974-168">Group Policy (ADMX) info</span></span>
  - <span data-ttu-id="53974-169">GP 唯一名称：releaseChannelPreference</span><span class="sxs-lookup"><span data-stu-id="53974-169">GP unique name: releaseChannelPreference</span></span>
  - <span data-ttu-id="53974-170">GP 名称：设置发布渠道搜索顺序首选项</span><span class="sxs-lookup"><span data-stu-id="53974-170">GP name: Set the release channel search order preference</span></span>
  - <span data-ttu-id="53974-171">GP 路径（强制）：管理模板/Microsoft Edge WebView2/加载器替代设置</span><span class="sxs-lookup"><span data-stu-id="53974-171">GP path (Mandatory): Administrative Templates/Microsoft Edge WebView2/Loader Override Settings</span></span>
  - <span data-ttu-id="53974-172">GP 路径（推荐）：不适用</span><span class="sxs-lookup"><span data-stu-id="53974-172">GP path (Recommended): N/A</span></span>
  - <span data-ttu-id="53974-173">GP ADMX 文件名：MSEdgeWebView2.admx</span><span class="sxs-lookup"><span data-stu-id="53974-173">GP ADMX file name: MSEdgeWebView2.admx</span></span>
  ##### <span data-ttu-id="53974-174">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="53974-174">Windows Registry Settings</span></span>
  - <span data-ttu-id="53974-175">路径（强制）：SOFTWARE\Policies\Microsoft\Edge\WebView2\releaseChannelPreference</span><span class="sxs-lookup"><span data-stu-id="53974-175">Path (Mandatory): SOFTWARE\Policies\Microsoft\Edge\WebView2\releaseChannelPreference</span></span>
  - <span data-ttu-id="53974-176">路径（推荐）：不适用</span><span class="sxs-lookup"><span data-stu-id="53974-176">Path (Recommended): N/A</span></span>
  - <span data-ttu-id="53974-177">值名称：REG_SZ 列表</span><span class="sxs-lookup"><span data-stu-id="53974-177">Value Name: list of REG_SZ</span></span>
  - <span data-ttu-id="53974-178">值类型：REG_SZ 列表</span><span class="sxs-lookup"><span data-stu-id="53974-178">Value Type: list of REG_SZ</span></span>
  ##### <span data-ttu-id="53974-179">示例值：</span><span class="sxs-lookup"><span data-stu-id="53974-179">Example value:</span></span>
```
SOFTWARE\Policies\Microsoft\Edge\WebView2\releaseChannelPreference = "Name: *, Value: 1"

```


  

  [<span data-ttu-id="53974-180">返回页首</span><span class="sxs-lookup"><span data-stu-id="53974-180">Back to top</span></span>](#microsoft-edge-webview2---policies)


## <span data-ttu-id="53974-181">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53974-181">See also</span></span>
- [<span data-ttu-id="53974-182">配置 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="53974-182">Configuring Microsoft Edge</span></span>](configure-microsoft-edge.md)
- [<span data-ttu-id="53974-183">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="53974-183">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="53974-184">Microsoft 安全基线博客</span><span class="sxs-lookup"><span data-stu-id="53974-184">Microsoft Security Baselines Blog</span></span>](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/bg-p/Microsoft-Security-Baselines)