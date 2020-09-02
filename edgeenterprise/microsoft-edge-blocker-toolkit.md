---
title: 可禁止自动传递 Microsoft Edge 的阻止程序工具包
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 06/30/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 可禁止自动传递 Microsoft Edge 的阻止程序工具包
ms.openlocfilehash: 7563d2c94cf91a8434328699e46c75dbcfb77561
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979365"
---
# 可禁止自动传递 Microsoft Edge（基于 Chromium）的阻止程序工具包

本文介绍了可用于禁止自动传递和安装 Microsoft Edge 的阻止程序工具包， 本文在 **2020 年 1 月 9 日**更新可能需要使用组织程序工具包的设备详细信息，并在 **2020 年 2 月 28 日**从设备条件中删除了“MDM 托管”，以从此自动更新中排除，**2020 年 6 月 30 日** 将反映所有 Windows 更新连接设备都在接收此更新的范围内（最早于 2020 年 7 月 30 日生效）。

> [!NOTE]
> 适用于 Microsoft Edge 稳定渠道。

## 概述

为了帮助客户更安全和保持最新，Microsoft 将 Microsoft Edge（基于 Chromium）分发到运行 Windows 10 版本 1803 和更新版本的 Windows 更新连接设备。 此过程将于 2020 年 1 月 15 日后启动，届时将提供更多信息。

阻止程序工具包适用于以下组织：计划在运行 Windows 10 版本 1803 和更高版本的 Winodws 更新连接设备上阻止自动传递 Microsoft Edge（基于 Chromium）。
受 Windows Server Update Services (WSUS) 或适用于企业的 Windows 更新 (WUfB) 管理的设备将从该自动更新中排除。

**请务必注意：**

- 阻止程序工具包不会阻止用户从 Internet 下载或外部介质手动安装 Microsoft Edge（基于 Chromium）。
- 通过适用于企业的 Windows 更新 (WUfB) 管理更新的组织将不会自动收到此更新，也不需要部署阻止程序工具包。
- 通过更新管理解决方案（如 Windows Server Update Services (WSUS) 或 System Center Configuration Manager (SCCM)）管理环境的组织无需部署阻止程序工具包。 组织可以使用这些产品全面管理环境中通过 Windows 更新和 Microsoft 更新发布的更新的部署，包括 Microsoft Edge（基于 Chromium）。
- 此更新是独立更新（不是每月累积更新的一部分），可向企业客户提供灵活性，并使其能够最大程度地控制如何部署此更新。
- 新的 Microsoft Edge（基于Chromium）将在 2020 年下半年作为 Windows 10，版本 20H2 功能更新的一部分。 阻止程序工具包不会影响 20H2 的行为或部署。 了解更多信息，请参阅[此处](https://blogs.windows.com/windowsexperience/2020/06/16/whats-next-for-windows-10-updates/) Windows 10，版本 20H2。 

你可以从 [https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe](https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe) 下载阻止程序工具包的可执行文件。

### 工具包组件

本工具包包含以下组件：

- 阻止程序脚本可执行文件 (.CMD)
- 组策略管理模板（.ADMX 和 .ADML）

### 支持的操作系统

Windows 10 版本 1803 和更高版本。

## 阻止程序脚本

该脚本可在本地计算机或远程目标计算机上创建注册表项，并将关联的值设置为阻止或取消阻止（具体取决于所使用的命令行选项）Microsoft Edge（基于 Chromium）的自动传递。

**注册表项：** `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate`<br>
**注册表项名称：** `DoNotUpdateToEdgeWithChromium`

| 值                | 结果                         |
|----------------------|--------------------------------|
| *未定义注册表项* | 将*不会*阻止分发。 |
| 0                    | 将*不会*阻止分发。 |
| 1                    | 将阻止分发。       |

此脚本具有以下命令行语法：<br>
`EdgeChromium_Blocker.cmd [<machine name>] [/B] [/U] [/H]`

### 计算机名

`<machine name>` 参数是可选的。 如果未指定，则在本地计算机上执行操作。 否则，将通过 `REG` 命令的远程注册表功能访问远程计算机。 如果由于安全权限而导致无法访问远程注册表，或者找不到远程计算机，`REG` 命令将返回一条错误消息。

### 开关

脚本使用的开关是互斥的，因此将仅对给定命令中的第一个有效开关进行操作。 可在同一台计算机上多次运行该脚本。

| 开关       | 描述                              |
|--------------|------------------------------------------|
| `/B`         | 将阻止分发                      |
| `/U`         | 将取消阻止分发                    |
| `/H` 或者 `/?` | 将显示以下摘要帮助：<br>`This tool can be used to remotely block or unblock the delivery of Microsoft Edge (Chromium-based) through Automatic Updates.`<br> `Usage:`<br>`EdgeChromium_Blocker.cmd [<machine name>] [/B][/U][/H]`<br>`B = Block Microsoft Edge (Chromium-based) deployment`<br>`U = Allow Microsoft Edge (Chromium-based) deployment`<br>`H = Help`<br>`Examples:`<br>`EdgeChromium_Blocker.cmd mymachine /B (blocks delivery on machine "mymachine")`<br>`EdgeChromium_Blocker.cmd /U (unblocks delivery on the local machine)`<br> |

## 组策略管理模板（.ADMX 和 .ADML 文件）

组策略管理模板（.ADMX 和 .ADML 文件）允许管理员导入新的组策略设置，以阻止或取消阻止将 Microsoft Edge（基于 Chromium）自动传递到他们的组策略环境中，并使用组策略在其环境中的各个系统之间集中执行操作。

运行 Windows 10 RS3 Enterprise/EDU 和 RS4 及更高版本的用户将在以下路径下看到策略：

```
/Computer Configuration  
  /Administrative Templates
    /Classic Administrative Templates
      /Windows Components
        /Windows Update  
          /Microsoft Edge (Chromium-based) Blockers  
```

此设置只能用作计算机设置；没有每用户设置。

> [!IMPORTANT]
> 此注册表设置未存储在策略注册表项中，并且被视为*首选项*。 因此，如果实现该设置的组策略对象已被删除或策略设置为**未配置**，该设置将保留。 要通过使用组策略来取消阻止 Microsoft Edge（基于 Chromium）的分发，请将策略设置为**已禁用**。

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://www.microsoftedgeinsider.com/enterprise)
- [用于支持 Microsoft Edge 的 Windows 更新](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-windows-updates)
- [如何访问旧版本的 Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-access-old-edge)
