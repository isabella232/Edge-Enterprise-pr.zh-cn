---
title: 适用于企业的 Microsoft Edge 安全
ms.author: collw
author: seanongit
manager: chuckf
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 适用于企业的 Microsoft Edge 安全
ms.openlocfilehash: f3ed91c76cb686b0ce67608f749817cce48b412831f29c7734fa0eec06694dd5
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "11727385"
---
# <a name="microsoft-edge-security-for-your-business"></a>适用于企业的 Microsoft Edge 安全

Microsoft Edge 建立在 Chromium 开放源代码项目（与 Google Chrome 核心相同的项目）之上，这意味着它在其基础上共享同样经过精心设计和测试的安全体系结构和设计。 Microsoft Edge 安全案例并不就此止步。 事实上，**对于使用 Windows 10 的企业来说， Microsoft Edge 比 Google Chrome 更安全**。 它具有强大的内置防御功能，可抵御网络钓鱼和恶意软件，并且本机支持 Windows 10 上的硬件隔离 — 实现这一安全基准不需要其他软件。 此外，当与 Microsoft 365 安全和合规性服务的本机支持配合使用时，Microsoft Edge 提供了额外的强大安全功能和特性，有助于防止数据丢失，从而获得更多好处。 有关详细信息，请观看[视频：Microsoft Edge 安全性、兼容性和可管理性](microsoft-edge-video-security-compatibility-manageability.md)。

让我们详细了解一下，从**外部威胁**开始，然后再看看**内部风险和信息保护**。

## <a name="external-threat-protection"></a>外部威胁防护

### <a name="highest-rated-protection-against-phishing-and-malware"></a>抵御网站钓鱼和恶意软件的最高级别防护

根据 NSS Labs 的一项独立研究，相比 Google Chrome 的安全浏览，内置在 Microsoft Edge 中的 SmartScreen 可阻止更多的[网络钓鱼](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWASN1)和[恶意软件](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWANMW)企图。 SmartScreen 可在用户联机工作时提供网站和下载的实时信誉检查，它是 [Microsoft Intelligent Security Graph](https://www.microsoft.com/microsoft-365/windows/intelligent-security) 的一部分，它汲取从 Microsoft 庞大的全球资产、研究人员和合作伙伴网络产生的信号和见解。 通过对基于云的动态危险网站和下载列表进行检查，Microsoft Edge 有助于检测和阻止快速消失的短暂威胁。  

在[NSS Labs的网络钓鱼防护](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWASN1)测试期间，[Microsoft Edge SmartScreen](//DeployEdge/microsoft-edge-security-smartscreen) 阻止了 95.5% 的网络钓鱼尝试，在[NSS Labs的恶意软件保护](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWANMW)测试期间阻止了 98.5% 的恶意软件尝试，而 Chrome 的安全浏览率分别为 86.9% 和 86.0%。

### <a name="the-only-browser-on-windows-10-that-natively-supports-hardware-isolation"></a>Windows 10 上唯一本机支持硬件隔离的浏览器

Microsoft Edge 是 Windows 10 上唯一本机支持硬件隔离功能的浏览器。 作为 Windows 10 专业版或企业版的一部分，Microsoft Defender 应用程序防护（简称“应用程序防护”）在与本地设备和内部网络隔离的内核中运行不受信任的网站。 不受信任的网站在“容器”中运行，因此当发生攻击时，它将从公司网络的其余部分沙盒化。 有关详细信息，请参阅 [Microsoft Edge 对应用程序防护的支持](./microsoft-edge-security-windows-defender-application-guard.md)。

对于Chrome，可以使用扩展来利用 Windows 10 硬件隔离 - MDAG 扩展。 此扩展将启动 Microsoft Edge，以便利用应用程序防护的内核级别隔离。 此外，要为仅使用 Chrome 的解决方案实现类似的内核级别隔离，需要第三方隔离软件。

> [!NOTE]
> 应用程序防护适用于 Windows 10、1809 和更高版本。 应用程序防护在 Windows 10 家庭版中不可用。

## <a name="internal-risks-and-information-protection"></a>内部风险和信息保护

### <a name="native-support-for-microsoft-365-security-without-additional-software"></a>无需其他软件即可对 Microsoft 365 安全提供本机支持

除了抵御外部威胁之外，IT 管理员还必须防范内部风险。 可靠且大规模地保护敏感公司数据是 IT 管理员的头等大事，尤其是在劳动力分散的情况下。 Microsoft Edge 是唯一一个无需其他软件即可本机支持 Azure AD 条件访问、Windows 信息保护和新的 Microsoft 端点数据丢失防护 (DLP) 的浏览器。

**Microsoft Edge 是唯一本机支持条件访问的浏览器**。 [Microsoft Edge 对条件访问的支持](ms-edge-security-conditional-access.md)使组织可以轻松地将身份信号用作其访问控制决策的一部分。 [条件访问](/azure/active-directory/conditional-access/overview)是 Azure Active Directory 工具用于将信号聚集在一起、制定决策和执行组织策略的工具。 条件访问是新的身份驱动控制平面的核心。 若要在 Chrome 上获得条件访问支持，需使用额外插件。

> [!NOTE]
> Azure AD 条件访问需要 Microsoft 365 E3 或更高版本的订阅。

**Microsoft Edge 是唯一一款本机支持 Windows 信息保护 (WIP)** 的浏览器，它为公司数据提供保护，以帮助防止 Windows 10 设备上的用户意外泄露。 可以将 [Microsoft Edge 对 WIP 的支持](./microsoft-edge-security-windows-information-protection.md)配置为仅允许 IT 强制应用访问公司数据。 它还提供了泄露控制功能，例如剪贴板保护、下载时加密文件以及防止文件上传到未经授权的网络共享或云位置，可实现无缝的用户体验。 WIP 使用基于外围的配置，其中 IT 管理员定义公司边界，并且该边界内的所有数据都被视为公司数据。 Chrome 未针对带有泄露控制的 WIP 进行优化。

> [!NOTE]
> Windows 信息保护 (WIP) 配置要求许可 Microsoft Intune 或 Microsoft Endpoint Configuration Manager，或者使用第三方移动设备管理 (MDM) 解决方案，这可能有额外的许可要求。

**Microsoft 终结点数据丢失防护（终结点 DLP）仅在 Microsoft Edge 中以本机方式受到支持**。 终结点 DLP 与 Microsoft 安全中心集成并将信息保护扩展到 Microsoft Edge，从而帮助就不合规的活动提醒用户，并在用户联机工作时防止数据丢失。 它可以发现并标记企业内部符合管理员定义的标准的敏感数据，例如包含信用卡号或政府 ID（例如身份证号）、财务信息等的文件。Microsoft 信息保护策略可以部署到 Microsoft Endpoint DLP，而无需进行额外的重新配置，包括敏感内容标识符和 IT 管理员已自定义的策略。 这是面向 IT 管理员的信息保护无缝部署。

若要详细了解终结点 DLP 的先决条件及其设置方式，请转到[终结点数据丢失防护入门](/microsoft-365/compliance/endpoint-dlp-getting-started?preserve-view=true&view=o365-worldwide)。

> [!NOTE]
> 要使用 Microsoft 终结点数据丢失防护功能，需具备 Microsoft 365 E5 或 Microsoft 365 E5 合规性订阅。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge 企业版登录页面](https://aka.ms/EdgeEnterprise)
- [视频：Microsoft Edge 安全性、兼容性和可管理性](microsoft-edge-video-security-compatibility-manageability.md)