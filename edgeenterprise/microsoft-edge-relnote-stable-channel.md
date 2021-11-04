---
title: Microsoft Edge Stable 渠道发行说明
ms.author: leahtu
author: dan-wesley
manager: srugh
ms.date: 11/01/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Stable 渠道发行说明
ms.openlocfilehash: 5c8a893254d9c9be0ccf22c76a3f873f31a58756
ms.sourcegitcommit: 42f01cad0bf15224222b2aeadb48f03d46c35723
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "12154493"
---
# <a name="release-notes-for-microsoft-edge-stable-channel"></a>Microsoft Edge Stable 渠道发行说明

这些发行说明提供有关 Microsoft Edge Stable 渠道中包含的新功能和非安全更新的信息。

- [此处](microsoft-edge-relnotes-security.md)列出所有安全更新。
- Microsoft Edge 稳定渠道的存档发行说明位于[此处](microsoft-edge-relnote-archive-stable-channel.md)。

 若要了解 Microsoft Edge 渠道，请参阅 [Microsoft Edge 渠道概述](microsoft-edge-channels.md)。

> [!NOTE]
> 对于稳定渠道，更新将在一天或多天内逐步推出。 要了解详细信息，请参阅 [Microsoft Edge 更新的渐进式推出](microsoft-edge-update-progressive-rollout.md)。
>
> Microsoft Edge Web 平台不断发展以改进用户体验、安全性和隐私。 要了解详细信息，请参阅 [Microsoft Edge 中即将推出的影响站点兼容性的更改](/microsoft-edge/web-platform/site-impacting-changes)。

## <a name="version-94099258-october-30"></a>版本 94.0.992.58：10 月 30 日

修复了扩展稳定版的各种 bug 和性能问题。

## <a name="version-950102040-october-29"></a>版本 95.0.1020.40：10 月 29 日

