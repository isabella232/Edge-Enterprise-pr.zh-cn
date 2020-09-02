---
title: 适用于 Microsoft Defender SmartScreen 的 Microsoft Edge 支持
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 04/23/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 适用于 Microsoft Defender SmartScreen 的 Microsoft Edge 支持
ms.openlocfilehash: d27366409d7792784c360cfee10f96ab174aa375
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979394"
---
# <span data-ttu-id="a405b-103">适用于 Microsoft Defender SmartScreen 的 Microsoft Edge 支持</span><span class="sxs-lookup"><span data-stu-id="a405b-103">Microsoft Edge support for Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="a405b-104">本文介绍使用 Microsoft Defender SmartScreen 的优点，说明了其工作原理，还介绍如何配置此 Microsoft Edge 功能。</span><span class="sxs-lookup"><span data-stu-id="a405b-104">This article describes the benefits of using Microsoft Defender SmartScreen, explains how it works, and describes how to configure this Microsoft Edge feature.</span></span>

> [!NOTE]
> <span data-ttu-id="a405b-105">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a405b-105">This article applies to Microsoft Edge version 77 or later.</span></span>

<span data-ttu-id="a405b-106">Microsoft Defender SmartScreen 是一项服务，在你浏览 web 时，Microsoft Edge 将使用该服务确保安全。</span><span class="sxs-lookup"><span data-stu-id="a405b-106">Microsoft Defender SmartScreen is a service that Microsoft Edge uses to keep you safe while you browse the web.</span></span> <span data-ttu-id="a405b-107">Microsoft Defender SmartScreen 针对可能从事钓鱼攻击，或尝试通过集中式攻击分发恶意软件的网站提供早期警告系统。</span><span class="sxs-lookup"><span data-stu-id="a405b-107">Microsoft Defender SmartScreen provides an early warning system against websites that might engage in phishing attacks or attempt to distribute malware through a focused attack.</span></span>

> [!NOTE]
> <span data-ttu-id="a405b-108">在 Windows 10 版本 1703 之前，此功能在浏览器中使用时称为 SmartScreen 筛选器，在浏览器之外使用时则称为 Microsoft SmartScreen。</span><span class="sxs-lookup"><span data-stu-id="a405b-108">Before Windows 10, version 1703, this feature was called the SmartScreen filter when used within the browser and Microsoft SmartScreen when used outside of the browser.</span></span>

## <span data-ttu-id="a405b-109">Microsoft Defender SmartScreen 的好处</span><span class="sxs-lookup"><span data-stu-id="a405b-109">The benefits of Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="a405b-110">Microsoft Defender SmartScreen 提供了几个优点，下面的列表对此进行了概述。</span><span class="sxs-lookup"><span data-stu-id="a405b-110">Microsoft Defender SmartScreen provides several benefits, which are summarized in the following list.</span></span> <span data-ttu-id="a405b-111">这些优点在 [Microsoft Defender SmartScreen 文档](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview#benefits-of-windows-defender-smartscreen)中详细叙述。</span><span class="sxs-lookup"><span data-stu-id="a405b-111">These benefits are described in detail in the [Microsoft Defender SmartScreen documentation](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview#benefits-of-windows-defender-smartscreen).</span></span> <span data-ttu-id="a405b-112">优点有：</span><span class="sxs-lookup"><span data-stu-id="a405b-112">The benefits are:</span></span>

- <span data-ttu-id="a405b-113">防网络钓鱼和反恶意软件支持</span><span class="sxs-lookup"><span data-stu-id="a405b-113">Anti-phishing and anti-malware support</span></span>
- <span data-ttu-id="a405b-114">基于信誉的 URL 和应用保护</span><span class="sxs-lookup"><span data-stu-id="a405b-114">Reputation-based URL and app protection</span></span>
- <span data-ttu-id="a405b-115">操作系统集成</span><span class="sxs-lookup"><span data-stu-id="a405b-115">Operating system integration</span></span>
- <span data-ttu-id="a405b-116">改进的启发和诊断数据</span><span class="sxs-lookup"><span data-stu-id="a405b-116">Improved heuristics and diagnostic data</span></span>
- <span data-ttu-id="a405b-117">通过组策略和 Microsoft Intune 进行管理</span><span class="sxs-lookup"><span data-stu-id="a405b-117">Management through Group Policy and Microsoft Intune</span></span>
- <span data-ttu-id="a405b-118">阻止与潜在有害应用程序关联的 URL</span><span class="sxs-lookup"><span data-stu-id="a405b-118">Blocking URLs associated with potentially unwanted applications</span></span>

