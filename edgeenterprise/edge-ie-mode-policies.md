---
title: 配置 IE 模式策略
ms.author: collw
author: AndreaLBarr
manager: srugh
ms.date: 07/23/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 配置 IE 模式策略
ms.openlocfilehash: 7ca8dffb0bc20acf954cf0f272f3894b39355846
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "11978968"
---
# <a name="configure-ie-mode-policies"></a>配置 IE 模式策略

>[!Note]
> Internet Explorer 11 桌面应用程序将于 2022 年 6 月 15 日停用并停止支持（若要查看包含内容的列表，[请参阅常见问题解答](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)）。 现在使用的 IE11 应用和网站可以在 Microsoft Edge 的 Internet Explorer 模式下打开。 [在此处了解详细信息](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。

本文介绍了如何配置 IE 模式策略。

> [!NOTE]
> 本文适用于 Microsoft Edge **Stable**、**Beta** 和 **Dev** 渠道版本 77 或更高版本。

若要配置 IE 模式，需要完成以下三步：

1. [配置 Internet Explorer 集成](#configure-internet-explorer-integration)
2. [将网站从 Microsoft Edge 重定向到 IE 模式](#redirect-sites-from-microsoft-edge-to-ie-mode)
3. （可选）[将网站从 IE 重定向到 Microsoft Edge](#redirect-sites-from-ie-to-microsoft-edge)

    1. 如果已准备好禁用 IE11 应用，请按照 [禁用 Internet Explorer 11 应用"中的步骤](/deployedge/edge-ie-disable-ie11)
    2. 否则，请按照"将网站从 IE 重定向到 Microsoft Edge [中的其余步骤](/deployedge/edge-ie-mode-policies#redirect-sites-from-ie-to-microsoft-edge)

> [!NOTE]
> 可通过 Intune 来配置启用 IE 模式的策略。 有关详细信息，请参阅[将 Microsoft Edge 添加到 Microsoft Intune](/intune/apps/apps-windows-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)和[使用 Microsoft Intune 配置 Microsoft Edge 策略](./configure-edge-with-intune.md)。

## <a name="configure-internet-explorer-integration"></a>配置 Internet Explorer 集成

可以将 Internet Explorer 配置为，直接在 Microsoft Edge（IE 模式）中打开。 也可以将 Internet Explorer 配置为，使用独立 Internet Explorer 11 窗口打开。 大多数用户倾向于直接在 Microsoft Edge 的 IE 模式下打开网站。

### <a name="enable-internet-explorer-integration-using-group-policy"></a>使用组策略启用 Internet Explorer 集成

1. 下载并使用最新的 [Microsoft Edge 策略模板](https://www.microsoft.com/en-us/edge/business/download)。
2. 打开组策略编辑器。
3. 单击**用户配置/计算机配置** > **管理模板** > **Microsoft Edge**。
4. 双击**配置 Internet Explorer 集成**。
5. 选中**已启用**。
6. 在**选项**下，将下拉列表值设置为
   -  **Internet Explorer 模式**：如果希望在 Microsoft Edge 中的 IE 模式下打开网站
   -  **Internet Explorer 11** 如果您希望网站在独立的 Internet Explorer 11 窗口中打开 (此选项在 2022 年 6 月 15 日之后将停用 Internet Explorer 11 桌面应用程序并退出支持。  2022 年 6 月 15 日之后，当 IE11 不再可用时，此选项的行为与 Internet Explorer **模式** 选项相同。)   
   -  **无**：如果希望阻止用户通过 edge://flags 或命令行来配置 Internet Explorer 模式

   > [!NOTE]
   > 将策略设置为**禁用**意味着 IE 模式已由策略禁用，但可以通过 edge://flags 或命令行选项进行设置。
7. 单击**确定**或**应用**以保存此策略设置。

## <a name="redirect-sites-from-microsoft-edge-to-ie-mode"></a>将网站从 Microsoft Edge 重定向到 IE 模式

若要识别应在 IE 模式下打开的网站，可以使用以下两种方法：

- （推荐）[配置企业站点列表中的站点](#configure-sites-on-the-enterprise-site-list)
- [配置所有 Intranet 站点](#configure-all-intranet-sites)

### <a name="configure-sites-on-the-enterprise-site-list"></a>配置企业站点列表中的站点

你可以使用以下组策略配置要在 IE 模式下打开的特定站点：

- [使用企业模式 IE 网站列表](#configure-using-the-use-the-enterprise-mode-ie-website-list-policy) (Internet Explorer)
- [配置企业模式站点列表](#configure-using-the-configure-the-enterprise-mode-site-list-policy)（Microsoft Edge 78 或更高版本）<br/>使用此策略，可以为 Microsoft Edge 单独创建 Enterprise Mode Site List。 如果“配置 Internet Explorer 集成”已启用，那么启用此策略会重写“使用企业模式 IE 网站列表”策略中的设置。 禁用或未配置此策略不会影响“配置 Internet Explorer 集成”策略的默认行为。
    > [!NOTE]
    > 配置 Microsoft Edge 策略并不是一项强制性要求。 许多组织将此策略用于重写目的，便于他们使用 IE 策略将当前网站列表定位到所有用户，并使用 Microsoft Edge 策略更轻松地将更新后的版本定位到试点网站用户。

有关模式站点列表Enterprise，请参阅使用Enterprise[站点列表管理器。](/deployedge/edge-ie-mode-site-list-manager)


### <a name="configure-using-the-use-the-enterprise-mode-ie-website-list-policy"></a>使用“使用企业模式 IE 网站列表”策略进行配置

IE 模式可使用为 Internet Explorer 配置 Enterprise Site List 的现有策略，这样你就能创建和维护一个列表了。

1. 创建或重用 Site List XML
    1. 所有具有 _\<open-in\>IE11\</open-in\>_ 元素的站点现在都将在 IE 模式下打开。
2. 打开组策略编辑器。
3. 单击**用户配置/计算机配置** > **管理模板** > **Windows 组件** > **Internet Explorer**。
4. 双击**使用企业模式 IE 网站列表**。
5. 选中**已启用**。
6. 在**选项**下，键入网站列表的位置。 可以使用以下位置之一：
    - （推荐）HTTPS 位置：https****://iemode/sites.xml****
    - 本地网络文件：**\\\network\shares\sites.xml**
    - 本地文件：**file:///c:/Users/\<user\>/Documents/sites.xml**
7. 单击**确定**或**应用**以保存这些设置。

### <a name="configure-using-the-configure-the-enterprise-mode-site-list-policy"></a>使用“配置 Enterprise Mode Site List”策略进行配置

也可以使用单独的 Microsoft Edge 策略来配置 IE 模式。 使用此附加策略，可以重写 IE 网站列表。 例如，一些组织会将生产网站列表定位到所有用户。 然后，你可以使用此策略将试点网站列表部署到一小组用户。

1. 创建或重用 Site List XML
    1. 所有具有 _\<open-in\>IE11\</open-in\>_ 元素的站点现在都将在 IE 模式下打开。
2. 打开组策略编辑器。
3. 单击**用户配置/计算机配置** > **管理模板** > **Microsoft Edge**。
4. 双击**配置企业模式站点列表**。
5. 选中**已启用**。
6. 在**选项**下，键入网站列表的位置。 可以使用以下位置之一：
    - （推荐）HTTPS 位置：https****://iemode/sites.xml**** <!--Trying to keep this from being an active link in MD -->
    - 本地网络文件：**\\\network\shares\sites.xml**
    - 本地文件：**file:///c:/Users/\<user\>/Documents/sites.xml**
7. 单击**确定**或**应用**以保存这些设置。

### <a name="configure-all-intranet-sites"></a>配置所有 Intranet 站点

可以将 IE 模式配置为，用于本地 Intranet 区域中的所有网站。 可以使用 Enterprise Mode Site List 从 IE 模式中删除各个网站。

>[!NOTE]
>
> 本地 Intranet 区域不但包含显式添加的网站，还分配有通过启发分配到此区域的网站。 这可以包括无点主机名（例如，https****://payroll****），以及代理配置脚本配置为不使用代理的网站。 如果外部参与方控制 DNS 或代理，它们可能会强制让网站在 IE 模式下运行。

1. 打开本地组策略编辑器。
2. 单击**用户配置/计算机配置** > **管理模板** > **Microsoft Edge**。
3. 双击**将所有 Intranet 站点发送到 Internet Explorer**。
4. 选择**已启用**，然后单击**确定**或**应用**以保存策略设置。

## <a name="redirect-sites-from-ie-to-microsoft-edge"></a>将网站从 IE 重定向到 Microsoft Edge

可以阻止用户使用 Internet Explorer 浏览不需要 IE 模式的网站。 Internet Explorer 可自动将网站列表中没有的网站重定向到 Microsoft Edge。

1. 打开组策略编辑器。
2. 依次单击 **“计算机配置”** > **“管理工具”** > **“Windows 组件”** > **“Internet Explorer”**。
3. 双击 **“将 Enterprise Mode Site List 中不包含的所有网站发送到 Microsoft Edge”**。
4. 选中“已启用”****
5. 单击**确定**或**应用**以保存这些设置。
6. 双击“配置要用于打开重定向网站的 Microsoft Edge 渠道”****。
7. 选中**已启用**。
8. 在“选项”**** 下，选择要使用的前三个渠道选项，Internet Explorer 会重定向到用户在相应设备上安装的排名最靠前的选项：
   - Microsoft Edge 稳定渠道
   - Microsoft Edge Beta 版本 77 或更高版本
   - Microsoft Edge Dev 版本 77 或更高版本
   - Microsoft Edge Canary 版本 77 或更高版本
   - Microsoft Edge 版本 45 或更低版本
9. 单击**确定**或**应用**以保存这些设置。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [关于 IE 模式](./edge-ie-mode.md)
- [其他企业模式信息](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
