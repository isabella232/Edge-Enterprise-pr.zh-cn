---
title: 为用户自动启用密码监视器
ms.author: supalsul
author: dan-wesley
manager: tulasim
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 为用户自动启用密码监视器
ms.openlocfilehash: 76fc4f0c0ce4bb59ba6b2d4d8a82b61592585918
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11643088"
---
# <a name="password-monitor-auto-enabled-for-users"></a><span data-ttu-id="1dd05-103">为用户自动启用密码监视器</span><span class="sxs-lookup"><span data-stu-id="1dd05-103">Password Monitor auto-enabled for users</span></span>

<span data-ttu-id="1dd05-104">本文介绍了如何为选定用户打开 Microsoft Edge 中的密码监视器，并给予管理员控制如何启用监视的步骤。</span><span class="sxs-lookup"><span data-stu-id="1dd05-104">This article describes how Password Monitor in Microsoft Edge will be turned on for select users and gives admins the steps to control how monitoring is enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="1dd05-105">本文适用于 Microsoft Edge 版本 88 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="1dd05-105">This article applies to Microsoft Edge version 88 or later.</span></span>

## <a name="introduction-benefits-and-availability"></a><span data-ttu-id="1dd05-106">简介、优势和可用性</span><span class="sxs-lookup"><span data-stu-id="1dd05-106">Introduction, benefits, and availability</span></span>

