---
title: 创建 SQL Server 连接 URI |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 688e2215-a4d8-4f55-a37c-7d91c3de080f
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6dc6ea7ef707cbb424576d532afee8038263ce0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369894"
---
# <a name="create-the-sql-server-connection-uri"></a>创建 SQL Server 连接 URI
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]连接 URI 包含适配器用来建立与 SQL Server 数据库的连接属性。 本主题介绍 SQL Server 连接 URI，并提供指向其他主题的解释如何在不同的编程方案中指定一个 URI。  
  
##  <a name="FailoverPartner"></a> SQL 适配器的连接 URI  
 典型的终结点地址 URI 在 WCF 中表示为： `scheme://hostinfoparams?query_string`，其中：  
  
- 方案为方案名称。  
  
- hostinfoparams 是建立与主机; 的连接所需的信息例如，服务器名称。  
  
- query_string 是由问号 （？） 分隔的参数的可选名称值集合。  
  
  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]连接 URI 遵循此基本格式和实现，如下所示：  
  
```  
  
mssql://[Server_Name[:Portno]]/[Database_Instance_Name]/[Database_Name]?FailoverPartner=[Partner_Server_Name]&InboundId=[Inbound_ID]  
```  
  
 其中，`mssql`是 SQL Server 连接 URI 的方案。  
  
 下表介绍了连接 URI 中包含的属性。  
  
|连接 URI 属性|Category|Description|  
|-----------------------------|--------------|-----------------|  
|[SERVER_NAME]|hostinfoparams|在其安装 SQL Server 的服务器的名称。 如果不指定一个值，适配器将假定为"localhost"的服务器名称，并建立与本地服务器上的 SQL Server 数据库的连接。|  
|[PORTNO]|hostinfoparams|建立连接的端口号。 如果不指定一个值，适配器将连接通过默认端口。|  
|[DATABASE_INSTANCE_NAME]|hostinfoparams|要连接到的 SQL Server 实例的名称。 如果不指定一个值，该适配器连接到默认数据库实例。|  
|[DATABASE_NAME]|hostinfoparams|要连接到的数据库的名称。 如果不指定一个值，该适配器连接到的默认数据库。|  
|[PARTNER_SERVER_NAME]|query_string|若要连接到主 SQL Server 数据库的故障转移 SQL Server 数据库的名称不可用。 有关高可用性的 SQL Server 方面的详细信息，请参阅[SQL Server 中的数据库镜像](https://msdn.microsoft.com/library/5h52hef8.aspx)。|  
|[INBOUND_ID]|query_string|您将添加到连接 URI，使其成为唯一标识符。 如果你想要生成的元数据，必须提供此连接参数**TypedPolling**的入站操作。 此外，在 BizTalk 应用程序中，如果有多个接收位置轮询同一数据库，入站的 ID 进行连接 URI 唯一的从而使适配器客户端可以接收来自同一个数据库上不同的轮询消息接收位置。 有关详细信息，请参阅[接收轮询消息跨多个接收端口从使用 BizTalk Server 的 SQL](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)。|  
  
> [!NOTE]
>  有关这些连接字符串属性的详细信息，请参阅[SqlConnection.ConnectionString 属性](https://msdn.microsoft.com/library/system.data.sqlclient.sqlconnection.connectionstring.aspx)。
  
## <a name="sql-server-credentials-and-the-connection-uri"></a>SQL Server 凭据和连接 URI  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不支持在连接 URI 中指定的凭据。 详细了解在使用的应用程序中指定凭据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[保护 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)。  
  
## <a name="using-special-characters-in-the-connection-uri"></a>在连接 URI 中使用特殊字符  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不支持指定连接 URI，其中含有特殊字符的任何参数值。 如果连接参数值包含特殊字符，请确保执行下列任一操作：  
  
- 如果在指定的 URI 中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则必须指定其作为-处于**URI 属性**选项卡上，即，而无需使用任何转义符。 如果指定的 URI 中直接**配置 URI**字段和连接参数包含特殊字符，则必须指定连接参数使用正确的转义字符。  
  
   例如，如果连接 URI 的名称的参数`sql server`，则必须指定其作为`sql%20server`。  
  
- 如果创建一个发送时指定的 URI 或接收端口中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中和连接参数包含特殊字符，则必须指定连接参数使用正确的转义字符。  
  
## <a name="using-the-connection-uri-to-connect-to-the-sql-server-database"></a>使用的连接 URI 连接到 SQL Server 数据库  
 下面是示例连接 URI 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
```  
mssql://sql_server/sql_server_instance//  
```  
  
 在上述示例中，"sql_server"是计算机的"sql server 实例"是计算机的要连接到的数据库实例的名称而在其安装 SQL Server 的名称。 由于不指定任何数据库名称，因此适配器将连接到的默认数据库。  
  
 以下是一个连接 URI 相同的计算机安装 SQL Server 数据库的示例[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 在此示例中，该适配器连接到数据库"my_database"本地计算机上的"sql server 实例"数据库实例。  
  
```  
mssql://localhost/sql_server_instance/my_database/  
```  
  
 在此示例中，适配器连接到本地计算机上运行的默认实例的默认数据库。  
  
```  
mssql://localhost///  
```  
  
 有关如何指定连接到 SQL Server 数据库的信息时您：  
  
- 使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，请参阅[连接到 SQL Server 在 Visual Studio 中使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md)。  
  
- 配置发送端口或接收端口 （位置） 中的 BizTalk Server 解决方案，请参阅[手动配置与 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。
  
- 编程解决方案中使用 WCF 通道模型，请参阅[创建一个通道，使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md)。  
  
- 编程解决方案中使用 WCF 服务模型，请参阅[为 SQL 适配器配置客户端绑定](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)。  
  
## <a name="see-also"></a>请参阅  
[开发 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)