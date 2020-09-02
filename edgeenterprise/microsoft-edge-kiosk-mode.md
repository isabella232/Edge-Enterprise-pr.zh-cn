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
# Microsoft Edge 展台模式

本文概述 Microsoft Edge（版本 77 或更高版本）展台模式选项。 它还涉及继续使用旧版 Microsoft Edge 展台模式（版本 45 和更低版本）需要做什么。

有关旧版 Microsoft Edge 展台模式（版本 45 和更早版本）的信息，请参阅[部署 Microsoft Edge 站台模式](https://aka.ms/edgekioskmode)。

## Microsoft Edge 与指派访问

可用 Windows 10 上的[多应用指派访问](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)（相当于旧版 Microsoft Edge 的“普通浏览”展台模式类型）运行 Microsoft Edge。 要为 Microsoft Edge 配置多应用指派访问，请按照关于[如何设置多应用展台](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)的说明进行操作。 Microsoft Edge Stable 渠道的 AUMID 为 **MSEdge**。

将 Microsoft Edge 用于多应用指派访问时，你可以使用 [Microsoft Edge 浏览器策略](microsoft-edge-policies.md)配置浏览体验以满足您的独特要求。

Microsoft Edge 现在不支持同样用于单应用指派访问的旧版 Microsoft Edge 展台模式类型和多应用指派访问中的“公共浏览”展台模式类型。 如果你需要适用于单应用指派访问展台设备的浏览器，我们建议使用[旧版 Microsoft Edge 展台模式](https://aka.ms/edgekioskmode)或 [Microsoft Kiosk Browser 应用](https://www.microsoft.com/p/kiosk-browser/9ngb5s5xg2kp?activetab=pivot:overviewtab)。 

## Microsoft Edge“--kiosk”命令行参数

你可以使用“`--kiosk`”命令行参数在展台模式下启动 Microsoft Edge。 这样将以全屏方式打开浏览器，并禁用全屏快捷键 (F11)。 为此，请创建一个快捷方式，并将其目标设置为：<br>
*`"<local path>\msedge.exe" --kiosk http://bing.com`*

> [!NOTE]
> “`--kiosk`”参数不阻止用户访问 Windows 快捷键，也不阻止其他应用程序运行。 要实现此类控制，请考虑使用 [AppLocker 创建 Windows 10 展台](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-applocker)和[键盘筛选器](https://docs.microsoft.com/windows-hardware/customize/enterprise/keyboardfilter)。

要退出展台模式并关闭浏览器，请使用 alt+F4。

## 对旧版 Microsoft Edge 展台模式的支持

安装 Microsoft Edge Stable 渠道的新版本后，将隐藏旧版 Microsoft Edge，并将所有尝试启动旧版 Microsoft Edge 的操作都重定向到新版本。 有关以下内容的信息：

- Windows 更新要求，请参阅[用于支持下一版本 Microsoft Edge 的 Windows 更新](microsoft-edge-sysupdate-windows-updates.md) 
- 在安装 Microsoft Edge 后访问旧版 Microsoft Edge，请参阅[在安装 Microsoft Edge 的新版本后访问旧版 Microsoft Edge](microsoft-edge-sysupdate-access-old-edge.md)
 
要继续在展台设备上使用旧版 Microsoft Edge 展台模式，请执行以下操作之一： 

- 如果打算安装 Microsoft Edge Stable 渠道、要允许安装它或展台设备上已装有它，请部署 Microsoft Edge 的[允许 Microsoft Edge 并行浏览器体验](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allowsxs)策略。
- 要阻止在展台设备上安装 Microsoft Edge Stable 渠道，请为 Stable 渠道部署 Microsoft Edge 的[允许安装默认项](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#allow-installation-default)策略，或考虑使用[阻止程序工具包禁止自动传递 Microsoft Edge](microsoft-edge-blocker-toolkit.md)。 

## 另请参阅

- [在 Windows 桌面版中配置展台和数字签名](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [部署旧版 Microsoft Edge 展台模式](https://aka.ms/edgekioskmode) 
- [规划 Microsoft Edge 部署](deploy-edge-plan-deployment.md)
- [Microsoft Edge Enterprise 着陆页](https://aka.ms/EdgeEnterprise)
