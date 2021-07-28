---
title: 自托管 Microsoft Edge 扩展
ms.author: aspoddar
author: AndreaLBarr
manager: balajek
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 了解如何在企业中打包和自托管 Microsoft Edge 扩展。
ms.openlocfilehash: 8b0e9ed346848f7ee9330c51f6a1c9274df89371
ms.sourcegitcommit: 9088e839e82d80c72460586e9af0610c6ca71b83
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2021
ms.locfileid: "11676109"
---
# <a name="self-host-microsoft-edge-extensions"></a>自托管 Microsoft Edge 扩展

本文提供有关将扩展打包到你自己的 Web 商店上托管的基本指南。 还包括有关如何将扩展部署到组织中的设备和用户的说明。

## <a name="prerequisites"></a>必备条件

若要自托管自己的扩展，需要为扩展及其清单文件提供自己的 Web 托管服务。

 以下步骤假定你已创建扩展，具有 XML 文件的一些经验，具有配置组策略的工作知识，并且知道如何使用 Windows 注册表。

## <a name="publish-an-extension"></a>发布扩展

发布扩展之前，需要将其打包到 CRX (Chrome 扩展) 文件中。 使用以下步骤作为打包扩展为 CRX 文件的指南。

1. 在 Microsoft Edge 地址栏中，转到"*edge://extensions*"，如果尚未启用，则打开"**开发工具**"模式。
2. 在 "**已安装的扩展**"下，单击 "**打包扩展**" 以创建 CRX 文件。
3. 使用 "**包扩展**" 对话框查找具有扩展源的目录。 选择目录，然后单击"**打包扩展**"。  这将创建 CRX 文件以及 PEM 文件。 保存 PEM 文件，因为对扩展进行版本更新需要该文件。 下一个屏幕截图显示了用于定位扩展根目录的"**包扩展**"对话框。

   :::image type="content" source="media/microsoft-edge-manage-extensions-webstore/manage-extensions-pack-dialog.png" alt-text="用于查找扩展的源代码的包扩展对话框。":::

   > [!IMPORTANT]
   > 将 PEM 文件存储在安全的位置，因为它是扩展的密钥，并且在将来更新时需要用到。

4. 将 CRX 文件拖动到扩展窗口中，并确保它可以加载。
5. 测试扩展并记下 ID 字段 (这是 CRX ID) 和版本号。 稍后将需要此信息。 下一个屏幕截图显示了具有 CRX ID 的测试扩展。

   :::image type="content" source="media/microsoft-edge-manage-extensions-webstore/manage-extensions-test-extension.png" alt-text="显示 CRX ID 的扩展示例":::

6. 将 CRX 文件上传到主机，并记下其下载位置的 URL。 XML 清单文件需要此信息。
7. 若要创建一个带有应用/扩展 ID、下载 URL 和版本的清单 XML 文件，请定义以下字段：  

   - **appid** - 步骤 5 中的扩展 ID
   - **codebase** - 步骤 6 中 CRX 文件的下载位置
   - **version** - 应用/扩展的版本，应该与扩展清单中指定的版本匹配。

   下一个代码段显示了 XML 清单文件的示例。

   ```xml
   <?xml version='1.0' encoding='UTF-8'?> 
   <gupdate xmlns='http://www.google.com/update2/response' protocol='2.0'> 
     <app appid='ekilpdeokbpjmminmhfcgkncmmohmfeb'> 
     <updatecheck codebase='https://app.somecompany.com/extensionfolder/helloworld.crx' version='1.0' /> 
     </app> 
   </gupdate> 
   ```

   有关详细信息，请参阅 [在 Microsoft Edge 中自动更新扩展 - Microsoft Edge 开发](/microsoft-edge/extensions-chromium/enterprise/auto-update)。

8. 将完成的 XML 文件上传到可下载的位置，并记录 URL。 使用组策略安装扩展时将需要此 URL。 请参阅 [分发专用托管的扩展](#distribute-a-privately-hosted-extension)。

   > [!IMPORTANT]
   > 扩展的托管位置不需要身份验证。 无论在何处使用用户设备，都要能够访问它。

## <a name="publish-updates-to-an-extension"></a>为扩展发布更新

更改并测试更新的扩展后，你可以发布它。 使用以下步骤作为发布更新的指南。

1. 使用下面的语法将扩展的 manifest.JSON 文件的版本号更改为更高的版本号：`"version":"versionString"`。 如果"版本"："1.0"，则可以更新为"版本"："1.1"或高于"1.0"的任何数字。
2. 更新 XML 文件中 `<updatecheck>` 的"版本"，以匹配在上一步输入清单文件的版本数值。 例如：<br>`<updatecheck codebase='https://app.somecompany.com/extensionfolder/helloworld.crx' version='1.1' />`
3. 创建包含新更改的 CRX 文件。 转到 *edge://extensions* 并启用 **开发人员模式**。
4. 单击 **打包扩展**，然后转到扩展源的目录。

   > [!IMPORTANT]
   > 使用在首次创建 CRX 文件时生成和保存的同一 PEM 文件。 如果不使用相同的 PEM 文件，扩展的应用 ID 将会更改，并且更新将被视为新扩展。

5. 将 CRX 文件拖放到扩展窗口中并验证它是否加载。 此操作后将禁用扩展。 若要启用它，请向 ExtensionInstallAllowList 策略添加扩展的 CRX ID。 
6. 测试更新的扩展。
7. 将旧的 CRX 文件和 XML 文件替换为已更新扩展的新文件。

将在下一个策略同步周期中选择扩展的更改。 有关更新扩展的详细信息，请参阅： [更新 URL](/microsoft-edge/extensions-chromium/enterprise/auto-update#update-url) 和 [更新清单](/microsoft-edge/extensions-chromium/enterprise/auto-update#updated-manifest)。

## <a name="distribute-a-privately-hosted-extension"></a>分发专用托管的扩展

你可以共享 CRX 文件的托管位置的链接，用户一旦在浏览器中输入 URL，就会下载并安装扩展。 用户可以从"edge://extensions"页面启用扩展。 若要允许用户安装自托管扩展，你需要将扩展 CRX ID 添加到 [ExtensionInstallAllowList](/deployedge/microsoft-edge-policies#extensioninstallallowlist) 策略，并添加 CRX 文件托管位置的 URL 到 [ExtensionInstallSources](/deployedge/microsoft-edge-policies#extensioninstallsources) 策略。

或者，可以使用组策略 [ExtensionInstallForceList](/deployedge/microsoft-edge-manage-extensions-policies#force-install-an-extension) 在用户的设备上强制安装扩展。

可以将这些策略应用于所选用户和/或设备。 请记住，策略更新不是即时更新，并且策略设置需要一段时间才能生效。

## <a name="see-also"></a>另请参阅

- [在企业中管理 Microsoft Edge 扩展](microsoft-edge-manage-extensions.md)
- [使用组策略管理 Microsoft Edge 扩展](microsoft-edge-manage-extensions-policies.md)
- [ExtensionSettings 策略的详细指南](microsoft-edge-manage-extensions-ref-guide.md)
- [Microsoft Edge 扩展的常见问题解答](microsoft-edge-manage-extensions-faq.md)
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
