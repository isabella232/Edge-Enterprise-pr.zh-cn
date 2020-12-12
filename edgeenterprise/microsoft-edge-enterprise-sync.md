---
title: Microsoft Edge Enterprise Sync
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 12/09/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Enterprise Sync
ms.openlocfilehash: 791188b5d28c867d6409a4d5373ea6c1ec7e49c7
ms.sourcegitcommit: 482b2e440a62cbf974dc45ac817f9d9d187ba1b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "11205461"
---
# <span data-ttu-id="3c97c-103">Microsoft Edge Enterprise Sync</span><span class="sxs-lookup"><span data-stu-id="3c97c-103">Microsoft Edge Enterprise Sync</span></span>

<span data-ttu-id="3c97c-104">本文介绍如何使用 Microsoft Edge 同步你所有已登录设备上的收藏夹、密码和其他浏览器数据。</span><span class="sxs-lookup"><span data-stu-id="3c97c-104">This article explains how to use Microsoft Edge to sync your favorites, passwords, and other browser data across all your signed-in devices.</span></span>

> [!NOTE]
> <span data-ttu-id="3c97c-105">除非另有说明，否则本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="3c97c-105">This article applies to Microsoft Edge version 77 or later unless otherwise noted.</span></span>

## <span data-ttu-id="3c97c-106">概述</span><span class="sxs-lookup"><span data-stu-id="3c97c-106">Overview</span></span>

<span data-ttu-id="3c97c-107">通过 Microsoft Edge 同步，用户可以访问他们所有已登录设备上的浏览数据。</span><span class="sxs-lookup"><span data-stu-id="3c97c-107">Microsoft Edge sync enables users to access their browsing data across all their signed-in devices.</span></span> <span data-ttu-id="3c97c-108">同步支持的数据包括：</span><span class="sxs-lookup"><span data-stu-id="3c97c-108">The data supported by sync includes:</span></span>

- <span data-ttu-id="3c97c-109">收藏夹</span><span class="sxs-lookup"><span data-stu-id="3c97c-109">Favorites</span></span>
- <span data-ttu-id="3c97c-110">密码</span><span class="sxs-lookup"><span data-stu-id="3c97c-110">Passwords</span></span>
- <span data-ttu-id="3c97c-111">地址等（表单填写）</span><span class="sxs-lookup"><span data-stu-id="3c97c-111">Addresses and more (form-fill)</span></span>
- <span data-ttu-id="3c97c-112">收藏</span><span class="sxs-lookup"><span data-stu-id="3c97c-112">Collections</span></span>
- <span data-ttu-id="3c97c-113">“设置”</span><span class="sxs-lookup"><span data-stu-id="3c97c-113">Settings</span></span>
- <span data-ttu-id="3c97c-114">扩展</span><span class="sxs-lookup"><span data-stu-id="3c97c-114">Extension</span></span>
- <span data-ttu-id="3c97c-115">打开选项卡（在 Microsoft Edge 版本 88 中可用）</span><span class="sxs-lookup"><span data-stu-id="3c97c-115">Open tabs (available in Microsoft Edge version 88)</span></span>
- <span data-ttu-id="3c97c-116">历史记录（在 Microsoft Edge 版本 88 中可用）</span><span class="sxs-lookup"><span data-stu-id="3c97c-116">History (available in Microsoft Edge version 88)</span></span>

<span data-ttu-id="3c97c-117">用户同意后即可启用同步功能，并且用户可以针对上面列出的每种数据类型打开或关闭同步功能。</span><span class="sxs-lookup"><span data-stu-id="3c97c-117">Sync functionality is enabled via user consent and users can turn sync on or off for each of the data types listed above.</span></span>

> [!NOTE]
> <span data-ttu-id="3c97c-118">将上载其他设备连接和配置数据（如设备名称、品牌和型号），以支持同步功能。</span><span class="sxs-lookup"><span data-stu-id="3c97c-118">Additional device connectivity and configuration data (such as device name, make and model) is uploaded to support sync functionality.</span></span>

