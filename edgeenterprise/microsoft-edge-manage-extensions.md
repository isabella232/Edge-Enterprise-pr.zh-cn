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
ms.openlocfilehash: 69c10bfa1e041d48f99594e6ac85dd39ba66379ca8d6d7fe12f1bdef6f3b54fe
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "11724906"
---
# <a name="manage-microsoft-edge-extensions-in-the-enterprise"></a>在企业中管理 Microsoft Edge 扩展

本文为在其组织中管理 Microsoft Edge 扩展的管理员提供最佳做法指南。 可以使用本文中的信息来制定管理组织中扩展的策略。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="introduction"></a>简介

组织希望保护公司和用户数据并评估浏览器扩展，以确保其安全且与企业相关。 管理员希望:

- 防止安装错误的应用和扩展。
- 保留用户完成其工作所需的扩展。
- 管理对用户和公司数据的访问。  

本文是系列文章中的第一篇，可帮助管理员管理扩展，为用户提供安全高效的体验。 本系列介绍不同的选项，并帮助你选择管理扩展的最佳方法。 本系列由以下文章组成：

- [在企业中管理的 Microsoft Edge 扩展](microsoft-edge-manage-extensions.md)。 创建管理扩展的策略，并设置管理浏览器所需的管理模板。
- [使用组策略管理 Microsoft Edge 扩展](microsoft-edge-manage-extensions-policies.md)。 使用组策略管理扩展的选项。
- [创建用于托管 Microsoft Edge 扩展的 Web 应用商店](microsoft-edge-manage-extensions-webstore.md)。 创建和托管扩展。
- [Microsoft Edge 扩展的常见问题解答](microsoft-edge-manage-extensions-faq.md)。 常见问题。

## <a name="things-to-consider-when-managing-extensions"></a>管理扩展时需考虑的事项

用户需要访问某些应用、网站和扩展以完成其工作，同时还需保护用户和公司数据。 有效的安全策略包括为企业提出正确的问题，以及扩展如何满足公司的需求。 要提出的一些关键问题包括：

- 我需要遵守哪些法规和合规性措施？
- 某些扩展是否要求具有过于广泛的权限，这可能会违反我公司的数据安全策略？
- 我的用户设备上存储了多少用户或公司数据？

回答这些问题时，可以使用 Microsoft Edge 提供的粒度策略：

- 根据数据保护策略在用户的计算机上阻止或允许扩展。
- 在用户的设备上强制安装扩展，以便他们拥有提高工作效率所需的工具。
- “允许列表”或“阻止列表”扩展，以允许用户拥有其工作所需的最少权限。

传统的扩展管理模式对特定扩展使用“允许列表”和“阻止列表”的方法。 然而，Microsoft Edge 也让你管理扩展程序所要求的权限。 使用此模型，可以决定要允许扩展在计算机和设备上使用哪些权限，然后实施全局策略，根据要求允许或阻止扩展。  

## <a name="understand-extension-permissions"></a>了解扩展权限

扩展可能需要拥有在设备或网页上进行更改的权限才能才能正常运行。 这些权利称为权限。 开发人员必须列出其扩展所需的权限和访问权限。 权限有两个主要类别，许多扩展需要以下两种权限：

- 主机权限要求扩展列出它可能查看或修改的网页。
- 设备权限是扩展在其运行的设备上所需的权利。

这些权限的一些示例包括：访问 USB 端口、存储或查看屏幕，以及与本机程序进行通信。  

## <a name="get-ready-to-manage-extensions"></a>准备好管理扩展

## <a name="before-you-begin"></a>在开始之前

扩展选项假定已为用户管理 Microsoft Edge。 关于为 Microsoft Edge 策略设置管理模板的更多信息，请参阅:

-   [在 Windows 上配置 Microsoft Edge 策略设置](/DeployEdge/configure-microsoft-edge)
-   [使用 Intune 为 Windows 配置](/mem/intune/configuration/administrative-templates-configure-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)
-   [使用移动设备管理为 Windows 配置](/deployedge/configure-edge-with-mdm)
-   [使用 .plist 为 macOS 配置](/deployedge/configure-microsoft-edge-on-mac)
-   [使用 Jamf 为 macOS 配置](/deployedge/configure-microsoft-edge-on-mac-jamf)

本文中的配置步骤是适用于 Windows，关于 MAC/Linux 中的相应实现，请参阅 Microsoft Edge 浏览器策略参考。

## <a name="decide-which-extensions-to-allow"></a>确定允许哪些扩展

