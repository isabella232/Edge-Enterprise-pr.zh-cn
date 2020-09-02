---
title: Microsoft Edge 和混合内容下载
ms.author: kele
author: dan-wesley
manager: srugh
ms.date: 04/30/2020
audience: ITPro
ms.topic: procedural
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 和混合内容下载
ms.openlocfilehash: 57da17a8684b97aad88e7837ff9d070f6862357b
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979291"
---
# <span data-ttu-id="dbfb5-103">了解 Microsoft Edge 和混合内容下载</span><span class="sxs-lookup"><span data-stu-id="dbfb5-103">Learn about Microsoft Edge and mixed content downloads</span></span>

<span data-ttu-id="dbfb5-104">本文介绍混合内容下载以及 Microsoft Edge 对此操作的处理方式。</span><span class="sxs-lookup"><span data-stu-id="dbfb5-104">This article explains mixed content downloads and how Microsoft Edge handles them.</span></span>

>[!NOTE]
><span data-ttu-id="dbfb5-105">本文适用于 Microsoft Edge 版本 85 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="dbfb5-105">This article applies to Microsoft Edge version 85 or later.</span></span>

## <span data-ttu-id="dbfb5-106">混合内容下载是什么？</span><span class="sxs-lookup"><span data-stu-id="dbfb5-106">What are mixed content downloads?</span></span>

<span data-ttu-id="dbfb5-107">从通过安全 HTTPS 连接加载的 HTML 页面启动下载时会发生混合内容下载，但存在以下情况之一：</span><span class="sxs-lookup"><span data-stu-id="dbfb5-107">A mixed content download happens when you start a download from an HTML page that was loaded over a secure HTTPS connection, but one of the following conditions exists:</span></span>

- <span data-ttu-id="dbfb5-108">一个或多个下载位置重定向是通过不安全的 HTTP 连接加载的。</span><span class="sxs-lookup"><span data-stu-id="dbfb5-108">One or more of the download location's redirects was loaded over an insecure HTTP connection.</span></span>
- <span data-ttu-id="dbfb5-109">最终下载位置是通过不安全的 HTTP 连接加载的。</span><span class="sxs-lookup"><span data-stu-id="dbfb5-109">The final download location was loaded over an insecure HTTP connection.</span></span>

<span data-ttu-id="dbfb5-110">这两种场景都是混合内容，因为请求是通过安全 HTTPS 发出的，并且最终下载目标同时涉及到 HTTP 和 HTTPS 内容。</span><span class="sxs-lookup"><span data-stu-id="dbfb5-110">Either scenario is a mixed content because the request was made using secure HTTPS and both HTTP and HTTPS content are involved in reaching the final download destination.</span></span> <span data-ttu-id="dbfb5-111">新式浏览器将显示有关此类型内容的警告，向用户表明，即使访问的原始页面是安全的，下载内容也可能是不安全的。</span><span class="sxs-lookup"><span data-stu-id="dbfb5-111">Modern browsers display warnings about this type of content to indicate to the user that this download may be transferred insecurely even though the original page accessed was secure.</span></span>

## <span data-ttu-id="dbfb5-112">下载警告和用户选项</span><span class="sxs-lookup"><span data-stu-id="dbfb5-112">Download warnings and user options</span></span>

<span data-ttu-id="dbfb5-113">下载警告确保用户知道正在下载的文件可能会被网络上的恶意攻击者读取。</span><span class="sxs-lookup"><span data-stu-id="dbfb5-113">The download warning ensures that users know that the file they're downloading could be read by malicious attackers on their network.</span></span> <span data-ttu-id="dbfb5-114">此警告让用户能够在知情的情况下决定是否下载文件。</span><span class="sxs-lookup"><span data-stu-id="dbfb5-114">This warning lets a user make an informed decision on whether to download the file.</span></span>

