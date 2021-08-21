---
title: Microsoft Edge Stable 渠道发行说明
ms.author: aguta
author: AndreaLBarr
manager: srugh
ms.date: 08/19/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Stable 渠道发行说明
ms.openlocfilehash: 66d70216da337b5052a7e5b86446db50c30a6f66
ms.sourcegitcommit: 81ecf79c5fd604cae91aaec3786859172c83ec79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2021
ms.locfileid: "11909897"
---
# <a name="release-notes-for-microsoft-edge-stable-channel"></a>Microsoft Edge Stable 渠道发行说明

这些发行说明提供有关 Microsoft Edge Stable 渠道中包含的新功能和非安全更新的信息。

- [此处](microsoft-edge-relnotes-security.md)列出所有安全更新。
- Microsoft Edge 稳定渠道的存档发行说明位于[此处](microsoft-edge-relnote-archive-stable-channel.md)。

 若要了解 Microsoft Edge 渠道，请参阅 [Microsoft Edge 渠道概述](microsoft-edge-channels.md)。

> [!NOTE]
> 对于稳定渠道，更新将在一天或多天内逐步推出。 要了解详细信息，请参阅 [Microsoft Edge 更新的渐进式推出](microsoft-edge-update-progressive-rollout.md)。
>
> Microsoft Edge Web 平台不断发展以改进用户体验、安全性和隐私。 要了解详细信息，请参阅 [Microsoft Edge 中影响网站兼容性的更改](/microsoft-edge/web-platform/site-impacting-changes)。

## <a name="version-92090278-august-19"></a>版本 92.0.902.78：8 月 19 日

