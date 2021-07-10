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
# <a name="how-to-use-microsoft-edge-command-line-options-to-configure-proxy-settings"></a><span data-ttu-id="31d11-103">如何使用 Microsoft Edge 命令行选项配置代理设置</span><span class="sxs-lookup"><span data-stu-id="31d11-103">How to use Microsoft Edge command-line options to configure proxy settings</span></span>

<span data-ttu-id="31d11-104">本文介绍了如何使用命令行选项替代默认系统网络设置。</span><span class="sxs-lookup"><span data-stu-id="31d11-104">This article describes how you can use command-line options to override the default system network settings.</span></span>

>[!NOTE]
><span data-ttu-id="31d11-105">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="31d11-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="system-network-settings"></a><span data-ttu-id="31d11-106">系统网络设置</span><span class="sxs-lookup"><span data-stu-id="31d11-106">System network settings</span></span>

<span data-ttu-id="31d11-107">默认情况下，Microsoft Edge 网络堆栈使用系统网络设置。</span><span class="sxs-lookup"><span data-stu-id="31d11-107">The Microsoft Edge network stack uses the system network settings by default.</span></span> <span data-ttu-id="31d11-108">这些设置包括*代理设置*以及*证书和私钥存储*。</span><span class="sxs-lookup"><span data-stu-id="31d11-108">These settings include *proxy settings*, and *certificate and private key stores*.</span></span>

<span data-ttu-id="31d11-109">在某些情况下，用户请求使用系统默认代理设置的替代方案。</span><span class="sxs-lookup"><span data-stu-id="31d11-109">There are scenarios where users request an alternative to using the system's default proxy settings.</span></span> <span data-ttu-id="31d11-110">为了对这些场景提供支持，Microsoft Edge 会支持可用于配置自定义代理设置的命令行选项。</span><span class="sxs-lookup"><span data-stu-id="31d11-110">To support these scenarios, Microsoft Edge supports command-line options that you can use to configure custom proxy settings.</span></span>

<span data-ttu-id="31d11-111">这些命令行选项对应于**代理服务器**组中的以下策略：</span><span class="sxs-lookup"><span data-stu-id="31d11-111">These command-line options correspond to the following policies in the **Proxy server** group:</span></span>

