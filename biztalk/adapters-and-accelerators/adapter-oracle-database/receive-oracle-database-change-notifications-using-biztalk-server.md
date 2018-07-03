---
title: 接收使用 BizTalk Server 的 Oracle 数据库更改通知 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 495a29bc-72f6-4140-8160-0b917d935503
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8bd67791e56d941d58cb0b221bf7ad63bb3778f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985038"
---
# <a name="receive-oracle-database-change-notifications-using-biztalk-server"></a>接收使用 BizTalk Server 的 Oracle 数据库更改通知
你可以配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]从 Oracle 数据库接收数据库更改通知消息。 可以指定适配器用于与 Oracle 数据库的通知注册的 SELECT 语句。 针对通知，请注册的 SELECT 语句的结果集更改时，适配器将接收通知消息。 有关如何在适配器支持通知的详细信息，请参阅[接收使用 Oracle 数据库适配器数据库更改通知时的注意事项](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)。  
  
 以下是可以在其中配置某些情况下[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]从 Oracle 数据库接收通知：  
  
- 适配器客户端获取仅"递增"通知，例如，仅为那些自上次通知以来对数据库表所做的更改。  
  
- 如果大量的行插入到数据库表中，适配器客户端可以配置多个接收到的负载平衡接收通知的位置。  
  
  适配器客户端收到一条通知消息后, 他们可以执行特定任务根据收到的通知的类型。 例如，BizTalk 业务流程可以设计它执行的任务，如果插入通知接收到一组和另一组任务的如果收到更新通知方式。  
  
> [!CAUTION]
>  如果没有在 Oracle 数据库和适配器客户端之间的网络中断，通知将不会发送到适配器客户端的网络中断期间对 Oracle 数据库进行的更改，此后。 因此，您必须使用轮询操作而不是关键方案的通知操作。  
  
 在本部分中的主题提供有关如何配置每种方案的适配器的信息。 若要开始从 Oracle 数据库使用获取通知[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，必须指定特定绑定的属性。 有关与通知相关的绑定属性的详细信息，请参阅[使用的绑定属性](https://msdn.microsoft.com/library/dd788467.aspx)。 有关通知消息的结构的详细信息，请参阅[通知操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-notification-operation1.md)。  
  
 用于从 Oracle 数据库接收通知，请确保：  
  
-   使用适配器连接到 Oracle 数据库版本 10.2 或更高版本。 10.2 之前的 oracle 数据库版本不支持通知。  
  
-   用来连接到 Oracle 通知的凭据具有`change notification`特权。 此权限是必需的接收数据库更改通知。 为此，请连接到 Oracle 数据库使用管理权限，然后在 SQL 提示符处键入以下命令。  
  
    ```  
    grant change notification to <user name>  
    ```  
  
-   决定你想要用于从 Oracle 数据库接收数据库更改通知的 ODP.NET TCP 端口。 将该端口添加到 Windows 防火墙例外列表。 有关如何将端口添加到 Windows 防火墙例外列表的说明，请参阅[ http://go.microsoft.com/fwlink/?LinkID=196959 ](http://go.microsoft.com/fwlink/?LinkID=196959)。 必须提供的同一端口号**NotificationPort**属性绑定。 有关绑定属性的详细信息，请参阅[使用的绑定属性](https://msdn.microsoft.com/library/dd788467.aspx)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [接收数据库更改通知使用 Oracle 数据库适配器时的注意事项](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)  
  
-   [处理的 Oracle 数据库使用 BizTalk Server 中完成特定任务的通知消息](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md)  
  
-   [以增量方式使用 BizTalk Server 的 Oracle 数据库更改通知的接收](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md)  
  
-   [在多个接收 Oracle 数据库更改通知的接收位置](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-on-multiple-receive-locations.md)  
  
-   [接收后的 Oracle 数据库更改通知接收位置中断](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-after-a-receive-location-breakdown.md)  
  
## <a name="see-also"></a>请参阅  
[若要开发与 Oracle 数据库的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)