---
title: "准备计算机以安装 |Microsoft 文档"
ms.custom: 
ms.date: 03/15/2016
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53df7a2f-638b-4921-a97f-736760248526
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26c2e732073ccc787cad32984720d7fac422a8cb
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="prepare-your-computer-for-installation"></a>准备计算机以进行安装
本主题将介绍如何通过安装和配置所有必备软件，然后再创建帐户并设置权限来准备你的计算机。  

> [!TIP] 
> 集成 MVP 准备了非常详细的分步指南，用于安装必备组件和 BizTalk Server：[BizTalk 2013 Installation and Configuration part 1](http://sandroaspbiztalkblog.wordpress.com/2013/05/05/biztalk-2013-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/)（BizTalk 2013 安装和配置第 1 部分）。  
> 
> Microsoft 不推荐某些步骤，例如，禁用用户访问控制 (UAC) 或 Windows 防火墙。 
  
> [!IMPORTANT]
>  按列出的顺序完成这些任务。  
  
##  <a name="BKMK_InstUpdates"></a> 安装 Windows 更新  
  
-   **Windows 7**：单击“开始”。 在“搜索”文本框中，键入 **Windows Update**。  
  
-   **Windows 8.1、 Windows Server 2012 和 Windows Server 2012 R2**： 单击 Windows 按钮上的键盘和类型**Windows Update**。 在搜索结果中，单击“Windows 更新”。  
  
 安装更新之后，你可能需要重新启动计算机。  
  
##  <a name="BKMK_IIS"></a> 启用 Internet Information Services  
 Microsoft Internet 信息服务 (IIS) 提供的 Web 应用程序基础结构许多 BizTalk Server 功能，包括：  
  
-   HTTP 适配器  
  
-   SOAP 适配器  
  
-   Windows SharePoint Services 适配器  
  
-   安全套接字层 (SSL) 加密  
  
-   BAM 门户  
  
#### <a name="install-iis"></a>安装 IIS

针对特定的安装步骤，请参阅： 

[安装 IIS （Windows 8 和 Windows Server 2012）](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/installing-iis-8-on-windows-server-2012)

[安装 IIS （Windows 7 和 Windows Vista）](https://docs.microsoft.com/iis/install/installing-iis-7/installing-iis-on-windows-vista-and-windows-7)


安装 IIS 时，除了默认选中的选项，还检查下列项目：  
  
- “Web 管理工具”：还需检查：  
  
    - IIS 6 管理兼容性：  
  
        - IIS 6 管理控制台  
  
        - IIS 元数据库和 IIS 6 配置兼容性  
  
    - IIS 管理控制台  
  
- **万维网服务**：展开“安全性”，还需选择：  
  
    - 基本身份验证  
  
    - Windows 身份验证  

同时还应考虑下列事项：  
  
- **.Net framework 3.5 功能**:.NET Framework 4.5 和.NET Framework 3.5 可以用于开发.Net 应用程序涉及 BizTalk 适配器包。 通常情况下， **.NET Framework 4.5 功能**已安装。 如果你将使用.NET Framework 3.5 然后在此计算机上创建应用程序**.Net Framework 3.5 功能**也可以安装。  
  
- **消息队列**：如果使用 MSMQ 适配器，可以通过选中“消息队列”创建本地 MSMQ 存储。  
  
- **SMTP 服务器**：如果使用 SMTP 适配器，可以通过选中“SMTP 服务器”创建本地 SMTP 服务器。  
  
- **Windows Identity Foundation 3.5**： 使用 CSOM 安装选项时，必须将 Windows Identity Foundation (WIF) 由 SharePoint 适配器。 [附录 b： 安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)介绍 SharePoint 适配器的 CSOM 安装选项。    
  
 
##  <a name="BKMK_XLS"></a> 安装 Microsoft Office Excel  
  
1.  运行 Microsoft Office 安装程序。  
  
2.  显示“安装类型”屏幕时，选择“自定义安装”，然后选择“下一步”。  
  
3.  在“自定义安装”屏幕上，选择“Excel”，然后选择“下一步”。  
  
4.  选择“安装”。  
  
5.  在“已完成安装”中，选择“完成”。  
  
 **补充说明**  
  
-   BizTalk Server 仅支持 32 位版本的 Microsoft Office。  
  
-   Microsoft Office Excel 需要由业务活动监视 (BAM) BizTalk Server 中。 可以使用 BAM Office Excel 工作簿来定义要监视的业务流程。 还可以使用 BAM Excel 工作簿定义业务用户查看 BAM 所收集的数据的方式。  
  
-   若要成功将 BAM.xla 加载到 Excel 中，请在“Office 共享功能”下安装“Visual Basic for Applications”。 否则，可能会收到“此工作簿已丢失了其 VBA 项目、ActiveX 控件以及其他任何与可编程性相关的功能”错误。  
  
##  <a name="BKMK_VS"></a> 安装 Visual Studio  
  
1.  以管理员身份运行 Visual Studio 安装程序。  
  
2.  接受许可协议，然后单击“下一步”。  
  
3.  在“要安装的可选功能”中，选择所需的选项，然后选择“安装”。 BizTalk Server 不需要任何可选功能。  
  
4.  在“完成”页面上，关闭窗口或单击“启动”打开 Visual Studio。  
  
 **补充说明**  
  
-   如果在安装 BizTalk Server 中之前, 安装 Visual Studio，然后升级到 Visual Studio 团队资源管理器，你可能需要修复从 BizTalk Server 安装**控制面板** / **程序**选项。  
  
-   Visual Studio 会自动安装 Microsoft SQL Server Express；而 BizTalk Server 并不使用它。 最好卸载 Microsoft SQL Server Express。  
  
-   BizTalk Server 开发工具基于 Visual Studio。 至少，你必须安装 Visual Studio 的 Microsoft Visual C#®.NET 组件，然后再安装 BizTalk Server**开发人员工具和 SDK**。  
  
-   Visual Studio 是*不*所需安装 BizTalk Server 上 （仅运行时） 的生产计算机的任何应用程序开发或调试时是必需的。  
  
-   BizTalk Server 运行时需要.NET Framework 4.5。 如果已安装 Windows Communication Foundation (WCF) 适配器或 WCF 侦听器，则需要安装 .NET Framework 3.0。  
  
##  <a name="BKMK_SQL"></a> 安装 SQL Server  
 安装 [SQL Server 2008 R2](http://msdn.microsoft.com/library/bb500395\(v=sql.105\).aspx)  
  
 安装 [SQL Server 2012](http://msdn.microsoft.com/library/bb500469\(v=sql.110\).aspx)  
  
 安装 [SQL Server 2014](http://msdn.microsoft.com/library/bb500469\(v=sql.120\).aspx)  
  
 在安装 SQL Server 时，选择以下功能：  
  
-   数据库引擎服务  
  
    -   SQL Server 复制  
  
    -   全文搜索  
  
-   Analysis Services  
  
-   Reporting Services  
  
-   共享功能  
  
    -   SQL Server Data Tools (SQL Server 2014/SQL Server 2012) 或 Business Intelligence Development Studio (SQL Server 2008 R2)  
  
         [下载 SQL Server 2014 Data Tools](http://www.microsoft.com/download/details.aspx?id=42313)  
  
    -   客户端工具连接  
  
    -   Integration Services  
  
    -   管理工具 - 基本  
  
        -   管理工具 - 完整  
  
 **补充说明**  
  
-   BizTalk Server 支持所有区分大小写和不区分大小写的 SQL Server 排序规则，二进制排序规则例外。 不支持二进制排序规则。  
  
-   为了获得最佳性能，Microsoft 建议使用 SQL Server Enterprise Edition。 请参阅 [SQL Server 2008 R2 版本](http://msdn.microsoft.com/library/cc645993\(v=sql.105\).aspx)、[SQL Server 2012 版本](http://msdn.microsoft.com/library/cc645993\(v=sql.110\).aspx)或 [SQL Server 2014 版本](http://msdn.microsoft.com/library/cc645993\(v=sql.120\).aspx)。  
  
-   支持 Service Pack 和 Windows Update，并且应进行安装。  
  
-   当 BizTalk Server 和 SQL Server 在不同计算机上时，分布式事务处理协调器 (MS DTC) 处理计算机之间的事务。 SQL Server AlwaysOn 功能不支持 MSDTC 事务。 不支持 SQL Server AlwaysOn 功能。  
  
##  <a name="BKMK_MQSeries"></a> 安装 MQSeries 必备组件  
 **MQSeries 适配器**：自动随 BizTalk Server 一起安装。  
  
 **MQSeries 客户端 (MQSC) 适配器**：  
  
1.  运行 Host Integration Server (HIS) 安装  
  
2.  在组件安装中，展开“BizTalk 适配器”。  
  
3.  选择“适用于 WebSphere MQ 的 BizTalk 适配器(基于客户端)”。  
  
 **支持的 IBM WebSphere MQ 版本：**：  
  
-   IBM WebSphere MQ 6.0.2.12 和更高版本  
  
-   IBM WebSphere MQ 7.0.1.9 和更高版本  
  
-   IBM WebSphere MQ 7.1.0.5 和更高版本  
  
-   IBM WebSphere MQ 7.5.0.3 和更高版本  
  
-   IBM WebSphere MQ 8（限制为运行时；无管理 API）  
  
     MQ 版本 8 支持随附在[主机集成服务器累积更新 3](https://support.microsoft.com/kb/3019572)中。  
  
> [!NOTE]
>  如果未列出特定的 WebSphere MQ 版本，如 MQ 5.x，那么它不支持与此 BizTalk Server 版本。  
  
 **补充说明**  
  
-   最佳做法是，始终安装最新的 WebSphere MQ 修补程序包。 请参阅 [http://www.ibm.com/support/docview.wss?uid=swg27006037](http://www.ibm.com/support/docview.wss?uid=swg27006037)。  
  
-   如果在非 Windows 计算机上安装 IBM WebSphere MQ，可将 **MQSAgent COM+ 应用程序** (MQSConfigWiz.exe) 和 **MQSeries Server for Windows** 安装在同一台计算机上。 如果在 Windows 计算机上安装 IBM WebSphere MQ，则不使用也不需要 **MQSAgent COM+ 应用程序**和 **MQSeries Server for Windows** 程序。  
  
     **MQSConfigWiz.exe**包含在 BizTalk Server 安装文件。  
  
     **MQSeries Server for Windows** 不是 Microsoft 程序，必须通过 IBM WebSphere MQ 程序获得。  
  
-   [MQSeries 适配器](http://technet.microsoft.com/library/aa547973\(v=BTS.80\).aspx)提供了有关 MQSeries 适配器及配置不同组件的详细信息。 [BizTalk Server：MQSeries 和 MQSeries 客户端 (MQSC) 适配器](http://social.technet.microsoft.com/wiki/contents/articles/18316.biztalk-server-mqseries-and-mqseries-client-mqsc-adapters.aspx)提供了有关 MQSeries 和 MQSC 适配器的详细信息。  
  
-   IBM WebSphere 不是 Microsoft 产品，也不受 Microsoft 支持。 Microsoft 不保证此程序的适用性。 有关 IBM WebSphere MQ 的详细信息，请参阅 www.ibm.com。  
  
##  <a name="BKMK_BAMAlerts"></a> BAM 警报  
 使用 SQL Server 2012 和更高版本的 BAM 警报使用 SQL Server 中的数据库邮件。 使用 SQL Server 2008 R2 和较旧版本的 BAM 警报使用 SQL Notification Services。 安装或配置 BAM 警报之前, 你必须对 SQL Server 中配置 Notification Services 或数据库邮件。  
  
###  <a name="BKMK_DBMail"></a> 使用 SQL Server 2012/2014 的 BAM 警报  
 配置 [SQL Server 2012 数据库邮件](http://msdn.microsoft.com/library/hh245116\(v=sql.110\).aspx)。  
  
 配置 [SQL Server 2014 数据库邮件](http://msdn.microsoft.com/library/hh245116\(v=sql.120\).aspx)。  
  
 **补充说明**  
  
-   数据库邮件使用 SMTP 服务器发送 BAM 警报。 在 BizTalk Server 或另一台 IIS 服务器上，可以本地安装 SMTP 服务器。 [附录 D：创建 SMTP 服务器](../install-and-config-guides/appendix-d-create-the-smtp-server.md)中列出了安装和配置 SMTP 服务器的步骤。  
  
###  <a name="BKMK_SSNS"></a> 使用 SQL Server 2008 R2 的 BAM 警报 – 安装 SQL Server 2005 Notification Services  
  
1.  转到 [SQL Server 2005 SP4 功能包](http://go.microsoft.com/fwlink/p/?LinkId=286285)。  
  
2.  下载并安装以下组件的相应平台包：  
  
     **Microsoft SQL Server Native Client**  
  
    -   HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli.msi" X86 Package (sqlncli.msi)  
  
    -   HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli_x64.msi" X64 Package (sqlncli_x64.msi)  
  
     **Microsoft SQL Server 2005 管理对象集合**  
  
    -   HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO.msi" X86 Package (SQLServer2005_XMO.msi)  
  
    -   HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO_x64.msi" X64 Package (SQLServer2005_XMO_x64.msi)  
  
     **Microsoft SQL Server 2005 Notification Services 客户端组件**  
  
    -   HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS.msi" X86 Package (SQLServer2005_NS.msi)  
  
    -   HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS_x64.msi" X64 Package (SQLServer2005_NS_x64.msi)  
  
 **补充说明**  
  
-   SQL Notification Services 不需要进行配置;仅安装在 BizTalk Server。  
  
##  <a name="BKMK_WIF"></a> Windows Identity Foundation  
  
|||  
|-|-|  
|Windows 8.1、 Windows Server 2012 和 Windows Server 2012 R2|Windows Identity Foundation 作为“打开或关闭 Windows 功能”中的功能包括在操作系统中。|  
|Windows Vista SP1|可在下面的地址下载[Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331) HYPERLINK "http://www.microsoft.com/download/details.aspx?id=17331"。|  
  
 **补充说明**  
  
-   Windows Identity Foundation (WIF) 是 SharePoint 适配器或 SharePoint Online 使用与 SharePoint 客户端对象模型 (CSOM) 时所必需的。 具体来说：  
  
    |安装选项|需要 WIF|  
    |-------------------------|------------------|  
    |使用 CSOM SharePoint 适配器|是|  
    |使用 CSOM 的 SharePoint Online|是|  
    |SharePoint 适配器 Web 服务 （已弃用）|否|  
    |无 SharePoint|否|  
  
-   [附录 b： 安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)SharePoint 安装选项提供特定信息。  
  
##  <a name="BKMK_WSS"></a> 安装和配置 Microsoft SharePoint  
 安装 [SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx)  
  
 安装 [SharePoint Online 服务](http://technet.microsoft.com/library/jj819267.aspx)  
  
 安装 [SharePoint Server 2010](http://technet.microsoft.com/library/cc303424\(v=office.14\).aspx)  
  
 安装 [SharePoint 2007](http://technet.microsoft.com/library/cc303424\(v=office.12\).aspx)  
  
 **补充说明**  
  
-   如果要安装 SharePoint，则必须在继续执行剩余的 BizTalk Server 先决条件之前执行操作。  
  
-   安装和配置 SharePoint 包括下列过程：  
  
    -   安装 SharePoint  
  
    -   配置 SharePoint  
  
    -   将默认网站扩展为虚拟服务器  
  
-   [附录 B：安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)描述了 BizTalk Server 的 SharePoint 适配器安装选项。  
  
-   使用 SharePoint 适配器时，建议安装新 CSOM 选项（而不是 SharePoint Service Web Service）；相关说明请参阅[附录 B：安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)。  
  
##  <a name="BKMK_SharedMem"></a> 禁用 Shared Memory 协议  
  
1.  打开 **SQL Server 配置管理器**。  
  
2.  在“SQL Server 配置管理器”中，展开“SQL Server 网络配置”，然后选择“MSSQLSERVER 的协议”。  
  
3.  右键单击“共享内存”，然后选择“禁用”。  
  
4.  选择“SQL Server 服务”，右键单击“SQL Server (MSSQLSERVER)”，然后再选择“停止”。 该服务停止后，再次右键单击“SQL Server (MSSQLSERVER)”，然后选择“启动”。  
  
5.  关闭“SQL Server 配置管理器”。  
  
 **补充说明**  
  
-   在任务繁忙时（例如，客户端从同一计算机访问 SQL Server 时），SQL Server Shared Memory 协议可能会降低 BizTalk Server 性能。 可以通过在“SQL Server 网络配置”中禁用 Shared Memory 网络协议来解决此行为。  
  
-   ReplaceThisText  
  
##  <a name="BKMK_LocalAdmin"></a> 加入本地管理员组  
 **Windows Server 2012** : [Windows Server 2012： 如何将帐户添加到本地管理员组](http://social.technet.microsoft.com/wiki/contents/articles/13436.windows-server-2012-how-to-add-an-account-to-a-local-administrator-group.aspx)  
  
 **Windows 8.1**：若要在 Windows 8 上打开“本地用户和组”，请单击键盘上的 Windows 按钮，然后键入“组”。 在“搜索”窗口中，单击“设置”。 在“结果”窗口中，单击“编辑本地用户和组”。 单击“组”，然后双击“管理员”以添加帐户。  
  
 **Windows 7 SP1**：单击“启动”。 在“搜索”文本框中，键入“计算机管理”，然后单击将其打开。 展开“本地用户和组”，单击“组”，然后双击以添加帐户。  
  
 **补充说明**  
  
-   你必须是本地 Administrators 组的成员，才能安装和配置 BizTalk Server。  
  
##  <a name="BKMK_AppLog"></a> 配置应用程序事件日志  
  
1.  打开“事件查看器”：  
  
     **Windows Server 2012** ： 单击 Windows 按钮上的键盘和类型**事件查看器**。 在“结果”窗口中，单击“事件查看器”。  
  
     **Windows 8.1**：单击键盘上的 Windows 按钮，并键入“事件查看器”。 在“搜索”窗口中，单击“设置”。 在“结果”窗口中，单击“查看事件日志”。  
  
     **Windows 7 SP1**：单击“启动”。 在“搜索”文本框中，键入**事件查看器**，然后单击将其打开。  
  
2.  展开“Windows 日志”，右键单击“应用程序”，然后单击“属性”。 在“日志属性”中：  
  
    -   若要确定可用空间，请比较“日志大小”和“最大日志大小”属性。  
  
    -   若要提供更多的空间，请在“最大日志大小”中输入一个更大的值。  
  
    -   若要在日志变满时启用对旧事件的覆盖功能，请选择“按需要覆盖事件”。  
  
    -   若要清除日志事件，请选择“清除日志”。  
  
3.  单击“确定”关闭“事件查看器”。  
  
 **补充说明**  
  
-   BizTalk Server 安装程序会将事件记录保留在应用程序事件日志中。 日志中所需的空间量可能会超出其限制，具体取决于已安装的 BizTalk Server 功能。 如果在 BizTalk Server 安装期间应用程序事件日志空间不足，安装将失败。 更改“应用程序事件日志”设置可防止此故障。  
  
## <a name="next"></a>Next  
 [选择 BizTalk Server 功能和组件](http://msdn.microsoft.com/library/b8c43fcf-9e5c-48ba-830b-13a5177e30f0)  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)   
 [附录 A：无提示安装](../install-and-config-guides/appendix-a-silent-installation.md)   
 [附录 B：安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)   
 [附录 C：可再发行的 CAB 文件](../install-and-config-guides/appendix-c-redistributable-cab-files.md)   
 [附录 D：创建 SMTP 服务器](../install-and-config-guides/appendix-d-create-the-smtp-server.md)
