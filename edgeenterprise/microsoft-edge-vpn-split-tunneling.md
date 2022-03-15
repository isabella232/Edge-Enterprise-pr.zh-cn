---
title: Microsoft Edge WebRTC 的拆分隧道 VPN 支持
ms.author: juso
author: dan-wesley
manager: harneets
ms.date: 01/24/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: '启用Microsoft Edge WebRTC (Web Real-Time 通信) '
ms.openlocfilehash: 73bd6494ebb95db23d2701cc9dab4023af28eb70
ms.sourcegitcommit: 556aca8dde42dd66364427f095e8e473b86651a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2022
ms.locfileid: "12445896"
---
# <a name="split-tunnel-vpn-support-for-webrtc-web-real-time-communication"></a>拆分隧道 VPN 支持 WebRTC (Web Real-Time 通信) 
  
本文介绍了如何Microsoft Edge WebRTC 的拆分隧道 VPN 支持。 通过此支持，企业客户可以受益于 VPN 拆分隧道，适用于 Microsoft Edge。 VPN 拆分隧道可提高用户的对等媒体流质量并减少 VPN 服务器负载。

> [!NOTE]
> 本文适用于 Microsoft Edge版本 96 或更高版本。

## <a name="what-is-vpn-split-tunneling-and-why-should-i-use-it"></a>什么是 VPN 拆分隧道？为什么应该使用它？

VPN 拆分隧道是一项功能，允许用户将两个不同的网络用于流量，而不是通过 VPN 路由所有流量。 Windows本机应用程序支持此功能，并且通过 Windows 上的 VPN 拆分隧道为 Microsoft 365 应用程序提供了 VPN 拆分Windows。 有关详细信息，请参阅[概述：VPN 拆分隧道与 Office 365 - Microsoft 365 企业版](/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel?view=o365-worldwide&preserve-view=true)。 Microsoft Edge还遵守 VPN 拆分隧道配置，但缺少对对等流量的支持。

我们了解客户需要通过他们的企业网络或云基础结构通过 VPN 路由对等用户流量。与本机应用程序相比，用户对浏览器上的视频会议呼叫质量感到沮丧。如本机体验所展示的，对等流量的 VPN 拆分隧道可以通过正常的 Internet 连接（而不是 VPN）路由用户视频呼叫，提高用户视频呼叫的质量。 它还可以通过路由 VPN 上的指定流量来降低总体 VPN 服务器负载。 Microsoft Edge，现在可以为企业客户带来此对等流量改进。

## <a name="how-to-configure-vpn-split-tunneling-on-microsoft-edge"></a>如何在网络上配置 VPN 拆分Microsoft Edge

若要启用 VPN 拆分隧道并配置用户网络，我们建议你从实现 Office 365 [- Microsoft 365 企业版 的 VPN 拆分隧道中的指南开始](/microsoft-365/enterprise/microsoft-365-vpn-implement-split-tunnel?view=o365-worldwide&preserve-view=true)。 在基于上一篇文章中所述的信息配置正确的路由表后，只需执行其他步骤来启用 [WebRtcRespectOsRoutingTableEnabled](/deployedge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) 策略。 此策略支持在Windows WebRTC 建立对等连接时对操作系统路由表规则的支持。 现在，你已准备好在 Microsoft Edge 上提供改进的对等媒体流Microsoft Edge！

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
