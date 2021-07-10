---
title: Microsoft Edge 代理设置
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: '使用命令行选项配置代理设置 '
ms.openlocfilehash: 99a5f0776ea42f1e26050e0d30adb48a63907b8c
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642158"
---
# <a name="how-to-use-microsoft-edge-command-line-options-to-configure-proxy-settings"></a>如何使用 Microsoft Edge 命令行选项配置代理设置

本文介绍了如何使用命令行选项替代默认系统网络设置。

>[!NOTE]
>本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="system-network-settings"></a>系统网络设置

默认情况下，Microsoft Edge 网络堆栈使用系统网络设置。 这些设置包括*代理设置*以及*证书和私钥存储*。

在某些情况下，用户请求使用系统默认代理设置的替代方案。 为了对这些场景提供支持，Microsoft Edge 会支持可用于配置自定义代理设置的命令行选项。

这些命令行选项对应于**代理服务器**组中的以下策略：

- [ProxyBypassList](./microsoft-edge-policies.md#proxybypasslist)
- [ProxyMode](./microsoft-edge-policies.md#proxymode)
- [ProxyPacUrl](./microsoft-edge-policies.md#proxypacurl)
- [ProxyServer](./microsoft-edge-policies.md#proxyserver)
- [ProxySettings](./microsoft-edge-policies.md#proxysettings)

## <a name="command-line-options-for-proxy-settings"></a>代理设置的命令行选项

Microsoft Edge 支持以下与代理相关的命令行选项。

 **`--no-proxy-server`**
 
指示 Microsoft Edge 不要使用代理，即使系统另外配置为使用代理也不例外。 它会替代所提供的任何其他代理设置。

**`--proxy-auto-detect`**

指示 Microsoft Edge 尝试自动检测你的代理配置。 如果配置了 `--proxy-server`，则忽略此参数。

**`--proxy-server=<scheme>=<uri>[:<port>][;...] | <uri>[:<port>] | "direct://"`**

指示 Microsoft Edge 使用自定义代理配置。 可以采用三种方式指定自定义代理配置。

1. 提供以分号分隔的列表方案到 URL/端口对的映射。 例如，`--proxy-server="http=proxy1:8080;ftp=ftpproxy"` 会指示 Microsoft Edge 将 HTTP 代理“proxy1:8080”用于 http URL，将 HTTP 代理“ftpproxy:80”用于 ftp URL。
2. 通过为单个 uri 提供可用于所有 URL 的可选端口。 例如，`--proxy-server="proxy2:8080"` 将对所有流量在“proxy2:8080”上使用代理。
3. 通过使用特殊的“direct://”值。 例如，`--proxy-server="direct://"` 将所有连接设为不使用代理。 

>[!NOTE]
>你可以将 Microsoft Edge 配置为尝试使用代理并在代理不可用时回退为直接前往。 例如，`--proxy-server="http://proxy2:8080,direct://`。

**`--proxy-bypass-list=(<trailing_domain>|<ip-address>)[:<port>][;...]`**

指示 Microsoft Edge 对以分号分隔的指定主机列表绕过任何指定代理。 此标志必须与 `--proxy-server` 配合使用。

>[!NOTE]
>尾部域匹配不需要“.”分隔符，“\*microsoft.com”将与“imicrosoft.com”匹配。 例如，`--proxy-server="proxy2:8080" --proxy-bypass-list="*.microsoft.com;*example.com;127.0.0.1:8080"` 将对所有主机在端口 8080 上使用代理服务器“proxy2”，但在端口 8080 上对 \*.microsoft.com、example.com 和 127.0.0.1 的请求除外。 在上一个示例中，仍将代理 imicrosoft.com 请求。 但是，iexample.com 请求将绕过代理，因为指定的是 \*example.com 而不是 \*.example.com。

**`--proxy-pac-url=<pac-file-url>`**

指示 Microsoft Edge 使用位于指定 URL 的 PAC 文件。 例如，`--proxy-pac-url="https://wpad/proxy.pac"` 会指示 Microsoft Edge 使用 **proxy.pac** 文件解析 URL 请求的代理信息。

## <a name="content-license"></a>内容许可证

> [!NOTE]
> 本页面的某些部分是根据 Chromium.org 创建和共享的作品所做的修改，并根据 [Creative Commons Attribution 4.0 国际许可证](http://creativecommons.org/licenses/by/4.0/)中所述的条款进行使用。 可在[此处](https://www.chromium.org/developers/design-documents/network-settings#TOC-Command-line-options-for-proxy-sett)找到原始页面。
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />此作品通过 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 国际许可证</a>获得许可。

## <a name="see-also"></a>另请参阅

- 若要查看高级配置设置和其他选项，请参阅 Chromium 开源项目中的[代理文档](https://chromium.googlesource.com/chromium/src/+/HEAD/net/docs/proxy.md)。
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)