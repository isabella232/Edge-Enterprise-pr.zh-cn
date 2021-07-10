---
title: 适用于虚拟化桌面基础结构的 Edge
ms.author: anlake
author: AndreaLBarr
manager: collw
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 适用于虚拟化桌面基础结构的 Microsoft Edge。
ms.openlocfilehash: 5dc234b0e6fbba4778f8236399a0ff438f704578
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641848"
---
# <a name="microsoft-edge-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="4b0c5-103">适用于虚拟化桌面基础结构的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="4b0c5-103">Microsoft Edge for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="4b0c5-104">本文介绍在虚拟化环境中使用 Microsoft Edge 的要求和限制。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-104">This article describes the requirements and limitations for using Microsoft Edge in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="4b0c5-105">什么是 VDI？</span><span class="sxs-lookup"><span data-stu-id="4b0c5-105">What is VDI?</span></span>

<span data-ttu-id="4b0c5-106">虚拟桌面基础结构 (VDI) 是一种虚拟化技术，可在数据中心的集中式服务器上托管桌面操作系统和应用程序。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="4b0c5-107">这为具有完全安全且合规的集中式源的用户提供完全个性化的桌面体验。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-107">This enables a fully personalized desktop experience for users with a fully secured and compliant centralized source.</span></span>

<span data-ttu-id="4b0c5-108">Microsoft Edge 可在此类虚拟化环境中使用的方式与在本地设备上使用的方式大致相同，同时从安全和受控的服务器环境运行。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-108">Microsoft Edge can be used in such a virtualized environment in much the same ways as it can be used on the local device, all the while running from secure and controlled server environment.</span></span> <span data-ttu-id="4b0c5-109">根据所选的 VDI 解决方案，还可能为用户提供对 Intranet 应用程序和网站的无缝访问权限。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-109">Depending on your chosen VDI solution it may also be possible to give your users seamless access to intranet Applications and Sites.</span></span>

<span data-ttu-id="4b0c5-110">没有任何特殊配置的 VDI 环境支持 Edge 的大多数功能。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-110">Most features of Edge are supported on VDI environments without any special configuration.</span></span> <span data-ttu-id="4b0c5-111">但是，为了确保获得最佳体验，建议遵循以下指南。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-111">However, to ensure an optimal experience it’s recommended to follow the guidance below.</span></span>

## <a name="platforms-certified-for-edge"></a><span data-ttu-id="4b0c5-112">Microsoft Edge 认证的平台</span><span class="sxs-lookup"><span data-stu-id="4b0c5-112">Platforms certified for Edge</span></span>

- <span data-ttu-id="4b0c5-113">Azure 虚拟桌面</span><span class="sxs-lookup"><span data-stu-id="4b0c5-113">Azure Virtual Desktop</span></span>
- <span data-ttu-id="4b0c5-114">Citrix 虚拟应用和桌面（以前称为 XenApp 和 XenDesktop）</span><span class="sxs-lookup"><span data-stu-id="4b0c5-114">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop)</span></span>

<span data-ttu-id="4b0c5-115">虽然 Edge 团队尚未验证其他 VDI 解决方案，但预期应支持 Edge 中最常见的工作流。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-115">While other VDI solutions have not yet been verified by the Edge team, it is expected that the most common workflows in Edge should be supported.</span></span> <span data-ttu-id="4b0c5-116">下面提供的指南可能适用于所选解决方案，也可能不适用于所选解决方案。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-116">Guidance provided below may or may not be applicable to your chosen solution.</span></span>

## <a name="edge-on-vdi-performance-considerations"></a><span data-ttu-id="4b0c5-117">Edge on VDI 性能注意事项</span><span class="sxs-lookup"><span data-stu-id="4b0c5-117">Edge on VDI performance considerations</span></span>

