---
title: Microsoft Edge Beta 渠道发行说明
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 11/03/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge Beta 渠道发行说明
ms.openlocfilehash: bcc2ecf91c6d90443de26b5bff1c744d7582aa18
ms.sourcegitcommit: 4ec03873a85f065d9bfa6203cfe6c3e938f79bc5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "12155099"
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

- **改进了 IE 模式和新式浏览器之间的切换。**  从此版本的 Microsoft Edge开始，Microsoft Edge 和 Internet Explorer 模式之间的导航将包括表单数据和其他 HTTP 标头。 引用者标头、帖子数据、表单数据和请求方法将跨这两种体验正确转发。 您可以使用 [InternetExplorerIntegrationComplexNavDataTypes 策略指定应包含哪些](/deployedge/microsoft-edge-policies#internetexplorerintegrationcomplexnavdatatypes) 数据类型。 有关详细信息，请参阅此常见问题解答：[我的应用程序需要在 IE](./edge-ie-mode-faq.md#my-application-requires-transferring-post-data-between-ie-mode-and-microsoft-edge-is-this-supported)模式和 IE 模式之间传输 POST Microsoft Edge。

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

<!-- archive from Version 94.0.992.9: September 2 to Version 92.0.902.40: July 6 -->
<!--Archive on Oct 27 From Version 92.0.902.22: June 21 to Version 89.0.774.23: February 8  -->
<!--- Archived from Version 87.0.664.18: October 26 to to version 89.0.774.18: February 3 ---->
<!--- Archived from Version 87.0.664.12: October 20 to to version 86.0.622.15: September 14 ---->
<!--- Archived to version 86.0.622.11: September 9 ---->
<!--- Archived to version 85.0.564.18: July 28 ---->

## <a name="see-also"></a>另请参阅

- [Microsoft Edge 企业版登录页面](https://aka.ms/EdgeEnterprise)
