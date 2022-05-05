---
title: “企业站点发现”分步指南
ms.author: collw
author: appcompatguy
manager: saudm
ms.date: 04/29/2022
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 有关使用 Enterprise Site Discovery 准备 IE 模式的指南。
ms.openlocfilehash: e2199637d7f52236bd98a2692ac3d008d2e2837c
ms.sourcegitcommit: 592f6e40b13e28af588473b2a75c3ae697e5db2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2022
ms.locfileid: "12505655"
---
# <a name="enterprise-site-discovery-step-by-step-guide"></a>“企业站点发现”分步指南

>[!Note]
> Internet Explorer 11 桌面应用程序将于 2022 年 6 月 15 日停用并停止支持（若要查看包含内容的列表， [请参阅常见问题解答](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549)）。 现在使用的 IE11 应用和网站可以在 Microsoft Edge 的 Internet Explorer 模式下打开。 [在此处了解详细信息](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/)。

本文提供了将“企业站点发现”与 Microsoft Endpoint Configuration Manager 搭配使用的分步指南。

> [!TIP]
> 除非环境需要使用本指南中的步骤，否则建议使用[Microsoft Edge部署向导](https://aka.ms/edgeadvisor)及其生成的脚本来配置Enterprise Site Discovery。

“企业站点发现”可以帮助你配置企业模式站点列表。 “企业站点发现”可以帮助你：

- 发现正在使用旧文档模式的站点。 除非这些站点正在检测新式浏览器并提供不同的 HTML，否则它们可能需要使用 IE 模式。
- 发现正在使用 ActiveX 控件的站点。 Microsoft Edge 不支持 ActiveX 控件。 除非这些站点正在检测新式浏览器并提供不同的 HTML，否则它们可能需要使用 IE 模式。

> [!NOTE]
> 本文适用于 Microsoft Edge **Stable**、**Beta** 和 **Dev** 渠道版本 77 或更高版本。

## <a name="prerequisites"></a>必备条件

本指南假定你正在使用 Microsoft Endpoint Configuration Manager 并且安装了以下服务和角色：

- Microsoft Endpoint Configuration Manager
- Microsoft SQL Server Reporting Services
-  (配置了可选) Configuration Manager Reporting Services点角色

## <a name="download-enterprise-site-discovery-tools"></a>下载“企业站点发现”工具

下载以下工具：

- [“企业站点发现”设置和配置包](https://go.microsoft.com/fwlink/p/?LinkId=517719)
- [Microsoft 报表生成器](https://www.microsoft.com/download/details.aspx?id=53613)

## <a name="enable-enterprise-site-discovery"></a>启用“企业站点发现”

在连接到Windows管理检测 (WMI) 以检索站点发现数据之前，需要将 WMI 类提供程序部署到正在收集此数据的设备。

从“**企业站点发现设置和配置包**”中，将内容提取到最终软件库文件共享中的某个文件夹。 示例：**\\\\DSL\\EnterpriseSiteDiscovery**。

接下来，在Microsoft Endpoint Configuration Manager中创建包，如Configuration Manager[中的包和程序中](/configmgr/apps/deploy-use/packages-and-programs)所述。

使用以下设置配置新包：

- 在 **“包** ”页上：
  - 选择 **名称** 并指定名称 **“启用站点发现”**
  - 选择 **此包包含源文件**
  - 指定提取文件以 (的源文件夹，例如 **\\\\DSL\\EnterpriseSiteDiscovery**) 
- 在“**程序类型**”页面上，选择“**标准程序**”
- 在 **“标准计划”** 页上，输入以下命令，在设备上配置 Site Discovery：

  ```dos
  
    powershell.exe -ExecutionPolicy Bypass .\IETelemetrySetUp-Win8.ps1

  ```

  > [!NOTE]
  > 该脚本支持为 `-ZoneAllowList` 和 `-SiteAllowList` 使用命令行开关。 对于此分步操作，我们将通过 [组](#configure-enterprise-site-discovery-via-group-policy)策略配置这些选项。

- 在 **“标准计划”** 页上：
  - 选择要运行 **“隐藏”** 的选项
  - 在 **“程序”下可以运行**，选择“**用户是否登录**”选项

创建程序包后，双击程序包名称“**启用站点发现**”以查看其属性。 对于 **“运行后”** 属性，选择 **Configuration Manager 重启计算机**。 WMI 数据收集将在设备重新启动后启动。

> [!NOTE]
> 可按照[客户端设置文档](/configmgr/core/clients/deploy/about-client-settings#computer-restart)中所述，配置用户必须重新启动设备的时间量。

若要确认数据收集是否正常工作，请访问几个网站并运行以下 PowerShell 命令，以验证是否正在 WMI 命名空间中填充数据。

```powershell

Get-WmiObject -Namespace “root/cimv2/IETelemetry” -Class IEURLInfo | Select-Object URL, NumberOfVisits, CrashCount, DocMode | Sort-Object

```

## <a name="configure-enterprise-site-discovery-via-group-policy"></a>通过组策略配置“企业站点发现”

启用“企业站点发现”后，可以配置要收集的数据。 请考虑当地法律和法规要求，如 [收集哪些数据](/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery#what-data-is-collected)中所述？

1. 打开组策略编辑器。
2. 选择**计算机** **ConfigurationAdministrative** >  模板 > **Windows** **ComponentsInternet** >  Explorer。
3. 双击 **“打开站点发现 WMI 输出**”。
4. 选中**已启用**。
5. 选择 **“确定** ”或 **“应用** ”以保存此策略设置。

可以选择要在其中收集站点数据的区域：

1. 双击“ **按区域限制站点发现”输出**。
2. 选中**已启用**。
3. 设置 **区域掩码**  以指示要为其启用站点发现的以下哪个区域。

    - 受限站点区域
    - Internet 区域
    - 受信任的站点区域
    - 本地 Intranet 区域
    - 本地计算机区域
   > [!NOTE]
   > 若要配置站点发现中包含的区域 () ，根据所选区域形成二进制数。 此数字的小数表示形式用于在策略中表示此数字。

    示例：区域掩码 2： **00010** 将仅收集本地 Intranet 区域的数据区域掩码 6： **00110** 将仅收集 Intranet 和受信任站点区域的数据

4. 选择 **“确定** ”或 **“应用** ”以保存此策略设置。

还可以限制要为其收集站点数据的域：

1. 双击“ **按域限制站点发现”输出**。
2. 选中**已启用**。
3. 输入要为其收集数据的域（每行一个域）。
4. 选择 **“确定** ”或 **“应用** ”以保存此策略设置。

## <a name="collect-site-discovery-data-using-configuration-manager"></a>使用 Configuration Manager 收集站点发现数据

设备现在正在生成数据，是时候在 Configuration Manager 中收集这些数据了。

1. 在Configuration Manager控制台中，选择 **AdministrationClient****** >  设置 > **Default 客户端设置**。
2. 在 **“主页** ”选项卡的 **“属性”** 组中，选择 **“属性**”。
3. 在 **“默认客户端设置**”对话框中，选择 **“硬件清单**”。
4. 在 **“设备设置**”列表中，选择 **“设置类**”。
5. 在“ **硬件清单类** ”对话框中，选择 **“添加**”。
6. 在 **“添加硬件清单类**”对话框中，选择**连接**。
7. 在“**连接到 Windows Management Instrumentation (WMI)**”对话框中，输入已在其中配置站点发现的计算机的名称。 如果要连接到其他计算机，则需要凭据以及访问 WMI 的权限。
8. 在 **WMI 命名空间** 文本框中，输入 **root\cimv2\IETelemetry**。
9. 选择**连接**。
10. 在 **“添加硬件清单类** ”对话框的 **“清单类** ”列表中，选择 WMI 类 **IESystemINfo**、 **IEUrlInfo** 和 **IECountInfo**。
11. 选择 **“确定** ”以关闭 **“类限定符** ”对话框和其他打开的对话框。

客户端更新管理点中的设置后，将在下次运行硬件清单（默认为每七天一次）时报表数据。

## <a name="import-site-discovery-reports"></a>导入站点发现报表

“企业站点发现”包中包括两个示例报表。 一份报告显示使用ActiveX控件的站点，报表显示使用旧文档模式的站点。

### <a name="configure-the-site-discovery-sample-report"></a>配置站点发现示例时报

使用这些步骤作为指南创建使用三个数据源的示例报表。 这些数据源包括：用户访问的站点、有关其系统的信息以及站点使用的文档模式。 此报表可以帮助你识别可能依赖旧文档模式的站点。

1. 将报表 **SCCM_Report-Site_Discovery.rdl** 复制到 Configuration Manager 服务器。
2. 安装 [Microsoft 报表生成器](/sql/reporting-services/install-windows/install-report-builder)。
3. 双击 **SCCM_Report-Site_Discovery.rdl** 在报表生成器中打开报表。
4. 首次尝试打开报表时，它将会尝试联系在其中创建该报表的服务器。 当系统提示**连接到报表服务器**时，请选择 **“否**”。
5. 报表打开之后，展开“**数据源**”并双击“**DataSource1**”。
6. 在 **“数据源属性”** 窗口中，选择 **“使用报表中嵌入的连接** ”，然后选择 **“生成...**”。

> [!NOTE]
> 确保选择Microsoft SQL Server作为数据源。 Report Builder默认为Microsoft SQL Server Analysis Services 作为数据源。

7. 在“**连接属性**”窗口中，选择“**服务器名称**”，然后输入 Configuration Manager 服务器的名称。 随后，在“**选择或输入数据库名称**”中，从下拉列表中选择 Configuration Manager 数据库。
8. 选择 **“确定** ”以关闭“ **连接属性”** 窗口。
9. 选择 **“测试连接** ”以测试连接。 如果连接成功，请选择 **“确定** ”关闭 **“数据源属性** ”窗口。
10. 对**数据源 2** 重复步骤 5-9。
11. 展开“**数据集**”并双击 **DataSet1**。
12. 在 **“数据集属性** ”窗口中，单击 **“查询：** ”文本框。 将查询复制到记事本，然后**找到CM_A1B**并将其替换为在步骤 7 中选择的数据库名称。 将更新后的查询粘贴到 **“查询：** ”文本框中。
13. 对 **DataSet2**、**DataSet3** 和 **DataSet4** 重复步骤 11-12。
14. 在功能区的 **“开始** ”选项卡中，选择 **“运行** ”按钮以测试报表。
15. 保存报表并关闭 Microsoft Report Builder。
17. 将报表文件重命名为 **Site Discovery.rdl**

### <a name="configure-the-activex-sample-report"></a>配置 ActiveX 示例报表

使用以下步骤创建一个使用一个数据源的示例报表：使用 ActiveX 控件的站点。 由于 Internet Explorer 是唯一支持ActiveX控件的浏览器，因此这些站点可能需要 Microsoft Edge 中的 IE 模式。

1. 将报表 **SCCM Report Sample - ActiveX.rdl** 复制到 Configuration Manager 服务器。
2. 安装 [Microsoft 报表生成器](/sql/reporting-services/install-windows/install-report-builder)。
3. 双击 **SCCM Report Sample - ActiveX.rdl** 在报表生成器中打开报表。
4. 首次尝试打开报表时，它将会尝试联系在其中创建该报表的服务器。 当系统提示**连接到报表服务器**时，请选择 **“否**”。
5. After the report opens, expand **Data Sources** and double-click **AutoGen__5C6358F2_4BB6_4a1b_A16E_8D96795D8602_**.
6. 在 **“数据源属性”** 窗口中，选择 **“使用报表中嵌入的连接** ”，然后选择 **“生成...**”。
7. 在“**连接属性**”窗口中，选择“**服务器名称**”，然后输入 Configuration Manager 服务器的名称。 随后，在“**选择或输入数据库名称**”中，从下拉列表中选择 Configuration Manager 数据库。
8. 选择 **“确定** ”以关闭“ **连接属性”** 窗口。
9. 选择 **“测试连接** ”以测试连接。 如果连接成功，请选择 **“确定** ”关闭 **“数据源属性** ”窗口。
10. 展开“**数据集**”并双击 **DataSet1**。
11. 在 **“数据集属性** ”窗口中，单击 **“查询：** ”文本框。 将查询复制到记事本，然后**找到CM_A1B**并将其替换为在步骤 7 中选择的数据库名称。 将更新后的查询粘贴到 **“查询：** ”文本框中。
12. 在功能区的 **“开始** ”选项卡中，选择 **“运行** ”按钮以测试报表。
13. 保存报表。
14. 关闭 Microsoft 报表生成器。
15. 将文件重命名为 **ActiveX**

### <a name="upload-configured-reports-to-microsoft-sql-server-reporting-services"></a>将配置的报表上载至 Microsoft SQL Server Reporting Services

为环境配置报表之后，将它们上载至报表服务器。

1. 启动**Reporting Services Configuration Manager** 应用程序。
2. 在 **“报表服务器连接**”窗口**中**，选择连接，然后选择 **Web 门户网站标识**下列出的 URL
3. 在打开的浏览器窗口中，应位于**SQL Server Reporting Services页**上 - 为 SCCM 站点代码选择**ConfigMgr_SCCMSiteCode**文件夹。
4. 在功能区中，将鼠标悬停在 **+New** 上，然后选择 **“文件夹”** 菜单项。
5. 输入文件夹名称，例如**Enterprise Site Discovery**，然后选择 **“创建”** 按钮。
6. 选择**Enterprise Site Discovery** 文件夹。
7. 在功能区上，选择**Upload**按钮。
8. 选择 **“站点发现”** 报表，然后选择 **“确定**”。
9. 对 **ActiveX** 报表重复步骤 7 和步骤 8。

### <a name="view-reports-in-configuration-manager"></a>在 Configuration Manager 中查看报表

在自定义和上载报表之后，你就可以在 Configuration Manager 中查看它们。

1. 在 Configuration Manager 控制台中，选择“**监视**” > “**报表**” > “**报表**” > “**企业站点发现**”
2. 双击报表以进行查看。

## <a name="disable-enterprise-site-discovery"></a>禁用“企业站点发现”

收集完数据后，禁用Enterprise Site Discovery。 根据Configuration Manager中的包和程序中所述，创建第二个包以禁用[Microsoft Endpoint Configuration Manager中的站](/configmgr/apps/deploy-use/packages-and-programs)点发现Enterprise。 配置以下选项：

- 在 **“包** ”页上：
  - 选择 **“名称** ”并指定名称 **“禁用站点发现**”。
  - 选择 **此包包含源文件**。
  - 指定提取文件以 (的源文件夹，例如 **\\\\DSL\\EnterpriseSiteDiscovery**) 。
- 在 **“程序类型** ”页上，选择 **“标准程序**”。
- 在 **“标准计划”** 页上，输入以下命令行，在设备上禁用 Site Discovery：

  ```dos
  powershell.exe -ExecutionPolicy Bypass .\IETelemetrySetUp-Win8.ps1 -IEFeatureOff

  ```

- 在 **“标准计划”** 页上：
  - 选择“运行 **隐藏”** 选项。
  - 在 **“程序”下可以运行**，选择“ **用户是否登录**”选项。

## <a name="see-also"></a>另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [关于 IE 模式](./edge-ie-mode.md)
- [其他企业模式信息](/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [其他“企业站点发现”信息](/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery)
