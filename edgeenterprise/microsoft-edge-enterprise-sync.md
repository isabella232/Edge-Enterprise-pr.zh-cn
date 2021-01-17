---
title: 配置 Microsoft Edge 同步并排除故障
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 01/14/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 配置 Microsoft Edge 同步并排除故障
ms.openlocfilehash: fa9b9ead6319bceeb95066003a77be7ecf84db46
ms.sourcegitcommit: 68b50c45b2b78acec5a0776ce4ddd11410a4e382
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "11270750"
---
# <span data-ttu-id="8c9da-103">配置 Microsoft Edge 同步并排除故障</span><span class="sxs-lookup"><span data-stu-id="8c9da-103">Configure and troubleshoot Microsoft Edge sync</span></span>

<span data-ttu-id="8c9da-104">本文介绍如何配置和使用 Microsoft Edge，以便在所有已登录设备上同步收藏夹、密码和其他浏览器数据。</span><span class="sxs-lookup"><span data-stu-id="8c9da-104">This article explains how to configure and use Microsoft Edge to sync your favorites, passwords, and other browser data across all your signed-in devices.</span></span> <span data-ttu-id="8c9da-105">本文还提供了有关最常见同步问题的故障排除步骤。</span><span class="sxs-lookup"><span data-stu-id="8c9da-105">This article also provides troubleshooting steps for the most commonly encountered sync issues.</span></span> <span data-ttu-id="8c9da-106">其中还包括用于收集故障排除所需日志的推荐工具。</span><span class="sxs-lookup"><span data-stu-id="8c9da-106">It also includes the recommended tools for gathering the logs needed for troubleshooting.</span></span>

> [!NOTE]
> <span data-ttu-id="8c9da-107">除非另有说明，否则本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="8c9da-107">Applies to Microsoft Edge version 77 or later unless otherwise noted.</span></span>

## <span data-ttu-id="8c9da-108">概述</span><span class="sxs-lookup"><span data-stu-id="8c9da-108">Overview</span></span>

<span data-ttu-id="8c9da-109">通过 Microsoft Edge 同步，用户可以访问他们所有已登录设备上的浏览数据。</span><span class="sxs-lookup"><span data-stu-id="8c9da-109">Microsoft Edge sync enables users to access their browsing data across all their signed-in devices.</span></span> <span data-ttu-id="8c9da-110">同步支持的数据包括：</span><span class="sxs-lookup"><span data-stu-id="8c9da-110">The data supported by sync includes:</span></span>

- <span data-ttu-id="8c9da-111">收藏夹</span><span class="sxs-lookup"><span data-stu-id="8c9da-111">Favorites</span></span>
- <span data-ttu-id="8c9da-112">密码</span><span class="sxs-lookup"><span data-stu-id="8c9da-112">Passwords</span></span>
- <span data-ttu-id="8c9da-113">地址等（表单填写）</span><span class="sxs-lookup"><span data-stu-id="8c9da-113">Addresses and more (form-fill)</span></span>
- <span data-ttu-id="8c9da-114">收藏</span><span class="sxs-lookup"><span data-stu-id="8c9da-114">Collections</span></span>
- <span data-ttu-id="8c9da-115">“设置”</span><span class="sxs-lookup"><span data-stu-id="8c9da-115">Settings</span></span>
- <span data-ttu-id="8c9da-116">扩展</span><span class="sxs-lookup"><span data-stu-id="8c9da-116">Extension</span></span>
- <span data-ttu-id="8c9da-117">打开选项卡（在 Microsoft Edge 版本 88 中可用）</span><span class="sxs-lookup"><span data-stu-id="8c9da-117">Open tabs (available in Microsoft Edge version 88)</span></span>
- <span data-ttu-id="8c9da-118">历史记录（在 Microsoft Edge 版本 88 中可用）</span><span class="sxs-lookup"><span data-stu-id="8c9da-118">History (available in Microsoft Edge version 88)</span></span>

<span data-ttu-id="8c9da-119">用户同意后即可启用同步功能，并且用户可以针对上面列出的每种数据类型打开或关闭同步功能。</span><span class="sxs-lookup"><span data-stu-id="8c9da-119">Sync functionality is enabled via user consent and users can turn sync on or off for each of the data types listed above.</span></span>

> [!NOTE]
> <span data-ttu-id="8c9da-120">将上载其他设备连接和配置数据（如设备名称、品牌和型号），以支持同步功能。</span><span class="sxs-lookup"><span data-stu-id="8c9da-120">Additional device connectivity and configuration data (such as device name, make and model) is uploaded to support sync functionality.</span></span>

## <span data-ttu-id="8c9da-121">必备条件</span><span class="sxs-lookup"><span data-stu-id="8c9da-121">Prerequisites</span></span>

<span data-ttu-id="8c9da-122">适用于 Azure Active Directory (Azure AD) 帐户的 Microsoft Edge 同步功能可供以下任何订阅使用：</span><span class="sxs-lookup"><span data-stu-id="8c9da-122">Microsoft Edge sync for Azure Active Directory (Azure AD) accounts is available for any of the following subscriptions:</span></span>

