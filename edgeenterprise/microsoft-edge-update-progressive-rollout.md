---
title: Microsoft Edge Stable 渠道更新的渐进式部署
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 05/21/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Stable 渠道更新的渐进式部署
ms.openlocfilehash: 5b0d2f58318b10538d0470b644d346b5b9b9489b
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979320"
---
# <span data-ttu-id="9605f-103">Microsoft Edge Stable 渠道更新的渐进式部署</span><span class="sxs-lookup"><span data-stu-id="9605f-103">Progressive rollouts for Microsoft Edge Stable channel updates</span></span>

<span data-ttu-id="9605f-104">从 Microsoft Edge 83 版开始，我们将在几天内将主要更新渐进式部署到 Microsoft Edge Stable 渠道中。</span><span class="sxs-lookup"><span data-stu-id="9605f-104">Starting with Microsoft Edge 83 release, we will perform gradual rollouts of major updates to Microsoft Edge Stable channel over the span of a few days.</span></span> <span data-ttu-id="9605f-105">此渐进式部署使我们能够监视升级并在整个组织中安全地更新浏览器。</span><span class="sxs-lookup"><span data-stu-id="9605f-105">This progressive rollout allows us to monitor upgrades and safely update the browser across the organization.</span></span>

> [!NOTE]
> <span data-ttu-id="9605f-106">适用于 Microsoft Edge Stable 渠道版本 83 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="9605f-106">This applies to Microsoft Edge Stable channel version 83 or later.</span></span>

## <span data-ttu-id="9605f-107">为什么需要渐进式部署？</span><span class="sxs-lookup"><span data-stu-id="9605f-107">Why do we need progressive rollout?</span></span>

<span data-ttu-id="9605f-108">通过在几天内严密监视更新的运行状况并部署更新，可限制新的更新可能发生的问题带来的影响。</span><span class="sxs-lookup"><span data-stu-id="9605f-108">By monitoring the health of our updates closely and rolling out the updates over the course of several days, we can limit the impact of issues that might occur with the new update.</span></span> <span data-ttu-id="9605f-109">使用 Microsoft Edge 发布版本 83，将为所有 Windows 7、Windows 8 & 8.1 和 Windows 10 版 Microsoft Edge 启用渐进式部署。</span><span class="sxs-lookup"><span data-stu-id="9605f-109">With Microsoft Edge release 83, Progressive Rollouts will be enabled for all Windows 7, Windows 8 & 8.1, and Windows 10 versions of Microsoft Edge.</span></span> <span data-ttu-id="9605f-110">我们将尽快在 Mac 上支持 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="9605f-110">We will support Microsoft Edge on Mac as soon as it is ready.</span></span>

## <span data-ttu-id="9605f-111">更新将如何工作？</span><span class="sxs-lookup"><span data-stu-id="9605f-111">How will the updates work?</span></span>

<span data-ttu-id="9605f-112">更新将为每个 Microsoft Edge 安装分配一个升级值。</span><span class="sxs-lookup"><span data-stu-id="9605f-112">Each installation of Microsoft Edge is assigned an upgrade value.</span></span> <span data-ttu-id="9605f-113">当我们开始以增量方式部署时，如果设备上的值落在升级值范围内，你就看到更新。</span><span class="sxs-lookup"><span data-stu-id="9605f-113">When we start rolling out incrementally, you'll see the update when the value on your device falls within the upgrade value range.</span></span> <span data-ttu-id="9605f-114">几天内随着部署的推进，所有用户最终都将获得更新。</span><span class="sxs-lookup"><span data-stu-id="9605f-114">As the rollout progresses (within a few days), all users will eventually get the update.</span></span> <span data-ttu-id="9605f-115">拥有关键安全修补程序浏览器更新部署速度会更快。</span><span class="sxs-lookup"><span data-stu-id="9605f-115">Browser updates with critical security fixes will have a faster rollout cadence than updates that don't have critical security fixes.</span></span> <span data-ttu-id="9605f-116">这样做是为了确保及时防范漏洞。</span><span class="sxs-lookup"><span data-stu-id="9605f-116">This is done to ensure prompt protection from vulnerabilities.</span></span>

## <span data-ttu-id="9605f-117">这对企业有何影响？</span><span class="sxs-lookup"><span data-stu-id="9605f-117">How does this affect enterprises?</span></span>

<span data-ttu-id="9605f-118">Microsoft Edge 产品通过多种机制（如 Microsoft Intune、Windows Server Update Service (WSUS) 和 Configuration Manager ）分发给企业。</span><span class="sxs-lookup"><span data-stu-id="9605f-118">Microsoft Edge artifacts are distributed to enterprises using multiple mechanisms such as Microsoft Intune, Windows Server Update Service (WSUS), and Configuration Manager.</span></span> <span data-ttu-id="9605f-119">这些部署工具在渐进式部署方面有不同的行为：</span><span class="sxs-lookup"><span data-stu-id="9605f-119">These deployment tools behave differently with respect to Progressive Rollout:</span></span>

- <span data-ttu-id="9605f-120">通过 Microsoft Intune 管理分发的企业会注册为自动更新。</span><span class="sxs-lookup"><span data-stu-id="9605f-120">Enterprises that manage distribution via Microsoft Intune are registered for auto-updates.</span></span> <span data-ttu-id="9605f-121">采用渐进式部署，所有用户将在几天内看到更新。</span><span class="sxs-lookup"><span data-stu-id="9605f-121">Progressive Rollout is used, and all the users will see an update in a few days.</span></span>
- <span data-ttu-id="9605f-122">通过 WSUS (Windows Server Update Services) 或 Configuration Manager 管理分发的企业不会注册为自动更新。</span><span class="sxs-lookup"><span data-stu-id="9605f-122">Enterprises that manage distribution through WSUS (Windows Server Update Services) or Configuration Manager are not registered for auto-updates.</span></span> <span data-ttu-id="9605f-123">从一开始，管理员就可以管理并应用更新。</span><span class="sxs-lookup"><span data-stu-id="9605f-123">Administrators manage and apply the updates that will be available from the start.</span></span> <span data-ttu-id="9605f-124">渐进式部署不会影响此过程。</span><span class="sxs-lookup"><span data-stu-id="9605f-124">Progressive Rollout does not affect this process.</span></span>

<span data-ttu-id="9605f-125">如果你有任何疑问或问题，请通过 User Voice、“应用程序反馈”按钮，或在以下评论中提供宝贵意见。</span><span class="sxs-lookup"><span data-stu-id="9605f-125">Please share your valuable feedback through user voice, the in-application feedback button, or below in the comments if you have any concerns or questions.</span></span>

## <span data-ttu-id="9605f-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9605f-126">See also</span></span>

- [<span data-ttu-id="9605f-127">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="9605f-127">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
