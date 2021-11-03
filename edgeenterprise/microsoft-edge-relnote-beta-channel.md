---
title: Microsoft Edge Beta 渠道发行说明
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 11/01/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge Beta 渠道发行说明
ms.openlocfilehash: 57ea92fde42d4ad4c63f238c3b30fa218ee5b360
ms.sourcegitcommit: 42f01cad0bf15224222b2aeadb48f03d46c35723
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "12154514"
---
# <a name="release-notes-for-microsoft-edge-beta-channel"></a>Microsoft Edge Beta 渠道的发行说明

本发行说明提供有关 Microsoft Edge Beta 渠道中包含的新功能和非安全更新的信息。 [此处](microsoft-edge-relnote-archive-beta-channel.md)提供了这些发行说明的存档版本。

> [!NOTE]
> Microsoft Edge Web 平台不断发展以改进用户体验、安全性和隐私。 要了解详细信息，请参阅 [Microsoft Edge 中即将推出的影响站点兼容性的更改](/microsoft-edge/web-platform/site-impacting-changes)。

## <a name="version-96010548-november-1"></a>版本 96.0.1054.8：11 月 1 日

### <a name="feature-updates"></a>功能更新

- **直接通过协议 (PWA) 启动渐进式 Web 应用。** 让已安装的 PWA 处理使用特定协议的链接，实现更加集成的体验。

- **了解如何使用数学规划求解求解数学问题。** 我们很高兴地宣布，您可以使用数学规划求解在 Microsoft Edge中获取有关各种数学概念的帮助。 这些概念包括从算术和二次方等式到三角法和计算。 利用数学规划求解，您可以拍摄手写或打印的数学问题的图片，然后提供一个即时解决方案以及分步说明，以帮助您了解如何在没有帮助的情况下找到解决方案。 数学规划求解还附带数学键盘，可用于轻松键入数学问题。 此键盘无需四处搜索传统键盘来查找所需的数学字符。 解决你的问题后，数学规划求解提供了一些选项，可以继续学习测验、工作表和视频教程。

- **滚动 PDF 文档的改进。** 我们正在改进滚动性能，以在 PDF 文档中提供更流畅的滚动体验。 在滚动期间，你将看不到白色条出现。

- **PDF 上的任意多边形突出显示。** 通过添加任意格式突出显示器改进了 PDF 查看和标记体验。 你可以突出显示你无法访问的 PDF 中的部分和扫描过的文档。

- **控制流实施技术 (CET) 。**  Microsoft Edge将开始支持更安全的浏览模式，该模式对浏览器进程使用依赖于硬件的控制流。 控制流在此受支持的硬件上提供：Intel 第 11 代。 或 AMD 管理 3。 可以通过使用组策略将映像文件执行选项 (IFEO) CET。

