---
title: ExtensionSettings 策略的详细指南
ms.author: aspoddar
author: dan-wesley
manager: balajek
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 有关使用 ExtensionSettings 策略配置 Microsoft Edge 扩展的详细参考指南。
ms.openlocfilehash: 3acd798be6b2b56761991d8adaf014ae614a3fd4
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641318"
---
# <a name="detailed-guide-to-the-extensionsettings-policy"></a><span data-ttu-id="5144b-103">ExtensionSettings 策略的详细指南</span><span class="sxs-lookup"><span data-stu-id="5144b-103">Detailed guide to the ExtensionSettings policy</span></span>

<span data-ttu-id="5144b-104">Microsoft Edge 提供了多种方法来管理扩展。</span><span class="sxs-lookup"><span data-stu-id="5144b-104">Microsoft Edge offers multiple ways to manage extensions.</span></span> <span data-ttu-id="5144b-105">一种常见方法是在 Windows 组策略编辑器或 Windows 注册表中使用 [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) 策略在一处通过 JSON 字符串设置多个策略。</span><span class="sxs-lookup"><span data-stu-id="5144b-105">A common way is to set multiple policies in one place with a JSON string in the Windows Group Policy Editor or in the Windows Registry using the [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) policy.</span></span>

> [!NOTE]
> <span data-ttu-id="5144b-106">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="5144b-106">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5144b-107">在你开始前</span><span class="sxs-lookup"><span data-stu-id="5144b-107">Before you begin</span></span>

<span data-ttu-id="5144b-108">你决定是要在此处设置所有扩展管理设置，还是通过其他策略设置这些控件。</span><span class="sxs-lookup"><span data-stu-id="5144b-108">You decide if you want to set all extension management settings here or set these controls through other policies.</span></span>
  
<span data-ttu-id="5144b-109">ExtensionSettings 策略可以覆盖已在组策略其他位置设置的其他策略，包括以下策略：</span><span class="sxs-lookup"><span data-stu-id="5144b-109">The ExtensionSettings policy can overwrite other policies that you've set elsewhere in group policy, including the following policies:</span></span>

