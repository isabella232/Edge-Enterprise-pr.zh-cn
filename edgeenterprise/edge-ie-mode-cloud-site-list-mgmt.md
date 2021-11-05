---
title: 云站点列表管理 Internet Explorer (IE) 模式 (公共预览版) "
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 11/03/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解如何使用 IE 模式配置和使用云站点列表 Microsoft 365 管理中心。
ms.openlocfilehash: 29984aa559c0afda5be0457fcbe618dc264a3e68
ms.sourcegitcommit: 4ec03873a85f065d9bfa6203cfe6c3e938f79bc5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "12155039"
---
# <a name="cloud-site-list-management-for-ie-mode-public-preview"></a>适用于 IE 模式的云站点列表管理 (公共预览版) 

本文介绍如何通过 Microsoft 365 管理中心为Internet Explorer （IE） 模式配置和使用云站点列表管理。

## <a name="overview"></a>概述

当你将工作流和应用程序从 IE11 转换到 IE 模式时，**云站点列表管理**允许你在云中管理 IE 模式的网站列表。 可以使用** Microsoft 365管理中心**中的网站列表体验** Microsoft Edge 网站列表**。

若要了解详细信息，请观看 [IE 模式视频的云站点列表管理体验](https://www.youtube.com/watch?v=9-GovDcryXQ)。

> [!NOTE]
> 此体验现在为公共预览版。

预览体验使你能够将组织的站点列表存储在兼容的云位置，无需本地基础结构来托管站点列表。 可以通过管理中心创建、导入、导出网站列表和审核对网站列表 Microsoft 365 管理更改。 你可以将多个站点列表发布到云，并使用组策略分配不同的设备组以使用不同的列表。

## <a name="prerequisites"></a>必备条件

以下先决条件适用于此公共预览版。

1. 客户必须具有一个 Azure AD 租户。
2. 管理员必须安装 Microsoft Edge 版本 93 或更高版本，以及最新版本的[策略文件](https://aka.ms/edgeenterprise)。
3. 管理员必须是租户上的[ Edge 管理员](/azure/active-directory/roles/permissions-reference#edge-administrator)或[全局管理员](/azure/active-directory/roles/permissions-reference#global-administrator)才能访问Microsoft Edge 站点列表体验。
   - 若要选择加入公共预览版，全局管理员需要选择租户加入定向发布。 有关详细信息，请参阅 [选择加入公共预览版](#opt-in-to-public-preview)。

## <a name="the-preview-experience"></a>预览体验

预览体验有三个方面。

### <a name="publish-enterprise-site-list-to-the-cloud"></a>将企业站点列表发布到云

管理员可以将一个或多个站点列表发布到经过身份验证的终结点，Microsoft Edge 租户中的客户端可以下载该终结点以获得 IE 模式体验。 管理员可以将现有企业站点列表 XML 导入 Microsoft 365 管理中心的Microsoft Edge 站点列表体验，然后将其发布到云位置。 

### <a name="associate-the-cloud-hosted-site-list-with-microsoft-edge"></a>将云托管站点列表与 Microsoft Edge 关联

使用 Microsoft Edge 版本 93，管理员可以使用[InternetExplorerIntegrationCloudSiteList](/docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationcloudsitelist)设置配置一个云托管站点列表，Microsoft Edge IE 模式可以使用这些列表。 用户必须登录 Microsoft Edge 客户端使用云中的站点列表。

> [!IMPORTANT]
> 配置此策略时，它将覆盖原始 [InternetExplorerIntegrationSiteList](/docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationsitelist) 策略。

### <a name="manage-site-list-contents-on-the-microsoft-365-admin-center"></a>管理 Microsoft 365 管理中心上的网站列表内容

管理员可以创建新列表或将现有网站列表导入到 Microsoft Edge 网站列表体验中。 他们可以添加、编辑、删除网站列表内容，并查看注释历史记录以跟踪对单个条目的更改。 下一部分介绍如何选择加入公共预览版，并访问Microsoft 365 管理中心的 Microsoft Edge 网站列表体验。

## <a name="opt-in-to-public-preview"></a>选择加入公共预览版

在公共预览版中，需要选择在 Microsoft 365 管理中心查看预览体验。 你必须是 Microsoft 365 的全局管理员，才能选择加入。

使用以下步骤更改组织接收 Microsoft 365 更新的方式。

> [!NOTE]
> 以下配置更改最多可能需要 24 小时才能在 Microsoft 365 中生效。 如果你在启用定向版本后选择退出该版本，你的用户可能会失去对尚未达到计划版本功能的访问权限。

1. 登录到[ Microsoft 365 管理中心，](https://admin.microsoft.com)然后转到 **设置 >组织设置**。 在 **组织配置文件** 选项卡下，选择 **发布首选项**。
2. 若要禁用定向发布，请选择 **标准发布**，然后选择 **保存更改**。
3. 若要为组织中所有用户启用定向发布，请选择 **面向所有人的定向发布**，然后选择 **保存更改**。
4. 若要为组织中某些人员启用定向发布，请选择 **所选用户的定向发布**，然后选择 **保存更改**。
5.  **选择用户** 一次添加一个用户，或 **上传用户** 批量添加。
6. 添加完用户后，选择 **保存更改**。

有关详细信息，请参阅[设置标准或定向发布选项 - Microsoft 365 管理员](/microsoft-365/admin/manage/release-options-in-office-365)

## <a name="publish-enterprise-site-list-to-the-cloud"></a>将企业站点列表发布到云

使用以下步骤作为创建网站列表、导入网站列表和发布网站列表的指南。 完成这些步骤之前，请登录 Microsoft 365 管理中心。

1. 若要访问[ Microsoft 365 管理中心](https://admin.microsoft.com)，请使用管理员帐户登录。
2. 在左侧导航窗格中，选择**设置 > 组织设置**。
3. 你将看到 ** Microsoft Edge 网站列表（预览版）** 选项。

### <a name="steps-to-create-a-site-list"></a>创建网站列表的步骤

1. 在组织设置页上，选择 ** Microsoft Edge 网站列表（预览版）**
2. 在生成的页面上，选择 **创建新列表**。
3. 输入**站点列表名称**和**说明**，然后选择**创建**。
4. 收到确认后，选择 **关闭面板**。 

### <a name="steps-to-import-a-site-list"></a>导入网站列表的步骤

1. 选择要填充的网站列表。
2. 在生成的页面上，选择 **导入列表**。
3. 在右侧面板上，选择**浏览**。
4. 选择要导入的文件，然后选择面板底部的**上传**。
5. 你可以浏览上传文件中 URL。 如果要选取其他文件，可以选择面板顶部的**上传其他文件**。 如果一切正常，请选择面板底部的**添加**。
6. 导入列表后，选择**关闭面板**。 

### <a name="steps-to-publish-a-site-list"></a>发布网站列表的步骤

1. 若要发布网站列表，请返回到 Microsoft Edge 网站列表级别。 选择网站列表名称上方痕迹导航,向上导航一级。
2. 在 Microsoft Edge 站点列表页面上，选择要发布到云的站点列表，然后选择**发布站点列表**。
3. 在右侧面板上，更新 **版本号** 并选择面板底部的**发布**。
4. 确认后，选择**关闭面板**。 
5.  **已发布状态**列、**上次发布时间**和**上次发布者**均已更新。

## <a name="associate-the-cloud-hosted-site-list-with-microsoft-edge"></a>将云托管站点列表与 Microsoft Edge 关联

使用以下步骤将云托管的站点列表与Microsoft Edge 关联。

1. 若要将设备配置为使用已发布的网站列表，请单击要分配给设备的站点列表。
2. 在生成的页面上，复制**网站列表 ID**。
3. 对于你选取的设备组，选择**已启用**，然后在[配置企业模式云站点列表](/deployedge/microsoft-edge-policies#internetexplorerintegrationcloudsitelist)策略中输入**站点列表 ID**。
4. 你可以从命令提示符运行** gpupdate/force** 以使用策略更新设备或等待组策略生效。 更新策略后，可以通过转到[ edge://compat/enterprise ](edge://compat/enterprise)来验证 Microsoft Edge 是否正在读取云站点列表。 你需要登录到 Microsoft Edge。

> [!NOTE]
> 首次发布网站列表并更新组策略后，需要重新启动 Microsoft Edge。 等待 60 秒或选择强制更新按钮[edge://compat/enterprise](edge://compat/enterprise)。 在向已关联的网站列表发布更新时，缓存中可能有较旧版本的网站列表。 此条目将在 60 秒后刷新。 有关详细信息，请参阅[请参阅如果用户注销 Microsoft Edge 会发生什么情况？](#what-happens-if-users-log-out-of-microsoft-edge)

## <a name="manage-site-list-contents-on-the-microsoft-365-admin-center"></a>管理 Microsoft 365 管理中心上的网站列表内容

可以添加单个网站条目、删除网站条目和查看注释更改历史记录。
如果混合方案要求将站点列表托管在本地，则可以从 Microsoft 365 管理中心导出站点列表。 使用以下步骤作为管理网站列表内容的指南。

### <a name="add-individual-sites-to-the-site-list"></a>将单个网站添加到网站列表

将单个网站添加到任何站点列表。 将网站添加到列表后，可以使用**筛选器**按钮（搜索输入区域旁边），查看列表更新。

1. 转到要添加网站的网站列表。
2. 选择**添加站点**。
3. 输入站点地址，并选取应该用于打开站点的引擎。 根据需要添加注释，然后选择**保存**。

   > [!NOTE]
   > 添加到已发布网站列表的任何条目的**状态**列将显示**添加挂起**。 如果通过选择屏幕顶部的 ** Microsoft Edge 网站列表**导航到网站列表 ，则会看到 **已发布状态** 列显示 **待发布更改**，以指示需要发布站点列表的最新更新，以便用户接收更新。 可以使用 **筛选器** 按钮 _（搜索框旁边）_ 选择添加挂起，以查看所有正在挂起发布的已添加条目。

### <a name="view-the-change-history-for-site-entries"></a>查看网站条目更改历史记录

1. 选择要查看其更改历史记录的网站条目，然后选择**查看注释**。

### <a name="delete-a-site-from-the-site-list"></a>从站点列表中删除站点

使用以下步骤删除站点条目。

1. 选取希望要删除站点的站点列表条目。 选择**删除站点**。
2. 选择窗格底部的 **删除**。
3. 看到已确认删除站点条目后，它将一直保留在列表中，直到站点列表发布到云位置。 可以通过选择筛选按钮并筛选处于**删除挂起**状态的网站，在发布之前查看已删除网站的列表。

   > [!NOTE]
   > 从已发布网站列表中删除任何条目的**状态**列将显示**删除挂起**。 如果通过选择屏幕顶部的** Microsoft Edge 网站列表**导航到网站列表 ，则会看到**已发布状态**列显示**待发布更改**，以指示需要发布站点列表的最新更新，以便用户接收更新。可以使用**筛选**按钮 _（搜索框旁边）_ 选择挂起的删除，以查看正在挂起发布的所有已删除条目。

### <a name="export-a-site-list"></a>导出网站列表

在某些情况下，需要导出网站列表。 例如，如果无法将站点列表马上移动到云中，或者你需要维护包含云和本地站点列表的混合环境。 可以使用云站点列表管理体验来管理中央位置中站点列表的更新，以及将站点列表导出到本地主机。

1. 在 Microsoft Edge 站点列表页上，选择要导出的站点列表。
2. 在生成的页面上，你将看到站点列表条目和**导出列表**选项。
3. 选择**导出列表**，以下载站点列表 XML 文件。

## <a name="faq"></a>常见问题

### <a name="when-i-select-microsoft-edge-site-lists-and-try-to-create-a-new-list-i-get-this-error---request-failed-with-status-code-500-why-is-that"></a>在选择“Microsoft Edge 站点列表”并尝试创建新列表时，收到此错误：“请求失败，状态代码为 500”。 为什么？

Microsoft Edge 站点列表将其数据和配置存储在与 Exchange Online、SharePoint Online、Teams 和 Azure Active Directory 等企业云服务共享的服务基础结构中。 在极少数情况下，当 Microsoft Edge 站点列表是使用此基础结构的第一项功能时，预配可能需要一些时间。 在这些情况下，来自 Microsoft 365 管理中心的初始请求将失败。 当请求失败时，会向预配系统发送警报以解决该问题。 通常，预配将在三天内完成。 因此，如果收到此错误，请在几天后重试，然后创建一个新列表。 如果仍无法创建新列表，或者如需紧急协助，请联系 Microsoft 支持部门。

### <a name="can-users-who-havent-signed-in-to-microsoft-edge-download-the-site-list"></a>尚未登录 Microsoft Edge 的用户能否下载站点列表？

否，用户必须登录到浏览器以下载云托管的站点列表。 可以配置策略以允许隐式登录，以防止用户体验中断。 有关详细信息，请参阅 [ImplicitSignInEnabled](/docs.microsoft.com/DeployEdge/microsoft-edge-policies#implicitsigninenabled)。

### <a name="what-is-the-default-refresh-interval-after-updates-are-made-to-site-list-contents"></a>对站点列表内容进行更新后，默认刷新间隔是什么？

站点列表每两个小时在 Microsoft Edge 刷新一次。 你可以更改[NavigationDelayForInitialSiteListDownloadTimeout](/docs.microsoft.com/deployedge/microsoft-edge-policies#navigationdelayforinitialsitelistdownloadtimeout)策略的此间隔。 最小刷新间隔为 30 分钟。

### <a name="what-happens-if-users-log-out-of-microsoft-edge"></a>如果用户注销 Microsoft Edge 会发生什么情况？

首次下载时，需要显式浏览器登录，以访问站点列表。 在用户登录后注销的情况下，网站列表缓存在 Microsoft Edge 中。 即使用户从其 Azure Active Directory （Azure AD） 帐户注销 Microsoft Edge，列表也会保持缓存状态。 配置云站点列表策略时，Microsoft Edge不会尝试回退到非云下载位置。 Microsoft Edge 尝试在下列时间更新缓存的站点列表（请注意，如果用户未登录到 Microsoft Edge，所有尝试都将失败）：

- 重新启动浏览器后 60 秒。 如果需要缩短 60 秒启动延迟，可以使用 [NavigationDelayForInitialSiteListDownloadTimeout](/deployedge/microsoft-edge-policies#navigationdelayforinitialsitelistdownloadtimeout) 策略更改延迟时间。
- 每两小时运行 Microsoft Edge 一次。

## <a name="support-and-feedback"></a>支持和反馈

在公共预览版中，现有 [ Microsoft Premier Support ](https://www.microsoft.com/en-us/unifiedsupport/premier) 合同涵盖了云站点列表管理体验。 你可以联系 Microsoft 支持人员报告问题或反馈。 还可以在我们的[ TechCommunity 论坛](https://techcommunity.microsoft.com/t5/enterprise/bd-p/EdgeInsiderEnterprise)中留下反馈。

## <a name="see-also"></a>另请参阅

- [关于 IE 模式](./edge-ie-mode.md)
- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
  
