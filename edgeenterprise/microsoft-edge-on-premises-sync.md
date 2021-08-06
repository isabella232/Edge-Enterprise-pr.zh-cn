---
title: Active Directory (AD) 用户的本地同步
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Active Directory (AD) 用户的本地同步
ms.openlocfilehash: e6b123122e6fb5cd97f72423cff079f61eee2f1836f217fe1970bc05492a0f69
ms.sourcegitcommit: d44c0997ffe40d67421312ed96e7766da947eaa0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "11727555"
---
# <a name="on-premises-sync-for-active-directory-ad-users"></a>Active Directory (AD) 用户的本地同步

本文介绍 Active Directory (AD) 用户如何在不连接到 Microsoft 云服务的情况下，在计算机之间漫游 Microsoft Edge 收藏夹和设置。

> [!NOTE]
> 本文适用于 Microsoft Edge 版本 85 或更高版本。

## <a name="introduction"></a>简介

若要在 Microsoft Edge 中同步用户数据，通常需要 Microsoft 帐户或 Azure Active Directory (Azure AD) 帐户，并且需要连接到 Microsoft 云服务。 使用本地同步时，Microsoft Edge 将 Active Directory 用户的收藏夹和设置保存到可在不同计算机之间移动的文件中。 本地同步不会影响允许云同步的那些配置文件的云同步。

## <a name="how-it-works"></a>工作原理

Microsoft Edge 允许配置文件与 Active Directory (AD) 帐户关联，而 Active Directory (AD) 帐户不能与云同步一起使用。启用本地同步后，AD 配置文件中的数据将保存到名为 profile.pb 的文件中。 默认情况下，此文件存储在 *%APPDATA%/Microsoft/Edge* 中。 写入此文件后，它可以在不同的计算机之间移动，并且用户数据将在每台计算机上读取和写入。 Microsoft Edge 仅读取和写入此文件；管理员负责确保按需要移动文件。

## <a name="use-on-premises-sync"></a>使用本地同步

若要使用本地同步，必须启用该功能，将配置文件与 AD 帐户关联，并可选择更改用户数据的位置。

### <a name="enable-on-premises-sync"></a>启用本地同步

若要在 Microsoft Edge 中启用本地同步，请配置 [RoamingProfileSupportEnabled](./microsoft-edge-policies.md#roamingprofilesupportenabled) 策略。

### <a name="ensure-that-a-profile-is-associated-with-an-active-directory-account"></a>确保配置文件与 Active Directory 帐户相关联

本地同步仅适用于与 Active Directory (AD) 帐户相关联的配置文件。 如果不存在此类配置文件，则本地同步将无法正常运行。 若要确保用户使用 AD 帐户登录，请配置 [ConfigureOnPremisesAccountAutoSignIn](./microsoft-edge-policies.md#configureonpremisesaccountautosignin) 策略。 对于本地同步，Microsoft Edge 仅依靠 AD 为用户数据建立标识，而 Microsoft Edge 如何读取和写入本地数据和管理员如何为 AD 用户配置漫游之间不存在直接关系。

### <a name="change-the-location-of-the-user-data-optional"></a>更改用户数据的位置（可选）

默认情况下，用户数据存储在 *%APPDATA%/Microsoft/Edge* 下名为 **profile.pb** 的文件中。 若要更改此文件的位置，请配置 [RoamingProfileLocation](./microsoft-edge-policies.md#roamingprofilelocation) 策略。

## <a name="changes-in-the-user-experience-when-on-premises-sync-is-enabled"></a>启用本地同步时的用户体验更改

启用本地同步时，不会要求用户启用同步。此外，用户无法在同步设置中关闭同步，也无法打开本地同步不支持的同步类型。

## <a name="on-premises-sync-usage-notes"></a>本地同步使用说明

### <a name="running-cloud-sync-and-on-premises-sync-on-the-same-computer"></a>在同一台计算机上运行云同步和本地同步

本地同步不会影响云同步。如果 Microsoft Edge 具有多个 Microsoft 帐户或 Azure Active Directory 配置文件同步到云，则在启用本地同步时，这些配置文件将继续同步。

### <a name="running-microsoft-edge-on-more-than-one-computer-at-a-time-isnt-recommended"></a>不建议一次在多台计算机上运行 Microsoft Edge

由于本地同步的工作方式是在计算机之间移动用户数据文件，因此本地同步不会在同时会话之间同步更改。 因此，本地同步一次在一台计算机上使用时效果最佳。 如果同时运行本地会话，则在下次启动浏览器会话时，任何计算机上的数据可能会被来自另一台计算机的数据意外覆盖。

> [!NOTE]
> 启用本地同步时，Microsoft Edge 将锁定 **profile.pb** 文件。 如果文件夹重定向用于在不同计算机之间共享单个 **profile.pb** 文件，则只能启动使用该文件的 Microsoft Edge 的一个实例。

### <a name="using-other-sync-policies-with-on-premises-sync"></a>将其他同步策略与本地同步配合使用

如果需要，可以使用 [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) 策略选择性地禁用收藏夹或设置同步。 [SyncDisabled](./microsoft-edge-policies.md#syncdisabled) 策略不会影响本地同步。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge 和企业状态漫游](microsoft-edge-enterprise-state-roaming.md)
- [Microsoft Edge Enterprise Sync](microsoft-edge-enterprise-sync.md)