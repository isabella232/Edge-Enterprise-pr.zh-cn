---
title: 使用组策略管理 Microsoft Edge 扩展
ms.author: aspoddar
author: AndreaLBarr
manager: balajek
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 使用组策略在企业中管理 Microsoft Edge 扩展
ms.openlocfilehash: dad239a448ec1f0ebef60c7072bfaad5c3baed57
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641368"
---
# <a name="use-group-policies-to-manage-microsoft-edge-extensions"></a><span data-ttu-id="3e810-103">使用组策略管理 Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="3e810-103">Use group policies to manage Microsoft Edge extensions</span></span>

<span data-ttu-id="3e810-104">本文介绍通过使用组策略管理扩展的选项和步骤。</span><span class="sxs-lookup"><span data-stu-id="3e810-104">This article describes the options and steps for managing extensions by using group policies.</span></span> <span data-ttu-id="3e810-105">这些选项假定你已为用户管理 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="3e810-105">These options  assume that you already have Microsoft Edge managed for your users.</span></span> <span data-ttu-id="3e810-106">如果尚未设置要为用户管理的 Microsoft Edge，请单击以下链接以立即执行此操作。</span><span class="sxs-lookup"><span data-stu-id="3e810-106">If you have not already set up Microsoft Edge to be managed for your users please follow the below link to do so now.</span></span>

- [<span data-ttu-id="3e810-107">在企业中管理 Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="3e810-107">Manage Microsoft Edge extensions in the enterprise</span></span>](/deployedge/microsoft-edge-manage-extensions)

> [!NOTE]
> <span data-ttu-id="3e810-108">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="3e810-108">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="block-extensions-based-on-their-permissions"></a><span data-ttu-id="3e810-109">基于其权限阻止扩展</span><span class="sxs-lookup"><span data-stu-id="3e810-109">Block extensions based on their permissions</span></span>

<span data-ttu-id="3e810-110">可以使用 [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) 策略来根据权限控制用户可以安装的扩展。</span><span class="sxs-lookup"><span data-stu-id="3e810-110">You can control what extensions your users can install based on permissions using the [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) policy.</span></span> <span data-ttu-id="3e810-111">如果已安装的扩展需要被阻止的权限，它将不会运行。</span><span class="sxs-lookup"><span data-stu-id="3e810-111">If an installed extension needs a permission that’s blocked, it just won't run.</span></span> <span data-ttu-id="3e810-112">该扩展不会被删除，只是被禁用。</span><span class="sxs-lookup"><span data-stu-id="3e810-112">The extension isn't removed, just disabled.</span></span>

> [!NOTE]
> <span data-ttu-id="3e810-113">只能在扩展设置策略中设置受阻止的权限设置。</span><span class="sxs-lookup"><span data-stu-id="3e810-113">The blocked permissions setting can only be set within the extension settings policy.</span></span>  

<span data-ttu-id="3e810-114">请使用以下步骤作为阻止扩展的指南。</span><span class="sxs-lookup"><span data-stu-id="3e810-114">Use the following steps as a guide for blocking an extension.</span></span>

1. <span data-ttu-id="3e810-115">打开组策略管理编辑器并转到“**管理模板”>“Microsoft Edge”>“扩展**”，然后选择“**配置扩展管理设置**”。</span><span class="sxs-lookup"><span data-stu-id="3e810-115">Open the group policy management editor and go to **Administrative Templates > Microsoft Edge > Extensions**  and then select **Configure extension management settings**.</span></span>
2. <span data-ttu-id="3e810-116">启用策略，然后通过使用经过压缩的 JSON 字符串输入要允许或阻止的权限。</span><span class="sxs-lookup"><span data-stu-id="3e810-116">Enable the policy, then enter the permissions that you want allowed or blocked, by using a JSON string that gets compressed.</span></span> <span data-ttu-id="3e810-117">下一个屏幕截图显示了如何阻止使用权限“usb”的扩展。</span><span class="sxs-lookup"><span data-stu-id="3e810-117">The next screenshot shows how to block an extension that uses the permission "usb".</span></span>

    :::image type="content" source="media/microsoft-edge-manage-extensions-policies/manage-extensions-gp-block-1.png" alt-text="配置组策略以阻止扩展。":::

<span data-ttu-id="3e810-119">下面的示例演示了用于阻止任何需要使用权限“usb”及其压缩字符串的扩展的 JSON。</span><span class="sxs-lookup"><span data-stu-id="3e810-119">The following example shows the JSON to block any extension that needs the use of permission "usb" and its compressed string.</span></span>

