---
title: BizTalk 适配器包 2016年软件必备组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65a063ca-37ae-420b-9d48-e6730caf17e3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0b33203d1e8e5b36c9fb8a54167c111a427b244
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22227117"
---
# <a name="software-prerequisites-for-biztalk-adapter-pack-2016"></a>BizTalk 适配器包 2016 软件必备项
列出了 Microsoft 的软件要求[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)](BAP) 中包含[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。
  
[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]可以从使用：  
  
-   .NET 应用程序  
  
-   Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   ADO 接口  
  
-   Microsoft SharePoint 门户网站  
  
 所需的软件基于如何使用适配器，而异。  
  
## <a name="prerequisites-when-using-a-net-application"></a>使用.NET 应用程序时的先决条件  
当使用.NET 应用程序使用的适配器，你的开发计算机 （你要在其中创建.NET 应用程序的计算机） 上需要以下软件。 按列出的顺序安装软件。
  
|BizTalk 适配器包 2016|
|---|
|<ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1  </li></ul>|
|.NET Framework 4.6.*x*|
|Visual Studio 2015|
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|
|企业应用程序客户端和关联的软件。 请参阅**受支持的企业应用程序版本**（本主题中）。|

## <a name="prerequisites-when-using-biztalk-server"></a>使用 BizTalk Server 时的先决条件  
使用时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要使用的适配器，以下软件上需要你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 按列出的顺序安装软件。
 
|BizTalk 适配器包 2016|
|---|
|<ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1  </li></ul>|
|.NET Framework 4.6.*x*|
|Visual Studio 2015|
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]<br /><br /> 安装[!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)]为[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]附带[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。 若要安装，请执行**自定义**(选择**BizTalk Server 外接程序**) 或**完成**安装[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。|
|[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]|
|企业应用程序客户端和关联的软件。 请参阅**受支持的企业应用程序版本**（本主题中）。|

## <a name="prerequisites-when-using-ado"></a>使用 ADO 时的先决条件  
  **[!INCLUDE[adaptersap](../includes/adaptersap-md.md)]** 和 **[!INCLUDE[adaptersiebel](../includes/adaptersiebel-md.md)]** 包括 ADO 层 ( *[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]* 和 *[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]* )，可以要用于写入的 ADO.NET 客户端可以连接到 SAP 系统或 Siebel 系统。 你还可用于 ADO 层与 SQL Server Integration Services (SSIS) 导入和导出数据从 LOB 应用程序和 SQL Server Reporting Services (SSRS) 生成报表来显示 LOB 系统中的数据。  
  
> [!NOTE]
>  使用 SSRS ADO 提供程序仅支持[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]。  
  
使用的计算机上需要以下软件[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]ADO 界面。 按列出的顺序安装软件。  

|BizTalk 适配器包 2016|
|---|
|<ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1  </li></ul>|
|.NET Framework 4.6.*x*|
|Visual Studio 2015|
|[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]|
|<ul><li>Microsoft SQL Server 2016</li><li>Microsoft SQL Server 2014 SP1</li></ul> |
|企业应用程序客户端和关联的软件。 请参阅**受支持的企业应用程序版本**（本主题中）。|

## <a name="prerequisites-when-using-sharepoint"></a>使用 SharePoint 时的先决条件  
使用与 Microsoft SharePoint 的适配器的目标是在 SharePoint 门户网站上显示的 LOB 应用程序中的数据。  
  
使用典型安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]和 SharePoint 可以使用一台计算机，或为不同任务使用不同的计算机。 下表列出每台计算机的软件必备项。 如果你使用的一台计算机，则必须在该计算机上安装所有软件。 按列出的顺序安装软件。  
  
|运行 WCF 适配器服务开发向导的位置的计算机|其中承载 WCF 服务的计算机|其中你可以使用 SharePoint 设计器来定义外部内容类型的计算机| 
|---|---|---|  
|<ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1</li><br/><br/><li>.NET Framework 4.6.*x*</li><br/><br/><li>Visual Studio 2015</li><br/><br/><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><br/><br/><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><br/><br/><li>企业应用程序客户端和关联的软件。 请参阅**受支持的企业应用程序版本**（本主题中）。</li></ul> | <ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1</li><br/><br/><li>.NET Framework 4.6.*x*</li><br/><br/><li>Visual Studio 2015</li><br/><br/><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><br/><br/><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><br/><br/><li>企业应用程序客户端和关联的软件。 请参阅**受支持的企业应用程序版本**（本主题中）。</li><br /><br /><li>附带了操作系统的 Internet 信息服务 (IIS) 版本。 [KB 224609](https://support.microsoft.com/kb/224609)列出的版本。</li> </ul>| Microsoft SharePoint 软件开发工具包 (SDK)|
  
<a name="BKMK_SuppLOB"></a>   
## <a name="supported-enterprise-application-versions"></a>支持的企业应用程序版本  
若要查看 BizTalk 适配器包支持的特定 LOB 系统版本，请参阅**[支持的业务线 (LOB) 系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx)**。

本部分列出每个适配器，任何额外的信息，如任何客户端 Dll 所需的每个适配器。  
  
### <a name="oracle-database-adapter"></a>Oracle 数据库适配器  
  
-   可选： 如果你使用 Oracle 数据库的分布式的事务，安装**Microsoft Transaction Server 的 Oracle 服务**（Oracle 客户端安装的一部分） 的计算机上运行适配器客户端。  
  
-   对于你应用程序以使用 ODP.NET 的最新版本，安装**策略 Dll**并在 GAC 中注册 Dll。 请参阅[Oracle 数据提供程序.NET 常见问题](http://www.oracle.com/technetwork/database/windows/faq-093106.html)。  

### <a name="oracle-e-business-adapter"></a>Oracle E-business 适配器  
  
-   可选： 若要使用 Oracle 数据库的分布式的事务，安装**Microsoft Transaction Server 的 Oracle 服务**（Oracle 客户端安装的一部分） 的计算机上运行适配器客户端。  
  
-   对于你应用程序以使用 ODP.NET 的最新版本，安装**策略 Dll**并在 GAC 中注册 Dll。 请参阅[Oracle 数据提供程序.NET 常见问题](http://www.oracle.com/technetwork/database/windows/faq-093106.html)。  
  
### <a name="sap-adapter"></a>SAP 适配器  
  
-   [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]需要而不考虑 SAP 系统是 Unicode 或非 Unicode 的 RFC sdk 的 Unicode 版本。  
  
-   **所需驱动程序**： 下表列出了所需的 Dll[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]以便与 SAP 系统：  
  
    |SAP 客户端版本|必需的驱动程序|  
    |---|---|  
    |7.2|- **SAP RFC SDK 7.10 UNICODE**。 这是可用的 SNOTE 一部分<sup>* </sup> 27517。若要下载 SDK 的说明进行操作都在[http://go.microsoft.com/fwlink/?LinkId=94691](http://go.microsoft.com/fwlink/?LinkId=94691)。你已下载并提取 SDK 后，将所有 Dll 从 \rfcsdk\bin 和 \rfcsdk\lib 文件夹都复制到前面此表的相关位置提到。<br /> <br /> -Dll 均可用从 SAP 作为的一部分**R3DLLINST.zip**。该文件包含 Microsoft 运行时 Dll 并可以从 SAP 站点下载。请参阅 SNOTE<sup> * </sup> 684106 有关详细信息。 你可以下载的.zip 文件[http://go.microsoft.com/fwlink/?LinkId=94693](http://go.microsoft.com/fwlink/?LinkId=94693)。 此链接已从你可以在其中下载包"附件"选项。<br /><br /> Microsoft Visual c + + 运行时 Dll 所需的 SAP 7.1 客户端是可从以下链接：<br /><br /> - **32 位 SAP 7.1 客户端**： 从 Vcredist_x86.exe [http://go.microsoft.com/fwlink/?LinkId=107086](http://go.microsoft.com/fwlink/?LinkId=107086)。<br /><br /> -                                 **64 位 SAP 7.1 客户端**： 从 Vcredist_x64.exe [http://go.microsoft.com/fwlink/?LinkId=107087](http://go.microsoft.com/fwlink/?LinkId=107087)。<br /><br /> -如果你使用 SAP 安全网络通信 (SNC) 连接到 SAP 系统，你还必须从 SAP 相关的 Dll。 这些 Dll 是不同的 32 位和 64 位平台且可提供与 SNOTE<sup> * </sup> 352295。 你可以下载从 Dll [http://go.microsoft.com/fwlink/?LinkId=104032](http://go.microsoft.com/fwlink/?LinkId=104032)。 此链接已从你可以在其中下载包"附件"选项。 Dll 的名称为：<br /><br /> - **适用于 32 位**: gsskrb5.dll、 gssntlm.dll<br /><br /> - **为 64 位 x86**: gx64krb5.dll、 gx64ntlm.dll|  
  
     > [!TIP]
     > SNOTEs 是伴随发布 sap 修复程序的发行说明。  

    必须从 SAP 服务应用商店下载的包，包含这些 Dll 的大多数。 若要从 SAP 服务应用商店获取下载： 
  
    1.  从 SAP 服务应用商店安装下载管理器可用。  
  
    2.  通过使用你的凭据适用于 SAP 服务 Marketplace 配置下载管理器。  
  
    3.  有权通过你组织中的 SAP 管理员从 SAP 服务网站下载软件。 这是必需的因为对 SAP 软件分发中心的访问权限受到下载软件授权对象。 这可确保，只能由授权用户下载软件。  
  
    4.  安装 SAPCAR 程序，需从 SAP 服务应用商店下载的包中提取文件。 SAP 服务 Marketplace 也是 SAPCAR。  
  
     32 位和 64 位版本的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，必须具有相应的 32 位和 64 位版本的这些 Dll。  
  
    -   在 32 位计算机上，必须将 Dll 的 32 位版本添加到 C:\Windows\System32 文件夹。  
  
    -   在 64 位计算机上，必须将 Dll 的 32 位版本添加到 C:\Windows\SysWow64 文件夹。 Dll 的 64 位版本必须添加到 C:\Windows\System32 文件夹中。  
    
    
### <a name="siebel-adapter"></a>Siebel 适配器  
任何额外的步骤。
  
### <a name="sql-adapter"></a>SQL 适配器  
  
**所需驱动程序**SQL Server 2014:  
  
-   如果你使用随 SQL Server 版本，例如，Geography，Udt 请确保以下 Dll 计算机上存在其中你使用该适配器在 SQL Server 上执行操作。 例如，如果你创建 BizTalk 项目，在 SQL Server 上执行操作，这些 Dll 必须存在于运行 BizTalk Server 的计算机上。  
  
    -   请确保 Microsoft.SqlServer.Types.dll 已添加到 GAC。  
  
    -   确保 SqlServerSpatial.dll System32 文件夹中可用。    
        
    可以通过运行 SQL Server 安装程序并选择在计算机上安装这些 Dll**管理工具-基本**和**管理工具 – 完整**中**功能选择**向导页。          
  
-   如果你使用该适配器上的 FILESTREAM 数据类型的列执行操作，请确保已安装的 SQL 客户端连接 SDK。 你可以通过运行 SQL Server 安装程序并选择安装 SQL 客户端连接 SDK **SQL 客户端连接 SDK**中**功能选择**向导页。 适配器使用 sqlncli10.dll，安装 SQL 客户端连接 SDK，与执行 FILESTREAM 操作。  

-   如果在 SQL Server 中创建你自己的 Udt，请确保 Udt 的相应程序集添加到 GAC。

## <a name="64-bit-host-instance-support"></a>64 位主机实例支持

Siebel 适配器被支持在 32 位主机实例中。 它不被支持的 64 位主机实例中运行 Siebel 适配器。 

所有其他适配器可以在一个 32 位或 64 位主机实例中运行。 
  
 有关安装的 32 位和 64 位的受支持的安装方案的详细信息[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，请参阅**32 位和 64 位安装方案**在[安装 BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)。  
 
## <a name="next-step"></a>下一步
[安装 BizTalk 适配器包](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)  
