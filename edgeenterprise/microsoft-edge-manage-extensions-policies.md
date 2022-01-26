---
title: 使用组策略管理 Microsoft Edge 扩展
ms.author: aspoddar
author: AndreaLBarr
manager: balajek
ms.date: 10/21/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 使用组策略在企业中管理 Microsoft Edge 扩展
ms.openlocfilehash: 2b09f057931ca525bf142381aa2777c51a036eba
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2022
ms.locfileid: "12297920"
---
# <a name="use-group-policies-to-manage-microsoft-edge-extensions"></a>使用组策略管理 Microsoft Edge 扩展

本文介绍通过使用组策略管理扩展的选项和步骤。 这些选项假定你已为用户管理 Microsoft Edge。 如果尚未设置要为用户管理的 Microsoft Edge，请单击以下链接以立即执行此操作。

- [在企业中管理 Microsoft Edge 扩展](/deployedge/microsoft-edge-manage-extensions)

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="block-extensions-based-on-their-permissions"></a>基于其权限阻止扩展

可以使用 [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) 策略来根据权限控制用户可以安装的扩展。 如果已安装的扩展需要被阻止的权限，它将不会运行。 该扩展不会被删除，只是被禁用。

> [!NOTE]
> 只能在扩展设置策略中设置受阻止的权限设置。  

请使用以下步骤作为阻止扩展的指南。

1. 打开组策略管理编辑器并转到“**管理模板”>“Microsoft Edge”>“扩展**”，然后选择“**配置扩展管理设置**”。
2. 启用策略，然后通过使用经过压缩的 JSON 字符串输入要允许或阻止的权限。 下一个屏幕截图显示了如何阻止使用权限“usb”的扩展。

    :::image type="content" source="media/microsoft-edge-manage-extensions-policies/manage-extensions-gp-block-1.png" alt-text="配置组策略以阻止扩展。":::

下面的示例演示了用于阻止任何需要使用权限“usb”及其压缩字符串的扩展的 JSON。

### <a name="json-example"></a>JSON 示例：

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
   > 要阻止使用该权限的所有扩展，请将星号用于扩展 ID，如前面的示例所示。 如果指定一个扩展 ID，则该策略将仅应用于该扩展。 可以阻止多个条目，但它们必须是单独的条目。

## <a name="prevent-extensions-from-altering-web-pages"></a>阻止扩展更改网页

此设置防止扩展读取和更改敏感网站和域中的数据。 阻止不需要的操作是通过阻止操作（如脚本注入网站、读取 Cookie 或进行 Web 请求修改）来完成的。 此设置不阻止用户安装或删除扩展，仅阻止扩展更改指定的网站。 
  
> [!NOTE]
> 只能在扩展设置策略中设置运行时允许/阻止的主机设置。  

可以在 ExtensionSettings 策略中配置以下设置，以防止（或允许）网站或域的更改：

- **Runtime_blocked_hosts**。 此设置阻止扩展从指定的网站进行更改或读取数据。
- **Runtime_allowed_hosts**。 此设置允许扩展从指定的网站进行更改或读取数据。 以下格式用于在策略的 JSON 字符串中指定网站：

  ```json
  [http|https|ftp|*]://[subdomain|*].[hostname|*].[eTLD|*] [http|https|ftp|*],
  ```

  > [!NOTE]
  > `[hostname|*], and [eTLD|*]` 节是必需的，但 `[subdomain|*]` 节则是可选的。

下表显示了有效的主机模式和匹配模式的示例。

|有效的主机模式|匹配|不匹配|
|--|--|--|
|  `*://*.example.*` | `http://example.com`<br>`https://test.example.co.uk`   | `https://example.microsoft.com`<br>`http://example.microsoft.co.uk`  |
| `http://example.*` | `http://example.com`<br>`http://example.ly` | `https://example.com`<br>`http://test.example.com`   |
| `http://example.com`   | `http://example.com` | `https://example.com`<br>`http://test.example.co.uk` |
| `*://*`   | 所有 URL  |   |

使用以下步骤作为指南来阻止或允许扩展访问网站或域。

1. 打开组策略管理编辑器，并转到“**管理模板”>“Microsoft Edge”>“扩展**”，然后选择“**配置扩展管理设置**。  
2. 启用策略，然后输入要允许或阻止的权限，将权限压缩为单个 JSON 字符串。

以下示例演示如何阻止主机名上的扩展以及如何阻止同一域上的扩展。

### <a name="json-example-to-block-hostname"></a>用于阻止主机名的 JSON 示例

此示例显示 JSON 和压缩的 JSON 字符串，用于阻止任何扩展访问 `www.microsoft.com` 主机名。

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
> 要阻止所有扩展访问网页，请将星号用于扩展 ID，如前面的示例所示。  如果指定一个扩展 ID 而不是星号，则策略将仅应用于该扩展。 可以阻止多个扩展，但它们必须是单独的条目。

