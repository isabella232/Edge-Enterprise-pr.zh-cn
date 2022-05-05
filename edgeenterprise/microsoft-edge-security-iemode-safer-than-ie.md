---
title: 针对易受攻击的旧版应用的新式安全保护
ms.author: v-danwesley
author: dan-wesley
manager: kawong
ms.date: 10/26/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解使用 IE Microsoft Edge如何为易受攻击的旧应用提供现代安全保护。
ms.openlocfilehash: 0222d4e66e411e9140880eff89e5504956bb7173
ms.sourcegitcommit: 592f6e40b13e28af588473b2a75c3ae697e5db2d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2022
ms.locfileid: "12505475"
---
# <a name="modern-security-protection-for-vulnerable-legacy-apps"></a>针对易受攻击的旧版应用的新式安全保护

随着 Internet 过去 20 年的发展，用户对使用的浏览器的需求和期望一直保持不变。 如今，Internet 是许多企业的基础，拥有旨在满足业务需求具有安全性的现代浏览器非常重要。 Microsoft Edge 是一种新式浏览器，可安全访问新式 Web。 本文介绍 Microsoft Edge 上的 Internet Explorer （IE） 模式如何比 Internet Explorer 更安全。

## <a name="introduction"></a>简介

Microsoft 的内部遥测显示浏览器是 #1 桌面应用。 作为日常生产力工具的核心，浏览器表现为一个暴露于来自 Internet 攻击的大型外围应用。 随着 Internet 及其应用程序越来越复杂，安全威胁也变得更加复杂。 多年来，威胁格局不断演变，制造了大批复杂的威胁参与者，包括但不限于国家/地区和有组织的犯罪集团等，他们希望通过网络钓鱼、勒索软件等获利。

尽管 IE 11 的迭代已发展并不断改进，但 IE 仍以 25 年积累的技术为基础。 这是一个旧版浏览器，在体系结构上已过时，无法应对新式 Web 的安全挑战。

为保证组织的网络安全抵御当今复杂的威胁，IT 管理员尝试让用户使用新式浏览器。 这可确保它们受新式安全功能（大多数或所有时间在浏览时）的保护。
如今使用新式浏览器和 IE 浏览器的常见做法是一种方便的解决方法，但效率很低。 对一个活动使用 IE 浏览器的用户最终可以轻松地将 IE 用于所有活动，这会对新式浏览器提供的保护进行否定。

Microsoft Edge 具有独特的定位，可提供最新的安全性，使用户能够充分利用现代安全技术。

## <a name="reduce-threat-surface-area"></a>减少威胁外围应用

我们知道，一次性实现所有旧网站的现代化并不可行。 使用 Microsoft Edge 和 IE 模式，可以在新式化之前使用安全的新式浏览器访问旧网站。 Microsoft Edge IE 模式使用唯一的双引擎系统，允许你使用 IE 引擎或新的新式引擎打开站点。 浏览器引擎由你访问的网站决定。 由于较旧的 IE 引擎安全性较低，因此你希望将旧引擎的使用限制为仅打开你信任的网站。 受信任的站点是你自己拥有、控制或知道没有安全漏洞的网站。 最佳做法是，应该仅使用新式浏览器引擎访问不受信任的网站，因为这样更安全。

IE 模式旨在管理对不受信任的站点的访问。 IE 模式使用"允许列表"，可在其中标识可使用旧版引擎的受信任站点。 任何不在列表中的网站都会使用新式引擎自动打开，以最安全的方式浏览体验。 不受信任的源中不受信任的内容始终由新式引擎处理。 使用 IE 模式，你可以控制使用旧版引擎呈现哪些网站，当你导航到任何其他站点时，Microsoft Edge 将自动切换回新式引擎。 因此，组织不必依赖用户行为和做法进行自我管理，并决定要使用哪个浏览器。 从用户的角度来看，这是一种流畅的体验。 他们无需考虑使用哪种"正确"的浏览器，无论是旧网站还是新式网站，Microsoft Edge 可以相应的打开他们想要访问的网站。

IE 模式比 IE 更安全，因为工具栏不受支持，从而减少了攻击面。 经验证工具栏是恶意软件和网络钓鱼攻击的载体。 此外，IE 桌面应用下架后将被禁用，这将减少用户使用过时浏览器的时间。 用户将能够访问在 Microsoft Edge 上的 IE 模式的允许列表中标识的受信任的旧应用和站点。

