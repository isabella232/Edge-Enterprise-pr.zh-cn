---
title: Microsoft Edge Beta 渠道发行说明
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 03/03/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Beta 渠道发行说明
ms.openlocfilehash: e2a2933e7edf3456bcb33e70d6db7a36ab72aa07
ms.sourcegitcommit: 6603dc23d8e7ff46df76bc6aa48b93a0b435fe7d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385625"
---
# <a name="release-notes-for-microsoft-edge-beta-channel"></a>Microsoft Edge Beta 渠道的发行说明

本发行说明提供有关 Microsoft Edge Beta 渠道中包含的新功能和非安全更新的信息。 此处提供了这些发行说明的存档 [版本](microsoft-edge-relnote-archive-beta-channel.md)。

## <a name="version-89077445-march-3"></a>版本 89.0.774.45：3 月 3 日

修复了各种错误和性能问题。

## <a name="version-89077439-february-26"></a>版本 89.0.774.39：2 月 26 日

修复了各种错误和性能问题。

## <a name="version-89077434-february-22"></a>版本 89.0.774.34：2 月 22 日

修复了各种错误和性能问题。

## <a name="version-89077427-february-12"></a>版本 89.0.774.27：2 月 12 日

修复了各种错误和性能问题。

## <a name="version-89077423-february-8"></a>版本 89.0.774.23：2 月 8 日

修复了各种错误和性能问题。
<!-- begin major 89 -->
## <a name="version-89077418-february-3"></a>版本 89.0.774.18：2 月 3 日

### <a name="feature-updates"></a>功能更新

