---
title: 禁用 Internet Explorer 11
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 03/02/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解如何在 Microsoft Edge Internet Explorer 11 和使用Internet Explorer模式。
ms.openlocfilehash: 08d1fe48bfc4614710f4a341a285048194a64794
ms.sourcegitcommit: 928714329d0b11575494f557498f69a8417a3289
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385324"
---
# <a name="disable-internet-explorer-11"></a>禁用 Internet Explorer 11

本文介绍如何在环境中禁用 Internet Explorer 11 作为独立浏览器。

## <a name="prerequisites"></a>必备条件

需要以下 Windows 更新和 Microsoft Edge 软件：

- Windows 更新

  - Windows 10 版本 2004、Windows Server 版本 2004、Windows 10 版本 [20H2：KB4598291](https://support.microsoft.com/topic/february-2-2021-kb4598291-os-builds-19041-789-and-19042-789-preview-6a766199-a4f1-616e-1f5c-58bdc3ca5e3b) 或更高版本
  - Windows 10 版本 1909，Windows Server 版本 [1909：KB4598298](https://support.microsoft.com/topic/january-21-2021-kb4598298-os-build-18363-1350-preview-02dfd9ba-91a2-1b82-dede-42f288c02511) 或更高版本
  - Windows 10 版本 1809、Windows Server 版本 1809 和 Windows Server [2019：KB4598296](https://support.microsoft.com/topic/january-21-2021-kb4598296-os-build-17763-1728-preview-4c0931ff-45b7-ff59-5e00-c03b5afb363d) 或更高版本
  - Windows 10 版本 1607、Windows Server [2016：KB4601318](https://support.microsoft.com/topic/february-9-2021-kb4601318-os-build-14393-4225-c5e3de6c-e3e6-ffb5-6197-48b9ce16446e) 或更高版本
   - 2015 年 7 月 (Windows 10 [) ：KB4601331](https://support.microsoft.com/office/february-9-2021%e2%80%94kb4601331-os-build-10240-18842-6227d078-fef3-8d67-27e0-1882e6cb79ff?ui=en-US&rs=en-US&ad=US) 或更高版本
  - Windows [8.1：KB4601384](https://support.microsoft.com/topic/february-9-2021-kb4601384-monthly-rollup-16bdbb75-dd4b-2910-abc5-7891c9756b96) 或更高版本
  - [Windows Server 2012：KB4601348](https://support.microsoft.com/topic/february-9-2021-kb4601348-monthly-rollup-2c338c0c-73d6-fb80-cc91-f1a86e80db0c)或更高版本
  
- Microsoft Edge 稳定渠道


## <a name="overview"></a>概述

对于需要 Internet Explorer 11 (IE11) 实现旧版兼容性的组织，Microsoft Edge 上的 Internet Explorer 模式 (IE 模式) 可提供无缝的单浏览器体验。 用户可以从 Microsoft Edge 内访问旧版应用程序，而无需切换回 IE11。

配置 IE 模式后，可以使用组策略禁用 **IE11** 作为独立浏览器，而不会影响整个组织的 IE 模式功能。

> [!NOTE]
> 如果需要用于特定站点的独立 IE11 应用，并且希望将所有其他浏览器流量重定向到 Microsoft Edge，可以将站点列表中未包含的所有站点都配置为 [Microsoft Edge](https://docs.microsoft.com/deployedge/edge-ie-mode-policies#redirect-sites-from-ie-to-microsoft-edge) 策略，以将站点从 IE 重定向到 Microsoft Edge。

## <a name="user-experience-after-redirecting-traffic-to-microsoft-edge"></a>将流量重定向到 Microsoft Edge 后的用户体验

当您启用禁用 **Internet Explorer 11 作为** 独立浏览器策略时，所有 IE11 活动将重定向到 Microsoft Edge，并且用户具有以下体验：

- 将删除"开始"菜单上的 IE11 图标，但任务栏上的图标将保留。
- 当用户尝试启动使用 IE11 的快捷方式或文件关联时，他们将被重定向以在 Microsoft Edge 中打开相同的文件/URL。
- 当用户尝试通过直接调用 IE11 iexplore.exe，Microsoft Edge 将改为启动。

作为为此体验设置策略的一部分，可以选择为尝试启动 IE11 的每个用户显示重定向消息。 可以将此消息设置为显示"始终"或"每个用户一次"。 默认情况下，不会显示下一张屏幕截图中显示的重定向消息。

:::image type="content" source="media/edge-ie-disable-ie11/disable-ie-redirect-msg.png" alt-text="尝试在重定向到 Microsoft Edge 处于活动状态后打开 IE 时发出警报。":::

如果你的企业模式站点列表包含配置为在 IE11 应用中打开的应用程序，并且你通过此策略禁用 IE11，它们在 Microsoft Edge 上将在 IE 模式下打开。
> [!NOTE]
> 将站点配置为在 IE11 中打开并设置禁用 IE11 策略时，用户流存在已知问题。 正在积极调查的问题。

## <a name="disable-internet-explorer-11-as-a-standalone-browser"></a>禁用 Internet Explorer 11 作为独立浏览器

若要使用Internet Explorer禁用 11，请按照以下步骤操作：

1. 下载并安装最新的 [Microsoft Edge 策略模板](https://www.microsoft.com/en-us/business/download)。
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
- [关于 IE 模式](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [其他企业模式信息](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
