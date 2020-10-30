---
title: 企业新选项卡页面的向后兼容性
ms.author: ruchir
author: dan-wesley
manager: vwehren
ms.date: 10/28/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 企业新选项卡页面的向后兼容性
ms.openlocfilehash: c10671a6ec8e1ff4dcb0db3f3c085f82ae973122
ms.sourcegitcommit: af6ab070d0c09bca4a9cf505b107ed7e04839763
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "11144469"
---
# 企业新选项卡页面的向后兼容性

本文介绍了新选项卡页面所做的更改，以及用户向后兼容 Microsoft Edge 87 版本及更低版本的情况。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 87 或更高版本。

## 来自单个终端的信息源

新版本的企业新选项卡页面结合了合规的 Microsoft 365 内容以及通过 MSN.com 终端点提供的符合行业的和合规的信息源。

> [!NOTE]
> Office 365 的内容最初是使用 [Office.com](https://www.office.com) 域提供服务的。

如果你的组织对 MSN.com 域的访问收到了限制，我们强烈建议授予用户访问此 [url](https://ntp.msn.com)的权限。

如果需要更多时间来启用对 MSN 域的访问，我们建议使用 [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)，以便为新的选项卡页面选择 Microsoft 新闻或 Office 365 源体验。

### 继续使用 Office.com

 可配置 **NewTabPageSetFeedType** 策略，以继续使用已弃用的 Office.com 域。

> [!IMPORTANT]
> 当Microsoft Edge 90 版本发布时，**NewTabPageSetFeedType** 策略和服务于 Office 365 内容的 Office.com 域将退出工作。

以下策略设置将强制企业新建选项卡页面渲染来自 Office.com 域的 Office 文档内容。

- 将策略设置为 **强制**。
- 设置策略映射的值为 **Office（1）= Office 365 源体验**。

如果无法切换到 Office.com，请转向联系我们并给我们发送反馈。 另一种选择是配置 [NewTabPageLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagelocation) ，使其指向组织所允许的端点 URL。

> [!NOTE]
> 如果同时还配置了 **NewTabPageSetFeedType** 策略，则 **NewTabPageLocation** 策略具有优先权。

## 现在，企业用户将通过我的源来获取 Microsoft 新闻内容

企业新选项卡页面将在 **我的源** 和 Office 365 内容中为使用Azure Active Directory （Azure AD）帐户登录的用户提供单一视图中的行业相关信息。 对于使用其 Azure Active Directory （Azure AD）登录并在设置浮出控件中选择了 Microsoft 资讯选项的用户，其新的选项卡页面视图将替换为 **我的源** 内容。 当用户在浏览器中打开一个新的选项卡页面时，其外观将与下一屏幕截图中的示例一样。。

![新选项卡页面显示我的源的内容。](media/microsoft-edge-ntp-backward-compatibility/microsoft-edge-ntp-myfeed-view.png)

> [!NOTE]
> 未使用 Azure AD 登录的用户将在打开新选项卡时继续看到 MSN 新闻源。

## 页面布局

随着新选项卡页面的变化，页面布局不再需要控制两种特定的内容类型（Office 365和Microsoft 资讯），因此内容切换无法使用。 下一张屏幕截图将显示页面布局的浮出控件。

![新选项卡页面的页面布局视图。](media/microsoft-edge-ntp-backward-compatibility/microsoft-edge-ntp-page-layout.png)

如果想要继续访问未绑定到组织的 Microsoft 资讯内容，则必须使用其他浏览器配置文件。 转到  *edge://settings/profiles* 并注销你的 Azure AD 配置文件。 此操作将调出企业新选项卡页面的标准视图。 

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [适用于 Internet Explorer 11 的企业模式](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
