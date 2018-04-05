---
title: Oracle 数据库适配器中接收基于轮询的数据更改消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- polling-base notification, support for
ms.assetid: 043afb88-701c-41d8-8b8e-84702bd0d984
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f234e57353d22c785dc57271add297e7a6d2c9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-polling-based-data-changed-messages-in-oracle-database-adapter"></a>Oracle 数据库适配器中接收基于轮询的数据更改消息
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]支持通过轮询 Oracle 数据库接收基于轮询的数据更改消息。 适配器将消息传送到您的应用程序：  
  
-   执行 SQL SELECT 查询以确定数据是否可用于轮询。 你可以配置执行 SQL SELECT 查询定期或连续的适配器。  
  
-   执行 SQL SELECT 查询针对 Oracle 表或视图或执行存储过程、 函数或打包的过程和函数。  
  
-   执行对 Oracle 数据库的一个可选的后轮询 PL/SQL 代码块。 若要更新目标中的查询记录上的字段或将查询的记录移到另一个表或视图，通常使用此代码块。  
  
-   在结果中返回查询结果设置通过调用 POLLINGSTMT 操作或存储的过程、 函数或打包的过程和函数作为轮询操作公开。  
  
 适配器执行所有这些操作 Oracle 事务内。  
  
 适配器还可以通过公开在同一应用程序接收多个 Oracle 的项目的数据更改消息`PollingId`连接 URI 中的参数。 此参数修改 POLLINGSTMT 操作的目标命名空间。  
  
## <a name="change-the-target-namespace-of-pollingstmt"></a>更改 POLLINGSTMT 的目标命名空间  
 你可以通过设置修改 POLLINGSTMT 操作的目标命名空间`PollingId`查询中连接 URI 的字符串参数。 如果`PollingId`中连接 URI，指定[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]追加中指定的字符串`PollingId`POLLINGSTMT 操作的默认目标命名空间的参数： `http://microsoft.lobservices.oracledb/2007/03/POLLINGSTMT`。 不修改 POLLINGSTMT 操作的消息操作。  
  
 例如，如果指定以下连接 URI: `OracleDb://User=SCOTT;Password=TIGER@Adapter?PollingId=AcctActivity`，目标命名空间将是`http:/microsoft.lobservices.oracledb/2007/03/POLLINGSTMTAcctActivity`。  
  
 通过为每个 POLLINGSTMT 操作提供唯一的命名空间，你可以在你的应用程序中接收数据更改多个 Oracle 表和视图的消息。  
  
 有关详细信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]连接 URI，请参阅[创建 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。  
  
## <a name="receive-data-changed-messages-using-binding-properties"></a>接收数据更改的消息，使用绑定属性
 你配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]以通过设置部分或全部以下绑定属性来接收数据更改消息。  
  
