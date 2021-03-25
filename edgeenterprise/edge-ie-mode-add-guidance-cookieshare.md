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
ms.openlocfilehash: d94c1337b7a3dbee789efb16e9c8b0a5ebc2c23b
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447736"
---
# <a name="cookie-sharing-from-microsoft-edge-to-internet-explorer"></a><span data-ttu-id="20190-103">从 Microsoft Edge 到 Internet Explorer 的 Cookie 共享</span><span class="sxs-lookup"><span data-stu-id="20190-103">Cookie sharing from Microsoft Edge to Internet Explorer</span></span>

<span data-ttu-id="20190-104">本文介绍了如何在使用 Internet Explorer 模式时，配置从 Microsoft Edge 进程到 Internet Explorer 进程的会话 cookie 共享。</span><span class="sxs-lookup"><span data-stu-id="20190-104">This article explains explains how to configure session cookie sharing from a Microsoft Edge process to Internet Explorer process, while using Internet Explorer mode.</span></span>

> [!NOTE]
> <span data-ttu-id="20190-105">本文适用于 Microsoft Edge 版本 87 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="20190-105">This article applies to Microsoft Edge version 87 or later.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="20190-106">必备条件</span><span class="sxs-lookup"><span data-stu-id="20190-106">Prerequisites</span></span>

- <span data-ttu-id="20190-107">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="20190-107">Windows updates</span></span>

  - <span data-ttu-id="20190-108">Windows 10 版本 2004、Windows Server 版本 2004 - KB4571744 或更高版本</span><span class="sxs-lookup"><span data-stu-id="20190-108">Windows 10 version 2004, Windows Server version 2004 - KB4571744 or higher</span></span>
  - <span data-ttu-id="20190-109">Windows 10 版本 1909、Windows Server 版本 1909 – KB4566116 或更高版本</span><span class="sxs-lookup"><span data-stu-id="20190-109">Windows 10 version 1909, Windows Server version 1909 – KB4566116 or higher</span></span>
  - <span data-ttu-id="20190-110">Windows 10 版本 1903、Windows Server 版本 1903 – KB4566116 或更高版本</span><span class="sxs-lookup"><span data-stu-id="20190-110">Windows 10 version 1903, Windows Server version 1903 – KB4566116 or higher</span></span>
  - <span data-ttu-id="20190-111">Windows10 版本 1809、Windows Server 版本 1809 和 Windows Server 2019 - KB4571748 或更高版本</span><span class="sxs-lookup"><span data-stu-id="20190-111">Windows 10 version 1809, Windows Server version 1809, and Windows Server 2019 - KB4571748 or higher</span></span>
  - <span data-ttu-id="20190-112">Windows 10 版本 1803 – KB4577032 或更高版本</span><span class="sxs-lookup"><span data-stu-id="20190-112">Windows 10 version 1803 – KB4577032 or higher</span></span>

- <span data-ttu-id="20190-113">Microsoft Edge 版本 87 或更高版本</span><span class="sxs-lookup"><span data-stu-id="20190-113">Microsoft Edge version 87 or later</span></span>
- <span data-ttu-id="20190-114">[IE 模式](./edge-ie-mode.md) 配置了企业模式网站列表</span><span class="sxs-lookup"><span data-stu-id="20190-114">[IE mode](./edge-ie-mode.md) configured with Enterprise Mode Site List</span></span>

## <a name="overview"></a><span data-ttu-id="20190-115">概述</span><span class="sxs-lookup"><span data-stu-id="20190-115">Overview</span></span>

<span data-ttu-id="20190-116">大型组织中的常见配置是，将一个在新式浏览器工作的应用程序链接到另一个应用程序上，可能将该应用程序配置为在启用单一登录（SSO）的 Internet Explorer 模式下打开作为工作流的一部分。</span><span class="sxs-lookup"><span data-stu-id="20190-116">A common configuration in large organizations is to have an application that works on a modern browser link to another application, which might be configured to open in Internet Explorer mode with Single Sign On (SSO) enabled as part of the workflow.</span></span>

