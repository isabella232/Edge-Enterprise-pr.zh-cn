---
title: Microsoft Edge 和混合内容下载
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 04/30/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 和混合内容下载
ms.openlocfilehash: a81c44754865b2303320bfe87346c7f7533e6133
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617302"
---
# <a name="learn-about-microsoft-edge-and-mixed-content-downloads"></a>了解 Microsoft Edge 和混合内容下载

本文介绍混合内容下载以及 Microsoft Edge 对此操作的处理方式。

>[!NOTE]
>本文适用于 Microsoft Edge 版本 85 或更高版本。

## <a name="what-are-mixed-content-downloads"></a>混合内容下载是什么？

从通过安全 HTTPS 连接加载的 HTML 页面启动下载时会发生混合内容下载，但存在以下情况之一：

- 一个或多个下载位置重定向是通过不安全的 HTTP 连接加载的。
- 最终下载位置是通过不安全的 HTTP 连接加载的。

这两种场景都是混合内容，因为请求是通过安全 HTTPS 发出的，并且最终下载目标同时涉及到 HTTP 和 HTTPS 内容。 新式浏览器将显示有关此类型内容的警告，向用户表明，即使访问的原始页面是安全的，下载内容也可能是不安全的。

## <a name="download-warnings-and-user-options"></a>下载警告和用户选项

下载警告确保用户知道正在下载的文件可能会被网络上的恶意攻击者读取。 此警告让用户能够在知情的情况下决定是否下载文件。

在 Microsoft Edge 中，混合内容下载将被阻止，但用户可以覆盖并下载文件（如果需要）。 Microsoft Edge 计划开始阻止混合内容可执行文件下载（从 Microsoft Edge 版本 85 开始），并将在未来版本中阻止不同的文件类型。

> [!NOTE]
> 此功能部署可能会根据发布计划和用户反馈进行更改。

<!-- The schedule of the block for different filetypes is to be determined and may be impacted by usage data and user feedback. -->

在下载栏中，阻止警告消息类似于下一屏幕截图中的示例。

 ![下载任务栏中的混合内容警告](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-tray-warning.png)

在下载页上，阻止警告类似于以下屏幕截图示例：

 ![混合内容覆盖提示](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-page-warning.png)

如果用户决定保留下载，系统会提示他们确认操作。 下一个屏幕截图将显示此确认提示示例。

 ![选择 Internet Explorer 模式](./media/edge-learnmore-mixed-content-downloads/edge-mixed-content-download-override.png)

## <a name="supporting-policies"></a>支持策略

希望从特定网站排除混合内容阻止的企业可使用 [InsecureContentAllowedForUrls](./microsoft-edge-policies.md#insecurecontentallowedforurls) 策略执行此操作。

## <a name="content-license"></a>内容许可证

> [!NOTE]
> 本页面的某些部分是根据 Chromium.org 创建和共享的作品所做的修改，并根据 [Creative Commons Attribution 4.0 国际许可证](http://creativecommons.org/licenses/by/4.0/)中所述的条款进行使用。 可在[此处](https://developers.google.com/web/fundamentals/security/prevent-mixed-content/what-is-mixed-content)找到原始页面。
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />此作品通过 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 国际许可证</a>获得许可。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)