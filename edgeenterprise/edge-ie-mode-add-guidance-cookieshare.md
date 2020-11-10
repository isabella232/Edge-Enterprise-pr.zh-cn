---
title: 从 Microsoft Edge 到 Internet Explorer 的 Cookie 共享
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 11/05/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: '如何将 cookie 从 Microsoft Edge 共享到 Internet Explorer '
ms.openlocfilehash: 5740a4ce31a240573b9106e7a20a5c44688aca0a
ms.sourcegitcommit: 2024629929044e2dcf146674058c1d6312c32e9a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2020
ms.locfileid: "11157535"
---
# 从 Microsoft Edge 到 Internet Explorer 的 Cookie 共享

本文介绍了如何在使用 Internet Explorer 模式时配置从 Microsoft Edge 过程到 Internet Explorer 进程的会话 cookie 共享。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 87 或更高版本。

## 必备条件

- Windows 更新

  - Windows 10 版本2004，Windows Server 版本 2004 – KB4571744 或更高版本
  - Windows 10 版本1909，Windows Server 版本 1909 – KB4566116 或更高版本
  - Windows 10 版本1903，Windows Server 版本 1903 – KB4566116 或更高版本
  - Windows10 版本 1809、Windows Server 版本 1809 和 Windows Server 2019 - KB4571748 或更高版本
  - Windows 10 版本 1803 – KB4577032 或更高版本

- Microsoft Edge 版本 87 或更高版本
- [IE 模式](https://aka.ms/iemodeonedge) 配置了企业模式网站列表

## 概述

大型组织中的常见配置是，将一个应用程序处理到另一个应用程序的新式浏览器链接中，该应用程序可能配置为在工作流中启用单一登录（SSO）的 Internet Explorer 模式下打开。

默认情况下，Microsoft Edge 和 Internet Explorer 进程不共享会话 cookie，在某些情况下，这可能不方便。 例如，用户必须在 Internet Explorer 模式下重新进行身份验证，或注销 Microsoft Edge 会话时，不会注销 Internet Explorer 模式会话。 在这些方案中，可将由 SSO 设置的特定 cookie 配置为从 Microsoft Edge 发送到 Internet Explorer，以便验证体验更无缝，方法是避免重新对其进行身份验证。

> [!NOTE]
> 只能将会话cookie从 Microsoft Edge 共享到 Internet Explorer。 无法反向共享会话 cookie （从 Internet Explorer 到 Microsoft Edge）。

## Cookie 共享的工作原理

企业模式网站列表 XML 已扩展，允许其他元素指定需要从 Microsoft Edge 会话与 Internet Explorer 共享的 cookie。  

第一次在 Microsoft Edge 会话中创建 Internet Explorer "模式" 选项卡时，所有匹配的 cookie 都会共享到 Internet Explorer 会话。 随后，任何时候都会添加、删除或修改与规则相匹配的 cookie，作为 Internet Explorer 会话的更新发送。 更新网站列表时，也会重新计算共享 cookie 的集合。

### 已更新的架构元素

下表介绍了为支持 cookie 共享功能而添加的 \<shared-cookie\> 元素。

| 元素| 描述 |
|-|-|
| \<shared-cookie **domain**=".contoso.com" **name**="cookie1"\>\</shared-cookie\><br><br>或者<br><br>\<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2"\>\</shared-cookie\>   |**（必需）** \<shared-cookie\> 元素至少需要 *域* （对于域 cookie）或 *主机* （对于仅限主机 cookie）属性和 *名称* 属性。<br>这些必须与 cookie 的域和名称分别完全匹配。 **请注意，** 子域不匹配。<br><br>*域* 属性用于域 cookie （并允许使用前导圆点，但可选择）。<br>*主机* 属性用于仅限主机的 cookie （前导圆点是错误）。 指定 "不" 或两者都将导致错误。<br>* 如果在 cookie 字符串中指定域（通过 HTTP Set-Cookie 响应头或文档），则 cookie 是域 cookie。 域cookie适用于指定域和所有子域。 如果未在 cookie 字符串中指定域，则 cookie 是仅限主机的 cookie，并且仅适用于其设置的特定主机。 请注意，诸如单字主机名（例如 http://intranetsite) ）和 IP 地址（例如 http://10.0.0.1) ）的一些 URL 类只能设置仅限主机的 cookie。    |
| \<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2" **path**="/a/b/c"\>\</shared-cookie\>  | **（可选）** 可指定 *路径* 属性。 如果未指定路径属性（或者路径属性为空），则无论路径规则如何，任何与域/主机和名称匹配的 Cookie 都会与策略匹配。<br><br>如果指定了路径，则它必须完全匹配。<br>如果 cookie 与带有路径的规则匹配，则优先于不带路径的规则。 |

#### 共享示例

```xml
<site-list version="1">
<shared-cookie domain=".contoso.com" name="cookie1"></shared-cookie> 
<shared-cookie host="subdomain.contoso.com" name="cookie2" path="/a/b/c">
</shared-cookie>
</site-list>
```

## 另请参阅

- [关于 IE 模式](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [可配置的网站信息](https://docs.microsoft.com/deployedge/edge-learnmore-configurable-sites-ie-mode)
- [其他企业模式信息](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
