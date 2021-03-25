---
title: 使用移动设备管理配置 Microsoft Edge
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 10/25/2019
audience: ITPro
ms.topic: technical
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 使用移动设备管理配置 Microsoft Edge。
ms.openlocfilehash: c9a725b5d0e820fb907150a8f83eeb17291b9f6a
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447546"
---
# <a name="configure-microsoft-edge-using-mobile-device-management"></a><span data-ttu-id="148cb-103">使用移动设备管理配置 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="148cb-103">Configure Microsoft Edge using Mobile Device Management</span></span>

<span data-ttu-id="148cb-104">本文介绍了如何使用[移动设备管理 (MDM)](/windows/client-management/mdm/) 通过 [ADMX 引入](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration)来配置 Windows 10 上的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="148cb-104">This article explains how to configure Microsoft Edge on Windows 10 using [Mobile Device Management (MDM)](/windows/client-management/mdm/) by means of [ADMX Ingestion](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration).</span></span> <span data-ttu-id="148cb-105">本文还介绍了：</span><span class="sxs-lookup"><span data-stu-id="148cb-105">This article also describes:</span></span>

- <span data-ttu-id="148cb-106">如何[为 Microsoft Edge 策略创建开放移动联盟统一资源标识符 (OMA-URI)](#create-an-oma-uri-for-microsoft-edge-policies)。</span><span class="sxs-lookup"><span data-stu-id="148cb-106">How to [create Open Mobile Alliance Uniform Resource Identifier (OMA-URI) for Microsoft Edge policies](#create-an-oma-uri-for-microsoft-edge-policies).</span></span>
- <span data-ttu-id="148cb-107">如何[使用 ADMX 引入和自定义 OMA-URI 在 Intune 中配置 Microsoft Edge](#configure-microsoft-edge-in-intune-using-admx-ingestion)。</span><span class="sxs-lookup"><span data-stu-id="148cb-107">How to [configure Microsoft Edge in Intune using ADMX ingestion and custom OMA-URI](#configure-microsoft-edge-in-intune-using-admx-ingestion).</span></span>

> [!NOTE]
> <span data-ttu-id="148cb-108">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="148cb-108">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="148cb-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="148cb-109">Prerequisites</span></span>

<span data-ttu-id="148cb-110">使用 Windows 10，最低系统要求如下：</span><span class="sxs-lookup"><span data-stu-id="148cb-110">Windows 10, with the following minimum system requirements:</span></span>

- <span data-ttu-id="148cb-111">Windows 10 版本 1903（已安装 [KB4512941](https://support.microsoft.com/help/4512941/) 和 [KB4517211](https://support.microsoft.com/help/4517211/)）</span><span class="sxs-lookup"><span data-stu-id="148cb-111">Windows 10, version 1903 with [KB4512941](https://support.microsoft.com/help/4512941/) and [KB4517211](https://support.microsoft.com/help/4517211/) installed</span></span>
- <span data-ttu-id="148cb-112">Windows 10 版本 1809（已安装 [KB4512534](https://support.microsoft.com/help/4512534/) 和 [KB4520062](https://support.microsoft.com/help/4520062/)）</span><span class="sxs-lookup"><span data-stu-id="148cb-112">Windows 10, version 1809 with [KB4512534](https://support.microsoft.com/help/4512534/) and [KB4520062](https://support.microsoft.com/help/4520062/) installed</span></span>
- <span data-ttu-id="148cb-113">Windows 10 版本 1803（已安装 [KB4512509](https://support.microsoft.com/help/4512509/) 和 [KB4519978](https://support.microsoft.com/help/4519978)）</span><span class="sxs-lookup"><span data-stu-id="148cb-113">Windows 10, version 1803 with [KB4512509](https://support.microsoft.com/help/4512509/) and [KB4519978](https://support.microsoft.com/help/4519978) installed</span></span>
- <span data-ttu-id="148cb-114">Windows 10 版本 1709（已安装 [KB4516071](https://support.microsoft.com/help/4516071/) 和 [KB4520006](https://support.microsoft.com/help/4520006)）</span><span class="sxs-lookup"><span data-stu-id="148cb-114">Windows 10, version 1709 with [KB4516071](https://support.microsoft.com/help/4516071/) and [KB4520006](https://support.microsoft.com/help/4520006) installed</span></span>

## <a name="overview"></a><span data-ttu-id="148cb-115">概述</span><span class="sxs-lookup"><span data-stu-id="148cb-115">Overview</span></span>

<span data-ttu-id="148cb-116">通过将 MDM 与支持 [ADMX 引入](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration)的首选企业移动性管理 (EMM) 或 MDM 提供程序配合使用，你可以配置 Windows 10 上的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="148cb-116">You can configure Microsoft Edge on Windows 10 using MDM with your preferred Enterprise Mobility Management (EMM) or MDM provider that supports [ADMX Ingestion](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration).</span></span>

<span data-ttu-id="148cb-117">使用 MDM 配置 Microsoft Edge 的过程分为两个部分：</span><span class="sxs-lookup"><span data-stu-id="148cb-117">Configuring Microsoft Edge with MDM is a two part process:</span></span>

1. <span data-ttu-id="148cb-118">将 Microsoft Edge ADMX 文件引入到 EMM 或 MDM 提供程序。</span><span class="sxs-lookup"><span data-stu-id="148cb-118">Ingesting the Microsoft Edge ADMX file into your EMM or MDM provider.</span></span> <span data-ttu-id="148cb-119">有关如何引入 ADMX 文件的说明，请参阅提供程序。</span><span class="sxs-lookup"><span data-stu-id="148cb-119">See your provider for instructions on how to ingest an ADMX file.</span></span>

   > [!NOTE]
   > <span data-ttu-id="148cb-120">有关 Microsoft Intune 的信息，请参阅[使用 ADMX 引入在 Intune 中配置 Microsoft Edge](#configure-microsoft-edge-in-intune-using-admx-ingestion)。</span><span class="sxs-lookup"><span data-stu-id="148cb-120">For Microsoft Intune, see [Configure Microsoft Edge in Intune using ADMX ingestion](#configure-microsoft-edge-in-intune-using-admx-ingestion).</span></span>

2. <span data-ttu-id="148cb-121">[为 Microsoft Edge 策略创建 OMA-URI](#create-an-oma-uri-for-microsoft-edge-policies)。</span><span class="sxs-lookup"><span data-stu-id="148cb-121">[Creating an OMA-URI for a Microsoft Edge policy](#create-an-oma-uri-for-microsoft-edge-policies).</span></span>

## <a name="create-an-oma-uri-for-microsoft-edge-policies"></a><span data-ttu-id="148cb-122">为 Microsoft Edge 策略创建 OMA-URI</span><span class="sxs-lookup"><span data-stu-id="148cb-122">Create an OMA-URI for Microsoft Edge policies</span></span>

<span data-ttu-id="148cb-123">以下各部分介绍了如何创建 OMA-URI 路径，以及如何为强制和推荐的浏览器策略查找和定义 XML 格式的值。</span><span class="sxs-lookup"><span data-stu-id="148cb-123">The following sections describe how to create the OMA-URI path and look up and define the value in XML format for mandatory and recommended browser polices.</span></span>

<span data-ttu-id="148cb-124">在开始之前，请从 [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)下载 Microsoft Edge 策略模板文件 (MicrosoftEdgePolicyTemplates.cab)，然后提取内容。</span><span class="sxs-lookup"><span data-stu-id="148cb-124">Before you get started download the Microsoft Edge policy templates file (MicrosoftEdgePolicyTemplates.cab) from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise) and extract the contents.</span></span>

<span data-ttu-id="148cb-125">定义 OMA-URI 有三个步骤：</span><span class="sxs-lookup"><span data-stu-id="148cb-125">There are three steps for defining the OMA-URI:</span></span>

1. [<span data-ttu-id="148cb-126">创建 OMA-URI 路径</span><span class="sxs-lookup"><span data-stu-id="148cb-126">Create the OMA-URI path</span></span>](#create-the-oma-uri-path)
2. [<span data-ttu-id="148cb-127">指定 OMA-URI 数据类型</span><span class="sxs-lookup"><span data-stu-id="148cb-127">Specify the OMA-URI data type</span></span>](#specify-the-data-type)
3. [<span data-ttu-id="148cb-128">设置 OMA-URI 值</span><span class="sxs-lookup"><span data-stu-id="148cb-128">Set the OMA-URI value</span></span>](#set-the-value-for-a-browser-policy)

### <a name="create-the-oma-uri-path"></a><span data-ttu-id="148cb-129">创建 OMA-URI 路径</span><span class="sxs-lookup"><span data-stu-id="148cb-129">Create the OMA-URI path</span></span>

<span data-ttu-id="148cb-130">使用以下公式作为指导来创建 OMA-URI 路径。</span><span class="sxs-lookup"><span data-stu-id="148cb-130">Use the following formula as a guide for creating the OMA-URI paths.</span></span> <br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/<ADMXIngestName>~Policy~<ADMXNamespace>~<ADMXCategory>/<PolicyName>`* <br/><br/>

| <span data-ttu-id="148cb-131">参数</span><span class="sxs-lookup"><span data-stu-id="148cb-131">Parameter</span></span>         | <span data-ttu-id="148cb-132">说明</span><span class="sxs-lookup"><span data-stu-id="148cb-132">Description</span></span>                                                                                   |
|-------------------|-----------------------------------------------------------------------------------------------|
| \<ADMXIngestName> | <span data-ttu-id="148cb-133">使用“Edge”或引入管理模板时定义的内容。</span><span class="sxs-lookup"><span data-stu-id="148cb-133">Use "Edge" or what you defined when ingesting the administrative template.</span></span> <span data-ttu-id="148cb-134">例如，如果你使用的是“/Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/MicrosoftEdge/Policy/EdgeAdmx”，则使用“MicrosoftEdge”。</span><span class="sxs-lookup"><span data-stu-id="148cb-134">For example, if you used "./Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/MicrosoftEdge/Policy/EdgeAdmx", then use "MicrosoftEdge".</span></span><br/><br/> <span data-ttu-id="148cb-135">`<ADMXIngestionName>` 必须与引入 ADMX 文件时所使用的内容匹配。</span><span class="sxs-lookup"><span data-stu-id="148cb-135">The `<ADMXIngestionName>` must match what was used when you ingested the ADMX file.</span></span> |
| \<ADMXNamespace>  | <span data-ttu-id="148cb-136">具体是“Microsoft_edge”还是“microsoft_edge_recommended”，取决于你是设置强制策略还是推荐的策略。</span><span class="sxs-lookup"><span data-stu-id="148cb-136">Either "microsoft_edge" or "microsoft_edge_recommended" depending on whether you're setting a mandatory or recommended policy.</span></span> |
| \<ADMXCategory>   | <span data-ttu-id="148cb-137">该策略的“parentCategory”在 ADMX 文件中定义。</span><span class="sxs-lookup"><span data-stu-id="148cb-137">The "parentCategory" of the policy is defined in the ADMX file.</span></span> <span data-ttu-id="148cb-138">如果策略未分组（未定义“parentCategory”），则省略 `<ADMXCategory>`。</span><span class="sxs-lookup"><span data-stu-id="148cb-138">Omit the `<ADMXCategory>` if the policy isn't grouped (No "parentCategory" defined).</span></span> |
| \<PolicyName>     | <span data-ttu-id="148cb-139">策略名称可在[浏览器策略参考](./microsoft-edge-policies.md)文章中找到。</span><span class="sxs-lookup"><span data-stu-id="148cb-139">The policy name can be found in the [Browser policy reference](./microsoft-edge-policies.md) article.</span></span> |

#### <a name="uri-path-example"></a><span data-ttu-id="148cb-140">URI 路径示例：</span><span class="sxs-lookup"><span data-stu-id="148cb-140">URI path example:</span></span>

<span data-ttu-id="148cb-141">在此示例中，假定 `<ADMXIngestName>` 节点被命名为“Edge”，并且你正在设置强制策略。</span><span class="sxs-lookup"><span data-stu-id="148cb-141">For this example, assume the `<ADMXIngestName>` node was named “Edge" and you're setting a mandatory policy.</span></span> <span data-ttu-id="148cb-142">URI 路径将为：</span><span class="sxs-lookup"><span data-stu-id="148cb-142">The URI path would be:</span></span><br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~<ADMXCategory>/<PolicyName>`*

<span data-ttu-id="148cb-143">如果策略不在组中（例如，DiskCacheSize），则删除“`~<ADMXCategory>`”。</span><span class="sxs-lookup"><span data-stu-id="148cb-143">If the policy isn't in a group (for example, DiskCacheSize) remove "`~<ADMXCategory>`".</span></span> <span data-ttu-id="148cb-144">将 `<PolicyName>` 替换为策略的名称 DiskCacheSize。</span><span class="sxs-lookup"><span data-stu-id="148cb-144">Replace `<PolicyName>` with the name of the policy, DiskCacheSize.</span></span> <span data-ttu-id="148cb-145">URI 路径将为：</span><span class="sxs-lookup"><span data-stu-id="148cb-145">The URI path would be:</span></span><br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/DiskCacheSize`*

<span data-ttu-id="148cb-146">如果策略位于组中，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="148cb-146">If the policy is in a group, follow these steps:</span></span>

1. <span data-ttu-id="148cb-147">使用任何 xml 编辑器打开 **msedge.admx**。</span><span class="sxs-lookup"><span data-stu-id="148cb-147">Open **msedge.admx** with any xml editor.</span></span>
2. <span data-ttu-id="148cb-148">搜索你想要设置的策略名称。</span><span class="sxs-lookup"><span data-stu-id="148cb-148">Search for the policy name you want to set.</span></span> <span data-ttu-id="148cb-149">例如，“ExtensionInstallForceList”。</span><span class="sxs-lookup"><span data-stu-id="148cb-149">For example, "ExtensionInstallForceList".</span></span>
3. <span data-ttu-id="148cb-150">使用 *parentCategory* 元素中 *ref* 属性的值。</span><span class="sxs-lookup"><span data-stu-id="148cb-150">Use the value of the *ref* attribute from the *parentCategory* element.</span></span> <span data-ttu-id="148cb-151">例如，\<parentCategory ref=" Extensions"/>中的“Extensions”。</span><span class="sxs-lookup"><span data-stu-id="148cb-151">For example, "Extensions" from \<parentCategory ref=" Extensions"/>.</span></span>
4. <span data-ttu-id="148cb-152">将 `<ADMXCategory>` 替换为 *ref* 属性值以构造 URI 路径。</span><span class="sxs-lookup"><span data-stu-id="148cb-152">Replace `<ADMXCategory>` with the *ref* attribute value to construct the URI path.</span></span> <span data-ttu-id="148cb-153">URI 路径将为：</span><span class="sxs-lookup"><span data-stu-id="148cb-153">The URI path would be:</span></span><br/><br/>
*`/Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Extensions/ExtensionInstallForcelist`*

### <a name="specify-the-data-type"></a><span data-ttu-id="148cb-154">指定数据类型</span><span class="sxs-lookup"><span data-stu-id="148cb-154">Specify the data type</span></span>

<span data-ttu-id="148cb-155">OMA-URI 数据类型始终为“字符串”。</span><span class="sxs-lookup"><span data-stu-id="148cb-155">The OMA-URI data type is always “String”.</span></span>

### <a name="set-the-value-for-a-browser-policy"></a><span data-ttu-id="148cb-156">设置浏览器策略的值</span><span class="sxs-lookup"><span data-stu-id="148cb-156">Set the value for a browser policy</span></span>

<span data-ttu-id="148cb-157">本部分介绍了如何为每种数据类型设置 XML 格式的值。</span><span class="sxs-lookup"><span data-stu-id="148cb-157">This section describes how to set the value, in XML format, for each data type.</span></span> <span data-ttu-id="148cb-158">转到[浏览器策略参考](./microsoft-edge-policies.md)以查找策略的数据类型。</span><span class="sxs-lookup"><span data-stu-id="148cb-158">Go to [Browser policy reference](./microsoft-edge-policies.md) to look up the data type of the policy.</span></span>

> [!NOTE]
> <span data-ttu-id="148cb-159">对于非布尔型数据类型，该值始终以 `<enabled/>` 开头。</span><span class="sxs-lookup"><span data-stu-id="148cb-159">For non-Boolean data types, the value always starts with `<enabled/>`.</span></span>

#### <a name="boolean-data-type"></a><span data-ttu-id="148cb-160">布尔型数据类型</span><span class="sxs-lookup"><span data-stu-id="148cb-160">Boolean data type</span></span>

<span data-ttu-id="148cb-161">对于布尔型类型的策略，请使用 `<enabled/>` 或 `<disabled/>`。</span><span class="sxs-lookup"><span data-stu-id="148cb-161">For policies that are Boolean types use `<enabled/>` or `<disabled/>`.</span></span>

#### <a name="integer-data-type"></a><span data-ttu-id="148cb-162">整数数据类型</span><span class="sxs-lookup"><span data-stu-id="148cb-162">Integer data type</span></span>

<span data-ttu-id="148cb-163">该值始终需要以 `<enabled/>` 元素开头，后跟 `<data id="[valueName]" value="[decimal value]"/>`。</span><span class="sxs-lookup"><span data-stu-id="148cb-163">The value always needs to start with the `<enabled/>` element followed by `<data id="[valueName]" value="[decimal value]"/>`.</span></span>

<span data-ttu-id="148cb-164">若要查找新选项卡页的值名称和小数值，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="148cb-164">To find the value name and decimal value for a new tab page, use the following steps:</span></span>

1. <span data-ttu-id="148cb-165">使用任何 xml 编辑器打开 **msedge.admx**。</span><span class="sxs-lookup"><span data-stu-id="148cb-165">Open **msedge.admx** with any xml editor.</span></span>
2. <span data-ttu-id="148cb-166">搜索名称属性与要设置的策略名称匹配的 `<policy>` 元素。</span><span class="sxs-lookup"><span data-stu-id="148cb-166">Search for the `<policy>` element where the name attribute matches the policy name you want to set.</span></span> <span data-ttu-id="148cb-167">对于“RestoreOnStartup”，搜索 `name="RestoreOnStartup"`。</span><span class="sxs-lookup"><span data-stu-id="148cb-167">For "RestoreOnStartup", search for `name="RestoreOnStartup"`.</span></span>
3. <span data-ttu-id="148cb-168">在 `<elements>` 节点中，查找要设置的值。</span><span class="sxs-lookup"><span data-stu-id="148cb-168">In the `<elements>` node, find the value you want to set.</span></span>
4. <span data-ttu-id="148cb-169">使用 `<elements>` 节点中“valueName”属性中的值。</span><span class="sxs-lookup"><span data-stu-id="148cb-169">Use the value in the "valueName" attribute in the `<elements>` node.</span></span> <span data-ttu-id="148cb-170">对于“RestoreOnStartup”，“valueName”是“RestoreOnStartup”。</span><span class="sxs-lookup"><span data-stu-id="148cb-170">For "RestoreOnStartup" the "valueName" is "RestoreOnStartup".</span></span>
5. <span data-ttu-id="148cb-171">使用 `<decimal>` 节点中“value”属性中的值。</span><span class="sxs-lookup"><span data-stu-id="148cb-171">Use the value in the "value" attribute in the `<decimal>` node.</span></span> <span data-ttu-id="148cb-172">若要使“RestoreOnStartup”打开新选项卡页，该值为“5”。</span><span class="sxs-lookup"><span data-stu-id="148cb-172">For "RestoreOnStartup" to open the new tab page the value is "5".</span></span>

<span data-ttu-id="148cb-173">若要在启动时打开新选项卡页，请使用：</span><span class="sxs-lookup"><span data-stu-id="148cb-173">To open the new tab page on startup use:</span></span><br>
`<enabled/> <data id="RestoreOnStartup" value="5"/>`

#### <a name="list-of-strings-data-type"></a><span data-ttu-id="148cb-174">字符串列表数据类型</span><span class="sxs-lookup"><span data-stu-id="148cb-174">List of strings data type</span></span>

<span data-ttu-id="148cb-175">该值始终需要以 `<enabled/>` 元素开头，后跟 `<data id="[listID]" value="[string 1];[string 2];[string 3]"/>`。</span><span class="sxs-lookup"><span data-stu-id="148cb-175">The value always needs to start with the `<enabled/>` element followed by `<data id="[listID]" value="[string 1];[string 2];[string 3]"/>`.</span></span>

> [!NOTE]
> <span data-ttu-id="148cb-176">即使大多数情况下“Id=”属性名称与策略名称匹配，但该属性名称不是策略名称。</span><span class="sxs-lookup"><span data-stu-id="148cb-176">The "id=" attribute name isn't the policy name, even though in most cases it matches the policy name.</span></span> <span data-ttu-id="148cb-177">它是 ADMX 文件中的 \<list> 节点 ID 属性值。</span><span class="sxs-lookup"><span data-stu-id="148cb-177">It's the \<list> node id attribute value, which is found in the ADMX file.</span></span>

<span data-ttu-id="148cb-178">若要查找 listID 并定义阻止 URL 的值，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="148cb-178">To find the listID and define the value to block a URL, follow these steps:</span></span>

1. <span data-ttu-id="148cb-179">使用任何 xml 编辑器打开 **msedge.admx**。</span><span class="sxs-lookup"><span data-stu-id="148cb-179">Open **msedge.admx** with any xml editor.</span></span>
2. <span data-ttu-id="148cb-180">搜索名称属性与要设置的策略名称匹配的 `<policy>` 元素。</span><span class="sxs-lookup"><span data-stu-id="148cb-180">Search for the `<policy>` element where the name attribute matches the policy name you want to set.</span></span> <span data-ttu-id="148cb-181">对于“URLBlocklist”，搜索 `name="URLBlocklist"`。</span><span class="sxs-lookup"><span data-stu-id="148cb-181">For "URLBlocklist", search for `name="URLBlocklist"`.</span></span>
3. <span data-ttu-id="148cb-182">使用 `<list> node for [listID]` 的“id”属性中的值。</span><span class="sxs-lookup"><span data-stu-id="148cb-182">Use the value in the "id" attribute of the `<list> node for [listID]`.</span></span>
4. <span data-ttu-id="148cb-183">“值”是由分号 (;) 分隔的 URL 列表</span><span class="sxs-lookup"><span data-stu-id="148cb-183">The "value" is a list of URLs separated by a semicolon (;)</span></span>

<span data-ttu-id="148cb-184">例如，用于阻止访问 `contoso.com` 和 `https://ssl.server.com`：</span><span class="sxs-lookup"><span data-stu-id="148cb-184">For example, to block access to `contoso.com` and `https://ssl.server.com`:</span></span><br>
`<enabled/> <data id=" URLBlocklistDesc" value="contoso.com;https://ssl.server.com"/>`

#### <a name="dictionary-or-string-data-type"></a><span data-ttu-id="148cb-185">字典或字符串数据类型</span><span class="sxs-lookup"><span data-stu-id="148cb-185">Dictionary or String data type</span></span>

<span data-ttu-id="148cb-186">该值始终需要以 `<enabled/>` 开头，后跟 `<data id="[textID]" value="[string]"/>`。</span><span class="sxs-lookup"><span data-stu-id="148cb-186">The value always needs to start with the `<enabled/>` followed by `<data id="[textID]" value="[string]"/>` .</span></span>

<span data-ttu-id="148cb-187">若要查找 textID 并定义值来设置区域设置，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="148cb-187">To find the textID and define the value set the locale, follow these steps:</span></span>

1. <span data-ttu-id="148cb-188">使用任何 xml 编辑器打开 **msedge.admx**。</span><span class="sxs-lookup"><span data-stu-id="148cb-188">Open **msedge.admx** with any xml editor.</span></span>
2. <span data-ttu-id="148cb-189">搜索名称属性与要设置的策略名称匹配的 `<policy>` 元素。</span><span class="sxs-lookup"><span data-stu-id="148cb-189">Search for the `<policy>` element where the name attribute matches the policy name you want to set.</span></span> <span data-ttu-id="148cb-190">对于“ApplicationLocaleValue”，搜索 `name="ApplicationLocaleValue"`。</span><span class="sxs-lookup"><span data-stu-id="148cb-190">For "ApplicationLocaleValue", search for `name="ApplicationLocaleValue"`.</span></span>
3. <span data-ttu-id="148cb-191">对于 `[textID]`，请使用 `<text>` 节点“id”属性中的值。</span><span class="sxs-lookup"><span data-stu-id="148cb-191">Use the value in the "id" attribute of the `<text>` node for `[textID]`.</span></span>
4. <span data-ttu-id="148cb-192">将“值”设置为区域性代码。</span><span class="sxs-lookup"><span data-stu-id="148cb-192">Set the "value" to the culture code.</span></span>

<span data-ttu-id="148cb-193">若要使用“ApplicationLocaleValue”策略将区域设置设为“es-US”，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="148cb-193">To set the locale to "es-US" with the "ApplicationLocaleValue" policy:</span></span><br>
`<enabled/> <data id="ApplicationLocaleValue" value="es-US"/>`

### <a name="create-the-oma-uri-for-a-recommended-policies"></a><span data-ttu-id="148cb-194">为推荐的策略创建 OMA-URI</span><span class="sxs-lookup"><span data-stu-id="148cb-194">Create the OMA-URI for a recommended policies</span></span>

<span data-ttu-id="148cb-195">为推荐的策略定义 URI 路径取决于你要配置的策略。</span><span class="sxs-lookup"><span data-stu-id="148cb-195">Defining the URI path for recommended policies depends on the policy you want to configure.</span></span>

#### <a name="to-define-the-uri-path-for-a-recommended-policy"></a><span data-ttu-id="148cb-196">要为推荐的策略定义 URI 路径，请执行以下步骤</span><span class="sxs-lookup"><span data-stu-id="148cb-196">To define the URI path for a recommended policy</span></span>

<span data-ttu-id="148cb-197">使用 URI 路径公式（*`./Device/Vendor/MSFT/Policy/Config/<ADMXIngestName>~Policy~<ADMXNamespace>~<ADMXCategory>/<PolicyName>`*）和以下步骤定义 URI 路径：</span><span class="sxs-lookup"><span data-stu-id="148cb-197">Use the URI path formula (*`./Device/Vendor/MSFT/Policy/Config/<ADMXIngestName>~Policy~<ADMXNamespace>~<ADMXCategory>/<PolicyName>`*) and the following steps to define the URI path:</span></span>

1. <span data-ttu-id="148cb-198">使用任何 xml 编辑器打开 **msedge.admx**。</span><span class="sxs-lookup"><span data-stu-id="148cb-198">Open **msedge.admx** with any xml editor.</span></span>
2. <span data-ttu-id="148cb-199">如果要配置的策略不在组中，请跳到第 4 步，然后从路径中删除 `~<ADMXCategory>`。</span><span class="sxs-lookup"><span data-stu-id="148cb-199">If the policy you want to configure isn't in a group, skip to step 4 and remove `~<ADMXCategory>` from the path.</span></span>
3. <span data-ttu-id="148cb-200">如果要配置的策略位于组中：</span><span class="sxs-lookup"><span data-stu-id="148cb-200">If the policy you want to configure is in a group:</span></span>

   - <span data-ttu-id="148cb-201">若要查找 `<ADMXCategory>`，请搜索要设置的策略。</span><span class="sxs-lookup"><span data-stu-id="148cb-201">To look up the `<ADMXCategory>`, search for the policy you want to set.</span></span> <span data-ttu-id="148cb-202">搜索时，将“_recommended”附加到策略名称。</span><span class="sxs-lookup"><span data-stu-id="148cb-202">When searching append "_recommended" to the policy name.</span></span> <span data-ttu-id="148cb-203">例如，搜索“RegisteredProtocolHandlers_recommended”的结果如下：</span><span class="sxs-lookup"><span data-stu-id="148cb-203">For example, a search for "RegisteredProtocolHandlers_recommended” has the following result:</span></span>

        ```xml
         <policy class="Both" displayName="$(string.RegisteredProtocolHandlers)" explainText="$(string.RegisteredProtocolHandlers_Explain)" key="Software\Policies\Microsoft\Edge\Recommended" name="RegisteredProtocolHandlers_recommended" presentation="$(presentation.RegisteredProtocolHandlers)">
           <parentCategory ref="ContentSettings_recommended"/>
           <supportedOn ref="SUPPORTED_WIN7_V77"/>
           <elements>
             <text id="RegisteredProtocolHandlers" maxLength="1000000" valueName="RegisteredProtocolHandlers"/>
           </elements>
         </policy>
        ```

   - <span data-ttu-id="148cb-204">从 `<parentCategory>` 元素中复制 *ref* 属性的值。</span><span class="sxs-lookup"><span data-stu-id="148cb-204">Copy the value of the *ref* attribute from the `<parentCategory>` element.</span></span> <span data-ttu-id="148cb-205">对于“ContentSettings”，请从 `<parentCategory ref=" ContentSettings_recommended"/>` 中复制“ContentSettings_recommended”。</span><span class="sxs-lookup"><span data-stu-id="148cb-205">For "ContentSettings", copy "ContentSettings_recommended" from `<parentCategory ref=" ContentSettings_recommended"/>`.</span></span>
   - <span data-ttu-id="148cb-206">将 `<ADMXCategory>` 替换为 *ref* 属性值以在 URI 路径公式中构造 URI 路径。</span><span class="sxs-lookup"><span data-stu-id="148cb-206">Replace `<ADMXCategory>` with the *ref* attribute value to construct the URI path in the URI path formula.</span></span>

4. <span data-ttu-id="148cb-207">`<PolicyName>` 是附加了“_recommended”的策略的名称。</span><span class="sxs-lookup"><span data-stu-id="148cb-207">The `<PolicyName>` is the name of the policy with "_recommended" appended to it.</span></span>

#### <a name="oma-uri-path-examples-for-recommended-policies"></a><span data-ttu-id="148cb-208">适用于推荐的策略的 OMA-URI 路径示例</span><span class="sxs-lookup"><span data-stu-id="148cb-208">OMA-URI path examples for recommended policies</span></span>

<span data-ttu-id="148cb-209">下表显示了推荐策略的 OMA-URI 路径的示例。</span><span class="sxs-lookup"><span data-stu-id="148cb-209">The following table shows examples of OMA-URI paths for recommended policies.</span></span>

|              <span data-ttu-id="148cb-210">策略</span><span class="sxs-lookup"><span data-stu-id="148cb-210">Policy</span></span>               |             <span data-ttu-id="148cb-211">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="148cb-211">OMA-URI</span></span>                      |
|-----------------------------------|------------------------------------------|
| [<span data-ttu-id="148cb-212">RegisteredProtocolHandlers</span><span class="sxs-lookup"><span data-stu-id="148cb-212">RegisteredProtocolHandlers</span></span>](./microsoft-edge-policies.md#registeredprotocolhandlers)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~ContentSettings_recommended/RegisteredProtocolHandlers_recommended`                        |
| [<span data-ttu-id="148cb-213">PasswordManagerEnabled</span><span class="sxs-lookup"><span data-stu-id="148cb-213">PasswordManagerEnabled</span></span>](./microsoft-edge-policies.md#passwordmanagerenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~PasswordManager_recommended/PasswordManagerEnabled_recommended`                        |
| [<span data-ttu-id="148cb-214">PrintHeaderFooter</span><span class="sxs-lookup"><span data-stu-id="148cb-214">PrintHeaderFooter</span></span>](./microsoft-edge-policies.md#printheaderfooter)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Printing_recommended/PrintHeaderFooter_recommended`                        |
| [<span data-ttu-id="148cb-215">SmartScreenEnabled</span><span class="sxs-lookup"><span data-stu-id="148cb-215">SmartScreenEnabled</span></span>](./microsoft-edge-policies.md#smartscreenenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~SmartScreen_recommended/SmartScreenEnabled_recommended`                        |
| [<span data-ttu-id="148cb-216">HomePageLocation</span><span class="sxs-lookup"><span data-stu-id="148cb-216">HomePageLocation</span></span>](./microsoft-edge-policies.md#homepagelocation)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Startup_recommended/HomepageLocation_recommended`                        |
| [<span data-ttu-id="148cb-217">ShowHomeButton</span><span class="sxs-lookup"><span data-stu-id="148cb-217">ShowHomeButton</span></span>](./microsoft-edge-policies.md#showhomebutton)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Startup_recommended/ShowHomeButton_recommended`                        |
| [<span data-ttu-id="148cb-218">FavoritesBarEnabled</span><span class="sxs-lookup"><span data-stu-id="148cb-218">FavoritesBarEnabled</span></span>](./microsoft-edge-policies.md#favoritesbarenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~/FavoritesBarEnabled_recommended`                        |

### <a name="oma-uri-examples"></a><span data-ttu-id="148cb-219">OMA-URI 示例</span><span class="sxs-lookup"><span data-stu-id="148cb-219">OMA-URI examples</span></span>

<span data-ttu-id="148cb-220">OMA-URI 示例及其 URI 路径、类型和示例值。</span><span class="sxs-lookup"><span data-stu-id="148cb-220">OMA-URI examples with their URI path, type, and an example value.</span></span>

#### <a name="boolean-data-type-examples"></a><span data-ttu-id="148cb-221">布尔型数据类型示例</span><span class="sxs-lookup"><span data-stu-id="148cb-221">Boolean data type examples</span></span>

*<span data-ttu-id="148cb-222">[ShowHomeButton](./microsoft-edge-policies.md#ShowHomeButton):</span><span class="sxs-lookup"><span data-stu-id="148cb-222">[ShowHomeButton](./microsoft-edge-policies.md#ShowHomeButton):</span></span>*

| <span data-ttu-id="148cb-223">字段</span><span class="sxs-lookup"><span data-stu-id="148cb-223">Field</span></span>   | <span data-ttu-id="148cb-224">值</span><span class="sxs-lookup"><span data-stu-id="148cb-224">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="148cb-225">名称</span><span class="sxs-lookup"><span data-stu-id="148cb-225">Name</span></span>    | <span data-ttu-id="148cb-226">Microsoft Edge：ShowHomeButton</span><span class="sxs-lookup"><span data-stu-id="148cb-226">Microsoft Edge: ShowHomeButton</span></span>                                                       |
| <span data-ttu-id="148cb-227">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="148cb-227">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/ShowHomeButton` |
| <span data-ttu-id="148cb-228">类型</span><span class="sxs-lookup"><span data-stu-id="148cb-228">type</span></span>    | <span data-ttu-id="148cb-229">字符串</span><span class="sxs-lookup"><span data-stu-id="148cb-229">String</span></span>                                                                               |
| <span data-ttu-id="148cb-230">值</span><span class="sxs-lookup"><span data-stu-id="148cb-230">Value</span></span>   | `<enabled/>`                                                                          |

*<span data-ttu-id="148cb-231">[DefaultSearchProviderEnabled](./microsoft-edge-policies.md#DefaultSearchProviderEnabled)：</span><span class="sxs-lookup"><span data-stu-id="148cb-231">[DefaultSearchProviderEnabled](./microsoft-edge-policies.md#DefaultSearchProviderEnabled):</span></span>*

| <span data-ttu-id="148cb-232">字段</span><span class="sxs-lookup"><span data-stu-id="148cb-232">Field</span></span>   | <span data-ttu-id="148cb-233">值</span><span class="sxs-lookup"><span data-stu-id="148cb-233">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="148cb-234">名称</span><span class="sxs-lookup"><span data-stu-id="148cb-234">Name</span></span>    | <span data-ttu-id="148cb-235">Microsoft Edge：DefaultSearchProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="148cb-235">Microsoft Edge: DefaultSearchProviderEnabled</span></span>                                         |
| <span data-ttu-id="148cb-236">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="148cb-236">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~DefaultSearchProvider/DefaultSearchProviderEnabled`    |
| <span data-ttu-id="148cb-237">类型</span><span class="sxs-lookup"><span data-stu-id="148cb-237">type</span></span>    | <span data-ttu-id="148cb-238">字符串</span><span class="sxs-lookup"><span data-stu-id="148cb-238">String</span></span>                                                                               |
| <span data-ttu-id="148cb-239">值</span><span class="sxs-lookup"><span data-stu-id="148cb-239">Value</span></span>   | `<disable/>`                                                                          |

### <a name="integer-data-type-examples"></a><span data-ttu-id="148cb-240">整数数据类型示例</span><span class="sxs-lookup"><span data-stu-id="148cb-240">Integer data type examples</span></span>

*<span data-ttu-id="148cb-241">[AutoImportAtFirstRun](./microsoft-edge-policies.md#AutoImportAtFirstRun)：</span><span class="sxs-lookup"><span data-stu-id="148cb-241">[AutoImportAtFirstRun](./microsoft-edge-policies.md#AutoImportAtFirstRun):</span></span>*

| <span data-ttu-id="148cb-242">字段</span><span class="sxs-lookup"><span data-stu-id="148cb-242">Field</span></span>   | <span data-ttu-id="148cb-243">值</span><span class="sxs-lookup"><span data-stu-id="148cb-243">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="148cb-244">名称</span><span class="sxs-lookup"><span data-stu-id="148cb-244">Name</span></span>    | <span data-ttu-id="148cb-245">Microsoft Edge：AutoImportAtFirstRun</span><span class="sxs-lookup"><span data-stu-id="148cb-245">Microsoft Edge: AutoImportAtFirstRun</span></span>                                                 |
| <span data-ttu-id="148cb-246">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="148cb-246">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/AutoImportAtFirstRun`   |
| <span data-ttu-id="148cb-247">类型</span><span class="sxs-lookup"><span data-stu-id="148cb-247">type</span></span>    | <span data-ttu-id="148cb-248">字符串</span><span class="sxs-lookup"><span data-stu-id="148cb-248">String</span></span>                                                                               |
| <span data-ttu-id="148cb-249">值</span><span class="sxs-lookup"><span data-stu-id="148cb-249">Value</span></span>   | `<enabled/><data id="AutoImportAtFirstRun" value="1"/>`                             |

*<span data-ttu-id="148cb-250">[DefaultImagesSetting](./microsoft-edge-policies.md#DefaultImagesSetting)：</span><span class="sxs-lookup"><span data-stu-id="148cb-250">[DefaultImagesSetting](./microsoft-edge-policies.md#DefaultImagesSetting):</span></span>*

| <span data-ttu-id="148cb-251">字段</span><span class="sxs-lookup"><span data-stu-id="148cb-251">Field</span></span>   | <span data-ttu-id="148cb-252">值</span><span class="sxs-lookup"><span data-stu-id="148cb-252">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="148cb-253">姓名</span><span class="sxs-lookup"><span data-stu-id="148cb-253">Name</span></span>    | <span data-ttu-id="148cb-254">Microsoft Edge：DefaultImagesSetting</span><span class="sxs-lookup"><span data-stu-id="148cb-254">Microsoft Edge: DefaultImagesSetting</span></span>                                                 |
| <span data-ttu-id="148cb-255">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="148cb-255">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ContentSettings/DefaultImagesSetting`    |
| <span data-ttu-id="148cb-256">类型</span><span class="sxs-lookup"><span data-stu-id="148cb-256">type</span></span>    | <span data-ttu-id="148cb-257">字符串</span><span class="sxs-lookup"><span data-stu-id="148cb-257">String</span></span>                                                                               |
| <span data-ttu-id="148cb-258">值</span><span class="sxs-lookup"><span data-stu-id="148cb-258">Value</span></span>   | `<enabled/><data id="DefaultImagesSetting" value="2"/>`                             |

*<span data-ttu-id="148cb-259">[DiskCacheSize](./microsoft-edge-policies.md#DiskCacheSize)：</span><span class="sxs-lookup"><span data-stu-id="148cb-259">[DiskCacheSize](./microsoft-edge-policies.md#DiskCacheSize):</span></span>*

| <span data-ttu-id="148cb-260">字段</span><span class="sxs-lookup"><span data-stu-id="148cb-260">Field</span></span>   | <span data-ttu-id="148cb-261">值</span><span class="sxs-lookup"><span data-stu-id="148cb-261">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="148cb-262">名称</span><span class="sxs-lookup"><span data-stu-id="148cb-262">Name</span></span>    | <span data-ttu-id="148cb-263">Microsoft Edge：DiskCacheSize</span><span class="sxs-lookup"><span data-stu-id="148cb-263">Microsoft Edge: DiskCacheSize</span></span>                                                        |
| <span data-ttu-id="148cb-264">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="148cb-264">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/DiskCacheSize`        |
| <span data-ttu-id="148cb-265">类型</span><span class="sxs-lookup"><span data-stu-id="148cb-265">type</span></span>    | <span data-ttu-id="148cb-266">字符串</span><span class="sxs-lookup"><span data-stu-id="148cb-266">String</span></span>                                                                               |
| <span data-ttu-id="148cb-267">值</span><span class="sxs-lookup"><span data-stu-id="148cb-267">Value</span></span>   | `<enabled/><data id="DiskCacheSize" value="1000000"/>`                               |

#### <a name="list-of-strings-data-type-examples"></a><span data-ttu-id="148cb-268">字符串列表数据类型示例</span><span class="sxs-lookup"><span data-stu-id="148cb-268">List of strings data type examples</span></span>
<!--
*[NotificationsAllowedForUrls](./microsoft-edge-policies.md#NotificationsAllowedForUrls):*

| Field   | Value                                                                                |
|---------|--------------------------------------------------------------------------------------|
| Name    | Microsoft Edge: NotificationsAllowedForUrls                                          |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ContentSettings/NotificationsAllowedForUrls`    |
| Type    | String                                                                               |
| Value   | `<enabled/><data id="NotificationsAllowedForUrlsDesc" value="https://www.contoso.com"/>`<br>For multiple list items: `<data id="NotificationsAllowedForUrlsDesc" value="https://www.contoso.com;[*.]contoso.edu"/>`                               |
-->
*<span data-ttu-id="148cb-269">[RestoreOnStartupURLS](./microsoft-edge-policies.md#RestoreOnStartupURLS)：</span><span class="sxs-lookup"><span data-stu-id="148cb-269">[RestoreOnStartupURLS](./microsoft-edge-policies.md#RestoreOnStartupURLS):</span></span>*

| <span data-ttu-id="148cb-270">字段</span><span class="sxs-lookup"><span data-stu-id="148cb-270">Field</span></span>   | <span data-ttu-id="148cb-271">值</span><span class="sxs-lookup"><span data-stu-id="148cb-271">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="148cb-272">名称</span><span class="sxs-lookup"><span data-stu-id="148cb-272">Name</span></span>    | <span data-ttu-id="148cb-273">Microsoft Edge：RestoreOnStartupURLS</span><span class="sxs-lookup"><span data-stu-id="148cb-273">Microsoft Edge: RestoreOnStartupURLS</span></span>                                                 |
| <span data-ttu-id="148cb-274">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="148cb-274">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/RestoreOnStartupURLs`    |
| <span data-ttu-id="148cb-275">类型</span><span class="sxs-lookup"><span data-stu-id="148cb-275">Type</span></span>    | <span data-ttu-id="148cb-276">字符串</span><span class="sxs-lookup"><span data-stu-id="148cb-276">String</span></span>                                                                               |
| <span data-ttu-id="148cb-277">值</span><span class="sxs-lookup"><span data-stu-id="148cb-277">Value</span></span>   | `<enabled/><data id="RestoreOnStartupURLsDesc" value="1&#xF000;http://www.bing.com"/>`<br><span data-ttu-id="148cb-278">对于多个列表项目：</span><span class="sxs-lookup"><span data-stu-id="148cb-278">For multiple list items:</span></span> `<enabled/><data id="RestoreOnStartupURLsDesc" value="1&#xF000;http://www.bing.com&#xF000;2&#xF000;http://www.microsoft.com"/>`  |

*<span data-ttu-id="148cb-279">[ExtensionInstallForcelist](./microsoft-edge-policies.md#ExtensionInstallForcelist)：</span><span class="sxs-lookup"><span data-stu-id="148cb-279">[ExtensionInstallForcelist](./microsoft-edge-policies.md#ExtensionInstallForcelist):</span></span>*

| <span data-ttu-id="148cb-280">字段</span><span class="sxs-lookup"><span data-stu-id="148cb-280">Field</span></span>   | <span data-ttu-id="148cb-281">值</span><span class="sxs-lookup"><span data-stu-id="148cb-281">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="148cb-282">名称</span><span class="sxs-lookup"><span data-stu-id="148cb-282">Name</span></span>    | <span data-ttu-id="148cb-283">Microsoft Edge：ExtensionInstallForcelist</span><span class="sxs-lookup"><span data-stu-id="148cb-283">Microsoft Edge: ExtensionInstallForcelist</span></span>                                            |
| <span data-ttu-id="148cb-284">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="148cb-284">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Extensions/ExtensionInstallForcelist`    |
| <span data-ttu-id="148cb-285">类型</span><span class="sxs-lookup"><span data-stu-id="148cb-285">Type</span></span>    | <span data-ttu-id="148cb-286">字符串</span><span class="sxs-lookup"><span data-stu-id="148cb-286">String</span></span>                                                                               |
| <span data-ttu-id="148cb-287">值</span><span class="sxs-lookup"><span data-stu-id="148cb-287">Value</span></span>   | `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000;gbchcmhmhahfdphkhkmpfmihenigjmpp;https://extensionwebstorebase.edgesv.net/v1/crx"/>`                               |

#### <a name="dictionary-and-string-data-type-example"></a><span data-ttu-id="148cb-288">字典和字符串数据类型示例</span><span class="sxs-lookup"><span data-stu-id="148cb-288">Dictionary and String data type example</span></span>

*<span data-ttu-id="148cb-289">[ProxyMode](./microsoft-edge-policies.md#ProxyMode)：</span><span class="sxs-lookup"><span data-stu-id="148cb-289">[ProxyMode](./microsoft-edge-policies.md#ProxyMode):</span></span>*

| <span data-ttu-id="148cb-290">字段</span><span class="sxs-lookup"><span data-stu-id="148cb-290">Field</span></span>   | <span data-ttu-id="148cb-291">值</span><span class="sxs-lookup"><span data-stu-id="148cb-291">Value</span></span>                                                                                |
|---------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="148cb-292">名称</span><span class="sxs-lookup"><span data-stu-id="148cb-292">Name</span></span>    | <span data-ttu-id="148cb-293">Microsoft Edge：ProxyMode</span><span class="sxs-lookup"><span data-stu-id="148cb-293">Microsoft Edge: ProxyMode</span></span>                                                            |
| <span data-ttu-id="148cb-294">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="148cb-294">OMA-URI</span></span> | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ProxyMode/ProxyMode`  |
| <span data-ttu-id="148cb-295">类型</span><span class="sxs-lookup"><span data-stu-id="148cb-295">Type</span></span>    | <span data-ttu-id="148cb-296">字符串</span><span class="sxs-lookup"><span data-stu-id="148cb-296">String</span></span>                                                                               |
| <span data-ttu-id="148cb-297">值</span><span class="sxs-lookup"><span data-stu-id="148cb-297">Value</span></span>   | `<enabled/><data id="ProxyMode" value="auto_detect"/>`                               |

## <a name="configure-microsoft-edge-in-intune-using-admx-ingestion"></a><span data-ttu-id="148cb-298">使用 ADMX 引入在 Intune 中配置 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="148cb-298">Configure Microsoft Edge in Intune using ADMX ingestion</span></span>

<span data-ttu-id="148cb-299">使用 Microsoft Intune 配置 Microsoft Edge 的推荐方法是使用管理模板配置文件，如[使用 Microsoft Intune 配置 Microsoft Edge 策略设置](./configure-edge-with-intune.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="148cb-299">The recommended way to configure Microsoft Edge with Microsoft Intune is to use the Administrative Templates profile as described in [Configure Microsoft Edge policy settings with Microsoft Intune](./configure-edge-with-intune.md).</span></span> <span data-ttu-id="148cb-300">如果想要评估 Intune 内的 Microsoft Edge 管理模板中当前不可用的策略，你可以使用 [Intune 中 Windows 10 设备的自定义设置](/intune/configuration/custom-settings-windows-10)来配置 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="148cb-300">If you want to evaluate a policy that is currently not available in the Microsoft Edge Administrative Templates in Intune you can configure Microsoft Edge using  [custom settings for Windows 10 devices in Intune](/intune/configuration/custom-settings-windows-10).</span></span>

<span data-ttu-id="148cb-301">本部分介绍了以下操作方法：</span><span class="sxs-lookup"><span data-stu-id="148cb-301">This section describes how to:</span></span>

1. [<span data-ttu-id="148cb-302">将 Microsoft Edge ADMX 文件引入到 Intune 中</span><span class="sxs-lookup"><span data-stu-id="148cb-302">Ingest the Microsoft Edge ADMX file into Intune</span></span>](#ingest-the-microsoft-edge-admx-file-into-intune)
2. [<span data-ttu-id="148cb-303">在 Intune 中使用自定义 OMA-URI 设置策略</span><span class="sxs-lookup"><span data-stu-id="148cb-303">Set a policy using custom OMA-URI in Intune</span></span>](#set-a-policy-using-custom-oma-uri-in-intune)

> [!IMPORTANT]
> <span data-ttu-id="148cb-304">最佳做法是，不要使用自定义 OMA-URI 配置文件和管理模板配置文件来配置 Intune 中的相同 Microsoft Edge 设置。</span><span class="sxs-lookup"><span data-stu-id="148cb-304">As a best practice, don’t use a custom OMA-URI profile and an Administration templates profile to configure the same Microsoft Edge setting in Intune.</span></span> <span data-ttu-id="148cb-305">如果同时使用自定义 OMA-URI 和管理模板配置文件部署同一策略，但使用的值不同，则用户将获得不可预知的结果。</span><span class="sxs-lookup"><span data-stu-id="148cb-305">If you deploy the same policy using both a custom OMA-URI  and an Administrative template profile, but with different values, users will get unpredictable results.</span></span> <span data-ttu-id="148cb-306">我们强烈建议在使用管理模板配置文件之前删除 OMA-URI 配置文件。</span><span class="sxs-lookup"><span data-stu-id="148cb-306">We strongly recommend removing your OMA-URI profile before using an Administration templates profile.</span></span>

### <a name="ingest-the-microsoft-edge-admx-file-into-intune"></a><span data-ttu-id="148cb-307">将 Microsoft Edge ADMX 文件引入到 Intune 中</span><span class="sxs-lookup"><span data-stu-id="148cb-307">Ingest the Microsoft Edge ADMX file into Intune</span></span>

<span data-ttu-id="148cb-308">本节介绍了如何将 Microsoft Edge 管理模板（**msedge admx**文件）引入到 Intune 中。</span><span class="sxs-lookup"><span data-stu-id="148cb-308">This section describes how to ingest the Microsoft Edge administrative template (**msedge.admx** file) into Intune.</span></span>

> [!WARNING]
> <span data-ttu-id="148cb-309">请不要在引入文件之前修改 ADMX 文件。</span><span class="sxs-lookup"><span data-stu-id="148cb-309">Don't modify the ADMX file before ingesting the file.</span></span>

<span data-ttu-id="148cb-310">要引入 ADMX 文件，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="148cb-310">To ingest the ADMX file, follow these steps:</span></span>

1. <span data-ttu-id="148cb-311">从 [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)下载 Microsoft Edge 策略模板文件 (MicrosoftEdgePolicyTemplates.cab)，然后提取内容。</span><span class="sxs-lookup"><span data-stu-id="148cb-311">Download the Microsoft Edge policy templates file (MicrosoftEdgePolicyTemplates.cab) from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise) and extract the contents.</span></span> <span data-ttu-id="148cb-312">你想要引入的文件是 **msedge.admx**。</span><span class="sxs-lookup"><span data-stu-id="148cb-312">The file that you want to ingest is **msedge.admx**.</span></span>
2. <span data-ttu-id="148cb-313">登录到 [Microsoft Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="148cb-313">Sign in to the [Microsoft Azure portal](https://portal.azure.com).</span></span>
3. <span data-ttu-id="148cb-314">从**所有服务**中选择 _Intune_，或在门户搜索框中搜索 Intune。</span><span class="sxs-lookup"><span data-stu-id="148cb-314">Select **Intune** from _All Services_, or search for Intune in the portal search box.</span></span>
4. <span data-ttu-id="148cb-315">从 _Microsoft Intune - 概述_中，选择**设备配置** | **配置文件**。</span><span class="sxs-lookup"><span data-stu-id="148cb-315">From _Microsoft Intune - Overview_, select **Device configuration** | **Profiles**.</span></span>
5. <span data-ttu-id="148cb-316">在顶部命令栏中，选择 **+ 创建配置文件**。</span><span class="sxs-lookup"><span data-stu-id="148cb-316">On the top command bar, select **+ Create profile**.</span></span>

   ![创建设备配置文件](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile.png)

6. <span data-ttu-id="148cb-318">提供以下配置文件信息：</span><span class="sxs-lookup"><span data-stu-id="148cb-318">Provide the following profile information:</span></span>

   - <span data-ttu-id="148cb-319">**名称**：输入描述性名称。</span><span class="sxs-lookup"><span data-stu-id="148cb-319">**Name**: Enter a descriptive name.</span></span> <span data-ttu-id="148cb-320">在此示例中，描述性名称为“Microsoft Edge ADMX 引入了配置”。</span><span class="sxs-lookup"><span data-stu-id="148cb-320">For this example, "Microsoft Edge ADMX ingested configuration".</span></span>
   - <span data-ttu-id="148cb-321">**描述**：为此配置文件输入可选描述。</span><span class="sxs-lookup"><span data-stu-id="148cb-321">**Description**: Enter an optional description for the profile.</span></span>
   - <span data-ttu-id="148cb-322">**平台**：选择“Windows 10 和更高版本”</span><span class="sxs-lookup"><span data-stu-id="148cb-322">**Platform**: Select "Windows 10 and later"</span></span>
   - <span data-ttu-id="148cb-323">**配置文件类型**：选择“自定义”</span><span class="sxs-lookup"><span data-stu-id="148cb-323">**Profile type**: Select "Custom"</span></span>

7. <span data-ttu-id="148cb-324">在**自定义 OMA-URI 设置**中，单击**添加**以添加 ADMX 引入。</span><span class="sxs-lookup"><span data-stu-id="148cb-324">On **Custom OMA-URI Settings**, click **Add** to add an ADMX ingestion.</span></span>

   ![为 OMA-URI 添加引入](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile-add-omauri.png)

8. <span data-ttu-id="148cb-326">在**添加行**上，提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="148cb-326">On **Add Row**, provide the following information:</span></span>

   - <span data-ttu-id="148cb-327">**名称**：输入描述性名称。</span><span class="sxs-lookup"><span data-stu-id="148cb-327">**Name**: Enter a descriptive name.</span></span> <span data-ttu-id="148cb-328">在此示例中，使用“Microsoft Edge ADMX 引入”。</span><span class="sxs-lookup"><span data-stu-id="148cb-328">For this example, use "Microsoft Edge ADMX ingestion".</span></span>
   - <span data-ttu-id="148cb-329">**描述**：为设置输入可选描述。</span><span class="sxs-lookup"><span data-stu-id="148cb-329">**Description**: Enter an optional description for the setting.</span></span>
   - <span data-ttu-id="148cb-330">**OMA-URI**：输入“*/Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/Edge/Policy/EdgeAdmx*”</span><span class="sxs-lookup"><span data-stu-id="148cb-330">**OMA-URI**: Enter "*./Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/Edge/Policy/EdgeAdmx*"</span></span>
   - <span data-ttu-id="148cb-331">**数据类型**：选择“字符串”</span><span class="sxs-lookup"><span data-stu-id="148cb-331">**Data type**: Select "String"</span></span>
   - <span data-ttu-id="148cb-332">**值**：选择**数据类型**后，将显示此输入区域。</span><span class="sxs-lookup"><span data-stu-id="148cb-332">**Value**: This input area appears after you select the **Data type**.</span></span> <span data-ttu-id="148cb-333">从你在第 1 步中提取的 Microsoft Edge 策略模板文件中打开 msedge.admx 文件。</span><span class="sxs-lookup"><span data-stu-id="148cb-333">Open the msedge.admx file from the Microsoft Edge policy templates file you extracted in step 1.</span></span> <span data-ttu-id="148cb-334">从 msedge.admx 文件中复制**所有文本**，然后将其粘贴到以下屏幕截图中显示的**值**文本区域中。</span><span class="sxs-lookup"><span data-stu-id="148cb-334">Copy **ALL the text** from the msedge.admx file and paste it in the **Value** text area shown in the following screenshot.</span></span>

        ![添加 ADMX 引入](./media/edge-cfg-with-mdm/configure-edge-intune-mdm-omauri-addrow-ingest.png)

   - <span data-ttu-id="148cb-336">单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="148cb-336">Click **OK**.</span></span>

9. <span data-ttu-id="148cb-337">在**自定义 OMA-URI 设置**上，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="148cb-337">On **Custom OMA-URI Settings**, click **OK**.</span></span>
10. <span data-ttu-id="148cb-338">在**创建配置文件**上，单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="148cb-338">On **Create profile**, click **Create**.</span></span> <span data-ttu-id="148cb-339">下一张屏幕截图显示有关新创建的配置文件的信息。</span><span class="sxs-lookup"><span data-stu-id="148cb-339">The next screenshot shows information about the newly created profile.</span></span>

    ![<span data-ttu-id="148cb-340">新设备配置文件信息</span><span class="sxs-lookup"><span data-stu-id="148cb-340">New device profile information</span></span> ](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile-done.png)

<!--
> [!NOTE]
> You can use the preceding steps to ingest the msedgeupate.admx policy template file.
-->
### <a name="set-a-policy-using-custom-oma-uri-in-intune"></a><span data-ttu-id="148cb-341">在 Intune 中使用自定义 OMA-URI 设置策略</span><span class="sxs-lookup"><span data-stu-id="148cb-341">Set a policy using custom OMA-URI in Intune</span></span>

> [!NOTE]
> <span data-ttu-id="148cb-342">在执行此部分中的步骤之前，必须完成[将 Microsoft Edge ADMX 文件引入到 Intune 中](#ingest-the-microsoft-edge-admx-file-into-intune)中描述的步骤。</span><span class="sxs-lookup"><span data-stu-id="148cb-342">Before using the steps in this section you must complete the steps described in [Ingest the Microsoft Edge ADMX file into Intune](#ingest-the-microsoft-edge-admx-file-into-intune).</span></span>

1. <span data-ttu-id="148cb-343">登录到 [Microsoft Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="148cb-343">Sign in to the [Microsoft Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="148cb-344">从**所有服务**中选择 _Intune_，或在门户搜索框中搜索 Intune。</span><span class="sxs-lookup"><span data-stu-id="148cb-344">Select **Intune** from _All Services_, or search for Intune in the portal search box.</span></span>
3. <span data-ttu-id="148cb-345">转到 **Intune**>**设备配置**>**配置文件**。</span><span class="sxs-lookup"><span data-stu-id="148cb-345">Go to **Intune**>**Device configuration**>**Profiles**.</span></span>
4. <span data-ttu-id="148cb-346">选择“Microsoft Edge ADMX 引入了配置”配置文件或用于此配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="148cb-346">Select the "Microsoft Edge ADMX ingested configuration" profile or the name you used for the profile.</span></span>
5. <span data-ttu-id="148cb-347">若要添加 Microsoft Edge 策略设置，你必须打开**自定义 OMA-URI 设置**。</span><span class="sxs-lookup"><span data-stu-id="148cb-347">To add Microsoft Edge policy settings, you have to open **Custom OMA-URI Settings**.</span></span> <span data-ttu-id="148cb-348">在**管理**下面，依次单击**属性**和**设置**。</span><span class="sxs-lookup"><span data-stu-id="148cb-348">Under **Manage**, click **Properties**, and then click **Settings**.</span></span>

    ![配置配置文件设置](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-add-policy-settings.png)

6. <span data-ttu-id="148cb-350">在**自定义 OMA-URI 设置**上，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="148cb-350">On **Custom OMA-URI Settings**, click **Add**.</span></span>

    ![向 OMA-URI 设置添加行](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-add-policy-settings-add-row.png)

7. <span data-ttu-id="148cb-352">在**添加行**上，提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="148cb-352">On **Add Row**, provide the following information:</span></span>

   - <span data-ttu-id="148cb-353">**名称**：输入描述性名称。</span><span class="sxs-lookup"><span data-stu-id="148cb-353">**Name**: Enter a descriptive name.</span></span> <span data-ttu-id="148cb-354">我们建议使用要配置的策略名称。</span><span class="sxs-lookup"><span data-stu-id="148cb-354">We suggest using the policy name you want to configure.</span></span> <span data-ttu-id="148cb-355">在此示例中，请使用“ShowHomeButton”。</span><span class="sxs-lookup"><span data-stu-id="148cb-355">For this example, use "ShowHomeButton".</span></span>
   - <span data-ttu-id="148cb-356">**描述**（可选）：为设置输入描述。</span><span class="sxs-lookup"><span data-stu-id="148cb-356">**Description** (Optional): Enter a description for the setting.</span></span>
   - <span data-ttu-id="148cb-357">**OMA-URI**：针对策略输入 OMA-URI。</span><span class="sxs-lookup"><span data-stu-id="148cb-357">**OMA-URI**: Enter the OMA-URI for the policy.</span></span> <span data-ttu-id="148cb-358">以“ShowHomeButton”策略为例，请使用此字符串：“*./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/ShowHomeButton*”</span><span class="sxs-lookup"><span data-stu-id="148cb-358">Using the for "ShowHomeButton" policy as an example, use this string: "*./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/ShowHomeButton*"</span></span>
   - <span data-ttu-id="148cb-359">**数据类型**：选择策略设置数据类型。</span><span class="sxs-lookup"><span data-stu-id="148cb-359">**Data type**: Select the policy settings data type.</span></span> <span data-ttu-id="148cb-360">对于“ShowHomeButton”策略，请使用“字符串”</span><span class="sxs-lookup"><span data-stu-id="148cb-360">For the "ShowHomeButton" policy, use "String"</span></span>
   - <span data-ttu-id="148cb-361">**值**：输入要为策略配置的设置。</span><span class="sxs-lookup"><span data-stu-id="148cb-361">**Value**: Enter the setting that you want to configure for the policy.</span></span> <span data-ttu-id="148cb-362">对于“ShowHomeButton”示例，请输入“\<enabled/>”。</span><span class="sxs-lookup"><span data-stu-id="148cb-362">For "ShowHomeButton" example, enter "\<enabled/>".</span></span> <span data-ttu-id="148cb-363">下面的屏幕截图显示了用于配置策略的设置。</span><span class="sxs-lookup"><span data-stu-id="148cb-363">The following screenshot shows the settings for configuring a policy.</span></span>

        ![添加“自定义 OMA-URI 设置”行](./media/edge-cfg-with-mdm/configure-edge-mdm-custom-omauri-setting.png)

   - <span data-ttu-id="148cb-365">单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="148cb-365">Click **OK**.</span></span>

8. <span data-ttu-id="148cb-366">在**自定义 OMA-URI 设置**上，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="148cb-366">On **Custom OMA-URI Settings**, click **OK**.</span></span>
9. <span data-ttu-id="148cb-367">在 **Microsoft Edge ADMX 引入了配置 - 属性**配置文件（或你使用的名称）上，单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="148cb-367">On the "**Microsoft Edge ADMX ingested configuration - Properties**" profile (or the name you used), click **Save**.</span></span>

<span data-ttu-id="148cb-368">创建配置文件并设置属性后，必须[在 Microsoft Intune 中分配配置文件](/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="148cb-368">After the profile is created and the properties set, you have to [assign the profile in Microsoft Intune](/intune/configuration/device-profile-assign).</span></span>

#### <a name="confirm-that-the-policy-was-set"></a><span data-ttu-id="148cb-369">确认策略已设置</span><span class="sxs-lookup"><span data-stu-id="148cb-369">Confirm that the policy was set</span></span>

<span data-ttu-id="148cb-370">使用以下步骤确认 Microsoft Edge 策略正在使用你创建的配置文件。</span><span class="sxs-lookup"><span data-stu-id="148cb-370">Use the following steps to confirm that the Microsoft Edge policy is using the profile you created.</span></span> <span data-ttu-id="148cb-371">（给 Microsoft Intune 一些时间，以将策略传播到你在“Microsoft Edge ADMX 引入了配置”配置文件示例中分配的设备。）</span><span class="sxs-lookup"><span data-stu-id="148cb-371">(Give Microsoft Intune time to propagate the policy to a device you assigned in the "Microsoft Edge ADMX ingested configuration" profile example.)</span></span>

1. <span data-ttu-id="148cb-372">打开 Microsoft Edge，然后转到 *edge://policy*。</span><span class="sxs-lookup"><span data-stu-id="148cb-372">Open Microsoft Edge and go to *edge://policy*.</span></span>
2. <span data-ttu-id="148cb-373">在**策略**页上，查看是否已列出你在配置文件中设置的策略。</span><span class="sxs-lookup"><span data-stu-id="148cb-373">On the **Policies** page, see if the policy you set in the profile is listed.</span></span>
3. <span data-ttu-id="148cb-374">如果未显示你的策略，请参阅[诊断 Windows 10 中的 MDM 故障](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10)或[策略设置疑难解答](#troubleshoot-a-policy-setting)。</span><span class="sxs-lookup"><span data-stu-id="148cb-374">If your policy isn't shown, see [Diagnose MDM failures in Windows 10](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) or [Troubleshoot a policy setting](#troubleshoot-a-policy-setting).</span></span>

#### <a name="troubleshoot-a-policy-setting"></a><span data-ttu-id="148cb-375">策略设置疑难解答</span><span class="sxs-lookup"><span data-stu-id="148cb-375">Troubleshoot a policy setting</span></span>

<span data-ttu-id="148cb-376">如果 Microsoft Edge 策略未生效，请尝试执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="148cb-376">If a Microsoft Edge policy isn’t taking effect, try the following steps:</span></span>

<span data-ttu-id="148cb-377">在目标设备（你在 Microsoft Intune 中将配置文件分配到的设备）上打开 *edge://policy* 页面，然后搜索该策略。</span><span class="sxs-lookup"><span data-stu-id="148cb-377">Open the *edge://policy* page on the target device (a device you assigned the profile to in Microsoft Intune) and search for the policy.</span></span> <span data-ttu-id="148cb-378">如果该策略未在 *edge://policy* 页面上，请尝试以下操作：</span><span class="sxs-lookup"><span data-stu-id="148cb-378">If the policy isn’t on the *edge://policy* page, try the following:</span></span>

- <span data-ttu-id="148cb-379">检查该策略是否在注册表中并且正确无误。</span><span class="sxs-lookup"><span data-stu-id="148cb-379">Check that the policy is in the registry and is correct.</span></span> <span data-ttu-id="148cb-380">在目标设备上，打开 Windows 10 注册表编辑器（**Windows 键 + r**，输入“*regedit*”，然后按 **Enter**）。检查是否在 *\Software\Policies\ Microsoft\Edge* 路径中正确定义了此策略。</span><span class="sxs-lookup"><span data-stu-id="148cb-380">On the target device open the Windows 10 Registry Editor (**Windows key + r**, enter “*regedit*” and then press **Enter**.) Check that the policy is correctly defined in the *\Software\Policies\ Microsoft\Edge* path.</span></span> <span data-ttu-id="148cb-381">如果未在预期路径中找到此策略，则不会正确地将策略推送到设备。</span><span class="sxs-lookup"><span data-stu-id="148cb-381">If you don’t find the policy in the expected path, then the policy wasn’t pushed to the device correctly.</span></span>
- <span data-ttu-id="148cb-382">请检查 OMA-URI 路径是否正确，并且该值是否为有效的 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="148cb-382">Check that the OMA-URI path is correct, and the value is a valid XML string.</span></span> <span data-ttu-id="148cb-383">如果其中任何一个不正确，则不会将策略推送到目标设备。</span><span class="sxs-lookup"><span data-stu-id="148cb-383">If either of these are incorrect the policy won’t be pushed to the target device.</span></span>

<span data-ttu-id="148cb-384">有关更多疑难解答提示，请参阅[设置 Microsoft Intune](/intune/fundamentals/setup-steps) 和[同步设备](/intune/remote-actions/device-sync)。</span><span class="sxs-lookup"><span data-stu-id="148cb-384">For more trouble shooting tips, see [Set up Microsoft Intune](/intune/fundamentals/setup-steps) and [Sync devices](/intune/remote-actions/device-sync).</span></span>

## <a name="see-also"></a><span data-ttu-id="148cb-385">另请参阅</span><span class="sxs-lookup"><span data-stu-id="148cb-385">See also</span></span>

- [<span data-ttu-id="148cb-386">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="148cb-386">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="148cb-387">使用 Microsoft Intune 配置 Microsoft Edge 策略设置</span><span class="sxs-lookup"><span data-stu-id="148cb-387">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>](configure-edge-with-intune.md)
- [<span data-ttu-id="148cb-388">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="148cb-388">Mobile device management</span></span>](/windows/client-management/mdm/)
- [<span data-ttu-id="148cb-389">在 Intune 中对 Windows 10 设备使用自定义设置</span><span class="sxs-lookup"><span data-stu-id="148cb-389">Use custom settings for Windows 10 devices in Intune</span></span>](/intune/configuration/custom-settings-windows-10)
- [<span data-ttu-id="148cb-390">Win32 和桌面桥应用策略配置</span><span class="sxs-lookup"><span data-stu-id="148cb-390">Win32 and Desktop Bridge app policy configuration</span></span>](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration)
- [<span data-ttu-id="148cb-391">了解 ADMX 支持的策略</span><span class="sxs-lookup"><span data-stu-id="148cb-391">Understanding ADMX-backed policies</span></span>](/windows/client-management/mdm/understanding-admx-backed-policies)