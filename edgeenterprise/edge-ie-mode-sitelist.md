---
title: 企业网站配置策略
ms.author: shisub
author: shisub
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 为 Internet Explorer 模式配置企业模式网站列表的分步指南。
ms.openlocfilehash: 72de393a5da0b4b0e2950951ae527f6ef870e110
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "11978881"
---
# <a name="enterprise-site-configuration-strategy"></a>企业网站配置策略

>[!Note]
> Internet Explorer 11 桌面应用程序将于 2022 年 6 月 15 日停用并停止支持（若要查看包含内容的列表， [请参阅常见问题解答](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)）。 现在使用的 IE11 应用和网站可以在 Microsoft Edge 的 Internet Explorer 模式下打开。 [在此处了解详细信息](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。

本文介绍对“企业模式网站列表”的更改，以支持针对 Microsoft Edge 版本 77 和更高版本的 Internet Explorer 模式。

若要详细了解 Enterprise Mode Site List XML 文件的架构，请参阅[企业模式架构 v.2 指南](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。
<!--
## Updated schema elements

The following table describes the \<open-in app\> element added to the v.2 of the Enterprise Mode schema:

| **Element** | **Description** |
| --- | --- |
| \<open-in app="**true**"\> | A child element that controls what browser is used for sites. This element is required for sites that need to **open in IE11**.|

**Example:**

``` xml
<site url="contoso.com">

  <open-in app="true">IE11</open-in>

</site>
```

The following table shows the possible values of the \<open-in\> element:

| **Value** | **Description** |
| --- | --- |
| **\<open-in\>IE11\</open-in\>** | Opens the site in IE mode or a full IE11 window. To enable IE mode, see [Configure IE mode policies](./edge-ie-mode-policies.md)|
| **\<open-in app="**true**"\>IE11\</open-in\>** | Opens the site in a full IE11 window |
| **\<open-in\>MSEdge\</open-in\>** | Opens the site in Microsoft Edge |
| **\<open-in\>None or not specified\</open-in\>** | Opens the site in the default browser or in the browser where the user navigated to the site. |
|**\<open-in\>Configurable\</open-in\>** | Allows the site to participate in IE mode engine determination. To learn more, see [Learn about Configurable sites in IE mode](edge-learnmore-configurable-sites-ie-mode.md).  |

>[!NOTE]
> The attribute app=**"true"** is only recognized when associated to _'open-in' IE11_. Adding it to the other 'open-in' elements won't change browser behavior.   -->

## <a name="configuration-strategy"></a>配置策略

以下步骤是适用于 IE 模式的网站配置策略的一部分：
1. 准备网站列表
2. 配置非特定网站
3. （可选）如有必要，请使用 Cookie 共享

<!--
Step 1.  – if you don’t have one use Site Discovery Step-by-Step
Step 2 – Neutral sites + sticky mode
        Use more examples and explain sticky mode better
Step 3 – If that doesn’t cover your needs, then use Cookie sharing -->

## <a name="prepare-your-site-list"></a>准备网站列表

如果已有 IE11 或 Microsoft Edge 旧版企业模式网站列表，可重复使用该列表来配置 IE 模式。

但是，如果你没有网站列表，可以使用"企业网站 [工具](/deployedge/edge-ie-mode-site-discovery) 你的网站列表。

## <a name="configure-neutral-sites"></a>配置非特定网站

为了使 IE 模式正常工作，需要显式将身份验证/单一登录 （SSO） 服务器配置为非特定站点。 否则，IE 模式网页会尝试重定向到 Microsoft Edge，且身份验证失败。

中性网站使用导航起始浏览器，要么是 Microsoft Edge，要么是 IE 模式。 配置中性网站可确保所有使用这些身份验证服务器的应用程序（无论是新式应用程序还是旧应用程序）都能继续正常运行。

可以通过在 Enterprise Mode Site List Manager 工具中将*打开方式*下拉列表设置为“无”或直接更新站点列表 XML 来配置中性站点：

``` xml
<site url="login.contoso.com">
   
    <open-in>None</open-in>

</site>
```

若要识别身份验证服务器，请使用 IE11 开发人员工具检查来自应用程序的网络流量。 如果需要更多时间来识别身份验证服务器，可以配置策略以在 IE 模式下保留所有页面内导航，以允许用户继续其工作流中断。 若要尽可能减少不必要的 IE 模式使用，在识别并将身份验证服务器添加到网站列表后，请禁用此设置。 有关详细信息，请参阅 [在 IE 模式下保留页面内](/deployedge/edge-learnmore-inpage-nav)。

>[!NOTE]
   >IE 模式集成不支持企业模式架构 v.1。 如果当前正在将架构 v.1 与 Internet Explorer 11 一起使用，则必须升级到架构 v.2。 有关详细信息，请参阅[企业模式架构 v.2 指南](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)。

## <a name="optional-use-cookie-sharing-if-necessary"></a>（可选）如有必要，请使用 Cookie 共享

默认情况下，Microsoft Edge 和 Internet Explorer 进程不共享会话 Cookie，因此在某些情况下，使用 IE 模式时可能不太方便进行共享。 例如，当用户习惯在以前习惯在 IE 模式下重新身份验证，或者当注销 Microsoft Edge 会话时，不会退出关键事务的 Internet Explorer 模式会话。 在这些方案中，可以配置 SSO 设置的特定 Cookie，以便从 Microsoft Edge 发送到 Internet Explorer，以便身份验证体验更加无缝，无需重新身份验证。 有关详细信息，请参阅 从 Microsoft Edge [Internet Explorer 的 Cookie 共享](/deployedge/edge-ie-mode-add-guidance-cookieshare)。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [关于 IE 模式](./edge-ie-mode.md)
- [其他企业模式信息](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
