---
title: 在 Enterprise Mode Site List 中配置网站
ms.author: cjacks
author: cjacks
manager: saudm
ms.date: 05/28/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 配置 Enterprise Mode Site List
ms.openlocfilehash: 969a4f6001dbe08a51c26ecf35812b101d315a59
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979349"
---
# <span data-ttu-id="7d361-103">在 Enterprise Mode Site List 中配置网站</span><span class="sxs-lookup"><span data-stu-id="7d361-103">Configure Sites on the Enterprise Mode Site List</span></span>

<span data-ttu-id="7d361-104">本文介绍了对 Enterprise Mode Site List 的更改，此列表支持配置用于 Microsoft Edge 版本 77 及更高版本的 IE 模式。</span><span class="sxs-lookup"><span data-stu-id="7d361-104">This article describes changes to the Enterprise Mode Site List that support configuring IE mode for Microsoft Edge version 77 and later.</span></span>

<span data-ttu-id="7d361-105">若要详细了解 Enterprise Mode Site List XML 文件的架构，请参阅[企业模式架构 v.2 指南](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)。</span><span class="sxs-lookup"><span data-stu-id="7d361-105">For more information on the schema for the Enterprise Mode Site List XML file, see [Enterprise Mode schema v.2 guidance](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>

> [!NOTE]
> <span data-ttu-id="7d361-106">本文适用于 Microsoft Edge **Stable**、**Beta** 和 **Dev** 渠道版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7d361-106">This article applies to Microsoft Edge **Stable**, **Beta** and **Dev** Channels, version 77 or later.</span></span>

## <span data-ttu-id="7d361-107">已更新的架构元素</span><span class="sxs-lookup"><span data-stu-id="7d361-107">Updated schema elements</span></span>

<span data-ttu-id="7d361-108">下表描述了添加到企业模式架构 v.2 中的 \<open-in app\> 元素：</span><span class="sxs-lookup"><span data-stu-id="7d361-108">The following table describes the \<open-in app\> element added to the v.2 of the Enterprise Mode schema:</span></span>

| **<span data-ttu-id="7d361-109">元素</span><span class="sxs-lookup"><span data-stu-id="7d361-109">Element</span></span>** | **<span data-ttu-id="7d361-110">描述</span><span class="sxs-lookup"><span data-stu-id="7d361-110">Description</span></span>** |
| --- | --- |
| \<open-in app="**true**"\> | <span data-ttu-id="7d361-111">控制哪个浏览器用于站点的子元素。</span><span class="sxs-lookup"><span data-stu-id="7d361-111">A child element that controls what browser is used for sites.</span></span> <span data-ttu-id="7d361-112">对于需要**在 IE11 中打开**的站点，此元素是必需的。</span><span class="sxs-lookup"><span data-stu-id="7d361-112">This element is required for sites that need to **open in IE11**.</span></span>|

**<span data-ttu-id="7d361-113">示例：</span><span class="sxs-lookup"><span data-stu-id="7d361-113">Example:</span></span>**

``` xml
<site url="contoso.com">

  <open-in app="true">IE11</open-in>

</site>
```

<span data-ttu-id="7d361-114">下表显示了 \<open-in\> 元素的可能值：</span><span class="sxs-lookup"><span data-stu-id="7d361-114">The following table shows the possible values of the \<open-in\> element:</span></span>

| **<span data-ttu-id="7d361-115">值</span><span class="sxs-lookup"><span data-stu-id="7d361-115">Value</span></span>** | **<span data-ttu-id="7d361-116">描述</span><span class="sxs-lookup"><span data-stu-id="7d361-116">Description</span></span>** |
| --- | --- |
| **\<open-in\><span data-ttu-id="7d361-117">IE11</span><span class="sxs-lookup"><span data-stu-id="7d361-117">IE11</span></span>\</open-in\>** | <span data-ttu-id="7d361-118">在 IE 模式下或在完整的 IE11 窗口中打开网站。</span><span class="sxs-lookup"><span data-stu-id="7d361-118">Opens the site in IE mode or a full IE11 window.</span></span> <span data-ttu-id="7d361-119">若要启用 IE 模式，请参阅[配置 IE 模式策略](https://docs.microsoft.com/deployedge/edge-ie-mode-policies)</span><span class="sxs-lookup"><span data-stu-id="7d361-119">To enable IE mode, see [Configure IE mode policies](https://docs.microsoft.com/deployedge/edge-ie-mode-policies)</span></span>|
| **\<open-in app="**true**"\><span data-ttu-id="7d361-120">IE11</span><span class="sxs-lookup"><span data-stu-id="7d361-120">IE11</span></span>\</open-in\>** | <span data-ttu-id="7d361-121">在完整的 IE11 窗口中打开网站</span><span class="sxs-lookup"><span data-stu-id="7d361-121">Opens the site in a full IE11 window</span></span> |
| **\<open-in\><span data-ttu-id="7d361-122">MSEdge</span><span class="sxs-lookup"><span data-stu-id="7d361-122">MSEdge</span></span>\</open-in\>** | <span data-ttu-id="7d361-123">在 Microsoft Edge 中打开网站</span><span class="sxs-lookup"><span data-stu-id="7d361-123">Opens the site in Microsoft Edge</span></span> |
| **\<open-in\><span data-ttu-id="7d361-124">无或未指定</span><span class="sxs-lookup"><span data-stu-id="7d361-124">None or not specified</span></span>\</open-in\>** | <span data-ttu-id="7d361-125">在默认浏览器中或在用户导航到网站所用的浏览器中打开网站。</span><span class="sxs-lookup"><span data-stu-id="7d361-125">Opens the site in the default browser or in the browser where the user navigated to the site.</span></span> |
|**\<open-in\><span data-ttu-id="7d361-126">可配置</span><span class="sxs-lookup"><span data-stu-id="7d361-126">Configurable</span></span>\</open-in\>** | <span data-ttu-id="7d361-127">允许网站参与 IE 模式引擎确定。</span><span class="sxs-lookup"><span data-stu-id="7d361-127">Allows the site to participate in IE mode engine determination.</span></span> <span data-ttu-id="7d361-128">若要了解详细信息，请参阅[了解 IE 模式下的可配置网站](edge-learnmore-configurable-sites-ie-mode.md)。</span><span class="sxs-lookup"><span data-stu-id="7d361-128">To learn more, see [Learn about Configurable sites in IE mode](edge-learnmore-configurable-sites-ie-mode.md).</span></span>  |

>[!NOTE]
> <span data-ttu-id="7d361-129">仅当与 _"open-in" IE11_ 关联时，才可识别属性 app=**"true"**。</span><span class="sxs-lookup"><span data-stu-id="7d361-129">The attribute app=**"true"** is only recognized when associated to _'open-in' IE11_.</span></span> <span data-ttu-id="7d361-130">将其添加到其他“open-in”元素不会更改浏览器行为。</span><span class="sxs-lookup"><span data-stu-id="7d361-130">Adding it to the other 'open-in' elements won't change browser behavior.</span></span>   

## <span data-ttu-id="7d361-131">配置非特定网站</span><span class="sxs-lookup"><span data-stu-id="7d361-131">Configure neutral sites</span></span>

<span data-ttu-id="7d361-132">必须将身份验证/单一登录服务器显式配置为中性网站，IE 模式才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="7d361-132">In order for IE mode to work properly, authentication / Single Sign-On servers will need to be explicitly configured as neutral sites.</span></span> <span data-ttu-id="7d361-133">否则，IE 模式网页会尝试重定向到 Microsoft Edge，且身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="7d361-133">Otherwise, IE mode pages will try to redirect to Microsoft Edge, and authentication will fail.</span></span>

<span data-ttu-id="7d361-134">中性网站使用导航起始浏览器，要么是 Microsoft Edge，要么是 IE 模式。</span><span class="sxs-lookup"><span data-stu-id="7d361-134">A neutral site will use the browser where the navigation started - either Microsoft Edge or IE mode.</span></span> <span data-ttu-id="7d361-135">配置中性网站可确保所有使用这些身份验证服务器的应用程序（无论是新式应用程序还是旧应用程序）都能继续正常运行。</span><span class="sxs-lookup"><span data-stu-id="7d361-135">Configuring neutral sites ensures that all applications using these authentication servers, both modern and legacy, continue to work.</span></span>

<span data-ttu-id="7d361-136">可以通过在 Enterprise Mode Site List Manager 工具中将*打开方式*下拉列表设置为“无”或直接更新站点列表 XML 来配置中性站点：</span><span class="sxs-lookup"><span data-stu-id="7d361-136">You can configure neutral sites by setting the *Open In* dropdown to 'None' in the Enterprise Mode Site List Manager tool or by directly updating the site list XML:</span></span>

``` xml
<site url="login.contoso.com">
   
    <open-in>None</open-in>

</site>
```

<span data-ttu-id="7d361-137">若要识别身份验证服务器，请使用 IE11 开发人员工具检查来自应用程序的网络流量。</span><span class="sxs-lookup"><span data-stu-id="7d361-137">To identify authentication servers, inspect the network traffic from an application using the IE11 Developer Tools.</span></span> <span data-ttu-id="7d361-138">如果需要更多时间来识别身份验证服务器，可以将策略配置为让所有页内导航都一直使用 IE 模式。</span><span class="sxs-lookup"><span data-stu-id="7d361-138">If you need more time to identify your authentication servers, you can configure a policy to keep all in-page navigation in IE mode.</span></span> <span data-ttu-id="7d361-139">为了最大限度地减少 IE 模式的使用，在识别身份验证服务器并将它们添加到网站列表后，请禁用此设置。</span><span class="sxs-lookup"><span data-stu-id="7d361-139">To minimize the use of IE mode, disable this setting once you've identified and added your authentication servers to the site list.</span></span> <span data-ttu-id="7d361-140">有关详细信息，请参阅[将页内导航配置为一直使用 IE 模式](https://docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationsiteredirect)。</span><span class="sxs-lookup"><span data-stu-id="7d361-140">For more information, see [Configure in-page navigation to remain in IE mode](https://docs.microsoft.com/deployedge/microsoft-edge-policies#internetexplorerintegrationsiteredirect).</span></span>

>[!NOTE]
   ><span data-ttu-id="7d361-141">IE 模式集成不支持企业模式架构 v.1。</span><span class="sxs-lookup"><span data-stu-id="7d361-141">Enterprise Mode schema v.1 isn't supported for IE mode integration.</span></span> <span data-ttu-id="7d361-142">如果当前正在将架构 v.1 与 Internet Explorer 11 一起使用，则必须升级到架构 v.2。</span><span class="sxs-lookup"><span data-stu-id="7d361-142">If you are currently using schema v.1 with Internet Explorer 11, you must upgrade to schema v.2.</span></span> <span data-ttu-id="7d361-143">有关详细信息，请参阅[企业模式架构 v.2 指南](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance)。</span><span class="sxs-lookup"><span data-stu-id="7d361-143">For more information, see [Enterprise Mode schema v.2 guidance](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-schema-version-2-guidance).</span></span>

## <span data-ttu-id="7d361-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d361-144">See also</span></span>

- [<span data-ttu-id="7d361-145">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="7d361-145">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="7d361-146">关于 IE 模式</span><span class="sxs-lookup"><span data-stu-id="7d361-146">About IE mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [<span data-ttu-id="7d361-147">其他企业模式信息</span><span class="sxs-lookup"><span data-stu-id="7d361-147">Additional Enterprise Mode information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)