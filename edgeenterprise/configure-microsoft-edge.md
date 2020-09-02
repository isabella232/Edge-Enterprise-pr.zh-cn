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
# <span data-ttu-id="6d646-103">在 Windows 上配置 Microsoft Edge 策略设置</span><span class="sxs-lookup"><span data-stu-id="6d646-103">Configure Microsoft Edge policy settings on Windows</span></span>

<span data-ttu-id="6d646-104">使用以下信息在 Windows 设备上配置 Microsoft Edge 策略设置。</span><span class="sxs-lookup"><span data-stu-id="6d646-104">Use the following information to configure Microsoft Edge policy settings on your Windows devices.</span></span>

> [!NOTE]
> <span data-ttu-id="6d646-105">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="6d646-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="6d646-106">在 Windows 上配置策略设置</span><span class="sxs-lookup"><span data-stu-id="6d646-106">Configure policy settings on Windows</span></span>

<span data-ttu-id="6d646-107">你可以使用_组策略对象 (GPO)_ 在所有版本的 Windows 上配置 Microsoft Edge 和受托管 Microsoft Edge 更新的策略设置。</span><span class="sxs-lookup"><span data-stu-id="6d646-107">You can use _group policy objects (GPO)_ to configure policy settings for Microsoft Edge and managed Microsoft Edge updates on all versions of Windows.</span></span> <span data-ttu-id="6d646-108">你还可以通过注册表为已加入 Microsoft Active Directory 域的 Windows 设备或在 Microsoft Intune 中注册设备管理的 Windows 10 专业版或企业版实例预配策略。</span><span class="sxs-lookup"><span data-stu-id="6d646-108">You can also provision policy through the registry for Windows devices that are joined to a Microsoft Active Directory domain, or Windows 10 Pro or Enterprise instances enrolled for device management in Microsoft Intune.</span></span> <span data-ttu-id="6d646-109">若要使用组策略对象配置 Microsoft Edge，请安装_管理模板_，以便将 Microsoft Edge 的规则和设置添加到 Active Directory 域内的组策略中央存储中，或者单台计算机上的策略定义模板文件夹中，然后配置想要设置的特定策略。</span><span class="sxs-lookup"><span data-stu-id="6d646-109">To configure Microsoft Edge with group policy objects, you install _administrative templates_ that add rules and settings for Microsoft Edge to the group policy Central Store in your Active Directory domain or to the Policy Definition template folder on individual computers and then configure the specific policies you want to set.</span></span>

<span data-ttu-id="6d646-110">如果你想要在域级别管理策略，可以使用 Active Directory 组策略配置 Microsoft Edge 策略设置。</span><span class="sxs-lookup"><span data-stu-id="6d646-110">You can use Active Directory group policy to configure Microsoft Edge policy settings if you prefer to manage policy at the domain level.</span></span> <span data-ttu-id="6d646-111">这样，你可以全局管理策略设置，并将不同的策略设置定向到特定的 OU，或使用 WMI 过滤器仅将设置应用于特定查询返回的用户或计算机。</span><span class="sxs-lookup"><span data-stu-id="6d646-111">This enables you to manage policy settings globally, targeting different policy settings to specific OUs, or using WMI filters to apply settings only to users or computers returned by a particular query.</span></span> <span data-ttu-id="6d646-112">如果你想要在单台计算机上配置策略，可以使用目标计算机上的本地组策略编辑器应用仅影响本地设备的策略设置。</span><span class="sxs-lookup"><span data-stu-id="6d646-112">If you want to configure policy on individual computers, you can apply policy settings that only affect the local device using the Local Group Policy Editor on the target computer.</span></span>

<span data-ttu-id="6d646-113">Microsoft Edge 支持_强制_和_推荐的_策略。</span><span class="sxs-lookup"><span data-stu-id="6d646-113">Microsoft Edge supports both _mandatory_ and _recommended_ policies.</span></span> <span data-ttu-id="6d646-114">强制策略会覆盖用户首选项并阻止用户对其进行更改，而推荐的策略则提供可能会被用户覆盖的默认设置。</span><span class="sxs-lookup"><span data-stu-id="6d646-114">Mandatory policies override user preferences and prevents the user from changing it, while recommended policy provide a default setting that may be overridden by the user.</span></span> <span data-ttu-id="6d646-115">大多数策略都是纯强制性策略，部分是强制性和推荐的策略。</span><span class="sxs-lookup"><span data-stu-id="6d646-115">Most policies are mandatory only; a subset are mandatory and recommended.</span></span> <span data-ttu-id="6d646-116">如果设置了这两种策略，则强制性设置优先。</span><span class="sxs-lookup"><span data-stu-id="6d646-116">If both versions of a policy are set, the mandatory setting takes precedence.</span></span>

