---
title: 使用 Jamf 在 macOS 上配置 Microsoft Edge
ms.author: brianalt
author: dan-wesley
manager: laurawi
ms.date: 11/30/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 使用 Jamf 在 Mac 设备上配置 Microsoft Edge 策略设置
ms.openlocfilehash: 1859d9fb1fd3ea8ff6908c41f75df21a8b338769
ms.sourcegitcommit: ed6a5afabf909df87bec48671c4c47bcdfaeb7bc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "11194710"
---
# 使用 Jamf 在 macOS 上配置 Microsoft Edge 策略设置

本文介绍如何使用 Jamf Pro 10.19 上的 Microsoft Edge 策略清单文件在 macOS 上配置策略设置。

还可以使用属性列表 (.plist) 文件在 macOS 上配置 Microsoft Edge 策略设置。 有关详细信息，请参阅[使用 .plist 针对 macOS 进行配置](configure-microsoft-edge-on-mac.md)


## 必备条件

需要以下软件：

- Microsoft Edge Stable 渠道 81
- 策略模板文件（版本 81.0.416.3）
- Jamf Pro（版本 10.19）

## 关于 Jamf Pro 的“应用程序和自定义设置”菜单

在 Jamf Pro 10.18 之前，管理 Office 365 涉及手动生成 .plist 文件。 这是一个耗时的工作流程，需要强大的技术背景。 Jamf Pro 10.18 通过简化配置过程消除了这些障碍。 但是，IT 管理员只能将此新用户界面用于由 Jamf 指定的特定应用程序和首选项域。

在 Jamf Pro 10.19 中，用户可上传 JSON 清单作为“自定义架构”以用于任何首选项域，并将从此清单生成图形用户界面。 创建的自定义架构遵循 JSON 架构规范。

有关详细信息，请参阅《Jamf Pro 管理员指南》中的[计算机配置文件](https://jamf.it/computer-configuration-profiles)。

## 获取特定 Microsoft Edge 版本的策略清单

若要获取策略清单，请执行以下操作：

- 转到 [Microsoft Edge Enterprise 登陆页面](https://aka.ms/EdgeEnterprise)。
- 在 "通道/版本" 下拉列表中，选择 **版本81或更高版本的任何通道。**_.
- 在 "生成" 下拉列表中，选择 "任何_ *81 生成" 或 "更高* * _版本"。
- 单击“获取策略文件”下载我们的策略模板捆绑包。

  > [!NOTE]
  > 目前，策略模板捆绑包签名为 CAB 文件。 需要在 macOS 上使用第三方工具（如 The Unarchiver）打开此文件。

解压缩 CAB 文件后，解压缩 ZIP 文件，然后导航到“mac”顶级目录。 名为“policy_manifest.json”的清单位于此目录中。

从内部版本 81.0.416.3 开始，在每个策略捆绑包中都会发布此清单。 如果你想要在开发渠道中测试策略，可以获取与每个开发版本相关联的清单，并在 Jamf Pro 中对其进行测试。  

## 在 Jamf Pro 中使用策略清单

请按照以下步骤将策略清单上传到 Jamf Pro，然后为 macOS 创建策略配置文件。

1. 登录 Jamf。
2. 选择 "_*计算机**" 选项卡。
3. 在“**内容管理**”下，选择“**配置文件**”。
4. 在“**配置文件**”页面上，单击“**+ 新建**”。

   ![在 Jamf 中添加新的配置文件](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles.png)

5. 在“**新建 macOS 配置文件**”>“**选项**”中，选择“**应用程序和自定义设置**”。
6. 在“**应用程序和自定义设置**”弹出窗口中，单击“**配置**”。

   ![配置应用程序和自定义设置](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom.png)

7. 在“**应用程序和自定义设置**”部分，设置以下屏幕截图中显示的值。

   ![配置文件源和自定义架构](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-schema.png)

   - 对于“**创建方法**”，选择“**配置设置**”。
   - 对于“**源**”，选择“**自定义架构**”。
   - 对于“**首选项域**”，提供你的域的名称。 此示例使用 *com.microsoft.Edge* 作为域。
   - 对于“**自定义架构**”，粘贴“policy_manifest.json”清单文件的内容。
   - 单击 **“保存”**。

8. 保存配置文件后，Jamf 将显示下一个屏幕截图中所示的“**常规**”部分。

   ![配置“常规”部分](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-general-setting.png)

   - 提供配置文件的显示“**名称**”和“**说明**”。
   - 保留“**类别**”的默认设置，即“**无**”。
   - 对于“**分发方法**”，选项为“**自动安装**”或“**使其在自助服务中可用**”。
   - 对于“**级别**”，选项为“**用户级别**”或“**计算机级别**”。
   - 单击 **“保存”**。

9. 保存“常规”部分后，Jamf 将显示为我们的示例设置的“Microsoft Edge Beta 渠道”配置文件。 在下一个屏幕截图中，请注意，可以单击“**编辑**”以继续处理配置文件；如果已完成，请单击“**完成**”。

   ![包含选项的新配置文件](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel.png)

   > [!NOTE]
   > 在保存此配置文件后，还可在其他 Jamf 会话中对其进行编辑。 例如，你可能决定将“分发方法”更改为“使其在自助服务中可用”。

   若要在 Microsoft Edge Stable 渠道中执行配置文件的后续编辑或将其删除，请选择配置文件名称，如以下“配置文件”屏幕截图中所示。

   ![“配置文件”列表](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel-done.png)

创建新的配置文件后，仍需为配置文件配置“**范围**”。

### 配置范围

1. 对于“**目标**”，提供以下最低设置：

   - 面向计算机。 选项为“特定计算机”或“所有计算机”。
   - 面向用户。 选项为“特定用户”或“所有用户”。
   - 单击 **“保存”**。
2. 对于“**限制**”，保留默认设置：“无”。 单击“取消”****。
3. 对于“**排除**”，保留默认设置：“无”。 单击“取消”****。

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [使用 Intune 针对 macOS 进行配置](configure-microsoft-edge-on-mac.md)
- [针对 Windows进行配置](configure-microsoft-edge.md)
- [使用 Intune 针对 Windows进行配置](configure-edge-with-intune.md)