## <span data-ttu-id="3c97c-119">必备条件</span><span class="sxs-lookup"><span data-stu-id="3c97c-119">Prerequisites</span></span>

<span data-ttu-id="3c97c-120">适用于 Azure Active Directory (Azure AD) 帐户的 Microsoft Edge 同步功能可供以下任何订阅使用：</span><span class="sxs-lookup"><span data-stu-id="3c97c-120">Microsoft Edge sync for Azure Active Directory (Azure AD) accounts is available for any of the following subscriptions:</span></span>

- <span data-ttu-id="3c97c-121">Azure AD Premium（P1 或 P2）</span><span class="sxs-lookup"><span data-stu-id="3c97c-121">Azure AD Premium (P1 or P2)</span></span>
- <span data-ttu-id="3c97c-122">M365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="3c97c-122">M365 Business Premium</span></span>
- <span data-ttu-id="3c97c-123">Office 365 E1 及更高版本</span><span class="sxs-lookup"><span data-stu-id="3c97c-123">Office 365 E1 and above</span></span>
- <span data-ttu-id="3c97c-124">Azure 信息保护 (AIP)（P1 或 P2）</span><span class="sxs-lookup"><span data-stu-id="3c97c-124">Azure Information Protection (AIP) (P1 or P2)</span></span>
- <span data-ttu-id="3c97c-125">所有 EDU 订阅（Microsoft 教育应用版（学生）或 Microsoft 教育应用版（教职员工）、Exchange Online 学生版或教职员工版、O365 A1 或更高版本、M365 A1 或更高版本，或者适用于学生或教职员的 Azure 信息保护 P1 或 P2）</span><span class="sxs-lookup"><span data-stu-id="3c97c-125">All EDU subscriptions (Microsoft Apps for Students or Faculty, Exchange Online for Students or Faculty, O365 A1 or above, M365 A1 or above, or Azure Information Protection P1 or P2 for Students or Faculty)</span></span>

## <span data-ttu-id="3c97c-126">配置 Microsoft Edge 同步功能</span><span class="sxs-lookup"><span data-stu-id="3c97c-126">Configuring Microsoft Edge sync</span></span>