>[!TIP]
> <span data-ttu-id="6d646-117">你可以使用 Microsoft Intune 配置 Microsoft Edge 策略设置。</span><span class="sxs-lookup"><span data-stu-id="6d646-117">You can use Microsoft Intune to configure Microsoft Edge policy settings.</span></span> <span data-ttu-id="6d646-118">有关详细信息，请参阅[使用 Microsoft Intune 配置 Microsoft Edge](configure-edge-with-intune.md)。</span><span class="sxs-lookup"><span data-stu-id="6d646-118">For more information, see [Configure Microsoft Edge using Microsoft Intune](configure-edge-with-intune.md).</span></span>

<span data-ttu-id="6d646-119">有以下两个适用于 Microsoft Edge 的管理模板，这两个模板都可以在计算机或 Active Directory 域级别应用：</span><span class="sxs-lookup"><span data-stu-id="6d646-119">There are two administrative templates for Microsoft Edge, both of which can be applied either at the computer or Active Directory domain level:</span></span>

- <span data-ttu-id="6d646-120">*msedge.admx*，用于[配置 Microsoft Edge 设置](microsoft-edge-policies.md)</span><span class="sxs-lookup"><span data-stu-id="6d646-120">*msedge.admx* to [configure Microsoft Edge settings](microsoft-edge-policies.md)</span></span>
- <span data-ttu-id="6d646-121">*msedgeupdate.admx*，用于[管理 Microsoft Edge 更新](microsoft-edge-update-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6d646-121">*msedgeupdate.admx* to [manage Microsoft Edge updates](microsoft-edge-update-policies.md).</span></span>

<span data-ttu-id="6d646-122">首先，请下载并安装 Microsoft Edge 管理模板。</span><span class="sxs-lookup"><span data-stu-id="6d646-122">To get started, download and install the Microsoft Edge administrative template.</span></span>

### <span data-ttu-id="6d646-123">1. 下载并安装 Microsoft Edge 管理模板</span><span class="sxs-lookup"><span data-stu-id="6d646-123">1. Download and install the Microsoft Edge administrative template</span></span>

<span data-ttu-id="6d646-124">如果你想要在 Active Directory 中配置 Microsoft Edge 策略设置，请将文件下载到可从安装有远程服务器管理工具 (RSAT) 的域控制器或工作站中访问的网络位置。</span><span class="sxs-lookup"><span data-stu-id="6d646-124">If you want to configure Microsoft Edge policy settings in Active Directory, download the files to a network location you can access from a domain controller or a workstation with the Remote Server Administration Tools (RSAT) installed.</span></span> <span data-ttu-id="6d646-125">若要在单台计算机上进行配置，只需将文件下载到该计算机。</span><span class="sxs-lookup"><span data-stu-id="6d646-125">To configure on an individual computer, simply download the files to that computer.</span></span>

<span data-ttu-id="6d646-126">将管理模板文件添加到相应位置时，Microsoft Edge 策略设置将在组策略编辑器中立即可用。</span><span class="sxs-lookup"><span data-stu-id="6d646-126">When you add the administrative template files to the appropriate location, Microsoft Edge policy settings are immediately available in the Group Policy Editor.</span></span>

<span data-ttu-id="6d646-127">转到 [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)以下载 Microsoft Edge 策略模板文件 (*MicrosoftEdgePolicyTemplates.cab*)，然后提取内容。</span><span class="sxs-lookup"><span data-stu-id="6d646-127">Go to the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise) to download the Microsoft Edge policy templates file (*MicrosoftEdgePolicyTemplates.cab*) and extract the contents.</span></span>

#### <span data-ttu-id="6d646-128">将管理模板添加到 Active Directory 中</span><span class="sxs-lookup"><span data-stu-id="6d646-128">Add the administrative template to Active Directory</span></span>

