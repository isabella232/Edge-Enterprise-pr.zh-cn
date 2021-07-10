---
title: Microsoft Edge 渠道概述
ms.author: srugh
author: srugh
manager: seanlynd
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 渠道概述
ms.openlocfilehash: 7d1fb72b458569cb4e4c6f44a6d89be7f65984df
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641988"
---
# <a name="overview-of-the-microsoft-edge-channels"></a><span data-ttu-id="75466-103">Microsoft Edge 渠道概述</span><span class="sxs-lookup"><span data-stu-id="75466-103">Overview of the Microsoft Edge channels</span></span>

<span data-ttu-id="75466-104">Microsoft Edge 下一版本的优点之一是 Microsoft 可定期提供新功能。</span><span class="sxs-lookup"><span data-stu-id="75466-104">One of the benefits of the next version of Microsoft Edge is that Microsoft can provide new features on a regular basis.</span></span> <span data-ttu-id="75466-105">但是，你作为将 Microsoft Edge 部署到组织中的用户的管理员，可能要更细致地控制你的用户多久获取一次这些新功能。</span><span class="sxs-lookup"><span data-stu-id="75466-105">However, as the admin who deploys Microsoft Edge to the users in your organization, you might want to have more control over how often your users get these new features.</span></span> <span data-ttu-id="75466-106">Microsoft 为你提供四个称为“渠道”的选项以控制多久用新功能更新一次 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="75466-106">Microsoft provides you four options, called channels, to control how often Microsoft Edge is updated with new features.</span></span> <span data-ttu-id="75466-107">下面是这四个选项的概述。</span><span class="sxs-lookup"><span data-stu-id="75466-107">Here's an overview of the four options.</span></span>

<span data-ttu-id="75466-108">有关每个频道支持的详细信息，请阅读: [Microsoft Edge 生命周期](/deployedge/microsoft-edge-support-lifecycle)</span><span class="sxs-lookup"><span data-stu-id="75466-108">For more information on support for each channel read: [Microsoft Edge Lifecycle](/deployedge/microsoft-edge-support-lifecycle)</span></span>
  
> [!NOTE]
> <span data-ttu-id="75466-109">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="75466-109">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="channel-overview"></a><span data-ttu-id="75466-110">渠道概述</span><span class="sxs-lookup"><span data-stu-id="75466-110">Channel overview</span></span>

