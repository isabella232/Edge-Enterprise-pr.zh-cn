---
title: 使用Microsoft Edge列表配置适用于 macOS 的客户端。
ms.author: brianalt
author: kelleyvice-msft
manager: laurawi
ms.date: 12/14/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 了解如何使用可部署到 Microsoft Edge 的属性列表在 macOS 上配置 Microsoft Intune。
ms.openlocfilehash: 4cb3d635c8fc108a3b81ec17175ce0e3d8fa287a
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2022
ms.locfileid: "12297695"
---
# <a name="configure-microsoft-edge-policy-settings-for-macos-using-a-property-list"></a>使用Microsoft Edge列表配置 macOS 的策略设置

本文介绍如何使用 Microsoft Edge\.plist 文件的属性列表在 macOS (配置) 文件。 你将了解如何创建此文件，然后将其部署到 Microsoft Intune。

有关详细信息，请参阅[关于信息属性列表文件](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html)（Apple 的网站）和[自定义负载设置](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1)。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="configure-microsoft-edge-policies-on-macos"></a>在 macOS 上配置 Microsoft Edge 策略

第一步是创建 plist。 可以使用任何文本编辑器创建 plist 文件。 另一个选项是使用 [终端创建配置文件](#create-a-configuration-profile-using-terminal)。 但是，使用可设置 XML 代码格式的工具更轻松地创建和编辑 plist 文件。 *Xcode* 是一个免费的集成开发环境，可在以下位置使用：

- [Apple 开发人员网站](https://developer.apple.com/xcode/)
- [Mac App Store](https://apps.apple.com/app/xcode/id497799835?mt=12)

有关受支持的策略及其首选项键名称的列表，请参阅 [Microsoft Edge 浏览器策略参考](./microsoft-edge-policies.md)。 在可以从[Microsoft Edge Enterprise](https://aka.ms/EdgeEnterprise)登录页面下载的策略模板文件中，示例文件夹中有一个 plist 示例 (*itadminexample.plist* **) 。** 此文件包含可自定义以定义策略设置的所有受支持的数据类型。

创建 plist 的内容后，使用首选项域（即 *"com.microsoft.Edge"）Microsoft Edge*plist。 此名称区分大小写，不应包含你面向的频道，因为它适用于所有Microsoft Edge频道。 plist 文件名必须是 **_com.microsoft.Edge.plist_**。

> [!IMPORTANT]
> 从版本 78.0.249.2 开始，macOS 上的所有 Microsoft Edge 频道都从 **com.microsoft.Edge** 首选项域中读取。 以前的所有版本都从特定于频道的域（如开发人员频道的 **com.microsoft.Edge.Dev**）中读取。

最后一步是使用首选的 MDM 提供程序（如 Microsoft Intune ）将 plist 部署到用户的 Mac 设备。 有关说明，请参阅[部署 plist](#deploy-your-plist)。

### <a name="create-a-configuration-profile-using-terminal"></a>使用终端创建配置文件

1. 在终端中，使用以下命令和你的首选设置在桌面上创建 Microsoft Edge plist：

   ```cmd
   /usr/bin/defaults write ~/Desktop/com.microsoft.Edge.plist RestoreOnStartup -int 1
   ```

2. 将 plist 从二进制格式转换为纯文本格式：

   ```cmd
   /usr/bin/plutil -convert xml1 ~/Desktop/com.microsoft.Edge.plist
   ```

转换文件后，请验证策略数据是否正确并包含设置，以用于配置文件。

> [!NOTE]
> plist 或 xml 文件的内容中应仅有键值对。 将文件上传到 Intune 之前，请从你的文件中删除所有 \<plist> 和 \<dict> 值以及 xml 标头。 该文件应仅包含键值对。

## <a name="deploy-your-plist"></a>部署你的 plist

使用 Microsoft Intune，创建面向 macOS 平台的新设备配置文件并选择*首选项文件*配置文件类型。 将 **com.microsoft.Edge** 作为目标首选项域名，然后上传你的 plist。 有关详细信息，请参阅使用 Microsoft Intune[将属性列表文件添加到 macOS 设备](/intune/configuration/preference-file-settings-macos)。

对于 Jamf，将 \.plist 文件作为*自定义*负载设置上载。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [使用 Jamf 为 macOS 配置](configure-microsoft-edge-on-mac-jamf.md)
- [针对 Windows 进行配置](configure-microsoft-edge.md)
- [使用 Intune 针对 Windows 进行配置](configure-edge-with-intune.md)