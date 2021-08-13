---
title: 什么是 Internet Explorer 模式？
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 08/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解 Microsoft Edge 中的 Internet Explorer 模式如何提供对需要 Internet Explorer 11 的网站的访问和新式网站的访问权限。
ms.openlocfilehash: cf2271f8b95c97a63695abf471ae67e693798ff2
ms.sourcegitcommit: 715cb8c8101a6daed48563f33d2bc40ee7109e0e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "11882278"
---
# <a name="what-is-internet-explorer-ie-mode"></a>什么是 Internet Explorer (IE) 模式？

>[!Note]
> Internet Explorer 11 桌面应用程序将于 2022 年 6 月 15 日停用并停止支持（若要查看包含内容的列表， [请参阅常见问题解答](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)）。 现在使用的 IE11 应用和网站可以在 Microsoft Edge 的 Internet Explorer 模式下打开。 [在此处了解详细信息](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。

我们在 Microsoft Edge 中创建了 Internet Explorer （IE） 模式，适用于仍需要 Internet Explorer 11 后向兼容现有网站但也需要现代浏览器的组织。 通过此功能，组织可以更加轻松地使用一个浏览器，用于旧版 Web/应用或新式 Web/应用。 本文简要介绍了将 Microsoft Edge 与 IE 模式一同使用。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="what-is-ie-mode"></a>什么是 IE 模式？

在 Microsoft Edge 中使用 IE 模式，可以在一个浏览器中轻松使用组织需要的所有网站。 此模式对新式网站使用集成 Chromium 引擎，并对旧网站使用 Internet Explorer 11 (IE11) 中的 Trident MSHTML 引擎。

当站点在 IE 模式下加载时，IE 徽标指示器将显示在导航栏的左侧。 单击 IE 徽标指示器可以显示更多信息，如下所示：

  ![IE 徽标指示器](./media/ie-mode/ie-logo-indicator1.png)

只有（通过策略）专门配置的网站会使用 IE 模式，其他所有网站都会呈现为新式网站。 若要让网站使用 IE 模式，需要执行以下操作：

- 在下面一个策略中定义的 Enterprise Mode Site List XML 中列出网站：
  - Microsoft Edge 78 或更高版本，“配置企业模式站点列表”
  - Internet Explorer，“使用企业模式 IE 网站列表”
  > [!NOTE]
  > 我们只处理一个 Enterprise Mode Site List。 Microsoft Edge 网站列表策略优先于 Internet Explorer 网站列表策略。
- 所有 Intranet 网站都已启用“将所有 Intranet 网站发送到 Internet Explorer”**** 组策略（Microsoft Edge 77 或更高版本）。

### <a name="ie-mode-supports-the-following-internet-explorer-functionality"></a>IE 模式支持以下 Internet Explorer 功能

- 所有文档模式和企业模式。
- ActiveX 控件（例如 Java 或 Silverlight）。 **注意**：Silverlight [将于](https://support.microsoft.com/windows/silverlight-end-of-support-0a3be3c7-bead-e203-2dfd-74f0a64f1788) 2021 年 10 月 12 日终止支持。 
- 浏览器帮助程序对象 
- Internet Explorer影响安全区域设置和受保护模式的组设置和组策略
- 适用于 IE 的 F12 开发人员工具，随 [IEChooser](/deployedge/edge-ie-mode-faq#how-can-i-debug-my-legacy-application-while-using-ie-mode-on-microsoft-edge-) 一起启动
- Microsoft Edge 扩展（不支持直接与 IE 页面内容交互的扩展。）

### <a name="ie-mode-doesnt-support-the-following-internet-explorer-functionality"></a>IE 模式不支持以下 Internet Explorer 功能

- Internet Explorer 工具栏
- 控制导航菜单的 Internet Explorer 的设置和组策略。
- IE11 或 Microsoft Edge F12 开发人员工具

## <a name="prerequisites"></a>必备条件

若要将 Microsoft Edge 与 IE 模式配合使用，应满足以下先决条件。

> [!IMPORTANT]
> 为了确保成功，请安装 Windows 和 Microsoft Edge 的最新更新。 否则可能会导致 IE 模式失败。

1. 下表中列出了操作系统的最低系统更新。

 | 操作系统 | 版本       | 更新 |
 |------------------|---------------|---------|
 | Windows 10       | 1909 或更高版本 |         |
 | Windows 10       | 1903          | [KB4501375](https://support.microsoft.com/help/4501375/windows-10-update-kb4501375) 或更高版本 |
 | Windows Server   | 1903          | [KB4501375](https://support.microsoft.com/help/4501375/windows-10-update-kb4501375) 或更高版本 |
 | Windows 10       | 1809          | [KB4501371](https://support.microsoft.com/help/4501371/windows-10-update-kb4501371) 或更高版本 |
 | Windows Server   | 1809          | [KB4501371](https://support.microsoft.com/help/4501371/windows-10-update-kb4501371) 或更高版本 |
 | Windows Server   | 2019          | [KB4501371](https://support.microsoft.com/help/4501371/windows-10-update-kb4501371) 或更高版本 |
 | Windows 10       | 1803          | [KB4512509](https://support.microsoft.com/help/4512509/windows-10-update-kb4512509) 或更高版本 |
 | Windows 10       | 1709          | [KB4512494](https://support.microsoft.com/help/4512494/windows-10-update-kb4512494) 或更高版本 |
 | Windows 10       | 1607          | [KB4516061](https://support.microsoft.com/help/4516061/windows-10-update-kb4516061) 或更高版本 |
 | Windows Server   | 2016          | [KB4516061](https://support.microsoft.com/help/4516061/windows-10-update-kb4516061) 或更高版本 |
 | Windows 10       | 初始版本，2015 年 7 月 | [KB4520011](https://support.microsoft.com/help/4520011/windows-10-update-kb4520011) 或更高版本 |
 | Windows 8       | 8.1              | [KB4507463](https://support.microsoft.com/help/4507463/july-16-2019-kb4507463-os-build-preview-of-monthly-rollup) 或更高版本；或者 [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) 或更高版本 |
 | Windows Server   | 2012 R2       | [KB4507463](https://support.microsoft.com/help/4507463/july-16-2019-kb4507463-os-build-preview-of-monthly-rollup) 或更高版本；或者 [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) 或更高版本 |
 | Windows 8  | 嵌入            | 安装 [KB4492872](https://support.microsoft.com/help/4492872/update-for-internet-explorer-april-16-2019) 以升级到 Internet Explorer 11；然后安装 [KB4507447](https://support.microsoft.com/help/4507447/windows-server-2012-update-kb4507447) 或更高版本或者 [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) 或更高版本 |
 | Windows Server   | 2012           | 安装 [KB4492872](https://support.microsoft.com/help/4492872/update-for-internet-explorer-april-16-2019) 以升级到 Internet Explorer 11；然后安装 [KB4507447](https://support.microsoft.com/help/4507447/windows-server-2012-update-kb4507447) 或更高版本或者 [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) 或更高版本 |
 | Windows 7        |  SP1**        | [KB4507437](https://support.microsoft.com/help/4507437/windows-7-update-kb4507437) 或更高版本；或者 [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) 或更高版本 |
 | Windows Server   |  2008 R2**    | [KB4507437](https://support.microsoft.com/help/4507437/windows-7-update-kb4507437) 或更高版本；或者 [KB4511872](https://support.microsoft.com/help/4511872/cumulative-security-update-for-internet-explorer) 或更高版本 |
  > [!IMPORTANT]
  > ** 即使不再为 Windows 7 和 Windows Server 2008 R2 提供支持服务，Microsoft Edge 也将支持这些操作系统。 要在这些操作系统中支持 IE 模式，设备需要具有[适用于 Windows 7 的扩展安全更新](https://support.microsoft.com/help/4527878/faq-about-extended-security-updates-for-windows-7)。 建议尽快升级到支持的操作系统以保证安全。 对于具有扩展安全更新的 Microsoft Edge 的支持应当视为达到受支持的操作系统状态的一种临时过渡。

2. Microsoft Edge 管理模板。 有关详细信息，请参阅[配置 Microsoft Edge](./configure-microsoft-edge.md)。
3. 在 Windows 功能中启用了 Internet Explorer 11。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [其他企业模式信息](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
