---
title: 将 Microsoft Edge 设置为 Windows 和 macOS 上的默认浏览器
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 1/15/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解如何将 Microsoft Edge 设为默认浏览器
ms.openlocfilehash: c8cc45e0fe42dcbbd828dd81ae568f141cda2985
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979252"
---
# <span data-ttu-id="5e162-103">将 Microsoft Edge 设为默认浏览器</span><span class="sxs-lookup"><span data-stu-id="5e162-103">Set Microsoft Edge as the default browser</span></span>

<span data-ttu-id="5e162-104">本文介绍了如何将 Microsoft Edge 设置为 Windows 和 macOS 上的默认浏览器。</span><span class="sxs-lookup"><span data-stu-id="5e162-104">This article explains how you can set Microsoft Edge as the default browser on Windows and macOS.</span></span>

> [!NOTE]
> <span data-ttu-id="5e162-105">本文适用于 Windows 8 和 Windows 10 上的 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="5e162-105">This article applies to Microsoft Edge version 77 or later on Windows 8 and Windows 10.</span></span> <span data-ttu-id="5e162-106">对于 Windows 7 和 macOS，请查看[将 Microsoft Edge 设为默认浏览器](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultbrowsersettingenabled)策略。</span><span class="sxs-lookup"><span data-stu-id="5e162-106">For Windows 7 and macOS, see the [Set Microsoft Edge as default browser](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultbrowsersettingenabled) policy.</span></span>

## <span data-ttu-id="5e162-107">简介</span><span class="sxs-lookup"><span data-stu-id="5e162-107">Introduction</span></span>

<span data-ttu-id="5e162-108">你可以使用**设置默认关联配置文件**组策略或 [DefaultAssociationsConfiguration](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) 移动设备管理设置将 Microsoft Edge 设为组织的默认浏览器。</span><span class="sxs-lookup"><span data-stu-id="5e162-108">You can use the **Set a default associations configuration file** Group Policy or the [DefaultAssociationsConfiguration](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) Mobile Device Management setting to set Microsoft Edge as the default browser for your organization.</span></span>

