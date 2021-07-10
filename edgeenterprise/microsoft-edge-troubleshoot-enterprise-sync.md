---
title: 诊断和修复 Microsoft Edge 同步问题
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 管理员可用于排查和修复常见企业同步问题的指南和工具
ms.openlocfilehash: 0aca8c98492aead0673b5738aa5dba85c3a34314
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642228"
---
# <a name="diagnose-and-fix-microsoft-edge-sync-issues"></a><span data-ttu-id="7a5d8-103">诊断和修复 Microsoft Edge 同步问题</span><span class="sxs-lookup"><span data-stu-id="7a5d8-103">Diagnose and fix Microsoft Edge sync issues</span></span>

<span data-ttu-id="7a5d8-104">本文针对 Azure Active Directory (Azure AD) 环境中最常遇到的同步问题提供疑难解答指南。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-104">This article provides troubleshooting guidance for the most commonly encountered sync issues in an Azure Active Directory (Azure AD) environment.</span></span> <span data-ttu-id="7a5d8-105">还包括收集故障排除同步问题所需日志的推荐工具。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-105">It also includes the recommended tools for gathering the logs needed for troubleshooting a sync issue.</span></span>

<span data-ttu-id="7a5d8-106">如果用户跨设备同步浏览器数据出现问题，可以尝试[重置同步](edge-learnmore-reset-data-in-cloud.md)。如果此操作不起作用，管理员或支持人员可以使用以下指南修复同步问题。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-106">If a user is experiencing an issue syncing browser data across their devices they can try [resetting sync](edge-learnmore-reset-data-in-cloud.md). If this doesn't work, admins or support staff can use the following guidance to fix a sync issue.</span></span>

> [!NOTE]
> <span data-ttu-id="7a5d8-107">除非另有说明，否则本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-107">Applies to Microsoft Edge version 77 or later unless otherwise noted.</span></span>

## <a name="identity-issues-versus-sync-issues"></a><span data-ttu-id="7a5d8-108">标识问题与同步问题</span><span class="sxs-lookup"><span data-stu-id="7a5d8-108">Identity issues versus sync issues</span></span>

<span data-ttu-id="7a5d8-109">在开始之前，了解标识问题和同步问题之间的区别是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-109">Before you begin it's important to understand the difference between identity issues and sync issues.</span></span> <span data-ttu-id="7a5d8-110">在浏览器中维护用户标识的一个常见用例是支持同步。因此，标识问题经常与同步问题混淆。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-110">A popular use case for maintaining user identity in the browser is to support sync. For this reason, identity issues are frequently confused with sync issues.</span></span> <span data-ttu-id="7a5d8-111">在开始排除同步故障之前，请了解标识和同步问题的区别。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-111">Understand the difference between identity and sync issue before you start troubleshooting sync.</span></span>

<span data-ttu-id="7a5d8-112">在将某个问题视为同步问题之前，请检查用户是否已使用有效帐户登录浏览器。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-112">Before you treat an issue as a sync issue, check to see if the user is signed into the browser with a valid account.</span></span>

<span data-ttu-id="7a5d8-113">下一个屏幕截图显示了标识错误的示例。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-113">The next screenshot shows an example of an identity error.</span></span> <span data-ttu-id="7a5d8-114">错误为“**最后令牌错误，EDGE_AUTH_ERROR: 3, 54, 3ea**”，它位于**凭据**下的 *edge://sync-internals* 中： </span><span class="sxs-lookup"><span data-stu-id="7a5d8-114">The error is "**Last Token Error, EDGE_AUTH_ERROR: 3, 54, 3ea**", which is found in *edge://sync-internals* under **Credentials**:</span></span>

:::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-identity-issue.png" alt-text="最后令牌错误 EDGE_AUTH_ERROR: 3, 54, 3ea":::

## <a name="common-sync-issues"></a><span data-ttu-id="7a5d8-116">常见同步问题</span><span class="sxs-lookup"><span data-stu-id="7a5d8-116">Common sync issues</span></span>

### <a name="issue-cant-access-m365-or-azure-information-protection-subscription"></a><span data-ttu-id="7a5d8-117">问题：无法访问 M365 或 Azure 信息保护订阅</span><span class="sxs-lookup"><span data-stu-id="7a5d8-117">Issue: Can't access M365 or Azure Information Protection subscription</span></span>

