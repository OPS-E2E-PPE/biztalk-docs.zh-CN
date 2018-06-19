---
title: 使用 SQL 适配器的 SQL Server 中轮询 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c31b3cda-c05e-46db-827b-6c47a53d1a3a
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d01bc3d004da60b98e0132aa3c8e04442a45426
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225845"
---
# <a name="polling-in-sql-server-using-the-sql-adapter"></a>使用 SQL 适配器的 SQL Server 中轮询
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]允许适配器客户端接收来自 SQL Server 数据库的数据更改消息。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接收"轮询基于"消息的支持其中适配器执行指定的 SQL 语句 （SELECT 语句或存储的过程），检索或更新的数据，并在结果中提供的定期到适配器客户端时间。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开对轮询执行以下操作：  
  
-   **轮询**： 使您能够接收的 SQL Server 表或视图的定期的数据更改消息。 消息不是强的类型。  
  
-   **TypedPolling**： 用于接收从 SQL Server 数据库的强类型化消息。 如果你想要映射到任何其他架构的轮询消息中的元素，则必须使用此操作。  
  
-   **XmlPolling**。 可以使用 SELECT 语句或存储的过程，使用 FOR XML 子句和 XML 消息的形式返回数据。 此操作返回作为 XML 消息的轮询消息。  
  
     有关 FOR XML 子句的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=131402](http://go.microsoft.com/fwlink/?LinkId=131402)。  
  
 有关中的轮询的详细信息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[从通过使用 BizTalk Server 的 SQL Server 基于接收轮询的数据更改消息](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)。  
  
## <a name="polling"></a>轮询  
 典型轮询操作使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]涉及下列：  
  
1.  适配器客户端必须指定`Polling`中的入站操作作为**InboundOperationType**绑定属性。 此绑定属性的默认值是`Polling`。  
  
2.  适配器客户端必须指定 SQL 语句中的以便**PolledDataAvailableStatement**绑定属性，用于确定是否存在可用于轮询数据。 第一个返回的结果集上执行此语句的第一行的第一列包含一个整数值。 如果没有任何数据可用于轮询，返回值为 0 （零）。 如果没有可用的数据，则返回值是大于零。  
  
3.  适配器客户端必须指定一个轮询间隔以供**PollingIntervalInSeconds**绑定属性来定义的间隔中的语句**PolledDataAvailableStatement**绑定执行属性。 在每个轮询间隔结束时，执行轮询的数据可用语句，并返回的结果集。  
  
4.  适配器客户端必须为指定轮询 SQL 语句 （SELECT 语句或存储的过程） **PollingStatement**绑定属性。 如果没有可用于轮询的数据 (由**PolledDataAvailableStatement**绑定属性)，适配器执行轮询语句，以获取以及更新 （如果适用） 中的 SQL Server 数据库的数据。 当[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]用于[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，也使用同一个事务提交邮件进行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
5.  适配器客户端可以使用**PollWhileDataFound**绑定忽略轮询间隔，并持续轮询数据，和时可用的属性。  
  
6.  作为执行轮询语句的结果而返回的结果集为入站消息发送到适配器客户端。  
  
> [!NOTE]
>  XmlPolling 运算涉及轮询操作与相同的步骤。  
  
## <a name="strongly-typed-polling"></a>强类型轮询  
 典型的强类型轮询操作使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]涉及下列：  
  
1.  适配器客户端必须指定`TypedPolling`中的入站操作作为**InboundOperationType**绑定属性。 此绑定属性的默认值是`Polling`。  
  
2.  适配器客户端必须指定连接 URI 的一部分的入站的 ID。 入站的 ID 可以是任意字符串，并附加到 TypedPolling 操作以避免命名空间冲突的标准命名空间。  
  
3.  余下的步骤是步骤 2-6 中前面部分所述轮询操作列出与相同的。  
  
 有关与轮询和强类型轮询相关的绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
> [!NOTE]
>  可以作为执行轮询语句的结果而返回多个结果集。 如果结果集不包含任何行，任何消息被不发送到适配器客户端。  
  
 下图提供有关中的轮询工作流信息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 轮询工作流的两种方案图所示：  
  
1.  时的值**PollWhileDataFound**设置为"False"（默认设置）。  
  
2.  时的值**PollWhileDataFound**设置为"True"。  
  
 ![轮询工作流 &#40;PollWhileDataFound &#61;False &#41;] (../../adapters-and-accelerators/adapter-sql/media/15598c14-3a62-4b8d-90bf-84e004a386db.gif "15598c14-3a62-4b8d-90bf-84e004a386db") ![轮询工作流 &#40;PollWhileDataFound &#61;True &#41;] (../../adapters-and-accelerators/adapter-sql/media/c20535be-ea45-4456-8b62-4d4585cb1d8c.gif "c20535be-ea45-4456-8b62-4d4585cb1d8c")  
  
## <a name="differences-between-polling-and-query-notification"></a>轮询和查询通知之间的差异  
 尽管轮询和查询通知这两个入站的操作，并且 SQL Server 数据库中的数据更改通知适配器客户端下, 表列出这两者之间的一些差异。 以下差异将帮助你决定在具体取决于你的要求操作：  
  
|轮询|查询通知|  
|-------------|------------------------|  
|轮询启动的适配器。 适配器执行一个语句来验证是否数据可用于轮询，并随后通过执行轮询语句，如果某些数据可用于轮询开始轮询。|通过 SQL Server 启动的查询通知。 只需适配器发出的通知语句指示要在该语句结果集中的更改的情况下启动通知的数据库。|  
|轮询语句可用于读取或更新 SQL Server 数据库表中的数据。|可以使用查询通知语句仅具有读取 SQL Server 数据库表中的数据。|  
|轮询通知你有关已更改的实际数据信息。|查询通知只会通知有关类型的更改数据，例如插入、 更新和删除。|  
|数据更改通知取决于轮询间隔，并且在每个轮询间隔的末尾，有关数据更改的适配器客户端通知。 **提示：** 轮询可以为你提供更佳的吞吐量在数据更改发生连续，并且不希望为每项更改的和发生时要通知的情况下。 作为替代，你指定要在其后自最后一个的数据更改通知以来发生的所有更改的通知轮询间隔。|数据更改通知是即时的。|  
  
 有关中的查询通知的详细信息[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]，请参阅[使用 BizTalk server 接收 SQL 的查询通知](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)