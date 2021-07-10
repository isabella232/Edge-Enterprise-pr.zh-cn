---
title: 重置 Microsoft Edge 数据
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 06/28/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 如何在云中重置 Microsoft Edge 数据
ms.openlocfilehash: 19ee60926e36371bd710937fcafc43de7ea035f4
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642038"
---
# <a name="reset-microsoft-edge-data-in-the-cloud"></a><span data-ttu-id="652ea-103">重置云中的 Microsoft Edge 数据</span><span class="sxs-lookup"><span data-stu-id="652ea-103">Reset Microsoft Edge data in the cloud</span></span>

<span data-ttu-id="652ea-104">本文介绍了在云中重置 Microsoft Edge 数据的步骤。</span><span class="sxs-lookup"><span data-stu-id="652ea-104">This article describes the steps for resetting your Microsoft Edge data in the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="652ea-105">除非另有说明，否则本文适用于 Microsoft Edge 版本 88 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="652ea-105">This article applies to Microsoft Edge version 88 or later unless otherwise noted.</span></span>

> [!NOTE]
> <span data-ttu-id="652ea-106">如果租户位于 GCC Mod 环境中，则租户管理员需要向 Microsoft 提交支持请求以重置数据。</span><span class="sxs-lookup"><span data-stu-id="652ea-106">If your tenant is in a GCC Mod environment, your tenant admin will need to file a support request with Microsoft to reset your data.</span></span>

## <a name="overview"></a><span data-ttu-id="652ea-107">概述</span><span class="sxs-lookup"><span data-stu-id="652ea-107">Overview</span></span>

<span data-ttu-id="652ea-108">在某些情况下，你想要在云中重置 Microsoft Edge 数据。</span><span class="sxs-lookup"><span data-stu-id="652ea-108">There are situations in which you want to reset your Microsoft Edge data in the cloud.</span></span> <span data-ttu-id="652ea-109">例如，您希望同步数据，但 Microsoft Edge 报告无法同步数据。</span><span class="sxs-lookup"><span data-stu-id="652ea-109">For example,  you want to synchronize your data, but Microsoft Edge reports that it is unable to synchronize the data.</span></span> <span data-ttu-id="652ea-110">或者，你可能希望确保你的数据已从 Microsoft 云中删除。</span><span class="sxs-lookup"><span data-stu-id="652ea-110">Or you might want to make sure that your data is removed from Microsoft’s cloud.</span></span> <span data-ttu-id="652ea-111">在这两种情况下，Microsoft Edge 都允许您执行云数据重置。</span><span class="sxs-lookup"><span data-stu-id="652ea-111">In both cases, Microsoft Edge lets you perform a cloud data reset.</span></span>

## <a name="back-up-your-favorites"></a><span data-ttu-id="652ea-112">备份收藏夹</span><span class="sxs-lookup"><span data-stu-id="652ea-112">Back up your favorites</span></span>

<span data-ttu-id="652ea-113">在执行重置之前，我们建议你备份收藏夹。</span><span class="sxs-lookup"><span data-stu-id="652ea-113">Before performing a reset, we recommend that you back up your favorites.</span></span> <span data-ttu-id="652ea-114">使用以下步骤备份收藏夹。</span><span class="sxs-lookup"><span data-stu-id="652ea-114">Use the following steps to back up your favorites.</span></span>

1. <span data-ttu-id="652ea-115">在 Microsoft Edge 中，选择 **“设置和更多”>“收藏夹”>“更多选项”>“导出收藏夹”**。</span><span class="sxs-lookup"><span data-stu-id="652ea-115">In Microsoft Edge, select **Settings and more > Favorites > More options > Export favorites**.</span></span>
2. <span data-ttu-id="652ea-116">选择用来保存收藏夹的文件。</span><span class="sxs-lookup"><span data-stu-id="652ea-116">Choose the file to where you want to save your favorites.</span></span> <span data-ttu-id="652ea-117">可以键入自己的文件名，或使用 Microsoft Edge 默认提供的名称 “favorites_month_day_year.html” 作为文件名。</span><span class="sxs-lookup"><span data-stu-id="652ea-117">You can type your own filename or use the name that Microsoft Edge provides by default,  "favorites_month_day_year.html" as a filename.</span></span> <span data-ttu-id="652ea-118">例如，”favorites_12_17_20.html”。</span><span class="sxs-lookup"><span data-stu-id="652ea-118">For example, "favorites_12_17_20.html".</span></span> <span data-ttu-id="652ea-119">如果稍后需要还原收藏夹，可以从该文件中还原。</span><span class="sxs-lookup"><span data-stu-id="652ea-119">If you need to restore your favorites later, you can do so from that file.</span></span>
3. <span data-ttu-id="652ea-120">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="652ea-120">Click **Save**.</span></span>

## <a name="perform-a-reset-to-fix-a-synchronization-problem"></a><span data-ttu-id="652ea-121">执行重置以修复同步问题</span><span class="sxs-lookup"><span data-stu-id="652ea-121">Perform a reset to fix a synchronization problem</span></span>

<span data-ttu-id="652ea-122">如果 Microsoft Edge 报告无法同步数据，并建议重置数据，请执行重置以修复此问题。</span><span class="sxs-lookup"><span data-stu-id="652ea-122">If Microsoft Edge reports that it can't synchronize your data and suggests resetting your data, perform a reset to fix the problem.</span></span>

<span data-ttu-id="652ea-123">使用以下步骤执行重置。</span><span class="sxs-lookup"><span data-stu-id="652ea-123">Use the following steps to do a reset.</span></span>