<span data-ttu-id="20190-117">默认情况下，Microsoft Edge 和 Internet Explorer 进程不共享会话 cookie，在某些情况下，这可能不方便。</span><span class="sxs-lookup"><span data-stu-id="20190-117">By default, the Microsoft Edge and Internet Explorer processes don't share session cookies, and this can be inconvenient in some cases.</span></span> <span data-ttu-id="20190-118">例如，用户必须在 Internet Explorer 模式下重新进行身份验证，或注销 Microsoft Edge 会话时，不会注销 Internet Explorer 模式会话。</span><span class="sxs-lookup"><span data-stu-id="20190-118">For example, when a user has to re-authenticate in Internet Explorer mode or when signing out of an Microsoft Edge session doesn’t sign out of the Internet Explorer mode session.</span></span> <span data-ttu-id="20190-119">在这些方案中，可将由 SSO 设置的特定 cookie 配置为从 Microsoft Edge 发送到 Internet Explorer，以便使验证体验更顺畅，方法是避免重新对其进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="20190-119">In these scenarios, you can configure specific cookies set by SSO to be sent from Microsoft Edge to Internet Explorer so the authentication experience becomes more seamless by eliminating the need to re-authenticate.</span></span>

> [!NOTE]
> <span data-ttu-id="20190-120">只能将会话 cookie 从 Microsoft Edge 共享到 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="20190-120">Session cookies can only be shared from Microsoft Edge to Internet Explorer.</span></span> <span data-ttu-id="20190-121">无法反向共享会话 cookie（从 Internet Explorer 到 Microsoft Edge）。</span><span class="sxs-lookup"><span data-stu-id="20190-121">Sharing session cookies in reverse (from Internet Explorer to Microsoft Edge) isn't possible.</span></span>

## <a name="how-cookie-sharing-works"></a><span data-ttu-id="20190-122">Cookie 共享的工作原理</span><span class="sxs-lookup"><span data-stu-id="20190-122">How cookie sharing works</span></span>

<span data-ttu-id="20190-123">已对企业模式网站列表 XML 进行了扩展，允许其他元素指定需要从 Microsoft Edge 会话共享到 Internet Explorer 的 cookie。</span><span class="sxs-lookup"><span data-stu-id="20190-123">The Enterprise Mode site list XML has been extended to allow additional elements to specify cookies that need to be shared from a Microsoft Edge session with Internet Explorer.</span></span>  

<span data-ttu-id="20190-124">第一次在 Microsoft Edge 会话中创建 Internet Explorer 模式选项卡时，所有匹配的 cookie 都会共享到 Internet Explorer 会话。</span><span class="sxs-lookup"><span data-stu-id="20190-124">The first time an Internet Explorer mode tab is created in a Microsoft Edge session, all matching cookies are shared to the Internet Explorer session.</span></span> <span data-ttu-id="20190-125">随后，任何时候添加、删除或修改与规则相匹配的 cookie，都将作为 Internet Explorer 会话的更新发送。</span><span class="sxs-lookup"><span data-stu-id="20190-125">Subsequently, any time a cookie that matches a rule is added, deleted, or modified it is sent as an update to the Internet Explorer session.</span></span> <span data-ttu-id="20190-126">更新网站列表时，也会重新评估共享 cookie 的集合。</span><span class="sxs-lookup"><span data-stu-id="20190-126">The set of shared cookies is also re-evaluated when the site list is updated.</span></span>

### <a name="updated-schema-elements"></a><span data-ttu-id="20190-127">已更新的架构元素</span><span class="sxs-lookup"><span data-stu-id="20190-127">Updated schema elements</span></span>

<span data-ttu-id="20190-128">下表介绍了为支持 cookie 共享功能而添加的 \<shared-cookie\> 元素。</span><span class="sxs-lookup"><span data-stu-id="20190-128">The following table describes the \<shared-cookie\> element added to support the cookie sharing feature.</span></span>

