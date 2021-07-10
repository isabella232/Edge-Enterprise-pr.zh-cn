---
title: 使用 Jamf 自动部署适用于 macOS 的 Microsoft Edge
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 如何使用 Jamf 自动部署适用于 macOS 的 Microsoft Edge。
ms.openlocfilehash: 9c8fc0af734d4784ac122602b685bc561aabf340
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642058"
---
# <a name="deploy-to-macos-with-jamf"></a>使用 Jamf 部署到 macOS

本文介绍了如何使用 Jamf 部署适用于 macOS 的 Microsoft Edge。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="prerequisites"></a>先决条件

在部署 Microsoft Edge 之前，请确保满足以下先决条件：

- Microsoft Edge 安装文件 **MicrosoftEdgeDev-\<version\>.pkg** 位于网络上的一个可访问位置中。 你可以从 [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)下载 Microsoft Edge Enterprise 安装文件。
- 你拥有一个 Jamf 云帐户，该帐户具有创建安装文件并将其部署到计算机所需的访问权限和特权级别。

## <a name="to-deploy-microsoft-edge-using-jamf"></a>要使用 Jamf 部署 Microsoft Edge，请执行以下操作：

1. 登录到 Jamf，然后转到**所有设置**。

    ![打开“所有设置”](./media/mac-deploy/jamf-dash-main-open-settings.png)

2. 在**所有设置**下，单击**计算机管理**。

    ![选择“计算机管理”](./media/mac-deploy/jamf-all-settings-computer-mgmt.png)

3. 在**计算机管理**下，单击**程序包**。

    ![选择程序包](./media/mac-deploy/jamf-all-settings-computer-mgmt-pkgs.png)

4. 在**程序包**页面上，单击 **+ 新建**以添加新程序包。

    ![选择“新建”以添加新程序包](./media/mac-deploy/jamf-all-settings-computer-mgmt-new-pkg.png)

5. 在**新建包**页面上，输入有关程序包的详细信息，然后单击**保存**。 （例如，“显示名称”、“信息”或“备注”。）

    ![选择“保存”以保存程序包信息](./media/mac-deploy/jamf-all-settings-computer-mgmt-save-pkg-info.png)

6. 在菜单栏上选择**计算机**，然后在导航栏中选择**策略**。

7. 选择 **+ 新建**以显示**新建策略**窗格。

    ![选择“新建”以创建新策略。](./media/mac-deploy/jamf-all-settings-computer-new-policy.png)

8. 在**选项**选项卡上，选择**常规**。

    - 在**显示名称**下，输入策略的显示名称。
    - 在**触发器**下，选择将触发该策略的事件。 （在下面的示例中，事件为“启动”。）

    ![输入部署信息](./media/mac-deploy/jamf-all-settings-computer-cfg-policy.png)

9. 在**选项**选项卡上，单击**程序包**。

10. 在**配置程序包**弹出窗口上，单击**配置**。

    ![配置程序包](./media/mac-deploy/jamf-all-settings-computer-policy-pkg-configure.png)

11. 你添加的程序包将显示在**程序包**窗格上。 单击**添加**。 在此示例中，程序包为以下屏幕截图中的“MicrosoftEdgeBeta”。

    ![添加程序包](./media/mac-deploy/jamf-all-settings-computer-policy-pkg-add-beta.png)

12. 在**新建策略**页上，使用下拉列表选择要为策略采用的**分发点**和**操作**。 单击**保存**。 以下屏幕截图以“每台计算机的默认分发点”和“安装”为例。

    ![选择分发点和操作](./media/mac-deploy/jamf-all-settings-computer-mgmt-pkg-cfg-distro.png)

13. 在**新建策略**页上，选择**范围**选项卡。你可以根据计算机或用户来管理部署的范围。 在此示例中，请从**目标计算机**下拉列表中选择**所有计算机**，然后单击**保存**。

    ![选择部署范围](./media/mac-deploy/jamf-all-settings-computer-mgmt-add-target.png)

14. 此时，你可以查看 Microsoft Edge 部署策略。 如果部署选项满足你的要求，请单击**完成**。

    ![单击“完成”](./media/mac-deploy/jamf-all-settings-computer-mgmt-finish-add-deployment.png)

    > [!NOTE]
    > 你可以随时返回到部署策略来更改设置。

恭喜你！ 你刚才已完成使用 Jamf 部署适用于 macOS 的 Microsoft Edge 的配置。 当你定义的触发器条件为 true 时，程序包将部署到你指定的计算机。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [Jamf.com](https://www.jamf.com/)
- [将 Jamf 与 Microsoft Intune 集成](/intune/conditional-access-integrate-jamf)