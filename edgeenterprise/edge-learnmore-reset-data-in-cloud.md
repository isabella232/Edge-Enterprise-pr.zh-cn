---
title: 重置 Microsoft Edge 数据
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 12/21/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 如何在云中重置 Microsoft Edge 数据
ms.openlocfilehash: 638abe5dc80aafa64d05bccd4a0f5542fa13860c
ms.sourcegitcommit: 51f43d220503547f24b56ff3dda5373c5aca6b57
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2020
ms.locfileid: "11238018"
---
# <span data-ttu-id="ea08e-103">重置云中的 Microsoft Edge 数据</span><span class="sxs-lookup"><span data-stu-id="ea08e-103">Reset Microsoft Edge data in the cloud</span></span>

<span data-ttu-id="ea08e-104">本文介绍了在云中重置 Microsoft Edge 数据的步骤。</span><span class="sxs-lookup"><span data-stu-id="ea08e-104">This article describes the steps for resetting your Microsoft Edge data in the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="ea08e-105">除非另有说明，否则本文适用于 Microsoft Edge 版本 88 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="ea08e-105">This article applies to Microsoft Edge version 88 or later unless otherwise noted.</span></span>

## <span data-ttu-id="ea08e-106">概述</span><span class="sxs-lookup"><span data-stu-id="ea08e-106">Overview</span></span>

<span data-ttu-id="ea08e-107">在某些情况下，你想要在云中重置 Microsoft Edge 数据。</span><span class="sxs-lookup"><span data-stu-id="ea08e-107">There are situations in which you want to reset your Microsoft Edge data in the cloud.</span></span> <span data-ttu-id="ea08e-108">例如，您希望同步数据，但 Microsoft Edge 报告无法同步数据。</span><span class="sxs-lookup"><span data-stu-id="ea08e-108">For example,  you want to synchronize your data, but Microsoft Edge reports that it is unable to synchronize the data.</span></span> <span data-ttu-id="ea08e-109">或者，你可能希望确保你的数据已从 Microsoft 云中删除。</span><span class="sxs-lookup"><span data-stu-id="ea08e-109">Or you might want to make sure that your data is removed from Microsoft’s cloud.</span></span> <span data-ttu-id="ea08e-110">在这两种情况下，Microsoft Edge 都允许您执行云数据重置。</span><span class="sxs-lookup"><span data-stu-id="ea08e-110">In both cases, Microsoft Edge lets you perform a cloud data reset.</span></span>

## <span data-ttu-id="ea08e-111">备份收藏夹</span><span class="sxs-lookup"><span data-stu-id="ea08e-111">Back up your favorites</span></span>

<span data-ttu-id="ea08e-112">在执行重置之前，我们建议你备份收藏夹。</span><span class="sxs-lookup"><span data-stu-id="ea08e-112">Before performing a reset, we recommend that you back up your favorites.</span></span> <span data-ttu-id="ea08e-113">使用以下步骤备份收藏夹。</span><span class="sxs-lookup"><span data-stu-id="ea08e-113">Use the following steps to back up your favorites.</span></span>

1. <span data-ttu-id="ea08e-114">在 Microsoft Edge 中，选择 **“设置和更多”>“收藏夹”>“更多选项”>“导出收藏夹”**。</span><span class="sxs-lookup"><span data-stu-id="ea08e-114">In Microsoft Edge, select **Settings and more > Favorites > More options > Export favorites**.</span></span>
2. <span data-ttu-id="ea08e-115">选择用来保存收藏夹的文件。</span><span class="sxs-lookup"><span data-stu-id="ea08e-115">Choose the file to where you want to save your favorites.</span></span> <span data-ttu-id="ea08e-116">可以键入自己的文件名，或使用 Microsoft Edge 默认提供的名称 “favorites_month_day_year.html” 作为文件名。</span><span class="sxs-lookup"><span data-stu-id="ea08e-116">You can type your own filename or use the name that Microsoft Edge provides by default,  "favorites_month_day_year.html" as a filename.</span></span> <span data-ttu-id="ea08e-117">例如，”favorites_12_17_20.html”。</span><span class="sxs-lookup"><span data-stu-id="ea08e-117">For example, "favorites_12_17_20.html".</span></span> <span data-ttu-id="ea08e-118">如果稍后需要还原收藏夹，可以从该文件中还原。</span><span class="sxs-lookup"><span data-stu-id="ea08e-118">If you need to restore your favorites later, you can do so from that file.</span></span>
3. <span data-ttu-id="ea08e-119">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="ea08e-119">Click **Save**.</span></span>

## <span data-ttu-id="ea08e-120">执行重置以修复同步问题</span><span class="sxs-lookup"><span data-stu-id="ea08e-120">Perform a reset to fix a synchronization problem</span></span>

<span data-ttu-id="ea08e-121">如果 Microsoft Edge 报告无法同步数据，并建议重置数据，请执行重置以修复此问题。</span><span class="sxs-lookup"><span data-stu-id="ea08e-121">If Microsoft Edge reports that it can't synchronize your data and suggests resetting your data, perform a reset to fix the problem.</span></span>

<span data-ttu-id="ea08e-122">使用以下步骤执行重置。</span><span class="sxs-lookup"><span data-stu-id="ea08e-122">Use the following steps to do a reset.</span></span>