<span data-ttu-id="3c97c-127">可通过 Azure 信息保护 (AIP) 服务获取 Microsoft Edge 同步的配置选项。</span><span class="sxs-lookup"><span data-stu-id="3c97c-127">Configuration options for Microsoft Edge sync are available through the Azure Information Protection (AIP) service.</span></span> <span data-ttu-id="3c97c-128">为租户启用 AIP 后，无论获得何种许可，所有用户均可同步 Microsoft Edge 数据。</span><span class="sxs-lookup"><span data-stu-id="3c97c-128">When AIP is enabled for a tenant, all users can sync Microsoft Edge data, regardless of licensing.</span></span> <span data-ttu-id="3c97c-129">有关如何启用 AIP 的说明，请参阅[此处](https://docs.microsoft.com/azure/information-protection/activate-office365)。</span><span class="sxs-lookup"><span data-stu-id="3c97c-129">Instructions on how to enable AIP can be found [here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span>

<span data-ttu-id="3c97c-130">若要限制某一组用户使用同步功能，可为这些用户启用 [AIP 登录控制策略](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true) 。</span><span class="sxs-lookup"><span data-stu-id="3c97c-130">To restrict sync to certain set of users, you can enable the [AIP onboarding control policy](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true) for those users.</span></span> <span data-ttu-id="3c97c-131">如果确保所有必需的用户均加入后同步仍不可用，请确保已使用 [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true) PowerShell cmdlet 启用 IPCv3Service。</span><span class="sxs-lookup"><span data-stu-id="3c97c-131">If sync is still not available after ensuring that all necessary users are onboarded, ensure that the IPCv3Service is enabled using the [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true)  PowerShell cmdlet.</span></span>

> [!CAUTION]
> <span data-ttu-id="3c97c-132">激活 Azure 信息保护还将允许其他应用程序（如 Microsoft Word 或 Microsoft Outlook）使用 AIP 保护内容。</span><span class="sxs-lookup"><span data-stu-id="3c97c-132">Activating Azure Information Protection will also allow other applications, such as Microsoft Word or Microsoft Outlook, to protect content with AIP.</span></span> <span data-ttu-id="3c97c-133">此外，用于限制 Microsoft Edge 同步的任何载入控制策略也将限制其他应用程序使用 AIP 保护内容。</span><span class="sxs-lookup"><span data-stu-id="3c97c-133">In addition, any onboarding control policy used to restrict Edge sync will also restrict other applications from protecting content using AIP.</span></span>

## <span data-ttu-id="3c97c-134">Microsoft Edge 和企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="3c97c-134">Microsoft Edge and Enterprise State Roaming</span></span>

<span data-ttu-id="3c97c-135">新版 Microsoft Edge 是跨平台应用程序，具有用于跨用户的所有设备同步用户数据的扩展作用域，并且不再是 Azure AD 企业状态漫游的一部分。</span><span class="sxs-lookup"><span data-stu-id="3c97c-135">The new Microsoft Edge is a cross-platform application with an expanded scope for syncing user data across all their devices and is no longer a part of Azure AD Enterprise State Roaming.</span></span> <span data-ttu-id="3c97c-136">但是，新版 Microsoft Edge 将履行 ESR 的数据保护承诺，例如引入你自己的密钥的功能。</span><span class="sxs-lookup"><span data-stu-id="3c97c-136">However, the new Microsoft Edge will fulfill the data protection promises of ESR, such as the ability to bring your own key.</span></span> <span data-ttu-id="3c97c-137">有关详细信息，请参阅 [Microsoft Edge 和企业状态漫游](microsoft-edge-enterprise-state-roaming.md)。</span><span class="sxs-lookup"><span data-stu-id="3c97c-137">For more information, see [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

## <span data-ttu-id="3c97c-138">同步组策略</span><span class="sxs-lookup"><span data-stu-id="3c97c-138">Sync group policies</span></span>

<span data-ttu-id="3c97c-139">以下组策略会影响 Microsoft Edge 同步：</span><span class="sxs-lookup"><span data-stu-id="3c97c-139">The following group policies impact Microsoft Edge sync:</span></span>

- <span data-ttu-id="3c97c-140">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled)：完全禁用同步。</span><span class="sxs-lookup"><span data-stu-id="3c97c-140">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): Disables sync completely.</span></span>
- <span data-ttu-id="3c97c-141">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled)：禁止保存浏览历史记录和同步。此策略还将禁用打开选项卡同步。</span><span class="sxs-lookup"><span data-stu-id="3c97c-141">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): Disables saving browsing history and sync. This policy also disables open-tabs sync.</span></span>
- <span data-ttu-id="3c97c-142">[AllowDeletingBrowserHistory](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory)：当此策略设置为禁用时，还将禁用历史记录同步。</span><span class="sxs-lookup"><span data-stu-id="3c97c-142">[AllowDeletingBrowserHistory](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory): When this policy is set to disabled, history sync will also be disabled.</span></span>
- <span data-ttu-id="3c97c-143">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled)：配置从同步中排除的类型列表。</span><span class="sxs-lookup"><span data-stu-id="3c97c-143">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): Configure the list of types that are excluded from synchronization.</span></span>
- <span data-ttu-id="3c97c-144">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled)：允许 Active Directory (AD) 配置文件使用本地存储。</span><span class="sxs-lookup"><span data-stu-id="3c97c-144">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): Allow Active Directory (AD) profiles to use on-premises storage.</span></span> <span data-ttu-id="3c97c-145">有关更多信息，请参阅 [Active Directory (AD) 用户的本地同步](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync)。</span><span class="sxs-lookup"><span data-stu-id="3c97c-145">For more information, see [On-premises sync for Active Directory (AD) users](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync).</span></span>
- <span data-ttu-id="3c97c-146">[ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync)：默认启用同步，且无需用户同意即可同步。</span><span class="sxs-lookup"><span data-stu-id="3c97c-146">[ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): Turn sync on by default and do not require user consent to sync.</span></span>  

