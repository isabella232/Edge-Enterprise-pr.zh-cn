---
title: Microsoft Edge 安全概述
ms.author: srugh
author: srugh
manager: seanlyn
ms.date: 04/29/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 安全部署概述
ms.openlocfilehash: f22f2dcbace00cd535d201950c2af488c708525b
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979386"
---
# <span data-ttu-id="4d797-103">Microsoft Edge 安全概述</span><span class="sxs-lookup"><span data-stu-id="4d797-103">Overview of Microsoft Edge security</span></span>
  
<span data-ttu-id="4d797-104">企业中的 IT 管理员在保护公司网络和设备免受恶意攻击并防止未经授权的访问和公司数据泄漏的同时，不断面临着众多现有和新出现的安全挑战。</span><span class="sxs-lookup"><span data-stu-id="4d797-104">IT admins in the enterprise are constantly facing a myriad of existing and emerging security challenges while protecting the corporate network and devices from malicious attacks and preventing unauthorized access and leaks of corporate data.</span></span> <span data-ttu-id="4d797-105">Microsoft Edge 提供了几种固有的内置独特功能，可帮助解决这些难题。</span><span class="sxs-lookup"><span data-stu-id="4d797-105">Microsoft Edge provides several natively built, unique capabilities that help address these challenges.</span></span>

> [!NOTE]
> <span data-ttu-id="4d797-106">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="4d797-106">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="4d797-107">条件访问</span><span class="sxs-lookup"><span data-stu-id="4d797-107">Conditional Access</span></span>

<span data-ttu-id="4d797-108">就管理云资源而言，身份和访问权限是云安全的一个重要方面。</span><span class="sxs-lookup"><span data-stu-id="4d797-108">A key aspect of cloud security is identity and access when it comes to managing your cloud resources.</span></span> <span data-ttu-id="4d797-109">在移动优先、云优先的世界中，用户可以从任何地方使用各种设备和应用来访问组织的资源。</span><span class="sxs-lookup"><span data-stu-id="4d797-109">In a mobile-first, cloud-first world, users can access your organization's resources using a variety of devices and apps from anywhere.</span></span> <span data-ttu-id="4d797-110">因此，仅关注谁可以访问资源是不够的。</span><span class="sxs-lookup"><span data-stu-id="4d797-110">As a result of this, just focusing on who can access a resource is not sufficient.</span></span> <span data-ttu-id="4d797-111">你还需要考虑访问资源的方式。</span><span class="sxs-lookup"><span data-stu-id="4d797-111">You also need to factor in how a resource is accessed.</span></span> <span data-ttu-id="4d797-112">Azure Active Directory (Azure AD) 条件访问可帮助你掌握安全性和工作效率之间的平衡。</span><span class="sxs-lookup"><span data-stu-id="4d797-112">Azure Active Directory (Azure AD) Conditional Access helps you master the balance between security and productivity.</span></span>

### <span data-ttu-id="4d797-113">在 Microsoft Edge 中访问受条件访问保护的资源</span><span class="sxs-lookup"><span data-stu-id="4d797-113">Accessing Conditional Access protected resources in Microsoft Edge</span></span>

<span data-ttu-id="4d797-114">Microsoft Edge 本身支持 Azure AD 条件访问。</span><span class="sxs-lookup"><span data-stu-id="4d797-114">Microsoft Edge natively supports Azure AD Conditional Access.</span></span> <span data-ttu-id="4d797-115">无需安装单独的扩展。</span><span class="sxs-lookup"><span data-stu-id="4d797-115">There's no need to install a separate extension.</span></span> <span data-ttu-id="4d797-116">如果你使用企业 Azure AD凭据登录 Microsoft Edge 配置文件，Microsoft Edge 允许无缝访问受条件访问保护的企业云资源。</span><span class="sxs-lookup"><span data-stu-id="4d797-116">When you're signed into a Microsoft Edge profile with enterprise Azure AD credentials, Microsoft Edge allows seamless access to enterprise cloud resources protected using Conditional Access.</span></span>

