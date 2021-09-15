---
title: Microsoft Edge 企业隐私设置
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 配置 Microsoft Edge 企业隐私设置
ms.openlocfilehash: b5b07353af558e3832cb7a08c647fa111a14a404
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "11978913"
---
# <a name="configure-microsoft-edge-policies-to-support-enterprise-privacy"></a>配置 Microsoft Edge 策略以支持企业隐私

Microsoft 致力于为企业提供在 Microsoft Edge 中进行与数据收集相关的选择所需的信息和控制。

## <a name="overview"></a>概述

将 Microsoft Edge 部署到 Windows 10 时，默认会根据用户的 [Windows 诊断数据设置](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)发送诊断数据。

将 Microsoft Edge 部署到非 Windows 平台上时，将按照以下组策略的设置收集诊断数据：

- （已弃用）[MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled)：启用使用情况和故障相关数据报告。 此策略将在 Microsoft Edge 版本 89 中过时。
- （已弃用）[SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices)：发送站点信息以改进 Microsoft 服务。 此策略将在 Microsoft Edge 版本 89 中过时。

之前已弃用的策略将被 Windows 10 上的[允许遥测](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)和所有其他平台的[DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) 策略取代。  

## <a name="configure-policy-settings"></a>配置策略设置

开始之前，请先下载并使用最新的 Microsoft Edge 策略模板（有关详细信息，请参阅[配置 Microsoft Edge](configure-microsoft-edge.md)。）

### <a name="send-required-and-optional-diagnostic-data-about-browser-usage"></a>发送有关浏览器使用情况的必需和可选诊断数据

如果已配置 [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) 策略，则其优先级高于 [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) 和[SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices)。

#### <a name="required-and-optional-diagnostic-data"></a>必需和可选诊断数据

收集必需诊断数据可确保 Microsoft Edge 安全、最新且按预期运行。

可选诊断数据包括有关如何使用浏览器、访问的网站和崩溃报告的数据，以帮助保持 Microsoft Edge 安全、最新且按预期运行，同时用于为所有用户改进 Microsoft Edge 和其他 Microsoft 产品和服务。

> [!NOTE]
> Windows 10 设备不支持此策略。 若要在 Windows 10 上控制此数据收集，IT 管理员必须使用 Windows 诊断数据组策略。 根据 Windows 版本的不同，此策略将为**允许遥测**或**允许诊断数据**。 详细了解 [Windows 10 诊断数据收集](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)。

使用以下设置之一配置 **DiagnosticData**：

- 关闭（不推荐）(0) 会关闭必需和可选诊断数据收集。 
- 必需数据 (1) 会发送必需诊断数据，但关闭可选诊断数据收集。 Microsoft Edge 会发送必需诊断数据，以确保 Microsoft Edge 安全、最新且按预期运行。 
- 可选数据 (2) 会发送可选诊断数据，包括有关浏览器使用情况、访问的网站和发送到 Microsoft 的崩溃报告的数据，以帮助保持 Microsoft Edge 安全、最新且按预期运行，同时用于为所有用户改进 Microsoft Edge 和其他 Microsoft 产品和服务。

对于 Windows 7、Windows 8/8.1 和 macOS，此策略控制向 Microsoft 发送必需和可选数据。

如果未配置或已禁用此策略，Microsoft Edge 将默认使用用户首选项。

### <a name="deprecated-enable-usage-and-crash-related-data-reporting"></a>（已弃用）启用使用情况和故障相关数据报告

**MetricsReportingEnabled** 策略允许向 Microsoft 发送关于 Microsoft Edge 的使用情况和故障相关数据的报告。

Microsoft Edge 收集一系列必需的数据，以确保产品保持最新状态、安全可靠且正常运行。 此数据包括来自 Microsoft Edge 的有关 Microsoft Edge 安装的当前数据收集许可、应用版本和安装状态的基本设备连接和配置信息。通过禁用策略可关闭此数据集合。

启用此策略可向 Microsoft 发送使用情况和故障相关数据的报告。 禁用此策略可以不将数据发送给 Microsoft。 在这两种情况下，用户不能更改或覆盖设置。

在 Windows 10 上运行 Microsoft Edge 时：

