---
title: 使用 System Center Configuration Manager 部署 Microsoft Edge
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/30/2019
audience: ITPro
ms.topic: procedural
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解如何使用 System Center Configuration Manager (SCCM) 部署 Microsoft Edge。
ms.openlocfilehash: 64b26412c4596a9514227d41d1a4e753a66ed057
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447826"
---
# <a name="deploy-microsoft-edge-using-system-center-configuration-manager"></a>使用 System Center Configuration Manager 部署 Microsoft Edge

本文向你介绍了如何使用 System Center Configuration Manager (SCCM) 自动部署 Microsoft Edge。

>[!NOTE]
>本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="before-you-begin"></a>开始之前

请查看 [Configuration Manager 中的应用程序管理简介](/sccm/apps/understand/introduction-to-application-management)中的信息。 此应用程序管理文章将帮助你了解本文中使用的术语，并且是准备站点以安装应用程序的指南。

从 [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)下载 Microsoft Edge Enterprise 安装文件（**MicrosoftEdgeDevEnterpriseX64.msi** 和/或 **MicrosoftEdgeDevEnterpriseX86.msi**）。

请确保将 Microsoft Edge 安装文件存储在可访问的网络位置。

## <a name="create-the-application"></a>创建应用程序

你将使用 Configuration Manager 向导创建应用程序。

### <a name="start-the-create-application-wizard-and-create-the-application"></a>启动创建应用程序向导并创建应用程序  

1. 在 Configuration Manager 控制台中，单击**软件库** > **应用程序管理** > **应用程序**。  

2. 在**主页**选项卡上的**创建**组中，单击**创建应用程序**。 或者，在导航栏中右键单击**应用程序**，然后单击**创建应用程序**。

    ![创建应用程序](./media/edge-ent-deployment-sccm/edge-ent-create-app-1.png)

3. 在**创建应用程序向导**的**常规**页上，选中**自动检测安装文件中有关此应用程序的信息**复选框。 这将使用从 .msi 安装文件中提取的信息来预填充向导中的某些信息。 请提供以下信息：  

   - **类型**：选择 **Windows Installer（\*.msi 文件）**。  

   - **位置**：键入安装文件 **MicrosoftEdgeDevEnterpriseX64.msi** 或 **MicrosoftEdgeDevEnterpriseX86.msi** 的位置（或单击**浏览**以选择位置）。 请注意，为了使 Configuration Manager 找到安装文件，必须以 *\\\Server\Share\File* 的形式指定位置。  

   你的**为此应用程序指定设置**页面将如以下示例所示：  

    ![为此应用程序指定设置](./media/edge-ent-deployment-sccm/edge-ent-create-app-2.png)

4. 单击**下一步**。 在**导入的信息**页面上的**详细信息**下，你将看到有关应用程序和已导入的任何关联文件的信息。 单击**下一步**以继续运行向导。  

    ![查看导入的信息](./media/edge-ent-deployment-sccm/edge-ent-create-app-3.png)

5. 在**常规信息**页面上，你可以添加有关应用程序的详细信息。 例如，软件版本、管理员备注和发布者。 你可以使用此信息来帮助你在 Configuration Manager 控制台中排序和查找应用程序。

   你还可以使用**安装程序**字段指定将用于在电脑上安装应用程序的完整命令行。 你可以编辑此项以添加自己的属性（例如添加 **/q** 以进行无人参与安装）。

   以下屏幕截图显示了一个示例，其中使用了**指定有关此应用程序的信息**字段。

   ![指定应用程序元数据](./media/edge-ent-deployment-sccm/edge-ent-create-app-5.png)

6. 单击**下一步**。
7. 在**摘要**页上，你可以在**详细信息**下面确认应用程序设置，然后完成向导。 单击**下一步**。  

    ![应用程序设置的详细信息](./media/edge-ent-deployment-sccm/edge-ent-create-app-6.png)

8. 在**完成**页上，单击**关闭**。

    ![“成功”对话框](./media/edge-ent-deployment-sccm/edge-ent-create-app-7.png)

你已完成了应用程序的创建。 使用以下步骤在 Configuration Manager 中查看它：

- 选择**软件库**工作区
- 展开**应用程序管理**
- 单击**应用程序**。

以下屏幕截图显示了本文使用的示例。  

![应用程序](./media/edge-ent-deployment-sccm/edge-ent-create-app-8.png)

## <a name="change-application-properties-and-deployment-settings"></a>更改应用程序属性和部署设置

创建应用程序后，你可以根据需要优化应用程序设置。 若要查看应用程序属性，请执行以下操作：

- 选择应用程序
- 在**主页**>**属性**中，单击**属性**。  

   ![配置应用程序属性](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-1.png)

 在 **<application name\> 应用程序属性**对话框页面中，你将看到可配置以更改应用程序行为的项目的选项卡式视图。 有关你可以配置的设置的详细信息，请参阅[创建应用程序](/sccm/apps/deploy-use/create-applications)。

在此示例中，你将更改应用程序部署类型的某些属性。 要更改部署属性，请执行以下操作：

1. 单击**部署类型**选项卡。
2. 在**部署类型:** 下面，选择应用程序**名称**
3. 单击**编辑**。

   ![编辑部署类型](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-2.png)

### <a name="add-a-requirement-to-the-deployment-type"></a>将要求添加到部署类型中

 要求指定在设备上安装应用程序之前必须满足的条件。 你可以从内置要求中进行选择，也可以创建自己的要求。 例如，你可以添加一个要求，要求将应用程序仅安装在运行 **Windows 10 x86** 或 **x64** 的电脑上，具体取决于安装文件的目标处理器体系结构。 在此示例中，你将指定 Windows 10 **x86**。

