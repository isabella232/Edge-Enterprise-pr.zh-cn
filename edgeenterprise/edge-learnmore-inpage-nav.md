---
title: 让页内导航继续保持 Internet Explorer 模式
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 05/01/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 让页内导航继续保持 Internet Explorer 模式
ms.openlocfilehash: 0acca9e05a0d09b02fa61d5ddd7de3f7c6cabb92
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979302"
---
# <span data-ttu-id="b47dd-103">让页内导航继续保持 Internet Explorer 模式</span><span class="sxs-lookup"><span data-stu-id="b47dd-103">Keep in-page navigation in Internet Explorer mode</span></span>

<span data-ttu-id="b47dd-104">可以将此策略用作临时解决方案，以强制来自 Internet Explorer 模式（IE 模式）网站的所有页内导航都继续保持 IE 模式。</span><span class="sxs-lookup"><span data-stu-id="b47dd-104">You can use this policy as a temporary solution to force all in-page navigation from Internet Explorer mode (IE mode) sites to stay in IE mode.</span></span>

<span data-ttu-id="b47dd-105">页内导航将从当前页上的链接、脚本或窗体启动。</span><span class="sxs-lookup"><span data-stu-id="b47dd-105">An in-page navigation is started from a link, a script, or a form on the current page.</span></span> <span data-ttu-id="b47dd-106">也可以是上次页内导航尝试的服务器端重定向。</span><span class="sxs-lookup"><span data-stu-id="b47dd-106">It can also be a server-side redirect of a previous in-page navigation attempt.</span></span> <span data-ttu-id="b47dd-107">相反，用户可以使用浏览器控件通过多种方式启动与当前页面无关的非页内导航。</span><span class="sxs-lookup"><span data-stu-id="b47dd-107">Conversely, a user can start a navigation that isn't in-page that's independent of the current page in several ways by using the browser controls.</span></span> <span data-ttu-id="b47dd-108">例如，使用地址栏、返回按钮或收藏夹链接。</span><span class="sxs-lookup"><span data-stu-id="b47dd-108">For example, using the address bar, the back button, or a favorite link.</span></span>

>[!NOTE]
><span data-ttu-id="b47dd-109">本文适用于 Microsoft Edge 版本 81 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="b47dd-109">This article applies to Microsoft Edge version 81 or later.</span></span>

## <span data-ttu-id="b47dd-110">必备条件</span><span class="sxs-lookup"><span data-stu-id="b47dd-110">Prerequisites</span></span>

<span data-ttu-id="b47dd-111">此策略需要以下 Windows 更新：</span><span class="sxs-lookup"><span data-stu-id="b47dd-111">The following Windows updates are required for this policy:</span></span>

