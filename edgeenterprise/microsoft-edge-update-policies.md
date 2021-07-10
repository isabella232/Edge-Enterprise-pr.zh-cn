---
title: Microsoft Edge 更新策略文档
ms.author: stmoody
author: dan-wesley
manager: tahills
ms.date: 06/29/2021
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.custom: ''
description: Microsoft Edge 更新程序支持的所有策略的文档
ms.openlocfilehash: a9808981acad544042c6e0ccb59ff755a670c848
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642318"
---
# <a name="microsoft-edge---update-policies"></a><span data-ttu-id="0f525-103">Microsoft Edge - 更新策略</span><span class="sxs-lookup"><span data-stu-id="0f525-103">Microsoft Edge - Update policies</span></span>

<span data-ttu-id="0f525-104">最新版本的 Microsoft Edge 包含以下策略，你可以使用这些策略控制更新 Microsoft Edge 的方式和时间。</span><span class="sxs-lookup"><span data-stu-id="0f525-104">The latest version of Microsoft Edge includes the following policies that you can use to control how and when Microsoft Edge is updated.</span></span>

<span data-ttu-id="0f525-105">有关 Microsoft Edge 中可用的其他策略的信息，请查看 [Microsoft Edge 浏览器策略引用](microsoft-edge-policies.md)</span><span class="sxs-lookup"><span data-stu-id="0f525-105">For information about other policies available in Microsoft Edge, check out [Microsoft Edge browser policy reference](microsoft-edge-policies.md)</span></span>
> [!NOTE]
> <span data-ttu-id="0f525-106">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="0f525-106">This article applies to Microsoft Edge version 77 or later.</span></span>
## <a name="available-policies"></a><span data-ttu-id="0f525-107">可用策略</span><span class="sxs-lookup"><span data-stu-id="0f525-107">Available policies</span></span>
<span data-ttu-id="0f525-108">这些表列出了本版本 Microsoft Edge 中提供的所有与更新相关的组策略。</span><span class="sxs-lookup"><span data-stu-id="0f525-108">These tables lists all of the update-related group policies available in this release of Microsoft Edge.</span></span> <span data-ttu-id="0f525-109">使用表中的链接获取有关特定策略的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="0f525-109">Use the links in the table to get more details about specific policies.</span></span>

