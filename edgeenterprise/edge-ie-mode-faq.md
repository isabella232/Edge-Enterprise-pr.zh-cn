---
title: IE 模式 FAQ
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 03/15/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 关于结合使用 Microsoft Edge 和 IE 模式的 FAQ 和故障排除
ms.openlocfilehash: f5279caddb5d3dfabaf04be6bd927f7095be1fc9
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447726"
---
# <a name="ie-mode-faq"></a><span data-ttu-id="c284b-103">IE 模式 FAQ</span><span class="sxs-lookup"><span data-stu-id="c284b-103">IE mode FAQ</span></span>

<span data-ttu-id="c284b-104">本文介绍了 Microsoft Edge 版本 77 或更高版本的故障排除提示和 FAQ。</span><span class="sxs-lookup"><span data-stu-id="c284b-104">This article provides troubleshooting tips and an FAQ for Microsoft Edge version 77 or later.</span></span>

> [!NOTE]
> <span data-ttu-id="c284b-105">本文适用于 Microsoft Edge **Stable**、**Beta** 和 **Dev** 渠道版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="c284b-105">This article applies to Microsoft Edge **Stable**, **Beta** and **Dev** Channels, version 77 or later.</span></span>


## <a name="troubleshoot-ie-mode"></a><span data-ttu-id="c284b-106">IE 模式疑难解答</span><span class="sxs-lookup"><span data-stu-id="c284b-106">Troubleshoot IE mode</span></span>

<span data-ttu-id="c284b-107">使用此部分中的信息诊断和修复 IE 模式问题。</span><span class="sxs-lookup"><span data-stu-id="c284b-107">Use the information in this section to diagnose and fix IE mode problems.</span></span>

### <a name="internet-explorer-mode-diagnostic-information"></a><span data-ttu-id="c284b-108">Internet Explorer 模式诊断信息</span><span class="sxs-lookup"><span data-stu-id="c284b-108">Internet Explorer mode diagnostic information</span></span>

<span data-ttu-id="c284b-109">可以在 Microsoft Edge 的“兼容性”选项卡上获取 Internet Explorer 模式诊断信息。若要打开此选项卡，请转到 *edge://compat/iediagnostic*。</span><span class="sxs-lookup"><span data-stu-id="c284b-109">You can get Internet Explorer mode diagnostic information on the Microsoft Edge Compatibility tab. To open this tab, go to *edge://compat/iediagnostic*.</span></span> <span data-ttu-id="c284b-110">此页面可能会显示诊断消息。</span><span class="sxs-lookup"><span data-stu-id="c284b-110">This page may show diagnostic messages.</span></span> <span data-ttu-id="c284b-111">此页面还显示以下类别的配置信息：</span><span class="sxs-lookup"><span data-stu-id="c284b-111">This page also provides configuration information for the following categories:</span></span>