- <span data-ttu-id="8c9da-123">Azure AD Premium（P1 或 P2）</span><span class="sxs-lookup"><span data-stu-id="8c9da-123">Azure AD Premium (P1 or P2)</span></span>
- <span data-ttu-id="8c9da-124">M365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="8c9da-124">M365 Business Premium</span></span>
- <span data-ttu-id="8c9da-125">Office 365 E1 及更高版本</span><span class="sxs-lookup"><span data-stu-id="8c9da-125">Office 365 E1 and above</span></span>
- <span data-ttu-id="8c9da-126">Azure 信息保护 (AIP)（P1 或 P2）</span><span class="sxs-lookup"><span data-stu-id="8c9da-126">Azure Information Protection (AIP) (P1 or P2)</span></span>
- <span data-ttu-id="8c9da-127">所有 EDU 订阅（Microsoft 教育应用版（学生）或 Microsoft 教育应用版（教职员工）、Exchange Online 学生版或教职员工版、O365 A1 或更高版本、M365 A1 或更高版本，或者适用于学生或教职员的 Azure 信息保护 P1 或 P2）</span><span class="sxs-lookup"><span data-stu-id="8c9da-127">All EDU subscriptions (Microsoft Apps for Students or Faculty, Exchange Online for Students or Faculty, O365 A1 or above, M365 A1 or above, or Azure Information Protection P1 or P2 for Students or Faculty)</span></span>

## <span data-ttu-id="8c9da-128">同步组策略</span><span class="sxs-lookup"><span data-stu-id="8c9da-128">Sync group policies</span></span>

<span data-ttu-id="8c9da-129">你可以使用以下组策略配置和管理 Microsoft Edge 同步：</span><span class="sxs-lookup"><span data-stu-id="8c9da-129">You can use the following group policies to configure and manage Microsoft Edge sync:</span></span>

- <span data-ttu-id="8c9da-130">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled)：完全禁用同步。</span><span class="sxs-lookup"><span data-stu-id="8c9da-130">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): Disables sync completely.</span></span>
- <span data-ttu-id="8c9da-131">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled)：禁止保存浏览历史记录和同步。此策略还将禁用打开选项卡同步。</span><span class="sxs-lookup"><span data-stu-id="8c9da-131">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): Disables saving browsing history and sync. This policy also disables open-tabs sync.</span></span>
- <span data-ttu-id="8c9da-132">[AllowDeletingBrowserHistory](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory)：当此策略设置为禁用时，还将禁用历史记录同步。</span><span class="sxs-lookup"><span data-stu-id="8c9da-132">[AllowDeletingBrowserHistory](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory): When this policy is set to disabled, history sync will also be disabled.</span></span>
- <span data-ttu-id="8c9da-133">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled)：配置从同步中排除的类型列表。</span><span class="sxs-lookup"><span data-stu-id="8c9da-133">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): Configure the list of types that are excluded from synchronization.</span></span>
- <span data-ttu-id="8c9da-134">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled)：允许 Active Directory (AD) 配置文件使用本地存储。</span><span class="sxs-lookup"><span data-stu-id="8c9da-134">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): Allow Active Directory (AD) profiles to use on-premises storage.</span></span> <span data-ttu-id="8c9da-135">有关更多信息，请参阅 [Active Directory (AD) 用户的本地同步](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync)。</span><span class="sxs-lookup"><span data-stu-id="8c9da-135">For more information, see [On-premises sync for Active Directory (AD) users](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync).</span></span>
- <span data-ttu-id="8c9da-136">[ForceSync：]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync)默认启用同步，无需用户同意。</span><span class="sxs-lookup"><span data-stu-id="8c9da-136">[ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): Turn on sync by default and do not require user consent to sync.</span></span>  

## <span data-ttu-id="8c9da-137">配置 Microsoft Edge 同步</span><span class="sxs-lookup"><span data-stu-id="8c9da-137">Configure Microsoft Edge sync</span></span>

