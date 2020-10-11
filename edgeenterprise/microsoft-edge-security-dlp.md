---
title: Microsoft Edge 中的数据丢失防护
ms.author: archandr
author: dan-wesley
manager: seanlynd
ms.date: 10/08/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 中的数据丢失防护 (DLP)
ms.openlocfilehash: 59c1b68c0526a49a2ee30283893707852514828d
ms.sourcegitcommit: 2af303fc97e8493024e2359fa2e8be162ab95a59
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104600"
---
# Microsoft Edge 中的数据丢失防护 (DLP)

数据丢失防护（DLP）是一套识别和保护企业敏感数据免受未经授权即泄露的技术系统。 为遵守商业标准和行业法规，组织必须保护敏感信息，防止其未经授权的泄露。 敏感信息包括财务数据或个人身份信息（PII），例如信用卡号码、社会保险号码或健康记录等。

远程工作更加强调使用DLP。 随着个人与工作活动在设备上的使用的增加，企业发现在工作场所之外未经授权共享企业数据的风险亦正在增加。

这种用户活动的融合也扩散到了设备上，数据通过各种公共和私有网络在个人和企业设备之间移动。 最终的结果是敏感数据暴露的风险大大增加。

Microsoft Edge 原身支持两种不同的DLP解决方案，即Microsoft Endpoint DLP和Windows信息保护（WIP）。

## Microsoft Endpoint DLP

Microsoft Endpoint DLP 是新一代的DLP，其采用了以数据为中心的保护等现代概念。 其内置于 Windows 10 和 Microsoft Edge 中，因此不需要在设备上安装额外的代理或插件。 若要了解有关端点 DLP 的详细信息，请参阅 [了解 Microsoft 365 端点数据丢失防护](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide)。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 85 或更高版本。

Microsoft Edge 对敏感文件执行管理员配置的策略，并记录不合规活动的审计事件。

可在运行 Windows 10 的设备上审核和管理的用户活动包括以下活动：

- 文件上传：保护敏感文件上传到未经授权的云端位置。 接下来的3张屏幕截图显示了用户试图将敏感数据文件放到其本地存储上的序列。
- 剪贴板保护：防止从文件中复制敏感数据。
- 打印保护：防止打印敏感文件。
- 保存到 USB/网络：防止可移动 USB 存储或未经授权的网络位置保存敏感文件。

有关可供审核和管理的用户活动的更多详细信息，请参阅[可监视并执行操作的端点活动](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide#endpoint-activities-you-can-monitor-and-take-action-on)。

## Windows 信息保护

查看 [对 Windows 信息保护](https://docs.microsoft.com/deployedge/microsoft-edge-security-windows-information-protection)的支持，其描述了 Microsoft Edge 支持 Windows 信息保护（WIP）的方式。 可在以下部分中了解系统要求、优点及支持的功能：

- [系统要求](https://docs.microsoft.com/deployedge/:microsoft-edge-security-windows-information-protection#system-requirements)
- [Windows信息保护的优势](https://docs.microsoft.com/deployedge/microsoft-edge-security-windows-information-protection#windows-information-protection-benefits)
- [Microsoft Edge 支持的 WIP 功能](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-information-protection#wip-features-supported-in-microsoft-edge)

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [视频：数据丢失防护 - Microsoft Edge](https://www.youtube.com/watch?v=dLD04U9eTqg)
- [防止数据丢失概述](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide)
- [使用 Windows 信息保护系统来保护企业数据](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)
