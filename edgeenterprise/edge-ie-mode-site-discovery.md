---
title: “企业站点发现”分步指南
ms.author: cjacks
author: appcompatguy
manager: saudm
ms.date: 04/07/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 使用“企业站点发现”为 IE 模式做准备
ms.openlocfilehash: 9ec748686b83466cd1c7d92fcc7fdc0f0d136977
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10979315"
---
# <span data-ttu-id="87429-103">“企业站点发现”分步指南</span><span class="sxs-lookup"><span data-stu-id="87429-103">Enterprise Site Discovery Step-by-Step Guide</span></span>

<span data-ttu-id="87429-104">本文提供了将“企业站点发现”与 Microsoft Endpoint Configuration Manager 搭配使用的分步指南。</span><span class="sxs-lookup"><span data-stu-id="87429-104">This article provides a step-by-step guide to using Enterprise Site Discovery with Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="87429-105">“企业站点发现”可以帮助你配置企业模式站点列表。</span><span class="sxs-lookup"><span data-stu-id="87429-105">Enterprise Site Discovery can help you configure your Enterprise Mode Site List.</span></span> <span data-ttu-id="87429-106">“企业站点发现”可以帮助你：</span><span class="sxs-lookup"><span data-stu-id="87429-106">Enterprise Site Discovery will help you:</span></span>

- <span data-ttu-id="87429-107">发现正在使用旧文档模式的站点。</span><span class="sxs-lookup"><span data-stu-id="87429-107">Discover which sites are using legacy document modes.</span></span> <span data-ttu-id="87429-108">除非这些站点正在检测新式浏览器并提供不同的 HTML，否则它们可能需要使用 IE 模式。</span><span class="sxs-lookup"><span data-stu-id="87429-108">Unless these sites are detecting modern browsers and providing different HTML, they probably need to use IE mode.</span></span>
- <span data-ttu-id="87429-109">发现正在使用 ActiveX 控件的站点。</span><span class="sxs-lookup"><span data-stu-id="87429-109">Discover which sites are using ActiveX controls.</span></span> <span data-ttu-id="87429-110">Microsoft Edge 不支持 ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="87429-110">Microsoft Edge doesn't support ActiveX controls.</span></span> <span data-ttu-id="87429-111">除非这些站点正在检测新式浏览器并提供不同的 HTML，否则它们可能需要使用 IE 模式。</span><span class="sxs-lookup"><span data-stu-id="87429-111">Unless these sites are detecting modern browsers and providing different HTML, they probably need to use IE mode.</span></span>

> [!NOTE]
> <span data-ttu-id="87429-112">本文适用于 Microsoft Edge **Stable**、**Beta** 和 **Dev** 渠道版本 77 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="87429-112">This article applies to Microsoft Edge **Stable**, **Beta** and **Dev** Channels, version 77 or later.</span></span>

## <span data-ttu-id="87429-113">必备条件</span><span class="sxs-lookup"><span data-stu-id="87429-113">Prerequisites</span></span>

<span data-ttu-id="87429-114">本指南假定你正在使用 Microsoft Endpoint Configuration Manager 并且安装了以下服务和角色：</span><span class="sxs-lookup"><span data-stu-id="87429-114">This guide assumes you're experienced with using Microsoft Endpoint Configuration Manager and have the following services and roles installed:</span></span>

1. <span data-ttu-id="87429-115">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="87429-115">Microsoft Endpoint Configuration Manager</span></span>
2. <span data-ttu-id="87429-116">Microsoft SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="87429-116">Microsoft SQL Server Reporting Services</span></span>
3. <span data-ttu-id="87429-117">（可选）已配置 Configuration Manager Reporting Services 点角色</span><span class="sxs-lookup"><span data-stu-id="87429-117">(Optional) Configuration Manager Reporting Services Point Role configured</span></span>

## <span data-ttu-id="87429-118">下载“企业站点发现”工具</span><span class="sxs-lookup"><span data-stu-id="87429-118">Download Enterprise Site Discovery Tools</span></span>

<span data-ttu-id="87429-119">下载以下工具：</span><span class="sxs-lookup"><span data-stu-id="87429-119">Download the following tools:</span></span>

