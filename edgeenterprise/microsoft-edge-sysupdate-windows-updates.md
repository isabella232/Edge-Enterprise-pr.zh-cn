---
title: Microsoft Edge 的 Windows 更新
ms.author: jtkim
author: dan-wesley
manager: srugh
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 的 Windows 更新。
ms.openlocfilehash: 953becc459fe729f84d54da419481b3c6e26cc47
ms.sourcegitcommit: 16a92a51560fdba6f6480e4533453348f026c7ef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "11313902"
---
# <span data-ttu-id="a09f1-103">用于支持下一版本 Microsoft Edge 的 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="a09f1-103">Windows updates to support the next version of Microsoft Edge</span></span>

<span data-ttu-id="a09f1-104">本文介绍了如何更新 Windows 以支持下一版本的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="a09f1-104">This article describes how Windows will be updated to support the next version of Microsoft Edge.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a09f1-105">有关 Microsoft Edge 旧版服务终止的信息，请参阅 Microsoft Edge 产品团队[博客文章](https://aka.ms/EdgeLegacyEOS)。</span><span class="sxs-lookup"><span data-stu-id="a09f1-105">Refer to the Microsoft Edge product team [blog post](https://aka.ms/EdgeLegacyEOS) about Microsoft Edge Legacy end of service.</span></span>

> [!NOTE]
> <span data-ttu-id="a09f1-106">本文适用于 Microsoft Edge 稳定渠道。</span><span class="sxs-lookup"><span data-stu-id="a09f1-106">This article applies to the Microsoft Edge Stable channel.</span></span>

## <span data-ttu-id="a09f1-107">Microsoft Edge 和 Windows 版本周期</span><span class="sxs-lookup"><span data-stu-id="a09f1-107">Microsoft Edge and the Windows release cycle</span></span>

<span data-ttu-id="a09f1-108">下一版本的 Microsoft Edge 具有更频繁且更灵活的更新功能。</span><span class="sxs-lookup"><span data-stu-id="a09f1-108">The next version of Microsoft Edge features more frequent and more flexible updating capabilities.</span></span> <span data-ttu-id="a09f1-109">由于浏览器版本未绑定到 Windows 主要版本，因此会对操作系统进行更改，以确保下一版本的 Microsoft Edge 可以无缝融入到 Windows 中。</span><span class="sxs-lookup"><span data-stu-id="a09f1-109">Because browser releases aren't bound to the Windows major releases, changes will be made to the operating system to ensure that the next version of Microsoft Edge fits seamlessly into Windows.</span></span> <span data-ttu-id="a09f1-110">因此，功能更新约每 6 周发布一次。</span><span class="sxs-lookup"><span data-stu-id="a09f1-110">As a result, feature updates will be released on a 6-week cycle (approximately).</span></span> <span data-ttu-id="a09f1-111">安全和兼容性更新按需提供。</span><span class="sxs-lookup"><span data-stu-id="a09f1-111">Security and compatibility updates will be shipped as needed.</span></span>

## <span data-ttu-id="a09f1-112">更新和用户体验</span><span class="sxs-lookup"><span data-stu-id="a09f1-112">Updates and the user experience</span></span>

<span data-ttu-id="a09f1-113">更新将不会更改用户体验，直到安装下一版本 Microsoft Edge 的稳定渠道为止。</span><span class="sxs-lookup"><span data-stu-id="a09f1-113">Updates won’t change the user experience until the Stable channel of the next version of Microsoft Edge is installed.</span></span> <span data-ttu-id="a09f1-114">安装 Microsoft Edge Beta、Dev 或 Canary 不会触发 Windows 中的任何更改。</span><span class="sxs-lookup"><span data-stu-id="a09f1-114">Installing Microsoft Edge Beta, Dev, or Canary won’t trigger any changes in Windows.</span></span> <span data-ttu-id="a09f1-115">这些浏览器版本将随现有浏览器一起安装。</span><span class="sxs-lookup"><span data-stu-id="a09f1-115">These browser releases will be installed alongside existing browsers.</span></span>

