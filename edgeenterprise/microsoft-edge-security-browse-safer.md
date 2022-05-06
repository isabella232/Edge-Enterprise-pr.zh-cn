---
title: 使用 Microsoft Edge 更安全地进行浏览
ms.author: pchiquini
author: dan-wesley
manager: robfranco
ms.date: 04/27/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解增强的安全性如何支持使用 Microsoft Edge 更安全地浏览。
ms.openlocfilehash: 48a40a40a1741da1cc89a180535f4bb568060ba8
ms.sourcegitcommit: 592f6e40b13e28af588473b2a75c3ae697e5db2d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2022
ms.locfileid: "12505405"
---
# <a name="browse-more-safely-with-microsoft-edge"></a>使用 Microsoft Edge 更安全地进行浏览

本文介绍 Microsoft Edge 如何在 Web 上提供增强的安全性。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 98 或更高版本。

## <a name="overview"></a>概述

Microsoft Edge 正在添加增强的安全保护，以便在用户浏览网页和访问不熟悉的网站时提供额外的保护层。 该 Web 平台旨在使用 JavaScript 等强大技术提供丰富的浏览体验。 另一方面，当你访问恶意网站时，这种能力可以转化为更多曝光率。 借助增强的安全性，Microsoft Edge 通过在不熟悉的网站上自动应用更保守的安全设置来帮助降低攻击风险，并随着你继续浏览而随着时间的推移进行调整。

## <a name="defense-in-depth"></a>深度防御

