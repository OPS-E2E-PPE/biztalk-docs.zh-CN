---
title: 从 SQL 使用 BizTalk Server 接收轮询消息跨多个接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 21cf4875-1c04-41cf-98f5-d1307987ca55
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17f7be558dfcd5939836143e361f4b3a76850701
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368713"
---
# <a name="receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk-server"></a>从 SQL 使用 BizTalk Server 接收轮询消息跨多个接收端口
假设你想要创建包含两个轮询操作的 BizTalk 应用程序。 每个轮询操作轮询单独的表，员工和客户，从同一个数据库。 在此类应用程序的部署时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你将需要创建两个接收端口。 连接 URI 为每个接收端口将是：  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>  
```  
  
 因为这两个接收端口将从同一台服务器上的相同数据库接收轮询消息、 连接 URI 的同时将相同。 但是，BizTalk 应用程序不能有两个接收端口与同一个连接 URI。  
  
 若要启用适配器客户端有两个 BizTalk 应用程序中的接收轮询同一数据库 （或甚至在数据库中的同一个表） 的端口[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]提供了连接属性**InboundID**。 可以指定此连接属性的任何值。 通过添加入站的 ID，一个连接 URI 变得唯一。 例如：  
  
 为端口接收轮询消息为 Employee 表的连接 URI 可以是：  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>?InboundID=Employee  
```  
  
 同样，为端口接收轮询消息的 Customer 表的连接 URI 可以是：  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>?InboundID=Customer  
```  
  
 因为通过添加连接 Uri 变得唯一**InboundID**属性，可以现在有多个接收端口轮询同一数据库或单个 BizTalk 应用程序中的表。  
  
> [!IMPORTANT]
>  您可以选择指定**InboundID**两个连接属性**轮询**并**TypedPolling**操作。  
  
## <a name="see-also"></a>请参阅  
 [使用 SQL 适配器与 BizTalk Server 轮询 SQL Server](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)