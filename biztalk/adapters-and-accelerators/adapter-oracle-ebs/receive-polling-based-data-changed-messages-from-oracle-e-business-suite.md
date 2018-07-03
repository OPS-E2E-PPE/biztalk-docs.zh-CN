---
title: 从 Oracle E-business Suite 接收基于轮询的数据更改消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cbcb23d0-508d-4601-91b4-c674d76cd063
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba602119a6143aae83e72b5c230f91f33a4eb5bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977614"
---
# <a name="receive-polling-based-data-changed-messages-from-oracle-e-business-suite"></a>从 Oracle E-business Suite 接收基于轮询的数据更改消息
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]支持接收基于轮询的数据更改消息通过轮询接口表、 界面视图、 表和视图。 该适配器将消息传递给由应用程序：  

- 执行 SQL SELECT 查询来确定数据是否可用于轮询。 可以配置要定期或连续执行 SQL SELECT 查询的适配器。  

- 执行对 Oracle 表或视图的 SQL SELECT 查询或执行存储过程、 函数或封装的过程和函数。  

- Oracle E-business Suite 上执行的可选后轮询 PL/SQL 代码块。 若要更新目标中的查询记录的字段或将查询的记录移到另一个表或视图，通常使用此代码块。  

- 在结果中返回查询结果集通过调用轮询操作或存储的过程、 函数或封装的过程和函数的方式被称为轮询操作。  

  适配器将执行所有这些操作在 Oracle 事务内。  

## <a name="how-do-i-configure-the-oracle-e-business-adapter-for-receiving-data-changed-messages-using-binding-properties"></a>如何配置 Oracle E-business 适配器用于接收使用绑定属性的数据更改消息？  
 配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]以通过设置某些或所有以下绑定属性来接收数据更改消息。  