<span data-ttu-id="1dd05-107">密码监视器通过通知 Microsoft Edge 用户在联机泄露中是否找到其任何密码来帮助其保护其联机帐户。</span><span class="sxs-lookup"><span data-stu-id="1dd05-107">Password Monitor helps Microsoft Edge users protect their online accounts by informing them if any of their passwords have been found in an online leak.</span></span> <span data-ttu-id="1dd05-108">当错误参与者从第三方应用或网站窃取数据时，将发生联机泄露或数据泄露。</span><span class="sxs-lookup"><span data-stu-id="1dd05-108">Online leaks or data breaches happen when bad actors steal data from third-party apps or websites.</span></span> <span data-ttu-id="1dd05-109">若要了解更多信息，请参阅 Microsoft 研究博客上的[密码监视器：保护 Microsoft Edge 中的密码](https://www.microsoft.com/research/blog/password-monitor-safeguarding-passwords-in-microsoft-edge/)一文。</span><span class="sxs-lookup"><span data-stu-id="1dd05-109">To learn more, see the [Password Monitor: Safeguarding passwords in Microsoft Edge](https://www.microsoft.com/research/blog/password-monitor-safeguarding-passwords-in-microsoft-edge/)  paper on the Microsoft Research Blog.</span></span>

### <a name="benefits"></a><span data-ttu-id="1dd05-110">优势</span><span class="sxs-lookup"><span data-stu-id="1dd05-110">Benefits</span></span>

<span data-ttu-id="1dd05-111">鉴于这些联机攻击的频率和范围，每个人必须拥有此类保护。</span><span class="sxs-lookup"><span data-stu-id="1dd05-111">Given the frequency and scope of these online attacks having this kind of protection has become necessary for everyone.</span></span> <span data-ttu-id="1dd05-112">Microsoft Edge 具有针对已知泄露的密码安全检查用户保存的密码的内置功能，如果找到匹配项，则发出警报。</span><span class="sxs-lookup"><span data-stu-id="1dd05-112">Microsoft Edge has the built-in ability to securely check a user's saved passwords against passwords that are known to be compromised and alerts them if a match is found.</span></span>  

### <a name="availability"></a><span data-ttu-id="1dd05-113">可用性</span><span class="sxs-lookup"><span data-stu-id="1dd05-113">Availability</span></span>

<span data-ttu-id="1dd05-114">从 1 月 21 日起，稳定渠道版本 88 中提供了密码监视器。</span><span class="sxs-lookup"><span data-stu-id="1dd05-114">Password Monitor is available in Stable Channel version 88 starting 1/21.</span></span> <span data-ttu-id="1dd05-115">新版本的推出将逐步进行，可能需要几周时间。更新后用户可以在“**设置**” > “**个人资料**” > “**密码**”页面中看到以下消息和控件。</span><span class="sxs-lookup"><span data-stu-id="1dd05-115">The rollout will be gradual and it could take a few weeks before you will see the following message and control in your **Settings** > **Profile** > **Password** page.</span></span>

:::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-enable-option.png" alt-text="启用密码监视器的选项":::

## <a name="configure-group-policy-for-password-monitor"></a><span data-ttu-id="1dd05-117">为密码监视器配置组策略</span><span class="sxs-lookup"><span data-stu-id="1dd05-117">Configure group policy for Password Monitor</span></span>

<span data-ttu-id="1dd05-118">此功能通过 [PasswordMonitorAllowed](./microsoft-edge-policies.md#passwordmonitorallowed) 组策略控制。</span><span class="sxs-lookup"><span data-stu-id="1dd05-118">This feature is controlled via the [PasswordMonitorAllowed](./microsoft-edge-policies.md#passwordmonitorallowed) group policy.</span></span>

<span data-ttu-id="1dd05-119">启用策略后，用户仍然需要同意才能启用该功能。</span><span class="sxs-lookup"><span data-stu-id="1dd05-119">After the policy is enabled, users still need to provide consent to turn on the feature.</span></span> <span data-ttu-id="1dd05-120">需要获得同意，因为该功能包含用户的敏感数据和个人数据（密码）。</span><span class="sxs-lookup"><span data-stu-id="1dd05-120">Consent is required because the feature contains user's sensitive and personal data (passwords).</span></span> <span data-ttu-id="1dd05-121">如果使用组策略禁用此功能，则用户不能覆盖此设置。</span><span class="sxs-lookup"><span data-stu-id="1dd05-121">If the feature is disabled using group policy, users can't override this setting.</span></span>  

## <a name="enabling-password-monitor-for-users"></a><span data-ttu-id="1dd05-122">为用户启用密码监视器</span><span class="sxs-lookup"><span data-stu-id="1dd05-122">Enabling Password Monitor for users</span></span>

<span data-ttu-id="1dd05-123">启用密码监视器策略后，用户可以通过多种方式使用此功能。</span><span class="sxs-lookup"><span data-stu-id="1dd05-123">After the password monitor policy is enabled, there are different ways this feature is made available to users.</span></span>

- <span data-ttu-id="1dd05-124">自动启用。</span><span class="sxs-lookup"><span data-stu-id="1dd05-124">Auto-enablement.</span></span> <span data-ttu-id="1dd05-125">使用工作帐户（Active Directory 或 Azure Active Directory）登陆并同步密码的用户会自动启用此功能。</span><span class="sxs-lookup"><span data-stu-id="1dd05-125">Users that are signed-in using their work account (Active Directory or Azure Active Directory) and syncing their passwords will be auto-enabled for this feature.</span></span> <span data-ttu-id="1dd05-126">用户会看到下一张屏幕截图所示的通知，表示他们已打开该功能。</span><span class="sxs-lookup"><span data-stu-id="1dd05-126">They will  see the notification in the next screenshot informing them that the feature's turned on.</span></span>

  :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-enabled-notice.png" alt-text="启用密码监视器的通知":::

-  <span data-ttu-id="1dd05-128">获得明确同意。</span><span class="sxs-lookup"><span data-stu-id="1dd05-128">Getting explicit consent.</span></span> <span data-ttu-id="1dd05-129">将要求尚未打开密码同步的用户获得打开密码监视器的权限。</span><span class="sxs-lookup"><span data-stu-id="1dd05-129">Users that don’t have Password Sync turned on will be asked for permission to turn on Password Monitor.</span></span> <span data-ttu-id="1dd05-130">发生以下操作时，系统将会提示它们：</span><span class="sxs-lookup"><span data-stu-id="1dd05-130">They will be prompted when the following actions happen:</span></span>
   - <span data-ttu-id="1dd05-131">用户保存新密码时。</span><span class="sxs-lookup"><span data-stu-id="1dd05-131">When a user is saving a new password.</span></span>
 
     :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-save-pw-prompt.png" alt-text="提示保存密码":::

   - <span data-ttu-id="1dd05-133">当用户使用保存的密码登录浏览器时。</span><span class="sxs-lookup"><span data-stu-id="1dd05-133">When a user has signed-in to the browser using a saved password.</span></span>
  
     :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-after-signin.png" alt-text="登录后确认提示":::
   
- <span data-ttu-id="1dd05-135">直接激活。</span><span class="sxs-lookup"><span data-stu-id="1dd05-135">Direct activation.</span></span> <span data-ttu-id="1dd05-136">用户可以随时转到“**设置**” > “**密码**”来打开或关闭此功能。</span><span class="sxs-lookup"><span data-stu-id="1dd05-136">Users can go to **Settings** > **Passwords** anytime and turn the feature On or Off.</span></span>

## <a name="user-scenarios-with-password-monitor-auto-enabled"></a><span data-ttu-id="1dd05-137">自动启用密码监视器的用户方案</span><span class="sxs-lookup"><span data-stu-id="1dd05-137">User scenarios with Password Monitor auto-enabled</span></span>

<span data-ttu-id="1dd05-138">下表显示了自动启用密码监视器的方案及其在用户设备上执行的方式。</span><span class="sxs-lookup"><span data-stu-id="1dd05-138">The following table shows scenarios where Password Monitor is auto-enabled and how it will work on user devices.</span></span>

| <span data-ttu-id="1dd05-139">方案</span><span class="sxs-lookup"><span data-stu-id="1dd05-139">Scenario</span></span> | <span data-ttu-id="1dd05-140">基本条件</span><span class="sxs-lookup"><span data-stu-id="1dd05-140">Base conditions</span></span> | <span data-ttu-id="1dd05-141">影响</span><span class="sxs-lookup"><span data-stu-id="1dd05-141">Impact</span></span> |
|--|--|--|
| <span data-ttu-id="1dd05-142">1 同步打开</span><span class="sxs-lookup"><span data-stu-id="1dd05-142">1 with Sync on</span></span> | <span data-ttu-id="1dd05-143">同步打开</span><span class="sxs-lookup"><span data-stu-id="1dd05-143">Sync ON</span></span><br><span data-ttu-id="1dd05-144">以前启用了功能：否</span><span class="sxs-lookup"><span data-stu-id="1dd05-144">Feature enabled previously: No</span></span><br><span data-ttu-id="1dd05-145">对同意 UI 的响应：无</span><span class="sxs-lookup"><span data-stu-id="1dd05-145">Response to Consent UI: None</span></span> | <span data-ttu-id="1dd05-146">默认情况下启用功能，浏览器启动 2 分钟后会显示通知气泡。</span><span class="sxs-lookup"><span data-stu-id="1dd05-146">Feature enabled by default and a notice bubble is shown 2 min after browser starts.</span></span><br><span data-ttu-id="1dd05-147">- 如果在此之后关闭同步，则禁用该功能。</span><span class="sxs-lookup"><span data-stu-id="1dd05-147">- If sync is turned off after that, the feature is disabled.</span></span><br><span data-ttu-id="1dd05-148">- 在更改同步之前关闭功能，同步将不再影响功能。</span><span class="sxs-lookup"><span data-stu-id="1dd05-148">-  Feature turned off before altering sync, sync will no longer affect the feature.</span></span>   |
| <span data-ttu-id="1dd05-149">2 打开同步</span><span class="sxs-lookup"><span data-stu-id="1dd05-149">2 with Sync on</span></span> | <span data-ttu-id="1dd05-150">同步打开</span><span class="sxs-lookup"><span data-stu-id="1dd05-150">Sync ON</span></span><br><span data-ttu-id="1dd05-151">以前启用了功能：是</span><span class="sxs-lookup"><span data-stu-id="1dd05-151">Feature enabled previously: Yes</span></span><br><span data-ttu-id="1dd05-152">对同意 UI 的响应：无</span><span class="sxs-lookup"><span data-stu-id="1dd05-152">Response to Consent UI: None</span></span> | <span data-ttu-id="1dd05-153">功能与用户选择相同。</span><span class="sxs-lookup"><span data-stu-id="1dd05-153">Feature stays the same as user choice.</span></span>  <span data-ttu-id="1dd05-154">请注意，气泡不会显示，并且同步更改不会影响功能值。</span><span class="sxs-lookup"><span data-stu-id="1dd05-154">Notice bubble isn't shown and there's no affect of sync change on feature value.</span></span>|
| <span data-ttu-id="1dd05-155">3 同步关闭</span><span class="sxs-lookup"><span data-stu-id="1dd05-155">3 with Sync off</span></span> | <span data-ttu-id="1dd05-156">同步关闭</span><span class="sxs-lookup"><span data-stu-id="1dd05-156">Sync Off</span></span><br><span data-ttu-id="1dd05-157">以前启用了功能：否</span><span class="sxs-lookup"><span data-stu-id="1dd05-157">Feature enabled previously: No</span></span><br><span data-ttu-id="1dd05-158">对同意 UI 的响应：无</span><span class="sxs-lookup"><span data-stu-id="1dd05-158">Response to Consent UI: None</span></span> | <span data-ttu-id="1dd05-159">同步将关闭，该功能将保持禁用状态</span><span class="sxs-lookup"><span data-stu-id="1dd05-159">Sync will be off and the feature will stay disabled</span></span><br><span data-ttu-id="1dd05-160">- 此后的任何时间点，如果用户在不更改功能的情况下打开同步：启用该功能，并且在同步打开 2 分钟后显示自动启用通知。</span><span class="sxs-lookup"><span data-stu-id="1dd05-160">- At any point after that if user turns the sync on without altering the feature: the feature is enabled and auto-enablement notification is shown 2 minutes after Sync is turned on.</span></span> <br> <span data-ttu-id="1dd05-161">- 如果再次关闭同步，则禁用该功能</span><span class="sxs-lookup"><span data-stu-id="1dd05-161">- If sync is turned off again, the  feature is disabled</span></span> <br><span data-ttu-id="1dd05-162">- 如果在打开同步之前更改了该功能，同步将不再影响密码监视器。</span><span class="sxs-lookup"><span data-stu-id="1dd05-162">- If the feature is changed before turning on sync, sync will no longer affect Password Monitor.</span></span>  |  
| <span data-ttu-id="1dd05-163">4 同步关闭</span><span class="sxs-lookup"><span data-stu-id="1dd05-163">4 with Sync off</span></span> | <span data-ttu-id="1dd05-164">同步关闭</span><span class="sxs-lookup"><span data-stu-id="1dd05-164">Sync OFF</span></span><br><span data-ttu-id="1dd05-165">以前启用了功能：是</span><span class="sxs-lookup"><span data-stu-id="1dd05-165">Feature enabled previously: Yes</span></span><br><span data-ttu-id="1dd05-166">对同意 UI 的响应：无</span><span class="sxs-lookup"><span data-stu-id="1dd05-166">Response to Consent UI: None</span></span> | <span data-ttu-id="1dd05-167">功能与用户选择相同，通知气泡不会显示，且同步更改对功能值没有影响。</span><span class="sxs-lookup"><span data-stu-id="1dd05-167">Feature stays the same as user choice, notice bubble isn't shown, and there's no effect of sync change on the feature value.</span></span>  |

<span data-ttu-id="1dd05-168">此外，如果用户使用通过以下任一策略限制的工作帐户登录，将不会为用户自动启用该功能：</span><span class="sxs-lookup"><span data-stu-id="1dd05-168">In addition, if a user is signed-in using a work account that is restricted via policies for any of the following, the feature will NOT be auto-enabled for them:</span></span>

- <span data-ttu-id="1dd05-169">密码监视器已禁用</span><span class="sxs-lookup"><span data-stu-id="1dd05-169">Password Monitor is disabled</span></span>  
- <span data-ttu-id="1dd05-170">密码同步已禁用</span><span class="sxs-lookup"><span data-stu-id="1dd05-170">Password Sync is disabled</span></span>
- <span data-ttu-id="1dd05-171">与 Microsoft 服务器共享数据已禁用</span><span class="sxs-lookup"><span data-stu-id="1dd05-171">Sharing of data with Microsoft servers is disabled</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="1dd05-172">常见问题</span><span class="sxs-lookup"><span data-stu-id="1dd05-172">Frequently Asked Questions</span></span>

### <a name="how-can-password-monitor-be-disabled-for-my-organization"></a><span data-ttu-id="1dd05-173">如何为组织禁用密码监视器？</span><span class="sxs-lookup"><span data-stu-id="1dd05-173">How can Password Monitor be disabled for my organization?</span></span>

<span data-ttu-id="1dd05-174">您可以按以下方法为组织禁用密码监视器：</span><span class="sxs-lookup"><span data-stu-id="1dd05-174">You can disable Password Monitor for your organization by:</span></span>
- <span data-ttu-id="1dd05-175">使用 PasswordMonitorAllowed 组策略。</span><span class="sxs-lookup"><span data-stu-id="1dd05-175">Using the PasswordMonitorAllowed group policy.</span></span>
- <span data-ttu-id="1dd05-176">阻止同步数据并发送到 Microsoft 服务器。</span><span class="sxs-lookup"><span data-stu-id="1dd05-176">Stopping data from being synchronized and sent to Microsoft servers.</span></span>

  > [!NOTE]
  > <span data-ttu-id="1dd05-177">密码监视器即使已禁用密码同步，也可以正常工作，只要用户明确同意打开该功能或通过“设置”自行打开该功能。</span><span class="sxs-lookup"><span data-stu-id="1dd05-177">Password Monitor can work even if Password Sync is disabled, as long as the user has given explicit consent to turn the feature On or have turned it on themselves via Settings.</span></span>

### <a name="what-happens-if-a-user-for-whom-the-feature-has-been-auto-enabled-turns-password-monitor-off-via-settings"></a><span data-ttu-id="1dd05-178">如果已自动启用该功能的用户通过“设置”关闭密码监视器，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="1dd05-178">What happens if a user for whom the feature has been auto-enabled, turns Password Monitor off via Settings?</span></span>

<span data-ttu-id="1dd05-179">尊重用户设置，为用户禁用该功能。</span><span class="sxs-lookup"><span data-stu-id="1dd05-179">The user setting is honored and the feature will remain disabled for that user.</span></span> <span data-ttu-id="1dd05-180">但是，如果以前从未响应过同意提示，可能会再次显示同意对话框。</span><span class="sxs-lookup"><span data-stu-id="1dd05-180">However, they might be shown a consent dialog again in case they've never previously responded to the consent prompt.</span></span>

## <a name="see-also"></a><span data-ttu-id="1dd05-181">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1dd05-181">See also</span></span>

- [<span data-ttu-id="1dd05-182">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="1dd05-182">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)