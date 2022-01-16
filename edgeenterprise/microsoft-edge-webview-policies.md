---
title: Microsoft Edge WebView2 政策文档
ms.author: stmoody
author: dan-wesley
manager: tahills
ms.date: 01/13/2022
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Microsoft Edge 浏览器支持的所有策略的 Windows 和 Mac 文档
ms.openlocfilehash: b7810b746abc82bd5c50adb39cc582b71336db63
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2022
ms.locfileid: "12297840"
---
# <a name="microsoft-edge-webview2---policies"></a>Microsoft Edge WebView2 - 策略

最新版本的 Microsoft Edge WebView2 包含以下策略。 可以使用这些策略来配置在你的组织中运行 Microsoft Edge WebView2 的方式。

有关用于控制 Microsoft Edge WebView2 的更新方式和时间的其他策略集的信息，请查看 [Microsoft Edge 更新策略参考](microsoft-edge-update-policies.md)。


> [!NOTE]
> 本文适用于 Microsoft Edge 版本 87 或更高版本。

## <a name="available-policies"></a>可用策略

这些表列出了本版本 Microsoft Edge WebView2 中提供的所有组策略。 使用表中的链接获取有关特定策略的更多详细信息。

- [加载器替代设置](#loader-override-settings)
- [附加](#additional)


### [*<a name="loader-override-settings"></a>加载器替代设置*](#loader-override-settings-policies)

|策略名称|标题|
|-|-|
|[BrowserExecutableFolder](#browserexecutablefolder)|配置浏览器可执行文件文件夹的位置|
|[ReleaseChannelPreference](#releasechannelpreference)|设置发布渠道搜索顺序首选项|
### [*<a name="additional"></a>附加*](#additional-policies)

|策略名称|字幕|
|-|-|
|[ExperimentationAndConfigurationServiceControl](#experimentationandconfigurationservicecontrol)|控制与试验和配置服务的通信|




  ## <a name="loader-override-settings-policies"></a>加载器替代设置策略

  [返回页首](#microsoft-edge-webview2---policies)

  ### <a name="browserexecutablefolder"></a>BrowserExecutableFolder

  #### <a name="configure-the-location-of-the-browser-executable-folder"></a>配置浏览器可执行文件文件夹的位置

  
  
  #### <a name="supported-versions"></a>支持的版本：

  - 在 87 版或更高版本的 Windows 上

  #### <a name="description"></a>描述

  此策略将 WebView2 应用程序配置为在指定路径中使用 WebView2 Runtime。 该文件夹应包含以下文件：msedgewebview2.exe、msedge.dll 等。

若要设置文件夹路径的值，请提供值名称和值对。 将值名称设置为 应用程序用户模型 ID 或可执行文件名称。 可将通配符“*”用作值名称，以便应用于所有应用程序。

  #### <a name="supported-features"></a>支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### <a name="data-type"></a>数据类型：

  - 字符串列表

  #### <a name="windows-information-and-settings"></a>Windows 信息和设置

  ##### <a name="group-policy-admx-info"></a>组策略 (ADMX) 信息

  - GP 唯一名称：BrowserExecutableFolder
  - GP 名称：配置浏览器可执行文件文件夹的位置
  - GP 路径（强制）：管理模板/Microsoft Edge WebView2/加载器替代设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdgeWebView2.admx

  ##### <a name="windows-registry-settings"></a>Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\WebView2\BrowserExecutableFolder
  - 路径（推荐）：不适用
  - 值名称：REG_SZ 列表
  - 值类型：REG_SZ 列表

  ##### <a name="example-value"></a>示例值：

```
SOFTWARE\Policies\Microsoft\Edge\WebView2\BrowserExecutableFolder = "Name: *, Value: C:\\Program Files\\Microsoft Edge WebView2 Runtime Redistributable 85.0.541.0 x64"

```

  

  [返回页首](#microsoft-edge-webview2---policies)

  ### <a name="releasechannelpreference"></a>ReleaseChannelPreference

  #### <a name="set-the-release-channel-search-order-preference"></a>设置发布渠道搜索顺序首选项

  
  
  #### <a name="supported-versions"></a>支持的版本：

  - 在 87 版或更高版本的 Windows 上

  #### <a name="description"></a>描述

  默认渠道搜索顺序是 WebView2 Runtime、Beta、Dev 和未带。

若要反转默认搜索顺序，请将此策略设置为 1。

若要设置发布渠道首选项的值，请提供值名称和值对。 将值名称设置为 应用程序用户模型 ID 或可执行文件名称。 可将通配符“*”用作值名称，以便应用于所有应用程序。

  #### <a name="supported-features"></a>支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### <a name="data-type"></a>数据类型：

  - 字符串列表

  #### <a name="windows-information-and-settings"></a>Windows 信息和设置

  ##### <a name="group-policy-admx-info"></a>组策略 (ADMX) 信息

  - GP 唯一名称：ReleaseChannelPreference
  - GP 名称：设置发布渠道搜索顺序首选项
  - GP 路径（强制）：管理模板/Microsoft Edge WebView2/加载器替代设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdgeWebView2.admx

  ##### <a name="windows-registry-settings"></a>Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\WebView2\ReleaseChannelPreference
  - 路径（推荐）：不适用
  - 值名称：REG_SZ 列表
  - 值类型：REG_SZ 列表

  ##### <a name="example-value"></a>示例值：

```
SOFTWARE\Policies\Microsoft\Edge\WebView2\ReleaseChannelPreference = "Name: *, Value: 1"

```

  

  [返回页首](#microsoft-edge-webview2---policies)

  ## <a name="additional-policies"></a>其他策略

  [返回页首](#microsoft-edge-webview2---policies)

  ### <a name="experimentationandconfigurationservicecontrol"></a>ExperimentationAndConfigurationServiceControl

  #### <a name="control-communication-with-the-experimentation-and-configuration-service"></a>控制与试验和配置服务的通信

  
  
  #### <a name="supported-versions"></a>支持的版本：

  - Windows 97 或更高版本

  #### <a name="description"></a>描述

  试验和配置服务用于将试验和配置有效负载部署到客户端。

试验有效负载包括 Microsoft 为测试和反馈启用的早期开发功能列表。

配置有效负载包含 Microsoft 希望部署到的建议设置列表以优化用户体验。

配置有效负载还可能包含出于兼容性原因对某些域采取的操作列表。 例如，如果某个网站被破坏，则浏览器可能会替代该网站上的用户代理字符串。 当 Microsoft 尝试解决网站所有者的问题时，这些操作中的每一个操作都是临时的。

如果将此策略设置为 'FullMode' 模式，则会从实验和配置服务下载完整的有效负载。 这包括试验和配置有效负载。

如果将此策略设置为 'ConfigurationsOnlyMode' 模式，则仅下载配置有效负载。

如果将此策略设置为 "RestrictedMode"，将完全停止与实验和配置服务的通信。 Microsoft 不建议此设置。

如果未配置此策略，则在 Stable 和 Beta 渠道的受管理设备上，行为与 'ConfigurationsOnlyMode' 模式相同。 在 Canary 和 Dev 频道上，行为与“FullMode”相同。

如果未配置此策略，则在未被管理的设备上，该行为与“FullMode”相同。

策略选项映射：

* FullMode (2) = 检索配置和实验

* ConfigurationsOnlyMode (1) = 仅检索配置

* RestrictedMode (0) = 禁用与实验和配置服务的通信

配置此策略时，请使用上述信息。

  #### <a name="supported-features"></a>支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### <a name="data-type"></a>数据类型：

  - 整型

  #### <a name="windows-information-and-settings"></a>Windows 信息和设置

  ##### <a name="group-policy-admx-info"></a>组策略 (ADMX) 信息

  - GP 唯一名称：ExperimentationAndConfigurationServiceControl
  - GP 名称：控制与试验和配置服务的通信
  - GP 路径（强制）：Administrative Templates/Microsoft Edge WebView2/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdgeWebView2.admx

  ##### <a name="windows-registry-settings"></a>Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\WebView2
  - 路径（推荐）：不适用
  - 值名称：ExperimentationAndConfigurationServiceControl
  - 值类型：REG_DWORD

  ##### <a name="example-value"></a>示例值：

```
0x00000002
```

  

  [返回页首](#microsoft-edge-webview2---policies)


## <a name="see-also"></a>另请参阅

- [配置 Microsoft Edge](configure-microsoft-edge.md)
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [Microsoft 安全基线博客](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/bg-p/Microsoft-Security-Baselines)