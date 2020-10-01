---
title: Microsoft Edge Enterprise Sync
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 09/30/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Enterprise Sync
ms.openlocfilehash: d5868fb496c036d750925bb5ae6dfa3de0293fd2
ms.sourcegitcommit: 8a4479a1b034c3c13ea03ee3a2374a1af332cb38
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2020
ms.locfileid: "11091944"
---
# <span data-ttu-id="7c1e1-103">Microsoft Edge Enterprise Sync</span><span class="sxs-lookup"><span data-stu-id="7c1e1-103">Microsoft Edge Enterprise Sync</span></span>

<span data-ttu-id="7c1e1-104">本文介绍如何使用 Microsoft Edge 同步你所有已登录设备上的收藏夹、密码和其他浏览器数据。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-104">This article explains how to use Microsoft Edge to sync your favorites, passwords, and other browser data across all your signed-in devices.</span></span>

> [!NOTE]
> <span data-ttu-id="7c1e1-105">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="7c1e1-106">概述</span><span class="sxs-lookup"><span data-stu-id="7c1e1-106">Overview</span></span>

<span data-ttu-id="7c1e1-107">通过 Microsoft Edge 同步，用户可以访问他们所有已登录设备上的浏览数据。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-107">Microsoft Edge sync enables users to access their browsing data across all their signed-in devices.</span></span> <span data-ttu-id="7c1e1-108">同步支持的数据包括：</span><span class="sxs-lookup"><span data-stu-id="7c1e1-108">The data supported by sync includes:</span></span>

- <span data-ttu-id="7c1e1-109">收藏夹</span><span class="sxs-lookup"><span data-stu-id="7c1e1-109">Favorites</span></span>
- <span data-ttu-id="7c1e1-110">密码</span><span class="sxs-lookup"><span data-stu-id="7c1e1-110">Passwords</span></span>
- <span data-ttu-id="7c1e1-111">地址等（表单填写）</span><span class="sxs-lookup"><span data-stu-id="7c1e1-111">Addresses and more (form-fill)</span></span>
- <span data-ttu-id="7c1e1-112">收藏</span><span class="sxs-lookup"><span data-stu-id="7c1e1-112">Collections</span></span>
- <span data-ttu-id="7c1e1-113">“设置”</span><span class="sxs-lookup"><span data-stu-id="7c1e1-113">Settings</span></span>

<span data-ttu-id="7c1e1-114">用户同意后即可启用同步功能，并且用户可以针对上面列出的每种数据类型打开或关闭同步功能。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-114">Sync functionality is enabled via user consent and users can turn sync on or off for each of the data types listed above.</span></span>

> [!NOTE]
> <span data-ttu-id="7c1e1-115">将上载其他设备连接和配置数据（如设备名称、品牌和型号），以支持同步功能。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-115">Additional device connectivity and configuration data (such as device name, make and model) is uploaded to support sync functionality.</span></span>

## <span data-ttu-id="7c1e1-116">必备条件</span><span class="sxs-lookup"><span data-stu-id="7c1e1-116">Prerequisites</span></span>

<span data-ttu-id="7c1e1-117">适用于 Azure Active Directory (Azure AD) 帐户的 Microsoft Edge 同步功能可供以下任何订阅使用：</span><span class="sxs-lookup"><span data-stu-id="7c1e1-117">Microsoft Edge sync for Azure Active Directory (Azure AD) accounts is available for any of the following subscriptions:</span></span>

- <span data-ttu-id="7c1e1-118">Azure AD Premium (P1 和 P2)</span><span class="sxs-lookup"><span data-stu-id="7c1e1-118">Azure AD Premium (P1 and P2)</span></span>
- <span data-ttu-id="7c1e1-119">M365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="7c1e1-119">M365 Business Premium</span></span>
- <span data-ttu-id="7c1e1-120">Office 365 E3 及更高版本</span><span class="sxs-lookup"><span data-stu-id="7c1e1-120">Office 365 E3 and above</span></span>
- <span data-ttu-id="7c1e1-121">Azure 信息保护 (AIP) (P1& P2)</span><span class="sxs-lookup"><span data-stu-id="7c1e1-121">Azure Information Protection (AIP) (P1& P2)</span></span>
- <span data-ttu-id="7c1e1-122">所有 EDU 订阅（Microsoft 教育应用版（学生）或 Microsoft 教育应用版（教职员工）、Exchange Online 学生版或教职员工版、O365 A1 或更高版本、M365 A1 或更高版本，或者适用于学生或教职员的 Azure 信息保护 P1 或 P2）</span><span class="sxs-lookup"><span data-stu-id="7c1e1-122">All EDU subscriptions (Microsoft Apps for Students or Faculty, Exchange Online for Students or Faculty, O365 A1 or above, M365 A1 or above, or Azure Information Protection P1 or P2 for Students or Faculty)</span></span>

