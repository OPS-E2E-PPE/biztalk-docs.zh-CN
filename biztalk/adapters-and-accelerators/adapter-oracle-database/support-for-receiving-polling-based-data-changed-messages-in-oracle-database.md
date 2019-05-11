---
title: 支持 Oracle 数据库中接收基于轮询的数据更改消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- notifications, polling-based
- post-polling
- POLLINGSTMT
- polling interval
- polling
ms.assetid: 9ff29d3f-ebb1-4d82-9106-150f939cbd9e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fc03b831cbfcc3ce4b1db4a8fe5b0a1028f8513
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375936"
---
# <a name="support-for-receiving-polling-based-data-changed-messages-in-oracle-database"></a>支持 Oracle 数据库中接收基于轮询的数据更改消息
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ，客户端程序可以从通知他们对 Oracle 数据库中存储的数据更改的 Oracle 数据库接收消息。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持接收适配器，其中执行指定的 SELECT 查询、 存储的过程、 函数或过程或函数的包中的"基于轮询的"消息中检索数据，并以常规客户端提供的结果按时间间隔。 若要启用此选项，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开 POLLINGSTMT 操作。 此外，所有存储的过程、 函数和过程和函数中的包被称为轮询的入站操作。  

 适配器提供轮询 Oracle 数据库的两种的方法：  

-   **使用 SELECT 语句**。 可以指定一个简单的 SELECT 语句来轮询的表和 Oracle 数据库中的视图。 适配器执行 SELECT 语句指定的时间间隔，并将结果返回到适配器客户端。  

-   **使用存储的过程、 函数或过程或函数的包中**。 您可以指定存储的过程、 函数或过程或函数来轮询 Oracle 数据库的包中。 适配器在指定的时间间隔执行的请求消息并将结果返回到适配器客户端。  

## <a name="polling-operation-workflow"></a>轮询操作工作流  
 典型轮询操作使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]涉及以下：  

1. 适配器客户端必须指定**轮询**中的入站操作**InboundOperationType**属性绑定。 此绑定属性的默认值是**轮询**。  

2. 适配器客户端必须指定 SELECT 语句，以**PolledDataAvailableStatement**属性以确定是否存在可用于轮询数据绑定。 在执行此语句时，如果返回的结果集的第一行的第一列包含一个正整数值，则日期可用于轮询。 默认情况下，此绑定属性的值设置为`Select 1 FROM DUAL`，这意味着与否，适配器必须继续轮询而不考虑轮询表是否包含数据。  

3. 适配器客户端必须指定为一个轮询间隔**PollingInterval**绑定属性，以秒为单位中指定的语句定义间隔**PolledDataAvailableStatement**执行属性绑定。 在每个轮询间隔结束时，执行轮询的数据可用语句，并返回的结果集。  

4. 适配器客户端必须指定 SELECT 语句或存储的过程**PollingStatement**属性绑定。  

   - 如果你想要轮询的表或视图，则必须在此绑定属性中指定的 SELECT 查询。  

   - 如果你想要使用存储的过程、 函数或过程或函数的包中轮询，则必须在此绑定属性中指定相应操作的整个请求消息。  

     中的语句**PollingStatement**仅当没有可用于轮询，由数据绑定属性执行**PolledDataAvailableStatement**属性绑定在步骤 1 中。  

5. 适配器客户端必须指定操作中轮询操作**PollingAction**属性绑定。 有关使用适配器服务外接程序使用的操作生成的元数据确定特定操作的轮询操作。  

   > [!NOTE]
   >  如果您轮询表，或查看使用中的 SELECT 语句**PollingStatement**绑定属性，您不需要指定任何值**PollingAction**属性绑定。 默认值为 Null，在这种情况下传递。  

