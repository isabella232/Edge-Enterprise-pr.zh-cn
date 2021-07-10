---
title: 'Microsoft Edge 中的 Enterprise Site List Manager '
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: '启用并使用 Microsoft Edge 中的 Enterprise Site List Manager '
ms.openlocfilehash: add635a17d05cb4be94e710fd99ab480b992a579
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641418"
---
# <a name="enterprise-site-list-manager-in-microsoft-edge"></a><span data-ttu-id="77399-103">Microsoft Edge 中的企业网站列表管理器</span><span class="sxs-lookup"><span data-stu-id="77399-103">Enterprise Site List Manager in Microsoft Edge</span></span>

>[!Note]
> <span data-ttu-id="77399-104">Internet Explorer 11 桌面应用程序将于 2022 年 6 月 15 日停用并停止支持（若要查看包含内容的列表，[请参阅常见问题解答](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)）。</span><span class="sxs-lookup"><span data-stu-id="77399-104">The Internet Explorer 11 desktop application will be retired and go out of support on June 15, 2022 (for a list of what’s in scope, [see the FAQ](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)).</span></span> <span data-ttu-id="77399-105">现在使用的 IE11 应用和网站可以在 Microsoft Edge 的 Internet Explorer 模式下打开。</span><span class="sxs-lookup"><span data-stu-id="77399-105">The same IE11 apps and sites you use today can open in Microsoft Edge with Internet Explorer mode.</span></span> <span data-ttu-id="77399-106">[在此处了解详细信息](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。</span><span class="sxs-lookup"><span data-stu-id="77399-106">[Learn more here](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).</span></span>

<span data-ttu-id="77399-107">本文介绍如何启用和访问 Microsoft Edge 中的 Enterprise Site List Manager 以创建、编辑和导出 Internet Explorer 模式的 Enterprise Mode Site List。</span><span class="sxs-lookup"><span data-stu-id="77399-107">This article explains how to enable access to and use the Enterprise Site List Manager in Microsoft Edge to create, edit and export your Enterprise Mode Site List for Internet Explorer mode.</span></span>

> [!NOTE]
> <span data-ttu-id="77399-108">本文适用于 Microsoft Edge 版本 89 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="77399-108">This article applies to Microsoft Edge version 89 or later.</span></span> 

## <a name="overview"></a><span data-ttu-id="77399-109">概述</span><span class="sxs-lookup"><span data-stu-id="77399-109">Overview</span></span>

<span data-ttu-id="77399-110">Enterprise Site List Manager 是[独立 Enterprise Mode Site List Manager 工具](https://www.microsoft.com/download/details.aspx?id=49974)的浏览器内版本，可让创建、编辑和导出组织的站点列表。</span><span class="sxs-lookup"><span data-stu-id="77399-110">The Enterprise Site List Manager is an in-browser version of the [standalone Enterprise Mode Site List Manager tool](https://www.microsoft.com/download/details.aspx?id=49974) that lets you create, edit, and export your organization’s site list.</span></span>

<span data-ttu-id="77399-111">通过 Microsoft Edge 中的 Enterprise Site List Manager，可以进一步改进用于 Internet Explorer 模式的工具。</span><span class="sxs-lookup"><span data-stu-id="77399-111">Future improvements to the tool for Internet Explorer mode will be available through Enterprise Site List Manager in Microsoft Edge.</span></span> <span data-ttu-id="77399-112">独立工具将继续在下载中心中提供，但无法获得任何功能更新。</span><span class="sxs-lookup"><span data-stu-id="77399-112">The standalone tool will continue to be available in the Download Center but won't get any feature updates.</span></span>

## <a name="enabling-access-to-enterprise-site-list-manager"></a><span data-ttu-id="77399-113">允许访问 Enterprise Site List Manager</span><span class="sxs-lookup"><span data-stu-id="77399-113">Enabling access to Enterprise Site List Manager</span></span>

<span data-ttu-id="77399-114">可以使用 [EnterpriseModeSiteListManagerAllowed](./microsoft-edge-policies.md#enterprisemodesitelistmanagerallowed) 组策略配置对工具的访问权限。</span><span class="sxs-lookup"><span data-stu-id="77399-114">You can configure access to the tool by using the [EnterpriseModeSiteListManagerAllowed](./microsoft-edge-policies.md#enterprisemodesitelistmanagerallowed) group policy.</span></span>

<span data-ttu-id="77399-115">如果启用，用户将在 *edge://compat* 的左侧导航窗格中看到一个名为 Enterprise Site List Manager 的选项。</span><span class="sxs-lookup"><span data-stu-id="77399-115">If enabled, your users will see an option named Enterprise Site List Manager on the left navigation pane in *edge://compat*.</span></span> <span data-ttu-id="77399-116">如果禁用，用户将不会在左侧导航窗格中看到 Enterprise Site List Manager 的入口点。</span><span class="sxs-lookup"><span data-stu-id="77399-116">If disabled, users will not see the entry point to Enterprise Site List Manager in the left navigation pane.</span></span> <span data-ttu-id="77399-117">这是默认行为。</span><span class="sxs-lookup"><span data-stu-id="77399-117">This is the default behavior.</span></span>

## <a name="using-the-enterprise-site-list-manager"></a><span data-ttu-id="77399-118">使用 Enterprise Site List Manager</span><span class="sxs-lookup"><span data-stu-id="77399-118">Using the Enterprise Site List Manager</span></span>

<span data-ttu-id="77399-119">Enterprise Site List Manager 工具使用 v.2 版本的架构。</span><span class="sxs-lookup"><span data-stu-id="77399-119">The Enterprise Site List Manager tool uses the v.2 version of the schema.</span></span> <span data-ttu-id="77399-120">如果将 v.1 版本架构导入到 Enterprise Site List Manager（架构 v.2）中，XML 将被保存到 v.2 版本的架构。</span><span class="sxs-lookup"><span data-stu-id="77399-120">If you import a v.1 version schema into the Enterprise Site List Manager (schema v.2), the XML is saved into the v.2 version of the schema.</span></span> <span data-ttu-id="77399-121">参阅 [企业模式架构 v.2 指南](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)。</span><span class="sxs-lookup"><span data-stu-id="77399-121">See [Enterprise Mode schema v.2 guidance](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>

### <a name="add-single-sites-to-your-site-list"></a><span data-ttu-id="77399-122">将单个站点添加到站点列表</span><span class="sxs-lookup"><span data-stu-id="77399-122">Add single sites to your site list</span></span>  

<span data-ttu-id="77399-123">使用以下步骤将单个站点添加到站点列表。</span><span class="sxs-lookup"><span data-stu-id="77399-123">Use the following steps to add individual sites to your site list.</span></span>

> [!NOTE]
> <span data-ttu-id="77399-124">你只能添加特定的 URL，而无法添加 Internet 或 Intranet 区域。</span><span class="sxs-lookup"><span data-stu-id="77399-124">You can only add specific URLs, not Internet or Intranet Zones.</span></span>

1. <span data-ttu-id="77399-125">在 Enterprise Site List Manager 中，单击“ **添加站点**”。</span><span class="sxs-lookup"><span data-stu-id="77399-125">In the Enterprise Site List Manager, click **Add a site**.</span></span>
2. <span data-ttu-id="77399-126">在 URL 框中输入要添加的站点网址，例如： <domain>.com or <domain>.com/<path> 。</span><span class="sxs-lookup"><span data-stu-id="77399-126">Type the URL for the website you’d like to add, for example: <domain>.com or <domain>.com/<path> in the URL box.</span></span>
3. <span data-ttu-id="77399-127">从“**打开方式**” 列表中选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="77399-127">Select one of the following options from the **Open in** list:</span></span>

   - <span data-ttu-id="77399-128">**IE11**。</span><span class="sxs-lookup"><span data-stu-id="77399-128">**IE11**.</span></span> <span data-ttu-id="77399-129">在 IE11 应用程序中打开站点。</span><span class="sxs-lookup"><span data-stu-id="77399-129">Opens the site in the IE11 application.</span></span>
   - <span data-ttu-id="77399-130">**IE 模式**。</span><span class="sxs-lookup"><span data-stu-id="77399-130">**IE mode**.</span></span> <span data-ttu-id="77399-131">如果启用，在 Microsoft Edge 的 Internet Explorer 模式中打开站点，否则在 IE11 应用中打开站点。</span><span class="sxs-lookup"><span data-stu-id="77399-131">Opens the site in Internet Explorer mode on Microsoft Edge if enabled and in the IE11 app otherwise.</span></span> <span data-ttu-id="77399-132">请参阅  [Microsoft Edge 上的 Internet Explorer 模式 ](./edge-ie-mode.md)。</span><span class="sxs-lookup"><span data-stu-id="77399-132">See [Internet Explorer mode on Microsoft Edge](./edge-ie-mode.md).</span></span>
   - <span data-ttu-id="77399-133">**MSEdge**。</span><span class="sxs-lookup"><span data-stu-id="77399-133">**MSEdge**.</span></span> <span data-ttu-id="77399-134">在 Microsoft Edge 中打开站点。</span><span class="sxs-lookup"><span data-stu-id="77399-134">Opens the site in Microsoft Edge.</span></span>
   - <span data-ttu-id="77399-135">**可配置**。</span><span class="sxs-lookup"><span data-stu-id="77399-135">**Configurable**.</span></span> <span data-ttu-id="77399-136">允许站点参与 IE 模式引擎确定。</span><span class="sxs-lookup"><span data-stu-id="77399-136">Allows the site to participate in IE mode engine determination.</span></span> <span data-ttu-id="77399-137">参见 [IE 模式下可配置的站点](./edge-learnmore-configurable-sites-ie-mode.md)</span><span class="sxs-lookup"><span data-stu-id="77399-137">See [Configurable sites in IE mode](./edge-learnmore-configurable-sites-ie-mode.md)</span></span>
   - <span data-ttu-id="77399-138">**无**。</span><span class="sxs-lookup"><span data-stu-id="77399-138">**None**.</span></span> <span data-ttu-id="77399-139">在用户选择的任意浏览器中打开。</span><span class="sxs-lookup"><span data-stu-id="77399-139">Opens in whatever browser the user chooses.</span></span>  

4. <span data-ttu-id="77399-140">在 **兼容模式**下，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="77399-140">Under **Compat Mode**, choose one of the following options:</span></span>

   - <span data-ttu-id="77399-141">**IE8Enterprise**。</span><span class="sxs-lookup"><span data-stu-id="77399-141">**IE8Enterprise**.</span></span> <span data-ttu-id="77399-142">在 IE8 企业模式中加载站点。</span><span class="sxs-lookup"><span data-stu-id="77399-142">Loads the site in IE8 Enterprise Mode.</span></span>
   - <span data-ttu-id="77399-143">**IE7Enterprise**。</span><span class="sxs-lookup"><span data-stu-id="77399-143">**IE7Enterprise**.</span></span> <span data-ttu-id="77399-144">在 IE7 企业模式中加载站点。</span><span class="sxs-lookup"><span data-stu-id="77399-144">Loads the site in IE7 Enterprise Mode.</span></span>
   - <span data-ttu-id="77399-145">**IE[x]**。</span><span class="sxs-lookup"><span data-stu-id="77399-145">**IE[x]**.</span></span> <span data-ttu-id="77399-146">其中 [x] 表示文档模式编号，在指定的文档模式中加载站点。</span><span class="sxs-lookup"><span data-stu-id="77399-146">Where [x] is the document mode number and the site loads in the specified document mode.</span></span>
   - <span data-ttu-id="77399-147">**默认模式**。</span><span class="sxs-lookup"><span data-stu-id="77399-147">**Default Mode**.</span></span> <span data-ttu-id="77399-148">使用适用于页面的默认兼容性模式加载站点。</span><span class="sxs-lookup"><span data-stu-id="77399-148">Loads the site using the default compatibility mode for the page.</span></span>

   <span data-ttu-id="77399-149">域内的路径可能需要对该域本身使用其他兼容性模式。</span><span class="sxs-lookup"><span data-stu-id="77399-149">The path within a domain can require a different compatibility mode from the domain itself.</span></span> <span data-ttu-id="77399-150">例如，域在默认 IE11 浏览器中可能没有问题，但路径可能有问题，并且需要使用企业模式。</span><span class="sxs-lookup"><span data-stu-id="77399-150">For example, the domain might look fine in the default IE11 browser, but the path might have problems and require the use of Enterprise Mode.</span></span> <span data-ttu-id="77399-151">如果你之前添加过域，则你的原始兼容性选择仍处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="77399-151">If you added the domain previously, your original compatibility choice is still selected.</span></span> <span data-ttu-id="77399-152">但是，如果域是全新的，将自动选择“ **IE8 企业模式** ”。</span><span class="sxs-lookup"><span data-stu-id="77399-152">However, if the domain is new, **IE8 Enterprise Mode** is automatically selected.</span></span>

   <span data-ttu-id="77399-153">由于企业模式优先于文档模式，因此已包含在企业模式站点列表中的站点不会受此更新影响，并将继续照常在企业模式中加载。</span><span class="sxs-lookup"><span data-stu-id="77399-153">Enterprise Mode takes precedence over document modes, so sites that are already included in the Enterprise Mode site list won’t be affected by this update and will continue to load in Enterprise Mode, as usual.</span></span> <span data-ttu-id="77399-154">有关使用文档模式的更具体的信息，请参阅 [使用文档模式和企业模式站点列表修复 Web 兼容性问题](/internet-explorer/ie11-deploy-guide/fix-compat-issues-with-doc-modes-and-enterprise-mode-site-list)。</span><span class="sxs-lookup"><span data-stu-id="77399-154">For more specific information about using document modes, see [Fix web compatibility issues using document modes and the Enterprise Mode site list](/internet-explorer/ie11-deploy-guide/fix-compat-issues-with-doc-modes-and-enterprise-mode-site-list).</span></span>

5. <span data-ttu-id="77399-155">**允许重定向** 复选框适用于服务器端重定向的处理。</span><span class="sxs-lookup"><span data-stu-id="77399-155">The **Allow Redirect** checkbox applies to the treatment of server-side redirects.</span></span> <span data-ttu-id="77399-156">如果选中此框，将在打开标记指定的浏览器中打开服务器端重定向。</span><span class="sxs-lookup"><span data-stu-id="77399-156">If you check this box, server-side redirects will open in the browser specified by the open-in tag.</span></span> <span data-ttu-id="77399-157">有关详细信息，请参阅 [这里](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance#updated-schema-attributes)。</span><span class="sxs-lookup"><span data-stu-id="77399-157">For more information, see [here](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance#updated-schema-attributes).</span></span>
6. <span data-ttu-id="77399-158">在“ **注释**”框中键入有关站点的任何注释。</span><span class="sxs-lookup"><span data-stu-id="77399-158">Type any comments about the website into the **Comment** box.</span></span> <span data-ttu-id="77399-159">管理员只有在使用此工具时才能看到注释，这些注释将保留在站点列表 xml 中。</span><span class="sxs-lookup"><span data-stu-id="77399-159">Administrators can only see comments while they’re in this tool and these comments are retained in the site list xml.</span></span>
7. <span data-ttu-id="77399-160">单击“ **添加**”将站点添加到站点列表。</span><span class="sxs-lookup"><span data-stu-id="77399-160">Click **Add** to add the site to your site list.</span></span>

### <a name="export-site-list-to-xml"></a><span data-ttu-id="77399-161">将站点列表导出到 XML</span><span class="sxs-lookup"><span data-stu-id="77399-161">Export site list to XML</span></span>

<span data-ttu-id="77399-162">使用 Enterprise Site List Manager 创建企业模式站点列表后，可以将这些内容导出到 Enterprise Mode (.EMIE) 文件。</span><span class="sxs-lookup"><span data-stu-id="77399-162">After you create your site list in the Enterprise Site List Manager, you can export the contents to an Enterprise Mode (.EMIE) or XML file.</span></span> 

> [!NOTE]
> <span data-ttu-id="77399-163">此文件包括你的所有 URL（包括你的兼容性模式选择）并应存储在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="77399-163">This file includes all of your URLs, including your compatibility mode selections and should be stored somewhere safe.</span></span>

<span data-ttu-id="77399-164">若要导出站点列表，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="77399-164">To export the site list, follow these steps:</span></span>

1. <span data-ttu-id="77399-165">在 Enterprise Site List Manager 中，单击\*\*导出到 XML \*\*。</span><span class="sxs-lookup"><span data-stu-id="77399-165">In the Enterprise Site List Manager, click **Export to XML**.</span></span>
2. <span data-ttu-id="77399-166">输入**版本号**和**文件名**。</span><span class="sxs-lookup"><span data-stu-id="77399-166">Enter a **Version number** and a **File name**.</span></span>
3. <span data-ttu-id="77399-167">单击“**导出**”。</span><span class="sxs-lookup"><span data-stu-id="77399-167">Click **Export**.</span></span>

<span data-ttu-id="77399-168">可以通过本地方式保存文件，也可以将文件保存到网络共享。</span><span class="sxs-lookup"><span data-stu-id="77399-168">You can save the file locally or to a network share.</span></span> <span data-ttu-id="77399-169">但是，你必须确保将文件部署到注册表项中的指定位置。</span><span class="sxs-lookup"><span data-stu-id="77399-169">However, you must make sure you deploy it to the location specified in your registry key.</span></span> <span data-ttu-id="77399-170">有关更多信息，请参阅 [打开 Internet Explorer 模式并使用站点列表](./edge-ie-mode-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="77399-170">For more information, see [Turn on Internet Explorer mode and use a site list](./edge-ie-mode-policies.md).</span></span>

### <a name="import-multiple-sites-to-your-site-list"></a><span data-ttu-id="77399-171">将多个站点导入站点列表</span><span class="sxs-lookup"><span data-stu-id="77399-171">Import multiple sites to your site list</span></span>

<span data-ttu-id="77399-172">创建 .xml 文件后，可以使用“**从 XML 导入**”将站点批量添加到编辑器中。</span><span class="sxs-lookup"><span data-stu-id="77399-172">After you create your .xml file, you can bulk add sites to the editor using **Import from XML**.</span></span>

<span data-ttu-id="77399-173">如果要替换编辑器中所有的内容，请单击省略号 (...) ，然后选择“**清除列表**”。</span><span class="sxs-lookup"><span data-stu-id="77399-173">If you want to replace all the contents in the editor, click  the ellipsis (…) and then choose **Clear list**.</span></span> <span data-ttu-id="77399-174">清除编辑器后，使用以下步骤导入站点。</span><span class="sxs-lookup"><span data-stu-id="77399-174">After you clear the editor, use the following steps to import the site.</span></span>

1. <span data-ttu-id="77399-175">在 Enterprise Site List Manager 中，单击“**从 XML 导入**”。</span><span class="sxs-lookup"><span data-stu-id="77399-175">In the Enterprise Site List Manager, click **Import from XML**.</span></span> 
2. <span data-ttu-id="77399-176">单击“**选择文件**”以选择站点列表，将包含的站点添加到工具。</span><span class="sxs-lookup"><span data-stu-id="77399-176">Click **Choose file** to select your site list to add the included sites to the tool.</span></span> <span data-ttu-id="77399-177">选取要添加的站点列表，然后单击“ **打开**”。</span><span class="sxs-lookup"><span data-stu-id="77399-177">Pick the site list you want to add and then click **Open**.</span></span> <span data-ttu-id="77399-178">支持的导入格式有 .xml、.emie 或 .txt，其中包含 Enterprise Mode Site Lis v.2 架构。</span><span class="sxs-lookup"><span data-stu-id="77399-178">Supported formats for Import are .xml, .emie or .txt containing the v.2 schema for Enterprise Mode Site List.</span></span> <span data-ttu-id="77399-179">参阅 [企业模式架构 v.2 指南](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)。</span><span class="sxs-lookup"><span data-stu-id="77399-179">See [Enterprise Mode schema v.2 guidance](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>
3. <span data-ttu-id="77399-180">单击“ **加载**” 以从文件 tp 编辑器添加站点。</span><span class="sxs-lookup"><span data-stu-id="77399-180">Click **Load** to add the sites from the file tp the editor.</span></span>

<span data-ttu-id="77399-181">可以通过本地方式保存文件，也可以将文件保存到网络共享。</span><span class="sxs-lookup"><span data-stu-id="77399-181">You can save the file locally or to a network share.</span></span> <span data-ttu-id="77399-182">但是，你必须确保将文件部署到注册表项中的指定位置。</span><span class="sxs-lookup"><span data-stu-id="77399-182">However, you must make sure you deploy it to the location specified in your registry key.</span></span> <span data-ttu-id="77399-183">有关更多信息，请参阅 [打开 Internet Explorer 模式并使用站点列表](./edge-ie-mode-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="77399-183">For more information, see [Turn on Internet Explorer mode and use a site list](./edge-ie-mode-policies.md).</span></span>

### <a name="edit-sites-in-your-site-list"></a><span data-ttu-id="77399-184">编辑站点列表中的站点</span><span class="sxs-lookup"><span data-stu-id="77399-184">Edit sites in your site list</span></span>

 <span data-ttu-id="77399-185">可以在 Enterprise Site List Manager 中编辑现有站点条目的属性。</span><span class="sxs-lookup"><span data-stu-id="77399-185">You can edit attributes of existing site entries in the Enterprise Site List Manager.</span></span> <span data-ttu-id="77399-186">你还可以添加、移除或删除相关联的注释。</span><span class="sxs-lookup"><span data-stu-id="77399-186">You can also add, remove, or delete associated comments.</span></span>

1. <span data-ttu-id="77399-187">在 Enterprise Site List Manager 中，单击省略号（...），然后为要编辑的 URL 选择“**编辑站点**”。</span><span class="sxs-lookup"><span data-stu-id="77399-187">In the Enterprise Site List Manager, click the ellipsis (…) and choose **Edit site** for the URL you want to edit.</span></span>
2. <span data-ttu-id="77399-188">可以编辑站点条目的任何属性（URL 除外）。</span><span class="sxs-lookup"><span data-stu-id="77399-188">You can edit any attribute of the site entry except the URL.</span></span> <span data-ttu-id="77399-189">完成编辑后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="77399-189">Click **Save** after you finish editing.</span></span>

   > [!NOTE]
   > <span data-ttu-id="77399-190">如果要删除站点条目，请选择步骤 1 中的“**删除站点**”。</span><span class="sxs-lookup"><span data-stu-id="77399-190">If you want to delete a site entry, choose **Delete site** in step 1.</span></span>

3. <span data-ttu-id="77399-191">单击“**导出到 XML**”。然后保存更新的文件。</span><span class="sxs-lookup"><span data-stu-id="77399-191">Click **Export to XML**, and save the updated file.</span></span>

<span data-ttu-id="77399-192">可以通过本地方式保存文件，也可以将文件保存到网络共享。</span><span class="sxs-lookup"><span data-stu-id="77399-192">You can save the file locally or to a network share.</span></span> <span data-ttu-id="77399-193">但是，你必须确保将文件部署到注册表项中的指定位置。</span><span class="sxs-lookup"><span data-stu-id="77399-193">However, you must make sure you deploy it to the location specified in your registry key.</span></span> <span data-ttu-id="77399-194">有关更多信息，请参阅 [打开 Internet Explorer 模式并使用站点列表](./edge-ie-mode-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="77399-194">For more information, see [Turn on Internet Explorer mode and use a site list](./edge-ie-mode-policies.md).</span></span>

### <a name="preview-your-site-list-in-xml-format"></a><span data-ttu-id="77399-195">以 XML 格式预览站点列表</span><span class="sxs-lookup"><span data-stu-id="77399-195">Preview your site list in XML format</span></span>

<span data-ttu-id="77399-196">可以在编辑器中以 XML 格式预览站点，然后导出并保存到站点列表位置。</span><span class="sxs-lookup"><span data-stu-id="77399-196">You can preview the sites in the editor in XML format before you export and save to your site list location.</span></span> <span data-ttu-id="77399-197">单击 **XML 预览** 以打开新选项卡中的文件。</span><span class="sxs-lookup"><span data-stu-id="77399-197">Click **XML preview** to open the file in a new tab.</span></span>

### <a name="search-in-the-enterprise-site-list-manager"></a><span data-ttu-id="77399-198">在 Enterprise Site List Manager 中搜索</span><span class="sxs-lookup"><span data-stu-id="77399-198">Search in the Enterprise Site List Manager</span></span>

<span data-ttu-id="77399-199">你可以搜索以查看特定站点是否已经显示在站点列表中，以便你无需再次尝试添加它。</span><span class="sxs-lookup"><span data-stu-id="77399-199">You can search to see if a specific site already appears in your site list so you don’t try to add it again.</span></span>

<span data-ttu-id="77399-200">若要进行搜索，请在编辑器右上角的“ **按 URL 筛选站点**”搜索框中键入 URL 的一部分。</span><span class="sxs-lookup"><span data-stu-id="77399-200">To search, type part of the URL into the **Filter sites by URL** search box on the top right-hand corner of the editor.</span></span>

## <a name="see-also"></a><span data-ttu-id="77399-201">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77399-201">See also</span></span>

- [<span data-ttu-id="77399-202">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="77399-202">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="77399-203">关于 IE 模式</span><span class="sxs-lookup"><span data-stu-id="77399-203">About IE mode</span></span>](./edge-ie-mode.md)
- [<span data-ttu-id="77399-204">企业模式架构 v.2 指南</span><span class="sxs-lookup"><span data-stu-id="77399-204">Enterprise Mode schema v.2 guidance</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)
- [<span data-ttu-id="77399-205">其他企业模式信息</span><span class="sxs-lookup"><span data-stu-id="77399-205">Additional Enterprise Mode information</span></span>](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)