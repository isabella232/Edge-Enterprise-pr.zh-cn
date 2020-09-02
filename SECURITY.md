---
ms.openlocfilehash: bc66462291f4b1959fe1080ab33849c935218ebd
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979245"
---
<!-- BEGIN MICROSOFT SECURITY.MD V0.0.5 BLOCK -->

## <span data-ttu-id="cb15d-101">安全性</span><span class="sxs-lookup"><span data-stu-id="cb15d-101">Security</span></span>

<span data-ttu-id="cb15d-102">Microsoft 会认真对待软件产品和服务的安全，其中包括通过我们的 GitHub 组织管理的所有源代码库，其中包括 [Microsoft](https://github.com/Microsoft)、 [Azure](https://github.com/Azure)、 [新](https://github.com/dotnet)、 [AspNet](https://github.com/aspnet)、 [Xamarin](https://github.com/xamarin)和 [我们的 github 组织](https://opensource.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="cb15d-102">Microsoft takes the security of our software products and services seriously, which includes all source code repositories managed through our GitHub organizations, which include [Microsoft](https://github.com/Microsoft), [Azure](https://github.com/Azure), [DotNet](https://github.com/dotnet), [AspNet](https://github.com/aspnet), [Xamarin](https://github.com/xamarin), and [our GitHub organizations](https://opensource.microsoft.com/).</span></span>

<span data-ttu-id="cb15d-103">如果您认为在任何 Microsoft 拥有的存储库中发现了任何满足 [microsoft 对安全漏洞的定义](https://docs.microsoft.com/en-us/previous-versions/tn-archive/cc751383(v=technet.10))的安全漏洞，请按照下面的说明将其报告给我们。</span><span class="sxs-lookup"><span data-stu-id="cb15d-103">If you believe you have found a security vulnerability in any Microsoft-owned repository that meets [Microsoft's definition of a security vulnerability](https://docs.microsoft.com/en-us/previous-versions/tn-archive/cc751383(v=technet.10)), please report it to us as described below.</span></span>

## <span data-ttu-id="cb15d-104">报告安全问题</span><span class="sxs-lookup"><span data-stu-id="cb15d-104">Reporting Security Issues</span></span>

**<span data-ttu-id="cb15d-105">请不要通过公共 GitHub 问题报告安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="cb15d-105">Please do not report security vulnerabilities through public GitHub issues.</span></span>**

<span data-ttu-id="cb15d-106">请改为将其报告给 Microsoft 安全回复中心 (MSRC) [https://msrc.microsoft.com/create-report](https://msrc.microsoft.com/create-report) 。</span><span class="sxs-lookup"><span data-stu-id="cb15d-106">Instead, please report them to the Microsoft Security Response Center (MSRC) at [https://msrc.microsoft.com/create-report](https://msrc.microsoft.com/create-report).</span></span>

<span data-ttu-id="cb15d-107">如果想要在不登录的情况下进行提交，请将电子邮件发送到 [secure@microsoft.com](mailto:secure@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="cb15d-107">If you prefer to submit without logging in, send email to [secure@microsoft.com](mailto:secure@microsoft.com).</span></span>  <span data-ttu-id="cb15d-108">如果可能，请用 "PGP" 键加密您的邮件;请从 [Microsoft 安全回复中心 "PGP 密钥" 页面](https://www.microsoft.com/en-us/msrc/pgp-key-msrc)下载。</span><span class="sxs-lookup"><span data-stu-id="cb15d-108">If possible, encrypt your message with our PGP key; please download it from the [Microsoft Security Response Center PGP Key page](https://www.microsoft.com/en-us/msrc/pgp-key-msrc).</span></span>

<span data-ttu-id="cb15d-109">您的答复将在24小时内收到。</span><span class="sxs-lookup"><span data-stu-id="cb15d-109">You should receive a response within 24 hours.</span></span> <span data-ttu-id="cb15d-110">如果由于某种原因而不是，请跟进电子邮件以确保收到原始邮件。</span><span class="sxs-lookup"><span data-stu-id="cb15d-110">If for some reason you do not, please follow up via email to ensure we received your original message.</span></span> <span data-ttu-id="cb15d-111">可在 [microsoft.com/msrc](https://www.microsoft.com/msrc)中找到其他信息。</span><span class="sxs-lookup"><span data-stu-id="cb15d-111">Additional information can be found at [microsoft.com/msrc](https://www.microsoft.com/msrc).</span></span> 

<span data-ttu-id="cb15d-112">请在下面列出所请求的信息 (，您可以提供) ，帮助我们更好地了解可能问题的性质和范围：</span><span class="sxs-lookup"><span data-stu-id="cb15d-112">Please include the requested information listed below (as much as you can provide) to help us better understand the nature and scope of the possible issue:</span></span>

  * <span data-ttu-id="cb15d-113">问题的类型 (例如缓冲区溢出、SQL 注入、跨网站脚本等 ) </span><span class="sxs-lookup"><span data-stu-id="cb15d-113">Type of issue (e.g. buffer overflow, SQL injection, cross-site scripting, etc.)</span></span>
  * <span data-ttu-id="cb15d-114">源文件 (s 的完整路径，) 与问题的表现形式相关</span><span class="sxs-lookup"><span data-stu-id="cb15d-114">Full paths of source file(s) related to the manifestation of the issue</span></span>
  * <span data-ttu-id="cb15d-115">受影响的源代码 (标记/分支/提交或直接 URL) 的位置</span><span class="sxs-lookup"><span data-stu-id="cb15d-115">The location of the affected source code (tag/branch/commit or direct URL)</span></span>
  * <span data-ttu-id="cb15d-116">再现问题所需的任何特殊配置</span><span class="sxs-lookup"><span data-stu-id="cb15d-116">Any special configuration required to reproduce the issue</span></span>
  * <span data-ttu-id="cb15d-117">再现问题的分步说明</span><span class="sxs-lookup"><span data-stu-id="cb15d-117">Step-by-step instructions to reproduce the issue</span></span>
  * <span data-ttu-id="cb15d-118">如果可能，请验证概念或漏洞代码 () </span><span class="sxs-lookup"><span data-stu-id="cb15d-118">Proof-of-concept or exploit code (if possible)</span></span>
  * <span data-ttu-id="cb15d-119">问题的影响，包括攻击者可能如何利用此问题</span><span class="sxs-lookup"><span data-stu-id="cb15d-119">Impact of the issue, including how an attacker might exploit the issue</span></span>

<span data-ttu-id="cb15d-120">此信息将帮助我们更快地会审你的报表。</span><span class="sxs-lookup"><span data-stu-id="cb15d-120">This information will help us triage your report more quickly.</span></span>

<span data-ttu-id="cb15d-121">如果你正在报告 bug bounty，则更完整的报表可能会增加更高的 bounty 奖。</span><span class="sxs-lookup"><span data-stu-id="cb15d-121">If you are reporting for a bug bounty, more complete reports can contribute to a higher bounty award.</span></span> <span data-ttu-id="cb15d-122">请访问我们的 [Microsoft Bug Bounty 程序](https://microsoft.com/msrc/bounty) 页面，了解有关我们的活动程序的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="cb15d-122">Please visit our [Microsoft Bug Bounty Program](https://microsoft.com/msrc/bounty) page for more details about our active programs.</span></span>

## <span data-ttu-id="cb15d-123">首选语言</span><span class="sxs-lookup"><span data-stu-id="cb15d-123">Preferred Languages</span></span>

<span data-ttu-id="cb15d-124">我们希望所有通信都采用英语。</span><span class="sxs-lookup"><span data-stu-id="cb15d-124">We prefer all communications to be in English.</span></span>

## <span data-ttu-id="cb15d-125">策略</span><span class="sxs-lookup"><span data-stu-id="cb15d-125">Policy</span></span>

<span data-ttu-id="cb15d-126">Microsoft 遵循 [协调漏洞披露](https://www.microsoft.com/en-us/msrc/cvd)的原则。</span><span class="sxs-lookup"><span data-stu-id="cb15d-126">Microsoft follows the principle of [Coordinated Vulnerability Disclosure](https://www.microsoft.com/en-us/msrc/cvd).</span></span>

<!-- END MICROSOFT SECURITY.MD BLOCK -->