---
title: Microsoft Edge 中的 PDF 阅读器
ms.author: adigan
author: dan-wesley
manager: balajek
ms.date: 08/05/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解 Microsoft Edge 中的 PDF 阅读器。
ms.openlocfilehash: c189bc08d4af0c9d5c4d9c573e0b5b7ef32a7fb3
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979373"
---
# <span data-ttu-id="17225-103">Microsoft Edge 中的 PDF 阅读器</span><span class="sxs-lookup"><span data-stu-id="17225-103">PDF reader in Microsoft Edge</span></span>

<span data-ttu-id="17225-104">我们在日常生活中会大量接触到 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="17225-104">PDF files make up a substantial part of our day-to-day lives.</span></span> <span data-ttu-id="17225-105">它们以合同与协议、新闻稿、表单、研究文章、简历等形式出现，不一而足。</span><span class="sxs-lookup"><span data-stu-id="17225-105">They come in the form of contracts and agreements, newsletters, forms, research articles, resumes, and so on.</span></span> <span data-ttu-id="17225-106">企业十分需要一款可靠、安全和强大的 PDF 阅读器来处理这些文件。</span><span class="sxs-lookup"><span data-stu-id="17225-106">These files highlight the need for a reliable, secure, and powerful PDF reader that can be adopted by Enterprises.</span></span>

<span data-ttu-id="17225-107">Microsoft Edge 内置的 PDF 阅读器可用于打开本地 PDF 文件、联机 PDF 文件或在网页中嵌入的 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="17225-107">Microsoft Edge comes with a built-in PDF reader that lets you open your local pdf files, online pdf files, or pdf files embedded in web pages.</span></span> <span data-ttu-id="17225-108">可使用墨迹和突出显示功能对这些文件添加批注。</span><span class="sxs-lookup"><span data-stu-id="17225-108">You can annotate these files with ink and highlighting.</span></span> <span data-ttu-id="17225-109">这款 PDF 阅读器应用可同时满足用户对网页和 PDF 文档的需求。</span><span class="sxs-lookup"><span data-stu-id="17225-109">This PDF reader gives users a single application to meet web page and PDF document needs.</span></span> <span data-ttu-id="17225-110">Microsoft Edge PDF 阅读器是一款安全可靠的应用程序，可跨 Windows 和 macOS 桌面平台工作。</span><span class="sxs-lookup"><span data-stu-id="17225-110">The Microsoft Edge PDF reader is a secure and reliable application that works across the Windows and macOS desktop platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="17225-111">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="17225-111">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="17225-112">前提条件、支持和约束</span><span class="sxs-lookup"><span data-stu-id="17225-112">Prerequisites, support, and constraints</span></span>

<span data-ttu-id="17225-113">下表显示了各个频道和版本的 Microsoft Edge 支持的 PDF 阅读器功能。</span><span class="sxs-lookup"><span data-stu-id="17225-113">The following table shows which channels and versions of Microsoft Edge support each PDF reader feature.</span></span>

