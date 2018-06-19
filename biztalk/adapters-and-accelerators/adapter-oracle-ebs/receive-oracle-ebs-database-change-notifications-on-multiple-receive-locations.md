---
title: 接收到 Oracle E-business Suite 数据库更改通知上多个接收位置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d25faa52-e0a4-4593-8449-3ec93d5887e9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5023dddeaab02c86db5507bc0f96ccfddd82c76e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217021"
---
# <a name="receive-oracle-e-business-suite-database-change-notifications-on-multiple-receive-locations"></a>接收到 Oracle E-business Suite 数据库更改通知上多个接收位置
在同一数据库中假设你有多个接收位置不同的 BizTalk 应用程序配置为接收同一个表 (例如 ACCOUNTACTIVITY) 的查询通知的一部分创建的其中一个方案。 如果上百个记录插入到同一个表中，所有接收位置将都收到通知消息。 若要有效地接收通知跨多个接收位置、 可以从 BizTalk 应用程序如果逐个收到通知接收位置的此类的方式调用操作、 其他接收位置不会获取相同的通知。 这样，你可以有效地在多个位置上收到的负载平衡通知。  
  
 设置负载平衡接收通知的业务流程所需的任务是与，对于相同[接收 Oracle E-business Suite 更改通知以增量方式使用 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-change-notifications-incrementally-using-biztalk-server.md)。 本主题列出了唯一两种方法之间的差异。  
  
## <a name="load-balancing-query-notifications-across-multiple-receive-locations"></a>在多个负载平衡查询通知接收位置  
 如主题中[接收 Oracle E-business Suite 更改通知以增量方式使用 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-change-notifications-incrementally-using-biztalk-server.md)，通过执行 PROCESS_RECORDS 过程配置增量的通知。 若要配置负载平衡，无法执行删除已接到通知有关的记录的存储的过程。 例如，考虑存储的过程 NOTIFY_LOAD_BALANCE 替换为以下定义：  
  
```  
PROCEDURE NOTIFY_LOAD_BALANCE (TABLE_DATA OUT SYS_REFCURSOR) IS  
  var int;  
BEGIN  
  SELECT TID INTO var FROM ACCOUNTACTIVITY WHERE ROWNUM = 1 FOR UPDATE;  
  OPEN TABLE_DATA FOR SELECT * FROM ACCOUNTACTIVITY WHERE TID = var;  
  DELETE FROM ACCOUNTACTIVITY WHERE TID = var;  
END NOTIFY_LOAD_BALANCE;  
```  
  
 BizTalk 应用程序的一部分执行此存储的过程时，获取删除已收到通知时该记录。 因此，其他接收下一条记录的位置获取的通知。  
  
 以下是配置负载平衡，用于接收通知时必须执行的高级步骤。  
  
1.  创建架构**通知**（入站操作） 和**NOTIFY_LOAD_BALANCE**过程 （出站操作）。  
  
2.  添加业务流程，并添加三个消息接收通知，执行过程，以及有关该过程中获取响应。  
  
3.  通过添加 Send 和 Receive 形状、 构造消息形状和端口创建业务流程。 可以使用相同的示例代码用于构造一条消息，以调用 NOTIFY_LOAD_BALANCE 存储过程。 请注意，尽管执行中的操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，您必须拥有位置 C:\TestLocation\MessageIn NOTIFY_LOAD_BALANCE 过程的请求消息。 这样做是因为在中创建业务流程的一部分调用的代码段[接收 Oracle E-business Suite 更改通知以增量方式使用 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-change-notifications-incrementally-using-biztalk-server.md)创建根据请求存在的 XML 请求消息在 C:\TestLocation\MessageIn。  
  
4.  生成和部署应用程序。 若要演示负载平衡，你必须部署此业务流程至少具有两台不同计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]安装。  
  
5.  在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]两台计算机上的管理控制台为 WCF 自定义或 WCF OracleEBS 接收位置指定以下绑定属性：  
  
    |绑定属性|值|  
    |----------------------|-----------|  
    |**InboundOperationType**|将其设置为**通知**。|  
    |**NotificationPort**|指定 ODP.NET 必须打开侦听从 Oracle 数据库的数据库更改通知的端口号。 将其设置为相同的端口号必须已添加到 Windows 防火墙例外列表。 有关如何将端口添加到 Windows 防火墙例外列表的说明，请参阅[http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)。 **重要说明：** 如果设置为默认值为-1，则你将需要完全禁用 Windows 防火墙，以接收通知消息。|  
    |**NotificationStatement**|将其设置为：<br /><br /> `SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’`**注意：** 必须指定表名称以及架构名称。 例如， `SCOTT.ACCOUNTACTIVITY`。|  
    |**NotifyOnListenerStart**|将其设置为**True**。|  
  
6.  启动 BizTalk 应用程序。  
  
7.  若要开始接收通知，请将上百个记录插入 ACCOUNTACTIVITY 表。 在这样做，请确保请求 XML 调用 NOTIFY_LOAD_BALANCE 过程位于 C:\TestLocation\MessageIn。  
  
8.  监视其中 BizTalk 应用程序将删除为通知消息 （在这两个计算机） 上的位置。 你将注意到，几百个记录插入的一个位置获取一些记录的通知时其他位置获取剩余的记录的通知。 在一起，这两个位置将会收到数百个的所有记录的通知。  
  
## <a name="see-also"></a>另请参阅  
 [接收使用 BizTalk Server 的 Oracle E-business Suite 数据库更改通知](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-biztalk-server.md)