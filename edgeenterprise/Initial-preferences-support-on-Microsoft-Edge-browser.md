---
title: 了解如何配置项目上的初始Microsoft Edge。
ms.author: collw
author: AndreaLBarr
manager: srugh
ms.date: 07/27/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 了解如何配置项目上的初始Microsoft Edge。
ms.openlocfilehash: 06452996be4e2f1e2c40bfc5ba1753b9d2b7b222
ms.sourcegitcommit: 556aca8dde42dd66364427f095e8e473b86651a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2022
ms.locfileid: "12445648"
---
# <a name="configure-microsoft-edge-using-initial-preferences-settings-for-the-first-run"></a>使用首次运行的“初始首选项”设置配置Microsoft Edge

使用本文中的信息在Microsoft Edge设备上配置"初始首选项Windows设置。

> [!Note]
> 本文适用于 Microsoft Edge版本 93 或更高版本。

## <a name="configure-policy-settings-on-windows"></a>在 Windows 上配置策略设置

从 Microsoft Edge 93 开始，Microsoft 支持数量有限的初始首选项（以前称为"主首选项）"，以帮助管理员为首次运行配置浏览器。 有关详细信息，请参阅以下首选项 [设置表中的支持](#preference-settings) 设置。

部署后，初始首选项充当托管设备上的默认浏览器设置。 这些首选项是管理员首选的设置，用作首次运行的默认浏览器设置。

> [!NOTE]
> 初始首选项可能会由用户更改，并且不适用于某些设备，因为它们未加入 Active Directory® 域。

一些初始首选项设置示例包括默认主页的初始配置或具有特定 URL 的选项卡。

首选项仅从文件 *initial_preferences一次* ，在配置后对此文件所做的更改将不被删除。 如果设置由策略管理Microsoft Edge策略[，](/deployedge/microsoft-edge-policies)且在 initial_preferences *文件中*配置，则策略始终优先。

### <a name="preference-settings"></a>首选项设置

下表显示了当前受 Microsoft Edge 支持的设置。

| 首选项类别 | 设置 |
| - | - |
| Bookmark_bar | show_apps_shortcut<br>show_managed_bookmarks<br>show_on_all_tabs |
| 书签 | editing_enabled |
| 浏览器/clear_data | browsing_history<br>browsing_history_basic"<br>缓存<br>cache_basic<br>Cookie<br>download_history<br>form_data<br>passwords |
| 历史记录 | browsing_history<br>缓存<br>Cookie<br>download_history<br>form_data<br>hosted_apps_data<br>passwords<br>site_settings |
| 浏览器 | first_run_tabs<br>dark_theme<br>show_toolbar_bookmarks_button<br>show_toolbar_collections_butto<br>show_toolbar_downloads_button<br>show_home_button<br>show_prompt_before_closing_tabs<br>show_toolbar_history_button |
| default_search_provider | [default_search_provider] 已启用 |
| 全屏 | 允许 |
| 主页 | Homepage_url |
| homepage_is_newtabpage | homepage_is_newtabpage |
| 会话 | restore_on_startup<br>startup_urls |
| Extensions | 扩展：设置 |

## <a name="1-download-an-example-initial_preferences-file"></a>1：下载示例initial_preferences文件

To get started， download the "Policy" file from the [Microsoft Edge Enterprise landing page](/edge/business/download). 解压缩下载中的文件，然后打开示例*initial_preferences**文件。* 下一个屏幕截图显示了可供下载的策略文件选项

:::image type="content" source="media/initial-preferences-support-on-microsoft-edge-browser/edge-policy-files.png" alt-text="Microsoft Edge策略文件可供下载。":::

## <a name="2-customize-and-validate-the-initial_preferences-file"></a>2：自定义和验证initial_preferences文件

自定义已下载的 initial_preferences 中的首选项设置并** 验证更改以确保 JSON 代码中没有错误。 如果发现错误，请检查文件语法和 *initial_preferences，更正* 并再次检查。 用于验证 JSON、Online [JSON 工具](https://jsonformatter.org/)或 [JSON](https://code.visualstudio.com/docs/languages/json) 编辑功能的示例工具Visual Studio Code。

## <a name="3-deploy-preferences-to-users-computer"></a>3：将首选项部署到用户的计算机

部署 *initial_preferences* 文件的同时，将文件部署到用户Microsoft Edge，将该文件置于设备的以下位置。

### <a name="windows-amd64-and-arm64"></a>Windows (AMD64 和 ARM64) 

| 频道 | 位置 |
| - | - |
| Stable | `"C:\Program Files (x86)\Microsoft\Edge\Application"` |
| Beta | `"C:\Program Files (x86)\Microsoft\Edge Beta\Application"` |
|Canary | `"%LOCALAPPDATA%\Microsoft\Edge SxS\Application"` |
| Dev | `"C:\Program Files (x86)\Microsoft\Edge Dev\Application"` |

> [!NOTE]
> 需要*initial_preferences*文件部署到与用户计算机上msedge.exe文件相同的Windows文件夹。* *  

### <a name="macos"></a>macOS

| 频道 | 位置 |
| - | - |
| Stable | `"~/Library/Application Support/Microsoft Edge/Microsoft Edge Initial Preferences"` |
| beta 版 | `“~/Library/Application Support/Microsoft Edge Beta/Microsoft Edge Initial Preferences"` |
| Canary | `“~/Library/Application Support/Microsoft Edge Canary/Microsoft Edge Initial Preferences"` |
| Dev | `"~/Library/Application Support/Microsoft Edge Dev/Microsoft Edge Initial Preferences"` |

## <a name="important-notes-msi--pkg-deployment-and-initial_preferences-interaction"></a>重要说明：MSI/Pkg 部署 *initial_preferences* 交互

初始首选项仅在最终用户首次运行浏览器 *initial_preferences* 部署浏览器文件后生效。  

## <a name="see-also"></a>另请参阅

- [示例 *initial_prefrences* 文件](/edge/business/download)
