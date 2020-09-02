---
title: Microsoft Edge Enterprise Sync
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 08/03/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Enterprise Sync
ms.openlocfilehash: a6d01356db478871a7c6b386bbb731b32dc4739a
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979357"
---
# <span data-ttu-id="bdd7e-103">Microsoft Edge Enterprise Sync</span><span class="sxs-lookup"><span data-stu-id="bdd7e-103">Microsoft Edge Enterprise Sync</span></span>

<span data-ttu-id="bdd7e-104">本文介绍如何使用 Microsoft Edge 同步你所有已登录设备上的收藏夹、密码和其他浏览器数据。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-104">This article explains how to use Microsoft Edge to sync your favorites, passwords, and other browser data across all your signed-in devices.</span></span>

> [!NOTE]
> <span data-ttu-id="bdd7e-105">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="bdd7e-106">概述</span><span class="sxs-lookup"><span data-stu-id="bdd7e-106">Overview</span></span>

<span data-ttu-id="bdd7e-107">通过 Microsoft Edge 同步，用户可以访问他们所有已登录设备上的浏览数据。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-107">Microsoft Edge sync enables users to access their browsing data across all their signed-in devices.</span></span> <span data-ttu-id="bdd7e-108">同步支持的数据包括：</span><span class="sxs-lookup"><span data-stu-id="bdd7e-108">The data supported by sync includes:</span></span>

- <span data-ttu-id="bdd7e-109">收藏夹</span><span class="sxs-lookup"><span data-stu-id="bdd7e-109">Favorites</span></span>
- <span data-ttu-id="bdd7e-110">密码</span><span class="sxs-lookup"><span data-stu-id="bdd7e-110">Passwords</span></span>
- <span data-ttu-id="bdd7e-111">地址等（表单填写）</span><span class="sxs-lookup"><span data-stu-id="bdd7e-111">Addresses and more (form-fill)</span></span>
- <span data-ttu-id="bdd7e-112">收藏</span><span class="sxs-lookup"><span data-stu-id="bdd7e-112">Collections</span></span>
- <span data-ttu-id="bdd7e-113">“设置”</span><span class="sxs-lookup"><span data-stu-id="bdd7e-113">Settings</span></span>

<span data-ttu-id="bdd7e-114">用户同意后即可启用同步功能，并且用户可以针对上面列出的每种数据类型打开或关闭同步功能。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-114">Sync functionality is enabled via user consent and users can turn sync on or off for each of the data types listed above.</span></span>

> [!NOTE]
> <span data-ttu-id="bdd7e-115">将上载其他设备连接和配置数据（如设备名称、品牌和型号），以支持同步功能。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-115">Additional device connectivity and configuration data (such as device name, make and model) is uploaded to support sync functionality.</span></span>

## <span data-ttu-id="bdd7e-116">必备条件</span><span class="sxs-lookup"><span data-stu-id="bdd7e-116">Prerequisites</span></span>

<span data-ttu-id="bdd7e-117">当前，适用于 Azure Active Directory (Azure AD) 帐户的 Microsoft Edge 同步功能供以下订阅使用：</span><span class="sxs-lookup"><span data-stu-id="bdd7e-117">Currently Microsoft Edge sync for Azure Active Directory (Azure AD) accounts is available for the following subscriptions:</span></span>

- <span data-ttu-id="bdd7e-118">Azure AD Premium (P1 和 P2)</span><span class="sxs-lookup"><span data-stu-id="bdd7e-118">Azure AD Premium (P1 and P2)</span></span>
- <span data-ttu-id="bdd7e-119">M365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="bdd7e-119">M365 Business Premium</span></span>
- <span data-ttu-id="bdd7e-120">Office 365 E3 及更高版本</span><span class="sxs-lookup"><span data-stu-id="bdd7e-120">Office 365 E3 and above</span></span>
- <span data-ttu-id="bdd7e-121">Azure 信息保护 (AIP) (P1& P2)</span><span class="sxs-lookup"><span data-stu-id="bdd7e-121">Azure Information Protection (AIP) (P1& P2)</span></span>
- <span data-ttu-id="bdd7e-122">所有 EDU 订阅（O365 A1 或更高版本、M365 A1 或更高版本，或者适用于学生或教职员的 Azure 信息保护 P1 或 P2）</span><span class="sxs-lookup"><span data-stu-id="bdd7e-122">All EDU subscriptions (O365 A1 or above, M365 A1 or above, or Azure Information Protection P1 or P2 for Students or Faculty)</span></span>

