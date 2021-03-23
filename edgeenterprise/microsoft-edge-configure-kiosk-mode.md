---
title: 配置 Microsoft Edge 展台模式
ms.author: aguta
author: aguta
manager: srugh
ms.date: 03/16/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解展台模式功能以及如何配置 Microsoft Edge 展台模式的选项。
ms.openlocfilehash: 516bc004a516b243e52d4128ae47f3ab9d7498df
ms.sourcegitcommit: 6a3787dead062e4a0860adbc570229974dcaee07
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442482"
---
# <a name="configure-microsoft-edge-kiosk-mode"></a>配置 Microsoft Edge 展台模式

本文介绍如何配置可以试用的 Microsoft Edge 展台模式选项。 还有一个在我们目标之中的功能路线图。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 87 或更高版本。

> [!IMPORTANT]
> 通过[使用展台模式功能](#use-kiosk-mode-features)中提供的命令行参数调用 Windows 10 Microsoft Edge 展台模式功能。

## <a name="overview"></a>概述

Microsoft Edge 展台模式提供两种浏览器锁定体验，因此组织可以创建、管理并为其客户提供最佳体验。 提供以下锁定体验：  

- **数字/交互式标志** 体验 - 以全屏模式显示特定网站。
- **公共浏览** 体验 - 运行 Microsoft Edge 的有限多选项卡版本。

这两种体验都在运行 Microsoft Edge InPrivate 会话，以保护用户数据。

## <a name="set-up-microsoft-edge-kiosk-mode"></a>设置 Microsoft Edge 展台模式

可以使用 Microsoft Edge Stable 渠道版本 87 测试一组初始展台模式功能。 你可以从 [Microsoft Edge (Official Stable 渠道)](https://www.microsoft.com/edge)下载。

### <a name="kiosk-mode-supported-features"></a>展台模式支持的功能

下表列出了 Microsoft Edge 和 Microsoft Edge 旧版中的展台模式支持的功能。 比较这两个版本的 Microsoft Edge 支持的功能有何不同，将此表用作指南以转换为 Microsoft Edge。

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
|结束会话按钮 * | N| Y| 89|Y|
|所有内部 Microsoft Edge URL 已将被阻止，除了*edge://downloads*和*edge://print* |N|Y|89|Y|
| Ctrl+N 阻止 (打开新窗口) * | Y | Y | 89 |Y|
| 已阻止 Ctrl+T（打开新选项卡） |Y | N | 89 |Y|
|设置和更多 (...) 将仅显示所需的选项  |Y |Y |89 |Y|
|限制从浏览器启动其他应用程序|Y|Y|90/91|Y|
|UI 打印设置锁定|Y|Y|90/91|Y|
|[将新标签页页面设置为主页](https://docs.microsoft.com/deployedge/microsoft-edge-policies#homepageisnewtabpage)（策略）|-|-|TBD|Y|

> [!NOTE]
> 后跟“*”的功能仅在已分配的访问单一应用场景中启用。

## <a name="use-kiosk-mode-features"></a>使用展台模式功能

对于数字/交互式标牌和公共浏览，可通过以下 Windows 10 命令行选项调用 Microsoft Edge 展台模式功能。

### <a name="kiosk-mode-digitalinteractive-signage"></a>展台模式数字/交互式标牌
 
```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen
```

### <a name="kiosk-mode-public-browsing"></a>展台模式公共浏览

```
msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing
```

### <a name="additional-command-line-options"></a>其他命令行选项

- **--no-first-run**：禁用首次 Microsoft Edge 运行体验。

   ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --no-first-run
  ```

  ```
  msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --no-first-run
  ```

- **--kiosk-idle-timeout-minutes=**：更改从上次用户活动到 Microsoft Edge 展台模式重置用户会话前的时间（以分钟为单位）。 将以下示例中的“值”替换为分钟数。

   ```
   --kiosk-idle-timeout-minutes=value
   ``` 
   支持以下“值”：

     - 默认值（分钟）
       - 全屏 - 0（关闭）
       - 公共浏览 - 5 分钟
    - 允许的值
      - 0 - 关闭计时器
      - 1-1440 分钟，用于在空闲计时器上重置


    ```
    msedge.exe --kiosk www.contoso.com --edge-kiosk-type=fullscreen --kiosk-idle-timeout-minutes=1
   ```

   ```
   msedge.exe --kiosk www.contoso.com --edge-kiosk-type=public-browsing --kiosk-idle-timeout-minutes=1
   ```

## <a name="support-policies-for-kiosk-mode"></a>展台模式的支持策略

使用下表中列出的任何 Microsoft Edge 策略增强所配置的 Microsoft Edge 展台模式类型的展台体验。 若要了解有关这些策略的信息，请参阅 [Microsoft Edge – 浏览器策略参考](https://docs.microsoft.com/deployedge/microsoft-edge-policies)。

> [!NOTE]
> 策略配置不限于下表中列出的策略，但应测试其他策略以确保展台模式功能不会受到负面影响。

|组策略|数字\交互式标志|公共浏览单应用|
|--|--|--|
|[打印](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printing-policies) | Y|Y |
|[HomePageLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#homepagelocation) |N | Y|
|[ShowHomeButton](https://docs.microsoft.com/deployedge/microsoft-edge-policies#showhomebutton) |N | Y|
|[NewTabPageLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagelocation) |N |Y |
|[FavoritesBarEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#favoritesbarenabled) |N |Y |
|[URLAllowlist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlallowlist) |Y |Y |
|[URLBlocklist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#urlblocklist) |Y | Y|
|[ManagedSearchEngines](https://docs.microsoft.com/deployedge/microsoft-edge-policies#managedsearchengines) |N | Y|
|[UserFeedbackAllowed](https://docs.microsoft.com/deployedge/microsoft-edge-policies#userfeedbackallowed) |N | Y|
|[VerticalTabsAllowed](https://docs.microsoft.com/deployedge/microsoft-edge-policies#verticaltabsallowed) | N|Y |
|[SmartScreen 设置](https://docs.microsoft.com/deployedge/microsoft-edge-policies#smartscreen-settings-policies) |Y |Y |
|[EdgeCollectionsEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#edgecollectionsenabled)|Y|Y|

## <a name="microsoft-edge-with-assigned-access"></a>Microsoft Edge 与指派访问

### <a name="single-app-kiosk"></a>单应用展台

Microsoft Edge 当前支持具有以下锁定体验的单应用分配访问权限的相同 Microsoft Edge 旧版展台模式类型的子集：数字/交互式标志和公共浏览。  

目前，在最新的  [Windows 10 Insider Preview 内部版本](https://insider.windows.com/)的版本 20215 或更高版本以及  [Microsoft Edge Beta 渠道](https://www.microsoftedgeinsider.com/download)的版本 89 或更高版本上，可以测试具有已分配访问权限的单应用的 Microsoft Edge 展台模式。

**如何获得 Windows 预览体验成员预览版？**

若要在电脑上安装 Windows 10 Insider Preview 内部版本，请按照 [开始使用 Windows 10 Insider Preview 版本](https://docs.microsoft.com/windows-insider/get-started)中的说明进行操作。

### <a name="multi-app-kiosk"></a>多应用展台。

可用 Windows 10 上的[多应用指派访问](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)（相当于旧版 Microsoft Edge 的“普通浏览”展台模式类型）运行 Microsoft Edge。 若要使用多应用分配的访问权限配置 Microsoft Edge，请按照有关[如何设置多应用展台](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps)的说明进行操作。 （Microsoft Edge Stable 渠道的 AUMID 为 **MSEdge**）。

将 Microsoft Edge 与多应用分配的访问权限一同使用时，可以将 Microsoft Edge 展台配置为使用 [Microsoft Edge 浏览器策略](https://review.docs.microsoft.com/DeployEdge/microsoft-edge-policies)配置浏览体验，以满足你的独特要求。

### <a name="configure-using-windows-settings"></a>使用 Windows 设置进行配置

Windows 设置是设置一个或两个单应用展台设备的最简单方法。 使用以下步骤设置单应用展台计算机。

1. 安装最新的 Windows 10 Insider Preview 版本 20215 或更高版本。 按照[开始使用 Windows 10 Insider Preview 版本](https://docs.microsoft.com/windows-insider/get-started)中的说明进行操作。
2. 若要测试最新功能，可以下载最新的 [Microsoft Edge Beta 渠道](https://www.microsoftedgeinsider.com/download)的 89 或更高版本。
3. 在展台计算机上，打开“Windows 设置”，然后在搜索字段中键入“展台”。 选择“ **设置展台（分配的访问权限）**”（如下一个屏幕截图所示），以打开用于创建展台的对话框。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-1-assigned-access.png" alt-text="设置具有分配的访问权限的展台":::

4. 在“**设置展台** ”页面上，单击“ **入门**”。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-2-get-started.png" alt-text="展台页面 - 入门":::

5. 键入名称以创建新的展台帐户，或从填充的下拉列表中选择现有帐户，然后单击“ **下一步**”。

   :::image type="content" source="media/microsoft-edge-configure-kiosk-mode/ms-kiosk-mode-3-create-account.png" alt-text="展台模式 - 创建帐户":::

6. 在“**选择展台应用** ”页面上，选择“**Microsoft Edge**”，然后单击“ **下一步**”。

   > [!NOTE]
   > 这仅适用于 Microsoft Edge Dev、Beta 和 Stable 渠道。

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

## <a name="functional-limitations"></a>功能限制

随着展台模式此预览版的发布，我们将继续改进产品和添加新功能。

目前不支持以下功能，建议关闭：

- [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)
- [IsolateOrigins](https://docs.microsoft.com/deployedge/microsoft-edge-policies#isolateorigins)
- [ManagedFavorites](https://docs.microsoft.com/deployedge/microsoft-edge-policies#managedfavorites)
- [EdgeShoppingAssistantEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#edgeshoppingassistantenabled)
- [EdgeCollectionsEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#edgecollectionsenabled)
- [UserFeedbackAllowed](https://docs.microsoft.com/deployedge/microsoft-edge-policies#userfeedbackallowed)
- [DefaultPopupsSetting](https://docs.microsoft.com/deployedge/microsoft-edge-policies#defaultpopupssetting)
- [StartupBoostEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startupboostenabled)
- [InternetExplorerIntegrationLevel](https://docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationlevel)
- [Extensions](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensions-policies)
- [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)
- [UserFeedbackAllowed](https://docs.microsoft.com/deployedge/microsoft-edge-policies#userfeedbackallowed)

## <a name="roadmap"></a>路线图

### <a name="in-early-2021"></a>2021 年初

我们将添加以下支持和功能：

- Microsoft Edge 展台模式在 Windows 10 1909 及更高版本上具有分配的访问权限单应用通用。
- 用于与 Microsoft Edge 旧版进行奇偶校验的其他功能。
- 与 Intune 集成，以使用展台模式配置文件 UX 配置设备。
- 限制从浏览器启动其他应用程序。
- UI 打印设置锁定。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [规划 Microsoft Edge 部署](deploy-edge-plan-deployment.md)
- [在 Windows 桌面版中配置展台和数字签名](https://docs.microsoft.com/windows/configuration/kiosk-methods)
- [规划展台模式转换](microsoft-edge-kiosk-mode-transition-plan.md)
