---
title: Internet Explorer (IE) 模式故障排除和常见问题解答
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 04/25/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Internet Explorer 模式Microsoft Edge疑难解答指南和常见问题解答
ms.openlocfilehash: 076ce09e3ec1c0e392b1bf1f311bbc17a2f62093
ms.sourcegitcommit: 592f6e40b13e28af588473b2a75c3ae697e5db2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2022
ms.locfileid: "12505355"
---
# <a name="internet-explorer-ie-mode-troubleshooting-and-faq"></a>Internet Explorer (IE) 模式故障排除和常见问题解答

> [!NOTE]
> Internet Explorer 11 桌面应用程序将于 2022 年 6 月 15 日停用并停止支持。 若要查看范围内的内容列表，请参阅 [Internet Explorer 11 桌面应用停用常见问题解答](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)。 现在使用的 IE11 应用和网站可以在 Microsoft Edge 的 Internet Explorer 模式下打开。 若要了解详细信息，请参阅[Windows 10上的 Internet Explorer 的未来Microsoft Edge](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)博客文章。

本文提供Microsoft Edge版本 77 或更高版本的疑难解答提示和常见问题解答。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="what-if-i-need-help-with-setting-up-microsoft-edge-or-internet-explorer-mode"></a>如果需要有关设置Microsoft Edge或 Internet Explorer 模式的帮助，该怎么办？

