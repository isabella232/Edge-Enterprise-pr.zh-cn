---
title: 预配 Microsoft Edge 收藏夹
ms.author: capoon
author: dan-wesley
manager: abutcher
ms.date: 09/29/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 预配 Microsoft Edge 收藏夹
ms.openlocfilehash: 94bd42573bdbc0fd1b971ded1c82e5fe152acc54
ms.sourcegitcommit: 854dd73eb168960c0eb4b483f81a8efe88806a64
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "11088684"
---
# 预配 Microsoft Edge 收藏夹

根据客户反馈，我们改进了预配收藏夹。 从 Microsoft Edge 版本 85 开始，管理员无需再手动创建文件来设置收藏夹。 管理员可使用 Microsoft Edge 用户界面添加收藏夹和文件夹，以便生成可导出到组策略的文件。

本文介绍如何为你的组织设置一组收藏夹和文件夹。 可使用[“配置收藏夹”](https://docs.microsoft.com//DeployEdge/microsoft-edge-policies#configure-favorites)策略来设置收藏夹和文件夹。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 85 或更高版本。

## 先决条件和建议

- Microsoft Edge 版本 85 为组策略安装了适当的管理模板。
- 建议在 Microsoft Edge 中使用新的配置文件来设置这些收藏夹。 将在导出中包含与该配置文件一起保存的所有收藏夹。  

## 预配收藏夹和文件夹

使用以下步骤为用户预配收藏夹和文件夹。

1. 转到 Microsoft Edge 地址栏并键入以下 URL： *edge://flags/#edge-favorites-admin-export*。
2. 在 **“为管理员导出收藏夹配置”** 下，从下拉列表中选择 **“启用”** ，然后单击 **“重新启动”**。

3. 转到**收藏** 页面 *edge://favorites*，添加你想要预配的收藏夹和文件夹。

<!--
4. On the **Favorites bar**, click **Add folder**. The folder structure of favorites that are set in the profile you're using will be reflected in the folder you provision for your users. The next screenshot shows "Managed favorites", the folder we'll use to provision favorites.

   ![Add a folder](media/edge-learnmore-provision-favorites/provision-favorites-add-folder.png)

   > [!TIP]
   > Add existing folders that contain favorites you want to provision for your users.

5. Select "Managed favorites" and then click **Add favorite**. The next screenshot shows the favorite we've added.

   ![Add a favorite](media/edge-learnmore-provision-favorites/provision-favorites-add-favorite.png)-->

4. 添加完收藏夹和文件夹后，可将其导出，以便 **“配置收藏夹”** 策略进行使用。 转到地址栏，导航到 *edge://favorites*，单击省略号 **“...”**，然后选择 **“导出收藏夹配置”**。 下一个屏幕截图将显示设置收藏夹时的选项。

   ![使用收藏夹的菜单选项。](media/edge-learnmore-provision-favorites/provision-favorites-menu-options.png)

5. 在 **“导出收藏夹配置”** 下为用户将看到的文件夹提供一个名称。 键入文件夹名称，然后选择要使用的平台格式。 单击 **“复制到剪贴板”**。 下一个屏幕截图将显示文件夹名称为“托管收藏夹”，并且平台是 Windows。

   ![将收藏夹导出到 Windows 文件夹的对话框。](media/edge-learnmore-provision-favorites/provision-favorites-export.png)

6. 打开组策略编辑器，导航到 *“计算机配置/管理模板/”* 并选择 **“配置收藏夹”**。 启用“配置收藏夹”策略。 在**选项下：**，将导出的内容粘贴到配置收藏夹文本区域，然后单击 **“应用”**。 下一个屏幕截图显示了步骤 5 中的“托管收藏夹”文件夹的示例。

   ![使用 gpedit 启用并配置“配置收藏夹”策略。](media/edge-learnmore-provision-favorites/provision-favorites-gpedit.png)

7. 单击 **“确定”** 或 **“应用”** 保存策略设置。

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)