- <span data-ttu-id="b47dd-112">Windows 10 版本 1909 和 1903，Windows Server 版本 1909 和 1903 ([KB4532695](https://support.microsoft.com/help/4532695))</span><span class="sxs-lookup"><span data-stu-id="b47dd-112">Windows 10 version 1909 & 1903, Windows Server version 1909 & 1903  ([KB4532695](https://support.microsoft.com/help/4532695))</span></span>
- <span data-ttu-id="b47dd-113">Windows 10 版本 1809，Windows Server 版本 1809，Windows Server 2019 ([KB4534321](https://support.microsoft.com/help/4534321))</span><span class="sxs-lookup"><span data-stu-id="b47dd-113">Windows 10 version 1809, Windows Server version 1809, Windows Server 2019 ([KB4534321](https://support.microsoft.com/help/4534321))</span></span>
- <span data-ttu-id="b47dd-114">Windows 10 版本 1803 ([KB4534308](https://support.microsoft.com/help/4534308))</span><span class="sxs-lookup"><span data-stu-id="b47dd-114">Windows 10 version 1803 ([KB4534308](https://support.microsoft.com/help/4534308))</span></span>
- <span data-ttu-id="b47dd-115">Windows 10 版本 1709 ([KB4534318](https://support.microsoft.com/help/4534318))</span><span class="sxs-lookup"><span data-stu-id="b47dd-115">Windows 10 version 1709 ([KB4534318](https://support.microsoft.com/help/4534318))</span></span>


## <span data-ttu-id="b47dd-116">关于此策略</span><span class="sxs-lookup"><span data-stu-id="b47dd-116">About this policy</span></span>

<span data-ttu-id="b47dd-117">此策略让你有时间识别和配置 IE 模式网站使用的所有身份验证服务器。</span><span class="sxs-lookup"><span data-stu-id="b47dd-117">This policy gives you time to identify and configure all of the authentication servers used by your IE mode sites.</span></span> <span data-ttu-id="b47dd-118">但是，此策略可能会产生不一致的浏览体验，在这种情况下，某些网站将以 IE 模式呈现，而在其他时间以 Microsoft Edge 模式呈现。</span><span class="sxs-lookup"><span data-stu-id="b47dd-118">However, this policy can result in an inconsistent browsing experience, where some sites are rendered in IE mode and at other times rendered in Microsoft Edge mode.</span></span> <span data-ttu-id="b47dd-119">此体验取决于是否是从 IE 模式页面导航到网站的。</span><span class="sxs-lookup"><span data-stu-id="b47dd-119">This experience depends on whether the navigation to the site began from an IE mode page.</span></span> <span data-ttu-id="b47dd-120">任何未显式配置为在特定呈现引擎中打开的网站都将出现此不一致性的情况。</span><span class="sxs-lookup"><span data-stu-id="b47dd-120">Any site that isn't explicitly configured to open in a specific rendering engine will be subject to this inconsistency.</span></span>

<span data-ttu-id="b47dd-121">如果启用此策略，建议你在识别所有身份验证服务器并将它们作为中性服务器添加到网站列表中以后将此策略禁用。</span><span class="sxs-lookup"><span data-stu-id="b47dd-121">If you enable this policy, we recommend that you disable it after you've identified all the authentication servers and added them to the site list as neutral.</span></span> <span data-ttu-id="b47dd-122">此操作可确保新式网站绝不会在 IE 模式下意外呈现。</span><span class="sxs-lookup"><span data-stu-id="b47dd-122">This action ensures that your modern sites never inadvertently render in IE mode.</span></span>

## <span data-ttu-id="b47dd-123">让页内导航继续保持 IE 模式</span><span class="sxs-lookup"><span data-stu-id="b47dd-123">Keep in-page navigation in IE mode</span></span>

<span data-ttu-id="b47dd-124">若要让自动导航或所有页内导航都继续保持 Internet Explorer 模式，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="b47dd-124">To keep automatic or all in-page navigation in Internet Explorer mode, follow these steps:</span></span>

1. <span data-ttu-id="b47dd-125">打开本地组策略编辑器。</span><span class="sxs-lookup"><span data-stu-id="b47dd-125">Open Local Group Policy Editor.</span></span>
2. <span data-ttu-id="b47dd-126">单击**计算机配置** > **管理模板** > **Microsoft Edge**。</span><span class="sxs-lookup"><span data-stu-id="b47dd-126">Click **Computer Configuration** > **Administrative Templates** > **Microsoft Edge**.</span></span>
3. <span data-ttu-id="b47dd-127">在**设置**下，双击**指定从 Internet Explorer 模式页面到未配置的网站的页内导航行为方式**。</span><span class="sxs-lookup"><span data-stu-id="b47dd-127">Under **Setting**, double-click **Specify how "in-page" navigations to unconfigured sites behave when started from Internet Explorer mode pages**.</span></span>

   ![页内策略设置](media/edge-learnmore-inpage-nav/learnmore-in-page-nav-settings.png)

4. <span data-ttu-id="b47dd-129">选中**已启用**</span><span class="sxs-lookup"><span data-stu-id="b47dd-129">Select **Enabled**</span></span> 

   ![启用页内策略](media/edge-learnmore-inpage-nav/learnmore-in-page-nav-enable.png)

5. <span data-ttu-id="b47dd-131">从下拉列表中选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="b47dd-131">Choose one of the following options from the dropdown list:</span></span>

   - <span data-ttu-id="b47dd-132">**默认** - 只有配置为以 Internet Explorer 模式打开的网站才会以该模式打开。</span><span class="sxs-lookup"><span data-stu-id="b47dd-132">**Default** - Only sites configured to open in Internet Explorer mode will open in that mode.</span></span> <span data-ttu-id="b47dd-133">任何未配置为以 Internet Explorer 模式打开的网站都将重定向回 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="b47dd-133">Any site not configured to open in Internet Explorer mode will be redirected back to Microsoft Edge.</span></span>
   - <span data-ttu-id="b47dd-134">**只让自动导航继续保持 Internet Explorer 模式** - 如果想要默认体验，但又让所有转到未配置网站的自动导航（如 302 重定向）都继续保持 Internet Explorer 模式，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="b47dd-134">**Keep only automatic navigations in Internet Explorer mode** - Use this option if you want the default experience except that all automatic navigations (such as 302 redirects) to unconfigured sites will be kept in Internet Explorer mode.</span></span>
   - <span data-ttu-id="b47dd-135">\*\*让所有页内导航都继续保持 Internet Explorer 模式\*\*\*\*\*（最不推荐）\*\*\*- 所有从 IE 模式下加载的页面转到未配置网站的导航都继续保持 Internet Explorer 模式。</span><span class="sxs-lookup"><span data-stu-id="b47dd-135">**Keep all in-page navigation in Internet Explorer mode** ***(Least Recommended)*** - All navigations from pages loaded in IE mode to unconfigured sites are kept in Internet Explorer mode.</span></span>

6. <span data-ttu-id="b47dd-136">单击**确定**或**应用**以保存策略设置。</span><span class="sxs-lookup"><span data-stu-id="b47dd-136">Click **OK** or **Apply** to save the policy settings.</span></span>

## <span data-ttu-id="b47dd-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b47dd-137">See also</span></span>

- [<span data-ttu-id="b47dd-138">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="b47dd-138">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
