---
title: 配置 Microsoft Edge 企业同步
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 03/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 用于配置 Microsoft Edge 以同步收藏夹、密码和其他浏览器数据的管理员和用户选项。
ms.openlocfilehash: 99edc97bd5f4bab7bf421e0d15e512c5f6f76cc0
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617752"
---
# <a name="configure-microsoft-edge-enterprise-sync"></a><span data-ttu-id="a9305-103">配置 Microsoft Edge 企业同步</span><span class="sxs-lookup"><span data-stu-id="a9305-103">Configure Microsoft Edge enterprise sync</span></span>

<span data-ttu-id="a9305-104">本文介绍管理员如何将 Microsoft Edge 配置为跨所有已登录设备同步用户收藏夹、密码、其他浏览器数据。如果你不是管理员，请通过本文了解如何跨设备登录和同步 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="a9305-104">This article explains how admins can configure Microsoft Edge to sync user favorites, passwords, and other browser data across all signed-in devices.If you are not an admin, please visit this article for how to sign-in and sync Microsoft Edge across devices.</span></span> <span data-ttu-id="a9305-105">[登录以在设备之间同步 Microsoft Edge](https://support.microsoft.com/microsoft-edge/sign-in-to-sync-microsoft-edge-across-devices-e6ffa79b-ed52-aa32-47e2-5d5597fe4674)。</span><span class="sxs-lookup"><span data-stu-id="a9305-105">[Sign in to sync Microsoft Edge across devices](https://support.microsoft.com/microsoft-edge/sign-in-to-sync-microsoft-edge-across-devices-e6ffa79b-ed52-aa32-47e2-5d5597fe4674).</span></span>

> [!NOTE]
> <span data-ttu-id="a9305-106">除非另有说明，否则本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a9305-106">Applies to Microsoft Edge version 77 or later unless otherwise noted.</span></span>

## <a name="overview"></a><span data-ttu-id="a9305-107">概述</span><span class="sxs-lookup"><span data-stu-id="a9305-107">Overview</span></span>

<span data-ttu-id="a9305-108">通过 Microsoft Edge 同步，用户可以访问他们所有已登录设备上的浏览数据。</span><span class="sxs-lookup"><span data-stu-id="a9305-108">Microsoft Edge sync enables users to access their browsing data across all their signed-in devices.</span></span> <span data-ttu-id="a9305-109">同步支持的数据包括：</span><span class="sxs-lookup"><span data-stu-id="a9305-109">The data supported by sync includes:</span></span>

- <span data-ttu-id="a9305-110">收藏夹</span><span class="sxs-lookup"><span data-stu-id="a9305-110">Favorites</span></span>
- <span data-ttu-id="a9305-111">密码</span><span class="sxs-lookup"><span data-stu-id="a9305-111">Passwords</span></span>
- <span data-ttu-id="a9305-112">地址等（表单填写）</span><span class="sxs-lookup"><span data-stu-id="a9305-112">Addresses and more (form-fill)</span></span>
- <span data-ttu-id="a9305-113">收藏</span><span class="sxs-lookup"><span data-stu-id="a9305-113">Collections</span></span>
- <span data-ttu-id="a9305-114">“设置”</span><span class="sxs-lookup"><span data-stu-id="a9305-114">Settings</span></span>
- <span data-ttu-id="a9305-115">扩展</span><span class="sxs-lookup"><span data-stu-id="a9305-115">Extension</span></span>
- <span data-ttu-id="a9305-116">打开选项卡（在 Microsoft Edge 版本 88 中可用）</span><span class="sxs-lookup"><span data-stu-id="a9305-116">Open tabs (available in Microsoft Edge version 88)</span></span>
- <span data-ttu-id="a9305-117">历史记录（在 Microsoft Edge 版本 88 中可用）</span><span class="sxs-lookup"><span data-stu-id="a9305-117">History (available in Microsoft Edge version 88)</span></span>

<span data-ttu-id="a9305-118">用户同意后即可启用同步功能，并且用户可以针对上面列出的每种数据类型打开或关闭同步功能。</span><span class="sxs-lookup"><span data-stu-id="a9305-118">Sync functionality is enabled via user consent and users can turn sync on or off for each of the data types listed above.</span></span> <span data-ttu-id="a9305-119">如果用户遇到同步问题，他们需要依次选择“**设置**” > “**配置文件**” > “**重置同步**”来重置同步。</span><span class="sxs-lookup"><span data-stu-id="a9305-119">If a user is experiencing a sync issue they might need to reset sync in **Settings** > **Profiles** > **Reset sync**.</span></span>

> [!NOTE]
> <span data-ttu-id="a9305-120">将上载其他设备连接和配置数据（如设备名称、品牌和型号），以支持同步功能。</span><span class="sxs-lookup"><span data-stu-id="a9305-120">Additional device connectivity and configuration data (such as device name, make and model) is uploaded to support sync functionality.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a9305-121">必备条件</span><span class="sxs-lookup"><span data-stu-id="a9305-121">Prerequisites</span></span>

<span data-ttu-id="a9305-122">适用于 Azure Active Directory (Azure AD) 帐户的 Microsoft Edge 同步功能可供以下任何订阅使用：</span><span class="sxs-lookup"><span data-stu-id="a9305-122">Microsoft Edge sync for Azure Active Directory (Azure AD) accounts is available for any of the following subscriptions:</span></span>

- <span data-ttu-id="a9305-123">Azure AD Premium（P1 或 P2）</span><span class="sxs-lookup"><span data-stu-id="a9305-123">Azure AD Premium (P1 or P2)</span></span>
- <span data-ttu-id="a9305-124">M365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="a9305-124">M365 Business Premium</span></span>
- <span data-ttu-id="a9305-125">Office 365 E1 及更高版本</span><span class="sxs-lookup"><span data-stu-id="a9305-125">Office 365 E1 and above</span></span>
- <span data-ttu-id="a9305-126">Azure 信息保护 (AIP)（P1 或 P2）</span><span class="sxs-lookup"><span data-stu-id="a9305-126">Azure Information Protection (AIP) (P1 or P2)</span></span>
- <span data-ttu-id="a9305-127">所有 EDU 订阅（Microsoft 教育应用版（学生）或 Microsoft 教育应用版（教职员工）、Exchange Online 学生版或教职员工版、O365 A1 或更高版本、M365 A1 或更高版本，或者适用于学生或教职员的 Azure 信息保护 P1 或 P2）</span><span class="sxs-lookup"><span data-stu-id="a9305-127">All EDU subscriptions (Microsoft Apps for Students or Faculty, Exchange Online for Students or Faculty, O365 A1 or above, M365 A1 or above, or Azure Information Protection P1 or P2 for Students or Faculty)</span></span>

## <a name="sync-group-policies"></a><span data-ttu-id="a9305-128">同步组策略</span><span class="sxs-lookup"><span data-stu-id="a9305-128">Sync group policies</span></span>

<span data-ttu-id="a9305-129">管理员可以使用以下组策略配置和管理 Microsoft Edge 同步：</span><span class="sxs-lookup"><span data-stu-id="a9305-129">Admins can use the following group policies to configure and manage Microsoft Edge sync:</span></span>

- <span data-ttu-id="a9305-130">[SyncDisabled](./microsoft-edge-policies.md#syncdisabled)：完全禁用同步。</span><span class="sxs-lookup"><span data-stu-id="a9305-130">[SyncDisabled](./microsoft-edge-policies.md#syncdisabled): Disables sync completely.</span></span>
- <span data-ttu-id="a9305-131">[SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled)：禁止保存浏览历史记录和同步。此策略还将禁用打开选项卡同步。</span><span class="sxs-lookup"><span data-stu-id="a9305-131">[SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled): Disables saving browsing history and sync. This policy also disables open-tabs sync.</span></span>
- <span data-ttu-id="a9305-132">[AllowDeletingBrowserHistory](./microsoft-edge-policies.md#allowdeletingbrowserhistory)：当此策略设置为禁用时，还将禁用历史记录同步。</span><span class="sxs-lookup"><span data-stu-id="a9305-132">[AllowDeletingBrowserHistory](./microsoft-edge-policies.md#allowdeletingbrowserhistory): When this policy is set to disabled, history sync will also be disabled.</span></span>
- <span data-ttu-id="a9305-133">[SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled)：配置从同步中排除的类型列表。</span><span class="sxs-lookup"><span data-stu-id="a9305-133">[SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled): Configure the list of types that are excluded from synchronization.</span></span>
- <span data-ttu-id="a9305-134">[RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled)：允许 Active Directory (AD) 配置文件使用本地存储。</span><span class="sxs-lookup"><span data-stu-id="a9305-134">[RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled): Allow Active Directory (AD) profiles to use on-premises storage.</span></span> <span data-ttu-id="a9305-135">有关更多信息，请参阅 [Active Directory (AD) 用户的本地同步](./microsoft-edge-on-premises-sync.md)。</span><span class="sxs-lookup"><span data-stu-id="a9305-135">For more information, see [On-premises sync for Active Directory (AD) users](./microsoft-edge-on-premises-sync.md).</span></span>
- <span data-ttu-id="a9305-136">[ForceSync：](/deployedge/microsoft-edge-policies#forcesync)默认启用同步，无需用户同意。</span><span class="sxs-lookup"><span data-stu-id="a9305-136">[ForceSync](/deployedge/microsoft-edge-policies#forcesync): Turn on sync by default and do not require user consent to sync.</span></span>  

## <a name="configure-microsoft-edge-sync"></a><span data-ttu-id="a9305-137">配置 Microsoft Edge 同步</span><span class="sxs-lookup"><span data-stu-id="a9305-137">Configure Microsoft Edge sync</span></span>

<span data-ttu-id="a9305-138">Azure 信息保护 (AIP) 服务提供了 Microsoft Edge 同步的配置选项。</span><span class="sxs-lookup"><span data-stu-id="a9305-138">Configuration options for Microsoft Edge sync are available through the Azure Information Protection (AIP) service.</span></span> <span data-ttu-id="a9305-139">为租户启用 AIP 后，无论获得何种许可，所有用户均可同步 Microsoft Edge 数据。</span><span class="sxs-lookup"><span data-stu-id="a9305-139">When AIP is enabled for a tenant, all users can sync Microsoft Edge data, regardless of licensing.</span></span> <span data-ttu-id="a9305-140">有关如何启用 AIP 的说明，请参阅[此处](/azure/information-protection/activate-office365)。</span><span class="sxs-lookup"><span data-stu-id="a9305-140">Instructions on how to enable AIP can be found [here](/azure/information-protection/activate-office365).</span></span>

<span data-ttu-id="a9305-141">若要限制某一组用户使用同步功能，可为这些用户启用 [AIP 登录控制策略](/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?preserve-view=true&view=azureipps) 。</span><span class="sxs-lookup"><span data-stu-id="a9305-141">To restrict sync to certain set of users, you can enable the [AIP onboarding control policy](/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?preserve-view=true&view=azureipps) for those users.</span></span> <span data-ttu-id="a9305-142">如果确保所有必需的用户均加入后同步仍不可用，请确保已使用 [Get-AIPServiceIPCv3](/powershell/module/aipservice/get-aipserviceipcv3?preserve-view=true&view=azureipps) PowerShell cmdlet 启用 IPCv3Service。</span><span class="sxs-lookup"><span data-stu-id="a9305-142">If sync is still not available after ensuring that all necessary users are onboarded, ensure that the IPCv3Service is enabled using the [Get-AIPServiceIPCv3](/powershell/module/aipservice/get-aipserviceipcv3?preserve-view=true&view=azureipps)  PowerShell cmdlet.</span></span>

> [!CAUTION]
> <span data-ttu-id="a9305-143">激活 Azure 信息保护还将允许其他应用程序（如 Microsoft Word 或 Microsoft Outlook）使用 AIP 保护内容。</span><span class="sxs-lookup"><span data-stu-id="a9305-143">Activating Azure Information Protection will also allow other applications, such as Microsoft Word or Microsoft Outlook, to protect content with AIP.</span></span> <span data-ttu-id="a9305-144">此外，用于限制 Microsoft Edge 同步的任何载入控制策略也将限制其他应用程序使用 AIP 保护内容。</span><span class="sxs-lookup"><span data-stu-id="a9305-144">In addition, any onboarding control policy used to restrict Edge sync will also restrict other applications from protecting content using AIP.</span></span>

## <a name="microsoft-edge-and-enterprise-state-roaming-esr"></a><span data-ttu-id="a9305-145">Microsoft Edge 和企业状态漫游 (ESR) </span><span class="sxs-lookup"><span data-stu-id="a9305-145">Microsoft Edge and Enterprise State Roaming (ESR)</span></span>

<span data-ttu-id="a9305-146">Microsoft Edge 是一个跨平台应用程序，扩展了跨用户的所有设备同步用户数据的范围，并且不再是 Azure AD 企业状态漫游的一部分。</span><span class="sxs-lookup"><span data-stu-id="a9305-146">Microsoft Edge is a cross-platform application with an expanded scope for syncing user data across all their devices and is no longer a part of Azure AD Enterprise State Roaming.</span></span> <span data-ttu-id="a9305-147">但是，Microsoft Edge 将履行 ESR 的数据保护承诺，例如能够引入你自己的密钥。</span><span class="sxs-lookup"><span data-stu-id="a9305-147">However, the Microsoft Edge will fulfill the data protection promises of ESR, such as the ability to bring your own key.</span></span> <span data-ttu-id="a9305-148">有关详细信息，请参阅 [Microsoft Edge 和企业状态漫游](microsoft-edge-enterprise-state-roaming.md)。</span><span class="sxs-lookup"><span data-stu-id="a9305-148">For more information, see [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a9305-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9305-149">See also</span></span>

- [<span data-ttu-id="a9305-150">Microsoft Edge 企业同步</span><span class="sxs-lookup"><span data-stu-id="a9305-150">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)
- [<span data-ttu-id="a9305-151">诊断和修复 Microsoft Edge 同步问题</span><span class="sxs-lookup"><span data-stu-id="a9305-151">Diagnose and fix Microsoft Edge sync issues</span></span>](microsoft-edge-troubleshoot-enterprise-sync.md)
- [<span data-ttu-id="a9305-152">Microsoft Edge 和企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="a9305-152">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="a9305-153">Microsoft Edge 企业版登录页面</span><span class="sxs-lookup"><span data-stu-id="a9305-153">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)