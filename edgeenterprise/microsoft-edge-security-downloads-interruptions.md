---
title: 识别并中断下载潜在危险文件
ms.author: kvice
author: AndreaLBarr
manager: srugh
ms.date: 01/10/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 了解如何Microsoft Edge和中断下载潜在危险文件
ms.openlocfilehash: 436c85248ef4012d75a9786c36e8f48d53f720d1
ms.sourcegitcommit: e7f3098d8b7d91cae20b5778a71a87daababc312
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2022
ms.locfileid: "12298190"
---
# <a name="identify-and-interrupt-downloads-of-potentially-dangerous-files"></a>识别并中断下载潜在危险文件

Microsoft Edge文件类型策略组件按文件的"危险程度"级别对文件进行分类，以管理文件下载。 无害文件 (例如，) 可自由下载，而类似 这样的潜在危险文件则受到更高程度 `.txt` `.dll` 审查。 此审查提供了更加安全意识型的用户体验。

## <a name="how-microsoft-edge-determines-the-danger-level-of-a-file-type"></a>如何Microsoft Edge文件类型危险级别

Microsoft Edge从上游浏览器继承其文件类型Chromium策略。 您可以在 [download_file_types.asciipb 文件中查看这些文件类型及其](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb;drc=af17ad3f07c1d8a24381eb7669bec0c2ffb86521) 分类。 在此文件中，你将看到每个类型都有一个 danger_level **，这是**三个值之一 `DANGEROUS` ：、 或 `NOT_DANGEROUS` `ALLOW_ON_USER_GESTURE` 。

以下两种分类很简单：

- **NOT_DANGEROUS** 意味着文件可安全下载，即使下载请求是意外的。
- **危险** 意味着浏览器应始终警告用户该下载可能会损害其设备。

第三个设置 **ALLOW_ON_USER_GESTURE** 更为细微。 这些文件具有潜在危险，但如果用户请求下载，则最有可能是无害的。 Microsoft Edge满足下列条件之一时，系统将自动允许这些下载继续：

- 有一 [个与启动](https://textslashplain.com/2020/05/18/browser-basics-user-gestures/) 下载的网络请求关联的用户手势。 例如，用户单击了指向下载的链接。
- 在访问引用源之前有一个记录 (，该页面在最近的午夜) 之前（即昨天或 (日）之前链接到下载) 。 此记录的访问意味着用户具有访问网站的历史记录。

如果用户使用"将链接另存为上下文"菜单命令显式启动下载，**** 将下载的 URL 直接输入浏览器的地址栏中，或者 Microsoft Defender SmartScreen 指示文件安全，下载也将自动继续。

> [!NOTE]
> 从版本 91 开始，Microsoft Edge缺少所需手势的下载中断。

## <a name="user-experience-for-downloads-that-lack-a-gesture"></a>缺少手势的下载的用户体验

如果在没有所需手势的情况下启动对潜在危险类型的下载，Microsoft Edge下载"已被阻止"。 名为 `Keep` 和 `Delete` 的命令在 **... 中可用。**  (下载) 省略号选项，以允许用户继续或取消下载。

:::image type="content" source="media/microsoft-edge-security-Download-interruptions/Dowload-was-blocked.png" alt-text="下载被阻止，用户可以保留或删除下载。":::

在 `edge://downloads` 页面上，用户将看到相同的选项。 下一个屏幕截图显示了这些选项和示例。

:::image type="content" source="media/microsoft-edge-security-Download-interruptions/msg-keep-delete-option.png" alt-text="下载被阻止，但用户可以保留或删除下载。":::

## <a name="enterprise-controls-for-downloads"></a>Enterprise下载的控件

虽然用户不太可能在每天使用的网站上遇到中断，但他们可能会在很少使用的网站上进行合法下载时遇到这种情况。 为了帮助简化企业用户体验，可以使用组策略。

企业可以使用 [ExemptDomainFileTypePairsFromFileTypeDownloadWarnings](/deployedge/microsoft-edge-policies#exemptdomainfiletypepairsfromfiletypedownloadwarnings) 指定允许从特定站点不间断下载的文件类型。 例如，以下策略允许 XML 文件从 contoso.com 和 woodgrovebank.com 且不会中断，MSG 文件可以从任何网站下载。

`[{"file_extension":"xml","domains":["contoso.com", "woodgrovebank.com"]},
{"file_extension":"msg", "domains": ["*"]}]`

## <a name="file-types-requiring-a-gesture"></a>需要手势的文件类型

最新的 [文件类型策略](https://source.chromium.org/chromium/chromium/src/+/main:components/safe_browsing/core/resources/download_file_types.asciipb;drc=af17ad3f07c1d8a24381eb7669bec0c2ffb86521) 已在 Chromium 源代码中发布。 自 2021 年 5 月起，至少一个操作系统平台上具有 `ALLOW_ON_USER_GESTURE` 的 `danger_level` 的文件类型包括：
`crx, pl, py, pyc, pyo, pyw, rb, efi, oxt, msi, msp, mst, ade, adp, mad, maf, mag, mam, maq, mar, mas, mat, mav, maw, mda, mdb, mde, mdt, mdw, mdz, accdb, accde, accdr, accda, ocx, ops, paf, pcd, pif, plg, prf, prg, pst, cpi, partial, xrm-ms, rels, svg, xml, xsl, xsd, ps1, ps1xml, ps2, ps2xml, psc1, psc2, js, jse, vb, vbe, vbs, vbscript, ws, wsc, wsf, wsh, msh, msh1, msh2, mshxml, msh1xml, msh2xml, ad, app, application, appref-ms, asp, asx, bas, bat, chi, chm, cmd, com, cpl, crt, cer, der, eml, exe, fon, fxp, hlp, htt, inf, ins, inx, isu, isp, job, lnk, mau, mht, mhtml, mmc, msc, msg, reg, rgs, scr, sct, search-ms, settingcontent-ms, shb, shs, slk, u3p, vdx, vsx, vtx, vsdx, vssx, vstx, vsdm, vssm, vstm, vsd, vsmacros, vss, vst, vsw, xnk, cdr, dart, dc42, diskcopy42, dmg, dmgpart, dvdr, dylib, img, imgpart, ndif, service, smi, sparsebundle, sparseimage, toast, udif, action, definition, wflow, caction, as, cpgz, command, mpkg, pax, workflow, xip, mobileconfig, configprofile, internetconnect, networkconnect, pkg, deb, pet, pup, rpm, slp, out, run, bash, csh, ksh, sh, shar, tcsh, desktop, dex,apk`

## <a name="the-file-type-danger-level-may-vary-by-operating-system"></a>文件类型危险级别可能因操作系统而异

文件类型设置有时因客户端操作系统平台而异。 例如，文件在 Mac 上不危险，而文件在 mac 上 `.exe` `.applescript` Windows。
