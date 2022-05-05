---
title: Microsoft Edge将禁用修改“document.domain”
ms.author: niarci
author: dan-wesley
manager: erikan
ms.date: 04/25/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge将禁用修改“document.domain”
ms.openlocfilehash: 197334da0f70aa2cfa081a240de383c79fbbf701
ms.sourcegitcommit: 592f6e40b13e28af588473b2a75c3ae697e5db2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2022
ms.locfileid: "12505703"
---
# <a name="microsoft-edge-will-disable-modifying-documentdomain"></a>Microsoft Edge将禁用修改`document.domain`

> [!NOTE]
> 本文适用于Microsoft Edge稳定版本 106 或更高版本。

> [!WARNING]
> 如果你的网站依赖于通过 `document.domain`放宽同源策略，则需要执行操作。 继续阅读有关此更改的原因的详细信息，或转到 [备用跨源通信](#alternative-cross-origin-communication) ，了解实现跨源通信的替代机制。

## <a name="introduction"></a>简介

文档接口的“域”属性获取或设置当前文档源的域部分，如 [同一源策略](https://developer.mozilla.org/docs/Web/Security/Same-origin_policy)所用。

从 Microsoft Edge 版本 106 开始，将忽略使用 JavaScript 修改`document.domain`属性的尝试。 需要使用替代方法（例如 `postMessage()` 频道消息传送 API）来跨源通信。

另一种选择是，如果你的网站依赖于同源策略放宽才能 `document.domain` 正常运行，则网站可能会发送标 `Origin-Agent-Cluster: ?0` 头;必须从需要放松的所有其他文档发送此标头。

> [!NOTE]
> `document.domain` 如果只有一个文档设置，则不起作用。

## <a name="why-make-documentdomain-immutable"></a>为什么使 `document.domain` 不可变？

某些网站设置为 `document.domain` 允许“同一站点但跨源”页面之间的通信。 通过设置 `document.domain` ，同一站点文档可以更轻松地进行通信。 由于此更改 [放宽了同源策略](https://html.spec.whatwg.org/multipage/origin.html#relaxing-the-same-origin-restriction)，因此父页面可以访问同一站点 iframe 的文档并遍历 DOM 树，反之亦然。

> [!IMPORTANT]
> 同一站点但跨源站点具有相同的 [eTLD+1](https://web.dev/same-site-same-origin/#:~:text=the%20whole%20site%20name%20is%20known%20as%20the%20etld%2B1) ，但具有不同的子域。

假设一个页面嵌`https://parent.example.com`入了 iframe 页面。`https://video.example.com` 这些页面具有具有不同子域的相同 eTLD+1 (`example.com`) 。 当这两个页面 `document.domain` 设置为 `'example.com'`时，浏览器会将这两个页面视为同源页面。

这种技术很方便：但它带来了安全风险。  

## <a name="security-concerns-with-documentdomain"></a>安全问题 `document.domain`

围绕 `document.domain` 安全问题导致规范发生更改，该规范警告开发人员注意这一问题，并告诉他们尽可能避免使用它。 当前 [与其他浏览器供应商](https://github.com/w3ctag/design-reviews/issues/564) 的讨论正朝着同一方向发展。

以下示例演示攻击者如何滥用 `document.domain`。

考虑为每个客户提供唯一子域的共享托管服务。 如果开发人员在其页面中设置 `document.domain` ，则从其他子域提供的攻击者页面可以设置相同的值并修改受害者页面的内容。

同样，请考虑使用每个客户的不同端口为页面提供服务的共享托管服务。 如果开发人员在其页面中设置 `document.domain` ，则从其他端口提供的攻击者页面可以设置相同的值并修改受害者页面的内容。 此攻击是可能的，因为 `document.domain` 忽略源的端口号组件。

> [!NOTE]
>若要详细了解设置 `document.domain`的安全含义，请阅读 [有关 MDN 的 Document.domain 文章](https://developer.mozilla.org/docs/Web/API/Document/domain#setter)。

## <a name="how-will-i-know-if-my-site-is-affected"></a>如何知道我的网站是否受到影响？

如果网站受到此更改的影响，Microsoft Edge将在 DevTools 问题面板中显示警告。 以下屏幕截图显示了此警告的示例。

:::image type="content" source="media/edge-learnmore-origin-keyed-agent-cluster/document-domain-modification-warning.png" alt-text="修改 document.domain 时发出警告。":::

如果设置了报表终结点，也会发送弃用报表。 详细了解 [如何将报表 API](https://web.dev/reporting-api/) 与现有报表收集服务结合使用，或构建自己的报表解决方案。

> [!TIP]
> 可以通过 [LightHouse 弃用的 API 审核](https://web.dev/deprecations/)运行站点，以查找计划从Microsoft Edge中删除的所有 API。

## <a name="alternative-cross-origin-communication"></a>替代跨源通信

目前，有两个选项可供网站替换 `document.domain` 。 在大多数用例中，跨源 [postMessage () ](https://developer.mozilla.org/docs/Web/API/Window/postMessage) 或 [通道消息传送 API](https://developer.mozilla.org/docs/Web/API/Channel_Messaging_API) 可以替换 `document.domain`。

以下列表显示开发人员需要执行的步骤 `postMessage()` ，而不是 `document.domain` 用于跨源 DOM 操作。

1. `https://parent.example.com` 通过 `postMessage()` iframe 发送消息，其中包含 `https://video.example.com` 要求其修改其自己的 DOM。
2. `https://video.example.com` 操作其 DOM，并用于 `postMessage` 通知父级其成功。
3. `https://parent.example.com` 确认成功。

对于步骤 1，请执行下一步 `https://parent.example.com`：

```

// Configure a handler to receive messages from the subframe.
iframe.addEventListener('message', (event) => { 

// Reject all messages except from https://video.example.com 
  if (event.origin !== 'https://video.example.com') return;
  
  // Filter success messages 
    if (event.data === 'succeeded') { 

    // DOM manipulation is succeeded 

  } 

}); 

// Send a message to the subframe at https://video.example.com

iframe.postMessage('Request DOM manipulation', 'https://video.example.com'); 

```

对于步骤 2，请执行下一步 `https://video.example.com`：

```

// Configure a handler to receive messages from the parent frame.
window.addEventListener('message', (event) => {
 
  // Reject all messages except ones from https://parent.example.com 
  
  if (event.origin !== 'https://parent.example.com') return;
  
  // Perform requested DOM manipulation on https://video.example.com.
  
  if (event.data === "showTheButton") {
     document.getElementById('btnContinue').style.visibility = 'visible';
     // Send a success message back to the parent.

     event.source.postMessage('succeeded', event.origin); 
  }
}); 

```

### <a name="send-the-origin-agent-cluster-0-header-as-a-last-resort"></a>`Origin-Agent-Cluster: ?0`将标头作为最后手段发送

如果有充分的理由继续设置 `document.domain`，则可以在目标文档上发送 `Origin-Agent-Cluster: ?0` 响应标头。

```
Origin-Agent-Cluster: ?0 
```

标 `Origin-Agent-Cluster` 头指示浏览器文档是否应由源密钥代理群集处理。 若要了解详细信息 `Origin-Agent-Cluster`，请阅读 [使用 Origin-Agent-Cluster 标头请求性能隔离](https://web.dev/origin-agent-cluster/)。

发送此标头时，即使文档默认变为不可变，文档也可以继续设置 `document.domain` 。

## <a name="browser-compatibility"></a>浏览器兼容性

以下组织支持为了浏览器兼容性而弃 `document.domain` 用。

- [“源”规范](https://html.spec.whatwg.org/multipage/origin.html#:~:text=Because%20of%20these%20security%20pitfalls%2C%20this%20feature%20is%20in%20the%20process%20of%20being%20removed%20from%20the%20web%20platform)指出应删除该功能。
- [Mozilla 标准位置](https://github.com/mozilla/standards-positions/issues/601)考虑默认禁用`document.domain`值得原型制作。
- [WebKit](https://github.com/w3ctag/design-reviews/issues/564#issuecomment-768450217) 表示它们对弃用 `document.domain` setter 持中度积极态度。

## <a name="other-resources"></a>其他资源

- [Document.domain](https://developer.mozilla.org/docs/Web/API/Document/domain)
- [源隔离和弃用 `document.domain`](https://github.com/mikewest/deprecating-document-domain/)
- [弃用 `document.domain` setter](https://github.com/w3ctag/design-reviews/issues/564)

## <a name="content-license"></a>内容许可证

> [!NOTE]
> 本页面的某些部分是根据 Chromium.org 创建和共享的作品所做的修改，并根据 [Creative Commons Attribution 4.0 国际许可证](http://creativecommons.org/licenses/by/4.0/)中所述的条款进行使用。 可在[此处](https://developer.chrome.com/blog/immutable-document-domain/)找到原始页面。

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />此作品通过 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 国际许可证</a>获得许可。