- <span data-ttu-id="c284b-112">**注册表项检查**。</span><span class="sxs-lookup"><span data-stu-id="c284b-112">**Registry key check**.</span></span> <span data-ttu-id="c284b-113">（仅在检查失败时才显示。）检查是否在注册表中正确设置了 Internet Explorer 集成。</span><span class="sxs-lookup"><span data-stu-id="c284b-113">(Displayed only if the check fails.) Checks to see if Internet Explorer integration is set up correctly in the registry.</span></span> <span data-ttu-id="c284b-114">如果没有正确设置，用户可以单击“修复”\*\*\*\* 来解决问题。</span><span class="sxs-lookup"><span data-stu-id="c284b-114">If not, the user can click **Fix it** to resolve the problem.</span></span>
- <span data-ttu-id="c284b-115">**Internet Explorer 模式**。</span><span class="sxs-lookup"><span data-stu-id="c284b-115">**Internet Explorer mode**.</span></span> <span data-ttu-id="c284b-116">根据配置和操作系统来显示使用的 API 版本。</span><span class="sxs-lookup"><span data-stu-id="c284b-116">Shows the API version that's used, based on the configuration and OS.</span></span> <span data-ttu-id="c284b-117">如果无法显示，系统可能会提示用户安装 **Windows 更新**。</span><span class="sxs-lookup"><span data-stu-id="c284b-117">If there's a problem, the user may be prompted to install a **Windows Update**.</span></span>
- <span data-ttu-id="c284b-118">**Internet Explorer 模式设置**。</span><span class="sxs-lookup"><span data-stu-id="c284b-118">**Internet Explorer mode setting**.</span></span> <span data-ttu-id="c284b-119">显示 Internet Explorer 模式是否已启用，以及是如何配置的。</span><span class="sxs-lookup"><span data-stu-id="c284b-119">Shows whether Internet Explorer mode is enabled, and how it's configured.</span></span>
- <span data-ttu-id="c284b-120">**命令行**。</span><span class="sxs-lookup"><span data-stu-id="c284b-120">**Command line**.</span></span> <span data-ttu-id="c284b-121">显示用于启动 Microsoft Edge 的命令行字符串和开关。</span><span class="sxs-lookup"><span data-stu-id="c284b-121">Shows the command line string and switches used to start Microsoft Edge.</span></span>
- <span data-ttu-id="c284b-122">**组策略设置**。</span><span class="sxs-lookup"><span data-stu-id="c284b-122">**Group policy settings**.</span></span> <span data-ttu-id="c284b-123">显示 IE 模式是否是使用组策略配置的，以及应用的策略。</span><span class="sxs-lookup"><span data-stu-id="c284b-123">Shows whether IE mode is configured using group policies, and the policies that are applied.</span></span>

### <a name="error-message-to-open-this-page-in-internet-explorer-mode-reinstall-microsoft-edge-with-administrator-privileges"></a><span data-ttu-id="c284b-124">错误消息：“要在 Internet Explorer 模式下打开此页面，请使用管理员权限重新安装 Microsoft Edge。”</span><span class="sxs-lookup"><span data-stu-id="c284b-124">Error message: "To open this page in Internet Explorer mode, reinstall Microsoft Edge with administrator privileges."</span></span>

<span data-ttu-id="c284b-125">如果没有安装所有必需 Windows 更新，可能会看到此错误。</span><span class="sxs-lookup"><span data-stu-id="c284b-125">You may see this error if you don't have all required Windows Updates.</span></span> <span data-ttu-id="c284b-126">有关必需 Windows 和 Microsoft Edge 版本，请参阅[关于 IE 模式](./edge-ie-mode.md)中列出的先决条件。</span><span class="sxs-lookup"><span data-stu-id="c284b-126">See the prerequisites listed in [About IE mode](./edge-ie-mode.md) for the required versions of Windows and Microsoft Edge.</span></span>

<span data-ttu-id="c284b-127">如果已安装所有必需 Windows 更新，但仍可能会在以下情况下看到此错误：</span><span class="sxs-lookup"><span data-stu-id="c284b-127">If you've already installed all required Windows Updates, you may see this error if:</span></span>

- <span data-ttu-id="c284b-128">你使用的是 Canary 渠道（默认安装在用户级别）。</span><span class="sxs-lookup"><span data-stu-id="c284b-128">You're using the Canary channel, which is installed at the user level by default.</span></span>
- <span data-ttu-id="c284b-129">你使用的是稳定渠道、Beta 渠道或 Dev 渠道，但在安装期间看到提升权限提示时，提升权限被取消了。</span><span class="sxs-lookup"><span data-stu-id="c284b-129">You're using the Stable, Beta, or Dev channel, but when prompted for elevation when installing the elevation was canceled.</span></span> <span data-ttu-id="c284b-130">如果你取消提升权限提示，安装将继续在用户级别进行。</span><span class="sxs-lookup"><span data-stu-id="c284b-130">When you cancel the elevation prompt, the installation will continue at the user level.</span></span>
- <span data-ttu-id="c284b-131">已在 Windows 功能中禁用 Internet Explorer 11。</span><span class="sxs-lookup"><span data-stu-id="c284b-131">Internet Explorer 11 has been disabled in Windows Features.</span></span>

