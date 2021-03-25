---
title: 使用 Jamf 自动部署适用于 macOS 的 Microsoft Edge
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 11/30/2019
audience: ITPro
ms.topic: technical
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 如何使用 Jamf 自动部署适用于 macOS 的 Microsoft Edge。
ms.openlocfilehash: f02b9efde872082cf2301a4cf66b0a3f3782e39b
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447486"
---
# <a name="deploy-to-macos-with-jamf"></a><span data-ttu-id="50ff8-103">使用 Jamf 部署到 macOS</span><span class="sxs-lookup"><span data-stu-id="50ff8-103">Deploy to macOS with Jamf</span></span>

<span data-ttu-id="50ff8-104">本文介绍了如何使用 Jamf 部署适用于 macOS 的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="50ff8-104">This article describes how to deploy Microsoft Edge for macOS using Jamf.</span></span>

> [!NOTE]
> <span data-ttu-id="50ff8-105">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="50ff8-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="50ff8-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="50ff8-106">Prerequisites</span></span>

<span data-ttu-id="50ff8-107">在部署 Microsoft Edge 之前，请确保满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="50ff8-107">Before you deploy Microsoft Edge, make sure you meet the following prerequisites:</span></span>

- <span data-ttu-id="50ff8-108">Microsoft Edge 安装文件 **MicrosoftEdgeDev-\<version\>.pkg** 位于网络上的一个可访问位置中。</span><span class="sxs-lookup"><span data-stu-id="50ff8-108">The Microsoft Edge installation file,  **MicrosoftEdgeDev-\<version\>.pkg** is in an accessible location on your network.</span></span> <span data-ttu-id="50ff8-109">你可以从 [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)下载 Microsoft Edge Enterprise 安装文件。</span><span class="sxs-lookup"><span data-stu-id="50ff8-109">You can download the Microsoft Edge Enterprise installation files from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise).</span></span>
- <span data-ttu-id="50ff8-110">你拥有一个 Jamf 云帐户，该帐户具有创建安装文件并将其部署到计算机所需的访问权限和特权级别。</span><span class="sxs-lookup"><span data-stu-id="50ff8-110">You have a Jamf Cloud account with the level of access and privileges needed to create and deploy installation files to computers.</span></span>

## <a name="to-deploy-microsoft-edge-using-jamf"></a><span data-ttu-id="50ff8-111">要使用 Jamf 部署 Microsoft Edge，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="50ff8-111">To deploy Microsoft Edge using Jamf:</span></span>

1. <span data-ttu-id="50ff8-112">登录到 Jamf，然后转到**所有设置**。</span><span class="sxs-lookup"><span data-stu-id="50ff8-112">Sign on to Jamf and go to **All Settings**.</span></span>

    ![打开“所有设置”](./media/mac-deploy/jamf-dash-main-open-settings.png)

2. <span data-ttu-id="50ff8-114">在**所有设置**下，单击**计算机管理**。</span><span class="sxs-lookup"><span data-stu-id="50ff8-114">Under **All Settings**, click **Computer Management**.</span></span>

    ![选择“计算机管理”](./media/mac-deploy/jamf-all-settings-computer-mgmt.png)

3. <span data-ttu-id="50ff8-116">在**计算机管理**下，单击**程序包**。</span><span class="sxs-lookup"><span data-stu-id="50ff8-116">Under **Computer Management**, click **Packages**.</span></span>

    ![选择程序包](./media/mac-deploy/jamf-all-settings-computer-mgmt-pkgs.png)

4. <span data-ttu-id="50ff8-118">在**程序包**页面上，单击 **+ 新建**以添加新程序包。</span><span class="sxs-lookup"><span data-stu-id="50ff8-118">On the **Packages** page, click **+ New** to add a new package.</span></span>

    ![选择“新建”以添加新程序包](./media/mac-deploy/jamf-all-settings-computer-mgmt-new-pkg.png)

5. <span data-ttu-id="50ff8-120">在**新建包**页面上，输入有关程序包的详细信息，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="50ff8-120">On the **New Package** page, enter the details about the package and then click **Save**.</span></span> <span data-ttu-id="50ff8-121">（例如，“显示名称”、“信息”或“备注”。）</span><span class="sxs-lookup"><span data-stu-id="50ff8-121">(For example, DISPLAY NAME, INFO, or NOTES.)</span></span>

    ![选择“保存”以保存程序包信息](./media/mac-deploy/jamf-all-settings-computer-mgmt-save-pkg-info.png)

6. <span data-ttu-id="50ff8-123">在菜单栏上选择**计算机**，然后在导航栏中选择**策略**。</span><span class="sxs-lookup"><span data-stu-id="50ff8-123">Select **Computers** on the menu bar, and then select **Policies** in the navigation bar.</span></span>

7. <span data-ttu-id="50ff8-124">选择 **+ 新建**以显示**新建策略**窗格。</span><span class="sxs-lookup"><span data-stu-id="50ff8-124">Select **+ New** to display the **New Policy** pane.</span></span>

    ![选择“新建”以创建新策略。](./media/mac-deploy/jamf-all-settings-computer-new-policy.png)