## <span data-ttu-id="3c97c-147">常见问题</span><span class="sxs-lookup"><span data-stu-id="3c97c-147">Frequently Asked Questions</span></span>

### <span data-ttu-id="3c97c-148">安全性和服务器/数据合规性</span><span class="sxs-lookup"><span data-stu-id="3c97c-148">SECURITY and SERVER/DATA COMPLIANCE</span></span>

#### <span data-ttu-id="3c97c-149">已同步的数据是否已加密？</span><span class="sxs-lookup"><span data-stu-id="3c97c-149">Is the synced data encrypted?</span></span>

<span data-ttu-id="3c97c-150">数据使用 TLS 1.2 或更高版本在传输中加密。</span><span class="sxs-lookup"><span data-stu-id="3c97c-150">The data is encrypted in transport using TLS 1.2 or greater.</span></span> <span data-ttu-id="3c97c-151">所有数据类型在休眠时，都会在 Microsoft 服务中使用 AES128 进行额外的加密。</span><span class="sxs-lookup"><span data-stu-id="3c97c-151">All data types are additionally encrypted at rest in Microsoft's service using AES128.</span></span> <span data-ttu-id="3c97c-152">除用于打开选项卡和历史记录同步的数据类型外，所有其他数据类型在离开用户设备之前都会使用由 [Azure 信息保护](https://docs.microsoft.com/azure/information-protection/)管理的密钥进行额外加密。</span><span class="sxs-lookup"><span data-stu-id="3c97c-152">All data types except those used for open tab and history sync are additionally encrypted before leaving the user’s device with keys managed via [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/).</span></span>

#### <span data-ttu-id="3c97c-153">为什么打开选项卡和历史记录数据没有额外的客户端加密？</span><span class="sxs-lookup"><span data-stu-id="3c97c-153">Why don’t open tab and history data have additional client-side encryption?</span></span>  

<span data-ttu-id="3c97c-154">为了降低最终用户设备上的资源利用率，将基于打开选项卡漫游数据在服务器端生成历史记录数据。</span><span class="sxs-lookup"><span data-stu-id="3c97c-154">In order to reduce resource utilization on end user devices, history data is generated server-side based on open tab roaming data.</span></span> <span data-ttu-id="3c97c-155">使用此数据的客户端加密将无法执行此过程。</span><span class="sxs-lookup"><span data-stu-id="3c97c-155">This process would not be possible with client-side encryption of this data.</span></span> <span data-ttu-id="3c97c-156">若要禁用打开选项卡和历史记录同步，请应用 [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled) 或 [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) 策略。</span><span class="sxs-lookup"><span data-stu-id="3c97c-156">To disable open tab and history sync, apply the [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled) or [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) policies.</span></span>

#### <span data-ttu-id="3c97c-157">租户管理员能否使用自己的密钥？</span><span class="sxs-lookup"><span data-stu-id="3c97c-157">Can tenant admins bring their own key?</span></span>

