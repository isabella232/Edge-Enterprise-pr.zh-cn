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
# <a name="interrupting-downloads-of-potentially-dangerous-files"></a>中断潜在危险文件的下载

Microsoft Edge 的文件类型策略组件允许按文件的“危险性”级别对文件进行分类，以便可以自由下载恶意文件（例如 `.txt` 文件），而潜在危险文件（例如 `.dll` 文件）则会受到更高程度的审查和更具安全意识的用户体验。

## <a name="determining-the-danger-level-of-a-file-type"></a>确定文件类型的危险级别

Microsoft Edge 从上游 Chromium 浏览器继承其文件类型策略；你可以在 [此处](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb) 查看列表的当前内容。 在列表中，你将看到每种类型都有一个 danger_level，它是三个值其中之一：`DANGEROUS`、`NOT_DANGEROUS` 或 `ALLOW_ON_USER_GESTURE`。

前两个很简单：**NOT_DANGEROUS** 表示文件可以安全下载，即使下载是意外操作。 **危险** 意味着浏览器应始终警告用户该下载可能会损害其设备。

第三个设置 **ALLOW_ON_USER_GESTURE** 则更为微妙。 此类文件可能有危险，但如果用户请求下载，则很可能是无害的。 如果满足两个条件，Microsoft Edge 将允许此类下载自动继续：

1. 一个是与启动下载的网络请求相关联的 [用户手势](https://textslashplain.com/2020/05/18/browser-basics-user-gestures/)（例如，用户单击了下载链接）。
2. 最近午夜（即昨天或更早时间）之前，有对参考源（链接到下载的页面）的之前访问记录。 这意味着用户有访问该网站的历史记录。

如果用户通过使用 **链接另存为** 上下文菜单命令显式启动下载，直接在浏览器的地址栏中输入下载的 URL，或者 Microsoft Defender SmartScreen 指示文件是安全的，则下载也将自动继续。

**更新：** 从版本 91 开始，Microsoft Edge 将中断缺少所需手势的下载。

## <a name="user-experience-for-downloads-lacking-gestures"></a>缺少手势的下载的用户体验

如果在不使用所需手势的情况下启动潜在危险类型的下载，Microsoft Edge 将表明“已阻止”该下载。 可以使用下载项上菜单中名为 `Keep` 和 `Delete` 的命令... 以允许用户继续或取消下载。

:::image type="content" source="media/microsoft-edge-security-Download-interruptions/Dowload-was-blocked.png" alt-text="已阻止下载":::

在 `edge://downloads` 页面上，用户将看到相同的选项：

:::image type="content" source="media/microsoft-edge-security-Download-interruptions/msg-keep-delete-option.png" alt-text="MSG 保留删除选项":::

## <a name="enterprise-controls"></a>企业版控件

虽然用户不太可能在每天使用的网站上遇到中断，但他们可能会在很少使用的网站上进行合法下载时遇到这种情况。 为了帮助简化企业用户体验，可以使用组策略。

企业可以使用 [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) 指定允许从特定站点不间断下载的文件类型。 例如，以下策略允许从 contoso.com 和 woodgrovebank.com 不间断下载 XML 文件，并可从任何网站下载 MSG 文件。

`[{"file_extension":"xml","domains":["contoso.com", "woodgrovebank.com"]},
{"file_extension":"msg", "domains": ["*"]}]`

## <a name="file-types-requiring-a-gesture"></a>需要手势的文件类型

最新的 [文件类型策略](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb) 已在 Chromium 源代码中发布。 自 2021 年 5 月起，至少一个操作系统平台上具有 `ALLOW_ON_USER_GESTURE` 的 `danger_level` 的文件类型包括：
`crx, pl, py, pyc, pyo, pyw, rb, efi, oxt, msi, msp, mst, ade, adp, mad, maf, mag, mam, maq, mar, mas, mat, mav, maw, mda, mdb, mde, mdt, mdw, mdz, accdb, accde, accdr, accda, ocx, ops, paf, pcd, pif, plg, prf, prg, pst, cpi, partial, xrm-ms, rels, svg, xml, xsl, xsd, ps1, ps1xml, ps2, ps2xml, psc1, psc2, js, jse, vb, vbe, vbs, vbscript, ws, wsc, wsf, wsh, msh, msh1, msh2, mshxml, msh1xml, msh2xml, ad, app, application, appref-ms, asp, asx, bas, bat, chi, chm, cmd, com, cpl, crt, cer, der, eml, exe, fon, fxp, hlp, htt, inf, ins, inx, isu, isp, job, lnk, mau, mht, mhtml, mmc, msc, msg, reg, rgs, scr, sct, search-ms, settingcontent-ms, shb, shs, slk, u3p, vdx, vsx, vtx, vsdx, vssx, vstx, vsdm, vssm, vstm, vsd, vsmacros, vss, vst, vsw, xnk, cdr, dart, dc42, diskcopy42, dmg, dmgpart, dvdr, dylib, img, imgpart, ndif, service, smi, sparsebundle, sparseimage, toast, udif, action, definition, wflow, caction, as, cpgz, command, mpkg, pax, workflow, xip, mobileconfig, configprofile, internetconnect, networkconnect, pkg, deb, pet, pup, rpm, slp, out, run, bash, csh, ksh, sh, shar, tcsh, desktop, dex,apk`

## <a name="danger-level-may-vary-by-operating-system"></a>危险级别可能因操作系统而异

文件类型设置有时因客户端操作系统平台而异。 例如，`.exe` 在 Mac 上并不危险，而 `.applescript` 在 Windows 上无害。
