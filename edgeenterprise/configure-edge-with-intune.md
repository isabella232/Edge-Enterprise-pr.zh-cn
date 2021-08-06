---
title: 使用 Microsoft Intune 配置适用于 Windows 的 Microsoft Edge 策略设置
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 使用 Microsoft Intune 配置适用于 Windows 的 Microsoft Edge 策略设置。
ms.openlocfilehash: cd11c8c92d67197d9cf1a24691615b0a56dd727626b9741b5664a5d1080ba950
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "11725453"
---
# <a name="configure-microsoft-edge-policy-settings-with-microsoft-intune"></a>使用 Microsoft Intune 配置 Microsoft Edge 策略设置

本文说明了如何使用 Microsoft Intune 配置适用于 Windows 10 的 Microsoft Edge 策略设置。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

你可以通过将设备配置文件添加到 Microsoft Intune 来配置 Microsoft Edge 策略和设置。 使用 Intune 管理和实施策略等同于在用户设备上使用 Active Directory 组策略或配置本地组策略对象 (GPO) 设置。

有关使用 Microsoft Intune 管理 Microsoft Edge 策略的详细信息，可以阅读[通过将 Microsoft Edge 和 Microsoft Intune 配合使用来管理 Web 访问](/intune/manage-microsoft-edge)，但是请记住，链接的文章特定于 Microsoft Edge 45 及更早版本，因此可能包含不适用于 Microsoft Edge Enterprise 77 及更高版本的信息和参考。

> [!TIP]
> 有关如何使用 Microsoft Intune 配置 macOS 上的 Microsoft Edge 的信息，请参阅[为 macOS 配置](configure-microsoft-edge-on-mac.md)。

## <a name="create-a-profile-to-manage-settings-in-microsoft-edge-for-windows-10"></a>创建配置文件以管理适用于 Windows 10 的 Microsoft Edge 中的设置

使用 Microsoft Intune 中的管理模板，你可以使用云管理 Windows 10 设备上的 Microsoft Edge 组策略。 此部分将帮助你创建模板来配置 Microsoft Edge 特定的应用程序设置。 当你创建模板时，它将创建一个设备配置文件。 然后，你可以将此配置文件分配或部署到你的组织中的 Windows 10 设备。

### <a name="prerequisites"></a>先决条件

- Windows 10 以及以下最低系统要求：
  - Windows 10 版本 1909
  - Windows 10 版本 1903（已安装 [KB4512941](https://support.microsoft.com/kb/4512941)）
  - Windows 10 版本 1809（已安装 [KB4512534](https://support.microsoft.com/kb/4512534)）
  - Windows 10 版本 1803（已安装 [KB4512509](https://support.microsoft.com/kb/4512509)）
  - Windows 10 版本 1709（已安装 [KB4516071](https://support.microsoft.com/kb/4516071)）

### <a name="use-administrative-templates-to-create-a-policy-for-microsoft-edge"></a>使用管理模板创建适用于 Microsoft Edge 的策略

此过程利用 Intune 中内置的管理模板（你可能在组策略中见到过）。 可通过在预配置列表中选择“设置”，使用这些模板为 Microsoft Edge 创建策略。

1. 登录 [Microsoft Endpoint Manager ](https://endpoint.microsoft.com/)门户。
2. 在左侧导航窗格中选择**设备**。
3. 从**设备** | **概述**中，选择 **配置文件**（在“策略”标题下）。
4. 在顶部命令栏中，选择**创建配置文件**。
5. 在**平台**下方的下拉列表中，选择 **Windows 10 及更高版本**。
6. 在**配置文件**下方的下拉列表中，选择**管理模板**然后单击**创建**按钮。 下一个屏幕截图将显示下拉列表，以选择平台和配置文件类型。

    ![选择平台和配置文件类型](./media/configure-edge-with-intune/create-profile-platform.png)

7. 在**基础知识**选项卡上，输入描述性**名称**，如 Microsoft Edge 策略。 （可选）输入策略的 **描述**。
下一个屏幕截图将显示**基础知识**选项卡的窗体，并且菜单栏将显示后续步骤（灰显选项卡）以创建配置文件。

   ![输入名称和描述](./media/configure-edge-with-intune/create-profile-basics-tab.png)

8. 选择**下一步** 。
9. 在**配置设置**选项卡上，选择以下任一位置中的 Microsoft Edge 文件夹：

   - 位于“计算机配置”文件夹下方
   - 位于“用户配置”文件夹下方。

   Microsoft Edge 的可用设置将显示在右窗格中。 例如，下面的屏幕截图中所示的*计算机配置/Microsoft Edge/允许下载限制*。

   ![配置设置选项卡](./media/configure-edge-with-intune/create-profile-configuration-settings-tab.png)

   > [!NOTE]
   > 有关 Microsoft Edge 的所有可用设置的最完整和最新的列表，请参阅 [Microsoft Edge – 策略](./microsoft-edge-policies.md)和 [Microsoft Edge – 更新策略](./microsoft-edge-update-policies.md)。

10. 使用搜索字段（“搜索以筛选项目 ...”）查找想要配置的特定设置。 在此示例中，搜索字符串是“主页”。 下一个屏幕截图将显示搜索结果。

    ![搜索结果](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-search.png)

11. 找到打算配置的设置后，选择它以公开可设置的值。 在接下来的屏幕截图中，我们选择了“配置主页 URL”作为示例。

    ![配置主页 URL 策略](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-edit-pol.png)

12. 启用策略并为主页 URL 输入一个值，如前面的屏幕截图所示。

13. 单击“确定”****。 设置“状态”列应显示为“已启用”，如以下屏幕截图示例中所示。

    ![设置状态为已启用](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-set-enabled.png)

14. 单击“下一步”**** 按钮。

15. 在**范围标记**选项卡上，根据需要添加范围标记，否则单击**下一步**按钮。

16. 在**分配**选项卡上，单击 **+ 选择要包括的组**将此策略分配给包含要接收此策略设置的设备或用户的 Azure Active Directory (Azure AD) 组。 请参阅[在 Microsoft Intune 中分配用户和设备配置文件](/intune/device-profile-assign)，以获取有关如何将配置文件分配给 Azure AD 用户或设备组的信息。

    ![选择要包含的组](./media/configure-edge-with-intune/create-profile-assignments-tab.png)

17. 单击“下一步”**** 按钮。

18. 在**审阅 + 创建**选项卡上，查看更改摘要以确保其正确，然后单击**创建**按钮。

19. 新创建的策略（Microsoft Edge 策略）显示在以下屏幕截图中。

    ![选择要包含的组](./media/configure-edge-with-intune/create-profile-new-policy-finished.png)

有关 Windows 10 配置文件的详细信息，请参阅[使用 Windows 10 模板在 Microsoft Intune 中配置组策略设置](/intune/administrative-templates-windows)。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [通过将 Microsoft Edge 和 Microsoft Intune 配合使用来管理 Web 访问](/intune/manage-microsoft-edge)
- [使用 Windows 10 模板在 Microsoft Intune 中配置组策略设置](/intune/administrative-templates-windows)
- [使用 Microsoft Intune 部署 Microsoft Edge](/intune/apps/apps-windows-edge/?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)