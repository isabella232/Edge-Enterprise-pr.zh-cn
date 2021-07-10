---
title: 你的环境中的 Microsoft Edge
ms.author: ryhecht
author: RyanHechtMSFT
manager: tinad
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 你的环境中的 Microsoft Edge
ms.openlocfilehash: 2381380cb399f6a1fbb5efa9378ffeba20fa774f
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641598"
---
# <a name="microsoft-edge-in-your-environment"></a><span data-ttu-id="a3bf5-103">你的环境中的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a3bf5-103">Microsoft Edge in your environment</span></span>

<span data-ttu-id="a3bf5-104">本文介绍了当 Microsoft Edge 旧版达到其服务寿命时如何为部署 Microsoft Edge 做好准备。</span><span class="sxs-lookup"><span data-stu-id="a3bf5-104">This article describes how to prepare to deploy Microsoft Edge when Microsoft Edge Legacy reaches its end of service.</span></span>

<span data-ttu-id="a3bf5-105">根据 Microsoft Edge 产品团队的[博客文章](https://aka.ms/EdgeLegacyEOS)，对 Microsoft Edge 旧版桌面应用程序的支持将在 2021 年 3 月 9 日结束。</span><span class="sxs-lookup"><span data-stu-id="a3bf5-105">As per the Microsoft Edge Product Team’s [blog post](https://aka.ms/EdgeLegacyEOS), support for the Microsoft Edge Legacy desktop application will end on March 9, 2021.</span></span> <span data-ttu-id="a3bf5-106">当你在 4 月应用星期二更新（或“B”）时，它会将 Microsoft Edge 旧版从运行 Windows 10 RS4 至 20H1 的设备上删除，并将其替换为 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="a3bf5-106">When you apply the Update Tuesday (or "B") release in April, it will remove Microsoft Edge Legacy from devices running Windows 10 RS4 through 20H1 and replace it with Microsoft Edge.</span></span>

## <a name="how-to-prepare"></a><span data-ttu-id="a3bf5-107">如何准备</span><span class="sxs-lookup"><span data-stu-id="a3bf5-107">How to Prepare</span></span>

<span data-ttu-id="a3bf5-108">若要准备通过 4 月的星期二更新将 Microsoft Edge 安装到 Windows 10 RS4 至 20H1 的设备上，建议阅读[规划部署 Microsoft Edge](deploy-edge-plan-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="a3bf5-108">To prepare for Microsoft Edge being installed on Windows 10 RS4 through 20H1 devices with the Update Tuesday release in April, we recommend reading [Plan your deployment of Microsoft Edge](deploy-edge-plan-deployment.md).</span></span>

<span data-ttu-id="a3bf5-109">规划部署之后，请使用以下其中一种方法准备部署 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="a3bf5-109">After you plan your deployment, use one of the following approaches to prepare to deploy Microsoft Edge.</span></span>

- <span data-ttu-id="a3bf5-110">**安装组策略以自定义 Microsoft Edge 更新方法**。</span><span class="sxs-lookup"><span data-stu-id="a3bf5-110">**Install group policies to customize your Microsoft Edge update approach**.</span></span> <span data-ttu-id="a3bf5-111">有关更多信息，请参阅[在 Windows 上配置 Microsoft Edge 策略设置](configure-microsoft-edge.md)，尤其注意[更新策略参考](microsoft-edge-update-policies.md)材料。</span><span class="sxs-lookup"><span data-stu-id="a3bf5-111">For more information, see [Configure Microsoft Edge policy settings on Windows](configure-microsoft-edge.md), and pay special attention to the [Update Policy reference](microsoft-edge-update-policies.md) material.</span></span> <span data-ttu-id="a3bf5-112">如果在安装 4 月的星期二更新版本之前安装用于管理更新的组策略，则 Microsoft Edge 将立即开始遵守你的策略。</span><span class="sxs-lookup"><span data-stu-id="a3bf5-112">If you install group policies to manage your updates before installing April’s Update Tuesday release, Microsoft Edge will immediately start respecting your policy.</span></span> <span data-ttu-id="a3bf5-113">如果没有安装任何组策略，则 Microsoft Edge 将会自动更新自身。</span><span class="sxs-lookup"><span data-stu-id="a3bf5-113">If there isn't any installed group policy, Microsoft Edge will automatically update itself.</span></span>

- <span data-ttu-id="a3bf5-114">**在 2021 年 3 月 9 日的服务结束日期之前删除 Microsoft Edge 旧版桌面应用程序，并部署 Microsoft Edge**。</span><span class="sxs-lookup"><span data-stu-id="a3bf5-114">**Remove the Microsoft Edge Legacy desktop application before its end of service date of March 9, 2021 and deploy Microsoft Edge**.</span></span> <span data-ttu-id="a3bf5-115">对于 Windows 10 RS4 至 20H1，你可以通过使用 Windows 更新实现此操作。</span><span class="sxs-lookup"><span data-stu-id="a3bf5-115">For Windows 10 RS4 through 20H1, you can do this by using Windows Updates.</span></span> <span data-ttu-id="a3bf5-116">有关详细信息，请参阅[使用 Windows 10 更新部署 Microsoft Edge](deploy-edge-with-windows-10-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="a3bf5-116">For more information, see [Deploy Microsoft Edge with Windows 10 updates](deploy-edge-with-windows-10-updates.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a3bf5-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3bf5-117">See also</span></span>

- [<span data-ttu-id="a3bf5-118">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="a3bf5-118">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="a3bf5-119">规划 Microsoft Edge 部署</span><span class="sxs-lookup"><span data-stu-id="a3bf5-119">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)