---
title: IE 模式疑难解答和常见问题解答
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 11/03/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge Internet Explorer 模式的疑难解答和常见问题解答
ms.openlocfilehash: 651fc438e64c21e33787724fb3d5931f0f5b75fa
ms.sourcegitcommit: 4ec03873a85f065d9bfa6203cfe6c3e938f79bc5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "12155140"
---
# <a name="internet-explorer-ie-mode-troubleshooting-and-faq"></a>Internet Explorer (IE) 模式疑难解答和常见问题解答

> [!NOTE]
> the Internet Explorer 11 desktop application will be retired and out of support on June 15， 2022. To see the list of what's in scope， see the [Internet Explorer desktop app retirement FAQ](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549). 现在使用的 IE11 应用和网站可以在 Microsoft Edge 的 Internet Explorer 模式下打开。 若要了解更多信息，请参阅 Internet Explorer [on Windows 10 中Microsoft Edge](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)文章。

本文介绍了 Microsoft Edge 版本 77 或更高版本的故障排除提示和 FAQ。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="troubleshoot-ie-mode"></a>IE 模式疑难解答

使用此部分中的信息诊断和修复 IE 模式问题。

### <a name="internet-explorer-mode--general-diagnostic-information"></a>Internet Explorer模式常规诊断信息

可以在 Microsoft Edge 的“兼容性”选项卡上获取 Internet Explorer 模式诊断信息。若要打开此选项卡，请转到 *edge://compat/iediagnostic*。 此页面可能会显示诊断消息。 此页面还显示以下类别的配置信息：

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

若要检查 Microsoft Edge 是否安装在系统级别，请在 Microsoft Edge 地址栏中键入“edge://version”。 “可执行文件路径”将会显示以“C:\Program Files”** 开头的路径，这就表示是系统安装。 如果可执行文件路径以*C：\Users*开头，请卸载并重新安装Microsoft Edge管理员权限。

### <a name="error-message-to-open-this-page-in-ie-mode-try-restarting-microsoft-edge"></a>错误消息"若要在 IE 模式下打开此页面，请尝试重新启动Microsoft Edge"。

如果发生意外错误，则可能会看到此错误Internet Explorer。 重启 Microsoft Edge 通常可以修复此错误。

### <a name="error-message-turn-off-remote-debugging-to-open-this-site-in-ie-mode-otherwise-it-might-not-work-as-expected"></a>错误消息：“关闭远程调试以在 IE 模式下打开此站点，否则可能无法正常工作。”

如果远程调试并导航到配置为在 IE 模式下运行的网页，则可能会看到此错误。 你可以继续操作，但网页会使用 Microsoft Edge 呈现。

### <a name="error-message-could-not-retrieve-emie-site-list"></a>错误消息："无法检索 EMIE 站点列表。"

您可能会在"网站列表 edge://compat/enterprise** 看到此错误，指示网站列表下载失败。 从 Microsoft Edge 版本 87 开始，当使用 [BlockThirdPartyCookies](/deployedge/microsoft-edge-policies#blockthirdpartycookies) 策略阻止第三方请求的Cookie 时，也不允许使用 HTTP 身份验证。 可以使用 [CookiesAllowedForURLs](/deployedge/microsoft-edge-policies#cookiesallowedforurls) 策略为托管 Enterprise Mode Site List 的特定域允许 Cookie，以确保站点列表下载成功。

## <a name="frequently-asked-questions"></a>常见问题

### <a name="will-ie-mode-replace-internet-explorer-11"></a>IE 模式是否将替换 Internet Explorer 11？

是的，Internet Explorer 11 桌面应用程序将于 2022 年 6 月 15 日停用并退出支持。 若要了解范围内内容，请参阅生命周期[常见问题解答 - Internet Explorer。](/lifecycle/faq/internet-explorer-microsoft-edge) 现在使用的 IE11 应用和网站可以在 Microsoft Edge 的 Internet Explorer 模式下打开。 若要了解更多信息，请参阅 Internet Explorer [on Windows 10 中Microsoft Edge。](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)

### <a name="how-can-i-debug-my-legacy-application-while-using-ie-mode-on-microsoft-edge"></a>如何在 IE 模式下对旧版应用程序进行调试Microsoft Edge？