### <a name="json-example"></a><span data-ttu-id="3e810-120">JSON 示例：</span><span class="sxs-lookup"><span data-stu-id="3e810-120">JSON example</span></span>

   ```json
   { 
        "*": { 
             "blocked_permissions": ["usb"] 
        } 
   } 
   ```

   ```json
   {"*":{"blocked_permissions":["usb"]}} 
   ```

   > [!NOTE]
   > <span data-ttu-id="3e810-121">要阻止使用该权限的所有扩展，请将星号用于扩展 ID，如前面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="3e810-121">To block all extensions that use the permission, use an asterisk for the extension ID, as shown in the previous example.</span></span> <span data-ttu-id="3e810-122">如果指定一个扩展 ID，则该策略将仅应用于该扩展。</span><span class="sxs-lookup"><span data-stu-id="3e810-122">If you specify one extension ID, the policy will only apply to that extension.</span></span> <span data-ttu-id="3e810-123">可以阻止多个条目，但它们必须是单独的条目。</span><span class="sxs-lookup"><span data-stu-id="3e810-123">You can block more than one, but they need to be separate entries.</span></span>

## <a name="prevent-extensions-from-altering-web-pages"></a><span data-ttu-id="3e810-124">阻止扩展更改网页</span><span class="sxs-lookup"><span data-stu-id="3e810-124">Prevent extensions from altering web pages</span></span>

<span data-ttu-id="3e810-125">此设置防止扩展读取和更改敏感网站和域中的数据。</span><span class="sxs-lookup"><span data-stu-id="3e810-125">This setting prevents extensions from reading and changing  data from sensitive websites and domains.</span></span> <span data-ttu-id="3e810-126">阻止不需要的操作是通过阻止操作（如脚本注入网站、读取 Cookie 或进行 Web 请求修改）来完成的。</span><span class="sxs-lookup"><span data-stu-id="3e810-126">Blocking unwanted actions is done by blocking actions such as script injection into your websites, reading the cookies, or making web-request modifications.</span></span> <span data-ttu-id="3e810-127">此设置不阻止用户安装或删除扩展，仅阻止扩展更改指定的网站。</span><span class="sxs-lookup"><span data-stu-id="3e810-127">This setting doesn’t prevent your users from installing or removing extensions, it only prevents extensions from altering the specified websites.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3e810-128">只能在扩展设置策略中设置运行时允许/阻止的主机设置。</span><span class="sxs-lookup"><span data-stu-id="3e810-128">The Runtime allowed/blocked hosts setting can only be set within the extension settings policy.</span></span>  

<span data-ttu-id="3e810-129">可以在 ExtensionSettings 策略中配置以下设置，以防止（或允许）网站或域的更改：</span><span class="sxs-lookup"><span data-stu-id="3e810-129">You can configure the following settings in the ExtensionSettings policy to prevent (or allow) alterations of websites or domains:</span></span>

- <span data-ttu-id="3e810-130">**Runtime_blocked_hosts**。</span><span class="sxs-lookup"><span data-stu-id="3e810-130">**Runtime_blocked_hosts**.</span></span> <span data-ttu-id="3e810-131">此设置阻止扩展从指定的网站进行更改或读取数据。</span><span class="sxs-lookup"><span data-stu-id="3e810-131">This setting blocks extensions from making changes or reading data from the websites you specify.</span></span>
- <span data-ttu-id="3e810-132">**Runtime_allowed_hosts**。</span><span class="sxs-lookup"><span data-stu-id="3e810-132">**Runtime_allowed_hosts**.</span></span> <span data-ttu-id="3e810-133">此设置允许扩展从指定的网站进行更改或读取数据。</span><span class="sxs-lookup"><span data-stu-id="3e810-133">This setting allows extensions to make changes or read data from the websites you specify.</span></span> <span data-ttu-id="3e810-134">以下格式用于在策略的 JSON 字符串中指定网站：</span><span class="sxs-lookup"><span data-stu-id="3e810-134">The following format is used for specifying your site(s) in the JSON string in the policy:</span></span>

  ```json
  [http|https|ftp|*]://[subdomain|*].[hostname|*].[eTLD|*] [http|https|ftp|*],
  ```

  > [!NOTE]
  > `[hostname|*], and [eTLD|*]` <span data-ttu-id="3e810-135">节是必需的，但 `[subdomain|*]` 节则是可选的。</span><span class="sxs-lookup"><span data-stu-id="3e810-135">sections are required, but `[subdomain|*]` section is optional.</span></span>

