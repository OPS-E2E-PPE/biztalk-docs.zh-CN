---
title: "创建 SQL Server 连接 URI |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 688e2215-a4d8-4f55-a37c-7d91c3de080f
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f31b6d6919924d3bb4bb1ac6c817c3f3b3d77dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="create-the-sql-server-connection-uri"></a>创建 SQL Server 连接 URI
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]连接 URI 包含适配器用于建立与 SQL Server 数据库的连接的属性。 本主题提供有关 SQL Server 连接 URI 的信息，并提供指向其他主题的说明如何在不同的编程方案中指定一个 URI。  
  
##  <a name="FailoverPartner"></a>SQL 适配器的连接 URI  
 典型的终结点地址 URI 在 WCF 中表示为： `scheme://hostinfoparams?query_string`，其中：  
  
-   方案是方案名称。  
  
-   hostinfoparams 是建立与主机; 的连接所需的信息例如，服务器名称。  
  
-   query_string 是可选的由问号 （？） 分隔的参数名称 / 值集合。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]连接 URI 遵循此基本格式和实现，如下所示：  
  
```  
  
mssql://[Server_Name[:Portno]]/[Database_Instance_Name]/[Database_Name]?FailoverPartner=[Partner_Server_Name]&InboundId=[Inbound_ID]  
```  
  
 其中，`mssql`是 SQL Server 连接 URI 的方案。  
  
 下表介绍了连接 URI 中包含的属性。  
  
|连接 URI 属性|类别|Description|  
|-----------------------------|--------------|-----------------|  
|[SERVER_NAME]|hostinfoparams|在其上安装 SQL Server 的服务器的名称。 如果未指定一个值，该适配器假定为"localhost"的服务器名称，并建立与本地服务器上的 SQL Server 数据库的连接。|  
|[PORTNO]|hostinfoparams|建立连接的端口号。 如果未指定一个值，该适配器将连接通过默认端口。|  
|[DATABASE_INSTANCE_NAME]|hostinfoparams|要连接到的 SQL Server 实例的名称。 如果未指定一个值，该适配器将连接到默认数据库实例。|  
|[DATABASE_NAME]|hostinfoparams|要连接到的数据库的名称。 如果未指定一个值，该适配器将连接到的默认数据库。|  
|[PARTNER_SERVER_NAME]|query_string|要连接到如果主 SQL Server 数据库的故障转移 SQL Server 数据库的名称不可用。 有关与 SQL Server 的高可用性的详细信息，请参阅[SQL Server 中的数据库镜像](https://msdn.microsoft.com/library/5h52hef8.aspx)。|  
|[INBOUND_ID]|query_string|你将添加到连接 URI，以使其唯一标识符。 如果你想要生成的元数据，必须提供此连接参数**TypedPolling**入站操作。 此外，在 BizTalk 应用程序中，如果你有多个接收位置轮询同一数据库中，入站的 ID 进行连接 URI 唯一的从而支持适配器客户端接收来自上不同的同一数据库的轮询消息接收位置。 有关详细信息，请参阅[接收轮询消息跨多个接收端口从 SQL 使用 BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)。|  
  
> [!NOTE]
>  有关这些连接字符串属性的详细信息，请参阅[SqlConnection.ConnectionString 属性](https://msdn.microsoft.com/library/system.data.sqlclient.sqlconnection.connectionstring.aspx)。
  
## <a name="sql-server-credentials-and-the-connection-uri"></a>SQL Server 凭据和连接 URI  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不支持连接 URI 中指定的凭据。 有关在使用的应用程序中指定凭据的详细信息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[保护 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)。  
  
## <a name="using-special-characters-in-the-connection-uri"></a>在连接 URI 中使用特殊字符  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不支持指定的连接具有任何参数值的特殊字符的 URI。 连接参数值包含特殊字符，请确保执行下列任一操作：  
  
-   如果在指定的 URI 中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，你必须指定它们作为-处于**URI 属性**选项卡上，即，而无需使用任何转义字符。 如果你指定直接在 URI**配置 URI**字段和连接参数包含特殊字符，则必须指定连接参数使用适当的转义字符。  
  
     例如，如果连接 URI 具有名称的参数`sql server`，你必须指定其作为`sql%20server`。  
  
-   如果你创建一个发送时指定的 URI，或接收中的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，和连接参数包含特殊字符，则必须指定连接参数使用适当的转义字符。  
  
## <a name="using-the-connection-uri-to-connect-to-the-sql-server-database"></a>连接 URI 用于连接到 SQL Server 数据库  
 下面是示例连接 URI 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
```  
mssql://sql_server/sql_server_instance//  
```  
  
 在前面的示例中，"sql_server"是计算机的"sql server 实例"是计算机的要连接到的数据库实例的名称而在其安装 SQL Server 的名称。 由于未不指定任何数据库名称，该适配器将连接到的默认数据库。  
  
 以下是一个连接 URI，将 SQL Server 数据库安装在同一台计算机的示例[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 在此示例中，适配器连接到数据库"my_database"本地计算机上的"sql server 实例"数据库实例。  
  
```  
mssql://localhost/sql_server_instance/my_database/  
```  
  
 在此示例中，适配器用来连接到本地计算机上运行的默认实例的默认数据库。  
  
```  
mssql://localhost///  
```  
  
 有关如何指定与 SQL Server 的连接信息数据库时你：  
  
-   使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，请参阅[连接到使用 SQL 适配器的 Visual Studio 中的 SQL Server](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md)。  
  
-   配置发送端口或接收 BizTalk Server 解决方案中的端口 （位置），请参阅[手动配置到 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。
  
-   使用编程解决方案中的 WCF 通道模型，请参阅[创建一个通道，使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md)。  
  
-   使用 WCF 服务模型编程解决方案中，请参阅[为 SQL 适配器配置客户端绑定](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)。  
  
## <a name="see-also"></a>另请参阅  
[开发 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)