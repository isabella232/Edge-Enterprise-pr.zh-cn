---
title: 配置 Microsoft Edge 企业同步
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 03/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 用于配置 Microsoft Edge 以同步收藏夹、密码和其他浏览器数据的管理员和用户选项。
ms.openlocfilehash: bfaa1db297093d0b0655a8d217aefcd59d11ac5e
ms.sourcegitcommit: 86e0de9b27ad4297a6d5a57c866d7ef4fc7bb0cd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400136"
---
# <a name="configure-microsoft-edge-enterprise-sync"></a><span data-ttu-id="fd8c4-103">配置 Microsoft Edge 企业同步</span><span class="sxs-lookup"><span data-stu-id="fd8c4-103">Configure Microsoft Edge enterprise sync</span></span>

<span data-ttu-id="fd8c4-104">本文介绍了管理员如何配置 Microsoft Edge，以便在所有登录设备上同步用户收藏夹、密码和其他浏览器数据。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-104">This article explains how admins can configure Microsoft Edge to sync user favorites, passwords, and other browser data across all signed-in devices.</span></span>

> [!NOTE]
> <span data-ttu-id="fd8c4-105">除非另有说明，否则本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-105">Applies to Microsoft Edge version 77 or later unless otherwise noted.</span></span>

## <a name="overview"></a><span data-ttu-id="fd8c4-106">概述</span><span class="sxs-lookup"><span data-stu-id="fd8c4-106">Overview</span></span>

<span data-ttu-id="fd8c4-107">通过 Microsoft Edge 同步，用户可以访问他们所有已登录设备上的浏览数据。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-107">Microsoft Edge sync enables users to access their browsing data across all their signed-in devices.</span></span> <span data-ttu-id="fd8c4-108">同步支持的数据包括：</span><span class="sxs-lookup"><span data-stu-id="fd8c4-108">The data supported by sync includes:</span></span>

- <span data-ttu-id="fd8c4-109">收藏夹</span><span class="sxs-lookup"><span data-stu-id="fd8c4-109">Favorites</span></span>
- <span data-ttu-id="fd8c4-110">密码</span><span class="sxs-lookup"><span data-stu-id="fd8c4-110">Passwords</span></span>
- <span data-ttu-id="fd8c4-111">地址等（表单填写）</span><span class="sxs-lookup"><span data-stu-id="fd8c4-111">Addresses and more (form-fill)</span></span>
- <span data-ttu-id="fd8c4-112">收藏</span><span class="sxs-lookup"><span data-stu-id="fd8c4-112">Collections</span></span>
- <span data-ttu-id="fd8c4-113">“设置”</span><span class="sxs-lookup"><span data-stu-id="fd8c4-113">Settings</span></span>
- <span data-ttu-id="fd8c4-114">扩展</span><span class="sxs-lookup"><span data-stu-id="fd8c4-114">Extension</span></span>
- <span data-ttu-id="fd8c4-115">打开选项卡（在 Microsoft Edge 版本 88 中可用）</span><span class="sxs-lookup"><span data-stu-id="fd8c4-115">Open tabs (available in Microsoft Edge version 88)</span></span>
- <span data-ttu-id="fd8c4-116">历史记录（在 Microsoft Edge 版本 88 中可用）</span><span class="sxs-lookup"><span data-stu-id="fd8c4-116">History (available in Microsoft Edge version 88)</span></span>

<span data-ttu-id="fd8c4-117">用户同意后即可启用同步功能，并且用户可以针对上面列出的每种数据类型打开或关闭同步功能。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-117">Sync functionality is enabled via user consent and users can turn sync on or off for each of the data types listed above.</span></span> <span data-ttu-id="fd8c4-118">如果用户遇到同步问题，他们需要依次选择“**设置**” > “**配置文件**” > “**重置同步**”来重置同步。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-118">If a user is experiencing a sync issue they might need to reset sync in **Settings** > **Profiles** > **Reset sync**.</span></span>

