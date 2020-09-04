---
title: Microsoft Edge 和 Microsoft Defender 应用程序防护
ms.author: srugh
author: dan-wesley
manager: seanlyn
ms.date: 06/19/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 对 Microsoft Defender 应用程序防护的支持
ms.openlocfilehash: 7bd2efd35e0cd65c524a17a88f659e9b3838233f
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979388"
---
# <span data-ttu-id="f40ed-103">Microsoft Edge 对 Microsoft Defender 应用程序防护的支持</span><span class="sxs-lookup"><span data-stu-id="f40ed-103">Microsoft Edge support for Microsoft Defender Application Guard</span></span>

<span data-ttu-id="f40ed-104">本文介绍 Microsoft Edge 如何支持 Microsoft Defender 应用程序防护（应用程序防护）。</span><span class="sxs-lookup"><span data-stu-id="f40ed-104">This article describes how Microsoft Edge supports Microsoft Defender Application Guard (Application Guard).</span></span>

> [!NOTE]
> <span data-ttu-id="f40ed-105">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="f40ed-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="f40ed-106">概述</span><span class="sxs-lookup"><span data-stu-id="f40ed-106">Overview</span></span>

<span data-ttu-id="f40ed-107">企业中的安全架构师必须处理生产力与安全性之间的矛盾。</span><span class="sxs-lookup"><span data-stu-id="f40ed-107">Security architects in the enterprise must deal with the tension that exists between productivity and security.</span></span> <span data-ttu-id="f40ed-108">锁定浏览器并且仅允许加载少数受信任的站点相对简单。</span><span class="sxs-lookup"><span data-stu-id="f40ed-108">It's relatively easy to lock down a browser and only allow a handful of trusted sites to load.</span></span> <span data-ttu-id="f40ed-109">这种方法可改进整体安全状态，但生产力会降低。</span><span class="sxs-lookup"><span data-stu-id="f40ed-109">This approach will improve the overall security posture but is arguably less productive.</span></span> <span data-ttu-id="f40ed-110">如果你为提高生产力而减少限制，则会增加风险。</span><span class="sxs-lookup"><span data-stu-id="f40ed-110">If you make it less restrictive to improve productivity, you increase the risk profile.</span></span> <span data-ttu-id="f40ed-111">这很难达到平衡！</span><span class="sxs-lookup"><span data-stu-id="f40ed-111">It's a hard balance to strike!</span></span>

<span data-ttu-id="f40ed-112">在不断变化的威胁形势下，即时了解新出现的威胁变得更加困难。</span><span class="sxs-lookup"><span data-stu-id="f40ed-112">It's even harder to keep up with new emerging threats in this constantly changing threat landscape.</span></span> <span data-ttu-id="f40ed-113">浏览器仍然是客户端设备上的主要攻击面，因为浏览器的基本任务是让用户访问、下载和打开来自不可信来源的不可信内容。</span><span class="sxs-lookup"><span data-stu-id="f40ed-113">Browsers remain the primary attack surface on client devices because the browser's basic job is to let users access, download, and open untrusted content from untrusted sources.</span></span> <span data-ttu-id="f40ed-114">恶意参与者一直在忙于对浏览器进行新形式的社会工程攻击。</span><span class="sxs-lookup"><span data-stu-id="f40ed-114">Malicious actors are constantly working to social engineer new forms of attacks against the browser.</span></span> <span data-ttu-id="f40ed-115">安全事件预防或检测/响应策略不能保证 100% 安全。</span><span class="sxs-lookup"><span data-stu-id="f40ed-115">Security incident prevention or detection/response strategies can't guarantee 100% safety.</span></span>

