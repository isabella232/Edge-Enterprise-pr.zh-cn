---
title: Microsoft Edge 企业同步常见问题解答
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 有关 Microsoft Edge 企业同步的常见问题解答。
ms.openlocfilehash: a13e1f02f6e871004d45f81159d5cf0a3397b6ad
ms.sourcegitcommit: 8968f3107291935ed9adc84bba348d5f187eadae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "11979001"
---
# <a name="microsoft-edge-enterprise-sync-faq"></a>Microsoft Edge 企业同步常见问题解答

本文解答了有关 Microsoft Edge 版本 77 或更高版本的企业同步的常见问题。

## <a name="security-and-serverdata-compliance"></a>安全性和服务器/数据合规性

### <a name="is-the-synced-data-encrypted"></a>已同步的数据是否已加密？

数据使用 TLS 1.2 或更高版本在传输中加密。 在 Microsoft 的服务中，所有数据类型都会使用 AES128 进行额外的静态加密。 除用于同步已打开标签页和历史记录的数据类型外，所有数据类型都会在离开用户设备之前使用 [Azure 信息保护](./microsoft-edge-policies.md#restrictsignintopattern)策略所管理的密钥进行额外加密。

### <a name="why-dont-open-tab-and-history-data-have-more-client-side-encryption"></a>为什么已打开标签页和历史记录数据没有更多的客户端加密？

为了降低最终用户设备上的资源利用率，系统将基于已打开标签页的漫游数据在服务器端生成历史记录数据。 此过程无法支持此类数据的客户端加密。 若要禁用打开选项卡和历史记录同步，请应用 [SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled) 或 [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) 策略。

### <a name="can-tenant-admins-bring-their-own-key"></a>租户管理员能否使用自己的密钥？

是，可通过  [Azure 信息保护](https://azure.microsoft.com/services/information-protection/)来实现。

### <a name="where-is-microsoft-edge-sync-data-stored"></a>Microsoft Edge 的同步数据存储在哪里？

Azure AD 帐户的同步数据将根据租户 ID 存储在安全服务器中。 例如，在美国注册的租户的数据存储在位于该地区地理位置的服务器上，并使用与 Office 应用程序相同的存储解决方案。

### <a name="does-the-data-ever-leave-microsofts-cloud-aside-from-syncing-to-microsoft-edge"></a>除了同步至 Microsoft Edge 外，数据是否会离开 Microsoft 云？

否。

### <a name="what-terms-of-service-does-enterprise-sync-fall-under"></a>企业同步属于哪项服务条款？

Microsoft Edge 同步服务条款已列入 Microsoft 软件许可证，可使用 Microsoft Edge 访问  *edge://terms* 进行查看。 你的 Azure AD 订阅和服务条款最终属于 Microsoft 的[联机服务条款](https://www.microsoft.com/licensing/product-licensing/products)。

### <a name="does-microsoft-edge-support-government-community-cloud-gcc-high-compliance"></a>Microsoft Edge 是否支持政府社区云 (GCC) 高合规性？

目前尚不支持。 对于使用 GCC 高云服务的客户，已禁用 Microsoft Edge 同步。

## <a name="applying-sync"></a>应用同步

### <a name="why-isnt-microsoft-edge-sync-supported-in-all-m365-subscriptions"></a>为什么并非所有 M365 订阅都支持 Microsoft Edge 同步？

企业同步取决于 [Azure 信息保护](https://azure.microsoft.com/services/information-protection/)，它并非在所有 M365 订阅中都可用。

### <a name="is-microsoft-edge-sync-based-on-enterprise-state-roaming"></a>Microsoft Edge 同步是否基于企业状态漫游？

否。 ESR 可用于启用同步，但 Microsoft Edge 同步不是 ESR 的一部分。 有关详细信息，请参阅 [Microsoft Edge 同步](/DeployEdge/microsoft-edge-enterprise-sync)和 [Microsoft Edge 和企业状态漫游](/DeployEdge/microsoft-edge-enterprise-state-roaming)。

### <a name="will-microsoft-edge-ever-support-syncing-between-microsoft-edge-and-ie"></a>Microsoft Edge 是否支持 Microsoft Edge 和 IE 之间的同步？

尚无支持此同步的计划。 如果你的环境仍需要 IE 来支持旧版应用，请考虑使用我们的[新 IE 模式](./edge-ie-mode.md)。

### <a name="will-microsoft-edge-sync-with-microsoft-edge-legacy"></a>Microsoft Edge 是否将与 Microsoft Edge 旧版同步？

否，不会同步。 我们认为连接这两个生态系统将降低 Microsoft Edge 同步的可靠性。 我们会确保将现有数据迁移到 Microsoft Edge。 用户还可以从自己选择的浏览器导入数据，这也意味着 Microsoft Edge 无法与 IE 同步。

## <a name="managing-sync"></a>管理同步

### <a name="is-it-possible-to-stop-my-users-from-syncing-with-a-personal-tenant"></a>是否可以阻止我的用户与个人租户同步？

无法直接阻止，但你可以使用 [RestrictSigninToPattern](./microsoft-edge-policies.md#restrictsignintopattern) 策略确定哪些配置文件可以登录到 Microsoft Edge。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge 企业同步](microsoft-edge-enterprise-sync.md)
- [Microsoft Edge 和企业状态漫游](microsoft-edge-enterprise-state-roaming.md)
- [Microsoft Edge 企业版登录页面](https://aka.ms/EdgeEnterprise)