## <span data-ttu-id="7c1e1-123">配置 Microsoft Edge 同步功能</span><span class="sxs-lookup"><span data-stu-id="7c1e1-123">Configuring Microsoft Edge sync</span></span>

<span data-ttu-id="7c1e1-124">可通过 Azure 信息保护 (AIP) 服务获取 Microsoft Edge 同步的配置选项。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-124">Configuration options for Microsoft Edge sync are available through the Azure Information Protection (AIP) service.</span></span> <span data-ttu-id="7c1e1-125">为租户启用 AIP 后，无论获得何种许可，所有用户均可同步 Microsoft Edge 数据。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-125">When AIP is enabled for a tenant, all users can sync Microsoft Edge data, regardless of licensing.</span></span> <span data-ttu-id="7c1e1-126">有关如何启用 AIP 的说明，请参阅[此处](https://docs.microsoft.com/azure/information-protection/activate-office365)。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-126">Instructions on how to enable AIP can be found [here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span>

<span data-ttu-id="7c1e1-127">若要限制某一组用户使用同步功能，可为这些用户启用 [AIP 登录控制策略](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps) 。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-127">To restrict sync to certain set of users, you can enable the [AIP onboarding control policy](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps) for those users.</span></span> <span data-ttu-id="7c1e1-128">如果确保所有必需的用户均加入后同步仍不可用，请确保已使用 [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps) PowerShell cmdlet 启用 IPCv3Service。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-128">If sync is still not available after ensuring that all necessary users are onboarded, ensure that the IPCv3Service is enabled using the [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps)  PowerShell cmdlet.</span></span>

> [!CAUTION]
> <span data-ttu-id="7c1e1-129">激活 Azure 信息保护还将允许其他应用程序（如 Microsoft Word 或 Microsoft Outlook）使用 AIP 保护内容。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-129">Activating Azure Information Protection will also allow other applications, such as Microsoft Word or Microsoft Outlook, to protect content with AIP.</span></span> <span data-ttu-id="7c1e1-130">此外，用于限制 Microsoft Edge 同步的任何载入控制策略也将限制其他应用程序使用 AIP 保护内容。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-130">In addition, any onboarding control policy used to restrict Edge sync will also restrict other applications from protecting content using AIP.</span></span>

## <span data-ttu-id="7c1e1-131">Microsoft Edge 和企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="7c1e1-131">Microsoft Edge and Enterprise State Roaming</span></span>

<span data-ttu-id="7c1e1-132">新版 Microsoft Edge 是跨平台应用程序，具有用于跨用户的所有设备同步用户数据的扩展作用域，并且不再是 Azure AD 企业状态漫游的一部分。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-132">The new Microsoft Edge is a cross-platform application with an expanded scope for syncing user data across all their devices and is no longer a part of Azure AD Enterprise State Roaming.</span></span> <span data-ttu-id="7c1e1-133">但是，新版 Microsoft Edge 将履行 ESR 的数据保护承诺，例如引入你自己的密钥的功能。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-133">However, the new Microsoft Edge will fulfill the data protection promises of ESR, such as the ability to bring your own key.</span></span> <span data-ttu-id="7c1e1-134">有关详细信息，请参阅 [Microsoft Edge 和企业状态漫游](microsoft-edge-enterprise-state-roaming.md)。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-134">For more information, see [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

## <span data-ttu-id="7c1e1-135">同步组策略</span><span class="sxs-lookup"><span data-stu-id="7c1e1-135">Sync group policies</span></span>

<span data-ttu-id="7c1e1-136">以下组策略会影响 Microsoft Edge 同步：</span><span class="sxs-lookup"><span data-stu-id="7c1e1-136">The following group policies impact Microsoft Edge sync:</span></span>

- <span data-ttu-id="7c1e1-137">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled)：完全禁用同步。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-137">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): Disables sync completely.</span></span>
- <span data-ttu-id="7c1e1-138">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled)：禁止保存浏览历史记录和同步。此策略还将禁用打开标签页同步。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-138">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): Disables saving browsing history and sync. This policy also disables open-tabs sync.</span></span>
- <span data-ttu-id="7c1e1-139">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled)：配置从同步中排除的类型列表。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-139">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): Configure the list of types that are excluded from synchronization.</span></span>
- <span data-ttu-id="7c1e1-140">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled)：允许 Active Directory (AD) 配置文件使用本地存储。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-140">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): Allow Active Directory (AD) profiles to use on-premises storage.</span></span> <span data-ttu-id="7c1e1-141">有关更多信息，请参阅 [Active Directory (AD) 用户的本地同步](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync)。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-141">For more information, see [On-premises sync for Active Directory (AD) users](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync).</span></span>
- <span data-ttu-id="7c1e1-142">[ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync)：默认启用同步，且无需用户同意即可同步。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-142">[ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): Turn sync on by default and do not require user consent to sync.</span></span>  

