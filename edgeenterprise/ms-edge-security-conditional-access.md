---
title: Microsoft Edge 和条件访问
ms.author: srugh
author: srugh
manager: seanlyn
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 和条件访问
ms.openlocfilehash: 27d93627f8a86ad821a00d6d78b7db352e9e557a
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642848"
---
# <a name="microsoft-edge-and-conditional-access"></a>Microsoft Edge 和条件访问
  
本文介绍 Microsoft Edge 如何支持条件访问，以及如何访问受条件访问保护的资源。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

就管理云资源而言，身份和访问权限是云安全的一个重要方面。 在移动优先、云优先的世界中，用户可以从任何地方使用各种设备和应用来访问组织的资源。 因此，仅关注谁可以访问资源是不够的。 你还需要考虑访问资源的方式。 Azure Active Directory (Azure AD) 条件访问可帮助你掌握安全性和工作效率之间的平衡。

## <a name="accessing-conditional-access-protected-resources-in-microsoft-edge"></a>在 Microsoft Edge 中访问受条件访问保护的资源

Microsoft Edge 本身支持 Azure AD 条件访问。 无需安装单独的扩展。 如果你使用企业 Azure AD凭据登录 Microsoft Edge 配置文件，Microsoft Edge 允许无缝访问受条件访问保护的企业云资源。

在符合标准的设备上，访问资源的标识应与配置文件上的标识匹配。  如果不匹配，你将看到类似于下一张屏幕截图中的消息。 在屏幕截图示例中，“testadmin@evostsoneboxtest.com”是访问资源所需的登录帐户。

![浏览器中的条件访问消息](./media/edge-security/microsoft-edge-security-conditional-access.png)

若要继续，你必须切换到所需配置文件（如果有）或者创建具有匹配标识的配置文件。

若要登录并使用你的配置文件，请单击浏览器右上角的用户头像。 可以使用下拉菜单执行以下操作：

- 选择其他配置文件。 单击配置文件名称。
- 创建配置文件。 单击**添加配置文件**。
- 管理你的配置文件。 单击**管理配置文件设置**。

所有平台（包括所有受支持的 Windows 和 macOS 版本）上均提供此支持。

### <a name="how-to-deploy-conditional-access-in-azure-active-directory"></a>如何在 Azure Active Directory 中部署条件访问

[部署条件访问](/azure/active-directory/conditional-access/plan-conditional-access)提供了有助于在 Azure Active Directory 中部署条件访问的详细指南。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [视频: 安全性、兼容性和可管理性](/microsoft-edge-video-security-compatibility-manageability.md)