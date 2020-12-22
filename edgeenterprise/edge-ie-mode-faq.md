---
title: IE 模式 FAQ
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 12/21/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 关于结合使用 Microsoft Edge 和 IE 模式的 FAQ 和故障排除
ms.openlocfilehash: 62bf8afc5ac908e18d2f503fa9248a19f78fd6f6
ms.sourcegitcommit: 306582403d4272831bcac390154c7cc7041a9b7e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2020
ms.locfileid: "11238169"
---
# <span data-ttu-id="c0057-103">IE 模式 FAQ</span><span class="sxs-lookup"><span data-stu-id="c0057-103">IE mode FAQ</span></span>

<span data-ttu-id="c0057-104">本文介绍了 Microsoft Edge（版本 77 或更高版本）的故障排除提示和 FAQ。</span><span class="sxs-lookup"><span data-stu-id="c0057-104">This article provides troubleshooting tips and an FAQ for Microsoft Edge (version 77 or later).</span></span>

> [!NOTE]
> <span data-ttu-id="c0057-105">本文适用于 Microsoft Edge **Stable**、**Beta** 和 **Dev** 渠道版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="c0057-105">This article applies to Microsoft Edge **Stable**, **Beta** and **Dev** Channels, version 77 or later.</span></span>

## <span data-ttu-id="c0057-106">IE 模式疑难解答</span><span class="sxs-lookup"><span data-stu-id="c0057-106">Troubleshoot IE mode</span></span>

<span data-ttu-id="c0057-107">使用此部分中的信息诊断和修复 IE 模式问题。</span><span class="sxs-lookup"><span data-stu-id="c0057-107">Use the information in this section to diagnose and fix IE mode problems.</span></span>

### <span data-ttu-id="c0057-108">Internet Explorer 模式诊断信息</span><span class="sxs-lookup"><span data-stu-id="c0057-108">Internet Explorer mode diagnostic information</span></span>

<span data-ttu-id="c0057-109">可以在 Microsoft Edge 的“兼容性”选项卡上获取 Internet Explorer 模式诊断信息。若要打开此选项卡，请转到 *edge://compat/iediagnostic*。</span><span class="sxs-lookup"><span data-stu-id="c0057-109">You can get Internet Explorer mode diagnostic information on the Microsoft Edge Compatibility tab. To open this tab, go to *edge://compat/iediagnostic*.</span></span> <span data-ttu-id="c0057-110">此页面可能会显示诊断消息。</span><span class="sxs-lookup"><span data-stu-id="c0057-110">This page may show diagnostic messages.</span></span> <span data-ttu-id="c0057-111">此页面还显示以下类别的配置信息：</span><span class="sxs-lookup"><span data-stu-id="c0057-111">This page also provides configuration information for the following categories:</span></span>

- <span data-ttu-id="c0057-112">**注册表项检查**。</span><span class="sxs-lookup"><span data-stu-id="c0057-112">**Registry key check**.</span></span> <span data-ttu-id="c0057-113">（仅在检查失败时才显示。）检查是否在注册表中正确设置了 Internet Explorer 集成。</span><span class="sxs-lookup"><span data-stu-id="c0057-113">(Displayed only if the check fails.) Checks to see if Internet Explorer integration is set up correctly in the registry.</span></span> <span data-ttu-id="c0057-114">如果没有正确设置，用户可以单击“修复”\*\*\*\* 来解决问题。</span><span class="sxs-lookup"><span data-stu-id="c0057-114">If not, the user can click **Fix it** to resolve the problem.</span></span>
- <span data-ttu-id="c0057-115">**Internet Explorer 模式**。</span><span class="sxs-lookup"><span data-stu-id="c0057-115">**Internet Explorer mode**.</span></span> <span data-ttu-id="c0057-116">根据配置和操作系统来显示使用的 API 版本。</span><span class="sxs-lookup"><span data-stu-id="c0057-116">Shows the API version that's used, based on the configuration and OS.</span></span> <span data-ttu-id="c0057-117">如果无法显示，系统可能会提示用户安装 **Windows 更新**。</span><span class="sxs-lookup"><span data-stu-id="c0057-117">If there's a problem, the user may be prompted to install a **Windows Update**.</span></span>
- <span data-ttu-id="c0057-118">**Internet Explorer 模式设置**。</span><span class="sxs-lookup"><span data-stu-id="c0057-118">**Internet Explorer mode setting**.</span></span> <span data-ttu-id="c0057-119">显示 Internet Explorer 模式是否已启用，以及是如何配置的。</span><span class="sxs-lookup"><span data-stu-id="c0057-119">Shows whether Internet Explorer mode is enabled, and how it's configured.</span></span>
- <span data-ttu-id="c0057-120">**命令行**。</span><span class="sxs-lookup"><span data-stu-id="c0057-120">**Command line**.</span></span> <span data-ttu-id="c0057-121">显示用于启动 Microsoft Edge 的命令行字符串和开关。</span><span class="sxs-lookup"><span data-stu-id="c0057-121">Shows the command line string and switches used to start Microsoft Edge.</span></span>
- <span data-ttu-id="c0057-122">**组策略设置**。</span><span class="sxs-lookup"><span data-stu-id="c0057-122">**Group policy settings**.</span></span> <span data-ttu-id="c0057-123">显示 IE 模式是否是使用组策略配置的，以及应用的策略。</span><span class="sxs-lookup"><span data-stu-id="c0057-123">Shows whether IE mode is configured using group policies, and the policies that are applied.</span></span>

