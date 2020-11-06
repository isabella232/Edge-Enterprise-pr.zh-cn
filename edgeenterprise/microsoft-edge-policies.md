---
title: Microsoft Edge 浏览器策略文档
ms.author: stmoody
author: dan-wesley
manager: tahills
ms.date: 11/04/2020
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Microsoft Edge 浏览器支持的所有策略的 Windows 和 Mac 文档
ms.openlocfilehash: 0e708707ae8465aa49ee49dcec542881a5080a57
ms.sourcegitcommit: a5b13de18c5f9006c92a7c8deba1e1645601ad5c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "11155309"
---
# Microsoft Edge - 策略

最新版本的 Microsoft Edge 包含以下策略。 可以使用这些策略来配置在你的组织中运行 Microsoft Edge 的方式。

有关用于控制 Microsoft Edge 的更新方式和时间的其他策略集的信息，请查看 [Microsoft Edge 更新策略参考](microsoft-edge-update-policies.md)。

可下载 [Microsoft Security Compliance Toolkit](https://www.microsoft.com/download/details.aspx?id=55319)，以获得 Microsoft Edge 的建议安全配置基线设置。 有关详细信息，请参阅 [Microsoft 安全基线博客](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/bg-p/Microsoft-Security-Baselines)。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## 新的和已弃用的策略

下表列出了对于此更新新的和已弃用的策略。

| 名称 | 状态 |
|-|-|
| [WebWidgetAllowed](#webwidgetallowed) | 新增 |
| [ProxyBypassList](#proxybypasslist) | 已弃用 |
| [ProxyMode](#proxymode) | 已弃用 |
| [ProxyPacUrl](#proxypacurl) | 已弃用 |
| [ProxyServer](#proxyserver) | 已弃用 |

## 可用策略

这些表列出了本版本 Microsoft Edge 中提供的所有与浏览器相关的组策略。 使用表中的链接获取有关特定策略的更多详细信息。

|||
|-|-|
|[应用程序防护设置](#application-guard-settings)|[Cast](#cast)|
|[内容设置](#content-settings)|[默认搜索提供程序](#default-search-provider)|
|[Extensions](#extensions)|[HTTP 身份验证](#http-authentication)|
|[展台模式设置](#kiosk-mode-settings)|[本机消息传递](#native-messaging)|
|[密码管理器和保护](#password-manager-and-protection)|[性能](#performance)|
|[打印](#printing)|[代理服务器](#proxy-server)|
|[SmartScreen 设置](#smartscreen-settings)|[启动、主页和新选项卡页](#startup-home-page-and-new-tab-page)|
|[附加](#additional)|

### [*应用程序防护设置*](#application-guard-settings-policies)

|策略名称|标题|
|-|-|
|[ApplicationGuardContainerProxy](#applicationguardcontainerproxy)|应用程序防护容器代理|
### [*Cast*](#cast-policies)

|策略名称|标题|
|-|-|
|[EnableMediaRouter](#enablemediarouter)|启用 Google Cast|
|[ShowCastIconInToolbar](#showcasticonintoolbar)|在工具栏中显示 Cast 图标|
### [*内容设置*](#content-settings-policies)

|策略名称|标题|
|-|-|
|[AutoSelectCertificateForUrls](#autoselectcertificateforurls)|自动为这些网站选择客户端证书|
|[CookiesAllowedForUrls](#cookiesallowedforurls)|在特定网站上允许 cookie|
|[CookiesBlockedForUrls](#cookiesblockedforurls)|在特定站点上阻止 Cookie|
|[CookiesSessionOnlyForUrls](#cookiessessiononlyforurls)|将来自特定网站的 Cookie 限制为当前会话|
|[DefaultCookiesSetting](#defaultcookiessetting)|配置 Cookie|
|[DefaultFileSystemReadGuardSetting](#defaultfilesystemreadguardsetting)|控制文件系统 API 在读取中的使用|
|[DefaultFileSystemWriteGuardSetting](#defaultfilesystemwriteguardsetting)|控制文件系统 API 在写入中的使用|
|[DefaultGeolocationSetting](#defaultgeolocationsetting)|默认地理位置设置|
|[DefaultImagesSetting](#defaultimagessetting)|默认图像设置|
|[DefaultInsecureContentSetting](#defaultinsecurecontentsetting)|控制不安全内容异常的使用|
|[DefaultJavaScriptSetting](#defaultjavascriptsetting)|默认 JavaScript 设置|
|[DefaultNotificationsSetting](#defaultnotificationssetting)|默认通知设置|
|[DefaultPluginsSetting](#defaultpluginssetting)|默认 Adobe Flash 设置|
|[DefaultPopupsSetting](#defaultpopupssetting)|默认弹出窗口设置|
|[DefaultWebBluetoothGuardSetting](#defaultwebbluetoothguardsetting)|控制 Web 蓝牙 API 的使用|
|[DefaultWebUsbGuardSetting](#defaultwebusbguardsetting)|控制 WebUSB API 的使用|
|[FileSystemReadAskForUrls](#filesystemreadaskforurls)|允许在这些网站上通过文件系统 API 进行读取访问|
|[FileSystemReadBlockedForUrls](#filesystemreadblockedforurls)|阻止在这些网站上通过文件系统 API 进行读取访问|
|[FileSystemWriteAskForUrls](#filesystemwriteaskforurls)|允许在这些网站上对文件和目录进行写入访问|
|[FileSystemWriteBlockedForUrls](#filesystemwriteblockedforurls)|阻止在这些网站上对文件和目录进行写入访问|
|[ImagesAllowedForUrls](#imagesallowedforurls)|在这些网站上允许图像|
|[ImagesBlockedForUrls](#imagesblockedforurls)|在这些网站上阻止图像|
|[InsecureContentAllowedForUrls](#insecurecontentallowedforurls)|在指定网站上允许不安全内容|
|[InsecureContentBlockedForUrls](#insecurecontentblockedforurls)|在指定网站上阻止不安全内容|
|[JavaScriptAllowedForUrls](#javascriptallowedforurls)|在特定网站上允许 JavaScript|
|[JavaScriptBlockedForUrls](#javascriptblockedforurls)|在特定网站上阻止 JavaScript|
|[LegacySameSiteCookieBehaviorEnabled](#legacysamesitecookiebehaviorenabled)|启用默认旧 SameSite Cookie 行为设置|
|[LegacySameSiteCookieBehaviorEnabledForDomainList](#legacysamesitecookiebehaviorenabledfordomainlist)|在指定网站上还原为 Cookie 的旧 SameSite 行为|
|[NotificationsAllowedForUrls](#notificationsallowedforurls)|在特定网站上允许通知|
|[NotificationsBlockedForUrls](#notificationsblockedforurls)|在特定网站上阻止通知|
|[PluginsAllowedForUrls](#pluginsallowedforurls)|在特定网站上允许 Adobe Flash 插件|
|[PluginsBlockedForUrls](#pluginsblockedforurls)|在特定网站上阻止 Adobe Flash 插件|
|[PopupsAllowedForUrls](#popupsallowedforurls)|在特定网站上允许弹出窗口|
|[PopupsBlockedForUrls](#popupsblockedforurls)|在特定网站上阻止弹出窗口|
|[RegisteredProtocolHandlers](#registeredprotocolhandlers)|注册协议处理程序|
|[SpotlightExperiencesAndRecommendationsEnabled](#spotlightexperiencesandrecommendationsenabled)|选择用户是否可接收自定义的背景图像和文本、建议、通知，
以及有关 Microsoft 服务的提示|
|[WebUsbAllowDevicesForUrls](#webusballowdevicesforurls)|授予特定网站连接到特定 USB 设备的访问权限|
|[WebUsbAskForUrls](#webusbaskforurls)|在特定网站上允许 WebUSB|
|[WebUsbBlockedForUrls](#webusbblockedforurls)|在特定网站上阻止 WebUSB|
### [*默认搜索提供程序*](#default-search-provider-policies)

|策略名称|标题|
|-|-|
|[DefaultSearchProviderEnabled](#defaultsearchproviderenabled)|启用默认搜索提供程序|
|[DefaultSearchProviderEncodings](#defaultsearchproviderencodings)|默认搜索提供程序编码|
|[DefaultSearchProviderImageURL](#defaultsearchproviderimageurl)|指定默认搜索提供程序的“按图像搜索”功能|
|[DefaultSearchProviderImageURLPostParams](#defaultsearchproviderimageurlpostparams)|使用 POST 的图像 URL 的参数|
|[DefaultSearchProviderKeyword](#defaultsearchproviderkeyword)|默认搜索提供程序关键字|
|[DefaultSearchProviderName](#defaultsearchprovidername)|默认搜索提供程序名称|
|[DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl)|默认搜索提供程序搜索 URL|
|[DefaultSearchProviderSuggestURL](#defaultsearchprovidersuggesturl)|建议的默认搜索提供程序 URL|
|[NewTabPageSearchBox](#newtabpagesearchbox)|配置新建选项卡页面搜索框体验|
### [*Extensions*](#extensions-policies)

|策略名称|标题|
|-|-|
|[ExtensionAllowedTypes](#extensionallowedtypes)|配置允许的扩展类型|
|[ExtensionInstallAllowlist](#extensioninstallallowlist)|允许安装特定扩展|
|[ExtensionInstallBlocklist](#extensioninstallblocklist)|控制无法安装的扩展|
|[ExtensionInstallForcelist](#extensioninstallforcelist)|控制静默安装的扩展|
|[ExtensionInstallSources](#extensioninstallsources)|配置扩展和用户脚本安装源|
|[ExtensionSettings](#extensionsettings)|配置扩展管理设置|
### [*HTTP 身份验证*](#http-authentication-policies)

|策略名称|标题|
|-|-|
|[AllowCrossOriginAuthPrompt](#allowcrossoriginauthprompt)|Allow cross-origin HTTP Authentication prompts|
|[AuthNegotiateDelegateAllowlist](#authnegotiatedelegateallowlist)|指定 Microsoft Edge 可将用户凭据委派到的服务器列表|
|[AuthSchemes](#authschemes)|支持的身份验证方案|
|[AuthServerAllowlist](#authserverallowlist)|配置允许的身份验证服务器列表|
|[DisableAuthNegotiateCnameLookup](#disableauthnegotiatecnamelookup)|在协商 Kerberos 身份验证时禁用 CNAME 查找|
|[EnableAuthNegotiatePort](#enableauthnegotiateport)|在 Kerberos SPN 中包括非标准端口|
|[NtlmV2Enabled](#ntlmv2enabled)|控制是否启用 NTLMv2 身份验证|
### [*展台模式设置*](#kiosk-mode-settings-policies)

|策略名称|标题|
|-|-|
|[KioskAddressBarEditingEnabled](#kioskaddressbareditingenabled)|配置地址栏编辑，实现展台模式的公共浏览体验。|
|[KioskDeleteDownloadsOnExit](#kioskdeletedownloadsonexit)|Microsoft Edge 关闭时删除作为展台会话的一部分下载的文件|
### [*本机消息传递*](#native-messaging-policies)

|策略名称|标题|
|-|-|
|[NativeMessagingAllowlist](#nativemessagingallowlist)|控制用户可使用的本机消息传递主机|
|[NativeMessagingBlocklist](#nativemessagingblocklist)|配置本机消息传递阻止列表|
|[NativeMessagingUserLevelHosts](#nativemessaginguserlevelhosts)|允许用户级本机消息传递主机（已安装但没有管理员权限）|
### [*密码管理器和保护*](#password-manager-and-protection-policies)

|策略名称|标题|
|-|-|
|[PasswordManagerEnabled](#passwordmanagerenabled)|允许将密码保存到密码管理器|
|[PasswordMonitorAllowed](#passwordmonitorallowed)|如果用户发现其密码不安全，则允许其收到通知|
|[PasswordProtectionChangePasswordURL](#passwordprotectionchangepasswordurl)|配置更改密码 URL|
|[PasswordProtectionLoginURLs](#passwordprotectionloginurls)|配置密码保护服务应在其中捕获加盐密码哈希的企业登录 URL 列表|
|[PasswordProtectionWarningTrigger](#passwordprotectionwarningtrigger)|配置密码保护警告触发器|
|[PasswordRevealEnabled](#passwordrevealenabled)|启用“显示密码”按钮|
### [*性能*](#performance-policies)

|策略名称|标题|
|-|-|
|[StartupBoostEnabled](#startupboostenabled)|启用启动增强|
### [*打印*](#printing-policies)

|策略名称|标题|
|-|-|
|[DefaultPrinterSelection](#defaultprinterselection)|默认打印机选择规则|
|[PrintHeaderFooter](#printheaderfooter)|打印页眉和页脚|
|[PrintPreviewUseSystemDefaultPrinter](#printpreviewusesystemdefaultprinter)|将系统默认打印机设置为默认打印机|
|[PrintingEnabled](#printingenabled)|启用打印|
|[PrintingPaperSizeDefault](#printingpapersizedefault)|默认打印页面大小|
|[UseSystemPrintDialog](#usesystemprintdialog)|使用系统打印对话框打印|
### [*代理服务器*](#proxy-server-policies)

|策略名称|标题|
|-|-|
|[ProxyBypassList](#proxybypasslist)|配置代理跳过规则（已弃用）|
|[ProxyMode](#proxymode)|配置代理服务器设置（已弃用）|
|[ProxyPacUrl](#proxypacurl)|设置代理 .pac 文件 URL（已弃用）|
|[ProxyServer](#proxyserver)|配置代理服务器的地址或 URL|
|[ProxySettings](#proxysettings)|代理设置|
### [*SmartScreen 设置*](#smartscreen-settings-policies)

|策略名称|标题|
|-|-|
|[PreventSmartScreenPromptOverride](#preventsmartscreenpromptoverride)|阻止跳过 Microsoft Defender SmartScreen 有关网站的提示|
|[PreventSmartScreenPromptOverrideForFiles](#preventsmartscreenpromptoverrideforfiles)|阻止跳过 Microsoft Defender SmartScreen 有关下载的警告|
|[SmartScreenAllowListDomains](#smartscreenallowlistdomains)|配置 Microsoft Defender SmartScreen 无法为其触发警告的域列表|
|[SmartScreenEnabled](#smartscreenenabled)|配置 Microsoft Defender SmartScreen|
|[SmartScreenForTrustedDownloadsEnabled](#smartscreenfortrusteddownloadsenabled)|强制 Microsoft Defender SmartScreen 检查从受信任来源下载的内容|
|[SmartScreenPuaEnabled](#smartscreenpuaenabled)|配置 Microsoft Defender SmartScreen 以阻止可能不需要的应用|
### [*启动&comma;、主页和新选项卡页*](#startup-home-page-and-new-tab-page-policies)

|策略名称|标题|
|-|-|
|[HomepageIsNewTabPage](#homepageisnewtabpage)|将新选项卡页设置为主页|
|[HomepageLocation](#homepagelocation)|配置主页 URL|
|[NewTabPageAllowedBackgroundTypes](#newtabpageallowedbackgroundtypes)|配置新选项卡页面布局允许使用的背景类型|
|[NewTabPageCompanyLogo](#newtabpagecompanylogo)|设置新选项卡页公司徽标（已过时）|
|[NewTabPageHideDefaultTopSites](#newtabpagehidedefaulttopsites)|从新选项卡页隐藏默认热门网站|
|[NewTabPageLocation](#newtabpagelocation)|配置新选项卡页 URL|
|[NewTabPageManagedQuickLinks](#newtabpagemanagedquicklinks)|设置新选项卡页快速链接|
|[NewTabPagePrerenderEnabled](#newtabpageprerenderenabled)|启用新选项卡页面的预加载，以便快速呈现|
|[NewTabPageSetFeedType](#newtabpagesetfeedtype)|配置 Microsoft Edge 新建标签页体验（已弃用）|
|[RestoreOnStartup](#restoreonstartup)|启动时要执行的操作|
|[RestoreOnStartupURLs](#restoreonstartupurls)|浏览器启动时要打开的网站|
|[ShowHomeButton](#showhomebutton)|在工具栏上显示“主页”按钮|
### [*附加*](#additional-policies)

|策略名称|标题|
|-|-|
|[AddressBarMicrosoftSearchInBingProviderEnabled](#addressbarmicrosoftsearchinbingproviderenabled)|在地址栏中启用 Microsoft 必应搜索建议|
|[AdsSettingForIntrusiveAdsSites](#adssettingforintrusiveadssites)|含侵扰广告的网站的广告设置|
|[AllowDeletingBrowserHistory](#allowdeletingbrowserhistory)|启用删除浏览器和下载历史记录|
|[AllowFileSelectionDialogs](#allowfileselectiondialogs)|允许文件选择对话框|
|[AllowPopupsDuringPageUnload](#allowpopupsduringpageunload)|允许页面在卸载期间显示弹出窗口|
|[AllowSurfGame](#allowsurfgame)|允许冲浪游戏|
|[AllowSyncXHRInPageDismissal](#allowsyncxhrinpagedismissal)|允许页面在页面关闭期间发送同步 XHR 请求（已弃用）|
|[AllowTokenBindingForUrls](#allowtokenbindingforurls)|配置 Microsoft Edge 将尝试与其建立令牌绑定的站点列表|
|[AllowTrackingForUrls](#allowtrackingforurls)|配置特定网站的跟踪防护例外|
|[AlternateErrorPagesEnabled](#alternateerrorpagesenabled)|找不到网页时建议类似页面|
|[AlwaysOpenPdfExternally](#alwaysopenpdfexternally)|始终在外部打开 PDF 文件|
|[AmbientAuthenticationInPrivateModesEnabled](#ambientauthenticationinprivatemodesenabled)|为 InPrivate 和来宾配置文件启用环境身份验证|
|[AppCacheForceEnabled](#appcacheforceenabled)|允许重新启用 AppCache 功能，即使因默认方式于关闭状态|
|[ApplicationLocaleValue](#applicationlocalevalue)|设置应用程序区域设置|
|[AudioCaptureAllowed](#audiocaptureallowed)|允许或阻止音频捕获|
|[AudioCaptureAllowedUrls](#audiocaptureallowedurls)|无需请求许可即可访问音频捕获设备的网站|
|[AudioSandboxEnabled](#audiosandboxenabled)|允许运行音频沙盒|
|[AutoImportAtFirstRun](#autoimportatfirstrun)|首次运行时自动导入另一个浏览器的数据和设置|
|[AutoLaunchProtocolsFromOrigins](#autolaunchprotocolsfromorigins)|定义可以从列出的源启动外部应用程序而不提示用户的协议列表|
|[AutoOpenAllowedForURLs](#autoopenallowedforurls)|AutoOpenFileTypes 可应用的 URL|
|[AutoOpenFileTypes](#autoopenfiletypes)|在下载中应该自动打开的文件类型列表|
|[AutofillAddressEnabled](#autofilladdressenabled)|启用地址自动填充|
|[AutofillCreditCardEnabled](#autofillcreditcardenabled)|启用信用卡自动填充|
|[AutoplayAllowed](#autoplayallowed)|允许网站媒体自动播放|
|[BackgroundModeEnabled](#backgroundmodeenabled)|Microsoft Edge 关闭后继续运行后台应用|
|[BackgroundTemplateListUpdatesEnabled](#backgroundtemplatelistupdatesenabled)|对“集锦”和使用模板的其他功能启用可用模板列表后台更新|
|[BingAdsSuppression](#bingadssuppression)|阻止必应搜索结果中的所有广告|
|[BlockThirdPartyCookies](#blockthirdpartycookies)|阻止第三方 Cookie|
|[BrowserAddProfileEnabled](#browseraddprofileenabled)|允许从“标识”浮出控件或“设置”页面创建配置文件|
|[BrowserGuestModeEnabled](#browserguestmodeenabled)|启用来宾模式|
|[BrowserNetworkTimeQueriesEnabled](#browsernetworktimequeriesenabled)|允许向浏览器网络时间服务发送查询|
|[BrowserSignin](#browsersignin)|浏览器登录设置|
|[BuiltInDnsClientEnabled](#builtindnsclientenabled)|使用内置 DNS 客户端|
|[BuiltinCertificateVerifierEnabled](#builtincertificateverifierenabled)|确定是否将使用内置证书验证程序来验证服务器证书（已弃用）|
|[CertificateTransparencyEnforcementDisabledForCas](#certificatetransparencyenforcementdisabledforcas)|针对 SubjectPublicKeyInfo 哈希列表禁用证书透明度强制|
|[CertificateTransparencyEnforcementDisabledForLegacyCas](#certificatetransparencyenforcementdisabledforlegacycas)|针对旧证书颁发机构列表禁用证书透明度强制|
|[CertificateTransparencyEnforcementDisabledForUrls](#certificatetransparencyenforcementdisabledforurls)|针对特定 URL 禁用证书透明度强制|
|[ClearBrowsingDataOnExit](#clearbrowsingdataonexit)|在 Microsoft Edge 关闭时清除浏览数据|
|[ClearCachedImagesAndFilesOnExit](#clearcachedimagesandfilesonexit)|在 Microsoft Edge 关闭时清除缓存的图像和文件|
|[ClickOnceEnabled](#clickonceenabled)|允许用户使用 ClickOnce 协议打开文件|
|[CollectionsServicesAndExportsBlockList](#collectionsservicesandexportsblocklist)|阻止访问指定服务列表及在集锦中导出目标|
|[CommandLineFlagSecurityWarningsEnabled](#commandlineflagsecuritywarningsenabled)|启用命令行标志的安全警告|
|[ComponentUpdatesEnabled](#componentupdatesenabled)|在 Microsoft Edge 中启用组件更新|
|[ConfigureDoNotTrack](#configuredonottrack)|配置 Do Not Track|
|[ConfigureFriendlyURLFormat](#configurefriendlyurlformat)|配置从 Microsoft Edge 复制的 URL 的默认粘贴格式，并确定用户是否可以使用其他格式|
|[ConfigureOnPremisesAccountAutoSignIn](#configureonpremisesaccountautosignin)|配置当没有 Azure AD 域帐户时使用 Active Directory 域帐户自动登录|
|[ConfigureOnlineTextToSpeech](#configureonlinetexttospeech)|配置联机文本到语音转换|
|[ConfigureShare](#configureshare)|配置共享体验|
|[CustomHelpLink](#customhelplink)|指定自定义帮助链接|
|[DNSInterceptionChecksEnabled](#dnsinterceptionchecksenabled)|已启用 DNS 拦截检查|
|[DefaultBrowserSettingEnabled](#defaultbrowsersettingenabled)|将 Microsoft Edge 设为默认浏览器|
|[DefaultSearchProviderContextMenuAccessAllowed](#defaultsearchprovidercontextmenuaccessallowed)|允许默认搜索提供程序快捷菜单搜索访问|
|[DefaultSensorsSetting](#defaultsensorssetting)|默认传感器设置|
|[DefaultSerialGuardSetting](#defaultserialguardsetting)|控制串行 API 的使用|
|[DelayNavigationsForInitialSiteListDownload](#delaynavigationsforinitialsitelistdownload)|要求企业模式站点列表在选项卡导航前可用
|
|[DeleteDataOnMigration](#deletedataonmigration)|迁移时删除旧的浏览器数据|
|[DeveloperToolsAvailability](#developertoolsavailability)|控制可使用开发人员工具的位置|
|[DiagnosticData](#diagnosticdata)|发送有关浏览器使用情况的必需和可选诊断数据|
|[DirectInvokeEnabled](#directinvokeenabled)|允许用户使用 DirectInvoke 协议打开文件|
|[Disable3DAPIs](#disable3dapis)|禁用对 3D 图形 API 的支持|
|[DisableScreenshots](#disablescreenshots)|禁止拍摄屏幕截图|
|[DiskCacheDir](#diskcachedir)|设置磁盘缓存目录|
|[DiskCacheSize](#diskcachesize)|设置磁盘缓存大小（以字节为单位）|
|[DnsOverHttpsMode](#dnsoverhttpsmode)|控制 DNS-over-HTTPS 的模式|
|[DnsOverHttpsTemplates](#dnsoverhttpstemplates)|指定所需 DNS-over-HTTPS 解析程序的 URI 模板|
|[DownloadDirectory](#downloaddirectory)|设置下载目录|
|[DownloadRestrictions](#downloadrestrictions)|允许下载限制|
|[EdgeCollectionsEnabled](#edgecollectionsenabled)|启用“集锦”功能|
|[EdgeShoppingAssistantEnabled](#edgeshoppingassistantenabled)|已启用在 Microsoft Edge 中购物的功能|
|[EditFavoritesEnabled](#editfavoritesenabled)|允许用户编辑收藏夹|
|[EnableDeprecatedWebPlatformFeatures](#enabledeprecatedwebplatformfeatures)|Re-enable deprecated web platform features for a limited time (obsolete)|
|[EnableDomainActionsDownload](#enabledomainactionsdownload)|启用 Microsoft 中的域操作下载（已过时）|
|[EnableOnlineRevocationChecks](#enableonlinerevocationchecks)|启用联机 OCSP/CRL 检查|
|[EnableSha1ForLocalAnchors](#enablesha1forlocalanchors)|当本地信任密钥发布证书时，允许使用 SHA-1 对证书进行签名（已弃用）|
|[EnterpriseHardwarePlatformAPIEnabled](#enterprisehardwareplatformapienabled)|允许托管扩展使用企业硬件平台 API|
|[EnterpriseModeSiteListManagerAllowed](#enterprisemodesitelistmanagerallowed)|允许访问 Enterprise Mode Site List Manager 工具|
|[ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](#exemptdomainfiletypepairsfromfiletypedownloadwarnings)|为域上指定的文件类型禁用基于下载文件类型扩展的警告|
|[ExperimentationAndConfigurationServiceControl](#experimentationandconfigurationservicecontrol)|控制与试验和配置服务的通信|
|[ExternalProtocolDialogShowAlwaysOpenCheckbox](#externalprotocoldialogshowalwaysopencheckbox)|在外部协议对话框中显示“始终打开”复选框|
|[FamilySafetySettingsEnabled](#familysafetysettingsenabled)|允许用户配置家庭安全|
|[FavoritesBarEnabled](#favoritesbarenabled)|启用收藏夹栏|
|[ForceBingSafeSearch](#forcebingsafesearch)|强制实施必应安全搜索|
|[ForceCertificatePromptsOnMultipleMatches](#forcecertificatepromptsonmultiplematches)|配置当配置了“AutoSelectCertificateForUrls”的网站有多个证书匹配项时，Microsoft Edge 是否应自动选择证书|
|[ForceEphemeralProfiles](#forceephemeralprofiles)|启用临时配置文件的使用|
|[ForceGoogleSafeSearch](#forcegooglesafesearch)|强制实施 Google 安全搜索|
|[ForceLegacyDefaultReferrerPolicy](#forcelegacydefaultreferrerpolicy)|使用 no-referrer-when-downgrade 的默认引用者策略。（已弃用）|
|[ForceNetworkInProcess](#forcenetworkinprocess)|强制网络代码在浏览器进程中运行（已过时）|
|[ForceSync](#forcesync)|强制同步浏览器数据，但不显示同步许可提示|
|[ForceYouTubeRestrict](#forceyoutuberestrict)|强制最低 YouTube 受限模式|
|[FullscreenAllowed](#fullscreenallowed)|允许全屏模式|
|[GloballyScopeHTTPAuthCacheEnabled](#globallyscopehttpauthcacheenabled)|启用全局范围的 HTTP 身份验证缓存|
|[GoToIntranetSiteForSingleWordEntryInAddressBar](#gotointranetsiteforsinglewordentryinaddressbar)|强制直接 Intranet 站点导航，而不是在地址栏中搜索单个词条|
|[HSTSPolicyBypassList](#hstspolicybypasslist)|配置将跳过 HSTS 策略检查的名称列表|
|[HardwareAccelerationModeEnabled](#hardwareaccelerationmodeenabled)|使用硬件加速（如果可用）|
|[HideFirstRunExperience](#hidefirstrunexperience)|隐藏首次运行体验和初始屏幕|
|[HideInternetExplorerRedirectUXForIncompatibleSitesEnabled](#hideinternetexplorerredirectuxforincompatiblesitesenabled)|隐藏一次性重定向对话框和 Microsoft Edge 上的横幅|
|[ImportAutofillFormData](#importautofillformdata)|允许导入自动填充表单数据|
|[ImportBrowserSettings](#importbrowsersettings)|允许导入浏览器设置|
|[ImportCookies](#importcookies)|允许导入 Cookie|
|[ImportExtensions](#importextensions)|允许导入扩展|
|[ImportFavorites](#importfavorites)|允许导入收藏夹|
|[ImportHistory](#importhistory)|允许导入浏览历史记录|
|[ImportHomepage](#importhomepage)|允许导入主页设置|
|[ImportOpenTabs](#importopentabs)|允许导入打开的选项卡|
|[ImportPaymentInfo](#importpaymentinfo)|允许导入付款信息|
|[ImportSavedPasswords](#importsavedpasswords)|允许导入保存的密码|
|[ImportSearchEngine](#importsearchengine)|允许导入搜索引擎设置|
|[ImportShortcuts](#importshortcuts)|允许导入快捷方式|
|[InPrivateModeAvailability](#inprivatemodeavailability)|配置 InPrivate 模式可用性|
|[InsecureFormsWarningsEnabled](#insecureformswarningsenabled)|启用不安全窗体的警告|
|[IntensiveWakeUpThrottlingEnabled](#intensivewakeupthrottlingenabled)|控制 IntensiveWakeUpThrottling 的功能|
|[InternetExplorerIntegrationEnhancedHangDetection](#internetexplorerintegrationenhancedhangdetection)|为 Internet Explorer 模式配置增强的挂起检测|
|[InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel)|配置 Internet Explorer 集成|
|[InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist)|配置企业模式站点列表|
|[InternetExplorerIntegrationSiteRedirect](#internetexplorerintegrationsiteredirect)|指定从 Internet Explorer 模式页面启动时未配置网站的“页内”导航行为|
|[InternetExplorerIntegrationTestingAllowed](#internetexplorerintegrationtestingallowed)|允许 Internet Explorer 模式测试|
|[IsolateOrigins](#isolateorigins)|针对特定源启用网站隔离|
|[LocalProvidersEnabled](#localprovidersenabled)|允许来自本地提供程序的建议|
|[ManagedFavorites](#managedfavorites)|配置收藏夹|
|[ManagedSearchEngines](#managedsearchengines)|管理搜索引擎|
|[MaxConnectionsPerProxy](#maxconnectionsperproxy)|代理服务器的最大并发连接数|
|[MediaRouterCastAllowAllIPs](#mediaroutercastallowallips)|允许 Google Cast 连接到所有 IP 地址上的 Cast 设备|
|[MetricsReportingEnabled](#metricsreportingenabled)|启用使用情况和故障相关数据报告（已弃用）|
|[NativeWindowOcclusionEnabled](#nativewindowocclusionenabled)|启用本机窗口封闭|
|[NavigationDelayForInitialSiteListDownloadTimeout](#navigationdelayforinitialsitelistdownloadtimeout)|为企业模式站点列表设置延迟选项卡导航延迟的超时|
|[NetworkPredictionOptions](#networkpredictionoptions)|启用网络预测|
|[NonRemovableProfileEnabled](#nonremovableprofileenabled)|配置用户是否始终具有使用其工作或学校帐户自动登录的默认配置文件|
|[OverrideSecurityRestrictionsOnInsecureOrigin](#overridesecurityrestrictionsoninsecureorigin)|控制对不安全源应用安全限制的位置|
|[PaymentMethodQueryEnabled](#paymentmethodqueryenabled)|允许网站查询可用的付款方式|
|[PersonalizationReportingEnabled](#personalizationreportingenabled)|通过向 Microsoft 发送浏览历史记录，允许对广告、搜索和新闻进行个性化设置|
|[PinningWizardAllowed](#pinningwizardallowed)|允许固定到任务栏向导|
|[ProactiveAuthEnabled](#proactiveauthenabled)|启用主动身份验证|
|[PromotionalTabsEnabled](#promotionaltabsenabled)|启用完整选项卡促销内容|
|[PromptForDownloadLocation](#promptfordownloadlocation)|询问在何处保存下载的文件|
|[QuicAllowed](#quicallowed)|允许 QUIC 协议|
|[RedirectSitesFromInternetExplorerPreventBHOInstall](#redirectsitesfrominternetexplorerpreventbhoinstall)|阻止安装可将不兼容的网站从 Internet Explorer 重定向到 Microsoft Edge 的 BHO|
|[RedirectSitesFromInternetExplorerRedirectMode](#redirectsitesfrominternetexplorerredirectmode)|将不兼容的网站从 Internet Explorer 重新定向到 Microsoft Edge|
|[RelaunchNotification](#relaunchnotification)|通知用户对于挂起的更新，推荐或需要重新启动浏览器|
|[RelaunchNotificationPeriod](#relaunchnotificationperiod)|设置更新通知的时间段|
|[RendererCodeIntegrityEnabled](#renderercodeintegrityenabled)|启用呈现器代码完整性|
|[RequireOnlineRevocationChecksForLocalAnchors](#requireonlinerevocationchecksforlocalanchors)|指定本地信任密钥是否需要联机 OCSP/CRL 检查|
|[ResolveNavigationErrorsUseWebService](#resolvenavigationerrorsusewebservice)|启用使用 Web 服务解决导航错误|
|[RestrictSigninToPattern](#restrictsignintopattern)|限制哪些帐户可用作 Microsoft Edge 主要帐户|
|[RoamingProfileLocation](#roamingprofilelocation)|设置漫游配置文件目录|
|[RoamingProfileSupportEnabled](#roamingprofilesupportenabled)|启用 Microsoft Edge 配置文件数据的漫游副本|
|[RunAllFlashInAllowMode](#runallflashinallowmode)|将 Adobe Flash 内容设置扩展到所有内容|
|[SSLErrorOverrideAllowed](#sslerroroverrideallowed)|允许用户从 HTTPS 警告页面继续操作|
|[SSLVersionMin](#sslversionmin)|已启用最低 TLS 版本|
|[SaveCookiesOnExit](#savecookiesonexit)|Microsoft Edge 关闭时保存 cookie|
|[SavingBrowserHistoryDisabled](#savingbrowserhistorydisabled)|禁止保存浏览器历史记录|
|[ScreenCaptureAllowed](#screencaptureallowed)|允许或拒绝屏幕捕获|
|[ScrollToTextFragmentEnabled](#scrolltotextfragmentenabled)|允许滚动到 URL 片段中指定的文本|
|[SearchSuggestEnabled](#searchsuggestenabled)|启用搜索建议|
|[SecurityKeyPermitAttestation](#securitykeypermitattestation)|无需相应权限即可使用直接安全密钥证明的网站或域|
|[SendIntranetToInternetExplorer](#sendintranettointernetexplorer)|将所有 Intranet 站点都发送到 Internet Explorer|
|[SendSiteInfoToImproveServices](#sendsiteinfotoimproveservices)|发送站点信息以改进 Microsoft 服务（已弃用）|
|[SensorsAllowedForUrls](#sensorsallowedforurls)|允许访问特定网站上的传感器|
|[SensorsBlockedForUrls](#sensorsblockedforurls)|阻止访问特定网站上的传感器|
|[SerialAskForUrls](#serialaskforurls)|在特定网站上允许串行 API|
|[SerialBlockedForUrls](#serialblockedforurls)|在特定网站上阻止串行 API|
|[ShowOfficeShortcutInFavoritesBar](#showofficeshortcutinfavoritesbar)|在收藏夹栏中显示 Microsoft Office 快捷方式（已弃用）|
|[SignedHTTPExchangeEnabled](#signedhttpexchangeenabled)|启用签名的 HTTP Exchange (SXG) 支持|
|[SitePerProcess](#siteperprocess)|对每个网站启用网站隔离|
|[SpeechRecognitionEnabled](#speechrecognitionenabled)|Configure Speech Recognition|
|[SpellcheckEnabled](#spellcheckenabled)|启用拼写检查|
|[SpellcheckLanguage](#spellchecklanguage)|启用特定拼写检查语言|
|[SpellcheckLanguageBlocklist](#spellchecklanguageblocklist)|强制禁用拼写检查语言|
|[StricterMixedContentTreatmentEnabled](#strictermixedcontenttreatmentenabled)|对混合内容启用更严格的处理（已弃用）|
|[SuppressUnsupportedOSWarning](#suppressunsupportedoswarning)|禁止对不支持的操作系统显示警告|
|[SyncDisabled](#syncdisabled)|禁止使用 Microsoft 同步服务进行数据同步|
|[SyncTypesListDisabled](#synctypeslistdisabled)|配置从同步中排除的类型列表|
|[TLS13HardeningForLocalAnchorsEnabled](#tls13hardeningforlocalanchorsenabled)|为本地信任密钥启用 TLS 1.3 安全功能（已过时）|
|[TLSCipherSuiteDenyList](#tlsciphersuitedenylist)|指定要禁用的 TLS 密码套件|
|[TabFreezingEnabled](#tabfreezingenabled)|允许冻结后台选项卡|
|[TaskManagerEndProcessEnabled](#taskmanagerendprocessenabled)|允许在浏览器任务管理器中结束进程|
|[TotalMemoryLimitMb](#totalmemorylimitmb)|设置单个 Microsoft Edge 实例可以使用的内存兆字节限制|
|[TrackingPrevention](#trackingprevention)|阻止跟踪用户的 Web 浏览活动|
|[TranslateEnabled](#translateenabled)|启用翻译|
|[URLAllowlist](#urlallowlist)|定义允许的 URL 列表|
|[URLBlocklist](#urlblocklist)|阻止对 URL 列表的访问|
|[UserAgentClientHintsEnabled](#useragentclienthintsenabled)|启用“User-Agent 客户端提示”功能（已弃用）|
|[UserDataDir](#userdatadir)|设置用户数据目录|
|[UserDataSnapshotRetentionLimit](#userdatasnapshotretentionlimit)|限制保留用于紧急回退的用户数据快照数量|
|[UserFeedbackAllowed](#userfeedbackallowed)|允许用户反馈|
|[VideoCaptureAllowed](#videocaptureallowed)|允许或阻止视频捕获|
|[VideoCaptureAllowedUrls](#videocaptureallowedurls)|无需请求许可即可访问视频捕获设备的网站|
|[WPADQuickCheckEnabled](#wpadquickcheckenabled)|设置 WPAD 优化|
|[WebAppInstallForceList](#webappinstallforcelist)|配置强制安装的 Web 应用列表|
|[WebCaptureEnabled](#webcaptureenabled)|在 Microsoft Edge 中启用网络捕获功能|
|[WebComponentsV0Enabled](#webcomponentsv0enabled)|重新启用 Web Components v0 API 直至 M84（已过时）|
|[WebDriverOverridesIncompatiblePolicies](#webdriveroverridesincompatiblepolicies)|允许 WebDriver 替代不兼容的策略（已弃用）|
|[WebRtcLocalIpsAllowedUrls](#webrtclocalipsallowedurls)|管理通过 WebRTC 暴露本地 IP 地址|
|[WebRtcLocalhostIpHandling](#webrtclocalhostiphandling)|限制通过 WebRTC 暴露本地 IP 地址|
|[WebRtcUdpPortRange](#webrtcudpportrange)|限制 WebRTC 使用的本地 UDP 端口的范围|
|[WebWidgetAllowed](#webwidgetallowed)|启用 Web 构件|
|[WebWidgetIsEnabledOnStartup](#webwidgetisenabledonstartup)|在 Windows 启动时允许Web构件|
|[WinHttpProxyResolverEnabled](#winhttpproxyresolverenabled)|使用 Windows 代理解析程序（已弃用）|




  ## 应用程序防护设置策略

  [返回页首](#microsoft-edge---policies)

  ### ApplicationGuardContainerProxy

  #### 应用程序防护容器代理

  
  
  #### 支持的版本：

  - 在 84 版或更高版本的 Windows 上

  #### 描述

  配置 Microsoft Edge 应用程序防护的代理设置。
如果启用此策略，Microsoft Edge 应用程序防护将忽略其他代理配置源。

如果未配置此策略，Microsoft Edge 应用程序防护将使用主机的代理配置。

此策略不会影响应用程序防护（在主机上）以外的 Microsoft Edge 代理配置。

使用 ProxyMode 字段，可指定 Microsoft Edge 应用程序防护使用的代理服务器。

ProxyPacUrl 字段是指向代理 .pac 文件的 URL。

ProxyServer 字段是代理服务器的 URL。

如果将direct”值选择为“ProxyMode”，则所有其他字段都将被忽略。

如果将“auto_detect”值选择为“ProxyMode”，则所有其他字段都将被忽略。

如果将“fixed_servers”值选择为“ProxyMode”，则使用“ProxyServer”字段。

如果将“pac_script”值选择为“ProxyMode”，则使用“ProxyPacUrl”字段。

有关通过双代理识别应用程序防护流量的详细信息，请访问 [https://go.microsoft.com/fwlink/?linkid=2134653](https://go.microsoft.com/fwlink/?linkid=2134653)。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - Dictionary

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ApplicationGuardContainerProxy
  - GP 名称：应用程序防护容器代理
  - GP 路径（强制）：管理模板/Microsoft Edge/应用程序防护设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ApplicationGuardContainerProxy
  - 值类型：REG_SZ

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\ApplicationGuardContainerProxy = {
  "ProxyMode": "direct", 
  "ProxyPacUrl": "https://internal.site/example.pac", 
  "ProxyServer": "123.123.123.123:8080"
}
```

  ##### 精简示例值：

  ```
  SOFTWARE\Policies\Microsoft\Edge\ApplicationGuardContainerProxy = {"ProxyMode": "direct", "ProxyPacUrl": "https://internal.site/example.pac", "ProxyServer": "123.123.123.123:8080"}
  ```
  

  

  [返回页首](#microsoft-edge---policies)

  ## Cast 策略

  [返回页首](#microsoft-edge---policies)

  ### EnableMediaRouter

  #### 启用 Google Cast

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  启用此策略以启用 Google Cast。 用户将能够从应用菜单、页面上下文菜单、启用了 Cast 的网站上的媒体控件以及 Cast 工具栏图标（如果显示）中启动它。

禁用此策略以禁用 Google Cast。

默认情况下，将启用 Google Cast。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：EnableMediaRouter
  - GP 名称：启用 Google Cast
  - GP 路径（强制）：管理模板/Microsoft Edge/Cast
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：EnableMediaRouter
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：EnableMediaRouter
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ShowCastIconInToolbar

  #### 在工具栏中显示 Cast 图标

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  将此策略设置为 true，以在工具栏或溢出菜单上显示 Cast 工具栏图标。 用户无法将其删除。

如果未配置此策略或将其禁用，则用户可以使用其上下文菜单固定或删除图标。

如果还将 [EnableMediaRouter](#enablemediarouter) 策略设置为 false，则此策略将被忽略，并且不会显示工具栏图标。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ShowCastIconInToolbar
  - GP 名称：在工具栏中显示 Cast 图标
  - GP 路径（强制）：管理模板/Microsoft Edge/Cast
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ShowCastIconInToolbar
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：ShowCastIconInToolbar
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ## 内容设置策略

  [返回页首](#microsoft-edge---policies)

  ### AutoSelectCertificateForUrls

  #### 自动为这些网站选择客户端证书

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  通过设置策略，您可以生成一个 URL 模式列表，这些模式指定 Microsoft Edge 可以为其自动选择客户端证书的站点。 该值是一个字符串化的 JSON 字典数组，每个字典的格式为 { "pattern": "$URL_PATTERN", "filter" : $FILTER }，其中 $URL_PATTERN 是内容设置模式。 $FILTER 限制浏览器自动从中选择的客户端证书。 独立于筛选器，仅选择与服务器证书请求匹配的证书。

"$FILTER" 部分的用法示例：

* 当 $FILTER 设置为 { "ISSUER": { "CN": "$ISSUER_CN" } } 时，只选择由 CommonName 为 $ISSUER\u CN 的证书颁发的客户端证书。

* 当 $FILTER 同时包含“证书颁发者”和“使用者”部分时，只选择满足这两个条件的客户端证书。

* 当 $FILTER 包含具有 “O” 值的“使用者”部分时，证书至少需要一个与指定值匹配的组织才能被选择。

* 当 $FILTER 包含具有 “OU” 值的“使用者”部分时，证书至少需要一个与指定值匹配的组织单位才能选择。

* 当 $FILTER 设置为 {} 时，客户端证书的选择不受额外限制。 请注意，web 服务器提供的过滤器仍然适用。

如果不设置策略，任何站点都不会自动选择。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AutoSelectCertificateForUrls
  - GP 名称：自动为这些网站选择客户端证书
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\AutoSelectCertificateForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\AutoSelectCertificateForUrls\1 = "{\"pattern\":\"https://www.contoso.com\",\"filter\":{\"ISSUER\":{\"CN\":\"certificate issuer name\", \"L\": \"certificate issuer location\", \"O\": \"certificate issuer org\", \"OU\": \"certificate issuer org unit\"}, \"SUBJECT\":{\"CN\":\"certificate subject name\", \"L\": \"certificate subject location\", \"O\": \"certificate subject org\", \"OU\": \"certificate subject org unit\"}}}"

```

  #### Mac 信息和设置
  
  - 首选项项名称：AutoSelectCertificateForUrls
  - 示例值：
``` xml
<array>
  <string>{"pattern":"https://www.contoso.com","filter":{"ISSUER":{"CN":"certificate issuer name", "L": "certificate issuer location", "O": "certificate issuer org", "OU": "certificate issuer org unit"}, "SUBJECT":{"CN":"certificate subject name", "L": "certificate subject location", "O": "certificate subject org", "OU": "certificate subject org unit"}}}</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### CookiesAllowedForUrls

  #### 在特定网站上允许 cookie

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  根据 URL 模式定义允许设置 Cookie 的网站列表。

如果未配置此策略，则所有网站都将使用 [DefaultCookiesSetting](#defaultcookiessetting) 策略中的全局默认值（如果已设置）或用户的个人配置。

有关详细信息，请参阅 [CookiesBlockedForUrls](#cookiesblockedforurls) 和 [CookiesSessionOnlyForUrls](#cookiessessiononlyforurls) 策略。

请注意，这三个策略设置的 URL 模式不能冲突：

- [CookiesBlockedForUrls](#cookiesblockedforurls)

- CookiesAllowedForUrls

- [CookiesSessionOnlyForUrls](#cookiessessiononlyforurls)

若要排除退出时删除 Cookie 的功能，请配置 [SaveCookiesOnExit](#savecookiesonexit) 策略。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：CookiesAllowedForUrls
  - GP 名称：在特定网站上允许 Cookie
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\CookiesAllowedForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\CookiesAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\CookiesAllowedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：CookiesAllowedForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### CookiesBlockedForUrls

  #### 在特定站点上阻止 Cookie

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  根据 URL 模式定义不能设置 Cookie 的网站列表。

如果未配置此策略，则所有网站都将使用 [DefaultCookiesSetting](#defaultcookiessetting) 策略中的全局默认值（如果已设置）或用户的个人配置。

有关详细信息，请参阅 [CookiesAllowedForUrls](#cookiesallowedforurls) 和 [CookiesSessionOnlyForUrls](#cookiessessiononlyforurls) 策略。

请注意，这三个策略设置的 URL 模式不能冲突：

- CookiesBlockedForUrls

- [CookiesAllowedForUrls](#cookiesallowedforurls)

- [CookiesSessionOnlyForUrls](#cookiessessiononlyforurls)

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：CookiesBlockedForUrls
  - GP 名称：在特定站点上阻止 Cookie
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\CookiesBlockedForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\CookiesBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\CookiesBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：CookiesBlockedForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### CookiesSessionOnlyForUrls

  #### 将来自特定网站的 Cookie 限制为当前会话

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  当会话结束时（窗口关闭时），将删除由与你定义的 URL 模式匹配的网站创建的 Cookie。

由与模式不匹配的网站创建的 Cookie 受 [DefaultCookiesSetting](#defaultcookiessetting) 策略（如果已设置）或用户的个人配置控制。 如果未配置此策略，这也是默认行为。

如果 Microsoft Edge 正在后台模式下运行，则该会话可能不会在最后一个窗口关闭时关闭，这意味着关闭窗口时不会清除 Cookie。 有关配置 Microsoft Edge 在后台模式下运行时发生的情况的信息，请参阅 [BackgroundModeEnabled](#backgroundmodeenabled) 策略。

还可以使用 [CookiesAllowedForUrls](#cookiesallowedforurls) 和 [CookiesBlockedForUrls](#cookiesblockedforurls) 策略来控制哪些网站可以创建 Cookie。

请注意，这三个策略设置的 URL 模式不能冲突：

- [CookiesBlockedForUrls](#cookiesblockedforurls)

- [CookiesAllowedForUrls](#cookiesallowedforurls)

- CookiesSessionOnlyForUrls

如果将 [RestoreOnStartup](#restoreonstartup) 策略设置为从以前的会话还原 URL，则此策略会被忽略，并且将永久存储这些网站的 Cookie。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：CookiesSessionOnlyForUrls
  - GP 名称：将来自特定网站的 Cookie 限制为当前会话
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\CookiesSessionOnlyForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\CookiesSessionOnlyForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\CookiesSessionOnlyForUrls\2 = "[*.]contoso.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：CookiesSessionOnlyForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultCookiesSetting

  #### 配置 Cookie

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  控制网站是否可以在用户的设备上创建 Cookie。 此策略为全有或全无 - 可以让所有网站创建 Cookie，或没有网站可创建 Cookie。 不能使用此策略来启用来自特定网站的 Cookie。

将策略设置为“SessionOnly”可在会话关闭时清除 Cookie。 如果 Microsoft Edge 正在后台模式下运行，则该会话可能不会在最后一个窗口关闭时关闭，这意味着关闭窗口时不会清除 Cookie。 有关配置 Microsoft Edge 在后台模式下运行时发生的情况的信息，请参阅 [BackgroundModeEnabled](#backgroundmodeenabled) 策略。

如果未配置此策略，则将使用默认的“AllowCookies”，用户可以在 Microsoft Edge “设置”中更改此设置。 （如果不希望用户能够更改此设置，请设置该策略。）

策略选项映射：

* AllowCookies (1) = 允许所有网站创建 Cookie

* BlockCookies (2) = 禁止任何网站创建 Cookie

* SessionOnly (4) = 在会话期间保留 Cookie，但 [SaveCookiesOnExit](#savecookiesonexit) 中列出的 Cookie除外

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultCookiesSetting
  - GP 名称：配置 Cookie
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DefaultCookiesSetting
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultCookiesSetting
  - 示例值：
``` xml
<integer>1</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultFileSystemReadGuardSetting

  #### 控制文件系统 API 在读取中的使用

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 86 或更高版本起

  #### 描述

  如果将此策略设置为 3，则网站可以使用文件系统 API 请求对主机操作系统的文件系统进行读取访问。 如果将此策略设置为 2，则会拒绝访问。

如果未设置此策略，网站可以请求访问。 用户可以更改此设置。

策略选项映射：

* BlockFileSystemRead (2) = 不允许任何网站通过文件系统 API 请求对文件和目录的读取权限

* AskFileSystemRead (3) = 允许网站通过文件系统 API 请求用户授予对文件和目录的读取权限

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultFileSystemReadGuardSetting
  - GP 名称：控制文件系统 API 在读取中的使用
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DefaultFileSystemReadGuardSetting
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000002
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultFileSystemReadGuardSetting
  - 示例值：
``` xml
<integer>2</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultFileSystemWriteGuardSetting

  #### 控制文件系统 API 在写入中的使用

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 86 或更高版本起

  #### 描述

  如果将此策略设置为 3，则网站可以使用文件系统 API 请求对主机操作系统的文件系统进行写入访问。 如果将此策略设置为 2，则会拒绝访问。

如果未设置此策略，网站可以请求访问。 用户可以更改此设置。

策略选项映射：

* BlockFileSystemWrite (2) = 不允许任何网站通过文件系统 API 请求对文件和目录的写入权限

* AskFileSystemWrite (3) = 允许网站请求用户授予对文件和目录的写入权限

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultFileSystemWriteGuardSetting
  - GP 名称：控制文件系统 API 在写入中的使用
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DefaultFileSystemWriteGuardSetting
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000002
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultFileSystemWriteGuardSetting
  - 示例值：
``` xml
<integer>2</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultGeolocationSetting

  #### 默认地理位置设置

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  设置网站是否可以跟踪用户的物理位置。 默认情况下，可允许跟踪（"AllowGeolocation"），默认情况下将其拒绝（"BlockGeolocation"），或在网站每次请求用户位置（"AskGeolocation"）时询问该用户。

如果未配置此策略，则会使用“AskGeolocation”策略，用户可以对其进行更改。

策略选项映射：

* AllowGeolocation (1) = 允许网站跟踪用户的物理位置

* BlockGeolocation (2) = 不允许任何网站跟踪用户的物理位置

* AskGeolocation (3) = 每当网站想要跟踪用户的物理位置时询问

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultGeolocationSetting
  - GP 名称：默认地理位置设置
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DefaultGeolocationSetting
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultGeolocationSetting
  - 示例值：
``` xml
<integer>1</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultImagesSetting

  #### 默认图像设置

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  设置网站是否可以显示图像。 可在所有网站上允许（"AllowImages"）或在所有网站上阻止这些图像（"BlockImages"）。

如果未配置此策略，则默认情况下允许图像，用户可以更改此设置。

策略选项映射：

* AllowImages (1) = 允许所有网站显示所有图像

* BlockImages (2) = 不允许任何网站显示图像

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultImagesSetting
  - GP 名称：默认图像设置
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DefaultImagesSetting
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultImagesSetting
  - 示例值：
``` xml
<integer>1</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultInsecureContentSetting

  #### 控制不安全内容异常的使用

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 80 或更高版本起

  #### 描述

  允许你设置用户是否可以添加例外来允许特定网站的混合内容。

对于特定 URL 模式，可使用 [InsecureContentAllowedForUrls](#insecurecontentallowedforurls) 和 [InsecureContentBlockedForUrls](#insecurecontentblockedforurls) 策略替代此策略。

如果未设置此策略，则允许用户添加例外，以便允许可阻止的混合内容，并禁用可选择性阻止的混合内容的自动升级。

策略选项映射：

* BlockInsecureContent (2) = 不允许任何网站加载混合内容

* AllowExceptionsInsecureContent (3) = 允许用户添加例外以允许混合内容

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultInsecureContentSetting
  - GP 名称：控制不安全内容异常的使用
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DefaultInsecureContentSetting
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000002
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultInsecureContentSetting
  - 示例值：
``` xml
<integer>2</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultJavaScriptSetting

  #### 默认 JavaScript 设置

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  设置网站是否可以运行 JavaScript。 可为所有网站允许 JavaScript （"AllowJavaScript"），或为所有网站阻止 JavaScript （"BlockJavaScript"）。

如果未配置此策略，则默认情况下，所有网站都可以运行 JavaScript，用户可以更改此设置。

策略选项映射：

* AllowJavaScript (1) = 允许所有网站运行 JavaScript

* BlockJavaScript (2) = 不允许任何网站运行 JavaScript

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultJavaScriptSetting
  - GP 名称：默认 JavaScript 设置
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DefaultJavaScriptSetting
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultJavaScriptSetting
  - 示例值：
``` xml
<integer>1</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultNotificationsSetting

  #### 默认通知设置

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  设置网站是否可以显示桌面通知。 默认情况下，可以允许他们（"AllowNotifications"），默认情况下将其拒绝（"BlockNotifications"），或者每次网站想要显示通知时，都会询问用户（"AskNotifications"）。

如果未配置此策略，则默认情况下允许通知，用户可以更改此设置。

策略选项映射：

* AllowNotifications (1) = 允许网站显示桌面通知

* BlockNotifications (2) = 不允许任何网站显示桌面通知

* AskNotifications (3) = 每次网站想要显示桌面通知时询问

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultNotificationsSetting
  - GP 名称：默认通知设置
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DefaultNotificationsSetting
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000002
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultNotificationsSetting
  - 示例值：
``` xml
<integer>2</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultPluginsSetting

  #### 默认 Adobe Flash 设置

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  先检查 [PluginsAllowedForUrls](#pluginsallowedforurls) 和 [PluginsBlockedForUrls](#pluginsblockedforurls)，然后再检查此策略。 选项为 "ClickToPlay" 和 "BlockPlugins"。 如果将此策略设置为 "BlockPlugins"，则所有网站均将拒绝该插件。 点击 "ClickToPlay" 可运行 Flash 插件，但用户需单击占位以启动。

如果未配置此策略，用户可以手动更改此设置。

注意：仅对 [PluginsAllowedForUrls](#pluginsallowedforurls) 策略中显式列出的域允许自动播放。 若要为所有网站打开"自动播放"，请将 http://* 和 https://* 添加到允许的 URL 列表中。

策略选项映射：

* BlockPlugins (2) = 阻止 Adobe Flash 插件

* ClickToPlay (3) = 单击播放

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultPluginsSetting
  - GP 名称：默认 Adobe Flash 设置
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DefaultPluginsSetting
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000002
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultPluginsSetting
  - 示例值：
``` xml
<integer>2</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultPopupsSetting

  #### 默认弹出窗口设置

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  设置网站是否可以显示弹出窗口。 可在所有网站上允许弹出窗口（"AllowPopups"），或在所有网站上阻止弹出窗口（"BlockPopups"）。

如果未配置此策略，则默认情况下将阻止弹出窗口，用户可以更改此设置。

策略选项映射：

* AllowPopups (1) = 允许所有网站显示弹出窗口

* BlockPopups (2) = 不允许任何网站显示弹出窗口

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultPopupsSetting
  - GP 名称：默认弹出窗口设置
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DefaultPopupsSetting
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultPopupsSetting
  - 示例值：
``` xml
<integer>1</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultWebBluetoothGuardSetting

  #### 控制 Web 蓝牙 API 的使用

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  控制网站是否可以访问附近的蓝牙设备。 可以完全阻止访问，也可以在网站每次想要访问蓝牙设备时询问用户。

如果未配置此策略，则使用默认值（'AskWebBluetooth'，意味着每次都询问用户），用户可以更改它。

策略选项映射：

* BlockWebBluetooth (2) = 不允许任何网站使用 Web 蓝牙 API 请求访问蓝牙设备

* AskWebBluetooth (3) = 允许网站请求用户授予对附近蓝牙设备的访问权限

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultWebBluetoothGuardSetting
  - GP 名称：控制 Web 蓝牙 API 的使用
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DefaultWebBluetoothGuardSetting
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000002
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultWebBluetoothGuardSetting
  - 示例值：
``` xml
<integer>2</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultWebUsbGuardSetting

  #### 控制 WebUSB API 的使用

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  设置网站是否可以访问已连接的 USB 设备。 可以完全阻止访问，也可以在网站每次想要访问连接的 USB 设备时询问用户。

对于特定 URL 模式，可以使用 [WebUsbAskForUrls](#webusbaskforurls) 和 [WebUsbLockedForUrls](#webusbblockedforurls) 策略来替代此策略。

如果未配置此策略，则默认情况下，网站可以询问用户是否能访问连接的 USB 设备 ('AskWebUsb')，用户可以更改此设置。

策略选项映射：

* BlockWebUsb (2) = 不允许任何网站通过 WebUSB API 请求访问 USB 设备

* AskWebUsb (3) = 允许网站请求用户授予对连接的 USB 设备的访问权限

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultWebUsbGuardSetting
  - GP 名称：控制 WebUSB API 的使用
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DefaultWebUsbGuardSetting
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000002
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultWebUsbGuardSetting
  - 示例值：
``` xml
<integer>2</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### FileSystemReadAskForUrls

  #### 允许在这些网站上通过文件系统 API 进行读取访问

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 86 或更高版本起

  #### 描述

  通过设置策略，你可以列出一些 URL 模式，指定哪些网站可以通过文件系统 API 请求用户向他们授予对主机操作系统文件系统中的文件或目录的访问权限。

不设置该策略意味着对所有网站应用 [DefaultFileSystemReadGuardSetting](#defaultfilesystemreadguardsetting)（如果已设置）。 如果未设置该策略，则应用用户的个人设置。

URL 模式不得与 [FileSystemReadBlockedForUrls](#filesystemreadblockedforurls) 冲突。 如果 URL 与两个策略都匹配，则这两个策略均不具有优先权。

有关有效 URL 模式的详细信息，请参阅 https://cloud.google.com/docs/chrome-enterprise/policies/url-patterns。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：FileSystemReadAskForUrls
  - GP 名称：允许在这些网站上通过文件系统 API 进行读取访问
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\FileSystemReadAskForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\FileSystemReadAskForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\FileSystemReadAskForUrls\2 = "[*.]example.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：FileSystemReadAskForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### FileSystemReadBlockedForUrls

  #### 阻止在这些网站上通过文件系统 API 进行读取访问

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 86 或更高版本起

  #### 描述

  如果设置了此策略，则可以列出一些 URL 模式，指定哪些网站无法通过文件系统 API 请求用户向他们授予对主机操作系统文件系统中的文件或目录的访问权限。

如果未设置此策略，则会对所有网站应用 [DefaultFileSystemReadGuardSetting](#defaultfilesystemreadguardsetting)（如果已设置）。 如果未设置该策略，则应用用户的个人设置。

URL 模式不得与 [FileSystemReadAskForUrls](#filesystemreadaskforurls) 冲突。 如果 URL 与两个策略都匹配，则这两个策略均不具有优先权。

有关有效 URL 模式的详细信息，请参阅 https://cloud.google.com/docs/chrome-enterprise/policies/url-patterns。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：FileSystemReadBlockedForUrls
  - GP 名称：阻止在这些网站上通过文件系统 API 进行读取访问
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\FileSystemReadBlockedForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\FileSystemReadBlockedForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\FileSystemReadBlockedForUrls\2 = "[*.]example.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：FileSystemReadBlockedForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### FileSystemWriteAskForUrls

  #### 允许在这些网站上对文件和目录进行写入访问

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 86 或更高版本起

  #### 描述

  如果设置了此策略，则可以列出一些 URL 模式，指定哪些网站可以请求用户向他们授予对主机操作系统文件系统中的文件或目录的写入权限。

如果未设置此策略，则会对所有网站应用 [DefaultFileSystemWriteGuardSetting](#defaultfilesystemwriteguardsetting)（如果已设置）。 如果未设置该策略，则应用用户的个人设置。

URL 模式不得与 [FileSystemWriteBlockedForUrls](#filesystemwriteblockedforurls) 冲突。 如果 URL 与两个策略都匹配，则这两个策略均不具有优先权。

有关有效 URL 模式的详细信息，请参阅 https://cloud.google.com/docs/chrome-enterprise/policies/url-patterns。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：FileSystemWriteAskForUrls
  - GP 名称：允许在这些网站上对文件和目录进行写入访问
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteAskForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteAskForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteAskForUrls\2 = "[*.]example.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：FileSystemWriteAskForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### FileSystemWriteBlockedForUrls

  #### 阻止在这些网站上对文件和目录进行写入访问

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 86 或更高版本起

  #### 描述

  如果设置了此策略，则可以列出一些 URL 模式，指定哪些网站无法请求用户向他们授予对主机操作系统文件系统中的文件或目录的写入权限。

如果未设置此策略，则会对所有网站应用 [DefaultFileSystemWriteGuardSetting](#defaultfilesystemwriteguardsetting)（如果已设置）。 如果未设置该策略，则应用用户的个人设置。

URL 模式不得与 [FileSystemWriteAskForUrls](#filesystemwriteaskforurls) 冲突。 如果 URL 与两个策略都匹配，则这两个策略均不具有优先权。

有关有效 URL 模式的详细信息，请参阅 https://cloud.google.com/docs/chrome-enterprise/policies/url-patterns。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：FileSystemWriteBlockedForUrls
  - GP 名称：阻止在这些网站上对文件和目录进行写入访问
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteBlockedForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteBlockedForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\FileSystemWriteBlockedForUrls\2 = "[*.]example.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：FileSystemWriteBlockedForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ImagesAllowedForUrls

  #### 在这些网站上允许图像

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  根据 URL 模式定义可显示图像的网站列表。

如果未配置此策略，则所有网站都将使用 [DefaultImagesSetting](#defaultimagessetting) 策略中的全局默认值（如果已设置）或用户的个人配置。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ImagesAllowedForUrls
  - GP 名称：在这些网站上允许图像
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\ImagesAllowedForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\ImagesAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\ImagesAllowedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：ImagesAllowedForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ImagesBlockedForUrls

  #### 在这些网站上阻止图像

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  根据 URL 模式定义不允许显示图像的网站列表。

如果未配置此策略，则所有网站都将使用 [DefaultImagesSetting](#defaultimagessetting) 策略中的全局默认值（如果已设置）或用户的个人配置。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ImagesBlockedForUrls
  - GP 名称：在这些网站上阻止图像
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\ImagesBlockedForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\ImagesBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\ImagesBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：ImagesBlockedForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### InsecureContentAllowedForUrls

  #### 在指定网站上允许不安全内容

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 80 或更高版本起

  #### 描述

  创建 URL 模式列表，以指定可显示不安全混合内容（即 HTTPS 网站上的 HTTP 内容）的网站。

如果未配置此策略，则可阻止的混合内容将被阻止，并且可选择阻止的混合内容将被升级。 但是，将允许用户设置例外，以允许特定网站使用不安全的混合内容。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：InsecureContentAllowedForUrls
  - GP 名称：在指定网站上允许不安全内容
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\InsecureContentAllowedForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\InsecureContentAllowedForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\InsecureContentAllowedForUrls\2 = "[*.]example.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：InsecureContentAllowedForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### InsecureContentBlockedForUrls

  #### 在指定网站上阻止不安全内容

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 80 或更高版本起

  #### 描述

  创建 URL 模式列表，以指定不允许显示可阻止（即活动）混合内容（即 HTTPS 网站上的 HTTP 内容）的网站，以及将禁用可选择阻止的混合内容升级的网站。

如果未配置此策略，则可阻止的混合内容将被阻止，并且可选择阻止的混合内容将被升级。 但是，将允许用户设置例外，以允许特定网站使用不安全的混合内容。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：InsecureContentBlockedForUrls
  - GP 名称：在指定网站上阻止不安全内容
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\InsecureContentBlockedForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\InsecureContentBlockedForUrls\1 = "https://www.example.com"
SOFTWARE\Policies\Microsoft\Edge\InsecureContentBlockedForUrls\2 = "[*.]example.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：InsecureContentBlockedForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### JavaScriptAllowedForUrls

  #### 在特定网站上允许 JavaScript

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  根据 URL 模式定义允许运行 JavaScript 的网站列表。

如果未配置此策略，则所有网站都将使用 [DefaultJavaScriptSetting](#defaultjavascriptsetting) 策略中的全局默认值（如果已设置）或用户的个人配置。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：JavaScriptAllowedForUrls
  - GP 名称：在特定网站上允许 JavaScript
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\JavaScriptAllowedForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\JavaScriptAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\JavaScriptAllowedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：JavaScriptAllowedForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### JavaScriptBlockedForUrls

  #### 在特定网站上阻止 JavaScript

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  根据 URL 模式定义不允许运行 JavaScript 的网站列表。

如果未配置此策略，则所有网站都将使用 [DefaultJavaScriptSetting](#defaultjavascriptsetting) 策略中的全局默认值（如果已设置）或用户的个人配置。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：JavaScriptBlockedForUrls
  - GP 名称：在特定网站上阻止 JavaScript
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\JavaScriptBlockedForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\JavaScriptBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\JavaScriptBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：JavaScriptBlockedForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### LegacySameSiteCookieBehaviorEnabled

  #### 启用默认旧 SameSite Cookie 行为设置

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 80 或更高版本起

  #### 描述

  允许你将所有 Cookie 恢复为旧的 SameSite 行为。 还原为旧行为会导致未指定 SameSite 属性的 Cookie 被视为 “SameSite=None”，删除了 “SameSite=None” Cookie 携带 “Secure” 属性的要求，并在评估两个站点是否为同一站点时跳过方案比较。

如果不设置此策略，Cookie 的 SameSite 行为将取决于 SameSite-by-default 功能、Cookies-without-SameSite-must-be-secure 功能、和 Schemeful Same-Site 功能的其他资源。 These features can also be configured by a field trial or the same-site-by-default-cookies flag, the cookies-without-same-site-must-be-secure flag, or the schemeful-same-site flag in edge://flags.

策略选项映射：

* DefaultToLegacySameSiteCookieBehavior (1) = 恢复所有网站上 Cookie 的 SameSite 行为

* DefaultToSameSiteByDefaultCookieBehavior (2) = 对所有网站上的 cookie 使用 SameSite-by-default 行为

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：LegacySameSiteCookieBehaviorEnabled
  - GP 名称：启用默认旧 SameSite Cookie 行为设置
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：LegacySameSiteCookieBehaviorEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：LegacySameSiteCookieBehaviorEnabled
  - 示例值：
``` xml
<integer>1</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### LegacySameSiteCookieBehaviorEnabledForDomainList

  #### 在指定网站上还原为 Cookie 的旧 SameSite 行为

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 80 或更高版本起

  #### 描述

  为域设置的 Cookie 与指定的模式匹配时，将还原为旧 SameSite 行为。

还原为旧行为会导致未指定 SameSite 属性的 Cookie 被视为 “SameSite=None”，删除了 “SameSite=None” Cookie 携带 “Secure” 属性的要求，并在评估两个站点是否为同一站点时跳过方案比较。

如果未设置此策略，则将使用全局默认值。 全局默认值也将用于你指定的模式未涵盖的域上的 Cookie。

全局默认值可以使用 [LegacySameSiteCookieBehaviorEnabled](#legacysamesitecookiebehaviorenabled) 策略进行配置。 如果未设置 [LegacySameSiteCookieBehaviorEnabled](#legacysamesitecookiebehaviorenabled)，则全局默认值将回退到其他配置源。

请注意，此策略中列出的模式将被视为域而不是 URL，因此不应指定方案或端口。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：LegacySameSiteCookieBehaviorEnabledForDomainList
  - GP 名称：在指定网站上还原为 Cookie 的旧 SameSite 行为
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\LegacySameSiteCookieBehaviorEnabledForDomainList
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\LegacySameSiteCookieBehaviorEnabledForDomainList\1 = "www.example.com"
SOFTWARE\Policies\Microsoft\Edge\LegacySameSiteCookieBehaviorEnabledForDomainList\2 = "[*.]example.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：LegacySameSiteCookieBehaviorEnabledForDomainList
  - 示例值：
``` xml
<array>
  <string>www.example.com</string>
  <string>[*.]example.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### NotificationsAllowedForUrls

  #### 在特定网站上允许通知

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  可用于创建 url 模式列表，以指定允许显示通知的网站。

如果未设置此策略，则将对所有网站使用全局默认值。 此默认值将来自 [DefaultNotificationsSetting](#defaultnotificationssetting) 策略（如果已设置）或用户的个人配置。 有关有效 url 模式的详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：NotificationsAllowedForUrls
  - GP 名称：在特定网站上允许通知
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\NotificationsAllowedForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\NotificationsAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\NotificationsAllowedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：NotificationsAllowedForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### NotificationsBlockedForUrls

  #### 在特定网站上阻止通知

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  可用于创建 url 模式列表，以指定不允许显示通知的网站。

如果未设置此策略，则将对所有网站使用全局默认值。 此默认值将来自 [DefaultNotificationsSetting](#defaultnotificationssetting) 策略（如果已设置）或用户的个人配置。 有关有效 url 模式的详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：NotificationsBlockedForUrls
  - GP 名称：在特定网站上阻止通知
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\NotificationsBlockedForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\NotificationsBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\NotificationsBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：NotificationsBlockedForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### PluginsAllowedForUrls

  #### 在特定网站上允许 Adobe Flash 插件

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  根据 URL 模式定义可运行 Adobe Flash 插件的网站列表。

如果未配置此策略，则所有网站都将使用 [DefaultPluginsSetting](#defaultpluginssetting) 策略中的全局默认值（如果已设置）或用户的个人配置。

有关有效 url 模式的详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)。 但是，从 M85 开始，该策略不再支持主机中带有 '*' 和 '[*.]' 通配符的模式。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：PluginsAllowedForUrls
  - GP 名称：在特定网站上允许 Adobe Flash 插件
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\PluginsAllowedForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\PluginsAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\PluginsAllowedForUrls\2 = "http://contoso.edu:8080"

```

  #### Mac 信息和设置
  
  - 首选项项名称：PluginsAllowedForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>http://contoso.edu:8080</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### PluginsBlockedForUrls

  #### 在特定网站上阻止 Adobe Flash 插件

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  根据 URL 模式定义阻止运行 Adobe Flash 的网站列表。

如果未配置此策略，则所有网站都将使用 [DefaultPluginsSetting](#defaultpluginssetting) 策略中的全局默认值（如果已设置）或用户的个人配置。

有关有效 url 模式的详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)。 但是，从 M85 开始，该策略不再支持主机中带有 '*' 和 '[*.]' 通配符的模式。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：PluginsBlockedForUrls
  - GP 名称：在特定网站上阻止 Adobe Flash 插件
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\PluginsBlockedForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\PluginsBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\PluginsBlockedForUrls\2 = "http://contoso.edu:8080"

```

  #### Mac 信息和设置
  
  - 首选项项名称：PluginsBlockedForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>http://contoso.edu:8080</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### PopupsAllowedForUrls

  #### 在特定网站上允许弹出窗口

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  根据 URL 模式定义可打开弹出窗口的网站列表。

如果未配置此策略，则所有网站都将使用 [DefaultPopupsSetting](#defaultpopupssetting) 策略中的全局默认值（如果已设置）或用户的个人配置。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：PopupsAllowedForUrls
  - GP 名称：在特定网站上允许弹出窗口
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\PopupsAllowedForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\PopupsAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\PopupsAllowedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：PopupsAllowedForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### PopupsBlockedForUrls

  #### 在特定网站上阻止弹出窗口

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  根据 URL 模式定义阻止打开弹出窗口的网站列表。

如果未配置此策略，则所有网站都将使用 [DefaultPopupsSetting](#defaultpopupssetting) 策略中的全局默认值（如果已设置）或用户的个人配置。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：PopupsBlockedForUrls
  - GP 名称：在特定网站上阻止弹出窗口
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\PopupsBlockedForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\PopupsBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\PopupsBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：PopupsBlockedForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### RegisteredProtocolHandlers

  #### 注册协议处理程序

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  设置此策略（仅推荐），注册协议处理程序列表。 此列表与用户注册的列表合并，两者均可使用。

注册协议处理程序：

- 将 "协议" 属性设置为方案（例如，"mailto"）
- 将 URL 属性设置为处理 "协议" 字段中指定的方案的应用程序的 URL 属性。 模式可包括已处理 URL 替换的 "% s" 占位符。

用户不能删除由此策略注册的协议处理程序。 但是，他们可以安装新的默认协议处理程序来替代现有的协议处理程序。

  #### 支持的功能：

  - 可以强制：否
  - 可以推荐：是
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - Dictionary

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：RegisteredProtocolHandlers
  - GP 名称：注册协议处理程序
  - GP 路径（强制）：不适用
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/内容设置
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：不适用
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：RegisteredProtocolHandlers
  - 值类型：REG_SZ

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\RegisteredProtocolHandlers = [
  {
    "default": true, 
    "protocol": "mailto", 
    "url": "https://mail.contoso.com/mail/?extsrc=mailto&url=%s"
  }
]
```

  ##### 精简示例值：

  ```
  SOFTWARE\Policies\Microsoft\Edge\RegisteredProtocolHandlers = [{"default": true, "protocol": "mailto", "url": "https://mail.contoso.com/mail/?extsrc=mailto&url=%s"}]
  ```
  

  #### Mac 信息和设置
  
  - 首选项项名称：RegisteredProtocolHandlers
  - 示例值：
``` xml
<key>RegisteredProtocolHandlers</key>
<array>
  <dict>
    <key>default</key>
    <true/>
    <key>protocol</key>
    <string>mailto</string>
    <key>url</key>
    <string>https://mail.contoso.com/mail/?extsrc=mailto&url=%s</string>
  </dict>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SpotlightExperiencesAndRecommendationsEnabled

  #### 选择用户是否可接收自定义的背景图像和文本、建议、通知，
以及有关 Microsoft 服务的提示

  
  
  #### 支持的版本：

  - 在 86 版或更高版本的 Windows 上

  #### 描述

  选择用户是否可接收自定义的背景图像和文本、建议、通知及 Microsoft 服务提示。

如果启用或未配置此设置，将启用聚焦体验和建议。

如果禁用此设置，聚焦体验和建议将关闭。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称： SpotlightExperiencesAndRecommendationsEnabled
  - GP 名称：选择用户是否可接收自定义的背景图像和文本、建议、通知及 Microsoft 服务提示
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：SpotlightExperiencesAndRecommendationsEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  

  [返回页首](#microsoft-edge---policies)

  ### WebUsbAllowDevicesForUrls

  #### 授予特定网站连接到特定 USB 设备的访问权限

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  允许你设置一个 url 列表，指定自动向哪些网站授予对具有给定供应商和产品 ID 的 USB 设备的访问权限。 列表中的每个项目必须同时包含设备和 url，策略才能有效。 设备中的每个项目都可包含供应商 ID 和产品 ID 字段。 省略的任何 ID 都将被视为通配符，但有一个例外，即如果未同时指定供应商 ID，则也无法指定产品 ID。 否则，该策略将无效并将被忽略。

USB 权限模式使用请求网站的 URL（“请求 URL”）和顶级框架网站的 URL（“嵌入 URL”）来向请求 URL 授予访问 USB 设备的权限。 当请求网站加载到 iframe 中时，请求 URL 可能与嵌入 URL 不同。 因此，“urls”字段最多可包含两个用逗号分隔的 URL 字符串，以分别指定请求 URL 和嵌入 URL。 如果仅指定一个 URL，则在请求网站的 URL 与此 URL 匹配时，将授予对相应 USB 设备的访问权限，而不管嵌入状态如何。 “urls”中的 URL 必须是有效的 URL，否则该策略将被忽略。

如果未设置此策略，则所有网站将使用 [DefaultWebUsbGuardSetting](#defaultwebusbguardsetting) 策略中的全局默认值（如果已设置），否则将使用用户的个人配置。

此策略中的 URL 模式不应与通过 [WebUsbBlockedForUrls](#webusbblockedforurls) 配置的 URL 模式冲突。 如果发生冲突，此策略将优先于 [WebUsbBlockedForUrls](#webusbblockedforurls) 和 [WebUsbAskForUrls](#webusbaskforurls)。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - Dictionary

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：WebUsbAllowDevicesForUrls
  - GP 名称：授予特定网站连接到特定 USB 设备的访问权限
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：WebUsbAllowDevicesForUrls
  - 值类型：REG_SZ

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\WebUsbAllowDevicesForUrls = [
  {
    "devices": [
      {
        "product_id": 5678, 
        "vendor_id": 1234
      }
    ], 
    "urls": [
      "https://contoso.com", 
      "https://fabrikam.com"
    ]
  }
]
```

  ##### 精简示例值：

  ```
  SOFTWARE\Policies\Microsoft\Edge\WebUsbAllowDevicesForUrls = [{"devices": [{"product_id": 5678, "vendor_id": 1234}], "urls": ["https://contoso.com", "https://fabrikam.com"]}]
  ```
  

  #### Mac 信息和设置
  
  - 首选项项名称：WebUsbAllowDevicesForUrls
  - 示例值：
``` xml
<key>WebUsbAllowDevicesForUrls</key>
<array>
  <dict>
    <key>devices</key>
    <array>
      <dict>
        <key>product_id</key>
        <integer>5678</integer>
        <key>vendor_id</key>
        <integer>1234</integer>
      </dict>
    </array>
    <key>urls</key>
    <array>
      <string>https://contoso.com</string>
      <string>https://fabrikam.com</string>
    </array>
  </dict>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### WebUsbAskForUrls

  #### 在特定网站上允许 WebUSB

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  根据 URL 模式定义可要求用户授予 USB 设备访问权限的网站列表。

如果未配置此策略，则所有网站都将使用 [DefaultWebUsbGuardSetting](#defaultwebusbguardsetting) 策略中的全局默认值（如果已设置）或用户的个人配置。

此策略中定义的 URL 模式不能与 [WebUsbBlockedForUrls](#webusbblockedforurls) 策略中配置的 URL 模式冲突 - 不能同时允许和阻止一个 URL。 有关有效 url 模式的详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：WebUsbAskForUrls
  - GP 名称：在特定网站上允许 WebUSB
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\WebUsbAskForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\WebUsbAskForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\WebUsbAskForUrls\2 = "[*.]contoso.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：WebUsbAskForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### WebUsbBlockedForUrls

  #### 在特定网站上阻止 WebUSB

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  根据 URL 模式定义不能要求用户授予 USB 设备访问权限的网站列表。

如果未配置此策略，则所有网站都将使用 [DefaultWebUsbGuardSetting](#defaultwebusbguardsetting) 策略中的全局默认值（如果已设置）或用户的个人配置。

此策略中的 URL 模式不能与 [WebUsbAskForUrls](#webusbaskforurls) 策略中配置的 URL 模式冲突。 不能同时允许和阻止一个 URL。  有关有效 url 模式的详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：WebUsbBlockedForUrls
  - GP 名称：在特定网站上阻止 WebUSB
  - GP 路径（强制）：管理模板/Microsoft Edge/内容设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\WebUsbBlockedForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\WebUsbBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\WebUsbBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：WebUsbBlockedForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ## 默认搜索提供程序策略

  [返回页首](#microsoft-edge---policies)

  ### DefaultSearchProviderEnabled

  #### 启用默认搜索提供程序

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  使用户能够使用默认搜索提供程序。

如果启用此策略，用户可以通过在地址栏中键入内容来搜索字词（前提是他们键入的内容不是 URL）。

可通过启用其余默认搜索策略来指定要使用的默认搜索提供程序。 如果这些保留为空（未配置）或配置不当，则用户可以选择默认提供程序。

如果禁用此策略，用户将无法从地址栏中进行搜索。

如果启用或禁用此策略，用户将无法更改或替代它。

如果未配置此策略，则将启用默认搜索提供程序，用户可以选择默认搜索提供程序并设置搜索提供程序列表。

此策略仅在加入 Microsoft Active Directory 域的 Windows 实例、已注册设备管理的 Windows 10 专业版或企业版实例，或者通过 MDM 托管或通过 MCX 加入域的 macOS 实例上可用。

从 Microsoft Edge 84 开始，你可以将此策略设置建议策略。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultSearchProviderEnabled
  - GP 名称：启用默认搜索提供程序
  - GP 路径（强制）：管理模板/Microsoft Edge/默认搜索提供程序
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认设置（用户可替代）/默认搜索提供程序
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：DefaultSearchProviderEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultSearchProviderEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultSearchProviderEncodings

  #### 默认搜索提供程序编码

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指定搜索提供程序支持的字符编码。 编码是 UTF-8、GB2312 和 ISO-8859-1 之类的代码页名称。 将按照提供的顺序尝试这些编码。

此策略是可选的。 如果未配置，则使用默认 UTF-8。

只有当启用 [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) 和 [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) 策略时，才会应用此策略。

从 Microsoft Edge 84 开始，你可以将此策略设置建议策略。 如果用户已经设置了默认搜索提供程序，此推荐策略配置的默认搜索提供程序不会添加到用户可选择的搜索提供程序列表中。 如果这是所需的行为，请使用[ManagedSearchEngines](#managedsearchengines)策略。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultSearchProviderEncodings
  - GP 名称：默认搜索提供程序编码
  - GP 路径（强制）：管理模板/Microsoft Edge/默认搜索提供程序
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认设置（用户可替代）/默认搜索提供程序
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\DefaultSearchProviderEncodings
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended\DefaultSearchProviderEncodings
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\DefaultSearchProviderEncodings\1 = "UTF-8"
SOFTWARE\Policies\Microsoft\Edge\DefaultSearchProviderEncodings\2 = "UTF-16"
SOFTWARE\Policies\Microsoft\Edge\DefaultSearchProviderEncodings\3 = "GB2312"
SOFTWARE\Policies\Microsoft\Edge\DefaultSearchProviderEncodings\4 = "ISO-8859-1"

```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultSearchProviderEncodings
  - 示例值：
``` xml
<array>
  <string>UTF-8</string>
  <string>UTF-16</string>
  <string>GB2312</string>
  <string>ISO-8859-1</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultSearchProviderImageURL

  #### 指定默认搜索提供程序的“按图像搜索”功能

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指定用于图像搜索的搜索引擎的 URL。 将使用 GET 方法发送搜索请求。

此策略是可选的。 如果未配置，则图像搜索不可用。

指定必应的图像搜索 URL，如下所示：“{bing:baseURL}images/detail/search?iss=sbiupload&FORM=ANCMS1#enterInsights”。

指定 Google 的图像搜索 URL，如下所示：“{google:baseURL}searchbyimage/upload”。

请参阅 [DefaultSearchProviderImageURLPostParams](#defaultsearchproviderimageurlpostparams) 策略，完成图像搜索的配置。

只有当启用 [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) 和 [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) 策略时，才会应用此策略。

从 Microsoft Edge 84 开始，你可以将此策略设置建议策略。 如果用户已经设置了默认搜索提供程序，此推荐策略配置的默认搜索提供程序不会添加到用户可选择的搜索提供程序列表中。 如果这是所需的行为，请使用[ManagedSearchEngines](#managedsearchengines)策略。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultSearchProviderImageURL
  - GP 名称：指定默认搜索提供程序的“按图像搜索”功能
  - GP 路径（强制）：管理模板/Microsoft Edge/默认搜索提供程序
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认设置（用户可替代）/默认搜索提供程序
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：DefaultSearchProviderImageURL
  - 值类型：REG_SZ

  ##### 示例值：

```
"https://search.contoso.com/searchbyimage/upload"
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultSearchProviderImageURL
  - 示例值：
``` xml
<string>https://search.contoso.com/searchbyimage/upload</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultSearchProviderImageURLPostParams

  #### 使用 POST 的图像 URL 的参数

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  如果启用此策略，则会指定在执行使用 POST 的图像搜索时使用的参数。 该策略由逗号分隔的名称/值对组成。 如果值是模板参数（如上例中的 {imageThumbnail}），则将替换为实际图像缩略图数据。 只有当启用 [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) 和 [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) 策略时，才会应用此策略。

指定必应的图像搜索 URL Post 参数，如下所示：“imageBin={google:imageThumbnailBase64}”。

指定 Google 的图像搜索 URL Post 参数，如下所示：“encoded_image={google:imageThumbnail},image_url={google:imageURL},sbisrc={google:imageSearchSource},original_width={google:imageOriginalWidth},original_height={google:imageOriginalHeight}”。

如果未设置此策略，则将使用 GET 方法发送图像搜索请求。

从 Microsoft Edge 84 开始，你可以将此策略设置建议策略。 如果用户已经设置了默认搜索提供程序，此推荐策略配置的默认搜索提供程序不会添加到用户可选择的搜索提供程序列表中。 如果这是所需的行为，请使用[ManagedSearchEngines](#managedsearchengines)策略。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultSearchProviderImageURLPostParams
  - GP 名称：使用 POST 的图像 URL 的参数
  - GP 路径（强制）：管理模板/Microsoft Edge/默认搜索提供程序
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认设置（用户可替代）/默认搜索提供程序
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：DefaultSearchProviderImageURLPostParams
  - 值类型：REG_SZ

  ##### 示例值：

```
"content={imageThumbnail},url={imageURL},sbisrc={SearchSource}"
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultSearchProviderImageURLPostParams
  - 示例值：
``` xml
<string>content={imageThumbnail},url={imageURL},sbisrc={SearchSource}</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultSearchProviderKeyword

  #### 默认搜索提供程序关键字

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指定关键字，它是用于在地址栏中对此提供程序触发搜索的快捷方式。

此策略是可选的。 如果未配置，则没有关键字激活搜索提供程序。

只有当启用 [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) 和 [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) 策略时，才会应用此策略。

从 Microsoft Edge 84 开始，你可以将此策略设置建议策略。 如果用户已经设置了默认搜索提供程序，此推荐策略配置的默认搜索提供程序不会添加到用户可选择的搜索提供程序列表中。 如果这是所需的行为，请使用[ManagedSearchEngines](#managedsearchengines)策略。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultSearchProviderKeyword
  - GP 名称：默认搜索提供程序关键字
  - GP 路径（强制）：管理模板/Microsoft Edge/默认搜索提供程序
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认设置（用户可替代）/默认搜索提供程序
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：DefaultSearchProviderKeyword
  - 值类型：REG_SZ

  ##### 示例值：

```
"mis"
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultSearchProviderKeyword
  - 示例值：
``` xml
<string>mis</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultSearchProviderName

  #### 默认搜索提供程序名称

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指定默认搜索提供程序的名称。

如果启用此策略，则设置默认搜索提供程序的名称。

如果未启用此策略或将其留空，则将使用搜索 URL 指定的主机名。

“DefaultSearchProviderName”应设置为组织批准的加密搜索提供程序，该搜索提供程序对应于 DTBC-0008 中设置的加密搜索提供程序。 只有当启用 [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) 和 [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) 策略时，才会应用此策略。

从 Microsoft Edge 84 开始，你可以将此策略设置建议策略。 如果用户已经设置了默认搜索提供程序，此推荐策略配置的默认搜索提供程序不会添加到用户可选择的搜索提供程序列表中。 如果这是所需的行为，请使用[ManagedSearchEngines](#managedsearchengines)策略。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultSearchProviderName
  - GP 名称：默认搜索提供程序名称
  - GP 路径（强制）：管理模板/Microsoft Edge/默认搜索提供程序
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认设置（用户可替代）/默认搜索提供程序
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：DefaultSearchProviderName
  - 值类型：REG_SZ

  ##### 示例值：

```
"My Intranet Search"
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultSearchProviderName
  - 示例值：
``` xml
<string>My Intranet Search</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultSearchProviderSearchURL

  #### 默认搜索提供程序搜索 URL

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指定用于默认搜索的搜索引擎的 URL。 该 URL 包含字符串“{searchTerms}”，在查询时，该字符串将替换为用户正在搜索的字词。

指定必应的搜索 URL，如下所示：

“{bing:baseURL}search?q={searchTerms}”。

指定 Google 的搜索 URL，如下所示：“{google:baseURL}search?q={searchTerms}&{google:RLZ}{google:originalQueryForSuggestion}{google:assistedQueryStats}{google:searchFieldtrialParameter}{google:searchClient}{google:sourceId}ie={inputEncoding}”。

启用 [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) 策略时，此策略是必需的；如果未启用 DefaultSearchProviderEnabled 策略，则此策略将被忽略。

从 Microsoft Edge 84 开始，你可以将此策略设置建议策略。 如果用户已经设置了默认搜索提供程序，此推荐策略配置的默认搜索提供程序不会添加到用户可选择的搜索提供程序列表中。 如果这是所需的行为，请使用[ManagedSearchEngines](#managedsearchengines)策略。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultSearchProviderSearchURL
  - GP 名称：默认搜索提供程序搜索 URL
  - GP 路径（强制）：管理模板/Microsoft Edge/默认搜索提供程序
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认设置（用户可替代）/默认搜索提供程序
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：DefaultSearchProviderSearchURL
  - 值类型：REG_SZ

  ##### 示例值：

```
"https://search.contoso.com/search?q={searchTerms}"
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultSearchProviderSearchURL
  - 示例值：
``` xml
<string>https://search.contoso.com/search?q={searchTerms}</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultSearchProviderSuggestURL

  #### 建议的默认搜索提供程序 URL

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指定用于提供搜索建议的搜索引擎的 URL。 该 URL 包含字符串“{searchTerms}”，在查询时，该字符串将替换为用户迄今为止输入的文本。

此策略是可选的。 如果未配置该策略，用户将看不到搜索建议；他们将看到来自浏览历史记录和收藏夹的建议。

必应的建议 URL 可指定为：

“{bing:baseURL}qbox?query={searchTerms}”。

Google 的建议 URL 可指定为：“{google:baseURL}complete/search?output=chrome&q={searchTerms}”。

只有当启用 [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) 和 [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) 策略时，才会应用此策略。

从 Microsoft Edge 84 开始，你可以将此策略设置建议策略。 如果用户已经设置了默认搜索提供程序，此推荐策略配置的默认搜索提供程序不会添加到用户可选择的搜索提供程序列表中。 如果这是所需的行为，请使用[ManagedSearchEngines](#managedsearchengines)策略。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultSearchProviderSuggestURL
  - GP 名称：建议的默认搜索提供程序 URL
  - GP 路径（强制）：管理模板/Microsoft Edge/默认搜索提供程序
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认设置（用户可替代）/默认搜索提供程序
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：DefaultSearchProviderSuggestURL
  - 值类型：REG_SZ

  ##### 示例值：

```
"https://search.contoso.com/suggest?q={searchTerms}"
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultSearchProviderSuggestURL
  - 示例值：
``` xml
<string>https://search.contoso.com/suggest?q={searchTerms}</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### NewTabPageSearchBox

  #### 配置新建选项卡页面搜索框体验

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 85 或更高版本起

  #### 描述

  你可以配置新的标签页搜索框使用“搜索框(推荐)”或“地址栏”来搜索新的标签页。 这个策略只有在你通过设置下面两个策略，将搜索引擎设置为 Bing 之外的值才有效： [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) 和[DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl)。

 如果禁用或未配置此策略和：

- 如果地址栏的默认搜索引擎是必应，新的选项卡页面使用搜索框搜索新的选项卡。
- 如果地址栏的默认搜索引擎不是必应，用户在搜索新标签时可以有额外的选择(使用“地址栏”)。


如果启用此策略并将其设置为：

- "搜索框（推荐）" （'必应'），新选项卡页面使用搜索框搜索新选项卡。
- "地址栏" （"重定向"），新建选项卡页面搜索框使用地址栏在新选项卡上搜索。

策略选项映射：

* bing (bing) = 搜索框（推荐）

* redirect (redirect) = 地址栏

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：NewTabPageSetFeedType
  - GP 名称：配置新的选项卡页面搜索框体验
  - GP 路径（强制）：管理模板/Microsoft Edge/默认搜索提供程序
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认设置（用户可替代）/默认搜索提供程序
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称： NewTabPageSearchBox
  - 值类型：REG_SZ

  ##### 示例值：

```
"bing"
```

  #### Mac 信息和设置
  
  - 首选项名称：NewTabPageSetFeedType
  - 示例值：
``` xml
<string>bing</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ## 扩展策略

  [返回页首](#microsoft-edge---policies)

  ### ExtensionAllowedTypes

  #### 配置允许的扩展类型

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  控制可安装的扩展类型并限制运行时访问。

此设置定义允许的扩展类型以及它们可以与哪些主机交互。 该值是一个字符串列表，其中每个字符串应为以下内容之一：“extension”、“theme”、“user_script”和“hosted_app”。 有关这些类型的详细信息，请参阅 Microsoft Edge 扩展文档。

请注意，此策略还会影响使用 [ExtensionInstallForcelist](#extensioninstallforcelist) 策略强制安装的扩展。

如果启用此策略，则只安装与列表中的类型匹配的扩展。

如果未配置此策略，则不会对可接受的扩展类型强制实施任何限制。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ExtensionAllowedTypes
  - GP 名称：配置允许的扩展类型
  - GP 路径（强制）：管理模板/Microsoft Edge/扩展
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\ExtensionAllowedTypes
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\ExtensionAllowedTypes\1 = "hosted_app"

```

  #### Mac 信息和设置
  
  - 首选项项名称：ExtensionAllowedTypes
  - 示例值：
``` xml
<array>
  <string>hosted_app</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ExtensionInstallAllowlist

  #### 允许安装特定扩展

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  默认情况下，允许所有扩展。 但是，如果通过将“ExtensionInstallBlockList”策略设置为“*”来阻止所有扩展，则用户只能安装此策略中定义的扩展。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ExtensionInstallAllowlist
  - GP 名称：允许安装特定扩展
  - GP 路径（强制）：管理模板/Microsoft Edge/扩展
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallAllowlist
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallAllowlist\1 = "extension_id1"
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallAllowlist\2 = "extension_id2"

```

  #### Mac 信息和设置
  
  - 首选项项名称：ExtensionInstallAllowlist
  - 示例值：
``` xml
<array>
  <string>extension_id1</string>
  <string>extension_id2</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ExtensionInstallBlocklist

  #### 控制无法安装的扩展

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  列出用户无法在 Microsoft Edge 中安装的特定扩展。 部署此策略时，此列表上以前安装的任何扩展都将被禁用，用户不能启用它们。 如果从阻止的扩展列表中删除某个项目，则该扩展将在以前安装的任何位置自动重新启用。

使用“*”可阻止允许列表中未明确列出的所有扩展。

如果未配置此策略，用户可以在 Microsoft Edge 中安装任何扩展。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ExtensionInstallBlocklist
  - GP 名称：控制无法安装的扩展
  - GP 路径（强制）：管理模板/Microsoft Edge/扩展
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallBlocklist
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallBlocklist\1 = "extension_id1"
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallBlocklist\2 = "extension_id2"

```

  #### Mac 信息和设置
  
  - 首选项项名称：ExtensionInstallBlocklist
  - 示例值：
``` xml
<array>
  <string>extension_id1</string>
  <string>extension_id2</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ExtensionInstallForcelist

  #### 控制静默安装的扩展

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指定静默安装、无需用户交互并且用户不能卸载或禁用（“强制安装”）的扩展。 扩展请求的所有权限都是隐式授予的，无需用户交互，包括扩展的未来版本所请求的任何其他权限。 此外，还为 enterprise.deviceAttributes 和 enterprise.platformKeys 扩展 API 授予权限。 （这两个 API 仅适用于强制安装的扩展。）

此策略优先于可能冲突的 [ExtensionInstallBlocklist](#extensioninstallblocklist) 策略。 当从强制安装列表中删除某个扩展时，Microsoft Edge 会自动卸载该扩展。

强制安装仅限于 Microsoft Edge 加载项网站中列出的不属于以下实例的应用和扩展：已加入 Microsoft Active Directory 域的 Windows 实例、已注册用于设备管理的 Windows 10 专业版或企业版实例，以及通过 MDM 管理的或通过 MCX 加入到域的 macOS 实例。

请注意，用户可以使用开发人员工具修改任何扩展的源代码，这可能会使扩展无法正常工作。 如果需要考虑此问题，请设置 [DeveloperToolsAvailability](#developertoolsavailability) 策略。

使用以下格式将扩展添加到列表中：

[extensionID];[updateURL]

- extensionID - 处于开发人员模式时在 edge://extensions 上找到的 32 个字母的字符串。

- updateURL（可选）是应用或扩展的更新清单 XML 文档的地址，如 [https://go.microsoft.com/fwlink/?linkid=2095043](https://go.microsoft.com/fwlink/?linkid=2095043) 中所述。 如果想要从 Chrome Web Store 安装扩展，请提供 Chrome Web Store 更新的 URL，https://clients2.google.com/service/update2/crx。 请注意，此策略中设置的更新 URL 仅用于初始安装；扩展的后续更新将使用扩展清单中指示的更新 URL。 如果未设置 updateURL，则会假定扩展名承载在 Microsoft Store 中，并使用以下更新 URL（ https://edge.microsoft.com/extensionwebstorebase/v1/crx)。

例如，gggmmkjegpiggikcnhidnjjhmicpibll;https://edge.microsoft.com/extensionwebstorebase/v1/crx 将从 Microsoft Store“更新”URL 安装 Microsoft Online 应用。 有关托管扩展的详细信息，请参阅：[https://go.microsoft.com/fwlink/?linkid=2095044](https://go.microsoft.com/fwlink/?linkid=2095044)。

如果未配置此策略，则不会自动安装任何扩展，用户可以卸载 Microsoft Edge 中的任何扩展。

请注意，此策略不适用于 InPrivate 模式。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ExtensionInstallForcelist
  - GP 名称：控制静默安装的扩展
  - GP 路径（强制）：管理模板/Microsoft Edge/扩展
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallForcelist
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallForcelist\1 = "gbchcmhmhahfdphkhkmpfmihenigjmpp;https://edge.microsoft.com/extensionwebstorebase/v1/crx"
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallForcelist\2 = "abcdefghijklmnopabcdefghijklmnop"

```

  #### Mac 信息和设置
  
  - 首选项项名称：ExtensionInstallForcelist
  - 示例值：
``` xml
<array>
  <string>gbchcmhmhahfdphkhkmpfmihenigjmpp;https://edge.microsoft.com/extensionwebstorebase/v1/crx</string>
  <string>abcdefghijklmnopabcdefghijklmnop</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ExtensionInstallSources

  #### 配置扩展和用户脚本安装源

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  定义可安装扩展和主题的 URL。

定义可直接安装扩展和主题的 Url，无需将包拖放到 edge://extensions 页面。

此列表中的每个项目都是扩展样式匹配模式（请参阅 [https://go.microsoft.com/fwlink/?linkid=2095039](https://go.microsoft.com/fwlink/?linkid=2095039)）。 用户可以轻松地从与此列表中的项目匹配的任何 URL 安装项目。 这些模式必须允许 *.crx 文件的位置和从其启动下载的页面（换句话说，即引用者）。 不要在需要身份验证的位置承载文件。

[ExtensionInstallBlocklist](#extensioninstallblocklist) 策略优先于此策略。 不会安装阻止列表上的任何扩展，即使它来自此列表上的网站也是如此。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ExtensionInstallSources
  - GP 名称：配置扩展和用户脚本安装源
  - GP 路径（强制）：管理模板/Microsoft Edge/扩展
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallSources
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\ExtensionInstallSources\1 = "https://corp.contoso.com/*"

```

  #### Mac 信息和设置
  
  - 首选项项名称：ExtensionInstallSources
  - 示例值：
``` xml
<array>
  <string>https://corp.contoso.com/*</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ExtensionSettings

  #### 配置扩展管理设置

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  配置 Microsoft Edge 的扩展管理设置。

此策略控制多个设置，包括由任何现有扩展相关策略控制的设置。 如果同时设置了此策略和任何旧策略，则此策略将替代旧策略。

此策略会将扩展 ID 或更新 URL 映射到其配置。 使用扩展 ID 时，配置仅应用于指定的扩展。 设置特殊 ID“*”的默认配置，以应用于此策略中未明确列出的所有扩展。 使用更新 URL 时，配置将应用于具有此扩展清单中所述的确切更新 URL 的所有扩展，如 [https://go.microsoft.com/fwlink/?linkid=2095043](https://go.microsoft.com/fwlink/?linkid=2095043) 所述。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - Dictionary

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ExtensionSettings
  - GP 名称：配置扩展管理设置
  - GP 路径（强制）：管理模板/Microsoft Edge/扩展
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ExtensionSettings
  - 值类型：REG_SZ

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\ExtensionSettings = {
  "*": {
    "allowed_types": [
      "hosted_app"
    ], 
    "blocked_install_message": "Custom error message.", 
    "blocked_permissions": [
      "downloads", 
      "bookmarks"
    ], 
    "install_sources": [
      "https://company-intranet/apps"
    ], 
    "installation_mode": "blocked", 
    "runtime_allowed_hosts": [
      "*://good.contoso.com"
    ], 
    "runtime_blocked_hosts": [
      "*://*.contoso.com"
    ]
  }, 
  "abcdefghijklmnopabcdefghijklmnop": {
    "blocked_permissions": [
      "history"
    ], 
    "installation_mode": "allowed", 
    "minimum_version_required": "1.0.1"
  }, 
  "bcdefghijklmnopabcdefghijklmnopa": {
    "allowed_permissions": [
      "downloads"
    ], 
    "installation_mode": "force_installed", 
    "runtime_allowed_hosts": [
      "*://good.contoso.com"
    ], 
    "runtime_blocked_hosts": [
      "*://*.contoso.com"
    ], 
    "update_url": "https://contoso.com/update_url"
  }, 
  "cdefghijklmnopabcdefghijklmnopab": {
    "blocked_install_message": "Custom error message.", 
    "installation_mode": "blocked"
  }, 
  "defghijklmnopabcdefghijklmnopabc,efghijklmnopabcdefghijklmnopabcd": {
    "blocked_install_message": "Custom error message.", 
    "installation_mode": "blocked"
  }, 
  "fghijklmnopabcdefghijklmnopabcde": {
    "blocked_install_message": "Custom removal message.", 
    "installation_mode": "removed"
  }, 
  "update_url:https://www.contoso.com/update.xml": {
    "allowed_permissions": [
      "downloads"
    ], 
    "blocked_permissions": [
      "wallpaper"
    ], 
    "installation_mode": "allowed"
  }
}
```

  ##### 精简示例值：

  ```
  SOFTWARE\Policies\Microsoft\Edge\ExtensionSettings = {"*": {"allowed_types": ["hosted_app"], "blocked_install_message": "Custom error message.", "blocked_permissions": ["downloads", "bookmarks"], "install_sources": ["https://company-intranet/apps"], "installation_mode": "blocked", "runtime_allowed_hosts": ["*://good.contoso.com"], "runtime_blocked_hosts": ["*://*.contoso.com"]}, "abcdefghijklmnopabcdefghijklmnop": {"blocked_permissions": ["history"], "installation_mode": "allowed", "minimum_version_required": "1.0.1"}, "bcdefghijklmnopabcdefghijklmnopa": {"allowed_permissions": ["downloads"], "installation_mode": "force_installed", "runtime_allowed_hosts": ["*://good.contoso.com"], "runtime_blocked_hosts": ["*://*.contoso.com"], "update_url": "https://contoso.com/update_url"}, "cdefghijklmnopabcdefghijklmnopab": {"blocked_install_message": "Custom error message.", "installation_mode": "blocked"}, "defghijklmnopabcdefghijklmnopabc,efghijklmnopabcdefghijklmnopabcd": {"blocked_install_message": "Custom error message.", "installation_mode": "blocked"}, "fghijklmnopabcdefghijklmnopabcde": {"blocked_install_message": "Custom removal message.", "installation_mode": "removed"}, "update_url:https://www.contoso.com/update.xml": {"allowed_permissions": ["downloads"], "blocked_permissions": ["wallpaper"], "installation_mode": "allowed"}}
  ```
  

  #### Mac 信息和设置
  
  - 首选项项名称：ExtensionSettings
  - 示例值：
``` xml
<key>ExtensionSettings</key>
<dict>
  <key>*</key>
  <dict>
    <key>allowed_types</key>
    <array>
      <string>hosted_app</string>
    </array>
    <key>blocked_install_message</key>
    <string>Custom error message.</string>
    <key>blocked_permissions</key>
    <array>
      <string>downloads</string>
      <string>bookmarks</string>
    </array>
    <key>install_sources</key>
    <array>
      <string>https://company-intranet/apps</string>
    </array>
    <key>installation_mode</key>
    <string>blocked</string>
    <key>runtime_allowed_hosts</key>
    <array>
      <string>*://good.contoso.com</string>
    </array>
    <key>runtime_blocked_hosts</key>
    <array>
      <string>*://*.contoso.com</string>
    </array>
  </dict>
  <key>abcdefghijklmnopabcdefghijklmnop</key>
  <dict>
    <key>blocked_permissions</key>
    <array>
      <string>history</string>
    </array>
    <key>installation_mode</key>
    <string>allowed</string>
    <key>minimum_version_required</key>
    <string>1.0.1</string>
  </dict>
  <key>bcdefghijklmnopabcdefghijklmnopa</key>
  <dict>
    <key>allowed_permissions</key>
    <array>
      <string>downloads</string>
    </array>
    <key>installation_mode</key>
    <string>force_installed</string>
    <key>runtime_allowed_hosts</key>
    <array>
      <string>*://good.contoso.com</string>
    </array>
    <key>runtime_blocked_hosts</key>
    <array>
      <string>*://*.contoso.com</string>
    </array>
    <key>update_url</key>
    <string>https://contoso.com/update_url</string>
  </dict>
  <key>cdefghijklmnopabcdefghijklmnopab</key>
  <dict>
    <key>blocked_install_message</key>
    <string>Custom error message.</string>
    <key>installation_mode</key>
    <string>blocked</string>
  </dict>
  <key>defghijklmnopabcdefghijklmnopabc,efghijklmnopabcdefghijklmnopabcd</key>
  <dict>
    <key>blocked_install_message</key>
    <string>Custom error message.</string>
    <key>installation_mode</key>
    <string>blocked</string>
  </dict>
  <key>fghijklmnopabcdefghijklmnopabcde</key>
  <dict>
    <key>blocked_install_message</key>
    <string>Custom removal message.</string>
    <key>installation_mode</key>
    <string>removed</string>
  </dict>
  <key>update_url:https://www.contoso.com/update.xml</key>
  <dict>
    <key>allowed_permissions</key>
    <array>
      <string>downloads</string>
    </array>
    <key>blocked_permissions</key>
    <array>
      <string>wallpaper</string>
    </array>
    <key>installation_mode</key>
    <string>allowed</string>
  </dict>
</dict>
```
  

  [返回页首](#microsoft-edge---policies)

  ## HTTP 身份验证策略

  [返回页首](#microsoft-edge---policies)

  ### AllowCrossOriginAuthPrompt

  #### Allow cross-origin HTTP Authentication prompts

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  Controls whether third-party images on a page can show an authentication prompt.

通常，这将被禁用，以抵御网络钓鱼威胁。 If you don't configure this policy, it's disabled and third-party images can't show an authentication prompt.

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AllowCrossOriginAuthPrompt
  - GP 名称: 允许跨域 HTTP 身份验证提示
  - GP 路径（强制）：管理模板/Microsoft Edge/HTTP 身份验证
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：AllowCrossOriginAuthPrompt
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：AllowCrossOriginAuthPrompt
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AuthNegotiateDelegateAllowlist

  #### 指定 Microsoft Edge 可将用户凭据委派到的服务器列表

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  配置 Microsoft Edge 可委派到的服务器列表。

以逗号分隔多个服务器名称。 允许使用通配符 (*)。

如果未配置此策略，即使服务器被检测为 Intranet，Microsoft Edge 也不会委派用户凭据。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AuthNegotiateDelegateAllowlist
  - GP 名称：指定 Microsoft Edge 可将用户凭据委派到的服务器列表
  - GP 路径（强制）：管理模板/Microsoft Edge/HTTP 身份验证
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：AuthNegotiateDelegateAllowlist
  - 值类型：REG_SZ

  ##### 示例值：

```
"contoso.com"
```

  #### Mac 信息和设置
  
  - 首选项项名称：AuthNegotiateDelegateAllowlist
  - 示例值：
``` xml
<string>contoso.com</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AuthSchemes

  #### 支持的身份验证方案

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指定支持的 HTTP 身份验证方案。

可使用以下值来配置策略：“basic”、“digest”、“ntlm”和“negotiate”。 用逗号分隔多个值。

如果未配置此策略，将使用所有 4 种方案。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AuthSchemes
  - GP 名称：支持的身份验证方案
  - GP 路径（强制）：管理模板/Microsoft Edge/HTTP 身份验证
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：AuthSchemes
  - 值类型：REG_SZ

  ##### 示例值：

```
"basic,digest,ntlm,negotiate"
```

  #### Mac 信息和设置
  
  - 首选项项名称：AuthSchemes
  - 示例值：
``` xml
<string>basic,digest,ntlm,negotiate</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AuthServerAllowlist

  #### 配置允许的身份验证服务器列表

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指定要启用集成身份验证的服务器。 仅当 Microsoft Edge 从代理或此列表中的服务器收到身份验证质询时，才会启用集成身份验证。

以逗号分隔多个服务器名称。 允许使用通配符 (*)。

如果未配置此策略，Microsoft Edge 将尝试检测服务器是否位于 Intranet 上 - 只有这样，它才会响应 IWA 请求。 如果服务器在 Internet 上，Microsoft Edge 将忽略来自服务器的 IWA 请求。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AuthServerAllowlist
  - GP 名称：配置允许的身份验证服务器列表
  - GP 路径（强制）：管理模板/Microsoft Edge/HTTP 身份验证
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：AuthServerAllowlist
  - 值类型：REG_SZ

  ##### 示例值：

```
"*contoso.com,contoso.com"
```

  #### Mac 信息和设置
  
  - 首选项项名称：AuthServerAllowlist
  - 示例值：
``` xml
<string>*contoso.com,contoso.com</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DisableAuthNegotiateCnameLookup

  #### 在协商 Kerberos 身份验证时禁用 CNAME 查找

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  确定生成的 Kerberos SPN 是基于规范 DNS 名称 (CNAME) 还是基于输入的原始名称。

如果启用此策略，将跳过 CNAME 查找，并使用服务器名称（如所输入）。

如果禁用或未配置此策略，则将使用服务器的规范名称。  这是通过 CNAME 查找确定的。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DisableAuthNegotiateCnameLookup
  - GP 名称：在协商 Kerberos 身份验证时禁用 CNAME 查找
  - GP 路径（强制）：管理模板/Microsoft Edge/HTTP 身份验证
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DisableAuthNegotiateCnameLookup
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：DisableAuthNegotiateCnameLookup
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### EnableAuthNegotiatePort

  #### 在 Kerberos SPN 中包括非标准端口

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指定生成的 Kerberos SPN 是否应包括非标准端口。

如果启用此策略，并且用户在 URL 中包括非标准端口（80 或 443 以外的端口），则该端口将包括在生成的 Kerberos SPN 中。

如果未配置或禁用此策略，则生成的 Kerberos SPN 在任何情况下都不包括端口。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：EnableAuthNegotiatePort
  - GP 名称：在 Kerberos SPN 中包括非标准端口
  - GP 路径（强制）：管理模板/Microsoft Edge/HTTP 身份验证
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：EnableAuthNegotiatePort
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：EnableAuthNegotiatePort
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### NtlmV2Enabled

  #### 控制是否启用 NTLMv2 身份验证

  
  
  #### 支持的版本：

  - 在 macOS 上自 77 或更高版本起

  #### 描述

  控制是否启用 NTLMv2。

Samba 和 Windows 服务器的所有最新版本都支持 NTLMv2。 只应禁用 NTLMv2 来解决向后兼容性问题，因为它会降低身份验证的安全性。

如果未配置此策略，则默认情况下将启用 NTLMv2。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  

  #### Mac 信息和设置
  
  - 首选项项名称：NtlmV2Enabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ## 展台模式设置策略

  [返回页首](#microsoft-edge---policies)

  ### KioskAddressBarEditingEnabled

  #### 配置地址栏编辑，实现展台模式的公共浏览体验。

  
  
  #### 支持的版本：

  - On Windows and macOS since 87 or later

  #### 描述

  此策略仅适用于使用公共浏览体验时的 Microsoft Edge 展台模式。

如果启用此策略，将阻止用户更改地址栏中的 URL。

如果禁用此策略或不对其进行配置，用户则可以更改地址栏中的 URL。

有关配置展台模式的详细信息，请参阅[https://go.microsoft.com/fwlink/?linkid=2137578](https://go.microsoft.com/fwlink/?linkid=2137578)。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：KioskAddressBarEditingEnabled
  - GP 名称：配置地址栏编辑，实现展台模式的公共浏览体验。
  - GP 路径（强制）：管理模板/Microsoft Edge/展台模式设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：KioskAddressBarEditingEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：KioskAddressBarEditingEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### KioskDeleteDownloadsOnExit

  #### Microsoft Edge 关闭时删除作为展台会话的一部分下载的文件

  
  
  #### 支持的版本：

  - 在 87 版或更高版本的 Windows 上

  #### 描述

  此策略仅适用于 Microsoft Edge 展台模式。

如果启用此策略，则每次关闭 Microsoft Edge 时，都会删除作为展台会话一部分下载的文件。

如果禁用或未配置此策略，则当 Microsoft Edge 关闭时，作为展台会话一部分下载的文件不会被删除。

有关配置展台模式的详细信息，请参阅[https://go.microsoft.com/fwlink/?linkid=2137578](https://go.microsoft.com/fwlink/?linkid=2137578)。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：KioskDeleteDownloadsOnExit
  - GP 名称：Microsoft Edge 关闭时删除作为展台会话的一部分下载的文件
  - GP 路径（强制）：管理模板/Microsoft Edge/展台模式设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：KioskDeleteDownloadsOnExit
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  

  [返回页首](#microsoft-edge---policies)

  ## 本机消息传递策略

  [返回页首](#microsoft-edge---policies)

  ### NativeMessagingAllowlist

  #### 控制用户可使用的本机消息传递主机

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  列出用户可以在 Microsoft Edge 中使用的特定本机消息传递主机。

默认情况下，允许所有本机消息传递主机。 如果将 [NativeMessagingBlocklist](#nativemessagingblocklist) 策略设置为 *，则会阻止所有本机消息传递主机，并且仅加载此处列出的本机消息传递主机。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：NativeMessagingAllowlist
  - GP 名称：控制用户可使用的本机消息传递主机
  - GP 路径（强制）：管理模板/Microsoft Edge/本机消息传递
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\NativeMessagingAllowlist
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\NativeMessagingAllowlist\1 = "com.native.messaging.host.name1"
SOFTWARE\Policies\Microsoft\Edge\NativeMessagingAllowlist\2 = "com.native.messaging.host.name2"

```

  #### Mac 信息和设置
  
  - 首选项项名称：NativeMessagingAllowlist
  - 示例值：
``` xml
<array>
  <string>com.native.messaging.host.name1</string>
  <string>com.native.messaging.host.name2</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### NativeMessagingBlocklist

  #### 配置本机消息传递阻止列表

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指定不应使用的本机消息传递主机。

使用“*”会阻止所有本机消息传递主机，除非它们明确列在允许列表中。

如果未配置此策略，Microsoft Edge 将加载所有已安装的本机消息传递主机。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：NativeMessagingBlocklist
  - GP 名称：配置本机消息传递阻止列表
  - GP 路径（强制）：管理模板/Microsoft Edge/本机消息传递
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\NativeMessagingBlocklist
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\NativeMessagingBlocklist\1 = "com.native.messaging.host.name1"
SOFTWARE\Policies\Microsoft\Edge\NativeMessagingBlocklist\2 = "com.native.messaging.host.name2"

```

  #### Mac 信息和设置
  
  - 首选项项名称：NativeMessagingBlocklist
  - 示例值：
``` xml
<array>
  <string>com.native.messaging.host.name1</string>
  <string>com.native.messaging.host.name2</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### NativeMessagingUserLevelHosts

  #### 允许用户级本机消息传递主机（已安装但没有管理员权限）

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  启用本机消息传递主机的用户级安装。

如果禁用此策略，Microsoft Edge 将仅使用在系统级安装的本机消息传递主机。

默认情况下，如果未配置此策略，Microsoft Edge 将允许使用用户级本机消息传递主机。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：NativeMessagingUserLevelHosts
  - GP 名称：允许用户级本机消息传递主机（已安装但没有管理员权限）
  - GP 路径（强制）：管理模板/Microsoft Edge/本机消息传递
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：NativeMessagingUserLevelHosts
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：NativeMessagingUserLevelHosts
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ## 密码管理器和保护策略

  [返回页首](#microsoft-edge---policies)

  ### PasswordManagerEnabled

  #### 允许将密码保存到密码管理器

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  允许 Microsoft Edge 保存用户密码。

如果启用此策略，用户可以在 Microsoft Edge 中保存其密码。 下次他们访问网站时，Microsoft Edge 将自动输入密码。

如果禁用此策略，用户将无法保存新密码，但仍然可以使用以前保存的密码。

如果启用或禁用此策略，用户将无法在 Microsoft Edge 中更改或替代它。 如果未配置此策略，用户可以保存密码以及关闭此功能。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：PasswordManagerEnabled
  - GP 名称：允许将密码保存到密码管理器
  - GP 路径（强制）：管理模板/Microsoft Edge/密码管理器和保护
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/密码管理器和保护
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：PasswordManagerEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：PasswordManagerEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### PasswordMonitorAllowed

  #### 如果用户发现其密码不安全，则允许其收到通知

  
  
  #### 支持的版本：

  - 在 85 版或更高版本的 Windows 上

  #### 描述

  允许 Microsoft Edge 监视用户密码。

如果你启用了该策略，并且用户同意启用该策略，此情况下，用户存储在 Microsoft Edge 中的任何密码被发现是不安全的，用户将收到警告。 Microsoft Edge 将显示一条通知，这些信息将在设置 > 密码 >密码监视器提供。

如果禁用此策略，用户将不会得到启用此功能的权限。 密码不会被扫描，也不会收到通知。

如果您启用或未配置策略，用户可以打开或关闭此功能。

若要深入了解 Microsoft Edge 如何查找不安全的密码，请参阅[https://go.microsoft.com/fwlink/?linkid=2133833](https://go.microsoft.com/fwlink/?linkid=2133833)

其他指南：

此策略可以设置为推荐的项目，也可以设置为强制的项目，但是必须使用重要标注。

强制启用：假设个别用户许可是为某位用户启用此功能的预条件，则此策略没有必需的已启用设置。
 如果将策略设置为强制启用，则设置中的 UI 将不会更改，并且将在 edge://policy 中显示以下错误消息。

示例错误状态消息：“忽略此策略值，因为密码监视器需要获得单个用户的同意才能打开它。 你可以要求你组织中的用户进入设置>个人资料>密码并打开该功能。”

建议启用：如果政策设置为推荐启用，UI设置将保持在“关闭”状态，但一个公文包图标旁边将可见这个描述显示在盘旋 - “你的组织推荐这个设置的特定值,你选择了一个不同的价值”

强制启用和推荐的禁用项目：强制和推荐禁用：这两种状态都将正常工作，且向用户显示常用标题。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称： PasswordMonitorAllowed
  - GP 名称：当用户的密码被发现不安全时，允许收到警告
  - GP 路径（强制）：管理模板/Microsoft Edge/密码管理器和保护
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/密码管理器和保护
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称： PasswordMonitorAllowed
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  

  [返回页首](#microsoft-edge---policies)

  ### PasswordProtectionChangePasswordURL

  #### 配置更改密码 URL

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  配置更改密码 URL（仅限 HTTP 和 HTTPS 方案）。

在浏览器中看到警告后，密码保护服务会将用户发送到此 URL 以更改其密码。

如果启用此策略，则密码保护服务会将用户发送到此 URL 以更改其密码。

如果禁用或未配置此策略，则密码保护服务不会将用户重定向到更改密码 URL。

此策略仅在加入 Microsoft Active Directory 域的 Windows 实例、已注册设备管理的 Windows 10 专业版或企业版实例，或者通过 MDM 托管或通过 MCX 加入域的 macOS 实例上可用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：PasswordProtectionChangePasswordURL
  - GP 名称：配置更改密码 URL
  - GP 路径（强制）：管理模板/Microsoft Edge/密码管理器和保护
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：PasswordProtectionChangePasswordURL
  - 值类型：REG_SZ

  ##### 示例值：

```
"https://contoso.com/change_password.html"
```

  #### Mac 信息和设置
  
  - 首选项项名称：PasswordProtectionChangePasswordURL
  - 示例值：
``` xml
<string>https://contoso.com/change_password.html</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### PasswordProtectionLoginURLs

  #### 配置密码保护服务应在其中捕获加盐密码哈希的企业登录 URL 列表

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  配置企业登录 URL 列表（仅限 HTTP 和 HTTPS 方案），Microsoft Edge 应在这些 URL 中捕获加盐密码哈希并将其用于密码重用检测。

如果启用此策略，密码保护服务将在定义的 URL 上捕获密码的指纹。

如果禁用或未配置此策略，则不会捕获密码指纹。

此策略仅在加入 Microsoft Active Directory 域的 Windows 实例、已注册设备管理的 Windows 10 专业版或企业版实例，或者通过 MDM 托管或通过 MCX 加入域的 macOS 实例上可用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：PasswordProtectionLoginURLs
  - GP 名称：配置密码保护服务应在其中捕获加盐密码哈希的企业登录 URL 列表
  - GP 路径（强制）：管理模板/Microsoft Edge/密码管理器和保护
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\PasswordProtectionLoginURLs
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\PasswordProtectionLoginURLs\1 = "https://contoso.com/login.html"
SOFTWARE\Policies\Microsoft\Edge\PasswordProtectionLoginURLs\2 = "https://login.contoso.com"

```

  #### Mac 信息和设置
  
  - 首选项项名称：PasswordProtectionLoginURLs
  - 示例值：
``` xml
<array>
  <string>https://contoso.com/login.html</string>
  <string>https://login.contoso.com</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### PasswordProtectionWarningTrigger

  #### 配置密码保护警告触发器

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  允许你控制何时触发密码保护警告。 当用户在可能可疑的网站上重复使用其受保护的密码时，密码保护会提醒用户。

可使用 [PasswordProtectionLoginURL](#passwordprotectionloginurls) 和 [PasswordProtectionChangePasswordURL](#passwordprotectionchangepasswordurl) 策略来配置要保护的密码。

免除：[PasswordProtectionLoginURL](#passwordprotectionloginurls) 和 [PasswordProtectionChangePasswordURL](#passwordprotectionchangepasswordurl) 中列出的网站以及 [SmartScreenAllowListDomains](#smartscreenallowlistdomains) 中列出的网站的密码不会触发密码保护警告。

设置为“PasswordProtectionWarningOff” 时，不会显示密码保护警告。

设置为“PasswordProtectionWarningOnPasswordReuse“ 后，当用户在所列不允许网站上重新使用其受保护的密码时，将显示密码保护警告。

如果禁用或未配置此策略，则不会显示警告触发器。

策略选项映射：

* PasswordProtectionWarningOff (0) = 关闭密码保护警告

* PasswordProtectionWarningOnPasswordReuse (1) = 密码重用触发密码保护警告

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：PasswordProtectionWarningTrigger
  - GP 名称：配置密码保护警告触发器
  - GP 路径（强制）：管理模板/Microsoft Edge/密码管理器和保护
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：PasswordProtectionWarningTrigger
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：PasswordProtectionWarningTrigger
  - 示例值：
``` xml
<integer>1</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### PasswordRevealEnabled

  #### 启用“显示密码”按钮

  
  
  #### 支持的版本：

  - On Windows and macOS since 87 or later

  #### 描述

  可用于配置网站密码输入字段的浏览器密码显示按钮的默认显示方式。

如果启用或未配置此策略，浏览器用户设置将默认显示密码显示按钮。

如果禁用此策略，浏览器用户设置将不会显示密码显示按钮。

对于辅助功能，用户可以通过默认策略更改浏览器设置。

此策略仅影响浏览器密码显示按钮，不影响网站的自定义显示按钮。

  #### 支持的功能：

  - 可以强制：否
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：PasswordRevealEnabled
  - GP 名称：启用“显示密码”按钮
  - GP 路径（强制）：不适用
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/密码管理器和保护
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：不适用
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：PasswordRevealEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：PasswordRevealEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ## 性能策略

  [返回页首](#microsoft-edge---policies)

  ### StartupBoostEnabled

  #### 启用启动增强

  
  
  #### 支持的版本：

  - 在 88 版或更高版本的 Windows 上

  #### 描述

  允许 Microsoft Edge 进程在操作系统登录时启动，并在最后一个浏览器窗口关闭后继续运行。

如果 Microsoft Edge 正在后台模式下运行，则浏览器可能不会在最后一个窗口关闭时关闭，并且当窗口关闭时，浏览器不会在后台重启。 有关配置 Microsoft Edge 在后台模式下运行时发生的情况的信息，请参阅 [BackgroundModeEnabled](#backgroundmodeenabled) 策略。

如果启用此策略，启动增强将打开。

如果禁用此策略，启动增强将关闭。

如果未配置此策略，启动增强可能初始处于关闭或打开状态。 用户可在 edge://settings/system 中配置其行为。

深入了解启动增强： [https://go.microsoft.com/fwlink/?linkid=2147018](https://go.microsoft.com/fwlink/?linkid=2147018)

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称： StartupBoostEnabled
  - GP名称：启用启动增强
  - GP 路径（强制）：管理模板/Microsoft Edge/性能
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/性能
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称： StartupBoostEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  

  [返回页首](#microsoft-edge---policies)

  ## 打印策略

  [返回页首](#microsoft-edge---policies)

  ### DefaultPrinterSelection

  #### 默认打印机选择规则

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  替代 Microsoft Edge 默认打印机选择规则。 此策略确定在 Microsoft Edge 中选择默认打印机的规则，这在用户首次尝试打印页面时发生。

设置此策略后，Microsoft Edge 将尝试查找与所有指定属性匹配的打印机，并将其用作默认打印机。 如果有多台打印机符合条件，则使用第一台匹配的打印机。

如果未配置此策略，或者在超时时间内未找到匹配的打印机，则打印机默认为内置 PDF 打印机，如果 PDF 打印机不可用，则默认为无打印机。

该值被解析为符合以下架构的 JSON 对象：{ "type": "object", "properties": { "idPattern": { "description": "Regular expression to match printer id.", "type": "string" }, "namePattern": { "description": "Regular expression to match printer display name.", "type": "string" } } }

省略字段意味着所有值都匹配；例如，如果未指定连接，打印预览将开始发现所有类型的本地打印机。 正则表达式模式必须遵循 JavaScript RegExp 语法，并且匹配项区分大小写。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultPrinterSelection
  - GP 名称：默认打印机选择规则
  - GP 路径（强制）：管理模板/Microsoft Edge/打印
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DefaultPrinterSelection
  - 值类型：REG_SZ

  ##### 示例值：

```
"{ \"idPattern\": \".*public\", \"namePattern\": \".*Color\" }"
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultPrinterSelection
  - 示例值：
``` xml
<string>{ "idPattern": ".*public", "namePattern": ".*Color" }</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### PrintHeaderFooter

  #### 打印页眉和页脚

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  在打印对话框中强制打开或关闭“页眉和页脚”。

如果未配置此策略，用户可以决定是否打印页眉和页脚。

如果禁用此策略，用户不能打印页眉和页脚。

如果启用此策略，用户将始终打印页眉和页脚。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：PrintHeaderFooter
  - GP 名称：打印页眉和页脚
  - GP 路径（强制）：管理模板/Microsoft Edge/打印
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/打印
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：PrintHeaderFooter
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：PrintHeaderFooter
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### PrintPreviewUseSystemDefaultPrinter

  #### 将系统默认打印机设置为默认打印机

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指示 Microsoft Edge 将系统默认打印机用作打印预览中的默认选项，而不是最近使用的打印机。

如果禁用或未配置此策略，则打印预览将使用最近使用的打印机作为默认目标选项。

如果启用此策略，打印预览将使用操作系统系统默认打印机作为默认目标选项。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：PrintPreviewUseSystemDefaultPrinter
  - GP 名称：将系统默认打印机设置为默认打印机
  - GP 路径（强制）：管理模板/Microsoft Edge/打印
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/打印
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：PrintPreviewUseSystemDefaultPrinter
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：PrintPreviewUseSystemDefaultPrinter
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### PrintingEnabled

  #### 启用打印

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  在 Microsoft Edge 中启用打印并防止用户更改此设置。

如果启用或未配置此策略，则用户可以打印。

如果禁用此策略，用户将无法从 Microsoft Edge 打印。 打印在扳手菜单、扩展、JavaScript 应用程序等中处于禁用状态。 用户仍可以从打印时跳过 Microsoft Edge 的插件进行打印。 例如，某些 Adobe Flash 应用程序的上下文菜单中具有打印选项，此策略未涵盖此选项。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：PrintingEnabled
  - GP 名称：启用打印
  - GP 路径（强制）：管理模板/Microsoft Edge/打印
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：PrintingEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：PrintingEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### PrintingPaperSizeDefault

  #### 默认打印页面大小

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 86 或更高版本起

  #### 描述

  覆盖默认打印页面大小。

名称应包含列出的格式之一；如果所需的纸张尺寸不在列表中，则名称应包含“自定义”。 如果提供了“自定义”值，则应指定 custom_size 属性。 它描述了所需的高度和宽度（以微米为单位）。 否则，则不应指定 custom_size 属性。 违反这些规则的策略将被忽略。

如果该页面大小在用户选择的打印机上不可用，则将忽略此策略。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - Dictionary

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：PrintingPaperSizeDefault
  - GP 名称：默认打印页面大小
  - GP 路径（强制）：管理模板/Microsoft Edge/打印
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：PrintingPaperSizeDefault
  - 值类型：REG_SZ

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\PrintingPaperSizeDefault = {
  "custom_size": {
    "height": 297000, 
    "width": 210000
  }, 
  "name": "custom"
}
```

  ##### 精简示例值：

  ```
  SOFTWARE\Policies\Microsoft\Edge\PrintingPaperSizeDefault = {"custom_size": {"height": 297000, "width": 210000}, "name": "custom"}
  ```
  

  #### Mac 信息和设置
  
  - 首选项项名称：PrintingPaperSizeDefault
  - 示例值：
``` xml
<key>PrintingPaperSizeDefault</key>
<dict>
  <key>custom_size</key>
  <dict>
    <key>height</key>
    <integer>297000</integer>
    <key>width</key>
    <integer>210000</integer>
  </dict>
  <key>name</key>
  <string>custom</string>
</dict>
```
  

  [返回页首](#microsoft-edge---policies)

  ### UseSystemPrintDialog

  #### 使用系统打印对话框打印

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  显示系统打印对话框而不是打印预览。

如果启用此策略，Microsoft Edge 将在用户打印页面时打开系统打印对话框，而不是内置打印预览。

如果未配置或禁用此策略，打印命令将触发 Microsoft Edge 打印预览屏幕。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：UseSystemPrintDialog
  - GP 名称：使用系统打印对话框打印
  - GP 路径（强制）：管理模板/Microsoft Edge/打印
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：UseSystemPrintDialog
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：UseSystemPrintDialog
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ## 代理服务器策略

  [返回页首](#microsoft-edge---policies)

  ### ProxyBypassList

  #### 配置代理跳过规则（已弃用）

  >已弃用：此策略已弃用。 当前受支持，但将在未来的版本中弃用。
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  此策略已弃用，改为使用[ProxySettings](#proxysettings)。 它在 Microsoft Edge 版本 91 中将不起作用。

定义 Microsoft Edge 为其跳过任何代理的主机列表。

仅当未指定 [ProxySettings](#proxysettings) 策略，并且已在 [ProxyMode](#proxymode) 策略中选择 fixed_servers 时，才会应用此策略。 如果选择了其他任何模式来配置代理策略，请不要启用或配置此策略。

如果启用此策略，则可创建 Microsoft Edge 不对其使用代理的主机列表。

如果未配置此策略，则不会创建 Microsoft Edge 对其跳过代理的主机列表。 如果已指定任何其他设置代理策略的方法，请将此策略保留为未配置。

有关更多详细示例，请转到 [https://go.microsoft.com/fwlink/?linkid=2094936](https://go.microsoft.com/fwlink/?linkid=2094936)。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ProxyBypassList
  - GP名称：配置代理跳过规则（已弃用）
  - GP 路径（强制）：管理模板/Microsoft Edge/代理服务器
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ProxyBypassList
  - 值类型：REG_SZ

  ##### 示例值：

```
"https://www.contoso.com, https://www.fabrikam.com"
```

  #### Mac 信息和设置
  
  - 首选项项名称：ProxyBypassList
  - 示例值：
``` xml
<string>https://www.contoso.com, https://www.fabrikam.com</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ProxyMode

  #### 配置代理服务器设置（已弃用）

  >已弃用：此策略已弃用。 当前受支持，但将在未来的版本中弃用。
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  此策略已弃用，改为使用[ProxySettings](#proxysettings)。 它在 Microsoft Edge 版本 91 中将不起作用。

如果将此策略设置为“启用”，可指定 Microsoft Edge 使用的代理服务器，并阻止用户更改代理设置。 Microsoft Edge 将忽略从命令行指定的所有与代理相关的选项。 仅当未指定 [ProxySettings](#proxysettings) 策略时，才会应用此策略。

如果选择以下选项之一，则会忽略其他选项：
  * direct = 从不使用代理服务器且始终直接连接
  * system = 使用系统代理设置
  * auto_detect = 自动检测代理服务器

如果你选择使用：
  * fixed_servers= 固定代理服务器。 可使用 [ProxyServer](#proxyserver) 和 [ProxyBypassList](#proxybypasslist)指定更多选项。
  * pac_script= .pac 代理脚本。 使用 [ProxyPacUrl](#proxypacurl) 将 URL 设置为代理 .pac 文件。

有关详细示例，请转到 [https://go.microsoft.com/fwlink/?linkid=2094936](https://go.microsoft.com/fwlink/?linkid=2094936)。

如果未配置此策略，用户可选择自己的代理设置。

策略选项映射：

* ProxyDisabled (direct) = 从不使用代理

* ProxyAutoDetect (auto_detect) = 自动检测代理设置

* ProxyPacScript (pac_script) = 使用 .pac 代理脚本

* ProxyFixedServers (fixed_servers) = 使用固定代理服务器

* ProxyUseSystem (system) = 使用系统代理设置

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ProxyMode
  - GP名称：配置代理服务器设置（已弃用）
  - GP 路径（强制）：管理模板/Microsoft Edge/代理服务器
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ProxyMode
  - 值类型：REG_SZ

  ##### 示例值：

```
"direct"
```

  #### Mac 信息和设置
  
  - 首选项项名称：ProxyMode
  - 示例值：
``` xml
<string>direct</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ProxyPacUrl

  #### 设置代理 .pac 文件 URL（已弃用）

  >已弃用：此策略已弃用。 当前受支持，但将在未来的版本中弃用。
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  此策略已弃用，改为使用[ProxySettings](#proxysettings)。 它在 Microsoft Edge 版本 91 中将不起作用。

指定代理自动配置 (PAC) 文件的 URL。

仅当未指定 [ProxySettings](#proxysettings) 策略，并且已在 [ProxyMode](#proxymode) 策略中选择 pac_script 时，才会应用此策略。 如果选择了其他任何模式来配置代理策略，请不要启用或配置此策略。

如果启用此策略，则可以指定 PAC 文件的 URL，该 URL 定义浏览器如何自动选择用于获取特定网站的相应代理服务器。

如果禁用或未配置此策略，则不指定 PAC 文件。 如果已指定任何其他设置代理策略的方法，请将此策略保留为未配置。

有关详细示例，请参阅 [https://go.microsoft.com/fwlink/?linkid=2094936](https://go.microsoft.com/fwlink/?linkid=2094936)。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ProxyPacUrl
  - GP 名称：设置代理 .pac 文件 URL（已弃用）
  - GP 路径（强制）：管理模板/Microsoft Edge/代理服务器
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ProxyPacUrl
  - 值类型：REG_SZ

  ##### 示例值：

```
"https://internal.contoso.com/example.pac"
```

  #### Mac 信息和设置
  
  - 首选项项名称：ProxyPacUrl
  - 示例值：
``` xml
<string>https://internal.contoso.com/example.pac</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ProxyServer

  #### 配置代理服务器的地址或 URL

  >已弃用：此策略已弃用。 当前受支持，但将在未来的版本中弃用。
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  此策略已弃用，改为使用[ProxySettings](#proxysettings)。 它在 Microsoft Edge 版本 91 中将不起作用。

指定代理服务器的 URL。

仅当未指定 [ProxySettings](#proxysettings) 策略，并且已在 [ProxyMode](#proxymode) 策略中选择 fixed_servers 时，才会应用此策略。 如果选择了其他任何模式来配置代理策略，请不要启用或配置此策略。

如果启用此策略，则此策略配置的代理服务器将用于所有 URL。

如果禁用或未配置此策略，用户可以在此代理模式下选择自己的代理设置。 如果已指定任何其他设置代理策略的方法，请将此策略保留为未配置。

有关更多选项和详细示例，请参阅 [https://go.microsoft.com/fwlink/?linkid=2094936](https://go.microsoft.com/fwlink/?linkid=2094936)。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ProxyServer
  - GP 名称：配置代理服务器的地址或 URL（已弃用）
  - GP 路径（强制）：管理模板/Microsoft Edge/代理服务器
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ProxyServer
  - 值类型：REG_SZ

  ##### 示例值：

```
"123.123.123.123:8080"
```

  #### Mac 信息和设置
  
  - 首选项项名称：ProxyServer
  - 示例值：
``` xml
<string>123.123.123.123:8080</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ProxySettings

  #### 代理设置

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  配置 Microsoft Edge 的代理设置。

如果启用此策略，Microsoft Edge 将忽略从命令行指定的所有与代理相关的选项。

如果未配置此策略，用户可选择自己的代理设置。

此策略将替代以下各个策略：

[ProxyMode](#proxymode)
[ProxyPacUrl](#proxypacurl)
[ProxyServer](#proxyserver)
[ProxyBypassList](#proxybypasslist)

将 [ProxySettings](#proxysettings) 策略设置为 "接受以下字段"：
  * ProxyMode，可指定 Microsoft Edge 使用的代理服务器，并阻止用户更改代理设置。
  * ProxyPacUrl, 代理 .pac 文件的 URL
  * ProxyServer, 代理服务器的 URL
  * ProxyBypassList, Microsoft Edge 跳过的代理主机列表。

对于 "ProxyMode"，如果你选择值：
  * direct, 永远不会使用代理，并且忽略所有其他字段。
  * system, 将使用系统的代理，并且忽略所有其他字段。
  * auto_detect，将忽略所有其他字段。
  * fixed_server，将使用 "ProxyServer" 和 "ProxyBypassList" 字段。
  * pac_script，将使用 "ProxyServer" 和 "ProxyBypassList" 字段。

有关更多详细示例，请转到 [https://go.microsoft.com/fwlink/?linkid=2094936](https://go.microsoft.com/fwlink/?linkid=2094936)。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - Dictionary

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ProxySettings
  - GP 名称：代理设置
  - GP 路径（强制）：管理模板/Microsoft Edge/代理服务器
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ProxySettings
  - 值类型：REG_SZ

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\ProxySettings = {
  "ProxyBypassList": "https://www.example1.com,https://www.example2.com,https://internalsite/", 
  "ProxyMode": "direct", 
  "ProxyPacUrl": "https://internal.site/example.pac", 
  "ProxyServer": "123.123.123.123:8080"
}
```

  ##### 精简示例值：

  ```
  SOFTWARE\Policies\Microsoft\Edge\ProxySettings = {"ProxyBypassList": "https://www.example1.com,https://www.example2.com,https://internalsite/", "ProxyMode": "direct", "ProxyPacUrl": "https://internal.site/example.pac", "ProxyServer": "123.123.123.123:8080"}
  ```
  

  #### Mac 信息和设置
  
  - 首选项项名称：ProxySettings
  - 示例值：
``` xml
<key>ProxySettings</key>
<dict>
  <key>ProxyBypassList</key>
  <string>https://www.example1.com,https://www.example2.com,https://internalsite/</string>
  <key>ProxyMode</key>
  <string>direct</string>
  <key>ProxyPacUrl</key>
  <string>https://internal.site/example.pac</string>
  <key>ProxyServer</key>
  <string>123.123.123.123:8080</string>
</dict>
```
  

  [返回页首](#microsoft-edge---policies)

  ## SmartScreen 设置策略

  [返回页首](#microsoft-edge---policies)

  ### PreventSmartScreenPromptOverride

  #### 阻止跳过 Microsoft Defender SmartScreen 有关网站的提示

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  通过此策略设置，可决定用户是否能替代有关潜在恶意网站的 Microsoft Defender SmartScreen 警告。

如果启用此设置，则用户不能忽略 Microsoft Defender SmartScreen 警告，并且无法继续访问该网站。

如果禁用或未配置此设置，则用户可以忽略 Microsoft Defender SmartScreen 警告，并且能继续访问该网站。

此策略仅在加入 Microsoft Active Directory 域的 Windows 实例、已注册设备管理的 Windows 10 专业版或企业版实例，或者通过 MDM 托管或通过 MCX 加入域的 macOS 实例上可用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：PreventSmartScreenPromptOverride
  - GP 名称：阻止跳过 Microsoft Defender SmartScreen 有关网站的提示
  - GP 路径（强制）：管理模板/Microsoft Edge/SmartScreen 设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：PreventSmartScreenPromptOverride
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：PreventSmartScreenPromptOverride
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### PreventSmartScreenPromptOverrideForFiles

  #### 阻止跳过 Microsoft Defender SmartScreen 有关下载的警告

  
  
  #### 支持的版本：

  - 在 Windows 上自 77 或更高版本起
  - 在 macOS 上自 79 或更高版本起

  #### 描述

  通过此策略，可决定用户是否能替代有关未验证下载的 Microsoft Defender SmartScreen 警告。

如果启用此策略，则你组织中的用户不能忽略 Microsoft Defender SmartScreen 警告，并且无法完成未经验证的下载。

如果禁用或未配置此策略，则用户可以忽略 Microsoft Defender SmartScreen 警告并完成未经验证的下载。

此策略仅在加入 Microsoft Active Directory 域的 Windows 实例、已注册设备管理的 Windows 10 专业版或企业版实例，或者通过 MDM 托管或通过 MCX 加入域的 macOS 实例上可用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：PreventSmartScreenPromptOverrideForFiles
  - GP 名称：阻止跳过 Microsoft Defender SmartScreen 有关下载的警告
  - GP 路径（强制）：管理模板/Microsoft Edge/SmartScreen 设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：PreventSmartScreenPromptOverrideForFiles
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：PreventSmartScreenPromptOverrideForFiles
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SmartScreenAllowListDomains

  #### 配置 Microsoft Defender SmartScreen 无法为其触发警告的域列表

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  配置 Microsoft Defender SmartScreen 受信任域列表。 这意味着：如果源 URL 与这些域匹配，Microsoft Defender SmartScreen 将不会检查潜在的恶意资源（如钓鱼软件和其他恶意软件）。
Microsoft Defender SmartScreen 下载保护服务不会检查这些域上托管的下载。

如果启用此策略，Microsoft Defender SmartScreen 将信任这些域。
如果禁用或未设置此策略，则默认 Microsoft Defender SmartScreen 保护将应用于所有资源。

此策略仅在加入 Microsoft Active Directory 域的 Windows 实例、已注册设备管理的 Windows 10 专业版或企业版实例，或者通过 MDM 托管或通过 MCX 加入域的 macOS 实例上可用。
另请注意，如果你的组织启用了 Microsoft Defender 高级威胁防护，则此策略不适用。 必须在 Microsoft Defender 安全中心中配置允许和阻止列表。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SmartScreenAllowListDomains
  - GP 名称：配置 Microsoft Defender SmartScreen 无法为其触发警告的域列表
  - GP 路径（强制）：管理模板/Microsoft Edge/SmartScreen 设置
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\SmartScreenAllowListDomains
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\SmartScreenAllowListDomains\1 = "mydomain.com"
SOFTWARE\Policies\Microsoft\Edge\SmartScreenAllowListDomains\2 = "myuniversity.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：SmartScreenAllowListDomains
  - 示例值：
``` xml
<array>
  <string>mydomain.com</string>
  <string>myuniversity.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SmartScreenEnabled

  #### 配置 Microsoft Defender SmartScreen

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  通过此策略设置，可配置是否打开 Microsoft Defender SmartScreen。 Microsoft Defender SmartScreen 可提供警告消息，帮助保护你的员工免受潜在钓鱼欺诈和恶意软件的侵害。 默认情况下，Microsoft Defender SmartScreen 处于打开状态。

如果启用此设置，Microsoft Defender SmartScreen 将打开。

如果禁用此设置，Microsoft Defender SmartScreen 将关闭。

如果未配置此设置，则用户可以选择是否使用 Microsoft Defender SmartScreen。

此策略仅在加入 Microsoft Active Directory 域的 Windows 实例、已注册设备管理的 Windows 10 专业版或企业版实例，或者通过 MDM 托管或通过 MCX 加入域的 macOS 实例上可用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SmartScreenEnabled
  - GP 名称：配置 Microsoft Defender SmartScreen
  - GP 路径（强制）：管理模板/Microsoft Edge/SmartScreen 设置
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/SmartScreen 设置
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：SmartScreenEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：SmartScreenEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SmartScreenForTrustedDownloadsEnabled

  #### 强制 Microsoft Defender SmartScreen 检查从受信任来源下载的内容

  
  
  #### 支持的版本：

  - 在 Windows 上自 78 或更高版本起

  #### 描述

  通过此策略设置，可配置 Microsoft Defender SmartScreen 是否检查受信任来源的下载信誉。

如果启用或未配置此设置，无论来源如何，Microsoft Defender SmartScreen 都会检查下载信誉。

如果禁用此设置，Microsoft Defender SmartScreen 在从受信任来源下载时不会检查下载内容的信誉。

此策略仅在加入 Microsoft Active Directory 域的 Windows 实例或者已注册设备管理的 Windows 10 专业版或企业版实例上可用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SmartScreenForTrustedDownloadsEnabled
  - GP 名称：强制 Microsoft Defender SmartScreen 检查从受信任来源下载的内容
  - GP 路径（强制）：管理模板/Microsoft Edge/SmartScreen 设置
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/SmartScreen 设置
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：SmartScreenForTrustedDownloadsEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  

  [返回页首](#microsoft-edge---policies)

  ### SmartScreenPuaEnabled

  #### 配置 Microsoft Defender SmartScreen 以阻止可能不需要的应用

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 80 或更高版本起

  #### 描述

  通过此策略设置，可配置是否允许使用 Microsoft Defender SmartScreen 阻止可能不需要的应用。 使用 Microsoft Defender SmartScreen 阻止可能不需要的应用时，将提供警告消息来帮助保护用户防范广告软件、硬币矿工、捆绑件和网站托管的其他低声誉应用。 默认情况下，将禁止使用 Microsoft Defender SmartScreen 阻止可能不需要的应用。

如果启用此设置，则将允许使用 Microsoft Defender SmartScreen 阻止可能不需要的应用。

如果禁用此设置，则将禁止使用 Microsoft Defender SmartScreen 阻止可能不需要的应用。

如果未配置此设置，则用户可选择是否使用 Microsoft Defender SmartScreen 阻止可能不需要的应用。

此策略仅在加入 Microsoft Active Directory 域的 Windows 实例、已注册设备管理的 Windows 10 专业版或企业版实例，或者通过 MDM 托管或通过 MCX 加入域的 macOS 实例上可用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SmartScreenPuaEnabled
  - GP 名称：配置 Microsoft Defender SmartScreen 以阻止可能不需要的应用
  - GP 路径（强制）：管理模板/Microsoft Edge/SmartScreen 设置
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/SmartScreen 设置
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：SmartScreenPuaEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：SmartScreenPuaEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ## 启动&comma;、主页和新选项卡页

  [返回页首](#microsoft-edge---policies)

  ### HomepageIsNewTabPage

  #### 将新选项卡页设置为主页

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  在 Microsoft Edge 中配置默认主页。 可将主页设置为你指定的 URL 或新选项卡页。

如果启用此策略，则新选项卡页将始终用于主页，并且将忽略主页 URL 位置。

如果禁用此策略，则用户的主页不能是新选项卡页，除非 URL 设置为“edge://newtab”。

如果未配置，用户可以选择新选项卡页是否作为其主页。

此策略仅在加入 Microsoft Active Directory 域的 Windows 实例、已注册设备管理的 Windows 10 专业版或企业版实例，或者通过 MDM 托管或通过 MCX 加入域的 macOS 实例上可用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：HomepageIsNewTabPage
  - GP 名称：将新选项卡页设置为主页
  - GP 路径（强制）：管理模板/Microsoft Edge/启动、主页和新选项卡页
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/启动、主页和新选项卡页
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：HomepageIsNewTabPage
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：HomepageIsNewTabPage
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### HomepageLocation

  #### 配置主页 URL

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  在 Microsoft Edge 中配置默认主页 URL。

主页是通过“主页”按钮打开的页面。 启动时打开的页面由 [RestoreOnStartup](#restoreonstartup) 策略控制。

可在此处设置 URL，也可以设置主页以打开新选项卡页。 如果选择打开新选项卡页，则此策略不会生效。

如果启用此策略，则用户不能更改其主页 URL，但他们可以选择使用新选项卡页作为其主页。

如果禁用或未配置此策略，则只要未启用 [HomepageIsNewTabPage](#homepageisnewtabpage) 策略，用户就可以选择自己的主页。

此策略仅在加入 Microsoft Active Directory 域的 Windows 实例、已注册设备管理的 Windows 10 专业版或企业版实例，或者通过 MDM 托管或通过 MCX 加入域的 macOS 实例上可用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：HomepageLocation
  - GP 名称：配置主页 URL
  - GP 路径（强制）：管理模板/Microsoft Edge/启动、主页和新选项卡页
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/启动、主页和新选项卡页
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：HomepageLocation
  - 值类型：REG_SZ

  ##### 示例值：

```
"https://www.contoso.com"
```

  #### Mac 信息和设置
  
  - 首选项项名称：HomepageLocation
  - 示例值：
``` xml
<string>https://www.contoso.com</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### NewTabPageAllowedBackgroundTypes

  #### 配置新选项卡页面布局允许使用的背景类型

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 86 或更高版本起

  #### 描述

  可在 Microsoft Edge 中的新选项卡页面布局上配置允许使用的背景图像类型。

如果未配置此策略，则将启用新选项卡页面上的所有背景图像类型。

策略选项映射：

* DisableImageOfTheDay (1) = 禁用每日背景图像类型

* DisableCustomImage (2) = 禁用自定义背景图像类型

* DisableAll (3) = 禁用所有背景图像类型

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称： NewTabPageAllowedBackgroundTypes
  - GP 名称：配置新选项卡页面布局允许使用的背景类型
  - GP 路径（强制）：管理模板/Microsoft Edge/启动、主页和新选项卡页
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：NewTabPageAllowedBackgroundTypes
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000002
```

  #### Mac 信息和设置
  
  - 首选项名称： NewTabPageAllowedBackgroundTypes
  - 示例值：
``` xml
<integer>2</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### NewTabPageCompanyLogo

  #### 设置新选项卡页公司徽标（已过时）

  
  >已过时：该策略已过时，Microsoft Edge 版本 85 后将无法正常工作。
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 79 起至 85

  #### 描述

  由于操作要求的更改，此策略未按预期工作。 因此，它已过时，不应使用。

指定要在 Microsoft Edge 的新选项卡页上使用的公司徽标。

该策略应配置为以 JSON 格式表示徽标的字符串。 例如：{ "default_logo": { "url": "https://www.contoso.com/logo.png", "hash": "cd0aa9856147b6c5b4ff2b7dfee5da20aa38253099ef1b4a64aced233c9afe29" }, "light_logo": { "url": "https://www.contoso.com/light_logo.png", "hash": "517d286edb416bb2625ccfcba9de78296e90da8e32330d4c9c8275c4c1c33737" } }

可通过指定 Microsoft Edge 可从中下载徽标的 URL 及其加密哈希 (SHA-256)（用于验证下载的完整性）来配置此策略。 徽标必须为 PNG 或 SVG 格式，其文件大小不得超过 16 MB。 徽标会下载并缓存，并且只要 URL 或哈希发生更改就会重新下载。 该 URL 必须无需任何身份验证即可访问。

“default_logo”是必需的，将在没有背景图像时使用。 如果提供了“light_logo”，则当用户的新选项卡页具有背景图像时，将使用它。 建议使用带左对齐且垂直居中的透明背景的水平徽标。 徽标的最小高度应为 32 像素，宽高比应为 1:1 至 4:1。 “default_logo”应与白色/黑色背景有适当的对比度，而“light_logo”应与背景图像有适当的对比度。

如果启用此策略，Microsoft Edge 将下载并在新选项卡页上显示指定的徽标。 用户不能替代或隐藏徽标。

如果禁用或未配置此策略，Microsoft Edge 不会在新选项卡页上显示公司徽标或 Microsoft 徽标。

有关确定 SHA-256 哈希的帮助，请参阅 https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-filehash。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - Dictionary

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：NewTabPageCompanyLogo
  - GP 名称：设置新选项卡页公司徽标（已过时）
  - GP 路径（强制）：管理模板/Microsoft Edge/启动、主页和新选项卡页
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：NewTabPageCompanyLogo
  - 值类型：REG_SZ

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\NewTabPageCompanyLogo = {
  "default_logo": {
    "hash": "cd0aa9856147b6c5b4ff2b7dfee5da20aa38253099ef1b4a64aced233c9afe29", 
    "url": "https://www.contoso.com/logo.png"
  }, 
  "light_logo": {
    "hash": "517d286edb416bb2625ccfcba9de78296e90da8e32330d4c9c8275c4c1c33737", 
    "url": "https://www.contoso.com/light_logo.png"
  }
}
```

  ##### 精简示例值：

  ```
  SOFTWARE\Policies\Microsoft\Edge\NewTabPageCompanyLogo = {"default_logo": {"hash": "cd0aa9856147b6c5b4ff2b7dfee5da20aa38253099ef1b4a64aced233c9afe29", "url": "https://www.contoso.com/logo.png"}, "light_logo": {"hash": "517d286edb416bb2625ccfcba9de78296e90da8e32330d4c9c8275c4c1c33737", "url": "https://www.contoso.com/light_logo.png"}}
  ```
  

  #### Mac 信息和设置
  
  - 首选项项名称：NewTabPageCompanyLogo
  - 示例值：
``` xml
<key>NewTabPageCompanyLogo</key>
<dict>
  <key>default_logo</key>
  <dict>
    <key>hash</key>
    <string>cd0aa9856147b6c5b4ff2b7dfee5da20aa38253099ef1b4a64aced233c9afe29</string>
    <key>url</key>
    <string>https://www.contoso.com/logo.png</string>
  </dict>
  <key>light_logo</key>
  <dict>
    <key>hash</key>
    <string>517d286edb416bb2625ccfcba9de78296e90da8e32330d4c9c8275c4c1c33737</string>
    <key>url</key>
    <string>https://www.contoso.com/light_logo.png</string>
  </dict>
</dict>
```
  

  [返回页首](#microsoft-edge---policies)

  ### NewTabPageHideDefaultTopSites

  #### 从新选项卡页隐藏默认热门网站

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  从 Microsoft Edge 中的新选项卡页隐藏默认热门网站。

如果将此策略设置为 true，则默认热门网站磁贴将隐藏。

如果将此策略设置为 false 或未配置它，则默认热门网站磁贴将保持可见。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：NewTabPageHideDefaultTopSites
  - GP 名称：从新选项卡页隐藏默认热门网站
  - GP 路径（强制）：管理模板/Microsoft Edge/启动、主页和新选项卡页
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：NewTabPageHideDefaultTopSites
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：NewTabPageHideDefaultTopSites
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### NewTabPageLocation

  #### 配置新选项卡页 URL

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  配置新选项卡页的默认 URL。

此策略确定创建新选项卡时打开的页面（包括打开新窗口时）。 如果启动页设置为打开新选项卡页，则该策略也会影响启动页。

此策略不确定启动时打开哪个页面；它由 [RestoreOnStartup](#restoreonstartup) 策略控制。 如果该策略设置为打开新选项卡页，则不会影响主页。

如果未配置此策略，则将使用默认新选项卡页。

如果配置此策略*和* [NewTabPageSetFeedType](#newtabpagesetfeedtype) 策略，则此策略优先。

如果提供了无效的 URL，则新选项卡将打开 about://blank。

此策略仅在加入 Microsoft Active Directory 域的 Windows 实例、已注册设备管理的 Windows 10 专业版或企业版实例，或者通过 MDM 托管或通过 MCX 加入域的 macOS 实例上可用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：NewTabPageLocation
  - GP 名称：配置新选项卡页 URL
  - GP 路径（强制）：管理模板/Microsoft Edge/启动、主页和新选项卡页
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/启动、主页和新选项卡页
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：NewTabPageLocation
  - 值类型：REG_SZ

  ##### 示例值：

```
"https://www.fabrikam.com"
```

  #### Mac 信息和设置
  
  - 首选项项名称：NewTabPageLocation
  - 示例值：
``` xml
<string>https://www.fabrikam.com</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### NewTabPageManagedQuickLinks

  #### 设置新选项卡页快速链接

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 79 或更高版本起

  #### 描述

  默认情况下，Microsoft Edge 会根据浏览历史记录，从用户添加的快捷方式和热门网站在新选项卡页上显示快速链接。 使用此策略，可在新选项卡页上配置最多三个快速链接磁贴，以 JSON 对象表示：

[ { "url": "https://www.contoso.com", "title": "Contoso Portal", "pinned": true/false }, ... ]

“url”字段为必填项；“title”和“pined”是可选的。 如果未提供“title”，则使用 URL 作为默认标题。 如果未提供“pinned”，则默认值为 false。

Microsoft Edge 将按列出的顺序从左到右显示这些磁贴，并显示所有固定的磁贴，但不显示未固定的磁贴。

如果该策略设置为强制，则将忽略“pinned”字段，并且将固定所有磁贴。 用户不能删除磁贴，并且磁贴始终显示在快速链接列表的前面。

如果该策略设置为推荐，则固定的磁贴将保留在列表中，但用户能够编辑和删除它们。 未固定的快速链接磁贴的行为与默认热门网站类似，如果其他网站访问频率更高，则这些磁贴会被推离列表。 通过此策略将未固定的链接应用到现有浏览器配置文件时，可能根本不会显示链接，具体取决于它们与用户浏览历史记录相比的排名。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - Dictionary

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：NewTabPageManagedQuickLinks
  - GP 名称：设置新选项卡页快速链接
  - GP 路径（强制）：管理模板/Microsoft Edge/启动、主页和新选项卡页
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/启动、主页和新选项卡页
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：NewTabPageManagedQuickLinks
  - 值类型：REG_SZ

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\NewTabPageManagedQuickLinks = [
  {
    "pinned": true, 
    "title": "Contoso Portal", 
    "url": "https://contoso.com"
  }, 
  {
    "title": "Fabrikam", 
    "url": "https://fabrikam.com"
  }
]
```

  ##### 精简示例值：

  ```
  SOFTWARE\Policies\Microsoft\Edge\NewTabPageManagedQuickLinks = [{"pinned": true, "title": "Contoso Portal", "url": "https://contoso.com"}, {"title": "Fabrikam", "url": "https://fabrikam.com"}]
  ```
  

  #### Mac 信息和设置
  
  - 首选项项名称：NewTabPageManagedQuickLinks
  - 示例值：
``` xml
<key>NewTabPageManagedQuickLinks</key>
<array>
  <dict>
    <key>pinned</key>
    <true/>
    <key>title</key>
    <string>Contoso Portal</string>
    <key>url</key>
    <string>https://contoso.com</string>
  </dict>
  <dict>
    <key>title</key>
    <string>Fabrikam</string>
    <key>url</key>
    <string>https://fabrikam.com</string>
  </dict>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### NewTabPagePrerenderEnabled

  #### 启用新选项卡页面的预加载，以便快速呈现

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 85 或更高版本起

  #### 描述

  如果配置了此策略，将启用预加载新选项卡页面，并且用户无法更改此设置。 如果不配置此策略，将启用预加载，用户可更改此设置。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称： NewTabPagePrerenderEnabled
  - GP 名称：启用新选项卡页面的预加载，以便快速呈现
  - GP 路径（强制）：管理模板/Microsoft Edge/启动、主页和新选项卡页
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/启动、主页和新选项卡页
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称： NewTabPagePrerenderEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选参数名称： NewTabPagePrerenderEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### NewTabPageSetFeedType

  #### 配置 Microsoft Edge 新建标签页体验（已弃用）

  >已弃用：此策略已弃用。 当前受支持，但将在未来的版本中弃用。
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 79 或更高版本起

  #### 描述

  我们将弃用此策略，因为新版的企业版新建标签页不再需要在不同内容类型之间进行选择。 实际上，可以通过 Microsoft 365 管理中心来控制向用户呈现的内容。 若要访问 Microsoft 365 管理中心，请使用管理员帐户登录 https://admin.microsoft.com。 在 Microsoft Edge 版本 90 后，此策略将弃用。

允许你为新选项卡页选择 Microsoft 资讯或 Office 365 源体验。

当将此策略设置为 'News' 时，用户将在新选项卡页上看到 Microsoft 资讯源体验。

当将此策略设置为 'Office' 时，使用 Azure Active Directory 浏览器登录的用户将在新选项卡页上看到 Office 365 源体验。

如果禁用或未配置此策略：

- 使用 Azure Active Directory 浏览器登录的用户将获得 Office 365 新选项卡页源体验以及标准的新选项卡页源体验。

- 不使用 Azure Active Directory 浏览器登录的用户将看到标准的新选项卡页体验。

如果配置了此策略*和* [NewTabPageLocation](#newtabpagelocation) 策略，则 [NewTabPageLocation](#newtabpagelocation) 优先。

默认设置：禁用或未配置。

策略选项映射：

* News (0) = Microsoft 资讯源体验

* Office (1) = Office 365 源体验

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：NewTabPageSetFeedType
  - GP 名称：配置 Microsoft Edge 新建标签页体验（已弃用）
  - GP 路径（强制）：管理模板/Microsoft Edge/启动、主页和新选项卡页
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/启动、主页和新选项卡页
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：NewTabPageSetFeedType
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：NewTabPageSetFeedType
  - 示例值：
``` xml
<integer>0</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### RestoreOnStartup

  #### 启动时要执行的操作

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指定 Microsoft Edge 启动时的行为方式。

如果想要在启动时始终打开新选项卡，请选择 "RestoreOnStartupIsNewTabPage"。

如果要重新打开上次 Microsoft Edge 关闭时打开的 URL，请选择 'RestoreOnStartupIsLastSession'。 浏览会话将按原样还原。 请注意，此选项会禁用某些依赖会话或在退出时执行操作的设置（例如，退出时清除浏览数据或仅清除会话 Cookie）。

如果想要打开一组特定的 URL，请选择 "RestoreOnStartupIsURLs"。

禁用此设置等同于未配置此设置。 用户将能够在 Microsoft Edge 中对其进行更改。

此策略仅在加入 Microsoft Active Directory 域的 Windows 实例、已注册设备管理的 Windows 10 专业版或企业版实例，或者通过 MDM 托管或通过 MCX 加入域的 macOS 实例上可用。

策略选项映射：

* RestoreOnStartupIsNewTabPage (5) = 打开新选项卡

* RestoreOnStartupIsLastSession (1) = 还原上次会话

* RestoreOnStartupIsURLs (4) = 打开 URL 列表

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：RestoreOnStartup
  - GP 名称：启动时要执行的操作
  - GP 路径（强制）：管理模板/Microsoft Edge/启动、主页和新选项卡页
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/启动、主页和新选项卡页
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：RestoreOnStartup
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000004
```

  #### Mac 信息和设置
  
  - 首选项项名称：RestoreOnStartup
  - 示例值：
``` xml
<integer>4</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### RestoreOnStartupURLs

  #### 浏览器启动时要打开的网站

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指定浏览器启动时自动打开的网站列表。 如果未配置此策略，则启动时将不会打开任何网站。

只有当还将 [RestoreOnStartup](#restoreonstartup) 策略设置为“打开 URL 列表”(4) 时，此策略才起作用。

此策略仅在加入 Microsoft Active Directory 域的 Windows 实例、已注册设备管理的 Windows 10 专业版或企业版实例，或者通过 MDM 托管或通过 MCX 加入域的 macOS 实例上可用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：RestoreOnStartupURLs
  - GP 名称：浏览器启动时要打开的网站
  - GP 路径（强制）：管理模板/Microsoft Edge/启动、主页和新选项卡页
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/启动、主页和新选项卡页
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\RestoreOnStartupURLs
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended\RestoreOnStartupURLs
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\RestoreOnStartupURLs\1 = "https://contoso.com"
SOFTWARE\Policies\Microsoft\Edge\RestoreOnStartupURLs\2 = "https://www.fabrikam.com"

```

  #### Mac 信息和设置
  
  - 首选项项名称：RestoreOnStartupURLs
  - 示例值：
``` xml
<array>
  <string>https://contoso.com</string>
  <string>https://www.fabrikam.com</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ShowHomeButton

  #### 在工具栏上显示“主页”按钮

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  在 Microsoft Edge 工具栏上显示“主页”按钮。

启用此策略后可始终显示“主页”按钮。 如果禁用该策略，则从不显示该按钮。

如果未配置该策略，则用户可以选择是否显示“主页”按钮。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ShowHomeButton
  - GP 名称：在工具栏上显示“主页”按钮
  - GP 路径（强制）：管理模板/Microsoft Edge/启动、主页和新选项卡页
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/启动、主页和新选项卡页
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：ShowHomeButton
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ShowHomeButton
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ## 其他策略

  [返回页首](#microsoft-edge---policies)

  ### AddressBarMicrosoftSearchInBingProviderEnabled

  #### 在地址栏中启用 Microsoft 必应搜索建议

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 81 或更高版本起

  #### 描述

  当用户在地址栏中键入搜索字符串时，可在地址栏的建议列表中显示相关的 Microsoft 必应搜索建议。 如果启用或未配置此策略，则用户可以在 Microsoft Edge 地址栏建议列表中看到由 Microsoft 必应搜索提供支持的内部结果。 若要查看 Microsoft 必应搜索结果，用户必须使用其组织的 Azure AD 帐户登录到 Microsoft Edge。
如果禁用此策略，用户将无法在 Microsoft Edge 地址栏建议列表中看到内部结果。
如果启用了强制使用默认搜索提供程序的策略集（[DefaultSearchProviderEnabled](#defaultsearchproviderenabled)、[DefaultSearchProviderName](#defaultsearchprovidername) 和 [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl)），并且指定的搜索提供程序不是必应，则此策略不适用，并且地址栏的建议列表中将没有 Microsoft 必应搜索建议。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AddressBarMicrosoftSearchInBingProviderEnabled
  - GP 名称：在地址栏中启用 Microsoft 必应搜索建议
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：AddressBarMicrosoftSearchInBingProviderEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：AddressBarMicrosoftSearchInBingProviderEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AdsSettingForIntrusiveAdsSites

  #### 含侵扰广告的网站的广告设置

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 78 或更高版本起

  #### 描述

  控制是否在具有侵扰广告的网站上阻止广告。

策略选项映射：

* AllowAds (1) = 在所有网站上允许广告

* BlockAds (2) = 在含侵入式广告的网站上阻止广告。 （默认值）

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AdsSettingForIntrusiveAdsSites
  - GP 名称：含侵扰广告的网站的广告设置
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：AdsSettingForIntrusiveAdsSites
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：AdsSettingForIntrusiveAdsSites
  - 示例值：
``` xml
<integer>1</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AllowDeletingBrowserHistory

  #### 启用删除浏览器和下载历史记录

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  允许删除浏览器历史记录和下载历史记录，并阻止用户更改此设置。

请注意，即使禁用了此策略，也不能保证保留浏览和下载历史记录：用户可以直接编辑或删除历史记录数据库文件，浏览器本身也可以随时删除（根据有效期）或者存档任何或所有历史记录项目。

如果启用或未配置此策略，用户可以删除浏览和下载历史记录。

如果禁用此策略，用户将无法删除浏览和下载历史记录，并且历史记录同步将被禁用。

如果启用此策略，请不要启用 [ClearBrowsingDataOnExit](#clearbrowsingdataonexit) 策略，因为它们都处理数据删除。 如果同时启用两者，则 [ClearBrowsingDataOnExit](#clearbrowsingdataonexit) 策略优先并且会在 Microsoft Edge 关闭时删除所有数据，而不管此策略是如何配置的。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AllowDeletingBrowserHistory
  - GP 名称：启用删除浏览器和下载历史记录
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：AllowDeletingBrowserHistory
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：AllowDeletingBrowserHistory
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AllowFileSelectionDialogs

  #### 允许文件选择对话框

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  通过让 Microsoft Edge 显示文件选择对话框来允许访问本地文件。

如果启用或未配置此策略，用户可以正常打开文件选择对话框。

如果禁用此策略，则每当用户执行触发文件选择对话框的操作（如导入收藏夹、上传文件或保存链接）时，都会显示一条消息，并假定用户已在文件选择对话框中单击“取消”。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AllowFileSelectionDialogs
  - GP 名称：允许文件选择对话框
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：AllowFileSelectionDialogs
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：AllowFileSelectionDialogs
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AllowPopupsDuringPageUnload

  #### 允许页面在卸载期间显示弹出窗口

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 78 或更高版本起

  #### 描述

  通过此策略，管理员能够指定页面在其卸载期间显示弹出窗口。

当该策略设置为启用时，允许页面在卸载时显示弹出窗口。

当该策略设置为禁用或未设置时，不允许页面在卸载时显示弹出窗口。 这将遵循规范：https://html.spec.whatwg.org/#apis-for-creating-and-navigating-browsing-contexts-by-name)。

将来会删除此策略。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AllowPopupsDuringPageUnload
  - GP 名称：允许页面在卸载期间显示弹出窗口
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：AllowPopupsDuringPageUnload
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：AllowPopupsDuringPageUnload
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AllowSurfGame

  #### 允许冲浪游戏

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 83 或更高版本起

  #### 描述

  如果禁用此策略，则当设备脱机或用户导航到 edge://surf 时，用户将无法玩冲浪游戏。

如果启用或未配置此策略，则用户可以玩冲浪游戏。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AllowSurfGame
  - GP 名称：允许冲浪游戏
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：AllowSurfGame
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：AllowSurfGame
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AllowSyncXHRInPageDismissal

  #### 允许页面在页面关闭期间发送同步 XHR 请求（已弃用）

  >已弃用：此策略已弃用。 当前受支持，但将在未来的版本中弃用。
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 79 或更高版本起

  #### 描述

  此策略已弃用，因为它仅作为一种短期机制提供，目的是让企业能够在发现与不允许在页面关闭期间发送同步 XHR 请求的更改不兼容时有更多的时间来更新其 Web 内容。 在 Microsoft Edge version 88 将不起作用。

通过此策略，可指定页面能够在页面关闭期间发送同步 XHR 请求。

如果启用此策略，则页面可以在页面关闭期间发送同步 XHR 请求。

如果禁用此策略或未配置此策略，则不允许页面在页面关闭期间发送同步 XHR 请求。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AllowSyncXHRInPageDismissal
  - GP 名称：允许页面在页面关闭期间发送同步 XHR 请求（已弃用）
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：AllowSyncXHRInPageDismissal
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：AllowSyncXHRInPageDismissal
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AllowTokenBindingForUrls

  #### 配置 Microsoft Edge 将尝试与其建立令牌绑定的站点列表

  
  
  #### 支持的版本：

  - 在 Windows 上自 83 或更高版本起

  #### 描述

  为浏览器将尝试为其执行令牌绑定协议的网站配置 URL 模式列表。
对于此列表中的域，浏览器将在 TLS 握手中发送令牌绑定 ClientHello（请参阅 https://tools.ietf.org/html/rfc8472)）。
如果服务器做出有效的 ServerHello 响应，浏览器将在后续 https 请求上创建并发送令牌绑定消息。 有关详细信息，请参阅 https://tools.ietf.org/html/rfc8471。

如果此列表为空，则将禁用令牌绑定。

此策略仅在具有虚拟安全模式功能的 Windows 10 设备上可用。

从 Microsoft Edge 86 开始，此策略不再支持动态刷新。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AllowTokenBindingForUrls
  - GP 名称：配置 Microsoft Edge 将尝试与其建立令牌绑定的网站列表
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\AllowTokenBindingForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\AllowTokenBindingForUrls\1 = "mydomain.com"
SOFTWARE\Policies\Microsoft\Edge\AllowTokenBindingForUrls\2 = "[*.]mydomain2.com"
SOFTWARE\Policies\Microsoft\Edge\AllowTokenBindingForUrls\3 = "[*.].mydomain2.com"

```

  

  [返回页首](#microsoft-edge---policies)

  ### AllowTrackingForUrls

  #### 配置特定网站的跟踪防护例外

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 78 或更高版本起

  #### 描述

  配置排除在跟踪防护之外的 URL 模式列表。

如果配置此策略，则已配置的 URL 模式列表将被排除在跟踪防护之外。

如果未配置此策略，则所有网站都将使用“阻止跟踪用户的 Web 浏览活动”策略中的全局默认值（如果已设置）或用户的个人配置。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AllowTrackingForUrls
  - GP 名称：配置特定网站的跟踪防护例外
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\AllowTrackingForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\AllowTrackingForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\AllowTrackingForUrls\2 = "[*.]contoso.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：AllowTrackingForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AlternateErrorPagesEnabled

  #### 找不到网页时建议类似页面

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 80 或更高版本起

  #### 描述

  允许 Microsoft Edge 发布与 Web 服务的连接，以针对连接问题（如 DNS 错误）生成 URL 和搜索建议。

如果启用此策略，则将使用 Web 服务针对网络错误生成 URL 和搜索建议。

如果禁用此策略，则不会调用 Web 服务，并且将显示标准错误页。

如果未配置此策略，Microsoft Edge 将遵循 edge://settings/privacy 处“服务”下设置的用户首选项。
具体而言，有一个“**找不到网页时建议类似页面**开关，用户可以打开或关闭该开关。 请注意，如果启用此策略 (AlternateErrorPagesEnabled)，则找不到网页时建议类似页面设置将打开，但用户无法使用该开关更改设置。 如果禁用此策略，则找不到网页时建议类似页面设置将关闭，并且用户无法使用该开关更改设置。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AlternateErrorPagesEnabled
  - GP 名称：找不到网页时建议类似页面
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：AlternateErrorPagesEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：AlternateErrorPagesEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AlwaysOpenPdfExternally

  #### 始终在外部打开 PDF 文件

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  在 Microsoft Edge 中禁用内部 PDF 查看器。

如果启用此策略，则 Microsoft Edge 会将 PDF 文件视为下载，并允许用户使用默认应用程序打开它们。

如果未配置此策略或将其禁用，则 Microsoft Edge 将打开 PDF 文件（除非用户将其禁用）。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AlwaysOpenPdfExternally
  - GP 名称：始终在外部打开 PDF 文件
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：AlwaysOpenPdfExternally
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：AlwaysOpenPdfExternally
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AmbientAuthenticationInPrivateModesEnabled

  #### 为 InPrivate 和来宾配置文件启用环境身份验证

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 81 或更高版本起

  #### 描述

  配置此策略以对 Microsoft Edge 中的 InPrivate 和来宾配置文件允许/禁止环境身份验证。

环境身份验证是指在未通过 NTLM/Kerberos/协商质询/响应方案提供显式凭据时使用默认凭据进行的 http 身份验证。

如果将该策略设置为 RegularOnly，则只允许对常规会话进行环境身份验证。 不允许 InPrivate 和来宾会话进行环境身份验证。

如果将该策略设置为 InPrivateAndRegular，则允许对 InPrivate 和常规会话进行环境身份验证。 不允许来宾会话进行环境身份验证。

如果将该策略设置为 GuestAndRegular，则允许对来宾和常规会话进行环境身份验证。 不允许 InPrivate 会话进行环境身份验证

如果将该策略设置为 'All'，则允许对所有会话进行环境身份验证。

请注意，始终允许对常规配置文件进行环境身份验证。

在 Microsoft Edge 81 及更高版本中，如果未设置该策略，则仅对常规会话启用环境身份验证。

策略选项映射：

* RegularOnly (0) = 仅在常规会话中启用环境身份验证

* InPrivateAndRegular (1) = 在 InPrivate 和常规会话中启用环境身份验证

* GuestAndRegular (2) = 在来宾和常规会话中启用环境身份验证

* All (3) = 在常规、InPrivate 和来宾会话中启用环境身份验证

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AmbientAuthenticationInPrivateModesEnabled
  - GP 名称：为 InPrivate 和来宾配置文件启用环境身份验证
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：AmbientAuthenticationInPrivateModesEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：AmbientAuthenticationInPrivateModesEnabled
  - 示例值：
``` xml
<integer>0</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AppCacheForceEnabled

  #### 允许重新启用 AppCache 功能，即使因默认方式于关闭状态

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 84 或更高版本起

  #### 描述

  如果将此策略设置为 true，将启用 AppCache，即使 Microsoft Edge 中的 AppCache 默认情况下不可用也是如此。

如果将此策略设置为 false 或不对其进行设置，AppCache 将遵循 Microsoft Edge 的默认设置。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称： AppCacheForceEnabled
  - GP 名称：允许重新启用 AppCache 功能，即使它在默认情况下处于关闭状态
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称： AppCacheForceEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选参数名称： AppCacheForceEnabled
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ApplicationLocaleValue

  #### 设置应用程序区域设置

  
  
  #### 支持的版本：

  - 在 Windows 上自 77 或更高版本起

  #### 描述

  在 Microsoft Edge 中配置应用程序区域设置并阻止用户更改区域设置。

如果启用此策略，Microsoft Edge 将使用指定的区域设置。 如果配置的区域设置不受支持，则使用“en-US”。

如果禁用或未配置此设置，Microsoft Edge 将使用用户指定的首选区域设置（如果已配置）或回退区域设置“en-US”。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ApplicationLocaleValue
  - GP 名称：设置应用程序区域设置
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：ApplicationLocaleValue
  - 值类型：REG_SZ

  ##### 示例值：

```
"en"
```

  

  [返回页首](#microsoft-edge---policies)

  ### AudioCaptureAllowed

  #### 允许或阻止音频捕获

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  允许你设置是否提示用户授予网站对其音频捕获设备的访问权限。 此策略适用于除 [AudioCaptureAllowedUrls](#audiocaptureallowedurls) 列表中配置的 URL 之外的所有 URL。

如果启用或未配置此策略（默认设置），则系统会提示用户授予音频捕获访问权限，[AudioCaptureAllowedUrls](#audiocaptureallowedurls) 列表中的 URL 除外。 将在不提示的情况下向列出的这些 URL 授予访问权限。

如果禁用此策略，则系统不会提示用户，并且只有 [AudioCaptureAllowedUrls](#audiocaptureallowedurls) 中配置的 URL 能够访问音频捕获。

此策略影响所有类型的音频输入，而不仅仅是内置麦克风。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AudioCaptureAllowed
  - GP 名称：允许或阻止音频捕获
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：AudioCaptureAllowed
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：AudioCaptureAllowed
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AudioCaptureAllowedUrls

  #### 无需请求许可即可访问音频捕获设备的网站

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  根据 URL 模式指定无需请求用户许可即可使用音频捕获设备的网站。 此列表中的模式将与请求 URL 的安全源进行匹配。 如果二者相符，则自动向网站授予对音频捕获设备的访问权限。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AudioCaptureAllowedUrls
  - GP 名称：无需请求许可即可访问音频捕获设备的网站
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\AudioCaptureAllowedUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\AudioCaptureAllowedUrls\1 = "https://www.contoso.com/"
SOFTWARE\Policies\Microsoft\Edge\AudioCaptureAllowedUrls\2 = "https://[*.]contoso.edu/"

```

  #### Mac 信息和设置
  
  - 首选项项名称：AudioCaptureAllowedUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com/</string>
  <string>https://[*.]contoso.edu/</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AudioSandboxEnabled

  #### 允许运行音频沙盒

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 81 或更高版本起

  #### 描述

  此策略控制音频进程沙盒。

如果启用此策略，则音频进程运行时将通过沙盒进行屏蔽。

如果禁用此策略，则音频进程运行时不通过沙盒进行屏蔽，WebRTC 音频处理模块将在呈现器进程中运行。
这样，用户将面临与运行音频子系统时不通过沙盒进行屏蔽相关的安全风险。

如果未配置此策略，则将使用音频沙盒的默认配置，这可能因平台而异。

此策略旨在让企业在使用干扰沙盒的安全软件设置时可以灵活地禁用音频沙盒。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AudioSandboxEnabled
  - GP 名称：允许运行音频沙盒
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：AudioSandboxEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：AudioSandboxEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AutoImportAtFirstRun

  #### 首次运行时自动导入另一个浏览器的数据和设置

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  如果启用此策略，则指定浏览器中所有支持的数据类型和设置将在首次运行时以静默方式自动导入。 在首次运行体验期间，也将跳过导入部分。

无论此策略的值如何，Microsoft Edge 旧版中的浏览器数据将始终在首次运行时以静默方式迁移。

如果此策略设置为 'FromDefaultBrowser'，则将导入与受管理设备上的默认浏览器对应的数据类型。

如果受管理设备中不存在指定为此策略值的浏览器，Microsoft Edge 将直接跳过导入，而不会向用户发出任何通知。

如果将此策略设置为“DisabledAutoImport”，则将完全跳过首次运行体验的导入部分，Microsoft Edge 不会自动导入浏览器数据和设置。

如果此策略设置为 'FromInternetExplorer' 的值，则将从 Internet Explorer 导入以下数据类型：
1. 收藏夹或书签
2. 保存的密码
3. 搜索引擎
4. 浏览历史记录
5. 主页

如果此策略设置为 'FromGoogleChrome' 的值，则将从 Google Chrome 导入以下数据类型：
1. 收藏夹
2. 保存的密码
3. 地址等
4. 付款信息
5. 浏览历史记录
6. “设置”
7. 已固定和打开的选项卡
8. Extensions
9. Cookie

注意：有关从 Google Chrome 导入的内容的更多详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2120835](https://go.microsoft.com/fwlink/?linkid=2120835)

如果该策略设置 'FromSafari' 的值，则不再将用户数据导入 Microsoft Edge。 这是由于 Mac 上的完全磁盘访问工作方式造成的。
在 macOS Mojave 及更高版本上，再也不可能自动将 Safari 数据导入到 Microsoft Edge 中。

从 Microsoft Edge 83 版开始，如果此策略设置为 'FromMozillaFirefox' 的值，则将从 Mozilla Firefox 导入以下数据类型：
1. 收藏夹或书签
2. 保存的密码
3. 地址等
4. 浏览历史记录

如果要限制特定数据类型在受管理设备上导入，可以将此策略与其他策略搭配使用，例如 [ImportAutofillFormData](#importautofillformdata)、[ImportBrowserSettings](#importbrowsersettings)、[ImportFavorites](#importfavorites) 等。

策略选项映射：

* FromDefaultBrowser (0) = 自动从默认浏览器导入所有支持的数据类型和设置

* FromInternetExplorer (1) = 自动从 Internet Explorer 导入所有支持的数据类型和设置

* FromGoogleChrome (2) = 自动从 Google Chrome 导入所有支持的数据类型和设置

* FromSafari (3) = 自动从 Safari 导入所有支持的数据类型和设置

* DisabledAutoImport (4) = 禁用自动导入，并跳过首次运行体验的导入部分

* FromMozillaFirefox (5) = 自动从 Mozilla Firefox 导入所有支持的数据类型和设置

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AutoImportAtFirstRun
  - GP 名称：首次运行时自动导入另一个浏览器的数据和设置
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：AutoImportAtFirstRun
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000002
```

  #### Mac 信息和设置
  
  - 首选项项名称：AutoImportAtFirstRun
  - 示例值：
``` xml
<integer>2</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AutoLaunchProtocolsFromOrigins

  #### 定义可以从列出的源启动外部应用程序而不提示用户的协议列表

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 85 或更高版本起

  #### 描述

  允许你设置协议列表，并为每个协议设置允许的原始模式的关联列表，这样可以启动外部应用程序而不提示用户。 列表协议时，不应包括尾部分隔符。 例如，列出 "skype"，而不是"skype:"或 "skype://"。

如果配置了此策略，仅允许在未通过策略提示的情况下启动外部应用程序的协议，如：

- 已列出该协议

- 试图启动协议的站点的源匹配该协议的 allowed_origins 列表中的一个源模式。

如果任一条件为 false，则策略将不会忽略外部协议启动提示。

如果未配置此策略，则无需提示即可启动任何协议。 除非[ExternalProtocolDialogShowAlwaysOpenCheckbox](#externalprotocoldialogshowalwaysopencheckbox)策略被设置为禁用，否则用户可以根据每个协议/每个站点选择退出提示。 此策略对用户设置的每个协议/每个站点的提示豁免没有影响。

来源匹配模式使用与[URLBlocklist](#urlblocklist)策略类似的格式，这些格式被记录在[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)。

但是，此策略的原始匹配模式不能包含"/path" 或 "@query"元素。 包含"/path" 或 "@query"元素的任何模式都将被忽略。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - Dictionary

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称： AutoLaunchProtocolsFromOrigins
  - GP 名称：定义可从列出的源启动外部应用程序的协议的列表，而无需提示用户
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称： AutoLaunchProtocolsFromOrigins
  - 值类型：REG_SZ

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\AutoLaunchProtocolsFromOrigins = [
  {
    "allowed_origins": [
      "example.com", 
      "http://www.example.com:8080"
    ], 
    "protocol": "spotify"
  }, 
  {
    "allowed_origins": [
      "https://example.com", 
      "https://.mail.example.com"
    ], 
    "protocol": "teams"
  }, 
  {
    "allowed_origins": [
      "*"
    ], 
    "protocol": "outlook"
  }
]
```

  ##### 精简示例值：

  ```
  SOFTWARE\Policies\Microsoft\Edge\AutoLaunchProtocolsFromOrigins = [{"allowed_origins": ["example.com", "http://www.example.com:8080"], "protocol": "spotify"}, {"allowed_origins": ["https://example.com", "https://.mail.example.com"], "protocol": "teams"}, {"allowed_origins": ["*"], "protocol": "outlook"}]
  ```
  

  #### Mac 信息和设置
  
  - 首选参数名称： AutoLaunchProtocolsFromOrigins
  - 示例值：
``` xml
<key>AutoLaunchProtocolsFromOrigins</key>
<array>
  <dict>
    <key>allowed_origins</key>
    <array>
      <string>example.com</string>
      <string>http://www.example.com:8080</string>
    </array>
    <key>protocol</key>
    <string>spotify</string>
  </dict>
  <dict>
    <key>allowed_origins</key>
    <array>
      <string>https://example.com</string>
      <string>https://.mail.example.com</string>
    </array>
    <key>protocol</key>
    <string>teams</string>
  </dict>
  <dict>
    <key>allowed_origins</key>
    <array>
      <string>*</string>
    </array>
    <key>protocol</key>
    <string>outlook</string>
  </dict>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AutoOpenAllowedForURLs

  #### AutoOpenFileTypes 可应用的 URL

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 85 或更高版本起

  #### 描述

  [AutoOpenFileTypes](#autoopenfiletypes)将应用到的 URL 的列表。 该策略对用户通过下载架... > “总是打开这种类型的文件”菜单项自动打开的值没有影响。

如果在此策略中设置URL，则只有在URL是此策略的一部分并且文件类型在[AutoOpenFileTypes](#autoopenfiletypes)中列出时，策略才会自动打开文件。 如果任一条件为 false，则下载不会通过策略自动打开。

如果未设置此策略，则所有文件类型均位于[AutoOpenFileTypes](#autoopenfiletypes)中的下载将自动打开。

URL 模式必须按[https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)进行格式设置。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称： AutoOpenAllowedForURLs
  - GP 名称： AutoOpenFileTypes 可应用的 Url
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径(强制) :SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs\1 = "example.com"
SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs\2 = "https://ssl.server.com"
SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs\3 = "hosting.com/good_path"
SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs\4 = "https://server:8080/path"
SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs\5 = ".exact.hostname.com"

```

  #### Mac 信息和设置
  
  - 首选参数名称： AutoOpenAllowedForURLs
  - 示例值：
``` xml
<array>
  <string>example.com</string>
  <string>https://ssl.server.com</string>
  <string>hosting.com/good_path</string>
  <string>https://server:8080/path</string>
  <string>.exact.hostname.com</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AutoOpenFileTypes

  #### 在下载中应该自动打开的文件类型列表

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 85 或更高版本起

  #### 描述

  此策略设置一个文件类型列表，这些文件类型应该在下载时自动打开。 注意：在列出文件类型时，不应该包括前导分隔符，所以用 "txt" 代替".txt"。

默认情况下，这些文件类型将自动在所有 Url 上打开。 您可以使用[AutoOpenAllowedForURLs](#autoopenallowedforurls)策略来限制将自动打开这些文件类型的URL。

那些应该被自动打开的文件类型仍然会受制于启用的 Microsoft Defender SmartScreen 检查，如果检查失败就不会被打开。

用户已经指定自动打开的文件类型将在下载时继续打开。 用户将继续能够指定自动打开的其他文件类型。

如果没有设置此策略，则只有用户已经指定为自动打开的文件类型才会在下载时自动打开。

此策略仅在加入 Microsoft Active Directory 域的 Windows 实例、已注册设备管理的 Windows 10 专业版或企业版实例，或者通过 MDM 托管或通过 MCX 加入域的 macOS 实例上可用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称： AutoOpenFileTypes
  - GP 名称：下载时自动打开的文件类型列表
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径(强制): SOFTWARE\Policies\Microsoft\Edge\AutoOpenFileTypes
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\AutoOpenFileTypes\1 = "exe"
SOFTWARE\Policies\Microsoft\Edge\AutoOpenFileTypes\2 = "txt"

```

  #### Mac 信息和设置
  
  - 首选项名称： AutoOpenFileTypes
  - 示例值：
``` xml
<array>
  <string>exe</string>
  <string>txt</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AutofillAddressEnabled

  #### 启用地址自动填充

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  启用自动填充功能，让用户能够使用以前存储的信息自动填写 Web 表单中的地址信息。

如果禁用此策略，自动填充不会建议或填写地址信息，也不会保存用户在浏览 Web 时可能提交的其他地址信息。

如果启用或未配置此策略，用户可以在用户界面中控制地址的自动填充。

请注意，如果禁用此策略，则还会停止所有 Web 表单（付款和密码表单除外）的所有活动。 不会保存任何其他条目，并且 Microsoft Edge 不会建议或自动填充任何以前的条目。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AutofillAddressEnabled
  - GP 名称：启用地址自动填充
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：AutofillAddressEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：AutofillAddressEnabled
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AutofillCreditCardEnabled

  #### 启用信用卡自动填充

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  启用 Microsoft Edge 的自动填充功能，让用户能够使用以前存储的信息自动填写 Web 表单中的信用卡信息。

如果禁用此策略，则自动填充从不建议或填写信用卡信息，也不会保存用户在浏览 Web 时可能提交的其他信用卡信息。

如果启用或未配置此策略，则用户可以控制信用卡的自动填充。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AutofillCreditCardEnabled
  - GP 名称：启用信用卡自动填充
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：AutofillCreditCardEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：AutofillCreditCardEnabled
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### AutoplayAllowed

  #### 允许网站媒体自动播放

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 78 或更高版本起

  #### 描述

  此策略设置网站的媒体自动播放策略。

默认设置“未配置”遵循当前媒体自动播放设置，并允许用户配置其自动播放设置。

设置为“已启用”会将媒体自动播放设置为“允许”。  允许所有网站自动播放媒体。 用户不能替代此策略。

设置为“已禁用”会将媒体自动播放设置为“阻止”。  不允许任何网站自动播放媒体。 用户不能替代此策略。

需要关闭并重新打开一个选项卡，此策略才会生效。


  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：AutoplayAllowed
  - GP 名称：允许网站媒体自动播放
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：AutoplayAllowed
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：AutoplayAllowed
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### BackgroundModeEnabled

  #### Microsoft Edge 关闭后继续运行后台应用

  
  
  #### 支持的版本：

  - 在 Windows 上自 77 或更高版本起

  #### 描述

  允许 Microsoft Edge 进程在操作系统登录时启动，并在最后一个浏览器窗口关闭后继续运行。 在这种情况下，后台应用和当前浏览会话将保持活动状态，包括任何会话 Cookie。 打开的后台进程会在系统托盘中显示一个图标，并且始终可以从该处关闭。

如果启用此策略，后台模式将打开。

如果禁用此策略，后台模式将关闭。

如果未配置此策略，则后台模式最初将关闭，用户可以在 edge://settings/system 中配置其行为。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：BackgroundModeEnabled
  - GP 名称：Microsoft Edge 关闭后继续运行后台应用
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：BackgroundModeEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  

  [返回页首](#microsoft-edge---policies)

  ### BackgroundTemplateListUpdatesEnabled

  #### 对“集锦”和使用模板的其他功能启用可用模板列表后台更新

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 79 或更高版本起

  #### 描述

  允许你对“集锦”和使用模板的其他功能启用或禁用可用模板列表后台更新。  当页面保存到某个集锦时，可使用模板从网页中提取丰富的元数据。

如果启用或未配置该设置，则将每隔 24 小时在后台从 Microsoft 服务下载可用模板列表。

如果禁用此设置，则将按需下载可用模板列表。 此类下载可能会对“集锦”和其他功能造成较小的性能损失。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：BackgroundTemplateListUpdatesEnabled
  - GP 名称：对“集锦”和使用模板的其他功能启用可用模板列表后台更新
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：BackgroundTemplateListUpdatesEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：BackgroundTemplateListUpdatesEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### BingAdsSuppression

  #### 阻止必应搜索结果中的所有广告

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 83 或更高版本起

  #### 描述

  在 Bing.com 上启用无广告搜索体验

如果启用此策略，则用户可以在 bing.com 上搜索并享受无广告搜索体验。 同时，安全搜索设置将设置为“严格”，用户无法更改。

如果未配置此策略，则默认体验将在 bing.com 上的搜索结果中显示广告。 默认情况下，安全搜索将设置为“中等”，用户可以更改该设置。

此策略仅适用于 Microsoft 识别为 EDU 租户的 K-12 SKU。

请参阅 [https://go.microsoft.com/fwlink/?linkid=2119711](https://go.microsoft.com/fwlink/?linkid=2119711)，了解有关此策略的更多信息或者以下情形是否适用于你：

* 你有 EDU 租户，但该策略不起作用。

* 你的 IP 因具有无广告搜索体验而被列入白名单。

* 你曾在 Microsoft Edge 旧版上体验了无广告搜索体验，并希望升级到新版本的 Microsoft Edge。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：BingAdsSuppression
  - GP 名称：阻止必应搜索结果中的所有广告
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：BingAdsSuppression
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：BingAdsSuppression
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### BlockThirdPartyCookies

  #### 阻止第三方 Cookie

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  阻止非来自地址栏中域的网页元素设置 Cookie。

如果启用此策略，则非来自地址栏中域的网页元素不能设置 Cookie

如果禁用此策略，则来自地址栏以外的其他域的网页元素可以设置 Cookie。

如果未配置此策略，则会启用第三方 Cookie，但用户可以更改此设置。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：BlockThirdPartyCookies
  - GP 名称：阻止第三方 Cookie
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：BlockThirdPartyCookies
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：BlockThirdPartyCookies
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### BrowserAddProfileEnabled

  #### 允许从“标识”浮出控件或“设置”页面创建配置文件

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  允许用户使用“**添加配置文件**”选项创建新的配置文件。
如果启用或未配置此策略，Microsoft Edge 将允许用户使用“标识”浮出菜单或“设置”页面上的“**添加配置文件**”来创建新的配置文件。

如果禁用此策略，则用户无法从“标识”浮出菜单或“设置”页面添加新的配置文件。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：BrowserAddProfileEnabled
  - GP 名称：允许从“标识”浮出控件或“设置”页面创建配置文件
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：BrowserAddProfileEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：BrowserAddProfileEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### BrowserGuestModeEnabled

  #### 启用来宾模式

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  启用该选项以允许在 Microsoft Edge 中使用来宾配置文件。 在来宾配置文件中，浏览器不会从现有配置文件导入浏览数据，并且在所有来宾配置文件关闭时将删除浏览数据。

如果启用或未配置此策略，则 Microsoft Edge 将允许用户在来宾配置文件中浏览。

如果禁用此策略，Microsoft Edge 将不允许用户在来宾配置文件中浏览。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：BrowserGuestModeEnabled
  - GP 名称：启用来宾模式
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：BrowserGuestModeEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：BrowserGuestModeEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### BrowserNetworkTimeQueriesEnabled

  #### 允许向浏览器网络时间服务发送查询

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  阻止 Microsoft Edge 偶尔向浏览器网络时间服务发送查询以检索准确的时间戳。

如果禁用此策略，Microsoft Edge 将停止向浏览器网络时间服务发送查询。

如果启用或未配置此策略，Microsoft Edge 将偶尔向浏览器网络时间服务发送查询。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：BrowserNetworkTimeQueriesEnabled
  - GP 名称：允许向浏览器网络时间服务发送查询
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：BrowserNetworkTimeQueriesEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：BrowserNetworkTimeQueriesEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### BrowserSignin

  #### 浏览器登录设置

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指定用户是否可以使用其帐户登录到 Microsoft Edge 并使用与帐户相关的服务（如同步和单一登录）。 要控制同步的可用性，请改用 [SyncDisabled](#syncdisabled) 策略。

如果将此策略设置为“禁用”，请确保还将 [NonRemovableProfileEnabled](#nonremovableprofileenabled) 策略设置为禁用，因为 [NonRemovableProfileEnabled](#nonremovableprofileenabled) 禁止创建自动登录的浏览器配置文件。 如果同时设置了这两个策略，Microsoft Edge 将使用“禁用浏览器登录”策略，其行为将如同 [NonRemovableProfileEnabled](#nonremovableprofileenabled) 设置为禁用一样。

如果将此策略设置为“启用”，则用户可以登录到浏览器。 登录到浏览器并不意味着默认情况下启用同步；用户必须单独选择加入才能使用此功能。

如果将此策略设置为 'Force'，用户必须登录到配置文件才能使用浏览器。 默认情况下，这将允许用户选择是否要同步到其帐户，除非域管理员已禁用同步或使用了 [SyncDisabled](#syncdisabled) 策略。 [BrowserGuestModeEnabled](#browserguestmodeenabled) 策略的默认值设置为 false。

如果未配置此策略，则用户可以决定是否要启用浏览器登录选项并根据需要使用它。

策略选项映射：

* Disable (0) = 禁用浏览器登录

* Enable (1) = 启用浏览器登录

* Force (2) = 强制用户登录以使用浏览器

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：BrowserSignin
  - GP 名称：浏览器登录设置
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：BrowserSignin
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000002
```

  #### Mac 信息和设置
  
  - 首选项项名称：BrowserSignin
  - 示例值：
``` xml
<integer>2</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### BuiltInDnsClientEnabled

  #### 使用内置 DNS 客户端

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  控制是否使用内置 DNS 客户端。

这不会影响所使用的 DNS 服务器；只影响用于与它们通信的软件堆栈。 例如，如果操作系统配置为使用企业 DNS 服务器，则内置 DNS 客户端将使用同一服务器。 但是，内置 DNS 客户端可能会使用更现代的 DNS 相关协议（如 DNS-over-TLS）以不同方式对服务器进行寻址。

如果启用此策略，则使用内置 DNS 客户端（如果可用）。

如果禁用此策略，则从不使用该客户端。

如果未配置此策略，则默认情况下在 MacOS 上启用内置 DNS 客户端，并且用户可以通过编辑 edge://flags 或指定命令行标志来更改是否使用内置 DNS 客户端。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：BuiltInDnsClientEnabled
  - GP 名称：使用内置 DNS 客户端
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：BuiltInDnsClientEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：BuiltInDnsClientEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### BuiltinCertificateVerifierEnabled

  #### 确定是否将使用内置证书验证程序来验证服务器证书（已弃用）

  >已弃用：此策略已弃用。 当前受支持，但将在未来的版本中弃用。
  
  #### 支持的版本：

  - 在 macOS 上自 83 或更高版本起

  #### 描述

  此策略已弃用，因为它仅作为一种短期机制提供，目的是让企业能够在发现与内置证书验证程序不兼容时有更多的时间来更新环境和报告问题。

在 Microsoft Edge 版本 87 将不起作用，因此计划在 Mac OS X 中删除此策略。


  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  

  #### Mac 信息和设置
  
  - 首选项项名称：BuiltinCertificateVerifierEnabled
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### CertificateTransparencyEnforcementDisabledForCas

  #### 针对 SubjectPublicKeyInfo 哈希列表禁用证书透明度强制

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  禁止对 subjectPublicKeyInfo 哈希列表强制实施证书透明度要求。

通过此策略，可针对包含具有其中一个指定 subjectPublicKeyInfo 哈希的证书的证书链禁用证书透明度披露要求。 这样，由于未正确公开披露而不受信任的证书仍将用于企业主机。

要在设置此策略时禁止强制实施证书透明度，必须满足以下其中一组条件：
1. 哈希属于服务器证书的 subjectPublicKeyInfo。
2. 哈希属于出现在证书链中某个 CA 证书中的 subjectPublicKeyInfo；该 CA 证书受 X.509v3 nameConstraints 扩展约束；permittedSubtrees 中存在一个或多个 DdirectoryName nameConstraint；DirectoryName 包含 organizationName 属性。
3. 哈希属于出现在证书链中某个 CA 证书中的 subjectPublicKeyInfo；CA 证书的证书使用者中具有一个或多个 organizationName 属性；服务器的证书包含数量相同且顺序一致的 organizationName 属性，并且每个字节的值都相同。

可通过将以下内容串联起来指定 subjectPublicKeyInfo 哈希：哈希算法名称、“/”字符以及哈希算法的 Base64 编码，该哈希算法应用于指定证书经过 DER 编码的 subjectPublicKeyInfo。 此 Base64 编码的格式与 SPKI 指纹相同，如 RFC 7469 第 2.4 节所定义。 无法识别的哈希算法将被忽略。 目前仅支持“sha256”哈希算法。

如果禁用或未配置此策略，则当需要通过证书透明度进行披露的任何证书未根据证书透明度策略进行披露时，将被视为不受信任。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：CertificateTransparencyEnforcementDisabledForCas
  - GP 名称：针对 SubjectPublicKeyInfo 哈希列表禁用证书透明度强制
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForCas
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForCas\1 = "sha256/AAAAAAAAAAAAAAAAAAAAAA=="
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForCas\2 = "sha256//////////////////////w=="

```

  #### Mac 信息和设置
  
  - 首选项项名称：CertificateTransparencyEnforcementDisabledForCas
  - 示例值：
``` xml
<array>
  <string>sha256/AAAAAAAAAAAAAAAAAAAAAA==</string>
  <string>sha256//////////////////////w==</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### CertificateTransparencyEnforcementDisabledForLegacyCas

  #### 针对旧证书颁发机构列表禁用证书透明度强制

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  禁止对旧证书颁发机构 (Cas) 列表强制实施证书透明度要求。

通过此策略，可针对包含具有其中一个指定 subjectPublicKeyInfo 哈希的证书的证书链禁用证书透明度披露要求。 这样，由于未正确公开披露而不受信任的证书将继续用于企业主机。

要禁用证书透明度强制实施，必须将哈希设置为出现在被识别为旧证书颁发机构 (CA) 的 CA 证书中的 SubjectPublicKeyInfo。 旧 CA 是默认情况下由 Microsoft Edge 支持的一个或多个操作系统公开信任的 CA。

可通过将以下内容串联起来指定 subjectPublicKeyInfo 哈希：哈希算法名称、“/”字符以及哈希算法的 Base64 编码，该哈希算法应用于指定证书经过 DER 编码的 subjectPublicKeyInfo。 此 Base64 编码的格式与 SPKI 指纹相同，如 RFC 7469 第 2.4 节所定义。 无法识别的哈希算法将被忽略。 目前仅支持“sha256”哈希算法。

如果未配置此策略，则当需要通过证书透明度进行披露的任何证书未根据证书透明度策略进行披露时，将被视为不受信任。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：CertificateTransparencyEnforcementDisabledForLegacyCas
  - GP 名称：针对旧证书颁发机构列表禁用证书透明度强制
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForLegacyCas
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForLegacyCas\1 = "sha256/AAAAAAAAAAAAAAAAAAAAAA=="
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForLegacyCas\2 = "sha256//////////////////////w=="

```

  #### Mac 信息和设置
  
  - 首选项项名称：CertificateTransparencyEnforcementDisabledForLegacyCas
  - 示例值：
``` xml
<array>
  <string>sha256/AAAAAAAAAAAAAAAAAAAAAA==</string>
  <string>sha256//////////////////////w==</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### CertificateTransparencyEnforcementDisabledForUrls

  #### 针对特定 URL 禁用证书透明度强制

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  禁止对列出的 URL 强制实施证书透明度要求。

通过此策略，可不通过证书透明度来披露指定 URL 中主机名的证书。 这样，你就可以使用由于未正确公开披露而不受信任的证书，但这会使得检测这些主机的错误颁发证书变得更加困难。

根据 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) 构建你的 URL 模式。 由于证书对给定主机名有效，与方案、端口或路径无关，因此仅考虑 URL 的主机名部分。 不支持通配符主机。

如果未配置此策略，则应通过证书透明度披露的任何证书如果未披露，则将被视为不受信任。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：CertificateTransparencyEnforcementDisabledForUrls
  - GP 名称：针对特定 URL 禁用证书透明度强制
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForUrls\1 = "contoso.com"
SOFTWARE\Policies\Microsoft\Edge\CertificateTransparencyEnforcementDisabledForUrls\2 = ".contoso.com"

```

  #### Mac 信息和设置
  
  - 首选项项名称：CertificateTransparencyEnforcementDisabledForUrls
  - 示例值：
``` xml
<array>
  <string>contoso.com</string>
  <string>.contoso.com</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ClearBrowsingDataOnExit

  #### 在 Microsoft Edge 关闭时清除浏览数据

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 78 或更高版本起

  #### 描述

  默认情况下，Microsoft Edge 关闭时不会清除浏览数据。 浏览数据包括在表单中输入的信息、密码乃至访问过的网站。

如果启用此策略，则每次 Microsoft Edge 关闭时都会删除所有浏览数据。 请注意，如果启用此策略，它将优先于 [DefaultCookiesSetting](#defaultcookiessetting) 的配置。

如果禁用或未配置此策略，用户可以在“设置”中配置“清除浏览数据”选项。

如果启用此策略，请不要配置 [AllowDeletingBrowserHistory](#allowdeletingbrowserhistory) 或 [ClearCachedImagesAndFilesOnExit](#clearcachedimagesandfilesonexit) 策略，因为它们都处理浏览数据删除。 如果配置了上述策略和此策略，则在 Microsoft Edge 关闭时，所有浏览数据都将被删除，而不管 [AllowDeletingBrowserHistory](#allowdeletingbrowserhistory) 或 [ClearCachedImagesAndFilesOnExit](#clearcachedimagesandfilesonexit) 的配置如何。

若要排除退出时删除 Cookie 的功能，请配置 [SaveCookiesOnExit](#savecookiesonexit) 策略。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ClearBrowsingDataOnExit
  - GP 名称：在 Microsoft Edge 关闭时清除浏览数据
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：ClearBrowsingDataOnExit
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ClearBrowsingDataOnExit
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ClearCachedImagesAndFilesOnExit

  #### 在 Microsoft Edge 关闭时清除缓存的图像和文件

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 83 或更高版本起

  #### 描述

  默认情况下，Microsoft Edge 关闭时不会清除缓存的图像和文件。

如果启用此策略，则每次 Microsoft Edge 关闭时，缓存的图像和文件都将被删除。

如果禁用此策略，用户将无法在 edge://settings/clearBrowsingDataOnClose 中配置缓存的图像和文件选项。

如果未配置此策略，用户可以选择是否在退出时清除缓存的图像和文件。

如果禁用此策略，请不要启用 [ClearBrowsingDataOnExit](#clearbrowsingdataonexit) 策略，因为它们都处理数据删除。 如果同时配置这两个策略，则 [ClearBrowsingDataOnExit](#clearbrowsingdataonexit) 策略优先并在 Microsoft Edge 关闭时删除所有数据，而不管 [ClearCacheedImagesAndFilesOnExit](#clearcachedimagesandfilesonexit) 的配置如何。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ClearCachedImagesAndFilesOnExit
  - GP 名称：在 Microsoft Edge 关闭时清除缓存的图像和文件
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：ClearCachedImagesAndFilesOnExit
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ClearCachedImagesAndFilesOnExit
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ClickOnceEnabled

  #### 允许用户使用 ClickOnce 协议打开文件

  
  
  #### 支持的版本：

  - 在 Windows 上自 78 或更高版本起

  #### 描述

  允许用户使用 ClickOnce 协议打开文件。 通过 ClickOnce 协议，网站可使用用户计算机或设备上的 ClickOnce 文件处理程序请求浏览器从特定 URL 打开文件。

如果启用此策略，用户可以使用 ClickOnce 协议打开文件。 此策略将替代 edge://flags/ 页面中用户的 ClickOnce 设置。

如果禁用此策略，用户将无法使用 ClickOnce 协议打开文件。 而是使用浏览器将文件保存到文件系统。 此策略将替代 edge://flags/ 页面中用户的 ClickOnce 设置。

如果未配置此策略，则默认情况下，拥有 Microsoft Edge 87 之前的 Microsoft Edge 版本的用户无法使用 ClickOnce 协议打开文件。 但是，他们可以选择允许将 ClickOnce 协议与 edge://flags/ 页面搭配使用。 默认情况下，拥有 Microsoft Edge 版本 87 和更高版本的用户可以使用 ClickOnce 协议打开文件，但可以选择使用 edge://flags/ 页面禁用 ClickOnce 协议。

禁用 ClickOnce 可能会导致 ClickOnce 应用程序（.application 文件）无法正常启动。

有关 ClickOnce 的详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2103872](https://go.microsoft.com/fwlink/?linkid=2103872) 和 [https://go.microsoft.com/fwlink/?linkid=2099880](https://go.microsoft.com/fwlink/?linkid=2099880)。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ClickOnceEnabled
  - GP 名称：允许用户使用 ClickOnce 协议打开文件
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ClickOnceEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  

  [返回页首](#microsoft-edge---policies)

  ### CollectionsServicesAndExportsBlockList

  #### 阻止访问指定服务列表及在集锦中导出目标

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 86 或更高版本起

  #### 描述

  在 Microsoft Edge 的“集锦”功能中列出用户无法访问的特定服务和导出目标。 这包括显示来自必应的其他数据，以及将集锦导出到 Microsoft 产品或外部合作伙伴。

如果启用此策略，将阻止与指定列表匹配的服务和导出目标。

如果未配置此策略，则不会对可接受的服务和导出目标强制实施任何限制。

策略选项映射：

* pinterest_suggestions (pinterest_suggestions) = Pinterest 建议

* collections_share （collections_share） = 集合的共享

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：CollectionsServicesAndExportsBlockList
  - GP 名称：阻止访问指定服务列表及在集锦中导出目标
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\CollectionsServicesAndExportsBlockList
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\CollectionsServicesAndExportsBlockList\1 = "pinterest_suggestions"
SOFTWARE\Policies\Microsoft\Edge\CollectionsServicesAndExportsBlockList\2 = "collections_share"

```

  #### Mac 信息和设置
  
  - 首选项名称： CollectionsServicesAndExportsBlockList
  - 示例值：
``` xml
<array>
  <string>pinterest_suggestions</string>
  <string>collections_share</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### CommandLineFlagSecurityWarningsEnabled

  #### 启用命令行标志的安全警告

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 78 或更高版本起

  #### 描述

  如果禁用，则此策略可阻止在使用潜在危险的命令行标志启动 Microsoft Edge 时出现安全警告。

如果启用或未设置，则在使用这些命令行标志启动 Microsoft Edge 时会显示安全警告。

例如，--disable-gpu-sandbox 标志将生成此警告：你正在使用不受支持的命令行标志：--disable-gpu-sandbox。 这会带来稳定性和安全风险。

此策略仅在加入 Microsoft Active Directory 域的 Windows 实例、已注册设备管理的 Windows 10 专业版或企业版实例，或者通过 MDM 托管或通过 MCX 加入域的 macOS 实例上可用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：CommandLineFlagSecurityWarningsEnabled
  - GP 名称：启用命令行标志的安全警告
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：CommandLineFlagSecurityWarningsEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：CommandLineFlagSecurityWarningsEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ComponentUpdatesEnabled

  #### 在 Microsoft Edge 中启用组件更新

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  如果启用或未配置此策略，则将在 Microsoft Edge 中启用组件更新。

如果禁用此策略或将其设置为 false，则 Microsoft Edge 中所有组件的组件更新都将被禁用。

但是，某些组件不受此策略约束。 这包括不含可执行代码、不会显著改变浏览器行为或者对安全至关重要的任何组件。 也就是说，即使禁用此策略，仍将应用被视为“对安全至关重要”的更新。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ComponentUpdatesEnabled
  - GP 名称：在 Microsoft Edge 中启用组件更新
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ComponentUpdatesEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ComponentUpdatesEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ConfigureDoNotTrack

  #### 配置 Do Not Track

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指定是否向要求跟踪信息的网站发送 Do Not Track 请求。 Do Not Track 请求可让你访问的网站知道你并不希望跟踪你的浏览活动。 默认情况下，Microsoft Edge 不发送 Do Not Track 请求，但用户可以打开此功能以发送请求。

如果启用此策略，则始终向要求跟踪信息的网站发送 Do Not Track 请求。

如果禁用此策略，则永远不会发送请求。

如果未配置此策略，用户可以选择是否发送这些请求。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ConfigureDoNotTrack
  - GP 名称：配置 Do Not Track
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ConfigureDoNotTrack
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：ConfigureDoNotTrack
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ConfigureFriendlyURLFormat

  #### 配置从 Microsoft Edge 复制的 URL 的默认粘贴格式，并确定用户是否可以使用其他格式

  
  
  #### 支持的版本：

  - 在 87 版或更高版本的 Windows 上
  - 在 macOS 上自 88 或更高版本起

  #### 描述

  如果启用了 FriendlyURLs，Microsoft Edge 将计算 URL 的其他表示形式并将其放入剪贴板。

当用户在外部应用程序中或在不带“粘贴为”上下文菜单项的 Microsoft Edge 中进行粘贴时，此策略将配置粘贴内容的格式。

如果已配置，此策略将代表用户作出选择。 edge://settings/shareCopyPaste 中的选项将显示为灰色，并且“粘贴为”上下文菜单中的选项将不可用。

* 未配置 = 用户将可以选择自己喜欢的粘贴格式。 默认情况下，会将此策略设置为友好 URL 格式。 Microsoft Edge 中将提供“粘贴为”菜单。

* 1 = 不会在剪贴板中存储其他格式。 Microsoft Edge 中将不显示“粘贴为”上下文菜单项，并且可用的粘贴格式只有纯文本 URL 格式。 实际上，友好 URL 功能将被禁用。

* 3 = 只要目标粘贴位置接受富文本，用户便会获得友好 URL。 对于不接受富文本的位置，则仍将提供纯文本 URL。 Microsoft Edge 中将不提供“粘贴为”菜单。

* 4 =（当前未使用）

某些粘贴目标和/或网站中可能不能很好地支持更丰富的格式。 因此，如果要配置此策略，则建议使用纯文本 URL 选项。

策略选项映射：

* PlainText (1) = 无任何额外信息的纯文本 URL，例如页面标题。 配置此策略时，推荐选择此选项。 有关详细信息，请参阅相关说明。

* TitledHyperlink (3) = 标题式超链接：指向复制的 URL 的超链接，但其可见文本是目标页面的标题。 这是一种友好的 URL 格式。

* WebPreview (4) = 即将推出。 如果设置，其行为与“纯文本 URL”相同。

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ConfigureFriendlyURLFormat
  - GP 名称：配置从 Microsoft Edge 复制的 URL 的默认粘贴格式，并确定用户是否可以使用其他格式
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ConfigureFriendlyURLFormat
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000003
```

  #### Mac 信息和设置
  
  - 首选项项名称：ConfigureFriendlyURLFormat
  - 示例值：
``` xml
<integer>3</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ConfigureOnPremisesAccountAutoSignIn

  #### 配置当没有 Azure AD 域帐户时使用 Active Directory 域帐户自动登录

  
  
  #### 支持的版本：

  - 在 Windows 上自 81 或更高版本起

  #### 描述

  如果用户的计算机已加入域，并且你的环境不是混合加入的，则可以使用 Active Directory 帐户进行自动登录。 如果希望用户使用其 Azure Active Directory 帐户自动登录，请对你的环境使用 Azure AD 加入（有关详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2118197](https://go.microsoft.com/fwlink/?linkid=2118197)）或混合加入（有关详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2118365](https://go.microsoft.com/fwlink/?linkid=2118365)）。

如果已将 [BrowserSigning](#browsersignin) 策略配置为禁用，则此策略将不会生效。

如果启用此策略并将其设置为 'SignInAndMakeDomainAccountNonRemovable'，则 Microsoft Edge 将会自动登录那些使用其 Active Directory 帐户来登录加入域的计算机的用户。

如果将此策略设置为“已禁用”或未设置该策略，则 Microsoft Edge 将不会自动登录那些使用其 Active Directory 帐户来登录加入域的计算机的用户。

策略选项映射：

* Disabled (0) = 禁用

* SignInAndMakeDomainAccountNonRemovable (1) = 登录并将域帐户设置为不可移动

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ConfigureOnPremisesAccountAutoSignIn
  - GP 名称：配置当没有 Azure AD 域帐户时使用 Active Directory 域帐户自动登录
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ConfigureOnPremisesAccountAutoSignIn
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  

  [返回页首](#microsoft-edge---policies)

  ### ConfigureOnlineTextToSpeech

  #### 配置联机文本到语音转换

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  设置浏览器是否可以利用联机文本到语音转换语音字体（Azure 认知服务的一部分）。 这些语音字体的质量高于预安装的系统语音字体。

如果启用或未配置此策略，则使用 SpeechSynthesis API 的基于 Web 的应用程序可以使用联机文本到语音转换语音字体。

如果禁用此策略，则语音字体不可用。

在此处阅读有关此功能的更多信息：SpeechSynthesis API：[https://go.microsoft.com/fwlink/?linkid=2110038](https://go.microsoft.com/fwlink/?linkid=2110038) 认知服务：[https://go.microsoft.com/fwlink/?linkid=2110141](https://go.microsoft.com/fwlink/?linkid=2110141)

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ConfigureOnlineTextToSpeech
  - GP 名称：配置联机文本到语音转换
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ConfigureOnlineTextToSpeech
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ConfigureOnlineTextToSpeech
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ConfigureShare

  #### 配置共享体验

  
  
  #### 支持的版本：

  - 在 Windows 上自 83 或更高版本起

  #### 描述

  如果将此策略设置为“ShareAllowed”（默认值），用户将能够从 Microsoft Edge 中的“设置及更多”菜单访问 Windows 10 共享体验，以便与系统上的其他应用共享。

如果将此策略设置为“ShareDisallowed”，用户将无法访问 Windows 10 共享体验。 如果“共享"按钮位于工具栏上，它也将被隐藏。

策略选项映射：

* ShareAllowed (0) = 允许使用共享体验

* ShareDisallowed (1) = 不允许使用共享体验

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ConfigureShare
  - GP 名称：配置共享体验
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ConfigureShare
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  

  [返回页首](#microsoft-edge---policies)

  ### CustomHelpLink

  #### 指定自定义帮助链接

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 79 或更高版本起

  #### 描述

  指定“帮助”菜单或 F1 键的链接。

如果启用此策略，管理员可以指定“帮助”菜单或 F1 键的链接。

如果禁用或未配置此策略，则将使用“帮助”菜单或 F1 键的默认链接。

此策略仅在加入 Microsoft Active Directory 域的 Windows 实例、已注册设备管理的 Windows 10 专业版或企业版实例，或者通过 MDM 托管或通过 MCX 加入域的 macOS 实例上可用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：CustomHelpLink
  - GP 名称：指定自定义帮助链接
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：CustomHelpLink
  - 值类型：REG_SZ

  ##### 示例值：

```
"https://go.microsoft.com/fwlink/?linkid=2080734"
```

  #### Mac 信息和设置
  
  - 首选项项名称：CustomHelpLink
  - 示例值：
``` xml
<string>https://go.microsoft.com/fwlink/?linkid=2080734</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DNSInterceptionChecksEnabled

  #### 已启用 DNS 拦截检查

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 80 或更高版本起

  #### 描述

  此策略配置可用于禁用 DNS 拦截检查的本地开关。 这些检查将尝试发现浏览器是否位于重定向未知主机名的代理后面。

在网络配置已知的企业环境中，可能不需要进行此检测。 可以将其禁用，以避免启动时和每次 DNS 配置更改时出现额外的 DNS 和 HTTP 流量。

如果启用或未设置此策略，则会执行 DNS 拦截检查。

如果禁用此策略，则不会执行 DNS 拦截检查。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DNSInterceptionChecksEnabled
  - GP 名称：已启用 DNS 拦截检查
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DNSInterceptionChecksEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：DNSInterceptionChecksEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultBrowserSettingEnabled

  #### 将 Microsoft Edge 设为默认浏览器

  
  
  #### 支持的版本：

  - 在 Windows 7 和 macOS 上自 77 或更高版本起

  #### 描述

  如果将此策略设置为 true，Microsoft Edge 将检查它是否为默认浏览器，并且在可能的情况下会自动注册。

如果将此策略设置为 False，则会阻止 Microsoft Edge 检查其是否为默认值，并将关闭此选项的用户控件。

如果未设置此策略，则 Microsoft Edge 可让用户控制是否为默认设置，如果不是，是否应显示用户通知。

Windows 管理员注意事项：此策略仅适用于运行 Windows 7 的电脑。 对于较高版本的 Windows，必须部署一个“默认应用程序关联”文件，该文件使 Microsoft Edge 成为 https 和 http 协议的处理程序（也可以涵盖 FTP 协议和文件格式，如 .html、.htm、.pdf、.svg、.webp） 有关详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2094932](https://go.microsoft.com/fwlink/?linkid=2094932)。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultBrowserSettingEnabled
  - GP 名称：将 Microsoft Edge 设为默认浏览器
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DefaultBrowserSettingEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultBrowserSettingEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultSearchProviderContextMenuAccessAllowed

  #### 允许默认搜索提供程序快捷菜单搜索访问

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 85 或更高版本起

  #### 描述

  允许在上下文菜单中使用默认搜索提供程序。

如果将此策略设置为 "禁用"，则依赖于默认搜索提供程序的搜索上下文菜单项和边栏搜索将不可用。

如果将此策略设置为 "启用" 或 "未设置"，则默认搜索提供程序的搜索上下文菜单项和边栏搜索将可用。

仅当启用 [DefaultSearchProviderEnabled](#defaultsearchproviderenabled) 策略时，该策略值才适用，否则将不适用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultSearchProviderContextMenuAccessAllowed
  - GP 名称：允许默认搜索提供程序快捷菜单搜索访问
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DefaultSearchProviderContextMenuAccessAllowed
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项名称： DefaultSearchProviderContextMenuAccessAllowed
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultSensorsSetting

  #### 默认传感器设置

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 86 或更高版本起

  #### 描述

  设置网站是否可访问和使用诸如运动和光传感器等传感器。 可完全阻止或允许网站获取对传感器的访问权限。

将策略设置为 “1” 可允许网站访问和使用传感器。 将策略设置为 “2” 将拒绝对传感器的访问。

对于特定 URL 模式，可以使用 [SensorsAllowedForUrls](#sensorsallowedforurls) 和 [SensorsBlockedForUrls](#sensorsblockedforurls) 策略来替代此策略。

如果未配置此策略，则网站可以访问和使用传感器，用户可以更改此设置。 这是 [SensorsAllowedForUrls](#sensorsallowedforurls) 和 [SensorsBlockedForUrls](#sensorsblockedforurls)的全局默认值。

策略选项映射：

* AllowSensors (1) = 允许网站访问传感器

* BlockSensors (2) = 不允许任何网站访问传感器

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultSensorsSetting
  - GP 名称：默认传感器设置
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DefaultSensorsSetting
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000002
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultSensorsSetting
  - 示例值：
``` xml
<integer>2</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DefaultSerialGuardSetting

  #### 控制串行 API 的使用

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 86 或更高版本起

  #### 描述

  设置网站是否可以访问串行端口。 可以完全阻止访问，也可以在网站每次想要访问串行端口时询问用户。

将策略设置为 “3” 可允许网站请求访问串行端口。 将策略设置为 "2" 将拒绝访问串行端口。

对于特定 URL 模式，可以使用 [SerialAskForUrls](#serialaskforurls) 和 [SerialBlockedForUrls](#serialblockedforurls) 策略来替代此策略。

如果未配置此策略，则默认情况下，网站可以询问用户是否能访问串行端口，用户可以更改此设置。

策略选项映射：

* BlockSerial (2) = 不允许任何网站通过串行 API 向串行端口请求访问

* AskSerial (3) = 允许网站向用户请求访问串行端口的许可

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DefaultSerialGuardSetting
  - GP 名称：控制串行 API 的使用
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DefaultSerialGuardSetting
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000002
```

  #### Mac 信息和设置
  
  - 首选项项名称：DefaultSerialGuardSetting
  - 示例值：
``` xml
<integer>2</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DelayNavigationsForInitialSiteListDownload

  #### 要求企业模式站点列表在选项卡导航前可用


  
  
  #### 支持的版本：

  - 在 84 版或更高版本的 Windows 上

  #### 描述

  允许你指定 Microsoft Edge 标签页是否在浏览器下载初始企业模式站点列表后，才会导航。 此设置适用于应该以 Internet Explorer 模式加载浏览器主页的场景，重要的是在启用IE模式后首次运行浏览器时执行此设置。 如果不存在此场景，我们建议不启用此设置，因为它可能会对加载主页的性能产生负面影响。 该设置仅适用于 Microsoft Edge 没有缓存的企业模式站点列表时，比如在启用IE模式后首次运行浏览器。

此设置与以下策略配合使用：[InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel) （设置为 'IEMode'） 和 [InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist) 策略 （列表至少有一个条目）。

该策略的超时行为可使用[NavigationDelayForInitialSiteListDownloadTimeout](#navigationdelayforinitialsitelistdownloadtimeout)策略进行配置。

如果将此策略设置为 'All'，当 Microsoft Edge 没有企业模式站点列表的缓存版本时，选项卡将在浏览器下载网站列表时延迟导航。 由站点列表配置为以 Internet Explorer 模式打开的网站将以 Internet Explorer 模式加载，即使是在浏览器的初始导航期间。 不能被配置为在 Internet Explorer 中打开的站点，比如使用 http:， https:，file:， 或 ftp: 以外的方案的站点，不会在 Edge 模式下立即延迟导航和加载。

如果将此策略设置为 'None' 或不对其进行配置，则当 Microsoft Edge 不具有缓存版本的企业模式站点列表时，选项卡将立即导航，而不会等待浏览器下载企业模式站点列表。 站点列表配置为在 Internet Explorer 模式下打开的站点将在 Microsoft Edge 模式下打开，直到浏览器完成企业模式站点列表的下载。

策略选项映射：

* None (0) = None

* All (1) = 所有符合条件的导航

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称： DelayNavigationsForInitialSiteListDownload
  - GP 名称：要求企业模式站点列表在选项卡导航前可用
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称： DelayNavigationsForInitialSiteListDownload
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  

  [返回页首](#microsoft-edge---policies)

  ### DeleteDataOnMigration

  #### 迁移时删除旧的浏览器数据

  
  
  #### 支持的版本：

  - 在 Windows 上自 83 或更高版本起

  #### 描述

  此策略确定在迁移到 Microsoft Edge 81 或更高版本后是否删除 Microsoft Edge 旧版中的用户浏览数据。

如果将此策略设置为“已启用”，则迁移到 Microsoft Edge 81 或更高版本后，Microsoft Edge 旧版中的所有浏览数据都将被删除。 必须在迁移到 Microsoft Edge 81 或更高版本之前设置此策略，以对现有浏览数据产生任何影响。

如果将此策略设置为“已禁用”，或者未配置此策略，则在迁移到 Microsoft Edge 83 或更高版本后，不会删除用户浏览数据。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DeleteDataOnMigration
  - GP 名称：迁移时删除旧的浏览器数据
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DeleteDataOnMigration
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  

  [返回页首](#microsoft-edge---policies)

  ### DeveloperToolsAvailability

  #### 控制可使用开发人员工具的位置

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  控制可使用开发人员工具的位置。

如果将此策略设置为“DeveloperToolsDisallowedForForceInstalledExtensions”（默认值），则用户通常可以访问开发人员工具和 JavaScript 控制台，但不能在企业策略安装的扩展上下文中访问。

如果将此策略设置为“DeveloperToolsAllowed”，则用户可以在所有上下文中访问开发人员工具和 JavaScript 控制台，包括企业策略安装的扩展在内。

如果将此策略设置为“DeveloperToolsDisallowed”，用户将无法访问开发人员工具或检查网站元素。 打开开发人员工具或 JavaScript 控制台的键盘快捷方式和菜单或上下文菜单项将被禁用。

策略选项映射：

* DeveloperToolsDisallowedForForceInstalledExtensions (0) = 阻止开发人员工具使用企业策略安装的扩展，并在其他情况下允许使用。

* DeveloperToolsAllowed (1) = 允许使用开发人员工具

* DeveloperToolsDisallowed (2) = 不允许使用开发人员工具

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DeveloperToolsAvailability
  - GP 名称：控制可使用开发人员工具的位置
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DeveloperToolsAvailability
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000002
```

  #### Mac 信息和设置
  
  - 首选项项名称：DeveloperToolsAvailability
  - 示例值：
``` xml
<integer>2</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DiagnosticData

  #### 发送有关浏览器使用情况的必需和可选诊断数据

  
  
  #### 支持的版本：

  - 在 Windows 7 和 macOS 上自 86 或更高版本起

  #### 描述

  此策略控制向 Microsoft 发送有关浏览器使用情况的必需和可选诊断数据。

收集所需的诊断数据可确保 Microsoft Edge 安全、最新且按预期运行。

可选诊断数据包括向 Microsoft 发送的用于改进产品和服务的有关浏览器使用情况、访问的网站以及故障报告的数据。

Windows 10 设备不支持此策略。 若要在 Windows 10 上控制此数据收集，IT 管理员必须使用 Windows 诊断数据组策略。 根据 Windows 版本的不同，此策略将是“允许遥测”或“允许诊断数据”。 详细了解 Windows 10 诊断数据收集：[https://go.microsoft.com/fwlink/?linkid=2099569](https://go.microsoft.com/fwlink/?linkid=2099569)

使用以下设置之一配置此策略：

'Off' 会关闭必需和可选的诊断数据收集。 不建议使用此选项。

'RequiredData' 会发送必需的诊断数据，但关闭可选的诊断数据收集。 Microsoft Edge 会发送必需的诊断数据，以确保 Microsoft Edge 安全、最新且按预期运行。

'OptionalData' 会发送可选诊断数据，包括向 Microsoft 发送的用于改进产品和服务的有关浏览器使用情况、访问的网站以及故障报告的数据。

对于 Windows 7/macOS，此策略控制向 Microsoft 发送的必需和可选数据。

如果未配置或已禁用此策略，Microsoft Edge 将默认使用用户首选项。

策略选项映射：

* Off (0) = 关闭（不推荐）

* RequiredData (1) = 必需数据

* OptionalData (2) = 可选数据

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DiagnosticData
  - GP 名称：发送有关浏览器使用情况的必需和可选诊断数据
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DiagnosticData
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000002
```

  #### Mac 信息和设置
  
  - 首选密钥名称：DiagnosticData
  - 示例值：
``` xml
<integer>2</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DirectInvokeEnabled

  #### 允许用户使用 DirectInvoke 协议打开文件

  
  
  #### 支持的版本：

  - 在 Windows 上自 78 或更高版本起

  #### 描述

  允许用户使用 DirectInvoke 协议打开文件。 通过 DirectInvoke 协议，网站可请求浏览器使用用户计算机或设备上的特定文件处理程序从特定 URL 打开文件。

如果启用或未配置此策略，用户可以使用 DirectInvoke 协议打开文件。

如果禁用此策略，用户将无法使用 DirectInvoke 协议打开文件。 而是将文件保存到文件系统。

注意：禁用 DirectInvoke 可能会导致某些 Microsoft SharePoint Online 功能无法按预期工作。

有关 DirectInvoke 的详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2103872](https://go.microsoft.com/fwlink/?linkid=2103872) 和 [https://go.microsoft.com/fwlink/?linkid=2099871](https://go.microsoft.com/fwlink/?linkid=2099871)。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DirectInvokeEnabled
  - GP 名称：允许用户使用 DirectInvoke 协议打开文件
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DirectInvokeEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  

  [返回页首](#microsoft-edge---policies)

  ### Disable3DAPIs

  #### 禁用对 3D 图形 API 的支持

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  阻止网页访问图形处理单元 (GPU)。 具体而言，网页无法访问 WebGL API，插件无法使用 Pepper 3D API。

如果未配置或禁用此策略，则可能允许网页使用 WebGL API 并允许插件使用 Pepper 3D API。 默认情况下，Microsoft Edge 可能仍需要传递命令行参数才能使用这些 API。

如果将 [HardwareAccelerationModeEnabled](#hardwareaccelerationmodeenabled) 策略设置为 false，则会忽略“Disable3DAPIs”策略的设置 - 其等效于将“Disable3DAPIs”策略设置为 true。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：Disable3DAPIs
  - GP 名称：禁用对 3D 图形 API 的支持
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：Disable3DAPIs
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：Disable3DAPIs
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DisableScreenshots

  #### 禁止拍摄屏幕截图

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  控制用户是否可以拍摄浏览器页面的屏幕截图。

如果启用，则用户不能使用键盘快捷方式或扩展 API 拍摄屏幕截图。

如果禁用或未配置此策略，则用户可以拍摄屏幕截图。

请注意，此策略控制从浏览器本身拍摄的屏幕截图。 即使启用此策略，用户可能仍然能够使用浏览器之外的某种方法（如使用操作系统功能或其他应用程序）拍摄屏幕截图。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DisableScreenshots
  - GP 名称：禁止拍摄屏幕截图
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DisableScreenshots
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：DisableScreenshots
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DiskCacheDir

  #### 设置磁盘缓存目录

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  配置用于存储缓存文件的目录。

如果启用此策略，Microsoft Edge 将使用提供的目录，而不管用户是否指定了“--disk-cache-dir”标志。 为避免数据丢失或其他意外错误，请不要将此策略配置为卷的根目录或用于其他目的的目录，因为 Microsoft Edge 负责管理其内容。

有关指定目录和路径时可使用的变量列表，请参阅 [https://go.microsoft.com/fwlink/?linkid=2095041](https://go.microsoft.com/fwlink/?linkid=2095041)。

如果未配置此策略，则将使用默认缓存目录，用户可以使用“--disk-cache-dir”命令行标志替代该默认值。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DiskCacheDir
  - GP 名称：设置磁盘缓存目录
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DiskCacheDir
  - 值类型：REG_SZ

  ##### 示例值：

```
"${user_home}/Edge_cache"
```

  #### Mac 信息和设置
  
  - 首选项项名称：DiskCacheDir
  - 示例值：
``` xml
<string>${user_home}/Edge_cache</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DiskCacheSize

  #### 设置磁盘缓存大小（以字节为单位）

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  配置用于在磁盘上存储文件的缓存大小（以字节为单位）。

如果启用此策略，Microsoft Edge 将使用提供的缓存大小，而不管用户是否指定了“--disk-cache-size”标志。 此策略中指定的值不是硬边界，而是对缓存系统的建议；任何小于几兆字节的值都太小，将被舍入到一个合理的最小值。

如果将此策略的值设为 0，则使用默认缓存大小，用户不能更改它。

如果未配置此策略，则使用默认大小，但用户可以使用“--disk-cache-size”标志替代它。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DiskCacheSize
  - GP 名称：设置磁盘缓存大小（以字节为单位）
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DiskCacheSize
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x06400000
```

  #### Mac 信息和设置
  
  - 首选项项名称：DiskCacheSize
  - 示例值：
``` xml
<integer>104857600</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DnsOverHttpsMode

  #### 控制 DNS-over-HTTPS 的模式

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 83 或更高版本起

  #### 描述

  控制 DNS-over-HTTPS 解析程序的模式。 请注意，此策略仅为每个查询设置默认模式。 对于特殊类型的查询（例如，解析 DNS-over-HTTPS 服务器主机名的请求），可以替代该模式。

“off”模式将禁用 DNS-over-HTTPS。

“automatic”模式将首先发送 DNS-over-HTTPS 查询（如果有 DNS-over-HTTPS 服务器可用），并且在发生错误时可能回退到发送不安全的查询。

“secure”模式只会发送 DNS-over-HTTPS 查询，并且在发生错误时无法解析。

如果未配置此策略，浏览器可能会将 DNS-over-HTTPS 请求发送到与用户配置的系统解析程序关联的解析程序。

策略选项映射：

* off (off) = 禁用 DNS-over-HTTPS

* automatic (automatic) = 启用不安全回退的 DNS-over-HTTPS

* secure (secure) = 启用不安全回退的 DNS-over-HTTPS

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DnsOverHttpsMode
  - GP 名称：控制 DNS-over-HTTPS 的模式
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DnsOverHttpsMode
  - 值类型：REG_SZ

  ##### 示例值：

```
"off"
```

  #### Mac 信息和设置
  
  - 首选项项名称：DnsOverHttpsMode
  - 示例值：
``` xml
<string>off</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DnsOverHttpsTemplates

  #### 指定所需 DNS-over-HTTPS 解析程序的 URI 模板

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 83 或更高版本起

  #### 描述

  所需 DNS-over-HTTPS 解析程序的 URI 模板。 要指定多个 DNS-over-HTTPS 解析程序，请用空格分隔相应的 URI 模板。

如果将 [DnsOverHttpsMode](#dnsoverhttpsmode) 设置为“secure”，则必须设置此策略，并且该策略不能为空。

如果将 [DnsOverHttpsMode](#dnsoverhttpsmode) 设置为“automatic”并且设置了此策略，则将使用指定的 URI 模板。 如果未设置此策略，则将使用硬编码映射来尝试将用户的当前 DNS 解析程序升级到由同一提供程序操作的 DOH 解析程序。

如果 URI 模板包含 DNS 变量，则向解析程序发出的请求将使用 GET；否则，请求将使用 POST。

格式不正确的模板将被忽略。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DnsOverHttpsTemplates
  - GP 名称：指定所需 DNS-over-HTTPS 解析程序的 URI 模板
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：DnsOverHttpsTemplates
  - 值类型：REG_SZ

  ##### 示例值：

```
"https://dns.example.net/dns-query{?dns}"
```

  #### Mac 信息和设置
  
  - 首选项项名称：DnsOverHttpsTemplates
  - 示例值：
``` xml
<string>https://dns.example.net/dns-query{?dns}</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DownloadDirectory

  #### 设置下载目录

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  配置下载文件时要使用的目录。

如果启用此策略，则无论用户已指定了一个目录，还是选择每次都提示提供下载位置，Microsoft Edge 都将使用提供的目录。 有关可使用的变量列表，请参阅 [https://go.microsoft.com/fwlink/?linkid=2095041](https://go.microsoft.com/fwlink/?linkid=2095041)。

如果禁用或未配置此策略，则使用默认下载目录，用户可以更改它。

如果设置了无效路径，Microsoft Edge 将默认为用户的默认下载目录。

如果路径指定的文件夹不存在，则下载操作将触发提示，询问用户要将其下载保存到何处。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DownloadDirectory
  - GP 名称：设置下载目录
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：DownloadDirectory
  - 值类型：REG_SZ

  ##### 示例值：

```
"\n      Linux-based OSes (including Mac): /home/${user_name}/Downloads\n      Windows: C:\\Users\\${user_name}\\Downloads"
```

  #### Mac 信息和设置
  
  - 首选项项名称：DownloadDirectory
  - 示例值：
``` xml
<string>
      Linux-based OSes (including Mac): /home/${user_name}/Downloads
      Windows: C:\Users\${user_name}\Downloads</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### DownloadRestrictions

  #### 允许下载限制

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  配置 Microsoft Edge 完全阻止的下载类型，而不允许用户替代安全决策。

设置 'BlockDangerousDownloads' 可允许所有下载，但带有 Microsoft Defender SmartScreen 警告的下载除外。

设置 'BlockPotentiallyDangerousDownloads' 可允许所有下载，但带有 Microsoft Defender SmartScreen 警告的潜在危险或不需要的下载除外。

设置 "BlockAllDownloads" 以阻止所有下载。

如果未配置此策略或设置 'DefaultDownloadSecurity' 选项，则下载将根据 Microsoft Defender SmartScreen 分析结果执行常规安全限制。

请注意，这些限制适用于网页内容中的下载以及“下载链接...”上下文菜单选项。 这些限制不适用于保存或下载当前显示的页面，也不适用于打印选项中的“另存为 PDF”选项。

有关 Microsoft Defender SmartScreen 的详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2094934](https://go.microsoft.com/fwlink/?linkid=2094934)。

策略选项映射：

* DefaultDownloadSecurity (0) = 无特殊限制

* BlockDangerousDownloads (1) = 阻止危险下载

* BlockPotentiallyDangerousDownloads (2) = 阻止潜在的危险或有害下载

* BlockAllDownloads (3) = 阻止所有下载

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：DownloadRestrictions
  - GP 名称：允许下载限制
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：DownloadRestrictions
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000002
```

  #### Mac 信息和设置
  
  - 首选项项名称：DownloadRestrictions
  - 示例值：
``` xml
<integer>2</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### EdgeCollectionsEnabled

  #### 启用“集锦”功能

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 78 或更高版本起

  #### 描述

  可让用户访问“集锦”功能，他们可在其中使用 Office 集成更高效地收集、组织、共享和导出内容。

如果启用或未配置此策略，则用户可以访问和使用 Microsoft Edge 中的“集锦”功能。

如果禁用此策略，用户将无法访问和使用 Microsoft Edge 中的“集锦”。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：EdgeCollectionsEnabled
  - GP 名称：启用“集锦”功能
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：EdgeCollectionsEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：EdgeCollectionsEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### EdgeShoppingAssistantEnabled

  #### 已启用在 Microsoft Edge 中购物的功能

  
  
  #### 支持的版本：

  - On Windows and macOS since 87 or later

  #### 描述

  通过此策略，用户可以比较正在查看的产品的价格、从其所在网站获取优惠券，或在结帐过程中自动应用优惠券。

如果启用或未配置此策略，将自动针对零售域应用价格比较和优惠券等购物功能。 系统将从服务器提取当前零售商的优惠券和其他零售商提供的价格。

如果禁用此策略，则不会自动针对零售域应用价格比较和优惠券等购物功能。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：EdgeShoppingAssistantEnabled
  - GP 名称：已启用在 Microsoft Edge 中购物的功能
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：EdgeShoppingAssistantEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：EdgeShoppingAssistantEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### EditFavoritesEnabled

  #### 允许用户编辑收藏夹

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  启用此策略后，用户可添加、删除和修改收藏夹。 如果未配置该策略，则这是默认行为。

禁用此策略后，用户将无法添加、删除或修改收藏夹。 他们仍然可以使用现有收藏夹。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：EditFavoritesEnabled
  - GP 名称：允许用户编辑收藏夹
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：EditFavoritesEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：EditFavoritesEnabled
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### EnableDeprecatedWebPlatformFeatures

  #### Re-enable deprecated web platform features for a limited time (obsolete)

  
  >OBSOLETE: This policy is obsolete and doesn't work after Microsoft Edge 86.
  #### 支持的版本：

  - On Windows and macOS since 77, until 86

  #### 描述

  This policy is obsolete because dedicated web platform policies are now used to manage individual web platform feature deprecations.

指定要临时重新启用的已弃用 Web 平台功能的列表。

通过此策略，可在有限的时间内重新启用已弃用的 Web 平台功能。 功能由字符串标记标识。

如果未配置此策略，列表为空，或者某个功能与支持的字符串标记之一不匹配，则所有已弃用的 Web 平台功能将保持禁用状态。

虽然该策略本身在上述平台上受支持，但它启用的功能可能并非在所有这些平台上都可用。 并非所有已弃用的 Web 平台功能都可以重新启用。 只有下面明确列出的功能才能重新启用，并且只能在有限的时间内重新启用，具体情况因功能而异。 可以在 https://bit.ly/blinkintents 查看 Web 平台功能更改背后的意图。

字符串标记的常规格式为 [DeprecatedFeatureName]_EffectiveUntil[yyyymmdd]。

策略选项映射：

* ExampleDeprecatedFeature (ExampleDeprecatedFeature_EffectiveUntil20080902) = 启用 ExampleDeprecatedFeature API 直至 2008/09/02

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：EnableDeprecatedWebPlatformFeatures
  - GP name: Re-enable deprecated web platform features for a limited time (obsolete)
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\EnableDeprecatedWebPlatformFeatures
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\EnableDeprecatedWebPlatformFeatures\1 = "ExampleDeprecatedFeature_EffectiveUntil20080902"

```

  #### Mac 信息和设置
  
  - 首选项项名称：EnableDeprecatedWebPlatformFeatures
  - 示例值：
``` xml
<array>
  <string>ExampleDeprecatedFeature_EffectiveUntil20080902</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### EnableDomainActionsDownload

  #### 启用 Microsoft 中的域操作下载（已过时）

  
  >已过时：该策略已过时，Microsoft Edge 版本 84 后将无法正常工作。
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 起至 84

  #### 描述

  由于应避免冲突状态，此策略无效。 此策略用于启用/禁用域操作列表下载，但它并不总是能达到所需状态。 负责处理下载的试验和配置服务有自己的策略来配置从服务下载的内容。 使用 [ExperimentationAndConfigurationServiceControl](#experimentationandconfigurationservicecontrol) 策略。

在 Microsoft Edge 中，域操作代表一系列兼容性功能，可帮助浏览器在 Web 上正常工作。

Microsoft 会保留一个列表，列出出于兼容性原因要对某些域执行的操作。 例如，如果 Microsoft Edge 上的新用户代理字符串导致某个网站被破坏，则浏览器可能会替代该网站上的用户代理字符串。 当 Microsoft 尝试解决网站所有者的问题时，这些操作中的每一个操作都是临时的。

当浏览器启动后定期出现时，浏览器将与包含要执行的兼容性操作最新列表的试验和配置服务联系。 此列表在首次检索后将保存到本地，以便后续请求仅在服务器的副本发生更改时更新该列表。

如果启用此策略，将继续从试验和配置服务下载域操作列表。

如果禁用此策略，将不再从试验和配置服务下载域操作列表。

如果未配置此策略，将继续从试验和配置服务下载域操作列表。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：EnableDomainActionsDownload
  - GP 名称：启用 Microsoft 中的域操作下载（已过时）
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：EnableDomainActionsDownload
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：EnableDomainActionsDownload
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### EnableOnlineRevocationChecks

  #### 启用联机 OCSP/CRL 检查

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  联机吊销检查不会提供显著的安全优势，默认情况下已禁用。

如果启用此策略，Microsoft Edge 将执行软故障联机 OCSP/CRL 检查。 “软故障”意味着如果无法访问吊销服务器，证书将被视为有效。

如果禁用或未配置该策略，Microsoft Edge 将不会执行联机吊销检查。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：EnableOnlineRevocationChecks
  - GP 名称：启用联机 OCSP/CRL 检查
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：EnableOnlineRevocationChecks
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：EnableOnlineRevocationChecks
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### EnableSha1ForLocalAnchors

  #### 当本地信任密钥发布证书时，允许使用 SHA-1 对证书进行签名（已弃用）

  >已弃用：此策略已弃用。 当前受支持，但将在未来的版本中弃用。
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 85 或更高版本起

  #### 描述

  启用此设置后，只要证书链接到本地​​安装的根证书并且该证书有效，Microsoft Edge 就会允许使用 SHA-1 签名证书保护连接。

请注意，此策略依赖于允许启用 SHA-1 签名的操作系统 (OS) 证书验证堆栈。 如果 OS 更新更改了 SHA-1 证书的 OS 处理，则此策略可能不再生效。  此外，此策略旨在作为临时解决方法，使企业有更多时间摆脱 SHA-1。 此策略将在 2021 年年中发布的 Microsoft Edge 92 中删除。

如果未设置此策略或将其设置为 false，或者 SHA-1 证书链接到公共信任的证书根目录，则 Microsoft Edge 将不允许 SHA-1 签名的证书。

此策略仅在加入 Microsoft Active Directory 域的 Windows 实例、已注册设备管理的 Windows 10 专业版或企业版实例，或者通过 MDM 托管或通过 MCX 加入域的 macOS 实例上可用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称： EnableSha1ForLocalAnchors
  - GP 名称：当本地信任密钥发布证书时，允许使用 SHA-1 对证书进行签名（已弃用）
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称： EnableSha1ForLocalAnchors
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项名称： EnableSha1ForLocalAnchors
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### EnterpriseHardwarePlatformAPIEnabled

  #### 允许托管扩展使用企业硬件平台 API

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 78 或更高版本起

  #### 描述

  当此策略设置为启用时，允许企业策略安装的扩展使用企业硬件平台 API。
当此策略设置为禁用或未设置时，不允许扩展使用企业硬件平台 API。
此策略也适用于组件扩展。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：EnterpriseHardwarePlatformAPIEnabled
  - GP 名称：允许托管扩展使用企业硬件平台 API
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：EnterpriseHardwarePlatformAPIEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：EnterpriseHardwarePlatformAPIEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### EnterpriseModeSiteListManagerAllowed

  #### 允许访问 Enterprise Mode Site List Manager 工具

  
  
  #### 支持的版本：

  - 在 86 版或更高版本的 Windows 上

  #### 描述

  可用于设置是否对用户提供 Enterprise Mode Site List Manager。

如果启用此策略，则用户可以在 edge://compat 页上看到 Enterprise Mode Site List Manager 导航按钮，导航到该工具并使用它。

如果禁用或未配置此策略，则用户将看不到 Enterprise Mode Site List Manager 导航按钮，也将无法使用它。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：EnterpriseModeSiteListManagerAllowed
  - GP 名称：允许访问 Enterprise Mode Site List Manager 工具
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：EnterpriseModeSiteListManagerAllowed
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  

  [返回页首](#microsoft-edge---policies)

  ### ExemptDomainFileTypePairsFromFileTypeDownloadWarnings

  #### 为域上指定的文件类型禁用基于下载文件类型扩展的警告

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 85 或更高版本起

  #### 描述

  你可以启用此策略来创建一个文件类型扩展名字典，其中包含相应的域列表，这些域将免于基于文件类型扩展名的下载警告。 这使得企业管理员可以阻止针对与列出域相关联的文件的基于文件类型扩展的下载警告。 例如，如果“jnlp”扩展名与“website1.com”相关，用户从“website1.com”下载“jnlp”文件时不会看到警告，但是从“website2.com”下载“jnlp”文件时会看到下载警告。

文件类型扩展名指定为该策略识别的域将仍然受到非文件类型扩展名的安全警告，如混合内容下载警告和 Microsoft Defender SmartScreen 警告。

如果禁用此策略或不对其进行配置，则触发基于扩展的下载警告的文件类型将向用户显示警告。

如果启用此策略：

* URL 模式应按 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)进行格式设置。
* 输入的文件类型扩展名必须采用低的 ASCII。 在列出文件类型扩展名时，不应该包括前导分隔符，因此应该使用列表“jnlp”而不是“.jnlp”。

示例：

下面的示例值将防止*.contoso.com域在swf、exe和jnlp扩展名上基于文件类型扩展的下载警告。 它将在任何其他域中为exe和jnlp文件显示基于文件类型的下载警告，但不为 swf 文件。

[ { "file_extension": "jnlp", "domains": ["contoso.com"] }, { "file_extension": "exe", "domains": ["contoso.com"] }, { "file_extension": "swf", "domains": ["*"] } ]

请注意，虽然前面的示例显示了对所有域的“swf”文件禁用基于文件类型扩展的下载警告，但出于安全考虑，不建议对所有域的任何危险文件类型扩展应用此类警告。 在示例中显示它只是为了演示这样做的能力。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称： ExemptDomainFileTypePairsFromFileTypeDownloadWarnings
  - GP 名称：禁止下载针对域中指定文件类型的基于文件类型扩展名的警告
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径(必需) : SOFTWARE\Policies\Microsoft\Edge\ExemptDomainFileTypePairsFromFileTypeDownloadWarnings
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\ExemptDomainFileTypePairsFromFileTypeDownloadWarnings\1 = {"domains": ["https://contoso.com", "contoso2.com"], "file_extension": "jnlp"}
SOFTWARE\Policies\Microsoft\Edge\ExemptDomainFileTypePairsFromFileTypeDownloadWarnings\2 = {"domains": ["*"], "file_extension": "swf"}

```

  #### Mac 信息和设置
  
  - 首选参数名称： ExemptDomainFileTypePairsFromFileTypeDownloadWarnings
  - 示例值：
``` xml
<array>
  <string>{'domains': ['https://contoso.com', 'contoso2.com'], 'file_extension': 'jnlp'}</string>
  <string>{'domains': ['*'], 'file_extension': 'swf'}</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ExperimentationAndConfigurationServiceControl

  #### 控制与试验和配置服务的通信

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  在 Microsoft Edge 中，试验和配置服务用于部署试验和配置有效负载。

试验有效负载包括 Microsoft 为测试和反馈启用的早期开发功能列表。

配置有效负载包含 Microsoft 希望部署到 Microsoft Edge 以优化用户体验的设置列表。 例如，配置有效负载可指定 Microsoft Edge 向试验和配置服务发送请求以检索最新有效负载的频率。

此外，配置有效负载还可能包含出于兼容性原因对某些域采取的操作列表。 例如，如果 Microsoft Edge 上的新用户代理字符串导致某个网站被破坏，则浏览器可能会替代该网站上的用户代理字符串。 当 Microsoft 尝试解决网站所有者的问题时，这些操作中的每一个操作都是临时的。

如果将此策略设置为 'FullMode' 模式，则会从实验和配置服务下载完整的有效负载。 这包括试验和配置有效负载。

如果将此策略设置为 'ConfigurationsOnlyMode' 模式，则仅提供配置有效负载。

如果将此策略设置为 "RestrictedMode"，将完全停止与实验和配置服务的通信。

如果未配置此策略，则在 Stable 和 Beta 渠道的受管理设备上，行为与 'ConfigurationsOnlyMode' 模式相同。

如果未配置此策略，则在未被管理的设备上，该行为与 "FullMode" 相同。

策略选项映射：

* FullMode (2) = 检索配置和实验

* ConfigurationsOnlyMode (1) = 仅检索配置

* RestrictedMode (0) = 禁用与实验和配置服务的通信

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ExperimentationAndConfigurationServiceControl
  - GP 名称：控制与试验和配置服务的通信
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ExperimentationAndConfigurationServiceControl
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000002
```

  #### Mac 信息和设置
  
  - 首选项项名称：ExperimentationAndConfigurationServiceControl
  - 示例值：
``` xml
<integer>2</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ExternalProtocolDialogShowAlwaysOpenCheckbox

  #### 在外部协议对话框中显示“始终打开”复选框

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 79 或更高版本起

  #### 描述

  此策略控制外部协议启动确认提示上是否显示“始终允许此网站打开此类型的链接”复选框。 此策略仅适用于 https:// links。

如果启用此策略，则当显示外部协议确认提示时，用户可以选择“始终允许”以跳过此网站上协议的所有未来确认提示。

如果禁用此策略，则不会显示“始终允许”复选框。 每次调用外部协议时，系统都会提示用户进行确认。

在 Microsoft Edge 83 前，如果未配置此策略，则不会显示“始终允许”复选框。 每次调用外部协议时，系统都会提示用户进行确认。

对于 Microsoft Edge 83，如果未配置此策略，复选框可见性由 edge://flags 中的“允许记住协议启动提示首选项”标志控制

自 Microsoft Edge 84 起，如果未配置此策略，则当显示外部协议确认提示时，用户可以选择“始终允许”跳过针对此网站上协议的所有未来确认提示。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ExternalProtocolDialogShowAlwaysOpenCheckbox
  - GP 名称：在外部协议对话框中显示“始终打开”复选框
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ExternalProtocolDialogShowAlwaysOpenCheckbox
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ExternalProtocolDialogShowAlwaysOpenCheckbox
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### FamilySafetySettingsEnabled

  #### 允许用户配置家庭安全

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 83 或更高版本起

  #### 描述

  此策略将禁用并完全隐藏“设置”中的家庭安全页面。 也将禁止导航至 edge://settings/familysafety。 家庭安全页面描述了哪些功能可用于家庭组以及如何加入家庭组。 在此处了解有关家庭安全的更多信息：([https://go.microsoft.com/fwlink/?linkid=2098432](https://go.microsoft.com/fwlink/?linkid=2098432))。

如果启用或未配置此策略，则将显示家庭安全页面。

如果禁用此策略，将不会显示家庭安全页面。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：FamilySafetySettingsEnabled
  - GP 名称：允许用户配置家庭安全
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：FamilySafetySettingsEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：FamilySafetySettingsEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### FavoritesBarEnabled

  #### 启用收藏夹栏

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  启用或禁用收藏夹栏。

如果启用此策略，用户将看到收藏夹栏。

如果禁用此策略，用户将看不到收藏夹栏。

如果未配置此策略，则用户可以决定是否使用收藏夹栏。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：FavoritesBarEnabled
  - GP 名称：启用收藏夹栏
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：FavoritesBarEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：FavoritesBarEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ForceBingSafeSearch

  #### 强制实施必应安全搜索

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  确保将安全搜索设为指定的值并完成必应 Web 搜索中的查询。 用户无法更改此设置。

如果将此策略配置为 "BingSafeSearchNoRestrictionsMode"，必应搜索中的搜索安全将回退到 bing.com 值。

如果将此策略配置为 'BingSafeSearchModerateMode'，则使用安全搜索中的中等设置。 “中等”设置可筛选成人视频和图像，但不能筛选搜索结果中的文本。

如果将此策略配置为 'BingSafeSearchStrictMode'，则使用安全搜索中的严格设置。 严格设置可筛选成人文本、图像和视频。

如果禁用或未配置此策略，则不会强制实施必应搜索中的安全搜索，用户可以在 bing.com 上设置所需的值。

策略选项映射：

* BingSafeSearchNoRestrictionsMode (0) = 不要在必应中配置搜索限制

* BingSafeSearchModerateMode (1) = 在必应中配置中等搜索限制

* BingSafeSearchStrictMode (2) = 在必应中配置严格搜索限制

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ForceBingSafeSearch
  - GP 名称：强制实施必应安全搜索
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ForceBingSafeSearch
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：ForceBingSafeSearch
  - 示例值：
``` xml
<integer>0</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ForceCertificatePromptsOnMultipleMatches

  #### 配置当配置了“AutoSelectCertificateForUrls”的网站有多个证书匹配项时，Microsoft Edge 是否应自动选择证书

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 81 或更高版本起

  #### 描述

  切换是否在有多个证书可用且网站配置了 [AutoSelectCertificateForUrls](#autoselectcertificateforurls) 时提示用户选择证书。 如果未为网站配置 [AutoSelectCertificateForUrls](#autoselectcertificateforurls)，则系统将始终提示用户选择证书。

如果将此策略设置为 True，则只有当有多个证书时，Microsoft Edge 才会提示用户为 [AutoSelectCertificateForUrls](#autoselectcertificateforurls) 中定义的列表上的网站选择证书。

如果将此策略设置为 False 或未配置，Microsoft Edge 将自动选择一个证书，即使证书有多个匹配项也是如此。 系统不会提示用户为 [AutoSelectCertificateForUrls](#autoselectcertificateforurls) 中定义的列表上的网站选择证书。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ForceCertificatePromptsOnMultipleMatches
  - GP 名称：配置当配置了“AutoSelectCertificateForUrls”的网站有多个证书匹配项时，Microsoft Edge 是否应自动选择证书
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ForceCertificatePromptsOnMultipleMatches
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ForceCertificatePromptsOnMultipleMatches
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ForceEphemeralProfiles

  #### 启用临时配置文件的使用

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  控制用户配置文件是否切换到临时模式。 会话开始时将创建一个临时配置文件，会话结束时将删除该配置文件，并且该配置文件与用户的原始配置文件相关联。

如果启用此策略，则配置文件将以临时模式运行。 这样，用户可从自己的设备工作，无需将浏览数据保存到这些设备。 如果将此策略启用为操作系统策略（例如，通过在 Windows 上使用 GPO），则它将应用于系统上的每个配置文件。

如果禁用此策略或未配置它，用户在登录浏览器时将获得其常规配置文件。

在临时模式下，配置文件数据仅在用户会话期间保存在磁盘上。 浏览器历史记录、扩展及其数据、Cookie 等 Web 数据以及 Web 数据库等功能在浏览器关闭后不会保存。 这不会阻止用户将任何数据手动下载到磁盘，或者保存页面或打印它们。 如果用户已启用同步，则所有数据都将保留在其同步帐户中，就像使用常规配置文件一样。 用户还可以在临时模式下使用 InPrivate 浏览，除非你明确禁用此功能。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ForceEphemeralProfiles
  - GP 名称：启用临时配置文件的使用
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ForceEphemeralProfiles
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ForceEphemeralProfiles
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ForceGoogleSafeSearch

  #### 强制实施 Google 安全搜索

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  将安全搜索设置为活动状态并强制执行 Google Web 搜索中的查询，并防止用户更改此设置。

如果启用此策略，则 Google 搜索中的安全搜索始终处于活动状态。

如果禁用或未配置此策略，则不会强制实施 Google 搜索中的安全搜索。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ForceGoogleSafeSearch
  - GP 名称：强制实施 Google 安全搜索
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ForceGoogleSafeSearch
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：ForceGoogleSafeSearch
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ForceLegacyDefaultReferrerPolicy

  #### 使用 no-referrer-when-downgrade 的默认引用者策略。（已弃用）

  >已弃用：此策略已弃用。 当前受支持，但将在未来的版本中弃用。
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 81 或更高版本起

  #### 描述

  此策略已弃用，因为它仅作为一种短期机制提供，目的是让企业能够在发现与当前默认引用者策略不兼容时有更多的时间来更新其 Web 内容。 在 Microsoft Edge version 88 将不起作用。

通过逐步部署，Microsoft Edge 的默认引用者策略已从其当前的 no-referrer-when-downgrade 值增强为更安全的 strict-origin-when-cross-origin。

在部署之前，此企业策略将不起作用。 部署后，如果启用此企业策略，Microsoft Edge 的默认引用者策略将设置为 no-referrer-when-downgrade 的旧值。

默认情况下，此企业策略处于禁用状态。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ForceLegacyDefaultReferrerPolicy
  - GP 名称：使用 no-referrer-when-downgrade 的默认引用者策略（已弃用）
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ForceLegacyDefaultReferrerPolicy
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：ForceLegacyDefaultReferrerPolicy
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ForceNetworkInProcess

  #### 强制网络代码在浏览器进程中运行（已过时）

  
  >已过时：该策略已过时，Microsoft Edge 版本83 后将无法正常工作。
  #### 支持的版本：

  - 在 78 版至83版本的 Windows 上

  #### 描述

  此策略不起作用，因为它仅作为一种短期机制提供，目的是让企业有更多时间迁移到不依赖于连接网络 API 的第三方软件。 建议使用代理服务器，而不是 LSP 和 Win32 API 修补。

此策略强制网络代码在浏览器进程中运行。

默认情况下，此策略处于禁用状态。 如果启用，则在网络进程被沙盒屏蔽时，用户会遇到安全问题。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ForceNetworkInProcess
  - GP 名称：强制网络代码在浏览器进程中运行（已过时）
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ForceNetworkInProcess
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  

  [返回页首](#microsoft-edge---policies)

  ### ForceSync

  #### 强制同步浏览器数据，但不显示同步许可提示

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 86 或更高版本起

  #### 描述

  强制 Microsoft Edge 中的数据同步。 此策略还会阻止用户关闭同步。

如果未配置此策略，用户将可以启用或禁用同步。 如果启用此策略，用户将不能关闭同步。

若要使此策略按预期工作，[BrowserSignin](#browsersignin) 策略必须配置，或者必须设置为"启用"。 如果 [BrowserSignin](#browsersignin) 设置为"已禁用"，则 [ForceSync](#forcesync) 将不会生效。

[SyncDisabled](#syncdisabled) 不可配置，或者必须设置为 False。 如果设置为 True，则 [ForceSync](#forcesync) 不会生效。

0 = 不会自动启动同步并显示同步许可（默认） 1 = 为 Azure AD/Azure AD 降级用户配置文件启用强制同步，并且不显示同步许可提示

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ForceSync
  - GP 名称：强制同步浏览器数据，但不显示同步许可提示
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ForceSync
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ForceSync
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ForceYouTubeRestrict

  #### 强制最低 YouTube 受限模式

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  对 YouTube 强制实施最低受限模式，并阻止用户选择限制较少的模式。

如果设置为 'Strict'，则将对 YouTube 强制实施严格受限模式。

如果设置为 'Moderate'，则将强制用户对 YouTube 仅使用中等受限模式和严格受限模式。 他们不能禁用受限模式。

如果设置为 'Off' 或未配置此策略，则不对 YouTube 强制实施受限模式。 外部策略（如 YouTube 策略）可能仍会强制实施受限模式。

策略选项映射：

* Off (0) = 不对 YouTube 强制实施受限模式

* Moderate (1) = 至少对 YouTube 强制实施中等受限模式

* Strict (2) = 对 YouTube 强制实施严格受限模式

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ForceYouTubeRestrict
  - GP 名称：强制最低 YouTube 受限模式
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ForceYouTubeRestrict
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：ForceYouTubeRestrict
  - 示例值：
``` xml
<integer>0</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### FullscreenAllowed

  #### 允许全屏模式

  
  
  #### 支持的版本：

  - 在 Windows 上自 77 或更高版本起

  #### 描述

  设置全屏模式的可用性 - 所有 Microsoft Edge UI 都将隐藏，并且仅 Web 内容可见。

如果启用或未配置此策略，则有相应权限的用户、应用和扩展可以进入全屏模式。

如果禁用此策略，则用户、应用和扩展无法进入全屏模式。

禁用全屏模式时，无法使用命令行在展台模式下打开 Microsoft Edge。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：FullscreenAllowed
  - GP 名称：允许全屏模式
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：FullscreenAllowed
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  

  [返回页首](#microsoft-edge---policies)

  ### GloballyScopeHTTPAuthCacheEnabled

  #### 启用全局范围的 HTTP 身份验证缓存

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 81 或更高版本起

  #### 描述

  此策略使用 HTTP 服务器身份验证凭据配置单个全局每配置文件缓存。

如果禁用或未设置此策略，浏览器将使用跨网站身份验证的默认行为，从版本 80 开始，将按热门网站划分 HTTP 服务器身份验证凭据的范围。 因此，如果两个网站使用来自同一身份验证域的资源，则需要在两个网站的上下文中独立提供凭据。 缓存的代理凭据将跨网站重复使用。

如果启用此策略，则在一个网站的上下文中输入的 HTTP 身份验证凭据将自动用于另一个网站的上下文。

启用此策略时，网站会对某些类型的跨网站攻击敞开大门，这些攻击能使用 URL 中嵌入的凭据将条目添加到 HTTP 身份验证缓存中，从而没有 Cookie 就能跨网站跟踪用户。

此策略旨在让依赖于旧行为的企业有机会更新其登录过程，将来会被删除。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：GloballyScopeHTTPAuthCacheEnabled
  - GP 名称：启用全局范围的 HTTP 身份验证缓存
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：GloballyScopeHTTPAuthCacheEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：GloballyScopeHTTPAuthCacheEnabled
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### GoToIntranetSiteForSingleWordEntryInAddressBar

  #### 强制直接 Intranet 站点导航，而不是在地址栏中搜索单个词条

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 78 或更高版本起

  #### 描述

  启用此策略时，如果在地址栏中输入的文本是一个没有标点符号的单词，则地址栏建议列表中最上方的自动建议结果将导航到 Intranet 站点。

键入不带标点符号的单个单词时，默认导航将定向到与输入的文本匹配的 Intranet 站点。

启用此策略时，如果输入的文本是一个没有标点符号的单词，则地址栏建议列表中的第二个自动建议结果将按照确切输入内容执行 Web 搜索。 除非还启用了阻止 Web 搜索的策略，否则将使用默认搜索提供程序。

启用此策略有以下两个影响：

不再导航到网站来响应通常解析为历史记录项的单个单词查询。 相反，浏览器将尝试导航到组织 Intranet 中可能不存在的 Intranet 站点。 这将导致 404 错误。

对于常用的单字搜索词，需要手动选择搜索建议才能正确执行搜索。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：GoToIntranetSiteForSingleWordEntryInAddressBar
  - GP 名称：强制直接 Intranet 站点导航，而不是在地址栏中搜索单个词条
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：GoToIntranetSiteForSingleWordEntryInAddressBar
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：GoToIntranetSiteForSingleWordEntryInAddressBar
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### HSTSPolicyBypassList

  #### 配置将跳过 HSTS 策略检查的名称列表

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 79 或更高版本起

  #### 描述

  此列表中指定的主机名将被排除在 HSTS 策略检查之外，该检查可能会将请求从“http://”升级到“https://”。 此策略中只允许使用单标签主机名。 主机名必须规范化。 任何 IDN 必须转换为其 A 标签格式，所有 ASCII 字母必须为小写。 此策略仅适用于指定的特定主机名；它不适用于列表中名称的子域。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：HSTSPolicyBypassList
  - GP 名称：配置将跳过 HSTS 策略检查的名称列表
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\HSTSPolicyBypassList
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\HSTSPolicyBypassList\1 = "meet"

```

  #### Mac 信息和设置
  
  - 首选项项名称：HSTSPolicyBypassList
  - 示例值：
``` xml
<array>
  <string>meet</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### HardwareAccelerationModeEnabled

  #### 使用硬件加速（如果可用）

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指定使用硬件加速（如果可用）。 如果启用或未配置此策略，则会启用硬件加速，除非 GPU 功能被明确阻止。

如果禁用此策略，则会禁用硬件加速。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：HardwareAccelerationModeEnabled
  - GP 名称：使用硬件加速（如果可用）
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：HardwareAccelerationModeEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：HardwareAccelerationModeEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### HideFirstRunExperience

  #### 隐藏首次运行体验和初始屏幕

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 80 或更高版本起

  #### 描述

  如果启用此策略，则首次运行 Microsoft Edge 时，用户将不会看到首次运行体验和初始屏幕。

对于首次运行体验中显示的配置选项，浏览器将默认为以下内容：

- 在新选项卡页上，源类型将设置为“MSN 新闻”，布局将设置为“鼓舞人心”。

- 如果 Windows 帐户为 Azure AD 或 MSA 类型，用户仍将自动登录到 Microsoft Edge。

-默认情况下不会启用同步，并且系统会提示用户选择是否要在浏览器启动时同步。 可使用 [ForceSync](#forcesync) 或 [SyncDisabled](#syncdisabled) 策略来配置同步和同步许可提示。

如果禁用或未配置此策略，将显示首次运行体验和初始屏幕。

注意：也可以使用其他特定策略管理首次运行体验中向用户显示的特定配置选项。 你可以将 HideFirstRunExperience 策略与这些策略搭配使用，以便在受管理设备上配置特定浏览器体验。 其他一些策略包括：

-[AutoImportAtFirstRun](#autoimportatfirstrun)

-[NewTabPageLocation](#newtabpagelocation)

-[NewTabPageSetFeedType](#newtabpagesetfeedtype)

-[ForceSync](#forcesync)

-[SyncDisabled](#syncdisabled)

-[BrowserSignin](#browsersignin)

-[NonRemovableProfileEnabled](#nonremovableprofileenabled)

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：HideFirstRunExperience
  - GP 名称：隐藏首次运行体验和初始屏幕
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：HideFirstRunExperience
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：HideFirstRunExperience
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### HideInternetExplorerRedirectUXForIncompatibleSitesEnabled

  #### 隐藏一次性重定向对话框和 Microsoft Edge 上的横幅

  
  
  #### 支持的版本：

  - 在 87 版或更高版本的 Windows 上

  #### 描述

  此策略将提供一个可禁用一次性重定向对话框和横幅的选项。 如果启用此策略，用户将不会看到一次性对话框和标题。
当在 Internet Explorer 中遇到不兼容的网站时，用户将继续重定向到 Microsoft Edge，但系统不会导入其浏览数据。

- 如果启用此策略，则一定不会向用户显示一次性重定向对话框和横幅。 发生重定向时，不会导入用户的浏览数据。

- 如果禁用或未设置此策略，系统会在首次重定向时显示重定向对话框，且对于以重定向开始的会话，系统将持续向用户显示重定向横幅。 每次用户遇到此类重定向时，都将导入用户的浏览数据（仅当用户在一次性对话框上同意重定向时）。


  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：HideInternetExplorerRedirectUXForIncompatibleSitesEnabled
  - GP 名称：隐藏一次性重定向对话框和 Microsoft Edge 上的横幅
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：HideInternetExplorerRedirectUXForIncompatibleSitesEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  

  [返回页首](#microsoft-edge---policies)

  ### ImportAutofillFormData

  #### 允许导入自动填充表单数据

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  允许用户将自动填充表单数据从另一个浏览器导入到 Microsoft Edge。

如果启用此策略，则会自动选中手动导入自动填充数据的选项。

如果禁用此策略，则首次运行时不会导入自动填充表单数据，并且用户不能手动导入这些数据。

如果未配置此策略，则首次运行时将导入自动填充数据，在以后的浏览会话期间，用户可以选择是否手动导入此数据。

可将此策略设置为建议。 这意味着 Microsoft Edge 将在首次运行时导入自动填充数据，但用户可以在手动导入期间选择或清除**自动填充数据**选项。

**注意**：此策略当前管理从 Google Chrome（Windows 7、8 和 10 以及 macOS 上）和 Mozilla Firefox（Windows 7、8 和 10 以及 macOS 上）浏览器导入。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ImportAutofillFormData
  - GP 名称：允许导入自动填充表单数据
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：ImportAutofillFormData
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ImportAutofillFormData
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ImportBrowserSettings

  #### 允许导入浏览器设置

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 78 或更高版本起

  #### 描述

  允许用户将浏览器设置从另一个浏览器导入到 Microsoft Edge。

如果启用此策略，将在“**导入浏览器数据**”对话框中自动选中“**浏览器设置**”复选框。

如果禁用此策略，则首次运行时不会导入浏览器设置，而且用户不能手动导入它们。

如果未配置此策略，则首次运行时将导入浏览器设置，在以后的浏览会话期间，用户可以选择是否手动导入它们。

还可将此策略设置为建议。 这意味着 Microsoft Edge 在首次运行时将导入设置，但用户可以在手动导入期间选择或清除**浏览器设置**选项。

**注意**：此策略当前管理导入 Google Chrome（在 Windows 7、8 和 10 以及 macOS 上）。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ImportBrowserSettings
  - GP 名称：允许导入浏览器设置
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：ImportBrowserSettings
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ImportBrowserSettings
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ImportCookies

  #### 允许导入 Cookie

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 81 或更高版本起

  #### 描述

  允许用户将 Cookie 从另一个浏览器导入到 Microsoft Edge。

如果禁用此策略，则首次运行时不会导入 Cookie。

如果未配置此策略，则首次运行时将导入 Cookie。

还可将此策略设置为建议。 这意味着 Microsoft Edge 在首次运行时将导入 Cookie。

**注意**：此策略当前管理导入 Google Chrome（在 Windows 7、8 和 10 以及 macOS 上）。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ImportCookies
  - GP 名称：允许导入 Cookie
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：ImportCookies
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ImportCookies
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ImportExtensions

  #### 允许导入扩展

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 81 或更高版本起

  #### 描述

  允许用户将扩展从另一个浏览器导入到 Microsoft Edge。

如果启用此策略，将在“**导入浏览器数据**”对话框中自动选中“**扩展**”复选框。

如果禁用此策略，则首次运行时不会导入扩展，而且用户不能手动导入它们。

如果未配置此策略，则首次运行时将导入扩展，在以后的浏览会话期间，用户可以选择是否手动导入它们。

还可将此策略设置为建议。 这意味着 Microsoft Edge 在首次运行时将导入扩展，但用户可以在手动导入期间选择或清除**收藏夹**选项。

**注意**：此策略目前仅支持从 Google Chrome（在 Windows 7、8、10和 macOS 上）导入。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ImportExtensions
  - GP 名称：允许导入扩展
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：ImportExtensions
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ImportExtensions
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ImportFavorites

  #### 允许导入收藏夹

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  允许用户将收藏夹从另一个浏览器导入 Microsoft Edge。

如果启用此策略，将在“**导入浏览器数据**”对话框中自动选中“**收藏夹**”复选框。

如果禁用此策略，则首次运行时不会导入收藏夹，而且用户不能手动导入它们。

如果未配置此策略，则首次运行时将导入收藏夹，在以后的浏览会话期间，用户可以选择是否手动导入它们。

还可将此策略设置为建议。 这意味着 Microsoft Edge 在首次运行时将导入收藏夹，但用户可以在手动导入期间选择或清除**收藏夹**选项。

**注意**：此策略当前管理从 Internet Explorer（Windows 7、8 和 10 上）、Google Chrome（在 Windows 7、8 和 10 上以及 macOS 上）、Mozilla Firefox（Windows 7、8 和 10 上以及 macOS 上）和 Apple Safari（macOS 上）浏览器导入。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ImportFavorites
  - GP 名称：允许导入收藏夹
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：ImportFavorites
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ImportFavorites
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ImportHistory

  #### 允许导入浏览历史记录

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  允许用户将浏览历史记录从另一个浏览器导入到 Microsoft Edge。

如果启用此策略，将在“**导入浏览器数据**”对话框中自动选中“**浏览历史记录**”复选框。

如果禁用此策略，则首次运行时不会导入浏览历史记录数据，并且用户不能手动导入此数据。

如果未配置此策略，则首次运行时将导入浏览历史记录数据，在以后的浏览会话期间，用户可以选择是否手动导入此数据。

还可将此策略设置为建议。 这意味着 Microsoft Edge 在首次运行时将导入浏览历史记录，但用户可以在手动导入期间选择或清除**历史记录**选项。

**注意**：此策略当前管理从 Internet Explorer（Windows 7、8 和 10 上）、Google Chrome（在 Windows 7、8 和 10 上以及 macOS 上）、Mozilla Firefox（Windows 7、8 和 10 上以及 macOS 上）和 Apple Safari (macOS) 浏览器导入。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ImportHistory
  - GP 名称：允许导入浏览历史记录
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：ImportHistory
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ImportHistory
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ImportHomepage

  #### 允许导入主页设置

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  允许用户将主页设置从另一个浏览器导入到 Microsoft Edge。

如果启用此策略，则会自动选中手动导入主页设置的选项。

如果禁用此策略，则首次运行时不会导入主页设置，并且用户不能手动导入它们。

如果未配置此策略，则首次运行时将导入主页设置，在以后的浏览会话期间，用户可以选择是否手动导入此数据。

可将此策略设置为建议。 这意味着 Microsoft Edge 在首次运行时将导入主页设置，但用户可以在手动导入期间选择或清除**主页**选项。

**注意**：此策略当前管理从 Internet Explorer（在 Windows 7、8 和 10 上）导入。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ImportHomepage
  - GP 名称：允许导入主页设置
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ImportHomepage
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ImportHomepage
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ImportOpenTabs

  #### 允许导入打开的选项卡

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 79 或更高版本起

  #### 描述

  允许用户将打开和固定的选项卡从另一个浏览器导入到 Microsoft Edge。

如果启用此策略，将在“**导入浏览器数据**”对话框中自动选中“**打开的选项卡**”复选框。

如果禁用此策略，则首次运行时不会导入打开的选项卡，而且用户不能手动导入它们。

如果未配置此策略，则首次运行时将导入打开的选项卡，在以后的浏览会话期间，用户可以选择是否手动导入它们。

还可将此策略设置为建议。 这意味着 Microsoft Edge 在首次运行时将导入打开的选项卡，但用户可以在手动导入期间选择或清除“**打开的选项卡**”选项。

**注意**：此策略目前仅支持从 Google Chrome（在 Windows 7、8、10和 macOS 上）导入。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ImportOpenTabs
  - GP 名称：允许导入打开的选项卡
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：ImportOpenTabs
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ImportOpenTabs
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ImportPaymentInfo

  #### 允许导入付款信息

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  允许用户将付款信息从另一个浏览器导入到 Microsoft Edge。

如果启用此策略，将在“**导入浏览器数据**”对话框中自动选中“**付款信息**”复选框。

如果禁用此策略，则首次运行时不会导入付款信息，并且用户不能手动导入该信息。

如果未配置此策略，则首次运行时将导入付款信息，在以后的浏览会话期间，用户可以选择是否手动导入该信息。

还可将此策略设置为建议。 这意味着 Microsoft Edge 在首次运行时将导入付款信息，但用户可以在手动导入期间选择或清除“**付款信息**”选项。

**注意：** 此策略目前管理从 Google Chrome（Windows 7、8 和 10 以及 macOS 上）导入。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ImportPaymentInfo
  - GP 名称：允许导入付款信息
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：ImportPaymentInfo
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ImportPaymentInfo
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ImportSavedPasswords

  #### 允许导入保存的密码

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  允许用户将保存的密码从另一个浏览器导入到 Microsoft Edge。

如果启用此策略，则会自动选中手动导入保存的密码的选项。

如果禁用此策略，则首次运行时不会导入保存的密码，而且用户不能手动导入它们。

如果未配置此策略，则首次运行时将导入密码，在以后的浏览会话期间，用户可以选择是否手动导入它们。

可将此策略设置为建议。 这意味着 Microsoft Edge 在首次运行时将导入密码，但用户可以在手动导入期间选择或清除“**密码**”选项。

**注意**：此策略当前管理从 Internet Explorer（Windows 7、8 和 10 上）、Google Chrome（在 Windows 7、8 和 10 上以及 macOS 上）和 Mozilla Firefox（Windows 7、8 和 10 上以及 macOS 上）浏览器导入。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ImportSavedPasswords
  - GP 名称：允许导入保存的密码
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：ImportSavedPasswords
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ImportSavedPasswords
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ImportSearchEngine

  #### 允许导入搜索引擎设置

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  允许用户将搜索引擎设置从另一个浏览器导入到 Microsoft Edge。

如果启用此策略，则会自动选中导入搜索引擎设置的选项。

如果禁用此策略，则首次运行时不会导入搜索引擎设置，而且用户不能手动导入它们。

如果未配置此策略，则首次运行时将导入搜索引擎设置，在以后的浏览会话期间，用户可以选择是否手动导入此数据。

可将此策略设置为建议。 这意味着 Microsoft Edge 在首次运行时将导入搜索引擎设置，但用户可以在手动导入期间选择或清除“**搜索引擎**”选项。

**注意**：此策略当前管理从 Internet Explorer（在 Windows 7、8 和 10 上）导入。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ImportSearchEngine
  - GP 名称：允许导入搜索引擎设置
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：ImportSearchEngine
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ImportSearchEngine
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ImportShortcuts

  #### 允许导入快捷方式

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 81 或更高版本起

  #### 描述

  允许用户将快捷方式从另一个浏览器导入 Microsoft Edge。

如果禁用此策略，则首次运行时不会导入快捷方式。

如果未配置此策略，则首次运行时将导入快捷方式。

还可将此策略设置为建议。 这意味着 Microsoft Edge 在首次运行时将导入快捷方式。

**注意**：此策略目前管理从 Google Chrome（Windows 7、8 和 10 以及 macOS 上）导入。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ImportShortcuts
  - GP 名称：允许导入快捷方式
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：ImportShortcuts
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ImportShortcuts
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### InPrivateModeAvailability

  #### 配置 InPrivate 模式可用性

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指定用户是否可以在 Microsoft Edge 中以 InPrivate 模式打开页面。

如果未配置此策略或将其设置为 'Enabled'，则用户可以以 InPrivate 模式打开页面。

将此策略设置为 'Disabled' 可阻止用户使用 InPrivate 模式。

将此策略设置为 'Forced' 可始终使用 InPrivate 模式。

策略选项映射：

* Enabled (0) = InPrivate 模式可用

* Disabled (1) = 禁用 InPrivate 模式

* Forced (2) = 强制 InPrivate 模式

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：InPrivateModeAvailability
  - GP 名称：配置 InPrivate 模式可用性
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：InPrivateModeAvailability
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：InPrivateModeAvailability
  - 示例值：
``` xml
<integer>1</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### InsecureFormsWarningsEnabled

  #### 启用不安全窗体的警告

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 86 或更高版本起

  #### 描述

  此策略控制嵌入浏览器中安全（HTTPS）网站的非安全窗体（通过 HTTP 提交的窗体）的处理。
如果启用此策略或不对其进行设置，则在提交不安全窗体时将显示完整的页面警告。 此外，如果窗体域获得焦点，将在窗体域旁显示警告气泡，并且将对这些窗体禁用自动填充。
如果禁用此策略，则不会显示不安全窗体的警告，并且自动填充将正常工作。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：InsecureFormsWarningsEnabled
  - GP 名称：启用不安全窗体的警告
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：InsecureFormsWarningsEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：InsecureFormsWarningsEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### IntensiveWakeUpThrottlingEnabled

  #### 控制 IntensiveWakeUpThrottling 的功能

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 85 或更高版本起

  #### 描述

  启用了 IntensiveWakeUpThrottling 特性时，背景标签中的Javascript 计时器会被强制地调节和合并，在页面背景关闭 5 分钟或更长时间后，每分钟运行不超过一次。

这是一个与 web 标准兼容的功能，但它可能会导致某些网站的某些操作延迟一分钟。 但是，启用它可以显著地节省CPU和电池。 有关更多详细信息，请参阅https://bit.ly/30b1XR4。

如果启用此策略，将强制启用该功能，用户将无法覆盖此设置。
如果禁用此策略，将强制禁用该功能，用户将无法覆盖此设置。
如果未配置此策略，该功能将由其自己的内部逻辑控制。 用户可以手动配置此设置。

请注意，每个体现程序将应用此策略，策略设置的最新值在呈现程序启动时生效。 若要确保所有加载的选项卡均会收到一致的策略设置，则需要完全重启。 使用此策略的不同值运行的进程是无害的。


  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称： IntensiveWakeUpThrottlingEnabled
  - GP 名称：控制 IntensiveWakeUpThrottling 功能
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称： IntensiveWakeUpThrottlingEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选参数名称： IntensiveWakeUpThrottlingEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### InternetExplorerIntegrationEnhancedHangDetection

  #### 为 Internet Explorer 模式配置增强的挂起检测

  
  
  #### 支持的版本：

  - 在 84 版或更高版本的 Windows 上

  #### 描述

  与独立的 Internet Explorer 相比，增强的挂起检测是一种更精细的方法来检测 Internet Explorer 模式下挂起的网页。 检测到挂起的网页时，浏览器将应用缓解措施，防止其余浏览器挂起。

通过此设置，可配置增强型挂起检测的使用情况，以防遇到与任何网站不兼容的问题。 当你在 Internet Explorer 模式看到通知，如“(网站)没有响应”，但不是在独立的 Internet Explorer，我们建议你禁用此政策。

此设置与以下策略配合使用：[InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel) （设置为 'IEMode'） 和 [InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist) 策略 （列表至少有一个条目）。

如果你将此策略设置为 'Enabled' 或未进行配置，则在 Internet Explorer 模式下运行的网站将使用增强挂起检测。

如果将此策略设置为 'Disabled'，则禁用增强挂起检测，用户将获得基本的 Internet Explorer 挂起检测状态。

要了解有关 Internet Explorer 模式的详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)

策略选项映射：

* Disabled (0) = 禁用 "增强挂起检测"

* Enabled (1) = 启用 "增强挂起检测"

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：InternetExplorerIntegrationEnhancedHangDetection
  - GP 名称：针对 Internet Explorer 模式配置增强型挂起检测
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称： InternetExplorerIntegrationEnhancedHangDetection
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  

  [返回页首](#microsoft-edge---policies)

  ### InternetExplorerIntegrationLevel

  #### 配置 Internet Explorer 集成

  
  
  #### 支持的版本：

  - 在 Windows 上自 77 或更高版本起

  #### 描述

  有关配置 Internet Explorer 模式的最佳体验的指南，请参阅 [https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)

策略选项映射：

* None (0) = None

* IEMode (1) = Internet Explorer 模式

* NeedIE (2) = Internet Explorer 11

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：InternetExplorerIntegrationLevel
  - GP 名称：配置 Internet Explorer 集成
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：InternetExplorerIntegrationLevel
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  

  [返回页首](#microsoft-edge---policies)

  ### InternetExplorerIntegrationSiteList

  #### 配置企业模式站点列表

  
  
  #### 支持的版本：

  - 在 Windows 上自 78 或更高版本起

  #### 描述

  有关配置 Internet Explorer 模式的最佳体验的指南，请参阅 [https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：InternetExplorerIntegrationSiteList
  - GP 名称：配置企业模式站点列表
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：InternetExplorerIntegrationSiteList
  - 值类型：REG_SZ

  ##### 示例值：

```
"https://internal.contoso.com/sitelist.xml"
```

  

  [返回页首](#microsoft-edge---policies)

  ### InternetExplorerIntegrationSiteRedirect

  #### 指定从 Internet Explorer 模式页面启动时未配置网站的“页内”导航行为

  
  
  #### 支持的版本：

  - 在 Windows 上自 81 或更高版本起

  #### 描述

  “页内”导航将从当前页上的链接、脚本或窗体启动。 它也可以是上次“页内”导航尝试的服务器端重定向。 相反，用户可以使用浏览器控件通过多种方式进行与当前页面无关的非“页内”导航。 例如，使用地址栏、返回按钮或收藏夹链接。

通过此设置，可指定从以 Internet Explorer 模式加载的页面到未配置的网站（未在企业模式站点列表中配置）的导航是切换回 Microsoft Edge，还是保留在 Internet Explorer 模式下。

此设置与以下策略配合使用：[InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel) （设置为 'IEMode'） 和 [InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist) 策略 （列表至少有一个条目）。

如果禁用或未配置此策略，则只有配置为在 Internet Explorer 模式下打开的网站才会在该模式下打开。 任何未配置为在 Internet Explorer 模式下打开的网站都将重定向回 Microsoft Edge。

如果将此策略设置为“默认”，则只有配置为在 Internet Explorer 模式下打开的网站才会在该模式下打开。 任何未配置为在 Internet Explorer 模式下打开的网站都将重定向回 Microsoft Edge。

如果将此策略设置为 AutomaticNavigationsOnly，则你将获得默认体验，但所有未配置站点的自动导航（如 302 重定向）将保持 Internet Explorer 模式。

如果将此策略设置为 AllInPageNavigations，则从以 IE 模式加载的页面到未配置的网站的所有导航都将保持 Internet Explorer 模式（最不推荐）。

要了解有关 Internet Explorer 模式的详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2105106](https://go.microsoft.com/fwlink/?linkid=2105106)

策略选项映射：

* Default (0) = 默认值

* AutomaticNavigationsOnly (1) = 仅保留 Internet Explorer 模式下的自动导航

* AllInPageNavigations (2) = 使所有页内导航保持 Internet Explorer 模式

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：InternetExplorerIntegrationSiteRedirect
  - GP 名称：指定从 Internet Explorer 模式页面启动时未配置网站的“页内”导航行为
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：InternetExplorerIntegrationSiteRedirect
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  

  [返回页首](#microsoft-edge---policies)

  ### InternetExplorerIntegrationTestingAllowed

  #### 允许 Internet Explorer 模式测试

  
  
  #### 支持的版本：

  - 在 86 版或更高版本的 Windows 上

  #### 描述

  通过使用此策略，用户可以在 Microsoft Edge 中打开 Internet Explorer 模式选项卡，在 Internet Explorer 模式下测试应用程序。

用户可以通过选择 "在 Internet Explorer 模式下打开网站"，在 "更多工具" 菜单内执行此操作。

此外，用户可以在新式浏览器中使用“在Edge模式下打开网站”选项来测试其应用程序，而无需删除网站列表中的应用程序。

此设置与以下策略配合使用：[InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel) （设置为 'IEMode'） 和 [InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist) 策略 （列表至少有一个条目）。

如果启用此策略，则 "更多工具" 下将显示 "在 Internet Explorer 模式中打开网站" 选项。 用户可在此选项卡上的 Internet Explorer 模式下查看其网站。"更多工具" 下的 "以Microsoft Edge 模式打开网站" 的另一个选项也会显示出来，以便在现代浏览器中测试网站，而无需将其从网站列表中删除。

如果禁用或未配置此策略，用户将看不到 "在 Internet Explorer 模式中打开" 和 "在Microsoft Edge 模式下打开" 选项，然后单击 "更多工具" 菜单。 但是，用户可以使用--ie-mode-test标志配置这些选项。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：InternetExplorerIntegrationTestingAllowed
  - GP 名称：允许 Internet Explorer 模式测试
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：InternetExplorerIntegrationTestingAllowed
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  

  [返回页首](#microsoft-edge---policies)

  ### IsolateOrigins

  #### 针对特定源启用网站隔离

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指定要在各自进程中单独运行的源。

此策略还会隔离由子域命名的源 - 例如，指定 https://contoso.com/ 将导致 https://foo.contoso.com/ 作为 https://contoso.com/ 站点的一部分被隔离。

如果启用该策略，则逗号分隔列表中的每个命名源将在其自己的进程中运行。

如果禁用此策略，则“IsolateOrigins”和“SitePerProcess”功能都将被禁用。 用户仍然可以通过命令行标志手动启用“IsolateOrigins”策略。

如果未配置该策略，则用户可以更改此设置。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：IsolateOrigins
  - GP 名称：针对特定源启用网站隔离
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：IsolateOrigins
  - 值类型：REG_SZ

  ##### 示例值：

```
"https://contoso.com/,https://fabrikam.com/"
```

  #### Mac 信息和设置
  
  - 首选项项名称：IsolateOrigins
  - 示例值：
``` xml
<string>https://contoso.com/,https://fabrikam.com/</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### LocalProvidersEnabled

  #### 允许来自本地提供程序的建议

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 83 或更高版本起

  #### 描述

  在 Microsoft Edge 的地址栏和自动建议列表中允许来自设备上的建议提供程序（本地提供程序，例如收藏夹和浏览历史记录）的建议。

如果启用此策略，则将使用本地提供程序的建议。

如果禁用此策略，则不会使用本地提供程序的建议。 不会显示本地历史记录和本地收藏夹建议。

如果未配置此策略，则允许来自本地提供程序的建议，但用户可以使用设置开关进行更改。

请注意，如果应用了禁用此功能的策略，则某些功能可能不可用。 例如，如果启用 [SavingBrowserHistoryDisabled](#savingbrowserhistorydisabled) 策略，则浏览历史记录建议将不可用。

此策略需要重新启动浏览器才能完成应用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：LocalProvidersEnabled
  - GP 名称：允许来自本地提供程序的建议
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：LocalProvidersEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：LocalProvidersEnabled
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ManagedFavorites

  #### 配置收藏夹

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  配置受管收藏夹列表。

该策略将创建收藏夹列表。 每个收藏夹都包含“name”和“url”项，它们用于保存收藏夹的名称及其目标。 可通过定义一个不带“url”项、但带有附加“children”项的收藏夹来配置一个子文件夹，其包含上面定义的收藏夹列表（其中一些收藏夹可能会再次成为文件夹）。 Microsoft Edge 将修正不完整的 URL，就像它们是通过地址栏提交的一样，例如，“microsoft.com”变为“https://microsoft.com/”。

这些收藏夹放置在用户无法修改的文件夹中（但用户可以选择从收藏夹栏中隐藏它）。 默认情况下，文件夹名称是“受管收藏夹”，但你可以通过向收藏夹列表添加一个字典来更改它，该字典包含“topleval_name”项并且以所需文件夹名称作为值。

受管收藏夹不会同步到用户帐户，并且无法通过扩展进行修改。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - Dictionary

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ManagedFavorites
  - GP 名称：配置收藏夹
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ManagedFavorites
  - 值类型：REG_SZ

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\ManagedFavorites = [
  {
    "toplevel_name": "My managed favorites folder"
  }, 
  {
    "name": "Microsoft", 
    "url": "microsoft.com"
  }, 
  {
    "name": "Bing", 
    "url": "bing.com"
  }, 
  {
    "children": [
      {
        "name": "Microsoft Edge Insiders", 
        "url": "www.microsoftedgeinsider.com"
      }, 
      {
        "name": "Microsoft Edge", 
        "url": "www.microsoft.com/windows/microsoft-edge"
      }
    ], 
    "name": "Microsoft Edge links"
  }
]
```

  ##### 精简示例值：

  ```
  SOFTWARE\Policies\Microsoft\Edge\ManagedFavorites = [{"toplevel_name": "My managed favorites folder"}, {"name": "Microsoft", "url": "microsoft.com"}, {"name": "Bing", "url": "bing.com"}, {"children": [{"name": "Microsoft Edge Insiders", "url": "www.microsoftedgeinsider.com"}, {"name": "Microsoft Edge", "url": "www.microsoft.com/windows/microsoft-edge"}], "name": "Microsoft Edge links"}]
  ```
  

  #### Mac 信息和设置
  
  - 首选项项名称：ManagedFavorites
  - 示例值：
``` xml
<key>ManagedFavorites</key>
<array>
  <dict>
    <key>toplevel_name</key>
    <string>My managed favorites folder</string>
  </dict>
  <dict>
    <key>name</key>
    <string>Microsoft</string>
    <key>url</key>
    <string>microsoft.com</string>
  </dict>
  <dict>
    <key>name</key>
    <string>Bing</string>
    <key>url</key>
    <string>bing.com</string>
  </dict>
  <dict>
    <key>children</key>
    <array>
      <dict>
        <key>name</key>
        <string>Microsoft Edge Insiders</string>
        <key>url</key>
        <string>www.microsoftedgeinsider.com</string>
      </dict>
      <dict>
        <key>name</key>
        <string>Microsoft Edge</string>
        <key>url</key>
        <string>www.microsoft.com/windows/microsoft-edge</string>
      </dict>
    </array>
    <key>name</key>
    <string>Microsoft Edge links</string>
  </dict>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ManagedSearchEngines

  #### 管理搜索引擎

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  可配置最多包含 10 个搜索引擎的列表，其中一个必须标记为默认搜索引擎。
不需要指定编码。 从 Microsoft Edge 80 开始，suggest_url 和 image_search_url 参数是可选的。 从 Microsoft Edge 80 开始，可使用可选参数 image_search_post_params（由逗号分隔的名称/值对组成）。

从 Microsoft Edge 83 开始，可使用 allow_search_enger_discovery 可选参数启用搜索引擎发现。 此参数必须是列表中的第一项。 如果未指定 allow_search_enger_discovery，则默认情况下将禁用搜索引擎发现。 从 Microsoft Edge 84 开始，你可以将此策略设置为允许搜索提供程序发现的建议策略。 无需添加 allow_search_engine_discovery 可选参数。

如果启用此策略，用户将无法在列表中添加、删除或更改任何搜索引擎。 用户可以将其默认搜索引擎设置为列表中的任何搜索引擎。

如果禁用或未配置此策略，用户可以根据需要修改搜索引擎列表。

如果设置了 [DefaultSearchProviderSearchURL](#defaultsearchprovidersearchurl) 策略，则此策略 (ManagedSearchEngines) 将被忽略。 用户必须重新启动浏览器才能完成应用此策略。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - Dictionary

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ManagedSearchEngines
  - GP 名称：管理搜索引擎
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：ManagedSearchEngines
  - 值类型：REG_SZ

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\ManagedSearchEngines = [
  {
    "allow_search_engine_discovery": true
  }, 
  {
    "is_default": true, 
    "keyword": "example1.com", 
    "name": "Example1", 
    "search_url": "https://www.example1.com/search?q={searchTerms}", 
    "suggest_url": "https://www.example1.com/qbox?query={searchTerms}"
  }, 
  {
    "image_search_post_params": "content={imageThumbnail},url={imageURL},sbisrc={SearchSource}", 
    "image_search_url": "https://www.example2.com/images/detail/search?iss=sbiupload", 
    "keyword": "example2.com", 
    "name": "Example2", 
    "search_url": "https://www.example2.com/search?q={searchTerms}", 
    "suggest_url": "https://www.example2.com/qbox?query={searchTerms}"
  }, 
  {
    "encoding": "UTF-8", 
    "image_search_url": "https://www.example3.com/images/detail/search?iss=sbiupload", 
    "keyword": "example3.com", 
    "name": "Example3", 
    "search_url": "https://www.example3.com/search?q={searchTerms}", 
    "suggest_url": "https://www.example3.com/qbox?query={searchTerms}"
  }, 
  {
    "keyword": "example4.com", 
    "name": "Example4", 
    "search_url": "https://www.example4.com/search?q={searchTerms}"
  }
]
```

  ##### 精简示例值：

  ```
  SOFTWARE\Policies\Microsoft\Edge\ManagedSearchEngines = [{"allow_search_engine_discovery": true}, {"is_default": true, "keyword": "example1.com", "name": "Example1", "search_url": "https://www.example1.com/search?q={searchTerms}", "suggest_url": "https://www.example1.com/qbox?query={searchTerms}"}, {"image_search_post_params": "content={imageThumbnail},url={imageURL},sbisrc={SearchSource}", "image_search_url": "https://www.example2.com/images/detail/search?iss=sbiupload", "keyword": "example2.com", "name": "Example2", "search_url": "https://www.example2.com/search?q={searchTerms}", "suggest_url": "https://www.example2.com/qbox?query={searchTerms}"}, {"encoding": "UTF-8", "image_search_url": "https://www.example3.com/images/detail/search?iss=sbiupload", "keyword": "example3.com", "name": "Example3", "search_url": "https://www.example3.com/search?q={searchTerms}", "suggest_url": "https://www.example3.com/qbox?query={searchTerms}"}, {"keyword": "example4.com", "name": "Example4", "search_url": "https://www.example4.com/search?q={searchTerms}"}]
  ```
  

  #### Mac 信息和设置
  
  - 首选项项名称：ManagedSearchEngines
  - 示例值：
``` xml
<key>ManagedSearchEngines</key>
<array>
  <dict>
    <key>allow_search_engine_discovery</key>
    <true/>
  </dict>
  <dict>
    <key>is_default</key>
    <true/>
    <key>keyword</key>
    <string>example1.com</string>
    <key>name</key>
    <string>Example1</string>
    <key>search_url</key>
    <string>https://www.example1.com/search?q={searchTerms}</string>
    <key>suggest_url</key>
    <string>https://www.example1.com/qbox?query={searchTerms}</string>
  </dict>
  <dict>
    <key>image_search_post_params</key>
    <string>content={imageThumbnail},url={imageURL},sbisrc={SearchSource}</string>
    <key>image_search_url</key>
    <string>https://www.example2.com/images/detail/search?iss=sbiupload</string>
    <key>keyword</key>
    <string>example2.com</string>
    <key>name</key>
    <string>Example2</string>
    <key>search_url</key>
    <string>https://www.example2.com/search?q={searchTerms}</string>
    <key>suggest_url</key>
    <string>https://www.example2.com/qbox?query={searchTerms}</string>
  </dict>
  <dict>
    <key>encoding</key>
    <string>UTF-8</string>
    <key>image_search_url</key>
    <string>https://www.example3.com/images/detail/search?iss=sbiupload</string>
    <key>keyword</key>
    <string>example3.com</string>
    <key>name</key>
    <string>Example3</string>
    <key>search_url</key>
    <string>https://www.example3.com/search?q={searchTerms}</string>
    <key>suggest_url</key>
    <string>https://www.example3.com/qbox?query={searchTerms}</string>
  </dict>
  <dict>
    <key>keyword</key>
    <string>example4.com</string>
    <key>name</key>
    <string>Example4</string>
    <key>search_url</key>
    <string>https://www.example4.com/search?q={searchTerms}</string>
  </dict>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### MaxConnectionsPerProxy

  #### 代理服务器的最大并发连接数

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指定同时连接到代理服务器的最大连接数。

某些代理服务器无法处理每个客户端大量并发连接 - 可通过将此策略设置为较低的值来解决此问题。

此策略的值应低于 100、高于 6。 默认值为 32。

众所周知，某些 Web 应用会通过挂起的 GET 占用多个连接 - 如果这些类型的 Web 应用中有太多处于打开状态，则将最大连接数降低到 32 以下可能会导致浏览器网络挂起。

如果未配置此策略，则使用默认值 (32)。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：MaxConnectionsPerProxy
  - GP 名称：代理服务器的最大并发连接数
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：MaxConnectionsPerProxy
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000020
```

  #### Mac 信息和设置
  
  - 首选项项名称：MaxConnectionsPerProxy
  - 示例值：
``` xml
<integer>32</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### MediaRouterCastAllowAllIPs

  #### 允许 Google Cast 连接到所有 IP 地址上的 Cast 设备

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  启用此策略时，可让 Google Cast 连接到所有 IP 地址上的 Cast 设备，而不仅仅是 RFC1918/RFC4193 专用地址。

禁用此策略时，可将 Google Cast 限制为 RFC1918/RFC4193 专用地址上的 Cast 设备。

如果未配置此策略，除非启用了 CastAllowAllIPs 功能，否则 Google Cast 仅连接到 RFC1918/RFC4193 专用地址上的 Cast 设备。

如果 [EnableMediaRouter](#enablemediarouter) 策略已禁用，则此策略将不起作用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：MediaRouterCastAllowAllIPs
  - GP 名称：允许 Google Cast 连接到所有 IP 地址上的 Cast 设备
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：MediaRouterCastAllowAllIPs
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：MediaRouterCastAllowAllIPs
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### MetricsReportingEnabled

  #### 启用使用情况和故障相关数据报告（已弃用）

  >已弃用：此策略已弃用。 当前受支持，但将在未来的版本中弃用。
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  此策略已弃用。 当前受支持，但在 Microsoft Edge 89 版本中将过时。 对于 Windows 7、Windows 8 和 macOS，此策略替换为新策略：[DiagnosticData](#diagnosticdata)。 对于 Win 10 ([https://go.microsoft.com/fwlink/?linkid=2099569](https://go.microsoft.com/fwlink/?linkid=2099569))，此策略替换为“允许遥测”。

此策略允许向 Microsoft 发送关于 Microsoft Edge 的使用情况和故障相关数据的报告。

启用此策略可向 Microsoft 发送使用情况和故障相关数据的报告。 禁用此策略可以不将数据发送给 Microsoft。 在这两种情况下，用户不能更改或覆盖设置。

在 Windows 10 上，如果未配置此策略，Microsoft Edge 将默认使用 Windows 诊断数据设置。 如果启用此策略，只有当 Windows 诊断数据设置设为“增强”或“完全”时，Microsoft Edge 才会发送使用情况数据。 如果禁用此策略，Microsoft Edge 将不会发送使用情况数据。 基于 Windows 诊断数据设置发送故障相关数据。 有关 Windows 诊断数据设置的详细信息，请访问 [https://go.microsoft.com/fwlink/?linkid=2099569](https://go.microsoft.com/fwlink/?linkid=2099569)

在 Windows 7、Windows 8 和 macOS 上，此策略控制使用情况和故障相关数据的发送。 如果未配置此策略，Microsoft Edge 将默认使用用户首选项。

若要启用此策略，必需将 [SendSiteInfoToImproveServices](#sendsiteinfotoimproveservices) 设置为“启用”。 如果 [MetricsReportingEnabled](#metricsreportingenabled) 或 [SendSiteInfoToImproveServices](#sendsiteinfotoimproveservices) 未配置或已禁用，则不会将此数据发送到 Microsoft。

此策略仅在加入 Microsoft Active Directory 域的 Windows 实例、已注册设备管理的 Windows 10 专业版或企业版实例，或者通过 MDM 托管或通过 MCX 加入域的 macOS 实例上可用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：MetricsReportingEnabled
  - GP 名称：启用使用情况和故障相关数据报告（已弃用）
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：MetricsReportingEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：MetricsReportingEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### NativeWindowOcclusionEnabled

  #### 启用本机窗口封闭

  
  
  #### 支持的版本：

  - 在 84 版或更高版本的 Windows 上

  #### 描述

  在 Microsoft Edge 中启用本机窗口封闭。

如果启用此设置，为了降低 CPU 使用率和功耗，Microsoft Edge 将检测窗口何时被其他窗口覆盖，并将暂停工作绘制像素。

如果禁用此设置，Microsoft Edge 将不会检测窗口何时被其他窗口覆盖。

如果未设置此策略，则将启用窗口隐藏检测。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：NativeWindowOcclusionEnabled
  - GP 名称：启用本机窗口封闭
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：NativeWindowOcclusionEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  

  [返回页首](#microsoft-edge---policies)

  ### NavigationDelayForInitialSiteListDownloadTimeout

  #### 为企业模式站点列表设置延迟选项卡导航延迟的超时

  
  
  #### 支持的版本：

  - 在 84 版或更高版本的 Windows 上

  #### 描述

  允许你设置一个超时（以秒为单位），以使  Microsoft Edge 选项卡一直等到浏览器下载了初始企业模式站点列表。

此设置与以下策略配合使用：[InternetExplorerIntegrationLevel](#internetexplorerintegrationlevel)（设置为 'IEMode'）、[InternetExplorerIntegrationSiteList](#internetexplorerintegrationsitelist) 策略（列表至少有一个条目）和 [DelayNavigationsForInitialSiteListDownload](#delaynavigationsforinitialsitelistdownload)（设置为 "All eligible navigations" (1)）。

选项卡等待企业模式站点列表下载的时间不会等多过此超时。 如果浏览器在超时时未完成下载企业模式网站列表， Microsoft Edge 选项卡将继续导航。 超时的值应该不大于20秒，也不小于1秒。

如果将此策略中的超时设置为大于默认值2秒的值，则会在2秒后向用户显示一个信息栏。 信息栏包含一个按钮，允许用户停止等待企业模式站点列表下载完成。

如果未配置此策略，将使用默认的2秒超时。 此默认设置可能会在将来更改。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称： NavigationDelayForInitialSiteListDownloadTimeout
  - GP 名称：为企业模式站点列表的选项卡导航设置延迟超时
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称： NavigationDelayForInitialSiteListDownloadTimeout
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x0000000a
```

  

  [返回页首](#microsoft-edge---policies)

  ### NetworkPredictionOptions

  #### 启用网络预测

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  启用网络预测并阻止用户更改此设置。

这样可控制 DNS 预取、TCP 和 SSL 预连接以及网页预呈现。

如果未配置此策略，则会启用网络预测，但用户可以更改它。

策略选项映射：

* NetworkPredictionAlways (0) = 预测任何网络连接上的网络操作

* NetworkPredictionWifiOnly (1) = 不受支持，如果使用该值，将被视为 "预报网络连接上的网络操作" （0）设置

* NetworkPredictionNever (2) = 不预测任何网络连接上的网络操作

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：NetworkPredictionOptions
  - GP 名称：启用网络预测
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：NetworkPredictionOptions
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000002
```

  #### Mac 信息和设置
  
  - 首选项项名称：NetworkPredictionOptions
  - 示例值：
``` xml
<integer>2</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### NonRemovableProfileEnabled

  #### 配置用户是否始终具有使用其工作或学校帐户自动登录的默认配置文件

  
  
  #### 支持的版本：

  - 在 Windows 上自 78 或更高版本起

  #### 描述

  此策略确定用户是否能够删除使用其工作或学校帐户自动登录的 Microsoft Edge 配置文件。

如果启用此策略，则将使用 Windows 上用户的工作或学校帐户创建一个不可删除的配置文件。 此配置文件无法注销或删除。

如果禁用或未配置此策略，用户可以注销或删除使用 Windows 上其工作或学校帐户自动登录的配置文件。

如果要配置浏览器登录，请使用 [BrowserSigning](#browsersignin) 策略。

此策略仅在加入 Microsoft Active Directory 域的 Windows 实例或者已注册设备管理的 Windows 10 专业版或企业版实例上可用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：NonRemovableProfileEnabled
  - GP 名称：配置用户是否始终具有使用其工作或学校帐户自动登录的默认配置文件
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：NonRemovableProfileEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  

  [返回页首](#microsoft-edge---policies)

  ### OverrideSecurityRestrictionsOnInsecureOrigin

  #### 控制对不安全源应用安全限制的位置

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指定不安全源的安全限制不适用的源 (URL) 或主机名模式（如“*.contoso.com”）列表。

通过此策略，可为无法部署 TLS 的旧应用程序指定允许的源，或者为内部 Web 开发设置临时服务器，以便开发人员不必在临时服务器上部署 TLS，就可以测试需要安全上下文的功能。 此策略还可防止源服务器在多功能地址栏中被标记为“不安全”。

在此策略中设置 URL 列表与将命令行标志“--unsafely-treat-insecure-origin-as-secure”设置为逗号分隔的相同 URL 列表的效果相同。 如果启用此策略，它将替代命令行标志。

有关安全上下文的详细信息，请参阅 https://www.w3.org/TR/secure-contexts/。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：OverrideSecurityRestrictionsOnInsecureOrigin
  - GP 名称：控制对不安全源应用安全限制的位置
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\OverrideSecurityRestrictionsOnInsecureOrigin
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\OverrideSecurityRestrictionsOnInsecureOrigin\1 = "http://testserver.contoso.com/"
SOFTWARE\Policies\Microsoft\Edge\OverrideSecurityRestrictionsOnInsecureOrigin\2 = "*.contoso.com"

```

  #### Mac 信息和设置
  
  - 首选项项名称：OverrideSecurityRestrictionsOnInsecureOrigin
  - 示例值：
``` xml
<array>
  <string>http://testserver.contoso.com/</string>
  <string>*.contoso.com</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### PaymentMethodQueryEnabled

  #### 允许网站查询可用的付款方式

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 80 或更高版本起

  #### 描述

  允许你设置网站是否可以检查用户是否保存了付款方式。

如果禁用此策略，则使用 PaymentRequest.canMakePayment 或 PaymentRequest.hasEnrolledInstrument API 的网站将被通知没有可用的付款方式。

如果启用此策略或未设置此策略，网站可以检查用户是否保存了付款方式。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：PaymentMethodQueryEnabled
  - GP 名称：允许网站查询可用的付款方式
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：PaymentMethodQueryEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：PaymentMethodQueryEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### PersonalizationReportingEnabled

  #### 通过向 Microsoft 发送浏览历史记录，允许对广告、搜索和新闻进行个性化设置

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 80 或更高版本起

  #### 描述

  此策略阻止 Microsoft 收集用户的 Microsoft Edge 浏览历史记录来对广告、搜索、新闻和其他 Microsoft 服务进行个性化设置。

此设置仅适用于具有 Microsoft 帐户的用户。 此设置不适用于儿童帐户或企业帐户。

如果禁用此策略，用户将无法更改或替代该设置。 如果启用或未配置此策略，Microsoft Edge 将默认为用户的首选项。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：PersonalizationReportingEnabled
  - GP 名称：通过向 Microsoft 发送浏览历史记录，允许对广告、搜索和新闻进行个性化设置
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：PersonalizationReportingEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：PersonalizationReportingEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### PinningWizardAllowed

  #### 允许固定到任务栏向导

  
  
  #### 支持的版本：

  - 在 Windows 上自 80 或更高版本起

  #### 描述

  Microsoft Edge 使用固定到任务栏向导帮助用户将建议的网站固定到任务栏。 固定到任务栏向导功能默认情况下处于启用状态，用户可通过“设置及更多”菜单访问该功能。

如果启用或未配置此策略，用户可以从“设置及更多”菜单调用固定到任务栏向导。 也可以通过协议发布来调用该向导。

如果禁用此策略，则将在菜单中禁用固定到任务栏向导，并且无法通过协议发布进行调用。

启用或禁用固定到任务栏向导的用户设置不可用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：PinningWizardAllowed
  - GP 名称：允许固定到任务栏向导
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：PinningWizardAllowed
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  

  [返回页首](#microsoft-edge---policies)

  ### ProactiveAuthEnabled

  #### 启用主动身份验证

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  让你可配置是否打开主动身份验证。

如果启用此策略，Microsoft Edge 将尝试使用 Microsoft 服务主动对已登录用户进行身份验证。 Microsoft Edge 会定期检查联机服务，查找是否有更新清单包含控制如何执行此操作的配置。

如果禁用此策略，Microsoft Edge 不会尝试使用 Microsoft 服务主动对已登录用户进行身份验证。 Microsoft Edge 不再检查联机服务来查找是否有更新清单包含执行此操作的配置。

如果未配置此策略，则将启用主动身份验证。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ProactiveAuthEnabled
  - GP 名称：启用主动身份验证
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ProactiveAuthEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ProactiveAuthEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### PromotionalTabsEnabled

  #### 启用完整选项卡促销内容

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  控制完整选项卡促销或教育内容的展示。 此设置控制欢迎页面的展示，可帮助用户登录 Microsoft Edge、选择其默认浏览器或了解产品功能。

如果启用此策略（将其设置为 true）或未配置此策略，Microsoft Edge 可以向用户显示完整选项卡内容以提供产品信息。

如果禁用（设置为 false）此策略，Microsoft Edge 将无法向用户显示完整选项卡内容。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：PromotionalTabsEnabled
  - GP 名称：启用完整选项卡促销内容
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：PromotionalTabsEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：PromotionalTabsEnabled
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### PromptForDownloadLocation

  #### 询问在何处保存下载的文件

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  设置是否在下载文件之前询问保存位置。

如果启用此策略，则会在下载前询问用户将每个文件保存在何处；如果未配置此策略，则文件将自动保存到默认位置，而不询问用户。

如果未配置此策略，用户将能够更改此设置。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：PromptForDownloadLocation
  - GP 名称：询问在何处保存下载的文件
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：PromptForDownloadLocation
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：PromptForDownloadLocation
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### QuicAllowed

  #### 允许 QUIC 协议

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  允许在 Microsoft Edge 中使用 QUIC 协议。

如果启用或未配置此策略，则允许使用 QUIC 协议。

如果禁用此策略，则 QUIC 协议将被阻止。

QUIC 是一种传输层网络协议，可提高当前使用 TCP 的 Web 应用程序的性能。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：QuicAllowed
  - GP 名称：允许 QUIC 协议
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：QuicAllowed
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：QuicAllowed
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### RedirectSitesFromInternetExplorerPreventBHOInstall

  #### 阻止安装可将不兼容的网站从 Internet Explorer 重定向到 Microsoft Edge 的 BHO

  
  
  #### 支持的版本：

  - 在 87 版或更高版本的 Windows 上

  #### 描述

  通过此设置，你可以指定是否阻止安装浏览器帮助程序对象(BHO)，BHO 可将不兼容的网站从 Internet Explorer 重定向到 Microsoft Edge，以支持需要使用新式浏览器的网站。

如果启用此策略，将不安装 BHO。 如果已安装，将在下一次 Microsoft Edge 更新时将其卸载。

如果未配置或禁用了此策略，将安装 BHO。

只有在安装 BHO 后，才会发生不兼容网站重定向，但重定向是否发生还受 [RedirectSitesFromInternetExplorerRedirectMode](#redirectsitesfrominternetexplorerredirectmode) 的控制。

有关此策略的详细信息，请参阅[https://go.microsoft.com/fwlink/?linkid=2141715](https://go.microsoft.com/fwlink/?linkid=2141715)

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：RedirectSitesFromInternetExplorerPreventBHOInstall
  - GP 名称：阻止安装可将不兼容的网站从 Internet Explorer 重定向到 Microsoft Edge 的 BHO
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：RedirectSitesFromInternetExplorerPreventBHOInstall
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  

  [返回页首](#microsoft-edge---policies)

  ### RedirectSitesFromInternetExplorerRedirectMode

  #### 将不兼容的网站从 Internet Explorer 重新定向到 Microsoft Edge

  
  
  #### 支持的版本：

  - 在 87 版或更高版本的 Windows 上

  #### 描述

  通过此设置，你可以指定 Internet Explorer 是否在导航到需要新式浏览器的网站时重定向到 Microsoft Edge。

如果未配置此策略或将其设置为“站点列表”，则从 M87 开始，Internet Explorer 会将需要新式浏览器的网站重定向到 Microsoft Edge。

从 Internet Explorer 将网站重定向到 Microsoft Edge 时，如果之前没有其他内容，则会关闭开始加载该网站的 Internet Explorer 标签页。 否则，将导航到 Microsoft 帮助页面，其中介绍了将相应网站重定向到 Microsoft Edge 的原因。

启动 Microsoft Edge 以从 IE 加载网站时，用户会看到一个信息栏，其中说明了该网站在新式浏览器中效果最佳。

如果将此策略设置为“禁用”，则 Internet Explorer 不会将任何流量重定向到 Microsoft Edge。

有关此策略的详细信息，请参阅[https://go.microsoft.com/fwlink/?linkid=2141715](https://go.microsoft.com/fwlink/?linkid=2141715)

策略选项映射：

* Disable (0) = 禁用

* Sitelist (1) = 基于不兼容网站列表重定向网站

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：RedirectSitesFromInternetExplorerRedirectMode
  - GP 名称：Redirect incompatible sites from Internet Explorer to Microsoft Edge
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：RedirectSitesFromInternetExplorerRedirectMode
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  

  [返回页首](#microsoft-edge---policies)

  ### RelaunchNotification

  #### 通知用户对于挂起的更新，推荐或需要重新启动浏览器

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  通知用户他们需要重新启动 Microsoft Edge 以应用挂起的更新。

如果未配置此策略，Microsoft Edge 将在顶部菜单栏最右侧添加一个回收图标，提示用户重新启动浏览器以应用更新。

如果启用此策略并将其设置为 'Recommended'，则会反复出现一条警告，提示用户建议重新启动。 用户可以解除此警告并推迟重新启动。

如果将该策略设置为 'Required'，则会反复出现一条警告，提示用户在通知期过后，浏览器将自动重新启动。 默认期限为七天。 可使用 [RelaunchNotificationPeriod](#relaunchnotificationperiod) 策略配置此期限。

浏览器重新启动后，将还原用户的会话。

策略选项映射：

* Recommended (1) = 推荐 - 向用户显示重复提示，指示建议重新启动

* Required (2) = 必需 - 向用户显示重复提示，指示需要重新启动

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：RelaunchNotification
  - GP 名称：通知用户对于挂起的更新，推荐或需要重新启动浏览器
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：RelaunchNotification
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：RelaunchNotification
  - 示例值：
``` xml
<integer>1</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### RelaunchNotificationPeriod

  #### 设置更新通知的时间段

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  可用于设置时间段（以毫秒为单位），在此时间段内，用户将收到通知：必须重新启动 Microsoft Edge 才能应用挂起的更新。

在此时间段内，将反复通知用户需要更新。 在 Microsoft Edge 中，通知期的三分之一过去后，应用菜单将更改以指示需要重新启动。 此通知会在通知期的三分之二过去后改变颜色，并在整个通知期结束后再次改变颜色。 由 [RelaunchNotification](#relaunchnotification) 策略启用的附加通知遵循相同的计划。

如果未设置，则使用默认周期 604800000 毫秒（一周）。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：RelaunchNotificationPeriod
  - GP 名称：设置更新通知的时间段
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：RelaunchNotificationPeriod
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x240c8400
```

  #### Mac 信息和设置
  
  - 首选项项名称：RelaunchNotificationPeriod
  - 示例值：
``` xml
<integer>604800000</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### RendererCodeIntegrityEnabled

  #### 启用呈现器代码完整性

  
  
  #### 支持的版本：

  - 在 Windows 上自 78 或更高版本起

  #### 描述

  如果启用或未设置此策略，则将启用呈现器代码完整性。 只有当必须在 Microsoft Edge 的呈现器进程中运行的第三方软件遇到兼容性问题时，才应禁用此策略。

禁用此策略会对 Microsoft Edge 的安全性和稳定性产生不利影响，因为允许在 Microsoft Edge 的呈现器进程中加载未知和潜在的恶意代码。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：RendererCodeIntegrityEnabled
  - GP 名称：启用呈现器代码完整性
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：RendererCodeIntegrityEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  

  [返回页首](#microsoft-edge---policies)

  ### RequireOnlineRevocationChecksForLocalAnchors

  #### 指定本地信任密钥是否需要联机 OCSP/CRL 检查

  
  
  #### 支持的版本：

  - 在 Windows 上自 77 或更高版本起

  #### 描述

  控制是否需要联机吊销检查（OCSP/CRL 检查）。 如果 Microsoft Edge 无法获取吊销状态信息，这些证书将被视为已吊销（“硬故障”）。

如果启用此策略，Microsoft Edge 将始终对成功验证并由本地安装的 CA 证书签名的服务器证书执行吊销检查。

如果未配置或禁用此策略，则 Microsoft Edge 将使用现有的联机吊销检查设置。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：RequireOnlineRevocationChecksForLocalAnchors
  - GP 名称：指定本地信任密钥是否需要联机 OCSP/CRL 检查
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：RequireOnlineRevocationChecksForLocalAnchors
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  

  [返回页首](#microsoft-edge---policies)

  ### ResolveNavigationErrorsUseWebService

  #### 启用使用 Web 服务解决导航错误

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  允许 Microsoft Edge 发布与 Web 服务的无数据连接，以便在酒店和机场 Wi-Fi 等情况下探测网络连接。

如果启用此策略，则将使用 Web 服务执行网络连接测试。

如果禁用此策略，Microsoft Edge 将使用本机 API 尝试解决网络连接和导航问题。

**注意**：除了 Windows 8 和更高版本的 Windows 之外，Microsoft Edge *始终*使用本机 API 来解决连接问题。

如果未配置此策略，Microsoft Edge 将遵循 edge://settings/privacy 处“服务”下设置的用户首选项。
具体而言，有一个“**使用 Web 服务帮助解决导航错误**”开关，用户可以打开或关闭该开关。 请注意，如果已启用此策略 (ResolveNavigationErrorsUseWebService)，则“**使用 Web 服务帮助解决导航错误**”设置将打开，但用户无法使用开关更改该设置。 如果禁用此策略，“**使用 Web 服务帮助解决导航错误**”设置将关闭，用户无法使用开关更改该设置。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ResolveNavigationErrorsUseWebService
  - GP 名称：启用使用 Web 服务解决导航错误
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：ResolveNavigationErrorsUseWebService
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：ResolveNavigationErrorsUseWebService
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### RestrictSigninToPattern

  #### 限制哪些帐户可用作 Microsoft Edge 主要帐户

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  确定哪些帐户可以设置为 Microsoft Edge 中的浏览器主帐户（在同步选择加入流程中选择的帐户）。

如果用户试图使用与此模式不匹配的用户名配置浏览器主帐户，则他们会被阻止，并且会看到相应的错误消息。 可以使用该模式的 Perl 样式正则表达式将此策略配置为匹配多个帐户。 请注意，模式匹配是区分大小写的。 有关所用正则表达式规则的详细信息，请参阅 https://go.microsoft.com/fwlink/p/?linkid=2133903。

如果未配置此策略或将其保留为空，用户可以在 Microsoft Edge 中将任何帐户设置为浏览器主帐户。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：RestrictSigninToPattern
  - GP 名称：限制哪些帐户可用作 Microsoft Edge 主要帐户
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：RestrictSigninToPattern
  - 值类型：REG_SZ

  ##### 示例值：

```
".*@contoso.com"
```

  #### Mac 信息和设置
  
  - 首选项项名称：RestrictSigninToPattern
  - 示例值：
``` xml
<string>.*@contoso.com</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### RoamingProfileLocation

  #### 设置漫游配置文件目录

  
  
  #### 支持的版本：

  - 在 85 版或更高版本的 Windows 上

  #### 描述

  配置用于存储配置文件的漫游副本的目录。

如果启用此策略，则 Microsoft Edge 将使用提供的目录存储配置文件的漫游副本，前提是你已启用了 [RoamingProfileSupportEnabled](#roamingprofilesupportenabled) 策略。 如果禁用 [RoamingProfileSupportEnabled](#roamingprofilesupportenabled) 策略或不对其进行配置，则不会使用存储在此策略中的值。

有关你可使用的变量列表，请参阅 [https://go.microsoft.com/fwlink/?linkid=2095041](https://go.microsoft.com/fwlink/?linkid=2095041)。

如果未配置此策略，则将使用默认的漫游配置文件路径。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称： RoamingProfileLocation
  - GP 名称：设置漫游配置文件目录
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称： RoamingProfileLocation
  - 值类型：REG_SZ

  ##### 示例值：

```
"${roaming_app_data}\\edge-profile"
```

  

  [返回页首](#microsoft-edge---policies)

  ### RoamingProfileSupportEnabled

  #### 启用 Microsoft Edge 配置文件数据的漫游副本

  
  
  #### 支持的版本：

  - 在 85 版或更高版本的 Windows 上

  #### 描述

  启用此策略，在 Windows 上使用漫游配置文件。 存储在 Microsoft Edge 配置文件中的设置（收藏夹和首选项）也保存到存储在漫游用户配置文件文件夹中的文件（或管理员通过[RoamingProfileLocation](#roamingprofilelocation)策略指定的位置）。

如果禁用该策略或不对其进行配置，则仅使用常规本地配置文件。

[SyncDisabled](#syncdisabled)禁用所有数据同步，覆盖策略。

有关使用漫游用户配置文件的详细信息，请参阅https://docs.microsoft.com/windows-server/storage/folder-redirection/deploy-roaming-user-profiles。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称： RoamingProfileSupportEnabled
  - GP 名称：支持使用 Microsoft Edge 配置文件数据的漫游副本
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：RoamingProfileSupportEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  

  [返回页首](#microsoft-edge---policies)

  ### RunAllFlashInAllowMode

  #### 将 Adobe Flash 内容设置扩展到所有内容

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  如果启用此策略，则内容设置中设为允许 Adobe Flash（由用户或通过企业策略）的网站中嵌入的所有 Adobe Flash 内容都将运行。 这包括来自其他源的内容和/或小型内容。

要控制允许哪些网站运行 Adobe Flash，请参阅 [DefaultPluginsSetting](#defaultpluginssetting)、[PluginsAllowedForUrls](#pluginsallowedforurls) 和 [PluginsBlockedForUrl](#pluginsblockedforurls) 策略中的规范。

如果禁用或未配置此策略，来自其他源的 Adobe Flash 内容（来自上面提到的三个策略中未指定的网站）或小型内容可能会被阻止。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：RunAllFlashInAllowMode
  - GP 名称：将 Adobe Flash 内容设置扩展到所有内容
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：RunAllFlashInAllowMode
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：RunAllFlashInAllowMode
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SSLErrorOverrideAllowed

  #### 允许用户从 HTTPS 警告页面继续操作

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  当用户访问存在 SSL 错误的网站时，Microsoft Edge 会显示警告页面。

如果启用或未配置（默认）此策略，则用户可以单击浏览这些警告页面。

如果禁用此策略，则将阻止用户单击浏览任何警告页面。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SSLErrorOverrideAllowed
  - GP 名称：允许用户从 HTTPS 警告页面继续操作
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：SSLErrorOverrideAllowed
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：SSLErrorOverrideAllowed
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SSLVersionMin

  #### 已启用最低 TLS 版本

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  Sets the minimum supported version of TLS. 如果未配置此策略，则 Microsoft Edge 将显示适用于 TLS 1.0 和 TLS 1.1 的错误，但用户将可以忽略它。

如果启用此策略，Microsoft Edge 将不会使用低于指定版本的任何 SSL/TLS 版本。 任何无法识别的值都将被忽略。

策略选项映射：

* TLSv1 (tls1) = TLS 1.0

* TLSv1.1 (tls1.1) = TLS 1.1

* TLSv1.2 (tls1.2) = TLS 1.2

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SSLVersionMin
  - GP 名称：已启用最低 TLS 版本
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：SSLVersionMin
  - 值类型：REG_SZ

  ##### 示例值：

```
"tls1"
```

  #### Mac 信息和设置
  
  - 首选项项名称：SSLVersionMin
  - 示例值：
``` xml
<string>tls1</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SaveCookiesOnExit

  #### Microsoft Edge 关闭时保存 cookie

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 86 或更高版本起

  #### 描述

  如果启用此策略，指定 cookie 集将在浏览器关闭时免于删除。 此策略仅适用于以下情况：
- 在“设置”/“隐私和服务”/“关闭时清除浏览数据”中配置了“Cookie 和其他站点数据”开关；或者
- 已启用策略 [ClearBrowsingDataOnExit](#clearbrowsingdataonexit)；或者
- 策略 [DefaultCookiesSetting](#defaultcookiessetting) 设置为“在会话期间保留 Cookie”。

可以根据 URL 模式定义一个站点列表，这些站点将跨会话保存它们的 Cookie。

注意：用户仍可编辑 Cookie 网站列表来添加或删除 URL。 但是，他们不能删除管理员添加的 URL。

如果启用此策略，浏览器关闭时将不会清除 Cookie 列表。

如果禁用或不配置此策略，则使用用户的个人配置。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SaveCookiesOnExit
  - GP 名称：Microsoft Edge 关闭时保存 Cookie
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\SaveCookiesOnExit
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\SaveCookiesOnExit\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SaveCookiesOnExit\2 = "[*.]contoso.edu"

```

  #### Mac 信息和设置
  
  - 首选密钥名称：SaveCookiesOnExit
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SavingBrowserHistoryDisabled

  #### 禁止保存浏览器历史记录

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  禁止保存浏览器历史记录并阻止用户更改此设置。

如果启用此策略，则不会保存浏览历史记录。 这也会禁用选项卡同步。

如果禁用或未配置此策略，则会保存浏览历史记录。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SavingBrowserHistoryDisabled
  - GP 名称：禁止保存浏览器历史记录
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：SavingBrowserHistoryDisabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：SavingBrowserHistoryDisabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ScreenCaptureAllowed

  #### 允许或拒绝屏幕捕获

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 83 或更高版本起

  #### 描述

  如果启用此策略或未配置此策略，则网页可以使用屏幕共享 API（例如 getDisplayMedia() 或桌面捕获扩展 API）进行屏幕捕获。
如果禁用此策略，对屏幕共享 API 的调用将失败。 例如，如果你使用的是基于 Web 的联机会议，则视频或屏幕共享将不起作用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ScreenCaptureAllowed
  - GP 名称：允许或拒绝屏幕捕获
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ScreenCaptureAllowed
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：ScreenCaptureAllowed
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ScrollToTextFragmentEnabled

  #### 允许滚动到 URL 片段中指定的文本

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 83 或更高版本起

  #### 描述

  此功能允许超链接和地址栏 URL 导航以网页上的特定文本为目标，在网页加载完成后将滚动到该文本。

如果启用或未配置此策略，则允许网页通过 URL 滚动到特定文本片段。

如果禁用此策略，则禁止网页通过 URL 滚动到特定文本片段。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ScrollToTextFragmentEnabled
  - GP 名称：允许滚动到 URL 片段中指定的文本
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ScrollToTextFragmentEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：ScrollToTextFragmentEnabled
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SearchSuggestEnabled

  #### 启用搜索建议

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  在 Microsoft Edge 的地址栏和自动建议列表中启用 Web 搜索建议，并阻止用户更改此策略。

如果启用此策略，将使用 Web 搜索建议。

如果禁用此策略，则永远不会使用 Web 搜索建议，但仍会显示本地历史记录和本地收藏夹建议。 如果禁用此策略，键入的字符和访问的 URL 都不会包含在 Microsoft 的遥测中。

如果未设置此策略，则会启用搜索建议，但用户可对此进行更改。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SearchSuggestEnabled
  - GP 名称：启用搜索建议
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：SearchSuggestEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：SearchSuggestEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SecurityKeyPermitAttestation

  #### 无需相应权限即可使用直接安全密钥证明的网站或域

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  指定在请求来自安全密钥的证明证书时不需要显式用户权限的网站和域。 此外，还会向安全密钥发送一个信号，指示它可以使用单个证明。 如果不这样做，每次网站请求安全密钥证明时都会提示用户。

网站（如 https://contoso.com/some/path)）仅与 U2F AppID 匹配。 域（如 contoso.com）仅与 webauthn RP ID 匹配。 要涵盖给定网站的 U2F 和 webauthn API，需要同时列出 appID URL 和域。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SecurityKeyPermitAttestation
  - GP 名称：无需相应权限即可使用直接安全密钥证明的网站或域
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\SecurityKeyPermitAttestation
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\SecurityKeyPermitAttestation\1 = "https://contoso.com"

```

  #### Mac 信息和设置
  
  - 首选项项名称：SecurityKeyPermitAttestation
  - 示例值：
``` xml
<array>
  <string>https://contoso.com</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SendIntranetToInternetExplorer

  #### 将所有 Intranet 站点都发送到 Internet Explorer

  
  
  #### 支持的版本：

  - 在 Windows 上自 77 或更高版本起

  #### 描述

  有关配置 Internet Explorer 模式的最佳体验的指南，请参阅 [https://go.microsoft.com/fwlink/?linkid=2094210](https://go.microsoft.com/fwlink/?linkid=2094210)

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SendIntranetToInternetExplorer
  - GP 名称：将所有 Intranet 站点都发送到 Internet Explorer
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：SendIntranetToInternetExplorer
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  

  [返回页首](#microsoft-edge---policies)

  ### SendSiteInfoToImproveServices

  #### 发送站点信息以改进 Microsoft 服务（已弃用）

  >已弃用：此策略已弃用。 当前受支持，但将在未来的版本中弃用。
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  此策略已弃用。 当前受支持，但在 Microsoft Edge 89 版本中将过时。 对于 Windows 7、Windows 8 和 macOS，此策略替换为新策略：[DiagnosticData](#diagnosticdata)。 对于 Win 10 ([https://go.microsoft.com/fwlink/?linkid=2099569](https://go.microsoft.com/fwlink/?linkid=2099569))，此策略替换为“允许遥测”。

此策略允许向 Microsoft 发送有关在 Microsoft Edge 中访问过的网站的信息，以改进搜索等服务。

启用此策略后，可将有关在 Microsoft Edge 中访问过的网站的信息发送给 Microsoft。 禁用此策略后，不会向 Microsoft 发送有关在 Microsoft Edge 中访问过的网站的信息。 在这两种情况下，用户不能更改或覆盖设置。

在 Windows 10 上，如果未配置此策略，Microsoft Edge 将默认使用 Windows 诊断数据设置。 启用此策略后，如果 Windows 诊断数据设置设为“完整”，Microsoft Edge 将仅发送有关在 Microsoft Edge 中访问过的网站的信息。 如果禁用此策略，Microsoft Edge 将不会发送有关所访问网站的信息。 详细了解 Windows 诊断数据设置：[https://go.microsoft.com/fwlink/?linkid=2099569](https://go.microsoft.com/fwlink/?linkid=2099569)

在 Windows 7、Windows 8 和 macOS 上，此策略控制发送有关已访问网站的信息。 如果未配置此策略，Microsoft Edge 将默认使用用户首选项。

若要启用此策略，必需将 [MetricsReportingEnabled](#metricsreportingenabled) 设置为“已启用”。 如果 [SendSiteInfoToImproveServices](#sendsiteinfotoimproveservices) 或 [MetricsReportingEnabled](#metricsreportingenabled) 未配置或已禁用，则不会将此数据发送到 Microsoft。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SendSiteInfoToImproveServices
  - GP 名称：发送站点信息以改进 Microsoft 服务（已弃用）
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：SendSiteInfoToImproveServices
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：SendSiteInfoToImproveServices
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SensorsAllowedForUrls

  #### 允许访问特定网站上的传感器

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 86 或更高版本起

  #### 描述

  基于 URL 模式，定义一个可访问并使用诸如运动和光传感器等传感器的网站列表。

如果未配置此策略，则所有网站都将使用 [DefaultSensorsSetting](#defaultsensorssetting) 策略中的全局默认值（如果已设置）或用户的个人配置。

对于与此策略不匹配的 URL 模式，将使用以下优先级顺序：[SensorsBlockedForUrls](#sensorsblockedforurls) 策略（如果有匹配）、[DefaultSensorsSetting](#defaultsensorssetting) 策略（如果已设置）或用户的个人设置。

此策略中定义的 URL 模式与 [SensorsBlockedForUrls](#sensorsblockedforurls) 策略中配置的不冲突。 不能同时允许和阻止一个 URL。

有关有效 URL 模式的详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SensorsAllowedForUrls
  - GP 名称：允许访问特定网站上的传感器
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\SensorsAllowedForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\SensorsAllowedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SensorsAllowedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：SensorsAllowedForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SensorsBlockedForUrls

  #### 阻止访问特定网站上的传感器

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 86 或更高版本起

  #### 描述

  基于 URL 模式，定义一个不能访问运动和光传感器等传感器的网站列表。

如果未配置此策略，则所有网站都将使用 [DefaultSensorsSetting](#defaultsensorssetting) 策略中的全局默认值（如果已设置）或用户的个人配置。

对于与此策略不匹配的 URL 模式，将使用以下优先级顺序： [SensorsAllowedForUrls](#sensorsallowedforurls) 策略（如果有匹配）、[DefaultSensorsSetting](#defaultsensorssetting) 策略（如果已设置）或用户的个人设置。

此策略中定义的 URL 模式与 [SensorsAllowedForUrls](#sensorsallowedforurls) 策略中配置的不冲突。 不能同时允许和阻止一个 URL。

有关有效 URL 模式的详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SensorsBlockedForUrls
  - GP 名称：阻止访问特定网站上的传感器
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\SensorsBlockedForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\SensorsBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SensorsBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：SensorsBlockedForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SerialAskForUrls

  #### 在特定网站上允许串行 API

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 86 或更高版本起

  #### 描述

  根据 URL 模式定义可要求用户授予串行端口访问权限的网站列表。

如果未配置此策略，则所有网站都将使用 [DefaultSerialGuardSetting](#defaultserialguardsetting) 策略中的全局默认值（如果已设置）或用户的个人配置。

对于与此策略不匹配的 URL 模式，将使用以下优先级顺序：[SerialBlockedForUrls](#serialblockedforurls) 策略（如果有匹配）、[DefaultSerialGuardSetting](#defaultserialguardsetting) 策略（如果已设置）或用户的个人设置。

此策略中定义的 URL 模式与 [SerialBlockedForUrls](#serialblockedforurls) 策略中配置的不冲突。 不能同时允许和阻止一个 URL。

有关有效 url 模式的详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SerialAskForUrls
  - GP 名称：在特定网站上允许串行 API
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\SerialAskForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\SerialAskForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SerialAskForUrls\2 = "[*.]contoso.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：SerialAskForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SerialBlockedForUrls

  #### 在特定网站上阻止串行 API

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 86 或更高版本起

  #### 描述

  根据 URL 模式定义不能要求用户授予串行端口访问权限的网站列表。

如果未配置此策略，则所有网站都将使用 [DefaultSerialGuardSetting](#defaultserialguardsetting) 策略中的全局默认值（如果已设置）或用户的个人配置。

对于与此策略不匹配的 URL 模式，将使用以下优先级顺序：[SerialAskForUrls](#serialaskforurls) 策略（如果有匹配）、[DefaultSerialGuardSetting](#defaultserialguardsetting) 策略（如果已设置）或用户的个人设置。

此策略中的 URL 模式不能与 [SerialAskForUrls](#serialaskforurls) 策略中配置的 URL 模式冲突。 不能同时允许和阻止一个 URL。

有关有效 URL 模式的详细信息，请参阅 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322)。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SerialBlockedForUrls
  - GP 名称：在特定网站上阻止串行 API
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\SerialBlockedForUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\SerialBlockedForUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\SerialBlockedForUrls\2 = "[*.]contoso.edu"

```

  #### Mac 信息和设置
  
  - 首选项项名称：SerialBlockedForUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>[*.]contoso.edu</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### ShowOfficeShortcutInFavoritesBar

  #### 在收藏夹栏中显示 Microsoft Office 快捷方式（已弃用）

  >已弃用：此策略已弃用。 当前受支持，但将在未来的版本中弃用。
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  由于操作要求的更改，此策略未按预期工作。 Therefore it's deprecated and should not be used.

指定是否在收藏夹栏中包含 Office.com 的快捷方式。 For users signed into Microsoft Edge the shortcut takes users to their Microsoft Office apps and docs. If you enable or don't configure this policy, users can choose whether to see the shortcut by changing the toggle in the favorites bar context menu.
If you disable this policy, the shortcut isn't shown.

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：ShowOfficeShortcutInFavoritesBar
  - GP 名称：在收藏夹栏中显示 Microsoft Office 快捷方式（已弃用）
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：ShowOfficeShortcutInFavoritesBar
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：ShowOfficeShortcutInFavoritesBar
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SignedHTTPExchangeEnabled

  #### 启用签名的 HTTP Exchange (SXG) 支持

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 78 或更高版本起

  #### 描述

  启用对签名的 HTTP Exchange (SXG) 的支持。

如果未设置或启用此策略，Microsoft Edge 将接受作为签名的 HTTP Exchange 提供 Web 内容。

如果此策略设置为禁用，则无法加载签名的 HTTP Exchange。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SignedHTTPExchangeEnabled
  - GP 名称：启用签名的 HTTP Exchange (SXG) 支持
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：SignedHTTPExchangeEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：SignedHTTPExchangeEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SitePerProcess

  #### 对每个网站启用网站隔离

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  “SitePerProcess”策略可用于防止用户选择退出默认行为，即隔离所有网站。 请注意，也可以使用 [IsolateOrigins](#isolateorigins) 策略来隔离其他更精细的来源。

如果启用此策略，则用户不能选择退出默认行为，即每个网站在其自己的进程中运行。

如果禁用或未配置此策略，用户可以选择退出网站隔离。  （例如，通过使用 edge://flags 中的“禁用网站隔离”条目。）禁用或未配置该策略不会关闭网站隔离。


  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SitePerProcess
  - GP 名称：对每个网站启用网站隔离
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：SitePerProcess
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：SitePerProcess
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SpeechRecognitionEnabled

  #### Configure Speech Recognition

  
  
  #### 支持的版本：

  - On Windows and macOS since 87 or later

  #### 描述

  Set whether websites can use the W3C Web Speech API to recognize speech from the user. The Microsoft Edge implementation of the Web Speech API uses Azure Cognitive Services, so voice data will leave the machine.

If you enable or don't configure this policy, web-based applications that use the Web Speech API can use Speech Recognition.

If you disable this policy, Speech Recognition is not available through the Web Speech API.

Read more about this feature here: SpeechRecognition API: [https://go.microsoft.com/fwlink/?linkid=2143388](https://go.microsoft.com/fwlink/?linkid=2143388) Cognitive Services: [https://go.microsoft.com/fwlink/?linkid=2143680](https://go.microsoft.com/fwlink/?linkid=2143680)

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP unique name: SpeechRecognitionEnabled
  - GP name: Configure Speech Recognition
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - Value Name: SpeechRecognitionEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - Preference Key Name: SpeechRecognitionEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SpellcheckEnabled

  #### 启用拼写检查

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  如果启用或未配置此策略，用户可以使用拼写检查。

如果禁用此策略，用户将无法使用拼写检查，并且 [SpellcheckLanguage](#spellchecklanguage) 和 [SpellcheckLanguageBlocklist](#spellchecklanguageblocklist) 策略也将被禁用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SpellcheckEnabled
  - GP 名称：启用拼写检查
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：SpellcheckEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：SpellcheckEnabled
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SpellcheckLanguage

  #### 启用特定拼写检查语言

  
  
  #### 支持的版本：

  - 在 Windows 上自 77 或更高版本起

  #### 描述

  启用不同的拼写检查语言。 你指定的任何无法识别的语言都将被忽略。

如果启用此策略，则会为指定的语言以及用户启用的任何语言启用拼写检查。

如果未配置或禁用此策略，则用户的拼写检查首选项不会发生任何更改。

如果禁用了 [SpellcheckEnabled](#spellcheckenabled) 策略，则此策略将不起作用。

如果“SpellcheckLanguage”和 [SpellcheckLanguageBlocklist](#spellchecklanguageblocklist) 策略中同时包含某种语言，则将启用该拼写检查语言。

支持的语言包括：af、bg、ca、cs、cy、da、de、el、en-AU、en-CA、en-GB、en-US、es、es-419、es-AR、es-ES、es-MX、es-US、et、fa、fo、fr、he、hi、hr、hu、id、it、ko、lt、lv、nb、nl、pl、pt-BR、pt-PT、ro、ru、sh、sk、sl、sq、sr、sv、ta、tg、tr、uk、vi。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SpellcheckLanguage
  - GP 名称：启用特定拼写检查语言
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\SpellcheckLanguage
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\SpellcheckLanguage\1 = "fr"
SOFTWARE\Policies\Microsoft\Edge\SpellcheckLanguage\2 = "es"

```

  

  [返回页首](#microsoft-edge---policies)

  ### SpellcheckLanguageBlocklist

  #### 强制禁用拼写检查语言

  
  
  #### 支持的版本：

  - 在 Windows 上自 78 或更高版本起

  #### 描述

  强制禁用拼写检查语言。 该列表中无法识别的语言将被忽略。

如果启用此策略，将对指定的语言禁用拼写检查。 用户仍可以对列表中未包含的语言启用或禁用拼写检查。

如果未设置或禁用此策略，用户的拼写检查首选项将不会发生任何更改。

如果 [SpellcheckEnabled](#spellcheckenabled) 策略设置为禁用，则此策略将不起作用。

如果 [SpellcheckLanguage](#spellchecklanguage) 和“SpellcheckLanguageBlocklist”策略中同时包含某种语言，则将启用该拼写检查语言。

当前支持的语言包括：af、bg、ca、cs、da、de、el、en-AU、en-CA、en-GB、en-US、es、es-419、es-AR、es-ES、es-MX、es-US、et、fa、fo、fr、he、hi、hr、hu、id、it、ko、lt、lv、nb、nl、pl、pt-BR、pt-PT、ro、ru、sh、sk、sl、sq、sr、sv、ta、tg、tr、uk、vi。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SpellcheckLanguageBlocklist
  - GP 名称：强制禁用拼写检查语言
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\SpellcheckLanguageBlocklist
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\SpellcheckLanguageBlocklist\1 = "fr"
SOFTWARE\Policies\Microsoft\Edge\SpellcheckLanguageBlocklist\2 = "es"

```

  

  [返回页首](#microsoft-edge---policies)

  ### StricterMixedContentTreatmentEnabled

  #### 对混合内容启用更严格的处理（已弃用）

  >已弃用：此策略已弃用。 当前受支持，但将在未来的版本中弃用。
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 81 或更高版本起

  #### 描述

  此策略已弃用，因为它仅作为一种短期机制提供，目的是让企业能够在发现与更严格的混合内容处理不兼容有更多的时间来更新其 Web 内容。 在 Microsoft Edge version 85 将不起作用。

此策略控制浏览器中混合内容（HTTPS 站点中的 HTTP 内容）的处理。

如果将此策略设置为 true 或未设置此策略，则音频和视频混合内容将自动升级到 HTTPS（即，URL 将重写为 HTTPS，如果资源不能通过 HTTPS 提供，则不会回退），并且 URL 栏中将对图像混合内容显示“不安全”警告。

如果将该策略设置为 false，则音频和视频的自动升级将被禁用，并且不会显示图像的警告。

此策略不会影响音频、视频和图像以外其他类型的混合内容。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：StricterMixedContentTreatmentEnabled
  - GP 名称：对混合内容启用更严格的处理（已弃用）
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：StricterMixedContentTreatmentEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：StricterMixedContentTreatmentEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SuppressUnsupportedOSWarning

  #### 禁止对不支持的操作系统显示警告

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  禁止当 Microsoft Edge 在不再受支持的计算机或操作系统上运行时出现的警告。

如果此策略为 false 或未设置，则警告将出现在这些不受支持的计算机或操作系统上。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SuppressUnsupportedOSWarning
  - GP 名称：禁止对不支持的操作系统显示警告
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：SuppressUnsupportedOSWarning
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：SuppressUnsupportedOSWarning
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SyncDisabled

  #### 禁止使用 Microsoft 同步服务进行数据同步

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  禁用 Microsoft Edge 中的数据同步。 此策略还可防止出现同步同意提示。

如果未设置此策略或未按建议应用此策略，用户将能够打开或关闭同步。 如果将此策略应用为强制，用户将无法打开同步。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SyncDisabled
  - GP 名称：禁止使用 Microsoft 同步服务进行数据同步
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：SyncDisabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：SyncDisabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### SyncTypesListDisabled

  #### 配置从同步中排除的类型列表

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 83 或更高版本起

  #### 描述

  如果启用此策略，则所有指定的数据类型都将从同步中排除。 此策略可用于限制上传到 Microsoft Edge 同步服务的数据类型。

可为此策略提供以下数据类型之一：“favorites”、“settings”、“passwords”、“addressesAndMore”、“extensions”、“history”、“openTabs”和“collections”。 请注意，这些数据类型名称区分大小写。

用户将无法替代已禁用的数据类型。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：SyncTypesListDisabled
  - GP 名称：配置从同步中排除的类型列表
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\SyncTypesListDisabled
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\SyncTypesListDisabled\1 = "favorites"

```

  #### Mac 信息和设置
  
  - 首选项项名称：SyncTypesListDisabled
  - 示例值：
``` xml
<array>
  <string>favorites</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### TLS13HardeningForLocalAnchorsEnabled

  #### 为本地信任密钥启用 TLS 1.3 安全功能（已过时）

  
  >已过时：该策略已过时，Microsoft Edge 版本 85 后将无法正常工作。
  #### 支持的版本：

  - 在 Windows 和 macOS 上，自 81 起至 85

  #### 描述

  此策略不起作用，因为它仅作为一种短期机制提供，目的是让企业有更多时间升级受影响的代理。

此策略控制 TLS 1.3 中保护连接免受降级攻击的安全功能。 它向后兼容，不会影响与符合 TLS 1.2 的服务器或代理的连接。 但是，某些 TLS 拦截代理的旧版本存在实现缺陷，导致它们不兼容。

如果启用或未设置此策略，Microsoft Edge 将为所有连接启用这些安全保护。

如果禁用此策略，Microsoft Edge 将对使用本地安装的 CA 证书进行身份验证的连接禁用这些安全保护。 对于通过公共信任的 CA 证书进行身份验证的连接，始终启用这些保护。

此策略可用于测试任何受影响的代理并对其进行升级。 受影响的代理预期会连接失败，并且出现错误代码 ERR_TLS13_DOWNGRADE_DETECTED。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：TLS13HardeningForLocalAnchorsEnabled
  - GP 名称：为本地信任密钥启用 TLS 1.3 安全功能（已过时）
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：TLS13HardeningForLocalAnchorsEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：TLS13HardeningForLocalAnchorsEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### TLSCipherSuiteDenyList

  #### 指定要禁用的 TLS 密码套件

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 85 或更高版本起

  #### 描述

  配置针对 TLS 连接禁用的密码套件的列表。

如果配置了此策略，建立 TLS 连接时将不会使用配置的密码套件列表。

如果未配置此策略，浏览器将选择要使用的 TLS 密码套件。

密码套件值将被指定为十六进制值。 这些值由 Internet 分配的号码核证机关（IANA）注册表分配。

Tls 1.3 所需的 TLS 1.3 密码套件 TLS_AES_128_GCM_SHA256 （0x1301），此策略无法禁用。

此策略不会影响基于 QUIC 的连接。 可通过[QuicAllowed](#quicallowed)策略关闭 QUIC。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称： TLSCipherSuiteDenyList
  - GP 名称：指定要禁用的 TLS 密码套件
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径(强制) :SOFTWARE\Policies\Microsoft\Edge\TLSCipherSuiteDenyList
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\TLSCipherSuiteDenyList\1 = "0x1303"
SOFTWARE\Policies\Microsoft\Edge\TLSCipherSuiteDenyList\2 = "0xcca8"
SOFTWARE\Policies\Microsoft\Edge\TLSCipherSuiteDenyList\3 = "0xcca9"

```

  #### Mac 信息和设置
  
  - 首选参数名称： TLSCipherSuiteDenyList
  - 示例值：
``` xml
<array>
  <string>0x1303</string>
  <string>0xcca8</string>
  <string>0xcca9</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### TabFreezingEnabled

  #### 允许冻结后台选项卡

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 79 或更高版本起

  #### 描述

  控制 Microsoft Edge 是否可以冻结处于后台至少 5 分钟的选项卡。

选项卡冻结可减少 CPU、电池和内存使用。 Microsoft Edge 使用启发式技术来避免冻结在后台执行有用工作的选项卡，例如显示通知、播放声音和流式传输视频。

如果启用或未配置此策略，则已在后台至少 5 分钟的选项卡可能会被冻结。

如果禁用此策略，则不会冻结任何选项卡。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：TabFreezingEnabled
  - GP 名称：允许冻结后台选项卡
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：TabFreezingEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：TabFreezingEnabled
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### TaskManagerEndProcessEnabled

  #### 允许在浏览器任务管理器中结束进程

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  如果启用或未配置此策略，用户可以在浏览器任务管理器中结束进程。 如果禁用该策略，用户将无法结束进程，并且浏览器任务管理器中的“结束进程”按钮将被禁用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：TaskManagerEndProcessEnabled
  - GP 名称：允许在浏览器任务管理器中结束进程
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：TaskManagerEndProcessEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：TaskManagerEndProcessEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### TotalMemoryLimitMb

  #### 设置单个 Microsoft Edge 实例可以使用的内存兆字节限制

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 80 或更高版本起

  #### 描述

  配置在选项卡开始被丢弃以节省内存之前单个 Microsoft Edge 实例可以使用的内存量。 该选项卡所使用的内存将被释放，并且在切换到该选项卡时必须重新加载。

如果启用此策略，一旦超出限制，浏览器将开始丢弃选项卡以节省内存。 但是，不能保证浏览器始终在限制范围内运行。 1024 以下的任何值将四舍五入为 1024。

如果未设置此策略，则浏览器只会在检测到计算机上的物理内存量不足时尝试节省内存。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：TotalMemoryLimitMb
  - GP 名称：设置单个 Microsoft Edge 实例可以使用的内存兆字节限制
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：TotalMemoryLimitMb
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000800
```

  #### Mac 信息和设置
  
  - 首选项项名称：TotalMemoryLimitMb
  - 示例值：
``` xml
<integer>2048</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### TrackingPrevention

  #### 阻止跟踪用户的 Web 浏览活动

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 78 或更高版本起

  #### 描述

  让你决定是否阻止网站跟踪用户的 Web 浏览活动。

如果禁用或未配置此策略，用户可以设置自己的跟踪防护级别。

策略选项映射：

* TrackingPreventionOff (0) = 关闭（无跟踪防护）

* TrackingPreventionBasic (1) = 基本（阻止有害跟踪器，内容和广告将个性化处理）

* TrackingPreventionBalanced (2) = 平衡（阻止有害跟踪器和来自用户未访问过的网站的跟踪器；内容和广告的个性化程度较低）

* TrackingPreventionStrict (3) = 严格（阻止所有站点中的有害跟踪器和大多数跟踪器；内容和广告的个性化程度最低。 网站的某些部分可能无法正常工作）

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：TrackingPrevention
  - GP 名称：阻止跟踪用户的 Web 浏览活动
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：TrackingPrevention
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000002
```

  #### Mac 信息和设置
  
  - 首选项项名称：TrackingPrevention
  - 示例值：
``` xml
<integer>2</integer>
```
  

  [返回页首](#microsoft-edge---policies)

  ### TranslateEnabled

  #### 启用翻译

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  在 Microsoft Edge 上启用集成的 Microsoft 翻译服务。

如果启用此策略，Microsoft Edge 将为用户提供翻译功能，方法是在适当时显示集成的翻译浮出控件，并在右键单击上下文菜单中显示翻译选项。

禁用此策略可禁用所有内置翻译功能。

如果未配置该策略，用户可以选择是否使用翻译功能。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：是
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：TranslateEnabled
  - GP 名称：启用翻译
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：管理模板/Microsoft Edge - 默认（用户可替代）/
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：SOFTWARE\Policies\Microsoft\Edge\Recommended
  - 值名称：TranslateEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：TranslateEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### URLAllowlist

  #### 定义允许的 URL 列表

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  通过设置该策略，可提供对所列 URL 的访问权限，将其作为 [URLBlocklist](#urlblocklist) 的例外情况。

根据 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) 设置 URL 模式的格式。

可使用此策略打开限制性阻止列表的例外。 例如，可以在阻止列表中包括“*”以阻止所有请求，然后使用此策略允许访问有限的 URL 列表。 可以使用此策略打开某些方案、其他域的子域、端口或特定路径的例外。

最具体的筛选器可确定是阻止还是允许 URL。 允许的列表优先于阻止列表。

此策略限制为 1000 个条目；后续条目将被忽略。

通过此策略，浏览器还可以自动调用注册为“电话：”或“ssh：”等协议的协议处理程序的外部应用程序。

如果未配置此策略，则 [URLBlocklist](#urlblocklist) 策略中的阻止列表不存在例外。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：URLAllowlist
  - GP 名称：定义允许的 URL 列表
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\URLAllowlist
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\URLAllowlist\1 = "contoso.com"
SOFTWARE\Policies\Microsoft\Edge\URLAllowlist\2 = "https://ssl.server.com"
SOFTWARE\Policies\Microsoft\Edge\URLAllowlist\3 = "hosting.com/good_path"
SOFTWARE\Policies\Microsoft\Edge\URLAllowlist\4 = "https://server:8080/path"
SOFTWARE\Policies\Microsoft\Edge\URLAllowlist\5 = ".exact.hostname.com"

```

  #### Mac 信息和设置
  
  - 首选项项名称：URLAllowlist
  - 示例值：
``` xml
<array>
  <string>contoso.com</string>
  <string>https://ssl.server.com</string>
  <string>hosting.com/good_path</string>
  <string>https://server:8080/path</string>
  <string>.exact.hostname.com</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### URLBlocklist

  #### 阻止对 URL 列表的访问

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  根据 URL 模式定义被阻止的网站列表（用户无法加载它们）。

根据 [https://go.microsoft.com/fwlink/?linkid=2095322](https://go.microsoft.com/fwlink/?linkid=2095322) 设置 URL 模式的格式。

可在 [URLAllowlist](#urlallowlist) 策略中定义例外。 这些策略限制为 1000 个条目；后续条目将被忽略。

请注意，不建议阻止内部“edge://”URL - 这可能会导致意外错误。

此策略不会阻止页面通过 JavaScript 动态更新。 例如，如果阻止“contoso.com/abc”，只要页面不刷新，用户仍可以访问“contoso.com”并单击链接访问“contoso.com/abc”。

如果未配置此策略，则不会阻止任何 URL。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：URLBlocklist
  - GP 名称：阻止对 URL 列表的访问
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\URLBlocklist
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\1 = "contoso.com"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\2 = "https://ssl.server.com"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\3 = "hosting.com/bad_path"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\4 = "https://server:8080/path"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\5 = ".exact.hostname.com"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\6 = "file://*"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\7 = "custom_scheme:*"
SOFTWARE\Policies\Microsoft\Edge\URLBlocklist\8 = "*"

```

  #### Mac 信息和设置
  
  - 首选项项名称：URLBlocklist
  - 示例值：
``` xml
<array>
  <string>contoso.com</string>
  <string>https://ssl.server.com</string>
  <string>hosting.com/bad_path</string>
  <string>https://server:8080/path</string>
  <string>.exact.hostname.com</string>
  <string>file://*</string>
  <string>custom_scheme:*</string>
  <string>*</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### UserAgentClientHintsEnabled

  #### 启用“User-Agent 客户端提示”功能（已弃用）

  >已弃用：此策略已弃用。 当前受支持，但将在未来的版本中弃用。
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 86 或更高版本起

  #### 描述

  此策略已弃用，因为它仅作为一种短期机制提供，目的是让企业能够在发现与“User-Agent 客户端提示”功能不兼容时有更多的时间来更新其 Web 内容。 它在 Microsoft Edge 版本 89 中将不起作用。

启用后，“User-Agent 客户端提示”功能将发送细化的请求标头，提供有关用户浏览器（例如，浏览器版本）和环境（例如，系统体系结构）的信息。

这是一项附加功能，但是新标头可能会破坏某些限制请求中可能包含的字符的网站。

如果启用或未配置此策略，将启用 “User-Agent 客户端提示”功能。 如果禁用此策略，则此功能不可用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称： UserAgentClientHintsEnabled
  - GP 名称：启用“User-Agent 客户端提示”功能（已弃用）
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：UserAgentClientHintsEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项名称： UserAgentClientHintsEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### UserDataDir

  #### 设置用户数据目录

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  设置用于存储用户数据的目录。

如果启用此策略，Microsoft Edge 将使用指定的目录，而不管用户是否设置了“--user-data-dir”命令行标志。

如果未启用此策略，则使用默认配置文件路径，但用户可以使用“--user-data-dir”标志替代它。 用户可以在 edge://version/ 的配置文件路径下找到配置文件的目录。

为避免数据丢失或其他错误，请不要将此策略配置为卷的根目录或用于其他目的的目录，因为 Microsoft Edge 管理其内容。

有关可使用的变量列表，请参阅 [https://go.microsoft.com/fwlink/?linkid=2095041](https://go.microsoft.com/fwlink/?linkid=2095041)。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：UserDataDir
  - GP 名称：设置用户数据目录
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：UserDataDir
  - 值类型：REG_SZ

  ##### 示例值：

```
"${users}/${user_name}/Edge"
```

  #### Mac 信息和设置
  
  - 首选项项名称：UserDataDir
  - 示例值：
``` xml
<string>${users}/${user_name}/Edge</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### UserDataSnapshotRetentionLimit

  #### 限制保留用于紧急回退的用户数据快照数量

  
  
  #### 支持的版本：

  - 在 86 版或更高版本的 Windows 上

  #### 描述

  按照每个主要版本的更新，Microsoft Edge 将创建用户浏览数据部分的快照，以便在将来的紧急情况下需要临时版本回退时使用。 如果对用户拥有相应快照的版本执行了临时回退，则快照中的数据会被还原。 这可让用户保留书签和自动填充数据等设置。

如果未设置此策略，将使用“3 张快照”的默认值。

如果你设置了此策略，旧的快照将根据需要被删除，以便遵守你设置的限制。 如果将此策略设置为 “0”，则不会执行任何快照。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 整型

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：UserDataSnapshotRetentionLimit
  - GP 名称：限制保留用于紧急回退情况的用户数据快照数量
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：UserDataSnapshotRetentionLimit
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000003
```

  

  [返回页首](#microsoft-edge---policies)

  ### UserFeedbackAllowed

  #### 允许用户反馈

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  Microsoft Edge 使用“Edge 反馈”功能（默认情况下启用），允许用户发送反馈、建议或客户调查以及报告浏览器的任何问题。 此外，默认情况下，用户无法禁用（关闭）“Edge 反馈”功能。

如果启用或未配置此策略，用户可以调用“Edge 反馈”。

如果禁用此策略，则用户不能调用“Edge 反馈”。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：UserFeedbackAllowed
  - GP 名称：允许用户反馈
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：UserFeedbackAllowed
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：UserFeedbackAllowed
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### VideoCaptureAllowed

  #### 允许或阻止视频捕获

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  控制网站是否可以捕获视频。

如果已启用或未配置（默认），系统将要求用户对所有网站授予视频捕获访问权限，但在 [VideoCaptureAllowedUrls](#videocaptureallowedurls) 策略列表中配置了 URL 的网站除外，这些网站将在没有提示的情况下被授予访问权限。

如果禁用此策略，则系统不会提示用户，并且视频捕获仅对在 [VideoCaptureAllowedUrls](#videocaptureallowedurls) 策略中配置的 URL 可用。

此策略会影响所有类型的视频输入，而不仅仅是内置摄像头。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：VideoCaptureAllowed
  - GP 名称：允许或阻止视频捕获
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：VideoCaptureAllowed
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000000
```

  #### Mac 信息和设置
  
  - 首选项项名称：VideoCaptureAllowed
  - 示例值：
``` xml
<false/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### VideoCaptureAllowedUrls

  #### 无需请求许可即可访问视频捕获设备的网站

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  根据 URL 模式指定无需请求用户许可即可使用视频捕获设备的网站。 此列表中的模式将与请求 URL 的安全源进行匹配。 如果二者相符，则将自动向网站授予对视频捕获设备的访问权限。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：VideoCaptureAllowedUrls
  - GP 名称：无需请求许可即可访问视频捕获设备的网站
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\VideoCaptureAllowedUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\VideoCaptureAllowedUrls\1 = "https://www.contoso.com/"
SOFTWARE\Policies\Microsoft\Edge\VideoCaptureAllowedUrls\2 = "https://[*.]contoso.edu/"

```

  #### Mac 信息和设置
  
  - 首选项项名称：VideoCaptureAllowedUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com/</string>
  <string>https://[*.]contoso.edu/</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### WPADQuickCheckEnabled

  #### 设置 WPAD 优化

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  允许你在 Microsoft Edge 中关闭 WPAD（Web 代理自动发现）优化。

如果禁用此策略，则将禁用 WPAD 优化，这会使浏览器对基于 DNS 的 WPAD 服务器等待更长时间。

如果启用或未配置该策略，则将启用 WPAD 优化。

无论是否启用或如何启用此策略，用户都无法更改 WPAD 优化设置。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：WPADQuickCheckEnabled
  - GP 名称：设置 WPAD 优化
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：WPADQuickCheckEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：WPADQuickCheckEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### WebAppInstallForceList

  #### 配置强制安装的 Web 应用列表

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 80 或更高版本起

  #### 描述

  配置此策略以指定一个无需用户交互即可自行安装的网页应用列表，并且用户无法卸载或关闭这些应用程序。

策略的每个列表项都是包含一个强制成员的对象：URL（要安装的 web 应用的 URL）和 2 个可选成员：default_launch_container（指定 web 应用打开的窗口模式 - 新选项卡为默认）和 create_desktop_shortcut（如果要创建 Linux 和 Windows 桌面快捷方式，则为 True）。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - Dictionary

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：WebAppInstallForceList
  - GP 名称：配置强制安装的 Web 应用列表
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：WebAppInstallForceList
  - 值类型：REG_SZ

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\WebAppInstallForceList = [
  {
    "create_desktop_shortcut": true, 
    "default_launch_container": "window", 
    "url": "https://www.contoso.com/maps"
  }, 
  {
    "default_launch_container": "tab", 
    "url": "https://app.contoso.edu"
  }
]
```

  ##### 精简示例值：

  ```
  SOFTWARE\Policies\Microsoft\Edge\WebAppInstallForceList = [{"create_desktop_shortcut": true, "default_launch_container": "window", "url": "https://www.contoso.com/maps"}, {"default_launch_container": "tab", "url": "https://app.contoso.edu"}]
  ```
  

  #### Mac 信息和设置
  
  - 首选项项名称：WebAppInstallForceList
  - 示例值：
``` xml
<key>WebAppInstallForceList</key>
<array>
  <dict>
    <key>create_desktop_shortcut</key>
    <true/>
    <key>default_launch_container</key>
    <string>window</string>
    <key>url</key>
    <string>https://www.contoso.com/maps</string>
  </dict>
  <dict>
    <key>default_launch_container</key>
    <string>tab</string>
    <key>url</key>
    <string>https://app.contoso.edu</string>
  </dict>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### WebCaptureEnabled

  #### 在 Microsoft Edge 中启用网络捕获功能

  
  
  #### 支持的版本：

  - On Windows and macOS since 87 or later

  #### 描述

  在 Microsoft Edge 中启用网页捕获功能，允许用户捕获 Web 内容并使用墨迹书写工具对捕获内容进行批注。
如果启用此策略或不对其进行配置，则会在上下文菜单、“设置”菜单和“更多”菜单中以及使用键盘快捷方式 CTRL+SHIFT+S 时显示网页捕获选项。
如果禁用此策略，用户将无法在 Microsoft Edge 中访问网页捕获功能。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：是

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：WebCaptureEnabled
  - GP 名称：Enable web capture feature in Microsoft Edge
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：WebCaptureEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：WebCaptureEnabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### WebComponentsV0Enabled

  #### 重新启用 Web Components v0 API 直至 M84（已过时）

  
  >已过时：该策略已过时，Microsoft Edge 版本 84 后将无法正常工作。
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 80 起至 84

  #### 描述

  此策略不起作用，因为此策略允许在 Microsoft Edge 版本85前有选择地重新启用这些功能。 Web Components v0 API（Shadow DOM v0、Custom Elements v0 和 HTML Imports）在 2018 中已弃用，并且从 Microsoft Edge 版本 80 开始已默认禁用。

如果将此策略设置为 True，则将为所有网站启用 Web Components v0 API 功能。

如果将此策略设置为 False 或未设置此策略，则从 Microsoft Edge 版本 80 开始，Web Components v0 功能将默认禁用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：WebComponentsV0Enabled
  - GP 名称：重新启用 Web Components v0 API 直至 M84（已过时）
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：WebComponentsV0Enabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：WebComponentsV0Enabled
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### WebDriverOverridesIncompatiblePolicies

  #### 允许 WebDriver 替代不兼容的策略（已弃用）

  >已弃用：此策略已弃用。 当前受支持，但将在未来的版本中弃用。
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 起至 84

  #### 描述

  此策略不起作用，因为 WebDriver 现在与所有现有策略兼容。

此策略允许 WebDriver 功能的用户替代可能干扰其操作的策略。

当前，此策略禁用 [SitePerProcess](#siteperprocess) 和 [IsolateOriggins](#isolateorigins) 策略。

如果启用该策略，WebDriver 将能够替代不兼容的策略。
如果禁用或未配置该策略，则不允许 WebDriver 替代不兼容的策略。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：WebDriverOverridesIncompatiblePolicies
  - GP 名称：允许 WebDriver 替代不兼容的策略（已弃用）
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：WebDriverOverridesIncompatiblePolicies
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  #### Mac 信息和设置
  
  - 首选项项名称：WebDriverOverridesIncompatiblePolicies
  - 示例值：
``` xml
<true/>
```
  

  [返回页首](#microsoft-edge---policies)

  ### WebRtcLocalIpsAllowedUrls

  #### 管理通过 WebRTC 暴露本地 IP 地址

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 80 或更高版本起

  #### 描述

  指定 WebRTC 应暴露其本地 IP 地址的源 (URL) 或主机名模式（如“*contoso.com*”）列表。

如果启用此策略并设置源 (URL) 或主机名模式列表，则当启用 edge://flags/#enable-webrtc-hide-local-ips-with-mdns 时，WebRTC 将显示与列表中模式匹配的案例的本地 IP 地址。

如果禁用或未配置此策略，并且启用了 edge://flags/#enable-webrtc-hide-local-ips-with-mdns，则 WebRTC 将不会暴露本地 IP 地址。 本地 IP 地址将屏蔽为 mDNS 主机名。

如果启用、禁用或未配置此策略，并且禁用了 edge://flags/#enable-webrtc-hide-local-ips-with-mdns，则 WebRTC 将暴露本地 IP 地址。

请注意，此策略会削弱管理员可能需要的本地 IP 地址保护。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 字符串列表

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：WebRtcLocalIpsAllowedUrls
  - GP 名称：管理通过 WebRTC 暴露本地 IP 地址
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge\WebRtcLocalIpsAllowedUrls
  - 路径（推荐）：不适用
  - 值名称：1, 2, 3, ...
  - 值类型：REG_SZ 列表

  ##### 示例值：

```
SOFTWARE\Policies\Microsoft\Edge\WebRtcLocalIpsAllowedUrls\1 = "https://www.contoso.com"
SOFTWARE\Policies\Microsoft\Edge\WebRtcLocalIpsAllowedUrls\2 = "*contoso.com*"

```

  #### Mac 信息和设置
  
  - 首选项项名称：WebRtcLocalIpsAllowedUrls
  - 示例值：
``` xml
<array>
  <string>https://www.contoso.com</string>
  <string>*contoso.com*</string>
</array>
```
  

  [返回页首](#microsoft-edge---policies)

  ### WebRtcLocalhostIpHandling

  #### 限制通过 WebRTC 暴露本地 IP 地址

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  允许你设置 WebRTC 是否暴露用户的本地 IP 地址。

如果将此策略设置为 "AllowAllInterfaces" 或 "AllowPublicAndPrivateInterfaces"，WebRTC 将公开本地 IP 地址。

如果将此策略设置为 "AllowPublicInterfaceOnly" 或 "DisableNonProxiedUdp"，则 WebRTC 不会公开本地 IP 地址。

如果未设置此策略或者将其禁用，WebRTC 会暴露本地 IP 地址。

策略选项映射：

* AllowAllInterfaces (default) = 允许所有界面。 这将暴露本地 IP 地址

* AllowPublicAndPrivateInterfaces (default_public_and_private_interfaces) = 允许公共和专用接口使用 http 默认路由。 这将暴露本地 IP 地址

* AllowPublicInterfaceOnly (default_public_interface_only) = 允许公共接口使用 http 默认路由。 这不会暴露本地 IP 地址

* DisableNonProxiedUdp (disable_non_proxied_udp) = 使用 TCP，除非代理服务器支持 UDP。 这不会暴露本地 IP 地址

配置此策略时，请使用上述信息。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：WebRtcLocalhostIpHandling
  - GP 名称：限制通过 WebRTC 暴露本地 IP 地址
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：WebRtcLocalhostIpHandling
  - 值类型：REG_SZ

  ##### 示例值：

```
"default"
```

  #### Mac 信息和设置
  
  - 首选项项名称：WebRtcLocalhostIpHandling
  - 示例值：
``` xml
<string>default</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### WebRtcUdpPortRange

  #### 限制 WebRTC 使用的本地 UDP 端口的范围

  
  
  #### 支持的版本：

  - 在 Windows 和 macOS 上自 77 或更高版本起

  #### 描述

  将 WebRTC 使用的 UDP 端口范围限制为指定的端口间隔（包括终结点）。

通过配置此策略，可指定 WebRTC 可以使用的本地 UDP 端口的范围。

如果未配置此策略，或者将其设置为空字符串或无效端口范围，则 WebRTC 可以使用任何可用的本地 UDP 端口。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 字符串

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称：WebRtcUdpPortRange
  - GP 名称：限制 WebRTC 使用的本地 UDP 端口的范围
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：WebRtcUdpPortRange
  - 值类型：REG_SZ

  ##### 示例值：

```
"10000-11999"
```

  #### Mac 信息和设置
  
  - 首选项项名称：WebRtcUdpPortRange
  - 示例值：
``` xml
<string>10000-11999</string>
```
  

  [返回页首](#microsoft-edge---policies)

  ### WebWidgetAllowed

  #### 启用 Web 构件

  
  
  #### 支持的版本：

  - 在 88 版或更高版本的 Windows 上

  #### 描述

  启用 Web 构件。 启用此功能后，用户可以使用构件从桌面或应用程序中搜索网页。 构件提供一个搜索框，显示 web 建议并打开 Microsoft Edge 中的所有 web 搜索。 "搜索" 框提供搜索（由必应提供支持）和 URL 建议。 该构件还包含源磁贴，用户可单击该磁贴以查看有关新 Microsoft Edge 浏览器选项卡或窗口中 msn.com 的详细信息。 源磁贴可能包含广告。 可从 Microsoft Edge 设置或 Microsoft Edge 中的 "更多工具" 菜单启动构件。

如果启用或未配置此策略：将自动为所有配置文件启用网页构件。
在 "Microsoft Edge 设置" 中，用户将看到用于启动构件的选项。
在 "Microsoft Edge 设置" 中，用户将看到菜单项用于在 Windows 启动时运行构件（自动启动）。
如果启用了 [WebWidgetIsEnabledOnStartup](#webwidgetisenabledonstartup) 策略，则启动时启用该构件的选项将切换。
如果已禁用或未配置 [WebWidgetIsEnabledOnStartup](#webwidgetisenabledonstartup) ，则启动时启用该构件的选项将关闭。
用户将看到从 "Microsoft Edge" 的 "更多工具" 菜单启动构件的菜单项。 用户可从 "更多工具" 启动构件。
可通过系统托盘中的 "退出" 选项或通过从任务栏关闭构件来关闭构件。 如果启用了自动启动，将在系统重新启动时重新启动该构件。

如果禁用此策略：将禁用所有配置文件的 Web 构件。
从 Microsoft Edge 设置启动构件的选项将被禁用。
在 Windows 启动时启动 "开始" 的选项（自动启动）将被禁用。
从 Microsoft Edge "更多工具" 菜单启动构件的选项将被禁用。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称： WebWidgetAllowed
  - GP名称：启用 Web 构件
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称： WebWidgetAllowed
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  

  [返回页首](#microsoft-edge---policies)

  ### WebWidgetIsEnabledOnStartup

  #### 在 Windows 启动时允许Web构件

  
  
  #### 支持的版本：

  - 在 88 版或更高版本的 Windows 上

  #### 描述

  允许 Web 构件在 Windows 启动时开始运行。

如果启用：默认情况下，Web 构件将在 Windows 启动时开始运行。
如果通过 [WebWidgetAllowed "](#webwidgetallowed) " 策略禁用了构件，则在 Windows 启动时，此策略将不会启动该构件。

如果禁用此策略： 所有配置文件的Web构件不会在 Windows 启动时启动。
在 Windows 启动时启动构件的选项将在 "Microsoft Edge 设置" 中被禁用，并处于关闭状态。

如果未配置策略：所有配置文件的 Web 构件不会在 Windows 启动时启动。
在 Windows 启动时，启动构件的选项将在 "Microsoft Edge 设置" 中处于关闭状态。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称： WebWidgetIsEnabledOnStartup
  - GP名称：在 Windows 启动时允许Web构件
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称：WebWidgetIsEnabledOnStartup
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  

  [返回页首](#microsoft-edge---policies)

  ### WinHttpProxyResolverEnabled

  #### 使用 Windows 代理解析程序（已弃用）

  >已弃用：此策略已弃用。 当前受支持，但将在未来的版本中弃用。
  
  #### 支持的版本：

  - 在 84 版或更高版本的 Windows 上

  #### 描述

  此策略已弃用，因为未来版本中的类似功能将取代该策略，请参阅https://crbug.com/1032820。

使用 Windows 来解析所有浏览器网络的代理，而不是内置在 Microsoft Edge 中的代理解析器。 Windows 代理解析器支持 Windows 代理功能，如DirectAccess/NRPT。

此策略附带由https://crbug.com/644030描述的问题。 它会导致 Windows 代码提取并执行 PAC 文件，包括通过[ProxyPacUrl](#proxypacurl)策略设置的 PAC 文件。 由于网络获取 PAC 文件是通过 Windows 而不是 Microsoft Edge 代码进行的，网络策略如[DnsOverHttpsMode](#dnsoverhttpsmode)将不会应用于网络获取 PAC 文件。

如果启用此策略，将使用 Windows 代理解决程序。

如果禁用或未配置此策略，将使用 Microsoft Edge 代理解决程序。

  #### 支持的功能：

  - 可以强制：是
  - 可以推荐：否
  - 动态策略刷新：否 - 需要重新启动浏览器

  #### 数据类型：

  - 布尔

  #### Windows 信息和设置

  ##### 组策略 (ADMX) 信息

  - GP 唯一名称： WinHttpProxyResolverEnabled
  - GP 名称：使用 Windows 代理解析程序（已弃用）
  - GP 路径（强制）：管理模板/Microsoft Edge/
  - GP 路径（推荐）：不适用
  - GP ADMX 文件名：MSEdge.admx

  ##### Windows 注册表设置

  - 路径（强制）：SOFTWARE\Policies\Microsoft\Edge
  - 路径（推荐）：不适用
  - 值名称： WinHttpProxyResolverEnabled
  - 值类型：REG_DWORD

  ##### 示例值：

```
0x00000001
```

  

  [返回页首](#microsoft-edge---policies)


## 另请参阅

- [配置 Microsoft Edge](configure-microsoft-edge.md)
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [Microsoft 安全基线博客](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/bg-p/Microsoft-Security-Baselines)