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
# <a name="deploy-microsoft-edge-using-system-center-configuration-manager"></a><span data-ttu-id="a2103-103">使用 System Center Configuration Manager 部署 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a2103-103">Deploy Microsoft Edge using System Center Configuration Manager</span></span>

<span data-ttu-id="a2103-104">本文向你介绍了如何使用 System Center Configuration Manager (SCCM) 自动部署 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="a2103-104">This article shows you how to automate a Microsoft Edge deployment by using System Center Configuration Manager (SCCM).</span></span>

>[!NOTE]
><span data-ttu-id="a2103-105">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a2103-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a2103-106">开始之前</span><span class="sxs-lookup"><span data-stu-id="a2103-106">Before you begin</span></span>

<span data-ttu-id="a2103-107">请查看 [Configuration Manager 中的应用程序管理简介](/sccm/apps/understand/introduction-to-application-management)中的信息。</span><span class="sxs-lookup"><span data-stu-id="a2103-107">Review the information in [Introduction to application management in Configuration Manager](/sccm/apps/understand/introduction-to-application-management).</span></span> <span data-ttu-id="a2103-108">此应用程序管理文章将帮助你了解本文中使用的术语，并且是准备站点以安装应用程序的指南。</span><span class="sxs-lookup"><span data-stu-id="a2103-108">This application management article will help you understand the terminology used in this article and is a guide to preparing your site to install applications.</span></span>

<span data-ttu-id="a2103-109">从 [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)下载 Microsoft Edge Enterprise 安装文件（**MicrosoftEdgeDevEnterpriseX64.msi** 和/或 **MicrosoftEdgeDevEnterpriseX86.msi**）。</span><span class="sxs-lookup"><span data-stu-id="a2103-109">Download the Microsoft Edge Enterprise installation files (**MicrosoftEdgeDevEnterpriseX64.msi** and/or **MicrosoftEdgeDevEnterpriseX86.msi**) from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise).</span></span>

<span data-ttu-id="a2103-110">请确保将 Microsoft Edge 安装文件存储在可访问的网络位置。</span><span class="sxs-lookup"><span data-stu-id="a2103-110">Make sure you store the Microsoft Edge installation files in an accessible network location.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="a2103-111">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="a2103-111">Create the application</span></span>

<span data-ttu-id="a2103-112">你将使用 Configuration Manager 向导创建应用程序。</span><span class="sxs-lookup"><span data-stu-id="a2103-112">You'll create the application using a Configuration Manager wizard.</span></span>

### <a name="start-the-create-application-wizard-and-create-the-application"></a><span data-ttu-id="a2103-113">启动创建应用程序向导并创建应用程序</span><span class="sxs-lookup"><span data-stu-id="a2103-113">Start the Create Application Wizard and create the application</span></span>  

1. <span data-ttu-id="a2103-114">在 Configuration Manager 控制台中，单击**软件库** > **应用程序管理** > **应用程序**。</span><span class="sxs-lookup"><span data-stu-id="a2103-114">In the Configuration Manager console, click **Software Library** > **Application Management** > **Applications**.</span></span>  

2. <span data-ttu-id="a2103-115">在**主页**选项卡上的**创建**组中，单击**创建应用程序**。</span><span class="sxs-lookup"><span data-stu-id="a2103-115">On the **Home** tab, in the **Create** group, click **Create Application**.</span></span> <span data-ttu-id="a2103-116">或者，在导航栏中右键单击**应用程序**，然后单击**创建应用程序**。</span><span class="sxs-lookup"><span data-stu-id="a2103-116">Or, right-click on **Applications** in the navigation bar and then click **Create Application**.</span></span>

    ![创建应用程序](./media/edge-ent-deployment-sccm/edge-ent-create-app-1.png)

