---
title: Microsoft Edge 中的 PDF 阅读器
ms.author: adigan
author: dan-wesley
manager: balajek
ms.date: 01/21/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解 Microsoft Edge 中的 PDF 阅读器。
ms.openlocfilehash: d4d9d3efa063b9b6981d5c7cd4bc69968b56448b
ms.sourcegitcommit: f0f250190fc09964175778338a177f1240946b98
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "11297201"
---
# <span data-ttu-id="3aae1-103">Microsoft Edge 中的 PDF 阅读器</span><span class="sxs-lookup"><span data-stu-id="3aae1-103">PDF reader in Microsoft Edge</span></span>

<span data-ttu-id="3aae1-104">PDF 文件是我们日常生活的重要组成部分。</span><span class="sxs-lookup"><span data-stu-id="3aae1-104">PDF files make up a large part of our day-to-day lives.</span></span> <span data-ttu-id="3aae1-105">它们以合同与协议、新闻稿、表单、研究文章、简历等形式出现，不一而足。</span><span class="sxs-lookup"><span data-stu-id="3aae1-105">They come in the form of contracts and agreements, newsletters, forms, research articles, resumes, and so on.</span></span> <span data-ttu-id="3aae1-106">企业十分需要一款可靠、安全和强大的 PDF 阅读器来处理这些文件。</span><span class="sxs-lookup"><span data-stu-id="3aae1-106">These files highlight the need for a reliable, secure, and powerful PDF reader that can be adopted by Enterprises.</span></span>

<span data-ttu-id="3aae1-107">Microsoft Edge 内置的 PDF 阅读器可用于打开本地 PDF 文件、联机 PDF 文件或在网页中嵌入的 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="3aae1-107">Microsoft Edge comes with a built-in PDF reader that lets you open your local pdf files, online pdf files, or pdf files embedded in web pages.</span></span> <span data-ttu-id="3aae1-108">可使用墨迹和突出显示功能对这些文件添加批注。</span><span class="sxs-lookup"><span data-stu-id="3aae1-108">You can annotate these files with ink and highlighting.</span></span> <span data-ttu-id="3aae1-109">这款 PDF 阅读器应用可同时满足用户对网页和 PDF 文档的需求。</span><span class="sxs-lookup"><span data-stu-id="3aae1-109">This PDF reader gives users a single application to meet web page and PDF document needs.</span></span> <span data-ttu-id="3aae1-110">Microsoft Edge PDF 阅读器是一款安全可靠的应用程序，可跨 Windows 和 macOS 桌面平台工作。</span><span class="sxs-lookup"><span data-stu-id="3aae1-110">The Microsoft Edge PDF reader is a secure and reliable application that works across the Windows and macOS desktop platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="3aae1-111">本文适用于 Microsoft Edge 版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="3aae1-111">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="3aae1-112">前提条件、支持和约束</span><span class="sxs-lookup"><span data-stu-id="3aae1-112">Prerequisites, support, and constraints</span></span>

<span data-ttu-id="3aae1-113">下表显示了各个频道和版本的 Microsoft Edge 支持的 PDF 阅读器功能。</span><span class="sxs-lookup"><span data-stu-id="3aae1-113">The following table shows which channels and versions of Microsoft Edge support each PDF reader feature.</span></span>