- **用于错误等同网站的新警告对话框。** 浏览器现在将在 URL 与其他网站非常相似的一些网站上显示警告。 此 UI 使用客户端启发来提醒用户有关可能欺骗热门网站的网站。 有关详细信息，请参阅什么是错[位？。](https://support.microsoft.com/topic/what-is-typosquatting-54a18872-8459-4d47-b3e3-d84d9a362eb0)

- **改进了 IE 模式和新式浏览器之间的切换。**  从此版本的 Microsoft Edge开始，Microsoft Edge 和 Internet Explorer 模式之间的导航将包括表单数据和其他 HTTP 标头。 引用者标头、帖子数据、表单数据和请求方法将跨这两种体验正确转发。 您可以使用 [InternetExplorerIntegrationComplexNavDataTypes 策略指定应包含哪些](/deployedge/microsoft-edge-policies#internetexplorerintegrationcomplexnavdatatypes) 数据类型。

- **公共预览版中适用于 IE 模式的云站点列表管理。**  通过云站点列表管理，可以在云中管理 IE 模式的网站列表，而无需本地基础结构来托管组织的站点列表。 您可以使用云站点列表管理中心中的Microsoft Edge网站列表体验来访问Microsoft 365 管理管理功能。 若要了解更多信息，请参阅适用于 [IE 模式的云站点列表管理 (公共预览) ](./edge-ie-mode-cloud-site-list-mgmt.md) 文章。

- **使用 Microsoft Edge WSUS 更新 WebWiew2。** 使用 WSUS 更新 Microsoft Edge IT 管理员还将能够使用 WSUS Microsoft Edge WebView2。 此功能使管理员能够更轻松地为脱机设备提供服务。

- **Server 的 WSUS 更新。** Microsoft Edge Stable、Beta、Dev)  (的 Microsoft Edge 渠道的 WSUS 和目录更新现在将适用于安装了 Microsoft Edge 的 Windows Server SK，包括 Windows Server 2022。 若要详细了解如何为 WSUS 配置 WSUS Microsoft Edge，请参阅[Update Microsoft Edge](https://docs.microsoft.com/mem/configmgr/apps/deploy-use/deploy-edge?bc=https%3A%2F%2Fdocs.microsoft.com%2FDeployEdge%2Fbreadcrumb%2Ftoc.json&toc=https%3A%2F%2Fdocs.microsoft.com%2FDeployEdge%2Ftoc.json#update-microsoft-edge)。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

- [ApplicationGuardUploadBlockingEnabled](/DeployEdge/microsoft-edge-policies#applicationguarduploadblockingenabled) - 防止在应用程序防护中上传文件。
- [AudioProcessHighPriorityEnabled](/DeployEdge/microsoft-edge-policies#audioprocesshighpriorityenabled) - 允许在音频流上以高于正常Windows。
- [AutoLaunchProtocolsComponentEnabled](/DeployEdge/microsoft-edge-policies#autolaunchprotocolscomponentenabled) - 启用自动启动协议组件。
- [EfficiencyMode](/DeployEdge/microsoft-edge-policies#efficiencymode) - 配置效率模式应处于活动状态时。
- [ForceSyncTypes](/DeployEdge/microsoft-edge-policies#forcesynctypes) - 配置同步包括的类型列表。
- [InternetExplorerIntegrationComplexNavDataTypes](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationcomplexnavdatatypes) - 配置在进入或退出表单模式时是否发送表单数据和 HTTP Internet Explorer标头。
- [InternetExplorerModeToolbarButtonEnabled](/DeployEdge/microsoft-edge-policies#internetexplorermodetoolbarbuttonenabled) - 在工具栏Internet Explorer模式按钮中显示重新加载。
- [PrintPostScriptMode](/DeployEdge/microsoft-edge-policies#printpostscriptmode) - 以PostScript打印。
- [PrintRasterizePdfDpi](/DeployEdge/microsoft-edge-policies#printrasterizepdfdpi) - 以 Rasterize PDF DPI 进行打印。
- [RendererAppContainerEnabled](/DeployEdge/microsoft-edge-policies#rendererappcontainerenabled) - 在应用容器中启用呈现器。
- [SharedLinksEnabled](/DeployEdge/microsoft-edge-policies#sharedlinksenabled) - 在历史记录中显示Microsoft 365应用共享的链接。
- [TyposquattingCheckerEnabled](/DeployEdge/microsoft-edge-policies#typosquattingcheckerenabled) - 配置 Edge TyposquattingChecker。

<!-- end major 96 --->

## <a name="version-950102038-october-28"></a>版本 95.0.1020.38：10 月 28 日

修复了各种 bug 和性能问题。

## <a name="version-950102020-october-11"></a>版本 95.0.1020.20：10 月 11 日

修复了各种 bug 和性能问题。

## <a name="version-950102014-october-5"></a>版本 95.0.1020.14：10 月 5 日

修复了各种 bug 和性能问题。

## <a name="version-95010209-september-28"></a>版本 95.0.1020.9：9 月 28 日

### <a name="feature-updates"></a>功能更新

- **在 Microsoft Edge 中查看对 SharePoint Online 库的文件资源管理器支持。**  现在，你可以为联机新式文档库启用"SharePoint资源管理器"功能。 若要使此体验可见且适用于你的用户，你需要启用 Microsoft Edge"在 Microsoft Edge 中为[SharePoint](/deployedge/microsoft-edge-policies#configureviewinfileexplorer)页面配置文件资源管理器中的查看功能"策略，并更新 SharePoint Online 租户配置。 了解更多信息：SharePoint文件资源管理器查看Microsoft Edge [- SharePoint Microsoft 365 |Microsoft Docs](/SharePoint/sharepoint-view-in-edge)。

- **Intranet 区域文件 URL 链接将在 Windows 文件资源管理器中打开。**  你可以允许文件 URL 链接到源自 Intranet 区域 HTTPS 网站的 Intranet 区域文件，以打开该文件或目录的 Windows 文件资源管理器。 可以使用 [IntranetFileLinksEnabled](/deployedge/microsoft-edge-policies#intranetfilelinksenabled) 策略启用此体验。

- **对下载体验进行的改进。**  对下载用户体验的支持正扩展到渐进式 Web 应用程序 PWA 和 WebView。 我们还将开始支持拖放到文件资源管理器和桌面。

- **继续你在 PDF 文件上的工作。**  可以从上次关闭 PDF 文档的位置继续阅读。

- **当笔记本电脑进入延长电池使用时间模式时，效率模式会延长延长电池寿命。**  当笔记本电脑进入电池保护模式时，效率模式将变得活跃，以允许浏览器管理资源使用状态来延长机器的电池寿命。 对于效率模式何时变为活动状态、拔掉电池和电量不足、已拔掉、始终和从不，你有四个选项。 注意：这是受控功能推出。 具有电池的设备应已打开该功能。

***新策略***

- [BrowserLegacyExtensionPointsBlockingEnabled](/DeployEdge/microsoft-edge-policies#browserlegacyextensionpointsblockingenabled) - 启用浏览器旧版扩展点阻止。
- [CrossOriginWebAssemblyModuleSharingEnabled](/DeployEdge/microsoft-edge-policies#crossoriginwebassemblymodulesharingenabled) - 指定是否可以跨源发送 WebAssembly 模块。
- [DisplayCapturePermissionsPolicyEnabled](/DeployEdge/microsoft-edge-policies#displaycapturepermissionspolicyenabled) - 指定是检查还是跳过显示捕获权限策略。
- [InternetExplorerIntegrationWindowOpenHeightAdjustment](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationwindowopenheightadjustment) - 配置来自 IE 模式页面与 Microsoft Edge 模式页面的 window.open 高度之间的像素调整。
- [InternetExplorerIntegrationWindowOpenWidthAdjustment](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationwindowopenheightadjustment) - 配置来自 IE 模式页面与 Microsoft Edge 模式页面的 window.open 宽度之间的像素调整。
- [IntranetFileLinksEnabled](/DeployEdge/microsoft-edge-policies#intranetfilelinksenabled) - 允许在文件资源管理器Microsoft Edge打开 Intranet 区域Windows URL 链接。
- [ShadowStackCrashRollbackBehavior](/DeployEdge/microsoft-edge-policies#shadowstackcrashrollbackbehavior) - 配置 ShadowStack 故障回滚行为。
- [VisualSearchEnabled](/DeployEdge/microsoft-edge-policies#visualsearchenabled) - 启用视觉搜索。

***已过时的策略***

- [InternetExplorerIntegrationTestingAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationtestingallowed) - 允许 Internet Explorer 模式测试。
- [LegacySameSiteCookieBehaviorEnabled](/DeployEdge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) - 启用默认旧式 SameSite Cookie 行为设置。

## <a name="version-94099223-september-17"></a>版本 94.0.992.23：9 月 17 日

修复了各种 bug 和性能问题。

## <a name="version-94099219-september-13"></a>版本 94.0.992.19：9 月 13 日

修复了各种 bug 和性能问题。

## <a name="version-94099214-september-7"></a>版本 94.0.992.14：9 月 7 日

修复了各种 bug 和性能问题。

## <a name="version-9409929-september-2"></a>版本 94.0.992.9：9 月 2 日

### <a name="feature-updates"></a>功能更新

- **Microsoft Edge Beta 和稳定渠道更新的节奏为 4 周。**  我们将对主要版本采用新的 4 周发布周期。 可以在此处阅读有关该决策的更多信息： https://blogs.windows.com/msedgedev/2021/03/12/new-release-cycles-microsoft-edge-extended-stable/

- **即将提供新的扩展稳定选项。**  我们将向托管企业客户提供新的扩展稳定选项。 扩展稳定选项将保留偶数编号修订版，并且每 8 周更新一次。 将提供每两周一次的安全更新。  请在此处查看其他信息：https://blogs.windows.com/msedgedev/2021/07/15/opt-in-extended-stable-release-cycle/

- **改进了打开 MHTML 文件的默认行为。**  如果启用了 IE 模式，则 MHTML 文件将继续在 IE 模式下打开，除非 MHTML 文件是从 Microsoft Edge 保存的（在 Microsoft Edge 中使用“另存为”或“页面另存为”选项）。 如果文件是从 Microsoft Edge 保存的，则它现在将在 Microsoft Edge 中打开。  此更改将修复在 IE 模式下打开从 Microsoft Edge 保存的 MHTML 文件时观察到的绘制问题。

- **限制专用网络请求以保护上下文。** 从 Internet 上的页面中访问本地 (Intranet) 网络上的资源需要通过 HTTPS 传递这些页面。 此更改发生在 Microsoft Edge 所基于的 Chromium 项目中。 有关详细信息，请导航到 [Chrome 平台状态条目](https://chromestatus.com/feature/5436853517811712)。 可使用两个兼容性策略支持需要保留与非安全页面的兼容性的方案：[InsecurePrivateNetworkRequestAllowed](/deployedge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed) 和 [InsecurePrivateNetworkRequestAllowedForUrls](/deployedge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls)。

- **阻止混合内容下载。** 安全页面将仅下载托管在其他安全页面上的文件，并且如果从安全页面启动，则将阻止托管在非安全（非 HTTPS）页面上的下载。 此更改发生在 Microsoft Edge 所基于的 Chromium 项目中。 有关详细信息，请导航到 [Google 安全博客条目](https://security.googleblog.com/2020/02/protecting-users-from-insecure_6.html)。

- **为本地帐户启用隐式登录。**   通过启用 OnlyOnPremisesImplicitSigninEnabled 策略，将仅启用本地帐户进行隐式登录。  Microsoft Edge 不会尝试隐式登录到 MSA 或 AAD 帐户。 从本地帐户升级到 AAD 帐户也将停止。

- **添加到 PDF 文档的自由格式文本框。**  我们现在支持将自由格式文本框添加到 PDF 文档，您可以使用这些文本框填充表单和添加可见便笺。

- **轻松更新密码。**  浏览器现在将你直接转到给定网站的"更改密码"页面，通过避免需要手动导航到该页面来节省时间和单击。 进入此页面后，浏览器还将自动填充现有密码，并建议一个唯一的强密码。  请注意：此功能当前在有限数量的网站上可用。  

- **新建辅助功能设置页。** 我们已将与辅助功能相关的设置组合在单个页面上。 可以在主设置列表下找到新的 edge://settings/accessibility 页面。 可在此处找到可放大网页和在焦点区域周围显示高可见性大纲的设置，以及有助于改善 Web 浏览体验的其他设置。 我们将继续在 Microsoft Edge 的未来版本中在此处添加新设置。

***新策略***

- [ApplicationGuardPassiveModeEnabled](/DeployEdge/microsoft-edge-policies#applicationguardpassivemodeenabled) 忽略应用程序防护网站列表配置并正常浏览 Edge
- [OnlyOnPremisesImplicitSigninEnabled](/DeployEdge/microsoft-edge-policies#onlyonpremisesimplicitsigninenabled) 仅启用了隐式登录的本地帐户
- [WebRtcRespectOsRoutingTableEnabled](/DeployEdge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) 在通过 WebRTC 建立对等连接时启用对 Windows OS 路由表规则的支持

***已过时的策略***

- [UserAgentClientHintsEnabled](/DeployEdge/microsoft-edge-policies#useragentclienthintsenabled) 启用 User-Agent 客户端提示功能

## <a name="version-93096133-august-27"></a>版本 93.0.961.33：8 月 27 日

修复了各种 bug 和性能问题。

## <a name="version-93096127-august-20"></a>版本 93.0.961.27：8 月 20 日

修复了各种 bug 和性能问题。

## <a name="version-93096124-august-18"></a>版本 93.0.961.24：8 月 18 日

修复了各种 bug 和性能问题。

## <a name="version-93096111-august-3"></a>版本 93.0.961.11：8 月 3 日

### <a name="feature-updates"></a>功能更新

- **Microsoft Edge 中的初始首选项。**  从 Microsoft Edge版本 93 开始，Microsoft Edge初始首选项 将更容易[部署到企业](/deployedge/initial-preferences-support-on-microsoft-edge-browser)。

- **Microsoft Edge 上的 IE 模式将支持“无合并”行为。**  从 Microsoft Edge版本 93 开始，Microsoft Edge上的 IE 模式将支持"无合并"。 对于最终用户，当从 IE 模式应用程序启动新的浏览器窗口时，它将位于单独的会话中，类似于 IE11 中的行为。 你将需要调整站点列表，以配置需要阻止会话共享的站点。 在后台，对于每个 Microsoft Edge 窗口，当首次在该窗口中访问 IE 模式选项卡时，如果其为其中一个指定的“无合并”站点，则该窗口至少会锁定到所有其他Microsoft Edge 窗口的不同“无合并”IE 会话中，直到最后的 IE 模式选项卡在该窗口中关闭。 请在[此处](/deployedge/edge-ie-mode-faq#does-ie-mode-on-microsoft-edge-support-the--no-merge--option-that-was-supported-in-internet-explorer-11-)了解详细信息。

- **选项卡组。**  将选项卡分类到用户定义的组的功能可帮助您更有效地跨多个工作流查找、切换和管理选项卡。 为了启用此功能，我们将从版本 93 开始启用选项卡Microsoft Edge分组。

- **使用“垂直标签”时隐藏标题栏。**  当在“垂直标签”中时，隐藏浏览器的标题栏以重获额外多个像素。 从 Microsoft Edge版本 93 开始，可以转到 edge://settings/appearance，在"自定义工具栏"部分下，选择在垂直选项卡模式下隐藏标题栏的选项。

- **悬停工具栏中的视频画中画(PiP)。**  从 Microsoft Edge版本 93 开始，在 PiP 模式的图片 (输入图片) 变得更加简单。 当将鼠标悬停在受支持的视频上时，工具栏将显示，允许在 PiP 窗口中查看该视频。  注意：这目前适用于 macOS Microsoft Edge用户。  在我们向用户继续推出时，请Windows检查。

- **在 TLS 中删除 3DES。**  从 Microsoft Edge版本 93 开始，将TLS_RSA_WITH_3DES_EDE_CBC_SHA密码套件的支持。 此更改发生在 Microsoft Edge 基于的 Chromium 项目中。 有关详细信息，请导航到 [Chrome 平台状态条目](https://chromestatus.com/feature/6678134168485888)。 此外，在 Microsoft Edge 版本 93 中，[TripleDESEnabled](/deployedge/microsoft-edge-policies#tripledesenabled) 策略将可用于支持需要保留与过时服务器的兼容性的场景。 此兼容性策略将过时，并停止在 Microsoft Edge 版本 95 中工作。 请确保在此之前更新受影响的服务器。

- **用于绕过 ClickOnce 和 DirectInvoke 提示的策略。**  我们更新了策略，以允许绕过来自指定域的指定文件类型的 ClickOnce 提示和 DirectInvoke 应用。 为此，需要:

  - 启用 [ClickOnceEnabled](/deployedge/microsoft-edge-policies#clickonceenabled) 或 [DirectInvokeEnabled](/deployedge/microsoft-edge-policies#directinvokeenabled)
  - 启用 [AutoOpenFileTypes](/deployedge/microsoft-edge-policies#autoopenfiletypes) 策略，并设置应禁用 ClickOnce 和 DirectInvoke 的特定文件类型的列表
  - 启用[AutoOpenAllowedForURLs](/deployedge/microsoft-edge-policies#autoopenallowedforurls)策略并设置特定域的列表，ClickOnce和 DirectInvoke 将被禁用

  注意: AutoOpenAllowedForURL 为 AutoOpenFileTypes 的策略。 如果未设置 AutoOpenAllowedForURL 但设置了 AutoOpenFileTypes，则列出的文件类型将从所有 URL 中自动打开。

### <a name="new-policies"></a>新策略

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

#### <a name="deprecated-policy"></a>已弃用的策略

- [LegacySameSiteCookieBehaviorEnabled](/DeployEdge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) 启用默认的旧 SameSite Cookie 行为设置

#### <a name="obsoleted-policy"></a>已过时的策略

- [NewTabPageSetFeedType](/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype) 配置 Microsoft Edge 新选项卡页面体验

#### <a name="additional-change"></a>其他更改

- [ConfigureShare](/DeployEdge/microsoft-edge-policies#configureshare) 添加 mac 平台支持

## <a name="version-93096118-august-10"></a>版本 93.0.961.18：8 月 10 日

修复了各种 bug 和性能问题。

## <a name="version-92090262-july-29"></a>版本 92.0.902.62：6 月 29 日

修复了各种 bug 和性能问题。

## <a name="version-92090255-july-21"></a>版本 92.0.902.55：7 月 21 日

修复了各种 bug 和性能问题。

## <a name="version-92090245-july-12"></a>版本 92.0.902.45：7 月 12 日

修复了各种 bug 和性能问题。

## <a name="version-92090240-july-6"></a>版本 92.0.902.40：7 月 6 日

修复了各种 bug 和性能问题。

<!--Archive on Oct 27 From Version 92.0.902.22: June 21 to Version 89.0.774.23: February 8  -->
<!--- Archived from Version 87.0.664.18: October 26 to to version 89.0.774.18: February 3 ---->
<!--- Archived from Version 87.0.664.12: October 20 to to version 86.0.622.15: September 14 ---->
<!--- Archived to version 86.0.622.11: September 9 ---->
<!--- Archived to version 85.0.564.18: July 28 ---->

## <a name="see-also"></a>另请参阅

- [Microsoft Edge 企业版登录页面](https://aka.ms/EdgeEnterprise)