<span data-ttu-id="a09f1-116">在系统级别应用所有更新并且安装下一版本 Microsoft Edge 的稳定渠道时，以下更改将在系统上生效：</span><span class="sxs-lookup"><span data-stu-id="a09f1-116">When all the updates are applied AND the Stable channel of the next version of Microsoft Edge is installed at the system-level, the following changes will take effect on the system:</span></span>

- <span data-ttu-id="a09f1-117">当前版本的 Microsoft Edge 的所有“开始”菜单 Pin、磁贴和快捷方式都将迁移到下一版本的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="a09f1-117">All start menu pins, tiles, and shortcuts for the current version of Microsoft Edge will migrate to the next version of Microsoft Edge.</span></span>
- <span data-ttu-id="a09f1-118">当前版本的 Microsoft Edge 的所有任务栏 Pin 和快捷方式都将迁移到下一版本的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="a09f1-118">All taskbar pins and shortcuts for the current version of Microsoft Edge will migrate to the next version of Microsoft Edge.</span></span>
- <span data-ttu-id="a09f1-119">下一版本的 Microsoft Edge 将固定到任务栏上。</span><span class="sxs-lookup"><span data-stu-id="a09f1-119">The next version of Microsoft Edge will be pinned to the taskbar.</span></span> <span data-ttu-id="a09f1-120">如果已固定当前版本的 Microsoft Edge，将替换它。</span><span class="sxs-lookup"><span data-stu-id="a09f1-120">If the current version of Microsoft Edge is already pinned, it will be replaced.</span></span>
- <span data-ttu-id="a09f1-121">下一版本的 Microsoft Edge 将向桌面添加快捷方式。</span><span class="sxs-lookup"><span data-stu-id="a09f1-121">The next version of Microsoft Edge will add a shortcut to the desktop.</span></span> <span data-ttu-id="a09f1-122">如果当前版本的 Microsoft Edge 已有快捷方式，则旧快捷方式将被替换。</span><span class="sxs-lookup"><span data-stu-id="a09f1-122">If the current version of Microsoft Edge already has a shortcut, it will be replaced.</span></span>
- <span data-ttu-id="a09f1-123">Microsoft Edge 默认处理的大多数协议都将迁移到下一版本的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="a09f1-123">Most protocols that Microsoft Edge handles by default will be migrated to the next version of Microsoft Edge.</span></span>
- <span data-ttu-id="a09f1-124">当前的 Microsoft Edge 将在操作系统内的所有 UX 界面中隐藏，包括设置、所有应用程序以及任何文件或协议支持对话框。</span><span class="sxs-lookup"><span data-stu-id="a09f1-124">Current Microsoft Edge will be hidden from all UX surfaces in the OS, including settings, all apps, and any file or protocol support dialogs.</span></span>
- <span data-ttu-id="a09f1-125">所有尝试启动当前版本的 Microsoft Edge 的操作都将重定向到下一版本的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="a09f1-125">All attempts to launch the current version of Microsoft Edge will redirect to the next version of Microsoft Edge.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a09f1-126">用户级别安装不会触发这些行为。</span><span class="sxs-lookup"><span data-stu-id="a09f1-126">User-level installs won’t trigger these behaviors.</span></span>

<span data-ttu-id="a09f1-127">除了以前的更改之外，还存在无论是否安装了下一版本 Microsoft Edge 的稳定渠道都将发生的更改。</span><span class="sxs-lookup"><span data-stu-id="a09f1-127">Along with the previous changes, there are changes that will happen regardless of whether the Stable channel of the next version of Microsoft Edge is installed.</span></span>