| <span data-ttu-id="20190-129">元素</span><span class="sxs-lookup"><span data-stu-id="20190-129">Element</span></span>| <span data-ttu-id="20190-130">描述</span><span class="sxs-lookup"><span data-stu-id="20190-130">Description</span></span> |
|-|-|
| \<shared-cookie **domain**=".contoso.com" **name**="cookie1"\>\</shared-cookie\><br><br><span data-ttu-id="20190-131">或者</span><span class="sxs-lookup"><span data-stu-id="20190-131">OR</span></span><br><br>\<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2"\>\</shared-cookie\>   |<span data-ttu-id="20190-132">**（必需）**\<shared-cookie\> 元素至少需要 *域*（对于域 cookie）或 *主机*（对于仅限主机 cookie）属性和 *名称* 属性。</span><span class="sxs-lookup"><span data-stu-id="20190-132">**(Required)** A \<shared-cookie\> element requires, at minimum, a *domain* (for domain cookies) or a *host* (for host-only cookies) attribute and a *name* attribute.</span></span><br><span data-ttu-id="20190-133">这些必须分别与 cookie 的域和名称完全匹配。</span><span class="sxs-lookup"><span data-stu-id="20190-133">These must be exact matches to the cookie's domain and name respectively.</span></span> <span data-ttu-id="20190-134">**请注意，** 子域不匹配。</span><span class="sxs-lookup"><span data-stu-id="20190-134">**Note** that subdomains do not match.</span></span><br><br><span data-ttu-id="20190-135">*域*属性用于域 cookie（允许使用前导圆点，但可选择）。</span><span class="sxs-lookup"><span data-stu-id="20190-135">The *domain* attribute is used for domain cookies (and a leading dot is allowed but optional).</span></span><br><span data-ttu-id="20190-136">*主机*属性用于仅限主机的 cookie（前导圆点错误）。</span><span class="sxs-lookup"><span data-stu-id="20190-136">The *host* attribute is used for host-only cookies (and a leading dot is an error).</span></span> <span data-ttu-id="20190-137">指定“两者”或者“两者都不”均会导致错误。</span><span class="sxs-lookup"><span data-stu-id="20190-137">Specifying neither or both will result in an error.</span></span><br><span data-ttu-id="20190-138">\* 如果在 cookie 字符串中指定域（通过 HTTP Set-Cookie 响应头或 document.cookie JS API），则 cookie 是域 cookie。</span><span class="sxs-lookup"><span data-stu-id="20190-138">\* A cookie is a domain cookie if a domain was specified in the cookie string (via HTTP Set-Cookie response header or document.cookie JS API).</span></span> <span data-ttu-id="20190-139">域 cookie 适用于指定域和所有子域。</span><span class="sxs-lookup"><span data-stu-id="20190-139">A domain cookie applies to the specified domain and all subdomains.</span></span> <span data-ttu-id="20190-140">如果未在 cookie 字符串中指定域，则 cookie 是仅限主机的 cookie，并且仅适用于其设置的特定主机。</span><span class="sxs-lookup"><span data-stu-id="20190-140">If a domain was not specified in the cookie string, the cookie is a host-only cookie and only applies to the specific host that it was set for.</span></span> <span data-ttu-id="20190-141">请注意，诸如单字主机名（例如 http://intranetsite)）和 IP 地址（例如 http://10.0.0.1)）的一些 URL 类只能设置仅限主机的 cookie。</span><span class="sxs-lookup"><span data-stu-id="20190-141">Note that some classes of URLs such as single-word hostnames (e.g. http://intranetsite) and IP addresses (e.g. http://10.0.0.1) can only set host-only cookies.</span></span>    |
| \<shared-cookie **host**="subdomain.contoso.com" **name**="cookie2" **path**="/a/b/c"\>\</shared-cookie\>  | <span data-ttu-id="20190-142">**（可选）** 可指定*路径*属性。</span><span class="sxs-lookup"><span data-stu-id="20190-142">**(Optional)** A *path* attribute may be specified.</span></span> <span data-ttu-id="20190-143">如果未指定路径属性（或者路径属性为空），则无论路径（通配符规则）如何，任何与域/主机和名称匹配的 Cookie 都会与策略匹配。</span><span class="sxs-lookup"><span data-stu-id="20190-143">If no path attribute is specified (or if the path attribute is empty), any cookies matching domain/host and name match the policy, regardless of path (wildcard rule).</span></span><br><br><span data-ttu-id="20190-144">如果指定了路径，则它必须完全匹配。</span><span class="sxs-lookup"><span data-stu-id="20190-144">If a path is specified, it must be an exact match.</span></span><br><span data-ttu-id="20190-145">如果 cookie 与带有路径的规则匹配，则优先级高于不带路径的规则。</span><span class="sxs-lookup"><span data-stu-id="20190-145">If a cookie matches a rule with a path, that takes precedence over a rule without a path.</span></span> |

#### <a name="sharing-example"></a><span data-ttu-id="20190-146">共享示例</span><span class="sxs-lookup"><span data-stu-id="20190-146">Sharing example</span></span>

```xml
<site-list version="1">
<shared-cookie domain=".contoso.com" name="cookie1"></shared-cookie> 
<shared-cookie host="subdomain.contoso.com" name="cookie2" path="/a/b/c">
</shared-cookie>
</site-list>
```

## <a name="see-also"></a><span data-ttu-id="20190-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20190-147">See also</span></span>

- [<span data-ttu-id="20190-148">关于 IE 模式</span><span class="sxs-lookup"><span data-stu-id="20190-148">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="20190-149">可配置的网站信息</span><span class="sxs-lookup"><span data-stu-id="20190-149">Configurable sites information</span></span>](./edge-learnmore-configurable-sites-ie-mode.md)
- [<span data-ttu-id="20190-150">其他企业模式信息</span><span class="sxs-lookup"><span data-stu-id="20190-150">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [<span data-ttu-id="20190-151">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="20190-151">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)