---
title: Active Directory (AD) 用户的本地同步
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 10/05/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Active Directory (AD) 用户的本地同步
ms.openlocfilehash: ce7fd912bc8cbd71e12444d58073e43df6b138db
ms.sourcegitcommit: bd68077356a944b99a424d03b444b04aa60272dd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2020
ms.locfileid: "11099741"
---
# <span data-ttu-id="2ece3-103">Active Directory (AD) 用户的本地同步</span><span class="sxs-lookup"><span data-stu-id="2ece3-103">On-premises sync for Active Directory (AD) users</span></span>

<span data-ttu-id="2ece3-104">本文介绍 Active Directory (AD) 用户如何在不连接到 Microsoft 云服务的情况下，在计算机之间漫游 Microsoft Edge 收藏夹和设置。</span><span class="sxs-lookup"><span data-stu-id="2ece3-104">This article explains how Active Directory (AD) users can roam Microsoft Edge favorites and settings between computers without connecting to Microsoft cloud services.</span></span>

> [!NOTE]
> <span data-ttu-id="2ece3-105">本文适用于 Microsoft Edge 版本 85 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="2ece3-105">This article applies to Microsoft Edge version 85 or later.</span></span>

## <span data-ttu-id="2ece3-106">简介</span><span class="sxs-lookup"><span data-stu-id="2ece3-106">Introduction</span></span>

<span data-ttu-id="2ece3-107">若要在 Microsoft Edge 中同步用户数据，通常需要 Microsoft 帐户或 Azure Active Directory (Azure AD) 帐户，并且需要连接到 Microsoft 云服务。</span><span class="sxs-lookup"><span data-stu-id="2ece3-107">Syncing user data in Microsoft Edge normally requires either a Microsoft Account or an Azure Active Directory (Azure AD) account, and a connection to Microsoft cloud services.</span></span> <span data-ttu-id="2ece3-108">使用本地同步时，Microsoft Edge 将 Active Directory 用户的收藏夹和设置保存到可在不同计算机之间移动的文件中。</span><span class="sxs-lookup"><span data-stu-id="2ece3-108">With on-premises sync, Microsoft Edge saves an Active Directory user's favorites and settings to a file that can be moved between different computers.</span></span> <span data-ttu-id="2ece3-109">本地同步不会影响允许云同步的那些配置文件的云同步。</span><span class="sxs-lookup"><span data-stu-id="2ece3-109">On-premises sync doesn't interfere with cloud syncing for those profiles that allow it.</span></span>

## <span data-ttu-id="2ece3-110">工作原理</span><span class="sxs-lookup"><span data-stu-id="2ece3-110">How it works</span></span>

<span data-ttu-id="2ece3-111">Microsoft Edge 允许配置文件与 Active Directory (AD) 帐户关联，而 Active Directory (AD) 帐户不能与云同步一起使用。启用本地同步后，AD 配置文件中的数据将保存到名为 profile.pb 的文件中。</span><span class="sxs-lookup"><span data-stu-id="2ece3-111">Microsoft Edge allows profiles to be associated with Active Directory (AD) accounts, which can't be used with cloud sync. When on-premises sync is enabled, the data from the AD profile is saved to a file named profile.pb.</span></span> <span data-ttu-id="2ece3-112">默认情况下，此文件存储在 *%APPDATA%/Microsoft/Edge* 中。</span><span class="sxs-lookup"><span data-stu-id="2ece3-112">By default, this file is stored in *%APPDATA%/Microsoft/Edge*.</span></span> <span data-ttu-id="2ece3-113">写入此文件后，它可以在不同的计算机之间移动，并且用户数据将在每台计算机上读取和写入。</span><span class="sxs-lookup"><span data-stu-id="2ece3-113">After this file is written, it can be moved between different computers, and user data will be read and written on each computer.</span></span>

## <span data-ttu-id="2ece3-114">使用本地同步</span><span class="sxs-lookup"><span data-stu-id="2ece3-114">Use on-premises sync</span></span>

<span data-ttu-id="2ece3-115">若要使用本地同步，必须启用该功能，将配置文件与 AD 帐户关联，并可选择更改用户数据的位置。</span><span class="sxs-lookup"><span data-stu-id="2ece3-115">To use on-premises sync, you have to enable it, associate a profile with an AD account, and optionally, change the location of the user data.</span></span>

### <span data-ttu-id="2ece3-116">启用本地同步</span><span class="sxs-lookup"><span data-stu-id="2ece3-116">Enable on-premises sync</span></span>

<span data-ttu-id="2ece3-117">若要在 Microsoft Edge 中启用本地同步，请配置 [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled) 策略。</span><span class="sxs-lookup"><span data-stu-id="2ece3-117">To enable on-premises sync in Microsoft Edge, configure the [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled) policy.</span></span>

### <span data-ttu-id="2ece3-118">确保配置文件与 Active Directory 帐户相关联</span><span class="sxs-lookup"><span data-stu-id="2ece3-118">Ensure that a profile is associated with an Active Directory account</span></span>

<span data-ttu-id="2ece3-119">本地同步仅适用于与 Active Directory (AD) 帐户相关联的配置文件。</span><span class="sxs-lookup"><span data-stu-id="2ece3-119">On-premises sync only works with the profile associated with an Active Directory (AD) account.</span></span> <span data-ttu-id="2ece3-120">如果不存在此类配置文件，则本地同步将无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="2ece3-120">If no such profile exists, on-premises sync will not function.</span></span> <span data-ttu-id="2ece3-121">若要确保用户使用 AD 帐户登录，请配置 [ConfigureOnPremisesAccountAutoSignIn](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureonpremisesaccountautosignin) 策略。</span><span class="sxs-lookup"><span data-stu-id="2ece3-121">To ensure that users sign on with an AD account, configure the [ConfigureOnPremisesAccountAutoSignIn](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configureonpremisesaccountautosignin) policy.</span></span>

