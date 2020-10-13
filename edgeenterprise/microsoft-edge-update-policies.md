---
title: Microsoft Edge 更新策略文档
ms.author: stmoody
author: brianalt-msft
manager: tahills
ms.date: 10/07/2020
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Microsoft Edge 更新程序支持的所有策略的文档
ms.openlocfilehash: feb7859f062ae39e2bbfe08d8e478386defb85cf
ms.sourcegitcommit: 4e6188ade942ca6fd599a4ce1c8e0d90d3d03399
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "11105566"
---
# <span data-ttu-id="7ccc9-103">Microsoft Edge - 更新策略</span><span class="sxs-lookup"><span data-stu-id="7ccc9-103">Microsoft Edge - Update policies</span></span>
<span data-ttu-id="7ccc9-104">最新版本的 Microsoft Edge 包含以下策略，你可以使用这些策略控制更新 Microsoft Edge 的方式和时间。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-104">The latest version of Microsoft Edge includes the following policies that you can use to control how and when Microsoft Edge is updated.</span></span>

<span data-ttu-id="7ccc9-105">有关 Microsoft Edge 中可用的其他策略的信息，请查看 [Microsoft Edge 浏览器策略引用](microsoft-edge-policies.md)</span><span class="sxs-lookup"><span data-stu-id="7ccc9-105">For information about other policies available in Microsoft Edge, check out [Microsoft Edge browser policy reference](microsoft-edge-policies.md)</span></span>
> [!NOTE]
> <span data-ttu-id="7ccc9-106">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-106">This article applies to Microsoft Edge version 77 or later.</span></span>
## <span data-ttu-id="7ccc9-107">可用策略</span><span class="sxs-lookup"><span data-stu-id="7ccc9-107">Available policies</span></span>
<span data-ttu-id="7ccc9-108">这些表列出了本版本 Microsoft Edge 中提供的所有与更新相关的组策略。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-108">These tables lists all of the update-related group policies available in this release of Microsoft Edge.</span></span> <span data-ttu-id="7ccc9-109">使用表中的链接获取有关特定策略的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-109">Use the links in the table to get more details about specific policies.</span></span>

