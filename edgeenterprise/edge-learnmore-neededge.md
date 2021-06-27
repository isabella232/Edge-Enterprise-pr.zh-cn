---
title: 从 Internet Explorer 重定向到 Microsoft Edge，以便与现代网站兼容
ms.author: laannade
author: dan-wesley
manager: ratetali
ms.date: 11/16/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 从 Internet Explorer 重定向到 Microsoft Edge，以便与现代网站兼容
ms.openlocfilehash: 7cd74eda6d8ada7647862ea69f77a982713f0c14
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617292"
---
# <a name="redirection-from-internet-explorer-to-microsoft-edge-for-compatibility-with-modern-web-sites"></a>从 Internet Explorer 重定向到 Microsoft Edge，以便与现代网站兼容

> [!NOTE]
> 本文适用于 Microsoft Edge 稳定版本 87 或更高版本。

## <a name="overview"></a>概述

>[!Note]
> Internet Explorer 11 桌面应用程序将于 2022 年 6 月 15 日停用并停止支持（若要查看包含内容的列表， [请参阅常见问题解答](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)）。 现在使用的 IE11 应用和网站可以在 Microsoft Edge 的 Internet Explorer 模式下打开。 [在此处了解详细信息](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。

许多新式网站的设计与 Internet Explorer 不兼容。 只要 Internet Explorer 用户访问不兼容的公共网站，就会收到一条消息，告知他们该网站与其浏览器不兼容，需要手动切换到其他浏览器。

需要手动切换到另一种浏览器的操作，从 Microsoft Edge 稳定版本 87 开始更改。

当用户转到与 Internet Explorer 不兼容的网站时，它们将被自动重定向到 Microsoft Edge。 本文介绍重定向的用户体验，以及用于配置或禁用自动重定向的组策略。

> [!NOTE]
> Microsoft 将保留已知与 Internet Explorer 不兼容的所有网站的列表。 有关详细信息，请参阅 [请求更新不兼容站点列表](/microsoft-edge/web-platform/ie-to-microsoft-edge-redirection#request-an-update-to-the-ie-compatibility-list)

## <a name="prerequisites"></a>必备条件
- Microsoft Edge Stable 版本 87 或更高版本
- Windows 版本
    - Windows 10 版本 1709 或更高版本
    - Windows 8.1
    - Windows 7



## <a name="redirection-experience"></a>重定向体验

重定向到 Microsoft Edge 后，将在下一屏幕截图中显示一次性对话框。 此对话框将说明它们被重定向的原因，并提示你同意将浏览数据和首选项从 Internet Explorer 复制到 Microsoft Edge。 将导入以下浏览数据： 收藏夹、密码、搜索引擎、打开选项卡、历史记录、设置、cookie 和主页。

![浏览通知并提示导入数据和首选项。](media/edge-learnmore-neededge/neededge-dialog1.png)

即使他们没有通过选中“总是导入 Internet Explorer 中的浏览数据和首选项”提供许可，他们也可以单击 **“继续浏览”** 来继续执行会话。

最后，下一个屏幕截图中显示的网站不兼容标题会显示在每次重定向地址栏的下方。

![有关新式网站的通知，以及将 Microsoft Edge 设置为默认浏览器或浏览 Microsoft Edge 的提示。](media/edge-learnmore-neededge/neededge-banner.png)

网站兼容性标题：

- 鼓励用户切换到 Microsoft Edge
- 将 Microsoft Edge 作为默认浏览器
- 为用户提供浏览 Microsoft Edge 的选项

从 Internet Explorer 将网站重定向到 Microsoft Edge 时，如果没有以前的内容，则会关闭启动加载网站的 Internet Explorer 选项卡。 否则，活动选项卡视图将转到 Microsoft [支持](https://support.microsoft.com/office/the-website-you-were-trying-to-reach-doesn-t-work-with-internet-explorer-8f5fc675-cd47-414c-9535-12821ddfc554?ui=en-US&rs=en-US&ad=US) 页面，说明网站重定向到 Microsoft Edge 的原因。

> [!NOTE]
> 重定向之后，用户可以使用 Internet Explorer 获取不在 Internet Explorer 兼容性列表中的网站。  

## <a name="policies-to-configure-redirection-to-microsoft-edge"></a>用于配置重定向到 Microsoft Edge 的策略

> [!NOTE]
> 这些策略将在 2020 年 10 月 26 日发布的 ADMX 文件更新中提供，并且将于 2020 年 11 月 9 日在 Intune 中提供。

必须将三个组策略配置为启用自动重定向到 Microsoft Edge。 这些策略是：

- RedirectSitesFromInternetExplorerPreventBHOInstall
- RedirectSitesFromInternetExplorerRedirectMode
- HideInternetExplorerRedirectUXForIncompatibleSitesEnabled

### <a name="policy-redirectsitesfrominternetexplorerpreventbhoinstall"></a>策略：RedirectSitesFromInternetExplorerPreventBHOInstall

从 Internet Explorer 重定向到 Microsoft Edge 需要一个名为 IEtoEdge BHO 的 Internet Explorer 浏览器帮助程序对象 (BHO)。 **RedirectSitesFromInternetExplorerPreventBHOInstall** 策略控制是否已安装此 BHO。  

- 如果启用此策略，重定向所需的 BHO 将不会安装，并且你的用户将继续看到 Internet Explorer 上某些网站的不兼容消息。 如果已安装 BHO，则在下一次更新 Microsoft Edge 稳定频道时，会将其卸载。
- 如果禁用或未配置此策略，将安装 BHO。 这是默认行为。

除了需要 BHO 外，还需要依赖 **RedirectSitesFromInternetExplorerRedirectMode**，其需要设置为“基于不兼容网站的网站列表重定向网站”或“未配置”。

### <a name="policy-redirectsitesfrominternetexplorerredirectmode"></a>策略：RedirectSitesFromInternetExplorerRedirectMode

 此策略对应于 Microsoft Edge **默认浏览器**设置“允许 Internet Explorer 在 Microsoft Edge 中打开网站”。 可通过 *edge://settings/defaultbrowser* URL 来访问此设置。  

- 如果未配置此策略或将其设置为“站点列表”，则 Internet Explorer 会将不兼容的网站重定向到 Microsoft Edge。 这是默认行为。
- 若要禁用此策略，请选择“**已启用**”，然后在“选项：将不兼容的网站从 Internet Explorer 重新定向到 Microsoft Edge”下的下拉列表中，选择“**禁用**”。 在此状态下，不兼容的网站不会重定向到 Microsoft Edge。

> [!NOTE]
> 如果你所在的个人设备并非由组织管理，你将在 **Internet Explorer 兼容性**下看到名为“允许在 Internet Explorer 模式中加载的网站”的另一个设置。
>
>如果你使用加入域或移动设备管理 (MDM) 注册设备，则不会看到此选项。
>
> 如果想让用户在 Internet Explorer 模式下加载网站，可通过将策略配置[允许 Internet Explorer 模式测试](./microsoft-edge-policies.md#intranetredirectbehavior)来实现此操作。

### <a name="policy-hideinternetexplorerredirectuxforincompatiblesitesenabled"></a>策略：HideInternetExplorerRedirectUXForIncompatibleSitesEnabled

此策略可将不兼容网站重定向的用户体验配置到 Microsoft Edge。  

- 如果启用此策略，用户则不会看到一次性重定向对话框和重定向标题。 不导入浏览器数据或用户偏好设置。
- 如果禁用或未配置此策略，重定向对话框将显示在第一次重定向中，且对于以重定向开头的会话将显示永久重定向标题。

  > [!NOTE]
  > 每次用户遇到新的重定向时，将导入用户浏览数据。 但是，只有用户同意一次性重定向对话框上的导入时才会发生这种情况。

## <a name="disable-redirection-to-microsoft-edge"></a>禁用重定向到 Microsoft Edge

如果想要在更新到 Microsoft Edge 稳定版本 87 之前禁用重定向，请执行以下步骤：

1. 将 **RedirectSitesFromInternetExplorerPreventBHOInstall** 策略设为 **“启用”**。

如果想要在更新到 Microsoft Edge 稳定版本 87 之后禁用重定向，请执行以下步骤：

1. 将 **RedirectSitesFromInternetExplorerRedirectMode** 策略设置为“**已启用**”，然后在“选项：将不兼容的网站从 Internet Explorer 重新定向到 Microsoft Edge”下的下拉列表中，选择“**禁用**”。 策略生效后，此设置将立即停止重定向。
2. 将 **RedirectSitesFromInternetExplorerPreventBHOInstall** 策略设为 **“启用”**。 策略生效后，将在下一次 Microsoft Edge 更新后卸载 BHO。

## <a name="see-also"></a>另请参阅

- [请求更新不兼容站点列表](/microsoft-edge/web-platform/ie-to-microsoft-edge-redirection#request-an-update-to-the-ie-compatibility-list)
- [Microsoft Edge 企业版登录页面](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 策略](./microsoft-edge-policies.md)