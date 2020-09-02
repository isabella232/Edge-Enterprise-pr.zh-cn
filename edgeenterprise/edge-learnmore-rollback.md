---
title: Microsoft Edge 企业版回退
ms.author: v-danwes
author: dan-wesley
manager: srugh
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 如何将 Microsoft Edge 回退到以前的版本
ms.openlocfilehash: 9af0881a079dd3059e567eaadb912b3d929924c4
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979287"
---
# 如何将 Microsoft Edge 回退到以前的版本

本文介绍如何使用“回退”功能回退到以前版本的 Microsoft Edge。

>[!NOTE]
>本文适用于 Microsoft Edge 版本 86 或更高版本。

## 回退简介

回退可让你将 Microsoft Edge 浏览器版本替换为更早期版本。 此功能旨在为企业部署 Microsoft Edge 提供安全网络。 它提供了一种解决 Microsoft Edge 问题的方法。 回退的优点是能够轻松快速地还原到先前的浏览器版本。 回退会降低 Microsoft Edge 问题对企业运营的潜在影响。

## 开始之前

请务必了解如何在 Microsoft Edge 环境中安装“回退”功能。 可使用两种不同方法部署回退：使用 MSI 手动部署或使用 Microsoft Edge 更新和组策略。 我们还鼓励使用多种组策略更顺利地部署回退。

### 建议

回退功能旨在临时修复 Microsoft Edge 浏览器更新中可能发现的问题。 我们建议用户安装最新版本的 Microsoft Edge 浏览器，以使用最新安全更新提供的保护。 回退到较早版本存在遇到已知安全问题的风险。

在暂时回退浏览器版本之前，强烈建议你为组织中的所有用户启用同步。 如果未启用同步，则会存在永久丢失浏览数据的风险。 有关详细信息，请参阅 [Microsoft Edge 同步](microsoft-edge-enterprise-sync.md)。

> [!CAUTION]
> 请仅在必要时使用回退，因为始终存在数据丢失风险。

## 启用通过 MSI 手动回退

请按照以下步骤手动使用 MSI 回退。

