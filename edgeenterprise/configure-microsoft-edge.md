---
title: 配置适用于 Windows 的 Microsoft Edge
ms.author: brianalt
author: kelleyvice-msft
manager: laurawi
ms.date: 10/09/2019
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 在 Windows 设备上配置 Microsoft Edge 策略设置
ms.openlocfilehash: 99aaf002f868ce29e81aa40024fa1de2e83d76e1
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979203"
---
# 在 Windows 上配置 Microsoft Edge 策略设置

使用以下信息在 Windows 设备上配置 Microsoft Edge 策略设置。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## 在 Windows 上配置策略设置

你可以使用_组策略对象 (GPO)_ 在所有版本的 Windows 上配置 Microsoft Edge 和受托管 Microsoft Edge 更新的策略设置。 你还可以通过注册表为已加入 Microsoft Active Directory 域的 Windows 设备或在 Microsoft Intune 中注册设备管理的 Windows 10 专业版或企业版实例预配策略。 若要使用组策略对象配置 Microsoft Edge，请安装_管理模板_，以便将 Microsoft Edge 的规则和设置添加到 Active Directory 域内的组策略中央存储中，或者单台计算机上的策略定义模板文件夹中，然后配置想要设置的特定策略。

如果你想要在域级别管理策略，可以使用 Active Directory 组策略配置 Microsoft Edge 策略设置。 这样，你可以全局管理策略设置，并将不同的策略设置定向到特定的 OU，或使用 WMI 过滤器仅将设置应用于特定查询返回的用户或计算机。 如果你想要在单台计算机上配置策略，可以使用目标计算机上的本地组策略编辑器应用仅影响本地设备的策略设置。

Microsoft Edge 支持_强制_和_推荐的_策略。 强制策略会覆盖用户首选项并阻止用户对其进行更改，而推荐的策略则提供可能会被用户覆盖的默认设置。 大多数策略都是纯强制性策略，部分是强制性和推荐的策略。 如果设置了这两种策略，则强制性设置优先。

>[!TIP]
> 你可以使用 Microsoft Intune 配置 Microsoft Edge 策略设置。 有关详细信息，请参阅[使用 Microsoft Intune 配置 Microsoft Edge](configure-edge-with-intune.md)。

有以下两个适用于 Microsoft Edge 的管理模板，这两个模板都可以在计算机或 Active Directory 域级别应用：

- *msedge.admx*，用于[配置 Microsoft Edge 设置](microsoft-edge-policies.md)
- *msedgeupdate.admx*，用于[管理 Microsoft Edge 更新](microsoft-edge-update-policies.md)。

首先，请下载并安装 Microsoft Edge 管理模板。

### 1. 下载并安装 Microsoft Edge 管理模板

如果你想要在 Active Directory 中配置 Microsoft Edge 策略设置，请将文件下载到可从安装有远程服务器管理工具 (RSAT) 的域控制器或工作站中访问的网络位置。 若要在单台计算机上进行配置，只需将文件下载到该计算机。

将管理模板文件添加到相应位置时，Microsoft Edge 策略设置将在组策略编辑器中立即可用。

转到 [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)以下载 Microsoft Edge 策略模板文件 (*MicrosoftEdgePolicyTemplates.cab*)，然后提取内容。

#### 将管理模板添加到 Active Directory 中

1. 在带有 RSAT 的域控制器或工作站上，浏览到适用于你的域的任何域控制器上的 **PolicyDefinition** 文件夹（也称为_中央存储_）。 对于较旧版本的 Windows Server，你可能需要创建 PolicyDefinition 文件夹。 有关详细信息，请参阅[如何在 Windows 中为组策略管理模板创建和管理中央存储](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)。
1. 打开 *MicrosoftEdgePolicyTemplates*，然后转到**窗口** > **admx**。
1. 将 *msedge.admx* 文件复制到 PolicyDefinition 文件夹。 （示例：%systemroot%\sysvol\domain\policies\PolicyDefinitions）
1. 在 *admx* 文件夹中，打开相应的语言文件夹。 例如，如果你在美国，请打开 **en-US** 文件夹。
1. 将 *msedge.adml* 文件复制到 PolicyDefinition 文件夹内匹配的语言文件夹中。 如果此文件夹尚不存在，请创建它。 （示例：%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US）
1. 如果你的域有多个域控制器，则新 ADMX 文件将按下一个域复制间隔复制到这些域控制器。
1. 要确认是否正确加载了文件，请从 Windows 管理工具中打开**组策略管理编辑器**，然后展开**计算机配置** > **策略** > **管理模板** > **Microsoft Edge**。 你应该会看到如下所示的一个或多个 Microsoft Edge 节点。

    ![Microsoft Edge 策略](./media/configure-microsoft-edge/edge-gpo-policies.png)

#### 将管理模板添加到单台计算机中

