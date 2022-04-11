---
title: Internet Explorer (IE) 模式的本地站点列表
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 03/24/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 了解如何启用本地站点列表和轻松访问 IE 模式
ms.openlocfilehash: 85aa6baa1abaa1a59f4e9cf9f2414f54ccf70cbb
ms.sourcegitcommit: dd8cdbd35726c795ddce917e549ddf17ee7f5290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "12473638"
---
# <a name="configure-local-site-list-for-internet-explorer-ie-mode"></a>为 Internet Explorer 配置本地站点列表 (IE) 模式

>[!Note]
> Internet Explorer 11 桌面应用程序将于 2022 年 6 月 15 日停用并停止支持， (获取范围列表，请参阅 [Internet Explorer 11 桌面应用停用常见问题解答](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)) 。 现在使用的 IE11 应用和网站可以在 Microsoft Edge 的 Internet Explorer 模式下打开。 若要了解详细信息，请参阅Windows 10[上的 Internet Explorer 的未来Microsoft Edge](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。

本文介绍如何配置对 Internet Explorer 模式的轻松访问 (IE 模式) 并允许在组织中使用本地站点列表。

> [!NOTE]
> 本文适用于Microsoft Edge版本 92 或更高版本。

## <a name="prerequisites"></a>必备条件

1. Windows 更新

   - Windows 11

   - Windows 10版本 1909 - [KB5003974](https://support.microsoft.com/topic/kb5003974-servicing-stack-update-for-windows-10-version-1909-june-15-2021-0e65680e-2d21-4a31-b97a-e24c022aeccf) 和 [KB5003698](https://support.microsoft.com/topic/june-15-2021-kb5003698-os-build-18363-1645-preview-1ecf117e-1f89-40f9-a0a5-ed5766737620) 或更高版本

   - Windows 10版本 2004;Windows 10版本 20H2 和 Windows 10，版本 21H - [KB5005260](https://support.microsoft.com/topic/kb5005260-servicing-stack-update-for-windows-10-version-2004-20h2-and-21h1-august-10-2021-ec4c5daa-2cec-4b06-be93-037f150fe3ba) 和 [KB5005101](https://support.microsoft.com/topic/september-1-2021-kb5005101-os-builds-19041-1202-19042-1202-and-19043-1202-preview-82a50f27-a56f-4212-96ce-1554e8058dc1) 或更高版本

2. Microsoft Edge版本 92 (92.0.902.55 或更高版本) 

> [!IMPORTANT]
> Windows Server 2016目前不支持此本地站点列表功能。

## <a name="overview"></a>概述

IE 模式由Enterprise模式站点列表的配置提供支持。 在网站列表中标识和配置站点以使用 IE 模式时，用户不再需要等待或回退到独立的 IE11 应用程序。

从Microsoft Edge版本 92 开始，对*未配置的* IE 模式站点的重复访问更为简单。 用户可以在 IE 模式下重新加载站点。 他们可以将这些网站添加到其本地网站列表，以在 IE 模式下自动呈现 30 天，同时更新组织的网站列表。 在环境中 [禁用 IE11](/deployedge/edge-ie-disable-ie11) 时，用户不再完全依赖于组织的网站列表。

可以通过组织的组策略配置此体验。

> [!NOTE]
> *未配置的*站点是需要 IE 模式但未配置为在 IE 模式下在Enterprise模式站点列表中打开的站点。

## <a name="enable-the-local-site-list-experience"></a>启用本地站点列表体验

若要启用本地站点列表体验，用户可以转到 URL *edge://settings/defaultBrowser* 并将 **允许在 Internet Explorer 模式下重新加载的站点** 设置为 **“允许**”。

:::image type="content" source="media/Edge-hybrid-IE-mode/internet-explorer-compatibilitiy.png" alt-text="Internet Explorer 兼容性":::

>[!Note]  
>
>1. 如果已通过 *InternetExplorerIntegrationTestingAllowed* 策略启用了 IE 模式测试，则会看到此设置，但除非显式启用 *InternetExplorerIntegrationReloadInIEModeAllowed* 策略，否则会灰显。
>
>2. 如果 **允许在 Internet Explorer 模式下重新加载的站点** 设置为 **默认**值，则如果用户具有现有的 Internet Explorer 11 使用情况，则他们也许能够在 IE 模式下重新加载站点。  

启用此设置后，用户可以通过选择**设置和更多 (省略号图标...) >在 Internet Explorer 模式下重新加载来重新加载**站点。 当用户右键单击某个选项卡或在新 Internet **Explorer 模式选项卡中**右键单击链接时，他们还可以**在 Internet Explorer 模式下选择“重新加载**”选项卡。

:::image type="content" source="media/Edge-hybrid-IE-mode/reload-in-internet-exploror-mode-screenshot.png" alt-text="在 Internet Explorer 模式下重新加载":::

Internet **Explorer 模式下的“重新加载** ”图标可以固定到工具栏。 工具栏按钮允许用户轻松进入和退出 IE 模式，并且可以通过 *edge://settings/appearance* URL 进行管理。

:::image type="content" source="media/Edge-hybrid-IE-mode/reload-in-internet-exploror-mode-icon-screenshot.png" alt-text="在 Internet Explorer 模式下重新加载图标":::

>[!Note]
>如果用户位于组织Enterprise模式站点列表中的站点上，则在 internet Explorer 模式下重载 (或退出) 选项将可见但灰显。

选择该选项后，站点会在 IE 模式下重新加载。 IE 模式指示器图标在地址栏左侧可见，浮出控件显示一个选项，用户可切换到下次在 Internet Explorer 模式下打开页面。 这会将用户所在的特定页面添加到本地站点列表，并将在未来 30 天内以 IE 模式自动打开。

:::image type="content" source="media/Edge-hybrid-IE-mode/site-has-been-reloaded-in-ie-mode-screenshot.png" alt-text="此页面在 Internet Explorer 模式下打开":::

在 IE 模式下重新加载站点后，“页面内”导航将保持 IE 模式， (例如，链接、脚本、页面上的窗体，或者从另一个“页面内”导航) 重定向服务器端。  

在 IE 模式下，用户将看到一个横幅，指示他们处于 IE 模式，即“离开 IE 模式”选项，如果工具栏尚未固定) ，则将其固定到工具栏 (。

:::image type="content" source="media/Edge-hybrid-IE-mode/ie-mode-banner-screenshot.png" alt-text="IE 模式横幅":::

用户可以选择使用横幅上的“离开”按钮、固定的 IE 模式图标或设置等从 IE 模式退出 IE 模式， (**省略号图标...) >退出 Internet Explorer 模式**，否则，Microsoft Edge会自动退出 IE 模式，例如，使用地址栏、后退按钮 (“页面内”导航时， 或收藏的链接) 。

条目保留在本地站点列表中，默认期限为 30 天。 建议在Enterprise模式站点列表中为组织配置旧网站。 本地站点列表将确保用户可以在更新组织的网站列表时继续工作流，而不会中断。 第 31 天，当用户导航到网站时，他们将看到一条横幅，说明站点将不再在 IE 模式下加载。 如果用户选择，则可以将其添加回本地站点列表。

:::image type="content" source="media/Edge-hybrid-IE-mode/page-will-no-longer-load-in-ie-mode-screenshot.png" alt-text="页面将不再在 IE 模式下加载":::

## <a name="policies-to-configure-the-use-of-local-site-lists-for-ie-mode"></a>为 IE 模式配置本地站点列表的使用策略

可使用两个组策略在Microsoft Edge中配置本地站点列表体验。 这些策略是：

### <a name="policy-internetexplorerintegrationreloadiniemodeallowed"></a>策略：InternetExplorerIntegrationReloadInIEModeAllowed

此策略对应于Microsoft Edge设置“允许在 Internet Explorer 模式下重新加载站点”。 可通过 *edge://settings/defaultbrowser* URL 来访问此设置。

- 如果启用此策略，则用户可以通过选择**设置和更多 (省略号图标来在 IE 模式下重新加载站点...>在 Internet Explorer 模式下重新加载**。 用户也可以在右键单击 **选项卡时选择 Internet Explorer 模式下的“重新加载”选项卡** ，或在右键单击链接时选择 **“在新的 Internet Explorer 模式下打开链接”选项卡** 。
用户可以选择性地告知Microsoft Edge将来对网站使用 IE 模式。 此选项将默认记住 30 天，并且可以使用策略 *InternetExplorerIntegrationLocalSiteListExpirationDays* 进行管理。

- 如果禁用此策略，则不允许用户在 IE 模式下重新加载未配置的站点。

- 如果未配置此策略，我们将显示用户选项以 IE 模式重新加载未配置的站点，具体取决于最近的 Internet Explorer 11 使用情况。

请注意，此策略优先于配置 [InternetExplorerIntegrationTestingAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationtestingallowed) 策略以及该策略的配置方式。

### <a name="policy-internetexplorerintegrationlocalsitelistexpirationdays"></a>策略：InternetExplorerIntegrationLocalSiteListExpirationDays

此策略可用于调整网站在用户的本地站点列表中保留的天数。  

- 如果禁用或未配置此策略，则使用默认值 30 天。

- 如果启用策略，则必须输入 0-90 天之间的值才能将网站保留在用户的本地站点列表中。

如果禁用 *InternetExplorerIntegrationReloadInIEModeAllowed* 策略，则此策略无效。

> [!NOTE]
> 本地站点列表当前不会跨设备同步。 此改进目前位于我们的积压工作中，我们将在可用时更新此功能。

## <a name="see-also"></a>另请参阅

- 禁用 Internet Explorer 11 - [禁用 Internet Explorer 11](/deployedge/edge-ie-disable-ie11)
- 配置 IE 模式策略 - [配置 IE 模式策略](/deployedge/edge-ie-mode-policies)