|||
|-|-|
|[<span data-ttu-id="7ccc9-110">应用程序</span><span class="sxs-lookup"><span data-stu-id="7ccc9-110">Applications</span></span>](#applications)|[<span data-ttu-id="7ccc9-111">首选项</span><span class="sxs-lookup"><span data-stu-id="7ccc9-111">Preferences</span></span>](#preferences)|
|[<span data-ttu-id="7ccc9-112">代理服务器</span><span class="sxs-lookup"><span data-stu-id="7ccc9-112">Proxy Server</span></span>](#proxy-server)|[<span data-ttu-id="7ccc9-113">Microsoft Edge Web 视图</span><span class="sxs-lookup"><span data-stu-id="7ccc9-113">Microsoft Edge WebView</span></span>](#microsoft-edge-webview)|

### [<span data-ttu-id="7ccc9-114">应用程序</span><span class="sxs-lookup"><span data-stu-id="7ccc9-114">Applications</span></span>](#applications-policies)
|<span data-ttu-id="7ccc9-115">策略名称</span><span class="sxs-lookup"><span data-stu-id="7ccc9-115">Policy Name</span></span>|<span data-ttu-id="7ccc9-116">标题</span><span class="sxs-lookup"><span data-stu-id="7ccc9-116">Caption</span></span>|
|-|-|
|[<span data-ttu-id="7ccc9-117">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="7ccc9-117">InstallDefault</span></span>](#installdefault)|<span data-ttu-id="7ccc9-118">允许安装默认项</span><span class="sxs-lookup"><span data-stu-id="7ccc9-118">Allow installation default</span></span>|
|[<span data-ttu-id="7ccc9-119">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="7ccc9-119">UpdateDefault</span></span>](#updatedefault)|<span data-ttu-id="7ccc9-120">更新策略替代默认值</span><span class="sxs-lookup"><span data-stu-id="7ccc9-120">Update policy override default</span></span>|
|[<span data-ttu-id="7ccc9-121">安装</span><span class="sxs-lookup"><span data-stu-id="7ccc9-121">Install</span></span>](#install)|<span data-ttu-id="7ccc9-122">允许安装（按渠道）</span><span class="sxs-lookup"><span data-stu-id="7ccc9-122">Allow installation (per channel)</span></span>|
|[<span data-ttu-id="7ccc9-123">更新</span><span class="sxs-lookup"><span data-stu-id="7ccc9-123">Update</span></span>](#update)|<span data-ttu-id="7ccc9-124">更新策略替代（按渠道）</span><span class="sxs-lookup"><span data-stu-id="7ccc9-124">Update policy override (per channel)</span></span>|
|[<span data-ttu-id="7ccc9-125">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="7ccc9-125">Allowsxs</span></span>](#allowsxs)|<span data-ttu-id="7ccc9-126">允许 Microsoft Edge 并行浏览器体验</span><span class="sxs-lookup"><span data-stu-id="7ccc9-126">Allow Microsoft Edge Side by Side browser experience</span></span>|
|[<span data-ttu-id="7ccc9-127">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="7ccc9-127">CreateDesktopShortcutDefault</span></span>](#createdesktopshortcutdefault)|<span data-ttu-id="7ccc9-128">安装默认项时阻止创建快捷方式</span><span class="sxs-lookup"><span data-stu-id="7ccc9-128">Prevent Desktop Shortcut creation upon install default</span></span>|
|[<span data-ttu-id="7ccc9-129">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="7ccc9-129">CreateDesktopShortcut</span></span>](#createdesktopshortcut)|<span data-ttu-id="7ccc9-130">安装时阻止创建快捷方式（按渠道）</span><span class="sxs-lookup"><span data-stu-id="7ccc9-130">Prevent Desktop Shortcut creation upon install (per channel)</span></span>|
|[<span data-ttu-id="7ccc9-131">RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="7ccc9-131">RollbackToTargetVersion</span></span>](#rollbacktotargetversion)|<span data-ttu-id="7ccc9-132">回退到目标版本（按渠道）</span><span class="sxs-lookup"><span data-stu-id="7ccc9-132">Rollback to Target version (per channel)</span></span>|
|[<span data-ttu-id="7ccc9-133">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="7ccc9-133">TargetVersionPrefix</span></span>](#targetversionprefix)|<span data-ttu-id="7ccc9-134">目标版本覆盖（各渠道）</span><span class="sxs-lookup"><span data-stu-id="7ccc9-134">Target version override (per channel)</span></span>|

### [<span data-ttu-id="7ccc9-135">首选项</span><span class="sxs-lookup"><span data-stu-id="7ccc9-135">Preferences</span></span>](#preferences-policies)
|<span data-ttu-id="7ccc9-136">策略名称</span><span class="sxs-lookup"><span data-stu-id="7ccc9-136">Policy Name</span></span>|<span data-ttu-id="7ccc9-137">标题</span><span class="sxs-lookup"><span data-stu-id="7ccc9-137">Caption</span></span>|
|-|-|
|[<span data-ttu-id="7ccc9-138">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="7ccc9-138">AutoUpdateCheckPeriodMinutes</span></span>](#autoupdatecheckperiodminutes)|<span data-ttu-id="7ccc9-139">自动更新检查期间替代</span><span class="sxs-lookup"><span data-stu-id="7ccc9-139">Auto-update check period override</span></span>|
|[<span data-ttu-id="7ccc9-140">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="7ccc9-140">UpdatesSuppressed</span></span>](#updatessuppressed)|<span data-ttu-id="7ccc9-141">每天中取消自动更新检查的时间段</span><span class="sxs-lookup"><span data-stu-id="7ccc9-141">Time period in each day to suppress auto-update check</span></span>|

### [<span data-ttu-id="7ccc9-142">代理服务器</span><span class="sxs-lookup"><span data-stu-id="7ccc9-142">Proxy Server</span></span>](#proxy-server-policies)
|<span data-ttu-id="7ccc9-143">策略名称</span><span class="sxs-lookup"><span data-stu-id="7ccc9-143">Policy Name</span></span>|<span data-ttu-id="7ccc9-144">描述文字</span><span class="sxs-lookup"><span data-stu-id="7ccc9-144">Caption</span></span>|
|-|-|
|[<span data-ttu-id="7ccc9-145">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="7ccc9-145">ProxyMode</span></span>](#proxymode)|<span data-ttu-id="7ccc9-146">选择指定代理服务器设置的方式</span><span class="sxs-lookup"><span data-stu-id="7ccc9-146">Choose how to specify proxy server settings</span></span>|
|[<span data-ttu-id="7ccc9-147">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="7ccc9-147">ProxyPacUrl</span></span>](#proxypacurl)|<span data-ttu-id="7ccc9-148">代理 .pac 文件的 URL</span><span class="sxs-lookup"><span data-stu-id="7ccc9-148">URL to a proxy .pac file</span></span>|
|[<span data-ttu-id="7ccc9-149">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="7ccc9-149">ProxyServer</span></span>](#proxyserver)|<span data-ttu-id="7ccc9-150">代理服务器的地址或 URL</span><span class="sxs-lookup"><span data-stu-id="7ccc9-150">Address or URL of proxy server</span></span>|

### [<span data-ttu-id="7ccc9-151">Microsoft Edge Web 视图</span><span class="sxs-lookup"><span data-stu-id="7ccc9-151">Microsoft Edge WebView</span></span>](#microsoft-edge-webview-policies)
|<span data-ttu-id="7ccc9-152">策略名称</span><span class="sxs-lookup"><span data-stu-id="7ccc9-152">Policy Name</span></span>|<span data-ttu-id="7ccc9-153">标题</span><span class="sxs-lookup"><span data-stu-id="7ccc9-153">Caption</span></span>|
|-|-|
|[<span data-ttu-id="7ccc9-154">安装</span><span class="sxs-lookup"><span data-stu-id="7ccc9-154">Install</span></span>](#install-webview)|<span data-ttu-id="7ccc9-155">允许安装</span><span class="sxs-lookup"><span data-stu-id="7ccc9-155">Allow installation</span></span>|
|[<span data-ttu-id="7ccc9-156">更新</span><span class="sxs-lookup"><span data-stu-id="7ccc9-156">Update</span></span>](#update-webview)|<span data-ttu-id="7ccc9-157">更新策略替代</span><span class="sxs-lookup"><span data-stu-id="7ccc9-157">Update policy override</span></span>|

## <span data-ttu-id="7ccc9-158">应用程序策略</span><span class="sxs-lookup"><span data-stu-id="7ccc9-158">Applications policies</span></span>

[<span data-ttu-id="7ccc9-159">返回页首</span><span class="sxs-lookup"><span data-stu-id="7ccc9-159">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="7ccc9-160">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="7ccc9-160">InstallDefault</span></span>
#### <span data-ttu-id="7ccc9-161">允许安装默认项</span><span class="sxs-lookup"><span data-stu-id="7ccc9-161">Allow installation default</span></span>
><span data-ttu-id="7ccc9-162">Microsoft Edge 更新 1.2.145.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="7ccc9-162">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="7ccc9-163">描述</span><span class="sxs-lookup"><span data-stu-id="7ccc9-163">Description</span></span>
<span data-ttu-id="7ccc9-164">可指定所有渠道的默认行为，以允许或阻止域连接设备上的Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-164">You can specify the default behavior of all channels to allow or block Microsoft Edge on domain-joined devices.</span></span>

<span data-ttu-id="7ccc9-165">通过为那些特定渠道启用“[允许安装](#install)”策略，可为个别渠道覆盖此策略。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-165">You can override this policy for individual channels by enabling the '[Allow installation](#install)' policy for specific channels.</span></span>

<span data-ttu-id="7ccc9-166">如果禁用此策略，则会阻止 Microsoft Edge的安装。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-166">If you disable this policy, the installation of Microsoft Edge is blocked.</span></span> <span data-ttu-id="7ccc9-167">只有当 "[允许安装](#install)" 策略设置为 "未配置" 时，才会影响Microsoft Edge软件的安装。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-167">This only affects the installation of Microsoft Edge software when the '[Allow installation](#install)' policy is set to Not Configured.</span></span>

<span data-ttu-id="7ccc9-168">此策略不会阻止运行 Microsoft Edge 更新，也不会阻止用户使用其他方法安装 Microsoft Edge 软件。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-168">This policy doesn't prevent Microsoft Edge Update from running or prevent users from installing Microsoft Edge software using other methods.</span></span>

<span data-ttu-id="7ccc9-169">此策略仅在加入Microsoft® Active Directory®域的Windows实例上可用。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-169">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="7ccc9-170">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-170">Windows information and settings</span></span>
##### <span data-ttu-id="7ccc9-171">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="7ccc9-171">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7ccc9-172">GP 唯一名称：InstallDefault</span><span class="sxs-lookup"><span data-stu-id="7ccc9-172">GP unique name: InstallDefault</span></span>
- <span data-ttu-id="7ccc9-173">GP 名称：允许安装默认项</span><span class="sxs-lookup"><span data-stu-id="7ccc9-173">GP name: Allow installation default</span></span>
- <span data-ttu-id="7ccc9-174">GP 路径：Administrative Templates/Microsoft Edge Update/Applications</span><span class="sxs-lookup"><span data-stu-id="7ccc9-174">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="7ccc9-175">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7ccc9-175">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7ccc9-176">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-176">Windows Registry Settings</span></span>
- <span data-ttu-id="7ccc9-177">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7ccc9-177">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7ccc9-178">值名称：InstallDefault</span><span class="sxs-lookup"><span data-stu-id="7ccc9-178">Value Name: InstallDefault</span></span>
- <span data-ttu-id="7ccc9-179">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7ccc9-179">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7ccc9-180">示例值：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-180">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="7ccc9-181">返回页首</span><span class="sxs-lookup"><span data-stu-id="7ccc9-181">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7ccc9-182">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="7ccc9-182">UpdateDefault</span></span>
#### <span data-ttu-id="7ccc9-183">更新策略替代默认值</span><span class="sxs-lookup"><span data-stu-id="7ccc9-183">Update policy override default</span></span>
><span data-ttu-id="7ccc9-184">Microsoft Edge 更新 1.2.145.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="7ccc9-184">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="7ccc9-185">描述</span><span class="sxs-lookup"><span data-stu-id="7ccc9-185">Description</span></span>
<span data-ttu-id="7ccc9-186">允许你为所有渠道指定与 Microsoft Edge 更新处理 Microsoft Edge 可用更新的方式有关的默认行为。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-186">Lets you specify the default behavior for all channels concerning the way Microsoft Edge Update handles available updates for Microsoft Edge.</span></span> <span data-ttu-id="7ccc9-187">通过为那些特定渠道指定“[更新策略替代](#update)”策略，可为个别渠道进行覆盖。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-187">Can be overridden for individual channels by specifying the '[Update policy override](#update)' policy for those specific channels.</span></span>

  <span data-ttu-id="7ccc9-188">如果你启用此策略，Microsoft Edge 更新将根据你配置以下选项的方式处理 Microsoft Edge 更新：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-188">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
   - <span data-ttu-id="7ccc9-189">始终允许更新：通过定期更新检查或通过手动更新检查，在发现更新时始终应用更新。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-189">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
   - <span data-ttu-id="7ccc9-190">仅限自动无提示更新：仅在定期更新检查找到更新后才应用更新。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-190">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
   - <span data-ttu-id="7ccc9-191">仅限手动更新：仅当用户运行手动更新检查时才应用更新。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-191">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span>
   - <span data-ttu-id="7ccc9-192">已禁用更新：从不应用更新。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-192">Updates disabled: Updates are never applied.</span></span>

  <span data-ttu-id="7ccc9-193">如果你选择手动更新，请确保使用应用的手动更新机制（如果有）定期检查更新。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-193">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="7ccc9-194">如果你禁用更新，请定期检查更新，然后将它们分发给用户。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-194">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

  <span data-ttu-id="7ccc9-195">如果你未启用和配置此策略，Microsoft Edge 更新将处理“[更新策略替代](#update)”策略指定的可用更新。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-195">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override](#update)' policy.</span></span>

  <span data-ttu-id="7ccc9-196">此策略仅在加入Microsoft® Active Directory®域的Windows实例上可用。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-196">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="7ccc9-197">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-197">Windows information and settings</span></span>
##### <span data-ttu-id="7ccc9-198">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="7ccc9-198">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7ccc9-199">GP 唯一名称：UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="7ccc9-199">GP unique name: UpdateDefault</span></span>
- <span data-ttu-id="7ccc9-200">GP 名称：更新策略替代默认值</span><span class="sxs-lookup"><span data-stu-id="7ccc9-200">GP name: Update policy override default</span></span>
- <span data-ttu-id="7ccc9-201">GP 路径：Administrative Templates/Microsoft Edge Update/Applications</span><span class="sxs-lookup"><span data-stu-id="7ccc9-201">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="7ccc9-202">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7ccc9-202">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7ccc9-203">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-203">Windows Registry Settings</span></span>
- <span data-ttu-id="7ccc9-204">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7ccc9-204">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7ccc9-205">值名称：UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="7ccc9-205">Value Name: UpdateDefault</span></span>
- <span data-ttu-id="7ccc9-206">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7ccc9-206">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7ccc9-207">示例值：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-207">Example value:</span></span>
```
0x00000003
```
[<span data-ttu-id="7ccc9-208">返回页首</span><span class="sxs-lookup"><span data-stu-id="7ccc9-208">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7ccc9-209">安装</span><span class="sxs-lookup"><span data-stu-id="7ccc9-209">Install</span></span>
#### <span data-ttu-id="7ccc9-210">允许安装</span><span class="sxs-lookup"><span data-stu-id="7ccc9-210">Allow installation</span></span>
><span data-ttu-id="7ccc9-211">Microsoft Edge 更新 1.2.145.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="7ccc9-211">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="7ccc9-212">描述</span><span class="sxs-lookup"><span data-stu-id="7ccc9-212">Description</span></span>
<span data-ttu-id="7ccc9-213">指定是否可以在域连接的设备上安装Microsoft Edge通道。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-213">Specifies whether a Microsoft Edge channel can be installed on domain-joined devices.</span></span>

  <span data-ttu-id="7ccc9-214">如果为渠道启用此策略，则不会阻止 Microsoft Edge 的安装。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-214">If you enable this policy for a channel, Microsoft Edge will not be blocked from installation.</span></span>

  <span data-ttu-id="7ccc9-215">如果为渠道启用此策略，则会阻止 Microsoft Edge 的安装。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-215">If you disable this policy for a channel, Microsoft Edge will be blocked from installation.</span></span>

  <span data-ttu-id="7ccc9-216">如果没有为渠道配置此策略，则“[允许安装默认项](#installdefault)”策略配置将决定用户是否可以安装Microsoft Edge的该渠道。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-216">If you don't configure this policy for a channel, the '[Allow installation default](#installdefault)' policy configuration determines whether users can install that channel of Microsoft Edge.</span></span>

  <span data-ttu-id="7ccc9-217">此策略仅在加入Microsoft® Active Directory®域的Windows实例上可用。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-217">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="7ccc9-218">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-218">Windows information and settings</span></span>
##### <span data-ttu-id="7ccc9-219">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="7ccc9-219">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7ccc9-220">GP 唯一名称：安装</span><span class="sxs-lookup"><span data-stu-id="7ccc9-220">GP unique name: Install</span></span>
- <span data-ttu-id="7ccc9-221">GP 名称：允许安装</span><span class="sxs-lookup"><span data-stu-id="7ccc9-221">GP name: Allow installation</span></span>
- <span data-ttu-id="7ccc9-222">GP 路径：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-222">GP path:</span></span> 
  - <span data-ttu-id="7ccc9-223">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7ccc9-223">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="7ccc9-224">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="7ccc9-224">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="7ccc9-225">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="7ccc9-225">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="7ccc9-226">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="7ccc9-226">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="7ccc9-227">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7ccc9-227">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7ccc9-228">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-228">Windows Registry Settings</span></span>
- <span data-ttu-id="7ccc9-229">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7ccc9-229">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7ccc9-230">值名称：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-230">Value Name:</span></span> 
  - <span data-ttu-id="7ccc9-231">（稳定）：安装 {56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-231">(Stable): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="7ccc9-232">(Beta)：安装 {2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-232">(Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="7ccc9-233">(Canary)：安装 {65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-233">(Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="7ccc9-234">(Dev)：安装 {0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-234">(Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="7ccc9-235">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7ccc9-235">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7ccc9-236">示例值：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-236">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="7ccc9-237">返回页首</span><span class="sxs-lookup"><span data-stu-id="7ccc9-237">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7ccc9-238">更新</span><span class="sxs-lookup"><span data-stu-id="7ccc9-238">Update</span></span>
#### <span data-ttu-id="7ccc9-239">更新策略替代</span><span class="sxs-lookup"><span data-stu-id="7ccc9-239">Update policy override</span></span>
><span data-ttu-id="7ccc9-240">Microsoft Edge 更新 1.2.145.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="7ccc9-240">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="7ccc9-241">描述</span><span class="sxs-lookup"><span data-stu-id="7ccc9-241">Description</span></span>
<span data-ttu-id="7ccc9-242">指定 Microsoft Edge 更新如何处理 Microsoft Edge 中的可用更新。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-242">Specifies how Microsoft Edge Update handles available updates from Microsoft Edge.</span></span>

<span data-ttu-id="7ccc9-243">如果你启用此策略，Microsoft Edge 更新将根据你配置以下选项的方式处理 Microsoft Edge 更新：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-243">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
  - <span data-ttu-id="7ccc9-244">始终允许更新：通过定期更新检查或通过手动更新检查，在发现更新时始终应用更新。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-244">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
  - <span data-ttu-id="7ccc9-245">仅限自动无提示更新：仅在定期更新检查找到更新后才应用更新。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-245">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
  - <span data-ttu-id="7ccc9-246">仅限手动更新：仅当用户运行手动更新检查时才应用更新。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-246">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span> <span data-ttu-id="7ccc9-247">（并非所有应用都为此选项提供接口。）</span><span class="sxs-lookup"><span data-stu-id="7ccc9-247">(Not all apps provide an interface for this option.)</span></span>
  - <span data-ttu-id="7ccc9-248">已禁用更新：从不应用更新。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-248">Updates disabled: Updates are never applied.</span></span>

<span data-ttu-id="7ccc9-249">如果你选择手动更新，请确保使用应用的手动更新机制（如果有）定期检查更新。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-249">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="7ccc9-250">如果你禁用更新，请定期检查更新，然后将它们分发给用户。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-250">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

<span data-ttu-id="7ccc9-251">如果你未启用和配置此策略，Microsoft Edge 更新将处理“[更新策略替代默认值](#updatedefault)”策略指定的可用更新。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-251">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override default](#updatedefault)' policy.</span></span>

<span data-ttu-id="7ccc9-252">有关详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2136406](https://go.microsoft.com/fwlink/?linkid=2136406)。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-252">See [https://go.microsoft.com/fwlink/?linkid=2136406](https://go.microsoft.com/fwlink/?linkid=2136406) for more information.</span></span>

<span data-ttu-id="7ccc9-253">此策略仅在加入Microsoft® Active Directory®域的Windows实例上可用。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-253">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="7ccc9-254">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-254">Windows information and settings</span></span>
##### <span data-ttu-id="7ccc9-255">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="7ccc9-255">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7ccc9-256">GP 唯一名称：更新</span><span class="sxs-lookup"><span data-stu-id="7ccc9-256">GP unique name: Update</span></span>
- <span data-ttu-id="7ccc9-257">GP 名称：更新策略替代</span><span class="sxs-lookup"><span data-stu-id="7ccc9-257">GP name: Update policy override</span></span>
- <span data-ttu-id="7ccc9-258">GP 路径：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-258">GP path:</span></span> 
  - <span data-ttu-id="7ccc9-259">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7ccc9-259">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="7ccc9-260">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="7ccc9-260">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="7ccc9-261">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="7ccc9-261">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="7ccc9-262">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="7ccc9-262">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="7ccc9-263">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7ccc9-263">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7ccc9-264">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-264">Windows Registry Settings</span></span>
- <span data-ttu-id="7ccc9-265">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7ccc9-265">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7ccc9-266">值名称：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-266">Value Name:</span></span> 
  - <span data-ttu-id="7ccc9-267">（稳定）：更新 {56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-267">(Stable): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="7ccc9-268">(Beta)：更新 {2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-268">(Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="7ccc9-269">(Canary)：更新 {65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-269">(Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="7ccc9-270">(Dev)：更新 {0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-270">(Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="7ccc9-271">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7ccc9-271">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7ccc9-272">示例值：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-272">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="7ccc9-273">返回页首</span><span class="sxs-lookup"><span data-stu-id="7ccc9-273">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7ccc9-274">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="7ccc9-274">Allowsxs</span></span>
#### <span data-ttu-id="7ccc9-275">允许 Microsoft Edge 并行浏览器体验</span><span class="sxs-lookup"><span data-stu-id="7ccc9-275">Allow Microsoft Edge Side by Side browser experience</span></span>
><span data-ttu-id="7ccc9-276">Microsoft Edge 更新 1.2.145.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="7ccc9-276">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="7ccc9-277">说明</span><span class="sxs-lookup"><span data-stu-id="7ccc9-277">Description</span></span>
<span data-ttu-id="7ccc9-278">此策略允许用户并行运行 Microsoft Edge (Edge HTML) 和 Microsoft Edge（基于 Chromium）。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-278">This policy lets a user run Microsoft Edge (Edge HTML) and Microsoft Edge (Chromium-based) side-by-side.</span></span>

<span data-ttu-id="7ccc9-279">如果将此策略设置为“未配置”，则在安装 Microsoft Edge（基于 Chromium）稳定渠道和 2019 年 11 月安全更新后，Microsoft Edge（基于 Chromium）将替换 Microsoft Edge (Edge HTML)。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-279">If this policy is set to “Not configured”, Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="7ccc9-280">此行为与“已禁用”设置相同。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-280">This is the same behavior as the “Disabled” setting.</span></span>

<span data-ttu-id="7ccc9-281">在安装 Microsoft Edge（基于 Chromium）稳定渠道和 2019 年 11 月安全更新后，“已禁用”设置会阻止并行体验，并且 Microsoft Edge（基于 Chromium）将替换 Microsoft Edge (Edge HTML)。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-281">The “Disabled” setting blocks a side-by-side experience and Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="7ccc9-282">此行为与“未配置”设置相同。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-282">This is the same behavior as the “Not Configured” setting.</span></span>

<span data-ttu-id="7ccc9-283">如果“已启用”此策略，则在安装 Microsoft Edge（基于 Chromium）后，Microsoft Edge（基于 Chromium）和 Microsoft Edge (Edge HTML) 可并行运行。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-283">When this policy is “Enabled”, Microsoft Edge (Chromium-based) and Microsoft Edge (Edge HTML) can run side-by-side after Microsoft Edge (Chromium-based) is installed.</span></span>

<span data-ttu-id="7ccc9-284">若要使此组策略生效，必须先配置它，然后再通过 Windows 更新自动安装 Microsoft Edge（基于 Chromium）。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-284">For this group policy to take affect, it must be configured before the automatic install of Microsoft Edge (Chromium-based) by Windows Update.</span></span> <span data-ttu-id="7ccc9-285">注意：通过使用 Microsoft Edge（基于 Chromium）阻止程序工具包，用户可以阻止自动更新 Microsoft Edge（基于 Chromium）。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-285">Note: A user can block the automatic update of Microsoft Edge (Chromium-based) by using the Microsoft Edge (Chromium-based) Blocker Toolkit.</span></span>
#### <span data-ttu-id="7ccc9-286">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-286">Windows information and settings</span></span>
##### <span data-ttu-id="7ccc9-287">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="7ccc9-287">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7ccc9-288">GP 唯一名称：Allowsxs</span><span class="sxs-lookup"><span data-stu-id="7ccc9-288">GP unique name: Allowsxs</span></span>
- <span data-ttu-id="7ccc9-289">GP 名称：允许 Microsoft Edge 并行浏览器体验</span><span class="sxs-lookup"><span data-stu-id="7ccc9-289">GP name: Allow Microsoft Edge Side by Side browser experience</span></span>
- <span data-ttu-id="7ccc9-290">GP 路径：Administrative Templates/Microsoft Edge Update/Applications</span><span class="sxs-lookup"><span data-stu-id="7ccc9-290">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="7ccc9-291">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7ccc9-291">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7ccc9-292">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-292">Windows Registry Settings</span></span>
- <span data-ttu-id="7ccc9-293">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7ccc9-293">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7ccc9-294">值名称：Allowsxs</span><span class="sxs-lookup"><span data-stu-id="7ccc9-294">Value Name: Allowsxs</span></span>
- <span data-ttu-id="7ccc9-295">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7ccc9-295">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7ccc9-296">示例值：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-296">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="7ccc9-297">返回页首</span><span class="sxs-lookup"><span data-stu-id="7ccc9-297">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7ccc9-298">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="7ccc9-298">CreateDesktopShortcutDefault</span></span>
#### <span data-ttu-id="7ccc9-299">安装默认项时阻止创建快捷方式</span><span class="sxs-lookup"><span data-stu-id="7ccc9-299">Prevent Desktop Shortcut creation upon install default</span></span>
><span data-ttu-id="7ccc9-300">Microsoft Edge 更新 1.3.128.0 和更高版本</span><span class="sxs-lookup"><span data-stu-id="7ccc9-300">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <span data-ttu-id="7ccc9-301">描述</span><span class="sxs-lookup"><span data-stu-id="7ccc9-301">Description</span></span>
<span data-ttu-id="7ccc9-302">安装 Microsoft Edge 时，可针对创建桌面快捷方式指定所有渠道的默认行为。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-302">Lets you specify the default behavior for all channels for creating a desktop shortcut when Microsoft Edge is installed.</span></span>

  <span data-ttu-id="7ccc9-303">如果启用此策略，在安装 Microsoft Edge 时会创建桌面快捷方式。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-303">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="7ccc9-304">如果禁用此策略，在安装 Microsoft Edge 时不创建桌面快捷方式。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-304">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="7ccc9-305">如果未配置此策略，会在安装过程中创建 Microsoft Edge 桌面快捷方式。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-305">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="7ccc9-306">如果已安装 Microsoft Edge，此策略将不起作用。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-306">If Microsoft Edge is already installed, this policy will have no effect.</span></span>
#### <span data-ttu-id="7ccc9-307">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-307">Windows information and settings</span></span>
##### <span data-ttu-id="7ccc9-308">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="7ccc9-308">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7ccc9-309">GP 唯一名称：CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="7ccc9-309">GP unique name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="7ccc9-310">GP 名称：安装默认项时阻止创建快捷方式</span><span class="sxs-lookup"><span data-stu-id="7ccc9-310">GP name: Prevent Desktop Shortcut creation upon install default</span></span>
- <span data-ttu-id="7ccc9-311">GP 路径：Administrative Templates/Microsoft Edge Update/Applications</span><span class="sxs-lookup"><span data-stu-id="7ccc9-311">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="7ccc9-312">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7ccc9-312">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7ccc9-313">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-313">Windows Registry Settings</span></span>
- <span data-ttu-id="7ccc9-314">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7ccc9-314">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7ccc9-315">值名称：CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="7ccc9-315">Value Name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="7ccc9-316">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7ccc9-316">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7ccc9-317">示例值：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-317">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="7ccc9-318">返回页首</span><span class="sxs-lookup"><span data-stu-id="7ccc9-318">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7ccc9-319">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="7ccc9-319">CreateDesktopShortcut</span></span>
#### <span data-ttu-id="7ccc9-320">安装时阻止创建快捷方式</span><span class="sxs-lookup"><span data-stu-id="7ccc9-320">Prevent Desktop Shortcut creation upon install</span></span>
><span data-ttu-id="7ccc9-321">Microsoft Edge 更新 1.3.128.0 和更高版本</span><span class="sxs-lookup"><span data-stu-id="7ccc9-321">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <span data-ttu-id="7ccc9-322">描述</span><span class="sxs-lookup"><span data-stu-id="7ccc9-322">Description</span></span>
<span data-ttu-id="7ccc9-323">如果启用此策略，在安装 Microsoft Edge 时会创建桌面快捷方式。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-323">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="7ccc9-324">如果禁用此策略，在安装 Microsoft Edge 时不创建桌面快捷方式。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-324">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="7ccc9-325">如果未配置此策略，会在安装过程中创建 Microsoft Edge 桌面快捷方式。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-325">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="7ccc9-326">如果已安装 Microsoft Edge，此策略将不起作用。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-326">If Microsoft Edge is already installed, this policy will have no effect.</span></span>

  <span data-ttu-id="7ccc9-327">如果未为频道配置此策略，则“[Prevent Desktop Shortcut creation upon install default](#createdesktopshortcutdefault)”策略配置将确定在安装 Microsoft Edge 时创建快捷方式。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-327">If you don't configure this policy for a channel, the '[Prevent Desktop Shortcut creation upon install default](#createdesktopshortcutdefault)' policy configuration determines shortcut creation when Microsoft Edge is installed.</span></span>
#### <span data-ttu-id="7ccc9-328">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-328">Windows information and settings</span></span>
##### <span data-ttu-id="7ccc9-329">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="7ccc9-329">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7ccc9-330">GP 唯一名称：CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="7ccc9-330">GP unique name: CreateDesktopShortcut</span></span>
- <span data-ttu-id="7ccc9-331">GP 名称：安装时阻止创建快捷方式</span><span class="sxs-lookup"><span data-stu-id="7ccc9-331">GP name: Prevent Desktop Shortcut creation upon install</span></span>
- <span data-ttu-id="7ccc9-332">GP 路径：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-332">GP path:</span></span> 
  - <span data-ttu-id="7ccc9-333">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7ccc9-333">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="7ccc9-334">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="7ccc9-334">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="7ccc9-335">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="7ccc9-335">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="7ccc9-336">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="7ccc9-336">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="7ccc9-337">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7ccc9-337">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7ccc9-338">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-338">Windows Registry Settings</span></span>
- <span data-ttu-id="7ccc9-339">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7ccc9-339">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7ccc9-340">值名称：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-340">Value Name:</span></span> 
  - <span data-ttu-id="7ccc9-341">（稳定）：CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-341">(Stable): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="7ccc9-342">(Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-342">(Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="7ccc9-343">(Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-343">(Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="7ccc9-344">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-344">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="7ccc9-345">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7ccc9-345">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7ccc9-346">示例值：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-346">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="7ccc9-347">返回页首</span><span class="sxs-lookup"><span data-stu-id="7ccc9-347">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7ccc9-348">RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="7ccc9-348">RollbackToTargetVersion</span></span>
#### <span data-ttu-id="7ccc9-349">回退到目标版本</span><span class="sxs-lookup"><span data-stu-id="7ccc9-349">Rollback to Target version</span></span>
><span data-ttu-id="7ccc9-350">Microsoft Edge 更新 1.3.133.3 和更高版本</span><span class="sxs-lookup"><span data-stu-id="7ccc9-350">Microsoft Edge Update 1.3.133.3 and later</span></span>

#### <span data-ttu-id="7ccc9-351">描述</span><span class="sxs-lookup"><span data-stu-id="7ccc9-351">Description</span></span>
<span data-ttu-id="7ccc9-352">指定 Microsoft Edge 更新应将 Microsoft Edge 的安装回退到 "[目标版本覆盖](#targetversionprefix)" 中指定的版本。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-352">Specifies that Microsoft Edge Update should rollback installations of Microsoft Edge to the version indicated in '[Target version override](#targetversionprefix)'.</span></span>

<span data-ttu-id="7ccc9-353">除非"[目标版本替代](#targetversionprefix)" 设置为 "开"，并且将 "[更新策略替代](#update)" 设置为 "开启" 状态之一（始终允许更新、仅自动无提示更新，仅限手动更新），否则该策略无效。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-353">This policy has no effect unless '[Target version override](#targetversionprefix)' is set and '[Update policy override](#update)' is set to one of the ON states (Always allow updates, Automatic silent updates only, Manual updates only).</span></span>

<span data-ttu-id="7ccc9-354">如果禁用该策略或不对其进行配置，则安装的版本高于由 "[目标版本替代](#targetversionprefix)" 所指定的版本则将保留原样。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-354">If you disable this policy or don't configure it, installs that have a version higher than that specified by '[Target version override](#targetversionprefix)' will be left as-is.</span></span>

<span data-ttu-id="7ccc9-355">如果启用此策略，则当前版本高于由 "[目标版本替代](#targetversionprefix)" 指定的安装将降级到目标版本。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-355">If you enable this policy, installs that have a current version higher than specified by the '[Target version override](#targetversionprefix)' will be downgraded to the target version.</span></span>

<span data-ttu-id="7ccc9-356">我们建议用户安装最新版本的 Microsoft Edge 浏览器，以确保受到最新安全更新的保护。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-356">We recommend that users install the latest version of the Microsoft Edge browser to ensure protection by the latest security updates.</span></span> <span data-ttu-id="7ccc9-357">回退到较早版本存在遇到已知安全问题的风险。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-357">Rollback to an earlier version risks exposure to known security issues.</span></span> <span data-ttu-id="7ccc9-358">该策略旨在作为一种临时修复措施，以解决Microsoft Edge浏览器更新中所面临的问题。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-358">This policy is meant to be used as a temporary fix to address issues in a Microsoft Edge browser update.</span></span>

<span data-ttu-id="7ccc9-359">在暂时回退浏览器版本之前，建议你为组织中的所有用户启用同步（[https://go.microsoft.com/fwlink/?linkid=2133032](https://go.microsoft.com/fwlink/?linkid=2133032)）。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-359">Before temporarily rolling back your browser version, we recommend that you turn on Sync ([https://go.microsoft.com/fwlink/?linkid=2133032](https://go.microsoft.com/fwlink/?linkid=2133032)) for all users in your organization.</span></span> <span data-ttu-id="7ccc9-360">如果未启用同步，则有可能造成永久性浏览数据丢失。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-360">If you don't turn on Sync, there is a risk of permanent browsing data loss.</span></span> <span data-ttu-id="7ccc9-361">使用本政策，风险自担。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-361">Use this policy at your own risk.</span></span>

<span data-ttu-id="7ccc9-362">注意：可在此处查看所有可供回退的版本 [https://aka.ms/EdgeEnterprise](https://aka.ms/EdgeEnterprise)。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-362">Note: All versions available for rollback can be viewed here [https://aka.ms/EdgeEnterprise](https://aka.ms/EdgeEnterprise).</span></span>

<span data-ttu-id="7ccc9-363">此政策适用于Microsoft Edge 86或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-363">This policy applies to Microsoft Edge version 86 or later.</span></span>

<span data-ttu-id="7ccc9-364">有关详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2133918](https://go.microsoft.com/fwlink/?linkid=2133918)。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-364">See [https://go.microsoft.com/fwlink/?linkid=2133918](https://go.microsoft.com/fwlink/?linkid=2133918) for more information.</span></span>

<span data-ttu-id="7ccc9-365">此策略仅在加入Microsoft® Active Directory®域的Windows实例上可用。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-365">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="7ccc9-366">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-366">Windows information and settings</span></span>
##### <span data-ttu-id="7ccc9-367">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="7ccc9-367">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7ccc9-368">GP 唯一名称：RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="7ccc9-368">GP unique name: RollbackToTargetVersion</span></span>
- <span data-ttu-id="7ccc9-369">GP 名称：回退到目标版本</span><span class="sxs-lookup"><span data-stu-id="7ccc9-369">GP name: Rollback to Target version</span></span>
- <span data-ttu-id="7ccc9-370">GP 路径：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-370">GP path:</span></span> 
  - <span data-ttu-id="7ccc9-371">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7ccc9-371">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="7ccc9-372">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="7ccc9-372">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="7ccc9-373">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="7ccc9-373">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="7ccc9-374">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="7ccc9-374">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="7ccc9-375">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7ccc9-375">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7ccc9-376">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-376">Windows Registry Settings</span></span>
- <span data-ttu-id="7ccc9-377">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7ccc9-377">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7ccc9-378">值名称：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-378">Value Name:</span></span> 
  - <span data-ttu-id="7ccc9-379">（稳定版）：RollbackToTargetVersion{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-379">(Stable): RollbackToTargetVersion{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="7ccc9-380">（Beta版）：RollbackToTargetVersion{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-380">(Beta): RollbackToTargetVersion{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="7ccc9-381">（Canary版）：RollbackToTargetVersion{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-381">(Canary): RollbackToTargetVersion{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="7ccc9-382">（开发者版）：RollbackToTargetVersion{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-382">(Dev): RollbackToTargetVersion{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="7ccc9-383">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7ccc9-383">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7ccc9-384">示例值：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-384">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="7ccc9-385">返回页首</span><span class="sxs-lookup"><span data-stu-id="7ccc9-385">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7ccc9-386">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="7ccc9-386">TargetVersionPrefix</span></span>
#### <span data-ttu-id="7ccc9-387">目标版本覆盖</span><span class="sxs-lookup"><span data-stu-id="7ccc9-387">Target version override</span></span>
><span data-ttu-id="7ccc9-388">Microsoft Edge 更新 1.3.119.43 和更高版本</span><span class="sxs-lookup"><span data-stu-id="7ccc9-388">Microsoft Edge Update 1.3.119.43 and later</span></span>

#### <span data-ttu-id="7ccc9-389">描述</span><span class="sxs-lookup"><span data-stu-id="7ccc9-389">Description</span></span>
<span data-ttu-id="7ccc9-390">启用此策略并启用自动更新后，Microsoft Edge 将更新为该策略值指定的版本。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-390">When this policy is enabled, and auto-update is enabled, Microsoft Edge will be updated to the version specified by this policy value.</span></span>

<span data-ttu-id="7ccc9-391">策略值必须是特定的 Microsoft Edge 版本，例如 83.0.499.12。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-391">The policy value must be a specific Microsoft Edge version, e.g. 83.0.499.12.</span></span>

<span data-ttu-id="7ccc9-392">如果设备的 Microsoft Edge 版本高于指定的值，Microsoft Edge 将保留较新版本，不会降级到指定版本。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-392">If a device has newer version of Microsoft Edge than the value specified, Microsoft Edge will remain on the newer version and not downgrade to the specified version.</span></span>

<span data-ttu-id="7ccc9-393">如果指定版本不存在，或格式不正确，Microsoft Edge 将保留当前版本，不会自动更新为未来版本。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-393">If the specified version does not exist, or is improperly formatted, then Microsoft Edge will remain on its current version and not update to future versions automatically.</span></span>

<span data-ttu-id="7ccc9-394">有关详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2136707](https://go.microsoft.com/fwlink/?linkid=2136707)。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-394">See [https://go.microsoft.com/fwlink/?linkid=2136707](https://go.microsoft.com/fwlink/?linkid=2136707) for more information.</span></span>

<span data-ttu-id="7ccc9-395">此策略仅在加入Microsoft® Active Directory®域的Windows实例上可用。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-395">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="7ccc9-396">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-396">Windows information and settings</span></span>
##### <span data-ttu-id="7ccc9-397">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="7ccc9-397">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7ccc9-398">GP 唯一名称：TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="7ccc9-398">GP unique name: TargetVersionPrefix</span></span>
- <span data-ttu-id="7ccc9-399">GP 名称：目标版本覆盖</span><span class="sxs-lookup"><span data-stu-id="7ccc9-399">GP name: Target version override</span></span>
- <span data-ttu-id="7ccc9-400">GP 路径：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-400">GP path:</span></span> 
  - <span data-ttu-id="7ccc9-401">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7ccc9-401">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="7ccc9-402">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="7ccc9-402">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="7ccc9-403">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="7ccc9-403">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="7ccc9-404">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="7ccc9-404">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="7ccc9-405">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7ccc9-405">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7ccc9-406">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-406">Windows Registry Settings</span></span>
- <span data-ttu-id="7ccc9-407">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7ccc9-407">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7ccc9-408">值名称：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-408">Value Name:</span></span> 
  - <span data-ttu-id="7ccc9-409">（稳定版）：TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-409">(Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="7ccc9-410">（Beta 版）： TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-410">(Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="7ccc9-411">（金丝雀版）： TargetVersionPrefix {65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-411">(Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="7ccc9-412">（开发者版本）：更新 {0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-412">(Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="7ccc9-413">值类型：REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7ccc9-413">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="7ccc9-414">示例值：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-414">Example value:</span></span>
```
83.0.499.12
```
[<span data-ttu-id="7ccc9-415">返回页首</span><span class="sxs-lookup"><span data-stu-id="7ccc9-415">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="7ccc9-416">首选项策略</span><span class="sxs-lookup"><span data-stu-id="7ccc9-416">Preferences policies</span></span>

[<span data-ttu-id="7ccc9-417">返回页首</span><span class="sxs-lookup"><span data-stu-id="7ccc9-417">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="7ccc9-418">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="7ccc9-418">AutoUpdateCheckPeriodMinutes</span></span>
#### <span data-ttu-id="7ccc9-419">自动更新检查期间替代</span><span class="sxs-lookup"><span data-stu-id="7ccc9-419">Auto-update check period override</span></span>
><span data-ttu-id="7ccc9-420">Microsoft Edge 更新 1.2.145.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="7ccc9-420">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="7ccc9-421">描述</span><span class="sxs-lookup"><span data-stu-id="7ccc9-421">Description</span></span>
<span data-ttu-id="7ccc9-422">如果启用了此策略，你可以为各次自动更新检查间隔的最小分钟数设置一个值。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-422">If enabled, this policy lets you set a value for the minimum number of minutes between automatic update checks.</span></span> <span data-ttu-id="7ccc9-423">否则，默认情况下，自动更新将每 10 小时检查一次更新。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-423">Otherwise, by default, auto-update checks for updates every 10 hours.</span></span>

  <span data-ttu-id="7ccc9-424">如果你想要禁用所有自动更新检查，请将该值设置为 0（不推荐）。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-424">If you want to disable all auto-update checks, set the value to 0 (not recommended).</span></span>
#### <span data-ttu-id="7ccc9-425">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-425">Windows information and settings</span></span>
##### <span data-ttu-id="7ccc9-426">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="7ccc9-426">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7ccc9-427">GP 唯一名称：AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="7ccc9-427">GP unique name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="7ccc9-428">GP 名称：自动更新检查期间替代</span><span class="sxs-lookup"><span data-stu-id="7ccc9-428">GP name: Auto-update check period override</span></span>
- <span data-ttu-id="7ccc9-429">GP 路径：Administrative Templates/Microsoft Edge Update/Preferences</span><span class="sxs-lookup"><span data-stu-id="7ccc9-429">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="7ccc9-430">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7ccc9-430">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7ccc9-431">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-431">Windows Registry Settings</span></span>
- <span data-ttu-id="7ccc9-432">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7ccc9-432">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7ccc9-433">值名称：AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="7ccc9-433">Value Name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="7ccc9-434">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7ccc9-434">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7ccc9-435">示例值：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-435">Example value:</span></span>
```
0x00000578
```
[<span data-ttu-id="7ccc9-436">返回页首</span><span class="sxs-lookup"><span data-stu-id="7ccc9-436">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7ccc9-437">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="7ccc9-437">UpdatesSuppressed</span></span>
#### <span data-ttu-id="7ccc9-438">每天中取消自动更新检查的时间段</span><span class="sxs-lookup"><span data-stu-id="7ccc9-438">Time period in each day to suppress auto-update check</span></span>
><span data-ttu-id="7ccc9-439">Microsoft Edge 更新 1.3.33.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="7ccc9-439">Microsoft Edge Update 1.3.33.5 and later</span></span>

#### <span data-ttu-id="7ccc9-440">描述</span><span class="sxs-lookup"><span data-stu-id="7ccc9-440">Description</span></span>
<span data-ttu-id="7ccc9-441">如果你启用此策略，则每天都会从 Hour:Minute 开始持续一段时间（以分钟为单位）禁止更新检查。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-441">If you enable this policy, update checks are suppressed each day starting at Hour:Minute for a period of Duration (in minutes).</span></span> <span data-ttu-id="7ccc9-442">持续时间不受夏令时影响。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-442">Duration isn't affected by daylight saving time.</span></span> <span data-ttu-id="7ccc9-443">例如，如果开始时间是 22:00，持续时间为 480 分钟，则无论夏令时是在此期间开始还是结束，更新都将正好禁止 8 小时。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-443">For example, if the start time is 22:00 and the duration is 480 minutes, updates will be suppressed for exactly 8 hours, regardless of whether daylight saving time starts or ends during this period.</span></span>

  <span data-ttu-id="7ccc9-444">如果你禁用或未配置此策略，则不会在任何特定期间取消更新检查。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-444">If you disable or don't configure this policy, update checks aren't suppressed during any specific period.</span></span>
#### <span data-ttu-id="7ccc9-445">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-445">Windows information and settings</span></span>
##### <span data-ttu-id="7ccc9-446">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="7ccc9-446">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7ccc9-447">GP 唯一名称：UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="7ccc9-447">GP unique name: UpdatesSuppressed</span></span>
- <span data-ttu-id="7ccc9-448">GP 名称：每天中取消自动更新检查的时间段</span><span class="sxs-lookup"><span data-stu-id="7ccc9-448">GP name: Time period in each day to suppress auto-update check</span></span>
  - <span data-ttu-id="7ccc9-449">选项 { Hour, Minute, Duration }</span><span class="sxs-lookup"><span data-stu-id="7ccc9-449">Options { Hour, Minute, Duration }</span></span>
- <span data-ttu-id="7ccc9-450">GP 路径：Administrative Templates/Microsoft Edge Update/Preferences</span><span class="sxs-lookup"><span data-stu-id="7ccc9-450">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="7ccc9-451">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7ccc9-451">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7ccc9-452">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-452">Windows Registry Settings</span></span>
- <span data-ttu-id="7ccc9-453">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7ccc9-453">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7ccc9-454">值名称：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-454">Value Name:</span></span> 
  - <span data-ttu-id="7ccc9-455">UpdatesSuppressedDurationMin</span><span class="sxs-lookup"><span data-stu-id="7ccc9-455">UpdatesSuppressedDurationMin</span></span>
  - <span data-ttu-id="7ccc9-456">UpdatesSuppressedStartHour</span><span class="sxs-lookup"><span data-stu-id="7ccc9-456">UpdatesSuppressedStartHour</span></span>
  - <span data-ttu-id="7ccc9-457">UpdatesSuppressedStartMin</span><span class="sxs-lookup"><span data-stu-id="7ccc9-457">UpdatesSuppressedStartMin</span></span>
- <span data-ttu-id="7ccc9-458">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7ccc9-458">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7ccc9-459">示例值：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-459">Example value:</span></span>
```
duration   : 0x0000003c
start hour : 0x00000001
start min  : 0x00000002
```
[<span data-ttu-id="7ccc9-460">返回页首</span><span class="sxs-lookup"><span data-stu-id="7ccc9-460">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="7ccc9-461">代理服务器策略</span><span class="sxs-lookup"><span data-stu-id="7ccc9-461">Proxy Server policies</span></span>

[<span data-ttu-id="7ccc9-462">返回页首</span><span class="sxs-lookup"><span data-stu-id="7ccc9-462">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="7ccc9-463">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="7ccc9-463">ProxyMode</span></span>
#### <span data-ttu-id="7ccc9-464">选择指定代理服务器设置的方式</span><span class="sxs-lookup"><span data-stu-id="7ccc9-464">Choose how to specify proxy server settings</span></span>
><span data-ttu-id="7ccc9-465">Microsoft Edge 更新 1.3.21.81 和更高版本</span><span class="sxs-lookup"><span data-stu-id="7ccc9-465">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="7ccc9-466">描述</span><span class="sxs-lookup"><span data-stu-id="7ccc9-466">Description</span></span>
<span data-ttu-id="7ccc9-467">允许你指定 Microsoft Edge 更新使用的代理服务器设置。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-467">Allows you to specify the proxy server settings that are used by Microsoft Edge Update.</span></span>

  <span data-ttu-id="7ccc9-468">如果你启用此策略，则可以在以下代理服务器选项之间进行选择：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-468">If you enable this policy, you can choose between the following proxy server options:</span></span>
   - <span data-ttu-id="7ccc9-469">如果你选择从不使用代理服务器并且始终直接连接，则所有其他选项都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-469">If you choose to never use a proxy server and always connect directly, all other options are ignored.</span></span>
   - <span data-ttu-id="7ccc9-470">如果你选择使用系统代理设置或自动检测代理服务器，则所有其他选项都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-470">If you choose to use system proxy settings or auto-detect the proxy server, all other options are ignored.</span></span>
   - <span data-ttu-id="7ccc9-471">如果你选择固定服务器代理模式，则可以在 “[代理服务器的地址或 URL](#proxyserver)” 策略中指定更多选项。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-471">If you choose fixed server proxy mode, you can specify further options in '[Address or URL of proxy server](#proxyserver)' policy.</span></span>
   - <span data-ttu-id="7ccc9-472">如果你选择使用 .pac 代理脚本，则必须在 “[代理 .pac 文件的 URL](#proxypacurl)”策略中为脚本指定 URL。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-472">If you choose to use a .pac proxy script, you must specify the URL for the script in '[URL to a proxy .pac file](#proxypacurl)' policy.</span></span>

  <span data-ttu-id="7ccc9-473">如果你启用此策略，则你所在组织中的用户无法在 Microsoft Edge 更新中更改代理设置。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-473">If you enable this policy, users in your organization can't change the proxy settings in Microsoft Edge Update.</span></span>

  <span data-ttu-id="7ccc9-474">如果你禁用或未配置此策略，则不会配置任何代理服务器设置，但组织中的用户可以为 Microsoft Edge 更新选择自己的代理设置。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-474">If you disable or don't configure this policy, no proxy server settings are configured, but users in your organization can choose their own proxy settings for Microsoft Edge Update.</span></span>
#### <span data-ttu-id="7ccc9-475">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-475">Windows information and settings</span></span>
##### <span data-ttu-id="7ccc9-476">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="7ccc9-476">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7ccc9-477">GP 唯一名称：ProxyMode</span><span class="sxs-lookup"><span data-stu-id="7ccc9-477">GP unique name: ProxyMode</span></span>
- <span data-ttu-id="7ccc9-478">GP 名称：选择指定代理服务器设置的方式</span><span class="sxs-lookup"><span data-stu-id="7ccc9-478">GP name: Choose how to specify proxy server settings</span></span>
- <span data-ttu-id="7ccc9-479">GP 路径：Administrative Templates/Microsoft Edge Update/Proxy Server</span><span class="sxs-lookup"><span data-stu-id="7ccc9-479">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="7ccc9-480">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7ccc9-480">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7ccc9-481">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-481">Windows Registry Settings</span></span>
- <span data-ttu-id="7ccc9-482">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7ccc9-482">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7ccc9-483">值名称：ProxyMode</span><span class="sxs-lookup"><span data-stu-id="7ccc9-483">Value Name: ProxyMode</span></span>
- <span data-ttu-id="7ccc9-484">值类型：REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7ccc9-484">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="7ccc9-485">示例值：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-485">Example value:</span></span>
```
fixed_servers
```
[<span data-ttu-id="7ccc9-486">返回页首</span><span class="sxs-lookup"><span data-stu-id="7ccc9-486">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7ccc9-487">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="7ccc9-487">ProxyPacUrl</span></span>
#### <span data-ttu-id="7ccc9-488">代理 .pac 文件的 URL</span><span class="sxs-lookup"><span data-stu-id="7ccc9-488">URL to a proxy .pac file</span></span>
><span data-ttu-id="7ccc9-489">Microsoft Edge 更新 1.3.21.81 和更高版本</span><span class="sxs-lookup"><span data-stu-id="7ccc9-489">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="7ccc9-490">描述</span><span class="sxs-lookup"><span data-stu-id="7ccc9-490">Description</span></span>
<span data-ttu-id="7ccc9-491">允许你为代理自动配置 (PAC) 文件指定 URL。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-491">Allows you to specify a URL for a proxy auto-config (PAC) file.</span></span>

  <span data-ttu-id="7ccc9-492">如果你启用此策略，则可以为 PAC 文件指定 URL，以自动执行 Microsoft Edge 更新为提取特定网站而选择合适代理服务器的方法。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-492">If you enable this policy, you can specify a URL for a PAC file to automate how Microsoft Edge Update selects the appropriate proxy server for fetching a particular website.</span></span>

  <span data-ttu-id="7ccc9-493">仅当你已在“[选择如何指定代理服务器设置](#proxymode)”策略中指定了手动代理设置时，才会应用此策略。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-493">This policy is applied only if you have specified manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="7ccc9-494">如果你已在“[选择如何指定代理服务器设置](#proxymode)”策略中选择了手动设置以外的其他代理设置，请不要配置此策略。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-494">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <span data-ttu-id="7ccc9-495">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-495">Windows information and settings</span></span>
##### <span data-ttu-id="7ccc9-496">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="7ccc9-496">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7ccc9-497">GP 唯一名称：ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="7ccc9-497">GP unique name: ProxyPacUrl</span></span>
- <span data-ttu-id="7ccc9-498">GP 名称：代理 .pac 文件的 URL</span><span class="sxs-lookup"><span data-stu-id="7ccc9-498">GP name: URL to a proxy .pac file</span></span>
- <span data-ttu-id="7ccc9-499">GP 路径：Administrative Templates/Microsoft Edge Update/Proxy Server</span><span class="sxs-lookup"><span data-stu-id="7ccc9-499">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="7ccc9-500">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7ccc9-500">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7ccc9-501">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-501">Windows Registry Settings</span></span>
- <span data-ttu-id="7ccc9-502">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7ccc9-502">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7ccc9-503">值名称：ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="7ccc9-503">Value Name: ProxyPacUrl</span></span>
- <span data-ttu-id="7ccc9-504">值类型：REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7ccc9-504">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="7ccc9-505">示例值：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-505">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="7ccc9-506">返回页首</span><span class="sxs-lookup"><span data-stu-id="7ccc9-506">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7ccc9-507">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="7ccc9-507">ProxyServer</span></span>
#### <span data-ttu-id="7ccc9-508">代理服务器的地址或 URL</span><span class="sxs-lookup"><span data-stu-id="7ccc9-508">Address or URL of proxy server</span></span>
><span data-ttu-id="7ccc9-509">Microsoft Edge 更新 1.3.21.81 和更高版本</span><span class="sxs-lookup"><span data-stu-id="7ccc9-509">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="7ccc9-510">说明</span><span class="sxs-lookup"><span data-stu-id="7ccc9-510">Description</span></span>
<span data-ttu-id="7ccc9-511">允许你指定供 Microsoft Edge 更新使用的代理服务器的 URL。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-511">Allows you to specify the URL of the proxy server for Microsoft Edge Update to use.</span></span>

  <span data-ttu-id="7ccc9-512">如果启用此策略，则可以设置组织中 Microsoft Edge 更新使用的代理服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-512">If you enable this policy, you can set the proxy server URL used by Microsoft Edge Update in your organization.</span></span>

  <span data-ttu-id="7ccc9-513">仅当你已在[“选择如何指定代理服务器设置”](#proxymode)策略中选择了手动代理设置时，才会应用此策略。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-513">This policy is applied only if you have selected manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="7ccc9-514">如果你已在“[选择如何指定代理服务器设置](#proxymode)”策略中选择了手动设置以外的其他代理设置，请不要配置此策略。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-514">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <span data-ttu-id="7ccc9-515">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-515">Windows information and settings</span></span>
##### <span data-ttu-id="7ccc9-516">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="7ccc9-516">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7ccc9-517">GP 唯一名称：ProxyServer</span><span class="sxs-lookup"><span data-stu-id="7ccc9-517">GP unique name: ProxyServer</span></span>
- <span data-ttu-id="7ccc9-518">GP 名称：代理服务器的地址或 URL</span><span class="sxs-lookup"><span data-stu-id="7ccc9-518">GP name: Address or URL of proxy server</span></span>
- <span data-ttu-id="7ccc9-519">GP 路径：Administrative Templates/Microsoft Edge Update/Proxy Server</span><span class="sxs-lookup"><span data-stu-id="7ccc9-519">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="7ccc9-520">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7ccc9-520">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7ccc9-521">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-521">Windows Registry Settings</span></span>
- <span data-ttu-id="7ccc9-522">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7ccc9-522">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7ccc9-523">值名称：ProxyServer</span><span class="sxs-lookup"><span data-stu-id="7ccc9-523">Value Name: ProxyServer</span></span>
- <span data-ttu-id="7ccc9-524">值类型：REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7ccc9-524">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="7ccc9-525">示例值：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-525">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="7ccc9-526">返回页首</span><span class="sxs-lookup"><span data-stu-id="7ccc9-526">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="7ccc9-527">- Microsoft Edge Web 视图策略</span><span class="sxs-lookup"><span data-stu-id="7ccc9-527">Microsoft Edge WebView policies</span></span>

[<span data-ttu-id="7ccc9-528">返回页首</span><span class="sxs-lookup"><span data-stu-id="7ccc9-528">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="7ccc9-529">安装（WebView）</span><span class="sxs-lookup"><span data-stu-id="7ccc9-529">Install (WebView)</span></span>
#### <span data-ttu-id="7ccc9-530">允许安装</span><span class="sxs-lookup"><span data-stu-id="7ccc9-530">Allow installation</span></span>
><span data-ttu-id="7ccc9-531">Microsoft Edge 更新 1.3.127.1 和更高版本</span><span class="sxs-lookup"><span data-stu-id="7ccc9-531">Microsoft Edge Update 1.3.127.1 and later</span></span>

#### <span data-ttu-id="7ccc9-532">描述</span><span class="sxs-lookup"><span data-stu-id="7ccc9-532">Description</span></span>
<span data-ttu-id="7ccc9-533">指定是否可以使用 Microsoft Edge 更新来安装 Microsoft Edge Web 视图。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-533">Lets you specify whether Microsoft Edge WebView can be installed using Microsoft Edge Update.</span></span>

  - <span data-ttu-id="7ccc9-534">如果启用此策略，用户可以通过 Microsoft Edge 更新来安装该 Microsoft Edge Web 视图。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-534">If you enable this policy, users can install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
  - <span data-ttu-id="7ccc9-535">如果禁用此策略，用户无法通过 Microsoft Edge 更新来安装该 Microsoft Edge Web 视图。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-535">If you disable this policy, users cannot install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
  - <span data-ttu-id="7ccc9-536">如果没有配置此策略，则“[允许安装默认项](#installdefault)”策略配置将决定用户是否可以通过 Microsoft Edge 更新来安装该 Microsoft Edge WebView。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-536">If you don't configure this policy, the '[Allow installation default](#installdefault)' policy configuration determines whether users can install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
#### <span data-ttu-id="7ccc9-537">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-537">Windows information and settings</span></span>
##### <span data-ttu-id="7ccc9-538">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="7ccc9-538">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7ccc9-539">GP 唯一名称：安装</span><span class="sxs-lookup"><span data-stu-id="7ccc9-539">GP unique name: Install</span></span>
- <span data-ttu-id="7ccc9-540">GP 名称：允许安装</span><span class="sxs-lookup"><span data-stu-id="7ccc9-540">GP name: Allow installation</span></span>
- <span data-ttu-id="7ccc9-541">GP 路径：Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="7ccc9-541">GP path: Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView</span></span>
- <span data-ttu-id="7ccc9-542">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7ccc9-542">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7ccc9-543">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-543">Windows Registry Settings</span></span>
- <span data-ttu-id="7ccc9-544">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7ccc9-544">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7ccc9-545">值名称：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-545">Value Name:</span></span> 
  - <span data-ttu-id="7ccc9-546">安装{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-546">Install{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span></span>
- <span data-ttu-id="7ccc9-547">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7ccc9-547">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7ccc9-548">示例值：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-548">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="7ccc9-549">返回页首</span><span class="sxs-lookup"><span data-stu-id="7ccc9-549">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="7ccc9-550">更新（WebView）</span><span class="sxs-lookup"><span data-stu-id="7ccc9-550">Update (WebView)</span></span>
#### <span data-ttu-id="7ccc9-551">更新策略替代</span><span class="sxs-lookup"><span data-stu-id="7ccc9-551">Update policy override</span></span>
><span data-ttu-id="7ccc9-552">Microsoft Edge 更新 1.3.127.1 和更高版本</span><span class="sxs-lookup"><span data-stu-id="7ccc9-552">Microsoft Edge Update 1.3.127.1 and later</span></span>

#### <span data-ttu-id="7ccc9-553">描述</span><span class="sxs-lookup"><span data-stu-id="7ccc9-553">Description</span></span>
<span data-ttu-id="7ccc9-554">可针对 Microsoft Edge Web 视图指定启用或不启用自动更新。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-554">Lets you specify whether or not automatic updates are enabled for Microsoft Edge WebView.</span></span> <span data-ttu-id="7ccc9-555">Microsoft Edge Web 视图是应用程序用来显示 Web 内容的组件。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-555">Microsoft Edge WebView is a component used by applications to display web content.</span></span>
<span data-ttu-id="7ccc9-556">默认情况下启用自动更新。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-556">Automatic updates are enabled by default.</span></span> <span data-ttu-id="7ccc9-557">禁用 Microsoft Edge Web Edge 自动更新可能会导致依赖于此组件的应用程序出现兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-557">Disabling automatic updates for Microsoft Edge WebView might cause compatibility issues with applications that depend on this component.</span></span>

  <span data-ttu-id="7ccc9-558">如果你启用此策略，Microsoft Edge 更新将根据你配置以下选项的方式处理 Microsoft Edge Web 视图更新：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-558">If you enable this policy, Microsoft Edge Update handles Microsoft Edge WebView updates according to how you configure the following options:</span></span>
  - <span data-ttu-id="7ccc9-559">始终允许更新：自动下载和应用更新</span><span class="sxs-lookup"><span data-stu-id="7ccc9-559">Always allow updates: Updates are automatically downloaded and applied</span></span>
  - <span data-ttu-id="7ccc9-560">禁用更新：从不下载或应用更新。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-560">Updates disabled: Updates are never downloaded or applied</span></span>

  <span data-ttu-id="7ccc9-561">如果未启用此策略，则自动下载并应用更新。</span><span class="sxs-lookup"><span data-stu-id="7ccc9-561">If you don't enable this policy, updates are automatically downloaded and applied.</span></span>
#### <span data-ttu-id="7ccc9-562">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-562">Windows information and settings</span></span>
##### <span data-ttu-id="7ccc9-563">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="7ccc9-563">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="7ccc9-564">GP 唯一名称：更新</span><span class="sxs-lookup"><span data-stu-id="7ccc9-564">GP unique name: Update</span></span>
- <span data-ttu-id="7ccc9-565">GP 名称：更新策略替代</span><span class="sxs-lookup"><span data-stu-id="7ccc9-565">GP name: Update policy override</span></span>
- <span data-ttu-id="7ccc9-566">GP 路径：Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="7ccc9-566">GP path: Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView</span></span>
- <span data-ttu-id="7ccc9-567">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="7ccc9-567">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="7ccc9-568">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="7ccc9-568">Windows Registry Settings</span></span>
- <span data-ttu-id="7ccc9-569">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="7ccc9-569">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="7ccc9-570">值名称：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-570">Value Name:</span></span> 
  - <span data-ttu-id="7ccc9-571">Update{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span><span class="sxs-lookup"><span data-stu-id="7ccc9-571">Update{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span></span>
- <span data-ttu-id="7ccc9-572">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="7ccc9-572">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="7ccc9-573">示例值：</span><span class="sxs-lookup"><span data-stu-id="7ccc9-573">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="7ccc9-574">返回页首</span><span class="sxs-lookup"><span data-stu-id="7ccc9-574">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="7ccc9-575">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ccc9-575">See also</span></span>
  - [<span data-ttu-id="7ccc9-576">配置 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7ccc9-576">Configuring Microsoft Edge</span></span>](configure-microsoft-edge.md)
  - [<span data-ttu-id="7ccc9-577">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="7ccc9-577">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)