---
title: 适用于虚拟化桌面基础结构的 Edge
ms.author: anlake
author: AndreaLBarr
manager: collw
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 适用于虚拟化桌面基础结构的 Microsoft Edge。
ms.openlocfilehash: 5dc234b0e6fbba4778f8236399a0ff438f704578
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11641848"
---
# <a name="microsoft-edge-for-virtualized-desktop-infrastructure"></a>适用于虚拟化桌面基础结构的 Microsoft Edge

本文介绍在虚拟化环境中使用 Microsoft Edge 的要求和限制。

## <a name="what-is-vdi"></a>什么是 VDI？

虚拟桌面基础结构 (VDI) 是一种虚拟化技术，可在数据中心的集中式服务器上托管桌面操作系统和应用程序。 这为具有完全安全且合规的集中式源的用户提供完全个性化的桌面体验。

Microsoft Edge 可在此类虚拟化环境中使用的方式与在本地设备上使用的方式大致相同，同时从安全和受控的服务器环境运行。 根据所选的 VDI 解决方案，还可能为用户提供对 Intranet 应用程序和网站的无缝访问权限。

没有任何特殊配置的 VDI 环境支持 Edge 的大多数功能。 但是，为了确保获得最佳体验，建议遵循以下指南。

## <a name="platforms-certified-for-edge"></a>Microsoft Edge 认证的平台

- Azure 虚拟桌面
- Citrix 虚拟应用和桌面（以前称为 XenApp 和 XenDesktop）

虽然 Edge 团队尚未验证其他 VDI 解决方案，但预期应支持 Edge 中最常见的工作流。 下面提供的指南可能适用于所选解决方案，也可能不适用于所选解决方案。

## <a name="edge-on-vdi-performance-considerations"></a>Edge on VDI 性能注意事项

设计 VDI 环境时，应仔细考虑用户的工作流和需求，以实现最佳性能，以及服务器配置的限制。

对于将 Edge 部署到 VDI 环境，Edge 建议满足以下最低要求：

- vCPU - 每个用户 2 - 4 个核心
- RAM - 每个用户 1 GB

请注意，大型复杂的 Web 应用程序和扩展需要更多内存，配置环境时必须将这一点考虑在内。

## <a name="edge-on-non-persisted-vdi-environments"></a>非持久化 VDI 环境中的 Edge

许多 VDI 解决方案都允许访问持久化环境和非持久化环境。在持久化环境中，用户分配有一个在会话之间持续存在的虚拟环境，而在非持久化环境中，则将用户分配到多个可用计算机之一（每个会话的计算机都可能不同），在会话之间用户数据可能同步，也可能不同步。

使用非持久化环境时，通常会创建一个“黄金映像”，用于包含所需应用和配置的每个设备。 下面是我们对于为此类映像准备 Edge 的建议。

### <a name="deploy-edge"></a>部署 Edge

如果使用的是 Windows 10 版本 1803 及更高版本，则应已在系统上安装 Microsoft Edge。 但是，如果你使用的是较旧版本的 Windows 或希望部署不同的 Edge 通道，则建议执行以下步骤。

1. 从以下位置下载与 VDI VM 操作系统匹配的 Edge MSI 包：

    - [下载适用于企业的 Microsoft Edge - Microsoft](https://www.microsoft.com/edge/business/download)

2. 通过运行以下命令将 MSI 安装到 VDI VM：

    - `msiexec /i <path_to_msi> /qn /norestart /l*v <install_logfile_name>`

### <a name="disable-automatic-updates"></a>禁用自动更新

对于非持久化计算机，最佳做法是禁用自动更新，而是并改为通过更新“黄金映像”来更新 Edge，以确保计算机池之间没有版本不匹配的情况。

请参阅以下用于禁用自动更新的策略：

- [更新策略替代默认值](/deployedge/microsoft-edge-update-policies#updatedefault)

- [更新策略替代](/deployedge/microsoft-edge-update-policies#update)

### <a name="profile-management"></a>配置文件管理

在非持久化设置上，请务必考虑 VM 可能无法在会话之间保持用户状态，或者可能会为用户分配一个以前从未使用过的 VM，因此没有其任何用户数据。

Edge 支持几种同步用户数据的方法，以便无论用户以何种方式访问 Edge，数据都是可用的。

### <a name="azure-ad-sync"></a>Azure AD Sync

如果 Azure AD 计划支持，则企业同步是确保将 Edge 用户数据同步到所有用户设备的最快和最简单的方法。  

有关要求和配置的详细信息，请参阅以下内容。  

- [配置 Microsoft Edge 企业同步 | Microsoft Docs](/deployedge/microsoft-edge-enterprise-sync)

### <a name="on-premise-sync-for-active-directory-users"></a>Active Directory 用户的本地同步

通过本地同步，Microsoft Edge 将 Active Directory 用户的收藏夹和设置保存到可轻松在不同计算机之间移动的文件中。  

有关要求和配置的详细信息，请参阅以下内容。  

- [Active Directory (AD) 用户的本地同步 | Microsoft Docs](/deployedge/microsoft-edge-on-premises-sync)

### <a name="user-profile-redirection"></a>用户配置文件重定向  

有多个解决方案用于迁移和重定向整个用户文件夹，以确保在此类非持久化环境中维护用户上下文。 请咨询 VDI 提供商以确定建议的解决方案。

一些热门解决方案包括：

- [FSLogix 概述 - FSLogix |Microsoft Docs](/fslogix/overview)
- [如何配置 Citrix 配置文件管理](https://support.citrix.com/article/CTX222893)

此外，建议在使用此方法时从备份的用户文件夹中排除不必要的文件夹，以减少用户登录到计算机并且正在迁移配置文件时的初始加载时间。 如果这样操作，我们建议从备份中排除以下文件夹以减小大小。

- %LocalAppData%\Microsoft\Edge\User Data\Default\Cache
- %LocalAppData%\Microsoft\Edge\User Data\Default\Code Cache
- %LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsTopSites
- %LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsRecentClosed

## <a name="known-issues"></a>已知问题

### <a name="microsoft-edge-crashes-in-older-versions-of-xenapp-and-xendesktop"></a>Microsoft Edge 在旧版 XenApp 和 XenDesktop 中崩溃

此问题应在较新版本中得到缓解，但如果在你的环境中遇到此问题，可以通过禁用适用于 Edge 的 Citrix API 挂钩来解决此问题，请参阅 [如何在每个应用程序的基础上禁用 Citrix API 挂钩。](https://support.citrix.com/article/CTX107825)

### <a name="degraded-performance-when-rendering-pages-with-exceptionally-large-html-tables"></a>呈现具有超大 HTML 表的页面时性能下降

已知以下 Citrix 策略会降低具有非常大（超过 30,000 行）表的 html 页的呈现速度。

- 自动键盘显示
- 远程组合框

有关详细信息，请参阅 [移动体验策略设置 (citrix.com)](https://docs.citrix.com/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/mobile-experience-policy-settings.html)。 禁用这些策略应该可以缓解此问题。

### <a name="windows-account-manager-authorization-scenarios-ie--azure-sync-fail-in-edge-when-run-as-a-citrix-seamless-application"></a>作为 Citrix 无缝应用程序，Windows 帐户管理器授权方案（即 Azure 同步）在 Edge 中失败

这是 Edge 和其他使用 WAM（即 Office）的应用程序中的一个已知问题，因为在“无缝”模式下运行时，此类方案所必需的 Windows 组件未初始化。 要解决此问题，请执行以下操作：

- 通过远程桌面将 Edge 用于 Citrix 主机，而不是用作无缝远程应用程序。
- 请改用 Azure 虚拟桌面远程应用，这可以缓解此问题。
