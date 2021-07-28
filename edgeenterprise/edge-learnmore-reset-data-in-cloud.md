---
title: 重置 Microsoft Edge 数据
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 07/09/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 如何在云中重置 Microsoft Edge 数据
ms.openlocfilehash: 65984daea523a7749a28d8ab6a4dd990c5fea849
ms.sourcegitcommit: 9088e839e82d80c72460586e9af0610c6ca71b83
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2021
ms.locfileid: "11675921"
---
# <a name="reset-microsoft-edge-data-in-the-cloud"></a>重置云中的 Microsoft Edge 数据

本文介绍了在云中重置 Microsoft Edge 数据的步骤。

> [!NOTE]
> 除非另有说明，否则本文适用于 Microsoft Edge 版本 88 或更高版本。

> [!NOTE]
> 如果租户位于 GCC Mod 环境中，则租户管理员需要向 Microsoft 提交支持请求以重置数据。

## <a name="overview"></a>概述

在某些情况下，你想要在云中重置 Microsoft Edge 数据。 例如，您希望同步数据，但 Microsoft Edge 报告无法同步数据。 或者，你可能希望确保你的数据已从 Microsoft 云中删除。 在这两种情况下，Microsoft Edge 都允许您执行云数据重置。

## <a name="back-up-your-favorites"></a>备份收藏夹

在执行重置之前，我们建议你备份收藏夹。 使用以下步骤备份收藏夹。

1. 在 Microsoft Edge 中，选择**按 Ctrl + Shift + O > 选择三点键 > 单击“导出收藏夹”**。
2. 选择用来保存收藏夹的文件。 可以键入自己的文件名，或使用 Microsoft Edge 默认提供的名称“favorites_month_day_year.html”作为文件名。 例如，“favorites_07_05_21.html”。 如果稍后需要还原收藏夹，可以从该文件中还原。
3. 单击 **“保存”**。

## <a name="perform-a-reset-to-fix-a-synchronization-problem"></a>执行重置以修复同步问题

如果 Microsoft Edge 报告无法同步数据，并建议重置数据，请执行重置以修复此问题。

使用以下步骤执行重置。

1. 首先，确保已在所有设备（包括移动设备）上退出 Microsoft Edge，但执行重置的设备除外。 若要注销 Microsoft Edge，请选择 **“设置”>“个人资料”>“注销”**。退出时，请不要选择从本地设备清除收藏夹和设置等选项。
2. 注销所有其他设备后，在桌面上打开 Microsoft Edge。 选择 **“设置”>“个人资料”>“重置同步”**。在生成的对话框中，选择在重置数据后恢复同步，然后选择 **“立即重置”**。

## <a name="perform-a-reset-to-remove-your-data-from-microsofts-cloud"></a>执行重置以从 Microsoft 云中删除数据

如果要从 Microsoft 云中删除数据，请使用以下步骤执行重置。

1. 在设备上停止同步，（除要执行重置的设备以外）。  在 Microsoft Edge 中，选择**设置 > 个人资料 > 关闭同步**。  
2. 停止同步后，选择**设置 > 个人资料 > 重置同步**。在生成的对话框中，**请勿**在重置同步后在此设备上恢复同步。选择**重置**。

## <a name="what-to-expect-during-and-after-a-data-reset"></a>数据重置期间和之后的预期结果

数据重置可能需要几秒钟到几分钟，具体取决于你在 Microsoft 云中存储了多少数据。 在某些情况下，你可能会看到一条消息，指出无法完成重置，并建议再次重置。 在这种情况下，请等待几小时，然后再次尝试重置数据。 如果仍无法重置数据，请与 Microsoft Edge 支持部门联系。

成功完成数据重置后，如果选择在重置后恢复同步，数据将再次从设备同步。 如果你想要从这些设备同步，则需要在其他设备上重新登录。 但是，如果未选择恢复同步，则 Microsoft Edge 数据将从云中删除，并且数据将不再同步。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge Enterprise Sync](microsoft-edge-enterprise-sync.md)
