---
title: 使用 Windows 10 更新部署 Microsoft Edge
ms.author: ryhecht
author: RyanHechtMSFT
manager: tinad
ms.date: 05/04/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 使用 Windows 10 更新部署 Microsoft Edge
ms.openlocfilehash: eec21e3f797166b31b0ac632f94103b866491066
ms.sourcegitcommit: 592f6e40b13e28af588473b2a75c3ae697e5db2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2022
ms.locfileid: "12505685"
---
# <a name="deploy-microsoft-edge-with-windows-10-updates"></a>使用 Windows 10 更新部署 Microsoft Edge

本文为使用 Windows 10 更新部署 Microsoft Edge 的用户提供了相关信息。

## <a name="for-windows-10-release-20h2"></a>对于 Windows 10 版本 20H2

Windows 10 20H2 及更高版本包括Microsoft Edge预安装为默认浏览器。 但是，随 Windows 10 20H2 一起交付的 84 版 Edge 和 92 版带 Windows 10 21H2 的 Edge 现已过时。 虽然Microsoft Edge会在用户登录后自动将自己更新到较新版本，但由于更新的时间取决于各种因素，因此这可能有些不令人意外。 对于希望获得更大控制并且希望确保边缘 (稳定通道) 在用户登录之前更新到最新版本的组织，可以使用以下 PowerShell 命令在 Windows OOBE 期间强制进行 Edge 更新。

`Start-Process -FilePath "C:\Program Files (x86)\Microsoft\EdgeUpdate\MicrosoftEdgeUpdate.exe" -argumentlist "/silent /install appguid={56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}&appname=Microsoft%20Edge&needsadmin=True"`

如果使用 Windows Autopilot，则可以使用 [Microsoft Win32 内容准备工具](/mem/intune/apps/apps-win32-prepare)将此脚本包装为 .intunewin 文件。 然后，可以根据需要将其设置为注册状态页 (ESP) 的必需应用。

> [!NOTE]
> 如果当前利用[目标通道替代](/deployedge/microsoft-edge-update-policies#target-channel-override)或[目标版本替代](/deployedge/microsoft-edge-update-policies#targetversionprefix)等策略保留在较旧版本的Microsoft Edge上，请注意，上述脚本不会考虑任何策略，只需更新到最新版本。 默认情况下，Microsoft Edge不会自行降级，包括以后收到此类策略后。

## <a name="for-windows-10-releases-rs4-through-20h1"></a>适用于 Windows 10 版本 RS4 至 20H1

Windows Server Update Services (WSUS) 拥有每个 Windows 10 版本（从 RS4 至 20H1）的更新，这将删除 Microsoft Edge 旧版桌面应用并将其替换为 Microsoft Edge。 有关更多信息，请参阅[此支持文章](https://support.microsoft.com/topic/update-in-wsus-for-the-new-microsoft-edge-for-windows-10-version-1809-1903-1909-and-2004-october-29-2020-b4980418-4ec4-dee7-3b17-1c6499bd127c)，以了解适合于你的 Windows 版本的 WSUS 更新。

## <a name="for-windows-10-releases-prior-to-rs4-and-windows-7-81-and-earlier"></a>对于 RS4 之前的 Windows 10 版本（以及 Windows 7、8.1 及更早版本）

安装 Microsoft Edge 的 Windows 更新对这些版本不可用。 请考虑其他将 Microsoft Edge 部署到这些设备的选项，例如[配置管理器](/configmgr/apps/deploy-use/deploy-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)或 [Intune](/intune/apps/apps-windows-edge/?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [规划 Microsoft Edge 部署](deploy-edge-plan-deployment.md)
