---
title: "从 SQL 使用 BizTalk Server 接收查询通知上多个接收位置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9afbe98e-8901-417c-a807-8db97fd7a24b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa858483914b8325e9250e1e41f99ae03226f3ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-query-notifications-on-multiple-receive-locations-from-sql-using-biztalk-server"></a>从 SQL 使用 BizTalk Server 接收查询通知上多个接收位置
在同一数据库中假设你有多个接收位置不同的 BizTalk 应用程序配置为接收同一个表 （例如员工） 的查询通知的一部分创建的其中一个方案。 如果上百个记录插入到同一个表中，所有接收位置将都收到通知消息。 若要有效地接收通知跨多个接收位置、 可以从 BizTalk 应用程序如果逐个收到通知接收位置的此类的方式调用操作、 其他接收位置不会获取相同的通知。 这样，你可以有效地在多个位置上收到的负载平衡通知。  
  
 设置负载平衡接收通知的业务流程所需的任务是与，对于相同[接收查询通知以增量方式从 SQL 使用 BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)。 本主题列出了唯一两种方法之间的差异。  
  
## <a name="load-balancing-query-notifications-across-multiple-receive-locations"></a>在多个负载平衡查询通知接收位置  
 如主题中[接收查询通知以增量方式从 SQL 使用 BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)，通过在已通知的记录上执行 UPDATE 语句配置增量的通知。 若要配置负载平衡，无法执行删除已接到通知有关的记录的存储的过程。 例如，考虑存储的过程 PROCESS_EMPLOYEE 替换为以下定义：  
  
```  
DECLARE @var int  
SELECT TOP 1 @var = Employee_ID FROM Employee  
SELECT * FROM Employee WHERE Employee_ID=@var  
DELETE FROM Employee WHERE Employee_ID=@var  
```  
  
 BizTalk 应用程序的一部分执行此存储的过程时，获取删除已收到通知时该记录。 因此，其他接收下一条记录的位置获取的通知。  
  
 以下是配置负载平衡，用于接收通知时必须执行的高级步骤。  
  
1.  创建架构**通知**（入站操作） 和**PROCESS_EMPLOYEE**存储过程 （出站操作）。  
  
2.  添加业务流程和添加接收通知、 执行存储的过程，并为存储过程获取响应的三条消息。  
  
3.  通过添加 Send 和 Receive 形状、 构造消息形状和端口创建业务流程。 可以使用相同的示例代码用于构造一条消息，以调用 PROCESS_EMPLOYEE 存储过程。 请注意，尽管执行中的操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你必须具有 PROCESS_EMPLOYEE 请求消息中的位置 C:\TestLocation\MessageIn 存储过程。 这样做是因为在中创建业务流程的一部分调用的代码段[接收查询通知以增量方式从 SQL 使用 BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)创建根据请求在 C:\ 中存在 XML 请求消息TestLocation\MessageIn。  
  
4.  生成和部署应用程序。 若要演示负载平衡，你必须部署此业务流程至少具有两台不同计算机上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装。  
  
5.  在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]两台计算机上的管理控制台指定的 WCF 自定义或 WCF SQL 的以下绑定属性接收位置：  
  
    |绑定属性|值|  
    |----------------------|-----------|  
    |**InboundOperationType**|将其设置为**通知**。|  
    |**NotificationStatement**|将其设置为：<br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> **注意：**对于通知语句，你必须始终指定表名称以及架构名称。 例如， `dbo.Employee`。|  
    |**NotifyOnListenerStart**|将其设置为**True**。|  
  
6.  启动 BizTalk 应用程序。  
  
7.  若要开始接收通知，请将上百个记录插入员工表。 在这样做，请确保请求 XML 调用 PROCESS_EMPLOYEE 的存储过程是在 C:\TestLocation\MessageIn 中可用。  
  
8.  监视其中 BizTalk 应用程序将删除为通知消息 （在这两个计算机） 上的位置。 你将注意到，几百个记录插入的一个位置获取一些记录的通知时其他位置获取剩余的记录的通知。 在一起，这两个位置将会收到数百个的所有记录的通知。  
  
## <a name="see-also"></a>另请参阅  
 [接收使用 BizTalk Server 的 SQL 查询通知](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)