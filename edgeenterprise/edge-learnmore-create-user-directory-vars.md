---
title: 创建 Microsoft Edge 用户数据目录变量
ms.author: brianalt
author: AndreaLBarr
manager: srugh
ms.date: 04/21/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解如何创建 Microsoft Edge 用户数据目录变量
ms.openlocfilehash: 5ec78f16c7e5cd43f01845f35b8473494cd0c4bf
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "11618030"
---
# <a name="create-microsoft-edge-user-data-directory-variables"></a>创建 Microsoft Edge 用户数据目录变量

本文介绍了如何在修改 Microsoft Edge 时使用数据目录变量，而不是使用硬编码路径。

>[!NOTE]
>本文适用于 Microsoft Edge 版本 77 或更高版本。
## <a name="path-variables"></a>路径变量

用于修改数据目录路径的策略（例如，配置 [UserDataDir](microsoft-edge-policies.md#userdatadir) 或 [DownloadDirectory](microsoft-edge-policies.md#downloaddirectory) 支持变量。 配置这些策略时，可以使用变量，而不是硬编码路径。 例如，将你的配置文件数据存储在 Windows 上的“用户本地应用程序数据”下，而不是存储在默认位置。 将 [UserDataDir](microsoft-edge-policies.md#userdatadir) 策略设置为 **${local_app_data}\Edge\Profile**。 在大多数 Windows 10 安装中，此路径会解析为 *C:\Users\\&lt;Current-user&gt;\AppData\Local\Microsoft\Edge\Profile*。

>[!NOTE]
>若要查看当前**配置文件路径**，请打开 **“关于版本”** 页（键入“edge://version”）。 **配置文件路径**遵循以下格式：*C:\Users\\&lt;Current-user&gt;\AppData\Local\Microsoft\Edge\User Data\Default*。

### <a name="guidance-for-using-path-variables"></a>路径变量使用指南

在使用路径变量之前，请查看以下指南。

- 涉及 Microsoft Edge 存储不同数据的路径的所有策略均取决于平台。 其中的某些策略仅在特定平台上可用，但其他策略可在所有平台上使用。
- 为了避免因应用程序在不同场合从不同位置启动而导致的错误，请确保路径是绝对路径。
- 每个变量在一个路径中只能出现一次。 对于大多数情况，这是使用变量的唯一有意义的方式，因为它们会解析为绝对路径。
- 如果不存在路径，那么几乎所有策略都将创建路径（如有可能，在现有环境中创建）。
- 对某些策略使用网络位置可能会导致意外的结果，因为 Microsoft Edge 的不同版本/渠道处理文件夹结构的方式不同。

### <a name="supported-path-variables"></a>支持的路径变量

Microsoft Edge 支持以下路径变量。

#### <a name="all-platforms"></a>所有平台

| 变量 | 说明 |
| --- | --- |
| **${user_name}** | 使用 Microsoft Edge 的用户。 Microsoft Edge 遵循 SUID（在执行时设置所有者用户 ID）示例：*audreysmall* |
| **${machine_name}** | 计算机名称，可能包括域名。 示例：*audreysmall* 或 *audrey.ex.contoso.com* |

#### <a name="windows-only"></a>仅适用于 Windows

| 变量 | 说明 |
| --- | --- |
| **${documents}** | 当前用户的“文档”文件夹。 示例：*C:\Users\Administrator\Documents* |
|**${local_app_data}** | 当前用户的“应用程序数据”文件夹。 示例：*C:\Users\Administrator\AppData\Local* |
|**${roaming_app_data}** | 当前用户的“漫游应用程序数据”文件夹。 示例：*C:\Users\Administrator\AppData\Roaming* |
| **${profile}** | 当前用户的主文件夹。 示例：*C:\Users\Administrator* |
| **${global_app_data}** | 系统范围的“应用程序数据”文件夹。 示例：*C:\AppData* |
| **${program_files}** | 当前进程的“程序文件”文件夹。 此文件夹取决于它是 32 位还是 64 位进程。 示例解决方法：*C:\Program Files (x86)* |
| **${windows}** | “Windows”文件夹。 示例：*C:\Windows* |
| **${client_name)** | 连接到 RDP 或 Citrix 会话的客户端电脑的名称。 如果在本地会话中使用此变量，则此变量为空。 如果在路径中使用它，请在它前面加上一定不为空的部分。 示例：*对于远程会话，C:\edge_profiles\session_${client_name}* 将解析为 *C:\edge_profiles\session_&lt;ForlocalSessions&gt;* 和 *C:\edge_profiles\session_&lt;SomePCname&gt;*。 |
| **${session_name}** | 活动会话的名称。 使用此名称可区分使用单个用户配置文件的多个同时连接的远程会话。 示例：*用于本地桌面会话的 WinSta0* |

#### <a name="macos-only"></a>仅 macOS

| 变量 | 说明 |
| --- | --- |
| **${users}** | 存储用户配置文件的文件夹。 示例：*/Users* |
| **${documents}** | 当前用户的“文档”文件夹。 示例：*/Users/audreysmall/Documents* |

## <a name="content-license"></a>内容许可证

>[!NOTE]
>本页面的某些部分是根据 Chromium.org 创建和共享的作品所做的修改，并根据 [Creative Commons Attribution 4.0 国际许可证](http://creativecommons.org/licenses/by/4.0/)中所述的条款进行使用。 可在[此处](https://www.chromium.org/administrators/policy-list-3/user-data-directory-variables)找到原始页面。
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br/>此作品通过 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 国际许可证</a>获得许可。
## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)