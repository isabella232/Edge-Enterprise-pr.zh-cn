---
title: Microsoft Edge 企业隐私设置
ms.author: likravit
author: dan-wesley
manager: srugh
ms.date: 05/26/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 配置 Microsoft Edge 企业隐私设置
ms.openlocfilehash: 2b7a33087ae5110c53d18b3192486d4ae62fa540
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979358"
---
# <span data-ttu-id="184b7-103">配置 Microsoft Edge 策略以支持企业隐私</span><span class="sxs-lookup"><span data-stu-id="184b7-103">Configure Microsoft Edge policies to support enterprise privacy</span></span>

<span data-ttu-id="184b7-104">Microsoft 致力于为企业提供在 Microsoft Edge 中进行与数据收集相关的选择所需的信息和控制。</span><span class="sxs-lookup"><span data-stu-id="184b7-104">Microsoft is committed to providing enterprises with the information and controls needed to make choices about data collection in Microsoft Edge.</span></span>

## <span data-ttu-id="184b7-105">概述</span><span class="sxs-lookup"><span data-stu-id="184b7-105">Overview</span></span>

<span data-ttu-id="184b7-106">默认情况下，部署在非 Windows 平台上的 Microsoft Edge 不会将诊断数据或网站信息发送到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="184b7-106">By default, Microsoft Edge deployed on non-Windows platforms doesn't send diagnostic data or site information to Microsoft.</span></span> <span data-ttu-id="184b7-107">将 Microsoft Edge 部署到 Windows 10 时，默认会根据用户的 [Windows 诊断数据设置](https://go.microsoft.com/fwlink/?linkid=2099569)发送诊断数据。</span><span class="sxs-lookup"><span data-stu-id="184b7-107">When Microsoft Edge is deployed on Windows 10, the default is to send diagnostic data based on the users' [Windows Diagnostic data setting](https://go.microsoft.com/fwlink/?linkid=2099569).</span></span>

<span data-ttu-id="184b7-108">你也可以使用以下组策略配置 Microsoft Edge 处理组织数据收集的方式：</span><span class="sxs-lookup"><span data-stu-id="184b7-108">You can also configure how Microsoft Edge handles data collection for your organization with the following group policies:</span></span>

- <span data-ttu-id="184b7-109">[MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled)：启用使用情况和故障相关数据报告。</span><span class="sxs-lookup"><span data-stu-id="184b7-109">[MetricsReportingEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#metricsreportingenabled) - Enable usage and crash-related data reporting.</span></span>
- <span data-ttu-id="184b7-110">[SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices)：发送站点信息以改进 Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="184b7-110">[SendSiteInfoToImproveServices](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#sendsiteinfotoimproveservices) - Send site information to improve Microsoft services.</span></span>

## <span data-ttu-id="184b7-111">配置策略设置</span><span class="sxs-lookup"><span data-stu-id="184b7-111">Configure policy settings</span></span>

<span data-ttu-id="184b7-112">开始之前，请先下载并使用最新的 Microsoft Edge 策略模板（有关详细信息，请参阅[配置 Microsoft Edge](configure-microsoft-edge.md)。）</span><span class="sxs-lookup"><span data-stu-id="184b7-112">Before you begin, download and use the latest Microsoft Edge Policy Template (For more information, see [Configure Microsoft Edge](configure-microsoft-edge.md).)</span></span>

### <span data-ttu-id="184b7-113">启用使用情况和故障相关数据报告</span><span class="sxs-lookup"><span data-stu-id="184b7-113">Enable usage and crash-related data reporting</span></span>

<span data-ttu-id="184b7-114">此策略允许向 Microsoft 发送关于 Microsoft Edge 的使用情况和故障相关数据的报告。</span><span class="sxs-lookup"><span data-stu-id="184b7-114">This policy enables reporting of usage and crash-related data about Microsoft Edge to Microsoft.</span></span>

<span data-ttu-id="184b7-115">Microsoft Edge 收集一系列必需的数据，以确保产品保持最新状态、安全可靠且正常运行。</span><span class="sxs-lookup"><span data-stu-id="184b7-115">Microsoft Edge collects a set of required data that's necessary to keep the product up to date, secure, and performing properly.</span></span> <span data-ttu-id="184b7-116">此数据包括来自 Microsoft Edge 的有关 Microsoft Edge 安装的当前数据收集许可、应用版本和安装状态的基本设备连接和配置信息。</span><span class="sxs-lookup"><span data-stu-id="184b7-116">This data includes basic device connectivity and configuration information from Microsoft Edge about the current data collection consent, app version, and installation state about your installation of Microsoft Edge.</span></span><span data-ttu-id="184b7-117">通过禁用策略可关闭此数据集合。</span><span class="sxs-lookup"><span data-stu-id="184b7-117"> This data collection can be turned off by disabling the policy.</span></span>

<span data-ttu-id="184b7-118">启用此策略可向 Microsoft 发送使用情况和故障相关数据的报告。</span><span class="sxs-lookup"><span data-stu-id="184b7-118">Enable this policy to send reporting of usage and crash-related data to Microsoft.</span></span> <span data-ttu-id="184b7-119">禁用此策略可以不将数据发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="184b7-119">Disable this policy to not send the data to Microsoft.</span></span> <span data-ttu-id="184b7-120">在这两种情况下，用户不能更改或覆盖设置。</span><span class="sxs-lookup"><span data-stu-id="184b7-120">In both cases, users can't change or override the setting.</span></span>

<span data-ttu-id="184b7-121">在 Windows 10 上运行 Microsoft Edge 时：</span><span class="sxs-lookup"><span data-stu-id="184b7-121">When Microsoft Edge is running on Windows 10:</span></span>

- <span data-ttu-id="184b7-122">如果未配置此策略，Microsoft Edge 将默认使用 Windows 诊断数据设置。</span><span class="sxs-lookup"><span data-stu-id="184b7-122">If this policy isn't configured, Microsoft Edge will default to the Windows diagnostic data setting.</span></span>
- <span data-ttu-id="184b7-123">如果启用此策略，则只有将 Windows 诊断数据设置设为**增强**或**完整**时，Microsoft Edge 才会发送使用情况数据。</span><span class="sxs-lookup"><span data-stu-id="184b7-123">If this policy is enabled, Microsoft Edge will only send usage data if the Windows Diagnostic data setting is set to **Enhanced** or **Full**.</span></span>
- <span data-ttu-id="184b7-124">如果禁用此策略，Microsoft Edge 将不会发送使用情况数据。</span><span class="sxs-lookup"><span data-stu-id="184b7-124">If this policy is disabled, Microsoft Edge will not send usage data.</span></span> <span data-ttu-id="184b7-125">基于 Windows 诊断数据设置发送故障相关数据。</span><span class="sxs-lookup"><span data-stu-id="184b7-125">Crash-related data is sent based on the Windows Diagnostic data setting.</span></span> <span data-ttu-id="184b7-126">[详细了解 Windows 诊断数据设置](https://go.microsoft.com/fwlink/?linkid=2099569)。</span><span class="sxs-lookup"><span data-stu-id="184b7-126">[Learn more about Windows Diagnostic data settings](https://go.microsoft.com/fwlink/?linkid=2099569).</span></span>

<span data-ttu-id="184b7-127">在 Windows 7、8 和 macOS 上运行 Microsoft Edge 时：</span><span class="sxs-lookup"><span data-stu-id="184b7-127">When Microsoft Edge is running on Windows 7, 8, and macOS:</span></span>

- <span data-ttu-id="184b7-128">如果未配置此策略，Microsoft Edge 将默认使用用户的首选项。</span><span class="sxs-lookup"><span data-stu-id="184b7-128">If this policy isn't configured, Microsoft Edge will default to the user's preference.</span></span>

### <span data-ttu-id="184b7-129">发送站点信息以改进 Microsoft 服务</span><span class="sxs-lookup"><span data-stu-id="184b7-129">Send site information to improve Microsoft services</span></span>

<span data-ttu-id="184b7-130">此策略支持将有关在 Microsoft Edge 中访问的网站的信息发送到 Microsoft，以改进 Microsoft 产品和服务（如搜索）。</span><span class="sxs-lookup"><span data-stu-id="184b7-130">This policy enables sending information about websites visited in Microsoft Edge to Microsoft to improve Microsoft products and services such as search.</span></span>

<span data-ttu-id="184b7-131">启用此策略可将有关在 Microsoft Edge 中访问的网站的信息发送到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="184b7-131">Enable this policy to send information about websites visited in Microsoft Edge to Microsoft.</span></span> <span data-ttu-id="184b7-132">禁用此策略以便不将有关在 Microsoft Edge 中访问的网站的信息发送到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="184b7-132">Disable this policy to not send information about the websites that are visited in Microsoft Edge to Microsoft.</span></span> <span data-ttu-id="184b7-133">在这两种情况下，用户不能更改或覆盖设置。</span><span class="sxs-lookup"><span data-stu-id="184b7-133">In both cases, users can't change or override the setting.</span></span>

<span data-ttu-id="184b7-134">在 Windows 10 上运行 Microsoft Edge 时：</span><span class="sxs-lookup"><span data-stu-id="184b7-134">When Microsoft Edge is running on Windows 10:</span></span>

- <span data-ttu-id="184b7-135">如果未配置此策略，Microsoft Edge 将默认使用 Windows 诊断数据设置。</span><span class="sxs-lookup"><span data-stu-id="184b7-135">If this policy isn't configured, Microsoft Edge will default to the Windows diagnostic data setting.</span></span>
- <span data-ttu-id="184b7-136">如果启用此策略，则只有将 Windows 诊断数据设置设为**完整**时，Microsoft Edge 才会发送有关所访问网站的信息。</span><span class="sxs-lookup"><span data-stu-id="184b7-136">If this policy is enabled, Microsoft Edge will only send information about the websites that are visited if the Windows Diagnostic data setting is set to **Full**.</span></span>
- <span data-ttu-id="184b7-137">如果禁用此策略，Microsoft Edge 将不会发送有关所访问网站的信息。</span><span class="sxs-lookup"><span data-stu-id="184b7-137">If this policy is disabled, Microsoft Edge will not send info about websites visited.</span></span> <span data-ttu-id="184b7-138">要[详细了解 Windows 诊断数据设置](https://go.microsoft.com/fwlink/?linkid=2099569)，请执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="184b7-138">To [learn more about Windows Diagnostic data settings](https://go.microsoft.com/fwlink/?linkid=2099569).</span></span>

<span data-ttu-id="184b7-139">在 Windows 7、8 和 macOS 上运行 Microsoft Edge 时：</span><span class="sxs-lookup"><span data-stu-id="184b7-139">When Microsoft Edge is running on Windows 7, 8, and macOS:</span></span>

- <span data-ttu-id="184b7-140">如果未配置此策略，Microsoft Edge 将默认使用用户的首选项。</span><span class="sxs-lookup"><span data-stu-id="184b7-140">If this policy isn't configured, Microsoft Edge will default to the user's preference.</span></span>

## <span data-ttu-id="184b7-141">实现详细信息</span><span class="sxs-lookup"><span data-stu-id="184b7-141">Implementation details</span></span>

<span data-ttu-id="184b7-142">为了让 Windows 10 了解我们的实现及其对 Windows 诊断数据设置的依赖性，下表介绍了相关配置（如果未配置**启用使用情况和故障相关数据报告**和**发送站点信息以改进 Microsoft 服务**）。</span><span class="sxs-lookup"><span data-stu-id="184b7-142">For Windows 10 to understand our implementation with the dependency on the Windows Diagnostic data setting, the following table describes our configuration if **Enable usage and crash-related data reporting** and **Send site information to improve Microsoft services** were not configured.</span></span>

| <span data-ttu-id="184b7-143">Windows 诊断数据设置</span><span class="sxs-lookup"><span data-stu-id="184b7-143">Windows Diagnostic data setting</span></span> | <span data-ttu-id="184b7-144">启用使用情况和故障相关数据报告</span><span class="sxs-lookup"><span data-stu-id="184b7-144">Enable usage and crash-related data reporting</span></span> | <span data-ttu-id="184b7-145">发送站点信息以改进 Microsoft 服务</span><span class="sxs-lookup"><span data-stu-id="184b7-145">Send site information to improve Microsoft services</span></span> |
|---------------------------------|-----------------------------------------------|-----------------------------------------------------|
| <span data-ttu-id="184b7-146">安全性</span><span class="sxs-lookup"><span data-stu-id="184b7-146">Security</span></span>                        | <span data-ttu-id="184b7-147">未发送</span><span class="sxs-lookup"><span data-stu-id="184b7-147">Not sent</span></span>                                      | <span data-ttu-id="184b7-148">未发送</span><span class="sxs-lookup"><span data-stu-id="184b7-148">Not sent</span></span>                                            |
| <span data-ttu-id="184b7-149">基本</span><span class="sxs-lookup"><span data-stu-id="184b7-149">Basic</span></span>                           | <span data-ttu-id="184b7-150">未发送</span><span class="sxs-lookup"><span data-stu-id="184b7-150">Not sent</span></span>                                      | <span data-ttu-id="184b7-151">未发送</span><span class="sxs-lookup"><span data-stu-id="184b7-151">Not sent</span></span>                                            |
| <span data-ttu-id="184b7-152">增强</span><span class="sxs-lookup"><span data-stu-id="184b7-152">Enhanced</span></span>                        | <span data-ttu-id="184b7-153">已发送</span><span class="sxs-lookup"><span data-stu-id="184b7-153">Sent</span></span>                                          | <span data-ttu-id="184b7-154">未发送</span><span class="sxs-lookup"><span data-stu-id="184b7-154">Not sent</span></span>                                            |
| <span data-ttu-id="184b7-155">完整</span><span class="sxs-lookup"><span data-stu-id="184b7-155">Full</span></span>                            | <span data-ttu-id="184b7-156">已发送</span><span class="sxs-lookup"><span data-stu-id="184b7-156">Sent</span></span>                                          | <span data-ttu-id="184b7-157">已发送</span><span class="sxs-lookup"><span data-stu-id="184b7-157">Sent</span></span>                                                |

<span data-ttu-id="184b7-158">根据先前的表，如果 Windows 10 的配置不正确，我们将恢复为较小的数据收集设置。</span><span class="sxs-lookup"><span data-stu-id="184b7-158">If your configurations for Windows 10 are misconfigured in accordance with the preceding table, we will fall back to the lesser data collection setting.</span></span>

<span data-ttu-id="184b7-159">例如：</span><span class="sxs-lookup"><span data-stu-id="184b7-159">For example:</span></span>

- <span data-ttu-id="184b7-160">将“启用使用情况和故障相关数据报告”策略设置为**已启用**，但将 Windows 诊断数据设置设为**基本**。</span><span class="sxs-lookup"><span data-stu-id="184b7-160">You set the "Enable usage and crash-related data reporting" policy to **Enabled** but the Windows Diagnostic data setting is set to **Basic**.</span></span> <span data-ttu-id="184b7-161">我们不会发送使用情况和故障相关数据。</span><span class="sxs-lookup"><span data-stu-id="184b7-161">We won't send usage and crash-related data.</span></span>
- <span data-ttu-id="184b7-162">已将“发送网站信息以改进 Microsoft 服务”策略设置为**已禁用**，但将 Windows 诊断数据设置设为**完整**。</span><span class="sxs-lookup"><span data-stu-id="184b7-162">You set the "Send site information to improve Microsoft services" policy to **Disabled** but the Windows Diagnostic data setting is set to **Full**.</span></span> <span data-ttu-id="184b7-163">我们不会发送有关所访问网站的信息。</span><span class="sxs-lookup"><span data-stu-id="184b7-163">We won't send information about the sites that are visited.</span></span>

<span data-ttu-id="184b7-164">对先前设置的正确实现方法是将“启用使用情况和故障相关数据报告”策略设为**已启用**，然后将 Windows 诊断数据设置设为**增强**或**完整**。</span><span class="sxs-lookup"><span data-stu-id="184b7-164">The correct implementation for the previous settings is to set the "Enable usage and crash-related data reporting" policy to **Enabled** and set the Windows Diagnostic data setting to **Enhanced** or **Full**.</span></span>

## <span data-ttu-id="184b7-165">其他隐私策略选项</span><span class="sxs-lookup"><span data-stu-id="184b7-165">Additional privacy policy options</span></span>

<span data-ttu-id="184b7-166">你可能需要考虑以下与数据隐私相关的组策略：</span><span class="sxs-lookup"><span data-stu-id="184b7-166">You may want to consider the following group policies related to data privacy:</span></span>

- <span data-ttu-id="184b7-167">在特定站点上阻止 Cookie</span><span class="sxs-lookup"><span data-stu-id="184b7-167">Block cookies on specific sites</span></span>
- <span data-ttu-id="184b7-168">阻止第三方 Cookie</span><span class="sxs-lookup"><span data-stu-id="184b7-168">Block third-party cookies</span></span>
- <span data-ttu-id="184b7-169">配置 Do Not Track</span><span class="sxs-lookup"><span data-stu-id="184b7-169">Configure Do Not Track</span></span>
- <span data-ttu-id="184b7-170">禁用 InPrivate 模式</span><span class="sxs-lookup"><span data-stu-id="184b7-170">Disable InPrivate mode</span></span>

## <span data-ttu-id="184b7-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="184b7-171">See also</span></span>

- [<span data-ttu-id="184b7-172">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="184b7-172">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="184b7-173">Microsoft Edge 策略</span><span class="sxs-lookup"><span data-stu-id="184b7-173">Microsoft Edge policies</span></span>](microsoft-edge-policies.md)
- [<span data-ttu-id="184b7-174">Microsoft Edge 隐私白皮书</span><span class="sxs-lookup"><span data-stu-id="184b7-174">Microsoft Edge Privacy Whitepaper</span></span>](https://docs.microsoft.com/microsoft-edge/privacy-whitepaper)
