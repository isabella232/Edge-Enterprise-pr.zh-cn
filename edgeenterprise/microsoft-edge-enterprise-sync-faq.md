---
title: Microsoft Edge 企业同步常见问题解答
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 03/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 有关 Microsoft Edge 企业同步的常见问题解答。
ms.openlocfilehash: 4bb41c8d7ded64fcc0b4fd4843ef2b7ec0adec23
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617762"
---
# <a name="microsoft-edge-enterprise-sync-faq"></a><span data-ttu-id="5c8ae-103">Microsoft Edge 企业同步常见问题解答</span><span class="sxs-lookup"><span data-stu-id="5c8ae-103">Microsoft Edge enterprise sync FAQ</span></span>

<span data-ttu-id="5c8ae-104">本文解答了有关 Microsoft Edge 版本 77 或更高版本的企业同步的常见问题。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-104">This article answers frequently asked questions about enterprise sync for Microsoft Edge version 77 or later.</span></span>

## <a name="security-and-serverdata-compliance"></a><span data-ttu-id="5c8ae-105">安全性和服务器/数据合规性</span><span class="sxs-lookup"><span data-stu-id="5c8ae-105">Security and Server/Data Compliance</span></span>

### <a name="is-the-synced-data-encrypted"></a><span data-ttu-id="5c8ae-106">已同步的数据是否已加密？</span><span class="sxs-lookup"><span data-stu-id="5c8ae-106">Is the synced data encrypted?</span></span>

<span data-ttu-id="5c8ae-107">数据使用 TLS 1.2 或更高版本在传输中加密。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-107">The data is encrypted in transport using TLS 1.2 or greater.</span></span> <span data-ttu-id="5c8ae-108">在 Microsoft 的服务中，所有数据类型都会使用 AES128 进行额外的静态加密。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-108">All data types are additionally encrypted at rest in Microsoft's service using AES128.</span></span> <span data-ttu-id="5c8ae-109">除用于同步已打开标签页和历史记录的数据类型外，所有数据类型都会在离开用户设备之前使用 [Azure 信息保护](./microsoft-edge-policies.md#restrictsignintopattern)策略所管理的密钥进行额外加密。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-109">All data types except those used for open tab and history sync are additionally encrypted before leaving the user’s device with keys managed via the [Azure Information Protection](./microsoft-edge-policies.md#restrictsignintopattern) policy.</span></span>

### <a name="why-dont-open-tab-and-history-data-have-more-client-side-encryption"></a><span data-ttu-id="5c8ae-110">为什么已打开标签页和历史记录数据没有更多的客户端加密？</span><span class="sxs-lookup"><span data-stu-id="5c8ae-110">Why don’t open tab and history data have more client-side encryption?</span></span>

<span data-ttu-id="5c8ae-111">为了降低最终用户设备上的资源利用率，系统将基于已打开标签页的漫游数据在服务器端生成历史记录数据。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-111">To reduce resource utilization on end-user devices, history data is generated server-side based on open tab roaming data.</span></span> <span data-ttu-id="5c8ae-112">此过程无法支持此类数据的客户端加密。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-112">This process would not be possible with client-side encryption of this data.</span></span> <span data-ttu-id="5c8ae-113">若要禁用打开选项卡和历史记录同步，请应用 [SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled) 或 [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) 策略。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-113">To disable open tab and history sync, apply the [SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled) or [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) policies.</span></span>

### <a name="can-tenant-admins-bring-their-own-key"></a><span data-ttu-id="5c8ae-114">租户管理员能否使用自己的密钥？</span><span class="sxs-lookup"><span data-stu-id="5c8ae-114">Can tenant admins bring their own key?</span></span>

