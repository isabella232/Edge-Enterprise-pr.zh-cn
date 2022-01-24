---
title: Microsoft Edge Beta 渠道发行说明
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 01/07/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge Beta 渠道发行说明
ms.openlocfilehash: ddb745c206dc392dc1dbb46a0522db9648ba624e
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2022
ms.locfileid: "12297710"
---
# <a name="release-notes-for-microsoft-edge-beta-channel"></a>Microsoft Edge Beta 渠道的发行说明

本发行说明提供有关 Microsoft Edge Beta 渠道中包含的新功能和非安全更新的信息。 这些发行说明的存档版本可在存档发行说明中Microsoft Edge Beta[频道。](./microsoft-edge-relnote-archive-beta-channel.md)

> [!NOTE]
> Microsoft Edge Web 平台不断发展以改进用户体验、安全性和隐私。 要了解详细信息，请参阅 [Microsoft Edge 中即将推出的影响站点兼容性的更改](/microsoft-edge/web-platform/site-impacting-changes)。

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

## <a name="version-970107221-december-1"></a>版本 97.0.1072.21：12 月 1 日

### <a name="feature-updates"></a>功能更新

- **在设备上登录多个工作或学校帐户时，使用当前配置文件登录网站。** 当在设备上登录多个工作或学校帐户时，将要求用户从帐户选取器中选择一个帐户，以继续访问网站。 在此版本中，系统将提示用户Microsoft Edge登录到使用登录到当前配置文件的工作和学校帐户自动登录网站。 用户可以在"配置文件"首选项**中设置和关闭此功能**。

- **在 macOS 上添加对 Microsoft Endpoint Data Loss Prevention (DLP) 的支持。** Microsoft Endpoint DLP 策略强制在 macOS 上本地可用。

- **打开数字签名的 PDF 文件。**  数字签名广泛使用以验证文档的真实性和更改。 用户可以直接从浏览器验证 PDF 文件的签名，而无需任何外接程序。