1. <span data-ttu-id="652ea-124">首先，确保已在所有设备（包括移动设备）上退出 Microsoft Edge，但执行重置的设备除外。</span><span class="sxs-lookup"><span data-stu-id="652ea-124">First, make sure that you’re signed out of Microsoft Edge on all your devices, including your mobile devices, except the device you are performing the reset on.</span></span> <span data-ttu-id="652ea-125">若要注销 Microsoft Edge，请选择 **“设置和更多”>“设置”>“注销”**。退出时，不要选择从本地设备清除收藏夹和设置等选项。</span><span class="sxs-lookup"><span data-stu-id="652ea-125">To sign out of Microsoft Edge, select **Settings and more > Settings > Sign out**. When signing out, do not select the option to clear favorites, settings, and etc. from your local device.</span></span>
2. <span data-ttu-id="652ea-126">注销所有其他设备后，在桌面上打开 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="652ea-126">After you sign out of all your other devices, open Microsoft Edge on your desktop.</span></span> <span data-ttu-id="652ea-127">**选择“设置和更多”>“同步”>“重置同步”**。在生成的对话框中，选择在重置数据后恢复同步，然后选择 **“重置”**。</span><span class="sxs-lookup"><span data-stu-id="652ea-127">**Select Settings and more > Sync > Reset sync**. In the resulting dialog box, choose to resume sync after resetting data, and then select **Reset**.</span></span>

## <a name="perform-a-reset-to-remove-your-data-from-microsofts-cloud"></a><span data-ttu-id="652ea-128">执行重置以从 Microsoft 云中删除数据</span><span class="sxs-lookup"><span data-stu-id="652ea-128">Perform a reset to remove your data from Microsoft’s cloud</span></span>

<span data-ttu-id="652ea-129">如果要从 Microsoft 云中删除数据，请使用以下步骤执行重置。</span><span class="sxs-lookup"><span data-stu-id="652ea-129">If you want to remove your data from Microsoft’s cloud, use the following steps to do a reset.</span></span>

1. <span data-ttu-id="652ea-130">在设备上停止同步（除要执行重置的设备以外）。</span><span class="sxs-lookup"><span data-stu-id="652ea-130">Stop synchronization on devices except the device you are performing the reset on.</span></span>  <span data-ttu-id="652ea-131">在 Microsoft Edge 中，选择 **“设置和更多”>“设置”>“同步”>“关闭同步”**。</span><span class="sxs-lookup"><span data-stu-id="652ea-131">In Microsoft Edge, select **Settings and more > Settings > Sync > Turn off sync**.</span></span>  
2. <span data-ttu-id="652ea-132">停止同步后，选择 **“设置和更多“>“同步”>“重置同步”**。在生成的对话框中，**不要** 选择在重置数据后恢复同步。</span><span class="sxs-lookup"><span data-stu-id="652ea-132">After you stop synchronization, select **Settings and more > Sync > Reset sync**. In the resulting dialog box, **do not** choose to resume sync after resetting data.</span></span> <span data-ttu-id="652ea-133">选择 **“重置”**。</span><span class="sxs-lookup"><span data-stu-id="652ea-133">Select **Reset**.</span></span>

## <a name="what-to-expect-during-and-after-a-data-reset"></a><span data-ttu-id="652ea-134">数据重置期间和之后预期结果</span><span class="sxs-lookup"><span data-stu-id="652ea-134">What to expect during and after a data reset</span></span>

<span data-ttu-id="652ea-135">数据重置可能需要几秒钟到几分钟，具体取决于你在 Microsoft 云中存储了多少数据。</span><span class="sxs-lookup"><span data-stu-id="652ea-135">A data reset can take from a few seconds to a few minutes, depending on how much data you have stored in Microsoft’s cloud.</span></span> <span data-ttu-id="652ea-136">在某些情况下，你可能会看到一条消息，指出无法完成重置，并建议再次重置。</span><span class="sxs-lookup"><span data-stu-id="652ea-136">In some cases, you might see a message saying that a reset could not be completed and a suggestion to reset again.</span></span> <span data-ttu-id="652ea-137">在这种情况下，请等待几小时，然后再次尝试重置数据。</span><span class="sxs-lookup"><span data-stu-id="652ea-137">In this case, wait a few hours and try to reset the data again.</span></span> <span data-ttu-id="652ea-138">如果仍无法重置数据，请与 Microsoft Edge 支持部门联系。</span><span class="sxs-lookup"><span data-stu-id="652ea-138">If you are still unable to reset your data, contact Microsoft Edge Support.</span></span>

<span data-ttu-id="652ea-139">成功完成数据重置后，如果选择在重置后恢复同步，数据将再次从设备同步。</span><span class="sxs-lookup"><span data-stu-id="652ea-139">After a data reset has been successfully completed, data will once again synchronize from your device if you chose to resume sync after the reset.</span></span> <span data-ttu-id="652ea-140">如果你想要从这些设备同步，则需要在其他设备上重新登录。</span><span class="sxs-lookup"><span data-stu-id="652ea-140">You will need to sign back in on your other devices if you want to sync from those devices.</span></span> <span data-ttu-id="652ea-141">但是，如果未选择恢复同步，则 Microsoft Edge 数据将从云中删除，并且数据将不再同步。</span><span class="sxs-lookup"><span data-stu-id="652ea-141">However, if you didn’t choose to resume sync, then your Microsoft Edge data is removed from the cloud and your data will no longer synchronize.</span></span>

## <a name="see-also"></a><span data-ttu-id="652ea-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="652ea-142">See also</span></span>

- [<span data-ttu-id="652ea-143">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="652ea-143">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="652ea-144">Microsoft Edge Enterprise Sync</span><span class="sxs-lookup"><span data-stu-id="652ea-144">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)