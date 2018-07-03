---
title: 接收查询通知使用 SQL 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b2ed0f0-d005-4eec-b1a6-97a0c94678dc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 786bbf556acb3a30e652a7ecb29723f40566cb06
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999742"
---
# <a name="receive-query-notifications-using-the-sql-adapter"></a>接收查询通知使用 SQL 适配器
适配器客户端可以订阅以接收有关数据更改的查询通知中的 SQL Server 数据库。 SQL SELECT 语句或存储的过程的查询通知触发对表中指定的数据更改条件和 SQL Server 发送作为查询通知时的结果集的 SELECT 语句或存储的过程发生更改。  
  
> [!IMPORTANT]
>  若要支持查询通知，适配器客户端和 SQL Server 数据库必须满足某些要求。 有关这些要求的详细信息，请参阅"启用查询通知"网址[ http://go.microsoft.com/fwlink/?LinkID=122323 ](http://go.microsoft.com/fwlink/?LinkID=122323)。  
  
 典型的查询通知涉及以下过程：  
  
- 适配器客户端必须指定`Notification`中的入站操作**InboundOperationType**属性绑定。 此绑定属性的默认值是`Polling`。  
  
- 适配器客户端必须指定一个 SQL 语句来注册中的查询通知**NotificationStatement**属性绑定。 只要指定的 SQL 语句更改的结果集适配器客户端从 SQL Server 中获取一条通知。  
  
  > [!IMPORTANT]
  >  若要接收通知，通知订阅的 SQL 语句*必须*满足特定条件。 有关可用于查询通知的 SQL 语句的信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=122160 ](http://go.microsoft.com/fwlink/?LinkId=122160)。  
  
- 适配器客户端必须指定适配器是否一旦启动侦听器在向适配器客户端发送了通知**NotifyOnListenerStart**属性绑定。  
  
- 通知发送到作为适配器客户端和中的结果集时指定的 SQL 语句**NotificationStatement**绑定属性发生更改。  
  
  有关这些绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
> [!NOTE]
>  通知订阅始终是已提交，而不考虑是否运行语句的事务已提交或回滚。 因此，通知操作可能会保证为通知订阅的查询的结果已更改。 例如，假设数据插入表行中 （为通知订阅） 在事务中，并立即通知发送到适配器通知有关的更改 （插入）。 由于某种原因，事务将回滚，并有效地将任何数据插入到表行。 但是，SQL Server 不会发送到事务回滚有关适配器通知。 有关 SQL Server 中的查询通知的信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=145367 ](http://go.microsoft.com/fwlink/?LinkId=145367)。  
  
## <a name="differences-between-query-notification-and-polling"></a>查询通知和轮询之间的差异  
 尽管查询通知和轮询是这两个入站的操作，并在 SQL Server 数据库中的数据更改通知适配器客户端下, 表列出了两者之间的一些差异。 以下差异将帮助你决定具体取决于您的要求操作：  
  
|查询通知|轮询|  
|------------------------|-------------|  
|查询通知是由 SQL Server 启动。 只需在适配器发出的通知语句指示要在没有语句的结果集中的更改的情况下启动通知的数据库。|由适配器启动轮询。 适配器执行语句，以验证是否可用于轮询，然后通过执行轮询语句，如果某些数据可用于轮询启动轮询数据。|  
|可以使用查询通知语句仅读取 SQL Server 数据库表中的数据。|轮询语句可用于读取或更新 SQL Server 数据库表中的数据。|  
|查询通知只告知如 Insert、 数据更改的类型更新和删除。|轮询通知您已更改的实际数据。|  
|数据更改通知是瞬间完成的。|数据更改通知取决于轮询间隔，并且适配器客户端将每个轮询间隔结束时通知数据更改。 **提示：** 轮询可以为您提供更好的吞吐量中情况下，数据更改发生的连续，并且不希望为每个更改的和发生时收到通知。 相反，您指定要在其后的发生是因为最后一个更改通知的所有更改通知的轮询间隔。|  
  
 有关详细信息中的查询通知[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]，请参阅[通过使用 BizTalk Server 接收 SQL 查询通知](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)