---
title: Microsoft Edge 配置和实验
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 02/20/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 配置和实验
ms.openlocfilehash: f66da4075c33c1f375dfb593c1a1bd2b4a139833
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979260"
---
# <span data-ttu-id="f745b-103">Microsoft Edge 配置和实验</span><span class="sxs-lookup"><span data-stu-id="f745b-103">Microsoft Edge configurations and experimentation</span></span>

<span data-ttu-id="f745b-104">本文介绍了 Microsoft Edge 与实验和配置服务 (ECS) 之间的交互。</span><span class="sxs-lookup"><span data-stu-id="f745b-104">This article describes the interaction between Microsoft Edge and the Experimentation and Configuration Service (ECS).</span></span> <span data-ttu-id="f745b-105">Microsoft Edge 与此服务通信以请求和接收不同种类的负载。</span><span class="sxs-lookup"><span data-stu-id="f745b-105">Microsoft Edge communicates with this service to request and receive different kinds of payloads.</span></span> <span data-ttu-id="f745b-106">这些负载包括配置、功能展示和实验。</span><span class="sxs-lookup"><span data-stu-id="f745b-106">These payloads include configurations, feature rollouts, and experiments.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f745b-107">确保客户端能够访问 `https://config.edge.skype.com` 以能够接收到负载。</span><span class="sxs-lookup"><span data-stu-id="f745b-107">Make sure clients are able to access `https://config.edge.skype.com` so payloads can be received.</span></span>

> [!NOTE]
> <span data-ttu-id="f745b-108">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="f745b-108">This applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="f745b-109">配置</span><span class="sxs-lookup"><span data-stu-id="f745b-109">Configurations</span></span>

<span data-ttu-id="f745b-110">配置是用于确保产品运行状况、安全性和隐私合规性的有效负载，旨在对所有用户都提供相同的值（基于平台和频道）。这可能是为域操作启用功能标志，也可用于在出现 bug 时禁用功能标志。</span><span class="sxs-lookup"><span data-stu-id="f745b-110">Configurations are the payload meant to ensure product health, security, and privacy compliance, and are intended to have the same value for all the users (based on platforms and channels.) This could be to enable a feature flag for a domain action, and can also be used to disable a feature flag in the event of a bug.</span></span>

## <span data-ttu-id="f745b-111">受控功能推出</span><span class="sxs-lookup"><span data-stu-id="f745b-111">Controlled Feature Rollout</span></span>

<span data-ttu-id="f745b-112">受控功能推出 (CFR) 是一种缓慢增加接收功能的用户组规模的过程。</span><span class="sxs-lookup"><span data-stu-id="f745b-112">Controlled Feature Rollout (CFR) is a procedure for slowly increasing the size of the user group that receives a feature.</span></span> <span data-ttu-id="f745b-113">通过将新功能分配给随机选择的一部分用户，可以将用户反馈与大小相同且无该功能的对照组进行比较，以评估该功能的影响。</span><span class="sxs-lookup"><span data-stu-id="f745b-113">By distributing a new feature to a randomly selected subset of the user population, it’s possible to compare user feedback to an equally sized control group without the feature to measure the impact of the feature.</span></span>

## <span data-ttu-id="f745b-114">试验</span><span class="sxs-lookup"><span data-stu-id="f745b-114">Experiments</span></span>

<span data-ttu-id="f745b-115">Microsoft Edge 版本具有仍在开发或实验中的特性和功能。</span><span class="sxs-lookup"><span data-stu-id="f745b-115">Microsoft Edge builds have features and functionality that are still in development or are experimental.</span></span> <span data-ttu-id="f745b-116">实验类似于 CFR，但用户组更小，以便于测试新概念。</span><span class="sxs-lookup"><span data-stu-id="f745b-116">Experiments are like CFR, but the size of the user group is much smaller for testing the new concept.</span></span> <span data-ttu-id="f745b-117">这些功能默认情况下将隐藏，直到推出该功能或实验结束为止。</span><span class="sxs-lookup"><span data-stu-id="f745b-117">These features are hidden by default until the feature's rolled out or the experiment's finished.</span></span> <span data-ttu-id="f745b-118">实验标志用于启用和禁用这些功能。</span><span class="sxs-lookup"><span data-stu-id="f745b-118">Experiment flags are used to enable and disable these features.</span></span>

## <span data-ttu-id="f745b-119">关于 ECS</span><span class="sxs-lookup"><span data-stu-id="f745b-119">About the ECS</span></span>

<span data-ttu-id="f745b-120">在上述所有场景下，该服务都会将功能标志值传递给浏览器客户端，以便可以应用这些值。</span><span class="sxs-lookup"><span data-stu-id="f745b-120">In all the preceding scenarios, the service delivers the feature flag values to the browser client so they can be applied.</span></span> <span data-ttu-id="f745b-121">将立即应用配置，或者在用户重启浏览器时立即应用配置，具体取决于更新。</span><span class="sxs-lookup"><span data-stu-id="f745b-121">Depending on the update, configurations are applied immediately or when the user restarts the browser.</span></span>

<span data-ttu-id="f745b-122">Microsoft Edge 与该服务的交互受 [ExperimentationAndConfigurationServiceControl](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#experimentationandconfigurationservicecontrol) 策略中的设置控制。</span><span class="sxs-lookup"><span data-stu-id="f745b-122">Microsoft Edge's interaction with this service is controlled by settings in the [ExperimentationAndConfigurationServiceControl](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#experimentationandconfigurationservicecontrol) policy.</span></span> <span data-ttu-id="f745b-123">你可以将策略设置配置为：</span><span class="sxs-lookup"><span data-stu-id="f745b-123">You can configure policy settings to:</span></span>

- <span data-ttu-id="f745b-124">仅检索配置</span><span class="sxs-lookup"><span data-stu-id="f745b-124">Retrieve configurations only</span></span>
- <span data-ttu-id="f745b-125">检索配置和实验</span><span class="sxs-lookup"><span data-stu-id="f745b-125">Retrieve configurations and experiments</span></span>
- <span data-ttu-id="f745b-126">禁止与服务通信</span><span class="sxs-lookup"><span data-stu-id="f745b-126">Disable communication with the service</span></span>

  > [!CAUTION]
  > <span data-ttu-id="f745b-127">如果你禁止与服务通信，这将影响 Microsoft 及时处理严重 bug 的能力。</span><span class="sxs-lookup"><span data-stu-id="f745b-127">If you disable communications with the service, this will affect Microsoft’s ability to respond to a severe bug in a timely manner.</span></span>

## <span data-ttu-id="f745b-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f745b-128">See also</span></span>

- [<span data-ttu-id="f745b-129">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="f745b-129">Microsoft Edge Enterprise landing page</span></span>](https://www.microsoftedgeinsider.com/enterprise)
- [<span data-ttu-id="f745b-130">Microsoft Edge 文档登录页面</span><span class="sxs-lookup"><span data-stu-id="f745b-130">Microsoft Edge documentation landing page</span></span>](https://docs.microsoft.com/DeployEdge/)
