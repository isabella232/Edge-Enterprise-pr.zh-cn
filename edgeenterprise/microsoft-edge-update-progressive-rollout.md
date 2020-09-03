---
title: Microsoft Edge Stable 渠道更新的渐进式部署
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 05/21/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Stable 渠道更新的渐进式部署
ms.openlocfilehash: 5b0d2f58318b10538d0470b644d346b5b9b9489b
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979320"
---
# Microsoft Edge Stable 渠道更新的渐进式部署

从 Microsoft Edge 83 版开始，我们将在几天内将主要更新渐进式部署到 Microsoft Edge Stable 渠道中。 此渐进式部署使我们能够监视升级并在整个组织中安全地更新浏览器。

> [!NOTE]
> 适用于 Microsoft Edge Stable 渠道版本 83 或更高版本。

## 为什么需要渐进式部署？

通过在几天内严密监视更新的运行状况并部署更新，可限制新的更新可能发生的问题带来的影响。 使用 Microsoft Edge 发布版本 83，将为所有 Windows 7、Windows 8 & 8.1 和 Windows 10 版 Microsoft Edge 启用渐进式部署。 我们将尽快在 Mac 上支持 Microsoft Edge。

## 更新将如何工作？

更新将为每个 Microsoft Edge 安装分配一个升级值。 当我们开始以增量方式部署时，如果设备上的值落在升级值范围内，你就看到更新。 几天内随着部署的推进，所有用户最终都将获得更新。 拥有关键安全修补程序浏览器更新部署速度会更快。 这样做是为了确保及时防范漏洞。

## 这对企业有何影响？

Microsoft Edge 产品通过多种机制（如 Microsoft Intune、Windows Server Update Service (WSUS) 和 Configuration Manager ）分发给企业。 这些部署工具在渐进式部署方面有不同的行为：

- 通过 Microsoft Intune 管理分发的企业会注册为自动更新。 采用渐进式部署，所有用户将在几天内看到更新。
- 通过 WSUS (Windows Server Update Services) 或 Configuration Manager 管理分发的企业不会注册为自动更新。 从一开始，管理员就可以管理并应用更新。 渐进式部署不会影响此过程。

如果你有任何疑问或问题，请通过 User Voice、“应用程序反馈”按钮，或在以下评论中提供宝贵意见。

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
