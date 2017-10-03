---
title: "创建 Oracle 数据库连接 URI |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connection URI, basic format of
- connection URI, database credentials and
- connection URI, connecting to the Oracle database
- connection URI
ms.assetid: 17d0a6d3-1b0c-43d6-a705-402c09a78ee0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45f7b0fcc0c83bd4a844ac1a83488e1a3e8d9a65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="create-the-oracle-database-connection-uri"></a>创建 Oracle 数据库连接 URI
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]连接 URI 包含适配器用于建立与 Oracle 数据库的连接的属性。 本主题提供有关如何指定要连接到 Oracle 数据库使用 tnsnames.ora 和不使用 tnsnames.ora URI 的连接信息。 它还提供有关使用连接 URI 来连接到 Oracle 数据库的信息。  
  
## <a name="connection-uri-to-connect-to-the-oracle-database-using-tnsnamesora"></a>连接要连接到使用 tnsnames.ora Oracle 数据库 URI  
  
> [!IMPORTANT]
>  -   有关此方法，你必须安装了适配器客户端，在计算机上的 tnsnames.ora 文件中添加 net 服务名称条目。 有关 net 服务名称条目的详细信息，请参阅[配置 Oracle 客户端为 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)。  
> -   由于 Oracle 客户端存在的限制， **DataSourceName**连接 URI 中的参数 （net 服务名称） 不能包含超过 39 个字符，如果你在事务中执行操作。 因此，请确保为指定的值**DataSourceName**参数是否小于或等于 39 个字符如果你将在事务中执行操作。  
  
 典型的终结点地址 URI 中的[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]表示为： `scheme://userauthparams@hostinfoparams?query_string`，其中：  
  
-   方案是方案名称。  
  
-   userauthparams 是终结点进行用户身份验证所需的参数名称 / 值集合。  
  
-   hostinfoparams 是建立与主机; 的连接所需的信息例如，路径。  
  
-   query_string 是可选的由问号 （？） 分隔的参数名称 / 值集合。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]连接 URI 遵循此基本格式和实现，如下所示：  
  
```  
oracledb://User=[USER_NAME];Password=[PASSWORD]@[NET_SERVICE_NAME]?PollingId=[POLLING_ID]  
```  
  
 下表介绍了连接 URI 中包含的属性。  
  
|连接 URI 属性|类别|Description|  
|-----------------------------|--------------|-----------------|  
|[用户名]|userauthparams|要使用 Oracle 数据库中; 上进行身份验证的用户名称例如，SCOTT。 必须设置**AcceptCredentialsInUri**属性绑定到**true**在连接 URI 中指定用户名和密码。<br /><br /> **请注意**[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]保留在打开对 Oracle 数据库的连接时输入的用户名的值的大小写。 对 Oracle 数据库的用户名称是区分大小写。 您应该确保你提供到的 Oracle 用户名[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在 Oracle 数据库所需的情况下。 通常，这意味着在 SCOTT/TIGER 凭据的用户名称应为大写形式:"SCOTT"。|  
|[PASSWORD]|userauthparams|用于 Oracle 数据库中; 上进行身份验证的密码例如，TIGER。 必须设置**AcceptCredentialsInUri**属性绑定到**true**在连接 URI 中指定用户名和密码。<br /><br /> **请注意**[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]保留在打开对 Oracle 数据库的连接时输入的密码的值的大小写。 对于发行版 10g 和更早版本，Oracle 系统上的密码是不区分大小写。|  
|[NET_SERVICE_NAME]|hostinfoparams|在计算机上的 tnsnames.ora 文件中指定的网络服务名称其中[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]安装。 有关 net 服务名称和 tnsnames.ora 的详细信息，请参阅[配置 Oracle 客户端为 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)。|  
|[POLLING_ID]|query_string|应通过 POLLINGSTMT 操作的标准命名空间的适配器将追加一个可选的字符串。 这使您可以指定唯一的命名空间为每个轮询操作何时项目包含多个轮询操作。 无需指定 PollingId 字符串，如果你的项目包含只需要一个 POLLINGSTMT 操作。|  
  
> [!NOTE]
>  为指定终结点地址时，查询参数也用在连接 URI[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]元数据交换客户端。  
  
## <a name="connection-uri-to-connect-to-the-oracle-database-without-using-tnsnamesora"></a>连接 URI，而无需使用 tnsnames.ora 连接到 Oracle 数据库  
  
> [!IMPORTANT]
>  -   此方法时，不需要存在于客户端计算机上 tnsnames.ora 文件中或实际 tnsnames.ora 文件本身中的 net 服务名称。  
> -   如果你在事务中执行操作，则不支持这种模式的连接。 这是因为 Oracle 客户端的限制。  
  
 典型的终结点地址 URI 中的[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]表示为： `scheme://userauthparams@hostinfoparams?query_string`，其中：  
  
-   方案是方案名称。  
  
-   userauthparams 是终结点进行用户身份验证所需的参数名称 / 值集合。  
  
-   hostinfoparams 是建立与主机; 的连接所需的信息例如，服务器名称、 端口号，等等。  
  
-   query_string 是可选的由问号 （？） 分隔的参数名称 / 值集合。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]连接 URI 遵循此基本格式和实现，如下所示：  
  