<span data-ttu-id="3c97c-158">是，可通过  [Azure 信息保护](https://azure.microsoft.com/services/information-protection/)来实现。</span><span class="sxs-lookup"><span data-stu-id="3c97c-158">Yes, through [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>

#### <span data-ttu-id="3c97c-159">Microsoft Edge 的同步数据存储在哪里？</span><span class="sxs-lookup"><span data-stu-id="3c97c-159">Where is Microsoft Edge sync data stored?</span></span>

<span data-ttu-id="3c97c-160">Azure AD 帐户的同步数据将根据租户 ID 存储在安全服务器中。</span><span class="sxs-lookup"><span data-stu-id="3c97c-160">Synced data for Azure AD accounts is stored in secure servers according to the tenant ID.</span></span> <span data-ttu-id="3c97c-161">例如，在美国注册的租户的数据存储在位于该地区地理位置的服务器上，并使用与 Office 应用程序相同的存储解决方案。</span><span class="sxs-lookup"><span data-stu-id="3c97c-161">For example, the data for a tenant that is registered in the United States is stored in servers geo-located for that region and uses the same storage solution as Office applications.</span></span>

#### <span data-ttu-id="3c97c-162">除了同步至 Microsoft Edge 外，数据是否会离开 Microsoft 云？</span><span class="sxs-lookup"><span data-stu-id="3c97c-162">Does the data ever leave Microsoft's cloud, aside from syncing to Microsoft Edge?</span></span>

<span data-ttu-id="3c97c-163">否。</span><span class="sxs-lookup"><span data-stu-id="3c97c-163">No.</span></span>

#### <span data-ttu-id="3c97c-164">企业同步属于哪项服务条款？</span><span class="sxs-lookup"><span data-stu-id="3c97c-164">What terms of service does enterprise sync fall under?</span></span>

<span data-ttu-id="3c97c-165">Microsoft Edge 同步服务条款已列入 Microsoft 软件许可证，可使用 Microsoft Edge 访问  *edge://terms* 进行查看。</span><span class="sxs-lookup"><span data-stu-id="3c97c-165">Terms of service for Microsoft Edge sync falls under the Microsoft software license viewable in Microsoft Edge at *edge://terms*.</span></span> <span data-ttu-id="3c97c-166">你的 Azure AD 订阅和服务条款最终属于 Microsoft 的[联机服务条款](https://www.microsoft.com/licensing/product-licensing/products)。</span><span class="sxs-lookup"><span data-stu-id="3c97c-166">Your Azure AD subscription and terms of service ultimately fall under Microsoft's [Online Service Terms](https://www.microsoft.com/licensing/product-licensing/products).</span></span>

#### <span data-ttu-id="3c97c-167">Microsoft Edge 是否支持政府社区云 (GCC) 高合规性？</span><span class="sxs-lookup"><span data-stu-id="3c97c-167">Does Microsoft Edge support Government Community Cloud (GCC) High compliance?</span></span>

<span data-ttu-id="3c97c-168">目前尚不支持。</span><span class="sxs-lookup"><span data-stu-id="3c97c-168">Not today.</span></span> <span data-ttu-id="3c97c-169">对于 GCC 高云中的客户，已禁用 Microsoft Edge 同步。</span><span class="sxs-lookup"><span data-stu-id="3c97c-169">For customers in the GCC High cloud, Microsoft Edge sync is disabled.</span></span>

### <span data-ttu-id="3c97c-170">应用同步</span><span class="sxs-lookup"><span data-stu-id="3c97c-170">APPLYING SYNC</span></span>

#### <span data-ttu-id="3c97c-171">为什么所有 M365 订阅都不支持 Microsoft Edge 同步？</span><span class="sxs-lookup"><span data-stu-id="3c97c-171">Why isn’t Microsoft Edge sync supported in all M365 subscriptions?</span></span>

<span data-ttu-id="3c97c-172">企业同步取决于 Azure 信息保护，它并非在所有 M365 订阅中都可用。</span><span class="sxs-lookup"><span data-stu-id="3c97c-172">Enterprise sync depends on Azure Information Protection, which is not available in all M365 subscriptions.</span></span>

#### <span data-ttu-id="3c97c-173">Microsoft Edge 同步是否基于企业状态漫游？</span><span class="sxs-lookup"><span data-stu-id="3c97c-173">Is Microsoft Edge sync based on Enterprise State Roaming?</span></span>

<span data-ttu-id="3c97c-174">否。</span><span class="sxs-lookup"><span data-stu-id="3c97c-174">No.</span></span> <span data-ttu-id="3c97c-175">ESR 可用于启用同步，但 Microsoft Edge 同步不是 ESR 的一部分。</span><span class="sxs-lookup"><span data-stu-id="3c97c-175">ESR can be used to enable sync, but Microsoft Edge sync is not a part of ESR.</span></span> <span data-ttu-id="3c97c-176">有关详细信息，请参阅 [Microsoft Edge 同步](microsoft-edge-enterprise-sync.md)和 [Microsoft Edge 和企业状态漫游](microsoft-edge-enterprise-state-roaming.md)。</span><span class="sxs-lookup"><span data-stu-id="3c97c-176">For more information, see [Microsoft Edge Sync](microsoft-edge-enterprise-sync.md) and [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

#### <span data-ttu-id="3c97c-177">Microsoft Edge 是否支持 Microsoft Edge 和 IE 之间的同步？</span><span class="sxs-lookup"><span data-stu-id="3c97c-177">Will Microsoft Edge ever support syncing between Microsoft Edge and IE?</span></span>

<span data-ttu-id="3c97c-178">尚无支持此同步的计划。</span><span class="sxs-lookup"><span data-stu-id="3c97c-178">There are no plans to support this syncing.</span></span> <span data-ttu-id="3c97c-179">如果你的环境仍需要 IE 来支持旧版应用，请考虑使用我们的[新 IE 模式](https://docs.microsoft.com/deployedge/edge-ie-mode)。</span><span class="sxs-lookup"><span data-stu-id="3c97c-179">If you still need IE in your environment to support legacy apps, consider our [new IE mode](https://docs.microsoft.com/deployedge/edge-ie-mode).</span></span>

#### <span data-ttu-id="3c97c-180">Microsoft Edge 是否将与 Microsoft Edge 旧版同步？</span><span class="sxs-lookup"><span data-stu-id="3c97c-180">Will Microsoft Edge sync with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="3c97c-181">否，不会同步。</span><span class="sxs-lookup"><span data-stu-id="3c97c-181">No, it won't.</span></span> <span data-ttu-id="3c97c-182">我们认为连接这两个生态系统将降低 Microsoft Edge 同步的可靠性。</span><span class="sxs-lookup"><span data-stu-id="3c97c-182">We believe connecting these two ecosystems will lead to compromises in the reliability of sync in the Microsoft Edge.</span></span> <span data-ttu-id="3c97c-183">我们会确保将现有数据迁移到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="3c97c-183">We will ensure that existing data is migrated to the Microsoft Edge.</span></span> <span data-ttu-id="3c97c-184">用户还可以从他们选择的浏览器导入数据。</span><span class="sxs-lookup"><span data-stu-id="3c97c-184">Users will also be able to import data from browser of their choice.</span></span> <span data-ttu-id="3c97c-185">这也意味着新版 Microsoft Edge 浏览器将无法与 IE 同步。</span><span class="sxs-lookup"><span data-stu-id="3c97c-185">This also means that new Microsoft Edge browser won't have a way to sync with IE.</span></span>

### <span data-ttu-id="3c97c-186">管理同步</span><span class="sxs-lookup"><span data-stu-id="3c97c-186">MANAGING SYNC</span></span>

#### <span data-ttu-id="3c97c-187">是否可以阻止我的用户与个人租户同步？</span><span class="sxs-lookup"><span data-stu-id="3c97c-187">Is it possible to stop my users from syncing with a personal tenant?</span></span>

<span data-ttu-id="3c97c-188">无法直接阻止，但你可以使用 [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) 策略确定哪些配置文件可以登录到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="3c97c-188">Not directly, but you can determine which profiles can sign on to Microsoft Edge using the [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) policy.</span></span>

## <span data-ttu-id="3c97c-189">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c97c-189">See also</span></span>

- [<span data-ttu-id="3c97c-190">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="3c97c-190">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="3c97c-191">Microsoft Edge 和企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="3c97c-191">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
