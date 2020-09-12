---
title: Microsoft Edge 中的 ClickOnce 和 DirectInvoke
ms.author: kele
author: dan-wesley
manager: srugh
ms.date: 09/10/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解有关 Microsoft Edge 中的 ClickOnce 和 DirectInvoke 的信息。
ms.openlocfilehash: 1d4e08c0ce3ee2afec7968cd892f77ef7bdc3fff
ms.sourcegitcommit: 4c0b84b03e686a7a2989ce2187dbadf35418104a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11012792"
---
# <span data-ttu-id="6dc9b-103">了解 Microsoft Edge 中的 ClickOnce 和 DirectInvoke 功能</span><span class="sxs-lookup"><span data-stu-id="6dc9b-103">Understand the ClickOnce and DirectInvoke features in Microsoft Edge</span></span>

<span data-ttu-id="6dc9b-104">ClickOnce 和 DirectInvoke 是 IE 和 Microsoft Edge（版本 45 和更早版本）中提供的功能，支持使用文件处理程序从网站下载文件。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-104">ClickOnce and DirectInvoke are features available in IE and Microsoft Edge (version 45 and earlier) that support the use of a file handler to download files from a website.</span></span> <span data-ttu-id="6dc9b-105">尽管它们适用于不同的用途，但这两个功能都允许网站指定在用户的设备上将请求下载的文件传递到文件处理程序。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-105">Although they serve different purposes, both features let websites specify that a file requested for download is passed to a file handler on the user's device.</span></span> <span data-ttu-id="6dc9b-106">ClickOnce 请求由 Windows 中的本机文件处理程序进行处理。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-106">ClickOnce requests are handled by the native file handler in Windows.</span></span> <span data-ttu-id="6dc9b-107">DirectInvoke 请求由承载文件的网站指定的注册文件处理程序进行处理。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-107">DirectInvoke requests are handled by a registered file handler specified by the website hosting the file.</span></span>

<span data-ttu-id="6dc9b-108">有关这些功能的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="6dc9b-108">For more information about these features, see:</span></span>

