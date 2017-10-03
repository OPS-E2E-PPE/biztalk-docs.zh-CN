---
title: "从 SQL 使用 BizTalk Server 接收轮询消息跨多个接收端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21cf4875-1c04-41cf-98f5-d1307987ca55
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2be084ca9e0a90813a541563bf6f600ea277aec9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk-server"></a>从 SQL 使用 BizTalk Server 接收轮询消息跨多个接收端口
请考虑你想要创建的 BizTalk 应用程序包括两个轮询操作的方案。 每个轮询操作轮询单独的表，员工和客户，从同一个数据库。 当部署中的此类的应用程序[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你将需要创建两个接收端口。 每个连接 URI 接收端口将是：  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>  
```  
  
 因为这两个接收端口从相同服务器上的相同数据库接收轮询消息、 连接 URI 的同时将相同。 但是，BizTalk 应用程序不能有两个接收与同一个连接 URI 的端口。  
  
 若要启用适配器客户端要有两个在 BizTalk 应用程序，接收轮询同一数据库 （或甚至数据库中的同一个表） 的端口[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]提供连接属性， **InboundID**。 你可以指定此连接属性的任何值。 通过添加入站的 ID 的连接 URI 变得唯一。 例如：  
  
 接收员工表的轮询消息的端口的连接 URI 可以是：  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>?InboundID=Employee  
```  
  
 同样，接收 Customer 表的轮询消息的端口的连接 URI 可以是：  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>?InboundID=Customer  
```  
  
 因为通过添加唯一的连接 Uri 变为**InboundID**属性，你可以现在有多个接收轮询同一个数据库或表中单个 BizTalk 应用程序的端口。  
  
> [!IMPORTANT]
>  你可以选择指定**InboundID**两个连接属性**轮询**和**TypedPolling**操作。  
  
## <a name="see-also"></a>另请参阅  
 [与 BizTalk Server 中使用 SQL 适配器的轮询 SQL Server](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)