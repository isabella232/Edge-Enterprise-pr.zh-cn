---
title: Microsoft Edge 和 Internet Explorer 之间的 Cookie 共享
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 03/08/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 了解如何在 Microsoft Edge 和 Internet Explorer 之间共享 Cookie
ms.openlocfilehash: 403404c96b91cde62e714324864b87ff2e57f8db
ms.sourcegitcommit: dd8cdbd35726c795ddce917e549ddf17ee7f5290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "12473419"
---
# <a name="cookie-sharing-between-microsoft-edge-and-internet-explorer"></a>Microsoft Edge 和 Internet Explorer 之间的 Cookie 共享

>[!Note]
> Internet Explorer (IE) 11 桌面应用程序将于 2022 年 6 月 15 日停用并停止支持。 若要查看 IE 11 停用时范围和范围外的内容，请参 [阅 Internet Explorer 11 桌面应用停用常见问题解答](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)。 现在使用的相同 IE 11 应用和站点可以在 Internet Explorer 模式下Microsoft Edge打开。 若要了解详细信息，请参阅Windows 10[上的 Internet Explorer 的未来Microsoft Edge](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。

本文介绍如何使用 Internet Explorer 模式在Microsoft Edge进程和 Internet Explorer 进程之间配置会话 Cookie 共享。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 87 或更高版本。

## <a name="prerequisites"></a>必备条件

将会话 Cookie 从Microsoft Edge共享到 Internet Explorer：

- Windows 更新

  - Windows 11
  - Windows 10 版本 2004、Windows Server 版本 2004 - KB4571744 或更高版本
  - Windows 10 版本 1909、Windows Server 版本 1909 – KB4566116 或更高版本
  - Windows 10 版本 1903、Windows Server 版本 1903 – KB4566116 或更高版本
  - Windows 10 版本 1809、Windows Server 版本 1809 和 Windows Server 2019 - KB4571748 或更高版本
  - Windows 10 版本 1803 – KB4577032 或更高版本
  - Windows 10 企业版 2016 LTSC 和 Windows Server 2016 - KB4580346 或更高版本
  - Windows 10 企业版 2015 长期服务 - KB4580327 或更高版本
  - Windows 8.1和Windows Server 2012 R2 - KB4586768 或更高版本
  - Windows 10 企业版 2016 LTSC 和 Windows Server 2016 - KB4580346 或更高版本
  - Windows 10 企业版 2015 长期服务 - KB4580327 或更高版本
  - Windows 8.1和Windows Server 2012 R2 - KB4586768 或更高版本
- Microsoft Edge 版本 87 或更高版本
- [IE 模式](./edge-ie-mode.md) 配置了企业模式网站列表

若要在 Microsoft Edge 和 Internet Explorer 之间共享会话 Cookie：

- Windows 更新
  
  - Windows 11 - KB5010414 或更高版本
  - Windows服务器 2022 - KB5010421 或更高版本
  - Windows 10版本 20H2 - KB5010415 或更高版本
  - Windows 10版本 21H1 - KB5010415 或更高版本
  - Windows 10版本 21H2- KB5010415 或更高版本
- Microsoft Edge版本 99 或更高版本
- [IE 模式](./edge-ie-mode.md) 配置了企业模式网站列表

## <a name="overview"></a>概述

大型组织中的常见配置是，将一个在新式浏览器工作的应用程序链接到另一个应用程序上，可能将该应用程序配置为在启用单一登录（SSO）的 Internet Explorer 模式下打开作为工作流的一部分。

默认情况下，Microsoft Edge和 Internet Explorer 进程不共享会话 Cookie，在某些情况下，这种缺少共享可能不方便。 例如，当用户必须以 Internet Explorer 模式重新身份验证或注销Microsoft Edge会话时，不会注销 Internet Explorer 模式会话。 在这些方案中，可以配置 SSO 设置的特定 Cookie，以便从 Microsoft Edge 发送到 Internet Explorer，以便身份验证体验更加无缝，无需重新身份验证。

> [!NOTE]
> 在Microsoft Edge版本 99 之前，只能将会话 Cookie 从Microsoft Edge共享到 Internet Explorer。 从 Microsoft Edge 版本 99 开始，可以将会话 Cookie 从 Internet Explorer 反向 (共享到Microsoft Edge) 。

## <a name="how-cookie-sharing-works"></a>Cookie 共享的工作原理

扩展了Enterprise模式站点列表 XML，以允许更多元素指定需要在 Microsoft Edge 和 Internet Explorer 之间共享的会话 Cookie。

第一次在 Microsoft Edge 会话中创建 Internet Explorer 模式选项卡时，所有匹配的 cookie 都会共享到 Internet Explorer 会话。 之后，每当添加、删除或修改与规则匹配的 Cookie 时，它将作为更新发送到 Internet Explorer 会话。 更新网站列表时，还会重新计算共享 Cookie 集。

### <a name="updated-schema-elements"></a>已更新的架构元素

下表介绍了为支持 cookie 共享功能而添加的 \<shared-cookie\> 元素。

| 元素| 描述 |
|-|-|
| \<shared-cookie **domain**=".contoso.com" **name**="cookie1"\>\</shared-cookie\><br><br>或者<br><br>\<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2"\>\</shared-cookie\>   |**（必需）**\<shared-cookie\> 元素至少需要 *域*（对于域 cookie）或 *主机*（对于仅限主机 cookie）属性和 *名称* 属性。<br>这些属性必须分别与 Cookie 的域和名称完全匹配。 **请注意，** 子域不匹配。<br><br>*域*属性用于域 cookie（允许使用前导圆点，但可选择）。<br>*主机*属性用于仅限主机的 cookie（前导圆点错误）。 指定“两者”或者“两者都不”均会导致错误。<br>* 如果在 cookie 字符串中指定域（通过 HTTP Set-Cookie 响应头或 document.cookie JS API），则 cookie 是域 cookie。 域 cookie 适用于指定域和所有子域。 如果 Cookie 字符串中未指定域，则 Cookie 是仅限主机的 Cookie，并且仅适用于其设置的特定主机。 例如 http://intranetsite) ，一些 URL 类（例如单字主机名 (和 IP 地址 (http://10.0.0.1) ）只能设置仅限主机的 Cookie。    |
| \<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2" **path**="/a/b/c"\>\</shared-cookie\>  | **（可选）** 可指定*路径*属性。 如果未指定路径属性（或者路径属性为空），则无论路径（通配符规则）如何，任何与域/主机和名称匹配的 Cookie 都会与策略匹配。<br><br>如果指定了路径，则它必须完全匹配。<br>如果 cookie 与带有路径的规则匹配，则优先级高于不带路径的规则。 |
| \<shared-cookie **domain**=".contoso.com" **name**="cookie1" **source-engine**="MSEdge"\>\</shared-cookie\><br><br>或者<br><br>\<shared-cookie **domain**=".contoso.com" **name**="cookie1" **source-engine**="IE11"\>\</shared-cookie\><br><br>或者<br><br>\<shared-cookie **domain**=".contoso.com" **name**="cookie1" **source-engine**="Both"\>\</shared-cookie\> | ** (可选) **源引擎属性指定如何在Microsoft Edge和 Internet Explorer 之间共享会话 Cookie。 其中：<br><br>- **MSEdge**。 将会话 Cookie 从Microsoft Edge共享到 Internet Explorer。<br>- **IE11**.  从 Internet Explorer 共享会话 Cookie 以Microsoft Edge。<br>- **两者。** 在 Microsoft Edge 和 Internet Explorer 中共享会话 Cookie。<br>- **默认值或未指定**。 会话 Cookie 将从Microsoft Edge共享到 Internet Explorer。 |

#### <a name="sharing-example"></a>共享示例

```xml
<site-list version="1"> 
<shared-cookie domain=".contoso.com" name="cookie1"></shared-cookie>  
<shared-cookie host="subdomain.contoso.com" name="cookie2" path="/a/b/c"> 
</shared-cookie> 
<shared-cookie host="subdomain.contoso.com" name="cookie3" source-engine="MSEdge"></shared-cookie> 
</site-list> 
```

## <a name="see-also"></a>另请参阅

- [关于 IE 模式](./edge-ie-mode.md)
- [可配置的网站信息](./edge-learnmore-configurable-sites-ie-mode.md)
- [其他企业模式信息](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