1. 在目标计算机上，打开 *MicrosoftEdgePolicyTemplates*，然后转到**窗口** > **admx**。
2. 将 *msedge.admx* 文件复制到“策略定义”模板文件夹。 （示例：C:\Windows\PolicyDefinitions）
3. 在 *admx* 文件夹中，打开相应的语言文件夹。 例如，如果你在美国，请打开 **en-US** 文件夹。
4. 将 *msedge.adml* 文件复制到“策略定义”文件夹内匹配的语言文件夹中。 （示例：C:\Windows\PolicyDefinitions\en-US）
5. 要确认是否正确加载了文件，请直接打开本地组策略编辑器（Windows 键 + R，然后输入 gpedit.msc），或者打开 MMC，然后加载本地组策略编辑器管理单元。 如果发生错误，通常是因为文件的位置不正确。

<!--
To add the administrative template to manage Microsoft Edge updates:

1. Open the *MicrosoftEdgePolicyTemplates* file and go to **windows** > **admx**.
2. Copy the *msedgeupdate.admx* file to your Policy Definition template folder. (Example: C:\Windows\PolicyDefinitions)
3. In the *updatepolicies* folder, open the appropriate language folder. For example, if you’re in Germany, open the **de-DE** folder.
4. Copy the *msedgeupdate.adml* file to the matching language folder in your Policy Definition folder. (Example: C:\Windows\PolicyDefinitions\de-DE)
5. Open MMC and load the Local Group Policy Editor snap-in to confirm the files loaded correctly. If an error occurs, it’s usually because the files are in an incorrect location.

> [!NOTE]
> Currently the Microsoft Edge update policies are only localized in en-US. Additional language support will be added in a future release.
-->

### 2. 设置强制性或推荐的策略

你可以设置强制性或推荐的策略，以针对 Active Directory 和单台计算机使用组策略编辑器配置 Microsoft Edge。 你可以选择适当的节点以将策略设置范围设置为**计算机配置**或**用户配置**，如下所述。

- 要配置强制性策略，请打开组策略编辑器，然后转到（**计算机配置**或**用户配置**）> **策略** > **管理模板** > **Microsoft Edge**。
- 要配置推荐的策略，请打开组策略编辑器，然后转到（**计算机配置**或**用户配置**）> **策略** > **管理模板** > **Microsoft Edge - 默认设置（用户可以覆盖）**。

  ![打开本地组策略编辑器](./media/configure-microsoft-edge/edge-ad-policy.png)

### 3. 测试策略

在目标客户端设备上，打开 Microsoft Edge，然后导航到 **edge://policy** 以查看应用的所有策略。 如果你在本地计算机上应用了策略设置，则策略应该会立即显示出来。 如果你正在配置策略设置，则可能需要关闭并重新打开 Microsoft Edge（如果它处于打开状态）。

![在浏览器中查看配置的策略](./media/configure-microsoft-edge/edge-gpEdit.png)

对于 Active Directory 组策略设置，策略设置将按域管理员定义的定期时间间隔传播到域计算机，并且目标计算机可能无法立即收到策略更新。 若要在目标计算机上手动刷新 Active Directory 组策略设置，请在目标计算机上通过命令提示符或 PowerShell 会话执行以下命令：

``` powershell
gpupdate /force
```

你可能需要关闭并重新打开 Microsoft Edge，然后才会显示新策略。

你还可以在目标计算机上使用 REGEDIT.exe 来查看存储组策略设置的注册表设置。 这些设置位于注册表路径 **HKLM\SOFTWARE\Policies\Microsoft\Edge** 中。

## 常见问题

### Microsoft Edge 可以配置为使用主首选项吗？

可以，你可以将 Microsoft Edge 配置为使用主首选项文件。

 主首选项文件允许你在部署 Microsoft Edge 时配置默认设置。 你还可以使用主首选项文件在未由设备管理系统管理的计算机上应用设置。 当用户首次运行浏览器时，这些设置将应用于用户的配置文件。 在用户运行浏览器后，不会应用对主首选项文件所做的更改。 用户可以在浏览器中更改主首选项的设置。 如果你想要在首次运行浏览器后将设置设为强制性设置或更改设置，则必须使用策略。

主首选项文件允许你为浏览器自定义许多不同的设置和首选项，包括与其他基于 Chromium 的浏览器共享以及特定于 Microsoft Edge 的那些设置和首选项。  与策略相关的首选项可使用主首选项文件进行配置。 如果设置了策略，并且有相应的主首选项集，则该策略设置优先。

> [!IMPORTANT]
> 所有可用的首选项可能与 Microsoft Edge 术语和命名约定不一致。  不能保证这些首选项将继续在将来的版本中按预期方式运行。 在更高版本中，首选项可能会发生更改或被忽略。

主首选项文件是使用 JSON 标记进行格式设置的文本文件。 需要将此文件添加到 msedge.exe 可执行文件所在的相同目录中。 对于 Windows 上的系统范围内的企业部署，此目录通常为：*Windows：C:\Program Files\Microsoft\Edge\Application\master_preferences*。

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [使用 Intune 为 Windows 配置](configure-edge-with-intune.md)
- [为 macOS 配置](configure-microsoft-edge-on-mac.md)
- [浏览 Microsoft Edge 企业策略](microsoft-edge-policies.md)