### <a name="json-example-to-block-extensions-on-same-domain"></a>用于阻止同一域上的扩展的 JSON 示例

此示例显示 JSON 和压缩的 JSON 字符串，用于阻止特定扩展在相同的域“importantwebsite”上运行。

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

## <a name="allow-or-block-extensions-in-group-policy"></a>允许或阻止组策略中的扩展

可以使用 [ExtensionInstallBlocklist](/DeployEdge/microsoft-edge-policies#extensioninstallblocklist) 和 [ExtensionInstallAllowlist](/DeployEdge/microsoft-edge-policies#extensioninstallallowlist) 策略来控制阻止或允许哪些扩展。 使用以下步骤作为指南，允许除要阻止的扩展之外的所有扩展。

1. 打开组策略管理编辑器，并转到“**管理模板”>“Microsoft Edge”>“扩展**”，然后选择“**控制哪些应用不可以安装**。
2. 选择“**已启用**”。
3. 单击“**显示**”。
4. 输入要阻止的扩展的应用 ID。 添加多个应用 ID 时，请对每个 ID 使用单独的行。
5. 要阻止所有扩展，请在策略中键入 ** \***，以防止安装任何扩展。 可以将此项与“允许安装特定扩展”策略结合使用，以仅允许安装某些扩展。 下一个屏幕截图显示将基于提供的应用 ID 而阻止的扩展。

   :::image type="content" source="media/microsoft-edge-manage-extensions-policies/manage-extensions-gp-block-2.png" alt-text="使用应用 ID 阻止扩展。":::

   > [!TIP]
   > 如果找不到扩展的应用 ID，请在 Microsoft Edge 加载项网站中查找扩展。 找到特定扩展，然后你将在多功能框中的 URL 末尾看到应用 ID。

> [!NOTE]
> 可以将扩展添加到用户计算机上已安装的阻止列表。 此操作将禁用扩展，并阻止用户重新启用它。 扩展不会卸载，而只是被禁用。

## <a name="force-install-an-extension"></a>强制安装扩展

使用 [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist) 策略来控制阻止或允许哪些扩展。 使用以下步骤作为指南以强制安装扩展。

1. 在组策略编辑器中，转到“**管理模板”>“Microsoft Edge”>“扩展**”，然后选择“**控制哪些扩展以静默方式安装**”。
2. 选择“**已启用**”。  
3. 单击“**显示**”。
4. 输入要强制安装的扩展的应用 ID。  

该扩展将以无提示方式安装，无需用户交互。 用户也无法卸载或禁用扩展。 此设置将覆盖已启用的任何阻止列表策略。

> [!NOTE]
> 对于托管在 Chrome Web store 中的扩展，请使用以下字符串，如：`pckdojakecnhhplcgfflhndiffaohfah;https://clients2.google.com/service/update2/crx`。
> 对于自托管扩展，请使用extension_id;update_url模式update_url更新清单 XML 文件的位置。 例如，`mfjlfjaknfckffgjgmdfeheeealceoak;https://file_location.azurewebsites.net/picture_of_the_day.xml`。

## <a name="block-extensions-from-a-specific-store-or-update-url"></a>阻止来自特定商店或更新 URL 的扩展

要阻止来自特定商店或 URL 的扩展，只需为该商店使用 [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) 策略来阻止 *update_url*。

使用以下步骤作为指南阻止来自特定商店或 URL 的扩展。

1. 打开组策略管理编辑器并转到“**管理模板”>“Microsoft Edge”>“>扩展**”，然后选择“**配置扩展管理设置**。  
2. 启用策略，然后输入要允许或阻止的权限，将其压缩为单个 JSON 字符串。

下一个示例演示要使用其更新 URL（`https://clients2.google.com/service/update2/crx`）来阻止 Chrome Web Store 的 JSON 和压缩 JSON 字符串。

### <a name="json-example-for-blocking-on-update-url"></a>用于阻止更新 URL 的 JSON 示例

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
> 你仍然可以使用 **ExtensionInstallForcelist** 和 **ExtensionInstallAllowlist** 来允许/强制安装特定扩展，即使使用上一示例中的 JSON 阻止了商店。

## <a name="see-also"></a>另请参阅

- [在企业中管理 Microsoft Edge 扩展](microsoft-edge-manage-extensions.md)
- [创建用于托管 Microsoft Edge 扩展的 Web 应用商店](microsoft-edge-manage-extensions-webstore.md)
- [ExtensionSettings 策略参考指南](microsoft-edge-manage-extensions-ref-guide.md)
- [Microsoft Edge 扩展的常见问题解答](microsoft-edge-manage-extensions-faq.md)
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
