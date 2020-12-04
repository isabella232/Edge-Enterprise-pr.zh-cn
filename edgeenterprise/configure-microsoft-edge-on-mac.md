---
title: 使用 .plist 配置用于 macOS 的 Microsoft Edge
ms.author: brianalt
author: kelleyvice-msft
manager: laurawi
ms.date: 11/30/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 使用 .plist 在 macOS 上配置 Microsoft Edge 策略设置
ms.openlocfilehash: abe110ab3589cc9276f28590273ece2d372be3b8
ms.sourcegitcommit: ed6a5afabf909df87bec48671c4c47bcdfaeb7bc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "11194681"
---
# <span data-ttu-id="b3afa-103">使用 .plist 配置适用于 macOS 的 Microsoft Edge 策略设置</span><span class="sxs-lookup"><span data-stu-id="b3afa-103">Configure Microsoft Edge policy settings for macOS using a .plist</span></span>

<span data-ttu-id="b3afa-104">本文介绍了如何使用属性列表 (.plist) 文件在 macOS 上配置 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="b3afa-104">This article describes how to configure Microsoft Edge on macOS using a property list (.plist) file.</span></span> <span data-ttu-id="b3afa-105">你将了解如何创建此文件，然后将其部署到 Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="b3afa-105">You'll learn how to create this file and then deploy it to Microsoft Intune.</span></span>