<span data-ttu-id="c284b-132">可能的解决方案：</span><span class="sxs-lookup"><span data-stu-id="c284b-132">Possible solutions:</span></span>

- <span data-ttu-id="c284b-133">在系统级别针对任意渠道运行安装程序：`installer.exe --system-level`。</span><span class="sxs-lookup"><span data-stu-id="c284b-133">Run the installer for any channel at the system level: `installer.exe --system-level`.</span></span>
- <span data-ttu-id="c284b-134">在 Windows 功能中启用 Internet Explorer 11。</span><span class="sxs-lookup"><span data-stu-id="c284b-134">Enable Internet Explorer 11 in Windows Features.</span></span>

<span data-ttu-id="c284b-135">若要检查 Microsoft Edge 是否安装在系统级别，请在 Microsoft Edge 地址栏中键入“edge://version”。</span><span class="sxs-lookup"><span data-stu-id="c284b-135">To check if Microsoft Edge is installed at the systems level, type "edge://version" in the Microsoft Edge address bar.</span></span> <span data-ttu-id="c284b-136">“可执行文件路径”将会显示以“C:\Program Files”\*\* 开头的路径，这就表示是系统安装。</span><span class="sxs-lookup"><span data-stu-id="c284b-136">The Executable path will show a path starting with *C:\Program Files*, which indicates a system install.</span></span> <span data-ttu-id="c284b-137">如果“可执行文件路径”以“C:\Users\”\*\*开头，请使用管理员特权卸载并重新安装 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="c284b-137">If the Executable path begins with \*C:\Users\*, uninstall and then reinstall Microsoft Edge with administrator privileges.</span></span>

### <a name="error-message-to-open-this-page-in-ie-mode-try-restarting-microsoft-edge"></a><span data-ttu-id="c284b-138">错误消息：“要在 IE 模式下打开此页面，请尝试重启 Microsoft Edge。”</span><span class="sxs-lookup"><span data-stu-id="c284b-138">Error message: "To open this page in IE mode, try restarting Microsoft Edge."</span></span>

<span data-ttu-id="c284b-139">如果 Internet Explorer 中出现意外错误，你可能就会看到此错误。</span><span class="sxs-lookup"><span data-stu-id="c284b-139">You may see this error if there was an unexpected error in Internet Explorer.</span></span> <span data-ttu-id="c284b-140">重启 Microsoft Edge 通常可以修复此错误。</span><span class="sxs-lookup"><span data-stu-id="c284b-140">Restarting Microsoft Edge usually fixes this error.</span></span>

### <a name="error-message-turn-off-remote-debugging-to-open-this-site-in-ie-mode-otherwise-it-might-not-work-as-expected"></a><span data-ttu-id="c284b-141">错误消息：“关闭远程调试以在 IE 模式下打开此站点，否则可能无法正常工作。”</span><span class="sxs-lookup"><span data-stu-id="c284b-141">Error message: "Turn off remote debugging to open this site in IE mode otherwise it might not work as expected."</span></span>

<span data-ttu-id="c284b-142">如果你正在进行远程调试，并导航到配置为在 IE 模式下运行的网页，可能就会看到此错误。</span><span class="sxs-lookup"><span data-stu-id="c284b-142">You may see this error if you're remote debugging and navigate to a web page configured to run in IE mode.</span></span> <span data-ttu-id="c284b-143">你可以继续操作，但网页会使用 Microsoft Edge 呈现。</span><span class="sxs-lookup"><span data-stu-id="c284b-143">You can continue, but the page will be rendered using Microsoft Edge.</span></span>

### <a name="error-message-error-could-not-retrieve-emie-site-list"></a><span data-ttu-id="c284b-144">错误消息：“错误：无法检索 EMIE 站点列表。”</span><span class="sxs-lookup"><span data-stu-id="c284b-144">Error message: "Error: Could not retrieve EMIE site list."</span></span>

