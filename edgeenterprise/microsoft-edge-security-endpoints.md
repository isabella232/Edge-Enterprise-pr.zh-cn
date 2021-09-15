---
title: Microsoft Edge 终结点的允许列表
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 终结点的允许列表
ms.openlocfilehash: 735e18e63095405dad4fdd51d51654956b564ca7
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "11979035"
---
# <a name="allow-list-for-microsoft-edge-endpoints"></a>Microsoft Edge 终结点的允许列表

Microsoft Edge 需要连接到 Internet 以支持其功能。 本文标识了需要添加到允许列表以确保通过防火墙和其他安全机制进行通信的域 URL。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="domain-urls-to-allow"></a>要允许的域 URL

对于 Microsoft Edge，允许以下域 URL。

### <a name="update-service"></a>更新服务

Microsoft Edge 用于检查新的更新内容的服务。

- `https://msedge.api.cdp.microsoft.com`

### <a name="experimentation-and-configuration-service"></a>实验和配置服务

- `https://config.edge.skype.com`

### <a name="download-locations-for-microsoft-edge"></a>Microsoft Edge 的下载位置

可在初始安装期间或有更新可用时从中下载 Microsoft Edge 的位置。 下载位置由更新服务确定。

#### <a name="http"></a>HTTP

- `http://msedge.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.f.dl.delivery.mp.microsoft.com`
- `http://msedge.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.b.dl.delivery.mp.microsoft.com`

#### <a name="https"></a>HTTPS

- `https://msedge.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sf.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > 要简化下载位置的允许列表，可以使用通配符： `*.dl.delivery.mp.microsoft.com`

### <a name="download-locations-for-microsoft-edge-extensions"></a>Microsoft Edge 扩展的下载位置

可在初始安装期间或有更新可用时从中下载 Microsoft Edge 扩展的位置。 下载位置由更新服务确定。

#### <a name="http"></a>HTTP

- `http://msedgeextensions.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.f.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.dl.delivery.mp.microsoft.com`

#### <a name="https"></a>HTTPS

- `https://msedgeextensions.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sf.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > 要简化下载位置的允许列表，可以使用通配符： `*.dl.delivery.mp.microsoft.com`

### <a name="optionally-for-download-delivery-optimization"></a>对于下载传递优化为可选

有关传递优化的详细信息，请参阅 [适用于 Windows 10 更新的传递优化](/windows/deployment/update/waas-delivery-optimization)。

- 客户端到服务的通信：`*.do.dsp.mp.microsoft.com`（HTTP 端口 80、HTTPS 端口 443）
- 客户端到客户端通信：应对入站流量打开 TCP 端口 7680

### <a name="sync"></a>Sync

这些终结点可管理同步数据的读取和写入、安全数据的权限管理，以及在有新同步数据时的浏览器通知。

- Microsoft Edge 同步服务终结点：

  - `https://edge-enterprise.activity.windows.com`
  - `https://edge.activity.windows.com`

- Azure 信息保护终结点：

  - `https://api.aadrm.com` （针对大多数租户）
  - `https://api.aadrm.de` （针对德国租户）
  - `https://api.aadrm.cn` （针对中国租户）

- [Windows 通知服务终结点](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)

## <a name="other-browser-support-services"></a>其他浏览器支持服务

提供浏览器功能的元数据，如跟踪保护、证书吊销列表和其他浏览器组件更新。 提供可下载的拼写检查字典和广告屏蔽阻止名单。 提供服务以支持诸如集合、自动填充和扩展存储等浏览器功能。

- `http://edge.microsoft.com/`
- `https://edge.microsoft.com/`

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 文档登录页面](./index.yml)
- [管理 Windows 10 企业版版本 1903 的连接终结点](/windows/privacy/manage-windows-1903-endpoints)