---
title: Microsoft Edge 功能的平台支持
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 功能的平台支持摘要
ms.openlocfilehash: c34249e126a1fb27c84a2f025c826654bb9df358
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "11978990"
---
# <a name="platform-support-for-microsoft-edge-features"></a>Microsoft Edge 功能的平台支持

本文总结了对 Microsoft Edge 功能的平台支持。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="feature-matrix-for-platforms"></a>平台的功能矩阵

下表总结了对 Windows 和 macOS 平台的功能支持。

> [!NOTE]
> Android 和 iOS 当前未在支持表中显示，但我们继续开发此信息，并将进行相应更新。

| 安全功能 |Win 10|Win 8.1|Win 7|macOS|URL|
|--------|-------|--------|-----|-------|---|
|Azure Active Directory （Azure AD） 条件访问|是|是|是|是|[Azure AD 条件访问](/deployedge/ms-edge-security-conditional-access#accessing-conditional-access-protected-resources-in-microsoft-edge)|
|Microsoft Defender 应用程序防护|支持 （1890+）|否|否|否|[Microsoft Defender 应用程序防护](/deployedge/microsoft-edge-security-windows-defender-application-guard) |
|Microsoft Defender SmartScreen|是|是|是|是|[Microsoft Defender SmartScreen](/deployedge/microsoft-edge-security-smartscreen) |
|Microsoft Endpoint DLP|是|否|否|否|[Microsoft Endpoint DLP](/deployedge/microsoft-edge-security-dlp#microsoft-endpoint-data-loss-prevention-endpoint-dlp)|
|密码监视器|是|是|是|是|[密码监视器](https://blogs.windows.com/msedgedev/2021/01/21/edge-88-privacy/)|
|密码生成器|是|是|是|是|[密码生成器](https://blogs.windows.com/msedgedev/2021/01/21/edge-88-privacy/)|
|Windows 信息保护 (WIP)|支持 （1607+）|否|否|否|[WIP](/deployedge/microsoft-edge-security-windows-information-protection#system-requirements)|

|身份功能| Win 10 | Win 8.1 | Win 7 | macOS | URL |
|--|--|--|--|--|--|
|自动登录（混合/AAD-J）|是|是|是|否|[混合/AAD-J](/deployedge/microsoft-edge-security-identity#automatic-sign-in)|
|自动登录（加入域）|是|是|是|否|[已加入域](/deployedge/microsoft-edge-security-identity#automatic-sign-in)|
|自动登录（OS 默认帐户为 MSA）|支持 （1709+）|否|否|否|[MSA](/deployedge/microsoft-edge-security-identity#automatic-sign-in)|
|浏览器至 Web 单一登录（SSO）|是|是|是|是|[浏览器-Web SSO](https://www.microsoft.com/microsoft-365/roadmap?featureid=66332)|
|引导式切换/"自动配置文件切换"|是|是|是|是|[在工作和家中使用多个配置文件](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/) |
|多个配置文件|是|是|是|是|[在工作和家中使用多个配置文件](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/) |
|Active Directory （AD） 本地同步|是|是|是|否|[Active Directory (AD) 用户的本地同步](/deployedge/microsoft-edge-on-premises-sync) |
|无缝 SSO|支持 （1709+）|是|是|是|[无缝 SSO](/deployedge/microsoft-edge-security-identity#seamless-sso)|
|采用主刷新令牌 (PRT) 的 SSO|支持 （1709+）|是|是|否|[SSO 与 PRT](/deployedge/microsoft-edge-security-identity#sso-with-primary-refresh-token-prt)|
|Windows 集成身份验证 (WIA)|是|是|是|是*（需要策略）|[WIA](/deployedge/microsoft-edge-security-identity#windows-integrated-authentication-wia)|

|其他功能|Win 10|Win 8.1|Win 7|macOS|URL|
|--------|-------|--------|-----|-------|---|
|集锦|是|是|是|是|[集锦](https://blogs.windows.com/msedgedev/2019/12/09/improvements-collections-sync-microsoft-edge/) |
|企业版新选项卡页面|是|是|是|是|[“新建选项卡”页面](https://blogs.windows.com/msedgedev/2020/10/29/enterprise-new-tab-page-my-feed/) |
|IE 模式|是|是|是|否|[IE 模式](/deployedge/edge-ie-mode#prerequisites)|
|展台模式|是|否|否|否|[展台模式](/deployedge/microsoft-edge-configure-kiosk-mode)|
|Microsoft 必应搜索|是|是|是|是|[必应中的智能搜索](https://www.microsoft.com/edge/business/intelligent-search-with-bing) |
|PDF 阅读器|是|是|是|是|[PDF 阅读器](/deployedge/microsoft-edge-pdf) |
|购物|是|是|是|是|[购物](https://techcommunity.microsoft.com/t5/articles/introducing-shopping-with-microsoft-edge/m-p/1870080) |
|<3> <2>子标签|是|是|是|是|[功能概念](/deployedge/microsoft-edge-relnote-stable-channel)<br>[最新博客文章](https://blogs.windows.com/msedgedev/2021/03/04/edge-89-performance/)<br>[组策略](/deployedge/microsoft-edge-policies#sleeping-tabs-settings)|
|同步|是|是|是|是| [企业同步](/deployedge/microsoft-edge-enterprise-sync) |
|版本回退|是|是|是|否|[版本回退](/deployedge/edge-learnmore-rollback) |
|垂直选项卡|是|是|是|是| |

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)