- [<span data-ttu-id="6dc9b-109">ClickOnce</span><span class="sxs-lookup"><span data-stu-id="6dc9b-109">ClickOnce</span></span>](https://docs.microsoft.com/visualstudio/deployment/clickonce-security-and-deployment?view=vs-2019)
- [<span data-ttu-id="6dc9b-110">DirectInvoke</span><span class="sxs-lookup"><span data-stu-id="6dc9b-110">DirectInvoke</span></span>]( https://technet.microsoft.com/learning/jj215788(v=vs.94).aspx)

> [!NOTE]
> <span data-ttu-id="6dc9b-111">目前，Chromium 不对 ClickOnce 或 DirectInvoke 提供本机支持。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-111">Currently, Chromium doesn't provide native support for ClickOnce or DirectInvoke.</span></span>

## <span data-ttu-id="6dc9b-112">概述：先决条件和过程</span><span class="sxs-lookup"><span data-stu-id="6dc9b-112">Overview: prerequisites and process</span></span>

<span data-ttu-id="6dc9b-113">为了使 ClickOnce 和 DirectInvoke 能按照设计正常工作，并且要成功请求文件处理程序，必须在操作系统中将文件处理程序注册为支持 ClickOnce 或 DirectInvoke。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-113">For ClickOnce and DirectInvoke to work as designed and for the file handler to be successfully requested, the file handler must be registered to the operating system as supporting ClickOnce or DirectInvoke.</span></span> <span data-ttu-id="6dc9b-114">通常，在安装了原始操作系统后，或者在安装的新程序要求能够使用 DirectInvoke 进行更新时，会进行此注册。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-114">This registration typically happens when the original operating system is installed or when a new program that's installed requests the ability to use DirectInvoke for updates.</span></span>

<span data-ttu-id="6dc9b-115">当网站收到需要使用 ClickOnce 或 DirectInvoke 的下载请求时，会进行操作：</span><span class="sxs-lookup"><span data-stu-id="6dc9b-115">When a website receives a download request that requires ClickOnce or DirectInvoke, the following actions happen:</span></span>

- <span data-ttu-id="6dc9b-116">该网站请求浏览器使用指定的文件处理程序。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-116">The website requests that the browser use a specified file handler.</span></span>
- <span data-ttu-id="6dc9b-117">浏览器检查操作系统注册表，以查看是否对请求的文件类型注册了文件处理程序。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-117">The browser checks the operating system registry to see if the file handler is registered for the requested file type.</span></span>
- <span data-ttu-id="6dc9b-118">如果注册了文件处理程序，则浏览器会调用此文件处理程序，并将 URL 作为参数传递给文件处理程序。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-118">If the file handler is registered, the browser calls the file handler and passes the URL as an argument to the file handler.</span></span>
- <span data-ttu-id="6dc9b-119">文件处理程序处理 URL 并下载文件。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-119">The file handler processes the URL and downloads the file.</span></span>

  > [!NOTE]
  > <span data-ttu-id="6dc9b-120">该 URL 用于确定文件的来源，以及访问文件时要使用的任何参数。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-120">The URL is used to determine the source of the file, as well as any parameters to use when accessing the file.</span></span>  <span data-ttu-id="6dc9b-121">例如：终结点、清单或元数据。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-121">For example: endpoints, a manifest, or metadata.</span></span>

## <span data-ttu-id="6dc9b-122">用例</span><span class="sxs-lookup"><span data-stu-id="6dc9b-122">Use cases</span></span>

<span data-ttu-id="6dc9b-123">以下用例具有代表性。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-123">The following use cases are representative.</span></span>

<span data-ttu-id="6dc9b-124">你可以使用 ClickOnce 轻松地在设备上部署和更新软件，但用户交互最少。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-124">You can use ClickOnce to easily deploy and update software on devices with minimal user interaction.</span></span> <span data-ttu-id="6dc9b-125">用户可以通过单击网页中的链接来安装和运行 Windows 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-125">Users can install and run a Windows application by clicking a link in a web page.</span></span> <span data-ttu-id="6dc9b-126">如果配置正确，ClickOnce 应用程序可以在不让用户为安装程序设置配置的情况下安装程序。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-126">If configured correctly, the ClickOnce application can install programs without having users set configurations for the installer.</span></span> <span data-ttu-id="6dc9b-127">例如，文件位置、要安装的选项等。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-127">For example, file locations, what options to install, and so on.</span></span>

<span data-ttu-id="6dc9b-128">DirectInvoke 用例取决于请求 DirectInvoke 的网站的意图。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-128">DirectInvoke use cases depend on the intent of the website requesting DirectInvoke.</span></span> <span data-ttu-id="6dc9b-129">例如，Microsoft Word 的协作文件编辑功能。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-129">For example, the collaborative file-editing feature of Microsoft Word.</span></span> <span data-ttu-id="6dc9b-130">DirectInvoke 允许你下载已更改的文档部分，而无需单击链接并下载你与同事合作的文档的整个副本。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-130">Instead of clicking a link and downloading the entire copy of a document you're working on with your colleagues, DirectInvoke lets you download the parts of the document that have been changed.</span></span> <span data-ttu-id="6dc9b-131">此策略减少了传输的数据量，并可以减少打开文档所需的时间。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-131">This strategy reduces the amount of data transferred and can reduce the time needed to open the document.</span></span>  

## <span data-ttu-id="6dc9b-132">Microsoft Edge 中对 ClickOnce 和 DirectInvoke 的最新支持</span><span class="sxs-lookup"><span data-stu-id="6dc9b-132">Current support for ClickOnce and DirectInvoke in Microsoft Edge</span></span>

<span data-ttu-id="6dc9b-133">对 ClickOnce 和 DirectInvoke 的支持：</span><span class="sxs-lookup"><span data-stu-id="6dc9b-133">Support for ClickOnce and DirectInvoke:</span></span>

- <span data-ttu-id="6dc9b-134">ClickOnce 和 DirectInvoke 可直接供所有 Windows 用户即时使用。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-134">ClickOnce and DirectInvoke are supported out of the box for all Windows users.</span></span>

  > [!NOTE]
  > <span data-ttu-id="6dc9b-135">想要禁用 ClickOnce 支持的用户可以转到 *edge://flags/#edge-click-once*，然后从下拉列表中选择“**已禁用**”。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-135">Users that want to disable ClickOnce support can go to *edge://flags/#edge-click-once* and select **Disabled** from the dropdown list.</span></span> <span data-ttu-id="6dc9b-136">你必须**重启**浏览器。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-136">You'll have to **Restart** the browser.</span></span>

- <span data-ttu-id="6dc9b-137">Windows 以外的任何平台都不支持 ClickOnce 和 DirectInvoke。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-137">ClickOnce and DirectInvoke aren't supported on any platforms other than Windows.</span></span>

## <span data-ttu-id="6dc9b-138">ClickOnce 和 DirectInvoke 文件处理安全性</span><span class="sxs-lookup"><span data-stu-id="6dc9b-138">ClickOnce and DirectInvoke file handling security</span></span>

<span data-ttu-id="6dc9b-139">ClickOnce 和 DirectInvoke 受 Microsoft Defender SmartScreen 的 URL 信誉扫描服务保护。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-139">ClickOnce and DirectInvoke are protected by Microsoft Defender SmartScreen's URL reputation scanning service.</span></span>

<span data-ttu-id="6dc9b-140">如果 Microsoft Defender SmartScreen URL 信誉服务将 ClickOnce 或 DirectInvoke 请求标记为不安全，则启用了 ClickOnce 或 DirectInvoke 的用户将看到两个弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-140">If a ClickOnce or a DirectInvoke request is flagged by the Microsoft Defender SmartScreen URL reputation service as unsafe, users with ClickOnce or DirectInvoke enabled will see two popups.</span></span>

<span data-ttu-id="6dc9b-141">第一个弹出窗口询问用户是否想要打开文件。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-141">The first popup asks the user if they want to open the file.</span></span> <span data-ttu-id="6dc9b-142">无论文件被标记为安全还是不安全，都会显示此弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-142">This popup is displayed regardless of whether the file was flagged as safe or unsafe.</span></span> <span data-ttu-id="6dc9b-143">用户可以**将文件报告为不安全**、**取消**请求或单击**打开**以继续。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-143">The user can **Report the file as unsafe**, **Cancel** the request, or click **Open** to continue.</span></span>

   ![提示打开文件 ](./media/edge-learn-more-co-di/edge-clickonce-modal-1.png)

<span data-ttu-id="6dc9b-145">如果用户尝试打开文件，并且文件被标记为不安全，则会显示第二个弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-145">If the user tries to open the file, and the file was flagged as unsafe, a second popup is displayed.</span></span>  <span data-ttu-id="6dc9b-146">此弹出窗口警告用户文件被标记为不安全，并询问他们是否确定要下载该文件。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-146">This popup warns the user that the file was flagged as unsafe, and asks them if they're sure they want to download the file.</span></span>

<span data-ttu-id="6dc9b-147">第二个弹出窗口仅在以下情况下显示：</span><span class="sxs-lookup"><span data-stu-id="6dc9b-147">The second popup only shows up if:</span></span>

- <span data-ttu-id="6dc9b-148">文件是 ClickOnce 或 DirectInvoke 文件</span><span class="sxs-lookup"><span data-stu-id="6dc9b-148">the file is a ClickOnce or DirectInvoke file</span></span>
- <span data-ttu-id="6dc9b-149">已启用 ClickOnce 或 DirectInvoke</span><span class="sxs-lookup"><span data-stu-id="6dc9b-149">ClickOnce or DirectInvoke are enabled</span></span>
- <span data-ttu-id="6dc9b-150">文件被标记为不安全</span><span class="sxs-lookup"><span data-stu-id="6dc9b-150">the file is flagged as unsafe</span></span>

 ![提示打开不安全的文件 ](./media/edge-learn-more-co-di/edge-clickonce-modal-2.png)

> [!NOTE]
> <span data-ttu-id="6dc9b-152">如果 ClickOnce 或 DirectInvoke 被禁用，则请求的文件将被视为常规下载；如果具有不安全标志，则会将其标记为不安全。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-152">If ClickOnce or DirectInvoke are disabled, requested files are treated as regular downloads and if flagged as unsafe, will be marked as unsafe.</span></span> <span data-ttu-id="6dc9b-153">这与其他不安全下载的处理一致。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-153">This is consistent with the treatment of other unsafe downloads.</span></span>

## <span data-ttu-id="6dc9b-154">ClickOnce 和 DirectInvoke 策略</span><span class="sxs-lookup"><span data-stu-id="6dc9b-154">ClickOnce and DirectInvoke policies</span></span>

<span data-ttu-id="6dc9b-155">有两个组策略可用于为企业用户启用或禁用 ClickOnce 和 DirectInvoke。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-155">There are two group policies that you can use to enable or disable ClickOnce and DirectInvoke for enterprise users.</span></span> <span data-ttu-id="6dc9b-156">这两个策略是 [ClickOnceEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#clickonceenabled) 和 [DirectInvokeEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#directinvokeenabled)。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-156">These two policies are [ClickOnceEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#clickonceenabled) and [DirectInvokeEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#directinvokeenabled).</span></span> <span data-ttu-id="6dc9b-157">这两个策略在组策略编辑器中分别标记为“允许用户使用 ClickOnce 协议打开文件”和“允许用户使用 DirectInvoke 协议打开文件”。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-157">These two policies are labeled in the Group Policy Editor as "Allow users to open files using the ClickOnce protocol" and "Allow users to open files using the DirectInvoke protocol" respectively.</span></span>

## <span data-ttu-id="6dc9b-158">ClickOnce 和 DirectInvoke 行为</span><span class="sxs-lookup"><span data-stu-id="6dc9b-158">ClickOnce and DirectInvoke behavior</span></span>

<span data-ttu-id="6dc9b-159">以下示例显示了启用或禁用 ClickOnce 和 DirectInvoke 时的文件处理。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-159">The following examples show file handling when ClickOnce and DirectInvoke are enabled or disabled.</span></span>

### <span data-ttu-id="6dc9b-160">已启用 ClickOnce</span><span class="sxs-lookup"><span data-stu-id="6dc9b-160">ClickOnce enabled</span></span>

1. <span data-ttu-id="6dc9b-161">用户打开一个页面链接，以请求 ClickOnce 支持，然后在下一张屏幕截图中收到提示。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-161">A user opens a link to a page that requests ClickOnce support and gets the prompt in the next screenshot.</span></span>

   ![提示打开不安全的文件 ](./media/edge-learn-more-co-di/edge-clickonce-enabled-1.png)

2. <span data-ttu-id="6dc9b-163">用户单击**打开**后，ClickOnce 将尝试启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-163">After the user clicks **Open**, ClickOnce attempts to launch the application.</span></span>

   ![ClickOnce 尝试启动应用程序](./media/edge-learn-more-co-di/edge-clickonce-enabled-launch-app.png)

3. <span data-ttu-id="6dc9b-165">用户单击**打开**后，浏览器将显示一个弹出窗口，询问用户是否确实要安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-165">After the user clicks **Open**, the browser shows a popup that asks the user if they're sure they want to install the application.</span></span>

   ![提示打开文件](./media/edge-learn-more-co-di/edge-clickonce-enabled-2.png)

   > [!NOTE]
   > <span data-ttu-id="6dc9b-167">ClickOnce 文件处理程序显示的接口、消息和选项因访问的文件的类型和配置而异。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-167">The interface, messaging, and options shown by the ClickOnce file handler will vary depending on the type and configuration of the file that's accessed.</span></span>

### <span data-ttu-id="6dc9b-168">已禁用 ClickOnce</span><span class="sxs-lookup"><span data-stu-id="6dc9b-168">ClickOnce disabled</span></span>

1. <span data-ttu-id="6dc9b-169">当用户打开页面链接以请求 ClickOnce 支持时，将在下载栏中看到一条消息，此消息类似于下一张屏幕截图中的消息。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-169">When a user opens a link to a page that requests ClickOnce support, they will see a message in the download tray that is similar to the one in the next screenshot.</span></span>

   ![文件下载提示](./media/edge-learn-more-co-di/edge-clickonce-disabled-1.png)

### <span data-ttu-id="6dc9b-171">已启用 DirectInvoke</span><span class="sxs-lookup"><span data-stu-id="6dc9b-171">DirectInvoke enabled</span></span>

1. <span data-ttu-id="6dc9b-172">用户打开页面链接以请求 DirectInvoke 支持，然后在下一张屏幕截图中收到提示。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-172">A user opens a link to a page that requests DirectInvoke support and gets the prompt in the next screenshot.</span></span>

   ![提示打开文件 ](./media/edge-learn-more-co-di/edge-directinvoke-open-link-1.png)

2. <span data-ttu-id="6dc9b-174">当用户单击**打开**时，将打开请求的文件处理程序。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-174">When the user clicks **Open**, the requested file handler is opened.</span></span> <span data-ttu-id="6dc9b-175">在此示例中，使用 Microsoft Word 打开上一张屏幕截图中显示的文档。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-175">In this example, Microsoft Word is used to open the document that's shown in the previous screenshot.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6dc9b-176">DirectInvoke 文件处理程序显示的接口、消息和选项因访问的文件的类型和配置而异。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-176">The interface, messaging, and options shown by the DirectInvoke file handler will vary depending on the type and configuration of the file that's accessed.</span></span>

### <span data-ttu-id="6dc9b-177">已禁用 DirectInvoke</span><span class="sxs-lookup"><span data-stu-id="6dc9b-177">DirectInvoke disabled</span></span>

1. <span data-ttu-id="6dc9b-178">当用户打开页面链接以请求 DirectInvoke 支持时，DirectInvoke 的行为与其在禁用 ClickOnce 时的行为相同。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-178">When a user opens a link to a page that requests DirectInvoke support, DirectInvoke behaves the same as when ClickOnce is disabled.</span></span> <span data-ttu-id="6dc9b-179">他们将在下载栏中看到一条消息，此消息类似于下一张屏幕截图中的消息。</span><span class="sxs-lookup"><span data-stu-id="6dc9b-179">They will see a message in the download tray that's similar to the one in the next screenshot.</span></span>

   ![提示打开文件](./media/edge-learn-more-co-di/edge-directinvoke-open-link-2.png)

## <span data-ttu-id="6dc9b-181">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6dc9b-181">See also</span></span>

- [<span data-ttu-id="6dc9b-182">ClickOnce 安全和部署</span><span class="sxs-lookup"><span data-stu-id="6dc9b-182">ClickOnce security and deployment</span></span>](https://go.microsoft.com/fwlink/?linkid=2099880)
- [<span data-ttu-id="6dc9b-183">Internet Explorer 中的 DirectInvoke</span><span class="sxs-lookup"><span data-stu-id="6dc9b-183">DirectInvoke in Internet Explorer</span></span>](https://go.microsoft.com/fwlink/?linkid=2099871)
- [<span data-ttu-id="6dc9b-184">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="6dc9b-184">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
