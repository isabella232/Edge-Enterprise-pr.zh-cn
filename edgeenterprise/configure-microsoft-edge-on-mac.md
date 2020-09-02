---
title: 使用 .plist 配置用于 macOS 的 Microsoft Edge
ms.author: brianalt
author: kelleyvice-msft
manager: laurawi
ms.date: 02/14/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 使用 .plist 在 macOS 上配置 Microsoft Edge 策略设置
ms.openlocfilehash: 84469a4f84deeee0e47b6d8899426fa36cf345aa
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979202"
---
# 使用 .plist 配置适用于 macOS 的 Microsoft Edge 策略设置

本文介绍了如何使用属性列表 (.plist) 文件在 macOS 上配置 Microsoft Edge。 你将了解如何创建此文件，然后将其部署到 Microsoft Intune。

有关详细信息，请参阅[关于信息属性列表文件](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html)（Apple 的网站）和[自定义负载设置](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1)。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## 在 macOS 上配置 Microsoft Edge 策略

第一步是创建 plist。 你可以使用任何文本编辑器创建 plist 文件，也可以[使用终端创建配置文件](#create-a-configuration-profile-using-terminal)。 但是，通过使用为你设置 XML 代码格式的工具，可以更加轻松地创建和编辑 plist 文件。 *Xcode* 是可从以下其中一个位置获取的免费集成开发环境：

- [Apple 开发人员网站](https://developer.apple.com/xcode/)
- [Mac App Store](https://apps.apple.com/app/xcode/id497799835?mt=12)

有关受支持的策略及其首选项键名称的列表，请参阅 [Microsoft Edge 浏览器策略参考](microsoft-edge-policies.md)。 在可从 [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)下载的策略模板文件中，**示例**文件夹中有一个示例 plist (*itadminexample.plist*)。 示例文件包含所有受支持的数据类型，你可以自定义这些数据类型以定义你的策略设置。 

创建 plist 内容后，下一步是使用 Microsoft Edge 首选项域 *.com*。 名称区分大小写，不应包含你的目标频道，因为它适用于所有 Microsoft Edge 频道。 plist 文件名必须是 **_com.microsoft.Edge.plist_**。 

> [!IMPORTANT]
> 从版本 78.0.249.2 开始，macOS 上的所有 Microsoft Edge 频道都从 **com.microsoft.Edge** 首选项域中读取。 以前的所有版本都从特定于频道的域（如开发人员频道的 **com.microsoft.Edge.Dev**）中读取。

最后一步是使用首选的 MDM 提供程序（如 Microsoft Intune ）将 plist 部署到用户的 Mac 设备。 有关说明，请参阅[部署 plist](#deploy-your-plist)。

### 使用终端创建配置文件

1. 在终端中，使用以下命令和你的首选设置在桌面上创建 Microsoft Edge plist：

   ```cmd
   /usr/bin/defaults write ~/Desktop/com.microsoft.Edge.plist RestoreOnStartup -int 1
   ```

2. 将 plist 从二进制格式转换为纯文本格式：

   ```cmd
   /usr/bin/plutil -convert xml1 ~/Desktop/com.microsoft.Edge.plist
   ```
在转换文件后，验证策略数据是否正确，以及是否包含你希望用于配置文件的设置。

> [!NOTE]
> plist 或 xml 文件的内容中应仅有键值对。 将文件上传到 Intune 之前，请从你的文件中删除所有 \<plist> 和 \<dict> 值以及 xml 标头。 该文件应仅包含键值对。

## 部署你的 plist

对于 Microsoft Intune，请创建面向 macOS 平台的新设备配置文件，然后选择*首选项文件*配置文件类型。 将 **com.microsoft.Edge** 作为目标首选项域名，然后上传你的 plist。 有关详细信息，请参阅[使用 Microsoft Intune 将属性列表文件添加到 macOS 设备中](https://docs.microsoft.com/intune/configuration/preference-file-settings-macos)。

对于 Jamf，将 plist 文件作为*自定义设置*负载上传。

## 常见问题

### Microsoft Edge 可以配置为使用主首选项吗？

可以，你可以将 Microsoft Edge 配置为使用主首选项文件。

主首选项文件允许你在部署 Microsoft Edge 时配置浏览器用户配置文件的默认设置。 你还可以使用主首选项文件在未由设备管理系统管理的计算机上应用设置。 当用户首次运行浏览器时，这些设置将应用于用户的配置文件。 在用户运行浏览器后，不会应用对主首选项文件所做的更改。 用户可以在浏览器中更改主首选项的设置。 如果你想要在首次运行浏览器后将设置设为强制性设置或更改设置，则必须使用策略。

主首选项文件允许你为浏览器自定义许多不同的设置和首选项，包括与其他基于 Chromium 的浏览器共享以及特定于 Microsoft Edge 的那些设置和首选项。  与策略相关的首选项可使用主首选项文件进行配置。 如果设置了策略，并且有相应的主首选项集，则该策略设置优先。

> [!IMPORTANT]
> 所有可用的首选项可能与 Microsoft Edge 术语和命名约定不一致。  不能保证这些首选项将继续在将来的版本中按预期方式运行。 在更高版本中，首选项可能会发生更改或被忽略。

主首选项文件是使用 JSON 标记进行格式设置的文本文件。 此文件需要添加到 msedge.exe 可执行文件所在的目录中。 对于 macOS 上的系统范围内的企业部署，这通常是：“*~/Library/Application Support/Microsoft/Microsoft Edge Master Preferences*”或“*/Library/Microsoft/Microsoft Edge Master Preferences*”。

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [使用 Jamf 为 macOS 配置](configure-microsoft-edge-on-mac-jamf.md)
- [针对 Windows进行配置](configure-microsoft-edge.md)
- [使用 Intune 针对 Windows进行配置](configure-edge-with-intune.md)
