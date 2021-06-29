---
title: '按策略排列的每站点配置 '
ms.author: collw
author: AndreaLBarr
manager: laurawi
ms.date: 05/03/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: '按策略排列的每站点配置 '
ms.openlocfilehash: 6bba2c9b1d691c338a3146ef246de9f94e262a03
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "11618035"
---
# <a name="persite-configuration-by-policy"></a><span data-ttu-id="b51a1-103">按策略排列的每站点配置</span><span class="sxs-lookup"><span data-stu-id="b51a1-103">PerSite Configuration by Policy</span></span>

## <a name="introduction-browsers-as-decision-makers"></a><span data-ttu-id="b51a1-104">简介：作为“决策制定者”的浏览器</span><span class="sxs-lookup"><span data-stu-id="b51a1-104">Introduction: Browsers as Decision Makers</span></span>

<span data-ttu-id="b51a1-105">作为每个页面加载的一部分，浏览器会做出许多决策 — 特定 API 是否可用？</span><span class="sxs-lookup"><span data-stu-id="b51a1-105">As a part of every page load, browsers make many decisions — should a particular API be available?</span></span> <span data-ttu-id="b51a1-106">是否应允许资源负载？</span><span class="sxs-lookup"><span data-stu-id="b51a1-106">Should a resource load be permitted?</span></span> <span data-ttu-id="b51a1-107">是否应允许脚本运行？</span><span class="sxs-lookup"><span data-stu-id="b51a1-107">Should script be allowed to run?</span></span> <span data-ttu-id="b51a1-108">列表很长。</span><span class="sxs-lookup"><span data-stu-id="b51a1-108">The list is long.</span></span>

<span data-ttu-id="b51a1-109">在大多数情况下，决策受两个输入的约束：用户设置和要为其做出决策页面的 URL。</span><span class="sxs-lookup"><span data-stu-id="b51a1-109">In most cases, decisions are governed by two inputs: a user setting, and the URL of the page for which the decision is being made.</span></span>

<span data-ttu-id="b51a1-110">在旧版 Internet Explorer Web 平台中，每个决策都称为 [URLAction](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537178%28v%3dvs.85%29)，并且企业组策略和 Internet 控制面板中的用户设置控制浏览器处理每个决策的方式。</span><span class="sxs-lookup"><span data-stu-id="b51a1-110">In the legacy Internet Explorer web platform, each of these decisions was called an [URLAction](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537178%28v%3dvs.85%29), and Enterprise Group Policy and user settings inside the Internet Control Panel controlled how the browser would handle each decision.</span></span>  

<span data-ttu-id="b51a1-111">在 Microsoft Edge 中，大多数每站点权限由设置和策略使用具有有限通配符支持的简单语法表达来控制。</span><span class="sxs-lookup"><span data-stu-id="b51a1-111">In the Microsoft Edge, most per-site permissions are controlled by settings and policies expressed using a simple syntax with limited wild carding support.</span></span> <span data-ttu-id="b51a1-112">Windows 安全区域仍然仅用于少量的配置决策。</span><span class="sxs-lookup"><span data-stu-id="b51a1-112">Windows Security Zones are still used only for a small number of configuration decisions.</span></span>

## <a name="background-windows-security-zones"></a><span data-ttu-id="b51a1-113">背景: Windows 安全区域</span><span class="sxs-lookup"><span data-stu-id="b51a1-113">Background: Windows Security Zones</span></span>

<span data-ttu-id="b51a1-114">为了简化用户或其管理员的配置，旧平台将站点分为五个不同的 **安全区域:** 本地计算机、本地 Intranet、受信任、Internet 和受限站点。</span><span class="sxs-lookup"><span data-stu-id="b51a1-114">To simplify configuration for the user or their administrator, the legacy platform classified sites into five different **Security Zones:** Local Machine, Local Intranet, Trusted, Internet, and Restricted Sites.</span></span>

<span data-ttu-id="b51a1-115">做出决策时，浏览器会首先将网站映射到区域，然后查阅该区域的 URLAction 设置，以确定该进行的操作。</span><span class="sxs-lookup"><span data-stu-id="b51a1-115">When making a decision, the browser would first map the website to a Zone, then consult the setting for that URLAction for that Zone to decide what to do.</span></span> <span data-ttu-id="b51a1-116">合理的默认值 (如“自动满足来自我的 Intranet 的身份验证挑战”) 意味着大多数用户不需要更改任何默认设置。</span><span class="sxs-lookup"><span data-stu-id="b51a1-116">Reasonable defaults like “Automatically satisfy authentication challenges from my Intranet” meant that most users never needed to change any settings away from their defaults.</span></span>

