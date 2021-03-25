---
title: 将 Microsoft Edge 设置为 Windows 和 macOS 上的默认浏览器
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 1/15/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解如何将 Microsoft Edge 设为默认浏览器
ms.openlocfilehash: 9151294c34cb2252a7fb32e660c1e3d9e64b5f76
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447756"
---
# <a name="set-microsoft-edge-as-the-default-browser"></a>将 Microsoft Edge 设为默认浏览器

本文介绍了如何将 Microsoft Edge 设置为 Windows 和 macOS 上的默认浏览器。

> [!NOTE]
> 本文适用于 Windows 8 和 Windows 10 上的 Microsoft Edge 版本 77 或更高版本。 对于 Windows 7 和 macOS，请查看[将 Microsoft Edge 设为默认浏览器](./microsoft-edge-policies.md#defaultbrowsersettingenabled)策略。

## <a name="introduction"></a>简介

你可以使用**设置默认关联配置文件**组策略或 [DefaultAssociationsConfiguration](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) 移动设备管理设置将 Microsoft Edge 设为组织的默认浏览器。

要将 Microsoft Edge Stable 版设置为 html 文件、http/https 链接和 PDF 文件的默认浏览器，请使用以下应用程序关联文件示例：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<DefaultAssociations> 
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".html"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".htm"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="http"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="https"/>  
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgePDF" Identifier=".pdf"/>
</DefaultAssociations>
```

> [!NOTE]
> 要将 Microsoft Edge Beta 设置为默认浏览器，请将 **ApplicationName** 设置为“Microsoft Edge Beta”，并将 **ProgId** 设置为“MSEdgeBHTML”。 要将 Microsoft Edge Dev 设置为默认浏览器，请将 **ApplicationName** 设置为“Microsoft Edge Dev”，并将 **ProgId** 设置为“MSEdgeDHTML”。


> [!NOTE]
> 如果 Microsoft Edge 未安装在目标设备上，则不会应用默认文件关联。 在此场景下，当用户打开某个链接或 htm/html 文件时，系统会提示他们选择其默认应用程序。

## <a name="set-microsoft-edge-as-the-default-browser-on-domain-joined-devices"></a>将 Microsoft Edge 设为加入域的设备上的默认浏览器

你可以通过配置**设置默认关联配置文件**组策略，将 Microsoft Edge 设置为加入域的设备上的默认浏览器。 开启此组策略要求你创建和存储默认的关联配置文件。 此文件存储在本地或网络共享上。 有关创建此文件的详细信息，请参阅[导出或导入默认应用程序关联](/windows-hardware/manufacture/desktop/export-or-import-default-application-associations)。

### <a name="to-configure-the-group-policy-for-a-default-file-type-and-protocol-associations-configuration-file"></a>若要为默认文件类型和协议关联配置文件配置组策略，请执行以下操作：

1. 打开组策略编辑器，然后转到**计算机配置\管理模板\Windows 组件\文件资源管理器**。
2. 选择**设置默认关联配置文件**。
3. 单击**策略设置**，然后单击**已启用**。
4. 在**选项:** 下，键入默认关联配置文件的位置。
5. 单击**确定**保存策略设置。

下一张屏幕截图中的示例显示了可从目标设备访问的网络共享上名为 *appassoc.xml* 的关联文件。

   ![在组策略中启用文件关联](./media/edge-learnmore-make-edge-default-browser/edge-learnmore-app-associations.png)

   > [!NOTE]
   > 如果启用了此设置，并且用户的设备已加入域，则在用户下次登录时会处理关联配置文件。

## <a name="set-microsoft-edge-as-the-default-browser-on-azure-active-directory-joined-devices"></a>将 Microsoft Edge 设置为加入 Azure Active Directory 的设备上的默认浏览器

要将 Microsoft Edge 设置为加入 Azure Active Directory 的设备上的默认浏览器，请使用以下应用程序关联文件为例执行 [DefaultAssociationsConfiguration](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) 移动设备管理设置中的步骤。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<DefaultAssociations>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".html"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".htm"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="http"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="https"/>  
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgePDF" Identifier=".pdf"/>
</DefaultAssociations>
```

> [!NOTE]
> 要将 Microsoft Edge Beta 设置为默认浏览器，请将 **ApplicationName** 设置为“Microsoft Edge Beta”，并将 **ProgId** 设置为“MSEdgeBHTML”。 要将 Microsoft Edge Dev 设置为默认浏览器，请将 **ApplicationName** 设置为“Microsoft Edge Dev”，并将 **ProgId** 设置为“MSEdgeDHTML”。

## <a name="set-microsoft-edge-as-the-default-browser-on-macos"></a>将 Microsoft Edge 设置为 macOS 上的默认浏览器

尝试以编程方式在 macOS 上设置默认浏览器，会导致系统向最终用户显示一条提示。 此提示是一项 macOS 安全功能，仅能通过 AppleScript 自动关闭。

由于此限制，将 Microsoft Edge 设置为 macOS 上的默认浏览器主要有两种方法。 第一个选项是使用 macOS 的映像来刷写设备，其中 Microsoft Edge 已设置为默认浏览器。 另一个选项是使用 [将 Microsoft Edge 设置为默认浏览器](./microsoft-edge-policies.md#defaultbrowsersettingenabled) 策略，这将提示用户将 Microsoft Edge 设置为默认浏览器。

使用上述任一方法时，用户仍有可能更改默认浏览器。 这是因为出于安全原因，不能以编程方式阻止默认浏览器首选项。 出于此原因，我们建议你部署**将 Microsoft Edge 设置为默认浏览器** 策略，即使你创建的映像以 Microsoft Edge 为默认浏览器。 如果设置了此策略，并且用户在下次打开 Microsoft Edge 时更改了默认浏览器 Microsoft Edge，系统会提示他们将其设置为默认浏览器。

## <a name="see-also"></a>另请参阅

- [规划 Microsoft Edge 部署](./deploy-edge-plan-deployment.md)
- [Microsoft Edge Enterprise 着陆页](https://aka.ms/EdgeEnterprise)
- [将 Microsoft Edge 设置为默认浏览器（Windows 7 和 macOS）](./microsoft-edge-policies.md#defaultbrowsersettingenabled)
- [Windows 10 - 如何为 IT 专业人员配置文件关联？](/archive/blogs/windowsinternals/windows-10-how-to-configure-file-associations-for-it-pros)
- [导出或导入默认应用程序关联](/windows-hardware/manufacture/desktop/export-or-import-default-application-associations)
  - [DISM 概述](/windows-hardware/manufacture/desktop/what-is-dism)
  - [DISM - 部署映像服务和管理](/windows-hardware/manufacture/desktop/dism---deployment-image-servicing-and-management-technical-reference-for-windows)