---
title: 访问旧版 Microsoft Edge
ms.author: jtkim
author: dan-wesley
manager: srugh
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解如何访问旧版 Microsoft Edge。
ms.openlocfilehash: b521ab9ea093b62db7268e6bf2f4d656b3dc8d4b
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447086"
---
# <a name="access-microsoft-edge-legacy-after-installing-the-new-version-of-microsoft-edge"></a>在安装 Microsoft Edge 的新版本后访问旧版 Microsoft Edge

Microsoft Edge 旧版将自 2021 年 3 月 9 日起停止接收安全更新。 在 4 月 13 日之前，你仍可访问 Microsoft Edge 旧版。 有关详细信息，请参阅 Microsoft Edge 产品团队的[博客文章](https://aka.ms/EdgeLegacyEOS)。

> [!NOTE]
> 本文适用于 Microsoft Edge [稳定渠道](microsoft-edge-channels.md)。

大多数组织希望将 Microsoft Edge 旧版本替换为新版本，但在某些情况下，用户需要访问这两个版本。 例如：

- 有些支持人员在与用户进行互动时，用户使用的是 Microsoft Edge 的其中一个版本或两个版本。
- 为使用其中一个或两个版本的 Microsoft Edge 的客户提供支持的开发人员。

> [!IMPORTANT]
> 不建议在生产中将 Microsoft Edge 旧版与新版 Microsoft Edge 并排运行。 此配置只应在需要使用两个浏览器版本进行测试的特定情况下使用。
>
> 将于 2021 年 3 月 9 日终止对 Microsoft Edge 旧版桌面应用的支持，取而代之的是新版 Microsoft Edge。 这意味着在该日期之后 Microsoft Edge 旧版将不再接收安全更新。 此更改适用于在 Microsoft Edge 旧版桌面应用中运行的所有体验。 [了解详细信息](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-365-apps-say-farewell-to-internet-explorer-11-and/ba-p/1591666)。

## <a name="before-you-begin"></a>开始之前
> [!NOTE]
> 从 Windows 10 版本 20H2 开始，不再包含 Microsoft Edge 旧版。 从 Windows 10 该版本开始，不支持并行使用体验。

本文中的过程适用于已用最新安全更新进行更新的系统。 安装 Microsoft Edge 的新版本后，将隐藏旧版本（旧版 Microsoft Edge）。 默认情况下，所有尝试启动旧版本的操作都将用户重定向到新安装的 Microsoft Edge 版本。 本文介绍如何在安装 Microsoft Edge 后继续使用 Microsoft Edge 旧版本。

## <a name="quickstart-side-by-side-experience-with-microsoft-edge-beta-channel-and-microsoft-edge-legacy"></a>快速入门：Microsoft Edge Beta 渠道和 Microsoft Edge 旧版本的并行使用体验

在使用本文中的详细说明之前，请考虑执行以下 2 个步骤，让你的用户可并行运行 Microsoft Edge 旧版和 Microsoft Edge [Beta 渠道](microsoft-edge-channels.md)。

1. 通过 [Windows 更新](https://support.microsoft.com/help/12373/windows-update-faq)阻止自动安装 Microsoft Edge 稳定渠道。
2. 安装 Microsoft Edge 新版本的 [Beta 渠道](https://www.microsoft.com/edge/business/download)。

   > [!NOTE]
   > 有关注册表项设置的信息，请阅读[其他信息](#additional-information)。

这种并行解决方案不太复杂，并且需要的管理比本文中所述的详细解决方案更少。 但是，此解决方案意味着你将运行 Beta 渠道，而非 Stable 渠道。

## <a name="side-by-side-experience-with-microsoft-edge-stable-channel-and-microsoft-edge-legacy"></a>Microsoft Edge Stable 渠道和 Microsoft Edge 旧版的并行使用体验

在系统级别安装 Microsoft Edge 下一版本的 Stable 渠道将导致隐藏当前版本（Microsoft Edge 旧版本）。 如果要让用户可在 Windows 中同时看到 Microsoft Edge 的两个版本，可通过将**允许 Microsoft Edge 并行浏览器体验**组策略设置为**已启用**来启用此体验。

[此处](./microsoft-edge-update-policies.md#allowsxs)记载了这个组策略

### <a name="to-set-up-the-side-by-side-browser-experience-policy"></a>若要设置并行浏览器体验策略，请执行以下操作：

1. 从 [Microsoft Edge For Business](https://www.microsoft.com/edge/business/download) 安装策略定义。

   - 选择要使用的渠道/内部版本和平台，然后单击“获取策略文件”。
   - 将压缩文件解压缩。
   - 将 msedge.admx 和 msedgeupdate.admx 复制到 `C:\Windows\PolicyDefinitions` 目录。
   - 将 msedge.adml 和 msedgeupdate.adml（从相应的语言/区域设置目录）复制到 `C:\Windows\PolicyDefinitions\[APPROPRIATE LANGUAGE/LOCALE]` 目录。

2. 打开组策略编辑器 (gpedit.msc)。
3. 在**计算机配置**下方，转到*管理模板 > Microsoft Edge 更新 > 应用程序*。

    > [!NOTE]
    > 如果看不到 *Microsoft Edge 更新*文件夹，请验证步骤 1 是否已正确完成。

4. 在**应用程序**下方，双击“允许 Microsoft Edge 并行浏览器体验”。 请参阅我们的[最佳实践指南](#best-practice-guidance)，然后再继续执行下一步。

    > [!NOTE]
    > 默认情况下，将这个组策略设置为“未配置”，这导致在安装 Microsoft Edge 的新版本后隐藏旧版 Microsoft Edge。

5. 选中**已启用**，然后单击**确定**。  

设置此策略会将以下注册表项设置为“00000001”：

- 注册表项： `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate`
- 值名称： `Allowsxs`
- 值类型： `'REG_DWORD'`

#### <a name="best-practice-guidance"></a>最佳实践指导

为了获得最佳体验，应先启用**允许 Microsoft Edge 并行浏览器体验**，然后再将 Microsoft Edge 的新版本部署到用户的设备。

如果在部署 Microsoft Edge 后才启用该组策略，则有以下这些副作用和所需采取的措施：

1. 直到再次运行 Microsoft Edge 新版本的安装程序后，**允许 Microsoft Edge 并行浏览器体验**才会生效。

   > [!NOTE]
   > 可直接运行该安装程序，也可在 Microsoft Edge 的新版本进行更新时自动运行该安装程序。

2. 需要将旧版 Microsoft Edge 重新固定到“开始”屏幕或任务栏，因为在部署 Microsoft Edge 的新版本时将迁移固定方式。
3. 对于旧版 Microsoft Edge 固定到“开始”屏幕或任务栏的网站将迁移到 Microsoft Edge 的新版本。

## <a name="additional-information"></a>其他信息

在完全更新系统并安装 Microsoft Edge 下一版本的 Stable 渠道后，将设置以下注册表项和值：

- 注册表项： `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\ClientState\{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}`
- 项值： `BrowserReplacement`

  > [!IMPORTANT]
  > 每次更新 Microsoft Edge Stable 渠道时，都会覆盖此项。 作为最佳实践，我们建议不要删除此项，以使用户可同时访问 Microsoft Edge 的两个版本。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [用于支持 Microsoft Edge 的 Windows 更新](microsoft-edge-sysupdate-windows-updates.md)