- **引文中的引Microsoft Edge。** 研究源是学生常见的要求。 他们必须管理许多研究参考和源，这不是一项简单的任务。 他们还必须将这些引文转换为正确的引文格式，如 APA、MLA 和 Chicago。 预览版中目前Microsoft Edge ("引文"这一) 为学生提供了一种在在线研究时管理和生成引文的更好方法。 在"集合"或 设置 及更多** (Alt-F) **中打开引文后，Microsoft Edge 自动生成学生稍后可以使用的引文，以便他们专注于研究。 完成后，他们可以轻松地将这些引文编译为最终可交付结果。 有关详细信息，请参阅预览引文[Microsoft Edge。](https://blogs.windows.com/msedgedev/2021/11/04/preview-citations-feature-edge/)

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

- [AccessibilityImageLabelsEnabled](/DeployEdge/microsoft-edge-policies#accessibilityimagelabelsenabled) - 从 Microsoft 启用获取图像说明
- [CORSNonWildcardRequestHeadersSupport](/DeployEdge/microsoft-edge-policies#corsnonwildcardrequestheaderssupport) - 启用 CORS 非通配符请求标头支持
- [EdgeDiscoverEnabled](/DeployEdge/microsoft-edge-policies#edgediscoverenabled) - 发现Microsoft Edge
- [EdgeEnhanceImagesEnabled](/DeployEdge/microsoft-edge-policies#edgeenhanceimagesenabled) - 增强已启用的图像
- [InternetExplorerModeTabInEdgeModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorermodetabinedgemodeallowed) - 允许为 Internet Explorer 模式配置的站点在 Microsoft Edge
- [SameOriginTabCaptureAllowedByOrigins](/DeployEdge/microsoft-edge-policies#sameorigintabcaptureallowedbyorigins) - 允许这些源捕获同源选项卡
- [ScreenCaptureAllowedByOrigins](/DeployEdge/microsoft-edge-policies#screencaptureallowedbyorigins) - 允许通过这些源捕获桌面、窗口和选项卡
- [SerialAllowAllPortsForUrls](/DeployEdge/microsoft-edge-policies#serialallowallportsforurls) - 自动授予站点连接所有串行端口的权限
- [SerialAllowUsbDevicesForUrls](/DeployEdge/microsoft-edge-policies#serialallowusbdevicesforurls) - 自动授予站点连接到 USB 串行设备的权限
- [SmartScreenDnsRequestsEnabled](/DeployEdge/microsoft-edge-policies#smartscreendnsrequestsenabled) - Microsoft Defender SmartScreen DNS 请求
- [TabCaptureAllowedByOrigins](/DeployEdge/microsoft-edge-policies#tabcaptureallowedbyorigins) - 允许这些原点捕获 Tab
- [WebSQLInThirdPartyContextEnabled](/DeployEdge/microsoft-edge-policies#websqlinthirdpartycontextenabled) - 强制重新启用第三方上下文中的 WebSQL
- [WindowCaptureAllowedByOrigins](/DeployEdge/microsoft-edge-policies#windowcaptureallowedbyorigins) - 允许通过这些原点捕获 Window 和 Tab

## <a name="version-960105434-november-23"></a>版本 96.0.1054.34：11 月 23 日

修复了各种 bug 和性能问题。

## <a name="version-960105426-november-17"></a>版本 96.0.1054.26：11 月 17 日

修复了各种 bug 和性能问题。

## <a name="version-960105424-november-16"></a>版本 96.0.1054.24：11 月 16 日

修复了各种 bug 和性能问题。

## <a name="version-960105413-november-5"></a>版本 96.0.1054.13：11 月 5 日

修复了各种 bug 和性能问题。

## <a name="version-96010548-november-1"></a>版本 96.0.1054.8：11 月 1 日

### <a name="feature-updates"></a>功能更新

- **直接通过协议 (PWA) 启动渐进式 Web 应用。** 让已安装的 PWA 处理使用特定协议的链接，实现更加集成的体验。

- **了解如何使用数学规划求解求解数学问题。** 我们很高兴地宣布，您可以使用数学规划求解在 Microsoft Edge中获取有关各种数学概念的帮助。 这些概念包括从算术和二次方等式到三角法和计算。 利用数学规划求解，您可以拍摄手写或打印的数学问题的图片，然后提供一个即时解决方案以及分步说明，以帮助您了解如何在没有帮助的情况下找到解决方案。 数学规划求解还附带数学键盘，可用于轻松键入数学问题。 此键盘无需四处搜索传统键盘来查找所需的数学字符。 解决你的问题后，数学规划求解提供了一些选项，可以继续学习测验、工作表和视频教程。

- **PDF 上的任意多边形突出显示。** 通过添加任意格式突出显示器改进了 PDF 查看和标记体验。 你可以突出显示你无法访问的 PDF 中的部分和扫描过的文档。

- **硬件强制执行的堆栈保护。**  Microsoft Edge将开始支持更安全的浏览模式，该模式对 Intel 第 11 代受支持硬件上的浏览器进程使用 (控制流。 或 AMD 管理 3) 。 注意：因为这是受控功能推出，你可能不会注意到此功能在所有设备上都已启用。 你可以启用或禁用硬件强制执行的堆栈保护，方法为使用组策略操作 IFEO (图像) 执行选项。

- **用于错误等同网站的新警告对话框。** 浏览器现在将在 URL 类似于其他网站的一些网站上显示警告。 此 UI 使用客户端启发来提醒用户有关可能欺骗热门网站的网站。 有关详细信息，请参阅什么是错[位？。](https://support.microsoft.com/topic/what-is-typosquatting-54a18872-8459-4d47-b3e3-d84d9a362eb0)

- **改进了 IE 模式和新式浏览器之间的切换。**  从此版本的 Microsoft Edge开始，Microsoft Edge 和 Internet Explorer 模式之间的导航将包括表单数据和其他 HTTP 标头。 引用者标头、帖子数据、表单数据和请求方法将跨这两种体验正确转发。 您可以使用 [InternetExplorerIntegrationComplexNavDataTypes 策略指定应包含哪些](/deployedge/microsoft-edge-policies#internetexplorerintegrationcomplexnavdatatypes) 数据类型。 有关详细信息，请参阅此常见问题解答：[我的应用程序需要在 IE](./edge-ie-mode-faq.md#my-application-requires-transferring-post-data-between-ie-mode-and-microsoft-edge-is-this-supported)模式和 IE 模式之间传输 POST Microsoft Edge。

- **公共预览版中适用于 IE 模式的云站点列表管理。**  通过云站点列表管理，可以在云中管理 IE 模式的网站列表，而无需本地基础结构来托管组织的站点列表。 您可以使用云站点列表管理中心中的Microsoft Edge网站列表体验来访问Microsoft 365 管理管理功能。 若要了解更多信息，请参阅适用于 [IE 模式的云站点列表管理 (公共预览) ](./edge-ie-mode-cloud-site-list-mgmt.md) 文章。

- **使用 Microsoft Edge WSUS 更新 WebWiew2。** 使用 WSUS 更新 Microsoft Edge IT 管理员还将能够使用 WSUS Microsoft Edge WebView2。 此功能使管理员能够更轻松地为脱机设备提供服务。

- **Server 的 WSUS 更新。** Microsoft Edge 渠道的 WSUS 和目录更新 (Stable、Beta、Dev) 现在将应用于安装了 Microsoft Edge 的 Windows Server SK，包括 Windows Server 2022。 若要详细了解如何为 WSUS 配置 WSUS Microsoft Edge，请参阅[Update Microsoft Edge](https://docs.microsoft.com/mem/configmgr/apps/deploy-use/deploy-edge?bc=https%3A%2F%2Fdocs.microsoft.com%2FDeployEdge%2Fbreadcrumb%2Ftoc.json&toc=https%3A%2F%2Fdocs.microsoft.com%2FDeployEdge%2Ftoc.json#update-microsoft-edge)。

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

<!-- archive from version 95.0.1020.9: September 28 to version 94.0.992.14: September 7 ---->
<!-- archive from Version 94.0.992.9: September 2 to Version 92.0.902.40: July 6 -->
<!--Archive on Oct 27 From Version 92.0.902.22: June 21 to Version 89.0.774.23: February 8  -->
<!--- Archived from Version 87.0.664.18: October 26 to to version 89.0.774.18: February 3 ---->
<!--- Archived from Version 87.0.664.12: October 20 to to version 86.0.622.15: September 14 ---->
<!--- Archived to version 86.0.622.11: September 9 ---->
<!--- Archived to version 85.0.564.18: July 28 ---->

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
