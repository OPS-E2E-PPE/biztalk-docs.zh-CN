---
title: Oracle E-business Suite 使用接收数据库更改通知 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e92520cf-c552-4225-abba-8e03f73ecf70
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6381e2c429763596e3aa5c1fd70619cae588b68d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991422"
---
# <a name="receive-oracle-e-business-suite-database-change-notifications-using-biztalk-server"></a>Oracle E-business Suite 使用接收数据库更改通知 BizTalk Server
你可以配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]从 Oracle E-business Suite 接收数据库更改通知消息。 可以指定适配器用于与 Oracle E-business Suite 的通知注册的 SELECT 语句。 针对通知，请注册的 SELECT 语句的结果集更改时，适配器将接收通知消息。 有关如何在适配器支持通知的详细信息，请参阅[接收使用 Oracle E-business Suite 适配器数据库更改通知时的注意事项](../../adapters-and-accelerators/adapter-oracle-ebs/before-you-receive-database-change-notifications-using-the-oracle-ebs-adapter.md)。  
  
 以下是可以在其中配置某些情况下[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]从 Oracle E-business Suite 接收通知：  
  
- 适配器客户端获取仅"递增"通知，例如，仅为那些自上次通知以来对数据库表所做的更改。  
  
- 如果大量的行插入到数据库表中，适配器客户端可以配置多个接收到的负载平衡接收通知的位置。  
  
  适配器客户端收到的通知消息后，他们可以执行特定任务根据收到的通知的类型。 例如，BizTalk 业务流程可以设计它执行的任务，如果插入通知接收到一组和另一组任务的如果收到更新通知方式。  
  
> [!CAUTION]
>  如果没有在 Oracle 数据库和适配器客户端之间的网络中断，通知将不会发送到适配器客户端的网络中断期间对 Oracle 数据库进行的更改，此后。 因此，您必须使用轮询操作而不是关键方案的通知操作。  
  
 在本部分中的主题提供有关如何配置每种方案的适配器的信息。 若要开始从 Oracle E-business Suite 使用获取通知[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，必须指定特定绑定的属性。 有关与通知相关的绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 有关通知消息的结构的详细信息，请参阅[通知操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-notification-operation2.md)。  
  
 用于 Oracle E-business Suite 中接收通知，请确保：  
  
-   使用适配器连接到受支持的 Oracle 数据库版本。 10.2 之前的 oracle 数据库版本不支持通知。  
  
-   **更改通知**是用于接收数据库更改通知需要权限。  若要配置此权限，连接到 Oracle 数据库使用管理权限，然后在 SQL 提示符处键入以下命令。  
  
    ```  
    grant change notification to <user name>  
    ```  
  
-   决定你想要用于从 Oracle 数据库接收数据库更改通知的 ODP.NET TCP 端口。 将该端口添加到 Windows 防火墙例外列表。 有关如何将端口添加到 Windows 防火墙例外列表的说明，请参阅[ http://go.microsoft.com/fwlink/?LinkID=196959 ](http://go.microsoft.com/fwlink/?LinkID=196959)。 必须提供的同一端口号**NotificationPort**属性绑定。 有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [接收使用 Oracle E-business Suite 适配器数据库更改通知时的注意事项](../../adapters-and-accelerators/adapter-oracle-ebs/before-you-receive-database-change-notifications-using-the-oracle-ebs-adapter.md)  
  
-   [处理通知消息来完成 Oracle E-business Suite 中的特定任务](../../adapters-and-accelerators/adapter-oracle-ebs/process-notification-messages-to-complete-specific-tasks-in-oracle-ebs.md)  
  
-   [接收 Oracle E-business Suite 更改通知以增量方式使用 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-change-notifications-incrementally-using-biztalk-server.md)  
  
-   [接收 Oracle E-business Suite 数据库更改通知上多个接收位置](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-on-multiple-receive-locations.md)  
  
-   [接收 Oracle E-business Suite 数据库更改通知后的接收位置中断](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-after-a-receive-location-stops.md)  
  
## <a name="see-also"></a>请参阅  
[开发 BizTalk 应用程序使用 Oracle E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)