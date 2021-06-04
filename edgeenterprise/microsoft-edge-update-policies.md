---
title: Microsoft Edge 更新策略文档
ms.author: stmoody
author: dan-wesley
manager: tahills
ms.date: 11/12/2020
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Microsoft Edge 更新程序支持的所有策略的文档
ms.openlocfilehash: 0cdcda984efff8d10a84431e44c49ffbf28ddf07
ms.sourcegitcommit: c2ac4f889b625210b9365a60a447482fb5b4c9d4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2020
ms.locfileid: "11167304"
---
# <a name="microsoft-edge---update-policies"></a>Microsoft Edge - 更新策略

最新版本的 Microsoft Edge 包含以下策略，你可以使用这些策略控制更新 Microsoft Edge 的方式和时间。

有关 Microsoft Edge 中可用的其他策略的信息，请查看 [Microsoft Edge 浏览器策略引用](microsoft-edge-policies.md)
> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。
##  <a name="available-policies"></a>可用策略
这些表列出了本版本 Microsoft Edge 中提供的所有与更新相关的组策略。 使用表中的链接获取有关特定策略的更多详细信息。

|||
|-|-|
|[应用程序](#applications)|[首选项](#preferences)|
|[代理服务器](#proxy-server)|[Microsoft Edge Web 视图](#microsoft-edge-webview)|

### [应用程序](#applications-policies)
|策略名称|标题|
|-|-|
|[InstallDefault](#installdefault)|允许安装默认项|
|[UpdateDefault](#updatedefault)|更新策略替代默认值|
|[安装](#install)|允许安装（按渠道）|
|[更新](#update)|更新策略替代（按渠道）|
|[Allowsxs](#allowsxs)|允许 Microsoft Edge 并行浏览器体验|
|[CreateDesktopShortcutDefault](#createdesktopshortcutdefault)|安装默认项时阻止创建快捷方式|
|[CreateDesktopShortcut](#createdesktopshortcut)|安装时阻止创建快捷方式（按渠道）|
|[RollbackToTargetVersion](#rollbacktotargetversion)|回退到目标版本（按渠道）|
|[TargetVersionPrefix](#targetversionprefix)|目标版本覆盖（各渠道）|

### [首选项](#preferences-policies)
|策略名称|标题|
|-|-|
|[AutoUpdateCheckPeriodMinutes](#autoupdatecheckperiodminutes)|自动更新检查期间替代|
|[UpdatesSuppressed](#updatessuppressed)|每天中取消自动更新检查的时间段|

### [代理服务器](#proxy-server-policies)
|策略名称|描述文字|
|-|-|
|[ProxyMode](#proxymode)|选择指定代理服务器设置的方式|
|[ProxyPacUrl](#proxypacurl)|代理 .pac 文件的 URL|
|[ProxyServer](#proxyserver)|代理服务器的地址或 URL|

### [Microsoft Edge Web 视图](#microsoft-edge-webview-policies)
|策略名称|标题|
|-|-|
|[安装](#install-webview)|允许安装|
|[更新](#update-webview)|更新策略替代|

##  <a name="applications-policies"></a>应用程序策略

[返回页首](#microsoft-edge---update-policies)
###  <a name="installdefault"></a>InstallDefault
#### 允许安装默认项
>Microsoft Edge 更新 1.2.145.5 和更高版本

#### 描述
可指定所有渠道的默认行为，以允许或阻止域连接设备上的Microsoft Edge。

通过为那些特定渠道启用“[允许安装](#install)”策略，可为个别渠道覆盖此策略。

如果禁用此策略，则会阻止 Microsoft Edge的安装。 只有当 "[允许安装](#install)" 策略设置为 "未配置" 时，才会影响Microsoft Edge软件的安装。

此策略不会阻止运行 Microsoft Edge 更新，也不会阻止用户使用其他方法安装 Microsoft Edge 软件。

此策略仅在加入Microsoft® Active Directory®域的Windows实例上可用。
#### Windows 信息和设置
##### 组策略 (ADMX) 信息
- GP 唯一名称：InstallDefault
- GP 名称：允许安装默认项
- GP 路径：Administrative Templates/Microsoft Edge Update/Applications
- GP ADMX文件名：msedgeupdate.admx
##### Windows 注册表设置
- 路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 值名称：InstallDefault
- 值类型：REG_DWORD
##### 示例值：
```
0x00000001
```
[返回页首](#microsoft-edge---update-policies)


###  <a name="updatedefault"></a>UpdateDefault
####  <a name="update"></a>更新策略替代默认值
>Microsoft Edge 更新 1.2.145.5 和更高版本

#### 描述
允许你为所有渠道指定与 Microsoft Edge 更新处理 Microsoft Edge 可用更新的方式有关的默认行为。 通过为那些特定渠道指定“[更新策略替代](#update)”策略，可为个别渠道进行覆盖。

  如果你启用此策略，Microsoft Edge 更新将根据你配置以下选项的方式处理 Microsoft Edge 更新：
   - 始终允许更新：通过定期更新检查或通过手动更新检查，在发现更新时始终应用更新。
   - 仅限自动无提示更新：仅在定期更新检查找到更新后才应用更新。
   - 仅限手动更新：仅当用户运行手动更新检查时才应用更新。
   - 已禁用更新：从不应用更新。

  如果你选择手动更新，请确保使用应用的手动更新机制（如果有）定期检查更新。 如果你禁用更新，请定期检查更新，然后将它们分发给用户。

  如果你未启用和配置此策略，Microsoft Edge 更新将处理“[更新策略替代](#update)”策略指定的可用更新。

  此策略仅在加入Microsoft® Active Directory®域的Windows实例上可用。
#### Windows 信息和设置
##### 组策略 (ADMX) 信息
- GP 唯一名称：UpdateDefault
- GP 名称：更新策略替代默认值
- GP 路径：Administrative Templates/Microsoft Edge Update/Applications
- GP ADMX文件名：msedgeupdate.admx
##### Windows 注册表设置
- 路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 值名称：UpdateDefault
- 值类型：REG_DWORD
##### 示例值：
```
0x00000003
```
[返回页首](#microsoft-edge---update-policies)


###  <a name="install"></a>安装
#### 允许安装
>Microsoft Edge 更新 1.2.145.5 和更高版本

#### 描述
指定是否可以在域连接的设备上安装Microsoft Edge通道。

  如果为渠道启用此策略，则不会阻止 Microsoft Edge 的安装。

  如果为渠道启用此策略，则会阻止 Microsoft Edge 的安装。

  如果没有为渠道配置此策略，则“[允许安装默认项](#installdefault)”策略配置将决定用户是否可以安装Microsoft Edge的该渠道。

  此策略仅在加入Microsoft® Active Directory®域的Windows实例上可用。
#### Windows 信息和设置
##### 组策略 (ADMX) 信息
- GP 唯一名称：安装
- GP 名称：允许安装
- GP 路径： 
  - Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge
  - Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta
  - Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary
  - Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev
- GP ADMX文件名：msedgeupdate.admx
##### Windows 注册表设置
- 路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 值名称： 
  - （稳定）：安装 {56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (Beta)：安装 {2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (Canary)：安装 {65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev)：安装 {0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- 值类型：REG_DWORD
##### 示例值：
```
0x00000001
```
[返回页首](#microsoft-edge---update-policies)


###  <a name="update"></a>更新
####  <a name="update"></a>更新策略替代
>Microsoft Edge 更新 1.2.145.5 和更高版本

#### 描述
指定 Microsoft Edge 更新如何处理 Microsoft Edge 中的可用更新。

如果你启用此策略，Microsoft Edge 更新将根据你配置以下选项的方式处理 Microsoft Edge 更新：
  - 始终允许更新：通过定期更新检查或通过手动更新检查，在发现更新时始终应用更新。
  - 仅限自动无提示更新：仅在定期更新检查找到更新后才应用更新。
  - 仅限手动更新：仅当用户运行手动更新检查时才应用更新。 （并非所有应用都为此选项提供接口。）
  - 已禁用更新：从不应用更新。

如果你选择手动更新，请确保使用应用的手动更新机制（如果有）定期检查更新。 如果你禁用更新，请定期检查更新，然后将它们分发给用户。

如果你未启用和配置此策略，Microsoft Edge 更新将处理“[更新策略替代默认值](#updatedefault)”策略指定的可用更新。

有关详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2136406](https://go.microsoft.com/fwlink/?linkid=2136406)。

此策略仅在加入Microsoft® Active Directory®域的Windows实例上可用。
#### Windows 信息和设置
##### 组策略 (ADMX) 信息
- GP 唯一名称：更新
- GP 名称：更新策略替代
- GP 路径： 
  - Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge
  - Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta
  - Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary
  - Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev
- GP ADMX文件名：msedgeupdate.admx
##### Windows 注册表设置
- 路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 值名称： 
  - （稳定）：更新 {56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (Beta)：更新 {2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (Canary)：更新 {65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev)：更新 {0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- 值类型：REG_DWORD
##### 示例值：
```
0x00000001
```
[返回页首](#microsoft-edge---update-policies)


###  <a name="allowsxs"></a>Allowsxs
#### 允许 Microsoft Edge 并行浏览器体验
>Microsoft Edge 更新 1.2.145.5 和更高版本

#### 说明
此策略允许用户并行运行 Microsoft Edge (Edge HTML) 和 Microsoft Edge（基于 Chromium）。

如果将此策略设置为“未配置”，则在安装 Microsoft Edge（基于 Chromium）稳定渠道和 2019 年 11 月安全更新后，Microsoft Edge（基于 Chromium）将替换 Microsoft Edge (Edge HTML)。  此行为与“已禁用”设置相同。

在安装 Microsoft Edge（基于 Chromium）稳定渠道和 2019 年 11 月安全更新后，“已禁用”设置会阻止并行体验，并且 Microsoft Edge（基于 Chromium）将替换 Microsoft Edge (Edge HTML)。  此行为与“未配置”设置相同。

如果“已启用”此策略，则在安装 Microsoft Edge（基于 Chromium）后，Microsoft Edge（基于 Chromium）和 Microsoft Edge (Edge HTML) 可并行运行。

若要使此组策略生效，必须先配置它，然后再通过 Windows 更新自动安装 Microsoft Edge（基于 Chromium）。 注意：通过使用 Microsoft Edge（基于 Chromium）阻止程序工具包，用户可以阻止自动更新 Microsoft Edge（基于 Chromium）。
#### Windows 信息和设置
##### 组策略 (ADMX) 信息
- GP 唯一名称：Allowsxs
- GP 名称：允许 Microsoft Edge 并行浏览器体验
- GP 路径：Administrative Templates/Microsoft Edge Update/Applications
- GP ADMX文件名：msedgeupdate.admx
##### Windows 注册表设置
- 路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 值名称：Allowsxs
- 值类型：REG_DWORD
##### 示例值：
```
0x00000001
```
[返回页首](#microsoft-edge---update-policies)


###  <a name="createdesktopshortcutdefault"></a>CreateDesktopShortcutDefault
####  <a name="install"></a>安装默认项时阻止创建快捷方式
>Microsoft Edge 更新 1.3.128.0 和更高版本

#### 描述
安装 Microsoft Edge 时，可针对创建桌面快捷方式指定所有渠道的默认行为。

  如果启用此策略，在安装 Microsoft Edge 时会创建桌面快捷方式。
如果禁用此策略，在安装 Microsoft Edge 时不创建桌面快捷方式。
如果未配置此策略，会在安装过程中创建 Microsoft Edge 桌面快捷方式。
如果已安装 Microsoft Edge，此策略将不起作用。
#### Windows 信息和设置
##### 组策略 (ADMX) 信息
- GP 唯一名称：CreateDesktopShortcutDefault
- GP 名称：安装默认项时阻止创建快捷方式
- GP 路径：Administrative Templates/Microsoft Edge Update/Applications
- GP ADMX文件名：msedgeupdate.admx
##### Windows 注册表设置
- 路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 值名称：CreateDesktopShortcutDefault
- 值类型：REG_DWORD
##### 示例值：
```
0x00000001
```
[返回页首](#microsoft-edge---update-policies)


###  <a name="createdesktopshortcut"></a>CreateDesktopShortcut
####  <a name="install"></a>安装时阻止创建快捷方式
>Microsoft Edge 更新 1.3.128.0 和更高版本

#### 描述
如果启用此策略，在安装 Microsoft Edge 时会创建桌面快捷方式。
如果禁用此策略，在安装 Microsoft Edge 时不创建桌面快捷方式。
如果未配置此策略，会在安装过程中创建 Microsoft Edge 桌面快捷方式。
如果已安装 Microsoft Edge，此策略将不起作用。

  如果未为频道配置此策略，则“[Prevent Desktop Shortcut creation upon install default](#createdesktopshortcutdefault)”策略配置将确定在安装 Microsoft Edge 时创建快捷方式。
#### Windows 信息和设置
##### 组策略 (ADMX) 信息
- GP 唯一名称：CreateDesktopShortcut
- GP 名称：安装时阻止创建快捷方式
- GP 路径： 
  - Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge
  - Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta
  - Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary
  - Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev
- GP ADMX文件名：msedgeupdate.admx
##### Windows 注册表设置
- 路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 值名称： 
  - （稳定）：CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- 值类型：REG_DWORD
##### 示例值：
```
0x00000001
```
[返回页首](#microsoft-edge---update-policies)


###  <a name="rollbacktotargetversion"></a>RollbackToTargetVersion
#### 回退到目标版本
>Microsoft Edge 更新 1.3.133.3 和更高版本

#### 描述
指定 Microsoft Edge 更新应将 Microsoft Edge 的安装回退到 "[目标版本覆盖](#targetversionprefix)" 中指定的版本。

除非"[目标版本替代](#targetversionprefix)" 设置为 "开"，并且将 "[更新策略替代](#update)" 设置为 "开启" 状态之一（始终允许更新、仅自动无提示更新，仅限手动更新），否则该策略无效。

如果禁用该策略或不对其进行配置，则安装的版本高于由 "[目标版本替代](#targetversionprefix)" 所指定的版本则将保留原样。

如果启用此策略，则当前版本高于由 "[目标版本替代](#targetversionprefix)" 指定的安装将降级到目标版本。

我们建议用户安装最新版本的 Microsoft Edge 浏览器，以确保受到最新安全更新的保护。 回退到较早版本存在遇到已知安全问题的风险。 该策略旨在作为一种临时修复措施，以解决Microsoft Edge浏览器更新中所面临的问题。

在暂时回退浏览器版本之前，建议你为组织中的所有用户启用同步（[https://go.microsoft.com/fwlink/?linkid=2133032](https://go.microsoft.com/fwlink/?linkid=2133032)）。 如果未启用同步，则有可能造成永久性浏览数据丢失。 使用本政策，风险自担。

注意：可在此处查看所有可供回退的版本 [https://aka.ms/EdgeEnterprise](https://aka.ms/EdgeEnterprise)。

此政策适用于Microsoft Edge 86或更高版本。

有关详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2133918](https://go.microsoft.com/fwlink/?linkid=2133918)。

此策略仅在加入Microsoft® Active Directory®域的Windows实例上可用。
#### Windows 信息和设置
##### 组策略 (ADMX) 信息
- GP 唯一名称：RollbackToTargetVersion
- GP 名称：回退到目标版本
- GP 路径： 
  - Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge
  - Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta
  - Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary
  - Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev
- GP ADMX文件名：msedgeupdate.admx
##### Windows 注册表设置
- 路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 值名称： 
  - （稳定版）：RollbackToTargetVersion{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - （Beta版）：RollbackToTargetVersion{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - （Canary版）：RollbackToTargetVersion{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - （开发者版）：RollbackToTargetVersion{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- 值类型：REG_DWORD
##### 示例值：
```
0x00000001
```
[返回页首](#microsoft-edge---update-policies)


###  <a name="targetversionprefix"></a>TargetVersionPrefix
#### 目标版本覆盖
>Microsoft Edge 更新 1.3.119.43 和更高版本

#### 描述
启用此策略并启用自动更新后，Microsoft Edge 将更新为该策略值指定的版本。

策略值必须是特定的 Microsoft Edge 版本，例如 83.0.499.12。

如果设备的 Microsoft Edge 版本高于指定的值，Microsoft Edge 将保留较新版本，不会降级到指定版本。

如果指定版本不存在，或格式不正确，Microsoft Edge 将保留当前版本，不会自动更新为未来版本。

有关详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2136707](https://go.microsoft.com/fwlink/?linkid=2136707)。

此策略仅在加入Microsoft® Active Directory®域的Windows实例上可用。
#### Windows 信息和设置
##### 组策略 (ADMX) 信息
- GP 唯一名称：TargetVersionPrefix
- GP 名称：目标版本覆盖
- GP 路径： 
  - Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge
  - Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta
  - Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary
  - Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev
- GP ADMX文件名：msedgeupdate.admx
##### Windows 注册表设置
- 路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 值名称： 
  - （稳定版）：TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - （Beta 版）： TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - （金丝雀版）： TargetVersionPrefix {65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - （开发者版本）：更新 {0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- 值类型：REG_SZ
##### 示例值：
```
83.0.499.12
```
[返回页首](#microsoft-edge---update-policies)


##  <a name="preferences-policies"></a>首选项策略

[返回页首](#microsoft-edge---update-policies)
###  <a name="autoupdatecheckperiodminutes"></a>AutoUpdateCheckPeriodMinutes
#### 自动更新检查期间替代
>Microsoft Edge 更新 1.2.145.5 和更高版本

#### 描述
如果启用了此策略，你可以为各次自动更新检查间隔的最小分钟数设置一个值。 否则，默认情况下，自动更新将每 10 小时检查一次更新。

  如果你想要禁用所有自动更新检查，请将该值设置为 0（不推荐）。
#### Windows 信息和设置
##### 组策略 (ADMX) 信息
- GP 唯一名称：AutoUpdateCheckPeriodMinutes
- GP 名称：自动更新检查期间替代
- GP 路径：Administrative Templates/Microsoft Edge Update/Preferences
- GP ADMX文件名：msedgeupdate.admx
##### Windows 注册表设置
- 路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 值名称：AutoUpdateCheckPeriodMinutes
- 值类型：REG_DWORD
##### 示例值：
```
0x00000578
```
[返回页首](#microsoft-edge---update-policies)


###  <a name="updatessuppressed"></a>UpdatesSuppressed
#### 每天中取消自动更新检查的时间段
>Microsoft Edge 更新 1.3.33.5 和更高版本

#### 描述
如果你启用此策略，则每天都会从 Hour:Minute 开始持续一段时间（以分钟为单位）禁止更新检查。 持续时间不受夏令时影响。 例如，如果开始时间是 22:00，持续时间为 480 分钟，则无论夏令时是在此期间开始还是结束，更新都将正好禁止 8 小时。

  如果你禁用或未配置此策略，则不会在任何特定期间取消更新检查。
#### Windows 信息和设置
##### 组策略 (ADMX) 信息
- GP 唯一名称：UpdatesSuppressed
- GP 名称：每天中取消自动更新检查的时间段
  - 选项 { Hour, Minute, Duration }
- GP 路径：Administrative Templates/Microsoft Edge Update/Preferences
- GP ADMX文件名：msedgeupdate.admx
##### Windows 注册表设置
- 路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 值名称： 
  - UpdatesSuppressedDurationMin
  - UpdatesSuppressedStartHour
  - UpdatesSuppressedStartMin
- 值类型：REG_DWORD
##### 示例值：
```
duration   : 0x0000003c
start hour : 0x00000001
start min  : 0x00000002
```
[返回页首](#microsoft-edge---update-policies)


##  <a name="proxy-server-policies"></a>代理服务器策略

[返回页首](#microsoft-edge---update-policies)
###  <a name="proxymode"></a>ProxyMode
#### 选择指定代理服务器设置的方式
>Microsoft Edge 更新 1.3.21.81 和更高版本

#### 描述
允许你指定 Microsoft Edge 更新使用的代理服务器设置。

  如果你启用此策略，则可以在以下代理服务器选项之间进行选择：
   - 如果你选择从不使用代理服务器并且始终直接连接，则所有其他选项都将被忽略。
   - 如果你选择使用系统代理设置或自动检测代理服务器，则所有其他选项都将被忽略。
   - 如果你选择固定服务器代理模式，则可以在 “[代理服务器的地址或 URL](#proxyserver)” 策略中指定更多选项。
   - 如果你选择使用 .pac 代理脚本，则必须在 “[代理 .pac 文件的 URL](#proxypacurl)”策略中为脚本指定 URL。

  如果你启用此策略，则你所在组织中的用户无法在 Microsoft Edge 更新中更改代理设置。

  如果你禁用或未配置此策略，则不会配置任何代理服务器设置，但组织中的用户可以为 Microsoft Edge 更新选择自己的代理设置。
#### Windows 信息和设置
##### 组策略 (ADMX) 信息
- GP 唯一名称：ProxyMode
- GP 名称：选择指定代理服务器设置的方式
- GP 路径：Administrative Templates/Microsoft Edge Update/Proxy Server
- GP ADMX文件名：msedgeupdate.admx
##### Windows 注册表设置
- 路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 值名称：ProxyMode
- 值类型：REG_SZ
##### 示例值：
```
fixed_servers
```
[返回页首](#microsoft-edge---update-policies)


###  <a name="proxypacurl"></a>ProxyPacUrl
#### 代理 .pac 文件的 URL
>Microsoft Edge 更新 1.3.21.81 和更高版本

#### 描述
允许你为代理自动配置 (PAC) 文件指定 URL。

  如果你启用此策略，则可以为 PAC 文件指定 URL，以自动执行 Microsoft Edge 更新为提取特定网站而选择合适代理服务器的方法。

  仅当你已在“[选择如何指定代理服务器设置](#proxymode)”策略中指定了手动代理设置时，才会应用此策略。

  如果你已在“[选择如何指定代理服务器设置](#proxymode)”策略中选择了手动设置以外的其他代理设置，请不要配置此策略。
#### Windows 信息和设置
##### 组策略 (ADMX) 信息
- GP 唯一名称：ProxyPacUrl
- GP 名称：代理 .pac 文件的 URL
- GP 路径：Administrative Templates/Microsoft Edge Update/Proxy Server
- GP ADMX文件名：msedgeupdate.admx
##### Windows 注册表设置
- 路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 值名称：ProxyPacUrl
- 值类型：REG_SZ
##### 示例值：
```
https://www.microsoft.com
```
[返回页首](#microsoft-edge---update-policies)


###  <a name="proxyserver"></a>ProxyServer
#### 代理服务器的地址或 URL
>Microsoft Edge 更新 1.3.21.81 和更高版本

#### 说明
允许你指定供 Microsoft Edge 更新使用的代理服务器的 URL。

  如果启用此策略，则可以设置组织中 Microsoft Edge 更新使用的代理服务器 URL。

  仅当你已在[“选择如何指定代理服务器设置”](#proxymode)策略中选择了手动代理设置时，才会应用此策略。

  如果你已在“[选择如何指定代理服务器设置](#proxymode)”策略中选择了手动设置以外的其他代理设置，请不要配置此策略。
#### Windows 信息和设置
##### 组策略 (ADMX) 信息
- GP 唯一名称：ProxyServer
- GP 名称：代理服务器的地址或 URL
- GP 路径：Administrative Templates/Microsoft Edge Update/Proxy Server
- GP ADMX文件名：msedgeupdate.admx
##### Windows 注册表设置
- 路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 值名称：ProxyServer
- 值类型：REG_SZ
##### 示例值：
```
https://www.microsoft.com
```
[返回页首](#microsoft-edge---update-policies)


##  <a name="microsoft-edge-webview-policies"></a>- Microsoft Edge Web 视图策略

[返回页首](#microsoft-edge---update-policies)
###  <a name="install-(webview)"></a>安装（WebView）
#### 允许安装
>Microsoft Edge 更新 1.3.127.1 和更高版本

#### 描述
指定是否可以使用 Microsoft Edge 更新来安装 Microsoft Edge Web 视图。

  - 如果启用此策略，用户可以通过 Microsoft Edge 更新来安装该 Microsoft Edge Web 视图。
  - 如果禁用此策略，用户无法通过 Microsoft Edge 更新来安装该 Microsoft Edge Web 视图。
  - 如果没有配置此策略，则“[允许安装默认项](#installdefault)”策略配置将决定用户是否可以通过 Microsoft Edge 更新来安装该 Microsoft Edge WebView。
#### Windows 信息和设置
##### 组策略 (ADMX) 信息
- GP 唯一名称：安装
- GP 名称：允许安装
- GP 路径：Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView
- GP ADMX文件名：msedgeupdate.admx
##### Windows 注册表设置
- 路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 值名称： 
  - 安装{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
- 值类型：REG_DWORD
##### 示例值：
```
0x00000001
```
[返回页首](#microsoft-edge---update-policies)


###  <a name="update-(webview)"></a>更新（WebView）
####  <a name="update"></a>更新策略替代
>Microsoft Edge 更新 1.3.127.1 和更高版本

#### 描述
可针对 Microsoft Edge Web 视图指定启用或不启用自动更新。 Microsoft Edge Web 视图是应用程序用来显示 Web 内容的组件。
默认情况下启用自动更新。 禁用 Microsoft Edge Web Edge 自动更新可能会导致依赖于此组件的应用程序出现兼容性问题。

  如果你启用此策略，Microsoft Edge 更新将根据你配置以下选项的方式处理 Microsoft Edge Web 视图更新：
  - 始终允许更新：自动下载和应用更新
  - 禁用更新：从不下载或应用更新。

  如果未启用此策略，则自动下载并应用更新。
#### Windows 信息和设置
##### 组策略 (ADMX) 信息
- GP 唯一名称：更新
- GP 名称：更新策略替代
- GP 路径：Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView
- GP ADMX文件名：msedgeupdate.admx
##### Windows 注册表设置
- 路径：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- 值名称： 
  - Update{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
- 值类型：REG_DWORD
##### 示例值：
```
0x00000001
```
[返回页首](#microsoft-edge---update-policies)


##  <a name="see-also"></a>另请参阅
  - [配置 Microsoft Edge](configure-microsoft-edge.md)
  - [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)