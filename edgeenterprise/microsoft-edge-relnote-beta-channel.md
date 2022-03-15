---
title: Microsoft Edge Beta 渠道发行说明
ms.author: leahtu
author: dan-wesley
manager: srugh
ms.date: 03/14/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge Beta 渠道发行说明
ms.openlocfilehash: 8633a5f15fe737a64a0160de714c1c4e53541482
ms.sourcegitcommit: 556aca8dde42dd66364427f095e8e473b86651a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2022
ms.locfileid: "12445706"
---
# <a name="release-notes-for-microsoft-edge-beta-channel"></a>Microsoft Edge Beta 渠道的发行说明

本发行说明提供有关 Microsoft Edge Beta 渠道中包含的新功能和非安全更新的信息。 这些发行说明的存档版本可在 Microsoft Edge Beta 频道的存档[发行说明上获得](./microsoft-edge-relnote-archive-beta-channel.md)。

> [!NOTE]
> Microsoft Edge Web 平台不断发展以改进用户体验、安全性和隐私。 要了解详细信息，请参阅 [Microsoft Edge 中即将推出的影响站点兼容性的更改](/microsoft-edge/web-platform/site-impacting-changes)。

## <a name="version-990115039-march-10"></a>版本 99.0.1150.39：3 月 10 日

### <a name="feature-updates"></a>功能更新

