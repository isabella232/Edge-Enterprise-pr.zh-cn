---
title: Microsoft Edge 中的 PDF 阅读器
ms.author: adigan
author: dan-wesley
manager: balajek
ms.date: 08/05/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解 Microsoft Edge 中的 PDF 阅读器。
ms.openlocfilehash: c189bc08d4af0c9d5c4d9c573e0b5b7ef32a7fb3
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979373"
---
# Microsoft Edge 中的 PDF 阅读器

我们在日常生活中会大量接触到 PDF 文件。 它们以合同与协议、新闻稿、表单、研究文章、简历等形式出现，不一而足。 企业十分需要一款可靠、安全和强大的 PDF 阅读器来处理这些文件。

Microsoft Edge 内置的 PDF 阅读器可用于打开本地 PDF 文件、联机 PDF 文件或在网页中嵌入的 PDF 文件。 可使用墨迹和突出显示功能对这些文件添加批注。 这款 PDF 阅读器应用可同时满足用户对网页和 PDF 文档的需求。 Microsoft Edge PDF 阅读器是一款安全可靠的应用程序，可跨 Windows 和 macOS 桌面平台工作。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## 前提条件、支持和约束

下表显示了各个频道和版本的 Microsoft Edge 支持的 PDF 阅读器功能。

