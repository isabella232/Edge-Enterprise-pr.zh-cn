---
title: Microsoft Edge 稳定渠道的存档发行说明
ms.author: leahtu
author: leahmsft
manager: srugh
ms.date: 04/28/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 稳定渠道的存档发行说明
ms.openlocfilehash: 9d4efe64eec64e94f5b67c2f4daa317c4752919c
ms.sourcegitcommit: 592f6e40b13e28af588473b2a75c3ae697e5db2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2022
ms.locfileid: "12505435"
---
# <a name="archived-release-notes-for-microsoft-edge-stable-channel"></a>Microsoft Edge 稳定渠道的存档发行说明

这些发行说明提供有关 Microsoft Edge Stable 渠道中包含的新功能和非安全更新的信息。 [此处](microsoft-edge-relnotes-security.md)列出所有安全更新。

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

## <a name="version-960105429-november-19"></a>版本 96.0.1054.29：11 月 19 日

[此处](/deployedge/microsoft-edge-relnotes-security#november-19-2021) 列出了稳定频道的安全更新。

### <a name="feature-updates"></a>功能更新

- **公共预览版中适用于 IE 模式的云站点列表管理。** 通过云站点列表管理，你可以在云中管理 IE 模式的站点列表，而无需本地基础结构来托管组织的站点列表。 可以使用Microsoft 365 管理中心的Microsoft Edge站点列表体验访问云站点列表管理功能。 若要了解详细信息，请参阅 [适用于 IE 模式的云站点列表管理 (公共预览) ](./edge-ie-mode-cloud-site-list-mgmt.md) 一文。
  
- **改进了 IE 模式与新式浏览器之间的交互。** 从此版本的Microsoft Edge开始，Microsoft Edge和 Internet Explorer 模式之间的导航将包括表单数据和其他 HTTP 标头。 引用器标头、发布数据、表单数据和请求方法将在两种体验中正确转发。 可以使用 InternetExplorerIntegrationComplexNavDataTypes 策略指定应包含哪些数据类型。 有关详细信息，请参阅此常见问题解答：[我的应用程序需要在 IE 模式和Microsoft Edge之间传输 POST 数据。是否支持此功能？](./edge-ie-mode-faq.md#my-application-requires-transferring-post-data-between-ie-mode-and-microsoft-edge-is-this-supported)

- **使用 WSUS 更新 Microsoft Edge WebWiew2。** 使用 Windows Server Update Services (WSUS) 更新Microsoft Edge的 IT 管理员还可以使用 WSUS 更新 Microsoft Edge WebView2。 此功能使管理员可以更轻松地为脱机设备提供服务。

- **服务器的 WSUS 更新。** Microsoft Edge通道 (稳定、Beta 和开发人员) 的 WSUS 和目录更新现在将应用于已安装Microsoft Edge的Windows服务器 SKU，包括 Windows Server 2022。 有关如何为Microsoft Edge配置 WSUS 更新的详细信息，请参阅[更新Microsoft Edge](/mem/configmgr/apps/deploy-use/deploy-edge)。

- **Microsoft Edge自动启动协议组件。** Microsoft Edge 96 引入了 AutoLaunch 协议[组件](https://textslashplain.com/2019/07/16/updating-browsers-quickly-flags-respins-and-components/)，其中包含自动允许或阻止方案源字典的列表。 这可保护客户免受危险方案 (例如，使用 0 天) 的协议处理程序，同时消除来自已知安全配对的提示 (例如，Teams网站可以打开Teams客户端应用) 。 如果出于某种原因，不希望Microsoft Edge阻止易受攻击的协议处理程序并允许已知安全配对，请在 *edge://settings/content/applicationLinks* 中使用切换，或将 [AutoLaunchProtocolsComponentEnabled 策略](/deployedge/microsoft-edge-policies#autolaunchprotocolscomponentenabled)设置为 False。

- **直接通过协议链接启动渐进式 Web 应用 (PWA) 。** 让已安装的 PWA 处理使用特定协议进行更集成体验的链接。

- **在浏览器中快速查看Office文件。** 用户现在可以在浏览器中直接浏览Microsoft Edge时查看Office文件，包括文档、电子表格和演示文稿，而无需下载文件，然后在其他应用程序中打开它。 对于托管在OneDrive或SharePoint上的Office文件，文件打开体验中不会有任何更改。
  
- **PDF 上的任意格式突出显示。** 通过添加自由格式荧光笔，PDF 查看和标记体验得到改进。 可以突出显示你无权访问的 PDF 中的各节，以及扫描的文档。

- **硬件强制实施的堆栈保护。** Microsoft Edge将开始支持更安全的浏览模式，该模式在受支持的硬件 (Intel 11 Gen 上对浏览器进程使用依赖硬件的控制流。 或 AMD Zen 3) 。 注意：由于这是受控功能推出，因此你可能没有注意到在所有设备上都启用了此功能。 可以通过使用组策略 (IFEO) 操作映像文件执行选项来启用或禁用硬件强制实施的 Stack Protection。

- **用于键入网站的新警告对话框。** 浏览器会在某些包含 URL 的站点上显示警告，这些 URL 看起来与其他网站非常相似。 此 UI 使用客户端启发式方法警告用户可能欺骗热门网站的网站。 有关详细信息，请参阅[什么是拼写错误？](https://support.microsoft.com/topic/what-is-typosquatting-54a18872-8459-4d47-b3e3-d84d9a362eb0)
  
- **在沉浸式阅读器中添加到微型工具栏的字典。**  我们将字典功能添加到微型工具栏，以帮助你阅读和研究。 在沉浸式阅读器体验中，你将能够更快、更轻松地查找单词的拼写和定义。
  
- **了解如何解决数学求解器的数学问题。** 我们很高兴地宣布，你可以使用数学求解器在Microsoft Edge，以获得各种数学概念的帮助。 这些概念的范围从基本算术和二次公式到三角和微积分。 数学求解器可让你拍摄手写或打印数学问题的图片，然后提供一个即时解决方案，其中包含分步说明，帮助你了解如何在没有帮助的情况下访问解决方案。 数学求解器还附带了一个数学键盘，可用于轻松键入数学问题。 此键盘无需在传统键盘周围搜索即可找到所需的数学字符。 解决问题后，Math Solver 提供了继续学习测验、工作表和视频教程的选项。

- **拆分对 WebRTC 的隧道 VPN 支持。** 使企业客户能够从 VPN 拆分隧道中获益，以便在Microsoft Edge上实现对等流量。 可以使用 [WebRtcRespectOsRoutingTableEnabled](/deployedge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) 策略启用此功能。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

- [ApplicationGuardUploadBlockingEnabled](/DeployEdge/microsoft-edge-policies#applicationguarduploadblockingenabled) - 防止在 Application Guard 中上传文件
- [AudioProcessHighPriorityEnabled](/DeployEdge/microsoft-edge-policies#audioprocesshighpriorityenabled) - 允许音频进程在Windows上以高于正常状态的优先级运行
- [AutoLaunchProtocolsComponentEnabled](/DeployEdge/microsoft-edge-policies#autolaunchprotocolscomponentenabled) - 已启用 AutoLaunch 协议组件
- [EfficiencyMode](/DeployEdge/microsoft-edge-policies#efficiencymode) - 配置效率模式何时应处于活动状态
- [ForceSyncTypes](/DeployEdge/microsoft-edge-policies#forcesynctypes) - 配置用于同步的类型列表
- [InternetExplorerIntegrationComplexNavDataTypes](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationcomplexnavdatatypes) - 配置在进入或退出 Internet Explorer 模式时是否发送表单数据和 HTTP 标头
- [InternetExplorerModeToolbarButtonEnabled](/DeployEdge/microsoft-edge-policies#internetexplorermodetoolbarbuttonenabled) - 在工具栏的 Internet Explorer 模式下显示重载按钮
- [PrintPostScriptMode](/DeployEdge/microsoft-edge-policies#printpostscriptmode) - 打印PostScript模式
- [PrintRasterizePdfDpi](/DeployEdge/microsoft-edge-policies#printrasterizepdfdpi) - 打印光栅化 PDF DPI
- [RendererAppContainerEnabled](/DeployEdge/microsoft-edge-policies#rendererappcontainerenabled) - 在应用容器中启用呈现器
- [SharedLinksEnabled](/DeployEdge/microsoft-edge-policies#sharedlinksenabled) - 显示从历史记录中的Microsoft 365应用共享的链接
- [TyposquattingCheckerEnabled](/DeployEdge/microsoft-edge-policies#typosquattingcheckerenabled) - 配置 Edge TyposquattingChecker

## <a name="version-950102053-november-12"></a>版本 95.0.1020.53：11 月 12 日

修复了各种 bug 和性能问题。

## <a name="version-950102044-november-4"></a>版本 95.0.1020.44：11 月 4 日

修复了各种 bug 和性能问题。

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

## <a name="version-92090255-july-22"></a>版本 92.0.902.55：7 月 22 日

[此处](/deployedge/microsoft-edge-relnotes-security#july-22-2021)列出了稳定频道的安全更新。

### <a name="feature-updates"></a>功能更新

**用户可以轻松地在 Microsoft Edge 上进入 Internet Explorer 模式**。 从 Microsoft Edge 版本 92 开始，用户可以在 Microsoft Edge 上以 Internet Explorer 模式重新加载站点，而不是等待站点在 Enterprise 模式站点列表中被配置的同时依赖独立 IE 11 应用程序。 系统将提示用户将网站添加到其本地站点列表，以便在 Microsoft Edge 中导航到的相同页面将在接下来 30 天内自动以 IE 模式呈现。 可以使用 [InternetExplorerIntegrationReloadInIEModeAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) 策略配置此体验，并允许访问 IE 模式入口点，以及允许将站点添加到本地站点列表。 可以使用 [InternetExplorerIntegrationLocalSiteListExpirationDays](/deployedge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) 策略调整将站点保留在本地站点列表中的天数。 请注意，对于端到端体验，Windows 10 版本 1909 需要 KB5003698 或更高版本; Windows 10 版本 2004、Windows 10 版本 20H2 或 Windows 10 版本 21H1 需要 KB5003690 或更高版本。 有关详细信息，请参阅 [ IE 模式下的本地站点列表](/deployedge/edge-ie-mode-local-site-list)。

**MHTML 文件将默认以 Internet Explorer 模式打开**。 从 Microsoft Edge 92 稳定版开始，MHTML 文件类型将在 Microsoft Edge 上以 Internet Explorer 模式自动打开，而不是在 Internet Explorer (IE11) 打开。 在用浏览器查看 Outlook 电子邮件时会经常遇到这种情况。 此更改仅在 IE11 是此文件类型的默认处理程序时发生。 如果想要更改此设置，可以在安装稳定版本 92 更新之前使用[此指南](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)。

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
>此更新包含 [CVE-2021-30551](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30551) 的修补程序，Chromium 团队已将其报告为具有外围攻击。 有关详细信息，请参阅 [安全更新指南](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002)。

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

- [ProactiveAuthEnabled](./microsoft-edge-policies.md#proactiveauthenabled) - 启用主动身份验证。

## <a name="version-90081866-may-20"></a>版本 90.0.818.66：5 月 20 日

修复了各种 bug 和性能问题。

## <a name="version-90081862-may-13"></a>版本 90.0.818.62：5 月 13 日

[此处](/deployedge/microsoft-edge-relnotes-security#may-13-2021) 列出了稳定频道的安全更新。

## <a name="version-90081856-may-6"></a>版本 90.0.818.56：5 月 6 日

修复了各种 bug 和性能问题。

## <a name="version-90081851-april-29"></a>版本 90.0.818.51：4 月 29 日

[此处](/deployedge/microsoft-edge-relnotes-security#april-29-2021) 列出了稳定频道的安全更新。

## <a name="version-90081849-april-26"></a>版本 90.0.818.49：4 月 26 日

修复了各种 bug 和性能问题。

## <a name="version-90081846-april-22"></a>版本 90.0.818.46：4 月 22 日 ##

[此处](/deployedge/microsoft-edge-relnotes-security#april-22-2021) 列出了稳定频道的安全更新。

## <a name="version-90081842-april-19"></a>版本 90.0.818.42：4 月 19 日

修复了各种 bug 和性能问题。

## <a name="version-90081841-april-16"></a>版本 90.0.818.41：4 月 16 日 ##

> [!Important]
>此次更新包含 [CVE-2021-21224](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21224) 的修复程序，Chromium 团队已报告该程序存在在野攻击。 有关详细信息，请参阅 [安全更新指南](https://msrc.microsoft.com/update-guide)。

[此处](/deployedge/microsoft-edge-relnotes-security#april-16-2021) 列出了稳定频道的安全更新。

## <a name="version-90081839-april-15"></a>版本 90.0.818.39：4 月 15 日 ##

[此处](/deployedge/microsoft-edge-relnotes-security#april-15-2021) 列出了稳定频道的安全更新。

## <a name="feature-updates"></a>功能更新 ##

-    **单一登录 (SSO) 现已适用于 macOS 上的 Azure Active Directory (Azure AD) 帐户和 Microsoft 帐户 (MSA)。** 现在，已在 macOS 上登录 Microsoft Edge 的用户将自动登录到配置为允许使用工作帐户和 Microsoft 帐户进行单一登录的网站（如 bing.com、office.com、msn.com 和 outlook.com）。

- **展台模式。** 从 Microsoft Edge 版本 90 开始，我们已锁定 UI 打印设置，以仅允许配置的打印机和“打印到 PDF”选项。 我们还在分配的访问权限单应用展台模式中进行了改进，以限制从浏览器启动其他应用程序。 有关展台模式功能的详细信息，请转到 [此处](/deployedge/microsoft-edge-configure-kiosk-mode#kiosk-mode-supported-features)。

- **中断下载** 从 Microsoft Edge 版本 91 开始，如果在未经用户交互的情况下启动对计算机有害的下载，并且 SmartScreen 应用程序信誉检查不支持此下载，则浏览器将自动中断该类型的下载。 用户可能会覆盖并继续下载，方法是右键单击并在下载项上选择“保留”。
企业管理员可以通过以下两个策略之一选择退出此行为：
- [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - 对域上的指定文件类型禁用基于文件类型扩展名的下载警告。有关详细信息，请参阅 [Microsoft Edge 安全下载中断](/deployedge/microsoft-edge-security-downloads-interruptions)

- **打印：**

    - **非 PostScript 打印机的全新打印光栅化模式。** 从 Microsoft Edge 版本 90 开始，管理员可以使用新策略为用户定义打印光栅化模式。 此策略控制 Microsoft Edge 如何在 Windows 上打印到非 PostScript 打印机。 有时，在非 PostScript 打印机上的打印作业需要进行光栅化才能正确打印。 打印选项为“完整”和“快速”。
    
  - **打印的其他页面缩放选项。** 用户现在可在使用其他选项打印网页和 PDF 文档时自定义缩放。 “适应页面”选项可确保网页或文档适合所选“纸张大小”中可用于打印的空间。 “实际大小”选项可确保无论所选“纸张大小”如何，正在打印内容的大小都没有任何变化。

-   **工作效率：**

    -   **自动填充建议扩展为包含剪贴板中的地址字段内容。** 在单击配置文件/地址字段（例如，电话、电子邮件、邮政编码、城市、省/市/县等）将分析剪贴板内容，以显示为自动填充建议。

    -   **即使未检测到表单或字段，用户也可以搜索自动填充建议。** 现在，如果将信息保存在 Microsoft Edge 上，将自动弹出自动填充建议，并帮助你在填写表单时节省时间。 如果自动填充遗漏了表单，或者你希望获取通常不会自动填充的表单（如临时表单）中的数据，可以使用自动填充来搜索信息。

-   **从菜单栏中的浮出控件访问下载。** 下载将显示在右上角，且所有活动下载都位于同一位置。 此菜单很容易消除，以便用户可以继续不间断地浏览，并且可以从工具栏直接监视总体下载进度。 [了解详细信息](https://techcommunity.microsoft.com/t5/articles/introducing-the-new-downloads-experience/m-p/2111551)。

-   **字体呈现的改进。** 从 Microsoft Edge 版本 90 开始，我们改进了文本呈现，以提高清晰度并减少模糊度。 字体呈现改进的一部分将在 Beta 版本 90 中落地，但默认情况下处于禁用状态。

- **儿童模式。** 我们已更新策略，以便在启用策略时，除了家庭安全之外，还将禁用儿童模式功能。 请在 [此处](https://go.microsoft.com/fwlink/?linkid=2146910) 了解儿童模式的详细信息

## <a name="policy-updates"></a>策略更新

## <a name="new-policies"></a>新策略

添加了 8 个新策略。 从 [Microsoft Edge 企业版登录页面](https://www.microsoft.com/edge/business/download) 下载更新的管理模板。 添加了以下新策略：
-   [ApplicationGuardFavoritesSyncEnabled](/DeployEdge/microsoft-edge-policies#applicationguardfavoritessyncenabled) - 已启用应用程序防护收藏夹同步
- [ApplicationGuardTrafficIdentificationEnabled](/DeployEdge/microsoft-edge-policies#applicationguardtrafficidentificationenabled) 应用程序防护流量标识
- [ExplicitlyAllowedNetworkPorts](/DeployEdge/microsoft-edge-policies#explicitlyallowednetworkports) 显式允许的网络端口
- [ImportStartupPageSettings](/DeployEdge/microsoft-edge-policies#importstartuppagesettings) 允许导入启动页设置
- [MathSolverEnabled](/DeployEdge/microsoft-edge-policies#mathsolverenabled) 让用户截取数学问题，并在 Microsoft Edge 中通过分步说明获取解决方案
- [NewTabPageContentEnabled](/DeployEdge/microsoft-edge-policies#newtabpagecontentenabled) 允许新选项卡页上的 Microsoft 新闻内容
- [NewTabPageQuickLinksEnabled](/DeployEdge/microsoft-edge-policies#newtabpagequicklinksenabled) 允许新选项卡页上的快速链接
-   [FetchKeepaliveDurationSecondsOnShutdown](/DeployEdge/microsoft-edge-policies#fetchkeepalivedurationsecondsonshutdown)- 在关闭时提取 keepalive 持续时间
-   [ManagedConfigurationPerOrigin](/DeployEdge/microsoft-edge-policies#managedconfigurationperorigin) - 将网站的托管配置值设置到特定源
-   [PrintRasterizationMode](/DeployEdge/microsoft-edge-policies#printrasterizationmode) - 打印光栅化模式
-   [QuickViewOfficeFilesEnabled](/DeployEdge/microsoft-edge-policies#quickviewofficefilesenabled) - 在 Microsoft Edge 中管理 QuickView Office 文件功能
-   [SSLErrorOverrideAllowedForOrigins](/DeployEdge/microsoft-edge-policies#sslerroroverrideallowedfororigins) - 允许用户从特定源的 HTTPS 警告页面继续操作
-   [WindowOcclusionEnabled](/DeployEdge/microsoft-edge-policies#windowocclusionenabled) - 启用窗口封闭
-   [WindowsHelloForHTTPAuthEnabled](/DeployEdge/microsoft-edge-policies#windowshelloforhttpauthenabled) - 已启用 Windows Hello HTTP 身份验证

## <a name="deprecated-policies"></a>弃用的策略

- [ProactiveAuthEnabled](/DeployEdge/microsoft-edge-policies#proactiveauthenabled) 启用主动身份验证。
-   [NativeWindowOcclusionEnabled](/DeployEdge/microsoft-edge-policies#nativewindowocclusionenabled) - 启用本机窗口封闭
-   [SSLVersionMin](/DeployEdge/microsoft-edge-policies#sslversionmin)- 已启用最低 TLS 版本

## <a name="version-89077477-april-14"></a>版本 89.0.774.77：4 月 14 日

> [!Important]
>此更新包含 [CVE-2021-21206](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21206) 和 [CVE-2021-21220](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21220) 的修补程序，Chromium团队已将其报告为在野外有攻击。  有关详细信息，请参阅 [安全更新指南](https://msrc.microsoft.com/update-guide)。

[此处](/deployedge/microsoft-edge-relnotes-security#april-14-2021) 列出了稳定频道的安全更新。

## <a name="version-89077476-april-12"></a>版本 89.0.774.76：4 月 12 日

修复了各种 bug 和性能问题。

## <a name="version-89077475-april-8"></a>版本 89.0.774.75：4 月 8 日

修复了各种 bug 和性能问题。

## <a name="version-89077468-april-1"></a>版本 89.0.774.68：4 月 1 日

[此处](./microsoft-edge-relnotes-security.md#april-1-2021)列出了稳定频道的安全更新。

## <a name="version-89077463-march-25"></a>版本 89.0.774.63：3 月 25 日

修复了各种 bug 和性能问题。

## <a name="version-89077457-march-18"></a>版本 89.0.774.57：3 月 18 日

修复了各种 bug 和性能问题。

## <a name="version-89077454-march-13"></a>版本 89.0.774.54：3 月 13 日

> [!IMPORTANT]
> 此更新包含已由 Chromium 团队报告用于现实中的 [CVE-2021-21193](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21193)。 有关详细信息，请参阅 [安全更新指南](https://msrc.microsoft.com/update-guide)。

[此处](./microsoft-edge-relnotes-security.md#march-13-2021)列出了稳定频道的安全更新。

## <a name="version-89077450-march-10"></a>版本 89.0.774.50：3 月 10 日

修复了各种错误和性能问题。

## <a name="version-89077448-march-8"></a>版本 89.0.774.48：3 月 8 日

修复了各种错误和性能问题。

<!-- begin major 89 -->

## <a name="version"></a>版本

> [!IMPORTANT]
> 此更新包含 [CVE-2021-21166，Chromium 团队已报告该 CVE-2021-21166](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21166) 具有通配符攻击。 有关详细信息，请参阅 [安全更新指南](https://msrc.microsoft.com/update-guide)。

[此处](./microsoft-edge-relnotes-security.md#march-4-2021)列出了稳定频道的安全更新。

### <a name="resolved-issues"></a>已解决的问题

- **任务栏和"开始"菜单的快捷方式更新和修复：**
  - 右键单击"开始"菜单中的 Microsoft Edge 快捷方式现可正确显示固定时从任务栏中取消固定 Microsoft Edge 的选项。
  - 为了将 Microsoft Edge 固定到任务栏启动包括 [任务栏配置](/windows/configuration/configure-windows-10-taskbar) 时，这不再导致第二个 Microsoft Edge 快捷方式固定到任务栏。
  - 如果用户登录到 Windows，则使用 Windows 漫游配置文件的组织将不再看到任务栏上的空白白色图标代替Microsoft Edge图标。

### <a name="feature-updates"></a>功能更新

- **展台模式支持其他锁定功能**。 从 Microsoft Edge 版本 89 开始，我们在展台模式下添加了其他锁定功能，使客户能够在高效和更安全的体验中完成工作。 [了解详细信息](microsoft-edge-configure-kiosk-mode.md#kiosk-mode-supported-features)。

- **Enterprise Mode Site List Manager 工具将在浏览器中通过 *edge://compat* 页提供**。 可以使用此工具在 Microsoft Edge 上为 Internet Explorer 模式创建、编辑和导出站点列表 XML。 可以根据需要通过组策略启用对此工具的访问。 [了解详情](./edge-ie-mode-site-list-manager.md)。

- **使用休眠选项卡提高浏览器性能**。 休眠选项卡通过将非活动选项卡置于睡眠状态以释放系统资源（如内存和 CPU）来提升浏览器性能，以便活动选项卡或其他应用程序可以使用它们。 用户可以阻止网站进入睡眠状态，并配置非活动选项卡进入睡眠状态之前的时间长度。 若要使用户保持其流，还有一些[启发性方法](https://techcommunity.microsoft.com/t5/articles/sleeping-tabs-faq/m-p/1705434)可阻止某些网站进入睡眠状态，例如 Intranet 网站。 可以使用组策略管理此功能。

- **手动重置云中的 Microsoft Edge 同步数据**。 我们正在引入一种从产品内重置 Microsoft Edge 同步数据的方法。 这确保从 Microsoft 服务中清除数据，同时也解决了以前需要支持票证的某些产品问题。

- **针对具有单个非 Azure AD Microsoft Edge 配置文件的用户的所有 Windows Azure Active Directory (Azure AD) 帐户智能启用单一登录 (SSO)**。  为从此功能受益最大的用户自动启用该设置。 如果用户只有一个 Microsoft Edge 配置文件（不是 Azure AD 或儿童模式），则当 Microsoft Edge 启动时，该设置将自动启用。 如果用户稍后选择使用 Azure AD 帐户登录其他 Microsoft Edge 配置文件，此自动切换功能也将自动关闭。 用户可以依次选择“**设置”>“配置文件”>“配置文件首选项”>“允许使用此配置文件对工作或学校网站进行单一登录**”手动更新此功能的首选项。

- **PDF 文档中文本选择体验的改善**。 从版本 89 开始，用户将开始在 Microsoft Edge 中打开的 PDF 文档中获得更流畅、一致的文本选择体验。

- **自动填充字段现在支持"出生日期"**。 现在，Microsoft Edge 通过自动填充地址、姓名、电话号码等数据，帮助你在线填写表单和创建帐户时节省时间和精力。从 Microsoft Edge 版本 89 开始，我们将添加对另一可保存及自动填充字段的支持—出生日期。 可以随时在个人资料设置中查看、编辑和删除此信息。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

添加了 7 个新策略。 从 [Microsoft Edge 企业登录页面](https://www.microsoft.com/edge/business/download)下载更新的管理模板。 已添加以下新策略。

- [BrowsingDataLifetime](./microsoft-edge-policies.md#browsingdatalifetime) - 浏览数据生存期设置
- [MAMEnabled](./microsoft-edge-policies.md#mamenabled) - 移动应用管理已启用
- [DefinePreferredLanguages](./microsoft-edge-policies.md#definepreferredlanguages) - 定义网站应在网站支持该语言时显示的首选语言的有序列表
- [ShowRecommendationsEnabled](./microsoft-edge-policies.md#showrecommendationsenabled) - 允许来自 Edge 的建议和促销通知
- [PrintingAllowedBackgroundGraphicsModes](./microsoft-edge-policies.md#printingallowedbackgroundgraphicsmodes) - 限制背景图形打印模式
- [PrintingBackgroundGraphicsDefault](./microsoft-edge-policies.md#printingbackgroundgraphicsdefault)- 默认背景图形打印模式
- [SmartActionsBlockList](./microsoft-edge-policies.md#smartactionsblocklist)- 阻止对服务列表执行智能操作

#### <a name="obsoleted-policies"></a>已过时的策略

以下策略已过时。

- [ForceLegacyDefaultReferrerPolicy](./microsoft-edge-policies.md#forcelegacydefaultreferrerpolicy) - 使用 no-referrer-when-downgrade 的默认引荐策略
- [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled)：启用使用情况和故障相关数据报告
- [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices)：发送站点信息以改进 Microsoft 服务

<!-- end major 89 -->

## <a name="version-88070581-february-25"></a>版本 88.0.705.81：2 月 25 日

修复了各种错误和性能问题。

## <a name="version-88070574-february-17"></a>版本 88.0.705.74：2 月 17 日

[此处](./microsoft-edge-relnotes-security.md#february-17-2021)列出了稳定频道的安全更新。

## <a name="version-88070568-february-11"></a>版本 88.0.705.68：2 月 11 日

修复了各种错误和性能问题。

## <a name="version-88070563-february-5"></a>版本 88.0.705.63：2 月 5 日

> [!IMPORTANT]
> 此更新包含已由 Chromium 团队报告的在现实中被利用的 [CVE-2021-21148](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21148)。

[此处](./microsoft-edge-relnotes-security.md#february-5-2021)列出了稳定频道的安全更新。

## <a name="version-88070562-february-4"></a>版本 88.0.705.62：2 月 4 日

[此处](./microsoft-edge-relnotes-security.md#february-4-2021)列出了稳定频道的安全更新。

修复了各种错误和性能问题。

## <a name="version-88070556-january-28"></a>版本 88.0.705.56：1 月 28 日

修复了各种 bug 和性能问题。

## <a name="version-88070553-january-26"></a>版本 88.0.705.53：1 月 26 日

修复了各种 bug 和性能问题。

## <a name="version-88070550-january-21"></a>版本 88.0.705.50：1 月 21 日

[此处](./microsoft-edge-relnotes-security.md#january-21-2021)列出了稳定频道的安全更新。

<!--- begin major 88  --->
### <a name="feature-updates"></a>功能更新

- **弃用：**

  - 弃用对 FTP 协议的支持。 已从 Microsoft Edge 中删除对旧版 FTP 协议的支持。 尝试导航到 FTP 链接将导致浏览器指示操作系统打开外部应用程序以处理 FTP 链接。 或者，IT 管理员可以将 Microsoft Edge 配置为对依赖于 FTP 协议的站点使用 IE 模式。
  - Adobe Flash 支持将被删除。 从 Microsoft Edge Beta 版本 88 开始，Adobe Flash 功能和支持将被删除。 了解更多信息 [：Adobe Flash Player 停止支持更新 - Microsoft Edge 博客 (windows.com) ](https://blogs.windows.com/msedgedev/2020/09/04/update-adobe-flash-end-support/)

- **身份验证：**

  - 单一登录 (SSO) 现在适用于低级别 Windows 上的 Azure Active Directory (Azure AD) 帐户和 Microsoft 帐户 (MSA)。 在低级别 Microsoft Windows (7、8.1) 上登录 Microsoft Edge 的用户现在将自动登录到配置为允许使用工作帐户和 Microsoft 帐户单一登录的网站（例如 bing.com、office.com、msn.com、outlook.com）。<br>注意：如果用户在 Microsoft Edge 88 之前的版本中登录 Microsoft Edge，可能需要注销然后重新登录，以利用此功能。
  
  - 在非 Azure AD Microsoft Edge 配置文件中，在系统上使用任意 Windows Azure Active Directory （Azure AD）帐户登录（SSO）来让网站工作。 对于未使用工作/学校帐户登录的任何配置文件，且不是来宾或专用的配置文件，可以启用此功能，并允许通过该配置文件在操作系统上使用任何登录的工作/学校帐户。 此功能可以在“**设置**” > “**配置文件**” > “**配置文件首选项**” > “**允许使用此配置文件单一登录到工作或学校网站**”中配置。
  
    > [!NOTE]
    > “使用 Microsoft Edge 配置文件单一登录 (SSO) 所有 Windows 账户”是对 1 月 21 日发行说明的一项更新。

- **结束会话的展台模式选项**。 “结束会话”按钮现在在展台模式公共浏览体验中可用。 此功能可确保在关闭 Microsoft Edge 时删除浏览器数据和设置。 详细了解展台模式功能和路线图，配置 [Microsoft Edge 展台模式](./microsoft-edge-configure-kiosk-mode.md)。

- **安全和隐私：**

  - 如果在联机泄露中发现用户的密码，则将生成警报。 将用户密码与已知的已破解的存储库进行核对，如果发现匹配，就会向用户发出警报。 为了确保安全和隐私，当用户密码在与已泄露的凭证数据库进行核对时，会进行哈希处理和加密。
  - 自动升级混合内容。 通过 HTTPS 传递的安全页面可能包含通过非安全 HTTP 提供的引用图像。 为了改进 Microsoft Edge 88 中的隐私和安全性，将改为通过 HTTPS 检索这些图像。 如果图像无法通过 HTTPS 使用，将不会加载它。
  - 按网站和最近活动查看网站权限。 从 Microsoft Edge 88 开始，用户将能够更轻松地管理网站权限。 他们将能够按网站查看权限，而不只是按权限类型查看权限。 此外，我们添加了一个最近的活动部分，它向用户显示其网站权限的所有最近更改。
  - 增加了浏览器 Cookie 的控件。 从 Microsoft Edge 88 开始，用户可以删除第三方 Cookie，而不会影响第一方 Cookie。 用户还可以按第一方或第三方筛选其 Cookie，并按名称、Cookie 数量以及存储和上次修改的数据量进行排序。

- **密码：**

  - 密码生成器。 Microsoft Edge 提供内置强密码生成器，可在注册新帐户或更改现有密码时使用。 只需在密码字段中查找浏览器建议的密码下拉列表，选中密码后，它将自动保存到浏览器并跨设备同步，方便将来使用。
  - 密码监视器。 如果保存到浏览器的任何密码与泄露凭据列表中显示的密码匹配，Microsoft Edge 将通知你并提示你更新密码。 密码监视器将代表你扫描匹配项，并且默认处于启用状态。
  - 编辑密码。 现在可以直接在 Microsoft Edge 设置中编辑保存的密码。 每次在 Microsoft Edge 外部更新密码时，都可以通过编辑“设置”中的已保存条目轻松地将保存的旧密码替换为新密码。 

- **通过启动增强提高 Microsoft Edge 启动速度**。 为了提高 Microsoft Edge 启动速度，我们开发了一个名为启动增强的功能。 启动增强使 Microsoft Edge 能够在后台运行，从而加快 Microsoft Edge 启动速度。 注意：此功能仅限于随机选择的一组已启用实验的用户。 这些用户向功能团队提供反馈。

- **工作效率：**

  - 使用垂直选项卡提高工作效率和多任务。 随着水平选项卡数量的增加，网站标题开始关闭，选项卡控件会随着每个选项卡的缩小而丢失。 这会中断用户工作流，因为他们将花费更多时间查找、切换和管理选项卡，并花费更少的时间处理当前任务。 通过垂直选项卡，用户可以将其选项卡移到一侧，其中垂直对齐的图标和较长的网站标题使快速扫描、标识并切换到要打开的选项卡变得更加简单。
  - 自动填写出生日期字段。 Microsoft Edge 已经通过自动填充用户数据（如地址、姓名、电话号码等）来帮助节省填写表单和联机创建帐户的时间和精力。Microsoft Edge 现在支持用户可保存并自动填充的出生日期字段。 用户可以随时在个人资料设置中查看、编辑和删除此信息。
  - 对历史记录中最近关闭的改进。 最近关闭现在使过去的任何浏览会话（而不只是上一个会话）中保留最后 25 个选项卡和窗口。 用户可以在新的历史记录体验中选择"最近关闭"以查看所有打开的选项卡。
  - 默认情况下启用"一天一览"功能。 从 Microsoft Edge 版本 88 开始，信息工作者可以从其新建选项卡页 (NTP) 的智能生产力功能中受益。 Microsoft Edge 87 用户还将在 Microsoft Edge 88 发布后的 2 周内体验这些功能。 我们为用户提供使用工作或学校帐户登录的个性化设置以及由 M365 Graph 支持的相关内容。 用户可以快速扫描其"一天一眼"模块，轻松跟踪其会议和最近工作，并快速启动他们想要使用的应用程序。

- **历史记录和打开的选项卡同步**。历史记录和打开的选项卡同步现在可供用户享受。 启用这些功能将有助于用户通过制作浏览历史记录并打开所有同步设备上可用的选项卡，从他们离开的地方继续操作。 我们更新了同步和浏览器历史记录策略，因此现在用户可以使用 Microsoft Edge 跨任何设备进行连接并提高工作效率。 [了解详细信息](https://blogs.windows.com/windowsexperience/2021/01/21/this-year-lets-resolve-to-make-the-most-of-our-time-online-and-better-protect-ourselves-from-online-threats/)。

- **PDF：**

  - 在书籍视图中显示 PDF 文档（两页）。 从 Microsoft Edge 版本 88 开始，用户可以在单页或两页书籍视图中查看 PDF 文档。 若要更改视图，请单击工具栏 中的“**页面视图**”按钮。
  - 定位的文本注释支持 PDF 文件。 从 Microsoft Edge 版本 87 开始，用户可以在 PDF 文件的任何文本条上添加键入的文本注释。

- **字体：**

  - 浏览器图标将更新为 Fluent 设计系统。 作为在浏览器中持续处理 Fluent Design 的一部分，我们进行了更改，使图标与新的 Microsoft 图标系统更加一致。 这些更改将影响我们的许多高接触用户界面，包括选项卡、地址栏，以及各种菜单中的导航和定位图标。
  - 改进了字体呈现。 改进了文本呈现，以提高清晰度并减少模糊性。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

添加了 18 个新策略。 从 [Microsoft Edge 企业登录页面](https://www.microsoft.com/edge/business/download)下载更新的管理模板。 已添加以下新策略。

- [BasicAuthOverHttpEnabled](./microsoft-edge-policies.md#basicauthoverhttpenabled) - 允许 HTTP 的基本身份验证。
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
- [TargetBlankImpliesNoOpener](./microsoft-edge-policies.md#targetblankimpliesnoopener) - 不要为面向 _blank 的链接设置 window.opener。
- [UpdatePolicyOverride](./microsoft-edge-policies.md#updatepolicyoverride) - 指定 Microsoft Edge 更新如何处理来自 Microsoft Edge 的可用更新。
- [VerticalTabsAllowed](./microsoft-edge-policies.md#verticaltabsallowed) - 为浏览器侧面的选项卡配置垂直布局的可用性。
- [WebRtcAllowLegacyTLSProtocols](./microsoft-edge-policies.md#webrtcallowlegacytlsprotocols) - 允许在 WebRTC 中降级旧版 TLS/DTLS。
- [WebWidgetAllowed](./microsoft-edge-policies.md#webwidgetallowed) - 启用 Web 小组件。
- [WebWidgetIsEnabledOnStartup](./microsoft-edge-policies.md#webwidgetisenabledonstartup) - 在 Windows 启动时允许 Web 小组件。

#### <a name="deprecated-policies"></a>已弃用的策略

- [ProactiveAuthEnabled](./microsoft-edge-policies.md#proactiveauthenabled) - 启用主动身份验证。
- [ProxyBypassList](./microsoft-edge-policies.md#proxybypasslist) - 配置代理绕过规则。
- [ProxyMode](./microsoft-edge-policies.md#proxymode) - 配置代理服务器设置。
- [ProxyPacUrl](./microsoft-edge-policies.md#proxypacurl) - 设置代理 .pac 文件 URL。
- [ProxyServer](./microsoft-edge-policies.md#proxyserver) - 配置代理服务器的地址或 URL。
- [WebDriverOverridesIncompatiblePolicies](./microsoft-edge-policies.md#webdriveroverridesincompatiblepolicies) - 允许 WebDriver 覆盖不兼容的策略。

### <a name="obsoleted-policies"></a>已过时的策略

- [AllowPopupsDuringPageUnload](./microsoft-edge-policies.md#allowpopupsduringpageunload) - 允许页面在卸载期间显示弹出窗口。
- [DefaultPluginsSetting](./microsoft-edge-policies.md#defaultpluginssetting) - 默认 Adobe Flash 设置。
- [PluginsAllowedForUrls](./microsoft-edge-policies.md#pluginsallowedforurls) - 允许特定网站上使用 Adobe Flash 插件。
- [PluginsBlockedForUrls](./microsoft-edge-policies.md#pluginsblockedforurls) - 阻止特定网站上 Adobe Flash 插件。
- [RunAllFlashInAllowMode](./microsoft-edge-policies.md#runallflashinallowmode) - 将 Adobe Flash 内容设置扩展到所有内容。
<!--- end major 88  --->
## <a name="version-87066475-january-7"></a>版本 87.0.664.75：1 月 7 日

[此处](./microsoft-edge-relnotes-security.md#january-7-2021)列出了稳定频道的安全更新。

## <a name="version-87066466-december-17"></a>版本 87.0.664.66：12 月 17 日

修复了各种 bug 和性能问题。

## <a name="version-87066460-december-10"></a>版本 87.0.664.60：12 月 10 日

修复了各种 bug 和性能问题。

## <a name="version-87066457-december-7"></a>版本87.0.664.57：12月7日

修复了各种错误和性能问题。 [此处](./microsoft-edge-relnotes-security.md#december-7-2020)列出了稳定频道的安全更新。

## <a name="version-87066455-december-3"></a>版本 87.0.664.55：12月3日

修复了各种 bug 和性能问题。 此版本的以下功能已更新。

- **默认情况下，购物处于启用状态**。 从 Microsoft Edge 版本87开始，企业用户可从 Microsoft Edge 中的购物中受益。 通过购物功能，Microsoft Edge 可帮助用户在在线购物时查找优惠券和更好的价格。 （稳定版本 87.0.664.41 的优惠券体验已发布。） 价格比较体验现已通过此更新提供。 此功能可使用 [EdgeShoppingAssistantEnabled](./microsoft-edge-policies.md#edgeshoppingassistantenabled) 策略进行配置。 查看我们的[博客](https://blogs.windows.com/windowsexperience/2020/11/19/finish-up-that-holiday-shopping-with-new-features-from-microsoft-edge-and-bing/) ，了解有关 Microsoft 购物的[详细信息](/microsoft-edge/privacy-whitepaper#shopping)。

## <a name="version-87066452-november-30"></a>版本 87.0.664.52：11月30日

修复了各种 bug 和性能问题。

## <a name="version-87066447-november-23"></a>版本 87.0.664.47：11 月 23 日

修复了各种 bug 和性能问题。

<!-- begin major 87 --->
## <a name="version-87066441-november-19"></a>版本 87.0.664.41：11 月 19 日

[此处](./microsoft-edge-relnotes-security.md#november-19-2020)列出了稳定频道的安全更新。

### <a name="feature-updates"></a>功能更新

- **从 Internet Explorer 到 Microsoft Edge 的不兼容网站的自动重定向**。 从 Microsoft Edge 87 稳定更新开始，在 Internet Explorer 上显示不兼容消息的公共网站将自动重定向到 Microsoft Edge。 若要了解详细信息并配置此体验，请参阅 [重定向不兼容的网站](./edge-learnmore-neededge.md)。

- **已启用展台模式隐私功能**。 从 Microsoft Edge 87 版本开始，将启用帮助企业实现用户数据隐私的展台模式功能。 这些功能将启用以下体验，例如，在退出时清除用户数据、删除已下载的文件，以及在指定的空闲时间后重置配置的启动体验。 深入了解如何[配置 Microsoft Edge 的展台模式](./microsoft-edge-configure-kiosk-mode.md)

- **默认情况下启用的购物功能**。 从 Microsoft Edge 版本 87 开始，企业用户也可以从 Edge 购物中受益。 通过购物功能，Microsoft Edge 可帮助用户在在线购物时查找优惠券和更好的价格。 通过此更新提供优惠券体验，价格比较将在 Microsoft Edge 87 的即将推出的更新中发布。 此功能可通过 [EdgeShoppingAssistantEnabled](./microsoft-edge-policies.md#edgeshoppingassistantenabled) 策略进行配置。 查看我们的[博客](https://blogs.windows.com/windowsexperience/2020/11/19/finish-up-that-holiday-shopping-with-new-features-from-microsoft-edge-and-bing/) ，了解有关 Microsoft 购物的[详细信息](/microsoft-edge/privacy-whitepaper#shopping)。

- **在默认情况下启用 ClickOnce 部署**。 Microsoft Edge 87 中默认启用 ClickOnce，这可减少企业部署软件的障碍，并更好地与 Microsoft Edge 旧版浏览器行为保持一致。 从 Microsoft Edge 87 开始，ClickOnceEnabled 策略的“未配置”状态将反映新的默认已启用 ClickOnce 状态（与先前默认“已禁用”状态相比）。

- **企业新选项卡页面（NTP）将生产力与可定制的、与工作相关的源内容整合在一起**。 企业 NTP 将我们提供给用工作或学校账户登录的用户 Office 365 生产率页面与与个性化的、与工作相关的公司和行业信息源融合在一起，并将这些信息源组织在单个页面中。 用户将能够识别熟悉的 Office 365 内容和由 Bing 提供支持的 Microsoft 搜索商业版。 此外，他们可以通过从其组织的可用内容和模块中选择最相关的内容，轻松自定义“我的源”。 IT 管理员可以通过转到 Microsoft 365 管理中心来控制其组织的新闻源设置，包括为 Edge 新建选项卡页所选定的行业。 [了解详细信息](https://blogs.windows.com/msedgedev/2020/10/29/enterprise-new-tab-page-my-feed/)

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
- [EdgeShoppingAssistantEnabled](./microsoft-edge-policies.md#edgeshoppingassistantenabled) - 已启用 Microsoft Edge 中的购物。
- [HideInternetExplorerRedirectUXForIncompatibleSitesEnabled](./microsoft-edge-policies.md#hideinternetexplorerredirectuxforincompatiblesitesenabled) - 隐藏 Microsoft Edge 上的一次性重定向对话框和横幅。
- [KioskAddressBarEditingEnabled](./microsoft-edge-policies.md#kioskaddressbareditingenabled) - 配置地址栏编辑，实现展台模式的公共浏览体验。
- [KioskDeleteDownloadsOnExit](./microsoft-edge-policies.md#kioskdeletedownloadsonexit) - 删除 Microsoft Edge 关闭时作为展台会话的一部分下载的文件。
- [PasswordRevealEnabled](./microsoft-edge-policies.md#passwordrevealenabled) -“启用密码显示”按钮。
- [RedirectSitesFromInternetExplorerPreventBHOInstall](./microsoft-edge-policies.md#redirectsitesfrominternetexplorerpreventbhoinstall) - 阻止安装浏览器帮助程序对象 (BHO) 将不兼容的网站从 Internet Explorer 重定向到 Microsoft Edge。
- [RedirectSitesFromInternetExplorerRedirectMode](./microsoft-edge-policies.md#redirectsitesfrominternetexplorerredirectmode) - 将不兼容的网站从 Internet Explorer 重定向到 Microsoft Edge。
- [SpeechRecognitionEnabled](./microsoft-edge-policies.md#speechrecognitionenabled) - 配置语音识别。
- [WebCaptureEnabled](./microsoft-edge-policies.md#webcaptureenabled) - 启用 Microsoft Edge 中的网页获取功能。

#### <a name="deprecated-policy"></a>已弃用政策

[NewTabPageSetFeedType](./microsoft-edge-policies.md#newtabpagesetfeedtype) - 配置 Microsoft Edge 的新选项卡页面体验。

#### <a name="obsoleted-policy"></a>已过时的策略

[EnableDeprecatedWebPlatformFeatures](./microsoft-edge-policies.md#enabledeprecatedwebplatformfeatures) - 在有限的时间内重新启用已超过限定时间的 web 平台功能。

<!-- end major 87 -->

## <a name="version-86062269-november-13"></a>版本 86.0.622.69：11 月 13 日

> [!IMPORTANT]
> 此更新包含已由 Chromium 团队报告的在现实中被利用的 [CVE-2020-16013](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16013) 和 [CVE-2020-16017](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16017)。

[此处](./microsoft-edge-relnotes-security.md#november-13-2020)列出了稳定频道的安全更新。

## <a name="version-86062268-november-11"></a>版本 86.0.622.68：11 月 11 日

[此处](./microsoft-edge-relnotes-security.md#november-11-2020)列出了稳定频道安全更新

## <a name="version-86062263-november-4"></a>版本 86.0.622.63：11 月 4 日

> [!IMPORTANT]
> 此更新包含已由 Chromium 团队报告的在现实中被利用的 [CVE-2020-16009](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16009)。

[此处](./microsoft-edge-relnotes-security.md#november-4-2020)列出了稳定频道的安全更新。

## <a name="version-86062261-november-2"></a>版本 86.0.622.61：11 月 2 日

修复了各种 bug 和性能问题。

## <a name="version-86062258-october-29"></a>版本 86.0.622.58：10 月 29 日

修复了各种 bug 和性能问题。

## <a name="version-86062256-october-27"></a>版本 86.0.622.56：10 月 27 日

修复了各种 bug 和性能问题。

## <a name="version-86062251-october-22"></a>版本 86.0.622.51：10 月 22 日

[此处](./microsoft-edge-relnotes-security.md#october-22-2020)列出了稳定频道安全更新

## <a name="version-86062248-october-20"></a>版本 86.0.622.48：10 月 20 日

修复了各种 bug 和性能问题。

## <a name="version-86062243-october-15"></a>版本 86.0.622.43：10 月 15 日

修复了各种 bug 和性能问题。

## <a name="version-86062238-october-9"></a>版本 86.0.622.38：10 月 9 日

[此处](./microsoft-edge-relnotes-security.md#october-9-2020)列出安全更新

### <a name="feature-updates"></a>功能更新

* **回退到先前的 Microsoft Edge 版本。** 如果最新版本的 Microsoft Edge 中有问题，则“回退”功能可让管理员还原到已知的正确版本的 Microsoft Edge。 **注意：** 稳定版本 86.0.622.38 是你可以回滚到的第一个版本，这意味着稳定版本 87 是可以从中回滚的第一个版本。 [了解详细信息](edge-learnmore-rollback.md)。

* **默认情况下，在企业范围内强制启用“同步”。**  默认情况下，管理员可使用[ForceSync](./microsoft-edge-policies.md#forcesync) 策略为 Azure Active Directory (Azure AD) 帐户启用同步。

* **Windows 7 和 8.1 上的自动配置文件切换。** Windows 10 上的 Microsoft Edge 中当前提供的自动配置文件切换扩展到了早期版本的 Windows（Windows 7 和 8.1）。 有关详细信息，请参阅博客文章中的[自动配置文件 切换](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/)。

* ** 默认情况下 SameSite=Lax Cookies**。 为了提高 Web 安全性和隐私，默认情况下，Cookie 将默认为 [SameSite=Lax](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite) 处理。 这意味着 Cookie 将仅在第一方上下文中发送，而对于发送给第三方的请求将被忽略。 此更改可能会对需要 Cookie 才能使第三方资源正常运行的网站造成兼容性影响。 为了允许此类 Cookie，Web 开发人员可以通过在设置 Cookie 时添加显式 `SameSite=none` 和 `Secure` 属性来标记应从第三方上下文设置并发送给第三方上下文的 Cookie。 希望将某些网站排除在此更改之外的企业可以使用 [LegacySameSiteCookieBehaviorEnabledForDomainList](./microsoft-edge-policies.md#legacysamesitecookiebehaviorenabledfordomainlist) 策略执行此操作，也可以使用 [LegacySameSiteCookieBehaviorEnabled](./microsoft-edge-policies.md#legacysamesitecookiebehaviorenabled) 策略在所有网站上选择退出此更改。

* **删除 HTML5 应用程序缓存 API。**  从 Microsoft Edge 版本 86 开始，从 Microsoft Edge 中删除了启用网页脱机使用的旧版应用程序缓存 API。 有关将应用程序缓存 API 替换为服务工作进程的信息，Web 开发人员可以查看 [WebDev 文档](https://web.dev/appcache-removal/)。  重要提示：你可以请求[ AppCache OriginTrial 令牌](https://developers.chrome.com/origintrials/#/view_trial/1776670052997660673)，该令牌允许网站继续使用已弃用的应用程序缓存 API，直至 Microsoft Edge 版本90。

* **隐私和安全：**

  * 为早期版本的 Windows 和 macOS 替换[MetricsReportingEnabled](/DeployEdge/microsoft-edge-policies#metricsreportingenabled) 和 [SendSiteInformationToImproveServices](/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices)策略。 这些策略在 Microsoft Edge 版本 86 中已弃用，在 Microsoft Edge 版本 89 中将不再使用。<br>
这些策略将被 Windows 10 上的[允许遥测](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)和所有其他平台的全新[DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) 策略取代。 这将使用户能够为 Windows 7、8、8.1 和 macOS 管理发送到 Microsoft 的诊断数据。
  * 安全 DNS (DNS-over-HTTPS) 支持。  从 Microsoft Edge 版本 86 开始，可以使用设置来控制非托管设备上的安全 DNS。 用户无法访问已托管设备上的这些设置，但 IT 管理员可以使用 [dnsoverhttpsmode](./microsoft-edge-policies.md#dnsoverhttpsmode) 组策略启用或禁用安全 DNS。

* **Internet Explorer 模式：** 让用户使用 Microsoft Edge 用户界面 (UI) 在 Internet Explorer 模式下测试网站。 从Microsoft Edge 版本 86 开始，管理员可以为用户启用一个 UI 选项，让用户在 Internet Explorer 模式加载一个选项卡，以进行测试，或者在网站被添加到网站列表的 XML 中之前作为替代。

* **PDF 更新：**

  * PDF 文档目录。 从版本 86 开始，Microsoft Edge 添加了对目录的支持，可让用户轻松浏览 PDF 文档。
  * 在小型外形规格屏幕上访问所有 PDF 功能。 在具有小型屏幕尺寸的设备上访问 Microsoft Edge PDF 阅读器的所有功能。
  * PDF 文件上对荧光笔的支持。 通过此更新，用户可使用数字荧光笔直接突出显示 PDF 文件上的文本，就像使用物理荧光笔和纸张一样。
  * 改进了 PDF 滚动。 现在，你可以在浏览较长的 PDF 文档时体验流畅的滚动效果。

* **当用户开始在 Microsoft Edge 加载项网站中键入搜索查询时，将看到自动完成建议。** 自动完成将帮助用户快速完成搜索查询，而无需键入完整字符串。 这将非常有用，因为用户无需记住正确的拼写，可以从显示的可用选项中进行选择。

* **使用组策略向全新选项卡页面 (NTP) 中添加自定义图像。** 从 Microsoft Edge 版本 86 开始，NTP 可以选择使用自定义用户提供的图像来替换默认图像。 组策略也支持管理此图像属性的功能。

* **匹配自定义键盘快捷方式与 VS Code。** Microsoft Edge 开发工具现在支持自定义开发工具中的键盘快捷方式，使其匹配你的编辑器/IDE。 （在 Microsoft Edge 84 中，我们添加了匹配开发工具键盘快捷方式和 VS Code 的功能）。

* **使用下载管理器从磁盘删除下载。** 用户现在无需离开浏览器即可从磁盘中删除其载的文件。 全新“删除下载”功能位于下载架或下载页面的弹出菜单中。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

添加了 23 个新策略。 从 [Microsoft Edge 企业登录页面](https://aka.ms/EdgeEnterprise)下载更新的管理模板。 已添加以下新策略。

- [CollectionsServicesAndExportsBlockList](./microsoft-edge-policies.md#collectionsservicesandexportsblocklist) - 阻止访问指定服务列表及在集锦中导出目标。
- [DefaultFileSystemReadGuardSetting](./microsoft-edge-policies.md#defaultfilesystemreadguardsetting) - 控制文件系统 API 在读取中的使用。
- [DefaultFileSystemWriteGuardSetting](./microsoft-edge-policies.md#defaultfilesystemwriteguardsetting) -控制文件系统 API 在写入中的使用。
- [DefaultSensorsSetting](./microsoft-edge-policies.md#defaultsensorssetting) - 默认传感器设置。
- [DefaultSerialGuardSetting](./microsoft-edge-policies.md#defaultserialguardsetting) - 控制串行 API 的使用。
- [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) - 发送有关浏览器使用情况的必需和可选诊断数据。
- [EnterpriseModeSiteListManagerAllowed](./microsoft-edge-policies.md#enterprisemodesitelistmanagerallowed) - 允许访问 Enterprise Mode Site List Manager 工具。
- [FileSystemReadAskForUrls](./microsoft-edge-policies.md#filesystemreadaskforurls) - 允许在这些网站上通过文件系统 API 进行读取访问。
- [FileSystemReadBlockedForUrls](./microsoft-edge-policies.md#filesystemreadblockedforurls) - 阻止在这些网站上通过文件系统 API 进行读取访问。
- [FileSystemWriteAskForUrls](./microsoft-edge-policies.md#filesystemwriteaskforurls) - 允许在这些网站上对文件和目录进行写入访问。
- [FileSystemWriteBlockedForUrls](./microsoft-edge-policies.md#filesystemwriteblockedforurls) - 阻止在这些网站上对文件和目录进行写入访问。
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
- [UserAgentClientHintsEnabled](./microsoft-edge-policies.md#useragentclienthintsenabled) - 启用“User-Agent 客户端提示”功能（已弃用）。
- [UserDataSnapshotRetentionLimit](./microsoft-edge-policies.md#userdatasnapshotretentionlimit) - 限制保留用于紧急回退情况的用户数据快照数量。

#### <a name="deprecated-policies"></a>已弃用的策略

- [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled)：启用使用情况和故障相关数据报告。
- [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices)：发送站点信息以改进 Microsoft 服务。

#### <a name="obsoleted-policy"></a>已过时的策略

[TLS13HardeningForLocalAnchorsEnabled](./microsoft-edge-policies.md#tls13hardeningforlocalanchorsenabled) - 为本地信任密钥启用 TLS 1.3 安全功能。

## <a name="version-85056470-october-6"></a>版本 85.0.564.70：10 月 6 日

修复了各种 bug 和性能问题。

## <a name="version-85056468-october-1"></a>版本 85.0.564.68：10 月 1 日

修复了各种 bug 和性能问题。

## <a name="version-85056463-september-23"></a>版本 85.0.564.63: 9 月 23 日

[此处](./microsoft-edge-relnotes-security.md#september-23-2020)列出安全更新

## <a name="version-85056451-september-9"></a>版本 85.0.564.51：9 月 9 日

[此处](./microsoft-edge-relnotes-security.md#september-9-2020)列出安全更新

## <a name="version-85056444-august-31"></a>版本 85.0.564.44：8 月 31 日

修复了各种 bug 和性能问题。

<!-- 85.0.564.41: August 27 -->

## <a name="version-85056441-august-27"></a>版本 85.0.564.41：8 月 27 日

[此处](./microsoft-edge-relnotes-security.md#august-27-2020)列出安全更新

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
- [EnableSha1ForLocalAnchors](./microsoft-edge-policies.md#enablesha1forlocalanchors) - 允许由本地信任定位点颁发的 SHA - 1 签名证书。 <!--- [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](./microsoft-edge-policies.md#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - Disable download file type extension-based warnings for specified file types on domains. -->
- [IntensiveWakeUpThrottlingEnabled](./microsoft-edge-policies.md#intensivewakeupthrottlingenabled) - 控制 IntensiveWakeUpThrottling 功能。
- [NewTabPagePrerenderEnabled](./microsoft-edge-policies.md#newtabpageprerenderenabled) - 启用新选项卡页面的预加载，以便快速呈现。
- [NewTabPageSearchBox](./microsoft-edge-policies.md#newtabpagesearchbox) - 配置新的选项卡页面搜索框体验。
- [PasswordMonitorAllowed](./microsoft-edge-policies.md#passwordmonitorallowed) - 当用户的密码被发现不安全时，允许收到警告。
- [RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled) - 支持使用 Microsoft Edge 配置文件数据的漫游副本。
- [RoamingProfileLocation](./microsoft-edge-policies.md#roamingprofilelocation) - 设置漫游配置文件目录。
- [TLSCsipherSuiteDenyList](./microsoft-edge-policies.md#tlsciphersuitedenylist) - 指定要禁用的 TLS 密码套件。

#### <a name="obsoleted-policies"></a>已过时的策略

- [EnableDomainActionsDownload](./microsoft-edge-policies.md#enabledomainactionsdownload) - 启用来自 Microsoft 的域操作下载。
- [WebComponentsV0Enabled](./microsoft-edge-policies.md#webcomponentsv0enabled) - 重新启用 Web 组件 v0 API 至 M84。
- [WebDriverOverridesIncompatiblePolicies](./microsoft-edge-policies.md#webdriveroverridesincompatiblepolicies)- 允许 WebDriver 覆盖不兼容策略。

## <a name="version-84052263-august-20"></a>版本 84.0.522.63：8 月 20 日

[此处](./microsoft-edge-relnotes-security.md#august-20-2020)列出安全更新。

## <a name="version-84052261-august-17"></a>版本84.0.522.61：8 月 17 日

修复了各种 bug 和性能问题。

## <a name="version-84052259-august-11"></a>版本 84.0.522.59：8 月 11日

[此处](./microsoft-edge-relnotes-security.md#august-11-2020)列出安全更新

## <a name="version-84052258-august-10"></a>版本 84.0.522.58：8 月 10 日

修复了各种 bug 和性能问题。

## <a name="version-84052252-august-1"></a>版本 84.0.522.52：8 月 1 日

修复了各种 bug 和性能问题。

## <a name="version-84052250-july-31"></a>版本 84.0.522.50：7 月 31 日

修复了各种 bug 和性能问题。

## <a name="version-84052249-july-29"></a>版本 84.0.522.49：7 月 29 日

[此处](./microsoft-edge-relnotes-security.md#july-29-2020)列出安全更新

## <a name="version-84052248-july-28"></a>版本 84.0.522.48：7 月 28 日

修复了各种 bug 和性能问题。

## <a name="version-84052244-july-23"></a>版本 84.0.522.44：7 月 23 日

修复了各种 bug 和性能问题。

## <a name="version-84052240-july-16"></a>版本 84.0.522.40：7 月 16 日

[此处](./microsoft-edge-relnotes-security.md#july-16-2020)列出安全更新

### <a name="feature-updates"></a>功能更新

- 该版本的 Microsoft Edge 缩短了 Internet Explorer 模式的网站列表下载时间。 没有缓存网站列表时，我们将 Internet Explorer 模式网站列表的下载延迟从 60 秒的等待时间缩短为了 0 秒。 我们还添加了组策略支持，用来应对需要推迟到网站列表下载后再进行 Internet Explorer 模式主页导航的情况。 有关详细信息，请参阅 [DelayNavigationsForInitialSiteListDownload](./microsoft-edge-policies.md#delaynavigationsforinitialsitelistdownload) 策略。

- 现在，Microsoft Edge 在 Windows 10 上“以管理员身份运行”时，允许用户登录到浏览器。 这将帮助用户在 Windows Server 上或在远程桌面和沙盒场景中运行 Microsoft Edge。

- Microsoft Edge 现在处于全屏模式时提供完整的鼠标支持。 现在，你无需退出全屏模式即可使用鼠标来访问选项卡、地址栏和其他项目。

- 改进了在线购买。 向保存的借记卡或信用卡添加自定义别名。 现在，你在线购买时可区分和辨别借记卡。 通过给借记卡或信用卡“起绰号”，可让你在使用“自动填充”功能来选择付款方式时选择适当的卡片。

- 默认禁用 TLS/1.0 和 TLS/1.1。  可通过 [SSLVersionMin](./microsoft-edge-policies.md#sslversionmin) 策略重新启用 TLS/1.0 和 TLS/1.1。 此策略将持续可用，直到至少达到 Microsoft Edge 版本 88 为止。 有关详细信息，请参阅 [Microsoft Edge 中影响网站兼容性的更改](/microsoft-edge/web-platform/site-impacting-changes)。

- 改进了集合：

  - 添加了一项“注释”功能，你可用它来对集合中的项目添加注释或备注。 注释分组到一起，即使你对集合中的项目进行了排序，它们也附加到相应的项目上。 若要试用这项新功能，请右键单击一个项目，然后选择“添加注释”。
  - 可更改集合中注释的背景色。 可使用颜色编码来帮助你整理信息并提高工作效率。
  - 有明显的性能改进，让你在将集合导出到 Excel 时所用时间比在之前版本的 Microsoft Edge 中操作时要短。

- 其他 Microsoft Edge API 支持：

  - 针对实验用途启用了存储访问 API。 为家庭版用户和企业版用户启用了此功能，且将 [ExperimentationAndConfigurationServiceControl](./microsoft-edge-policies.md#experimentationandconfigurationservicecontrol) 策略设置为“Full”。 在 Microsoft Edge 稳定频道版本 85 中，将默认为所有用户启用此功能。
  
    随着隐私对用户来说越来越重要，对更严格的浏览器默认设置和用户选择加入设置（例如阻止所有第三方存储访问）的需求越来越常见。 虽然这些设置可帮助加强隐私保护和阻止未知或不受信任的用户方不必要的访问，但它们也可能产生并未期待的副作用，例如阻止访问用户可能想要查看的内容（比如社交媒体和嵌入的媒体内容）。

    当用户直接指示允许本来会被浏览器的当前配置阻止的存储时，可使用此存储访问 API 来在第三方上下文中访问第一方存储。 有关详细信息，请参阅[存储访问 API](https://www.chromestatus.com/feature/5612590694662144)。

  - 本机文件系统 API，这意味着你可通过它来向网站授予编辑文件或文件夹的权限。

- 改进了 PDF：

  - 通过 PDF 的“大声朗读”功能，用户可在执行其他对他们而言可能很重要的任务的同时收听 PDF 内容。 它还有助于音频视觉学习者专注阅读内容，让学习变得更轻松。
  - PDF 文件编辑也得到了改进。 你现可将对 PDF 进行的编辑保存回文件，而不是每次编辑 PDF 时都保存一个副本。

- Microsoft Edge 现在沉浸式阅读器中启用翻译功能。 当用户打开“沉浸式阅读器”视图时，他们可将页面翻译成他们期待的语言。

- 对开发工具的多项更新，包括支持自定义键盘快捷方式以匹配 VS Code 和支持以高对比度查看开发工具。  有关详细信息，请参阅[开发工具 (Microsoft Edge 84) 中的新增功能](/microsoft-edge/devtools-guide-chromium/whats-new/2020/05/devtools)。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

添加了 7 个新策略。 从 [Microsoft Edge 企业登录页面](https://aka.ms/EdgeEnterprise)下载更新的管理模板。 已添加以下新策略。

- [AppCacheForceEnabled](./microsoft-edge-policies.md#appcacheforceenabled) - 允许重新启用 AppCache 功能，即使该功能默认关闭也是如此。
- [ApplicationGuardContainerProxy](./microsoft-edge-policies.md#applicationguardcontainerproxy) - 配置应用程序防护容器代理的设置。
- [DelayNavigationsForInitialSiteListDownload](./microsoft-edge-policies.md#delaynavigationsforinitialsitelistdownload) - 要求在可进行标签页导航之前，企业模式网站列表可用。
- [WinHttpProxyResolverEnabled](./microsoft-edge-policies.md#winhttpproxyresolverenabled) - 使用 Windows 代理解析程序。
- [InternetExplorerIntegrationEnhancedHangDetection](./microsoft-edge-policies.md#internetexplorerintegrationenhancedhangdetection) - 为 Internet Explorer 模式配置增强型挂起检测。
- [NativeWindowOcclusionEnabled](./microsoft-edge-policies.md#nativewindowocclusionenabled) - 为降低 CPU 使用率和功耗，Microsoft Edge 将检测窗口何时被其他窗口覆盖，并将暂停工作绘制像素。
- [NavigationDelayForInitialSiteListDownloadTimeout](./microsoft-edge-policies.md#navigationdelayforinitialsitelistdownloadtimeout) -为企业模式网站列表设置标签页导航的延迟超时。

#### <a name="deprecated-policies"></a>已弃用的策略

- [AllowSyncXHRInPageDismissal](./microsoft-edge-policies.md#allowsyncxhrinpagedismissal) - 允许页面在页面关闭期间发送同步 XHR 请求。
- [BuiltinCertificateVerifierEnabled](./microsoft-edge-policies.md#builtincertificateverifierenabled) - 确定是否将使用内置证书验证程序来验证服务器证书。
- [StricterMixedContentTreatmentEnabled](./microsoft-edge-policies.md#strictermixedcontenttreatmentenabled) - 对混合内容进行更严格的处理。

#### <a name="obsoleted-policy"></a>已过时的策略

[ForceNetworkInProcess](./microsoft-edge-policies.md#forcenetworkinprocess) - 强制网络代码在浏览器进程中运行。

<!-- End 84 -->
## <a name="version-83047864-july-13"></a>版本 83.0.478.64：7 月 13 日

修复了各种 bug 和性能问题。

## <a name="version-83047861-july-7"></a>版本 83.0.478.61：7 月 7 日

修复了各种 bug 和性能问题。

## <a name="version-83047858-june-30"></a>版本 83.0.478.58：6 月 30 日

修复了各种 bug 和性能问题。

## <a name="version-83047856-june-24"></a>版本 83.0.478.56：6 月 24 日

修复了各种 bug 和性能问题。

[此处](./microsoft-edge-relnotes-security.md#june-24-2020)列出安全更新

## <a name="version-83047854-june-17"></a>版本 83.0.478.54：6 月 17 日

[此处](./microsoft-edge-relnotes-security.md#june-17-2020)列出安全更新

## <a name="version-83047850-june-15"></a>版本 83.0.478.50：6 月 15 日

修复了各种 bug 和性能问题。

## <a name="version-83047845-june-4"></a>版本 83.0.478.45：6 月 4 日

[此处](./microsoft-edge-relnotes-security.md#june-4-2020)列出安全更新

## <a name="version-83047844-june-1"></a>版本 83.0.478.44：6 月 1 日

修复了各种 bug 和性能问题。

## <a name="version-83047837-may-21"></a>版本 83.0.478.37：5 月 21 日

[此处](./microsoft-edge-relnotes-security.md#may-21-2020)列出安全更新

### <a name="feature-updates"></a>功能更新

- Microsoft Edge 更新现将逐步推出。 今后将在几天时间内向我们的用户推出 Microsoft Edge 的更新。 这样，我们能够保护你们当中的更多人免受意外错误更新的困扰，这改进了更新体验。 而作为用户，你将继续获得无缝顺畅的自动更新。 如果你的组织没有注册自动更新，你将不受此更改的影响。 若要了解详细信息，请参阅[“渐进式推出”一文](microsoft-edge-update-progressive-rollout.md)。
- Microsoft Defender SmartScreen 改进：对 Microsoft Defender SmartScreen 服务进行了多种改进，如改进了对加载时重定向的恶意网站的保护，以及通过 Microsoft Defender SmartScreen 安全页完全替换恶意网站的顶级框架阻止。 顶级框架阻止功能可阻止播放恶意网站中的音频和其他媒体，从而使用户感觉更容易、更轻松。

- 根据用户反馈，用户现在可以解除部分 Cookie 限制，使其在浏览器关闭时自动清除。 如果有用户不希望注销的网站，但是希望在关闭浏览器时清除所有其他 Cookie ，则此选项非常有用。 若要使用此功能，请转到 *edge://settings/clearBrowsingDataOnClose* 并启用“Cookie 和其他网站数据”切换。

- 自动配置文件切换现在可用，有助于更轻松地跨配置文件获取工作内容。 如果你在工作中使用多个配置文件，可以在使用个人配置文件时，通过浏览至需要工作或学校账户验证的网站查看配置文件。 检测到此情况时，您将收到提示，提示您切换到工作配置文件以访问该网站，无需进行身份验证。 选择希望切换至的工作简介时，网站将直接在工作简介中打开。 此配置文件切换功能将有助于将工作和个人数据分开，轻松地获取工作内容。 如果不希望提示切换配置文件的功能，可选择“不再询问”选项，然后就会不再发出提醒。

- 集合功能改进：
  - 可以使用拖放操作将项目添加到集合中，而无需打开集合。 拖放期间，还可在集合列表中选择希望放置项目的位置。
  - 可以将多个项目添加到集合中，而不是一次添加一项。 若要添加多个项，选择项，然后拖动至集合中。 或者，可以选择项目，右键单击，然后选择希望放置项的集合。

- 可以将 Edge 窗口中的所有选项卡添加到新集合中，而无需单独添加。 若要执行此操作，请右键单击任意选项卡，然后选择“将所有选项卡添加到新集合”。

- 扩展同步现在可用。 现在，可以在你的所有设备上同步扩展！ Microsoft 和 Chrome 应用商店中的扩展程序都将与 Microsoft Edge 同步。 若要使用此功能：单击菜单栏上的省略号（**...**），选择“**设置**”。 在配置文件下，单击“**同步**”以查看“同步”选项。 在“**配置文件 / 同步**”下，使用切换来启用扩展。 可使用 [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) 组策略来禁用扩展同步。

- 改进了下载管理页面上针对已阻止的不安全下载的消息。

- 沉浸式阅读器改进：
  - 现在支持在沉浸式阅读器中的“词性”体验中使用“副词”。 在沉浸式阅读器中阅读文章时，打开“语法工具”，并在“词性”中打开“副词”，可以突出显示页面上的所有副词。
  - 现在支持选择网页上的任何内容并在在沉浸式阅读器中打开。 借助此功能，用户可以在所有网站中使用沉浸式阅读器和所有学习工具，如“行焦点”和“大声朗读”。

- 在用户输入错误的 URL 时，链接医生会向用户提供主机更正和搜索查询。 例如： <br>
用户将“powerbi”错误输入为“powerbbi”.com。 链接医生将建议“powerbi”.com 作为更正，并创建一个链接以搜索“powerbbi”，以防用户查找不同的内容。

- 允许用户保存其为特定站点启动外部协议的决定。 用户可以配置 [ExternalProtocolDialogShowAlwaysOpenCheckbox](/DeployEdge/microsoft-edge-policies#externalprotocoldialogshowalwaysopencheckbox) 策略以启用或禁用此功能。

- 用户可以直接从 Microsoft Edge“**设置**”将 Microsoft Edge 设为默认浏览器。 这使用户可以更轻松地在浏览器本身上下文中更改其默认浏览器，而不必搜索操作系统设置。 要使用此功能，请转到 *edge://settings/defaultBrowser*，然后单击“**设为默认值**”。

- 许多开发工具更新，包括新的远程调试支持、UI 改进等。 有关详细信息，请参见[开发工具 (Microsoft Edge 83) 中的新增功能](/microsoft-edge/devtools-guide-chromium/whats-new/2020/03/devtools)。

- Microsoft Defender for Cloud Apps警告方案现已推出。 这使管理员能够设置警告，这是Defender for Cloud应用块的新类别，用户可在其中替代Defender for Cloud应用块页。 MDATP E5 阻止功能已与 Microsoft Edge 中的 SmartScreen 阻止功能集成，可提供无缝体验。 通过此体验，可整页呈红色表示阻止并显示“你的组织已阻止此网站”消息，而不是只显示 toast 通知。

- 在页面关闭期间禁止同步 XmlHttpRequest。 将取消在网页卸载期间发送同步 XmlHttpRequest 的操作。 此更改将提高浏览器的性能和可靠性，但如果有 Web 应用程序尚未更新以使用更新式的 Web API（包括 sendBeacon 和 fetch），则这些应用可能会受到影响。 在 Microsoft Edge 88 版本之后，才可使用用于禁用此更改并在页面关闭期间允许同步 XHR 的组策略。 有关详细信息，请参阅 [Microsoft Edge 中影响网站兼容性的更改](/microsoft-edge/web-platform/site-impacting-changes)。

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

<!-- end 83 -->

## <a name="version-81041677-may-18"></a>版本 81.0.416.77：5 月 18 日

修复了各种 bug 和性能问题。

## <a name="version-81041672-may-7"></a>版本 81.0.416.72：5 月 7 日

[此处](./microsoft-edge-relnotes-security.md#may-7-2020)列出安全更新

## <a name="version-81041668-april-29"></a>版本 81.0.416.68：4 月 29 日

[此处](./microsoft-edge-relnotes-security.md#april-29-2020)列出安全更新

## <a name="version-81041664-april-23"></a>版本 81.0.416.64：4 月 23 日

[此处](./microsoft-edge-relnotes-security.md#april-23-2020)列出安全更新

## <a name="version-81041658-april-17"></a>版本 81.0.416.58：4 月 17 日

[此处](./microsoft-edge-relnotes-security.md#april-17-2020)列出安全更新

## <a name="version-81041653-april-13"></a>版本 81.0.416.53：4 月 13 日

[此处](./microsoft-edge-relnotes-security.md#april-13-2020)列出安全更新

### <a name="feature-updates"></a>功能更新

- 新增了对 Windows 信息保护（WIP）的支持，帮助企业保护敏感数据免受未经授权的泄露。 [了解详情](./microsoft-edge-security-windows-information-protection.md)。

- 现已推出“收藏”功能。 若要开始，请单击地址栏旁边的“收藏夹”图标。 此操作将打开“收藏”窗格，可在其中创建、编辑和查看收藏。 我们根据你在 Web 上的行为设计了“收藏”功能。 如果你是购物者、旅行者、教师或学生，那么“收藏”功能可以为你提供帮助。 [了解详细信息](https://blogs.windows.com/msedgedev/2019/12/09/improvements-collections-sync-microsoft-edge/#LuDPRDUDCgdgdOVt.97)。

- 允许从 Microsoft Edge 工具栏中删除“收藏”按钮（从工具栏隐藏）以保持一致性。

- 本地 Active Directory 帐户自动登录将仅针对启用该功能的组织。  如果用户已使用本地 AD 帐户登录，可以注销该帐户。 仅当用户在操作系统上的主帐户是 Microsoft 帐户或 Azure Active Directory 帐户时，才会使用该帐户自动登录。 管理员可以使用 ConfigureOnPremisesAccountAutoSignIn 策略启用本地 AD 帐户的自动登录。

- 应用程序防护。 容器中现已提供扩展支持。

- 添加了一条消息，通知用户当导航到配置为在 Internet Explorer 模式下打开的页面时不会安装 Internet Explorer。

- 使用新功能更新了 Microsoft Edge DevTools 中的 3D 视图工具，可帮助调试 z-index 堆叠上下文。 3D 视图使用颜色和堆叠来显示 DOM（文档对象模型）深度的表示形式，而 z-Index 视图可帮助隔离页面的不同堆叠上下文。 [了解详细信息](https://blogs.windows.com/msedgedev/2020/01/23/debug-z-index-3d-view-edge-devtools/)。

- 已将 F12 Dev 工具本地化为 10 种新语言，因此它们将与其他浏览器中使用的语言匹配。 [了解详细信息](https://blogs.windows.com/msedgedev/2020/02/04/localizing-edge-devtools/)。

- 添加了对 Dolby Vision 播放的支持。 在已启用 Dolby Vision 的 Windows 10 内部版本 17134（2018 年 4 月更新）中，网站可以显示 Dolby Vision 内容。 了解如何从 [Netflix](https://help.netflix.com/en/node/42384) 启用 Dolby Vision。

- Microsoft Edge 现在可以识别并删除重复收藏夹，以及合并具有相同名称的文件夹。 若要访问该工具，请单击浏览器工具栏上的星星图标，然后选择“删除重复的收藏夹”。  你可确认更改，并且对收藏夹所做的任何更新都将在设备之间同步。

- 我们从用户那里得知，很难区分采用深色主题的普通浏览窗口与 InPrivate 窗口，因为这两个窗口框架都是深色的。 右上角的新 InPrivate 纯蓝色药丸图标有助于确保用户正在浏览 InPrivate。

- 在正确的浏览器配置文件中打开外部链接。 从 *edge://settings/multiProfileSettings* 中，为在外部应用中打开的链接选择默认配置文件。

- 添加了一条警告，以警告先前使用其他帐户登录后使用某个帐户登录浏览器配置文件的用户。 此警告将有助于防止意外数据合并。

- 如果你的 Microsoft 帐户中保存了支付卡，则可以在填写支付方式时在 Microsoft Edge 中使用它们。 你的 Microsoft 帐户中的卡片将在桌面设备之间同步，并且在进行双因素身份验证（CVC 代码和你的 Microsoft 标识）之后，将与网站共享完整详细信息。为了进一步的方便，你可以选择在身份验证期间将卡片的副本安全地保存在设备上。

- “行焦点”功能专为希望在阅读时专注于部分内容的用户而设计。 它可让用户一次将注意力集中在 第一、三或五行上，并使页面的其余部分变暗，以便用户在阅读时不会分散注意力。 用户可通过触摸或箭头键进行滚动，并且焦点将相应地移动。

- Microsoft Edge 现在已与 Windows 平台 8.1 及更高版本上的 Windows 拼写器相集成。 此集成可提供更强大的语言支持，访问更多的语言词典，还可让用户使用 Windows 自定义词典。 在操作系统语言设置中添加语言后，用户无需采取任何其他措施。 此外，在 Microsoft Edge 设置中启用了语言拼写检查切换。

- 使用 Microsoft Edge 打开 PDF 文档后，用户现在可以创建突出显示、更改颜色和删除突出显示。 此功能有助于以后参考文档的重要部分并进行协作。

- 如果加载已针对 Web 优化的长篇 PDF 文档，则在加载文档的其余部分时，将更快地并行加载用户正在查看的页面。

- 现在，只需按 F9 键就即可更轻松地启动网站的沉浸式阅读器。

- 现在，可使用键盘快捷方式 (Ctrl + Shift + U) 更轻松地启动“大声朗读”。

- 添加了 MSI 命令行参数，可在安装 Microsoft Edge 时禁止创建桌面图标。 以下示例演示了如何使用此新的参数： <br>
`MicrosoftEdgeEnterpriseX64.msi DONOTCREATEDESKTOPSHORTCUT=true`<br>
在即将发布的版本中，将提供一个组策略来支持此功能。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

添加了 11 个新策略。 从 [Microsoft Edge 企业登录页面](https://aka.ms/EdgeEnterprise)下载更新的管理模板。 已添加以下新策略。

- [AmbientAuthenticationInPrivateModesEnabled](./microsoft-edge-policies.md#ambientauthenticationinprivatemodesenabled) - 为 InPrivate 和来宾配置文件启用环境身份验证。 
- [AudioSandboxEnabled](./microsoft-edge-policies.md#audiosandboxenabled) - 允许运行音频沙盒。
- [ForceLegacyDefaultReferrerPolicy](./microsoft-edge-policies.md#forcelegacydefaultreferrerpolicy) - 使用 no-referrer-when-downgrade 的默认引荐策略。
- [GloballyScopeHTTPAuthCacheEnabled](./microsoft-edge-policies.md#globallyscopehttpauthcacheenabled) - 启用全局范围的 HTTP 身份验证缓存。
- [ImportExtensions](./microsoft-edge-policies.md#importextensions) - 允许导入扩展。
- [ImportCookies](./microsoft-edge-policies.md#importcookies) - 允许导入 Cookie。
- [ImportShortcuts](./microsoft-edge-policies.md#importshortcuts) - 允许导入快捷方式。
- [InternetExplorerIntegrationSiteRedirect](./microsoft-edge-policies.md#internetexplorerintegrationsiteredirect) - 指定从 Internet Explorer 模式页面到未配置的网站的“页内”导航行为方式。
- [StricterMixedContentTreatmentEnabled](./microsoft-edge-policies.md#strictermixedcontenttreatmentenabled) - 对混合内容进行更严格的处理。
- [TLS13HardeningForLocalAnchorsEnabled](./microsoft-edge-policies.md#tls13hardeningforlocalanchorsenabled) - 为本地信任密钥启用 TLS 1.3 安全功能。
- [ConfigureOnPremisesAccountAutoSignIn](./microsoft-edge-policies.md#configureonpremisesaccountautosignin) - 当没有 Azure AD 域帐户时配置 Active Directory 域帐户的自动登录。

#### <a name="policy-name-and-caption-changes"></a>策略名称和标题更改

策略 `OmniboxMSBProviderEnabled` 更改为 [AddressBarMicrosoftSearchInBingProviderEnabled](//DeployEdge/microsoft-edge-policies#addressbarmicrosoftsearchinbingproviderenabled)-策略的标题为“在地址栏中的必应建议中启用 Microsoft 搜索”。

#### <a name="deprecated-policies"></a>已弃用的策略

以下策略在此版本中继续有效。 在未来的版本中，它们将被“弃用”。

- [WebComponentsV0Enabled](./microsoft-edge-policies.md#webcomponentsv0enabled) - 重新启用 Web 组件 v0 API 至 M84。
- [WebDriverOverridesIncompatiblePolicies](./microsoft-edge-policies.md#webdriveroverridesincompatiblepolicies) - 允许 WebDriver 覆盖不兼容策略。

#### <a name="resolved-issues"></a>已解决的问题

- 修复了以下问题：即使下载了文件，Microsoft Edge 上的IE模式也导致显示正在进行的下载对话框。
- 修复了以下问题：已处于 IE 模式的页面触发打开新的 IE 模式选项卡时，Microsoft Edge 会丢弃会话 Cookie。

## <a name="version-800361111-april-7"></a>版本 80.0.361.111：4 月 7 日

修复了各种 bug 和性能问题。

## <a name="version-800361109-april-1"></a>版本 80.0.361.109：4 月 1 日

[此处](./microsoft-edge-relnotes-security.md#april-1-2020)列出安全更新

## <a name="version-80036169-march-19"></a>版本 80.0.361.69：3 月 19 日

[此处](./microsoft-edge-relnotes-security.md#march-19-2020)列出安全更新

## <a name="version-80036166-march-4"></a>版本 80.0.361.66：3 月 4 日

[此处](./microsoft-edge-relnotes-security.md#march-4-2020)列出安全更新

## <a name="version-80036162-february-25"></a>版本 80.0.361.62：2 月 25 日

[此处](./microsoft-edge-relnotes-security.md#february-25-2020)列出安全更新

## <a name="version-80036157-february-20"></a>版本 80.0.361.57：2 月 20 日

[此处](./microsoft-edge-relnotes-security.md#february-20-2020)列出安全更新

## <a name="version-80036156-february-19"></a>版本 80.0.361.56：2 月 19 日

修复了各种 bug 和性能问题。

## <a name="version-80036154-february-14"></a>版本 80.0.361.54：2 月 14 日

### <a name="resolved-issues"></a>已解决的问题

- 修复了密码、付款和 Cookie 无法导入至 Microsoft Edge 的问题。

## <a name="version-80036150-february-11"></a>版本 80.0.361.50：2 月 11 日

修复了各种 bug 和性能修复程序。

## <a name="version-80036148-february-7"></a>版本 80.0.361.48：2 月 7 日

[此处](./microsoft-edge-relnotes-security.md#february-7-2020)列出安全更新

### <a name="feature-updates"></a>功能更新

- 添加了 SmartScreen 保护，可防止下载可能有害的应用。 [了解详细信息](/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus)
- 添加了对 Dolby Vision 播放的支持。
- 允许 Windows Mixed Reality 用户在 VR 耳机上观看 360° 视频。
- 在阅读视图中添加了一个用于增加文本间距的选项。
- 添加了使用 Surface 触控笔橡皮擦来擦除链接的支持。
- 添加了对在编辑器模式下使用箭头键和空格键在反馈屏幕截图进行绘制的支持。
- 提高了屏幕截图的可靠性，以便在提交反馈时它们不再显示为黑色。
- 在设备未连接到 Internet 时显示的本地新标签页中添加了深色主题支持。
- 添加了当浏览器会话在更新、崩溃等之后恢复时，恢复作为应用安装的网站的功能。
- 通过组策略管理浏览器时，为 PDF UI 添加了深色主题支持。
- 已将 Adobe Flash 更新到版本 32.0.0.321。 [了解详细信息](https://helpx.adobe.com/flash-player/release-note/fp_32_air_32_release_notes.html)

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

添加了 16 个新策略。 从 [Microsoft Edge 企业登录页面](https://aka.ms/EdgeEnterprise)下载更新的管理模板。 已添加以下新策略。

- [AlternateErrorPagesEnabled](./microsoft-edge-policies.md#alternateerrorpagesenabled) - 如果找不到网页，则推荐类似的页面。
- [DefaultInsecureContentSetting](./microsoft-edge-policies.md#defaultinsecurecontentsetting) - 控制不安全的内容异常的使用。
- [DNSInterceptionChecksEnabled](./microsoft-edge-policies.md#dnsinterceptionchecksenabled) - 已启用 DNS 拦截检查。
- [HideFirstRunExperience](./microsoft-edge-policies.md#hidefirstrunexperience) - 隐藏首次运行体验和初始屏幕。
- [InsecureContentAllowedForUrls](./microsoft-edge-policies.md#insecurecontentallowedforurls) - 允许指定网站上的不安全内容。
- [InsecureContentBlockedForUrls](./microsoft-edge-policies.md#insecurecontentblockedforurls) - 阻止指定网站上的不安全内容。
- [LegacySameSiteCookieBehaviorEnabled](./microsoft-edge-policies.md#legacysamesitecookiebehaviorenabled) - 启用默认旧式 SameSite Cookie 行为设置。
- [LegacySameSiteCookieBehaviorEnabledForDomainList](./microsoft-edge-policies.md#legacysamesitecookiebehaviorenabledfordomainlist) - 将指定网站上的 Cookie 恢复为旧式 SameSite 行为。
- [PaymentMethodQueryEnabled](./microsoft-edge-policies.md#paymentmethodqueryenabled) - 允许网站查询可用的支付方式。
- [PersonalizationReportingEnabled](./microsoft-edge-policies.md#personalizationreportingenabled) - 通过向 Microsoft 发送浏览历史记录，允许对广告、搜索和新闻进行个性化设置。
- [PinningWizardAllowed](./microsoft-edge-policies.md#pinningwizardallowed) - 允许固定到任务栏向导。
- [SmartScreenPuaEnabled](./microsoft-edge-policies.md#smartscreenpuaenabled) - 配置 Microsoft Defender SmartScreen 以阻止可能有害的应用。
- [TotalMemoryLimitMb](./microsoft-edge-policies.md#totalmemorylimitmb) - 设置单个 Microsoft Edge 实例可以使用的内存兆字节限制。
- [WebAppInstallForceList](./microsoft-edge-policies.md#webappinstallforcelist) - 配置强制安装的 Web 应用列表。
- [WebComponentsV0Enabled](./microsoft-edge-policies.md#webcomponentsv0enabled) - 重新启用 Web 组件 v0 API 至 M84。
- [WebRtcLocalIpsAllowedUrls](./microsoft-edge-policies.md#webrtclocalipsallowedurls) - 通过 WebRTC 管理本地 IP 地址的暴露。

#### <a name="deprecated-policies"></a>已弃用的策略

已弃用以下策略。

- [NewTabPageCompanyLogo](./microsoft-edge-policies.md#newtabpagecompanylogo) - 设置新标签页公司徽标。

### <a name="resolved-issues"></a>已解决的问题

- 修复了音频在 Citrix 环境中不工作的问题。
- 修复了 Microsoft Edge 和旧版 Microsoft Edge 并排体验导致旧链接损坏和崩溃的问题。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)