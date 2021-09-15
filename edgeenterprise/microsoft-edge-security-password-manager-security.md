---
title: 'Microsoft Edge 密码管理器安全性 '
ms.author: v-andreabarr
author: AndreaLBarr
manager: collw
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge 密码管理器安全性
ms.openlocfilehash: 816bbd2c18fcae0a20a19fb0feab199454aa67b6
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "11979034"
---
# <a name="microsoft-edge-password-manager-security"></a>Microsoft Edge 密码管理器安全性 

本文中的常见问题介绍了 Microsoft Edge 内置密码管理器如何为用户密码提供安全性。

> [!Note]
>本文适用于 Microsoft Edge 版本 77 或更高版本。

## <a name="how-are-passwords-stored-in-microsoft-edge-and-how-safe-is-this-approach"></a>密码如何存储在 Microsoft Edge 上？此方法有多安全？

Microsoft Edge 存储在磁盘上加密的密码。 它们使用 AES256 进行加密，并且加密密钥保存在操作系统 (OS) 存储区域中。 此技术称为本地数据加密。 尽管并非所有浏览器数据都经过加密，但敏感数据（如密码、信用卡号和 Cookie）在保存时会进行加密。

Microsoft Edge 密码管理器对密码进行加密，以便只有在用户登录到操作系统时才有权限访问这些密码。 即使攻击者具有管理员权限或脱机访问权限，并且可以访问本地存储的数据，系统设计会阻止攻击者获取未登录用户的纯文本密码。

解密其他用户密码的方法是，该用户已登录，并且攻击者拥有该用户的密码或已破坏域控制器。

### <a name="about-the-encryption-method"></a>关于加密方法

配置文件的加密密钥使用 Chromium OSCrypt 进行保护，并具有以下特定于平台的操作系统存储位置：

- 在 Windows 上，存储区域为 DPAPI

- 在 Mac 上，存储区域为密钥链

- 在 Linux 上，存储区域是 Gnome Keyring 或 KWallet

所有这些存储区域都使用以用户身份运行的部分或所有进程可访问的密钥对 AES256 密钥进行加密。 此攻击途径在博客中通常被称为为可能的“攻击”或“漏洞”，这是对浏览器威胁模型和安全性的不正确理解。

但是，物理上的本地攻击和恶意软件位于威胁模型之外，在这些条件下，加密数据将易受攻击。 如果你的计算机感染了恶意软件，攻击者可以解密对浏览器存储区域的访问权限。 攻击者的代码会以用户帐户身份运行，可以执行你可执行的任何操作。

## <a name="why-encrypt-data-locally-why-not-store-the-encryption-key-elsewhere-or-make-it-harder-to-obtain"></a>为什么在本地加密数据？ 为什么不将加密密钥存储在其他位置，或者使获取更加困难？

Internet 浏览器（包括 Microsoft Edge）未具备功能以抵御因恶意软件在计算机上以用户身份运行而导致整个设备被破坏的威胁。 但是，程序（如 Microsoft Defender SmartScreen）和操作系统级保护（如 Windows Defender）旨在确保设备从一开始就不会受到威胁。

尽管无法抵御完全信任的恶意软件，但本地数据加密在某些情况下很有用。 例如，如果攻击者找到一种从磁盘窃取文件的方法，但无法执行代码，或者盗取了一台不受完全磁盘加密保护的笔记本电脑，本地数据加密会使盗窃者更难获取存储的数据。

## <a name="do-you-recommend-storing-passwords-in-microsoft-edge"></a>是否建议将密码存储在 Microsoft Edge 上？

可以依赖 Microsoft Edge 内置密码管理器的用户可以（通常）使用更强大的唯一密码，因为他们无需记住所有密码，也无需经常键入密码。 此外，由于密码管理器只会自动填充其所属网站上的密码，因此用户不太可能遭受网络钓鱼攻击。

> [!Note]
>行业报告显示，80% 的在线事件与网络钓鱼相关，超过 37% 的未经过培训的用户无法通过网络钓鱼测试。

Microsoft Edge 密码管理器方便且易于分发，这有助于提高安全性。 与同步结合使用时，可以在所有设备上获取所有密码，并且很容易针对每个网站使用不同的密码。 可以针对每个网站使用不必记住的长而复杂的密码，并跳过每次键入复杂字符串的麻烦。 密码管理器的便利意味着有较低遭受钓鱼攻击的风险。

但是，使用以用户操作系统登录会话为键的密码管理器也意味着该会话中的攻击者可以立即检索用户保存的所有密码。 如果没有密码管理器可以进行窃取，攻击者将需要跟踪击键或监视提交的密码。

决定是否使用密码管理器取决于我们怎样评估整个设备可能受到的威胁以及所描述的优势。 对于大多数威胁模型，推荐使用 Microsoft Edge 密码管理器。

> [!Note]
>如果企业担心密码盗窃或由于密码被盗而网站受到入侵，则应采取其他预防措施。 一些有助于缓解此类事件的有效解决方案是通过 Active Directory、Azure Active Directory 或第三方进行单一登录（SSO）。 其他解决方案包括 2FA（[如 MS Authenticator](/azure/active-directory/user-help/user-help-auth-app-download-install)）或 [WebAuthN](https://webauthn.guide/)。

## <a name="should-a-password-manager-be-enabled-by-an-organization"></a>组织应启用密码管理器吗？

简单的回答是：应该，请使用浏览器的密码管理器。

更完整的响应意味着深入了解威胁模型，因为安全选项和选择因不同的威胁模型而异。 考虑是否应该为组织启用密码管理器时要考虑的一些相关问题包括：

- 你担心什么类型的攻击者？

- 你的用户登录到哪种类型的网站？

- 用户是否选择强的唯一密码？

- 你的用户帐户是否受 2FA 保护？

- 哪种类型的攻击最有可能发生？

- 如何保护企业设备免受恶意软件的攻击？

- 用户个人对不便的容限是什么？

- 考虑数据同步的影响。

在用户数据同步到各种用户设备以及组织对自动填充数据同步的控制量时，考虑用户数据的安全性非常重要。

数据同步和 Microsoft Edge：

- 可以在整个组织中根据需要启用或禁用数据同步。

- 传输中和云中静止状态的数据安全性：在浏览器和 Microsoft 服务器之间传输时，所有已同步数据在通过 HTTPS 传输时进行加密。 同步的数据也以加密状态存储在 Microsoft 服务器上。 同步之前，在设备上进一步加密敏感数据类型（如地址和密码）。 如果你使用的是工作或学校帐户，则所有数据类型都将进一步加密，然后再使用 Microsoft 信息保护同步。

## <a name="why-do-microsoft-security-baselines-recommend-disabling-the-password-manager"></a>为什么 Microsoft 安全基线建议禁用密码管理器？

Microsoft 安全团队当前对蠕虫的影响进行了评分，该蠕虫会危害 Enterprise PCS 网络（导致所有设备的密码管理器丢失所有凭据），它的严重性比会危害单个用户输入的凭据的靶向钓鱼攻击（几率更大但影响较低）威胁更大。

此评估正在讨论中，可能会随着 Microsoft Edge 中新的安全增强功能而变动。

## <a name="can-malicious-extensions-gain-access-to-passwords"></a>恶意扩展能否获取对密码的访问权限？

具有与页面交互的权限的扩展本质上可以访问该页面中的内容，包括自动填充的密码。 同样，恶意扩展可能会修改表单字段和网络请求/响应的内容，以滥用当前用户登录上下文的权力。

但是，Microsoft Edge 提供了一组覆盖广泛的策略，可精细控制已安装的扩展。 使用下表中的策略是保护公司数据所必需的。

| 策略 | 描述文字 |
|-|-|
|[BlockExternalExtensions](/deployedge/microsoft-edge-policies#blockexternalextensions)|阻止安装外部扩展|
|[ExtensionAllowedTypes](/deployedge/microsoft-edge-policies#extensionallowedtypes)|配置允许的扩展类型|
|[ExtensionInstallAllowlist](/deployedge/microsoft-edge-policies#extensioninstallallowlist)|允许安装特定扩展|
|[ExtensionInstallBlocklist](/deployedge/microsoft-edge-policies#extensioninstallblocklist)|控制无法安装的扩展|
|[ExtensionInstallForcelist](/deployedge/microsoft-edge-policies#extensioninstallforcelist)|控制静默安装的扩展|
|[ExtensionInstallSources](/deployedge/microsoft-edge-policies#extensioninstallsources)|配置扩展和用户脚本安装源|
| [ExtensionSettings](/deployedge/microsoft-edge-policies#extensionsettings) |配置扩展管理设置 |

## <a name="how-does-the-microsoft-edge-password-manager-compare-with-a-third-party-product"></a>Microsoft Edge 密码管理器和第三方产品相比如何？

下表显示了 Microsoft Edge 密码管理器与第三方密码管理器的比较。

| 第三方密码管理器 | Microsoft Edge 密码管理器|
|-|-|
| *服务器同步*。某些产品在云中存储密码以同步所有设备。 此功能很有用，但如果云服务受到威胁，你的数据被公开，则存在风险。 **备注：** 通过在云中加密密码，将加密密钥存储在你的设备上，让攻击者无法获取密钥和密码，可以减轻风险。| 存在云曝光风险，因为密码会在已安装 Windows Edge 的 Windows 设备之间同步。 **备注：** 此风险可通过本文中介绍的数据安全步骤得到减轻。|
| *信任*。 有必要信任第三方不会进行任何恶意操作，例如将密码发送给另一方。 **备注：** 通过查看源代码（开源产品）或相信供应商在意其信誉和收入，可以减轻此风险。 | **备注：** Microsoft 是一家知名且受信任的供应商，在提供企业级安全性和工作效率方面拥有数十年历史，并拥有旨在保护全球密码的资源。 |
| *供应链安全*。 很难验证供应商是否具有源代码的安全供应链/生成/发布流程。 |**备注：** Microsoft 具有可靠的内部流程，以确保源代码的风险降到最小。 |
| *客户端或帐户受到威胁*。如果客户端设备或用户帐户受到威胁，攻击者可以获取密码。 **备注：** 使用要求用户输入未在本地存储的主密码来解密密码的某些密码管理器，可以减轻此风险。主密码只能部分缓解问题，因为攻击者在填写表单字段时，可能会读取击键并获取主密码，因为它是从进程内存中键入或读取的密码。 | **备注：** Microsoft 提供操作系统级别的保护，如 Windows Defender 旨在确保首先设备不会受到入侵。 但是，如果客户端设备受到威胁，攻击者可能会解密密码。 |

> [!Note]
> 第三方产品可以针对其他威胁模型提供保护，但这也增加了复杂性，牺牲了易用性。 Microsoft Edge 密码管理器旨在提供方便易用的密码管理，这些密码管理可通过 IT 管理员使用组策略完全控制，并且不需要信任第三方。

## <a name="why-doesnt-microsoft-offer-a-master-password-to-protect-the-data"></a>为什么 Microsoft 不提供主密码来保护数据？

在磁盘上加密浏览器密码时，加密密钥可用于设备上的任何进程，包括任何本地运行的恶意软件。 即使密码通过主密钥在“保管库”中加密，在浏览器的内存空间中加载密码时也会解密密码，并在解锁保管库后获取密码。

（在自动填充其数据之前对用户进行身份验证）的主密码功能更加便捷，便于更广泛的威胁缓解。 具体而言，它有助于减少数据暴露给潜在恶意软件或实际本地攻击者的窗口。 但是，主密码不是万能密码，本地攻击者和专用恶意软件具有各种避开主密码保护的策略。

> [!Note]
> Microsoft 意识到在自动填充之前识别验证用户的重要性，此功能会在将来的版本中添加到 Microsoft Edge。

## <a name="can-using-a-password-manager-impact-my-privacy"></a>使用密码管理器会影响我的隐私吗？

不会，如果已执行了保护已保存密码访问权限的步骤，就不会。

一些广告商会利用一个已知的漏洞，它使用存储的密码来唯一地标识和跟踪用户。 有关详细信息，请参阅 [广告商在从浏览器的密码管理器拉取数据](https://www.theverge.com/2017/12/30/16829804/browser-password-manager-adthink-princeton-research)。 浏览器已采取措施来缓解此 [隐私问题](https://bugs.chromium.org/p/chromium/issues/detail?id=798492)。PasswordValueGatekeeper 类可用于限制对密码字段数据的访问，即使浏览器配置为在加载时自动填充。

通过启用可选的 edge://flags/#fill-on-account-select 功能，可以轻松缓解用户信息拉取威胁。 此功能仅允许在用户显式选择凭据后将密码添加到表单字段中，这可确保用户了解接收其密码的相关方。

## <a name="see-also"></a>另请参阅

[Microsoft Edge Enterprise 登录页面](https://www.microsoft.com/edge/business/download)

[在 Windows 10 上，Microsoft Edge 比 Chrome 商业版更安全的地方](/DeployEdge/ms-edge-security-for-business)