### <span data-ttu-id="c0057-124">错误消息：“要在 Internet Explorer 模式下打开此页面，请使用管理员权限重新安装 Microsoft Edge。”</span><span class="sxs-lookup"><span data-stu-id="c0057-124">Error message: "To open this page in Internet Explorer mode, reinstall Microsoft Edge with administrator privileges."</span></span>

<span data-ttu-id="c0057-125">如果没有安装所有必需 Windows 更新，可能会看到此错误。</span><span class="sxs-lookup"><span data-stu-id="c0057-125">You may see this error if you don't have all required Windows Updates.</span></span> <span data-ttu-id="c0057-126">有关必需 Windows 和 Microsoft Edge 版本，请参阅[关于 IE 模式](https://docs.microsoft.com/deployedge/edge-ie-mode)中列出的先决条件。</span><span class="sxs-lookup"><span data-stu-id="c0057-126">See the prerequisites listed in [About IE mode](https://docs.microsoft.com/deployedge/edge-ie-mode) for the required versions of Windows and Microsoft Edge.</span></span>

<span data-ttu-id="c0057-127">如果已安装所有必需 Windows 更新，但仍可能会在以下情况下看到此错误：</span><span class="sxs-lookup"><span data-stu-id="c0057-127">If you've already installed all required Windows Updates, you may see this error if:</span></span>

- <span data-ttu-id="c0057-128">你使用的是 Canary 渠道（默认安装在用户级别）。</span><span class="sxs-lookup"><span data-stu-id="c0057-128">You're using the Canary channel, which is installed at the user level by default.</span></span>
- <span data-ttu-id="c0057-129">你使用的是稳定渠道、Beta 渠道或 Dev 渠道，但在安装期间看到提升权限提示时，提升权限被取消了。</span><span class="sxs-lookup"><span data-stu-id="c0057-129">You're using the Stable, Beta, or Dev channel, but when prompted for elevation when installing the elevation was canceled.</span></span> <span data-ttu-id="c0057-130">如果你取消提升权限提示，安装将继续在用户级别进行。</span><span class="sxs-lookup"><span data-stu-id="c0057-130">When you cancel the elevation prompt, the installation will continue at the user level.</span></span>
- <span data-ttu-id="c0057-131">已在 Windows 功能中禁用 Internet Explorer 11。</span><span class="sxs-lookup"><span data-stu-id="c0057-131">Internet Explorer 11 has been disabled in Windows Features.</span></span>

<span data-ttu-id="c0057-132">可能的解决方案：</span><span class="sxs-lookup"><span data-stu-id="c0057-132">Possible solutions:</span></span>

- <span data-ttu-id="c0057-133">在系统级别针对任意渠道运行安装程序：`installer.exe --system-level`。</span><span class="sxs-lookup"><span data-stu-id="c0057-133">Run the installer for any channel at the system level: `installer.exe --system-level`.</span></span>
- <span data-ttu-id="c0057-134">在 Windows 功能中启用 Internet Explorer 11。</span><span class="sxs-lookup"><span data-stu-id="c0057-134">Enable Internet Explorer 11 in Windows Features.</span></span>

