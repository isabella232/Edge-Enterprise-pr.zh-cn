---
title: Microsoft Edge Stable 渠道发行说明
ms.author: leahtu
author: dan-wesley
manager: srugh
ms.date: 05/03/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Stable 渠道发行说明
ms.openlocfilehash: bca403e0ae56a5473a2ea4458206fc6262b29640
ms.sourcegitcommit: 592f6e40b13e28af588473b2a75c3ae697e5db2d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2022
ms.locfileid: "12505325"
---
# <a name="release-notes-for-microsoft-edge-stable-channel"></a>Microsoft Edge Stable 渠道发行说明

这些发行说明提供有关 Microsoft Edge Stable 渠道中包含的新功能和非安全更新的信息。

- 所有安全更新均在 [Microsoft Edge 安全更新的发行说明](./microsoft-edge-relnotes-security.md)中列出。
- Microsoft Edge 稳定渠道的存档发行说明位于 [Microsoft Edge 稳定渠道的存档发行说明](./microsoft-edge-relnote-archive-stable-channel.md)中。

 若要了解 Microsoft Edge 渠道，请参阅 [Microsoft Edge 渠道概述](./microsoft-edge-channels.md)。

> [!NOTE]
> 对于稳定渠道，更新将在一天或多天内逐步推出。 要了解详细信息，请参阅 [Microsoft Edge 更新的渐进式推出](./microsoft-edge-update-progressive-rollout.md)。
>
> Microsoft Edge Web 平台不断发展以改进用户体验、安全性和隐私。 要了解详细信息，请参阅 [Microsoft Edge 中即将推出的影响站点兼容性的更改](/microsoft-edge/web-platform/site-impacting-changes)。

## <a name="version-1000118557-may-2"></a>版本 100.0.1185.57：5 月 2 日

修复了扩展稳定版的各种 bug 和性能问题。

## <a name="version-1010121032-april-28"></a>版本 101.0.1210.32：4 月 28 日