1. <span data-ttu-id="ea08e-123">首先，确保已在所有设备（包括移动设备）上退出 Microsoft Edge，但执行重置的设备除外。</span><span class="sxs-lookup"><span data-stu-id="ea08e-123">First, make sure that you’re signed out of Microsoft Edge on all your devices, including your mobile devices, except the device you are performing the reset on.</span></span> <span data-ttu-id="ea08e-124">若要注销 Microsoft Edge，请选择 **“设置和更多”>“设置”>“注销”**。退出时，不要选择从本地设备清除收藏夹和设置等选项。</span><span class="sxs-lookup"><span data-stu-id="ea08e-124">To sign out of Microsoft Edge, select **Settings and more > Settings > Sign out**. When signing out, do not select the option to clear favorites, settings, and etc. from your local device.</span></span>
2. <span data-ttu-id="ea08e-125">注销所有其他设备后，在桌面上打开 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="ea08e-125">After you sign out of all your other devices, open Microsoft Edge on your desktop.</span></span> <span data-ttu-id="ea08e-126">**选择“设置和更多”>“同步”>“重置同步”**。在生成的对话框中，选择在重置数据后恢复同步，然后选择 **“重置”**。</span><span class="sxs-lookup"><span data-stu-id="ea08e-126">**Select Settings and more > Sync > Reset sync**. In the resulting dialog box, choose to resume sync after resetting data, and then select **Reset**.</span></span>

## <span data-ttu-id="ea08e-127">执行重置以从 Microsoft 云中删除数据</span><span class="sxs-lookup"><span data-stu-id="ea08e-127">Perform a reset to remove your data from Microsoft’s cloud</span></span>

<span data-ttu-id="ea08e-128">如果要从 Microsoft 云中删除数据，请使用以下步骤执行重置。</span><span class="sxs-lookup"><span data-stu-id="ea08e-128">If you want to remove your data from Microsoft’s cloud, use the following steps to do a reset.</span></span>

1. <span data-ttu-id="ea08e-129">在设备上停止同步（除要执行重置的设备以外）。</span><span class="sxs-lookup"><span data-stu-id="ea08e-129">Stop synchronization on devices except the device you are performing the reset on.</span></span>  <span data-ttu-id="ea08e-130">在 Microsoft Edge 中，选择 **“设置和更多”>“设置”>“同步”>“关闭同步”**。</span><span class="sxs-lookup"><span data-stu-id="ea08e-130">In Microsoft Edge, select **Settings and more > Settings > Sync > Turn off sync**.</span></span>  
2. <span data-ttu-id="ea08e-131">停止同步后，选择 **“设置和更多“>“同步”>“重置同步”**。在生成的对话框中，**不要** 选择在重置数据后恢复同步。</span><span class="sxs-lookup"><span data-stu-id="ea08e-131">After you stop synchronization, select **Settings and more > Sync > Reset sync**. In the resulting dialog box, **do not** choose to resume sync after resetting data.</span></span> <span data-ttu-id="ea08e-132">选择 **“重置”**。</span><span class="sxs-lookup"><span data-stu-id="ea08e-132">Select **Reset**.</span></span>

## <span data-ttu-id="ea08e-133">数据重置期间和之后预期结果</span><span class="sxs-lookup"><span data-stu-id="ea08e-133">What to expect during and after a data reset</span></span>

<span data-ttu-id="ea08e-134">数据重置可能需要几秒钟到几分钟，具体取决于你在 Microsoft 云中存储了多少数据。</span><span class="sxs-lookup"><span data-stu-id="ea08e-134">A data reset can take from a few seconds to a few minutes, depending on how much data you have stored in Microsoft’s cloud.</span></span> <span data-ttu-id="ea08e-135">在某些情况下，你可能会看到一条消息，指出无法完成重置，并建议再次重置。</span><span class="sxs-lookup"><span data-stu-id="ea08e-135">In some cases, you might see a message saying that a reset could not be completed and a suggestion to reset again.</span></span> <span data-ttu-id="ea08e-136">在这种情况下，请等待几小时，然后再次尝试重置数据。</span><span class="sxs-lookup"><span data-stu-id="ea08e-136">In this case, wait a few hours and try to reset the data again.</span></span> <span data-ttu-id="ea08e-137">如果仍无法重置数据，请与 Microsoft Edge 支持部门联系。</span><span class="sxs-lookup"><span data-stu-id="ea08e-137">If you are still unable to reset your data, contact Microsoft Edge Support.</span></span>

<span data-ttu-id="ea08e-138">成功完成数据重置后，如果选择在重置后恢复同步，数据将再次从设备同步。</span><span class="sxs-lookup"><span data-stu-id="ea08e-138">After a data reset has been successfully completed, data will once again synchronize from your device if you chose to resume sync after the reset.</span></span> <span data-ttu-id="ea08e-139">如果你想要从这些设备同步，则需要在其他设备上重新登录。</span><span class="sxs-lookup"><span data-stu-id="ea08e-139">You will need to sign back in on your other devices if you want to sync from those devices.</span></span> <span data-ttu-id="ea08e-140">但是，如果未选择恢复同步，则 Microsoft Edge 数据将从云中删除，并且数据将不再同步。</span><span class="sxs-lookup"><span data-stu-id="ea08e-140">However, if you didn’t choose to resume sync, then your Microsoft Edge data is removed from the cloud and your data will no longer synchronize.</span></span>

## <span data-ttu-id="ea08e-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea08e-141">See also</span></span>

- [<span data-ttu-id="ea08e-142">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="ea08e-142">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="ea08e-143">Microsoft Edge Enterprise Sync</span><span class="sxs-lookup"><span data-stu-id="ea08e-143">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)