- [<span data-ttu-id="31d11-112">ProxyBypassList</span><span class="sxs-lookup"><span data-stu-id="31d11-112">ProxyBypassList</span></span>](./microsoft-edge-policies.md#proxybypasslist)
- [<span data-ttu-id="31d11-113">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="31d11-113">ProxyMode</span></span>](./microsoft-edge-policies.md#proxymode)
- [<span data-ttu-id="31d11-114">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="31d11-114">ProxyPacUrl</span></span>](./microsoft-edge-policies.md#proxypacurl)
- [<span data-ttu-id="31d11-115">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="31d11-115">ProxyServer</span></span>](./microsoft-edge-policies.md#proxyserver)
- [<span data-ttu-id="31d11-116">ProxySettings</span><span class="sxs-lookup"><span data-stu-id="31d11-116">ProxySettings</span></span>](./microsoft-edge-policies.md#proxysettings)

## <a name="command-line-options-for-proxy-settings"></a><span data-ttu-id="31d11-117">代理设置的命令行选项</span><span class="sxs-lookup"><span data-stu-id="31d11-117">Command-line options for proxy settings</span></span>

<span data-ttu-id="31d11-118">Microsoft Edge 支持以下与代理相关的命令行选项。</span><span class="sxs-lookup"><span data-stu-id="31d11-118">Microsoft Edge supports the following proxy-related command-line options.</span></span>

 **`--no-proxy-server`**
 
<span data-ttu-id="31d11-119">指示 Microsoft Edge 不要使用代理，即使系统另外配置为使用代理也不例外。</span><span class="sxs-lookup"><span data-stu-id="31d11-119">Tells Microsoft Edge not to use a Proxy, even if the system is otherwise configured to use one.</span></span> <span data-ttu-id="31d11-120">它会替代所提供的任何其他代理设置。</span><span class="sxs-lookup"><span data-stu-id="31d11-120">It overrides any other proxy settings that are provided.</span></span>

**`--proxy-auto-detect`**

<span data-ttu-id="31d11-121">指示 Microsoft Edge 尝试自动检测你的代理配置。</span><span class="sxs-lookup"><span data-stu-id="31d11-121">Tells Microsoft Edge to try and automatically detect your proxy configuration.</span></span> <span data-ttu-id="31d11-122">如果配置了 `--proxy-server`，则忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="31d11-122">This argument is ignored if `--proxy-server` is configured.</span></span>

**`--proxy-server=<scheme>=<uri>[:<port>][;...] | <uri>[:<port>] | "direct://"`**

<span data-ttu-id="31d11-123">指示 Microsoft Edge 使用自定义代理配置。</span><span class="sxs-lookup"><span data-stu-id="31d11-123">Tells Microsoft Edge to use a custom proxy configuration.</span></span> <span data-ttu-id="31d11-124">可以采用三种方式指定自定义代理配置。</span><span class="sxs-lookup"><span data-stu-id="31d11-124">You can specify a custom proxy configuration in three ways.</span></span>

1. <span data-ttu-id="31d11-125">提供以分号分隔的列表方案到 URL/端口对的映射。</span><span class="sxs-lookup"><span data-stu-id="31d11-125">Provide a semicolon-separated mapping of list scheme to url/port pairs.</span></span> <span data-ttu-id="31d11-126">例如，`--proxy-server="http=proxy1:8080;ftp=ftpproxy"` 会指示 Microsoft Edge 将 HTTP 代理“proxy1:8080”用于 http URL，将 HTTP 代理“ftpproxy:80”用于 ftp URL。</span><span class="sxs-lookup"><span data-stu-id="31d11-126">For example, `--proxy-server="http=proxy1:8080;ftp=ftpproxy"` tells Microsoft Edge to use HTTP proxy "proxy1:8080" for http URLs and HTTP proxy "ftpproxy:80" for ftp URLs.</span></span>
2. <span data-ttu-id="31d11-127">通过为单个 uri 提供可用于所有 URL 的可选端口。</span><span class="sxs-lookup"><span data-stu-id="31d11-127">By providing a single uri with optional port to use for all URLs.</span></span> <span data-ttu-id="31d11-128">例如，`--proxy-server="proxy2:8080"` 将对所有流量在“proxy2:8080”上使用代理。</span><span class="sxs-lookup"><span data-stu-id="31d11-128">For example, `--proxy-server="proxy2:8080"` will use the proxy at "proxy2:8080" for all traffic.</span></span>
3. <span data-ttu-id="31d11-129">通过使用特殊的“direct://”值。</span><span class="sxs-lookup"><span data-stu-id="31d11-129">By using the special "direct://" value.</span></span> <span data-ttu-id="31d11-130">例如，`--proxy-server="direct://"` 将所有连接设为不使用代理。</span><span class="sxs-lookup"><span data-stu-id="31d11-130">For example, `--proxy-server="direct://"` will make all connections not use a proxy.</span></span> 

>[!NOTE]
><span data-ttu-id="31d11-131">你可以将 Microsoft Edge 配置为尝试使用代理并在代理不可用时回退为直接前往。</span><span class="sxs-lookup"><span data-stu-id="31d11-131">You can configure Microsoft Edge to try using a proxy and fallback to going direct if the proxy isn't available.</span></span> <span data-ttu-id="31d11-132">例如，`--proxy-server="http://proxy2:8080,direct://`。</span><span class="sxs-lookup"><span data-stu-id="31d11-132">For example, `--proxy-server="http://proxy2:8080,direct://`.</span></span>

**`--proxy-bypass-list=(<trailing_domain>|<ip-address>)[:<port>][;...]`**

<span data-ttu-id="31d11-133">指示 Microsoft Edge 对以分号分隔的指定主机列表绕过任何指定代理。</span><span class="sxs-lookup"><span data-stu-id="31d11-133">Tells Microsoft Edge to bypass any specified proxy for the specified semicolon-separated list of hosts.</span></span> <span data-ttu-id="31d11-134">此标志必须与 `--proxy-server` 配合使用。</span><span class="sxs-lookup"><span data-stu-id="31d11-134">This flag must be used with `--proxy-server`.</span></span>

>[!NOTE]
><span data-ttu-id="31d11-135">尾部域匹配不需要“.”分隔符，“\*microsoft.com”将与“imicrosoft.com”匹配。</span><span class="sxs-lookup"><span data-stu-id="31d11-135">Trailing-domain matching doesn't require "." separators, "\*microsoft.com" will match "imicrosoft.com".</span></span> <span data-ttu-id="31d11-136">例如，`--proxy-server="proxy2:8080" --proxy-bypass-list="*.microsoft.com;*example.com;127.0.0.1:8080"` 将对所有主机在端口 8080 上使用代理服务器“proxy2”，但在端口 8080 上对 \*.microsoft.com、example.com 和 127.0.0.1 的请求除外。</span><span class="sxs-lookup"><span data-stu-id="31d11-136">For example, `--proxy-server="proxy2:8080" --proxy-bypass-list="*.microsoft.com;*example.com;127.0.0.1:8080"` will use the proxy server "proxy2" on port 8080 for all hosts except requests for \*.microsoft.com, example.com, and 127.0.0.1 on port 8080.</span></span> <span data-ttu-id="31d11-137">在上一个示例中，仍将代理 imicrosoft.com 请求。</span><span class="sxs-lookup"><span data-stu-id="31d11-137">In the previous example, imicrosoft.com requests will still be proxied.</span></span> <span data-ttu-id="31d11-138">但是，iexample.com 请求将绕过代理，因为指定的是 \*example.com 而不是 \*.example.com。</span><span class="sxs-lookup"><span data-stu-id="31d11-138">However, iexample.com requests will bypass the proxy because \*example.com was specified instead of \*.example.com.</span></span>

**`--proxy-pac-url=<pac-file-url>`**

<span data-ttu-id="31d11-139">指示 Microsoft Edge 使用位于指定 URL 的 PAC 文件。</span><span class="sxs-lookup"><span data-stu-id="31d11-139">Tells Microsoft Edge to use the PAC file at the specified URL.</span></span> <span data-ttu-id="31d11-140">例如，`--proxy-pac-url="https://wpad/proxy.pac"` 会指示 Microsoft Edge 使用 **proxy.pac** 文件解析 URL 请求的代理信息。</span><span class="sxs-lookup"><span data-stu-id="31d11-140">For example, `--proxy-pac-url="https://wpad/proxy.pac"` tells Microsoft Edge to resolve proxy information for URL requests using the **proxy.pac** file.</span></span>

## <a name="content-license"></a><span data-ttu-id="31d11-141">内容许可证</span><span class="sxs-lookup"><span data-stu-id="31d11-141">Content license</span></span>

> [!NOTE]
> <span data-ttu-id="31d11-142">本页面的某些部分是根据 Chromium.org 创建和共享的作品所做的修改，并根据 [Creative Commons Attribution 4.0 国际许可证](http://creativecommons.org/licenses/by/4.0/)中所述的条款进行使用。</span><span class="sxs-lookup"><span data-stu-id="31d11-142">Portions of this page are modifications based on work created and shared by Chromium.org and used according to terms described in the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).</span></span> <span data-ttu-id="31d11-143">可在[此处](https://www.chromium.org/developers/design-documents/network-settings#TOC-Command-line-options-for-proxy-sett)找到原始页面。</span><span class="sxs-lookup"><span data-stu-id="31d11-143">The original page can be found [here](https://www.chromium.org/developers/design-documents/network-settings#TOC-Command-line-options-for-proxy-sett).</span></span>
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /><span data-ttu-id="31d11-144">此作品通过 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 国际许可证</a>获得许可。</span><span class="sxs-lookup"><span data-stu-id="31d11-144">This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.</span></span>

## <a name="see-also"></a><span data-ttu-id="31d11-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31d11-145">See also</span></span>

- <span data-ttu-id="31d11-146">若要查看高级配置设置和其他选项，请参阅 Chromium 开源项目中的[代理文档](https://chromium.googlesource.com/chromium/src/+/HEAD/net/docs/proxy.md)。</span><span class="sxs-lookup"><span data-stu-id="31d11-146">To see advanced configuration settings and additional options, consult the [proxy documentation](https://chromium.googlesource.com/chromium/src/+/HEAD/net/docs/proxy.md) in the Chromium Open Source project.</span></span>
- [<span data-ttu-id="31d11-147">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="31d11-147">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)