---
title: 使用 Microsoft Intune 配置适用于 Windows 的 Microsoft Edge 策略设置
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/18/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 使用 Microsoft Intune 配置适用于 Windows 的 Microsoft Edge 策略设置。
ms.openlocfilehash: 6200b52e9061f37f85fe0bfe7cf59a2172db97df
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979238"
---
# <span data-ttu-id="7fb81-103">使用 Microsoft Intune 配置 Microsoft Edge 策略设置</span><span class="sxs-lookup"><span data-stu-id="7fb81-103">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>

<span data-ttu-id="7fb81-104">本文说明了如何使用 Microsoft Intune 配置适用于 Windows 10 的 Microsoft Edge 策略设置。</span><span class="sxs-lookup"><span data-stu-id="7fb81-104">This article explains how to configure Microsoft Edge policy settings for Windows 10 using Microsoft Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="7fb81-105">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7fb81-105">This article applies to Microsoft Edge version 77 or later.</span></span>

<span data-ttu-id="7fb81-106">你可以通过将设备配置文件添加到 Microsoft Intune 来配置 Microsoft Edge 策略和设置。</span><span class="sxs-lookup"><span data-stu-id="7fb81-106">You can configure Microsoft Edge policies and settings by adding a device configuration profile to Microsoft Intune.</span></span> <span data-ttu-id="7fb81-107">使用 Intune 管理和实施策略等同于在用户设备上使用 Active Directory 组策略或配置本地组策略对象 (GPO) 设置。</span><span class="sxs-lookup"><span data-stu-id="7fb81-107">Using Intune to manage and enforce policies is equivalent to using Active Directory Group Policy or configuring local Group Policy Object (GPO) settings on user devices.</span></span>

