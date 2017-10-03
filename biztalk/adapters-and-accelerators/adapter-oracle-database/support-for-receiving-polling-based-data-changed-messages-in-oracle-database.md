---
title: "支持 Oracle 数据库中接收基于轮询的数据更改消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- notifications, polling-based
- post-polling
- POLLINGSTMT
- polling interval
- polling
ms.assetid: 9ff29d3f-ebb1-4d82-9106-150f939cbd9e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d8a29901672ba11f3ac48220f7096b2c355fc2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="support-for-receiving-polling-based-data-changed-messages-in-oracle-database"></a>支持 Oracle 数据库中接收基于轮询的数据更改消息
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]启用客户端程序来告知他们对 Oracle 数据库中存储的数据的更改的 Oracle 数据库从接收消息。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接收其中适配器执行指定的 SELECT 查询、 存储的过程、 函数或过程或函数在一个包内的"轮询基于"消息的支持检索数据，然后将提供给常规的客户端的结果时间间隔。 若要启用此选项，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开 POLLINGSTMT 操作。 此外，所有存储的过程、 函数和过程和函数包内的作为进行轮询的入站操作公开。  
  
 适配器提供轮询 Oracle 数据库的两种的方法：  
  
-   **使用 SELECT 语句**。 你可以指定要轮询的表和视图的 Oracle 数据库中的简单 SELECT 语句。 适配器执行 SELECT 语句指定时间间隔，并将结果返回给适配器客户端。  
  
-   **使用存储的过程、 函数或过程或函数在一个包内的**。 你可以指定存储的过程、 函数或过程或函数在包轮询 Oracle 数据库中。 适配器在指定的时间间隔执行的请求消息，并将结果返回给适配器客户端。  
  
## <a name="polling-operation-workflow"></a>轮询操作工作流  
 典型轮询操作使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]涉及下列：  
  
1.  适配器客户端必须指定**轮询**中的入站操作作为**InboundOperationType**绑定属性。 此绑定属性的默认值是**轮询**。  
  
2.  适配器客户端必须指定 SELECT 语句，以**PolledDataAvailableStatement**绑定属性来确定是否存在可用于轮询数据。 在执行此语句时，如果返回的结果集的第一行的第一列包含正整数值，则日期可用于轮询。 默认情况下，此绑定属性的值设置为`Select 1 FROM DUAL`，这表明是否，适配器必须继续而不考虑轮询表是否具有数据的轮询。  
  
3.  适配器客户端必须指定一个轮询间隔以供**PollingInterval**绑定属性来定义以秒为单位语句中指定的间隔**PolledDataAvailableStatement**执行绑定属性。 在每个轮询间隔结束时，执行轮询的数据可用语句，并返回的结果集。  
  
4.  适配器客户端必须指定 SELECT 语句或存储的过程作为**PollingStatement**绑定属性。  
  
    -   如果你想要轮询的表或视图，则必须指定此绑定属性中的 SELECT 查询。  
  
    -   如果你想要轮询使用存储的过程、 函数或过程或函数在一个包内的，你必须在绑定属性中指定相应的操作的整个请求消息。  
  
     中的语句**PollingStatement**仅当没有数据可用于轮询，它由绑定属性执行**PolledDataAvailableStatement**步骤 1 中的绑定属性。  
  
5.  适配器客户端必须指定中的轮询操作的一项操作**PollingAction**绑定属性。 针对特定操作的轮询操作由使用适配器服务外接程序使用的操作生成的元数据。  
  
    > [!NOTE]
    >  如果轮询表或视图使用 SELECT 语句中的**PollingStatement**绑定属性，则你不需要指定任何值**PollingAction**绑定属性。 默认值，为 Null，在这种情况下传递。  
  
6.  适配器客户端可以使用**PollWhileDataFound**绑定忽略轮询间隔，并持续轮询数据，和时可用的属性。  
  
    > [!IMPORTANT]
    >  如果你设置的值**PollWhileDataFound**绑定属性为 True，适配器客户端持续轮询数据从 Oracle 和进程中打开和关闭连接到 Oracle 数据库在循环中。 如 ODP.NET 打开连接的速率大于正在关闭的连接，连接获取耗尽一段时间后，将引发异常。 作为替代，请确保值**UseOracleConnectionPool**设置为 True，和中提到了适当的值**IncrPoolSize**绑定属性控制的连接数可以打开适配器客户端。  
  
7.  适配器客户端可以为指定的后轮询语句，Oracle PL/SQL 块**PostPollStatement**绑定属性。 此绑定属性中指定的语句执行的语句中指定后**PollingStatement**绑定属性执行。  
  
 适配器在事务中包装轮询语句和后轮询语句和事务超时值设置为指定的值为**PollingInterval**绑定属性。 因此，很重要，若要指定超时值大于或等于需处理传入消息并发送答复的时间。 如果要使用的消息或执行后轮询查询的客户端程序所需的时间超过超时值，则回滚事务。 如果所用的时间小于超时值，该适配器将提交事务，并"休眠"在执行下一次轮询之前轮询的剩余时间。  
  
 适配器禁止显示来自 Oracle 数据库的任何空轮询响应。  
  
## <a name="differences-between-polling-and-notification"></a>轮询和通知之间的差异  
 尽管轮询和通知是这两个入站的操作，Oracle 数据库中的数据更改通知适配器客户端下, 表说明了这两个之间的一些差异。 以下差异将帮助你决定在具体取决于你的要求操作：  
  
|轮询|通知|  
|-------------|------------------|  
|所有支持的 Oracle 数据库版本支持轮询[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。|通知是仅支持 Oracle 数据库版本 10.2 及更高版本。|  
|你可以配置的轮询间隔来检查可用于按固定时间间隔轮询数据或即时的方式，以及何时有可用的数据。 **提示：**轮询可以为你提供更佳的吞吐量在数据更改发生连续，并且不希望为每项更改的和发生时要通知的情况下。 作为替代，你指定要在其后的发生是因为最后一个更改通知的所有更改的通知轮询间隔。|数据更改通知始终是即时的。|  
|轮询启动的适配器。 适配器执行 SQL 语句以验证是否数据可用于轮询，并随后通过执行轮询语句，如果某些数据可用于轮询开始轮询。|Oracle 数据库发出通知。 只需适配器发出的通知语句指示要在该语句结果集中的更改的情况下启动通知的数据库。 通知是 Oracle 数据库的一项功能。|  
|轮询语句可用于读取或更新的 Oracle 数据库中的数据。|可以使用通知语句仅具有读取 Oracle 数据库中的数据。|  
|轮询通知你有关已更改的实际数据信息。|通知会告知仅如 Insert、 数据中的更改类型的更新和删除。|  
  
 有关详细信息：  
  
-   如何的适配器支持从 Oracle 数据库接收基于轮询的消息，请参阅[接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)。  
  
-   从 Oracle 数据库使用接收基于轮询消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[调用函数和 Oracle 数据库使用 Biztalk Server 中的过程](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md)。  
  
-   从 Oracle 数据库使用 WCF 服务模型中接收基于轮询的消息，请参阅[从使用 WCF 通道模型的 SQL Server 基于接收轮询的数据更改消息](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md)。  
  
-   从 Oracle 数据库使用 WCF 通道模型接收基于轮询的消息，请参阅[从使用 WCF 通道模型的 SQL Server 基于接收轮询的数据更改消息](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md)。  
  
-   消息结构和用于执行轮询查询的 SOAP 操作，请参阅[轮询操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md)。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)