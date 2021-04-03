---
title: 配置 IE 模式策略
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 03/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 配置 IE 模式策略
ms.openlocfilehash: a2abf6f6ef71c1f30786031ef19b9633bfafc43f
ms.sourcegitcommit: 93851b83dc11422924646a04a9e0f60ff2554af7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470160"
---
# <a name="configure-ie-mode-policies"></a><span data-ttu-id="b0ace-103">配置 IE 模式策略</span><span class="sxs-lookup"><span data-stu-id="b0ace-103">Configure IE mode policies</span></span>

<span data-ttu-id="b0ace-104">本文介绍了如何配置 IE 模式策略。</span><span class="sxs-lookup"><span data-stu-id="b0ace-104">This article explains how to configure IE mode policies.</span></span>

> [!NOTE]
> <span data-ttu-id="b0ace-105">本文适用于 Microsoft Edge **Stable**、**Beta** 和 **Dev** 渠道版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="b0ace-105">This article applies to Microsoft Edge **Stable**, **Beta** and **Dev** Channels, version 77 or later.</span></span>

<span data-ttu-id="b0ace-106">若要配置 IE 模式，需要完成以下三步：</span><span class="sxs-lookup"><span data-stu-id="b0ace-106">Configuring IE mode requires three steps:</span></span>

