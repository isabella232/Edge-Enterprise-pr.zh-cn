---
title: Microsoft Edge 旧版到 Microsoft Edge 策略映射
ms.author: brianalt
author: brianalt
manager: srugh
ms.date: 02/10/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 旧版到 Microsoft Edge 策略映射
ms.openlocfilehash: f0ce58f3876bf9f02691d7d6bf2a7c7d1944fd24
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447996"
---
# <a name="microsoft-edge-legacy-to-microsoft-edge-policy-mapping"></a>Microsoft Edge 旧版到 Microsoft Edge 策略映射

本文将 Microsoft Edge 旧版本（版本 45 及更低版本）组策略 (GP) 和移动设备管理 (MDM) 设置映射到相关的 Microsoft Edge 版本 80 策略。 有关 Google Chrome 策略，请参阅 [Google Chrome 到 Microsoft Edge 策略映射](microsoft-edge-policy-map-chrome-to-newedge.md) 文章。

> [!NOTE]
> 下面提供的映射旨在帮助你进行 Microsoft Edge 版本 80 的初始部署。 有关最新策略的权威性列表，请参阅：
> - [浏览器策略参考](microsoft-edge-policies.md)
> - [更新策略参考](microsoft-edge-update-policies.md)

## <a name="microsoft-edge-legacy-to-microsoft-edge-policy-map"></a>Microsoft Edge 旧版本到 Microsoft Edge 策略映射