<span data-ttu-id="4d797-117">在符合标准的设备上，访问资源的标识应与配置文件上的标识匹配。</span><span class="sxs-lookup"><span data-stu-id="4d797-117">On a compliant device, the identity accessing the resource should match the identity on the profile.</span></span>  <span data-ttu-id="4d797-118">如果不匹配，你将看到类似于下一张屏幕截图中的消息。</span><span class="sxs-lookup"><span data-stu-id="4d797-118">If it doesn't, you'll see a message like the one in the next screenshot.</span></span> <span data-ttu-id="4d797-119">在屏幕截图示例中，“testadmin@evostsoneboxtest.com”是访问资源所需的登录帐户。</span><span class="sxs-lookup"><span data-stu-id="4d797-119">In the screenshot example, "testadmin@evostsoneboxtest.com" is the sign-in account needed to access the resource.</span></span>

![浏览器中的条件访问消息](./media/edge-security/microsoft-edge-security-conditional-access.png)

<span data-ttu-id="4d797-121">若要继续，你必须切换到所需配置文件（如果有）或者创建具有匹配标识的配置文件。</span><span class="sxs-lookup"><span data-stu-id="4d797-121">To continue, you have to switch to the required profile (if you have one) or create a profile with matching identity.</span></span>

<span data-ttu-id="4d797-122">若要登录并使用你的配置文件，请单击浏览器右上角的用户头像。</span><span class="sxs-lookup"><span data-stu-id="4d797-122">To sign in and work with your profile, click the account picture in the top right corner of the browser.</span></span> <span data-ttu-id="4d797-123">可以使用下拉菜单执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4d797-123">You can use the dropdown menu to:</span></span>

- <span data-ttu-id="4d797-124">选择其他配置文件。</span><span class="sxs-lookup"><span data-stu-id="4d797-124">Select another profile.</span></span> <span data-ttu-id="4d797-125">单击配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="4d797-125">Click the profile name.</span></span>
- <span data-ttu-id="4d797-126">创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="4d797-126">Create a profile.</span></span> <span data-ttu-id="4d797-127">单击**添加配置文件**。</span><span class="sxs-lookup"><span data-stu-id="4d797-127">Click **Add a profile**.</span></span>
- <span data-ttu-id="4d797-128">管理你的配置文件。</span><span class="sxs-lookup"><span data-stu-id="4d797-128">Manage your profiles.</span></span> <span data-ttu-id="4d797-129">单击**管理配置文件设置**。</span><span class="sxs-lookup"><span data-stu-id="4d797-129">Click **Manage profile settings**.</span></span>

<span data-ttu-id="4d797-130">所有平台（包括所有受支持的 Windows 和 macOS 版本）上均提供此支持。</span><span class="sxs-lookup"><span data-stu-id="4d797-130">This support is available across all platforms, including all supported versions of Windows and macOS.</span></span>

### <span data-ttu-id="4d797-131">如何在 Azure Active Directory 中部署条件访问</span><span class="sxs-lookup"><span data-stu-id="4d797-131">How to deploy Conditional Access in Azure Active Directory</span></span>

<span data-ttu-id="4d797-132">[部署条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)提供了有助于在 Azure Active Directory 中部署条件访问的详细指南。</span><span class="sxs-lookup"><span data-stu-id="4d797-132">[Deploy Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) provides a detailed guide to help deploy Conditional Access in Azure Active Directory.</span></span>

## <span data-ttu-id="4d797-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d797-133">See also</span></span>

- [<span data-ttu-id="4d797-134">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="4d797-134">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="4d797-135">视频: 安全性、兼容性和可管理性</span><span class="sxs-lookup"><span data-stu-id="4d797-135">Video: Security, compatibility, and manageability</span></span>](/microsoft-edge-video-security-compatibility-manageability.md)
