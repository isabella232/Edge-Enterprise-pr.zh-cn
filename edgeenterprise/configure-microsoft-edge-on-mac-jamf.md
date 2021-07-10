---
title: 使用 Jamf 在 macOS 上配置 Microsoft Edge
ms.author: brianalt
author: dan-wesley
manager: laurawi
ms.date: 6/29/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 使用 Jamf 在 Mac 设备上配置 Microsoft Edge 策略设置
ms.openlocfilehash: 8556a5b1d0fc01feb67fc86cb016a9ed47061b55
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641628"
---
# <a name="configure-microsoft-edge-policy-settings-on-macos-with-jamf"></a><span data-ttu-id="5bbdb-103">使用 Jamf 在 macOS 上配置 Microsoft Edge 策略设置</span><span class="sxs-lookup"><span data-stu-id="5bbdb-103">Configure Microsoft Edge policy settings on macOS with Jamf</span></span>

<span data-ttu-id="5bbdb-104">本文介绍如何使用 Jamf Pro 10.19 上的 Microsoft Edge 策略清单文件在 macOS 上配置策略设置。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-104">This article describes how to configure policy settings on macOS using a Microsoft Edge policy manifest file on Jamf Pro 10.19.</span></span>

<span data-ttu-id="5bbdb-105">还可以使用属性列表 (.plist) 文件在 macOS 上配置 Microsoft Edge 策略设置。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-105">You can also configure Microsoft Edge policy settings on macOS by using a property list (.plist) file.</span></span> <span data-ttu-id="5bbdb-106">有关详细信息，请参阅[使用 .plist 针对 macOS 进行配置](configure-microsoft-edge-on-mac.md)</span><span class="sxs-lookup"><span data-stu-id="5bbdb-106">For more information, see [Configure for macOS using a .plist](configure-microsoft-edge-on-mac.md)</span></span>


## <a name="prerequisites"></a><span data-ttu-id="5bbdb-107">必备条件</span><span class="sxs-lookup"><span data-stu-id="5bbdb-107">Prerequisites</span></span>

<span data-ttu-id="5bbdb-108">需要以下软件：</span><span class="sxs-lookup"><span data-stu-id="5bbdb-108">The following software is required:</span></span>

- <span data-ttu-id="5bbdb-109">Microsoft Edge Stable 渠道 81</span><span class="sxs-lookup"><span data-stu-id="5bbdb-109">Microsoft Edge Stable channel 81</span></span>
- <span data-ttu-id="5bbdb-110">策略模板文件（版本 81.0.416.3）</span><span class="sxs-lookup"><span data-stu-id="5bbdb-110">Policy Templates file, version 81.0.416.3</span></span>
- <span data-ttu-id="5bbdb-111">Jamf Pro（版本 10.19）</span><span class="sxs-lookup"><span data-stu-id="5bbdb-111">Jamf Pro, Version 10.19</span></span>

## <a name="about-the-jamf-pro-application--custom-settings-menu"></a><span data-ttu-id="5bbdb-112">关于 Jamf Pro 的“应用程序和自定义设置”菜单</span><span class="sxs-lookup"><span data-stu-id="5bbdb-112">About the Jamf Pro Application & Custom Settings menu</span></span>

<span data-ttu-id="5bbdb-113">在 Jamf Pro 10.18 之前，管理 Office 365 涉及手动生成 .plist 文件。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-113">Before Jamf Pro 10.18, managing Office 365 involved manually building a .plist file.</span></span> <span data-ttu-id="5bbdb-114">这是一个耗时的工作流程，需要强大的技术背景。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-114">This was a time-consuming workflow that required a strong technical background.</span></span> <span data-ttu-id="5bbdb-115">Jamf Pro 10.18 通过简化配置过程消除了这些障碍。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-115">Jamf Pro 10.18 eliminated those barriers by streamlining the configuration process.</span></span> <span data-ttu-id="5bbdb-116">但是，IT 管理员只能将此新用户界面用于由 Jamf 指定的特定应用程序和首选项域。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-116">However, IT Admins could only use this new user interface for specific applications and preference domains specified by Jamf.</span></span>

