---
title: 禁用 Internet Explorer 11
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 03/09/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解如何在 Microsoft Edge Internet Explorer 11 和使用Internet Explorer模式。
ms.openlocfilehash: 89fa6f81879be851f0036990a41e36e1eaee7fca
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447386"
---
# <a name="disable-internet-explorer-11"></a><span data-ttu-id="4520d-103">禁用 Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="4520d-103">Disable Internet Explorer 11</span></span>

<span data-ttu-id="4520d-104">本文介绍如何在环境中禁用 Internet Explorer 11 作为独立浏览器。</span><span class="sxs-lookup"><span data-stu-id="4520d-104">This article describes how to disable Internet Explorer 11 as a standalone browser in your environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4520d-105">必备条件</span><span class="sxs-lookup"><span data-stu-id="4520d-105">Prerequisites</span></span>

<span data-ttu-id="4520d-106">需要以下 Windows 更新和 Microsoft Edge 软件：</span><span class="sxs-lookup"><span data-stu-id="4520d-106">The following Windows updates and Microsoft Edge software are required:</span></span>

- <span data-ttu-id="4520d-107">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="4520d-107">Windows updates</span></span>

  - <span data-ttu-id="4520d-108">Windows 10 版本 2004、Windows Server 版本 2004、Windows 10 版本 [20H2：KB4598291](https://support.microsoft.com/topic/february-2-2021-kb4598291-os-builds-19041-789-and-19042-789-preview-6a766199-a4f1-616e-1f5c-58bdc3ca5e3b) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="4520d-108">Windows 10, version 2004, Windows Server version 2004, Windows 10, version 20H2: [KB4598291](https://support.microsoft.com/topic/february-2-2021-kb4598291-os-builds-19041-789-and-19042-789-preview-6a766199-a4f1-616e-1f5c-58bdc3ca5e3b) or later</span></span>
  - <span data-ttu-id="4520d-109">Windows 10 版本 1909，Windows Server 版本 [1909：KB4598298](https://support.microsoft.com/topic/january-21-2021-kb4598298-os-build-18363-1350-preview-02dfd9ba-91a2-1b82-dede-42f288c02511) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="4520d-109">Windows 10 version 1909, Windows Server version 1909: [KB4598298](https://support.microsoft.com/topic/january-21-2021-kb4598298-os-build-18363-1350-preview-02dfd9ba-91a2-1b82-dede-42f288c02511) or later</span></span>
  - <span data-ttu-id="4520d-110">Windows 10 版本 1809、Windows Server 版本 1809 和 Windows Server [2019：KB4598296](https://support.microsoft.com/topic/january-21-2021-kb4598296-os-build-17763-1728-preview-4c0931ff-45b7-ff59-5e00-c03b5afb363d) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="4520d-110">Windows 10 version 1809, Windows Server version 1809, and Windows Server 2019: [KB4598296](https://support.microsoft.com/topic/january-21-2021-kb4598296-os-build-17763-1728-preview-4c0931ff-45b7-ff59-5e00-c03b5afb363d) or later</span></span>
  - <span data-ttu-id="4520d-111">Windows 10 版本 1607、Windows Server [2016：KB4601318](https://support.microsoft.com/topic/february-9-2021-kb4601318-os-build-14393-4225-c5e3de6c-e3e6-ffb5-6197-48b9ce16446e) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="4520d-111">Windows 10, version 1607, Windows Server 2016: [KB4601318](https://support.microsoft.com/topic/february-9-2021-kb4601318-os-build-14393-4225-c5e3de6c-e3e6-ffb5-6197-48b9ce16446e) or later</span></span>
   - <span data-ttu-id="4520d-112">2015 年 7 月 (Windows 10 [) ：KB4601331](https://support.microsoft.com/office/february-9-2021%e2%80%94kb4601331-os-build-10240-18842-6227d078-fef3-8d67-27e0-1882e6cb79ff?ui=en-US&rs=en-US&ad=US) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="4520d-112">Windows 10 initial version (July 2015): [KB4601331](https://support.microsoft.com/office/february-9-2021%e2%80%94kb4601331-os-build-10240-18842-6227d078-fef3-8d67-27e0-1882e6cb79ff?ui=en-US&rs=en-US&ad=US) or later</span></span>
  - <span data-ttu-id="4520d-113">Windows [8.1：KB4601384](https://support.microsoft.com/topic/february-9-2021-kb4601384-monthly-rollup-16bdbb75-dd4b-2910-abc5-7891c9756b96) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="4520d-113">Windows 8.1: [KB4601384](https://support.microsoft.com/topic/february-9-2021-kb4601384-monthly-rollup-16bdbb75-dd4b-2910-abc5-7891c9756b96) or later</span></span>
  - <span data-ttu-id="4520d-114">[Windows Server 2012：KB4601348](https://support.microsoft.com/topic/february-9-2021-kb4601348-monthly-rollup-2c338c0c-73d6-fb80-cc91-f1a86e80db0c)或更高版本</span><span class="sxs-lookup"><span data-stu-id="4520d-114">Windows Server 2012: [KB4601348](https://support.microsoft.com/topic/february-9-2021-kb4601348-monthly-rollup-2c338c0c-73d6-fb80-cc91-f1a86e80db0c) or later</span></span>
  
- <span data-ttu-id="4520d-115">Microsoft Edge 稳定渠道</span><span class="sxs-lookup"><span data-stu-id="4520d-115">Microsoft Edge Stable Channel</span></span>


## <a name="overview"></a><span data-ttu-id="4520d-116">概述</span><span class="sxs-lookup"><span data-stu-id="4520d-116">Overview</span></span>

<span data-ttu-id="4520d-117">对于需要 Internet Explorer 11 (IE11) 实现旧版兼容性的组织，Microsoft Edge 上的 Internet Explorer 模式 (IE 模式) 可提供无缝的单浏览器体验。</span><span class="sxs-lookup"><span data-stu-id="4520d-117">For organizations that require Internet Explorer 11 (IE11) for legacy compatibility, Internet Explorer mode (IE mode) on Microsoft Edge provides a seamless, single browser experience.</span></span> <span data-ttu-id="4520d-118">用户可以从 Microsoft Edge 内访问旧版应用程序，而无需切换回 IE11。</span><span class="sxs-lookup"><span data-stu-id="4520d-118">Users can access legacy applications from within Microsoft Edge without having to switch back to IE11.</span></span>

<span data-ttu-id="4520d-119">配置 IE 模式后，可以使用组策略禁用 **IE11** 作为独立浏览器，而不会影响整个组织的 IE 模式功能。</span><span class="sxs-lookup"><span data-stu-id="4520d-119">After you configure IE mode, you can disable IE11 as a standalone browser **without affecting IE mode functionality** across your organization using group policy.</span></span>

> [!NOTE]
> <span data-ttu-id="4520d-120">如果需要用于特定站点的独立 IE11 应用，并且希望将所有其他浏览器流量重定向到 Microsoft Edge，可以将站点列表中未包含的所有站点都配置为 [Microsoft Edge](./edge-ie-mode-policies.md#redirect-sites-from-ie-to-microsoft-edge) 策略，以将站点从 IE 重定向到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="4520d-120">If you need the standalone IE11 app for specific sites, and want to redirect all other browser traffic to Microsoft Edge, you can configure the [Send all sites not included in the site list to Microsoft Edge](./edge-ie-mode-policies.md#redirect-sites-from-ie-to-microsoft-edge) policy to redirect sites from IE to Microsoft Edge.</span></span>

## <a name="user-experience-after-redirecting-traffic-to-microsoft-edge"></a><span data-ttu-id="4520d-121">将流量重定向到 Microsoft Edge 后的用户体验</span><span class="sxs-lookup"><span data-stu-id="4520d-121">User experience after redirecting traffic to Microsoft Edge</span></span>

<span data-ttu-id="4520d-122">当您启用禁用 **Internet Explorer 11 作为** 独立浏览器策略时，所有 IE11 活动将重定向到 Microsoft Edge，并且用户具有以下体验：</span><span class="sxs-lookup"><span data-stu-id="4520d-122">When you enable the **Disable Internet Explorer 11 as a standalone browser** policy, all IE11 activity is redirected to Microsoft Edge and users have the following experience:</span></span>

- <span data-ttu-id="4520d-123">将删除"开始"菜单上的 IE11 图标，但任务栏上的图标将保留。</span><span class="sxs-lookup"><span data-stu-id="4520d-123">The IE11 icon on the Start Menu will be removed, but the one on the taskbar will remain.</span></span>
- <span data-ttu-id="4520d-124">当用户尝试启动使用 IE11 的快捷方式或文件关联时，他们将被重定向以在 Microsoft Edge 中打开相同的文件/URL。</span><span class="sxs-lookup"><span data-stu-id="4520d-124">When users try to launch shortcuts or file associations that use IE11, they will be redirected to open the same file/URL in Microsoft Edge.</span></span>
- <span data-ttu-id="4520d-125">当用户尝试通过直接调用 IE11 iexplore.exe，Microsoft Edge 将改为启动。</span><span class="sxs-lookup"><span data-stu-id="4520d-125">When users try to launch IE11 by directly invoking the iexplore.exe binary, Microsoft Edge will launch instead.</span></span>

<span data-ttu-id="4520d-126">作为为此体验设置策略的一部分，可以选择为尝试启动 IE11 的每个用户显示重定向消息。</span><span class="sxs-lookup"><span data-stu-id="4520d-126">As part of setting the policy for this experience, you can optionally show a redirect message for each user who tries to launch IE11.</span></span> <span data-ttu-id="4520d-127">可以将此消息设置为显示"始终"或"每个用户一次"。</span><span class="sxs-lookup"><span data-stu-id="4520d-127">This message can be set to display "Always" or "Once per user".</span></span> <span data-ttu-id="4520d-128">默认情况下，不会显示下一张屏幕截图中显示的重定向消息。</span><span class="sxs-lookup"><span data-stu-id="4520d-128">By default, the redirect message shown in the next screenshot is never shown.</span></span>

:::image type="content" source="media/edge-ie-disable-ie11/disable-ie-redirect-msg.png" alt-text="尝试在重定向到 Microsoft Edge 处于活动状态后打开 IE 时发出警报。":::

<span data-ttu-id="4520d-130">如果你的企业模式站点列表包含配置为在 IE11 应用中打开的应用程序，并且你通过此策略禁用 IE11，它们在 Microsoft Edge 上将在 IE 模式下打开。</span><span class="sxs-lookup"><span data-stu-id="4520d-130">If your Enterprise Mode Site List contains applications that are configured to open in the IE11 app and you disable IE11 with this policy, they will open in IE mode on Microsoft Edge.</span></span>
> [!NOTE]
> <span data-ttu-id="4520d-131">将站点配置为在 IE11 中打开并设置禁用 IE11 策略时，用户流存在已知问题。</span><span class="sxs-lookup"><span data-stu-id="4520d-131">There is a known issue with the user flow when a site is configured to open in IE11 and the disable IE11 policy is set.</span></span> <span data-ttu-id="4520d-132">正在积极调查的问题。</span><span class="sxs-lookup"><span data-stu-id="4520d-132">The issue being actively investigated.</span></span>

## <a name="disable-internet-explorer-11-as-a-standalone-browser"></a><span data-ttu-id="4520d-133">禁用 Internet Explorer 11 作为独立浏览器</span><span class="sxs-lookup"><span data-stu-id="4520d-133">Disable Internet Explorer 11 as a standalone browser</span></span>

<span data-ttu-id="4520d-134">若要使用组策略禁用 Internet Explorer 11，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="4520d-134">To disable Internet Explorer 11 using group policy, follow these steps:</span></span>

1. <span data-ttu-id="4520d-135">确保你有必备的操作系统更新。</span><span class="sxs-lookup"><span data-stu-id="4520d-135">Ensure you have the pre-requisite operating system updates.</span></span> <span data-ttu-id="4520d-136">此步骤将直接更新计算机上的 ADMX 文件（特别是 inetres.adml 和 inetres.admx）。</span><span class="sxs-lookup"><span data-stu-id="4520d-136">This step will update the ADMX files on your machine directly (specifically inetres.adml and inetres.admx).</span></span> <span data-ttu-id="4520d-137">请注意，如果要更新中央存储，则需要从有必备更新的计算机上复制 .adml 和 .admx 文件。</span><span class="sxs-lookup"><span data-stu-id="4520d-137">Please note that if you want to update your Central Store, you will need to copy over the .adml and .admx files from a machine that has the pre-requisite updates.</span></span> <span data-ttu-id="4520d-138">有关详细信息，请参阅[创建和管理中央存储](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)</span><span class="sxs-lookup"><span data-stu-id="4520d-138">For more information, see [Create and manage Central Store](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)</span></span>
2. <span data-ttu-id="4520d-139">打开组策略编辑器。</span><span class="sxs-lookup"><span data-stu-id="4520d-139">Open the Group Policy Editor.</span></span>
3. <span data-ttu-id="4520d-140">转到***计算机配置/管理模板/Windows 组件/Internet Explorer。***</span><span class="sxs-lookup"><span data-stu-id="4520d-140">Go to ***Computer Configuration/Administrative Templates/Windows Components/Internet Explorer***.</span></span> 
4. <span data-ttu-id="4520d-141">双击禁用 **Internet Explorer 11 作为独立浏览器**。</span><span class="sxs-lookup"><span data-stu-id="4520d-141">Double-click **Disable Internet Explorer 11 as a standalone browser**.</span></span>
5. <span data-ttu-id="4520d-142">选择 **"已启用"。**</span><span class="sxs-lookup"><span data-stu-id="4520d-142">Select **Enabled**.</span></span>
6. <span data-ttu-id="4520d-143">在 **"** 选项"下，选取下列值之一：</span><span class="sxs-lookup"><span data-stu-id="4520d-143">Under **Options**, pick one of the following values:</span></span>

   - <span data-ttu-id="4520d-144">**从不**  如果不想通知用户 IE11 已禁用。</span><span class="sxs-lookup"><span data-stu-id="4520d-144">**Never** if you don’t want to notify users that IE11 is disabled.</span></span>
   - <span data-ttu-id="4520d-145">**始终**  如果希望每次从 IE11 重定向用户时通知用户。</span><span class="sxs-lookup"><span data-stu-id="4520d-145">**Always** if you want to notify users every time they're redirected from IE11.</span></span>
   - <span data-ttu-id="4520d-146">**每个用户一次**  如果希望仅在第一次重定向用户时通知用户。</span><span class="sxs-lookup"><span data-stu-id="4520d-146">**Once per user** if you want to notify users only the first time they are redirected.</span></span>

7. <span data-ttu-id="4520d-147">单击 **"**   确定 **"或"应用**   "保存此策略设置。</span><span class="sxs-lookup"><span data-stu-id="4520d-147">Click **OK** or **Apply** to save this policy setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="4520d-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4520d-148">See also</span></span>

- [<span data-ttu-id="4520d-149">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="4520d-149">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="4520d-150">关于 IE 模式</span><span class="sxs-lookup"><span data-stu-id="4520d-150">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="4520d-151">其他企业模式信息</span><span class="sxs-lookup"><span data-stu-id="4520d-151">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)