<span data-ttu-id="4b0c5-118">设计 VDI 环境时，应仔细考虑用户的工作流和需求，以实现最佳性能，以及服务器配置的限制。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-118">When designing your VDI environment you should carefully consider the workflows and needs of your users to achieve optimal performance, as well as the limits of your server configuration.</span></span>

<span data-ttu-id="4b0c5-119">对于将 Edge 部署到 VDI 环境，Edge 建议满足以下最低要求：</span><span class="sxs-lookup"><span data-stu-id="4b0c5-119">Edge recommends the following minimal requirements for deploying Edge to VDI environments:</span></span>

- <span data-ttu-id="4b0c5-120">vCPU - 每个用户 2 - 4 个核心</span><span class="sxs-lookup"><span data-stu-id="4b0c5-120">vCPU – 2-4 Cores per User</span></span>
- <span data-ttu-id="4b0c5-121">RAM - 每个用户 1 GB</span><span class="sxs-lookup"><span data-stu-id="4b0c5-121">RAM – 1 GB per User</span></span>

<span data-ttu-id="4b0c5-122">请注意，大型复杂的 Web 应用程序和扩展需要更多内存，配置环境时必须将这一点考虑在内。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-122">Please note that large complex web applications and extensions will require more memory and will have to be accounted for when configuring your environment.</span></span>

## <a name="edge-on-non-persisted-vdi-environments"></a><span data-ttu-id="4b0c5-123">非持久化 VDI 环境中的 Edge</span><span class="sxs-lookup"><span data-stu-id="4b0c5-123">Edge on non-persisted VDI environments</span></span>

<span data-ttu-id="4b0c5-124">许多 VDI 解决方案都允许访问持久化环境和非持久化环境。在持久化环境中，用户分配有一个在会话之间持续存在的虚拟环境，而在非持久化环境中，则将用户分配到多个可用计算机之一（每个会话的计算机都可能不同），在会话之间用户数据可能同步，也可能不同步。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-124">Many VDI solutions allow access to persisted environments, where users are assigned a virtual environment that persists between sessions, and non-persisted environments, where users are assigned to one of several available machines, possibly a different machine each session, user data may or may not sync between sessions.</span></span>

<span data-ttu-id="4b0c5-125">使用非持久化环境时，通常会创建一个“黄金映像”，用于包含所需应用和配置的每个设备。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-125">When using a non-persisted environment, one usually creates a “golden image” which is used for each device that includes the needed apps and configurations.</span></span> <span data-ttu-id="4b0c5-126">下面是我们对于为此类映像准备 Edge 的建议。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-126">Below are our recommendations for preparing Edge for such an image.</span></span>

### <a name="deploy-edge"></a><span data-ttu-id="4b0c5-127">部署 Edge</span><span class="sxs-lookup"><span data-stu-id="4b0c5-127">Deploy Edge</span></span>

<span data-ttu-id="4b0c5-128">如果使用的是 Windows 10 版本 1803 及更高版本，则应已在系统上安装 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-128">If you are on Windows 10, version 1803 and above, you should have Microsoft Edge installed on your system.</span></span> <span data-ttu-id="4b0c5-129">但是，如果你使用的是较旧版本的 Windows 或希望部署不同的 Edge 通道，则建议执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-129">However, if you are on an older version of Windows or wish to deploy a different channel of Edge, the following steps are recommended.</span></span>