```  
oracledb://User=[USER_NAME];Password=[PASSWORD]@[SERVER_NAME]:[PORT_NUMBER]/[SERVICE_NAME]/SERVICE_TYPE]?PollingId=[POLLING_ID]  
```  
  
 下表介绍了连接 URI 中包含的属性。  
  
|连接 URI 属性|类别|Description|  
|-----------------------------|--------------|-----------------|  
|[用户名]|userauthparams|要使用 Oracle 数据库中; 上进行身份验证的用户名称例如，SCOTT。 必须设置**AcceptCredentialsInUri**属性绑定到**true**在连接 URI 中指定用户名和密码。<br /><br /> **请注意**[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]保留在打开对 Oracle 数据库的连接时输入的用户名的值的大小写。 对 Oracle 数据库的用户名称是区分大小写。 您应该确保你提供到的 Oracle 用户名[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在 Oracle 数据库所需的情况下。 通常，这意味着在 SCOTT/TIGER 凭据的用户名称应为大写形式:"SCOTT"。|  
|[PASSWORD]|userauthparams|用于 Oracle 数据库中; 上进行身份验证的密码例如，TIGER。 必须设置**AcceptCredentialsInUri**属性绑定到**true**在连接 URI 中指定用户名和密码。<br /><br /> **请注意**[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]保留在打开对 Oracle 数据库的连接时输入的密码的值的大小写。 对于发行版 10g 和更早版本，Oracle 系统上的密码是不区分大小写。|  
|[SERVER_NAME]|hostinfoparams|在其上运行 Oracle 数据库的服务器的名称。 必须设置此项。|  
|[PORT_NUMBER]|hostinfoparams|Oracle Net 侦听器端口。 如果未不指定任何值，该适配器将采用默认值 1521年。|  
|[SERVICE_NAME]|hostinfoparams|Oracle 数据库服务名称。 必须设置此项。|  
|[SERVICE_TYPE]|hostinfoparams|Oracle 服务的类型。 可能的值为**专用**或**共享**。 专用的服务使用专用的服务器进程为只有一个用户进程提供服务。 共享的服务使用的共享的服务器进程可以中可用于满足多个用户进程。 默认值是**专用**。|  
|[POLLING_ID]|query_string|应通过 POLLINGSTMT 操作的标准命名空间的适配器将追加一个可选的字符串。 这使您可以指定唯一的命名空间为每个轮询操作何时项目包含多个轮询操作。 无需指定 PollingId 字符串，如果你的项目包含只需要一个 POLLINGSTMT 操作。|  
  
> [!NOTE]
>  为指定终结点地址时，查询参数也用在连接 URI[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]元数据交换客户端。  
  
## <a name="oracle-database-credentials-and-the-connection-uri"></a>Oracle 数据库凭据和连接 URI  
 默认情况下，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]连接 URI 中指定 Oracle 数据库凭据时将引发异常。 这是因为这些凭据被表示为纯文本格式连接 URI，而这会带来安全风险。 你可以设置**AcceptCredentialsInUri**连接 URI 可以包含用于 Oracle 数据库的凭据是否将属性绑定到控件。 如果**AcceptCredentialsInUri**属性是**false**、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]引发异常，如果连接 URI 包含 Oracle 数据库凭据; 如果属性是**true**，不会引发异常。 有几个有限的情况下它是需要在连接 URI; 中指定凭据例如，若要接收入站的 POLLINGSTMT 操作时使用 WCF 服务模型或 WCF 通道模型。 但是，对于大多数情况下，应避免提供连接 URI 中的凭据。 有关如何更安全地提供 Oracle 数据库的凭据的详细信息，请参阅[保护 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)。  
  
