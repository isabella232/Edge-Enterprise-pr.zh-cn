---
title: Microsoft Edge 企业隐私设置
ms.author: collw
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 配置 Microsoft Edge 企业隐私设置
ms.openlocfilehash: b5b07353af558e3832cb7a08c647fa111a14a404
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642268"
---
# <a name="configure-microsoft-edge-policies-to-support-enterprise-privacy"></a><span data-ttu-id="600f4-103">配置 Microsoft Edge 策略以支持企业隐私</span><span class="sxs-lookup"><span data-stu-id="600f4-103">Configure Microsoft Edge policies to support enterprise privacy</span></span>

<span data-ttu-id="600f4-104">Microsoft 致力于为企业提供在 Microsoft Edge 中进行与数据收集相关的选择所需的信息和控制。</span><span class="sxs-lookup"><span data-stu-id="600f4-104">Microsoft is committed to providing enterprises with the information and controls needed to make choices about data collection in Microsoft Edge.</span></span>

## <a name="overview"></a><span data-ttu-id="600f4-105">概述</span><span class="sxs-lookup"><span data-stu-id="600f4-105">Overview</span></span>

<span data-ttu-id="600f4-106">将 Microsoft Edge 部署到 Windows 10 时，默认会根据用户的 [Windows 诊断数据设置](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)发送诊断数据。</span><span class="sxs-lookup"><span data-stu-id="600f4-106">When Microsoft Edge is deployed on Windows 10, the default is to send diagnostic data based on the users' [Windows Diagnostic data setting](/windows/privacy/configure-windows-diagnostic-data-in-your-organization).</span></span>

<span data-ttu-id="600f4-107">将 Microsoft Edge 部署到非 Windows 平台上时，将按照以下组策略的设置收集诊断数据：</span><span class="sxs-lookup"><span data-stu-id="600f4-107">When Microsoft Edge is deployed on non-Windows platforms, diagnostic data is collected according to the settings of the following group policies:</span></span>

- <span data-ttu-id="600f4-108">（已弃用）[MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled)：启用使用情况和故障相关数据报告。</span><span class="sxs-lookup"><span data-stu-id="600f4-108">(DEPRECATED) [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) - Enable usage and crash-related data reporting.</span></span> <span data-ttu-id="600f4-109">此策略将在 Microsoft Edge 版本 89 中过时。</span><span class="sxs-lookup"><span data-stu-id="600f4-109">This policy will be obsolete in Microsoft Edge version 89.</span></span>
- <span data-ttu-id="600f4-110">（已弃用）[SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices)：发送站点信息以改进 Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="600f4-110">(DEPRECATED) [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) - Send site information to improve Microsoft services.</span></span> <span data-ttu-id="600f4-111">此策略将在 Microsoft Edge 版本 89 中过时。</span><span class="sxs-lookup"><span data-stu-id="600f4-111">This policy will be obsolete in Microsoft Edge version 89.</span></span>

<span data-ttu-id="600f4-112">之前已弃用的策略将被 Windows 10 上的[允许遥测](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)和所有其他平台的[DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) 策略取代。</span><span class="sxs-lookup"><span data-stu-id="600f4-112">The preceding deprecated policies are replaced by [Allow Telemetry](/windows/privacy/configure-windows-diagnostic-data-in-your-organization) on Windows 10, and [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) policy for all other platforms.</span></span>  

## <a name="configure-policy-settings"></a><span data-ttu-id="600f4-113">配置策略设置</span><span class="sxs-lookup"><span data-stu-id="600f4-113">Configure policy settings</span></span>

<span data-ttu-id="600f4-114">开始之前，请先下载并使用最新的 Microsoft Edge 策略模板（有关详细信息，请参阅[配置 Microsoft Edge](configure-microsoft-edge.md)。）</span><span class="sxs-lookup"><span data-stu-id="600f4-114">Before you begin, download and use the latest Microsoft Edge Policy Template (For more information, see [Configure Microsoft Edge](configure-microsoft-edge.md).)</span></span>

### <a name="send-required-and-optional-diagnostic-data-about-browser-usage"></a><span data-ttu-id="600f4-115">发送有关浏览器使用情况的必需和可选诊断数据</span><span class="sxs-lookup"><span data-stu-id="600f4-115">Send required and optional diagnostic data about browser usage</span></span>

