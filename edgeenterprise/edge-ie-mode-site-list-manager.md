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
# Microsoft Edge 中的 Enterprise Site List Manager

本文介绍如何启用和访问 Microsoft Edge 中的 Enterprise Site List Manager 以创建、编辑和导出 Internet Explorer 模式的 Enterprise Mode Site List。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 89 或更高版本。

## 概述

Enterprise Site List Manager 是[独立 Enterprise Mode Site List Manager 工具](https://www.microsoft.com/download/details.aspx?id=49974)的浏览器内版本，可让创建、编辑和导出组织的站点列表。

通过 Microsoft Edge 中的 Enterprise Site List Manager，可以进一步改进用于 Internet Explorer 模式的工具。 独立工具将继续在下载中心中提供，但无法获得任何功能更新。

## 允许访问 Enterprise Site List Manager

可以使用 [EnterpriseModeSiteListManagerAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enterprisemodesitelistmanagerallowed) 组策略配置对工具的访问权限。

如果启用，用户将在 *edge://compat* 的左侧导航窗格中看到一个名为 Enterprise Site List Manager 的选项。 如果禁用，用户将不会在左侧导航窗格中看到 Enterprise Site List Manager 的入口点。 这是默认行为。

## 使用 Enterprise Site List Manager

Enterprise Site List Manager 工具使用 v.2 版本的架构。 如果将 v.1 版本架构导入到 Enterprise Site List Manager（架构 v.2）中，XML 将被保存到 v.2 版本的架构。

### 将单个站点添加到站点列表  

使用以下步骤将单个站点添加到站点列表。

> [!NOTE]
> 你只能添加特定的 URL，而无法添加 Internet 或 Intranet 区域。

1. 在 Enterprise Site List Manager 中，单击“ **添加站点**”。
2. 在 URL 框中输入要添加的站点网址，例如： <domain>.com or <domain>.com/<path> 。
3. 从“**打开方式**” 列表中选择以下选项之一：

   - **IE11**。 在 IE11 应用程序中打开站点。
   - **IE 模式**。 如果启用，在 Microsoft Edge 的 Internet Explorer 模式中打开站点，否则在 IE11 应用中打开站点。 请参阅  [Microsoft Edge 上的 Internet Explorer 模式 ](https://docs.microsoft.com/deployedge/edge-ie-mode)。
   - **MSEdge**。 在 Microsoft Edge 中打开站点。
   - **可配置**。 允许站点参与 IE 模式引擎确定。 参见 [IE 模式下可配置的站点](https://docs.microsoft.com/deployedge/edge-learnmore-configurable-sites-ie-mode)
   - **无**。 在用户选择的任意浏览器中打开。  

4. 在 **兼容模式**下，选择下列选项之一：

   - **IE8Enterprise**。 在 IE8 企业模式中加载站点。
   - **IE7Enterprise**。 在 IE7 企业模式中加载站点。
   - **IE[x]**。 其中 [x] 表示文档模式编号，在指定的文档模式中加载站点。
   - **默认模式**。 使用适用于页面的默认兼容性模式加载站点。

   域内的路径可能需要对该域本身使用其他兼容性模式。 例如，域在默认 IE11 浏览器中可能没有问题，但路径可能有问题，并且需要使用企业模式。 如果你之前添加过域，则你的原始兼容性选择仍处于选中状态。 但是，如果域是全新的，将自动选择“ **IE8 企业模式** ”。

   由于企业模式优先于文档模式，因此已包含在企业模式站点列表中的站点不会受此更新影响，并将继续照常在企业模式中加载。 有关使用文档模式的更具体的信息，请参阅 [使用文档模式和企业模式站点列表修复 Web 兼容性问题](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/fix-compat-issues-with-doc-modes-and-enterprise-mode-site-list)。

5. **允许重定向** 复选框适用于服务器端重定向的处理。 如果选中此框，将在打开标记指定的浏览器中打开服务器端重定向。 有关详细信息，请参阅 [这里](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance#updated-schema-attributes)。
6. 在“ **注释**”框中键入有关站点的任何注释。 管理员只有在使用此工具时才能看到注释，这些注释将保留在站点列表 xml 中。
7. 单击“ **添加**”将站点添加到站点列表。

### 将站点列表导出到 XML

使用 Enterprise Site List Manager 创建企业模式站点列表后，可以将这些内容导出到 Enterprise Mode (.EMIE) 文件。 

> [!NOTE]
> 此文件包括你的所有 URL（包括你的兼容性模式选择）并应存储在安全的位置。

若要导出站点列表，请按照以下步骤操作：

1. 在 Enterprise Site List Manager 中，单击**导出到 XML **。
2. 输入**版本号**和**文件名**。
3. 单击“**导出**”。

可以通过本地方式保存文件，也可以将文件保存到网络共享。 但是，你必须确保将文件部署到注册表项中的指定位置。 有关更多信息，请参阅 [打开 Internet Explorer 模式并使用站点列表](https://docs.microsoft.com/deployedge/edge-ie-mode-policies)。

### 将多个站点导入站点列表

创建 .xml 文件后，可以使用“**从 XML 导入**”将站点批量添加到编辑器中。

如果要替换编辑器中所有的内容，请单击省略号 (...) ，然后选择“**清除列表**”。 清除编辑器后，使用以下步骤导入站点。

1. 在 Enterprise Site List Manager 中，单击“**从 XML 导入**”。 
2. 单击“**选择文件**”以选择站点列表，将包含的站点添加到工具。 选取要添加的站点列表，然后单击“ **打开**”。 支持的导入格式有 .xml、.emie 或 .txt，其中包含 Enterprise Mode Site Lis v.2 架构。 参阅 [企业模式架构 v.2 指南](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)。
3. 单击“ **加载**” 以从文件 tp 编辑器添加站点。

可以通过本地方式保存文件，也可以将文件保存到网络共享。 但是，你必须确保将文件部署到注册表项中的指定位置。 有关更多信息，请参阅 [打开 Internet Explorer 模式并使用站点列表](https://docs.microsoft.com/deployedge/edge-ie-mode-policies)。

### 编辑站点列表中的站点

 可以在 Enterprise Site List Manager 中编辑现有站点条目的属性。 你还可以添加、移除或删除相关联的注释。

1. 在 Enterprise Site List Manager 中，单击省略号（...），然后为要编辑的 URL 选择“**编辑站点**”。
2. 可以编辑站点条目的任何属性（URL 除外）。 完成编辑后单击“**保存**”。

   > [!NOTE]
   > 如果要删除站点条目，请选择步骤 1 中的“**删除站点**”。

3. 单击“**导出到 XML**”。然后保存更新的文件。

可以通过本地方式保存文件，也可以将文件保存到网络共享。 但是，你必须确保将文件部署到注册表项中的指定位置。 有关更多信息，请参阅 [打开 Internet Explorer 模式并使用站点列表](https://docs.microsoft.com/deployedge/edge-ie-mode-policies)。

### 以 XML 格式预览站点列表

可以在编辑器中以 XML 格式预览站点，然后导出并保存到站点列表位置。 单击 **XML 预览** 以打开新选项卡中的文件。

### 在 Enterprise Site List Manager 中搜索

你可以搜索以查看特定站点是否已经显示在站点列表中，以便你无需再次尝试添加它。

若要进行搜索，请在编辑器右上角的“ **按 URL 筛选站点**”搜索框中键入 URL 的一部分。

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [关于 IE 模式](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [其他企业模式信息](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [其他“企业站点发现”信息](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery)
