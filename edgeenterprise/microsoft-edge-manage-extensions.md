---
title: 在企业中管理 Microsoft Edge 扩展
ms.author: aspoddar
author: AndreaLBarr
manager: balajek
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 在企业中管理 Microsoft Edge 扩展
ms.openlocfilehash: 26134a8c352354c0c447518120f3d79332100c80
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642918"
---
# <a name="manage-microsoft-edge-extensions-in-the-enterprise"></a><span data-ttu-id="ce709-103">在企业中管理 Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="ce709-103">Manage Microsoft Edge extensions in the enterprise</span></span>

<span data-ttu-id="ce709-104">本文为在其组织中管理 Microsoft Edge 扩展的管理员提供最佳做法指南。</span><span class="sxs-lookup"><span data-stu-id="ce709-104">This article provides best practice guidance for admins who are managing Microsoft Edge extensions in their organizations.</span></span> <span data-ttu-id="ce709-105">可以使用本文中的信息来制定管理组织中扩展的策略。</span><span class="sxs-lookup"><span data-stu-id="ce709-105">You can use the information in this article to develop a strategy for managing extensions in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="ce709-106">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="ce709-106">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="introduction"></a><span data-ttu-id="ce709-107">简介</span><span class="sxs-lookup"><span data-stu-id="ce709-107">Introduction</span></span>

<span data-ttu-id="ce709-108">组织希望保护公司和用户数据并评估浏览器扩展，以确保其安全且与企业相关。</span><span class="sxs-lookup"><span data-stu-id="ce709-108">Organizations want to protect corporate and user data and evaluate browser extensions to ensure that they’re safe and relevant to their enterprise.</span></span> <span data-ttu-id="ce709-109">管理员希望:</span><span class="sxs-lookup"><span data-stu-id="ce709-109">Admins want to:</span></span>

- <span data-ttu-id="ce709-110">防止安装错误的应用和扩展。</span><span class="sxs-lookup"><span data-stu-id="ce709-110">Prevent bad apps and extensions from being installed.</span></span>
- <span data-ttu-id="ce709-111">保留用户完成其工作所需的扩展。</span><span class="sxs-lookup"><span data-stu-id="ce709-111">Keep extensions that users need to do their job.</span></span>
- <span data-ttu-id="ce709-112">管理对用户和公司数据的访问。</span><span class="sxs-lookup"><span data-stu-id="ce709-112">Manage access to user and company data.</span></span>  

<span data-ttu-id="ce709-113">本文是系列文章中的第一篇，可帮助管理员管理扩展，为用户提供安全高效的体验。</span><span class="sxs-lookup"><span data-stu-id="ce709-113">This article is the first in a series that that helps admins manage extensions to provide a safe and productive experience for their users.</span></span> <span data-ttu-id="ce709-114">本系列介绍不同的选项，并帮助你选择管理扩展的最佳方法。</span><span class="sxs-lookup"><span data-stu-id="ce709-114">This series walks through the different options and helps you pick the best method for managing extensions.</span></span> <span data-ttu-id="ce709-115">本系列由以下文章组成：</span><span class="sxs-lookup"><span data-stu-id="ce709-115">The series consists of the following articles:</span></span>

