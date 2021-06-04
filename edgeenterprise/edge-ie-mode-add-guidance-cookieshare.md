---
title: 从 Microsoft Edge 到 Internet Explorer 的 Cookie 共享
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 12/21/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: '如何从 Microsoft Edge 共享 cookie 到 Internet Explorer '
ms.openlocfilehash: ddd9d34b5e2b0ee49093734da82e4a4fa7aa6a69
ms.sourcegitcommit: 306582403d4272831bcac390154c7cc7041a9b7e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2020
ms.locfileid: "11238179"
---
# 从 Microsoft Edge 到 Internet Explorer 的 Cookie 共享

本文介绍了如何在使用 Internet Explorer 模式时，配置从 Microsoft Edge 进程到 Internet Explorer 进程的会话 cookie 共享。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 87 或更高版本。

##  <a name="prerequisites"></a>必备条件

- Windows 更新

  - Windows 10 版本 2004、Windows Server 版本 2004 - KB4571744 或更高版本
  - Windows 10 版本 1909、Windows Server 版本 1909 – KB4566116 或更高版本
  - Windows 10 版本 1903、Windows Server 版本 1903 – KB4566116 或更高版本
  - Windows 10 版本 1809、Windows Server 版本 1809 和 Windows Server 2019 - KB4571748 或更高版本
  - Windows 10 版本 1803 – KB4577032 或更高版本

- Microsoft Edge 版本 87 或更高版本
- [IE 模式](https://aka.ms/iemodeonedge) 配置了企业模式网站列表

##  <a name="overview"></a>概述

大型组织中的常见配置是，将一个在新式浏览器工作的应用程序链接到另一个应用程序上，可能将该应用程序配置为在启用单一登录（SSO）的 Internet Explorer 模式下打开作为工作流的一部分。

默认情况下，Microsoft Edge 和 Internet Explorer 进程不共享会话 cookie，在某些情况下，这可能不方便。 例如，用户必须在 Internet Explorer 模式下重新进行身份验证，或注销 Microsoft Edge 会话时，不会注销 Internet Explorer 模式会话。 在这些方案中，可将由 SSO 设置的特定 cookie 配置为从 Microsoft Edge 发送到 Internet Explorer，以便使验证体验更顺畅，方法是避免重新对其进行身份验证。

> [!NOTE]
> 只能将会话 cookie 从 Microsoft Edge 共享到 Internet Explorer。 无法反向共享会话 cookie（从 Internet Explorer 到 Microsoft Edge）。

##  <a name="how-cookie-sharing-works"></a>Cookie 共享的工作原理

已对企业模式网站列表 XML 进行了扩展，允许其他元素指定需要从 Microsoft Edge 会话共享到 Internet Explorer 的 cookie。  

第一次在 Microsoft Edge 会话中创建 Internet Explorer 模式选项卡时，所有匹配的 cookie 都会共享到 Internet Explorer 会话。 随后，任何时候添加、删除或修改与规则相匹配的 cookie，都将作为 Internet Explorer 会话的更新发送。 更新网站列表时，也会重新评估共享 cookie 的集合。

###  <a name="updated-schema-elements"></a>已更新的架构元素

下表介绍了为支持 cookie 共享功能而添加的 \<shared-cookie\> 元素。

| 元素| 描述 |
|-|-|
| \<shared-cookie **domain**=".contoso.com" **name**="cookie1"\>\</shared-cookie\><br><br>或者<br><br>\<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2"\>\</shared-cookie\>   |**（必需）**\<shared-cookie\> 元素至少需要 *域*（对于域 cookie）或 *主机*（对于仅限主机 cookie）属性和 *名称* 属性。<br>这些必须分别与 cookie 的域和名称完全匹配。 **请注意，** 子域不匹配。<br><br>*域*属性用于域 cookie（允许使用前导圆点，但可选择）。<br>*主机*属性用于仅限主机的 cookie（前导圆点错误）。 指定“两者”或者“两者都不”均会导致错误。<br>* 如果在 cookie 字符串中指定域（通过 HTTP Set-Cookie 响应头或 document.cookie JS API），则 cookie 是域 cookie。 域 cookie 适用于指定域和所有子域。 如果未在 cookie 字符串中指定域，则 cookie 是仅限主机的 cookie，并且仅适用于其设置的特定主机。 请注意，诸如单字主机名（例如 http://intranetsite)）和 IP 地址（例如 http://10.0.0.1)）的一些 URL 类只能设置仅限主机的 cookie。    |
| \<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2" **path**="/a/b/c"\>\</shared-cookie\>  | **（可选）** 可指定*路径*属性。 如果未指定路径属性（或者路径属性为空），则无论路径（通配符规则）如何，任何与域/主机和名称匹配的 Cookie 都会与策略匹配。<br><br>如果指定了路径，则它必须完全匹配。<br>如果 cookie 与带有路径的规则匹配，则优先级高于不带路径的规则。 |

#### 共享示例

```xml
<site-list version="1">
<shared-cookie domain=".contoso.com" name="cookie1"></shared-cookie> 
<shared-cookie host="subdomain.contoso.com" name="cookie2" path="/a/b/c">
</shared-cookie>
</site-list>
```

##  <a name="see-also"></a>另请参阅

- [关于 IE 模式](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [可配置的网站信息](https://docs.microsoft.com/deployedge/edge-learnmore-configurable-sites-ie-mode)
- [其他企业模式信息](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
