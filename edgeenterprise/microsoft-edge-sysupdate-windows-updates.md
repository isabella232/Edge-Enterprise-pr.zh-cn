---
title: 用于支持 Microsoft Edge 的 Windows 更新
ms.author: jtkim
author: dan-wesley
manager: srugh
ms.date: 11/17/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 用于支持 Microsoft Edge 的 Windows 更新。
ms.openlocfilehash: 85f60b3ee09154c702debcfb222567996be9462f
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2022
ms.locfileid: "12298160"
---
# <a name="windows-updates-to-support-the-next-version-of-microsoft-edge"></a>用于支持下一版本 Microsoft Edge 的 Windows 更新

本文介绍了如何更新 Windows 以支持下一版本的 Microsoft Edge

> [!IMPORTANT]
> 有关 Microsoft Edge 旧版服务终止的信息，请参阅 Microsoft Edge 产品团队[博客文章](https://aka.ms/EdgeLegacyEOS)。

> [!NOTE]
> 本文适用于 Microsoft Edge 稳定渠道。

## <a name="microsoft-edge-and-the-windows-release-cycle"></a>Microsoft Edge 和 Windows 版本周期

下一版本的 Microsoft Edge 具有更频繁且更灵活的更新功能。 由于浏览器版本未绑定到 Windows 主要版本，因此会对操作系统进行更改，以确保下一版本的 Microsoft Edge 可以无缝融入到 Windows 中。 因此，功能更新约每 4 周发布一次。 安全和兼容性更新按需提供。

## <a name="updates-and-the-user-experience"></a>更新和用户体验

更新将不会更改用户体验，直到安装下一版本 Microsoft Edge 的稳定渠道为止。 安装 Microsoft Edge Beta、Dev 或 Canary 不会触发 Windows 中的任何更改。 这些浏览器版本将随现有浏览器一起安装。

在系统级别应用所有更新并且安装下一版本 Microsoft Edge 的稳定渠道时，以下更改将在系统上生效：

- 当前版本的 Microsoft Edge 的所有“开始”菜单 Pin、磁贴和快捷方式都将迁移到下一版本的 Microsoft Edge。
- 当前版本的 Microsoft Edge 的所有任务栏 Pin 和快捷方式都将迁移到下一版本的 Microsoft Edge。
- 下一版本的 Microsoft Edge 将固定到任务栏上。 如果已固定当前版本的 Microsoft Edge，将替换它。
- 下一版本的 Microsoft Edge 将向桌面添加快捷方式。 如果当前版本的 Microsoft Edge 已有快捷方式，则旧快捷方式将被替换。
- Microsoft Edge 默认处理的大多数协议都将迁移到下一版本的 Microsoft Edge。
- 当前的 Microsoft Edge 将在操作系统内的所有 UX 界面中隐藏，包括设置、所有应用程序以及任何文件或协议支持对话框。
- 所有尝试启动当前版本的 Microsoft Edge 的操作都将重定向到下一版本的 Microsoft Edge。

  > [!NOTE]
  > 用户级别安装不会触发前面的行为。

除了以前的更改之外，还存在无论是否安装了下一版本 Microsoft Edge 的稳定渠道都将发生的更改。

- Microsoft Edge 将为下一个版本的 Microsoft Edge 不支持的书籍和 XML 协议取消注册。 尝试打开这些协议的用户将获得一个对话框，此对话框将提示他们选择默认应用。 请访问 Microsoft Store，查看我们为电子书阅读器提供的建议。
  
## <a name="older-versions-of-windows"></a>其他版本的 Windows

若要在运行早于 Windows 10 RS4 的 Windows 版本的设备上部署 Microsoft Edge，请使用 [配置服务器](https://docs.microsoft.com/mem/configmgr/apps/deploy-use/deploy-edge?bc=https%3A%2F%2Fdocs.microsoft.com%2FDeployEdge%2Fbreadcrumb%2Ftoc.json&toc=https%3A%2F%2Fdocs.microsoft.com%2FDeployEdge%2Ftoc.json)、[Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-windows-edge?bc=https%3A%2F%2Fdocs.microsoft.com%2FDeployEdge%2Fbreadcrumb%2Ftoc.json&toc=https%3A%2F%2Fdocs.microsoft.com%2FDeployEdge%2Ftoc.json) 或升级到受支持的 Windows 10 版本。 以下文章列出了当前支持的 Windows 10 和 Windows 11 版本。

- [受支持的 Windows 客户端版本](/windows/release-health/supported-versions-windows-client)

> [!NOTE]
> 对于 Windows 10 RS4-20H1，请从 2021 年 5 月或更高版本来部署 Windows LCU 以获取 Microsoft Edge。 有关详细信息，请参阅 [Windows 10 更新历史记录](https://support.microsoft.com/topic/windows-10-update-history-1b6aac92-bf01-42b5-b158-f80c6d93eb11)

> [!IMPORTANT]
> 如果需要此处未列出的更新，请运行 Windows 更新或与管理员联系。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 文档](./index.yml)