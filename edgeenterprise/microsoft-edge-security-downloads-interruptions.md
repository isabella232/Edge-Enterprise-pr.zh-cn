---
title: 中断潜在危险文件的下载
ms.author: kvice
author: AndreaLBarr
manager: srugh
ms.date: 05/20/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 中断潜在危险文件的下载
ms.openlocfilehash: 6239fd766c9e10d070188133a84ec0d7ce42a882
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "11618055"
---
# <a name="interrupting-downloads-of-potentially-dangerous-files"></a><span data-ttu-id="b47ff-103">中断潜在危险文件的下载</span><span class="sxs-lookup"><span data-stu-id="b47ff-103">Interrupting Downloads of Potentially Dangerous Files</span></span>

<span data-ttu-id="b47ff-104">Microsoft Edge 的文件类型策略组件允许按文件的“危险性”级别对文件进行分类，以便可以自由下载恶意文件（例如 `.txt` 文件），而潜在危险文件（例如 `.dll` 文件）则会受到更高程度的审查和更具安全意识的用户体验。</span><span class="sxs-lookup"><span data-stu-id="b47ff-104">Microsoft Edge’s File Type Policies component allows files to be classified by their level of “dangerousness”, such that harmless files (e.g. `.txt` files) can be downloaded freely, whilst potentially-dangerous files (e.g. `.dll` files) are subjected to a higher degree of vetting and a more security-conscious user-experience.</span></span>

## <a name="determining-the-danger-level-of-a-file-type"></a><span data-ttu-id="b47ff-105">确定文件类型的危险级别</span><span class="sxs-lookup"><span data-stu-id="b47ff-105">Determining the Danger Level of a File Type</span></span>

<span data-ttu-id="b47ff-106">Microsoft Edge 从上游 Chromium 浏览器继承其文件类型策略；你可以在 [此处](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb) 查看列表的当前内容。</span><span class="sxs-lookup"><span data-stu-id="b47ff-106">Microsoft Edge inherits its file type policies from the upstream Chromium browser; you can view the current contents of the list [here](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb).</span></span> <span data-ttu-id="b47ff-107">在列表中，你将看到每种类型都有一个 danger_level，它是三个值其中之一：`DANGEROUS`、`NOT_DANGEROUS` 或 `ALLOW_ON_USER_GESTURE`。</span><span class="sxs-lookup"><span data-stu-id="b47ff-107">Within the list, you’ll see that each type has a danger_level, which is one of three values: `DANGEROUS`, `NOT_DANGEROUS`, or `ALLOW_ON_USER_GESTURE`.</span></span>

<span data-ttu-id="b47ff-108">前两个很简单：**NOT_DANGEROUS** 表示文件可以安全下载，即使下载是意外操作。</span><span class="sxs-lookup"><span data-stu-id="b47ff-108">The first two are simple: **NOT_DANGEROUS** means that the file is safe to download, even if the download was accidental.</span></span> <span data-ttu-id="b47ff-109">**危险** 意味着浏览器应始终警告用户该下载可能会损害其设备。</span><span class="sxs-lookup"><span data-stu-id="b47ff-109">**DANGEROUS** means that the browser should always warn the user that the download may harm their device.</span></span>

<span data-ttu-id="b47ff-110">第三个设置 **ALLOW_ON_USER_GESTURE** 则更为微妙。</span><span class="sxs-lookup"><span data-stu-id="b47ff-110">The third setting **ALLOW_ON_USER_GESTURE** is more subtle.</span></span> <span data-ttu-id="b47ff-111">此类文件可能有危险，但如果用户请求下载，则很可能是无害的。</span><span class="sxs-lookup"><span data-stu-id="b47ff-111">Such files are potentially dangerous, but most likely harmless if the user requested the download.</span></span> <span data-ttu-id="b47ff-112">如果满足两个条件，Microsoft Edge 将允许此类下载自动继续：</span><span class="sxs-lookup"><span data-stu-id="b47ff-112">Microsoft Edge will allow such downloads to proceed automatically if two conditions are met:</span></span>

