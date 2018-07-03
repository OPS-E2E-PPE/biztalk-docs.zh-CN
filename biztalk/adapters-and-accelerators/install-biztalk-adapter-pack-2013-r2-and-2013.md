---
title: 安装 BizTalk 适配器包 2013 R2 和 2013年 |Microsoft Docs
description: 先决条件和安装 BAP 2013 R2 和 BizTalk Server 附带的 BAP 2013 的步骤
ms.custom: ''
ms.date: 2015-12-09
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9980953a-8d38-476f-af38-4f4214ba61f2
caps.latest.revision: 107
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac127e569603e77889e24dfb410cc1b5e48ebf67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023147"
---
# <a name="install-biztalk-adapter-pack-2013-r2-and-2013"></a>安装 BizTalk 适配器包 2013 R2 和 2013
本文档列出了的软件要求，和步骤安装 Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] (BAP) 中包含 BizTalk Server 2013 或[!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)]。  

## <a name="change-log"></a>更改日志  

|date|更改|  
|---|---|  
|2016 年 3 月|在**后安装...**，添加 Oracle 数据库适配器配置为使用较新的 Oracle.DataAccess.dll 版本的步骤。|  

<a name="BKMK_Prereqs"></a>   
## <a name="software-prerequisites"></a>软件必备项  
 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]可以从使用：  

- .NET 应用程序  

- Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  

- ADO 接口  

- Microsoft SharePoint 门户网站  

  根据如何使用适配器，所需的软件各不相同。  

### <a name="prerequisites-when-using-a-net-application"></a>使用.NET 应用程序时的先决条件  
当使用.NET 应用程序以使用适配器，在开发计算机 （要在其中创建.NET 应用程序的计算机） 上需要以下软件。 按所列顺序安装软件。


|                                                             BizTalk 适配器包 2013 R2                                                              |                                                               BizTalk 适配器包 2013                                                                |
|-------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2 中， [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]，Windows 8.1，Windows 7 SP1 | [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)][!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1、 Windows 8、 Windows 7 SP1 |
|                                                  [!INCLUDE[dotnet451](../includes/dotnet451-md.md)]                                                   |                                               Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]                                               |
|                                                                  Visual Studio 2013                                                                   |                                                                   Visual Studio 2012                                                                   |
|                                         [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]                                          |                                          [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]                                          |
|              企业应用程序客户端和关联的软件。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。              |              企业应用程序客户端和关联的软件。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。               |

### <a name="prerequisites-when-using-a-biztalk-server"></a>使用 BizTalk Server 时的先决条件  
当使用 BizTalk Server 使用的适配器，BizTalk Server 需要以下软件。 按所列顺序安装软件。


|                                                                                                                                                                                                                                             BizTalk 适配器包 2013 R2                                                                                                                                                                                                                                             |                                                                                                                                                                                                                                              BizTalk 适配器包 2013                                                                                                                                                                                                                                               |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                                                                                                [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2 中， [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]，Windows 8.1，Windows 7 SP1                                                                                                                                                                                 |                                                                                                                                                                                [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)][!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1、 Windows 8、 Windows 7 SP1                                                                                                                                                                                |
|                                                                                                                                                                                                                                  [!INCLUDE[dotnet451](../includes/dotnet451-md.md)]                                                                                                                                                                                                                                  |                                                                                                                                                                                                                              Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]                                                                                                                                                                                                                              |
|                                                                                                                                                                                                                                                  Visual Studio 2013                                                                                                                                                                                                                                                  |                                                                                                                                                                                                                                                  Visual Studio 2012                                                                                                                                                                                                                                                  |
| [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]<br /><br /> 安装[!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)]有关[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]附带[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。 若要安装，请执行**自定义**(选择**BizTalk Server 外接程序**) 或**完成**安装[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。 | [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]<br /><br /> 安装[!INCLUDE[consumeadapterservlong](../includes/consumeadapterservlong-md.md)]有关[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]附带[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。 若要安装，请执行**自定义**(选择**BizTalk Server 外接程序**) 或**完成**安装[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。 |
|                                                                                                                                                                                                                                                BizTalk Server 2013 R2                                                                                                                                                                                                                                                |                                                                                                                                                                                                                                                 BizTalk Server 2013                                                                                                                                                                                                                                                  |
|                                                                                                                                                                                             企业应用程序客户端和关联的软件。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。                                                                                                                                                                                              |                                                                                                                                                                                             企业应用程序客户端和关联的软件。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。                                                                                                                                                                                              |

### <a name="prerequisites-when-using-ado"></a>使用 ADO 时的先决条件  
 **[!INCLUDE[adaptersap](../includes/adaptersap-md.md)]** 并**[!INCLUDE[adaptersiebel](../includes/adaptersiebel-md.md)]** 包括 ADO 层 (*[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]* 和*[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]*)。 此 ADO 层可用于编写 ADO.NET 客户端连接到 SAP 系统或 Siebel 系统。 您可以还使用 ADO 层与 SQL Server Integration Services (SSIS) 导入和导出数据从 LOB 应用程序和 SQL Server Reporting Services (SSRS) 以生成报表以显示来自 LOB 系统的数据。  

> [!NOTE]
>  与 SSRS 使用 ADO 提供程序仅支持*[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]*。  

使用计算机上需要以下软件[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]与 ADO 接口。 按所列顺序安装软件。


|                                                             BizTalk 适配器包 2013 R2                                                              |                                                               BizTalk 适配器包 2013                                                                |
|-------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2 中， [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]，Windows 8.1，Windows 7 SP1 | [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)][!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1、 Windows 8、 Windows 7 SP1 |
|                                                  [!INCLUDE[dotnet451](../includes/dotnet451-md.md)]                                                   |                                               Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]                                               |
|                                                                  Visual Studio 2013                                                                   |                                                                   Visual Studio 2012                                                                   |
|                                         [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]                                          |                                          [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]                                          |
|                [!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)], [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]                 |            [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)], [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]            |
|              企业应用程序客户端和关联的软件。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。              |              企业应用程序客户端和关联的软件。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。               |

### <a name="prerequisites-when-using-microsoft-sharepoint"></a>使用 Microsoft SharePoint 时的先决条件  
 使用与 Microsoft SharePoint 适配器的目标是在 SharePoint 门户网站上显示的 LOB 应用程序中的数据。  

使用典型设置[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，SharePoint 可以一台计算机，或为不同任务使用不同的计算机。 下表总结了每台计算机的必备软件。 如果使用一台计算机，该计算机上需要的所有软件。 按所列顺序安装软件。  


|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             运行 WCF 适配器服务开发向导计算机                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      你在其中托管 WCF 服务的计算机                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | 计算机在其中使用 SharePoint Designer 来定义外部内容类型 |                                    计算机中，使用 SharePoint 来显示从 LOB 应用程序信息                                     |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **BAP 2013 R2**:<ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2<br/>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>Windows 8.1<br/>Windows 7 SP1</li><li>[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]</li><li> Visual Studio 2013</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><li>各自的企业应用程序客户端和关联的软件。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。</li></ul> **BAP 2013**:<ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1<br/>Windows 8<br/>Windows 7 SP1</li><li>Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</li><li>Visual Studio 2012</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><li>各自的企业应用程序客户端和关联的软件。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。</li></ul> | **BAP 2013 R2**:<ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2<br/>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>Windows 8.1<br/>Windows 7 SP1</li><li>[!INCLUDE[dotnet451](../includes/dotnet451-md.md)]</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><li>各自的企业应用程序客户端和关联的软件。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。</li><li>附带了操作系统的 Internet 信息服务 (IIS) 版本。 KB 224609 列出的版本。</li></ul>**BAP 2013**:<ul><li>[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]<br/>[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] SP1<br/>Windows 8<br/>Windows 7 SP1</li><li>Microsoft [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]</li><li>[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]</li><li>Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]</li><li>各自的企业应用程序客户端和关联的软件。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。</li><li>附带了操作系统的 Internet 信息服务 (IIS) 版本。 KB 224609 列出的版本。</li></ul> |            Microsoft Office SharePoint Server 软件开发工具包 (SDK)             | Microsoft Office 服务器基础结构更新。 在下载[ http://go.microsoft.com/fwlink/?LinkId=128344 ](http://go.microsoft.com/fwlink/?LinkId=128344)。 |

<a name="BKMK_SuppLOB"></a>   
## <a name="supported-enterprise-application-versions"></a>受支持的企业应用程序版本  

若要查看特定的 LOB 系统版本支持的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，请参阅**[受支持的业务线 (LOB) 系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx)**。 

本部分列出了每个适配器，任何额外信息，如 Dll 的任何客户端所需的每个适配器。  

### <a name="oracle-database-adapter"></a>Oracle 数据库适配器  

-   可选： 如果使用 Oracle 数据库使用分布式的事务，安装**Oracle 服务的 Microsoft Transaction Server** （Oracle 客户端安装的一部分） 的计算机上运行适配器客户端。  

-   对于应用程序可以使用 ODP.NET 的最新版本，安装**策略 Dll**和在 GAC 中注册 Dll。 请参阅[Oracle 数据提供程序的.NET 常见问题解答](http://www.oracle.com/technetwork/database/windows/faq-093106.html)。  

### <a name="oracle-e-business-adapter"></a>Oracle E-business 适配器  

-   可选： 若要使用 Oracle 数据库的分布式的事务，安装**Oracle 服务的 Microsoft Transaction Server** （Oracle 客户端安装的一部分） 的计算机上运行适配器客户端。  

-   对于应用程序可以使用 ODP.NET 的最新版本，安装**策略 Dll**和在 GAC 中注册 Dll。 请参阅[Oracle 数据提供程序的.NET 常见问题解答](http://www.oracle.com/technetwork/database/windows/faq-093106.html)。  

### <a name="sap-adapter"></a>SAP 适配器  

- [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]需要 Unicode 版本而不考虑 SAP 系统是否是 Unicode 或非 Unicode 的 RFC SDK。  

- **所需的驱动程序**： 下表列出了所需的 Dll[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]与 SAP 系统进行交互。 必须从 SAP Service Marketplace 下载大部分包含这些 Dll 的包。 若要获取从 SAP Service Marketplace 下载： 

  1. 从 SAP Service Marketplace 安装 Download Manager 可用。  

  2. 配置通过你的凭据用于 SAP Service Marketplace 下载管理器。  

  3. 授权由你的组织中的 SAP 管理员从 SAP 服务网站上下载软件。 这是必需的因为对 SAP 软件分发中心访问受限制的下载软件授权对象。 这可确保只能由授权用户下载的软件。  

  4. 安装 SAPCAR 程序，需从 SAP Service Marketplace 下载的包中提取文件。 SAP Service Marketplace 也是 SAPCAR。  

     32 位和 64 位版本的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，必须具有相应的 32 位和 64 位版本的这些 Dll。  

  -   32 位计算机上，必须将 Dll 的 32 位版本添加到 C:\Windows\System32 文件夹。  

  -   64 位计算机上，必须将 Dll 的 32 位版本添加到 C:\Windows\SysWow64 文件夹。 必须将 Dll 的 64 位版本添加到 C:\Windows\System32 文件夹中。  

  | SAP 客户端版本 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  必需的驱动程序                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
  |--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  |        6.4         |                                                                                                                                                                                                                       **BizTalk 适配器包 2013年仅**<br /><br /> - **SAP RFC SDK 6.40 UNICODE**。 这是可作为一部分 SNOTE<sup> * </sup> 27517。若要下载 SDK 的说明[ http://go.microsoft.com/fwlink/?LinkId=94691 ](http://go.microsoft.com/fwlink/?LinkId=94691)。下载并解压缩 SDK 后，将所有 Dll 从 \rfcsdk\bin 和 \rfcsdk\lib 文件夹都复制到此表前面提到的相关位置。<br /> <br /> -Dll 的形式提供来自 SAP 的一部分\* \*R3DLLINST.zip*<em>。 该文件包含 Microsoft 运行时 Dll 并可以从 SAP 网站上下载。 请参阅 SNOTE<sup> </em> </sup> 684106 有关详细信息。 可以下载.zip 文件[ http://go.microsoft.com/fwlink/?LinkId=94693 ](http://go.microsoft.com/fwlink/?LinkId=94693)。 此链接都有可以在哪里下载包上的"附件"选项。<br /><br /> -如果使用 SAP 安全网络通信 (SNC) 连接到 SAP 系统，您还必须从 SAP 相关的 Dll。 这些 Dll 是不同的 32 位和 64 位平台和适用于 SNOTE<sup> * </sup> 352295。您可以下载从 Dll [ http://go.microsoft.com/fwlink/?LinkId=104032 ](http://go.microsoft.com/fwlink/?LinkId=104032)。此链接都有可以在哪里下载包上的"附件"选项。Dll 的名称为：<br /><br /> - \*\*为 32 位*<em>: gsskrb5.dll、 gssntlm.dll<br /><br /> -  \*\*针对 64 位 x86</em>\*: gx64krb5.dll、 gx64ntlm.dll                                                                                                                                                                                                                       |
  |        7.0         |                                                                                                                                                                                                                                             - **SAP RFC SDK 7.00 UNICODE**。 这是可作为一部分 SNOTE<sup> * </sup> 27517。若要下载 SDK 的说明[ http://go.microsoft.com/fwlink/?LinkId=94691 ](http://go.microsoft.com/fwlink/?LinkId=94691)。下载并解压缩 SDK 后，将复制所有 Dll，\rfcsdk\bin 和 \rfcsdk\lib 文件夹从 / 向此表前面提到的相关位置。<br /> <br /> -Dll 的形式提供来自 SAP 的一部分\* \*R3DLLINST.zip*<em>。 该文件包含 Microsoft 运行时 Dll 并可以从 SAP 网站上下载。 请参阅 SNOTE<sup> </em> </sup> 684106 有关详细信息。 可以下载.zip 文件[ http://go.microsoft.com/fwlink/?LinkId=94693 ](http://go.microsoft.com/fwlink/?LinkId=94693)。 此链接都有可以在哪里下载包上的"附件"选项。<br /><br /> -如果使用 SAP 安全网络通信 (SNC) 连接到 SAP 系统，您还必须从 SAP 相关的 Dll。 这些 Dll 是不同的 32 位和 64 位平台和适用于 SNOTE<sup> * </sup> 352295。您可以下载从 Dll [ http://go.microsoft.com/fwlink/?LinkId=104032 ](http://go.microsoft.com/fwlink/?LinkId=104032)。此链接都有可以在哪里下载包上的"附件"选项。Dll 的名称为：<br /><br /> - \*\*为 32 位*<em>: gsskrb5.dll、 gssntlm.dll<br /><br /> - \*\*针对 64 位 x86</em>\*: gx64krb5.dll、 gx64ntlm.dll                                                                                                                                                                                                                                             |
  |        7.1         | - **SAP RFC SDK 7.10 UNICODE**。 这是可作为一部分 SNOTE<sup> * </sup> 27517。若要下载 SDK 的说明[ http://go.microsoft.com/fwlink/?LinkId=94691 ](http://go.microsoft.com/fwlink/?LinkId=94691)。下载并解压缩 SDK 后，将所有 Dll 从 \rfcsdk\bin 和 \rfcsdk\lib 文件夹都复制到此表前面提到的相关位置。<br /> <br /> -Dll 的形式提供来自 SAP 的一部分\* \*R3DLLINST.zip*<em>。 该文件包含 Microsoft 运行时 Dll 并可以从 SAP 网站上下载。 请参阅 SNOTE<sup> </em> </sup> 684106 有关详细信息。 可以下载.zip 文件[ http://go.microsoft.com/fwlink/?LinkId=94693 ](http://go.microsoft.com/fwlink/?LinkId=94693)。 此链接都有可以在哪里下载包上的"附件"选项。<br /><br /> Microsoft Visual c + + 运行时 Dll 所需的 SAP 7.1 客户端是可从以下链接：<br /><br /> - **对于 32 位 SAP 7.1 客户端**： 从 Vcredist_x86.exe [ http://go.microsoft.com/fwlink/?LinkId=107086 ](http://go.microsoft.com/fwlink/?LinkId=107086)。<br /><br /> -                                 **对于 64 位 SAP 7.1 客户端**： 从 Vcredist_x64.exe [ http://go.microsoft.com/fwlink/?LinkId=107087 ](http://go.microsoft.com/fwlink/?LinkId=107087)。<br /><br /> -如果使用 SAP 安全网络通信 (SNC) 连接到 SAP 系统，您还必须从 SAP 相关的 Dll。 这些 Dll 是不同的 32 位和 64 位平台和适用于 SNOTE<sup> * </sup> 352295。您可以下载从 Dll [ http://go.microsoft.com/fwlink/?LinkId=104032 ](http://go.microsoft.com/fwlink/?LinkId=104032)。此链接都有可以在哪里下载包上的"附件"选项。Dll 的名称为：<br /><br /> - \*\*为 32 位*<em>: gsskrb5.dll、 gssntlm.dll<br /><br /> - \*\*针对 64 位 x86</em>\*: gx64krb5.dll、 gx64ntlm.dll |

   * SNOTEs 是附带由 SAP 发布的修补程序的发行说明。  

### <a name="siebel-adapter"></a>Siebel 适配器  
没有额外的步骤。

### <a name="sql-adapter"></a>SQL 适配器  

**所需的驱动程序**:  

-   **为 SQL Server 2005**： 如果在 SQL Server 中创建用户定义类型 (Udt)，请确保对 Udt 的相应程序集添加到 GAC。  

-   **SQL server 2014，SQL Server 2012 中，SQL Server 2008 R2 和 SQL Server 2008 SP1**:  

    -   如果使用 Udt 附带的 SQL Server 版本，例如，地理位置，请确保以下 Dll 计算机上存在其中使用该适配器在 SQL Server 上执行操作。 例如，如果在 BizTalk 项目，在 SQL Server 上执行操作，这些 Dll 必须在运行 BizTalk Server 的计算机上存在。  

        -   请确保 Microsoft.SqlServer.Types.dll 添加到 GAC。  

        -   确保 SqlServerSpatial.dll System32 文件夹中可用。    

        可以通过运行 SQL Server 安装程序并选择在计算机上安装这些 Dll**管理工具-Basic**并**管理工具-完整**中**功能选择**向导页。          

    -   如果使用适配器来执行对 FILESTREAM 数据类型的列的操作，请确保已安装的 SQL 客户端连接 SDK。 可以通过运行 SQL Server 安装程序并选择安装 SQL 客户端连接 SDK **SQL 客户端连接 SDK**中**功能选择**向导页。 适配器使用 sqlncli10.dll，随 SQL 客户端连接 SDK，用于执行 FILESTREAM 操作。  

    -   如果在 SQL Server 中创建你自己的 Udt，请确保对 Udt 的相应程序集添加到 GAC。

## <a name="64-bit-support"></a>64 位支持

Siebel 适配器支持在 32 位主机实例中。 不支持在 64 位主机实例中运行的 Siebel 适配器。 

所有其他适配器可以运行的 32 位或 64 位主机实例中。 



 有关用于安装 32 位和 64 位支持的安装方案详细信息[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，请参阅[安装在 32 位和 64 位平台上的 BizTalk 适配器包方案](#BKMK_Install_Scenarios)。  

<a name="BKMK_Install_Adap"></a>   
## <a name="installing-the-biztalk-adapter-pack"></a>安装 BizTalk 适配器包  
 确保所有[必备软件](#BKMK_Prereqs)安装之前安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。 你可以安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]以下两种方式：  

- **在交互模式下**： 运行安装程序向导  

- **在静默模式下**： 使用命令行  

  > [!IMPORTANT]
  >  必须在其中安装的计算机上具有管理特权[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，不考虑是否要安装使用向导或命令行。  

### <a name="typical-vs-custom-installation"></a>典型安装与自定义安装  
本部分列出了安装类型，以及每个选项安装的功能：  

- **典型**并**完成**选项与关联的数据提供程序安装所有适配器。 没有选择特定的适配器的安装的选项。  

- **自定义**选项与关联的数据提供程序将安装一个或多个适配器。 你可以选择要安装的适配器。 如果您选择安装数据提供程序，还必须安装相应的适配器。 但是，你可以无需安装相应的数据提供程序安装适配器。 执行此操作通过展开**ADO 提供程序**节点，并选择不想要安装的提供程序。 请参阅[以交互模式安装的 BizTalk 适配器包](#BKMK_Install_wizard)。  

   例如，如果在安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，还必须安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]。 但是，可以安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]而无需安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]。  

<a name="BKMK_Install_Scenarios"></a>   
### <a name="scenarios-for-installing-the-biztalk-adapter-pack-on-32-bit-and-64-bit-platforms"></a>在 32 位和 64 位平台上安装 BizTalk 适配器包方案  
 与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，则[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]可用于： 

- [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 设计时 （时生成的操作的 LOB 应用程序的元数据）

- BizTalk Server 管理控制台 （用于创建物理端口） 的设计时

  > [!NOTE]
  >  BizTalk Server 管理控制台作为 32 位 Microsoft 管理控制台 (MMC) 应用程序运行。  

- BizTalk 运行时 （发送和接收消息时的 LOB 应用程序）

可以为所有这些任务，使用一台计算机，也可以使用不同的计算机。 因为这两[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]以及 BizTalk MMC 是 32 位进程，你必须安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]中完成的设计时任务的计算机上。 

#### <a name="scenarios-for-installing-the-biztalk-adapter-pack-on-a-32-bit-platform"></a>在 32 位平台上安装 BizTalk 适配器包方案  
 在 32 位平台上支持的方案包括：  


|                                                                                                                 为 Visual Studio 设计时                                                                                                                  |                                                                                                                  为 BizTalk MMC 设计时                                                                                                                   |                                                                                                                      Biztalk 运行时                                                                                                                      |                                                                                        Visual Studio 设计时和/或 BizTalk MMC 设计时间 + BizTalk 运行时                                                                                         |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 安装 32 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> 安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他所需的 Dll。 | 安装 32 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> 安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他所需的 Dll。 | 安装 32 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> 安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他所需的 Dll。 | 安装 32 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> 安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他所需的 Dll。 |

#### <a name="scenarios-for-installing-the-biztalk-adapter-pack-on-a-64-bit-platform"></a>在 64 位平台上安装 BizTalk 适配器包方案  
 在 64 位平台上支持的方案包括：  


|                                                                                                                 为 Visual Studio 设计时                                                                                                                  |                                                                                                                  为 BizTalk MMC 设计时                                                                                                                   |                                                                                                                                                                                                                                                                                                         Biztalk 运行时                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                                Visual Studio 设计时和/或 BizTalk MMC 设计时间 + BizTalk 运行时                                                                                                                                                                                                                                                                                                                                                                |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> 安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他所需的 Dll。 | 安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> 安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他所需的 Dll。 | **对于 32 位 BizTalk 进程**:<br /><br /> 安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> 安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他所需的 Dll。<br /><br /> **对于 64 位 BizTalk 进程**:<br /><br /> 安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> 安装 64 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 64 位 LOB 客户端和其他所需的 Dll。 | **对于 32 位 BizTalk 进程**:<br /><br /> 安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> 安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他所需的 Dll。<br /><br /> **对于 64 位 BizTalk 进程**:<br /><br /> 安装 64 位[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]。<br /><br /> 安装 64 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 64 位 LOB 客户端和其他所需的 Dll。<br /><br /> 安装 32 位[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。<br /><br /> -安装 32 位 LOB 客户端和其他所需的 Dll。 |

> [!NOTE]
>  你想要执行设计时任务的任何计算机上使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk MMC 中，你必须安装 32 位或[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。  

<a name="BKMK_Install_wizard"></a>   
### <a name="installing-the-biztalk-adapter-pack-in-interactive-mode"></a>在交互模式下安装 BizTalk 适配器包  
完成以下步骤来安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]使用安装向导。  

1. 从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装媒体上，运行**Setup.exe**。  

2. 选择**安装 Microsoft BizTalk 适配器**。 在下一步的窗口中，选择**安装 Microsoft BizTalk Adapter Pack**或**安装 Microsoft BizTalk 适配器包 (x64)**，取决于你的平台。  

   > [!NOTE]
   >  如果您正在安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]虚拟机上安装向导可能无法继续超出了对话框，通知安装程序正在检查的可用磁盘空间。 在这种情况下，我们建议你使用的无提示安装选项。 请参阅[以无提示模式安装 BizTalk 适配器包](#BKMK_SilentInst)（在本主题中）。  

3. 在欢迎屏幕上，选择**下一步**。  

4. 接受最终用户许可协议 (EULA)，然后选择**下一步**。  

5. 在中**选择安装类型**:  

   -   若要安装的最常见的功能，请选择**典型**。  

   -   若要选择你想要安装的适配器，请选择**自定义**，然后继续下一步。  

   -   若要安装所有功能，请选择**完成**。  

       > [!IMPORTANT]
       >  若要安装用于与你的企业应用程序中，选择适配器**自定义**安装。  

6. **所需**仅在您选择自定义安装。 如果选择了**典型**或**完成**安装，然后跳过此步骤中，并转到步骤 7。  

    1.  在中**自定义安装**，展开**基适配器**若要查看可用的适配器。  

    2.  对于不希望适配器，选择适配器旁的图标，然后选择**整个功能将不可**。  

    3.  展开**ADO 提供程序**，然后选择不想要安装的提供程序。  

    4.  选择“下一步” 。  

7. 选择“安装”。  

8. 在中**客户体验改善计划**，可以选择进行注册。 如果你注册，可以与 Microsoft 共享的以下数据：  

   - 与正在其安装的计算机硬件相关的数据[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。  

   - 与将用于企业应用程序版本相关的数据[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。  

     选择“确定”。 [CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699)提供了详细信息。  

   > [!NOTE]
   >  通过在从修复模式下运行安装程序可以随时更改此设置**程序**。  

9. 选择“完成”。  

<a name="BKMK_SilentInst"></a>   
### <a name="installing-the-biztalk-adapter-pack-in-silent-mode"></a>在无提示模式下安装 BizTalk 适配器包  
 使用**msiexec**命令执行无提示安装。 作为 msiexec 命令的一部分，输入你想要安装的各个组件。 下表列出了每个组件中的值[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。 使用这些值来安装 （或删除） 特定的组件。 若要安装 （或删除） 多个组件，可以使用逗号分隔这些值的组合。  


|                                    组件名称                                    |                                                                命令行属性的相应值                                                                 |
|--------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]        |                                                                                   DbFeature                                                                                    |
| [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)] |                                                                                OracleEBSFeature                                                                                |
|           [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]           |                                                                             SapBaseAdapterFeature                                                                              |
|        [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]        |                                                                            SiebelBaseAdapterFeature                                                                            |
|            [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]            |                                                                                   SqlFeature                                                                                   |
|        [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]        |     SapAdoFeature<br /><br /> **请注意**： 必须提供此值，仅当你安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]还。      |
|     [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]     | SiebelAdoFeature<br /><br /> **请注意**： 必须提供此值，仅当你安装[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]还。 |
|                                    所有组件                                    |                                                                                      ALL                                                                                       |

> [!IMPORTANT]
>  功能名称不区分大小写。  

 以下步骤显示如何完成的无提示安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]不同组件。  

##### <a name="install-in-silent-mode"></a>在无提示模式下安装  

1. 打开命令提示符，并转到[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]根中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。  

2. 运行以下命令，根据你想要安装：  

   > [!NOTE]
   >  若要执行无提示安装的基于 x64 的平台上，替换`AdaptersSetup.msi`与`AdaptersSetup64.msi`以下命令中。  

   - 若要执行的完整安装，安装所有适配器包括.NET Framework 数据提供程序，请键入：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=ALL  
     ```  

   - 若要仅安装[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，类型：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=DbFeature  
     ```  

   - 若要仅安装[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]，类型：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=OracleEBSFeature  
     ```  

   - 若要仅安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，类型：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature  
     ```  

   - 若要安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]连同[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，类型：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature  
     ```  

   - 若要仅安装[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]，类型：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature  
     ```  

   - 若要安装[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]连同[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]，类型：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature,SiebelAdoFeature  
     ```  

   - 若要仅安装[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]，类型：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SqlFeature  
     ```  

   - 若要安装所有基适配器，请键入：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SiebelBaseAdapterFeature,DbFeature,OracleEBSFeature,SqlFeature  
     ```  

   - 若要安装两个.NET Framework 数据提供程序，请键入：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapAdoFeature,SiebelAdoFeature  
     ```  

   - 任何类型的用逗号分隔的组件的自定义安装。 例如，若要安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]与[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]，和[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]类型：  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature,SiebelBaseAdapterFeature  
     ```  

   - 您还可以选择无提示安装的一部分注册 CEIP。 类型：  

     ```  
     msiexec /i AdaptersSetup.msi /qn CEIP_OPTIN=true  
     ```  

      默认情况下，选项为 false。 

     > [!IMPORTANT]
     >  安装时[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]评估版在静默模式下，CEIP 的默认选项为 true。  

     有关 msiexec 命令类型的详细信息`msiexec`上的命令行和按`ENTER`。 或转至[ http://go.microsoft.com/fwlink/p/?LinkId=103199 ](http://go.microsoft.com/fwlink/p/?LinkId=103199)。

<a name="BKMK_PostInst"></a>   
### <a name="after-installing-the-biztalk-adapter-pack"></a>安装 BizTalk 适配器包后  
 可能需要在安装后执行以下任务[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]根据想要与每个适配器执行哪些操作：  

- [配置 Oracle 数据库适配器以使用较新的 Oracle.DataAccess.dll 版本](#BKMK_ConfigNewOracleDLL)OracleDB 配置文件中。  

- [（仅适用于 SAP 适配器） 创建 SQL Server 数据库对象](#BKMK_CreateSQLServer)SAP 系统中调用事务 Rfc (Trfc)。  

- [注册适配器绑定](#BKMK_Register_Bindings)和.NET Framework 数据提供程序，如果安装程序向导无法执行此操作。  

- [确定公用密钥和版本](#BKMK_PubKey)的不同适配器文件。  

- [安装自定义 Rfc](#BKMK_InstallCustomRFC)如果您选择安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]。  

<a name="BKMK_ConfigNewOracleDLL"></a>   
#### <a name="configure-the-oracle-database-adapter-to-use-a-newer-oracledataaccessdll-version"></a>配置 Oracle 数据库适配器以使用较新的 Oracle.DataAccess.dll 版本  
 在配置要使用 Wcf-oracledb 适配器或使用 Visual Studio 使用生成的适配器的端口时，显示一条消息，适配器需要 Oracle.DataAccess.dll 版本 2.111.7.0。 若要解决此消息，请安装受支持的 Oracle.DataAccess.dll 版本 (请参阅[受支持版本列表](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx))，然后更新`bindingRedirect`OracleDB 配置文件中的元素。 步骤：  

1.  在 BizTalk 服务器上，请转到以下文件夹：  

     *驱动器*: \Program Files\Microsoft BizTalk Adapter Pack (x64) \bin  

     *驱动器*: \Program 文件 (x86) \Microsoft BizTalk Adapter Pack\bin  

2.  打开 Microsoft.Adapters.OracleDB.config 文件。  

3.  以下部分中，找到并复制/粘贴以下：  

    ```  
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
              <dependentAssembly>  
                        <assemblyIdentity name="Oracle.DataAccess" publicKeyToken="89b483f429c47342" culture="neutral" />  
                        <bindingRedirect oldVersion="2.111.7.00" newVersion="2.112.1.00"/>  
              </dependentAssembly>  
    </assemblyBinding>  

    ```  

    > [!NOTE]
    >  在此示例中，我们将设置*newVersion* 2.112.1.00 到。 将此值设置为已安装的版本。  

> [!IMPORTANT]
> - 如果此组中有多个 BizTalk Server，请在组中的所有 BizTalk 服务器上进行此更改。  
>   -   *NewVersion*值需要更新基于 Oracle.DataAccess.dll 文件在计算机上安装的版本。  包含从 Oracle 安装 Oracle 客户端 Oracle.DataAccess.dll。  您只需安装的 Oracle 客户端版本[支持的 BizTalk 适配器包](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)。  

<a name="BKMK_CreateSQLServer"></a>   
#### <a name="create-sql-server-database-objects-only-for-the-sap-adapter"></a>创建 SQL Server 数据库对象 （仅适用于 SAP 适配器）  
 若要调用 Trfc SAP 系统中，运行*SapAdapter DbScript Install.sql* SQL 脚本。 此脚本安装使用[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装，并在 SQL Server 中创建数据库对象。 该脚本通常安装在\<安装驱动器\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。 只要使用的适配器来调用 Trfc 时输入该数据库名称，可以针对任何 SQL Server 数据库，运行此脚本。  

<a name="BKMK_Register_Bindings"></a>   
#### <a name="register-the-adapter-bindings"></a>注册适配器绑定  
 期间[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装，安装向导可能无法注册适配器绑定或.NET Framework Data Provider for mySAP Business Suite，但安装程序继续执行适配器安装。 这可能会导致问题的 Windows Communication Foundation (WCF) 安装中，由于[!INCLUDE[afproductnamelong](../includes/afproductnamelong-md.md)]安装或被损坏的 machine.config 文件。  

完成这些步骤*仅*如果安装向导无法在 machine.config 文件中注册的适配器绑定或.NET Framework 数据提供程序。  

###### <a name="register-the-adapter-bindings-or-the-net-framework-data-providers"></a>注册适配器绑定或.NET Framework 数据提供程序  

1. 请转到计算机上的 machine.config 文件。 例如，在 32 位平台上，在 machine.config 位于下\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。  

2. 打开文件使用文本编辑器。  

3. 注册适配器绑定：  

   1. 搜索`system.serviceModel`元素，并添加其下的以下：  

      ```  
      <client>  
        <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
        <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
        <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
        <endpoint binding="oracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  
      ```  

   2. 搜索`bindingElementExtensions`system.serviceModel\extensions 下的元素。  

   3. 查找缺失的适配器绑定。 添加以下各节下的`bindingElementExtensions`节点，具体取决于缺少的适配器绑定。 如果安装向导无法注册任何，则必须注册的所有绑定。  

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

   4. 搜索`bindingExtensions`system.serviceModel\extensions 下的元素。  

   5. 查找缺失的适配器绑定。 添加以下各节下的`bindingExtensions`节点，具体取决于缺少的适配器绑定。 如果安装向导无法注册任何，则必须注册的所有绑定。  

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
   >  有关如何确定的公钥的信息，请参阅[确定公用密钥和版本](#BKMK_PubKey)。  

4. 注册.NET Framework 数据提供程序：  

   1. 搜索`DbProviderFactories`system.data 节点下的元素。  

   2. 查找缺少的.NET Framework 数据提供程序。 添加以下各节下的`DbProviderFactories`节点，具体取决于缺失的提供程序。 如果安装向导无法注册任何，则必须注册的所有提供程序。  

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

5. 保存并关闭 machine.config 文件。  

<a name="BKMK_PubKey"></a>   
#### <a name="determine-the-public-key-and-version"></a>确定公用密钥和版本  
 完成以下步骤来确定公用密钥和适配器或.NET Framework 数据提供程序的版本。  

###### <a name="determine-the-public-key"></a>确定公共密钥  

1. 转到 Windows 目录，通常 C:\WINDOWS\assembly。  

2. 右键单击的 DLL 为其也希望将公钥，并选择**属性**。 下表列出了为每个适配器和提供程序 Dll 的名称：  


   |                         适配器/.NET Framework 数据提供程序                         |       DLL 的名称        |
   |--------------------------------------------------------------------------------------|------------------------------|
   |           [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]           |    Microsoft.Adapters.SAP    |
   |        [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]        |  Microsoft.Adapters.Siebel   |
   |        [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]        | Microsoft.Adapters.OracleDB  |
   | [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)] | Microsoft.Adapters.OracleEBS |
   |            [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]            |  Microsoft.Adapters.Sql.dll  |
   |        [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]        |   Microsoft.Data.SAPClient   |
   |     [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]     | Microsoft.Data.SiebelClient  |


3. 上**常规**选项卡上，**公钥标记**值是 DLL 的公共密钥。 **版本**值是 DLL 的版本号。  

4. 复制公钥，并选择**取消**。  

<a name="BKMK_InstallCustomRFC"></a>   
#### <a name="install-the-custom-rfcs"></a>安装自定义 Rfc  
 只需执行此任务，如果你想要使用[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]。 有关安装自定义 Rfc 的说明，请参阅[安装自定义 Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)中[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]文档。 

> [!IMPORTANT]
>  如果使用早期版本的提供的自定义 Rfc [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，则必须将其升级到此版本中提供的 Rfc。 通过删除早期的 Rfc 中，执行此操作，然后安装 Rfc 随此版本。  

## <a name="installing-the-enterprise-applications"></a>安装企业应用程序  
有关步骤和指南来安装不同企业 LOB 系统，我们使用其特定安装 recommendnd 指导。 如果有的话还引用特定的配置更改，其适配器文档。   

## <a name="installation-and-post-installation-checklist"></a>安装和安装后清单  

- 请确保安装所有[必备软件](#BKMK_Prereqs)使用正确的安装选项。

- 请确保已安装在计算机上安装的企业 LOB 应用程序的受支持的版本[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。 请参阅[受支持的企业应用程序版本](#BKMK_SuppLOB)。  

- 若要安装仅适用于企业你想要连接的 LOB 系统的适配器，请确保你安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]使用**自定义**安装选项。 请确保你未安装[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]使用**完成**安装选项。 请参阅[安装的 BizTalk 适配器包](#BKMK_Install_Adap)。  

- 如果你想要进行 SAP 系统使用 tRFC 调用[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，请确保 SQL Server 数据库中创建所需的表。 请参阅[安装的 BizTalk 适配器包后](#BKMK_PostInst)。

- 运行时[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装向导中，可能会收到指示安装程序无法注册绑定的错误消息。 如果是这样，请手动注册它们。 请参阅[安装的 BizTalk 适配器包后](#BKMK_PostInst)。  

- 如果您选择安装[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]作为的一部分[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装，请确保在 SAP 系统上安装自定义 Rfc。 请参阅[安装的 BizTalk 适配器包后](#BKMK_PostInst)。  

<a name="BKMK_Modify_Adap"></a>   
## <a name="change-the-biztalk-adapter-pack-installation"></a>更改 BizTalk 适配器包安装  
 完成以下步骤，更改[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装。 请确保你拥有[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]安装，然后运行安装向导以修改[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装。  

 您可以修改[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装在交互模式下 （安装程序向导），或在无提示模式下 （命令行）。

#### <a name="change-the-bap-installation-in-interactive-mode"></a>更改在交互模式下 BAP 安装  

1. 使用 BizTalk Server Administrators 组的成员帐户登录。  

2. 在中**程序和功能**，选择**卸载程序**。  

3. 右键单击**Microsoft BizTalk Adapter Pack**，然后选择**更改**。  

4. 在欢迎屏幕上，选择**下一步**。  

5. 在中**更改、 修复或删除安装**:  

   - 若要选择你想要安装的组件，请选择**更改**并转到步骤 6。  

   - 若要修复最新安装中的错误，请选择**修复**并转到步骤 7。  

   - 若要删除 Microsoft[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]从计算机上，选择**删除**，然后转到步骤 10。  

6. 如果您选择修改安装：  

   -   展开**Microsoft BizTalk 适配器包**节点，以选择要安装的基本适配器、.NET Framework 数据提供程序，或两者。  

   -   展开**基本适配器**节点，以选择要安装所有适配器或特定的适配器。  

   -   展开**ADO 提供程序**节点，以选择要安装所有提供程序或特定提供程序。  

   -   选择“下一步” 。  

   -   选择**更改**，然后选择**完成**。  

7. 如果您选择中的修复安装，**准备好修复 Microsoft BizTalk Adapter Pack**对话框中，选择**修复**。 启动向导，修复安装。  

8. 如果需要，更改您的首选项有关选择加入 ceip，，然后选择**确定**。 

9. 选择“完成”。  

10. 如果您选择要删除适配器，在**准备好删除 Microsoft BizTalk Adapter Pack**对话框中，选择**删除**，然后选择**完成**。  

#### <a name="change-the-bap-installation-in-silent-mode"></a>更改在静默模式下 BAP 安装  

1. 打开命令提示符，并转到根目录下的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装程序。  

2. 运行类似于下面的命令：  

   > [!NOTE]
   >  若要修改[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在基于 x64 的平台，在以下命令中上, 无提示模式下安装替换`AdaptersSetup.msi`与`AdaptersSetup64.msi`。  

   ```  
   msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature ADDLOCAL=SapBaseAdapterFeature  
   ```  

    此命令将删除[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]，并将安装[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]。  

    通过使用不同的值`REMOVE`和`ADDLOCAL`属性，可以添加或删除特定的组件。 中的表是指[以无提示模式安装 BizTalk 适配器包](#BKMK_SilentInst)（在本主题中） 可以使用这些属性的值有关的信息。  

    此外可以使用 msiexec 命令的一部分 /f 选项执行无提示的修复。 例如：  

   ```  
   msiexec /i AdaptersSetup.msi /qn /f  
   ```  

    使用 /f 选项，可以使用各种不同的组合。 有关 msiexec 命令类型的详细信息`msiexec`上的命令行和按`ENTER`。 或转至[ http://go.microsoft.com/fwlink/p/?LinkId=103199 ](http://go.microsoft.com/fwlink/p/?LinkId=103199)。  

   > [!IMPORTANT]
   >  修改时[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在静默模式下安装，不能更改首选项的选择加入或退出 CEIP。 在过程中选择安装会保留，即使你显式设置为 true 或 false 的 CEIP_OPTIN 首选项。  

<a name="BKMK_Remove_Adap"></a>   
## <a name="removing-the-biztalk-adapter-pack"></a>删除 BizTalk 适配器包  

> [!IMPORTANT]
>  如果要使用的 tRFC 功能的 SQL Server 数据库中创建表[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]，你必须手动将其删除然后再删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装将复制的 SapAdapter DbScript Uninstall.sql 文件通常\<安装驱动器\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。 运行此文件以删除你创建的表。  

完成以下步骤以删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]从您的计算机。 请确保您具有[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]安装，然后运行安装向导以删除适配器。  

 您可以删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在交互模式下 （安装程序向导），或在无提示模式下 （命令行）。

#### <a name="uninstall-the-biztalk-adapter-pack-in-interactive-mode"></a>卸载在交互模式下的 BizTalk 适配器包  

1.  在中**程序和功能**，选择**卸载程序**。  

2.  右键单击**Microsoft BizTalk Adapter Pack**，然后选择**卸载**。  

#### <a name="uninstall-the-biztalk-adapter-pack-in-silent-mode"></a>卸载在静默模式下的 BizTalk 适配器包  

1. 打开命令提示符，并转到根目录下的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装程序。  

2. 运行以下命令：  

   > [!NOTE]
   >  若要删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]在无提示模式在基于 x64 的平台，在以下命令中，替换`AdaptersSetup.msi`与`AdaptersSetup64.msi`。  

   ```  
   msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature  
   ```  

    此命令将删除[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]从[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装。  

    通过提供不同的值`REMOVE`属性，您可以删除特定组件从[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装。 中的表是指[以无提示模式安装 BizTalk 适配器包](#BKMK_SilentInst)（在本主题中） 可以使用此属性的值有关的信息。  

    若要完全删除[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，执行以下命令：  

   ```  
   msiexec /x AdaptersSetup.msi /qn  
   ```  

    有关 msiexec 命令类型的详细信息`msiexec`上的命令行和按`ENTER`。 或转至[ http://go.microsoft.com/fwlink/p/?LinkId=103199 ](http://go.microsoft.com/fwlink/p/?LinkId=103199)。

<a name="BKMK_PostRemove"></a>   
### <a name="after-removing-the-biztalk-adapter-pack"></a>在删除 BizTalk Adapter Pack 之后  
 可能需要删除后执行以下步骤[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]:  

- 删除适配器绑定或.NET Framework 数据提供程序在注册时，如果安装向导未能完成此操作

- 删除自定义 Rfc，如果您选择安装 [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]

<a name="BKMK_Remove_Binding"></a>   
#### <a name="remove-the-bindings-or-the-net-framework-data-provider-registration"></a>删除的绑定或.NET Framework 数据提供程序注册  
 完成这些步骤*仅*如果安装向导无法从 machine.config 文件中删除适配器绑定或.NET Framework 数据提供程序注册。  

###### <a name="remove-the-adapter-bindings-or-net-framework-data-provider-registration"></a>删除适配器绑定或.NET Framework 数据提供程序注册  

1. 请转到计算机上的 machine.config 文件。 例如，在 32 位平台上，在 machine.config 位于下\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。  

2. 打开文件使用文本编辑器。  

3. 删除适配器绑定注册：  

   1. 搜索`system.serviceModel`元素，并删除以下从元素下：  

      ```  
      <client>  
        <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
        <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
        <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
        <endpoint binding="OracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  

      ```  

   2. 搜索`bindingElementExtensions`system.serviceModel\extensions 下的元素。  

   3. 删除以下各节下的`bindingElementExtensions`节点，具体取决于可用的适配器绑定。 如果无法删除任何安装向导，则必须删除所有绑定。  

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

   4. 搜索`bindingExtensions`system.serviceModel\extensions 下的元素。  

   5. 删除以下各节下的`bindingExtensions`节点，具体取决于可用的适配器绑定。 如果无法删除任何安装向导，则必须删除所有绑定。  

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

4. 删除.NET Framework 数据提供程序注册：  

   - 搜索`DbProviderFactories`system.data 节点下的元素。  

   - 查找.NET Framework 数据提供程序仍注册。 删除以下各节下的`DbProviderFactories`节点，具体取决于现有的.NET Framework 数据提供程序。 如果它们存在，则必须删除所有提供程序。  

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

5. 保存并关闭 machine.config 文件。  

<a name="BKMK_Remove_SAP_Pro"></a>   
#### <a name="remove-the-custom-rfcs"></a>删除自定义 Rfc  
完成此步骤以删除自定义安装 SAP 系统中的 Rfc。 请参阅[安装或删除自定义 Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。  

## <a name="troubleshoot-biztalk-adapter-pack-installation"></a>BizTalk 适配器包安装进行故障排除  
 以下是安装时可能会遇到一些问题[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。 有关与安装相关的问题的完整列表，请参阅**排查**每个适配器主题。  

- **在 64 位计算机上的运行安装程序可能会访问架构文件时引发错误**  

   [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装程序访问时将引发错误**Microsoft.Adapters。*\<AdapterName\>*_schema.xml**文件，但继续进行安装适配器。  

   **原因**  

   如果 32 位和 64 位版本的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]安装在同一计算机上同时使用的目标架构文件是相同。 因此，32 位安装的文件[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]可能正在由 IIS 使用 64 位安装程序会尝试对其进行访问时。  

   **解决方法**  

   手动复制**Microsoft.Adapters。*\<AdapterName\>*_schema.xml**从文件`C:\Program Files\Microsoft BizTalk Adapter Pack(x64)\IIS Schemas`"到`C:\Windows\System32\inetsrv\config\schema`。  