| <span data-ttu-id="3aae1-114">功能</span><span class="sxs-lookup"><span data-stu-id="3aae1-114">Feature</span></span> | <span data-ttu-id="3aae1-115">稳定频道版本</span><span class="sxs-lookup"><span data-stu-id="3aae1-115">Stable channel version</span></span> |
|---------|------------------------|
| <span data-ttu-id="3aae1-116">查看和打印本地、联机和嵌入的 PDF 文件</span><span class="sxs-lookup"><span data-stu-id="3aae1-116">View and print local, online, and embedded PDF files</span></span> | <span data-ttu-id="3aae1-117">79.0.309.71</span><span class="sxs-lookup"><span data-stu-id="3aae1-117">79.0.309.71</span></span>                |
| <span data-ttu-id="3aae1-118">基本的表单填写</span><span class="sxs-lookup"><span data-stu-id="3aae1-118">Basic form filling</span></span><br><span data-ttu-id="3aae1-119">（不支持 JavaScript 表单）</span><span class="sxs-lookup"><span data-stu-id="3aae1-119">(JavaScript forms aren't supported)</span></span> | <span data-ttu-id="3aae1-120">79.0.309.71</span><span class="sxs-lookup"><span data-stu-id="3aae1-120">79.0.309.71</span></span>           |
|<span data-ttu-id="3aae1-121">目录</span><span class="sxs-lookup"><span data-stu-id="3aae1-121">Table of contents</span></span>| <span data-ttu-id="3aae1-122">86.0.622.38</span><span class="sxs-lookup"><span data-stu-id="3aae1-122">86.0.622.38</span></span> |
| <span data-ttu-id="3aae1-123">页面视图</span><span class="sxs-lookup"><span data-stu-id="3aae1-123">Page view</span></span> |<span data-ttu-id="3aae1-124">目前正在 [Microsoft Edge 预览体验计划](https://www.microsoftedgeinsider.com/)频道内升级</span><span class="sxs-lookup"><span data-stu-id="3aae1-124">Currently being promoted in [Microsoft Edge Insider](https://www.microsoftedgeinsider.com/) channels</span></span> |
| <span data-ttu-id="3aae1-125">插入光标模式浏览</span><span class="sxs-lookup"><span data-stu-id="3aae1-125">Caret mode browsing</span></span> |<span data-ttu-id="3aae1-126">87.0.664.41</span><span class="sxs-lookup"><span data-stu-id="3aae1-126">87.0.664.41</span></span> |
| <span data-ttu-id="3aae1-127">墨迹书写</span><span class="sxs-lookup"><span data-stu-id="3aae1-127">Inking</span></span>  | <span data-ttu-id="3aae1-128">80.0.361.48</span><span class="sxs-lookup"><span data-stu-id="3aae1-128">80.0.361.48</span></span>            |
| <span data-ttu-id="3aae1-129">墨迹自定义</span><span class="sxs-lookup"><span data-stu-id="3aae1-129">Ink customization</span></span> | <span data-ttu-id="3aae1-130">83.0.478.54</span><span class="sxs-lookup"><span data-stu-id="3aae1-130">83.0.478.54</span></span>  |
| <span data-ttu-id="3aae1-131">Highlight</span><span class="sxs-lookup"><span data-stu-id="3aae1-131">Highlight</span></span>  | <span data-ttu-id="3aae1-132">81.0.416.53</span><span class="sxs-lookup"><span data-stu-id="3aae1-132">81.0.416.53</span></span>         |
| <span data-ttu-id="3aae1-133">文本注释</span><span class="sxs-lookup"><span data-stu-id="3aae1-133">Text notes</span></span> | <span data-ttu-id="3aae1-134">目前正在 [Microsoft Edge 预览体验计划](https://www.microsoftedgeinsider.com/)频道内升级</span><span class="sxs-lookup"><span data-stu-id="3aae1-134">Currently being promoted in [Microsoft Edge Insider](https://www.microsoftedgeinsider.com/) channels</span></span> |
| <span data-ttu-id="3aae1-135">大声朗读</span><span class="sxs-lookup"><span data-stu-id="3aae1-135">Read aloud</span></span> | <span data-ttu-id="3aae1-136">84.0.522.63</span><span class="sxs-lookup"><span data-stu-id="3aae1-136">84.0.522.63</span></span>  |
| <span data-ttu-id="3aae1-137">查看受 Microsoft 信息保护 (MIP) 保护的文件</span><span class="sxs-lookup"><span data-stu-id="3aae1-137">View Microsoft Information Protection (MIP) protected files</span></span> | <span data-ttu-id="3aae1-138">80.0.361.48 中的 Windows 支持</span><span class="sxs-lookup"><span data-stu-id="3aae1-138">Windows support in 80.0.361.48</span></span><br><span data-ttu-id="3aae1-139">81.0.416.53 中的 Mac 支持</span><span class="sxs-lookup"><span data-stu-id="3aae1-139">Mac support in 81.0.416.53</span></span> |
|  <span data-ttu-id="3aae1-140">查看受 Information Rights Management (IRM) 保护的文件</span><span class="sxs-lookup"><span data-stu-id="3aae1-140">View Information Rights Management (IRM) protected files</span></span>  | <span data-ttu-id="3aae1-141">83.0.478.37</span><span class="sxs-lookup"><span data-stu-id="3aae1-141">83.0.478.37</span></span>            |
| <span data-ttu-id="3aae1-142">查看和验证数字签名</span><span class="sxs-lookup"><span data-stu-id="3aae1-142">View and validate Digital Signatures</span></span> | <span data-ttu-id="3aae1-143">在 Canary 和 Dev 渠道中可用。</span><span class="sxs-lookup"><span data-stu-id="3aae1-143">Available in Canary and Dev channels.</span></span> <span data-ttu-id="3aae1-144">正在积极处理。</span><span class="sxs-lookup"><span data-stu-id="3aae1-144">Being actively worked on.</span></span> |

### <span data-ttu-id="3aae1-145">约束</span><span class="sxs-lookup"><span data-stu-id="3aae1-145">Constraints</span></span>

<span data-ttu-id="3aae1-146">请注意，当前 PDF 阅读器存在以下限制：</span><span class="sxs-lookup"><span data-stu-id="3aae1-146">Note the following constraints for the current PDF reader:</span></span>

-  <span data-ttu-id="3aae1-147">XML 表单体系结构 (XFA) 是一种旧表单格式，在 Microsoft Edge 中不受支持。</span><span class="sxs-lookup"><span data-stu-id="3aae1-147">XML Forms Architecture (XFA), is a legacy format of forms that isn't  supported in Microsoft Edge.</span></span>
-  <span data-ttu-id="3aae1-148">有关当前不受支持的辅助功能场景的文档，可在 [Microsoft 辅助功能一致性报告](https://cloudblogs.microsoft.com/industry-blog/government/2018/09/11/accessibility-conformance-reports/)博客中找到。</span><span class="sxs-lookup"><span data-stu-id="3aae1-148">Documentation related to Accessibility scenarios that currently aren't supported can be found on the [Microsoft Accessibility Conformance Reports](https://cloudblogs.microsoft.com/industry-blog/government/2018/09/11/accessibility-conformance-reports/) blog.</span></span>

## <span data-ttu-id="3aae1-149">功能</span><span class="sxs-lookup"><span data-stu-id="3aae1-149">Features</span></span>

<span data-ttu-id="3aae1-150">PDF 阅读器内置于 Microsoft Edge 中，具有基本的阅读和导航功能，如缩放、旋转、适合页面/宽度、跳转到页面和搜索等。</span><span class="sxs-lookup"><span data-stu-id="3aae1-150">The PDF reader, built into Microsoft Edge, comes with the basic reading and navigation features, as Zoom, Rotate, Fit to page/width, jump to page, and search, among others.</span></span> <span data-ttu-id="3aae1-151">它们可以通过 PDF 内容顶部的可固定工具栏访问。</span><span class="sxs-lookup"><span data-stu-id="3aae1-151">They can be accessed through a pin-able toolbar at the top of PDF content.</span></span> <span data-ttu-id="3aae1-152">本节概述了一些重要功能。</span><span class="sxs-lookup"><span data-stu-id="3aae1-152">This section gives an overview of some important functions.</span></span> <span data-ttu-id="3aae1-153">下一张屏幕截图显示了 PDF 阅读器工具栏。</span><span class="sxs-lookup"><span data-stu-id="3aae1-153">The next screenshot shows the PDF reader toolbar.</span></span>

![PDF 阅读器工具栏](media/microsoft-edge-pdf/pdf-reader-toolbar.png)

### <span data-ttu-id="3aae1-155">目录</span><span class="sxs-lookup"><span data-stu-id="3aae1-155">Table of contents</span></span>

<span data-ttu-id="3aae1-156">目录使用户能够轻松浏览具有目录的 PDF 文档。</span><span class="sxs-lookup"><span data-stu-id="3aae1-156">Table of contents lets users easily navigate through PDF documents that have a table of contents.</span></span> <span data-ttu-id="3aae1-157">当用户单击目录图标时，将出现显示 PDF 文档中标记的部分和子部分列表的导航窗格。</span><span class="sxs-lookup"><span data-stu-id="3aae1-157">When a user clicks the Table of contents icon, a navigation pane that  shows a list of the labeled sections and subsections in the PDF document is shown.</span></span> <span data-ttu-id="3aae1-158">然后用户可以单击窗格中的任何标签以导航到文档的该部分。</span><span class="sxs-lookup"><span data-stu-id="3aae1-158">The user can then click any of the labels in the pane to navigate to that section of the document.</span></span> <span data-ttu-id="3aae1-159">只要需要，窗格就会保持打开状态，当用户想继续阅读文档时，可以关闭窗格。</span><span class="sxs-lookup"><span data-stu-id="3aae1-159">The pane stays open for as long as needed and can be closed when the user wants to go back to reading the document.</span></span> <span data-ttu-id="3aae1-160">下一个屏幕截图显示了打开文档的导航窗格。</span><span class="sxs-lookup"><span data-stu-id="3aae1-160">The next screenshot shows the navigation pane for an open document.</span></span>

![带目录的 PDF 阅读器导航](media/microsoft-edge-pdf/pdf-reader-toc.png)

### <span data-ttu-id="3aae1-162">页面视图</span><span class="sxs-lookup"><span data-stu-id="3aae1-162">Page view</span></span>

<span data-ttu-id="3aae1-163">Microsoft Edge 支持在开发人员和 Canary 渠道中查看不同的 PDF 文档。</span><span class="sxs-lookup"><span data-stu-id="3aae1-163">Microsoft Edge supports different views for PDF documents in our Dev and Canary channels.</span></span> <span data-ttu-id="3aae1-164">用户可以将文档的布局从单个页面视图更改为并排显示的两个页面。</span><span class="sxs-lookup"><span data-stu-id="3aae1-164">Users can change the layout of a document from a single page view to two pages that are displayed side by side.</span></span> <span data-ttu-id="3aae1-165">要更改查看 PDF 文档的方式，用户可以单击 PDF 工具栏中的“页面视图”按钮，然后选择要使用的任一视图。</span><span class="sxs-lookup"><span data-stu-id="3aae1-165">To change how the PDF document is being viewed, users can click the Page View button in the PDF toolbar and then choose either view they want to use.</span></span> <span data-ttu-id="3aae1-166">下一张屏幕截图中显示了两个页面视图。</span><span class="sxs-lookup"><span data-stu-id="3aae1-166">The two page view is shown in the next screenshot.</span></span>

![PDF 阅读器使用两个页面文档视图。](media/microsoft-edge-pdf/pdf-reader-page-view.png)

### <span data-ttu-id="3aae1-168">插入光标模式浏览</span><span class="sxs-lookup"><span data-stu-id="3aae1-168">Caret mode browsing</span></span>

<span data-ttu-id="3aae1-169">在 Microsoft Edge 中打开的 PDF 文件可使用插入光标浏览，这意味着用户可以使用键盘与 PDF 文件进行交互。</span><span class="sxs-lookup"><span data-stu-id="3aae1-169">Caret browsing is available for PDF files opened in Microsoft Edge, which means that users can interact with PDF files using the keyboard.</span></span> <span data-ttu-id="3aae1-170">如果用户在浏览器的任何地方按 F7 键，就会询问是否应该打开插入光标浏览。</span><span class="sxs-lookup"><span data-stu-id="3aae1-170">If a user presses the F7 key anywhere in the browser, they're asked if caret browsing should be turned on.</span></span> <span data-ttu-id="3aae1-171">如果启用，插入光标浏览可用于在浏览器中打开的任何内容，无论是 PDF 文件还是网页。</span><span class="sxs-lookup"><span data-stu-id="3aae1-171">If enabled, caret browsing is available for any content opened in the browser, be it PDF files or web pages.</span></span> <span data-ttu-id="3aae1-172">当用户再次按 F7 时，将关闭插入光标浏览。</span><span class="sxs-lookup"><span data-stu-id="3aae1-172">When a user presses F7 again, caret browsing is turned off.</span></span> <span data-ttu-id="3aae1-173">当插入光标浏览处于活动状态且焦点在内容上时，用户将在 PDF 文件中看到闪烁的光标。</span><span class="sxs-lookup"><span data-stu-id="3aae1-173">When caret browsing is active and the focus is on the content, users will see a blinking cursor in the PDF file.</span></span> <span data-ttu-id="3aae1-174">插入光标还可用于在文件中导航，或在移动光标时按 Shift 键选择文本。</span><span class="sxs-lookup"><span data-stu-id="3aae1-174">The caret can also be used to navigate through the file, or to select text by pressing Shift while moving the cursor.</span></span> <span data-ttu-id="3aae1-175">此功能允许用户轻松地创建作为突出显示的元素，或与作为链接的元素交互，使用键盘形成字段。</span><span class="sxs-lookup"><span data-stu-id="3aae1-175">This ability lets users easily create elements as highlights, or interact with elements as links, form fields with the keyboard.</span></span> <span data-ttu-id="3aae1-176">下一个屏幕截图显示了打开“插入光标模式浏览”的弹出菜单。</span><span class="sxs-lookup"><span data-stu-id="3aae1-176">The next screenshot shows the popup menu for turning on Caret mode browsing.</span></span>

![用于插入光标模式浏览的 PDF 阅读器菜单。](media/microsoft-edge-pdf/pdf-reader-caret-mode.png)

### <span data-ttu-id="3aae1-178">墨迹书写</span><span class="sxs-lookup"><span data-stu-id="3aae1-178">Inking</span></span>

<span data-ttu-id="3aae1-179">PDF 文件的墨迹书写非常方便，可快速记录参考、签名或填写 PDF 表单。</span><span class="sxs-lookup"><span data-stu-id="3aae1-179">Inking on PDF files comes in handy to take quick notes for easy reference, sign, or fill out PDF forms.</span></span> <span data-ttu-id="3aae1-180">现在，Microsoft Edge 中支持此功能。</span><span class="sxs-lookup"><span data-stu-id="3aae1-180">This capability is now available in Microsoft Edge.</span></span> <span data-ttu-id="3aae1-181">除了可根据需要向 PDF 文件添加墨迹书写外，还可以使用颜色和笔划宽度使他人留意 PDF 文件的不同部分。</span><span class="sxs-lookup"><span data-stu-id="3aae1-181">In addition to inking PDF files as needed, you can use color and stroke width to bring attention to different parts of the PDF file.</span></span> <span data-ttu-id="3aae1-182">下一张屏幕截图将显示用户如何向 PDF 页面添加墨迹书写。</span><span class="sxs-lookup"><span data-stu-id="3aae1-182">The next screenshot shows how a user can add inking to a pdf page.</span></span>

![向 PDF 页面添加墨迹书写](media/microsoft-edge-pdf/pdf-reader-inking.png)

### <span data-ttu-id="3aae1-184">Highlight</span><span class="sxs-lookup"><span data-stu-id="3aae1-184">Highlight</span></span>

<span data-ttu-id="3aae1-185">Microsoft Edge 中的 PDF 阅读器支持添加和编辑突出显示。</span><span class="sxs-lookup"><span data-stu-id="3aae1-185">PDF reader in Microsoft Edge comes with support for adding and editing highlights.</span></span> <span data-ttu-id="3aae1-186">若要创建突出显示，用户只需选择文本，右键单击它，选择菜单中的“突出显示”，然后选择希望使用的颜色。</span><span class="sxs-lookup"><span data-stu-id="3aae1-186">To create a highlight, the user simply needs to select the text, right-click on it, select highlights in the menu and choose the desired color.</span></span> <span data-ttu-id="3aae1-187">还可使用笔触笔或键盘创建突出显示。</span><span class="sxs-lookup"><span data-stu-id="3aae1-187">Highlights can also be created using a pen, or keyboard.</span></span> <span data-ttu-id="3aae1-188">下一张屏幕截图将显示可用的突出显示选项。</span><span class="sxs-lookup"><span data-stu-id="3aae1-188">The next screenshot shows the highlight options that are available.</span></span>

![使用 PDF 阅读器中的“突出显示”选项](media/microsoft-edge-pdf/pdf-reader-highlight.png)

### <span data-ttu-id="3aae1-190">文本注释</span><span class="sxs-lookup"><span data-stu-id="3aae1-190">Text notes</span></span>

<span data-ttu-id="3aae1-191">阅读 PDF 文件时，可以将文本笔记添加到文件中的文本中，以记下想法，方便日后参考。</span><span class="sxs-lookup"><span data-stu-id="3aae1-191">While reading a PDF file, text notes can be added to text in the file to jot down thoughts for easy reference later.</span></span>

<span data-ttu-id="3aae1-192">用户可以通过选择要添加笔记的文本并调用右键单击上下文菜单来添加笔记。</span><span class="sxs-lookup"><span data-stu-id="3aae1-192">Users can add a note by selecting the piece of text they wish to add a note for and invoking the right-click context menu.</span></span> <span data-ttu-id="3aae1-193">选择菜单中的**添加笔记**选项将打开用户可以在其中添加注释的文本框。</span><span class="sxs-lookup"><span data-stu-id="3aae1-193">Selecting the **Add Comment** option in the menu will open a text box where users can add their comments.</span></span> <span data-ttu-id="3aae1-194">他们可以键入注释，然后单击复选标记保存笔记。</span><span class="sxs-lookup"><span data-stu-id="3aae1-194">They can type the comment and then click the check mark to save the comment.</span></span>

<span data-ttu-id="3aae1-195">添加笔记后，所选文本将突出显示，并显示笔记图标以指示笔记。</span><span class="sxs-lookup"><span data-stu-id="3aae1-195">After a note is added, the selected text will be highlighted, and a comment icon will appear to indicate the comment.</span></span> <span data-ttu-id="3aae1-196">用户可以将鼠标悬停在该图标上预览评论，也可以单击它打开并编辑注释。</span><span class="sxs-lookup"><span data-stu-id="3aae1-196">Users can hover over that icon to preview the comment or click on it to open and edit the note.</span></span>

<span data-ttu-id="3aae1-197">下一个屏幕截图显示笔记被添加到突出显示的文本中。</span><span class="sxs-lookup"><span data-stu-id="3aae1-197">The next screenshot shows a note getting added to highlighted text.</span></span>

![PDF 阅读器将文本笔记添加到文档。](media/microsoft-edge-pdf/pdf-reader-text-note.png)

### <span data-ttu-id="3aae1-199">大声朗读</span><span class="sxs-lookup"><span data-stu-id="3aae1-199">Read aloud</span></span>

<span data-ttu-id="3aae1-200">通过 PDF 的“大声朗读”功能，用户可在执行其他对他们而言可能很重要的任务的同时，轻松收听 PDF 内容。</span><span class="sxs-lookup"><span data-stu-id="3aae1-200">Read aloud for PDF adds the convenience of listening to PDF content while carrying out other tasks that may be important to users.</span></span> <span data-ttu-id="3aae1-201">此外，它还可帮助视障学习者专注于内容，让学习变得更加轻松。</span><span class="sxs-lookup"><span data-stu-id="3aae1-201">It also helps auditory learners focus on the content, which makes learning much easier.</span></span> <span data-ttu-id="3aae1-202">下一张屏幕截图将显示一个“大声朗读”的示例。</span><span class="sxs-lookup"><span data-stu-id="3aae1-202">The next screenshot shows a Read aloud example.</span></span> <span data-ttu-id="3aae1-203">“突出显示”将显示当前正在阅读的文本。</span><span class="sxs-lookup"><span data-stu-id="3aae1-203">The highlighting shows the text that is currently being read.</span></span>

![在 PDF 阅读器中使用“大声朗读”的突出显示选项 ](media/microsoft-edge-pdf/pdf-reader-read-aloud-example.png)

### <span data-ttu-id="3aae1-205">受保护的 PDF 文件</span><span class="sxs-lookup"><span data-stu-id="3aae1-205">Protected PDFs</span></span>

<span data-ttu-id="3aae1-206">[Microsoft 信息保护 (MIP)](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide&preserve-view=true) 使用户能够安全地与他人协作，同时遵守组织的合规政策。</span><span class="sxs-lookup"><span data-stu-id="3aae1-206">[Microsoft Information Protection (MIP)](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide&preserve-view=true) enables users to collaborate with others securely, while adhering to your organization's compliance policies.</span></span> <span data-ttu-id="3aae1-207">文件受到保护后，用户可以对其执行的操作取决于被分配的权限。</span><span class="sxs-lookup"><span data-stu-id="3aae1-207">After a file is protected, the actions users can take on it are determined by the permissions assigned to them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3aae1-208">MIP 需要许可证。</span><span class="sxs-lookup"><span data-stu-id="3aae1-208">A license is required for MIP.</span></span> <span data-ttu-id="3aae1-209">有关详细信息，请参阅此 [Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。</span><span class="sxs-lookup"><span data-stu-id="3aae1-209">For more information, see this [Microsoft 365 licensing guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

<span data-ttu-id="3aae1-210">无需下载任何其他软件或安装任何加载项，便可直接在浏览器中打开这些文件。</span><span class="sxs-lookup"><span data-stu-id="3aae1-210">These files can be opened directly in the browser, without the need to download any other software, or install any add-in.</span></span> <span data-ttu-id="3aae1-211">此功能将 MIP 提供的安全性直接集成到浏览器中，为用户提供无缝的工作流。</span><span class="sxs-lookup"><span data-stu-id="3aae1-211">This capability integrates the security provided by MIP directly into the browser, providing a seamless workflow.</span></span>

![受保护的 PDF 文档。](media/microsoft-edge-pdf/pdf-reader-protected-pdf2.png)

<span data-ttu-id="3aae1-213">除 MIP 受保护文件之外，还可在本地浏览器中打开[信息权限管理 (IRM)](https://docs.microsoft.com/microsoft-365/compliance/set-up-irm-in-sp-admin-center?view=o365-worldwide&preserve-view=true) 受保护的 SharePoint 库中的 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="3aae1-213">In addition to MIP protected files, PDF files in [Information Rights Management (IRM)](https://docs.microsoft.com/microsoft-365/compliance/set-up-irm-in-sp-admin-center?view=o365-worldwide&preserve-view=true) protected SharePoint libraries can also be opened natively in the browser.</span></span>

<span data-ttu-id="3aae1-214">用户可在 Microsoft Edge 中查看保存在本地或云中的 MIP 受保护文件。</span><span class="sxs-lookup"><span data-stu-id="3aae1-214">With Microsoft Edge, users can view MIP protected files saved locally, or in the cloud.</span></span> <span data-ttu-id="3aae1-215">如果保存在本地，则可直接在浏览器中打开文件。</span><span class="sxs-lookup"><span data-stu-id="3aae1-215">If saved locally, the file can be opened directly in the browser.</span></span> <span data-ttu-id="3aae1-216">如果文件是从 SharePoint 等云服务中打开的，则用户可能需要使用“在浏览器中打开”选项。</span><span class="sxs-lookup"><span data-stu-id="3aae1-216">If the file is opened from a cloud service as SharePoint, the user may need to use the "Open in browser" option.</span></span>

<span data-ttu-id="3aae1-217">如果用户登录到 Microsoft Edge 的配置文件至少具有对文件的“查看”权限，则文件将在“Microsoft Edge”中打开。</span><span class="sxs-lookup"><span data-stu-id="3aae1-217">If the profile that the user is logged into Microsoft Edge with has at least view permissions to the file, the file will open in Microsoft Edge.</span></span>

![提示保存 MIP 保护的 SharePoint PDF 页面](media/microsoft-edge-pdf/pdf-reader-sharepoint-irm.png)

### <span data-ttu-id="3aae1-219">查看和验证基于证书的数字签名</span><span class="sxs-lookup"><span data-stu-id="3aae1-219">View and validate certificate-based digital signatures</span></span>

<span data-ttu-id="3aae1-220">在这个数字世界中，建立文档内容的真实性和所有权变得非常重要。</span><span class="sxs-lookup"><span data-stu-id="3aae1-220">In this digital world, it becomes important to establish the authenticity and ownership of the content in the document.</span></span> <span data-ttu-id="3aae1-221">基于证书的数字签名通常用于 PDF 文档中，以确保文档中的内容与作者的意图相同，并且没有更改。</span><span class="sxs-lookup"><span data-stu-id="3aae1-221">Certificate-based digital signatures are commonly used in PDF documents to ensure that the content in the document is the same as what the author intended it to be, and has not been changed.</span></span> <span data-ttu-id="3aae1-222">使用 Microsoft Edge，可以查看并验证 PDF 中的证书数字签名。</span><span class="sxs-lookup"><span data-stu-id="3aae1-222">With Microsoft Edge, you can view and validate certificate digital signatures in PDFs.</span></span>

<span data-ttu-id="3aae1-223">我们正在积极致力于改进支持以解决更多方案，并期待着有关相同的反馈。</span><span class="sxs-lookup"><span data-stu-id="3aae1-223">We’re actively working on improving the support to address more scenarios, and are looking forward for feedback about the same.</span></span>

## <span data-ttu-id="3aae1-224">辅助功能</span><span class="sxs-lookup"><span data-stu-id="3aae1-224">Accessibility</span></span>

<span data-ttu-id="3aae1-225">PDF 阅读器支持键盘辅助功能、高对比度模式以及跨 Windows 和 macOS 设备的屏幕阅读器。</span><span class="sxs-lookup"><span data-stu-id="3aae1-225">The PDF reader comes with support for Keyboard accessibility, High contrast mode, and screen reader support across Windows and macOS devices.</span></span>

### <span data-ttu-id="3aae1-226">键盘辅助功能</span><span class="sxs-lookup"><span data-stu-id="3aae1-226">Keyboard Accessibility</span></span>

<span data-ttu-id="3aae1-227">用户可使用键盘导航到文档中可交互的不同部分，如表单字段和突出显示。</span><span class="sxs-lookup"><span data-stu-id="3aae1-227">Users can use navigate to different parts of the document that a user can interact with, such as form fields and highlights, using the keyboard.</span></span> <span data-ttu-id="3aae1-228">用户还可以使用插入光标模式来导航并使用键盘与 PDF 文件交互。</span><span class="sxs-lookup"><span data-stu-id="3aae1-228">Users can also use Caret mode to navigate and interact with the PDF files using the keyboard.</span></span>

### <span data-ttu-id="3aae1-229">高对比度模式</span><span class="sxs-lookup"><span data-stu-id="3aae1-229">High contrast mode</span></span>

<span data-ttu-id="3aae1-230">PDF 阅读器将使用在操作系统级别定义的设置，在高对比度模式下呈现 PDF 内容。</span><span class="sxs-lookup"><span data-stu-id="3aae1-230">PDF reader will use the settings defined at the operating system level to render PDF content in high contrast mode.</span></span>

### <span data-ttu-id="3aae1-231">屏幕阅读器支持</span><span class="sxs-lookup"><span data-stu-id="3aae1-231">Screen reader support</span></span>

<span data-ttu-id="3aae1-232">用户可以使用 Windows 和 Mac 计算机上的屏幕阅读器浏览和阅读 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="3aae1-232">Users can navigate through and read PDF files using screen readers on Windows and Mac computers.</span></span>

## <span data-ttu-id="3aae1-233">安全与可靠</span><span class="sxs-lookup"><span data-stu-id="3aae1-233">Security and reliability</span></span>

<span data-ttu-id="3aae1-234">安全是任何组织最重要的原则之一。</span><span class="sxs-lookup"><span data-stu-id="3aae1-234">Security is among the most important tenets for any organization.</span></span> <span data-ttu-id="3aae1-235">PDF 阅读器安全性是 Microsoft Edge 安全设计的一个有机组成部分。</span><span class="sxs-lookup"><span data-stu-id="3aae1-235">PDF reader security is an integral part of the Microsoft Edge security design.</span></span> <span data-ttu-id="3aae1-236">PDF 阅读器中最重要的两大安全功能是，进程隔离和 Microsoft Defender 应用程序防护（以下简称“应用程序防护”）。</span><span class="sxs-lookup"><span data-stu-id="3aae1-236">Two of the most important security features From a PDF reader perspective, two important security features are process isolation and Microsoft Defender Application Guard (Application Guard).</span></span>

- <span data-ttu-id="3aae1-237">进程隔离。</span><span class="sxs-lookup"><span data-stu-id="3aae1-237">Process isolation.</span></span> <span data-ttu-id="3aae1-238">从不同网站打开的 PDF，其进程完成彼此隔离。</span><span class="sxs-lookup"><span data-stu-id="3aae1-238">PDFs opened from different web sites are completely process isolated.</span></span> <span data-ttu-id="3aae1-239">浏览器无需同任何网站或从其他来源打开的 PDF 文件进行通信。</span><span class="sxs-lookup"><span data-stu-id="3aae1-239">The browser doesn't have to communicate with any websites, or PDF files opened from another source.</span></span> <span data-ttu-id="3aae1-240">因此，浏览 PDF 不会遭受任何计划使用遭入侵的 PDF 作为攻击面的攻击。</span><span class="sxs-lookup"><span data-stu-id="3aae1-240">PDF browsing is secure from any attacks that plan to use compromised PDFs as an attack surface.</span></span>

- <span data-ttu-id="3aae1-241">应用程序防护。</span><span class="sxs-lookup"><span data-stu-id="3aae1-241">Application Guard.</span></span> <span data-ttu-id="3aae1-242">借助应用程序防护，管理员可以设置组织信任的网站列表。</span><span class="sxs-lookup"><span data-stu-id="3aae1-242">With Application Guard, admins can set a list of sites that are trusted by their organization.</span></span> <span data-ttu-id="3aae1-243">如果用户打开任何其他网站，将在单独的应用程序防护窗口中打开，该窗口在自己的容器中运行。</span><span class="sxs-lookup"><span data-stu-id="3aae1-243">If users open any other sites, they are opened in a separate Application Guard window that runs in its own container.</span></span> <span data-ttu-id="3aae1-244">该容器可帮助保护公司网络和用户计算机上的任何数据免遭入侵。</span><span class="sxs-lookup"><span data-stu-id="3aae1-244">The container helps protect the corporate network and any data on user's computer from being compromised.</span></span><br><br>
<span data-ttu-id="3aae1-245">此保护同样适用于已查看的任何联机 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="3aae1-245">This protection also applies to any online PDF files that are viewed.</span></span> <span data-ttu-id="3aae1-246">此外，将存储任何从应用程序防护下载的 PDF 文件，并在需要时在容器中重新打开。</span><span class="sxs-lookup"><span data-stu-id="3aae1-246">Further, any PDF files that are downloaded from an Application Guard window are stored, and when needed, re-opened in the container.</span></span> <span data-ttu-id="3aae1-247">这将帮助你的环境不只在下载文件时，而是在 PDF 文件的整个生命周期中保持安全。</span><span class="sxs-lookup"><span data-stu-id="3aae1-247">This helps keeps your environment secure not just when the file is downloaded, but through its whole lifecycle.</span></span> <span data-ttu-id="3aae1-248">有关详细信息，请参阅[应用程序防护](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-defender-application-guard)。</span><span class="sxs-lookup"><span data-stu-id="3aae1-248">For more information, see [Application Guard](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-defender-application-guard).</span></span>

### <span data-ttu-id="3aae1-249">可靠性</span><span class="sxs-lookup"><span data-stu-id="3aae1-249">Reliability</span></span>

<span data-ttu-id="3aae1-250">由于 Microsoft Edge 是一款基于 Chromium 的浏览器，因此能为用户提供与其他基于 Chromium 的浏览器相同级别的可靠性。</span><span class="sxs-lookup"><span data-stu-id="3aae1-250">Because Microsoft Edge is Chromium-based, users can expect the same level of reliability that they're used to seeing in other Chromium-based browsers.</span></span>

## <span data-ttu-id="3aae1-251">部署和更新 PDF 阅读器</span><span class="sxs-lookup"><span data-stu-id="3aae1-251">Deploy and update PDF reader</span></span>

<span data-ttu-id="3aae1-252">PDF 阅读器会随 Microsoft Edge 浏览器的其余部分进行部署和更新。</span><span class="sxs-lookup"><span data-stu-id="3aae1-252">The PDF reader gets deployed and updated with the rest of the Microsoft Edge browser.</span></span> <span data-ttu-id="3aae1-253">若要了解有关部署 Microsoft Edge 的详细信息，请观看[将 Microsoft Edge 部署到成百上千的设备](microsoft-edge-video-deploy.md)视频。</span><span class="sxs-lookup"><span data-stu-id="3aae1-253">To learn more about deploying Microsoft Edge, watch the [Deploy Microsoft Edge to hundreds or thousands of devices](microsoft-edge-video-deploy.md) video.</span></span> <span data-ttu-id="3aae1-254">此外，还可访问 [Microsoft Edge 文档](https://docs.microsoft.com/DeployEdge/)登陆页面，获得更多部署信息。</span><span class="sxs-lookup"><span data-stu-id="3aae1-254">You can also find more deployment information on the [Microsoft Edge documentation](https://docs.microsoft.com/DeployEdge/) landing page.</span></span>

> [!TIP]
> <span data-ttu-id="3aae1-255">你可以将 Microsoft Edge 设置为组织的默认 PDF 阅读器。</span><span class="sxs-lookup"><span data-stu-id="3aae1-255">You can make Microsoft Edge the default PDF reader for your organization.</span></span> <span data-ttu-id="3aae1-256">为此，[请执行下列步骤](https://docs.microsoft.com/deployedge/edge-default-browser)。</span><span class="sxs-lookup"><span data-stu-id="3aae1-256">To do this, [follow these steps](https://docs.microsoft.com/deployedge/edge-default-browser).</span></span>

## <span data-ttu-id="3aae1-257">路线图和反馈</span><span class="sxs-lookup"><span data-stu-id="3aae1-257">Roadmap and feedback</span></span>

<span data-ttu-id="3aae1-258">Microsoft Edge 中的 PDF 阅读器路线图可在[此处](https://techcommunity.microsoft.com/t5/articles/roadmap-for-pdf-reader-in-microsoft-edge/m-p/1467667)查看。</span><span class="sxs-lookup"><span data-stu-id="3aae1-258">The roadmap for PDF reader in Microsoft Edge is available [here](https://techcommunity.microsoft.com/t5/articles/roadmap-for-pdf-reader-in-microsoft-edge/m-p/1467667).</span></span>

<span data-ttu-id="3aae1-259">我们正积极研究你认为重要的功能反馈。</span><span class="sxs-lookup"><span data-stu-id="3aae1-259">We're actively looking at feedback from you about the features you find important.</span></span> <span data-ttu-id="3aae1-260">可随时通过 [Microsoft Edge UserVoice](https://microsoftedge.uservoice.com/) 以及前往 [Microsoft Edge 预览体验计划](https://techcommunity.microsoft.com/t5/microsoft-edge-insider/ct-p/MicrosoftEdgeInsider)论坛与我们分享你的反馈意见。</span><span class="sxs-lookup"><span data-stu-id="3aae1-260">Feel free to send us feedback through [Microsoft Edge UserVoice](https://microsoftedge.uservoice.com/) and on [Microsoft Edge Insider](https://techcommunity.microsoft.com/t5/microsoft-edge-insider/ct-p/MicrosoftEdgeInsider) forum.</span></span>

## <span data-ttu-id="3aae1-261">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3aae1-261">See also</span></span>

- [<span data-ttu-id="3aae1-262">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="3aae1-262">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="3aae1-263">Microsoft 365 路线图</span><span class="sxs-lookup"><span data-stu-id="3aae1-263">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap)
- [<span data-ttu-id="3aae1-264">视频：Microsoft Edge 企业级 PDF 阅读器</span><span class="sxs-lookup"><span data-stu-id="3aae1-264">Video: Microsoft Edge enterprise grade PDF reader</span></span>](microsoft-edge-video-pdf-reader.md)