<span data-ttu-id="b51a1-117">用户可以使用 Internet 控制面板将特定站点分配到区域，并为每个区域配置权限结果。</span><span class="sxs-lookup"><span data-stu-id="b51a1-117">Users can use the Internet Control Panel to assign specific sites to Zones and to configure the permission results for each zone.</span></span> <span data-ttu-id="b51a1-118">在托管环境中，管理员可以使用组策略将特定站点分配到区域（通过“站点到区域分配列表”策略），并根据每个区域指定 URLActions 设置。</span><span class="sxs-lookup"><span data-stu-id="b51a1-118">In managed environments, administrators can use Group Policy to assign specific sites to Zones (via “Site to Zone Assignment List” policy) and specify the settings for URLActions on a per-zone basis.</span></span> <span data-ttu-id="b51a1-119">除了将站点手动管理或用户分配到区域之外，其他启发还可以  [将站点分配到本地 Intranet 区域](/archive/blogs/ieinternals/the-intranet-zone)。</span><span class="sxs-lookup"><span data-stu-id="b51a1-119">Beyond manual administrative or user assignment of sites to Zones, additional heuristics could [assign sites to the Local Intranet Zone](/archive/blogs/ieinternals/the-intranet-zone).</span></span> <span data-ttu-id="b51a1-120">特别是，分配无点主机名 (例如，`http://payroll`) 到 Intranet 区域。</span><span class="sxs-lookup"><span data-stu-id="b51a1-120">In particular, dotless host names (e.g. `http://payroll`) were assigned to the Intranet Zone.</span></span> <span data-ttu-id="b51a1-121">如果使用了代理配置脚本，则配置为绕过代理的任何站点都将映射到 Intranet 区域。</span><span class="sxs-lookup"><span data-stu-id="b51a1-121">If a Proxy Configuration script was used, any sites configured to bypass the proxy would be mapped to the Intranet Zone.</span></span>

<span data-ttu-id="b51a1-122">Microsoft Edge 旧版通过一些简化的更改从其 Internet Explorer 前身继承了区域体系结构：</span><span class="sxs-lookup"><span data-stu-id="b51a1-122">Microsoft Edge Legacy inherited the Zones architecture from its Internet Explorer predecessor with a few simplifying changes:</span></span>

- <span data-ttu-id="b51a1-123">Windows 的五个内置区域已折叠为三个: Internet (Internet)、受信任 (Intranet+Trusted) 和本地计算机。</span><span class="sxs-lookup"><span data-stu-id="b51a1-123">Windows’ five built-in Zones were collapsed to three: Internet (Internet), Trusted (Intranet+Trusted), and Local Computer.</span></span> <span data-ttu-id="b51a1-124">已删除受限站点区域。</span><span class="sxs-lookup"><span data-stu-id="b51a1-124">The Restricted Sites Zone was removed.</span></span>

- <span data-ttu-id="b51a1-125">已硬编码区域与 URLAction 的映射到浏览器中，忽略了“组策略”和“Internet 控件面板”中的设置。</span><span class="sxs-lookup"><span data-stu-id="b51a1-125">Zone to URLAction mappings were hardcoded into the browser, ignoring Group Policies and settings in the Internet Control Panel.</span></span>

## <a name="per-site-permissions-in-the-microsoft-edge"></a><span data-ttu-id="b51a1-126">Microsoft Edge 中的每站点权限</span><span class="sxs-lookup"><span data-stu-id="b51a1-126">Per-Site Permissions in the Microsoft Edge</span></span>

<span data-ttu-id="b51a1-127">与其前版本不同，新 Microsoft Edge 对 Windows 安全区域的使用非常有限。</span><span class="sxs-lookup"><span data-stu-id="b51a1-127">Unlike its predecessors, the new Microsoft Edge makes very limited use of Windows Security Zones.</span></span> <span data-ttu-id="b51a1-128">相反，大多数通过 [策略](/deployedge/microsoft-edge-policies)为管理员提供每站点配置的权限和功能都依赖于 [URL 筛选格式](/DeployEdge/edge-learnmmore-url-list-filter%20format)中的规则列表。</span><span class="sxs-lookup"><span data-stu-id="b51a1-128">Instead, most permissions and features that offer administrators per-site configuration via [policy](/deployedge/microsoft-edge-policies) rely on lists of rules in the [URL Filter Format](/DeployEdge/edge-learnmmore-url-list-filter%20format).</span></span>

