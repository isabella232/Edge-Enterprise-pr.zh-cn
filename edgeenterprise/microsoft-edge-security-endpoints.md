---
title: Microsoft Edge 终结点的允许列表
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 11/25/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 终结点的允许列表
ms.openlocfilehash: 3d46e2e8c85eadc39cf9788df44b45592ea4fb1b
ms.sourcegitcommit: ed6a5afabf909df87bec48671c4c47bcdfaeb7bc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "11194682"
---
# <span data-ttu-id="91a15-103">Microsoft Edge 终结点的允许列表</span><span class="sxs-lookup"><span data-stu-id="91a15-103">Allow list for Microsoft Edge endpoints</span></span>

<span data-ttu-id="91a15-104">Microsoft Edge 需要连接到 Internet 以支持其功能。</span><span class="sxs-lookup"><span data-stu-id="91a15-104">Microsoft Edge requires connectivity to the Internet to support its features.</span></span> <span data-ttu-id="91a15-105">本文标识了需要添加到允许列表以确保通过防火墙和其他安全机制进行通信的域 URL。</span><span class="sxs-lookup"><span data-stu-id="91a15-105">This article identifies the domain URLs that you need to add to the Allow list to ensure communications through firewalls and other security mechanisms.</span></span>

> [!NOTE]
> <span data-ttu-id="91a15-106">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="91a15-106">This applies  to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="91a15-107">要允许的域 URL</span><span class="sxs-lookup"><span data-stu-id="91a15-107">Domain URLs to allow</span></span>

<span data-ttu-id="91a15-108">对于 Microsoft Edge，允许以下域 URL。</span><span class="sxs-lookup"><span data-stu-id="91a15-108">Allow the following domain URLs for Microsoft Edge.</span></span>

### <span data-ttu-id="91a15-109">更新服务</span><span class="sxs-lookup"><span data-stu-id="91a15-109">Update Service</span></span>

<span data-ttu-id="91a15-110">Microsoft Edge 用于检查新的更新内容的服务。</span><span class="sxs-lookup"><span data-stu-id="91a15-110">The service that Microsoft Edge uses to check for new updates.</span></span>

- `https://msedge.api.cdp.microsoft.com`

### <span data-ttu-id="91a15-111">实验和配置服务</span><span class="sxs-lookup"><span data-stu-id="91a15-111">Experimentation and Configuration service</span></span>

- `https://config.edge.skype.com`

### <span data-ttu-id="91a15-112">Microsoft Edge 的下载位置</span><span class="sxs-lookup"><span data-stu-id="91a15-112">Download locations for Microsoft Edge</span></span>

<span data-ttu-id="91a15-113">可在初始安装期间或有更新可用时从中下载 Microsoft Edge 的位置。</span><span class="sxs-lookup"><span data-stu-id="91a15-113">Locations Microsoft Edge can be downloaded from during an initial install or when an update is available.</span></span> <span data-ttu-id="91a15-114">下载位置由更新服务确定。</span><span class="sxs-lookup"><span data-stu-id="91a15-114">The download location is determined by the Update Service.</span></span>

#### <span data-ttu-id="91a15-115">HTTP</span><span class="sxs-lookup"><span data-stu-id="91a15-115">HTTP</span></span>

- `http://msedge.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.f.dl.delivery.mp.microsoft.com`
- `http://msedge.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.b.dl.delivery.mp.microsoft.com`

#### <span data-ttu-id="91a15-116">HTTPS</span><span class="sxs-lookup"><span data-stu-id="91a15-116">HTTPS</span></span>

- `https://msedge.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sf.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > <span data-ttu-id="91a15-117">要简化下载位置的允许列表，可以使用通配符：</span><span class="sxs-lookup"><span data-stu-id="91a15-117">To simplify the allow list for download locations a wild card can be used:</span></span> `*.dl.delivery.mp.microsoft.com`

### <span data-ttu-id="91a15-118">Microsoft Edge 扩展的下载位置</span><span class="sxs-lookup"><span data-stu-id="91a15-118">Download locations for Microsoft Edge Extensions</span></span>

<span data-ttu-id="91a15-119">可在初始安装期间或有更新可用时从中下载 Microsoft Edge 扩展的位置。</span><span class="sxs-lookup"><span data-stu-id="91a15-119">Locations Microsoft Edge Extensions can be downloaded from during an initial install or when an update is available.</span></span> <span data-ttu-id="91a15-120">下载位置由更新服务确定。</span><span class="sxs-lookup"><span data-stu-id="91a15-120">The download location is determined by the Update Service.</span></span>

#### <span data-ttu-id="91a15-121">HTTP</span><span class="sxs-lookup"><span data-stu-id="91a15-121">HTTP</span></span>

- `http://msedgeextensions.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.f.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.dl.delivery.mp.microsoft.com`

#### <span data-ttu-id="91a15-122">HTTPS</span><span class="sxs-lookup"><span data-stu-id="91a15-122">HTTPS</span></span>

