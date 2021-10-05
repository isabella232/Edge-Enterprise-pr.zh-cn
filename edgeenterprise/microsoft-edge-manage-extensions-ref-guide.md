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
ms.openlocfilehash: 7dceff78172626d70863883e0762be2f4cb7e51c
ms.sourcegitcommit: e825c6a1b0e63004288e13f6bb672743b0ecfafb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2021
ms.locfileid: "12069008"
---
# <a name="detailed-guide-to-the-extensionsettings-policy"></a>ExtensionSettings 策略的详细指南

Microsoft Edge 提供了多种方法来管理扩展。 一种常见方法是在 Windows 组策略编辑器或 Windows 注册表中使用 [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) 策略在一处通过 JSON 字符串设置多个策略。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="before-you-begin"></a>在你开始前

你决定是要在此处设置所有扩展管理设置，还是通过其他策略设置这些控件。
  
ExtensionSettings 策略可以覆盖已在组策略其他位置设置的其他策略，包括以下策略：

- [ExtensionAllowedTypes](/DeployEdge/microsoft-edge-policies#extensionallowedtypes)
- [ExtensionInstallBlocklist](/DeployEdge/microsoft-edge-policies#extensioninstallblocklist)
- [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)
- [ExtensionInstallSources](/DeployEdge/microsoft-edge-policies#extensioninstallsources)
- [ExtensionInstallAllowlist](/DeployEdge/microsoft-edge-policies#extensioninstallsources)

## <a name="extensionsettings-policy-fields"></a>ExtensionSettings 策略字段

此策略可以控制更新 URL 等设置，从中下载扩展以进行初始安装，以及阻止权限，或不允许运行哪些权限。 下表描述了可用的策略字段。

| &nbsp; | 描述 |
|--|--|
| **allowed_types** | 只能用于配置默认配置 *。 指定允许用户在 Microsoft Edge 上安装的应用或扩展类型。 该值为字符串列表，其中每个字符串应为以下类型之一："extension"、"theme"、"user_script" 和 "hosted_app"。   |
| **blocked_install_message**| 如果阻止用户安装某些扩展，可以指定在用户尝试安装这些扩展时在浏览器中显示的自定义消息。<br>将文本追加到在 Microsoft Edge 加载项网站上显示的一般错误消息。 例如，你可以告诉用户如何联系其 IT 部门或特定扩展不可用的原因。 消息的长度最多可为 1000 个字符。   |
|**blocked_permissions**  | 阻止用户安装和运行请求组织不允许的特定 API 权限的扩展。 例如，可以阻止访问 Cookie 的扩展。 如果扩展需要你阻止的权限，则用户无法安装它。 如果用户以前安装了该扩展，它将不再加载。 如果扩展包含阻止权限的可选要求，它将照常安装。 然后，当扩展正在运行时，会自动拒绝被阻止的权限。<br>有关可用权限的列表，请参阅[声明权限](/microsoft-edge/extensions-chromium/enterprise/declare-permissions)。   |
| **installation_mode**| 控制是否以及如何将指定的扩展添加到 Microsoft Edge。 可以将安装模式设置为以下选项之一：<br>- 允许：用户可以安装扩展。 如果未定义安装模式，则此设置为默认设置。<br>- 已阻止：用户无法安装扩展。<br>- force_installed：无需用户交互即可自动安装扩展。 用户无法删除它。 还需要使用 update_url 定义扩展下载位置。 **注意**：不能将此设置与 * 一起使用，因为 Microsoft Edge 不知道要自动安装的扩展。<br>- normal_installed：无需用户交互即可自动安装扩展。 用户可以禁用它。 还需要使用 update_url 定义扩展下载位置。 **注意**：不能将此设置与 * 一起使用，因为 Microsoft Edge 不知道要自动安装的扩展。<br>- 已删除：用户无法安装扩展。 如果用户以前安装了扩展，Microsoft Edge 将其删除。 |  |
| **install_sources** | 只能用于配置默认配置 *。 指定允许哪些 URL 安装扩展。 这些模式必须允许 *.crx 文件的位置和启动下载的页面（即引用者）。 有关 URL 模式示例，请参阅[匹配模式](/microsoft-edge/extensions-chromium/enterprise/match-patterns)。  |
| **minimum_version_required** |Microsoft Edge 禁用版本早于指定最低版本的扩展，包括强制安装的扩展。<br>版本字符串的格式与扩展清单中使用的格式相同。     |
| **update_url** | 仅适用于 force_installed和normal_installed。 指定 Microsoft Edge 应从何处下载扩展。 如果扩展托管在 Microsoft Edge 加载项网站中，请使用以下位置：`https://edge.microsoft.com/extensionwebstorebase/v1/crx`。<br>Microsoft Edge 使用为初始扩展安装指定的 URL。 对于后续扩展更新，Microsoft Edge 使用扩展清单中的 URL。   |
| **runtime_allowed_hosts**| 允许扩展与指定网站交互，即使它们也在 runtime_blocked_hosts 中定义了。 最多可以指定 100 个条目。 将放弃额外的条目。<br>主机模式格式类似于 [匹配模式](/microsoft-edge/extensions-chromium/enterprise/match-patterns) ，但不能定义路径。 例如：<br>- *://*.example.com<br>- *://example.*—支持 eTLD 通配符     |
| **runtime_blocked_hosts**| 阻止扩展与指定的网站交互或修改网站。 修改包括阻止 JavaScript 注入、Cookie 访问、Web 请求修改。<br>最多可以指定 100 个条目。 将放弃额外的条目。<br>主机模式格式类似于匹配模式，但不能定义路径。 例如：<br>- *://*.example.com<br>- *://example.*—支持 eTLD 通配符   |
| **override_update_url**| 在 Edge 93 中可用<br>如果设置为 `true` ，则 Edge 将使用 ExtensionSettings 策略或 ExtensionInstallForcelist 策略中指定的更新 URL 进行后续扩展更新。<br>如果未设置或设置为 ，Edge 将使用扩展清单中指定的 `false` URL 进行更新。|
| **toolbar_state**| 在 Edge 94 中可用<br>此策略设置允许你向工具栏强制显示已安装的扩展。 默认状态是 `default_shown` 适用于所有扩展。 此设置可能具有以下状态<br>-`force_shown`：可以选择强制在工具栏上显示已安装的扩展。 用户将无法从工具栏中隐藏特定的扩展图标。<br>-`default_hidden`：在此状态中，扩展在安装时在工具栏中隐藏。 如果需要，用户可以在工具栏上显示它们。<br>-`default_shown`：这是浏览器上所有已安装扩展的失聪设置。

这些是全局范围内允许的键 (*) ： 

- blocked_permissions
- installation_mode - 仅 `"blocked"` `"allowed"` ， 或 `"removed"` 是此作用域中的有效值。
- runtime_blocked_hosts
- blocked_install_message
- allowed_types
- runtime_allowed_hosts
- install_sources

这些是单个扩展作用域中允许的键： 

- blocked_permissions
- minimum_version_required
- blocked_install_message
- installation_mode - `"blocked"` 、 `"allowed"` 、 、 和 `"removed"` `"force_installed"` `"normal_installed"` 是可能的值。
- runtime_allowed_hosts
- update_url
- override_update_url
- runtime_blocked_hosts
- toolbar_state

这些键是更新 URL 范围内允许的键： 

- blocked_permissions
- installation_mode - 仅 `"blocked"` `"allowed"` ， 或 `"removed"` 是此作用域中的有效值。

## <a name="configure-using-a-json-string-in-windows-group-policy-editor"></a>在 Windows 组策略编辑器中使用 JSON 字符串进行配置

使用 GPO 使用扩展设置策略的步骤假定你已导入 adM/ADMX for Microsoft Edge 策略。

1. 打开组策略编辑器，转到 **Microsoft Edge >扩展>配置扩展管理设置策略**。
2. 启用策略，并在文本框中输入其紧凑的 JavaScript 对象表示法 (JSON) 数据作为一行，不带换行符。
3. 若要验证策略并将其压缩为单行，请使用 JSON 压缩工具。

### <a name="properly-format-json-for-the-extension-settings-policy"></a>为扩展设置策略正确设置 JSON 格式

你需要了解此策略的两个部分 - 默认范围和单个作用域。 对于没有其自身作用域的扩展，默认范围为 catch-all。 单个范围仅应用于该扩展。  

默认范围由星号 (*) 标识。 下一个示例定义了默认范围和单个扩展范围。

```json
{ 
   “*”: {}, 
   “nckgahadagoaajjgafhacjanaoiihapd”: {} 
} 
```

扩展将仅从一个范围获取其设置。 如果该扩展有单个扩展范围，则它们将是应用于该扩展的设置。 如果不存在单个扩展范围，则扩展将使用默认范围。  

下一个 JSON 示例阻止任何扩展在 `.example.com` 上运行，并阻止任何需要权限 "USB" 的扩展。

```json
{ 
  "*": { 
    "runtime_blocked_hosts": ["*://*.example.com"], 
    "blocked_permissions": ["usb"] 
  } 
} 
```

**压缩 JSON**

```json
{"*":{"runtime_blocked_hosts":["*://*.example.com"],"blocked_permissions":["usb"]}} 
```

### <a name="a-few-more-json-examples-for-extension-settings"></a>扩展设置的更多 JSON 示例

#### <a name="using-installation_mode-property-to-allow-and-block-extensions"></a>使用 installation_mode 属性允许和阻止扩展

- 用户可以安装所有扩展 - 这是默认设置 

  `{ "*": {"installation_mode": "allowed" }}`
- 用户无法安装任何扩展。  

  `{ "*": {"installation_mode": "blocked" }}`

- 指定阻止安装时要显示的自定义消息。

   `{"*": {"blocked_install_message": ["Call IT(408 - 555 - 1234) for an exception"]}}`

#### <a name="using-installation_mode-property-to-force-install-extensions"></a>使用 installation_mode 属性强制安装扩展

将 installation_mode 用作 "force_installed" 时，无需用户交互即可自动安装扩展。 用户无法禁用或删除扩展。 如果扩展是“正常”或“强制”安装的，则还必须定义 **update_url** 字段。 此字段指向可从中安装扩展的位置。 对 **update_url** 字段使用以下位置：

- 如果要下载的扩展托管在 Microsoft Edge 加载项存储上，请使用 [https://edge.microsoft.com/extensionwebstorebase/v1/crx](https://edge.microsoft.com/extensionwebstorebase/v1/crx)。
- 如果要下载的扩展托管在Chrome Web Store上，请使用 [https://clients2.google.com/service/update2/crx](https://clients2.google.com/service/update2/crx)。
- 如果要在自己的服务器上托管扩展，请使用 Microsoft Edge 可以从中下载打包扩展（.crx 文件）的 URL。 JSON 示例：

   `{"nckgahadagoaajjgafhacjanaoiihapd": {"installation_mode": "force_installed","update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx"}}`
  
在上面的示例中，如果使用 "normal_installed" 而不是 "force_installed"，则无需用户交互即可自动安装扩展，但可以禁用扩展。  

   > [!TIP]
   > 正确设置 JSON 字符串的格式可能比较棘手。 在实现策略之前，请使用 JSON 检查器。 或尝试早期版本的 [扩展设置生成器工具](https://microsoft.github.io/edge-extension-settings-generator/minimal)

## <a name="configure-using-the-windows-registry"></a>使用 Windows 注册表进行配置

ExtensionSettings 策略应写入此建下的注册表：

`HKLM\Software\Policies\Microsoft\Edge\`

> [!NOTE]
> 可以使用 HKCU 而不是 HKLM。 可以使用组策略对象（GPO）配置等效路径。  

对于 Microsoft Edge，所有设置都将在此键下启动：

`HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge\`

你将创建的下一个键是单个作用域的扩展 ID 或默认作用域的星号 (*)。 例如，将以下位置用于适用于 Google Hangouts 的设置：

`HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge\ExtensionSettings\nckgahadagoaajjgafhacjanaoiihapd`

对于应用于默认作用域的设置，请使用以下位置：

`HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge\ExtensionSettings\*`

不同的设置将需要不同的格式，具体取决于它们是字符串还是字符串数组。 数组值需要 [ " value " ]。 可以按当前方式输入字符串值。 以下列表显示哪些设置是数组或字符串：

- Installation_mode = 字符串
- update_url = 字符串
- blocked_permissions = 字符串数组
- allowed_permissions = 字符串数组
- minimum_version_required = 字符串
- runtime_blocked_hosts = 字符串数组
- runtime_allowed_hosts = 字符串数组
- blocked_install_message = 字符串


## <a name="see-also"></a>另请参阅

- [在企业中管理 Microsoft Edge 扩展](microsoft-edge-manage-extensions.md)
- [使用组策略管理 Microsoft Edge 扩展](microsoft-edge-manage-extensions-policies.md)
- [Microsoft Edge 扩展的常见问题解答](microsoft-edge-manage-extensions-faq.md)
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
