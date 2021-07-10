---
title: 预配 Microsoft Edge 收藏夹
ms.author: capoon
author: dan-wesley
manager: abutcher
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 预配 Microsoft Edge 收藏夹
ms.openlocfilehash: 2d75e9c22a8aa9cc70d8b96c280934137396620a
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642178"
---
# <a name="provision-favorites-for-microsoft-edge"></a><span data-ttu-id="1eae8-103">预配 Microsoft Edge 收藏夹</span><span class="sxs-lookup"><span data-stu-id="1eae8-103">Provision favorites for Microsoft Edge</span></span>

<span data-ttu-id="1eae8-104">根据客户反馈，我们改进了预配收藏夹。</span><span class="sxs-lookup"><span data-stu-id="1eae8-104">Based on customer feedback, we've made improvements to provisioning favorites.</span></span> <span data-ttu-id="1eae8-105">从 Microsoft Edge 版本 85 开始，管理员无需再手动创建文件来设置收藏夹。</span><span class="sxs-lookup"><span data-stu-id="1eae8-105">Starting with Microsoft Edge version 85, Admins no longer have to manually craft a file to provision favorites.</span></span> <span data-ttu-id="1eae8-106">管理员可使用 Microsoft Edge 用户界面添加收藏夹和文件夹，以便生成可导出到组策略的文件。</span><span class="sxs-lookup"><span data-stu-id="1eae8-106">Admins can add favorites and folders using the Microsoft Edge UI to generate a file that can be exported to a group policy.</span></span>