<span data-ttu-id="600f4-116">如果已配置 [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) 策略，则其优先级高于 [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) 和[SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices)。</span><span class="sxs-lookup"><span data-stu-id="600f4-116">If the [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) policy is configured, it takes precedence over [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) and [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices).</span></span>

#### <a name="required-and-optional-diagnostic-data"></a><span data-ttu-id="600f4-117">必需和可选诊断数据</span><span class="sxs-lookup"><span data-stu-id="600f4-117">Required and optional diagnostic data</span></span>

<span data-ttu-id="600f4-118">收集必需诊断数据可确保 Microsoft Edge 安全、最新且按预期运行。</span><span class="sxs-lookup"><span data-stu-id="600f4-118">Required diagnostic data is collected to keep Microsoft Edge secure, up to date and performing as expected.</span></span>

<span data-ttu-id="600f4-119">可选诊断数据包括有关如何使用浏览器、访问的网站和崩溃报告的数据，以帮助保持 Microsoft Edge 安全、最新且按预期运行，同时用于为所有用户改进 Microsoft Edge 和其他 Microsoft 产品和服务。</span><span class="sxs-lookup"><span data-stu-id="600f4-119">Optional diagnostic data includes data about how you use the browser, websites you visit and crash reports to help keep Microsoft Edge secure, up to date, and performing as expected and is used to improve Microsoft Edge and other Microsoft products and services for all users.</span></span>

> [!NOTE]
> <span data-ttu-id="600f4-120">Windows 10 设备不支持此策略。</span><span class="sxs-lookup"><span data-stu-id="600f4-120">This policy isn't supported on Windows 10 devices.</span></span> <span data-ttu-id="600f4-121">若要在 Windows 10 上控制此数据收集，IT 管理员必须使用 Windows 诊断数据组策略。</span><span class="sxs-lookup"><span data-stu-id="600f4-121">To control data collection on Windows 10, IT admins must use the Windows diagnostic data group policy.</span></span> <span data-ttu-id="600f4-122">根据 Windows 版本的不同，此策略将为**允许遥测**或**允许诊断数据**。</span><span class="sxs-lookup"><span data-stu-id="600f4-122">This policy will either be to **Allow Telemetry** or to **Allow Diagnostic Data**, depending on the version of Windows.</span></span> <span data-ttu-id="600f4-123">详细了解 [Windows 10 诊断数据收集](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="600f4-123">Learn more about [Windows 10 diagnostic data collection](/windows/privacy/configure-windows-diagnostic-data-in-your-organization).</span></span>

<span data-ttu-id="600f4-124">使用以下设置之一配置 **DiagnosticData**：</span><span class="sxs-lookup"><span data-stu-id="600f4-124">Use one of the following settings to configure **DiagnosticData**:</span></span>

- <span data-ttu-id="600f4-125">关闭（不推荐）(0) 会关闭必需和可选诊断数据收集。</span><span class="sxs-lookup"><span data-stu-id="600f4-125">Off (Not recommended) (0) turns off required and optional diagnostic data collection.</span></span> 
- <span data-ttu-id="600f4-126">必需数据 (1) 会发送必需诊断数据，但关闭可选诊断数据收集。</span><span class="sxs-lookup"><span data-stu-id="600f4-126">Required data (1) sends required diagnostic data but turns off optional diagnostic data collection.</span></span> <span data-ttu-id="600f4-127">Microsoft Edge 会发送必需诊断数据，以确保 Microsoft Edge 安全、最新且按预期运行。</span><span class="sxs-lookup"><span data-stu-id="600f4-127">Microsoft Edge will send required diagnostic data necessary to keep Microsoft Edge secure, up to date and performing as expected.</span></span> 
- <span data-ttu-id="600f4-128">可选数据 (2) 会发送可选诊断数据，包括有关浏览器使用情况、访问的网站和发送到 Microsoft 的崩溃报告的数据，以帮助保持 Microsoft Edge 安全、最新且按预期运行，同时用于为所有用户改进 Microsoft Edge 和其他 Microsoft 产品和服务。</span><span class="sxs-lookup"><span data-stu-id="600f4-128">Optional data (2) sends optional diagnostic data includes data about browser usage, websites that are visited, crash reports sent to Microsoft to help keep Microsoft Edge secure, up to date, and performing as expected and is used to improve Microsoft Edge and other Microsoft products and services for all users.</span></span>

