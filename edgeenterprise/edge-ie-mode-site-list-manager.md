---
title: 'Microsoft Edge 中的 Enterprise Site List Manager '
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 01/20/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: '启用并使用 Microsoft Edge 中的 Enterprise Site List Manager '
ms.openlocfilehash: 2d10886624918c97933a841c428ea66ccf5b34c9
ms.sourcegitcommit: a6c58b19976c194299be217c58b9a99b48756fd0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11281042"
---
# <span data-ttu-id="5cc67-103">Microsoft Edge 中的 Enterprise Site List Manager</span><span class="sxs-lookup"><span data-stu-id="5cc67-103">Enterprise Site List Manager in Microsoft Edge</span></span>

<span data-ttu-id="5cc67-104">本文介绍如何启用和访问 Microsoft Edge 中的 Enterprise Site List Manager 以创建、编辑和导出 Internet Explorer 模式的 Enterprise Mode Site List。</span><span class="sxs-lookup"><span data-stu-id="5cc67-104">This article explains how to enable access to and use the Enterprise Site List Manager in Microsoft Edge to create, edit and export your Enterprise Mode Site List for Internet Explorer mode.</span></span>

> [!NOTE]
> <span data-ttu-id="5cc67-105">本文适用于 Microsoft Edge 版本 89 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="5cc67-105">This article applies to Microsoft Edge version 89 or later.</span></span>

## <span data-ttu-id="5cc67-106">概述</span><span class="sxs-lookup"><span data-stu-id="5cc67-106">Overview</span></span>

