---
title: Microsoft Edge 标识支持和配置
ms.author: avvaid
author: dan-wesley
manager: srugh
ms.date: 07/15/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge 标识支持和配置
ms.openlocfilehash: 357f3928d870f83aa087f86cbe30db3ec4f360a2
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979392"
---
# Microsoft Edge 标识支持和配置

本文介绍了 Microsoft Edge 如何使用标识支持同步和单一登录（SSO）等功能。 Microsoft Edge 支持使用 Active Directory 域服务 (AD DS)、Azure Active Directory (Azure AD) 和 Microsoft 帐户 (MSA) 登录。 目前，Microsoft Edge 仅支持属于全局云或 GCC 主权云的 Azure Active Directory (Azure AD) 帐户。 我们正在努力添加对其他主权云的支持。 

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 77 或更高版本。

## 浏览器登录和身份验证功能

Microsoft Edge 支持使用 Azure AD、MSA 或域帐户登录浏览器配置文件。 用于登录的帐户类型确定 Microsoft Edge 中的用户可以使用哪些经过身份验证的功能。 下表总结了每种帐户类型的功能支持。

|    | Azure AD Premium | Azure AD Free | 本地 AD DS | MSA     |
|----|------------------|---------------|----------------|---------|
| 同步 | 是 | 否 | 否 | 是 |
| 采用主刷新令牌的 SSO | 是 | 是 | 不可用 | 是 |
| 无缝 SSO | 是 | 是 | 是 | 不适用 |
| 集成的 Windows 身份验证 | 是 | 是 | 是 | 不适用 |
| 企业新选项卡页 | 需要 O365 |   需要 O365 | 否 | 不适用 |
| Microsoft 搜索 | 需要 O365 | 需要 O365 | 否 | 不适用 |

## 用户如何登录 Microsoft Edge

### 自动登录

Microsoft Edge 使用操作系统默认帐户自动登录浏览器。 根据设备的配置方式，用户可以使用以下方法之一自动登录 Microsoft Edge。