- <span data-ttu-id="a09f1-128">Microsoft Edge 将为下一个版本的 Microsoft Edge 不支持的书籍和 XML 协议取消注册。</span><span class="sxs-lookup"><span data-stu-id="a09f1-128">Microsoft Edge will de-register for the books and XML protocols that the next version of Microsoft Edge doesn't support.</span></span> <span data-ttu-id="a09f1-129">尝试打开这些协议的用户将获得一个对话框，此对话框将提示他们选择默认应用。</span><span class="sxs-lookup"><span data-stu-id="a09f1-129">Users attempting to open these protocols will get a dialog that prompts them to choose a default app.</span></span> <span data-ttu-id="a09f1-130">请在[下载 ePub 应用以继续阅读电子书](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fsupport.microsoft.com%2Fhelp%2F4517840&data=02%7C01%7Cv-danwes%40microsoft.com%7Cc9f8571b880549c30fcf08d72be5eaf9%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637026138803983526&sdata=qtb3DvVZQ6H%2FFXnBievkl%2B%2BngAQXwl340PcH8kRc3y4%3D&reserved=0)中了解有关图书支持更改的更多信息。</span><span class="sxs-lookup"><span data-stu-id="a09f1-130">Learn more about changes to books support at [Download an ePub app to keep reading e-books](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fsupport.microsoft.com%2Fhelp%2F4517840&data=02%7C01%7Cv-danwes%40microsoft.com%7Cc9f8571b880549c30fcf08d72be5eaf9%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637026138803983526&sdata=qtb3DvVZQ6H%2FFXnBievkl%2B%2BngAQXwl340PcH8kRc3y4%3D&reserved=0).</span></span>

## <span data-ttu-id="a09f1-131">时间线</span><span class="sxs-lookup"><span data-stu-id="a09f1-131">Timeline</span></span>

<span data-ttu-id="a09f1-132">支持所述体验所需的更改将随 Windows 不同版本的三个更新一起提供。</span><span class="sxs-lookup"><span data-stu-id="a09f1-132">The changes needed to support the described experience will be delivered with three updates for different versions of Windows.</span></span>

### <span data-ttu-id="a09f1-133">Windows 版本 1903 和 1909</span><span class="sxs-lookup"><span data-stu-id="a09f1-133">Windows versions 1903 and 1909</span></span>

- <span data-ttu-id="a09f1-134">可选的 2019 年 7 月更新中的第一组更改，与 2019 年 8 月安全更新一起提供。</span><span class="sxs-lookup"><span data-stu-id="a09f1-134">First set of changes in optional July 2019 update, delivered with the August 2019 security update.</span></span>
- <span data-ttu-id="a09f1-135">可选的 2019 年 8 月更新中的第二组更改，与 2019 年 9 月安全更新一起提供。</span><span class="sxs-lookup"><span data-stu-id="a09f1-135">Second set of changes in the optional August 2019 update, delivered with the September 2019 security update.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a09f1-136">在此更新中，Microsoft Edge 将取消注册 XML 协议。</span><span class="sxs-lookup"><span data-stu-id="a09f1-136">This is the update where Microsoft Edge will de-register for the XML protocol.</span></span>

- <span data-ttu-id="a09f1-137">可选的 2019 年 9 月更新中的第三组更改，与 2019 年 10 月安全更新一起提供。</span><span class="sxs-lookup"><span data-stu-id="a09f1-137">Third set of changes in the optional September 2019 update, delivered with the October 2019 security update.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a09f1-138">在此更新中，Microsoft Edge 将不再支持电子书。</span><span class="sxs-lookup"><span data-stu-id="a09f1-138">This is the update where Microsoft Edge will no longer support eBooks.</span></span>

### <span data-ttu-id="a09f1-139">Windows 版本 1709、1803 和 1809</span><span class="sxs-lookup"><span data-stu-id="a09f1-139">Windows versions 1709, 1803, and 1809</span></span>

- <span data-ttu-id="a09f1-140">可选的 2019 年 8 月更新中的第一组更改，与 2019 年 9 月安全更新一起提供。</span><span class="sxs-lookup"><span data-stu-id="a09f1-140">First set of changes in an optional August 2019 update, delivered with the September 2019 security update.</span></span>
- <span data-ttu-id="a09f1-141">可选的 2019 年 9 月更新中的第二组更改，与 2019 年 10 月安全更新一起提供。</span><span class="sxs-lookup"><span data-stu-id="a09f1-141">Second set of changes in an optional September 2019 update, delivered with the October 2019 security update.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a09f1-142">在此更新中，Microsoft Edge 将取消注册 XML 协议。</span><span class="sxs-lookup"><span data-stu-id="a09f1-142">This is the update where Microsoft Edge will de-register for the XML protocol.</span></span>

