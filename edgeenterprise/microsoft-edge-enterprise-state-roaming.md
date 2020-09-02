---
title: Microsoft Edge 和企业状态漫游
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 02/14/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 和企业状态漫游
ms.openlocfilehash: a759b1d9d4be8dced7bfcc2ef8d0f23b514f4be0
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979368"
---
# <span data-ttu-id="98330-103">Microsoft Edge 和企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="98330-103">Microsoft Edge and Enterprise State Roaming</span></span>

<span data-ttu-id="98330-104">本文介绍了为更好地支持跨平台和设备同步，加入企业状态漫游 (ESR) 产品的 Microsoft Edge 进行了哪些更改。</span><span class="sxs-lookup"><span data-stu-id="98330-104">This article explains how Microsoft Edge participation in the Enterprise State Roaming (ESR) offering is changing to better support sync across platforms and devices.</span></span>

> [!NOTE]
> <span data-ttu-id="98330-105">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="98330-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="98330-106">简介</span><span class="sxs-lookup"><span data-stu-id="98330-106">Introduction</span></span>

<span data-ttu-id="98330-107">通过 Windows 10，[Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) 用户能够将其用户设置和应用程序设置数据安全地同步到云。</span><span class="sxs-lookup"><span data-stu-id="98330-107">With Windows 10, [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) users gained the ability to securely synchronize their user settings and application settings data to the cloud.</span></span> <span data-ttu-id="98330-108">[企业状态漫游 (ESR)](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) 还让用户在不同 Windows 设备上具有统一的体验，并缩短了配置新设备所需的时间。</span><span class="sxs-lookup"><span data-stu-id="98330-108">[Enterprise State Roaming (ESR)](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) provides users with a unified experience across their Windows devices and reduces the time needed for configuring a new device.</span></span>

<span data-ttu-id="98330-109">它的同步解决方案是采用 Chromium 平台的 Microsoft Edge 的一部分，现在已与 Windows 同步框架断开连接。</span><span class="sxs-lookup"><span data-stu-id="98330-109">As part of Microsoft Edge adopting the Chromium platform, its sync solution is now disconnected from Windows sync framework.</span></span> <span data-ttu-id="98330-110">这会影响到 Microsoft Edge 与 ESR 产品的关系。</span><span class="sxs-lookup"><span data-stu-id="98330-110">This affects the relationship of Microsoft Edge to the ESR offering.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="98330-111">新版 Microsoft Edge 未加入 ESR 产品。</span><span class="sxs-lookup"><span data-stu-id="98330-111">The new Microsoft Edge does not participate in the ESR offering.</span></span>

## <span data-ttu-id="98330-112">Microsoft Edge 有何变化？</span><span class="sxs-lookup"><span data-stu-id="98330-112">What’s changing with Microsoft Edge?</span></span>