## <span data-ttu-id="7c1e1-143">常见问题</span><span class="sxs-lookup"><span data-stu-id="7c1e1-143">Frequently Asked Questions</span></span>

### <span data-ttu-id="7c1e1-144">安全性和服务器/数据合规性</span><span class="sxs-lookup"><span data-stu-id="7c1e1-144">SECURITY and SERVER/DATA COMPLIANCE</span></span>

#### <span data-ttu-id="7c1e1-145">已同步的数据是否已加密？</span><span class="sxs-lookup"><span data-stu-id="7c1e1-145">Is the synced data encrypted?</span></span> 

<span data-ttu-id="7c1e1-146">数据使用 TLS 1.2 或更高版本在传输中加密。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-146">The data is encrypted in transport using TLS 1.2 or greater.</span></span> <span data-ttu-id="7c1e1-147">大多数的数据类型在休眠时，都会在 Microsoft 服务中使用 AES256 进行额外的加密。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-147">Most data types are additionally encrypted at rest in Microsoft's service using AES256.</span></span> 

#### <span data-ttu-id="7c1e1-148">Microsoft Edge 的同步数据存储在哪里？</span><span class="sxs-lookup"><span data-stu-id="7c1e1-148">Where is Microsoft Edge sync data stored?</span></span>

<span data-ttu-id="7c1e1-149">Azure AD 帐户的同步数据将根据租户 ID 存储在安全服务器中。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-149">Synced data for Azure AD accounts is stored in secure servers according to the tenant ID.</span></span> <span data-ttu-id="7c1e1-150">例如，在美国注册的租户的数据存储在位于该地区地理位置的服务器上，并使用与 Office 应用程序相同的存储解决方案。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-150">For example, the data for a tenant that is registered in the United States is stored in servers geo-located for that region and uses the same storage solution as Office applications.</span></span>

#### <span data-ttu-id="7c1e1-151">除了同步至 Microsoft Edge 外，数据是否会离开 Microsoft 云？</span><span class="sxs-lookup"><span data-stu-id="7c1e1-151">Does the data ever leave Microsoft's cloud, aside from syncing to Microsoft Edge?</span></span>

<span data-ttu-id="7c1e1-152">否。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-152">No.</span></span>

#### <span data-ttu-id="7c1e1-153">租户管理员能否使用自己的密钥？</span><span class="sxs-lookup"><span data-stu-id="7c1e1-153">Can tenant admins bring their own key?</span></span>

