---
title: IE 模式的本地站点列表
ms.author: shisub
author: AndreaLBarr
manager: srugh
ms.date: 09/13/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 了解如何启用本地站点列表并轻松访问 IE 模式
ms.openlocfilehash: 8130a835cd803f5cdeb50f825ccee895f35f62e3
ms.sourcegitcommit: c3d63d913eb15e7dbeb9f45b5f28fc841b46bce1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2021
ms.locfileid: "12016561"
---
## <a name="local-site-list-for-ie-mode"></a>IE 模式的本地站点列表

>[!Note]
> Internet Explorer 11 桌面应用程序将于 2022 年 6 月 15 日停用并停止支持（若要查看包含内容的列表， [请参阅常见问题解答](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)）。 现在使用的 IE11 应用和网站可以在 Microsoft Edge 的 Internet Explorer 模式下打开。 [在此处了解详细信息](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。

本文介绍如何配置对 IE 模式Internet Explorer访问 (IE 模式) 并允许在组织中使用本地站点列表。

> [!NOTE]
> 本文适用于 Microsoft Edge 92 或更高版本。

### <a name="prerequisites"></a>必备条件

1. Windows 更新

- Windows 10版本 1909 - [KB5003698](https://support.microsoft.com/topic/june-15-2021-kb5003698-os-build-18363-1645-preview-1ecf117e-1f89-40f9-a0a5-ed5766737620)或更高版本  

- Windows 10，版本 2004;Windows 10 20H2 和 Windows 10 版本 21H1 – [KB5003690](https://support.microsoft.com/topic/june-21-2021-kb5003690-os-builds-19041-1081-19042-1081-and-19043-1081-preview-11a7581f-2a01-47d5-ba12-431709ee2248)或更高版本

2. Microsoft Edge版本 92 (92.0.925.0 或更高版本) 

## <a name="overview"></a>概述

IE 模式由 Enterprise 站点列表的配置提供电源。 当你在站点列表上标识和配置站点以使用 IE 模式时，你的用户不再需要等待或回退到独立 IE11 应用程序。

从 Microsoft Edge版本 92 开始，可以更轻松地重复访问未配置的*IE*模式站点。 用户可以在 IE 模式下重新加载网站。 他们可以将这些网站添加到其本地站点列表，以在 30 天内以 IE 模式自动呈现，同时更新组织的网站列表。 在 [环境中禁用 IE11](/deployedge/edge-ie-disable-ie11) 后，用户不再仅依赖于组织的站点列表。

可以通过组织的组策略配置此体验。

注意：*未配置的*站点需要 IE 模式，但不配置为在 IE 模式下在 Enterprise 站点列表中打开。

## <a name="local-site-list-experience"></a>本地站点列表体验

若要启用本地站点列表体验，用户可以转到*URL* edge://settings/defaultBrowser，将"允许以Internet Explorer重新加载网站"**设置为****"允许"。**

:::image type="content" source="media/Edge-hybrid-IE-mode/internet-explorer-compatibilitiy.png" alt-text="Internet Explorer兼容性":::

>[!Note]  
>
>1. 如果已经通过 *InternetExplorerIntegrationTestingAllowed* 策略启用 IE 模式测试，则会看到此设置，但除非明确启用 *InternetExplorerIntegrationReloadInIEModeAllowed* 策略，否则此设置将灰显。
>
>2. 如果 **"允许以默认模式** Internet Explorer重新加载网站"设置为 **"** 默认"，则用户可能能够在 IE 模式下重新加载网站（如果他们的现有 Internet Explorer 11 用法）。  

启用此设置后，用户可以通过选择 设置 和更多 (省略号图标 ...) > Reload in Internet Explorer 模式，在 IE**模式下重新加载网站**。 当用户 **右键单击** 选项卡Internet Explorer，也可以选择"重新加载"选项卡，或在右键单击链接时选择"打开新 **Internet Explorer** 模式"选项卡中的链接。

:::image type="content" source="media/Edge-hybrid-IE-mode/reload-in-internet-exploror-mode-screenshot.png" alt-text="在 Internet Explorer 模式下重新加载":::

" **在Internet Explorer** 模式下重新加载"图标可以固定到工具栏。 工具栏按钮允许用户轻松进入和退出 IE 模式，并且可以通过 edge://settings/appearance *URL* 进行管理。

:::image type="content" source="media/Edge-hybrid-IE-mode/reload-in-internet-exploror-mode-icon-screenshot.png" alt-text="在 Internet Explorer 模式下重新加载图标":::

>[!Note]
>如果用户位于已位于组织的 Enterprise 模式站点列表中的站点，则以 (或 Exit) Internet Explorer 模式重新加载的选项将可见，但灰显。

选择该选项时，网站在 IE 模式下重新加载。 IE 模式指示器图标在地址栏左侧可见，并且飞出显示一个选项，用户可以在下次切换为"在Internet Explorer打开页面"。 这会将用户位于的特定页面添加到本地站点列表，并会在接下来 30 天内在 IE 模式下自动打开。

:::image type="content" source="media/Edge-hybrid-IE-mode/site-has-been-reloaded-in-ie-mode-screenshot.png" alt-text="此页面在 Internet Explorer 模式下打开":::

在 IE 模式下重新加载网站后，"页内"导航将保持 IE 模式 (例如，页面上的链接、脚本或表单，或者从另一个"页内"导航菜单的服务器端重定向) 。  

在 IE 模式下时，用户将看到一个横幅，指示他们位于 IE 模式下，选择"离开 IE 模式"，以及将 IE 模式图标固定到工具栏 (（如果尚未固定) ）。

:::image type="content" source="media/Edge-hybrid-IE-mode/ie-mode-banner-screenshot.png" alt-text="IE 模式横幅":::

用户可以选择退出 IE 模式，使用横幅上的"离开"按钮、固定的 IE 模式图标或 设置 以及更多 (省略号图标 **...) > Exit Internet Explorer 模式**，否则当非"页内"导航发生时，Microsoft Edge 将自动退出 IE 模式 (例如，使用地址栏、后退按钮或收藏的链接) 。

条目在本地网站列表中保留默认期限为 30 天。 我们建议在模式站点列表中为组织配置Enterprise站点。 本地网站列表将确保用户在更新组织的网站列表时可以继续其工作流，而不会中断。 在 31 日，当用户导航到网站时，他们将看到一个横幅，说明该网站将不再在 IE 模式下加载。 用户可以将其添加回本地站点列表（如果他们选择这样做）。

:::image type="content" source="media/Edge-hybrid-IE-mode/page-will-no-longer-load-in-ie-mode-screenshot.png" alt-text="在 IE 模式下，页面将不再加载":::

## <a name="policies-to-configure-the-use-of-local-site-lists-for-ie-mode"></a>配置 IE 模式本地站点列表使用的策略

有两个组策略可用于配置本地站点列表Microsoft Edge。 这些策略是：

### *<a name="policy-internetexplorerintegrationreloadiniemodeallowed"></a>策略：InternetExplorerIntegrationReloadInIEModeAllowed*

此策略对应于"Microsoft Edge模式下重新加载网站"Internet Explorer设置。 可通过 *edge://settings/defaultbrowser* URL 来访问此设置。

- 如果启用此策略，则用户可以在 IE 模式下重新加载站点，方式为选择"设置"， (省略号**图标...">在Internet Explorer重新加载"。** 当用户右键单击选项卡时 **，Internet Explorer** 模式选择"重新加载"选项卡，或在右键单击链接时选择"新建 Internet Explorer 模式" **选项卡** 中的"打开链接"。
用户可以选择Microsoft Edge以后对网站使用 IE 模式。 此选项将默认记住 30 天，并且可以使用 *策略 InternetExplorerIntegrationLocalSiteListExpirationDays 进行管理*。

- 如果禁用此策略，则不允许用户在 IE 模式下重新加载未配置的网站。

- 如果未配置此策略，我们将根据最近使用 11 Internet Explorer IE 模式显示用户重新加载未配置网站的选项。

请注意，此策略优先于 [InternetExplorerIntegrationTestingAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationtestingallowed) 策略的配置方式，并且该策略将被禁用。

### *<a name="policy-internetexplorerintegrationlocalsitelistexpirationdays"></a>策略：InternetExplorerIntegrationLocalSiteListExpirationDays*

此策略可用于调整网站在用户的本地站点列表中保留的天数。  

- 如果禁用或不配置此策略，则使用默认值 30 天。

- 如果启用该策略，则必须输入一个介于 0 到 90 天之间的值，以使网站位于用户的本地站点列表中。

如果禁用了 *InternetExplorerIntegrationReloadInIEModeAllowed* 策略，此策略将不起作用。

**注意：**

本地站点列表当前不会跨设备同步。 此改进目前适用于我们的积压工作，我们将在可用时进行更新。

## <a name="see-also"></a>另请参阅

禁用 Internet Explorer 11 - [禁用 Internet Explorer 11 |Microsoft Docs](/deployedge/edge-ie-disable-ie11)

配置 IE 模式策略 - [配置 IE 模式策略|Microsoft Docs](/deployedge/edge-ie-mode-policies)