<span data-ttu-id="0f525-110">|&nbsp;|&nbsp;| |**-**|-| |**[应用程序](#applications)**|[首选项](#preferences)| |**[代理服务器](#proxy-server)**|[Microsoft Edge WebView](#microsoft-edge-webview)|</span><span class="sxs-lookup"><span data-stu-id="0f525-110">|&nbsp;|&nbsp;| |**-**|-| |**[Applications](#applications)**|[Preferences](#preferences)| |**[Proxy Server](#proxy-server)**|[Microsoft Edge WebView](#microsoft-edge-webview)|</span></span>
### [<a name="applications"></a><span data-ttu-id="0f525-111">应用程序</span><span class="sxs-lookup"><span data-stu-id="0f525-111">Applications</span></span>](#applications-policies)
|<span data-ttu-id="0f525-112">策略名称</span><span class="sxs-lookup"><span data-stu-id="0f525-112">Policy Name</span></span>|<span data-ttu-id="0f525-113">描述文字</span><span class="sxs-lookup"><span data-stu-id="0f525-113">Caption</span></span>|
|-|-|
|[<span data-ttu-id="0f525-114">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="0f525-114">InstallDefault</span></span>](#installdefault)|<span data-ttu-id="0f525-115">允许安装默认项</span><span class="sxs-lookup"><span data-stu-id="0f525-115">Allow installation default</span></span>|
|[<span data-ttu-id="0f525-116">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="0f525-116">UpdateDefault</span></span>](#updatedefault)|<span data-ttu-id="0f525-117">更新策略替代默认值</span><span class="sxs-lookup"><span data-stu-id="0f525-117">Update policy override default</span></span>|
|[<span data-ttu-id="0f525-118">安装</span><span class="sxs-lookup"><span data-stu-id="0f525-118">Install</span></span>](#install)|<span data-ttu-id="0f525-119">允许安装（按渠道）</span><span class="sxs-lookup"><span data-stu-id="0f525-119">Allow installation (per channel)</span></span>|
|[<span data-ttu-id="0f525-120">更新</span><span class="sxs-lookup"><span data-stu-id="0f525-120">Update</span></span>](#update)|<span data-ttu-id="0f525-121">更新策略替代（按渠道）</span><span class="sxs-lookup"><span data-stu-id="0f525-121">Update policy override (per channel)</span></span>|
|[<span data-ttu-id="0f525-122">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="0f525-122">Allowsxs</span></span>](#allowsxs)|<span data-ttu-id="0f525-123">允许 Microsoft Edge 并行浏览器体验</span><span class="sxs-lookup"><span data-stu-id="0f525-123">Allow Microsoft Edge Side by Side browser experience</span></span>|
|[<span data-ttu-id="0f525-124">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="0f525-124">CreateDesktopShortcutDefault</span></span>](#createdesktopshortcutdefault)|<span data-ttu-id="0f525-125">安装默认项时阻止创建快捷方式</span><span class="sxs-lookup"><span data-stu-id="0f525-125">Prevent Desktop Shortcut creation upon install default</span></span>|
|[<span data-ttu-id="0f525-126">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="0f525-126">CreateDesktopShortcut</span></span>](#createdesktopshortcut)|<span data-ttu-id="0f525-127">安装时阻止创建快捷方式（按渠道）</span><span class="sxs-lookup"><span data-stu-id="0f525-127">Prevent Desktop Shortcut creation upon install (per channel)</span></span>|
|[<span data-ttu-id="0f525-128">RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="0f525-128">RollbackToTargetVersion</span></span>](#rollbacktotargetversion)|<span data-ttu-id="0f525-129">回退到目标版本（按渠道）</span><span class="sxs-lookup"><span data-stu-id="0f525-129">Rollback to Target version (per channel)</span></span>|
|[<span data-ttu-id="0f525-130">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="0f525-130">TargetVersionPrefix</span></span>](#targetversionprefix)|<span data-ttu-id="0f525-131">目标版本覆盖（各渠道）</span><span class="sxs-lookup"><span data-stu-id="0f525-131">Target version override (per channel)</span></span>|

### [<a name="preferences"></a><span data-ttu-id="0f525-132">首选项</span><span class="sxs-lookup"><span data-stu-id="0f525-132">Preferences</span></span>](#preferences-policies)
|<span data-ttu-id="0f525-133">策略名称</span><span class="sxs-lookup"><span data-stu-id="0f525-133">Policy Name</span></span>|<span data-ttu-id="0f525-134">描述文字</span><span class="sxs-lookup"><span data-stu-id="0f525-134">Caption</span></span>|
|-|-|
|[<span data-ttu-id="0f525-135">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="0f525-135">AutoUpdateCheckPeriodMinutes</span></span>](#autoupdatecheckperiodminutes)|<span data-ttu-id="0f525-136">自动更新检查期间替代</span><span class="sxs-lookup"><span data-stu-id="0f525-136">Auto-update check period override</span></span>|
|[<span data-ttu-id="0f525-137">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="0f525-137">UpdatesSuppressed</span></span>](#updatessuppressed)|<span data-ttu-id="0f525-138">每天中取消自动更新检查的时间段</span><span class="sxs-lookup"><span data-stu-id="0f525-138">Time period in each day to suppress auto-update check</span></span>|

### [<a name="proxy-server"></a><span data-ttu-id="0f525-139">代理服务器</span><span class="sxs-lookup"><span data-stu-id="0f525-139">Proxy Server</span></span>](#proxy-server-policies)
|<span data-ttu-id="0f525-140">策略名称</span><span class="sxs-lookup"><span data-stu-id="0f525-140">Policy Name</span></span>|<span data-ttu-id="0f525-141">描述文字</span><span class="sxs-lookup"><span data-stu-id="0f525-141">Caption</span></span>|
|-|-|
|[<span data-ttu-id="0f525-142">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="0f525-142">ProxyMode</span></span>](#proxymode)|<span data-ttu-id="0f525-143">选择指定代理服务器设置的方式</span><span class="sxs-lookup"><span data-stu-id="0f525-143">Choose how to specify proxy server settings</span></span>|
|[<span data-ttu-id="0f525-144">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="0f525-144">ProxyPacUrl</span></span>](#proxypacurl)|<span data-ttu-id="0f525-145">代理 .pac 文件的 URL</span><span class="sxs-lookup"><span data-stu-id="0f525-145">URL to a proxy .pac file</span></span>|
|[<span data-ttu-id="0f525-146">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="0f525-146">ProxyServer</span></span>](#proxyserver)|<span data-ttu-id="0f525-147">代理服务器的地址或 URL</span><span class="sxs-lookup"><span data-stu-id="0f525-147">Address or URL of proxy server</span></span>|

### [<a name="microsoft-edge-webview"></a><span data-ttu-id="0f525-148">Microsoft Edge Web 视图</span><span class="sxs-lookup"><span data-stu-id="0f525-148">Microsoft Edge WebView</span></span>](#microsoft-edge-webview-policies)
|<span data-ttu-id="0f525-149">策略名称</span><span class="sxs-lookup"><span data-stu-id="0f525-149">Policy Name</span></span>|<span data-ttu-id="0f525-150">标题</span><span class="sxs-lookup"><span data-stu-id="0f525-150">Caption</span></span>|
|-|-|
|[<span data-ttu-id="0f525-151">安装</span><span class="sxs-lookup"><span data-stu-id="0f525-151">Install</span></span>](#install-webview)|<span data-ttu-id="0f525-152">允许安装</span><span class="sxs-lookup"><span data-stu-id="0f525-152">Allow installation</span></span>|
|[<span data-ttu-id="0f525-153">更新</span><span class="sxs-lookup"><span data-stu-id="0f525-153">Update</span></span>](#update-webview)|<span data-ttu-id="0f525-154">更新策略替代</span><span class="sxs-lookup"><span data-stu-id="0f525-154">Update policy override</span></span>|

## <a name="applications-policies"></a><span data-ttu-id="0f525-155">应用程序策略</span><span class="sxs-lookup"><span data-stu-id="0f525-155">Applications policies</span></span>

[<span data-ttu-id="0f525-156">返回页首</span><span class="sxs-lookup"><span data-stu-id="0f525-156">Back to top</span></span>](#microsoft-edge---update-policies)
### <a name="installdefault"></a><span data-ttu-id="0f525-157">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="0f525-157">InstallDefault</span></span>
#### <a name="allow-installation-default"></a><span data-ttu-id="0f525-158">允许安装默认项</span><span class="sxs-lookup"><span data-stu-id="0f525-158">Allow installation default</span></span>
><span data-ttu-id="0f525-159">Microsoft Edge 更新 1.2.145.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="0f525-159">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="0f525-160">描述</span><span class="sxs-lookup"><span data-stu-id="0f525-160">Description</span></span>
<span data-ttu-id="0f525-161">可指定所有渠道的默认行为，以允许或阻止域连接设备上的Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="0f525-161">You can specify the default behavior of all channels to allow or block Microsoft Edge on domain-joined devices.</span></span>

<span data-ttu-id="0f525-162">通过为那些特定渠道启用“[允许安装](#install)”策略，可为个别渠道覆盖此策略。</span><span class="sxs-lookup"><span data-stu-id="0f525-162">You can override this policy for individual channels by enabling the '[Allow installation](#install)' policy for specific channels.</span></span>

<span data-ttu-id="0f525-163">如果禁用此策略，则会阻止 Microsoft Edge的安装。</span><span class="sxs-lookup"><span data-stu-id="0f525-163">If you disable this policy, the installation of Microsoft Edge is blocked.</span></span> <span data-ttu-id="0f525-164">只有当 "[允许安装](#install)" 策略设置为 "未配置" 时，才会影响Microsoft Edge软件的安装。</span><span class="sxs-lookup"><span data-stu-id="0f525-164">This only affects the installation of Microsoft Edge software when the '[Allow installation](#install)' policy is set to Not Configured.</span></span>

<span data-ttu-id="0f525-165">此策略不会阻止运行 Microsoft Edge 更新，也不会阻止用户使用其他方法安装 Microsoft Edge 软件。</span><span class="sxs-lookup"><span data-stu-id="0f525-165">This policy doesn't prevent Microsoft Edge Update from running or prevent users from installing Microsoft Edge software using other methods.</span></span>

<span data-ttu-id="0f525-166">此策略仅在加入Microsoft® Active Directory®域的Windows实例上可用。</span><span class="sxs-lookup"><span data-stu-id="0f525-166">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="0f525-167">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="0f525-167">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="0f525-168">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="0f525-168">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="0f525-169">GP 唯一名称：InstallDefault</span><span class="sxs-lookup"><span data-stu-id="0f525-169">GP unique name: InstallDefault</span></span>
- <span data-ttu-id="0f525-170">GP 名称：允许安装默认项</span><span class="sxs-lookup"><span data-stu-id="0f525-170">GP name: Allow installation default</span></span>
- <span data-ttu-id="0f525-171">GP 路径：Administrative Templates/Microsoft Edge Update/Applications</span><span class="sxs-lookup"><span data-stu-id="0f525-171">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="0f525-172">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="0f525-172">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="0f525-173">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="0f525-173">Windows Registry Settings</span></span>
- <span data-ttu-id="0f525-174">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="0f525-174">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="0f525-175">值名称：InstallDefault</span><span class="sxs-lookup"><span data-stu-id="0f525-175">Value Name: InstallDefault</span></span>
- <span data-ttu-id="0f525-176">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="0f525-176">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="0f525-177">示例值：</span><span class="sxs-lookup"><span data-stu-id="0f525-177">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="0f525-178">返回页首</span><span class="sxs-lookup"><span data-stu-id="0f525-178">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="updatedefault"></a><span data-ttu-id="0f525-179">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="0f525-179">UpdateDefault</span></span>
#### <a name="update-policy-override-default"></a><span data-ttu-id="0f525-180">更新策略替代默认值</span><span class="sxs-lookup"><span data-stu-id="0f525-180">Update policy override default</span></span>
><span data-ttu-id="0f525-181">Microsoft Edge 更新 1.2.145.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="0f525-181">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="0f525-182">描述</span><span class="sxs-lookup"><span data-stu-id="0f525-182">Description</span></span>
<span data-ttu-id="0f525-183">允许你为所有渠道指定与 Microsoft Edge 更新处理 Microsoft Edge 可用更新的方式有关的默认行为。</span><span class="sxs-lookup"><span data-stu-id="0f525-183">Lets you specify the default behavior for all channels concerning the way Microsoft Edge Update handles available updates for Microsoft Edge.</span></span> <span data-ttu-id="0f525-184">通过为那些特定渠道指定“[更新策略替代](#update)”策略，可为个别渠道进行覆盖。</span><span class="sxs-lookup"><span data-stu-id="0f525-184">Can be overridden for individual channels by specifying the '[Update policy override](#update)' policy for those specific channels.</span></span>

  <span data-ttu-id="0f525-185">如果你启用此策略，Microsoft Edge 更新将根据你配置以下选项的方式处理 Microsoft Edge 更新：</span><span class="sxs-lookup"><span data-stu-id="0f525-185">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
   - <span data-ttu-id="0f525-186">始终允许更新：通过定期更新检查或通过手动更新检查，在发现更新时始终应用更新。</span><span class="sxs-lookup"><span data-stu-id="0f525-186">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
   - <span data-ttu-id="0f525-187">仅限自动无提示更新：仅在定期更新检查找到更新后才应用更新。</span><span class="sxs-lookup"><span data-stu-id="0f525-187">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
   - <span data-ttu-id="0f525-188">仅限手动更新：仅当用户运行手动更新检查时才应用更新。</span><span class="sxs-lookup"><span data-stu-id="0f525-188">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span>
   - <span data-ttu-id="0f525-189">已禁用更新：从不应用更新。</span><span class="sxs-lookup"><span data-stu-id="0f525-189">Updates disabled: Updates are never applied.</span></span>

  <span data-ttu-id="0f525-190">如果你选择手动更新，请确保使用应用的手动更新机制（如果有）定期检查更新。</span><span class="sxs-lookup"><span data-stu-id="0f525-190">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="0f525-191">如果你禁用更新，请定期检查更新，然后将它们分发给用户。</span><span class="sxs-lookup"><span data-stu-id="0f525-191">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

  <span data-ttu-id="0f525-192">如果你未启用和配置此策略，Microsoft Edge 更新将处理“[更新策略替代](#update)”策略指定的可用更新。</span><span class="sxs-lookup"><span data-stu-id="0f525-192">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override](#update)' policy.</span></span>

  <span data-ttu-id="0f525-193">此策略仅在加入Microsoft® Active Directory®域的Windows实例上可用。</span><span class="sxs-lookup"><span data-stu-id="0f525-193">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="0f525-194">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="0f525-194">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="0f525-195">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="0f525-195">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="0f525-196">GP 唯一名称：UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="0f525-196">GP unique name: UpdateDefault</span></span>
- <span data-ttu-id="0f525-197">GP 名称：更新策略替代默认值</span><span class="sxs-lookup"><span data-stu-id="0f525-197">GP name: Update policy override default</span></span>
- <span data-ttu-id="0f525-198">GP 路径：Administrative Templates/Microsoft Edge Update/Applications</span><span class="sxs-lookup"><span data-stu-id="0f525-198">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="0f525-199">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="0f525-199">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="0f525-200">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="0f525-200">Windows Registry Settings</span></span>
- <span data-ttu-id="0f525-201">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="0f525-201">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="0f525-202">值名称：UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="0f525-202">Value Name: UpdateDefault</span></span>
- <span data-ttu-id="0f525-203">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="0f525-203">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="0f525-204">示例值：</span><span class="sxs-lookup"><span data-stu-id="0f525-204">Example value:</span></span>
```
0x00000003
```
[<span data-ttu-id="0f525-205">返回页首</span><span class="sxs-lookup"><span data-stu-id="0f525-205">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="install"></a><span data-ttu-id="0f525-206">安装</span><span class="sxs-lookup"><span data-stu-id="0f525-206">Install</span></span>
#### <a name="allow-installation"></a><span data-ttu-id="0f525-207">允许安装</span><span class="sxs-lookup"><span data-stu-id="0f525-207">Allow installation</span></span>
><span data-ttu-id="0f525-208">Microsoft Edge 更新 1.2.145.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="0f525-208">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="0f525-209">描述</span><span class="sxs-lookup"><span data-stu-id="0f525-209">Description</span></span>
<span data-ttu-id="0f525-210">指定是否可以在域连接的设备上安装Microsoft Edge通道。</span><span class="sxs-lookup"><span data-stu-id="0f525-210">Specifies whether a Microsoft Edge channel can be installed on domain-joined devices.</span></span>

  <span data-ttu-id="0f525-211">如果为渠道启用此策略，则不会阻止 Microsoft Edge 的安装。</span><span class="sxs-lookup"><span data-stu-id="0f525-211">If you enable this policy for a channel, Microsoft Edge will not be blocked from installation.</span></span>

  <span data-ttu-id="0f525-212">如果为渠道启用此策略，则会阻止 Microsoft Edge 的安装。</span><span class="sxs-lookup"><span data-stu-id="0f525-212">If you disable this policy for a channel, Microsoft Edge will be blocked from installation.</span></span>

  <span data-ttu-id="0f525-213">如果没有为渠道配置此策略，则“[允许安装默认项](#installdefault)”策略配置将决定用户是否可以安装Microsoft Edge的该渠道。</span><span class="sxs-lookup"><span data-stu-id="0f525-213">If you don't configure this policy for a channel, the '[Allow installation default](#installdefault)' policy configuration determines whether users can install that channel of Microsoft Edge.</span></span>

  <span data-ttu-id="0f525-214">此策略仅在加入Microsoft® Active Directory®域的Windows实例上可用。</span><span class="sxs-lookup"><span data-stu-id="0f525-214">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="0f525-215">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="0f525-215">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="0f525-216">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="0f525-216">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="0f525-217">GP 唯一名称：安装</span><span class="sxs-lookup"><span data-stu-id="0f525-217">GP unique name: Install</span></span>
- <span data-ttu-id="0f525-218">GP 名称：允许安装</span><span class="sxs-lookup"><span data-stu-id="0f525-218">GP name: Allow installation</span></span>
- <span data-ttu-id="0f525-219">GP 路径：</span><span class="sxs-lookup"><span data-stu-id="0f525-219">GP path:</span></span> 
  - <span data-ttu-id="0f525-220">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0f525-220">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="0f525-221">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="0f525-221">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="0f525-222">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="0f525-222">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="0f525-223">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="0f525-223">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="0f525-224">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="0f525-224">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="0f525-225">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="0f525-225">Windows Registry Settings</span></span>
- <span data-ttu-id="0f525-226">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="0f525-226">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="0f525-227">值名称：</span><span class="sxs-lookup"><span data-stu-id="0f525-227">Value Name:</span></span> 
  - <span data-ttu-id="0f525-228">（稳定）：安装 {56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="0f525-228">(Stable): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="0f525-229">(Beta)：安装 {2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="0f525-229">(Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="0f525-230">(Canary)：安装 {65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="0f525-230">(Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="0f525-231">(Dev)：安装 {0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="0f525-231">(Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="0f525-232">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="0f525-232">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="0f525-233">示例值：</span><span class="sxs-lookup"><span data-stu-id="0f525-233">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="0f525-234">返回页首</span><span class="sxs-lookup"><span data-stu-id="0f525-234">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="update"></a><span data-ttu-id="0f525-235">更新</span><span class="sxs-lookup"><span data-stu-id="0f525-235">Update</span></span>
#### <a name="update-policy-override"></a><span data-ttu-id="0f525-236">更新策略替代</span><span class="sxs-lookup"><span data-stu-id="0f525-236">Update policy override</span></span>
><span data-ttu-id="0f525-237">Microsoft Edge 更新 1.2.145.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="0f525-237">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="0f525-238">描述</span><span class="sxs-lookup"><span data-stu-id="0f525-238">Description</span></span>
<span data-ttu-id="0f525-239">指定 Microsoft Edge 更新如何处理 Microsoft Edge 中的可用更新。</span><span class="sxs-lookup"><span data-stu-id="0f525-239">Specifies how Microsoft Edge Update handles available updates from Microsoft Edge.</span></span>

<span data-ttu-id="0f525-240">如果你启用此策略，Microsoft Edge 更新将根据你配置以下选项的方式处理 Microsoft Edge 更新：</span><span class="sxs-lookup"><span data-stu-id="0f525-240">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
  - <span data-ttu-id="0f525-241">始终允许更新：通过定期更新检查或通过手动更新检查，在发现更新时始终应用更新。</span><span class="sxs-lookup"><span data-stu-id="0f525-241">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
  - <span data-ttu-id="0f525-242">仅限自动无提示更新：仅在定期更新检查找到更新后才应用更新。</span><span class="sxs-lookup"><span data-stu-id="0f525-242">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
  - <span data-ttu-id="0f525-243">仅限手动更新：仅当用户运行手动更新检查时才应用更新。</span><span class="sxs-lookup"><span data-stu-id="0f525-243">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span> <span data-ttu-id="0f525-244">（并非所有应用都为此选项提供接口。）</span><span class="sxs-lookup"><span data-stu-id="0f525-244">(Not all apps provide an interface for this option.)</span></span>
  - <span data-ttu-id="0f525-245">已禁用更新：从不应用更新。</span><span class="sxs-lookup"><span data-stu-id="0f525-245">Updates disabled: Updates are never applied.</span></span>

<span data-ttu-id="0f525-246">如果你选择手动更新，请确保使用应用的手动更新机制（如果有）定期检查更新。</span><span class="sxs-lookup"><span data-stu-id="0f525-246">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="0f525-247">如果你禁用更新，请定期检查更新，然后将它们分发给用户。</span><span class="sxs-lookup"><span data-stu-id="0f525-247">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

<span data-ttu-id="0f525-248">如果你未启用和配置此策略，Microsoft Edge 更新将处理“[更新策略替代默认值](#updatedefault)”策略指定的可用更新。</span><span class="sxs-lookup"><span data-stu-id="0f525-248">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override default](#updatedefault)' policy.</span></span>

<span data-ttu-id="0f525-249">有关详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2136406](https://go.microsoft.com/fwlink/?linkid=2136406)。</span><span class="sxs-lookup"><span data-stu-id="0f525-249">See [https://go.microsoft.com/fwlink/?linkid=2136406](https://go.microsoft.com/fwlink/?linkid=2136406) for more information.</span></span>

<span data-ttu-id="0f525-250">此策略仅在加入Microsoft® Active Directory®域的Windows实例上可用。</span><span class="sxs-lookup"><span data-stu-id="0f525-250">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="0f525-251">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="0f525-251">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="0f525-252">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="0f525-252">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="0f525-253">GP 唯一名称：更新</span><span class="sxs-lookup"><span data-stu-id="0f525-253">GP unique name: Update</span></span>
- <span data-ttu-id="0f525-254">GP 名称：更新策略替代</span><span class="sxs-lookup"><span data-stu-id="0f525-254">GP name: Update policy override</span></span>
- <span data-ttu-id="0f525-255">GP 路径：</span><span class="sxs-lookup"><span data-stu-id="0f525-255">GP path:</span></span> 
  - <span data-ttu-id="0f525-256">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0f525-256">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="0f525-257">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="0f525-257">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="0f525-258">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="0f525-258">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="0f525-259">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="0f525-259">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="0f525-260">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="0f525-260">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="0f525-261">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="0f525-261">Windows Registry Settings</span></span>
- <span data-ttu-id="0f525-262">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="0f525-262">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="0f525-263">值名称：</span><span class="sxs-lookup"><span data-stu-id="0f525-263">Value Name:</span></span> 
  - <span data-ttu-id="0f525-264">（稳定）：更新 {56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="0f525-264">(Stable): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="0f525-265">(Beta)：更新 {2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="0f525-265">(Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="0f525-266">(Canary)：更新 {65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="0f525-266">(Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="0f525-267">(Dev)：更新 {0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="0f525-267">(Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="0f525-268">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="0f525-268">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="0f525-269">示例值：</span><span class="sxs-lookup"><span data-stu-id="0f525-269">Example value:</span></span>
```
always allow updates 0x00000001
Automatic silent updates only 0x00000003
manual updates only 0x00000002
updates disabled 0x00000000
```
[<span data-ttu-id="0f525-270">返回页首</span><span class="sxs-lookup"><span data-stu-id="0f525-270">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="allowsxs"></a><span data-ttu-id="0f525-271">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="0f525-271">Allowsxs</span></span>
#### <a name="allow-microsoft-edge-side-by-side-browser-experience"></a><span data-ttu-id="0f525-272">允许 Microsoft Edge 并行浏览器体验</span><span class="sxs-lookup"><span data-stu-id="0f525-272">Allow Microsoft Edge Side by Side browser experience</span></span>
><span data-ttu-id="0f525-273">Microsoft Edge 更新 1.2.145.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="0f525-273">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="0f525-274">说明</span><span class="sxs-lookup"><span data-stu-id="0f525-274">Description</span></span>
<span data-ttu-id="0f525-275">此策略允许用户并行运行 Microsoft Edge (Edge HTML) 和 Microsoft Edge（基于 Chromium）。</span><span class="sxs-lookup"><span data-stu-id="0f525-275">This policy lets a user run Microsoft Edge (Edge HTML) and Microsoft Edge (Chromium-based) side-by-side.</span></span>

<span data-ttu-id="0f525-276">如果将此策略设置为“未配置”，则在安装 Microsoft Edge（基于 Chromium）稳定渠道和 2019 年 11 月安全更新后，Microsoft Edge（基于 Chromium）将替换 Microsoft Edge (Edge HTML)。</span><span class="sxs-lookup"><span data-stu-id="0f525-276">If this policy is set to “Not configured”, Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="0f525-277">此行为与“已禁用”设置相同。</span><span class="sxs-lookup"><span data-stu-id="0f525-277">This is the same behavior as the “Disabled” setting.</span></span>

<span data-ttu-id="0f525-278">在安装 Microsoft Edge（基于 Chromium）稳定渠道和 2019 年 11 月安全更新后，“已禁用”设置会阻止并行体验，并且 Microsoft Edge（基于 Chromium）将替换 Microsoft Edge (Edge HTML)。</span><span class="sxs-lookup"><span data-stu-id="0f525-278">The “Disabled” setting blocks a side-by-side experience and Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="0f525-279">此行为与“未配置”设置相同。</span><span class="sxs-lookup"><span data-stu-id="0f525-279">This is the same behavior as the “Not Configured” setting.</span></span>

<span data-ttu-id="0f525-280">如果“已启用”此策略，则在安装 Microsoft Edge（基于 Chromium）后，Microsoft Edge（基于 Chromium）和 Microsoft Edge (Edge HTML) 可并行运行。</span><span class="sxs-lookup"><span data-stu-id="0f525-280">When this policy is “Enabled”, Microsoft Edge (Chromium-based) and Microsoft Edge (Edge HTML) can run side-by-side after Microsoft Edge (Chromium-based) is installed.</span></span>

<span data-ttu-id="0f525-281">若要使此组策略生效，必须先配置它，然后再通过 Windows 更新自动安装 Microsoft Edge（基于 Chromium）。</span><span class="sxs-lookup"><span data-stu-id="0f525-281">For this group policy to take affect, it must be configured before the automatic install of Microsoft Edge (Chromium-based) by Windows Update.</span></span> <span data-ttu-id="0f525-282">注意：通过使用 Microsoft Edge（基于 Chromium）阻止程序工具包，用户可以阻止自动更新 Microsoft Edge（基于 Chromium）。</span><span class="sxs-lookup"><span data-stu-id="0f525-282">Note: A user can block the automatic update of Microsoft Edge (Chromium-based) by using the Microsoft Edge (Chromium-based) Blocker Toolkit.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="0f525-283">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="0f525-283">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="0f525-284">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="0f525-284">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="0f525-285">GP 唯一名称：Allowsxs</span><span class="sxs-lookup"><span data-stu-id="0f525-285">GP unique name: Allowsxs</span></span>
- <span data-ttu-id="0f525-286">GP 名称：允许 Microsoft Edge 并行浏览器体验</span><span class="sxs-lookup"><span data-stu-id="0f525-286">GP name: Allow Microsoft Edge Side by Side browser experience</span></span>
- <span data-ttu-id="0f525-287">GP 路径：Administrative Templates/Microsoft Edge Update/Applications</span><span class="sxs-lookup"><span data-stu-id="0f525-287">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="0f525-288">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="0f525-288">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="0f525-289">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="0f525-289">Windows Registry Settings</span></span>
- <span data-ttu-id="0f525-290">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="0f525-290">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="0f525-291">值名称：Allowsxs</span><span class="sxs-lookup"><span data-stu-id="0f525-291">Value Name: Allowsxs</span></span>
- <span data-ttu-id="0f525-292">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="0f525-292">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="0f525-293">示例值：</span><span class="sxs-lookup"><span data-stu-id="0f525-293">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="0f525-294">返回页首</span><span class="sxs-lookup"><span data-stu-id="0f525-294">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="createdesktopshortcutdefault"></a><span data-ttu-id="0f525-295">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="0f525-295">CreateDesktopShortcutDefault</span></span>
#### <a name="prevent-desktop-shortcut-creation-upon-install-default"></a><span data-ttu-id="0f525-296">安装默认项时阻止创建快捷方式</span><span class="sxs-lookup"><span data-stu-id="0f525-296">Prevent Desktop Shortcut creation upon install default</span></span>
><span data-ttu-id="0f525-297">Microsoft Edge 更新 1.3.128.0 和更高版本</span><span class="sxs-lookup"><span data-stu-id="0f525-297">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <a name="description"></a><span data-ttu-id="0f525-298">描述</span><span class="sxs-lookup"><span data-stu-id="0f525-298">Description</span></span>
<span data-ttu-id="0f525-299">安装 Microsoft Edge 时，可针对创建桌面快捷方式指定所有渠道的默认行为。</span><span class="sxs-lookup"><span data-stu-id="0f525-299">Lets you specify the default behavior for all channels for creating a desktop shortcut when Microsoft Edge is installed.</span></span>

  <span data-ttu-id="0f525-300">如果启用此策略，在安装 Microsoft Edge 时会创建桌面快捷方式。</span><span class="sxs-lookup"><span data-stu-id="0f525-300">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="0f525-301">如果禁用此策略，在安装 Microsoft Edge 时不创建桌面快捷方式。</span><span class="sxs-lookup"><span data-stu-id="0f525-301">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="0f525-302">如果未配置此策略，会在安装过程中创建 Microsoft Edge 桌面快捷方式。</span><span class="sxs-lookup"><span data-stu-id="0f525-302">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="0f525-303">如果已安装 Microsoft Edge，此策略将不起作用。</span><span class="sxs-lookup"><span data-stu-id="0f525-303">If Microsoft Edge is already installed, this policy will have no effect.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="0f525-304">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="0f525-304">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="0f525-305">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="0f525-305">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="0f525-306">GP 唯一名称：CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="0f525-306">GP unique name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="0f525-307">GP 名称：安装默认项时阻止创建快捷方式</span><span class="sxs-lookup"><span data-stu-id="0f525-307">GP name: Prevent Desktop Shortcut creation upon install default</span></span>
- <span data-ttu-id="0f525-308">GP 路径：Administrative Templates/Microsoft Edge Update/Applications</span><span class="sxs-lookup"><span data-stu-id="0f525-308">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="0f525-309">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="0f525-309">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="0f525-310">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="0f525-310">Windows Registry Settings</span></span>
- <span data-ttu-id="0f525-311">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="0f525-311">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="0f525-312">值名称：CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="0f525-312">Value Name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="0f525-313">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="0f525-313">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="0f525-314">示例值：</span><span class="sxs-lookup"><span data-stu-id="0f525-314">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="0f525-315">返回页首</span><span class="sxs-lookup"><span data-stu-id="0f525-315">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="createdesktopshortcut"></a><span data-ttu-id="0f525-316">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="0f525-316">CreateDesktopShortcut</span></span>
#### <a name="prevent-desktop-shortcut-creation-upon-install"></a><span data-ttu-id="0f525-317">安装时阻止创建快捷方式</span><span class="sxs-lookup"><span data-stu-id="0f525-317">Prevent Desktop Shortcut creation upon install</span></span>
><span data-ttu-id="0f525-318">Microsoft Edge 更新 1.3.128.0 和更高版本</span><span class="sxs-lookup"><span data-stu-id="0f525-318">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <a name="description"></a><span data-ttu-id="0f525-319">描述</span><span class="sxs-lookup"><span data-stu-id="0f525-319">Description</span></span>
<span data-ttu-id="0f525-320">如果启用此策略，在安装 Microsoft Edge 时会创建桌面快捷方式。</span><span class="sxs-lookup"><span data-stu-id="0f525-320">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="0f525-321">如果禁用此策略，在安装 Microsoft Edge 时不创建桌面快捷方式。</span><span class="sxs-lookup"><span data-stu-id="0f525-321">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="0f525-322">如果未配置此策略，会在安装过程中创建 Microsoft Edge 桌面快捷方式。</span><span class="sxs-lookup"><span data-stu-id="0f525-322">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="0f525-323">如果已安装 Microsoft Edge，此策略将不起作用。</span><span class="sxs-lookup"><span data-stu-id="0f525-323">If Microsoft Edge is already installed, this policy will have no effect.</span></span>

  <span data-ttu-id="0f525-324">如果未为频道配置此策略，则“[Prevent Desktop Shortcut creation upon install default](#createdesktopshortcutdefault)”策略配置将确定在安装 Microsoft Edge 时创建快捷方式。</span><span class="sxs-lookup"><span data-stu-id="0f525-324">If you don't configure this policy for a channel, the '[Prevent Desktop Shortcut creation upon install default](#createdesktopshortcutdefault)' policy configuration determines shortcut creation when Microsoft Edge is installed.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="0f525-325">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="0f525-325">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="0f525-326">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="0f525-326">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="0f525-327">GP 唯一名称：CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="0f525-327">GP unique name: CreateDesktopShortcut</span></span>
- <span data-ttu-id="0f525-328">GP 名称：安装时阻止创建快捷方式</span><span class="sxs-lookup"><span data-stu-id="0f525-328">GP name: Prevent Desktop Shortcut creation upon install</span></span>
- <span data-ttu-id="0f525-329">GP 路径：</span><span class="sxs-lookup"><span data-stu-id="0f525-329">GP path:</span></span> 
  - <span data-ttu-id="0f525-330">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0f525-330">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="0f525-331">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="0f525-331">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="0f525-332">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="0f525-332">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="0f525-333">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="0f525-333">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="0f525-334">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="0f525-334">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="0f525-335">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="0f525-335">Windows Registry Settings</span></span>
- <span data-ttu-id="0f525-336">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="0f525-336">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="0f525-337">值名称：</span><span class="sxs-lookup"><span data-stu-id="0f525-337">Value Name:</span></span> 
  - <span data-ttu-id="0f525-338">（稳定）：CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="0f525-338">(Stable): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="0f525-339">(Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="0f525-339">(Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="0f525-340">(Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="0f525-340">(Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="0f525-341">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="0f525-341">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="0f525-342">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="0f525-342">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="0f525-343">示例值：</span><span class="sxs-lookup"><span data-stu-id="0f525-343">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="0f525-344">返回页首</span><span class="sxs-lookup"><span data-stu-id="0f525-344">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="rollbacktotargetversion"></a><span data-ttu-id="0f525-345">RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="0f525-345">RollbackToTargetVersion</span></span>
#### <a name="rollback-to-target-version"></a><span data-ttu-id="0f525-346">回退到目标版本</span><span class="sxs-lookup"><span data-stu-id="0f525-346">Rollback to Target version</span></span>
><span data-ttu-id="0f525-347">Microsoft Edge 更新 1.3.133.3 和更高版本</span><span class="sxs-lookup"><span data-stu-id="0f525-347">Microsoft Edge Update 1.3.133.3 and later</span></span>

#### <a name="description"></a><span data-ttu-id="0f525-348">描述</span><span class="sxs-lookup"><span data-stu-id="0f525-348">Description</span></span>
<span data-ttu-id="0f525-349">指定 Microsoft Edge 更新应将 Microsoft Edge 的安装回退到 "[目标版本覆盖](#targetversionprefix)" 中指定的版本。</span><span class="sxs-lookup"><span data-stu-id="0f525-349">Specifies that Microsoft Edge Update should rollback installations of Microsoft Edge to the version indicated in '[Target version override](#targetversionprefix)'.</span></span>

<span data-ttu-id="0f525-350">除非"[目标版本替代](#targetversionprefix)" 设置为 "开"，并且将 "[更新策略替代](#update)" 设置为 "开启" 状态之一（始终允许更新、仅自动无提示更新，仅限手动更新），否则该策略无效。</span><span class="sxs-lookup"><span data-stu-id="0f525-350">This policy has no effect unless '[Target version override](#targetversionprefix)' is set and '[Update policy override](#update)' is set to one of the ON states (Always allow updates, Automatic silent updates only, Manual updates only).</span></span>

<span data-ttu-id="0f525-351">如果禁用该策略或不对其进行配置，则安装的版本高于由 "[目标版本替代](#targetversionprefix)" 所指定的版本则将保留原样。</span><span class="sxs-lookup"><span data-stu-id="0f525-351">If you disable this policy or don't configure it, installs that have a version higher than that specified by '[Target version override](#targetversionprefix)' will be left as-is.</span></span>

<span data-ttu-id="0f525-352">如果启用此策略，则当前版本高于由 "[目标版本替代](#targetversionprefix)" 指定的安装将降级到目标版本。</span><span class="sxs-lookup"><span data-stu-id="0f525-352">If you enable this policy, installs that have a current version higher than specified by the '[Target version override](#targetversionprefix)' will be downgraded to the target version.</span></span>

<span data-ttu-id="0f525-353">我们建议用户安装最新版本的 Microsoft Edge 浏览器，以确保受到最新安全更新的保护。</span><span class="sxs-lookup"><span data-stu-id="0f525-353">We recommend that users install the latest version of the Microsoft Edge browser to ensure protection by the latest security updates.</span></span> <span data-ttu-id="0f525-354">回退到较早版本存在遇到已知安全问题的风险。</span><span class="sxs-lookup"><span data-stu-id="0f525-354">Rollback to an earlier version risks exposure to known security issues.</span></span> <span data-ttu-id="0f525-355">该策略旨在作为一种临时修复措施，以解决Microsoft Edge浏览器更新中所面临的问题。</span><span class="sxs-lookup"><span data-stu-id="0f525-355">This policy is meant to be used as a temporary fix to address issues in a Microsoft Edge browser update.</span></span>

<span data-ttu-id="0f525-356">在暂时回退浏览器版本之前，建议你为组织中的所有用户启用同步（[https://go.microsoft.com/fwlink/?linkid=2133032](https://go.microsoft.com/fwlink/?linkid=2133032)）。</span><span class="sxs-lookup"><span data-stu-id="0f525-356">Before temporarily rolling back your browser version, we recommend that you turn on Sync ([https://go.microsoft.com/fwlink/?linkid=2133032](https://go.microsoft.com/fwlink/?linkid=2133032)) for all users in your organization.</span></span> <span data-ttu-id="0f525-357">如果未启用同步，则有可能造成永久性浏览数据丢失。</span><span class="sxs-lookup"><span data-stu-id="0f525-357">If you don't turn on Sync, there is a risk of permanent browsing data loss.</span></span> <span data-ttu-id="0f525-358">使用本政策，风险自担。</span><span class="sxs-lookup"><span data-stu-id="0f525-358">Use this policy at your own risk.</span></span>

<span data-ttu-id="0f525-359">注意：可在此处查看所有可供回退的版本 [https://aka.ms/EdgeEnterprise](https://aka.ms/EdgeEnterprise)。</span><span class="sxs-lookup"><span data-stu-id="0f525-359">Note: All versions available for rollback can be viewed here [https://aka.ms/EdgeEnterprise](https://aka.ms/EdgeEnterprise).</span></span>

<span data-ttu-id="0f525-360">此政策适用于Microsoft Edge 86或更高版本。</span><span class="sxs-lookup"><span data-stu-id="0f525-360">This policy applies to Microsoft Edge version 86 or later.</span></span>

<span data-ttu-id="0f525-361">有关详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2133918](https://go.microsoft.com/fwlink/?linkid=2133918)。</span><span class="sxs-lookup"><span data-stu-id="0f525-361">See [https://go.microsoft.com/fwlink/?linkid=2133918](https://go.microsoft.com/fwlink/?linkid=2133918) for more information.</span></span>

<span data-ttu-id="0f525-362">此策略仅在加入Microsoft® Active Directory®域的Windows实例上可用。</span><span class="sxs-lookup"><span data-stu-id="0f525-362">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="0f525-363">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="0f525-363">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="0f525-364">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="0f525-364">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="0f525-365">GP 唯一名称：RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="0f525-365">GP unique name: RollbackToTargetVersion</span></span>
- <span data-ttu-id="0f525-366">GP 名称：回退到目标版本</span><span class="sxs-lookup"><span data-stu-id="0f525-366">GP name: Rollback to Target version</span></span>
- <span data-ttu-id="0f525-367">GP 路径：</span><span class="sxs-lookup"><span data-stu-id="0f525-367">GP path:</span></span> 
  - <span data-ttu-id="0f525-368">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0f525-368">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="0f525-369">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="0f525-369">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="0f525-370">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="0f525-370">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="0f525-371">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="0f525-371">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="0f525-372">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="0f525-372">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="0f525-373">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="0f525-373">Windows Registry Settings</span></span>
- <span data-ttu-id="0f525-374">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="0f525-374">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="0f525-375">值名称：</span><span class="sxs-lookup"><span data-stu-id="0f525-375">Value Name:</span></span> 
  - <span data-ttu-id="0f525-376">（稳定版）：RollbackToTargetVersion{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="0f525-376">(Stable): RollbackToTargetVersion{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="0f525-377">（Beta版）：RollbackToTargetVersion{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="0f525-377">(Beta): RollbackToTargetVersion{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="0f525-378">（Canary版）：RollbackToTargetVersion{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="0f525-378">(Canary): RollbackToTargetVersion{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="0f525-379">（开发者版）：RollbackToTargetVersion{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="0f525-379">(Dev): RollbackToTargetVersion{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="0f525-380">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="0f525-380">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="0f525-381">示例值：</span><span class="sxs-lookup"><span data-stu-id="0f525-381">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="0f525-382">返回页首</span><span class="sxs-lookup"><span data-stu-id="0f525-382">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="targetversionprefix"></a><span data-ttu-id="0f525-383">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="0f525-383">TargetVersionPrefix</span></span>
#### <a name="target-version-override"></a><span data-ttu-id="0f525-384">目标版本覆盖</span><span class="sxs-lookup"><span data-stu-id="0f525-384">Target version override</span></span>
><span data-ttu-id="0f525-385">Microsoft Edge 更新 1.3.119.43 和更高版本</span><span class="sxs-lookup"><span data-stu-id="0f525-385">Microsoft Edge Update 1.3.119.43 and later</span></span>

#### <a name="description"></a><span data-ttu-id="0f525-386">描述</span><span class="sxs-lookup"><span data-stu-id="0f525-386">Description</span></span>
<span data-ttu-id="0f525-387">启用此策略并启用自动更新后，Microsoft Edge 将更新为该策略值指定的版本。</span><span class="sxs-lookup"><span data-stu-id="0f525-387">When this policy is enabled, and auto-update is enabled, Microsoft Edge will be updated to the version specified by this policy value.</span></span>

<span data-ttu-id="0f525-388">策略值必须是特定的 Microsoft Edge 版本，例如 83.0.499.12。</span><span class="sxs-lookup"><span data-stu-id="0f525-388">The policy value must be a specific Microsoft Edge version, e.g. 83.0.499.12.</span></span>

<span data-ttu-id="0f525-389">如果设备的 Microsoft Edge 版本高于指定的值，Microsoft Edge 将保留较新版本，不会降级到指定版本。</span><span class="sxs-lookup"><span data-stu-id="0f525-389">If a device has newer version of Microsoft Edge than the value specified, Microsoft Edge will remain on the newer version and not downgrade to the specified version.</span></span>

<span data-ttu-id="0f525-390">如果指定版本不存在，或格式不正确，Microsoft Edge 将保留当前版本，不会自动更新为未来版本。</span><span class="sxs-lookup"><span data-stu-id="0f525-390">If the specified version does not exist, or is improperly formatted, then Microsoft Edge will remain on its current version and not update to future versions automatically.</span></span>

<span data-ttu-id="0f525-391">有关详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2136707](https://go.microsoft.com/fwlink/?linkid=2136707)。</span><span class="sxs-lookup"><span data-stu-id="0f525-391">See [https://go.microsoft.com/fwlink/?linkid=2136707](https://go.microsoft.com/fwlink/?linkid=2136707) for more information.</span></span>

<span data-ttu-id="0f525-392">此策略仅在加入Microsoft® Active Directory®域的Windows实例上可用。</span><span class="sxs-lookup"><span data-stu-id="0f525-392">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="0f525-393">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="0f525-393">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="0f525-394">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="0f525-394">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="0f525-395">GP 唯一名称：TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="0f525-395">GP unique name: TargetVersionPrefix</span></span>
- <span data-ttu-id="0f525-396">GP 名称：目标版本覆盖</span><span class="sxs-lookup"><span data-stu-id="0f525-396">GP name: Target version override</span></span>
- <span data-ttu-id="0f525-397">GP 路径：</span><span class="sxs-lookup"><span data-stu-id="0f525-397">GP path:</span></span> 
  - <span data-ttu-id="0f525-398">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0f525-398">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="0f525-399">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="0f525-399">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="0f525-400">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="0f525-400">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="0f525-401">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="0f525-401">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="0f525-402">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="0f525-402">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="0f525-403">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="0f525-403">Windows Registry Settings</span></span>
- <span data-ttu-id="0f525-404">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="0f525-404">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="0f525-405">值名称：</span><span class="sxs-lookup"><span data-stu-id="0f525-405">Value Name:</span></span> 
  - <span data-ttu-id="0f525-406">（稳定版）：TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="0f525-406">(Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="0f525-407">（Beta 版）： TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="0f525-407">(Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="0f525-408">（金丝雀版）： TargetVersionPrefix {65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="0f525-408">(Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="0f525-409">（开发者版本）：更新 {0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="0f525-409">(Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="0f525-410">值类型：REG_SZ</span><span class="sxs-lookup"><span data-stu-id="0f525-410">Value Type: REG_SZ</span></span>
##### <a name="example-value"></a><span data-ttu-id="0f525-411">示例值：</span><span class="sxs-lookup"><span data-stu-id="0f525-411">Example value:</span></span>
```
83.0.499.12
```
[<span data-ttu-id="0f525-412">返回页首</span><span class="sxs-lookup"><span data-stu-id="0f525-412">Back to top</span></span>](#microsoft-edge---update-policies)


## <a name="preferences-policies"></a><span data-ttu-id="0f525-413">首选项策略</span><span class="sxs-lookup"><span data-stu-id="0f525-413">Preferences policies</span></span>

[<span data-ttu-id="0f525-414">返回页首</span><span class="sxs-lookup"><span data-stu-id="0f525-414">Back to top</span></span>](#microsoft-edge---update-policies)
### <a name="autoupdatecheckperiodminutes"></a><span data-ttu-id="0f525-415">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="0f525-415">AutoUpdateCheckPeriodMinutes</span></span>
#### <a name="auto-update-check-period-override"></a><span data-ttu-id="0f525-416">自动更新检查期间替代</span><span class="sxs-lookup"><span data-stu-id="0f525-416">Auto-update check period override</span></span>
><span data-ttu-id="0f525-417">Microsoft Edge 更新 1.2.145.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="0f525-417">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="0f525-418">描述</span><span class="sxs-lookup"><span data-stu-id="0f525-418">Description</span></span>
<span data-ttu-id="0f525-419">如果启用了此策略，你可以为各次自动更新检查间隔的最小分钟数设置一个值。</span><span class="sxs-lookup"><span data-stu-id="0f525-419">If enabled, this policy lets you set a value for the minimum number of minutes between automatic update checks.</span></span> <span data-ttu-id="0f525-420">否则，默认情况下，自动更新将每 10 小时检查一次更新。</span><span class="sxs-lookup"><span data-stu-id="0f525-420">Otherwise, by default, auto-update checks for updates every 10 hours.</span></span>

  <span data-ttu-id="0f525-421">如果你想要禁用所有自动更新检查，请将该值设置为 0（不推荐）。</span><span class="sxs-lookup"><span data-stu-id="0f525-421">If you want to disable all auto-update checks, set the value to 0 (not recommended).</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="0f525-422">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="0f525-422">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="0f525-423">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="0f525-423">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="0f525-424">GP 唯一名称：AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="0f525-424">GP unique name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="0f525-425">GP 名称：自动更新检查期间替代</span><span class="sxs-lookup"><span data-stu-id="0f525-425">GP name: Auto-update check period override</span></span>
- <span data-ttu-id="0f525-426">GP 路径：Administrative Templates/Microsoft Edge Update/Preferences</span><span class="sxs-lookup"><span data-stu-id="0f525-426">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="0f525-427">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="0f525-427">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="0f525-428">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="0f525-428">Windows Registry Settings</span></span>
- <span data-ttu-id="0f525-429">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="0f525-429">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="0f525-430">值名称：AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="0f525-430">Value Name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="0f525-431">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="0f525-431">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="0f525-432">示例值：</span><span class="sxs-lookup"><span data-stu-id="0f525-432">Example value:</span></span>
```
0x00000578
```
[<span data-ttu-id="0f525-433">返回页首</span><span class="sxs-lookup"><span data-stu-id="0f525-433">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="updatessuppressed"></a><span data-ttu-id="0f525-434">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="0f525-434">UpdatesSuppressed</span></span>
#### <a name="time-period-in-each-day-to-suppress-auto-update-check"></a><span data-ttu-id="0f525-435">每天中取消自动更新检查的时间段</span><span class="sxs-lookup"><span data-stu-id="0f525-435">Time period in each day to suppress auto-update check</span></span>
><span data-ttu-id="0f525-436">Microsoft Edge 更新 1.3.33.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="0f525-436">Microsoft Edge Update 1.3.33.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="0f525-437">描述</span><span class="sxs-lookup"><span data-stu-id="0f525-437">Description</span></span>
<span data-ttu-id="0f525-438">如果你启用此策略，则每天都会从 Hour:Minute 开始持续一段时间（以分钟为单位）禁止更新检查。</span><span class="sxs-lookup"><span data-stu-id="0f525-438">If you enable this policy, update checks are suppressed each day starting at Hour:Minute for a period of Duration (in minutes).</span></span> <span data-ttu-id="0f525-439">持续时间不受夏令时影响。</span><span class="sxs-lookup"><span data-stu-id="0f525-439">Duration isn't affected by daylight saving time.</span></span> <span data-ttu-id="0f525-440">例如，如果开始时间是 22:00，持续时间为 480 分钟，则无论夏令时是在此期间开始还是结束，更新都将正好禁止 8 小时。</span><span class="sxs-lookup"><span data-stu-id="0f525-440">For example, if the start time is 22:00 and the duration is 480 minutes, updates will be suppressed for exactly 8 hours, regardless of whether daylight saving time starts or ends during this period.</span></span>

  <span data-ttu-id="0f525-441">如果你禁用或未配置此策略，则不会在任何特定期间取消更新检查。</span><span class="sxs-lookup"><span data-stu-id="0f525-441">If you disable or don't configure this policy, update checks aren't suppressed during any specific period.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="0f525-442">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="0f525-442">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="0f525-443">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="0f525-443">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="0f525-444">GP 唯一名称：UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="0f525-444">GP unique name: UpdatesSuppressed</span></span>
- <span data-ttu-id="0f525-445">GP 名称：每天中取消自动更新检查的时间段</span><span class="sxs-lookup"><span data-stu-id="0f525-445">GP name: Time period in each day to suppress auto-update check</span></span>
  - <span data-ttu-id="0f525-446">选项 { Hour, Minute, Duration }</span><span class="sxs-lookup"><span data-stu-id="0f525-446">Options { Hour, Minute, Duration }</span></span>
- <span data-ttu-id="0f525-447">GP 路径：Administrative Templates/Microsoft Edge Update/Preferences</span><span class="sxs-lookup"><span data-stu-id="0f525-447">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="0f525-448">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="0f525-448">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="0f525-449">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="0f525-449">Windows Registry Settings</span></span>
- <span data-ttu-id="0f525-450">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="0f525-450">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="0f525-451">值名称：</span><span class="sxs-lookup"><span data-stu-id="0f525-451">Value Name:</span></span> 
  - <span data-ttu-id="0f525-452">UpdatesSuppressedDurationMin</span><span class="sxs-lookup"><span data-stu-id="0f525-452">UpdatesSuppressedDurationMin</span></span>
  - <span data-ttu-id="0f525-453">UpdatesSuppressedStartHour</span><span class="sxs-lookup"><span data-stu-id="0f525-453">UpdatesSuppressedStartHour</span></span>
  - <span data-ttu-id="0f525-454">UpdatesSuppressedStartMin</span><span class="sxs-lookup"><span data-stu-id="0f525-454">UpdatesSuppressedStartMin</span></span>
- <span data-ttu-id="0f525-455">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="0f525-455">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="0f525-456">示例值：</span><span class="sxs-lookup"><span data-stu-id="0f525-456">Example value:</span></span>
```
duration   : 0x0000003c
start hour : 0x00000001
start min  : 0x00000002
```
[<span data-ttu-id="0f525-457">返回页首</span><span class="sxs-lookup"><span data-stu-id="0f525-457">Back to top</span></span>](#microsoft-edge---update-policies)


## <a name="proxy-server-policies"></a><span data-ttu-id="0f525-458">代理服务器策略</span><span class="sxs-lookup"><span data-stu-id="0f525-458">Proxy Server policies</span></span>

[<span data-ttu-id="0f525-459">返回页首</span><span class="sxs-lookup"><span data-stu-id="0f525-459">Back to top</span></span>](#microsoft-edge---update-policies)
### <a name="proxymode"></a><span data-ttu-id="0f525-460">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="0f525-460">ProxyMode</span></span>
#### <a name="choose-how-to-specify-proxy-server-settings"></a><span data-ttu-id="0f525-461">选择指定代理服务器设置的方式</span><span class="sxs-lookup"><span data-stu-id="0f525-461">Choose how to specify proxy server settings</span></span>
><span data-ttu-id="0f525-462">Microsoft Edge 更新 1.3.21.81 和更高版本</span><span class="sxs-lookup"><span data-stu-id="0f525-462">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <a name="description"></a><span data-ttu-id="0f525-463">描述</span><span class="sxs-lookup"><span data-stu-id="0f525-463">Description</span></span>
<span data-ttu-id="0f525-464">允许你指定 Microsoft Edge 更新使用的代理服务器设置。</span><span class="sxs-lookup"><span data-stu-id="0f525-464">Allows you to specify the proxy server settings that are used by Microsoft Edge Update.</span></span>

  <span data-ttu-id="0f525-465">如果你启用此策略，则可以在以下代理服务器选项之间进行选择：</span><span class="sxs-lookup"><span data-stu-id="0f525-465">If you enable this policy, you can choose between the following proxy server options:</span></span>
   - <span data-ttu-id="0f525-466">如果你选择从不使用代理服务器并且始终直接连接，则所有其他选项都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="0f525-466">If you choose to never use a proxy server and always connect directly, all other options are ignored.</span></span>
   - <span data-ttu-id="0f525-467">如果你选择使用系统代理设置或自动检测代理服务器，则所有其他选项都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="0f525-467">If you choose to use system proxy settings or auto-detect the proxy server, all other options are ignored.</span></span>
   - <span data-ttu-id="0f525-468">如果你选择固定服务器代理模式，则可以在 “[代理服务器的地址或 URL](#proxyserver)” 策略中指定更多选项。</span><span class="sxs-lookup"><span data-stu-id="0f525-468">If you choose fixed server proxy mode, you can specify further options in '[Address or URL of proxy server](#proxyserver)' policy.</span></span>
   - <span data-ttu-id="0f525-469">如果你选择使用 .pac 代理脚本，则必须在 “[代理 .pac 文件的 URL](#proxypacurl)”策略中为脚本指定 URL。</span><span class="sxs-lookup"><span data-stu-id="0f525-469">If you choose to use a .pac proxy script, you must specify the URL for the script in '[URL to a proxy .pac file](#proxypacurl)' policy.</span></span>

  <span data-ttu-id="0f525-470">如果你启用此策略，则你所在组织中的用户无法在 Microsoft Edge 更新中更改代理设置。</span><span class="sxs-lookup"><span data-stu-id="0f525-470">If you enable this policy, users in your organization can't change the proxy settings in Microsoft Edge Update.</span></span>

  <span data-ttu-id="0f525-471">如果你禁用或未配置此策略，则不会配置任何代理服务器设置，但组织中的用户可以为 Microsoft Edge 更新选择自己的代理设置。</span><span class="sxs-lookup"><span data-stu-id="0f525-471">If you disable or don't configure this policy, no proxy server settings are configured, but users in your organization can choose their own proxy settings for Microsoft Edge Update.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="0f525-472">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="0f525-472">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="0f525-473">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="0f525-473">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="0f525-474">GP 唯一名称：ProxyMode</span><span class="sxs-lookup"><span data-stu-id="0f525-474">GP unique name: ProxyMode</span></span>
- <span data-ttu-id="0f525-475">GP 名称：选择指定代理服务器设置的方式</span><span class="sxs-lookup"><span data-stu-id="0f525-475">GP name: Choose how to specify proxy server settings</span></span>
- <span data-ttu-id="0f525-476">GP 路径：Administrative Templates/Microsoft Edge Update/Proxy Server</span><span class="sxs-lookup"><span data-stu-id="0f525-476">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="0f525-477">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="0f525-477">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="0f525-478">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="0f525-478">Windows Registry Settings</span></span>
- <span data-ttu-id="0f525-479">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="0f525-479">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="0f525-480">值名称：ProxyMode</span><span class="sxs-lookup"><span data-stu-id="0f525-480">Value Name: ProxyMode</span></span>
- <span data-ttu-id="0f525-481">值类型：REG_SZ</span><span class="sxs-lookup"><span data-stu-id="0f525-481">Value Type: REG_SZ</span></span>
##### <a name="example-value"></a><span data-ttu-id="0f525-482">示例值：</span><span class="sxs-lookup"><span data-stu-id="0f525-482">Example value:</span></span>
```
fixed_servers
```
[<span data-ttu-id="0f525-483">返回页首</span><span class="sxs-lookup"><span data-stu-id="0f525-483">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="proxypacurl"></a><span data-ttu-id="0f525-484">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="0f525-484">ProxyPacUrl</span></span>
#### <a name="url-to-a-proxy-pac-file"></a><span data-ttu-id="0f525-485">代理 .pac 文件的 URL</span><span class="sxs-lookup"><span data-stu-id="0f525-485">URL to a proxy .pac file</span></span>
><span data-ttu-id="0f525-486">Microsoft Edge 更新 1.3.21.81 和更高版本</span><span class="sxs-lookup"><span data-stu-id="0f525-486">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <a name="description"></a><span data-ttu-id="0f525-487">描述</span><span class="sxs-lookup"><span data-stu-id="0f525-487">Description</span></span>
<span data-ttu-id="0f525-488">允许你为代理自动配置 (PAC) 文件指定 URL。</span><span class="sxs-lookup"><span data-stu-id="0f525-488">Allows you to specify a URL for a proxy auto-config (PAC) file.</span></span>

  <span data-ttu-id="0f525-489">如果你启用此策略，则可以为 PAC 文件指定 URL，以自动执行 Microsoft Edge 更新为提取特定网站而选择合适代理服务器的方法。</span><span class="sxs-lookup"><span data-stu-id="0f525-489">If you enable this policy, you can specify a URL for a PAC file to automate how Microsoft Edge Update selects the appropriate proxy server for fetching a particular website.</span></span>

  <span data-ttu-id="0f525-490">仅当你已在“[选择如何指定代理服务器设置](#proxymode)”策略中指定了手动代理设置时，才会应用此策略。</span><span class="sxs-lookup"><span data-stu-id="0f525-490">This policy is applied only if you have specified manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="0f525-491">如果你已在“[选择如何指定代理服务器设置](#proxymode)”策略中选择了手动设置以外的其他代理设置，请不要配置此策略。</span><span class="sxs-lookup"><span data-stu-id="0f525-491">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="0f525-492">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="0f525-492">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="0f525-493">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="0f525-493">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="0f525-494">GP 唯一名称：ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="0f525-494">GP unique name: ProxyPacUrl</span></span>
- <span data-ttu-id="0f525-495">GP 名称：代理 .pac 文件的 URL</span><span class="sxs-lookup"><span data-stu-id="0f525-495">GP name: URL to a proxy .pac file</span></span>
- <span data-ttu-id="0f525-496">GP 路径：Administrative Templates/Microsoft Edge Update/Proxy Server</span><span class="sxs-lookup"><span data-stu-id="0f525-496">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="0f525-497">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="0f525-497">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="0f525-498">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="0f525-498">Windows Registry Settings</span></span>
- <span data-ttu-id="0f525-499">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="0f525-499">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="0f525-500">值名称：ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="0f525-500">Value Name: ProxyPacUrl</span></span>
- <span data-ttu-id="0f525-501">值类型：REG_SZ</span><span class="sxs-lookup"><span data-stu-id="0f525-501">Value Type: REG_SZ</span></span>
##### <a name="example-value"></a><span data-ttu-id="0f525-502">示例值：</span><span class="sxs-lookup"><span data-stu-id="0f525-502">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="0f525-503">返回页首</span><span class="sxs-lookup"><span data-stu-id="0f525-503">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="proxyserver"></a><span data-ttu-id="0f525-504">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="0f525-504">ProxyServer</span></span>
#### <a name="address-or-url-of-proxy-server"></a><span data-ttu-id="0f525-505">代理服务器的地址或 URL</span><span class="sxs-lookup"><span data-stu-id="0f525-505">Address or URL of proxy server</span></span>
><span data-ttu-id="0f525-506">Microsoft Edge 更新 1.3.21.81 和更高版本</span><span class="sxs-lookup"><span data-stu-id="0f525-506">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <a name="description"></a><span data-ttu-id="0f525-507">说明</span><span class="sxs-lookup"><span data-stu-id="0f525-507">Description</span></span>
<span data-ttu-id="0f525-508">允许你指定供 Microsoft Edge 更新使用的代理服务器的 URL。</span><span class="sxs-lookup"><span data-stu-id="0f525-508">Allows you to specify the URL of the proxy server for Microsoft Edge Update to use.</span></span>

  <span data-ttu-id="0f525-509">如果启用此策略，则可以设置组织中 Microsoft Edge 更新使用的代理服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="0f525-509">If you enable this policy, you can set the proxy server URL used by Microsoft Edge Update in your organization.</span></span>

  <span data-ttu-id="0f525-510">仅当你已在[“选择如何指定代理服务器设置”](#proxymode)策略中选择了手动代理设置时，才会应用此策略。</span><span class="sxs-lookup"><span data-stu-id="0f525-510">This policy is applied only if you have selected manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="0f525-511">如果你已在“[选择如何指定代理服务器设置](#proxymode)”策略中选择了手动设置以外的其他代理设置，请不要配置此策略。</span><span class="sxs-lookup"><span data-stu-id="0f525-511">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="0f525-512">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="0f525-512">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="0f525-513">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="0f525-513">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="0f525-514">GP 唯一名称：ProxyServer</span><span class="sxs-lookup"><span data-stu-id="0f525-514">GP unique name: ProxyServer</span></span>
- <span data-ttu-id="0f525-515">GP 名称：代理服务器的地址或 URL</span><span class="sxs-lookup"><span data-stu-id="0f525-515">GP name: Address or URL of proxy server</span></span>
- <span data-ttu-id="0f525-516">GP 路径：Administrative Templates/Microsoft Edge Update/Proxy Server</span><span class="sxs-lookup"><span data-stu-id="0f525-516">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="0f525-517">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="0f525-517">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="0f525-518">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="0f525-518">Windows Registry Settings</span></span>
- <span data-ttu-id="0f525-519">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="0f525-519">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="0f525-520">值名称：ProxyServer</span><span class="sxs-lookup"><span data-stu-id="0f525-520">Value Name: ProxyServer</span></span>
- <span data-ttu-id="0f525-521">值类型：REG_SZ</span><span class="sxs-lookup"><span data-stu-id="0f525-521">Value Type: REG_SZ</span></span>
##### <a name="example-value"></a><span data-ttu-id="0f525-522">示例值：</span><span class="sxs-lookup"><span data-stu-id="0f525-522">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="0f525-523">返回页首</span><span class="sxs-lookup"><span data-stu-id="0f525-523">Back to top</span></span>](#microsoft-edge---update-policies)


## <a name="microsoft-edge-webview-policies"></a><span data-ttu-id="0f525-524">- Microsoft Edge Web 视图策略</span><span class="sxs-lookup"><span data-stu-id="0f525-524">Microsoft Edge WebView policies</span></span>

[<span data-ttu-id="0f525-525">返回页首</span><span class="sxs-lookup"><span data-stu-id="0f525-525">Back to top</span></span>](#microsoft-edge---update-policies)
### <a name="install-webview"></a><span data-ttu-id="0f525-526">安装（WebView）</span><span class="sxs-lookup"><span data-stu-id="0f525-526">Install (WebView)</span></span>
#### <a name="allow-installation"></a><span data-ttu-id="0f525-527">允许安装</span><span class="sxs-lookup"><span data-stu-id="0f525-527">Allow installation</span></span>
><span data-ttu-id="0f525-528">Microsoft Edge 更新 1.3.127.1 和更高版本</span><span class="sxs-lookup"><span data-stu-id="0f525-528">Microsoft Edge Update 1.3.127.1 and later</span></span>

#### <a name="description"></a><span data-ttu-id="0f525-529">描述</span><span class="sxs-lookup"><span data-stu-id="0f525-529">Description</span></span>
<span data-ttu-id="0f525-530">指定是否可以使用 Microsoft Edge 更新来安装 Microsoft Edge Web 视图。</span><span class="sxs-lookup"><span data-stu-id="0f525-530">Lets you specify whether Microsoft Edge WebView can be installed using Microsoft Edge Update.</span></span>

  - <span data-ttu-id="0f525-531">如果启用此策略，用户可以通过 Microsoft Edge 更新来安装该 Microsoft Edge Web 视图。</span><span class="sxs-lookup"><span data-stu-id="0f525-531">If you enable this policy, users can install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
  - <span data-ttu-id="0f525-532">如果禁用此策略，用户无法通过 Microsoft Edge 更新来安装该 Microsoft Edge Web 视图。</span><span class="sxs-lookup"><span data-stu-id="0f525-532">If you disable this policy, users cannot install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
  - <span data-ttu-id="0f525-533">如果没有配置此策略，则“[允许安装默认项](#installdefault)”策略配置将决定用户是否可以通过 Microsoft Edge 更新来安装该 Microsoft Edge WebView。</span><span class="sxs-lookup"><span data-stu-id="0f525-533">If you don't configure this policy, the '[Allow installation default](#installdefault)' policy configuration determines whether users can install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="0f525-534">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="0f525-534">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="0f525-535">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="0f525-535">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="0f525-536">GP 唯一名称：安装</span><span class="sxs-lookup"><span data-stu-id="0f525-536">GP unique name: Install</span></span>
- <span data-ttu-id="0f525-537">GP 名称：允许安装</span><span class="sxs-lookup"><span data-stu-id="0f525-537">GP name: Allow installation</span></span>
- <span data-ttu-id="0f525-538">GP 路径：Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="0f525-538">GP path: Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView</span></span>
- <span data-ttu-id="0f525-539">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="0f525-539">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="0f525-540">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="0f525-540">Windows Registry Settings</span></span>
- <span data-ttu-id="0f525-541">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="0f525-541">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="0f525-542">值名称：</span><span class="sxs-lookup"><span data-stu-id="0f525-542">Value Name:</span></span> 
  - <span data-ttu-id="0f525-543">安装{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span><span class="sxs-lookup"><span data-stu-id="0f525-543">Install{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span></span>
- <span data-ttu-id="0f525-544">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="0f525-544">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="0f525-545">示例值：</span><span class="sxs-lookup"><span data-stu-id="0f525-545">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="0f525-546">返回页首</span><span class="sxs-lookup"><span data-stu-id="0f525-546">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="update-webview"></a><span data-ttu-id="0f525-547">更新（WebView）</span><span class="sxs-lookup"><span data-stu-id="0f525-547">Update (WebView)</span></span>
#### <a name="update-policy-override"></a><span data-ttu-id="0f525-548">更新策略替代</span><span class="sxs-lookup"><span data-stu-id="0f525-548">Update policy override</span></span>
><span data-ttu-id="0f525-549">Microsoft Edge 更新 1.3.127.1 和更高版本</span><span class="sxs-lookup"><span data-stu-id="0f525-549">Microsoft Edge Update 1.3.127.1 and later</span></span>

#### <a name="description"></a><span data-ttu-id="0f525-550">描述</span><span class="sxs-lookup"><span data-stu-id="0f525-550">Description</span></span>
<span data-ttu-id="0f525-551">可针对 Microsoft Edge Web 视图指定启用或不启用自动更新。</span><span class="sxs-lookup"><span data-stu-id="0f525-551">Lets you specify whether or not automatic updates are enabled for Microsoft Edge WebView.</span></span> <span data-ttu-id="0f525-552">Microsoft Edge Web 视图是应用程序用来显示 Web 内容的组件。</span><span class="sxs-lookup"><span data-stu-id="0f525-552">Microsoft Edge WebView is a component used by applications to display web content.</span></span>
<span data-ttu-id="0f525-553">默认情况下启用自动更新。</span><span class="sxs-lookup"><span data-stu-id="0f525-553">Automatic updates are enabled by default.</span></span> <span data-ttu-id="0f525-554">禁用 Microsoft Edge Web Edge 自动更新可能会导致依赖于此组件的应用程序出现兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="0f525-554">Disabling automatic updates for Microsoft Edge WebView might cause compatibility issues with applications that depend on this component.</span></span>

  <span data-ttu-id="0f525-555">如果你启用此策略，Microsoft Edge 更新将根据你配置以下选项的方式处理 Microsoft Edge Web 视图更新：</span><span class="sxs-lookup"><span data-stu-id="0f525-555">If you enable this policy, Microsoft Edge Update handles Microsoft Edge WebView updates according to how you configure the following options:</span></span>
  - <span data-ttu-id="0f525-556">始终允许更新：自动下载和应用更新</span><span class="sxs-lookup"><span data-stu-id="0f525-556">Always allow updates: Updates are automatically downloaded and applied</span></span>
  - <span data-ttu-id="0f525-557">禁用更新：从不下载或应用更新。</span><span class="sxs-lookup"><span data-stu-id="0f525-557">Updates disabled: Updates are never downloaded or applied</span></span>

  <span data-ttu-id="0f525-558">如果未启用此策略，则自动下载并应用更新。</span><span class="sxs-lookup"><span data-stu-id="0f525-558">If you don't enable this policy, updates are automatically downloaded and applied.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="0f525-559">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="0f525-559">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="0f525-560">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="0f525-560">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="0f525-561">GP 唯一名称：更新</span><span class="sxs-lookup"><span data-stu-id="0f525-561">GP unique name: Update</span></span>
- <span data-ttu-id="0f525-562">GP 名称：更新策略替代</span><span class="sxs-lookup"><span data-stu-id="0f525-562">GP name: Update policy override</span></span>
- <span data-ttu-id="0f525-563">GP 路径：Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="0f525-563">GP path: Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView</span></span>
- <span data-ttu-id="0f525-564">GP ADMX文件名：msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="0f525-564">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="0f525-565">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="0f525-565">Windows Registry Settings</span></span>
- <span data-ttu-id="0f525-566">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="0f525-566">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="0f525-567">值名称：</span><span class="sxs-lookup"><span data-stu-id="0f525-567">Value Name:</span></span> 
  - <span data-ttu-id="0f525-568">Update{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span><span class="sxs-lookup"><span data-stu-id="0f525-568">Update{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span></span>
- <span data-ttu-id="0f525-569">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="0f525-569">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="0f525-570">示例值：</span><span class="sxs-lookup"><span data-stu-id="0f525-570">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="0f525-571">返回页首</span><span class="sxs-lookup"><span data-stu-id="0f525-571">Back to top</span></span>](#microsoft-edge---update-policies)


## <a name="see-also"></a><span data-ttu-id="0f525-572">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f525-572">See also</span></span>
  - [<span data-ttu-id="0f525-573">配置 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0f525-573">Configuring Microsoft Edge</span></span>](configure-microsoft-edge.md)
  - [<span data-ttu-id="0f525-574">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="0f525-574">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