- **设备是混合/AAD 加入：** 可用于 Win10、早期版本 Windows 和相应的服务器版本。
用户将使用 Azure AD 帐户自动登录。
- **设备加入域：** 可用于 Win10、早期版本 Windows 和相应的服务器版本。
默认情况下，用户将不会自动登录。 如果用户以域账户登录，使用[ConfigureOnPremisesAccountAutoSignIn](https://docs.microsoft.com/deployedge/microsoft-edge-policies#configureonpremisesaccountautosignin)策略。 如果要使用 Azure AD 帐户自动登录用户，请考虑以混合方式加入设备。
- **操作系统默认帐户是 MSA：** Win10 RS3（版本1709 /内部版本10.0.16299）及更高版本。 在企业设备上不太可能出现这种情况。 但是，如果 OS 默认帐户是 MSA，Microsoft Edge 将自动使用 MSA 帐户登录。

### 手动登录

如果用户未自动登录到 Microsoft Edge，则可在首次运行体验、浏览器设置或打开“身份”浮出控件过程中手动登录 Microsoft Edge。 

### 管理浏览器登录

如果要管理浏览器登录，可以使用以下策略：

- 确保用户在 Microsoft Edge 中始终有工作配置文件。 [参见 NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled)
- 将登录限制为受信任的帐户组。 [参见 RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern)
- 禁用或强制浏览器登录。 [参见 BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)

## 浏览器至 Web 单一登录（SSO）

在部分平台上，可配置 Microsoft Edge 以让用户登录网站。 通过此选项，免除了他们重新输入凭据以访问工作网站的麻烦，并提高了工作效率。

### 采用主刷新令牌 (PRT) 的 SSO

Microsoft Edge 对基于 PRT 的 SSO 提供本机支持，不需要扩展。 在 Windows 10 RS3及更高版本上，如果用户登录了他们的浏览器配置文件，则将通过PRT机制实现对支持基于 PRT 的 SSO 网站实现 SSO。

主刷新令牌 (PRT) 是一个 Azure AD 密钥，用于在 Windows 10、iOS 和 Android 设备上进行身份验证。 它支持在这些设备上使用的应用程序中进行单一登录 (SSO)。 有关详细信息，请参阅[主刷新令牌是什么？](https://docs.microsoft.com/azure/active-directory/devices/concept-primary-refresh-token)。

### 无缝 SSO

正如 PRT SSO 一样，Microsoft Edge 提供本机无缝 SSO 支持，无需扩展。 在 Windows 10 RS3及更高版本上，如果用户登录了他们的浏览器配置文件，则将通过PRT机制实现对支持基于 PRT 的 SSO 网站实现 SSO。

当用户在连接到公司网络的公司设备上时，无缝单一登录会自动为用户签名。 启用后，用户无需输入密码即可登录 Azure AD。 通常，他们甚至不必键入用户名。 有关详细信息，请参阅 [Azure Active Directory 无缝单一登录](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso)。

### Windows 集成身份验证 (WIA)

Microsoft Edge 还支持 Windows 集成身份验证，以便在组织内部网络中对使用浏览器进行身份验证的任何应用程序提出身份验证请求。 Windows 10 的所有版本和早期版本的 Windows 均支持此功能。 默认情况下，Microsoft Edge 使用 Intranet 区域作为 WIA 的允许列表。 若要配置启用集成身份验证的服务器，参阅 [AuthServerAllowlist 策略](https://docs.microsoft.com/deployedge/microsoft-edge-policies#authserverallowlist)。

为了在 Microsoft Edge（版本 77 和更高版本）上支持基于 WIA 的SSO，可能还必须进行一些服务器端配置。 可能必须配置 Active Directory 联合身份验证服务 (AD FS) 属性 **WiaSupportedUserAgents**，以添加对新 Microsoft Edge 用户代理字符串的支持。 有关如何执行此操作的说明，请参阅[查看 WIASupportedUserAgent 设置](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/configure-ad-fs-browser-wia#view-wiasupporteduseragent-settings)和[更改 WIASupportedUserAgent 设置](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/configure-ad-fs-browser-wia#change-wiasupporteduseragent-settings)。 Windows 10 上 Microsoft Edge 用户代理字符串的示例如下显示，可在这里更多了解 [Microsoft Edge UA 字符串](https://docs.microsoft.com/microsoft-edge/web-platform/user-agent-string)。 

下面的 UA 字符串示例适用于发布此文章时的最新 Dev 渠道版本：<br> `"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3951.0 Safari/537.36 Edg/80.0.334.2"`

在MacOS上，还可以使用[ AuthServerAllowlist ](https://docs.microsoft.com/deployedge/microsoft-edge-policies#authserverallowlist)和[ AuthNegotiateDelegateAllowlist ](https://docs.microsoft.com/deployedge/microsoft-edge-policies#authnegotiatedelegateallowlist)策略来通过 Microsoft Edge 启用 Kerberos SSO。

## 附加身份验证方案

### 主动身份验证

主动身份验证是对浏览器到网站SSO的优化，可将身份验证预先加载到部分第一方网站。 如果用户使用必应作为搜索引擎，则可以提高地址栏的性能。 这为用户提供了个性化的 Microsoft Search for Business（MSB）搜索结果。 它还支持允许对关键服务（如 Office “新建选项卡”页面）进行身份验证。 你可使用 [ProactiveAuthEnabled]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled) 策略进行控制。

### NTLM 身份验证 Windows Hello CredUI

网站尝试使用 NTLM 或协商机制来登录用户但 SSO 不可用时，我们为用户提供了一种体验，他们可以与此网站共享操作系统凭据，以使用 Windows Hello Cred UI 来满足身份验证质询。 此登录流程仅在 NTLM 或协商质询期间，对于无法进行单一登录的 Windows 10 用户显示。

### 使用保存的密码自动登录

如果用户将密码保存在 Microsoft Edge 中，则可以启用一项功能，此功能会自动将其登录到保存凭据的网站中。 用户可以通过导航到*edge://settings/passwords*来切换此功能。 如果要配置此功能，可以使用[密码管理器](https://docs.microsoft.com/deployedge/microsoft-edge-policies#password-manager-and-protection)策略。

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 文档登录页面](https://docs.microsoft.com/DeployEdge/)
- [标识和访问管理](https://www.microsoft.com/security/technology/identity-access-management)
- [标识平台](https://developer.microsoft.com/identity)
- [使用 Azure Active Directory 建立坚实的身份标识基础的四个步骤](https://docs.microsoft.com/azure/active-directory/hybrid/four-steps)