1. 从你刚打开的部署类型属性页中，单击**要求**选项卡。

2. 单击**添加**以打开**创建要求**对话框。

    ![创建要求](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-3.png)

3. 在**创建要求**对话框中，指定下列信息：

    - **类别**：**设备**  

    - **条件**：**操作系统**  

    - **规则类型**：**值**  

    - **运算符**：**其中一个**  

    - 从操作系统列表中，选择 **Windows 10** > **所有 Windows 10（32 位）**。  

    完成操作后，对话框看起来将类似于以下屏幕截图示例：

    ![添加要求](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-4.png)

4. 单击**确定**以关闭每个打开的属性页，然后返回到 Configuration Manager 控制台中的**应用程序**列表。  

## <a name="add-the-application-content-to-a-distribution-point"></a>将应用程序内容添加到分发点  

若要将更新后的应用程序部署到电脑，请确保将应用程序内容复制到分发点。 电脑访问分发点以安装应用程序。  

>[!TIP]
>若要了解有关 Configuration Manager 中的分发点和内容管理的详细信息，请参阅[部署和管理 System Center Configuration Manager 的内容](/sccm/core/servers/deploy/configure/deploy-and-manage-content)。  

1. 在 Configuration Manager 控制台中，单击**软件库**。  

2. 在**软件库**工作区中，展开**应用程序**。 在应用程序列表中选择你创建的应用程序。

3. 在**主页**选项卡上的**部署**组中，单击**分发内容**。  

4. 在**分发内容向导**的**常规**页上，检查应用程序名称是否正确，然后单击**下一步**。  

5. 在**内容**页上，查看将复制到分发点的信息，然后单击**下一步**。  

6. 在**内容目标**页上，单击**添加**以选择要在其上安装应用程序内容的一个或多个集合、分发点或分发点组。

7. 完成该向导。

你可以在**分发状态** > **内容状态**下检查应用程序内容是否已成功从**监视**工作区复制到分发点。  

## <a name="deploy-the-application"></a>部署应用程序  

接下来，将应用程序部署到层次结构中的设备集合。 在此示例中，你将应用程序部署到**所有系统**设备集合。  

>[!TIP]
>请记住，由于你先前选择了一些要求，因此只有具有指定处理器体系结构的 Windows 10 计算机才会安装该应用程序。  

1. 在 Configuration Manager 控制台中，单击**软件库** > **应用程序管理** > **应用程序**。

2. 从应用程序列表中，选择你先前创建的应用程序。 然后，在**主页**选项卡上的**部署**组中，单击**部署**，或者右键单击应用程序，然后选择**部署**。

    ![部署应用程序](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-1.png)

3. 在**部署软件向导**的**常规**页上，单击**浏览**以选择要向其部署应用程序的设备集合。

    ![浏览到安装文件](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-2.png)

4. 在**内容**页上，检查是否选择了要让电脑从其中安装应用程序的分发点。

    ![指定分发点](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-6.png)

5. 在**部署设置**页上，确保将部署操作设置为**安装**，然后将部署目的设置为**必需**。

    ![配置部署设置](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-8.png)

    >[!TIP]
    >通过将部署目的设置为**必需**，可确保将应用程序安装在满足你设定的要求的电脑上。 如果将此值设置为**可用**，则用户可以根据需要通过软件中心安装应用程序。  

6. 在**计划**页面上，你可以配置应用程序的安装时间。 对于本示例，请选择**在可用时间之后尽快**。

    ![计划部署](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-9.png)

7. 在**用户体验**页面上，选择所需的值并单击**下一步**。

    ![指定用户体验](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-10.png)

8. 指定所需的警报选项，然后单击**下一步**。

    ![指定警报设置](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-11.png)

9. 完成该向导。

使用以下**监视应用程序**部分中的信息查看应用程序部署的状态。  

## <a name="monitor-the-application"></a>监视应用程序

 在此部分中，你可以快速查看刚部署的应用程序的部署状态。  

### <a name="to-review-the-deployment-status"></a>要查看部署状态，请执行以下操作  

1. 在 Configuration Manager 控制台中，单击**监视** > **部署**。  

2. 从部署列表中，选择应用程序。

    ![监视部署](./media/edge-ent-deployment-sccm/edge-ent-monitor-deployment.png)

3. 在**主页**选项卡上的**部署**组中，单击**查看状态**。  

4. 选择以下选项卡之一，查看有关应用程序部署的更多状态更新：  

    - **成功**：已在指示的电脑上成功安装应用程序。  

    - **正在进行**：应用程序尚未完成安装。  

    - **错误**：在指示的电脑上安装应用程序时发生错误。 还将显示有关错误的更多信息。  

    - **未满足要求**：未在指示的设备上尝试安装，因为设备不符合你配置的要求（在此示例中，因为设备未运行 Windows 10。）

    - **未知**：Configuration Manager 无法报告部署的状态。 请稍后重新查看。  

    >[!TIP]
    >可以通过多种方法监视应用程序部署。 有关详细信息，请参阅[通过 System Center Configuration Manager 控制台监视应用程序](/sccm/apps/deploy-use/monitor-applications-from-the-console)。  

## <a name="end-user-experience"></a>最终用户体验  

如果用户拥有 Configuration Manager 管理的电脑，并且正在运行指定处理器体系结构的 Windows 10，那么这些用户将看到一条消息，得知自己必须安装 Microsoft Edge Dev 应用程序。 当他们接受此安装选项时，将安装该应用程序。  

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [使用 System Center Configuration Manager 创建和部署应用程序](/sccm/apps/get-started/create-and-deploy-an-application)