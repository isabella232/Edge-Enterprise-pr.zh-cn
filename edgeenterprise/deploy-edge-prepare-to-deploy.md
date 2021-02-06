---
title: 你的环境中的 Microsoft Edge
ms.author: ryhecht
author: RyanHechtMSFT
manager: tinad
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 你的环境中的 Microsoft Edge
ms.openlocfilehash: e1418d21ff9e541d83d5b86baf5ff25c50d2299d
ms.sourcegitcommit: 16a92a51560fdba6f6480e4533453348f026c7ef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "11313918"
---
# 你的环境中的 Microsoft Edge

本文介绍了当 Microsoft Edge 旧版达到其服务寿命时如何为部署 Microsoft Edge 做好准备。

根据 Microsoft Edge 产品团队的[博客文章](https://aka.ms/EdgeLegacyEOS)，对 Microsoft Edge 旧版桌面应用程序的支持将在 2021 年 3 月 9 日结束。 当你在 4 月应用星期二更新（或“B”）时，它会将 Microsoft Edge 旧版从运行 Windows 10 RS4 至 20H1 的设备上删除，并将其替换为 Microsoft Edge。

## 如何准备

若要准备通过 4 月的星期二更新将 Microsoft Edge 安装到 Windows 10 RS4 至 20H1 的设备上，建议阅读[规划部署 Microsoft Edge](deploy-edge-plan-deployment.md)。

规划部署之后，请使用以下其中一种方法准备部署 Microsoft Edge。

- **安装组策略以自定义 Microsoft Edge 更新方法**。 有关更多信息，请参阅[在 Windows 上配置 Microsoft Edge 策略设置](configure-microsoft-edge.md)，尤其注意[更新策略参考](microsoft-edge-update-policies.md)材料。 如果在安装 4 月的星期二更新版本之前安装用于管理更新的组策略，则 Microsoft Edge 将立即开始遵守你的策略。 如果没有安装任何组策略，则 Microsoft Edge 将会自动更新自身。

- **在 2021 年 3 月 9 日的服务结束日期之前删除 Microsoft Edge 旧版桌面应用程序，并部署 Microsoft Edge**。 对于 Windows 10 RS4 至 20H1，你可以通过使用 Windows 更新实现此操作。 有关详细信息，请参阅[使用 Windows 10 更新部署 Microsoft Edge](deploy-edge-with-windows-10-updates.md)。

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [规划 Microsoft Edge 部署](deploy-edge-plan-deployment.md)