Microsoft Edge 中增强的安全性通过禁用实时 (JIT) JavaScript 编译并为浏览器启用额外的操作系统保护，来缓解与内存相关的漏洞。 这些保护包括[硬件强制实施的堆栈保护](https://techcommunity.microsoft.com/t5/windows-kernel-internals-blog/developer-guidance-for-hardware-enforced-stack-protection/ba-p/2163340)和[任意代码防护 (ACG)](/microsoft-365/security/defender-endpoint/exploit-protection-reference?view=o365-worldwide#arbitrary-code-guard)。

结合起来，这些更改有助于提供“深度防御”，因为它们使恶意网站比以往更加难以利用未修补的漏洞写入可执行内存并攻击最终用户。 可以从 Microsoft Edge 安全团队的[博客文章](https://microsoftedge.github.io/edgevr/posts/Super-Duper-Secure-Mode)和 [Microsoft Edge 增强的安全性简介](https://microsoftedge.github.io/edgevr/posts/Introducing-Enhanced-Security-for-Microsoft-Edge/)中了解有关试验结果的详细信息。

你可能还有兴趣详细了解 [Microsoft Edge 中的一线安全保护](/deployedge/ms-edge-security-for-business)。 值得注意的是，你可能想要详细了解 [Microsoft Edge SmartScreen](/deployedge/microsoft-edge-security-smartscreen) 如何保护用户免受网络钓鱼欺诈和恶意软件下载的侵害。

> [!NOTE]
> 此模式目前不支持使用 WebAssembly (WASM) 的网站。 如果需要访问需要 WASM 的网站，请考虑将其添加到例外网站列表，如[例外网站列表](#exception-site-list)中所述。

## <a name="whats-new-in-microsoft-edge-security-settings"></a>Microsoft Edge 安全设置中的新增功能

利用“**增强 Web 安全性**”，Microsoft Edge 可在浏览网页时提供额外一层保护。

使用以下步骤配置增加的安全性。

1. 在 Microsoft Edge 中，转到“**设置及更多**” > “**设置**” > “**隐私、搜索和服务**”。
2. 在“**安全性**”下，验证是否已启用“**增强 Web 安全性**”。
3. 选择最适合浏览的选项。

以下切换设置可用：

- 切换开关关闭（默认）：功能已关闭
- 切换开关打开 – 平衡（推荐）：Microsoft Edge 将在用户访问不熟悉的网站时应用附加的安全保护，但绕过对经常访问的网站的那些保护。 这种组合提供了针对攻击者的实用级别的保护，同时保留了用户在 Web 上的常规任务用户体验。
- 切换开关打开 – 严格：Microsoft Edge 将针对用户访问的所有网站应用额外的安全保护。 用户可能会报告完成其常规任务时面临的一些挑战。

以下屏幕截图显示了“增强 Web 安全性”配置页面，其中启用了增强的安全性，并设置为提供“平衡”安全性。

:::image type="content" source="media/microsoft-edge-security-browse-safer/browse-safer-enhance-security-dialog.png" alt-text="用于配置 Web 平衡安全性的对话框。":::

### <a name="how-balanced-mode-works"></a>“平衡”模式的工作原理

“平衡”模式是一种自适应模式，它基于用户在特定设备上的行为以及 Microsoft 对 Web 风险的理解，为用户最有可能使用和信任的网站提供对 Web 平台的完全访问权限，同时限制新网站和不熟悉网站可以执行的操作。

### <a name="how-strict-mode-works"></a>“严格”模式的工作原理

顾名思义，默认情况下，“严格”模式会将这些安全保护应用于所有网站。 但是，你仍然可以手动将网站添加到例外网站列表，并且企业管理员配置（如果存在）仍然适用。 “严格”模式不适用于大多数最终用户，因为它可能需要某种级别的配置，用户才能完成其正常任务。

### <a name="exception-site-list"></a>例外网站列表

在“平衡”和“严格”模式中，还可以为信任的某些熟悉网站创建例外。 请使用以下步骤将网站添加到例外列表。

1. 在 Microsoft Edge 中，选择“**设置及更多**” > “**设置**” > “**隐私、搜索和服务**”。
2. 验证是否已启用“**增强 Web 安全性**”。
3. 在“**增强 Web 安全性**”下，选择“**例外**”。
4. 选择“**添加网站**”，键入完整的 URL，然后选择“**添加**”。

> [!NOTE]
> 可以使用步骤 (1 - 3) 查看“**增强的安全性例外**”中的网站。 可以**编辑**网站、**删除**网站或删除**所有**例外。

下一个屏幕截图显示了安全例外的设置页面。

:::image type="content" source="media/microsoft-edge-security-browse-safer/browse-safer-enhanced-exceptions.png" alt-text="用于配置安全例外的“设置”页面":::

### <a name="enterprise-controls"></a>企业控制

企业管理员可以使用组策略设置来配置此安全功能，包括创建“允许”和“拒绝”列表，以在访问某些网站时显式增强用户的安全性，或为其他人禁用该模式。 有关策略的完整列表，请参阅 [Microsoft Edge 浏览器策略文档](/deployedge/microsoft-edge-policies)。

## <a name="user-experience-with-enhanced-security"></a>增强的安全性的用户体验

在用户启用增强的安全性后，当 Microsoft Edge 为特定网站应用增强的安全性时，他们将在其 URL 导航栏中看到带有“已增强安全性”字样的横幅。

:::image type="content" source="media/microsoft-edge-security-browse-safer/browse-safer-added-security-banner.png" alt-text="显示已启用增强的安全性的横幅。":::

选择该横幅时，将看到以下浮出控件。 可以切换“增强此网站的安全性”，以手动为特定网站启用或禁用增强的安全性。 如果更改“增强此网站的安全性”开关，Microsoft Edge 会将该网站添加到例外网站列表。 下一个屏幕截图显示了为网站关闭的功能。  

:::image type="content" source="media/microsoft-edge-security-browse-safer/browse-safer-enhanced-security-off.png" alt-text="已关闭增强的安全性的对话框。":::

> [!NOTE]
> 只有当在“设置”页面中启用了增强的安全性时，才会显示“增强此网站的安全性”。

## <a name="send-us-feedback"></a>向我们发送反馈

我们希望获得有关下一次迭代的反馈，以便改进“增强 Web 安全性”。 如果某些内容无法按预期方式工作，或者如果你有关于这些更改的反馈需要分享，我们希望收到你的反馈。 你可以联系 Microsoft 支持人员报告问题或反馈。 还可以在我们的[ TechCommunity 论坛](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise)中留下反馈。

## <a name="see-also"></a>另请参阅

- [视频：Microsoft Edge 上的安全浏览](microsoft-edge-video-security-smartscreen.md)
- [Super Duper 安全模式](https://microsoftedge.github.io/edgevr/posts/Super-Duper-Secure-Mode/)
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