<span data-ttu-id="c0057-135">若要检查 Microsoft Edge 是否安装在系统级别，请在 Microsoft Edge 地址栏中键入“edge://version”。</span><span class="sxs-lookup"><span data-stu-id="c0057-135">To check if Microsoft Edge is installed at the systems level, type "edge://version" in the Microsoft Edge address bar.</span></span> <span data-ttu-id="c0057-136">“可执行文件路径”将会显示以“C:\Program Files”\*\* 开头的路径，这就表示是系统安装。</span><span class="sxs-lookup"><span data-stu-id="c0057-136">The Executable path will show a path starting with *C:\Program Files*, which indicates a system install.</span></span> <span data-ttu-id="c0057-137">如果“可执行文件路径”以“C:\Users\”\*\*开头，请使用管理员特权卸载并重新安装 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="c0057-137">If the Executable path begins with \*C:\Users\*, uninstall and then reinstall Microsoft Edge with administrator privileges.</span></span>

### <span data-ttu-id="c0057-138">错误消息：“要在 IE 模式下打开此页面，请尝试重启 Microsoft Edge。”</span><span class="sxs-lookup"><span data-stu-id="c0057-138">Error message: "To open this page in IE mode, try restarting Microsoft Edge."</span></span>

<span data-ttu-id="c0057-139">如果 Internet Explorer 中出现意外错误，你可能就会看到此错误。</span><span class="sxs-lookup"><span data-stu-id="c0057-139">You may see this error if there was an unexpected error in Internet Explorer.</span></span> <span data-ttu-id="c0057-140">重启 Microsoft Edge 通常可以修复此错误。</span><span class="sxs-lookup"><span data-stu-id="c0057-140">Restarting Microsoft Edge usually fixes this error.</span></span>

### <span data-ttu-id="c0057-141">错误消息：“关闭远程调试以在 IE 模式下打开此站点，否则可能无法正常工作。”</span><span class="sxs-lookup"><span data-stu-id="c0057-141">Error message: "Turn off remote debugging to open this site in IE mode otherwise it might not work as expected."</span></span>

<span data-ttu-id="c0057-142">如果你正在进行远程调试，并导航到配置为在 IE 模式下运行的网页，可能就会看到此错误。</span><span class="sxs-lookup"><span data-stu-id="c0057-142">You may see this error if you're remote debugging and navigate to a web page configured to run in IE mode.</span></span> <span data-ttu-id="c0057-143">你可以继续操作，但网页会使用 Microsoft Edge 呈现。</span><span class="sxs-lookup"><span data-stu-id="c0057-143">You can continue, but the page will be rendered using Microsoft Edge.</span></span>

## <span data-ttu-id="c0057-144">常见问题</span><span class="sxs-lookup"><span data-stu-id="c0057-144">Frequently Asked Questions</span></span>

### <span data-ttu-id="c0057-145">IE 模式是否将替换 Internet Explorer 11？</span><span class="sxs-lookup"><span data-stu-id="c0057-145">Will IE mode replace Internet Explorer 11?</span></span>