> [!NOTE]
> <span data-ttu-id="bdd7e-123">同步功能依赖 Azure 信息保护 (AIP) 提供的保护服务来保护同步数据。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-123">Sync has a dependency on the protection service offered by Azure Information Protection (AIP) to protect sync data.</span></span> <span data-ttu-id="bdd7e-124">此服务当前可供前述订阅使用。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-124">This service is currently available to the preceding subscriptions.</span></span> <span data-ttu-id="bdd7e-125">要查看具有 AIP 的 SKU 的完整列表，请参阅[信息保护定价](https://azure.microsoft.com/pricing/details/information-protection/)。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-125">To see the full list of SKUs with AIP, see [Information Protection Pricing](https://azure.microsoft.com/pricing/details/information-protection/).</span></span>

## <span data-ttu-id="bdd7e-126">Microsoft Edge 同步的配置选项</span><span class="sxs-lookup"><span data-stu-id="bdd7e-126">Configuration options for Microsoft Edge sync</span></span>

<span data-ttu-id="bdd7e-127">下列配置选项可用于启用 Microsoft Edge 同步：</span><span class="sxs-lookup"><span data-stu-id="bdd7e-127">The following configuration options are available for enabling Microsoft Edge sync:</span></span>

- <span data-ttu-id="bdd7e-128">Azure 信息保护 (AIP)</span><span class="sxs-lookup"><span data-stu-id="bdd7e-128">Azure Information Protection (AIP)</span></span>
- <span data-ttu-id="bdd7e-129">Azure AD 企业状态漫游 (ESR)</span><span class="sxs-lookup"><span data-stu-id="bdd7e-129">Azure AD Enterprise State Roaming (ESR)</span></span>

<span data-ttu-id="bdd7e-130">如果 AIP 和 ESR 均已禁用，则用户将看到一条错误消息，指示同步功能不适用于其帐户。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-130">If both AIP and ESR are disabled, users will see an error message indicating that sync is not available for their account.</span></span>

### <span data-ttu-id="bdd7e-131">Azure 信息保护 (AIP)</span><span class="sxs-lookup"><span data-stu-id="bdd7e-131">Azure Information Protection (AIP)</span></span>

<span data-ttu-id="bdd7e-132">如果为租户启用了 Azure 信息保护 (AIP) 服务，不管是否获得许可，所有用户均可同步 Microsoft Edge 数据。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-132">If the Azure Information Protection (AIP) service is enabled for a tenant, all users can sync Microsoft Edge data, regardless of licensing.</span></span> <span data-ttu-id="bdd7e-133">有关如何启用 AIP 的说明，请参阅[此处](https://docs.microsoft.com/azure/information-protection/activate-office365)。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-133">Instructions on how to enable AIP can be found [here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span>

<span data-ttu-id="bdd7e-134">要限制某一组用户使用同步功能，可为这些用户启用 [AADRM 登录控制策略](https://docs.microsoft.com/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps)。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-134">To restrict sync to certain set of users, you can enable the [AADRM onboarding control policy](https://docs.microsoft.com/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) for those users.</span></span> <span data-ttu-id="bdd7e-135">如果确保所有必需的用户均加入后同步仍不可用，请确保使用 [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/Get-AipServiceIPCv3?view=azureipps) PowerShell cmdlet 启用了 IPCv3Service。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-135">If sync is still not available after ensuring that all necessary users are onboarded, ensure that the IPCv3Service is enabled using the [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/Get-AipServiceIPCv3?view=azureipps) PowerShell cmdlet.</span></span>

> [!CAUTION]
> <span data-ttu-id="bdd7e-136">启用 Azure 信息保护还将限制使用 AIP 对其他应用程序（如 Microsoft Word 或 Microsoft Outlook）的访问。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-136">Activating Azure Information Protection will also restrict access for other applications using AIP, such as Microsoft Word or Microsoft Outlook.</span></span>

### <span data-ttu-id="bdd7e-137">Azure AD 企业状态漫游 (ESR)</span><span class="sxs-lookup"><span data-stu-id="bdd7e-137">Azure AD Enterprise State Roaming (ESR)</span></span>

<span data-ttu-id="bdd7e-138">如果为任何用户或租户启用 Azure Active Directory [企业状态漫游](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) (ESR) 功能，则无论加入控制策略设置如何，他们都可以使用 Microsoft Edge 同步功能。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-138">If the Azure Active Directory [Enterprise State Roaming](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) (ESR) feature is enabled for any user or tenant, they can use the Microsoft Edge sync feature regardless of the onboarding control policy setting.</span></span>

## <span data-ttu-id="bdd7e-139">Microsoft Edge 和企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="bdd7e-139">Microsoft Edge and Enterprise State Roaming</span></span>

<span data-ttu-id="bdd7e-140">新版 Microsoft Edge 是跨平台应用程序，具有用于跨用户的所有设备同步用户数据的扩展作用域，并且不再是 Azure AD 企业状态漫游的一部分。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-140">The new Microsoft Edge is a cross-platform application with an expanded scope for syncing user data across all their devices and is no longer a part of Azure AD Enterprise State Roaming.</span></span> <span data-ttu-id="bdd7e-141">但是，新版 Microsoft Edge 将履行 ESR 的数据保护承诺，例如引入你自己的密钥的功能。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-141">However, the new Microsoft Edge will fulfill the data protection promises of ESR, such as the ability to bring your own key.</span></span> <span data-ttu-id="bdd7e-142">有关详细信息，请参阅 [Microsoft Edge 和企业状态漫游](microsoft-edge-enterprise-state-roaming.md)。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-142">For more information, see [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

## <span data-ttu-id="bdd7e-143">同步组策略</span><span class="sxs-lookup"><span data-stu-id="bdd7e-143">Sync group policies</span></span>

<span data-ttu-id="bdd7e-144">以下组策略会影响 Microsoft Edge 同步：</span><span class="sxs-lookup"><span data-stu-id="bdd7e-144">The following group policies impact Microsoft Edge sync:</span></span>

- <span data-ttu-id="bdd7e-145">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled)：完全禁用同步。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-145">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): Disables sync completely.</span></span>
- <span data-ttu-id="bdd7e-146">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled)：禁止保存浏览历史记录和同步。此策略还将禁用打开标签页同步。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-146">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): Disables saving browsing history and sync. This policy also disables open-tabs sync.</span></span>
- <span data-ttu-id="bdd7e-147">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled)：配置从同步中排除的类型列表。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-147">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): Configure the list of types that are excluded from synchronization.</span></span>

