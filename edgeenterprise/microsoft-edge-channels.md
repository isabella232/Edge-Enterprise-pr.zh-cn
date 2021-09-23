---
title: Microsoft Edge 渠道概述
ms.author: srugh
author: RyanHechtMSFT
manager: seanlynd
ms.date: 09/23/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 渠道概述
ms.openlocfilehash: dd65d932950be90d3d9278fa41ae843335b2074d
ms.sourcegitcommit: 8e5294e82cf62abc916cfd24692f55925330d42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2021
ms.locfileid: "12037183"
---
# <a name="overview-of-the-microsoft-edge-channels"></a>Microsoft Edge 渠道概述

Microsoft Edge 下一版本的优点之一是 Microsoft 可定期提供新功能。 但是，你作为将 Microsoft Edge 部署到组织中的用户的管理员，可能要更细致地控制你的用户多久获取一次这些新功能。 Microsoft 为你提供四个称为“渠道”的选项以控制多久用新功能更新一次 Microsoft Edge。 下面是这四个选项的概述。

有关每个频道支持的详细信息，请阅读: [Microsoft Edge 生命周期](/deployedge/microsoft-edge-support-lifecycle)
  
> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="channel-overview"></a>渠道概述

|频道|主要用途|多久用新功能更新一次|是否受支持？|
|:---:|---|:---:|:---:|
|[Stable](#stable-channel)|广泛部署|~4 周|是|
|[扩展稳定](#extended-stable-channel)|与较长的发布周期保持一致的稳定企业发布选项 |~8 周|是|
|[Beta](#beta-channel)|在组织中进行代表性验证|~4 周|是|
|[Dev](#dev-channel)|规划和开发|每周|否|
|[Canary](#canary-channel)|最前沿并有风险的内容|每天|否|

决定向用户部署的更新频道取决于多种因素，例如用户利用的业务线应用程序数量，以及用户拥有更新版本的 Microsoft Edge 时需要测试这些应用程序。 要帮助你做出此决策，请查看以下关于为 Microsoft Edge 提供的四个更新渠道的信息。

### <a name="stable-channel"></a>Stable 渠道

Stable 渠道旨在广泛部署到你的组织中，它是大多数用户应所处的渠道。 它是最稳定的渠道，并且是之前 Beta 渠道版本中提供的功能集稳定的结果。 大约每 4 周提供一次新功能。 根据需要推出安全和质量更新。 Stable 渠道中的版本将一直提供服务，直至推出此渠道中的下一版本为止。

### <a name="beta-channel"></a>Beta 渠道

Beta 渠道旨在将它部署到你的组织中一组有代表性的示范用户进行生产活动。 它是受支持的版本，并且 Beta 中的每个版本均提供服务，直至发布此渠道中的下一版本为止。 这是一个好机会，可验证在你的环境中一切符合预期，并且如果你遇到问题，可在该版本发布到 Stable 渠道之前修复该问题。 大约每 4 周提供一次新功能。 根据需要推出安全和质量更新。

### <a name="dev-channel"></a>Dev 渠道

Dev 渠道旨在帮助你用 Microsoft Edge 的最新功能进行规划和开发，但质量高于 Canary 渠道。 借此机会，你可以提前了解后续功能并为下一 Beta 版本做好准备。

### <a name="canary-channel"></a>Canary 渠道

Canary 渠道每天发布一次，在所有渠道中最为前沿，但有风险。 如果你希望访问最新投资，它们首先将在此处显示。 由于此节奏的性质，问题将超时出现，因此，如果你要利用 Canary 版本，你可能希望并排安装另一个频道。

### <a name="extended-stable-channel"></a>扩展稳定渠道

与 Canary (Dev 和 Beta) 的预览频道不同，扩展稳定渠道不作为单独的浏览器应用程序提供;相反，它是适用于 Microsoft Edge Stable 应用程序的企业版本选项，与 Stable) 中的 4 周主要发布周期相反 (它与更长、8 周的主要发布周期相对。 尽管我们建议在 4 周发布周期自动更新 Stable，但扩展稳定的存在可以更有效地为可能需要更长的时间线来测试和验证新浏览器版本的组织提供服务。

Microsoft Edge Stable 的 8 周"扩展稳定"发布周期选项提供与从 Microsoft Edge 94__ 开始的编号为一致的累积功能更新;奇数版本的任何功能更新都将打包，并作为后续偶数版中的一部分提供。 例如，如果组织选择使用 Microsoft Edge 94 的 8 周"扩展稳定"发布周期，他们将收到 Microsoft Edge 96、Microsoft Edge 98 等的后续功能更新。 虽然功能更新根据所选的发布周期打包并随新版本一起提供，但重要的安全修补程序和修补程序将根据需要提供，独立于所选的发布选项，以帮助维护浏览器安全。 客户随时可以选择加入扩展稳定版本选项，它将在下一个扩展稳定版本生效。

![比较 Stable Microsoft Edge扩展稳定发布周期选项的示例。](./media/microsoft-edge-channels/extended-stable-explainer.png)

#### <a name="opting-in-to-the-extended-stable-release-cadence"></a>选择加入扩展稳定发布节奏

##### <a name="opting-in-to-extended-stable-on-windows-with-automatic-updates-recommended"></a>选择加入使用自动更新Windows扩展稳定 (推荐) 

如果自动更新Microsoft Edge，可以使用组策略对象选择加入扩展稳定发布节奏。 [若要详细了解](/DeployEdge/configure-microsoft-edge#1-download-and-install-the-microsoft-edge-administrative-template)下载和安装最新的组策略管理模板，Microsoft Edge本指南。

1. 打开本地组策略编辑器，然后转到“_计算机配置”>“管理模板”>“Microsoft Edge 更新”>“应用程序”>“Microsoft edge”>_。
2. 选择 **"目标通道覆盖"，** 然后选择"已启用 **"。**
3. 在 **选项**下， **从策略下拉列表** 中选取"扩展稳定"。

当对扩展稳定渠道的下一次更新的版本号大于当前安装的版本时，Microsoft Edge自动更新到扩展稳定渠道。 上的版本 `edge://settings/help` 字符串将指示您运行的是其他通道。

> [!NOTE]
> 当扩展稳定渠道上存在新更新，其版本号大于 (主要或次要) 比当前安装在你的设备上时，选择加入扩展稳定将生效。 如果你运行的是最新版本的 Microsoft Edge Stable，并且选择加入扩展稳定版，它将随下一个修补程序或 Microsoft Edge。
>
> 默认情况下，Microsoft Edge不会降级自身。 如果你当前运行的是奇数版本的 Microsoft Edge Stable，选择加入扩展稳定意味着你将在下次偶数编号发布之前不会收到Microsoft Edge更新。
>
> 如果你想要确保所有设备都从特定版本的扩展稳定开始，可以将该特定版本的 Edge Stable 部署为已启用回滚的 MSI。 例如，如果你想要从扩展稳定 94 开始，但某些设备已更新到 Stable 95，你可以部署启用了回滚的边缘 94 的 MSI。 若要详细了解如何在启用回滚功能时部署边缘 MSIS，请参阅 [回滚指南](/DeployEdge/edge-learnmore-rollback)。

##### <a name="opting-in-to-extended-stable-on-windows-via-intune"></a>通过 Intune 选择加入 Windows Stable

Microsoft Edge管理模板的管理方式与管理中心中的本地组策略Microsoft Endpoint Manager类似。 按照使用[Intune Microsoft Edge指南](/mem/intune/configuration/administrative-templates-configure-edge)操作。 

"目标**通道覆盖**"设置位于"Microsoft Edge 更新 >_Applications>Microsoft Edge"_ 子文件夹下。 它应设置为"**扩展稳定"** 

当对扩展稳定渠道的下一次更新的版本号大于当前安装的版本时，Microsoft Edge自动更新到扩展稳定渠道。 上的版本 `edge://settings/help` 字符串将指示您运行的是其他通道。

##### <a name="opting-in-to-extended-stable-on-windows-via-configuration-manager"></a>通过 Configuration Manager 选择加入 Windows Stable

请参阅我们的有关使用 Configuration [Manager Microsoft Edge](/mem/configmgr/apps/deploy-use/deploy-edge#update-microsoft-edge)更新指南，了解有关如何在 Configuration Manager 中同步和批准Microsoft Edge更新的信息。

扩展稳定更新分发在软件库中的"Microsoft Edge"产品类别下，类似于 Stable、Beta 和 Dev 渠道的现有更新。 但是，与适用于其自己的浏览器应用程序的 Beta 和 Dev 不同，扩展稳定更新适用于 Microsoft Edge Stable 应用程序。 因此，为了Windows更新客户端确定是应用稳定更新还是扩展稳定更新，它会检查"目标渠道覆盖"组策略的状态。 如果未配置策略或未设置为"稳定"，将应用稳定更新。 如果设置为"扩展稳定"，将应用扩展稳定更新。 有关如何正确设置组策略的说明，请按照上述说明选择加入使用自动更新的扩展稳定。 

## <a name="flighting-pre-release-channels-in-your-organization"></a>在组织中对预发布频道进行航班

"目标通道覆盖"组策略还可用于在组织中无缝测试 Microsoft Edge 的预发布通道，而无需用户使用第二个 Web 浏览器应用程序。 例如，你可以为组织中具有代表性的用户示例集将"目标通道覆盖"策略设置为"Beta"。 当这些用户打开Microsoft Edge时，他们将运行 Beta 渠道版本，而不是 Stable (，他们甚至不会意识到！) 。 这可让你提前了解下一版本的 Microsoft Edge 在企业中的表现，并帮助验证一切是否在你的环境中都如期工作。 你将从遇到任何问题的用户收到早期信号，并且可以确保在将版本发布到稳定渠道之前修复它们。 作为用户问题疑难解答的一部分，版本字符串 将通知你用户的渠道是否不同于默认的 `edge://settings/help` Stable 渠道。

> [!NOTE]
> 由于在 Microsoft Edge 的"Beta"和"开发"渠道上构建的主要版本号大于"Stable"版本，因此如果你对"Beta"或"Dev"渠道进行更新，并且希望恢复为稳定，Microsoft Edge 的回滚功能是必需的。 [](/DeployEdge/edge-learnmore-rollback) 只需将"目标渠道覆盖"设置回 Stable，意味着在最新稳定版本的版本号比当前在你的设备上运行的 Microsoft Edge版本更高的版本之前，你将收到任何更新。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [渠道下载](https://aka.ms/EdgeEnterprise)