1. 禁用 Microsoft Edge 更新。

   > [!NOTE]
   > 建议安装最新的管理模板。 有关详细信息，请参阅[下载并安装 Microsoft Edge 管理模板](https://docs.microsoft.com/DeployEdge/configure-microsoft-edge#1-download-and-install-the-microsoft-edge-administrative-template)。

   - 打开本地组策略编辑器，然后转到“*计算机配置”>“管理模板”>“Microsoft Edge 更新”>“应用程序”>“Microsoft edge”>*。
   - 选择“**更新策略替代**”，然后选择“**已启用**”。
   - 在“**选项**”下，从“策略”下拉列表中选择“**已禁用更新**”。

2. 获取 MSI。

   - 从[这里](https://www.microsoft.com/edge/business/download)下载您想要回退到的版本的 MSI。
   - 将 MSI 保存到桌面。

3. 运行回退命令。

   - 使用“**以管理员身份运行**”打开 Windows 命令提示。
   - 键入以下命令，其中：*C:\Users\username\Desktop\test*  是已下载的 MSI 所在路径，FileName 是 .msi 文件的名称：<br>
 `C:\Users\username\Desktop\test>msiexec /I FileName.msi /qn ALLOWDOWNGRADE=1`<br>
     > [!NOTE]
     > 有关 msiexec 的详细信息，请参阅 [msiexec](https://docs.microsoft.com/windows-server/administration/windows-commands/msiexec)。
   - 关闭并重新打开 Microsoft Edge，验证回退是否成功。 在“**设置”和“更多**” (ALT + F) 下，转到 “**设置**”并选择“**关于 Microsoft Edge**”。

## 使用 Microsoft Edge 更新和组策略启用回退

按照以下步骤可使用 Microsoft Edge 更新和组策略启用回退。

1. 打开本地组策略编辑器，然后转到“*计算机配置”>“管理模板”>“Microsoft Edge 更新”>“应用程序”>“Microsoft edge”>*。
2. 选择“**回退到目标版本**”，然后选择 “**已启用**”。
3. 选择“**目标版本替代**”，并选择要回退到的浏览器版本。
4. 选择“**更新策略替代**”，然后选择“**已启用**”。 在“**选项**”下，从“策略”下拉列表中选择以下选项之一（“**已禁用更新**”除外）：

   - 始终允许更新
   - 仅自动静默更新
   - 仅手动更新  

5. 将在下次 Microsoft Edge 更新检查更新时执行回退。

   > [!NOTE]
   > 如果你希望立即回退，则必须更改 Microsoft Edge 更新轮询间隔，或使用 MSI 启用回退。

### 常见回退错误

以下错误将阻止回退：

- 输入为不受支持的目标版本
- 输入为不存在的目标版本
- 输入未正确格式化。

### 推荐的组策略

强烈推荐使用回退功能时采用以下组策略和设置。

#### 同步组策略

- ForceSync. 将 ForceSync 设置为“启用”。 此策略将强制启用所有 Azure Active Directory (Azure AD) 用户的同步。 此策略仅适用于 Microsoft Edge 版本 86 及更高版本。
- *配置从同步策略中排除的类型列表*允许管理员控制用户可同步哪些数据。

#### 浏览器重新启动组策略

建议启用回退后，对用户强制重启。

- 启用*通知用户对于挂起的更新，推荐或需要重新启动浏览器*。 在“选项”下，选择“**必需**”。
- 启用*设置更新通知时间段，然后设置所需时间（以毫秒为单位）*。

## 常见问题

### 手动 MSI 回退

#### 可能发生哪些常见 MSI 故障？

1. 如果禁用“安装更新”组策略，则不会发生回退。

   - 若要使用回退，请确保将“安装”设置为“**启用**”。 如果禁用此策略，将阻止安装 Microsoft Edge 频道。 有关详细信息，请参阅[安装](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#install)。

2. 如果启发更新不存在，将阻止 Microsoft Edge 安装，除非已启用*允许 Microsoft Edge 并排浏览体验*。

   - 针对 Windows 版本 1903 和 1909：如果上次更新早于 2019 年 10 月，则可能会存在此问题。
   - 针对 Windows 版本 1709、1803 和 1809：如果上次更新早于 2019 年 11 月，则可能会存在此问题。<br>
有关详细信息，请参阅[用于支持下一版 Microsoft Edge 的 Windows 更新](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-windows-updates)。

#### 使用命令提示但回退没发生后，显示以下错误消息。 究竟是哪里出现错误？

![回退状态消息](./media/edge-learnmore-rollback/edge-rollback-cmd-flag-error.png)

*ALLOWDOWNGRADE = 1* 未执行。

### Microsoft Edge 更新和组策略回退

#### 我设置了*回退到目标版本*、启用了*更新策略替代*，且输入了*目标版本替代*希望回退到的浏览器版本，但浏览器版本不是我要回退到的版本。 究竟是哪里出现错误？

以下常见错误会阻止回退：

- 如果未设置回退到目标版本，将不会执行回退。
- 目标版本替代设置存在以下问题之一：

  - 目标版本替代被设置为不受支持的目标版本。
  - 目标版本替代被设置为不存在的目标版本。
  - 目标版本替代输入的格式不正确。

- 如果将”更新策略替代“设置为“禁用更新”，则 Microsoft Edge 更新不会接受任何更新。 这将导致不执行回退。

### 我正确设置了所有组策略，但回退未执行。 发生了什么情况？

Microsoft Edge 更新尚未运行更新检查。 默认情况下，自动更新将每 10 小时检查一次更新。 可通过更改 Microsoft Edge 更新的轮询间隔来修复此错误，自动更新检查周期将覆盖组策略。 有关详细信息，请参阅 [AutoUpdateCheckPeriodMinutes](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies#autoupdatecheckperiodminutes) 策略。

### 作为 IT 管理员，我按照正确回退的所有步骤进行了操作。 “我的用户组”的一部分已回退。 为什么尚未回退其他用户？

组策略设置尚未同步到所有客户端。 当管理员设置组策略时，客户端不会立即收到这些设置。

<!--
You can update all users' group policy with the  

When admins set all users don't get this setting instantaneously 

GP Update force group policy – link to this 

-->





## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