1. [<span data-ttu-id="b0ace-107">配置 Internet Explorer 集成</span><span class="sxs-lookup"><span data-stu-id="b0ace-107">Configure Internet Explorer integration</span></span>](#configure-internet-explorer-integration)
2. [<span data-ttu-id="b0ace-108">将网站从 Microsoft Edge 重定向到 IE 模式</span><span class="sxs-lookup"><span data-stu-id="b0ace-108">Redirect sites from Microsoft Edge to IE mode</span></span>](#redirect-sites-from-microsoft-edge-to-ie-mode)
3. <span data-ttu-id="b0ace-109">（可选）[将网站从 IE 重定向到 Microsoft Edge](#redirect-sites-from-ie-to-microsoft-edge)</span><span class="sxs-lookup"><span data-stu-id="b0ace-109">(Optional) [Redirect sites from IE to Microsoft Edge](#redirect-sites-from-ie-to-microsoft-edge)</span></span>

    1. <span data-ttu-id="b0ace-110">如果已准备好禁用 IE11 应用，请按照 [禁用 Internet Explorer 11 应用"中的步骤](https://docs.microsoft.com/deployedge/edge-ie-disable-ie11)</span><span class="sxs-lookup"><span data-stu-id="b0ace-110">If you are ready to disable the IE11 app, follow the steps in [Disable Internet Explorer 11](https://docs.microsoft.com/deployedge/edge-ie-disable-ie11)</span></span>
    2. <span data-ttu-id="b0ace-111">否则，请按照"将网站从 IE 重定向到 Microsoft Edge [中的其余步骤](https://docs.microsoft.com/deployedge/edge-ie-mode-policies#redirect-sites-from-ie-to-microsoft-edge)</span><span class="sxs-lookup"><span data-stu-id="b0ace-111">Otherwise,  follow the rest of the steps in [Redirect sites from IE to Microsoft Edge](https://docs.microsoft.com/deployedge/edge-ie-mode-policies#redirect-sites-from-ie-to-microsoft-edge)</span></span>

> [!NOTE]
> <span data-ttu-id="b0ace-112">可通过 Intune 来配置启用 IE 模式的策略。</span><span class="sxs-lookup"><span data-stu-id="b0ace-112">Policies to enable IE mode can be configured through Intune.</span></span> <span data-ttu-id="b0ace-113">有关详细信息，请参阅[将 Microsoft Edge 添加到 Microsoft Intune](/intune/apps/apps-windows-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)和[使用 Microsoft Intune 配置 Microsoft Edge 策略](./configure-edge-with-intune.md)。</span><span class="sxs-lookup"><span data-stu-id="b0ace-113">For more information, see [Add Microsoft Edge to Microsoft Intune](/intune/apps/apps-windows-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json) and [Configure Microsoft Edge policies with Microsoft Intune](./configure-edge-with-intune.md).</span></span>

## <a name="configure-internet-explorer-integration"></a><span data-ttu-id="b0ace-114">配置 Internet Explorer 集成</span><span class="sxs-lookup"><span data-stu-id="b0ace-114">Configure Internet Explorer integration</span></span>

<span data-ttu-id="b0ace-115">可以将 Internet Explorer 配置为，直接在 Microsoft Edge（IE 模式）中打开。</span><span class="sxs-lookup"><span data-stu-id="b0ace-115">You can configure Internet Explorer to open directly within Microsoft Edge (IE mode).</span></span> <span data-ttu-id="b0ace-116">也可以将 Internet Explorer 配置为，使用独立 Internet Explorer 11 窗口打开。</span><span class="sxs-lookup"><span data-stu-id="b0ace-116">You can also configure Internet Explorer to open with a standalone Internet Explorer 11 window.</span></span> <span data-ttu-id="b0ace-117">大多数用户倾向于直接在 Microsoft Edge 的 IE 模式下打开网站。</span><span class="sxs-lookup"><span data-stu-id="b0ace-117">Most users prefer when sites open directly within Microsoft Edge in IE mode.</span></span>

### <a name="enable-internet-explorer-integration-using-group-policy"></a><span data-ttu-id="b0ace-118">使用组策略启用 Internet Explorer 集成</span><span class="sxs-lookup"><span data-stu-id="b0ace-118">Enable Internet Explorer integration using Group Policy</span></span>

1. <span data-ttu-id="b0ace-119">下载并使用最新的 [Microsoft Edge 策略模板](https://www.microsoft.com/en-us/edge/business/download)。</span><span class="sxs-lookup"><span data-stu-id="b0ace-119">Download and use the latest [Microsoft Edge Policy Template](https://www.microsoft.com/en-us/edge/business/download).</span></span>
2. <span data-ttu-id="b0ace-120">组策略编辑器。</span><span class="sxs-lookup"><span data-stu-id="b0ace-120">Open Group Policy Editor.</span></span>
3. <span data-ttu-id="b0ace-121">单击**计算机配置** > **管理模板** > **Microsoft Edge**。</span><span class="sxs-lookup"><span data-stu-id="b0ace-121">Click **Computer Configuration** > **Administrative Templates** > **Microsoft Edge**.</span></span>
4. <span data-ttu-id="b0ace-122">双击**配置 Internet Explorer 集成**。</span><span class="sxs-lookup"><span data-stu-id="b0ace-122">Double-click **Configure Internet Explorer integration**.</span></span>
5. <span data-ttu-id="b0ace-123">选中**已启用**。</span><span class="sxs-lookup"><span data-stu-id="b0ace-123">Select **Enabled**.</span></span>
6. <span data-ttu-id="b0ace-124">在**选项**下，将下拉列表值设置为</span><span class="sxs-lookup"><span data-stu-id="b0ace-124">Under **Options**, set the dropdown value to</span></span> 
   -  <span data-ttu-id="b0ace-125">**Internet Explorer 模式**：如果希望在 Microsoft Edge 中的 IE 模式下打开网站</span><span class="sxs-lookup"><span data-stu-id="b0ace-125">**Internet Explorer mode** if you want sites to open in IE mode on Microsoft Edge</span></span>
   -  <span data-ttu-id="b0ace-126">**Internet Explorer 11**（如果希望在独立的 Internet Explorer 11 窗口中打开网站）</span><span class="sxs-lookup"><span data-stu-id="b0ace-126">**Internet Explorer 11** if you want sites to open in a standalone Internet Explorer 11 window</span></span>
   -  <span data-ttu-id="b0ace-127">**无**：如果希望阻止用户通过 edge://flags 或命令行来配置 Internet Explorer 模式</span><span class="sxs-lookup"><span data-stu-id="b0ace-127">**None** if you want to stop users from configuring Internet Explorer mode via edge://flags or through the command line</span></span>

   > [!NOTE]
   > <span data-ttu-id="b0ace-128">将策略设置为**禁用**意味着 IE 模式已由策略禁用，但可以通过 edge://flags 或命令行选项进行设置。</span><span class="sxs-lookup"><span data-stu-id="b0ace-128">Setting the policy to **Disabled** implies IE mode is disabled by policy, but can be set through edge://flags or command line options.</span></span>
7. <span data-ttu-id="b0ace-129">单击**确定**或**应用**以保存此策略设置。</span><span class="sxs-lookup"><span data-stu-id="b0ace-129">Click **OK** or **Apply** to save this policy setting.</span></span>

## <a name="redirect-sites-from-microsoft-edge-to-ie-mode"></a><span data-ttu-id="b0ace-130">将网站从 Microsoft Edge 重定向到 IE 模式</span><span class="sxs-lookup"><span data-stu-id="b0ace-130">Redirect sites from Microsoft Edge to IE mode</span></span>

<span data-ttu-id="b0ace-131">若要识别应在 IE 模式下打开的网站，可以使用以下两种方法：</span><span class="sxs-lookup"><span data-stu-id="b0ace-131">There are two options for identifying which sites should open in IE mode:</span></span>

- <span data-ttu-id="b0ace-132">（推荐）[配置企业站点列表中的站点](#configure-sites-on-the-enterprise-site-list)</span><span class="sxs-lookup"><span data-stu-id="b0ace-132">(Recommended) [Configure sites on the Enterprise Site list](#configure-sites-on-the-enterprise-site-list)</span></span>
- [<span data-ttu-id="b0ace-133">配置所有 Intranet 站点</span><span class="sxs-lookup"><span data-stu-id="b0ace-133">Configure all Intranet sites</span></span>](#configure-all-intranet-sites)

### <a name="configure-sites-on-the-enterprise-site-list"></a><span data-ttu-id="b0ace-134">配置企业站点列表中的站点</span><span class="sxs-lookup"><span data-stu-id="b0ace-134">Configure sites on the Enterprise Site list</span></span>

<span data-ttu-id="b0ace-135">你可以使用以下组策略配置要在 IE 模式下打开的特定站点：</span><span class="sxs-lookup"><span data-stu-id="b0ace-135">You can use the following group policies to configure specific sites to open in IE mode:</span></span>

- <span data-ttu-id="b0ace-136">[使用企业模式 IE 网站列表](#configure-using-the-use-the-enterprise-mode-ie-website-list-policy) (Internet Explorer)</span><span class="sxs-lookup"><span data-stu-id="b0ace-136">[Use the Enterprise Mode IE website list](#configure-using-the-use-the-enterprise-mode-ie-website-list-policy) (Internet Explorer)</span></span>
- <span data-ttu-id="b0ace-137">[配置企业模式站点列表](#configure-using-the-configure-the-enterprise-mode-site-list-policy)（Microsoft Edge 78 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="b0ace-137">[Configure the Enterprise Mode Site List](#configure-using-the-configure-the-enterprise-mode-site-list-policy) (Microsoft Edge, version 78 or later)</span></span><br/><span data-ttu-id="b0ace-138">使用此策略，可以为 Microsoft Edge 单独创建 Enterprise Mode Site List。</span><span class="sxs-lookup"><span data-stu-id="b0ace-138">This policy lets you create a separate Enterprise Mode Site list for Microsoft Edge.</span></span> <span data-ttu-id="b0ace-139">如果“配置 Internet Explorer 集成”已启用，那么启用此策略会重写“使用企业模式 IE 网站列表”策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="b0ace-139">Enabling this policy overrides the settings in the "Use the Enterprise Mode IE website list" policy, if "Configure Internet Explorer integration" is enabled.</span></span> <span data-ttu-id="b0ace-140">禁用或未配置此策略不会影响“配置 Internet Explorer 集成”策略的默认行为。</span><span class="sxs-lookup"><span data-stu-id="b0ace-140">Disabling or not configuring this policy doesn't affect the default behavior of the "Configure Internet Explorer integration" policy.</span></span>
    > [!NOTE]
    > <span data-ttu-id="b0ace-141">配置 Microsoft Edge 策略并不是一项强制性要求。</span><span class="sxs-lookup"><span data-stu-id="b0ace-141">It is not mandatory to configure the Microsoft Edge policy.</span></span> <span data-ttu-id="b0ace-142">许多组织将此策略用于重写目的，便于他们使用 IE 策略将当前网站列表定位到所有用户，并使用 Microsoft Edge 策略更轻松地将更新后的版本定位到试点网站用户。</span><span class="sxs-lookup"><span data-stu-id="b0ace-142">Many organizations use this as an override, allowing them to target the current Site List at all users with the IE policy, and more easily target an updated version to pilot uses with the Microsoft Edge policy.</span></span>

<span data-ttu-id="b0ace-143">有关企业模式站点列表的更多信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="b0ace-143">For more information about Enterprise Mode Site lists, see:</span></span>

- [<span data-ttu-id="b0ace-144">使用 Enterprise Mode Site List Manager</span><span class="sxs-lookup"><span data-stu-id="b0ace-144">Use the Enterprise Mode Site List Manager</span></span>](/internet-explorer/ie11-deploy-guide/use-the-enterprise-mode-site-list-manager)
- <span data-ttu-id="b0ace-145">[使用文件和 Enterprise Mode Site List Manager（架构 v.2）将多个站点添加到企业模式站点列表](/internet-explorer/ie11-deploy-guide/add-multiple-sites-to-enterprise-mode-site-list-using-the-version-2-schema-and-enterprise-mode-tool)。</span><span class="sxs-lookup"><span data-stu-id="b0ace-145">[Add multiple sites to the Enterprise Mode site list using a file and the Enterprise Mode Site List Manager (schema v.2)](/internet-explorer/ie11-deploy-guide/add-multiple-sites-to-enterprise-mode-site-list-using-the-version-2-schema-and-enterprise-mode-tool).</span></span>

### <a name="configure-using-the-use-the-enterprise-mode-ie-website-list-policy"></a><span data-ttu-id="b0ace-146">使用“使用企业模式 IE 网站列表”策略进行配置</span><span class="sxs-lookup"><span data-stu-id="b0ace-146">Configure using the Use the Enterprise Mode IE website list policy</span></span>

<span data-ttu-id="b0ace-147">IE 模式可使用为 Internet Explorer 配置 Enterprise Site List 的现有策略，这样你就能创建和维护一个列表了。</span><span class="sxs-lookup"><span data-stu-id="b0ace-147">IE mode can use the existing policy configuring the Enterprise Site List for Internet Explorer, allowing you to create and maintain a single list.</span></span>

1. <span data-ttu-id="b0ace-148">创建或重用 Site List XML</span><span class="sxs-lookup"><span data-stu-id="b0ace-148">Create or reuse a Site List XML</span></span>
    1. <span data-ttu-id="b0ace-149">所有具有 _\<open-in\>IE11\</open-in\>_ 元素的站点现在都将在 IE 模式下打开。</span><span class="sxs-lookup"><span data-stu-id="b0ace-149">All sites that have the element _\<open-in\>IE11\</open-in\>_ will now open in IE mode.</span></span>
2. <span data-ttu-id="b0ace-150">组策略编辑器。</span><span class="sxs-lookup"><span data-stu-id="b0ace-150">Open Group Policy Editor.</span></span>
3. <span data-ttu-id="b0ace-151">单击**计算机配置** > **管理模板** > **Windows 组件** > **Internet Explorer**。</span><span class="sxs-lookup"><span data-stu-id="b0ace-151">Click **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Internet Explorer**.</span></span>
4. <span data-ttu-id="b0ace-152">双击**使用企业模式 IE 网站列表**。</span><span class="sxs-lookup"><span data-stu-id="b0ace-152">Double-click **Use the Enterprise Mode IE website list**.</span></span>
5. <span data-ttu-id="b0ace-153">选中**已启用**。</span><span class="sxs-lookup"><span data-stu-id="b0ace-153">Select **Enabled**.</span></span>
6. <span data-ttu-id="b0ace-154">在**选项**下，键入网站列表的位置。</span><span class="sxs-lookup"><span data-stu-id="b0ace-154">Under **Options**, type the location of website list.</span></span> <span data-ttu-id="b0ace-155">可以使用以下位置之一：</span><span class="sxs-lookup"><span data-stu-id="b0ace-155">You can use one of the following locations:</span></span>
    - <span data-ttu-id="b0ace-156">（推荐）HTTPS 位置：https\*\*\*\*://iemode/sites.xml\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b0ace-156">(Recommended) HTTPS location: **https**:**//iemode/sites.xml**</span></span>
    - <span data-ttu-id="b0ace-157">本地网络文件：**\\\network\shares\sites.xml**</span><span class="sxs-lookup"><span data-stu-id="b0ace-157">Local network file: **\\\network\shares\sites.xml**</span></span>
    - <span data-ttu-id="b0ace-158">本地文件：**file:///c:/Users/\<user\>/Documents/sites.xml**</span><span class="sxs-lookup"><span data-stu-id="b0ace-158">Local file: **file:///c:/Users/\<user\>/Documents/sites.xml**</span></span>
7. <span data-ttu-id="b0ace-159">单击**确定**或**应用**以保存这些设置。</span><span class="sxs-lookup"><span data-stu-id="b0ace-159">Click **OK** or **Apply** to save these settings.</span></span>

### <a name="configure-using-the-configure-the-enterprise-mode-site-list-policy"></a><span data-ttu-id="b0ace-160">使用“配置 Enterprise Mode Site List”策略进行配置</span><span class="sxs-lookup"><span data-stu-id="b0ace-160">Configure using the Configure the Enterprise Mode Site List policy</span></span>

<span data-ttu-id="b0ace-161">也可以使用单独的 Microsoft Edge 策略来配置 IE 模式。</span><span class="sxs-lookup"><span data-stu-id="b0ace-161">You can also configure IE mode with a separate policy for Microsoft Edge.</span></span> <span data-ttu-id="b0ace-162">使用此附加策略，可以重写 IE 网站列表。</span><span class="sxs-lookup"><span data-stu-id="b0ace-162">This additional policy allows you to override the IE site list.</span></span> <span data-ttu-id="b0ace-163">例如，一些组织会将生产网站列表定位到所有用户。</span><span class="sxs-lookup"><span data-stu-id="b0ace-163">For example, some organizations will target the production site list to all users.</span></span> <span data-ttu-id="b0ace-164">然后，你可以使用此策略将试点网站列表部署到一小组用户。</span><span class="sxs-lookup"><span data-stu-id="b0ace-164">You can then deploy the pilot site list to a small group of users using this policy.</span></span>

1. <span data-ttu-id="b0ace-165">创建或重用 Site List XML</span><span class="sxs-lookup"><span data-stu-id="b0ace-165">Create or reuse a Site List XML</span></span>
    1. <span data-ttu-id="b0ace-166">所有具有 _\<open-in\>IE11\</open-in\>_ 元素的站点现在都将在 IE 模式下打开。</span><span class="sxs-lookup"><span data-stu-id="b0ace-166">All sites that have the element _\<open-in\>IE11\</open-in\>_ will now open in IE mode.</span></span>
2. <span data-ttu-id="b0ace-167">组策略编辑器。</span><span class="sxs-lookup"><span data-stu-id="b0ace-167">Open Group Policy Editor.</span></span>
3. <span data-ttu-id="b0ace-168">单击**计算机配置** > **管理模板** > **Microsoft Edge**。</span><span class="sxs-lookup"><span data-stu-id="b0ace-168">Click **Computer Configuration** > **Administrative Templates** > **Microsoft Edge**.</span></span>
4. <span data-ttu-id="b0ace-169">双击**配置企业模式站点列表**。</span><span class="sxs-lookup"><span data-stu-id="b0ace-169">Double-click **Configure the Enterprise Mode Site List**.</span></span>
5. <span data-ttu-id="b0ace-170">选中**已启用**。</span><span class="sxs-lookup"><span data-stu-id="b0ace-170">Select **Enabled**.</span></span>
6. <span data-ttu-id="b0ace-171">在**选项**下，键入网站列表的位置。</span><span class="sxs-lookup"><span data-stu-id="b0ace-171">Under **Options**, type the location of website list.</span></span> <span data-ttu-id="b0ace-172">可以使用以下位置之一：</span><span class="sxs-lookup"><span data-stu-id="b0ace-172">You can use one of the following locations:</span></span>
    - <span data-ttu-id="b0ace-173">（推荐）HTTPS 位置：https\*\*\*\*://iemode/sites.xml\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b0ace-173">(Recommended) HTTPS location: **https**:**//iemode/sites.xml**</span></span> <!--Trying to keep this from being an active link in MD -->
    - <span data-ttu-id="b0ace-174">本地网络文件：**\\\network\shares\sites.xml**</span><span class="sxs-lookup"><span data-stu-id="b0ace-174">Local network file: **\\\network\shares\sites.xml**</span></span>
    - <span data-ttu-id="b0ace-175">本地文件：**file:///c:/Users/\<user\>/Documents/sites.xml**</span><span class="sxs-lookup"><span data-stu-id="b0ace-175">Local file: **file:///c:/Users/\<user\>/Documents/sites.xml**</span></span>
7. <span data-ttu-id="b0ace-176">单击**确定**或**应用**以保存这些设置。</span><span class="sxs-lookup"><span data-stu-id="b0ace-176">Click **OK** or **Apply** to save these settings.</span></span>

### <a name="configure-all-intranet-sites"></a><span data-ttu-id="b0ace-177">配置所有 Intranet 站点</span><span class="sxs-lookup"><span data-stu-id="b0ace-177">Configure all intranet sites</span></span>

<span data-ttu-id="b0ace-178">可以将 IE 模式配置为，用于本地 Intranet 区域中的所有网站。</span><span class="sxs-lookup"><span data-stu-id="b0ace-178">IE mode can be configured as for all sites in the Local Intranet zone.</span></span> <span data-ttu-id="b0ace-179">可以使用 Enterprise Mode Site List 从 IE 模式中删除各个网站。</span><span class="sxs-lookup"><span data-stu-id="b0ace-179">You can remove individual sites from IE mode using an Enterprise Mode Site List.</span></span>

>[!NOTE]
>
> <span data-ttu-id="b0ace-180">本地 Intranet 区域不但包含显式添加的网站，还分配有通过启发分配到此区域的网站。</span><span class="sxs-lookup"><span data-stu-id="b0ace-180">The Local Intranet zone contains explicitly added sites, but also assigns sites to this zone using heuristics.</span></span> <span data-ttu-id="b0ace-181">这可以包括无点主机名（例如，https\*\*\*\*://payroll\*\*\*\*），以及代理配置脚本配置为不使用代理的网站。</span><span class="sxs-lookup"><span data-stu-id="b0ace-181">This can include dotless host names (e.g. **https**:**//payroll**) and sites that the proxy configuration script configures to bypass the proxy.</span></span> <span data-ttu-id="b0ace-182">如果外部参与方控制 DNS 或代理，它们可能会强制让网站在 IE 模式下运行。</span><span class="sxs-lookup"><span data-stu-id="b0ace-182">If an external party controls DNS or proxy, they could potentially force websites into IE mode.</span></span>

1. <span data-ttu-id="b0ace-183">打开本地组策略编辑器。</span><span class="sxs-lookup"><span data-stu-id="b0ace-183">Open Local Group Policy Editor.</span></span>
2. <span data-ttu-id="b0ace-184">单击**计算机配置** > **管理模板** > **Microsoft Edge**。</span><span class="sxs-lookup"><span data-stu-id="b0ace-184">Click **Computer Configuration** > **Administrative Templates** > **Microsoft Edge**.</span></span>
3. <span data-ttu-id="b0ace-185">双击**将所有 Intranet 站点都发送到 Internet Explorer**。</span><span class="sxs-lookup"><span data-stu-id="b0ace-185">Double-click **Send all intranet sites to Internet Explorer**.</span></span>
4. <span data-ttu-id="b0ace-186">选择**已启用**，然后单击**确定**或**应用**以保存策略设置。</span><span class="sxs-lookup"><span data-stu-id="b0ace-186">Select **Enabled**, and then click **OK** or **Apply** to save the policy settings.</span></span>

## <a name="redirect-sites-from-ie-to-microsoft-edge"></a><span data-ttu-id="b0ace-187">将网站从 IE 重定向到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b0ace-187">Redirect sites from IE to Microsoft Edge</span></span>

<span data-ttu-id="b0ace-188">可以阻止用户使用 Internet Explorer 浏览不需要 IE 模式的网站。</span><span class="sxs-lookup"><span data-stu-id="b0ace-188">You can prevent your users from using Internet Explorer for sites that don't need it.</span></span> <span data-ttu-id="b0ace-189">Internet Explorer 可自动将网站列表中没有的网站重定向到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="b0ace-189">Internet Explorer can automatically redirect sites to Microsoft Edge if they aren't on your site list.</span></span>

1. <span data-ttu-id="b0ace-190">组策略编辑器。</span><span class="sxs-lookup"><span data-stu-id="b0ace-190">Open Group Policy Editor.</span></span>
2. <span data-ttu-id="b0ace-191">依次单击“计算机配置”\*\*\*\* > “管理工具”\*\*\*\* > “Windows 组件”\*\*\*\* > “Internet Explorer”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0ace-191">Click **Computer Configuration** > **Administrative Tools** > **Windows Components** > **Internet Explorer**.</span></span>
3. <span data-ttu-id="b0ace-192">双击“将 Enterprise Mode Site List 中不包含的所有网站发送到 Microsoft Edge”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0ace-192">Double-click **Send all sites not included in the Enterprise Mode Site List to Microsoft Edge.**</span></span>
4. <span data-ttu-id="b0ace-193">选中“已启用”\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b0ace-193">Select **Enabled**</span></span>
5. <span data-ttu-id="b0ace-194">单击**确定**或**应用**以保存这些设置。</span><span class="sxs-lookup"><span data-stu-id="b0ace-194">Click **OK** or **Apply** to save these settings.</span></span>
6. <span data-ttu-id="b0ace-195">双击“配置要用于打开重定向网站的 Microsoft Edge 渠道”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0ace-195">Double-click **Configure which channel of Microsoft Edge to use for opening redirected sites**.</span></span>
7. <span data-ttu-id="b0ace-196">选中**已启用**。</span><span class="sxs-lookup"><span data-stu-id="b0ace-196">Select **Enabled**.</span></span>
8. <span data-ttu-id="b0ace-197">在“选项”\*\*\*\* 下，选择要使用的前三个渠道选项，Internet Explorer 会重定向到用户在相应设备上安装的排名最靠前的选项：</span><span class="sxs-lookup"><span data-stu-id="b0ace-197">Under **Options**, select your top three choices for the channel to use - Internet Explorer will redirect to the highest ranked choice that the user has installed on that device:</span></span>
   - <span data-ttu-id="b0ace-198">Microsoft Edge 稳定渠道</span><span class="sxs-lookup"><span data-stu-id="b0ace-198">Microsoft Edge Stable</span></span>
   - <span data-ttu-id="b0ace-199">Microsoft Edge Beta 版本 77 或更高版本</span><span class="sxs-lookup"><span data-stu-id="b0ace-199">Microsoft Edge Beta version 77 or later</span></span>
   - <span data-ttu-id="b0ace-200">Microsoft Edge Dev 版本 77 或更高版本</span><span class="sxs-lookup"><span data-stu-id="b0ace-200">Microsoft Edge Dev version 77 or later</span></span>
   - <span data-ttu-id="b0ace-201">Microsoft Edge Canary 版本 77 或更高版本</span><span class="sxs-lookup"><span data-stu-id="b0ace-201">Microsoft Edge Canary version 77 or later</span></span>
   - <span data-ttu-id="b0ace-202">Microsoft Edge 版本 45 或更低版本</span><span class="sxs-lookup"><span data-stu-id="b0ace-202">Microsoft Edge version 45 or earlier</span></span>
9. <span data-ttu-id="b0ace-203">单击**确定**或**应用**以保存这些设置。</span><span class="sxs-lookup"><span data-stu-id="b0ace-203">Click **OK** or **Apply** to save these settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0ace-204">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0ace-204">See also</span></span>

- [<span data-ttu-id="b0ace-205">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="b0ace-205">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="b0ace-206">关于 IE 模式</span><span class="sxs-lookup"><span data-stu-id="b0ace-206">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="b0ace-207">其他企业模式信息</span><span class="sxs-lookup"><span data-stu-id="b0ace-207">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)