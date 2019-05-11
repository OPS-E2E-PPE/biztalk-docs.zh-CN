---
title: 创建 Oracle 数据库连接 URI |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI, basic format of
- connection URI, database credentials and
- connection URI, connecting to the Oracle database
- connection URI
ms.assetid: 17d0a6d3-1b0c-43d6-a705-402c09a78ee0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 937f0fa551ff33620a75a254cc06266c704f69fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376774"
---
# <a name="create-the-oracle-database-connection-uri"></a>创建 Oracle 数据库连接 URI
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]连接 URI 包含适配器用来建立与 Oracle 数据库的连接属性。 本主题提供有关如何指定连接 URI 连接到 Oracle 数据库使用 tnsnames.ora，无需使用 tnsnames.ora 的信息。 它还提供有关使用的连接 URI 连接到 Oracle 数据库的信息。  

## <a name="connection-uri-to-connect-to-the-oracle-database-using-tnsnamesora"></a>连接连接到 Oracle 数据库使用 tnsnames.ora URI  

> [!IMPORTANT]
> - 对于这种方法，必须在计算机上的 tnsnames.ora 文件中添加 net 服务名称项，安装了适配器客户端。 有关 net 服务名称条目的详细信息，请参阅[配置 Oracle 数据库适配器的 Oracle 客户端](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)。  
>   -   由于 Oracle 客户端限制， **DataSourceName**连接 URI 中的参数 （net 服务名称） 不能包含超过 39 个字符，如果您在事务中执行的操作。 因此，请确保为指定的值**DataSourceName**参数是小于或等于 39 个字符如果您将在事务中执行的操作。  

 典型的终结点地址中的 URI[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]表示为： `scheme://userauthparams@hostinfoparams?query_string`，其中：  

- 方案为方案名称。  

- userauthparams 是终结点进行用户身份验证所需的参数名称值集合。  

- hostinfoparams 是建立与主机; 的连接所需的信息例如，路径。  

- query_string 是由问号 （？） 分隔的参数的可选名称值集合。  

  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]连接 URI 遵循此基本格式和实现，如下所示：  

```  
oracledb://User=[USER_NAME];Password=[PASSWORD]@[NET_SERVICE_NAME]?PollingId=[POLLING_ID]  
```  

 下表介绍了连接 URI 中包含的属性。  


