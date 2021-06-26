---
title: Microsoft Edge 中的 ClickOnce 和 DirectInvoke
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 09/10/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解有关 Microsoft Edge 中的 ClickOnce 和 DirectInvoke 的信息。
ms.openlocfilehash: 528c9f39a2aa6a8b30e4ec92b6b0765fc04cb817
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617352"
---
# <a name="understand-the-clickonce-and-directinvoke-features-in-microsoft-edge"></a>了解 Microsoft Edge 中的 ClickOnce 和 DirectInvoke 功能

ClickOnce 和 DirectInvoke 是 IE 和 Microsoft Edge（版本 45 和更早版本）中提供的功能，支持使用文件处理程序从网站下载文件。 尽管它们适用于不同的用途，但这两个功能都允许网站指定在用户的设备上将请求下载的文件传递到文件处理程序。 ClickOnce 请求由 Windows 中的本机文件处理程序进行处理。 DirectInvoke 请求由承载文件的网站指定的注册文件处理程序进行处理。

有关这些功能的详细信息，请参阅：

- [ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment?view=vs-2019)
- [DirectInvoke]( https://technet.microsoft.com/learning/jj215788(v=vs.94).aspx)

> [!NOTE]
> 目前，Chromium 不对 ClickOnce 或 DirectInvoke 提供本机支持。

## <a name="overview-prerequisites-and-process"></a>概述：先决条件和过程

为了使 ClickOnce 和 DirectInvoke 能按照设计正常工作，并且要成功请求文件处理程序，必须在操作系统中将文件处理程序注册为支持 ClickOnce 或 DirectInvoke。 通常，在安装了原始操作系统后，或者在安装的新程序要求能够使用 DirectInvoke 进行更新时，会进行此注册。

当网站收到需要使用 ClickOnce 或 DirectInvoke 的下载请求时，会进行操作：

- 该网站请求浏览器使用指定的文件处理程序。
- 浏览器检查操作系统注册表，以查看是否对请求的文件类型注册了文件处理程序。
- 如果注册了文件处理程序，则浏览器会调用此文件处理程序，并将 URL 作为参数传递给文件处理程序。
- 文件处理程序处理 URL 并下载文件。

  > [!NOTE]
  > 该 URL 用于确定文件的来源，以及访问文件时要使用的任何参数。  例如：终结点、清单或元数据。

## <a name="use-cases"></a>用例

以下用例具有代表性。

你可以使用 ClickOnce 轻松地在设备上部署和更新软件，但用户交互最少。 用户可以通过单击网页中的链接来安装和运行 Windows 应用程序。 如果配置正确，ClickOnce 应用程序可以在不让用户为安装程序设置配置的情况下安装程序。 例如，文件位置、要安装的选项等。

DirectInvoke 用例取决于请求 DirectInvoke 的网站的意图。 例如，Microsoft Word 的协作文件编辑功能。 DirectInvoke 允许你下载已更改的文档部分，而无需单击链接并下载你与同事合作的文档的整个副本。 此策略减少了传输的数据量，并可以减少打开文档所需的时间。  

## <a name="current-support-for-clickonce-and-directinvoke-in-microsoft-edge"></a>Microsoft Edge 中对 ClickOnce 和 DirectInvoke 的最新支持

对 ClickOnce 和 DirectInvoke 的支持：

- ClickOnce 和 DirectInvoke 可直接供所有 Windows 用户即时使用。

  > [!NOTE]
  > 想要禁用 ClickOnce 支持的用户可以转到 *edge://flags/#edge-click-once*，然后从下拉列表中选择“**已禁用**”。 你必须**重启**浏览器。

- Windows 以外的任何平台都不支持 ClickOnce 和 DirectInvoke。

## <a name="clickonce-and-directinvoke-file-handling-security"></a>ClickOnce 和 DirectInvoke 文件处理安全性

ClickOnce 和 DirectInvoke 受 Microsoft Defender SmartScreen 的 URL 信誉扫描服务保护。

如果 Microsoft Defender SmartScreen URL 信誉服务将 ClickOnce 或 DirectInvoke 请求标记为不安全，则启用了 ClickOnce 或 DirectInvoke 的用户将看到两个弹出窗口。

第一个弹出窗口询问用户是否想要打开文件。 无论文件被标记为安全还是不安全，都会显示此弹出窗口。 用户可以**将文件报告为不安全**、**取消**请求或单击**打开**以继续。

   ![提示打开文件 ](./media/edge-learn-more-co-di/edge-clickonce-modal-1.png)

如果用户尝试打开文件，并且文件被标记为不安全，则会显示第二个弹出窗口。  此弹出窗口警告用户文件被标记为不安全，并询问他们是否确定要下载该文件。

第二个弹出窗口仅在以下情况下显示：

- 文件是 ClickOnce 或 DirectInvoke 文件
- 已启用 ClickOnce 或 DirectInvoke
- 文件被标记为不安全

 ![提示打开不安全的文件 ](./media/edge-learn-more-co-di/edge-clickonce-modal-2.png)

> [!NOTE]
> 如果 ClickOnce 或 DirectInvoke 被禁用，则请求的文件将被视为常规下载；如果具有不安全标志，则会将其标记为不安全。 这与其他不安全下载的处理一致。

## <a name="clickonce-and-directinvoke-policies"></a>ClickOnce 和 DirectInvoke 策略

有两个组策略可用于为企业用户启用或禁用 ClickOnce 和 DirectInvoke。 这两个策略是 [ClickOnceEnabled](./microsoft-edge-policies.md#clickonceenabled) 和 [DirectInvokeEnabled](./microsoft-edge-policies.md#directinvokeenabled)。 这两个策略在组策略编辑器中分别标记为“允许用户使用 ClickOnce 协议打开文件”和“允许用户使用 DirectInvoke 协议打开文件”。

## <a name="clickonce-and-directinvoke-behavior"></a>ClickOnce 和 DirectInvoke 行为

以下示例显示了启用或禁用 ClickOnce 和 DirectInvoke 时的文件处理。

### <a name="clickonce-enabled"></a>已启用 ClickOnce

1. 用户打开一个页面链接，以请求 ClickOnce 支持，然后在下一张屏幕截图中收到提示。

   ![提示打开不安全的文件 ](./media/edge-learn-more-co-di/edge-clickonce-enabled-1.png)

2. 用户单击**打开**后，ClickOnce 将尝试启动应用程序。

   ![ClickOnce 尝试启动应用程序](./media/edge-learn-more-co-di/edge-clickonce-enabled-launch-app.png)

3. 用户单击**打开**后，浏览器将显示一个弹出窗口，询问用户是否确实要安装应用程序。

   ![提示打开文件](./media/edge-learn-more-co-di/edge-clickonce-enabled-2.png)

   > [!NOTE]
   > ClickOnce 文件处理程序显示的接口、消息和选项因访问的文件的类型和配置而异。

### <a name="clickonce-disabled"></a>已禁用 ClickOnce

1. 当用户打开页面链接以请求 ClickOnce 支持时，将在下载栏中看到一条消息，此消息类似于下一张屏幕截图中的消息。

   ![文件下载提示](./media/edge-learn-more-co-di/edge-clickonce-disabled-1.png)

### <a name="directinvoke-enabled"></a>已启用 DirectInvoke

1. 用户打开页面链接以请求 DirectInvoke 支持，然后在下一张屏幕截图中收到提示。

   ![提示打开文件 ](./media/edge-learn-more-co-di/edge-directinvoke-open-link-1.png)

2. 当用户单击**打开**时，将打开请求的文件处理程序。 在此示例中，使用 Microsoft Word 打开上一张屏幕截图中显示的文档。

   > [!NOTE]
   > DirectInvoke 文件处理程序显示的接口、消息和选项因访问的文件的类型和配置而异。

### <a name="directinvoke-disabled"></a>已禁用 DirectInvoke

1. 当用户打开页面链接以请求 DirectInvoke 支持时，DirectInvoke 的行为与其在禁用 ClickOnce 时的行为相同。 他们将在下载栏中看到一条消息，此消息类似于下一张屏幕截图中的消息。

   ![提示打开文件](./media/edge-learn-more-co-di/edge-directinvoke-open-link-2.png)

## <a name="see-also"></a>另请参阅

- [ClickOnce 安全和部署](/visualstudio/deployment/clickonce-security-and-deployment)
- [Internet Explorer 中的 DirectInvoke](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/jj215788(v=vs.85))
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)