## <span data-ttu-id="a405b-119">了解 Microsoft Defender SmartScreen 的工作原理</span><span class="sxs-lookup"><span data-stu-id="a405b-119">Understand how Microsoft Defender SmartScreen works</span></span>

<span data-ttu-id="a405b-120">许多输入会导致 Microsoft Defender SmartScreen 警告。</span><span class="sxs-lookup"><span data-stu-id="a405b-120">A number of inputs contribute to Microsoft Defender SmartScreen warnings.</span></span> <span data-ttu-id="a405b-121">数据接收自多个来源，包括用户反馈、数据提供商和智能模型。</span><span class="sxs-lookup"><span data-stu-id="a405b-121">Data is received from many sources, including user feedback, data providers, and intelligence models.</span></span> <span data-ttu-id="a405b-122">此数据用于帮助识别潜在的恶意内容。</span><span class="sxs-lookup"><span data-stu-id="a405b-122">This data is used to help identify potentially malicious content.</span></span> <span data-ttu-id="a405b-123">Microsoft Defender SmartScreen 还检查已下载的应用或应用安装程序是否有恶意。</span><span class="sxs-lookup"><span data-stu-id="a405b-123">Microsoft Defender SmartScreen also checks downloaded apps or app installers to see if they're malicious.</span></span> <span data-ttu-id="a405b-124">在这两种情况下，Microsoft Defender SmartScreen 都会警告用户有关可疑内容的信息。</span><span class="sxs-lookup"><span data-stu-id="a405b-124">In both scenarios, Microsoft Defender SmartScreen warns users appropriately about suspicious content.</span></span>

### <span data-ttu-id="a405b-125">站点分析</span><span class="sxs-lookup"><span data-stu-id="a405b-125">Site analysis</span></span>

<span data-ttu-id="a405b-126">Microsoft Defender SmartScreen 可通过以下方法确定某站点是否为潜在恶意网站：</span><span class="sxs-lookup"><span data-stu-id="a405b-126">Microsoft Defender SmartScreen determines whether a site is potentially malicious by:</span></span>

- <span data-ttu-id="a405b-127">分析已访问的页面，发现可以行为的迹象。</span><span class="sxs-lookup"><span data-stu-id="a405b-127">Analyzing visited webpages for indications of suspicious behavior.</span></span>
- <span data-ttu-id="a405b-128">检查已访问站点，以获取所报告的钓鱼网站的动态记录。</span><span class="sxs-lookup"><span data-stu-id="a405b-128">Checking the visited sites against a dynamic record of reported phishing sites.</span></span>

<span data-ttu-id="a405b-129">如果 Microsoft Defender SmartScreen 确定某个页面是恶意的，将显示一个警告页面，通知用户该站点被报告为不安全。</span><span class="sxs-lookup"><span data-stu-id="a405b-129">If Microsoft Defender SmartScreen determines that a page is malicious, it will show a warning page to notify the user that that site is reported as unsafe.</span></span> <span data-ttu-id="a405b-130">下一个屏幕截图显示了用户尝试打开恶意网站时出现的 Microsoft Defender SmartScreen 警告页面的示例。</span><span class="sxs-lookup"><span data-stu-id="a405b-130">The next screenshot shows an example of a Microsoft Defender SmartScreen warning page when a user tries to open a malicious website.</span></span>

![Microsoft Defender SmartScreen 阻止指向外部网站的链接](media/microsoft-edge-security-smartscreen/microsoft-edge-smartscreen-warning.png)