|绑定属性|值|默认|必需/可选|  
|----------------------|-----------|-------------|------------------------|  
|**InboundOperationType**|请确保值设置为**轮询**。|轮询|必需的。 如果未显式设置，默认值将应用。|  
|**PolledDataAvailableStatement**|指定执行，以确定任何数据是否可用于轮询的特定表的 SELECT 语句。 指定的语句必须返回的结果集行和列组成。 结果集的第一个单元中的值指示适配器是否执行指定的值**PollingStatement**绑定属性。 如果结果的第一个单元包含一个正值，适配器执行的轮询语句。 例如，将为此绑定属性有效的语句：<br /><br /> `Select * from <table_name>`<br /><br /> **注意：**您不能指定此绑定属性的存储的过程。 此外，此语句不能修改基础的 Oracle 数据库。|从双选择 1|必需的。 如果未显式设置，默认值将应用，这意味着，适配器必须继续进行而不考虑或不轮询表是否具有数据的轮询。|  
|**PollingAction**|指定轮询操作的操作。 你可以确定从元数据生成操作使用特定操作的轮询操作[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。|null|对于上表和视图使用 SELECT 语句的轮询操作可选。|  
|**PollingInterval**|设置为间隔，以秒为单位，您想要在 Oracle 数据库中查询的适配器。 此属性指定轮询间隔和轮询事务超时。值应大于执行的查询和后轮询语句 （如果指定了一个） 对 Oracle 数据库所花的时间量加上的客户端来处理查询数据并返回轮询响应消息所花费的时间量。|500|必需的。 如果未显式设置，默认值将应用。|  
|**PollingStatement**|指定以下方法之一：<br /><br /> 应对其执行 Oracle 数据库的 SQL SELECT 语句。 此语句应包含 FOR UPDATE 子句。 有关 FOR UPDATE 子句的信息，请参阅[的轮询语句中指定 FOR UPDATE 子句](#ForUpdate)本主题中更高版本。<br /><br /> -请求的存储的过程、 函数或过程或函数在你想要进行轮询一个包内的消息。|null|必需的。 设置**PollingStatement**为非 null 值可启用轮询。|  
|**PollWhileDataFound**|指定是否[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]忽略轮询间隔和持续轮询 Oracle 数据库时，如果数据中轮询的表。 如果表中可用的任何数据不，该适配器将恢复执行 SQL 语句按照指定的轮询间隔|False|必需的。 如果未显式设置，默认值将应用。|  
|**PostPollStatement**|设置为一个可选的 PL/SQL 代码块后，执行查询，但在查询之前数据返回到客户端执行适配器。|null|可选。 如果未不指定任何值，则不执行 post 轮询语句。|  
  
> [!NOTE]
>  如果你使用的 WCF 服务模型或 WCF 通道模型，你还必须设置**AcceptCredentialsInUri**绑定属性。  
  
##  <a name="ForUpdate"></a>在轮询语句中输入的更新  
 如果使用的作为轮询语句和执行影响在 SELECT 语句中指定的行后轮询语句的 SELECT 语句，你必须在轮询语句中使用 FOR UPDATE 子句。 指定 FOR UPDATE 子句可确保通过轮询语句所选择的记录将被锁定在事务处理期间并后轮询语句可以对它们执行任何所需的更新。  
  
> [!CAUTION]
>  你可以方案其中在轮询和后轮询语句之间的时间范围，更多记录添加到满足后轮询语句的条件的表中。 在这种情况下，满足条件的所有记录，以及不只是选择作为轮询语句的一部分的记录，将更新后的轮询语句。  
  
 如果未指定后期轮询语句和轮询语句不包含 FOR UPDATE 子句，则会出现以下两种情况之一：  
  
-   如果**TransactionIsolationLevel**设置为**ReadCommitted**后, 轮询查询不会更新所选的行。  
  
-   如果**TransactionIsolationLevel**设置为**Serializable**，以下面向系统异常 (**Microsoft.ServiceModel.Channels.Common.TargetSystemException**) 执行后轮询语句时将发生:"ORA 08177 无法序列化此事务的访问"。 在这种情况下，你必须设置**PollingRetryCount**绑定属性，用于定义所需的适配器重试相同的事务的次数。  
  
 有关如何设置事务的隔离级别的说明，请参阅[与 Oracle 数据库配置事务隔离级别和事务超时](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md)。  
  
 如果适配器客户端已配置为使用事务和的值，则在事务中执行的轮询和后轮询语句**UseAmbientTransaction**绑定属性设置为**True**适配器中。  
  
 具有 FOR UPDATE 选项的轮询查询的一个示例是：  
  
```  
SELECT * from EMP WHERE FLAG = 'Y' FOR UPDATE  
```  
  
### <a name="enter-a-nowait-clause-in-the-polling-statement"></a>在轮询语句中输入的 NOWAIT 子句  
 您可能必须的方案，并发线程访问表轮询，从而导致过多表中的争用。 这可能导致轮询查询才会被阻止，以在表行获取锁。 如果使用的作为轮询语句的 SELECT 语句，你可能想要在 SELECT 语句中指定 FOR UPDATE 关键字以及 NOWAIT 关键字。 这将导致轮询查询执行中的适配器上的轮询查询尝试选择行是否存在锁立即返回。 异常通常在这种情况下引发由 Oracle。 若要再次使用适配器客户端可能**PollingInterval**绑定属性指定为轮询数据的时间间隔之后适配器客户端必须重试。  
  
 具有 NOWAIT 选项的轮询查询的一个示例是：  
  
```  
SELECT * from EMP WHERE FLAG = 'Y' FOR UPDATE NOWAIT  
```  
  
### <a name="enter-a-skip-locked-clause-in-the-polling-statement"></a>在轮询语句中输入的跳过锁定子句  
 您可能必须并发线程访问轮询的表，由于锁定中轮询查询中指定的 WHERE 子句的结果集的某些行是其中方案。 例如，轮询查询从表; 返回 6 行方式由于某些其他事务已锁定 4 超出这些 6 行。 在这种情况下，你可能想要指定 FOR UPDATE 关键字，指示要尝试锁定由 WHERE 子句中，指定的行，并跳过找到已锁定所有行的数据库以及一个跳都过锁定关键字。 WHERE 子句中未锁定的行被锁定在事务处理期间，并后轮询语句可以任何所需的更新在执行，以便不会再次轮询这些行。 这可确保你无需等待以接收的轮询消息，直到所有行都指定由 WHERE 子句均已解除锁定。  
  
 跳过锁定关键字可在方案中必须用轮询数据库中的相同表的多台计算机适配器客户端。 你可以通过配置接收在该点的时间，未锁定的行由 WHERE 子句指定的基于轮询的数据更改消息的方式轮询操作负载适配器客户端之间的平衡，然后更新的行，以确保如果适配器客户端收到基于轮询的数据更改消息时，其他客户端未得到，同一消息。  
  
 轮询查询使用跳过锁定选项的一个示例是：  
  
```  
SELECT * from EMP WHERE FLAG = 'Y' FOR UPDATE SKIP LOCKED  
```  
  
## <a name="support-for-ordered-delivery-fifo"></a>对有序传递 (FIFO) 的支持  
 在生产环境中，轮询可以用于监视 Oracle 数据库中的数据更改。 这些数据更改的消息接收适配器客户端使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 根据业务方案，它可能非常重要，正确的顺序中的适配器客户端接收的数据更改的消息。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持有序传递或后进先出 (FIFO) 以维护从 Oracle 数据库接收消息的顺序。 以下是相关支持在入站方案中的先进先出的几个注意事项[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
-   如果消息所使用的业务流程，业务流程必须设置为来自的消息有序的传递[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接收端口。  
  
-   如果消息所使用的发送端口 （在基于内容的路由） 方案，必须订购发送端口传递来自的消息设置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接收端口。  
  
 WCF 自定义或 WCF OracleDB 适配器有一个属性**失败的挂起请求消息**，它指定是否挂起失败入站的处理的请求消息。 可以设置此属性上**消息**WCF 自定义或 WCF OracleDB 选项卡上接收端口下的**错误处理**部分。 下表列出了描述如何处理传入消息的方案基于是否设置此属性和消息订阅服务器 （业务流程或端口） 的状态。  
  
|Port 属性|订阅服务器中取消登记的状态|登记的过程中但已停止状态的订阅服务器|  
|-------------------|------------------------------------|----------------------------------------------|  
|**挂起失败的请求消息**未设置属性|-路由故障报告生成为挂起的 （非挂起消息）<br /><br /> -实际的消息则不会挂起<br /><br /> -Post，如获取中止事务时不执行轮询查询。 因此轮询重复并且再次提取行。<br /><br /> -在事件日志，以说明发生中报告的错误。|-不被视为"失败"。 事件日志中有任何错误消息。<br /><br /> -实际消息放入挂起 （恢复） 队列中。<br /><br /> -订阅的端口或业务流程启动时，还可以自动恢复消息。 如果在订阅服务器上设置有序的传递，则它将遵循此模式。<br /><br /> 的此外可能手动恢复消息。|  
|**挂起失败的请求消息**属性设置|-路由故障报告生成为挂起的 （非挂起消息）<br /><br /> -实际消息也会被暂停<br /><br /> -Post，如获取中止事务时不执行轮询查询。 因此轮询重复并且再次提取行。<br /><br /> -在事件日志，以说明发生中报告的错误。|-不被视为"失败"。 事件日志中有任何错误消息。<br /><br /> -实际消息放入挂起 （恢复） 队列中。<br /><br /> -订阅的端口或业务流程启动时，还可以自动恢复消息。 如果在订阅服务器上设置有序的传递，则它将遵循此模式。<br /><br /> 的此外可能手动恢复消息。|  
  
## <a name="see-also"></a>另请参阅  
[开发 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)  
 [使用 BizTalk Server 轮询 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-database-using-biztalk-server.md)   
 [使用 WCF 服务模型的 Oracle 数据库中接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-service.md)   
 [使用 WCF 通道模型的 Oracle 数据库中接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-channel.md)