---
title: Microsoft Edge Beta 渠道发行说明
ms.author: aguta
author: AndreaLBarr
manager: srugh
ms.date: 08/31/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge Beta 渠道发行说明
ms.openlocfilehash: 1fad7c52819ce5ca6516d400ea00151a54bc66e7
ms.sourcegitcommit: 822db9d312a13a13928ff1c10c2b35b6b46598fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2021
ms.locfileid: "11934622"
---
# <a name="release-notes-for-microsoft-edge-beta-channel"></a>Microsoft Edge Beta 渠道的发行说明

本发行说明提供有关 Microsoft Edge Beta 渠道中包含的新功能和非安全更新的信息。 [此处](microsoft-edge-relnote-archive-beta-channel.md)提供了这些发行说明的存档版本。

> [!NOTE]
> Microsoft Edge Web 平台不断发展以改进用户体验、安全性和隐私。 要了解详细信息，请参阅 [Microsoft Edge 中影响网站兼容性的更改](/microsoft-edge/web-platform/site-impacting-changes)。

## <a name="version-93096133-august-27"></a>版本 93.0.961.33：8 月 27 日

修复了各种错误和性能问题。

## <a name="version-93096127-august-20"></a>版本 93.0.961.27：8 月 20 日

修复了各种错误和性能问题。

## <a name="version-93096124-august-18"></a>版本 93.0.961.24：8 月 18 日

修复了各种错误和性能问题。

## <a name="version-93096111-august-3"></a>版本 93.0.961.11：8 月 3 日

### <a name="feature-updates"></a>功能更新

- **中的初始Microsoft Edge。**  从 Microsoft Edge版本 93 开始，Microsoft Edge初始首选项将更容易部署到企业。