3. <span data-ttu-id="a2103-118">在**创建应用程序向导**的**常规**页上，选中**自动检测安装文件中有关此应用程序的信息**复选框。</span><span class="sxs-lookup"><span data-stu-id="a2103-118">On the **General** page of the **Create Application Wizard**, choose **Automatically detect information about this application from installation files**.</span></span> <span data-ttu-id="a2103-119">这将使用从 .msi 安装文件中提取的信息来预填充向导中的某些信息。</span><span class="sxs-lookup"><span data-stu-id="a2103-119">This pre-populates some of the information in the wizard with information that's extracted from the installation .msi file.</span></span> <span data-ttu-id="a2103-120">请提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="a2103-120">Provide the following information:</span></span>  

   - <span data-ttu-id="a2103-121">**类型**：选择 **Windows Installer（\*.msi 文件）**。</span><span class="sxs-lookup"><span data-stu-id="a2103-121">**Type**: Choose **Windows Installer (\*.msi file)**.</span></span>  

   - <span data-ttu-id="a2103-122">**位置**：键入安装文件 **MicrosoftEdgeDevEnterpriseX64.msi** 或 **MicrosoftEdgeDevEnterpriseX86.msi** 的位置（或单击**浏览**以选择位置）。</span><span class="sxs-lookup"><span data-stu-id="a2103-122">**Location**: Type the location (or click **Browse** to select the location) of the installation file **MicrosoftEdgeDevEnterpriseX64.msi** or **MicrosoftEdgeDevEnterpriseX86.msi**.</span></span> <span data-ttu-id="a2103-123">请注意，为了使 Configuration Manager 找到安装文件，必须以 *\\\Server\Share\File* 的形式指定位置。</span><span class="sxs-lookup"><span data-stu-id="a2103-123">Note that the location must be specified in the form *\\\Server\Share\File* for Configuration Manager to locate the installation files.</span></span>  

   <span data-ttu-id="a2103-124">你的**为此应用程序指定设置**页面将如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="a2103-124">Your **Specify settings for this application** page will look like the following example:</span></span>  

    ![为此应用程序指定设置](./media/edge-ent-deployment-sccm/edge-ent-create-app-2.png)

4. <span data-ttu-id="a2103-126">单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a2103-126">Click **Next**.</span></span> <span data-ttu-id="a2103-127">在**导入的信息**页面上的**详细信息**下，你将看到有关应用程序和已导入的任何关联文件的信息。</span><span class="sxs-lookup"><span data-stu-id="a2103-127">Under **Details** on the **Imported Information** page, you'll see information about the application and any associated files that were imported.</span></span> <span data-ttu-id="a2103-128">单击**下一步**以继续运行向导。</span><span class="sxs-lookup"><span data-stu-id="a2103-128">Click **Next** to continue with the wizard.</span></span>  

    ![查看导入的信息](./media/edge-ent-deployment-sccm/edge-ent-create-app-3.png)

5. <span data-ttu-id="a2103-130">在**常规信息**页面上，你可以添加有关应用程序的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a2103-130">On the **General Information** page, you can add more information about the application.</span></span> <span data-ttu-id="a2103-131">例如，软件版本、管理员备注和发布者。</span><span class="sxs-lookup"><span data-stu-id="a2103-131">For example, Software version, Administrator comments, and Publisher.</span></span> <span data-ttu-id="a2103-132">你可以使用此信息来帮助你在 Configuration Manager 控制台中排序和查找应用程序。</span><span class="sxs-lookup"><span data-stu-id="a2103-132">You can use this information to to help you sort and find the application in the Configuration Manager console.</span></span>

   <span data-ttu-id="a2103-133">你还可以使用**安装程序**字段指定将用于在电脑上安装应用程序的完整命令行。</span><span class="sxs-lookup"><span data-stu-id="a2103-133">You can also use the **Installation program** field to specify the full command line that will be used to install the application on PCs.</span></span> <span data-ttu-id="a2103-134">你可以编辑此项以添加自己的属性（例如添加 **/q** 以进行无人参与安装）。</span><span class="sxs-lookup"><span data-stu-id="a2103-134">You can edit this to add your own properties (for example, **/q** for an unattended installation).</span></span>

   <span data-ttu-id="a2103-135">以下屏幕截图显示了一个示例，其中使用了**指定有关此应用程序的信息**字段。</span><span class="sxs-lookup"><span data-stu-id="a2103-135">The following screenshot shows an example where the **Specify information about this application** fields are used.</span></span>

   ![指定应用程序元数据](./media/edge-ent-deployment-sccm/edge-ent-create-app-5.png)

6. <span data-ttu-id="a2103-137">单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a2103-137">Click **Next**.</span></span>
7. <span data-ttu-id="a2103-138">在**摘要**页上，你可以在**详细信息**下面确认应用程序设置，然后完成向导。</span><span class="sxs-lookup"><span data-stu-id="a2103-138">On the **Summary** page, you can confirm your application settings under **Details** and then finish using the wizard.</span></span> <span data-ttu-id="a2103-139">单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a2103-139">Click **Next**.</span></span>  

    ![应用程序设置的详细信息](./media/edge-ent-deployment-sccm/edge-ent-create-app-6.png)

