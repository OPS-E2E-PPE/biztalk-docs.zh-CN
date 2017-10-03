---
title: "安装 BizTalk 适配器包 2013 R2 和 2013年 |Microsoft 文档"
description: "先决条件和步骤来安装 BAP 2013 R2 及 BizTalk Server 附带的 BAP 2013"
ms.custom: 
ms.date: 2015-12-09
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9980953a-8d38-476f-af38-4f4214ba61f2
caps.latest.revision: "107"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d91e697504adf23585392c6c761bc13b300c3ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="install-biztalk-adapter-pack-2013-r2-and-2013"></a>安装 BizTalk 适配器包 2013 R2 和 2013
本文档列出的软件要求，和步骤安装 Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] (BAP) 中包含 BizTalk Server 2013 或[!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)]。  
  
## <a name="change-log"></a>更改日志  
  
|日期|更改|  
|---|---|  
|2016 年 3 月|在**安装后...**，添加步骤来配置 Oracle 数据库适配器，以使用较新的 Oracle.DataAccess.dll 版本。|  
  
<a name="BKMK_Prereqs"></a>   
## <a name="software-prerequisites"></a>软件必备项  
 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]可以从使用：  
  
-   .NET 应用程序  
  
-   Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   ADO 接口  
  
-   Microsoft SharePoint 门户网站  
  
 所需的软件基于如何使用适配器，而异。  
  
### <a name="prerequisites-when-using-a-net-application"></a>使用.NET 应用程序时的先决条件  
当使用.NET 应用程序使用的适配器，你的开发计算机 （你要在其中创建.NET 应用程序的计算机） 上需要以下软件。 按列出的顺序安装软件。
  
|BizTalk 适配器包 2013 R2|BizTalk 适配器包 2013|  
|---|---|  
|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]R2， [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]，Windows 8.1、 Windows 7 SP1|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)][!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1、 Windows 8、 Windows 7 SP1|  
|[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]|Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]|  
|Visual Studio 2013|Visual Studio 2012|  
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|  
|企业应用程序客户端和关联的软件。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。|企业应用程序客户端和关联的软件。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。|  

### <a name="prerequisites-when-using-a-biztalk-server"></a>使用 BizTalk Server 时的先决条件  
当使用 BizTalk Server 使用适配器，BizTalk 服务器上需要以下软件。 按列出的顺序安装软件。
  
|BizTalk 适配器包 2013 R2|BizTalk 适配器包 2013|  
|---|---|  
|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]R2， [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]，Windows 8.1、 Windows 7 SP1|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)][!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1、 Windows 8、 Windows 7 SP1|  
|[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]|Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]|  
|Visual Studio 2013|Visual Studio 2012|  
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]<br /><br /> 安装[!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)]为[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]附带[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。 若要安装，请执行**自定义**(选择**BizTalk Server 外接程序**) 或**完成**安装[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]<br /><br /> 安装[!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)]为[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]附带[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。 若要安装，请执行**自定义**(选择**BizTalk Server 外接程序**) 或**完成**安装[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。|  
|BizTalk Server 2013 R2|BizTalk Server 2013|  
|企业应用程序客户端和关联的软件。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。|企业应用程序客户端和关联的软件。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。|  

### <a name="prerequisites-when-using-ado"></a>使用 ADO 时的先决条件  
  **[!INCLUDE[adaptersap](../includes/adaptersap-md.md)]** 和 **[!INCLUDE[adaptersiebel](../includes/adaptersiebel-md.md)]** 包括 ADO 层 ( *[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]* 和 *[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]* )。 此 ADO 层可以用于写入的 ADO.NET 客户端可以连接到 SAP 系统或 Siebel 系统。 你还可用于 ADO 层与 SQL Server Integration Services (SSIS) 导入和导出数据从 LOB 应用程序和 SQL Server Reporting Services (SSRS) 生成报表来显示 LOB 系统中的数据。  
  
> [!NOTE]
>  使用 SSRS ADO 提供程序仅支持 *[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]* 。  
  
使用的计算机上需要以下软件[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]ADO 界面。 按列出的顺序安装软件。
  
|BizTalk 适配器包 2013 R2|BizTalk 适配器包 2013|  
|---|---|  
|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]R2， [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]，Windows 8.1、 Windows 7 SP1|[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)][!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1、 Windows 8、 Windows 7 SP1|  
|[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]|Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]|  
|Visual Studio 2013|Visual Studio 2012|  
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|  
|[!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)], [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]|[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)], [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]|  
|企业应用程序客户端和关联的软件。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。|企业应用程序客户端和关联的软件。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。|  

### <a name="prerequisites-when-using-microsoft-sharepoint"></a>使用 Microsoft SharePoint 时的先决条件  
 使用与 Microsoft SharePoint 的适配器的目标是在 SharePoint 门户网站上显示的 LOB 应用程序中的数据。  
  
使用典型安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]和 SharePoint 可以为一台计算机或为不同任务使用不同的计算机。 下表总结了每个计算机的软件必备组件。 如果你使用的一台计算机，则会将所有软件都需要在该计算机上。 按列出的顺序安装软件。  
  
