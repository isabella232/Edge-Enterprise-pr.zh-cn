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
# 基于 URL 列表的策略的筛选器格式

本文介绍了用于 Microsoft Edge 基于 URL 列表的策略（[例如 URLBlocklist](microsoft-edge-policies.md#urlblocklist)、[URLAllowList](microsoft-edge-policies.md#urlallowlist) 和 [CertificateTransparencyEnforcementDisabledForUrls](microsoft-edge-policies.md#certificatetransparencyenforcementdisabledforurls) 策略）的筛选器格式。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## 筛选器格式

筛选器格式为：

```
    [scheme://][.]host[:port][/path][@query]
```

筛选器格式中的字段为：

| 字段 | 说明 |
| --- | --- |
| **方案**（*可选*） | 它可以是 http://、https://、ftp://、edge:// 等。 |
| **主机**（*必需*） | 它必须是有效的主机名或 IP 地址，并且你可以使用通配符（“\*”）。 若要禁用子域匹配，请在**主机**前添加可选的点（“.”）。 |
| **端口**（*可选*） | 有效值范围为 1 到 65535。 |
| **路径**（*可选*） | 你可以在路径中使用任何字符串。 |
| **查询**（*可选*） | **查询**是用 & 号分隔的键值或纯键令牌。 使用等号（“=”）分隔键值令牌。 若要指明前缀匹配，可以在**查询**结尾处使用星号（“\*”）。 |

## 将筛选器格式与 URL 格式进行比较

筛选器格式类似于 URL 格式，但有以下几点不同：

- 如果你添加“user:pass”，它会被忽略。 例如，http://user:pass@ftp.contoso.com/pub/example.iso。
- 如果你添加片段标识符（“#”），此标识符及其后面跟的所有内容都会被忽略。
- 你可以将通配符（“*”）用作**主机**，并能在它前面添加点（“.”）。
- 你可以使用左斜线（“/”）或点（“.”）作为**主机**的后缀。 在这种情况下，后缀会被忽略。

## 筛选器选择条件

为 URL 选择的筛选器是处理以下筛选器选择规则后找到的最具体的匹配项：

1. 首先选择具有最长**主机**匹配项的筛选器。
2. 在所选筛选器中，任何包含不匹配方案或端口的筛选器都会被放弃。
3. 从其余筛选器中，选择具有最长匹配**路径**的筛选器。
4. 在剩下的筛选器中，选择的是具有最长查询令牌集的筛选器。 在这一步，如果允许列表筛选器和阻止列表筛选器的**路径**长度和**查询**令牌数都相同，则允许列表筛选器优先于阻止列表筛选器。
5. 如果剩余筛选器无效，则从**主机**中删除最左侧的子域，并从第 1 步重新开始执行选择过程。 特殊星号（“*”）**主机**是最后搜索的，它匹配所有主机。
6. 如果筛选器可用，它会阻止或允许 URL 请求。

   >[!NOTE]
   >如果没有匹配的筛选器，则默认行为是允许 URL 请求。

## 筛选器选择条件示例

在此示例中，搜索“https://sub.contoso.com/docs”的匹配项时，筛选器选择会：

1. 搜索“sub.contoso.com”的筛选器。 如果找到筛选器，搜索将转到第 2 步。 如果找不到筛选器，它会使用“contoso.com”和“com”重试，最后用 "" 重试。
2. 在所选筛选器中，任何在**方案**中没有“http”的项都会被删除。
3. 在剩下的筛选器中，任何具有非“80”的确切端口号的筛选器都会被删除。
4. 从其余筛选器中，删除**路径**前缀不是“/docs”的任何项。
5. 从其余筛选器中，选择并应用路径前缀最长的筛选器。 如果未找到筛选器，则从第 1 步重新开始执行选择过程。 使用下一个子域重复此过程。

### 其他筛选器信息

如果筛选器包含点（“.”）**主机**前缀，则只筛选完全匹配的**主机**。 例如：

- “contoso.com”（无点前缀）将与“contoso.com”、“www.contoso.com”和“sub.www.contoso.com”匹配
- “.www.contoso.com”（带点前缀）将只与“www.contoso.com”匹配

你可以使用标准或自定义**架构**。 受支持的标准架构包括：

- _about_、_blob_、_content_、_edge_、_cid_、_data_、_file_、_filesystem_、_ftp_、_gopher_、_http_、_https_、_javascript_、_mailto_、_ws_ 和 _wss_。

任何其他**架构**都被视为自定义**架构**，但只允许使用 _schema:_ 和 _schema://*_ 模式。 例如：

- “custom:*”或“custom://*”将与“custom:app”匹配
- “custom:app”或“custom://app”无效

**架构**和**主机**不区分大小写。 例如：

- “http://contoso.com”筛选器与“HTTP://contoso.com”、“http://contoso.COM”和“http://contoso.com”匹配

**路径**和**查询**区分大小写。 例如：

- “http://contoso.com/path?query=A”筛选器与“http://contoso.com/Path?query=A”或“http://contoso.com/path?Query=A”不匹配。 它与“http://contoso.COM/path?query=A”匹配。

## 内容许可证

> [!NOTE]
> 本页面的某些部分是根据 Chromium.org 创建和共享的作品所做的修改，并根据 [Creative Commons Attribution 4.0 国际许可证](http://creativecommons.org/licenses/by/4.0/)中所述的条款进行使用。 [可在此处找到原始 Chromium 页面](https://www.chromium.org/administrators/url-blacklist-filter-format)。
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />此作品通过 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 国际许可证</a>获得许可。

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
