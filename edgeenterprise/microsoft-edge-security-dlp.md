---
title: Microsoft Edge 中的数据丢失防护
ms.author: archandr
author: dan-wesley
manager: seanlynd
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 中的数据丢失防护 (DLP)
ms.openlocfilehash: 8c7906f69f8d1161b47aa381bc04bcdaa70fe6cd
ms.sourcegitcommit: c290b0b0fa6b7d7f94dcdfdda91302da733326ec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314555"
---
# <span data-ttu-id="d2d1c-103">Microsoft Edge 中的数据丢失防护 (DLP)</span><span class="sxs-lookup"><span data-stu-id="d2d1c-103">Data Loss Prevention (DLP) in Microsoft Edge</span></span>

<span data-ttu-id="d2d1c-104">数据丢失防护（DLP）是一套识别和保护企业敏感数据免受未经授权即泄露的技术系统。</span><span class="sxs-lookup"><span data-stu-id="d2d1c-104">Data loss prevention (DLP) is a system of technologies that identify and safeguard sensitive enterprise data from unauthorized disclosure.</span></span> <span data-ttu-id="d2d1c-105">为遵守商业标准和行业法规，组织必须保护敏感信息，防止其未经授权的泄露。</span><span class="sxs-lookup"><span data-stu-id="d2d1c-105">To comply with business standards and industry regulations, organizations must protect sensitive information and prevent its unauthorized disclosure.</span></span> <span data-ttu-id="d2d1c-106">敏感信息包括财务数据或个人身份信息（PII），例如信用卡号码、社会保险号码或健康记录等。</span><span class="sxs-lookup"><span data-stu-id="d2d1c-106">Sensitive information includes financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records, among many other things.</span></span>

<span data-ttu-id="d2d1c-107">远程工作更加强调使用DLP。</span><span class="sxs-lookup"><span data-stu-id="d2d1c-107">Remote work has increased the emphasis on using DLP.</span></span> <span data-ttu-id="d2d1c-108">随着个人与工作活动在设备上的使用的增加，企业发现在工作场所之外未经授权共享企业数据的风险亦正在增加。</span><span class="sxs-lookup"><span data-stu-id="d2d1c-108">With the growing use of personal and work activities on devices, enterprises are seeing an increased risk of unauthorized sharing of corporate data outside the workplace.</span></span>

<span data-ttu-id="d2d1c-109">这种用户活动的融合也扩散到了设备上，数据通过各种公共和私有网络在个人和企业设备之间移动。</span><span class="sxs-lookup"><span data-stu-id="d2d1c-109">This blending of user activities has spread to devices as well, where data is moved between personal and corporate devices over a variety of public and private networks.</span></span> <span data-ttu-id="d2d1c-110">最终的结果是敏感数据暴露的风险大大增加。</span><span class="sxs-lookup"><span data-stu-id="d2d1c-110">The net result is a dramatically increased risk of exposing sensitive data.</span></span>

<span data-ttu-id="d2d1c-111">Microsoft Edge 原身支持两种不同的DLP解决方案，即Microsoft Endpoint DLP和Windows信息保护（WIP）。</span><span class="sxs-lookup"><span data-stu-id="d2d1c-111">Microsoft Edge natively supports two different DLP solutions, Microsoft Endpoint DLP and Windows Information Protection (WIP).</span></span>

## <span data-ttu-id="d2d1c-112">使用 Microsoft 终结点数据丢失防护（终结点 DLP）</span><span class="sxs-lookup"><span data-stu-id="d2d1c-112">Microsoft Endpoint data loss prevention (Endpoint DLP)</span></span>

<span data-ttu-id="d2d1c-113">Microsoft 终结点 DLP 是运用现代概念（例如以数据为中心的保护）的下一代数据丢失防护。</span><span class="sxs-lookup"><span data-stu-id="d2d1c-113">Microsoft Endpoint DLP is the next generation of data loss prevention using modern concepts such as data-centric protection.</span></span> <span data-ttu-id="d2d1c-114">它内置在 Windows 10 和 Microsoft Edge 中，因此无需在设备上具备其他代理或插件。</span><span class="sxs-lookup"><span data-stu-id="d2d1c-114">It's built-in to Windows 10 and Microsoft Edge so it doesn't need additional agents or plugins on the device.</span></span>

> [!NOTE]
> <span data-ttu-id="d2d1c-115">这适用于 Microsoft Edge 85 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d2d1c-115">This applies to Microsoft Edge version 85 or later.</span></span>

<span data-ttu-id="d2d1c-116">若要了解有关终结点 DLP 的更多信息，请使用以下资源：</span><span class="sxs-lookup"><span data-stu-id="d2d1c-116">To learn more about Endpoint DLP, use the following resources:</span></span>

- [<span data-ttu-id="d2d1c-117">视频：Microsoft Edge 和数据丢失防护 (DLP)</span><span class="sxs-lookup"><span data-stu-id="d2d1c-117">Video: Microsoft Edge and Data loss prevention (DLP)</span></span>](microsoft-edge-video-security-dlp.md)
- [<span data-ttu-id="d2d1c-118">了解 Microsoft 365 终结点数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="d2d1c-118">Learn about Microsoft 365 Endpoint data loss prevention</span></span>](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide&preserve-view=true)
- [<span data-ttu-id="d2d1c-119">终结点数据丢失防护入门</span><span class="sxs-lookup"><span data-stu-id="d2d1c-119">Get started with Endpoint data loss prevention</span></span>](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-getting-started?view=o365-worldwide&preserve-view=true)