|Microsoft Edge 旧版本 GP|Microsoft Edge 旧版本 MDM|Microsoft Edge 策略 <br> 和 GP 名称|
|-|-|-|
|[允许共享书籍文件夹](/microsoft-edge/deploy/available-policies#allow-a-shared-books-folder)|[UseSharedFolderForBooks](/windows/client-management/mdm/policy-csp-browser#browser-usesharedfolderforbooks)|不适用|
|[允许使用地址栏下拉列表建议](/microsoft-edge/deploy/available-policies#allow-address-bar-drop-down-list-suggestions)|[AllowAddressBarDropdown](/windows/client-management/mdm/policy-csp-browser#browser-allowaddressbardropdown)|[SearchSuggestEnabled](./microsoft-edge-policies.md#searchsuggestenabled) <br> 启用搜索建议|
|[允许使用 Adobe Flash](/microsoft-edge/deploy/available-policies#allow-adobe-flash)|[AllowFlash](/windows/client-management/mdm/policy-csp-browser#browser-allowflash)|[DefaultPluginsSetting](./microsoft-edge-policies.md#defaultpluginssetting) <br> 默认 Adobe Flash 设置|
|[允许退出时清除浏览数据](/microsoft-edge/deploy/available-policies#allow-clearing-browsing-data-on-exit)|[ClearBrowsingDataOnExit](/windows/client-management/mdm/policy-csp-browser#browser-clearbrowsingdataonexit)|[ClearBrowsingDataOnExit](./microsoft-edge-policies.md#clearbrowsingdataonexit) <br> 在 Microsoft Edge 关闭时清除浏览数据|
|[允许对书籍库进行配置更新](/microsoft-edge/deploy/available-policies#allow-configuration-updates-for-the-books-library)|[AllowConfigurationUpdateForBooksLibrary](/windows/client-management/mdm/policy-csp-browser#browser-allowconfigurationupdateforbookslibrary)|不适用|
|[允许使用 Cortana](/microsoft-edge/deploy/available-policies#allow-cortana)|[AllowCortana](/windows/client-management/mdm/policy-csp-browser#browser-allowcortana)|不适用|
|[允许开发人员工具](/microsoft-edge/deploy/available-policies#allow-developer-tools)|[AllowDeveloperTools](/windows/client-management/mdm/policy-csp-browser#browser-allowdevelopertools)|[DeveloperToolsAvailability](./microsoft-edge-policies.md#developertoolsavailability) <br> 控制可使用开发人员工具的位置|
|[允许“书籍”选项卡的扩展遥测](/microsoft-edge/deploy/available-policies#allow-extended-telemetry-for-the-books-tab)|[EnableExtendedBooksTelemetry](/windows/client-management/mdm/policy-csp-browser#browser-enableextendedbookstelemetry)|不适用|
|[允许扩展](/microsoft-edge/deploy/available-policies#allow-extensions)|[AllowExtensions](/windows/client-management/mdm/policy-csp-browser#browser-allowextensions)|[ExtensionInstallBlockList](./microsoft-edge-policies.md#extensioninstallblocklist) <br> 控制无法安装的扩展 <br/><br/>_若要阻止所有扩展，使用“*”_|
|[允许全屏模式](/microsoft-edge/deploy/group-policies/browser-settings-management-gp#allow-fullscreen-mode)|[AllowFullscreen](/windows/client-management/mdm/policy-csp-browser#browser-allowfullscreen)|[FullscreenAllowed](./microsoft-edge-policies.md#fullscreenallowed) <br> 允许全屏模式|
|[允许 Microsoft 兼容性列表](/microsoft-edge/deploy/available-policies#allow-microsoft-compatibility-list)|[AllowMicrosoftCompatibilityList](/windows/client-management/mdm/policy-csp-browser#browser-allowmicrosoftcompatibilitylist)|不适用|
|[允许 Microsoft Edge 在 Windows 启动时、系统空闲时和每次关闭 Microsoft edge 时预先启动](/microsoft-edge/deploy/group-policies/prelaunch-preload-gp#allow-microsoft-edge-to-load-the-start-and-new-tab-page-at-windows-startup-and-each-time-microsoft-edge-is-closed)|[AllowPrelaunch](/windows/client-management/mdm/policy-csp-browser#browser-allowprelaunch)|不适用|
|[允许 Microsoft Edge 在 Windows 启动时和每次关闭 Microsoft Edge 时启动并加载“开始”和“新标签页”页面](/microsoft-edge/deploy/group-policies/prelaunch-preload-gp#allow-microsoft-edge-to-load-the-start-and-new-tab-page-at-windows-startup-and-each-time-microsoft-edge-is-closed)|[AllowTabPreloading](/windows/client-management/mdm/policy-csp-browser#browser-allowtabpreloading)|[BackgroundModeEnabled](./microsoft-edge-policies.md#backgroundmodeenabled) <br> 关闭 Microsoft Edge 后继续运行后台应用|
|[允许打印](/microsoft-edge/deploy/group-policies/browser-settings-management-gp#allow-printing)|[AllowPrinting](/windows/client-management/mdm/policy-csp-browser#browser-allowprinting)|[PrintingEnabled](./microsoft-edge-policies.md#printingenabled) <br> 启用打印|
|[允许保存历史记录](/microsoft-edge/deploy/group-policies/browser-settings-management-gp#allow-saving-history)|[AllowSavingHistory](/windows/client-management/mdm/policy-csp-browser#browser-allowsavinghistory)|[SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled) <br> 禁止保存浏览器历史记录|
|[允许搜索引擎自定义](/microsoft-edge/deploy/available-policies#allow-search-engine-customization)|[AllowSearchEngineCustomization](/windows/client-management/mdm/policy-csp-browser#browser-allowsearchenginecustomization)|[请参阅默认搜索提供程序策略](./microsoft-edge-policies.md#default-search-provider)|
|[允许旁加载扩展](/microsoft-edge/deploy/group-policies/extensions-management-gp#allow-sideloading-of-extensions)|[AllowSideloadingExtensions](/windows/client-management/mdm/policy-csp-browser#browser-allowsideloadingextensions)|[ExtensionInstallBlocklist](./microsoft-edge-policies.md#extensioninstallblocklist)<br/>控制无法安装的扩展<br/>或 [DeveloperToolsAvailability](./microsoft-edge-policies.md#developertoolsavailability)<br/>控制可使用开发人员工具的位置|
|[允许“新建选项卡”页面中的 Web 内容](/microsoft-edge/deploy/available-policies#allow-web-content-on-new-tab-page)|[AllowWebContentOnNewTabPage](/windows/client-management/mdm/policy-csp-browser#browser-allowwebcontentonnewtabpage)|[NewTabPageLocation](./microsoft-edge-policies.md#newtabpagelocation) <br> 配置新标签页 URL|
|[始终在 Microsoft Edge 中显示书籍库](/microsoft-edge/deploy/available-policies#always-show-the-books-library-in-microsoft-edge)|[AlwaysEnableBooksLibrary](/windows/client-management/mdm/policy-csp-browser#browser-alwaysenablebookslibrary)|不适用|
|[配置其他搜索引擎](/microsoft-edge/deploy/available-policies#configure-additional-search-engines)|[ConfigureAdditionalSearchEngines](/windows/client-management/mdm/policy-csp-browser#browser-configureadditionalsearchengines)|[请参阅默认搜索提供程序策略](./microsoft-edge-policies.md#default-search-provider)|
|[配置自动填充](/microsoft-edge/deploy/available-policies#configure-autofill)|[AllowAutofill](/windows/client-management/mdm/policy-csp-browser#browser-allowautofill)|[AutofillAddressEnabled](./microsoft-edge-policies.md#autofilladdressenabled) <br> 启用地址自动填充|
|[配置 Cookie](/microsoft-edge/deploy/group-policies/security-privacy-management-gp#configure-cookies)|[AllowCookies](/windows/client-management/mdm/policy-csp-browser#browser-allowcookies)|[DefaultCookiesSetting](./microsoft-edge-policies.md#defaultcookiessetting) <br> 配置 Cookie|
|[配置 Do Not Track](/microsoft-edge/deploy/available-policies#configure-do-not-track)|[AllowDoNotTrack](/windows/client-management/mdm/policy-csp-browser#browser-allowdonottrack)|[ConfigureDoNotTrack](./microsoft-edge-policies.md#configuredonottrack) <br> 配置 Do Not Track|
|[配置收藏夹栏](/microsoft-edge/deploy/group-policies/favorites-management-gp#configure-favorites-bar)|[ConfigureFavoritesBar](/windows/client-management/mdm/policy-csp-browser#browser-configurefavoritesbar)|[FavoritesBarEnabled](./microsoft-edge-policies.md#favoritesbarenabled) <br> 启用收藏夹栏|
|[配置“开始”按钮](/microsoft-edge/deploy/group-policies/home-button-gp#configure-home-button)|[ConfigureHomeButton](/windows/client-management/mdm/policy-csp-browser#browser-configurehomebutton)|[HomepageIsNewTabPage](./microsoft-edge-policies.md#homepageisnewtabpage) <br> 将新标签页设置为开始页|
|[配置展台模式](/windows/client-management/mdm/policy-csp-browser#browser-configurekioskmode)|[ConfigureKioskMode](/windows/client-management/mdm/policy-csp-browser#browser-configurekioskmode)|不适用|
|[配置空闲超时后的展台复位](/windows/client-management/mdm/policy-csp-browser#browser-configurekioskresetafteridletimeout)|[ConfigureKioskResetAfterIdleTimeout](/windows/client-management/mdm/policy-csp-browser#browser-configurekioskresetafteridletimeout)|不适用|
|[配置 Microsoft Edge 打开方式](/microsoft-edge/deploy/group-policies/start-pages-gp#configure-open-microsoft-edge-with)|[ConfigureOpenEdgeWith](/windows/client-management/mdm/policy-csp-browser#browser-configureopenedgewith)|[RestoreOnStartup](./microsoft-edge-policies.md#restoreonstartup) <br> 启动时要执行的操作|
|[配置密码管理器](/microsoft-edge/deploy/available-policies#configure-password-manager)|[AllowPasswordManager](/windows/client-management/mdm/policy-csp-browser#browser-allowpasswordmanager)|[PasswordManagerEnabled](./microsoft-edge-policies.md#passwordmanagerenabled) <br> 允许将密码保存到密码管理器|
|[配置弹出窗口阻止程序](/microsoft-edge/deploy/available-policies#configure-pop-up-blocker)|[AllowPopups](/windows/client-management/mdm/policy-csp-browser#browser-allowpopups)|[DefaultPopupsSetting](./microsoft-edge-policies.md#defaultpopupssetting) <br> 默认弹出窗口设置|
|[配置地址栏中的搜索建议](/microsoft-edge/deploy/available-policies#configure-search-suggestions-in-address-bar)|[AllowSearchSuggestionsinAddressBar](/windows/client-management/mdm/policy-csp-browser#browser-allowsearchsuggestionsinaddressbar)|[请参阅默认搜索提供程序策略](./microsoft-edge-policies.md#default-search-provider)|
|[配置“开始”页面](/microsoft-edge/deploy/available-policies#configure-start-pages)|[主页](/windows/client-management/mdm/policy-csp-browser#browser-homepages)|[RestoreOnStartupURLs](./microsoft-edge-policies.md#restoreonstartupurls) <br> 浏览器启动时要打开的站点|
|[配置 Adobe Flash 即点即用设置](/microsoft-edge/deploy/available-policies#configure-the-adobe-flash-click-to-run-setting)|[AllowFlashClickToRun](/windows/client-management/mdm/policy-csp-browser#browser-allowflashclicktorun)|[DefaultPluginsSetting](./microsoft-edge-policies.md#defaultpluginssetting) <br> 默认 Adobe Flash 设置|
|[配置企业模式站点列表](/microsoft-edge/deploy/available-policies#configure-the-enterprise-mode-site-list)|[EnterpriseModeSiteList](/windows/client-management/mdm/policy-csp-browser#browser-enterprisemodesitelist)|[InternetExplorerIntegrationSiteList](./microsoft-edge-policies.md#internetexplorerintegrationsitelist) <br> 配置企业模式站点列表|
|[配置 Windows Defender SmartScreen](/microsoft-edge/deploy/available-policies#configure-windows-defender-smartscreen)|[AllowSmartScreen](/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen)|[SmartScreenEnabled](./microsoft-edge-policies.md#smartscreenenabled) <br> 配置 Microsoft Defender SmartScreen|
|[禁用锁定“开始”页面](/microsoft-edge/deploy/available-policies#disable-lockdown-of-start-pages)|[DisableLockdownOfStartPages](/windows/client-management/mdm/policy-csp-browser#browser-disablelockdownofstartpages)|[RestoreOnStartupURLs](./microsoft-edge-policies.md#restoreonstartupurls) <br> 浏览器启动时要打开的网站（推荐的版本）|
|[不同步](/microsoft-edge/deploy/available-policies#do-not-sync)|[AllowSyncMySettings](/windows/client-management/mdm/policy-csp-browser#browser-allowsyncmysettings)|[SyncDisabled](./microsoft-edge-policies.md#syncdisabled) <br> 禁止使用 Microsoft 同步服务进行数据同步|
|[不同步浏览器设置](/microsoft-edge/deploy/available-policies#do-not-sync-browser-settings)|[DoNotSyncBrowserSettings](/windows/client-management/mdm/policy-csp-experience#experience-donotsyncbrowsersetting)|不适用|
|[在 Internet Explorer 和 Microsoft Edge 之间保持收藏夹同步](/microsoft-edge/deploy/available-policies#keep-favorites-in-sync-between-internet-explorer-and-microsoft-edge)|[SyncFavoritesBetweenIEAndMicrosoftEdge](/windows/client-management/mdm/policy-csp-browser#browser-syncfavoritesbetweenieandmicrosoftedge)|不适用|
|[阻止对 about:flags 页面的访问](/microsoft-edge/deploy/available-policies#prevent-access-to-the-aboutflags-page)|[PreventAccessToAboutFlagsInMicrosoftEdge](/windows/client-management/mdm/policy-csp-browser#browser-preventaccesstoaboutflagsinmicrosoftedge)|[URLBlocklist](./microsoft-edge-policies.md#urlblocklist) <br> 阻止对 URL 列表的访问 <br/><br/>_设置为“edge://flags”。 建议不要使用此策略来阻止 edge://* 页面，因为这可能会产生意想不到的结果。_|
|[阻止绕过对文件的 Windows Defender SmartScreen 提示](/microsoft-edge/deploy/available-policies#prevent-bypassing-windows-defender-smartscreen-prompts-for-files)|[PreventSmartScreenPromptOverrideForFiles](/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverrideforfiles)|[PreventSmartScreenPromptOverrideForFiles](./microsoft-edge-policies.md#preventsmartscreenpromptoverrideforfiles) <br> 阻止绕过 Microsoft Defender SmartScreen 有关下载的警告|
|[阻止绕过对站点的 Windows Defender SmartScreen 提示](/microsoft-edge/deploy/available-policies#prevent-bypassing-windows-defender-smartscreen-prompts-for-sites)|[PreventSmartscreenPromptOverride](/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverride)|[PreventSmartScreenPromptOverride](./microsoft-edge-policies.md#preventsmartscreenpromptoverride) <br> 阻止绕过 Microsoft Defender SmartScreen 有关站点的提示|
|[防止证书错误覆盖](/microsoft-edge/deploy/group-policies/security-privacy-management-gp#prevent-certificate-error-overrides)|[PreventCertErrorOverrides](/windows/client-management/mdm/policy-csp-browser#browser-preventcerterroroverrides)|[SSLErrorOverrideAllowed](./microsoft-edge-policies.md#sslerroroverrideallowed) <br> 允许用户从 HTTPS 警告页面继续操作|
|[阻止更改 Microsoft Edge 上的收藏夹](/microsoft-edge/deploy/available-policies#prevent-changes-to-favorites-on-microsoft-edge)|[LockdownFavorites](/windows/client-management/mdm/policy-csp-browser#browser-lockdownfavorites)|[EditFavoritesEnabled](./microsoft-edge-policies.md#editfavoritesenabled) <br> 允许用户编辑收藏夹|
|[阻止 Microsoft Edge 在用户将站点固定到“开始”菜单时收集动态磁贴信息](/microsoft-edge/deploy/available-policies#prevent-microsoft-edge-from-gathering-live-tile-information-when-pinning-a-site-to-start)|[PreventLiveTileDataCollection](/windows/client-management/mdm/policy-csp-browser#browser-preventlivetiledatacollection)|不适用|
|[阻止在 Microsoft Edge 中打开首次运行网页](/microsoft-edge/deploy/available-policies#prevent-the-first-run-webpage-from-opening-on-microsoft-edge)|[PreventFirstRunPage](/windows/client-management/mdm/policy-csp-browser#browser-preventfirstrunpage)|[HideFirstRunExperience](./microsoft-edge-policies.md#hidefirstrunexperience) <br> 隐藏首次运行体验和初始屏幕|
|[阻止关闭所需扩展](/microsoft-edge/deploy/group-policies/extensions-management-gp#prevent-turning-off-required-extensions)|[PreventTurningOffRequiredExtensions](/windows/client-management/mdm/policy-csp-browser#browser-preventturningoffrequiredextensions)|[ExtensionInstallForcelist](./microsoft-edge-policies.md#extensioninstallforcelist) <br> 控制静默安装的扩展|
|[阻止用户启用浏览器同步](/microsoft-edge/deploy/available-policies#prevent-users-from-turning-on-browser-syncing)|[PreventUsersFromTurningOnBrowserSyncing](/windows/client-management/mdm/policy-csp-experience#experience-preventusersfromturningonbrowsersyncing)|不适用|
|[阻止为 WebRTC 使用 Localhost IP 地址](/microsoft-edge/deploy/available-policies#prevent-using-localhost-ip-address-for-webrtc)|[PreventUsingLocalHostIPAddressForWebRTC](/windows/client-management/mdm/policy-csp-browser#browser-preventusinglocalhostipaddressforwebrtc)|[WebRtcLocalhostIpHandling](./microsoft-edge-policies.md#webrtclocalhostiphandling) <br> 限制通过 WebRTC 暴露本地 IP 地址|
|[预配收藏夹](/microsoft-edge/deploy/available-policies#provision-favorites)|[ProvisionFavorites](/windows/client-management/mdm/policy-csp-browser#browser-provisionfavorites)|[ManagedFavorites](./microsoft-edge-policies.md#managedfavorites) <br> 配置收藏夹|
|[将所有 Intranet 站点都发送到 Internet Explorer 11](/microsoft-edge/deploy/available-policies#send-all-intranet-sites-to-internet-explorer-11)|[SendIntranetTraffictoInternetExplorer](/windows/client-management/mdm/policy-csp-browser#browser-sendintranettraffictointernetexplorer)|[SendIntranetToInternetExplorer](./microsoft-edge-policies.md#sendintranettointernetexplorer) <br> 将所有 Intranet 站点都发送到 Internet Explorer|
|[设置默认搜索引擎](/microsoft-edge/deploy/available-policies#set-default-search-engine)|[SetDefaultSearchEngine](/windows/client-management/mdm/policy-csp-browser#browser-setdefaultsearchengine)|[请参阅默认搜索提供程序策略](./microsoft-edge-policies.md#default-search-provider)|
|[设置“开始”按钮 URL](/microsoft-edge/deploy/group-policies/home-button-gp#set-home-button-url)|[SetHomeButtonURL](/windows/client-management/mdm/policy-csp-browser#browser-sethomebuttonurl)|[HomepageLocation](./microsoft-edge-policies.md#homepagelocation) <br> 配置开始页 URL|
|[设置新标签页 URL](/microsoft-edge/deploy/group-policies/new-tab-page-settings-gp#set-new-tab-page-url)|[SetNewTabPageURL](/windows/client-management/mdm/policy-csp-browser#browser-setnewtabpageurl)|[NewTabPageLocation](./microsoft-edge-policies.md#newtabpagelocation) <br> 配置新标签页 URL|
|[在 Internet Explorer 中打开站点时显示消息](/microsoft-edge/deploy/available-policies#show-message-when-opening-sites-in-internet-explorer)|[ShowMessageWhenOpeningSitesInInternetExplorer](/windows/client-management/mdm/policy-csp-browser#browser-showmessagewhenopeningsitesininternetexplorer)|不适用|
|[解锁开始按钮](/microsoft-edge/deploy/group-policies/home-button-gp#unlock-home-button)|[UnlockHomeButton](/windows/client-management/mdm/policy-csp-browser#browser-unlockhomebutton)|[ShowHomeButton ](./microsoft-edge-policies.md#showhomebutton) <br> 在工具栏上显示“开始”按钮（推荐的版本）|


## <a name="see-also"></a>另请参阅
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [配置 Microsoft Edge](configure-microsoft-edge.md)
-   [浏览器策略参考](microsoft-edge-policies.md)