> [!NOTE]
> <span data-ttu-id="fd8c4-119">将上载其他设备连接和配置数据（如设备名称、品牌和型号），以支持同步功能。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-119">Additional device connectivity and configuration data (such as device name, make and model) is uploaded to support sync functionality.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fd8c4-120">必备条件</span><span class="sxs-lookup"><span data-stu-id="fd8c4-120">Prerequisites</span></span>

<span data-ttu-id="fd8c4-121">适用于 Azure Active Directory (Azure AD) 帐户的 Microsoft Edge 同步功能可供以下任何订阅使用：</span><span class="sxs-lookup"><span data-stu-id="fd8c4-121">Microsoft Edge sync for Azure Active Directory (Azure AD) accounts is available for any of the following subscriptions:</span></span>

- <span data-ttu-id="fd8c4-122">Azure AD Premium（P1 或 P2）</span><span class="sxs-lookup"><span data-stu-id="fd8c4-122">Azure AD Premium (P1 or P2)</span></span>
- <span data-ttu-id="fd8c4-123">M365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="fd8c4-123">M365 Business Premium</span></span>
- <span data-ttu-id="fd8c4-124">Office 365 E1 及更高版本</span><span class="sxs-lookup"><span data-stu-id="fd8c4-124">Office 365 E1 and above</span></span>
- <span data-ttu-id="fd8c4-125">Azure 信息保护 (AIP)（P1 或 P2）</span><span class="sxs-lookup"><span data-stu-id="fd8c4-125">Azure Information Protection (AIP) (P1 or P2)</span></span>
- <span data-ttu-id="fd8c4-126">所有 EDU 订阅（Microsoft 教育应用版（学生）或 Microsoft 教育应用版（教职员工）、Exchange Online 学生版或教职员工版、O365 A1 或更高版本、M365 A1 或更高版本，或者适用于学生或教职员的 Azure 信息保护 P1 或 P2）</span><span class="sxs-lookup"><span data-stu-id="fd8c4-126">All EDU subscriptions (Microsoft Apps for Students or Faculty, Exchange Online for Students or Faculty, O365 A1 or above, M365 A1 or above, or Azure Information Protection P1 or P2 for Students or Faculty)</span></span>

## <a name="sync-group-policies"></a><span data-ttu-id="fd8c4-127">同步组策略</span><span class="sxs-lookup"><span data-stu-id="fd8c4-127">Sync group policies</span></span>

<span data-ttu-id="fd8c4-128">管理员可以使用以下组策略配置和管理 Microsoft Edge 同步：</span><span class="sxs-lookup"><span data-stu-id="fd8c4-128">Admins can use the following group policies to configure and manage Microsoft Edge sync:</span></span>

- <span data-ttu-id="fd8c4-129">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled)：完全禁用同步。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-129">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): Disables sync completely.</span></span>
- <span data-ttu-id="fd8c4-130">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled)：禁止保存浏览历史记录和同步。此策略还将禁用打开选项卡同步。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-130">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): Disables saving browsing history and sync. This policy also disables open-tabs sync.</span></span>
- <span data-ttu-id="fd8c4-131">[AllowDeletingBrowserHistory](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory)：当此策略设置为禁用时，还将禁用历史记录同步。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-131">[AllowDeletingBrowserHistory](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory): When this policy is set to disabled, history sync will also be disabled.</span></span>
- <span data-ttu-id="fd8c4-132">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled)：配置从同步中排除的类型列表。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-132">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): Configure the list of types that are excluded from synchronization.</span></span>
- <span data-ttu-id="fd8c4-133">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled)：允许 Active Directory (AD) 配置文件使用本地存储。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-133">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): Allow Active Directory (AD) profiles to use on-premises storage.</span></span> <span data-ttu-id="fd8c4-134">有关更多信息，请参阅 [Active Directory (AD) 用户的本地同步](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync)。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-134">For more information, see [On-premises sync for Active Directory (AD) users](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync).</span></span>
- <span data-ttu-id="fd8c4-135">[ForceSync：]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync)默认启用同步，无需用户同意。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-135">[ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): Turn on sync by default and do not require user consent to sync.</span></span>  

## <a name="configure-microsoft-edge-sync"></a><span data-ttu-id="fd8c4-136">配置 Microsoft Edge 同步</span><span class="sxs-lookup"><span data-stu-id="fd8c4-136">Configure Microsoft Edge sync</span></span>

