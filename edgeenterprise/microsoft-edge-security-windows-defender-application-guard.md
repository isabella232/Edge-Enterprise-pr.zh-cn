---
title: Microsoft Edge 和 Microsoft Defender 应用程序防护
ms.author: srugh
author: dan-wesley
manager: seanlyn
ms.date: 06/19/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 对 Microsoft Defender 应用程序防护的支持
ms.openlocfilehash: 7bd2efd35e0cd65c524a17a88f659e9b3838233f
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979388"
---
# Microsoft Edge 对 Microsoft Defender 应用程序防护的支持

本文介绍 Microsoft Edge 如何支持 Microsoft Defender 应用程序防护（应用程序防护）。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## 概述

企业中的安全架构师必须处理生产力与安全性之间的矛盾。 锁定浏览器并且仅允许加载少数受信任的站点相对简单。 这种方法可改进整体安全状态，但生产力会降低。 如果你为提高生产力而减少限制，则会增加风险。 这很难达到平衡！

在不断变化的威胁形势下，即时了解新出现的威胁变得更加困难。 浏览器仍然是客户端设备上的主要攻击面，因为浏览器的基本任务是让用户访问、下载和打开来自不可信来源的不可信内容。 恶意参与者一直在忙于对浏览器进行新形式的社会工程攻击。 安全事件预防或检测/响应策略不能保证 100% 安全。

要考虑的一个关键安全策略是[假设失陷方法](https://docs.microsoft.com/office365/Enterprise/office-365-monitoring-and-testing#assume-breach-methodology)，这意味着用户接受无论如何努力地抵御攻击，该攻击总会成功一次的观念。 此思维方式要求建立防御机制来遏制损坏，这可确保企业网络和其他资源在这种情况下得到保护。  为 Microsoft Edge 部署应用程序防护符合此策略。

## 关于应用程序防护

专为 Windows 10 和 Microsoft Edge 设计，应用程序防护使用硬件隔离方法。 这种方法允许在容器中启动不受信任的站点导航。 硬件隔离可帮助企业保护其企业网络和数据，以防用户访问受到威胁或恶意的站点。

企业管理员定义什么是受信任的站点、云资源和内部网络。 不在受信任站点列表中的所有内容都被视为不可信内容。 这些站点与企业网络和用户设备上的数据相隔离。

有关详细信息，请参阅[什么是应用程序防护，以及它是如何工作的？](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview#what-is-application-guard-and-how-does-it-work)。

下一个屏幕截图显示应用程序防护的消息示例，它显示用户正在安全空间中浏览。

![应用程序防护安全浏览消息](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-1.png)

## 新增功能

新版 Microsoft Edge 浏览器中的应用程序防护支持与 Microsoft Edge 旧版具有同等的功能，并包括多项改进。

### 容器内的扩展支持

容器内的扩展支持是客户的首要请求之一。 场景范围从希望在容器内运行广告拦截器以提高浏览器性能，到能够在容器内运行自定义的本地扩展。

从 Microsoft Edge 版本 81 开始，现在支持在容器中安装扩展。 可通过策略控制此支持。 在 [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist) 策略中使用的 `updateURL` 应作为中性资源添加到应用程序防护使用的网络隔离策略中。

容器支持的一些示例包括以下场景：

- 强制在主机上安装扩展
- 从主机中删除扩展
- 主机上阻止的扩展

> [!NOTE]
> 也可以从扩展存储区中手动将单个扩展安装在容器内。 手动安装的扩展仅在启用“[允许持久性](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/configure-md-app-guard#application-specific-settings)”策略时才保留在容器中。

### 通过双代理识别应用程序防护流量

一些企业客户正在部署适用于特定用例的应用程序防护，他们需要识别来自 Microsoft Defender 应用程序防护容器的代理级别 web 流量。 从稳定渠道版本 84 开始，Microsoft Edge 将支持双代理来满足这一要求。 可使用 [ApplicationGuardContainerProxy](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#applicationguardcontainerproxy) 策略配置此功能。

下图显示了 Microsoft Edge 双代理的体系结构。

![应用程序防护的双代理体系结构](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-dual-proxy.png)

### 用于故障排除的诊断页面

用户的另一个痛点是在报告问题后对设备上的应用程序防护配置进行故障排除。 Microsoft Edge 有一个诊断页面 (`edge://application-guard-internals`)，用于对用户问题进行故障排除。 其中一个诊断功能是可以根据用户设备上的配置检查 URL 信任。

下一个屏幕截图显示了多选项卡诊断页面，用于帮助诊断用户在设备上报告的问题。

![应用程序防护诊断页面](media/microsoft-edge-security-windows-defender-application-guard/wd-application-guard-2.png)

### 容器中的 Microsoft Edge 更新

容器中的 Microsoft Edge 旧版更新是 Windows 操作系统更新周期的一部分。 由于新版本的 Microsoft Edge 更新独立于 Windows 操作系统，因此不再依赖于容器更新。 主机 Microsoft Edge 的频道和版本可在容器内复制。

## 必备条件

以下要求适用于将应用程序防护与 Microsoft Edge 配合使用的设备：

- Windows 10 1809 (RS5) 及更高版本。
- 仅 Windows 客户端 SKU

  > [!NOTE]
  > 应用程序防护仅在 Windows 10 专业版和 Windows 10 企业版 SKU 上受支持。

- [软件要求](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard#software-requirements)中介绍的管理解决方案之一

## 如何安装应用程序防护

以下文章提供了使用 Microsoft Edge 安装、配置和测试应用程序防护所需的信息。

- [系统要求](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)
- [安装 Microsoft Defender 应用程序防护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)
- [配置 Microsoft Defender 组策略设置](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/configure-md-app-guard)
- [测试应用程序防护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/test-scenarios-md-app-guard)

## 常见问题

### 应用程序防护是否可在 IE 模式下工作？

IE 模式支持应用程序防护功能，但我们预计不会在 IE 模式下过多地使用此功能。 建议为受信任的内部站点列表部署 IE 模式，而应用程序保护仅针对不受信任的站点。 确保所有 IE 模式的网站或 IP 地址也添加到网络隔离策略中，以便应用程序防护将其视为受信任的资源。

### 是否需要安装应用程序防护 Chrome 扩展？

否，Microsoft Edge 本身支持应用程序防护功能。 实际上，应用程序防护 Chrome 扩展配置在 Microsoft Edge 中不受支持。

### 是否有其他与平台相关的常见问题？

是。 [常见问题 - Microsoft Defender 应用程序防护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/faq-md-app-guard) 

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [安全性概述](security-overview.md)
- [Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