8. <span data-ttu-id="a2103-141">在**完成**页上，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="a2103-141">On the **Completion** page, click **Close**.</span></span>

    ![“成功”对话框](./media/edge-ent-deployment-sccm/edge-ent-create-app-7.png)

<span data-ttu-id="a2103-143">你已完成了应用程序的创建。</span><span class="sxs-lookup"><span data-stu-id="a2103-143">You've finished creating the application.</span></span> <span data-ttu-id="a2103-144">使用以下步骤在 Configuration Manager 中查看它：</span><span class="sxs-lookup"><span data-stu-id="a2103-144">Use the following steps to see it in Configuration Manager:</span></span>

- <span data-ttu-id="a2103-145">选择**软件库**工作区</span><span class="sxs-lookup"><span data-stu-id="a2103-145">select the **Software Library** workspace</span></span>
- <span data-ttu-id="a2103-146">展开**应用程序管理**</span><span class="sxs-lookup"><span data-stu-id="a2103-146">expand **Application Management**</span></span>
- <span data-ttu-id="a2103-147">单击**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="a2103-147">click **Applications**.</span></span>

<span data-ttu-id="a2103-148">以下屏幕截图显示了本文使用的示例。</span><span class="sxs-lookup"><span data-stu-id="a2103-148">The following screenshot shows the example used for this article.</span></span>  

![应用程序](./media/edge-ent-deployment-sccm/edge-ent-create-app-8.png)

## <a name="change-application-properties-and-deployment-settings"></a><span data-ttu-id="a2103-150">更改应用程序属性和部署设置</span><span class="sxs-lookup"><span data-stu-id="a2103-150">Change application properties and deployment settings</span></span>

<span data-ttu-id="a2103-151">创建应用程序后，你可以根据需要优化应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="a2103-151">After you create an application, you can refine the application settings if you need to.</span></span> <span data-ttu-id="a2103-152">若要查看应用程序属性，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a2103-152">To look at the application properties:</span></span>

- <span data-ttu-id="a2103-153">选择应用程序</span><span class="sxs-lookup"><span data-stu-id="a2103-153">select the application</span></span>
- <span data-ttu-id="a2103-154">在**主页**>**属性**中，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="a2103-154">in **Home**>**Properties**, click **Properties**.</span></span>  

   ![配置应用程序属性](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-1.png)

 <span data-ttu-id="a2103-156">在 **<application name\> 应用程序属性**对话框页面中，你将看到可配置以更改应用程序行为的项目的选项卡式视图。</span><span class="sxs-lookup"><span data-stu-id="a2103-156">In the **<application name\> Application Properties** dialog page, you'll see a tabbed view of the items that you can configure to change the behavior of the application.</span></span> <span data-ttu-id="a2103-157">有关你可以配置的设置的详细信息，请参阅[创建应用程序](/sccm/apps/deploy-use/create-applications)。</span><span class="sxs-lookup"><span data-stu-id="a2103-157">For more information about the settings you can configure, see [Create applications](/sccm/apps/deploy-use/create-applications).</span></span>

<span data-ttu-id="a2103-158">在此示例中，你将更改应用程序部署类型的某些属性。</span><span class="sxs-lookup"><span data-stu-id="a2103-158">For this example, you'll change some properties of the application's deployment type.</span></span> <span data-ttu-id="a2103-159">要更改部署属性，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a2103-159">To change the deployment properties:</span></span>

1. <span data-ttu-id="a2103-160">单击**部署类型**选项卡。</span><span class="sxs-lookup"><span data-stu-id="a2103-160">Click the **Deployment Types** tab.</span></span>
2. <span data-ttu-id="a2103-161">在**部署类型:** 下面，选择应用程序**名称**</span><span class="sxs-lookup"><span data-stu-id="a2103-161">Under **Deployment types:**, select the application **Name**</span></span>
3. <span data-ttu-id="a2103-162">单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="a2103-162">Click **Edit**.</span></span>

   ![编辑部署类型](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-2.png)