<span data-ttu-id="3e810-136">下表显示了有效的主机模式和匹配模式的示例。</span><span class="sxs-lookup"><span data-stu-id="3e810-136">The following table shows examples of valid host patterns and matching patterns.</span></span>

|<span data-ttu-id="3e810-137">有效的主机模式</span><span class="sxs-lookup"><span data-stu-id="3e810-137">Valid host patterns</span></span>|<span data-ttu-id="3e810-138">匹配</span><span class="sxs-lookup"><span data-stu-id="3e810-138">Matches</span></span>|<span data-ttu-id="3e810-139">不匹配</span><span class="sxs-lookup"><span data-stu-id="3e810-139">Doesn't match</span></span>|
|--|--|--|
|  `*://*.example.*` | `http://example.com`<br>`https://test.example.co.uk`   | `https://example.microsoft.com`<br>`http://example.microsoft.co.uk`  |
| `http://example.*` | `http://example.com`<br>`http://example.ly` | `https://example.com`<br>`http://test.example.com`   |
| `http://example.com`   | `http://example.com` | `https://example.com`<br>`http://test.example.co.uk` |
| `*://*`   | <span data-ttu-id="3e810-140">所有 URL</span><span class="sxs-lookup"><span data-stu-id="3e810-140">All URLs</span></span>  |   |

<span data-ttu-id="3e810-141">使用以下步骤作为指南来阻止或允许扩展访问网站或域。</span><span class="sxs-lookup"><span data-stu-id="3e810-141">Use the following steps as a guide to block or allow extensions to access a website or domain.</span></span>

1. <span data-ttu-id="3e810-142">打开组策略管理编辑器，并转到“**管理模板”>“Microsoft Edge”>“扩展**”，然后选择“**配置扩展管理设置**。</span><span class="sxs-lookup"><span data-stu-id="3e810-142">Open the group policy management editor and go to **Administrative Templates > Microsoft Edge > Extensions**, and then select **Configure extension management settings**.</span></span>  
2. <span data-ttu-id="3e810-143">启用策略，然后输入要允许或阻止的权限，将权限压缩为单个 JSON 字符串。</span><span class="sxs-lookup"><span data-stu-id="3e810-143">Enable the policy, then enter the permissions that you want allowed or blocked, compressing the permissions to a single JSON string.</span></span>

<span data-ttu-id="3e810-144">以下示例演示如何阻止主机名上的扩展以及如何阻止同一域上的扩展。</span><span class="sxs-lookup"><span data-stu-id="3e810-144">The following examples show how to block extensions on a hostname and how to block extensions on the same domain.</span></span>

### <a name="json-example-to-block-hostname"></a><span data-ttu-id="3e810-145">用于阻止主机名的 JSON 示例</span><span class="sxs-lookup"><span data-stu-id="3e810-145">JSON example to block hostname</span></span>

<span data-ttu-id="3e810-146">此示例显示 JSON 和压缩的 JSON 字符串，用于阻止任何扩展访问 `www.microsoft.com` 主机名。</span><span class="sxs-lookup"><span data-stu-id="3e810-146">This example shows the JSON and compressed JSON string to block any extension from accessing the `www.microsoft.com` hostname.</span></span>

```json
{ 
    "*":{ 
            "runtime_blocked_hosts":["www.microsoft.com"] 
    } 
} 
```

```json
{"*":{"runtime_blocked_hosts":["www.microsoft.com"]}} 
```

> [!NOTE]
> <span data-ttu-id="3e810-147">要阻止所有扩展访问网页，请将星号用于扩展 ID，如前面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="3e810-147">To block all extensions from accessing a webpage, use an asterisk for the extension ID, as shown in the previous example.</span></span>  <span data-ttu-id="3e810-148">如果指定一个扩展 ID 而不是星号，则策略将仅应用于该扩展。</span><span class="sxs-lookup"><span data-stu-id="3e810-148">If you specify one extension ID instead of an asterisk, the policy will only apply to that extension.</span></span> <span data-ttu-id="3e810-149">可以阻止多个扩展，但它们必须是单独的条目。</span><span class="sxs-lookup"><span data-stu-id="3e810-149">You can block more than one extension, but they need to be separate entries.</span></span>