| <span data-ttu-id="17225-114">功能</span><span class="sxs-lookup"><span data-stu-id="17225-114">Feature</span></span> | <span data-ttu-id="17225-115">稳定频道版本</span><span class="sxs-lookup"><span data-stu-id="17225-115">Stable channel version</span></span> |
|---------|------------------------|
| <span data-ttu-id="17225-116">查看和打印本地、联机和嵌入的 PDF 文件</span><span class="sxs-lookup"><span data-stu-id="17225-116">View and print local, online, and embedded PDF files</span></span> | <span data-ttu-id="17225-117">79.0.309.71</span><span class="sxs-lookup"><span data-stu-id="17225-117">79.0.309.71</span></span>                |
| <span data-ttu-id="17225-118">基本的表单填写</span><span class="sxs-lookup"><span data-stu-id="17225-118">Basic form filling</span></span><br><span data-ttu-id="17225-119">（不支持 JavaScript 表单）</span><span class="sxs-lookup"><span data-stu-id="17225-119">(JavaScript forms aren't supported)</span></span> | <span data-ttu-id="17225-120">79.0.309.71</span><span class="sxs-lookup"><span data-stu-id="17225-120">79.0.309.71</span></span>           |
| <span data-ttu-id="17225-121">墨迹书写</span><span class="sxs-lookup"><span data-stu-id="17225-121">Inking</span></span>  | <span data-ttu-id="17225-122">80.0.361.48</span><span class="sxs-lookup"><span data-stu-id="17225-122">80.0.361.48</span></span>            |
| <span data-ttu-id="17225-123">墨迹自定义</span><span class="sxs-lookup"><span data-stu-id="17225-123">Ink customization</span></span> | <span data-ttu-id="17225-124">83.0.478.54</span><span class="sxs-lookup"><span data-stu-id="17225-124">83.0.478.54</span></span>  |
| <span data-ttu-id="17225-125">Highlight</span><span class="sxs-lookup"><span data-stu-id="17225-125">Highlight</span></span>  | <span data-ttu-id="17225-126">81.0.416.53</span><span class="sxs-lookup"><span data-stu-id="17225-126">81.0.416.53</span></span>         |
| <span data-ttu-id="17225-127">大声朗读</span><span class="sxs-lookup"><span data-stu-id="17225-127">Read Aloud</span></span> | <span data-ttu-id="17225-128">目前正在 [Microsoft Edge 预览体验计划](https://www.microsoftedgeinsider.com/)频道内升级</span><span class="sxs-lookup"><span data-stu-id="17225-128">Currently being promoted in [Microsoft Edge Insider](https://www.microsoftedgeinsider.com/) channels</span></span> |
| <span data-ttu-id="17225-129">查看 MIP 受保护的文件</span><span class="sxs-lookup"><span data-stu-id="17225-129">View MIP protected files</span></span> | <span data-ttu-id="17225-130">80.0.361.48 中的 Window 支持</span><span class="sxs-lookup"><span data-stu-id="17225-130">Windows support in 80.0.361.48</span></span><br><span data-ttu-id="17225-131">81.0.416.53 中的 Mac 支持</span><span class="sxs-lookup"><span data-stu-id="17225-131">Mac support in 81.0.416.53</span></span> |
|  <span data-ttu-id="17225-132">查看 IRM 受保护的文件</span><span class="sxs-lookup"><span data-stu-id="17225-132">View IRM protected files</span></span>  | <span data-ttu-id="17225-133">83.0.478.37</span><span class="sxs-lookup"><span data-stu-id="17225-133">83.0.478.37</span></span>            |

### <span data-ttu-id="17225-134">约束</span><span class="sxs-lookup"><span data-stu-id="17225-134">Constraints</span></span>

<span data-ttu-id="17225-135">请注意，当前 PDF 阅读器存在以下限制：</span><span class="sxs-lookup"><span data-stu-id="17225-135">Note the following constraints for the current PDF reader:</span></span>

-  <span data-ttu-id="17225-136">XML 表单体系结构 (XFA) 是一种旧表单格式，在 Microsoft Edge 中不受支持。</span><span class="sxs-lookup"><span data-stu-id="17225-136">XML Forms Architecture (XFA), is a legacy format of forms that isn't  supported in Microsoft Edge.</span></span>
-  <span data-ttu-id="17225-137">有关当前不受支持的辅助功能场景的文档，可在 [Microsoft 辅助功能一致性报告](https://cloudblogs.microsoft.com/industry-blog/government/2018/09/11/accessibility-conformance-reports/)博客中找到。</span><span class="sxs-lookup"><span data-stu-id="17225-137">Documentation related to Accessibility scenarios that currently aren't supported can be found on the [Microsoft Accessibility Conformance Reports](https://cloudblogs.microsoft.com/industry-blog/government/2018/09/11/accessibility-conformance-reports/) blog.</span></span>

## <span data-ttu-id="17225-138">功能</span><span class="sxs-lookup"><span data-stu-id="17225-138">Features</span></span>

### <span data-ttu-id="17225-139">墨迹书写</span><span class="sxs-lookup"><span data-stu-id="17225-139">Inking</span></span>

<span data-ttu-id="17225-140">PDF 文件的墨迹书写非常方便，可快速记录参考、签名或填写 PDF 表单。</span><span class="sxs-lookup"><span data-stu-id="17225-140">Inking on PDF files comes in handy to take quick notes for easy reference, sign, or fill out PDF forms.</span></span> <span data-ttu-id="17225-141">现在，Microsoft Edge 中支持此功能。</span><span class="sxs-lookup"><span data-stu-id="17225-141">This capability is now available in Microsoft Edge.</span></span> <span data-ttu-id="17225-142">除了可根据需要向 PDF 文件添加墨迹书写外，还可以使用颜色和笔划宽度使他人留意 PDF 文件的不同部分。</span><span class="sxs-lookup"><span data-stu-id="17225-142">In addition to inking PDF files as needed, you can use color and stroke width to bring attention to different parts of the PDF file.</span></span> <span data-ttu-id="17225-143">下一张屏幕截图将显示用户如何向 PDF 页面添加墨迹书写。</span><span class="sxs-lookup"><span data-stu-id="17225-143">The next screenshot shows how a user can add inking to a pdf page.</span></span>

<!-- SCREENSHOT -->
![向 PDF 页面添加墨迹书写](media/microsoft-edge-pdf/pdf-reader-inking.png)

### <span data-ttu-id="17225-145">Highlight</span><span class="sxs-lookup"><span data-stu-id="17225-145">Highlight</span></span>

<span data-ttu-id="17225-146">Microsoft Edge 中的 PDF 阅读器支持添加和编辑突出显示。</span><span class="sxs-lookup"><span data-stu-id="17225-146">PDF reader in Microsoft Edge comes with support for adding and editing highlights.</span></span> <span data-ttu-id="17225-147">若要创建突出显示，用户只需选择文本，右键单击它，选择菜单中的“突出显示”，然后选择希望使用的颜色。</span><span class="sxs-lookup"><span data-stu-id="17225-147">To create a highlight, the user simply needs to select the text, right-click on it, select highlights in the menu and choose the desired color.</span></span> <span data-ttu-id="17225-148">下一张屏幕截图将显示可用的突出显示选项。</span><span class="sxs-lookup"><span data-stu-id="17225-148">The next screenshot shows the highlight options that are available.</span></span>

![使用 PDF 阅读器中的“突出显示”选项](media/microsoft-edge-pdf/pdf-reader-highlight.png)

### <span data-ttu-id="17225-150">大声朗读</span><span class="sxs-lookup"><span data-stu-id="17225-150">Read Aloud</span></span>

<span data-ttu-id="17225-151">通过 PDF 的“大声朗读”功能，用户可在执行其他对他们而言可能很重要的任务的同时，轻松收听 PDF 内容。</span><span class="sxs-lookup"><span data-stu-id="17225-151">Read Aloud for PDF adds the convenience of listening to PDF content while carrying out other tasks that may be important to users.</span></span> <span data-ttu-id="17225-152">此外，它还可帮助视障学习者专注于内容，让学习变得更加轻松。</span><span class="sxs-lookup"><span data-stu-id="17225-152">It also helps auditory learners focus on the content, which makes learning much easier.</span></span> <span data-ttu-id="17225-153">下一张屏幕截图将显示一个“大声朗读”的示例。</span><span class="sxs-lookup"><span data-stu-id="17225-153">The next screenshot shows a Read Aloud example.</span></span> <span data-ttu-id="17225-154">“突出显示”将显示当前正在阅读的文本。</span><span class="sxs-lookup"><span data-stu-id="17225-154">The highlighting shows the text that is currently being read.</span></span>

![使用 PDF 阅读器中的“突出显示”选项](media/microsoft-edge-pdf/pdf-reader-read-aloud-example.png)

### <span data-ttu-id="17225-156">受保护的 PDF 文件</span><span class="sxs-lookup"><span data-stu-id="17225-156">Protected PDFs</span></span>

<span data-ttu-id="17225-157">[Microsoft 信息保护 (MIP)](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide) 使用户能够安全地与他人协作，同时遵守组织的合规政策。</span><span class="sxs-lookup"><span data-stu-id="17225-157">[Microsoft Information Protection (MIP)](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide) enables users to collaborate with others securely, while adhering to your organization's compliance policies.</span></span> <span data-ttu-id="17225-158">文件受到保护后，用户可以对其执行的操作取决于被分配的权限。</span><span class="sxs-lookup"><span data-stu-id="17225-158">After a file is protected, the actions users can take on it are determined by the permissions assigned to them.</span></span>

<span data-ttu-id="17225-159">无需下载任何其他软件或安装任何加载项，便可直接在浏览器中打开这些文件。</span><span class="sxs-lookup"><span data-stu-id="17225-159">These files can be opened directly in the browser, without the need to download any other software, or install any add-in.</span></span> <span data-ttu-id="17225-160">这样一来，便将 MIP 提供的安全性直接集成到浏览器中，为用户提供无缝的工作流。</span><span class="sxs-lookup"><span data-stu-id="17225-160">This integrates the security provided by MIP directly into the browser, providing a seamless workflow.</span></span>

<!-- SCREENSHOT -->
![受保护的 PDF 文档。](media/microsoft-edge-pdf/pdf-reader-protected-pdf2.png)

<span data-ttu-id="17225-162">除 MIP 受保护文件之外，还可在本地浏览器中打开[信息权限管理 (IRM)](https://docs.microsoft.com/microsoft-365/compliance/set-up-irm-in-sp-admin-center?view=o365-worldwide) 受保护的 SharePoint 库中的 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="17225-162">In addition to MIP protected files, PDF files in [Information Rights Management (IRM)](https://docs.microsoft.com/microsoft-365/compliance/set-up-irm-in-sp-admin-center?view=o365-worldwide) protected SharePoint libraries can also be opened natively in the browser.</span></span>

<span data-ttu-id="17225-163">用户可在 Microsoft Edge 中查看保存在本地或云中的 MIP 受保护文件。</span><span class="sxs-lookup"><span data-stu-id="17225-163">With Microsoft Edge, users can view MIP protected files saved locally, or in the cloud.</span></span> <span data-ttu-id="17225-164">如果保存在本地，则可直接在浏览器中打开文件。</span><span class="sxs-lookup"><span data-stu-id="17225-164">If saved locally, the file can be opened directly in the browser.</span></span> <span data-ttu-id="17225-165">如果文件是从 SharePoint 等云服务中打开的，则用户可能需要使用“在浏览器中打开”选项。</span><span class="sxs-lookup"><span data-stu-id="17225-165">If the file is opened from a cloud service as SharePoint, the user may need to use the "Open in browser" option.</span></span>

<span data-ttu-id="17225-166">如果用户登录到 Microsoft Edge 的配置文件至少具有对文件的“查看”权限，则文件将在“Microsoft Edge”中打开。</span><span class="sxs-lookup"><span data-stu-id="17225-166">If the profile that the user is logged into Microsoft Edge with has at least view permissions to the file, the file will open in Microsoft Edge.</span></span>

<!-- SCREENSHOT -->
![提示保存 MIP 保护的 SharePoint PDF 页面](media/microsoft-edge-pdf/pdf-reader-sharepoint-irm.png)

## <span data-ttu-id="17225-168">辅助功能</span><span class="sxs-lookup"><span data-stu-id="17225-168">Accessibility</span></span>

<span data-ttu-id="17225-169">PDF 阅读器支持键盘辅助功能、高对比度模式以及跨 Windows 和 macOS 设备的屏幕阅读器。</span><span class="sxs-lookup"><span data-stu-id="17225-169">The PDF reader comes with support for Keyboard accessibility, High contrast mode, and screen reader support across Windows and macOS devices.</span></span>

### <span data-ttu-id="17225-170">键盘辅助功能</span><span class="sxs-lookup"><span data-stu-id="17225-170">Keyboard Accessibility</span></span>

<span data-ttu-id="17225-171">用户可使用键盘导航到文档中可交互的不同部分，如表单字段和突出显示。</span><span class="sxs-lookup"><span data-stu-id="17225-171">Users can use navigate to different parts of the document that a user can interact with, such as form fields and highlights, using the keyboard.</span></span>

<!-- SCREENSHOT -->

### <span data-ttu-id="17225-172">高对比度模式</span><span class="sxs-lookup"><span data-stu-id="17225-172">High contrast mode</span></span>

<span data-ttu-id="17225-173">PDF 阅读器将使用在操作系统级别定义的设置，在高对比度模式下呈现 PDF 内容。</span><span class="sxs-lookup"><span data-stu-id="17225-173">PDF reader will use the settings defined at the operating system level to render PDF content in high contrast mode.</span></span>

<!-- SCREENSHOT -->
<!--![High contrast mode for pdf file](media/microsoft-edge-pdf/pdf-reader-high-contrast.png)-->

### <span data-ttu-id="17225-174">屏幕阅读器支持</span><span class="sxs-lookup"><span data-stu-id="17225-174">Screen reader support</span></span>

<span data-ttu-id="17225-175">用户可以使用 Windows 和 Mac 计算机上的屏幕阅读器浏览和阅读 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="17225-175">Users can navigate through and read PDF files using screen readers on Windows and Mac computers.</span></span> <!--The next screenshot shows the toolbar that users can use for audio settings when they're using the Read Aloud option in PDF reader. -->

<!-- SCREENSHOT -->
<!--
![Screen reader toolbar](media/microsoft-edge-pdf/pdf-reader-read-aloud.png) -->

## <span data-ttu-id="17225-176">安全与可靠</span><span class="sxs-lookup"><span data-stu-id="17225-176">Security and reliability</span></span>

<span data-ttu-id="17225-177">安全是任何组织最重要的原则之一。</span><span class="sxs-lookup"><span data-stu-id="17225-177">Security is among the most important tenets for any organization.</span></span> <span data-ttu-id="17225-178">PDF 阅读器安全性是 Microsoft Edge 安全设计的一个有机组成部分。</span><span class="sxs-lookup"><span data-stu-id="17225-178">PDF reader security is an integral part of the Microsoft Edge security design.</span></span> <span data-ttu-id="17225-179">PDF 阅读器中最重要的两大安全功能是，进程隔离和 Microsoft Defender 应用程序防护（以下简称“应用程序防护”）。</span><span class="sxs-lookup"><span data-stu-id="17225-179">Two of the most important security features From a PDF reader perspective, two important security features are process isolation and Microsoft Defender Application Guard (Application Guard).</span></span>

- <span data-ttu-id="17225-180">进程隔离。</span><span class="sxs-lookup"><span data-stu-id="17225-180">Process isolation.</span></span> <span data-ttu-id="17225-181">从不同网站打开的 PDF，其进程完成彼此隔离。</span><span class="sxs-lookup"><span data-stu-id="17225-181">PDFs opened from different web sites are completely process isolated.</span></span> <span data-ttu-id="17225-182">浏览器无需同任何网站或从其他来源打开的 PDF 文件进行通信。</span><span class="sxs-lookup"><span data-stu-id="17225-182">The browser doesn't have to communicate with any websites, or PDF files opened from another source.</span></span> <span data-ttu-id="17225-183">因此，浏览 PDF 不会遭受任何计划使用遭入侵的 PDF 作为攻击面的攻击。</span><span class="sxs-lookup"><span data-stu-id="17225-183">PDF browsing is secure from any attacks that plan to use compromised PDFs as an attack surface.</span></span>

- <span data-ttu-id="17225-184">应用程序防护。</span><span class="sxs-lookup"><span data-stu-id="17225-184">Application Guard.</span></span> <span data-ttu-id="17225-185">借助应用程序防护，管理员可以设置组织信任的网站列表。</span><span class="sxs-lookup"><span data-stu-id="17225-185">With Application Guard, admins can set a list of sites that are trusted by their organization.</span></span> <span data-ttu-id="17225-186">如果用户打开任何其他网站，将在单独的应用程序防护窗口中打开，该窗口在自己的容器中运行。</span><span class="sxs-lookup"><span data-stu-id="17225-186">If users open any other sites, they are opened in a separate Application Guard window that runs in its own container.</span></span> <span data-ttu-id="17225-187">该容器可帮助保护公司网络和用户计算机上的任何数据免遭入侵。</span><span class="sxs-lookup"><span data-stu-id="17225-187">The container helps protect the corporate network and any data on user's computer from being compromised.</span></span><br><br>
<span data-ttu-id="17225-188">此保护同样适用于已查看的任何联机 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="17225-188">This protection also applies to any online PDF files that are viewed.</span></span> <span data-ttu-id="17225-189">此外，将存储任何从应用程序防护下载的 PDF 文件，并在需要时在容器中重新打开。</span><span class="sxs-lookup"><span data-stu-id="17225-189">Further, any PDF files that are downloaded from an Application Guard window are stored, and when needed, re-opened in the container.</span></span> <span data-ttu-id="17225-190">这将帮助你的环境不只在下载文件时，而是在 PDF 文件的整个生命周期中保持安全。</span><span class="sxs-lookup"><span data-stu-id="17225-190">This helps keeps your environment secure not just when the file is downloaded, but through its whole lifecycle.</span></span> <span data-ttu-id="17225-191">有关详细信息，请参阅[应用程序防护](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-defender-application-guard)。</span><span class="sxs-lookup"><span data-stu-id="17225-191">For more information, see [Application Guard](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-defender-application-guard).</span></span>

### <span data-ttu-id="17225-192">可靠性</span><span class="sxs-lookup"><span data-stu-id="17225-192">Reliability</span></span>

<span data-ttu-id="17225-193">由于 Microsoft Edge 是一款 Chromium 内核浏览器，因此能够为用户提供与 Google Chrome 浏览器相同级别的可靠性。</span><span class="sxs-lookup"><span data-stu-id="17225-193">Because Microsoft Edge is Chromium-based, users can expect the same level of reliability that they're used to seeing in Google Chrome.</span></span>

## <span data-ttu-id="17225-194">部署和更新 PDF 阅读器</span><span class="sxs-lookup"><span data-stu-id="17225-194">Deploy and update PDF reader</span></span>

<span data-ttu-id="17225-195">PDF 阅读器会随 Microsoft Edge 浏览器的其余部分进行部署和更新。</span><span class="sxs-lookup"><span data-stu-id="17225-195">The PDF reader gets deployed and updated with the rest of the Microsoft Edge browser.</span></span> <span data-ttu-id="17225-196">若要了解有关部署 Microsoft Edge 的详细信息，请观看[将 Microsoft Edge 部署到成百上千的设备](microsoft-edge-video-deploy.md)视频。</span><span class="sxs-lookup"><span data-stu-id="17225-196">To learn more about deploying Microsoft Edge, watch the [Deploy Microsoft Edge to hundreds or thousands of devices](microsoft-edge-video-deploy.md) video.</span></span> <span data-ttu-id="17225-197">此外，还可访问 [Microsoft Edge 文档](https://docs.microsoft.com/DeployEdge/)登陆页面，获得更多部署信息。</span><span class="sxs-lookup"><span data-stu-id="17225-197">You can also find more deployment information on the [Microsoft Edge documentation](https://docs.microsoft.com/DeployEdge/) landing page.</span></span>

> [!TIP]
> <span data-ttu-id="17225-198">你可以将 Microsoft Edge 设置为组织的默认 PDF 阅读器。</span><span class="sxs-lookup"><span data-stu-id="17225-198">You can make Microsoft Edge the default PDF reader for your organization.</span></span> <span data-ttu-id="17225-199">为此，[请执行下列步骤](https://docs.microsoft.com/deployedge/edge-default-browser)。</span><span class="sxs-lookup"><span data-stu-id="17225-199">To do this, [follow these steps](https://docs.microsoft.com/deployedge/edge-default-browser).</span></span>

## <span data-ttu-id="17225-200">路线图和反馈</span><span class="sxs-lookup"><span data-stu-id="17225-200">Roadmap and feedback</span></span>

<span data-ttu-id="17225-201">Microsoft Edge 中的 PDF 阅读器路线图可在[此处](https://techcommunity.microsoft.com/t5/articles/roadmap-for-pdf-reader-in-microsoft-edge/m-p/1467667)查看。</span><span class="sxs-lookup"><span data-stu-id="17225-201">The roadmap for PDF Reader in Microsoft Edge is available [here](https://techcommunity.microsoft.com/t5/articles/roadmap-for-pdf-reader-in-microsoft-edge/m-p/1467667).</span></span>

<span data-ttu-id="17225-202">我们正积极研究你认为重要的功能反馈。</span><span class="sxs-lookup"><span data-stu-id="17225-202">We're actively looking at feedback from you about the features you find important.</span></span> <span data-ttu-id="17225-203">可随时通过 [Microsoft Edge UserVoice](https://microsoftedge.uservoice.com/) 以及前往 [Microsoft Edge 预览体验计划](https://techcommunity.microsoft.com/t5/microsoft-edge-insider/ct-p/MicrosoftEdgeInsider)论坛与我们分享你的反馈意见。</span><span class="sxs-lookup"><span data-stu-id="17225-203">Feel free to send us feedback through [Microsoft Edge UserVoice](https://microsoftedge.uservoice.com/) and on [Microsoft Edge Insider](https://techcommunity.microsoft.com/t5/microsoft-edge-insider/ct-p/MicrosoftEdgeInsider) forum.</span></span>

## <span data-ttu-id="17225-204">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17225-204">See also</span></span>

- [<span data-ttu-id="17225-205">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="17225-205">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)