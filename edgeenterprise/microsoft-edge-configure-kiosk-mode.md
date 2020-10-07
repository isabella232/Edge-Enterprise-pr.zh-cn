---
title: 配置 Microsoft Edge 展台模式
ms.author: aguta
author: aguta
manager: srugh
ms.date: 10/05/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 配置 Microsoft Edge 展台模式
ms.openlocfilehash: 799b3dd4b7fc96f0b8e5cb718bca98fd4f38ec15
ms.sourcegitcommit: 78905f66f4a6590a57c8f2bf808af92106b62996
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2020
ms.locfileid: "11094859"
---
# 配置 Microsoft Edge 展台模式

本文介绍如何配置可以试用的 Microsoft Edge 展台模式选项。 还有一个我们要遵循的功能路线图。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 87 或更高版本。

## 概述

Microsoft Edge 展台模式提供两种浏览器锁定体验，因此组织可以创建、管理并为其客户提供最佳体验。 提供以下锁定体验：  

- 数字/交互式标牌体验以全屏模式显示特定网站。
- 公开浏览体验运行 Microsoft Edge 的受限多选项卡版本。

这两种体验都在运行 Microsoft Edge InPrivate 会话，以保护用户数据。

## 设置 Microsoft Edge 展台模式

现在可以使用 Microsoft Edge Canary 渠道版本 87 测试一组初始展台模式功能。 可以从 [Microsoft Edge Insider Channels](https://www.microsoftedgeinsider.com/download) 页面下载 Microsoft Edge Canary。

### 展台模式功能

提供以下功能：

- InPrivate 导航通过在会话结束时删除浏览器数据和下载来保护用户数据。
- 配置退出时删除下载的策略。
- 在处于非活动状态特定时间段后重置用户会话的选项。
- 初始锁定功能集。 提供以下功能：

  - 鼠标上下文菜单
  - F12 开发人员工具
  - F11 退出全屏（在全屏模式下）
  - 阻止初始 *Edge://* 页面集

> [!NOTE]
> 随着展台模式的发展，将提供更多功能。

## 使用展台模式功能

可使用以下 Windows 10 命令行选项来调用 Microsoft Edge 展台模式功能：

- 展台模式数字/交互式标牌： `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen`
- 展台模式公共浏览： `msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing`

### 其他命令行选项

- `--no-first-run` ：禁用首次 Microsoft Edge 运行体验。
- `--kiosk-idle-timeout-minutes` ：更改从上次用户活动到 Microsoft Edge 展台模式重置用户会话前的时间（以分钟为单位）。 支持以下值：

  - 默认值
    - 全屏 - 已关闭
    - 公共浏览 - 5 分钟
  - 允许的值
    - 0 - 关闭计时器
    - 1-1440 分钟，用于在空闲计时器上重置

## Microsoft Edge 与指派访问

### 单应用展台

Microsoft Edge 目前支持具有以下锁定体验、数字/交互标志和公共浏览的单一应用的相同 Microsoft 旧版展台模式类型的子集。  

具有分配的访问权限的展台模式可用于测试最新的  [Windows 10 Insider Preview 版本](https://insider.windows.com/)（版本 20215 或更高版本）以及  [Microsoft Edge Dev 渠道](https://www.microsoftedgeinsider.com/download)版本 87.0.644.4 或更高版本。

**如何获得 Windows 预览体验成员预览版？**

若要在电脑上安装 Windows 10 Insider Preview 内部版本，请按照 [开始使用 Windows 10 Insider Preview 版本](https://docs.microsoft.com/windows-insider/get-started)中的说明进行操作。

### 多应用展台。

可用 Windows 10 上的[多应用指派访问](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)（相当于旧版 Microsoft Edge 的“普通浏览”展台模式类型）运行 Microsoft Edge。 要为 Microsoft Edge 配置多应用指派访问，请按照关于[如何设置多应用展台](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)的说明进行操作。 （Microsoft Edge Stable 渠道的 AUMID 为 **MSEdge**）。

配置 Microsoft Edge 展台模式：将 Microsoft Edge 用于多应用指派访问时，你可以使用 [Microsoft Edge 浏览器策略](https://review.docs.microsoft.com/en-us/DeployEdge/microsoft-edge-policies)配置浏览体验以满足你的独特要求。

### 使用 Windows 设置进行配置

Windows 设置是设置一个或两个单应用展台设备的最简单方法。 使用以下步骤设置单应用展台计算机。

1. 安装最新的 Windows 10 Insider Preview 版本 20215 或更高版本。 按照[开始使用 Windows 10 Insider Preview 版本](https://docs.microsoft.com/windows-insider/get-started)中的说明进行操作。
2. 安装最新版本的 [Microsoft Edge Dev 渠道](https://www.microsoftedgeinsider.com/download)，即 87.0.644.4 或更高版本。

   > [!IMPORTANT]
   > 由于需要设备级安装，因此只支持非 Canary 渠道。

3. 在展台计算机上，打开“Windows 设置”，然后在搜索字段中键入“展台”。 选择“ **设置展台（分配的访问权限）**”（如下一个屏幕截图所示），以打开用于创建展台的对话框。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="设置具有分配的访问权限的展台":::

4. 在“**设置展台** ”页面上，单击“ **入门**”。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="设置具有分配的访问权限的展台":::

5. 键入名称以创建新的展台帐户，或从填充的下拉列表中选择现有帐户，然后单击“ **下一步**”。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="设置具有分配的访问权限的展台":::

6. 在“**选择展台应用** ”页面上，选择“**Microsoft Edge**”，然后单击“ **下一步**”。

   > [!NOTE]
   > 这仅适用于 Microsoft Edge Dev、Beta 和 Stable 渠道。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="设置具有分配的访问权限的展台":::

7. 选择以下选项之一，了解 Microsoft Edge 在展台模式下运行时的显示方式：

   - 数字/交互式标牌 - 运行 Microsoft Edge 时以全屏模式显示特定网站。
   - 公共浏览器 - 运行 Microsoft Edge 的受限多选项卡版本。

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="设置具有分配的访问权限的展台":::

8. 选择“ **下一步**”。
9. 键入要在展台启动时加载的 URL。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="设置具有分配的访问权限的展台":::

10. 接受“5 分钟”的空闲时间默认值或提供你自己的值。

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="设置具有分配的访问权限的展台":::

11. 单击“ **下一步**”。
12. 关闭“ **设置** ”窗口，保存并应用你的选择。

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="设置具有分配的访问权限的展台":::

13. 从展台设备注销并使用本地展台帐户登录，以验证配置情况。

## 功能限制

随着展台模式此预览版的发布，我们将继续改进产品和添加新功能。

尽管展台模式当前不支持以下功能，但我们正努力开发以下功能：

- 收藏
- Extensions
- Internet Explorer 模式
- Windows Defender 应用程序保护 (WDAG)

## 路线图

### 今年晚些时候 (2020)

我们将添加以下功能：

- “结束会话”按钮
- 只读地址栏  
  - 可通过组策略配置
  - 启用后，将阻止用户编辑地址栏并导航到其他页面。

- 更多锁定功能：

  - 其他加速器将被阻止（例如 CTRL+N）
  - “…”设置菜单将仅启用所需选项（例如“打印”、“帮助”、“反馈”和“大声朗读”）
  - 其他 *edge://* 页面锁定（例如 *edge://settings*）
  - 配置打印选项 UI
  - 仅将文件资源管理器限制为下载文件夹。

### 2021 年初

我们将添加以下支持和功能：

- 正式发布在 Windows 上具有分配的访问权限单应用的 Microsoft Edge 展台模式。
- 用于与 Microsoft Edge 旧版进行奇偶校验的其他功能。
- 与 Intune 集成，以使用展台模式配置文件 UX 配置设备。

## 另请参阅

- [在 Windows 桌面版中配置展台和数字签名](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [部署旧版 Microsoft Edge 展台模式](https://aka.ms/edgekioskmode)
- [规划 Microsoft Edge 部署](deploy-edge-plan-deployment.md)
- [Microsoft Edge Enterprise 着陆页](https://aka.ms/EdgeEnterprise)
