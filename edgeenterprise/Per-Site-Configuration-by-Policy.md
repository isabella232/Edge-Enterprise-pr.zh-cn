---
title: 按策略配置每个站点
ms.author: collw
author: dan-wesley
manager: laurawi
ms.date: 01/04/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 按策略配置每个站点
ms.openlocfilehash: 147f14fdd09f56161bf03ca88b5e6107ba9c88c5
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2022
ms.locfileid: "12297861"
---
# <a name="per-site-configuration-by-policy"></a>按策略配置每个站点

本文按策略介绍每个站点配置，以及浏览器如何处理从网站加载页面。

## <a name="the-browser-as-a-decision-maker"></a>作为决策制定者浏览器

作为每个页面加载的一部分，浏览器会做出许多决定。 这些决策中的一些（而不是全部）包括：特定 API 是否可用、是否允许资源负载，以及是否允许脚本运行。

在大多数情况下，浏览器决策受以下输入控制：

- 用户设置
- 做出决策的页面的 URL

在 Internet Explorer Web 平台中，每个决策都称为 URLAction。 有关详细信息，请参阅 [URL 操作标志](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537178%28v%3dvs.85%29)。 Internet 控制面板Enterprise URLAction、组策略和用户设置控制浏览器处理每个决策的方式。  

在Microsoft Edge，大多数每个网站的权限由使用具有有限通配符支持的简单语法表示的设置和策略控制。 Windows 安全中心区域仍用于一些配置决策。

## <a name="windows-security-zones"></a>Windows 安全中心区域

为了简化用户或管理员的配置，旧平台将网站分类为五个不同的安全区域之一。 这些安全区域包括：本地计算机、本地 Intranet、受信任的站点、Internet 和受限站点。

做出页面加载决策时，浏览器将网站映射到区域，然后查看该区域 URLAction 的设置，以决定要执行哪些操作。 "自动满足来自 Intranet 的身份验证挑战"等合理默认值意味着大多数用户永远不需要更改任何默认设置。

用户可以使用 Internet 控制面板将特定站点分配到区域，并为每个区域配置权限结果。 在托管环境中，管理员可以使用组策略将特定站点分配到区域（通过“站点到区域分配列表”策略），并根据每个区域指定 URLActions 设置。 除了手动管理或用户向区域分配站点外，其他启发式方法还可以将站点 [分配到本地 Intranet 区域](/archive/blogs/ieinternals/the-intranet-zone)。 特别是，无点主机 (例如，) `http://payroll` 分配给 Intranet 区域。 如果使用了代理配置脚本，则配置为绕过代理的任何站点都将映射到 Intranet 区域。

Microsoft Edge 旧版通过一些简化的更改从其 Internet Explorer 前身继承了区域体系结构：

- Windows 的五个内置区域已折叠为三个: Internet (Internet)、受信任 (Intranet+Trusted) 和本地计算机。 已删除受限站点区域。
- 已硬编码区域与 URLAction 的映射到浏览器中，忽略了“组策略”和“Internet 控件面板”中的设置。

## <a name="per-site-permissions-in-microsoft-edge"></a>每个网站权限Microsoft Edge

Microsoft Edge对区域进行Windows 安全中心使用。 相反，大多数通过 [策略](/deployedge/microsoft-edge-policies)为管理员提供每站点配置的权限和功能都依赖于 [URL 筛选格式](/DeployEdge/edge-learnmmore-url-list-filter%20format)中的规则列表。

当最终用户打开设置页（如 ）时，他们将找到各种权限的配置 `edge://settings/content/siteDetails?site=https://example.com` 开关和列表的长列表。 用户很少直接设置页面，而是在页面信息下拉列表中浏览和使用各种小组件和切换 **时**   做出选择。 当您选择地址栏中的锁定图标时，将显示此列表。 您还可以使用地址栏右边缘的各种提示或按钮。 下一个屏幕截图显示了页面信息的示例。

:::image type="content" source="media/per-site-configuration-by-policy/edge-page-info.png" alt-text="浏览器中当前页面的页面信息和设置。":::