## <span data-ttu-id="bdd7e-148">常见问题</span><span class="sxs-lookup"><span data-stu-id="bdd7e-148">Frequently Asked Questions</span></span>

### <span data-ttu-id="bdd7e-149">安全性和服务器/数据合规性</span><span class="sxs-lookup"><span data-stu-id="bdd7e-149">SECURITY and SERVER/DATA COMPLIANCE</span></span>

#### <span data-ttu-id="bdd7e-150">已同步的数据是否已加密？</span><span class="sxs-lookup"><span data-stu-id="bdd7e-150">Is the synced data encrypted?</span></span> 

<span data-ttu-id="bdd7e-151">数据已在传输过程中使用 TLS 1.2 或更高版本加密，此外，还使用 AES256 在 Microsoft 的服务中进行了静态加密。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-151">The data is encrypted in transport using TLS 1.2 or greater, and additionally at rest in Microsoft's service using AES256.</span></span>

#### <span data-ttu-id="bdd7e-152">Microsoft Edge 的同步数据存储在哪里？</span><span class="sxs-lookup"><span data-stu-id="bdd7e-152">Where is Microsoft Edge sync data stored?</span></span>

<span data-ttu-id="bdd7e-153">Azure AD 帐户的同步数据将根据租户 ID 存储在安全服务器中。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-153">Synced data for Azure AD accounts is stored in secure servers according to the tenant ID.</span></span> <span data-ttu-id="bdd7e-154">例如，在美国注册的租户的数据存储在位于该地区地理位置的服务器上，并使用与 Office 应用程序相同的存储解决方案。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-154">For example, the data for a tenant that is registered in the United States is stored in servers geo-located for that region and uses the same storage solution as Office applications.</span></span>

