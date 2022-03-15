---
title: Internet Explorer (IE) 模式疑难解答和常见问题解答
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 01/18/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 疑难解答指南和Microsoft Edge Internet Explorer常见问题
ms.openlocfilehash: 064174744dbdc8d16912e4c196a8974c243de732
ms.sourcegitcommit: 556aca8dde42dd66364427f095e8e473b86651a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2022
ms.locfileid: "12445676"
---
# <a name="internet-explorer-ie-mode-troubleshooting-and-faq"></a>Internet Explorer (IE) 模式疑难解答和常见问题解答

> [!NOTE]
> 11 Internet Explorer 11 桌面应用程序将于 2022 年 6 月 15 日停用并停用支持。 To see the list of what's in scope， see the [Internet Explorer desktop app retirement FAQ](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549). 现在使用的 IE11 应用和网站可以在 Microsoft Edge 的 Internet Explorer 模式下打开。 若要了解更多信息，请参阅 Internet Explorer [on Windows 10文章Microsoft Edge](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)文章。

本文提供有关版本 77 或Microsoft Edge疑难解答提示和常见问题解答。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="what-if-i-need-help-with-setting-up-microsoft-edge-or-internet-explorer-mode"></a>如果需要有关设置或设置Microsoft Edge或Internet Explorer的帮助，Internet Explorer？

