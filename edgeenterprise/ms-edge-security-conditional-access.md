---
title: Microsoft Edge 和条件访问
ms.author: srugh
author: srugh
manager: seanlyn
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 和条件访问
ms.openlocfilehash: 27d93627f8a86ad821a00d6d78b7db352e9e557a
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642848"
---
# <a name="microsoft-edge-and-conditional-access"></a><span data-ttu-id="21796-103">Microsoft Edge 和条件访问</span><span class="sxs-lookup"><span data-stu-id="21796-103">Microsoft Edge and Conditional Access</span></span>
  
<span data-ttu-id="21796-104">本文介绍 Microsoft Edge 如何支持条件访问，以及如何访问受条件访问保护的资源。</span><span class="sxs-lookup"><span data-stu-id="21796-104">This article describes how Microsoft Edge supports Conditional Access, and how to access resources protected by Conditional Access.</span></span>

> [!NOTE]
> <span data-ttu-id="21796-105">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="21796-105">This article applies to Microsoft Edge version 77 or later.</span></span>

<span data-ttu-id="21796-106">就管理云资源而言，身份和访问权限是云安全的一个重要方面。</span><span class="sxs-lookup"><span data-stu-id="21796-106">A key aspect of cloud security is identity and access when it comes to managing your cloud resources.</span></span> <span data-ttu-id="21796-107">在移动优先、云优先的世界中，用户可以从任何地方使用各种设备和应用来访问组织的资源。</span><span class="sxs-lookup"><span data-stu-id="21796-107">In a mobile-first, cloud-first world, users can access your organization's resources using a variety of devices and apps from anywhere.</span></span> <span data-ttu-id="21796-108">因此，仅关注谁可以访问资源是不够的。</span><span class="sxs-lookup"><span data-stu-id="21796-108">As a result of this, just focusing on who can access a resource is not sufficient.</span></span> <span data-ttu-id="21796-109">你还需要考虑访问资源的方式。</span><span class="sxs-lookup"><span data-stu-id="21796-109">You also need to factor in how a resource is accessed.</span></span> <span data-ttu-id="21796-110">Azure Active Directory (Azure AD) 条件访问可帮助你掌握安全性和工作效率之间的平衡。</span><span class="sxs-lookup"><span data-stu-id="21796-110">Azure Active Directory (Azure AD) Conditional Access helps you master the balance between security and productivity.</span></span>

## <a name="accessing-conditional-access-protected-resources-in-microsoft-edge"></a><span data-ttu-id="21796-111">在 Microsoft Edge 中访问受条件访问保护的资源</span><span class="sxs-lookup"><span data-stu-id="21796-111">Accessing Conditional Access protected resources in Microsoft Edge</span></span>

<span data-ttu-id="21796-112">Microsoft Edge 本身支持 Azure AD 条件访问。</span><span class="sxs-lookup"><span data-stu-id="21796-112">Microsoft Edge natively supports Azure AD Conditional Access.</span></span> <span data-ttu-id="21796-113">无需安装单独的扩展。</span><span class="sxs-lookup"><span data-stu-id="21796-113">There's no need to install a separate extension.</span></span> <span data-ttu-id="21796-114">如果你使用企业 Azure AD凭据登录 Microsoft Edge 配置文件，Microsoft Edge 允许无缝访问受条件访问保护的企业云资源。</span><span class="sxs-lookup"><span data-stu-id="21796-114">When you're signed into a Microsoft Edge profile with enterprise Azure AD credentials, Microsoft Edge allows seamless access to enterprise cloud resources protected using Conditional Access.</span></span>

<span data-ttu-id="21796-115">在符合标准的设备上，访问资源的标识应与配置文件上的标识匹配。</span><span class="sxs-lookup"><span data-stu-id="21796-115">On a compliant device, the identity accessing the resource should match the identity on the profile.</span></span>  <span data-ttu-id="21796-116">如果不匹配，你将看到类似于下一张屏幕截图中的消息。</span><span class="sxs-lookup"><span data-stu-id="21796-116">If it doesn't, you'll see a message like the one in the next screenshot.</span></span> <span data-ttu-id="21796-117">在屏幕截图示例中，“testadmin@evostsoneboxtest.com”是访问资源所需的登录帐户。</span><span class="sxs-lookup"><span data-stu-id="21796-117">In the screenshot example, "testadmin@evostsoneboxtest.com" is the sign-in account needed to access the resource.</span></span>

![浏览器中的条件访问消息](./media/edge-security/microsoft-edge-security-conditional-access.png)

<span data-ttu-id="21796-119">若要继续，你必须切换到所需配置文件（如果有）或者创建具有匹配标识的配置文件。</span><span class="sxs-lookup"><span data-stu-id="21796-119">To continue, you have to switch to the required profile (if you have one) or create a profile with matching identity.</span></span>

<span data-ttu-id="21796-120">若要登录并使用你的配置文件，请单击浏览器右上角的用户头像。</span><span class="sxs-lookup"><span data-stu-id="21796-120">To sign in and work with your profile, click the account picture in the top right corner of the browser.</span></span> <span data-ttu-id="21796-121">可以使用下拉菜单执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="21796-121">You can use the dropdown menu to:</span></span>

- <span data-ttu-id="21796-122">选择其他配置文件。</span><span class="sxs-lookup"><span data-stu-id="21796-122">Select another profile.</span></span> <span data-ttu-id="21796-123">单击配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="21796-123">Click the profile name.</span></span>
- <span data-ttu-id="21796-124">创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="21796-124">Create a profile.</span></span> <span data-ttu-id="21796-125">单击**添加配置文件**。</span><span class="sxs-lookup"><span data-stu-id="21796-125">Click **Add a profile**.</span></span>
- <span data-ttu-id="21796-126">管理你的配置文件。</span><span class="sxs-lookup"><span data-stu-id="21796-126">Manage your profiles.</span></span> <span data-ttu-id="21796-127">单击**管理配置文件设置**。</span><span class="sxs-lookup"><span data-stu-id="21796-127">Click **Manage profile settings**.</span></span>

<span data-ttu-id="21796-128">所有平台（包括所有受支持的 Windows 和 macOS 版本）上均提供此支持。</span><span class="sxs-lookup"><span data-stu-id="21796-128">This support is available across all platforms, including all supported versions of Windows and macOS.</span></span>

### <a name="how-to-deploy-conditional-access-in-azure-active-directory"></a><span data-ttu-id="21796-129">如何在 Azure Active Directory 中部署条件访问</span><span class="sxs-lookup"><span data-stu-id="21796-129">How to deploy Conditional Access in Azure Active Directory</span></span>

<span data-ttu-id="21796-130">[部署条件访问](/azure/active-directory/conditional-access/plan-conditional-access)提供了有助于在 Azure Active Directory 中部署条件访问的详细指南。</span><span class="sxs-lookup"><span data-stu-id="21796-130">[Deploy Conditional Access](/azure/active-directory/conditional-access/plan-conditional-access) provides a detailed guide to help deploy Conditional Access in Azure Active Directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="21796-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21796-131">See also</span></span>

- [<span data-ttu-id="21796-132">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="21796-132">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="21796-133">视频: 安全性、兼容性和可管理性</span><span class="sxs-lookup"><span data-stu-id="21796-133">Video: Security, compatibility, and manageability</span></span>](/microsoft-edge-video-security-compatibility-manageability.md)