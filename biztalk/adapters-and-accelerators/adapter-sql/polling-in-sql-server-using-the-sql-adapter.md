---
title: 在使用 SQL 适配器的 SQL Server 中轮询 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2019
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c31b3cda-c05e-46db-827b-6c47a53d1a3a
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia,niklase
manager: anneta
ms.openlocfilehash: 80e9251babad12915ce9d9f1ad7662ec90db4eff
ms.sourcegitcommit: 85e827c42f193e44ca8b5b8d78d6f8b8ac686f1e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58764561"
---
# <a name="polling-in-sql-server-using-the-sql-adapter"></a>在使用 SQL 适配器的 SQL Server 中轮询
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] 允许适配器客户端接收来自 SQL Server 数据库的数据更改消息。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]支持接收"基于轮询的"消息其中适配器执行指定的 SQL 语句 （SELECT 语句或存储的过程），检索或更新的数据，并按固定间隔的适配器客户端提供的结果时间。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开的轮询的以下操作：  
  
- **轮询**:可以接收定期的数据更改消息的 SQL Server 表或视图。 消息不是强的类型。  
  
- **TypedPolling**:可以接收来自 SQL Server 数据库的强类型化消息。 如果你想要将轮询消息中的元素映射到任何其他架构，则必须使用此操作。  
  
- **XmlPolling**。 可以使用 SELECT 语句或存储的过程使用 FOR XML 子句，并以 XML 消息形式返回数据。 此操作将返回作为 XML 消息轮询消息。  
  
   有关 FOR XML 子句的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=131402 ](http://go.microsoft.com/fwlink/?LinkId=131402)。  
  
  详细了解在轮询[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[从 SQL Server 使用 BizTalk server 基于接收轮询的数据更改消息](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)。  
  
## <a name="polling"></a>轮询  
 典型轮询操作使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]涉及以下：  
  
1. 适配器客户端必须指定`Polling`中的入站操作**InboundOperationType**属性绑定。 此绑定属性的默认值是`Polling`。  
  
2. 适配器客户端必须指定 SQL 语句中的以便**PolledDataAvailableStatement**绑定属性，用于确定是否存在可用于轮询数据。 第一个返回的结果集上执行该语句的第一行的第一列包含一个整数值。 如果没有可用于轮询的数据，返回值为 0 （零）。 如果没有可用的数据，则返回值是大于零。  
  
3. 适配器客户端必须指定为一个轮询间隔**PollingIntervalInSeconds**绑定属性来定义的时间间隔中的语句**PolledDataAvailableStatement**绑定执行属性。 在每个轮询间隔结束时，执行轮询的数据可用语句，并返回的结果集。  
  
4. 适配器客户端必须为指定的轮询 SQL 语句 （SELECT 语句或存储的过程） **PollingStatement**属性绑定。 如果没有可用于轮询的数据 (由**PolledDataAvailableStatement**属性绑定)，适配器将执行轮询语句来获取和更新 （如果适用） SQL Server 数据库中的数据。 当[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]用于[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，在同一个事务还用于将消息提交给[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
5. 适配器客户端可以使用**PollWhileDataFound**属性要忽略的轮询间隔，并连续轮询数据，以及可用时绑定。  
  
6. 作为执行轮询语句的结果而返回的结果集为入站消息发送到适配器客户端。  

> [!NOTE]
>  当**UseAmbientTransaction**设置为 False， **PolledDataAvailableStatement**不调用。 相反，适配器直接调用**PollingStatement**。

> [!NOTE]
>  XmlPolling 操作涉及到与轮询操作相同的步骤。  
  
## <a name="strongly-typed-polling"></a>强类型轮询  
 典型的强类型轮询操作使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]涉及以下：  
  
1. 适配器客户端必须指定`TypedPolling`中的入站操作**InboundOperationType**属性绑定。 此绑定属性的默认值是`Polling`。  
  
2. 适配器客户端必须指定连接 URI 的一部分的入站的 ID。 入站的 ID 可以是任意字符串，并追加到 TypedPolling 操作以避免命名空间冲突的标准命名空间。  
  
3. 步骤 2 – 6 中前面部分中描述的轮询操作列出与相同的剩余步骤。  
  
   有关与轮询和强类型轮询的绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
> [!NOTE]
>  由于执行轮询语句可以返回多个结果集。 如果结果集不包含任何行，任何消息都不发送到适配器客户端。  
  
 下图提供了有关中的轮询工作流信息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 轮询工作流的两种方案是所示：  
  
1. 时的值**PollWhileDataFound**设置为"False"（默认设置）。  
  
2. 时的值**PollWhileDataFound**设置为"True。  
  
   ![轮询工作流&#40;PollWhileDataFound &#61; False&#41;](../../adapters-and-accelerators/adapter-sql/media/15598c14-3a62-4b8d-90bf-84e004a386db.gif "15598c14-3a62-4b8d-90bf-84e004a386db") ![轮询工作流&#40;PollWhileDataFound &#61; True&#41; ](../../adapters-and-accelerators/adapter-sql/media/c20535be-ea45-4456-8b62-4d4585cb1d8c.gif "c20535be-ea45-4456-8b62-4d4585cb1d8c")  
  
## <a name="differences-between-polling-and-query-notification"></a>轮询查询通知之间的差异  
 尽管轮询和查询通知是这两个入站的操作，并在 SQL Server 数据库中的数据更改通知适配器客户端下, 表列出了两者之间的一些差异。 以下差异将帮助你决定具体取决于您的要求操作：  
  
|轮询|查询通知|  
|-------------|------------------------|  
|由适配器启动轮询。 适配器执行语句，以验证是否可用于轮询，然后通过执行轮询语句，如果某些数据可用于轮询启动轮询数据。|查询通知是由 SQL Server 启动。 只需在适配器发出的通知语句指示要在没有语句的结果集中的更改的情况下启动通知的数据库。|  
|轮询语句可用于读取或更新 SQL Server 数据库表中的数据。|可以使用查询通知语句仅读取 SQL Server 数据库表中的数据。|  
|轮询通知您已更改的实际数据。|查询通知只会通知有关类型的更改数据，例如插入、 更新和删除。|  
|数据更改通知取决于轮询间隔，并且适配器客户端将每个轮询间隔结束时通知数据更改。 **提示：** 轮询可以提供更好的吞吐量中情况下，数据更改发生的连续，并且不希望为每个更改的和发生时收到通知。 相反，您指定要在其后自上次数据更改通知以来已发生的所有更改的通知轮询间隔。|数据更改通知是瞬间完成的。|  
  
 有关详细信息中的查询通知[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]，请参阅[通过使用 BizTalk Server 接收 SQL 查询通知](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)