- 如果未配置此策略，Microsoft Edge 将默认使用 Windows 诊断数据设置。
- 如果启用此策略，则只有将 Windows 诊断数据设置设为**增强**或**完整**时，Microsoft Edge 才会发送使用情况数据。
  - 如果启用此策略，Microsoft Edge 将仅发送使用情况数据（如果 [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) 也处于启用状态）。
- 如果禁用此策略，Microsoft Edge 将不会发送使用情况数据。 基于 Windows 诊断数据设置发送故障相关数据。 [详细了解 Windows 诊断数据设置](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)。

在 Windows 7、8 和 macOS 上运行 Microsoft Edge 时：

- 如果未配置此策略，Microsoft Edge 将默认使用用户的首选项。
-  如果启用此策略，Microsoft Edge 将仅发送使用情况数据（如果 [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) 也处于启用状态）。

### <a name="deprecated-send-site-information-to-improve-microsoft-services"></a>（已弃用）发送站点信息以改进 Microsoft 服务

**SendSiteInformationToImproveServices** 策略允许向 Microsoft 发送关于在 Microsoft Edge 中访问的网站的信息，以改进 Microsoft 产品和服务（如搜索）。

启用此策略可将有关在 Microsoft Edge 中访问的网站的信息发送到 Microsoft。 禁用此策略以便不将有关在 Microsoft Edge 中访问的网站的信息发送到 Microsoft。 在这两种情况下，用户不能更改或覆盖设置。

在 Windows 10 上运行 Microsoft Edge 时：

- 如果未配置此策略，Microsoft Edge 将默认使用 Windows 诊断数据设置。
- 如果启用此策略，则只有将 Windows 诊断数据设置设为**完整**时，Microsoft Edge 才会发送有关所访问网站的信息。
  - 如果启用此策略，Microsoft Edge 将仅发送使用情况数据（如果 [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) 也处于启用状态）。 
- 如果禁用此策略，Microsoft Edge 将不会发送有关所访问网站的信息。 要[详细了解 Windows 诊断数据设置](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)，请执行以下操作。

在 Windows 7、8 和 macOS 上运行 Microsoft Edge 时：

- 如果启用此策略，Microsoft Edge 将仅发送使用情况数据（如果 [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) 也处于启用状态）。
- 如果未配置此策略，Microsoft Edge 将默认使用用户的首选项。

## <a name="implementation-details"></a>实现详细信息

对于非 Windows 10 设备： 
- 如果已配置 [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) 策略，则其优先级高于 [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) 和[SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices)。 
- 如果未配置 [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) 策略，Microsoft Edge将侦听 [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) 和[SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices)。  

为了让 Windows 10 了解我们依赖 Windows 诊断数据设置的实现，下表列出了是否将 **必需**和**可选** 诊断数据发送到 Microsoft。

| Windows 诊断数据设置 | 必需诊断数据  | 可选诊断数据 |
|---------------------------------|-----------------------------------------------|-----------------------------------------------------|
| 安全性                        | 未发送                                      | 未发送                                            |
| 基本                           | 已发送                                      | 未发送                                            |
| 增强                        | 已发送                                          | 未发送                                            |
| 完整                            | 已发送                                          | 已发送                                                |

> [!IMPORTANT]
> Microsoft Edge 将支持适用于 Microsoft Edge 版本86 – 88（含）的 **MetricsReportingEnabled**  和** SendSiteInfoToImproveServices**。 在 Microsoft Edge 版本 89 中，将不再支持 **MetricsReportingEnabled**  和 **SendSiteInfoToImproveServices**，并且将默认为非 Windows 10 平台使用 **DiagnosticData**，或默认为 Windows 10 使用**允许遥测**策略。

## <a name="additional-privacy-policy-options"></a>其他隐私策略选项

你可能需要考虑以下与数据隐私相关的组策略：

- 在特定站点上阻止 Cookie
- 阻止第三方 Cookie
- 配置 Do Not Track
- 禁用 InPrivate 模式

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 策略](microsoft-edge-policies.md)
- [Microsoft Edge 隐私白皮书](/microsoft-edge/privacy-whitepaper)