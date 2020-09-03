---
title: Microsoft Edge 更新策略文档
ms.author: stmoody
author: brianalt-msft
manager: tahills
ms.date: 06/10/2020
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Microsoft Edge 更新程序支持的所有策略的文档
ms.openlocfilehash: d772d8dd6f60b89e9bd12a77b740e5fad699756a
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979322"
---
# <span data-ttu-id="c43b9-103">Microsoft Edge - 更新策略</span><span class="sxs-lookup"><span data-stu-id="c43b9-103">Microsoft Edge - Update policies</span></span>
<span data-ttu-id="c43b9-104">最新版本的 Microsoft Edge 包含以下策略，你可以使用这些策略控制更新 Microsoft Edge 的方式和时间。</span><span class="sxs-lookup"><span data-stu-id="c43b9-104">The latest version of Microsoft Edge includes the following policies that you can use to control how and when Microsoft Edge is updated.</span></span>

           
<span data-ttu-id="c43b9-105">有关 Microsoft Edge 中可用的其他策略的信息，请查看 [Microsoft Edge 浏览器策略引用](microsoft-edge-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c43b9-105">For information about other policies available in Microsoft Edge, check out [Microsoft Edge browser policy reference](microsoft-edge-policies.md)</span></span>
> [!NOTE]
> <span data-ttu-id="c43b9-106">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="c43b9-106">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="c43b9-107">可用策略</span><span class="sxs-lookup"><span data-stu-id="c43b9-107">Available policies</span></span>
<span data-ttu-id="c43b9-108">这些表列出了本版本 Microsoft Edge 中提供的所有与更新相关的组策略。</span><span class="sxs-lookup"><span data-stu-id="c43b9-108">These tables lists all of the update-related group policies available in this release of Microsoft Edge.</span></span> <span data-ttu-id="c43b9-109">使用表中的链接获取有关特定策略的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="c43b9-109">Use the links in the table to get more details about specific policies.</span></span>

|||
|-|-|
|[<span data-ttu-id="c43b9-110">应用程序</span><span class="sxs-lookup"><span data-stu-id="c43b9-110">Applications</span></span>](#applications)|[<span data-ttu-id="c43b9-111">首选项</span><span class="sxs-lookup"><span data-stu-id="c43b9-111">Preferences</span></span>](#preferences)|
|[<span data-ttu-id="c43b9-112">代理服务器</span><span class="sxs-lookup"><span data-stu-id="c43b9-112">Proxy Server</span></span>](#proxy-server)||

### [<span data-ttu-id="c43b9-113">应用程序</span><span class="sxs-lookup"><span data-stu-id="c43b9-113">Applications</span></span>](#applications-policies)
|<span data-ttu-id="c43b9-114">策略名称</span><span class="sxs-lookup"><span data-stu-id="c43b9-114">Policy Name</span></span>|<span data-ttu-id="c43b9-115">标题</span><span class="sxs-lookup"><span data-stu-id="c43b9-115">Caption</span></span>|
|-|-|
|[<span data-ttu-id="c43b9-116">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="c43b9-116">InstallDefault</span></span>](#installdefault)|<span data-ttu-id="c43b9-117">允许安装默认项</span><span class="sxs-lookup"><span data-stu-id="c43b9-117">Allow installation default</span></span>|
|[<span data-ttu-id="c43b9-118">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="c43b9-118">UpdateDefault</span></span>](#updatedefault)|<span data-ttu-id="c43b9-119">更新策略替代默认值</span><span class="sxs-lookup"><span data-stu-id="c43b9-119">Update policy override default</span></span>|
|[<span data-ttu-id="c43b9-120">安装</span><span class="sxs-lookup"><span data-stu-id="c43b9-120">Install</span></span>](#install)|<span data-ttu-id="c43b9-121">允许安装（按渠道）</span><span class="sxs-lookup"><span data-stu-id="c43b9-121">Allow installation (per channel)</span></span>|
|[<span data-ttu-id="c43b9-122">更新</span><span class="sxs-lookup"><span data-stu-id="c43b9-122">Update</span></span>](#update)|<span data-ttu-id="c43b9-123">更新策略替代（按渠道）</span><span class="sxs-lookup"><span data-stu-id="c43b9-123">Update policy override (per channel)</span></span>|
|[<span data-ttu-id="c43b9-124">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="c43b9-124">Allowsxs</span></span>](#allowsxs)|<span data-ttu-id="c43b9-125">允许 Microsoft Edge 并行浏览器体验</span><span class="sxs-lookup"><span data-stu-id="c43b9-125">Allow Microsoft Edge Side by Side browser experience</span></span>|
|[<span data-ttu-id="c43b9-126">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="c43b9-126">CreateDesktopShortcutDefault</span></span>](#createdesktopshortcutdefault)|<span data-ttu-id="c43b9-127">安装默认项时阻止创建快捷方式</span><span class="sxs-lookup"><span data-stu-id="c43b9-127">Prevent Desktop Shortcut creation upon install default</span></span>|
|[<span data-ttu-id="c43b9-128">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="c43b9-128">CreateDesktopShortcut</span></span>](#createdesktopshortcut)|<span data-ttu-id="c43b9-129">安装时阻止创建快捷方式（按渠道）</span><span class="sxs-lookup"><span data-stu-id="c43b9-129">Prevent Desktop Shortcut creation upon install (per channel)</span></span>|
|[<span data-ttu-id="c43b9-130">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="c43b9-130">TargetVersionPrefix</span></span>](#targetversionprefix)|<span data-ttu-id="c43b9-131">目标版本覆盖（各渠道）</span><span class="sxs-lookup"><span data-stu-id="c43b9-131">Target version override (per channel)</span></span>|

### [<span data-ttu-id="c43b9-132">首选项</span><span class="sxs-lookup"><span data-stu-id="c43b9-132">Preferences</span></span>](#preferences-policies)
|<span data-ttu-id="c43b9-133">策略名称</span><span class="sxs-lookup"><span data-stu-id="c43b9-133">Policy Name</span></span>|<span data-ttu-id="c43b9-134">标题</span><span class="sxs-lookup"><span data-stu-id="c43b9-134">Caption</span></span>|
|-|-|
|[<span data-ttu-id="c43b9-135">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="c43b9-135">AutoUpdateCheckPeriodMinutes</span></span>](#autoupdatecheckperiodminutes)|<span data-ttu-id="c43b9-136">自动更新检查期间替代</span><span class="sxs-lookup"><span data-stu-id="c43b9-136">Auto-update check period override</span></span>|
|[<span data-ttu-id="c43b9-137">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="c43b9-137">UpdatesSuppressed</span></span>](#updatessuppressed)|<span data-ttu-id="c43b9-138">每天中取消自动更新检查的时间段</span><span class="sxs-lookup"><span data-stu-id="c43b9-138">Time period in each day to suppress auto-update check</span></span>|

### [<span data-ttu-id="c43b9-139">代理服务器</span><span class="sxs-lookup"><span data-stu-id="c43b9-139">Proxy Server</span></span>](#proxy-server-policies)
|<span data-ttu-id="c43b9-140">策略名称</span><span class="sxs-lookup"><span data-stu-id="c43b9-140">Policy Name</span></span>|<span data-ttu-id="c43b9-141">描述文字</span><span class="sxs-lookup"><span data-stu-id="c43b9-141">Caption</span></span>|
|-|-|
|[<span data-ttu-id="c43b9-142">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="c43b9-142">ProxyMode</span></span>](#proxymode)|<span data-ttu-id="c43b9-143">选择指定代理服务器设置的方式</span><span class="sxs-lookup"><span data-stu-id="c43b9-143">Choose how to specify proxy server settings</span></span>|
|[<span data-ttu-id="c43b9-144">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="c43b9-144">ProxyPacUrl</span></span>](#proxypacurl)|<span data-ttu-id="c43b9-145">代理 .pac 文件的 URL</span><span class="sxs-lookup"><span data-stu-id="c43b9-145">URL to a proxy .pac file</span></span>|
|[<span data-ttu-id="c43b9-146">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="c43b9-146">ProxyServer</span></span>](#proxyserver)|<span data-ttu-id="c43b9-147">代理服务器的地址或 URL</span><span class="sxs-lookup"><span data-stu-id="c43b9-147">Address or URL of proxy server</span></span>|

                 
      
  
             
            
                  

## <span data-ttu-id="c43b9-148">应用程序策略</span><span class="sxs-lookup"><span data-stu-id="c43b9-148">Applications policies</span></span>

[<span data-ttu-id="c43b9-149">返回页首</span><span class="sxs-lookup"><span data-stu-id="c43b9-149">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="c43b9-150">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="c43b9-150">InstallDefault</span></span>
#### <span data-ttu-id="c43b9-151">允许安装默认项</span><span class="sxs-lookup"><span data-stu-id="c43b9-151">Allow installation default</span></span>
><span data-ttu-id="c43b9-152">Microsoft Edge 更新 1.2.145.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="c43b9-152">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="c43b9-153">描述</span><span class="sxs-lookup"><span data-stu-id="c43b9-153">Description</span></span>
<span data-ttu-id="c43b9-154">可指定所有渠道的默认行为，以在使用 Microsoft Edge 更新时允许或阻止更新 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="c43b9-154">You can specify the default behavior of all channels to allow or block Microsoft Edge updates when Microsoft Edge Update is used.</span></span>

<span data-ttu-id="c43b9-155">通过为那些特定渠道启用“[允许安装](#install)”策略，可为个别渠道覆盖此策略。</span><span class="sxs-lookup"><span data-stu-id="c43b9-155">You can override this policy for individual channels by enabling the '[Allow installation](#install)' policy for specific channels.</span></span>

<span data-ttu-id="c43b9-156">如果禁用此策略，则会禁止通过 Microsoft Edge 更新安装 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="c43b9-156">If you disable this policy, the installation of Microsoft Edge through Microsoft Edge Update is blocked.</span></span> <span data-ttu-id="c43b9-157">这仅当用户运行 Microsoft Edge 更新，并且未配置“[允许安装](#install)”策略时，才会影响 Microsoft Edge 软件的安装。</span><span class="sxs-lookup"><span data-stu-id="c43b9-157">This only affects the installation of Microsoft Edge software only when users are running Microsoft Edge Update and when they haven't configured the '[Allow installation](#install)' policy.</span></span>

<span data-ttu-id="c43b9-158">此策略不会阻止运行 Microsoft Edge 更新，也不会阻止用户使用其他方法安装 Microsoft Edge 软件。</span><span class="sxs-lookup"><span data-stu-id="c43b9-158">This policy doesn't prevent Microsoft Edge Update from running or prevent users from installing Microsoft Edge software using other methods.</span></span>
#### <span data-ttu-id="c43b9-159">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-159">Windows information and settings</span></span>
##### <span data-ttu-id="c43b9-160">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="c43b9-160">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c43b9-161">GP 唯一名称：InstallDefault</span><span class="sxs-lookup"><span data-stu-id="c43b9-161">GP unique name: InstallDefault</span></span>
- <span data-ttu-id="c43b9-162">GP 名称：允许安装默认项</span><span class="sxs-lookup"><span data-stu-id="c43b9-162">GP name: Allow installation default</span></span>
- <span data-ttu-id="c43b9-163">GP 路径：Administrative Templates/Microsoft Edge Update/Applications</span><span class="sxs-lookup"><span data-stu-id="c43b9-163">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="c43b9-164">GP ADMX 文件名：edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c43b9-164">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c43b9-165">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-165">Windows Registry Settings</span></span>
- <span data-ttu-id="c43b9-166">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c43b9-166">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c43b9-167">值名称：InstallDefault</span><span class="sxs-lookup"><span data-stu-id="c43b9-167">Value Name: InstallDefault</span></span>
- <span data-ttu-id="c43b9-168">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c43b9-168">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="c43b9-169">示例值：</span><span class="sxs-lookup"><span data-stu-id="c43b9-169">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="c43b9-170">返回页首</span><span class="sxs-lookup"><span data-stu-id="c43b9-170">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="c43b9-171">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="c43b9-171">UpdateDefault</span></span>
#### <span data-ttu-id="c43b9-172">更新策略替代默认值</span><span class="sxs-lookup"><span data-stu-id="c43b9-172">Update policy override default</span></span>
><span data-ttu-id="c43b9-173">Microsoft Edge 更新 1.2.145.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="c43b9-173">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="c43b9-174">描述</span><span class="sxs-lookup"><span data-stu-id="c43b9-174">Description</span></span>
<span data-ttu-id="c43b9-175">允许你为所有渠道指定与 Microsoft Edge 更新处理 Microsoft Edge 可用更新的方式有关的默认行为。</span><span class="sxs-lookup"><span data-stu-id="c43b9-175">Lets you specify the default behavior for all channels concerning the way Microsoft Edge Update handles available updates for Microsoft Edge.</span></span> <span data-ttu-id="c43b9-176">通过为那些特定渠道指定“[更新策略替代](#update)”策略，可为个别渠道进行覆盖。</span><span class="sxs-lookup"><span data-stu-id="c43b9-176">Can be overridden for individual channels by specifying the '[Update policy override](#update)' policy for those specific channels.</span></span>

  <span data-ttu-id="c43b9-177">如果你启用此策略，Microsoft Edge 更新将根据你配置以下选项的方式处理 Microsoft Edge 更新：</span><span class="sxs-lookup"><span data-stu-id="c43b9-177">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
   - <span data-ttu-id="c43b9-178">始终允许更新：通过定期更新检查或通过手动更新检查，在发现更新时始终应用更新。</span><span class="sxs-lookup"><span data-stu-id="c43b9-178">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
   - <span data-ttu-id="c43b9-179">仅限自动无提示更新：仅在定期更新检查找到更新后才应用更新。</span><span class="sxs-lookup"><span data-stu-id="c43b9-179">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
   - <span data-ttu-id="c43b9-180">仅限手动更新：仅当用户运行手动更新检查时才应用更新。</span><span class="sxs-lookup"><span data-stu-id="c43b9-180">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span>
   - <span data-ttu-id="c43b9-181">已禁用更新：从不应用更新。</span><span class="sxs-lookup"><span data-stu-id="c43b9-181">Updates disabled: Updates are never applied.</span></span>

  <span data-ttu-id="c43b9-182">如果你选择手动更新，请确保使用应用的手动更新机制（如果有）定期检查更新。</span><span class="sxs-lookup"><span data-stu-id="c43b9-182">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="c43b9-183">如果你禁用更新，请定期检查更新，然后将它们分发给用户。</span><span class="sxs-lookup"><span data-stu-id="c43b9-183">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

  <span data-ttu-id="c43b9-184">如果你未启用和配置此策略，Microsoft Edge 更新将处理“[更新策略替代](#update)”策略指定的可用更新。</span><span class="sxs-lookup"><span data-stu-id="c43b9-184">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override](#update)' policy.</span></span>
#### <span data-ttu-id="c43b9-185">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-185">Windows information and settings</span></span>
##### <span data-ttu-id="c43b9-186">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="c43b9-186">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c43b9-187">GP 唯一名称：UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="c43b9-187">GP unique name: UpdateDefault</span></span>
- <span data-ttu-id="c43b9-188">GP 名称：更新策略替代默认值</span><span class="sxs-lookup"><span data-stu-id="c43b9-188">GP name: Update policy override default</span></span>
- <span data-ttu-id="c43b9-189">GP 路径：Administrative Templates/Microsoft Edge Update/Applications</span><span class="sxs-lookup"><span data-stu-id="c43b9-189">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="c43b9-190">GP ADMX 文件名：edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c43b9-190">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c43b9-191">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-191">Windows Registry Settings</span></span>
- <span data-ttu-id="c43b9-192">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c43b9-192">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c43b9-193">值名称：UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="c43b9-193">Value Name: UpdateDefault</span></span>
- <span data-ttu-id="c43b9-194">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c43b9-194">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="c43b9-195">示例值：</span><span class="sxs-lookup"><span data-stu-id="c43b9-195">Example value:</span></span>
```
0x00000003
```
[<span data-ttu-id="c43b9-196">返回页首</span><span class="sxs-lookup"><span data-stu-id="c43b9-196">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="c43b9-197">安装</span><span class="sxs-lookup"><span data-stu-id="c43b9-197">Install</span></span>
#### <span data-ttu-id="c43b9-198">允许安装</span><span class="sxs-lookup"><span data-stu-id="c43b9-198">Allow installation</span></span>
><span data-ttu-id="c43b9-199">Microsoft Edge 更新 1.2.145.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="c43b9-199">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="c43b9-200">说明</span><span class="sxs-lookup"><span data-stu-id="c43b9-200">Description</span></span>
<span data-ttu-id="c43b9-201">指定是否可以使用 Microsoft Edge 更新来安装 Microsoft Edge 渠道。</span><span class="sxs-lookup"><span data-stu-id="c43b9-201">Specifies whether a Microsoft Edge channel can be installed using Microsoft Edge Update.</span></span>

  <span data-ttu-id="c43b9-202">如果你为某个渠道启用此策略，则用户可以通过 Microsoft Edge 更新来安装该 Microsoft Edge 渠道。</span><span class="sxs-lookup"><span data-stu-id="c43b9-202">If you enable this policy for a channel, users can install that channel of Microsoft Edge through Microsoft Edge Update.</span></span>

  <span data-ttu-id="c43b9-203">如果你为某个渠道禁用此策略，则用户无法通过 Microsoft Edge 更新来安装该 Microsoft Edge 渠道。</span><span class="sxs-lookup"><span data-stu-id="c43b9-203">If you disable this policy for a channel, users cannot install that channel of Microsoft Edge through Microsoft Edge Update.</span></span>

  <span data-ttu-id="c43b9-204">如果没有为渠道配置此策略，则“[允许安装默认项](#installdefault)”策略配置将确定用户是否可以通过 Microsoft Edge 更新来安装该 Microsoft Edge 渠道。</span><span class="sxs-lookup"><span data-stu-id="c43b9-204">If you don't configure this policy for a channel, the '[Allow installation default](#installdefault)' policy configuration determines whether users can install that channel of Microsoft Edge through Microsoft Edge Update.</span></span>
#### <span data-ttu-id="c43b9-205">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-205">Windows information and settings</span></span>
##### <span data-ttu-id="c43b9-206">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="c43b9-206">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c43b9-207">GP 唯一名称：安装</span><span class="sxs-lookup"><span data-stu-id="c43b9-207">GP unique name: Install</span></span>
- <span data-ttu-id="c43b9-208">GP 名称：允许安装</span><span class="sxs-lookup"><span data-stu-id="c43b9-208">GP name: Allow installation</span></span>
- <span data-ttu-id="c43b9-209">GP 路径：</span><span class="sxs-lookup"><span data-stu-id="c43b9-209">GP path:</span></span> 
  - <span data-ttu-id="c43b9-210">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c43b9-210">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="c43b9-211">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="c43b9-211">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="c43b9-212">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="c43b9-212">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="c43b9-213">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="c43b9-213">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="c43b9-214">GP ADMX 文件名：edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c43b9-214">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c43b9-215">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-215">Windows Registry Settings</span></span>
- <span data-ttu-id="c43b9-216">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c43b9-216">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c43b9-217">值名称：</span><span class="sxs-lookup"><span data-stu-id="c43b9-217">Value Name:</span></span> 
  - <span data-ttu-id="c43b9-218">（稳定）：安装 {56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="c43b9-218">(Stable): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="c43b9-219">(Beta)：安装 {2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="c43b9-219">(Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="c43b9-220">(Canary)：安装 {65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="c43b9-220">(Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="c43b9-221">(Dev)：安装 {0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="c43b9-221">(Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="c43b9-222">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c43b9-222">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="c43b9-223">示例值：</span><span class="sxs-lookup"><span data-stu-id="c43b9-223">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="c43b9-224">返回页首</span><span class="sxs-lookup"><span data-stu-id="c43b9-224">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="c43b9-225">更新</span><span class="sxs-lookup"><span data-stu-id="c43b9-225">Update</span></span>
#### <span data-ttu-id="c43b9-226">更新策略替代</span><span class="sxs-lookup"><span data-stu-id="c43b9-226">Update policy override</span></span>
><span data-ttu-id="c43b9-227">Microsoft Edge 更新 1.2.145.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="c43b9-227">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="c43b9-228">描述</span><span class="sxs-lookup"><span data-stu-id="c43b9-228">Description</span></span>
<span data-ttu-id="c43b9-229">指定 Microsoft Edge 更新如何处理 Microsoft Edge 中的可用更新。</span><span class="sxs-lookup"><span data-stu-id="c43b9-229">Specifies how Microsoft Edge Update handles available updates from Microsoft Edge.</span></span>

  <span data-ttu-id="c43b9-230">如果你启用此策略，Microsoft Edge 更新将根据你配置以下选项的方式处理 Microsoft Edge 更新：</span><span class="sxs-lookup"><span data-stu-id="c43b9-230">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
   - <span data-ttu-id="c43b9-231">始终允许更新：通过定期更新检查或通过手动更新检查，在发现更新时始终应用更新。</span><span class="sxs-lookup"><span data-stu-id="c43b9-231">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
   - <span data-ttu-id="c43b9-232">仅限自动无提示更新：仅在定期更新检查找到更新后才应用更新。</span><span class="sxs-lookup"><span data-stu-id="c43b9-232">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
   - <span data-ttu-id="c43b9-233">仅限手动更新：仅当用户运行手动更新检查时才应用更新。</span><span class="sxs-lookup"><span data-stu-id="c43b9-233">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span> <span data-ttu-id="c43b9-234">（并非所有应用都为此选项提供接口。）</span><span class="sxs-lookup"><span data-stu-id="c43b9-234">(Not all apps provide an interface for this option.)</span></span>
   - <span data-ttu-id="c43b9-235">已禁用更新：从不应用更新。</span><span class="sxs-lookup"><span data-stu-id="c43b9-235">Updates disabled: Updates are never applied.</span></span>

  <span data-ttu-id="c43b9-236">如果你选择手动更新，请确保使用应用的手动更新机制（如果有）定期检查更新。</span><span class="sxs-lookup"><span data-stu-id="c43b9-236">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="c43b9-237">如果你禁用更新，请定期检查更新，然后将它们分发给用户。</span><span class="sxs-lookup"><span data-stu-id="c43b9-237">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

  <span data-ttu-id="c43b9-238">如果你未启用和配置此策略，Microsoft Edge 更新将处理“[更新策略替代默认值](#updatedefault)”策略指定的可用更新。</span><span class="sxs-lookup"><span data-stu-id="c43b9-238">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override default](#updatedefault)' policy.</span></span>
#### <span data-ttu-id="c43b9-239">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-239">Windows information and settings</span></span>
##### <span data-ttu-id="c43b9-240">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="c43b9-240">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c43b9-241">GP 唯一名称：更新</span><span class="sxs-lookup"><span data-stu-id="c43b9-241">GP unique name: Update</span></span>
- <span data-ttu-id="c43b9-242">GP 名称：更新策略替代</span><span class="sxs-lookup"><span data-stu-id="c43b9-242">GP name: Update policy override</span></span>
- <span data-ttu-id="c43b9-243">GP 路径：</span><span class="sxs-lookup"><span data-stu-id="c43b9-243">GP path:</span></span> 
  - <span data-ttu-id="c43b9-244">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c43b9-244">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="c43b9-245">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="c43b9-245">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="c43b9-246">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="c43b9-246">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="c43b9-247">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="c43b9-247">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="c43b9-248">GP ADMX 文件名：edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c43b9-248">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c43b9-249">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-249">Windows Registry Settings</span></span>
- <span data-ttu-id="c43b9-250">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c43b9-250">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c43b9-251">值名称：</span><span class="sxs-lookup"><span data-stu-id="c43b9-251">Value Name:</span></span> 
  - <span data-ttu-id="c43b9-252">（稳定）：更新 {56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="c43b9-252">(Stable): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="c43b9-253">(Beta)：更新 {2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="c43b9-253">(Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="c43b9-254">(Canary)：更新 {65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="c43b9-254">(Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="c43b9-255">(Dev)：更新 {0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="c43b9-255">(Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="c43b9-256">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c43b9-256">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="c43b9-257">示例值：</span><span class="sxs-lookup"><span data-stu-id="c43b9-257">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="c43b9-258">返回页首</span><span class="sxs-lookup"><span data-stu-id="c43b9-258">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="c43b9-259">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="c43b9-259">Allowsxs</span></span>
#### <span data-ttu-id="c43b9-260">允许 Microsoft Edge 并行浏览器体验</span><span class="sxs-lookup"><span data-stu-id="c43b9-260">Allow Microsoft Edge Side by Side browser experience</span></span>
><span data-ttu-id="c43b9-261">Microsoft Edge 更新 1.2.145.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="c43b9-261">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="c43b9-262">说明</span><span class="sxs-lookup"><span data-stu-id="c43b9-262">Description</span></span>
<span data-ttu-id="c43b9-263">此策略允许用户并行运行 Microsoft Edge (Edge HTML) 和 Microsoft Edge（基于 Chromium）。</span><span class="sxs-lookup"><span data-stu-id="c43b9-263">This policy lets a user run Microsoft Edge (Edge HTML) and Microsoft Edge (Chromium-based) side-by-side.</span></span>

<span data-ttu-id="c43b9-264">如果将此策略设置为“未配置”，则在安装 Microsoft Edge（基于 Chromium）稳定渠道和 2019 年 11 月安全更新后，Microsoft Edge（基于 Chromium）将替换 Microsoft Edge (Edge HTML)。</span><span class="sxs-lookup"><span data-stu-id="c43b9-264">If this policy is set to “Not configured”, Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="c43b9-265">此行为与“已禁用”设置相同。</span><span class="sxs-lookup"><span data-stu-id="c43b9-265">This is the same behavior as the “Disabled” setting.</span></span>

<span data-ttu-id="c43b9-266">在安装 Microsoft Edge（基于 Chromium）稳定渠道和 2019 年 11 月安全更新后，“已禁用”设置会阻止并行体验，并且 Microsoft Edge（基于 Chromium）将替换 Microsoft Edge (Edge HTML)。</span><span class="sxs-lookup"><span data-stu-id="c43b9-266">The “Disabled” setting blocks a side-by-side experience and Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="c43b9-267">此行为与“未配置”设置相同。</span><span class="sxs-lookup"><span data-stu-id="c43b9-267">This is the same behavior as the “Not Configured” setting.</span></span>

<span data-ttu-id="c43b9-268">如果“已启用”此策略，则在安装 Microsoft Edge（基于 Chromium）后，Microsoft Edge（基于 Chromium）和 Microsoft Edge (Edge HTML) 可并行运行。</span><span class="sxs-lookup"><span data-stu-id="c43b9-268">When this policy is “Enabled”, Microsoft Edge (Chromium-based) and Microsoft Edge (Edge HTML) can run side-by-side after Microsoft Edge (Chromium-based) is installed.</span></span>

<span data-ttu-id="c43b9-269">若要使此组策略生效，必须先配置它，然后再通过 Windows 更新自动安装 Microsoft Edge（基于 Chromium）。</span><span class="sxs-lookup"><span data-stu-id="c43b9-269">For this group policy to take affect, it must be configured before the automatic install of Microsoft Edge (Chromium-based) by Windows Update.</span></span> <span data-ttu-id="c43b9-270">注意：通过使用 Microsoft Edge（基于 Chromium）阻止程序工具包，用户可以阻止自动更新 Microsoft Edge（基于 Chromium）。</span><span class="sxs-lookup"><span data-stu-id="c43b9-270">Note: A user can block the automatic update of Microsoft Edge (Chromium-based) by using the Microsoft Edge (Chromium-based) Blocker Toolkit.</span></span>
#### <span data-ttu-id="c43b9-271">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-271">Windows information and settings</span></span>
##### <span data-ttu-id="c43b9-272">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="c43b9-272">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c43b9-273">GP 唯一名称：Allowsxs</span><span class="sxs-lookup"><span data-stu-id="c43b9-273">GP unique name: Allowsxs</span></span>
- <span data-ttu-id="c43b9-274">GP 名称：允许 Microsoft Edge 并行浏览器体验</span><span class="sxs-lookup"><span data-stu-id="c43b9-274">GP name: Allow Microsoft Edge Side by Side browser experience</span></span>
- <span data-ttu-id="c43b9-275">GP 路径：Administrative Templates/Microsoft Edge Update/Applications</span><span class="sxs-lookup"><span data-stu-id="c43b9-275">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="c43b9-276">GP ADMX 文件名：edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c43b9-276">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c43b9-277">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-277">Windows Registry Settings</span></span>
- <span data-ttu-id="c43b9-278">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c43b9-278">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c43b9-279">值名称：Allowsxs</span><span class="sxs-lookup"><span data-stu-id="c43b9-279">Value Name: Allowsxs</span></span>
- <span data-ttu-id="c43b9-280">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c43b9-280">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="c43b9-281">示例值：</span><span class="sxs-lookup"><span data-stu-id="c43b9-281">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="c43b9-282">返回页首</span><span class="sxs-lookup"><span data-stu-id="c43b9-282">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="c43b9-283">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="c43b9-283">CreateDesktopShortcutDefault</span></span>
#### <span data-ttu-id="c43b9-284">安装默认项时阻止创建快捷方式</span><span class="sxs-lookup"><span data-stu-id="c43b9-284">Prevent Desktop Shortcut creation upon install default</span></span>
><span data-ttu-id="c43b9-285">Microsoft Edge 更新 1.3.128.0 和更高版本</span><span class="sxs-lookup"><span data-stu-id="c43b9-285">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <span data-ttu-id="c43b9-286">描述</span><span class="sxs-lookup"><span data-stu-id="c43b9-286">Description</span></span>
<span data-ttu-id="c43b9-287">安装 Microsoft Edge 时，可针对创建桌面快捷方式指定所有渠道的默认行为。</span><span class="sxs-lookup"><span data-stu-id="c43b9-287">Lets you specify the default behavior for all channels for creating a desktop shortcut when Microsoft Edge is installed.</span></span>

  <span data-ttu-id="c43b9-288">如果启用此策略，在安装 Microsoft Edge 时会创建桌面快捷方式。</span><span class="sxs-lookup"><span data-stu-id="c43b9-288">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="c43b9-289">如果禁用此策略，在安装 Microsoft Edge 时不创建桌面快捷方式。</span><span class="sxs-lookup"><span data-stu-id="c43b9-289">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="c43b9-290">如果未配置此策略，会在安装过程中创建 Microsoft Edge 桌面快捷方式。</span><span class="sxs-lookup"><span data-stu-id="c43b9-290">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="c43b9-291">如果已安装 Microsoft Edge，此策略将不起作用。</span><span class="sxs-lookup"><span data-stu-id="c43b9-291">If Microsoft Edge is already installed, this policy will have no effect.</span></span>
#### <span data-ttu-id="c43b9-292">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-292">Windows information and settings</span></span>
##### <span data-ttu-id="c43b9-293">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="c43b9-293">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c43b9-294">GP 唯一名称：CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="c43b9-294">GP unique name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="c43b9-295">GP 名称：安装默认项时阻止创建快捷方式</span><span class="sxs-lookup"><span data-stu-id="c43b9-295">GP name: Prevent Desktop Shortcut creation upon install default</span></span>
- <span data-ttu-id="c43b9-296">GP 路径：Administrative Templates/Microsoft Edge Update/Applications</span><span class="sxs-lookup"><span data-stu-id="c43b9-296">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="c43b9-297">GP ADMX 文件名：edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c43b9-297">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c43b9-298">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-298">Windows Registry Settings</span></span>
- <span data-ttu-id="c43b9-299">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c43b9-299">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c43b9-300">值名称：CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="c43b9-300">Value Name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="c43b9-301">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c43b9-301">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="c43b9-302">示例值：</span><span class="sxs-lookup"><span data-stu-id="c43b9-302">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="c43b9-303">返回页首</span><span class="sxs-lookup"><span data-stu-id="c43b9-303">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="c43b9-304">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="c43b9-304">CreateDesktopShortcut</span></span>
#### <span data-ttu-id="c43b9-305">安装时阻止创建快捷方式</span><span class="sxs-lookup"><span data-stu-id="c43b9-305">Prevent Desktop Shortcut creation upon install</span></span>
><span data-ttu-id="c43b9-306">Microsoft Edge 更新 1.3.128.0 和更高版本</span><span class="sxs-lookup"><span data-stu-id="c43b9-306">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <span data-ttu-id="c43b9-307">描述</span><span class="sxs-lookup"><span data-stu-id="c43b9-307">Description</span></span>
<span data-ttu-id="c43b9-308">如果启用此策略，在安装 Microsoft Edge 时会创建桌面快捷方式。</span><span class="sxs-lookup"><span data-stu-id="c43b9-308">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="c43b9-309">如果禁用此策略，在安装 Microsoft Edge 时不创建桌面快捷方式。</span><span class="sxs-lookup"><span data-stu-id="c43b9-309">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="c43b9-310">如果未配置此策略，会在安装过程中创建 Microsoft Edge 桌面快捷方式。</span><span class="sxs-lookup"><span data-stu-id="c43b9-310">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="c43b9-311">如果已安装 Microsoft Edge，此策略将不起作用。</span><span class="sxs-lookup"><span data-stu-id="c43b9-311">If Microsoft Edge is already installed, this policy will have no effect.</span></span>

  <span data-ttu-id="c43b9-312">如果未为频道配置此策略，则“[Prevent Desktop Shortcut creation upon install default](#createdesktopshortcutdefault)”策略配置将确定在安装 Microsoft Edge 时创建快捷方式。</span><span class="sxs-lookup"><span data-stu-id="c43b9-312">If you don't configure this policy for a channel, the '[Prevent Desktop Shortcut creation upon install default](#createdesktopshortcutdefault)' policy configuration determines shortcut creation when Microsoft Edge is installed.</span></span>
#### <span data-ttu-id="c43b9-313">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-313">Windows information and settings</span></span>
##### <span data-ttu-id="c43b9-314">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="c43b9-314">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c43b9-315">GP 唯一名称：CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="c43b9-315">GP unique name: CreateDesktopShortcut</span></span>
- <span data-ttu-id="c43b9-316">GP 名称：安装时阻止创建快捷方式</span><span class="sxs-lookup"><span data-stu-id="c43b9-316">GP name: Prevent Desktop Shortcut creation upon install</span></span>
- <span data-ttu-id="c43b9-317">GP 路径：</span><span class="sxs-lookup"><span data-stu-id="c43b9-317">GP path:</span></span> 
  - <span data-ttu-id="c43b9-318">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c43b9-318">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="c43b9-319">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="c43b9-319">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="c43b9-320">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="c43b9-320">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="c43b9-321">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="c43b9-321">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="c43b9-322">GP ADMX 文件名：edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c43b9-322">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c43b9-323">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-323">Windows Registry Settings</span></span>
- <span data-ttu-id="c43b9-324">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c43b9-324">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c43b9-325">值名称：</span><span class="sxs-lookup"><span data-stu-id="c43b9-325">Value Name:</span></span> 
  - <span data-ttu-id="c43b9-326">（稳定）：CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="c43b9-326">(Stable): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="c43b9-327">(Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="c43b9-327">(Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="c43b9-328">(Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="c43b9-328">(Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="c43b9-329">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="c43b9-329">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="c43b9-330">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c43b9-330">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="c43b9-331">示例值：</span><span class="sxs-lookup"><span data-stu-id="c43b9-331">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="c43b9-332">返回页首</span><span class="sxs-lookup"><span data-stu-id="c43b9-332">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="c43b9-333">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="c43b9-333">TargetVersionPrefix</span></span>
#### <span data-ttu-id="c43b9-334">目标版本覆盖</span><span class="sxs-lookup"><span data-stu-id="c43b9-334">Target version override</span></span>
><span data-ttu-id="c43b9-335">Microsoft Edge 更新 1.3.119.43 和更高版本</span><span class="sxs-lookup"><span data-stu-id="c43b9-335">Microsoft Edge Update 1.3.119.43 and later</span></span>

#### <span data-ttu-id="c43b9-336">描述</span><span class="sxs-lookup"><span data-stu-id="c43b9-336">Description</span></span>
<span data-ttu-id="c43b9-337">启用此策略并启用自动更新后，Microsoft Edge 将更新为该策略值指定的版本。</span><span class="sxs-lookup"><span data-stu-id="c43b9-337">When this policy is enabled, and auto-update is enabled, Microsoft Edge will be updated to the version specified by this policy value.</span></span>

<span data-ttu-id="c43b9-338">策略值必须是特定的 Microsoft Edge 版本，例如 83.0.499.12。</span><span class="sxs-lookup"><span data-stu-id="c43b9-338">The policy value must be a specific Microsoft Edge version, e.g. 83.0.499.12.</span></span>

<span data-ttu-id="c43b9-339">如果设备的 Microsoft Edge 版本高于指定的值，Microsoft Edge 将保留较新版本，不会降级到指定版本。</span><span class="sxs-lookup"><span data-stu-id="c43b9-339">If a device has newer version of Microsoft Edge than the value specified, Microsoft Edge will remain on the newer version and not downgrade to the specified version.</span></span>

<span data-ttu-id="c43b9-340">如果指定版本不存在，或格式不正确，Microsoft Edge 将保留当前版本，不会自动更新为未来版本。</span><span class="sxs-lookup"><span data-stu-id="c43b9-340">If the specified version does not exist, or is improperly formatted, then Microsoft Edge will remain on its current version and not update to future versions automatically.</span></span>
#### <span data-ttu-id="c43b9-341">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-341">Windows information and settings</span></span>
##### <span data-ttu-id="c43b9-342">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="c43b9-342">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c43b9-343">GP 唯一名称：TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="c43b9-343">GP unique name: TargetVersionPrefix</span></span>
- <span data-ttu-id="c43b9-344">GP 名称：目标版本覆盖</span><span class="sxs-lookup"><span data-stu-id="c43b9-344">GP name: Target version override</span></span>
- <span data-ttu-id="c43b9-345">GP 路径：</span><span class="sxs-lookup"><span data-stu-id="c43b9-345">GP path:</span></span> 
  - <span data-ttu-id="c43b9-346">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c43b9-346">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="c43b9-347">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="c43b9-347">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="c43b9-348">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="c43b9-348">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="c43b9-349">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="c43b9-349">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="c43b9-350">GP ADMX 文件名：edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c43b9-350">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c43b9-351">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-351">Windows Registry Settings</span></span>
- <span data-ttu-id="c43b9-352">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c43b9-352">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c43b9-353">值名称：</span><span class="sxs-lookup"><span data-stu-id="c43b9-353">Value Name:</span></span> 
  - <span data-ttu-id="c43b9-354">（稳定版）：TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="c43b9-354">(Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="c43b9-355">（Beta 版）： TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="c43b9-355">(Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="c43b9-356">（金丝雀版）： TargetVersionPrefix {65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="c43b9-356">(Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="c43b9-357">（开发者版本）：更新 {0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="c43b9-357">(Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="c43b9-358">值类型：REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c43b9-358">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="c43b9-359">示例值：</span><span class="sxs-lookup"><span data-stu-id="c43b9-359">Example value:</span></span>
```
83.0.499.12
```
[<span data-ttu-id="c43b9-360">返回页首</span><span class="sxs-lookup"><span data-stu-id="c43b9-360">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="c43b9-361">首选项策略</span><span class="sxs-lookup"><span data-stu-id="c43b9-361">Preferences policies</span></span>

[<span data-ttu-id="c43b9-362">返回页首</span><span class="sxs-lookup"><span data-stu-id="c43b9-362">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="c43b9-363">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="c43b9-363">AutoUpdateCheckPeriodMinutes</span></span>
#### <span data-ttu-id="c43b9-364">自动更新检查期间替代</span><span class="sxs-lookup"><span data-stu-id="c43b9-364">Auto-update check period override</span></span>
><span data-ttu-id="c43b9-365">Microsoft Edge 更新 1.2.145.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="c43b9-365">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="c43b9-366">描述</span><span class="sxs-lookup"><span data-stu-id="c43b9-366">Description</span></span>
<span data-ttu-id="c43b9-367">如果启用了此策略，你可以为各次自动更新检查间隔的最小分钟数设置一个值。</span><span class="sxs-lookup"><span data-stu-id="c43b9-367">If enabled, this policy lets you set a value for the minimum number of minutes between automatic update checks.</span></span> <span data-ttu-id="c43b9-368">否则，默认情况下，自动更新将每 10 小时检查一次更新。</span><span class="sxs-lookup"><span data-stu-id="c43b9-368">Otherwise, by default, auto-update checks for updates every 10 hours.</span></span>

  <span data-ttu-id="c43b9-369">如果你想要禁用所有自动更新检查，请将该值设置为 0（不推荐）。</span><span class="sxs-lookup"><span data-stu-id="c43b9-369">If you want to disable all auto-update checks, set the value to 0 (not recommended).</span></span>
#### <span data-ttu-id="c43b9-370">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-370">Windows information and settings</span></span>
##### <span data-ttu-id="c43b9-371">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="c43b9-371">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c43b9-372">GP 唯一名称：AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="c43b9-372">GP unique name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="c43b9-373">GP 名称：自动更新检查期间替代</span><span class="sxs-lookup"><span data-stu-id="c43b9-373">GP name: Auto-update check period override</span></span>
- <span data-ttu-id="c43b9-374">GP 路径：Administrative Templates/Microsoft Edge Update/Preferences</span><span class="sxs-lookup"><span data-stu-id="c43b9-374">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="c43b9-375">GP ADMX 文件名：edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c43b9-375">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c43b9-376">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-376">Windows Registry Settings</span></span>
- <span data-ttu-id="c43b9-377">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c43b9-377">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c43b9-378">值名称：AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="c43b9-378">Value Name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="c43b9-379">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c43b9-379">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="c43b9-380">示例值：</span><span class="sxs-lookup"><span data-stu-id="c43b9-380">Example value:</span></span>
```
0x00000578
```
[<span data-ttu-id="c43b9-381">返回页首</span><span class="sxs-lookup"><span data-stu-id="c43b9-381">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="c43b9-382">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="c43b9-382">UpdatesSuppressed</span></span>
#### <span data-ttu-id="c43b9-383">每天中取消自动更新检查的时间段</span><span class="sxs-lookup"><span data-stu-id="c43b9-383">Time period in each day to suppress auto-update check</span></span>
><span data-ttu-id="c43b9-384">Microsoft Edge 更新 1.3.33.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="c43b9-384">Microsoft Edge Update 1.3.33.5 and later</span></span>

#### <span data-ttu-id="c43b9-385">描述</span><span class="sxs-lookup"><span data-stu-id="c43b9-385">Description</span></span>
<span data-ttu-id="c43b9-386">如果你启用此策略，则每天都会从 Hour:Minute 开始持续一段时间（以分钟为单位）禁止更新检查。</span><span class="sxs-lookup"><span data-stu-id="c43b9-386">If you enable this policy, update checks are suppressed each day starting at Hour:Minute for a period of Duration (in minutes).</span></span> <span data-ttu-id="c43b9-387">持续时间不受夏令时影响。</span><span class="sxs-lookup"><span data-stu-id="c43b9-387">Duration isn't affected by daylight saving time.</span></span> <span data-ttu-id="c43b9-388">例如，如果开始时间是 22:00，持续时间为 480 分钟，则无论夏令时是在此期间开始还是结束，更新都将正好禁止 8 小时。</span><span class="sxs-lookup"><span data-stu-id="c43b9-388">For example, if the start time is 22:00 and the duration is 480 minutes, updates will be suppressed for exactly 8 hours, regardless of whether daylight saving time starts or ends during this period.</span></span>

  <span data-ttu-id="c43b9-389">如果你禁用或未配置此策略，则不会在任何特定期间取消更新检查。</span><span class="sxs-lookup"><span data-stu-id="c43b9-389">If you disable or don't configure this policy, update checks aren't suppressed during any specific period.</span></span>
#### <span data-ttu-id="c43b9-390">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-390">Windows information and settings</span></span>
##### <span data-ttu-id="c43b9-391">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="c43b9-391">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c43b9-392">GP 唯一名称：UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="c43b9-392">GP unique name: UpdatesSuppressed</span></span>
- <span data-ttu-id="c43b9-393">GP 名称：每天中取消自动更新检查的时间段</span><span class="sxs-lookup"><span data-stu-id="c43b9-393">GP name: Time period in each day to suppress auto-update check</span></span>
  - <span data-ttu-id="c43b9-394">选项 { Hour, Minute, Duration }</span><span class="sxs-lookup"><span data-stu-id="c43b9-394">Options { Hour, Minute, Duration }</span></span>
- <span data-ttu-id="c43b9-395">GP 路径：Administrative Templates/Microsoft Edge Update/Preferences</span><span class="sxs-lookup"><span data-stu-id="c43b9-395">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="c43b9-396">GP ADMX 文件名：edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c43b9-396">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c43b9-397">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-397">Windows Registry Settings</span></span>
- <span data-ttu-id="c43b9-398">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c43b9-398">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c43b9-399">值名称：</span><span class="sxs-lookup"><span data-stu-id="c43b9-399">Value Name:</span></span> 
  - <span data-ttu-id="c43b9-400">UpdatesSuppressedDurationMin</span><span class="sxs-lookup"><span data-stu-id="c43b9-400">UpdatesSuppressedDurationMin</span></span>
  - <span data-ttu-id="c43b9-401">UpdatesSuppressedStartHour</span><span class="sxs-lookup"><span data-stu-id="c43b9-401">UpdatesSuppressedStartHour</span></span>
  - <span data-ttu-id="c43b9-402">UpdatesSuppressedStartMin</span><span class="sxs-lookup"><span data-stu-id="c43b9-402">UpdatesSuppressedStartMin</span></span>
- <span data-ttu-id="c43b9-403">值类型：REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c43b9-403">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="c43b9-404">示例值：</span><span class="sxs-lookup"><span data-stu-id="c43b9-404">Example value:</span></span>
```
duration   : 0x0000003c
start hour : 0x00000001
start min  : 0x00000002
```
[<span data-ttu-id="c43b9-405">返回页首</span><span class="sxs-lookup"><span data-stu-id="c43b9-405">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="c43b9-406">代理服务器策略</span><span class="sxs-lookup"><span data-stu-id="c43b9-406">Proxy Server policies</span></span>
  
  

[<span data-ttu-id="c43b9-407">返回页首</span><span class="sxs-lookup"><span data-stu-id="c43b9-407">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="c43b9-408">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="c43b9-408">ProxyMode</span></span>
#### <span data-ttu-id="c43b9-409">选择指定代理服务器设置的方式</span><span class="sxs-lookup"><span data-stu-id="c43b9-409">Choose how to specify proxy server settings</span></span>
><span data-ttu-id="c43b9-410">Microsoft Edge 更新 1.3.21.81 和更高版本</span><span class="sxs-lookup"><span data-stu-id="c43b9-410">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="c43b9-411">描述</span><span class="sxs-lookup"><span data-stu-id="c43b9-411">Description</span></span>
<span data-ttu-id="c43b9-412">允许你指定 Microsoft Edge 更新使用的代理服务器设置。</span><span class="sxs-lookup"><span data-stu-id="c43b9-412">Allows you to specify the proxy server settings that are used by Microsoft Edge Update.</span></span>

  <span data-ttu-id="c43b9-413">如果你启用此策略，则可以在以下代理服务器选项之间进行选择：</span><span class="sxs-lookup"><span data-stu-id="c43b9-413">If you enable this policy, you can choose between the following proxy server options:</span></span>
   - <span data-ttu-id="c43b9-414">如果你选择从不使用代理服务器并且始终直接连接，则所有其他选项都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="c43b9-414">If you choose to never use a proxy server and always connect directly, all other options are ignored.</span></span>
   - <span data-ttu-id="c43b9-415">如果你选择使用系统代理设置或自动检测代理服务器，则所有其他选项都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="c43b9-415">If you choose to use system proxy settings or auto-detect the proxy server, all other options are ignored.</span></span>
   - <span data-ttu-id="c43b9-416">如果你选择固定服务器代理模式，则可以在 “[代理服务器的地址或 URL](#proxyserver)” 策略中指定更多选项。</span><span class="sxs-lookup"><span data-stu-id="c43b9-416">If you choose fixed server proxy mode, you can specify further options in '[Address or URL of proxy server](#proxyserver)' policy.</span></span>
   - <span data-ttu-id="c43b9-417">如果你选择使用 .pac 代理脚本，则必须在 “[代理 .pac 文件的 URL](#proxypacurl)”策略中为脚本指定 URL。</span><span class="sxs-lookup"><span data-stu-id="c43b9-417">If you choose to use a .pac proxy script, you must specify the URL for the script in '[URL to a proxy .pac file](#proxypacurl)' policy.</span></span>

  <span data-ttu-id="c43b9-418">如果你启用此策略，则你所在组织中的用户无法在 Microsoft Edge 更新中更改代理设置。</span><span class="sxs-lookup"><span data-stu-id="c43b9-418">If you enable this policy, users in your organization can't change the proxy settings in Microsoft Edge Update.</span></span>

  <span data-ttu-id="c43b9-419">如果你禁用或未配置此策略，则不会配置任何代理服务器设置，但组织中的用户可以为 Microsoft Edge 更新选择自己的代理设置。</span><span class="sxs-lookup"><span data-stu-id="c43b9-419">If you disable or don't configure this policy, no proxy server settings are configured, but users in your organization can choose their own proxy settings for Microsoft Edge Update.</span></span>
#### <span data-ttu-id="c43b9-420">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-420">Windows information and settings</span></span>
##### <span data-ttu-id="c43b9-421">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="c43b9-421">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c43b9-422">GP 唯一名称：ProxyMode</span><span class="sxs-lookup"><span data-stu-id="c43b9-422">GP unique name: ProxyMode</span></span>
- <span data-ttu-id="c43b9-423">GP 名称：选择指定代理服务器设置的方式</span><span class="sxs-lookup"><span data-stu-id="c43b9-423">GP name: Choose how to specify proxy server settings</span></span>
- <span data-ttu-id="c43b9-424">GP 路径：Administrative Templates/Microsoft Edge Update/Proxy Server</span><span class="sxs-lookup"><span data-stu-id="c43b9-424">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="c43b9-425">GP ADMX 文件名：edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c43b9-425">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c43b9-426">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-426">Windows Registry Settings</span></span>
- <span data-ttu-id="c43b9-427">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c43b9-427">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c43b9-428">值名称：ProxyMode</span><span class="sxs-lookup"><span data-stu-id="c43b9-428">Value Name: ProxyMode</span></span>
- <span data-ttu-id="c43b9-429">值类型：REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c43b9-429">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="c43b9-430">示例值：</span><span class="sxs-lookup"><span data-stu-id="c43b9-430">Example value:</span></span>
```
fixed_servers
```
[<span data-ttu-id="c43b9-431">返回页首</span><span class="sxs-lookup"><span data-stu-id="c43b9-431">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="c43b9-432">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="c43b9-432">ProxyPacUrl</span></span>
#### <span data-ttu-id="c43b9-433">代理 .pac 文件的 URL</span><span class="sxs-lookup"><span data-stu-id="c43b9-433">URL to a proxy .pac file</span></span>
><span data-ttu-id="c43b9-434">Microsoft Edge 更新 1.3.21.81 和更高版本</span><span class="sxs-lookup"><span data-stu-id="c43b9-434">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="c43b9-435">描述</span><span class="sxs-lookup"><span data-stu-id="c43b9-435">Description</span></span>
<span data-ttu-id="c43b9-436">允许你为代理自动配置 (PAC) 文件指定 URL。</span><span class="sxs-lookup"><span data-stu-id="c43b9-436">Allows you to specify a URL for a proxy auto-config (PAC) file.</span></span>

  <span data-ttu-id="c43b9-437">如果你启用此策略，则可以为 PAC 文件指定 URL，以自动执行 Microsoft Edge 更新为提取特定网站而选择合适代理服务器的方法。</span><span class="sxs-lookup"><span data-stu-id="c43b9-437">If you enable this policy, you can specify a URL for a PAC file to automate how Microsoft Edge Update selects the appropriate proxy server for fetching a particular website.</span></span>

  <span data-ttu-id="c43b9-438">仅当你已在“[选择如何指定代理服务器设置](#proxymode)”策略中指定了手动代理设置时，才会应用此策略。</span><span class="sxs-lookup"><span data-stu-id="c43b9-438">This policy is applied only if you have specified manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="c43b9-439">如果你已在“[选择如何指定代理服务器设置](#proxymode)”策略中选择了手动设置以外的其他代理设置，请不要配置此策略。</span><span class="sxs-lookup"><span data-stu-id="c43b9-439">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <span data-ttu-id="c43b9-440">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-440">Windows information and settings</span></span>
##### <span data-ttu-id="c43b9-441">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="c43b9-441">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c43b9-442">GP 唯一名称：ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="c43b9-442">GP unique name: ProxyPacUrl</span></span>
- <span data-ttu-id="c43b9-443">GP 名称：代理 .pac 文件的 URL</span><span class="sxs-lookup"><span data-stu-id="c43b9-443">GP name: URL to a proxy .pac file</span></span>
- <span data-ttu-id="c43b9-444">GP 路径：Administrative Templates/Microsoft Edge Update/Proxy Server</span><span class="sxs-lookup"><span data-stu-id="c43b9-444">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="c43b9-445">GP ADMX 文件名：edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c43b9-445">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c43b9-446">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-446">Windows Registry Settings</span></span>
- <span data-ttu-id="c43b9-447">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c43b9-447">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c43b9-448">值名称：ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="c43b9-448">Value Name: ProxyPacUrl</span></span>
- <span data-ttu-id="c43b9-449">值类型：REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c43b9-449">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="c43b9-450">示例值：</span><span class="sxs-lookup"><span data-stu-id="c43b9-450">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="c43b9-451">返回页首</span><span class="sxs-lookup"><span data-stu-id="c43b9-451">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="c43b9-452">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="c43b9-452">ProxyServer</span></span>
#### <span data-ttu-id="c43b9-453">代理服务器的地址或 URL</span><span class="sxs-lookup"><span data-stu-id="c43b9-453">Address or URL of proxy server</span></span>
><span data-ttu-id="c43b9-454">Microsoft Edge 更新 1.3.21.81 和更高版本</span><span class="sxs-lookup"><span data-stu-id="c43b9-454">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="c43b9-455">说明</span><span class="sxs-lookup"><span data-stu-id="c43b9-455">Description</span></span>
<span data-ttu-id="c43b9-456">允许你指定供 Microsoft Edge 更新使用的代理服务器的 URL。</span><span class="sxs-lookup"><span data-stu-id="c43b9-456">Allows you to specify the URL of the proxy server for Microsoft Edge Update to use.</span></span>

  <span data-ttu-id="c43b9-457">如果启用此策略，则可以设置组织中 Microsoft Edge 更新使用的代理服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="c43b9-457">If you enable this policy, you can set the proxy server URL used by Microsoft Edge Update in your organization.</span></span>

  <span data-ttu-id="c43b9-458">仅当你已在[“选择如何指定代理服务器设置”](#proxymode)策略中选择了手动代理设置时，才会应用此策略。</span><span class="sxs-lookup"><span data-stu-id="c43b9-458">This policy is applied only if you have selected manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="c43b9-459">如果你已在“[选择如何指定代理服务器设置](#proxymode)”策略中选择了手动设置以外的其他代理设置，请不要配置此策略。</span><span class="sxs-lookup"><span data-stu-id="c43b9-459">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <span data-ttu-id="c43b9-460">Windows 信息和设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-460">Windows information and settings</span></span>
##### <span data-ttu-id="c43b9-461">组策略 (ADMX) 信息</span><span class="sxs-lookup"><span data-stu-id="c43b9-461">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="c43b9-462">GP 唯一名称：ProxyServer</span><span class="sxs-lookup"><span data-stu-id="c43b9-462">GP unique name: ProxyServer</span></span>
- <span data-ttu-id="c43b9-463">GP 名称：代理服务器的地址或 URL</span><span class="sxs-lookup"><span data-stu-id="c43b9-463">GP name: Address or URL of proxy server</span></span>
- <span data-ttu-id="c43b9-464">GP 路径：Administrative Templates/Microsoft Edge Update/Proxy Server</span><span class="sxs-lookup"><span data-stu-id="c43b9-464">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="c43b9-465">GP ADMX 文件名：edgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="c43b9-465">GP ADMX file name: edgeupdate.admx</span></span>
##### <span data-ttu-id="c43b9-466">Windows 注册表设置</span><span class="sxs-lookup"><span data-stu-id="c43b9-466">Windows Registry Settings</span></span>
- <span data-ttu-id="c43b9-467">路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="c43b9-467">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="c43b9-468">值名称：ProxyServer</span><span class="sxs-lookup"><span data-stu-id="c43b9-468">Value Name: ProxyServer</span></span>
- <span data-ttu-id="c43b9-469">值类型：REG_SZ</span><span class="sxs-lookup"><span data-stu-id="c43b9-469">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="c43b9-470">示例值：</span><span class="sxs-lookup"><span data-stu-id="c43b9-470">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="c43b9-471">返回页首</span><span class="sxs-lookup"><span data-stu-id="c43b9-471">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="c43b9-472">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c43b9-472">See also</span></span>
  - [<span data-ttu-id="c43b9-473">配置 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c43b9-473">Configuring Microsoft Edge</span></span>](configure-microsoft-edge.md)
  - [<span data-ttu-id="c43b9-474">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="c43b9-474">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
