---
title: 适用于 Microsoft Edge URL 策略的筛选器格式
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 05/01/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解用于 Microsoft Edge URLBlocklist 和 URLAllowlist 策略的筛选器格式。
ms.openlocfilehash: 5a0eff1ca7be17fccd1087716d426b13ea302847
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979295"
---
# <span data-ttu-id="0be59-103">基于 URL 列表的策略的筛选器格式</span><span class="sxs-lookup"><span data-stu-id="0be59-103">Filter format for URL list-based policies</span></span>

<span data-ttu-id="0be59-104">本文介绍了用于 Microsoft Edge 基于 URL 列表的策略（[例如 URLBlocklist](microsoft-edge-policies.md#urlblocklist)、[URLAllowList](microsoft-edge-policies.md#urlallowlist) 和 [CertificateTransparencyEnforcementDisabledForUrls](microsoft-edge-policies.md#certificatetransparencyenforcementdisabledforurls) 策略）的筛选器格式。</span><span class="sxs-lookup"><span data-stu-id="0be59-104">This article describes the filter format used for the Microsoft Edge URL list-based policies (For example, [URLBlocklist](microsoft-edge-policies.md#urlblocklist), [URLAllowList](microsoft-edge-policies.md#urlallowlist), and [CertificateTransparencyEnforcementDisabledForUrls](microsoft-edge-policies.md#certificatetransparencyenforcementdisabledforurls) policies.</span></span>

> [!NOTE]
> <span data-ttu-id="0be59-105">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="0be59-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="0be59-106">筛选器格式</span><span class="sxs-lookup"><span data-stu-id="0be59-106">The filter format</span></span>

<span data-ttu-id="0be59-107">筛选器格式为：</span><span class="sxs-lookup"><span data-stu-id="0be59-107">The filter format is:</span></span>

```
    [scheme://][.]host[:port][/path][@query]
```

<span data-ttu-id="0be59-108">筛选器格式中的字段为：</span><span class="sxs-lookup"><span data-stu-id="0be59-108">The fields in the filter format are:</span></span>

| <span data-ttu-id="0be59-109">字段</span><span class="sxs-lookup"><span data-stu-id="0be59-109">Field</span></span> | <span data-ttu-id="0be59-110">说明</span><span class="sxs-lookup"><span data-stu-id="0be59-110">Description</span></span> |
| --- | --- |
| <span data-ttu-id="0be59-111">**方案**（*可选*）</span><span class="sxs-lookup"><span data-stu-id="0be59-111">**scheme** (*optional*)</span></span> | <span data-ttu-id="0be59-112">它可以是 http://、https://、ftp://、edge:// 等。</span><span class="sxs-lookup"><span data-stu-id="0be59-112">It can be http://, https://, ftp://, edge://, etc.</span></span> |
| <span data-ttu-id="0be59-113">**主机**（*必需*）</span><span class="sxs-lookup"><span data-stu-id="0be59-113">**host** (*required*)</span></span> | <span data-ttu-id="0be59-114">它必须是有效的主机名或 IP 地址，并且你可以使用通配符（“\*”）。</span><span class="sxs-lookup"><span data-stu-id="0be59-114">It must be a valid host name or IP address and you can use a wildcard ("\*").</span></span> <span data-ttu-id="0be59-115">若要禁用子域匹配，请在**主机**前添加可选的点（“.”）。</span><span class="sxs-lookup"><span data-stu-id="0be59-115">To disable subdomain matching, include an optional dot (".") before **host**.</span></span> |
| <span data-ttu-id="0be59-116">**端口**（*可选*）</span><span class="sxs-lookup"><span data-stu-id="0be59-116">**port** (*optional*)</span></span> | <span data-ttu-id="0be59-117">有效值范围为 1 到 65535。</span><span class="sxs-lookup"><span data-stu-id="0be59-117">Valid values range from 1 to 65535.</span></span> |
| <span data-ttu-id="0be59-118">**路径**（*可选*）</span><span class="sxs-lookup"><span data-stu-id="0be59-118">**path** (*optional*)</span></span> | <span data-ttu-id="0be59-119">你可以在路径中使用任何字符串。</span><span class="sxs-lookup"><span data-stu-id="0be59-119">You can use any string in the path.</span></span> |
| <span data-ttu-id="0be59-120">**查询**（*可选*）</span><span class="sxs-lookup"><span data-stu-id="0be59-120">**query** (*optional*)</span></span> | <span data-ttu-id="0be59-121">**查询**是用 & 号分隔的键值或纯键令牌。</span><span class="sxs-lookup"><span data-stu-id="0be59-121">The **query** is either key-value or key-only tokens separated by an ampersand ("&").</span></span> <span data-ttu-id="0be59-122">使用等号（“=”）分隔键值令牌。</span><span class="sxs-lookup"><span data-stu-id="0be59-122">Separate key-value tokens with an equal sign ("=").</span></span> <span data-ttu-id="0be59-123">若要指明前缀匹配，可以在**查询**结尾处使用星号（“\*”）。</span><span class="sxs-lookup"><span data-stu-id="0be59-123">To indicate a prefix match, you can use an asterisk ("\*") at the end of the **query**.</span></span> |

## <span data-ttu-id="0be59-124">将筛选器格式与 URL 格式进行比较</span><span class="sxs-lookup"><span data-stu-id="0be59-124">Comparing the filter format to the URL format</span></span>

<span data-ttu-id="0be59-125">筛选器格式类似于 URL 格式，但有以下几点不同：</span><span class="sxs-lookup"><span data-stu-id="0be59-125">The filter format resembles the URL format, except for the following differences:</span></span>

- <span data-ttu-id="0be59-126">如果你添加“user:pass”，它会被忽略。</span><span class="sxs-lookup"><span data-stu-id="0be59-126">If you include "user:pass", it will be ignored.</span></span> <span data-ttu-id="0be59-127">例如，http://user:pass@ftp.contoso.com/pub/example.iso。</span><span class="sxs-lookup"><span data-stu-id="0be59-127">For example, http://user:pass@ftp.contoso.com/pub/example.iso.</span></span>
- <span data-ttu-id="0be59-128">如果你添加片段标识符（“#”），此标识符及其后面跟的所有内容都会被忽略。</span><span class="sxs-lookup"><span data-stu-id="0be59-128">If you include a fragment identifier ("#"), it and everything that follows the identifier is ignored.</span></span>
- <span data-ttu-id="0be59-129">你可以将通配符（“\*”）用作**主机**，并能在它前面添加点（“.”）。</span><span class="sxs-lookup"><span data-stu-id="0be59-129">You can use a wildcard ("\*") as the **host** and you can prefix it with a dot (".").</span></span>
- <span data-ttu-id="0be59-130">你可以使用左斜线（“/”）或点（“.”）作为**主机**的后缀。</span><span class="sxs-lookup"><span data-stu-id="0be59-130">You can use a forward slash ("/") or a dot (".") as a suffix for the **host**.</span></span> <span data-ttu-id="0be59-131">在这种情况下，后缀会被忽略。</span><span class="sxs-lookup"><span data-stu-id="0be59-131">In this case, the suffix is ignored.</span></span>

## <span data-ttu-id="0be59-132">筛选器选择条件</span><span class="sxs-lookup"><span data-stu-id="0be59-132">Filter selection criteria</span></span>

<span data-ttu-id="0be59-133">为 URL 选择的筛选器是处理以下筛选器选择规则后找到的最具体的匹配项：</span><span class="sxs-lookup"><span data-stu-id="0be59-133">The filter selected for a URL is the most specific match found after processing the following filter selection rules:</span></span>

1. <span data-ttu-id="0be59-134">首先选择具有最长**主机**匹配项的筛选器。</span><span class="sxs-lookup"><span data-stu-id="0be59-134">Filters with the longest **host** match are selected first.</span></span>
2. <span data-ttu-id="0be59-135">在所选筛选器中，任何包含不匹配方案或端口的筛选器都会被放弃。</span><span class="sxs-lookup"><span data-stu-id="0be59-135">From the selected filters, any filter with a non-matching scheme or port is discarded.</span></span>
3. <span data-ttu-id="0be59-136">从其余筛选器中，选择具有最长匹配**路径**的筛选器。</span><span class="sxs-lookup"><span data-stu-id="0be59-136">From the remaining filters, the filter with the longest matching **path** is selected.</span></span>
4. <span data-ttu-id="0be59-137">在剩下的筛选器中，选择的是具有最长查询令牌集的筛选器。</span><span class="sxs-lookup"><span data-stu-id="0be59-137">From the remaining filters, the filter with the longest set of query tokens is selected.</span></span> <span data-ttu-id="0be59-138">在这一步，如果允许列表筛选器和阻止列表筛选器的**路径**长度和**查询**令牌数都相同，则允许列表筛选器优先于阻止列表筛选器。</span><span class="sxs-lookup"><span data-stu-id="0be59-138">At this step, the allow list filter takes precedence over the block list filter if both filters have the same **path** length and number of **query** tokens.</span></span>
5. <span data-ttu-id="0be59-139">如果剩余筛选器无效，则从**主机**中删除最左侧的子域，并从第 1 步重新开始执行选择过程。</span><span class="sxs-lookup"><span data-stu-id="0be59-139">If there's no valid filter remaining, then the left-most subdomain is removed from **host** and the selection process starts over at step 1.</span></span> <span data-ttu-id="0be59-140">特殊星号（“\*”）**主机**是最后搜索的，它匹配所有主机。</span><span class="sxs-lookup"><span data-stu-id="0be59-140">The special asterisk ("\*") **host** is the last searched and it matches all hosts.</span></span>
6. <span data-ttu-id="0be59-141">如果筛选器可用，它会阻止或允许 URL 请求。</span><span class="sxs-lookup"><span data-stu-id="0be59-141">If a filter's available, it blocks or allows the URL request.</span></span>

   >[!NOTE]
   ><span data-ttu-id="0be59-142">如果没有匹配的筛选器，则默认行为是允许 URL 请求。</span><span class="sxs-lookup"><span data-stu-id="0be59-142">The default behavior is to allow the URL request if no filter is matched.</span></span>

## <span data-ttu-id="0be59-143">筛选器选择条件示例</span><span class="sxs-lookup"><span data-stu-id="0be59-143">Example filter selection criteria</span></span>

<span data-ttu-id="0be59-144">在此示例中，搜索“https://sub.contoso.com/docs”的匹配项时，筛选器选择会：</span><span class="sxs-lookup"><span data-stu-id="0be59-144">In this example, when searching for a match to "https://sub.contoso.com/docs" the filter selection will:</span></span>

1. <span data-ttu-id="0be59-145">搜索“sub.contoso.com”的筛选器。</span><span class="sxs-lookup"><span data-stu-id="0be59-145">Search for a filter for "sub.contoso.com".</span></span> <span data-ttu-id="0be59-146">如果找到筛选器，搜索将转到第 2 步。</span><span class="sxs-lookup"><span data-stu-id="0be59-146">If it finds a filter, the search moves to step 2.</span></span> <span data-ttu-id="0be59-147">如果找不到筛选器，它会使用“contoso.com”和“com”重试，最后用 "" 重试。</span><span class="sxs-lookup"><span data-stu-id="0be59-147">If a filter isn't found, then it tries again with "contoso.com", "com", and finally "".</span></span>
2. <span data-ttu-id="0be59-148">在所选筛选器中，任何在**方案**中没有“http”的项都会被删除。</span><span class="sxs-lookup"><span data-stu-id="0be59-148">From the selected filters, any that don't have "http" in the **scheme** are removed.</span></span>
3. <span data-ttu-id="0be59-149">在剩下的筛选器中，任何具有非“80”的确切端口号的筛选器都会被删除。</span><span class="sxs-lookup"><span data-stu-id="0be59-149">From the remaining filters, any that have an exact port number that isn't "80" are removed.</span></span>
4. <span data-ttu-id="0be59-150">从其余筛选器中，删除**路径**前缀不是“/docs”的任何项。</span><span class="sxs-lookup"><span data-stu-id="0be59-150">From the remaining filters, any that don't have "/docs" as a prefix of the **path** are removed.</span></span>
5. <span data-ttu-id="0be59-151">从其余筛选器中，选择并应用路径前缀最长的筛选器。</span><span class="sxs-lookup"><span data-stu-id="0be59-151">From the remaining filters, the filter with the longest path prefix is selected and applied.</span></span> <span data-ttu-id="0be59-152">如果未找到筛选器，则从第 1 步重新开始执行选择过程。</span><span class="sxs-lookup"><span data-stu-id="0be59-152">If a filter isn't found, the selection process starts over again at step 1.</span></span> <span data-ttu-id="0be59-153">使用下一个子域重复此过程。</span><span class="sxs-lookup"><span data-stu-id="0be59-153">The process is repeated with the next subdomain.</span></span>

### <span data-ttu-id="0be59-154">其他筛选器信息</span><span class="sxs-lookup"><span data-stu-id="0be59-154">Additional filter information</span></span>

<span data-ttu-id="0be59-155">如果筛选器包含点（“.”）**主机**前缀，则只筛选完全匹配的**主机**。</span><span class="sxs-lookup"><span data-stu-id="0be59-155">If a filter has a dot (".") prefixing the **host** then only exact **host** matches are filtered.</span></span> <span data-ttu-id="0be59-156">例如：</span><span class="sxs-lookup"><span data-stu-id="0be59-156">For example:</span></span>

- <span data-ttu-id="0be59-157">“contoso.com”（无点前缀）将与“contoso.com”、“www.contoso.com”和“sub.www.contoso.com”匹配</span><span class="sxs-lookup"><span data-stu-id="0be59-157">"contoso.com" (no dot) will match "contoso.com", "www.contoso.com", and "sub.www.contoso.com"</span></span>
- <span data-ttu-id="0be59-158">“.www.contoso.com”（带点前缀）将只与“www.contoso.com”匹配</span><span class="sxs-lookup"><span data-stu-id="0be59-158">".www.contoso.com" (with a dot prefix) will only match "www.contoso.com"</span></span>

<span data-ttu-id="0be59-159">你可以使用标准或自定义**架构**。</span><span class="sxs-lookup"><span data-stu-id="0be59-159">You can use either a standard or customer **schema**.</span></span> <span data-ttu-id="0be59-160">受支持的标准架构包括：</span><span class="sxs-lookup"><span data-stu-id="0be59-160">Supported standard schemas include:</span></span>

- <span data-ttu-id="0be59-161">_about_、_blob_、_content_、_edge_、_cid_、_data_、_file_、_filesystem_、_ftp_、_gopher_、_http_、_https_、_javascript_、_mailto_、_ws_ 和 _wss_。</span><span class="sxs-lookup"><span data-stu-id="0be59-161">_about_, _blob_, _content_, _edge_, _cid_, _data_, _file_, _filesystem_, _ftp_, _gopher_, _http_, _https_, _javascript_, _mailto_, _ws_, and _wss_.</span></span>

<span data-ttu-id="0be59-162">任何其他**架构**都被视为自定义**架构**，但只允许使用 _schema:_ 和 _schema://\*_ 模式。</span><span class="sxs-lookup"><span data-stu-id="0be59-162">Any other **schema** is treated as a custom **schema**, but only the _schema:\*_ and _schema://\*_ patterns are allowed.</span></span> <span data-ttu-id="0be59-163">例如：</span><span class="sxs-lookup"><span data-stu-id="0be59-163">For example:</span></span>

- <span data-ttu-id="0be59-164">“custom:*”或“custom://*”将与“custom:app”匹配</span><span class="sxs-lookup"><span data-stu-id="0be59-164">"custom:*" or "custom://*" will match "custom:app"</span></span>
- <span data-ttu-id="0be59-165">“custom:app”或“custom://app”无效</span><span class="sxs-lookup"><span data-stu-id="0be59-165">"custom:app" or "custom://app" are invalid</span></span>

<span data-ttu-id="0be59-166">**架构**和**主机**不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0be59-166">**schema** and **host** aren't case-sensitive.</span></span> <span data-ttu-id="0be59-167">例如：</span><span class="sxs-lookup"><span data-stu-id="0be59-167">For example:</span></span>

- <span data-ttu-id="0be59-168">“http://contoso.com”筛选器与“HTTP://contoso.com”、“http://contoso.COM”和“http://contoso.com”匹配</span><span class="sxs-lookup"><span data-stu-id="0be59-168">"http://contoso.com" filter matches "HTTP://contoso.com", "http://contoso.COM", and "http://contoso.com"</span></span>

<span data-ttu-id="0be59-169">**路径**和**查询**区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0be59-169">**path** and **query** are case-sensitive.</span></span> <span data-ttu-id="0be59-170">例如：</span><span class="sxs-lookup"><span data-stu-id="0be59-170">For example:</span></span>

- <span data-ttu-id="0be59-171">“http://contoso.com/path?query=A”筛选器与“http://contoso.com/Path?query=A”或“http://contoso.com/path?Query=A”不匹配。</span><span class="sxs-lookup"><span data-stu-id="0be59-171">"http://contoso.com/path?query=A" filter doesn't match "http://contoso.com/Path?query=A" or "http://contoso.com/path?Query=A".</span></span> <span data-ttu-id="0be59-172">它与“http://contoso.COM/path?query=A”匹配。</span><span class="sxs-lookup"><span data-stu-id="0be59-172">It does match "http://contoso.COM/path?query=A".</span></span>

## <span data-ttu-id="0be59-173">内容许可证</span><span class="sxs-lookup"><span data-stu-id="0be59-173">Content license</span></span>

> [!NOTE]
> <span data-ttu-id="0be59-174">本页面的某些部分是根据 Chromium.org 创建和共享的作品所做的修改，并根据 [Creative Commons Attribution 4.0 国际许可证](http://creativecommons.org/licenses/by/4.0/)中所述的条款进行使用。</span><span class="sxs-lookup"><span data-stu-id="0be59-174">Portions of this page are modifications based on work created and shared by Chromium.org and used according to terms described in the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).</span></span> <span data-ttu-id="0be59-175">[可在此处找到原始 Chromium 页面](https://www.chromium.org/administrators/url-blacklist-filter-format)。</span><span class="sxs-lookup"><span data-stu-id="0be59-175">The original [Chromium page can be found here](https://www.chromium.org/administrators/url-blacklist-filter-format).</span></span>
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /><span data-ttu-id="0be59-176">此作品通过 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 国际许可证</a>获得许可。</span><span class="sxs-lookup"><span data-stu-id="0be59-176">This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.</span></span>

## <span data-ttu-id="0be59-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0be59-177">See also</span></span>

- [<span data-ttu-id="0be59-178">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="0be59-178">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