- **展台模式支持其他锁定功能**。 从 Microsoft Edge 版本 89 开始，我们在展台模式下添加了其他锁定功能，使客户能够在高效和更安全的体验中完成工作。 [了解详细信息](microsoft-edge-configure-kiosk-mode.md#kiosk-mode-supported-features)。

- **Enterprise Mode Site List Manager 工具将在浏览器中通过 *edge://compat* 页提供**。 可以使用此工具在 Microsoft Edge 上为 Internet Explorer 模式创建、编辑和导出站点列表 XML。 可以根据需要通过组策略启用对此工具的访问。 [了解详情](https://docs.microsoft.com/deployedge/edge-ie-mode-site-list-manager)。

- **使用休眠选项卡提高浏览器性能**。 休眠选项卡通过将非活动选项卡置于睡眠状态以释放系统资源（如内存和 CPU）来提升浏览器性能，以便活动选项卡或其他应用程序可以使用它们。 用户可以阻止网站进入睡眠状态，并配置非活动选项卡进入睡眠状态之前的时间长度。 若要使用户保持其流，还有一些[启发性方法](https://techcommunity.microsoft.com/t5/articles/sleeping-tabs-faq/m-p/1705434)可阻止某些网站进入睡眠状态，例如 Intranet 网站。 可以使用组策略管理此功能。

  > [!NOTE]
  > “使用休眠选项卡提高浏览器性能”是 2 月 3 日主要版本 89.0.774.18 发行说明的更新。

- **手动重置云中的 Microsoft Edge 同步数据**。 我们正在引入一种从产品内重置 Microsoft Edge 同步数据的方法。 这确保从 Microsoft 服务中清除数据，同时也解决了以前需要支持票证的某些产品问题。

- **PDF 文档中文本选择体验的改善**。 从版本 89 开始，用户将开始在 Microsoft Edge 中打开的 PDF 文档中获得更流畅、一致的文本选择体验。

- **可永久取消“禁用开发人员模式扩展”警告**。 从 Microsoft Edge 版本 89 开始，可以通过选择“不再显示此消息”选项来关闭“禁用开发人员模式扩展”警告。

- **从工具栏管理扩展**。 工具栏上的新扩展菜单允许你轻松隐藏/锁定扩展。 管理扩展和查找新扩展的快速链接将使你轻松找到新扩展和管理现有扩展。

- **支持在地址栏、历史记录搜索页面和历史记录中心上进行自然语言搜索**。 从 Microsoft Edge 版本 89 开始，使用地址栏、历史页面和历史中心上的自然语言搜索使查找文章/网站更容易。 除了标题/URL 关键字匹配之外，用户还可以搜索以前查看过的页面内容/描述/时间（例如“上周的蛋糕食谱”）。

- **工作效率：**

  - “自动填充”现在支持“出生日期”字段。 现在，Microsoft Edge 通过自动填充地址、姓名、电话号码等数据，帮助你在线填写表单和创建帐户时节省时间和精力。从 Microsoft Edge 版本 89 开始，我们将添加对另一可保存及自动填充字段的支持—出生日期。 可以随时在个人资料设置中查看、编辑和删除此信息。
  - 扩展自动填充建议以包含剪贴板中的内容。 选择要显示为自动填充建议的配置文件/地址字段（例如，电话、电子邮件、邮政编码、城市、州等）时，剪贴板内容将被分析。

- **支持阻止自动播放视频**。 从 Microsoft Edge 版本 89 开始，用户可以选择阻止媒体自动播放。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

- [BrowsingDataLifetime](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#browsingdatalifetime) - 浏览数据生存期设置
- [MAMEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#mamenabled) - 移动应用管理已启用
- [DefinePreferredLanguages](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#definepreferredlanguages) - 定义网站应在网站支持该语言时显示的首选语言的有序列表
- [ShowRecommendationsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#showrecommendationsenabled) - 允许来自 Microsoft Edge 的建议和促销通知
- [PrintingAllowedBackgroundGraphicsModes](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#printingallowedbackgroundgraphicsmodes) - 限制背景图形打印模式
- [PrintingBackgroundGraphicsDefault](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#printingbackgroundgraphicsdefault)- 默认背景图形打印模式
- [SmartActionsBlockList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartactionsblocklist)- 阻止对服务列表执行智能操作

#### <a name="obsoleted-policies"></a>已过时的策略

- [ForceLegacyDefaultReferrerPolicy](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcelegacydefaultreferrerpolicy) - 使用 no-referrer-when-downgrade 的默认引荐策略
- [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled)：启用使用情况和故障相关数据报告
- [SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices)：发送站点信息以改进 Microsoft 服务
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

- **结束会话的展台模式选项**。 “结束会话”按钮现在在展台模式公共浏览体验中可用。 此功能可确保在关闭 Microsoft Edge 时删除浏览器数据和设置。 详细了解展台模式功能和路线图，配置 [Microsoft Edge 展台模式](https://docs.microsoft.com/deployedge/microsoft-edge-configure-kiosk-mode)。

- **安全和隐私：**

  - 如果在联机泄露中发现用户的密码，则将生成警报。 将用户密码与已知的已破解的存储库进行核对，如果发现匹配，就会向用户发出警报。 为了确保安全和隐私，当用户密码在与已泄露的凭证数据库进行核对时，会进行哈希处理和加密。
  - 自动升级混合内容。 通过 HTTPS 传递的安全页面可能包含通过非安全 HTTP 提供的引用图像。 为了改进 Microsoft Edge 88 中的隐私和安全性，将改为通过 HTTPS 检索这些图像。 如果图像无法通过 HTTPS 使用，将不会加载它。
  - 按网站和最近活动查看网站权限。 从 Microsoft Edge 88 开始，用户将能够更轻松地管理网站权限。 他们将能够按网站查看权限，而不只是按权限类型查看权限。 此外，我们添加了一个最近的活动部分，它向用户显示其网站权限的所有最近更改。
  - 增加了浏览器 Cookie 的控件。 从 Microsoft Edge 88 开始，用户可以删除第三方 Cookie，而不会影响第一方 Cookie。 用户还可以按第一方或第三方筛选其 Cookie，并按名称、Cookie 数量以及存储和上次修改的数据量进行排序。

- **性能：**

  - 使用休眠选项卡提高浏览器性能。 休眠选项卡通过将非活动选项卡置于睡眠状态以释放系统资源（如内存和 CPU）来提升浏览器性能，以便活动选项卡或其他应用程序可以使用它们。 用户可以阻止网站进入睡眠状态，并配置非活动选项卡进入睡眠状态之前的时间长度。 若要使用户保持其流，还有一些启发性方法可阻止某些网站进入睡眠状态，例如 Intranet 网站。 此功能仅限于一组启用了实验的随机选择的用户。 我们计划默认使用 Microsoft Edge 版本 89 启用休眠选项卡功能。 可以使用组策略管理此功能。
  - 通过启动提升提高 Microsoft Edge 启动速度。 为了提高 Microsoft Edge 启动速度，我们开发了一个名为启动提升的功能。 启动提升使 Microsoft Edge 能够在后台运行，从而加快 Microsoft Edge 启动速度。 注意：此功能仅限于随机选择的一组已启用实验的用户。 这些用户向功能团队提供反馈。

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

- [BlockExternalExtensions](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#blockexternalextensions) - 阻止安装外部扩展。
- [InternetExplorerIntegrationLocalFileAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalfileallowed) - 允许在 Internet Explorer 模式下启动本地文件。
- [InternetExplorerIntegrationLocalFileExtensionAllowList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalfileextensionallowlist) - 在 Internet Explorer 文件扩展名允许列表中打开本地文件。
- [InternetExplorerIntegrationLocalFileShowContextMenu](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalfileshowcontextmenu) - 显示上下文菜单以在 Internet Explorer 链接。
- [IntranetRedirectBehavior](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#intranetredirectbehavior) - Intranet 重定向行为。
- [PrinterTypeDenyList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#printertypedenylist) - 禁用拒绝列表上的打印机类型。
- [ShowMicrosoftRewards](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#showmicrosoftrewards) - 显示 Microsoft 奖励体验。
- [SleepingTabsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sleepingtabsenabled) - 配置睡眠选项卡。
- [TimeoutTabsTimeout](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sleepingtabstimeout) - 为休眠选项卡设置后台选项卡不活动超时。
- [SleepingTabsBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sleepingtabsblockedforurls) - 阻止特定网站上休眠的选项卡。
- [StartupBoostEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#startupboostenabled) - 启用启动增强。
- [UpdatePolicyOverride](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#updatepolicyoverride) - 指定 Microsoft Edge 更新如何处理来自 Microsoft Edge 的可用更新。
- [VerticalTabsAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#verticaltabsallowed) - 为浏览器侧面的选项卡配置垂直布局的可用性。
- [WebRtcAllowLegacyTLSProtocols](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webrtcallowlegacytlsprotocols) - 允许在 WebRTC 中降级旧版 TLS/DTLS。

#### <a name="deprecated-policies"></a>已弃用的策略

以下策略已弃用。

- [ProactiveAuthEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proactiveauthenabled) - 启用主动身份验证。
- [ProxyBypassList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxybypasslist) - 配置代理绕过规则。
- [ProxyMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxymode) - 配置代理服务器设置。
- [ProxyPacUrl](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxypacurl) - 设置代理 .pac 文件 URL。
- [ProxyServer](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#proxyserver) - 配置代理服务器的地址或 URL。
- [WebDriverOverridesIncompatiblePolicies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webdriveroverridesincompatiblepolicies) - 允许 WebDriver 覆盖不兼容的策略。

#### <a name="obsoleted-policies"></a>已过时的策略

以下策略已过时。

- [DefaultPluginsSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultpluginssetting) - 默认 Adobe Flash 设置。
- [PluginsAllowedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsallowedforurls) - 允许特定网站上使用 Adobe Flash 插件。
- [PluginsBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#pluginsblockedforurls) - 阻止特定网站上 Adobe Flash 插件。
- [RunAllFlashInAllowMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#runallflashinallowmode) - 将 Adobe Flash 内容设置扩展到所有内容。

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

- **已启用展台模式隐私功能**。 从 Microsoft Edge 87版本开始，将启用帮助企业实现用户数据隐私的展台模式功能。 这些功能将启用以下体验，例如，在退出时清除用户数据、删除已下载的文件，以及在指定的空闲时间后重置配置的启动体验。 深入了解如何 [配置 Microsoft Edge 的展台模式](https://docs.microsoft.com/deployedge/microsoft-edge-configure-kiosk-mode)
- **在默认情况下启用 ClickOnce 部署**。 Microsoft Edge 87 中默认启用 ClickOnce，这可减少企业部署软件的障碍，并更好地与 Microsoft Edge 旧版浏览器行为保持一致。 从 Microsoft Edge 87 开始，ClickOnceEnabled 策略的“未配置”状态将反映新的默认已启用 ClickOnce 状态（与先前默认“已禁用”状态相比）。
- **企业新选项卡页面（NTP）将生产力与可定制的、与工作相关的源内容整合在一起**。 企业 NTP 将我们提供给用工作或学校账户登录的用户 Office 365 生产率页面与与个性化的、与工作相关的公司和行业信息源融合在一起，并将这些信息源组织在单个页面中。 用户将能够识别熟悉的 Office 365 内容和由 Bing 提供支持的 Microsoft 搜索商业版。 此外，他们可以轻松地翻转到一个可自定义的 "我的信息源"，其中包含与用户、其公司或行业相关的内容和模块，以及组织所提供的其他源的选择。 [了解详细信息](https://docs.microsoft.com/microsoft-365/admin/manage/manage-industry-news?view=o365-worldwide&preserve-view=true)。

- **隐私和安全：**

  - 支持策略配置网站的TLS令牌绑定。 TLS令牌绑定有助于防止令牌窃取攻击，以确保无法从初始设置的设备以外的设备上重新使用cookie。 使用 TLS 令牌绑定需要设置 [AllowTokenBindingForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowtokenbindingforurls) 策略，并要求列出的网站支持该功能。

- ** 键盘支持对PDF文件的高亮显示**。 用户可使用其键盘键来突出显示 PDF 中的任何文本。

- **打印：**

  - 双面打印时选择翻转的是哪一面。 用户在双面打印时，可以选择在纸张的长边或短边进行翻转。
  - 选择企业的打印光栅化模式。 控制 Microsoft Edge 打印到 Windows 上的非 PostScript 打印机的方式。 有时，在非PostScript打印机上的打印作业需要进行光栅化才能正确打印。 打印选项有 “完整” 和 “快速”。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

增加了十项新政策。 从 [Microsoft Edge 企业登录页面](https://www.microsoft.com/edge/business/download)下载更新的管理模板。 已添加以下新策略。

- [ConfigureFriendlyURLFormat](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configurefriendlyurlformat) - 配置从 Microsoft Edge 复制的 Url 的默认粘贴格式，并确定用户是否可以使用其他格式。
- [EdgeShoppingAssistantEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#edgeshoppingassistantenabled) - 已启用 Microsoft Edge 中购物。
- [HideInternetExplorerRedirectUXForIncompatibleSitesEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#hideinternetexplorerredirectuxforincompatiblesitesenabled) - 隐藏Microsoft Edge上的一次性重定向对话框和横幅。
- [KioskAddressBarEditingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) - 配置地址栏编辑，实现展台模式的公共浏览体验。
- [KioskDeleteDownloadsOnExit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit) - 删除 Microsoft Edge 关闭时作为展台会话的一部分下载的文件。
- [PasswordRevealEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#passwordrevealenabled) - 启用密码展示显示按钮。
- [RedirectSitesFromInternetExplorerPreventBHOInstall](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#redirectsitesfrominternetexplorerpreventbhoinstall) - 阻止安装BHO，将不兼容的网站从Internet Explorer重定向到Microsoft Edge。
- [RedirectSitesFromInternetExplorerRedirectMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#redirectsitesfrominternetexplorerredirectmode) - 将不兼容的网站从Internet Explorer重定向到Microsoft Edge。
- [SpeechRecognitionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#speechrecognitionenabled) - 配置语音识别。
- [WebCaptureEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webcaptureenabled) - 在Microsoft Edge中启用网络捕获功能。

#### <a name="deprecated-policy"></a>已弃用政策

[NewTabPageSetFeedType](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype) - 配置 Microsoft Edge 的新选项卡页面体验。

#### <a name="obsoleted-policy"></a>已过时的策略

[EnableDeprecatedWebPlatformFeatures](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enabledeprecatedwebplatformfeatures) - 在有限的时间内重新启用已超过限定时间的 web 平台功能。

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

<!--- Archived to version 86.0.622.11: September 9 ---->
<!--- Archived to version 85.0.564.18: July 28 ---->

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
