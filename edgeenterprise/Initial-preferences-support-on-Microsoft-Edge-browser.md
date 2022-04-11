---
title: 了解如何在Microsoft Edge上配置初始首选项。
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 03/23/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 了解如何在Microsoft Edge上配置初始首选项。
ms.openlocfilehash: 751097853e02589fe1b900f6af0d290feb5fbe67
ms.sourcegitcommit: dd8cdbd35726c795ddce917e549ddf17ee7f5290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "12473407"
---
# <a name="configure-microsoft-edge-using-initial-preferences-settings-for-the-first-run"></a>使用首次运行的“初始首选项”设置配置Microsoft Edge

使用本文中的信息在Windows设备上配置Microsoft Edge初始首选项设置。

> [!Note]
> 本文适用于 Microsoft Edge 版本 93 或更高版本。

## <a name="configure-policy-settings-on-windows"></a>在 Windows 上配置策略设置

从Microsoft Edge版本 93 开始，Microsoft 支持数量有限的初始首选项（以前称为“主首选项”），以帮助管理员配置首次运行的浏览器。 有关详细信息，请参阅以下 [首选项设置](#preference-settings) 表中支持的设置。

部署时，初始首选项充当托管设备上的默认浏览器设置。 这些首选项是管理员首选的设置，可用作首次运行的默认浏览器设置。

> [!NOTE]
> 初始首选项可由用户更改，并且不适用于某些设备，因为它们未加入 Active Directory® 域。

初始首选项设置的一些示例包括初始配置具有特定 URL 的默认主页或选项卡。

首选项仅从 *initial_preferences* 文件复制一次，配置后对此文件所做的更改将不受到尊重。 如果设置由[Microsoft Edge](/deployedge/microsoft-edge-policies)策略管理并在*initial_preferences文件*中配置，则策略始终优先。

### <a name="preference-settings"></a>首选项设置

下表显示了Microsoft Edge当前支持的设置。

| 首选项类别 | 设置 |
| - | - |
| Bookmark_bar | show_apps_shortcut<br>show_managed_bookmarks<br>show_on_all_tabs |
| 书签 | editing_enabled |
| 浏览器/clear_data | browsing_history<br>browsing_history_basic”<br>缓存<br>cache_basic<br>Cookie<br>download_history<br>form_data<br>密码 |
| 历史记录 | browsing_history<br>缓存<br>Cookie<br>download_history<br>form_data<br>hosted_apps_data<br>密码<br>site_settings |
| 浏览器 | first_run_tabs<br>dark_theme<br>show_toolbar_bookmarks_button<br>show_toolbar_collections_butto<br>show_toolbar_downloads_button<br>show_home_button<br>show_prompt_before_closing_tabs<br>show_toolbar_history_button |
| default_search_provider | [default_search_provider] 已启用 |
| 全屏 | 允许 |
| 主页 | Homepage_url |
| homepage_is_newtabpage | homepage_is_newtabpage |
| 会话 | restore_on_startup<br>startup_urls |
| Extensions | 扩展：设置 |

## <a name="1-download-an-example-initial_preferences-file"></a>1：下载示例initial_preferences文件

若要开始，请从[Microsoft Edge Enterprise登陆页](https://www.microsoft.com/edge/business/download)下载“Policy”文件。 提取下载中的文件，然后在*示例*文件夹中打开*initial_preferences*文件。 下一个屏幕截图显示了可供下载的策略文件选项

:::image type="content" source="media/initial-preferences-support-on-microsoft-edge-browser/edge-policy-files.png" alt-text="Microsoft Edge可下载的策略文件。":::

## <a name="2-customize-and-validate-the-initial_preferences-file"></a>2：自定义和验证initial_preferences文件

自定义下载的 *initial_preferences* 文件中的首选项设置，并验证更改以确保 JSON 代码中没有错误。 如果发现错误，请检查 *initial_preferences* 文件的语法和结构，进行更正，然后再次检查。 在Visual Studio Code中验证 JSON、联机 [JSON 工具](https://jsonformatter.org/)或 [JSON 编辑的](https://code.visualstudio.com/docs/languages/json)示例工具很少。

## <a name="3-deploy-preferences-to-users-computer"></a>3：将首选项部署到用户的计算机

在部署*Microsoft Edge*的同时将initial_preferences文件部署到用户的设备，并将文件置于设备上的以下位置。

### <a name="windows-amd64-and-arm64"></a>Windows (AMD64 和 ARM64) 

| 频道 | 位置 |
| - | - |
| Stable | `"C:\Program Files (x86)\Microsoft\Edge\Application"` |
| Beta | `"C:\Program Files (x86)\Microsoft\Edge Beta\Application"` |
|Canary | `"%LOCALAPPDATA%\Microsoft\Edge SxS\Application"` |
| Dev | `"C:\Program Files (x86)\Microsoft\Edge Dev\Application"` |

> [!NOTE]
> initial_preferences文件需要部署到用户*Windows*计算机上*msedge.exe*文件所在的同一文件夹。  

### <a name="macos"></a>macOS

| 频道 | 位置 |
| - | - |
| Stable | `"~/Library/Application Support/Microsoft Edge/Microsoft Edge Initial Preferences"` |
| Beta | `“~/Library/Application Support/Microsoft Edge Beta/Microsoft Edge Initial Preferences"` |
| Canary | `“~/Library/Application Support/Microsoft Edge Canary/Microsoft Edge Initial Preferences"` |
| Dev | `"~/Library/Application Support/Microsoft Edge Dev/Microsoft Edge Initial Preferences"` |

## <a name="important-notes-msi--pkg-deployment-and-initial_preferences-interaction"></a>重要说明：MSI/Pkg 部署和*initial_preferences交互*

初始首选项仅在最终用户在浏览器首次运行之前部署 *initial_preferences* 文件后生效。  

## <a name="see-also"></a>另请参阅

- [*initial_prefrences*示例模板文件](/edge/business/download)