#### <span data-ttu-id="bdd7e-155">除了同步至 Microsoft Edge 外，数据是否会离开 Microsoft 云？</span><span class="sxs-lookup"><span data-stu-id="bdd7e-155">Does the data ever leave Microsoft's cloud, aside from syncing to Microsoft Edge?</span></span>

<span data-ttu-id="bdd7e-156">否。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-156">No.</span></span>

#### <span data-ttu-id="bdd7e-157">租户管理员能否使用自己的密钥？</span><span class="sxs-lookup"><span data-stu-id="bdd7e-157">Can tenant admins bring their own key?</span></span>

<span data-ttu-id="bdd7e-158">可以，通过 [Azure 信息保护](https://azure.microsoft.com/services/information-protection/)。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-158">Yes, through [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>

#### <span data-ttu-id="bdd7e-159">企业同步属于哪项服务条款？</span><span class="sxs-lookup"><span data-stu-id="bdd7e-159">What terms of service does enterprise sync fall under?</span></span>

<span data-ttu-id="bdd7e-160">服务条款与 Azure AD 订阅的条款相同。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-160">The terms of service are the same terms as your Azure AD subscription.</span></span> <span data-ttu-id="bdd7e-161">所有 Azure AD 服务条款最终均属于 Microsoft 的[联机服务条款](https://www.microsoft.com/licensing/product-licensing/products)。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-161">All the Azure AD terms of service ultimately fall under Microsoft's [Online Service Terms](https://www.microsoft.com/licensing/product-licensing/products).</span></span>

#### <span data-ttu-id="bdd7e-162">Microsoft Edge 是否支持政府社区云 (GCC) 高合规性？</span><span class="sxs-lookup"><span data-stu-id="bdd7e-162">Does Microsoft Edge support Government Community Cloud (GCC) High compliance?</span></span>

<span data-ttu-id="bdd7e-163">目前尚不支持。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-163">Not today.</span></span> <span data-ttu-id="bdd7e-164">GCC 高合规性是 D 层，而 Microsoft Edge 最多支持 C 层。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-164">GCC High is Tier D, while Microsoft Edge supports up to Tier C.</span></span>

### <span data-ttu-id="bdd7e-165">应用同步</span><span class="sxs-lookup"><span data-stu-id="bdd7e-165">APPLYING SYNC</span></span>

#### <span data-ttu-id="bdd7e-166">对于决定保留旧版 Microsoft Edge 的企业和教育客户，将会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="bdd7e-166">What happens with enterprise and educational customers who decide to stay with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="bdd7e-167">当前版本的 Microsoft Edge 浏览器将继续加入 ESR 产品/服务。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-167">The current version of Microsoft Edge browser will continue to participate in the ESR offering.</span></span>

#### <span data-ttu-id="bdd7e-168">为什么需要高级 Azure AD 订阅才能进行同步？</span><span class="sxs-lookup"><span data-stu-id="bdd7e-168">Why do I need a premium Azure AD subscription to sync?</span></span>

<span data-ttu-id="bdd7e-169">企业同步依赖于 Azure 信息保护，它在所有 Azure AD 层中均不可用。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-169">Enterprise sync depends on Azure Information Protection, which is not available in all Azure AD tiers.</span></span>

#### <span data-ttu-id="bdd7e-170">Microsoft Edge 同步是否基于企业状态漫游？</span><span class="sxs-lookup"><span data-stu-id="bdd7e-170">Is Microsoft Edge sync based on Enterprise State Roaming?</span></span>

<span data-ttu-id="bdd7e-171">否。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-171">No.</span></span> <span data-ttu-id="bdd7e-172">ESR 可用于启用同步，但 Microsoft Edge 同步不是 ESR 的一部分。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-172">ESR can be used to enable sync, but Microsoft Edge sync is not a part of ESR.</span></span> <span data-ttu-id="bdd7e-173">有关详细信息，请参阅 [Microsoft Edge 同步](microsoft-edge-enterprise-sync.md)和 [Microsoft Edge 和企业状态漫游](microsoft-edge-enterprise-state-roaming.md)。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-173">For more information, see [Microsoft Edge Sync](microsoft-edge-enterprise-sync.md) and [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

#### <span data-ttu-id="bdd7e-174">Microsoft Edge 是否支持 Microsoft Edge 和 IE 之间的同步？</span><span class="sxs-lookup"><span data-stu-id="bdd7e-174">Will Microsoft Edge ever support syncing between Microsoft Edge and IE?</span></span>

<span data-ttu-id="bdd7e-175">尚无支持此同步的计划。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-175">There are no plans to support this syncing.</span></span> <span data-ttu-id="bdd7e-176">如果你的环境中仍需要 IE 来支持旧版应用，请考虑使用我们的[新 IE 模式](https://docs.microsoft.com/deployedge/edge-ie-mode)。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-176">If you still need IE in your environment to support legacy apps, consider our [new IE mode](https://docs.microsoft.com/deployedge/edge-ie-mode).</span></span>

#### <span data-ttu-id="bdd7e-177">新的 Microsoft Edge 浏览器是否将与 Microsoft Edge 旧版同步？</span><span class="sxs-lookup"><span data-stu-id="bdd7e-177">Will the new Microsoft Edge browser sync with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="bdd7e-178">否，不会同步。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-178">No, it won't.</span></span> <span data-ttu-id="bdd7e-179">我们认为连接这两个生态系统将降低新版 Microsoft Edge 同步的可靠性。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-179">We believe connecting these two ecosystems will lead to compromises in the reliability of sync in the new Microsoft Edge.</span></span> <span data-ttu-id="bdd7e-180">我们会确保将现有数据迁移到新版 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-180">We will ensure that existing data is migrated to the new Microsoft Edge.</span></span> <span data-ttu-id="bdd7e-181">用户还可以从他们选择的浏览器导入数据。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-181">Users will also be able to import data from browser of their choice.</span></span> <span data-ttu-id="bdd7e-182">这也意味着新版 Microsoft Edge 浏览器将无法与 IE 同步。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-182">This also means that new Microsoft Edge browser won't have a way to sync with IE.</span></span>

### <span data-ttu-id="bdd7e-183">管理同步</span><span class="sxs-lookup"><span data-stu-id="bdd7e-183">MANAGING SYNC</span></span>

#### <span data-ttu-id="bdd7e-184">是否可以阻止我的用户与个人租户同步？</span><span class="sxs-lookup"><span data-stu-id="bdd7e-184">Is it possible to stop my users from syncing with a personal tenant?</span></span>

<span data-ttu-id="bdd7e-185">无法直接阻止，但你可以使用 [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) 策略确定哪些配置文件可以登录到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="bdd7e-185">Not directly, but you can determine which profiles can sign on to Microsoft Edge using the [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) policy.</span></span>

## <span data-ttu-id="bdd7e-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bdd7e-186">See also</span></span>

- [<span data-ttu-id="bdd7e-187">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="bdd7e-187">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="bdd7e-188">Microsoft Edge 和企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="bdd7e-188">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
