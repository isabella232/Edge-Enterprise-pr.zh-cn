---
title: IE 模式Internet Explorer (本地) 列表
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 11/15/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 了解如何启用本地站点列表并轻松访问 IE 模式
ms.openlocfilehash: 8113b3baa613a0c19c80a738b3bbddfc330ec3ba
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2022
ms.locfileid: "12297953"
---
# <a name="configure-local-site-list-for-internet-explorer-ie-mode"></a>为 IE Internet Explorer (配置) 列表

>[!Note]
> 有关 Internet Explorer 11 桌面应用程序的范围列表，请参阅 [Internet Explorer 11](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549) 桌面应用停用常见问题解答) 。2022 年 6 月 15 日将停用 (。 现在使用的 IE11 应用和网站可以在 Microsoft Edge 的 Internet Explorer 模式下打开。 若要了解更多信息，请参阅 Internet Explorer [on Windows 10 的未来Microsoft Edge。](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)

本文介绍如何在 IE 模式下配置Internet Explorer访问 (IE) 并允许在组织中使用本地站点列表。

> [!NOTE]
> 本文适用于 Microsoft Edge版本 92 或更高版本。

## <a name="prerequisites"></a>必备条件

1. Windows 更新

   - Windows 10，版本 1909 - [KB5003698](https://support.microsoft.com/topic/june-15-2021-kb5003698-os-build-18363-1645-preview-1ecf117e-1f89-40f9-a0a5-ed5766737620)或更高版本  

   - Windows 10，版本 2004;Windows 10 20H2 和 Windows 10 版本 21H1 – [KB5003690](https://support.microsoft.com/topic/june-21-2021-kb5003690-os-builds-19041-1081-19042-1081-and-19043-1081-preview-11a7581f-2a01-47d5-ba12-431709ee2248)或更高版本

2. Microsoft Edge版本 92 (92.0.902.55 或更高版本) 

> [!IMPORTANT]
> 目前，本地网站列表功能Windows Server 2016本地网站列表功能。

## <a name="overview"></a>概述

IE 模式由 IE 模式站点Enterprise配置提供电源。 当你在站点列表上标识和配置站点以使用 IE 模式时，你的用户不再需要等待或回退到独立 IE11 应用程序。

从 Microsoft Edge版本 92 开始，可以更轻松地重复访问未配置的*IE*模式站点。 用户可以在 IE 模式下重新加载网站。 他们可以将这些网站添加到其本地站点列表，以在 IE 模式下自动呈现 30 天，同时更新组织的网站列表。 在 [环境中禁用 IE11](/deployedge/edge-ie-disable-ie11) 后，用户不再仅依赖于组织的站点列表。

可以通过组织的组策略配置此体验。

> [!NOTE]
> 未*配置的站点*需要 IE 模式，但不配置为在 IE 模式下在"Enterprise站点列表"中打开。

## <a name="enable-the-local-site-list-experience"></a>启用本地站点列表体验

若要启用本地站点列表体验，用户可以转到*URL* edge://settings/defaultBrowser，将"允许以Internet Explorer重新加载网站"**设置为****"允许"。**

:::image type="content" source="media/Edge-hybrid-IE-mode/internet-explorer-compatibilitiy.png" alt-text="Internet Explorer兼容性":::

>[!Note]  
>
>1. 如果已经通过 *InternetExplorerIntegrationTestingAllowed* 策略启用 IE 模式测试，你将看到此设置，但除非明确启用 *InternetExplorerIntegrationReloadInIEModeAllowed* 策略，否则它将灰显。
>
>2. 如果 **"允许以默认模式** Internet Explorer重新加载网站"设置为 **"** 默认"，则用户可能会能够在 IE 模式下重新加载网站（如果他们的现有 Internet Explorer 11 用法）。  

启用此设置后，用户可以通过选择 设置 和更多 (省略号图标 **...) > Reload**in Internet Explorer 模式，在 IE 模式下重新加载网站。 当用户 **右键单击** 某个选项卡Internet Explorer，也可以选择"重新加载"选项卡，或在右键单击链接时选择"在新的 **Internet Explorer** 模式"选项卡中打开链接。

:::image type="content" source="media/Edge-hybrid-IE-mode/reload-in-internet-exploror-mode-screenshot.png" alt-text="在 Internet Explorer 模式下重新加载":::

" **在Internet Explorer重新加载** "图标可以固定到工具栏。 工具栏按钮允许用户轻松进入和退出 IE 模式，并且可以通过 edge://settings/appearance *URL* 进行管理。

:::image type="content" source="media/Edge-hybrid-IE-mode/reload-in-internet-exploror-mode-icon-screenshot.png" alt-text="在 Internet Explorer 模式下重新加载图标":::

>[!Note]
>如果用户位于已位于组织的 Enterprise 模式站点列表中的站点中，则"在 ("或"退出) Internet Explorer"模式下重新加载的选项将可见，但灰显。

选择该选项时，网站在 IE 模式下重新加载。 IE 模式指示器图标在地址栏左侧可见，并且飞出显示一个选项，用户可以在下次切换为"在Internet Explorer打开页面"。 这会将用户位于的特定页面添加到本地站点列表，并会在接下来 30 天内在 IE 模式下自动打开。

:::image type="content" source="media/Edge-hybrid-IE-mode/site-has-been-reloaded-in-ie-mode-screenshot.png" alt-text="此页面在 Internet Explorer 模式下打开":::

在 IE 模式下重新加载网站后，"页内"导航将保持 IE 模式 (例如，链接、脚本、页面上的表单或另一个"页内"导航) 的服务器端重定向。  

在 IE 模式下时，用户将看到一个横幅，指示他们位于 IE 模式下，选择"离开 IE 模式"，将 IE 模式图标固定到工具栏 (（如果尚未固定) ）。

:::image type="content" source="media/Edge-hybrid-IE-mode/ie-mode-banner-screenshot.png" alt-text="IE 模式横幅":::

用户可以选择退出 IE 模式，使用横幅上的"离开"按钮、固定的 IE 模式图标或 设置 等 (省略号图标 **...) > Exit Internet Explorer 模式**，否则当非"页内"导航发生时，Microsoft Edge 将自动退出 IE 模式 (例如，使用地址栏、后退按钮、 或收藏的链接) 。

条目在本地网站列表中保留默认期限为 30 天。 我们建议在模式站点列表中为组织配置Enterprise站点。 本地网站列表将确保用户在更新组织的网站列表时可以继续其工作流，而不会中断。 在 31 日，当用户导航到网站时，他们将看到一个横幅，说明该网站将不再在 IE 模式下加载。 用户可以将其添加回本地站点列表（如果他们选择这样做）。

:::image type="content" source="media/Edge-hybrid-IE-mode/page-will-no-longer-load-in-ie-mode-screenshot.png" alt-text="在 IE 模式下，页面将不再加载":::

## <a name="policies-to-configure-the-use-of-local-site-lists-for-ie-mode"></a>配置 IE 模式本地站点列表使用的策略

有两个组策略可用于在 Microsoft Edge 中配置本地站点列表体验。 这些策略是：

### <a name="policy-internetexplorerintegrationreloadiniemodeallowed"></a>策略：InternetExplorerIntegrationReloadInIEModeAllowed

此策略对应于"Microsoft Edge模式下重新加载网站"Internet Explorer设置。 可通过 *edge://settings/defaultbrowser* URL 来访问此设置。

- 如果启用此策略，则用户可以在 IE 模式下重新加载站点，方式为选择"设置"， (省略号**图标...">在Internet Explorer重新加载"。** 当用户 **右键单击** 选项卡时，Internet Explorer模式选择"重新加载"选项卡，或在右键单击某个链接时选择"在新的 **Internet Explorer** 模式"选项卡中打开链接。
用户可以选择Microsoft Edge以后对网站使用 IE 模式。 此选项将默认记住 30 天，并且可以使用 *策略 InternetExplorerIntegrationLocalSiteListExpirationDays 进行管理*。

- 如果禁用此策略，则不允许用户在 IE 模式下重新加载未配置的网站。

- 如果未配置此策略，我们将根据最近的 11 Internet Explorer在 IE 模式下显示重新加载未配置网站的选项。

请注意，此策略优先于 [InternetExplorerIntegrationTestingAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationtestingallowed) 策略的配置方式，并且该策略将被禁用。

### <a name="policy-internetexplorerintegrationlocalsitelistexpirationdays"></a>策略：InternetExplorerIntegrationLocalSiteListExpirationDays

此策略可用于调整网站在用户的本地站点列表中保留的天数。  

- 如果禁用或不配置此策略，则使用默认值 30 天。

- 如果启用该策略，则必须输入一个介于 0 到 90 天之间的值，以使网站位于用户的本地站点列表中。

如果禁用了 *InternetExplorerIntegrationReloadInIEModeAllowed* 策略，此策略将不起作用。

> [!NOTE]
> 本地站点列表当前未跨设备同步。 此改进目前位于我们的积压工作积压工作中，我们将在此功能可用时更新它。

## <a name="see-also"></a>另请参阅

- 禁用 Internet Explorer 11 - [禁用Internet Explorer 11](/deployedge/edge-ie-disable-ie11)
- 配置 IE 模式策略 - [配置 IE 模式策略](/deployedge/edge-ie-mode-policies)