<span data-ttu-id="98330-113">在新版 Microsoft Edge 中，同步解决方案不会绑定到 Windows 同步生态系统。</span><span class="sxs-lookup"><span data-stu-id="98330-113">With the new Microsoft Edge, the sync solution isn’t tied to Windows sync ecosystem.</span></span> <span data-ttu-id="98330-114">这使我们可以在所有平台上提供 Microsoft Edge，例如 Windows 7、Windows 8 .1、iOS、Android 和 macOS。</span><span class="sxs-lookup"><span data-stu-id="98330-114">This enables us to offer Microsoft Edge across all the platforms, such as Windows 7, Windows 8.1, iOS, Android and macOS.</span></span> <span data-ttu-id="98330-115">另外这还使我们可以为 Windows 上的非主要帐户提供同步。</span><span class="sxs-lookup"><span data-stu-id="98330-115">This also enables us to offer sync for non-primary accounts on Windows.</span></span> <span data-ttu-id="98330-116">此外，我们还可以使用比 Windows 更频繁且更灵活的发行节奏来交付 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="98330-116">In addition, we can ship Microsoft Edge at a more frequent and flexible release cadence than Windows.</span></span> <span data-ttu-id="98330-117">（有关详细信息，请参阅[用于支持下一版 Microsoft Edge 的 Windows 更新](microsoft-edge-sysupdate-windows-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="98330-117">(For more information, see [Windows updates to support the next version of Microsoft Edge](microsoft-edge-sysupdate-windows-updates.md).</span></span> <span data-ttu-id="98330-118">所有这些因素都突出显示了重新评估 Microsoft Edge 加入 ESR 产品的必要性。</span><span class="sxs-lookup"><span data-stu-id="98330-118">All these factors highlighted the need to re-assess Microsoft Edge participation in the ESR offering.</span></span>

<span data-ttu-id="98330-119">ESR 设计为 Windows 产品，其中包含对 Windows 设备中数据的处理方式的承诺，但 Microsoft Edge 同步将不局限于 Windows 设备。</span><span class="sxs-lookup"><span data-stu-id="98330-119">ESR is framed as a Windows product offering with promises about how data from Windows devices is handled, but Microsoft Edge sync will extend beyond Windows devices.</span></span> <span data-ttu-id="98330-120">此外，随着数据在这些设备之间漫游，在 ESR 上下文中定义 Microsoft Edge 同步产品会很困难。</span><span class="sxs-lookup"><span data-stu-id="98330-120">And, as the data roams across these devices, it makes it difficult to define the Microsoft Edge sync offering in the context of ESR.</span></span> <span data-ttu-id="98330-121">为了简化同步的工作和管理方式，以及为了适应突出显示的更改，我们已决定让 Microsoft Edge 退出 ESR 产品。</span><span class="sxs-lookup"><span data-stu-id="98330-121">To simplify how sync works and is managed, and to accommodate the changes that are highlighted, a decision was made to pull Microsoft Edge out of the ESR offering.</span></span>

## <span data-ttu-id="98330-122">这是否意味着企业不再具备 ESR 所提供的功能？</span><span class="sxs-lookup"><span data-stu-id="98330-122">Does this mean Enterprises will lose the abilities they had as part of ESR?</span></span>

<span data-ttu-id="98330-123">否。</span><span class="sxs-lookup"><span data-stu-id="98330-123">No.</span></span> <span data-ttu-id="98330-124">Microsoft Edge 将继续支持 ESR 产品中提供的大部分功能。</span><span class="sxs-lookup"><span data-stu-id="98330-124">Microsoft Edge will continue to support most of the abilities provided in the ESR offering.</span></span>

### <span data-ttu-id="98330-125">设备间的统一体验和新的设备配置时间</span><span class="sxs-lookup"><span data-stu-id="98330-125">Unified experience across devices and new device configuration time</span></span>

<span data-ttu-id="98330-126">当用户使用 Azure Active Directory（Azure AD 帐户）登录到自己的 Windows 设备时，Microsoft Edge 将在首次启动新浏览器时隐式继承该标识。</span><span class="sxs-lookup"><span data-stu-id="98330-126">When a user is signed into their windows device with an Azure Active Directory (Azure AD account), Microsoft Edge will implicitly inherit that Identity on first launch of the new browser.</span></span>

<span data-ttu-id="98330-127">在用户明确同意在新版 Microsoft Edge 中打开同步后，浏览器将同步所有浏览器数据，如收藏夹、密码和历史记录。</span><span class="sxs-lookup"><span data-stu-id="98330-127">After a user has explicitly consented to turning on sync in the new Microsoft Edge, the browser will sync all the browser data, such as favorites, passwords, and history.</span></span> <span data-ttu-id="98330-128">这确保了可获得跨设备统一体验，并缩短了个性化设置浏览器所需的时间。</span><span class="sxs-lookup"><span data-stu-id="98330-128">This ensures a unified experience across devices and reduces the time needed to personalize the browser.</span></span>

### <span data-ttu-id="98330-129">分离公司和消费者数据</span><span class="sxs-lookup"><span data-stu-id="98330-129">Separation of corporate and consumer data</span></span>

<span data-ttu-id="98330-130">组织拥有其数据的控制权，不会在消费者云帐户中掺混公司数据，也不会在企业云帐户中掺混消费者数据。</span><span class="sxs-lookup"><span data-stu-id="98330-130">Organizations are in control of their data, and there is no mixing of corporate data in a consumer cloud account or consumer data in an enterprise cloud account.</span></span>

### <span data-ttu-id="98330-131">增强的安全性</span><span class="sxs-lookup"><span data-stu-id="98330-131">Enhanced security</span></span>

<span data-ttu-id="98330-132">在数据离开用户 Windows 10 设备之前通过使用 Azure 信息保护自动对其加密，并且数据在云中保持静态加密状态。</span><span class="sxs-lookup"><span data-stu-id="98330-132">Data is automatically encrypted before leaving the user’s Windows 10 device by using Azure Information Protection, and data stays encrypted at rest in the cloud.</span></span> <span data-ttu-id="98330-133">所有内容在云（命名空间除外）中保持静态加密，例如设置名称。</span><span class="sxs-lookup"><span data-stu-id="98330-133">All content stays encrypted at rest in the cloud, except for the namespaces, like settings names.</span></span>

### <span data-ttu-id="98330-134">监视</span><span class="sxs-lookup"><span data-stu-id="98330-134">Monitoring</span></span>

<span data-ttu-id="98330-135">我们将通过与 Azure AD 门户集成，控制并显示贵组织中的哪些人在哪些设备中同步设置。</span><span class="sxs-lookup"><span data-stu-id="98330-135">We will provide control and visibility over who syncs settings in your organization and on which devices through integration with the Azure AD portal.</span></span> <span data-ttu-id="98330-136">在未来版本中将启用该功能。</span><span class="sxs-lookup"><span data-stu-id="98330-136">This capability will be enabled in a future release.</span></span>

### <span data-ttu-id="98330-137">管理</span><span class="sxs-lookup"><span data-stu-id="98330-137">Management</span></span>

<span data-ttu-id="98330-138">管理员将可控制贵组织中的哪些成员能够启用同步。请参阅 [Microsoft Edge 同步的配置选项](microsoft-edge-enterprise-sync.md#configuration-options-for-microsoft-edge-sync)和[同步组策略](microsoft-edge-enterprise-sync.md#sync-group-policies)。</span><span class="sxs-lookup"><span data-stu-id="98330-138">Admins will be able to control which members in your organization can enable sync. See [Configuration options for Microsoft Edge sync](microsoft-edge-enterprise-sync.md#configuration-options-for-microsoft-edge-sync) and [Sync group policies](microsoft-edge-enterprise-sync.md#sync-group-policies).</span></span> <span data-ttu-id="98330-139">此外，用户可以针对每台设备打开/关闭同步，并分别切换每个数据属性以进行同步。</span><span class="sxs-lookup"><span data-stu-id="98330-139">Additionally, users can turn sync on/off for each of their devices as well as toggle each data attribute individually for sync.</span></span>

### <span data-ttu-id="98330-140">密钥管理</span><span class="sxs-lookup"><span data-stu-id="98330-140">Key management</span></span>

<span data-ttu-id="98330-141">同步功能利用 Azure 信息保护 (AIP)，仅为用户和企业管理员保护同步数据。</span><span class="sxs-lookup"><span data-stu-id="98330-141">The synchronization feature leverages Azure Information Protection (AIP) to protect the synchronized data for only the user and the enterprise admins.</span></span> <span data-ttu-id="98330-142">AIP 既支持 Microsoft 托管（默认），也引入了你自己的密钥以用于云密钥管理。</span><span class="sxs-lookup"><span data-stu-id="98330-142">AIP supports both Microsoft managed (default) and bring your own key for cloud-key management.</span></span> <span data-ttu-id="98330-143">贵组织使用的云密钥管理策略对于 Microsoft Edge 是透明的，对同步功能没有任何影响。</span><span class="sxs-lookup"><span data-stu-id="98330-143">The cloud-key management strategy your organization uses is transparent to Microsoft Edge and has no impact on the synchronization feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="98330-144">[保留自己的密钥 (HYOK)](https://docs.microsoft.com/azure/information-protection/configure-adrms-restrictions)，但不支持 Active Directory Rights Management Service。</span><span class="sxs-lookup"><span data-stu-id="98330-144">[Hold your own key (HYOK)](https://docs.microsoft.com/azure/information-protection/configure-adrms-restrictions) and the Active Directory Rights Management Service aren't supported.</span></span>

## <span data-ttu-id="98330-145">同步属性摘要</span><span class="sxs-lookup"><span data-stu-id="98330-145">Summary of sync attributes</span></span>

<span data-ttu-id="98330-146">以下数据属性将在新版本 Microsoft Edge 首次启动时同步：</span><span class="sxs-lookup"><span data-stu-id="98330-146">The following data attributes will sync in the new version of Microsoft Edge at first launch:</span></span>

- <span data-ttu-id="98330-147">收藏夹</span><span class="sxs-lookup"><span data-stu-id="98330-147">Favorites</span></span>
- <span data-ttu-id="98330-148">密码</span><span class="sxs-lookup"><span data-stu-id="98330-148">Passwords</span></span>
- <span data-ttu-id="98330-149">表单填写</span><span class="sxs-lookup"><span data-stu-id="98330-149">Form-fill</span></span>
- <span data-ttu-id="98330-150">历史记录</span><span class="sxs-lookup"><span data-stu-id="98330-150">History</span></span>
- <span data-ttu-id="98330-151">打开标签页（会话）</span><span class="sxs-lookup"><span data-stu-id="98330-151">Open tabs (sessions)</span></span>
- <span data-ttu-id="98330-152">设置（首选项）</span><span class="sxs-lookup"><span data-stu-id="98330-152">Settings (preferences)</span></span>
- <span data-ttu-id="98330-153">扩展</span><span class="sxs-lookup"><span data-stu-id="98330-153">Extensions</span></span>

<span data-ttu-id="98330-154">前述属性列表不同于可在 Microsoft Edge 旧版中同步的属性。</span><span class="sxs-lookup"><span data-stu-id="98330-154">The preceding list of attributes is different than the attributes that could be synced in Microsoft Edge Legacy.</span></span> <span data-ttu-id="98330-155">（有关 Microsoft Edge 旧版设置的详细信息，请参阅 [Windows 10 漫游设置](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-windows-settings-reference)）。用户可以使用 Microsoft Edge 设置有选择地启用/禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="98330-155">(For details about Microsoft Edge Legacy settings, see [Windows 10 roaming settings](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-windows-settings-reference).) Users can selectively enable/disable these attributes using Microsoft Edge settings.</span></span> <span data-ttu-id="98330-156">鉴于两个版本之间属性（如“历史记录”）的不同，系统可能会要求用户再次授予同步许可。</span><span class="sxs-lookup"><span data-stu-id="98330-156">Given the difference in attributes between the two versions (for example, history), users might be asked to give sync consent again.</span></span>

> [!NOTE]
> <span data-ttu-id="98330-157">与 Microsoft Edge 旧版不同的是，新版 Microsoft Edge 不会使用 Windows 凭据管理器中的密码，因此不会将密码与 Internet Explorer 或其他使用 Windows 凭据管理器的应用程序同步。</span><span class="sxs-lookup"><span data-stu-id="98330-157">Unlike Microsoft Edge Legacy, the new Microsoft Edge doesn't use Windows credential Manager for passwords and as a result, won't sync passwords with Internet Explorer or other apps that use Windows Credential manager.</span></span>

## <span data-ttu-id="98330-158">服务条款</span><span class="sxs-lookup"><span data-stu-id="98330-158">Terms of service</span></span>

<span data-ttu-id="98330-159">Microsoft Edge 同步服务条款已列入 Microsoft 软件许可证，可使用 Microsoft Edge 访问 *edge://terms* 进行查看。</span><span class="sxs-lookup"><span data-stu-id="98330-159">Terms of service for Microsoft Edge sync falls under the Microsoft software license viewable in Microsoft Edge at *edge://terms*.</span></span>

## <span data-ttu-id="98330-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98330-160">See also</span></span>

- [<span data-ttu-id="98330-161">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="98330-161">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="98330-162">Microsoft Edge 同步</span><span class="sxs-lookup"><span data-stu-id="98330-162">Microsoft Edge Sync</span></span>](microsoft-edge-enterprise-sync.md)