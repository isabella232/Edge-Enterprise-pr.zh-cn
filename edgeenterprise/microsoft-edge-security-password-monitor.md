---
title: 为用户自动启用密码监视器
ms.author: supalsul
author: dan-wesley
manager: tulasim
ms.date: 01/26/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 为用户自动启用密码监视器
ms.openlocfilehash: 2f796f0cd1bbb437f83d04a8bd59586ef7b6a982
ms.sourcegitcommit: 187203e9eaa9c48c59095b7e7d625d3081a6ba19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2021
ms.locfileid: "11304532"
---
# 为用户自动启用密码监视器

本文介绍了如何为选定用户打开 Microsoft Edge 中的密码监视器，并给予管理员控制如何启用监视的步骤。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 88 或更高版本。

## 简介、优势和可用性

密码监视器通过通知 Microsoft Edge 用户在联机泄露中是否找到其任何密码来帮助其保护其联机帐户。 当错误参与者从第三方应用或网站窃取数据时，将发生联机泄露或数据泄露。 若要了解更多信息，请参阅 Microsoft 研究博客上的[密码监视器：保护 Microsoft Edge 中的密码](https://www.microsoft.com/research/blog/password-monitor-safeguarding-passwords-in-microsoft-edge/)一文。

### 优势

鉴于这些联机攻击的频率和范围，每个人必须拥有此类保护。 Microsoft Edge 具有针对已知泄露的密码安全检查用户保存的密码的内置功能，如果找到匹配项，则发出警报。  

### 可用性

从 1 月 21 日起，稳定渠道版本 88 中提供了密码监视器。 新版本的推出将逐步进行，可能需要几周时间。更新后用户可以在“**设置**” > “**个人资料**” > “**密码**”页面中看到以下消息和控件。

:::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-enable-option.png" alt-text="启用密码监视器的选项":::

## 为密码监视器配置组策略

此功能通过 [PasswordMonitorAllowed](https://docs.microsoft.com/deployedge/microsoft-edge-policies#passwordmonitorallowed) 组策略控制。

启用策略后，用户仍然需要同意才能启用该功能。 需要获得同意，因为该功能包含用户的敏感数据和个人数据（密码）。 如果使用组策略禁用此功能，则用户不能覆盖此设置。  

## 为用户启用密码监视器

启用密码监视器策略后，用户可以通过多种方式使用此功能。

- 自动启用。 使用工作帐户（Active Directory 或 Azure Active Directory）登陆并同步密码的用户会自动启用此功能。 用户会看到下一张屏幕截图所示的通知，表示他们已打开该功能。

  :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-enabled-notice.png" alt-text="启用密码监视器的通知":::

-  获得明确同意。 将要求尚未打开密码同步的用户获得打开密码监视器的权限。 发生以下操作时，系统将会提示它们：
   - 用户保存新密码时。
 
     :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-save-pw-prompt.png" alt-text="提示保存密码":::

   - 当用户使用保存的密码登录浏览器时。
  
     :::image type="content" source="media/microsoft-edge-security-password-monitor/monitor-after-signin.png" alt-text="登录后确认提示":::
   
- 直接激活。 用户可以随时转到“**设置**” > “**密码**”来打开或关闭此功能。

## 自动启用密码监视器的用户方案

下表显示了自动启用密码监视器的方案及其在用户设备上执行的方式。

| 方案 | 基本条件 | 影响 |
|--|--|--|
| 1 同步打开 | 同步打开<br>以前启用了功能：否<br>对同意 UI 的响应：无 | 默认情况下启用功能，浏览器启动 2 分钟后会显示通知气泡。<br>- 如果在此之后关闭同步，则禁用该功能。<br>- 在更改同步之前关闭功能，同步将不再影响功能。   |
| 2 打开同步 | 同步打开<br>以前启用了功能：是<br>对同意 UI 的响应：无 | 功能与用户选择相同。  请注意，气泡不会显示，并且同步更改不会影响功能值。|
| 3 同步关闭 | 同步关闭<br>以前启用了功能：否<br>对同意 UI 的响应：无 | 同步将关闭，该功能将保持禁用状态<br>- 此后的任何时间点，如果用户在不更改功能的情况下打开同步：启用该功能，并且在同步打开 2 分钟后显示自动启用通知。 <br> - 如果再次关闭同步，则禁用该功能 <br>- 如果在打开同步之前更改了该功能，同步将不再影响密码监视器。  |  
| 4 同步关闭 | 同步关闭<br>以前启用了功能：是<br>对同意 UI 的响应：无 | 功能与用户选择相同，通知气泡不会显示，且同步更改对功能值没有影响。  |

此外，如果用户使用通过以下任一策略限制的工作帐户登录，将不会为用户自动启用该功能：

- 密码监视器已禁用  
- 密码同步已禁用
- 与 Microsoft 服务器共享数据已禁用

## 常见问题

### 如何为组织禁用密码监视器？

您可以按以下方法为组织禁用密码监视器：
- 使用 PasswordMonitorAllowed 组策略。
- 阻止同步数据并发送到 Microsoft 服务器。

  > [!NOTE]
  > 密码监视器即使已禁用密码同步，也可以正常工作，只要用户明确同意打开该功能或通过“设置”自行打开该功能。

### 如果已自动启用该功能的用户通过“设置”关闭密码监视器，会发生什么情况？

尊重用户设置，为用户禁用该功能。 但是，如果以前从未响应过同意提示，可能会再次显示同意对话框。

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)