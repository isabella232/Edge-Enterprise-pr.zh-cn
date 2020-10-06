---
title: 适用于企业的 Microsoft Edge 安全
ms.author: seanlynd
author: seanongit
manager: chuckf
ms.date: 10/02/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 适用于企业的 Microsoft Edge 安全
ms.openlocfilehash: 018353c4f85bc380d85554d058d029dfde959257
ms.sourcegitcommit: 3478cfcf2b03944213a7c7c61f05490bc37aa7c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2020
ms.locfileid: "11094736"
---
# 适用于企业的 Microsoft Edge 安全

Microsoft Edge 建立在 Chromium 开放源代码项目（与 Google Chrome 核心相同的项目）之上，这意味着它在其基础上共享同样经过精心设计和测试的安全体系结构和设计。 Microsoft Edge 安全案例并不就此止步。 事实上，**对于使用 Windows 10 的企业来说， Microsoft Edge 比 Google Chrome 更安全**。 它具有强大的内置防御功能，可抵御网络钓鱼和恶意软件，并且本机支持 Windows 10 上的硬件隔离 — 实现这一安全基准不需要其他软件。 此外，当与 Microsoft 365 安全和合规性服务的本机支持配合使用时，Microsoft Edge 提供了额外的强大安全功能和特性，有助于防止数据丢失，从而获得更多好处。

让我们详细了解一下，从**外部威胁**开始，然后再看看**内部风险和信息保护**。

## 外部威胁防护

### 抵御网站钓鱼和恶意软件的最高级别防护

根据 [NSS Labs 的一项独立研究](https://www.nsslabs.com/tested-technologies/web-browser-security-wbs/)，相比 Google Chrome 的安全浏览，内置在 Microsoft Edge 中的 SmartScreen 可阻止更多的网络钓鱼和恶意软件尝试。 SmartScreen 可在用户联机工作时提供网站和下载的实时信誉检查，它是 [Microsoft Intelligent Security Graph](https://www.microsoft.com/microsoft-365/windows/intelligent-security) 的一部分，它汲取从 Microsoft 庞大的全球资产、研究人员和合作伙伴网络产生的信号和见解。 通过对基于云的动态危险网站和下载列表进行检查，Microsoft Edge 有助于检测和阻止快速消失的短暂威胁。  

[在 NSS Labs 测试期间](https://www.nsslabs.com/tested-technologies/web-browser-security-wbs/)，[带有 SmartScreen 的 Microsoft Edge](https://docs.microsoft.com//DeployEdge/microsoft-edge-security-smartscreen) 阻止了 95.5% 的网络钓鱼尝试和 98.5% 的恶意软件尝试，而 Chrome 安全浏览的比率分别为 86.9% 和86.0%。

### Windows 10 上唯一本机支持硬件隔离的浏览器

Microsoft Edge 是 Windows 10 上唯一本机支持硬件隔离功能的浏览器。 作为 Windows 10 专业版或企业版的一部分，Microsoft Defender 应用程序防护（简称“应用程序防护”）在与本地设备和内部网络隔离的内核中运行不受信任的网站。 不受信任的网站在“容器”中运行，因此当发生攻击时，它将从公司网络的其余部分沙盒化。 有关详细信息，请参阅 [Microsoft Edge 对应用程序防护的支持](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-defender-application-guard)。

对于Chrome，可以使用扩展来利用 Windows 10 硬件隔离 - MDAG 扩展。 此扩展将启动 Microsoft Edge，以便利用应用程序防护的内核级别隔离。 此外，要为仅使用 Chrome 的解决方案实现类似的内核级别隔离，需要第三方隔离软件。

> [!NOTE]
> 应用程序防护适用于 Windows 10、1809 和更高版本。 应用程序防护在 Windows 10 家庭版中不可用。

## 内部风险和信息保护

### 无需其他软件即可对 Microsoft 365 安全提供本机支持

除了抵御外部威胁之外，IT 管理员还必须防范内部风险。 可靠且大规模地保护敏感公司数据是 IT 管理员的头等大事，尤其是在劳动力分散的情况下。 Microsoft Edge 是唯一一个无需其他软件即可本机支持 Azure AD 条件访问、Windows 信息保护和新的 Microsoft 端点数据丢失防护 (DLP) 的浏览器。

**Microsoft Edge 是唯一本机支持条件访问的浏览器**。 [Microsoft Edge 对条件访问的支持](ms-edge-security-conditional-access.md)使组织可以轻松地将身份信号用作其访问控制决策的一部分。 [条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)是 Azure Active Directory 工具用于将信号聚集在一起、制定决策和执行组织策略的工具。 条件访问是新的身份驱动控制平面的核心。 若要在 Chrome 上获得条件访问支持，需使用额外插件。

> [!NOTE]
> Azure AD 条件访问需要 Microsoft 365 E3 或更高版本的订阅。

**Microsoft Edge 是唯一一款本机支持 Windows 信息保护 (WIP)** 的浏览器，它为公司数据提供保护，以帮助防止 Windows 10 设备上的用户意外泄露。 可以将 [Microsoft Edge 对 WIP 的支持](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-information-protection)配置为仅允许 IT 强制应用访问公司数据。 它还提供了泄露控制功能，例如剪贴板保护、下载时加密文件以及防止文件上传到未经授权的网络共享或云位置，可实现无缝的用户体验。 WIP 使用基于外围的配置，其中 IT 管理员定义公司边界，并且该边界内的所有数据都被视为公司数据。 Chrome 未针对带有泄露控制的 WIP 进行优化。

> [!NOTE]
> Windows 信息保护 (WIP) 配置要求许可 Microsoft Intune 或 Microsoft Endpoint Configuration Manager，或者使用第三方移动设备管理 (MDM) 解决方案，这可能有额外的许可要求。

**Microsoft Endpoint DLP 10 月正式上市时将仅在 Microsoft Edge 上受本机支持**。 Microsoft 端点数据丢失防护 (DLP) 与 Microsoft 安全中心集成，并将信息保护扩展到 Microsoft Edge，以帮助警告用户不符合要求的活动，并防止用户在联机工作时丢失数据。 它可以发现并标记企业内部符合管理员定义的标准的敏感数据，例如包含信用卡号或政府 ID（例如身份证号）、财务信息等的文件。Microsoft 信息保护策略可以部署到 Microsoft Endpoint DLP，而无需进行额外的重新配置，包括敏感内容标识符和 IT 管理员已自定义的策略。 这是面向 IT 管理员的信息保护无缝部署。

> [!NOTE]
> Microsoft 端点数据丢失防护需要 Microsoft 365 E5 或 Microsoft 365 E5 合规性订阅。

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