- <span data-ttu-id="a09f1-143">可选的 2019 年 10 月更新中的第三组更改，与 2019 年 11 月安全更新一起提供。</span><span class="sxs-lookup"><span data-stu-id="a09f1-143">Third set of changes in an optional October 2019 update, delivered with the November 2019 security update.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a09f1-144">在此更新中，Microsoft Edge 将不再支持电子书。</span><span class="sxs-lookup"><span data-stu-id="a09f1-144">This is the update where Microsoft Edge will no longer support eBooks.</span></span>

<span data-ttu-id="a09f1-145">下表提供了每组更改中的特定更新的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a09f1-145">The following table gives the details for specific updates in each set of changes.</span></span>

| <span data-ttu-id="a09f1-146">Windows 10</span><span class="sxs-lookup"><span data-stu-id="a09f1-146">Windows 10</span></span> | <span data-ttu-id="a09f1-147">详细信息</span><span class="sxs-lookup"><span data-stu-id="a09f1-147">More Information</span></span> | <span data-ttu-id="a09f1-148">需要下载的内容</span><span class="sxs-lookup"><span data-stu-id="a09f1-148">Required Download</span></span> |
|--|--|--|
| <span data-ttu-id="a09f1-149">版本 1709</span><span class="sxs-lookup"><span data-stu-id="a09f1-149">Version 1709</span></span> | [<span data-ttu-id="a09f1-150">KB4525241</span><span class="sxs-lookup"><span data-stu-id="a09f1-150">KB4525241</span></span>](https://support.microsoft.com/help/4525241/windows-10-update-kb4525241) | [<span data-ttu-id="a09f1-151">Windows 10 版本 1709 的累积更新</span><span class="sxs-lookup"><span data-stu-id="a09f1-151">Cumulative Update for Windows 10 Version 1709</span></span>](https://www.catalog.update.microsoft.com/Search.aspx?q=4525241) |
| <span data-ttu-id="a09f1-152">版本 1803</span><span class="sxs-lookup"><span data-stu-id="a09f1-152">Version 1803</span></span>  | [<span data-ttu-id="a09f1-153">KB4525237</span><span class="sxs-lookup"><span data-stu-id="a09f1-153">KB4525237</span></span>](https://support.microsoft.com/help/4525237/windows-10-update-kb4525237) | [<span data-ttu-id="a09f1-154">Windows 10 版本 1803 的累积更新</span><span class="sxs-lookup"><span data-stu-id="a09f1-154">Cumulative Update for Windows 10 Version 1803</span></span>](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4525237) |
| <span data-ttu-id="a09f1-155">版本 1809</span><span class="sxs-lookup"><span data-stu-id="a09f1-155">Version 1809</span></span>  | [<span data-ttu-id="a09f1-156">KB4523205</span><span class="sxs-lookup"><span data-stu-id="a09f1-156">KB4523205</span></span>](https://support.microsoft.com/help/4523205/windows-10-update-kb4523205) | [<span data-ttu-id="a09f1-157">Windows 10 版本 1809 的累积更新</span><span class="sxs-lookup"><span data-stu-id="a09f1-157">Cumulative Update for Windows 10 Version 1809</span></span>](https://www.catalog.update.microsoft.com/Search.aspx?q=4523205) |
| <span data-ttu-id="a09f1-158">版本 1903 和 1909</span><span class="sxs-lookup"><span data-stu-id="a09f1-158">Version 1903 and 1909</span></span> |[<span data-ttu-id="a09f1-159">KB4517389</span><span class="sxs-lookup"><span data-stu-id="a09f1-159">KB4517389</span></span>](https://support.microsoft.com/help/4517389/windows-10-update-kb4517389)  | [<span data-ttu-id="a09f1-160">Windows 10 版本 1903 和 1909 的累积更新</span><span class="sxs-lookup"><span data-stu-id="a09f1-160">Cumulative Update for Windows 10 Version 1903 and 1909</span></span>](https://www.catalog.update.microsoft.com/Search.aspx?q=4517389) |

## <span data-ttu-id="a09f1-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a09f1-161">See also</span></span>

- [<span data-ttu-id="a09f1-162">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="a09f1-162">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="a09f1-163">Microsoft Edge 文档</span><span class="sxs-lookup"><span data-stu-id="a09f1-163">Microsoft Edge documentation</span></span>](https://docs.microsoft.com/DeployEdge/)
