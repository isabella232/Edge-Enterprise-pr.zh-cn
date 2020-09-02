---
title: 使用 Microsoft Edge 防止潜在有害应用程序
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 03/04/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 使用 Microsoft Edge 防止潜在有害应用程序
ms.openlocfilehash: 615442acc0e9ed58da37aa0ef8b3747e916a8024
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979205"
---
# <span data-ttu-id="909a1-103">防止潜在的有害应用程序 (PUA)</span><span class="sxs-lookup"><span data-stu-id="909a1-103">Protect against potentially unwanted applications (PUAs)</span></span>

<span data-ttu-id="909a1-104">本文介绍了如何使用 Microsoft Edge 或使用 Windows Defender 防病毒防止潜在有害应用程序 (PUA)。</span><span class="sxs-lookup"><span data-stu-id="909a1-104">This article explains how you can protect against potentially unwanted applications (PUAs) using Microsoft Edge or by using Windows Defender Antivirus.</span></span>

> [!NOTE]
> <span data-ttu-id="909a1-105">本文适用于 Microsoft Edge 版本 80 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="909a1-105">This article applies to Microsoft Edge version 80 or later.</span></span>

## <span data-ttu-id="909a1-106">概述</span><span class="sxs-lookup"><span data-stu-id="909a1-106">Overview</span></span>

<span data-ttu-id="909a1-107">潜在有害应用程序不被视为病毒或恶意软件，但这些应用程序可能会在终结点上执行，对终结点性能或使用产生不利影响的操作。</span><span class="sxs-lookup"><span data-stu-id="909a1-107">Potentially unwanted applications aren't considered to be viruses or malware, but these apps might perform actions on endpoints that adversely affect endpoint performance or use.</span></span> <span data-ttu-id="909a1-108">例如，*Evasion 软件*会主动尝试规避安全产品的检测。</span><span class="sxs-lookup"><span data-stu-id="909a1-108">For example, *Evasion software* actively tries to evade detection by security products.</span></span> <span data-ttu-id="909a1-109">此类软件会增加网络受到实际恶意软件感染的风险。</span><span class="sxs-lookup"><span data-stu-id="909a1-109">This kind of software can increase the risk of your network being infected with actual malware.</span></span> <span data-ttu-id="909a1-110">PUA 也可以指信誉不佳的应用程序。</span><span class="sxs-lookup"><span data-stu-id="909a1-110">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="909a1-111">有关将软件归类为 PUA 的标准的说明，请参阅[潜在有害应用程序](https://docs.microsoft.com/windows/security/threat-protection/intelligence/criteria#potentially-unwanted-application-pua)。</span><span class="sxs-lookup"><span data-stu-id="909a1-111">For a description of the criteria used to classify software as a PUA, see [Potentially unwanted application](https://docs.microsoft.com/windows/security/threat-protection/intelligence/criteria#potentially-unwanted-application-pua).</span></span>

## <span data-ttu-id="909a1-112">使用 Microsoft Edge 防止 PUA</span><span class="sxs-lookup"><span data-stu-id="909a1-112">Protect against PUA with Microsoft Edge</span></span>

<span data-ttu-id="909a1-113">Microsoft Edge（版本 80.0.361.50 或更高版本）会阻止 PUA 下载和关联的资源 URL。</span><span class="sxs-lookup"><span data-stu-id="909a1-113">Microsoft Edge (version 80.0.361.50 or later) blocks PUA downloads and associated resource URLs.</span></span>

<span data-ttu-id="909a1-114">你可以通过在 Microsoft Edge 中启用“**阻止潜在有害应用程序**”功能来设置保护。</span><span class="sxs-lookup"><span data-stu-id="909a1-114">You can set up protection by enabling the **Block potentially unwanted apps** feature in Microsoft Edge.</span></span>