- [<span data-ttu-id="87429-120">“企业站点发现”设置和配置包</span><span class="sxs-lookup"><span data-stu-id="87429-120">Enterprise Site Discovery Setup and Configuration Package</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=517719)
- [<span data-ttu-id="87429-121">Microsoft 报表生成器</span><span class="sxs-lookup"><span data-stu-id="87429-121">Microsoft Report Builder</span></span>](https://www.microsoft.com/download/details.aspx?id=53613)

## <span data-ttu-id="87429-122">启用“企业站点发现”</span><span class="sxs-lookup"><span data-stu-id="87429-122">Enable Enterprise Site Discovery</span></span>

<span data-ttu-id="87429-123">必须先在设备上部署 WMI 类提供程序，才能连接到 Windows Management Instrumentation (WMI) 以检索站点发现数据。</span><span class="sxs-lookup"><span data-stu-id="87429-123">Before you can connect to Windows Management Instrumentation (WMI) to retrieve site discovery data, you must first deploy the WMI class provider to the device.</span></span>

<span data-ttu-id="87429-124">从“**企业站点发现设置和配置包**”中，将内容提取到最终软件库文件共享中的某个文件夹。</span><span class="sxs-lookup"><span data-stu-id="87429-124">From the **Enterprise Site Discovery Setup and Configuration Package**, extract the contents to a folder in your definitive software library file share.</span></span> <span data-ttu-id="87429-125">示例：**\\\\DSL\\EnterpriseSiteDiscovery**。</span><span class="sxs-lookup"><span data-stu-id="87429-125">Example: **\\\\DSL\\EnterpriseSiteDiscovery**.</span></span>

<span data-ttu-id="87429-126">接着，按照[文档](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)中所述，在 Microsoft Endpoint Configuration Manager 中创建一个程序包，然后选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="87429-126">Next, create a package in Microsoft Endpoint Configuration Manager, as described in the [documentation](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs), selecting the following options:</span></span>

- <span data-ttu-id="87429-127">在“**程序**”包上，选择“**名称**”并指定名称“**启用站点发现**”</span><span class="sxs-lookup"><span data-stu-id="87429-127">On the **Package** page, select **Name** and specify the name **Enable Site Discovery**</span></span>
- <span data-ttu-id="87429-128">在“**程序包**”页面上，选择“**此程序包包含源文件**”</span><span class="sxs-lookup"><span data-stu-id="87429-128">On the **Package** page, select **This package contains source files**</span></span>
- <span data-ttu-id="87429-129">在“**程序包**”页面上，指定文件所提取到的源文件夹（例如，**\\\\DSL\\EnterpriseSiteDiscovery**）</span><span class="sxs-lookup"><span data-stu-id="87429-129">On the **Package** page, specify the source folder you extracted the files to (for example, **\\\\DSL\\EnterpriseSiteDiscovery**)</span></span>
- <span data-ttu-id="87429-130">在“**程序类型**”页面上，选择“**标准程序**”</span><span class="sxs-lookup"><span data-stu-id="87429-130">On the **Program Type** page, choose **Standard Program**</span></span>
- <span data-ttu-id="87429-131">在“**标准程序**”页面上，按如下所示输入命令行以配置设备上的站点发现：</span><span class="sxs-lookup"><span data-stu-id="87429-131">On the **Standard Program** page, enter the command line to configure Site Discovery on the device as follows:</span></span>
  ```dos
  powershell.exe -ExecutionPolicy Bypass .\IETelemetrySetUp-Win8.ps1
  ```
  > [!NOTE]
  > <span data-ttu-id="87429-132">该脚本支持为 `-ZoneAllowList` 和 `-SiteAllowList` 使用命令行开关。</span><span class="sxs-lookup"><span data-stu-id="87429-132">The script supports using command line switches for `-ZoneAllowList` and `-SiteAllowList`.</span></span> <span data-ttu-id="87429-133">在本分步指南中，我们将通过组策略配置这些选项（如下所示）。</span><span class="sxs-lookup"><span data-stu-id="87429-133">For this step-by-step, we will configure these options via group policy (below).</span></span>
- <span data-ttu-id="87429-134">在“**标准程序**”页面上，选择用于运行“**已隐藏**”的选项。</span><span class="sxs-lookup"><span data-stu-id="87429-134">On the **Standard Program** page, select the option to run **Hidden**.</span></span>
- <span data-ttu-id="87429-135">在“**标准程序**”页面的“**程序可运行**”下，选择选项“**用户是否已登录**”</span><span class="sxs-lookup"><span data-stu-id="87429-135">On the **Standard Program** page, under **Program can run**, select the option **Whether or not a user is logged in**</span></span>

<span data-ttu-id="87429-136">创建程序包后，双击程序包名称“**启用站点发现**”以查看其属性。</span><span class="sxs-lookup"><span data-stu-id="87429-136">After creating the package, double-click on the package name **Enable Site Discovery** to view its properties.</span></span> <span data-ttu-id="87429-137">在“**运行后**”属性中，选择“**Configuration Manager 重新启动计算机**”。</span><span class="sxs-lookup"><span data-stu-id="87429-137">In the **After running** property, select **Configuration manager restarts computer**.</span></span> <span data-ttu-id="87429-138">WMI 数据收集将在设备重启之后开始。</span><span class="sxs-lookup"><span data-stu-id="87429-138">WMI data collection will begin after the devices reboot.</span></span>

> [!NOTE]
> <span data-ttu-id="87429-139">可按照[客户端设置文档](https://docs.microsoft.com/configmgr/core/clients/deploy/about-client-settings#computer-restart)中所述，配置用户必须重新启动设备的时间量。</span><span class="sxs-lookup"><span data-stu-id="87429-139">You can configure the amount of time a user has to restart the device as described in the [client settings documentation](https://docs.microsoft.com/configmgr/core/clients/deploy/about-client-settings#computer-restart).</span></span>

## <span data-ttu-id="87429-140">通过组策略配置“企业站点发现”</span><span class="sxs-lookup"><span data-stu-id="87429-140">Configure Enterprise Site Discovery via Group Policy</span></span>

<span data-ttu-id="87429-141">启用“企业站点发现”后，可以配置要收集的数据。</span><span class="sxs-lookup"><span data-stu-id="87429-141">With Enterprise Site Discovery enabled, you can configure what data you'll collect.</span></span> <span data-ttu-id="87429-142">请考虑当地法律和法规要求，如[此处](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery#what-data-is-collected)所述。</span><span class="sxs-lookup"><span data-stu-id="87429-142">Consider local laws and regulatory requirements as described [here](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery#what-data-is-collected).</span></span>

1. <span data-ttu-id="87429-143">打开组策略编辑器</span><span class="sxs-lookup"><span data-stu-id="87429-143">Open Group Policy Editor</span></span>
2. <span data-ttu-id="87429-144">单击“**计算机配置**” > “**管理模板**” > “**Windows 组件**” > “**Internet Explorer**”</span><span class="sxs-lookup"><span data-stu-id="87429-144">Click **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Internet Explorer**</span></span> 
3. <span data-ttu-id="87429-145">双击“**打开站点发现 WMI 输出**”</span><span class="sxs-lookup"><span data-stu-id="87429-145">Double-click **Turn on Site Discovery WMI output**</span></span>
4. <span data-ttu-id="87429-146">选中“已启用”\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87429-146">Select **Enabled**</span></span>
5. <span data-ttu-id="87429-147">单击“**确定**”或“**应用**”以保存此策略设置</span><span class="sxs-lookup"><span data-stu-id="87429-147">Click **OK** or **Apply** to save this policy setting</span></span>

<span data-ttu-id="87429-148">可限制在其中收集站点数据的区域：</span><span class="sxs-lookup"><span data-stu-id="87429-148">You can limit the zones in which you collect site data:</span></span>

1. <span data-ttu-id="87429-149">双击“**按区域限制站点发现输出**”</span><span class="sxs-lookup"><span data-stu-id="87429-149">Double-click **Limit Site Discovery output by Zone**</span></span>
2. <span data-ttu-id="87429-150">选中“已启用”\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87429-150">Select **Enabled**</span></span>
3. <span data-ttu-id="87429-151">输入一个位掩码，指示要为其启用站点发现的区域：</span><span class="sxs-lookup"><span data-stu-id="87429-151">Enter a bitmask indicating which zones to enable site discover for:</span></span>
    1. <span data-ttu-id="87429-152">受限制的站点区域</span><span class="sxs-lookup"><span data-stu-id="87429-152">Restricted Sites zone</span></span>
    2. <span data-ttu-id="87429-153">Internet 区域</span><span class="sxs-lookup"><span data-stu-id="87429-153">Internet zone</span></span>
    3. <span data-ttu-id="87429-154">受信任的站点区域</span><span class="sxs-lookup"><span data-stu-id="87429-154">Trusted Sites zone</span></span>
    4. <span data-ttu-id="87429-155">本地 Intranet 区域</span><span class="sxs-lookup"><span data-stu-id="87429-155">Local Intranet zone</span></span>
    5. <span data-ttu-id="87429-156">本地计算机区域</span><span class="sxs-lookup"><span data-stu-id="87429-156">Local Machine zone</span></span>
    
    <span data-ttu-id="87429-157">示例 1：**00010** 将仅收集本地 Intranet 区域数据</span><span class="sxs-lookup"><span data-stu-id="87429-157">Example 1: **00010** will collect data only for the Local Intranet zone</span></span>

    <span data-ttu-id="87429-158">示例2： **10111** 将收集除 Internet 区域之外的所有区域的数据</span><span class="sxs-lookup"><span data-stu-id="87429-158">Example 2: **10111** will collect data for all zones except the Internet zone</span></span>
4. <span data-ttu-id="87429-159">单击“**确定**”或“**应用**”以保存此策略设置</span><span class="sxs-lookup"><span data-stu-id="87429-159">Click **OK** or **Apply** to save this policy setting</span></span>

<span data-ttu-id="87429-160">可限制为其收集站点数据的域：</span><span class="sxs-lookup"><span data-stu-id="87429-160">You can limit the domains for which you collect site data:</span></span>

1. <span data-ttu-id="87429-161">双击“**按域限制站点发现输出**”</span><span class="sxs-lookup"><span data-stu-id="87429-161">Double-click **Limit Site Discovery output by domain**</span></span>
2. <span data-ttu-id="87429-162">选中“已启用”\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="87429-162">Select **Enabled**</span></span>
3. <span data-ttu-id="87429-163">输入想要为其收集数据的域（一行输入一个域）</span><span class="sxs-lookup"><span data-stu-id="87429-163">Enter the domains you want to collect data for, one domain per line</span></span>
4. <span data-ttu-id="87429-164">单击“**确定**”或“**应用**”以保存此策略设置</span><span class="sxs-lookup"><span data-stu-id="87429-164">Click **OK** or **Apply** to save this policy setting</span></span>

## <span data-ttu-id="87429-165">使用 Configuration Manager 收集站点发现数据</span><span class="sxs-lookup"><span data-stu-id="87429-165">Collect Site Discovery data using Configuration Manager</span></span>

<span data-ttu-id="87429-166">设备现在正在生成数据，是时候在 Configuration Manager 中收集这些数据了。</span><span class="sxs-lookup"><span data-stu-id="87429-166">Now that your devices are generating data, it's time to collect this data in Configuration Manager.</span></span>

1. <span data-ttu-id="87429-167">在 Configuration Manager 控制台中，选择“**管理**” > “**客户端设置**” > “**默认客户端设置**”</span><span class="sxs-lookup"><span data-stu-id="87429-167">In the Configuration Manager console, choose **Administration** > **Client Settings** > **Default Client Settings**</span></span>
2. <span data-ttu-id="87429-168">在“**主页**”选项卡的“**属性**”组中，选择“**属性**”</span><span class="sxs-lookup"><span data-stu-id="87429-168">On the **Home** tab, in the **Properties** group, choose **Properties**</span></span>
3. <span data-ttu-id="87429-169">在“**默认客户端设置**”对话框中，选择“**硬件清单**”</span><span class="sxs-lookup"><span data-stu-id="87429-169">In the **Default Client Settings** dialog box, choose **Hardware Inventory**</span></span>
4. <span data-ttu-id="87429-170">在“**设备设置**”列表中，选择“**设置类**”</span><span class="sxs-lookup"><span data-stu-id="87429-170">In the **Device Settings** list, choose **Set Classes**</span></span>
5. <span data-ttu-id="87429-171">在“**硬件清单类**”对话框中，选择“**添加**”</span><span class="sxs-lookup"><span data-stu-id="87429-171">In the **Hardware Inventory Classes** dialog box, choose **Add**</span></span>
6. <span data-ttu-id="87429-172">在“**添加硬件清单类**”对话框中，单击“**连接**”</span><span class="sxs-lookup"><span data-stu-id="87429-172">In the **Add Hardware Inventory Class** dialog box, click **Connect**</span></span>
7. <span data-ttu-id="87429-173">在“**连接到 Windows Management Instrumentation (WMI)**”对话框中，输入已在其中配置站点发现的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="87429-173">In the **Connect to Windows Management Instrumentation (WMI)** dialog box, enter the name of a computer where Enterprise Site Discovery is configured.</span></span> <span data-ttu-id="87429-174">如果要连接到其他计算机，则需要凭据以及访问 WMI 的权限。</span><span class="sxs-lookup"><span data-stu-id="87429-174">If you're connecting to another computer, you'll need credentials with permission to access WMI.</span></span>
8. <span data-ttu-id="87429-175">在“**WMI 命名空间**”文本框中，输入 **root\cimv2\IETelemetry**</span><span class="sxs-lookup"><span data-stu-id="87429-175">In the **WMI Namespace** text box, enter **root\cimv2\IETelemetry**</span></span>
9. <span data-ttu-id="87429-176">选择“**连接**”</span><span class="sxs-lookup"><span data-stu-id="87429-176">Choose **Connect**</span></span>
10. <span data-ttu-id="87429-177">在“**添加硬件清单类**”对话框的“**清单类**”列表中，选择 WMI 类 **IESystemINfo**、**IEUrlInfo** 和 \**IECountInfo*。</span><span class="sxs-lookup"><span data-stu-id="87429-177">In the **Add Hardware Inventory Class** dialog box, in the **Inventory classes** list, select the WMI classes **IESystemINfo**, **IEUrlInfo**, and \**IECountInfo*.</span></span>
11. <span data-ttu-id="87429-178">单击“**确定**”关闭“**类限定符**”对话框和其他打开的对话。</span><span class="sxs-lookup"><span data-stu-id="87429-178">Click **OK** to close the **Class qualifiers** dialog box and the other open dialogs.</span></span>

<span data-ttu-id="87429-179">客户端更新管理点中的设置后，将在下次运行硬件清单（默认为每七天一次）时报表数据。</span><span class="sxs-lookup"><span data-stu-id="87429-179">After the client updates settings from the management point, data will be reported when the next hardware inventory runs (by default every seven days).</span></span>

## <span data-ttu-id="87429-180">导入站点发现报表</span><span class="sxs-lookup"><span data-stu-id="87429-180">Import Site Discovery reports</span></span>

<span data-ttu-id="87429-181">“企业站点发现”包中包括两个示例报表。</span><span class="sxs-lookup"><span data-stu-id="87429-181">The Enterprise Site Discovery package includes two sample reports.</span></span> <span data-ttu-id="87429-182">一个报表显示使用 ActiveX 控件的站点，另一个报表显示使用旧文档模式的站点。</span><span class="sxs-lookup"><span data-stu-id="87429-182">One report shows sites using ActiveX controls, and another shows sites using legacy document modes.</span></span>

### <span data-ttu-id="87429-183">配置站点发现示例时报</span><span class="sxs-lookup"><span data-stu-id="87429-183">Configure the Site Discovery sample report</span></span>

<span data-ttu-id="87429-184">使用以下步骤创建一个使用以下三种数据源的示例报表：用户访问的站点、与用户系统相关的信息以及站点使用的文档模式。</span><span class="sxs-lookup"><span data-stu-id="87429-184">Use the following procedure to create a sample report that uses three data sources: the sites a user visits, information about their system, and the document modes used by the sites.</span></span> <span data-ttu-id="87429-185">此报表可以帮助你识别可能依赖旧文档模式的站点。</span><span class="sxs-lookup"><span data-stu-id="87429-185">This report helps you identify sites that may depend on legacy document modes.</span></span>

1. <span data-ttu-id="87429-186">将报表 **SCCM_Report-Site_Discovery.rdl** 复制到 Configuration Manager 服务器。</span><span class="sxs-lookup"><span data-stu-id="87429-186">Copy the report **SCCM_Report-Site_Discovery.rdl** to your Configuration Manager server.</span></span>
2. <span data-ttu-id="87429-187">安装 [Microsoft 报表生成器](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder?view=sql-server-ver15)。</span><span class="sxs-lookup"><span data-stu-id="87429-187">Install [Microsoft Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder?view=sql-server-ver15).</span></span>
3. <span data-ttu-id="87429-188">双击 **SCCM_Report-Site_Discovery.rdl** 在报表生成器中打开报表。</span><span class="sxs-lookup"><span data-stu-id="87429-188">Double-click **SCCM_Report-Site_Discovery.rdl** to open the report in Report Builder.</span></span>
4. <span data-ttu-id="87429-189">首次尝试打开报表时，它将会尝试联系在其中创建该报表的服务器。</span><span class="sxs-lookup"><span data-stu-id="87429-189">The first time you try to open the report, it will try to contact the server where it was created.</span></span> <span data-ttu-id="87429-190">提示“**连接到报表服务器**”时，单击“**否**”。</span><span class="sxs-lookup"><span data-stu-id="87429-190">When prompted to **Connect to Report Server**, click **No**.</span></span>
5. <span data-ttu-id="87429-191">报表打开之后，展开“**数据源**”并双击“**DataSource1**”。</span><span class="sxs-lookup"><span data-stu-id="87429-191">After the report opens, expand **Data Sources** and double-click **DataSource1**.</span></span>
6. <span data-ttu-id="87429-192">在“**数据源属性**”窗口中，选择“**使用我的报表中嵌入的链接**”，然后单击“**生成...**”按钮。</span><span class="sxs-lookup"><span data-stu-id="87429-192">In the **Data Source Properties** window, select **Use a connection embedded in my report** and then click the **Build...** button.</span></span>
7. <span data-ttu-id="87429-193">在“**连接属性**”窗口中，选择“**服务器名称**”，然后输入 Configuration Manager 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="87429-193">In the **Connection Properties** window, select **Server Name** and enter the name of the Configuration Manager server.</span></span> <span data-ttu-id="87429-194">随后，在“**选择或输入数据库名称**”中，从下拉列表中选择 Configuration Manager 数据库。</span><span class="sxs-lookup"><span data-stu-id="87429-194">Then, in **Select or enter a database name** select the name of the Configuration Manager database from the dropdown list.</span></span>
8. <span data-ttu-id="87429-195">单击“**确定**”关闭“**连接属性**”窗口。</span><span class="sxs-lookup"><span data-stu-id="87429-195">Click **OK** to close the **Connection Properties** window.</span></span>
9. <span data-ttu-id="87429-196">单击“**测试连接**”测试连接。</span><span class="sxs-lookup"><span data-stu-id="87429-196">Click **Test Connection** to test the connection.</span></span> <span data-ttu-id="87429-197">如果连接成功，则单击“**确定**”关闭“**数据源属性**”窗口。</span><span class="sxs-lookup"><span data-stu-id="87429-197">If the connection is successful, click **OK** to close the **Data Source Properties** window.</span></span>
10. <span data-ttu-id="87429-198">对**数据源 2** 重复步骤 5-9。</span><span class="sxs-lookup"><span data-stu-id="87429-198">Repeat Steps 5 through 9 for **Data Source 2**.</span></span>
11. <span data-ttu-id="87429-199">展开“**数据集**”并双击 **DataSet1**。</span><span class="sxs-lookup"><span data-stu-id="87429-199">Expand **Datasets** and double-click **DataSet1**.</span></span>
12. <span data-ttu-id="87429-200">在“**数据集属性**”窗口中，单击“**查询:**”文本框并将 **USE CM_A1B** 替换为在步骤 7 中选择的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="87429-200">In the **Dataset Properties** window, click in the **Query:** textbox and replace **USE CM_A1B** with the database name you selected in Step 7.</span></span>
13. <span data-ttu-id="87429-201">对 **DataSet2**、**DataSet3** 和 **DataSet4** 重复步骤 11-12。</span><span class="sxs-lookup"><span data-stu-id="87429-201">Repeat steps 11 through 12 for **DataSet2**, **DataSet3**, and **DataSet4**.</span></span>
14. <span data-ttu-id="87429-202">在功能区的“**主页**”选项卡中，单击“**运行**”按钮测试报表。</span><span class="sxs-lookup"><span data-stu-id="87429-202">In the **Home** tab of the ribbon, click the **Run** button to test the report.</span></span>
15. <span data-ttu-id="87429-203">保存报表。</span><span class="sxs-lookup"><span data-stu-id="87429-203">Save the report.</span></span>
16. <span data-ttu-id="87429-204">关闭 Microsoft 报表生成器。</span><span class="sxs-lookup"><span data-stu-id="87429-204">Close Microsoft Report Builder.</span></span>
17. <span data-ttu-id="87429-205">将文件重命名为 **Site Discovery.rdl**</span><span class="sxs-lookup"><span data-stu-id="87429-205">Rename the file to **Site Discovery.rdl**</span></span>

### <span data-ttu-id="87429-206">配置 ActiveX 示例报表</span><span class="sxs-lookup"><span data-stu-id="87429-206">Configure the ActiveX sample report</span></span>

<span data-ttu-id="87429-207">使用以下步骤创建一个使用一个数据源的示例报表：使用 ActiveX 控件的站点。</span><span class="sxs-lookup"><span data-stu-id="87429-207">Use the following procedure to create a sample report that uses one data source: the sites that are using ActiveX controls.</span></span> <span data-ttu-id="87429-208">Internet Explorer 是唯一支持 ActiveX 控件的浏览器，因此，这些站点可能需要 IE 模式。</span><span class="sxs-lookup"><span data-stu-id="87429-208">Since Internet Explorer is the only browser that support ActiveX controls, these sites may require IE mode.</span></span>

1. <span data-ttu-id="87429-209">将报表 **SCCM Report Sample - ActiveX.rdl** 复制到 Configuration Manager 服务器。</span><span class="sxs-lookup"><span data-stu-id="87429-209">Copy the report **SCCM Report Sample - ActiveX.rdl** to your Configuration Manager server.</span></span>
2. <span data-ttu-id="87429-210">安装 [Microsoft 报表生成器](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder?view=sql-server-ver15)。</span><span class="sxs-lookup"><span data-stu-id="87429-210">Install [Microsoft Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder?view=sql-server-ver15).</span></span>
3. <span data-ttu-id="87429-211">双击 **SCCM Report Sample - ActiveX.rdl** 在报表生成器中打开报表。</span><span class="sxs-lookup"><span data-stu-id="87429-211">Double-click **SCCM Report Sample - ActiveX.rdl** to open the report in Report Builder.</span></span>
4. <span data-ttu-id="87429-212">首次尝试打开报表时，它将会尝试联系在其中创建该报表的服务器。</span><span class="sxs-lookup"><span data-stu-id="87429-212">The first time you try to open the report, it will try to contact the server where it was created.</span></span> <span data-ttu-id="87429-213">提示“**连接到报表服务器**”时，单击“**否**”。</span><span class="sxs-lookup"><span data-stu-id="87429-213">When prompted to **Connect to Report Server**, click **No**.</span></span>
5. <span data-ttu-id="87429-214">After the report opens, expand **Data Sources** and double-click **AutoGen__5C6358F2_4BB6_4a1b_A16E_8D96795D8602_**.</span><span class="sxs-lookup"><span data-stu-id="87429-214">After the report opens, expand **Data Sources** and double-click **AutoGen__5C6358F2_4BB6_4a1b_A16E_8D96795D8602_**.</span></span>
6. <span data-ttu-id="87429-215">在“**数据源属性**”窗口中，选择“**使用我的报表中嵌入的链接**”，然后单击“**生成...**”按钮。</span><span class="sxs-lookup"><span data-stu-id="87429-215">In the **Data Source Properties** window, select **Use a connection embedded in my report** and then click the **Build...** button.</span></span>
7. <span data-ttu-id="87429-216">在“**连接属性**”窗口中，选择“**服务器名称**”，然后输入 Configuration Manager 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="87429-216">In the **Connection Properties** window, select **Server Name** and enter the name of the Configuration Manager server.</span></span> <span data-ttu-id="87429-217">随后，在“**选择或输入数据库名称**”中，从下拉列表中选择 Configuration Manager 数据库。</span><span class="sxs-lookup"><span data-stu-id="87429-217">Then, in **Select or enter a database name** select the name of the Configuration Manager database from the dropdown list.</span></span>
8. <span data-ttu-id="87429-218">单击“**确定**”关闭“**连接属性**”窗口。</span><span class="sxs-lookup"><span data-stu-id="87429-218">Click **OK** to close the **Connection Properties** window.</span></span>
9. <span data-ttu-id="87429-219">单击“**测试连接**”测试连接。</span><span class="sxs-lookup"><span data-stu-id="87429-219">Click **Test Connection** to test the connection.</span></span> <span data-ttu-id="87429-220">如果连接成功，则单击“**确定**”关闭“**数据源属性**”窗口。</span><span class="sxs-lookup"><span data-stu-id="87429-220">If the connection is successful, click **OK** to close the **Data Source Properties** window.</span></span>
10. <span data-ttu-id="87429-221">展开“**数据集**”并双击 **DataSet1**。</span><span class="sxs-lookup"><span data-stu-id="87429-221">Expand **Datasets** and double-click **DataSet1**.</span></span>
11. <span data-ttu-id="87429-222">在“**数据集属性**”窗口中，单击“**查询:**”文本框并将 **USE CM_A1B** 替换为在步骤 7 中选择的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="87429-222">In the **Dataset Properties** window, click in the **Query:** textbox and replace **USE CM_A1B** with the database name you selected in Step 7.</span></span>
12. <span data-ttu-id="87429-223">在功能区的“**主页**”选项卡中，单击“**运行**”按钮测试报表。</span><span class="sxs-lookup"><span data-stu-id="87429-223">In the **Home** tab of the ribbon, click the **Run** button to test the report.</span></span>
13. <span data-ttu-id="87429-224">保存报表。</span><span class="sxs-lookup"><span data-stu-id="87429-224">Save the report.</span></span>
14. <span data-ttu-id="87429-225">关闭 Microsoft 报表生成器。</span><span class="sxs-lookup"><span data-stu-id="87429-225">Close Microsoft Report Builder.</span></span>
15. <span data-ttu-id="87429-226">将文件重命名为 **ActiveX**</span><span class="sxs-lookup"><span data-stu-id="87429-226">Rename the file to **ActiveX**</span></span>

### <span data-ttu-id="87429-227">将配置的报表上载至 Microsoft SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="87429-227">Upload configured reports to Microsoft SQL Server Reporting Services</span></span>

<span data-ttu-id="87429-228">为环境配置报表之后，将它们上载至报表服务器。</span><span class="sxs-lookup"><span data-stu-id="87429-228">After you've configured the reports for your environment, upload them to the reporting server.</span></span>

1. <span data-ttu-id="87429-229">启动**Reporting Services Configuration Manager** 应用程序。</span><span class="sxs-lookup"><span data-stu-id="87429-229">Launch the **Reporting Services Configuration Manager** application.</span></span>
2. <span data-ttu-id="87429-230">在“**报表服务器连接**”窗口中，单击“**连接**”，然后单击 **Web 门户网站标识**下面列出的 URL。</span><span class="sxs-lookup"><span data-stu-id="87429-230">In the **Report Server Connection** window, click **Connect** and then click on the URL listed under **Web Portal Site Identification**</span></span>
3. <span data-ttu-id="87429-231">在打开的浏览器窗口中，你应该位于 **SQL Server Reporting Services 页面**上 - 单击 SCCM 站点代码的 **ConfigMgr_SCCMSiteCode** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="87429-231">In the browser window that opens, you should be on the **SQL Server Reporting Services Page** - click the **ConfigMgr_SCCMSiteCode** folder for your SCCM Site Code.</span></span>
4. <span data-ttu-id="87429-232">在功能区中，将鼠标悬停在“**+新建**”并单击“**文件夹**”菜单项。</span><span class="sxs-lookup"><span data-stu-id="87429-232">In the ribbon, hover over **+New** and click the **Folder** menu item.</span></span>
5. <span data-ttu-id="87429-233">输入文件夹名称，例如 **Enterprise Site Discovery**，然后单击“**创建**”按钮。</span><span class="sxs-lookup"><span data-stu-id="87429-233">Enter a folder name, such as **Enterprise Site Discovery**, and then click the **Create** button.</span></span>
6. <span data-ttu-id="87429-234">单击“**企业站点发现**”文件夹。</span><span class="sxs-lookup"><span data-stu-id="87429-234">Click on the **Enterprise Site Discovery** folder.</span></span>
7. <span data-ttu-id="87429-235">在功能区中，单击“**上载**”按钮。</span><span class="sxs-lookup"><span data-stu-id="87429-235">In the ribbon, click the **Upload** button.</span></span>
8. <span data-ttu-id="87429-236">选择“**站点发现**”报表，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="87429-236">Select the **Site Discovery** report, and click **OK**.</span></span>
9. <span data-ttu-id="87429-237">对 **ActiveX** 报表重复步骤 7 和步骤 8。</span><span class="sxs-lookup"><span data-stu-id="87429-237">Repeat steps 7 and 8 for the **ActiveX** report.</span></span>

### <span data-ttu-id="87429-238">在 Configuration Manager 中查看报表</span><span class="sxs-lookup"><span data-stu-id="87429-238">View reports in Configuration Manager</span></span>

<span data-ttu-id="87429-239">在自定义和上载报表之后，你就可以在 Configuration Manager 中查看它们。</span><span class="sxs-lookup"><span data-stu-id="87429-239">Now that you've customized and uploaded the reports, you can view them in Configuration Manager.</span></span>

1. <span data-ttu-id="87429-240">在 Configuration Manager 控制台中，选择“**监视**” > “**报表**” > “**报表**” > “**企业站点发现**”</span><span class="sxs-lookup"><span data-stu-id="87429-240">In the Configuration Manager console, choose **Monitoring** > **Reporting** > **Reports** > **Enterprise Site Discovery**</span></span>
2. <span data-ttu-id="87429-241">双击报表以进行查看。</span><span class="sxs-lookup"><span data-stu-id="87429-241">Double-click on a report to view it.</span></span>

## <span data-ttu-id="87429-242">禁用“企业站点发现”</span><span class="sxs-lookup"><span data-stu-id="87429-242">Disable Enterprise Site Discovery</span></span>

<span data-ttu-id="87429-243">完成数据收集之后，应禁用“企业站点发现”。</span><span class="sxs-lookup"><span data-stu-id="87429-243">When you're finished collecting data, you should disable Enterprise Site Discovery.</span></span> <span data-ttu-id="87429-244">如[文档](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)中所述，在 Microsoft Endpoint Configuration Manage 中创建另一个程序包以禁用“企业站点发现”，然后选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="87429-244">Create a second package to disable Enterprise Site Discovery in Microsoft Endpoint Configuration Manager, as described in the [documentation](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs), selecting the following options:</span></span>

- <span data-ttu-id="87429-245">在“**程序包**”页面上，选择“**名称**”并指定名称“**禁用站点发现**”</span><span class="sxs-lookup"><span data-stu-id="87429-245">On the **Package** page, select **Name** and specify the name **Disable Site Discovery**</span></span>
- <span data-ttu-id="87429-246">在“**程序包**”页面上，选择“**此程序包包含源文件**”</span><span class="sxs-lookup"><span data-stu-id="87429-246">On the **Package** page, select **This package contains source files**</span></span>
- <span data-ttu-id="87429-247">在“**程序包**”页面上，指定文件所提取到的源文件夹（例如，**\\\\DSL\\EnterpriseSiteDiscovery**）</span><span class="sxs-lookup"><span data-stu-id="87429-247">On the **Package** page, specify the source folder you extracted the files to (for example, **\\\\DSL\\EnterpriseSiteDiscovery**)</span></span>
- <span data-ttu-id="87429-248">在“**程序类型**”页面上，选择“**标准程序**”</span><span class="sxs-lookup"><span data-stu-id="87429-248">On the **Program Type** page, choose **Standard Program**</span></span>
- <span data-ttu-id="87429-249">在“**标准程序**”页面上，按如下所示输入命令行以禁用站点发现：</span><span class="sxs-lookup"><span data-stu-id="87429-249">On the **Standard Program** page, enter the command line that will disable Site Discovery on the device as follows:</span></span>
  ```dos
  powershell.exe -ExecutionPolicy Bypass .\IETelemetrySetUp-Win8.ps1 -IEFeatureOff
  ```
- <span data-ttu-id="87429-250">在“**标准程序**”页面上，选择用于运行“**已隐藏**”的选项</span><span class="sxs-lookup"><span data-stu-id="87429-250">On the **Standard Program** page, select the option to run **Hidden**</span></span>
- <span data-ttu-id="87429-251">在“**标准程序**”页面的“**程序可运行**”下，选择选项“**用户是否已登录**”</span><span class="sxs-lookup"><span data-stu-id="87429-251">On the **Standard Program** page, under **Program can run**, select the option **Whether or not a user is logged in**</span></span>

## <span data-ttu-id="87429-252">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87429-252">See also</span></span>

- [<span data-ttu-id="87429-253">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="87429-253">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="87429-254">关于 IE 模式</span><span class="sxs-lookup"><span data-stu-id="87429-254">About IE mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [<span data-ttu-id="87429-255">其他企业模式信息</span><span class="sxs-lookup"><span data-stu-id="87429-255">Additional Enterprise Mode information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [<span data-ttu-id="87429-256">其他“企业站点发现”信息</span><span class="sxs-lookup"><span data-stu-id="87429-256">Additional Enterprise Site Discovery information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery)