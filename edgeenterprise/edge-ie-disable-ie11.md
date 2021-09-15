---
title: 禁用 Internet Explorer 11
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 07/09/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 了解如何在 Microsoft Edge Internet Explorer 11 和使用Internet Explorer模式。
ms.openlocfilehash: b70da0ff7437d1f5e70cec40e31211046a66205a
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "11978940"
---
# <a name="disable-internet-explorer-11"></a>禁用 Internet Explorer 11

>[!Note]
> Internet Explorer 11 桌面应用程序将于 2022 年 6 月 15 日停用并停止支持（若要查看包含内容的列表，[请参阅常见问题解答](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)）。 现在使用的 IE11 应用和网站可以在 Microsoft Edge 的 Internet Explorer 模式下打开。 [在此处了解详细信息](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。

本文介绍如何在环境中禁用 Internet Explorer 11 作为独立浏览器。

## <a name="prerequisites"></a>必备条件

需要以下 Windows 更新和 Microsoft Edge 软件：

- Windows 更新

  - Windows 10，版本 21H1 或更高版本
  - Windows 10，版本 2004;Windows服务器版本 2004;Windows 10，版本 20H2;Windows服务器版本[20H2：KB4598291](https://support.microsoft.com/topic/february-2-2021-kb4598291-os-builds-19041-789-and-19042-789-preview-6a766199-a4f1-616e-1f5c-58bdc3ca5e3b)或更高版本
  - Windows 10版本[1909：KB4598298](https://support.microsoft.com/topic/january-21-2021-kb4598298-os-build-18363-1350-preview-02dfd9ba-91a2-1b82-dede-42f288c02511)或更高版本
  - WindowsServer 2019;Windows 10 企业版 2019 [LTSC：KB4598296](https://support.microsoft.com/topic/january-21-2021-kb4598296-os-build-17763-1728-preview-4c0931ff-45b7-ff59-5e00-c03b5afb363d)或更高版本
  - Windows Server 2016;[Windows 10 企业版 2016 长期服务版：KB4601318](https://support.microsoft.com/topic/february-9-2021-kb4601318-os-build-14393-4225-c5e3de6c-e3e6-ffb5-6197-48b9ce16446e)或更高版本
  - [Windows 10 企业版 2015 长期服务：KB4601331](https://support.microsoft.com/office/february-9-2021%e2%80%94kb4601331-os-build-10240-18842-6227d078-fef3-8d67-27e0-1882e6cb79ff?ui=en-US&rs=en-US&ad=US)或更高版本
  - Windows 8.1;Windows Server 2012[R2：KB4601384](https://support.microsoft.com/topic/february-9-2021-kb4601384-monthly-rollup-16bdbb75-dd4b-2910-abc5-7891c9756b96)或更高版本
  - [Windows Server 2012：KB4601348](https://support.microsoft.com/topic/february-9-2021-kb4601348-monthly-rollup-2c338c0c-73d6-fb80-cc91-f1a86e80db0c)或更高版本
  
- Microsoft Edge 稳定渠道


## <a name="overview"></a>概述

对于需要 Internet Explorer 11 (IE11) 实现旧版兼容性的组织，Microsoft Edge 上的 Internet Explorer 模式 (IE 模式) 可提供无缝的单浏览器体验。 用户可以从 Microsoft Edge 内访问旧版应用程序，而无需切换回 IE11。

配置 IE 模式后，可以使用组策略禁用 **IE11** 作为独立浏览器，而不会影响整个组织的 IE 模式功能。

> [!NOTE]
> 如果需要用于特定站点的独立 IE11 应用，并且希望将所有其他浏览器流量重定向到 Microsoft Edge，可以将站点列表中未包含的所有站点都配置为 [Microsoft Edge](./edge-ie-mode-policies.md#redirect-sites-from-ie-to-microsoft-edge) 策略，以将站点从 IE 重定向到 Microsoft Edge。

## <a name="user-experience-after-redirecting-traffic-to-microsoft-edge"></a>将流量重定向到 Microsoft Edge 后的用户体验

当您启用禁用 **Internet Explorer 11 作为** 独立浏览器策略时，所有 IE11 活动将重定向到 Microsoft Edge，并且用户具有以下体验：

- 将删除"开始"菜单上的 IE11 图标，但任务栏上的图标将保留。
- 当用户尝试启动使用 IE11 的快捷方式或文件关联时，他们将被重定向以在 Microsoft Edge 中打开相同的文件/URL。
- 当用户尝试通过直接调用 IE11 iexplore.exe，Microsoft Edge 将改为启动。

作为为此体验设置策略的一部分，可以选择为尝试启动 IE11 的每个用户显示重定向消息。 可以将此消息设置为显示"始终"或"每个用户一次"。 默认情况下，不会显示下一张屏幕截图中显示的重定向消息。

:::image type="content" source="media/edge-ie-disable-ie11/disable-ie-redirect-msg.png" alt-text="尝试在重定向到 Microsoft Edge 处于活动状态后打开 IE 时发出警报。":::

如果你的企业模式站点列表包含配置为在 IE11 应用中打开的应用程序，并且你通过此策略禁用 IE11，它们在 Microsoft Edge 上将在 IE 模式下打开。
> [!NOTE]
> 将站点配置为在 IE11 应用程序中打开并设置禁用 IE11 策略时，用户流存在已知问题。 此问题已在 Microsoft Edge 版本 91.0.840.0 或更高版本中修复。

## <a name="disable-internet-explorer-11-as-a-standalone-browser"></a>禁用 Internet Explorer 11 作为独立浏览器

若要使用组策略禁用 Internet Explorer 11，请按照以下步骤操作：

1. 确保你有必备的操作系统更新。 此步骤将直接更新计算机上的 ADMX 文件（特别是 inetres.adml 和 inetres.admx）。 请注意，如果要更新中央存储，则需要从有必备更新的计算机上复制 .adml 和 .admx 文件。 有关详细信息，请参阅[创建和管理中央存储](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)
2. 打开组策略编辑器。
3. 转到***计算机配置/管理模板/Windows 组件/Internet Explorer。*** 
4. 双击禁用 **Internet Explorer 11 作为独立浏览器**。
5. 选择 **"已启用"。**
6. 在 **"** 选项"下，选取下列值之一：

   - **从不**  如果不想通知用户 IE11 已禁用。
   - **始终**  如果希望每次从 IE11 重定向用户时通知用户。
   - **每个用户一次**  如果希望仅在第一次重定向用户时通知用户。

7. 单击 **"**   确定 **"或"应用**   "保存此策略设置。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [关于 IE 模式](./edge-ie-mode.md)
- [其他企业模式信息](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