<span data-ttu-id="7a5d8-118">你是不是以前拥有的 M365 或 Azure 信息保护 (AIP) 订阅已过期，然后替换成了新订阅？</span><span class="sxs-lookup"><span data-stu-id="7a5d8-118">Do you have a previous M365 or Azure Information Protection (AIP) subscription that expired and then replaced with a new subscription?</span></span> <span data-ttu-id="7a5d8-119">如果是，则租户 ID 已更改，需要重置服务数据。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-119">If so, then the tenant ID has changed and the service data needs to be reset.</span></span> <span data-ttu-id="7a5d8-120">请参阅**遇到密码器错误**问题中有关重置数据的说明。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-120">See the instructions for resetting data in the **Cryptographer error encountered** issue.</span></span>

### <a name="issue-sync-is-not-available-for-this-account"></a><span data-ttu-id="7a5d8-121">问题：“此帐户无法使用同步功能。”</span><span class="sxs-lookup"><span data-stu-id="7a5d8-121">Issue: “Sync is not available for this account.”</span></span>

<span data-ttu-id="7a5d8-122">如果 Azure Active Directory 帐户遇到此错误，或 *edge://sync-internals* 中出现 DISABLED_BY_ADMIN，请按顺序执行下一过程中的步骤，直到问题得到解决。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-122">If this error is encountered for an Azure Active Directory account, or if DISABLED_BY_ADMIN appears in *edge://sync-internals*, follow the steps in the next procedure sequentially until the problem is fixed.</span></span>

> [!NOTE]
> <span data-ttu-id="7a5d8-123">由于此错误的来源通常需要在 Azure Active Directory 租户中更改配置，因此这些故障排除步骤只能由租户管理员执行，而不能由最终用户执行。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-123">Because the source of this error is usually requires a configuration change in an Azure Active Directory tenant, these troubleshooting steps can only performed by a tenant admin and not by end users.</span></span>

