---
title: Microsoft Edge Beta 渠道发行说明
ms.author: leahtu
author: dan-wesley
manager: srugh
ms.date: 04/27/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge Beta 渠道发行说明
ms.openlocfilehash: 41f9efd48fa9afef215c2fd8e6499b2840ec256c
ms.sourcegitcommit: 592f6e40b13e28af588473b2a75c3ae697e5db2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2022
ms.locfileid: "12505365"
---
# <a name="release-notes-for-microsoft-edge-beta-channel"></a>Microsoft Edge Beta 渠道的发行说明

本发行说明提供有关 Microsoft Edge Beta 渠道中包含的新功能和非安全更新的信息。 Microsoft Edge Beta[频道的存档发行说明](./microsoft-edge-relnote-archive-beta-channel.md)中提供了这些发行说明的存档版本。

> [!NOTE]
> Microsoft Edge Web 平台不断发展以改进用户体验、安全性和隐私。 要了解详细信息，请参阅 [Microsoft Edge 中即将推出的影响站点兼容性的更改](/microsoft-edge/web-platform/site-impacting-changes)。

## <a name="version-1010121031-april-27"></a>版本 101.0.1210.31：4 月 27 日

修复了各种 bug 和性能问题。

## <a name="version-1010121026-april-22"></a>版本 101.0.1210.26：4 月 22 日

修复了各种 bug 和性能问题。

## <a name="version-1010121019-april-18"></a>版本 101.0.1210.19：4 月 18 日

修复了各种 bug 和性能问题。

## <a name="version-1010121014-april-12"></a>版本 101.0.1210.14：4 月 12 日

修复了各种 bug 和性能问题。

### <a name="feature-updates"></a>功能更新

