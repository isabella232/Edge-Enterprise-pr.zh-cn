---
title: 在 Enterprise Mode Site List 中配置网站
ms.author: cjacks
author: cjacks
manager: saudm
ms.date: 05/28/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 配置 Enterprise Mode Site List
ms.openlocfilehash: 969a4f6001dbe08a51c26ecf35812b101d315a59
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979349"
---
# 在 Enterprise Mode Site List 中配置网站

本文介绍了对 Enterprise Mode Site List 的更改，此列表支持配置用于 Microsoft Edge 版本 77 及更高版本的 IE 模式。

若要详细了解 Enterprise Mode Site List XML 文件的架构，请参阅[企业模式架构 v.2 指南](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)。

> [!NOTE]
> 本文适用于 Microsoft Edge **Stable**、**Beta** 和 **Dev** 渠道版本 77 或更高版本。

## 已更新的架构元素

下表描述了添加到企业模式架构 v.2 中的 \<open-in app\> 元素：

| **元素** | **描述** |
| --- | --- |
| \<open-in app="**true**"\> | 控制哪个浏览器用于站点的子元素。 对于需要**在 IE11 中打开**的站点，此元素是必需的。|

**示例：**

``` xml
<site url="contoso.com">

  <open-in app="true">IE11</open-in>

</site>
```

下表显示了 \<open-in\> 元素的可能值：

| **值** | **描述** |
| --- | --- |
| **\<open-in\>IE11\</open-in\>** | 在 IE 模式下或在完整的 IE11 窗口中打开网站。 若要启用 IE 模式，请参阅[配置 IE 模式策略](https://docs.microsoft.com/deployedge/edge-ie-mode-policies)|
| **\<open-in app="**true**"\>IE11\</open-in\>** | 在完整的 IE11 窗口中打开网站 |
| **\<open-in\>MSEdge\</open-in\>** | 在 Microsoft Edge 中打开网站 |
| **\<open-in\>无或未指定\</open-in\>** | 在默认浏览器中或在用户导航到网站所用的浏览器中打开网站。 |
|**\<open-in\>可配置\</open-in\>** | 允许网站参与 IE 模式引擎确定。 若要了解详细信息，请参阅[了解 IE 模式下的可配置网站](edge-learnmore-configurable-sites-ie-mode.md)。  |

>[!NOTE]
> 仅当与 _"open-in" IE11_ 关联时，才可识别属性 app=**"true"**。 将其添加到其他“open-in”元素不会更改浏览器行为。   

## 配置非特定网站

必须将身份验证/单一登录服务器显式配置为中性网站，IE 模式才能正常运行。 否则，IE 模式网页会尝试重定向到 Microsoft Edge，且身份验证失败。

中性网站使用导航起始浏览器，要么是 Microsoft Edge，要么是 IE 模式。 配置中性网站可确保所有使用这些身份验证服务器的应用程序（无论是新式应用程序还是旧应用程序）都能继续正常运行。

可以通过在 Enterprise Mode Site List Manager 工具中将*打开方式*下拉列表设置为“无”或直接更新站点列表 XML 来配置中性站点：

``` xml
<site url="login.contoso.com">
   
    <open-in>None</open-in>

</site>
```

若要识别身份验证服务器，请使用 IE11 开发人员工具检查来自应用程序的网络流量。 如果需要更多时间来识别身份验证服务器，可以将策略配置为让所有页内导航都一直使用 IE 模式。 为了最大限度地减少 IE 模式的使用，在识别身份验证服务器并将它们添加到网站列表后，请禁用此设置。 有关详细信息，请参阅[将页内导航配置为一直使用 IE 模式](https://docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationsiteredirect)。

>[!NOTE]
   >IE 模式集成不支持企业模式架构 v.1。 如果当前正在将架构 v.1 与 Internet Explorer 11 一起使用，则必须升级到架构 v.2。 有关详细信息，请参阅[企业模式架构 v.2 指南](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)。

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [关于 IE 模式](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [其他企业模式信息](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)