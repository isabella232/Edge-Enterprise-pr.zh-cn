---
title: '按策略排列的每站点配置 '
ms.author: collw
author: AndreaLBarr
manager: laurawi
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: '按策略排列的每站点配置 '
ms.openlocfilehash: 4f1bf9a421f0098ba8105e78f77ac4af62530239
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641688"
---
# <a name="persite-configuration-by-policy"></a>按策略排列的每站点配置

## <a name="introduction-browsers-as-decision-makers"></a>简介：作为“决策制定者”的浏览器

作为每个页面加载的一部分，浏览器会做出许多决策 — 特定 API 是否可用？ 是否应允许资源负载？ 是否应允许脚本运行？ 列表很长。

在大多数情况下，决策受两个输入的约束：用户设置和要为其做出决策页面的 URL。

在旧版 Internet Explorer Web 平台中，每个决策都称为 [URLAction](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537178%28v%3dvs.85%29)，并且企业组策略和 Internet 控制面板中的用户设置控制浏览器处理每个决策的方式。  

在 Microsoft Edge 中，大多数每站点权限由设置和策略使用具有有限通配符支持的简单语法表达来控制。 Windows 安全区域仍然仅用于少量的配置决策。

## <a name="background-windows-security-zones"></a>背景: Windows 安全区域

为了简化用户或其管理员的配置，旧平台将站点分为五个不同的 **安全区域:** 本地计算机、本地 Intranet、受信任、Internet 和受限站点。

做出决策时，浏览器会首先将网站映射到区域，然后查阅该区域的 URLAction 设置，以确定该进行的操作。 合理的默认值 (如“自动满足来自我的 Intranet 的身份验证挑战”) 意味着大多数用户不需要更改任何默认设置。

用户可以使用 Internet 控制面板将特定站点分配到区域，并为每个区域配置权限结果。 在托管环境中，管理员可以使用组策略将特定站点分配到区域（通过“站点到区域分配列表”策略），并根据每个区域指定 URLActions 设置。 除了将站点手动管理或用户分配到区域之外，其他启发还可以  [将站点分配到本地 Intranet 区域](/archive/blogs/ieinternals/the-intranet-zone)。 特别是，分配无点主机名 (例如，`http://payroll`) 到 Intranet 区域。 如果使用了代理配置脚本，则配置为绕过代理的任何站点都将映射到 Intranet 区域。

Microsoft Edge 旧版通过一些简化的更改从其 Internet Explorer 前身继承了区域体系结构：

- Windows 的五个内置区域已折叠为三个: Internet (Internet)、受信任 (Intranet+Trusted) 和本地计算机。 已删除受限站点区域。

- 已硬编码区域与 URLAction 的映射到浏览器中，忽略了“组策略”和“Internet 控件面板”中的设置。

## <a name="per-site-permissions-in-the-microsoft-edge"></a>Microsoft Edge 中的每站点权限

与其前版本不同，新 Microsoft Edge 对 Windows 安全区域的使用非常有限。 相反，大多数通过 [策略](/deployedge/microsoft-edge-policies)为管理员提供每站点配置的权限和功能都依赖于 [URL 筛选格式](/DeployEdge/edge-learnmmore-url-list-filter%20format)中的规则列表。

当终端用户打开  <code>edge://settings/content/siteDetails?site=https://example.com</code> 时，他们会发现一长串配置开关和各种权限的列表。 用户很少直接使用“设置页面”，而是在浏览时使用各种小组件和 **页面信息** 下拉菜单 (当点击地址栏中的锁定图标时出现) 中的切换，或通过地址栏右边缘的各种提示或按钮进行选择。

