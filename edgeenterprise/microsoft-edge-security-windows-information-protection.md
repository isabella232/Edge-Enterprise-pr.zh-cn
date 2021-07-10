---
title: Microsoft Edge 对 Windows 信息保护的支持
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 06/29/2029
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 对 Windows 信息保护的支持
ms.openlocfilehash: 53564d6089e84969501ac4802cf96dbdb1b24361
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642238"
---
# <a name="microsoft-edge-support-for-windows-information-protection-wip"></a><span data-ttu-id="2f8f6-103">Microsoft Edge 对 Windows 信息保护 (WIP) 的支持</span><span class="sxs-lookup"><span data-stu-id="2f8f6-103">Microsoft Edge support for Windows Information Protection (WIP)</span></span>

<span data-ttu-id="2f8f6-104">本文介绍 Microsoft Edge 对 Windows 信息保护 (WIP) 的支持情况。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-104">This article describes how Microsoft Edge supports Windows Information Protection (WIP).</span></span>

> [!NOTE]
> <span data-ttu-id="2f8f6-105">本文适用于 Microsoft Edge 版本 81 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-105">This applies to Microsoft Edge version 81 or later.</span></span>

## <a name="overview"></a><span data-ttu-id="2f8f6-106">概述</span><span class="sxs-lookup"><span data-stu-id="2f8f6-106">Overview</span></span>

<span data-ttu-id="2f8f6-107">Windows 信息保护 (WIP) 是一种 Windows 10 功能，可帮助保护企业数据免遭未经授权的或意外的泄露。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-107">Windows Information Protection (WIP) is a Windows 10 feature that helps protect enterprise data from unauthorized or accidental disclosure.</span></span> <span data-ttu-id="2f8f6-108">随着远程工作的增长，在工作场所之外共享公司数据会增加风险。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-108">With the rise of remote work, there's an increased risk of sharing corporate data outside the workplace.</span></span> <span data-ttu-id="2f8f6-109">在公司设备上进行个人活动和工作活动时，这种风险就会增加。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-109">This risk increases when personal activities and work activities occur on corporate devices.</span></span>

<span data-ttu-id="2f8f6-110">Microsoft Edge 支持 WIP 以在用户经常共享和分发内容的 Web 环境中帮助保护内容安全。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-110">Microsoft Edge supports WIP to help protect content in a web environment where users often share and distribute content.</span></span>

### <a name="system-requirements"></a><span data-ttu-id="2f8f6-111">系统要求</span><span class="sxs-lookup"><span data-stu-id="2f8f6-111">System requirements</span></span>

<span data-ttu-id="2f8f6-112">以下要求适用于企业中使用 WIP 的设备：</span><span class="sxs-lookup"><span data-stu-id="2f8f6-112">The follow requirements apply to devices using WIP in the enterprise:</span></span>

