---
title: Microsoft Edge 安全概述
ms.author: srugh
author: srugh
manager: seanlyn
ms.date: 04/29/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 安全部署概述
ms.openlocfilehash: f22f2dcbace00cd535d201950c2af488c708525b
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979386"
---
# Microsoft Edge 安全概述
  
企业中的 IT 管理员在保护公司网络和设备免受恶意攻击并防止未经授权的访问和公司数据泄漏的同时，不断面临着众多现有和新出现的安全挑战。 Microsoft Edge 提供了几种固有的内置独特功能，可帮助解决这些难题。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## 条件访问

就管理云资源而言，身份和访问权限是云安全的一个重要方面。 在移动优先、云优先的世界中，用户可以从任何地方使用各种设备和应用来访问组织的资源。 因此，仅关注谁可以访问资源是不够的。 你还需要考虑访问资源的方式。 Azure Active Directory (Azure AD) 条件访问可帮助你掌握安全性和工作效率之间的平衡。

### 在 Microsoft Edge 中访问受条件访问保护的资源

Microsoft Edge 本身支持 Azure AD 条件访问。 无需安装单独的扩展。 如果你使用企业 Azure AD凭据登录 Microsoft Edge 配置文件，Microsoft Edge 允许无缝访问受条件访问保护的企业云资源。

在符合标准的设备上，访问资源的标识应与配置文件上的标识匹配。  如果不匹配，你将看到类似于下一张屏幕截图中的消息。 在屏幕截图示例中，“testadmin@evostsoneboxtest.com”是访问资源所需的登录帐户。

![浏览器中的条件访问消息](./media/edge-security/microsoft-edge-security-conditional-access.png)

若要继续，你必须切换到所需配置文件（如果有）或者创建具有匹配标识的配置文件。

若要登录并使用你的配置文件，请单击浏览器右上角的用户头像。 可以使用下拉菜单执行以下操作：

- 选择其他配置文件。 单击配置文件名称。
- 创建配置文件。 单击**添加配置文件**。
- 管理你的配置文件。 单击**管理配置文件设置**。

所有平台（包括所有受支持的 Windows 和 macOS 版本）上均提供此支持。

### 如何在 Azure Active Directory 中部署条件访问

[部署条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)提供了有助于在 Azure Active Directory 中部署条件访问的详细指南。

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [视频: 安全性、兼容性和可管理性](/microsoft-edge-video-security-compatibility-manageability.md)