<span data-ttu-id="7fb81-108">有关使用 Microsoft Intune 管理 Microsoft Edge 策略的详细信息，可以阅读[通过将 Microsoft Edge 和 Microsoft Intune 配合使用来管理 Web 访问](https://docs.microsoft.com/intune/manage-microsoft-edge)，但是请记住，链接的文章特定于 Microsoft Edge 45 及更早版本，因此可能包含不适用于 Microsoft Edge Enterprise 77 及更高版本的信息和参考。</span><span class="sxs-lookup"><span data-stu-id="7fb81-108">For more information about managing Microsoft Edge policies with Microsoft Intune, you can read [Manage web access by using Microsoft Edge with Microsoft Intune](https://docs.microsoft.com/intune/manage-microsoft-edge), but keep in mind that the linked article is specific to Microsoft Edge version 45 and earlier and therefore may contain information and references that don't apply to Microsoft Edge Enterprise version 77 and later.</span></span>

> [!TIP]
> <span data-ttu-id="7fb81-109">有关如何使用 Microsoft Intune 配置 macOS 上的 Microsoft Edge 的信息，请参阅[为 macOS 配置](configure-microsoft-edge-on-mac.md)。</span><span class="sxs-lookup"><span data-stu-id="7fb81-109">For information on how to configure Microsoft Edge on macOS using Microsoft Intune, see [Configure for macOS](configure-microsoft-edge-on-mac.md).</span></span>

## <span data-ttu-id="7fb81-110">创建配置文件以管理适用于 Windows 10 的 Microsoft Edge 中的设置</span><span class="sxs-lookup"><span data-stu-id="7fb81-110">Create a profile to manage settings in Microsoft Edge for Windows 10</span></span>

<span data-ttu-id="7fb81-111">使用 Microsoft Intune 中的管理模板，你可以使用云管理 Windows 10 设备上的 Microsoft Edge 组策略。</span><span class="sxs-lookup"><span data-stu-id="7fb81-111">Using Administrative Templates in Microsoft Intune, you can manage Microsoft Edge group policies on your Windows 10 devices using the cloud.</span></span> <span data-ttu-id="7fb81-112">此部分将帮助你创建模板来配置 Microsoft Edge 特定的应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="7fb81-112">This section will help you create a template to configure Microsoft Edge-specific application settings.</span></span> <span data-ttu-id="7fb81-113">当你创建模板时，它将创建一个设备配置文件。</span><span class="sxs-lookup"><span data-stu-id="7fb81-113">When you create the template, it creates a device configuration profile.</span></span> <span data-ttu-id="7fb81-114">然后，你可以将此配置文件分配或部署到你的组织中的 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="7fb81-114">You can then assign or deploy this profile to Windows 10 devices in your organization.</span></span>

### <span data-ttu-id="7fb81-115">先决条件</span><span class="sxs-lookup"><span data-stu-id="7fb81-115">Prerequisites</span></span>

- <span data-ttu-id="7fb81-116">Windows 10 以及以下最低系统要求：</span><span class="sxs-lookup"><span data-stu-id="7fb81-116">Windows 10 with the following minimum system requirements:</span></span>
  - <span data-ttu-id="7fb81-117">Windows 10 版本 1909</span><span class="sxs-lookup"><span data-stu-id="7fb81-117">Windows 10, version 1909</span></span>
  - <span data-ttu-id="7fb81-118">Windows 10 版本 1903（已安装 [KB4512941](https://support.microsoft.com/kb/4512941)）</span><span class="sxs-lookup"><span data-stu-id="7fb81-118">Windows 10, version 1903 with [KB4512941](https://support.microsoft.com/kb/4512941) installed</span></span>
  - <span data-ttu-id="7fb81-119">Windows 10 版本 1809（已安装 [KB4512534](https://support.microsoft.com/kb/4512534)）</span><span class="sxs-lookup"><span data-stu-id="7fb81-119">Windows 10, version 1809 with [KB4512534](https://support.microsoft.com/kb/4512534) installed</span></span>
  - <span data-ttu-id="7fb81-120">Windows 10 版本 1803（已安装 [KB4512509](https://support.microsoft.com/kb/4512509)）</span><span class="sxs-lookup"><span data-stu-id="7fb81-120">Windows 10, version 1803 with [KB4512509](https://support.microsoft.com/kb/4512509) installed</span></span>
  - <span data-ttu-id="7fb81-121">Windows 10 版本 1709（已安装 [KB4516071](https://support.microsoft.com/kb/4516071)）</span><span class="sxs-lookup"><span data-stu-id="7fb81-121">Windows 10, version 1709 with [KB4516071](https://support.microsoft.com/kb/4516071) installed</span></span>

### <span data-ttu-id="7fb81-122">使用管理模板创建适用于 Microsoft Edge 的策略</span><span class="sxs-lookup"><span data-stu-id="7fb81-122">Use Administrative Templates to create a policy for Microsoft Edge</span></span>

<span data-ttu-id="7fb81-123">此过程利用 Intune 中内置的管理模板（你可能在组策略中见到过）。</span><span class="sxs-lookup"><span data-stu-id="7fb81-123">This procedure leverages Administrative templates (which you might be familiar with from Group Policy) that are built into Intune.</span></span> <span data-ttu-id="7fb81-124">可通过在预配置列表中选择“设置”，使用这些模板为 Microsoft Edge 创建策略。</span><span class="sxs-lookup"><span data-stu-id="7fb81-124">You can use these templates to create a policy for Microsoft Edge by selecting settings from a pre-configured list.</span></span>

1. <span data-ttu-id="7fb81-125">登录 [Microsoft Endpoint Manager ](https://endpoint.microsoft.com/)门户。</span><span class="sxs-lookup"><span data-stu-id="7fb81-125">Sign in to the [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) portal.</span></span>
2. <span data-ttu-id="7fb81-126">在左侧导航窗格中选择**设备**。</span><span class="sxs-lookup"><span data-stu-id="7fb81-126">Select **Devices** in the left-hand navigation pane.</span></span>
3. <span data-ttu-id="7fb81-127">从**设备** | **概述**中，选择 **配置文件**（在“策略”标题下）。</span><span class="sxs-lookup"><span data-stu-id="7fb81-127">From **Devices** | **Overview**, select **Configuration Profiles** (under Policy heading).</span></span>
4. <span data-ttu-id="7fb81-128">在顶部命令栏中，选择**创建配置文件**。</span><span class="sxs-lookup"><span data-stu-id="7fb81-128">On the top command bar, select **Create profile**.</span></span>
5. <span data-ttu-id="7fb81-129">在**平台**下方的下拉列表中，选择 **Windows 10 及更高版本**。</span><span class="sxs-lookup"><span data-stu-id="7fb81-129">In the drop-down list below **Platform**, select **Windows 10 and later**.</span></span>
6. <span data-ttu-id="7fb81-130">在**配置文件**下方的下拉列表中，选择**管理模板**然后单击**创建**按钮。</span><span class="sxs-lookup"><span data-stu-id="7fb81-130">In the drop-down list below **Profile**, select **Administrative Templates** and then click the **Create** button.</span></span> <span data-ttu-id="7fb81-131">下一个屏幕截图将显示下拉列表，以选择平台和配置文件类型。</span><span class="sxs-lookup"><span data-stu-id="7fb81-131">The next screenshot shows the drop-down lists to select the platform and type of profile.</span></span>

    ![选择平台和配置文件类型](./media/configure-edge-with-intune/create-profile-platform.png)

7. <span data-ttu-id="7fb81-133">在**基础知识**选项卡上，输入描述性**名称**，如 Microsoft Edge 策略。</span><span class="sxs-lookup"><span data-stu-id="7fb81-133">On the **Basics** tab, enter a descriptive **Name**, such as Microsoft Edge Policy.</span></span> <span data-ttu-id="7fb81-134">（可选）输入策略的 **描述**。</span><span class="sxs-lookup"><span data-stu-id="7fb81-134">Optionally, enter a  **Description** for the policy.</span></span>
<span data-ttu-id="7fb81-135">下一个屏幕截图将显示**基础知识**选项卡的窗体，并且菜单栏将显示后续步骤（灰显选项卡）以创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="7fb81-135">The next screenshot shows the form for the **Basics** tab and the menu bar shows the next steps (as grayed out tabs) to create the profile.</span></span>

   ![输入名称和描述](./media/configure-edge-with-intune/create-profile-basics-tab.png)

8. <span data-ttu-id="7fb81-137">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="7fb81-137">Select **Next**.</span></span>
9. <span data-ttu-id="7fb81-138">在**配置设置**选项卡上，选择以下任一位置中的 Microsoft Edge 文件夹：</span><span class="sxs-lookup"><span data-stu-id="7fb81-138">On the **Configuration settings** tab, select the Microsoft Edge folder in one of the following locations:</span></span>

   - <span data-ttu-id="7fb81-139">位于“计算机配置”文件夹下方</span><span class="sxs-lookup"><span data-stu-id="7fb81-139">below the Computer Configuration folder</span></span>
   - <span data-ttu-id="7fb81-140">位于“用户配置”文件夹下方。</span><span class="sxs-lookup"><span data-stu-id="7fb81-140">below the User Configuration folder.</span></span>

   <span data-ttu-id="7fb81-141">Microsoft Edge 的可用设置将显示在右窗格中。</span><span class="sxs-lookup"><span data-stu-id="7fb81-141">The available settings for Microsoft Edge will be shown on the right pane.</span></span> <span data-ttu-id="7fb81-142">例如，下面的屏幕截图中所示的*计算机配置/Microsoft Edge/允许下载限制*。</span><span class="sxs-lookup"><span data-stu-id="7fb81-142">For example, *Computer Configuration/Microsoft Edge/Allow download restrictions* shown in the following screenshot.</span></span>

   ![配置设置选项卡](./media/configure-edge-with-intune/create-profile-configuration-settings-tab.png)

   > [!NOTE]
   > <span data-ttu-id="7fb81-144">有关 Microsoft Edge 的所有可用设置的最完整和最新的列表，请参阅 [Microsoft Edge – 策略](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies)和 [Microsoft Edge – 更新策略](https://docs.microsoft.com/DeployEdge/microsoft-edge-update-policies)。</span><span class="sxs-lookup"><span data-stu-id="7fb81-144">See [Microsoft Edge – Policies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies) and [Microsoft Edge – Update policies](https://docs.microsoft.com/DeployEdge/microsoft-edge-update-policies) for the most complete and up to date list of all the available settings for Microsoft Edge.</span></span>

10. <span data-ttu-id="7fb81-145">使用搜索字段（“搜索以筛选项目 ...”）查找想要配置的特定设置。</span><span class="sxs-lookup"><span data-stu-id="7fb81-145">Use the search field ("Search to filter items ...") to find a specific setting you want to configure.</span></span> <span data-ttu-id="7fb81-146">在此示例中，搜索字符串是“主页”。</span><span class="sxs-lookup"><span data-stu-id="7fb81-146">In this example, the search string is "home page".</span></span> <span data-ttu-id="7fb81-147">下一个屏幕截图将显示搜索结果。</span><span class="sxs-lookup"><span data-stu-id="7fb81-147">The next screenshot shows the search results.</span></span>

    ![搜索结果](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-search.png)

11. <span data-ttu-id="7fb81-149">找到打算配置的设置后，选择它以公开可设置的值。</span><span class="sxs-lookup"><span data-stu-id="7fb81-149">After you find the setting you intend to configure, select it to expose the values you can set.</span></span> <span data-ttu-id="7fb81-150">在接下来的屏幕截图中，我们选择了“配置主页 URL”作为示例。</span><span class="sxs-lookup"><span data-stu-id="7fb81-150">In the next screenshot, we selected "Configure the home page URL" as an example.</span></span>

    ![配置主页 URL 策略](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-edit-pol.png)

12. <span data-ttu-id="7fb81-152">启用策略并为主页 URL 输入一个值，如前面的屏幕截图所示。</span><span class="sxs-lookup"><span data-stu-id="7fb81-152">Enable the policy and enter a value for the Home page URL, as shown in the previous screenshot.</span></span>

13. <span data-ttu-id="7fb81-153">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7fb81-153">Click **OK**.</span></span> <span data-ttu-id="7fb81-154">设置“状态”列应显示为“已启用”，如以下屏幕截图示例中所示。</span><span class="sxs-lookup"><span data-stu-id="7fb81-154">The settings "State" column should appear as "Enabled", as shown in the following screenshot example.</span></span>

    ![设置状态为已启用](./media/configure-edge-with-intune/create-profile-configuration-settings-tab-set-enabled.png)

14. <span data-ttu-id="7fb81-156">单击“下一步”\*\*\*\* 按钮。</span><span class="sxs-lookup"><span data-stu-id="7fb81-156">Click the **Next** button.</span></span>

15. <span data-ttu-id="7fb81-157">在**范围标记**选项卡上，根据需要添加范围标记，否则单击**下一步**按钮。</span><span class="sxs-lookup"><span data-stu-id="7fb81-157">On the **Scope tags** tab, add a Scope tag if wanted, otherwise click the **Next** button.</span></span>

16. <span data-ttu-id="7fb81-158">在**分配**选项卡上，单击 **+ 选择要包括的组**将此策略分配给包含要接收此策略设置的设备或用户的 Azure Active Directory (Azure AD) 组。</span><span class="sxs-lookup"><span data-stu-id="7fb81-158">On the **Assignments** tab, click **+ Select groups to include** to assign this policy to the Azure Active Directory (Azure AD) group that contains the devices or the users that you want to receive this policy setting.</span></span> <span data-ttu-id="7fb81-159">请参阅[在 Microsoft Intune 中分配用户和设备配置文件](https://docs.microsoft.com/intune/device-profile-assign)，以获取有关如何将配置文件分配给 Azure AD 用户或设备组的信息。</span><span class="sxs-lookup"><span data-stu-id="7fb81-159">See [Assign user and device profiles in Microsoft Intune](https://docs.microsoft.com/intune/device-profile-assign) for information about how to assign the profile to your Azure AD user or device groups.</span></span>

    ![选择要包含的组](./media/configure-edge-with-intune/create-profile-assignments-tab.png)

17. <span data-ttu-id="7fb81-161">单击“下一步”\*\*\*\* 按钮。</span><span class="sxs-lookup"><span data-stu-id="7fb81-161">Click the **Next** button.</span></span>

18. <span data-ttu-id="7fb81-162">在**审阅 + 创建**选项卡上，查看更改摘要以确保其正确，然后单击**创建**按钮。</span><span class="sxs-lookup"><span data-stu-id="7fb81-162">On the **Review + create** tab, review the summary of your changes to ensure it's correct and then click the **Create** button.</span></span>

19. <span data-ttu-id="7fb81-163">新创建的策略（Microsoft Edge 策略）显示在以下屏幕截图中。</span><span class="sxs-lookup"><span data-stu-id="7fb81-163">The newly created policy (Microsoft Edge Policy) is shown in the following screenshot.</span></span>

    ![选择要包含的组](./media/configure-edge-with-intune/create-profile-new-policy-finished.png)

<span data-ttu-id="7fb81-165">有关 Windows 10 配置文件的详细信息，请参阅[使用 Windows 10 模板在 Microsoft Intune 中配置组策略设置](https://docs.microsoft.com/intune/administrative-templates-windows)。</span><span class="sxs-lookup"><span data-stu-id="7fb81-165">For more information about Windows 10 profiles, see [Use Windows 10 templates to configure group policy settings in Microsoft Intune](https://docs.microsoft.com/intune/administrative-templates-windows).</span></span>

## <span data-ttu-id="7fb81-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7fb81-166">See also</span></span>

- [<span data-ttu-id="7fb81-167">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="7fb81-167">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="7fb81-168">通过将 Microsoft Edge 和 Microsoft Intune 配合使用来管理 Web 访问</span><span class="sxs-lookup"><span data-stu-id="7fb81-168">Manage web access by using Microsoft Edge with Microsoft Intune</span></span>](https://docs.microsoft.com/intune/manage-microsoft-edge)
- [<span data-ttu-id="7fb81-169">使用 Windows 10 模板在 Microsoft Intune 中配置组策略设置</span><span class="sxs-lookup"><span data-stu-id="7fb81-169">Use Windows 10 templates to configure group policy settings in Microsoft Intune</span></span>](https://docs.microsoft.com/intune/administrative-templates-windows)
- [<span data-ttu-id="7fb81-170">使用 Microsoft Intune 部署 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7fb81-170">Deploy Microsoft Edge using Microsoft Intune</span></span>](https://docs.microsoft.com/intune/apps/apps-windows-edge/?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json)
