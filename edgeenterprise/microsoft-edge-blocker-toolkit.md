---
title: 可禁止自动传递 Microsoft Edge 的阻止程序工具包
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 12/16/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 可禁止自动传递 Microsoft Edge 的阻止程序工具包
ms.openlocfilehash: 9fb97d2dfec4822f8ce76dc3e37b85118c6572ad
ms.sourcegitcommit: 606282995b466a968bab40c16005a6653323c763
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "11229613"
---
# 可禁止自动传递 Microsoft Edge（基于 Chromium）的阻止程序工具包

本文介绍了可用于禁止自动传递和安装 Microsoft Edge 的阻止程序工具包，

本文进行了以下更新：

- **01/09/2020，** 详细了解可能要求你使用阻止程序Toolkit
- **2020 年 2 月 28** 日 从要从此自动更新中排除的设备条件中删除"MDM 托管"
- **2020 年 6 月 30 日** 以反映所有已连接 Windows 更新的设备均在接收此更新 (2020 年 7 月 30 日)  
- **2020 年 12 月 10** 日 解释 20H2 之前将忽略阻止程序Toolkit的情况

> [!NOTE]
> 适用于 Microsoft Edge 稳定渠道。

## 概述

为了帮助客户更安全和保持最新，Microsoft 将 Microsoft Edge（基于 Chromium）分发到运行 Windows 10 版本 1803 和更新版本的 Windows 更新连接设备。 此过程将于 2020 年 1 月 15 日后启动，届时将提供更多信息。

阻止程序工具包适用于以下组织：计划在运行 Windows 10 版本 1803 和更高版本的 Winodws 更新连接设备上阻止自动传递 Microsoft Edge（基于 Chromium）。 属于 Windows Server Update Services (WSUS) 或适用于企业的 Windows 更新 (WUfB) 的设备将从此自动 Windows 更新中排除，但可能会通过其组织接收新的 (基于 Chromium 的) Microsoft Edge。

**请务必注意：**

- 阻止程序工具包不会阻止用户从 Internet 下载或外部介质手动安装 Microsoft Edge（基于 Chromium）。
- 通过适用于企业的 Windows 更新 (WUfB) 管理更新的组织将不会自动收到此更新，也不需要部署阻止程序工具包。
- 通过更新管理解决方案（如 Windows Server Update Services (WSUS) 或 System Center Configuration Manager (SCCM)）管理环境的组织无需部署阻止程序工具包。 他们可以使用这些产品在其环境中完全管理通过 Windows 更新网站和 Microsoft 更新网站发布的更新的部署，包括 [WSUS](https://support.microsoft.com/help/4584642/update-in-wsus-for-the-new-microsoft-edge)中新 Microsoft Edge 的更新。
- 此更新是独立更新（不是每月累积更新的一部分），可向企业客户提供灵活性，并使其能够最大程度地控制如何部署此更新。
- 新的 Microsoft Edge (Chromium) 包含在 2020 年下半年的 Windows 10 版本 20H2 功能更新中。 阻止程序工具包不会影响 20H2 的行为或部署。 了解更多信息，请参阅[此处](https://blogs.windows.com/windowsexperience/2020/06/16/whats-next-for-windows-10-updates/) Windows 10，版本 20H2。 

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