<span data-ttu-id="dbfb5-115">在 Microsoft Edge 中，混合内容下载将被阻止，但用户可以覆盖并下载文件（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="dbfb5-115">In Microsoft Edge, mixed content downloads will be blocked but users can override and download the file if they want to.</span></span> <span data-ttu-id="dbfb5-116">Microsoft Edge 计划开始阻止混合内容可执行文件下载（从 Microsoft Edge 版本 85 开始），并将在未来版本中阻止不同的文件类型。</span><span class="sxs-lookup"><span data-stu-id="dbfb5-116">Microsoft Edge plans on starting to block mixed content executable file downloads starting with Microsoft Edge version 85 and will block different filetypes in future releases.</span></span>

> [!NOTE]
> <span data-ttu-id="dbfb5-117">此功能部署可能会根据发布计划和用户反馈进行更改。</span><span class="sxs-lookup"><span data-stu-id="dbfb5-117">Deployment of this feature is subject to change based on release schedule and user feedback.</span></span>

<!-- The schedule of the block for different filetypes is to be determined and may be impacted by usage data and user feedback. -->

<span data-ttu-id="dbfb5-118">在下载栏中，阻止警告消息类似于下一屏幕截图中的示例。</span><span class="sxs-lookup"><span data-stu-id="dbfb5-118">In the download shelf, the block warning message looks like the example in the next screenshot.</span></span>

 ![下载任务栏中的混合内容警告](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-tray-warning.png)

<span data-ttu-id="dbfb5-120">在下载页上，阻止警告类似于以下屏幕截图示例：</span><span class="sxs-lookup"><span data-stu-id="dbfb5-120">On the download page, the block warning looks like the following screenshot example:</span></span>

 ![混合内容覆盖提示](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-page-warning.png)

<span data-ttu-id="dbfb5-122">如果用户决定保留下载，系统会提示他们确认操作。</span><span class="sxs-lookup"><span data-stu-id="dbfb5-122">If a user decides to keep the download, they are prompted to confirm their action.</span></span> <span data-ttu-id="dbfb5-123">下一个屏幕截图将显示此确认提示示例。</span><span class="sxs-lookup"><span data-stu-id="dbfb5-123">The next screenshot shows an example of this confirmation prompt.</span></span>

 ![选择 Internet Explorer 模式](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-override.png)

## <span data-ttu-id="dbfb5-125">支持策略</span><span class="sxs-lookup"><span data-stu-id="dbfb5-125">Supporting policies</span></span>

<span data-ttu-id="dbfb5-126">希望从特定网站排除混合内容阻止的企业可使用 [InsecureContentAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#insecurecontentallowedforurls) 策略执行此操作。</span><span class="sxs-lookup"><span data-stu-id="dbfb5-126">Enterprises that want to exclude mixed content blocking from specific websites can use the [InsecureContentAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#insecurecontentallowedforurls) policy to do so.</span></span>

## <span data-ttu-id="dbfb5-127">内容许可证</span><span class="sxs-lookup"><span data-stu-id="dbfb5-127">Content license</span></span>

> [!NOTE]
> <span data-ttu-id="dbfb5-128">本页面的某些部分是根据 Chromium.org 创建和共享的作品所做的修改，并根据 [Creative Commons Attribution 4.0 国际许可证](http://creativecommons.org/licenses/by/4.0/)中所述的条款进行使用。</span><span class="sxs-lookup"><span data-stu-id="dbfb5-128">Portions of this page are modifications based on work created and shared by Chromium.org and used according to terms described in the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).</span></span> <span data-ttu-id="dbfb5-129">可在[此处](https://developers.google.com/web/fundamentals/security/prevent-mixed-content/what-is-mixed-content)找到原始页面。</span><span class="sxs-lookup"><span data-stu-id="dbfb5-129">The original page can be found [here](https://developers.google.com/web/fundamentals/security/prevent-mixed-content/what-is-mixed-content).</span></span>
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /><span data-ttu-id="dbfb5-130">此作品通过 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 国际许可证</a>获得许可。</span><span class="sxs-lookup"><span data-stu-id="dbfb5-130">This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.</span></span>

## <span data-ttu-id="dbfb5-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dbfb5-131">See also</span></span>

- [<span data-ttu-id="dbfb5-132">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="dbfb5-132">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