- <span data-ttu-id="ce709-116">[在企业中管理的 Microsoft Edge 扩展](microsoft-edge-manage-extensions.md)。</span><span class="sxs-lookup"><span data-stu-id="ce709-116">[Manage Microsoft Edge extensions in the enterprise](microsoft-edge-manage-extensions.md).</span></span> <span data-ttu-id="ce709-117">创建管理扩展的策略，并设置管理浏览器所需的管理模板。</span><span class="sxs-lookup"><span data-stu-id="ce709-117">Create a strategy to manage extensions and set up administrative templates required for managing the browser.</span></span>
- <span data-ttu-id="ce709-118">[使用组策略管理 Microsoft Edge 扩展](microsoft-edge-manage-extensions-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ce709-118">[Use group policies to manage Microsoft Edge extensions](microsoft-edge-manage-extensions-policies.md).</span></span> <span data-ttu-id="ce709-119">使用组策略管理扩展的选项。</span><span class="sxs-lookup"><span data-stu-id="ce709-119">Options using group policies to manage extensions.</span></span>
- <span data-ttu-id="ce709-120">[创建用于托管 Microsoft Edge 扩展的 Web 应用商店](microsoft-edge-manage-extensions-webstore.md)。</span><span class="sxs-lookup"><span data-stu-id="ce709-120">[Create a web store to host Microsoft Edge extensions](microsoft-edge-manage-extensions-webstore.md).</span></span> <span data-ttu-id="ce709-121">创建和托管扩展。</span><span class="sxs-lookup"><span data-stu-id="ce709-121">Create and host extensions.</span></span>
- <span data-ttu-id="ce709-122">[Microsoft Edge 扩展的常见问题解答](microsoft-edge-manage-extensions-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="ce709-122">[FAQ for Microsoft Edge Extensions](microsoft-edge-manage-extensions-faq.md).</span></span> <span data-ttu-id="ce709-123">常见问题。</span><span class="sxs-lookup"><span data-stu-id="ce709-123">Frequently Asked Questions.</span></span>

## <a name="things-to-consider-when-managing-extensions"></a><span data-ttu-id="ce709-124">管理扩展时需考虑的事项</span><span class="sxs-lookup"><span data-stu-id="ce709-124">Things to consider when managing extensions</span></span>

<span data-ttu-id="ce709-125">用户需要访问某些应用、网站和扩展以完成其工作，同时还需保护用户和公司数据。</span><span class="sxs-lookup"><span data-stu-id="ce709-125">Your users need access to certain apps, sites, and extensions to do their jobs while at the same time protecting users and company data.</span></span> <span data-ttu-id="ce709-126">有效的安全策略包括为企业提出正确的问题，以及扩展如何满足公司的需求。</span><span class="sxs-lookup"><span data-stu-id="ce709-126">An effective security strategy involves asking the right questions for your enterprise and how extensions can fit your company’s needs.</span></span> <span data-ttu-id="ce709-127">要提出的一些关键问题包括：</span><span class="sxs-lookup"><span data-stu-id="ce709-127">Some of the key questions to ask are:</span></span>

- <span data-ttu-id="ce709-128">我需要遵守哪些法规和合规性措施？</span><span class="sxs-lookup"><span data-stu-id="ce709-128">What regulations and compliance measures do I need to adhere to?</span></span>
- <span data-ttu-id="ce709-129">某些扩展是否要求具有过于广泛的权限，这可能会违反我公司的数据安全策略？</span><span class="sxs-lookup"><span data-stu-id="ce709-129">Do some extensions ask for overly broad permissions, which could go against my company’s data security policies?</span></span>
- <span data-ttu-id="ce709-130">我的用户设备上存储了多少用户或公司数据？</span><span class="sxs-lookup"><span data-stu-id="ce709-130">How much user or corporate data is stored on my users’ devices?</span></span>

<span data-ttu-id="ce709-131">回答这些问题时，可以使用 Microsoft Edge 提供的粒度策略：</span><span class="sxs-lookup"><span data-stu-id="ce709-131">As you answer these questions, you can use the granular policies that Microsoft Edge provides to:</span></span>

- <span data-ttu-id="ce709-132">根据数据保护策略在用户的计算机上阻止或允许扩展。</span><span class="sxs-lookup"><span data-stu-id="ce709-132">Block or allow extensions on users’ computers based on your data protection policies.</span></span>
- <span data-ttu-id="ce709-133">在用户的设备上强制安装扩展，以便他们拥有提高工作效率所需的工具。</span><span class="sxs-lookup"><span data-stu-id="ce709-133">Force-install extensions on your users' devices so they have tools that they need to be productive.</span></span>
- <span data-ttu-id="ce709-134">“允许列表”或“阻止列表”扩展，以允许用户拥有其工作所需的最少权限。</span><span class="sxs-lookup"><span data-stu-id="ce709-134">Allowlist or blocklist extensions to allow the least amount of rights needed for your users to do their  work.</span></span>

<span data-ttu-id="ce709-135">传统的扩展管理模式对特定扩展使用“允许列表”和“阻止列表”的方法。</span><span class="sxs-lookup"><span data-stu-id="ce709-135">The traditional model for managing extensions uses the allowlist and blocklist approach for specific extensions.</span></span> <span data-ttu-id="ce709-136">然而，Microsoft Edge 也让你管理扩展程序所要求的权限。</span><span class="sxs-lookup"><span data-stu-id="ce709-136">However, Microsoft Edge also lets you manage the permissions requested by extensions.</span></span> <span data-ttu-id="ce709-137">使用此模型，可以决定要允许扩展在计算机和设备上使用哪些权限，然后实施全局策略，根据要求允许或阻止扩展。</span><span class="sxs-lookup"><span data-stu-id="ce709-137">Using this model, you can decide which rights and permissions you want to allow extensions to use on your computers and devices, and then implement a global policy that allows or block extensions based on your requirements.</span></span>  

## <a name="understand-extension-permissions"></a><span data-ttu-id="ce709-138">了解扩展权限</span><span class="sxs-lookup"><span data-stu-id="ce709-138">Understand extension permissions</span></span>

<span data-ttu-id="ce709-139">扩展可能需要拥有在设备或网页上进行更改的权限才能才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="ce709-139">Extensions can require rights to make changes on a device or a web page to run properly.</span></span> <span data-ttu-id="ce709-140">这些权利称为权限。</span><span class="sxs-lookup"><span data-stu-id="ce709-140">These rights are called permissions.</span></span> <span data-ttu-id="ce709-141">开发人员必须列出其扩展所需的权限和访问权限。</span><span class="sxs-lookup"><span data-stu-id="ce709-141">Developers must list what rights and access their extensions need.</span></span> <span data-ttu-id="ce709-142">权限有两个主要类别，许多扩展需要以下两种权限：</span><span class="sxs-lookup"><span data-stu-id="ce709-142">There are two main categories for permissions, and many extensions need both of the following permissions:</span></span>

- <span data-ttu-id="ce709-143">主机权限要求扩展列出它可能查看或修改的网页。</span><span class="sxs-lookup"><span data-stu-id="ce709-143">Host permissions require the extension to list webpages it may view or modify.</span></span>
- <span data-ttu-id="ce709-144">设备权限是扩展在其运行的设备上所需的权利。</span><span class="sxs-lookup"><span data-stu-id="ce709-144">Device permissions are the rights needed by an extension on the device where it’s running.</span></span>

<span data-ttu-id="ce709-145">这些权限的一些示例包括：访问 USB 端口、存储或查看屏幕，以及与本机程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="ce709-145">Some examples of these permissions are: access to a USB port, storage or viewing screen, and communicating with native programs.</span></span>  

## <a name="get-ready-to-manage-extensions"></a><span data-ttu-id="ce709-146">准备好管理扩展</span><span class="sxs-lookup"><span data-stu-id="ce709-146">Get ready to manage extensions</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ce709-147">在开始之前</span><span class="sxs-lookup"><span data-stu-id="ce709-147">Before you begin</span></span>

<span data-ttu-id="ce709-148">扩展选项假定已为用户管理 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="ce709-148">The extensions options assume that you already have Microsoft Edge managed for your users.</span></span> <span data-ttu-id="ce709-149">关于为 Microsoft Edge 策略设置管理模板的更多信息，请参阅:</span><span class="sxs-lookup"><span data-stu-id="ce709-149">For more information about setting up administrative templates for Microsoft Edge policies, see:</span></span>

-   [<span data-ttu-id="ce709-150">在 Windows 上配置 Microsoft Edge 策略设置</span><span class="sxs-lookup"><span data-stu-id="ce709-150">Configure Microsoft Edge policy settings on Windows</span></span>](/DeployEdge/configure-microsoft-edge)
-   [<span data-ttu-id="ce709-151">使用 Intune 为 Windows 配置</span><span class="sxs-lookup"><span data-stu-id="ce709-151">Configure for Windows with Intune</span></span>](/mem/intune/configuration/administrative-templates-configure-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)
-   [<span data-ttu-id="ce709-152">使用移动设备管理为 Windows 配置</span><span class="sxs-lookup"><span data-stu-id="ce709-152">Configure for Windows with Mobile Device Management</span></span>](/deployedge/configure-edge-with-mdm)
-   [<span data-ttu-id="ce709-153">使用 .plist 为 macOS 配置</span><span class="sxs-lookup"><span data-stu-id="ce709-153">Configure for macOS using a .plist</span></span>](/deployedge/configure-microsoft-edge-on-mac)
-   [<span data-ttu-id="ce709-154">使用 Jamf 为 macOS 配置</span><span class="sxs-lookup"><span data-stu-id="ce709-154">Configure for macOS with Jamf</span></span>](/deployedge/configure-microsoft-edge-on-mac-jamf)

<span data-ttu-id="ce709-155">本文中的配置步骤是适用于 Windows，关于 MAC/Linux 中的相应实现，请参阅 Microsoft Edge 浏览器策略参考。</span><span class="sxs-lookup"><span data-stu-id="ce709-155">The configuration steps in this article are for Windows, for the corresponding implementation in MAC/Linux, see the Microsoft Edge browser policy reference.</span></span>

## <a name="decide-which-extensions-to-allow"></a><span data-ttu-id="ce709-156">确定允许哪些扩展</span><span class="sxs-lookup"><span data-stu-id="ce709-156">Decide which extensions to allow</span></span>

<span data-ttu-id="ce709-157">大多数组织应按其权限以及其可访问的网站来管理扩展。</span><span class="sxs-lookup"><span data-stu-id="ce709-157">Most organizations should manage extensions by their permissions and what websites they have access to.</span></span> <span data-ttu-id="ce709-158">此方法更安全、更易于管理，并且对于大型组织是可缩放的。</span><span class="sxs-lookup"><span data-stu-id="ce709-158">This method is more secure, easier to manage, and is scalable for large organizations.</span></span>  

- <span data-ttu-id="ce709-159">阻止/允许的权限 – 允许按其所需的权限来控制扩展。</span><span class="sxs-lookup"><span data-stu-id="ce709-159">Blocked/allowed permissions – Lets you control extensions by the permissions they need.</span></span>
- <span data-ttu-id="ce709-160">运行时块主机 – 允许控制这些扩展可访问的网站。</span><span class="sxs-lookup"><span data-stu-id="ce709-160">Runtime block hosts – Lets you to control what websites these extensions can access.</span></span>

<span data-ttu-id="ce709-161">使用此方法可以节省时间，因为只需设置一次。</span><span class="sxs-lookup"><span data-stu-id="ce709-161">Using this approach saves time because you only need to set these once.</span></span> <span data-ttu-id="ce709-162">使用运行时主机策略，最重要的站点将受到保护。还有其他选项，例如：</span><span class="sxs-lookup"><span data-stu-id="ce709-162">And with the run-time hosts policy, your most important sites will be protected.There are other options as well such as:</span></span>

-   <span data-ttu-id="ce709-163">强制安装扩展 - 允许以无提示方式安装扩展。</span><span class="sxs-lookup"><span data-stu-id="ce709-163">Force install extensions – Lets you install extensions silently.</span></span>
-   <span data-ttu-id="ce709-164">“允许列表/阻止列表”（如果需要）– 确定允许安装哪些扩展。</span><span class="sxs-lookup"><span data-stu-id="ce709-164">Allowlist/blocklist (if required) – Decide what extensions are allowed to be installed.</span></span>

<span data-ttu-id="ce709-165">使用以下步骤作为指南来确定在组织中允许哪些扩展。</span><span class="sxs-lookup"><span data-stu-id="ce709-165">Use the following steps as a guide to decide which extensions to allow in your organization.</span></span>

1. <span data-ttu-id="ce709-166">创建员工在其计算机上需要哪些扩展的列表。</span><span class="sxs-lookup"><span data-stu-id="ce709-166">Create a list of which extensions employees need on their computers.</span></span> <span data-ttu-id="ce709-167">在测试环境中测试扩展，以诊断与内部应用程序相关的任何兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="ce709-167">Test the extensions in a test environment to diagnose any compatibility issues with internal apps.</span></span>
2. <span data-ttu-id="ce709-168">选择需要更安全保障的站点。</span><span class="sxs-lookup"><span data-stu-id="ce709-168">Choose which sites need to be more secure.</span></span>

   - <span data-ttu-id="ce709-169">了解需要阻止扩展对哪些敏感内部网站或域进行更改或从中读取数据。</span><span class="sxs-lookup"><span data-stu-id="ce709-169">Find out which sensitive internal websites or domains you need to block extensions from making changes to or reading data from.</span></span>  
   - <span data-ttu-id="ce709-170">通过在扩展运行时阻止 API 调用来阻止对这些站点的访问。</span><span class="sxs-lookup"><span data-stu-id="ce709-170">Prevent access to these sites by blocking the API calls when the extension is run.</span></span> <span data-ttu-id="ce709-171">这包括阻止 Web 请求、读取 Cookie、JavaScript 注入、XHR 等。</span><span class="sxs-lookup"><span data-stu-id="ce709-171">This includes blocking web requests, reading cookies, JavaScript injection, XHR, and so on.</span></span>

3. <span data-ttu-id="ce709-172">确定这些扩展运行所需的权限。</span><span class="sxs-lookup"><span data-stu-id="ce709-172">Determine which permissions are required for these extensions to run.</span></span> <span data-ttu-id="ce709-173">识别哪些权限会给用户带来潜在风险。</span><span class="sxs-lookup"><span data-stu-id="ce709-173">Identify which permissions pose potential risks to your users.</span></span>

   - <span data-ttu-id="ce709-174">审核用户已安装的扩展，并查看他们需要哪些权限。</span><span class="sxs-lookup"><span data-stu-id="ce709-174">Audit the extensions your users have installed and see what permissions they need.</span></span> <span data-ttu-id="ce709-175">可以查看扩展代码中 Web 应用清单的 JSON 文件。</span><span class="sxs-lookup"><span data-stu-id="ce709-175">You can look at the web app manifest JSON file in the code of the extension.</span></span> <span data-ttu-id="ce709-176">执行以下步骤，了解扩展需要哪些权限：</span><span class="sxs-lookup"><span data-stu-id="ce709-176">Take the following steps to see what rights the extension needs:</span></span>

     - <span data-ttu-id="ce709-177">从 [Microsoft Edge 加载项](https://microsoftedge.microsoft.com/addons/) 网站或 [Chrome Web Store](https://chrome.google.com/webstore) 安装扩展。</span><span class="sxs-lookup"><span data-stu-id="ce709-177">Install the extension from the [Microsoft Edge Add-ons](https://microsoftedge.microsoft.com/addons/) website or the [Chrome Web Store](https://chrome.google.com/webstore).</span></span>
     - <span data-ttu-id="ce709-178">测试扩展并了解其在组织中的工作原理。</span><span class="sxs-lookup"><span data-stu-id="ce709-178">Test the extension and understand how it works in your organization.</span></span>
     - <span data-ttu-id="ce709-179">通过导航到 *edge://extensions* 来查看扩展所需的权限。</span><span class="sxs-lookup"><span data-stu-id="ce709-179">Review the permissions that the extension requires by navigating to *edge://extensions*.</span></span> <span data-ttu-id="ce709-180">例如，下一个屏幕截图中显示的 Microsoft Office 扩展请求“读取浏览历史记录”和“显示通知”的权限。</span><span class="sxs-lookup"><span data-stu-id="ce709-180">For example, the Microsoft Office extension shown in the next screenshot requests the permissions "Read your browsing history" and "Display notifications".</span></span> <span data-ttu-id="ce709-181">根据此扩展请求的权限级别来权衡此扩展的有用性。</span><span class="sxs-lookup"><span data-stu-id="ce709-181">Weigh the usefulness of this extension against the level of permissions it requests.</span></span> <span data-ttu-id="ce709-182">批准组织的扩展后，使用以下工具对其进行管理。</span><span class="sxs-lookup"><span data-stu-id="ce709-182">After you approve an extension for your organization, manage it using the following tools.</span></span>
   :::image type="content" source="media/microsoft-edge-manage-extensions/manage-extesions-office-extension.png" alt-text="具有权限的 Microsoft Office 扩展。":::

   - <span data-ttu-id="ce709-184">可以在组织中批准用户之前，验证组织中的用户请求的扩展。</span><span class="sxs-lookup"><span data-stu-id="ce709-184">You can also validate the extensions requested by users in your organization before approving them in the organization.</span></span> <span data-ttu-id="ce709-185">扩展使用的某些权限可能不明确。</span><span class="sxs-lookup"><span data-stu-id="ce709-185">Some of the permissions that extensions use can be vague.</span></span> <span data-ttu-id="ce709-186">对于关键业务应用，可以直接联系应用开发人员或供应商，以获取更多有关扩展的信息或查看源代码。</span><span class="sxs-lookup"><span data-stu-id="ce709-186">For business-critical apps, you can reach out to the app developer or vendor directly to get more information about the extension or look at the source code.</span></span> <span data-ttu-id="ce709-187">他们应能够详细地介绍该扩展可以在设备和网站上所进行的更改。</span><span class="sxs-lookup"><span data-stu-id="ce709-187">They should be able to detail the changes that the extension can make on devices and websites.</span></span>
   - <span data-ttu-id="ce709-188">查看“声明权限”列表，其中列出了扩展可以使用的所有权限。</span><span class="sxs-lookup"><span data-stu-id="ce709-188">Review the Declare Permissions list, which lists all permissions an extension can use.</span></span> <span data-ttu-id="ce709-189">从此列表中，可以决定要在组织中允许哪些权限。</span><span class="sxs-lookup"><span data-stu-id="ce709-189">From this list, you can decide which permissions you want to allow in your organization.</span></span>

4. <span data-ttu-id="ce709-190">从收集的数据中创建主列表。此列表将包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="ce709-190">Create a master list from the data you collected.This list will include the following information:</span></span>

   - <span data-ttu-id="ce709-191">**所需的扩展**。</span><span class="sxs-lookup"><span data-stu-id="ce709-191">**Required extensions**.</span></span> <span data-ttu-id="ce709-192">此列表可以按部门、办公室位置或其他相关信息进行组织。</span><span class="sxs-lookup"><span data-stu-id="ce709-192">This list could be organized by department, office location, or other relevant information.</span></span>
   - <span data-ttu-id="ce709-193">**扩展允许列表**。</span><span class="sxs-lookup"><span data-stu-id="ce709-193">**Extension Allowlist**.</span></span> <span data-ttu-id="ce709-194">具有权限可能遭到阻止但允许其运行的所需扩展。</span><span class="sxs-lookup"><span data-stu-id="ce709-194">Required extensions with permissions that may be blocked but will be allowed to run.</span></span> <span data-ttu-id="ce709-195">用户需要这些扩展，或者通过与供应商的对话确定不会带来风险。</span><span class="sxs-lookup"><span data-stu-id="ce709-195">These extensions are needed by your users or are determined to not be a risk through conversations with the vendor.</span></span>
   - <span data-ttu-id="ce709-196">**扩展阻止列表**。</span><span class="sxs-lookup"><span data-stu-id="ce709-196">**Extension Blocklist**.</span></span> <span data-ttu-id="ce709-197">阻止安装的扩展。</span><span class="sxs-lookup"><span data-stu-id="ce709-197">Extensions that are blocked from installation.</span></span> <span data-ttu-id="ce709-198">此列表中的扩展不具有允许运行的权限。</span><span class="sxs-lookup"><span data-stu-id="ce709-198">The extensions in this list have the permissions that aren’t allowed to run.</span></span> <span data-ttu-id="ce709-199">还包括要保持安全且不允许扩展访问的核心站点和域。</span><span class="sxs-lookup"><span data-stu-id="ce709-199">Also include the core sites and domains to be kept secure and not allowed extension access.</span></span> <span data-ttu-id="ce709-200">稍后可以将此阻止列表与已有的其他阻止列表进行比较。</span><span class="sxs-lookup"><span data-stu-id="ce709-200">Later you can compare this blocklist to others you already have in place.</span></span> <span data-ttu-id="ce709-201">可能会发现可以放宽当前的阻止列表策略。</span><span class="sxs-lookup"><span data-stu-id="ce709-201">You might find that you can relax your current blocklist policies.</span></span>

5. <span data-ttu-id="ce709-202">向利益干系人和 IT 团队展示你的列表以获取支持。</span><span class="sxs-lookup"><span data-stu-id="ce709-202">Present your list to your stakeholders and the IT team to get buy in.</span></span>
6. <span data-ttu-id="ce709-203">在实验室中或在组织中进行小型试点来测试新策略。</span><span class="sxs-lookup"><span data-stu-id="ce709-203">Test out the new policy in your lab or with a small pilot in your organization.</span></span>
7. <span data-ttu-id="ce709-204">分阶段向员工推出这些新策略集。</span><span class="sxs-lookup"><span data-stu-id="ce709-204">Roll out these new sets of policies to employees in phases.</span></span> <span data-ttu-id="ce709-205">有关详细信息，请参阅 [使用组策略管理 Microsoft Edge 扩展](microsoft-edge-manage-extensions-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ce709-205">For more information, see [Use group policies to manage Microsoft Edge extensions](microsoft-edge-manage-extensions-policies.md).</span></span>
8. <span data-ttu-id="ce709-206">查看用户的反馈。</span><span class="sxs-lookup"><span data-stu-id="ce709-206">Review feedback from your users.</span></span>
9. <span data-ttu-id="ce709-207">每月、每季度或每年重复并微调流程。</span><span class="sxs-lookup"><span data-stu-id="ce709-207">Repeat and fine-tune the process monthly, quarterly, or yearly.</span></span>

<span data-ttu-id="ce709-208">通过允许权限基线的强制实施和对敏感公司站点的保护，可以为企业提供更多安全性，同时为用户提供更好的体验。</span><span class="sxs-lookup"><span data-stu-id="ce709-208">With your baseline of allowed permissions enforced and sensitive corporate sites protected, you can provide your enterprise with more security while providing a better experience for users.</span></span> <span data-ttu-id="ce709-209">员工可能会安装之前无法安装的扩展，但无法在敏感的业务网站上运行它们。</span><span class="sxs-lookup"><span data-stu-id="ce709-209">Staff might install extensions that they couldn't before, but not run them on sensitive business sites.</span></span>  

## <a name="see-also"></a><span data-ttu-id="ce709-210">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce709-210">See also</span></span>

- [<span data-ttu-id="ce709-211">使用组策略管理 Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="ce709-211">Use group policies to manage Microsoft Edge extensions</span></span>](microsoft-edge-manage-extensions-policies.md)
- [<span data-ttu-id="ce709-212">创建用于托管 Microsoft Edge 扩展的 Web 应用商店</span><span class="sxs-lookup"><span data-stu-id="ce709-212">Create a web store to host Microsoft Edge extensions</span></span>](microsoft-edge-manage-extensions-webstore.md)
- [<span data-ttu-id="ce709-213">ExtensionSettings 策略参考指南</span><span class="sxs-lookup"><span data-stu-id="ce709-213">Reference guide for the ExtensionSettings policy</span></span>](microsoft-edge-manage-extensions-ref-guide.md)
- [<span data-ttu-id="ce709-214">Microsoft Edge 扩展的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="ce709-214">FAQ for Microsoft Edge Extensions</span></span>](microsoft-edge-manage-extensions-faq.md)
- [<span data-ttu-id="ce709-215">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="ce709-215">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)