8. <span data-ttu-id="50ff8-126">在**选项**选项卡上，选择**常规**。</span><span class="sxs-lookup"><span data-stu-id="50ff8-126">On the **Options** tab, select **General**.</span></span>

    - <span data-ttu-id="50ff8-127">在**显示名称**下，输入策略的显示名称。</span><span class="sxs-lookup"><span data-stu-id="50ff8-127">Under **DISPLAY NAME**, enter the display name for the policy.</span></span>
    - <span data-ttu-id="50ff8-128">在**触发器**下，选择将触发该策略的事件。</span><span class="sxs-lookup"><span data-stu-id="50ff8-128">Under **Trigger**, select the event that will trigger the policy.</span></span> <span data-ttu-id="50ff8-129">（在下面的示例中，事件为“启动”。）</span><span class="sxs-lookup"><span data-stu-id="50ff8-129">(In the following example, the event is Startup.)</span></span>

    ![输入部署信息](./media/mac-deploy/jamf-all-settings-computer-cfg-policy.png)

9. <span data-ttu-id="50ff8-131">在**选项**选项卡上，单击**程序包**。</span><span class="sxs-lookup"><span data-stu-id="50ff8-131">On the **Options** tab, click **Packages**.</span></span>

10. <span data-ttu-id="50ff8-132">在**配置程序包**弹出窗口上，单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="50ff8-132">On the **Configure Packages** popup, click **Configure**.</span></span>

    ![配置程序包](./media/mac-deploy/jamf-all-settings-computer-policy-pkg-configure.png)

11. <span data-ttu-id="50ff8-134">你添加的程序包将显示在**程序包**窗格上。</span><span class="sxs-lookup"><span data-stu-id="50ff8-134">The package that you added shows on the **Packages** pane.</span></span> <span data-ttu-id="50ff8-135">单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="50ff8-135">Click **Add**.</span></span> <span data-ttu-id="50ff8-136">在此示例中，程序包为以下屏幕截图中的“MicrosoftEdgeBeta”。</span><span class="sxs-lookup"><span data-stu-id="50ff8-136">For this example, the package is "MicrosoftEdgeBeta" in the following screenshot.</span></span>

    ![添加程序包](./media/mac-deploy/jamf-all-settings-computer-policy-pkg-add-beta.png)

12. <span data-ttu-id="50ff8-138">在**新建策略**页上，使用下拉列表选择要为策略采用的**分发点**和**操作**。</span><span class="sxs-lookup"><span data-stu-id="50ff8-138">On the **New Policy** page, uUse the drop-down lists to select the **DISTRIBUTION POINT** and **ACTION** to take for the policy.</span></span> <span data-ttu-id="50ff8-139">单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="50ff8-139">Click **Save**.</span></span> <span data-ttu-id="50ff8-140">以下屏幕截图以“每台计算机的默认分发点”和“安装”为例。</span><span class="sxs-lookup"><span data-stu-id="50ff8-140">The following screenshot uses "Each computer's default distribution point" and "Install" as an example.</span></span>

    ![选择分发点和操作](./media/mac-deploy/jamf-all-settings-computer-mgmt-pkg-cfg-distro.png)

13. <span data-ttu-id="50ff8-142">在**新建策略**页上，选择**范围**选项卡。你可以根据计算机或用户来管理部署的范围。</span><span class="sxs-lookup"><span data-stu-id="50ff8-142">On the **New Policy** page, select the **Scope** tab. You can manage the scope of the deployment based on computers or users.</span></span> <span data-ttu-id="50ff8-143">在此示例中，请从**目标计算机**下拉列表中选择**所有计算机**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="50ff8-143">For this example, select **All Computers** from the **TARGET COMPUTERS** drop-down list and then click **Save**.</span></span>

    ![选择部署范围](./media/mac-deploy/jamf-all-settings-computer-mgmt-add-target.png)

14. <span data-ttu-id="50ff8-145">此时，你可以查看 Microsoft Edge 部署策略。</span><span class="sxs-lookup"><span data-stu-id="50ff8-145">At this point you can review the Microsoft Edge deployment policy.</span></span> <span data-ttu-id="50ff8-146">如果部署选项满足你的要求，请单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="50ff8-146">If the deployment options meet your requirements, click **Done**.</span></span>

    ![单击“完成”](./media/mac-deploy/jamf-all-settings-computer-mgmt-finish-add-deployment.png)

    > [!NOTE]
    > <span data-ttu-id="50ff8-148">你可以随时返回到部署策略来更改设置。</span><span class="sxs-lookup"><span data-stu-id="50ff8-148">You can return to a deployment policy at any time to change settings.</span></span>

<span data-ttu-id="50ff8-149">恭喜你！</span><span class="sxs-lookup"><span data-stu-id="50ff8-149">Congratulations!</span></span> <span data-ttu-id="50ff8-150">你刚才已完成使用 Jamf 部署适用于 macOS 的 Microsoft Edge 的配置。</span><span class="sxs-lookup"><span data-stu-id="50ff8-150">You’ve just finished configuring Jamf to deploy Microsoft Edge for macOS.</span></span> <span data-ttu-id="50ff8-151">当你定义的触发器条件为 true 时，程序包将部署到你指定的计算机。</span><span class="sxs-lookup"><span data-stu-id="50ff8-151">When the trigger condition you defined is true, the package will get deployed to the computers you specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="50ff8-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50ff8-152">See also</span></span>

- [<span data-ttu-id="50ff8-153">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="50ff8-153">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="50ff8-154">Jamf.com</span><span class="sxs-lookup"><span data-stu-id="50ff8-154">Jamf.com</span></span>](https://www.jamf.com/)
- [<span data-ttu-id="50ff8-155">将 Jamf 与 Microsoft Intune 集成</span><span class="sxs-lookup"><span data-stu-id="50ff8-155">Integrate Jamf with Microsoft Intune</span></span>](/intune/conditional-access-integrate-jamf)