<span data-ttu-id="c284b-145">您可能会在 *edge://compat/enterprise* 页面上看到此错误，表示站点列表下载失败。</span><span class="sxs-lookup"><span data-stu-id="c284b-145">You may see this error on the *edge://compat/enterprise* page indicating that the site list download failed.</span></span> <span data-ttu-id="c284b-146">从 Microsoft Edge 版本 87 开始，当使用 [BlockThirdPartyCookies](./microsoft-edge-policies.md#blockthirdpartycookies) 策略阻止第三方请求的Cookie 时，也不允许使用 HTTP 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c284b-146">Starting with Microsoft Edge version 87, when cookies are blocked for third party requests using the [BlockThirdPartyCookies](./microsoft-edge-policies.md#blockthirdpartycookies) policy, HTTP authentication is also disallowed.</span></span> <span data-ttu-id="c284b-147">可以使用 [CookiesAllowedForURLs](./microsoft-edge-policies.md#cookiesallowedforurls) 策略为托管 Enterprise Mode Site List 的特定域允许 Cookie，以确保站点列表下载成功。</span><span class="sxs-lookup"><span data-stu-id="c284b-147">You can allow cookies for the specific domain hosting your Enterprise Mode Site List using the [CookiesAllowedForURLs](./microsoft-edge-policies.md#cookiesallowedforurls) policy to ensure that site list downloads are successful.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c284b-148">常见问题</span><span class="sxs-lookup"><span data-stu-id="c284b-148">Frequently Asked Questions</span></span>

### <a name="will-ie-mode-replace-internet-explorer-11"></a><span data-ttu-id="c284b-149">IE 模式是否将替换 Internet Explorer 11？</span><span class="sxs-lookup"><span data-stu-id="c284b-149">Will IE mode replace Internet Explorer 11?</span></span>