### <a name="add-a-requirement-to-the-deployment-type"></a><span data-ttu-id="a2103-164">将要求添加到部署类型中</span><span class="sxs-lookup"><span data-stu-id="a2103-164">Add a requirement to the deployment type</span></span>

 <span data-ttu-id="a2103-165">要求指定在设备上安装应用程序之前必须满足的条件。</span><span class="sxs-lookup"><span data-stu-id="a2103-165">Requirements specify conditions that must be met before an application is installed on a device.</span></span> <span data-ttu-id="a2103-166">你可以从内置要求中进行选择，也可以创建自己的要求。</span><span class="sxs-lookup"><span data-stu-id="a2103-166">You can choose from built-in requirements or you can create your own.</span></span> <span data-ttu-id="a2103-167">例如，你可以添加一个要求，要求将应用程序仅安装在运行 **Windows 10 x86** 或 **x64** 的电脑上，具体取决于安装文件的目标处理器体系结构。</span><span class="sxs-lookup"><span data-stu-id="a2103-167">For example, you can add a requirement that the application will only be installed on PCs that are running Windows 10 **x86** or **x64**, depending on the installation file's target processor architecture.</span></span> <span data-ttu-id="a2103-168">在此示例中，你将指定 Windows 10 **x86**。</span><span class="sxs-lookup"><span data-stu-id="a2103-168">In this example, you'll specify Windows 10 **x86**.</span></span>

1. <span data-ttu-id="a2103-169">从你刚打开的部署类型属性页中，单击**要求**选项卡。</span><span class="sxs-lookup"><span data-stu-id="a2103-169">From the deployment type properties page you just opened, click the **Requirements** tab.</span></span>

2. <span data-ttu-id="a2103-170">单击**添加**以打开**创建要求**对话框。</span><span class="sxs-lookup"><span data-stu-id="a2103-170">Click **Add** to open the **Create Requirement** dialog.</span></span>

    ![创建要求](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-3.png)

3. <span data-ttu-id="a2103-172">在**创建要求**对话框中，指定下列信息：</span><span class="sxs-lookup"><span data-stu-id="a2103-172">In the **Create Requirement** dialog box, specify the following information:</span></span>

    - <span data-ttu-id="a2103-173">**类别**：**设备**</span><span class="sxs-lookup"><span data-stu-id="a2103-173">**Category**: **Device**</span></span>  

    - <span data-ttu-id="a2103-174">**条件**：**操作系统**</span><span class="sxs-lookup"><span data-stu-id="a2103-174">**Condition**: **Operating system**</span></span>  

    - <span data-ttu-id="a2103-175">**规则类型**：**值**</span><span class="sxs-lookup"><span data-stu-id="a2103-175">**Rule type**: **Value**</span></span>  

    - <span data-ttu-id="a2103-176">**运算符**：**其中一个**</span><span class="sxs-lookup"><span data-stu-id="a2103-176">**Operator**: **One of**</span></span>  

    - <span data-ttu-id="a2103-177">从操作系统列表中，选择 **Windows 10** > **所有 Windows 10（32 位）**。</span><span class="sxs-lookup"><span data-stu-id="a2103-177">From the operating systems list, select **Windows 10** > **All Windows 10 (32-bit)**.</span></span>  

    <span data-ttu-id="a2103-178">完成操作后，对话框看起来将类似于以下屏幕截图示例：</span><span class="sxs-lookup"><span data-stu-id="a2103-178">When you're finished, the dialog will look like the following screenshot example:</span></span>

    ![添加要求](./media/edge-ent-deployment-sccm/edge-ent-create-app-req-4.png)

4. <span data-ttu-id="a2103-180">单击**确定**以关闭每个打开的属性页，然后返回到 Configuration Manager 控制台中的**应用程序**列表。</span><span class="sxs-lookup"><span data-stu-id="a2103-180">Click **OK** to close each open property page and return to the **Applications** list in the Configuration Manager console.</span></span>  

## <a name="add-the-application-content-to-a-distribution-point"></a><span data-ttu-id="a2103-181">将应用程序内容添加到分发点</span><span class="sxs-lookup"><span data-stu-id="a2103-181">Add the application content to a distribution point</span></span>  

<span data-ttu-id="a2103-182">若要将更新后的应用程序部署到电脑，请确保将应用程序内容复制到分发点。</span><span class="sxs-lookup"><span data-stu-id="a2103-182">To deploy the updated application to PCs, make sure that the application content is copied to a distribution point.</span></span> <span data-ttu-id="a2103-183">电脑访问分发点以安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="a2103-183">PCs access the distribution point to install the application.</span></span>  

