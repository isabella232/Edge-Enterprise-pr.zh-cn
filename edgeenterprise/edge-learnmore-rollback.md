---
title: Microsoft Edge 企业版回退
ms.author: v-danwes
author: dan-wesley
manager: srugh
ms.date: 02/04/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 如何将 Microsoft Edge 回退到以前的版本
ms.openlocfilehash: 58323071fcbe4704f29819684bb5359d92c030b6
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "11448156"
---
# <a name="how-to-roll-back-microsoft-edge-to-a-previous-version"></a>如何将 Microsoft Edge 回退到以前的版本

本文介绍如何使用“回退”功能回退到以前版本的 Microsoft Edge。 若要详细了解此功能，请观看[视频：Microsoft Edge 版本回退](microsoft-edge-video-version-rollback.md)。

>[!NOTE]
>本文适用于 Microsoft Edge 版本 86 或更高版本。

## <a name="introduction-to-rollback"></a>回退简介

回退可让你将 Microsoft Edge 浏览器版本替换为更早期版本。 此功能旨在为企业部署 Microsoft Edge 提供安全网络。 它提供了一种解决 Microsoft Edge 问题的方法。 回退的优点是能够轻松快速地还原到先前的浏览器版本。 回退会降低 Microsoft Edge 问题对企业运营的潜在影响。

## <a name="before-you-begin"></a>开始之前

请务必了解如何在 Microsoft Edge 环境中安装“回退”功能。 可使用两种不同方法部署回退：使用 MSI 手动部署或使用 Microsoft Edge 更新和组策略。 我们还鼓励通过使用组策略选择实现更流畅的部署。

### <a name="recommendations"></a>建议

回退功能旨在临时修复 Microsoft Edge 浏览器更新中可能发现的问题。 我们建议用户安装最新版本的 Microsoft Edge 浏览器，以使用最新安全更新提供的保护。 回退到较早版本存在遇到已知安全问题的风险。

在暂时回退浏览器版本之前，强烈建议你为组织中的所有用户启用同步。 如果未启用同步，则会存在永久丢失浏览数据的风险。 有关详细信息，请参阅 [Microsoft Edge 同步](microsoft-edge-enterprise-sync.md)。

> [!CAUTION]
> 请仅在必要时使用回退，因为始终存在数据丢失风险。

## <a name="enable-rollback-manually-with-an-msi"></a>启用通过 MSI 手动回退

请按照以下步骤手动使用 MSI 回退。