| 连接 URI 属性 |    Category    |                                                                                                                                                                                                                                                                                                                                                                                           Description                                                                                                                                                                                                                                                                                                                                                                                            |
|-------------------------|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       [USER_NAME]       | userauthparams | 要使用 Oracle 数据库中; 上进行身份验证的用户名称例如，SCOTT。 必须设置**AcceptCredentialsInUri**属性绑定到**true**连接 URI 中指定的用户名和密码。<br /><br /> **请注意**[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将保留在打开对 Oracle 数据库的连接时输入的用户名的值的大小写。 对 Oracle 数据库用户名称是区分大小写。 应确保提供 Oracle 用户名称[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在所需的 Oracle 数据库的情况下。 通常情况下，这意味着在 SCOTT/TIGER 凭据的用户名称应为大写："SCOTT"。 |
|       [PASSWORD]        | userauthparams |                                                                                                                                要使用 Oracle 数据库中; 上进行身份验证的密码例如，TIGER。 必须设置**AcceptCredentialsInUri**属性绑定到**true**连接 URI 中指定的用户名和密码。<br /><br /> **请注意**[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将保留在打开对 Oracle 数据库的连接时输入的密码值的大小写。 对于发行版 10g 和更早版本，不区分大小写上 Oracle 系统的密码。                                                                                                                                |
|   [NET_SERVICE_NAME]    | hostinfoparams |                                                                                                                                                                            Net 服务名称在计算机上的 tnsnames.ora 文件中指定其中[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]安装。 有关 net 服务名称和 tnsnames.ora 的详细信息，请参阅[配置 Oracle 数据库适配器的 Oracle 客户端](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)。                                                                                                                                                                             |
|      [POLLING_ID]       |  query_string  |                                                                                                                                                                                                                     应由适配器添加到 POLLINGSTMT 操作的标准命名空间追加一个可选字符串。 这使您可以指定唯一的命名空间为每个轮询操作，当一个项目包含多个轮询操作时。 无需指定 PollingId 字符串，如果您的项目包含只有一个 POLLINGSTMT 操作。                                                                                                                                                                                                                      |

> [!NOTE]
>  为指定的终结点地址时，在连接 URI 中还使用查询参数[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]元数据交换客户端。  

## <a name="connection-uri-to-connect-to-the-oracle-database-without-using-tnsnamesora"></a>连接 URI，而无需使用 tnsnames.ora 连接到 Oracle 数据库  

> [!IMPORTANT]
> - 此方法时，不需要存在于客户端计算机上 tnsnames.ora 文件或实际 tnsnames.ora 文件本身中的 net 服务名称。  
>   -   如果你在事务中执行操作，则不支持这种模式的连接。 这是由于 Oracle 客户端的限制。  

 典型的终结点地址中的 URI[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]表示为： `scheme://userauthparams@hostinfoparams?query_string`，其中：  

- 方案为方案名称。  

- userauthparams 是终结点进行用户身份验证所需的参数名称值集合。  

- hostinfoparams 是建立与主机; 的连接所需的信息例如，服务器名称、 端口号，等等。  

- query_string 是由问号 （？） 分隔的参数的可选名称值集合。  

  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]连接 URI 遵循此基本格式和实现，如下所示：  

```  
oracledb://User=[USER_NAME];Password=[PASSWORD]@[SERVER_NAME]:[PORT_NUMBER]/[SERVICE_NAME]/SERVICE_TYPE]?PollingId=[POLLING_ID]  
```  

 下表介绍了连接 URI 中包含的属性。  


| 连接 URI 属性 |    Category    |                                                                                                                                                                                                                                                                                                                                                                                           Description                                                                                                                                                                                                                                                                                                                                                                                            |
|-------------------------|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       [USER_NAME]       | userauthparams | 要使用 Oracle 数据库中; 上进行身份验证的用户名称例如，SCOTT。 必须设置**AcceptCredentialsInUri**属性绑定到**true**连接 URI 中指定的用户名和密码。<br /><br /> **请注意**[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将保留在打开对 Oracle 数据库的连接时输入的用户名的值的大小写。 对 Oracle 数据库用户名称是区分大小写。 应确保提供 Oracle 用户名称[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在所需的 Oracle 数据库的情况下。 通常情况下，这意味着在 SCOTT/TIGER 凭据的用户名称应为大写："SCOTT"。 |
|       [PASSWORD]        | userauthparams |                                                                                                                                要使用 Oracle 数据库中; 上进行身份验证的密码例如，TIGER。 必须设置**AcceptCredentialsInUri**属性绑定到**true**连接 URI 中指定的用户名和密码。<br /><br /> **请注意**[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将保留在打开对 Oracle 数据库的连接时输入的密码值的大小写。 对于发行版 10g 和更早版本，不区分大小写上 Oracle 系统的密码。                                                                                                                                |
|      [SERVER_NAME]      | hostinfoparams |                                                                                                                                                                                                                                                                                                                                                          在其运行 Oracle 数据库服务器的名称。 这是必需的。                                                                                                                                                                                                                                                                                                                                                          |
|      [PORT_NUMBER]      | hostinfoparams |                                                                                                                                                                                                                                                                                                                                                Oracle Net 侦听器端口。 如果未不指定任何值，则适配器将采用默认值 1521年。                                                                                                                                                                                                                                                                                                                                                 |
|     [SERVICE_NAME]      | hostinfoparams |                                                                                                                                                                                                                                                                                                                                                                       Oracle 数据库的服务名称。 这是必需的。                                                                                                                                                                                                                                                                                                                                                                       |
|     [SERVICE_TYPE]      | hostinfoparams |                                                                                                                                                                                                                                                  Oracle 服务的类型。 可能的值为**专用**或**共享**。 专用的服务使用专用的服务器进程为只有一个用户进程提供服务。 共享的服务使用的共享的服务器进程可以可提供多个用户进程。 默认值是**专用**。                                                                                                                                                                                                                                                   |
|      [POLLING_ID]       |  query_string  |                                                                                                                                                                                                                     应由适配器添加到 POLLINGSTMT 操作的标准命名空间追加一个可选字符串。 这使您可以指定唯一的命名空间为每个轮询操作，当一个项目包含多个轮询操作时。 无需指定 PollingId 字符串，如果您的项目包含只有一个 POLLINGSTMT 操作。                                                                                                                                                                                                                      |

> [!NOTE]
>  为指定的终结点地址时，在连接 URI 中还使用查询参数[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]元数据交换客户端。  

## <a name="oracle-database-credentials-and-the-connection-uri"></a>Oracle 数据库凭据和连接 URI  
 默认情况下，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]连接 URI 中指定 Oracle 数据库凭据时，将引发异常。 这是因为这些凭据被表示为纯文本形式的连接 URI，而这会带来安全风险。 可以设置**AcceptCredentialsInUri**属性绑定到控件是否连接 URI 可以包含用于 Oracle 数据库的凭据。 如果**AcceptCredentialsInUri**属性是**false**，则[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]时引发异常的连接 URI 包含数据库的 Oracle 凭据; 如果该属性是 **，则返回 true**，不会引发异常。 有几个有限的情况，它是需要在连接 URI; 中指定凭据例如，若要接收的入站的 POLLINGSTMT 操作时使用 WCF 服务模型或 WCF 通道模型。 但是，大多数情况下，应避免提供的连接 URI 中的凭据。 有关如何更安全地提供 Oracle 数据库的凭据的详细信息，请参阅[保护 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)。  

> [!IMPORTANT]
>  由于通过在字符串中以明文形式传递凭据带来的安全风险，应避免在连接 URI 中指定 Oracle 数据库连接凭据。  

## <a name="using-reserved-characters-in-the-connection-uri"></a>在连接 URI 中使用保留的字符  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持指定连接 URI，其中含有特殊字符的任何参数值。 如果连接参数值包含特殊字符，请确保执行下列任一操作：  

- 如果在指定的 URI 中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则必须指定其作为-处于**URI 属性**选项卡上，即，而无需使用任何转义符。 如果指定的 URI 中直接**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。  

- 如果创建一个发送时指定的 URI 或接收端口中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。  

## <a name="using-the-connection-uri-to-connect-to-the-oracle-database"></a>使用的连接 URI 连接到 Oracle 数据库  
 以下是一个连接 URI 的示例为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  

|使用 tnsnames.ora|而无需使用 tnsnames.ora|  
|------------------------|--------------------------------|  
|`oracledb://ADAPTER`<br /><br /> 在此示例中，适配器是与目标 Oracle 数据库中 tnsnames.ora 的服务名称和连接信息相关联的 net 服务名称。|`oracledb://yourOracleServer:1521/yourOracleDatabaseServiceName/Dedicated`<br /><br /> 在此示例中，服务器名称是"yourOracleServer"和服务名称是"yourOracleDatabaseServiceName"。|  

 下面是连接的 POLLINGSTMT 操作 URI 的示例。 此 URI 包含 PollingId 参数来修改 POLLINGSTMT 操作的命名空间。  

|使用 tnsnames.ora|而无需使用 tnsnames.ora|  
|------------------------|--------------------------------|  
|`oracledb://ADAPTER?PollingId=MyPollingNotification1`|`oracledb://yourOracleServer:1521/yourOracleDatabaseServiceName/Dedicated? PollingId=MyPollingNotification1`|  

 上述连接 Uri，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]创建 POLLINGSTMT 操作的以下命名空间。  

```  
http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTMyPollingNotification1  
```  

 有关如何建立与 Oracle 数据库的信息时您：  

- 使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，请参阅[连接到 Oracle 数据库，在 Visual Studio 中使用使用适配器服务](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md)。  

- 配置发送端口或接收端口 （位置） 中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案，请参阅[手动配置到 Oracle 数据库适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)。  

- 编程解决方案中使用 WCF 通道模型，请参阅[创建一个通道，使用 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md)。  

- 编程解决方案中使用 WCF 服务模型，请参阅[配置客户端绑定用于 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/configure-a-client-binding-for-the-oracle-database.md)。  

- 使用 WCF ServiceModel Metadata Utility Tool (svcutil.exe)，请参阅[对 Oracle 数据库的 BizTalk 适配器使用 ServiceModel Metadata Utility Tool](../../adapters-and-accelerators/adapter-oracle-database/use-the-servicemodel-metadata-utility-with-the-oracle-db-adapter-in-biztalk.md)。  

## <a name="see-also"></a>请参阅  
[创建与 Oracle 数据库的连接](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)   
 [配置 Oracle 数据库适配器的 Oracle 客户端](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)