>[!TIP]
><span data-ttu-id="a2103-184">若要了解有关 Configuration Manager 中的分发点和内容管理的详细信息，请参阅[部署和管理 System Center Configuration Manager 的内容](/sccm/core/servers/deploy/configure/deploy-and-manage-content)。</span><span class="sxs-lookup"><span data-stu-id="a2103-184">To find out more about distribution points and content management in Configuration Manager, see [Deploy and manage content for System Center Configuration Manager](/sccm/core/servers/deploy/configure/deploy-and-manage-content).</span></span>  

1. <span data-ttu-id="a2103-185">在 Configuration Manager 控制台中，单击**软件库**。</span><span class="sxs-lookup"><span data-stu-id="a2103-185">In the Configuration Manager console, click **Software Library**.</span></span>  

2. <span data-ttu-id="a2103-186">在**软件库**工作区中，展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="a2103-186">In the **Software Library** workspace, expand **Applications**.</span></span> <span data-ttu-id="a2103-187">在应用程序列表中选择你创建的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a2103-187">Select the application you created in the list of applications.</span></span>

3. <span data-ttu-id="a2103-188">在**主页**选项卡上的**部署**组中，单击**分发内容**。</span><span class="sxs-lookup"><span data-stu-id="a2103-188">On the **Home** tab in the **Deployment** group, click **Distribute Content**.</span></span>  

4. <span data-ttu-id="a2103-189">在**分发内容向导**的**常规**页上，检查应用程序名称是否正确，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a2103-189">On the **General** page of the **Distribute Content Wizard**, check that the application name is correct, and then click **Next**.</span></span>  

5. <span data-ttu-id="a2103-190">在**内容**页上，查看将复制到分发点的信息，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a2103-190">On the **Content** page, review the information that will be copied to the distribution point, and then click **Next**.</span></span>  

6. <span data-ttu-id="a2103-191">在**内容目标**页上，单击**添加**以选择要在其上安装应用程序内容的一个或多个集合、分发点或分发点组。</span><span class="sxs-lookup"><span data-stu-id="a2103-191">On the **Content Destination** page, click **Add** to select one or more collections, distribution points, or distribution point groups on which to install the application content.</span></span>

7. <span data-ttu-id="a2103-192">完成该向导。</span><span class="sxs-lookup"><span data-stu-id="a2103-192">Complete the wizard.</span></span>

<span data-ttu-id="a2103-193">你可以在**分发状态** > **内容状态**下检查应用程序内容是否已成功从**监视**工作区复制到分发点。</span><span class="sxs-lookup"><span data-stu-id="a2103-193">You can check that the application content was copied successfully to the distribution point from the **Monitoring** workspace, under **Distribution Status** > **Content Status**.</span></span>  

## <a name="deploy-the-application"></a><span data-ttu-id="a2103-194">部署应用程序</span><span class="sxs-lookup"><span data-stu-id="a2103-194">Deploy the application</span></span>  

<span data-ttu-id="a2103-195">接下来，将应用程序部署到层次结构中的设备集合。</span><span class="sxs-lookup"><span data-stu-id="a2103-195">Next, deploy the application to a device collection in your hierarchy.</span></span> <span data-ttu-id="a2103-196">在此示例中，你将应用程序部署到**所有系统**设备集合。</span><span class="sxs-lookup"><span data-stu-id="a2103-196">In this example, you deploy the application to the **All Systems** device collection.</span></span>  

>[!TIP]
><span data-ttu-id="a2103-197">请记住，由于你先前选择了一些要求，因此只有具有指定处理器体系结构的 Windows 10 计算机才会安装该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a2103-197">Remember that only Windows 10 computers of the specified processor architecture will install the application because of the requirements that you selected earlier.</span></span>  

1. <span data-ttu-id="a2103-198">在 Configuration Manager 控制台中，单击**软件库** > **应用程序管理** > **应用程序**。</span><span class="sxs-lookup"><span data-stu-id="a2103-198">In the Configuration Manager console, click **Software Library** > **Application Management** > **Applications**.</span></span>

2. <span data-ttu-id="a2103-199">从应用程序列表中，选择你先前创建的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a2103-199">From the list of applications, select the application that you created earlier.</span></span> <span data-ttu-id="a2103-200">然后，在**主页**选项卡上的**部署**组中，单击**部署**，或者右键单击应用程序，然后选择**部署**。</span><span class="sxs-lookup"><span data-stu-id="a2103-200">Then, on the **Home** tab in the **Deployment** group, click **Deploy**, or right-click the application and select **Deploy**.</span></span>

    ![部署应用程序](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-1.png)