> [!IMPORTANT]
> 此次更新包含 [CVE-2021-38000](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-38000) 和 [CVE-2021-38003](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-38003) 的修复程序，Chromium 团队已报告该程序存在在野攻击。 有关详细信息，请参阅[安全更新指南](https://msrc.microsoft.com/update-guide)。

[此处](/deployedge/microsoft-edge-relnotes-security#october-29-2021) 列出了稳定频道的安全更新。

## <a name="version-950102038-october-28"></a>版本 95.0.1020.38：10 月 28 日

修复了各种 bug 和性能问题。

## <a name="version-94099257-october-27"></a>版本 94.0.992.57：10 月 27 日

修复了扩展稳定版的各种 bug 和性能问题。

## <a name="version-950102030-october-21"></a>版本 95.0.1020.30: 10 月 21 日

[此处](/deployedge/microsoft-edge-relnotes-security#october-21-2021)列出了稳定频道的安全更新。

### <a name="feature-updates"></a>功能更新

- **在 Microsoft Edge 中查看对 SharePoint Online 库的文件资源管理器支持。**  现在可以在 SharePoint Online 新式文档库上启用“文件资源管理器视图”功能。 若要使此体验可见且适用于用户，需要启用 Microsoft Edge 策略 [在 Microsoft Edge 中为 SharePoint 页面配置“文件资源管理器视图”功能](/deployedge/microsoft-edge-policies#configureviewinfileexplorer)，并更新 SharePoint Online 租户配置。 了解更多信息: [在 Microsoft Edge 中使用“文件资源管理器”查看 SharePoint 文件](/SharePoint/sharepoint-view-in-edge)。

- **Intranet 区域文件 URL 链接将在 Windows 文件资源管理器中打开。**  你可以允许文件 URL 链接到源自 Intranet 区域 HTTPS 网站的 Intranet 区域文件，以打开该文件或目录的 Windows 文件资源管理器。 可以使用 [IntranetFileLinksEnabled](/deployedge/microsoft-edge-policies#intranetfilelinksenabled) 策略启用此体验。

- **对下载体验进行的改进。** 对下载用户体验的支持已扩展到渐进式 Web 应用程序 PWA 和 WebView。 我们还将开始支持拖放到文件资源管理器和桌面。

- **继续你在 PDF 文件上的工作。**  现在，你将能够从上次关闭 PDF 文档的位置继续阅读。

- **当笔记本电脑进入延长电池使用时间模式时，效率模式会延长延长电池寿命。**  当笔记本电脑进入电池保护模式时，效率模式将变得活跃，以允许浏览器管理资源使用状态来延长机器的电池寿命。 当效率模式变为活动状态时，将有四个选项: 拔出电源和电池电量不足、不拔出电源、始终和从不。 请注意: 这是限制性功能推出的功能。 如果无法看到此功能，请在我们稍后继续推出时再返回查看。

- **添加到 PDF 文档的自由格式文本框。** 我们现在支持向 PDF 文档添加自由格式文本框。 可以使用这些框来填写表单并添加可见笔记。

- **添加到集合的引文支持。**  我们改进了集合体验，尤其是对于学生和研究人员。 集合将开始支持引文和阅读列表。

- **更快地更新密码，并减少单击次数。** 现在，浏览器将直接转到给定网站的“更改密码”页面。 此操作可节省时间和单击次数，无需手动导航到页面。 在进入此页面上后，浏览器还将自动填充现有密码，并建议使用强大且唯一的新密码。  请注意: 此功能目前仅在有限数量的站点上可用。

- **自动创建账户。** 我们现在在注册页面上提供额外的支持，允许一键创建在线账户。 可以在点击报名表中任何表单字段时，选择建议下拉来执行此操作。 这样做不仅会显示与注册表单相关的信息，而且还会显示一个强大的新密码建议。 选择后，所有相关信息将填充在相应的字段中，建议的密码将在提交到网站时自动存储。 请注意: 此功能目前仅在有限数量的站点上可用。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

- [BrowserLegacyExtensionPointsBlockingEnabled](/DeployEdge/microsoft-edge-policies#browserlegacyextensionpointsblockingenabled) 启用浏览器旧扩展点阻止
- [CrossOriginWebAssemblyModuleSharingEnabled](/DeployEdge/microsoft-edge-policies#crossoriginwebassemblymodulesharingenabled) 指定 WebAssembly 模块是否可以跨源发送
- [DisplayCapturePermissionsPolicyEnabled](/DeployEdge/microsoft-edge-policies#displaycapturepermissionspolicyenabled) 指定是否检查或跳过显示捕获权限策略
- [InternetExplorerIntegrationWindowOpenHeightAdjustment](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationwindowopenheightadjustment) 配置来自 IE 模式页面与 Edge 模式页面的 window.open 高度像素调整
- [InternetExplorerIntegrationWindowOpenWidthAdjustment](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationwindowopenwidthadjustment) 配置来自 IE 模式页面与 Edge 模式页面的 window.open 宽度像素调整
- [IntranetFileLinksEnabled](/DeployEdge/microsoft-edge-policies#intranetfilelinksenabled) 允许在 Windows 文件资源管理器中打开来自 Microsoft Edge 的 Intranet 区域文件 URL 链接
- [NewSmartScreenLibraryEnabled](/DeployEdge/microsoft-edge-policies#newsmartscreenlibraryenabled) 启用新的 SmartScreen 库
- [ShadowStackCrashRollbackBehavior](/DeployEdge/microsoft-edge-policies#shadowstackcrashrollbackbehavior) 配置 ShadowStack 故障回滚行为
- [VisualSearchEnabled](/DeployEdge/microsoft-edge-policies#visualsearchenabled) 已启用视觉搜索

#### <a name="obsoleted-policies"></a>已过时的策略

- [InternetExplorerIntegrationTestingAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationtestingallowed)：允许 Internet Explorer 模式测试
- [LegacySameSiteCookieBehaviorEnabled](/DeployEdge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) 启用默认的旧 SameSite Cookie 行为设置

## <a name="version-94099250-october-14"></a>版本 94.0.992.50：10 月 14 日

修复了各种 bug 和性能问题。

## <a name="version-94099247-october-11"></a>版本 94.0.992.47：10 月 11 日

[此处](/deployedge/microsoft-edge-relnotes-security#october-11-2021) 列出了稳定频道的安全更新。

## <a name="version-94099238-october-1"></a>版本 94.0.992.38：10 月 1 日

> [!Important]
> 此次更新包含 [CVE-2021-37975](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-37975) 和 [CVE-2021-37976](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-37976) 的修复程序，Chromium 团队已报告该程序存在在野攻击。 有关详细信息，请参阅[安全更新指南](https://msrc.microsoft.com/update-guide)。

[此处](/deployedge/microsoft-edge-relnotes-security#october-01-2021) 列出了稳定频道的安全更新。

## <a name="version-94099237-september-30"></a>版本 94.0.992.37：9 月 30 日

修复了各种 bug 和性能问题。

## <a name="version-94099231-september-24"></a>版本 94.0.992.31：9 月 24 日

> [!Important]
> 此更新包含 [CVE-2021-37973](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-37973) 的修补程序，Chromium 团队已将其报告为具有野外漏洞。 有关详细信息，请参阅 [安全更新指南](https://msrc.microsoft.com/update-guide)。

[此处](/deployedge/microsoft-edge-relnotes-security#september-24-2021) 列出了稳定渠道安全性更新。

### <a name="feature-updates"></a>功能更新

- **Microsoft Edge 已完成向 4 周更新节奏的迁移。**  我们已为主要版本采用新的 4 周发布周期。 在此处阅读详细信息：https://blogs.windows.com/msedgedev/2021/03/12/new-release-cycles-microsoft-edge-extended-stable/

- **即将提供新的扩展稳定选项。**  我们将向托管企业客户提供新的扩展稳定选项。 扩展稳定选项将保留偶数编号修订版，并且每 8 周更新一次。 将提供每两周一次的安全更新。  请在此处查看其他信息：https://blogs.windows.com/msedgedev/2021/07/15/opt-in-extended-stable-release-cycle/

- **改进了打开 MHTML 文件的默认行为。**  如果启用了 IE 模式，则 MHTML 文件将继续在 IE 模式下打开，除非 MHTML 文件是从 Microsoft Edge 保存的（在 Microsoft Edge 中使用“另存为”或“页面另存为”选项）。 如果文件是从 Microsoft Edge 保存的，则它现在将在 Microsoft Edge 中打开。  此更改将修复在 IE 模式下打开从 Microsoft Edge 保存的 MHTML 文件时观察到的绘制问题。

- **限制专用网络请求以保护上下文。** 从 Internet 上的页面中访问本地 (Intranet) 网络上的资源需要通过 HTTPS 传递这些页面。 此更改发生在 Microsoft Edge 所基于的 Chromium 项目中。 有关详细信息，请导航到 [Chrome 平台状态条目](https://chromestatus.com/feature/5436853517811712)。 可使用两个兼容性策略支持需要保留与非安全页面的兼容性的方案：[InsecurePrivateNetworkRequestAllowed](/deployedge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed) 和 [InsecurePrivateNetworkRequestAllowedForUrls](/deployedge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls)。

- **阻止混合内容下载。** 安全页面将仅下载托管在其他安全页面上的文件，并且如果从安全页面启动，则将阻止托管在非安全（非 HTTPS）页面上的下载。 此更改发生在 Microsoft Edge 所基于的 Chromium 项目中。 有关详细信息，请导航到 [Google 安全博客条目](https://security.googleblog.com/2020/02/protecting-users-from-insecure_6.html)。

- **为本地帐户启用隐式登录。** 通过启用 [OnlyOnPremisesImplicitSigninEnabled](/deployedge/microsoft-edge-policies#onlyonpremisesimplicitsigninenabled) 策略，将仅启用本地帐户进行隐式登录。  Microsoft Edge 将不会尝试隐式登录到 MSA 或 AAD 帐户。 从本地帐户升级到 AAD 帐户也将停止。

- **新建辅助功能设置页。**  我们已将与辅助功能相关的设置组合在单个页面上。 可以在主设置列表下找到新的 edge://settings/accessibility 页面。 可在此处找到可放大网页和在焦点区域周围显示高可见性大纲的设置，以及有助于改善 Web 浏览体验的其他设置。 我们将继续在 Microsoft Edge 的未来版本中在此处添加新设置。

***新策略***

- [ApplicationGuardPassiveModeEnabled](/DeployEdge/microsoft-edge-policies#applicationguardpassivemodeenabled) 忽略应用程序防护网站列表配置并正常浏览 Edge
- [OnlyOnPremisesImplicitSigninEnabled](/DeployEdge/microsoft-edge-policies#onlyonpremisesimplicitsigninenabled) 仅启用了隐式登录的本地帐户
- [WebRtcRespectOsRoutingTableEnabled](/DeployEdge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) 在通过 WebRTC 建立对等连接时启用对 Windows OS 路由表规则的支持

***已过时的策略***

- [UserAgentClientHintsEnabled](/DeployEdge/microsoft-edge-policies#useragentclienthintsenabled) 启用 User-Agent 客户端提示功能

## <a name="version-93096152-september-16"></a>版本 93.0.961.52：9 月 16 日

>[!Important]
>此更新包含[CVE-2021-30633](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30632)的修补程序，Chromium 团队已将其报告为具有外围攻击。 有关详细信息，请参阅 [安全更新指南](https://msrc.microsoft.com/update-guide)。

[此处](/deployedge/microsoft-edge-relnotes-security#september-16-2021) 列出了稳定渠道安全性更新。

## <a name="version-93096147-september-11"></a>版本 93.0.961.47：9 月 11 日

> [!Important]
> 此更新包含 [CVE-2021-30632](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30632) 修补程序，Chromium 团队已将其报告为具有外围攻击。 有关详细信息，请参阅 [安全更新指南](https://msrc.microsoft.com/update-guide)。

[此处](/deployedge/microsoft-edge-relnotes-security#september-11-2021) 列出了稳定渠道安全性更新。

## <a name="version-93096144-september-9"></a>版本 93.0.961.44：9 月 9 日

[此处](/deployedge/microsoft-edge-relnotes-security#september-09-2021) 列出了稳定渠道安全性更新。

## <a name="version-93096138-september-2"></a>版本 93.0.961.38: 9 月 2 日

[此处](/deployedge/microsoft-edge-relnotes-security#september-02-2021) 列出了稳定渠道安全性更新。

### <a name="feature-updates"></a>功能更新

- **Microsoft Edge 中的初始首选项。**  现在，Microsoft Edge 支持有限数量的“初始首选项”(旧称为“主首选项”)。 在其用户首次运行浏览器之前，IT 管理员可以将这些设置部署为默认设置。 此处的其他信息: [使用首次运行的“初始首选项”设置配置 Microsoft Edge](/deployedge/initial-preferences-support-on-microsoft-edge-browser)。

- **Microsoft Edge 上的 IE 模式将支持“无合并”行为。**  对于最终用户，当从 IE 模式应用程序启动新的浏览器窗口时，其将位于单独会话中，类似于 IE11 中的无合并行为。 需要调整站点列表，从而配置需要阻止会话共享为“无合并”的站点。 在后台，对于每个 Microsoft Edge 窗口，当首次在该窗口中访问 IE 模式选项卡时，如果其为其中一个指定的“无合并”站点，则该窗口至少会锁定到所有其他Microsoft Edge 窗口的不同“无合并”IE 会话中，直到最后的 IE 模式选项卡在该窗口中关闭。 此遵循之前的行为: 用户可以启动具有不合并的 IE，也可以通过其他机制在无合并的情况下启动 Microsoft Edge。  此处的其他信息: [IE 模式疑难解答与 FAQ | Microsoft Docs](/deployedge/edge-ie-mode-faq#does-ie-mode-on-microsoft-edge-support-the--nomerge--option-that-was-supported-in-internet-explorer-11-)

- **用于停止隐式登录的新策略。**  [ImplicitSignInEnabled](/deployedge/microsoft-edge-policies#implicitsigninenabled) 策略允许系统管理员在Microsoft Edge 浏览器上禁用隐式登录。

- **用于绕过 ClickOnce 和 DirectInvoke 提示的策略。** 我们更新了策略，以允许绕过来自指定域的指定文件类型的 ClickOnce 提示和 DirectInvoke 应用。 为此，需要:

  - 启用 [ClickOnceEnabled](/deployedge/microsoft-edge-policies#clickonceenabled) 或 [DirectInvokeEnabled](/deployedge/microsoft-edge-policies#directinvokeenabled)
  - 启用 [AutoOpenFileTypes](/deployedge/microsoft-edge-policies#autoopenfiletypes) 策略，并设置应禁用 ClickOnce 和 DirectInvoke 的特定文件类型的列表
  - 启用 [AutoOpenAllowedForURLs](/deployedge/microsoft-edge-policies#autoopenallowedforurls) 策略并设置将禁用 ClickOnce 和 DirectInvoke 的特定域的列表。

  注意: AutoOpenAllowedForURL 为 AutoOpenFileTypes 的策略。 如果未设置 AutoOpenAllowedForURL 但设置了 AutoOpenFileTypes，则列出的文件类型将从所有 URL 中自动打开。

- **选项卡组。**  我们正在启用选项卡分组，其有助于将选项卡分类为用户定义的组，并帮助高效查找、切换和管理多个工作流中的选项卡。  

- **使用“垂直标签”时隐藏标题栏。**  当在“垂直标签”中时，隐藏浏览器的标题栏以重获额外多个像素。 现在，你可以转到 edge://settings/appearance，在“自定义工具栏”部分下，选择在“垂直标签”模式下隐藏标题栏的选项。

- **悬停工具栏中的视频画中画(PiP)。**  当将鼠标悬停在受支持的视频上时，工具栏将显示，允许在 PiP 窗口中查看该视频。  请注意: 此功能当前适用于 macOS 上的 Microsoft Edge 用户。  

- **在 TLS 中删除 3DES。 将删除对 TLS_RSA_WITH_3DES_EDE_CBC_SHA 密码套件的支持。** 此更改发生在 Microsoft Edge 基于的 Chromium 项目中。 有关详细信息，请导航到 [Chrome 平台状态条目](https://chromestatus.com/feature/6678134168485888)。 此外，在 Microsoft Edge 版本 93 中，[TripleDESEnabled](/deployedge/microsoft-edge-policies#tripledesenabled) 策略将可用于支持需要保留与过时服务器的兼容性的场景。 此兼容性策略将过时，并停止在 Microsoft Edge 版本 95 中工作。 请确保在此之前更新受影响的服务器。

***新策略***

- [AutoplayAllowlist](/DeployEdge/microsoft-edge-policies#autoplayallowlist) 允许在特定网站上自动播放媒体
- [CECPQ2Enabled](/DeployEdge/microsoft-edge-policies#cecpq2enabled) 为 TLS 启用的 CECPQ2 后量子密钥协议
- [ConfigureViewInFileExplorer](/DeployEdge/microsoft-edge-policies#configureviewinfileexplorer) 在文件资源管理器中为 Microsoft Edge 中的 SharePoint 页面配置视图
- [DefaultJavaScriptJitSetting](/DeployEdge/microsoft-edge-policies#defaultjavascriptjitsetting) 控制 JavaScript JIT 的使用
- [ShowPDFDefaultRecommendationsEnabled](/DeployEdge/microsoft-edge-policies#showpdfdefaultrecommendationsenabled) 允许将 Microsoft Edge 设置为默认 PDF 阅读器的通知
- [FeatureFlagOverridesControl](/DeployEdge/microsoft-edge-policies#featureflagoverridescontrol) 配置用户替代功能标志的能力
- [ImplicitSignInEnabled](/DeployEdge/microsoft-edge-policies#implicitsigninenabled) 启用隐式登录
- [InternetExplorerIntegrationCloudSiteList](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationcloudsitelist) 配置企业模式云站点列表
- [InternetExplorerIntegrationSiteListRefreshInterval](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationsitelistrefreshinterval) 配置刷新企业模式网站列表的频率
- [JavaScriptJitAllowedForSites](/DeployEdge/microsoft-edge-policies#javascriptjitallowedforsites) 允许 JavaScript 在这些网站上使用 JIT
- [JavaScriptJitBlockedForSites](/DeployEdge/microsoft-edge-policies#javascriptjitblockedforsites) 阻止 JavaScript 在这些网站上使用 JIT
- [LocalBrowserDataShareEnabled](/DeployEdge/microsoft-edge-policies#localbrowserdatashareenabled) 让 Windows 可以搜索本地Microsoft Edge 浏览数据
- [MAUEnabled](/DeployEdge/microsoft-edge-policies#mauenabled) 始终使用 Microsoft AutoUpdate 作为 Microsoft Edge 的更新程序
- [MSAWebSiteSSOUsingThisProfileAllowed](/DeployEdge/microsoft-edge-policies#msawebsitessousingthisprofileallowed) 允许使用此个人资料在 Microsoft 网站上进行单一登录
- [OneAuthAuthenticationEnforced](/DeployEdge/microsoft-edge-policies#oneauthauthenticationenforced) 强制执行以进行登录的 OneAuth 身份验证流
- [PasswordGeneratorEnabled](/DeployEdge/microsoft-edge-policies#passwordgeneratorenabled) 允许用户在联机创建帐户时获取强密码建议
- [PrimaryPasswordSetting](/DeployEdge/microsoft-edge-policies#primarypasswordsetting) 配置要求用户在使用密码自动填充时输入其设备密码的设置
- [PrintingWebpageLayout](/DeployEdge/microsoft-edge-policies#printingwebpagelayout) 设置打印的布局
- [RemoteDebuggingAllowed](/DeployEdge/microsoft-edge-policies#remotedebuggingallowed) 允许远程调试
- [RelaunchWindow](/DeployEdge/microsoft-edge-policies#relaunchwindow) 设置重新启动的时间间隔
- [TravelAssistanceEnabled](/DeployEdge/microsoft-edge-policies#travelassistanceenabled) 启用旅行协助
- [TripleDESEnabled](/DeployEdge/microsoft-edge-policies#tripledesenabled) 在 TLS 中启用 3DES 密码套件
- [WAMAuthBelowWin10RS3Enabled](/DeployEdge/microsoft-edge-policies#wamauthbelowwin10rs3enabled) 已启用低于 Windows 10 RS3 的版本中用于身份验证的 WAM

***已弃用的策略***

- [LegacySameSiteCookieBehaviorEnabled](/DeployEdge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) 启用默认的旧 SameSite Cookie 行为设置

***已过时的策略***

- [NewTabPageSetFeedType](/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype) 配置 Microsoft Edge 新选项卡页面体验

***其他更改***

- [ConfigureShare](/DeployEdge/microsoft-edge-policies#configureshare) 添加 mac 平台支持
- [PasswordMonitorAllowed](/DeployEdge/microsoft-edge-policies#passwordmonitorallowed) 添加 mac 平台支持

## <a name="version-92090284-august-26"></a>版本 92.0.902.84: 8 月 26 日

修复了各种 bug 和性能问题。

## <a name="version-92090278-august-19"></a>版本 92.0.902.78：8 月 19 日

[此处](/deployedge/microsoft-edge-relnotes-security#august-19-2021) 列出了稳定渠道安全更新。

## <a name="version-92090273-august-12"></a>版本 92.0.902.73：8 月 12 日

修复了各种 bug 和性能问题。

## <a name="version-92090267-august-5"></a>版本 92.0.902.67：8 月 5 日

[此处](/deployedge/microsoft-edge-relnotes-security#august-05-2021)列出了稳定频道的安全更新。

## <a name="version-92090262-july-29"></a>版本 92.0.902.62：6 月 29 日

修复了各种 bug 和性能问题。

### <a name="modified-policy"></a>修改的策略

- AutoplayAllowed - 现在，设置为“已禁用”将媒体自动播放设置为“限制”
<!-- end major 92 -->
<!-- Archive from Version 92.0.902.55: July 22 to Version 91.0.864.37: May 27 -->
<!-- Archive from 89.0.774.45: March 4 to 90.0.818.66: May 20 ->
<!-- Archive from 86.0.622.43: October 15 to beta 88.0.705.81: February 25  ->
<!-- Archive from 86.0.622.38-october-9 to beta 86.0.62.215-september-14  ->
<!-- Archived to version 84.0.522.40: July 16 -->

## <a name="see-also"></a>另请参阅

- [Microsoft Edge 企业版登录页面](https://aka.ms/EdgeEnterprise)