### <span data-ttu-id="2ece3-122">更改用户数据的位置（可选）</span><span class="sxs-lookup"><span data-stu-id="2ece3-122">Change the location of the user data (optional)</span></span>

<span data-ttu-id="2ece3-123">默认情况下，用户数据存储在 *%APPDATA%/Microsoft/Edge* 下名为 **profile.pb** 的文件中。</span><span class="sxs-lookup"><span data-stu-id="2ece3-123">By default, the user data is stored in a filed named **profile.pb** in *%APPDATA%/Microsoft/Edge*.</span></span> <span data-ttu-id="2ece3-124">若要更改此文件的位置，请配置 [RoamingProfileLocation](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilelocation) 策略。</span><span class="sxs-lookup"><span data-stu-id="2ece3-124">To change the location of this file, configure the [RoamingProfileLocation](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilelocation) policy.</span></span>

## <span data-ttu-id="2ece3-125">启用本地同步时的用户体验更改</span><span class="sxs-lookup"><span data-stu-id="2ece3-125">Changes in the user experience when on-premises sync is enabled</span></span>

<span data-ttu-id="2ece3-126">启用本地同步时，不会要求用户启用同步。此外，用户无法在同步设置中关闭同步，也无法打开本地同步不支持的同步类型。</span><span class="sxs-lookup"><span data-stu-id="2ece3-126">When on-premises sync is enabled, users won't be asked to enable sync. In addition, users can't turn off sync in Sync settings, and they can't turn on sync types that aren't supported by on-premises sync.</span></span>

## <span data-ttu-id="2ece3-127">本地同步使用说明</span><span class="sxs-lookup"><span data-stu-id="2ece3-127">On-premises sync usage notes</span></span>

### <span data-ttu-id="2ece3-128">在同一台计算机上运行云同步和本地同步</span><span class="sxs-lookup"><span data-stu-id="2ece3-128">Running cloud sync and on-premises sync on the same computer</span></span>

<span data-ttu-id="2ece3-129">本地同步不会影响云同步。如果 Microsoft Edge 具有多个 Microsoft 帐户或 Azure Active Directory 配置文件同步到云，则在启用本地同步时，这些配置文件将继续同步。</span><span class="sxs-lookup"><span data-stu-id="2ece3-129">On-premises sync doesn't interfere with cloud sync. If Microsoft Edge has multiple Microsoft Account or Azure Active Directory profiles that sync to the cloud, these profiles will continue to sync while on-premises sync is enabled.</span></span>

### <span data-ttu-id="2ece3-130">不建议一次在多台计算机上运行 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2ece3-130">Running Microsoft Edge on more than one computer at a time isn't recommended</span></span>

<span data-ttu-id="2ece3-131">由于本地同步的工作方式是在计算机之间移动用户数据文件，因此本地同步不会在同时会话之间同步更改。</span><span class="sxs-lookup"><span data-stu-id="2ece3-131">Because on-premises sync works by moving a user data file between computers, on-premises sync doesn't sync changes between simultaneous sessions.</span></span> <span data-ttu-id="2ece3-132">因此，本地同步一次在一台计算机上使用时效果最佳。</span><span class="sxs-lookup"><span data-stu-id="2ece3-132">For this reason, on-premises sync works best when used on one computer at a time.</span></span> <span data-ttu-id="2ece3-133">如果同时运行本地会话，则在下次启动浏览器会话时，任何计算机上的数据可能会被来自另一台计算机的数据意外覆盖。</span><span class="sxs-lookup"><span data-stu-id="2ece3-133">If there are simultaneous on-premises sessions running, data on any of the computers may be unexpectedly overwritten by data from another computer the next time you start a browser session.</span></span>

> [!NOTE]
> <span data-ttu-id="2ece3-134">启用本地同步时，Microsoft Edge 将锁定 **profile.pb** 文件。</span><span class="sxs-lookup"><span data-stu-id="2ece3-134">Microsoft Edge locks the **profile.pb** file when on-premises sync is enabled.</span></span> <span data-ttu-id="2ece3-135">如果文件夹重定向用于在不同计算机之间共享单个 **profile.pb** 文件，则只能启动使用该文件的 Microsoft Edge 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="2ece3-135">If folder redirection is used to share a single **profile.pb** file between different computers, then only one instance of Microsoft Edge using that file can be started.</span></span>

### <span data-ttu-id="2ece3-136">将其他同步策略与本地同步配合使用</span><span class="sxs-lookup"><span data-stu-id="2ece3-136">Using other sync policies with on-premises sync</span></span>

<span data-ttu-id="2ece3-137">如果需要，可以使用 [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) 策略选择性地禁用收藏夹或设置同步。</span><span class="sxs-lookup"><span data-stu-id="2ece3-137">The [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) policy can be used to selectively disable either favorites or settings sync if desired.</span></span> <span data-ttu-id="2ece3-138">如果 [SyncDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#syncdisabled) 策略处于活动状态，则也将禁用本地同步。</span><span class="sxs-lookup"><span data-stu-id="2ece3-138">If the [SyncDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#syncdisabled) policy is active, then on-premises sync is disabled as well.</span></span>  

## <span data-ttu-id="2ece3-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ece3-139">See also</span></span>

- [<span data-ttu-id="2ece3-140">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="2ece3-140">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="2ece3-141">Microsoft Edge 和企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="2ece3-141">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="2ece3-142">Microsoft Edge Enterprise Sync</span><span class="sxs-lookup"><span data-stu-id="2ece3-142">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)