|         绑定属性         |                                                                                                                                                                                                                                                                                                                                                                                     ReplTest1                                                                                                                                                                                                                                                                                                                                                                                     | ，则“默认” |                                必需/可选                                |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------|---------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                                                                                                                                                                                                                请确保值设置为**轮询**。                                                                                                                                                                                                                                                                                                                                                                | 轮询 |         必需的。 如果未显式设置，默认值将应用。          |
| **PolledDataAvailableStatement** | 指定 SELECT 语句可确定是否可用于轮询的特定表的任何数据。 指定的语句必须返回的结果集由行和列组成。 在结果集中的第一个单元中的值指示适配器是否执行指定的值**PollingInput**属性绑定。 如果结果的第一个单元格包含一个正值，适配器将执行轮询语句。 例如，将为此绑定属性有效的语句：<br /><br /> `Select * from <table_name>`<br /><br /> **注意：** 您必须指定此绑定属性的存储的过程。 此外，此语句不能修改 Oracle E-business Suite 或基础的 Oracle 数据库中的数据。 |  null   |                                    必需的。                                    |
|        **PollingAction**         |                                                                                                                                                                                                                                                          指定轮询操作的操作。 您可以确定操作使用生成的元数据中的特定操作的轮询操作[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。                                                                                                                                                                                                                                                          |  null   | 可选的表和视图使用 SELECT 语句轮询操作。 |
|         **PollingInput**         |                                                                                                                                                       指定以下任一操作：<br /><br /> 对 Oracle E-business Suite 应执行的 SQL SELECT 语句。 此语句应包含 FOR UPDATE 子句。 在 FOR UPDATE 子句有关的信息，请参阅[轮询语句中指定 FOR UPDATE 子句](#ForUpdate)本主题中更高版本。<br /><br /> -请求消息的存储的过程、 函数或过程或想要轮询的包中的函数。                                                                                                                                                       |  null   |     必需的。 设置**PollingInput**为非 null 值可启用轮询。     |
|       **PollingInterval**        |                                                                                                                                                       设置的时间间隔，以秒为单位，要查询 Oracle E-business Suite 适配器。 此属性指定的轮询间隔和轮询事务超时。值应大于 （如果已指定） 上 Oracle E-business Suite 中执行查询和轮询后语句所需的时间量以及客户端处理的查询数据，并返回轮询的响应消息所需的时间量。                                                                                                                                                       |   30    |         必需的。 如果未显式设置，默认值将应用。          |
|      **PollWhileDataFound**      |                                                                                                                                                                                                      指定是否[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]忽略的轮询间隔，并持续轮询 Oracle E-business Suite，如果数据是可用的轮询的表。 如果表中有任何数据，不则适配器将恢复执行 SQL 语句按照指定的轮询间隔                                                                                                                                                                                                      |  False  |         必需的。 如果未显式设置，默认值将应用。          |
|      **PostPollStatement**       |                                                                                                                                                                                                                                                                                                            设置为执行查询，但在查询前先数据返回到客户端后，适配器执行的可选 PL/SQL 代码块。                                                                                                                                                                                                                                                                                                            |  null   |   可选。 如果未不指定任何值，不执行轮询后语句。    |

> [!NOTE]
>  如果使用 WCF 服务模型或 WCF 通道模型，则还必须设置**AcceptCredentialsInUri**属性绑定。  

##  <a name="ForUpdate"></a> 指定一个 FOR 更新轮询语句中的子句  
 如果使用的 SELECT 语句作为轮询语句和执行轮询后语句影响的 SELECT 语句中指定的行，必须在轮询语句中使用 FOR UPDATE 子句。 指定 FOR UPDATE 子句可确保由轮询语句所选择的记录将被锁定在事务期间并后轮询语句可以对它们执行任何所需的更新。  

> [!CAUTION]
>  可以在此处的轮询和轮询后语句之间的时间范围有方案，对符合条件后轮询语句的表添加更多的记录。 在这种情况下，满足条件的所有记录并不只是作为轮询语句的一部分选择的记录，将更新后的轮询语句。  

 如果未指定后期轮询语句和轮询语句不包含 FOR UPDATE 子句，则会遇到以下两种情况之一：  

- 如果**TransactionIsolationLevel**设置为**ReadCommitted**后, 轮询查询将不会更新所选的行。  

- 如果**TransactionIsolationLevel**设置为**Serializable**，以下目标的系统异常 (**Microsoft.ServiceModel.Channels.Common.TargetSystemException**) 执行轮询后语句时，将发生:"ora-08177 无法序列化此事务的访问权限"。 在这种情况下，必须设置**PollingRetryCount**绑定属性可以定义你想要重试同一事务的适配器的次数。  

  有关如何设置事务隔离级别的说明，请参阅[与 Oracle E-business Suite 中配置事务隔离级别和事务超时](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)。  

  如果适配器客户端已配置为使用事务和的值在事务中执行的轮询和轮询后语句**UseAmbientTransaction**绑定属性设置为**True**适配器中。  

  轮询查询使用 FOR UPDATE 选项的一个示例是：  

```  
SELECT * from EMP WHERE FLAG = 'Y' FOR UPDATE  
```  

### <a name="specifying-a-nowait-clause-in-the-polling-statement"></a>在轮询语句中指定 NOWAIT 子句  
 可能有的并发线程访问要轮询的表的情况下导致过多争用的表。 这可能会导致轮询查询才会被阻止，若要获取表行的锁。 如果使用的 SELECT 语句的轮询语句时，可能想要在 SELECT 语句中指定 FOR UPDATE 关键字 NOWAIT 关键字。 这会导致适配器立即返回而轮询查询尝试选择的行上是否存在锁内执行轮询查询。 异常通常在这种情况下引发由 Oracle。 若要再次使用适配器客户端可能**PollingInterval**绑定属性来指定用于轮询数据的时间间隔之后适配器客户端必须重试。  

 轮询查询使用 NOWAIT 选项的一个示例是：  

```  
SELECT * from EMP WHERE FLAG = 'Y' FOR UPDATE NOWAIT  
```  

### <a name="specifying-a-skip-locked-clause-in-the-polling-statement"></a>在轮询语句中指定的跳过已锁定子句  
 您可能因访问轮询的表的并发线程，而锁定中轮询查询中指定的 WHERE 子句的结果集的某些行是其中的方案。 例如，轮询查询返回 6 行表中;利用这些 6 行 4 为由于某些其他事务已锁定。 在这种情况下，你可能想要指定 FOR UPDATE 关键字，指示要尝试锁定由 WHERE 子句中，指定的行，并跳过任何找到已锁定的行的数据库以及一个跳过已锁定关键字。 在事务期间锁定 WHERE 子句中未锁定的行和后轮询语句可以执行任何所需的更新它们，以便这些行都不被再次轮询。 这可确保不需要等待接收轮询消息，直到所有的行指定由 WHERE 子句不会被锁定。  

 跳过锁定关键字是在其中轮询数据库中的同一个表的多台计算机具有适配器客户端方案中非常有用。 可以通过在接收基于轮询的数据更改消息的不会被锁定在该点的时间，由 WHERE 子句指定行的这样一种方式中配置轮询操作进行负载均衡在适配器客户端之间，然后更新的行，以确保如果适配器客户端接收基于轮询的数据更改消息，其他客户端不会收到相同的消息。  

 轮询查询跳过锁定选项的一个示例是：  

```  
SELECT * from EMP WHERE FLAG = 'Y' FOR UPDATE SKIP LOCKED  
```  

## <a name="support-for-ordered-delivery-fifo"></a>按序送达 (FIFO) 的的支持  
 在生产环境中，轮询可以用于监视 Oracle E-business Suite 中的数据更改。 这些数据更改消息接收适配器客户端使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 根据业务方案，它可能很关键，正确的顺序中的适配器客户端接收数据更改消息。  

 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持按序传递扩展插件或第一个先出 (FIFO) 来维护从 Oracle E-business Suite 接收消息的顺序。 此处需注意以下事项相关支持在入站方案中的先进先出[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  

- 如果消息由业务流程，该业务流程必须设置为从传入的消息按序的送达[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接收端口。  

- 如果消息由发送端口 （在基于内容的路由） 方案中，发送端口必须具有按序送达设置为从传入的消息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接收端口。  

  WCF 自定义或 Wcf-oracleebs 适配器具有的属性**失败时挂起请求消息**，指定是否挂起入站的处理失败的请求消息。 在上设置此属性**消息**选项卡上的 WCF 自定义或 WCF OracleEBS 接收端口下的**错误处理**部分。 下表列出了描述如何处理传入消息的方案基于是否设置此属性和消息订阅者 （业务流程或端口） 的状态。  

|WCF 自定义端口属性|订阅服务器中已取消登记状态|已登记中但已停止状态的订阅服务器|  
|-------------------------------|------------------------------------|----------------------------------------------|  
|**在失败时挂起请求消息**未设置属性|的挂起 （不可恢复消息） 作为生成路由故障报告<br /><br /> -实际的消息不会挂起<br /><br /> -Post，如获取中止事务时不执行轮询查询。 因此轮询重复并再次提取行。<br /><br /> -报告在事件日志以内容描述已发生的错误。|-不被视为"失败"。 事件日志中没有任何错误消息。<br /><br /> -实际的消息放入挂起 （可恢复） 队列。<br /><br /> -订阅端口或业务流程启动时，还可以自动恢复消息。 如果在订阅服务器上设置按序的送达，则它会执行。<br /><br /> 的此外可以手动恢复消息。|  
|**在失败时挂起请求消息**属性设置|的挂起 （不可恢复消息） 作为生成路由故障报告<br /><br /> -实际的消息也会被暂停<br /><br /> -Post，如获取中止事务时不执行轮询查询。 因此轮询重复并再次提取行。<br /><br /> -报告在事件日志以内容描述已发生的错误。|-不被视为"失败"。 事件日志中没有任何错误消息。<br /><br /> -实际的消息放入挂起 （可恢复） 队列。<br /><br /> -订阅端口或业务流程启动时，还可以自动恢复消息。 如果在订阅服务器上设置按序的送达，则它会执行。<br /><br /> 的此外可以手动恢复消息。|  

## <a name="see-also"></a>请参阅  
 [开发活动](../../esb-toolkit/development-activities.md)   
 [使用 BizTalk Server 轮询 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-biztalk-server.md)