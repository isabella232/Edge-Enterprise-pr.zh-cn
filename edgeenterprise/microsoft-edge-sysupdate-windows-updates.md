---
title: Microsoft Edge 的 Windows 更新
ms.author: jtkim
author: dan-wesley
manager: srugh
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 的 Windows 更新。
ms.openlocfilehash: 953becc459fe729f84d54da419481b3c6e26cc47
ms.sourcegitcommit: 16a92a51560fdba6f6480e4533453348f026c7ef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "11313902"
---
# 用于支持下一版本 Microsoft Edge 的 Windows 更新

本文介绍了如何更新 Windows 以支持下一版本的 Microsoft Edge。

> [!IMPORTANT]
> 有关 Microsoft Edge 旧版服务终止的信息，请参阅 Microsoft Edge 产品团队[博客文章](https://aka.ms/EdgeLegacyEOS)。

> [!NOTE]
> 本文适用于 Microsoft Edge 稳定渠道。

## Microsoft Edge 和 Windows 版本周期

下一版本的 Microsoft Edge 具有更频繁且更灵活的更新功能。 由于浏览器版本未绑定到 Windows 主要版本，因此会对操作系统进行更改，以确保下一版本的 Microsoft Edge 可以无缝融入到 Windows 中。 因此，功能更新约每 6 周发布一次。 安全和兼容性更新按需提供。

## 更新和用户体验

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
  > 用户级别安装不会触发这些行为。

除了以前的更改之外，还存在无论是否安装了下一版本 Microsoft Edge 的稳定渠道都将发生的更改。

- Microsoft Edge 将为下一个版本的 Microsoft Edge 不支持的书籍和 XML 协议取消注册。 尝试打开这些协议的用户将获得一个对话框，此对话框将提示他们选择默认应用。 请在[下载 ePub 应用以继续阅读电子书](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fsupport.microsoft.com%2Fhelp%2F4517840&data=02%7C01%7Cv-danwes%40microsoft.com%7Cc9f8571b880549c30fcf08d72be5eaf9%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637026138803983526&sdata=qtb3DvVZQ6H%2FFXnBievkl%2B%2BngAQXwl340PcH8kRc3y4%3D&reserved=0)中了解有关图书支持更改的更多信息。

## 时间线

支持所述体验所需的更改将随 Windows 不同版本的三个更新一起提供。

### Windows 版本 1903 和 1909

- 可选的 2019 年 7 月更新中的第一组更改，与 2019 年 8 月安全更新一起提供。
- 可选的 2019 年 8 月更新中的第二组更改，与 2019 年 9 月安全更新一起提供。

  > [!NOTE]
  > 在此更新中，Microsoft Edge 将取消注册 XML 协议。

- 可选的 2019 年 9 月更新中的第三组更改，与 2019 年 10 月安全更新一起提供。

  > [!NOTE]
  > 在此更新中，Microsoft Edge 将不再支持电子书。

### Windows 版本 1709、1803 和 1809

- 可选的 2019 年 8 月更新中的第一组更改，与 2019 年 9 月安全更新一起提供。
- 可选的 2019 年 9 月更新中的第二组更改，与 2019 年 10 月安全更新一起提供。

  > [!NOTE]
  > 在此更新中，Microsoft Edge 将取消注册 XML 协议。

- 可选的 2019 年 10 月更新中的第三组更改，与 2019 年 11 月安全更新一起提供。

  > [!NOTE]
  > 在此更新中，Microsoft Edge 将不再支持电子书。

下表提供了每组更改中的特定更新的详细信息。

| Windows10 | 详细信息 | 需要下载的内容 |
|--|--|--|
| 版本 1709 | [KB4525241](https://support.microsoft.com/help/4525241/windows-10-update-kb4525241) | [Windows 10 版本 1709 的累积更新](https://www.catalog.update.microsoft.com/Search.aspx?q=4525241) |
| 版本 1803  | [KB4525237](https://support.microsoft.com/help/4525237/windows-10-update-kb4525237) | [Windows 10 版本 1803 的累积更新](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4525237) |
| 版本 1809  | [KB4523205](https://support.microsoft.com/help/4523205/windows-10-update-kb4523205) | [Windows 10 版本 1809 的累积更新](https://www.catalog.update.microsoft.com/Search.aspx?q=4523205) |
| 版本 1903 和 1909 |[KB4517389](https://support.microsoft.com/help/4517389/windows-10-update-kb4517389)  | [Windows 10 版本 1903 和 1909 的累积更新](https://www.catalog.update.microsoft.com/Search.aspx?q=4517389) |

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 文档](https://docs.microsoft.com/DeployEdge/)
