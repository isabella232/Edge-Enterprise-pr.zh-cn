---
title: 使用 Microsoft Edge 防止潜在有害应用程序
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 03/04/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 使用 Microsoft Edge 防止潜在有害应用程序
ms.openlocfilehash: 615442acc0e9ed58da37aa0ef8b3747e916a8024
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979205"
---
# 防止潜在的有害应用程序 (PUA)

本文介绍了如何使用 Microsoft Edge 或使用 Windows Defender 防病毒防止潜在有害应用程序 (PUA)。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 80 或更高版本。

## 概述

潜在有害应用程序不被视为病毒或恶意软件，但这些应用程序可能会在终结点上执行，对终结点性能或使用产生不利影响的操作。 例如，*Evasion 软件*会主动尝试规避安全产品的检测。 此类软件会增加网络受到实际恶意软件感染的风险。 PUA 也可以指信誉不佳的应用程序。

有关将软件归类为 PUA 的标准的说明，请参阅[潜在有害应用程序](https://docs.microsoft.com/windows/security/threat-protection/intelligence/criteria#potentially-unwanted-application-pua)。

## 使用 Microsoft Edge 防止 PUA

Microsoft Edge（版本 80.0.361.50 或更高版本）会阻止 PUA 下载和关联的资源 URL。

你可以通过在 Microsoft Edge 中启用“**阻止潜在有害应用程序**”功能来设置保护。

> [!NOTE]
> [Microsoft Edge 团队博客文章](https://blogs.windows.com/msedgedev/2020/02/27/protecting-users-potentially-unwanted-apps/)介绍了此新增功能，并说明了处理被错误标识的应用程序或将其报告为有害应用程序的方法。

### 要启用 PUA 保护：

1. 在浏览器中打开“**设置**”。
2. 选择“**隐私和服务**”。
3. 在“**服务**”部分中，检查是否已启用“**Microsoft Defender SmartScreen**”。 如果没有，请启用 Microsoft Defender SmartScreen。 以下屏幕截图中的示例显示了浏览器由组织管理，并且已启用 Microsoft Defender SmartScreen。

   ![在“设置”中启用 Microsoft Edge PUA](./media/microsoft-edge-potentially-unwanted-apps/security-pua-setup.png)

4. 在“**服务**”部分中，使用前面屏幕截图中所示的切换按钮启用“**阻止潜在有害应用程序**”。

   > [!TIP]
   > 你可以通过在我们的 Windows Defender SmartScreen [演示页面](https://demo.smartscreen.msft.net/)中进行测试来安全地浏览 PUA 保护的 URL 阻止功能。

当 Microsoft Edge 检测到 PUA 时，你将看到一条类似于下一屏幕截图中的消息。

   ![Microsoft Edge PUA 警告消息](./media/microsoft-edge-potentially-unwanted-apps/security-pua-msg.png)

### 要阻止与 PUA 关联的 URL

在 Microsoft Edge 中打开 PUA 保护后，Windows Defender SmartScreen 将保护你不受与 PUA 关联的 URL 的侵害。

管理员可通过多种方法来配置 Microsoft Edge 和 Windows Defender SmartScreen 如何协同工作，以保护用户免受与 PUA 关联的 URL 的影响。 有关详细信息，请参阅：

- [在 Windows 上配置 Microsoft Edge 策略设置](https://docs.microsoft.com/DeployEdge/configure-microsoft-edge)
- [SmartScreen 设置](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreen-settings)
- [SmartScreenPuaEnabled 策略](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)
- [配置 Windows Defender SmartScreen](https://docs.microsoft.com/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen)

管理员还可以自定义 Microsoft Defender 高级威胁防护 (Microsoft Defender ATP) 阻止列表。 他们可以使用 Microsoft Defender ATP 门户来[创建和管理 IP 和 URL 的指示器](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators#create-indicators-for-ips-and-urlsdomains-preview)。

## 使用 Windows Defender 防病毒阻止 PUA

[检测并阻止潜在有害应用程序](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#windows-defender-antivirus)文章还介绍了如何配置 Windows Defender 防病毒来启用 PUA 保护。 可使用下列任一选项来配置保护：

- [Microsoft Intune](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-intune-to-configure-pua-protection)
- [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-configuration-manager-to-configure-pua-protection)
- [组策略](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-group-policy-to-configure-pua-protection)
- [PowerShell cmdlet](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-powershell-cmdlets-to-configure-pua-protection)

当 Windows Defender 在某个终结点上检测到 PUA 文件时，它将隔离该文件并以与普通威胁检测相同的格式（以“PUA:”开头）通知用户（[除非已禁用通知](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-notifications-windows-defender-antivirus)）。检测到的威胁也将显示在 [Windows 安全应用程序的隔离列表中](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-security-center-antivirus#detection-history)。

### PUA 通知和事件

管理员可通过多种方法查看 PUA 事件：

- 在 Windows 事件查看器中（而不是在 Microsoft Endpoint Configuration Manager 或 Intune 中）。
- 在电子邮件中（如果用于 PUA 检测的电子邮件通知已启用）。
- 在 [Windows Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus)事件日志中（PUA 事件记录在事件 ID 1116 下，并显示以下消息：“反恶意软件平台检测到恶意软件或其他潜在有害软件”）。

> [!NOTE]
> 用户将看到“*.exe 是一个潜在有害应用程序，已被 Microsoft Defender SmartScreen 阻止”。

### 允许列表应用程序

与 Microsoft Edge 一样，Windows Defender 防病毒提供了一种允许安装被错误阻止的文件或运行为完成某项任务所需的文件的方法。 如果发生此类情况，你可以启用允许列表文件。 有关详细信息，请参阅[如何在配置服务器中配置 Endpoint Protection](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#to-exclude-specific-files-or-folders) 以了解如何排除特定文件或文件夹。

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [威胁防护](https://docs.microsoft.com/windows/security/threat-protection/index)
- [配置行为型、启发式的实时保护](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-protection-features-windows-defender-antivirus)
- [下一代保护](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)
- [基于 Chromium 的 Microsoft Edge 版本 79 的安全性基线](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/security-baseline-final-for-chromium-based-microsoft-edge/ba-p/1111863)