1. <span data-ttu-id="6d646-129">在带有 RSAT 的域控制器或工作站上，浏览到适用于你的域的任何域控制器上的 **PolicyDefinition** 文件夹（也称为_中央存储_）。</span><span class="sxs-lookup"><span data-stu-id="6d646-129">On a domain controller or workstation with RSAT, browse to the **PolicyDefinition** folder (also known as the _Central Store_) on any domain controller for your domain.</span></span> <span data-ttu-id="6d646-130">对于较旧版本的 Windows Server，你可能需要创建 PolicyDefinition 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d646-130">For older versions of Windows Server, you may need to create the PolicyDefinition folder.</span></span> <span data-ttu-id="6d646-131">有关详细信息，请参阅[如何在 Windows 中为组策略管理模板创建和管理中央存储](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)。</span><span class="sxs-lookup"><span data-stu-id="6d646-131">For more information, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>
1. <span data-ttu-id="6d646-132">打开 *MicrosoftEdgePolicyTemplates*，然后转到**窗口** > **admx**。</span><span class="sxs-lookup"><span data-stu-id="6d646-132">Open *MicrosoftEdgePolicyTemplates* and go to **windows** > **admx**.</span></span>
1. <span data-ttu-id="6d646-133">将 *msedge.admx* 文件复制到 PolicyDefinition 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d646-133">Copy the *msedge.admx* file to the PolicyDefinition folder.</span></span> <span data-ttu-id="6d646-134">（示例：%systemroot%\sysvol\domain\policies\PolicyDefinitions）</span><span class="sxs-lookup"><span data-stu-id="6d646-134">(Example: %systemroot%\sysvol\domain\policies\PolicyDefinitions)</span></span>
1. <span data-ttu-id="6d646-135">在 *admx* 文件夹中，打开相应的语言文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d646-135">In the *admx* folder, open the appropriate language folder.</span></span> <span data-ttu-id="6d646-136">例如，如果你在美国，请打开 **en-US** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d646-136">For example, if you’re in the U.S., open the **en-US** folder.</span></span>
1. <span data-ttu-id="6d646-137">将 *msedge.adml* 文件复制到 PolicyDefinition 文件夹内匹配的语言文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6d646-137">Copy the *msedge.adml* file to the matching language folder in the PolicyDefinition folder.</span></span> <span data-ttu-id="6d646-138">如果此文件夹尚不存在，请创建它。</span><span class="sxs-lookup"><span data-stu-id="6d646-138">Create the folder if it does not already exist.</span></span> <span data-ttu-id="6d646-139">（示例：%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US）</span><span class="sxs-lookup"><span data-stu-id="6d646-139">(Example: %systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US)</span></span>
1. <span data-ttu-id="6d646-140">如果你的域有多个域控制器，则新 ADMX 文件将按下一个域复制间隔复制到这些域控制器。</span><span class="sxs-lookup"><span data-stu-id="6d646-140">If your domain has more than one domain controller, the new ADMX files will be replicated to them at the next domain replication interval.</span></span>
1. <span data-ttu-id="6d646-141">要确认是否正确加载了文件，请从 Windows 管理工具中打开**组策略管理编辑器**，然后展开**计算机配置** > **策略** > **管理模板** > **Microsoft Edge**。</span><span class="sxs-lookup"><span data-stu-id="6d646-141">To confirm the files loaded correctly, open the **Group Policy Management Editor** from Windows Administrative Tools and expand **Computer Configuration** > **Policies** > **Administrative Templates** > **Microsoft Edge**.</span></span> <span data-ttu-id="6d646-142">你应该会看到如下所示的一个或多个 Microsoft Edge 节点。</span><span class="sxs-lookup"><span data-stu-id="6d646-142">You should see one or more Microsoft Edge nodes as shown below.</span></span>

    ![Microsoft Edge 策略](./media/configure-microsoft-edge/edge-gpo-policies.png)

#### <span data-ttu-id="6d646-144">将管理模板添加到单台计算机中</span><span class="sxs-lookup"><span data-stu-id="6d646-144">Add the administrative template to an individual computer</span></span>