<span data-ttu-id="5bbdb-117">在 Jamf Pro 10.19 中，用户可上传 JSON 清单作为“自定义架构”以用于任何首选项域，并将从此清单生成图形用户界面。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-117">In Jamf Pro 10.19, a user can upload a JSON manifest as a "custom schema" to target any preference domain, and the graphical user interface will be generated from this manifest.</span></span> <span data-ttu-id="5bbdb-118">创建的自定义架构遵循 JSON 架构规范。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-118">The custom schema that's created follows the JSON Schema specification.</span></span>

<span data-ttu-id="5bbdb-119">有关详细信息，请参阅《Jamf Pro 管理员指南》中的[计算机配置文件](https://jamf.it/computer-configuration-profiles)。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-119">For more information, see [Computer Configuration Profiles](https://jamf.it/computer-configuration-profiles) in the Jamf Pro Administrator's Guide.</span></span>

## <a name="get-the-policy-manifest-for-a-specific-version-of-microsoft-edge"></a><span data-ttu-id="5bbdb-120">获取特定 Microsoft Edge 版本的策略清单</span><span class="sxs-lookup"><span data-stu-id="5bbdb-120">Get the policy manifest for a specific version of Microsoft Edge</span></span>

<span data-ttu-id="5bbdb-121">若要获取策略清单，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5bbdb-121">To get the policy manifest:</span></span>

- <span data-ttu-id="5bbdb-122">转到 [Microsoft Edge Enterprise 登陆页面](https://aka.ms/EdgeEnterprise)。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-122">Go to the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise).</span></span>
- <span data-ttu-id="5bbdb-123">在 "通道/版本" 下拉列表中，选择 **版本81或更高版本的任何通道。**_.</span><span class="sxs-lookup"><span data-stu-id="5bbdb-123">On the Channel/Version dropdown list, select **any channel with version 81 or later.**_.</span></span>
- <span data-ttu-id="5bbdb-124">在 "生成" 下拉列表中，选择 "任何_ *81 生成" 或 "更高* \* _版本"。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-124">On the Build dropdown list, select any _*81 build or later.*\*_.</span></span>
- <span data-ttu-id="5bbdb-125">单击“获取策略文件”下载我们的策略模板捆绑包。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-125">Click GET POLICY FILES to download our policy templates bundle.</span></span>

  > [!NOTE]
  > <span data-ttu-id="5bbdb-126">目前，策略模板捆绑包签名为 CAB 文件。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-126">Currently, the policy templates bundle is signed as a CAB file.</span></span> <span data-ttu-id="5bbdb-127">需要在 macOS 上使用第三方工具（如 The Unarchiver）打开此文件。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-127">You'll need to use a 3rd party tool, such as The Unarchiver to open the file on macOS.</span></span>

<span data-ttu-id="5bbdb-128">解压缩 CAB 文件后，解压缩 ZIP 文件，然后导航到“mac”顶级目录。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-128">After you unpack the CAB file, unpack the ZIP file and navigate to the "mac" top level directory.</span></span> <span data-ttu-id="5bbdb-129">名为“policy_manifest.json”的清单位于此目录中。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-129">The manifest, which is named "policy_manifest.json", is in this directory.</span></span>

<span data-ttu-id="5bbdb-130">从内部版本 81.0.416.3 开始，在每个策略捆绑包中都会发布此清单。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-130">This manifest will be published in every policy bundle starting with build 81.0.416.3.</span></span> <span data-ttu-id="5bbdb-131">如果你想要在开发渠道中测试策略，可以获取与每个开发版本相关联的清单，并在 Jamf Pro 中对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-131">If you want to test policies in the Dev channel, you can take the manifest associated with each Dev release and test it in Jamf Pro.</span></span>  

## <a name="use-the-policy-manifest-in-jamf-pro"></a><span data-ttu-id="5bbdb-132">在 Jamf Pro 中使用策略清单</span><span class="sxs-lookup"><span data-stu-id="5bbdb-132">Use the policy manifest in Jamf Pro</span></span>

<span data-ttu-id="5bbdb-133">请按照以下步骤将策略清单上传到 Jamf Pro，然后为 macOS 创建策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-133">Use the following steps to upload the policy manifest to Jamf Pro and then create a policy profile for macOS.</span></span>

1. <span data-ttu-id="5bbdb-134">登录 Jamf。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-134">Sign in to Jamf.</span></span>
2. <span data-ttu-id="5bbdb-135">选择 "_\*计算机\*\*" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-135">Select the _*Computer*\* tab.</span></span>
3. <span data-ttu-id="5bbdb-136">在“**内容管理**”下，选择“**配置文件**”。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-136">Under **Content Management**, select **Configuration Profiles**.</span></span>
4. <span data-ttu-id="5bbdb-137">在“**配置文件**”页面上，单击“**+ 新建**”。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-137">On the **Configuration Profiles** page, click **+ New**.</span></span>

   ![在 Jamf 中添加新的配置文件](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles.png)

5. <span data-ttu-id="5bbdb-139">在“**新建 macOS 配置文件**”>“**选项**”中，选择“**应用程序和自定义设置**”。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-139">On **New macOS Configuration Profile**>**Options**, select **Application & Custom Settings**.</span></span>
6. <span data-ttu-id="5bbdb-140">在“**应用程序和自定义设置**”弹出窗口中，单击“**配置**”。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-140">On the **Application & Custom Settings** popup window, click **Configure**.</span></span>

   ![配置应用程序和自定义设置](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom.png)

7. <span data-ttu-id="5bbdb-142">在“**应用程序和自定义设置**”部分，设置以下屏幕截图中显示的值。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-142">In the **Application & Custom Settings** section, set the values shown in the following screen shot.</span></span>

   ![配置文件源和自定义架构](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-schema.png)

   - <span data-ttu-id="5bbdb-144">对于“**创建方法**”，选择“**配置设置**”。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-144">For **Creation Method**, pick **Configure settings**.</span></span>
   - <span data-ttu-id="5bbdb-145">对于“**源**”，选择“**自定义架构**”。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-145">For **Source**, pick **Custom Schema**.</span></span>
   - <span data-ttu-id="5bbdb-146">对于“**首选项域**”，提供你的域的名称。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-146">For **Preference Domain**, provide the name of your domain.</span></span> <span data-ttu-id="5bbdb-147">此示例使用 *com.microsoft.Edge* 作为域。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-147">This example uses *com.microsoft.Edge* as the domain.</span></span>
   - <span data-ttu-id="5bbdb-148">对于“**自定义架构**”，粘贴“policy_manifest.json”清单文件的内容。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-148">For **Custom Schema**, paste the contents of the "policy_manifest.json" manifest file.</span></span>
   - <span data-ttu-id="5bbdb-149">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-149">Click **Save**.</span></span>

8. <span data-ttu-id="5bbdb-150">保存配置文件后，Jamf 将显示下一个屏幕截图中所示的“**常规**”部分。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-150">After you save the profile, Jamf displays the **General** section shown in the next screen shot.</span></span>

   ![配置“常规”部分](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-app-and-custom-general-setting.png)

   - <span data-ttu-id="5bbdb-152">提供配置文件的显示“**名称**”和“**说明**”。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-152">Provide a display **Name** for the profile and a **Description**.</span></span>
   - <span data-ttu-id="5bbdb-153">保留“**类别**”的默认设置，即“**无**”。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-153">Keep the default setting for **Category**, which is **None**.</span></span>
   - <span data-ttu-id="5bbdb-154">对于“**分发方法**”，选项为“**自动安装**”或“**使其在自助服务中可用**”。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-154">For **Distribution Method**, the options are **Install Automatically** or **Make Available in Self Service**.</span></span>
   - <span data-ttu-id="5bbdb-155">对于“**级别**”，选项为“**用户级别**”或“**计算机级别**”。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-155">For **Level**, the options are **User Level** or **Computer Level**.</span></span>
   - <span data-ttu-id="5bbdb-156">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-156">Click **Save**.</span></span>

9. <span data-ttu-id="5bbdb-157">保存“常规”部分后，Jamf 将显示为我们的示例设置的“Microsoft Edge Beta 渠道”配置文件。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-157">After you save the General section, Jamf shows the "Microsoft Edge Beta Channel" configuration profile set up for our example.</span></span> <span data-ttu-id="5bbdb-158">在下一个屏幕截图中，请注意，可以单击“**编辑**”以继续处理配置文件；如果已完成，请单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-158">In the next screen shot, note that you can keep working the profile by clicking **Edit** or if you're finished, click **Done**.</span></span>

   ![包含选项的新配置文件](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel.png)

   > [!NOTE]
   > <span data-ttu-id="5bbdb-160">在保存此配置文件后，还可在其他 Jamf 会话中对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-160">You can edit this profile after it's been saved and in another Jamf session.</span></span> <span data-ttu-id="5bbdb-161">例如，你可能决定将“分发方法”更改为“使其在自助服务中可用”。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-161">For example, you might decide to change the Distribution Method to Make Available in Self Service.</span></span>

   <span data-ttu-id="5bbdb-162">若要在 Microsoft Edge Stable 渠道中执行配置文件的后续编辑或将其删除，请选择配置文件名称，如以下“配置文件”屏幕截图中所示。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-162">To do a follow up edit on the Microsoft Edge Stable Channel, or delete it, select the profile name, shown in the following Configuration Profiles screen shot.</span></span>

   ![“配置文件”列表](media/configure-microsoft-edge-on-mac-jamf/configure-macos-jamf-configuration-profiles-beta-channel-done.png)

<span data-ttu-id="5bbdb-164">创建新的配置文件后，仍需为配置文件配置“**范围**”。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-164">After you create the new configuration profile you still have to configure the **Scope** for the profile.</span></span>

### <a name="to-configure-the-scope"></a><span data-ttu-id="5bbdb-165">配置范围</span><span class="sxs-lookup"><span data-stu-id="5bbdb-165">To configure the scope</span></span>

1. <span data-ttu-id="5bbdb-166">对于“**目标**”，提供以下最低设置：</span><span class="sxs-lookup"><span data-stu-id="5bbdb-166">For **Targets**, provide the following minimum settings:</span></span>

   - <span data-ttu-id="5bbdb-167">面向计算机。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-167">TARGET COMPUTERS.</span></span> <span data-ttu-id="5bbdb-168">选项为“特定计算机”或“所有计算机”。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-168">The options are Specific Computers or All Computers.</span></span>
   - <span data-ttu-id="5bbdb-169">面向用户。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-169">TARGET USERS.</span></span> <span data-ttu-id="5bbdb-170">选项为“特定用户”或“所有用户”。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-170">The options are Specific Users or All Users.</span></span>
   - <span data-ttu-id="5bbdb-171">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-171">Click **Save**.</span></span>
2. <span data-ttu-id="5bbdb-172">对于“**限制**”，保留默认设置：“无”。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-172">For **Limitations**, keep the default setting: None.</span></span> <span data-ttu-id="5bbdb-173">单击“取消”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-173">Click **Cancel**.</span></span>
3. <span data-ttu-id="5bbdb-174">对于“**排除**”，保留默认设置：“无”。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-174">For **Exclusions**, keep the default setting: None.</span></span> <span data-ttu-id="5bbdb-175">单击“取消”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5bbdb-175">Click **Cancel**.</span></span>

## <a name="see-also"></a><span data-ttu-id="5bbdb-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5bbdb-176">See also</span></span>

- [<span data-ttu-id="5bbdb-177">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="5bbdb-177">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="5bbdb-178">使用 Intune 针对 macOS 进行配置</span><span class="sxs-lookup"><span data-stu-id="5bbdb-178">Configure for macOS with Intune</span></span>](configure-microsoft-edge-on-mac.md)
- [<span data-ttu-id="5bbdb-179">针对 Windows 进行配置</span><span class="sxs-lookup"><span data-stu-id="5bbdb-179">Configure for Windows</span></span>](configure-microsoft-edge.md)
- [<span data-ttu-id="5bbdb-180">使用 Intune 针对 Windows 进行配置</span><span class="sxs-lookup"><span data-stu-id="5bbdb-180">Configure for Windows with Intune</span></span>](configure-edge-with-intune.md)