<span data-ttu-id="5cc67-107">Enterprise Site List Manager 是[独立 Enterprise Mode Site List Manager 工具](https://www.microsoft.com/download/details.aspx?id=49974)的浏览器内版本，可让创建、编辑和导出组织的站点列表。</span><span class="sxs-lookup"><span data-stu-id="5cc67-107">The Enterprise Site List Manager is an in-browser version of the [standalone Enterprise Mode Site List Manager tool](https://www.microsoft.com/download/details.aspx?id=49974) that lets you create, edit, and export your organization’s site list.</span></span>

<span data-ttu-id="5cc67-108">通过 Microsoft Edge 中的 Enterprise Site List Manager，可以进一步改进用于 Internet Explorer 模式的工具。</span><span class="sxs-lookup"><span data-stu-id="5cc67-108">Future improvements to the tool for Internet Explorer mode will be available through Enterprise Site List Manager in Microsoft Edge.</span></span> <span data-ttu-id="5cc67-109">独立工具将继续在下载中心中提供，但无法获得任何功能更新。</span><span class="sxs-lookup"><span data-stu-id="5cc67-109">The standalone tool will continue to be available in the Download Center but won't get any feature updates.</span></span>

## <span data-ttu-id="5cc67-110">允许访问 Enterprise Site List Manager</span><span class="sxs-lookup"><span data-stu-id="5cc67-110">Enabling access to Enterprise Site List Manager</span></span>

<span data-ttu-id="5cc67-111">可以使用 [EnterpriseModeSiteListManagerAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enterprisemodesitelistmanagerallowed) 组策略配置对工具的访问权限。</span><span class="sxs-lookup"><span data-stu-id="5cc67-111">You can configure access to the tool by using the [EnterpriseModeSiteListManagerAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enterprisemodesitelistmanagerallowed) group policy.</span></span>

<span data-ttu-id="5cc67-112">如果启用，用户将在 *edge://compat* 的左侧导航窗格中看到一个名为 Enterprise Site List Manager 的选项。</span><span class="sxs-lookup"><span data-stu-id="5cc67-112">If enabled, your users will see an option named Enterprise Site List Manager on the left navigation pane in *edge://compat*.</span></span> <span data-ttu-id="5cc67-113">如果禁用，用户将不会在左侧导航窗格中看到 Enterprise Site List Manager 的入口点。</span><span class="sxs-lookup"><span data-stu-id="5cc67-113">If Disabled, users will not see the entry point to Enterprise Site List Manager in the left navigation pane.</span></span> <span data-ttu-id="5cc67-114">这是默认行为。</span><span class="sxs-lookup"><span data-stu-id="5cc67-114">This is the default behavior.</span></span>

## <span data-ttu-id="5cc67-115">使用 Enterprise Site List Manager</span><span class="sxs-lookup"><span data-stu-id="5cc67-115">Using the Enterprise Site List Manager</span></span>

<span data-ttu-id="5cc67-116">Enterprise Site List Manager 工具使用 v.2 版本的架构。</span><span class="sxs-lookup"><span data-stu-id="5cc67-116">The Enterprise Site List Manager tool uses the v.2 version of the schema.</span></span> <span data-ttu-id="5cc67-117">如果将 v.1 版本架构导入到 Enterprise Site List Manager（架构 v.2）中，XML 将被保存到 v.2 版本的架构。</span><span class="sxs-lookup"><span data-stu-id="5cc67-117">If you import a v.1 version schema into the Enterprise Site List Manager (schema v.2), the XML is saved into the v.2 version of the schema.</span></span>

### <span data-ttu-id="5cc67-118">将单个站点添加到站点列表</span><span class="sxs-lookup"><span data-stu-id="5cc67-118">Add single sites to your site list</span></span>  

<span data-ttu-id="5cc67-119">使用以下步骤将单个站点添加到站点列表。</span><span class="sxs-lookup"><span data-stu-id="5cc67-119">Use the following steps to add individual sites to your site list.</span></span>

> [!NOTE]
> <span data-ttu-id="5cc67-120">你只能添加特定的 URL，而无法添加 Internet 或 Intranet 区域。</span><span class="sxs-lookup"><span data-stu-id="5cc67-120">You can only add specific URLs, not Internet or Intranet Zones.</span></span>

1. <span data-ttu-id="5cc67-121">在 Enterprise Site List Manager 中，单击“ **添加站点**”。</span><span class="sxs-lookup"><span data-stu-id="5cc67-121">In the Enterprise Site List Manager, click **Add a site**.</span></span>
2. <span data-ttu-id="5cc67-122">在 URL 框中输入要添加的站点网址，例如： <domain>.com or <domain>.com/<path> 。</span><span class="sxs-lookup"><span data-stu-id="5cc67-122">Type the URL for the website you’d like to add, for example: <domain>.com or <domain>.com/<path> in the URL box.</span></span>
3. <span data-ttu-id="5cc67-123">从“**打开方式**” 列表中选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="5cc67-123">Select one of the following options from the **Open in** list:</span></span>

   - <span data-ttu-id="5cc67-124">**IE11**。</span><span class="sxs-lookup"><span data-stu-id="5cc67-124">**IE11**.</span></span> <span data-ttu-id="5cc67-125">在 IE11 应用程序中打开站点。</span><span class="sxs-lookup"><span data-stu-id="5cc67-125">Opens the site in the IE11 application.</span></span>
   - <span data-ttu-id="5cc67-126">**IE 模式**。</span><span class="sxs-lookup"><span data-stu-id="5cc67-126">**IE mode**.</span></span> <span data-ttu-id="5cc67-127">如果启用，在 Microsoft Edge 的 Internet Explorer 模式中打开站点，否则在 IE11 应用中打开站点。</span><span class="sxs-lookup"><span data-stu-id="5cc67-127">Opens the site in Internet Explorer mode on Microsoft Edge if enabled and in the IE11 app otherwise.</span></span> <span data-ttu-id="5cc67-128">请参阅  [Microsoft Edge 上的 Internet Explorer 模式 ](https://docs.microsoft.com/deployedge/edge-ie-mode)。</span><span class="sxs-lookup"><span data-stu-id="5cc67-128">See [Internet Explorer mode on Microsoft Edge](https://docs.microsoft.com/deployedge/edge-ie-mode).</span></span>
   - <span data-ttu-id="5cc67-129">**MSEdge**。</span><span class="sxs-lookup"><span data-stu-id="5cc67-129">**MSEdge**.</span></span> <span data-ttu-id="5cc67-130">在 Microsoft Edge 中打开站点。</span><span class="sxs-lookup"><span data-stu-id="5cc67-130">Opens the site in Microsoft Edge.</span></span>
   - <span data-ttu-id="5cc67-131">**可配置**。</span><span class="sxs-lookup"><span data-stu-id="5cc67-131">**Configurable**.</span></span> <span data-ttu-id="5cc67-132">允许站点参与 IE 模式引擎确定。</span><span class="sxs-lookup"><span data-stu-id="5cc67-132">Allows the site to participate in IE mode engine determination.</span></span> <span data-ttu-id="5cc67-133">参见 [IE 模式下可配置的站点](https://docs.microsoft.com/deployedge/edge-learnmore-configurable-sites-ie-mode)</span><span class="sxs-lookup"><span data-stu-id="5cc67-133">See [Configurable sites in IE mode](https://docs.microsoft.com/deployedge/edge-learnmore-configurable-sites-ie-mode)</span></span>
   - <span data-ttu-id="5cc67-134">**无**。</span><span class="sxs-lookup"><span data-stu-id="5cc67-134">**None**.</span></span> <span data-ttu-id="5cc67-135">在用户选择的任意浏览器中打开。</span><span class="sxs-lookup"><span data-stu-id="5cc67-135">Opens in whatever browser the user chooses.</span></span>  

4. <span data-ttu-id="5cc67-136">在 **兼容模式**下，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="5cc67-136">Under **Compat Mode**, choose one of the following options:</span></span>

   - <span data-ttu-id="5cc67-137">**IE8Enterprise**。</span><span class="sxs-lookup"><span data-stu-id="5cc67-137">**IE8Enterprise**.</span></span> <span data-ttu-id="5cc67-138">在 IE8 企业模式中加载站点。</span><span class="sxs-lookup"><span data-stu-id="5cc67-138">Loads the site in IE8 Enterprise Mode.</span></span>
   - <span data-ttu-id="5cc67-139">**IE7Enterprise**。</span><span class="sxs-lookup"><span data-stu-id="5cc67-139">**IE7Enterprise**.</span></span> <span data-ttu-id="5cc67-140">在 IE7 企业模式中加载站点。</span><span class="sxs-lookup"><span data-stu-id="5cc67-140">Loads the site in IE7 Enterprise Mode.</span></span>
   - <span data-ttu-id="5cc67-141">**IE[x]**。</span><span class="sxs-lookup"><span data-stu-id="5cc67-141">**IE[x]**.</span></span> <span data-ttu-id="5cc67-142">其中 [x] 表示文档模式编号，在指定的文档模式中加载站点。</span><span class="sxs-lookup"><span data-stu-id="5cc67-142">Where [x] is the document mode number and the site loads in the specified document mode.</span></span>
   - <span data-ttu-id="5cc67-143">**默认模式**。</span><span class="sxs-lookup"><span data-stu-id="5cc67-143">**Default Mode**.</span></span> <span data-ttu-id="5cc67-144">使用适用于页面的默认兼容性模式加载站点。</span><span class="sxs-lookup"><span data-stu-id="5cc67-144">Loads the site using the default compatibility mode for the page.</span></span>

   <span data-ttu-id="5cc67-145">域内的路径可能需要对该域本身使用其他兼容性模式。</span><span class="sxs-lookup"><span data-stu-id="5cc67-145">The path within a domain can require a different compatibility mode from the domain itself.</span></span> <span data-ttu-id="5cc67-146">例如，域在默认 IE11 浏览器中可能没有问题，但路径可能有问题，并且需要使用企业模式。</span><span class="sxs-lookup"><span data-stu-id="5cc67-146">For example, the domain might look fine in the default IE11 browser, but the path might have problems and require the use of Enterprise Mode.</span></span> <span data-ttu-id="5cc67-147">如果你之前添加过域，则你的原始兼容性选择仍处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="5cc67-147">If you added the domain previously, your original compatibility choice is still selected.</span></span> <span data-ttu-id="5cc67-148">但是，如果域是全新的，将自动选择“ **IE8 企业模式** ”。</span><span class="sxs-lookup"><span data-stu-id="5cc67-148">However, if the domain is new, **IE8 Enterprise Mode** is automatically selected.</span></span>

   <span data-ttu-id="5cc67-149">由于企业模式优先于文档模式，因此已包含在企业模式站点列表中的站点不会受此更新影响，并将继续照常在企业模式中加载。</span><span class="sxs-lookup"><span data-stu-id="5cc67-149">Enterprise Mode takes precedence over document modes, so sites that are already included in the Enterprise Mode site list won’t be affected by this update and will continue to load in Enterprise Mode, as usual.</span></span> <span data-ttu-id="5cc67-150">有关使用文档模式的更具体的信息，请参阅 [使用文档模式和企业模式站点列表修复 Web 兼容性问题](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/fix-compat-issues-with-doc-modes-and-enterprise-mode-site-list)。</span><span class="sxs-lookup"><span data-stu-id="5cc67-150">For more specific information about using document modes, see [Fix web compatibility issues using document modes and the Enterprise Mode site list](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/fix-compat-issues-with-doc-modes-and-enterprise-mode-site-list).</span></span>

5. <span data-ttu-id="5cc67-151">**允许重定向** 复选框适用于服务器端重定向的处理。</span><span class="sxs-lookup"><span data-stu-id="5cc67-151">The **Allow Redirect** checkbox applies to the treatment of server-side redirects.</span></span> <span data-ttu-id="5cc67-152">如果选中此框，将在打开标记指定的浏览器中打开服务器端重定向。</span><span class="sxs-lookup"><span data-stu-id="5cc67-152">If you check this box, server-side redirects will open in the browser specified by the open-in tag.</span></span> <span data-ttu-id="5cc67-153">有关详细信息，请参阅 [这里](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance#updated-schema-attributes)。</span><span class="sxs-lookup"><span data-stu-id="5cc67-153">For more information, see [here](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance#updated-schema-attributes).</span></span>
6. <span data-ttu-id="5cc67-154">在“ **注释**”框中键入有关站点的任何注释。</span><span class="sxs-lookup"><span data-stu-id="5cc67-154">Type any comments about the website into the **Comment** box.</span></span> <span data-ttu-id="5cc67-155">管理员只有在使用此工具时才能看到注释，这些注释将保留在站点列表 xml 中。</span><span class="sxs-lookup"><span data-stu-id="5cc67-155">Administrators can only see comments while they’re in this tool and these comments are retained in the site list xml.</span></span>
7. <span data-ttu-id="5cc67-156">单击“ **添加**”将站点添加到站点列表。</span><span class="sxs-lookup"><span data-stu-id="5cc67-156">Click **Add** to add the site to your site list.</span></span>

### <span data-ttu-id="5cc67-157">将站点列表导出到 XML</span><span class="sxs-lookup"><span data-stu-id="5cc67-157">Export site list to XML</span></span>

<span data-ttu-id="5cc67-158">使用 Enterprise Site List Manager 创建企业模式站点列表后，可以将这些内容导出到 Enterprise Mode (.EMIE) 文件。</span><span class="sxs-lookup"><span data-stu-id="5cc67-158">After you create your site list in the Enterprise Site List Manager, you can export the contents to an Enterprise Mode (.EMIE) or XML file.</span></span> 

> [!NOTE]
> <span data-ttu-id="5cc67-159">此文件包括你的所有 URL（包括你的兼容性模式选择）并应存储在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="5cc67-159">This file includes all of your URLs, including your compatibility mode selections and should be stored somewhere safe.</span></span>

<span data-ttu-id="5cc67-160">若要导出站点列表，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="5cc67-160">To export the site list, follow these steps:</span></span>

1. <span data-ttu-id="5cc67-161">在 Enterprise Site List Manager 中，单击\*\*导出到 XML \*\*。</span><span class="sxs-lookup"><span data-stu-id="5cc67-161">In the Enterprise Site List Manager, click **Export to XML**.</span></span>
2. <span data-ttu-id="5cc67-162">输入**版本号**和**文件名**。</span><span class="sxs-lookup"><span data-stu-id="5cc67-162">Enter a **Version number** and a **File name**.</span></span>
3. <span data-ttu-id="5cc67-163">单击“**导出**”。</span><span class="sxs-lookup"><span data-stu-id="5cc67-163">Click **Export**.</span></span>

<span data-ttu-id="5cc67-164">可以通过本地方式保存文件，也可以将文件保存到网络共享。</span><span class="sxs-lookup"><span data-stu-id="5cc67-164">You can save the file locally or to a network share.</span></span> <span data-ttu-id="5cc67-165">但是，你必须确保将文件部署到注册表项中的指定位置。</span><span class="sxs-lookup"><span data-stu-id="5cc67-165">However, you must make sure you deploy it to the location specified in your registry key.</span></span> <span data-ttu-id="5cc67-166">有关更多信息，请参阅 [打开 Internet Explorer 模式并使用站点列表](https://docs.microsoft.com/deployedge/edge-ie-mode-policies)。</span><span class="sxs-lookup"><span data-stu-id="5cc67-166">For more information, see [Turn on Internet Explorer mode and use a site list](https://docs.microsoft.com/deployedge/edge-ie-mode-policies).</span></span>

### <span data-ttu-id="5cc67-167">将多个站点导入站点列表</span><span class="sxs-lookup"><span data-stu-id="5cc67-167">Import multiple sites to your site list</span></span>

<span data-ttu-id="5cc67-168">创建 .xml 文件后，可以使用“**从 XML 导入**”将站点批量添加到编辑器中。</span><span class="sxs-lookup"><span data-stu-id="5cc67-168">After you create your .xml file, you can bulk add sites to the editor using **Import from XML**.</span></span>

<span data-ttu-id="5cc67-169">如果要替换编辑器中所有的内容，请单击省略号 (...) ，然后选择“**清除列表**”。</span><span class="sxs-lookup"><span data-stu-id="5cc67-169">If you want to replace all the contents in the editor, click  the ellipsis (…) and then choose **Clear list**.</span></span> <span data-ttu-id="5cc67-170">清除编辑器后，使用以下步骤导入站点。</span><span class="sxs-lookup"><span data-stu-id="5cc67-170">After you clear the editor, use the following steps to import the site.</span></span>

1. <span data-ttu-id="5cc67-171">在 Enterprise Site List Manager 中，单击“**从 XML 导入**”。</span><span class="sxs-lookup"><span data-stu-id="5cc67-171">In the Enterprise Site List Manager, click **Import from XML**.</span></span> 
2. <span data-ttu-id="5cc67-172">单击“**选择文件**”以选择站点列表，将包含的站点添加到工具。</span><span class="sxs-lookup"><span data-stu-id="5cc67-172">Click **Choose file** to select your site list to add the included sites to the tool.</span></span> <span data-ttu-id="5cc67-173">选取要添加的站点列表，然后单击“ **打开**”。</span><span class="sxs-lookup"><span data-stu-id="5cc67-173">Pick the site list you want to add and then click **Open**.</span></span> <span data-ttu-id="5cc67-174">支持的导入格式有 .xml、.emie 或 .txt，其中包含 Enterprise Mode Site Lis v.2 架构。</span><span class="sxs-lookup"><span data-stu-id="5cc67-174">Supported formats for Import are .xml, .emie or .txt containing the v.2 schema for Enterprise Mode Site List.</span></span> <span data-ttu-id="5cc67-175">参阅 [企业模式架构 v.2 指南](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)。</span><span class="sxs-lookup"><span data-stu-id="5cc67-175">See [Enterprise Mode schema v.2 guidance](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>
3. <span data-ttu-id="5cc67-176">单击“ **加载**” 以从文件 tp 编辑器添加站点。</span><span class="sxs-lookup"><span data-stu-id="5cc67-176">Click **Load** to add the sites from the file tp the editor.</span></span>

<span data-ttu-id="5cc67-177">可以通过本地方式保存文件，也可以将文件保存到网络共享。</span><span class="sxs-lookup"><span data-stu-id="5cc67-177">You can save the file locally or to a network share.</span></span> <span data-ttu-id="5cc67-178">但是，你必须确保将文件部署到注册表项中的指定位置。</span><span class="sxs-lookup"><span data-stu-id="5cc67-178">However, you must make sure you deploy it to the location specified in your registry key.</span></span> <span data-ttu-id="5cc67-179">有关更多信息，请参阅 [打开 Internet Explorer 模式并使用站点列表](https://docs.microsoft.com/deployedge/edge-ie-mode-policies)。</span><span class="sxs-lookup"><span data-stu-id="5cc67-179">For more information, see [Turn on Internet Explorer mode and use a site list](https://docs.microsoft.com/deployedge/edge-ie-mode-policies).</span></span>

### <span data-ttu-id="5cc67-180">编辑站点列表中的站点</span><span class="sxs-lookup"><span data-stu-id="5cc67-180">Edit sites in your site list</span></span>

 <span data-ttu-id="5cc67-181">可以在 Enterprise Site List Manager 中编辑现有站点条目的属性。</span><span class="sxs-lookup"><span data-stu-id="5cc67-181">You can edit attributes of existing site entries in the Enterprise Site List Manager.</span></span> <span data-ttu-id="5cc67-182">你还可以添加、移除或删除相关联的注释。</span><span class="sxs-lookup"><span data-stu-id="5cc67-182">You can also add, remove, or delete associated comments.</span></span>

1. <span data-ttu-id="5cc67-183">在 Enterprise Site List Manager 中，单击省略号（...），然后为要编辑的 URL 选择“**编辑站点**”。</span><span class="sxs-lookup"><span data-stu-id="5cc67-183">In the Enterprise Site List Manager, click the ellipsis (…) and choose **Edit site** for the URL you want to edit.</span></span>
2. <span data-ttu-id="5cc67-184">可以编辑站点条目的任何属性（URL 除外）。</span><span class="sxs-lookup"><span data-stu-id="5cc67-184">You can edit any attribute of the site entry except the URL.</span></span> <span data-ttu-id="5cc67-185">完成编辑后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="5cc67-185">Click **Save** after you finish editing.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5cc67-186">如果要删除站点条目，请选择步骤 1 中的“**删除站点**”。</span><span class="sxs-lookup"><span data-stu-id="5cc67-186">If you want to delete a site entry, choose **Delete site** in step 1.</span></span>

3. <span data-ttu-id="5cc67-187">单击“**导出到 XML**”。然后保存更新的文件。</span><span class="sxs-lookup"><span data-stu-id="5cc67-187">Click **Export to XML**, and save the updated file.</span></span>

<span data-ttu-id="5cc67-188">可以通过本地方式保存文件，也可以将文件保存到网络共享。</span><span class="sxs-lookup"><span data-stu-id="5cc67-188">You can save the file locally or to a network share.</span></span> <span data-ttu-id="5cc67-189">但是，你必须确保将文件部署到注册表项中的指定位置。</span><span class="sxs-lookup"><span data-stu-id="5cc67-189">However, you must make sure you deploy it to the location specified in your registry key.</span></span> <span data-ttu-id="5cc67-190">有关更多信息，请参阅 [打开 Internet Explorer 模式并使用站点列表](https://docs.microsoft.com/deployedge/edge-ie-mode-policies)。</span><span class="sxs-lookup"><span data-stu-id="5cc67-190">For more information, see [Turn on Internet Explorer mode and use a site list](https://docs.microsoft.com/deployedge/edge-ie-mode-policies).</span></span>

### <span data-ttu-id="5cc67-191">以 XML 格式预览站点列表</span><span class="sxs-lookup"><span data-stu-id="5cc67-191">Preview your site list in XML format</span></span>

<span data-ttu-id="5cc67-192">可以在编辑器中以 XML 格式预览站点，然后导出并保存到站点列表位置。</span><span class="sxs-lookup"><span data-stu-id="5cc67-192">You can preview the sites in the editor in XML format before you export and save to your site list location.</span></span> <span data-ttu-id="5cc67-193">单击 **XML 预览** 以打开新选项卡中的文件。</span><span class="sxs-lookup"><span data-stu-id="5cc67-193">Click **XML preview** to open the file in a new tab.</span></span>

### <span data-ttu-id="5cc67-194">在 Enterprise Site List Manager 中搜索</span><span class="sxs-lookup"><span data-stu-id="5cc67-194">Search in the Enterprise Site List Manager</span></span>

<span data-ttu-id="5cc67-195">你可以搜索以查看特定站点是否已经显示在站点列表中，以便你无需再次尝试添加它。</span><span class="sxs-lookup"><span data-stu-id="5cc67-195">You can search to see if a specific site already appears in your site list so you don’t try to add it again.</span></span>

<span data-ttu-id="5cc67-196">若要进行搜索，请在编辑器右上角的“ **按 URL 筛选站点**”搜索框中键入 URL 的一部分。</span><span class="sxs-lookup"><span data-stu-id="5cc67-196">To search, type part of the URL into the **Filter sites by URL** search box on the top right-hand corner of the editor.</span></span>

## <span data-ttu-id="5cc67-197">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5cc67-197">See also</span></span>

- [<span data-ttu-id="5cc67-198">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="5cc67-198">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="5cc67-199">关于 IE 模式</span><span class="sxs-lookup"><span data-stu-id="5cc67-199">About IE mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [<span data-ttu-id="5cc67-200">其他企业模式信息</span><span class="sxs-lookup"><span data-stu-id="5cc67-200">Additional Enterprise Mode information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [<span data-ttu-id="5cc67-201">其他“企业站点发现”信息</span><span class="sxs-lookup"><span data-stu-id="5cc67-201">Additional Enterprise Site Discovery information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery)
