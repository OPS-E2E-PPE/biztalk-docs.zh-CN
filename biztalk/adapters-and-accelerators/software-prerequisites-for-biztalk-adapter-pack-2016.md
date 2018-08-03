---
title: BizTalk 适配器包 2016年的软件必备组件 |Microsoft Docs
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
ms.openlocfilehash: 2832333e7c38b824fb26f988ec01423e519a83d4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973270"
---
# <a name="software-prerequisites-for-biztalk-adapter-pack-2016"></a>BizTalk 适配器包 2016年的必备软件
列出了 Microsoft 的软件要求[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)](BAP) 中包含[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。

[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]可以从使用：  

- .NET 应用程序  

- Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  

- ADO 接口  

- Microsoft SharePoint 门户网站  

  根据如何使用适配器，所需的软件各不相同。  

## <a name="prerequisites-when-using-a-net-application"></a>使用.NET 应用程序时的先决条件  
当使用.NET 应用程序以使用适配器，在开发计算机 （要在其中创建.NET 应用程序的计算机） 上需要以下软件。 按所列顺序安装软件。


|                                                   BizTalk 适配器包 2016                                                    |
|--------------------------------------------------------------------------------------------------------------------------------|
|         <ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1  </li></ul>          |
|                                                     .NET Framework 4.6.*x*                                                     |
|                                                       Visual Studio 2015                                                       |
|                              [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]                              |
| 企业应用程序客户端和关联的软件。 请参阅**受支持的企业应用程序版本**（在本主题中）。 |

## <a name="prerequisites-when-using-biztalk-server"></a>使用 BizTalk Server 时的先决条件  
使用时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要使用的适配器，以下软件需要对你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 按所列顺序安装软件。


|                                                                                                                                                                                                                                              BizTalk 适配器包 2016                                                                                                                                                                                                                                               |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                                                                                                                    <ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1  </li></ul>                                                                                                                                                                                                     |
|                                                                                                                                                                                                                                                .NET Framework 4.6.*x*                                                                                                                                                                                                                                                |
|                                                                                                                                                                                                                                                  Visual Studio 2015                                                                                                                                                                                                                                                  |
| [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]<br /><br /> 安装[!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)]有关[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]附带[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。 若要安装，请执行**自定义**(选择**BizTalk Server 外接程序**) 或**完成**安装[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。 |
|                                                                                                                                                                                                                                  [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]                                                                                                                                                                                                                                   |
|                                                                                                                                                                                            企业应用程序客户端和关联的软件。 请参阅**受支持的企业应用程序版本**（在本主题中）。                                                                                                                                                                                            |

## <a name="prerequisites-when-using-ado"></a>使用 ADO 时的先决条件  
 **[!INCLUDE[adaptersap](../includes/adaptersap-md.md)]** 并**[!INCLUDE[adaptersiebel](../includes/adaptersiebel-md.md)]** 包括 ADO 层 (*[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]* 和*[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]*)，可以用于编写 ADO.NET 客户端连接到 SAP 系统或 Siebel 系统。 您可以还使用 ADO 层与 SQL Server Integration Services (SSIS) 导入和导出数据从 LOB 应用程序和 SQL Server Reporting Services (SSRS) 以生成报表以显示来自 LOB 系统的数据。  

> [!NOTE]
>  与 SSRS 使用 ADO 提供程序仅支持[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]。  

使用计算机上需要以下软件[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]与 ADO 接口。 按所列顺序安装软件。  


|                                                   BizTalk 适配器包 2016                                                    |
|--------------------------------------------------------------------------------------------------------------------------------|
|         <ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1  </li></ul>          |
|                                                     .NET Framework 4.6.*x*                                                     |
|                                                       Visual Studio 2015                                                       |
|                              [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]                              |
|                       <ul><li>Microsoft SQL Server 2016</li><li>Microsoft SQL Server 2014 SP1</li></ul>                        |
| 企业应用程序客户端和关联的软件。 请参阅**受支持的企业应用程序版本**（在本主题中）。 |

## <a name="prerequisites-when-using-sharepoint"></a>使用 SharePoint 时的先决条件  
使用与 Microsoft SharePoint 适配器的目标是在 SharePoint 门户网站上显示的 LOB 应用程序中的数据。  

使用典型设置[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]和 SharePoint 可以使用一台计算机或为不同任务使用不同的计算机。 下表列出了每台计算机的必备软件。 如果使用一台计算机，则必须在该计算机上安装所有软件。 按所列顺序安装软件。  


|                                                                                                                                                                                                                                             运行 WCF 适配器服务开发向导计算机                                                                                                                                                                                                                                              |                                                                                                                                                                                                                                                                                                                                                  你在其中托管 WCF 服务的计算机                                                                                                                                                                                                                                                                                                                                                   | 计算机在其中使用 SharePoint Designer 来定义外部内容类型 |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| <ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1</li><br/><br/><li>.NET Framework 4.6.<em>x</em></li><br/><br/><li>Visual Studio 2015</li><br/><br/><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><br/><br/><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><br/><br/><li>企业应用程序客户端和关联的软件。 请参阅<strong>受支持的企业应用程序版本</strong>（在本主题中）。</li></ul> | <ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1</li><br/><br/><li>.NET Framework 4.6.<em>x</em></li><br/><br/><li>Visual Studio 2015</li><br/><br/><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><br/><br/><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><br/><br/><li>企业应用程序客户端和关联的软件。 请参阅<strong>受支持的企业应用程序版本</strong>（在本主题中）。</li><br /><br /><li>附带了操作系统的 Internet 信息服务 (IIS) 版本。 [KB 224609](https://support.microsoft.com/kb/224609)列出的版本。</li> </ul> |                   Microsoft SharePoint 软件开发工具包 (SDK)                    |

<a name="BKMK_SuppLOB"></a>   
## <a name="supported-enterprise-application-versions"></a>受支持的企业应用程序版本  
若要查看特定的 LOB 系统版本的 BizTalk 适配器包支持，请参阅**[支持的业务线 (LOB) 系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx)**。

本部分列出了每个适配器，任何额外信息，如 Dll 的任何客户端所需的每个适配器。  

### <a name="oracle-database-adapter"></a>Oracle 数据库适配器  

-   可选： 如果使用 Oracle 数据库使用分布式的事务，安装**Oracle 服务的 Microsoft Transaction Server** （Oracle 客户端安装的一部分） 的计算机上运行适配器客户端。  

-   对于应用程序可以使用 ODP.NET 的最新版本，安装**策略 Dll**和在 GAC 中注册 Dll。 请参阅[Oracle 数据提供程序的.NET 常见问题解答](http://www.oracle.com/technetwork/database/windows/faq-093106.html)。  

### <a name="oracle-e-business-adapter"></a>Oracle E-business 适配器  

-   可选： 若要使用 Oracle 数据库的分布式的事务，安装**Oracle 服务的 Microsoft Transaction Server** （Oracle 客户端安装的一部分） 的计算机上运行适配器客户端。  

-   对于应用程序可以使用 ODP.NET 的最新版本，安装**策略 Dll**和在 GAC 中注册 Dll。 请参阅[Oracle 数据提供程序的.NET 常见问题解答](http://www.oracle.com/technetwork/database/windows/faq-093106.html)。  

### <a name="sap-adapter"></a>SAP 适配器  

- [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]需要 Unicode 版本而不考虑 SAP 系统是否是 Unicode 或非 Unicode 的 RFC SDK。  

- **所需的驱动程序**： 下表列出了所需的 Dll[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]与 SAP 系统进行交互：  


  | SAP 客户端版本 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  必需的驱动程序                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
  |--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  |        7.2         | - **SAP RFC SDK 7.10 UNICODE**。 这是可作为一部分 SNOTE<sup> * </sup> 27517。若要下载 SDK 的说明[ http://go.microsoft.com/fwlink/?LinkId=94691 ](http://go.microsoft.com/fwlink/?LinkId=94691)。下载并解压缩 SDK 后，将所有 Dll 从 \rfcsdk\bin 和 \rfcsdk\lib 文件夹都复制到此表前面提到的相关位置。<br /> <br /> -Dll 的形式提供来自 SAP 的一部分\* \*R3DLLINST.zip*<em>。 该文件包含 Microsoft 运行时 Dll 并可以从 SAP 网站上下载。 请参阅 SNOTE<sup> </em> </sup> 684106 有关详细信息。 可以下载.zip 文件[ http://go.microsoft.com/fwlink/?LinkId=94693 ](http://go.microsoft.com/fwlink/?LinkId=94693)。 此链接都有可以在哪里下载包上的"附件"选项。<br /><br /> Microsoft Visual c + + 运行时 Dll 所需的 SAP 7.1 客户端是可从以下链接：<br /><br /> - **对于 32 位 SAP 7.1 客户端**： 从 Vcredist_x86.exe [ http://go.microsoft.com/fwlink/?LinkId=107086 ](http://go.microsoft.com/fwlink/?LinkId=107086)。<br /><br /> -                                 **对于 64 位 SAP 7.1 客户端**： 从 Vcredist_x64.exe [ http://go.microsoft.com/fwlink/?LinkId=107087 ](http://go.microsoft.com/fwlink/?LinkId=107087)。<br /><br /> -如果使用 SAP 安全网络通信 (SNC) 连接到 SAP 系统，您还必须从 SAP 相关的 Dll。 这些 Dll 是不同的 32 位和 64 位平台和适用于 SNOTE<sup> * </sup> 352295。您可以下载从 Dll [ http://go.microsoft.com/fwlink/?LinkId=104032 ](http://go.microsoft.com/fwlink/?LinkId=104032)。此链接都有可以在哪里下载包上的"附件"选项。Dll 的名称为：<br /><br /> - \*\*为 32 位*<em>: gsskrb5.dll、 gssntlm.dll<br /><br /> - \*\*针对 64 位 x86</em>\*: gx64krb5.dll、 gx64ntlm.dll |

   > [!TIP]
   > SNOTEs 是附带由 SAP 发布的修补程序的发行说明。  

  必须从 SAP Service Marketplace 下载大部分包含这些 Dll 的包。 若要获取从 SAP Service Marketplace 下载： 

  1. 从 SAP Service Marketplace 安装 Download Manager 可用。  

  2. 配置通过你的凭据用于 SAP Service Marketplace 下载管理器。  

  3. 授权由你的组织中的 SAP 管理员从 SAP 服务网站上下载软件。 这是必需的因为对 SAP 软件分发中心访问受限制的下载软件授权对象。 这可确保只能由授权用户下载的软件。  

  4. 安装 SAPCAR 程序，需从 SAP Service Marketplace 下载的包中提取文件。 SAP Service Marketplace 也是 SAPCAR。  

     32 位和 64 位版本的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，必须具有相应的 32 位和 64 位版本的这些 Dll。  

  -   32 位计算机上，必须将 Dll 的 32 位版本添加到 C:\Windows\System32 文件夹。  

  -   64 位计算机上，必须将 Dll 的 32 位版本添加到 C:\Windows\SysWow64 文件夹。 必须将 Dll 的 64 位版本添加到 C:\Windows\System32 文件夹中。  


### <a name="siebel-adapter"></a>Siebel 适配器  
没有额外的步骤。

### <a name="sql-adapter"></a>SQL 适配器  

**所需的驱动程序**适用于 SQL Server 2014:  

-   如果使用 Udt 附带的 SQL Server 版本，例如，地理位置，请确保以下 Dll 计算机上存在其中使用该适配器在 SQL Server 上执行操作。 例如，如果在 BizTalk 项目，在 SQL Server 上执行操作，这些 Dll 必须在运行 BizTalk Server 的计算机上存在。  

    -   请确保 Microsoft.SqlServer.Types.dll 添加到 GAC。  

    -   确保 SqlServerSpatial.dll System32 文件夹中可用。    

    可以通过运行 SQL Server 安装程序并选择在计算机上安装这些 Dll**管理工具-Basic**并**管理工具-完整**中**功能选择**向导页。          

-   如果使用适配器来执行对 FILESTREAM 数据类型的列的操作，请确保已安装的 SQL 客户端连接 SDK。 可以通过运行 SQL Server 安装程序并选择安装 SQL 客户端连接 SDK **SQL 客户端连接 SDK**中**功能选择**向导页。 适配器使用 sqlncli10.dll，随 SQL 客户端连接 SDK，用于执行 FILESTREAM 操作。  

-   如果在 SQL Server 中创建你自己的 Udt，请确保对 Udt 的相应程序集添加到 GAC。

## <a name="64-bit-host-instance-support"></a>64 位主机实例支持

Siebel 适配器支持在 32 位主机实例中。 不支持在 64 位主机实例中运行的 Siebel 适配器。 

所有其他适配器可以运行的 32 位或 64 位主机实例中。 

 有关用于安装 32 位和 64 位支持的安装方案详细信息[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，请参阅**32 位和 64 位安装方案**处[安装 BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)。  

## <a name="next-step"></a>下一步
[安装 BizTalk 适配器包](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)  