### <a name="json-example-to-block-extensions-on-same-domain"></a><span data-ttu-id="3e810-150">用于阻止同一域上的扩展的 JSON 示例</span><span class="sxs-lookup"><span data-stu-id="3e810-150">JSON example to block extensions on same domain</span></span>

<span data-ttu-id="3e810-151">此示例显示 JSON 和压缩的 JSON 字符串，用于阻止特定扩展在相同的域“importantwebsite”上运行。</span><span class="sxs-lookup"><span data-stu-id="3e810-151">This example shows the JSON and compressed JSON string to block specific extensions from running on the same domain, "importantwebsite".</span></span>

```json
{ 
    "aapbdbdomjkkjkaonfhkkikfgjllcleb": { 
        "runtime_blocked_hosts": ["*://*.importantwebsite"] 
    }, 
    "bfbmjmiodbnnpllbbbfblcplfjjepjdn": { 
        "runtime_blocked_hosts": ["*://*.importantwebsite"] 
    } 
} 
```

```json
{"aapbdbdomjkkjkaonfhkkikfgjllcleb": {"runtime_blocked_hosts": ["*://,*.importantwebsite"]},"bfbmjmiodbnnpllbbbfblcplfjjepjdn": {"runtime_blocked_hosts": ["*://*.importantwebsite"]}} 
```

## <a name="allow-or-block-extensions-in-group-policy"></a><span data-ttu-id="3e810-152">允许或阻止组策略中的扩展</span><span class="sxs-lookup"><span data-stu-id="3e810-152">Allow or block extensions in group policy</span></span>