可以使用 IEChooser 启动 Internet Explorer Tools 以调试 IE 模式选项卡的内容。 若要使用 IEChooser，请按照以下步骤操作：

1. 打开 IEChooser。
   - 打开“运行”对话框。 例如，按 `Windows logo key`  +  `R` 。
   - 输入 `%systemroot%\system32\f12\IEChooser.exe` ，然后选择"确定 **"。**
2. 在 IEChooser 中，选择"IE 模式"选项卡的条目。

### <a name="can-i-test-a-site-in-microsoft-edge-while-it-is-configured-to-open-ie-mode-in-the-enterprise-mode-site-list"></a>当站点配置为在Microsoft Edge站点列表中打开 IE 模式时，我能否Enterprise测试该站点？

是的，在现代化旧网站时，可以在新网站上测试 IE 模式配置Microsoft Edge。 为此，可以使用命令行Microsoft Edge `--ie-mode-test` 运行命令。 确保没有运行任何其他Microsoft Edge实例。 然后，你可以选择**设置**省略号 (...)>在边缘>打开站点**更多工具"。**

### <a name="can-i-use-view-in-file-explorer-in-sharepoint-online-on-microsoft-edge"></a>能否在 SharePoint Online 上使用"在文件资源管理器Microsoft Edge？

从 Microsoft Edge版本 95 开始，你可以为 SharePoint **** Online 新式文档库启用"在文件资源管理器中查看"功能。 若要使此体验可见且适用于你的用户，你需要启用 Microsoft Edge"在 Microsoft Edge 中为 SharePoint 页面配置文件资源管理器中的查看功能["](/deployedge/microsoft-edge-policies#configureviewinfileexplorer)策略，并更新 SharePoint Online 租户配置。 了解更多信息：SharePoint文件资源管理器查看Microsoft Edge [- SharePoint Microsoft 365 |Microsoft Docs](/SharePoint/sharepoint-view-in-edge)。

但是，与使用"在文件资源管理器中查看"选项不同，管理 SharePoint 外部的文件和文件夹的建议方法是将 SharePoint 和[Teams](https://support.microsoft.com/office/sync-sharepoint-and-teams-files-with-your-computer-6de9ede8-5b6e-4503-80b2-6190f3354a88?ui=en-us&rs=en-us&ad=us)文件与计算机同步，或在 SharePoint 中移动或[复制](https://support.microsoft.com/office/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc?ui=en-us&rs=en-us&ad=us)文件。

### <a name="does-ie-mode-on-microsoft-edge-support-the-no-merge-option-that-was-supported-in-internet-explorer-11"></a>IE 模式是否Microsoft Edge 11 中支持的"不合并"Internet Explorer？

建议对网站中的非合并功能Microsoft Edge操作之一：

1. 在"Microsoft Edge配置文件 - 每个配置文件映射到 IE 模式页面的不同 IE 会话，因此其行为与不合并选项相同。
2. 使用`--user-data-dir=<path>`命令行，但每个会话的路径不同。 如果需要，可以创建一个既可以启动 Microsoft Edge，也可以更改会话的路径的实用程序供用户运行。

如果上述选项均不适用于你的方案，从 Microsoft Edge版本 93 开始，Microsoft Edge IE 模式将支持不合并。 对于最终用户，当从 IE 模式应用程序启动新的浏览器窗口时，它将位于单独的会话中，如 IE11 中的无合并行为。

对于每个 Microsoft Edge 窗口，首次访问该窗口中的 IE 模式选项卡时，如果它是指定的"不合并"站点，该窗口将被锁定到其他"不合并"IE 会话中。  在锁定窗口中关闭最后一个 IE 模式选项卡Microsoft Edge窗口保持锁定状态。 遵循以前的行为，其中用户可以在不采用其他机制Microsoft Edge不合并的情况下启动 IE 并启动 IE。 新窗口中打开的所有网站 (window.open) 将尊重父进程的合并特性。

> [!NOTE]
> 不支持会话切换。 同一 IE 模式选项卡中的导航将使用相同的会话。

可以按照以下步骤验证 Microsoft Edge 93 或更高版本中的不合并行为：

1. 确保 IE 模式在 Microsoft Edge版本 93 或更高版本上启用。
2. 可以通过将 merge-type 属性的值设置为"no-merge"来配置需要在 Enterprise 模式站点列表中阻止会话共享的站点。 此属性仅在 open-in 元素设置为 Microsoft Edge。 默认情况下，所有网站都有 merge 类型的 merge 值。  (**注意：** 添加或编辑网站时，edge://compat/sitelistmanager 集成的网站列表** 管理器工具包含"不合并****"复选框) 

   ```
   <site url="contoso.com">
   <open-in merge-type="no-merge">IE11</open-in>
   </site>
   ```

3. 导航到配置为不合并的任何网站。 网站应在其自己未合并的 IE 会话中。 打开另一Microsoft Edge实例或窗口并导航到同一站点时，它应在其自己的 IE 会话中。 请注意，任务管理器iexplore.exe多个任务进程。

如果你有任何反馈，请通过我们的一个反馈渠道联系：Microsoft 支持或 [TechCommunity](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise) 论坛。

### <a name="can-i-save-links-as-webpages-in-internet-explorer-mode"></a>我能否将链接另存为 Internet Explorer 模式的网页？

可以，可以在 Microsoft Edge 中的 Internet Explorer 模式下在在上下文菜单中启用“目标另存为”选项。 为此，请配置组策略"允许在** Internet Explorer 模式下将目标另存为"，该策略位于 Computer *Configuration > Administrative Templates > Windows Components > Internet Explorer*。 保存机制的工作方式与在 Internet Explorer 中相同，并且如果目标另存为 html 文件，重新打开文件将在 Microsoft Edge 中呈现页面。

若要将链接另存为网页，需要以下最低操作系统更新：

- Windows 10 版本 2004、Windows Server 版本 2004、Windows 10 版本 20H2：[KB4580364](https://support.microsoft.com/help/4580364/windows-10-update-kb4580364)
- Windows 10 版本 1903、Windows 10 版本 1909、Windows Server 版本 1903：[KB4580386](https://support.microsoft.com/help/4580386/windows-10-update-kb4580386)
- Windows 10 版本 1809、Windows Server 版本 1809、Windows Server 2019：[KB4580390](https://support.microsoft.com/help/4580390/windows-10-update-kb4580390)
- Windows 10 版本 1803：[KB4586785](https://support.microsoft.com/help/4586785/windows-10-update-kb4586785)
- Windows 10 版本 1607：[KB4586830](https://support.microsoft.com/help/4586830/windows-10-update-kb4586830)
- Windows 10 版本 1507：[KB4586787](https://support.microsoft.com/help/4586787/windows-10-update-kb4586787)

### <a name="can-i-test-a-site-in-microsoft-edge-while-it-is-configured-to-open-ie-mode-in-the-enterprise-mode-site-list"></a>当站点配置为在Microsoft Edge站点列表中打开 IE 模式时，我能否Enterprise测试该站点？

是的，在现代化旧站点时，可以在新网站上测试 IE Microsoft Edge。 为此，可以使用命令行Microsoft Edge `--ie-mode-test` 运行命令。 确保没有运行任何其他Microsoft Edge实例。 然后选择 **"设置"， (** 省略号图标"...") ..."**>"在>模式中打开站点"的更多工具**。

### <a name="my-application-requires-transferring-post-data-between-ie-mode-and-microsoft-edge-is-this-supported"></a>我的应用程序需要在 IE 模式和 IE 模式之间传输 POST Microsoft Edge。 是否支持？

从 Microsoft Edge Beta 渠道版本 96 开始，在 Internet Explorer 模式Microsoft Edge导航将包括表单数据和其他 HTTP 标头。 但是，如果表单数据包含文件附件，则这些附件不会在引擎之间传输。 可以使用 [InternetExplorerIntegrationComplexNavDataTypes](/deployedge/microsoft-edge-policies#internetexplorerintegrationcomplexnavdatatypes) 组策略选择此类导航中应包含哪些数据类型。

除了 Microsoft Edge版本 96 之外，还需要安装以下Windows更新以用于此体验：

- Windows 10 2004 版;Windows服务器版本 2004;Windows 10版本;Windows服务器版本 20H2 和 Windows 10 21H1 - KB5006738 或更高版本

  > [!NOTE]
  > 即将Windows 10 19H2、Windows Server 2022 Windows 11更新。

## <a name="see-also"></a>另请参阅
  
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [关于 IE 模式](./edge-ie-mode.md)
- [其他企业模式信息](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
