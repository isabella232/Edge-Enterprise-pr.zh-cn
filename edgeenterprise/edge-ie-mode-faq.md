---
title: IE 模式疑难解答和常见问题解答
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 03/15/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Internet Explorer 模式的疑难解答和常见问题解答
ms.openlocfilehash: 77b31362bd7d28598ead7f0a3b33a69f2f4cb264
ms.sourcegitcommit: 93851b83dc11422924646a04a9e0f60ff2554af7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470200"
---
# <a name="ie-mode-troubleshooting-and-faq"></a>IE 模式疑难解答和常见问题解答

本文介绍了 Microsoft Edge 版本 77 或更高版本的故障排除提示和 FAQ。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。


## <a name="troubleshoot-ie-mode"></a>IE 模式疑难解答

使用此部分中的信息诊断和修复 IE 模式问题。

### <a name="internet-explorer-mode-diagnostic-information"></a>Internet Explorer 模式诊断信息

可以在 Microsoft Edge 的“兼容性”选项卡上获取 Internet Explorer 模式诊断信息。若要打开此选项卡，请转到 *edge://compat/iediagnostic*。 此页面可能会显示诊断消息。 此页面还显示以下类别的配置信息：

- **注册表项检查**。 （仅在检查失败时才显示。）检查是否在注册表中正确设置了 Internet Explorer 集成。 如果没有正确设置，用户可以单击“修复”**** 来解决问题。
- **Internet Explorer 模式**。 根据配置和操作系统来显示使用的 API 版本。 如果无法显示，系统可能会提示用户安装 **Windows 更新**。
- **Internet Explorer 模式设置**。 显示 Internet Explorer 模式是否已启用，以及是如何配置的。
- **命令行**。 显示用于启动 Microsoft Edge 的命令行字符串和开关。
- **组策略设置**。 显示 IE 模式是否是使用组策略配置的，以及应用的策略。

### <a name="error-message-to-open-this-page-in-internet-explorer-mode-reinstall-microsoft-edge-with-administrator-privileges"></a>错误消息：“要在 Internet Explorer 模式下打开此页面，请使用管理员权限重新安装 Microsoft Edge。”

如果没有安装所有必需 Windows 更新，可能会看到此错误。 有关必需 Windows 和 Microsoft Edge 版本，请参阅[关于 IE 模式](./edge-ie-mode.md)中列出的先决条件。

如果已安装所有必需 Windows 更新，但仍可能会在以下情况下看到此错误：

- 你使用的是 Canary 渠道（默认安装在用户级别）。
- 你使用的是稳定渠道、Beta 渠道或 Dev 渠道，但在安装期间看到提升权限提示时，提升权限被取消了。 如果你取消提升权限提示，安装将继续在用户级别进行。
- 已在 Windows 功能中禁用 Internet Explorer 11。

可能的解决方案：

- 在系统级别针对任意渠道运行安装程序：`installer.exe --system-level`。
- 在 Windows 功能中启用 Internet Explorer 11。

若要检查 Microsoft Edge 是否安装在系统级别，请在 Microsoft Edge 地址栏中键入“edge://version”。 “可执行文件路径”将会显示以“C:\Program Files”** 开头的路径，这就表示是系统安装。 如果“可执行文件路径”以“C:\Users\”**开头，请使用管理员特权卸载并重新安装 Microsoft Edge。

### <a name="error-message-to-open-this-page-in-ie-mode-try-restarting-microsoft-edge"></a>错误消息：“要在 IE 模式下打开此页面，请尝试重启 Microsoft Edge。”

如果 Internet Explorer 中出现意外错误，你可能就会看到此错误。 重启 Microsoft Edge 通常可以修复此错误。

### <a name="error-message-turn-off-remote-debugging-to-open-this-site-in-ie-mode-otherwise-it-might-not-work-as-expected"></a>错误消息：“关闭远程调试以在 IE 模式下打开此站点，否则可能无法正常工作。”

如果你正在进行远程调试，并导航到配置为在 IE 模式下运行的网页，可能就会看到此错误。 你可以继续操作，但网页会使用 Microsoft Edge 呈现。

### <a name="error-message-error-could-not-retrieve-emie-site-list"></a>错误消息：“错误：无法检索 EMIE 站点列表。”