3. <span data-ttu-id="a2103-202">在**部署软件向导**的**常规**页上，单击**浏览**以选择要向其部署应用程序的设备集合。</span><span class="sxs-lookup"><span data-stu-id="a2103-202">On the **General** page of the **Deploy Software Wizard**, click **Browse** to select the device collection to which you want to deploy the application.</span></span>

    ![浏览到安装文件](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-2.png)

4. <span data-ttu-id="a2103-204">在**内容**页上，检查是否选择了要让电脑从其中安装应用程序的分发点。</span><span class="sxs-lookup"><span data-stu-id="a2103-204">On the **Content** page, check that the distribution point from which you want PCs to install the application is selected.</span></span>

    ![指定分发点](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-6.png)

5. <span data-ttu-id="a2103-206">在**部署设置**页上，确保将部署操作设置为**安装**，然后将部署目的设置为**必需**。</span><span class="sxs-lookup"><span data-stu-id="a2103-206">On the **Deployment Settings** page, make sure that the deployment action is set to **Install**, and the deployment purpose is set to **Required**.</span></span>

    ![配置部署设置](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-8.png)

    >[!TIP]
    ><span data-ttu-id="a2103-208">通过将部署目的设置为**必需**，可确保将应用程序安装在满足你设定的要求的电脑上。</span><span class="sxs-lookup"><span data-stu-id="a2103-208">By setting the deployment purpose to **Required**, you make sure that the application is installed on PCs that meet the requirements that you set.</span></span> <span data-ttu-id="a2103-209">如果将此值设置为**可用**，则用户可以根据需要通过软件中心安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="a2103-209">If you set this value to **Available**, then users can install the application on demand from Software Center.</span></span>  

6. <span data-ttu-id="a2103-210">在**计划**页面上，你可以配置应用程序的安装时间。</span><span class="sxs-lookup"><span data-stu-id="a2103-210">On the **Scheduling** page, you can configure when the application will be installed.</span></span> <span data-ttu-id="a2103-211">对于本示例，请选择**在可用时间之后尽快**。</span><span class="sxs-lookup"><span data-stu-id="a2103-211">For this example, select **As soon as possible after the available time**.</span></span>

    ![计划部署](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-9.png)

7. <span data-ttu-id="a2103-213">在**用户体验**页面上，选择所需的值并单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a2103-213">On the **User Experience** page, select your desired values and click **Next**.</span></span>

    ![指定用户体验](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-10.png)

8. <span data-ttu-id="a2103-215">指定所需的警报选项，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a2103-215">Specify your desired alert options and click **Next**.</span></span>

    ![指定警报设置](./media/edge-ent-deployment-sccm/edge-ent-deploy-app-11.png)

9. <span data-ttu-id="a2103-217">完成该向导。</span><span class="sxs-lookup"><span data-stu-id="a2103-217">Complete the wizard.</span></span>

<span data-ttu-id="a2103-218">使用以下**监视应用程序**部分中的信息查看应用程序部署的状态。</span><span class="sxs-lookup"><span data-stu-id="a2103-218">Use the information in the following **Monitor the application** section to see the status of your application deployment.</span></span>  

## <a name="monitor-the-application"></a><span data-ttu-id="a2103-219">监视应用程序</span><span class="sxs-lookup"><span data-stu-id="a2103-219">Monitor the application</span></span>

 <span data-ttu-id="a2103-220">在此部分中，你可以快速查看刚部署的应用程序的部署状态。</span><span class="sxs-lookup"><span data-stu-id="a2103-220">In this section, you'll take a quick look at the deployment status of the application that you just deployed.</span></span>  

### <a name="to-review-the-deployment-status"></a><span data-ttu-id="a2103-221">要查看部署状态，请执行以下操作</span><span class="sxs-lookup"><span data-stu-id="a2103-221">To review the deployment status</span></span>  

1. <span data-ttu-id="a2103-222">在 Configuration Manager 控制台中，单击**监视** > **部署**。</span><span class="sxs-lookup"><span data-stu-id="a2103-222">In the Configuration Manager console, click **Monitoring** > **Deployments**.</span></span>  