<span data-ttu-id="fd8c4-137">Azure 信息保护 (AIP) 服务提供了 Microsoft Edge 同步的配置选项。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-137">Configuration options for Microsoft Edge sync are available through the Azure Information Protection (AIP) service.</span></span> <span data-ttu-id="fd8c4-138">为租户启用 AIP 后，无论获得何种许可，所有用户均可同步 Microsoft Edge 数据。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-138">When AIP is enabled for a tenant, all users can sync Microsoft Edge data, regardless of licensing.</span></span> <span data-ttu-id="fd8c4-139">有关如何启用 AIP 的说明，请参阅[此处](https://docs.microsoft.com/azure/information-protection/activate-office365)。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-139">Instructions on how to enable AIP can be found [here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span>

<span data-ttu-id="fd8c4-140">若要限制某一组用户使用同步功能，可为这些用户启用 [AIP 登录控制策略](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true) 。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-140">To restrict sync to certain set of users, you can enable the [AIP onboarding control policy](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true) for those users.</span></span> <span data-ttu-id="fd8c4-141">如果确保所有必需的用户均加入后同步仍不可用，请确保已使用 [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true) PowerShell cmdlet 启用 IPCv3Service。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-141">If sync is still not available after ensuring that all necessary users are onboarded, ensure that the IPCv3Service is enabled using the [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true)  PowerShell cmdlet.</span></span>

> [!CAUTION]
> <span data-ttu-id="fd8c4-142">激活 Azure 信息保护还将允许其他应用程序（如 Microsoft Word 或 Microsoft Outlook）使用 AIP 保护内容。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-142">Activating Azure Information Protection will also allow other applications, such as Microsoft Word or Microsoft Outlook, to protect content with AIP.</span></span> <span data-ttu-id="fd8c4-143">此外，用于限制 Microsoft Edge 同步的任何载入控制策略也将限制其他应用程序使用 AIP 保护内容。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-143">In addition, any onboarding control policy used to restrict Edge sync will also restrict other applications from protecting content using AIP.</span></span>

## <a name="microsoft-edge-and-enterprise-state-roaming-esr"></a><span data-ttu-id="fd8c4-144">Microsoft Edge 和企业状态漫游 (ESR) </span><span class="sxs-lookup"><span data-stu-id="fd8c4-144">Microsoft Edge and Enterprise State Roaming (ESR)</span></span>

<span data-ttu-id="fd8c4-145">Microsoft Edge 是一个跨平台应用程序，扩展了跨用户的所有设备同步用户数据的范围，并且不再是 Azure AD 企业状态漫游的一部分。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-145">Microsoft Edge is a cross-platform application with an expanded scope for syncing user data across all their devices and is no longer a part of Azure AD Enterprise State Roaming.</span></span> <span data-ttu-id="fd8c4-146">但是，Microsoft Edge 将履行 ESR 的数据保护承诺，例如能够引入你自己的密钥。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-146">However, the Microsoft Edge will fulfill the data protection promises of ESR, such as the ability to bring your own key.</span></span> <span data-ttu-id="fd8c4-147">有关详细信息，请参阅 [Microsoft Edge 和企业状态漫游](microsoft-edge-enterprise-state-roaming.md)。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-147">For more information, see [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fd8c4-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd8c4-148">See also</span></span>

- [<span data-ttu-id="fd8c4-149">Microsoft Edge 企业同步</span><span class="sxs-lookup"><span data-stu-id="fd8c4-149">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)
- [<span data-ttu-id="fd8c4-150">诊断和修复 Microsoft Edge 同步问题</span><span class="sxs-lookup"><span data-stu-id="fd8c4-150">Diagnose and fix Microsoft Edge sync issues</span></span>](microsoft-edge-troubleshoot-enterprise-sync.md)
- [<span data-ttu-id="fd8c4-151">Microsoft Edge 和企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="fd8c4-151">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="fd8c4-152">Microsoft Edge 企业版登录页面</span><span class="sxs-lookup"><span data-stu-id="fd8c4-152">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
