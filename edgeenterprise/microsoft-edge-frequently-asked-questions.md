---
title: 有关企业 (的) 常见问题Microsoft Edge常见问题解答
ms.author: collw
author: dan-wesley
manager: seanlynd
ms.date: 01/11/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 有关企业 (的) 常见问题Microsoft Edge常见问题解答
ms.openlocfilehash: 86f1fdee4697d8087014e35daf41b600eeb62471
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2022
ms.locfileid: "12298312"
---
# <a name="microsoft-edge-frequently-asked-questions"></a>Microsoft Edge常见问题

本文包含有关企业中 () 常见问题Microsoft Edge常见问题解答。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="how-do-i-know-which-version-of-microsoft-edge-i-have"></a>我怎么知道我拥有哪个版本的 Microsoft Edge？

选择 (**右上角**) ..."的省略号Microsoft Edge，然后选择 **"设置"。** 选择**关于 Microsoft Edge** 以查看你的 Microsoft Edge 版本。

## <a name="what-about-internet-explorer-11"></a>第 11 Internet Explorer呢？

11 Internet Explorer 11 桌面应用程序将于 2022 年 6 月 15 日停用并停用支持。 To see what's in scope， see [The future of Internet Explorer on Windows 10 is in Microsoft Edge](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/). 现在使用的 IE11 应用和网站可以在 Microsoft Edge 的 Internet Explorer 模式下打开。 有关详细信息，请参阅Internet Explorer [11 桌面应用停用常见问题解答](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)。

## <a name="does-microsoft-edge-support-activex-controls-or-browser-helper-objects-like-silverlight-or-java"></a>是否Microsoft Edge支持ActiveX或浏览器帮助程序对象，如 Silverlight 或 Java？

否。 Microsoft Edge Silverlight 或 ActiveX 等 (BH 对象) 浏览器帮助Java。 但是，如果你在 Internet Explorer 11 上运行使用 ActiveX 控件、BHOs 或旧文档模式的 Web 应用，你可以将它们配置为在 Microsoft Edge 上的 IE 模式下运行。 有关详细信息，请参阅“[在 Microsoft Edge 上配置 IE 模式](./edge-ie-mode.md)。

## <a name="will-favorites-be-ported-over-from-the-current-version-of-microsoft-edge-or-will-i-have-to-re-add-them"></a>收藏夹是从当前版本的 Microsoft Edge还是必须重新添加？

Microsoft Edge Win10 Microsoft Edge 上现有安装的 Microsoft Edge、Chrome、Internet Explorer 和 Firefox (导入) 。 支持导入以下设置：书签、历史记录、密码和自动填充 (付款、地址和常规) 。 你可以选择从首次运行体验或从浏览器设置进行导入。

## <a name="whats-the-difference-between-the-stable-beta-dev-and-canary-channelsbuilds"></a>Stable、Beta、Dev 和 Canary 渠道/版本之间有什么区别？

Stable 渠道Microsoft Edge我们提供的最稳定渠道，提供以企业为中心的功能，可供你在整个[组织中进行试用](https://aka.ms/EdgeEnterprise)和评估。 通过 Beta 渠道，可通过一组有代表性的用户验证下一个 Stable 版本。 Stable 和 Beta 渠道大约每六周更新一次。 Dev 和 Canary 频道继续分别每周和每天更新一次。 脱机安装程序 (MSIs 和 PKG) 仅适用于 Stable、Beta 和 Dev 渠道。 有关详细信息，请参阅 [Microsoft Edge 渠道概述](./microsoft-edge-channels.md)。

## <a name="what-kind-of-extension-support-do-i-have-with-microsoft-edge"></a>我拥有哪种类型的扩展Microsoft Edge？

Microsoft Edge支持预览体验成员[Microsoft Edge加载项](https://go.microsoft.com/fwlink/?linkid=2081222)中的扩展[Chrome Web Store。](https://go.microsoft.com/fwlink/?linkid=2072338)

## <a name="do-you-support-mobile-device-management-mdm-and-microsoft-intune"></a>你是否支持移动设备管理 (MDM) 和 Microsoft Intune？

是。 现已支持使用 Microsoft Intune 和移动设备管理 (MDM) 在 Windows 10 上配置 Microsoft Edge。 有关详细信息，请参阅[使用 Microsoft Intune 配置 Microsoft Edge](./configure-edge-with-intune.md) 以及[使用移动设备管理配置 Microsoft Edge](./configure-edge-with-mdm.md)。

## <a name="does-windows-server-update-services-wsus-support-the-initial-deployment-of-microsoft-edge"></a>WSUS Windows Server Update Services (是否) 初始部署Microsoft Edge？

是。 Microsoft 更新目录中有[](https://www.catalog.update.microsoft.com/Search.aspx?q=the%20new%20microsoft%20edge%20for%20windows)一些程序包可用于通过 WSUS Microsoft Edge部署。 初始部署后，默认配置自动更新。 有关更多信息，请参阅[ WSUS 中的用于Windows 10的新Microsoft Edge的更新，版本为1809、1903、1909和2004：2020年10月29日](https://support.microsoft.com/help/4584642/update-in-wsus-for-the-new-microsoft-edge)。

 可通过配置管理工具（如 [ConfigMgr）执行手动更新](/configmgr/apps/deploy-use/deploy-edge?bc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2fbreadcrumb%2ftoc.json&toc=https%3a%2f%2fdocs.microsoft.com%2fDeployEdge%2ftoc.json)。

## <a name="are-initial-preferences-supported"></a>是否支持初始首选项？

是。 有关详细信息，请参阅 Configure [Microsoft Edge using Initial Preferences settings for the first run](./initial-preferences-support-on-microsoft-edge-browser.md)

## <a name="see-also"></a>另请参阅

- [Microsoft Edge 文档登录页面](./index.yml)
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
  