---
title: Microsoft Edge Stable 渠道发行说明
ms.author: aguta
author: AndreaLBarr
manager: srugh
ms.date: 10/14/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Stable 渠道发行说明
ms.openlocfilehash: 6ed7942320875a57e43bea73c98bac6cafe6146e
ms.sourcegitcommit: 568c379989a5fbc64ca3d724a0afb69bbc650b41
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/14/2021
ms.locfileid: "12094505"
---
# <a name="release-notes-for-microsoft-edge-stable-channel"></a>Microsoft Edge Stable 渠道发行说明

这些发行说明提供有关 Microsoft Edge Stable 渠道中包含的新功能和非安全更新的信息。

- [此处](microsoft-edge-relnotes-security.md)列出所有安全更新。
- Microsoft Edge 稳定渠道的存档发行说明位于[此处](microsoft-edge-relnote-archive-stable-channel.md)。

 若要了解 Microsoft Edge 渠道，请参阅 [Microsoft Edge 渠道概述](microsoft-edge-channels.md)。

> [!NOTE]
> 对于稳定渠道，更新将在一天或多天内逐步推出。 要了解详细信息，请参阅 [Microsoft Edge 更新的渐进式推出](microsoft-edge-update-progressive-rollout.md)。
>
> Microsoft Edge Web 平台不断发展以改进用户体验、安全性和隐私。 要了解详细信息，请参阅 [Microsoft Edge 中即将推出的影响站点兼容性的更改](https://docs.microsoft.com/microsoft-edge/web-platform/site-impacting-changes)。

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

[此处](/deployedge/microsoft-edge-relnotes-security#september-24-2021)列出了稳定频道的安全更新。

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

## <a name="version-92090255-july-22"></a>版本 92.0.902.55：7 月 22 日

[此处](/deployedge/microsoft-edge-relnotes-security#july-22-2021)列出了稳定频道的安全更新。

### <a name="feature-updates"></a>功能更新

**用户可以轻松地在 Microsoft Edge 上进入 Internet Explorer 模式**。 从 Microsoft Edge 版本 92 开始，用户可以在 Microsoft Edge 上以 Internet Explorer 模式重新加载站点，而不是等待站点在 Enterprise 模式站点列表中被配置的同时依赖独立 IE 11 应用程序。 系统将提示用户将网站添加到其本地站点列表，以便在 Microsoft Edge 中导航到的相同页面将在接下来 30 天内自动以 IE 模式呈现。 可以使用 [InternetExplorerIntegrationReloadInIEModeAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) 策略配置此体验，并允许访问 IE 模式入口点，以及允许将站点添加到本地站点列表。 可以使用 [InternetExplorerIntegrationLocalSiteListExpirationDays](/deployedge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) 策略调整将站点保留在本地站点列表中的天数。 请注意，对于端到端体验，Windows 10 版本 1909 需要 KB5003698 或更高版本; Windows 10 版本 2004、Windows 10 版本 20H2 或 Windows 10 版本 21H1 需要 KB5003690 或更高版本。 有关详细信息，请参阅 [ IE 模式下的本地站点列表](/deployedge/edge-ie-mode-local-site-list)。

**MHTML 文件将默认以 Internet Explorer 模式打开**。 从 Microsoft Edge 92 稳定版开始，MHTML 文件类型将在 Microsoft Edge 上以 Internet Explorer 模式自动打开，而不是在 Internet Explorer (IE11) 打开。 在用浏览器查看 Outlook 电子邮件时会经常遇到这种情况。 此更改仅在 IE11 是此文件类型的默认处理程序时发生。 如果想要更改此设置，可以在安装稳定版本 92 更新之前使用[此指南](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)。

**"禁用开发人员模式扩展"警告可以消除 2 周**。 从 Microsoft Edge 版本 92 开始，可以在警告对话框下拉列表中选择将"禁用开发人员模式扩展"警告暂停 2 周。

**直接从工具栏管理扩展**。 工具栏上新增的扩展菜单将允许你轻松隐藏/固定扩展。 管理扩展和查找新扩展的快速链接将使你轻松找到新扩展和管理现有扩展。

**自动播放的默认值将设置为限制**。  为了帮助你在上网时保持专注，从 Microsoft Edge 版本 92 开始，我们将自动播放媒体的默认设置从“允许”更改成了“限制”。

**付款工具现在可跨设备同步**。 从 Microsoft Edge 版本 92 开始，可以选择跨已登录设备同步付款信息。 请注意：这是限制性的功能推出。 如果看不到此功能，请在我们继续推出时再检查。
目前，此功能仅在美国可用，并且仅适用于 MSA 用户（而非 AAD）

**字体呈现的改进**。 改进了文本呈现，以提高清晰度并降低模糊度。 请注意：这是限制性的功能推出。 如果看不到此功能，请在我们继续推出时再检查。

**“收藏夹”和“集锦”等工具栏按钮功能将记住用户将其固定到窗口一侧的选择**。 现在默认启用，如果用户选择固定某个工具栏按钮，该按钮将始终以固定状态打开，直到他们决定取消固定。

**用户现在可以通过组策略管理“允许使用此配置文件对工作或学校网站进行单一登录”选项**。  “允许使用此配置文件对工作或学校网站进行单一登录”允许非 AAD 配置文件使用计算机上存在的工作或学校凭据对工作或学校网站使用单一登录。 此选项仅在“设置”->“个人资料”->“用户配置偏好设置”中作为切换项向非 AAD 配置文件的最终用户显示。  可以使用 [AADWebSiteSSOUsingThisProfileEnabled](/deployedge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) 策略配置该行为。  

**密码运行状况**。必须在不同帐户中使用较强且唯一的密码，以保持上网安全。 但是，这一点说起来容易，做起来难，并且大多数用户都表现出较差的密码习惯，如使用易于猜到的弱密码，或者在不同的帐户中重复使用相同的强密码。

在这一最新版本的 Microsoft Edge 中，使用较强且唯一的密码的任务将会变得稍微简单一些！ Microsoft Edge 现在将告知你保存的密码是否足够强，并指示是否已在多个站点中使用相应密码，从而有助于保持上网安全。 在 edge://settings/passwords 页面的已保存密码列表中，可以找到你的密码运行状况信息。
  
**提高了已保存密码的隐私程度**。如果你使用的是与他人共享的设备或出于任何原因而未在离开时锁定计算机，你现在可以选择使用设备密码进行第二次验证，以避免其他人获得你的网站密码。 就是这么简单！

**Outlook 扩展**。  随时了解 Microsoft Outlook 收件箱、日历、任务等，而无需打开新的浏览器窗口。  你可以在此处获取新的 Outlook 扩展：[Microsoft Outlook - Microsoft Edge 加载项](https://microsoftedge.microsoft.com/addons/detail/microsoft-outlook/kkpalkknhlklpbflpcpkepmmbnmfailf?hl=en-US)

**与 Chromium 开源项目保持一致，Microsoft Edge正在更新其在网页上呈现表的方式**。 此更改修复了已知问题，使Microsoft Edge更接近表在 Web/其他浏览器中呈现的指定方式。 建议在环境中测试重要工作流是否存在意外问题。 [here](https://docs.google.com/document/d/16PFD1GtMI9Zgwu0jtPaKZJ75Q2wyZ9EZnVbBacOfiNA/edit)提供完整的解释器。

### <a name="new-policies"></a>新策略

- [AADWebSiteSSOUsingThisProfileEnabled](/DeployEdge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled)：已启用使用此配置文件对工作或学校网站进行单一登录的功能
- [AutomaticHttpsDefault](/DeployEdge/microsoft-edge-policies#automatichttpsdefault)：配置自动 HTTPS
- [HeadlessModeEnabled](/DeployEdge/microsoft-edge-policies#headlessmodeenabled)：控制无头模式的使用
- [InsecurePrivateNetworkRequestsAllowed](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed)：指定是否允许不安全网站向专用性较强的网络端点提出请求
- [InsecurePrivateNetworkRequestsAllowedForUrls](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls)：允许列出的站点从不安全环境向专用性较强的网络端点提出请求
- [InternetExplorerIntegrationLocalSiteListExpirationDays](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) 指定站点在本地 IE 模式站点列表中保留的天数
- [InternetExplorerIntegrationReloadInIEModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) 允许以 Internet Explorer 模式重新加载未配置的网站
- [SharedArrayBufferUnrestrictedAccessAllowed](/DeployEdge/microsoft-edge-policies#sharedarraybufferunrestrictedaccessallowed)：指定是否可以在非跨源隔离环境中使用 SharedArrayBuffers

### <a name="deprecated-policy"></a>不推荐使用的策略

- [InternetExplorerIntegrationTestingAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationtestingallowed)：允许 Internet Explorer 模式测试

### <a name="obsoleted-policy"></a>已弃用策略

- [EnableSha1ForLocalAnchors](/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors)：当证书由本地信任锚点颁发时，允许使用 SHA-1 签名的证书

## <a name="version-91086471-july-19"></a>版本 91.0.864.71：7 月 19 日

> [!Important]
>此更新包含 [CVE-2021-30563](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30563) 的修补程序，Chromium 团队已将其报告为具有外围攻击。 有关详细信息，请参阅[安全更新指南](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002)。

[此处](/deployedge/microsoft-edge-relnotes-security#july-19-2021)列出了稳定频道的安全更新。

## <a name="version-91086467-july-8"></a>版本 91.0.864.67：7 月 8 日

修复了各种 bug 和性能问题。

## <a name="version-91086464-july-2"></a>版本 91.0.864.64: 7 月 2 日

修复了各种 bug 和性能问题。

## <a name="version-91086459-june-24"></a>版本 91.0.864.59：6 月 24 日

[此处](/deployedge/microsoft-edge-relnotes-security#june-24-2021) 列出了稳定频道的安全更新。

## <a name="version-91086454-june-18"></a>版本 91.0.864.54：6 月 18 日

> [!Important]
> 此更新包含 [CVE-2021-30554](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30554) 的修补程序，Chromium 团队已将其报告为具有外围攻击。 有关详细信息，请参阅[安全更新指南](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002)。

[此处](/deployedge/microsoft-edge-relnotes-security#june-18-2021) 列出了稳定频道的安全更新。

## <a name="version-91086448-june-11"></a>版本 91.0.864.48：6 月 11 日

> [!Important]
>此更新包含 [CVE-2021-30551](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30551) 的修补程序，Chromium 团队已将其报告为具有外围攻击。 有关详细信息，请参阅[安全更新指南](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002)。

[此处](/deployedge/microsoft-edge-relnotes-security#june-11-2021) 列出了稳定频道的安全更新。

## <a name="version-91086441-june-3"></a>版本 91.0.864.41：6 月 3 日

[此处](/deployedge/microsoft-edge-relnotes-security#june-3-2021) 列出了稳定频道的安全更新。

## <a name="version-91086437-may-27"></a>版本 91.0.864.37：5 月 27 日

[此处](/deployedge/microsoft-edge-relnotes-security#may-27-2021) 列出了稳定频道的安全更新。

### <a name="feature-updates"></a>功能更新

- **标识源自代理级别的 Microsoft Defender 应用程序防护容器的网络流量**。 从 Microsoft Edge 版本 91 开始，内置了对源自应用程序防护容器的网络流量进行标记的支持，允许企业识别这些流量并应用特定策略。

- **支持允许将收藏夹从主机同步到边缘应用程序防护容器的选项**。 从 Microsoft Edge 版本 91 开始，用户可以选择配置应用程序防护以将其收藏夹从主机同步到容器。 这确保了容器上也可显示新的收藏夹。

- **从 Microsoft Edge 版本 91 开始，如果在未经用户交互的情况下启动对计算机有害的下载，并且 SmartScreen 应用程序信誉度检查不支持此下载，则浏览器将自动中断该类型的下载**。 用户可能会覆盖并继续下载，方法是右键单击并在下载项上选择“保留”。 企业管理员可能会通过配置以下策略选择退出此行为：
  - [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings.md) - 对域上的指定文件类型禁用基于下载文件类型扩展名的警告

    有关详细信息，请参阅 [Microsoft Edge 安全性下载中断](microsoft-edge-security-downloads-interruptions.md)。

- **支持语音识别 API。** 从 Microsoft Edge 版本 91 开始，将添加对 Google.com 和类似网站上语音识别命令的 API 支持。 此功能仅限于一组启用了实验的随机选择的用户。 这些用户向功能团队提供反馈。

- **使用新的主题颜色个性化设置浏览器**。 使用“设置”->“外观”页上的十四种新主题颜色之一打造你自己的 Microsoft Edge。 也可以从 Microsoft Edge 加载项网站安装自定义主题。 [了解详细信息](https://techcommunity.microsoft.com/t5/articles/make-microsoft-edge-your-own-with-themes/m-p/2083165)

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

添加了六条新的策略。 从 [Microsoft Edge 企业版登录页面](https://www.microsoft.com/edge/business/download) 下载更新的管理模板。 添加了以下新策略：

- [ApplicationGuardTrafficIdentificationEnabled](/DeployEdge/microsoft-edge-policies#applicationguardtrafficidentificationenabled) - 应用程序防护流量标识
- [ExplicitlyAllowedNetworkPorts](/DeployEdge/microsoft-edge-policies#explicitlyallowednetworkports) - 显式允许的网络端口
- [ImportStartupPageSettings](/DeployEdge/microsoft-edge-policies#importstartuppagesettings) - 允许导入启动页设置
- [MathSolverEnabled](/DeployEdge/microsoft-edge-policies#mathsolverenabled) - 允许用户截取数学问题，并通过 Microsoft Edge 中的分步说明获取解决方案
- [NewTabPageContentEnabled](/DeployEdge/microsoft-edge-policies#newtabpagecontentenabled) - 允许新选项卡页上的 Microsoft 新闻内容
- [NewTabPageQuickLinksEnabled](/DeployEdge/microsoft-edge-policies#newtabpagequicklinksenabled) - 允许新选项卡页上的快速链接

#### <a name="obsoleted-policy"></a>已过时的策略

- [ProactiveAuthEnabled](./microsoft-edge-policies.md#proactiveauthenabled) - 启用主动身份验证
<!-- end major 91 -->

<!-- Archive from 89.0.774.45: March 4 to 90.0.818.66: May 20 ->
<!-- Archive from 86.0.622.43: October 15 to beta 88.0.705.81: February 25  ->
<!-- Archive from 86.0.622.38-october-9 to beta 86.0.62.215-september-14  ->
<!-- Archived to version 84.0.522.40: July 16 -->

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