<span data-ttu-id="d2d1c-120">Microsoft Edge 对敏感文件执行管理员配置的策略，并记录不合规活动的审核事件。</span><span class="sxs-lookup"><span data-stu-id="d2d1c-120">Microsoft Edge enforces admin configured policies for sensitive files and records audit events for non-compliant activities.</span></span>

<span data-ttu-id="d2d1c-121">可在运行 Windows 10 的设备上审核和管理的用户活动包括以下活动：</span><span class="sxs-lookup"><span data-stu-id="d2d1c-121">Some of the user activities that you can audit and manage on devices running Windows 10 include the following activities:</span></span>

- <span data-ttu-id="d2d1c-122">文件上传：保护敏感文件上传到未经授权的云端位置。</span><span class="sxs-lookup"><span data-stu-id="d2d1c-122">File Upload: Protect sensitive file upload to unauthorized cloud locations.</span></span> <!-- The next 3 screenshots show a sequence where a user tries to drop a sensitive data file on to their local storage.-->
- <span data-ttu-id="d2d1c-123">剪贴板保护：防止从文件中复制敏感数据。</span><span class="sxs-lookup"><span data-stu-id="d2d1c-123">Clipboard Protection: Protect sensitive data from being copied out of the file.</span></span>
- <span data-ttu-id="d2d1c-124">打印保护：防止打印敏感文件。</span><span class="sxs-lookup"><span data-stu-id="d2d1c-124">Print Protection: Protect sensitive file from being printed.</span></span>
- <span data-ttu-id="d2d1c-125">保存到 USB/网络：防止可移动 USB 存储或未经授权的网络位置保存敏感文件。</span><span class="sxs-lookup"><span data-stu-id="d2d1c-125">Save to USB/Network: Protect sensitive file from being saved to removable USB storage or unauthorized network locations.</span></span>

<span data-ttu-id="d2d1c-126">有关可供审核和管理的用户活动的更多详细信息，请参阅[可监视并执行操作的端点活动](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide#endpoint-activities-you-can-monitor-and-take-action-on&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="d2d1c-126">For more detailed information about user activities you can audit and manage, see [Endpoint activities you can monitor and take action on](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide#endpoint-activities-you-can-monitor-and-take-action-on&preserve-view=true).</span></span>

## <span data-ttu-id="d2d1c-127">Windows 信息保护</span><span class="sxs-lookup"><span data-stu-id="d2d1c-127">Windows Information Protection</span></span>

<span data-ttu-id="d2d1c-128">查看 [对 Windows 信息保护](https://docs.microsoft.com/deployedge/microsoft-edge-security-windows-information-protection)的支持，其描述了 Microsoft Edge 支持 Windows 信息保护（WIP）的方式。</span><span class="sxs-lookup"><span data-stu-id="d2d1c-128">Check out [Support for Windows Information Protection](https://docs.microsoft.com/deployedge/microsoft-edge-security-windows-information-protection), which describes how Microsoft Edge supports Windows Information Protection (WIP).</span></span> <span data-ttu-id="d2d1c-129">可在以下部分中了解系统要求、优点及支持的功能：</span><span class="sxs-lookup"><span data-stu-id="d2d1c-129">You can learn moe about system requirements, benefits, and supported features in the following sections:</span></span>

- [<span data-ttu-id="d2d1c-130">系统要求</span><span class="sxs-lookup"><span data-stu-id="d2d1c-130">System Requirements</span></span>](https://docs.microsoft.com/deployedge/:microsoft-edge-security-windows-information-protection#system-requirements)
- [<span data-ttu-id="d2d1c-131">Windows信息保护的优势</span><span class="sxs-lookup"><span data-stu-id="d2d1c-131">Windows Information Protection Benefits</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-security-windows-information-protection#windows-information-protection-benefits)
- [<span data-ttu-id="d2d1c-132">Microsoft Edge 支持的 WIP 功能</span><span class="sxs-lookup"><span data-stu-id="d2d1c-132">WIP features supported in Microsoft Edge</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-information-protection#wip-features-supported-in-microsoft-edge)

## <span data-ttu-id="d2d1c-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2d1c-133">See also</span></span>

- [<span data-ttu-id="d2d1c-134">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="d2d1c-134">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="d2d1c-135">视频：数据丢失防护 - Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d2d1c-135">Video: Data loss prevention - Microsoft Edge</span></span>](https://www.youtube.com/watch?v=dLD04U9eTqg)
- [<span data-ttu-id="d2d1c-136">防止数据丢失概述</span><span class="sxs-lookup"><span data-stu-id="d2d1c-136">Overview of data loss prevention</span></span>](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide&preserve-view=true)
- [<span data-ttu-id="d2d1c-137">使用 Windows 信息保护系统来保护企业数据</span><span class="sxs-lookup"><span data-stu-id="d2d1c-137">Protect your enterprise data using Windows Information Protection</span></span>](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)