<span data-ttu-id="3e810-153">可以使用 [ExtensionInstallBlocklist](/DeployEdge/microsoft-edge-policies#extensioninstallblocklist) 和 [ExtensionInstallAllowlist](/DeployEdge/microsoft-edge-policies#extensioninstallallowlist) 策略来控制阻止或允许哪些扩展。</span><span class="sxs-lookup"><span data-stu-id="3e810-153">You can use the [ExtensionInstallBlocklist](/DeployEdge/microsoft-edge-policies#extensioninstallblocklist) and [ExtensionInstallAllowlist](/DeployEdge/microsoft-edge-policies#extensioninstallallowlist) policies to control which extensions are blocked or allowed.</span></span> <span data-ttu-id="3e810-154">使用以下步骤作为指南，允许除要阻止的扩展之外的所有扩展。</span><span class="sxs-lookup"><span data-stu-id="3e810-154">Use the following steps as a guide to allow all extensions except those you want to block.</span></span>

1. <span data-ttu-id="3e810-155">打开组策略管理编辑器，并转到“**管理模板”>“Microsoft Edge”>“扩展**”，然后选择“**控制哪些应用不可以安装**。</span><span class="sxs-lookup"><span data-stu-id="3e810-155">Open the group policy management editor and go to **Administrative Templates > Microsoft Edge > Extensions >** and then select **Control which extensions cannot be installed**.</span></span>
2. <span data-ttu-id="3e810-156">选择“**已启用**”。</span><span class="sxs-lookup"><span data-stu-id="3e810-156">Select **Enabled**.</span></span>
3. <span data-ttu-id="3e810-157">单击“**显示**”。</span><span class="sxs-lookup"><span data-stu-id="3e810-157">Click **Show**.</span></span>
4. <span data-ttu-id="3e810-158">输入要阻止的扩展的应用 ID。</span><span class="sxs-lookup"><span data-stu-id="3e810-158">Enter the app ID of the extensions that you want to block.</span></span> <span data-ttu-id="3e810-159">添加多个应用 ID 时，请对每个 ID 使用单独的行。</span><span class="sxs-lookup"><span data-stu-id="3e810-159">When adding multiple app ID’s use a separate row for each ID.</span></span>
5. <span data-ttu-id="3e810-160">若要阻止所有扩展，在策略中键入 \* *\** _ 以防止安装任何扩展。</span><span class="sxs-lookup"><span data-stu-id="3e810-160">To block all extensions, type \**\**_ into the policy to prevent any extensions from being installed.</span></span> <span data-ttu-id="3e810-161">可以将此项与“允许安装特定扩展”策略结合使用，以仅允许安装某些扩展。</span><span class="sxs-lookup"><span data-stu-id="3e810-161">You can use this in conjunction with the "Allow specific extensions to be installed" policy to only allow certain extensions to be installed.</span></span> <span data-ttu-id="3e810-162">下一个屏幕截图显示将基于提供的应用 ID 而阻止的扩展。</span><span class="sxs-lookup"><span data-stu-id="3e810-162">The next screenshot shows an extension that will be blocked based on the app ID that's provided.</span></span>

   :::image type="content" source="media/microsoft-edge-manage-extensions-policies/manage-extensions-gp-block-2.png" alt-text="使用应用 ID 阻止扩展。":::

   > [!TIP]
   > <span data-ttu-id="3e810-164">如果找不到扩展的应用 ID，请在 Microsoft Edge 加载项网站中查找扩展。</span><span class="sxs-lookup"><span data-stu-id="3e810-164">If you can’t find the app ID of an extension, look at the extension in the Microsoft Edge Add-ons website.</span></span> <span data-ttu-id="3e810-165">找到特定扩展，然后你将在多功能框中的 URL 末尾看到应用 ID。</span><span class="sxs-lookup"><span data-stu-id="3e810-165">Find the specific extension and you will see the app ID at the end of the URL in the omnibox.</span></span>

> [!NOTE]
> <span data-ttu-id="3e810-166">可以将扩展添加到用户计算机上已安装的阻止列表。</span><span class="sxs-lookup"><span data-stu-id="3e810-166">You can add an extension to the blocklist that’s already installed on a user’s computer.</span></span> <span data-ttu-id="3e810-167">此操作将禁用扩展，并阻止用户重新启用它。</span><span class="sxs-lookup"><span data-stu-id="3e810-167">This will disable the extension and prevent the user from re-enabling it.</span></span> <span data-ttu-id="3e810-168">扩展不会卸载，而只是被禁用。</span><span class="sxs-lookup"><span data-stu-id="3e810-168">It won't be uninstalled, just disabled.</span></span>

## <a name="force-install-an-extension"></a><span data-ttu-id="3e810-169">强制安装扩展</span><span class="sxs-lookup"><span data-stu-id="3e810-169">Force-install an extension</span></span>

<span data-ttu-id="3e810-170">使用 [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist) 策略来控制阻止或允许哪些扩展。</span><span class="sxs-lookup"><span data-stu-id="3e810-170">Use the [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist) policy to control which extensions are blocked or allowed.</span></span> <span data-ttu-id="3e810-171">使用以下步骤作为指南以强制安装扩展。</span><span class="sxs-lookup"><span data-stu-id="3e810-171">Use the following steps as a guide to force-install an extension.</span></span>

1. <span data-ttu-id="3e810-172">在组策略编辑器中，转到 *_Administrative Templates> Microsoft Edge > Extensions >*\* ，然后选择控制以静默方式安装的**扩展**。</span><span class="sxs-lookup"><span data-stu-id="3e810-172">In the Group Policy Editor, go to _*Administrative Templates> Microsoft Edge >  Extensions >*\* and then select **Control which extensions are installed silently**.</span></span>
2. <span data-ttu-id="3e810-173">选择“**已启用**”。</span><span class="sxs-lookup"><span data-stu-id="3e810-173">Select **Enabled**.</span></span>  
3. <span data-ttu-id="3e810-174">单击“**显示**”。</span><span class="sxs-lookup"><span data-stu-id="3e810-174">Click **Show**.</span></span>
4. <span data-ttu-id="3e810-175">输入要强制安装的扩展的应用 ID。</span><span class="sxs-lookup"><span data-stu-id="3e810-175">Enter the app ID or IDs of the extension or extensions you want to force-install.</span></span>  

<span data-ttu-id="3e810-176">该扩展将以无提示方式安装，无需用户交互。</span><span class="sxs-lookup"><span data-stu-id="3e810-176">The extension will be installed silently with no need for user interaction.</span></span> <span data-ttu-id="3e810-177">用户也无法卸载或禁用扩展。</span><span class="sxs-lookup"><span data-stu-id="3e810-177">The user also won’t be able to uninstall or disable the extension.</span></span> <span data-ttu-id="3e810-178">此设置将覆盖已启用的任何阻止列表策略。</span><span class="sxs-lookup"><span data-stu-id="3e810-178">This setting will overwrite over any blocklist policy that’s enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="3e810-179">对于托管在 Chrome Web store 中的扩展，请使用以下字符串，如：`pckdojakecnhhplcgfflhndiffaohfah;https://clients2.google.com/service/update2/crx`。</span><span class="sxs-lookup"><span data-stu-id="3e810-179">For extensions hosted in the Chrome web store use a string such as: `pckdojakecnhhplcgfflhndiffaohfah;https://clients2.google.com/service/update2/crx`.</span></span>

## <a name="block-extensions-from-a-specific-store-or-update-url"></a><span data-ttu-id="3e810-180">阻止来自特定商店或更新 URL 的扩展</span><span class="sxs-lookup"><span data-stu-id="3e810-180">Block extensions from a specific store or update URL</span></span>

<span data-ttu-id="3e810-181">要阻止来自特定商店或 URL 的扩展，只需为该商店使用 [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) 策略来阻止 *update_url*。</span><span class="sxs-lookup"><span data-stu-id="3e810-181">To block extensions from a particular store or URL, you only need to block the *update_url* for that store using the [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) policy.</span></span>

<span data-ttu-id="3e810-182">使用以下步骤作为指南阻止来自特定商店或 URL 的扩展。</span><span class="sxs-lookup"><span data-stu-id="3e810-182">Use the following steps as a guide to block extensions from an particular store or URL.</span></span>

1. <span data-ttu-id="3e810-183">打开组策略管理编辑器并转到“**管理模板”>“Microsoft Edge”>“>扩展**”，然后选择“**配置扩展管理设置**。</span><span class="sxs-lookup"><span data-stu-id="3e810-183">Open the group policy management editor and go to **Administrative Templates > Microsoft Edge > Extensions >** and then select **Configure extension management settings**.</span></span>  
2. <span data-ttu-id="3e810-184">启用策略，然后输入要允许或阻止的权限，将其压缩为单个 JSON 字符串。</span><span class="sxs-lookup"><span data-stu-id="3e810-184">Enable the policy, then enter the permissions that you want allowed or blocked, compressing it to a single JSON string.</span></span>

<span data-ttu-id="3e810-185">下一个示例演示要使用其更新 URL（`https://clients2.google.com/service/update2/crx`）来阻止 Chrome Web Store 的 JSON 和压缩 JSON 字符串。</span><span class="sxs-lookup"><span data-stu-id="3e810-185">The next example shows the JSON and compressed JSON string to block from the Chrome Web Store using its update URL (`https://clients2.google.com/service/update2/crx`).</span></span>

### <a name="json-example-for-blocking-on-update-url"></a><span data-ttu-id="3e810-186">用于阻止更新 URL 的 JSON 示例</span><span class="sxs-lookup"><span data-stu-id="3e810-186">JSON example for blocking on update URL</span></span>

```json
{ 
"update_url:https://clients2.google.com/service/update2/crx":{ 
                                                             " installation_mode":"blocked" 
                                                             } 
} 
```

```json
{"update_url:https://clients2.google.com/service/update2/crx":{"installation_mode":"blocked"}} 
```

> [!NOTE]
> <span data-ttu-id="3e810-187">你仍然可以使用 **ExtensionInstallForcelist** 和 **ExtensionInstallAllowlist** 来允许/强制安装特定扩展，即使使用上一示例中的 JSON 阻止了商店。</span><span class="sxs-lookup"><span data-stu-id="3e810-187">You can still use **ExtensionInstallForceList** and **ExtensionInstallAllowList** to allow/force install specific extensions even if the store is blocked using the JSON in the previous example.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e810-188">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e810-188">See also</span></span>

- [<span data-ttu-id="3e810-189">在企业中管理 Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="3e810-189">Manage Microsoft Edge extensions in the enterprise</span></span>](microsoft-edge-manage-extensions.md)
- [<span data-ttu-id="3e810-190">创建用于托管 Microsoft Edge 扩展的 Web 应用商店</span><span class="sxs-lookup"><span data-stu-id="3e810-190">Create a web store to host Microsoft Edge extensions</span></span>](microsoft-edge-manage-extensions-webstore.md)
- [<span data-ttu-id="3e810-191">ExtensionSettings 策略参考指南</span><span class="sxs-lookup"><span data-stu-id="3e810-191">Reference guide for the ExtensionSettings policy</span></span>](microsoft-edge-manage-extensions-ref-guide.md)
- [<span data-ttu-id="3e810-192">Microsoft Edge 扩展的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="3e810-192">FAQ for Microsoft Edge Extensions</span></span>](microsoft-edge-manage-extensions-faq.md)
- [<span data-ttu-id="3e810-193">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="3e810-193">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