- **改进了 IE 模式的云站点列表管理体验。** 使用 [InternetExplorerIntegrationCloudUserSitesReporting](/deployedge/microsoft-edge-policies#internetexplorerintegrationcloudusersitesreporting) 和 [InternetExplorerIntegrationCloudNeutralSitesReporting](/deployedge/microsoft-edge-policies#internetexplorerintegrationcloudneutralsitesreporting) 策略配置站点反馈报告，确定企业站点列表中的差异。 您可以在网站中心查看来自用户的本地站点列表 URL，以及Microsoft Edge网站列表体验中可能配置错误的中性Microsoft 365 管理 URL。 若要了解更多信息，请参阅[在网站中心Microsoft 365 管理反馈](/deployedge/edge-ie-mode-cloud-site-list-mgmt#view-site-feedback-on-the-microsoft-365-admin-center-1)。  **注意：** 这是受控功能推出。 如果看不到此功能，请在继续推出时重新查看。

## <a name="version-990115030-march-2"></a>版本 99.0.1150.30：3 月 2 日

修复了各种 bug 和性能问题。

## <a name="version-990115025-february-25"></a>版本 99.0.1150.25：2 月 25 日

修复了各种 bug 和性能问题。

## <a name="version-990115021-february-22"></a>版本 99.0.1150.21：2 月 22 日

修复了各种 bug 和性能问题。

## <a name="version-990115016-february-14"></a>版本 99.0.1150.16：2 月 14 日

修复了各种 bug 和性能问题。

## <a name="version-990115011-february-9"></a>版本 99.0.1150.11：2 月 9 日

### <a name="feature-updates"></a>功能更新

- **用户代理字符串中即将推出的三位数版本号。** 从版本 100 开始，Microsoft Edge将在 User-Agent 标头中发送一个三位数的版本号，例如"Edg/100"。 从 Microsoft Edge 97 开始，网站所有者可以通过在 *edge://flags* 中启用 **#force-major-version-to-100** 实验标志来测试即将推出的代理字符串，以确保其 User-Agent 分析逻辑可靠且按预期工作。

- **使用网站的配置文件首选项个性化设置多配置文件体验。** 用户可以个性化设置其多配置文件体验，并能够创建自定义网站列表，以在 Microsoft Edge 中自动切换配置文件。

- **IE 模式的双向 Cookie 共享。** 此功能扩展了已提供的 Cookie 共享功能，并允许用户将特定会话 cookie 从 Internet Explorer/IE 模式同步到Microsoft Edge。 有关详细信息，请参阅 Cookie [在 Microsoft Edge 和 Internet Explorer](/deployedge/edge-ie-mode-add-guidance-cookieshare)。

- **使用页面缩略图导航 PDF 文档。** 现在，您将能够使用表示页面的缩略图在 PDF 文档中导航。 这些缩略图将显示在 PDF 阅读器左侧的窗格中。

- **配置将 (禁用其密码管理器用户界面和 UI) 用于保存) 填充的域列表。** 使用 [PasswordManagerBlocklist](/deployedge/microsoft-edge-policies#passwordmanagerblocklist) 策略配置域列表 (HTTP/HTTPS 架构和主机名) 其中 Microsoft Edge 应禁用密码管理器。 这意味着将禁用"保存"和"填充"工作流，这可以确保这些网站的密码无法保存或自动填充到 Web 表单中。

- **在公共预览Microsoft Edge中，使用 API (更新加载项) 。** 你可以将这些 API 直接集成到生成管道中，并将程序包更新发布到Microsoft Edge加载项网站。 若要了解更多信息，请参阅在专用Microsoft Edge预览版 ([加载项 API) ](/microsoft-edge/extensions-chromium/publish/api/using-addons-api)

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

- [AllowGamesMenu](/DeployEdge/microsoft-edge-policies#allowgamesmenu) - 允许用户访问游戏菜单
- [DoNotSilentlyBlockProtocolsFromOrigins](/DeployEdge/microsoft-edge-policies#donotsilentlyblockprotocolsfromorigins) - 定义无法无提示阻止的反淹没保护的协议列表
- [HubsSidebarEnabled](/DeployEdge/microsoft-edge-policies#hubssidebarenabled) - 显示中心边栏
- [InternetExplorerIntegrationCloudNeutralSitesReporting](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationcloudneutralsitesreporting) - 配置对 M365 管理中心网站列表应用可能配置不当的中性网站 URL 的报告
- [InternetExplorerIntegrationCloudUserSitesReporting](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationcloudusersitesreporting) - 配置 M365 管理中心站点列表应用 IE 模式用户列表条目的报告
- [PasswordManagerBlocklist](/DeployEdge/microsoft-edge-policies#passwordmanagerblocklist) - 配置将禁用其密码管理器 UI (保存和) 的域列表
- [RelatedMatchesCloudServiceEnabled](/DeployEdge/microsoft-edge-policies#relatedmatchescloudserviceenabled) - 在页面上查找中配置相关匹配
- [SignInCtaOnNtpEnabled](/DeployEdge/microsoft-edge-policies#signinctaonntpenabled) - 启用登录单击操作对话框
- [UserAgentReduction](/DeployEdge/microsoft-edge-policies#useragentreduction) - 启用或禁用User-Agent减少

## <a name="version-980110848-february-8"></a>版本 98.0.1108.48：2 月 8 日

修复了各种 bug 和性能问题。

## <a name="version-980110843-february-3"></a>版本 98.0.1108.43：2 月 3 日

修复了各种 bug 和性能问题。

## <a name="version-980110842-february-2"></a>版本 98.0.1108.42：2 月 2 日

修复了各种 bug 和性能问题。

## <a name="version-980110839-january-31"></a>版本 98.0.1108.39：1 月 31 日

修复了各种 bug 和性能问题。

## <a name="version-980110833-january-24"></a>版本 98.0.1108.33：1 月 24 日

修复了各种 bug 和性能问题。

## <a name="version-980110827-january-19"></a>版本 98.0.1108.27：1 月 19 日

修复了各种 bug 和性能问题。

## <a name="version-980110823-january-14"></a>版本 98.0.1108.23：1 月 14 日

### <a name="feature-updates"></a>功能更新

- **增强 Web 安全性。** 浏览器安全性Microsoft Edge的浏览模式，在浏览 Web 时为您提供了额外的保护层。 管理员可以将以下组策略应用于最终用户桌面设备 (Windows macOS 和 Linux) 帮助防止零日。 这些策略还使重要网站和业务线应用程序继续按照预期方式工作。 此功能是一项巨大的前进步骤，因为它允许我们根据历史趋势 (意外的活动零) 。 启用后，此功能将硬件强制执行的堆栈保护、任意代码防护 (ACG) 和内容 Flow Guard (CFG) 作为支持安全缓解措施，以提高用户 Web 上的安全性。
组策略：
  - [EnhanceSecurityMode](/DeployEdge/microsoft-edge-policies#enhancesecuritymode)
  - [EnhanceSecurityModeBypassListDomains](/DeployEdge/microsoft-edge-policies#enhancesecuritymodebypasslistdomains)
  - [EnhanceSecurityModeEnforceListDomains](/DeployEdge/microsoft-edge-policies#enhancesecuritymodeenforcelistdomains)

- **自定义主密码。** 浏览器已具有以下功能：用户可以在保存的密码自动填充 Web 表单之前添加身份验证步骤。 这添加了另一层隐私，有助于防止未经授权的用户使用保存的密码登录网站。 自定义主密码是同一功能的发展，用户现在可以使用他们选择的自定义字符串作为其主要密码。 启用后，用户将输入此密码自行进行身份验证，并自动将保存的密码填写到 Web 表单中。

- **覆盖添加到 web 页面的滚动Microsoft Edge。** 我们已使用基于覆盖的设计更新了滚动条。 用户可以在 edge://flags 中 *edge://flags*。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

- [AddressBarEditingEnabled](/DeployEdge/microsoft-edge-policies#addressbareditingenabled) - 配置地址栏编辑。
- [EdgeFollowEnabled](/DeployEdge/microsoft-edge-policies#edgefollowenabled) - 在服务中启用Microsoft Edge。
- [EnhanceSecurityMode](/DeployEdge/microsoft-edge-policies#enhancesecuritymode) - 增强安全Microsoft Edge。
- [EnhanceSecurityModeBypassListDomains](/DeployEdge/microsoft-edge-policies#enhancesecuritymodebypasslistdomains) - 配置不会强制实施增强安全模式的域列表。
- [EnhanceSecurityModeEnforceListDomains](/DeployEdge/microsoft-edge-policies#enhancesecuritymodeenforcelistdomains) - 配置将始终强制实施增强安全模式的域列表。
- [InAppSupportEnabled](/DeployEdge/microsoft-edge-policies#inappsupportenabled) - 启用应用内支持。
- [MicrosoftEdgeInsiderPromotionEnabled](/DeployEdge/microsoft-edge-policies#microsoftedgeinsiderpromotionenabled) - Microsoft Edge预览体验成员促销已启用。
- [PrintStickySettings](/DeployEdge/microsoft-edge-policies#printstickysettings) - 打印预览粘滞设置。
- [SandboxExternalProtocolBlocked](/DeployEdge/microsoft-edge-policies#sandboxexternalprotocolblocked) - Microsoft Edge阻止导航到沙盒 iframe 中的外部协议。
- [U2fSecurityKeyApiEnabled](/DeployEdge/microsoft-edge-policies#u2fsecuritykeyapienabled) - 允许使用已弃用的 U2F 安全密钥 API。

## <a name="version-970107254-january-5"></a>版本 97.0.1072.54：1 月 5 日

修复了各种 bug 和性能问题。

## <a name="version-970107252-january-3"></a>版本 97.0.1072.52：1 月 3 日

修复了各种 bug 和性能问题。

## <a name="version-970107241-december-20"></a>版本 97.0.1072.41：12 月 20 日

修复了各种 bug 和性能问题。

## <a name="version-970107234-december-13"></a>版本 97.0.1072.34：12 月 13 日

修复了各种 bug 和性能问题。

## <a name="version-970107228-december-8"></a>版本 97.0.1072.28：12 月 8 日

修复了各种 bug 和性能问题。

<!--- Version 97.0.1072.21: December 1 to Version 96.0.1054.13: November 5  --->
<!--- archive from Version 96.0.1054.8: November 1 to Version 95.0.1020.14: October 5  --->
<!-- archive from version 95.0.1020.9: September 28 to version 94.0.992.14: September 7 ---->
<!-- archive from Version 94.0.992.9: September 2 to Version 92.0.902.40: July 6 -->
<!--Archive on Oct 27 From Version 92.0.902.22: June 21 to Version 89.0.774.23: February 8  -->
<!--- Archived from Version 87.0.664.18: October 26 to to version 89.0.774.18: February 3 ---->
<!--- Archived from Version 87.0.664.12: October 20 to to version 86.0.622.15: September 14 ---->
<!--- Archived to version 86.0.622.11: September 9 ---->
<!--- Archived to version 85.0.564.18: July 28 ---->

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)