<span data-ttu-id="c284b-150">我们致力于使 Internet Explorer 成为受支持、可靠和安全的浏览器。</span><span class="sxs-lookup"><span data-stu-id="c284b-150">We're committed to keeping Internet Explorer a supported, reliable, and safe browser.</span></span> <span data-ttu-id="c284b-151">Internet Explorer 仍然是 Windows 的组件，并遵循其安装所在操作系统的支持生命周期。</span><span class="sxs-lookup"><span data-stu-id="c284b-151">Internet Explorer is still a component of Windows and follows the support lifecycle of the OS on which it's installed.</span></span> <span data-ttu-id="c284b-152">有关详细信息，请参阅[生命周期常见问题解答 - Internet Explorer](https://support.microsoft.com/help/17454/)。</span><span class="sxs-lookup"><span data-stu-id="c284b-152">For details, see [Lifecycle FAQ - Internet Explorer](https://support.microsoft.com/help/17454/).</span></span> <span data-ttu-id="c284b-153">尽管 Microsoft 会继续支持和更新 Internet Explorer，但最新功能和平台更新将仅在 Microsoft Edge 中提供。</span><span class="sxs-lookup"><span data-stu-id="c284b-153">While Microsoft continues to support and update Internet Explorer, the latest features and platform updates will only be available in Microsoft Edge.</span></span>

### <a name="can-i-use-open-with-explorer-or-view-in-file-explorer-in-sharepoint-with-ie-mode"></a><span data-ttu-id="c284b-154">是否可在 IE 模式下的 SharePoint 中使用“使用资源管理器打开”或“在文件资源管理器中查看”？</span><span class="sxs-lookup"><span data-stu-id="c284b-154">Can I use "Open with Explorer" or "View in File Explorer" in SharePoint with IE mode?</span></span>

<span data-ttu-id="c284b-155">能，如果这适用于独立 Internet Explorer 11，则也适用于 IE 模式。</span><span class="sxs-lookup"><span data-stu-id="c284b-155">Yes, if this works in standalone Internet Explorer 11 it will work in IE mode.</span></span> <span data-ttu-id="c284b-156">不过，若要管理 SharePoint 外部文件和文件夹，推荐方法是[同步 SharePoint 文件](https://support.office.com/en-us/article/sync-sharepoint-files-with-the-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)或[在 SharePoint 中移动或复制文件](https://support.office.com/en-us/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc)，而不是使用“使用资源管理器打开”选项。</span><span class="sxs-lookup"><span data-stu-id="c284b-156">However, rather than use the Open with Explorer option, the recommended approach to managing files and folders outside of SharePoint is to [sync your SharePoint files](https://support.office.com/en-us/article/sync-sharepoint-files-with-the-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88) or [move or copy files in SharePoint](https://support.office.com/en-us/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc).</span></span>

### <a name="does-ie-mode-on-microsoft-edge-support-the-nomerge-option-that-was-supported-in-internet-explorer-11"></a><span data-ttu-id="c284b-157">Microsoft Edge 上的 IE 模式是否支持 Internet Explorer 11中支持的 *nomerge* 选项？</span><span class="sxs-lookup"><span data-stu-id="c284b-157">Does IE mode on Microsoft Edge support the *nomerge* option that was supported in Internet Explorer 11?</span></span>

<span data-ttu-id="c284b-158">在 Microsoft Edge 中没有明确的命令行来镜像 *nomerge* 选项，但是我们建议使用两种替代方法来提供此功能。</span><span class="sxs-lookup"><span data-stu-id="c284b-158">There is no explicit command line in Microsoft Edge to mirror the *nomerge* option, but there are a couple of alternatives that we recommend to provide this functionality.</span></span>

1. <span data-ttu-id="c284b-159">在 Microsoft Edge 中使用配置文件-每个配置文件对用 IE 模式页面的不同 IE 会话，因此其行为与 *nomerge* 选项相同。</span><span class="sxs-lookup"><span data-stu-id="c284b-159">Use Profiles in Microsoft Edge - Each profile maps to a different IE session for IE mode pages, so it behaves identically to the *nomerge* option.</span></span>
2. <span data-ttu-id="c284b-160">使用`--user-data-dir=<path>`命令行，但每个会话的路径不同。</span><span class="sxs-lookup"><span data-stu-id="c284b-160">Use the `--user-data-dir=<path>` command line, but with a different path for each session.</span></span> <span data-ttu-id="c284b-161">如果需要，可以创建一个既可以启动 Microsoft Edge，也可以更改会话的路径的实用程序供用户运行。</span><span class="sxs-lookup"><span data-stu-id="c284b-161">If needed, you can create a utility for the user to run that both launches Microsoft Edge and changes the path for the session.</span></span>

<span data-ttu-id="c284b-162">如果以上两个选项都不适用于你的情况，请通过其中一个反馈渠道联系我们：Microsoft 支持或 [TechCommunity 论坛](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise)。</span><span class="sxs-lookup"><span data-stu-id="c284b-162">If neither of the above options works for your scenario, reach out through one of our feedback channels:  Microsoft support or [TechCommunity forum](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise).</span></span>

### <a name="can-i-save-links-as-webpages-in-internet-explorer-mode"></a><span data-ttu-id="c284b-163">我能否将链接另存为 Internet Explorer 模式的网页？</span><span class="sxs-lookup"><span data-stu-id="c284b-163">Can I save links as webpages in Internet Explorer mode?</span></span>

<span data-ttu-id="c284b-164">可以，可以在 Microsoft Edge 中的 Internet Explorer 模式下在在上下文菜单中启用“目标另存为”选项。</span><span class="sxs-lookup"><span data-stu-id="c284b-164">Yes, you can enable the Save Target As option in the context menu for Internet Explorer mode in Microsoft Edge.</span></span> <span data-ttu-id="c284b-165">为此，请配置组策略 *"允许在 Internet Explorer 模式下将目标另存为"*，该策略位于 *“计算机配置>“管理模板”>“Windows 组件”>”Internet Explorer”*。</span><span class="sxs-lookup"><span data-stu-id="c284b-165">To do this, configure the group policy *"Allow Save Target As in Internet Explorer mode"* located at *Computer Configuration > Administrative Templates > Windows Components > Internet Explorer*.</span></span>
<span data-ttu-id="c284b-166">保存机制的工作方式与在 Internet Explorer 中相同，并且如果目标另存为 html 文件，重新打开文件将在 Microsoft Edge 中呈现页面。</span><span class="sxs-lookup"><span data-stu-id="c284b-166">The save mechanism works the same as it does in Internet Explorer and if the target is saved as an html file, re-opening the file will render the page in Microsoft Edge.</span></span>
 
<span data-ttu-id="c284b-167">请注意，此功能需要以下最低要求的操作系统更新：</span><span class="sxs-lookup"><span data-stu-id="c284b-167">Note that this functionality requires the following minimum operating system updates:</span></span>
- <span data-ttu-id="c284b-168">Windows 10 版本 2004、Windows Server 版本 2004、Windows 10 版本 20H2：[KB4580364](https://support.microsoft.com/help/4580364/windows-10-update-kb4580364)</span><span class="sxs-lookup"><span data-stu-id="c284b-168">Windows 10, version 2004, Windows Server version 2004, Windows 10, version 20H2 : [KB4580364](https://support.microsoft.com/help/4580364/windows-10-update-kb4580364)</span></span>
- <span data-ttu-id="c284b-169">Windows 10 版本 1903、Windows 10 版本 1909、Windows Server 版本 1903：[KB4580386](https://support.microsoft.com/help/4580386/windows-10-update-kb4580386)</span><span class="sxs-lookup"><span data-stu-id="c284b-169">Windows 10, version 1903, Windows 10, version 1909, Windows Server version 1903: [KB4580386](https://support.microsoft.com/help/4580386/windows-10-update-kb4580386)</span></span>
- <span data-ttu-id="c284b-170">Windows 10 版本 1809、Windows Server 版本 1809、Windows Server 2019：[KB4580390](https://support.microsoft.com/help/4580390/windows-10-update-kb4580390)</span><span class="sxs-lookup"><span data-stu-id="c284b-170">Windows 10, version 1809, Windows Server version 1809, Windows Server 2019: [KB4580390](https://support.microsoft.com/help/4580390/windows-10-update-kb4580390)</span></span>
- <span data-ttu-id="c284b-171">Windows 10 版本 1803：[KB4586785](https://support.microsoft.com/help/4586785/windows-10-update-kb4586785)</span><span class="sxs-lookup"><span data-stu-id="c284b-171">Windows 10, version 1803: [KB4586785](https://support.microsoft.com/help/4586785/windows-10-update-kb4586785)</span></span>
- <span data-ttu-id="c284b-172">Windows 10 版本 1607：[KB4586830](https://support.microsoft.com/help/4586830/windows-10-update-kb4586830)</span><span class="sxs-lookup"><span data-stu-id="c284b-172">Windows 10, version 1607: [KB4586830](https://support.microsoft.com/help/4586830/windows-10-update-kb4586830)</span></span>
- <span data-ttu-id="c284b-173">Windows 10 版本 1507：[KB4586787](https://support.microsoft.com/help/4586787/windows-10-update-kb4586787)</span><span class="sxs-lookup"><span data-stu-id="c284b-173">Windows 10, version 1507: [KB4586787](https://support.microsoft.com/help/4586787/windows-10-update-kb4586787)</span></span>


## <a name="see-also"></a><span data-ttu-id="c284b-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c284b-174">See also</span></span>

- [<span data-ttu-id="c284b-175">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="c284b-175">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="c284b-176">关于 IE 模式</span><span class="sxs-lookup"><span data-stu-id="c284b-176">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="c284b-177">其他企业模式信息</span><span class="sxs-lookup"><span data-stu-id="c284b-177">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)