我们提供各种支持选项。 如果有Microsoft 统一支持，可以联系该支持服务以获取过渡帮助。 此外 [FastTrack](https://www.microsoft.com/en-us/fasttrack/microsoft-365/microsoft-edge?rtc=1)，对于拥有 150 个或更多Windows 10付费席位的客户，无需额外付费。

我们还建议我们Microsoft Edge + Internet Explorer 模式[入门指南](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWEHMs)和 [IE 模式博客系列](https://techcommunity.microsoft.com/t5/windows-10/internet-explorer-to-microsoft-edge-with-ie-mode-blog-series/m-p/2617124)。

## <a name="are-there-any-tools-that-i-can-use-to-guide-me-through-ie-mode-troubleshooting"></a>是否有任何工具可用于指导我完成 IE 模式故障排除？

是的， [Microsoft 虚拟代理](https://go.microsoft.com/fwlink/?linkid=2194137) 提供了一个基于方案的引导式演练，用于排查 IE 模式问题。

## <a name="common-ie-mode-issues"></a>常见的 IE 模式问题

使用本部分作为指南，帮助你在使用 IE 模式迁移到Microsoft Edge时排查和修复两个最常见的问题。 这些问题包括：

- 文档模式配置不正确
- 不完整的中性站点配置

### <a name="incorrect-document-mode-configurations"></a>文档模式配置不正确

本部分介绍症状，并提供诊断和解决此问题的步骤。

#### <a name="symptoms"></a>症状

用户将遇到以下症状：
  
- 页面元素的大小和定位可能已关闭，或者它们可能缺失 
- 某些功能可能会丢失或无法按预期工作。 例如，使用 Internet Explorer 的按钮不会执行任何操作或返回错误。

#### <a name="how-to-troubleshoot-and-fix"></a>如何进行故障排除和修复

一般策略是复制与 Internet Explorer 11 在 IE 模式站点列表中的特定站点相同的设置。 在 IE 11 中使用 F12 开发人员工具栏的“仿真”选项卡，在下一个屏幕截图中显示，用于调查要修复的方案。 若要打开开发人员工具栏，请按 F12 键，然后选择 **“打开 DevTools**”。

![DevTools 视图上的“仿真”选项卡](./media/edge-ie-mode-faq/edge-ie-mode-emulation-tab.png)

“仿真”选项卡显示两个要关注的信息：文档模式 (1) ，下拉列表下方的文本 (2) 。 此信息有助于解释为什么我们处于要查看的页面或网站的 11 (默认) 模式。

可以为文档模式显示不同的消息，在我们的示例中，这些消息是：
  
- 通过 X-UA 兼容的元标记
- 通过 X-UA 兼容的 HTTP 标头

两个 X-UA 兼容选项指示托管网站的网页或 Web 服务器显示浏览器应使用的文档模式。  

在几乎所有情况下，我们都希望遵循文档模式。 为此，我们需要在网站的 IE 模式站点列表条目中选择以下模式之一：

- 默认值
- IE8 Enterprise
- IE7 Enterprise

这些选项遵循网页或 Web 服务器指令。 请记住，我们需要选择包含指定文档模式的选项。 在屏幕截图示例中，由于指定的文档模式为 11，因此我们将选择“默认”，因为 IE8 Enterprise和 IE7 Enterprise不支持 IE 11 文档模式。  

如果文档模式指示站点需要以下兼容性视图之一，则配置设置非常简单。

- 通过本地兼容性视图设置
- 通过兼容性视图列表
- 通过 Intranet 兼容性设置

由于所有兼容性视图设置都会导致“IE7 Enterprise”行为，因此请在 IE 模式网站列表条目的“兼容模式”部分中选择此设置。

有关 Internet Explorer 或 IE 模式用于在一个文档模式下登陆到另一个文档模式的逻辑的详细信息，请参阅 [已弃用的文档模式和 Internet Explorer 11](/internet-explorer/ie11-deploy-guide/deprecated-document-modes) 文章。

一般规则是使用当前基于逻辑的模式，允许给定站点按预期工作。 我们将从默认模式开始，移到 IE8 Enterprise模式，然后根据需要转到 IE7 Enterprise模式。 此选择使子页面能够根据需要通过内置逻辑灵活地使用不同的文档模式，以满足其特定需求。 因此，所有网站页面不会锁定到一个特定的文档模式。  

下表列出了这些设置的可用文档模式。

| 基于逻辑的模式 | 默认值 | IE8 Enterprise | IE7 Enterprise |
|--|--|--|--|
| 可用文档模式 | IE11 Doc 模式<br> IE10 Doc 模式<br>IE9 Doc 模式<br> IE8 Doc 模式<br>IE7 Doc 模式<br>IE5 Quirks 模式 | IE8 Doc 模式<br>IE7 Doc 模式<br>IE5 Quirks 模式   | IE7 Doc 模式<br>IE5 Quirks 模式  |

> [!NOTE]
> 在某些情况下，特定网站或页面需要特定的文档模式才能按设计运行。 建议仅在基于逻辑的选项无效时使用显式文档模式选项。

### <a name="incomplete-neutral-site-configurations"></a>不完整的中性站点配置

本部分介绍症状，并提供诊断和解决此问题的步骤。

#### <a name="symptoms"></a>症状
  
页面依赖于 SSO 进行身份验证，但系统会多次提示用户输入凭据、遇到循环重定向行为、身份验证错误失败或出现这些症状的一些组合。
  
#### <a name="how-to-troubleshoot-and-fix"></a>如何进行故障排除和修复
  
在开始分析Microsoft Edge中失败的工作流之前，请查看 IE 模式“e”徽标的地址栏，如下一屏幕截图所示。

![菜单栏上的 IE 徽标Microsoft Edge。](./media/edge-ie-mode-faq/edge--ie-mode-logo.png)

如果在 SSO 身份验证过程中看到“e”，但在重定向后消失，则此行为指向缺少的中性站点。 Microsoft Edge进入 IE 模式后，我们需要留在那里维护会话和 Cookie 信息。 如果 URL 显示在地址栏中足够长的时间来标识它，请使用 [配置中性网站](/deployedge/edge-ie-mode-sitelist#configure-neutral-sites)中所述的步骤将其添加到 IE 模式站点列表中作为中性站点。

通常，重定向周期发生得如此之快，以至于很难识别缺失的中性站点。 为了帮助进行此分析，我们使用内置于Chromium引擎中的工具：**net-export**。

> [!TIP]
> 网络跟踪本质上是嘈杂的。 若要最大程度地减少干扰，请关闭所调查特定工作流不需要的所有其他浏览器实例和选项卡。

以下步骤介绍如何排查中性站点配置问题。
  
1. 在Microsoft Edge中打开新选项卡，然后转到 *edge://net-export*。
2. 选择 **“开始记录到磁盘**”，然后选择要保存生成的 .json 日志的位置。 完成故障排除后，可以安全地删除此日志。
3. 打开另一个选项卡 (使“净导出”选项卡保持打开) ，并重复失败的工作流。
4. 完成后，返回到“净导出”选项卡，然后选择 **“停止日志记录**”。
5. 选择“netlog 查看器”超链接。
6. 在生成的页面上， **选择“选择文件**”，然后选择在步骤 2 中创建的 .json 文件。
7. 加载日志文件后，从左侧菜单中选择 **“事件** ”。
8. 滚动浏览网络日志并标识起始 URL。  (还可以使用搜索函数查找起点。) 
9. 从起点开始，向下滚动，在工作流中查找没有 IE 模式站点列表中的条目的 URL。 特别注意具有 SSO、AUTH、LOGIN 等指标的 URL。
10. 标识候选 URL 后，通过在“开放式”下拉列表中选择 **“无** ”，将其添加到 IE 模式站点列表中作为中性网站。 再次测试工作流。

在某些情况下，需要多个中性网站条目，具体取决于特定的站点体系结构。 如果添加新的中性站点后工作流仍然失败，请重复该过程以捕获新的净导出日志并执行另一个传递。

在某些极少数实例中，可能需要配置特定的共享 Cookie，以确保所需的信息到达 IE 模式站点。 如果知道需要特定的 Cookie，可以使用 [Cookie 共享中介绍的从Microsoft Edge到 Internet Explorer](/deployedge/edge-ie-mode-add-guidance-cookieshare) 的步骤来配置 Cookie 共享。

### <a name="what-if-these-steps-dont-fix-the-issue"></a>如果这些步骤未解决问题，该怎么办？

本文旨在帮助排查最常见的 IE 模式配置问题，但可能无法涵盖所有可能的方案。 如果遇到无法修复且需要帮助的问题，请联系 App Assure [https://aka.ms/AppAssure](https://aka.ms/AppAssure) ，我们将帮助你解决问题。

## <a name="get-general-diagnostic-and-configuration-information"></a>获取常规诊断和配置信息

可以在 Microsoft Edge 的“兼容性”选项卡上获取 Internet Explorer 模式诊断信息。若要打开此选项卡，请转到 *edge://compat/iediagnostic*。 “Internet Explorer 模式诊断信息”页可能会显示诊断消息，你可以将诊断数据导出到 xml 文件。 此诊断信息页还提供以下类别的配置信息：

- **注册表项检查。** （仅在检查失败时才显示。）检查是否在注册表中正确设置了 Internet Explorer 集成。 如果没有，用户可以选择 **“修复”** 来解决问题。
- **Internet Explorer 模式。** 根据配置和操作系统来显示使用的 API 版本。 如果无法显示，系统可能会提示用户安装 Windows 更新。
- **Internet Explorer 模式设置。** 显示 Internet Explorer 模式是否已启用，以及是如何配置的。
- **命令行。** 显示用于启动Microsoft Edge的命令行字符串和开关。
- **组策略设置。** 显示 IE 模式是否是使用组策略配置的，以及应用的策略。

### <a name="error-message-to-open-this-page-in-internet-explorer-mode-reinstall-microsoft-edge-with-administrator-privileges"></a>错误消息：“要在 Internet Explorer 模式下打开此页面，请使用管理员权限重新安装 Microsoft Edge。”

如果没有所有必需Windows更新，则可能会看到此错误。 有关必需 Windows 和 Microsoft Edge 版本，请参阅[关于 IE 模式](./edge-ie-mode.md)中列出的先决条件。

如果已安装所有所需的Windows更新，则在以下情况下可能会看到此错误：

- 你使用的是 Canary 渠道（默认安装在用户级别）。
- 你使用的是稳定渠道、Beta 渠道或 Dev 渠道，但在安装期间看到提升权限提示时，提升权限被取消了。 如果你取消提升权限提示，安装将继续在用户级别进行。
- 已在 Windows 功能中禁用 Internet Explorer 11。

可能的解决方案包括：

- 在系统级别针对任意渠道运行安装程序：`installer.exe --system-level`。
- 在 Windows 功能中启用 Internet Explorer 11。

若要检查 Microsoft Edge 是否安装在系统级别，请在 Microsoft Edge 地址栏中键入“edge://version”。 “可执行文件路径”将会显示以“C:\Program Files”** 开头的路径，这就表示是系统安装。 如果可执行路径以 *C：\Users* 开头，请卸载，然后使用管理员权限重新安装Microsoft Edge。

### <a name="error-message-to-open-this-page-in-ie-mode-try-restarting-microsoft-edge"></a>错误消息“若要在 IE 模式下打开此页面，请尝试重启Microsoft Edge”。

如果 Internet Explorer 中出现意外错误，可能会看到此错误。 重启 Microsoft Edge 通常可以修复此错误。

### <a name="error-message-turn-off-remote-debugging-to-open-this-site-in-ie-mode-otherwise-it-might-not-work-as-expected"></a>错误消息：“关闭远程调试以在 IE 模式下打开此站点，否则可能无法正常工作。”

如果要远程调试并导航到配置为在 IE 模式下运行的网页，可能会看到此错误。 你可以继续操作，但网页会使用 Microsoft Edge 呈现。

### <a name="error-message-could-not-retrieve-emie-site-list"></a>错误消息：“无法检索 EMIE 站点列表。

可能会在 *edge://compat/enterprise* 页上看到此错误，指示网站列表下载失败。 从 Microsoft Edge 版本 87 开始，当使用 [BlockThirdPartyCookies](/deployedge/microsoft-edge-policies#blockthirdpartycookies) 策略阻止第三方请求的 Cookie 时，也不允许进行 HTTP 身份验证。 可以使用 [CookiesAllowedForURLs](/deployedge/microsoft-edge-policies#cookiesallowedforurls) 策略为托管 Enterprise Mode Site List 的特定域允许 Cookie，以确保站点列表下载成功。

### <a name="error-message-the-connection-for-this-site-is-not-secure"></a>错误消息：“此站点的连接不安全”

如果尝试在 IE 模式下打开旧网站，并且网站配置为在 TLS 1.0 或 TLS 1.1 中运行，则可能会发生此错误。 默认情况下，这些协议在Microsoft Edge中处于禁用状态。 有关详细信息，请参阅 [计划更改：默认情况下即将禁用 TLS 1.0 和 TLS 1.1](https://blogs.windows.com/msedgedev/2020/03/31/tls-1-0-tls-1-1-schedule-update-edge-ie11/)

### <a name="error-message-this-form-cannot-be-opened-in-a-web-browser-to-open-this-form-use-microsoft-infopath"></a>错误消息：“无法在 Web 浏览器中打开此窗体。 若要打开此窗体，请使用 Microsoft InfoPath”

某些应用程序可能需要在 IE 模式下加载网页。 可以在Microsoft Edge中使用 IE 模式功能。

可能还必须将Enterprise模式站点列表中的属性设置`compat-mode`为**默认**值。 有关详细信息，请参阅[Enterprise模式和Enterprise模式站点列表](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#enterprise-mode-and-the-enterprise-mode-site-list-1)。

> [!TIP]
> 用户可以通过在Microsoft Edge中键入 **about：compat** 来轻松查看此网站列表和兼容模式。

## <a name="frequently-asked-questions"></a>常见问题

### <a name="will-ie-mode-replace-internet-explorer-11"></a>IE 模式是否将替换 Internet Explorer 11？

是的，Internet Explorer 11 桌面应用程序将于 2022 年 6 月 15 日停用并停止支持。 若要查看作用域中的内容，请参阅 [生命周期常见问题解答 - Internet Explorer](/lifecycle/faq/internet-explorer-microsoft-edge)。 现在使用的 IE11 应用和网站可以在 Microsoft Edge 的 Internet Explorer 模式下打开。 若要了解详细信息，请阅读[Windows 10上的 Internet Explorer 的未来Microsoft Edge](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。

### <a name="can-i-use-view-in-file-explorer-in-sharepoint-online-on-microsoft-edge"></a>是否可以在 Microsoft Edge 上的 SharePoint Online 中使用“文件资源管理器中的视图”？

从 Microsoft Edge 版本 95 开始，可以为SharePoint联机新式文档库启用**视图文件资源管理器**功能。 若要使此体验可见且适用于用户，需要启用Microsoft Edge[“为Microsoft Edge中的SharePoint页面配置视图文件资源管理器功能”](/deployedge/microsoft-edge-policies#configureviewinfileexplorer)策略，并更新SharePoint联机租户配置。 了解详细信息：[使用Microsoft Edge中的文件资源管理器查看SharePoint文件 - SharePoint Microsoft 365 |Microsoft Docs](/SharePoint/sharepoint-view-in-edge)。

但是，建议在SharePoint之外管理文件和文件夹的方法不是在文件资源管理器选项中使用“视图”，而是使用[计算机同步SharePoint和Teams文件](https://support.microsoft.com/office/sync-sharepoint-and-teams-files-with-your-computer-6de9ede8-5b6e-4503-80b2-6190f3354a88?ui=en-us&rs=en-us&ad=us)，[或者在SharePoint中移动或复制文件](https://support.microsoft.com/office/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc?ui=en-us&rs=en-us&ad=us)。

### <a name="does-ie-mode-on-microsoft-edge-support-the-no-merge-option-that-was-supported-in-internet-explorer-11"></a>Microsoft Edge上的 IE 模式是否支持 Internet Explorer 11 中支持的“无合并”选项？

Microsoft Edge中无合并功能的建议替代方法是以下操作之一：

1. 在Microsoft Edge中使用配置文件 - 每个配置文件映射到 IE 模式页面的不同 IE 会话，因此它的行为与无合并选项相同。
2. 使用`--user-data-dir=<path>`命令行，但每个会话的路径不同。 如果需要，可以创建一个实用工具，供用户运行，以启动Microsoft Edge并更改会话的路径。

如果上述两个选项都不适用于你的方案，则从 Microsoft Edge 版本 93 开始，Microsoft Edge上的 IE 模式将支持不合并。 对于最终用户，从 IE 模式应用程序启动新的浏览器窗口时，它将位于单独的会话中，如 IE11 中的无合并行为。

对于每个Microsoft Edge窗口，第一次访问该窗口中的 IE 模式选项卡（如果它是指定的“无合并”站点）时，该窗口会锁定在不同的“无合并”IE 会话中。  在锁定窗口中关闭最后一个 IE 模式选项卡之前，此窗口一直锁定在所有其他Microsoft Edge窗口中。 此前的行为是，用户可以在不合并的情况下启动 IE 并启动Microsoft Edge而无需使用其他机制进行合并。 在新窗口中打开的所有站点 (通过 window.open) 将尊重父进程的合并性质。

> [!NOTE]
> 不支持会话切换。 同一 IE 模式选项卡中的导航将使用同一会话。

可以按照以下步骤验证 Microsoft Edge 版本 93 或更高版本中的无合并行为：

1. 确保在版本 93 或更高版本Microsoft Edge启用 IE 模式。
2. 可以通过将合并类型属性的值设置为“no-merge”来配置需要阻止在Enterprise模式站点列表中共享会话的站点。 仅当打开的元素设置为Microsoft Edge时，此属性才适用。 默认情况下，所有站点都有合并类型的合并值。  (**注意：***在添加*或编辑网站时，edge://compat/sitelistmanager 提供的集成站点列表管理器工具包括 **“无合并**”复选框。) 

   ```
   <site url="contoso.com">
   <open-in merge-type="no-merge">IE11</open-in>
   </site>
   ```

3. 导航到配置为无合并的任何站点。 站点应位于其自己的未合并 IE 会话中。 打开另一Microsoft Edge实例或窗口并导航到同一站点时，它应位于其自己的 IE 会话中。 请注意，任务管理器中有多个iexplore.exe进程。

如果你有任何反馈，请通过我们的一个反馈渠道进行联系：Microsoft 支持或 [TechCommunity](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise) 论坛。

### <a name="can-i-save-links-as-webpages-in-internet-explorer-mode"></a>我能否将链接另存为 Internet Explorer 模式的网页？

可以，可以在 Microsoft Edge 中的 Internet Explorer 模式下在在上下文菜单中启用“目标另存为”选项。 为此，请在*计算机配置>管理模板> Windows Internet Explorer >组件*中配置组策略“*允许在 Internet Explorer 模式下另存目标*”。 保存机制的工作方式与在 Internet Explorer 中的工作方式相同，如果目标保存为 html 文件，则重新打开该文件将在Microsoft Edge中呈现页面。

能够将链接另存为网页需要以下最低操作系统更新：

- Windows 10 版本 2004、Windows Server 版本 2004、Windows 10 版本 20H2：[KB4580364](https://support.microsoft.com/help/4580364/windows-10-update-kb4580364)
- Windows 10 版本 1903、Windows 10 版本 1909、Windows Server 版本 1903：[KB4580386](https://support.microsoft.com/help/4580386/windows-10-update-kb4580386)
- Windows 10 版本 1809、Windows Server 版本 1809、Windows Server 2019：[KB4580390](https://support.microsoft.com/help/4580390/windows-10-update-kb4580390)
- Windows 10 版本 1803：[KB4586785](https://support.microsoft.com/help/4586785/windows-10-update-kb4586785)
- Windows 10 版本 1607：[KB4586830](https://support.microsoft.com/help/4586830/windows-10-update-kb4586830)
- Windows 10 版本 1507：[KB4586787](https://support.microsoft.com/help/4586787/windows-10-update-kb4586787)

### <a name="can-i-test-a-site-in-microsoft-edge-while-it-is-configured-to-open-ie-mode-in-the-enterprise-mode-site-list"></a>在将网站配置为在Enterprise模式站点列表中打开 IE 模式时，是否可以在Microsoft Edge中测试站点？

是的，在更新旧网站时，可以在Microsoft Edge上测试配置的应用程序的 IE 模式。 若要测试这些应用，可以配置 [InternetExplorerModeTabInEdgeModeAllowed](/deployedge/microsoft-edge-policies#internetexplorermodetabinedgemodeallowed) 策略。 如果启用此策略，则用户可以通过选择**设置和更多** (省略号图标...) > Edge 模式下**的更多 ToolsOpen** >  站点，在Microsoft Edge中打开 IE 模式**站点**。

### <a name="how-can-i-debug-my-legacy-application-while-using-ie-mode-on-microsoft-edge"></a>如何在Microsoft Edge上使用 IE 模式调试旧版应用程序？

可以使用 IEChooser 启动 Internet Explorer DevTools 来调试 IE 模式选项卡的内容。 若要使用 IEChooser，请执行以下步骤：

1. 打开 IEChooser。
   - 打开“运行”对话框。 例如，按 .`Windows logo key` + `R`
   - 输入 `%systemroot%\system32\f12\IEChooser.exe`，然后选择 **“确定**”。
2. 在 IEChooser 中，选择“IE 模式”选项卡的条目。

### <a name="my-application-requires-transferring-post-data-between-ie-mode-and-microsoft-edge-is-this-supported"></a>我的应用程序需要在 IE 模式和Microsoft Edge之间传输 POST 数据。 是否支持？

从 Microsoft Edge Beta 渠道 版本 96 开始，在 Internet Explorer 模式和Microsoft Edge之间切换的导航将包括表单数据和额外的 HTTP 标头。 但是，如果表单数据包含文件附件，则它们不会在引擎之间传输。 可以使用 [InternetExplorerIntegrationComplexNavDataTypes](/deployedge/microsoft-edge-policies#internetexplorerintegrationcomplexnavdatatypes) 组策略选择此类导航中应包含哪些数据类型。

除了Microsoft Edge版本 96，还需要安装以下Windows更新以实现此体验：

- Windows 11 [KB5007262](https://support.microsoft.com/topic/november-22-2021-kb5007262-os-build-22000-348-preview-7f3e18d7-4189-4882-b0e9-afc920253aee) 或更高版本
- Windows服务器 2022 [KB5007254](
https://support.microsoft.com/topic/november-22-2021-kb5007254-os-build-20348-380-preview-9a960291-d62e-486a-adcc-6babe5ae6fc1) 或更高版本
- Windows 10版本 2004;Windows服务器版本 2004;Windows 10版本;Windows服务器版本 20H2 和 Windows 10 版本 21H1 - [KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541) 或更高版本
- Windows 10版本 1909 [KB5007189](
https://support.microsoft.com/topic/november-9-2021-kb5007189-os-build-18362-1916-91b4647c-9979-4d84-8e64-efc8674e8c1f) 或更高版本

### <a name="where-can-i-find-the-reload-in-internet-explorer-mode-option"></a>在哪里可以找到“在 Internet Explorer 模式下重新加载”选项？

此功能在 Microsoft Edge 版本 92 或更高版本上提供。 若要启用此选项，请在Microsoft Edge中将“允许在 Internet Explorer 模式设置中重新加载站点”配置为“允许”。  有关详细信息，请参阅 [“启用本地站点列表”体验](/deployedge/edge-ie-mode-local-site-list#enable-the-local-site-list-experience)。

### <a name="where-is-the-file--new-session-option-in-microsoft-edge"></a>Microsoft Edge中的“文件>新会话”选项在哪里？

新式浏览器解决方案可在Microsoft Edge中使用多个配置文件。 使用此功能，可以使用另一个帐户创建新的会话。 以下资源提供有关多个配置文件的优势以及如何使用它们的信息。

- [视频：Microsoft Edge 和标识](/deployedge/microsoft-edge-video-identity)
- [现在，在工作和家中使用多个配置文件更容易Microsoft Edge](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/)

### <a name="why-am-i-getting-multiple-authentication-prompts-when-running-a-page-in-ie-mode-on-microsoft-edge"></a>为什么在 Microsoft Edge 上以 IE 模式运行页面时收到多个身份验证提示？

可以在 IE 模式下请求两次客户端证书。 第一次左右，证书选择对话框将以 IE 模式显示，第二次左右，对话将在Microsoft Edge中显示。 帧进程和窗口进程都需要请求身份验证。

创建 favicon 缓存后，除非删除缓存，否则不会再次要求提供客户端证书。 或者，可以在服务器配置（如 IIS）中设置规则，而无需为 favicon 提供客户端证书。

### <a name="why-are-there-rendering-issues-like-text-wrapping-and-content-truncation-when-child-windows-are-running-in-ie-mode-in-microsoft-edge"></a>当子窗口在 Microsoft Edge 的 IE 模式下运行时，为什么会出现文本包装和内容截断等呈现问题？

在 Microsoft Edge 中以 IE 模式呈现的子窗口的内容区域与 Internet Explorer 11 上的内容区域略有不同。 如果网页的设计具有基于像素的对齐方式或定位，则可能会遇到不正确的呈现、文本包装等情况。

将两个策略设置添加到 Microsoft Edge 版本 95，使你可以通过该方法指定对从 `window.open` IE 模式站点生成的弹出窗口的高度和宽度的自定义调整。 可以使用以下策略调整窗口大小：

- [InternetExplorerIntegrationWindowOpenHeightAdjustment](/deployedge/microsoft-edge-policies#internetexplorerintegrationwindowopenheightadjustment) - 此设置允许您指定自定义调整从 Internet Explorer 模式站点生成的弹出窗口的高度。
- [InternetExplorerIntegrationWindowOpenWidthAdjustment](/deployedge/microsoft-edge-policies#internetexplorerintegrationwindowopenwidthadjustment) - 此设置允许您指定对从 Internet Explorer 模式站点生成的弹出窗口宽度的自定义调整。

### <a name="why-arent-pop-ups-or-redirected-websites-loading-in-ie-mode-or-in-internet-explorer-11"></a>为什么弹出窗口或重定向网站未在 IE 模式或 Internet Explorer 11 中加载？

配置 IE 模式后，某些网站，尤其是那些创建新窗口或重定向网站的网站，可能不会在 IE 模式下呈现或在 Internet Explorer 11 中打开。

对于此类重定向网站，可以使用 `allow-redirect="true"` 网站列表配置中的内容。 有关详细信息，请参阅 [更新后的架构元素](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance#updated-schema-elements)。

### <a name="why-arent-websites-loading-in-ie-mode-when-i-launch-microsoft-edge-for-the-first-time"></a>为什么首次启动Microsoft Edge时网站未在 IE 模式下加载？

Microsoft Edge需要先下载 IE 模式网站列表，然后才能应用 IE 模式设置。 启动浏览器时，此过程可能无法完成。 有一个策略可用，可以在加载网站之前强制加载网站列表。 有关详细信息，请参阅 [DelayNavigationsForInitialSiteListDownload](/deployedge/microsoft-edge-policies#delaynavigationsforinitialsitelistdownload) 策略。

### <a name="why-cant-i-open-files-or-pages-that-are-found-by-using-file-urls-in-microsoft-edge"></a>为什么无法打开在Microsoft Edge中使用 file:// URL 找到的文件或页面？

由于Chromium安全限制，需要使用 IE 模式。 可以使用Microsoft Edge的 IE 模式功能加载托管在 intranet 区域内 **file://** 协议上的网页。 可以使用 [IntranetFileLinksEnabled](/deployedge/microsoft-edge-policies#intranetfilelinksenabled) 组策略来启用此功能。

## <a name="see-also"></a>另请参阅
  
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [关于 IE 模式](./edge-ie-mode.md)
- [其他企业模式信息](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