<span data-ttu-id="5c8ae-115">是，可通过  [Azure 信息保护](https://azure.microsoft.com/services/information-protection/)来实现。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-115">Yes, through [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>

### <a name="where-is-microsoft-edge-sync-data-stored"></a><span data-ttu-id="5c8ae-116">Microsoft Edge 的同步数据存储在哪里？</span><span class="sxs-lookup"><span data-stu-id="5c8ae-116">Where is Microsoft Edge sync data stored?</span></span>

<span data-ttu-id="5c8ae-117">Azure AD 帐户的同步数据将根据租户 ID 存储在安全服务器中。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-117">Synced data for Azure AD accounts is stored in secure servers according to the tenant ID.</span></span> <span data-ttu-id="5c8ae-118">例如，在美国注册的租户的数据存储在位于该地区地理位置的服务器上，并使用与 Office 应用程序相同的存储解决方案。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-118">For example, the data for a tenant that is registered in the United States is stored in servers geo-located for that region and uses the same storage solution as Office applications.</span></span>

### <a name="does-the-data-ever-leave-microsofts-cloud-aside-from-syncing-to-microsoft-edge"></a><span data-ttu-id="5c8ae-119">除了同步至 Microsoft Edge 外，数据是否会离开 Microsoft 云？</span><span class="sxs-lookup"><span data-stu-id="5c8ae-119">Does the data ever leave Microsoft's cloud, aside from syncing to Microsoft Edge?</span></span>

<span data-ttu-id="5c8ae-120">否。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-120">No.</span></span>

### <a name="what-terms-of-service-does-enterprise-sync-fall-under"></a><span data-ttu-id="5c8ae-121">企业同步属于哪项服务条款？</span><span class="sxs-lookup"><span data-stu-id="5c8ae-121">What terms of service does enterprise sync fall under?</span></span>

<span data-ttu-id="5c8ae-122">Microsoft Edge 同步服务条款已列入 Microsoft 软件许可证，可使用 Microsoft Edge 访问  *edge://terms* 进行查看。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-122">Terms of service for Microsoft Edge sync falls under the Microsoft software license viewable in Microsoft Edge at *edge://terms*.</span></span> <span data-ttu-id="5c8ae-123">你的 Azure AD 订阅和服务条款最终属于 Microsoft 的[联机服务条款](https://www.microsoft.com/licensing/product-licensing/products)。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-123">Your Azure AD subscription and terms of service ultimately fall under Microsoft's [Online Service Terms](https://www.microsoft.com/licensing/product-licensing/products).</span></span>

### <a name="does-microsoft-edge-support-government-community-cloud-gcc-high-compliance"></a><span data-ttu-id="5c8ae-124">Microsoft Edge 是否支持政府社区云 (GCC) 高合规性？</span><span class="sxs-lookup"><span data-stu-id="5c8ae-124">Does Microsoft Edge support Government Community Cloud (GCC) High compliance?</span></span>

<span data-ttu-id="5c8ae-125">目前尚不支持。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-125">Not today.</span></span> <span data-ttu-id="5c8ae-126">对于使用 GCC 高云服务的客户，已禁用 Microsoft Edge 同步。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-126">For customers in the GCC High cloud, Microsoft Edge sync is disabled.</span></span>

## <a name="applying-sync"></a><span data-ttu-id="5c8ae-127">应用同步</span><span class="sxs-lookup"><span data-stu-id="5c8ae-127">Applying Sync</span></span>

### <a name="why-isnt-microsoft-edge-sync-supported-in-all-m365-subscriptions"></a><span data-ttu-id="5c8ae-128">为什么并非所有 M365 订阅都支持 Microsoft Edge 同步？</span><span class="sxs-lookup"><span data-stu-id="5c8ae-128">Why isn’t Microsoft Edge sync supported in all M365 subscriptions?</span></span>

<span data-ttu-id="5c8ae-129">企业同步取决于 [Azure 信息保护](https://azure.microsoft.com/services/information-protection/)，它并非在所有 M365 订阅中都可用。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-129">Enterprise sync depends on [Azure Information Protection](https://azure.microsoft.com/services/information-protection/), which is not available in all M365 subscriptions.</span></span>

### <a name="is-microsoft-edge-sync-based-on-enterprise-state-roaming"></a><span data-ttu-id="5c8ae-130">Microsoft Edge 同步是否基于企业状态漫游？</span><span class="sxs-lookup"><span data-stu-id="5c8ae-130">Is Microsoft Edge sync based on Enterprise State Roaming?</span></span>

<span data-ttu-id="5c8ae-131">否。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-131">No.</span></span> <span data-ttu-id="5c8ae-132">ESR 可用于启用同步，但 Microsoft Edge 同步不是 ESR 的一部分。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-132">ESR can be used to enable sync, but Microsoft Edge sync is not a part of ESR.</span></span> <span data-ttu-id="5c8ae-133">有关详细信息，请参阅 [Microsoft Edge 同步](/DeployEdge/microsoft-edge-enterprise-sync)和 [Microsoft Edge 和企业状态漫游](/DeployEdge/microsoft-edge-enterprise-state-roaming)。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-133">For more information, see [Microsoft Edge Sync](/DeployEdge/microsoft-edge-enterprise-sync) and [Microsoft Edge and Enterprise State Roaming](/DeployEdge/microsoft-edge-enterprise-state-roaming).</span></span>

### <a name="will-microsoft-edge-ever-support-syncing-between-microsoft-edge-and-ie"></a><span data-ttu-id="5c8ae-134">Microsoft Edge 是否支持 Microsoft Edge 和 IE 之间的同步？</span><span class="sxs-lookup"><span data-stu-id="5c8ae-134">Will Microsoft Edge ever support syncing between Microsoft Edge and IE?</span></span>

<span data-ttu-id="5c8ae-135">尚无支持此同步的计划。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-135">There are no plans to support this syncing.</span></span> <span data-ttu-id="5c8ae-136">如果你的环境仍需要 IE 来支持旧版应用，请考虑使用我们的[新 IE 模式](./edge-ie-mode.md)。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-136">If you still need IE in your environment to support legacy apps, consider our [new IE mode](./edge-ie-mode.md).</span></span>

### <a name="will-microsoft-edge-sync-with-microsoft-edge-legacy"></a><span data-ttu-id="5c8ae-137">Microsoft Edge 是否将与 Microsoft Edge 旧版同步？</span><span class="sxs-lookup"><span data-stu-id="5c8ae-137">Will Microsoft Edge sync with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="5c8ae-138">否，不会同步。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-138">No, it won't.</span></span> <span data-ttu-id="5c8ae-139">我们认为连接这两个生态系统将降低 Microsoft Edge 同步的可靠性。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-139">We believe connecting these two ecosystems will lead to compromises in the reliability of sync in the Microsoft Edge.</span></span> <span data-ttu-id="5c8ae-140">我们会确保将现有数据迁移到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-140">We will ensure that existing data is migrated to the Microsoft Edge.</span></span> <span data-ttu-id="5c8ae-141">用户还可以从自己选择的浏览器导入数据，这也意味着 Microsoft Edge 无法与 IE 同步。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-141">Users will also be able to import data from browser of their choice, which also means that Microsoft Edge won't have a way to sync with IE.</span></span>

## <a name="managing-sync"></a><span data-ttu-id="5c8ae-142">管理同步</span><span class="sxs-lookup"><span data-stu-id="5c8ae-142">Managing Sync</span></span>

### <a name="is-it-possible-to-stop-my-users-from-syncing-with-a-personal-tenant"></a><span data-ttu-id="5c8ae-143">是否可以阻止我的用户与个人租户同步？</span><span class="sxs-lookup"><span data-stu-id="5c8ae-143">Is it possible to stop my users from syncing with a personal tenant?</span></span>

<span data-ttu-id="5c8ae-144">无法直接阻止，但你可以使用 [RestrictSigninToPattern](./microsoft-edge-policies.md#restrictsignintopattern) 策略确定哪些配置文件可以登录到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="5c8ae-144">Not directly, but you can determine which profiles can sign on to Microsoft Edge using the [RestrictSigninToPattern](./microsoft-edge-policies.md#restrictsignintopattern) policy.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c8ae-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c8ae-145">See also</span></span>

- [<span data-ttu-id="5c8ae-146">Microsoft Edge 企业同步</span><span class="sxs-lookup"><span data-stu-id="5c8ae-146">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)
- [<span data-ttu-id="5c8ae-147">Microsoft Edge 和企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="5c8ae-147">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="5c8ae-148">Microsoft Edge 企业版登录页面</span><span class="sxs-lookup"><span data-stu-id="5c8ae-148">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)