> [!IMPORTANT]
>  由于为纯文本字符串中传递凭据所带来安全风险，应避免在连接 URI 中指定 Oracle 数据库连接凭据。  
  
## <a name="using-reserved-characters-in-the-connection-uri"></a>在连接 URI 中使用保留的字符  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持指定的连接具有任何参数值的特殊字符的 URI。 连接参数值包含特殊字符，请确保执行下列任一操作：  
  
-   如果在指定的 URI 中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，你必须指定它们作为-处于**URI 属性**选项卡上，即，而无需使用任何转义字符。 如果你指定直接在 URI**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用适当的转义字符。  
  
-   如果你创建一个发送时指定的 URI，或接收中的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，和连接参数包含保留的字符，则必须指定连接参数使用适当的转义字符。  
  
## <a name="using-the-connection-uri-to-connect-to-the-oracle-database"></a>使用连接 URI 来连接到 Oracle 数据库  
 以下是一个连接 URI 的示例为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
|使用 tnsnames.ora|而无需使用 tnsnames.ora|  
|------------------------|--------------------------------|  
|`oracledb://ADAPTER`<br /><br /> 在此示例中，适配器是与 tnsnames.ora 中的目标 Oracle 数据库的服务名称和连接信息相关联的 net 服务名称。|`oracledb://yourOracleServer:1521/yourOracleDatabaseServiceName/Dedicated`<br /><br /> 在此示例中，服务器名称是"yourOracleServer"和服务名称是"yourOracleDatabaseServiceName"。|  
  
 下面是连接的 POLLINGSTMT 操作 URI 的示例。 此 URI 包含 PollingId 参数来修改 POLLINGSTMT 操作的命名空间。  
  
|使用 tnsnames.ora|而无需使用 tnsnames.ora|  
|------------------------|--------------------------------|  
|`oracledb://ADAPTER?PollingId=MyPollingNotification1`|`oracledb://yourOracleServer:1521/yourOracleDatabaseServiceName/Dedicated? PollingId=MyPollingNotification1`|  
  
 为上述连接 Uri，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]创建 POLLINGSTMT 操作的以下命名空间。  
  
```  
http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTMyPollingNotification1  
```  
  
 有关如何建立的连接到 Oracle 数据库时你：  
  
-   使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，请参阅[连接到 Visual Studio 使用使用适配器服务中的 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md)。  
  
-   配置发送端口或接收端口 （位置） 中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案，请参阅[手动配置到 Oracle 数据库适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)。  
  
-   使用编程解决方案中的 WCF 通道模型，请参阅[创建一个通道，使用 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md)。  
  
-   使用 WCF 服务模型编程解决方案中，请参阅[配置客户端绑定用于 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/configure-a-client-binding-for-the-oracle-database.md)。  
  
-   使用 WCF ServiceModel 元数据实用工具 (svcutil.exe)，请参阅[ServiceModel 元数据实用工具使用 BizTalk 适配器将用于 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/use-the-servicemodel-metadata-utility-with-the-oracle-db-adapter-in-biztalk.md)。  
  
## <a name="see-also"></a>另请参阅  
[创建与 Oracle 数据库的连接](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)   
 [配置 Oracle 数据库适配器 Oracle 客户端](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)