<span data-ttu-id="5e162-109">要将 Microsoft Edge Stable 版设置为 html 文件、http/https 链接和 PDF 文件的默认浏览器，请使用以下应用程序关联文件示例：</span><span class="sxs-lookup"><span data-stu-id="5e162-109">To set Microsoft Edge Stable as the default browser for html files, http/https links, and PDF files use the following application association file example:</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<DefaultAssociations> 
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".html"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".htm"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="http"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="https"/>  
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgePDF" Identifier=".pdf"/>
</DefaultAssociations>
```

> [!NOTE]
> <span data-ttu-id="5e162-110">要将 Microsoft Edge Beta 设置为默认浏览器，请将 **ApplicationName** 设置为“Microsoft Edge Beta”，并将 **ProgId** 设置为“MSEdgeBHTML”。</span><span class="sxs-lookup"><span data-stu-id="5e162-110">To set Microsoft Edge Beta as the default browser, set **ApplicationName** to "Microsoft Edge Beta" and **ProgId** to "MSEdgeBHTML".</span></span> <span data-ttu-id="5e162-111">要将 Microsoft Edge Dev 设置为默认浏览器，请将 **ApplicationName** 设置为“Microsoft Edge Dev”，并将 **ProgId** 设置为“MSEdgeDHTML”。</span><span class="sxs-lookup"><span data-stu-id="5e162-111">To set Microsoft Edge Dev as the default browser, set **ApplicationName** to "Microsoft Edge Dev" and **ProgId** to "MSEdgeDHTML".</span></span>


> [!NOTE]
> <span data-ttu-id="5e162-112">如果 Microsoft Edge 未安装在目标设备上，则不会应用默认文件关联。</span><span class="sxs-lookup"><span data-stu-id="5e162-112">The default file associations aren't applied if Microsoft Edge isn't installed on the target device.</span></span> <span data-ttu-id="5e162-113">在此场景下，当用户打开某个链接或 htm/html 文件时，系统会提示他们选择其默认应用程序。</span><span class="sxs-lookup"><span data-stu-id="5e162-113">In this scenario, users are prompted to select their default application when they open a link or a htm/html file.</span></span>

## <span data-ttu-id="5e162-114">将 Microsoft Edge 设为加入域的设备上的默认浏览器</span><span class="sxs-lookup"><span data-stu-id="5e162-114">Set Microsoft Edge as the default browser on domain-joined devices</span></span>

<span data-ttu-id="5e162-115">你可以通过配置**设置默认关联配置文件**组策略，将 Microsoft Edge 设置为加入域的设备上的默认浏览器。</span><span class="sxs-lookup"><span data-stu-id="5e162-115">You can set Microsoft Edge as the default browser on domain-joined devices by configuring the **Set a default associations configuration file** group policy.</span></span> <span data-ttu-id="5e162-116">开启此组策略要求你创建和存储默认的关联配置文件。</span><span class="sxs-lookup"><span data-stu-id="5e162-116">Turning this group policy on requires you to create and store a default associations configuration file.</span></span> <span data-ttu-id="5e162-117">此文件存储在本地或网络共享上。</span><span class="sxs-lookup"><span data-stu-id="5e162-117">This file is stored locally or on a network share.</span></span> <span data-ttu-id="5e162-118">有关创建此文件的详细信息，请参阅[导出或导入默认应用程序关联](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations)。</span><span class="sxs-lookup"><span data-stu-id="5e162-118">For more information about creating this file, see [Export or Import Default Application Associations](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations).</span></span>

### <span data-ttu-id="5e162-119">若要为默认文件类型和协议关联配置文件配置组策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5e162-119">To configure the group policy for a default file type and protocol associations configuration file:</span></span>

1. <span data-ttu-id="5e162-120">打开组策略编辑器，然后转到**计算机配置\管理模板\Windows 组件\文件资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="5e162-120">Open the Group Policy editor and go to the **Computer Configuration\Administrative Templates\Windows Components\File Explorer**.</span></span>
2. <span data-ttu-id="5e162-121">选择**设置默认关联配置文件**。</span><span class="sxs-lookup"><span data-stu-id="5e162-121">Select **Set a default associations configuration file**.</span></span>
3. <span data-ttu-id="5e162-122">单击**策略设置**，然后单击**已启用**。</span><span class="sxs-lookup"><span data-stu-id="5e162-122">Click **policy setting**, and then click **Enabled**.</span></span>
4. <span data-ttu-id="5e162-123">在**选项:** 下，键入默认关联配置文件的位置。</span><span class="sxs-lookup"><span data-stu-id="5e162-123">Under **Options:**, type the location to your default associations configuration file.</span></span>
5. <span data-ttu-id="5e162-124">单击**确定**保存策略设置。</span><span class="sxs-lookup"><span data-stu-id="5e162-124">Click **OK** to save the policy settings.</span></span>

<span data-ttu-id="5e162-125">下一张屏幕截图中的示例显示了可从目标设备访问的网络共享上名为 *appassoc.xml* 的关联文件。</span><span class="sxs-lookup"><span data-stu-id="5e162-125">The example in the next screenshot shows an associations file named *appassoc.xml* on a network share that is accessible from the target device.</span></span>

   ![在组策略中启用文件关联](./media/edge-learnmore-make-edge-default-browser/edge-learnmore-app-associations.png)

   > [!NOTE]
   > <span data-ttu-id="5e162-127">如果启用了此设置，并且用户的设备已加入域，则在用户下次登录时会处理关联配置文件。</span><span class="sxs-lookup"><span data-stu-id="5e162-127">If this setting is enabled and the user's device is domain-joined, the associations configuration file is processed the next time the user signs on.</span></span>

## <span data-ttu-id="5e162-128">将 Microsoft Edge 设置为加入 Azure Active Directory 的设备上的默认浏览器</span><span class="sxs-lookup"><span data-stu-id="5e162-128">Set Microsoft Edge as the default browser on Azure Active Directory joined devices</span></span>

<span data-ttu-id="5e162-129">要将 Microsoft Edge 设置为加入 Azure Active Directory 的设备上的默认浏览器，请使用以下应用程序关联文件为例执行 [DefaultAssociationsConfiguration](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) 移动设备管理设置中的步骤。</span><span class="sxs-lookup"><span data-stu-id="5e162-129">To set Microsoft Edge as the default browser on Azure Active Directory joined devices follow the steps in the [DefaultAssociationsConfiguration](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration) Mobile Device Management setting using the following application association file as an example.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<DefaultAssociations>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".html"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier=".htm"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="http"/>
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgeHTM" Identifier="https"/>  
  <Association ApplicationName="Microsoft Edge" ProgId="MSEdgePDF" Identifier=".pdf"/>
</DefaultAssociations>
```

> [!NOTE]
> <span data-ttu-id="5e162-130">要将 Microsoft Edge Beta 设置为默认浏览器，请将 **ApplicationName** 设置为“Microsoft Edge Beta”，并将 **ProgId** 设置为“MSEdgeBHTML”。</span><span class="sxs-lookup"><span data-stu-id="5e162-130">To set Microsoft Edge Beta as the default browser, set **ApplicationName** to "Microsoft Edge Beta" and **ProgId** to "MSEdgeBHTML".</span></span> <span data-ttu-id="5e162-131">要将 Microsoft Edge Dev 设置为默认浏览器，请将 **ApplicationName** 设置为“Microsoft Edge Dev”，并将 **ProgId** 设置为“MSEdgeDHTML”。</span><span class="sxs-lookup"><span data-stu-id="5e162-131">To set Microsoft Edge Dev as the default browser, set **ApplicationName** to "Microsoft Edge Dev" and **ProgId** to "MSEdgeDHTML".</span></span>

## <span data-ttu-id="5e162-132">将 Microsoft Edge 设置为 macOS 上的默认浏览器</span><span class="sxs-lookup"><span data-stu-id="5e162-132">Set Microsoft Edge as the default browser on macOS</span></span>