<span data-ttu-id="a405b-132">用户可以选择在警告消息中将网站报告为安全或不安全。</span><span class="sxs-lookup"><span data-stu-id="a405b-132">Users are given the option of reporting a site as safe or unsafe within the warning message.</span></span> <span data-ttu-id="a405b-133">有关详细信息，请参阅“[如何报告网站](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-set-individual-device#how-users-can-report-websites-as-safe-or-unsafe)”。</span><span class="sxs-lookup"><span data-stu-id="a405b-133">For more information, see [how to report a site](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-set-individual-device#how-users-can-report-websites-as-safe-or-unsafe).</span></span>

### <span data-ttu-id="a405b-134">文件分析</span><span class="sxs-lookup"><span data-stu-id="a405b-134">File analysis</span></span>

<span data-ttu-id="a405b-135">Microsoft Defender SmartScreen 基于许多标准（例如下载流量、下载历史记录、过去的防病毒结果和 URL 信誉）来确定下载的应用或应用安装程序是否有潜在恶意。</span><span class="sxs-lookup"><span data-stu-id="a405b-135">Microsoft Defender SmartScreen determines whether a downloaded app or app installer is potentially malicious based on many criteria, such as download traffic, download history, past anti-virus results, and URL reputation.</span></span>

- <span data-ttu-id="a405b-136">自动下载信誉已知安全的文件，不发出任何通知。</span><span class="sxs-lookup"><span data-stu-id="a405b-136">Files with a known safe reputation will download without any notification.</span></span>  
- <span data-ttu-id="a405b-137">信誉已知恶意的文件会显示警告，以使用户知道文件不安全，已报告为恶意。</span><span class="sxs-lookup"><span data-stu-id="a405b-137">Files with a known malicious reputation show a warning to let the user know that the file is unsafe and has been reported as malicious.</span></span> <span data-ttu-id="a405b-138">下一个屏幕截图是针对恶意文件的警告示例。</span><span class="sxs-lookup"><span data-stu-id="a405b-138">The next screenshot is an example of a warning for a malicious file.</span></span>

  ![Microsoft Defender SmartScreen 阻止信誉可以的页面文件](media/microsoft-edge-security-smartscreen/ms-edge-smartscreen-known-malicious.png)

- <span data-ttu-id="a405b-140">未知文件会显示警告，以使用户知道下载的文件大小未知，并请注意。</span><span class="sxs-lookup"><span data-stu-id="a405b-140">Files that are unknown show a warning to let the user know that the download doesn't have a known footprint and advise caution.</span></span> <span data-ttu-id="a405b-141">下一个屏幕截图是针对未知文件的警告示例。</span><span class="sxs-lookup"><span data-stu-id="a405b-141">The next screenshot is an example of a warning for an unknown file.</span></span>

  ![Microsoft Defender SmartScreen 阻止信誉可以的页面文件](media/microsoft-edge-security-smartscreen/ms-edge-smartscreen-unknown-malicious.png)

<span data-ttu-id="a405b-143">并非所有未知程序都是恶意的，未知警告旨在为需要它的用户提供上下文和指导，特别是如果警告是意外的。</span><span class="sxs-lookup"><span data-stu-id="a405b-143">Not all unknown programs are malicious, and the unknown warning is intended to provide context and guidance for users who need it, especially if the warning is unexpected.</span></span>

  ![保留恶意信誉文件](media/microsoft-edge-security-smartscreen/ms-edge-smartscreen-unknown-malicious-keep.png)

<span data-ttu-id="a405b-145">但是用户仍可通过点击 **... | 保留 | 显示更多 | 仍要保留**来下载并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="a405b-145">However, users can still download and run the application by clicking **... | Keep | Show More | Keep anyway**.</span></span>

> [!TIP]
> **<span data-ttu-id="a405b-146">仅供企业用户参考。</span><span class="sxs-lookup"><span data-stu-id="a405b-146">FYI for Enterprise Customers.</span></span>** <span data-ttu-id="a405b-147">默认情况下，Microsoft Defender SmartScreen 允许用户忽视警告。</span><span class="sxs-lookup"><span data-stu-id="a405b-147">By default, Microsoft Defender SmartScreen lets users bypass warnings.</span></span> <span data-ttu-id="a405b-148">由于用户交互可能存在风险，因此建议查看以下[推荐的组策略设置](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-available-settings#recommended-group-policy-and-mdm-settings-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="a405b-148">Because this user interaction is potentially risky, we recommend that you review these [recommended group policy settings](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-available-settings#recommended-group-policy-and-mdm-settings-for-your-organization).</span></span>

<span data-ttu-id="a405b-149">你将看到 Microsoft Defender SmartScreen 如何使用[演示网站](https://demo.smartscreen.msft.net/)来响应不同的情况。</span><span class="sxs-lookup"><span data-stu-id="a405b-149">You see how Microsoft Defender SmartScreen responds to different scenarios using our [demo site](https://demo.smartscreen.msft.net/).</span></span>

## <span data-ttu-id="a405b-150">Microsoft Defender SmartScreen 和用户隐私</span><span class="sxs-lookup"><span data-stu-id="a405b-150">Microsoft Defender SmartScreen and user privacy</span></span>

<span data-ttu-id="a405b-151">用户使用信誉检查系统浏览 Internet 时，Microsoft Defender SmartScreen 可以保护用户。</span><span class="sxs-lookup"><span data-stu-id="a405b-151">Microsoft Defender SmartScreen protects users while they browse the Internet by using a reputation check system.</span></span> <span data-ttu-id="a405b-152">Microsoft Edge 将有关 URL 或文件的相关信息传递给 Microsoft Defender SmartScreen 服务以启动信誉检查。</span><span class="sxs-lookup"><span data-stu-id="a405b-152">Microsoft Edge passes relevant information about the URL or file to the Microsoft Defender SmartScreen service to start the reputation check.</span></span> <span data-ttu-id="a405b-153">此检查将网站或文件与危险已知的站点和文件动态列表进行比较。</span><span class="sxs-lookup"><span data-stu-id="a405b-153">The check compares the website or file against dynamic lists of sites and files that are known to be dangerous.</span></span> <span data-ttu-id="a405b-154">所有 Microsoft Defender SmartScreen 服务请求均可使用 TLS 加密进行。</span><span class="sxs-lookup"><span data-stu-id="a405b-154">All requests to the Microsoft Defender SmartScreen service are made with TLS encryption.</span></span> <span data-ttu-id="a405b-155">服务返回信誉检查的结果，可能会导致 Microsoft Edge 显示网站或文件的警告。</span><span class="sxs-lookup"><span data-stu-id="a405b-155">The service returns the results of the reputation check, which might lead to Microsoft Edge showing a warning for the site or file.</span></span> <span data-ttu-id="a405b-156">这些结果将本地存储在设备上。</span><span class="sxs-lookup"><span data-stu-id="a405b-156">These results are stored locally on the device.</span></span>

<span data-ttu-id="a405b-157">Microsoft Defender SmartScreen 服务存储有关信誉检查的数据。</span><span class="sxs-lookup"><span data-stu-id="a405b-157">The Microsoft Defender SmartScreen service stores data about reputation checks.</span></span> <span data-ttu-id="a405b-158">识别到新站点后，该服务将添加到已知的恶意 URL 和文件动态数据库中。</span><span class="sxs-lookup"><span data-stu-id="a405b-158">As new sites are identified, the service adds to a dynamic database of known malicious URLs and files.</span></span> <span data-ttu-id="a405b-159">此数据存储在安全的 Microsoft 服务器上，仅用于 Microsoft 安全服务。</span><span class="sxs-lookup"><span data-stu-id="a405b-159">This data is stored on secure Microsoft servers and is only used for Microsoft security services.</span></span> <span data-ttu-id="a405b-160">此数据绝不会以任何方式用于识别或定位用户。</span><span class="sxs-lookup"><span data-stu-id="a405b-160">This data will never be used to identify or target users in any way.</span></span> <span data-ttu-id="a405b-161">清除浏览缓存将清除所有本地存储的 Microsoft Defender SmartScreen URL 数据。</span><span class="sxs-lookup"><span data-stu-id="a405b-161">Clearing browsing cache clears all locally stored Microsoft Defender SmartScreen URL data.</span></span> <span data-ttu-id="a405b-162">清除下载历史记录将删除本地存储的任何有关文件下载的 SmartScreen 数据。</span><span class="sxs-lookup"><span data-stu-id="a405b-162">Clearing download history will remove any locally stored SmartScreen data about file downloads.</span></span>

<span data-ttu-id="a405b-163">有关 Microsoft Defender SmartScreen 和 Microsoft Edge 上的隐私的详细信息，请阅读 [Microsoft Edge 隐私白皮书](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper#smartscreen)。</span><span class="sxs-lookup"><span data-stu-id="a405b-163">For more information about Microsoft Defender SmartScreen and privacy on Microsoft Edge, read the [Microsoft Edge Privacy Whitepaper](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper#smartscreen).</span></span>

## <span data-ttu-id="a405b-164">Microsoft Defender SmartScreen 管理员设置</span><span class="sxs-lookup"><span data-stu-id="a405b-164">Microsoft Defender SmartScreen setup for admins</span></span>

<span data-ttu-id="a405b-165">管理员可以使用组策略、Microsoft Intune 或移动设备管理（MDM）设置配置 Microsoft Defender SmartScreen。</span><span class="sxs-lookup"><span data-stu-id="a405b-165">Admins can configure Microsoft Defender SmartScreen using Group Policy, Microsoft Intune, or mobile device management (MDM) settings.</span></span> <span data-ttu-id="a405b-166">根据你设置 Microsoft Defender SmartScreen 的方式，你可以向用户显示一个警告页面并让他们继续使用站点，也可以完全阻止站点。</span><span class="sxs-lookup"><span data-stu-id="a405b-166">Based on how you set up Microsoft Defender SmartScreen, you can show users a warning page and let them continue to the site or block the site entirely.</span></span>

### <span data-ttu-id="a405b-167">使用组策略设置 Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="a405b-167">Microsoft Defender SmartScreen set up using Group Policy</span></span>

<span data-ttu-id="a405b-168">有关 SmartScreen 策略的完整列表，请参阅 [Microsoft Defender SmartScreen 设置](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreen-settings)</span><span class="sxs-lookup"><span data-stu-id="a405b-168">For a complete list of SmartScreen policies, see [Microsoft Defender SmartScreen settings](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreen-settings)</span></span>

### <span data-ttu-id="a405b-169">使用 MDM 设置 Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="a405b-169">Microsoft Defender SmartScreen set up using MDM</span></span>

<span data-ttu-id="a405b-170">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="a405b-170">For more information, see:</span></span>

- [<span data-ttu-id="a405b-171">适用于 Microsoft Defender SmartScreen 的 Windows Intune 设置</span><span class="sxs-lookup"><span data-stu-id="a405b-171">Windows Intune settings for Microsoft Defender SmartScreen</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#windows-defender-smartscreen-settings)
- [<span data-ttu-id="a405b-172">MDM 策略设置</span><span class="sxs-lookup"><span data-stu-id="a405b-172">MDM policy settings</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#windows-defender-smartscreen-settings)

## <span data-ttu-id="a405b-173">Microsoft Defender SmartScreen 用户设置</span><span class="sxs-lookup"><span data-stu-id="a405b-173">Microsoft Defender SmartScreen setup for users</span></span>

<span data-ttu-id="a405b-174">默认情况下，Microsoft Edge 将启用 Microsoft Defender SmartScreen。</span><span class="sxs-lookup"><span data-stu-id="a405b-174">Microsoft Defender SmartScreen is turned on by default for Microsoft Edge.</span></span> <span data-ttu-id="a405b-175">若要关闭 Microsoft Defender SmartScreen，转到 *edge://settings/privacy > Services > Microsoft Defender SmartScreen*。</span><span class="sxs-lookup"><span data-stu-id="a405b-175">To turn off Microsoft Defender SmartScreen, go to *edge://settings/privacy > Services > Microsoft Defender SmartScreen*.</span></span> <span data-ttu-id="a405b-176">对于与设备上所有 Microsoft Edge 安装相关的配置文件，此设置相同。</span><span class="sxs-lookup"><span data-stu-id="a405b-176">This setting is the same for all profiles associated with the installation of Microsoft Edge on a device.</span></span> <span data-ttu-id="a405b-177">此设置不会跨设备同步。</span><span class="sxs-lookup"><span data-stu-id="a405b-177">This setting is not synced across devices.</span></span> <span data-ttu-id="a405b-178">此设置适用于 InPrivate 浏览和来宾模式。</span><span class="sxs-lookup"><span data-stu-id="a405b-178">The setting applies to InPrivate browsing and Guest mode.</span></span> <span data-ttu-id="a405b-179">如果设备由组织设置的组策略管理，此配置将在*edge://settings/privacy*中展现出来。</span><span class="sxs-lookup"><span data-stu-id="a405b-179">If a device is managed with group policies set by an organization, this configuration will be reflected in *edge://settings/privacy*.</span></span>

> [!NOTE]
> <span data-ttu-id="a405b-180">用户可以为单个设备设置 Microsoft Defender SmartScreen，除非配置了组策略或 MDM 来阻止它。</span><span class="sxs-lookup"><span data-stu-id="a405b-180">Users can set up Microsoft Defender SmartScreen for an individual device unless Group Policy or MDM is configured to prevent it.</span></span> <span data-ttu-id="a405b-181">有关更多信息，请参阅[在各个设备上设置并使用 Microsoft Defender SmartScreen ](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-set-individual-device)。</span><span class="sxs-lookup"><span data-stu-id="a405b-181">For more information, see [set up and use Microsoft Defender SmartScreen on individual devices](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-set-individual-device).</span></span>

## <span data-ttu-id="a405b-182">常见问题</span><span class="sxs-lookup"><span data-stu-id="a405b-182">Frequently asked questions</span></span>

### <span data-ttu-id="a405b-183">信誉检查系统是如何工作的？</span><span class="sxs-lookup"><span data-stu-id="a405b-183">How does the reputation check system work?</span></span>

<span data-ttu-id="a405b-184">浏览网络时，Microsoft Defender SmartScreen 将网站和下载分类为主要流量、危险或未知。</span><span class="sxs-lookup"><span data-stu-id="a405b-184">As you browse the web, Microsoft Defender SmartScreen categorizes websites and downloads as top traffic, dangerous, or unknown.</span></span> <span data-ttu-id="a405b-185">主要流量是被 Microsoft Defender SmartScreen 确定为可信的网站。</span><span class="sxs-lookup"><span data-stu-id="a405b-185">Top traffic is popular sites that Microsoft Defender SmartScreen has determined are trustworthy.</span></span> <span data-ttu-id="a405b-186">如果转到标记为危险的站点，Microsoft Defender SmartScreen 将立即阻止你访问此站点。</span><span class="sxs-lookup"><span data-stu-id="a405b-186">If you go to a site marked as dangerous, Microsoft Defender SmartScreen immediately blocks you from accessing the site.</span></span> <span data-ttu-id="a405b-187">转到未知站点时，Microsoft DefenderSmartScreen 会检查其信誉以确定是否应访问此站点。</span><span class="sxs-lookup"><span data-stu-id="a405b-187">When you go to an unknown site, Microsoft DefenderSmartScreen checks its reputation to determine if you should access the site.</span></span>

## <span data-ttu-id="a405b-188">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a405b-188">See also</span></span>

- [<span data-ttu-id="a405b-189">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="a405b-189">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="a405b-190">Microsoft Defender SmartScreen 概述</span><span class="sxs-lookup"><span data-stu-id="a405b-190">Microsoft Defender SmartScreen Overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview)
- [<span data-ttu-id="a405b-191">威胁防护</span><span class="sxs-lookup"><span data-stu-id="a405b-191">Threat protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/index)
- [<span data-ttu-id="a405b-192">阻止潜在的有害应用程序</span><span class="sxs-lookup"><span data-stu-id="a405b-192">Protect against potentially unwanted applications</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-potentially-unwanted-apps)