大多数组织应按其权限以及其可访问的网站来管理扩展。 此方法更安全、更易于管理，并且对于大型组织是可缩放的。  

- 阻止/允许的权限 – 允许按其所需的权限来控制扩展。
- 运行时块主机 – 允许控制这些扩展可访问的网站。

使用此方法可以节省时间，因为只需设置一次。 使用运行时主机策略，最重要的站点将受到保护。还有其他选项，例如：

-   强制安装扩展 - 允许以无提示方式安装扩展。
-   “允许列表/阻止列表”（如果需要）– 确定允许安装哪些扩展。

使用以下步骤作为指南来确定在组织中允许哪些扩展。

1. 创建员工在其计算机上需要哪些扩展的列表。 在测试环境中测试扩展，以诊断与内部应用程序相关的任何兼容性问题。
2. 选择需要更安全保障的站点。

   - 了解需要阻止扩展对哪些敏感内部网站或域进行更改或从中读取数据。  
   - 通过在扩展运行时阻止 API 调用来阻止对这些站点的访问。 这包括阻止 Web 请求、读取 Cookie、JavaScript 注入、XHR 等。

3. 确定这些扩展运行所需的权限。 识别哪些权限会给用户带来潜在风险。

   - 审核用户已安装的扩展，并查看他们需要哪些权限。 可以查看扩展代码中 Web 应用清单的 JSON 文件。 执行以下步骤，了解扩展需要哪些权限：

     - 从 [Microsoft Edge 加载项](https://microsoftedge.microsoft.com/addons/) 网站或 [Chrome Web Store](https://chrome.google.com/webstore) 安装扩展。
     - 测试扩展并了解其在组织中的工作原理。
     - 通过导航到 *edge://extensions* 来查看扩展所需的权限。 例如，下一个屏幕截图中显示的 Microsoft Office 扩展请求“读取浏览历史记录”和“显示通知”的权限。 根据此扩展请求的权限级别来权衡此扩展的有用性。 批准组织的扩展后，使用以下工具对其进行管理。
   :::image type="content" source="media/microsoft-edge-manage-extensions/manage-extesions-office-extension.png" alt-text="具有权限的 Microsoft Office 扩展。":::

   - 可以在组织中批准用户之前，验证组织中的用户请求的扩展。 扩展使用的某些权限可能不明确。 对于关键业务应用，可以直接联系应用开发人员或供应商，以获取更多有关扩展的信息或查看源代码。 他们应能够详细地介绍该扩展可以在设备和网站上所进行的更改。
   - 查看“声明权限”列表，其中列出了扩展可以使用的所有权限。 从此列表中，可以决定要在组织中允许哪些权限。

4. 从收集的数据中创建主列表。此列表将包括以下信息：

   - **所需的扩展**。 此列表可以按部门、办公室位置或其他相关信息进行组织。
   - **扩展允许列表**。 具有权限可能遭到阻止但允许其运行的所需扩展。 用户需要这些扩展，或者通过与供应商的对话确定不会带来风险。
   - **扩展阻止列表**。 阻止安装的扩展。 此列表中的扩展不具有允许运行的权限。 还包括要保持安全且不允许扩展访问的核心站点和域。 稍后可以将此阻止列表与已有的其他阻止列表进行比较。 可能会发现可以放宽当前的阻止列表策略。

5. 向利益干系人和 IT 团队展示你的列表以获取支持。
6. 在实验室中或在组织中进行小型试点来测试新策略。
7. 分阶段向员工推出这些新策略集。 有关详细信息，请参阅 [使用组策略管理 Microsoft Edge 扩展](microsoft-edge-manage-extensions-policies.md)。
8. 查看用户的反馈。
9. 每月、每季度或每年重复并微调流程。

通过允许权限基线的强制实施和对敏感公司站点的保护，可以为企业提供更多安全性，同时为用户提供更好的体验。 员工可能会安装之前无法安装的扩展，但无法在敏感的业务网站上运行它们。  

## <a name="see-also"></a>另请参阅

- [使用组策略管理 Microsoft Edge 扩展](microsoft-edge-manage-extensions-policies.md)
- [创建用于托管 Microsoft Edge 扩展的 Web 应用商店](microsoft-edge-manage-extensions-webstore.md)
- [ExtensionSettings 策略参考指南](microsoft-edge-manage-extensions-ref-guide.md)
- [Microsoft Edge 扩展的常见问题解答](microsoft-edge-manage-extensions-faq.md)
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)