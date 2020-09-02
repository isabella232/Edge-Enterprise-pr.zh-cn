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
# “企业站点发现”分步指南

本文提供了将“企业站点发现”与 Microsoft Endpoint Configuration Manager 搭配使用的分步指南。

“企业站点发现”可以帮助你配置企业模式站点列表。 “企业站点发现”可以帮助你：

- 发现正在使用旧文档模式的站点。 除非这些站点正在检测新式浏览器并提供不同的 HTML，否则它们可能需要使用 IE 模式。
- 发现正在使用 ActiveX 控件的站点。 Microsoft Edge 不支持 ActiveX 控件。 除非这些站点正在检测新式浏览器并提供不同的 HTML，否则它们可能需要使用 IE 模式。

> [!NOTE]
> 本文适用于 Microsoft Edge **Stable**、**Beta** 和 **Dev** 渠道版本 77 或更高版本。

## 必备条件

本指南假定你正在使用 Microsoft Endpoint Configuration Manager 并且安装了以下服务和角色：

1. Microsoft Endpoint Configuration Manager
2. Microsoft SQL Server Reporting Services
3. （可选）已配置 Configuration Manager Reporting Services 点角色

## 下载“企业站点发现”工具

下载以下工具：

- [“企业站点发现”设置和配置包](https://go.microsoft.com/fwlink/p/?LinkId=517719)
- [Microsoft 报表生成器](https://www.microsoft.com/download/details.aspx?id=53613)

## 启用“企业站点发现”

必须先在设备上部署 WMI 类提供程序，才能连接到 Windows Management Instrumentation (WMI) 以检索站点发现数据。

从“**企业站点发现设置和配置包**”中，将内容提取到最终软件库文件共享中的某个文件夹。 示例：**\\\\DSL\\EnterpriseSiteDiscovery**。

接着，按照[文档](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)中所述，在 Microsoft Endpoint Configuration Manager 中创建一个程序包，然后选择以下选项：

- 在“**程序**”包上，选择“**名称**”并指定名称“**启用站点发现**”
- 在“**程序包**”页面上，选择“**此程序包包含源文件**”
- 在“**程序包**”页面上，指定文件所提取到的源文件夹（例如，**\\\\DSL\\EnterpriseSiteDiscovery**）
- 在“**程序类型**”页面上，选择“**标准程序**”
- 在“**标准程序**”页面上，按如下所示输入命令行以配置设备上的站点发现：
  ```dos
  powershell.exe -ExecutionPolicy Bypass .\IETelemetrySetUp-Win8.ps1
  ```
  > [!NOTE]
  > 该脚本支持为 `-ZoneAllowList` 和 `-SiteAllowList` 使用命令行开关。 在本分步指南中，我们将通过组策略配置这些选项（如下所示）。
- 在“**标准程序**”页面上，选择用于运行“**已隐藏**”的选项。
- 在“**标准程序**”页面的“**程序可运行**”下，选择选项“**用户是否已登录**”

创建程序包后，双击程序包名称“**启用站点发现**”以查看其属性。 在“**运行后**”属性中，选择“**Configuration Manager 重新启动计算机**”。 WMI 数据收集将在设备重启之后开始。

> [!NOTE]
> 可按照[客户端设置文档](https://docs.microsoft.com/configmgr/core/clients/deploy/about-client-settings#computer-restart)中所述，配置用户必须重新启动设备的时间量。

## 通过组策略配置“企业站点发现”

启用“企业站点发现”后，可以配置要收集的数据。 请考虑当地法律和法规要求，如[此处](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery#what-data-is-collected)所述。

1. 打开组策略编辑器
2. 单击“**计算机配置**” > “**管理模板**” > “**Windows 组件**” > “**Internet Explorer**” 
3. 双击“**打开站点发现 WMI 输出**”
4. 选中“已启用”****
5. 单击“**确定**”或“**应用**”以保存此策略设置

可限制在其中收集站点数据的区域：

1. 双击“**按区域限制站点发现输出**”
2. 选中“已启用”****
3. 输入一个位掩码，指示要为其启用站点发现的区域：
    1. 受限制的站点区域
    2. Internet 区域
    3. 受信任的站点区域
    4. 本地 Intranet 区域
    5. 本地计算机区域
    
    示例 1：**00010** 将仅收集本地 Intranet 区域数据

    示例2： **10111** 将收集除 Internet 区域之外的所有区域的数据
4. 单击“**确定**”或“**应用**”以保存此策略设置

可限制为其收集站点数据的域：

1. 双击“**按域限制站点发现输出**”
2. 选中“已启用”****
3. 输入想要为其收集数据的域（一行输入一个域）
4. 单击“**确定**”或“**应用**”以保存此策略设置

## 使用 Configuration Manager 收集站点发现数据

设备现在正在生成数据，是时候在 Configuration Manager 中收集这些数据了。

1. 在 Configuration Manager 控制台中，选择“**管理**” > “**客户端设置**” > “**默认客户端设置**”
2. 在“**主页**”选项卡的“**属性**”组中，选择“**属性**”
3. 在“**默认客户端设置**”对话框中，选择“**硬件清单**”
4. 在“**设备设置**”列表中，选择“**设置类**”
5. 在“**硬件清单类**”对话框中，选择“**添加**”
6. 在“**添加硬件清单类**”对话框中，单击“**连接**”
7. 在“**连接到 Windows Management Instrumentation (WMI)**”对话框中，输入已在其中配置站点发现的计算机的名称。 如果要连接到其他计算机，则需要凭据以及访问 WMI 的权限。
8. 在“**WMI 命名空间**”文本框中，输入 **root\cimv2\IETelemetry**
9. 选择“**连接**”
10. 在“**添加硬件清单类**”对话框的“**清单类**”列表中，选择 WMI 类 **IESystemINfo**、**IEUrlInfo** 和 **IECountInfo*。
11. 单击“**确定**”关闭“**类限定符**”对话框和其他打开的对话。

客户端更新管理点中的设置后，将在下次运行硬件清单（默认为每七天一次）时报表数据。

## 导入站点发现报表

“企业站点发现”包中包括两个示例报表。 一个报表显示使用 ActiveX 控件的站点，另一个报表显示使用旧文档模式的站点。

### 配置站点发现示例时报

使用以下步骤创建一个使用以下三种数据源的示例报表：用户访问的站点、与用户系统相关的信息以及站点使用的文档模式。 此报表可以帮助你识别可能依赖旧文档模式的站点。

1. 将报表 **SCCM_Report-Site_Discovery.rdl** 复制到 Configuration Manager 服务器。
2. 安装 [Microsoft 报表生成器](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder?view=sql-server-ver15)。
3. 双击 **SCCM_Report-Site_Discovery.rdl** 在报表生成器中打开报表。
4. 首次尝试打开报表时，它将会尝试联系在其中创建该报表的服务器。 提示“**连接到报表服务器**”时，单击“**否**”。
5. 报表打开之后，展开“**数据源**”并双击“**DataSource1**”。
6. 在“**数据源属性**”窗口中，选择“**使用我的报表中嵌入的链接**”，然后单击“**生成...**”按钮。
7. 在“**连接属性**”窗口中，选择“**服务器名称**”，然后输入 Configuration Manager 服务器的名称。 随后，在“**选择或输入数据库名称**”中，从下拉列表中选择 Configuration Manager 数据库。
8. 单击“**确定**”关闭“**连接属性**”窗口。
9. 单击“**测试连接**”测试连接。 如果连接成功，则单击“**确定**”关闭“**数据源属性**”窗口。
10. 对**数据源 2** 重复步骤 5-9。
11. 展开“**数据集**”并双击 **DataSet1**。
12. 在“**数据集属性**”窗口中，单击“**查询:**”文本框并将 **USE CM_A1B** 替换为在步骤 7 中选择的数据库名称。
13. 对 **DataSet2**、**DataSet3** 和 **DataSet4** 重复步骤 11-12。
14. 在功能区的“**主页**”选项卡中，单击“**运行**”按钮测试报表。
15. 保存报表。
16. 关闭 Microsoft 报表生成器。
17. 将文件重命名为 **Site Discovery.rdl**

### 配置 ActiveX 示例报表

使用以下步骤创建一个使用一个数据源的示例报表：使用 ActiveX 控件的站点。 Internet Explorer 是唯一支持 ActiveX 控件的浏览器，因此，这些站点可能需要 IE 模式。

1. 将报表 **SCCM Report Sample - ActiveX.rdl** 复制到 Configuration Manager 服务器。
2. 安装 [Microsoft 报表生成器](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder?view=sql-server-ver15)。
3. 双击 **SCCM Report Sample - ActiveX.rdl** 在报表生成器中打开报表。
4. 首次尝试打开报表时，它将会尝试联系在其中创建该报表的服务器。 提示“**连接到报表服务器**”时，单击“**否**”。
5. After the report opens, expand **Data Sources** and double-click **AutoGen__5C6358F2_4BB6_4a1b_A16E_8D96795D8602_**.
6. 在“**数据源属性**”窗口中，选择“**使用我的报表中嵌入的链接**”，然后单击“**生成...**”按钮。
7. 在“**连接属性**”窗口中，选择“**服务器名称**”，然后输入 Configuration Manager 服务器的名称。 随后，在“**选择或输入数据库名称**”中，从下拉列表中选择 Configuration Manager 数据库。
8. 单击“**确定**”关闭“**连接属性**”窗口。
9. 单击“**测试连接**”测试连接。 如果连接成功，则单击“**确定**”关闭“**数据源属性**”窗口。
10. 展开“**数据集**”并双击 **DataSet1**。
11. 在“**数据集属性**”窗口中，单击“**查询:**”文本框并将 **USE CM_A1B** 替换为在步骤 7 中选择的数据库名称。
12. 在功能区的“**主页**”选项卡中，单击“**运行**”按钮测试报表。
13. 保存报表。
14. 关闭 Microsoft 报表生成器。
15. 将文件重命名为 **ActiveX**

### 将配置的报表上载至 Microsoft SQL Server Reporting Services

为环境配置报表之后，将它们上载至报表服务器。

1. 启动**Reporting Services Configuration Manager** 应用程序。
2. 在“**报表服务器连接**”窗口中，单击“**连接**”，然后单击 **Web 门户网站标识**下面列出的 URL。
3. 在打开的浏览器窗口中，你应该位于 **SQL Server Reporting Services 页面**上 - 单击 SCCM 站点代码的 **ConfigMgr_SCCMSiteCode** 文件夹。
4. 在功能区中，将鼠标悬停在“**+新建**”并单击“**文件夹**”菜单项。
5. 输入文件夹名称，例如 **Enterprise Site Discovery**，然后单击“**创建**”按钮。
6. 单击“**企业站点发现**”文件夹。
7. 在功能区中，单击“**上载**”按钮。
8. 选择“**站点发现**”报表，然后单击“**确定**”。
9. 对 **ActiveX** 报表重复步骤 7 和步骤 8。

### 在 Configuration Manager 中查看报表

在自定义和上载报表之后，你就可以在 Configuration Manager 中查看它们。

1. 在 Configuration Manager 控制台中，选择“**监视**” > “**报表**” > “**报表**” > “**企业站点发现**”
2. 双击报表以进行查看。

## 禁用“企业站点发现”

完成数据收集之后，应禁用“企业站点发现”。 如[文档](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)中所述，在 Microsoft Endpoint Configuration Manage 中创建另一个程序包以禁用“企业站点发现”，然后选择以下选项：

- 在“**程序包**”页面上，选择“**名称**”并指定名称“**禁用站点发现**”
- 在“**程序包**”页面上，选择“**此程序包包含源文件**”
- 在“**程序包**”页面上，指定文件所提取到的源文件夹（例如，**\\\\DSL\\EnterpriseSiteDiscovery**）
- 在“**程序类型**”页面上，选择“**标准程序**”
- 在“**标准程序**”页面上，按如下所示输入命令行以禁用站点发现：
  ```dos
  powershell.exe -ExecutionPolicy Bypass .\IETelemetrySetUp-Win8.ps1 -IEFeatureOff
  ```
- 在“**标准程序**”页面上，选择用于运行“**已隐藏**”的选项
- 在“**标准程序**”页面的“**程序可运行**”下，选择选项“**用户是否已登录**”

## 另请参阅

- [Microsoft Edge Enterprise 登录页面](https://aka.ms/EdgeEnterprise)
- [关于 IE 模式](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [其他企业模式信息](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)
- [其他“企业站点发现”信息](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery)