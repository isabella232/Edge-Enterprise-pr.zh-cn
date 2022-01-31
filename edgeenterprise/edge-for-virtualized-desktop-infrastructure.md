---
title: 'Microsoft Edge VDI (虚拟桌面基础结构) '
ms.author: anlake
author: dan-wesley
manager: collw
ms.date: 11/12/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Microsoft Edge VDI (虚拟桌面基础结构) 。
ms.openlocfilehash: fe1c1a7acf0b514812ff0aaf8f7a2b307304657d
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2022
ms.locfileid: "12298130"
---
# <a name="microsoft-edge-for-virtual-desktop-infrastructure-vdi"></a>Microsoft Edge VDI (虚拟桌面基础结构) 

本文介绍在虚拟环境中使用 Microsoft Edge的要求和限制。

## <a name="what-is-vdi"></a>什么是 VDI？

VDI (虚拟) 是一种桌面虚拟化技术，在数据中心的集中服务器上承载操作系统和应用程序。 此技术为安全且合规的集中源上的用户提供完全个性化的桌面体验。

Microsoft Edge虚拟环境中使用的方法与在本地设备上使用的方式相同。 虚拟桌面利用安全且受控的服务器环境。 根据选择的 VDI 解决方案，可能还可以为用户提供对 Intranet 应用程序和网站的无缝访问权限。

大多数Microsoft Edge功能在 VDI 环境中都受支持，无需任何特殊配置。 但是，为了确保获得最佳体验，我们建议您查看以下指南。

## <a name="platforms-certified-for-microsoft-edge"></a>经认证用于Microsoft Edge

以下平台经过认证Microsoft Edge：

- Azure 虚拟桌面
- Citrix 虚拟应用和桌面（以前称为 XenApp 和 XenDesktop）

尽管其他 VDI 解决方案尚未由 Microsoft Edge认证，但预计应该支持 Microsoft Edge 中的最常见工作流。 以下指南可能适用于所选解决方案，也可能不适用。

## <a name="performance-considerations-for-microsoft-edge-on-vdi"></a>在 VDI 上Microsoft Edge性能注意事项

在设计 VDI 环境时，应仔细考虑用户的工作流和需求，以实现最佳性能，并了解服务器配置的限制。

建议在 VDI 环境中部署Microsoft Edge最低要求：

- vCPU – 每个用户 2-4 个内核
- RAM - 每个用户 1 GB

大型和复杂的 Web 应用程序和扩展需要更多的内存和处理功能，配置虚拟环境时必须考虑这一点。

## <a name="microsoft-edge-on-non-persisted-vdi-environments"></a>Microsoft Edge非持久 VDI 环境中运行

许多 VDI 解决方案都允许访问持久化环境和非持久化环境。在持久化环境中，用户分配有一个在会话之间持续存在的虚拟环境，而在非持久化环境中，则将用户分配到多个可用计算机之一（每个会话的计算机都可能不同），在会话之间用户数据可能同步，也可能不同步。

使用非持久性环境时，通常会创建一个"黄金映像"，该映像具有将在每个设备上部署所需的应用和配置。 使用以下建议作为准备黄金图像的指南。

### <a name="deploy-microsoft-edge"></a>部署 Microsoft Edge

如果你使用 Windows 10 版本 1803 及以上版本，则应该已经Microsoft Edge已安装在系统上。 但是，如果你使用的是较旧版本的 Windows或想要部署其他Microsoft Edge频道，请按照以下步骤操作：

1. 从以下Microsoft Edge与 VDI VM 操作系统匹配的 MSI 程序包：

    - [下载适用于企业的 Microsoft Edge - Microsoft](https://www.microsoft.com/edge/business/download)

2. 运行以下命令，将 MSI 安装到 VM (VDI) ：

    - `msiexec /i <path_to_msi> /qn /norestart /l*v <install_logfile_name>`

### <a name="disable-automatic-updates"></a>禁用自动更新

对于非持久性计算机，最佳做法是通过更新黄金映像来禁用自动更新和更新 Microsoft Edge 以确保虚拟机池之间没有版本不匹配。

有关禁用自动更新的信息，请参阅以下策略：

- [更新策略替代默认值](/deployedge/microsoft-edge-update-policies#updatedefault)

- [更新策略替代](/deployedge/microsoft-edge-update-policies#update)

### <a name="profile-management"></a>配置文件管理

对于非持续安装，必须考虑 VM 可能不会在会话之间保持用户状态，或者可能会为用户分配以前从未使用过的 VM。 在此方案中，VM 没有任何用户数据。

Microsoft Edge支持多种用于同步用户数据的方法，因此无论用户数据以何种方式访问Microsoft Edge。 两种方法Azure Active Directory (Azure AD) AD 用户的同步和本地同步。

### <a name="azure-ad-sync"></a>Azure AD Sync

如果你Azure AD支持，Enterprise同步是保证用户数据同步到Microsoft Edge用户数据的最快且最简单的方法。 有关详细信息，请参阅配置[企业Microsoft Edge同步](/deployedge/microsoft-edge-enterprise-sync)

### <a name="on-premise-sync-for-active-directory-users"></a>Active Directory 用户的本地同步

通过本地同步，Microsoft Edge 将 Active Directory 用户的收藏夹和设置保存到可轻松在不同计算机之间移动的文件中。  

有关要求和配置详细信息，请参阅 [Active Directory (AD 用户) 同步](/deployedge/microsoft-edge-on-premises-sync)

### <a name="user-profile-redirection"></a>用户配置文件重定向  

有几种用于迁移和重定向整个用户文件夹的解决方案，以确保在非持久环境中维护用户上下文。 请与 VDI 提供程序联系，以确定适用于你的环境的建议解决方案。

一些热门解决方案包括以下选项：

- [FSLogix 概述 - FSLogix](/fslogix/overview)
- [如何配置 Citrix 配置文件管理](https://support.citrix.com/article/CTX222893)

在某些情况下，应从备份的用户文件夹中排除不必要的文件夹，以减少用户登录到计算机并迁移其配置文件时的初始加载时间。 如果这样操作，我们建议从备份中排除以下文件夹以减小大小。

- %LocalAppData%\Microsoft\Edge\User Data\Default\Cache
- %LocalAppData%\Microsoft\Edge\User Data\Default\Code Cache
- %LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsTopSites
- %LocalAppData%\Microsoft\Edge\User Data\Default\JumpListIconsRecentClosed

## <a name="known-issues"></a>已知问题

### <a name="microsoft-edge-crashes-in-older-versions-of-xenapp-and-xendesktop"></a>Microsoft Edge 在旧版 XenApp 和 XenDesktop 中崩溃

应在这些产品的较新版本中缓解此问题。 但是，如果你在环境中遇到此问题，可以通过禁用 Microsoft Edge 的 Citrix API 挂钩来解决此问题，请参阅如何基于每个应用程序禁用[Citrix API](https://support.citrix.com/article/CTX107825)挂钩。

### <a name="degraded-performance-when-rendering-pages-with-exceptionally-large-html-tables"></a>呈现具有超大 HTML 表的页面时性能下降

以下 Citrix 策略已知会减慢包含 30，000 (行的 html) 呈现速度。

- 自动键盘显示
- 远程组合框

有关详细信息，请参阅移动 [体验策略 (citrix.com) ](https://docs.citrix.com/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/mobile-experience-policy-settings.html) 设置。 禁用这些策略应该可以缓解此问题。

### <a name="windows-account-manager-authorization-scenarios-that-is-azure-sync-fail-in-microsoft-edge-when-run-as-a-citrix-seamless-application"></a>Windows帐户管理器授权 (，即 Azure 同步) 以 Citrix 无缝Microsoft Edge运行时，Azure 同步可能会失败。

这是 Microsoft Edge 和其他使用 WAM (的应用程序中的一个已知问题，即 Office) 由于在"无缝"模式下运行时未初始化必要的 Windows 组件。 请尝试以下选项之一来解决此问题：

- 通过Microsoft Edge桌面连接到 Citrix 主机，而不是使用无缝远程应用程序。
- 改为使用 Azure 虚拟桌面远程应用，这可缓解此问题。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [Azure 虚拟桌面](https://azure.microsoft.com/services/virtual-desktop/)