6. 适配器客户端可以使用**PollWhileDataFound**属性要忽略的轮询间隔，并连续轮询数据，以及可用时绑定。  

   > [!IMPORTANT]
   >  如果设置的值**PollWhileDataFound**绑定属性设为 True，连续轮询适配器客户端数据从 Oracle 或进程中打开和关闭连接到 Oracle 数据库在循环中。 如 ODP.NET 打开连接的速率大于连接处于关闭状态，连接用尽段时间后，并引发异常。 作为替代方案，请确保的值**UseOracleConnectionPool**设置为 True，并适当的值中提及**IncrPoolSize**绑定属性来控制连接数可以通过适配器客户端打开的。  

7. 适配器客户端可以为指定的轮询后语句，Oracle PL/SQL 块中， **PostPollStatement**属性绑定。 在此绑定属性中指定的语句执行后的语句中指定**PollingStatement**执行绑定属性。  

   该适配器将轮询语句和轮询后语句包装在事务和事务超时值设置为指定的值作为**PollingInterval**属性绑定。 因此，务必指定超时值大于或等于所需以处理传入消息并发送答复的时间。 如果客户端程序使用的消息或执行后轮询查询所花费的时间超过超时值的详细信息，则回滚事务。 如果所用的时间小于超时值，该适配器提交事务，并"休眠"中执行下一次轮询之前轮询的剩余时间。  

   适配器禁止显示来自 Oracle 数据库的任何空轮询响应。  

## <a name="differences-between-polling-and-notification"></a>轮询和通知之间的差异  
 尽管轮询和通知这两个入站操作，并在 Oracle 数据库中的数据更改通知适配器客户端下, 表说明了这两个之间的一些差异。 以下差异将帮助你决定具体取决于您的要求操作：  


|                                                                                                                                                                                                                                                      轮询                                                                                                                                                                                                                                                      |                                                                                                                              通知                                                                                                                               |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                                                                                          对于所有支持的 Oracle 数据库版本支持轮询[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。                                                                                                                                                                           |                                                                                               通知是仅支持 Oracle 数据库版本 10.2 和更高版本。                                                                                               |
| 你可以配置轮询间隔来检查可用的固定时间间隔轮询的数据或在瞬间完成，以及何时有可用的数据。 **提示：** 轮询可以提供更好的吞吐量中情况下，数据更改发生的连续，并且不希望为每个更改的和发生时收到通知。 相反，您指定要在其后的发生是因为最后一个更改通知的所有更改通知的轮询间隔。 |                                                                                                          数据更改通知始终是瞬间完成的。                                                                                                          |
|                                                                                                                                         由适配器启动轮询。 适配器执行 SQL 语句，以验证是否可用于轮询，然后通过执行轮询语句，如果某些数据可用于轮询启动轮询数据。                                                                                                                                         | Oracle 数据库发出通知。 只需在适配器发出的通知语句指示要在没有语句的结果集中的更改的情况下启动通知的数据库。 通知是 Oracle 数据库的一项功能。 |
|                                                                                                                                                                                                                 轮询语句可用于读取或更新 Oracle 数据库中的数据。                                                                                                                                                                                                                  |                                                                                             通知语句可用于只读取 Oracle 数据库中的数据。                                                                                             |
|                                                                                                                                                                                                                            轮询通知您已更改的实际数据。                                                                                                                                                                                                                            |                                                                                   通知只告知如 Insert、 数据更改的类型更新和删除。                                                                                    |

 有关详细信息：  

- 如何在适配器支持从 Oracle 数据库接收基于轮询的消息，请参阅[接收基于轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)。  

- 从 Oracle 数据库使用接收基于轮询的消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[调用的函数和过程在 Oracle 数据库中使用 Biztalk Server](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md)。  

- 从使用 WCF 服务模型的 Oracle 数据库接收基于轮询的消息，请参阅[从 SQL Server 使用 WCF 通道模型基于接收轮询的数据更改消息](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md)。  

- 从使用 WCF 通道模型 Oracle 数据库接收基于轮询的消息，请参阅[从 SQL Server 使用 WCF 通道模型基于接收轮询的数据更改消息](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md)。  

- 消息结构和用于执行轮询查询的 SOAP 操作，请参见[轮询操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md)。  

## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)