- **IE 模式Microsoft Edge"不合并"行为。**  从 Microsoft Edge版本 93 开始，Microsoft Edge上的 IE 模式将支持"无合并"。 对于最终用户，当从 IE 模式应用程序启动新的浏览器窗口时，它将位于单独的会话中，类似于 IE11 中的行为。 你将需要调整站点列表，以配置需要阻止会话共享的站点。 在后台，对于 Microsoft Edge 的每个窗口，首次访问该窗口中的 IE 模式选项卡（如果它是指定的"不合并"站点之一）时，该窗口至少会锁定到与所有其他 Microsoft Edge 窗口不同的"不合并"IE 会话，直到关闭该窗口中的最后一个 IE 模式选项卡。 请在[此处](/deployedge/edge-ie-mode-faq#does-ie-mode-on-microsoft-edge-support-the--no-merge--option-that-was-supported-in-internet-explorer-11-)了解详细信息。

- **选项卡组。**  将选项卡分类到用户定义的组的功能可帮助您更有效地跨多个工作流查找、切换和管理选项卡。 若要启用此功能，我们将从版本 93 开始启用选项卡Microsoft Edge分组。

- **使用垂直选项卡时隐藏标题栏。**  通过隐藏浏览器的标题栏（同时在垂直选项卡中）获取额外几个像素。 从 Microsoft Edge版本 93 开始，可以转到 edge://settings/appearance，在"自定义工具栏"部分下，选择在垂直选项卡模式下隐藏标题栏的选项。

- **从悬停工具栏 (PiP) 图片。**  从 Microsoft Edge版本 93 开始，在 PiP 模式的图片 (输入图片) 变得更加简单。 将鼠标悬停在受支持的视频上时，将显示一个工具栏，允许您在 PiP 窗口中查看该视频。  注意：这当前适用于 macOS Microsoft Edge用户。  在我们向用户继续推出时，请Windows检查。

- **在 TLS 中删除 3DES。**  从 Microsoft Edge版本 93 开始，将TLS_RSA_WITH_3DES_EDE_CBC_SHA密码套件的支持。 此更改发生在Chromium项目上，Microsoft Edge项目。 有关详细信息，请导航到 [Chrome 平台状态条目](https://chromestatus.com/feature/6678134168485888)。 此外，Microsoft Edge 93 版本中[，TripleDESEnabled](/deployedge/microsoft-edge-policies#tripledesenabled)策略可用于支持需要保留与过时服务器的兼容性的方案。 此兼容性策略将过时，在版本 95 Microsoft Edge停止工作。 请确保在更新之前更新受影响的服务器。

- **绕过 directInvoke ClickOnce和 DirectInvoke 提示的策略。**  我们已更新我们的策略，以允许从ClickOnce域中绕过对指定文件类型的提示和 DirectInvoke 应用。 为此，你需要：

  - 启用 [ClickOnceEnabled](/deployedge/microsoft-edge-policies#clickonceenabled) 或 [DirectInvokeEnabled](/deployedge/microsoft-edge-policies#directinvokeenabled)
  - 启用[AutoOpenFileTypes](/deployedge/microsoft-edge-policies#autoopenfiletypes)策略并设置应禁用 ClickOnce DirectInvoke 的特定文件类型的列表
  - 启用[AutoOpenAllowedForURLs](/deployedge/microsoft-edge-policies#autoopenallowedforurls)策略并设置特定域的列表，ClickOnce和 DirectInvoke 将被禁用

  注意：AutoOpenAllowedForURLs 是 AutoOpenFileTypes 的一个策略。 如果未设置 AutoOpenAllowedForURLs 并且设置了 AutoOpenFileTypes，则列出的文件类型将自动从所有 URL 打开。

### <a name="new-policies"></a>新策略

- [AutoplayAllowlist](/DeployEdge/microsoft-edge-policies#autoplayallowlist) 允许媒体自动播放特定网站
- [CECPQ2Enabled](/DeployEdge/microsoft-edge-policies#cecpq2enabled) 为 TLS 启用的 CECPQ2 后量子密钥协议
- [ConfigureViewInFileExplorer](/DeployEdge/microsoft-edge-policies#configureviewinfileexplorer)为文件资源管理器中的"文件资源管理器"SharePoint"视图Microsoft Edge
- [DefaultJavaScriptJitSetting](/DeployEdge/microsoft-edge-policies#defaultjavascriptjitsetting) 控制 JavaScript JIT 的使用
- [ShowPDFDefaultRecommendationsEnabled](/DeployEdge/microsoft-edge-policies#showpdfdefaultrecommendationsenabled)允许通知将 Microsoft Edge设置为默认 PDF 阅读器
- [FeatureFlagOverridesControl](/DeployEdge/microsoft-edge-policies#featureflagoverridescontrol) 配置用户重写功能标志的能力
- [ImplicitSignInEnabled](/DeployEdge/microsoft-edge-policies#implicitsigninenabled) 启用隐式登录
- [InternetExplorerIntegrationCloudSiteList](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationcloudsitelist)配置Enterprise云站点列表
- [InternetExplorerIntegrationSiteListRefreshInterval](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationsitelistrefreshinterval)配置刷新Enterprise站点列表的频率
- [JavaScriptJitAllowedForSites](/DeployEdge/microsoft-edge-policies#javascriptjitallowedforsites) 允许 JavaScript 在这些网站上使用 JIT
- [JavaScriptJitBlockedForSites](/DeployEdge/microsoft-edge-policies#javascriptjitblockedforsites) 阻止 JavaScript 在这些网站上使用 JIT
- [LocalBrowserDataShareEnabled](/DeployEdge/microsoft-edge-policies#localbrowserdatashareenabled)启用Windows搜索本地搜索Microsoft Edge数据
- [MAUEnabled](/DeployEdge/microsoft-edge-policies#mauenabled)始终使用 Microsoft AutoUpdate 作为更新程序进行Microsoft Edge
- [MSAWebSiteSSOUsingThisProfileAllowed](/DeployEdge/microsoft-edge-policies#msawebsitessousingthisprofileallowed) 允许使用此配置文件的单一登录 Microsoft 网站
- [OneAuthAuthenticationEnforced](/DeployEdge/microsoft-edge-policies#oneauthauthenticationenforced)强制登录Flow OneAuth 身份验证
- [PasswordGeneratorEnabled](/DeployEdge/microsoft-edge-policies#passwordgeneratorenabled) 允许用户在联机创建帐户时获取强密码建议
- [PrimaryPasswordSetting](/DeployEdge/microsoft-edge-policies#primarypasswordsetting) 配置要求用户在使用密码自动填充时输入其设备密码的设置
- [PrintingWebpageLayout](/DeployEdge/microsoft-edge-policies#printingwebpagelayout) 设置打印的布局
- [RemoteDebuggingAllowed](/DeployEdge/microsoft-edge-policies#remotedebuggingallowed) 允许远程调试
- [RelaunchWindow](/DeployEdge/microsoft-edge-policies#relaunchwindow) 设置重新启动的时间间隔
- [TravelAssistanceEnabled](/DeployEdge/microsoft-edge-policies#travelassistanceenabled) 启用旅行协助
- [TripleDESEnabled](/DeployEdge/microsoft-edge-policies#tripledesenabled) 在 TLS 中启用 3DES 密码套件

#### <a name="deprecated-policy"></a>不推荐使用的策略

- [LegacySameSiteCookieBehaviorEnabled](/DeployEdge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) 启用默认的旧 SameSite Cookie 行为设置

#### <a name="obsoleted-policy"></a>已过时的策略

- [NewTabPageSetFeedType](/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype)配置Microsoft Edge选项卡页体验

#### <a name="additional-change"></a>其他更改

- [ConfigureShare](/DeployEdge/microsoft-edge-policies#configureshare) 添加 mac 平台支持

## <a name="version-93096118-august-10"></a>版本 93.0.961.18：8 月 10 日

修复了各种错误和性能问题。

## <a name="version-92090262-july-29"></a>版本 92.0.902.62：6 月 29 日

修复了各种错误和性能问题。

## <a name="version-92090255-july-21"></a>版本 92.0.902.55：7 月 21 日

修复了各种错误和性能问题。

## <a name="version-92090245-july-12"></a>版本 92.0.902.45：7 月 12 日

修复了各种错误和性能问题。

## <a name="version-92090240-july-6"></a>版本 92.0.902.40：7 月 6 日

修复了各种错误和性能问题。

## <a name="version-92090222-june-21"></a>版本 92.0.902.22：6 月 21 日

### <a name="feature-updates"></a>功能更新

- **地址栏上的浏览器历史记录的自然语言搜索**。 借助地址栏中的自然语言搜索，现在可以更轻松地查找要查找的文章/网站。 除了标题/URL 关键字匹配之外，您还可以根据页面内容/说明/ (搜索结果，例如"上个星期的食谱") "。
请注意：这是限制性的功能推出。 如果看不到此功能，请在我们继续推出时再检查。

- **用户可以轻松地在 Microsoft Edge 上进入 Internet Explorer 模式**。 从 Microsoft Edge 版本 92 开始，用户可以在 Microsoft Edge 上以 Internet Explorer 模式重新加载站点，而不是等待站点在 Enterprise 模式站点列表中被配置的同时依赖独立 IE 11 应用程序。 系统将提示用户将网站添加到其本地站点列表，以便在 Microsoft Edge 中导航到的相同页面将在接下来 30 天内自动以 IE 模式呈现。 可以使用 *[InternetExplorerIntegrationReloadInIEModeAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed)* 策略配置此体验，并允许访问 IE 模式入口点，以及允许将站点添加到本地站点列表。 可以使用 *[InternetExplorerIntegrationLocalSiteListExpirationDays](/deployedge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays)* 策略调整将网站保留在本地站点列表中的天数。
请注意，对于端到端体验，Windows 10 版本 1909 需要 KB5003698 或更高版本; Windows 10 版本 2004、Windows 10 版本 20H2 或 Windows 10 版本 21H1 需要 KB5003690 或更高版本。

- **MHTML 文件将默认以 Internet Explorer 模式打开**。 从 Microsoft Edge 92 稳定版开始，MHTML 文件类型将在 Microsoft Edge 上以 Internet Explorer 模式自动打开，而不是在 Internet Explorer (IE11) 打开。 在用浏览器查看 Outlook 电子邮件时会经常遇到这种情况。 此更改仅在 IE11 是此文件类型的默认处理程序时发生。 如果想要更改此设置，可以在安装稳定版本 92 更新之前使用 [本指南](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)。

- **付款工具现在跨设备同步**。 从 Microsoft Edge 版本 92 开始，可以选择跨已登录设备同步付款信息。
请注意：这是限制性的功能推出。 如果看不到此功能，请在我们继续推出时尽快查看。

- **“禁用开发人员模式扩展”警告可以永久消除**。 从 Microsoft Edge 版本 92 开始，可以通过单击"不要再次显示此扩展"选项来关闭"禁用开发人员模式扩展"警告。
请注意：这是限制性的功能推出。 如果看不到此功能，请在我们继续推出时尽快查看。

- **直接从工具栏管理扩展**。 工具栏上新增的扩展菜单将允许你轻松隐藏/固定扩展。 管理扩展和查找新扩展的快速链接将使你轻松找到新扩展和管理现有扩展。
请注意：这是限制性的功能推出。 如果看不到此功能，请在我们继续推出时尽快查看。

- **自动 HTTPS**。 用户可以选择在可能支持此更安全协议的域上将导航从 HTTP 升级到 HTTPS。 此支持还可以配置为在所有域上尝试 HTTPS 传输。
请注意：我们正在试验此功能，如果你已选择退出实验，则将不会看到此行为。

- **字体呈现的改进**。 改进了文本呈现，以提高清晰度并降低模糊度。
请注意：这是限制性的功能推出。 如果看不到此功能，请在我们继续推出时尽快查看。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

添加了 8 个新策略。 从 [Microsoft Edge 企业版登录页面](https://www.microsoft.com/edge/business/download) 下载更新的管理模板。 添加了以下新策略：

- [AADWebSiteSSOUsingThisProfileEnabled](/DeployEdge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) 启用通过此配置文件对工作或学校网站进行单一登录。
- [AutomaticHttpsDefault](/DeployEdge/microsoft-edge-policies#automatichttpsdefault) 配置自动 HTTPS
- [HeadlessModeEnabled](/DeployEdge/microsoft-edge-policies#headlessmodeenabled) 控制无头模式的使用
- [InsecurePrivateNetworkRequestsAllowed](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed)指定是否允许不安全网站向更专用的网络终结点提出请求
- [InsecurePrivateNetworkRequestsAllowedForUrls](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls) 允许列出的站点从不安全环境向更专用的网络终结点提出请求
- [InternetExplorerIntegrationLocalSiteListExpirationDays](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) 指定站点在本地 IE 模式站点列表中保留的天数
- [InternetExplorerIntegrationReloadInIEModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) 允许以 Internet Explorer 模式重新加载未配置的网站
- [SharedArrayBufferUnrestrictedAccessAllowed](/DeployEdge/microsoft-edge-policies#sharedarraybufferunrestrictedaccessallowed) 指定是否可以在非跨源隔离环境中使用 SharedArrayBuffers

#### <a name="obsoleted-policy"></a>已过时的策略

- [EnableSha1ForLocalAnchors](/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors) 允许使用本地信任锚点颁发的 SHA-1 签名的证书。

## <a name="version-9209029-june-8"></a>版本 92.0.902.9：6 月 8 日

修复了各种 bug 和性能问题。

## <a name="version-91086441-june-3"></a>版本 91.0.864.41：6 月 3 日

修复了各种 bug 和性能问题。

## <a name="version-91086437-may-27"></a>版本 91.0.864.37：5 月 27 日

修复了各种 bug 和性能问题。

## <a name="version-91086436-may-26"></a>版本 91.0.864.36：5 月 26 日

修复了各种 bug 和性能问题。

## <a name="version-91086433-may-21"></a>版本 91.0.864.33：5 月 21 日

修复了各种 bug 和性能问题。

## <a name="version-91086427-may-14"></a>版本 91.0.864.27：5 月 14 日

修复了各种 bug 和性能问题。

## <a name="version-91086419-may-7"></a>版本 91.0.864.19：5 月 7 日

修复了各种 bug 和性能问题。

## <a name="version-91086415-may-3"></a>版本 91.0.864.15：5 月 3 日

修复了各种 bug 和性能问题。

## <a name="version-91086411-april-30"></a>版本 91.0.864.11：4 月 30 日

### <a name="feature-updates"></a>功能更新

- **标识源自代理级别的 Microsoft Defender 应用程序防护容器的网络流量**。 从 Microsoft Edge 版本 91 开始，内置了对源自应用程序防护容器的网络流量进行标记的支持，允许企业识别这些流量并应用特定策略。

- **支持允许将收藏夹从主机同步到边缘应用程序防护容器的选项**。 从 Microsoft Edge 版本 91 开始，用户可以选择配置应用程序防护以将其收藏夹从主机同步到容器。 这确保了容器上也可显示新的收藏夹。

- **支持语音识别 API。** 从 Microsoft Edge 版本 91 开始，将添加对 Google.com 和类似网站上语音识别命令的 API 支持。 此功能仅限于一组启用了实验的随机选择的用户。 这些用户向功能团队提供反馈。

- **使用新的主题颜色个性化设置浏览器**。 使用“设置”->“外观”页上的十四种新主题颜色之一打造你自己的 Microsoft Edge。 也可以从 Microsoft Edge 加载项网站安装自定义主题。 [了解详细信息](https://techcommunity.microsoft.com/t5/articles/make-microsoft-edge-your-own-with-themes/m-p/2083165)

- **中断下载** 从 Microsoft Edge 版本 91 开始，如果在未经用户交互的情况下启动对计算机有害的下载，并且 SmartScreen 应用程序信誉检查不支持此下载，则浏览器将自动中断该类型的下载。 用户可能会覆盖并继续下载，方法是右键单击并在下载项上选择“保留”。
企业管理员可以通过以下两个策略之一选择退出此行为：
    - [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - 对域上的指定文件类型禁用基于文件类型扩展名的下载警告。有关详细信息，请参阅 [Microsoft Edge 安全下载中断](/deployedge/microsoft-edge-security-downloads-interruptions)

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

- [ProactiveAuthEnabled](./microsoft-edge-policies.md#proactiveauthenabled) - 启用主动身份验证。
<!-- end major 91 -->

## <a name="version-90081846-april-22"></a>版本 90.0.818.46：4 月 22 日

修复了各种 bug 和性能问题。

## <a name="version-90081842-april-20"></a>版本 90.0.818.42：4 月 20 日

修复了各种 bug 和性能问题。

## <a name="version-90081841-april-16"></a>版本 90.0.818.41：4 月 16 日

修复了各种 bug 和性能问题。

## <a name="version-90081838-april-14"></a>版本 90.0.818.38：4 月 14 日

修复了各种 bug 和性能问题。

## <a name="version-90081836-april-12"></a>版本 90.0.818.36：4 月 12 日

修复了各种 bug 和性能问题。

## <a name="version-90081827-april-2"></a>版本 90.0.818.27：4 月 2 日

修复了各种 bug 和性能问题。

## <a name="version-90081822-march-29"></a>版本 90.0.818.22：3 月 29 日

修复了各种 bug 和性能问题。

## <a name="version-90081814-march-22"></a>版本 90.0.818.14：3 月 22 日

修复了各种 bug 和性能问题。
<!-- begin major 90 -->
## <a name="version-9008188-march-16"></a>版本 90.0.818.8：3 月 16 日

### <a name="feature-updates"></a>功能更新

- **SSO（单一登录）现已适用于 macOS 上的Azure Active Directory (Azure AD) 帐户和 Microsoft 帐户 (MSA)**。 现在，已在 macOS 上登录 Microsoft Edge 的用户将自动登录到配置为允许使用工作帐户和 Microsoft 帐户进行单一登录的网站（如 bing.com、office.com、msn.com 和 outlook.com）。

- **展台模式。** 从 Microsoft Edge 版本 90 开始，我们已锁定 UI 打印设置，以仅允许配置的打印机和“打印到 PDF”选项。 我们还在分配的访问权限单应用展台模式中进行了改进，以限制从浏览器启动其他应用程序。 有关展台模式功能的详细信息，请转到 [此处](/deployedge/microsoft-edge-configure-kiosk-mode#kiosk-mode-supported-features)。

- **打印：**

  - **非 PostScript 打印机的全新打印光栅化模式**。 从 Microsoft Edge 版本 90 开始，管理员可以使用新策略为用户定义打印光栅化模式。 此策略控制 Microsoft Edge 如何在 Windows 上打印到非 PostScript 打印机。  有时，在非 PostScript 打印机上的打印作业需要进行光栅化才能正确打印。 打印选项为“完整”和“快速”。

  - **打印的其他页面缩放选项**。 用户现在可在使用其他选项打印网页和 PDF 文档时自定义缩放。 “适应页面”选项可确保网页或文档适合所选“纸张大小”中可用于打印的空间。 “实际大小”选项可确保无论所选“纸张大小”如何，正在打印内容的大小都没有任何变化。

- **工作效率：**

  - **自动填充建议扩展为包含剪贴板中的地址字段内容**。 在单击配置文件/地址字段（例如，电话、电子邮件、邮政编码、城市、省/市/县等）将分析剪贴板内容，以显示为自动填充建议。

  - **即使未检测到表单或字段，用户也可以搜索自动填充建议**。 现在，如果将信息保存在 Microsoft Edge 上，将自动弹出自动填充建议，并帮助你在填写表单时节省时间。 如果自动填充遗漏了表单，或者希望获取通常没有自动填充的表单（如 临时表单）的数据，可以使用自动填充来搜索信息。

- **从菜单栏中的浮出控件访问下载**。 下载将显示在右上角，且所有活动下载都位于同一位置。 此菜单很容易消除，以便用户可以继续不间断地浏览，并且可以从工具栏直接监视总体下载进度。 [了解详细信息](https://techcommunity.microsoft.com/t5/articles/introducing-the-new-downloads-experience/m-p/2111551)。


### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

添加了 7 个新策略。 从 [Microsoft Edge 企业版登录页面](https://www.microsoft.com/edge/business/download) 下载更新的管理模板。 添加了以下新策略：

- [ApplicationGuardFavoritesSyncEnabled](./microsoft-edge-policies.md#applicationguardfavoritessyncenabled) - 已启用应用程序防护收藏夹同步
- [ManagedConfigurationPerOrigin](./microsoft-edge-policies.md#managedconfigurationperorigin) - 将网站的托管配置值设置到特定源
- [PrintRasterizationMode](./microsoft-edge-policies.md#printrasterizationmode) - 打印光栅化模式
- [QuickViewOfficeFilesEnabled](./microsoft-edge-policies.md#quickviewofficefilesenabled) - 在 Microsoft Edge 中管理 QuickView Office 文件功能
- [SSLErrorOverrideAllowedForOrigins](./microsoft-edge-policies.md#sslerroroverrideallowedfororigins) - 允许用户从特定源的 HTTPS 警告页面继续操作
- [WindowOcclusionEnabled](./microsoft-edge-policies.md#windowocclusionenabled) - 启用窗口封闭
- [WindowsHelloForHTTPAuthEnabled](./microsoft-edge-policies.md#windowshelloforhttpauthenabled) - 已启用 Windows Hello HTTP 身份验证

#### <a name="deprecated-policies"></a>已弃用的策略

- [NativeWindowOcclusionEnabled](./microsoft-edge-policies.md#nativewindowocclusionenabled) - 启用本机窗口封闭
- [SSLVersionMin](./microsoft-edge-policies.md#sslversionmin)- 已启用最低 TLS 版本
<!-- end major 90 -->

## <a name="version-89077454-march-13"></a>版本 89.0.774.54：3 月 13 日

修复了各种 bug 和性能问题。

## <a name="version-89077450-march-10"></a>版本 89.0.774.50：3 月 10 日

修复了各种错误和性能问题。

## <a name="version-89077448-march-8"></a>版本 89.0.774.48：3 月 8 日

修复了各种错误和性能问题。

## <a name="version-89077445-march-3"></a>版本 89.0.774.45：3 月 3 日

修复了各种错误和性能问题。

## <a name="version-89077439-february-26"></a>版本 89.0.774.39：2 月 26 日

修复了各种错误和性能问题。

## <a name="version-89077434-february-22"></a>版本 89.0.774.34：2 月 22 日

修复了各种错误和性能问题。

## <a name="version-89077427-february-12"></a>版本 89.0.774.27：2 月 12 日

修复了各种错误和性能问题。

## <a name="version-89077423-february-8"></a>版本 89.0.774.23：2 月 8 日

修复了各种 bug 和性能问题。

<!-- begin major 89 -->

<!--- Archived from Version 87.0.664.18: October 26 to to version 89.0.774.18: February 3 ---->
<!--- Archived from Version 87.0.664.12: October 20 to to version 86.0.622.15: September 14 ---->
<!--- Archived to version 86.0.622.11: September 9 ---->
<!--- Archived to version 85.0.564.18: July 28 ---->

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