<span data-ttu-id="8c9da-138">Azure 信息保护 (AIP) 服务提供了 Microsoft Edge 同步的配置选项。</span><span class="sxs-lookup"><span data-stu-id="8c9da-138">Configuration options for Microsoft Edge sync are available through the Azure Information Protection (AIP) service.</span></span> <span data-ttu-id="8c9da-139">为租户启用 AIP 后，无论获得何种许可，所有用户均可同步 Microsoft Edge 数据。</span><span class="sxs-lookup"><span data-stu-id="8c9da-139">When AIP is enabled for a tenant, all users can sync Microsoft Edge data, regardless of licensing.</span></span> <span data-ttu-id="8c9da-140">有关如何启用 AIP 的说明，请参阅[此处](https://docs.microsoft.com/azure/information-protection/activate-office365)。</span><span class="sxs-lookup"><span data-stu-id="8c9da-140">Instructions on how to enable AIP can be found [here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span>

<span data-ttu-id="8c9da-141">若要限制某一组用户使用同步功能，可为这些用户启用 [AIP 登录控制策略](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true) 。</span><span class="sxs-lookup"><span data-stu-id="8c9da-141">To restrict sync to certain set of users, you can enable the [AIP onboarding control policy](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true) for those users.</span></span> <span data-ttu-id="8c9da-142">如果确保所有必需的用户均加入后同步仍不可用，请确保已使用 [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true) PowerShell cmdlet 启用 IPCv3Service。</span><span class="sxs-lookup"><span data-stu-id="8c9da-142">If sync is still not available after ensuring that all necessary users are onboarded, ensure that the IPCv3Service is enabled using the [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true)  PowerShell cmdlet.</span></span>

> [!CAUTION]
> <span data-ttu-id="8c9da-143">激活 Azure 信息保护还将允许其他应用程序（如 Microsoft Word 或 Microsoft Outlook）使用 AIP 保护内容。</span><span class="sxs-lookup"><span data-stu-id="8c9da-143">Activating Azure Information Protection will also allow other applications, such as Microsoft Word or Microsoft Outlook, to protect content with AIP.</span></span> <span data-ttu-id="8c9da-144">此外，用于限制 Microsoft Edge 同步的任何载入控制策略也将限制其他应用程序使用 AIP 保护内容。</span><span class="sxs-lookup"><span data-stu-id="8c9da-144">In addition, any onboarding control policy used to restrict Edge sync will also restrict other applications from protecting content using AIP.</span></span>

## <span data-ttu-id="8c9da-145">Microsoft Edge 和企业状态漫游 (ESR) </span><span class="sxs-lookup"><span data-stu-id="8c9da-145">Microsoft Edge and Enterprise State Roaming (ESR)</span></span>

<span data-ttu-id="8c9da-146">Microsoft Edge 是一个跨平台应用程序，扩展了跨用户的所有设备同步用户数据的范围，并且不再是 Azure AD 企业状态漫游的一部分。</span><span class="sxs-lookup"><span data-stu-id="8c9da-146">Microsoft Edge is a cross-platform application with an expanded scope for syncing user data across all their devices and is no longer a part of Azure AD Enterprise State Roaming.</span></span> <span data-ttu-id="8c9da-147">但是，Microsoft Edge 将履行 ESR 的数据保护承诺，例如能够引入你自己的密钥。</span><span class="sxs-lookup"><span data-stu-id="8c9da-147">However, the Microsoft Edge will fulfill the data protection promises of ESR, such as the ability to bring your own key.</span></span> <span data-ttu-id="8c9da-148">有关详细信息，请参阅 [Microsoft Edge 和企业状态漫游](microsoft-edge-enterprise-state-roaming.md)。</span><span class="sxs-lookup"><span data-stu-id="8c9da-148">For more information, see [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

## <span data-ttu-id="8c9da-149">同步问题故障排除</span><span class="sxs-lookup"><span data-stu-id="8c9da-149">Troubleshoot sync issues</span></span>

<span data-ttu-id="8c9da-150">本部分提供了针对常见同步问题的故障排除步骤。</span><span class="sxs-lookup"><span data-stu-id="8c9da-150">This section provides troubleshooting steps for the most encountered sync issues.</span></span> <span data-ttu-id="8c9da-151">其中还包括用于收集故障排除所需日志的推荐工具。</span><span class="sxs-lookup"><span data-stu-id="8c9da-151">It also includes the recommended tools for gathering the logs needed for troubleshooting.</span></span>

### <span data-ttu-id="8c9da-152">标识问题与同步问题</span><span class="sxs-lookup"><span data-stu-id="8c9da-152">Identity issues versus sync issues</span></span>

<span data-ttu-id="8c9da-153">在浏览器中维护用户标识的一个常见用例是支持同步。因此，标识问题经常与同步问题混淆。</span><span class="sxs-lookup"><span data-stu-id="8c9da-153">A popular use case for maintaining user identity in the browser is to support sync. For this reason, identity issues are frequently confused with sync issues.</span></span> <span data-ttu-id="8c9da-154">在开始排除同步故障之前，请了解标识和同步问题的区别。</span><span class="sxs-lookup"><span data-stu-id="8c9da-154">Understand the difference between identity and sync issue before you start troubleshooting sync.</span></span>

<span data-ttu-id="8c9da-155">在将某个问题视为同步问题之前，请检查用户是否已使用有效帐户登录浏览器。</span><span class="sxs-lookup"><span data-stu-id="8c9da-155">Before you treat an issue as a sync issue, check to see if the user is signed into the browser with a valid account.</span></span>

<span data-ttu-id="8c9da-156">接下来的屏幕截图显示了在 *edge://sync-internals* 中出现在“**Credentials**”下的标识错误示例：</span><span class="sxs-lookup"><span data-stu-id="8c9da-156">The next screenshot shows an example of an identity error found in *edge://sync-internals* under **Credentials**:</span></span>

:::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-identity-issue.png" alt-text="标识错误":::

### <span data-ttu-id="8c9da-158">常见同步问题</span><span class="sxs-lookup"><span data-stu-id="8c9da-158">Common sync issues</span></span>

#### <span data-ttu-id="8c9da-159">问题：无法访问 M365 或 Azure 信息保护订阅</span><span class="sxs-lookup"><span data-stu-id="8c9da-159">Issue: Can't access M365 or Azure Information Protection subscription</span></span>

<span data-ttu-id="8c9da-160">你是不是以前拥有的 M365 或 Azure 信息保护 (AIP) 订阅已过期，然后替换成了新订阅？</span><span class="sxs-lookup"><span data-stu-id="8c9da-160">Do you have a previous M365 or Azure Information Protection (AIP) subscription that expired and then replaced with a new subscription?</span></span> <span data-ttu-id="8c9da-161">如果是，则租户 ID 已更改，需要重置服务数据。</span><span class="sxs-lookup"><span data-stu-id="8c9da-161">If so, then the tenant ID has changed and the service data needs to be reset.</span></span> <span data-ttu-id="8c9da-162">请参阅**遇到密码器错误**问题中有关重置数据的说明。</span><span class="sxs-lookup"><span data-stu-id="8c9da-162">See the instructions for resetting data in the **Cryptographer error encountered** issue.</span></span>

#### <span data-ttu-id="8c9da-163">问题：“此帐户无法使用同步功能。”</span><span class="sxs-lookup"><span data-stu-id="8c9da-163">Issue: “Sync is not available for this account.”</span></span>

<span data-ttu-id="8c9da-164">如果 Azure Active Directory 帐户遇到此错误，或 *edge://sync-internals* 中出现 DISABLED_BY_ADMIN，请按顺序执行下一过程中的步骤，直到问题得到解决。</span><span class="sxs-lookup"><span data-stu-id="8c9da-164">If this error is encountered for an Azure Active Directory account, or if DISABLED_BY_ADMIN appears in *edge://sync-internals*, follow the steps in the next procedure sequentially until the problem is fixed.</span></span>

> [!NOTE]
> <span data-ttu-id="8c9da-165">由于此错误的来源通常需要在 Azure Active Directory 租户中更改配置，因此这些故障排除步骤只能由租户管理员执行，而不能由最终用户执行。</span><span class="sxs-lookup"><span data-stu-id="8c9da-165">Because the source of this error is usually requires a configuration change in an Azure Active Directory tenant, these troubleshooting steps can only performed by a tenant admin and not by end users.</span></span>

1. <span data-ttu-id="8c9da-166">验证企业租户是否具有受支持的 M365 订阅。</span><span class="sxs-lookup"><span data-stu-id="8c9da-166">Verify that the enterprise tenant has a supported M365 subscription.</span></span> <span data-ttu-id="8c9da-167">[此处](https://docs.microsoft.com/azure/information-protection/activate-office365)提供了可用订阅类型的当前列表。</span><span class="sxs-lookup"><span data-stu-id="8c9da-167">The current list of available subscription types is [provided here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span> <span data-ttu-id="8c9da-168">如果租户没有受支持的订阅，他们可以单独购买 Azure 信息保护，也可以升级到受支持的某个订阅。</span><span class="sxs-lookup"><span data-stu-id="8c9da-168">If the tenant doesn't have a supported subscription, they can either purchase Azure Information Protection separately, or upgrade to one of the supported subscriptions.</span></span>
2. <span data-ttu-id="8c9da-169">如果具有受支持的订阅，请验证租户是否具有可用的 Azure 信息保护 (AIP)。</span><span class="sxs-lookup"><span data-stu-id="8c9da-169">If a supported subscription is available, verify that the tenant has Azure Information Protection (AIP) available.</span></span> <span data-ttu-id="8c9da-170">有关检查 AIP 状态以及在必要时激活 AIP 的说明，请参阅[此处](https://docs.microsoft.com/azure/information-protection/activate-office365)。</span><span class="sxs-lookup"><span data-stu-id="8c9da-170">The instructions for checking the AIP status and, if necessary, activating AIP are [here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span>
3. <span data-ttu-id="8c9da-171">如果步骤 2 显示 AIP 处于活动状态，但仍无法使用同步功能，请启用企业状态漫游 (ESR)。</span><span class="sxs-lookup"><span data-stu-id="8c9da-171">If step 2 shows that AIP is active but sync still doesn't work, turn on Enterprise State Roaming (ESR).</span></span> <span data-ttu-id="8c9da-172">有关启用 ESR 的说明，请参阅[此处](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)。</span><span class="sxs-lookup"><span data-stu-id="8c9da-172">The instructions for enabling ESR are [here](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span> <span data-ttu-id="8c9da-173">请注意，无需将 ESR 保持启用状态。</span><span class="sxs-lookup"><span data-stu-id="8c9da-173">Note that ESR does not need to stay on.</span></span> <span data-ttu-id="8c9da-174">如果此步骤修复了问题，可以禁用 ESR。</span><span class="sxs-lookup"><span data-stu-id="8c9da-174">You can turn off ESR if this step fixes the issue.</span></span>
4. <span data-ttu-id="8c9da-175">确认 Azure 信息保护未通过载入策略确定作用域。</span><span class="sxs-lookup"><span data-stu-id="8c9da-175">Confirm that Azure Information Protection is not scoped via an onboarding policy.</span></span> <span data-ttu-id="8c9da-176">你可以使用 [Get-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell 小程序来查看是否启用了作用域功能。</span><span class="sxs-lookup"><span data-stu-id="8c9da-176">You can use the [Get-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmonboardingcontrolpolicy?view=azureipps)  PowerShell applet to see if scoping is enabled.</span></span> <span data-ttu-id="8c9da-177">接下来的两个示例显示了一个无作用域配置和一个作用域为特定安全组的配置。</span><span class="sxs-lookup"><span data-stu-id="8c9da-177">The next two examples show an unscoped configuration and a configuration scoped to a specific security group.</span></span>

   ```powershell
    PS C:\Work\scripts\PowerShell> Get-AadrmOnboardingControlPolicy
 
    UseRmsUserLicense SecurityGroupObjectId                Scope
    ----------------- ---------------------                -----
                False 
   ```

   ```powershell

    PS C:\Work\scripts\PowerShell> Get-AadrmOnboardingControlPolicy
 
    UseRmsUserLicense SecurityGroupObjectId                Scope
    ----------------- ---------------------                -----
                False f1488a05-8196-40a6-9483-524948b90282   All
   ```


   <span data-ttu-id="8c9da-178">如果启用了作用域功能，则应该将受影响的用户添加到相应作用域的安全组，或者删除该作用域。</span><span class="sxs-lookup"><span data-stu-id="8c9da-178">If scoping is enabled, the affected user should either be added to the security group for the scope, or the scope should be removed.</span></span> <span data-ttu-id="8c9da-179">在下面的示例中，载入将 AIP 的作用域设定成了指示的安全组，应该使用 [Set-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell 小程序删除作用域功能。</span><span class="sxs-lookup"><span data-stu-id="8c9da-179">In the example below, onboarding has scoped AIP to the indicated security group and the scoping should be removed with the [Set-AadrmOnboardingControlPolicy](https://docs.microsoft.com/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell applet.</span></span>

5. <span data-ttu-id="8c9da-180">确认已在租户中启用 IPCv3Service。</span><span class="sxs-lookup"><span data-stu-id="8c9da-180">Confirm that the IPCv3Service is turned on in the tenant.</span></span> <span data-ttu-id="8c9da-181">[Get-AadrmConfiguration](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmconfiguration?view=azureipps) PowerShell 小程序可显示该服务的状态。</span><span class="sxs-lookup"><span data-stu-id="8c9da-181">The [Get-AadrmConfiguration](https://docs.microsoft.com/powershell/module/aadrm/get-aadrmconfiguration?view=azureipps)  PowerShell applet shows the status of the service.</span></span>

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-scoped-cfg-example.png" alt-text="检查是否已启用 IPCv3Service。":::

6. <span data-ttu-id="8c9da-183">如果未能解决问题，请与 [Microsoft Edge 支持人员](https://www.microsoftedgeinsider.com/support)联系。</span><span class="sxs-lookup"><span data-stu-id="8c9da-183">If the issue isn't fixed, contact [Microsoft Edge support](https://www.microsoftedgeinsider.com/support).</span></span>

#### <span data-ttu-id="8c9da-184">问题：卡在“正在设置同步...”或“无法连接到同步服务器。</span><span class="sxs-lookup"><span data-stu-id="8c9da-184">Issue: Stuck at "Setting up sync..." or “Couldn’t connect to the sync server.</span></span> <span data-ttu-id="8c9da-185">正在重试…”环节</span><span class="sxs-lookup"><span data-stu-id="8c9da-185">Retrying…”</span></span>

1. <span data-ttu-id="8c9da-186">尝试注销，然后再登录。</span><span class="sxs-lookup"><span data-stu-id="8c9da-186">Try to sign out and then sign in.</span></span>
2. <span data-ttu-id="8c9da-187">转到 *edge://sync-internals*。</span><span class="sxs-lookup"><span data-stu-id="8c9da-187">Go to *edge://sync-internals*.</span></span> <span data-ttu-id="8c9da-188">如果“**Type info**”部分下存在以下错误，请跳到以下问题：**遇到密码器错误**。</span><span class="sxs-lookup"><span data-stu-id="8c9da-188">If under the "**Type info**" section the following error is present, then  skip to the following issue, **Cryptographer error encountered**.</span></span>

   `"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered"`

3. <span data-ttu-id="8c9da-189">尝试 ping 服务器终结点。</span><span class="sxs-lookup"><span data-stu-id="8c9da-189">Try pinging the server endpoint.</span></span> <span data-ttu-id="8c9da-190">*edge://sync-internals* 中提供了客户端的服务器终结点。</span><span class="sxs-lookup"><span data-stu-id="8c9da-190">The server endpoint for a client is available in *edge://sync-internals*.</span></span> <span data-ttu-id="8c9da-191">接下来的屏幕截图显示了“**Environment Info**”下的终结点信息。</span><span class="sxs-lookup"><span data-stu-id="8c9da-191">The next screenshot shows endpoint information under **Environment Info**.</span></span>

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-endpoint-info.png" alt-text="终结点信息":::

4. <span data-ttu-id="8c9da-193">如果服务器终结点为空，或者无法对服务器执行 ping 操作且环境中存在防火墙，请确认客户端计算机可以使用必要的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="8c9da-193">If the server endpoint is empty, or if server cannot be pinged and a firewall is present in the environment, confirm that the necessary service endpoints are available to the client computer.</span></span>

   - <span data-ttu-id="8c9da-194">Microsoft Edge 同步服务终结点：</span><span class="sxs-lookup"><span data-stu-id="8c9da-194">Microsoft Edge sync service endpoints:</span></span>
     - [https://edge-enterprise.activity.windows.com](https://edge-enterprise.activity.windows.com)
     - [https://edge.activity.windows.com](https://edge.activity.windows.com)
    - <span data-ttu-id="8c9da-195">Azure 信息保护终结点：</span><span class="sxs-lookup"><span data-stu-id="8c9da-195">Azure Information Protection endpoints:</span></span>
      - <span data-ttu-id="8c9da-196">[https://api.aadrm.com](https://api.aadrm.com)（适用于大多数租户）</span><span class="sxs-lookup"><span data-stu-id="8c9da-196">[https://api.aadrm.com](https://api.aadrm.com) (for most tenants)</span></span>
      - <span data-ttu-id="8c9da-197">[https://api.aadrm.de](https://api.aadrm.de)（适用于德国的租户）</span><span class="sxs-lookup"><span data-stu-id="8c9da-197">[https://api.aadrm.de](https://api.aadrm.de) (for tenants in Germany)</span></span>
      - <span data-ttu-id="8c9da-198">[https://api.aadrm.cn](https://api.aadrm.cn)（适用于中国的租户）</span><span class="sxs-lookup"><span data-stu-id="8c9da-198">[https://api.aadrm.cn](https://api.aadrm.cn) (for tenants in China)</span></span>
   - <span data-ttu-id="8c9da-199">[Windows 通知服务终结点](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)。</span><span class="sxs-lookup"><span data-stu-id="8c9da-199">[Windows Notification Service endpoints](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config).</span></span>

5. <span data-ttu-id="8c9da-200">如果仍未能解决问题，请与 [Microsoft Edge 支持人员](https://www.microsoftedgeinsider.com/support)联系。</span><span class="sxs-lookup"><span data-stu-id="8c9da-200">If the issue still isn't fixed, contact [Microsoft Edge support](https://www.microsoftedgeinsider.com/support).</span></span>

### <span data-ttu-id="8c9da-201">问题：遇到密码器错误</span><span class="sxs-lookup"><span data-stu-id="8c9da-201">Issue: Cryptographer error encountered</span></span>

<span data-ttu-id="8c9da-202">此错误显示在 *edge://sync-internals* 中的“**Type info**”下，并且可能意味着需要重置用户的服务器端数据。</span><span class="sxs-lookup"><span data-stu-id="8c9da-202">This error is visible under **Type info** in *edge://sync-internals* and may mean that the user's service side data needs to be reset.</span></span> <span data-ttu-id="8c9da-203">接下来的屏幕截图显示了密码器错误的详细信息示例。</span><span class="sxs-lookup"><span data-stu-id="8c9da-203">The next screenshot shows an example of the details for a cryptography error.</span></span>

:::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-crypto-error-new.png" alt-text="密码器错误。":::

1. <span data-ttu-id="8c9da-205">重新启动 Microsoft Edge 并导航到 *edge://sync-internals*，检查“**AAD Account Key Status**”部分</span><span class="sxs-lookup"><span data-stu-id="8c9da-205">Restart Microsoft Edge and navigate to *edge://sync-internals* and check the “**AAD Account Key Status**” section</span></span>
   - <span data-ttu-id="8c9da-206">“Last MIP Result”中为“Success”：该密码器错误意味着服务器数据在加密时使用的可能是丢失的密钥。</span><span class="sxs-lookup"><span data-stu-id="8c9da-206">"Success" in "Last MIP Result": the cryptographer error means server data might be encrypted with a lost key.</span></span> <span data-ttu-id="8c9da-207">需要重置数据才能恢复同步。</span><span class="sxs-lookup"><span data-stu-id="8c9da-207">Data reset is needed to resume sync.</span></span>
   - <span data-ttu-id="8c9da-208">“Last MIP Result”中为“No permissions”：这可能是由 Azure AD 更改或租户订阅更改引起的。</span><span class="sxs-lookup"><span data-stu-id="8c9da-208">"No permissions" in "Last MIP Result": It is possibly caused by an Azure AD change or tenant subscription changes.</span></span> <span data-ttu-id="8c9da-209">需要重置数据才能恢复同步。</span><span class="sxs-lookup"><span data-stu-id="8c9da-209">Data reset is needed to resume sync.</span></span>
   - <span data-ttu-id="8c9da-210">其他错误可能意味着服务器配置问题。</span><span class="sxs-lookup"><span data-stu-id="8c9da-210">Other errors may mean server configuration issues.</span></span>
2. <span data-ttu-id="8c9da-211">如果需要重置数据，请参阅[重置云中的 Microsoft Edge 数据](edge-learnmore-reset-data-in-cloud.md)。</span><span class="sxs-lookup"><span data-stu-id="8c9da-211">If data reset is needed, see [Reset Microsoft Edge data in the cloud](edge-learnmore-reset-data-in-cloud.md).</span></span>

#### <span data-ttu-id="8c9da-212">问题：“管理员已禁用同步。”</span><span class="sxs-lookup"><span data-stu-id="8c9da-212">Issue: “Sync has been turned off by your administrator.”</span></span>

<span data-ttu-id="8c9da-213">确保未设置 [SyncDisabled 策略](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled)。</span><span class="sxs-lookup"><span data-stu-id="8c9da-213">Make sure that the [SyncDisabled policy](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled)  is not set.</span></span>

## <span data-ttu-id="8c9da-214">常见问题</span><span class="sxs-lookup"><span data-stu-id="8c9da-214">Frequently Asked Questions</span></span>

### <span data-ttu-id="8c9da-215">安全性和服务器/数据合规性</span><span class="sxs-lookup"><span data-stu-id="8c9da-215">SECURITY and SERVER/DATA COMPLIANCE</span></span>

#### <span data-ttu-id="8c9da-216">已同步的数据是否已加密？</span><span class="sxs-lookup"><span data-stu-id="8c9da-216">Is the synced data encrypted?</span></span>

<span data-ttu-id="8c9da-217">数据使用 TLS 1.2 或更高版本在传输中加密。</span><span class="sxs-lookup"><span data-stu-id="8c9da-217">The data is encrypted in transport using TLS 1.2 or greater.</span></span> <span data-ttu-id="8c9da-218">在 Microsoft 的服务中，所有数据类型都会使用 AES128 进行额外的静态加密。</span><span class="sxs-lookup"><span data-stu-id="8c9da-218">All data types are additionally encrypted at rest in Microsoft's service using AES128.</span></span> <span data-ttu-id="8c9da-219">除用于同步已打开标签页和历史记录的数据类型外，所有数据类型都会在离开用户设备之前使用 [Azure 信息保护](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern)策略所管理的密钥进行额外加密。</span><span class="sxs-lookup"><span data-stu-id="8c9da-219">All data types except those used for open tab and history sync are additionally encrypted before leaving the user’s device with keys managed via the [Azure Information Protection](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) policy.</span></span>

#### <span data-ttu-id="8c9da-220">为什么已打开标签页和历史记录数据没有更多的客户端加密？</span><span class="sxs-lookup"><span data-stu-id="8c9da-220">Why don’t open tab and history data have more client-side encryption?</span></span>

<span data-ttu-id="8c9da-221">为了降低最终用户设备上的资源利用率，系统将基于已打开标签页的漫游数据在服务器端生成历史记录数据。</span><span class="sxs-lookup"><span data-stu-id="8c9da-221">To reduce resource utilization on end-user devices, history data is generated server-side based on open tab roaming data.</span></span> <span data-ttu-id="8c9da-222">此过程无法支持此类数据的客户端加密。</span><span class="sxs-lookup"><span data-stu-id="8c9da-222">This process would not be possible with client-side encryption of this data.</span></span> <span data-ttu-id="8c9da-223">若要禁用打开选项卡和历史记录同步，请应用 [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled) 或 [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) 策略。</span><span class="sxs-lookup"><span data-stu-id="8c9da-223">To disable open tab and history sync, apply the [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled) or [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) policies.</span></span>

#### <span data-ttu-id="8c9da-224">租户管理员能否使用自己的密钥？</span><span class="sxs-lookup"><span data-stu-id="8c9da-224">Can tenant admins bring their own key?</span></span>

<span data-ttu-id="8c9da-225">是，可通过  [Azure 信息保护](https://azure.microsoft.com/services/information-protection/)来实现。</span><span class="sxs-lookup"><span data-stu-id="8c9da-225">Yes, through [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>

#### <span data-ttu-id="8c9da-226">Microsoft Edge 的同步数据存储在哪里？</span><span class="sxs-lookup"><span data-stu-id="8c9da-226">Where is Microsoft Edge sync data stored?</span></span>

<span data-ttu-id="8c9da-227">Azure AD 帐户的同步数据将根据租户 ID 存储在安全服务器中。</span><span class="sxs-lookup"><span data-stu-id="8c9da-227">Synced data for Azure AD accounts is stored in secure servers according to the tenant ID.</span></span> <span data-ttu-id="8c9da-228">例如，在美国注册的租户的数据存储在位于该地区地理位置的服务器上，并使用与 Office 应用程序相同的存储解决方案。</span><span class="sxs-lookup"><span data-stu-id="8c9da-228">For example, the data for a tenant that is registered in the United States is stored in servers geo-located for that region and uses the same storage solution as Office applications.</span></span>

#### <span data-ttu-id="8c9da-229">除了同步至 Microsoft Edge 外，数据是否会离开 Microsoft 云？</span><span class="sxs-lookup"><span data-stu-id="8c9da-229">Does the data ever leave Microsoft's cloud, aside from syncing to Microsoft Edge?</span></span>

<span data-ttu-id="8c9da-230">否。</span><span class="sxs-lookup"><span data-stu-id="8c9da-230">No.</span></span>

#### <span data-ttu-id="8c9da-231">企业同步属于哪项服务条款？</span><span class="sxs-lookup"><span data-stu-id="8c9da-231">What terms of service does enterprise sync fall under?</span></span>

<span data-ttu-id="8c9da-232">Microsoft Edge 同步服务条款已列入 Microsoft 软件许可证，可使用 Microsoft Edge 访问  *edge://terms* 进行查看。</span><span class="sxs-lookup"><span data-stu-id="8c9da-232">Terms of service for Microsoft Edge sync falls under the Microsoft software license viewable in Microsoft Edge at *edge://terms*.</span></span> <span data-ttu-id="8c9da-233">你的 Azure AD 订阅和服务条款最终属于 Microsoft 的[联机服务条款](https://www.microsoft.com/licensing/product-licensing/products)。</span><span class="sxs-lookup"><span data-stu-id="8c9da-233">Your Azure AD subscription and terms of service ultimately fall under Microsoft's [Online Service Terms](https://www.microsoft.com/licensing/product-licensing/products).</span></span>

#### <span data-ttu-id="8c9da-234">Microsoft Edge 是否支持政府社区云 (GCC) 高合规性？</span><span class="sxs-lookup"><span data-stu-id="8c9da-234">Does Microsoft Edge support Government Community Cloud (GCC) High compliance?</span></span>

<span data-ttu-id="8c9da-235">目前尚不支持。</span><span class="sxs-lookup"><span data-stu-id="8c9da-235">Not today.</span></span> <span data-ttu-id="8c9da-236">对于 GCC 高云中的客户，已禁用 Microsoft Edge 同步。</span><span class="sxs-lookup"><span data-stu-id="8c9da-236">For customers in the GCC High cloud, Microsoft Edge sync is disabled.</span></span>

### <span data-ttu-id="8c9da-237">应用同步</span><span class="sxs-lookup"><span data-stu-id="8c9da-237">APPLYING SYNC</span></span>

#### <span data-ttu-id="8c9da-238">为什么并非所有 M365 订阅都支持 Microsoft Edge 同步？</span><span class="sxs-lookup"><span data-stu-id="8c9da-238">Why isn’t Microsoft Edge sync supported in all M365 subscriptions?</span></span>

<span data-ttu-id="8c9da-239">企业同步取决于 [Azure 信息保护](https://azure.microsoft.com/services/information-protection/)，后者并非在所有 M365 订阅中都可用。</span><span class="sxs-lookup"><span data-stu-id="8c9da-239">Enterprise sync depends on[Azure Information Protection](https://azure.microsoft.com/services/information-protection/), which is not available in all M365 subscriptions.</span></span>

#### <span data-ttu-id="8c9da-240">Microsoft Edge 同步是否基于企业状态漫游？</span><span class="sxs-lookup"><span data-stu-id="8c9da-240">Is Microsoft Edge sync based on Enterprise State Roaming?</span></span>

<span data-ttu-id="8c9da-241">否。</span><span class="sxs-lookup"><span data-stu-id="8c9da-241">No.</span></span> <span data-ttu-id="8c9da-242">ESR 可用于启用同步，但 Microsoft Edge 同步不是 ESR 的一部分。</span><span class="sxs-lookup"><span data-stu-id="8c9da-242">ESR can be used to enable sync, but Microsoft Edge sync is not a part of ESR.</span></span> <span data-ttu-id="8c9da-243">有关详细信息，请参阅 [Microsoft Edge 同步](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-sync)和 [Microsoft Edge 和企业状态漫游](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-state-roaming)。</span><span class="sxs-lookup"><span data-stu-id="8c9da-243">For more information, see [Microsoft Edge Sync](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-sync) and [Microsoft Edge and Enterprise State Roaming](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-enterprise-state-roaming).</span></span>

#### <span data-ttu-id="8c9da-244">Microsoft Edge 是否支持 Microsoft Edge 和 IE 之间的同步？</span><span class="sxs-lookup"><span data-stu-id="8c9da-244">Will Microsoft Edge ever support syncing between Microsoft Edge and IE?</span></span>

<span data-ttu-id="8c9da-245">尚无支持此同步的计划。</span><span class="sxs-lookup"><span data-stu-id="8c9da-245">There are no plans to support this syncing.</span></span> <span data-ttu-id="8c9da-246">如果你的环境仍需要 IE 来支持旧版应用，请考虑使用我们的[新 IE 模式](https://docs.microsoft.com/deployedge/edge-ie-mode)。</span><span class="sxs-lookup"><span data-stu-id="8c9da-246">If you still need IE in your environment to support legacy apps, consider our [new IE mode](https://docs.microsoft.com/deployedge/edge-ie-mode).</span></span>

#### <span data-ttu-id="8c9da-247">Microsoft Edge 是否将与 Microsoft Edge 旧版同步？</span><span class="sxs-lookup"><span data-stu-id="8c9da-247">Will Microsoft Edge sync with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="8c9da-248">否，不会同步。</span><span class="sxs-lookup"><span data-stu-id="8c9da-248">No, it won't.</span></span> <span data-ttu-id="8c9da-249">我们认为连接这两个生态系统将降低 Microsoft Edge 同步的可靠性。</span><span class="sxs-lookup"><span data-stu-id="8c9da-249">We believe connecting these two ecosystems will lead to compromises in the reliability of sync in the Microsoft Edge.</span></span> <span data-ttu-id="8c9da-250">我们会确保将现有数据迁移到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="8c9da-250">We will ensure that existing data is migrated to the Microsoft Edge.</span></span> <span data-ttu-id="8c9da-251">用户还可以从自己选择的浏览器导入数据，这也意味着 Microsoft Edge 无法与 IE 同步。</span><span class="sxs-lookup"><span data-stu-id="8c9da-251">Users will also be able to import data from browser of their choice, which also means that Microsoft Edge won't have a way to sync with IE.</span></span>

### <span data-ttu-id="8c9da-252">管理同步</span><span class="sxs-lookup"><span data-stu-id="8c9da-252">MANAGING SYNC</span></span>

#### <span data-ttu-id="8c9da-253">是否可以阻止我的用户与个人租户同步？</span><span class="sxs-lookup"><span data-stu-id="8c9da-253">Is it possible to stop my users from syncing with a personal tenant?</span></span>

<span data-ttu-id="8c9da-254">无法直接阻止，但你可以使用 [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) 策略确定哪些配置文件可以登录到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="8c9da-254">Not directly, but you can determine which profiles can sign on to Microsoft Edge using the [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) policy.</span></span>

## <span data-ttu-id="8c9da-255">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c9da-255">See also</span></span>

- [<span data-ttu-id="8c9da-256">Microsoft Edge 企业同步</span><span class="sxs-lookup"><span data-stu-id="8c9da-256">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)
- [<span data-ttu-id="8c9da-257">Microsoft Edge 和企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="8c9da-257">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="8c9da-258">Microsoft Edge 企业版登录页面</span><span class="sxs-lookup"><span data-stu-id="8c9da-258">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