<span data-ttu-id="600f4-129">对于 Windows 7、Windows 8/8.1 和 macOS，此策略控制向 Microsoft 发送必需和可选数据。</span><span class="sxs-lookup"><span data-stu-id="600f4-129">On Windows 7, Windows 8/8.1, and macOS, this policy controls sending required and optional data to Microsoft.</span></span>

<span data-ttu-id="600f4-130">如果未配置或已禁用此策略，Microsoft Edge 将默认使用用户首选项。</span><span class="sxs-lookup"><span data-stu-id="600f4-130">If you don't configure this policy or disable it Microsoft Edge will default to the user's preference.</span></span>

### <a name="deprecated-enable-usage-and-crash-related-data-reporting"></a><span data-ttu-id="600f4-131">（已弃用）启用使用情况和故障相关数据报告</span><span class="sxs-lookup"><span data-stu-id="600f4-131">(DEPRECATED) Enable usage and crash-related data reporting</span></span>

<span data-ttu-id="600f4-132">**MetricsReportingEnabled** 策略允许向 Microsoft 发送关于 Microsoft Edge 的使用情况和故障相关数据的报告。</span><span class="sxs-lookup"><span data-stu-id="600f4-132">The **MetricsReportingEnabled** policy enables reporting of usage and crash-related data about Microsoft Edge to Microsoft.</span></span>

<span data-ttu-id="600f4-133">Microsoft Edge 收集一系列必需的数据，以确保产品保持最新状态、安全可靠且正常运行。</span><span class="sxs-lookup"><span data-stu-id="600f4-133">Microsoft Edge collects a set of required data that's necessary to keep the product up to date, secure, and performing as expected.</span></span> <span data-ttu-id="600f4-134">此数据包括来自 Microsoft Edge 的有关 Microsoft Edge 安装的当前数据收集许可、应用版本和安装状态的基本设备连接和配置信息。</span><span class="sxs-lookup"><span data-stu-id="600f4-134">This data includes basic device connectivity and configuration information from Microsoft Edge about the current data collection consent, app version, and installation state about your installation of Microsoft Edge.</span></span><span data-ttu-id="600f4-135">通过禁用策略可关闭此数据集合。</span><span class="sxs-lookup"><span data-stu-id="600f4-135"> This data collection can be turned off by disabling the policy.</span></span>

<span data-ttu-id="600f4-136">启用此策略可向 Microsoft 发送使用情况和故障相关数据的报告。</span><span class="sxs-lookup"><span data-stu-id="600f4-136">Enable this policy to send reporting of usage and crash-related data to Microsoft.</span></span> <span data-ttu-id="600f4-137">禁用此策略可以不将数据发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="600f4-137">Disable this policy to not send the data to Microsoft.</span></span> <span data-ttu-id="600f4-138">在这两种情况下，用户不能更改或覆盖设置。</span><span class="sxs-lookup"><span data-stu-id="600f4-138">In both cases, users can't change or override the setting.</span></span>

<span data-ttu-id="600f4-139">在 Windows 10 上运行 Microsoft Edge 时：</span><span class="sxs-lookup"><span data-stu-id="600f4-139">When Microsoft Edge is running on Windows 10:</span></span>

- <span data-ttu-id="600f4-140">如果未配置此策略，Microsoft Edge 将默认使用 Windows 诊断数据设置。</span><span class="sxs-lookup"><span data-stu-id="600f4-140">If this policy isn't configured, Microsoft Edge will default to the Windows diagnostic data setting.</span></span>
- <span data-ttu-id="600f4-141">如果启用此策略，则只有将 Windows 诊断数据设置设为**增强**或**完整**时，Microsoft Edge 才会发送使用情况数据。</span><span class="sxs-lookup"><span data-stu-id="600f4-141">If this policy is enabled, Microsoft Edge will only send usage data if the Windows Diagnostic data setting is set to **Enhanced** or **Full**.</span></span>
  - <span data-ttu-id="600f4-142">如果启用此策略，Microsoft Edge 将仅发送使用情况数据（如果 [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) 也处于启用状态）。</span><span class="sxs-lookup"><span data-stu-id="600f4-142">If this policy is enabled, Microsoft Edge will only send usage data if [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) is also enabled.</span></span>