| 功能 | 稳定频道版本 |
|---------|------------------------|
| 查看和打印本地、联机和嵌入的 PDF 文件 | 79.0.309.71                |
| 基本的表单填写<br>（不支持 JavaScript 表单） | 79.0.309.71           |
| 墨迹书写  | 80.0.361.48            |
| 墨迹自定义 | 83.0.478.54  |
| Highlight  | 81.0.416.53         |
| 大声朗读 | 目前正在 [Microsoft Edge 预览体验计划](https://www.microsoftedgeinsider.com/)频道内升级 |
| 查看 MIP 受保护的文件 | 80.0.361.48 中的 Window 支持<br>81.0.416.53 中的 Mac 支持 |
|  查看 IRM 受保护的文件  | 83.0.478.37            |

### 约束

请注意，当前 PDF 阅读器存在以下限制：

-  XML 表单体系结构 (XFA) 是一种旧表单格式，在 Microsoft Edge 中不受支持。
-  有关当前不受支持的辅助功能场景的文档，可在 [Microsoft 辅助功能一致性报告](https://cloudblogs.microsoft.com/industry-blog/government/2018/09/11/accessibility-conformance-reports/)博客中找到。

## 功能

### 墨迹书写

PDF 文件的墨迹书写非常方便，可快速记录参考、签名或填写 PDF 表单。 现在，Microsoft Edge 中支持此功能。 除了可根据需要向 PDF 文件添加墨迹书写外，还可以使用颜色和笔划宽度使他人留意 PDF 文件的不同部分。 下一张屏幕截图将显示用户如何向 PDF 页面添加墨迹书写。

<!-- SCREENSHOT -->
![向 PDF 页面添加墨迹书写](media/microsoft-edge-pdf/pdf-reader-inking.png)

### Highlight

Microsoft Edge 中的 PDF 阅读器支持添加和编辑突出显示。 若要创建突出显示，用户只需选择文本，右键单击它，选择菜单中的“突出显示”，然后选择希望使用的颜色。 下一张屏幕截图将显示可用的突出显示选项。

![使用 PDF 阅读器中的“突出显示”选项](media/microsoft-edge-pdf/pdf-reader-highlight.png)

### 大声朗读

通过 PDF 的“大声朗读”功能，用户可在执行其他对他们而言可能很重要的任务的同时，轻松收听 PDF 内容。 此外，它还可帮助视障学习者专注于内容，让学习变得更加轻松。 下一张屏幕截图将显示一个“大声朗读”的示例。 “突出显示”将显示当前正在阅读的文本。

![使用 PDF 阅读器中的“突出显示”选项](media/microsoft-edge-pdf/pdf-reader-read-aloud-example.png)

### 受保护的 PDF 文件

[Microsoft 信息保护 (MIP)](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide) 使用户能够安全地与他人协作，同时遵守组织的合规政策。 文件受到保护后，用户可以对其执行的操作取决于被分配的权限。

无需下载任何其他软件或安装任何加载项，便可直接在浏览器中打开这些文件。 这样一来，便将 MIP 提供的安全性直接集成到浏览器中，为用户提供无缝的工作流。

<!-- SCREENSHOT -->
![受保护的 PDF 文档。](media/microsoft-edge-pdf/pdf-reader-protected-pdf2.png)

除 MIP 受保护文件之外，还可在本地浏览器中打开[信息权限管理 (IRM)](https://docs.microsoft.com/microsoft-365/compliance/set-up-irm-in-sp-admin-center?view=o365-worldwide) 受保护的 SharePoint 库中的 PDF 文件。

用户可在 Microsoft Edge 中查看保存在本地或云中的 MIP 受保护文件。 如果保存在本地，则可直接在浏览器中打开文件。 如果文件是从 SharePoint 等云服务中打开的，则用户可能需要使用“在浏览器中打开”选项。

如果用户登录到 Microsoft Edge 的配置文件至少具有对文件的“查看”权限，则文件将在“Microsoft Edge”中打开。

<!-- SCREENSHOT -->
![提示保存 MIP 保护的 SharePoint PDF 页面](media/microsoft-edge-pdf/pdf-reader-sharepoint-irm.png)

## 辅助功能

PDF 阅读器支持键盘辅助功能、高对比度模式以及跨 Windows 和 macOS 设备的屏幕阅读器。

### 键盘辅助功能

用户可使用键盘导航到文档中可交互的不同部分，如表单字段和突出显示。

<!-- SCREENSHOT -->

### 高对比度模式

PDF 阅读器将使用在操作系统级别定义的设置，在高对比度模式下呈现 PDF 内容。

<!-- SCREENSHOT -->
<!--![High contrast mode for pdf file](media/microsoft-edge-pdf/pdf-reader-high-contrast.png)-->

### 屏幕阅读器支持

用户可以使用 Windows 和 Mac 计算机上的屏幕阅读器浏览和阅读 PDF 文件。 <!--The next screenshot shows the toolbar that users can use for audio settings when they're using the Read Aloud option in PDF reader. -->

<!-- SCREENSHOT -->
<!--
![Screen reader toolbar](media/microsoft-edge-pdf/pdf-reader-read-aloud.png) -->

## 安全与可靠

安全是任何组织最重要的原则之一。 PDF 阅读器安全性是 Microsoft Edge 安全设计的一个有机组成部分。 PDF 阅读器中最重要的两大安全功能是，进程隔离和 Microsoft Defender 应用程序防护（以下简称“应用程序防护”）。

- 进程隔离。 从不同网站打开的 PDF，其进程完成彼此隔离。 浏览器无需同任何网站或从其他来源打开的 PDF 文件进行通信。 因此，浏览 PDF 不会遭受任何计划使用遭入侵的 PDF 作为攻击面的攻击。

- 应用程序防护。 借助应用程序防护，管理员可以设置组织信任的网站列表。 如果用户打开任何其他网站，将在单独的应用程序防护窗口中打开，该窗口在自己的容器中运行。 该容器可帮助保护公司网络和用户计算机上的任何数据免遭入侵。<br><br>
此保护同样适用于已查看的任何联机 PDF 文件。 此外，将存储任何从应用程序防护下载的 PDF 文件，并在需要时在容器中重新打开。 这将帮助你的环境不只在下载文件时，而是在 PDF 文件的整个生命周期中保持安全。 有关详细信息，请参阅[应用程序防护](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-defender-application-guard)。

### 可靠性

由于 Microsoft Edge 是一款 Chromium 内核浏览器，因此能够为用户提供与 Google Chrome 浏览器相同级别的可靠性。

## 部署和更新 PDF 阅读器

PDF 阅读器会随 Microsoft Edge 浏览器的其余部分进行部署和更新。 若要了解有关部署 Microsoft Edge 的详细信息，请观看[将 Microsoft Edge 部署到成百上千的设备](microsoft-edge-video-deploy.md)视频。 此外，还可访问 [Microsoft Edge 文档](https://docs.microsoft.com/DeployEdge/)登陆页面，获得更多部署信息。

> [!TIP]
> 你可以将 Microsoft Edge 设置为组织的默认 PDF 阅读器。 为此，[请执行下列步骤](https://docs.microsoft.com/deployedge/edge-default-browser)。

## 路线图和反馈

Microsoft Edge 中的 PDF 阅读器路线图可在[此处](https://techcommunity.microsoft.com/t5/articles/roadmap-for-pdf-reader-in-microsoft-edge/m-p/1467667)查看。

我们正积极研究你认为重要的功能反馈。 可随时通过 [Microsoft Edge UserVoice](https://microsoftedge.uservoice.com/) 以及前往 [Microsoft Edge 预览体验计划](https://techcommunity.microsoft.com/t5/microsoft-edge-insider/ct-p/MicrosoftEdgeInsider)论坛与我们分享你的反馈意见。

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)