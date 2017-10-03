---
title: "接收使用 BizTalk Server 的 SQL 查询通知 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69444df7-f2ae-4d1a-9b49-817b437517d8
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1632bde50a0daf9df22b9c1cfb7aaca8d59fbce7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-sql-query-notifications-using-biztalk-server"></a>接收使用 BizTalk Server 的 SQL 查询通知
你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以接收通知消息的 SQL Server 表或视图。 你可以指定适配器用于与 SQL Server 通知注册的 SQL 语句。 通知语句可以是 SELECT 语句或存储的过程返回的结果集。 有关查询通知的详细信息，请参阅"使用查询通知"网址[http://go.microsoft.com/fwlink/?LinkId=122159](http://go.microsoft.com/fwlink/?LinkId=122159)。 有关可以用于查询通知的查询的信息，请参阅"创建查询的通知"网址[http://go.microsoft.com/fwlink/?LinkId=122160](http://go.microsoft.com/fwlink/?LinkId=122160)。  
  
 从 SQL Server 接收查询通知是类似于轮询 SQL Server，有一些关键的区别。 差异的列表，请参阅[注意事项接收查询通知使用的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)。  
  
 以下是某些情况下，你可以在其中配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]从 SQL Server 接收通知：  
  
-   适配器客户端获取仅"增量"通知，例如，仅为已对数据库表从上次通知这些更改。  
  
-   如果多行插入到数据库表中，适配器客户端可以配置多个接收到的负载平衡接收通知的位置。  
  
-   如果适配器客户端在其接收通知的接收位置出现故障，适配器客户端可以配置的适配器接收位置再次已启动时，就会立即收到通知。 客户端还必须在其应用程序来处理可能已插入、 更新，或接收位置已关闭时删除的记录中实现的逻辑。  
  
 一旦适配器客户端收到的通知消息，他们可以执行特定任务根据收到的通知的类型。 例如，它执行的任务，如果收到插入通知的一组和另一组任务的如果收到更新通知的方式可以设计 BizTalk 业务流程。  
  
 此部分中的主题提供有关如何配置每种方案的适配器的信息。 若要开始获取来自 SQL Server 使用的通知[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，你必须指定特定的绑定属性。 有关如何适配器支持接收消息的详细信息，请参阅[注意事项接收查询通知使用的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)。 有关与通知相关的绑定属性的详细信息，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。 有关通知消息结构的详细信息，请参阅[查询通知的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-query-notification.md)。  
  
 您还必须启用查询通知的 SQL Server 上执行以下任务。  
  
-   你必须为 SQL Server 数据库中启用 Service Broker。  
  
-   你必须确保适配器客户端具有足够的权限来执行命令以请求通知。  
  
 有关这些任务的详细信息，请参阅"启用查询通知"网址[http://go.microsoft.com/fwlink/?LinkID=122323](http://go.microsoft.com/fwlink/?LinkID=122323)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [注意事项接收查询通知使用的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)  
  
-   [若要完成 SQL 使用 BizTalk Server 中的特定任务的进程通知消息](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)  
  
-   [从使用 BizTalk Server 的 SQL 查询通知以增量方式接收](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)  
  
-   [从 SQL 使用 BizTalk Server 接收查询通知上多个接收位置](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-on-receive-locations-from-sql-server-using-biztalk.md)  
  
-   [接收查询通知后接收位置分解 SQL 使用 BizTalk Server 中](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-after-a-sql-receive-location-stops-in-biztalk.md)  
  
## <a name="see-also"></a>另请参阅  
[开发使用 SQL 适配器的 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)