---
title: "接收使用 BizTalk Server Oracle E-business Suite 数据库更改通知 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e92520cf-c552-4225-abba-8e03f73ecf70
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24ac132f599256c2051763ed849e4e5329563201
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-oracle-e-business-suite-database-change-notifications-using-biztalk-server"></a>接收使用 BizTalk Server Oracle E-business Suite 数据库更改通知
你可以配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]从 Oracle E-business Suite 接收数据库更改通知消息。 你可以指定适配器用于 Oracle E-business Suite 通知注册的 SELECT 语句。 适配器将结果集中为 SELECT 语句中，为通知注册更改时接收通知消息。 有关如何适配器支持通知的详细信息，请参阅[接收使用 Oracle E-business Suite 适配器数据库更改通知时的注意事项](../../adapters-and-accelerators/adapter-oracle-ebs/before-you-receive-database-change-notifications-using-the-oracle-ebs-adapter.md)。  
  
 以下是某些情况下，你可以在其中配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]从 Oracle E-business Suite 接收通知：  
  
-   适配器客户端获取仅"增量"通知，例如，仅为已对数据库表从上次通知这些更改。  
  
-   如果大量的行插入到数据库表中，适配器客户端可以配置多个接收到的负载平衡接收通知的位置。  
  
 适配器客户端收到的通知消息后，他们能够执行特定任务根据收到的通知的类型。 例如，它执行的任务，如果收到插入通知的一组和另一组任务的如果收到更新通知的方式可以设计 BizTalk 业务流程。  
  
> [!CAUTION]
>  如果没有在 Oracle 数据库和适配器客户端之间的网络中断，通知将不发送到适配器客户端的网络中断期间对 Oracle 数据库进行的更改并且之后。 因此，你必须使用轮询操作而不是关键方案的通知操作。  
  
 此部分中的主题提供有关如何配置每种方案的适配器的信息。 若要开始从 Oracle E-business Suite 使用获取通知[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，你必须指定特定的绑定属性。 有关与通知相关的绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 有关通知消息结构的详细信息，请参阅[通知操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-notification-operation2.md)。  
  
 用于 Oracle E-business Suite 从接收通知，请确保：  
  
-   你可以使用该适配器连接到受支持的 Oracle 数据库版本。 10.2 之前的 oracle 数据库版本不支持通知。  
  
-   **更改通知**权限，才能使用数据库更改通知的接收。  若要配置此特权，连接到 Oracle 数据库使用管理权限，然后在 SQL 提示符处键入以下命令。  
  
    ```  
    grant change notification to <user name>  
    ```  
  
-   决定在 TCP 端口上要 ODP.NET 用于接收从 Oracle 数据库的数据库更改通知。 将该端口添加到 Windows 防火墙例外列表。 有关如何将端口添加到 Windows 防火墙例外列表的说明，请参阅[http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)。 必须提供相同的端口号为**NotificationPort**绑定属性。 有关绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [接收使用 Oracle E-business Suite 适配器数据库更改通知时的注意事项](../../adapters-and-accelerators/adapter-oracle-ebs/before-you-receive-database-change-notifications-using-the-oracle-ebs-adapter.md)  
  
-   [处理通知邮件完成 Oracle E-business Suite 中的特定任务](../../adapters-and-accelerators/adapter-oracle-ebs/process-notification-messages-to-complete-specific-tasks-in-oracle-ebs.md)  
  
-   [接收 Oracle E-business Suite 更改通知以增量方式使用 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-change-notifications-incrementally-using-biztalk-server.md)  
  
-   [接收 Oracle E-business Suite 数据库更改通知上多个接收位置](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-on-multiple-receive-locations.md)  
  
-   [接收 Oracle E-business Suite 数据库更改通知后的接收位置细分](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-after-a-receive-location-stops.md)  
  
## <a name="see-also"></a>另请参阅  
[开发使用 Oracle E-business Suite 适配器的 BizTalk 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)