- `https://msedgeextensions.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sf.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > <span data-ttu-id="91a15-123">要简化下载位置的允许列表，可以使用通配符：</span><span class="sxs-lookup"><span data-stu-id="91a15-123">To simplify the allow list for download locations a wild card can be used:</span></span> `*.dl.delivery.mp.microsoft.com`

### <span data-ttu-id="91a15-124">对于下载传递优化为可选</span><span class="sxs-lookup"><span data-stu-id="91a15-124">Optionally for Download Delivery Optimization</span></span>

<span data-ttu-id="91a15-125">有关传递优化的详细信息，请参阅 [适用于 Windows 10 更新的传递优化](https://aka.ms/waas-do)。</span><span class="sxs-lookup"><span data-stu-id="91a15-125">For information about delivery optimization, see [Delivery Optimization for Windows 10 updates](https://aka.ms/waas-do).</span></span>

- <span data-ttu-id="91a15-126">客户端到服务的通信：`*.do.dsp.mp.microsoft.com`（HTTP 端口 80、HTTPS 端口 443）</span><span class="sxs-lookup"><span data-stu-id="91a15-126">Client to Service communication: `*.do.dsp.mp.microsoft.com` (HTTP Port 80, HTTPS Port 443)</span></span>
- <span data-ttu-id="91a15-127">客户端到客户端通信：应对入站流量打开 TCP 端口 7680</span><span class="sxs-lookup"><span data-stu-id="91a15-127">Client to Client communication: TCP port 7680 should be open for inbound traffic</span></span>

### <span data-ttu-id="91a15-128">Sync</span><span class="sxs-lookup"><span data-stu-id="91a15-128">Sync</span></span>

<span data-ttu-id="91a15-129">这些终结点可管理同步数据的读取和写入、安全数据的权限管理，以及在有新同步数据时的浏览器通知。</span><span class="sxs-lookup"><span data-stu-id="91a15-129">These endpoints manage the reading and writing of synced data, rights management for secure data, and notifying the browser when new sync data is available.</span></span>

- <span data-ttu-id="91a15-130">Microsoft Edge 同步服务终结点：</span><span class="sxs-lookup"><span data-stu-id="91a15-130">Edge sync service endpoints:</span></span>

  - `https://edge-enterprise.activity.windows.com`
  - `https://edge.activity.windows.com`

- <span data-ttu-id="91a15-131">Azure 信息保护终结点：</span><span class="sxs-lookup"><span data-stu-id="91a15-131">Azure Information Protection endpoints:</span></span>

  - `https://api.aadrm.com` <span data-ttu-id="91a15-132">（针对大多数租户）</span><span class="sxs-lookup"><span data-stu-id="91a15-132">(for most tenants)</span></span>
  - `https://api.aadrm.de` <span data-ttu-id="91a15-133">（针对德国租户）</span><span class="sxs-lookup"><span data-stu-id="91a15-133">(for tenants in Germany)</span></span>
  - `https://api.aadrm.cn` <span data-ttu-id="91a15-134">（针对中国租户）</span><span class="sxs-lookup"><span data-stu-id="91a15-134">(for tenants in China)</span></span>

- [<span data-ttu-id="91a15-135">Windows 通知服务终结点</span><span class="sxs-lookup"><span data-stu-id="91a15-135">Windows Notification Service endpoints</span></span>](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)

## <span data-ttu-id="91a15-136">其他浏览器支持服务</span><span class="sxs-lookup"><span data-stu-id="91a15-136">Other browser support services</span></span>

<span data-ttu-id="91a15-137">提供浏览器功能的元数据，如跟踪保护、证书吊销列表和其他浏览器组件更新。</span><span class="sxs-lookup"><span data-stu-id="91a15-137">Provide metadata for browser features such as tracking protection, certificate revocation lists, and other browser component updates.</span></span> <span data-ttu-id="91a15-138">提供可下载的拼写检查字典和广告屏蔽阻止名单。</span><span class="sxs-lookup"><span data-stu-id="91a15-138">Provide downloadable spellcheck dictionaries and ad-blocking block lists.</span></span> <span data-ttu-id="91a15-139">提供服务以支持诸如集合、自动填充和扩展存储等浏览器功能。</span><span class="sxs-lookup"><span data-stu-id="91a15-139">Provide services to support browser features such as collections, autofill, and extension store.</span></span>

- `http://edge.microsoft.com/`
- `https://edge.microsoft.com/`

## <span data-ttu-id="91a15-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91a15-140">See also</span></span>

- [<span data-ttu-id="91a15-141">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="91a15-141">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="91a15-142">Microsoft Edge 文档登录页面</span><span class="sxs-lookup"><span data-stu-id="91a15-142">Microsoft Edge documentation landing page</span></span>](https://docs.microsoft.com/DeployEdge/)
- [<span data-ttu-id="91a15-143">管理 Windows 10 企业版版本 1903 的连接终结点</span><span class="sxs-lookup"><span data-stu-id="91a15-143">Manage connection endpoints for Windows 10 Enterprise, version 1903</span></span>](https://docs.microsoft.com/windows/privacy/manage-windows-1903-endpoints)
