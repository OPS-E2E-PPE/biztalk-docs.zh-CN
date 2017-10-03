---
title: "了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4606f583-da74-4a26-95cb-88915ecafe37
caps.latest.revision: "43"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3d10bd82fa17501920150c6324695ae1cc9834b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties"></a>了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]呈现几个绑定属性。 通过设置这些属性，可以控制某些适配器的行为。 本部分介绍公开的绑定属性[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 它还演示如何访问它们通过使用.NET 编程或通过设置属性[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]物理端口绑定。  
  
## <a name="the-adapter-binding-properties"></a>适配器绑定属性  
 下表显示[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定属性按类别分组。 类别是指在其下每个绑定属性将显示在提供的不同应用程序可配置的适配器 （或绑定） 的对话框中的节点。  
  
|绑定属性|类别|Description|.NET 类型|  
|----------------------|--------------|-----------------|---------------|  
|**XmlStoredProcedureRootNodeName**|（对于 XML)|指定 FOR XML 子句有 SELECT 语句中的存储过程的响应架构的根节点的名称。 此根节点封装在执行此类存储的过程后从 SQL Server 接收到的 XML 响应。 必须将此根节点添加到响应架构中，主题中所述[执行存储过程具有 FOR XML 子句中使用 BizTalk Server 的 SQL Server](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-having-a-for-xml-clause-in-sql-server-using-biztalk.md)。<br /><br /> **重要说明：**执行与 FOR XML 子句的存储的过程时，必须设置此绑定属性。|string|  
|**XmlStoredProcedureRootNodeNamespace**|（对于 XML)|指定 FOR XML 子句有 SELECT 语句中的存储过程的响应架构的根节点的目标命名空间。|string|  
|**CloseTimeout**|（常规）|[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]连接关闭超时。 默认值为 1 分钟。|System.TimeSpan|  
|**名称**|（常规）|一个只读的值，返回生成的文件的名称[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]来保存[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端类。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]窗体的值通过追加"客户端"的文件名称**名称**属性。 此属性的默认值是"SqlAdapterBinding";对于此值，生成的文件将命名为"SqlAdapterBindingClient"。|string|  
|**OpenTimeout**|（常规）|指定[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]连接打开超时。 默认值为 1 分钟。<br /><br /> **重要说明：** [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]始终使用**OpenTimeout**在打开与 SQL Server 的连接时设置的连接打开超时。 适配器将忽略任何超时 (**System.TimeSpan**) 打开通信对象时传递的参数。 例如，该适配器将忽略任何传递打开通道时的超时参数。|System.TimeSpan|  
|**ReceiveTimeout**|（常规）|指定[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]消息接收超时。 从根本上来说，这意味着的最大适配器等待入站消息的时间量。 默认值为 10 分钟。<br /><br /> **重要说明：**对于如轮询的入站操作，我们建议将超时设置为最大可能的值，该值是 24.20:31:23.6470000 （24 天）。 使用的适配器时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，将超时设置为较大的值不会影响的适配器的功能。|System.TimeSpan|  
|**SendTimeout**|（常规）|指定[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]消息发送超时。 默认值为 1 分钟。|System.TimeSpan|  
|**EnableBizTalkCompatibilityMode**|BizTalk|指示适配器是否正在使用与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]或.NET 应用程序。<br /><br /> -当使用从适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]（或为适配器使用 BizTalk 项目中的 SQL 服务器上的操作生成元数据），你必须始终将属性设置为**True**。 这样可确保为 System.Data.DataSet 处于与兼容的格式生成的架构[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，否则你的 BizTalk 项目将无法编译。<br /><br /> -当使用从适配器[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]在.NET 应用程序，必须将属性设置为**False**如果你想要用作数据集的响应。 这可确保为 System.Data.DataSet 生成架构在与 WCF DataContractSerializer 兼容的格式。|bool (System.Boolean)|  
|**BatchSize**|缓冲|SQL Server 数据库中指定表或视图上多个记录插入、 更新和删除操作的批次大小。 默认值为 20。 值**BatchSize**大于 1，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]到一个调用批处理指定的数目的记录。 较高的值可能会提高性能，但会影响内存消耗。|int (System.Int32)|  
|**ChunkSize**|缓冲|指定用于设置集合 < column_name > 操作的缓冲区大小。 默认值为 4194304 个字节。 较高的值可能会提高性能，但会影响内存消耗。<br /><br /> **注意：** Set < column_name > 操作有关的详细信息，请参阅[操作对表和视图，包含大型数据类型使用的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md)。|int (System.Int32)|  
|**加密**|连接|指定适用于 SQL Server 和客户端之间的所有数据传输中 （与安装的有效证书） 的 SQL Server 是否使用 SSL 加密。 默认值是**false**。|bool (System.Boolean)|  
|**MaxConnectionPoolSize**|连接|指定的最大针对特定连接字符串连接池中允许的连接数。 默认值为 100。 此属性用于性能优化。<br /><br /> **重要说明：**必须设置**MaxConnectionPoolSize**谨慎。 如果此值设置过大，它是可能会耗尽可用，连接数。|int (System.Int32)|  
|**WorkstationId**|连接|指定连接到 SQL Server 数据库使用的工作站 （客户端计算机） 的唯一 ID [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 此属性值为绑定，如果指定，用于**工作站 ID** SqlConnection.ConnectionString 属性的关键字。 有关详细信息，请参阅[SqlConnection.ConnectionString 属性](https://msdn.microsoft.com/library/system.data.sqlclient.sqlconnection.connectionstring.aspx)。|string|  
|**EnablePerformanceCounters**|诊断|指定是否启用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]性能计数器和[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]LOB 延迟性能计数器。 默认值是**False**; 性能计数器已禁用。 LOB 延迟性能计数器测量所花费的总时间[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]中对 SQL Server 数据库进行调用。<br /><br /> 有关详细信息有关的性能计数器[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[使用性能计数器与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/use-performance-counters-with-the-sql-adapter.md)。|int (System.Int32)|  
|**InboundOperationType**|入站|指定是否想要执行**轮询**， **TypedPolling**， **XmlPolling**，或**通知**入站操作。 默认值是**轮询**。<br /><br /> 有关详细信息**轮询**， **TypedPolling**，和**XmlPolling**请参阅[进行轮询的支持](https://msdn.microsoft.com/library/dd788416.aspx)。 有关详细信息**通知**，请参阅[注意事项接收查询通知使用的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)。|枚举|  
|**UseDatabaseNameInXsdNamespace**|元数据|指定是否为一个特定的项目生成的 XSD 包含数据库名称。 将其设置为**True**包括数据库名称。 否则，将其设置为**False**。 默认值是**False**。<br /><br /> 这是单个应用程序希望在不同的数据库中执行操作上具有相同名称的项目具有不同的元数据的方案中十分有用。 如果命名空间中没有任何数据库名称，则生成的元数据将发生冲突。 设置此绑定属性可以包括数据库名称在命名空间，从而使其唯一。 下面是示例突出显示命名空间中的更改。<br /><br /> **UseDatabaseNameInXsdNamespace = False**<br /><br /> `http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee`<br /><br /> **UseDatabaseNameInXsdNamespace = True**<br /><br /> `http://schemas.microsoft.com/Sql/2008/05/TableOp/MyDatabase/dbo/Employee`<br /><br /> 请注意，当绑定属性设置为命名空间中包含的数据库名称**True**。|枚举|  
|**AllowIdentityInsert**|杂项|指定适配器是否可以在 Insert 和 Update 操作期间插入为标识列的值。 将此属性设置为**True**插入或更新为标识列的值。 否则将其设置为**False**。 默认值是**False**。<br /><br /> **注意：**将此属性设置为**True**都会转换为适配器使用"`SET IDENTITY_INSERT <table_name> ON`"。 有关详细信息，请参阅[SET IDENTITY_INSERT (Transact SQL)](https://msdn.microsoft.com/library/ms188059.aspx)。 <br /><br /> 在使用此绑定属性，你必须考虑以下几点：<br /><br /> -适配器不会验证您要传递标识列的值。 例如，如果表具有的"标识种子"设置为 100 的标识列和"标识增量"设置为 1，并且适配器客户端传递一个值，假设 95，标识列，该适配器只是将传递对此值到 SQL Server。<br /><br /> -即使你设置**AllowIdentityInsert**到**True**，它不是强制的适配器客户端请求消息中指定的标识列的值。 如果为标识列显示一个值，该适配器将其传递到 SQL Server。 如果值不存在，则 SQL Server 将插入基于标识列的规范的值。|bool (System.Boolean)|  
|**NotificationStatement**|通知 （入站）|指定的 SQL 语句 (SELECT 或 EXEC\<存储过程 >) 用于注册 SQL Server 通知。 请注意，你必须明确指定的列名称在语句中此 SELECT 语句中所示。<br /><br /> `SELECT Employee_ID,Designation FROM dbo.Employee WHERE Status=0`<br /><br /> **注意：**必须指定数据库对象的名称以及架构名称。 例如， `dbo.Employee`。<br /><br /> 仅当指定的 SQL 语句更改的结果集时，适配器从 SQL Server 获取的通知消息。|string|  
|**NotifyOnListenerStart**|通知 （入站）|指定适配器是否将通知消息发送到适配器客户端，通知的接收位置正在运行，侦听器启动时。 默认值是**True**。<br /><br /> 您收到类似于以下内容的通知消息：<br /><br /> `<?xml version="1.0" encoding="utf-8" ?> <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">   <Info>ListenerStarted</Info>    <Source>SqlBinding</Source>    <Type>Startup</Type>  </Notification>`|bool (System.Boolean)|  
|**PolledDataAvailableStatement**|轮询 （入站）|指定执行以确定任何数据是否可用于轮询的特定表中的 SQL Server 数据库的 SQL 语句。 指定的语句必须返回的结果集行和列组成。 结果集的第一个单元中的值指示适配器是否执行为指定的 SQL 语句**PollingStatement**绑定属性。 如果结果的第一个单元包含一个正值，适配器执行的轮询语句。 下面是一些你可以为此绑定属性中指定的有效语句的示例：<br /><br /> -如果在指定的 SELECT 语句：<br /><br /> `SELECT COUNT(*) from <table_name>`<br /><br /> -如果您在指定的存储的过程，你的存储的过程可能被定义为：<br /><br /> `CREATE PROCEDURE <procedure_name>  AS BEGIN      SELECT COUNT(*) FROM <table_name> END GO`<br /><br /> 或<br /><br /> `CREATE PROCEDURE <procedure_name>  AS BEGIN      DECLARE @count int      SELECT @count = SELECT(*) FROM <table_name>      SELECT @count END GO`<br /><br /> 如果你使用存储的过程，则会指定**PolledDataAvailableStatement**作为`EXEC <procedure_name>`。<br /><br /> **重要说明：**该语句指定为此绑定属性不在内执行*启动的适配器*事务，并可能会多次调用执行实际轮询语句前 （即使执行的语句指示存在可用于轮询行）。|string|  
|**PollingIntervalInSeconds**|轮询 （入站）|指定的时间间隔，以秒为单位，从该处[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行为指定的语句**PolledDataAvailableStatement**绑定属性。 默认值为 30 秒。 轮询间隔确定连续两次轮询之间的时间间隔。 如果在指定间隔内执行该语句，该适配器处于非活动状态的剩余时间的时间间隔内。|int (System.Int32)|  
|**PollingStatement**|轮询 （入站）|指定要轮询的 SQL Server 数据库表的 SQL 语句。 你可以指定简单的 SELECT 语句或存储的过程的轮询语句。 默认值为 **null**。 必须指定的值**PollingStatement**来启用轮询。 仅当没有数据可用于轮询，该域由执行轮询语句**PolledDataAvailableStatement**绑定属性。<br /><br /> 你可以指定任意数量的由分号分隔的 SQL 语句。 轮询语句可用于读取或更新 SQL Server 数据库表中的数据。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行在一个事务内的轮询语句。 当与使用该适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，同一个事务用于提交消息从 SQL Server 到 BizTalk 消息框。|string|  
|**PollWhileDataFound**|轮询 （入站）|指定是否[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]忽略轮询间隔和连续执行为指定的 SQL 语句**PolledDataAvailableStatement**绑定属性，如果数据中轮询的表。 如果表中可用的任何数据不，该适配器将恢复执行 SQL 语句按照指定的轮询间隔。 默认值是**false**。<br /><br /> 其中的轮询间隔设置为 60 秒，并且为该语句指定的方案，请考虑**PolledDataAvailableStatement**返回数据是可用于轮询。 适配器然后执行为指定的语句**PollingStatement**绑定属性。 假定该适配器需要仅 10 秒钟的时间来执行轮询语句，它现在需要等待 50 秒，然后执行**PolledDataAvailableStatement**试，然后随后执行轮询语句. 相反，若要优化的性能，你可以设置**PollWhileDataFound**属性绑定到**true** ，以便该适配器可以开始执行下一个轮询周期尽快在上一轮询周期结束。|bool (System.Boolean)|  
|**UseAmbientTransaction**|事务|指定是否[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行使用由调用方提供的事务上下文的操作。 默认值是**true**，这意味着适配器始终在事务上下文中执行操作。 如果有参与该事务的其他资源和 SQL Server 还联接该事务，事务获取提升为 MSDTC 事务中。<br /><br /> 但是，可以在你不希望在事务上下文中执行操作的适配器的方案。 例如：<br /><br /> -时执行简单的选择 SQL Server 操作数据库<br /><br /> -时指定轮询语句执行选择操作，并不涉及对表的 Delete 语句通过或通过调用存储的过程的任何更改。<br /><br /> 同时这些操作不要对数据库表进行任何更新，并且，因此，从而提升这些操作使用 MSDTC 事务可以将性能开销。 在这种情况下，你可以将绑定属性设置为**false**以便[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]没有事务的上下文中执行的操作。<br /><br /> **注意：**最好仅对未对数据库进行更改的操作未在事务上下文中执行操作是。 对于更新数据库中的数据的操作，我们建议将绑定属性设置为**true**; 否则为也可能会遇到消息丢失或重复的消息，具体取决于您执行的入站或出站操作。|bool (System.Boolean)|  
  
## <a name="how-do-i-set-sql-server-binding-properties"></a>如何设置绑定属性的 SQL Server？  
 指定连接到 SQL Server 时，你可以设置 SQL Server 绑定属性。 有关如何设置绑定属性的信息时您：  
  
-   使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，请参阅[连接到 SQL Server 使用 Windows 身份验证与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)。  
  
    > [!IMPORTANT]
    >  在使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，如果未指定的字符串类型的绑定属性的值，并且其默认值为 null，则该绑定属性将不可用绑定文件 （XML 文件） 或 app.config 文件中分别。 你必须手动添加绑定属性，并且其值在绑定文件或 app.config 文件中，如果需要。  
  
-   配置发送端口或接收 BizTalk Server 解决方案中的端口 （位置），请参阅[手动配置到 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。
  
-   使用编程解决方案中的 WCF 通道模型，请参阅[创建一个通道，使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md)。  
  
-   使用 WCF 服务模型编程解决方案中，请参阅[为 SQL 适配器配置客户端绑定](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)。  
  
## <a name="see-also"></a>另请参阅  
[开发 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)