---
title: Microsoft Edge 中的数据丢失防护
ms.author: archandr
author: dan-wesley
manager: seanlynd
ms.date: 03/01/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 中的数据丢失防护 (DLP)
ms.openlocfilehash: ac34386ed1b691d7b45f30c2b2ec295955d11104
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447926"
---
# <a name="data-loss-prevention-dlp-in-microsoft-edge"></a>Microsoft Edge 中的数据丢失防护 (DLP)

数据丢失防护（DLP）是一套识别和保护企业敏感数据免受未经授权即泄露的技术系统。 为遵守商业标准和行业法规，组织必须保护敏感信息，防止其未经授权的泄露。 敏感信息包括财务数据或个人身份信息（PII），例如信用卡号码、社会保险号码或健康记录等。

远程工作更加强调使用DLP。 随着个人与工作活动在设备上的使用的增加，企业发现在工作场所之外未经授权共享企业数据的风险亦正在增加。

这种用户活动的融合也扩散到了设备上，数据通过各种公共和私有网络在个人和企业设备之间移动。 最终的结果是敏感数据暴露的风险大大增加。

Microsoft Edge 原身支持两种不同的DLP解决方案，即Microsoft Endpoint DLP和Windows信息保护（WIP）。

## <a name="microsoft-endpoint-data-loss-prevention-endpoint-dlp"></a>使用 Microsoft 终结点数据丢失防护（终结点 DLP）

Microsoft 终结点 DLP 是运用现代概念（例如以数据为中心的保护）的下一代数据丢失防护。 它内置在 Windows 10 和 Microsoft Edge 中，因此无需在设备上具备其他代理或插件。

> [!NOTE]
> 这适用于 Microsoft Edge 85 或更高版本。

若要了解有关终结点 DLP 的更多信息，请使用以下资源：

- [视频：Microsoft Edge 和数据丢失防护 (DLP)](microsoft-edge-video-security-dlp.md)
- [了解 Microsoft 365 终结点数据丢失防护](/microsoft-365/compliance/endpoint-dlp-learn-about?preserve-view=true&view=o365-worldwide)
- [终结点数据丢失防护入门](/microsoft-365/compliance/endpoint-dlp-getting-started?preserve-view=true&view=o365-worldwide)

Microsoft Edge 对敏感文件执行管理员配置的策略，并记录不合规活动的审核事件。

可在运行 Windows 10 的设备上审核和管理的用户活动包括以下活动：

- 文件上传：保护敏感文件上传到未经授权的云端位置。 <!-- The next 3 screenshots show a sequence where a user tries to drop a sensitive data file on to their local storage.-->
- 剪贴板保护：防止从文件中复制敏感数据。
- 打印保护：防止打印敏感文件。
- 保存到 USB/网络：防止可移动 USB 存储或未经授权的网络位置保存敏感文件。

有关可供审核和管理的用户活动的更多详细信息，请参阅[可监视并执行操作的端点活动](/microsoft-365/compliance/endpoint-dlp-learn-about?preserve-view=true&view=o365-worldwide#endpoint-activities-you-can-monitor-and-take-action-on)。

## <a name="windows-information-protection"></a>Windows 信息保护

查看 [对 Windows 信息保护](./microsoft-edge-security-windows-information-protection.md)的支持，其描述了 Microsoft Edge 支持 Windows 信息保护（WIP）的方式。 可在以下部分中了解系统要求、优点及支持的功能：

- [系统要求](./microsoft-edge-security-windows-information-protection.md#system-requirements)
- [Windows信息保护的优势](./microsoft-edge-security-windows-information-protection.md#windows-information-protection-benefits)
- [Microsoft Edge 支持的 WIP 功能](./microsoft-edge-security-windows-information-protection.md#wip-features-supported-in-microsoft-edge)

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [视频：数据丢失防护 - Microsoft Edge](https://www.youtube.com/watch?v=dLD04U9eTqg)
- [防止数据丢失概述](/microsoft-365/compliance/data-loss-prevention-policies?preserve-view=true&view=o365-worldwide)
- [使用 Windows 信息保护系统来保护企业数据](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)