<span data-ttu-id="c0057-146">我们致力于使 Internet Explorer 成为受支持、可靠和安全的浏览器。</span><span class="sxs-lookup"><span data-stu-id="c0057-146">We're committed to keeping Internet Explorer a supported, reliable, and safe browser.</span></span> <span data-ttu-id="c0057-147">Internet Explorer 仍然是 Windows 的组件，并遵循其安装所在操作系统的支持生命周期。</span><span class="sxs-lookup"><span data-stu-id="c0057-147">Internet Explorer is still a component of Windows and follows the support lifecycle of the OS on which it's installed.</span></span> <span data-ttu-id="c0057-148">有关详细信息，请参阅[生命周期常见问题解答 - Internet Explorer](https://support.microsoft.com/help/17454/)。</span><span class="sxs-lookup"><span data-stu-id="c0057-148">For details, see [Lifecycle FAQ - Internet Explorer](https://support.microsoft.com/help/17454/).</span></span> <span data-ttu-id="c0057-149">尽管 Microsoft 会继续支持和更新 Internet Explorer，但最新功能和平台更新将仅在 Microsoft Edge 中提供。</span><span class="sxs-lookup"><span data-stu-id="c0057-149">While Microsoft continues to support and update Internet Explorer, the latest features and platform updates will only be available in Microsoft Edge.</span></span>

### <span data-ttu-id="c0057-150">是否可在 IE 模式下的 SharePoint 中使用“使用资源管理器打开”或“在文件资源管理器中查看”？</span><span class="sxs-lookup"><span data-stu-id="c0057-150">Can I use "Open with Explorer" or "View in File Explorer" in SharePoint with IE mode?</span></span>

<span data-ttu-id="c0057-151">能，如果这适用于独立 Internet Explorer 11，则也适用于 IE 模式。</span><span class="sxs-lookup"><span data-stu-id="c0057-151">Yes, if this works in standalone Internet Explorer 11 it will work in IE mode.</span></span> <span data-ttu-id="c0057-152">不过，若要管理 SharePoint 外部文件和文件夹，推荐方法是[同步 SharePoint 文件](https://support.office.com/en-us/article/sync-sharepoint-files-with-the-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)或[在 SharePoint 中移动或复制文件](https://support.office.com/en-us/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc)，而不是使用“使用资源管理器打开”选项。</span><span class="sxs-lookup"><span data-stu-id="c0057-152">However, rather than use the Open with Explorer option, the recommended approach to managing files and folders outside of SharePoint is to [sync your SharePoint files](https://support.office.com/en-us/article/sync-sharepoint-files-with-the-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88) or [move or copy files in SharePoint](https://support.office.com/en-us/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc).</span></span>

### <span data-ttu-id="c0057-153">Microsoft Edge 上的 IE 模式是否支持 Internet Explorer 11中支持的 *nomerge* 选项？</span><span class="sxs-lookup"><span data-stu-id="c0057-153">Does IE mode on Microsoft Edge support the *nomerge* option that was supported in Internet Explorer 11?</span></span>

<span data-ttu-id="c0057-154">在 Microsoft Edge 中没有明确的命令行来镜像 *nomerge* 选项，但是我们建议使用两种替代方法来提供此功能。</span><span class="sxs-lookup"><span data-stu-id="c0057-154">There is no explicit command line in Microsoft Edge to mirror the *nomerge* option, but there are a couple of alternatives that we recommend to provide this functionality.</span></span>

1. <span data-ttu-id="c0057-155">在 Microsoft Edge 中使用配置文件-每个配置文件对用 IE 模式页面的不同 IE 会话，因此其行为与 *nomerge* 选项相同。</span><span class="sxs-lookup"><span data-stu-id="c0057-155">Use Profiles in Microsoft Edge - Each profile maps to a different IE session for IE mode pages, so it behaves identically to the *nomerge* option.</span></span>
2. <span data-ttu-id="c0057-156">使用`--user-data-dir=<path>`命令行，但每个会话的路径不同。</span><span class="sxs-lookup"><span data-stu-id="c0057-156">Use the `--user-data-dir=<path>` command line, but with a different path for each session.</span></span> <span data-ttu-id="c0057-157">如果需要，可以创建一个既可以启动 Microsoft Edge，也可以更改会话的路径的实用程序供用户运行。</span><span class="sxs-lookup"><span data-stu-id="c0057-157">If needed, you can create a utility for the user to run that both launches Microsoft Edge and changes the path for the session.</span></span>

<span data-ttu-id="c0057-158">如果以上两个选项都不适用于你的情况，请通过其中一个反馈渠道联系我们：Microsoft 支持、[TechCommunity 论坛](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise)或 [Microsoft Edge UserVoice](https://microsoftedge.uservoice.com/forums/928825-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="c0057-158">If neither of the above options works for your scenario, reach out through one of our feedback channels:  Microsoft support, [TechCommunity forum](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise), or [Microsoft Edge UserVoice](https://microsoftedge.uservoice.com/forums/928825-enterprise).</span></span>

### <span data-ttu-id="c0057-159">我能否将链接另存为 Internet Explorer 模式的网页？</span><span class="sxs-lookup"><span data-stu-id="c0057-159">Can I save links as webpages in Internet Explorer mode?</span></span>
 
<span data-ttu-id="c0057-160">可以，可以在 Microsoft Edge 中的 Internet Explorer 模式下在在上下文菜单中启用“目标另存为”选项。</span><span class="sxs-lookup"><span data-stu-id="c0057-160">Yes, you can enable the Save Target As option in the context menu for Internet Explorer mode in Microsoft Edge.</span></span> <span data-ttu-id="c0057-161">为此，请配置组策略 *"允许在 Internet Explorer 模式下将目标另存为"*，该策略位于 *“计算机配置>“管理模板”>“Windows 组件”>”Internet Explorer”*。</span><span class="sxs-lookup"><span data-stu-id="c0057-161">To do this, configure the group policy *"Allow Save Target As in Internet Explorer mode"* located at *Computer Configuration > Administrative Templates > Windows Components > Internet Explorer*.</span></span>
<span data-ttu-id="c0057-162">保存机制的工作方式与在 Internet Explorer 中相同，并且如果目标另存为 html 文件，重新打开文件将在 Microsoft Edge 中呈现页面。</span><span class="sxs-lookup"><span data-stu-id="c0057-162">The save mechanism works the same as it does in Internet Explorer and if the target is saved as an html file, re-opening the file will render the page in Microsoft Edge.</span></span>
 
<span data-ttu-id="c0057-163">请注意，此功能需要以下最低要求的操作系统更新：</span><span class="sxs-lookup"><span data-stu-id="c0057-163">Note that this functionality requires the following minimum operating system updates:</span></span>
- <span data-ttu-id="c0057-164">Windows 10 版本 2004、Windows Server 版本 2004、Windows 10 版本 20H2：[KB4580364](https://support.microsoft.com/help/4580364/windows-10-update-kb4580364)</span><span class="sxs-lookup"><span data-stu-id="c0057-164">Windows 10, version 2004, Windows Server version 2004, Windows 10, version 20H2 : [KB4580364](https://support.microsoft.com/help/4580364/windows-10-update-kb4580364)</span></span>
- <span data-ttu-id="c0057-165">Windows 10 版本 1903、Windows 10 版本 1909、Windows Server 版本 1903：[KB4580386](https://support.microsoft.com/help/4580386/windows-10-update-kb4580386)</span><span class="sxs-lookup"><span data-stu-id="c0057-165">Windows 10, version 1903, Windows 10, version 1909, Windows Server version 1903: [KB4580386](https://support.microsoft.com/help/4580386/windows-10-update-kb4580386)</span></span>
- <span data-ttu-id="c0057-166">Windows 10 版本 1809、Windows Server 版本 1809、Windows Server 2019：[KB4580390](https://support.microsoft.com/help/4580390/windows-10-update-kb4580390)</span><span class="sxs-lookup"><span data-stu-id="c0057-166">Windows 10, version 1809, Windows Server version 1809, Windows Server 2019: [KB4580390](https://support.microsoft.com/help/4580390/windows-10-update-kb4580390)</span></span>
- <span data-ttu-id="c0057-167">Windows 10 版本 1803：[KB4586785](https://support.microsoft.com/help/4586785/windows-10-update-kb4586785)</span><span class="sxs-lookup"><span data-stu-id="c0057-167">Windows 10, version 1803: [KB4586785](https://support.microsoft.com/help/4586785/windows-10-update-kb4586785)</span></span>
- <span data-ttu-id="c0057-168">Windows 10 版本 1607：[KB4586830](https://support.microsoft.com/help/4586830/windows-10-update-kb4586830)</span><span class="sxs-lookup"><span data-stu-id="c0057-168">Windows 10, version 1607: [KB4586830](https://support.microsoft.com/help/4586830/windows-10-update-kb4586830)</span></span>
- <span data-ttu-id="c0057-169">Windows 10 版本 1507：[KB4586787](https://support.microsoft.com/help/4586787/windows-10-update-kb4586787)</span><span class="sxs-lookup"><span data-stu-id="c0057-169">Windows 10, version 1507: [KB4586787](https://support.microsoft.com/help/4586787/windows-10-update-kb4586787)</span></span>


## <span data-ttu-id="c0057-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0057-170">See also</span></span>

- [<span data-ttu-id="c0057-171">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="c0057-171">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="c0057-172">关于 IE 模式</span><span class="sxs-lookup"><span data-stu-id="c0057-172">About IE mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [<span data-ttu-id="c0057-173">其他企业模式信息</span><span class="sxs-lookup"><span data-stu-id="c0057-173">Additional Enterprise Mode information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
