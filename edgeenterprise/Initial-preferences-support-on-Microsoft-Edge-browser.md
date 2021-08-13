---
title: 浏览器上的初始首选项Microsoft Edge支持
ms.author: collw
author: AndreaLBarr
manager: srugh
ms.date: 07/27/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 浏览器上的初始首选项Microsoft Edge支持。
ms.openlocfilehash: 39af88d21107ad548166c749c3ba765754270b48
ms.sourcegitcommit: 715cb8c8101a6daed48563f33d2bc40ee7109e0e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "11882258"
---
# <a name="configure-microsoft-edge-using-initial-preferences-settings-for-the-first-run"></a>使用首次运行的“初始首选项”设置配置Microsoft Edge

使用以下信息在 Microsoft Edge设备上配置"初始首选项Windows设置。

> [!Note]
> 本文适用于 Microsoft Edge版本 93 或更高版本。

## <a name="configure-policy-settings-on-windows"></a>在 Windows 上配置策略设置

从 93 Microsoft Edge，Microsoft 支持数量有限的初始首选项（以前称为"主首选项）"，以帮助管理员为首次运行配置浏览器;请参阅下面的受支持设置列表。  

部署后，初始首选项充当托管设备上的默认浏览器设置;这些是管理员首选的设置，用作默认设置，但用户可以更改这些设置，也可以不用于某些设备，因为它们未加入 Active Directory® 域。

初始首选项设置的一些示例包括默认主页的初始配置或具有特定 URL 的选项卡。

首选项仅从文件initial_preferences一次，在配置后对此文件进行的任何更改都将不会得到遵守。 如果设置由策略Microsoft Edge[策略管理](/deployedge/microsoft-edge-policies)，initial_preferences文件中进行配置，则策略始终优先。

下面是当前受用户支持的首选项设置Microsoft Edge：

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
| Extensions | Extensions ： settings |

## <a name="1-download-an-example-initial_preferences-file"></a>1：下载示例initial_preferences文件

To get started， download the example *initial_preferences* file form this location the [Microsoft Edge Enterprise landing page](https://www.microsoft.com/edge/business/download) **and** follow the steps below.

## <a name="2-customize-and-validate-the-initial_preferences-file"></a>2：自定义和验证initial_preferences文件

自定义已下载的 initial_preferences 中的首选项** 设置并验证更改以确保 JSON 代码中没有任何错误。 如果发现错误，请检查文件语法和 *initial_preferences，更正* 并再次验证。 用于验证 JSON、Online [JSON 工具](https://jsonformatter.org/)或[JSON](https://code.visualstudio.com/docs/languages/json)编辑的示例工具Visual Studio Code。

## <a name="3-deploy-preferences-to-users-computer"></a>3：将首选项部署到用户的计算机

在*initial_preferences*浏览器的同时将文件部署到用户Microsoft Edge，将该文件放在设备的以下位置。

### <a name="windows-amd64-and-arm64"></a>Windows (AMD64 和 ARM64) 

| 频道 | 位置 |
| - | - |
| Stable | `"C:\Program Files (x86)\Microsoft\Edge\Application"` |
| Beta | `"C:\Program Files (x86)\Microsoft\Edge Beta\Application"` |
|Canary | `"%LOCALAPPDATA%\Microsoft\Edge SxS\Application"` |
| Dev | `"C:\Program Files (x86)\Microsoft\Edge Dev\Application"` |

**注意***：initial_preferences*文件需要部署到用户计算机上与 msedge.exe 文件相同的Windows文件夹。  

### <a name="macos"></a>macOS

| 频道 | 位置 |
| - | - |
| Stable | `"~/Library/Application Support/Microsoft Edge/Microsoft Edge Initial Preferences"` |
| Beta | `“~/Library/Application Support/Microsoft Edge Beta/Microsoft Edge Initial Preferences"` |
| Canary | `“~/Library/Application Support/Microsoft Edge Canary/Microsoft Edge Initial Preferences"` |
| Dev | `"~/Library/Application Support/Microsoft Edge Dev/Microsoft Edge Initial Preferences"` |

## <a name="important-notes-msi--pkg-deployment-and-initial_preferences-interaction"></a>重要说明：MSI/Pkg 部署 *initial_preferences* 交互

初始首选项仅在最终用户首次运行浏览器initial_preferences部署文件时生效。  

## <a name="see-also"></a>另请参阅

- [示例 *initial_prefrences* 文件](https://www.microsoft.com/edge/business/download)
