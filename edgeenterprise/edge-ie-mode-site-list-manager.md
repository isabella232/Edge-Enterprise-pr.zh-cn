---
title: 'Microsoft Edge 中的 Enterprise Site List Manager '
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 04/20/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 了解如何在Microsoft Edge中启用和使用Enterprise站点列表管理器
ms.openlocfilehash: a17225f3243e57e8f45b04991b858c592f9f75d6
ms.sourcegitcommit: 592f6e40b13e28af588473b2a75c3ae697e5db2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2022
ms.locfileid: "12505643"
---
# <a name="enterprise-site-list-manager-in-microsoft-edge"></a>Microsoft Edge 中的企业站点列表管理器

>[!Note]
> Internet Explorer 11 桌面应用程序将于 2022 年 6 月 15 日停用并停止支持， (获取范围列表，请参阅 [Internet Explorer 11 桌面应用停用常见问题解答](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)) 。 现在使用的 IE11 应用和网站可以在 Microsoft Edge 的 Internet Explorer 模式下打开。 [在此处了解详细信息](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。

本文介绍如何在Microsoft Edge中启用访问和使用Enterprise站点列表管理器，以创建、编辑和导出 Internet Explorer (IE) 模式的Enterprise模式站点列表。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 89 或更高版本。 共享 Cookie 功能在版本 101 或更高版本Microsoft Edge可用。

## <a name="overview"></a>概述

Enterprise Site List Manager 是独立 Enterprise Mode Site List Manager 工具的浏览器内版本，可让创建、编辑和导出组织的站点列表。 可以在 edge://compat/SiteListManager 访问浏览器Enterprise站点列表管理*器。*

将来将通过Enterprise站点列表管理器 (edge://compat/SiteListManager) Microsoft Edge提供 Internet Explorer 模式工具的改进。** 独立工具将继续在下载中心中提供，但无法获得任何功能更新。

## <a name="enabling-access-to-enterprise-site-list-manager"></a>允许访问 Enterprise Site List Manager

可以使用 [EnterpriseModeSiteListManagerAllowed](./microsoft-edge-policies.md#enterprisemodesitelistmanagerallowed) 组策略配置对站点列表管理器工具的访问权限。

如果启用此策略，用户将在 edge://compat 的左侧导航窗格中看到名为“Enterprise站点列表管理器 *”* 的选项。 如果禁用策略，则用户不会在左侧导航窗格中看到指向Enterprise站点列表管理器的入口点，这是默认行为。

## <a name="using-the-enterprise-site-list-manager"></a>使用 Enterprise Site List Manager

Enterprise Site List Manager 工具使用 v.2 版本的架构。 如果将 v.1 版本架构导入到 Enterprise Site List Manager（架构 v.2）中，XML 将被保存到 v.2 版本的架构。 参阅 [企业模式架构 v.2 指南](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)。

### <a name="add-single-sites-to-your-site-list"></a>将单个站点添加到站点列表  

使用以下步骤将单个站点添加到站点列表。

> [!NOTE]
> 你只能添加特定的 URL，而无法添加 Internet 或 Intranet 区域。

1. 在Enterprise站点列表管理器中，选择 **“已添加网站**”。
2. 输入要添加的网站的 URL，例如： \<domain\>.com 或 \<domain\>.com/\<path\> 在 URL 框中。
3. 从“**打开方式**” 列表中选择以下选项之一：

   - **IE11**。 在 IE11 应用程序中打开站点。
   - **IE 模式**。 如果启用，在 Microsoft Edge 的 Internet Explorer 模式中打开站点，否则在 IE11 应用中打开站点。 请参阅  [Microsoft Edge 上的 Internet Explorer 模式 ](./edge-ie-mode.md)。
   - **MSEdge**。 在 Microsoft Edge 中打开站点。
   - **可配置**。 允许站点参与 IE 模式引擎确定。 参见 [IE 模式下可配置的站点](./edge-learnmore-configurable-sites-ie-mode.md)
   - **无**。 在用户选择的任意浏览器中打开。  

4. 在 **兼容模式**下，选择下列选项之一：

   - **IE8Enterprise**。 在 IE8 企业模式中加载站点。
   - **IE7Enterprise**。 在 IE7 企业模式中加载站点。
   - **IE[x]**。 其中 [x] 表示文档模式编号，在指定的文档模式中加载站点。
   - **默认模式**。 使用适用于页面的默认兼容性模式加载站点。

   域内的路径可能需要对该域本身使用其他兼容性模式。 例如，域在默认 IE11 浏览器中可能没有问题，但路径可能有问题，并且需要使用企业模式。 如果你之前添加过域，则你的原始兼容性选择仍处于选中状态。 但是，如果域是全新的，将自动选择“ **IE8 企业模式** ”。

   Enterprise模式优先于文档模式，因此已包含在Enterprise模式站点列表中的网站不会受到此更新的影响。 这些站点将继续在Enterprise模式下加载。 有关使用文档模式的更具体的信息，请参阅 [使用文档模式和企业模式站点列表修复 Web 兼容性问题](/internet-explorer/ie11-deploy-guide/fix-compat-issues-with-doc-modes-and-enterprise-mode-site-list)。

5. **允许重定向** 复选框适用于服务器端重定向的处理。 如果选中此框，将在打开标记指定的浏览器中打开服务器端重定向。 有关详细信息，请参阅`allow-redirect`[更新后的架构属性](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance#updated-schema-attributes)。
6. 在“ **注释**”框中键入有关站点的任何注释。 管理员只有在使用此工具时才能看到注释，这些注释将保留在站点列表 xml 中。
7.  **SelectAdd** 将网站添加到网站列表。

### <a name="add-shared-cookies-to-your-site-list"></a>将共享 Cookie 添加到网站列表

使用以下步骤将单个共享 Cookie 添加到网站列表。 若要了解有关 Cookie 共享的详细信息，请参阅 [Microsoft Edge 和 Internet Explorer 之间的 Cookie 共享](/deployedge/edge-ie-mode-add-guidance-cookieshare)。

1. 在Enterprise站点列表管理器中，选择 **“添加共享 Cookie**”。
2. 在“域”框中输入要添加的 **域** 。 在 **Cookie 名称框中输入 Cookie 的** 名称。
3. 如果 Cookie 是仅限主机的 Cookie，请 **仅检查主机**。
4. 如果需要，请在 **“路径** ”框中输入路径。
5. 从 **源引擎** 列表中选择以下选项之一：

   - **MSEdge**。 将会话 Cookie 从Microsoft Edge共享到 Internet Explorer。
   - **IE11**。 从 Internet Explorer 共享会话 Cookie 以Microsoft Edge。
   - **两者。** 在 Microsoft Edge 和 Internet Explorer 中共享会话 Cookie。

6. 在“ **批注** ”框中输入有关共享 Cookie 的任何注释。
7. 选择 **“添加** ”以添加共享 Cookie。

### <a name="export-site-list-to-xml"></a>将站点列表导出到 XML

使用 Enterprise Site List Manager 创建企业模式站点列表后，可以将这些内容导出到 Enterprise Mode (.EMIE) 文件。

> [!NOTE]
> 此文件包含所有 URL 和共享 Cookie，应存储在安全的位置。

若要导出站点列表，请按照以下步骤操作：

1. 在Enterprise站点列表管理器中，选择 **“导出到 XML**”。
2. 输入**版本号**和**文件名**。
3. 选择 **“导出**”。

可以通过本地方式保存文件，也可以将文件保存到网络共享。 但是，你必须确保将文件部署到注册表项中的指定位置。 有关更多信息，请参阅 [打开 Internet Explorer 模式并使用站点列表](./edge-ie-mode-policies.md)。

### <a name="import-multiple-sites-and-shared-cookies-to-your-site-list"></a>将多个站点和共享 Cookie 导入到网站列表

创建.xml文件后，可以使用 **“从 XML 导**入”将网站或共享 Cookie 批量添加到编辑器。

如果要替换编辑器中的所有内容，请选择省略号 (**...**) ，然后选择 **“清除列表**”。 清除编辑器后，请使用以下步骤导入站点列表。

1. 在Enterprise站点列表管理器中，**从 XML 中选择“导入**”。
2. 选择 **“选择文件** ”以选择网站列表，将包含的网站或共享 Cookie 添加到该工具。 选择要添加的网站列表，然后选择 **“打开**”。

   “导入”支持的格式.xml、.emie 或.txt，其中包含Enterprise模式站点列表的 v.2 架构。 参阅 [企业模式架构 v.2 指南](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)。

3.  **SelectLoadto**  将网站或共享 Cookie 从文件添加到编辑器。

可以通过本地方式保存文件，也可以将文件保存到网络共享。 但是，你必须确保将文件部署到注册表项中的指定位置。 有关更多信息，请参阅 [打开 Internet Explorer 模式并使用站点列表](./edge-ie-mode-policies.md)。

### <a name="edit-sites-in-your-site-list"></a>编辑站点列表中的站点

 可以在 Enterprise Site List Manager 中编辑现有站点条目的属性。 你还可以添加、移除或删除相关联的注释。

1. 在Enterprise站点列表管理器中，选择省略号 (**...**) ，然后为要编辑的 URL 选择 **“编辑网站**”。
2. 可以编辑站点条目的任何属性（URL 除外）。 完成编辑后选择 **“保存** ”。

   > [!NOTE]
   > 如果要删除站点条目，请选择步骤 1 中的“**删除站点**”。

3. 选择 **“导出到 XML**”，并保存更新后的文件。

可以通过本地方式保存文件，也可以将文件保存到网络共享。 但是，你必须确保将文件部署到注册表项中的指定位置。 有关更多信息，请参阅 [打开 Internet Explorer 模式并使用站点列表](./edge-ie-mode-policies.md)。

### <a name="edit-shared-cookies-in-your-site-list"></a>编辑网站列表中的共享 Cookie

可以编辑Enterprise站点列表管理器中现有共享 Cookie 条目的属性。 你还可以添加、移除或删除相关联的注释。 使用以下步骤编辑共享 Cookie。

1. 在Enterprise站点列表管理器中，选择省略号 (**...**) ，然后为要编辑的域选择 **“编辑 Cookie**”。
2. 可以编辑网站条目的任何属性，但域除外。 完成编辑后选择 **“保存** ”。

> [!NOTE]
> 如果要删除共享 Cookie 条目，请在步骤 1 中选择 **“删除共享 Cookie** ”。

### <a name="preview-your-site-list-in-xml-format"></a>以 XML 格式预览站点列表

在导出并保存到站点列表位置之前，可以以 XML 格式预览编辑器中的网站和共享 Cookie。 选择 **XML 预览** 以在新选项卡中打开文件。

### <a name="search-in-the-enterprise-site-list-manager"></a>在 Enterprise Site List Manager 中搜索

可以搜索以查看特定网站或共享 Cookie 是否已显示在网站列表中，以便不再尝试添加它。

若要搜索，请在编辑器右上角的搜索框中键入 URL 或域的一部分。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [关于 IE 模式](./edge-ie-mode.md)
- [企业模式架构 v.2 指南](/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)
- [其他企业模式信息](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)