> [!NOTE]
> <span data-ttu-id="909a1-115">[Microsoft Edge 团队博客文章](https://blogs.windows.com/msedgedev/2020/02/27/protecting-users-potentially-unwanted-apps/)介绍了此新增功能，并说明了处理被错误标识的应用程序或将其报告为有害应用程序的方法。</span><span class="sxs-lookup"><span data-stu-id="909a1-115">The [Microsoft Edge Team blog post](https://blogs.windows.com/msedgedev/2020/02/27/protecting-users-potentially-unwanted-apps/) describes this new feature and explains how to handle a mislabeled app or report an app as unwanted.</span></span>

### <span data-ttu-id="909a1-116">要启用 PUA 保护：</span><span class="sxs-lookup"><span data-stu-id="909a1-116">To enable PUA protection:</span></span>

1. <span data-ttu-id="909a1-117">在浏览器中打开“**设置**”。</span><span class="sxs-lookup"><span data-stu-id="909a1-117">Open **Settings** in the browser.</span></span>
2. <span data-ttu-id="909a1-118">选择“**隐私和服务**”。</span><span class="sxs-lookup"><span data-stu-id="909a1-118">Select **Privacy and services**.</span></span>
3. <span data-ttu-id="909a1-119">在“**服务**”部分中，检查是否已启用“**Microsoft Defender SmartScreen**”。</span><span class="sxs-lookup"><span data-stu-id="909a1-119">In the **Services** section, check to see that **Microsoft Defender SmartScreen** is turned on.</span></span> <span data-ttu-id="909a1-120">如果没有，请启用 Microsoft Defender SmartScreen。</span><span class="sxs-lookup"><span data-stu-id="909a1-120">If not, then turn on Microsoft Defender SmartScreen.</span></span> <span data-ttu-id="909a1-121">以下屏幕截图中的示例显示了浏览器由组织管理，并且已启用 Microsoft Defender SmartScreen。</span><span class="sxs-lookup"><span data-stu-id="909a1-121">The example in the following screenshot shows the browser is managed by the organization and that Microsoft Defender SmartScreen is turned on.</span></span>

   ![在“设置”中启用 Microsoft Edge PUA](./media/microsoft-edge-potentially-unwanted-apps/security-pua-setup.png)

4. <span data-ttu-id="909a1-123">在“**服务**”部分中，使用前面屏幕截图中所示的切换按钮启用“**阻止潜在有害应用程序**”。</span><span class="sxs-lookup"><span data-stu-id="909a1-123">In the **Services** section, use the toggle shown in the preceding screenshot to turn on **Block potentially unwanted apps**.</span></span>

   > [!TIP]
   > <span data-ttu-id="909a1-124">你可以通过在我们的 Windows Defender SmartScreen [演示页面](https://demo.smartscreen.msft.net/)中进行测试来安全地浏览 PUA 保护的 URL 阻止功能。</span><span class="sxs-lookup"><span data-stu-id="909a1-124">You can safely explore the URL-blocking feature of PUA protection by testing it out on one of our Windows Defender SmartScreen [demo pages](https://demo.smartscreen.msft.net/).</span></span>

<span data-ttu-id="909a1-125">当 Microsoft Edge 检测到 PUA 时，你将看到一条类似于下一屏幕截图中的消息。</span><span class="sxs-lookup"><span data-stu-id="909a1-125">When Microsoft Edge detects a PUA, you will see a message like the one in the next screenshot.</span></span>

   ![Microsoft Edge PUA 警告消息](./media/microsoft-edge-potentially-unwanted-apps/security-pua-msg.png)

### <span data-ttu-id="909a1-127">要阻止与 PUA 关联的 URL</span><span class="sxs-lookup"><span data-stu-id="909a1-127">To block against PUA-associated URLs</span></span>

<span data-ttu-id="909a1-128">在 Microsoft Edge 中打开 PUA 保护后，Windows Defender SmartScreen 将保护你不受与 PUA 关联的 URL 的侵害。</span><span class="sxs-lookup"><span data-stu-id="909a1-128">After you turn on PUA protection in Microsoft Edge, Windows Defender SmartScreen will protect you from PUA-associated URLs.</span></span>

<span data-ttu-id="909a1-129">管理员可通过多种方法来配置 Microsoft Edge 和 Windows Defender SmartScreen 如何协同工作，以保护用户免受与 PUA 关联的 URL 的影响。</span><span class="sxs-lookup"><span data-stu-id="909a1-129">There are several ways admins can configure how Microsoft Edge and Windows Defender SmartScreen work together to protect users from PUA-associated URLs.</span></span> <span data-ttu-id="909a1-130">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="909a1-130">For more information, see:</span></span>

- [<span data-ttu-id="909a1-131">在 Windows 上配置 Microsoft Edge 策略设置</span><span class="sxs-lookup"><span data-stu-id="909a1-131">Configure Microsoft Edge policy settings on Windows</span></span>](https://docs.microsoft.com/DeployEdge/configure-microsoft-edge)
- [<span data-ttu-id="909a1-132">SmartScreen 设置</span><span class="sxs-lookup"><span data-stu-id="909a1-132">SmartScreen settings</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreen-settings)
- [<span data-ttu-id="909a1-133">SmartScreenPuaEnabled 策略</span><span class="sxs-lookup"><span data-stu-id="909a1-133">SmartScreenPuaEnabled policy</span></span>](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)
- [<span data-ttu-id="909a1-134">配置 Windows Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="909a1-134">Configure Windows Defender SmartScreen</span></span>](https://docs.microsoft.com/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen)

<span data-ttu-id="909a1-135">管理员还可以自定义 Microsoft Defender 高级威胁防护 (Microsoft Defender ATP) 阻止列表。</span><span class="sxs-lookup"><span data-stu-id="909a1-135">Admins can also customize the Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) block list.</span></span> <span data-ttu-id="909a1-136">他们可以使用 Microsoft Defender ATP 门户来[创建和管理 IP 和 URL 的指示器](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators#create-indicators-for-ips-and-urlsdomains-preview)。</span><span class="sxs-lookup"><span data-stu-id="909a1-136">They can use the Microsoft Defender ATP portal to [create and manage indicators for IPs and URLs](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators#create-indicators-for-ips-and-urlsdomains-preview).</span></span>

## <span data-ttu-id="909a1-137">使用 Windows Defender 防病毒阻止 PUA</span><span class="sxs-lookup"><span data-stu-id="909a1-137">Protect against PUA with Windows Defender Antivirus</span></span>

<span data-ttu-id="909a1-138">[检测并阻止潜在有害应用程序](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#windows-defender-antivirus)文章还介绍了如何配置 Windows Defender 防病毒来启用 PUA 保护。</span><span class="sxs-lookup"><span data-stu-id="909a1-138">The [Detect and block potentially unwanted applications](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#windows-defender-antivirus) article also describes how you can configure Windows Defender Antivirus to enable PUA protection.</span></span> <span data-ttu-id="909a1-139">可使用下列任一选项来配置保护：</span><span class="sxs-lookup"><span data-stu-id="909a1-139">You can configure protection using any of the following options:</span></span>

- [<span data-ttu-id="909a1-140">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="909a1-140">Microsoft Intune</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-intune-to-configure-pua-protection)
- [<span data-ttu-id="909a1-141">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="909a1-141">Microsoft Endpoint Configuration Manager</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-configuration-manager-to-configure-pua-protection)
- [<span data-ttu-id="909a1-142">组策略</span><span class="sxs-lookup"><span data-stu-id="909a1-142">Group Policy</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-group-policy-to-configure-pua-protection)
- [<span data-ttu-id="909a1-143">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="909a1-143">PowerShell cmdlets</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus#use-powershell-cmdlets-to-configure-pua-protection)

<span data-ttu-id="909a1-144">当 Windows Defender 在某个终结点上检测到 PUA 文件时，它将隔离该文件并以与普通威胁检测相同的格式（以“PUA:”开头）通知用户（[除非已禁用通知](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-notifications-windows-defender-antivirus)）。检测到的威胁也将显示在 [Windows 安全应用程序的隔离列表中](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-security-center-antivirus#detection-history)。</span><span class="sxs-lookup"><span data-stu-id="909a1-144">When Windows Defender detects a PUA file on an endpoint it quarantines the file and notifies the user ([unless notifications are disabled](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-notifications-windows-defender-antivirus)) in the same format as a normal threat detection (prefaced with "PUA:".) Detected threats also appear in the [quarantine list in the Windows Security app](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-security-center-antivirus#detection-history).</span></span>

### <span data-ttu-id="909a1-145">PUA 通知和事件</span><span class="sxs-lookup"><span data-stu-id="909a1-145">PUA notifications and events</span></span>

<span data-ttu-id="909a1-146">管理员可通过多种方法查看 PUA 事件：</span><span class="sxs-lookup"><span data-stu-id="909a1-146">There are several ways an admin can see PUA events:</span></span>

- <span data-ttu-id="909a1-147">在 Windows 事件查看器中（而不是在 Microsoft Endpoint Configuration Manager 或 Intune 中）。</span><span class="sxs-lookup"><span data-stu-id="909a1-147">In the Windows Event Viewer, but not in Microsoft Endpoint Configuration Manager or Intune.</span></span>
- <span data-ttu-id="909a1-148">在电子邮件中（如果用于 PUA 检测的电子邮件通知已启用）。</span><span class="sxs-lookup"><span data-stu-id="909a1-148">In an email if email notifications for PUA detections is turned on.</span></span>
- <span data-ttu-id="909a1-149">在 [Windows Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus)事件日志中（PUA 事件记录在事件 ID 1116 下，并显示以下消息：“反恶意软件平台检测到恶意软件或其他潜在有害软件”）。</span><span class="sxs-lookup"><span data-stu-id="909a1-149">In [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus) event logs, where a PUA event is recorded under event ID 1116 with the message: "The antimalware platform detected malware or other potentially unwanted software."</span></span>

> [!NOTE]
> <span data-ttu-id="909a1-150">用户将看到“\*.exe 是一个潜在有害应用程序，已被 Microsoft Defender SmartScreen 阻止”。</span><span class="sxs-lookup"><span data-stu-id="909a1-150">Users will see "\*.exe has been blocked as a potentially unwanted app by Microsoft Defender SmartScreen".</span></span>

### <span data-ttu-id="909a1-151">允许列表应用程序</span><span class="sxs-lookup"><span data-stu-id="909a1-151">Allow-list an app</span></span>

<span data-ttu-id="909a1-152">与 Microsoft Edge 一样，Windows Defender 防病毒提供了一种允许安装被错误阻止的文件或运行为完成某项任务所需的文件的方法。</span><span class="sxs-lookup"><span data-stu-id="909a1-152">Like Microsoft Edge, Windows Defender Antivirus provides a way to allow files that are blocked by mistake or needed to complete a task.</span></span> <span data-ttu-id="909a1-153">如果发生此类情况，你可以启用允许列表文件。</span><span class="sxs-lookup"><span data-stu-id="909a1-153">If this happens you can allow-list a file.</span></span> <span data-ttu-id="909a1-154">有关详细信息，请参阅[如何在配置服务器中配置 Endpoint Protection](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#to-exclude-specific-files-or-folders) 以了解如何排除特定文件或文件夹。</span><span class="sxs-lookup"><span data-stu-id="909a1-154">For more information, see [How to Configure Endpoint Protection in Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#to-exclude-specific-files-or-folders) to learn how to exclude specific files or folders.</span></span>

## <span data-ttu-id="909a1-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="909a1-155">See also</span></span>

- [<span data-ttu-id="909a1-156">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="909a1-156">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="909a1-157">威胁防护</span><span class="sxs-lookup"><span data-stu-id="909a1-157">Threat protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/index)
- [<span data-ttu-id="909a1-158">配置行为型、启发式的实时保护</span><span class="sxs-lookup"><span data-stu-id="909a1-158">Configure behavioral, heuristic, and real-time protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-protection-features-windows-defender-antivirus)
- [<span data-ttu-id="909a1-159">下一代保护</span><span class="sxs-lookup"><span data-stu-id="909a1-159">Next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)
- [<span data-ttu-id="909a1-160">基于 Chromium 的 Microsoft Edge 版本 79 的安全性基线</span><span class="sxs-lookup"><span data-stu-id="909a1-160">Security baseline for Chromium-based Microsoft Edge, version 79</span></span>](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/security-baseline-final-for-chromium-based-microsoft-edge/ba-p/1111863)