1. <span data-ttu-id="b47ff-113">一个是与启动下载的网络请求相关联的 [用户手势](https://textslashplain.com/2020/05/18/browser-basics-user-gestures/)（例如，用户单击了下载链接）。</span><span class="sxs-lookup"><span data-stu-id="b47ff-113">There is a [user gesture](https://textslashplain.com/2020/05/18/browser-basics-user-gestures/) associated with the network request that initiated the download (e.g., the user clicked a link to the download).</span></span>
2. <span data-ttu-id="b47ff-114">最近午夜（即昨天或更早时间）之前，有对参考源（链接到下载的页面）的之前访问记录。</span><span class="sxs-lookup"><span data-stu-id="b47ff-114">There is a recorded prior visit to the referring origin (the page linking to the download) prior to the most recent midnight (i.e., yesterday or earlier).</span></span> <span data-ttu-id="b47ff-115">这意味着用户有访问该网站的历史记录。</span><span class="sxs-lookup"><span data-stu-id="b47ff-115">This implies that the user has a history of visiting the site.</span></span>

<span data-ttu-id="b47ff-116">如果用户通过使用 **链接另存为** 上下文菜单命令显式启动下载，直接在浏览器的地址栏中输入下载的 URL，或者 Microsoft Defender SmartScreen 指示文件是安全的，则下载也将自动继续。</span><span class="sxs-lookup"><span data-stu-id="b47ff-116">The download will also proceed automatically if the user explicitly initiated it by using the **Save link as** context menu command, entered the download’s URL directly into the browser’s address bar, or if Microsoft Defender SmartScreen indicated that the file is safe.</span></span>

<span data-ttu-id="b47ff-117">**更新：** 从版本 91 开始，Microsoft Edge 将中断缺少所需手势的下载。</span><span class="sxs-lookup"><span data-stu-id="b47ff-117">**Update:** Starting in version 91, Microsoft Edge will interrupt downloads that lack the required gesture.</span></span>

## <a name="user-experience-for-downloads-lacking-gestures"></a><span data-ttu-id="b47ff-118">缺少手势的下载的用户体验</span><span class="sxs-lookup"><span data-stu-id="b47ff-118">User Experience for Downloads Lacking Gestures</span></span>

<span data-ttu-id="b47ff-119">如果在不使用所需手势的情况下启动潜在危险类型的下载，Microsoft Edge 将表明“已阻止”该下载。</span><span class="sxs-lookup"><span data-stu-id="b47ff-119">If a download for a potentially dangerous type starts without the required gesture, Microsoft Edge states that the download “was blocked”.</span></span> <span data-ttu-id="b47ff-120">可以使用下载项上菜单中名为 `Keep` 和 `Delete` 的命令...</span><span class="sxs-lookup"><span data-stu-id="b47ff-120">Commands named `Keep` and `Delete` are available from the …</span></span> <span data-ttu-id="b47ff-121">以允许用户继续或取消下载。</span><span class="sxs-lookup"><span data-stu-id="b47ff-121">menu on the download item to allow the user to continue or cancel the download.</span></span>

:::image type="content" source="media/microsoft-edge-security-Download-interruptions/Dowload-was-blocked.png" alt-text="已阻止下载":::

<span data-ttu-id="b47ff-123">在 `edge://downloads` 页面上，用户将看到相同的选项：</span><span class="sxs-lookup"><span data-stu-id="b47ff-123">On the `edge://downloads`, page, the user will see the same options:</span></span>

:::image type="content" source="media/microsoft-edge-security-Download-interruptions/msg-keep-delete-option.png" alt-text="MSG 保留删除选项":::

## <a name="enterprise-controls"></a><span data-ttu-id="b47ff-125">企业版控件</span><span class="sxs-lookup"><span data-stu-id="b47ff-125">Enterprise Controls</span></span>

<span data-ttu-id="b47ff-126">虽然用户不太可能在每天使用的网站上遇到中断，但他们可能会在很少使用的网站上进行合法下载时遇到这种情况。</span><span class="sxs-lookup"><span data-stu-id="b47ff-126">While users are unlikely to encounter download interruptions for sites they use every day, they might encounter them for legitimate downloads on sites that they use rarely.</span></span> <span data-ttu-id="b47ff-127">为了帮助简化企业用户体验，可以使用组策略。</span><span class="sxs-lookup"><span data-stu-id="b47ff-127">To help streamline the user-experience for Enterprises, a Group Policy is available.</span></span>

<span data-ttu-id="b47ff-128">企业可以使用 [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) 指定允许从特定站点不间断下载的文件类型。</span><span class="sxs-lookup"><span data-stu-id="b47ff-128">Enterprises can use [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) to specify the filetypes that are allowed to download from specific sites without interruption.</span></span> <span data-ttu-id="b47ff-129">例如，以下策略允许从 contoso.com 和 woodgrovebank.com 不间断下载 XML 文件，并可从任何网站下载 MSG 文件。</span><span class="sxs-lookup"><span data-stu-id="b47ff-129">For instance, the following policy allows XML files to download from contoso.com and woodgrovebank.com without interruption, and MSG files to download from any site.</span></span>

`[{"file_extension":"xml","domains":["contoso.com", "woodgrovebank.com"]},
{"file_extension":"msg", "domains": ["*"]}]`

## <a name="file-types-requiring-a-gesture"></a><span data-ttu-id="b47ff-130">需要手势的文件类型</span><span class="sxs-lookup"><span data-stu-id="b47ff-130">File Types Requiring a Gesture</span></span>

<span data-ttu-id="b47ff-131">最新的 [文件类型策略](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb) 已在 Chromium 源代码中发布。</span><span class="sxs-lookup"><span data-stu-id="b47ff-131">The latest [file types policies](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb) are published in the Chromium source code.</span></span> <span data-ttu-id="b47ff-132">自 2021 年 5 月起，至少一个操作系统平台上具有 `ALLOW_ON_USER_GESTURE` 的 `danger_level` 的文件类型包括：</span><span class="sxs-lookup"><span data-stu-id="b47ff-132">As of May 2021, file types with a `danger_level` of `ALLOW_ON_USER_GESTURE` on at least one OS platform include:</span></span>
`crx, pl, py, pyc, pyo, pyw, rb, efi, oxt, msi, msp, mst, ade, adp, mad, maf, mag, mam, maq, mar, mas, mat, mav, maw, mda, mdb, mde, mdt, mdw, mdz, accdb, accde, accdr, accda, ocx, ops, paf, pcd, pif, plg, prf, prg, pst, cpi, partial, xrm-ms, rels, svg, xml, xsl, xsd, ps1, ps1xml, ps2, ps2xml, psc1, psc2, js, jse, vb, vbe, vbs, vbscript, ws, wsc, wsf, wsh, msh, msh1, msh2, mshxml, msh1xml, msh2xml, ad, app, application, appref-ms, asp, asx, bas, bat, chi, chm, cmd, com, cpl, crt, cer, der, eml, exe, fon, fxp, hlp, htt, inf, ins, inx, isu, isp, job, lnk, mau, mht, mhtml, mmc, msc, msg, reg, rgs, scr, sct, search-ms, settingcontent-ms, shb, shs, slk, u3p, vdx, vsx, vtx, vsdx, vssx, vstx, vsdm, vssm, vstm, vsd, vsmacros, vss, vst, vsw, xnk, cdr, dart, dc42, diskcopy42, dmg, dmgpart, dvdr, dylib, img, imgpart, ndif, service, smi, sparsebundle, sparseimage, toast, udif, action, definition, wflow, caction, as, cpgz, command, mpkg, pax, workflow, xip, mobileconfig, configprofile, internetconnect, networkconnect, pkg, deb, pet, pup, rpm, slp, out, run, bash, csh, ksh, sh, shar, tcsh, desktop, dex,apk`

## <a name="danger-level-may-vary-by-operating-system"></a><span data-ttu-id="b47ff-133">危险级别可能因操作系统而异</span><span class="sxs-lookup"><span data-stu-id="b47ff-133">Danger Level May Vary By Operating System</span></span>

<span data-ttu-id="b47ff-134">文件类型设置有时因客户端操作系统平台而异。</span><span class="sxs-lookup"><span data-stu-id="b47ff-134">File type settings sometimes vary depending on the client OS platform.</span></span> <span data-ttu-id="b47ff-135">例如，`.exe` 在 Mac 上并不危险，而 `.applescript` 在 Windows 上无害。</span><span class="sxs-lookup"><span data-stu-id="b47ff-135">For instance, an `.exe` is not dangerous on a Mac, while an `.applescript` is harmless on Windows.</span></span>