- **对Enterprise站点列表管理器的改进。** 现在，可以在企业站点列表的Microsoft Edge和 Internet Explorer 之间配置共享 Cookie。 可以在 [edge://compat/SiteListManager 访问Enterprise站点列表管理](/deployedge/edge-ie-mode-site-list-manager)*器*。

## <a name="version-1010121010-april-8"></a>版本 101.0.1210.10：4 月 8 日

### <a name="feature-updates"></a>功能更新

- **能够设置默认配置文件。** [EdgeDefaultProfileEnabled](/DeployEdge/microsoft-edge-policies#edgedefaultprofileenabled) 策略允许你设置在打开浏览器时使用的默认配置文件，而不是使用的最后一个配置文件。 如果已指定参数， `--profile-directory` 则此策略将不适用。

- **客户端证书切换器。** 此功能可让用户在访问需要 http 证书身份验证的站点时清除已记住的证书并重新显示证书选取器。 无需手动退出Microsoft Edge即可完成此操作。

- **从收藏夹栏) 启动渐进式Web 应用 (PVA。** PWA启动体验的改进将从可添加到工具栏的“应用”图标开始显示。

- **管理“允许从其他存储扩展”设置。** 使用 [ControlDefaultStateOfAllowExtensionFromOtherStoresSettingEnabled 策略](/DeployEdge/microsoft-edge-policies#controldefaultstateofallowextensionfromotherstoressettingenabled) 控制“允许从其他存储扩展”设置的默认状态。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

- [配置KeyboardShortcuts](/DeployEdge/microsoft-edge-policies#configurekeyboardshortcuts) - 配置要禁用键盘快捷方式的命令列表
- [ControlDefaultStateOfAllowExtensionFromOtherStoresSettingEnabled](/DeployEdge/microsoft-edge-policies#controldefaultstateofallowextensionfromotherstoressettingenabled) - 从其他存储设置配置允许扩展的默认状态
- [EdgeAssetDeliveryServiceEnabled](/DeployEdge/microsoft-edge-policies#edgeassetdeliveryserviceenabled) - 允许功能从资产传送服务下载资产
- [EdgeDefaultProfileEnabled](/DeployEdge/microsoft-edge-policies#edgedefaultprofileenabled) - 启用默认配置文件设置
- [InternetExplorerModeEnableSavePageAs](/DeployEdge/microsoft-edge-policies#internetexplorermodeenablesavepageas) - 允许在 Internet Explorer 模式下保存页面
- [KioskSwipeGesturesEnabled](/DeployEdge/microsoft-edge-policies#kioskswipegesturesenabled) - 在启用Microsoft Edge展台模式下轻扫手势
- [MicrosoftOfficeMenuEnabled](/DeployEdge/microsoft-edge-policies#microsoftofficemenuenabled) - 允许用户访问Microsoft Office菜单
- [SiteSafetyServicesEnabled](/DeployEdge/microsoft-edge-policies#sitesafetyservicesenabled) - 允许用户配置站点安全服务

#### <a name="deprecated-policy"></a>已弃用策略

- [ForceCertificatePromptsOnMultipleMatches](/DeployEdge/microsoft-edge-policies#forcecertificatepromptsonmultiplematches) - 配置当配置有“AutoSelectCertificateForUrls”的站点存在多个证书匹配项时，Microsoft Edge是否应自动选择证书

#### <a name="obsoleted-policy"></a>已过时的策略

- [WebSQLInThirdPartyContextEnabled](/DeployEdge/microsoft-edge-policies#websqlinthirdpartycontextenabled) - 强制重新启用第三方上下文中的 WebSQL


## <a name="version-1000118527-march-31"></a>版本 100.0.1185.27：3 月 31 日

修复了各种 bug 和性能问题。

## <a name="version-1000118523-march-28"></a>版本 100.0.1185.23：3 月 28 日

修复了各种 bug 和性能问题。

## <a name="version-1000118517-march-23"></a>版本 100.0.1185.17：3 月 23 日

修复了各种 bug 和性能问题。

## <a name="version-1000118512-march-18"></a>版本 100.0.1185.12：3 月 18 日

修复了各种 bug 和性能问题。

### <a name="feature-updates"></a>功能更新

- **简化 Microsoft 365 应用程序协议激活。** 现在 受信任的 Microsoft 云存储服务上的 Microsoft 365 应用程序协议激活将直接启动某些 Microsoft 365 应用程序，包括 SharePoint 子域和 Microsoft OneDrive URL。 可以使用策略 [AutoLaunchProtocolsComponentEnabled](/deployedge/microsoft-edge-policies#autolaunchprotocolscomponentenabled) 和 [AutoLaunchProtocolsFromOrigins](/deployedge/microsoft-edge-policies#autolaunchprotocolsfromorigins) 启用应用程序协议激活提示（如果需要），并定义启用或禁用警告的其他应用程序和服务。

## <a name="version-1000118510-march-17"></a>版本 100.0.1185.10：3 月 17 日

### <a name="feature-updates"></a>功能更新

- **对 IE 模式的云站点列表管理体验的改进。** 可以在Microsoft 365 管理中心的站点列表中为 IE 模式的Microsoft Edge和 Internet Explorer 之间配置会话 Cookie 共享。 **注意：** 这是受控功能的推出。 如果看不到此功能，请在继续推出时返回

- **在 Microsoft Outlook 和文件资源管理器中预览 PDF 文件。** 用户可以在轻量级且丰富的只读预览版中查看 PDF 文件。  可用于Outlook桌面 PDF 附件或使用 文件资源管理器 的本地 PDF 文件。  

- **在所有桌面设备上安装的 Web 应用同步。** 已安装为应用程序的网站或渐进式Web 应用 (PVA) 将在已登录并启用同步的所有桌面设备之间同步。 它们将显示为“可用应用”供你安装。 从一台设备中删除的应用将在所有设备上同步删除。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

- [AdsTransparencyEnabled](/DeployEdge/microsoft-edge-policies#adstransparencyenabled) - 配置是否启用广告透明度功能
- [DefaultWebHidGuardSetting](/DeployEdge/microsoft-edge-policies#defaultwebhidguardsetting) - 控制 WebHID API 的使用
- [HideRestoreDialogEnabled](/DeployEdge/microsoft-edge-policies#hiderestoredialogenabled) - 在浏览器崩溃后隐藏还原页对话框
- [PDFSecureMode](/DeployEdge/microsoft-edge-policies#pdfsecuremode) - 本机 PDF 阅读器中的安全模式和基于证书的数字签名验证
- [PromptOnMultipleMatchingCertificates](/DeployEdge/microsoft-edge-policies#promptonmultiplematchingcertificates) - 当多个证书匹配时提示用户选择证书
- [WebHidAskForUrls](/DeployEdge/microsoft-edge-policies#webhidaskforurls) - 允许在这些网站上使用 WebHID API
- [WebHidBlockedForUrls](/DeployEdge/microsoft-edge-policies#webhidblockedforurls) - 阻止这些网站上的 WebHID API

#### <a name="deprecated-policy"></a>已弃用策略

- [BackgroundTemplateListUpdatesEnabled](/DeployEdge/microsoft-edge-policies#backgroundtemplatelistupdatesenabled) - 对“集锦”和使用模板的其他功能启用可用模板列表后台更新

#### <a name="obsoleted-policy"></a>已过时的策略

- [AllowSyncXHRInPageDismissal](/DeployEdge/microsoft-edge-policies#allowsyncxhrinpagedismissal) - 允许页面在页面关闭期间发送同步 XHR 请求。

## <a name="version-990115039-march-10"></a>版本 99.0.1150.39：3 月 10 日

### <a name="feature-updates"></a>功能更新

- **对 IE 模式的云站点列表管理体验的改进。** 通过使用 [InternetExplorerIntegrationCloudUserSitesReporting](/deployedge/microsoft-edge-policies#internetexplorerintegrationcloudusersitesreporting) 和 [InternetExplorerIntegrationCloudNeutralSitesReporting](/deployedge/microsoft-edge-policies#internetexplorerintegrationcloudneutralsitesreporting) 策略配置网站反馈报告，确定企业网站列表中的差距。 可以在Microsoft 365 管理中心Microsoft Edge网站列表体验中查看来自用户的本地站点列表 URL 以及可能配置错误的中性站点 URL。 若要了解详细信息，请参阅[Microsoft 365 管理中心的“查看网站反馈](/deployedge/edge-ie-mode-cloud-site-list-mgmt#view-site-feedback-on-the-microsoft-365-admin-center-1)”。  **注意：** 这是受控功能的推出。 如果看不到此功能，请在继续推出时返回。

## <a name="version-990115030-march-2"></a>版本 99.0.1150.30：3 月 2 日

修复了各种 bug 和性能问题。

## <a name="version-990115025-february-25"></a>版本 99.0.1150.25：2 月 25 日

修复了各种 bug 和性能问题。

## <a name="version-990115021-february-22"></a>版本 99.0.1150.21：2 月 22 日

修复了各种 bug 和性能问题。

## <a name="version-990115016-february-14"></a>版本 99.0.1150.16：2 月 14 日

修复了各种 bug 和性能问题。

<!--- From Version 99.0.1150.11: February 9 to Version 98.0.1108.27: January 19 --->
<!-- archive from Version 98.0.1108.23: January 14 to Version 97.0.1072.28: December 8 -->
<!--- Version 97.0.1072.21: December 1 to Version 96.0.1054.13: November 5  --->
<!--- archive from Version 96.0.1054.8: November 1 to Version 95.0.1020.14: October 5  --->
<!-- archive from version 95.0.1020.9: September 28 to version 94.0.992.14: September 7 -->
<!-- archive from Version 94.0.992.9: September 2 to Version 92.0.902.40: July 6 -->
<!--Archive from Version 92.0.902.22: June 21 to Version 89.0.774.23: February 8  -->
<!-- Archive from Version 87.0.664.18: October 26 to to version 89.0.774.18: February 3 --->
<!-- Archive from Version 87.0.664.12: October 20 to version 86.0.622.15: September 14 -->
<!--- Archived to version 86.0.622.11: September 9 ---->
<!--- Archived to version 85.0.564.18: July 28 ---->

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)

