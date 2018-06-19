---
title: Oracle 数据库的 BizTalk 适配器的体系结构概述 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, and WCF
- architecture of the Oracle Database adapter
- ODAC
- Oracle Data Access Components
- endpoint
- adapter, architecture
- endpoint address
- ODP.NET
- Oracle Data Provider for .NET
- architecture
ms.assetid: cc59beb5-327a-4b00-a45c-82cc9d505167
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f5d4a23b9802c04af37716f8bef07735d8f80bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216589"
---
# <a name="architecture-overview-of-the-biztalk-adapter-for-oracle-database"></a>Oracle 数据库的 BizTalk 适配器的体系结构概述
说明用于体系结构[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]。 

了解[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]体系结构可帮助你：  
  
-   了解之间的关系[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]和[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]。  
  
-   了解安全边界，以便你可以更好地保护你的解决方案中的数据。  
  
-   了解[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]绑定属性。  
  
-   解决安装问题。  
  
本主题介绍使用的端到端解决方案的体系结构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]对 Oracle 数据库进行操作，还将说明内部体系结构的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
 
## <a name="adapter-architecture-overview"></a>适配器体系结构概述
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 此绑定包含用于实现与 Oracle 数据库进行通信的单个自定义传输绑定元素。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]由包装[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]运行时，并向应用程序可以通过公开[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道体系结构。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] .NET (ODP.NET) 和 Oracle 客户端，属于 Windows Oracle 数据访问组件 (ODAC) 与 Oracle 数据提供程序通过 Oracle 数据库通信。  
  
 下图显示了通过使用开发的解决方案的端到端体系结构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
 ![Oracle 数据库适配器体系结构关系图](../../adapters-and-accelerators/adapter-oracle-database/media/bts-oracledb-architecturec.gif "bts_OracleDB_Architecturec")  
  
## <a name="consuming-the-adapter"></a>使用适配器  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开 Oracle 数据库作为[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务客户端应用程序。 若要执行的操作和访问 Oracle 数据库上的数据，客户端应用程序交换使用 SOAP 消息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道。 上图显示四种方式在其中[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]可使用。 它们分别是：  
  
-   通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型应用程序。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型应用程序执行对 Oracle 数据库的操作通过使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]直接与通道模型交换 SOAP 消息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 有关开发解决方案的详细信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型，请参见[开发 Oracle 数据库应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)。  
  