<span data-ttu-id="f40ed-116">要考虑的一个关键安全策略是[假设失陷方法](https://docs.microsoft.com/office365/Enterprise/office-365-monitoring-and-testing#assume-breach-methodology)，这意味着用户接受无论如何努力地抵御攻击，该攻击总会成功一次的观念。</span><span class="sxs-lookup"><span data-stu-id="f40ed-116">A key security strategy to consider is the [Assume Breach Methodology](https://docs.microsoft.com/office365/Enterprise/office-365-monitoring-and-testing#assume-breach-methodology), which means there's an acceptance that an attack is going to succeed at least once regardless of efforts to prevent it.</span></span> <span data-ttu-id="f40ed-117">此思维方式要求建立防御机制来遏制损坏，这可确保企业网络和其他资源在这种情况下得到保护。</span><span class="sxs-lookup"><span data-stu-id="f40ed-117">This mindset requires building defenses to contain the damage, which ensures that corporate network and other resources remain protected in this scenario.</span></span>  <span data-ttu-id="f40ed-118">为 Microsoft Edge 部署应用程序防护符合此策略。</span><span class="sxs-lookup"><span data-stu-id="f40ed-118">Deploying Application Guard for Microsoft Edge fits right into this strategy.</span></span>

## <span data-ttu-id="f40ed-119">关于应用程序防护</span><span class="sxs-lookup"><span data-stu-id="f40ed-119">About Application Guard</span></span>

<span data-ttu-id="f40ed-120">专为 Windows 10 和 Microsoft Edge 设计，应用程序防护使用硬件隔离方法。</span><span class="sxs-lookup"><span data-stu-id="f40ed-120">Designed for Windows 10 and Microsoft Edge, Application Guard uses a hardware isolation approach.</span></span> <span data-ttu-id="f40ed-121">这种方法允许在容器中启动不受信任的站点导航。</span><span class="sxs-lookup"><span data-stu-id="f40ed-121">This approach lets untrusted site navigation launch inside a container.</span></span> <span data-ttu-id="f40ed-122">硬件隔离可帮助企业保护其企业网络和数据，以防用户访问受到威胁或恶意的站点。</span><span class="sxs-lookup"><span data-stu-id="f40ed-122">Hardware isolation helps enterprises safeguard their corporate network and data in case users visit a site that is compromised or is malicious.</span></span>

<span data-ttu-id="f40ed-123">企业管理员定义什么是受信任的站点、云资源和内部网络。</span><span class="sxs-lookup"><span data-stu-id="f40ed-123">The enterprise administrator defines what are trusted sites, cloud resources, and internal networks.</span></span> <span data-ttu-id="f40ed-124">不在受信任站点列表中的所有内容都被视为不可信内容。</span><span class="sxs-lookup"><span data-stu-id="f40ed-124">Everything that's not in the trusted sites list is considered untrusted.</span></span> <span data-ttu-id="f40ed-125">这些站点与企业网络和用户设备上的数据相隔离。</span><span class="sxs-lookup"><span data-stu-id="f40ed-125">These sites are isolated from the corporate network and data on the user's device.</span></span>

<span data-ttu-id="f40ed-126">有关详细信息，请参阅[什么是应用程序防护，以及它是如何工作的？](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview#what-is-application-guard-and-how-does-it-work)。</span><span class="sxs-lookup"><span data-stu-id="f40ed-126">For more information, see [What is Application Guard and how does it work?](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview#what-is-application-guard-and-how-does-it-work).</span></span>

<span data-ttu-id="f40ed-127">下一个屏幕截图显示应用程序防护的消息示例，它显示用户正在安全空间中浏览。</span><span class="sxs-lookup"><span data-stu-id="f40ed-127">The next screenshot shows an example of Application Guard's message showing that the user is browsing in a safe space.</span></span>

![应用程序防护安全浏览消息](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-1.png)

## <span data-ttu-id="f40ed-129">新增功能</span><span class="sxs-lookup"><span data-stu-id="f40ed-129">What's new</span></span>

<span data-ttu-id="f40ed-130">新版 Microsoft Edge 浏览器中的应用程序防护支持与 Microsoft Edge 旧版具有同等的功能，并包括多项改进。</span><span class="sxs-lookup"><span data-stu-id="f40ed-130">Application Guard support in the new Microsoft Edge  browser has functional parity with Microsoft Edge Legacy and includes several improvements.</span></span>

### <span data-ttu-id="f40ed-131">容器内的扩展支持</span><span class="sxs-lookup"><span data-stu-id="f40ed-131">Extension support inside the container</span></span>

<span data-ttu-id="f40ed-132">容器内的扩展支持是客户的首要请求之一。</span><span class="sxs-lookup"><span data-stu-id="f40ed-132">Extension support inside the container has been one of the top requests from the customers.</span></span> <span data-ttu-id="f40ed-133">场景范围从希望在容器内运行广告拦截器以提高浏览器性能，到能够在容器内运行自定义的本地扩展。</span><span class="sxs-lookup"><span data-stu-id="f40ed-133">Scenarios ranged from wanting to run ad-blockers inside the container to boost browser performance to having the ability to run custom home-grown extensions inside the container.</span></span>

<span data-ttu-id="f40ed-134">从 Microsoft Edge 版本 81 开始，现在支持在容器中安装扩展。</span><span class="sxs-lookup"><span data-stu-id="f40ed-134">Extension installs in the container is now supported, starting from Microsoft Edge version 81.</span></span> <span data-ttu-id="f40ed-135">可通过策略控制此支持。</span><span class="sxs-lookup"><span data-stu-id="f40ed-135">This support can be controlled via policy.</span></span> <span data-ttu-id="f40ed-136">在 [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist) 策略中使用的 `updateURL` 应作为中性资源添加到应用程序防护使用的网络隔离策略中。</span><span class="sxs-lookup"><span data-stu-id="f40ed-136">The `updateURL` that gets used in [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist) policy should be added as Neutral Resources in the Network Isolation policies used by Application Guard.</span></span>

<span data-ttu-id="f40ed-137">容器支持的一些示例包括以下场景：</span><span class="sxs-lookup"><span data-stu-id="f40ed-137">Some examples of container support include the following scenarios:</span></span>

- <span data-ttu-id="f40ed-138">强制在主机上安装扩展</span><span class="sxs-lookup"><span data-stu-id="f40ed-138">Force installs of an extension on the host</span></span>
- <span data-ttu-id="f40ed-139">从主机中删除扩展</span><span class="sxs-lookup"><span data-stu-id="f40ed-139">Removing an extension from the host</span></span>
- <span data-ttu-id="f40ed-140">主机上阻止的扩展</span><span class="sxs-lookup"><span data-stu-id="f40ed-140">Extensions blocked on the host</span></span>

> [!NOTE]
> <span data-ttu-id="f40ed-141">也可以从扩展存储区中手动将单个扩展安装在容器内。</span><span class="sxs-lookup"><span data-stu-id="f40ed-141">It's also possible to manually install individual extensions inside the container from the extension store.</span></span> <span data-ttu-id="f40ed-142">手动安装的扩展仅在启用“[允许持久性](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/configure-md-app-guard#application-specific-settings)”策略时才保留在容器中。</span><span class="sxs-lookup"><span data-stu-id="f40ed-142">Manually installed extensions will only persist in the container when [Allow Persistence](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/configure-md-app-guard#application-specific-settings) policy is enabled.</span></span>

### <span data-ttu-id="f40ed-143">通过双代理识别应用程序防护流量</span><span class="sxs-lookup"><span data-stu-id="f40ed-143">Identifying Application Guard traffic via Dual Proxy</span></span>

<span data-ttu-id="f40ed-144">一些企业客户正在部署适用于特定用例的应用程序防护，他们需要识别来自 Microsoft Defender 应用程序防护容器的代理级别 web 流量。</span><span class="sxs-lookup"><span data-stu-id="f40ed-144">Some enterprise customers are deploying Application Guard with a specific use case where they need to identify web traffic coming out of a Microsoft Defender Application Guard container at the proxy level.</span></span> <span data-ttu-id="f40ed-145">从稳定渠道版本 84 开始，Microsoft Edge 将支持双代理来满足这一要求。</span><span class="sxs-lookup"><span data-stu-id="f40ed-145">Starting with Stable Channel version 84, Microsoft Edge will support dual proxy to address this requirement.</span></span> <span data-ttu-id="f40ed-146">可使用 [ApplicationGuardContainerProxy](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#applicationguardcontainerproxy) 策略配置此功能。</span><span class="sxs-lookup"><span data-stu-id="f40ed-146">You can configure this functionality using the [ApplicationGuardContainerProxy](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#applicationguardcontainerproxy) policy.</span></span>

<span data-ttu-id="f40ed-147">下图显示了 Microsoft Edge 双代理的体系结构。</span><span class="sxs-lookup"><span data-stu-id="f40ed-147">The following drawing shows the dual proxy architecture for Microsoft Edge.</span></span>

![应用程序防护的双代理体系结构](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-dual-proxy.png)

### <span data-ttu-id="f40ed-149">用于故障排除的诊断页面</span><span class="sxs-lookup"><span data-stu-id="f40ed-149">Diagnostic page for troubleshooting</span></span>

<span data-ttu-id="f40ed-150">用户的另一个痛点是在报告问题后对设备上的应用程序防护配置进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="f40ed-150">Another user pain point is troubleshooting the Application Guard configuration on a device when a problem is reported.</span></span> <span data-ttu-id="f40ed-151">Microsoft Edge 有一个诊断页面 (`edge://application-guard-internals`)，用于对用户问题进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="f40ed-151">Microsoft Edge has a diagnostics page (`edge://application-guard-internals`) to troubleshoot user issues.</span></span> <span data-ttu-id="f40ed-152">其中一个诊断功能是可以根据用户设备上的配置检查 URL 信任。</span><span class="sxs-lookup"><span data-stu-id="f40ed-152">One of these diagnostics is being able to check the URL trust based on the configuration on the user's device.</span></span>

<span data-ttu-id="f40ed-153">下一个屏幕截图显示了多选项卡诊断页面，用于帮助诊断用户在设备上报告的问题。</span><span class="sxs-lookup"><span data-stu-id="f40ed-153">The next screenshot shows a multiple tab diagnostics page to help diagnose user reported issues on the device.</span></span>

![应用程序防护诊断页面](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-2.png)

### <span data-ttu-id="f40ed-155">容器中的 Microsoft Edge 更新</span><span class="sxs-lookup"><span data-stu-id="f40ed-155">Microsoft Edge updates in the container</span></span>

<span data-ttu-id="f40ed-156">容器中的 Microsoft Edge 旧版更新是 Windows 操作系统更新周期的一部分。</span><span class="sxs-lookup"><span data-stu-id="f40ed-156">Microsoft Edge Legacy updates in the container are part of the Windows OS update cycle.</span></span> <span data-ttu-id="f40ed-157">由于新版本的 Microsoft Edge 更新独立于 Windows 操作系统，因此不再依赖于容器更新。</span><span class="sxs-lookup"><span data-stu-id="f40ed-157">Because the new version of Microsoft Edge updates itself independent of the Windows OS, there is no longer any dependency on container updates.</span></span> <span data-ttu-id="f40ed-158">主机 Microsoft Edge 的频道和版本可在容器内复制。</span><span class="sxs-lookup"><span data-stu-id="f40ed-158">The channel and version of the host Microsoft Edge is replicated inside the container.</span></span>

## <span data-ttu-id="f40ed-159">必备条件</span><span class="sxs-lookup"><span data-stu-id="f40ed-159">Prerequisites</span></span>

<span data-ttu-id="f40ed-160">以下要求适用于将应用程序防护与 Microsoft Edge 配合使用的设备：</span><span class="sxs-lookup"><span data-stu-id="f40ed-160">The following  requirements apply to devices using Application Guard with Microsoft Edge:</span></span>

- <span data-ttu-id="f40ed-161">Windows 10 1809 (RS5) 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="f40ed-161">Windows 10 1809 (RS5) and above.</span></span>
- <span data-ttu-id="f40ed-162">仅 Windows 客户端 SKU</span><span class="sxs-lookup"><span data-stu-id="f40ed-162">Only Windows client SKUs</span></span>

  > [!NOTE]
  > <span data-ttu-id="f40ed-163">应用程序防护仅在 Windows 10 专业版和 Windows 10 企业版 SKU 上受支持。</span><span class="sxs-lookup"><span data-stu-id="f40ed-163">Application Guard is only supported on Windows 10 Pro and Windows 10 Enterprise SKUs.</span></span>

- <span data-ttu-id="f40ed-164">[软件要求](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard#software-requirements)中介绍的管理解决方案之一</span><span class="sxs-lookup"><span data-stu-id="f40ed-164">One of the management solutions described in [Software requirements](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard#software-requirements)</span></span>

## <span data-ttu-id="f40ed-165">如何安装应用程序防护</span><span class="sxs-lookup"><span data-stu-id="f40ed-165">How to install Application Guard</span></span>

<span data-ttu-id="f40ed-166">以下文章提供了使用 Microsoft Edge 安装、配置和测试应用程序防护所需的信息。</span><span class="sxs-lookup"><span data-stu-id="f40ed-166">The following articles provide the information you need to install, configure, and test Application Guard with Microsoft Edge.</span></span>

- [<span data-ttu-id="f40ed-167">系统要求</span><span class="sxs-lookup"><span data-stu-id="f40ed-167">System requirements</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)
- [<span data-ttu-id="f40ed-168">安装 Microsoft Defender 应用程序防护</span><span class="sxs-lookup"><span data-stu-id="f40ed-168">Install Microsoft Defender Application Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)
- [<span data-ttu-id="f40ed-169">配置 Microsoft Defender 组策略设置</span><span class="sxs-lookup"><span data-stu-id="f40ed-169">Configure Microsoft Defender group policy settings</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/configure-md-app-guard)
- [<span data-ttu-id="f40ed-170">测试应用程序防护</span><span class="sxs-lookup"><span data-stu-id="f40ed-170">Test Application Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/test-scenarios-md-app-guard)

## <span data-ttu-id="f40ed-171">常见问题</span><span class="sxs-lookup"><span data-stu-id="f40ed-171">Frequently Asked Questions</span></span>

### <span data-ttu-id="f40ed-172">应用程序防护是否可在 IE 模式下工作？</span><span class="sxs-lookup"><span data-stu-id="f40ed-172">Does Application Guard work in IE Mode?</span></span>

<span data-ttu-id="f40ed-173">IE 模式支持应用程序防护功能，但我们预计不会在 IE 模式下过多地使用此功能。</span><span class="sxs-lookup"><span data-stu-id="f40ed-173">IE Mode supports Application Guard functionality, but we don't anticipate much use of this feature in IE Mode.</span></span> <span data-ttu-id="f40ed-174">建议为受信任的内部站点列表部署 IE 模式，而应用程序保护仅针对不受信任的站点。</span><span class="sxs-lookup"><span data-stu-id="f40ed-174">IE Mode is recommended to be deployed for a list of trusted internal sites, and Application Guard is for untrusted sites only.</span></span> <span data-ttu-id="f40ed-175">确保所有 IE 模式的网站或 IP 地址也添加到网络隔离策略中，以便应用程序防护将其视为受信任的资源。</span><span class="sxs-lookup"><span data-stu-id="f40ed-175">Make sure all the IE mode sites or IP addresses are also added to the Network Isolation policy to be considered as trusted resource by Application Guard.</span></span>

### <span data-ttu-id="f40ed-176">是否需要安装应用程序防护 Chrome 扩展？</span><span class="sxs-lookup"><span data-stu-id="f40ed-176">Do I need to install the Application Guard Chrome extension?</span></span>

<span data-ttu-id="f40ed-177">否，Microsoft Edge 本身支持应用程序防护功能。</span><span class="sxs-lookup"><span data-stu-id="f40ed-177">No, the Application Guard feature is natively supported in Microsoft Edge.</span></span> <span data-ttu-id="f40ed-178">实际上，应用程序防护 Chrome 扩展配置在 Microsoft Edge 中不受支持。</span><span class="sxs-lookup"><span data-stu-id="f40ed-178">In fact, the Application Guard Chrome extension isn't a supported configuration in Microsoft Edge.</span></span>

### <span data-ttu-id="f40ed-179">是否有其他与平台相关的常见问题？</span><span class="sxs-lookup"><span data-stu-id="f40ed-179">Are there any other platform related FAQs?</span></span>

<span data-ttu-id="f40ed-180">是。</span><span class="sxs-lookup"><span data-stu-id="f40ed-180">Yes.</span></span> [<span data-ttu-id="f40ed-181">常见问题 - Microsoft Defender 应用程序防护</span><span class="sxs-lookup"><span data-stu-id="f40ed-181">Frequently asked questions - Microsoft Defender Application Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/faq-md-app-guard) 

## <span data-ttu-id="f40ed-182">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f40ed-182">See also</span></span>

- [<span data-ttu-id="f40ed-183">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="f40ed-183">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="f40ed-184">安全性概述</span><span class="sxs-lookup"><span data-stu-id="f40ed-184">Security overview</span></span>](security-overview.md)
- [<span data-ttu-id="f40ed-185">Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="f40ed-185">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