<span data-ttu-id="b51a1-129">当终端用户打开  <code>edge://settings/content/siteDetails?site=https://example.com</code> 时，他们会发现一长串配置开关和各种权限的列表。</span><span class="sxs-lookup"><span data-stu-id="b51a1-129">When end-users open <code>edge://settings/content/siteDetails?site=https://example.com</code>, they’ll find a long list of configuration switches and lists for various permissions.</span></span> <span data-ttu-id="b51a1-130">用户很少直接使用“设置页面”，而是在浏览时使用各种小组件和 **页面信息** 下拉菜单 (当点击地址栏中的锁定图标时出现) 中的切换，或通过地址栏右边缘的各种提示或按钮进行选择。</span><span class="sxs-lookup"><span data-stu-id="b51a1-130">Users rarely use the Settings Page directly, instead making choices while browsing using various widgets and toggles in the **Page Info** dropdown (which appears when you click the lock icon in the address bar) or via various prompts or buttons at the right-edge of the address bar.</span></span>

<span data-ttu-id="b51a1-131">企业可以使用“组策略”为控制浏览器行为的各个策略提供站点列表。</span><span class="sxs-lookup"><span data-stu-id="b51a1-131">Enterprises can use Group Policy to provision site lists for individual policies that control the browser’s behavior.</span></span> <span data-ttu-id="b51a1-132">若要查找这些策略，只需打开 [Microsoft Edge 组策略文档](/deployedge/microsoft-edge-policies) 并搜索 **ForUrls** ，以根据加载站点的 URL 查找允许和阻止行为的策略。</span><span class="sxs-lookup"><span data-stu-id="b51a1-132">To find these policies, simply open the [Microsoft Edge Group Policy documentation](/deployedge/microsoft-edge-policies) and search for **ForUrls** to find the policies that allow and block behavior based on the loaded site’s URL.</span></span> <span data-ttu-id="b51a1-133">大多数相关设置都列在 [“内容设置”的“组策略”](/deployedge/microsoft-edge-policies#content-settings) 部分。</span><span class="sxs-lookup"><span data-stu-id="b51a1-133">Most of the relevant settings are listed within the [Group Policy for Content Settings](/deployedge/microsoft-edge-policies#content-settings) section.</span></span>

<span data-ttu-id="b51a1-134">还有许多策略 (其名称包含  **默认**) 控制特定设置的默认行为。</span><span class="sxs-lookup"><span data-stu-id="b51a1-134">There are also a number of policies (whose names contain **Default**) that control the default behavior for a given setting.</span></span>

<span data-ttu-id="b51a1-135">许多设置非常模糊（WebSerial、WebMIDI），并且通常没有任何理由更改默认设置 (图像)。</span><span class="sxs-lookup"><span data-stu-id="b51a1-135">Many of the settings are very obscure (WebSerial, WebMIDI) and there’s very often no reason to change a setting away from the default (Images).</span></span>

## <a name="common-questions"></a><span data-ttu-id="b51a1-136">常见问题</span><span class="sxs-lookup"><span data-stu-id="b51a1-136">Common Questions</span></span>

## <a name="q-can-the-url-filter-format-match-on-a-sites-ip-address"></a><span data-ttu-id="b51a1-137">问: URL 筛选器格式是否与站点的 IP 地址相匹配?</span><span class="sxs-lookup"><span data-stu-id="b51a1-137">Q: Can the URL Filter Format match on a site’s IP address?</span></span>

<span data-ttu-id="b51a1-138">否，格式不支持为允许列表和阻止列表指定 IP 范围。</span><span class="sxs-lookup"><span data-stu-id="b51a1-138">No, the format does not support specifying an IP-range for allow and block lists.</span></span> <span data-ttu-id="b51a1-139">它确实支持单个 IP  **文本** 的规范，但仅当用户使用上述文本导航到站点时，才遵守此类规则 (例如  <http://127.0.0.1/>)。</span><span class="sxs-lookup"><span data-stu-id="b51a1-139">It does support specification of individual IP **literals**, but such rules are only respected if the user navigates to the site using said literal (e.g. <http://127.0.0.1/>).</span></span> <span data-ttu-id="b51a1-140">如果使用主机名 (<http://localhost>)，即使主机的解析 IP 与筛选器列出的 IP 相匹配，也不会遵守 IP 文本规则。</span><span class="sxs-lookup"><span data-stu-id="b51a1-140">If a hostname is used (<http://localhost>), the IP Literal rule will not be respected even though the resolved IP of the host matches the filter-listed IP.</span></span>

## <a name="q-can-url-filters-matchjustdotless-host-names"></a><span data-ttu-id="b51a1-141">问：URL 筛选器是否仅匹配无点主机名？</span><span class="sxs-lookup"><span data-stu-id="b51a1-141">Q: Can URL Filters match just dotless host names?</span></span>

<span data-ttu-id="b51a1-142">否。</span><span class="sxs-lookup"><span data-stu-id="b51a1-142">No.</span></span> <span data-ttu-id="b51a1-143">必须单独列出每个所需的主机名，例如 (`https://payroll`、`https://stock`、`https://who`等)。</span><span class="sxs-lookup"><span data-stu-id="b51a1-143">You must individually list each desired hostname, e.g. (`https://payroll`, `https://stock`, `https://who`, etc).</span></span>

<span data-ttu-id="b51a1-144">如果有足够的远见将 Intranet 结构化，使主机名采用以下形式:</span><span class="sxs-lookup"><span data-stu-id="b51a1-144">If you were forward-thinking enough to structure your intranet such that your host names are of the form:</span></span>

- <div style="display: inline">`https://payroll.contoso-intranet.com`</div>

- <div style="display: inline">`https://timecard.contoso-intranet.com`</div>

- <div style="display: inline">`https://sharepoint.contoso-intranet.com`</div>

<span data-ttu-id="b51a1-145">恭喜，你已实现最佳做法。</span><span class="sxs-lookup"><span data-stu-id="b51a1-145">Congratulations, you’ve implemented a best practice.</span></span> <span data-ttu-id="b51a1-146">可以使用 \***.contoso-intranet.com**  条目配置每个所需的策略，并且将选择加入整个 Intranet。</span><span class="sxs-lookup"><span data-stu-id="b51a1-146">You can configure each desired policy with a \***.contoso-intranet.com** entry and your entire Intranet will be opted in.</span></span>

## <a name="use-of-security-zones-inthe-microsoft-edge"></a><span data-ttu-id="b51a1-147">在 Microsoft Edge 中使用安全区域</span><span class="sxs-lookup"><span data-stu-id="b51a1-147">Use of Security Zones in the Microsoft Edge</span></span>

<span data-ttu-id="b51a1-148">虽然 Microsoft Edge 主要依赖于使用 URL 筛选器格式的单个策略，但它默认情况下会在少数位置继续使用 Windows 安全区域，以简化过去依赖于区域配置的企业中的部署。</span><span class="sxs-lookup"><span data-stu-id="b51a1-148">While Microsoft Edge mostly relies upon individual policies using the URL Filter format, it continues to use Windows’ Security Zones by default in a small number of places in order to simplify deployment within Enterprises that have historically relied upon Zones configuration.</span></span> <span data-ttu-id="b51a1-149">以下行为由区域策略控制：</span><span class="sxs-lookup"><span data-stu-id="b51a1-149">The following behaviors are controlled by Zone policy:</span></span>

1. <span data-ttu-id="b51a1-150">决定是否自动释放 Windows 集成身份验证 （Kerberos/NTLM） 凭据时</span><span class="sxs-lookup"><span data-stu-id="b51a1-150">When deciding whether to release Windows Integrated Authentication (Kerberos/NTLM) credentials automatically</span></span>

2. <span data-ttu-id="b51a1-151">确定如何处理文件下载时</span><span class="sxs-lookup"><span data-stu-id="b51a1-151">When deciding how to handle File Downloads</span></span>

3. <span data-ttu-id="b51a1-152">Internet Explorer 模式</span><span class="sxs-lookup"><span data-stu-id="b51a1-152">For Internet Explorer Mode</span></span>

## <a name="credential-release"></a><span data-ttu-id="b51a1-153">凭据释放</span><span class="sxs-lookup"><span data-stu-id="b51a1-153">Credential Release</span></span>

<span data-ttu-id="b51a1-154">默认情况下，Microsoft Edge 将评估 URLACTION_CREDENTIALS_USE 以确定是自动使用 Windows 集成身份验证，还是用户应看到手动身份验证提示。</span><span class="sxs-lookup"><span data-stu-id="b51a1-154">By default, Microsoft Edge will evaluate URLACTION_CREDENTIALS_USE to decide whether Windows Integrated Authentication is used automatically, or the user should instead see a manual authentication prompt.</span></span> <span data-ttu-id="b51a1-155">配置 [AuthServerAllowlist 站点列表策略](/deployedge/microsoft-edge-policies#authserverallowlist) 将阻止查阅区域策略。</span><span class="sxs-lookup"><span data-stu-id="b51a1-155">Configuring an [AuthServerAllowlist site list policy](/deployedge/microsoft-edge-policies#authserverallowlist) will prevent Zone Policy from being consulted.</span></span>

## <a name="file-downloads"></a><span data-ttu-id="b51a1-156">文件下载</span><span class="sxs-lookup"><span data-stu-id="b51a1-156">File Downloads</span></span>

<span data-ttu-id="b51a1-157">关于文件下载来源的证据 (所谓的“[Web 标记](https://textslashplain.com/2016/04/04/downloads-and-the-mark-of-the-web/) 是对从 Internet 区域下载的文件的记录。</span><span class="sxs-lookup"><span data-stu-id="b51a1-157">Evidence about the origins of a file download (the so-called “[Mark of the Web](https://textslashplain.com/2016/04/04/downloads-and-the-mark-of-the-web/) is recorded for files downloaded from the Internet Zone.</span></span> <span data-ttu-id="b51a1-158">其他应用程序 (例如 Windows Shell、Microsoft Office 等) 在决定如何处理文件时可能会考虑此来源证据。</span><span class="sxs-lookup"><span data-stu-id="b51a1-158">Other applications (e.g. the Windows Shell, Microsoft Office, etc) may take this origin evidence into account when deciding how to handle a file.</span></span>

<span data-ttu-id="b51a1-159">如果 Windows 安全区域策略配置为禁用“启动应用程序和不安全文件”设置，则 Microsoft Edge 下载管理器将阻止从该区域中的站点下载文件，并附注:“无法下载 – 已阻止”。</span><span class="sxs-lookup"><span data-stu-id="b51a1-159">If the Windows Security Zone policy is configured to Disable the setting Launching applications and unsafe files, the Microsoft Edge download manager will block file downloads from sites in that Zone with a note: “Couldn’t download – Blocked.”</span></span>  

## <a name="ie-mode"></a><span data-ttu-id="b51a1-160">IE 模式</span><span class="sxs-lookup"><span data-stu-id="b51a1-160">IE mode</span></span>

<span data-ttu-id="b51a1-161">可以将 IE 模式配置为  [在 IE 模式下打开所有 Intranet 站点](/deployedge/edge-ie-mode#configure-all-intranet-sites)。</span><span class="sxs-lookup"><span data-stu-id="b51a1-161">IE mode can be configured to [open all Intranet sites in IE mode](/deployedge/edge-ie-mode#configure-all-intranet-sites).</span></span> <span data-ttu-id="b51a1-162">在此配置中，Edge 在决定是否应在 IE 模式下打开时评估 URL 的区域。</span><span class="sxs-lookup"><span data-stu-id="b51a1-162">When in this configuration, Edge evaluates the Zone of a URL when deciding whether or not it should open in IE mode.</span></span> <span data-ttu-id="b51a1-163">除了此初始决策之外，IE 模式选项卡实际上正在运行Internet Explorer，因此它们会像 Internet Explorer 本身一样评估每个策略决策的区域设置。</span><span class="sxs-lookup"><span data-stu-id="b51a1-163">Beyond this initial decision, IE mode tabs are really running Internet Explorer, and as a consequence they evaluate Zones settings for every policy decision just as Internet Explorer itself did.</span></span>

## <a name="summary"></a><span data-ttu-id="b51a1-164">摘要</span><span class="sxs-lookup"><span data-stu-id="b51a1-164">Summary</span></span>

<span data-ttu-id="b51a1-165">在大多数情况下，Microsoft Edge 设置可以保留为默认值。</span><span class="sxs-lookup"><span data-stu-id="b51a1-165">In most cases, Microsoft Edge settings can be left at their defaults.</span></span> <span data-ttu-id="b51a1-166">希望更改所有站点或特定站点默认值的管理员可以使用相应的组策略来指定站点列表或默认行为。</span><span class="sxs-lookup"><span data-stu-id="b51a1-166">Administrators who wish to change the defaults for all sites or specific sites can use the appropriate Group Policies to specify Site Lists or default behaviors.</span></span> <span data-ttu-id="b51a1-167">在少数情况下 (凭据释放、文件下载和 IE 模式)，管理员将继续通过配置 Windows 安全区域设置来控制行为。</span><span class="sxs-lookup"><span data-stu-id="b51a1-167">In a handful of cases (credential release, file download, and IE mode), administrators will continue to control behavior by configuring Windows Security Zones settings.</span></span>
