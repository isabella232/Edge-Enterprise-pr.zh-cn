---
title: Microsoft Edge Beta 渠道发行说明
ms.author: aguta
author: AndreaLBarr
manager: srugh
ms.date: 06/25/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Beta 渠道发行说明
ms.openlocfilehash: a4ef80420bfa87bf5fcfa154937ebe52b7cb375f
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617932"
---
# <a name="release-notes-for-microsoft-edge-beta-channel"></a><span data-ttu-id="d7d9b-103">Microsoft Edge Beta 渠道的发行说明</span><span class="sxs-lookup"><span data-stu-id="d7d9b-103">Release notes for Microsoft Edge Beta Channel</span></span>

<span data-ttu-id="d7d9b-104">本发行说明提供有关 Microsoft Edge Beta 渠道中包含的新功能和非安全更新的信息。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-104">These release notes provide information about new features and non-security updates that are included in the Microsoft Edge Beta Channel.</span></span> <span data-ttu-id="d7d9b-105">[此处](microsoft-edge-relnote-archive-beta-channel.md)提供了这些发行说明的存档版本。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-105">Archived versions of these release notes are available [here](microsoft-edge-relnote-archive-beta-channel.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d7d9b-106">Microsoft Edge Web 平台不断发展以改进用户体验、安全性和隐私。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-106">Microsoft Edge Web Platform constantly evolves to improve user experience, security, and privacy.</span></span> <span data-ttu-id="d7d9b-107">要了解详细信息，请参阅 [Microsoft Edge 即将带来的影响网站兼容性的更改](/microsoft-edge/web-platform/site-impacting-changes)。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-107">To learn more, see [Site compatibility-impacting changes coming to Microsoft Edge](/microsoft-edge/web-platform/site-impacting-changes).</span></span>

## <a name="version-92090222-june-21"></a><span data-ttu-id="d7d9b-108">版本 92.0.902.22：6 月 21 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-108">Version 92.0.902.22: June 21</span></span>

### <a name="feature-updates"></a><span data-ttu-id="d7d9b-109">功能更新</span><span class="sxs-lookup"><span data-stu-id="d7d9b-109">Feature updates</span></span>

- <span data-ttu-id="d7d9b-110">**用户可以轻松地在 Microsoft Edge 上进入 Internet Explorer 模式**。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-110">**Users can easily get to Internet Explorer mode on Microsoft Edge**.</span></span> <span data-ttu-id="d7d9b-111">从 Microsoft Edge 版本 92 开始，用户可以在 Microsoft Edge 上以 Internet Explorer 模式重新加载站点，而不是等待站点在 Enterprise 模式站点列表中被配置的同时依赖独立 IE 11 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-111">Starting with Microsoft Edge version 92, users can reload a site in Internet Explorer mode on Microsoft Edge instead of relying on the standalone IE 11 application while waiting for a site to be configured in the Enterprise Mode Site List.</span></span> <span data-ttu-id="d7d9b-112">系统将提示用户将网站添加到其本地站点列表，以便在 Microsoft Edge 中导航到的相同页面将在接下来 30 天内自动以 IE 模式呈现。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-112">Users will be prompted to add the site to their local site list such that navigating to the same page in Microsoft Edge will automatically render in IE mode for the next 30 days.</span></span> <span data-ttu-id="d7d9b-113">可以使用 *[InternetExplorerIntegrationReloadInIEModeAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed)* 策略配置此体验，并允许访问 IE 模式入口点，以及允许将站点添加到本地站点列表。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-113">You can use the *[InternetExplorerIntegrationReloadInIEModeAllowed](/deployedge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed)* policy to configure this experience and allow access to the IE mode entry points as well as the ability to add sites to the local site list.</span></span> <span data-ttu-id="d7d9b-114">可以使用 *[InternetExplorerIntegrationLocalSiteListExpirationDays](/deployedge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays)* 策略调整将网站保留在本地站点列表中的天数。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-114">You can use the *[InternetExplorerIntegrationLocalSiteListExpirationDays](/deployedge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays)* policy to adjust the number of days to keep sites on the local site list.</span></span>
<span data-ttu-id="d7d9b-115">请注意，对于端到端体验，Windows 10 版本 1909 需要 KB5003698 或更高版本; Windows 10 版本 2004、Windows 10 版本 20H2 或 Windows 10 版本 21H1 需要 KB5003690 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-115">Note that KB5003698 or later is required for Windows 10, version 1909; or KB5003690 or later is required for Windows 10, version 2004, Windows 10, version 20H2, or Windows 10, version 21H1 for the end-to-end experience.</span></span>

- <span data-ttu-id="d7d9b-116">**MHTML 文件将默认以 Internet Explorer 模式打开**。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-116">**MHTML files will default to opening in Internet Explorer mode**.</span></span> <span data-ttu-id="d7d9b-117">从 Microsoft Edge 92 稳定版开始，MHTML 文件类型将在 Microsoft Edge 上以 Internet Explorer 模式自动打开，而不是在 Internet Explorer (IE11) 打开。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-117">Starting in Microsoft Edge version 92 Stable, MHTML file types will automatically open in Internet Explorer mode on Microsoft Edge instead of the Internet Explorer (IE11) application.</span></span> <span data-ttu-id="d7d9b-118">在用浏览器查看 Outlook 电子邮件时会经常遇到这种情况。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-118">This is most commonly observed while trying to view Outlook emails in a browser.</span></span> <span data-ttu-id="d7d9b-119">此更改仅在 IE11 是此文件类型的默认处理程序时发生。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-119">This change will occur only if IE11 is the default handler for this file type.</span></span> <span data-ttu-id="d7d9b-120">如果想要更改此设置，可以在安装稳定版本 92 更新之前使用 [本指南](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-120">If you'd prefer to change this, you can do so prior to installing the Stable version 92 update using [this guidance](/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration).</span></span>

- <span data-ttu-id="d7d9b-121">**付款工具现在跨设备同步**。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-121">**Payment instruments are now synced across devices**.</span></span> <span data-ttu-id="d7d9b-122">从 Microsoft Edge 版本 92 开始，可以选择跨已登录设备同步付款信息。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-122">Beginning with Microsoft Edge version 92, you have the option to synchronize your payment information across your signed in devices.</span></span>
<span data-ttu-id="d7d9b-123">请注意：这是受控功能推出，目前推出率为 50%。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-123">Please note: this is a Controlled Feature Rollout and we are currently at 50%.</span></span> <span data-ttu-id="d7d9b-124">如果看不到此功能，请在我们继续推出时再检查。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-124">If you don’t see this feature, please check back shortly as we continue our rollout.</span></span>

- <span data-ttu-id="d7d9b-125">**"禁用开发人员模式扩展"警告可以永久消除**。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-125">**"Disable developer mode extensions" warning can be permanently dismissed**.</span></span> <span data-ttu-id="d7d9b-126">从 Microsoft Edge 版本 92 开始，可以通过单击"不要再次显示此扩展"选项来关闭"禁用开发人员模式扩展"警告。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-126">Beginning with Microsoft Edge version 92, you can turn off the warning "Disable developer mode extensions" by clicking on the 'Don't show this again' option.</span></span>
<span data-ttu-id="d7d9b-127">请注意：这是受控功能推出，目前推出率为 25%。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-127">Please note: this is a Controlled Feature Rollout and we are currently at 25%.</span></span> <span data-ttu-id="d7d9b-128">如果看不到此功能，请在我们继续推出时再检查。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-128">If you don’t see this feature, please check back shortly as we continue our rollout.</span></span>

- <span data-ttu-id="d7d9b-129">**从工具栏管理扩展**。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-129">**Manage your extensions right from the toolbar**.</span></span> <span data-ttu-id="d7d9b-130">工具栏上新增的扩展菜单将允许你轻松隐藏/固定扩展。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-130">The all-new extensions menu on the toolbar will allow you to hide/pin extensions easily.</span></span> <span data-ttu-id="d7d9b-131">管理扩展和查找新扩展的快速链接将使你轻松找到新扩展和管理现有扩展。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-131">The quick links to manage extensions and find new extensions will make it easy for you to find new extensions and manage your existing ones.</span></span>
<span data-ttu-id="d7d9b-132">请注意：这是受控功能推出，目前推出率为 25%。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-132">Please note: this is a Controlled Feature Rollout and we are currently at 25%.</span></span> <span data-ttu-id="d7d9b-133">如果看不到此功能，请在我们继续推出时再检查。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-133">If you don’t see this feature, please check back shortly as we continue our rollout.</span></span>

- <span data-ttu-id="d7d9b-134">**自动 HTTPS**。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-134">**Automatic HTTPS**.</span></span> <span data-ttu-id="d7d9b-135">用户可以选择在可能支持此更安全协议的域上将导航从 HTTP 升级到 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-135">Users will have the option to upgrade navigation from HTTP to HTTPS on domains likely to support this more secure protocol.</span></span> <span data-ttu-id="d7d9b-136">此支持还可以配置为在所有域上尝试 HTTPS 传输。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-136">This support can also be configured to attempt delivery over HTTPS for all domains.</span></span>
<span data-ttu-id="d7d9b-137">请注意：我们正在试验此功能，如果你已选择退出实验，则将不会看到此行为。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-137">Please note: we are experimenting with this feature and this behavior won’t be seen if you have opted out of experiments.</span></span>

- <span data-ttu-id="d7d9b-138">**字体呈现的改进**。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-138">**Improvements to font rendering**.</span></span> <span data-ttu-id="d7d9b-139">改进了文本呈现，以提高清晰度并降低模糊度。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-139">Improvements have been made to the rendering of text to improve clarity and reduce blurriness.</span></span>
<span data-ttu-id="d7d9b-140">请注意：这是受控功能推出，目前推出率为 25%。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-140">Please note: this is a Controlled Feature Rollout and we are currently at 25%.</span></span> <span data-ttu-id="d7d9b-141">如果看不到此功能，请在我们继续推出时再检查。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-141">If you don’t see this feature, please check back shortly as we continue our rollout.</span></span>

### <a name="policy-updates"></a><span data-ttu-id="d7d9b-142">策略更新</span><span class="sxs-lookup"><span data-stu-id="d7d9b-142">Policy updates</span></span>

#### <a name="new-policies"></a><span data-ttu-id="d7d9b-143">新策略</span><span class="sxs-lookup"><span data-stu-id="d7d9b-143">New policies</span></span>

<span data-ttu-id="d7d9b-144">添加了 8 个新策略。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-144">Eight new policies were added.</span></span> <span data-ttu-id="d7d9b-145">从 [Microsoft Edge 企业版登录页面](https://www.microsoft.com/edge/business/download) 下载更新的管理模板。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-145">Download the updated Administrative Templates from the [Microsoft Edge Enterprise landing page](https://www.microsoft.com/edge/business/download).</span></span> <span data-ttu-id="d7d9b-146">添加了以下新策略：</span><span class="sxs-lookup"><span data-stu-id="d7d9b-146">The following new policies were added:</span></span>

- <span data-ttu-id="d7d9b-147">[AADWebSiteSSOUsingThisProfileEnabled](/DeployEdge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) 启用通过此配置文件对工作或学校网站进行单一登录。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-147">[AADWebSiteSSOUsingThisProfileEnabled](/DeployEdge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) Single sign-on for work or school sites using this profile enabled.</span></span>
- <span data-ttu-id="d7d9b-148">[AutomaticHttpsDefault](/DeployEdge/microsoft-edge-policies#automatichttpsdefault) 配置自动 HTTPS</span><span class="sxs-lookup"><span data-stu-id="d7d9b-148">[AutomaticHttpsDefault](/DeployEdge/microsoft-edge-policies#automatichttpsdefault) Configure Automatic HTTPS</span></span>
- <span data-ttu-id="d7d9b-149">[HeadlessModeEnabled](/DeployEdge/microsoft-edge-policies#headlessmodeenabled) 控制无头模式的使用</span><span class="sxs-lookup"><span data-stu-id="d7d9b-149">[HeadlessModeEnabled](/DeployEdge/microsoft-edge-policies#headlessmodeenabled) Control use of the Headless Mode</span></span>
- <span data-ttu-id="d7d9b-150">[InsecurePrivateNetworkRequestsAllowed](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed)指定是否允许不安全网站向更专用的网络终结点提出请求</span><span class="sxs-lookup"><span data-stu-id="d7d9b-150">[InsecurePrivateNetworkRequestsAllowed](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed)Specifies whether to allow insecure websites to make requests to more-private network endpoints</span></span>
- <span data-ttu-id="d7d9b-151">[InsecurePrivateNetworkRequestsAllowedForUrls](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls) 允许列出的站点从不安全环境向更专用的网络终结点提出请求</span><span class="sxs-lookup"><span data-stu-id="d7d9b-151">[InsecurePrivateNetworkRequestsAllowedForUrls](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls) Allow the listed sites to make requests to more-private network endpoints from insecure contexts</span></span>
- <span data-ttu-id="d7d9b-152">[InternetExplorerIntegrationLocalSiteListExpirationDays](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) 指定站点在本地 IE 模式站点列表中保留的天数</span><span class="sxs-lookup"><span data-stu-id="d7d9b-152">[InternetExplorerIntegrationLocalSiteListExpirationDays](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) Specify the number of days that a site remains on the local IE mode site list</span></span>
- <span data-ttu-id="d7d9b-153">[InternetExplorerIntegrationReloadInIEModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) 允许以 Internet Explorer 模式重新加载未配置的网站</span><span class="sxs-lookup"><span data-stu-id="d7d9b-153">[InternetExplorerIntegrationReloadInIEModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) Allow unconfigured sites to be reloaded in Internet Explorer mode</span></span>
- <span data-ttu-id="d7d9b-154">[SharedArrayBufferUnrestrictedAccessAllowed](/DeployEdge/microsoft-edge-policies#sharedarraybufferunrestrictedaccessallowed) 指定是否可以在非跨源隔离环境中使用 SharedArrayBuffers</span><span class="sxs-lookup"><span data-stu-id="d7d9b-154">[SharedArrayBufferUnrestrictedAccessAllowed](/DeployEdge/microsoft-edge-policies#sharedarraybufferunrestrictedaccessallowed) Specifies whether SharedArrayBuffers can be used in a non cross-origin-isolated context</span></span>

#### <a name="obsoleted-policy"></a><span data-ttu-id="d7d9b-155">已过时的策略</span><span class="sxs-lookup"><span data-stu-id="d7d9b-155">Obsoleted Policy</span></span>

- <span data-ttu-id="d7d9b-156">[EnableSha1ForLocalAnchors](/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors) 允许使用本地信任锚点颁发的 SHA-1 签名的证书。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-156">[EnableSha1ForLocalAnchors](/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors) Allow certificates signed using SHA-1 when issued by local trust anchors.</span></span>
- <span data-ttu-id="d7d9b-157">[AADWebSiteSSOUsingThisProfileEnabled](/DeployEdge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) 启用通过此配置文件对工作或学校网站进行单一登录。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-157">[AADWebSiteSSOUsingThisProfileEnabled](/DeployEdge/microsoft-edge-policies#aadwebsitessousingthisprofileenabled) Single sign-on for work or school sites using this profile enabled.</span></span>
- <span data-ttu-id="d7d9b-158">[AutomaticHttpsDefault](/DeployEdge/microsoft-edge-policies#automatichttpsdefault) 配置自动 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-158">[AutomaticHttpsDefault](/DeployEdge/microsoft-edge-policies#automatichttpsdefault) Configure Automatic HTTPS.</span></span>
- <span data-ttu-id="d7d9b-159">[HeadlessModeEnabled](/DeployEdge/microsoft-edge-policies#headlessmodeenabled) 控制无头模式的使用。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-159">[HeadlessModeEnabled](/DeployEdge/microsoft-edge-policies#headlessmodeenabled) Control use of the Headless Mode.</span></span>
- <span data-ttu-id="d7d9b-160">[InsecurePrivateNetworkRequestsAllowed](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed) 指定是否允许不安全网站向更专用的网络终结点提出请求。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-160">[InsecurePrivateNetworkRequestsAllowed](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowed) Specifies whether to allow insecure websites to make requests to more-private network endpoints.</span></span>
- <span data-ttu-id="d7d9b-161">[InsecurePrivateNetworkRequestsAllowedForUrls](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls) 允许列出的站点从不安全环境向更专用的网络终结点提出请求。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-161">[InsecurePrivateNetworkRequestsAllowedForUrls](/DeployEdge/microsoft-edge-policies#insecureprivatenetworkrequestsallowedforurls) Allow the listed sites to make requests to more-private network endpoints from insecure contexts.</span></span>
- <span data-ttu-id="d7d9b-162">[InternetExplorerIntegrationLocalSiteListExpirationDays](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) 指定站点在本地 IE 模式站点列表中保留的天数。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-162">[InternetExplorerIntegrationLocalSiteListExpirationDays](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationlocalsitelistexpirationdays) Specify the number of days that a site remains on the local IE mode site list.</span></span>
- <span data-ttu-id="d7d9b-163">[InternetExplorerIntegrationReloadInIEModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) 允许以 Internet Explorer 模式重新加载未配置的网站。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-163">[InternetExplorerIntegrationReloadInIEModeAllowed](/DeployEdge/microsoft-edge-policies#internetexplorerintegrationreloadiniemodeallowed) Allow unconfigured sites to be reloaded in Internet Explorer mode.</span></span>
- <span data-ttu-id="d7d9b-164">[SharedArrayBufferUnrestrictedAccessAllowed](/DeployEdge/microsoft-edge-policies#sharedarraybufferunrestrictedaccessallowed) 指定是否可以在非跨源隔离环境中使用 SharedArrayBuffers。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-164">[SharedArrayBufferUnrestrictedAccessAllowed](/DeployEdge/microsoft-edge-policies#sharedarraybufferunrestrictedaccessallowed) Specifies whether SharedArrayBuffers can be used in a non cross-origin-isolated context.</span></span>

#### <a name="obsoleted-policy"></a><span data-ttu-id="d7d9b-165">已过时的策略</span><span class="sxs-lookup"><span data-stu-id="d7d9b-165">Obsoleted Policy</span></span>

- <span data-ttu-id="d7d9b-166">[EnableSha1ForLocalAnchors](/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors) 允许使用本地信任锚点颁发的 SHA-1 签名的证书。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-166">[EnableSha1ForLocalAnchors](/DeployEdge/microsoft-edge-policies#enablesha1forlocalanchors) Allow certificates signed using SHA-1 when issued by local trust anchors.</span></span>

## <a name="version-9209029-june-8"></a><span data-ttu-id="d7d9b-167">版本 92.0.902.9：6 月 8 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-167">Version 92.0.902.9: June 8</span></span>

<span data-ttu-id="d7d9b-168">修复了各种 bug 和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-168">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086441-june-3"></a><span data-ttu-id="d7d9b-169">版本 91.0.864.41：6 月 3 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-169">Version 91.0.864.41: June 3</span></span>

<span data-ttu-id="d7d9b-170">修复了各种 bug 和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-170">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086437-may-27"></a><span data-ttu-id="d7d9b-171">版本 91.0.864.37：5 月 27 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-171">Version 91.0.864.37: May 27</span></span>

<span data-ttu-id="d7d9b-172">修复了各种 bug 和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-172">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086436-may-26"></a><span data-ttu-id="d7d9b-173">版本 91.0.864.36：5 月 26 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-173">Version 91.0.864.36: May 26</span></span>

<span data-ttu-id="d7d9b-174">修复了各种 bug 和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-174">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086433-may-21"></a><span data-ttu-id="d7d9b-175">版本 91.0.864.33：5 月 21 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-175">Version 91.0.864.33: May 21</span></span>

<span data-ttu-id="d7d9b-176">修复了各种 bug 和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-176">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086427-may-14"></a><span data-ttu-id="d7d9b-177">版本 91.0.864.27：5 月 14 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-177">Version 91.0.864.27: May 14</span></span>

<span data-ttu-id="d7d9b-178">修复了各种 bug 和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-178">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086419-may-7"></a><span data-ttu-id="d7d9b-179">版本 91.0.864.19：5 月 7 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-179">Version 91.0.864.19: May 7</span></span>

<span data-ttu-id="d7d9b-180">修复了各种 bug 和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-180">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086415-may-3"></a><span data-ttu-id="d7d9b-181">版本 91.0.864.15：5 月 3 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-181">Version 91.0.864.15: May 3</span></span>

<span data-ttu-id="d7d9b-182">修复了各种 bug 和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-182">Fixed various bugs and performance issues.</span></span>

## <a name="version-91086411-april-30"></a><span data-ttu-id="d7d9b-183">版本 91.0.864.11：4 月 30 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-183">Version 91.0.864.11: April 30</span></span>

### <a name="feature-updates"></a><span data-ttu-id="d7d9b-184">功能更新</span><span class="sxs-lookup"><span data-stu-id="d7d9b-184">Feature updates</span></span>

- <span data-ttu-id="d7d9b-185">**标识源自代理级别的 Microsoft Defender 应用程序防护容器的网络流量**。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-185">**Identify network traffic originating from Microsoft Defender Application Guard containers at the proxy level**.</span></span> <span data-ttu-id="d7d9b-186">从 Microsoft Edge 版本 91 开始，内置了对源自应用程序防护容器的网络流量进行标记的支持，允许企业识别这些流量并应用特定策略。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-186">Starting with Microsoft Edge version 91, there’s built in support to tag network traffic originating from Application Guard containers, allowing enterprises to identify them and apply specific policies.</span></span>

- <span data-ttu-id="d7d9b-187">**支持允许将收藏夹从主机同步到边缘应用程序防护容器的选项**。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-187">**Support option to allow synchronizing Favorites from the host to the Edge Application Guard container**.</span></span> <span data-ttu-id="d7d9b-188">从 Microsoft Edge 版本 91 开始，用户可以选择配置应用程序防护以将其收藏夹从主机同步到容器。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-188">Starting with Microsoft Edge version 91, users have the option to configure Application Guard to synchronize their favorites from the host to the container.</span></span> <span data-ttu-id="d7d9b-189">这确保了容器上也可显示新的收藏夹。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-189">This ensures new favorites appear on the container as well.</span></span>

- <span data-ttu-id="d7d9b-190">**支持语音识别 API。**</span><span class="sxs-lookup"><span data-stu-id="d7d9b-190">**Support for Speech Recognition APIs**.</span></span> <span data-ttu-id="d7d9b-191">从 Microsoft Edge 版本 91 开始，将添加对 Google.com 和类似网站上语音识别命令的 API 支持。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-191">Starting with Microsoft Edge version 91, API support for speech recognition commands on Google.com and similar sites will be added.</span></span> <span data-ttu-id="d7d9b-192">此功能仅限于一组启用了实验的随机选择的用户。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-192">This feature is limited to a randomly selected group of users who have enabled experimentation.</span></span> <span data-ttu-id="d7d9b-193">这些用户向功能团队提供反馈。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-193">These users are giving feedback to the feature team.</span></span>

- <span data-ttu-id="d7d9b-194">**使用新的主题颜色个性化设置浏览器**。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-194">**Personalize your browser with new theme colors**.</span></span> <span data-ttu-id="d7d9b-195">使用“设置”->“外观”页上的十四种新主题颜色之一打造你自己的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-195">Make Microsoft Edge your own with one of the fourteen new theme colors on the Settings -> Appearance page.</span></span> <span data-ttu-id="d7d9b-196">也可以从 Microsoft Edge 加载项网站安装自定义主题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-196">You can also install custom themes from the Microsoft Edge Add-on site.</span></span> [<span data-ttu-id="d7d9b-197">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="d7d9b-197">Learn more</span></span>](https://techcommunity.microsoft.com/t5/articles/make-microsoft-edge-your-own-with-themes/m-p/2083165)

- <span data-ttu-id="d7d9b-198">**中断下载** 从 Microsoft Edge 版本 91 开始，如果在未经用户交互的情况下启动对计算机有害的下载，并且 SmartScreen 应用程序信誉检查不支持此下载，则浏览器将自动中断该类型的下载。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-198">**Interrupt Downloads** Starting with Microsoft Edge version 91 the browser will automatically interrupt downloads of types which could harm your computer if those downloads are started without a user interaction and are not supported by SmartScreen Application Reputation check.</span></span> <span data-ttu-id="d7d9b-199">用户可能会覆盖并继续下载，方法是右键单击并在下载项上选择“保留”。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-199">Users may override and continue to download by right clicking and choosing “Keep” on the download item.</span></span>
<span data-ttu-id="d7d9b-200">企业管理员可以通过以下两个策略之一选择退出此行为：</span><span class="sxs-lookup"><span data-stu-id="d7d9b-200">Enterprise administrators may opt out of this behavior one of these two policies:</span></span>
    - <span data-ttu-id="d7d9b-201">[ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - 对域上的指定文件类型禁用基于文件类型扩展名的下载警告。有关详细信息，请参阅 [Microsoft Edge 安全下载中断](/deployedge/microsoft-edge-security-downloads-interruptions)</span><span class="sxs-lookup"><span data-stu-id="d7d9b-201">[ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) - Disable download file type extension-based warnings for specified file types on domains For more information, see [Microsoft Edge Security downloads interruptions](/deployedge/microsoft-edge-security-downloads-interruptions)</span></span>

### <a name="policy-updates"></a><span data-ttu-id="d7d9b-202">策略更新</span><span class="sxs-lookup"><span data-stu-id="d7d9b-202">Policy updates</span></span>

#### <a name="new-policies"></a><span data-ttu-id="d7d9b-203">新策略</span><span class="sxs-lookup"><span data-stu-id="d7d9b-203">New policies</span></span>

<span data-ttu-id="d7d9b-204">添加了六条新的策略。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-204">Six new policies were added.</span></span> <span data-ttu-id="d7d9b-205">从 [Microsoft Edge 企业版登录页面](https://www.microsoft.com/edge/business/download) 下载更新的管理模板。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-205">Download the updated Administrative Templates from the [Microsoft Edge Enterprise landing page](https://www.microsoft.com/edge/business/download).</span></span> <span data-ttu-id="d7d9b-206">添加了以下新策略：</span><span class="sxs-lookup"><span data-stu-id="d7d9b-206">The following new policies were added:</span></span>

- <span data-ttu-id="d7d9b-207">[ApplicationGuardTrafficIdentificationEnabled](/DeployEdge/microsoft-edge-policies#applicationguardtrafficidentificationenabled) - 应用程序防护流量标识</span><span class="sxs-lookup"><span data-stu-id="d7d9b-207">[ApplicationGuardTrafficIdentificationEnabled](/DeployEdge/microsoft-edge-policies#applicationguardtrafficidentificationenabled) - Application Guard Traffic Identification</span></span>
- <span data-ttu-id="d7d9b-208">[ExplicitlyAllowedNetworkPorts](/DeployEdge/microsoft-edge-policies#explicitlyallowednetworkports) - 显式允许的网络端口</span><span class="sxs-lookup"><span data-stu-id="d7d9b-208">[ExplicitlyAllowedNetworkPorts](/DeployEdge/microsoft-edge-policies#explicitlyallowednetworkports) - Explicitly allowed network ports</span></span>
- <span data-ttu-id="d7d9b-209">[ImportStartupPageSettings](/DeployEdge/microsoft-edge-policies#importstartuppagesettings) - 允许导入启动页设置</span><span class="sxs-lookup"><span data-stu-id="d7d9b-209">[ImportStartupPageSettings](/DeployEdge/microsoft-edge-policies#importstartuppagesettings) - Allow importing of startup page settings</span></span>
- <span data-ttu-id="d7d9b-210">[MathSolverEnabled](/DeployEdge/microsoft-edge-policies#mathsolverenabled) - 允许用户截取数学问题，并通过 Microsoft Edge 中的分步说明获取解决方案</span><span class="sxs-lookup"><span data-stu-id="d7d9b-210">[MathSolverEnabled](/DeployEdge/microsoft-edge-policies#mathsolverenabled) - Let users snip a Math problem and get the solution with a step-by-step explanation in Microsoft Edge</span></span>
- <span data-ttu-id="d7d9b-211">[NewTabPageContentEnabled](/DeployEdge/microsoft-edge-policies#newtabpagecontentenabled) - 允许新选项卡页上的 Microsoft 新闻内容</span><span class="sxs-lookup"><span data-stu-id="d7d9b-211">[NewTabPageContentEnabled](/DeployEdge/microsoft-edge-policies#newtabpagecontentenabled) - Allow Microsoft News content on the new tab page</span></span>
- <span data-ttu-id="d7d9b-212">[NewTabPageQuickLinksEnabled](/DeployEdge/microsoft-edge-policies#newtabpagequicklinksenabled) - 允许新选项卡页上的快速链接</span><span class="sxs-lookup"><span data-stu-id="d7d9b-212">[NewTabPageQuickLinksEnabled](/DeployEdge/microsoft-edge-policies#newtabpagequicklinksenabled) - Allow quick links on the new tab page</span></span>

#### <a name="obsoleted-policy"></a><span data-ttu-id="d7d9b-213">已过时的策略</span><span class="sxs-lookup"><span data-stu-id="d7d9b-213">Obsoleted Policy</span></span>

- <span data-ttu-id="d7d9b-214">[ProactiveAuthEnabled](./microsoft-edge-policies.md#proactiveauthenabled) - 启用主动身份验证。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-214">[ProactiveAuthEnabled](./microsoft-edge-policies.md#proactiveauthenabled) - Enable Proactive Authentication</span></span>
<!-- end major 91 -->

## <a name="version-90081846-april-22"></a><span data-ttu-id="d7d9b-215">版本 90.0.818.46：4 月 22 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-215">Version 90.0.818.46: April 22</span></span>

<span data-ttu-id="d7d9b-216">修复了各种 bug 和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-216">Fixed various bugs and performance issues.</span></span>

## <a name="version-90081842-april-20"></a><span data-ttu-id="d7d9b-217">版本 90.0.818.42：4 月 20 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-217">Version 90.0.818.42: April 20</span></span>

<span data-ttu-id="d7d9b-218">修复了各种 bug 和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-218">Fixed various bugs and performance issues.</span></span>

## <a name="version-90081841-april-16"></a><span data-ttu-id="d7d9b-219">版本 90.0.818.41：4 月 16 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-219">Version 90.0.818.41: April 16</span></span>

<span data-ttu-id="d7d9b-220">修复了各种 bug 和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-220">Fixed various bugs and performance issues.</span></span>

## <a name="version-90081838-april-14"></a><span data-ttu-id="d7d9b-221">版本 90.0.818.38：4 月 14 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-221">Version 90.0.818.38: April 14</span></span>

<span data-ttu-id="d7d9b-222">修复了各种 bug 和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-222">Fixed various bugs and performance issues.</span></span>

## <a name="version-90081836-april-12"></a><span data-ttu-id="d7d9b-223">版本 90.0.818.36：4 月 12 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-223">Version 90.0.818.36: April 12</span></span>

<span data-ttu-id="d7d9b-224">修复了各种 bug 和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-224">Fixed various bugs and performance issues.</span></span>

## <a name="version-90081827-april-2"></a><span data-ttu-id="d7d9b-225">版本 90.0.818.27：4 月 2 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-225">Version 90.0.818.27: April 2</span></span>

<span data-ttu-id="d7d9b-226">修复了各种 bug 和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-226">Fixed various bugs and performance issues.</span></span>

## <a name="version-90081822-march-29"></a><span data-ttu-id="d7d9b-227">版本 90.0.818.22：3 月 29 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-227">Version 90.0.818.22: March 29</span></span>

<span data-ttu-id="d7d9b-228">修复了各种 bug 和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-228">Fixed various bugs and performance issues.</span></span>

## <a name="version-90081814-march-22"></a><span data-ttu-id="d7d9b-229">版本 90.0.818.14：3 月 22 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-229">Version 90.0.818.14: March 22</span></span>

<span data-ttu-id="d7d9b-230">修复了各种 bug 和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-230">Fixed various bugs and performance issues.</span></span>
<!-- begin major 90 -->
## <a name="version-9008188-march-16"></a><span data-ttu-id="d7d9b-231">版本 90.0.818.8：3 月 16 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-231">Version 90.0.818.8: March 16</span></span>

### <a name="feature-updates"></a><span data-ttu-id="d7d9b-232">功能更新</span><span class="sxs-lookup"><span data-stu-id="d7d9b-232">Feature updates</span></span>

- <span data-ttu-id="d7d9b-233">**SSO（单一登录）现已适用于 macOS 上的Azure Active Directory (Azure AD) 帐户和 Microsoft 帐户 (MSA)**。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-233">**Single Sign On (SSO) is now available for Azure Active Directory (Azure AD) accounts and Microsoft Account (MSA) on macOS**.</span></span> <span data-ttu-id="d7d9b-234">现在，已在 macOS 上登录 Microsoft Edge 的用户将自动登录到配置为允许使用工作帐户和 Microsoft 帐户进行单一登录的网站（如 bing.com、office.com、msn.com 和 outlook.com）。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-234">A user signed in on Microsoft Edge on macOS will now get automatically signed into websites that are configured to allow single sign on with Work and Microsoft accounts (for example, bing.com, office.com, msn.com, and outlook.com).</span></span>

- **<span data-ttu-id="d7d9b-235">展台模式。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-235">Kiosk mode.</span></span>** <span data-ttu-id="d7d9b-236">从 Microsoft Edge 版本 90 开始，我们已锁定 UI 打印设置，以仅允许配置的打印机和“打印到 PDF”选项。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-236">Starting with Microsoft Edge version 90, we have locked down the UI print settings to only allow the configured printers and “Print to PDF” options.</span></span> <span data-ttu-id="d7d9b-237">我们还在分配的访问权限单应用展台模式中进行了改进，以限制从浏览器启动其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-237">We have also done improvements within the assigned access single app kiosk mode to restrict the launch of other applications from the browser.</span></span> <span data-ttu-id="d7d9b-238">有关展台模式功能的详细信息，请转到 [此处](/deployedge/microsoft-edge-configure-kiosk-mode#kiosk-mode-supported-features)。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-238">For more information about the kiosk mode features please go [here](/deployedge/microsoft-edge-configure-kiosk-mode#kiosk-mode-supported-features).</span></span>

- **<span data-ttu-id="d7d9b-239">打印：</span><span class="sxs-lookup"><span data-stu-id="d7d9b-239">Printing:</span></span>**

  - <span data-ttu-id="d7d9b-240">**非 PostScript 打印机的全新打印光栅化模式**。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-240">**New print rasterization mode for non-PostScript printers**.</span></span> <span data-ttu-id="d7d9b-241">从 Microsoft Edge 版本 90 开始，管理员可以使用新策略为用户定义打印光栅化模式。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-241">Starting with Microsoft Edge version 90, Admins can use a new policy to define print rasterization mode for their users.</span></span> <span data-ttu-id="d7d9b-242">此策略控制 Microsoft Edge 如何在 Windows 上打印到非 PostScript 打印机。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-242">This policy  controls how Microsoft Edge prints to non-PostScript printers on Windows.</span></span>  <span data-ttu-id="d7d9b-243">有时，在非 PostScript 打印机上的打印作业需要进行光栅化才能正确打印。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-243">Sometimes print jobs on non-PostScript printers need to be rasterized to print correctly.</span></span> <span data-ttu-id="d7d9b-244">打印选项为“完整”和“快速”。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-244">The print options are Full and Fast.</span></span>

  - <span data-ttu-id="d7d9b-245">**打印的其他页面缩放选项**。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-245">**Additional page scaling options for printing**.</span></span> <span data-ttu-id="d7d9b-246">用户现在可在使用其他选项打印网页和 PDF 文档时自定义缩放。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-246">Users are now able to customize scaling while printing webpages and PDF documents using additional options.</span></span> <span data-ttu-id="d7d9b-247">“适应页面”选项可确保网页或文档适合所选“纸张大小”中可用于打印的空间。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-247">The "Fit to Page" option ensures that the webpage or document is fit into the space available in the selected "Paper size" for printing.</span></span> <span data-ttu-id="d7d9b-248">“实际大小”选项可确保无论所选“纸张大小”如何，正在打印内容的大小都没有任何变化。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-248">The "Actual size" option ensures that there are no changes in the size of the contents being printed regardless of the selected "Paper size".</span></span>

- **<span data-ttu-id="d7d9b-249">工作效率：</span><span class="sxs-lookup"><span data-stu-id="d7d9b-249">Productivity:</span></span>**

  - <span data-ttu-id="d7d9b-250">**自动填充建议扩展为包含剪贴板中的地址字段内容**。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-250">**Autofill suggestions are extended to include address fields content from clipboard**.</span></span> <span data-ttu-id="d7d9b-251">在单击配置文件/地址字段（例如，电话、电子邮件、邮政编码、城市、省/市/县等）将分析剪贴板内容，以显示为自动填充建议。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-251">Clipboard content is parsed when you click on a profile/address field (for example, phone, email, zip code, city, state, etc.) to show as autofill suggestions.</span></span>

  - <span data-ttu-id="d7d9b-252">**即使未检测到表单或字段，用户也可以搜索自动填充建议**。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-252">**Users can search for autofill suggestions even if a form or field isn’t detected**.</span></span> <span data-ttu-id="d7d9b-253">现在，如果将信息保存在 Microsoft Edge 上，将自动弹出自动填充建议，并帮助你在填写表单时节省时间。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-253">Today if you have your information saved on Microsoft Edge, autofill suggestions pop up automatically and help you save time while filling out forms.</span></span> <span data-ttu-id="d7d9b-254">如果自动填充遗漏了表单，或者希望获取通常没有自动填充的表单（如 临时表单）的数据，可以使用自动填充来搜索信息。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-254">In cases where autofill misses a form, or if you want to fetch data in forms that don't typically have autofill (like temporary forms), you can search for your information using autofill.</span></span>

- <span data-ttu-id="d7d9b-255">**从菜单栏中的浮出控件访问下载**。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-255">**Access downloads from a flyout in the menu bar**.</span></span> <span data-ttu-id="d7d9b-256">下载将显示在右上角，且所有活动下载都位于同一位置。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-256">Downloads will appear in the top-right corner with all the active downloads in one place.</span></span> <span data-ttu-id="d7d9b-257">此菜单很容易消除，以便用户可以继续不间断地浏览，并且可以从工具栏直接监视总体下载进度。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-257">This menu is easily dismissible so users can continue browsing uninterrupted, and they can monitor overall download progress right from the toolbar.</span></span> <span data-ttu-id="d7d9b-258">[了解详细信息](https://techcommunity.microsoft.com/t5/articles/introducing-the-new-downloads-experience/m-p/2111551)。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-258">[Learn more](https://techcommunity.microsoft.com/t5/articles/introducing-the-new-downloads-experience/m-p/2111551).</span></span>


### <a name="policy-updates"></a><span data-ttu-id="d7d9b-259">策略更新</span><span class="sxs-lookup"><span data-stu-id="d7d9b-259">Policy updates</span></span>

#### <a name="new-policies"></a><span data-ttu-id="d7d9b-260">新策略</span><span class="sxs-lookup"><span data-stu-id="d7d9b-260">New policies</span></span>

<span data-ttu-id="d7d9b-261">添加了 7 个新策略。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-261">Seven new policies were added.</span></span> <span data-ttu-id="d7d9b-262">从 [Microsoft Edge 企业版登录页面](https://www.microsoft.com/edge/business/download) 下载更新的管理模板。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-262">Download the updated Administrative Templates from the [Microsoft Edge Enterprise landing page](https://www.microsoft.com/edge/business/download).</span></span> <span data-ttu-id="d7d9b-263">添加了以下新策略：</span><span class="sxs-lookup"><span data-stu-id="d7d9b-263">The following new policies were added:</span></span>

- <span data-ttu-id="d7d9b-264">[ApplicationGuardFavoritesSyncEnabled](./microsoft-edge-policies.md#applicationguardfavoritessyncenabled) - 已启用应用程序防护收藏夹同步</span><span class="sxs-lookup"><span data-stu-id="d7d9b-264">[ApplicationGuardFavoritesSyncEnabled](./microsoft-edge-policies.md#applicationguardfavoritessyncenabled) - Application Guard Favorites Sync Enabled</span></span>
- <span data-ttu-id="d7d9b-265">[ManagedConfigurationPerOrigin](./microsoft-edge-policies.md#managedconfigurationperorigin) - 将网站的托管配置值设置到特定源</span><span class="sxs-lookup"><span data-stu-id="d7d9b-265">[ManagedConfigurationPerOrigin](./microsoft-edge-policies.md#managedconfigurationperorigin) - Sets managed configuration values for websites to specific origins</span></span>
- <span data-ttu-id="d7d9b-266">[PrintRasterizationMode](./microsoft-edge-policies.md#printrasterizationmode) - 打印光栅化模式</span><span class="sxs-lookup"><span data-stu-id="d7d9b-266">[PrintRasterizationMode](./microsoft-edge-policies.md#printrasterizationmode) - Print Rasterization Mode</span></span>
- <span data-ttu-id="d7d9b-267">[QuickViewOfficeFilesEnabled](./microsoft-edge-policies.md#quickviewofficefilesenabled) - 在 Microsoft Edge 中管理 QuickView Office 文件功能</span><span class="sxs-lookup"><span data-stu-id="d7d9b-267">[QuickViewOfficeFilesEnabled](./microsoft-edge-policies.md#quickviewofficefilesenabled) - Manage QuickView Office files capability in Microsoft Edge</span></span>
- <span data-ttu-id="d7d9b-268">[SSLErrorOverrideAllowedForOrigins](./microsoft-edge-policies.md#sslerroroverrideallowedfororigins) - 允许用户从特定源的 HTTPS 警告页面继续操作</span><span class="sxs-lookup"><span data-stu-id="d7d9b-268">[SSLErrorOverrideAllowedForOrigins](./microsoft-edge-policies.md#sslerroroverrideallowedfororigins) - Allow users to proceed from the HTTPS warning page for specific origins</span></span>
- <span data-ttu-id="d7d9b-269">[WindowOcclusionEnabled](./microsoft-edge-policies.md#windowocclusionenabled) - 启用窗口封闭</span><span class="sxs-lookup"><span data-stu-id="d7d9b-269">[WindowOcclusionEnabled](./microsoft-edge-policies.md#windowocclusionenabled) - Enable Window Occlusion</span></span>
- <span data-ttu-id="d7d9b-270">[WindowsHelloForHTTPAuthEnabled](./microsoft-edge-policies.md#windowshelloforhttpauthenabled) - 已启用 Windows Hello HTTP 身份验证</span><span class="sxs-lookup"><span data-stu-id="d7d9b-270">[WindowsHelloForHTTPAuthEnabled](./microsoft-edge-policies.md#windowshelloforhttpauthenabled) - Windows Hello For HTTP Auth Enabled</span></span>

#### <a name="deprecated-policies"></a><span data-ttu-id="d7d9b-271">已弃用的策略</span><span class="sxs-lookup"><span data-stu-id="d7d9b-271">Deprecated policies</span></span>

- <span data-ttu-id="d7d9b-272">[NativeWindowOcclusionEnabled](./microsoft-edge-policies.md#nativewindowocclusionenabled) - 启用本机窗口封闭</span><span class="sxs-lookup"><span data-stu-id="d7d9b-272">[NativeWindowOcclusionEnabled](./microsoft-edge-policies.md#nativewindowocclusionenabled) - Enable Native Window Occlusion</span></span>
- <span data-ttu-id="d7d9b-273">[SSLVersionMin](./microsoft-edge-policies.md#sslversionmin)- 已启用最低 TLS 版本</span><span class="sxs-lookup"><span data-stu-id="d7d9b-273">[SSLVersionMin](./microsoft-edge-policies.md#sslversionmin)- Minimum TLS version enabled</span></span>
<!-- end major 90 -->

## <a name="version-89077454-march-13"></a><span data-ttu-id="d7d9b-274">版本 89.0.774.54：3 月 13 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-274">Version 89.0.774.54: March 13</span></span>

<span data-ttu-id="d7d9b-275">修复了各种 bug 和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-275">Fixed various bugs and performance issues.</span></span>

## <a name="version-89077450-march-10"></a><span data-ttu-id="d7d9b-276">版本 89.0.774.50：3 月 10 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-276">Version 89.0.774.50: March 10</span></span>

<span data-ttu-id="d7d9b-277">修复了各种错误和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-277">Fixed various bugs and performance issues.</span></span>

## <a name="version-89077448-march-8"></a><span data-ttu-id="d7d9b-278">版本 89.0.774.48：3 月 8 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-278">Version 89.0.774.48: March 8</span></span>

<span data-ttu-id="d7d9b-279">修复了各种错误和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-279">Fixed various bugs and performance issues.</span></span>

## <a name="version-89077445-march-3"></a><span data-ttu-id="d7d9b-280">版本 89.0.774.45：3 月 3 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-280">Version 89.0.774.45: March 3</span></span>

<span data-ttu-id="d7d9b-281">修复了各种错误和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-281">Fixed various bugs and performance issues.</span></span>

## <a name="version-89077439-february-26"></a><span data-ttu-id="d7d9b-282">版本 89.0.774.39：2 月 26 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-282">Version 89.0.774.39: February 26</span></span>

<span data-ttu-id="d7d9b-283">修复了各种错误和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-283">Fixed various bugs and performance issues.</span></span>

## <a name="version-89077434-february-22"></a><span data-ttu-id="d7d9b-284">版本 89.0.774.34：2 月 22 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-284">Version 89.0.774.34: February 22</span></span>

<span data-ttu-id="d7d9b-285">修复了各种错误和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-285">Fixed various bugs and performance issues.</span></span>

## <a name="version-89077427-february-12"></a><span data-ttu-id="d7d9b-286">版本 89.0.774.27：2 月 12 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-286">Version 89.0.774.27: February 12</span></span>

<span data-ttu-id="d7d9b-287">修复了各种错误和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-287">Fixed various bugs and performance issues.</span></span>

## <a name="version-89077423-february-8"></a><span data-ttu-id="d7d9b-288">版本 89.0.774.23：2 月 8 日</span><span class="sxs-lookup"><span data-stu-id="d7d9b-288">Version 89.0.774.23: February 8</span></span>

<span data-ttu-id="d7d9b-289">修复了各种 bug 和性能问题。</span><span class="sxs-lookup"><span data-stu-id="d7d9b-289">Fixed various bugs and performance issues.</span></span>

<!-- begin major 89 -->

<!--- Archived from Version 87.0.664.18: October 26 to to version 89.0.774.18: February 3 ---->
<!--- Archived from Version 87.0.664.12: October 20 to to version 86.0.622.15: September 14 ---->
<!--- Archived to version 86.0.622.11: September 9 ---->
<!--- Archived to version 85.0.564.18: July 28 ---->

## <a name="see-also"></a><span data-ttu-id="d7d9b-290">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7d9b-290">See also</span></span>

- [<span data-ttu-id="d7d9b-291">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="d7d9b-291">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
