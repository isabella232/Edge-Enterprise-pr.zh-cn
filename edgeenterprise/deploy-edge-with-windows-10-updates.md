---
title: 使用 Windows 10 更新部署 Microsoft Edge
ms.author: ryhecht
author: RyanHechtMSFT
manager: tinad
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 使用 Windows 10 更新部署 Microsoft Edge
ms.openlocfilehash: c8ea65f6c452b52b01c00d8fca418fe59db801b1
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447376"
---
# <a name="deploy-microsoft-edge-with-windows-10-updates"></a><span data-ttu-id="efc7f-103">使用 Windows 10 更新部署 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="efc7f-103">Deploy Microsoft Edge with Windows 10 updates</span></span>

<span data-ttu-id="efc7f-104">本文为使用 Windows 10 更新部署 Microsoft Edge 的用户提供了相关信息。</span><span class="sxs-lookup"><span data-stu-id="efc7f-104">The article provides information for users who are deploying Microsoft Edge by using Windows 10 updates.</span></span>

## <a name="for-windows-10-release-20h2"></a><span data-ttu-id="efc7f-105">对于 Windows 10 版本 20H2</span><span class="sxs-lookup"><span data-stu-id="efc7f-105">For Windows 10 release 20H2</span></span>

<span data-ttu-id="efc7f-106">Windows 10 版本 20H2 已将 Microsoft Edge 安装为其默认浏览器。</span><span class="sxs-lookup"><span data-stu-id="efc7f-106">Windows 10 version 20H2 already has Microsoft Edge installed as its default browser.</span></span>

## <a name="for-windows-10-releases-rs4-through-20h1"></a><span data-ttu-id="efc7f-107">适用于 Windows 10 版本 RS4 至 20H1</span><span class="sxs-lookup"><span data-stu-id="efc7f-107">For Windows 10 releases RS4 through 20H1</span></span>

<span data-ttu-id="efc7f-108">Windows Server Update Services (WSUS) 拥有每个 Windows 10 版本（从 RS4 至 20H1）的更新，这将删除 Microsoft Edge 旧版桌面应用并将其替换为 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="efc7f-108">Windows Server Update Services (WSUS) has updates for each version of Windows 10 from RS4 through 20H1 that will remove the Microsoft Edge Legacy desktop app and replace it with Microsoft Edge.</span></span> <span data-ttu-id="efc7f-109">有关更多信息，请参阅[此支持文章](https://support.microsoft.com/topic/update-in-wsus-for-the-new-microsoft-edge-for-windows-10-version-1809-1903-1909-and-2004-october-29-2020-b4980418-4ec4-dee7-3b17-1c6499bd127c)，以了解适合于你的 Windows 版本的 WSUS 更新。</span><span class="sxs-lookup"><span data-stu-id="efc7f-109">For more information, see [this support article](https://support.microsoft.com/topic/update-in-wsus-for-the-new-microsoft-edge-for-windows-10-version-1809-1903-1909-and-2004-october-29-2020-b4980418-4ec4-dee7-3b17-1c6499bd127c) to find out which WSUS update is right for your Windows version.</span></span>

## <a name="for-windows-10-releases-prior-to-rs4-and-windows-7-81-and-earlier"></a><span data-ttu-id="efc7f-110">对于 RS4 之前的 Windows 10 版本（以及 Windows 7、8.1 及更早版本）</span><span class="sxs-lookup"><span data-stu-id="efc7f-110">For Windows 10 releases prior to RS4 (and Windows 7, 8.1, and earlier)</span></span>

<span data-ttu-id="efc7f-111">安装 Microsoft Edge 的 Windows 更新对这些版本不可用。</span><span class="sxs-lookup"><span data-stu-id="efc7f-111">Windows updates to install Microsoft Edge aren't available for these versions.</span></span> <span data-ttu-id="efc7f-112">请考虑其他将 Microsoft Edge 部署到这些设备的选项，例如[配置管理器](/configmgr/apps/deploy-use/deploy-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)或 [Intune](/intune/apps/apps-windows-edge/?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)。</span><span class="sxs-lookup"><span data-stu-id="efc7f-112">Consider other options for deploying Microsoft Edge to these devices such as [Configuration Manager](/configmgr/apps/deploy-use/deploy-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json) or [Intune](/intune/apps/apps-windows-edge/?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json).</span></span>

## <a name="see-also"></a><span data-ttu-id="efc7f-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="efc7f-113">See also</span></span>

- [<span data-ttu-id="efc7f-114">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="efc7f-114">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="efc7f-115">规划 Microsoft Edge 部署</span><span class="sxs-lookup"><span data-stu-id="efc7f-115">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)