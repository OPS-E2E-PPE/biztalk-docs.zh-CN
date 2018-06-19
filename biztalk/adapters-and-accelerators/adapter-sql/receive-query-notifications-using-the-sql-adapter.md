---
title: 接收查询通知使用的 SQL 适配器 |Microsoft 文档
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
ms.openlocfilehash: 37d333a2248c943d1d404aa086565ae4b1662226
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224501"
---
# <a name="receive-query-notifications-using-the-sql-adapter"></a>接收查询通知使用的 SQL 适配器
适配器客户端可以订阅接收查询通知有关数据更改 SQL Server 数据库中。 SQL SELECT 语句或存储的过程用于触发的查询通知中，表中指定的数据更改条件以及 SQL Server 发送作为查询通知和时的结果集的 SELECT 语句或存储的过程更改。  
  
> [!IMPORTANT]
>  若要支持查询通知，适配器客户端和 SQL Server 数据库必须满足某些要求。 有关这些要求的详细信息，请参阅"启用查询通知"网址[http://go.microsoft.com/fwlink/?LinkID=122323](http://go.microsoft.com/fwlink/?LinkID=122323)。  
  
 典型查询通知涉及以下过程：  
  
-   适配器客户端必须指定`Notification`中的入站操作作为**InboundOperationType**绑定属性。 此绑定属性的默认值是`Polling`。  
  
-   适配器客户端必须指定一个 SQL 语句来注册中的查询通知**NotificationStatement**绑定属性。 指定的 SQL 语句更改的结果集时，就会立即适配器客户端从 SQL Server 中获取一条通知。  
  
    > [!IMPORTANT]
    >  若要接收通知，通知订阅的 SQL 语句*必须*满足特定条件。 有关可以用于查询通知的 SQL 语句的信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=122160](http://go.microsoft.com/fwlink/?LinkId=122160)。  
  
-   适配器客户端必须指定适配器是否在中启动侦听器时，就会立即在向适配器客户端发送了通知**NotifyOnListenerStart**绑定属性。  
  
-   通知将发送到适配器客户端视为和中的结果集时指定的 SQL 语句**NotificationStatement**绑定属性更改。  
  
 有关这些绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
> [!NOTE]
>  通知订阅始终是已提交，无论该语句已运行的事务已提交还是回滚。 因此，该通知操作可能不保证查询通知订阅的结果已更改。 例如，假设数据插入表行中 （订阅通知） 在事务中，并立即将通知发送到的更改 （插入） 的相关适配器通知。 由于某些原因，事务能够回滚，并有效地将任何数据插入到表行。 但是，SQL Server 不会将通知发送到有关事务回滚适配器。 有关 SQL Server 中的查询通知的信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=145367](http://go.microsoft.com/fwlink/?LinkId=145367)。  
  
## <a name="differences-between-query-notification-and-polling"></a>查询通知和轮询之间的差异  
 尽管查询通知和轮询是这两个入站的操作，SQL Server 数据库中的数据更改通知适配器客户端下, 表列出这两者之间的一些差异。 以下差异将帮助你决定在具体取决于你的要求操作：  
  
|查询通知|轮询|  
|------------------------|-------------|  
|通过 SQL Server 启动的查询通知。 只需适配器发出的通知语句指示要在该语句结果集中的更改的情况下启动通知的数据库。|轮询启动的适配器。 适配器执行一个语句来验证是否数据可用于轮询，并随后通过执行轮询语句，如果某些数据可用于轮询开始轮询。|  
|可以使用查询通知语句仅具有读取 SQL Server 数据库表中的数据。|轮询语句可用于读取或更新 SQL Server 数据库表中的数据。|  
|查询通知会告知仅如 Insert、 数据中的更改类型的更新和删除。|轮询通知你有关已更改的实际数据信息。|  
|数据更改通知是即时的。|数据更改通知取决于轮询间隔，并且在每个轮询间隔的末尾，有关数据更改的适配器客户端通知。 **提示：** 轮询可以为你提供更佳的吞吐量在数据更改发生连续，并且不希望为每项更改的和发生时要通知的情况下。 作为替代，你指定要在其后的发生是因为最后一个更改通知的所有更改的通知轮询间隔。|  
  
 有关中的查询通知的详细信息[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]，请参阅[使用 BizTalk server 接收 SQL 的查询通知](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)