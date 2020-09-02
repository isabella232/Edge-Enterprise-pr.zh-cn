---
title: Microsoft Edge 展台模式
ms.author: brianalt
author: brianalt
manager: seanlynd
ms.date: 01/16/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 展台模式
ms.openlocfilehash: 7a690820752b5361349bf394055a737bd8175215
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979370"
---
# <span data-ttu-id="21916-103">Microsoft Edge 展台模式</span><span class="sxs-lookup"><span data-stu-id="21916-103">Microsoft Edge kiosk mode</span></span>

<span data-ttu-id="21916-104">本文概述 Microsoft Edge（版本 77 或更高版本）展台模式选项。</span><span class="sxs-lookup"><span data-stu-id="21916-104">This article provides an overview of the Microsoft Edge (version 77 or later) kiosk mode options.</span></span> <span data-ttu-id="21916-105">它还涉及继续使用旧版 Microsoft Edge 展台模式（版本 45 和更低版本）需要做什么。</span><span class="sxs-lookup"><span data-stu-id="21916-105">It also covers what's required to continue using Microsoft Edge Legacy kiosk mode (version 45 and earlier.)</span></span>

<span data-ttu-id="21916-106">有关旧版 Microsoft Edge 展台模式（版本 45 和更早版本）的信息，请参阅[部署 Microsoft Edge 站台模式](https://aka.ms/edgekioskmode)。</span><span class="sxs-lookup"><span data-stu-id="21916-106">For information about Microsoft Edge Legacy kiosk mode (version 45 and earlier) see [Deploy Microsoft Edge kiosk mode](https://aka.ms/edgekioskmode).</span></span>

## <span data-ttu-id="21916-107">Microsoft Edge 与指派访问</span><span class="sxs-lookup"><span data-stu-id="21916-107">Microsoft Edge with assigned access</span></span>

<span data-ttu-id="21916-108">可用 Windows 10 上的[多应用指派访问](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)（相当于旧版 Microsoft Edge 的“普通浏览”展台模式类型）运行 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="21916-108">Microsoft Edge can be run with [multi-app assigned access](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) on Windows 10, which is the equivalent of Microsoft Edge Legacy "Normal browsing” kiosk mode type.</span></span> <span data-ttu-id="21916-109">要为 Microsoft Edge 配置多应用指派访问，请按照关于[如何设置多应用展台](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="21916-109">To configure Microsoft Edge with multi-app assigned access follow the instructions on how to [Set up a multi-app kiosk](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps).</span></span> <span data-ttu-id="21916-110">Microsoft Edge Stable 渠道的 AUMID 为 **MSEdge**。</span><span class="sxs-lookup"><span data-stu-id="21916-110">The AUMID for the Microsoft Edge Stable channel is **MSEdge**.</span></span>

<span data-ttu-id="21916-111">将 Microsoft Edge 用于多应用指派访问时，你可以使用 [Microsoft Edge 浏览器策略](microsoft-edge-policies.md)配置浏览体验以满足您的独特要求。</span><span class="sxs-lookup"><span data-stu-id="21916-111">When using Microsoft Edge with multi-app assigned access you can use the [Microsoft Edge browser policies](microsoft-edge-policies.md) to configure the browsing experience to meet your unique requirements.</span></span>

<span data-ttu-id="21916-112">Microsoft Edge 现在不支持同样用于单应用指派访问的旧版 Microsoft Edge 展台模式类型和多应用指派访问中的“公共浏览”展台模式类型。</span><span class="sxs-lookup"><span data-stu-id="21916-112">Today Microsoft Edge does not support the same Microsoft Edge Legacy kiosk mode types for single-app assigned access and the "Public browsing" kiosk mode type in multi-app assigned access.</span></span> <span data-ttu-id="21916-113">如果你需要适用于单应用指派访问展台设备的浏览器，我们建议使用[旧版 Microsoft Edge 展台模式](https://aka.ms/edgekioskmode)或 [Microsoft Kiosk Browser 应用](https://www.microsoft.com/p/kiosk-browser/9ngb5s5xg2kp?activetab=pivot:overviewtab)。</span><span class="sxs-lookup"><span data-stu-id="21916-113">If you need a browser for your single-app assigned access kiosk device, we recommend using [Microsoft Edge Legacy kiosk mode](https://aka.ms/edgekioskmode) or the [Microsoft Kiosk Browser app](https://www.microsoft.com/p/kiosk-browser/9ngb5s5xg2kp?activetab=pivot:overviewtab).</span></span> 

## <span data-ttu-id="21916-114">Microsoft Edge“--kiosk”命令行参数</span><span class="sxs-lookup"><span data-stu-id="21916-114">Microsoft Edge “--kiosk” command line parameter</span></span>

<span data-ttu-id="21916-115">你可以使用“`--kiosk`”命令行参数在展台模式下启动 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="21916-115">You can launch Microsoft Edge in kiosk mode using the “`--kiosk`” command line parameter.</span></span> <span data-ttu-id="21916-116">这样将以全屏方式打开浏览器，并禁用全屏快捷键 (F11)。</span><span class="sxs-lookup"><span data-stu-id="21916-116">This opens the browser in full screen with the full screen keyboard shortcut disabled (F11).</span></span> <span data-ttu-id="21916-117">为此，请创建一个快捷方式，并将其目标设置为：</span><span class="sxs-lookup"><span data-stu-id="21916-117">To accomplish this, create a shortcut with the target set to:</span></span><br>
*`"<local path>\msedge.exe" --kiosk http://bing.com`*

> [!NOTE]
> <span data-ttu-id="21916-118">“`--kiosk`”参数不阻止用户访问 Windows 快捷键，也不阻止其他应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="21916-118">The "`--kiosk`" parameter will not prevent the user from accessing Windows keyboard shortcuts and will not prevent other applications from running.</span></span> <span data-ttu-id="21916-119">要实现此类控制，请考虑使用 [AppLocker 创建 Windows 10 展台](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-applocker)和[键盘筛选器](https://docs.microsoft.com/windows-hardware/customize/enterprise/keyboardfilter)。</span><span class="sxs-lookup"><span data-stu-id="21916-119">To accomplish this type of control, consider using [AppLocker to create a Windows 10 kiosk](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-applocker) and [Keyboard Filter](https://docs.microsoft.com/windows-hardware/customize/enterprise/keyboardfilter).</span></span>

<span data-ttu-id="21916-120">要退出展台模式并关闭浏览器，请使用 alt+F4。</span><span class="sxs-lookup"><span data-stu-id="21916-120">To exit kiosk mode and close the browser use alt+F4.</span></span>

## <span data-ttu-id="21916-121">对旧版 Microsoft Edge 展台模式的支持</span><span class="sxs-lookup"><span data-stu-id="21916-121">Support for Microsoft Edge Legacy kiosk mode</span></span>

<span data-ttu-id="21916-122">安装 Microsoft Edge Stable 渠道的新版本后，将隐藏旧版 Microsoft Edge，并将所有尝试启动旧版 Microsoft Edge 的操作都重定向到新版本。</span><span class="sxs-lookup"><span data-stu-id="21916-122">When the new version of Microsoft Edge Stable channel is installed, Microsoft Edge Legacy is hidden and all attempts to launch Microsoft Edge Legacy are redirected to the new version.</span></span> <span data-ttu-id="21916-123">有关以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="21916-123">For information about:</span></span>

- <span data-ttu-id="21916-124">Windows 更新要求，请参阅[用于支持下一版本 Microsoft Edge 的 Windows 更新](microsoft-edge-sysupdate-windows-updates.md)</span><span class="sxs-lookup"><span data-stu-id="21916-124">Windows update requirements, see [Windows updates to support the next version of Microsoft Edge](microsoft-edge-sysupdate-windows-updates.md)</span></span> 
- <span data-ttu-id="21916-125">在安装 Microsoft Edge 后访问旧版 Microsoft Edge，请参阅[在安装 Microsoft Edge 的新版本后访问旧版 Microsoft Edge](microsoft-edge-sysupdate-access-old-edge.md)</span><span class="sxs-lookup"><span data-stu-id="21916-125">Accessing Microsoft Edge Legacy after installing Microsoft Edge,  see [Access Microsoft Edge Legacy after installing the new version of Microsoft Edge](microsoft-edge-sysupdate-access-old-edge.md)</span></span>
 
<span data-ttu-id="21916-126">要继续在展台设备上使用旧版 Microsoft Edge 展台模式，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="21916-126">To continue using Microsoft Edge Legacy kiosk mode on your kiosk devices take one of the following actions:</span></span> 

- <span data-ttu-id="21916-127">如果打算安装 Microsoft Edge Stable 渠道、要允许安装它或展台设备上已装有它，请部署 Microsoft Edge 的[允许 Microsoft Edge 并行浏览器体验](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allowsxs)策略。</span><span class="sxs-lookup"><span data-stu-id="21916-127">If you plan to install Microsoft Edge Stable channel, want to allow it to be installed, or if it's already installed on your kiosk device deploy the Microsoft Edge [Allow Microsoft Edge Side by Side browser experience](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allowsxs) policy.</span></span>
- <span data-ttu-id="21916-128">要阻止在展台设备上安装 Microsoft Edge Stable 渠道，请为 Stable 渠道部署 Microsoft Edge 的[允许安装默认项](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allow-installation-default)策略，或考虑使用[阻止程序工具包禁止自动传递 Microsoft Edge](microsoft-edge-blocker-toolkit.md)。</span><span class="sxs-lookup"><span data-stu-id="21916-128">To prevent Microsoft Edge Stable channel from being installed on your kiosk devices deploy the Microsoft Edge [Allow installation default](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allow-installation-default) policy for Stable channel or consider using the [Blocker toolkit to disable automatic delivery of Microsoft Edge](microsoft-edge-blocker-toolkit.md).</span></span> 

## <span data-ttu-id="21916-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21916-129">See also</span></span>

- [<span data-ttu-id="21916-130">在 Windows 桌面版中配置展台和数字签名</span><span class="sxs-lookup"><span data-stu-id="21916-130">Configure kiosks and digital signs on Windows desktop editions</span></span>](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [<span data-ttu-id="21916-131">部署旧版 Microsoft Edge 展台模式</span><span class="sxs-lookup"><span data-stu-id="21916-131">Deploy Microsoft Edge Legacy kiosk mode</span></span>](https://aka.ms/edgekioskmode) 
- [<span data-ttu-id="21916-132">规划 Microsoft Edge 部署</span><span class="sxs-lookup"><span data-stu-id="21916-132">Plan your deployment of Microsoft Edge</span></span>](deploy-edge-plan-deployment.md)
- [<span data-ttu-id="21916-133">Microsoft Edge Enterprise 着陆页</span><span class="sxs-lookup"><span data-stu-id="21916-133">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
