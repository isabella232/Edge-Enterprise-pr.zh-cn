---
title: Microsoft Edge Beta 渠道的存档发行说明
ms.author: aguta
author: AndreaLBarr
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge Beta 渠道的存档发行说明
ms.openlocfilehash: 065c665892edc264e2ab94375bedf3af9dbc936c
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "11978671"
---
# <a name="archived-release-notes-for-microsoft-edge-beta-channel"></a>Microsoft Edge Beta 渠道的存档发行说明

本发行说明提供有关 Microsoft Edge Beta 渠道中包含的新功能和非安全更新的信息。 若要了解 Microsoft Edge 渠道，请参阅 [Microsoft Edge 渠道概述](microsoft-edge-channels.md)。 [此处](microsoft-edge-relnotes-security.md)列出所有安全更新。
## <a name="version-89077418-february-3"></a>版本 89.0.774.18：2 月 3 日

### <a name="feature-updates"></a>功能更新

- **展台模式支持其他锁定功能**。 从 Microsoft Edge 版本 89 开始，我们在展台模式下添加了其他锁定功能，使客户能够在高效和更安全的体验中完成工作。 [了解详细信息](microsoft-edge-configure-kiosk-mode.md#kiosk-mode-supported-features)。

- **Enterprise Mode Site List Manager 工具将在浏览器中通过 *edge://compat* 页提供**。 可以使用此工具在 Microsoft Edge 上为 Internet Explorer 模式创建、编辑和导出站点列表 XML。 可以根据需要通过组策略启用对此工具的访问。 [了解详情](./edge-ie-mode-site-list-manager.md)。

- **使用休眠选项卡提高浏览器性能**。 休眠选项卡通过将非活动选项卡置于睡眠状态以释放系统资源（如内存和 CPU）来提升浏览器性能，以便活动选项卡或其他应用程序可以使用它们。 用户可以阻止网站进入睡眠状态，并配置非活动选项卡进入睡眠状态之前的时间长度。 若要使用户保持其流，还有一些[启发性方法](https://techcommunity.microsoft.com/t5/articles/sleeping-tabs-faq/m-p/1705434)可阻止某些网站进入睡眠状态，例如 Intranet 网站。 可以使用组策略管理此功能。

  > [!NOTE]
  > “使用休眠选项卡提高浏览器性能”是 2 月 3 日主要版本 89.0.774.18 发行说明的更新。

- **手动重置云中的 Microsoft Edge 同步数据**。 我们正在引入一种从产品内重置 Microsoft Edge 同步数据的方法。 这确保从 Microsoft 服务中清除数据，同时也解决了以前需要支持票证的某些产品问题。

- **PDF 文档中文本选择体验的改善**。 从版本 89 开始，用户将开始在 Microsoft Edge 中打开的 PDF 文档中获得更流畅、一致的文本选择体验。

- **自动填充字段现在支持"出生日期"**。 现在，Microsoft Edge 通过自动填充地址、姓名、电话号码等数据，帮助你在线填写表单和创建帐户时节省时间和精力。从 Microsoft Edge 版本 89 开始，我们将添加对另一可保存及自动填充字段的支持—出生日期。 可以随时在个人资料设置中查看、编辑和删除此信息。

- **支持在地址栏、历史记录搜索页面和历史记录中心上进行自然语言搜索**。 从 Microsoft Edge 版本 89 开始，使用地址栏、历史页面和历史中心上的自然语言搜索使查找文章/网站更容易。 除了标题/URL 关键字匹配之外，用户还可以搜索以前查看过的页面内容/描述/时间（例如“上周的蛋糕食谱”）。 此功能仅限于一组启用了实验的随机选择的用户。 这些用户向功能团队提供反馈。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

- [BrowsingDataLifetime](./microsoft-edge-policies.md#browsingdatalifetime) - 浏览数据生存期设置
- [MAMEnabled](./microsoft-edge-policies.md#mamenabled) - 移动应用管理已启用
- [DefinePreferredLanguages](./microsoft-edge-policies.md#definepreferredlanguages) - 定义网站应在网站支持该语言时显示的首选语言的有序列表
- [ShowRecommendationsEnabled](./microsoft-edge-policies.md#showrecommendationsenabled) - 允许来自 Microsoft Edge 的建议和促销通知
- [PrintingAllowedBackgroundGraphicsModes](./microsoft-edge-policies.md#printingallowedbackgroundgraphicsmodes) - 限制背景图形打印模式
- [PrintingBackgroundGraphicsDefault](./microsoft-edge-policies.md#printingbackgroundgraphicsdefault)- 默认背景图形打印模式
- [SmartActionsBlockList](./microsoft-edge-policies.md#smartactionsblocklist)- 阻止对服务列表执行智能操作

#### <a name="obsoleted-policies"></a>已过时的策略

- [ForceLegacyDefaultReferrerPolicy](./microsoft-edge-policies.md#forcelegacydefaultreferrerpolicy) - 使用 no-referrer-when-downgrade 的默认引荐策略
- [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled)：启用使用情况和故障相关数据报告
- [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices)：发送站点信息以改进 Microsoft 服务
<!-- end major 89 -->

## <a name="version-88070556-january-29"></a>版本 88.0.705.56：1 月 29 日

修复了各种 bug 和性能问题。

## <a name="version-88070549-january-20"></a>版本 88.0.705.49：1 月 20 日

修复了各种 bug 和性能问题。

## <a name="version-88070545-january-15"></a>版本 88.0.705.45：1 月 15 日

修复了各种 bug 和性能问题。

## <a name="version-88070541-january-11"></a>版本 88.0.705.41：1 月 11 日

修复了各种 bug 和性能问题。

## <a name="version-88070529-december-21"></a>版本 88.0.705.29：12 月 21 日

修复了各种 bug 和性能问题。

<!-- begin major 88 -->
## <a name="version-88070518-december-9"></a>版本 88.0.705.18：12 月 9 日

### <a name="feature-updates"></a>功能更新

- **弃用：**

  - 弃用对 FTP 协议的支持。 已从 Microsoft Edge 中删除对旧版 FTP 协议的支持。 尝试导航到 FTP 链接将导致浏览器指示操作系统打开外部应用程序以处理 FTP 链接。 或者，IT 管理员可以将 Microsoft Edge 配置为对依赖于 FTP 协议的站点使用 IE 模式。
  - Adobe Flash 支持将被删除。 从 Microsoft Edge Beta 版本 88 开始，Adobe Flash 功能和支持将被删除。 了解更多信息 [：Adobe Flash Player 停止支持更新 - Microsoft Edge 博客 (windows.com) ](https://blogs.windows.com/msedgedev/2020/09/04/update-adobe-flash-end-support/)

- **身份验证：**

  - 单一登录 (SSO) 现在适用于 macOS 和低级别 Windows 上的 Azure Active Directory (Azure AD) 帐户和 Microsoft 帐户 (MSA)。 在 macOS 或低级别 Microsoft Windows (7、8.1) 上登录 Microsoft Edge 的用户现在将自动登录到配置为允许使用工作帐户和 Microsoft 帐户单一登录的网站 (例如 bing.com、office.com、msn.com、outlook.com)。<br>注意：如果用户在 Microsoft Edge 88 之前的版本中登录 Microsoft Edge，可能需要注销然后重新登录，以利用此功能。
  - 自动将 macOS 上的用户切换到使用工作帐户进行身份验证的网站的工作配置文件。 从 Microsoft Edge 版本 88 开始，我们提供了在 macOS 上切换使用用户工作配置文件进行身份验证的网站的能力。<br>注意：如果用户在 Microsoft Edge 88 之前的版本中登录 Microsoft Edge，可能需要注销然后重新登录，以利用此功能。

- **结束会话的展台模式选项**。 “结束会话”按钮现在在展台模式公共浏览体验中可用。 此功能可确保在关闭 Microsoft Edge 时删除浏览器数据和设置。 详细了解展台模式功能和路线图，配置 [Microsoft Edge 展台模式](./microsoft-edge-configure-kiosk-mode.md)。

- **安全和隐私：**

  - 如果在联机泄露中发现用户的密码，则将生成警报。 将用户密码与已知的已破解的存储库进行核对，如果发现匹配，就会向用户发出警报。 为了确保安全和隐私，当用户密码在与已泄露的凭证数据库进行核对时，会进行哈希处理和加密。
  - 自动升级混合内容。 通过 HTTPS 传递的安全页面可能包含通过非安全 HTTP 提供的引用图像。 为了改进 Microsoft Edge 88 中的隐私和安全性，将改为通过 HTTPS 检索这些图像。 如果图像无法通过 HTTPS 使用，将不会加载它。
  - 按网站和最近活动查看网站权限。 从 Microsoft Edge 88 开始，用户将能够更轻松地管理网站权限。 他们将能够按网站查看权限，而不只是按权限类型查看权限。 此外，我们添加了一个最近的活动部分，它向用户显示其网站权限的所有最近更改。
  - 增加了浏览器 Cookie 的控件。 从 Microsoft Edge 88 开始，用户可以删除第三方 Cookie，而不会影响第一方 Cookie。 用户还可以按第一方或第三方筛选其 Cookie，并按名称、Cookie 数量以及存储和上次修改的数据量进行排序。

- **性能：**

  - 使用休眠选项卡提高浏览器性能。 休眠选项卡通过将非活动选项卡置于睡眠状态以释放系统资源（如内存和 CPU）来提升浏览器性能，以便活动选项卡或其他应用程序可以使用它们。 用户可以阻止网站进入睡眠状态，并配置非活动选项卡进入睡眠状态之前的时间长度。 若要使用户保持其流，还有一些启发性方法可阻止某些网站进入睡眠状态，例如 Intranet 网站。 此功能仅限于一组启用了实验的随机选择的用户。 我们计划默认使用 Microsoft Edge 版本 89 启用休眠选项卡功能。 可以使用组策略管理此功能。
  - 通过启动增强提高 Microsoft Edge 启动速度。 为了提高 Microsoft Edge 启动速度，我们开发了一个名为启动增强的功能。 启动增强使 Microsoft Edge 能够在后台运行，从而加快 Microsoft Edge 启动速度。 注意：此功能仅限于随机选择的一组已启用实验的用户。 这些用户向功能团队提供反馈。

- **工作效率：**

  - 使用垂直选项卡提高工作效率和多任务。 随着水平选项卡数量的增加，网站标题开始关闭，选项卡控件会随着每个选项卡的缩小而丢失。 这会中断用户工作流，因为他们将花费更多时间查找、切换和管理选项卡，并花费更少的时间处理当前任务。 通过垂直选项卡，用户可以将其选项卡移到一侧，其中垂直对齐的图标和较长的网站标题使快速扫描、标识并切换到要打开的选项卡变得更加简单。
  - 自动填写出生日期字段。 Microsoft Edge 已经通过自动填充用户数据（如地址、姓名、电话号码等）来帮助节省填写表单和联机创建帐户的时间和精力。Microsoft Edge 现在支持用户可保存并自动填充的出生日期字段。 用户可以随时在个人资料设置中查看、编辑和删除此信息。
  - 对历史记录中最近关闭的改进。 最近关闭现在使过去的任何浏览会话（而不只是上一个会话）中保留最后 25 个选项卡和窗口。 用户可以在新的历史记录体验中选择"最近关闭"以查看所有打开的选项卡。
  - 默认情况下启用"一天一览"功能。 从 Microsoft Edge 版本 88 开始，信息工作者可以从其"新建"选项卡页中的智能生产力功能 (NTP)。 我们为用户提供使用工作或学校帐户登录的个性化内容以及由 M365 Graph 支持的相关内容。 用户可以快速扫描其"一天一眼"模块，轻松跟踪其会议和最近工作，并快速启动他们想要使用的应用程序。

- **PDF：**

  - 在书籍视图中显示 PDF 文档（两页）。 从 Microsoft Edge 版本 88 开始，用户可以在单页或两页书籍视图中查看 PDF 文档。 若要更改视图，请单击工具栏 中的“**页面视图**”按钮。
  - 定位的文本注释支持 PDF 文件。 从 Microsoft Edge 版本 87 开始，用户可以在 PDF 文件的任何文本条上添加键入的文本注释。
  - PDF 文档中的文本选择体验更流畅。 用户将在 Microsoft Edge 中打开的 PDF 文档中获得更流畅、一致的文本选择体验。
  - 查看在下载栏中另存为 PDF 文件的网页。 用户现在可以通过将“另存为 PDF”设置为下载栏中网页的打印机目标来查看生成的 PDF 文件。

- **字体：**

  - 浏览器图标将更新为 Fluent 设计系统。 作为在浏览器中持续处理 Fluent Design 的一部分，我们进行了更改，使图标与新的 Microsoft 图标系统更加一致。 这些更改将影响我们的许多高接触用户界面，包括选项卡、地址栏，以及各种菜单中的导航和定位图标。
  - 改进了字体呈现。 改进了文本呈现，以提高清晰度并减少模糊性。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

添加了 16 个新策略。 从 [Microsoft Edge 企业登录页面](https://www.microsoft.com/edge/business/download)下载更新的管理模板。 已添加以下新策略。

- [BlockExternalExtensions](./microsoft-edge-policies.md#blockexternalextensions) - 阻止安装外部扩展。
- [InternetExplorerIntegrationLocalFileAllowed](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileallowed) - 允许在 Internet Explorer 模式下启动本地文件。
- [InternetExplorerIntegrationLocalFileExtensionAllowList](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileextensionallowlist) - 在 Internet Explorer 文件扩展名允许列表中打开本地文件。
- [InternetExplorerIntegrationLocalFileShowContextMenu](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileshowcontextmenu) - 显示上下文菜单以在 Internet Explorer 链接。
- [IntranetRedirectBehavior](./microsoft-edge-policies.md#intranetredirectbehavior) - Intranet 重定向行为。
- [PrinterTypeDenyList](./microsoft-edge-policies.md#printertypedenylist) - 禁用拒绝列表上的打印机类型。
- [ShowMicrosoftRewards](./microsoft-edge-policies.md#showmicrosoftrewards) - 显示 Microsoft 奖励体验。
- [SleepingTabsEnabled](./microsoft-edge-policies.md#sleepingtabsenabled) - 配置睡眠选项卡。
- [TimeoutTabsTimeout](./microsoft-edge-policies.md#sleepingtabstimeout) - 为休眠选项卡设置后台选项卡不活动超时。
- [SleepingTabsBlockedForUrls](./microsoft-edge-policies.md#sleepingtabsblockedforurls) - 阻止特定网站上休眠的选项卡。
- [StartupBoostEnabled](./microsoft-edge-policies.md#startupboostenabled) - 启用启动增强。
- [UpdatePolicyOverride](./microsoft-edge-policies.md#updatepolicyoverride) - 指定 Microsoft Edge 更新如何处理来自 Microsoft Edge 的可用更新。
- [VerticalTabsAllowed](./microsoft-edge-policies.md#verticaltabsallowed) - 为浏览器侧面的选项卡配置垂直布局的可用性。
- [WebRtcAllowLegacyTLSProtocols](./microsoft-edge-policies.md#webrtcallowlegacytlsprotocols) - 允许在 WebRTC 中降级旧版 TLS/DTLS。

#### <a name="deprecated-policies"></a>已弃用的策略

以下策略已弃用。

- [ProactiveAuthEnabled](./microsoft-edge-policies.md#proactiveauthenabled) - 启用主动身份验证。
- [ProxyBypassList](./microsoft-edge-policies.md#proxybypasslist) - 配置代理绕过规则。
- [ProxyMode](./microsoft-edge-policies.md#proxymode) - 配置代理服务器设置。
- [ProxyPacUrl](./microsoft-edge-policies.md#proxypacurl) - 设置代理 .pac 文件 URL。
- [ProxyServer](./microsoft-edge-policies.md#proxyserver) - 配置代理服务器的地址或 URL。
- [WebDriverOverridesIncompatiblePolicies](./microsoft-edge-policies.md#webdriveroverridesincompatiblepolicies) - 允许 WebDriver 覆盖不兼容的策略。

#### <a name="obsoleted-policies"></a>已过时的策略

以下策略已过时。

- [DefaultPluginsSetting](./microsoft-edge-policies.md#defaultpluginssetting) - 默认 Adobe Flash 设置。
- [PluginsAllowedForUrls](./microsoft-edge-policies.md#pluginsallowedforurls) - 允许特定网站上使用 Adobe Flash 插件。
- [PluginsBlockedForUrls](./microsoft-edge-policies.md#pluginsblockedforurls) - 阻止特定网站上 Adobe Flash 插件。
- [RunAllFlashInAllowMode](./microsoft-edge-policies.md#runallflashinallowmode) - 将 Adobe Flash 内容设置扩展到所有内容。

<!-- end major 88 -->

## <a name="version-87066455-december-3"></a>版本 87.0.664.55：12月3日

修复了各种 bug 和性能问题。 此版本支持以下新功能。

- **如果在联机泄露中发现用户的密码，则将生成警报**。 用户密码会与已知的已破解的凭证库进行核对，如果发现匹配，就会向用户发出警报。 为了确保安全和隐私，当用户密码在与已泄露的凭证数据库进行核对时，会进行哈希处理和加密。

## <a name="version-87066452-november-30"></a>版本 87.0.664.52：11月30日

修复了各种 bug 和性能问题。

## <a name="version-87066440-november-18"></a>版本 87.0.664.40：11 月 18 日

修复了各种 bug 和性能问题。

## <a name="version-87066436-november-16"></a>版本 87.0.664.36：11 月 16 日

修复了各种 bug 和性能问题。

## <a name="version-87066430-november-9"></a>版本 87.0.664.30：11 月 9 日

修复了各种 bug 和性能问题。

## <a name="version-87066424-november-2"></a>版本 87.0.664.24：11 月 2 日

修复了各种 bug 和性能问题。

## <a name="version-87066418-october-26"></a>版本 87.0.664.18：10 月 26 日

修复了各种 bug 和性能问题。

<!-- begin major 87 -->
## <a name="version-87066412-october-20"></a>版本 87.0.664.12：10 月 20 日

### <a name="feature-updates"></a>功能更新

- **已启用展台模式隐私功能**。 从 Microsoft Edge 87版本开始，将启用帮助企业实现用户数据隐私的展台模式功能。 这些功能将启用以下体验，例如，在退出时清除用户数据、删除已下载的文件，以及在指定的空闲时间后重置配置的启动体验。 深入了解如何 [配置 Microsoft Edge 的展台模式](./microsoft-edge-configure-kiosk-mode.md)
- **在默认情况下启用 ClickOnce 部署**。 Microsoft Edge 87 中默认启用 ClickOnce，这可减少企业部署软件的障碍，并更好地与 Microsoft Edge 旧版浏览器行为保持一致。 从 Microsoft Edge 87 开始，ClickOnceEnabled 策略的“未配置”状态将反映新的默认已启用 ClickOnce 状态（与先前默认“已禁用”状态相比）。
- **企业新选项卡页面（NTP）将生产力与可定制的、与工作相关的源内容整合在一起**。 企业 NTP 将我们提供给用工作或学校账户登录的用户 Office 365 生产率页面与与个性化的、与工作相关的公司和行业信息源融合在一起，并将这些信息源组织在单个页面中。 用户将能够识别熟悉的 Office 365 内容和由 Bing 提供支持的 Microsoft 搜索商业版。 此外，他们可以轻松地翻转到一个可自定义的 "我的信息源"，其中包含与用户、其公司或行业相关的内容和模块，以及组织所提供的其他源的选择。 [了解详细信息](/microsoft-365/admin/manage/manage-industry-news?preserve-view=true&view=o365-worldwide)。

- **隐私和安全：**

  - 支持策略配置网站的TLS令牌绑定。 TLS令牌绑定有助于防止令牌窃取攻击，以确保无法从初始设置的设备以外的设备上重新使用cookie。 使用 TLS 令牌绑定需要设置 [AllowTokenBindingForUrls](./microsoft-edge-policies.md#allowtokenbindingforurls) 策略，并要求列出的网站支持该功能。

- ** 键盘支持对PDF文件的高亮显示**。 用户可使用其键盘键来突出显示 PDF 中的任何文本。

- **打印：**

  - 双面打印时选择翻转的是哪一面。 用户在双面打印时，可以选择在纸张的长边或短边进行翻转。
  - 选择企业的打印光栅化模式。 控制 Microsoft Edge 打印到 Windows 上的非 PostScript 打印机的方式。 有时，在非PostScript打印机上的打印作业需要进行光栅化才能正确打印。 打印选项有 “完整” 和 “快速”。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

增加了十项新政策。 从 [Microsoft Edge 企业登录页面](https://www.microsoft.com/edge/business/download)下载更新的管理模板。 已添加以下新策略。

- [ConfigureFriendlyURLFormat](./microsoft-edge-policies.md#configurefriendlyurlformat) - 配置从 Microsoft Edge 复制的 Url 的默认粘贴格式，并确定用户是否可以使用其他格式。
- [EdgeShoppingAssistantEnabled](./microsoft-edge-policies.md#edgeshoppingassistantenabled) - 已启用 Microsoft Edge 中购物。
- [HideInternetExplorerRedirectUXForIncompatibleSitesEnabled](./microsoft-edge-policies.md#hideinternetexplorerredirectuxforincompatiblesitesenabled) - 隐藏Microsoft Edge上的一次性重定向对话框和横幅。
- [KioskAddressBarEditingEnabled](./microsoft-edge-policies.md#kioskaddressbareditingenabled) - 配置地址栏编辑，实现展台模式的公共浏览体验。
- [KioskDeleteDownloadsOnExit](./microsoft-edge-policies.md#kioskdeletedownloadsonexit) - 删除 Microsoft Edge 关闭时作为展台会话的一部分下载的文件。
- [PasswordRevealEnabled](./microsoft-edge-policies.md#passwordrevealenabled) - 启用密码展示显示按钮。
- [RedirectSitesFromInternetExplorerPreventBHOInstall](./microsoft-edge-policies.md#redirectsitesfrominternetexplorerpreventbhoinstall) - 阻止安装BHO，将不兼容的网站从Internet Explorer重定向到Microsoft Edge。
- [RedirectSitesFromInternetExplorerRedirectMode](./microsoft-edge-policies.md#redirectsitesfrominternetexplorerredirectmode) - 将不兼容的网站从Internet Explorer重定向到Microsoft Edge。
- [SpeechRecognitionEnabled](./microsoft-edge-policies.md#speechrecognitionenabled) - 配置语音识别。
- [WebCaptureEnabled](./microsoft-edge-policies.md#webcaptureenabled) - 在Microsoft Edge中启用网络捕获功能。

#### <a name="deprecated-policy"></a>已弃用政策

[NewTabPageSetFeedType](./microsoft-edge-policies.md#newtabpagesetfeedtype) - 配置 Microsoft Edge 的新选项卡页面体验。

#### <a name="obsoleted-policy"></a>已过时的策略

[EnableDeprecatedWebPlatformFeatures](./microsoft-edge-policies.md#enabledeprecatedwebplatformfeatures) - 在有限的时间内重新启用已超过限定时间的 web 平台功能。

<!-- end major 87 -->

## <a name="version-86062243-october-16"></a>版本 86.0.622.43：10 月 16 日

修复了各种 bug 和性能问题。

## <a name="version-86062236-october-7"></a>版本 86.0.622.36：10 月 7 日

修复了各种 bug 和性能问题。

## <a name="version-86062231-october-1"></a>版本 86.0.622.31：10 月 1 日

修复了各种 bug 和性能问题。

## <a name="version-86062228-september-28"></a>版本 86.0.622.28：9 月 28 日

修复了各种 bug 和性能问题。

## <a name="version-86062215-september-14"></a>版本 86.0.622.15：9 月 14 日

修复了各种 bug 和性能问题。
<!-- major 86 -->
## <a name="version-86062211-september-9"></a>版本 86.0.622.11：9 月 9 日

### <a name="feature-updates"></a>功能更新

* **Internet Explorer 模式：**

   * 让用户使用 Microsoft Edge 用户界面 (UI) 在 Internet Explorer 模式下测试网站。 从Microsoft Edge 版本 86 开始，管理员可以为用户启用一个 UI 选项，让用户在 Internet Explorer 模式加载一个选项卡，以进行测试，或者在网站被添加到网站列表的 XML 中之前作为替代。

* **使用下载管理器从磁盘删除下载。** 用户现在无需离开浏览器即可从磁盘中删除其载的文件。 全新“删除下载”功能位于下载架或下载页面的弹出菜单中。

* **回退到先前的 Microsoft Edge 版本。** 如果最新版本的 Microsoft Edge 中有问题，则“回退”功能可让管理员还原到已知的正确版本的 Microsoft Edge。
[了解详细信息](edge-learnmore-rollback.md)。

* **默认情况下，在企业范围内强制启用“同步”。**  默认情况下，管理员可使用[ForceSync](./microsoft-edge-policies.md#forcesync) 策略为 Azure Active Directory (Azure AD) 帐户启用同步。

* **PDF 更新：**

  * PDF 文档目录。 从版本 86 开始，Microsoft Edge 添加了对目录的支持，可让用户轻松浏览 PDF 文档。
  * 在小型外形规格屏幕上访问所有 PDF 功能。 在具有小型屏幕尺寸的设备上访问 Microsoft Edge PDF 阅读器的所有功能。
  * PDF 文件上对荧光笔的支持。 通过此更新，用户可使用数字荧光笔直接突出显示 PDF 文件上的文本，就像使用物理荧光笔和纸张一样。
  * 改进了 PDF 滚动。 现在，你可以在浏览较长的 PDF 文档时体验流畅的滚动效果。

* **Windows 7、8 和 8.1 上的自动配置文件切换。** Windows 10 上的 Microsoft Edge 中当前提供的自动配置文件切换扩展到了早期版本的 Windows （Windows 7、8 和 8.1）。 有关详细信息，请参阅博客文章中的[自动配置文件 切换](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/)。

* **当用户开始在 Microsoft Edge 加载项网站中键入搜索查询时，将看到自动完成建议。** 自动完成将帮助用户快速完成搜索查询，而无需键入完整字符串。 这将非常有用，因为用户无需记住正确的拼写，可以从显示的可用选项中进行选择。

* **删除 HTML5 应用程序缓存 API。**  从 Microsoft Edge 版本 86 开始，从 Microsoft Edge 中删除了启用网页脱机使用的旧版应用程序缓存 API。 有关将应用程序缓存 API 替换为服务工作进程的信息，Web 开发人员可以查看 [WebDev 文档](https://web.dev/appcache-removal/)。  重要提示：你可以请求[ AppCache OriginTrial 令牌](https://developers.chrome.com/origintrials/#/view_trial/1776670052997660673)，该令牌允许网站继续使用已弃用的应用程序缓存 API，直至 Microsoft Edge 版本90。

* **安全性：**

  * 安全 DNS (DNS-over-HTTPS) 支持。  从 Microsoft Edge 版本 86 开始，可以使用设置来控制非托管设备上的安全 DNS。 用户无法访问已托管设备上的这些设置，但 IT 管理员可以使用 [dnsoverhttpsmode](./microsoft-edge-policies.md#dnsoverhttpsmode) 组策略启用或禁用安全 DNS。


* **使用组策略向全新选项卡页面 (NTP) 中添加自定义图像。** 从 Microsoft Edge 版本 86 开始，NTP 可以选择使用自定义用户提供的图像来替换默认图像。 组策略也支持管理此图像属性的功能。

* **匹配自定义键盘快捷方式与 VS Code。** Microsoft Edge 开发工具现在支持自定义开发工具中的键盘快捷方式，使其匹配你的编辑器/IDE。 （在 Microsoft Edge 84 中，我们添加了匹配开发工具键盘快捷方式和 VS Code 的功能）。

* **为早期版本的 Windows 和 macOS 替换[MetricsReportingEnabled]( /DeployEdge/microsoft-edge-policies#metricsreportingenabled) 和 [SendSiteInformationToImproveServices]( /DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices)策略。** 这些策略在 Microsoft Edge 版本 86 中已弃用，在 Microsoft Edge 版本 89 中将不再使用。<br>
这些策略将被 Windows 10 上的[允许遥测](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)和所有其他平台的全新[DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) 策略取代。 这将使用户能够为 Windows 7、8、8.1 和 macOS 管理发送到 Microsoft 的诊断数据。

* ** 默认情况下 SameSite=Lax Cookies**。 为了提高 Web 安全性和隐私，默认情况下，Cookie 将默认为 [SameSite=Lax](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite) 处理。 这意味着 Cookie 将仅在第一方上下文中发送，而对于发送给第三方的请求将被忽略。 此更改可能会对需要 Cookie 才能使第三方资源正常运行的网站造成兼容性影响。 为了允许此类 Cookie，Web 开发人员可以通过在设置 Cookie 时添加显式 `SameSite=none` 和 `Secure` 属性来标记应从第三方上下文设置并发送给第三方上下文的 Cookie。 希望将某些网站排除在此更改之外的企业可以使用 [LegacySameSiteCookieBehaviorEnabledForDomainList](./microsoft-edge-policies.md#legacysamesitecookiebehaviorenabledfordomainlist) 策略执行此操作，也可以使用 [LegacySameSiteCookieBehaviorEnabled](./microsoft-edge-policies.md#legacysamesitecookiebehaviorenabled) 策略在所有网站上选择退出此更改。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

已添加 19 个新策略。 从 [Microsoft Edge 企业登录页面](https://aka.ms/EdgeEnterprise)下载更新的管理模板。 已添加以下新策略。

- [CollectionsServicesAndExportsBlockList](./microsoft-edge-policies.md#collectionsservicesandexportsblocklist) - 阻止访问指定服务列表及在集锦中导出目标。
- [DefaultSensorsSetting](./microsoft-edge-policies.md#defaultsensorssetting) - 默认传感器设置。
- [DefaultSerialGuardSetting](./microsoft-edge-policies.md#defaultserialguardsetting) - 控制串行 API 的使用。
- [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) - 发送有关浏览器使用情况的必需和可选诊断数据。
- [EnterpriseModeSiteListManagerAllowed](./microsoft-edge-policies.md#enterprisemodesitelistmanagerallowed) - 允许访问 Enterprise Mode Site List Manager 工具。
- [ForceSync](./microsoft-edge-policies.md#forcesync) - 强制同步浏览器数据，但不显示同步许可提示。
- [InsecureFormsWarningsEnabled](./microsoft-edge-policies.md#insecureformswarningsenabled) - 启用不安全窗体的警告。
- [InternetExplorerIntegrationTestingAllowed](./microsoft-edge-policies.md#internetexplorerintegrationtestingallowed) - 允许 Internet Explorer 模式测试。
- [SpotlightExperiencesAndRecommendationsEnabled](./microsoft-edge-policies.md#spotlightexperiencesandrecommendationsenabled) - 选择用户是否可接收自定义的背景图像和文本、建议、通知及 Microsoft 服务提示。
- [NewTabPageAllowedBackgroundTypes](./microsoft-edge-policies.md#newtabpageallowedbackgroundtypes) - 配置全新选项卡页面布局允许使用的背景类型。
- [SaveCookiesOnExit](./microsoft-edge-policies.md#savecookiesonexit) - Microsoft Edge 关闭时保存 Cookie。
- [SensorsAllowedForUrls](./microsoft-edge-policies.md#sensorsallowedforurls) - 允许访问特定网站上的传感器。
- [SensorsBlockedForUrls](./microsoft-edge-policies.md#sensorsblockedforurls) - 阻止访问特定网站上的传感器。
- [SerialAskForUrls](./microsoft-edge-policies.md#serialaskforurls) - 在特定网站上允许串行 API。
- [SerialBlockedForUrls](./microsoft-edge-policies.md#serialblockedforurls) - 在特定网站上阻止串行 API。
- [URLBlocklist](./microsoft-edge-policies.md#urlblocklist) - 阻止对 URL 列表的访问。
- [URLAllowlist](./microsoft-edge-policies.md#urlallowlist) - 定义允许的 URL 列表。
- [UserAgentClientHintsEnabled](./microsoft-edge-policies.md#useragentclienthintsenabled) - 启用“User-Agent 客户端提示”功能（已弃用）。
- [UserDataSnapshotRetentionLimit](./microsoft-edge-policies.md#userdatasnapshotretentionlimit) - 限制保留用于紧急回退情况的用户数据快照数量。

#### <a name="deprecated-policies"></a>已弃用的策略

- [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled)：启用使用情况和故障相关数据报告。
- [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices)：发送站点信息以改进 Microsoft 服务。

#### <a name="obsoleted-policy"></a>已过时的策略

[TLS13HardeningForLocalAnchorsEnabled](./microsoft-edge-policies.md#tls13hardeningforlocalanchorsenabled) - 为本地信任密钥启用 TLS 1.3 安全功能。

#### <a name="policy-caption-changed"></a>已更改策略标题

[NativeWindowOcclusionEnabled](./microsoft-edge-policies.md#nativewindowocclusionenabled) - 启用本机窗口封闭。

#### <a name="policy-description-changed"></a>已更改策略说明

- [AdsSettingForIntrusiveAdsSites](./microsoft-edge-policies.md#adssettingforintrusiveadssites)
- [AllowTokenBindingForUrls](./microsoft-edge-policies.md#allowtokenbindingforurls)
- [AmbientAuthenticationInPrivateModesEnabled](./microsoft-edge-policies.md#ambientauthenticationinprivatemodesenabled)
- [ApplicationGuardContainerProxy](./microsoft-edge-policies.md#applicationguardcontainerproxy)
- [AutoImportAtFirstRun](./microsoft-edge-policies.md#autoimportatfirstrun)
- [AutoOpenFileTypes](./microsoft-edge-policies.md#autoopenfiletypes)
- [BrowserSignin](./microsoft-edge-policies.md#browsersignin)
- [ClearBrowsingDataOnExit](./microsoft-edge-policies.md#clearbrowsingdataonexit) 
- [ClickOnceEnabled](./microsoft-edge-policies.md#clickonceenabled)
- [CommandLineFlagSecurityWarningsEnabled](./microsoft-edge-policies.md#commandlineflagsecuritywarningsenabled)
- [ConfigureOnPremisesAccountAutoSignIn](./microsoft-edge-policies.md#configureonpremisesaccountautosignin)
- [ConfigureShare](./microsoft-edge-policies.md#configureshare)
- [CookiesAllowedForUrls](./microsoft-edge-policies.md#cookiesallowedforurls)
- [CustomHelpLink](./microsoft-edge-policies.md#customhelplink)
- [DefaultCookiesSetting](./microsoft-edge-policies.md#defaultcookiessetting)
- [DefaultGeolocationSetting](./microsoft-edge-policies.md#defaultgeolocationsetting)
- [DefaultImagesSetting](./microsoft-edge-policies.md#defaultimagessetting)
- [DefaultInsecureContentSetting](./microsoft-edge-policies.md#defaultinsecurecontentsetting)
- [DefaultJavaScriptSetting](./microsoft-edge-policies.md#defaultjavascriptsetting)
- [DefaultNotificationsSetting](./microsoft-edge-policies.md#defaultnotificationssetting)
- [DefaultPluginsSetting](./microsoft-edge-policies.md#defaultpluginssetting)
- [DefaultPopupsSetting](./microsoft-edge-policies.md#defaultpopupssetting)
- [DefaultSearchProviderEnabled](./microsoft-edge-policies.md#defaultsearchproviderenabled)
- [DefaultWebBluetoothGuardSetting](./microsoft-edge-policies.md#defaultwebbluetoothguardsetting)
- [DefaultWebUsbGuardSetting](./microsoft-edge-policies.md#defaultwebusbguardsetting)
- [DelayNavigationsForInitialSiteListDownload](./microsoft-edge-policies.md#delaynavigationsforinitialsitelistdownload)
- [DeveloperToolsAvailability](./microsoft-edge-policies.md#developertoolsavailability)
- [EnableSha1ForLocalAnchors](./microsoft-edge-policies.md#enablesha1forlocalanchors)
- [DownloadRestrictions](./microsoft-edge-policies.md#downloadrestrictions)
- [EnableDeprecatedWebPlatformFeatures](./microsoft-edge-policies.md#enabledeprecatedwebplatformfeatures)
- [WinHttpProxyResolverEnabled](./microsoft-edge-policies.md#winhttpproxyresolverenabled)
- [ExperimentationAndConfigurationServiceControl](./microsoft-edge-policies.md#experimentationandconfigurationservicecontrol)
- [ExternalProtocolDialogShowAlwaysOpenCheckbox](./microsoft-edge-policies.md#externalprotocoldialogshowalwaysopencheckbox)
- [ExtensionInstallForcelist](./microsoft-edge-policies.md#extensioninstallforcelist)
- [ForceBingSafeSearch](./microsoft-edge-policies.md#forcebingsafesearch)
- [ForceYouTubeRestrict](./microsoft-edge-policies.md#forceyoutuberestrict)
- [HomepageIsNewTabPage](./microsoft-edge-policies.md#homepageisnewtabpage)
- [HomepageLocation](./microsoft-edge-policies.md#homepagelocation)
- [InPrivateModeAvailability](./microsoft-edge-policies.md#inprivatemodeavailability)
- [InternetExplorerIntegrationEnhancedHangDetection](./microsoft-edge-policies.md#internetexplorerintegrationenhancedhangdetection)
- [InternetExplorerIntegrationLevel](./microsoft-edge-policies.md#internetexplorerintegrationlevel)
- [InternetExplorerIntegrationSiteRedirect](./microsoft-edge-policies.md#internetexplorerintegrationsiteredirect)
- [LegacySameSiteCookieBehaviorEnabled](./microsoft-edge-policies.md#legacysamesitecookiebehaviorenabled)
- [NativeWindowOcclusionEnabled](./microsoft-edge-policies.md#nativewindowocclusionenabled)
- [NavigationDelayForInitialSiteListDownloadTimeout](./microsoft-edge-policies.md#navigationdelayforinitialsitelistdownloadtimeout)
- [NetworkPredictionOptions](./microsoft-edge-policies.md#networkpredictionoptions)
- [NewTabPageLocation](./microsoft-edge-policies.md#newtabpagelocation)
- [NewTabPageSearchBox](./microsoft-edge-policies.md#newtabpagesearchbox)
- [NewTabPageSetFeedType](./microsoft-edge-policies.md#newtabpagesetfeedtype)
- [NonRemovableProfileEnabled](./microsoft-edge-policies.md#nonremovableprofileenabled)
- [PasswordProtectionWarningTrigger](./microsoft-edge-policies.md#passwordprotectionwarningtrigger)
- [PasswordProtectionLoginURLs](./microsoft-edge-policies.md#passwordprotectionloginurls)
- [PasswordProtectionChangePasswordURL](./microsoft-edge-policies.md#passwordprotectionchangepasswordurl)
- [PluginsAllowedForUrls](./microsoft-edge-policies.md#pluginsallowedforurls)
- [PluginsBlockedForUrls](./microsoft-edge-policies.md#pluginsblockedforurls)
- [PreventSmartScreenPromptOverride](./microsoft-edge-policies.md#preventsmartscreenpromptoverride)
- [PreventSmartScreenPromptOverrideForFiles](./microsoft-edge-policies.md#preventsmartscreenpromptoverrideforfiles)
- [ProxyMode](./microsoft-edge-policies.md#proxymode)
- [RegisteredProtocolHandlers](./microsoft-edge-policies.md#registeredprotocolhandlers)
- [RelaunchNotification](./microsoft-edge-policies.md#relaunchnotification)
- [RestoreOnStartup](./microsoft-edge-policies.md#restoreonstartup)
- [RestoreOnStartupURLs](./microsoft-edge-policies.md#restoreonstartupurls)
- [RestrictSigninToPattern](./microsoft-edge-policies.md#restrictsignintopattern)
- [SSLVersionMin](./microsoft-edge-policies.md#sslversionmin)
- [SmartScreenAllowListDomains](./microsoft-edge-policies.md#smartscreenallowlistdomains)
- [SmartScreenEnabled](./microsoft-edge-policies.md#smartscreenenabled)
- [SmartScreenForTrustedDownloadsEnabled](./microsoft-edge-policies.md#smartscreenfortrusteddownloadsenabled)
- [SmartScreenPuaEnabled](./microsoft-edge-policies.md#smartscreenpuaenabled)
- [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled)
- [TrackingPrevention](./microsoft-edge-policies.md#trackingprevention)
- [WebRtcLocalhostIpHandling](./microsoft-edge-policies.md#webrtclocalhostiphandling)

<!-- end 86 -->

## <a name="version-85056441-august-25"></a>版本 85.0.564.41：8 月 25 日

修复了各种 bug 和性能问题。

## <a name="version-85056440-august-21"></a>版本 85.0.564.40：8 月 21 日

修复了各种 bug 和性能问题。

## <a name="version-85056436-august-17"></a>版本 85.0.564.36：8 月 17 日

修复了各种 bug 和性能问题。

## <a name="version-85056430-august-10"></a>版本 85.0.564.30：8 月 10 日

修复了各种 bug 和性能问题。

## <a name="version-85056423-august-3"></a>版本 85.0.564.23：8 月 3 日

修复了各种 bug 和性能问题。
<!-- major 85 -->
## <a name="version-85056418-july-28"></a>版本 85.0.564.18：7 月 28 日

### <a name="feature-updates"></a>功能更新

- **收藏夹和设置的本地同步**。 你现在可以在自己的环境中实现 Active Directory 配置文件之间的浏览器收藏夹和设置同步，而无需云同步。

- **使用 Microsoft Edge 组策略支持，无需确认提示即可启动信任网站 + 应用组合。** 已添加的组策略支持允许管理员添加受信任的网站 + 应用组合，无需确认提示即可启动。 这添加了一项功能，让管理员为其最终用户配置信任协议/原点组合（例如 Microsoft 365 应用），从而在导航到包含应用协议的 URL 时禁止确认提示。

- **PDF 荧光笔工具**。 此工具可添加到 PDF 工具栏中，方便突出显示重要文本。

- **存储访问 API 现可使用**。 当用户直接指示允许本来会被浏览器的当前配置阻止的存储时，可使用此存储访问 API 来访问第三方上下文中的第一方存储。 有关详细信息，请参阅[存储访问 API](https://www.chromestatus.com/feature/5612590694662144)。

- **Microsoft Edge 集合现可使用“发送至 OneNote”**。 所有人都期待能将集合中已收集的信息发送至 OneNote，从而追加信息到更大的项目中，与他人进行协作！ 更重要的是，在 Microsoft Edge 85 中，使用 Microsoft 帐户和 Azure Active Directory 均可发送内容到 *Office for Mac* 产品（Word、Excel 和 OneNote）。

- **开发工具更新**。 有关以下更新的详细信息，请参阅[开发工具新增功能 (Microsoft Edge 85)](/microsoft-edge/devtools-guide-chromium/whats-new/2020/06/devtools)。

   - Microsoft Edge 开发工具支持 Surface Duo 仿真。 Microsoft Edge 开发工具能够仿真 Surface Duo，因此可测试 Web 内容在双屏设备上的显示效果。 若要在开发工具中打开此试验，请在 Windows 上按 Ctrl+Shift+M 或在 macOS 上按 Command+Shift+M 来输入设备模式，然后在设备下拉列表中选择 Surface Duo。
   - Microsoft Edge 开发工具允许键盘快捷方式和 VS Code 相匹配。 Microsoft Edge 开发工具支持自定义开发工具中的键盘快捷方式，使其匹配你的编辑器/IDE。 在 Microsoft Edge 85 中，我们添加了匹配开发工具键盘快捷方式和 VS Code 的功能。 此更改将有助于增加 VS Code 和开发工具之间的工作效率。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

添加了 13 个新策略。 从 [Microsoft Edge 企业登录页面](https://aka.ms/EdgeEnterprise)下载更新的管理模板。 已添加以下新策略。

- [AutoLaunchProtocolsFromOrigins](./microsoft-edge-policies.md#autolaunchprotocolsfromorigins) - 定义可从列出的源启动外部应用程序的协议的列表，而无需提示用户。
- [AutoOpenAllowedForURLs](./microsoft-edge-policies.md#autoopenallowedforurls) - AutoOpenFileTypes 可应用的 URL。
- [AutoOpenFileTypes](./microsoft-edge-policies.md#autoopenfiletypes) - 下载时自动打开的文件类型列表。
- [DefaultSearchProviderContextMenuAccessAllowed](./microsoft-edge-policies.md#defaultsearchprovidercontextmenuaccessallowed) - 允许默认搜索提供程序中的上下文菜单搜索访问。
- [EnableSha1ForLocalAnchors](./microsoft-edge-policies.md#enablesha1forlocalanchors) - 允许由本地信任定位点颁发的 SHA - 1 签名证书。
- [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](./microsoft-edge-policies.md#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - 对域上指定的文件类型，禁用基于文件类型扩展名下载的警告。
- [IntensiveWakeUpThrottlingEnabled](./microsoft-edge-policies.md#intensivewakeupthrottlingenabled) - 控制 IntensiveWakeUpThrottling 功能。
- [NewTabPagePrerenderEnabled](./microsoft-edge-policies.md#newtabpageprerenderenabled) - 启用新选项卡页面的预加载，以便快速呈现。
- [NewTabPageSearchBox](./microsoft-edge-policies.md#newtabpagesearchbox) - 配置新的选项卡页面搜索框体验。
- [PasswordMonitorAllowed](./microsoft-edge-policies.md#passwordmonitorallowed) - 当用户的密码被发现不安全时，允许收到警告。
- [RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled) - 支持使用 Microsoft Edge 配置文件数据的漫游副本。
- [RoamingProfileLocation](./microsoft-edge-policies.md#roamingprofilelocation) - 设置漫游配置文件目录。
- [TLSCipherSuiteDenyList](./microsoft-edge-policies.md#tlsciphersuitedenylist) - 指定要禁用的 TLS 密码套件。

#### <a name="obsoleted-policies"></a>已过时的策略

- [EnableDomainActionsDownload](./microsoft-edge-policies.md#enabledomainactionsdownload) - 启用来自 Microsoft 的域操作下载。
- [WebComponentsV0Enabled](./microsoft-edge-policies.md#webcomponentsv0enabled) - 重新启用 Web 组件 v0 API 至 M84。
- [WebDriverOverridesIncompatiblePolicies](./microsoft-edge-policies.md#webdriveroverridesincompatiblepolicies)- 允许 WebDriver 覆盖不兼容策略。

<!--- END ---->

## <a name="version-84052235-july-9"></a>版本 84.0.522.35：7 月 9 日

修复了各种 bug 和性能问题。

## <a name="version-84052228-june-26"></a>版本 84.0.522.28：6 月 26 日

修复了各种 bug 和性能问题。

## <a name="version-84052226-june-24"></a>版本 84.0.522.26：6 月 24 日

修复了各种 bug 和性能问题。

## <a name="version-84052220-june-15"></a>版本 84.0.522.20：6 月 15 日

修复了各种 bug 和性能问题。

## <a name="version-84052215-june-8"></a>版本 84.0.522.15：6 月 8 日

修复了各种 bug 和性能问题。

## <a name="version-84052211-june-2"></a>版本 84.0.522.11：6 月 2 日

### <a name="feature-updates"></a>功能更新

- 该版本的 Microsoft Edge 缩短了 Internet Explorer 模式的网站列表下载时间。  没有缓存网站列表时，我们将 Internet Explorer 模式网站列表的下载延迟从 60 秒的等待时间缩短为了 0 秒。 我们还添加了组策略支持，用来应对需要推迟到网站列表下载后再进行 Internet Explorer 模式主页导航的情况。 有关详细信息，请参阅 [DelayNavigationsForInitialSiteListDownload](./microsoft-edge-policies.md#delaynavigationsforinitialsitelistdownload) 策略。

- 现在，Microsoft Edge 在 Windows 10 上“以管理员身份运行”时，允许用户登录到浏览器。 这将帮助用户在 Windows Server 上或在远程桌面和沙盒场景中运行 Microsoft Edge。

- Microsoft Edge 现在处于全屏模式时提供完整的鼠标支持。 现在，你无需退出全屏模式即可使用鼠标来访问选项卡、地址栏和其他项目。

- 改进了在线购买。 向保存的借记卡或信用卡添加自定义别名。 现在，你在线购买时可区分和辨别借记卡。 通过给借记卡或信用卡“起绰号”，可让你在使用“自动填充”功能来选择付款方式时选择适当的卡片。

- 默认禁用 TLS/1.0 和 TLS/1.1。 为帮助发现受影响的网站，你可设置 *edge://flags/#display-legacy-tls-warnings* 标志，使 Microsoft Edge 在加载需要旧的 TLS 协议的页面时显示非阻塞的“不安全”通知。 可通过 [SSLVersionMin](./microsoft-edge-policies.md#sslversionmin) 策略重新启用 TLS/1.0 和 TLS/1.1。 此策略将持续可用，直到至少达到 Microsoft Edge 版本 88 为止。 有关详细信息，请参阅 [Microsoft Edge 中影响网站兼容性的更改](/microsoft-edge/web-platform/site-impacting-changes)。

- 改进了集合：

  - 添加了一项“注释”功能，你可用它来对集合中的项目添加注释或备注。 注释分组到一起，即使你对集合中的项目进行了排序，它们也附加到相应的项目上。 若要试用这项新功能，请右键单击一个项目，然后选择“添加注释”。
  - 可更改集合中注释的背景色。 可使用颜色编码来帮助你整理信息并提高工作效率。
  - 有明显的性能改进，让你在将集合导出到 Excel 时所用时间比在之前版本的 Microsoft Edge 中操作时要短。

- 其他 Microsoft Edge API 支持：

  - 存储访问 API。 当用户直接指示允许本来会被浏览器的当前配置阻止的存储时，可使用此 API 来访问第三方上下文中的第一方存储。

    随着隐私对用户来说越来越重要，对更严格的浏览器默认设置和用户选择加入设置（例如阻止所有第三方存储访问）的需求越来越常见。 虽然这些设置可帮助加强隐私保护和阻止未知或不受信任的用户方不必要的访问，但它们也可能产生并未期待的副作用，例如阻止访问用户可能想要查看的内容（比如社交媒体和嵌入的媒体内容）。

  - 本机文件系统 API，这意味着你可通过它来向网站授予编辑文件或文件夹的权限。

- 改进了 PDF：

  - 通过 PDF 的“大声朗读”功能，用户可在执行其他对他们而言可能很重要的任务的同时收听 PDF 内容。 它还有助于音频视觉学习者专注阅读内容，让学习变得更轻松。
  - PDF 文件编辑也得到了改进。 你现可将对 PDF 进行的编辑保存回文件，而不是每次编辑 PDF 时都保存一个副本。

- Microsoft Edge 现在沉浸式阅读器中启用翻译功能。 当用户打开“沉浸式阅读器”视图时，他们可将页面翻译成他们期待的语言。

- 开发工具支持自定义键盘快捷方式，使其匹配你的编辑器/IDE（包括 VS Code）。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

添加了 5 个新策略。 从 [Microsoft Edge 企业登录页面](https://aka.ms/EdgeEnterprise)下载更新的管理模板。 已添加以下新策略。

- [AppCacheForceEnabled](./microsoft-edge-policies.md#appcacheforceenabled) - 允许重新启用 AppCache 功能，即使该功能默认关闭也是如此。
- [ApplicationGuardContainerProxy](./microsoft-edge-policies.md#applicationguardcontainerproxy) - 应用程序防护容器代理。
- [DelayNavigationsForInitialSiteListDownload](./microsoft-edge-policies.md#delaynavigationsforinitialsitelistdownload) - 要求在可进行标签页导航之前，企业模式网站列表可用。
- [NativeWindowOcclusionEnabled](./microsoft-edge-policies.md#nativewindowocclusionenabled) - 允许隐藏本机窗口。
- [NavigationDelayForInitialSiteListDownloadTimeout](./microsoft-edge-policies.md#navigationdelayforinitialsitelistdownloadtimeout) -为企业模式网站列表设置标签页导航的延迟超时。

#### <a name="deprecated-policies"></a>已弃用的策略

- [AllowSyncXHRInPageDismissal](./microsoft-edge-policies.md#allowsyncxhrinpagedismissal) - 允许页面在页面关闭期间发送同步 XHR 请求。
- [BuiltinCertificateVerifierEnabled](./microsoft-edge-policies.md#builtincertificateverifierenabled) - 确定是否将使用内置证书验证程序来验证服务器证书。
- [StricterMixedContentTreatmentEnabled](./microsoft-edge-policies.md#strictermixedcontenttreatmentenabled) - 对混合内容进行更严格的处理。

#### <a name="obsoleted-policy"></a>已过时的策略

[ForceNetworkInProcess](./microsoft-edge-policies.md#forcenetworkinprocess) - 强制网络代码在浏览器进程中运行。

<!-- end 84 -->

## <a name="version-83047844-june-1"></a>版本 83.0.478.44：6 月 1 日

修复了各种 bug 和性能问题。

## <a name="version-83047837-may-20"></a>版本 83.0.478.37：5 月 20 日

修复了各种 bug 和性能问题。

## <a name="version-83047833-may-15"></a>版本 83.0.478.33：5 月 15 日

修复了各种 bug 和性能问题。

## <a name="version-83047828-may-7"></a>版本 83.0.478.28：5 月 7 日

修复了各种 bug 和性能问题。

## <a name="version-83047825-may-4"></a>版本 83.0.478.25：5 月 4 日

修复了各种 bug 和性能问题。

## <a name="version-83047818-april-27"></a>版本 83.0.478.18：4 月 27 日

修复了各种 bug 和性能问题。

## <a name="version-83047813-april-22"></a>版本 83.0.478.13：4 月 22 日

### <a name="feature-updates"></a>功能更新

- Microsoft Defender SmartScreen 改进：对 Microsoft Defender SmartScreen 服务进行了多种改进，如改进了对加载时重定向的恶意网站的保护，以及通过 Microsoft Defender SmartScreen 安全页完全替换恶意网站的顶级框架阻止。 顶级框架阻止功能可阻止播放恶意网站中的音频和其他媒体，从而使用户感觉更容易、更轻松。

- 根据用户反馈，用户现在可以解除部分 Cookie 限制，使其在浏览器关闭时自动清除。 如果有用户不希望注销的网站，但是希望在关闭浏览器时清除所有其他 Cookie ，则此选项非常有用。 若要使用此功能，请转到 *edge://settings/clearBrowsingDataOnClose* 并启用“Cookie 和其他网站数据”切换。

- 自动配置文件切换现在可用，有助于更轻松地跨配置文件获取工作内容。 如果你在工作中使用多个配置文件，可以在使用个人配置文件时，通过浏览至需要工作或学校账户验证的网站查看配置文件。 如果检测到更改，你将收到切换到工作简介的提示，这样无需进行身份验证即可访问该网站。 选择你想切换到的工作简介后，该网站将打开你的工作简介。 此配置文件切换功能将有助于将工作和个人数据分开，轻松地获取工作内容。 如果不希望提示切换配置文件的功能，可选择“不再询问”选项，然后就会不再发出提醒。

- 集合功能改进：
  - 可以使用拖放操作将项目添加到集合中，而无需打开集合。 拖放期间，还可在集合列表中选择希望放置项目的位置。
  - 可以将多个项目添加到集合中，而不是一次添加一项。 若要添加多个项，选择项，然后拖动至集合中。 或者，可以选择项目，右键单击，然后选择希望放置项的集合。

- 可以将 Edge 窗口中的所有选项卡添加到新集合中，而无需单独添加。 若要添加所有选项卡，右键单击任意选项卡，然后选择“将所有选项卡添加到新集合中”。

- 扩展同步现在可用。 现在，可以在你的所有设备上同步扩展！ Microsoft 和 Chrome 应用商店中的扩展程序都将与 Microsoft Edge 同步。 若要使用此功能：单击菜单栏上的省略号（**...**），选择“**设置**”。 在配置文件下，单击“**同步**”以查看“同步”选项。 在“**配置文件 / 同步**”下，使用切换来启用扩展。 可使用 [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) 组策略来禁用扩展同步。

- 改进了下载管理页面上针对已阻止的不安全下载的消息。

- 沉浸式阅读器改进：
  - 现在支持在沉浸式阅读器中的“词性”体验中使用“副词”。 在沉浸式阅读器中阅读文章时，打开“语法工具”，并在“词性”中打开“副词”，可以突出显示页面上的所有副词。
  - 现在支持选择网页上的任何内容并在在沉浸式阅读器中打开。 借助此功能，用户可以在所有网站中使用沉浸式阅读器和所有学习工具，如“行焦点”和“大声朗读”。

- 在用户输入错误的 URL 时，链接医生会向用户提供主机更正和搜索查询。 例如： <br>
用户将“powerbi”错误输入为“powerbbi”.com。 链接医生将建议“powerbi”.com 作为更正，并创建一个链接以搜索“powerbbi”，以防用户查找不同的内容。

- 允许用户保存其为特定站点启动外部协议的决定。 用户可以配置 [ExternalProtocolDialogShowAlwaysOpenCheckbox](/DeployEdge/microsoft-edge-policies#externalprotocoldialogshowalwaysopencheckbox) 策略以启用或禁用此功能。

- 用户可以直接从 Microsoft Edge“**设置**”将 Microsoft Edge 设为默认浏览器。 此功能对用户来说，能够更加轻松地在浏览器自身上下文中更改默认浏览器，无需搜索整个操作系统设置。 要使用此功能，请转到 *edge://settings/defaultBrowser*，然后单击“**设为默认值**”。

- 许多开发工具更新，包括新的远程调试支持、UI 改进等。 有关详细信息，请参阅 [开发工具新增功能(Microsoft Edge 83)](/microsoft-edge/devtools-guide-chromium/whats-new/2020/03/devtools)。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

添加了 15 个新策略。 从 [Microsoft Edge 企业登录页面](https://aka.ms/EdgeEnterprise)下载更新的管理模板。 已添加以下新策略。

- [AllowSurfGame](./microsoft-edge-policies.md#allowsurfgame) - 允许冲浪游戏。
- [AllowTokenBindingForUrls](./microsoft-edge-policies.md#allowtokenbindingforurls) - 配置 Microsoft Edge 将尝试与其建立令牌绑定的网站列表。
- [BingAdsSuppression](./microsoft-edge-policies.md#bingadssuppression) - 阻止所有必应搜索结果中的广告。
- [BuiltinCertificateVerifierEnabled](./microsoft-edge-policies.md#builtincertificateverifierenabled) - 确定是否将使用内置证书验证程序来验证服务器证书。
- [ClearCachedImagesAndFilesOnExit](./microsoft-edge-policies.md#clearcachedimagesandfilesonexit) - Microsoft Edge关闭时，清除缓存的图像和文件。
- [ConfigureShare](./microsoft-edge-policies.md#configureshare) - 配置共享体验。
- [DeleteDataOnMigration](./microsoft-edge-policies.md#deletedataonmigration) - 迁移时删除旧的浏览器数据。
- [DnsOverHttpsMode](./microsoft-edge-policies.md#dnsoverhttpsmode) - 控制 DNS-over-HTTPS 的模式。
- [DnsOverHttpsTemplates](./microsoft-edge-policies.md#dnsoverhttpstemplates) - 指定期望 DNS-over-HTTPS 解析程序的 URI 模板。
- [FamilySafetySettingsEnabled](./microsoft-edge-policies.md#familysafetysettingsenabled) - 允许用户配置家庭安全。
- [LocalProvidersEnabled](./microsoft-edge-policies.md#localprovidersenabled) - 允许来自本地提供商的建议。
- [ScrollToTextFragmentEnabled](./microsoft-edge-policies.md#scrolltotextfragmentenabled) - 启用滚动到 URL 片段中的文本。
- [ScreenCaptureAllowed](./microsoft-edge-policies.md#screencaptureallowed) - 允许或拒绝屏幕捕获。
- [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) - 配置同步中排除的类型列表。
- [NativeWindowOcclusionEnabled](./microsoft-edge-policies.md#nativewindowocclusionenabled) - 允许隐藏本机窗口。

#### <a name="deprecated-policy"></a>已弃用策略

以下策略将在此版本中继续有效。 在未来的版本中，它将被“弃用”。

[EnableDomainActionsDownload](./microsoft-edge-policies.md#enabledomainactionsdownload) 启用来自 Microsoft 的域操作下载

<!--  end 83 -->

## <a name="version-81041660-april-20"></a>版本 81.0.416.60：4 月 20 日

修复了各种 bug 和性能问题。

## <a name="version-81041658-april-17"></a>版本 81.0.416.58：4 月 17 日

安全更新。

## <a name="version-81041650-april-10"></a>版本 81.0.416.50：4 月 10 日

修复了各种 bug 和性能问题。

## <a name="version-81041645-april-3"></a>版本 81.0.416.45：4 月 3 日

修复了各种 bug 和性能问题。

## <a name="version-81041641-march-30"></a>版本 81.0.416.41：3 月 30 日

修复了各种 bug 和性能问题。

## <a name="version-81041634-march-17"></a>版本 81.0.416.34：3 月 17 日

修复了各种 bug 和性能问题。

## <a name="version-81041631-march-12"></a>版本 81.0.416.31：3 月 12 日

修复了各种 bug 和性能问题。

## <a name="version-81041628-march-9"></a>版本 81.0.416.28：3 月 9 日

修复了各种 bug 和性能问题。

## <a name="version-81041620-february-28"></a>版本 81.0.416.20：2 月 28 日

修复了各种 bug 和性能问题。

## <a name="version-81041612-february-20"></a>版本 81.0.416.12：2 月 20 日

### <a name="feature-updates"></a>功能更新

- 现已推出“收藏”功能。 可通过单击地址栏旁边的“收藏”图标开始使用。 此操作将打开“收藏”窗格，可在其中创建、编辑和查看收藏。 我们根据你在 Web 上的行为设计了“收藏”功能。 如果你是购物者、旅行者、教师或学生，那么“收藏”功能可以为你提供帮助。 [了解详细信息](https://blogs.windows.com/msedgedev/2019/12/09/improvements-collections-sync-microsoft-edge/#LuDPRDUDCgdgdOVt.97)。

- 允许从 Microsoft Edge 工具栏中删除“收藏”按钮（从工具栏隐藏）以保持一致性。

- 本地 Active Directory 帐户自动登录将仅针对启用该功能的组织。 如果用户已使用本地 AD 帐户登录，则现在可以注销该帐户。 现在，仅当用户在操作系统上的主帐户是 Microsoft 帐户或 Azure Active Directory 帐户时，才会使用该帐户自动登录。 管理员可以使用 ConfigureOnPremisesAccountAutoSignIn 策略启用本地 AD 帐户的自动登录。

- 应用程序防护。 容器中现已提供扩展支持。

- 添加了一条消息，通知用户当导航到配置为在 Internet Explorer 模式下打开的页面时不会安装 Internet Explorer。

- 使用新功能更新了 Microsoft Edge DevTools 中的 3D 视图工具，可帮助调试 z-index 堆叠上下文。 3D 视图使用颜色和堆叠来显示 DOM（文档对象模型）深度的表示形式，而 z-Index 视图可帮助隔离页面的不同堆叠上下文。 [了解详细信息](https://blogs.windows.com/msedgedev/2020/01/23/debug-z-index-3d-view-edge-devtools/)。

- 已将 F12 Dev 工具本地化为 10 种新语言，因此它们将与其他浏览器中使用的语言匹配。 [了解详细信息](https://blogs.windows.com/msedgedev/2020/02/04/localizing-edge-devtools/)。

- 添加了对 Dolby Vision 播放的支持。 在已启用 Dolby Vision 的 Windows 10 内部版本 17134（2018 年 4 月更新）中，网站可以显示 Dolby Vision 内容。 了解如何从 [Netflix](https://help.netflix.com/en/node/42384) 启用 Dolby Vision。

- Microsoft Edge 现在可以识别并删除重复收藏夹，以及合并具有相同名称的文件夹。 若要访问该工具，请单击浏览器工具栏上的星星图标，然后选择“删除重复的收藏夹”。  你将能够确认更改，并且对收藏夹所做的任何更新都将在设备之间同步。

- 我们从用户那里得知，很难区分采用深色主题的普通浏览窗口与 InPrivate 窗口，因为这两个窗口框架都是深色的。 右上角的新 InPrivate 纯蓝色药丸图标有助于确保用户正在浏览 InPrivate。

- 在正确的浏览器配置文件中打开外部链接。 从 *edge://settings/multiProfileSettings* 中，为在外部应用中打开的链接选择默认配置文件。

- 添加了一条警告，以警告先前使用其他帐户登录后使用某个帐户登录浏览器配置文件的用户。 这将有助于防止意外数据合并。

- 如果你的 Microsoft 帐户中保存了支付卡，则可以在填写支付方式时在 Microsoft Edge 中使用它们。 你的 Microsoft 帐户中的卡片将在桌面设备之间同步，并且在进行双因素身份验证（CVC 代码和你的 Microsoft 标识）之后，将与网站共享完整详细信息。为了进一步的方便，你可以选择在身份验证期间将卡片的副本安全地保存在设备上。

- “行焦点”功能专为希望在阅读时专注于部分内容的用户而设计。 它可让用户一次将注意力集中在 1、3 或 5 行上，并使页面的其余部分变暗，以便用户在阅读时不会分散注意力。 用户可通过触摸或箭头键进行滚动，并且焦点将相应地移动。

- Microsoft Edge 现在已与 Windows 平台 8.1 及更高版本上的 Windows 拼写器相集成。 此集成可提供更强大的语言支持，访问更多的语言词典，还可让用户使用 Windows 自定义词典。 在操作系统语言设置中添加语言并在 Microsoft Edge 设置中启用语言拼写检查切换后，用户无需执行其他操作。

- 使用 Microsoft Edge 打开 PDF 文档后，用户现在可以创建突出显示、更改颜色和删除突出显示。 这有助于以后参考文档的重要部分并进行协作。

- 如果加载已针对 Web 优化的长篇 PDF 文档，则在加载文档的其余部分时，将更快地并行加载用户正在查看的页面。

- 现在，只需按 F9 键就即可更轻松地启动网站的沉浸式阅读器。

- 现在，可使用键盘快捷方式 (Ctrl + Shift + U) 更轻松地启动“大声朗读”。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

添加了 12 个新策略。 从 [Microsoft Edge 企业登录页面](https://aka.ms/EdgeEnterprise)下载更新的管理模板。 已添加以下新策略。

- [AmbientAuthenticationInPrivateModesEnabled](./microsoft-edge-policies.md#ambientauthenticationinprivatemodesenabled) - 为 InPrivate 和来宾配置文件启用环境身份验证。 
- [AudioSandboxEnabled](./microsoft-edge-policies.md#audiosandboxenabled) - 允许运行音频沙盒。
- [ForceLegacyDefaultReferrerPolicy](./microsoft-edge-policies.md#forcelegacydefaultreferrerpolicy) - 使用 no-referrer-when-downgrade 的默认引荐策略。
- [GloballyScopeHTTPAuthCacheEnabled](./microsoft-edge-policies.md#globallyscopehttpauthcacheenabled) - 启用全局范围的 HTTP 身份验证缓存。
- [ImportExtensions](./microsoft-edge-policies.md#importextensions) - 允许导入扩展。
- [ImportCookies](./microsoft-edge-policies.md#importcookies) - 允许导入 Cookie。
- [ImportShortcuts](./microsoft-edge-policies.md#importshortcuts) - 允许导入快捷方式。
- [InternetExplorerIntegrationSiteRedirect](./microsoft-edge-policies.md#internetexplorerintegrationsiteredirect) - 指定从 Internet Explorer 模式页面到未配置的网站的“页内”导航行为方式。
- [OmniboxMSBProviderEnabled](./microsoft-edge-policies.md) - 在多功能框中启用适用于企业的 Microsoft 搜索提供程序。
- [StricterMixedContentTreatmentEnabled](./microsoft-edge-policies.md#strictermixedcontenttreatmentenabled) - 对混合内容进行更严格的处理。
- [TLS13HardeningForLocalAnchorsEnabled](./microsoft-edge-policies.md#tls13hardeningforlocalanchorsenabled) - 为本地信任密钥启用 TLS 1.3 安全功能。
- [ConfigureOnPremisesAccountAutoSignIn](./microsoft-edge-policies.md#configureonpremisesaccountautosignin) - 当没有 Azure AD 域帐户时配置 Active Directory 域帐户的自动登录。

#### <a name="deprecated-policies"></a>已弃用的策略

以下策略在此版本中继续有效。 在未来的版本中，它们将被“弃用”。

- [WebComponentsV0Enabled](./microsoft-edge-policies.md#webcomponentsv0enabled) - 重新启用 Web 组件 v0 API 至 M84。
- [WebDriverOverridesIncompatiblePolicies](./microsoft-edge-policies.md#webdriveroverridesincompatiblepolicies) - 允许 WebDriver 覆盖不兼容策略。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)