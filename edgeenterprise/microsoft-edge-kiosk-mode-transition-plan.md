---
title: 规划展台模式转换
ms.author: aguta
author: aguta
manager: srugh
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 规划展台模式转换
ms.openlocfilehash: 3a438c6dd71d9e1f0e644d24e3b1d1d60b099e8e
ms.sourcegitcommit: b1d49b229c47dc1d99e1b677d75aad38b3334ed6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "11314232"
---
# 规划展台模式转换

本文提供有关如何将展台从 Microsoft Edge 旧版转换到 Microsoft Edge 的指南。  

> [!NOTE]
> 本文适用于 Microsoft Edge 稳定、Beta 和 Dev 渠道版本 87 或更高版本。

> [!IMPORTANT]
> 当 2021 年 3 月 9 日对 Microsoft Edge 旧版的支持结束时，作为 4 月 Windows 更新的一部分，它将会被删除并替换为 Chromium 上的 Microsoft Edge。 有关详细信息，请转至[此博客文章](https://aka.ms/EdgeLegacyEOS)。 若要继续使用基于浏览器的展台方案，你需要先安装 Chromium 上的 Microsoft Edge 并设置展台模式，然后再在设备上安装 4 月 Windows 更新版本。

## 展台设置步骤

使用以下步骤作为指南，在 Microsoft Edge 中设置展台。

**第 1 步：根据已发布的（和即将发布的）展台模式功能，评估你的需求。** 下表列出了 Chromium 上的 Microsoft Edge 和 Microsoft Edge 旧版中的展台模式支持的功能。 比较这两个版本的 Microsoft Edge 支持的功能有何不同，将此表用作指南以转换为 Microsoft Edge。

|功能|数字\交互式标志|公共浏览|适用于 Microsoft Edge 版本（及更高版本）|适用于 Microsoft Edge 旧版|
|-|-|-|-|-|
|InPrivate 导航|Y|Y|89|Y|
|在处于非活动状态时重置|Y|Y|89|Y|
|[只读地址栏](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) (策略) |N|Y |89|N|
|[退出时删除下载](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit)（策略）  | Y|Y |89|N|
|已阻止 F11（进入/退出全屏） | Y | Y | 89 |Y|
|已阻止F12（启动开发人员工具） | Y | Y | 89 |Y|
| 多选项卡支持 | N| Y| 89|Y|
|[允许 URL 支持](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlallowlist)（策略）|Y|Y|89|N|
|[阻止 URL 支持](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlblocklist)（策略）|Y|Y|89|N|
|[显示“主页”按钮](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#showhomebutton)（策略）|N|Y|89|Y|
|[管理收藏夹](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#managedfavorites)（策略）|N|Y|89|Y|
|[启用打印机](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)（策略）|Y|Y|89|Y|
|[配置新标签页页面 URL](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagelocation)（策略）|N|Y||Y|
|“结束会话”按钮 | N| Y| 89|Y|
|所有内部 Microsoft Edge URL 已将被阻止，除了*edge://downloads*和*edge://print* |N|Y|89|Y|
| 已阻止 Ctrl+N（打开一个新窗口） | Y | Y | 89 |Y|
| 已阻止 Ctrl+T（打开新选项卡） |Y | Y | 89 |Y|
|设置和更多 (...) 将仅显示所需的选项  |Y |Y |89 |Y|
|限制从浏览器启动其他应用程序|Y|Y|90/91|Y|
|UI 打印设置锁定|Y|Y|90/91|Y|
|[将新标签页页面设置为主页](https://docs.microsoft.com/deployedge/microsoft-edge-policies#homepageisnewtabpage)（策略）|-|-|TBD|Y|

> [!NOTE]
> 有关 Microsoft Edge 发布计划的信息，请参阅 [Microsoft Edge 发布计划](microsoft-edge-release-schedule.md)。

**第 2 步：在 Microsoft Edge 中测试新展台。** 我们建议你在 Microsoft Edge 中测试展台模式的设置。 测试展台模式的一种快速、简单方式是按照下面所述使用 Windows 设置配置已分配访问权限的单应用。

1. 安装最新的 Windows 10 Insider Preview 版本 20215 或更高版本。 按照[开始使用 Windows 10 Insider Preview 版本](https://docs.microsoft.com/windows-insider/get-started)中的说明进行操作。
2. 安装最新版本的 [Microsoft Edge 稳定渠道版本](https://www.microsoft.com/edge)的 87 或更高版本。  若要测试最新功能，可以下载最新的 [Microsoft Edge Beta 渠道](https://www.microsoftedgeinsider.com/download)的 89 或更高版本。

   > [!IMPORTANT]
   > 由于需要设备级别安装，因此 Canary 起到不受支持。

3. 在展台计算机上，打开“Windows 设置”，然后在搜索字段中键入“展台”。 选择“ **设置展台（分配的访问权限）**”（如下一个屏幕截图所示），以打开用于创建展台的对话框。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="设置具有分配的访问权限的展台":::

4. 在“**设置展台** ”页面上，单击“ **入门**”。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="展台页面 - 入门":::

5. 键入名称以创建新的展台帐户，或从填充的下拉列表中选择现有帐户，然后单击“ **下一步**”。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="展台模式 - 创建帐户":::

6. 在“**选择展台应用** ”页面上，选择“**Microsoft Edge**”，然后单击“ **下一步**”。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-4-pick-app.png" alt-text="展台模式 - 选择应用":::

7. 选择以下选项之一，了解 Microsoft Edge 在展台模式下运行时的显示方式：

   - 数字/交互式标牌 - 运行 Microsoft Edge 时以全屏模式显示特定网站。
   - 公共浏览器 - 运行 Microsoft Edge 的受限多选项卡版本。

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-5a-digital-sign.png" alt-text="展台模式显示 - 全屏数字签名":::

8. 选择“ **下一步**”。
9. 键入要在展台启动时加载的 URL。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-6-enter-url.png" alt-text="展台模式 - 输入 URL":::

10. 接受“5 分钟”的空闲时间默认值或提供你自己的值。

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-7-enter-idle-time.png" alt-text="展台模式 - 输入空闲时间":::

11. 单击“ **下一步**”。
12. 关闭“ **设置** ”窗口，保存并应用你的选择。

    :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode--8-done.png" alt-text="展台模式 - 完成设置":::

13. 从展台设备注销，然后使用本地展台帐户登录以验证配置。

**第 3 步：制定转换计划。** 根据你的测试和组织需求，我们建议制定转换计划，在 2021 年 3 月 9 日结束对 Microsoft Edge 旧版的支持之前移动到 Chromium 上的 Microsoft Edge。

## 其他需要重新创建现有展台模式的方案

如果更新到 Windows 10 版本 20H2，将安装 Chromium 上的 Microsoft Edge，并隐藏 Microsoft Edge 旧版。 在此情况下，你需要在 Chromium 上的 Microsoft Edge 中再次设置展台模式。

## 如何获取帮助

展台模式可能是日常业务的重要部分，因此我们希望帮助你尽可能顺利地实现转换，并帮助你避免中断。 如果你的企业在转换到 Chromium 上的 Microsoft Edge 时需要帮助：

- Microsoft 可以提供[支持](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=a77ee9b7-b6b6-aa08-d7b9-887ebe228207)。 
- 对于拥有 150 或更多个 Windows 10 企业版付费座席的客户，可免费提供 [FastTrack 支持](https://www.microsoft.com/fasttrack/microsoft-365/microsoft-edge?rtc=1)。
- 如果遇到站点或应用兼容性问题，则可使用[应用 Assure](https://www.microsoft.com/en-us/fasttrack/microsoft-365/app-assure)。

## 另请参阅

- [Microsoft Edge 企业版登录页面](https://aka.ms/EdgeEnterprise)
- [通过 4 月的 Windows 10 星期二更新版本，使用新的 Microsoft Edge 替换 Microsoft Edge 旧版](https://techcommunity.microsoft.com/t5/microsoft-365-blog/new-microsoft-edge-to-replace-microsoft-edge-legacy-with-april-s/ba-p/2114224)