<span data-ttu-id="5e162-133">尝试以编程方式在 macOS 上设置默认浏览器，会导致系统向最终用户显示一条提示。</span><span class="sxs-lookup"><span data-stu-id="5e162-133">Attempting to programmatically set the default browser on macOS causes a prompt to appear for the end user.</span></span> <span data-ttu-id="5e162-134">此提示是一项 macOS 安全功能，仅能通过 AppleScript 自动关闭。</span><span class="sxs-lookup"><span data-stu-id="5e162-134">This prompt is a macOS security feature that can only be automated away by using an AppleScript.</span></span>

<span data-ttu-id="5e162-135">由于此限制，将 Microsoft Edge 设置为 macOS 上的默认浏览器主要有两种方法。</span><span class="sxs-lookup"><span data-stu-id="5e162-135">Because of this limitation, there are two main methods for setting Microsoft Edge as the default browser on a macOS.</span></span> <span data-ttu-id="5e162-136">第一个选项是使用 macOS 的映像来刷写设备，其中 Microsoft Edge 已设置为默认浏览器。</span><span class="sxs-lookup"><span data-stu-id="5e162-136">The first option is to flash the device with an image of macOS where Microsoft Edge has already been set as the default browser.</span></span> <span data-ttu-id="5e162-137">另一个选项是使用 [将 Microsoft Edge 设置为默认浏览器](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultbrowsersettingenabled) 策略，这将提示用户将 Microsoft Edge 设置为默认浏览器。</span><span class="sxs-lookup"><span data-stu-id="5e162-137">The other option is to use the [Set Microsoft Edge as default browser](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultbrowsersettingenabled) policy, which prompts the user to set Microsoft Edge as the default browser.</span></span>

<span data-ttu-id="5e162-138">使用上述任一方法时，用户仍有可能更改默认浏览器。</span><span class="sxs-lookup"><span data-stu-id="5e162-138">When using either of these methods, it is still possible for a user to change the default browser.</span></span> <span data-ttu-id="5e162-139">这是因为出于安全原因，不能以编程方式阻止默认浏览器首选项。</span><span class="sxs-lookup"><span data-stu-id="5e162-139">This is because for security reasons, the default browser preference can’t be blocked programmatically.</span></span> <span data-ttu-id="5e162-140">出于此原因，我们建议你部署**将 Microsoft Edge 设置为默认浏览器** 策略，即使你创建的映像以 Microsoft Edge 为默认浏览器。</span><span class="sxs-lookup"><span data-stu-id="5e162-140">For this reason, we recommend that you deploy the **Set Microsoft Edge as default browser** policy even if you create an image with Microsoft Edge as the default browser.</span></span> <span data-ttu-id="5e162-141">如果设置了此策略，并且用户在下次打开 Microsoft Edge 时更改了默认浏览器 Microsoft Edge，系统会提示他们将其设置为默认浏览器。</span><span class="sxs-lookup"><span data-stu-id="5e162-141">If the policy is set and a user changes the default browser from Microsoft Edge the next time they open Microsoft Edge, they will be prompted to set it as the default.</span></span>

## <span data-ttu-id="5e162-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e162-142">See also</span></span>

- [<span data-ttu-id="5e162-143">规划 Microsoft Edge 部署</span><span class="sxs-lookup"><span data-stu-id="5e162-143">Plan your deployment of Microsoft Edge</span></span>](https://docs.microsoft.com/DeployEdge/deploy-edge-plan-deployment)
- [<span data-ttu-id="5e162-144">Microsoft Edge Enterprise 着陆页</span><span class="sxs-lookup"><span data-stu-id="5e162-144">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="5e162-145">将 Microsoft Edge 设置为默认浏览器（Windows 7 和 macOS）</span><span class="sxs-lookup"><span data-stu-id="5e162-145">Set Microsoft Edge as default browser (Windows 7 and macOS)</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultbrowsersettingenabled)
- [<span data-ttu-id="5e162-146">Windows 10 - 如何为 IT 专业人员配置文件关联？</span><span class="sxs-lookup"><span data-stu-id="5e162-146">Windows 10 – How to configure file associations for IT Pros?</span></span>](https://docs.microsoft.com/archive/blogs/windowsinternals/windows-10-how-to-configure-file-associations-for-it-pros)
- [<span data-ttu-id="5e162-147">导出或导入默认应用程序关联</span><span class="sxs-lookup"><span data-stu-id="5e162-147">Export or Import Default Application Associations</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations)
  - [<span data-ttu-id="5e162-148">DISM 概述</span><span class="sxs-lookup"><span data-stu-id="5e162-148">DISM Overview</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/what-is-dism)
  - [<span data-ttu-id="5e162-149">DISM - 部署映像服务和管理</span><span class="sxs-lookup"><span data-stu-id="5e162-149">DISM - Deployment Image Servicing and Management</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism---deployment-image-servicing-and-management-technical-reference-for-windows)
