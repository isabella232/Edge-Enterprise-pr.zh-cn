---
title: 禁用 Internet Explorer 11
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 03/02/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解如何在 Microsoft Edge Internet Explorer 11 和使用Internet Explorer模式。
ms.openlocfilehash: 08d1fe48bfc4614710f4a341a285048194a64794
ms.sourcegitcommit: 928714329d0b11575494f557498f69a8417a3289
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385324"
---
# <a name="disable-internet-explorer-11"></a><span data-ttu-id="0fb08-103">禁用 Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="0fb08-103">Disable Internet Explorer 11</span></span>

<span data-ttu-id="0fb08-104">本文介绍如何在环境中禁用 Internet Explorer 11 作为独立浏览器。</span><span class="sxs-lookup"><span data-stu-id="0fb08-104">This article describes how to disable Internet Explorer 11 as a standalone browser in your environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0fb08-105">必备条件</span><span class="sxs-lookup"><span data-stu-id="0fb08-105">Prerequisites</span></span>

<span data-ttu-id="0fb08-106">需要以下 Windows 更新和 Microsoft Edge 软件：</span><span class="sxs-lookup"><span data-stu-id="0fb08-106">The following Windows updates and Microsoft Edge software are required:</span></span>

- <span data-ttu-id="0fb08-107">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="0fb08-107">Windows updates</span></span>

  - <span data-ttu-id="0fb08-108">Windows 10 版本 2004、Windows Server 版本 2004、Windows 10 版本 [20H2：KB4598291](https://support.microsoft.com/topic/february-2-2021-kb4598291-os-builds-19041-789-and-19042-789-preview-6a766199-a4f1-616e-1f5c-58bdc3ca5e3b) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="0fb08-108">Windows 10, version 2004, Windows Server version 2004, Windows 10, version 20H2: [KB4598291](https://support.microsoft.com/topic/february-2-2021-kb4598291-os-builds-19041-789-and-19042-789-preview-6a766199-a4f1-616e-1f5c-58bdc3ca5e3b) or later</span></span>
  - <span data-ttu-id="0fb08-109">Windows 10 版本 1909，Windows Server 版本 [1909：KB4598298](https://support.microsoft.com/topic/january-21-2021-kb4598298-os-build-18363-1350-preview-02dfd9ba-91a2-1b82-dede-42f288c02511) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="0fb08-109">Windows 10 version 1909, Windows Server version 1909: [KB4598298](https://support.microsoft.com/topic/january-21-2021-kb4598298-os-build-18363-1350-preview-02dfd9ba-91a2-1b82-dede-42f288c02511) or later</span></span>
  - <span data-ttu-id="0fb08-110">Windows 10 版本 1809、Windows Server 版本 1809 和 Windows Server [2019：KB4598296](https://support.microsoft.com/topic/january-21-2021-kb4598296-os-build-17763-1728-preview-4c0931ff-45b7-ff59-5e00-c03b5afb363d) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="0fb08-110">Windows 10 version 1809, Windows Server version 1809, and Windows Server 2019: [KB4598296](https://support.microsoft.com/topic/january-21-2021-kb4598296-os-build-17763-1728-preview-4c0931ff-45b7-ff59-5e00-c03b5afb363d) or later</span></span>
  - <span data-ttu-id="0fb08-111">Windows 10 版本 1607、Windows Server [2016：KB4601318](https://support.microsoft.com/topic/february-9-2021-kb4601318-os-build-14393-4225-c5e3de6c-e3e6-ffb5-6197-48b9ce16446e) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="0fb08-111">Windows 10, version 1607, Windows Server 2016: [KB4601318](https://support.microsoft.com/topic/february-9-2021-kb4601318-os-build-14393-4225-c5e3de6c-e3e6-ffb5-6197-48b9ce16446e) or later</span></span>
   - <span data-ttu-id="0fb08-112">2015 年 7 月 (Windows 10 [) ：KB4601331](https://support.microsoft.com/office/february-9-2021%e2%80%94kb4601331-os-build-10240-18842-6227d078-fef3-8d67-27e0-1882e6cb79ff?ui=en-US&rs=en-US&ad=US) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="0fb08-112">Windows 10 initial version (July 2015): [KB4601331](https://support.microsoft.com/office/february-9-2021%e2%80%94kb4601331-os-build-10240-18842-6227d078-fef3-8d67-27e0-1882e6cb79ff?ui=en-US&rs=en-US&ad=US) or later</span></span>
  - <span data-ttu-id="0fb08-113">Windows [8.1：KB4601384](https://support.microsoft.com/topic/february-9-2021-kb4601384-monthly-rollup-16bdbb75-dd4b-2910-abc5-7891c9756b96) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="0fb08-113">Windows 8.1: [KB4601384](https://support.microsoft.com/topic/february-9-2021-kb4601384-monthly-rollup-16bdbb75-dd4b-2910-abc5-7891c9756b96) or later</span></span>
  - <span data-ttu-id="0fb08-114">[Windows Server 2012：KB4601348](https://support.microsoft.com/topic/february-9-2021-kb4601348-monthly-rollup-2c338c0c-73d6-fb80-cc91-f1a86e80db0c)或更高版本</span><span class="sxs-lookup"><span data-stu-id="0fb08-114">Windows Server 2012: [KB4601348](https://support.microsoft.com/topic/february-9-2021-kb4601348-monthly-rollup-2c338c0c-73d6-fb80-cc91-f1a86e80db0c) or later</span></span>
  
- <span data-ttu-id="0fb08-115">Microsoft Edge 稳定渠道</span><span class="sxs-lookup"><span data-stu-id="0fb08-115">Microsoft Edge Stable Channel</span></span>


## <a name="overview"></a><span data-ttu-id="0fb08-116">概述</span><span class="sxs-lookup"><span data-stu-id="0fb08-116">Overview</span></span>

<span data-ttu-id="0fb08-117">对于需要 Internet Explorer 11 (IE11) 实现旧版兼容性的组织，Microsoft Edge 上的 Internet Explorer 模式 (IE 模式) 可提供无缝的单浏览器体验。</span><span class="sxs-lookup"><span data-stu-id="0fb08-117">For organizations that require Internet Explorer 11 (IE11) for legacy compatibility, Internet Explorer mode (IE mode) on Microsoft Edge provides a seamless, single browser experience.</span></span> <span data-ttu-id="0fb08-118">用户可以从 Microsoft Edge 内访问旧版应用程序，而无需切换回 IE11。</span><span class="sxs-lookup"><span data-stu-id="0fb08-118">Users can access legacy applications from within Microsoft Edge without having to switch back to IE11.</span></span>

<span data-ttu-id="0fb08-119">配置 IE 模式后，可以使用组策略禁用 **IE11** 作为独立浏览器，而不会影响整个组织的 IE 模式功能。</span><span class="sxs-lookup"><span data-stu-id="0fb08-119">After you configure IE mode, you can disable IE11 as a standalone browser **without affecting IE mode functionality** across your organization using group policy.</span></span>

> [!NOTE]
> <span data-ttu-id="0fb08-120">如果需要用于特定站点的独立 IE11 应用，并且希望将所有其他浏览器流量重定向到 Microsoft Edge，可以将站点列表中未包含的所有站点都配置为 [Microsoft Edge](https://docs.microsoft.com/deployedge/edge-ie-mode-policies#redirect-sites-from-ie-to-microsoft-edge) 策略，以将站点从 IE 重定向到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="0fb08-120">If you need the standalone IE11 app for specific sites, and want to redirect all other browser traffic to Microsoft Edge, you can configure the [Send all sites not included in the site list to Microsoft Edge](https://docs.microsoft.com/deployedge/edge-ie-mode-policies#redirect-sites-from-ie-to-microsoft-edge) policy to redirect sites from IE to Microsoft Edge.</span></span>

## <a name="user-experience-after-redirecting-traffic-to-microsoft-edge"></a><span data-ttu-id="0fb08-121">将流量重定向到 Microsoft Edge 后的用户体验</span><span class="sxs-lookup"><span data-stu-id="0fb08-121">User experience after redirecting traffic to Microsoft Edge</span></span>

<span data-ttu-id="0fb08-122">当您启用禁用 **Internet Explorer 11 作为** 独立浏览器策略时，所有 IE11 活动将重定向到 Microsoft Edge，并且用户具有以下体验：</span><span class="sxs-lookup"><span data-stu-id="0fb08-122">When you enable the **Disable Internet Explorer 11 as a standalone browser** policy, all IE11 activity is redirected to Microsoft Edge and users have the following experience:</span></span>

- <span data-ttu-id="0fb08-123">将删除"开始"菜单上的 IE11 图标，但任务栏上的图标将保留。</span><span class="sxs-lookup"><span data-stu-id="0fb08-123">The IE11 icon on the Start Menu will be removed, but the one on the taskbar will remain.</span></span>
- <span data-ttu-id="0fb08-124">当用户尝试启动使用 IE11 的快捷方式或文件关联时，他们将被重定向以在 Microsoft Edge 中打开相同的文件/URL。</span><span class="sxs-lookup"><span data-stu-id="0fb08-124">When users try to launch shortcuts or file associations that use IE11, they will be redirected to open the same file/URL in Microsoft Edge.</span></span>
- <span data-ttu-id="0fb08-125">当用户尝试通过直接调用 IE11 iexplore.exe，Microsoft Edge 将改为启动。</span><span class="sxs-lookup"><span data-stu-id="0fb08-125">When users try to launch IE11 by directly invoking the iexplore.exe binary, Microsoft Edge will launch instead.</span></span>

<span data-ttu-id="0fb08-126">作为为此体验设置策略的一部分，可以选择为尝试启动 IE11 的每个用户显示重定向消息。</span><span class="sxs-lookup"><span data-stu-id="0fb08-126">As part of setting the policy for this experience, you can optionally show a redirect message for each user who tries to launch IE11.</span></span> <span data-ttu-id="0fb08-127">可以将此消息设置为显示"始终"或"每个用户一次"。</span><span class="sxs-lookup"><span data-stu-id="0fb08-127">This message can be set to display "Always" or "Once per user".</span></span> <span data-ttu-id="0fb08-128">默认情况下，不会显示下一张屏幕截图中显示的重定向消息。</span><span class="sxs-lookup"><span data-stu-id="0fb08-128">By default, the redirect message shown in the next screenshot is never shown.</span></span>

:::image type="content" source="media/edge-ie-disable-ie11/disable-ie-redirect-msg.png" alt-text="尝试在重定向到 Microsoft Edge 处于活动状态后打开 IE 时发出警报。":::

<span data-ttu-id="0fb08-130">如果你的企业模式站点列表包含配置为在 IE11 应用中打开的应用程序，并且你通过此策略禁用 IE11，它们在 Microsoft Edge 上将在 IE 模式下打开。</span><span class="sxs-lookup"><span data-stu-id="0fb08-130">If your Enterprise Mode Site List contains applications that are configured to open in the IE11 app and you disable IE11 with this policy, they will open in IE mode on Microsoft Edge.</span></span>
> [!NOTE]
> <span data-ttu-id="0fb08-131">将站点配置为在 IE11 中打开并设置禁用 IE11 策略时，用户流存在已知问题。</span><span class="sxs-lookup"><span data-stu-id="0fb08-131">There is a known issue with the user flow when a site is configured to open in IE11 and the disable IE11 policy is set.</span></span> <span data-ttu-id="0fb08-132">正在积极调查的问题。</span><span class="sxs-lookup"><span data-stu-id="0fb08-132">The issue being actively investigated.</span></span>

## <a name="disable-internet-explorer-11-as-a-standalone-browser"></a><span data-ttu-id="0fb08-133">禁用 Internet Explorer 11 作为独立浏览器</span><span class="sxs-lookup"><span data-stu-id="0fb08-133">Disable Internet Explorer 11 as a standalone browser</span></span>

<span data-ttu-id="0fb08-134">若要使用Internet Explorer禁用 11，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="0fb08-134">To disable Internet Explorer 11 using group policy, follow these steps:</span></span>

1. <span data-ttu-id="0fb08-135">下载并安装最新的 [Microsoft Edge 策略模板](https://www.microsoft.com/en-us/business/download)。</span><span class="sxs-lookup"><span data-stu-id="0fb08-135">Download and install the latest [Microsoft Edge Policy Template](https://www.microsoft.com/en-us/business/download).</span></span>
2. <span data-ttu-id="0fb08-136">打开组策略编辑器。</span><span class="sxs-lookup"><span data-stu-id="0fb08-136">Open the Group Policy Editor.</span></span>
3. <span data-ttu-id="0fb08-137">转到***计算机配置/管理模板/Windows 组件/Internet Explorer。***</span><span class="sxs-lookup"><span data-stu-id="0fb08-137">Go to ***Computer Configuration/Administrative Templates/Windows Components/Internet Explorer***.</span></span> 
4. <span data-ttu-id="0fb08-138">双击禁用 **Internet Explorer 11 作为独立浏览器**。</span><span class="sxs-lookup"><span data-stu-id="0fb08-138">Double-click **Disable Internet Explorer 11 as a standalone browser**.</span></span>
5. <span data-ttu-id="0fb08-139">选择 **"已启用"。**</span><span class="sxs-lookup"><span data-stu-id="0fb08-139">Select **Enabled**.</span></span>
6. <span data-ttu-id="0fb08-140">在 **"** 选项"下，选取下列值之一：</span><span class="sxs-lookup"><span data-stu-id="0fb08-140">Under **Options**, pick one of the following values:</span></span>

   - <span data-ttu-id="0fb08-141">**从不**  如果不想通知用户 IE11 已禁用。</span><span class="sxs-lookup"><span data-stu-id="0fb08-141">**Never** if you don’t want to notify users that IE11 is disabled.</span></span>
   - <span data-ttu-id="0fb08-142">**始终**  如果希望每次从 IE11 重定向用户时通知用户。</span><span class="sxs-lookup"><span data-stu-id="0fb08-142">**Always** if you want to notify users every time they're redirected from IE11.</span></span>
   - <span data-ttu-id="0fb08-143">**每个用户一次**  如果希望仅在第一次重定向用户时通知用户。</span><span class="sxs-lookup"><span data-stu-id="0fb08-143">**Once per user** if you want to notify users only the first time they are redirected.</span></span>

7. <span data-ttu-id="0fb08-144">单击 **"**   确定 **"或"应用**   "保存此策略设置。</span><span class="sxs-lookup"><span data-stu-id="0fb08-144">Click **OK** or **Apply** to save this policy setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="0fb08-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0fb08-145">See also</span></span>

- [<span data-ttu-id="0fb08-146">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="0fb08-146">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="0fb08-147">关于 IE 模式</span><span class="sxs-lookup"><span data-stu-id="0fb08-147">About IE mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [<span data-ttu-id="0fb08-148">其他企业模式信息</span><span class="sxs-lookup"><span data-stu-id="0fb08-148">Additional Enterprise Mode information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
