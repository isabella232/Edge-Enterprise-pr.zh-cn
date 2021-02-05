---
title: Microsoft Edge WebView2 政策文档
ms.author: stmoody
author: dan-wesley
manager: tahills
ms.date: 02/03/2021
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Microsoft Edge 浏览器支持的所有策略的 Windows 和 Mac 文档
ms.openlocfilehash: 774e92c265d1a9bfca1f68b18f34a1262a418946
ms.sourcegitcommit: 5cdcf44324e35c3ac71d7ca78e512f64d4dcbfea
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2021
ms.locfileid: "11313430"
---
# Microsoft Edge WebView2 - 策略

最新版本的 Microsoft Edge WebView2 包含以下策略。 可以使用这些策略来配置在你的组织中运行 Microsoft Edge WebView2 的方式。

有关用于控制 Microsoft Edge WebView2 的更新方式和时间的其他策略集的信息，请查看 [Microsoft Edge 更新策略参考](microsoft-edge-update-policies.md)。


> [!NOTE]
> 本文适用于 Microsoft Edge 版本 87 或更高版本。

## 可用策略

这些表列出了本版本 Microsoft Edge WebView2 中提供的所有组策略。 使用表中的链接获取有关特定策略的更多详细信息。

|||
|-|-|
|[加载器替代设置](#loader-override-settings)|

### [*加载器替代设置*](#loader-override-settings-policies)

|策略名称|标题|
|-|-|
|[BrowserExecutableFolder](#browserexecutablefolder)|配置浏览器可执行文件文件夹的位置|
|[ReleaseChannelPreference](#releasechannelpreference)|设置发布渠道搜索顺序首选项|




  ## 加载器替代设置策略

  [返回页首](#microsoft-edge-webview2---policies)

  ### BrowserExecutableFolder

  #### 配置浏览器可执行文件文件夹的位置

  
  
  #### 支持的版本：

  - 在 87 版或更高版本的 Windows 上

  #### 描述

  此策略将 WebView2 应用程序配置为在指定路径中使用 WebView2 Runtime。 该文件夹应包含以下文件：msedgewebview2.exe、msedge.dll 等。

若要设置文件夹路径的值，请提供值名称和值对。 将值名称设置为 应用程序用户模型 ID 或可执行文件名称。 可将通配符“*”用作值名称，以便应用于所有应用程序。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：BrowserExecutableFolder
  - GP 名称：配置浏览器可执行文件文件夹的位置
  - GP 路径（强制）：管理模板/Microsoft Edge WebView2/加载器替代设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdgeWebView2.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\WebView2\BrowserExecutableFolder
  - 路径（推荐）：不适用
  - 值名称：REG_SZ 列表
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\WebView2\BrowserExecutableFolder = "Name: *, Value: C:\\Program Files\\Microsoft Edge WebView2 Runtime Redistributable 85.0.541.0 x64"

```

  

  [返回页首](#microsoft-edge-webview2---policies)

  ### ReleaseChannelPreference

  #### 设置发布渠道搜索顺序首选项

  
  
  #### 支持的版本：

  - 在 87 版或更高版本的 Windows 上

  #### 描述

  默认渠道搜索顺序是 WebView2 Runtime、Beta、Dev 和未带。

若要反转默认搜索顺序，请将此策略设置为 1。

若要设置发布渠道首选项的值，请提供值名称和值对。 将值名称设置为 应用程序用户模型 ID 或可执行文件名称。 可将通配符“*”用作值名称，以便应用于所有应用程序。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ReleaseChannelPreference
  - GP 名称：设置发布渠道搜索顺序首选项
  - GP 路径（强制）：管理模板/Microsoft Edge WebView2/加载器替代设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdgeWebView2.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\WebView2\ReleaseChannelPreference
  - 路径（推荐）：不适用
  - 值名称：REG_SZ 列表
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\WebView2\ReleaseChannelPreference = "Name: *, Value: 1"

```

  

  [返回页首](#microsoft-edge-webview2---policies)


## 另请参阅

- [配置 Microsoft Edge](configure-microsoft-edge.md)
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [Microsoft 安全基线博客](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/bg-p/Microsoft-Security-Baselines)