企业可以使用组策略为控制浏览器行为的个人策略设置站点列表。 若要查找这些策略，请打开 [](/deployedge/microsoft-edge-policies)Microsoft Edge 组策略文档并搜索"ForUrls"，以查找允许和阻止基于已加载网站的   URL 的行为的策略。 大部分相关设置都列在"内容策略组 [策略"设置](/deployedge/microsoft-edge-policies#content-settings)部分中。

此外，许多策略 (其名称包含"默认") 用于控制给定设置的默认行为。

许多设置都 (WebSerial、WebMIDI) 并且通常没有理由更改默认设置。

## <a name="security-zones-inmicrosoft-edge"></a>安全区域中Microsoft Edge

尽管Microsoft Edge主要依赖于使用 URL 筛选器格式的单个策略，但在某些情况下，Windows继续使用安全区域。 此方法简化了过去一直依赖区域配置的企业中部署。

以下行为由区域策略控制：

- 决定是自动Windows Kerberos (NTLM) 集成身份验证。
- 决定如何处理文件下载。
- 对于Internet Explorer模式。

## <a name="credential-release"></a>凭据发布

默认情况下，Microsoft Edge评估以确定Windows是否自动使用集成身份验证，或者用户是否将看到  `URLACTION_CREDENTIALS_USE`  手动身份验证提示。 配置 [AuthServerAllowlist 站点列表策略](/deployedge/microsoft-edge-policies#authserverallowlist) 将阻止咨询区域策略。

## <a name="file-downloads"></a>文件下载

对于从 Internet 区域下载 (文件下载源（也称为"Web 标记[](https://textslashplain.com/2016/04/04/downloads-and-the-mark-of-the-web/)"）的证据会进行记录。 其他应用程序（如 Windows Shell）Microsoft Office决定如何处理文件时，可能会考虑此来源证据。

如果将Windows 安全中心区域策略配置为禁用启动应用程序和下载不安全文件的设置，Microsoft Edge 的下载管理器将阻止从该区域中的站点下载文件。 用户将看到以下注释："无法下载 – 已阻止"。  

## <a name="ie-mode"></a>IE 模式

可以将 IE 模式配置为  [在 IE 模式下打开所有 Intranet 站点](/deployedge/edge-ie-mode#configure-all-intranet-sites)。 使用此配置时，Microsoft Edge在决定是否应在 IE 模式下打开它时评估 URL 的区域。 除了此初始决策之外，IE 模式选项卡实际上Internet Explorer，因此它们评估每个策略决策的区域设置，就像Internet Explorer一样。

## <a name="summary"></a>摘要

在大多数情况下，Microsoft Edge 设置可以保留为默认值。 希望更改所有站点或特定站点默认值的管理员可以使用相应的组策略来指定站点列表或默认行为。 在少数情况下（如凭据发布、文件下载和 IE 模式）中，管理员将继续通过配置"区域"Windows 安全中心行为。

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="can-the-url-filter-format-match-on-a-sites-ip-address"></a>URL 筛选器格式能否与网站的 IP 地址相匹配？

否，格式不支持指定允许列表和阻止列表的 IP 范围。 它支持单个 **IP**文本的规范，但仅在用户使用上述文字文本（例如， (）导航到网站时 `http://127.0.0.1/` ，才遵守) 。 如果使用主机名 (`http://localhost`)，即使主机的解析 IP 与筛选器列出的 IP 相匹配，也不会遵守 IP 文本规则。

### <a name="can-url-filters-matchdotless-host-names"></a>URL 筛选器可以匹配无点主机名吗？

否。 必须列出每个主机名，例如 `https://payroll` 、 `https://stock` 、 `https://who` 等。

如果您进行了充分向前思考，以构建 Intranet，使主机名具有以下形式，则已实现最佳实践。

- `https://payroll.contoso-intranet.com`

- `https://timecard.contoso-intranet.com`

- `https://sharepoint.contoso-intranet.com`

在上一个方案中，可以使用 ***.contoso-intranet.com**条目配置每个策略，将选择加入   整个 Intranet。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge 文档](./index.yml)
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