您可能会在 *edge://compat/enterprise* 页面上看到此错误，表示站点列表下载失败。 从 Microsoft Edge 版本 87 开始，当使用 [BlockThirdPartyCookies](./microsoft-edge-policies.md#blockthirdpartycookies) 策略阻止第三方请求的Cookie 时，也不允许使用 HTTP 身份验证。 可以使用 [CookiesAllowedForURLs](./microsoft-edge-policies.md#cookiesallowedforurls) 策略为托管 Enterprise Mode Site List 的特定域允许 Cookie，以确保站点列表下载成功。

## <a name="frequently-asked-questions"></a>常见问题

### <a name="will-ie-mode-replace-internet-explorer-11"></a>IE 模式是否将替换 Internet Explorer 11？

我们致力于使 Internet Explorer 成为受支持、可靠和安全的浏览器。 Internet Explorer 仍然是 Windows 的组件，并遵循其安装所在操作系统的支持生命周期。 有关详细信息，请参阅[生命周期常见问题解答 - Internet Explorer](https://support.microsoft.com/help/17454/)。 尽管 Microsoft 会继续支持和更新 Internet Explorer，但最新功能和平台更新将仅在 Microsoft Edge 中提供。

### <a name="can-i-use-open-with-explorer-or-view-in-file-explorer-in-sharepoint-with-ie-mode"></a>是否可在 IE 模式下的 SharePoint 中使用“使用资源管理器打开”或“在文件资源管理器中查看”？

能，如果这适用于独立 Internet Explorer 11，则也适用于 IE 模式。 不过，若要管理 SharePoint 外部文件和文件夹，推荐方法是[同步 SharePoint 文件](https://support.office.com/en-us/article/sync-sharepoint-files-with-the-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)或[在 SharePoint 中移动或复制文件](https://support.office.com/en-us/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc)，而不是使用“使用资源管理器打开”选项。

### <a name="does-ie-mode-on-microsoft-edge-support-the-nomerge-option-that-was-supported-in-internet-explorer-11"></a>Microsoft Edge 上的 IE 模式是否支持 Internet Explorer 11中支持的 *nomerge* 选项？

在 Microsoft Edge 中没有明确的命令行来镜像 *nomerge* 选项，但是我们建议使用两种替代方法来提供此功能。

1. 在 Microsoft Edge 中使用配置文件-每个配置文件对用 IE 模式页面的不同 IE 会话，因此其行为与 *nomerge* 选项相同。
2. 使用`--user-data-dir=<path>`命令行，但每个会话的路径不同。 如果需要，可以创建一个既可以启动 Microsoft Edge，也可以更改会话的路径的实用程序供用户运行。

如果以上两个选项都不适用于你的情况，请通过其中一个反馈渠道联系我们：Microsoft 支持或 [TechCommunity 论坛](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise)。

### <a name="can-i-save-links-as-webpages-in-internet-explorer-mode"></a>我能否将链接另存为 Internet Explorer 模式的网页？

可以，可以在 Microsoft Edge 中的 Internet Explorer 模式下在在上下文菜单中启用“目标另存为”选项。 为此，请配置组策略 *"允许在 Internet Explorer 模式下将目标另存为"*，该策略位于 *“计算机配置>“管理模板”>“Windows 组件”>”Internet Explorer”*。
保存机制的工作方式与在 Internet Explorer 中相同，并且如果目标另存为 html 文件，重新打开文件将在 Microsoft Edge 中呈现页面。
 
请注意，此功能需要以下最低要求的操作系统更新：
- Windows 10 版本 2004、Windows Server 版本 2004、Windows 10 版本 20H2：[KB4580364](https://support.microsoft.com/help/4580364/windows-10-update-kb4580364)
- Windows 10 版本 1903、Windows 10 版本 1909、Windows Server 版本 1903：[KB4580386](https://support.microsoft.com/help/4580386/windows-10-update-kb4580386)
- Windows 10 版本 1809、Windows Server 版本 1809、Windows Server 2019：[KB4580390](https://support.microsoft.com/help/4580390/windows-10-update-kb4580390)
- Windows 10 版本 1803：[KB4586785](https://support.microsoft.com/help/4586785/windows-10-update-kb4586785)
- Windows 10 版本 1607：[KB4586830](https://support.microsoft.com/help/4586830/windows-10-update-kb4586830)
- Windows 10 版本 1507：[KB4586787](https://support.microsoft.com/help/4586787/windows-10-update-kb4586787)


## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [关于 IE 模式](./edge-ie-mode.md)
- [其他企业模式信息](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)