1. <span data-ttu-id="7a5d8-124">验证企业租户是否具有受支持的 M365 订阅。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-124">Verify that the enterprise tenant has a supported M365 subscription.</span></span> <span data-ttu-id="7a5d8-125">[此处](/azure/information-protection/activate-office365)提供了可用订阅类型的当前列表。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-125">The current list of available subscription types is [provided here](/azure/information-protection/activate-office365).</span></span> <span data-ttu-id="7a5d8-126">如果租户没有受支持的订阅，他们可以单独购买 Azure 信息保护，也可以升级到受支持的某个订阅。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-126">If the tenant doesn't have a supported subscription, they can either purchase Azure Information Protection separately, or upgrade to one of the supported subscriptions.</span></span>
2. <span data-ttu-id="7a5d8-127">如果具有受支持的订阅，请验证租户是否具有可用的 Azure 信息保护 (AIP)。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-127">If a supported subscription is available, verify that the tenant has Azure Information Protection (AIP) available.</span></span> <span data-ttu-id="7a5d8-128">有关检查 AIP 状态以及在必要时激活 AIP 的说明，请参阅[此处](/azure/information-protection/activate-office365)。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-128">The instructions for checking the AIP status and, if necessary, activating AIP are [here](/azure/information-protection/activate-office365).</span></span>
3. <span data-ttu-id="7a5d8-129">如果步骤 2 显示 AIP 处于活动状态，但仍无法使用同步功能，请启用企业状态漫游 (ESR)。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-129">If step 2 shows that AIP is active but sync still doesn't work, turn on Enterprise State Roaming (ESR).</span></span> <span data-ttu-id="7a5d8-130">有关启用 ESR 的说明，请参阅[此处](/azure/active-directory/devices/enterprise-state-roaming-enable)。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-130">The instructions for enabling ESR are [here](/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span> <span data-ttu-id="7a5d8-131">请注意，无需将 ESR 保持启用状态。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-131">Note that ESR does not need to stay on.</span></span> <span data-ttu-id="7a5d8-132">如果此步骤修复了问题，可以禁用 ESR。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-132">You can turn off ESR if this step fixes the issue.</span></span>
4. <span data-ttu-id="7a5d8-133">确认 Azure 信息保护未通过载入策略确定作用域。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-133">Confirm that Azure Information Protection is not scoped via an onboarding policy.</span></span> <span data-ttu-id="7a5d8-134">可以使用 [Get-AadrmOnboardingControlPolicy](/powershell/module/aadrm/get-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell 小程序查看是否启用了作用域功能。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-134">You can use the [Get-AadrmOnboardingControlPolicy](/powershell/module/aadrm/get-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell applet to see if scoping is enabled.</span></span> <span data-ttu-id="7a5d8-135">接下来的两个示例将展示无作用域配置和作用域为特定安全组的配置。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-135">The next two examples show an unscoped configuration and a configuration scoped to a specific security group.</span></span>

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

   <span data-ttu-id="7a5d8-136">如果启用了作用域功能，则应该将受影响的用户添加到相应作用域的安全组，或者删除该作用域。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-136">If scoping is enabled, the affected user should either be added to the security group for the scope, or the scope should be removed.</span></span> <span data-ttu-id="7a5d8-137">在下面的示例中，载入将 AIP 的作用域设定成了指示的安全组，应该使用 [Set-AadrmOnboardingControlPolicy](/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell 小程序删除作用域功能。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-137">In the example below, onboarding has scoped AIP to the indicated security group and the scoping should be removed with the [Set-AadrmOnboardingControlPolicy](/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell applet.</span></span>

5. <span data-ttu-id="7a5d8-138">确认已在租户中启用 IPCv3Service。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-138">Confirm that the IPCv3Service is turned on in the tenant.</span></span> <span data-ttu-id="7a5d8-139">[Get-AadrmConfiguration](/powershell/module/aadrm/get-aadrmconfiguration?view=azureipps) PowerShell 小程序可显示该服务的状态。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-139">The [Get-AadrmConfiguration](/powershell/module/aadrm/get-aadrmconfiguration?view=azureipps)  PowerShell applet shows the status of the service.</span></span>

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-scoped-cfg-example.png" alt-text="检查是否已启用 IPCv3Service。":::

6. <span data-ttu-id="7a5d8-141">如果未能解决问题，请与 [Microsoft Edge 支持人员](https://www.microsoftedgeinsider.com/support)联系。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-141">If the issue isn't fixed, contact [Microsoft Edge support](https://www.microsoftedgeinsider.com/support).</span></span>

### <a name="issue-stuck-at-setting-up-sync-or-couldnt-connect-to-the-sync-server-retrying"></a><span data-ttu-id="7a5d8-142">问题：卡在“正在设置同步...”或“无法连接到同步服务器。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-142">Issue: Stuck at "Setting up sync..." or “Couldn’t connect to the sync server.</span></span> <span data-ttu-id="7a5d8-143">正在重试…”环节</span><span class="sxs-lookup"><span data-stu-id="7a5d8-143">Retrying…”</span></span>

1. <span data-ttu-id="7a5d8-144">尝试注销，然后再登录。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-144">Try to sign out and then sign in.</span></span>
2. <span data-ttu-id="7a5d8-145">转到 *edge://sync-internals*。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-145">Go to *edge://sync-internals*.</span></span> <span data-ttu-id="7a5d8-146">如果“**Type info**”部分下存在以下错误，请跳到以下问题：**遇到密码器错误**。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-146">If under the "**Type info**" section the following error is present, then  skip to the following issue, **Cryptographer error encountered**.</span></span>

   `"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered"`

3. <span data-ttu-id="7a5d8-147">尝试 ping 服务器终结点。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-147">Try pinging the server endpoint.</span></span> <span data-ttu-id="7a5d8-148">*edge://sync-internals* 中提供了客户端的服务器终结点。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-148">The server endpoint for a client is available in *edge://sync-internals*.</span></span> <span data-ttu-id="7a5d8-149">接下来的屏幕截图显示了“**Environment Info**”下的终结点信息。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-149">The next screenshot shows endpoint information under **Environment Info**.</span></span>

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-endpoint-info.png" alt-text="终结点信息":::

4. <span data-ttu-id="7a5d8-151">如果服务器终结点为空，或者无法对服务器执行 ping 操作且环境中存在防火墙，请确认客户端计算机可以使用必要的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-151">If the server endpoint is empty, or if server cannot be pinged and a firewall is present in the environment, confirm that the necessary service endpoints are available to the client computer.</span></span>

   - <span data-ttu-id="7a5d8-152">Microsoft Edge 同步服务终结点：</span><span class="sxs-lookup"><span data-stu-id="7a5d8-152">Microsoft Edge sync service endpoints:</span></span>
     - [https://edge-enterprise.activity.windows.com](https://edge-enterprise.activity.windows.com)
     - [https://edge.activity.windows.com](https://edge.activity.windows.com)
    - <span data-ttu-id="7a5d8-153">Azure 信息保护终结点：</span><span class="sxs-lookup"><span data-stu-id="7a5d8-153">Azure Information Protection endpoints:</span></span>
      - <span data-ttu-id="7a5d8-154">[https://api.aadrm.com](https://api.aadrm.com)（适用于大多数租户）</span><span class="sxs-lookup"><span data-stu-id="7a5d8-154">[https://api.aadrm.com](https://api.aadrm.com) (for most tenants)</span></span>
      - <span data-ttu-id="7a5d8-155">[https://api.aadrm.de](https://api.aadrm.de)（适用于德国的租户）</span><span class="sxs-lookup"><span data-stu-id="7a5d8-155">[https://api.aadrm.de](https://api.aadrm.de) (for tenants in Germany)</span></span>
      - <span data-ttu-id="7a5d8-156">[https://api.aadrm.cn](https://api.aadrm.cn)（适用于中国的租户）</span><span class="sxs-lookup"><span data-stu-id="7a5d8-156">[https://api.aadrm.cn](https://api.aadrm.cn) (for tenants in China)</span></span>
   - <span data-ttu-id="7a5d8-157">[Windows 通知服务终结点](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-157">[Windows Notification Service endpoints](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config).</span></span>

5. <span data-ttu-id="7a5d8-158">如果仍未能解决问题，请与 [Microsoft Edge 支持人员](https://www.microsoftedgeinsider.com/support)联系。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-158">If the issue still isn't fixed, contact [Microsoft Edge support](https://www.microsoftedgeinsider.com/support).</span></span>

### <a name="issue-cryptographer-error-encountered"></a><span data-ttu-id="7a5d8-159">问题：遇到密码器错误</span><span class="sxs-lookup"><span data-stu-id="7a5d8-159">Issue: Cryptographer error encountered</span></span>

<span data-ttu-id="7a5d8-160">此错误显示在 *edge://sync-internals* 中的“**类型信息**”下，它可能意味着需要重置用户的服务器端数据。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-160">This error is visible under **Type info** in *edge://sync-internals* and may mean that the user's service side data needs to be reset.</span></span> <span data-ttu-id="7a5d8-161">以下示例显示加密错误消息：</span><span class="sxs-lookup"><span data-stu-id="7a5d8-161">The following example shows a cryptography error message:</span></span>
<br><span data-ttu-id="7a5d8-162">"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered".</span><span class="sxs-lookup"><span data-stu-id="7a5d8-162">"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered".</span></span>

1. <span data-ttu-id="7a5d8-163">重新启动 Microsoft Edge 并导航到 *edge://sync-internals*，检查“**AAD 账户密钥状态**”部分</span><span class="sxs-lookup"><span data-stu-id="7a5d8-163">Restart Microsoft Edge and navigate to *edge://sync-internals* and check the “**AAD Account Key Status**” section</span></span>
   - <span data-ttu-id="7a5d8-164">“Last MIP Result”中为“Success”：该密码器错误意味着服务器数据在加密时使用的可能是丢失的密钥。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-164">"Success" in "Last MIP Result": the cryptographer error means server data might be encrypted with a lost key.</span></span> <span data-ttu-id="7a5d8-165">需要重置数据才能恢复同步。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-165">Data reset is needed to resume sync.</span></span>
   - <span data-ttu-id="7a5d8-166">“Last MIP Result”中为“No permissions”：这可能是由 Azure AD 更改或租户订阅更改引起的。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-166">"No permissions" in "Last MIP Result": It is possibly caused by an Azure AD change or tenant subscription changes.</span></span> <span data-ttu-id="7a5d8-167">需要重置数据才能恢复同步。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-167">Data reset is needed to resume sync.</span></span>
   - <span data-ttu-id="7a5d8-168">其他错误可能意味着服务器配置问题。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-168">Other errors may mean server configuration issues.</span></span>
2. <span data-ttu-id="7a5d8-169">如果需要重置数据，请参阅[重置云中的 Microsoft Edge 数据](edge-learnmore-reset-data-in-cloud.md)。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-169">If data reset is needed, see [Reset Microsoft Edge data in the cloud](edge-learnmore-reset-data-in-cloud.md).</span></span>

### <a name="issue-sync-has-been-turned-off-by-your-administrator"></a><span data-ttu-id="7a5d8-170">问题：“管理员已禁用同步。”</span><span class="sxs-lookup"><span data-stu-id="7a5d8-170">Issue: “Sync has been turned off by your administrator.”</span></span>

<span data-ttu-id="7a5d8-171">确保未设置 [SyncDisabled 策略](./microsoft-edge-policies.md#syncdisabled)。</span><span class="sxs-lookup"><span data-stu-id="7a5d8-171">Make sure that the [SyncDisabled policy](./microsoft-edge-policies.md#syncdisabled)  is not set.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a5d8-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a5d8-172">See also</span></span>

- [<span data-ttu-id="7a5d8-173">Microsoft Edge 企业同步</span><span class="sxs-lookup"><span data-stu-id="7a5d8-173">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)
- [<span data-ttu-id="7a5d8-174">Microsoft Edge 和企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="7a5d8-174">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="7a5d8-175">Microsoft Edge 企业版登录页面</span><span class="sxs-lookup"><span data-stu-id="7a5d8-175">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)