我们提供各种支持选项。 如果已Microsoft 统一支持，可以联系该支持服务，获得转换帮助。 此外，FastTrack 150 个或 150 多个付费席位的客户无需额外付费Windows 10。 [](https://www.microsoft.com/en-us/fasttrack/microsoft-365/microsoft-edge?rtc=1)

我们还推荐我们的 Microsoft Edge + Internet Explorer [模式入门指南](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWEHMs)和 [IE 模式博客系列](https://techcommunity.microsoft.com/t5/windows-10/internet-explorer-to-microsoft-edge-with-ie-mode-blog-series/m-p/2617124)。

## <a name="common-ie-mode-issues"></a>常见的 IE 模式问题

使用此部分作为指南，可帮助你排查并修复在使用 IE 模式Microsoft Edge两个最常见的问题。 这些问题包括：

- 文档模式配置不正确
- 不完整的中性网站配置

### <a name="incorrect-document-mode-configurations"></a>文档模式配置不正确

本节介绍这些症状，并提供了诊断和修复此问题的步骤。

#### <a name="symptoms"></a>症状

用户将遇到以下症状：
  
- 页面元素大小调整和定位可能已关闭，或者它们可能缺失 
- 某些功能可能会丢失或无法正常工作。 例如，使用Internet Explorer按钮不会执行任何操作或返回错误。

#### <a name="how-to-troubleshoot-and-fix"></a>如何排查和修复

常规策略是复制与 IE 模式站点列表中特定站点Internet Explorer 11 一起工作的相同设置。 使用 IE 11 中的 F12 开发人员工具栏的"模拟"选项卡（显示在下一个屏幕截图中）来调查要修复的方案。 若要打开开发人员工具栏，请按 F12 键，然后选择打开 **DevTools**。

![DevTools 视图上的"模拟"选项卡](./media/edge-ie-mode-faq/edge-ie-mode-emulation-tab.png)

"模拟"选项卡显示两条要关注的信息：文档模式 (1) 和下拉列表下方文本 (2) 。 此信息可以帮助解释我们为何在所查看的页面或 (11) 默认页面模式。

对于文档模式，可以显示不同的消息，在我们的示例中，消息包括：
  
- 通过 X-UA-compatible meta 标记
- 通过 X-UA-compatible HTTP 标头

两个 X-UA 兼容选项指示承载网站的网页或 Web 服务器显示浏览器应该使用的文档模式。  

我们希望在大多数情况下都遵守文档模式。 为此，我们需要在站点的 IE 模式站点列表条目中选择以下模式之一：

- 默认值
- IE8 Enterprise
- IE7 Enterprise

这些选项遵守网页或 Web 服务器指令。 请记住，我们需要选择一个包含指定文档模式的选项。 在屏幕截图示例中，由于指定的文档模式为 11，我们将选择"默认"，因为 IE8 Enterprise 和 IE7 Enterprise不支持 IE 11 文档模式。  

如果"文档"模式指示站点需要以下兼容性视图之一，则配置设置非常简单。

- 通过本地兼容性视图设置
- 通过兼容性视图列表
- 通过 Intranet 兼容性设置

由于所有兼容性视图设置都会导致"IE7 Enterprise"行为，因此在 IE 模式站点列表条目的"兼容模式"部分中选择此设置。

有关 IE 模式或 IE Internet Explorer用于进入一个文档模式而在另一个文档模式中使用的逻辑，请参阅弃用的文档模式和 Internet Explorer [11](/internet-explorer/ie11-deploy-guide/deprecated-document-modes) 文章。

一般规则是使用最新的基于逻辑的模式，该模式允许给定网站按预期方式工作。 我们将从默认模式开始，移动到 IE8 Enterprise模式，然后根据需要移动到 IE7 Enterprise模式。 此选择使子页面能够在必要时通过内置逻辑灵活使用不同的文档模式以满足其特定需求。 因此，所有网站页面不会锁定到一个特定的文档模式。  

下表列出了这些设置的可用文档模式。

| 基于逻辑的模式 | 默认值 | IE8 Enterprise | IE7 Enterprise |
|--|--|--|--|
| 可用的文档模式 | IE11 文档模式<br> IE10 文档模式<br>IE9 文档模式<br> IE8 文档模式<br>IE7 文档模式<br>IE5 Quirks 模式 | IE8 文档模式<br>IE7 文档模式<br>IE5 Quirks 模式   | IE7 文档模式<br>IE5 Quirks 模式  |

> [!NOTE]
> 在某些情况下，特定网站或页面需要特定的文档模式，以根据设计正常运行。 我们建议仅在基于逻辑的选项不有效时，才使用显式文档模式选项。

### <a name="incomplete-neutral-site-configurations"></a>不完整的中性网站配置

本节介绍这些症状，并提供了诊断和修复此问题的步骤。

#### <a name="symptoms"></a>症状
  
页面依赖 SSO 进行身份验证，但会多次提示用户提供凭据、遇到循环重定向行为、失败的身份验证错误或这些症状的某种组合。
  
#### <a name="how-to-troubleshoot-and-fix"></a>如何排查和修复
  
在开始分析 Microsoft Edge 中的失败工作流之前，请看一下 IE 模式"e"徽标的地址栏，如下一张屏幕截图所示。

![菜单栏上的 IE Microsoft Edge徽标。](./media/edge-ie-mode-faq/edge--ie-mode-logo.png)

如果在 SSO 身份验证过程中，我们看到了"e"，但它在重定向后消失，则此行为指向缺失的中性网站。 在Microsoft Edge进入 IE 模式后，我们需要一直保留在那里，以维护会话和 Cookie 信息。 如果 URL 显示在地址栏中足以标识它，则使用配置中性站点中所述的步骤将其添加到 IE 模式站点列表作为中性 [站点](/deployedge/edge-ie-mode-sitelist#configure-neutral-sites)。

通常，重定向周期发生得非常快，很难识别缺少的中性网站。 为了帮助进行此分析，我们使用内置于 Chromium 引擎的工具：**net-export**。

> [!TIP]
> 网络跟踪本质上是干扰的。 若要最大限度地减少干扰，请关闭正在调查的特定工作流不需要的所有其他浏览器实例和选项卡。

以下步骤介绍如何对中性站点配置进行故障排除。
  
1. 在"新建"选项卡Microsoft Edge并转到"edge://net-export *"*。
2. 选择 **"开始记录到**磁盘"，然后选择要保存生成的 .json 日志的位置。 完成疑难解答后，可以安全地删除此日志。
3. 打开另一 (使"net-export"选项卡保持打开) ，并重复失败的工作流。
4. 完成后，返回到"网络导出"选项卡并选择"停止 **日志记录"**。
5. 选择"netlog viewer"超链接。
6. 在生成的页面上，选择 **"选择**文件"，然后选择在步骤 2 中创建的 .json 文件。
7. 加载日志文件后 **，从左侧** 菜单中选择"事件"。
8. 滚动网络日志并标识起始 URL。  (您还可以使用搜索函数查找起始点。) 
9. 从起始点开始，向下滚动，在工作流中查找在 IE 模式网站列表中没有条目的 URL。 请特别注意具有 SSO、AUTH、LOGIN 等指示器的 URL。
10. 确定候选 URL 后，通过在"打开"下拉列表中选择"无"，将其添加到 IE 模式站点列表作为**** 中性站点。 再次测试工作流。

在某些情况下，需要多个中性网站条目，具体取决于特定的网站体系结构。 如果工作流在添加新的中性网站后仍失败，请重复此过程以捕获新的网络导出日志并执行另一个传递。

在极少数情况下，可能必须配置特定的共享 Cookie，以确保所需信息可进入 IE 模式站点。 如果您知道所需的特定 Cookie，您可以使用 Cookie 共享从一个站点到一个站点中的 Microsoft Edge 中所述的步骤配置[Internet Explorer](/deployedge/edge-ie-mode-add-guidance-cookieshare)。

### <a name="what-if-these-steps-dont-fix-the-issue"></a>如果这些步骤不能解决问题，如何操作？

本文旨在帮助解决最常见的 IE 模式配置问题，但可能并未涵盖每种可能的方案。 如果遇到无法修复并需要帮助的问题，请联系 应用保证 ， [https://aka.ms/AppAssure](https://aka.ms/AppAssure) 我们将帮助你解决问题。

## <a name="get-general-diagnostic-and-configuration-information"></a>获取常规诊断和配置信息

可以在 Microsoft Edge 的“兼容性”选项卡上获取 Internet Explorer 模式诊断信息。若要打开此选项卡，请转到 *edge://compat/iediagnostic*。 "Internet Explorer模式诊断信息"页可能会显示诊断消息，并且可以将诊断数据导出到 xml 文件。 此诊断信息页还提供了以下类别的配置信息：

- **注册表项检查。** （仅在检查失败时才显示。）检查是否在注册表中正确设置了 Internet Explorer 集成。 如果没有，用户可以选择"修复 **"** 来解决问题。
- **Internet Explorer 模式。** 根据配置和操作系统来显示使用的 API 版本。 如果无法显示，系统可能会提示用户安装 Windows 更新。
- **Internet Explorer 模式设置。** 显示 Internet Explorer 模式是否已启用，以及是如何配置的。
- **命令行。** 显示用于启动命令的命令行字符串和Microsoft Edge。
- **组策略设置。** 显示 IE 模式是否是使用组策略配置的，以及应用的策略。

### <a name="error-message-to-open-this-page-in-internet-explorer-mode-reinstall-microsoft-edge-with-administrator-privileges"></a>错误消息：“要在 Internet Explorer 模式下打开此页面，请使用管理员权限重新安装 Microsoft Edge。”

如果没有安装所有必需的更新，Windows此错误。 有关必需 Windows 和 Microsoft Edge 版本，请参阅[关于 IE 模式](./edge-ie-mode.md)中列出的先决条件。

如果已安装所有必需的更新Windows，则可能会看到此错误：：

- 你使用的是 Canary 渠道（默认安装在用户级别）。
- 你使用的是稳定渠道、Beta 渠道或 Dev 渠道，但在安装期间看到提升权限提示时，提升权限被取消了。 如果你取消提升权限提示，安装将继续在用户级别进行。
- 已在 Windows 功能中禁用 Internet Explorer 11。

可能的解决方案包括：

- 在系统级别针对任意渠道运行安装程序：`installer.exe --system-level`。
- 在 Windows 功能中启用 Internet Explorer 11。

若要检查 Microsoft Edge 是否安装在系统级别，请在 Microsoft Edge 地址栏中键入“edge://version”。 “可执行文件路径”将会显示以“C:\Program Files”** 开头的路径，这就表示是系统安装。 如果可执行文件路径以 *C：\Users* 开头，请卸载并重新安装Microsoft Edge管理员权限。

### <a name="error-message-to-open-this-page-in-ie-mode-try-restarting-microsoft-edge"></a>错误消息"若要在 IE 模式下打开此页面，请尝试重新启动Microsoft Edge"。

如果发生意外错误，则可能会看到此错误Internet Explorer。 重启 Microsoft Edge 通常可以修复此错误。

### <a name="error-message-turn-off-remote-debugging-to-open-this-site-in-ie-mode-otherwise-it-might-not-work-as-expected"></a>错误消息：“关闭远程调试以在 IE 模式下打开此站点，否则可能无法正常工作。”

如果远程调试并导航到配置为在 IE 模式下运行的网页，则可能会看到此错误。 你可以继续操作，但网页会使用 Microsoft Edge 呈现。

### <a name="error-message-could-not-retrieve-emie-site-list"></a>错误消息："无法检索 EMIE 站点列表。"

您可能在"网站列表 edge://compat/enterprise 显示** 此错误，指示网站列表下载失败。 从 Microsoft Edge版本 87 开始，当使用 [BlockThirdPartyCookies](/deployedge/microsoft-edge-policies#blockthirdpartycookies) 策略阻止第三方请求的 Cookie 时，也不允许 HTTP 身份验证。 可以使用 [CookiesAllowedForURLs](/deployedge/microsoft-edge-policies#cookiesallowedforurls) 策略为托管 Enterprise Mode Site List 的特定域允许 Cookie，以确保站点列表下载成功。

### <a name="error-message-the-connection-for-this-site-is-not-secure"></a>错误消息："此网站的连接不安全"

如果你尝试在 IE 模式下打开旧网站，并且该网站配置为在 TLS 1.0 或 TLS 1.1 中运行，则可能会发生此错误。 默认情况下，这些协议在 Microsoft Edge。 有关详细信息，请参阅 Plan [for change： TLS 1.0 and TLS 1.1 soon to be disabled by default](https://blogs.windows.com/msedgedev/2020/03/31/tls-1-0-tls-1-1-schedule-update-edge-ie11/)

### <a name="error-message-this-form-cannot-be-opened-in-a-web-browser-to-open-this-form-use-microsoft-infopath"></a>错误消息："无法在 Web 浏览器中打开此表单。 若要打开此表单，请使用 Microsoft InfoPath"

某些应用程序可能需要你在 IE 模式下加载网页。 可以在 IE 模式下使用 Microsoft Edge。

您可能还必须将模式站点`compat-mode`列表中的属性Enterprise设置为 **Default**。 有关详细信息，请参阅Enterprise[模式和Enterprise站点列表](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#enterprise-mode-and-the-enterprise-mode-site-list-1)。

> [!TIP]
> 用户可以轻松查看此站点列表和兼容性模式，在 Microsoft Edge 中键入 **about：compat**。

## <a name="frequently-asked-questions"></a>常见问题

### <a name="will-ie-mode-replace-internet-explorer-11"></a>IE 模式是否将替换 Internet Explorer 11？

是的，Internet Explorer 11 桌面应用程序将于 2022 年 6 月 15 日停用并停用支持。 若要了解范围内内容，请参阅生命周期 [常见问题解答 - Internet Explorer](/lifecycle/faq/internet-explorer-microsoft-edge)。 现在使用的 IE11 应用和网站可以在 Microsoft Edge 的 Internet Explorer 模式下打开。 若要了解更多信息，请参阅 Internet Explorer [on Windows 10 in Microsoft Edge](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。

### <a name="can-i-use-view-in-file-explorer-in-sharepoint-online-on-microsoft-edge"></a>我能否在 Microsoft Edge Online 的 SharePoint"在文件资源管理器Microsoft Edge？

从 Microsoft Edge版本 95 开始，你可以为 SharePoint Online 新式文档库启用****"在文件资源管理器中查看"功能。 若要使此体验可见且适用于你的用户，你需要启用 Microsoft Edge"在 Microsoft Edge 中为 SharePoint 页面配置文件资源管理器中的查看功能["](/deployedge/microsoft-edge-policies#configureviewinfileexplorer)策略，并更新 SharePoint Online 租户配置。 了解更多信息：SharePoint文件资源管理器查看Microsoft Edge [- SharePoint Microsoft 365 |Microsoft Docs](/SharePoint/sharepoint-view-in-edge)。

但是，建议的方法是将 [SharePoint 和 Teams](https://support.microsoft.com/office/sync-sharepoint-and-teams-files-with-your-computer-6de9ede8-5b6e-4503-80b2-6190f3354a88?ui=en-us&rs=en-us&ad=us) 文件与计算机同步或移动或复制 SharePoint 中的文件，而不是使用"在文件资源管理器中查看["](https://support.microsoft.com/office/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc?ui=en-us&rs=en-us&ad=us)选项来管理 SharePoint 外部的文件和文件夹。

### <a name="does-ie-mode-on-microsoft-edge-support-the-no-merge-option-that-was-supported-in-internet-explorer-11"></a>IE 模式是否Microsoft Edge 11 中支持的"不合并"Internet Explorer？

建议对网站中的非合并功能Microsoft Edge操作之一：

1. 在"Microsoft Edge配置文件 - 每个配置文件映射到 IE 模式页面的不同 IE 会话，因此其行为与"不合并"选项相同。
2. 使用`--user-data-dir=<path>`命令行，但每个会话的路径不同。 如果需要，你可以为用户创建一个实用工具来运行该实用工具Microsoft Edge并更改会话的路径。

如果上述选项均不适用于你的方案，从 Microsoft Edge版本 93 开始，Microsoft Edge上的 IE 模式将支持不合并。 对于最终用户，当从 IE 模式应用程序启动新的浏览器窗口时，它将位于单独的会话中，如 IE11 中的无合并行为。

对于每个 Microsoft Edge 窗口，首次访问该窗口中的 IE 模式选项卡时，如果它是指定的"不合并"网站，该窗口将锁定到其他"无合并"IE 会话中。  在锁定窗口中关闭最后一个 IE 模式选项卡Microsoft Edge，此窗口保持锁定状态。 此行为遵循以前的行为，其中用户可以通过不合并来启动 IE，Microsoft Edge其他机制不合并的情况下启动 IE。 新窗口中打开的所有网站 (window.open) 将遵守父进程的合并特性。

> [!NOTE]
> 不支持会话切换。 同一 IE 模式选项卡中的导航将使用相同的会话。

可以按照以下步骤验证 Microsoft Edge 93 或更高版本中的不合并行为：

1. 确保在版本 93 或Microsoft Edge上启用 IE 模式。
2. 可以通过将 merge-type 属性的值设置为"no-merge"来配置需要在 Enterprise 模式站点列表中阻止会话共享的站点。 此属性仅在 open-in 元素设置为 Microsoft Edge。 默认情况下，所有网站都有 merge 类型的 merge 值。  (**注意：** 添加或编辑网站时，edge://compat/sitelistmanager 集成的网站列表管理器** 工具包含"不合并"**** 复选框。) 

   ```
   <site url="contoso.com">
   <open-in merge-type="no-merge">IE11</open-in>
   </site>
   ```

3. 导航到配置为不合并的任何网站。 网站应在其自己未合并的 IE 会话中。 打开另一Microsoft Edge实例或窗口并导航到同一站点时，它应在其自己的 IE 会话中。 请注意，任务管理器iexplore.exe多个任务进程。

如果你有任何反馈，请通过我们的一个反馈渠道联系：Microsoft 支持或 [TechCommunity](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise) 论坛。

### <a name="can-i-save-links-as-webpages-in-internet-explorer-mode"></a>我能否将链接另存为 Internet Explorer 模式的网页？

可以，可以在 Microsoft Edge 中的 Internet Explorer 模式下在在上下文菜单中启用“目标另存为”选项。 为此，请配置组策略"允许在 Internet Explorer 模式下将目标另存*为"，* 该策略位于计算机配置 *>管理模板> Windows组件> Internet Explorer*。 保存机制的工作方式与在 web 中相同Internet Explorer如果目标另存为 html 文件，重新打开该文件将在 Microsoft Edge 中呈现页面。

若要将链接另存为网页，需要以下最低操作系统更新：

- Windows 10 版本 2004、Windows Server 版本 2004、Windows 10 版本 20H2：[KB4580364](https://support.microsoft.com/help/4580364/windows-10-update-kb4580364)
- Windows 10 版本 1903、Windows 10 版本 1909、Windows Server 版本 1903：[KB4580386](https://support.microsoft.com/help/4580386/windows-10-update-kb4580386)
- Windows 10 版本 1809、Windows Server 版本 1809、Windows Server 2019：[KB4580390](https://support.microsoft.com/help/4580390/windows-10-update-kb4580390)
- Windows 10 版本 1803：[KB4586785](https://support.microsoft.com/help/4586785/windows-10-update-kb4586785)
- Windows 10 版本 1607：[KB4586830](https://support.microsoft.com/help/4586830/windows-10-update-kb4586830)
- Windows 10 版本 1507：[KB4586787](https://support.microsoft.com/help/4586787/windows-10-update-kb4586787)

### <a name="can-i-test-a-site-in-microsoft-edge-while-it-is-configured-to-open-ie-mode-in-the-enterprise-mode-site-list"></a>当站点配置为在Microsoft Edge站点列表中打开 IE 模式时，我能否Enterprise测试该站点？

是的，在现代化旧网站时，可以在新网站上测试 IE 模式配置Microsoft Edge。 若要测试这些应用，可以配置 [InternetExplorerModeTabInEdgeModeAllowed](/deployedge/microsoft-edge-policies#internetexplorermodetabinedgemodeallowed) 策略。 如果启用此策略，用户可以通过选择 设置 和更多 (省略号图标 ...) > **More ToolsOpen** >  **sites in Edge** 模式，在 **Microsoft Edge** 中打开 IE 模式站点。

### <a name="how-can-i-debug-my-legacy-application-while-using-ie-mode-on-microsoft-edge"></a>如何在 IE 模式下对旧版应用程序进行调试Microsoft Edge？

可以使用 IEChooser 启动开发人员Internet Explorer调试 IE 模式选项卡的内容。 若要使用 IEChooser，请按照以下步骤操作：

1. 打开 IEChooser。
   - 打开“运行”对话框。 例如，按 `Windows logo key` + `R`。
   - 输入 `%systemroot%\system32\f12\IEChooser.exe`，然后选择"确定 **"**。
2. 在 IEChooser 中，选择"IE 模式"选项卡的条目。

### <a name="my-application-requires-transferring-post-data-between-ie-mode-and-microsoft-edge-is-this-supported"></a>我的应用程序需要在 IE 模式和 IE 模式之间传输 POST Microsoft Edge。 是否支持？

从 Microsoft Edge Beta 渠道版本 96 开始，在 Internet Explorer 模式Microsoft Edge导航将包括表单数据和额外的 HTTP 标头。 但是，如果表单数据包含文件附件，则这些附件不会在引擎之间传输。 可以使用 [InternetExplorerIntegrationComplexNavDataTypes](/deployedge/microsoft-edge-policies#internetexplorerintegrationcomplexnavdatatypes) 组策略选择此类导航中应包含哪些数据类型。

除了Microsoft Edge版本 96 之外，还需要安装以下Windows更新以用于此体验：

- Windows 11 [KB5007262](https://support.microsoft.com/topic/november-22-2021-kb5007262-os-build-22000-348-preview-7f3e18d7-4189-4882-b0e9-afc920253aee) 或更高版本
- Windows Server 2022 [KB5007254](
https://support.microsoft.com/topic/november-22-2021-kb5007254-os-build-20348-380-preview-9a960291-d62e-486a-adcc-6babe5ae6fc1) 或更高版本
- Windows 10 2004 版;Windows Server 版本 2004;Windows 10版本;Windows Server 版本 20H2 和 Windows 10 21H1 - [KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541) 或更高版本
- Windows 10版本 1909 [KB5007189](
https://support.microsoft.com/topic/november-9-2021-kb5007189-os-build-18362-1916-91b4647c-9979-4d84-8e64-efc8674e8c1f) 或更高版本

### <a name="where-can-i-find-the-reload-in-internet-explorer-mode-option"></a>在哪里可以找到"在Internet Explorer重新加载"选项？

此功能适用于 Microsoft Edge版本 92 或更高版本。 若要启用此选项，请配置"允许以Internet Explorer模式设置重新加载网站"，Microsoft Edge设置为"允许"。  有关详细信息，请参阅 [启用本地站点列表体验](/deployedge/edge-ie-mode-local-site-list#enable-the-local-site-list-experience)。

### <a name="where-is-the-file--new-session-option-in-microsoft-edge"></a>其中，"文件>新会话"选项位于Microsoft Edge？

新式浏览器解决方案可在 Microsoft Edge 中使用多个配置文件。 此功能允许你使用另一个帐户创建新会话。 以下资源提供有关多个配置文件的好处以及如何使用它们的信息。

- [视频：Microsoft Edge 和标识](/deployedge/microsoft-edge-video-identity)
- [现在可以更轻松地在工作或家使用多个配置文件Microsoft Edge](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/)

### <a name="why-am-i-getting-multiple-authentication-prompts-when-running-a-page-in-ie-mode-on-microsoft-edge"></a>为什么在 IE 模式下运行页面时，我收到多个身份验证Microsoft Edge？

客户端证书可能在 IE 模式下请求两次。 第一次时，证书选择对话框将在 IE 模式下显示，第二次在 IE 模式下Microsoft Edge。 帧进程和窗口进程都需要请求身份验证。

创建 favicon 缓存后，系统不会再次要求您提供客户端证书，除非您删除缓存。 或者，可以在服务器配置（如 IIS）中设置规则，不要求使用客户端证书作为 favicon。

### <a name="why-are-there-rendering-issues-like-text-wrapping-and-content-truncation-when-child-windows-are-running-in-ie-mode-in-microsoft-edge"></a>为什么当子窗口在 IE 模式下运行时，文本换行和内容截断等呈现Microsoft Edge？

以 IE 模式呈现的子窗口的内容区域Microsoft Edge 11 上的内容区域略有不同Internet Explorer不同。 如果网页的设计采用基于像素的对齐方式或定位，则可能会遇到呈现错误、文本换行等情况。

在版本 95 Microsoft Edge添加了两个策略设置，用于指定对通过 方法从 IE 模式网站生成的弹出窗口的高度和宽度进行自定义`window.open`调整。 可以使用以下策略调整窗口大小：

- [InternetExplorerIntegrationWindowOpenHeightAdjustment](/deployedge/microsoft-edge-policies#internetexplorerintegrationwindowopenheightadjustment) - 此设置允许你指定自定义调整到从 Internet Explorer 模式网站生成的弹出窗口的高度。
- [InternetExplorerIntegrationWindowOpenWidthAdjustment](/deployedge/microsoft-edge-policies#internetexplorerintegrationwindowopenwidthadjustment) - 此设置允许你指定自定义调整从模式网站生成的弹出窗口的宽度Internet Explorer调整。

### <a name="why-arent-pop-ups-or-redirected-websites-loading-in-ie-mode-or-in-internet-explorer-11"></a>为什么未在 IE 模式或 11 中加载弹出窗口或重定向Internet Explorer？

配置 IE 模式后，某些网站（尤其是创建新窗口的网站或重定向的网站）可能不会在 IE 模式下呈现或在 Internet Explorer 11 中打开。

对于此类重定向网站，您可以使用站点 `allow-redirect="true"` 列表配置中的 。 有关详细信息，请参阅更新 [的架构元素](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance#updated-schema-elements)。

### <a name="why-arent-websites-loading-in-ie-mode-when-i-launch-microsoft-edge-for-the-first-time"></a>为什么我在首次启动网站时未在 IE Microsoft Edge加载网站？

Microsoft Edge应用 IE 模式设置之前，需要下载 IE 模式站点列表。 当浏览器启动时，此过程可能无法完成。 有一个可在加载网站之前强制加载站点列表的策略。 有关详细信息，请参阅 [DelayNavigationsForInitialSiteListDownload](/deployedge/microsoft-edge-policies#delaynavigationsforinitialsitelistdownload) 策略。

### <a name="why-cant-i-open-files-or-pages-that-are-found-by-using-file-urls-in-microsoft-edge"></a>Why can't I open files or pages that are found by using file:// URLs in Microsoft Edge？

由于Chromium限制，需要使用 IE 模式。 可以使用 IE Microsoft Edge功能在 Intranet 区域中加载托管 file:// 协议的网页。**** 可以使用 [IntranetFileLinksEnabled](/deployedge/microsoft-edge-policies#intranetfilelinksenabled) 组策略启用此功能。

## <a name="see-also"></a>另请参阅
  
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [关于 IE 模式](./edge-ie-mode.md)
- [其他企业模式信息](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