1. <span data-ttu-id="4b0c5-130">从以下位置下载与 VDI VM 操作系统匹配的 Edge MSI 包：</span><span class="sxs-lookup"><span data-stu-id="4b0c5-130">Download the Edge MSI package matching your VDI VM operating system from:</span></span>

    - [<span data-ttu-id="4b0c5-131">下载适用于企业的 Microsoft Edge - Microsoft</span><span class="sxs-lookup"><span data-stu-id="4b0c5-131">Download Microsoft Edge for Business - Microsoft</span></span>](https://www.microsoft.com/edge/business/download)

2. <span data-ttu-id="4b0c5-132">通过运行以下命令将 MSI 安装到 VDI VM：</span><span class="sxs-lookup"><span data-stu-id="4b0c5-132">Install the MSI to the VDI VM by running the following command:</span></span>

    - `msiexec /i <path_to_msi> /qn /norestart /l*v <install_logfile_name>`

### <a name="disable-automatic-updates"></a><span data-ttu-id="4b0c5-133">禁用自动更新</span><span class="sxs-lookup"><span data-stu-id="4b0c5-133">Disable automatic updates</span></span>

<span data-ttu-id="4b0c5-134">对于非持久化计算机，最佳做法是禁用自动更新，而是并改为通过更新“黄金映像”来更新 Edge，以确保计算机池之间没有版本不匹配的情况。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-134">For non-persisted machines it is best practice to disable automatic updates and instead update Edge by updating the “golden image” to ensure that there are no version mismatches among the pool of machines.</span></span>

<span data-ttu-id="4b0c5-135">请参阅以下用于禁用自动更新的策略：</span><span class="sxs-lookup"><span data-stu-id="4b0c5-135">See the following policies for disabling automatic updates:</span></span>

- [<span data-ttu-id="4b0c5-136">更新策略替代默认值</span><span class="sxs-lookup"><span data-stu-id="4b0c5-136">Update policy override default</span></span>](/deployedge/microsoft-edge-update-policies#updatedefault)

- [<span data-ttu-id="4b0c5-137">更新策略替代</span><span class="sxs-lookup"><span data-stu-id="4b0c5-137">Update policy override</span></span>](/deployedge/microsoft-edge-update-policies#update)

### <a name="profile-management"></a><span data-ttu-id="4b0c5-138">配置文件管理</span><span class="sxs-lookup"><span data-stu-id="4b0c5-138">Profile management</span></span>

<span data-ttu-id="4b0c5-139">在非持久化设置上，请务必考虑 VM 可能无法在会话之间保持用户状态，或者可能会为用户分配一个以前从未使用过的 VM，因此没有其任何用户数据。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-139">On non-persisted setups it is important to consider that VMs may not maintain user state between sessions or users may be assigned a VM they have never used before and as such has none of their user data.</span></span>

<span data-ttu-id="4b0c5-140">Edge 支持几种同步用户数据的方法，以便无论用户以何种方式访问 Edge，数据都是可用的。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-140">Edge supports several methods for syncing user data such that it is available regardless of how they are accessing Edge.</span></span>

### <a name="azure-ad-sync"></a><span data-ttu-id="4b0c5-141">Azure AD Sync</span><span class="sxs-lookup"><span data-stu-id="4b0c5-141">Azure AD Sync</span></span>

<span data-ttu-id="4b0c5-142">如果 Azure AD 计划支持，则企业同步是确保将 Edge 用户数据同步到所有用户设备的最快和最简单的方法。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-142">If your Azure AD plan supports it, Enterprise sync is the fastest and easiest method to ensure that Edge user data is synced to all user devices.</span></span>  

<span data-ttu-id="4b0c5-143">有关要求和配置的详细信息，请参阅以下内容。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-143">See the following for more information on requirements and configuration.</span></span>  

- [<span data-ttu-id="4b0c5-144">配置 Microsoft Edge 企业同步 | Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="4b0c5-144">Configure Microsoft Edge enterprise sync | Microsoft Docs</span></span>](/deployedge/microsoft-edge-enterprise-sync)

### <a name="on-premise-sync-for-active-directory-users"></a><span data-ttu-id="4b0c5-145">Active Directory 用户的本地同步</span><span class="sxs-lookup"><span data-stu-id="4b0c5-145">On-premise Sync for Active Directory Users</span></span>

<span data-ttu-id="4b0c5-146">通过本地同步，Microsoft Edge 将 Active Directory 用户的收藏夹和设置保存到可轻松在不同计算机之间移动的文件中。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-146">With on-premises sync, Microsoft Edge saves an Active Directory user's favorites and settings to a file that can easily be moved between different computers.</span></span>  

<span data-ttu-id="4b0c5-147">有关要求和配置的详细信息，请参阅以下内容。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-147">See the following for more information on requirements and configuration.</span></span>  

- [<span data-ttu-id="4b0c5-148">Active Directory (AD) 用户的本地同步 | Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="4b0c5-148">On-premises sync for Active Directory (AD) users | Microsoft Docs</span></span>](/deployedge/microsoft-edge-on-premises-sync)

### <a name="user-profile-redirection"></a><span data-ttu-id="4b0c5-149">用户配置文件重定向</span><span class="sxs-lookup"><span data-stu-id="4b0c5-149">User Profile Redirection</span></span>  

<span data-ttu-id="4b0c5-150">有多个解决方案用于迁移和重定向整个用户文件夹，以确保在此类非持久化环境中维护用户上下文。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-150">There are several solutions for migrating and redirecting the entire user folder to ensure that user context is maintained in such non-persisted environments.</span></span> <span data-ttu-id="4b0c5-151">请咨询 VDI 提供商以确定建议的解决方案。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-151">Check with your VDI provider to determine the recommended solution.</span></span>

<span data-ttu-id="4b0c5-152">一些热门解决方案包括：</span><span class="sxs-lookup"><span data-stu-id="4b0c5-152">Some popular solutions include:</span></span>

- [<span data-ttu-id="4b0c5-153">FSLogix 概述 - FSLogix |Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="4b0c5-153">FSLogix Overview - FSLogix | Microsoft Docs</span></span>](/fslogix/overview)
- [<span data-ttu-id="4b0c5-154">如何配置 Citrix 配置文件管理</span><span class="sxs-lookup"><span data-stu-id="4b0c5-154">How to Configure Citrix Profile Management</span></span>](https://support.citrix.com/article/CTX222893)

<span data-ttu-id="4b0c5-155">此外，建议在使用此方法时从备份的用户文件夹中排除不必要的文件夹，以减少用户登录到计算机并且正在迁移配置文件时的初始加载时间。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-155">It is also may be recommended that when using this method unnecessary folders be excluded from the backed-up user folder to reduce initial loading times when users are logging on to a machine and the profile is being migrated.</span></span> <span data-ttu-id="4b0c5-156">如果这样操作，我们建议从备份中排除以下文件夹以减小大小。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-156">If so, we recommend the following folders be excluded from your backup to reduce size.</span></span>

- <span data-ttu-id="4b0c5-157">%LocalAppData%\Microsoft\Edge\User Data\Default\Cache</span><span class="sxs-lookup"><span data-stu-id="4b0c5-157">%LocalAppData%\Microsoft\Edge\User Data\Default\Cache</span></span>
- <span data-ttu-id="4b0c5-158">%LocalAppData%\Microsoft\Edge\User Data\Default\Code Cache</span><span class="sxs-lookup"><span data-stu-id="4b0c5-158">%LocalAppData%\Microsoft\Edge\User Data\Default\Code Cache</span></span>
- <span data-ttu-id="4b0c5-159">%LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsTopSites</span><span class="sxs-lookup"><span data-stu-id="4b0c5-159">%LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsTopSites</span></span>
- <span data-ttu-id="4b0c5-160">%LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsRecentClosed</span><span class="sxs-lookup"><span data-stu-id="4b0c5-160">%LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsRecentClosed</span></span>

## <a name="known-issues"></a><span data-ttu-id="4b0c5-161">已知问题</span><span class="sxs-lookup"><span data-stu-id="4b0c5-161">Known issues</span></span>

### <a name="microsoft-edge-crashes-in-older-versions-of-xenapp-and-xendesktop"></a><span data-ttu-id="4b0c5-162">Microsoft Edge 在旧版 XenApp 和 XenDesktop 中崩溃</span><span class="sxs-lookup"><span data-stu-id="4b0c5-162">Microsoft Edge crashes in older versions of XenApp and XenDesktop</span></span>

<span data-ttu-id="4b0c5-163">此问题应在较新版本中得到缓解，但如果在你的环境中遇到此问题，可以通过禁用适用于 Edge 的 Citrix API 挂钩来解决此问题，请参阅 [如何在每个应用程序的基础上禁用 Citrix API 挂钩。](https://support.citrix.com/article/CTX107825)</span><span class="sxs-lookup"><span data-stu-id="4b0c5-163">This issue should be mitigated in newer versions however if you are encountering this issue in your environment, you can work around the issue by disabling Citrix API Hooks for Edge, see [How to Disable Citrix API Hooks on a Per-application Basis.](https://support.citrix.com/article/CTX107825)</span></span>

### <a name="degraded-performance-when-rendering-pages-with-exceptionally-large-html-tables"></a><span data-ttu-id="4b0c5-164">呈现具有超大 HTML 表的页面时性能下降</span><span class="sxs-lookup"><span data-stu-id="4b0c5-164">Degraded performance when rendering pages with exceptionally large HTML tables</span></span>

<span data-ttu-id="4b0c5-165">已知以下 Citrix 策略会降低具有非常大（超过 30,000 行）表的 html 页的呈现速度。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-165">The following Citrix policies are known to slow rendering of html pages with very large (30,000+ row) tables.</span></span>

- <span data-ttu-id="4b0c5-166">自动键盘显示</span><span class="sxs-lookup"><span data-stu-id="4b0c5-166">Automatic keyboard display</span></span>
- <span data-ttu-id="4b0c5-167">远程组合框</span><span class="sxs-lookup"><span data-stu-id="4b0c5-167">Remote the combo box</span></span>

<span data-ttu-id="4b0c5-168">有关详细信息，请参阅 [移动体验策略设置 (citrix.com)](https://docs.citrix.com/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/mobile-experience-policy-settings.html)。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-168">See [Mobile experience policy settings (citrix.com)](https://docs.citrix.com/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/mobile-experience-policy-settings.html) for more information.</span></span> <span data-ttu-id="4b0c5-169">禁用这些策略应该可以缓解此问题。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-169">Disabling these policies should mitigate the issue.</span></span>

### <a name="windows-account-manager-authorization-scenarios-ie--azure-sync-fail-in-edge-when-run-as-a-citrix-seamless-application"></a><span data-ttu-id="4b0c5-170">作为 Citrix 无缝应用程序，Windows 帐户管理器授权方案（即 Azure 同步）在 Edge 中失败</span><span class="sxs-lookup"><span data-stu-id="4b0c5-170">Windows Account Manager authorization scenarios (i.e.  Azure sync) fail in Edge when run as a Citrix seamless application</span></span>

<span data-ttu-id="4b0c5-171">这是 Edge 和其他使用 WAM（即 Office）的应用程序中的一个已知问题，因为在“无缝”模式下运行时，此类方案所必需的 Windows 组件未初始化。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-171">This is a known issue in Edge and other applications that use WAM (i.e. Office) due to Windows components necessary for such scenarios not being initialized when running in the “seamless” mode.</span></span> <span data-ttu-id="4b0c5-172">要解决此问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4b0c5-172">To work around this issue:</span></span>

- <span data-ttu-id="4b0c5-173">通过远程桌面将 Edge 用于 Citrix 主机，而不是用作无缝远程应用程序。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-173">Use Edge via a Remote Desktop to the Citrix Host instead of as a seamless remote application.</span></span>
- <span data-ttu-id="4b0c5-174">请改用 Azure 虚拟桌面远程应用，这可以缓解此问题。</span><span class="sxs-lookup"><span data-stu-id="4b0c5-174">Use Azure Virtual Desktop remote apps instead, which has mitigation's for this issue.</span></span>
