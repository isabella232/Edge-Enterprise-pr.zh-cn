---
title: 使用 Windows 10 更新部署 Microsoft Edge
ms.author: ryhecht
author: RyanHechtMSFT
manager: tinad
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 使用 Windows 10 更新部署 Microsoft Edge
ms.openlocfilehash: 1f3a99259cb28c46e4f6f30de05fade6ac158336
ms.sourcegitcommit: 556aca8dde42dd66364427f095e8e473b86651a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2022
ms.locfileid: "12445826"
---
# <a name="deploy-microsoft-edge-with-windows-10-updates"></a>使用 Windows 10 更新部署 Microsoft Edge

本文为使用 Windows 10 更新部署 Microsoft Edge 的用户提供了相关信息。

## <a name="for-windows-10-release-20h2"></a>对于 Windows 10 版本 20H2

Windows 10 20H2 及更高版本Microsoft Edge预安装为默认浏览器。 但是，Windows 10 20H2 附带的 Edge 版本 84 和 Windows 10 21H2 附带的 Edge 版本 92 现已过时。 尽管Microsoft Edge在用户登录后会自动将自身更新到较新版本，但由于更新的时间取决于各种因素，因此这有些不成功。 对于希望获得更大控制权并且希望确保 Edge (Stable 渠道) 在用户登录之前更新到最新版本的组织，以下 PowerShell 命令可用于在 Windows OOBE 期间强制进行边缘更新。

`Start-Process -FilePath "C:\Program Files (x86)\Microsoft\EdgeUpdate\MicrosoftEdgeUpdate.exe" -argumentlist "/silent /install appguid={56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}&appname=Microsoft%20Edge&needsadmin=True"`

如果使用 Windows Autopilot，则有可能使用 [Microsoft Win32](/mem/intune/apps/apps-win32-prepare) 内容准备工具将此脚本打包为 .intunewin 文件。 然后，可以将它设置为 ESP 注册状态页的必需 (ESP) 应用。

> [!NOTE]
> 如果当前利用目标通道覆盖或[](/deployedge/microsoft-edge-update-policies#target-channel-override)目标版本覆盖等[](/deployedge/microsoft-edge-update-policies#targetversionprefix)策略保留在较旧版本的边缘上，请注意，上述脚本不会考虑任何策略，只会更新到最新版本。 默认情况下，Edge 不会降级自身，包括以后收到此类策略后。

## <a name="for-windows-10-releases-rs4-through-20h1"></a>适用于 Windows 10 版本 RS4 至 20H1

Windows Server Update Services (WSUS) 拥有每个 Windows 10 版本（从 RS4 至 20H1）的更新，这将删除 Microsoft Edge 旧版桌面应用并将其替换为 Microsoft Edge。 有关更多信息，请参阅[此支持文章](https://support.microsoft.com/topic/update-in-wsus-for-the-new-microsoft-edge-for-windows-10-version-1809-1903-1909-and-2004-october-29-2020-b4980418-4ec4-dee7-3b17-1c6499bd127c)，以了解适合于你的 Windows 版本的 WSUS 更新。

## <a name="for-windows-10-releases-prior-to-rs4-and-windows-7-81-and-earlier"></a>对于 RS4 之前的 Windows 10 版本（以及 Windows 7、8.1 及更早版本）

安装 Microsoft Edge 的 Windows 更新对这些版本不可用。 请考虑其他将 Microsoft Edge 部署到这些设备的选项，例如[配置管理器](/configmgr/apps/deploy-use/deploy-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)或 [Intune](/intune/apps/apps-windows-edge/?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [规划 Microsoft Edge 部署](deploy-edge-plan-deployment.md)