1. <span data-ttu-id="6d646-145">在目标计算机上，打开 *MicrosoftEdgePolicyTemplates*，然后转到**窗口** > **admx**。</span><span class="sxs-lookup"><span data-stu-id="6d646-145">On the target computer, open *MicrosoftEdgePolicyTemplates* and go to **windows** > **admx**.</span></span>
2. <span data-ttu-id="6d646-146">将 *msedge.admx* 文件复制到“策略定义”模板文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d646-146">Copy the *msedge.admx* file to your Policy Definition template folder.</span></span> <span data-ttu-id="6d646-147">（示例：C:\Windows\PolicyDefinitions）</span><span class="sxs-lookup"><span data-stu-id="6d646-147">(Example: C:\Windows\PolicyDefinitions)</span></span>
3. <span data-ttu-id="6d646-148">在 *admx* 文件夹中，打开相应的语言文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d646-148">In the *admx* folder, open the appropriate language folder.</span></span> <span data-ttu-id="6d646-149">例如，如果你在美国，请打开 **en-US** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d646-149">For example, if you’re in the U.S., open the **en-US** folder.</span></span>
4. <span data-ttu-id="6d646-150">将 *msedge.adml* 文件复制到“策略定义”文件夹内匹配的语言文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6d646-150">Copy the *msedge.adml* file to the matching language folder in your Policy Definition folder.</span></span> <span data-ttu-id="6d646-151">（示例：C:\Windows\PolicyDefinitions\en-US）</span><span class="sxs-lookup"><span data-stu-id="6d646-151">(Example: C:\Windows\PolicyDefinitions\en-US)</span></span>
5. <span data-ttu-id="6d646-152">要确认是否正确加载了文件，请直接打开本地组策略编辑器（Windows 键 + R，然后输入 gpedit.msc），或者打开 MMC，然后加载本地组策略编辑器管理单元。</span><span class="sxs-lookup"><span data-stu-id="6d646-152">To confirm the files loaded correctly either open Local Group Policy Editor directly (Windows key + R and enter gpedit.msc) or open MMC and load the Local Group Policy Editor snap-in.</span></span> <span data-ttu-id="6d646-153">如果发生错误，通常是因为文件的位置不正确。</span><span class="sxs-lookup"><span data-stu-id="6d646-153">If an error occurs, it’s usually because the files are in an incorrect location.</span></span>

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

### <span data-ttu-id="6d646-154">2. 设置强制性或推荐的策略</span><span class="sxs-lookup"><span data-stu-id="6d646-154">2. Set mandatory or recommended policies</span></span>

<span data-ttu-id="6d646-155">你可以设置强制性或推荐的策略，以针对 Active Directory 和单台计算机使用组策略编辑器配置 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="6d646-155">You can set mandatory or recommended policies to configure Microsoft Edge with the Group Policy Editor for both Active Directory and individual computers.</span></span> <span data-ttu-id="6d646-156">你可以选择适当的节点以将策略设置范围设置为**计算机配置**或**用户配置**，如下所述。</span><span class="sxs-lookup"><span data-stu-id="6d646-156">You can scope policy settings to either the **Computer Configuration** or **User Configuration** by selecting the appropriate node as described below.</span></span>

- <span data-ttu-id="6d646-157">要配置强制性策略，请打开组策略编辑器，然后转到（**计算机配置**或**用户配置**）> **策略** > **管理模板** > **Microsoft Edge**。</span><span class="sxs-lookup"><span data-stu-id="6d646-157">To configure a mandatory policy, open the Group Policy Editor and go to (**Computer Configuration** or **User Configuration**) > **Policies** > **Administrative Templates** > **Microsoft Edge**.</span></span>
- <span data-ttu-id="6d646-158">要配置推荐的策略，请打开组策略编辑器，然后转到（**计算机配置**或**用户配置**）> **策略** > **管理模板** > **Microsoft Edge - 默认设置（用户可以覆盖）**。</span><span class="sxs-lookup"><span data-stu-id="6d646-158">To configure a recommended policy, open the Group Policy Editor and go to (**Computer Configuration** or **User Configuration**) > **Policies** > **Administrative Templates** > **Microsoft Edge – Default Settings (users can override)**.</span></span>

  ![打开本地组策略编辑器](./media/configure-microsoft-edge/edge-ad-policy.png)

### <span data-ttu-id="6d646-160">3. 测试策略</span><span class="sxs-lookup"><span data-stu-id="6d646-160">3. Test your policies</span></span>