- <span data-ttu-id="600f4-143">如果禁用此策略，Microsoft Edge 将不会发送使用情况数据。</span><span class="sxs-lookup"><span data-stu-id="600f4-143">If this policy is disabled, Microsoft Edge will not send usage data.</span></span> <span data-ttu-id="600f4-144">基于 Windows 诊断数据设置发送故障相关数据。</span><span class="sxs-lookup"><span data-stu-id="600f4-144">Crash-related data is sent based on the Windows Diagnostic data setting.</span></span> <span data-ttu-id="600f4-145">[详细了解 Windows 诊断数据设置](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="600f4-145">[Learn more about Windows Diagnostic data settings](/windows/privacy/configure-windows-diagnostic-data-in-your-organization).</span></span>

<span data-ttu-id="600f4-146">在 Windows 7、8 和 macOS 上运行 Microsoft Edge 时：</span><span class="sxs-lookup"><span data-stu-id="600f4-146">When Microsoft Edge is running on Windows 7, 8, and macOS:</span></span>

- <span data-ttu-id="600f4-147">如果未配置此策略，Microsoft Edge 将默认使用用户的首选项。</span><span class="sxs-lookup"><span data-stu-id="600f4-147">If this policy isn't configured, Microsoft Edge defaults to the user's preference.</span></span>
-  <span data-ttu-id="600f4-148">如果启用此策略，Microsoft Edge 将仅发送使用情况数据（如果 [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) 也处于启用状态）。</span><span class="sxs-lookup"><span data-stu-id="600f4-148">If this policy is enabled, Microsoft Edge will only send usage data if [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices) is also enabled.</span></span>

### <a name="deprecated-send-site-information-to-improve-microsoft-services"></a><span data-ttu-id="600f4-149">（已弃用）发送站点信息以改进 Microsoft 服务</span><span class="sxs-lookup"><span data-stu-id="600f4-149">(DEPRECATED) Send site information to improve Microsoft services</span></span>

<span data-ttu-id="600f4-150">**SendSiteInformationToImproveServices** 策略允许向 Microsoft 发送关于在 Microsoft Edge 中访问的网站的信息，以改进 Microsoft 产品和服务（如搜索）。</span><span class="sxs-lookup"><span data-stu-id="600f4-150">The  **SendSiteInformationToImproveServices** policy enables sending information about websites visited in Microsoft Edge to Microsoft to improve Microsoft products and services such as search.</span></span>

<span data-ttu-id="600f4-151">启用此策略可将有关在 Microsoft Edge 中访问的网站的信息发送到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="600f4-151">Enable this policy to send information about websites visited in Microsoft Edge to Microsoft.</span></span> <span data-ttu-id="600f4-152">禁用此策略以便不将有关在 Microsoft Edge 中访问的网站的信息发送到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="600f4-152">Disable this policy to not send information about the websites that are visited in Microsoft Edge to Microsoft.</span></span> <span data-ttu-id="600f4-153">在这两种情况下，用户不能更改或覆盖设置。</span><span class="sxs-lookup"><span data-stu-id="600f4-153">In both cases, users can't change or override the setting.</span></span>

<span data-ttu-id="600f4-154">在 Windows 10 上运行 Microsoft Edge 时：</span><span class="sxs-lookup"><span data-stu-id="600f4-154">When Microsoft Edge is running on Windows 10:</span></span>

- <span data-ttu-id="600f4-155">如果未配置此策略，Microsoft Edge 将默认使用 Windows 诊断数据设置。</span><span class="sxs-lookup"><span data-stu-id="600f4-155">If this policy isn't configured, Microsoft Edge will default to the Windows diagnostic data setting.</span></span>
- <span data-ttu-id="600f4-156">如果启用此策略，则只有将 Windows 诊断数据设置设为**完整**时，Microsoft Edge 才会发送有关所访问网站的信息。</span><span class="sxs-lookup"><span data-stu-id="600f4-156">If this policy is enabled, Microsoft Edge will only send information about the websites that are visited if the Windows Diagnostic data setting is set to **Full**.</span></span>
  - <span data-ttu-id="600f4-157">如果启用此策略，Microsoft Edge 将仅发送使用情况数据（如果 [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) 也处于启用状态）。</span><span class="sxs-lookup"><span data-stu-id="600f4-157">If this policy is enabled, Microsoft Edge will only send usage data if [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) is also enabled.</span></span> 
- <span data-ttu-id="600f4-158">如果禁用此策略，Microsoft Edge 将不会发送有关所访问网站的信息。</span><span class="sxs-lookup"><span data-stu-id="600f4-158">If this policy is disabled, Microsoft Edge will not send info about websites visited.</span></span> <span data-ttu-id="600f4-159">要[详细了解 Windows 诊断数据设置](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)，请执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="600f4-159">To [learn more about Windows Diagnostic data settings](/windows/privacy/configure-windows-diagnostic-data-in-your-organization).</span></span>

<span data-ttu-id="600f4-160">在 Windows 7、8 和 macOS 上运行 Microsoft Edge 时：</span><span class="sxs-lookup"><span data-stu-id="600f4-160">When Microsoft Edge is running on Windows 7, 8, and macOS:</span></span>

- <span data-ttu-id="600f4-161">如果启用此策略，Microsoft Edge 将仅发送使用情况数据（如果 [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) 也处于启用状态）。</span><span class="sxs-lookup"><span data-stu-id="600f4-161">If this policy is enabled, Microsoft Edge will only send usage data if [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) is also enabled.</span></span>
- <span data-ttu-id="600f4-162">如果未配置此策略，Microsoft Edge 将默认使用用户的首选项。</span><span class="sxs-lookup"><span data-stu-id="600f4-162">If this policy isn't configured, Microsoft Edge defaults to the user's preference.</span></span>

## <a name="implementation-details"></a><span data-ttu-id="600f4-163">实现详细信息</span><span class="sxs-lookup"><span data-stu-id="600f4-163">Implementation details</span></span>

<span data-ttu-id="600f4-164">对于非 Windows 10 设备：</span><span class="sxs-lookup"><span data-stu-id="600f4-164">For non-Windows 10 devices:</span></span> 
- <span data-ttu-id="600f4-165">如果已配置 [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) 策略，则其优先级高于 [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) 和[SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices)。</span><span class="sxs-lookup"><span data-stu-id="600f4-165">If [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) policy is configured, it takes precedence over [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) and [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices).</span></span> 
- <span data-ttu-id="600f4-166">如果未配置 [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) 策略，Microsoft Edge将侦听 [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) 和[SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices)。</span><span class="sxs-lookup"><span data-stu-id="600f4-166">If [DiagnosticData](./microsoft-edge-policies.md#diagnosticdata) policy isn't configured, Microsoft Edge listens to [MetricsReportingEnabled](./microsoft-edge-policies.md#metricsreportingenabled) and [SendSiteInfoToImproveServices](./microsoft-edge-policies.md#sendsiteinfotoimproveservices).</span></span>  

<span data-ttu-id="600f4-167">为了让 Windows 10 了解我们依赖 Windows 诊断数据设置的实现，下表列出了是否将 **必需**和**可选** 诊断数据发送到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="600f4-167">For Windows 10 to understand our implementation with the dependency on the Windows Diagnostic data setting, the following table identifies whether **Required** and **Optional** diagnostic data is sent to Microsoft.</span></span>

| <span data-ttu-id="600f4-168">Windows 诊断数据设置</span><span class="sxs-lookup"><span data-stu-id="600f4-168">Windows Diagnostic data setting</span></span> | <span data-ttu-id="600f4-169">必需诊断数据</span><span class="sxs-lookup"><span data-stu-id="600f4-169">Required diagnostic data</span></span>  | <span data-ttu-id="600f4-170">可选诊断数据</span><span class="sxs-lookup"><span data-stu-id="600f4-170">Optional diagnostic data</span></span> |
|---------------------------------|-----------------------------------------------|-----------------------------------------------------|
| <span data-ttu-id="600f4-171">安全性</span><span class="sxs-lookup"><span data-stu-id="600f4-171">Security</span></span>                        | <span data-ttu-id="600f4-172">未发送</span><span class="sxs-lookup"><span data-stu-id="600f4-172">Not sent</span></span>                                      | <span data-ttu-id="600f4-173">未发送</span><span class="sxs-lookup"><span data-stu-id="600f4-173">Not sent</span></span>                                            |
| <span data-ttu-id="600f4-174">基本</span><span class="sxs-lookup"><span data-stu-id="600f4-174">Basic</span></span>                           | <span data-ttu-id="600f4-175">已发送</span><span class="sxs-lookup"><span data-stu-id="600f4-175">Sent</span></span>                                      | <span data-ttu-id="600f4-176">未发送</span><span class="sxs-lookup"><span data-stu-id="600f4-176">Not sent</span></span>                                            |
| <span data-ttu-id="600f4-177">增强</span><span class="sxs-lookup"><span data-stu-id="600f4-177">Enhanced</span></span>                        | <span data-ttu-id="600f4-178">已发送</span><span class="sxs-lookup"><span data-stu-id="600f4-178">Sent</span></span>                                          | <span data-ttu-id="600f4-179">未发送</span><span class="sxs-lookup"><span data-stu-id="600f4-179">Not sent</span></span>                                            |
| <span data-ttu-id="600f4-180">完整</span><span class="sxs-lookup"><span data-stu-id="600f4-180">Full</span></span>                            | <span data-ttu-id="600f4-181">已发送</span><span class="sxs-lookup"><span data-stu-id="600f4-181">Sent</span></span>                                          | <span data-ttu-id="600f4-182">已发送</span><span class="sxs-lookup"><span data-stu-id="600f4-182">Sent</span></span>                                                |

> [!IMPORTANT]
> <span data-ttu-id="600f4-183">Microsoft Edge 将支持适用于 Microsoft Edge 版本86 – 88（含）的 **MetricsReportingEnabled**  和\*\* SendSiteInfoToImproveServices\*\*。</span><span class="sxs-lookup"><span data-stu-id="600f4-183">Microsoft Edge will support **MetricsReportingEnabled** and **SendSiteInfoToImproveServices** for Microsoft Edge versions 86 – 88 inclusive.</span></span> <span data-ttu-id="600f4-184">在 Microsoft Edge 版本 89 中，将不再支持 **MetricsReportingEnabled**  和 **SendSiteInfoToImproveServices**，并且将默认为非 Windows 10 平台使用 **DiagnosticData**，或默认为 Windows 10 使用**允许遥测**策略。</span><span class="sxs-lookup"><span data-stu-id="600f4-184">In Microsoft Edge version 89, **MetricsReportingEnabled** and **SendSiteInfoToImproveServices** will no longer be supported and will default to **DiagnosticData** on non-Windows 10 platforms or the **Allow Telemetry** policy for Windows 10.</span></span>

## <a name="additional-privacy-policy-options"></a><span data-ttu-id="600f4-185">其他隐私策略选项</span><span class="sxs-lookup"><span data-stu-id="600f4-185">Additional privacy policy options</span></span>

<span data-ttu-id="600f4-186">你可能需要考虑以下与数据隐私相关的组策略：</span><span class="sxs-lookup"><span data-stu-id="600f4-186">You may want to consider the following group policies related to data privacy:</span></span>

- <span data-ttu-id="600f4-187">在特定站点上阻止 Cookie</span><span class="sxs-lookup"><span data-stu-id="600f4-187">Block cookies on specific sites</span></span>
- <span data-ttu-id="600f4-188">阻止第三方 Cookie</span><span class="sxs-lookup"><span data-stu-id="600f4-188">Block third-party cookies</span></span>
- <span data-ttu-id="600f4-189">配置 Do Not Track</span><span class="sxs-lookup"><span data-stu-id="600f4-189">Configure Do Not Track</span></span>
- <span data-ttu-id="600f4-190">禁用 InPrivate 模式</span><span class="sxs-lookup"><span data-stu-id="600f4-190">Disable InPrivate mode</span></span>

## <a name="see-also"></a><span data-ttu-id="600f4-191">另请参阅</span><span class="sxs-lookup"><span data-stu-id="600f4-191">See also</span></span>

- [<span data-ttu-id="600f4-192">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="600f4-192">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="600f4-193">Microsoft Edge 策略</span><span class="sxs-lookup"><span data-stu-id="600f4-193">Microsoft Edge policies</span></span>](microsoft-edge-policies.md)
- [<span data-ttu-id="600f4-194">Microsoft Edge 隐私白皮书</span><span class="sxs-lookup"><span data-stu-id="600f4-194">Microsoft Edge Privacy Whitepaper</span></span>](/microsoft-edge/privacy-whitepaper)