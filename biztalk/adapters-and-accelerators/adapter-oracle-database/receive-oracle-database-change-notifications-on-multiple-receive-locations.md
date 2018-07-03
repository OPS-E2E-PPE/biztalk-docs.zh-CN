---
title: 接收到 Oracle 数据库更改通知在多个接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d273517-9527-4208-99be-97c8a92f176d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9da4eac1c08768e5c4c349ae12de26dce2266d1e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011295"
---
# <a name="receive-oracle-database-change-notifications-on-multiple-receive-locations"></a>接收到 Oracle 数据库更改通知在多个接收位置
假设其中有多个接收位置配置为接收同一个表 (例如 ACCOUNTACTIVITY) 的查询通知的不同 BizTalk 应用程序的一部分创建的同一数据库中。 如果 100 个记录插入到同一个表，所有接收位置将都收到通知消息。 若要有效地接收通知跨多个接收位置，可以从 BizTalk 应用程序如果收到了通知由一个接收位置的此类的方式调用操作，其他接收位置不会获取相同的通知。 因此，您可以有效地在多个位置上接收到的负载平衡通知。  

 若要设置到负载平衡接收通知的业务流程所需的任务是相同的[接收 Oracle 数据库更改通知以增量方式使用 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md)。 本主题列出了唯一两个方法之间的差异。  

## <a name="load-balancing-query-notifications-across-multiple-receive-locations"></a>跨多个负载平衡查询通知的接收位置  
 如本主题中所示[接收 Oracle 数据库更改通知以增量方式使用 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md)，通过执行 PROCESS_RECORDS 过程配置增量通知。 若要配置负载平衡，你可以执行删除已通知的记录的存储的过程。 例如，考虑具有以下定义的存储的过程 NOTIFY_LOAD_BALANCE:  

```  
PROCEDURE NOTIFY_LOAD_BALANCE (TABLE_DATA OUT SYS_REFCURSOR) IS  
  var int;  
BEGIN  
  SELECT TID INTO var FROM ACCOUNTACTIVITY WHERE ROWNUM = 1 FOR UPDATE;  
  OPEN TABLE_DATA FOR SELECT * FROM ACCOUNTACTIVITY WHERE TID = var;  
  DELETE FROM ACCOUNTACTIVITY WHERE TID = var;  
END NOTIFY_LOAD_BALANCE;  
```  

 在此存储的过程执行 BizTalk 应用程序的一部分时，会删除已收到通知时的记录。 因此，其他接收位置获取通知下一条记录。  

 以下是你配置用于接收通知的负载平衡所要执行的高级步骤。  

1. 为创建的架构**通知**（入站操作） 和**NOTIFY_LOAD_BALANCE**过程 （出站操作）。  

2. 添加业务流程和接收通知、 执行过程，并获取响应的过程的三个消息。  

3. 通过添加发送和接收形状、 构造消息形状和端口创建一个业务流程。 可以使用相同的示例代码用于构造一条消息，以调用 NOTIFY_LOAD_BALANCE 存储过程。 请注意，尽管执行中的操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，您必须拥有位置 C:\TestLocation\MessageIn NOTIFY_LOAD_BALANCE 过程的请求消息。 这样做是因为在创建的业务流程的一部分调用的代码段[接收 Oracle 数据库更改通知以增量方式使用 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md)创建基于请求 XML 在 C:\ 中存在的请求消息TestLocation\MessageIn。  

4. 生成和部署应用程序。 若要演示负载平衡，你必须部署此业务流程至少具有两台不同计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]安装。  

5. 在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]两台计算机上的管理控制台指定的 WCF 自定义或 Wcf-oracledb 的以下绑定属性接收位置：  


   |     绑定属性      |                                                                                                                                                                                                                                                                         ReplTest1                                                                                                                                                                                                                                                                         |
   |---------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **InboundOperationType**  |                                                                                                                                                                                                                                                             将此设置为**通知**。                                                                                                                                                                                                                                                             |
   |   **NotificationPort**    | 指定 ODP.NET 必须打开从 Oracle 数据库的数据库更改通知侦听的端口号。 将此设置为相同的端口号必须已添加到 Windows 防火墙例外列表。 有关如何将端口添加到 Windows 防火墙例外列表的说明，请参阅[ http://go.microsoft.com/fwlink/?LinkID=196959 ](http://go.microsoft.com/fwlink/?LinkID=196959)。 **重要说明：** 如果将其设置为默认值-1，必须完全禁用 Windows 防火墙，以接收通知消息。 |
   | **NotificationStatement** |                                                                                                                                                                 将此设置为：<br /><br /> `SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’` **注意：** 必须指定表名称以及架构名称。 例如， `SCOTT.ACCOUNTACTIVITY`。                                                                                                                                                                 |
   | **NotifyOnListenerStart** |                                                                                                                                                                                                                                                                 将此设置为 **，则返回 True**。                                                                                                                                                                                                                                                                 |


6. 启动 BizTalk 应用程序。  

7. 若要开始接收通知，请将 100 条记录插入 ACCOUNTACTIVITY 表。 在执行此操作，请确保请求 XML 调用 NOTIFY_LOAD_BALANCE 过程现已推出 C:\TestLocation\MessageIn。  

8. 监视将删除通知消息的 BizTalk 应用程序 （在这两台计算机） 上的位置。 您将注意到，插入的几百个记录，一个位置获取的某些记录通知而在其他位置获取剩余的记录的通知。 在一起，这两个位置将收到通知的所有几百个记录。  

## <a name="see-also"></a>请参阅  
 [以增量方式使用 BizTalk Server 的 Oracle 数据库更改通知的接收](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md)