-   通过[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型应用程序。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型应用程序上调用方法[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端在 Oracle 数据库上执行操作。 A[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端模型公开的运算[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]作为.NET 方法。 你可以使用[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]或 WCF ServiceModel 元数据实用工具 (svcutil.exe) 创建[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]从公开元数据的客户端类[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 有关详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型和[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[开发 Oracle 数据库应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)。  
  
-   通过 BizTalk 接收位置或发送配置为使用 Microsoft BizTalk WCF 自定义适配器的端口。 WCF 自定义适配器启用的使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]扩展性功能。 使用 WCF 自定义适配器中，你可以选择和配置 Oracle DB 绑定和接收位置的行为或发送端口。 有关如何使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案，请参阅[开发 BizTalk 应用程序](../../core/develop-your-biztalk-applications.md)。  
  
-   通过 IIS 托管的 Web 服务。 在此方案中，使用标准的 WCF Http 绑定的 IIS 中承载 WCF 服务代理生成使用适配器。 这将作为 Web 服务向外部用户公开的服务协定。 IIS 自动托管在运行时，这反过来，与 Oracle 数据库通信的适配器。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]并且 ODAC 始终托管进程的应用程序或服务使用适配器。  
  
## <a name="oracle-database-adapter-and-wcf"></a>Oracle 数据库适配器和 WCF  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供一个基于 SOAP 消息的交换对客户端和服务之间的通道的编程模型。 这些消息将由通信的客户端和服务公开的终结点之间发送。 终结点组成：  
  
-   *终结点地址*，它指定从该处接收消息的位置  
  
-   A*绑定*，它指定用于交换消息的通信协议  
  
-   A*协定*，它指定终结点公开的操作和数据类型。  
  
 绑定由一个或多个堆叠在一起以定义如何与终结点交换消息的绑定元素组成。 至少，绑定必须指定的传输和编码用于与终结点交换消息。 会通过组成一个或多个通道的通道堆栈终结点之间的消息交换。 每个通道是一个终结点配置的绑定中的绑定元素的具体实现。 [WCF 文档](http://go.microsoft.com/fwlink/?LinkID=196850)更多详细信息包括有关[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，和[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]编程模型。  
  
 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]公开[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]自定义绑定，Oracle DB 绑定 (**Microsoft.Adapters.OracleDB.OracleDBBinding**)。 默认情况下，此绑定包含单个自定义传输绑定元素，Oracle 数据库适配器绑定元素 (**Microsoft.Adapters.OracleDB.OracleDBAdapter**)，这样 Oracle 数据库上的操作。  
  
 **Microsoft.Adapters.OracleDB.OracleDBBinding** （Oracle DB 绑定） 和**Microsoft.Adapters.OracleDB.OracleDBAdapter** （Oracle 数据库适配器绑定元素） 是公共类并向还公开配置系统。 由于 Oracle 数据库适配器绑定元素公开时公开，你可以构建自己的自定义[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]绑定支持的扩展的功能[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 例如，可以实现一个自定义绑定以支持企业单一登录 (SSO) 在[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道或服务模型解决方案。 聚合数据库操作到单个多功能操作或执行由自定义应用程序实现的操作和 Oracle 数据库上的操作之间的架构转换是执行此操作的原因。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]之上生成[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]和上运行[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]运行时。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供的软件框架和工具可供基础结构，它[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]用于向用户和适配器客户端提供一组丰富的功能。  

## <a name="oracle-database-adapter-and-wcf-lob-adapter-sdk"></a>Oracle 数据库适配器和 WCF LOB 适配器 SDK
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]实现利用提供的功能的核心组件的一组[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]并提供有关.NET (ODP.NET) 的连接到 Oracle 数据库通过 Oracle 数据提供程序。  
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]用作通过其软件层[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接口与[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。 ODP.NET 用作通过其层[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与 Oracle 数据库的接口。 
 
下图显示的内部组件之间的关系[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]， [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，和 ODP.NET。  
  
 ![Oracle 数据库适配器内部体系结构](../../adapters-and-accelerators/adapter-oracle-database/media/fa730561-9db7-40d1-bfcd-bc4eb119eea8.gif "fa730561-9db7-40d1-bfcd-bc4eb119eea8")  
 
   
## <a name="odpnet"></a>ODP.NET  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与 Oracle 数据库通过 ODP.NET 和 Oracle 客户端连接。 这两个这些组件是一部分的 Oracle 数据访问组件 (ODAC)。  
  
 ODP.NET 实现的数据提供程序与 ADO.NET 界面一致的 Oracle 数据库。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]由 ODP.NET 公开的类用于对 Oracle 数据库进行操作。  
  
 Oracle 客户端提供与 Oracle 数据库的连接。 通过提供一个连接 URI 建立与 Oracle 数据库的连接到[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 你可以通过两种方式指定连接 URI:  
  
-   **使用 tnsnames.ora**。 在此方法中，连接由适配器客户端提供的 URI 包含在 tnsnames.ora 文件中指定的网络服务名称。 适配器从文件中的 net 服务名称条目中提取的连接参数，例如服务器名称、 服务名称、 端口号等。 若要使用此方法，必须配置运行 Oracle 客户端的计算机为 tnsnames.ora 文件中包括 Oracle 数据库的 net 服务名称。  
  
-   **而无需使用 tnsnames.ora**。 在此方法中，适配器客户端指定直接在连接 URI 中的连接参数。 这不需要的 net 服务名称必须包含在客户端计算机上的 tnsnames.ora 文件中。 此方法甚至不需要在客户端计算机上显示的 tnsnames.ora 文件。  
  
 有关连接 URI 的详细信息，请参阅[创建与 Oracle 数据库的连接](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)。
  
## <a name="next"></a>Next
[保护 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)