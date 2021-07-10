---
title: 企业新选项卡页面的向后兼容性
ms.author: ruchir
author: dan-wesley
manager: vwehren
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 企业新选项卡页面的向后兼容性
ms.openlocfilehash: e2534f9df82aa81843d7cd292ada99a4c7574a3c
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642078"
---
# <a name="backwards-compatibility-for-the-enterprise-new-tab-page"></a><span data-ttu-id="52e9b-103">企业新选项卡页面的向后兼容性</span><span class="sxs-lookup"><span data-stu-id="52e9b-103">Backwards compatibility for the Enterprise New tab page</span></span>

<span data-ttu-id="52e9b-104">本文介绍了新选项卡页面所做的更改，以及用户向后兼容 Microsoft Edge 87 版本及更低版本的情况。</span><span class="sxs-lookup"><span data-stu-id="52e9b-104">This article describes the change to the New tab page and how users can be backwards compatible with Microsoft Edge version 87 and earlier.</span></span>

> [!NOTE]
> <span data-ttu-id="52e9b-105">本文适用于 Microsoft Edge 版本 87 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="52e9b-105">This article applies to Microsoft Edge version 87 or later.</span></span>

## <a name="information-feeds-from-single-endpoint"></a><span data-ttu-id="52e9b-106">来自单个终端的信息源</span><span class="sxs-lookup"><span data-stu-id="52e9b-106">Information feeds from single endpoint</span></span>

