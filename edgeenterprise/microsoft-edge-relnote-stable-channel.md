---
title: Microsoft Edge Stable 渠道发行说明
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 01/13/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Stable 渠道发行说明
ms.openlocfilehash: a69b6cd7ab1fa077f2a72c01fa363fcc0efdcf24
ms.sourcegitcommit: 498a62144b099a1198c06f98ad010cf95aa33727
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "11268233"
---
# Microsoft Edge Stable 渠道发行说明

这些发行说明提供有关 Microsoft Edge Stable 渠道中包含的新功能和非安全更新的信息。

- [此处](microsoft-edge-relnotes-security.md)列出所有安全更新。
- Microsoft Edge 稳定渠道的存档发行说明位于[此处](microsoft-edge-relnote-archive-stable-channel.md)。

 若要了解 Microsoft Edge 渠道，请参阅 [Microsoft Edge 渠道概述](microsoft-edge-channels.md)。

> [!NOTE]
> 对于稳定渠道，更新将在一天或多天内逐步推出。 若要了解详细信息，请参阅 [Microsoft Edge 更新的渐进式推出](microsoft-edge-update-progressive-rollout.md)。

## 版本87.0.664.75：1 月 7 日

[此处](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#january-7-2021)列出安全更新。

## 版本 87.0.664.66：12 月 17 日

修复了各种 bug 和性能问题。

## 版本 87.0.664.60：12 月 10 日

修复了各种 bug 和性能问题。

## 版本87.0.664.57：12月7日

修复了各种 bug 和性能问题。 [此处](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#december-7-2020)列出安全更新。

## 版本 87.0.664.55：12月3日

修复了各种 bug 和性能问题。 此版本的以下功能已更新。

- **默认情况下，购物处于启用状态**。 从 Microsoft Edge 版本87开始，企业用户可从 Microsoft Edge 中的购物中受益。 通过购物功能，Microsoft Edge 可帮助用户在在线购物时查找优惠券和更好的价格。 （稳定版本 87.0.664.41 的优惠券体验已发布。） 价格比较体验现已通过此更新提供。 此功能可使用 [EdgeShoppingAssistantEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#edgeshoppingassistantenabled) 策略进行配置。 查看我们的[博客](https://blogs.windows.com/windowsexperience/2020/11/19/finish-up-that-holiday-shopping-with-new-features-from-microsoft-edge-and-bing/) ，了解有关 Microsoft 购物的[详细信息](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper#shopping)。

## 版本 87.0.664.52：11月30日

修复了各种 bug 和性能问题。

## 版本 87.0.664.47：11 月 23 日

修复了各种 bug 和性能问题。

<!-- begin major 87 --->
## 版本 87.0.664.41：11 月 19 日

[此处](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#november-19-2020)列出安全更新。

### 功能更新

- **从 Internet Explorer 到 Microsoft Edge 的不兼容网站的自动重定向**。 从 Microsoft Edge 87 稳定更新开始，在 Internet Explorer 上显示不兼容消息的公共网站将自动重定向到 Microsoft Edge。 若要了解详细信息并配置此体验，请参阅 [重定向不兼容的网站](https://docs.microsoft.com/deployedge/edge-learnmore-neededge)。

- **已启用展台模式隐私功能**。 从 Microsoft Edge 87 版本开始，将启用帮助企业实现用户数据隐私的展台模式功能。 这些功能将启用以下体验，例如，在退出时清除用户数据、删除已下载的文件，以及在指定的空闲时间后重置配置的启动体验。 深入了解如何[配置 Microsoft Edge 的展台模式](https://docs.microsoft.com/deployedge/microsoft-edge-configure-kiosk-mode)

- **默认情况下启用的购物功能**。 从 Microsoft Edge 版本 87 开始，企业用户也可以从 Edge 购物中受益。 通过购物功能，Microsoft Edge 可帮助用户在在线购物时查找优惠券和更好的价格。 通过此更新提供优惠券体验，价格比较将在 Microsoft Edge 87 的即将推出的更新中发布。 此功能可通过 [EdgeShoppingAssistantEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#edgeshoppingassistantenabled) 策略进行配置。 查看我们的[博客](https://blogs.windows.com/windowsexperience/2020/11/19/finish-up-that-holiday-shopping-with-new-features-from-microsoft-edge-and-bing/) ，了解有关 Microsoft 购物的[详细信息](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper#shopping)。

- **在默认情况下启用 ClickOnce 部署**。 Microsoft Edge 87 中默认启用 ClickOnce，这可减少企业部署软件的障碍，并更好地与 Microsoft Edge 旧版浏览器行为保持一致。 从 Microsoft Edge 87 开始，ClickOnceEnabled 策略的“未配置”状态将反映新的默认已启用 ClickOnce 状态（与先前默认“已禁用”状态相比）。

- **企业新选项卡页面（NTP）将生产力与可定制的、与工作相关的源内容整合在一起**。 企业 NTP 将我们提供给用工作或学校账户登录的用户 Office 365 生产率页面与与个性化的、与工作相关的公司和行业信息源融合在一起，并将这些信息源组织在单个页面中。 用户将能够识别熟悉的 Office 365 内容和由 Bing 提供支持的 Microsoft 搜索商业版。 此外，他们可以通过从其组织的可用内容和模块中选择最相关的内容，轻松自定义“我的源”。 IT 管理员可以通过转到 Microsoft 365 管理中心来控制其组织的新闻源设置，包括为 Edge 新建选项卡页所选定的行业。 [了解详细信息](https://blogs.windows.com/msedgedev/2020/10/29/enterprise-new-tab-page-my-feed/)

- **隐私和安全：**

  - 支持策略配置网站的TLS令牌绑定。 TLS令牌绑定有助于防止令牌窃取攻击，以确保无法从初始设置的设备以外的设备上重新使用cookie。 使用 TLS 令牌绑定需要设置 [AllowTokenBindingForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowtokenbindingforurls) 策略，并要求列出的网站支持该功能。

- ** 键盘支持对PDF文件的高亮显示**。 用户可使用其键盘键来突出显示 PDF 中的任何文本。

- **打印：**

  - 双面打印时选择翻转的是哪一面。 用户在双面打印时，可以选择在纸张的长边或短边进行翻转。
  - 选择企业的打印光栅化模式。 控制 Microsoft Edge 打印到 Windows 上的非 PostScript 打印机的方式。 有时，在非PostScript打印机上的打印作业需要进行光栅化才能正确打印。 打印选项有 “完整” 和 “快速”。

### 策略更新

#### 新策略

增加了十项新政策。 从 [Microsoft Edge 企业登录页面](https://www.microsoft.com/edge/business/download)下载更新的管理模板。 已添加以下新策略。

- [ConfigureFriendlyURLFormat](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#configurefriendlyurlformat) - 配置从 Microsoft Edge 复制的 Url 的默认粘贴格式，并确定用户是否可以使用其他格式。
- [EdgeShoppingAssistantEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#edgeshoppingassistantenabled) - 已启用 Microsoft Edge 中的购物。
- [HideInternetExplorerRedirectUXForIncompatibleSitesEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#hideinternetexplorerredirectuxforincompatiblesitesenabled) - 隐藏 Microsoft Edge 上的一次性重定向对话框和横幅。
- [KioskAddressBarEditingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskaddressbareditingenabled) - 配置地址栏编辑，实现展台模式的公共浏览体验。
- [KioskDeleteDownloadsOnExit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#kioskdeletedownloadsonexit) - 删除 Microsoft Edge 关闭时作为展台会话的一部分下载的文件。
- [PasswordRevealEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#passwordrevealenabled) -“启用密码显示”按钮。
- [RedirectSitesFromInternetExplorerPreventBHOInstall](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#redirectsitesfrominternetexplorerpreventbhoinstall) - 阻止安装浏览器帮助程序对象 (BHO) 将不兼容的网站从 Internet Explorer 重定向到 Microsoft Edge。
- [RedirectSitesFromInternetExplorerRedirectMode](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#redirectsitesfrominternetexplorerredirectmode) - 将不兼容的网站从 Internet Explorer 重定向到 Microsoft Edge。
- [SpeechRecognitionEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#speechrecognitionenabled) - 配置语音识别。
- [WebCaptureEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webcaptureenabled) - 启用 Microsoft Edge 中的网页获取功能。

#### 已弃用政策

[NewTabPageSetFeedType](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagesetfeedtype) - 配置 Microsoft Edge 的新选项卡页面体验。

#### 已过时的策略

[EnableDeprecatedWebPlatformFeatures](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enabledeprecatedwebplatformfeatures) - 在有限的时间内重新启用已超过限定时间的 web 平台功能。

<!-- end major 87 -->

## 版本 86.0.622.69：11 月 13 日

[此处](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#november-13-2020)列出安全更新。 此更新包含已由 Chromium 团队报告的在现实中被利用的 [CVE-2020-16013](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16013) 和 [CVE-2020-16017](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16017)。

## 版本 86.0.622.68：11 月 11 日

[此处](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#november-11-2020)列出安全更新

## 版本 86.0.622.63：11 月 4 日

[此处](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#november-4-2020)列出安全更新。 此更新包含已由 Chromium 团队报告的在现实中被利用的 [CVE-2020-16009](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16009)。

## 版本 86.0.622.61：11 月 2 日

修复了各种 bug 和性能问题。

## 版本 86.0.622.58：10 月 29 日

修复了各种 bug 和性能问题。

## 版本 86.0.622.56：10 月 27 日

修复了各种 bug 和性能问题。

## 版本 86.0.622.51：10 月 22 日

[此处](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#october-22-2020)列出安全更新

## 版本 86.0.622.48：10 月 20 日

修复了各种 bug 和性能问题。

## 版本 86.0.622.43：10 月 15 日

修复了各种 bug 和性能问题。

<!-- begin major 86 -->
## 版本 86.0.622.38：10 月 9 日

[此处](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#october-9-2020)列出安全更新

### 功能更新

* **回退到先前的 Microsoft Edge 版本。** 如果最新版本的 Microsoft Edge 中有问题，则“回退”功能可让管理员还原到已知的正确版本的 Microsoft Edge。 **注意：** 稳定版本 86.0.622.38 是你可以回滚到的第一个版本，这意味着稳定版本 87 是可以从中回滚的第一个版本。 [了解详细信息](edge-learnmore-rollback.md)。

* **默认情况下，在企业范围内强制启用“同步”。**  默认情况下，管理员可使用[ForceSync](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcesync) 策略为 Azure Active Directory (Azure AD) 帐户启用同步。

* **Windows 7 和 8.1 上的自动配置文件切换。** Windows 10 上的 Microsoft Edge 中当前提供的自动配置文件切换扩展到了早期版本的 Windows（Windows 7 和 8.1）。 有关详细信息，请参阅博客文章中的[自动配置文件 切换](https://blogs.windows.com/msedgedev/2020/04/30/automatic-profile-switching/)。

* ** 默认情况下 SameSite=Lax Cookies**。 为了提高 Web 安全性和隐私，默认情况下，Cookie 将默认为 [SameSite=Lax](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite) 处理。 这意味着 Cookie 将仅在第一方上下文中发送，而对于发送给第三方的请求将被忽略。 此更改可能会对需要 Cookie 才能使第三方资源正常运行的网站造成兼容性影响。 为了允许此类 Cookie，Web 开发人员可以通过在设置 Cookie 时添加显式 `SameSite=none` 和 `Secure` 属性来标记应从第三方上下文设置并发送给第三方上下文的 Cookie。 希望将某些网站排除在此更改之外的企业可以使用 [LegacySameSiteCookieBehaviorEnabledForDomainList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#legacysamesitecookiebehaviorenabledfordomainlist) 策略执行此操作，也可以使用 [LegacySameSiteCookieBehaviorEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#legacysamesitecookiebehaviorenabled) 策略在所有网站上选择退出此更改。

* **删除 HTML5 应用程序缓存 API。**  从 Microsoft Edge 版本 86 开始，从 Microsoft Edge 中删除了启用网页脱机使用的旧版应用程序缓存 API。 有关将应用程序缓存 API 替换为服务工作进程的信息，Web 开发人员可以查看 [WebDev 文档](https://web.dev/appcache-removal/)。  重要提示：你可以请求[ AppCache OriginTrial 令牌](https://developers.chrome.com/origintrials/#/view_trial/1776670052997660673)，该令牌允许网站继续使用已弃用的应用程序缓存 API，直至 Microsoft Edge 版本90。

* **隐私和安全：**

  * **为早期版本的 Windows 和 macOS 替换[MetricsReportingEnabled]( https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) 和 [SendSiteInformationToImproveServices]( https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices)策略。** 这些策略在 Microsoft Edge 版本 86 中已弃用，在 Microsoft Edge 版本 89 中将不再使用。<br>
这些策略将被 Windows 10 上的[允许遥测](https://go.microsoft.com/fwlink/?linkid=2099569)和所有其他平台的全新[DiagnosticData](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#diagnosticdata) 策略取代。 这将使用户能够为 Windows 7、8、8.1 和 macOS 管理发送到 Microsoft 的诊断数据。
  * 安全 DNS (DNS-over-HTTPS) 支持。  从 Microsoft Edge 版本 86 开始，可以使用设置来控制非托管设备上的安全 DNS。 用户无法访问已托管设备上的这些设置，但 IT 管理员可以使用 [dnsoverhttpsmode](https://docs.microsoft.com/deployedge/microsoft-edge-policies#dnsoverhttpsmode) 组策略启用或禁用安全 DNS。

* **Internet Explorer 模式：** 让用户使用 Microsoft Edge 用户界面 (UI) 在 Internet Explorer 模式下测试网站。 从Microsoft Edge 版本 86 开始，管理员可以为用户启用一个 UI 选项，让用户在 Internet Explorer 模式加载一个选项卡，以进行测试，或者在网站被添加到网站列表的 XML 中之前作为替代。

* **PDF 更新：**

  * PDF 文档目录。 从版本 86 开始，Microsoft Edge 添加了对目录的支持，可让用户轻松浏览 PDF 文档。
  * 在小型外形规格屏幕上访问所有 PDF 功能。 在具有小型屏幕尺寸的设备上访问 Microsoft Edge PDF 阅读器的所有功能。
  * PDF 文件上对荧光笔的支持。 通过此更新，用户可使用数字荧光笔直接突出显示 PDF 文件上的文本，就像使用物理荧光笔和纸张一样。
  * 改进了 PDF 滚动。 现在，你可以在浏览较长的 PDF 文档时体验流畅的滚动效果。

* **当用户开始在 Microsoft Edge 加载项网站中键入搜索查询时，将看到自动完成建议。** 自动完成将帮助用户快速完成搜索查询，而无需键入完整字符串。 这将非常有用，因为用户无需记住正确的拼写，可以从显示的可用选项中进行选择。

* **使用组策略向全新选项卡页面 (NTP) 中添加自定义图像。** 从 Microsoft Edge 版本 86 开始，NTP 可以选择使用自定义用户提供的图像来替换默认图像。 组策略也支持管理此图像属性的功能。

* **匹配自定义键盘快捷方式与 VS Code。** Microsoft Edge 开发工具现在支持自定义开发工具中的键盘快捷方式，使其匹配你的编辑器/IDE。 （在 Microsoft Edge 84 中，我们添加了匹配开发工具键盘快捷方式和 VS Code 的功能）。

* **使用下载管理器从磁盘删除下载。** 用户现在无需离开浏览器即可从磁盘中删除其载的文件。 全新“删除下载”功能位于下载架或下载页面的弹出菜单中。

### 策略更新

#### 新策略

添加了 23 个新策略。 从 [Microsoft Edge 企业登录页面](https://aka.ms/EdgeEnterprise)下载更新的管理模板。 已添加以下新策略。

- [CollectionsServicesAndExportsBlockList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#collectionsservicesandexportsblocklist) - 阻止访问指定服务列表及在集锦中导出目标。
- [DefaultFileSystemReadGuardSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultfilesystemreadguardsetting) - 控制文件系统 API 在读取中的使用。
- [DefaultFileSystemWriteGuardSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultfilesystemwriteguardsetting) -控制文件系统 API 在写入中的使用。
- [DefaultSensorsSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultsensorssetting) - 默认传感器设置。
- [DefaultSerialGuardSetting](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultserialguardsetting) - 控制串行 API 的使用。
- [DiagnosticData](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#diagnosticdata) - 发送有关浏览器使用情况的必需和可选诊断数据。
- [EnterpriseModeSiteListManagerAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enterprisemodesitelistmanagerallowed) - 允许访问 Enterprise Mode Site List Manager 工具。
- [FileSystemReadAskForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#filesystemreadaskforurls) - 允许在这些网站上通过文件系统 API 进行读取访问。
- [FileSystemReadBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#filesystemreadblockedforurls) - 阻止在这些网站上通过文件系统 API 进行读取访问。
- [FileSystemWriteAskForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#filesystemwriteaskforurls) - 允许在这些网站上对文件和目录进行写入访问。
- [FileSystemWriteBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#filesystemwriteblockedforurls) - 阻止在这些网站上对文件和目录进行写入访问。
- [ForceSync](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#forcesync) - 强制同步浏览器数据，但不显示同步许可提示。
- [InsecureFormsWarningsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#insecureformswarningsenabled) - 启用不安全窗体的警告。
- [InternetExplorerIntegrationTestingAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#internetexplorerintegrationtestingallowed) - 允许 Internet Explorer 模式测试。
- [SpotlightExperiencesAndRecommendationsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#spotlightexperiencesandrecommendationsenabled) - 选择用户是否可接收自定义的背景图像和文本、建议、通知及 Microsoft 服务提示。
- [NewTabPageAllowedBackgroundTypes](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpageallowedbackgroundtypes) - 配置全新选项卡页面布局允许使用的背景类型。
- [SaveCookiesOnExit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#savecookiesonexit) - Microsoft Edge 关闭时保存 Cookie。
- [SensorsAllowedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sensorsallowedforurls) - 允许访问特定网站上的传感器。
- [SensorsBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sensorsblockedforurls) - 阻止访问特定网站上的传感器。
- [SerialAskForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#serialaskforurls) - 在特定网站上允许串行 API。
- [SerialBlockedForUrls](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#serialblockedforurls) - 在特定网站上阻止串行 API。
- [UserAgentClientHintsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#useragentclienthintsenabled) - 启用“User-Agent 客户端提示”功能（已弃用）。
- [UserDataSnapshotRetentionLimit](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#userdatasnapshotretentionlimit) - 限制保留用于紧急回退情况的用户数据快照数量。

#### 已弃用的策略

- [MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled)：启用使用情况和故障相关数据报告。
- [SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices)：发送站点信息以改进 Microsoft 服务。

#### 已过时的策略

[TLS13HardeningForLocalAnchorsEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#tls13hardeningforlocalanchorsenabled) - 为本地信任密钥启用 TLS 1.3 安全功能。

<!-- end 86 -->
## 版本 85.0.564.70：10 月 6 日

修复了各种 bug 和性能问题。

## 版本 85.0.564.68：10 月 1 日

修复了各种 bug 和性能问题。

## 版本 85.0.564.63: 9 月 23 日

[此处](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#september-23-2020)列出安全更新

## 版本 85.0.564.51：9 月 9 日

[此处](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#september-9-2020)列出安全更新

## 版本 85.0.564.44：8 月 31 日

修复了各种 bug 和性能问题。
<!-- begin 85 -->
## 版本 85.0.564.41：8 月 27 日

[此处](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#august-27-2020)列出安全更新

### 功能更新

- **收藏夹和设置的本地同步**。 你现在可以在自己的环境中实现 Active Directory 配置文件之间的浏览器收藏夹和设置同步，而无需云同步。

- **使用 Microsoft Edge 组策略支持，无需确认提示即可启动信任网站 + 应用组合。** 已添加的组策略支持允许管理员添加受信任的网站 + 应用组合，无需确认提示即可启动。 这添加了一项功能，让管理员为其最终用户配置信任协议/原点组合（例如 Microsoft 365 应用），从而在导航到包含应用协议的 URL 时禁止确认提示。

- **PDF 荧光笔工具**。 此工具可添加到 PDF 工具栏中，方便突出显示重要文本。

- **存储访问 API 现可使用**。 当用户直接指示允许本来会被浏览器的当前配置阻止的存储时，可使用此存储访问 API 来访问第三方上下文中的第一方存储。 有关详细信息，请参阅[存储访问 API](https://www.chromestatus.com/feature/5612590694662144)。

- **Microsoft Edge 集合现可使用“发送至 OneNote”**。 所有人都期待能将集合中已收集的信息发送至 OneNote，从而追加信息到更大的项目中，与他人进行协作！ 更重要的是，在 Microsoft Edge 85 中，使用 Microsoft 帐户和 Azure Active Directory 均可发送内容到 *Office for Mac* 产品（Word、Excel 和 OneNote）。

- **开发工具更新**。 有关以下更新的详细信息，请参阅[开发工具新增功能 (Microsoft Edge 85)](https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/whats-new/2020/06/devtools)。

   - Microsoft Edge 开发工具支持 Surface Duo 仿真。 Microsoft Edge 开发工具能够仿真 Surface Duo，因此可测试 Web 内容在双屏设备上的显示效果。 若要在开发工具中打开此试验，请在 Windows 上按 Ctrl+Shift+M 或在 macOS 上按 Command+Shift+M 来输入设备模式，然后在设备下拉列表中选择 Surface Duo。
   - Microsoft Edge 开发工具允许键盘快捷方式和 VS Code 相匹配。 Microsoft Edge 开发工具支持自定义开发工具中的键盘快捷方式，使其匹配你的编辑器/IDE。 在 Microsoft Edge 85 中，我们添加了匹配开发工具键盘快捷方式和 VS Code 的功能。 此更改将有助于增加 VS Code 和开发工具之间的工作效率。

### 策略更新

#### 新策略

添加了 13 个新策略。 从 [Microsoft Edge 企业登录页面](https://aka.ms/EdgeEnterprise)下载更新的管理模板。 已添加以下新策略。

- [AutoLaunchProtocolsFromOrigins](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autolaunchprotocolsfromorigins) - 定义可从列出的源启动外部应用程序的协议的列表，而无需提示用户。
- [AutoOpenAllowedForURLs](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autoopenallowedforurls) - AutoOpenFileTypes 可应用的 URL。
- [AutoOpenFileTypes](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#autoopenfiletypes) - 下载时自动打开的文件类型列表。
- [DefaultSearchProviderContextMenuAccessAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#defaultsearchprovidercontextmenuaccessallowed) - 允许默认搜索提供程序中的上下文菜单搜索访问。
- [EnableSha1ForLocalAnchors](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors) - 允许由本地信任定位点颁发的 SHA - 1 签名证书。
- [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - 对域上指定的文件类型，禁用基于文件类型扩展名下载的警告。
- [IntensiveWakeUpThrottlingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#intensivewakeupthrottlingenabled) - 控制 IntensiveWakeUpThrottling 功能。
- [NewTabPagePrerenderEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpageprerenderenabled) - 启用新选项卡页面的预加载，以便快速呈现。
- [NewTabPageSearchBox](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#newtabpagesearchbox) - 配置新的选项卡页面搜索框体验。
- [PasswordMonitorAllowed](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#passwordmonitorallowed) - 当用户的密码被发现不安全时，允许收到警告。
- [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled) - 支持使用 Microsoft Edge 配置文件数据的漫游副本。
- [RoamingProfileLocation](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilelocation) - 设置漫游配置文件目录。
- [TLSCsipherSuiteDenyList](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#tlsciphersuitedenylist) - 指定要禁用的 TLS 密码套件。

#### 已过时的策略

- [EnableDomainActionsDownload](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#enabledomainactionsdownload) - 启用来自 Microsoft 的域操作下载。
- [WebComponentsV0Enabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webcomponentsv0enabled) - 重新启用 Web 组件 v0 API 至 M84。
- [WebDriverOverridesIncompatiblePolicies](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#webdriveroverridesincompatiblepolicies)- 允许 WebDriver 覆盖不兼容策略。

<!--- END 85 ---->

## 版本 84.0.522.63：8 月 20 日

[此处](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#august-20-2020)列出安全更新。

## 版本84.0.522.61：8 月 17 日

修复了各种 bug 和性能问题。

## 版本 84.0.522.59：8 月 11日

[此处](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#august-11-2020)列出安全更新

## 版本 84.0.522.58：8 月 10 日

修复了各种 bug 和性能问题。

## 版本 84.0.522.52：8 月 1 日

修复了各种 bug 和性能问题。

## 版本 84.0.522.50：7 月 31 日

修复了各种 bug 和性能问题。

## 版本 84.0.522.49：7 月 29 日

[此处](https://docs.microsoft.com/DeployEdge/microsoft-edge-relnotes-security#july-29-2020)列出安全更新

## 版本 84.0.522.48：7 月 28 日

修复了各种 bug 和性能问题。

## 版本 84.0.522.44：7 月 23 日

修复了各种 bug 和性能问题。

<!-- Archived to version 84.0.522.40: July 16 -->

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