- [<span data-ttu-id="5144b-110">ExtensionAllowedTypes</span><span class="sxs-lookup"><span data-stu-id="5144b-110">ExtensionAllowedTypes</span></span>](/DeployEdge/microsoft-edge-policies#extensionallowedtypes)
- [<span data-ttu-id="5144b-111">ExtensionInstallBlocklist</span><span class="sxs-lookup"><span data-stu-id="5144b-111">ExtensionInstallBlocklist</span></span>](/DeployEdge/microsoft-edge-policies#extensioninstallblocklist)
- [<span data-ttu-id="5144b-112">ExtensionInstallForcelist</span><span class="sxs-lookup"><span data-stu-id="5144b-112">ExtensionInstallForcelist</span></span>](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)
- [<span data-ttu-id="5144b-113">ExtensionInstallSources</span><span class="sxs-lookup"><span data-stu-id="5144b-113">ExtensionInstallSources</span></span>](/DeployEdge/microsoft-edge-policies#extensioninstallsources)
- [<span data-ttu-id="5144b-114">ExtensionInstallAllowlist</span><span class="sxs-lookup"><span data-stu-id="5144b-114">ExtensionInstallAllowlist</span></span>](/DeployEdge/microsoft-edge-policies#extensioninstallsources)

## <a name="extensionsettings-policy-fields"></a><span data-ttu-id="5144b-115">ExtensionSettings 策略字段</span><span class="sxs-lookup"><span data-stu-id="5144b-115">ExtensionSettings policy fields</span></span>

<span data-ttu-id="5144b-116">此策略可以控制更新 URL 等设置，从中下载扩展以进行初始安装，以及阻止权限，或不允许运行哪些权限。</span><span class="sxs-lookup"><span data-stu-id="5144b-116">This policy can control settings such as Update URL, where the extension will be downloaded from for initial install, and Blocked permissions, or which permissions aren't allowed to run.</span></span> <span data-ttu-id="5144b-117">下表描述了可用的策略字段。</span><span class="sxs-lookup"><span data-stu-id="5144b-117">The available policy fields are described in the following table.</span></span>

| &nbsp; | <span data-ttu-id="5144b-118">描述</span><span class="sxs-lookup"><span data-stu-id="5144b-118">Description</span></span> |
|--|--|
| **<span data-ttu-id="5144b-119">allowed_types</span><span class="sxs-lookup"><span data-stu-id="5144b-119">allowed_types</span></span>** | <span data-ttu-id="5144b-120">只能用于配置默认配置 \*。</span><span class="sxs-lookup"><span data-stu-id="5144b-120">Can only be used to configure the default configuration, \*.</span></span> <span data-ttu-id="5144b-121">指定允许用户在 Microsoft Edge 上安装的应用或扩展类型。</span><span class="sxs-lookup"><span data-stu-id="5144b-121">Specifies what types of app or extension users are allowed to install on Microsoft Edge.</span></span> <span data-ttu-id="5144b-122">该值为字符串列表，其中每个字符串应为以下类型之一："extension"、"theme"、"user_script" 和 "hosted_app"。</span><span class="sxs-lookup"><span data-stu-id="5144b-122">The value is a list of strings, each of which should be one of the following types: "extension", "theme", "user_script", and "hosted_app"</span></span>   |
| **<span data-ttu-id="5144b-123">blocked_install_message</span><span class="sxs-lookup"><span data-stu-id="5144b-123">blocked_install_message</span></span>**| <span data-ttu-id="5144b-124">如果阻止用户安装某些扩展，可以指定在用户尝试安装这些扩展时在浏览器中显示的自定义消息。</span><span class="sxs-lookup"><span data-stu-id="5144b-124">If you block users from installing certain extensions, you can specify a custom message to display in the browser if users try to install them.</span></span><br><span data-ttu-id="5144b-125">将文本追加到在 Microsoft Edge 加载项网站上显示的一般错误消息。</span><span class="sxs-lookup"><span data-stu-id="5144b-125">Append text to the generic error message that is displayed on the Microsoft Edge Add-ons website.</span></span> <span data-ttu-id="5144b-126">例如，你可以告诉用户如何联系其 IT 部门或特定扩展不可用的原因。</span><span class="sxs-lookup"><span data-stu-id="5144b-126">For example, you can tell users how to contact their IT department or why a particular extension is unavailable.</span></span> <span data-ttu-id="5144b-127">消息的长度最多可为 1000 个字符。</span><span class="sxs-lookup"><span data-stu-id="5144b-127">The message can be up to 1,000 characters long.</span></span>   |
|**<span data-ttu-id="5144b-128">blocked_permissions</span><span class="sxs-lookup"><span data-stu-id="5144b-128">blocked_permissions</span></span>**  | <span data-ttu-id="5144b-129">阻止用户安装和运行请求组织不允许的特定 API 权限的扩展。</span><span class="sxs-lookup"><span data-stu-id="5144b-129">Prevents users from installing and running extensions that request certain API permissions that your organization doesn’t allow.</span></span> <span data-ttu-id="5144b-130">例如，可以阻止访问 Cookie 的扩展。</span><span class="sxs-lookup"><span data-stu-id="5144b-130">For example, you can block extensions that access cookies.</span></span> <span data-ttu-id="5144b-131">如果扩展需要你阻止的权限，则用户无法安装它。</span><span class="sxs-lookup"><span data-stu-id="5144b-131">If an extension requires a permission that you blocked, the user can’t install it.</span></span> <span data-ttu-id="5144b-132">如果用户以前安装了该扩展，它将不再加载。</span><span class="sxs-lookup"><span data-stu-id="5144b-132">If users previously installed the extension, it will no longer load.</span></span> <span data-ttu-id="5144b-133">如果扩展包含阻止权限的可选要求，它将照常安装。</span><span class="sxs-lookup"><span data-stu-id="5144b-133">If an extension contains a blocked permission as an optional requirement, it installs as usual.</span></span> <span data-ttu-id="5144b-134">然后，当扩展正在运行时，会自动拒绝被阻止的权限。</span><span class="sxs-lookup"><span data-stu-id="5144b-134">Then, while the extension is running, blocked permissions are automatically declined.</span></span><br><span data-ttu-id="5144b-135">有关可用权限的列表，请参阅[声明权限](/microsoft-edge/extensions-chromium/enterprise/declare-permissions)。</span><span class="sxs-lookup"><span data-stu-id="5144b-135">For a list of available permissions, see [declare permissions](/microsoft-edge/extensions-chromium/enterprise/declare-permissions).</span></span>   |
| **<span data-ttu-id="5144b-136">installation_mode</span><span class="sxs-lookup"><span data-stu-id="5144b-136">installation_mode</span></span>**| <span data-ttu-id="5144b-137">控制是否以及如何将指定的扩展添加到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="5144b-137">Controls if and how extensions that you specify are added to Microsoft Edge.</span></span> <span data-ttu-id="5144b-138">可以将安装模式设置为以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="5144b-138">You can set the installation mode to one of the following options:</span></span><br><span data-ttu-id="5144b-139">- 允许：用户可以安装扩展。</span><span class="sxs-lookup"><span data-stu-id="5144b-139">- allowed: Users can install the extension.</span></span> <span data-ttu-id="5144b-140">如果未定义安装模式，则此设置为默认设置。</span><span class="sxs-lookup"><span data-stu-id="5144b-140">If no installation mode is defined, this setting is the default.</span></span><br><span data-ttu-id="5144b-141">- 已阻止：用户无法安装扩展。</span><span class="sxs-lookup"><span data-stu-id="5144b-141">- blocked: Users can’t install the extension.</span></span><br><span data-ttu-id="5144b-142">- force_installed：无需用户交互即可自动安装扩展。</span><span class="sxs-lookup"><span data-stu-id="5144b-142">- force_installed: Automatically install the extension without user interaction.</span></span> <span data-ttu-id="5144b-143">用户无法删除它。</span><span class="sxs-lookup"><span data-stu-id="5144b-143">Users can’t remove it.</span></span> <span data-ttu-id="5144b-144">还需要使用 update_url 定义扩展下载位置。</span><span class="sxs-lookup"><span data-stu-id="5144b-144">You also need to define the extension download location using update_url.</span></span> <span data-ttu-id="5144b-145">**注意**：不能将此设置与 \* 一起使用，因为 Microsoft Edge 不知道要自动安装的扩展。</span><span class="sxs-lookup"><span data-stu-id="5144b-145">**Note**: You can’t use this setting with \* because Microsoft Edge wouldn't know which extension to automatically install.</span></span><br><span data-ttu-id="5144b-146">- normal_installed：无需用户交互即可自动安装扩展。</span><span class="sxs-lookup"><span data-stu-id="5144b-146">- normal_installed: Automatically install the extension without user interaction.</span></span> <span data-ttu-id="5144b-147">用户可以禁用它。</span><span class="sxs-lookup"><span data-stu-id="5144b-147">Users can disable it.</span></span> <span data-ttu-id="5144b-148">还需要使用 update_url 定义扩展下载位置。</span><span class="sxs-lookup"><span data-stu-id="5144b-148">You also need to define the extension download location using update_url.</span></span> <span data-ttu-id="5144b-149">**注意**：不能将此设置与 \* 一起使用，因为 Microsoft Edge 不知道要自动安装的扩展。</span><span class="sxs-lookup"><span data-stu-id="5144b-149">**Note**: You can’t use this setting with \* because Microsoft Edge wouldn't know which extension to automatically install.</span></span><br><span data-ttu-id="5144b-150">- 已删除：用户无法安装扩展。</span><span class="sxs-lookup"><span data-stu-id="5144b-150">- removed: Users can’t install the extension.</span></span> <span data-ttu-id="5144b-151">如果用户以前安装了扩展，Microsoft Edge 将其删除。</span><span class="sxs-lookup"><span data-stu-id="5144b-151">If users previously installed the extension, Microsoft Edge removes it.</span></span> |  |
| **<span data-ttu-id="5144b-152">install_sources</span><span class="sxs-lookup"><span data-stu-id="5144b-152">install_sources</span></span>** | <span data-ttu-id="5144b-153">只能用于配置默认配置 \*。</span><span class="sxs-lookup"><span data-stu-id="5144b-153">Can be used only to configure the default configuration, \*.</span></span> <span data-ttu-id="5144b-154">指定允许哪些 URL 安装扩展。</span><span class="sxs-lookup"><span data-stu-id="5144b-154">Specifies which URLs are allowed to install extensions.</span></span> <span data-ttu-id="5144b-155">这些模式必须允许 \*.crx 文件的位置和启动下载的页面（即引用者）。</span><span class="sxs-lookup"><span data-stu-id="5144b-155">Both the location of the \*.crx file and the page where the download is started from (the referrer) must be allowed by these patterns.</span></span> <span data-ttu-id="5144b-156">有关 URL 模式示例，请参阅[匹配模式](/microsoft-edge/extensions-chromium/enterprise/match-patterns)。</span><span class="sxs-lookup"><span data-stu-id="5144b-156">For URL pattern examples, see the [match patterns](/microsoft-edge/extensions-chromium/enterprise/match-patterns).</span></span>  |
| **<span data-ttu-id="5144b-157">minimum_version_required</span><span class="sxs-lookup"><span data-stu-id="5144b-157">minimum_version_required</span></span>** |<span data-ttu-id="5144b-158">Microsoft Edge 禁用版本早于指定最低版本的扩展，包括强制安装的扩展。</span><span class="sxs-lookup"><span data-stu-id="5144b-158">Microsoft Edge disables extensions, including force-installed extensions, with a version older than the specified minimum version.</span></span><br><span data-ttu-id="5144b-159">版本字符串的格式与扩展清单中使用的格式相同。</span><span class="sxs-lookup"><span data-stu-id="5144b-159">The format of the version string is the same as the one used in the extension manifest.</span></span>     |
| **<span data-ttu-id="5144b-160">update_url</span><span class="sxs-lookup"><span data-stu-id="5144b-160">update_url</span></span>** | <span data-ttu-id="5144b-161">仅适用于 force_installed和normal_installed。</span><span class="sxs-lookup"><span data-stu-id="5144b-161">Only applies to force_installed and normal_installed.</span></span> <span data-ttu-id="5144b-162">指定 Microsoft Edge 应从何处下载扩展。</span><span class="sxs-lookup"><span data-stu-id="5144b-162">Specifies where Microsoft Edge should download an extension from.</span></span> <span data-ttu-id="5144b-163">如果扩展托管在 Microsoft Edge 加载项网站中，请使用以下位置：`https://edge.microsoft.com/extensionwebstorebase/v1/crx`。</span><span class="sxs-lookup"><span data-stu-id="5144b-163">If the extension is hosted in the Microsoft Edge Add-ons website, use this location: `https://edge.microsoft.com/extensionwebstorebase/v1/crx`.</span></span><br><span data-ttu-id="5144b-164">Microsoft Edge 使用为初始扩展安装指定的 URL。</span><span class="sxs-lookup"><span data-stu-id="5144b-164">Microsoft Edge uses the URL that you specify for the initial extension installation.</span></span> <span data-ttu-id="5144b-165">对于后续扩展更新，Microsoft Edge 使用扩展清单中的 URL。</span><span class="sxs-lookup"><span data-stu-id="5144b-165">For subsequent extension updates, Microsoft Edge uses the URL in the extension's manifest.</span></span>   |
| **<span data-ttu-id="5144b-166">runtime_allowed_hosts</span><span class="sxs-lookup"><span data-stu-id="5144b-166">runtime_allowed_hosts</span></span>**| <span data-ttu-id="5144b-167">允许扩展与指定网站交互，即使它们也在 runtime_blocked_hosts 中定义了。</span><span class="sxs-lookup"><span data-stu-id="5144b-167">Allows extensions to interact with specified websites, even if they’re also defined in runtime_blocked_hosts.</span></span> <span data-ttu-id="5144b-168">最多可以指定 100 个条目。</span><span class="sxs-lookup"><span data-stu-id="5144b-168">You can specify up to 100 entries.</span></span> <span data-ttu-id="5144b-169">将放弃额外的条目。</span><span class="sxs-lookup"><span data-stu-id="5144b-169">Extra entries are discarded.</span></span><br><span data-ttu-id="5144b-170">主机模式格式类似于 [匹配模式](/microsoft-edge/extensions-chromium/enterprise/match-patterns) ，但不能定义路径。</span><span class="sxs-lookup"><span data-stu-id="5144b-170">The host pattern format is similar to [match patterns](/microsoft-edge/extensions-chromium/enterprise/match-patterns) except you can’t define the path.</span></span> <span data-ttu-id="5144b-171">例如：</span><span class="sxs-lookup"><span data-stu-id="5144b-171">For example:</span></span><br><span data-ttu-id="5144b-172">- *://*.example.com</span><span class="sxs-lookup"><span data-stu-id="5144b-172">- *://*.example.com</span></span><br><span data-ttu-id="5144b-173">- *://example.*—支持 eTLD 通配符</span><span class="sxs-lookup"><span data-stu-id="5144b-173">- *://example.*—eTLD wildcards are supported</span></span>     |
| **<span data-ttu-id="5144b-174">runtime_blocked_hosts</span><span class="sxs-lookup"><span data-stu-id="5144b-174">runtime_blocked_hosts</span></span>**| <span data-ttu-id="5144b-175">阻止扩展与指定的网站交互或修改网站。</span><span class="sxs-lookup"><span data-stu-id="5144b-175">Prevent extensions from interacting with or modifying websites that you specify.</span></span> <span data-ttu-id="5144b-176">修改包括阻止 JavaScript 注入、Cookie 访问、Web 请求修改。</span><span class="sxs-lookup"><span data-stu-id="5144b-176">Modifications include blocking JavaScript injection, cookie access, and web-request modifications.</span></span><br><span data-ttu-id="5144b-177">最多可以指定 100 个条目。</span><span class="sxs-lookup"><span data-stu-id="5144b-177">You can specify up to 100 entries.</span></span> <span data-ttu-id="5144b-178">将放弃额外的条目。</span><span class="sxs-lookup"><span data-stu-id="5144b-178">Extra entries are discarded.</span></span><br><span data-ttu-id="5144b-179">主机模式格式类似于匹配模式，但不能定义路径。</span><span class="sxs-lookup"><span data-stu-id="5144b-179">The host pattern format is similar to match patterns except you can’t define the path.</span></span> <span data-ttu-id="5144b-180">例如：</span><span class="sxs-lookup"><span data-stu-id="5144b-180">For example:</span></span><br><span data-ttu-id="5144b-181">- *://*.example.com</span><span class="sxs-lookup"><span data-stu-id="5144b-181">- *://*.example.com</span></span><br><span data-ttu-id="5144b-182">- *://example.*—支持 eTLD 通配符</span><span class="sxs-lookup"><span data-stu-id="5144b-182">- *://example.*—eTLD wildcards are supported</span></span>   |


## <a name="configure-using-a-json-string-in-windows-group-policy-editor"></a><span data-ttu-id="5144b-183">在 Windows 组策略编辑器中使用 JSON 字符串进行配置</span><span class="sxs-lookup"><span data-stu-id="5144b-183">Configure using a JSON string in Windows Group Policy Editor</span></span>

<span data-ttu-id="5144b-184">使用 GPO 使用扩展设置策略的步骤假定你已导入 adM/ADMX for Microsoft Edge 策略。</span><span class="sxs-lookup"><span data-stu-id="5144b-184">The steps to use the extension settings policy using GPO assume that you've already imported the ADM/ADMX for Microsoft Edge Policies.</span></span>

1. <span data-ttu-id="5144b-185">打开组策略编辑器，转到 **Microsoft Edge >扩展>配置扩展管理设置策略**。</span><span class="sxs-lookup"><span data-stu-id="5144b-185">Open the group policy editor and go to go to **Microsoft Edge > Extensions > Configure extension management setting policy**.</span></span>
2. <span data-ttu-id="5144b-186">启用策略，并在文本框中输入其紧凑的 JavaScript 对象表示法 (JSON) 数据作为一行，不带换行符。</span><span class="sxs-lookup"><span data-stu-id="5144b-186">Enable the policy and enter its compact JavaScript Object Notation (JSON) data in the text box as a single line with no line breaks.</span></span>
3. <span data-ttu-id="5144b-187">若要验证策略并将其压缩为单行，请使用 JSON 压缩工具。</span><span class="sxs-lookup"><span data-stu-id="5144b-187">To validate the policy and compact it into a single line, use a JSON compression tool.</span></span>

### <a name="properly-format-json-for-the-extension-settings-policy"></a><span data-ttu-id="5144b-188">为扩展设置策略正确设置 JSON 格式</span><span class="sxs-lookup"><span data-stu-id="5144b-188">Properly format JSON for the extension settings policy</span></span>

<span data-ttu-id="5144b-189">你需要了解此策略的两个部分 - 默认范围和单个作用域。</span><span class="sxs-lookup"><span data-stu-id="5144b-189">You need to understand the two parts to this policy — the default scope and the individual scope.</span></span> <span data-ttu-id="5144b-190">对于没有其自身作用域的扩展，默认范围为 catch-all。</span><span class="sxs-lookup"><span data-stu-id="5144b-190">The default scope is a catch-all for extensions without their own scope.</span></span> <span data-ttu-id="5144b-191">单个范围仅应用于该扩展。</span><span class="sxs-lookup"><span data-stu-id="5144b-191">The individual scope is applied to that extension only.</span></span>  

<span data-ttu-id="5144b-192">默认范围由星号 (\*) 标识。</span><span class="sxs-lookup"><span data-stu-id="5144b-192">The default scope is identified by the asterisk (\*).</span></span> <span data-ttu-id="5144b-193">下一个示例定义了默认范围和单个扩展范围。</span><span class="sxs-lookup"><span data-stu-id="5144b-193">The next example defines a default scope and an individual extension scope.</span></span>

```json
{ 
   “*”: {}, 
   “nckgahadagoaajjgafhacjanaoiihapd”: {} 
} 
```

<span data-ttu-id="5144b-194">扩展将仅从一个范围获取其设置。</span><span class="sxs-lookup"><span data-stu-id="5144b-194">An extension will only get its settings from one scope.</span></span> <span data-ttu-id="5144b-195">如果该扩展有单个扩展范围，则它们将是应用于该扩展的设置。</span><span class="sxs-lookup"><span data-stu-id="5144b-195">If there’s an individual extension scope for that extension, those will be the settings that apply to that extension.</span></span> <span data-ttu-id="5144b-196">如果不存在单个扩展范围，则扩展将使用默认范围。</span><span class="sxs-lookup"><span data-stu-id="5144b-196">If no individual extension scope exists, then the extension will use the default scope.</span></span>  

<span data-ttu-id="5144b-197">下一个 JSON 示例阻止任何扩展在 `.example.com` 上运行，并阻止任何需要权限 "USB" 的扩展。</span><span class="sxs-lookup"><span data-stu-id="5144b-197">The next JSON example blocks any extension from running on `.example.com` and blocks any extension that requires the permission "USB".</span></span>

```json
{ 
  "*": { 
    "runtime_blocked_hosts": ["*://*.example.com"], 
    "blocked_permissions": ["usb"] 
  } 
} 
```

**<span data-ttu-id="5144b-198">压缩 JSON</span><span class="sxs-lookup"><span data-stu-id="5144b-198">Compact JSON</span></span>**

```json
{"*":{"runtime_blocked_hosts":["*://*.example.com"],"blocked_permissions":["usb"]}} 
```

### <a name="a-few-more-json-examples-for-extension-settings"></a><span data-ttu-id="5144b-199">扩展设置的更多 JSON 示例</span><span class="sxs-lookup"><span data-stu-id="5144b-199">A few more JSON examples for extension settings</span></span>

#### <a name="using-installation_mode-property-to-allow-and-block-extensions"></a><span data-ttu-id="5144b-200">使用 installation_mode 属性允许和阻止扩展</span><span class="sxs-lookup"><span data-stu-id="5144b-200">Using installation_mode property to allow and block extensions</span></span>

- <span data-ttu-id="5144b-201">用户可以安装所有扩展 - 这是默认设置</span><span class="sxs-lookup"><span data-stu-id="5144b-201">User can install all extensions - this is the default setting</span></span> 

  `{ "*": {"installation_mode": "allowed" }}`
- <span data-ttu-id="5144b-202">用户无法安装任何扩展。</span><span class="sxs-lookup"><span data-stu-id="5144b-202">User can’t install any extensions.</span></span>  

  `{ "*": {"installation_mode": "blocked" }}`

- <span data-ttu-id="5144b-203">指定阻止安装时要显示的自定义消息。</span><span class="sxs-lookup"><span data-stu-id="5144b-203">Specify a custom message to display when installation is blocked.</span></span>

   `{"*": {"blocked_install_message": ["Call IT(408 - 555 - 1234) for an exception"]}}`

#### <a name="using-installation_mode-property-to-force-install-extensions"></a><span data-ttu-id="5144b-204">使用 installation_mode 属性强制安装扩展</span><span class="sxs-lookup"><span data-stu-id="5144b-204">Using installation_mode property to force install extensions</span></span>

<span data-ttu-id="5144b-205">将 installation_mode 用作 "force_installed" 时，无需用户交互即可自动安装扩展。</span><span class="sxs-lookup"><span data-stu-id="5144b-205">When using installation_mode as "force_installed", the extension is automatically installed without user interaction.</span></span> <span data-ttu-id="5144b-206">用户无法禁用或删除扩展。</span><span class="sxs-lookup"><span data-stu-id="5144b-206">A user can’t disable or remove the extension.</span></span> <span data-ttu-id="5144b-207">如果扩展是“正常”或“强制”安装的，则还必须定义 **update_url** 字段。</span><span class="sxs-lookup"><span data-stu-id="5144b-207">If an extension is "normal" or "force" installed, the **update_url** field must also be defined.</span></span> <span data-ttu-id="5144b-208">此字段指向可从中安装扩展的位置。</span><span class="sxs-lookup"><span data-stu-id="5144b-208">This field points to the location where the extension can be installed from.</span></span> <span data-ttu-id="5144b-209">对 **update_url** 字段使用以下位置：</span><span class="sxs-lookup"><span data-stu-id="5144b-209">Use the following locations for the **update_url** field:</span></span>

- <span data-ttu-id="5144b-210">如果要下载的扩展托管在 Microsoft Edge 加载项存储上，请使用 [https://edge.microsoft.com/extensionwebstorebase/v1/crx](https://edge.microsoft.com/extensionwebstorebase/v1/crx)。</span><span class="sxs-lookup"><span data-stu-id="5144b-210">If the extension you’re downloading is hosted on the Microsoft Edge Add-ons store, use [https://edge.microsoft.com/extensionwebstorebase/v1/crx](https://edge.microsoft.com/extensionwebstorebase/v1/crx).</span></span>
- <span data-ttu-id="5144b-211">如果要下载的扩展托管在Chrome Web Store上，请使用 [https://clients2.google.com/service/update2/crx](https://clients2.google.com/service/update2/crx)。</span><span class="sxs-lookup"><span data-stu-id="5144b-211">If the extension you’re downloading is hosted on the Chrome Web Store, use [https://clients2.google.com/service/update2/crx](https://clients2.google.com/service/update2/crx).</span></span>
- <span data-ttu-id="5144b-212">如果要在自己的服务器上托管扩展，请使用 Microsoft Edge 可以从中下载打包扩展（.crx 文件）的 URL。</span><span class="sxs-lookup"><span data-stu-id="5144b-212">If you’re hosting the extension on your own server, use the URL where Microsoft Edge can download the packed extension (.crx file).</span></span> <span data-ttu-id="5144b-213">JSON 示例：</span><span class="sxs-lookup"><span data-stu-id="5144b-213">JSON example:</span></span>

   `{"nckgahadagoaajjgafhacjanaoiihapd": {"installation_mode": "force_installed","update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx"}}`
  
<span data-ttu-id="5144b-214">在上面的示例中，如果使用 "normal_installed" 而不是 "force_installed"，则无需用户交互即可自动安装扩展，但可以禁用扩展。</span><span class="sxs-lookup"><span data-stu-id="5144b-214">In the above example Instead of "force_installed", if you use "normal_installed", then the extension is automatically installed without user interaction, but they can disable the extension.</span></span>  

   > [!TIP]
   > <span data-ttu-id="5144b-215">正确设置 JSON 字符串的格式可能比较棘手。</span><span class="sxs-lookup"><span data-stu-id="5144b-215">Formatting a JSON string correctly can be tricky.</span></span> <span data-ttu-id="5144b-216">在实现策略之前，请使用 JSON 检查器。</span><span class="sxs-lookup"><span data-stu-id="5144b-216">Use a JSON checker before implementing the policy.</span></span> <span data-ttu-id="5144b-217">或尝试早期版本的 [扩展设置生成器工具](https://microsoft.github.io/edge-extension-settings-generator/minimal)</span><span class="sxs-lookup"><span data-stu-id="5144b-217">Or try the early version of [Extension Settings Generator Tool](https://microsoft.github.io/edge-extension-settings-generator/minimal)</span></span>

## <a name="configure-using-the-windows-registry"></a><span data-ttu-id="5144b-218">使用 Windows 注册表进行配置</span><span class="sxs-lookup"><span data-stu-id="5144b-218">Configure using the Windows Registry</span></span>

<span data-ttu-id="5144b-219">ExtensionSettings 策略应写入此建下的注册表：</span><span class="sxs-lookup"><span data-stu-id="5144b-219">The ExtensionSettings policy should be written to the registry under this key:</span></span>

`HKLM\Software\Policies\Microsoft\Edge\`

> [!NOTE]
> <span data-ttu-id="5144b-220">可以使用 HKCU 而不是 HKLM。</span><span class="sxs-lookup"><span data-stu-id="5144b-220">It’s possible to use HKCU instead of HKLM.</span></span> <span data-ttu-id="5144b-221">可以使用组策略对象（GPO）配置等效路径。</span><span class="sxs-lookup"><span data-stu-id="5144b-221">The equivalent path can be configured with Group Policy Object (GPO).</span></span>  

<span data-ttu-id="5144b-222">对于 Microsoft Edge，所有设置都将在此键下启动：</span><span class="sxs-lookup"><span data-stu-id="5144b-222">For Microsoft Edge, all settings will start under this key:</span></span>

`HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge\`

<span data-ttu-id="5144b-223">你将创建的下一个键是单个作用域的扩展 ID 或默认作用域的星号 (\*)。</span><span class="sxs-lookup"><span data-stu-id="5144b-223">The next key that you will create is either the Extension ID for individual scope or an asterisk (\*) for the Default Scope.</span></span> <span data-ttu-id="5144b-224">例如，将以下位置用于适用于 Google Hangouts 的设置：</span><span class="sxs-lookup"><span data-stu-id="5144b-224">For example, you'd use the following location for settings that apply to Google Hangouts:</span></span>

`HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge\ExtensionSettings\nckgahadagoaajjgafhacjanaoiihapd`

<span data-ttu-id="5144b-225">对于应用于默认作用域的设置，请使用以下位置：</span><span class="sxs-lookup"><span data-stu-id="5144b-225">For settings that apply to the Default Scope, use this location:</span></span>

`HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge\ExtensionSettings\*`

<span data-ttu-id="5144b-226">不同的设置将需要不同的格式，具体取决于它们是字符串还是字符串数组。</span><span class="sxs-lookup"><span data-stu-id="5144b-226">Different settings will require different formats, depending on whether they are a string or an array of strings.</span></span> <span data-ttu-id="5144b-227">数组值需要 [ " value " ]。</span><span class="sxs-lookup"><span data-stu-id="5144b-227">Array values require [＂value＂].</span></span> <span data-ttu-id="5144b-228">可以按当前方式输入字符串值。</span><span class="sxs-lookup"><span data-stu-id="5144b-228">String values can be entered as is.</span></span> <span data-ttu-id="5144b-229">以下列表显示哪些设置是数组或字符串：</span><span class="sxs-lookup"><span data-stu-id="5144b-229">The following list shows which settings are arrays or strings:</span></span>

- <span data-ttu-id="5144b-230">Installation_mode = 字符串</span><span class="sxs-lookup"><span data-stu-id="5144b-230">Installation_mode = String</span></span>
- <span data-ttu-id="5144b-231">update_url = 字符串</span><span class="sxs-lookup"><span data-stu-id="5144b-231">update_url = String</span></span>
- <span data-ttu-id="5144b-232">blocked_permissions = 字符串数组</span><span class="sxs-lookup"><span data-stu-id="5144b-232">blocked_permissions = Array of strings</span></span>
- <span data-ttu-id="5144b-233">allowed_permissions = 字符串数组</span><span class="sxs-lookup"><span data-stu-id="5144b-233">allowed_permissions = Array of Strings</span></span>
- <span data-ttu-id="5144b-234">minimum_version_required = 字符串</span><span class="sxs-lookup"><span data-stu-id="5144b-234">minimum_version_required = String</span></span>
- <span data-ttu-id="5144b-235">runtime_blocked_hosts = 字符串数组</span><span class="sxs-lookup"><span data-stu-id="5144b-235">runtime_blocked_hosts = Array of strings</span></span>
- <span data-ttu-id="5144b-236">runtime_allowed_hosts = 字符串数组</span><span class="sxs-lookup"><span data-stu-id="5144b-236">runtime_allowed_hosts = Array of Strings</span></span>
- <span data-ttu-id="5144b-237">blocked_install_message = 字符串</span><span class="sxs-lookup"><span data-stu-id="5144b-237">blocked_install_message = String</span></span>


## <a name="see-also"></a><span data-ttu-id="5144b-238">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5144b-238">See also</span></span>

- [<span data-ttu-id="5144b-239">在企业中管理 Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="5144b-239">Manage Microsoft Edge extensions in the enterprise</span></span>](microsoft-edge-manage-extensions.md)
- [<span data-ttu-id="5144b-240">使用组策略管理 Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="5144b-240">Use group policies to manage Microsoft Edge extensions</span></span>](microsoft-edge-manage-extensions-policies.md)
- [<span data-ttu-id="5144b-241">Microsoft Edge 扩展的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="5144b-241">FAQ for Microsoft Edge Extensions</span></span>](microsoft-edge-manage-extensions-faq.md)
- [<span data-ttu-id="5144b-242">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="5144b-242">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