<span data-ttu-id="52e9b-107">新版本的企业新选项卡页面结合了合规的 Microsoft 365 内容以及通过 MSN.com 终端点提供的符合行业的和合规的信息源。</span><span class="sxs-lookup"><span data-stu-id="52e9b-107">The new version of the Enterprise New tab page combines compliant Microsoft 365 content with industry relevant and compliant information feeds that are served via the MSN.com endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="52e9b-108">Office 365 的内容最初是使用 [Office.com](https://www.office.com) 域提供服务的。</span><span class="sxs-lookup"><span data-stu-id="52e9b-108">Office 365 content was originally served using the [Office.com](https://www.office.com) domain.</span></span>

<span data-ttu-id="52e9b-109">如果你的组织对 MSN.com 域的访问收到了限制，我们强烈建议授予用户访问此 [url](https://ntp.msn.com)的权限。</span><span class="sxs-lookup"><span data-stu-id="52e9b-109">If access to the MSN.com domain is restricted for your organization, we strongly recommend giving users access to this [url](https://ntp.msn.com).</span></span>

<span data-ttu-id="52e9b-110">如果需要更多时间来启用对 MSN 域的访问，我们建议使用 [NewTabPageSetFeedType](./microsoft-edge-policies.md#newtabpagesetfeedtype)，以便为新的选项卡页面选择 Microsoft 新闻或 Office 365 源体验。</span><span class="sxs-lookup"><span data-stu-id="52e9b-110">If you need more time to enable access to the MSN domain, we recommend using the [NewTabPageSetFeedType](./microsoft-edge-policies.md#newtabpagesetfeedtype), that lets you choose either the Microsoft News or Office 365 feed experience for the new tab page.</span></span>

### <a name="keep-using-officecom"></a><span data-ttu-id="52e9b-111">继续使用 Office.com</span><span class="sxs-lookup"><span data-stu-id="52e9b-111">Keep using Office.com</span></span>

 <span data-ttu-id="52e9b-112">可配置 **NewTabPageSetFeedType** 策略，以继续使用已弃用的 Office.com 域。</span><span class="sxs-lookup"><span data-stu-id="52e9b-112">You can configure the **NewTabPageSetFeedType** policy to keep using the deprecated Office.com domain.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52e9b-113">当Microsoft Edge 90 版本发布时，**NewTabPageSetFeedType** 策略和服务于 Office 365 内容的 Office.com 域将退出工作。</span><span class="sxs-lookup"><span data-stu-id="52e9b-113">The **NewTabPageSetFeedType** policy and the Office.com domain that serves Office 365 content will quit working when Microsoft Edge version 90 is released.</span></span>

<span data-ttu-id="52e9b-114">以下策略设置将强制企业新建选项卡页面渲染来自 Office.com 域的 Office 文档内容。</span><span class="sxs-lookup"><span data-stu-id="52e9b-114">The following policy settings will force the Enterprise New tab page to render Office document content from the Office.com domain.</span></span>

- <span data-ttu-id="52e9b-115">将策略设置为 **强制**。</span><span class="sxs-lookup"><span data-stu-id="52e9b-115">Set the policy as **Mandatory**.</span></span>
- <span data-ttu-id="52e9b-116">设置策略映射的值为 **Office（1）= Office 365 源体验**。</span><span class="sxs-lookup"><span data-stu-id="52e9b-116">Set the value of the policy mapping to **Office (1) = Office 365 feed experience**.</span></span>

<span data-ttu-id="52e9b-117">如果无法切换到 Office.com，请转向联系我们并给我们发送反馈。</span><span class="sxs-lookup"><span data-stu-id="52e9b-117">If the switch to the Office.com isn't possible, reach out and send us feedback.</span></span> <span data-ttu-id="52e9b-118">另一种选择是配置 [NewTabPageLocation](./microsoft-edge-policies.md#newtabpagelocation) ，使其指向组织所允许的端点 URL。</span><span class="sxs-lookup"><span data-stu-id="52e9b-118">Another option is to configure the [NewTabPageLocation](./microsoft-edge-policies.md#newtabpagelocation) so it points to an endpoint URL that's allowed by your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="52e9b-119">如果同时还配置了 **NewTabPageSetFeedType** 策略，则 **NewTabPageLocation** 策略具有优先权。</span><span class="sxs-lookup"><span data-stu-id="52e9b-119">The **NewTabPageLocation** policy has precedence if the **NewTabPageSetFeedType** policy is also configured.</span></span>

## <a name="enterprise-users-will-now-get-microsoft-news-content-via-my-feed"></a><span data-ttu-id="52e9b-120">现在，企业用户将通过我的源来获取 Microsoft 新闻内容</span><span class="sxs-lookup"><span data-stu-id="52e9b-120">Enterprise users will now get Microsoft news content via My Feed</span></span>

<span data-ttu-id="52e9b-121">企业新选项卡页面将在 **我的源** 和 Office 365 内容中为使用Azure Active Directory （Azure AD）帐户登录的用户提供单一视图中的行业相关信息。</span><span class="sxs-lookup"><span data-stu-id="52e9b-121">The Enterprise New tab page will offer industry relevant information in **My Feed** and Office 365 content in a single view for users signed in with their Azure Active Directory (Azure AD) account.</span></span> <span data-ttu-id="52e9b-122">对于使用其 Azure Active Directory （Azure AD）登录并在设置浮出控件中选择了 Microsoft 资讯选项的用户，其新的选项卡页面视图将替换为 **我的源** 内容。</span><span class="sxs-lookup"><span data-stu-id="52e9b-122">For users signed in with their Azure Active Directory (Azure AD) who selected the Microsoft News option in the settings flyout, their new tab page view will be replaced with **My Feed** content.</span></span> <span data-ttu-id="52e9b-123">当用户在浏览器中打开一个新的选项卡页面时，其外观将与下一屏幕截图中的示例一样。。</span><span class="sxs-lookup"><span data-stu-id="52e9b-123">When they open a new tab page in the browser it will look like the example in the next screenshot.</span></span>

![新选项卡页面显示我的源的内容。](media/microsoft-edge-ntp-backward-compatibility/microsoft-edge-ntp-myfeed-view.png)

> [!NOTE]
> <span data-ttu-id="52e9b-125">未使用 Azure AD 登录的用户将在打开新选项卡时继续看到 MSN 新闻源。</span><span class="sxs-lookup"><span data-stu-id="52e9b-125">Users who aren't signed in with Azure AD will continue to see the MSN News feed when they open a new tab.</span></span>

## <a name="page-layout"></a><span data-ttu-id="52e9b-126">页面布局</span><span class="sxs-lookup"><span data-stu-id="52e9b-126">Page layout</span></span>

<span data-ttu-id="52e9b-127">随着新选项卡页面的变化，页面布局不再需要控制两种特定的内容类型（Office 365和Microsoft 资讯），因此内容切换无法使用。</span><span class="sxs-lookup"><span data-stu-id="52e9b-127">With the changes to the New tab page, the Page layout no longer has to control two specific content types (Office 365 and Microsoft News), so the content toggle isn't available.</span></span> <span data-ttu-id="52e9b-128">下一张屏幕截图将显示页面布局的浮出控件。</span><span class="sxs-lookup"><span data-stu-id="52e9b-128">The next screenshot shows the flyout for the Page layout.</span></span>

![新选项卡页面的页面布局视图。](media/microsoft-edge-ntp-backward-compatibility/microsoft-edge-ntp-page-layout.png)

<span data-ttu-id="52e9b-130">如果想要继续访问未绑定到组织的 Microsoft 资讯内容，则必须使用其他浏览器配置文件。</span><span class="sxs-lookup"><span data-stu-id="52e9b-130">If you want to keep accessing Microsoft News content that isn't tied to your organization, you must use a different browser profile.</span></span> <span data-ttu-id="52e9b-131">转到  *edge://settings/profiles* 并注销你的 Azure AD 配置文件。</span><span class="sxs-lookup"><span data-stu-id="52e9b-131">Go to  *edge://settings/profiles* and sign out of your Azure AD profile.</span></span> <span data-ttu-id="52e9b-132">此操作将调出企业新选项卡页面的标准视图。</span><span class="sxs-lookup"><span data-stu-id="52e9b-132">This action will bring up the  standard view for the Enterprise new tab page.</span></span> 

## <a name="see-also"></a><span data-ttu-id="52e9b-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52e9b-133">See also</span></span>

- [<span data-ttu-id="52e9b-134">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="52e9b-134">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="52e9b-135">适用于 Internet Explorer 11 的企业模式</span><span class="sxs-lookup"><span data-stu-id="52e9b-135">Enterprise Mode for Internet Explorer 11</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)