企业可以使用“组策略”为控制浏览器行为的各个策略提供站点列表。 若要查找这些策略，只需打开 [Microsoft Edge 组策略文档](/deployedge/microsoft-edge-policies) 并搜索 **ForUrls** ，以根据加载站点的 URL 查找允许和阻止行为的策略。 大多数相关设置都列在 [“内容设置”的“组策略”](/deployedge/microsoft-edge-policies#content-settings) 部分。

还有许多策略 (其名称包含  **默认**) 控制特定设置的默认行为。

许多设置非常模糊（WebSerial、WebMIDI），并且通常没有任何理由更改默认设置 (图像)。

## <a name="common-questions"></a>常见问题

## <a name="q-can-the-url-filter-format-match-on-a-sites-ip-address"></a>问: URL 筛选器格式是否与站点的 IP 地址相匹配?

否，格式不支持为允许列表和阻止列表指定 IP 范围。 它确实支持单个 IP  **文本** 的规范，但仅当用户使用上述文本导航到站点时，才遵守此类规则 (例如  <http://127.0.0.1/>)。 如果使用主机名 (<http://localhost>)，即使主机的解析 IP 与筛选器列出的 IP 相匹配，也不会遵守 IP 文本规则。

## <a name="q-can-url-filters-matchjustdotless-host-names"></a>问：URL 筛选器是否仅匹配无点主机名？

否。 必须单独列出每个所需的主机名，例如 (`https://payroll`、`https://stock`、`https://who`等)。

如果有足够的远见将 Intranet 结构化，使主机名采用以下形式:

- <div style="display: inline">`https://payroll.contoso-intranet.com`</div>

- <div style="display: inline">`https://timecard.contoso-intranet.com`</div>

- <div style="display: inline">`https://sharepoint.contoso-intranet.com`</div>

恭喜，你已实现最佳做法。 可以使用 **_.contoso-intranet.com_* 条目配置每个所需策略，将选择加入   整个 Intranet。

## <a name="use-of-security-zones-inthe-microsoft-edge"></a>在 Microsoft Edge 中使用安全区域

虽然 Microsoft Edge 主要依赖于使用 URL 筛选器格式的单个策略，但它默认情况下会在少数位置继续使用 Windows 安全区域，以简化过去依赖于区域配置的企业中的部署。 以下行为由区域策略控制：

1. 决定是否自动释放 Windows 集成身份验证 （Kerberos/NTLM） 凭据时

2. 确定如何处理文件下载时

3. Internet Explorer 模式

## <a name="credential-release"></a>凭据释放

默认情况下，Microsoft Edge 将评估 URLACTION_CREDENTIALS_USE 以确定是自动使用 Windows 集成身份验证，还是用户应看到手动身份验证提示。 配置 [AuthServerAllowlist 站点列表策略](/deployedge/microsoft-edge-policies#authserverallowlist) 将阻止查阅区域策略。

## <a name="file-downloads"></a>文件下载

关于文件下载来源的证据 (所谓的“[Web 标记](https://textslashplain.com/2016/04/04/downloads-and-the-mark-of-the-web/) 是对从 Internet 区域下载的文件的记录。 其他应用程序 (例如 Windows Shell、Microsoft Office 等) 在决定如何处理文件时可能会考虑此来源证据。

如果 Windows 安全区域策略配置为禁用“启动应用程序和不安全文件”设置，则 Microsoft Edge 下载管理器将阻止从该区域中的站点下载文件，并附注:“无法下载 – 已阻止”。  

## <a name="ie-mode"></a>IE 模式

可以将 IE 模式配置为  [在 IE 模式下打开所有 Intranet 站点](/deployedge/edge-ie-mode#configure-all-intranet-sites)。 在此配置中，Edge 在决定是否应在 IE 模式下打开时评估 URL 的区域。 除了此初始决策之外，IE 模式选项卡实际上正在运行Internet Explorer，因此它们会像 Internet Explorer 本身一样评估每个策略决策的区域设置。

## <a name="summary"></a>摘要

在大多数情况下，Microsoft Edge 设置可以保留为默认值。 希望更改所有站点或特定站点默认值的管理员可以使用相应的组策略来指定站点列表或默认行为。 在少数情况下 (凭据释放、文件下载和 IE 模式)，管理员将继续通过配置 Windows 安全区域设置来控制行为。