[此处](/deployedge/microsoft-edge-relnotes-security#august-19-2021)列出了稳定渠道的安全更新。

## <a name="version-92090267-august-5"></a>版本 92.0.902.67：8 月 5 日

[此处](/deployedge/microsoft-edge-relnotes-security#august-05-2021)列出了稳定频道的安全更新。

## <a name="version-92090262-july-29"></a>版本 92.0.902.62：6 月 29 日

修复了各种 bug 和性能问题。

### <a name="modified-policy"></a>修改的策略

- AutoplayAllowed - 现在，设置为“已禁用”将媒体自动播放设置为“限制”

## <a name="version-92090255-july-22"></a>版本 92.0.902.55：7 月 22 日

[此处](/deployedge/microsoft-edge-relnotes-security#july-22-2021)列出了稳定频道的安全更新。

### <a name="feature-updates"></a>功能更新

**用户可以轻松地在 Microsoft Edge 上进入 Internet Explorer 模式**。 从 Microsoft Edge 版本 92 开始，用户可以在 Microsoft Edge 上以 Internet Explorer 模式重新加载站点，而不是等待站点在 Enterprise 模式站点列表中被配置的同时依赖独立 IE 11 应用程序。 系统将提示用户将网站添加到其本地站点列表，以便在 Microsoft Edge 中导航到的相同页面将在接下来 30 天内自动以 IE 模式呈现。 可以使用 [InternetExplorerIntegrationReloadInIEModeAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) 策略配置此体验，并允许访问 IE 模式入口点，以及允许将站点添加到本地站点列表。 可以使用 [InternetExplorerIntegrationLocalSiteListExpirationDays](/deployedge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) 策略调整将站点保留在本地站点列表中的天数。 请注意，对于端到端体验，Windows 10 版本 1909 需要 KB5003698 或更高版本; Windows 10 版本 2004、Windows 10 版本 20H2 或 Windows 10 版本 21H1 需要 KB5003690 或更高版本。 有关详细信息，请参阅 [ IE 模式下的本地站点列表](/deployedge/edge-ie-mode-local-site-list)。

**MHTML 文件将默认以 Internet Explorer 模式打开**。 从 Microsoft Edge 92 稳定版开始，MHTML 文件类型将在 Microsoft Edge 上以 Internet Explorer 模式自动打开，而不是在 Internet Explorer (IE11) 打开。 在用浏览器查看 Outlook 电子邮件时会经常遇到这种情况。 此更改仅在 IE11 是此文件类型的默认处理程序时发生。 如果想要更改此设置，可以在安装稳定版本 92 更新之前使用[此指南](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)。

**"禁用开发人员模式扩展"警告可以消除 2 周**。 从 Microsoft Edge 版本 92 开始，可以在警告对话框下拉列表中选择将"禁用开发人员模式扩展"警告暂停 2 周。

**直接从工具栏管理扩展**。 工具栏上新增的扩展菜单将允许你轻松隐藏/固定扩展。 管理扩展和查找新扩展的快速链接将使你轻松找到新扩展和管理现有扩展。

**自动播放的默认值将设置为限制**。  为了帮助你在上网时保持专注，从 Microsoft Edge 版本 92 开始，我们将自动播放媒体的默认设置从“允许”更改成了“限制”。

**付款工具现在可跨设备同步**。 从 Microsoft Edge 版本 92 开始，可以选择跨已登录设备同步付款信息。 请注意：这是限制性的功能推出。 如果看不到此功能，请在我们继续推出时再检查。
目前，此功能仅在美国可用，并且仅适用于 MSA 用户（而非 AAD）

**字体呈现的改进**。 改进了文本呈现，以提高清晰度并降低模糊度。 请注意：这是限制性的功能推出。 如果看不到此功能，请在我们继续推出时再检查。

**“收藏夹”和“集锦”等工具栏按钮功能将记住用户将其固定到窗口一侧的选择**。 现在默认启用，如果用户选择固定某个工具栏按钮，该按钮将始终以固定状态打开，直到他们决定取消固定。

**用户现在可以通过组策略管理“允许使用此配置文件对工作或学校网站进行单一登录”选项**。  “允许使用此配置文件对工作或学校网站进行单一登录”允许非 AAD 配置文件使用计算机上存在的工作或学校凭据对工作或学校网站使用单一登录。 此选项仅在“设置”->“个人资料”->“用户配置偏好设置”中作为切换项向非 AAD 配置文件的最终用户显示。  可以使用 [AADWebSiteSSOUsingThisProfileEnabled](/deployedge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) 策略配置该行为。  

**密码运行状况**。必须在不同帐户中使用较强且唯一的密码，以保持上网安全。 但是，这一点说起来容易，做起来难，并且大多数用户都表现出较差的密码习惯，如使用易于猜到的弱密码，或者在不同的帐户中重复使用相同的强密码。

在这一最新版本的 Microsoft Edge 中，使用较强且唯一的密码的任务将会变得稍微简单一些！ Microsoft Edge 现在将告知你保存的密码是否足够强，并指示是否已在多个站点中使用相应密码，从而有助于保持上网安全。 在 edge://settings/passwords 页面的已保存密码列表中，可以找到你的密码运行状况信息。
  
**提高了已保存密码的隐私程度**。如果你使用的是与他人共享的设备或出于任何原因而未在离开时锁定计算机，你现在可以选择使用设备密码进行第二次验证，以避免其他人获得你的网站密码。 就是这么简单！

**Outlook 扩展**。  随时了解 Microsoft Outlook 收件箱、日历、任务等，而无需打开新的浏览器窗口。  你可以在此处获取新的 Outlook 扩展：[Microsoft Outlook - Microsoft Edge 加载项](https://microsoftedge.microsoft.com/addons/detail/microsoft-outlook/kkpalkknhlklpbflpcpkepmmbnmfailf?hl=en-US)

**与 Chromium 开源项目保持一致，Microsoft Edge正在更新其在网页上呈现表的方式**。 此更改修复了已知问题，使Microsoft Edge更接近表在 Web/其他浏览器中呈现的指定方式。 建议在环境中测试重要工作流是否存在意外问题。 [here](https://docs.google.com/document/d/16PFD1GtMI9Zgwu0jtPaKZJ75Q2wyZ9EZnVbBacOfiNA/edit)提供完整的解释器。

### <a name="new-policies"></a>新策略

- [AADWebSiteSSOUsingThisProfileEnabled](/DeployEdge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled)：已启用使用此配置文件对工作或学校网站进行单一登录的功能
- [AutomaticHttpsDefault](/DeployEdge/microsoft-edge-policies#automatichttpsdefault)：配置自动 HTTPS
- [HeadlessModeEnabled](/DeployEdge/microsoft-edge-policies#headlessmodeenabled)：控制无头模式的使用
- [InsecurePrivateNetworkRequestsAllowed](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed)：指定是否允许不安全网站向专用性较强的网络端点提出请求
- [InsecurePrivateNetworkRequestsAllowedForUrls](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls)：允许列出的站点从不安全环境向专用性较强的网络端点提出请求
- [InternetExplorerIntegrationLocalSiteListExpirationDays](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) 指定站点在本地 IE 模式站点列表中保留的天数
- [InternetExplorerIntegrationReloadInIEModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) 允许以 Internet Explorer 模式重新加载未配置的网站
- [SharedArrayBufferUnrestrictedAccessAllowed](/DeployEdge/microsoft-edge-policies#sharedarraybufferunrestrictedaccessallowed)：指定是否可以在非跨源隔离环境中使用 SharedArrayBuffers

### <a name="deprecated-policy"></a>不推荐使用的策略

- [InternetExplorerIntegrationTestingAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationtestingallowed)：允许 Internet Explorer 模式测试

### <a name="obsoleted-policy"></a>已弃用策略

- [EnableSha1ForLocalAnchors](/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors)：当证书由本地信任锚点颁发时，允许使用 SHA-1 签名的证书

## <a name="version-91086471-july-19"></a>版本 91.0.864.71：7 月 19 日

> [!Important]
>此更新包含已由 Chromium 团队报告为具有在野利用的 [CVE-2021-30563](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30563)。 有关详细信息，请参阅[安全更新指南](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002)。

[此处](/deployedge/microsoft-edge-relnotes-security#july-19-2021)列出了稳定频道的安全更新。

## <a name="version-91086467-july-8"></a>版本 91.0.864.67：7 月 8 日

修复了各种 bug 和性能问题。

## <a name="version-91086464-july-2"></a>版本 91.0.864.64: 7 月 2 日

修复了各种 bug 和性能问题。

## <a name="version-91086459-june-24"></a>版本 91.0.864.59：6 月 24 日

[此处](/deployedge/microsoft-edge-relnotes-security#june-24-2021) 列出了稳定频道的安全更新。

## <a name="version-91086454-june-18"></a>版本 91.0.864.54：6 月 18 日

> [!Important]
> 此更新包含已由 Chromium 团队报告为具有在野利用的 [CVE-2021-30554](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30554)。 有关详细信息，请参阅 [安全更新指南](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002)。

[此处](/deployedge/microsoft-edge-relnotes-security#june-18-2021) 列出了稳定频道的安全更新。

## <a name="version-91086448-june-11"></a>版本 91.0.864.48：6 月 11 日

> [!Important]
>此更新包含已由 Chromium 团队报告为具有在野利用的 [CVE-2021-30551](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-30551)。 有关详细信息，请参阅 [安全更新指南](https://msrc.microsoft.com/update-guide/vulnerability/ADV200002)。

[此处](/deployedge/microsoft-edge-relnotes-security#june-11-2021) 列出了稳定频道的安全更新。

## <a name="version-91086441-june-3"></a>版本 91.0.864.41：6 月 3 日

[此处](/deployedge/microsoft-edge-relnotes-security#june-3-2021) 列出了稳定频道的安全更新。

## <a name="version-91086437-may-27"></a>版本 91.0.864.37：5 月 27 日

[此处](/deployedge/microsoft-edge-relnotes-security#may-27-2021) 列出了稳定频道的安全更新。

### <a name="feature-updates"></a>功能更新

- **标识源自代理级别的 Microsoft Defender 应用程序防护容器的网络流量**。 从 Microsoft Edge 版本 91 开始，内置了对源自应用程序防护容器的网络流量进行标记的支持，允许企业识别这些流量并应用特定策略。

- **支持允许将收藏夹从主机同步到边缘应用程序防护容器的选项**。 从 Microsoft Edge 版本 91 开始，用户可以选择配置应用程序防护以将其收藏夹从主机同步到容器。 这确保了容器上也可显示新的收藏夹。

- **从 Microsoft Edge 版本 91 开始，如果在未经用户交互的情况下启动对计算机有害的下载，并且 SmartScreen 应用程序信誉度检查不支持此下载，则浏览器将自动中断该类型的下载**。 用户可能会覆盖并继续下载，方法是右键单击并在下载项上选择“保留”。 企业管理员可能会通过配置以下策略选择退出此行为：
  - [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings.md) - 对域上的指定文件类型禁用基于下载文件类型扩展名的警告

    有关详细信息，请参阅 [Microsoft Edge 安全性下载中断](microsoft-edge-security-downloads-interruptions.md)。

- **支持语音识别 API。** 从 Microsoft Edge 版本 91 开始，将添加对 Google.com 和类似网站上语音识别命令的 API 支持。 此功能仅限于一组启用了实验的随机选择的用户。 这些用户向功能团队提供反馈。

- **使用新的主题颜色个性化设置浏览器**。 使用“设置”->“外观”页上的十四种新主题颜色之一打造你自己的 Microsoft Edge。 也可以从 Microsoft Edge 加载项网站安装自定义主题。 [了解详细信息](https://techcommunity.microsoft.com/t5/articles/make-microsoft-edge-your-own-with-themes/m-p/2083165)

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

添加了六条新的策略。 从 [Microsoft Edge 企业版登录页面](https://www.microsoft.com/edge/business/download) 下载更新的管理模板。 添加了以下新策略：

- [ApplicationGuardTrafficIdentificationEnabled](/DeployEdge/microsoft-edge-policies#applicationguardtrafficidentificationenabled) - 应用程序防护流量标识
- [ExplicitlyAllowedNetworkPorts](/DeployEdge/microsoft-edge-policies#explicitlyallowednetworkports) - 显式允许的网络端口
- [ImportStartupPageSettings](/DeployEdge/microsoft-edge-policies#importstartuppagesettings) - 允许导入启动页设置
- [MathSolverEnabled](/DeployEdge/microsoft-edge-policies#mathsolverenabled) - 允许用户截取数学问题，并通过 Microsoft Edge 中的分步说明获取解决方案
- [NewTabPageContentEnabled](/DeployEdge/microsoft-edge-policies#newtabpagecontentenabled) - 允许新选项卡页上的 Microsoft 新闻内容
- [NewTabPageQuickLinksEnabled](/DeployEdge/microsoft-edge-policies#newtabpagequicklinksenabled) - 允许新选项卡页上的快速链接

#### <a name="obsoleted-policy"></a>已过时的策略

- [ProactiveAuthEnabled](./microsoft-edge-policies.md#proactiveauthenabled) - 启用主动身份验证。
<!-- end major 91 -->

## <a name="version-90081866-may-20"></a>版本 90.0.818.66：5 月 20 日

修复了各种 bug 和性能问题。

## <a name="version-90081862-may-13"></a>版本 90.0.818.62：5 月 13 日

[此处](/deployedge/microsoft-edge-relnotes-security#may-13-2021) 列出了稳定频道的安全更新。

## <a name="version-90081856-may-6"></a>版本 90.0.818.56：5 月 6 日

修复了各种 bug 和性能问题。

## <a name="version-90081851-april-29"></a>版本 90.0.818.51：4 月 29 日

[此处](/deployedge/microsoft-edge-relnotes-security#april-29-2021) 列出了稳定频道的安全更新。

## <a name="version-90081849-april-26"></a>版本 90.0.818.49：4 月 26 日

修复了各种 bug 和性能问题。

## <a name="version-90081846-april-22"></a>版本 90.0.818.46：4 月 22 日 ##

[此处](/deployedge/microsoft-edge-relnotes-security#april-22-2021) 列出了稳定频道的安全更新。

## <a name="version-90081842-april-19"></a>版本 90.0.818.42：4 月 19 日

修复了各种 bug 和性能问题。

## <a name="version-90081841-april-16"></a>版本 90.0.818.41：4 月 16 日 ##

> [!Important]
>此更新包含已由 Chromium 团队报告为具有在野利用的 [CVE-2021-21224](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21224)。 有关详细信息，请参阅 [安全更新指南](https://msrc.microsoft.com/update-guide)。

[此处](/deployedge/microsoft-edge-relnotes-security#april-16-2021) 列出了稳定频道的安全更新。

## <a name="version-90081839-april-15"></a>版本 90.0.818.39：4 月 15 日 ##

[此处](/deployedge/microsoft-edge-relnotes-security#april-15-2021) 列出了稳定频道的安全更新。

## <a name="feature-updates"></a>功能更新 ##

-    **单一登录 (SSO) 现已适用于 macOS 上的 Azure Active Directory (Azure AD) 帐户和 Microsoft 帐户 (MSA)。** 现在，已在 macOS 上登录 Microsoft Edge 的用户将自动登录到配置为允许使用工作帐户和 Microsoft 帐户进行单一登录的网站（如 bing.com、office.com、msn.com 和 outlook.com）。

- **展台模式。** 从 Microsoft Edge 版本 90 开始，我们已锁定 UI 打印设置，以仅允许配置的打印机和“打印到 PDF”选项。 我们还在分配的访问权限单应用展台模式中进行了改进，以限制从浏览器启动其他应用程序。 有关展台模式功能的详细信息，请转到 [此处](/deployedge/microsoft-edge-configure-kiosk-mode#kiosk-mode-supported-features)。

- **中断下载** 从 Microsoft Edge 版本 91 开始，如果在未经用户交互的情况下启动对计算机有害的下载，并且 SmartScreen 应用程序信誉检查不支持此下载，则浏览器将自动中断该类型的下载。 用户可能会覆盖并继续下载，方法是右键单击并在下载项上选择“保留”。
企业管理员可以通过以下两个策略之一选择退出此行为：
- [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - 对域上的指定文件类型禁用基于文件类型扩展名的下载警告。有关详细信息，请参阅 [Microsoft Edge 安全下载中断](/deployedge/microsoft-edge-security-downloads-interruptions)

- **打印：**

    - **非 PostScript 打印机的全新打印光栅化模式。** 从 Microsoft Edge 版本 90 开始，管理员可以使用新策略为用户定义打印光栅化模式。 此策略控制 Microsoft Edge 如何在 Windows 上打印到非 PostScript 打印机。 有时，在非 PostScript 打印机上的打印作业需要进行光栅化才能正确打印。 打印选项为“完整”和“快速”。
    
  - **打印的其他页面缩放选项。** 用户现在可在使用其他选项打印网页和 PDF 文档时自定义缩放。 “适应页面”选项可确保网页或文档适合所选“纸张大小”中可用于打印的空间。 “实际大小”选项可确保无论所选“纸张大小”如何，正在打印内容的大小都没有任何变化。

-   **工作效率：**

    -   **自动填充建议扩展为包含剪贴板中的地址字段内容。** 在单击配置文件/地址字段（例如，电话、电子邮件、邮政编码、城市、省/市/县等）将分析剪贴板内容，以显示为自动填充建议。

    -   **即使未检测到表单或字段，用户也可以搜索自动填充建议。** 现在，如果将信息保存在 Microsoft Edge 上，将自动弹出自动填充建议，并帮助你在填写表单时节省时间。 如果自动填充遗漏了表单，或者你希望获取通常不会自动填充的表单（如临时表单）中的数据，可以使用自动填充来搜索信息。

-   **从菜单栏中的浮出控件访问下载。** 下载将显示在右上角，且所有活动下载都位于同一位置。 此菜单很容易消除，以便用户可以继续不间断地浏览，并且可以从工具栏直接监视总体下载进度。 [了解详细信息](https://techcommunity.microsoft.com/t5/articles/introducing-the-new-downloads-experience/m-p/2111551)。

-   **字体呈现的改进。** 从 Microsoft Edge 版本 90 开始，我们改进了文本呈现，以提高清晰度并减少模糊度。 字体呈现改进的一部分将在 Beta 版本 90 中落地，但默认情况下处于禁用状态。

- **儿童模式。** 我们已更新策略，以便在启用策略时，除了家庭安全之外，还将禁用儿童模式功能。 请在 [此处](https://go.microsoft.com/fwlink/?linkid=2146910) 了解儿童模式的详细信息

## <a name="policy-updates"></a>策略更新

## <a name="new-policies"></a>新策略

添加了 8 个新策略。 从 [Microsoft Edge 企业版登录页面](https://www.microsoft.com/edge/business/download) 下载更新的管理模板。 添加了以下新策略：
-   [ApplicationGuardFavoritesSyncEnabled](/DeployEdge/microsoft-edge-policies#applicationguardfavoritessyncenabled) - 已启用应用程序防护收藏夹同步
- [ApplicationGuardTrafficIdentificationEnabled](/DeployEdge/microsoft-edge-policies#applicationguardtrafficidentificationenabled) 应用程序防护流量标识
- [ExplicitlyAllowedNetworkPorts](/DeployEdge/microsoft-edge-policies#explicitlyallowednetworkports) 显式允许的网络端口
- [ImportStartupPageSettings](/DeployEdge/microsoft-edge-policies#importstartuppagesettings) 允许导入启动页设置
- [MathSolverEnabled](/DeployEdge/microsoft-edge-policies#mathsolverenabled) 让用户截取数学问题，并在 Microsoft Edge 中通过分步说明获取解决方案
- [NewTabPageContentEnabled](/DeployEdge/microsoft-edge-policies#newtabpagecontentenabled) 允许新选项卡页上的 Microsoft 新闻内容
- [NewTabPageQuickLinksEnabled](/DeployEdge/microsoft-edge-policies#newtabpagequicklinksenabled) 允许新选项卡页上的快速链接
-   [FetchKeepaliveDurationSecondsOnShutdown](/DeployEdge/microsoft-edge-policies#fetchkeepalivedurationsecondsonshutdown)- 在关闭时提取 keepalive 持续时间
-   [ManagedConfigurationPerOrigin](/DeployEdge/microsoft-edge-policies#managedconfigurationperorigin) - 将网站的托管配置值设置到特定源
-   [PrintRasterizationMode](/DeployEdge/microsoft-edge-policies#printrasterizationmode) - 打印光栅化模式
-   [QuickViewOfficeFilesEnabled](/DeployEdge/microsoft-edge-policies#quickviewofficefilesenabled) - 在 Microsoft Edge 中管理 QuickView Office 文件功能
-   [SSLErrorOverrideAllowedForOrigins](/DeployEdge/microsoft-edge-policies#sslerroroverrideallowedfororigins) - 允许用户从特定源的 HTTPS 警告页面继续操作
-   [WindowOcclusionEnabled](/DeployEdge/microsoft-edge-policies#windowocclusionenabled) - 启用窗口封闭
-   [WindowsHelloForHTTPAuthEnabled](/DeployEdge/microsoft-edge-policies#windowshelloforhttpauthenabled) - 已启用 Windows Hello HTTP 身份验证

## <a name="deprecated-policies"></a>弃用的策略

- [ProactiveAuthEnabled](/DeployEdge/microsoft-edge-policies#proactiveauthenabled) 启用主动身份验证。
-   [NativeWindowOcclusionEnabled](/DeployEdge/microsoft-edge-policies#nativewindowocclusionenabled) - 启用本机窗口封闭
-   [SSLVersionMin](/DeployEdge/microsoft-edge-policies#sslversionmin)- 已启用最低 TLS 版本

## <a name="version-89077477-april-14"></a>版本 89.0.774.77：4 月 14 日

> [!Important]
>此更新包含已由 Chromium 团队报告为具有在野利用的 [CVE-2021-21206](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21206) 和 [CVE-2021-21220](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21220)。  有关详细信息，请参阅 [安全更新指南](https://msrc.microsoft.com/update-guide)。

[此处](/deployedge/microsoft-edge-relnotes-security#april-14-2021) 列出了稳定频道的安全更新。

## <a name="version-89077476-april-12"></a>版本 89.0.774.76：4 月 12 日

修复了各种 bug 和性能问题。

## <a name="version-89077475-april-8"></a>版本 89.0.774.75：4 月 8 日

修复了各种 bug 和性能问题。

## <a name="version-89077468-april-1"></a>版本 89.0.774.68：4 月 1 日

[此处](./microsoft-edge-relnotes-security.md#april-1-2021)列出了稳定频道的安全更新。

## <a name="version-89077463-march-25"></a>版本 89.0.774.63：3 月 25 日

修复了各种 bug 和性能问题。

## <a name="version-89077457-march-18"></a>版本 89.0.774.57：3 月 18 日

修复了各种 bug 和性能问题。

## <a name="version-89077454-march-13"></a>版本 89.0.774.54：3 月 13 日

> [!IMPORTANT]
> 此更新包含已由 Chromium 团队报告用于现实中的 [CVE-2021-21193](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21193)。 有关详细信息，请参阅 [安全更新指南](https://msrc.microsoft.com/update-guide)。

[此处](./microsoft-edge-relnotes-security.md#march-13-2021)列出了稳定频道的安全更新。

## <a name="version-89077450-march-10"></a>版本 89.0.774.50：3 月 10 日

修复了各种错误和性能问题。

## <a name="version-89077448-march-8"></a>版本 89.0.774.48：3 月 8 日

修复了各种错误和性能问题。

<!-- begin major 89 -->
## <a name="version-89077445-march-4"></a>版本 89.0.774.45：3 月 4 日

> [!IMPORTANT]
> 此更新包含 [CVE-2021-21166](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-21166)Chromium团队报告该更新现实中已被利用。 有关详细信息，请参阅 [安全更新指南](https://msrc.microsoft.com/update-guide)。

[此处](./microsoft-edge-relnotes-security.md#march-4-2021)列出了稳定频道的安全更新。

### <a name="resolved-issues"></a>已解决的问题

- **任务栏和"开始"菜单的快捷方式更新和修复：**
  - 右键单击"开始"菜单中的 Microsoft Edge 快捷方式现可正确显示固定时从任务栏中取消固定 Microsoft Edge 的选项。
  - 为了将 Microsoft Edge 固定到任务栏启动包括 [任务栏配置](/windows/configuration/configure-windows-10-taskbar) 时，这不再导致第二个 Microsoft Edge 快捷方式固定到任务栏。
  - 如果用户登录到 Windows，则使用 Windows 漫游配置文件的组织将不再看到任务栏上的空白白色图标代替Microsoft Edge图标。

### <a name="feature-updates"></a>功能更新

- **展台模式支持其他锁定功能**。 从 Microsoft Edge 版本 89 开始，我们在展台模式下添加了其他锁定功能，使客户能够在高效和更安全的体验中完成工作。 [了解详细信息](microsoft-edge-configure-kiosk-mode.md#kiosk-mode-supported-features)。

- **Enterprise Mode Site List Manager 工具将在浏览器中通过 *edge://compat* 页提供**。 可以使用此工具在 Microsoft Edge 上为 Internet Explorer 模式创建、编辑和导出站点列表 XML。 可以根据需要通过组策略启用对此工具的访问。 [了解详情](./edge-ie-mode-site-list-manager.md)。

- **使用休眠选项卡提高浏览器性能**。 休眠选项卡通过将非活动选项卡置于睡眠状态以释放系统资源（如内存和 CPU）来提升浏览器性能，以便活动选项卡或其他应用程序可以使用它们。 用户可以阻止网站进入睡眠状态，并配置非活动选项卡进入睡眠状态之前的时间长度。 若要使用户保持其流，还有一些[启发性方法](https://techcommunity.microsoft.com/t5/articles/sleeping-tabs-faq/m-p/1705434)可阻止某些网站进入睡眠状态，例如 Intranet 网站。 可以使用组策略管理此功能。

- **手动重置云中的 Microsoft Edge 同步数据**。 我们正在引入一种从产品内重置 Microsoft Edge 同步数据的方法。 这确保从 Microsoft 服务中清除数据，同时也解决了以前需要支持票证的某些产品问题。

- **针对具有单个非 Azure AD Microsoft Edge 配置文件的用户的所有 Windows Azure Active Directory (Azure AD) 帐户智能启用单一登录 (SSO)**。  为从此功能受益最大的用户自动启用该设置。 如果用户只有一个 Microsoft Edge 配置文件（不是 Azure AD 或儿童模式），则当 Microsoft Edge 启动时，该设置将自动启用。 如果用户稍后选择使用 Azure AD 帐户登录其他 Microsoft Edge 配置文件，此自动切换功能也将自动关闭。 用户可以依次选择“**设置”>“配置文件”>“配置文件首选项”>“允许使用此配置文件对工作或学校网站进行单一登录**”手动更新此功能的首选项。

- **PDF 文档中文本选择体验的改善**。 从版本 89 开始，用户将开始在 Microsoft Edge 中打开的 PDF 文档中获得更流畅、一致的文本选择体验。

- **自动填充字段现在支持"出生日期"**。 现在，Microsoft Edge 通过自动填充地址、姓名、电话号码等数据，帮助你在线填写表单和创建帐户时节省时间和精力。从 Microsoft Edge 版本 89 开始，我们将添加对另一可保存及自动填充字段的支持—出生日期。 可以随时在个人资料设置中查看、编辑和删除此信息。

### <a name="policy-updates"></a>策略更新

#### <a name="new-policies"></a>新策略

添加了 7 个新策略。 从 [Microsoft Edge 企业登录页面](https://www.microsoft.com/edge/business/download)下载更新的管理模板。 已添加以下新策略。

- [BrowsingDataLifetime](./microsoft-edge-policies.md#browsingdatalifetime) - 浏览数据生存期设置
- [MAMEnabled](./microsoft-edge-policies.md#mamenabled) - 移动应用管理已启用
- [DefinePreferredLanguages](./microsoft-edge-policies.md#definepreferredlanguages) - 定义网站应在网站支持该语言时显示的首选语言的有序列表
- [ShowRecommendationsEnabled](./microsoft-edge-policies.md#showrecommendationsenabled) - 允许来自 Edge 的建议和促销通知
- [PrintingAllowedBackgroundGraphicsModes](./microsoft-edge-policies.md#printingallowedbackgroundgraphicsmodes) - 限制背景图形打印模式
- [PrintingBackgroundGraphicsDefault](./microsoft-edge-policies.md#printingbackgroundgraphicsdefault)- 默认背景图形打印模式
- [SmartActionsBlockList](./microsoft-edge-policies.md#smartactionsblocklist)- 阻止对服务列表执行智能操作

#### <a name="obsoleted-policies"></a>已过时的策略

以下策略已过时。

- [ForceLegacyDefaultReferrerPolicy](./microsoft-edge-policies.md#forcelegacydefaultreferrerpolicy) - 使用 no-referrer-when-downgrade 的默认引荐策略
- [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled)：启用使用情况和故障相关数据报告
- [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices)：发送站点信息以改进 Microsoft 服务
<!-- end major 89 -->

<!-- Archive from 86.0.622.43: October 15 to beta 88.0.705.81: February 25  ->
<!-- Archive from 86.0.622.38-october-9 to beta 86.0.62.215-september-14  ->
<!-- Archived to version 84.0.522.40: July 16 -->

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
