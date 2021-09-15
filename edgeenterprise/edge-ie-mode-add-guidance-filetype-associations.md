---
title: 将文件扩展名与 Internet Explorer 模式关联
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 将文件扩展名与 Internet Explorer 模式关联
ms.openlocfilehash: 7efa30a6ec3013cf5b1595471f1fb91dca8bdfda
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "11978936"
---
# <a name="associate-file-extensions-with-internet-explorer-mode"></a>将文件扩展名与 Internet Explorer 模式关联

>[!Note]
> Internet Explorer 11 桌面应用程序将于 2022 年 6 月 15 日停用并停止支持（若要查看包含内容的列表，[请参阅常见问题解答](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)）。 现在使用的 IE11 应用和网站可以在 Microsoft Edge 的 Internet Explorer 模式下打开。 [在此处了解详细信息](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。

本文介绍如何将 Microsoft Edge 和 Internet Explorer 模式与桌面应用程序的文件扩展名相关联。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 86 或更高版本。

## <a name="guidance-for-file-extension-association-with-internet-explorer-mode"></a>与 Internet Explorer 模式的文件扩展名关联指南

以下说明显示了一个将 Microsoft Edge 和 IE 模式与 .mht 文件类型相关联的条目。 请使用以下步骤作为设置文件关联的指南。

> [!NOTE]
> 你可以使用策略**设置默认关联配置文件**，从而将特定文件扩展名设置为默认情况下在 Internet Explorer 模式下打开。 有关详细信息，请参阅[策略 CSP - ApplicationDefaults](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)。

1. 使用 Microsoft Edge 频道定义一个新的 ProgID，用于以 Internet Explorer 模式打开。 ProgID 包括应用程序名称和图标以及 msedge.exe 的完整路径。

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\Application]
"ApplicationCompany"="Microsoft Corporation"
"ApplicationName"="Microsoft Edge with IE Mode"
"ApplicationIcon"="C:\\<edge_installation_dir>\\msedge.exe,4"
"AppUserModelId"=""
```

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\DefaultIcon]
@="C:\\<edge_installation_dir>\\msedge.exe,4"
```

2. 配置 shell 更新以传递使用 IE 模式打开所需的命令行。

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open\command]
@="\"C:\\<edge_installation_dir>\\msedge.exe\" -ie-mode-file-url -- \"%1\""
```

3. 最后，将 .mht 文件扩展名与新的 ProgID 关联。 将你的 ProgID 添加为值名称，其值类型为 REG_SZ。

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.mht\OpenWithProgids]
"MSEdgeIEModeMHT"=hex(0):
```

设置上例中所述的注册表项后，用户将在“**打开方式**菜单上看到一个附加选项，可使用 Microsoft Edge \<channel\> 和 IE 模式打开 .mht 文件。

## <a name="registry-example"></a>注册表示例

你可以将以下代码片段另存为 .reg 文件并将其导入注册表。

```markdown
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.mht\OpenWithProgids]
"MSEdgeIEModeMHT"=hex(0):

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT]

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\Application]
"ApplicationCompany"="Microsoft Corporation"
"ApplicationName"="Microsoft Edge with IE Mode"
"ApplicationIcon"="C:\\<edge_installation_dir>\\msedge.exe,4"
"AppUserModelId"=""

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\DefaultIcon]
@="C:\\<edge_installation_dir>\\msedge.exe,4"

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell]

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open]

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open\command]
@="\"C:\\<edge_installation_dir>\\msedge.exe\" -ie-mode-file-url -- \"%1\""

```

## <a name="configuring-file-types-to-open-in-internet-explorer-mode"></a>配置文件类型以在 Internet Explorer 模式下打开

从 Microsoft Edge 88 开始，你可以使用策略[“显示上下文菜单以 在 Internet Explorer 模式下打开链接”](./microsoft-edge-policies.md#internetexplorerintegrationreloadiniemodeallowed)将特定文件类型链接配置为在 Internet Explorer 模式下打开，。

通过在此策略[“在 Internet Explorer 模式下打开本地文件文件扩展名允许列表”](./microsoft-edge-policies.md#internetexplorerintegrationlocalfileextensionallowlist)中指定文件扩展名，可以定义此选项应应用的文件类型。 

## <a name="see-also"></a>另请参阅

- [关于 IE 模式](./edge-ie-mode.md)
- [可配置的网站信息](./edge-learnmore-configurable-sites-ie-mode.md)
- [其他企业模式信息](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [设置文件类型关联](/windows/win32/shell/fa-file-types)
- [Microsoft Edge Enterprise 登陆页面](https://aka.ms/EdgeEnterprise)