<span data-ttu-id="1eae8-107">本文介绍如何为你的组织设置一组收藏夹和文件夹。</span><span class="sxs-lookup"><span data-stu-id="1eae8-107">This article describes how to provision a set of favorites and folders for your organization.</span></span> <span data-ttu-id="1eae8-108">可使用[“配置收藏夹”](//DeployEdge/microsoft-edge-policies#configure-favorites)策略来设置收藏夹和文件夹。</span><span class="sxs-lookup"><span data-stu-id="1eae8-108">You can use the [Configure favorites](//DeployEdge/microsoft-edge-policies#configure-favorites) policy to provision favorites and folders.</span></span>

> [!NOTE]
> <span data-ttu-id="1eae8-109">本文适用于 Microsoft Edge 版本 85 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="1eae8-109">This article applies to Microsoft Edge version 85 or later.</span></span>

## <a name="prerequisites-and-recommendations"></a><span data-ttu-id="1eae8-110">先决条件和建议</span><span class="sxs-lookup"><span data-stu-id="1eae8-110">Prerequisites and recommendations</span></span>

- <span data-ttu-id="1eae8-111">Microsoft Edge 版本 85 为组策略安装了适当的管理模板。</span><span class="sxs-lookup"><span data-stu-id="1eae8-111">Microsoft Edge version 85 with the appropriate administrative template installed for group policies.</span></span>
- <span data-ttu-id="1eae8-112">建议在 Microsoft Edge 中使用新的配置文件来设置这些收藏夹。</span><span class="sxs-lookup"><span data-stu-id="1eae8-112">We recommend that you use a new profile in Microsoft Edge to provision these favorites.</span></span> <span data-ttu-id="1eae8-113">将在导出中包含与该配置文件一起保存的所有收藏夹。</span><span class="sxs-lookup"><span data-stu-id="1eae8-113">All favorites that are saved with the profile will be included in the export.</span></span>  

## <a name="provision-favorites-and-folders"></a><span data-ttu-id="1eae8-114">预配收藏夹和文件夹</span><span class="sxs-lookup"><span data-stu-id="1eae8-114">Provision favorites and folders</span></span>

<span data-ttu-id="1eae8-115">使用以下步骤为用户预配收藏夹和文件夹。</span><span class="sxs-lookup"><span data-stu-id="1eae8-115">Use the following steps to provision favorites and folders for your users.</span></span>

1. <span data-ttu-id="1eae8-116">转到 Microsoft Edge 地址栏并键入以下 URL： *edge://flags/#edge-favorites-admin-export*。</span><span class="sxs-lookup"><span data-stu-id="1eae8-116">Go to the Microsoft Edge address bar and type this URL: *edge://flags/#edge-favorites-admin-export*.</span></span>
2. <span data-ttu-id="1eae8-117">在 **“为管理员导出收藏夹配置”** 下，从下拉列表中选择 **“启用”** ，然后单击 **“重新启动”**。</span><span class="sxs-lookup"><span data-stu-id="1eae8-117">Under **Favorites configuration export for administrators**, pick **Enabled** from the dropdown list and then click **Restart**.</span></span>

3. <span data-ttu-id="1eae8-118">转到**收藏** 页面 *edge://favorites*，添加你想要预配的收藏夹和文件夹。</span><span class="sxs-lookup"><span data-stu-id="1eae8-118">Go to the **Favorites** page at *edge://favorites* so you can add the favorites and folders that you want to provision.</span></span>

<!--
4. On the **Favorites bar**, click **Add folder**. The folder structure of favorites that are set in the profile you're using will be reflected in the folder you provision for your users. The next screenshot shows "Managed favorites", the folder we'll use to provision favorites.

   ![Add a folder](media/edge-learnmore-provision-favorites/provision-favorites-add-folder.png)

   > [!TIP]
   > Add existing folders that contain favorites you want to provision for your users.

5. Select "Managed favorites" and then click **Add favorite**. The next screenshot shows the favorite we've added.

   ![Add a favorite](media/edge-learnmore-provision-favorites/provision-favorites-add-favorite.png)-->

4. <span data-ttu-id="1eae8-119">添加完收藏夹和文件夹后，可将其导出，以便 **“配置收藏夹”** 策略进行使用。</span><span class="sxs-lookup"><span data-stu-id="1eae8-119">When you finish adding favorites and folders you'll export them so they can be used by the **Configure favorites** policy.</span></span> <span data-ttu-id="1eae8-120">转到地址栏，导航到 *edge://favorites*，单击省略号 **“...”**，然后选择 **“导出收藏夹配置”**。</span><span class="sxs-lookup"><span data-stu-id="1eae8-120">Go to the address bar and navigate to *edge://favorites*, click the ellipsis "**…**" and choose **Export favorites configuration**.</span></span> <span data-ttu-id="1eae8-121">下一个屏幕截图将显示设置收藏夹时的选项。</span><span class="sxs-lookup"><span data-stu-id="1eae8-121">The next screenshot shows the options you have when provisioning favorites.</span></span>

   ![使用收藏夹的菜单选项。](media/edge-learnmore-provision-favorites/provision-favorites-menu-options.png)

5. <span data-ttu-id="1eae8-123">在 **“导出收藏夹配置”** 下为用户将看到的文件夹提供一个名称。</span><span class="sxs-lookup"><span data-stu-id="1eae8-123">Under **Export your favorites configuration** you provide a name for the folder that your users will see.</span></span> <span data-ttu-id="1eae8-124">键入文件夹名称，然后选择要使用的平台格式。</span><span class="sxs-lookup"><span data-stu-id="1eae8-124">Type the Folder name and pick the Platform format you want to use.</span></span> <span data-ttu-id="1eae8-125">单击 **“复制到剪贴板”**。</span><span class="sxs-lookup"><span data-stu-id="1eae8-125">Click **Copy to clipboard**.</span></span> <span data-ttu-id="1eae8-126">下一个屏幕截图将显示文件夹名称为“托管收藏夹”，并且平台是 Windows。</span><span class="sxs-lookup"><span data-stu-id="1eae8-126">The next screenshot shows "Managed favorites" for the folder name and the platform is Windows.</span></span>

   ![将收藏夹导出到 Windows 文件夹的对话框。](media/edge-learnmore-provision-favorites/provision-favorites-export.png)

6. <span data-ttu-id="1eae8-128">打开组策略编辑器，导航到 *“计算机配置/管理模板/”* 并选择 **“配置收藏夹”**。</span><span class="sxs-lookup"><span data-stu-id="1eae8-128">Open the Group Policy Editor, navigate to *Computer Configuration/Administrative Templates/* and pick **Configure Favorites**.</span></span> <span data-ttu-id="1eae8-129">启用“配置收藏夹”策略。</span><span class="sxs-lookup"><span data-stu-id="1eae8-129">Enable the "Configure Favorites" policy.</span></span> <span data-ttu-id="1eae8-130">在**选项下：**，将导出的内容粘贴到配置收藏夹文本区域，然后单击 **“应用”**。</span><span class="sxs-lookup"><span data-stu-id="1eae8-130">Under **Options:**, paste the exported contents in the Configure favorites text area then click **Apply**.</span></span> <span data-ttu-id="1eae8-131">下一个屏幕截图显示了步骤 5 中的“托管收藏夹”文件夹的示例。</span><span class="sxs-lookup"><span data-stu-id="1eae8-131">The next screenshot shows an example of the "Managed favorites" folder from step 5.</span></span>

   ![使用 gpedit 启用并配置“配置收藏夹”策略。](media/edge-learnmore-provision-favorites/provision-favorites-gpedit.png)

7. <span data-ttu-id="1eae8-133">单击 **“确定”** 或 **“应用”** 保存策略设置。</span><span class="sxs-lookup"><span data-stu-id="1eae8-133">Click **OK** or **Apply** to safe the policy settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="1eae8-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1eae8-134">See also</span></span>

- [<span data-ttu-id="1eae8-135">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="1eae8-135">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)