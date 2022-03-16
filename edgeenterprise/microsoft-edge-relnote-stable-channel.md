---
title: Microsoft Edge Stable 渠道发行说明
ms.author: leahtu
author: dan-wesley
manager: srugh
ms.date: 03/10/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Stable 渠道发行说明
ms.openlocfilehash: a7e11586c77b600253f25c2819a26e72e18f4b28
ms.sourcegitcommit: 556aca8dde42dd66364427f095e8e473b86651a0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2022
ms.locfileid: "12445636"
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

## <a name="version-980110843-february-3"></a>版本 98.0.1108.43：2 月 3 日

[此处](/deployedge/microsoft-edge-relnotes-security#february-3-2022)列出了稳定频道的安全更新。

### <a name="feature-updates"></a>功能更新

- **增强 Web 安全性。** 这是 Microsoft Edge 中的一种优先考虑浏览器安全的浏览模式，可在用户浏览网页时为其提供额外一层保护。 管理员可以将组策略应用到最终用户桌面（Windows、macOS 和 Linux），以帮助防范自动散布型病毒攻击（也称为 0 天）。 以下组策略支持此浏览模式：

  - [EnhanceSecurityMode](/deployedge/microsoft-edge-policies#enhancesecuritymode)
  - [EnhanceSecurityModeBypassListDomains](/deployedge/microsoft-edge-policies#enhancesecuritymodebypasslistdomains)
  - [EnhanceSecurityModeEnforceListDomains](/deployedge/microsoft-edge-policies#enhancesecuritymodeenforcelistdomains)

- **用户代理字符串中即将推出三位数版本号。** 从版本 100 开始，Microsoft Edge 将在 User-Agent 标头中发送三位数的版本号，例如“Edg/**100**”。 从 Microsoft Edge 97 开始，网站所有者可以通过在 *edge://flags* 中启用 **#force-major-version-to-100** 实验标志来测试此即将推出的用户代理字符串，以确保其 User-Agent 分析逻辑可靠且按预期工作。

- **弃用 WebRTC 的 Plan B SDP 语义。** 此更改将弃用名为 Plan B 的旧版会话描述协议 (SDP) 方言。此 SDP 格式将被 Unified Plan 取代，其是一种符合规范且跨浏览器兼容的 SDP 格式。 有关详细信息，请参阅 Chrome 平台状态条目 [PSA：Plan B 应在 M96 Beta 和稳定版中引发异常](https://chromestatus.com/feature/5823036655665152)和 [PSA：Plan B 在稳定版中引发异常，已延长弃用试用版结束日期](https://groups.google.com/g/discuss-webrtc/c/gEHrZyYKsfU)。 请求 [RTCPeerConnection Plan B SDP 语义的试用版](https://developer.chrome.com/origintrials/#/view_trial/3892235977954951169)允许网站继续使用弃用的 API，直到版本 101。

- **添加到 Microsoft Edge 的叠加滚动条。** 我们已使用基于叠加的设计更新了滚动条。 用户可以在 *edge://flags* 中启用此功能。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

- [AddressBarEditingEnabled](/DeployEdge/microsoft-edge-policies#addressbareditingenabled) - 配置地址栏编辑
- [AllowGamesMenu](/DeployEdge/microsoft-edge-policies#allowgamesmenu) - 允许用户访问游戏菜单
- [EdgeFollowEnabled](/DeployEdge/microsoft-edge-policies#edgefollowenabled) - 在 Microsoft Edge 中启用关注服务
- [EnhanceSecurityMode](/DeployEdge/microsoft-edge-policies#enhancesecuritymode) - 增强 Microsoft Edge 中的安全状态
- [EnhanceSecurityModeBypassListDomains](/DeployEdge/microsoft-edge-policies#enhancesecuritymodebypasslistdomains) - 配置将不会强制执行增强安全模式的域列表
- [EnhanceSecurityModeEnforceListDomains](/DeployEdge/microsoft-edge-policies#enhancesecuritymodeenforcelistdomains) - 配置将始终强制执行增强安全模式的域列表
- [InAppSupportEnabled](/DeployEdge/microsoft-edge-policies#inappsupportenabled) - 启用应用内支持
- [MicrosoftEdgeInsiderPromotionEnabled](/DeployEdge/microsoft-edge-policies#microsoftedgeinsiderpromotionenabled) - 启用 Microsoft Edge 预览体验成员促销
- [PrintStickySettings](/DeployEdge/microsoft-edge-policies#printstickysettings) - 打印预览粘滞设置
- [SandboxExternalProtocolBlocked](/DeployEdge/microsoft-edge-policies#sandboxexternalprotocolblocked) - 允许 Microsoft Edge 在沙盒 iframe 中阻止对外部协议的导航
- [U2fSecurityKeyApiEnabled](/DeployEdge/microsoft-edge-policies#u2fsecuritykeyapienabled) - 允许使用已弃用的 U2F 安全密钥 API

## <a name="version-970107276-january-27"></a>版本 97.0.1072.76：1 月 27 日

修复了各种 bug 和性能问题。

### <a name="feature-updates"></a>功能更新

- **用户代理字符串中即将推出三位数版本号。** 从版本 100 开始，Microsoft Edge 将在 User-Agent 标头中发送三位数的版本号，例如“Edg/**100**”。 从 Microsoft Edge 97 开始，网站所有者可以通过在 *edge://flags* 中启用 **#force-major-version-to-100** 实验标志来测试此即将推出的用户代理字符串，以确保其 User-Agent 分析逻辑可靠且按预期工作。

## <a name="version-960105475-january-21"></a>版本 96.0.1054.75：1 月 21 日

修复了扩展稳定版的各种 bug 和性能问题。

## <a name="version-970107269-january-20"></a>版本 97.0.1072.69：1 月 20 日

[此处](/deployedge/microsoft-edge-relnotes-security#january-20-2022) 列出了稳定渠道安全性更新。

## <a name="version-970107262-january-13"></a>版本 97.0.1072.62：1 月 13 日

修复了各种 bug 和性能问题。

## <a name="version-960105472-january-6"></a>版本 96.0.1054.72：1 月 6 日

修复了扩展稳定版的各种 bug 和性能问题。

## <a name="version-970107255-january-6"></a>版本 97.0.1072.55：1 月 6 日

[此处](/deployedge/microsoft-edge-relnotes-security#january-6-2022)列出了稳定频道的安全更新。

### <a name="feature-updates"></a>功能更新

- **在设备上登录多个工作或学校帐户时，使用当前配置文件登录网站。** 当在设备上登录多个工作或学校帐户时，将要求用户从帐户选取器中选择一个帐户来继续访问网站。 在此版本中，系统将提示用户让 Microsoft Edge 使用已登录当前配置文件的工作或学校帐户自动登录网站。 用户可以在“**设置**” > “**配置文件首选项**”中打开和关闭此功能。

- **在 macOS 上添加对 Microsoft 终结点数据丢失防护 (DLP) 的支持。** Microsoft 终结点 DLP 策略实施将在 macOS 上本地提供。

- **自动 HTTPS。** 用户可以在可能支持此更安全协议的域上将导航从 HTTP 升级到 HTTPS。 此支持还可以配置为在所有域上尝试 HTTPS 传输。 请注意: 这是限制性功能推出的功能。 如果没有看到此功能，请在我们继续推出时回来查看。

- **在第三方上下文中阻止 WebSQL。** 将阻止第三方框架使用旧版 WebSQL 功能。 在 Microsoft Edge 版本 101 之前，[WebSQLInThirdPartyContextEnabled](/deployedge/microsoft-edge-policies#websqlinthirdpartycontextenabled) 策略可作为选择退出选项使用。 此更改发生在 Microsoft Edge 所基于的 Chromium 项目中。 有关详细信息，请导航到 [Chrome Platform Status](https://chromestatus.com/feature/5684870116278272) 条目。

- **Microsoft Edge 中的引文。** 研究的引用来源是学生的普遍要求。 他们必须管理许多研究参考资料和来源，这不是一项简单的任务。 他们还必须将这些引文转换为正确的引文格式，如 APA、MLA 和 Chicago。 这项新的“引文”功能现已在 Microsoft Edge 中预览，它为学生提供了一种在线研究时管理和生成引文的更好方法。 在“集锦”中或从“**设置及更多 (Alt-F)**”打开“引文”后，Microsoft Edge 会自动生成学生以后可以使用的引文，以便他们可以专注于其研究。 完成后，他们可以轻松地将这些引文编译为最终可交付结果。 有关详细信息，请参阅[在 Microsoft Edge 中预览引文](https://blogs.windows.com/msedgedev/2021/11/04/preview-citations-feature-edge/)。

- **控制流保护 (CFG)。** Microsoft Edge 将通过打击内存损坏漏洞和保护间接调用来开始支持更精细的保护。 仅 Windows 8 及更高版本支持 CFG。 有关详细信息，请参阅[控制流防护](/windows/win32/secbp/control-flow-guard)。
  
  > [!NOTE]
  > 这是一项不断发展的技术，请分享你反馈，以帮助我们加强对它的支持。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

- [AccessibilityImageLabelsEnabled](/DeployEdge/microsoft-edge-policies#accessibilityimagelabelsenabled) - 启用从 Microsoft 获取图像说明
- [CORSNonWildcardRequestHeadersSupport](/DeployEdge/microsoft-edge-policies#corsnonwildcardrequestheaderssupport) -启用 CORS 非通配符请求标头支持
- [EdgeDiscoverEnabled](/DeployEdge/microsoft-edge-policies#edgediscoverenabled) - 发现 Microsoft Edge 中的功能
- [EdgeEnhanceImagesEnabled](/DeployEdge/microsoft-edge-policies#edgeenhanceimagesenabled) - 启用增强图像
- [InternetExplorerModeTabInEdgeModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorermodetabinedgemodeallowed) - 允许为 Internet Explorer 模式配置的网站在 Microsoft Edge 中打开
- [SameOriginTabCaptureAllowedByOrigins](/DeployEdge/microsoft-edge-policies#sameorigintabcaptureallowedbyorigins) - 允许这些源捕获同一源选项卡
- [ScreenCaptureAllowedByOrigins](/DeployEdge/microsoft-edge-policies#screencaptureallowedbyorigins) - 允许按这些源捕获桌面、窗口和选项卡
- [SerialAllowAllPortsForUrls](/DeployEdge/microsoft-edge-policies#serialallowallportsforurls) - 自动授予网站连接所有串行端口的权限
- [SerialAllowUsbDevicesForUrls](/DeployEdge/microsoft-edge-policies#serialallowusbdevicesforurls) - 自动授予网站连接到 USB 串行设备的权限
- [SmartScreenDnsRequestsEnabled](/DeployEdge/microsoft-edge-policies#smartscreendnsrequestsenabled) - 启用 Microsoft Defender SmartScreen DNS 请求
- [TabCaptureAllowedByOrigins](/DeployEdge/microsoft-edge-policies#tabcaptureallowedbyorigins) - 允许按这些源捕获选项卡
- [WebSQLInThirdPartyContextEnabled](/DeployEdge/microsoft-edge-policies#websqlinthirdpartycontextenabled) - 强制重新启用第三方上下文中的 WebSQL
- [WindowCaptureAllowedByOrigins](/DeployEdge/microsoft-edge-policies#windowcaptureallowedbyorigins) - 允许按这些源捕获窗口和选项卡

## <a name="version-960105462-december-17"></a>版本 96.0.1054.62：12 月 17 日

修复了各种 bug 和性能问题。

## <a name="version-960105457-december-14"></a>版本 96.0.1054.57：12 月 14 日

> [!Important]
> 此更新包含 [CVE-2021-4102](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-4102) 的修补程序，Chromium 团队已将其报告为具有自动散布型病毒攻击。 有关详细信息，请参阅[安全更新指南](https://msrc.microsoft.com/update-guide)。

[此处](/deployedge/microsoft-edge-relnotes-security#december-14-2021) 列出了稳定渠道安全性更新。

## <a name="version-960105453-december-10"></a>版本 96.0.1054.53：12 月 10 日

[此处](/deployedge/microsoft-edge-relnotes-security#december-10-2021) 列出了稳定频道的安全更新。

## <a name="version-960105443-december-2"></a>版本 96.0.1054.43：12 月 2 日

修复了各种 bug 和性能问题。

## <a name="version-960105441-november-30"></a>版本 96.0.1054.41：11 月 30 日

修复了各种 bug 和性能问题。

## <a name="version-960105434-november-23"></a>版本 96.0.1054.34：11 月 23 日

修复了各种 bug 和性能问题。

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