- <span data-ttu-id="2f8f6-113">Windows 10 版本 1607 或更高版本</span><span class="sxs-lookup"><span data-stu-id="2f8f6-113">Windows 10, version 1607 or later</span></span>
- <span data-ttu-id="2f8f6-114">仅 Windows 客户端 SKU</span><span class="sxs-lookup"><span data-stu-id="2f8f6-114">Only Windows client SKUs</span></span>
- <span data-ttu-id="2f8f6-115">[WIP 先决条件](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip#prerequisites)中描述的管理解决方案之一</span><span class="sxs-lookup"><span data-stu-id="2f8f6-115">One of the management solutions described in [WIP prerequisites](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip#prerequisites)</span></span>

### <a name="windows-information-protection-benefits"></a><span data-ttu-id="2f8f6-116">Windows 信息保护的优势</span><span class="sxs-lookup"><span data-stu-id="2f8f6-116">Windows Information Protection benefits</span></span>

<span data-ttu-id="2f8f6-117">WIP 具有以下优势：</span><span class="sxs-lookup"><span data-stu-id="2f8f6-117">WIP provides the following benefits:</span></span>

- <span data-ttu-id="2f8f6-118">个人和公司数据之间的明显分离，而不要求员工切换环境或应用。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-118">Obvious separation between personal and corporate data, without requiring employees to switch environments or apps.</span></span>
- <span data-ttu-id="2f8f6-119">对于现有业务线应用的其他数据保护，而无需更新应用。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-119">Additional data protection for existing line-of-business apps without a need to update the apps.</span></span>
- <span data-ttu-id="2f8f6-120">允许远程擦除 Intune 移动设备管理 (MDM) 注册的设备上的公司数据而不影响个人数据。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-120">The ability to remote wipes corporate data from Intune Mobile Device Management (MDM) enrolled devices while leaving personal data unaffected.</span></span> 
- <span data-ttu-id="2f8f6-121">有关跟踪问题以及补救措施（例如针对用户的合规性培训）的审核报告。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-121">Audit reports for tracking issues and for remedial actions such as compliance training for users.</span></span>
- <span data-ttu-id="2f8f6-122">与现有管理系统进行集成以配置、部署和管理 WIP。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-122">Integration with your existing management system to configure, deploy, and manage WIP.</span></span> <span data-ttu-id="2f8f6-123">一些示例包括 Microsoft Intune、Microsoft Endpoint Configuration Manager 或当前的移动设备管理 (MDM) 系统。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-123">Some examples are Microsoft Intune, Microsoft Endpoint Configuration Manager, or your current mobile device management (MDM) system.</span></span>

## <a name="wip-policy-and-protection-modes"></a><span data-ttu-id="2f8f6-124">WIP 策略和保护模式</span><span class="sxs-lookup"><span data-stu-id="2f8f6-124">WIP policy and protection modes</span></span>

<span data-ttu-id="2f8f6-125">使用策略可以配置下表中所述的四种保护模式。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-125">Using policies, you can configure the four protection modes described in the following table.</span></span> <span data-ttu-id="2f8f6-126">有关详细信息，请参阅 [WIP 保护模式](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip#wip-protection-modes)。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-126">For more information, see [WIP-protection modes](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip#wip-protection-modes).</span></span>

| <span data-ttu-id="2f8f6-127">模式</span><span class="sxs-lookup"><span data-stu-id="2f8f6-127">Mode</span></span> | <span data-ttu-id="2f8f6-128">描述</span><span class="sxs-lookup"><span data-stu-id="2f8f6-128">Description</span></span> |
|------|-------------|
| <span data-ttu-id="2f8f6-129">阻止</span><span class="sxs-lookup"><span data-stu-id="2f8f6-129">Block</span></span> | <span data-ttu-id="2f8f6-130">WIP 将查找不恰当的数据共享行为并阻止员工完成该操作。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-130">WIP looks for inappropriate data sharing practices and stops the employee from completing the action.</span></span> <span data-ttu-id="2f8f6-131">除了在应用之间共享企业数据或在组织网络之外尝试共享之外，此搜索还可以包括向非企业保护的应用共享企业数据。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-131">This search can include sharing enterprise data to non-enterprise-protected apps in addition to sharing enterprise data between apps or attempting to share outside of your organization's network.</span></span> |
| <span data-ttu-id="2f8f6-132">允许覆盖</span><span class="sxs-lookup"><span data-stu-id="2f8f6-132">Allow Overrides</span></span> | <span data-ttu-id="2f8f6-133">WIP 将查找不恰当的数据共享，当员工执行某些视为可能不安全的操作时会向他们发出警告。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-133">WIP looks for inappropriate data sharing, warning employees if they do something deemed potentially unsafe.</span></span> <span data-ttu-id="2f8f6-134">但是，此管理模式允许员工覆盖策略并共享数据，同时将该操作记录到审核日志。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-134">However, this management mode lets the employee override the policy and share the data, logging the action to your audit log.</span></span> |
| <span data-ttu-id="2f8f6-135">静默</span><span class="sxs-lookup"><span data-stu-id="2f8f6-135">Silent</span></span> | <span data-ttu-id="2f8f6-136">WIP 将静默运行，同时记录不恰当的数据共享，但不会阻止在“允许覆盖”模式下时本来会针对员工交互而发出的任何内容提示。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-136">WIP runs silently, logging inappropriate data sharing, without stopping anything that would have been prompted for employee interaction while in Allow Overrides mode.</span></span> <span data-ttu-id="2f8f6-137">像应用不恰当地尝试访问网络资源或 WIP 保护的数据等不被允许的操作仍将受到阻止。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-137">Unallowed actions, like apps inappropriately trying to access a network resource or WIP-protected data, are still stopped.</span></span> |
| <span data-ttu-id="2f8f6-138">关闭</span><span class="sxs-lookup"><span data-stu-id="2f8f6-138">Off</span></span> | <span data-ttu-id="2f8f6-139">WIP 将处于关闭状态，并且不会帮助保护或审核你的数据。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-139">WIP is turned off and doesn't help to protect or audit your data.</span></span> <span data-ttu-id="2f8f6-140">关闭 WIP 后，系统将尝试解密本地连接的驱动器上的任何 WIP 标记文件。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-140">After you turn off WIP, an attempt is made to decrypt any WIP-tagged files on the locally attached drives.</span></span> <span data-ttu-id="2f8f6-141">如果重新打开 WIP 保护，以前的解密和策略信息不会自动重新应用。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-141">Your previous decryption and policy info isn't automatically reapplied if you turn WIP protection back on.</span></span>
 |

## <a name="wip-features-supported-in-microsoft-edge"></a><span data-ttu-id="2f8f6-142">Microsoft Edge 支持的 WIP 功能</span><span class="sxs-lookup"><span data-stu-id="2f8f6-142">WIP features supported in Microsoft Edge</span></span>

<span data-ttu-id="2f8f6-143">Microsoft Edge 从版本 81 开始支持以下功能：</span><span class="sxs-lookup"><span data-stu-id="2f8f6-143">Starting with Microsoft Edge version 81, the following features are supported:</span></span>

- <span data-ttu-id="2f8f6-144">地址栏上的公文包图标将指示工作网站。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-144">Work sites will be indicated by a briefcase icon on the address bar.</span></span>  
- <span data-ttu-id="2f8f6-145">从工作位置下载的文件会自动加密。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-145">Files downloaded from a work location are automatically encrypted.</span></span>
- <span data-ttu-id="2f8f6-146">以静默/阻止/覆盖模式将工作文件上传到非工作位置。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-146">Silent/Block/Override enforcement for work file uploads to non-work locations.</span></span>  
- <span data-ttu-id="2f8f6-147">以静默/阻止/覆盖模式执行文件拖放操作。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-147">Silent/Block/Override enforcement for file Drag & Drop actions.</span></span>
- <span data-ttu-id="2f8f6-148">以静默/阻止/覆盖模式执行剪贴板操作。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-148">Silent/Block/Override enforcement for Clipboard actions.</span></span>
- <span data-ttu-id="2f8f6-149">从非工作配置文件浏览到工作位置会自动重定向到工作配置文件（与 Azure AD 标识相关联）。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-149">Browsing to work locations from non-work profiles automatically redirects to the Work Profile (associated with the Azure AD Identity.)</span></span>
- <span data-ttu-id="2f8f6-150">IE 模式支持完整的 WIP 功能。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-150">IE Mode supports full WIP functionality.</span></span>

## <a name="working-with-wip-in-microsoft-edge"></a><span data-ttu-id="2f8f6-151">在 Microsoft Edge 中使用 WIP</span><span class="sxs-lookup"><span data-stu-id="2f8f6-151">Working with WIP in Microsoft Edge</span></span>

<span data-ttu-id="2f8f6-152">为 Microsoft Edge 启用 WIP 支持后，用户将在访问工作相关信息时看到这一点。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-152">After WIP support is enabled for Microsoft Edge, users will see when work-related information is accessed.</span></span> <span data-ttu-id="2f8f6-153">下一个屏幕截图显示了地址栏中的公文包图标，表明可通过浏览器访问工作相关信息。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-153">The next screenshot shows the briefcase icon in the address bar, indicating that work-related information is accessed via the browser.</span></span>

 ![标记为“工作”的网站的地址栏指示器](./media/microsoft-edge-security-windows-information-protection/microsoft-edge-wip-notify.png)

<span data-ttu-id="2f8f6-155">Microsoft Edge 让用户能够在未批准的网站中共享受保护的内容。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-155">Microsoft Edge gives users the ability to share protected content in an unapproved website.</span></span> <span data-ttu-id="2f8f6-156">下一个屏幕截图显示了 Microsoft Edge 提示，允许用户在未批准的网站中使用受保护的内容。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-156">The next screenshot shows the Microsoft Edge prompt that allows a user to use protected content in an unapproved website.</span></span>

 ![受保护内容覆盖提示](./media/microsoft-edge-security-windows-information-protection/microsoft-edge-wip-override.png)

## <a name="configure-policies-to-support-wip"></a><span data-ttu-id="2f8f6-158">配置策略以支持 WIP</span><span class="sxs-lookup"><span data-stu-id="2f8f6-158">Configure policies to support WIP</span></span>

<span data-ttu-id="2f8f6-159">将 WIP 与 Microsoft Edge 配合使用时，需要存在工作配置文件。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-159">Using WIP with Microsoft Edge requires the presence of a work profile.</span></span>

### <a name="ensure-the-presence-of-a-work-profile"></a><span data-ttu-id="2f8f6-160">确保存在工作配置文件</span><span class="sxs-lookup"><span data-stu-id="2f8f6-160">Ensure the presence of a work profile</span></span>

<span data-ttu-id="2f8f6-161">在已加入混合的计算机上，Microsoft Edge 将自动使用 Azure Active Directory (Azure AD) 帐户登录。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-161">On hybrid joined machines, Microsoft Edge is automatically signed in with the Azure Active Directory (Azure AD) account.</span></span> <span data-ttu-id="2f8f6-162">若要确保用户不删除此配置文件（WIP 需要此配置文件），请配置以下策略：</span><span class="sxs-lookup"><span data-stu-id="2f8f6-162">To make sure that users don't remove this profile, which is needed for WIP, configure the following policy:</span></span>

- [<span data-ttu-id="2f8f6-163">NonRemovableProfileEnabled</span><span class="sxs-lookup"><span data-stu-id="2f8f6-163">NonRemovableProfileEnabled</span></span>](./microsoft-edge-policies.md#nonremovableprofileenabled)

> [!NOTE]
> <span data-ttu-id="2f8f6-164">如果你的环境未加入混合，则可以按照以下说明加入混合：[规划加入混合 Azure Active Directory 的实现方式](/azure/active-directory/devices/hybrid-azuread-join-plan)。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-164">If your environment isn't hybrid joined, you can hybrid join using these instructions: [Plan your hybrid Azure Active Directory join implementation](/azure/active-directory/devices/hybrid-azuread-join-plan).</span></span>

<span data-ttu-id="2f8f6-165">如果不能选择加入混合，则可以使用本地的 Active Directory 帐户，允许 Edge 使用用户的域帐户自动创建特殊工作配置文件。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-165">If hybrid joining isn't an option, you can use on-prem Active Directory accounts to allow Microsoft Edge to auto create a special work profile with the users' domain accounts.</span></span> <span data-ttu-id="2f8f6-166">请注意，本地帐户可能不会获得 Azure AD 的所有功能，如云同步、Office NTP 等。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-166">Note that on-premises accounts may not receive all of Azure AD's features, such as cloud sync, Office NTP, and so on.)</span></span>

#### <a name="active-directory-ad-accounts"></a><span data-ttu-id="2f8f6-167">Active Directory (AD) 帐户</span><span class="sxs-lookup"><span data-stu-id="2f8f6-167">Active Directory (AD) accounts</span></span>

<span data-ttu-id="2f8f6-168">对于 AD 帐户，必须配置以下策略，使 Microsoft Edge 自动创建一个特殊工作配置文件。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-168">For AD accounts, you must configure the following policy to have the Microsoft Edge auto create a special work profile.</span></span>

- [<span data-ttu-id="2f8f6-169">ConfigureOnPremisesAccountAutoSignIn</span><span class="sxs-lookup"><span data-stu-id="2f8f6-169">ConfigureOnPremisesAccountAutoSignIn</span></span>](./microsoft-edge-policies.md#configureonpremisesaccountautosignin)

### <a name="windows-policies-for-wip"></a><span data-ttu-id="2f8f6-170">适用于 WIP 的 Windows 策略</span><span class="sxs-lookup"><span data-stu-id="2f8f6-170">Windows policies for WIP</span></span>

<span data-ttu-id="2f8f6-171">可使用 Windows 策略配置 WIP。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-171">You can configure WIP using Windows policies.</span></span> <span data-ttu-id="2f8f6-172">有关详细信息，请参阅[使用 Microsoft Intune 创建和部署 WIP 策略](/windows/security/information-protection/windows-information-protection/overview-create-wip-policy)</span><span class="sxs-lookup"><span data-stu-id="2f8f6-172">For more information, see [Create and deploy WIP policies using Microsoft Intune](/windows/security/information-protection/windows-information-protection/overview-create-wip-policy)</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="2f8f6-173">常见问题</span><span class="sxs-lookup"><span data-stu-id="2f8f6-173">Frequently Asked Questions</span></span>

### <a name="how-do-i-resolve-error-code--2147024540"></a><span data-ttu-id="2f8f6-174">如何解决错误代码 - 2147024540？</span><span class="sxs-lookup"><span data-stu-id="2f8f6-174">How do I resolve Error Code -2147024540?</span></span>

<span data-ttu-id="2f8f6-175">此错误代码对应于以下 Windows 信息保护错误：*ERROR_EDP_POLICY_DENIES_OPERATION: 请求的操作已被 Windows 信息保护策略阻止。有关详细信息，请联系系统管理员。*</span><span class="sxs-lookup"><span data-stu-id="2f8f6-175">This error code corresponds to the following Windows Information Protection error: *ERROR_EDP_POLICY_DENIES_OPERATION: The requested operation was blocked by Windows Information Protection policy. For more information, contact your system administrator.*</span></span>

<span data-ttu-id="2f8f6-176">当组织已启用 Windows 信息保护 (WIP) 以仅允许具有已批准应用程序的用户访问公司资源时，Microsoft Edge 显示此错误。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-176">Microsoft Edge shows this error when the organization has enabled Windows Information Protection (WIP) to only allow users with approved applications to access corporate resources.</span></span> <span data-ttu-id="2f8f6-177">在这种情况下，由于 Microsoft Edge 不在已批准的应用程序列表上，因此管理员必须更新 WIP 策略以授予对 Microsoft Edge 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-177">In this case because Microsoft Edge isn't on the approved applications list, the admin will have to update the WIP policies to grant access to Microsoft Edge.</span></span>

<span data-ttu-id="2f8f6-178">以下屏幕截图显示了如何使用 Microsoft Intune 将 Microsoft Edge 添加为 WIP允许的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-178">The following screenshot shows how the Microsoft Intune is used to add Microsoft Edge as an allowed app for WIP.</span></span>

 ![将 Microsoft Edge 添加为 WIP 应用的 Intune 对话框](./media/microsoft-edge-security-windows-information-protection/microsoft-edge-wip-exemption.png)

<span data-ttu-id="2f8f6-180">如果没有使用 Microsoft Intune，请下载并应用 [WIP 企业 AppLocker 策略](https://download.microsoft.com/download/8/9/9/8995d820-065c-4ab1-aa2a-9d6dc0cd7ffa/MsEdge%20-%20WIP%20Enterprise%20AppLocker%20Policy%20Files.zip)文件中的策略更新。</span><span class="sxs-lookup"><span data-stu-id="2f8f6-180">If you're not using Microsoft Intune, download and apply the policy update in the [WIP Enterprise AppLocker Policy](https://download.microsoft.com/download/8/9/9/8995d820-065c-4ab1-aa2a-9d6dc0cd7ffa/MsEdge%20-%20WIP%20Enterprise%20AppLocker%20Policy%20Files.zip) file.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f8f6-181">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f8f6-181">See also</span></span>

- [<span data-ttu-id="2f8f6-182">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="2f8f6-182">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise) 
- [<span data-ttu-id="2f8f6-183">使用 Windows 信息保护来保护企业数据</span><span class="sxs-lookup"><span data-stu-id="2f8f6-183">Protect enterprise data using Windows Information Protection</span></span>](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)