[此处](/deployedge/microsoft-edge-relnotes-security#april-28-2022) 列出了稳定渠道安全性更新。

### <a name="feature-updates"></a>功能更新

- **设置默认配置文件的功能。** 使用 [EdgeDefaultProfileEnabled](/DeployEdge/microsoft-edge-policies#edgedefaultprofileenabled) 策略，可以设置在打开浏览器时使用的默认配置文件，而不是已使用的最后一个配置文件。 如果指定了 `--profile-directory` 参数，则此策略将不适用。

- **从收藏夹栏启动渐进式 Web 应用 (PWA)。** 对 PWA 启动体验的改进将从可添加到工具栏的“应用”图标开始显示。

- **管理“允许来自其他应用商店的扩展”设置。** 现在，你可以使用 [ControlDefaultStateOfAllowExtensionFromOtherStoresSettingEnabled](/DeployEdge/microsoft-edge-policies#controldefaultstateofallowextensionfromotherstoressettingenabled) 策略来设置“允许来自其他应用商店的扩展”设置的默认状态。

- **对企业站点列表管理器的改进。** 现在，可以在企业站点列表上配置 Microsoft Edge 和 Internet Explorer 之间的共享 Cookie。 可以访问位于 *edge://compat/SiteListManager* 的 [企业站点列表管理器](/deployedge/edge-ie-mode-site-list-manager)。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

- [ConfigureKeyboardShortcuts](/DeployEdge/microsoft-edge-policies#configurekeyboardshortcuts) - 配置要为其禁用键盘快捷方式的命令列表
- [ControlDefaultStateOfAllowExtensionFromOtherStoresSettingEnabled](/DeployEdge/microsoft-edge-policies#controldefaultstateofallowextensionfromotherstoressettingenabled) - 配置“允许来自其他应用商店的扩展”设置的默认状态
- [EdgeAssetDeliveryServiceEnabled](/DeployEdge/microsoft-edge-policies#edgeassetdeliveryserviceenabled) - 允许从资产传送服务下载资产的功能
- [EdgeDefaultProfileEnabled](/DeployEdge/microsoft-edge-policies#edgedefaultprofileenabled) - 已启用默认配置文件设置
- [InternetExplorerModeEnableSavePageAs](/DeployEdge/microsoft-edge-policies#internetexplorermodeenablesavepageas) - 在 Internet Explorer 模式下允许页面另存为
- [KioskSwipeGesturesEnabled](/DeployEdge/microsoft-edge-policies#kioskswipegesturesenabled) - 已启用 Microsoft Edge 展台模式下的轻扫手势
- [MicrosoftOfficeMenuEnabled](/DeployEdge/microsoft-edge-policies#microsoftofficemenuenabled) - 允许用户访问 Microsoft Office 菜单
- [SiteSafetyServicesEnabled](/DeployEdge/microsoft-edge-policies#sitesafetyservicesenabled) - 允许用户配置站点安全服务

#### <a name="deprecated-policies"></a>弃用的策略

- [ForceCertificatePromptsOnMultipleMatches](/DeployEdge/microsoft-edge-policies#forcecertificatepromptsonmultiplematches) - 当配置为“AutoSelectCertificateForUrls”的网站具有多个证书匹配项时，配置 Microsoft Edge 是否应自动选择证书

#### <a name="obsoleted-policies"></a>已过时的策略

- [WebSQLInThirdPartyContextEnabled](/DeployEdge/microsoft-edge-policies#websqlinthirdpartycontextenabled) - 强制重新启用第三方上下文中的 WebSQL

## <a name="version-1000118550-april-21"></a>版本 100.0.1185.50：4 月 21 日

修复了稳定版和扩展稳定版的各种 bug 和性能问题。

## <a name="version-1000118544-april-15"></a>版本 100.0.1185.44：4 月 15 日

> [!Important]
> 此更新包含 [CVE-2022-1364](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2022-1364) 的修补程序，Chromium 团队已将其报告为具有在野利用。 有关详细信息，请参阅 [安全更新指南](https://msrc.microsoft.com/update-guide)。

[此处](/deployedge/microsoft-edge-relnotes-security#april-15-2022) 列出了稳定渠道安全性更新。

## <a name="version-1000118539-april-11"></a>版本 100.0.1185.39：4 月 11 日

修复了稳定版和扩展稳定版的各种 bug 和性能问题。

## <a name="version-1000118536-april-7"></a>版本 100.0.1185.36：4 月 7 日

[此处](/deployedge/microsoft-edge-relnotes-security#april-7-2022) 列出了稳定频道的安全更新。

## <a name="version-1000118529-april-1"></a>版本 100.0.1185.29：4 月 1 日

[此处](/deployedge/microsoft-edge-relnotes-security#april-1-2022)列出了稳定频道的安全更新。

### <a name="feature-updates"></a>功能更新

- **用户代理字符串中的三位数版本号。** Microsoft Edge 现在将发送一个三位数的版本号，例如 User-Agent 标头中的 Edg/100。 这可能会混淆使用错误分析器来确定 User-Agent 字符串版本号的脚本或服务器端分析。 可以使用 [ForceMajorVersionToMinorPositionInUserAgent](/deployedge/microsoft-edge-policies#forcemajorversiontominorpositioninuseragent) 策略来控制是否应在 99 版本冻结 User-Agent 字符串主版本。 此外， **#force-major-version-to-minor** 标志可用于 *edge://flags* 中，以将 User-Agent 字符串中的主要版本冻结为 99。

- **简化 Microsoft 365 应用程序协议激活。** 现在 受信任的 Microsoft 云存储服务上的 Microsoft 365 应用程序协议激活将直接启动某些 Microsoft 365 应用程序，包括 SharePoint 子域和 Microsoft OneDrive URL。 可以使用策略 [AutoLaunchProtocolsComponentEnabled](/deployedge/microsoft-edge-policies#autolaunchprotocolscomponentenabled) 和 [AutoLaunchProtocolsFromOrigins](/deployedge/microsoft-edge-policies#autolaunchprotocolsfromorigins) 启用应用程序协议激活提示（如果需要），并定义启用或禁用警告的其他应用程序和服务。

- **硬件强制实施的堆栈保护。** Microsoft Edge 将通过打击内存损坏漏洞和保护间接调用来继续支持更精细的保护。 硬件强制实施的堆栈保护仅受 Windows 8 及更高版本的支持。 有关详细信息，请参阅[硬件强制实施的堆栈保护](https://techcommunity.microsoft.com/t5/windows-kernel-internals-blog/developer-guidance-for-hardware-enforced-stack-protection/ba-p/2163340)。 可以使用 [ShadowStackCrashRollbackBehavior](/deployedge/microsoft-edge-policies#shadowstackcrashrollbackbehavior) 策略来控制此功能行为。

- **在 Microsoft Outlook 和文件资源管理器中预览 PDF 文件。** 用户可以在轻量级且丰富的只读预览版中查看 PDF 文件。 此功能适用于 Outlook 桌面 PDF 附件或使用文件资源管理器的本地 PDF 文件。

- **打开数字签名的 PDF 文件。** 数字签名广泛用于验证文档的真实性和文档中所做的更改。 可以使用 [PDFSecureMode](/deployedge/microsoft-edge-policies#pdfsecuremode) 策略直接从浏览器为 PDF 文件启用数字签名验证，而无需任何加载项。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

- [AdsTransparencyEnabled](/DeployEdge/microsoft-edge-policies#adstransparencyenabled) - 配置是否启用广告透明度功能
- [DefaultWebHidGuardSetting](/DeployEdge/microsoft-edge-policies#defaultwebhidguardsetting) - 控制 WebHID API 的使用
- [HideRestoreDialogEnabled](/DeployEdge/microsoft-edge-policies#hiderestoredialogenabled) - 在浏览器崩溃后隐藏还原页对话框
- [PDFSecureMode](/DeployEdge/microsoft-edge-policies#pdfsecuremode) - 本机 PDF 阅读器中的安全模式和基于证书的数字签名验证
- [PromptOnMultipleMatchingCertificates](/DeployEdge/microsoft-edge-policies#promptonmultiplematchingcertificates) - 当多个证书匹配时提示用户选择证书
- [WebHidAskForUrls](/DeployEdge/microsoft-edge-policies#webhidaskforurls) - 允许在这些网站上使用 WebHID API
- [WebHidBlockedForUrls](/DeployEdge/microsoft-edge-policies#webhidblockedforurls) - 阻止这些网站上的 WebHID API

#### <a name="deprecated-policy"></a>已弃用策略

- [BackgroundTemplateListUpdatesEnabled](/DeployEdge/microsoft-edge-policies#backgroundtemplatelistupdatesenabled) - 对“集锦”和使用模板的其他功能启用可用模板列表后台更新

#### <a name="obsoleted-policy"></a>已过时的策略

- [AllowSyncXHRInPageDismissal](/DeployEdge/microsoft-edge-policies#allowsyncxhrinpagedismissal) - 允许页面在页面关闭期间发送同步 XHR 请求。

## <a name="version-980110892-march-26"></a>版本 98.0.1108.92：3 月 26 日

修复了扩展稳定版的各种 bug 和性能问题。

## <a name="version-990115055-march-26"></a>版本 99.0.1150.55：3 月 26 日

> [!Important]
> 此更新包含 [CVE-2022-1096](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2022-1096) 的修补程序，Chromium 团队已将其报告为具有在野利用。 有关详细信息，请参阅 [安全更新指南](https://msrc.microsoft.com/update-guide)。

[此处](/deployedge/microsoft-edge-relnotes-security#march-26-2022) 列出了稳定渠道安全性更新。

## <a name="version-990115052-march-24"></a>版本 99.0.1150.52：3 月 24 日

修复了各种 bug 和性能问题。

## <a name="version-980110884-march-17"></a>版本 98.0.1108.84：3 月 17 日

修复了扩展稳定版的各种 bug 和性能问题。

## <a name="version-990115046-march-17"></a>版本 99.0.1150.46：3 月 17 日

[此处](/deployedge/microsoft-edge-relnotes-security#march-17-2022) 列出了稳定频道的安全更新。

## <a name="version-990115039-march-10"></a>版本 99.0.1150.39：3 月 10 日

修复了各种 bug 和性能问题。

## <a name="version-980110876-march-9"></a>版本 98.0.1108.76：3 月 9 日

修复了扩展稳定版的各种 bug 和性能问题。

## <a name="version-990115036-march-7"></a>版本 99.0.1150.36：3 月 7 日

修复了各种 bug 和性能问题。

## <a name="version-990115030-march-3"></a>版本 99.0.1150.30：3 月 3 日

[此处](/deployedge/microsoft-edge-relnotes-security#march-3-2022) 列出了稳定频道的安全更新。

### <a name="feature-updates"></a>功能更新

- **用户代理字符串中即将推出三位数版本号。** 从版本 100 开始，Microsoft Edge 将在 User-Agent 标头中发送三位数的版本号，例如“Edg/100”。 从 Microsoft Edge 97 开始，网站所有者可以通过在 *edge://flags* 中启用 **#force-major-version-to-100** 实验标志来测试此即将推出的代理字符串，以确保其 User-Agent 分析逻辑可靠且按预期工作。

- **使用网站的配置文件首选项个性化设置多配置文件体验。** 用户可以个性化设置其多配置文件体验，并能够创建自定义网站列表，以在 Microsoft Edge 中自动切换配置文件。

- **使用页面缩略图导航 PDF 文档。** 现在，你将能够使用表示页面的缩略图浏览 PDF 文档。 这些缩略图将显示在 PDF 阅读器左侧的窗格中。

- **配置将禁用用于保存和填充的密码管理器用户界面 (UI) 的域列表。** 使用 [PasswordManagerBlocklist](/deployedge/microsoft-edge-policies#passwordmanagerblocklist) 策略配置域列表（仅限 HTTP/HTTPS 架构和主机名），其中 Microsoft Edge 应禁用密码管理器。 这意味着将禁用保存和填充工作流，这可确保无法将这些网站的密码保存或自动填充到 Web 表单中。

- **自定义主密码。** 浏览器已具备以下功能：用户可以在保存的密码自动填充 Web 表单之前添加身份验证步骤。 这增加了另一层隐私，有助于防止未经授权的用户使用保存的密码登录网站。 自定义主密码是同一功能的演变，用户现在可以使用自己选择的自定义字符串作为主密码。 启用后，用户将输入此密码进行身份验证，并将其保存的密码自动填充到 Web 表单中。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

- [DoNotSilentlyBlockProtocolsFromOrigins](/DeployEdge/microsoft-edge-policies#donotsilentlyblockprotocolsfromorigins) - 定义防淹没防护无法静默阻止的协议列表
- [ForceMajorVersionToMinorPositionInUserAgent](/DeployEdge/microsoft-edge-policies#forcemajorversiontominorpositioninuseragent) - 在主要版本 99 上启用或禁用冻结 User-Agent 字符串
- [HubsSidebarEnabled](/DeployEdge/microsoft-edge-policies#hubssidebarenabled) - 显示中心边栏
- [InternetExplorerIntegrationCloudNeutralSitesReporting](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationcloudneutralsitesreporting) - 配置向 M365 管理中心网站列表应用报告可能配置错误的中性网站 URL
- [InternetExplorerIntegrationCloudUserSitesReporting](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationcloudusersitesreporting) - 配置向 M365 管理中心网站列表应用报告 IE 模式用户列表条目
- [PasswordManagerBlocklist](/DeployEdge/microsoft-edge-policies#passwordmanagerblocklist) - 配置将禁用密码管理器 UI（保存和填充）的域列表
- [RelatedMatchesCloudServiceEnabled](/DeployEdge/microsoft-edge-policies#relatedmatchescloudserviceenabled) - 在“在页面上查找”中配置相关匹配项
- [SignInCtaOnNtpEnabled](/DeployEdge/microsoft-edge-policies#signinctaonntpenabled) - 启用登录单击操作对话框
- [UserAgentReduction](/DeployEdge/microsoft-edge-policies#useragentreduction) - 启用或禁用 User-Agent 减少

## <a name="version-980110862-february-24"></a>版本 98.0.1108.62：2 月 24 日

修复了稳定版和扩展稳定版的各种 bug 和性能问题。

## <a name="version-980110856-february-17"></a>版本 98.0.1108.56：2 月 17 日

修复了稳定版和扩展稳定版的各种 bug 和性能问题。

## <a name="version-980110855-february-16"></a>版本 98.0.1108.55：2 月 16 日

> [!Important]
> 此更新包含 [CVE-2022-0609](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2022-0609) 的修补程序，Chromium 团队已将其报告为具有自动散布型病毒攻击。 有关详细信息，请参阅[安全更新指南](https://msrc.microsoft.com/update-guide)。

[此处](/deployedge/microsoft-edge-relnotes-security#february-16-2022) 列出了稳定频道的安全更新。

## <a name="version-980110850-february-10"></a>版本 98.0.1108.50：2 月 10 日

[此处](/deployedge/microsoft-edge-relnotes-security#february-10-2022)列出了稳定频道的安全更新。


<!--- from Version 98.0.1108.43: February 3 to Version 96.0.1054.72: January 6  -->
<!---- From Version 97.0.1072.55: January 6 to Version 96.0.1054.34: November 23 ---->
<!---archive from Version 96.0.1054.29: November 19 to Version 94.0.992.57: October 27 --->
<!-- archive from Version 95.0.1020.30: October 21 to Version 94.0.992.37: September 30 -->
<!-- archive from Version 94.0.992.31: September 24 to Version 93.0.961.44: September 9  -->
<!--- Archive from Version 93.0.961.38: September 2 to Version 92.0.902.62: July 29 --->
<!-- Archive from Version 92.0.902.55: July 22 to Version 91.0.864.37: May 27 -->
<!-- Archive from 89.0.774.45: March 4 to 90.0.818.66: May 20 ->
<!-- Archive from 86.0.622.43: October 15 to beta 88.0.705.81: February 25  ->
<!-- Archive from 86.0.622.38-october-9 to beta 86.0.62.215-september-14  ->
<!-- Archived to version 84.0.522.40: July 16 -->

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