|运行 WCF 适配器服务开发向导的位置的计算机|其中承载 WCF 服务的计算机|其中你可以使用 SharePoint 设计器来定义外部内容类型的计算机|其中使用 SharePoint 提供的 LOB 应用程序中的信息的计算机|  
|---|---|---|---|  
|**BAP 2013 R2**:<ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2<br/>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>Windows 8.1<br/>Windows 7 SP1</li><li>[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]</li><li> Visual Studio 2013</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><li>相应的企业应用程序客户端和关联的软件。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。</li></ul> **BAP 2013**:<ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1<br/>Windows 8<br/>Windows 7 SP1</li><li>Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</li><li>Visual Studio 2012</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><li>相应的企业应用程序客户端和关联的软件。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。</li></ul>|**BAP 2013 R2**:<ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2<br/>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>Windows 8.1<br/>Windows 7 SP1</li><li>[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><li>相应的企业应用程序客户端和关联的软件。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。</li><li>附带了操作系统的 Internet 信息服务 (IIS) 版本。 KB 224609 列出的版本。</li></ul>**BAP 2013**:<ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1<br/>Windows 8<br/>Windows 7 SP1</li><li>Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><li>相应的企业应用程序客户端和关联的软件。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。</li><li>附带了操作系统的 Internet 信息服务 (IIS) 版本。 KB 224609 列出的版本。</li></ul>|Microsoft Office SharePoint Server 软件开发工具包 (SDK)|Microsoft Office 更新服务器基础结构。 在下载[http://go.microsoft.com/fwlink/?LinkId=128344](http://go.microsoft.com/fwlink/?LinkId=128344)。|  
  
<a name="BKMK_SuppLOB"></a>   
## <a name="supported-enterprise-application-versions"></a>支持的企业应用程序版本  

若要查看支持的特定 LOB 系统版本[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，请参阅**[支持的业务线 (LOB) 系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx)**。 

本部分列出每个适配器，任何额外的信息，如任何客户端 Dll 所需的每个适配器。  
  
### <a name="oracle-database-adapter"></a>Oracle 数据库适配器  
  
-   可选： 如果你使用 Oracle 数据库的分布式的事务，安装**Microsoft Transaction Server 的 Oracle 服务**（Oracle 客户端安装的一部分） 的计算机上运行适配器客户端。  
  
-   对于你应用程序以使用 ODP.NET 的最新版本，安装**策略 Dll**并在 GAC 中注册 Dll。 请参阅[Oracle 数据提供程序.NET 常见问题](http://www.oracle.com/technetwork/database/windows/faq-093106.html)。  

### <a name="oracle-e-business-adapter"></a>Oracle E-business 适配器  
  
-   可选： 若要使用 Oracle 数据库的分布式的事务，安装**Microsoft Transaction Server 的 Oracle 服务**（Oracle 客户端安装的一部分） 的计算机上运行适配器客户端。  
  
-   对于你应用程序以使用 ODP.NET 的最新版本，安装**策略 Dll**并在 GAC 中注册 Dll。 请参阅[Oracle 数据提供程序.NET 常见问题](http://www.oracle.com/technetwork/database/windows/faq-093106.html)。  
  
### <a name="sap-adapter"></a>SAP 适配器  
  
-   [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]需要而不考虑 SAP 系统是 Unicode 或非 Unicode 的 RFC sdk 的 Unicode 版本。  
  
-   **所需驱动程序**： 下表列出了所需的 Dll[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]以便与 SAP 系统。 必须从 SAP 服务应用商店下载的包，包含这些 Dll 的大多数。 若要从 SAP 服务应用商店获取下载： 
  
    1.  从 SAP 服务应用商店安装下载管理器可用。  
  
    2.  通过使用你的凭据适用于 SAP 服务 Marketplace 配置下载管理器。  
  
    3.  有权通过你组织中的 SAP 管理员从 SAP 服务网站下载软件。 这是必需的因为对 SAP 软件分发中心的访问权限受到下载软件授权对象。 这可确保，只能由授权用户下载软件。  
  
    4.  安装 SAPCAR 程序，需从 SAP 服务应用商店下载的包中提取文件。 SAP 服务 Marketplace 也是 SAPCAR。  
  
     32 位和 64 位版本的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，必须具有相应的 32 位和 64 位版本的这些 Dll。  
  
    -   在 32 位计算机上，必须将 Dll 的 32 位版本添加到 C:\Windows\System32 文件夹。  
  
    -   在 64 位计算机上，必须将 Dll 的 32 位版本添加到 C:\Windows\SysWow64 文件夹。 Dll 的 64 位版本必须添加到 C:\Windows\System32 文件夹中。  
  
    |SAP 客户端版本|必需的驱动程序|  
    |------------------------|----------------------|  
    |6.4|**BizTalk 适配器包 2013年仅**<br /><br /> - **SAP RFC SDK 6.40 UNICODE**。 这是可用的 SNOTE 一部分<sup>* </sup> 27517。若要下载 SDK 的说明进行操作都在[http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691)。你已下载并提取 SDK 后，将所有 Dll 从 \rfcsdk\bin 和 \rfcsdk\lib 文件夹都复制到前面此表的相关位置提到。<br /> <br /> -Dll 均可用从 SAP 作为的一部分**R3DLLINST.zip**。该文件包含 Microsoft 运行时 Dll 并可以从 SAP 站点下载。请参阅 SNOTE<sup> * </sup> 684106 有关详细信息。 你可以下载的.zip 文件[http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693)。 此链接已从你可以在其中下载包"附件"选项。<br /><br /> -如果你使用 SAP 安全网络通信 (SNC) 连接到 SAP 系统，你还必须从 SAP 相关的 Dll。 这些 Dll 是不同的 32 位和 64 位平台且可提供与 SNOTE<sup> * </sup> 352295。 你可以下载从 Dll [http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032)。 此链接已从你可以在其中下载包"附件"选项。 Dll 的名称为：<br /><br /> - **适用于 32 位**: gsskrb5.dll、 gssntlm.dll<br /><br /> -  **为 64 位 x86**: gx64krb5.dll、 gx64ntlm.dll|  
    |7.0|- **SAP RFC SDK 7.00 UNICODE**。 这是可用的 SNOTE 一部分<sup>* </sup> 27517。若要下载 SDK 的说明进行操作都在[http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691)。你已下载并提取 SDK 后，将复制所有 Dll，从 \rfcsdk\bin 和 \rfcsdk\lib 文件夹和前面此表的相关位置提到。<br /> <br /> -Dll 均可用从 SAP 作为的一部分**R3DLLINST.zip**。该文件包含 Microsoft 运行时 Dll 并可以从 SAP 站点下载。请参阅 SNOTE<sup> * </sup> 684106 有关详细信息。 你可以下载的.zip 文件[http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693)。 此链接已从你可以在其中下载包"附件"选项。<br /><br /> -如果你使用 SAP 安全网络通信 (SNC) 连接到 SAP 系统，你还必须从 SAP 相关的 Dll。 这些 Dll 是不同的 32 位和 64 位平台且可提供与 SNOTE<sup> * </sup> 352295。 你可以下载从 Dll [http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032)。 此链接已从你可以在其中下载包"附件"选项。 Dll 的名称为：<br /><br /> - **适用于 32 位**: gsskrb5.dll、 gssntlm.dll<br /><br /> - **为 64 位 x86**: gx64krb5.dll、 gx64ntlm.dll|  
    |7.1|- **SAP RFC SDK 7.10 UNICODE**。 这是可用的 SNOTE 一部分<sup>* </sup> 27517。若要下载 SDK 的说明进行操作都在[http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691)。你已下载并提取 SDK 后，将所有 Dll 从 \rfcsdk\bin 和 \rfcsdk\lib 文件夹都复制到前面此表的相关位置提到。<br /> <br /> -Dll 均可用从 SAP 作为的一部分**R3DLLINST.zip**。该文件包含 Microsoft 运行时 Dll 并可以从 SAP 站点下载。请参阅 SNOTE<sup> * </sup> 684106 有关详细信息。 你可以下载的.zip 文件[http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693)。 此链接已从你可以在其中下载包"附件"选项。<br /><br /> Microsoft Visual c + + 运行时 Dll 所需的 SAP 7.1 客户端是可从以下链接：<br /><br /> - **32 位 SAP 7.1 客户端**： 从 Vcredist_x86.exe [http://go.microsoft.com/fwlink/?LinkId=107086](http://go.microsoft.com/fwlink/?LinkId=107086)。<br /><br /> -                                 **64 位 SAP 7.1 客户端**： 从 Vcredist_x64.exe [http://go.microsoft.com/fwlink/?LinkId=107087](http://go.microsoft.com/fwlink/?LinkId=107087)。<br /><br /> -如果你使用 SAP 安全网络通信 (SNC) 连接到 SAP 系统，你还必须从 SAP 相关的 Dll。 这些 Dll 是不同的 32 位和 64 位平台且可提供与 SNOTE<sup> * </sup> 352295。 你可以下载从 Dll [http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032)。 此链接已从你可以在其中下载包"附件"选项。 Dll 的名称为：<br /><br /> - **适用于 32 位**: gsskrb5.dll、 gssntlm.dll<br /><br /> - **为 64 位 x86**: gx64krb5.dll、 gx64ntlm.dll|  
  
     * SNOTEs 是伴随发布 sap 修复程序的发行说明。  

### <a name="siebel-adapter"></a>Siebel 适配器  
任何额外的步骤。
  
### <a name="sql-adapter"></a>SQL 适配器  
  
**所需驱动程序**:  
  
-   **为 SQL Server 2005**： 如果在 SQL Server 中创建用户定义类型 (Udt)，请确保 Udt 的相应程序集添加到 GAC。  
  
-   **SQL server 2014，SQL Server 2012，SQL Server 2008 R2、 SQL Server 2008 SP1**:  
  
    -   如果你使用随 SQL Server 版本，例如，Geography，Udt 请确保以下 Dll 计算机上存在其中你使用该适配器在 SQL Server 上执行操作。 例如，如果你创建 BizTalk 项目，在 SQL Server 上执行操作，这些 Dll 必须存在于运行 BizTalk Server 的计算机上。  
  
        -   请确保 Microsoft.SqlServer.Types.dll 已添加到 GAC。  
  
        -   确保 SqlServerSpatial.dll System32 文件夹中可用。    
        
        可以通过运行 SQL Server 安装程序并选择在计算机上安装这些 Dll**管理工具-基本**和**管理工具 – 完整**中**功能选择**向导页。          
  
    -   如果你使用该适配器上的 FILESTREAM 数据类型的列执行操作，请确保已安装的 SQL 客户端连接 SDK。 你可以通过运行 SQL Server 安装程序并选择安装 SQL 客户端连接 SDK **SQL 客户端连接 SDK**中**功能选择**向导页。 适配器使用 sqlncli10.dll，安装 SQL 客户端连接 SDK，与执行 FILESTREAM 操作。  

    -   如果在 SQL Server 中创建你自己的 Udt，请确保 Udt 的相应程序集添加到 GAC。

## <a name="64-bit-support"></a>64 位支持

Siebel 适配器被支持在 32 位主机实例中。 它不被支持的 64 位主机实例中运行 Siebel 适配器。 

所有其他适配器可以在一个 32 位或 64 位主机实例中运行。 


  
 有关安装的 32 位和 64 位的受支持的安装方案的详细信息[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，请参阅[在 32 位和 64 位平台上安装 BizTalk 适配器包方案](#BKMK_Install_Scenarios)。  
  
<a name="BKMK_Install_Adap"></a>   
## <a name="installing-the-biztalk-adapter-pack"></a>安装 BizTalk 适配器包  
 确保所有[软件必备项](#BKMK_Prereqs)在安装之前安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。 你可以安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]以下两种方式：  
  
-   **在交互模式中**： 运行安装程序向导  
  
-   **在静默模式下**： 使用命令行  
  
    > [!IMPORTANT]
    >  必须在其中安装的计算机上具有管理特权[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，不管是否使用安装向导或命令行。  

### <a name="typical-vs-custom-installation"></a>典型安装与自定义安装  
本部分列出的安装类型，以及每个选项安装的功能：  
  
-   **典型**和**完成**选项安装所有的适配器，请与关联的数据提供程序。 你没有选择特定的适配器的安装的选项。  
  
-   **自定义**选项与关联的数据提供程序安装一个或多个适配器。 你可以选择要安装哪些适配器。 如果你选择安装数据提供程序，你还必须安装相应的适配器。 但是，你可以安装适配器，而无需安装相应的数据提供程序。 执行此操作通过展开**ADO 提供程序**节点，，然后选择你不想要安装的提供程序。 请参阅[在交互模式中安装 BizTalk 适配器包](#BKMK_Install_wizard)。  
  
     例如，如果你安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，还必须安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]。 但是，你可以安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]而无需安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]。  
  
<a name="BKMK_Install_Scenarios"></a>   
### <a name="scenarios-for-installing-the-biztalk-adapter-pack-on-32-bit-and-64-bit-platforms"></a>在 32 位和 64 位平台上安装 BizTalk 适配器包方案  
 与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]可用于： 
  
-   [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]设计时 （在生成 LOB 应用程序上的操作的元数据）
  
-   BizTalk Server 管理控制台 （用于创建的物理端口） 的设计时
  
    > [!NOTE]
    >  BizTalk Server 管理控制台将作为 32 位 Microsoft 管理控制台 (MMC) 应用程序运行。  
  
-   BizTalk 运行时 （发送和接收消息时从 LOB 应用程序）

你可以为所有这些大小，使用一台计算机，或使用不同的计算机。 因为同时[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]和 BizTalk MMC 是 32 位进程，则必须安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]你在其中完成的设计时任务的计算机上。 

#### <a name="scenarios-for-installing-the-biztalk-adapter-pack-on-a-32-bit-platform"></a>在 32 位平台上安装 BizTalk 适配器包方案  
 在 32 位平台上支持的方案包括：  
  
|为 Visual Studio 设计时|为 BizTalk MMC 设计时|有关 BizTalk 运行时|Visual Studio 设计时间和/或 BizTalk MMC 设计时 + BizTalk 运行时|  
|---|---|---|---|  
|-安装 32 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> -安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他必要的 Dll。|-安装 32 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> -安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他必要的 Dll。|-安装 32 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> -安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他必要的 Dll。|-安装 32 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> -安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他必要的 Dll。|  
  
#### <a name="scenarios-for-installing-the-biztalk-adapter-pack-on-a-64-bit-platform"></a>在 64 位平台上安装 BizTalk 适配器包方案  
 在 64 位平台上支持的方案包括：  
  
|为 Visual Studio 设计时|为 BizTalk MMC 设计时|有关 BizTalk 运行时|Visual Studio 设计时间和/或 BizTalk MMC 设计时 + BizTalk 运行时|  
|---|---|---|---|  
|-安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> -安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他必要的 Dll。|-安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> -安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他必要的 Dll。|**对于 32 位 BizTalk 进程**:<br /><br /> -安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> -安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他必要的 Dll。<br /><br /> **对于 64 位 BizTalk 进程**:<br /><br /> -安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> -安装 64 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 64 位 LOB 客户端和其他必要的 Dll。|**对于 32 位 BizTalk 进程**:<br /><br /> -安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> -安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他必要的 Dll。<br /><br /> **对于 64 位 BizTalk 进程**:<br /><br /> -安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> -安装 64 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 64 位 LOB 客户端和其他必要的 Dll。<br /><br /> -安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他必要的 Dll。|  
  
> [!NOTE]
>  在你想要执行设计时任务的任何计算机上使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]或者 BizTalk MMC 中，则必须安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。  
  
<a name="BKMK_Install_wizard"></a>   
### <a name="installing-the-biztalk-adapter-pack-in-interactive-mode"></a>在交互模式中安装 BizTalk 适配器包  
完成以下步骤以安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]使用安装向导。  
  
1.  从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装媒体上，运行**Setup.exe**。  
  
2.  选择**安装 Microsoft BizTalk 适配器**。 在下一步的窗口中，选择**安装 Microsoft BizTalk 适配器包**或**安装 Microsoft BizTalk 适配器包 (x64)**，取决于你的平台。  
  
    > [!NOTE]
    >  如果你正在安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]上虚拟机，安装向导可能不会继续超出了通知，安装程序正在检查可用磁盘空间的对话框。 在这种情况下，我们建议你使用的无提示安装选项。 请参阅[在无提示模式下安装 BizTalk 适配器包](#BKMK_SilentInst)（本主题中）。  
  
3.  在欢迎屏幕上，选择**下一步**。  
  
4.  接受最终用户许可协议 (EULA)，然后选择**下一步**。  
  
5.  在**选择安装类型**:  
  
    -   若要安装的最常见的功能，请选择**典型**。  
  
    -   若要选择你想要安装的适配器，选择**自定义**，然后继续下一步。  
  
    -   若要安装所有功能，请选择**完成**。  
  
        > [!IMPORTANT]
        >  若要安装使用要与企业应用程序之间的接口，请选择适配器**自定义**安装。  
  
6. **所需**仅在您选择自定义安装。 如果你选择了**典型**或**完成**安装，然后跳过此步骤中，并转到步骤 7。  
  
    1.  在**自定义安装**，展开**基适配器**若要查看可用的适配器。  
  
    2.  对于你不希望的适配器，选择该适配器旁边的图标，然后选择**整个功能将不可**。  
  
    3.  展开**ADO 提供程序**，然后选择你不想要安装的提供程序。  
  
    4.  选择“下一步” 。  
  
7.  选择“安装”。  
  
8.  在**客户体验改善计划**，你可以选择注册。 如果注册后，你可以与 Microsoft 共享的下列数据：  
  
    -   与你正在其安装的计算机硬件相关的数据[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。  
  
    -   与你使用的企业应用程序版本相关的数据[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。  
  
     选择“确定”。 [CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699)提供了详细信息。  
  
    > [!NOTE]
    >  你始终可以通过在从修复模式下运行安装程序来更改此设置**程序**。  
  
9. 选择“完成”。  
  
<a name="BKMK_SilentInst"></a>   
### <a name="installing-the-biztalk-adapter-pack-in-silent-mode"></a>在无提示模式下安装 BizTalk 适配器包  
 使用**msiexec**命令以执行无提示安装。 作为 msiexec 命令的一部分，输入你想要安装的各个组件。 下表列出了每个组件值[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。 使用这些值来安装 （或删除） 特定的组件。 若要安装 （或删除） 多个组件，可以使用由逗号分隔这些值的组合。  
  
|组件名称|对应的命令行属性值|  
|---|---|  
|[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]|DbFeature|  
|[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]|OracleEBSFeature|  
|[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]|SapBaseAdapterFeature|  
|[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]|SiebelBaseAdapterFeature|  
|[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]|SqlFeature|  
|[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]|SapAdoFeature<br /><br /> **请注意**： 必须提供此值，仅当你安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]还。|  
|[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]|SiebelAdoFeature<br /><br /> **请注意**： 必须提供此值，仅当你安装[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]还。|  
|所有组件|ALL|  
  
> [!IMPORTANT]
>  功能名称是区分大小写。  
  
 以下步骤显示如何完成的无提示安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]不同组件。  
  
##### <a name="install-in-silent-mode"></a>在无提示模式下安装  
  
1.  打开命令提示符，并转到[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]根中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。  
  
2.  运行基于你想要安装的以下命令：  
  
    > [!NOTE]
    >  若要执行无提示安装在基于 x64 的平台上，将`AdaptersSetup.msi`与`AdaptersSetup64.msi`以下命令中。  
  
    -   若要执行的完整安装，安装所有适配器包括.NET Framework 数据提供程序，请键入：  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=ALL  
        ```  
  
    -   仅安装[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，类型：  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=DbFeature  
        ```  
  
    -   仅安装[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，类型：  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=OracleEBSFeature  
        ```  
  
    -   仅安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，类型：  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature  
        ```  
  
    -   若要安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]连同[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，类型：  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature  
        ```  
  
    -   仅安装[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，类型：  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature  
        ```  
  
    -   若要安装[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]连同[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]，类型：  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature,SiebelAdoFeature  
        ```  
  
    -   仅安装[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，类型：  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SqlFeature  
        ```  
  
    -   若要安装的所有基适配器，请键入：  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SiebelBaseAdapterFeature,DbFeature,OracleEBSFeature,SqlFeature  
        ```  
  
    -   若要安装两个.NET Framework 数据提供程序，请键入：  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapAdoFeature,SiebelAdoFeature  
        ```  
  
    -   任何类型的以逗号分隔各个组件的自定义安装。 例如，若要安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]与[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，和[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]类型：  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature,SiebelBaseAdapterFeature  
        ```  
  
    -   你还可以选择注册 CEIP 的无提示安装的一部分。 类型：  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn CEIP_OPTIN=true  
        ```  
  
         默认情况下该选项为 false。 
  
        > [!IMPORTANT]
        >  安装时[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在静默模式下的评估版，CEIP 的默认选项为 true。  
  
     有关 msiexec 命令类型的详细信息`msiexec`上的命令行和按`ENTER`。 或转到[http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)。
  
<a name="BKMK_PostInst"></a>   
### <a name="after-installing-the-biztalk-adapter-pack"></a>安装 BizTalk 适配器包后  
 你可能需要在安装后执行以下任务[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，将根据你想要与每个适配器执行哪些操作：  
  
-   [配置 Oracle 数据库适配器，以使用较新的 Oracle.DataAccess.dll 版本](#BKMK_ConfigNewOracleDLL)OracleDB 配置文件中。  
  
-   [（仅为 SAP 适配器中） 创建 SQL Server 数据库对象](#BKMK_CreateSQLServer)来调用中某个 SAP 系统的事务性 Rfc (tRFCs)。  
  
-   [注册的适配器绑定](#BKMK_Register_Bindings)与.NET Framework 数据提供程序安装向导时若要这样做。  
  
-   [确定的公钥和版本](#BKMK_PubKey)的其他适配器文件。  
  
-   [安装自定义 Rfc](#BKMK_InstallCustomRFC)如果你选择安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]。  
  
<a name="BKMK_ConfigNewOracleDLL"></a>   
#### <a name="configure-the-oracle-database-adapter-to-use-a-newer-oracledataaccessdll-version"></a>配置 Oracle 数据库适配器，以使用较新的 Oracle.DataAccess.dll 版本  
 当配置要使用 WCF OracleDB 适配器，或者使用 Visual Studio 使用的生成的适配器的端口时，显示一条消息，该适配器需要 Oracle.DataAccess.dll 版本 2.111.7.0。 若要解决此消息，请安装支持的 Oracle.DataAccess.dll 版本 (请参阅[支持版本列表](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx))，然后更新`bindingRedirect`OracleDB 配置文件中的元素。 步骤：  
  
1.  在 BizTalk Server 中，转到以下文件夹：  
  
     *驱动器*: files\microsoft BizTalk 适配器包 (x64) \bin  
  
     *驱动器*: \Program 文件 (x86) \Microsoft BizTalk Adapter Pack\bin  
  
2.  打开 Microsoft.Adapters.OracleDB.config 文件。  
  
3.  找到以下部分中，并复制/粘贴以下内容：  
  
    ```  
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
              <dependentAssembly>  
                        <assemblyIdentity name="Oracle.DataAccess" publicKeyToken="89b483f429c47342" culture="neutral" />  
                        <bindingRedirect oldVersion="2.111.7.00" newVersion="2.112.1.00"/>  
              </dependentAssembly>  
    </assemblyBinding>  
  
    ```  
  
    > [!NOTE]
    >  在此示例中，我们将设置*newVersion*到 2.112.1.00。 将此值设置为已安装的版本。  
  
> [!IMPORTANT]
>  -   如果此组中有多个 BizTalk 服务器，请在组中的所有 BizTalk 服务器上进行此更改。  
> -   *NewVersion*值需要更新的计算机上安装的 Oracle.DataAccess.dll 文件的版本。  Oracle.DataAccess.dll 都附带从 Oracle 安装 Oracle 客户端。  你只需安装的 Oracle 客户端版本[的 BizTalk 适配器包支持](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)。  
  
<a name="BKMK_CreateSQLServer"></a>   
#### <a name="create-sql-server-database-objects-only-for-the-sap-adapter"></a>创建 SQL Server 数据库对象 （仅适用于 SAP 适配器）  
 若要调用 tRFCs SAP 系统中，运行*SapAdapter DbScript Install.sql* SQL 脚本。 此脚本安装使用[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装，并在 SQL Server 中创建数据库对象。 该脚本通常安装在\<安装驱动器 >: files\microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。 只要在使用该适配器调用 tRFCs 时输入该数据库名称，你可以针对任何 SQL Server 数据库，运行此脚本。  
  
<a name="BKMK_Register_Bindings"></a>   
#### <a name="register-the-adapter-bindings"></a>注册的适配器绑定  
 期间[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装，安装向导可能无法注册的适配器绑定或.NET Framework 数据提供程序 mySAP Business Suite，但安装程序将继续执行适配器安装。 这可能会由于使用 Windows Communication Foundation (WCF) 安装时，问题而导致[!INCLUDE[afproductnamelong](../includes/afproductnamelong-md.md)]安装或被损坏的 machine.config 文件。  
  
完成这些步骤*仅*如果安装向导无法在 machine.config 文件中注册的适配器绑定或.NET Framework 数据提供程序。  
  
###### <a name="register-the-adapter-bindings-or-the-net-framework-data-providers"></a>注册的适配器绑定或.NET Framework 数据提供程序  
  
1.  转到计算机上的 machine.config 文件。 例如，在 32 位平台上，machine.config 位于下\<系统驱动器 >: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。  
  
2.  打开使用文本编辑器的文件。  
  
3.  注册的适配器绑定：  
  
    1.  搜索`system.serviceModel`元素，并添加其下的以下：  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
          <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
          <endpoint binding="oracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
        ```  
  
    2.  搜索`bindingElementExtensions`system.serviceModel\extensions 下的元素。  
  
    3.  查找缺失的适配器绑定。 添加以下各节下的`bindingElementExtensions`节点，具体取决于缺少的适配器绑定。 如果安装向导无法注册任何，则必须注册的所有绑定。  
  
         有关[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，添加：  
  
        ```  
        <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，添加：  
  
        ```  
        <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，添加：  
  
        ```  
        <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，添加：  
  
        ```  
        <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，添加：  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  搜索`bindingExtensions`system.serviceModel\extensions 下的元素。  
  
    5.  查找缺失的适配器绑定。 添加以下各节下的`bindingExtensions`节点，具体取决于缺少的适配器绑定。 如果安装向导无法注册任何，则必须注册的所有绑定。  
  
         有关[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，添加：  
  
        ```  
        <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，添加：  
  
        ```  
        <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，添加：  
  
        ```  
        <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，添加：  
  
        ```  
        <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS,Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，添加：  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    > [!NOTE]
    >  有关如何确定的公钥的信息，请参阅[确定的公钥和版本](#BKMK_PubKey)。  
  
4.  注册.NET Framework 数据提供程序：  
  
    1.  搜索`DbProviderFactories`system.data 节点下的元素。  
  
    2.  查找缺少的.NET Framework 数据提供程序。 添加以下各节下的`DbProviderFactories`节点，具体取决于缺少提供程序。 如果安装向导无法注册任何，则必须注册的所有提供程序。  
  
         有关[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，添加：  
  
        ```  
        <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
            description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]，添加：  
  
        ```  
        <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
            description=".NET Framework Data Provider for Siebel eBusiness Applications"  
            type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  保存并关闭 machine.config 文件。  
  
<a name="BKMK_PubKey"></a>   
#### <a name="determine-the-public-key-and-version"></a>确定的公钥和版本  
 完成以下步骤以确定公钥和适配器或.NET Framework 数据提供程序的版本。  
  
###### <a name="determine-the-public-key"></a>确定的公钥  
  
1.  请转到 Windows 目录中，通常 C:\WINDOWS\assembly。  
  
2.  右键单击该 DLL 为其您希望将公钥，，然后选择**属性**。 下表列出的每个适配器和提供程序 Dll 的名称：  
  
    |适配器/.NET Framework 数据提供程序|DLL 的名称|  
    |---|---|  
    |[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]|Microsoft.Adapters.SAP|  
    |[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]|Microsoft.Adapters.Siebel|  
    |[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]|Microsoft.Adapters.OracleDB|  
    |[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]|Microsoft.Adapters.OracleEBS|  
    |[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]|Microsoft.Adapters.Sql.dll|  
    |[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]|Microsoft.Data.SAPClient|  
    |[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]|Microsoft.Data.SiebelClient|  
  
3.  上**常规**选项卡上， **Public Key Token**值是 DLL 的公共密钥。 **版本**值是 DLL 的版本号。  
  
4.  复制公钥，，然后选择**取消**。  
  
<a name="BKMK_InstallCustomRFC"></a>   
#### <a name="install-the-custom-rfcs"></a>安装自定义的 Rfc  
 只需执行此任务，如果你想要使用[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]。 有关安装自定义的 Rfc 的说明，请参阅[安装自定义 Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)中[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]文档。 
  
> [!IMPORTANT]
>  如果您将早期版本的自定义的 Rfc 随附[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，然后必须将它们升级到此版本中提供了 Rfc。 通过删除早期的 Rfc 中，执行此操作，然后安装了 Rfc 附带此版本。  

## <a name="installing-the-enterprise-applications"></a>安装企业应用程序  
有关步骤和指南来安装不同企业 LOB 系统，我们使用其特定安装 recommendnd 指导。 如果任何还引用特定的配置更改，及其适配器文档。   

## <a name="installation-and-post-installation-checklist"></a>安装和安装后的清单  
  
-   请确保安装所有[软件必备项](#BKMK_Prereqs)使用正确的安装选项。
  
-   请确保企业的 LOB 应用程序安装在计算机上安装受支持的版本[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。  
  
-   若要安装仅适用于企业你想要连接的 LOB 系统的适配器，请确保你安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]使用**自定义**安装选项。 请确保你安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]使用**完成**安装选项。 请参阅[安装 BizTalk 适配器包](#BKMK_Install_Adap)。  
  
-   如果你想要对 SAP 系统使用 tRFC 调用[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，请确保 SQL Server 数据库中创建所需的表。 请参阅[安装 BizTalk 适配器包后](#BKMK_PostInst)。
  
-   在运行时[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装向导中，你可能会收到一个表明安装程序无法注册绑定的错误消息。 如果是这样，则手动注册它们。 请参阅[安装 BizTalk 适配器包后](#BKMK_PostInst)。  
  
-   如果你选择安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]作为的一部分[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装，请确保在 SAP 系统上安装了自定义的 Rfc。 请参阅[安装 BizTalk 适配器包后](#BKMK_PostInst)。  
  
<a name="BKMK_Modify_Adap"></a>   
## <a name="change-the-biztalk-adapter-pack-installation"></a>更改 BizTalk 适配器包安装  
 完成以下步骤以更改[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装。 请确保你具有[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]安装之前您运行安装向导以修改[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装。  
  
 你可以修改[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装在交互模式下 （安装程序向导），或在静默模式下 （命令行）。
  
#### <a name="change-the-bap-installation-in-interactive-mode"></a>更改 BAP 安装在交互模式中  
  
1.  使用 BizTalk Server Administrators 组的成员的帐户登录。  
  
2.  在**程序和功能**，选择**卸载程序**。  
  
3.  右键单击**Microsoft BizTalk 适配器包**，然后选择**更改**。  
  
4.  在欢迎屏幕上，选择**下一步**。  
  
5.  在**更改、 修复或删除安装**:  
  
    -   若要选择你想要安装的组件，选择**更改**并转到步骤 6。  
  
    -   若要修复最新安装中的错误，选择**修复**并转到步骤 7。  
  
    -   若要删除 Microsoft[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]从计算机上，选择**删除**，然后转到步骤 10。  
  
6.  如果你选择要修改安装：  
  
    -   展开**Microsoft BizTalk 适配器包**节点，以选择要安装的基的适配器和 / 或.NET Framework 数据提供程序。  
  
    -   展开**基适配器**节点，以选择安装所有适配器或特定的适配器。  
  
    -   展开**ADO 提供程序**节点，以选择安装所有提供程序或特定的提供程序安装。  
  
    -   选择“下一步” 。  
  
    -   选择**更改**，然后选择**完成**。  
  
7.  如果你选择在修复安装，**准备好修复 Microsoft BizTalk 适配器包**对话框中，选择**修复**。 启动向导，修复安装。  
  
8.  如果需要，更改你的首选项有关选择加入的 CEIP，，然后选择**确定**。 
  
9. 选择“完成”。  
  
10. 如果您选择中删除适配器，**准备好删除 Microsoft BizTalk 适配器包**对话框中，选择**删除**，然后选择**完成**。  
  
#### <a name="change-the-bap-installation-in-silent-mode"></a>更改在静默模式下 BAP 安装  
  
1.  打开命令提示符，并转到根目录下的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装程序。  
  
2.  运行如下命令：  
  
    > [!NOTE]
    >  若要修改[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在基于 x64 的平台上，在以下命令，以无提示模式安装替换`AdaptersSetup.msi`与`AdaptersSetup64.msi`。  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature ADDLOCAL=SapBaseAdapterFeature  
    ```  
  
     此命令删除[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，并安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]。  
  
     通过使用不同的值`REMOVE`和`ADDLOCAL`属性，可以添加或删除特定的组件。 中的表是指[在无提示模式下安装 BizTalk 适配器包](#BKMK_SilentInst)（本主题中） 中有关你可以使用这些属性的值。  
  
     你还可以通过为 msiexec 命令的一部分使用 /f 选项来执行无提示的修复。 例如：  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn /f  
    ```  
  
     带 /f 选项，可以使用各种不同的组合。 有关 msiexec 命令类型的详细信息`msiexec`上的命令行和按`ENTER`。 或转到[http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)。  
  
    > [!IMPORTANT]
    >  修改时[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在静默模式下的安装，不能更改用于选择加入或退出 CEIP 首选项。 在过程中选择该安装将保持，即使你显式设置为 true 或 false 的 CEIP_OPTIN 首选项。  
  
<a name="BKMK_Remove_Adap"></a>   
## <a name="removing-the-biztalk-adapter-pack"></a>删除 BizTalk 适配器包  
  
> [!IMPORTANT]
>  如果你在要使用的 tRFC 功能的 SQL Server 数据库中创建表[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，你必须手动删除之前删除它们[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装将 SapAdapter DbScript Uninstall.sql 文件通常情况下的复制\<安装驱动器 >: files\microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。 运行此文件，以删除你创建的表。  
  
完成以下步骤以删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]从您的计算机。 请确保你具有[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]安装之前您运行安装向导以删除适配器。  
  
 你可以删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在交互模式 （安装程序向导） 中或在静默模式下 （命令行）。
  
#### <a name="uninstall-the-biztalk-adapter-pack-in-interactive-mode"></a>卸载在交互模式中的 BizTalk 适配器包  
  
1.  在**程序和功能**，选择**卸载程序**。  
  
2.  右键单击**Microsoft BizTalk 适配器包**，然后选择**卸载**。  
  
#### <a name="uninstall-the-biztalk-adapter-pack-in-silent-mode"></a>卸载在静默模式下 BizTalk 适配器包  
  
1.  打开命令提示符，并转到根目录下的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装程序。  
  
2.  运行以下命令：  
  
    > [!NOTE]
    >  若要删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在静默模式下，在基于 x64 的平台上，在以下命令，将`AdaptersSetup.msi`与`AdaptersSetup64.msi`。  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature  
    ```  
  
     此命令删除[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]从[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装。  
  
     通过提供不同的值`REMOVE`属性，您可以删除从特定组件[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装。 中的表是指[在无提示模式下安装 BizTalk 适配器包](#BKMK_SilentInst)（本主题中） 中有关你可以使用此属性的值。  
  
     若要完全删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，执行以下命令：  
  
    ```  
    msiexec /x AdaptersSetup.msi /qn  
    ```  
  
     有关 msiexec 命令类型的详细信息`msiexec`上的命令行和按`ENTER`。 或转到[http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)。
  
<a name="BKMK_PostRemove"></a>   
### <a name="after-removing-the-biztalk-adapter-pack"></a>删除 BizTalk 适配器包后  
 你可能需要删除后执行以下步骤[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]:  
  
-   删除适配器绑定或.NET Framework 数据提供程序在注册时，如果安装向导未能完成此操作
  
-   删除自定义的 Rfc 中，如果你选择安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]
  
<a name="BKMK_Remove_Binding"></a>   
#### <a name="remove-the-bindings-or-the-net-framework-data-provider-registration"></a>删除绑定或.NET Framework 数据提供程序注册  
 完成这些步骤*仅*如果安装向导无法从 machine.config 文件中删除适配器绑定或.NET Framework 数据提供程序注册。  
  
###### <a name="remove-the-adapter-bindings-or-net-framework-data-provider-registration"></a>删除适配器绑定或.NET Framework 数据提供程序注册  
  
1.  转到计算机上的 machine.config 文件。 例如，在 32 位平台上，machine.config 位于下\<系统驱动器 >: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。  
  
2.  打开使用文本编辑器的文件。  
  
3.  删除适配器绑定注册：  
  
    1.  搜索`system.serviceModel`元素，并删除以下从元素：  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
          <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
          <endpoint binding="OracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
  
        ```  
  
    2.  搜索`bindingElementExtensions`system.serviceModel\extensions 下的元素。  
  
    3.  删除以下各节下的`bindingElementExtensions`节点，具体取决于可用的适配器绑定。 如果安装向导删除任何失败，则必须删除所有绑定。  
  
         有关[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，删除：  
  
        ```  
        <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，删除：  
  
        ```  
        <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，删除：  
  
        ```  
        <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，删除：  
  
        ```  
        <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，删除：  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  搜索`bindingExtensions`system.serviceModel\extensions 下的元素。  
  
    5.  删除以下各节下的`bindingExtensions`节点，具体取决于可用的适配器绑定。 如果安装向导删除任何失败，则必须删除所有绑定。  
  
         有关[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，删除：  
  
        ```  
        <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，删除：  
  
        ```  
        <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，删除：  
  
        ```  
        <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，删除：  
  
        ```  
        <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，删除：  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
4.  删除.NET Framework 数据提供程序注册：  
  
    -   搜索`DbProviderFactories`system.data 节点下的元素。  
  
    -   查找仍有注册.NET Framework 数据提供程序。 删除以下各节下的`DbProviderFactories`节点，具体取决于现有的.NET Framework 数据提供程序。 如果它们存在，则必须删除所有提供程序。  
  
         有关[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，删除：  
  
        ```  
        <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
            description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         有关[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]，删除：  
  
        ```  
        <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
            description=".NET Framework Data Provider for Siebel eBusiness Applications"  
            type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  保存并关闭 machine.config 文件。  
  
<a name="BKMK_Remove_SAP_Pro"></a>   
#### <a name="remove-the-custom-rfcs"></a>删除自定义的 Rfc  
完成此步骤以删除 SAP 系统中安装了自定义 Rfc。 请参阅[安装或删除自定义的 Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。  
  
## <a name="troubleshoot-biztalk-adapter-pack-installation"></a>BizTalk 适配器包安装进行故障排除  
 以下是在安装时，你可能面临一些问题[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。 有关安装相关的问题的完整列表，请参阅**疑难解答**为每个适配器的主题。  
  
-   **在 64 位计算机上的运行安装程序可能会访问架构文件时将引发错误**  
  
     [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装程序在访问时引发错误 **Microsoft.Adapters。*\<AdapterName >*_schema.xml** 文件，但与适配器安装继续进行。  
  
     **可能的原因**  
  
     如果 32 位和 64 位版本的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装在同一计算机上使用两个目标架构文件是相同。 因此，该文件安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]可能正在使用 IIS 时 64 位安装程序会尝试访问它。  
  
     **解决方法**  
  
     手动复制 **Microsoft.Adapters。*\<AdapterName >*_schema.xml** 文件从`C:\Program Files\Microsoft BizTalk Adapter Pack(x64)\IIS Schemas`"到`C:\Windows\System32\inetsrv\config\schema`。  