<span data-ttu-id="6d646-161">在目标客户端设备上，打开 Microsoft Edge，然后导航到 **edge://policy** 以查看应用的所有策略。</span><span class="sxs-lookup"><span data-stu-id="6d646-161">On a target client device, open Microsoft Edge and navigate to **edge://policy** to see all policies that are applied.</span></span> <span data-ttu-id="6d646-162">如果你在本地计算机上应用了策略设置，则策略应该会立即显示出来。</span><span class="sxs-lookup"><span data-stu-id="6d646-162">If you applied policy settings on the local computer, policies should appear immediately.</span></span> <span data-ttu-id="6d646-163">如果你正在配置策略设置，则可能需要关闭并重新打开 Microsoft Edge（如果它处于打开状态）。</span><span class="sxs-lookup"><span data-stu-id="6d646-163">You may need to close and reopen Microsoft Edge if it was open while you were configuring policy settings.</span></span>

![在浏览器中查看配置的策略](./media/configure-microsoft-edge/edge-gpEdit.png)

<span data-ttu-id="6d646-165">对于 Active Directory 组策略设置，策略设置将按域管理员定义的定期时间间隔传播到域计算机，并且目标计算机可能无法立即收到策略更新。</span><span class="sxs-lookup"><span data-stu-id="6d646-165">For Active Directory group policy settings, policy settings are propagated to domain computers at a regular interval defined by your domain administrator, and target computers may not receive policy updates right away.</span></span> <span data-ttu-id="6d646-166">若要在目标计算机上手动刷新 Active Directory 组策略设置，请在目标计算机上通过命令提示符或 PowerShell 会话执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="6d646-166">To manually refresh Active Directory group policy settings on a target computer, execute the following command from a command prompt or PowerShell session on the target computer:</span></span>

``` powershell
gpupdate /force
```

<span data-ttu-id="6d646-167">你可能需要关闭并重新打开 Microsoft Edge，然后才会显示新策略。</span><span class="sxs-lookup"><span data-stu-id="6d646-167">You may need to close and reopen Microsoft Edge before the new policies appear.</span></span>

<span data-ttu-id="6d646-168">你还可以在目标计算机上使用 REGEDIT.exe 来查看存储组策略设置的注册表设置。</span><span class="sxs-lookup"><span data-stu-id="6d646-168">You can also use REGEDIT.exe on a target computer to view the registry settings that store group policy settings.</span></span> <span data-ttu-id="6d646-169">这些设置位于注册表路径 **HKLM\SOFTWARE\Policies\Microsoft\Edge** 中。</span><span class="sxs-lookup"><span data-stu-id="6d646-169">These settings are located at the registry path **HKLM\SOFTWARE\Policies\Microsoft\Edge**.</span></span>

## <span data-ttu-id="6d646-170">常见问题</span><span class="sxs-lookup"><span data-stu-id="6d646-170">Frequently Asked Questions</span></span>

### <span data-ttu-id="6d646-171">Microsoft Edge 可以配置为使用主首选项吗？</span><span class="sxs-lookup"><span data-stu-id="6d646-171">Can Microsoft Edge be configured to use master preferences?</span></span>

<span data-ttu-id="6d646-172">可以，你可以将 Microsoft Edge 配置为使用主首选项文件。</span><span class="sxs-lookup"><span data-stu-id="6d646-172">Yes, you can configure Microsoft Edge to use a master preferences file.</span></span>

 <span data-ttu-id="6d646-173">主首选项文件允许你在部署 Microsoft Edge 时配置默认设置。</span><span class="sxs-lookup"><span data-stu-id="6d646-173">A master preferences file lets you configure default settings when Microsoft Edge is deployed.</span></span> <span data-ttu-id="6d646-174">你还可以使用主首选项文件在未由设备管理系统管理的计算机上应用设置。</span><span class="sxs-lookup"><span data-stu-id="6d646-174">You can also use a master preferences file to apply settings on computers that aren't managed by a device management system.</span></span> <span data-ttu-id="6d646-175">当用户首次运行浏览器时，这些设置将应用于用户的配置文件。</span><span class="sxs-lookup"><span data-stu-id="6d646-175">These settings are applied to the user’s profile the first time the user runs the browser.</span></span> <span data-ttu-id="6d646-176">在用户运行浏览器后，不会应用对主首选项文件所做的更改。</span><span class="sxs-lookup"><span data-stu-id="6d646-176">After the user runs the browser, changes to the master preferences file aren’t applied.</span></span> <span data-ttu-id="6d646-177">用户可以在浏览器中更改主首选项的设置。</span><span class="sxs-lookup"><span data-stu-id="6d646-177">A user can change settings from the master preferences in the browser.</span></span> <span data-ttu-id="6d646-178">如果你想要在首次运行浏览器后将设置设为强制性设置或更改设置，则必须使用策略。</span><span class="sxs-lookup"><span data-stu-id="6d646-178">If you want to make a setting mandatory or change a setting after the first run of the browser, you must use a policy.</span></span>

<span data-ttu-id="6d646-179">主首选项文件允许你为浏览器自定义许多不同的设置和首选项，包括与其他基于 Chromium 的浏览器共享以及特定于 Microsoft Edge 的那些设置和首选项。</span><span class="sxs-lookup"><span data-stu-id="6d646-179">A master preferences file lets you to customize many different settings and preferences for the browser, including those shared with other Chromium based browsers and specific to Microsoft Edge.</span></span>  <span data-ttu-id="6d646-180">与策略相关的首选项可使用主首选项文件进行配置。</span><span class="sxs-lookup"><span data-stu-id="6d646-180">Policy related preferences can be configured using the master preferences file.</span></span> <span data-ttu-id="6d646-181">如果设置了策略，并且有相应的主首选项集，则该策略设置优先。</span><span class="sxs-lookup"><span data-stu-id="6d646-181">In cases where a policy is set and there’s a corresponding master preference set, the policy setting takes precedence.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d646-182">所有可用的首选项可能与 Microsoft Edge 术语和命名约定不一致。</span><span class="sxs-lookup"><span data-stu-id="6d646-182">All the available preferences might not be consistent with Microsoft Edge terminology and naming conventions.</span></span>  <span data-ttu-id="6d646-183">不能保证这些首选项将继续在将来的版本中按预期方式运行。</span><span class="sxs-lookup"><span data-stu-id="6d646-183">There’s no guarantee that these preferences will continue to work as expected in future releases.</span></span> <span data-ttu-id="6d646-184">在更高版本中，首选项可能会发生更改或被忽略。</span><span class="sxs-lookup"><span data-stu-id="6d646-184">Preferences might be changed or ignored in later versions.</span></span>

<span data-ttu-id="6d646-185">主首选项文件是使用 JSON 标记进行格式设置的文本文件。</span><span class="sxs-lookup"><span data-stu-id="6d646-185">A master preferences file is a text file that’s formatted using JSON markup.</span></span> <span data-ttu-id="6d646-186">需要将此文件添加到 msedge.exe 可执行文件所在的相同目录中。</span><span class="sxs-lookup"><span data-stu-id="6d646-186">This file needs to be added to the same directory as the msedge.exe executable.</span></span> <span data-ttu-id="6d646-187">对于 Windows 上的系统范围内的企业部署，此目录通常为：*Windows：C:\Program Files\Microsoft\Edge\Application\master_preferences*。</span><span class="sxs-lookup"><span data-stu-id="6d646-187">For system wide enterprise deployments on Windows this is typically: *Windows: C:\Program Files\Microsoft\Edge\Application\master_preferences*.</span></span>

## <span data-ttu-id="6d646-188">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d646-188">See also</span></span>

- [<span data-ttu-id="6d646-189">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="6d646-189">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="6d646-190">使用 Intune 为 Windows 配置</span><span class="sxs-lookup"><span data-stu-id="6d646-190">Configure for Windows with Intune</span></span>](configure-edge-with-intune.md)
- [<span data-ttu-id="6d646-191">为 macOS 配置</span><span class="sxs-lookup"><span data-stu-id="6d646-191">Configure for macOS</span></span>](configure-microsoft-edge-on-mac.md)
- [<span data-ttu-id="6d646-192">浏览 Microsoft Edge 企业策略</span><span class="sxs-lookup"><span data-stu-id="6d646-192">Browse Microsoft Edge Enterprise Policies</span></span>](microsoft-edge-policies.md)