用户将处于新式环境中，无需调整其行为，也不会失去对任务关键型旧版应用和站点的访问权限。 Microsoft Edge 是唯一允许用户使用单个浏览器访问旧版和新式网站的浏览器。  

下一节将说明尽可能减少用户使用旧版浏览器引擎所花的时间为什么很重要。

## <a name="minimize-legacy-browser-use"></a>最大程度地减少旧版浏览器使用

以下各节重点介绍尽量减少旧版浏览器引擎使用的原因。

### <a name="architectural-deficiency"></a>体系结构缺陷

IE 中的体系结构缺陷源于其原始体系结构未考虑到新式 Web 的复杂性或现代威胁形势。 IE 从单个进程体系结构演变，导致沙盒不足和相对广泛的攻击面。 新式浏览器 Microsoft Edge 基于当前威胁环境围绕威胁模型进行设计。 这些浏览器在安全方面进行了改进，如网站隔离和基于硬件的安全功能。 例如，Intel 的控制流强制执行技术 (CET) ，可处理许多现代安全威胁。 这些安全缓解措施在 IE 中不可用，因此，即使是简单的攻击，它也很容易成为目标。

### <a name="ease-of-exploitation"></a>易于利用

IE 比 Microsoft Edge 更容易利用，因为它的体系结构和对新式安全功能缺乏支持。 在 IE 中查找可能导致远程代码执行 （RCE） 的单个漏洞比在 Microsoft Edge 中查找类似的漏洞要容易，因为必须将多个漏洞链接在一起才能实现类似的结果。 此外，ActiveX 和浏览器帮助程序对象已成为漏洞，IE 对它们的支持使浏览器更易于利用。  

### <a name="speed-of-security-patching"></a>安全修补速度

浏览器是桌面上最常用的应用程序之一，用于定期下载和处理来自不受信任源的不受信任的内容。 为了在安全威胁中保持领先，新式浏览器可以快速部署安全更新。 由于 IE 与 Windows 操作系统关联，因此安全更新速度有限，导致 IE 在较长时间内仍然易受攻击。 与 IE 相比，Microsoft Edge 具有更新节奏要快得多的内置更新程序，从而将响应时间缩短为数天而不是数周或数月。

### <a name="security-researcher-ecosystem"></a>安全研究工具生态系统

提高实际浏览器安全性很大程度上依赖于广泛的外部安全研究人员生态系统，这些研究人员由布尔计划激活，以发现新的漏洞和漏洞。 Internet Explorer 不支持布尔计划，这将限制其安全改进的范围。 相比之下，Microsoft Edge 具有全面的布尔计划和内部漏洞研究团队，可以提升先进的浏览器安全性。 由于 Microsoft Edge 基于 Chromium 开放源代码，因此它还受益于 Chromium 的浏览器安全生态系统。

### <a name="phishing-protection-using-smartscreen"></a>使用 SmartScreen 进行网络钓鱼保护

根据[ CyberRatings.org ](https://www.cyberratings.org/)的独立研究，相比 Google Chrome 的安全浏览，Microsoft 网络钓鱼保护技术 SmartScreen 可阻止更多的网络钓鱼 <sup>1</sup>和恶意软件<sup>2</sup>企图。

> [!NOTE]
> <sup>1</sup> Web 浏览器与网络钓鱼、比较测试报告（2021 年 7 月）、CyberRatings.org<br>
> <sup>2</sup>Web 浏览器与恶意软件、比较测试报告（2021 年 7 月）、CyberRatings.org

Microsoft Edge为 SmartScreen 提供完全本机支持，但由于其体系结构已过时，IE 仅部分受支持。

除了提供映射到新式安全实践的安全改进之外，Microsoft Edge 比适用于 Windows 1 0上的企业的 Chrome 更安全。 Microsoft Edge 还利用了 Microsoft 365套件和 Windows 10 中提供的安全特性、功能和工具。 此产品生态系统降低了 IT 团队的安全性和隐私复杂性。 例如，可以轻松地将 Microsoft 365 中标识的投资和决策应用于 Microsoft Edge。

Microsoft Edge上的 IE 模式是一种独特的解决方案，可确保用户可以访问任务关键型 IE 旧站点，同时保护其免受新式威胁的侵害。

## <a name="see-also"></a>另请参阅

- [关于 IE 模式](./edge-ie-mode.md)
- [其他企业模式信息](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [业务安全性](./ms-edge-security-for-business.md)
- [Microsoft Edge 企业版登录页面](https://aka.ms/EdgeEnterprise)