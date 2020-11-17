---
title: 将 Internet Explorer 模式添加到“打开方式”上下文菜单
ms.author: shisub
author: dan-wesley
manager: srugh
ms.date: 11/13/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 将 Internet Explorer 模式添加到“打开方式”上下文菜单
ms.openlocfilehash: 6453cd2587e3bec10404d2491914debb999fcf3f
ms.sourcegitcommit: e3c80274a9b8ef15761c968214b3cba593476132
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "11168479"
---
# <span data-ttu-id="4017b-103">将 Internet Explorer 模式添加到“打开方式”上下文菜单</span><span class="sxs-lookup"><span data-stu-id="4017b-103">Add Internet Explorer mode to the "Open with" context menu</span></span>

<span data-ttu-id="4017b-104">本文介绍如何将 Microsoft Edge 和 Internet Explorer 模式与桌面应用程序的文件扩展名相关联。</span><span class="sxs-lookup"><span data-stu-id="4017b-104">This article explains how to associate Microsoft Edge with Internet Explorer mode with file extensions for desktop applications.</span></span>

> [!NOTE]
> <span data-ttu-id="4017b-105">本文适用于 Microsoft Edge 版本 86 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="4017b-105">This article applies to Microsoft Edge version 86 or later.</span></span>

## <span data-ttu-id="4017b-106">与 Internet Explorer 模式的文件扩展名关联指南</span><span class="sxs-lookup"><span data-stu-id="4017b-106">Guidance for file extension association with Internet Explorer mode</span></span>

<span data-ttu-id="4017b-107">以下说明显示了一个将 Microsoft Edge 和 IE 模式与 .mht 文件类型相关联的条目。</span><span class="sxs-lookup"><span data-stu-id="4017b-107">The following instructions show an entry that associates Microsoft Edge with IE mode with the .mht file type.</span></span> <span data-ttu-id="4017b-108">请使用以下步骤作为设置文件关联的指南。</span><span class="sxs-lookup"><span data-stu-id="4017b-108">Use the following steps as a guide for setting a file association.</span></span>

> [!NOTE]
> <span data-ttu-id="4017b-109">你可以使用策略**设置默认关联配置文件**，从而将特定文件扩展名设置为默认情况下在 Internet Explorer 模式下打开。</span><span class="sxs-lookup"><span data-stu-id="4017b-109">You can set specific file extensions to open in Internet Explorer mode by default using the policy to **Set a default associations configuration file**.</span></span> <span data-ttu-id="4017b-110">有关详细信息，请参阅[策略 CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="4017b-110">For more information, see [Policy CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults#applicationdefaults-defaultassociationsconfiguration).</span></span>

1. <span data-ttu-id="4017b-111">使用 Microsoft Edge 频道定义一个新的 ProgID，用于以 Internet Explorer 模式打开。</span><span class="sxs-lookup"><span data-stu-id="4017b-111">Define a new ProgID with the Microsoft Edge channel to use to open with Internet Explorer mode.</span></span> <span data-ttu-id="4017b-112">ProgID 包括应用程序名称和图标以及 msedge.exe 的完整路径。</span><span class="sxs-lookup"><span data-stu-id="4017b-112">The ProgID includes the application name and Icon and the full path to msedge.exe.</span></span>

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\Application]
"ApplicationCompany"="Microsoft Corporation"
"ApplicationName"="Microsoft Edge with IE Mode"
"ApplicationIcon"="C:\\<edge_installation_dir>\\msedge.exe,4"
"AppUserModelId"=""
```

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\DefaultIcon]
@="C:\\<edge_installation_dir>\\msedge.exe,4"
```

2. <span data-ttu-id="4017b-113">配置 shell 更新以传递使用 IE 模式打开所需的命令行。</span><span class="sxs-lookup"><span data-stu-id="4017b-113">Configure shell updates to pass the command line needed to open with IE mode.</span></span>

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open\command]
@="\"C:\\<edge_installation_dir>\\msedge.exe\" -ie-mode-file-url -- \"%1\""
```

3. <span data-ttu-id="4017b-114">最后，将 .mht 文件扩展名与新的 ProgID 关联。</span><span class="sxs-lookup"><span data-stu-id="4017b-114">Finally, associate the .mht file extension with a new ProgID.</span></span> <span data-ttu-id="4017b-115">将你的 ProgID 添加为值名称，其值类型为 REG_SZ。</span><span class="sxs-lookup"><span data-stu-id="4017b-115">Add your ProgID as a value name, with the value type of REG_SZ.</span></span>

```markdown
[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.mht\OpenWithProgids]
"MSEdgeIEModeMHT"=hex(0):
```

<span data-ttu-id="4017b-116">设置上例中所述的注册表项后，用户将在“**打开方式**菜单上看到一个附加选项，可使用 Microsoft Edge \<channel\> 和 IE 模式打开 .mht 文件。</span><span class="sxs-lookup"><span data-stu-id="4017b-116">After you set the keys described in the previous example, your users will see an additional option on the **Open with** menu to open an .mht file using Microsoft Edge \<channel\> with IE mode.</span></span>

## <span data-ttu-id="4017b-117">注册表示例</span><span class="sxs-lookup"><span data-stu-id="4017b-117">Registry Example</span></span>

<span data-ttu-id="4017b-118">你可以将以下代码片段另存为 .reg 文件并将其导入注册表。</span><span class="sxs-lookup"><span data-stu-id="4017b-118">You can save the following code snippet as a .reg file and import it into the registry.</span></span>

```markdown
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FileExts\.mht\OpenWithProgids]
"MSEdgeIEModeMHT"=hex(0):

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT]

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\Application]
"ApplicationCompany"="Microsoft Corporation"
"ApplicationName"="Microsoft Edge with IE Mode"
"ApplicationIcon"="C:\\<edge_installation_dir>\\msedge.exe,4"
"AppUserModelId"=""

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\DefaultIcon]
@="C:\\<edge_installation_dir>\\msedge.exe,4"

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell]

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open]

[HKEY_CURRENT_USER\SOFTWARE\Classes\MSEdgeIEModeMHT\shell\open\command]
@="\"C:\\<edge_installation_dir>\\msedge.exe\" -ie-mode-file-url -- \"%1\""

```

## <span data-ttu-id="4017b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4017b-119">See also</span></span>

- [<span data-ttu-id="4017b-120">关于 IE 模式</span><span class="sxs-lookup"><span data-stu-id="4017b-120">About IE mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [<span data-ttu-id="4017b-121">可配置的网站信息</span><span class="sxs-lookup"><span data-stu-id="4017b-121">Configurable sites information</span></span>](https://docs.microsoft.com/deployedge/edge-learnmore-configurable-sites-ie-mode)
- [<span data-ttu-id="4017b-122">其他企业模式信息</span><span class="sxs-lookup"><span data-stu-id="4017b-122">Additional Enterprise Mode information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [<span data-ttu-id="4017b-123">设置文件类型关联</span><span class="sxs-lookup"><span data-stu-id="4017b-123">Setting file type associations</span></span>](https://docs.microsoft.com/windows/win32/shell/fa-file-types)
- [<span data-ttu-id="4017b-124">Microsoft Edge Enterprise 登陆页面</span><span class="sxs-lookup"><span data-stu-id="4017b-124">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
