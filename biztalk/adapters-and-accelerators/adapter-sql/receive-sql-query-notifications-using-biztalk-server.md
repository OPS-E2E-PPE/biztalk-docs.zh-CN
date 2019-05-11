---
title: 接收使用 BizTalk Server 的 SQL 查询通知 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 69444df7-f2ae-4d1a-9b49-817b437517d8
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc64165dcdf642e1ce9a0166b4f38c1c229e391f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368230"
---
# <a name="receive-sql-query-notifications-using-biztalk-server"></a>接收使用 BizTalk Server 的 SQL 查询通知
你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以接收通知消息的 SQL Server 表或视图。 可以指定适配器用于与 SQL Server 通知注册的 SQL 语句。 通知语句可以是 SELECT 语句或存储的过程返回一个结果集。 有关查询通知的详细信息，请参阅"使用查询通知"网址[ http://go.microsoft.com/fwlink/?LinkId=122159 ](http://go.microsoft.com/fwlink/?LinkId=122159)。 有关可用于查询通知的查询的信息，请参阅"创建查询的通知"网址[ http://go.microsoft.com/fwlink/?LinkId=122160 ](http://go.microsoft.com/fwlink/?LinkId=122160)。  
  
 从 SQL Server 接收查询通知是类似于轮询 SQL Server，有一些关键的区别。 有关差异的列表，请参阅[注意事项接收查询通知使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)。  
  
 以下是可以在其中配置某些情况下[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]从 SQL Server 接收通知：  
  
- 适配器客户端获取仅"递增"通知，例如，仅为那些自上次通知以来对数据库表所做的更改。  
  
- 如果许多行插入到数据库表中，适配器客户端可以配置多个接收到的负载平衡接收通知的位置。  
  
- 如果适配器客户端能够在其接收通知的接收位置出现故障，适配器客户端可以配置适配器的接收位置之后再次接收通知。 客户端还必须实现逻辑以处理可能具有已插入、 更新或接收位置已关闭时删除的记录其应用程序中。  
  
  适配器客户端收到一条通知消息后, 他们可以执行特定任务根据收到的通知的类型。 例如，BizTalk 业务流程可以设计它执行的任务，如果插入通知接收到一组和另一组任务的如果收到更新通知方式。  
  
  在本部分中的主题提供有关如何配置每种方案的适配器的信息。 若要开始从 SQL Server 使用获取通知[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，必须指定特定绑定的属性。 有关如何在适配器支持接收消息的详细信息，请参阅[注意事项接收查询通知使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)。 有关与通知相关的绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。 有关通知消息的结构的详细信息，请参阅[查询通知的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-query-notification.md)。  
  
  若要启用查询通知的 SQL Server 上，您还必须执行以下任务。  
  
- 必须为 SQL Server 数据库启用服务中介程序。  
  
- 您必须确保适配器客户端具有必要的权限来执行命令请求通知。  
  
  有关这些任务的详细信息，请参阅"启用查询通知"网址[ http://go.microsoft.com/fwlink/?LinkID=122323 ](http://go.microsoft.com/fwlink/?LinkID=122323)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [注意事项接收查询通知使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)  
  
-   [进程通知消息，以完成特定任务中使用 BizTalk Server 的 SQL](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)  
  
-   [从使用 BizTalk Server 的 SQL 查询通知以增量方式接收](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)  
  
-   [从 SQL 使用 BizTalk Server 接收查询通知上多个接收位置](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-on-receive-locations-from-sql-server-using-biztalk.md)  
  
-   [在 SQL 中使用 BizTalk Server 接收查询通知后接收位置中断](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-after-a-sql-receive-location-stops-in-biztalk.md)  
  
## <a name="see-also"></a>请参阅  
[使用 SQL 适配器开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)