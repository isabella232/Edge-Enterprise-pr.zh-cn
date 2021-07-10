---
title: 计划 Microsoft Edge 部署
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 计划 Microsoft Edge 部署
ms.openlocfilehash: be85aa5182bbee51f90fe42e80cdee0b9c793b4e
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641938"
---
# <a name="plan-your-deployment-of-microsoft-edge"></a>计划 Microsoft Edge 部署

本文介绍在企业环境中部署 Microsoft Edge 的建议做法。

>[!NOTE]
>本文适用于 Microsoft Edge 版本 77 或更高版本。

以下部分针对 Microsoft Edge 部署规划提供了具体指导。

- [评估浏览器环境和要求](#evaluate-your-existing-browser-environment-and-browser-needs)
- [确保 Windows 10 设备准备就绪](#make-sure-your-windows-10-devices-are-ready)
- [选择部署方法](#determine-your-deployment-methodology)
- [进行站点发现](#do-site-discovery)
- [选择渠道策略](#determine-your-channel-strategy)
- [确定和配置策略](#define-and-configure-policies)
- [测试应用兼容性](#do-app-compatibility-testing)
- [Microsoft Edge 试点](#deploy-microsoft-edge-to-a-pilot-group)
- [评估试点](#validate-your-deployment)
- [在企业中部署 Microsoft Edge](#broad-deployment-of-microsoft-edge)

## <a name="evaluate-your-existing-browser-environment-and-browser-needs"></a>评估现有浏览器环境和浏览器需求

请花些时间来了解当前的浏览器状态和项目远景，以确保所有项目利益相关方都保持一致并努力达到相同的结果。

首先定义当前状态：

- 当前在环境中部署了哪些浏览器？
- 哪个浏览器被设置为默认浏览器？
- 是否需要将 Internet Explorer 用于某些应用？
- 现在你是否使用企业模式站点列表配置 Internet Explorer？
- 你的环境中支持哪些操作系统平台？ （Windows 10、macOS、Windows 7、Windows Server 等）
- 你使用哪些管理工具进行浏览器管理？
- 谁负责浏览器配置和管理？
- 验证浏览器兼容性的过程是什么？

了解当前状态后，你可以确定所需的浏览器部署目标，并考虑以下各项：

- 是否要[将 Microsoft Edge 设置为默认浏览器](./edge-default-browser.md)？
- 如何[配置 Microsoft Edge](./configure-microsoft-edge.md)？
- 初始部署过程中配置哪些功能至关重要？
- 解决任何已确定的兼容性或配置问题的过程是什么？

你还应了解感兴趣的功能的**先决条件**，例如：

- [Windows Defender 应用程序防护](/windows/security/threat-protection/windows-defender-application-guard/reqs-wd-app-guard)
- [Internet Explorer 模式](./edge-ie-mode.md)
- [身份验证和同步](./microsoft-edge-security-identity.md)

考虑这些答案后，就可以计划 Microsoft Edge 部署了。
<!--bookmark -->

## <a name="make-sure-your-windows-10-devices-are-ready"></a>确保 Windows 10 设备就绪

Microsoft Edge 稳定频道需要 2019 年 10 月（或更晚）的最新累积更新 (LCU)。 如果尝试部署到拥有较早 LCU 的 Windows 10 设备，则安装将失败。 有关部署 Microsoft Edge 前必须应用的最小 LCU 的详细信息，请参阅[用于支持下一版本 Microsoft Edge 的 Windows 更新](./microsoft-edge-sysupdate-windows-updates.md)。

## <a name="determine-your-deployment-methodology"></a>确定部署方法

在知道所需的结束状态后，便可以开始计划如何达到目的。 部署 Microsoft Edge 的两种主要方法是按角色部署和按站点部署。

### <a name="deploy-to-end-users-by-role"></a>按角色部署到最终用户

如果应用兼容性是你主要关注的问题，并且对要测试哪些应用没有牢固的把握，那么可能需要考虑按角色部署到最终用户。 这样，每波分阶段部署都能提供关于可能需要修改配置来解决兼容性问题的应用的反馈和见解。

### <a name="deploy-to-end-users-by-site"></a>按站点部署到最终用户

如果带宽是你主要关注的问题，你可能需要事先考虑进行应用程序兼容性测试。 完成测试后，按站点部署到最终用户，以便你可以利用“缓存其他软件传递优化”这一过程。

## <a name="do-site-discovery"></a>进行站点发现

如果依赖旧版 Web 应用程序，并且计划使用 Internet Explorer 模式（大多数客户都使用），则可能需要进行一些额外的站点发现。

### <a name="if-youve-already-deployed-and-configured-the-legacy-version-of-microsoft-edge"></a>如果已经部署并配置了旧版 Microsoft Edge

如果已将企业站点列表配置为适用于旧版 Microsoft Edge，则工作就已经接近完成了！ 你可能需要添加的一项内容就是中性站点。

中性站点通常是提供单一登录 (SSO) 的站点。 如果从 Microsoft Edge 中导航到中性站点，则需要保持在 Microsoft Edge 中以进行身份验证。 如果在 Internet Explorer 模式下导航到中性站点，则需要保持在 Internet Explorer 模式中以进行身份验证。

标识使用的任何 SSO（或其他中性）站点，并将它们添加到企业站点列表中。

### <a name="if-youve-configured-internet-explorer-as-your-default-browser"></a>如果已将 Internet Explorer 配置为默认浏览器

如果当前仅使用 Internet Explorer，则可能不知道哪些站点已升级到新式 Web 标准，以及哪些仍需要 Internet Explorer。 你需要查找这些站点并将它们添加到企业站点列表中。 这样，可以仅在需要的站点上使用 Internet Explorer 模式。

> [!TIP]
> 使用[企业站点发现](/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery)工具发现可能需要使用 Internet Explorer 模式的站点。 通过 Windows 10、Windows 8.1 或 Windows 7 上的 Internet Explorer 11，你可以在运行 Windows Internet Explorer 8 的计算机上收集数据。

### <a name="analyze-site-discovery-data"></a>分析站点发现数据

收集站点数据后，我们建议采用以下 4 步过程来分析数据：

1. 依次按域和 URL 对数据进行排序。
2. 定义要为 Internet Explorer 模式配置的“应用”的边界。 你需要包含定义该应用的所有站点和 Web 控件。 但是，不需要过于广泛地定义应用来包含各种额外的站点和控件。 某些站点可能像“http://contoso.com/app1”一样简单，而其他站点可能要求定义多个站点和页面。
3. 测试应用以验证它是否未在本机工作。 许多站点在检测到新式浏览器时将提供新式内容，并且仅在检测到 Internet Explorer 时才提供旧版内容。
4. 如果应用未通过测试，请将该应用添加到企业站点列表中。

   > [!NOTE]
   > 作为最佳做法，请将构成应用的所有站点归为一组。 如果所有站点都需要用于完成同一项任务，并且如果这些站点通常一起更新，则充分表明应将它们归组。 这样，当升级应用时，可以更轻松地从 Internet Explorer 模式中删除整个站点并开始将新式浏览器用于该应用。

## <a name="determine-your-channel-strategy"></a>确定渠道策略

Microsoft Edge 通过[多个渠道](./microsoft-edge-channels.md)进行发布。

> [!NOTE]
> 你可以在设备上安装多个渠道

稳定渠道是你将要部署到大多数设备上的渠道。 但是，应该考虑包含多个设备和多个渠道的部署策略。

### <a name="multiple-devices-and-channels"></a>多个设备和渠道

我们建议将具有代表性的设备子集配置为使用 Beta 渠道。 这使你可以预览即将推出的浏览器更改。 你可以查看这些更改是否会影响最终用户或应用。

你可能还需要为某些角色（如 Web 开发人员）提供 Dev 渠道（或者甚至是 Canary 渠道）。 考虑是想要针对渠道更加流畅且快速变化的某些设备，还是只是让这些渠道可供用户选择安装。

因为可以在设备上安装多个渠道，所以可以针对已选择安装预发布版渠道的用户缓解测试风险。 例如，如果你有一位使用 Beta 渠道的用户，并且出现了问题，那么他们可以切换到稳定渠道，然后继续工作。 这会取消阻止他们，直到问题得以解决。

> [!NOTE]
> 如果用户启用了同步，则其配置将跨渠道同步，从而使渠道之间的过渡变得更容易。

## <a name="define-and-configure-policies"></a>定义和配置策略

创建企业站点列表后，我们建议确定和配置打算使用 Microsoft Edge 部署的策略。 这可确保在执行测试时应用这些策略。

首先，考虑希望用户拥有的首次运行体验。 如果想要自动导入当前浏览器中的设置，请配置 [AutoImportAtFirstRun](./microsoft-edge-policies.md#autoimportatfirstrun) 策略。

对于安全策略，我们建议从 Microsoft Edge 安全基准开始。 可以使用[推荐的安全配置基准设置](https://techcommunity.microsoft.com/t5/Microsoft-Security-Baselines/Security-baseline-DRAFT-for-Chromium-based-Microsoft-Edge/ba-p/949991)或使用 [Microsoft Intune](/intune/protect/security-baseline-settings-edge) 来应用安全基准。

对于其他策略，我们建议查看 [Microsoft Edge](./microsoft-edge-policies.md) 和 [Microsoft Edge 更新](./microsoft-edge-update-policies.md)的策略配置。

### <a name="define-your-update-strategy-and-policies"></a>定义更新策略和策略

你还需要确定在部署 Microsoft Edge 后想要如何进行更新：

- **允许 Microsoft Edge 自行更新**（默认）。 如果选择允许 Microsoft Edge 自动更新，则 Microsoft Edge 将按照你部署的渠道所确定的节奏自动更新自身。
- **按照自己的节奏更新 Microsoft Edge**。 如果你希望显式控制部署更新的时间，则可以禁用自动更新并自行部署更新（请参阅[更新策略参考](./microsoft-edge-update-policies.md)）。在禁用自动更新后，你可以使用以下工具之一为每个渠道部署更新：

- [Intune](/intune/apps/apps-windows-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)
- [Configuration Manager](./deploy-edge-with-configuration-manager.md)
- 你选择的部署工具。

无论采用何种更新策略，我们都建议充分利用环形部署策略。 对于自动更新，这意味着要有运行 Beta 渠道的代表性用户样本，以确定关于什么将成为稳定渠道的问题。 对于手动更新，这可能还包括在发布新的稳定渠道版本后对试点组进行的其他验证。 接下来就是广泛部署。

>[!NOTE]
>Microsoft Edge 支持将仅适用于每个渠道中的最新版本的 Microsoft Edge

## <a name="do-app-compatibility-testing"></a>执行应用兼容性测试

Microsoft Edge 的应用程序兼容性相当高 - 因此，Microsoft 提供以下兼容性承诺：

1. 如果适用于 *Microsoft Edge* 版本 45 和更早版本，则适用于 Microsoft Edge *版本 77 和更高版本*。
2. 如果适用于 Internet Explorer，那么将在 Internet Explorer 模式下适用于 Microsoft Edge。
3. 如果适用于 Google Chrome，则将适用于 Microsoft Edge。

如果你有一款应用程序，而我们未在该应用中兑现我们的兼容性承诺，那么我们将坚守承诺，使用 [Microsoft 应用保证](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure)来解决此问题。

### <a name="internal-line-of-business-app-testing"></a>内部业务线应用测试

尽管我们有兼容性承诺，但我们知道许多组织必须验证某些应用程序的合规性或风险管理原因。 尽管我们希望简单直接地测试应用，但此过程务必要做到严格有序。

有两种方法可以执行应用兼容性测试：

1. 实验室测试。 使用特定配置在严格控制的环境中验证应用程序。
2. 试验测试。 少量用户使用他们自己的设备在其日常工作环境中验证应用程序。

选择最适合每个应用的方法来管理风险，无需在兼容性测试方面过度投资。

### <a name="third-party-app-support"></a>第三方应用支持

除了自己的业务线应用之外，很多组织还使用由外部来源提供的应用。 [准备好使用 Microsoft Edge](deploy-edge-ready-for-edge.md) 文章有一个列表，其中列出了可能已在你的组织中使用的 Web 应用程序。 此列表提供提供商支持声明链接，在将其产品与 Microsoft Edge 结合使用时可进行查看。

## <a name="deploy-microsoft-edge-to-a-pilot-group"></a>将 Microsoft Edge 部署到试点组

在定义策略并完成初始应用兼容性测试后，即可开始部署到试点组。 使用以下工具之一部署到试点组：

- [适用于 Windows 的 Microsoft Intune](/intune/apps/apps-windows-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json) 或[适用于 macOS 的 Microsoft Intune](/intune/apps/apps-edge-macos?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)
- [Configuration Manager](./deploy-edge-with-configuration-manager.md)。
- 另一个管理工具，下载并部署 [Microsoft Edge 的 MSI 文件](https://www.microsoftedgeinsider.com/enterprise)。

## <a name="validate-your-deployment"></a>验证你的部署

部署试验版后，需要捕获从用户那里获取的所有反馈。

- 捕获有关兼容性的反馈。 确定属于企业站点列表并且在站点发现期间未标识的站点。
- 捕获有关策略配置的反馈。 确保用户可以在遵循安全指南时使用关键功能并执行其工作。
- 捕获有关易用性和新功能的反馈。 确定任何应根据用户问题开发和提供培训的领域。

## <a name="broad-deployment-of-microsoft-edge"></a>Microsoft Edge 的广泛部署

在完成试验并根据从试验中吸取的经验教训更新部署计划后，就可以向所有用户全面部署 Microsoft Edge。  恭喜你！

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [视频 - 部署 Microsoft Edge](microsoft-edge-video-deploy.md)