|<span data-ttu-id="75466-111">频道</span><span class="sxs-lookup"><span data-stu-id="75466-111">Channel</span></span>|<span data-ttu-id="75466-112">主要用途</span><span class="sxs-lookup"><span data-stu-id="75466-112">Primary purpose</span></span>|<span data-ttu-id="75466-113">多久用新功能更新一次</span><span class="sxs-lookup"><span data-stu-id="75466-113">How often updated with new features</span></span>|<span data-ttu-id="75466-114">是否受支持？</span><span class="sxs-lookup"><span data-stu-id="75466-114">Supported?</span></span>|
|:---:|---|:---:|:---:|
|[<span data-ttu-id="75466-115">Stable</span><span class="sxs-lookup"><span data-stu-id="75466-115">Stable</span></span>](#stable-channel)|<span data-ttu-id="75466-116">广泛部署</span><span class="sxs-lookup"><span data-stu-id="75466-116">Broad Deployment</span></span>|<span data-ttu-id="75466-117">约 6 周</span><span class="sxs-lookup"><span data-stu-id="75466-117">~6 weeks</span></span>|<span data-ttu-id="75466-118">是</span><span class="sxs-lookup"><span data-stu-id="75466-118">Yes</span></span>|
|[<span data-ttu-id="75466-119">Beta</span><span class="sxs-lookup"><span data-stu-id="75466-119">Beta</span></span>](#beta-channel)|<span data-ttu-id="75466-120">在组织中进行代表性验证</span><span class="sxs-lookup"><span data-stu-id="75466-120">Representative validation in the organization</span></span>|<span data-ttu-id="75466-121">约 6 周</span><span class="sxs-lookup"><span data-stu-id="75466-121">~6 weeks</span></span>|<span data-ttu-id="75466-122">是</span><span class="sxs-lookup"><span data-stu-id="75466-122">Yes</span></span>|
|[<span data-ttu-id="75466-123">Dev</span><span class="sxs-lookup"><span data-stu-id="75466-123">Dev</span></span>](#dev-channel)|<span data-ttu-id="75466-124">规划和开发</span><span class="sxs-lookup"><span data-stu-id="75466-124">Planning and developing</span></span>|<span data-ttu-id="75466-125">每周</span><span class="sxs-lookup"><span data-stu-id="75466-125">Weekly</span></span>|<span data-ttu-id="75466-126">否</span><span class="sxs-lookup"><span data-stu-id="75466-126">No</span></span>|
|[<span data-ttu-id="75466-127">Canary</span><span class="sxs-lookup"><span data-stu-id="75466-127">Canary</span></span>](#canary-channel)|<span data-ttu-id="75466-128">最前沿并有风险的内容</span><span class="sxs-lookup"><span data-stu-id="75466-128">Bleeding edge content</span></span>|<span data-ttu-id="75466-129">每天</span><span class="sxs-lookup"><span data-stu-id="75466-129">Daily</span></span>|<span data-ttu-id="75466-130">否</span><span class="sxs-lookup"><span data-stu-id="75466-130">No</span></span>|

<span data-ttu-id="75466-131">你决定将哪个更新渠道部署到你的用户取决于多个因素，如用户利用多少个业务线应用程序，以及在他们更新了 Microsoft Edge 版本的任何时候你需要测试多少个业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="75466-131">Which update channel you decide to deploy to your users depends on several factors, such as how many line of business applications the user leverages and that you need to test any time they have an updated version of Microsoft Edge.</span></span> <span data-ttu-id="75466-132">要帮助你做出此决策，请查看以下关于为 Microsoft Edge 提供的四个更新渠道的信息。</span><span class="sxs-lookup"><span data-stu-id="75466-132">To help you make this decision, review the following information about the four update channels that are available for Microsoft Edge.</span></span>

### <a name="stable-channel"></a><span data-ttu-id="75466-133">Stable 渠道</span><span class="sxs-lookup"><span data-stu-id="75466-133">Stable Channel</span></span>

<span data-ttu-id="75466-134">Stable 渠道旨在广泛部署到你的组织中，它是大多数用户应所处的渠道。</span><span class="sxs-lookup"><span data-stu-id="75466-134">The Stable Channel is intended for broad deployment in your organization, and it is the channel that most users should be on.</span></span> <span data-ttu-id="75466-135">它是其中最稳定的渠道，是在前一 Beta 渠道版本中提供的功能集达到稳定后的结果。</span><span class="sxs-lookup"><span data-stu-id="75466-135">It is the most stable of the channels and is the a result of the stabilization of the feature set available in the prior Beta Channel release.</span></span> <span data-ttu-id="75466-136">大约每 6 周推出一次新功能。</span><span class="sxs-lookup"><span data-stu-id="75466-136">New features ship about every 6 weeks.</span></span> <span data-ttu-id="75466-137">根据需要推出安全和质量更新。</span><span class="sxs-lookup"><span data-stu-id="75466-137">Security and quality updates ship as needed.</span></span> <span data-ttu-id="75466-138">Stable 渠道中的版本将一直提供服务，直至推出此渠道中的下一版本为止。</span><span class="sxs-lookup"><span data-stu-id="75466-138">A release from the Stable Channel is serviced until the next release from the channel is available.</span></span>

### <a name="beta-channel"></a><span data-ttu-id="75466-139">Beta 渠道</span><span class="sxs-lookup"><span data-stu-id="75466-139">Beta Channel</span></span>

<span data-ttu-id="75466-140">Beta 渠道旨在将它部署到你的组织中一组有代表性的示范用户进行生产活动。</span><span class="sxs-lookup"><span data-stu-id="75466-140">The Beta Channel is intended for production deployment in your organization to a representative sample set of users.</span></span> <span data-ttu-id="75466-141">它是受支持的版本，并且 Beta 中的每个版本均提供服务，直至发布此渠道中的下一版本为止。</span><span class="sxs-lookup"><span data-stu-id="75466-141">It is a supported release, and each release from Beta is serviced until the next release from this channel is available.</span></span> <span data-ttu-id="75466-142">这是一个好机会，可验证在你的环境中一切符合预期，并且如果你遇到问题，可在该版本发布到 Stable 渠道之前修复该问题。</span><span class="sxs-lookup"><span data-stu-id="75466-142">This is a great opportunity to validate that things work as expected in your environment, and if you encounter an issue have it remediated prior to the release going publishing to the Stable Channel.</span></span> <span data-ttu-id="75466-143">大约每 6 周推出一次新功能。</span><span class="sxs-lookup"><span data-stu-id="75466-143">New features ship about every 6 weeks.</span></span> <span data-ttu-id="75466-144">根据需要推出安全和质量更新。</span><span class="sxs-lookup"><span data-stu-id="75466-144">Security and quality updates ship as needed.</span></span>

### <a name="dev-channel"></a><span data-ttu-id="75466-145">Dev 渠道</span><span class="sxs-lookup"><span data-stu-id="75466-145">Dev Channel</span></span>

<span data-ttu-id="75466-146">Dev 渠道旨在帮助你用 Microsoft Edge 的最新功能进行规划和开发，但质量高于 Canary 渠道。</span><span class="sxs-lookup"><span data-stu-id="75466-146">The Dev Channel is intended to help you plan and develop with the latest capabilities of Microsoft Edge, but with higher quality than the Canary Channel.</span></span> <span data-ttu-id="75466-147">借此机会，你可以提前了解后续功能并为下一 Beta 版本做好准备。</span><span class="sxs-lookup"><span data-stu-id="75466-147">This is your opportunity to get an early look at what is coming next and prepare for the next Beta release.</span></span>

### <a name="canary-channel"></a><span data-ttu-id="75466-148">Canary 渠道</span><span class="sxs-lookup"><span data-stu-id="75466-148">Canary Channel</span></span>

<span data-ttu-id="75466-149">Canary 渠道每天发布一次，在所有渠道中最为前沿，但有风险。</span><span class="sxs-lookup"><span data-stu-id="75466-149">The Canary Channel ships daily and is the most bleeding edge of all the channels.</span></span> <span data-ttu-id="75466-150">如果你想要获得最新成果，它们将出现在此处。</span><span class="sxs-lookup"><span data-stu-id="75466-150">If you want access to the newest investments then they will appear here first.</span></span> <span data-ttu-id="75466-151">由于这种节奏的性质所致，逐渐将产生各种问题，因此如果你正在利用 Canary 版本，则你可能要同时安装另一渠道。</span><span class="sxs-lookup"><span data-stu-id="75466-151">Because of the nature of this cadence problems will arise overtime, so you may want another channel installed side by side if you are leveraging the Canary releases.</span></span>

## <a name="see-also"></a><span data-ttu-id="75466-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75466-152">See also</span></span>

- [<span data-ttu-id="75466-153">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="75466-153">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="75466-154">渠道下载</span><span class="sxs-lookup"><span data-stu-id="75466-154">Channel downloads</span></span>](https://aka.ms/EdgeEnterprise)
