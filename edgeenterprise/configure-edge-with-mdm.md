---
title: 使用移动设备管理配置 Microsoft Edge
ms.author: kvice
author: dan-wesley
manager: laurawi
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 使用移动设备管理配置 Microsoft Edge。
ms.openlocfilehash: 0927d64366652986b87c2f517ca8ebafd4c9ac55
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "11978713"
---
# <a name="configure-microsoft-edge-using-mobile-device-management"></a>使用移动设备管理配置 Microsoft Edge

本文介绍了如何使用[移动设备管理 (MDM)](/windows/client-management/mdm/) 通过 [ADMX 引入](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration)来配置 Windows 10 上的 Microsoft Edge。 本文还介绍了：

- 如何[为 Microsoft Edge 策略创建开放移动联盟统一资源标识符 (OMA-URI)](#create-an-oma-uri-for-microsoft-edge-policies)。
- 如何[使用 ADMX 引入和自定义 OMA-URI 在 Intune 中配置 Microsoft Edge](#configure-microsoft-edge-in-intune-using-admx-ingestion)。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="prerequisites"></a>先决条件

使用 Windows 10，最低系统要求如下：

- Windows 10 版本 1903（已安装 [KB4512941](https://support.microsoft.com/help/4512941/) 和 [KB4517211](https://support.microsoft.com/help/4517211/)）
- Windows 10 版本 1809（已安装 [KB4512534](https://support.microsoft.com/help/4512534/) 和 [KB4520062](https://support.microsoft.com/help/4520062/)）
- Windows 10 版本 1803（已安装 [KB4512509](https://support.microsoft.com/help/4512509/) 和 [KB4519978](https://support.microsoft.com/help/4519978)）
- Windows 10 版本 1709（已安装 [KB4516071](https://support.microsoft.com/help/4516071/) 和 [KB4520006](https://support.microsoft.com/help/4520006)）

## <a name="overview"></a>概述

通过将 MDM 与支持 [ADMX 引入](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration)的首选企业移动性管理 (EMM) 或 MDM 提供程序配合使用，你可以配置 Windows 10 上的 Microsoft Edge。

使用 MDM 配置 Microsoft Edge 的过程分为两个部分：

1. 将 Microsoft Edge ADMX 文件引入到 EMM 或 MDM 提供程序。 有关如何引入 ADMX 文件的说明，请参阅提供程序。

   > [!NOTE]
   > 有关 Microsoft Intune 的信息，请参阅[使用 ADMX 引入在 Intune 中配置 Microsoft Edge](#configure-microsoft-edge-in-intune-using-admx-ingestion)。

2. [为 Microsoft Edge 策略创建 OMA-URI](#create-an-oma-uri-for-microsoft-edge-policies)。

## <a name="create-an-oma-uri-for-microsoft-edge-policies"></a>为 Microsoft Edge 策略创建 OMA-URI

以下各部分介绍了如何创建 OMA-URI 路径，以及如何为强制和推荐的浏览器策略查找和定义 XML 格式的值。

在开始之前，请从 [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)下载 Microsoft Edge 策略模板文件 (MicrosoftEdgePolicyTemplates.cab)，然后提取内容。

定义 OMA-URI 有三个步骤：

1. [创建 OMA-URI 路径](#create-the-oma-uri-path)
2. [指定 OMA-URI 数据类型](#specify-the-data-type)
3. [设置 OMA-URI 值](#set-the-value-for-a-browser-policy)

### <a name="create-the-oma-uri-path"></a>创建 OMA-URI 路径

使用以下公式作为指导来创建 OMA-URI 路径。 <br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/<ADMXIngestName>~Policy~<ADMXNamespace>~<ADMXCategory>/<PolicyName>`* <br/><br/>

| 参数         | 说明                                                                                   |
|-------------------|-----------------------------------------------------------------------------------------------|
| \<ADMXIngestName> | 使用“Edge”或引入管理模板时定义的内容。 例如，如果你使用的是“/Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/MicrosoftEdge/Policy/EdgeAdmx”，则使用“MicrosoftEdge”。<br/><br/> `<ADMXIngestionName>` 必须与引入 ADMX 文件时所使用的内容匹配。 |
| \<ADMXNamespace>  | 具体是“Microsoft_edge”还是“microsoft_edge_recommended”，取决于你是设置强制策略还是推荐的策略。 |
| \<ADMXCategory>   | 该策略的“parentCategory”在 ADMX 文件中定义。 如果策略未分组（未定义“parentCategory”），则省略 `<ADMXCategory>`。 |
| \<PolicyName>     | 策略名称可在[浏览器策略参考](./microsoft-edge-policies.md)文章中找到。 |

#### <a name="uri-path-example"></a>URI 路径示例：

在此示例中，假定 `<ADMXIngestName>` 节点被命名为“Edge”，并且你正在设置强制策略。 URI 路径将为：<br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~<ADMXCategory>/<PolicyName>`*

如果策略不在组中（例如，DiskCacheSize），则删除“`~<ADMXCategory>`”。 将 `<PolicyName>` 替换为策略的名称 DiskCacheSize。 URI 路径将为：<br/><br/>
*`./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/DiskCacheSize`*

如果策略位于组中，请执行以下步骤：

1. 使用任何 xml 编辑器打开 **msedge.admx**。
2. 搜索你想要设置的策略名称。 例如，“ExtensionInstallForceList”。
3. 使用 *parentCategory* 元素中 *ref* 属性的值。 例如，\<parentCategory ref=" Extensions"/>中的“Extensions”。
4. 将 `<ADMXCategory>` 替换为 *ref* 属性值以构造 URI 路径。 URI 路径将为：<br/><br/>
*`/Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Extensions/ExtensionInstallForcelist`*

### <a name="specify-the-data-type"></a>指定数据类型

OMA-URI 数据类型始终为“字符串”。

### <a name="set-the-value-for-a-browser-policy"></a>设置浏览器策略的值

本部分介绍了如何为每种数据类型设置 XML 格式的值。 转到[浏览器策略参考](./microsoft-edge-policies.md)以查找策略的数据类型。

> [!NOTE]
> 对于非布尔型数据类型，该值始终以 `<enabled/>` 开头。

#### <a name="boolean-data-type"></a>布尔型数据类型

对于布尔型类型的策略，请使用 `<enabled/>` 或 `<disabled/>`。

#### <a name="integer-data-type"></a>整数数据类型

该值始终需要以 `<enabled/>` 元素开头，后跟 `<data id="[valueName]" value="[decimal value]"/>`。

若要查找新选项卡页的值名称和小数值，请执行以下步骤：

1. 使用任何 xml 编辑器打开 **msedge.admx**。
2. 搜索名称属性与要设置的策略名称匹配的 `<policy>` 元素。 对于“RestoreOnStartup”，搜索 `name="RestoreOnStartup"`。
3. 在 `<elements>` 节点中，查找要设置的值。
4. 使用 `<elements>` 节点中“valueName”属性中的值。 对于“RestoreOnStartup”，“valueName”是“RestoreOnStartup”。
5. 使用 `<decimal>` 节点中“value”属性中的值。 若要使“RestoreOnStartup”打开新选项卡页，该值为“5”。

若要在启动时打开新选项卡页，请使用：<br>
`<enabled/> <data id="RestoreOnStartup" value="5"/>`

#### <a name="list-of-strings-data-type"></a>字符串列表数据类型

该值始终需要以 `<enabled/>` 元素开头，后跟 `<data id="[listID]" value="[string 1];[string 2];[string 3]"/>`。

> [!NOTE]
> 即使大多数情况下“Id=”属性名称与策略名称匹配，但该属性名称不是策略名称。 它是 ADMX 文件中的 \<list> 节点 ID 属性值。

若要查找 listID 并定义阻止 URL 的值，请执行以下步骤：

1. 使用任何 xml 编辑器打开 **msedge.admx**。
2. 搜索名称属性与要设置的策略名称匹配的 `<policy>` 元素。 对于“URLBlocklist”，搜索 `name="URLBlocklist"`。
3. 使用 `<list> node for [listID]` 的“id”属性中的值。
4. “值”是由分号 (;) 分隔的 URL 列表

例如，用于阻止访问 `contoso.com` 和 `https://ssl.server.com`：<br>
`<enabled/> <data id=" URLBlocklistDesc" value="contoso.com;https://ssl.server.com"/>`

#### <a name="dictionary-or-string-data-type"></a>字典或字符串数据类型

该值始终需要以 `<enabled/>` 开头，后跟 `<data id="[textID]" value="[string]"/>`。

若要查找 textID 并定义值来设置区域设置，请执行以下步骤：

1. 使用任何 xml 编辑器打开 **msedge.admx**。
2. 搜索名称属性与要设置的策略名称匹配的 `<policy>` 元素。 对于“ApplicationLocaleValue”，搜索 `name="ApplicationLocaleValue"`。
3. 对于 `[textID]`，请使用 `<text>` 节点“id”属性中的值。
4. 将“值”设置为区域性代码。

若要使用“ApplicationLocaleValue”策略将区域设置设为“es-US”，请执行以下操作：<br>
`<enabled/> <data id="ApplicationLocaleValue" value="es-US"/>`

### <a name="create-the-oma-uri-for-a-recommended-policies"></a>为推荐的策略创建 OMA-URI

为推荐的策略定义 URI 路径取决于你要配置的策略。

#### <a name="to-define-the-uri-path-for-a-recommended-policy"></a>要为推荐的策略定义 URI 路径，请执行以下步骤

使用 URI 路径公式（*`./Device/Vendor/MSFT/Policy/Config/<ADMXIngestName>~Policy~<ADMXNamespace>~<ADMXCategory>/<PolicyName>`*）和以下步骤定义 URI 路径：

1. 使用任何 xml 编辑器打开 **msedge.admx**。
2. 如果要配置的策略不在组中，请跳到第 4 步，然后从路径中删除 `~<ADMXCategory>`。
3. 如果要配置的策略位于组中：

   - 若要查找 `<ADMXCategory>`，请搜索要设置的策略。 搜索时，将“_recommended”附加到策略名称。 例如，搜索“RegisteredProtocolHandlers_recommended”的结果如下：

        ```xml
         <policy class="Both" displayName="$(string.RegisteredProtocolHandlers)" explainText="$(string.RegisteredProtocolHandlers_Explain)" key="Software\Policies\Microsoft\Edge\Recommended" name="RegisteredProtocolHandlers_recommended" presentation="$(presentation.RegisteredProtocolHandlers)">
           <parentCategory ref="ContentSettings_recommended"/>
           <supportedOn ref="SUPPORTED_WIN7_V77"/>
           <elements>
             <text id="RegisteredProtocolHandlers" maxLength="1000000" valueName="RegisteredProtocolHandlers"/>
           </elements>
         </policy>
        ```

   - 从 `<parentCategory>` 元素中复制 *ref* 属性的值。 对于“ContentSettings”，请从 `<parentCategory ref=" ContentSettings_recommended"/>` 中复制“ContentSettings_recommended”。
   - 将 `<ADMXCategory>` 替换为 *ref* 属性值以在 URI 路径公式中构造 URI 路径。

4. `<PolicyName>` 是附加了“_recommended”的策略的名称。

#### <a name="oma-uri-path-examples-for-recommended-policies"></a>适用于推荐的策略的 OMA-URI 路径示例

下表显示了推荐策略的 OMA-URI 路径的示例。

|              策略               |             OMA-URI                      |
|-----------------------------------|------------------------------------------|
| [RegisteredProtocolHandlers](./microsoft-edge-policies.md#registeredprotocolhandlers)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~ContentSettings_recommended/RegisteredProtocolHandlers_recommended`                        |
| [PasswordManagerEnabled](./microsoft-edge-policies.md#passwordmanagerenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~PasswordManager_recommended/PasswordManagerEnabled_recommended`                        |
| [PrintHeaderFooter](./microsoft-edge-policies.md#printheaderfooter)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Printing_recommended/PrintHeaderFooter_recommended`                        |
| [SmartScreenEnabled](./microsoft-edge-policies.md#smartscreenenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~SmartScreen_recommended/SmartScreenEnabled_recommended`                        |
| [HomePageLocation](./microsoft-edge-policies.md#homepagelocation)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Startup_recommended/HomepageLocation_recommended`                        |
| [ShowHomeButton](./microsoft-edge-policies.md#showhomebutton)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~Startup_recommended/ShowHomeButton_recommended`                        |
| [FavoritesBarEnabled](./microsoft-edge-policies.md#favoritesbarenabled)                       | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge_recommended~/FavoritesBarEnabled_recommended`                        |

### <a name="oma-uri-examples"></a>OMA-URI 示例

OMA-URI 示例及其 URI 路径、类型和示例值。

#### <a name="boolean-data-type-examples"></a>布尔型数据类型示例

*[ShowHomeButton](./microsoft-edge-policies.md#showhomebutton):*

| 字段   | 值                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 名称    | Microsoft Edge：ShowHomeButton                                                       |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/ShowHomeButton` |
| 类型    | 字符串                                                                               |
| 值   | `<enabled/>`                                                                          |

*[DefaultSearchProviderEnabled](./microsoft-edge-policies.md#defaultsearchproviderenabled)：*

| 字段   | 值                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 名称    | Microsoft Edge：DefaultSearchProviderEnabled                                         |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~DefaultSearchProvider/DefaultSearchProviderEnabled`    |
| 类型    | 字符串                                                                               |
| 值   | `<disable/>`                                                                          |

### <a name="integer-data-type-examples"></a>整数数据类型示例

*[AutoImportAtFirstRun](./microsoft-edge-policies.md#autoimportatfirstrun)：*

| 字段   | 值                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 名称    | Microsoft Edge：AutoImportAtFirstRun                                                 |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/AutoImportAtFirstRun`   |
| 类型    | 字符串                                                                               |
| 值   | `<enabled/><data id="AutoImportAtFirstRun" value="1"/>`                             |

*[DefaultImagesSetting](./microsoft-edge-policies.md#defaultimagessetting)：*

| 字段   | 值                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 姓名    | Microsoft Edge：DefaultImagesSetting                                                 |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ContentSettings/DefaultImagesSetting`    |
| 类型    | 字符串                                                                               |
| 值   | `<enabled/><data id="DefaultImagesSetting" value="2"/>`                             |

*[DiskCacheSize](./microsoft-edge-policies.md#diskcachesize)：*

| 字段   | 值                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 名称    | Microsoft Edge：DiskCacheSize                                                        |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge/DiskCacheSize`        |
| 类型    | 字符串                                                                               |
| 值   | `<enabled/><data id="DiskCacheSize" value="1000000"/>`                               |

#### <a name="list-of-strings-data-type-examples"></a>字符串列表数据类型示例
<!--
*[NotificationsAllowedForUrls](./microsoft-edge-policies.md#NotificationsAllowedForUrls):*

| Field   | Value                                                                                |
|---------|--------------------------------------------------------------------------------------|
| Name    | Microsoft Edge: NotificationsAllowedForUrls                                          |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ContentSettings/NotificationsAllowedForUrls`    |
| Type    | String                                                                               |
| Value   | `<enabled/><data id="NotificationsAllowedForUrlsDesc" value="https://www.contoso.com"/>`<br>For multiple list items: `<data id="NotificationsAllowedForUrlsDesc" value="https://www.contoso.com;[*.]contoso.edu"/>`                           |
-->
*[RestoreOnStartupURLS](./microsoft-edge-policies.md#restoreonstartupurls)：*

| 字段   | 值                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 名称    | Microsoft Edge：RestoreOnStartupURLS                                                 |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/RestoreOnStartupURLs`    |
| 类型    | 字符串                                                                               |
| 值   | `<enabled/><data id="RestoreOnStartupURLsDesc" value="1&#xF000;http://www.bing.com"/>`<br>对于多个列表项目： `<enabled/><data id="RestoreOnStartupURLsDesc" value="1&#xF000;http://www.bing.com&#xF000;2&#xF000;http://www.microsoft.com"/>`  |

*[ExtensionInstallForcelist](./microsoft-edge-policies.md#extensioninstallforcelist)：*

| 字段   | 值                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 名称    | Microsoft Edge：ExtensionInstallForcelist                                            |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Extensions/ExtensionInstallForcelist`    |
| 类型    | 字符串                                                                               |
| 值   | `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000;gbchcmhmhahfdphkhkmpfmihenigjmpp;https://extensionwebstorebase.edgesv.net/v1/crx"/>`                               |

#### <a name="dictionary-and-string-data-type-example"></a>字典和字符串数据类型示例

*[ProxyMode](./microsoft-edge-policies.md#proxymode)：*

| 字段   | 值                                                                                |
|---------|--------------------------------------------------------------------------------------|
| 名称    | Microsoft Edge：ProxyMode                                                            |
| OMA-URI | `./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~ProxyMode/ProxyMode`  |
| 类型    | 字符串                                                                               |
| 值   | `<enabled/><data id="ProxyMode" value="auto_detect"/>`                               |

## <a name="configure-microsoft-edge-in-intune-using-admx-ingestion"></a>使用 ADMX 引入在 Intune 中配置 Microsoft Edge

使用 Microsoft Intune 配置 Microsoft Edge 的推荐方法是使用管理模板配置文件，如[使用 Microsoft Intune 配置 Microsoft Edge 策略设置](./configure-edge-with-intune.md)中所述。 如果想要评估 Intune 内的 Microsoft Edge 管理模板中当前不可用的策略，你可以使用 [Intune 中 Windows 10 设备的自定义设置](/intune/configuration/custom-settings-windows-10)来配置 Microsoft Edge。

本部分介绍了以下操作方法：

1. [将 Microsoft Edge ADMX 文件引入到 Intune 中](#ingest-the-microsoft-edge-admx-file-into-intune)
2. [在 Intune 中使用自定义 OMA-URI 设置策略](#set-a-policy-using-custom-oma-uri-in-intune)

> [!IMPORTANT]
> 最佳做法是，不要使用自定义 OMA-URI 配置文件和管理模板配置文件来配置 Intune 中的相同 Microsoft Edge 设置。 如果同时使用自定义 OMA-URI 和管理模板配置文件部署同一策略，但使用的值不同，则用户将获得不可预知的结果。 我们强烈建议在使用管理模板配置文件之前删除 OMA-URI 配置文件。

### <a name="ingest-the-microsoft-edge-admx-file-into-intune"></a>将 Microsoft Edge ADMX 文件引入到 Intune 中

本节介绍了如何将 Microsoft Edge 管理模板（**msedge admx**文件）引入到 Intune 中。

> [!WARNING]
> 请不要在引入文件之前修改 ADMX 文件。

要引入 ADMX 文件，请执行以下步骤：

1. 从 [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)下载 Microsoft Edge 策略模板文件 (MicrosoftEdgePolicyTemplates.cab)，然后提取内容。 你想要引入的文件是 **msedge.admx**。
2. 登录到 [Microsoft Azure 门户](https://portal.azure.com)。
3. 从**所有服务**中选择 _Intune_，或在门户搜索框中搜索 Intune。
4. 从 _Microsoft Intune - 概述_中，选择**设备配置** | **配置文件**。
5. 在顶部命令栏中，选择 **+ 创建配置文件**。

   ![创建设备配置文件](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile.png)

6. 提供以下配置文件信息：

   - **名称**：输入描述性名称。 在此示例中，描述性名称为“Microsoft Edge ADMX 引入了配置”。
   - **描述**：为此配置文件输入可选描述。
   - **平台**：选择“Windows 10 和更高版本”
   - **配置文件类型**：选择“自定义”

7. 在**自定义 OMA-URI 设置**中，单击**添加**以添加 ADMX 引入。

   ![为 OMA-URI 添加引入](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile-add-omauri.png)

8. 在**添加行**上，提供以下信息：

   - **名称**：输入描述性名称。 在此示例中，使用“Microsoft Edge ADMX 引入”。
   - **描述**：为设置输入可选描述。
   - **OMA-URI**：输入“*/Device/Vendor/MSFT/Policy/ConfigOperations/ADMXInstall/Edge/Policy/EdgeAdmx*”
   - **数据类型**：选择“字符串”
   - **值**：选择**数据类型**后，将显示此输入区域。 从你在第 1 步中提取的 Microsoft Edge 策略模板文件中打开 msedge.admx 文件。 从 msedge.admx 文件中复制**所有文本**，然后将其粘贴到以下屏幕截图中显示的**值**文本区域中。

        ![添加 ADMX 引入](./media/edge-cfg-with-mdm/configure-edge-intune-mdm-omauri-addrow-ingest.png)

   - 单击**确定**。

9. 在**自定义 OMA-URI 设置**上，单击**确定**。
10. 在**创建配置文件**上，单击**创建**。 下一张屏幕截图显示有关新创建的配置文件的信息。

    ![新设备配置文件信息 ](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-create-profile-done.png)

<!--
> [!NOTE]
> You can use the preceding steps to ingest the msedgeupate.admx policy template file.
-->
### <a name="set-a-policy-using-custom-oma-uri-in-intune"></a>在 Intune 中使用自定义 OMA-URI 设置策略

> [!NOTE]
> 在执行此部分中的步骤之前，必须完成[将 Microsoft Edge ADMX 文件引入到 Intune 中](#ingest-the-microsoft-edge-admx-file-into-intune)中描述的步骤。

1. 登录到 [Microsoft Azure 门户](https://portal.azure.com)。
2. 从**所有服务**中选择 _Intune_，或在门户搜索框中搜索 Intune。
3. 转到 **Intune**>**设备配置**>**配置文件**。
4. 选择“Microsoft Edge ADMX 引入了配置”配置文件或用于此配置文件的名称。
5. 若要添加 Microsoft Edge 策略设置，你必须打开**自定义 OMA-URI 设置**。 在**管理**下面，依次单击**属性**和**设置**。

    ![配置配置文件设置](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-add-policy-settings.png)

6. 在**自定义 OMA-URI 设置**上，单击**添加**。

    ![向 OMA-URI 设置添加行](./media/edge-cfg-with-mdm/configure-edge-mdm-intune-add-policy-settings-add-row.png)

7. 在**添加行**上，提供以下信息：

   - **名称**：输入描述性名称。 我们建议使用要配置的策略名称。 在此示例中，请使用“ShowHomeButton”。
   - **描述**（可选）：为设置输入描述。
   - **OMA-URI**：针对策略输入 OMA-URI。 以“ShowHomeButton”策略为例，请使用此字符串：“*./Device/Vendor/MSFT/Policy/Config/Edge~Policy~microsoft_edge~Startup/ShowHomeButton*”
   - **数据类型**：选择策略设置数据类型。 对于“ShowHomeButton”策略，请使用“字符串”
   - **值**：输入要为策略配置的设置。 对于“ShowHomeButton”示例，请输入“\<enabled/>”。 下面的屏幕截图显示了用于配置策略的设置。

        ![添加“自定义 OMA-URI 设置”行](./media/edge-cfg-with-mdm/configure-edge-mdm-custom-omauri-setting.png)

   - 单击**确定**。

8. 在**自定义 OMA-URI 设置**上，单击**确定**。
9. 在 **Microsoft Edge ADMX 引入了配置 - 属性**配置文件（或你使用的名称）上，单击**保存**。

创建配置文件并设置属性后，必须[在 Microsoft Intune 中分配配置文件](/intune/configuration/device-profile-assign)。

#### <a name="confirm-that-the-policy-was-set"></a>确认策略已设置

使用以下步骤确认 Microsoft Edge 策略正在使用你创建的配置文件。 （给 Microsoft Intune 一些时间，以将策略传播到你在“Microsoft Edge ADMX 引入了配置”配置文件示例中分配的设备。）

1. 打开 Microsoft Edge，然后转到 *edge://policy*。
2. 在**策略**页上，查看是否已列出你在配置文件中设置的策略。
3. 如果未显示你的策略，请参阅[诊断 Windows 10 中的 MDM 故障](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10)或[策略设置疑难解答](#troubleshoot-a-policy-setting)。

#### <a name="troubleshoot-a-policy-setting"></a>策略设置疑难解答

如果 Microsoft Edge 策略未生效，请尝试执行以下步骤：

在目标设备（你在 Microsoft Intune 中将配置文件分配到的设备）上打开 *edge://policy* 页面，然后搜索该策略。 如果该策略未在 *edge://policy* 页面上，请尝试以下操作：

- 检查该策略是否在注册表中并且正确无误。 在目标设备上，打开 Windows 10 注册表编辑器（**Windows 键 + r**，输入“*regedit*”，然后按 **Enter**）。检查是否在 *\Software\Policies\ Microsoft\Edge* 路径中正确定义了此策略。 如果未在预期路径中找到此策略，则不会正确地将策略推送到设备。
- 请检查 OMA-URI 路径是否正确，并且该值是否为有效的 XML 字符串。 如果其中任何一个不正确，则不会将策略推送到目标设备。

有关更多疑难解答提示，请参阅[设置 Microsoft Intune](/intune/fundamentals/setup-steps) 和[同步设备](/intune/remote-actions/device-sync)。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [使用 Microsoft Intune 配置 Microsoft Edge 策略设置](configure-edge-with-intune.md)
- [移动设备管理](/windows/client-management/mdm/)
- [在 Intune 中对 Windows 10 设备使用自定义设置](/intune/configuration/custom-settings-windows-10)
- [Win32 和桌面桥应用策略配置](/windows/client-management/mdm/win32-and-centennial-app-policy-configuration)
- [了解 ADMX 支持的策略](/windows/client-management/mdm/understanding-admx-backed-policies)