2. <span data-ttu-id="a2103-223">从部署列表中，选择应用程序。</span><span class="sxs-lookup"><span data-stu-id="a2103-223">From the list of deployments, select the application.</span></span>

    ![监视部署](./media/edge-ent-deployment-sccm/edge-ent-monitor-deployment.png)

3. <span data-ttu-id="a2103-225">在**主页**选项卡上的**部署**组中，单击**查看状态**。</span><span class="sxs-lookup"><span data-stu-id="a2103-225">On the **Home** tab in the **Deployment** group, click **View Status**.</span></span>  

4. <span data-ttu-id="a2103-226">选择以下选项卡之一，查看有关应用程序部署的更多状态更新：</span><span class="sxs-lookup"><span data-stu-id="a2103-226">Select one of the following tabs to see more status updates about the application deployment:</span></span>  

    - <span data-ttu-id="a2103-227">**成功**：已在指示的电脑上成功安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="a2103-227">**Success**: The application installed successfully on the indicated PCs.</span></span>  

    - <span data-ttu-id="a2103-228">**正在进行**：应用程序尚未完成安装。</span><span class="sxs-lookup"><span data-stu-id="a2103-228">**In Progress**: The application has not yet finished installing.</span></span>  

    - <span data-ttu-id="a2103-229">**错误**：在指示的电脑上安装应用程序时发生错误。</span><span class="sxs-lookup"><span data-stu-id="a2103-229">**Error**: An error occurred installing the application on the indicated PCs.</span></span> <span data-ttu-id="a2103-230">还将显示有关错误的更多信息。</span><span class="sxs-lookup"><span data-stu-id="a2103-230">Further information about the error is also displayed.</span></span>  

    - <span data-ttu-id="a2103-231">**未满足要求**：未在指示的设备上尝试安装，因为设备不符合你配置的要求（在此示例中，因为设备未运行 Windows 10。）</span><span class="sxs-lookup"><span data-stu-id="a2103-231">**Requirements Not Met**: No installation attempt was made on the indicated devices because they did not meet the requirements you configured (in this example, because they do not run on Windows 10.)</span></span>

    - <span data-ttu-id="a2103-232">**未知**：Configuration Manager 无法报告部署的状态。</span><span class="sxs-lookup"><span data-stu-id="a2103-232">**Unknown**: Configuration Manager was unable to report the status of the deployment.</span></span> <span data-ttu-id="a2103-233">请稍后重新查看。</span><span class="sxs-lookup"><span data-stu-id="a2103-233">Check back again later.</span></span>  

    >[!TIP]
    ><span data-ttu-id="a2103-234">可以通过多种方法监视应用程序部署。</span><span class="sxs-lookup"><span data-stu-id="a2103-234">There are several ways you can monitor application deployments.</span></span> <span data-ttu-id="a2103-235">有关详细信息，请参阅[通过 System Center Configuration Manager 控制台监视应用程序](/sccm/apps/deploy-use/monitor-applications-from-the-console)。</span><span class="sxs-lookup"><span data-stu-id="a2103-235">For more information, see [Monitor applications from the System Center Configuration Manager console](/sccm/apps/deploy-use/monitor-applications-from-the-console).</span></span>  

## <a name="end-user-experience"></a><span data-ttu-id="a2103-236">最终用户体验</span><span class="sxs-lookup"><span data-stu-id="a2103-236">End-user experience</span></span>  

<span data-ttu-id="a2103-237">如果用户拥有 Configuration Manager 管理的电脑，并且正在运行指定处理器体系结构的 Windows 10，那么这些用户将看到一条消息，得知自己必须安装 Microsoft Edge Dev 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a2103-237">Users who have PCs that are managed by Configuration Manager and are running Windows 10 of the specified processor architecture, will see a message telling them that they must install the Microsoft Edge Dev application.</span></span> <span data-ttu-id="a2103-238">当他们接受此安装选项时，将安装该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a2103-238">When they accept this installation option, the application is installed.</span></span>  

## <a name="see-also"></a><span data-ttu-id="a2103-239">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2103-239">See also</span></span>

- [<span data-ttu-id="a2103-240">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="a2103-240">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="a2103-241">使用 System Center Configuration Manager 创建和部署应用程序</span><span class="sxs-lookup"><span data-stu-id="a2103-241">Create and deploy an application with System Center Configuration Manager</span></span>](/sccm/apps/get-started/create-and-deploy-an-application)