1. 禁用 Microsoft Edge 更新。

   > [!NOTE]
   > 建议安装最新的管理模板。 有关详细信息，请参阅[下载并安装 Microsoft Edge 管理模板](./configure-microsoft-edge.md#1-download-and-install-the-microsoft-edge-administrative-template)。

   - 打开本地组策略编辑器，然后转到“*计算机配置”>“管理模板”>“Microsoft Edge 更新”>“应用程序”>“Microsoft edge”>*。
   - 选择“**更新策略替代**”，然后选择“**已启用**”。
   - 在“**选项**”下，从“策略”下拉列表中选择“**已禁用更新**”。

2. 获取 MSI。

   - 从[这里](https://www.microsoft.com/edge/business/download)下载您想要回退到的版本的 MSI。
   - 将 MSI 保存到桌面。

3. 运行回退命令。

   - 使用“**以管理员身份运行**”打开 Windows 命令提示。
   - 键入以下命令，其中：*C:\Users\username\Desktop\test*  是已下载的 MSI 所在路径，FileName 是 .msi 文件的名称：<br>
 `C:\Users\username\Desktop\test>msiexec /I FileName.msi /qn ALLOWDOWNGRADE=1`<br>
     > [!NOTE]
     > 有关 msiexec 的详细信息，请参阅 [msiexec](/windows-server/administration/windows-commands/msiexec)。
   - 关闭并重新打开 Microsoft Edge，验证回退是否成功。 在“**设置”和“更多**” (ALT + F) 下，转到 “**设置**”并选择“**关于 Microsoft Edge**”。

## <a name="enable-rollback-with-microsoft-edge-update-and-group-policy"></a>使用 Microsoft Edge 更新和组策略启用回退

按照以下步骤可使用 Microsoft Edge 更新和组策略启用回退。

1. 打开本地组策略编辑器，然后转到“*计算机配置”>“管理模板”>“Microsoft Edge 更新”>“应用程序”>“Microsoft edge”>*。
2. 选择“**回退到目标版本**”，然后选择 “**已启用**”。
3. 选择“**目标版本替代**”，并选择要回退到的浏览器版本。
4. 选择“**更新策略替代**”，然后选择“**已启用**”。 在“**选项**”下，从“策略”下拉列表中选择以下选项之一（“**已禁用更新**”除外）：

   - 始终允许更新
   - 仅自动静默更新

     > [!NOTE]
     > 若要强制执行组策略更新，请在 Windows 管理员命令提示处`gpupdate /force`键入（以管理员身份运行）。

5. 单击**确定**保存策略设置。 将在下次 Microsoft Edge 更新检查更新时执行回退。 如果希望更快地进行更新，可以更改 Microsoft Edge 更新轮询间隔或使用 MSI 启用回退。

### <a name="common-rollback-errors"></a>常见回退错误

以下错误将阻止回退：

- 输入为不受支持的目标版本
- 输入为不存在的目标版本
- 输入未正确格式化。

### <a name="recommended-group-policies"></a>推荐的组策略

强烈推荐使用回退功能时采用以下组策略和设置。

#### <a name="sync-group-policies"></a>同步组策略

- ForceSync. 将 ForceSync 设置为“启用”。 此策略将强制启用所有 Azure Active Directory (Azure AD) 用户的同步。 此策略仅适用于 Microsoft Edge 版本 86 及更高版本。
- *配置从同步策略中排除的类型列表*允许管理员控制用户可同步哪些数据。

#### <a name="browser-restart-group-policies"></a>浏览器重新启动组策略

建议启用回退后，对用户强制重启。

- 启用*通知用户对于挂起的更新，推荐或需要重新启动浏览器*。 在“选项”下，选择“**必需**”。
- 启用*设置更新通知时间段，然后设置所需时间（以毫秒为单位）*。

## <a name="snapshot"></a>快照

快照是用户数据文件夹的版本标记副本。 在版本升级过程中，将生成以前版本的快照并将其存储在快照文件夹中。 在回退后，版本匹配的快照将被复制到新用户数据文件夹中，并从快照文件夹中删除。 如果降级后没有版本匹配的快照可用，回退会依赖同步将用户数据写入到新 Microsoft Edge 版本中。

[UserDataSnapshotRetentionLimit](./microsoft-edge-policies.md#userdatasnapshotretentionlimit) 组策略允许你针对任意给定时间内保留的快照数设置限制。 默认情况下，保留三个快照。 您可以将此策略配置为保留 0-5 个快照。

## <a name="frequently-asked-questions"></a>常见问题

### <a name="manual-msi-rollback"></a>手动 MSI 回退

#### <a name="what-generic-msi-failures-that-can-happen"></a>可能发生哪些常见 MSI 故障？

1. 如果禁用“安装更新”组策略，则不会发生回退。

   - 若要使用回退，请确保将“安装”设置为“**启用**”。 如果禁用此策略，将阻止安装 Microsoft Edge 频道。 有关详细信息，请参阅[安装](./microsoft-edge-update-policies.md#install)。

2. 如果启发更新不存在，将阻止 Microsoft Edge 安装，除非已启用*允许 Microsoft Edge 并排浏览体验*。

   - 针对 Windows 版本 1903 和 1909：如果上次更新早于 2019 年 10 月，则可能会存在此问题。
   - 针对 Windows 版本 1709、1803 和 1809：如果上次更新早于 2019 年 11 月，则可能会存在此问题。<br>
有关详细信息，请参阅[用于支持下一版 Microsoft Edge 的 Windows 更新](./microsoft-edge-sysupdate-windows-updates.md)。

#### <a name="the-following-error-message-was-shown-after-using-the-command-prompt-and-rollback-didnt-occur-whats-wrong"></a>使用命令提示但回退没发生后，显示以下错误消息。 究竟是哪里出现错误？

![回退状态消息](./media/edge-learnmore-rollback/edge-rollback-cmd-flag-error.png)

*ALLOWDOWNGRADE = 1* 未执行。

### <a name="microsoft-edge-update-and-group-policy-rollback"></a>Microsoft Edge 更新和组策略回退

#### <a name="i-set-rollback-to-target-version-enabled-update-policy-override-input-my-desired-browser-version-for-target-version-override-but-the-browser-version-wasnt-what-i-expected-whats-wrong"></a>我设置了*回退到目标版本*、启用了*更新策略替代*，且输入了*目标版本替代*希望回退到的浏览器版本，但浏览器版本不是我要回退到的版本。 究竟是哪里出现错误？

以下常见错误会阻止回退：

- 如果未设置回退到目标版本，将不会执行回退。
- 目标版本替代设置存在以下问题之一：

  - 目标版本替代被设置为不受支持的目标版本。
  - 目标版本替代被设置为不存在的目标版本。
  - 目标版本替代输入的格式不正确。

- 如果将”更新策略替代“设置为“禁用更新”，则 Microsoft Edge 更新不会接受任何更新，并且不会执行回退。

### <a name="i-set-all-the-group-policies-correctly-but-rollback-didnt-execute-what-happened"></a>我正确设置了所有组策略，但回退未执行。 发生了什么情况？

Microsoft Edge 更新尚未运行更新检查。 默认情况下，自动更新将每 10 小时检查一次更新。 可通过更改 Microsoft Edge 更新的轮询间隔来修复此问题，自动更新检查周期将覆盖组策略。 有关详细信息，请参阅 [AutoUpdateCheckPeriodMinutes](./microsoft-edge-update-policies.md#autoupdatecheckperiodminutes) 策略。

### <a name="as-an-it-admin-i-followed-all-the-steps-for-rollback-correctly-only-a-portion-of-my-user-group-was-rolled-back-why-havent-the-other-users-been-rolled-back-yet"></a>作为 IT 管理员，我按照正确回退的所有步骤进行了操作。 “我的用户组”的一部分已回退。 为什么尚未回退其他用户？

组策略设置尚未同步到所有客户端。 当管理员设置组策略时，客户端不会立即收到这些设置。 你可以[强制一个远程组策略刷新](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/jj134201(v=ws.11))。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge 企业版登录页面](https://aka.ms/EdgeEnterprise)
- [视频：Microsoft Edge 版本回滚](microsoft-edge-video-version-rollback.md)