<span data-ttu-id="7c1e1-154">可以，通过 [Azure 信息保护](https://azure.microsoft.com/services/information-protection/)。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-154">Yes, through [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>

#### <span data-ttu-id="7c1e1-155">企业同步属于哪项服务条款？</span><span class="sxs-lookup"><span data-stu-id="7c1e1-155">What terms of service does enterprise sync fall under?</span></span>

<span data-ttu-id="7c1e1-156">服务条款与 Azure AD 订阅的条款相同。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-156">The terms of service are the same terms as your Azure AD subscription.</span></span> <span data-ttu-id="7c1e1-157">所有 Azure AD 服务条款最终均属于 Microsoft 的[联机服务条款](https://www.microsoft.com/licensing/product-licensing/products)。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-157">All the Azure AD terms of service ultimately fall under Microsoft's [Online Service Terms](https://www.microsoft.com/licensing/product-licensing/products).</span></span>

#### <span data-ttu-id="7c1e1-158">Microsoft Edge 是否支持政府社区云 (GCC) 高合规性？</span><span class="sxs-lookup"><span data-stu-id="7c1e1-158">Does Microsoft Edge support Government Community Cloud (GCC) High compliance?</span></span>

<span data-ttu-id="7c1e1-159">目前尚不支持。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-159">Not today.</span></span> <span data-ttu-id="7c1e1-160">GCC 高合规性是 D 层，而 Microsoft Edge 最多支持 C 层。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-160">GCC High is Tier D, while Microsoft Edge supports up to Tier C.</span></span>

### <span data-ttu-id="7c1e1-161">应用同步</span><span class="sxs-lookup"><span data-stu-id="7c1e1-161">APPLYING SYNC</span></span>

#### <span data-ttu-id="7c1e1-162">对于决定保留旧版 Microsoft Edge 的企业和教育客户，将会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="7c1e1-162">What happens with enterprise and educational customers who decide to stay with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="7c1e1-163">当前版本的 Microsoft Edge 浏览器将继续加入 ESR 产品/服务。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-163">The current version of Microsoft Edge browser will continue to participate in the ESR offering.</span></span>

#### <span data-ttu-id="7c1e1-164">为什么需要高级 Azure AD 订阅才能进行同步？</span><span class="sxs-lookup"><span data-stu-id="7c1e1-164">Why do I need a premium Azure AD subscription to sync?</span></span>

<span data-ttu-id="7c1e1-165">企业同步依赖于 Azure 信息保护，它在所有 Azure AD 层中均不可用。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-165">Enterprise sync depends on Azure Information Protection, which is not available in all Azure AD tiers.</span></span>

#### <span data-ttu-id="7c1e1-166">Microsoft Edge 同步是否基于企业状态漫游？</span><span class="sxs-lookup"><span data-stu-id="7c1e1-166">Is Microsoft Edge sync based on Enterprise State Roaming?</span></span>

<span data-ttu-id="7c1e1-167">否。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-167">No.</span></span> <span data-ttu-id="7c1e1-168">ESR 可用于启用同步，但 Microsoft Edge 同步不是 ESR 的一部分。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-168">ESR can be used to enable sync, but Microsoft Edge sync is not a part of ESR.</span></span> <span data-ttu-id="7c1e1-169">有关详细信息，请参阅 [Microsoft Edge 同步](microsoft-edge-enterprise-sync.md)和 [Microsoft Edge 和企业状态漫游](microsoft-edge-enterprise-state-roaming.md)。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-169">For more information, see [Microsoft Edge Sync](microsoft-edge-enterprise-sync.md) and [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

#### <span data-ttu-id="7c1e1-170">Microsoft Edge 是否支持 Microsoft Edge 和 IE 之间的同步？</span><span class="sxs-lookup"><span data-stu-id="7c1e1-170">Will Microsoft Edge ever support syncing between Microsoft Edge and IE?</span></span>

<span data-ttu-id="7c1e1-171">尚无支持此同步的计划。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-171">There are no plans to support this syncing.</span></span> <span data-ttu-id="7c1e1-172">如果你的环境中仍需要 IE 来支持旧版应用，请考虑使用我们的[新 IE 模式](https://docs.microsoft.com/deployedge/edge-ie-mode)。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-172">If you still need IE in your environment to support legacy apps, consider our [new IE mode](https://docs.microsoft.com/deployedge/edge-ie-mode).</span></span>

#### <span data-ttu-id="7c1e1-173">新的 Microsoft Edge 浏览器是否将与 Microsoft Edge 旧版同步？</span><span class="sxs-lookup"><span data-stu-id="7c1e1-173">Will the new Microsoft Edge browser sync with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="7c1e1-174">否，不会同步。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-174">No, it won't.</span></span> <span data-ttu-id="7c1e1-175">我们认为连接这两个生态系统将降低新版 Microsoft Edge 同步的可靠性。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-175">We believe connecting these two ecosystems will lead to compromises in the reliability of sync in the new Microsoft Edge.</span></span> <span data-ttu-id="7c1e1-176">我们会确保将现有数据迁移到新版 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-176">We will ensure that existing data is migrated to the new Microsoft Edge.</span></span> <span data-ttu-id="7c1e1-177">用户还可以从他们选择的浏览器导入数据。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-177">Users will also be able to import data from browser of their choice.</span></span> <span data-ttu-id="7c1e1-178">这也意味着新版 Microsoft Edge 浏览器将无法与 IE 同步。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-178">This also means that new Microsoft Edge browser won't have a way to sync with IE.</span></span>

### <span data-ttu-id="7c1e1-179">管理同步</span><span class="sxs-lookup"><span data-stu-id="7c1e1-179">MANAGING SYNC</span></span>

#### <span data-ttu-id="7c1e1-180">是否可以阻止我的用户与个人租户同步？</span><span class="sxs-lookup"><span data-stu-id="7c1e1-180">Is it possible to stop my users from syncing with a personal tenant?</span></span>

<span data-ttu-id="7c1e1-181">无法直接阻止，但你可以使用 [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) 策略确定哪些配置文件可以登录到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="7c1e1-181">Not directly, but you can determine which profiles can sign on to Microsoft Edge using the [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) policy.</span></span>

## <span data-ttu-id="7c1e1-182">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c1e1-182">See also</span></span>

- [<span data-ttu-id="7c1e1-183">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="7c1e1-183">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="7c1e1-184">Microsoft Edge 和企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="7c1e1-184">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
