---
title: 让页内导航继续保持 Internet Explorer 模式
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 05/01/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 让页内导航继续保持 Internet Explorer 模式
ms.openlocfilehash: 0acca9e05a0d09b02fa61d5ddd7de3f7c6cabb92
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979302"
---
# 让页内导航继续保持 Internet Explorer 模式

可以将此策略用作临时解决方案，以强制来自 Internet Explorer 模式（IE 模式）网站的所有页内导航都继续保持 IE 模式。

页内导航将从当前页上的链接、脚本或窗体启动。 也可以是上次页内导航尝试的服务器端重定向。 相反，用户可以使用浏览器控件通过多种方式启动与当前页面无关的非页内导航。 例如，使用地址栏、返回按钮或收藏夹链接。

>[!NOTE]
>本文适用于 Microsoft Edge 版本 81 或更高版本。

## 必备条件

此策略需要以下 Windows 更新：

- Windows 10 版本 1909 和 1903，Windows Server 版本 1909 和 1903 ([KB4532695](https://support.microsoft.com/help/4532695))
- Windows 10 版本 1809，Windows Server 版本 1809，Windows Server 2019 ([KB4534321](https://support.microsoft.com/help/4534321))
- Windows 10 版本 1803 ([KB4534308](https://support.microsoft.com/help/4534308))
- Windows 10 版本 1709 ([KB4534318](https://support.microsoft.com/help/4534318))


## 关于此策略

此策略让你有时间识别和配置 IE 模式网站使用的所有身份验证服务器。 但是，此策略可能会产生不一致的浏览体验，在这种情况下，某些网站将以 IE 模式呈现，而在其他时间以 Microsoft Edge 模式呈现。 此体验取决于是否是从 IE 模式页面导航到网站的。 任何未显式配置为在特定呈现引擎中打开的网站都将出现此不一致性的情况。

如果启用此策略，建议你在识别所有身份验证服务器并将它们作为中性服务器添加到网站列表中以后将此策略禁用。 此操作可确保新式网站绝不会在 IE 模式下意外呈现。

## 让页内导航继续保持 IE 模式

若要让自动导航或所有页内导航都继续保持 Internet Explorer 模式，请按照以下步骤操作：

1. 打开本地组策略编辑器。
2. 单击**计算机配置** > **管理模板** > **Microsoft Edge**。
3. 在**设置**下，双击**指定从 Internet Explorer 模式页面到未配置的网站的页内导航行为方式**。

   ![页内策略设置](media/edge-learnmore-inpage-nav/learnmore-in-page-nav-settings.png)

4. 选中**已启用** 

   ![启用页内策略](media/edge-learnmore-inpage-nav/learnmore-in-page-nav-enable.png)

5. 从下拉列表中选择以下选项之一：

   - **默认** - 只有配置为以 Internet Explorer 模式打开的网站才会以该模式打开。 任何未配置为以 Internet Explorer 模式打开的网站都将重定向回 Microsoft Edge。
   - **只让自动导航继续保持 Internet Explorer 模式** - 如果想要默认体验，但又让所有转到未配置网站的自动导航（如 302 重定向）都继续保持 Internet Explorer 模式，请使用此选项。
   - **让所有页内导航都继续保持 Internet Explorer 模式*****（最不推荐）***- 所有从 IE 模式下加载的页面转到未配置网站的导航都继续保持 Internet Explorer 模式。

6. 单击**确定**或**应用**以保存策略设置。

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