<span data-ttu-id="b3afa-106">有关详细信息，请参阅[关于信息属性列表文件](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html)（Apple 的网站）和[自定义负载设置](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1)。</span><span class="sxs-lookup"><span data-stu-id="b3afa-106">For more information, see [About Information Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) (Apple's website) and [Custom payload settings](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1).</span></span>

> [!NOTE]
> <span data-ttu-id="b3afa-107">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="b3afa-107">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="b3afa-108">在 macOS 上配置 Microsoft Edge 策略</span><span class="sxs-lookup"><span data-stu-id="b3afa-108">Configure Microsoft Edge policies on macOS</span></span>

<span data-ttu-id="b3afa-109">第一步是创建 plist。</span><span class="sxs-lookup"><span data-stu-id="b3afa-109">The first step is to create your plist.</span></span> <span data-ttu-id="b3afa-110">你可以使用任何文本编辑器创建 plist 文件，也可以[使用终端创建配置文件](#create-a-configuration-profile-using-terminal)。</span><span class="sxs-lookup"><span data-stu-id="b3afa-110">You can create the plist file with any text editor or you can use [Terminal to create the configuration profile](#create-a-configuration-profile-using-terminal).</span></span> <span data-ttu-id="b3afa-111">但是，通过使用为你设置 XML 代码格式的工具，可以更加轻松地创建和编辑 plist 文件。</span><span class="sxs-lookup"><span data-stu-id="b3afa-111">However, it's easier to create and edit a plist file using a tool that formats the XML code for you.</span></span> <span data-ttu-id="b3afa-112">*Xcode* 是可从以下其中一个位置获取的免费集成开发环境：</span><span class="sxs-lookup"><span data-stu-id="b3afa-112">*Xcode* is a free integrated development environment that you can get from one of the following locations:</span></span>

- [<span data-ttu-id="b3afa-113">Apple 开发人员网站</span><span class="sxs-lookup"><span data-stu-id="b3afa-113">Apple developer website</span></span>](https://developer.apple.com/xcode/)
- [<span data-ttu-id="b3afa-114">Mac App Store</span><span class="sxs-lookup"><span data-stu-id="b3afa-114">Mac App Store</span></span>](https://apps.apple.com/app/xcode/id497799835?mt=12)

<span data-ttu-id="b3afa-115">有关受支持的策略及其首选项键名称的列表，请参阅 [Microsoft Edge 浏览器策略参考](microsoft-edge-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b3afa-115">For a list of supported policies and their preference key names, see [Microsoft Edge browser policies reference](microsoft-edge-policies.md).</span></span> <span data-ttu-id="b3afa-116">在可从 [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)下载的策略模板文件中，**示例**文件夹中有一个示例 plist (*itadminexample.plist*)。</span><span class="sxs-lookup"><span data-stu-id="b3afa-116">In the policy templates file, which can be downloaded from the [Microsoft Edge Enterprise landing page](https://aka.ms/EdgeEnterprise), there's an example plist (*itadminexample.plist*) in the **examples** folder.</span></span> <span data-ttu-id="b3afa-117">示例文件包含所有受支持的数据类型，你可以自定义这些数据类型以定义你的策略设置。</span><span class="sxs-lookup"><span data-stu-id="b3afa-117">The example file contains all supported data types that you can customize to define your policy settings.</span></span> 

<span data-ttu-id="b3afa-118">创建 plist 内容后，下一步是使用 Microsoft Edge 首选项域 *.com*。</span><span class="sxs-lookup"><span data-stu-id="b3afa-118">The next step after you create the contents of your plist, is to name it using the Microsoft Edge preference domain, *com.microsoft.Edge*.</span></span> <span data-ttu-id="b3afa-119">名称区分大小写，不应包含你的目标频道，因为它适用于所有 Microsoft Edge 频道。</span><span class="sxs-lookup"><span data-stu-id="b3afa-119">The name is case sensitive and should not include the channel you are targeting because it applies to all Microsoft Edge channels.</span></span> <span data-ttu-id="b3afa-120">plist 文件名必须是 **_com.microsoft.Edge.plist_**。</span><span class="sxs-lookup"><span data-stu-id="b3afa-120">The plist file name must be **_com.microsoft.Edge.plist_**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3afa-121">从版本 78.0.249.2 开始，macOS 上的所有 Microsoft Edge 频道都从 **com.microsoft.Edge** 首选项域中读取。</span><span class="sxs-lookup"><span data-stu-id="b3afa-121">Starting with build 78.0.249.2, all Microsoft Edge channels on macOS read from the **com.microsoft.Edge** preference domain.</span></span> <span data-ttu-id="b3afa-122">以前的所有版本都从特定于频道的域（如开发人员频道的 **com.microsoft.Edge.Dev**）中读取。</span><span class="sxs-lookup"><span data-stu-id="b3afa-122">All prior releases read from a channel specific domain, such as **com.microsoft.Edge.Dev** for Dev channel.</span></span>

<span data-ttu-id="b3afa-123">最后一步是使用首选的 MDM 提供程序（如 Microsoft Intune ）将 plist 部署到用户的 Mac 设备。</span><span class="sxs-lookup"><span data-stu-id="b3afa-123">The last step is to deploy your plist to your users' Mac devices using your preferred MDM provider, such as Microsoft Intune.</span></span> <span data-ttu-id="b3afa-124">有关说明，请参阅[部署 plist](#deploy-your-plist)。</span><span class="sxs-lookup"><span data-stu-id="b3afa-124">For instructions see [Deploy your plist](#deploy-your-plist).</span></span>

### <span data-ttu-id="b3afa-125">使用终端创建配置文件</span><span class="sxs-lookup"><span data-stu-id="b3afa-125">Create a configuration profile using Terminal</span></span>

1. <span data-ttu-id="b3afa-126">在终端中，使用以下命令和你的首选设置在桌面上创建 Microsoft Edge plist：</span><span class="sxs-lookup"><span data-stu-id="b3afa-126">In Terminal, use the following command to create a plist for Microsoft Edge on your desktop with your preferred settings:</span></span>

   ```cmd
   /usr/bin/defaults write ~/Desktop/com.microsoft.Edge.plist RestoreOnStartup -int 1
   ```

2. <span data-ttu-id="b3afa-127">将 plist 从二进制格式转换为纯文本格式：</span><span class="sxs-lookup"><span data-stu-id="b3afa-127">Convert the plist from binary to plain text format:</span></span>

   ```cmd
   /usr/bin/plutil -convert xml1 ~/Desktop/com.microsoft.Edge.plist
   ```

<span data-ttu-id="b3afa-128">在转换文件后，验证策略数据是否正确，以及是否包含你希望用于配置文件的设置。</span><span class="sxs-lookup"><span data-stu-id="b3afa-128">After converting the file verify that your policy data is correct and contains the settings you want for your configuration profile.</span></span>

> [!NOTE]
> <span data-ttu-id="b3afa-129">plist 或 xml 文件的内容中应仅有键值对。</span><span class="sxs-lookup"><span data-stu-id="b3afa-129">Only key value pairs should be in the contents of the plist or xml file.</span></span> <span data-ttu-id="b3afa-130">将文件上传到 Intune 之前，请从你的文件中删除所有 \<plist> 和 \<dict> 值以及 xml 标头。</span><span class="sxs-lookup"><span data-stu-id="b3afa-130">Prior to uploading your file into Intune remove all the \<plist> and \<dict> values, and xml headers from your file.</span></span> <span data-ttu-id="b3afa-131">该文件应仅包含键值对。</span><span class="sxs-lookup"><span data-stu-id="b3afa-131">The file should only contain key value pairs.</span></span>

## <span data-ttu-id="b3afa-132">部署你的 plist</span><span class="sxs-lookup"><span data-stu-id="b3afa-132">Deploy your plist</span></span>

<span data-ttu-id="b3afa-133">对于 Microsoft Intune，请创建面向 macOS 平台的新设备配置文件，然后选择*首选项文件*配置文件类型。</span><span class="sxs-lookup"><span data-stu-id="b3afa-133">For Microsoft Intune create a new device configuration profile targeting the macOS platform and select the *Preference file* profile type.</span></span> <span data-ttu-id="b3afa-134">将 **com.microsoft.Edge** 作为目标首选项域名，然后上传你的 plist。</span><span class="sxs-lookup"><span data-stu-id="b3afa-134">Target **com.microsoft.Edge** as the preference domain name and upload your plist.</span></span> <span data-ttu-id="b3afa-135">有关详细信息，请参阅[使用 Microsoft Intune 将属性列表文件添加到 macOS 设备中](https://docs.microsoft.com/intune/configuration/preference-file-settings-macos)。</span><span class="sxs-lookup"><span data-stu-id="b3afa-135">For more information see [Add a property list file to macOS devices using Microsoft Intune](https://docs.microsoft.com/intune/configuration/preference-file-settings-macos).</span></span>

<span data-ttu-id="b3afa-136">对于 Jamf，将 plist 文件作为*自定义设置*负载上传。</span><span class="sxs-lookup"><span data-stu-id="b3afa-136">For Jamf upload the .plist file as a *Custom Settings* payload.</span></span>

## <span data-ttu-id="b3afa-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3afa-137">See also</span></span>

- [<span data-ttu-id="b3afa-138">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="b3afa-138">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="b3afa-139">使用 Jamf 为 macOS 配置</span><span class="sxs-lookup"><span data-stu-id="b3afa-139">Configure for macOS with Jamf</span></span>](configure-microsoft-edge-on-mac-jamf.md)
- [<span data-ttu-id="b3afa-140">针对 Windows进行配置</span><span class="sxs-lookup"><span data-stu-id="b3afa-140">Configure for Windows</span></span>](configure-microsoft-edge.md)
- [<span data-ttu-id="b3afa-141">使用 Intune 针对 Windows进行配置</span><span class="sxs-lookup"><span data-stu-id="b3afa-141">Configure for Windows with Intune</span></span>](configure-edge-with-intune.md)
