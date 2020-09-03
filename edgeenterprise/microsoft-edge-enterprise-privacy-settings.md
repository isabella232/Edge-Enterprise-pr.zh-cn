---
title: Microsoft Edge 企业隐私设置
ms.author: likravit
author: dan-wesley
manager: srugh
ms.date: 05/26/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 配置 Microsoft Edge 企业隐私设置
ms.openlocfilehash: 2b7a33087ae5110c53d18b3192486d4ae62fa540
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979358"
---
# 配置 Microsoft Edge 策略以支持企业隐私

Microsoft 致力于为企业提供在 Microsoft Edge 中进行与数据收集相关的选择所需的信息和控制。

## 概述

默认情况下，部署在非 Windows 平台上的 Microsoft Edge 不会将诊断数据或网站信息发送到 Microsoft。 将 Microsoft Edge 部署到 Windows 10 时，默认会根据用户的 [Windows 诊断数据设置](https://go.microsoft.com/fwlink/?linkid=2099569)发送诊断数据。

你也可以使用以下组策略配置 Microsoft Edge 处理组织数据收集的方式：

- [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled)：启用使用情况和故障相关数据报告。
- [SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices)：发送站点信息以改进 Microsoft 服务。

## 配置策略设置

开始之前，请先下载并使用最新的 Microsoft Edge 策略模板（有关详细信息，请参阅[配置 Microsoft Edge](configure-microsoft-edge.md)。）

### 启用使用情况和故障相关数据报告

此策略允许向 Microsoft 发送关于 Microsoft Edge 的使用情况和故障相关数据的报告。

Microsoft Edge 收集一系列必需的数据，以确保产品保持最新状态、安全可靠且正常运行。 此数据包括来自 Microsoft Edge 的有关 Microsoft Edge 安装的当前数据收集许可、应用版本和安装状态的基本设备连接和配置信息。通过禁用策略可关闭此数据集合。

启用此策略可向 Microsoft 发送使用情况和故障相关数据的报告。 禁用此策略可以不将数据发送给 Microsoft。 在这两种情况下，用户不能更改或覆盖设置。

在 Windows 10 上运行 Microsoft Edge 时：

- 如果未配置此策略，Microsoft Edge 将默认使用 Windows 诊断数据设置。
- 如果启用此策略，则只有将 Windows 诊断数据设置设为**增强**或**完整**时，Microsoft Edge 才会发送使用情况数据。
- 如果禁用此策略，Microsoft Edge 将不会发送使用情况数据。 基于 Windows 诊断数据设置发送故障相关数据。 [详细了解 Windows 诊断数据设置](https://go.microsoft.com/fwlink/?linkid=2099569)。

在 Windows 7、8 和 macOS 上运行 Microsoft Edge 时：

- 如果未配置此策略，Microsoft Edge 将默认使用用户的首选项。

### 发送站点信息以改进 Microsoft 服务

此策略支持将有关在 Microsoft Edge 中访问的网站的信息发送到 Microsoft，以改进 Microsoft 产品和服务（如搜索）。

启用此策略可将有关在 Microsoft Edge 中访问的网站的信息发送到 Microsoft。 禁用此策略以便不将有关在 Microsoft Edge 中访问的网站的信息发送到 Microsoft。 在这两种情况下，用户不能更改或覆盖设置。

在 Windows 10 上运行 Microsoft Edge 时：

- 如果未配置此策略，Microsoft Edge 将默认使用 Windows 诊断数据设置。
- 如果启用此策略，则只有将 Windows 诊断数据设置设为**完整**时，Microsoft Edge 才会发送有关所访问网站的信息。
- 如果禁用此策略，Microsoft Edge 将不会发送有关所访问网站的信息。 要[详细了解 Windows 诊断数据设置](https://go.microsoft.com/fwlink/?linkid=2099569)，请执行以下操作。

在 Windows 7、8 和 macOS 上运行 Microsoft Edge 时：

- 如果未配置此策略，Microsoft Edge 将默认使用用户的首选项。

## 实现详细信息

为了让 Windows 10 了解我们的实现及其对 Windows 诊断数据设置的依赖性，下表介绍了相关配置（如果未配置**启用使用情况和故障相关数据报告**和**发送站点信息以改进 Microsoft 服务**）。

| Windows 诊断数据设置 | 启用使用情况和故障相关数据报告 | 发送站点信息以改进 Microsoft 服务 |
|---------------------------------|-----------------------------------------------|-----------------------------------------------------|
| 安全性                        | 未发送                                      | 未发送                                            |
| 基本                           | 未发送                                      | 未发送                                            |
| 增强                        | 已发送                                          | 未发送                                            |
| 完整                            | 已发送                                          | 已发送                                                |

根据先前的表，如果 Windows 10 的配置不正确，我们将恢复为较小的数据收集设置。

例如：

- 将“启用使用情况和故障相关数据报告”策略设置为**已启用**，但将 Windows 诊断数据设置设为**基本**。 我们不会发送使用情况和故障相关数据。
- 已将“发送网站信息以改进 Microsoft 服务”策略设置为**已禁用**，但将 Windows 诊断数据设置设为**完整**。 我们不会发送有关所访问网站的信息。

对先前设置的正确实现方法是将“启用使用情况和故障相关数据报告”策略设为**已启用**，然后将 Windows 诊断数据设置设为**增强**或**完整**。

## 其他隐私策略选项

你可能需要考虑以下与数据隐私相关的组策略：

- 在特定站点上阻止 Cookie
- 阻止第三方 Cookie
- 配置 Do Not Track
- 禁用 InPrivate 模式

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 策略](microsoft-edge-policies.md)
- [Microsoft Edge 隐私白皮书](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper)
