---
title: "发布和订阅体系结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- publish/subscribe architecture, publishers
- architecture, publish/subscribe
- publishing, publish/subscribe architecture
- publish/subscribe architecture, about publish/subscribe architecture
- creating, subscriptions
- publish/subscribe architecture, Messaging Engine
- routing, publishing
- Messaging Engine, publishing
- publish/subscribe architecture, subscribers
- publish/subscribe architecture
- subscriptions, publish/subscribe architecture
- publish/subscribe architecture, creating subscriptions
- subscriptions, creating
- Messaging Engine, subscribing
- publishing, routing
- Messaging Engine, publish/subscribe architecture
- publish/subscribe architecture, events
ms.assetid: 5ed36c1f-077d-468f-a99e-60f97377cef6
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b11ed175fc047eee59761547d8d13ab798ac860c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="publish-and-subscribe-architecture"></a>发布和订阅体系结构
在发布/订阅设计中，您可以使用以下三个组件：  
  
-   发布服务器  
  
-   订阅服务器  
  
-   事件  
  
 发布服务器包括接收发布中到达的消息的端口其接收位置，将消息发布发送消息或以异步方式启动另一个业务流程和请求/响应发送端口发布时的业务流程在从目标应用程序或传输收到响应时的消息。  
  
 在 BizTalk Server 中，有两种主要类型的订阅： 激活和实例。 *激活订阅*一个指定的满足订阅的消息应激活，或者创建，订阅服务器时收到的新实例。 创建激活订阅的示例包括具有筛选器的发送端口或绑定到业务流程的发送端口，以及将其“激活”属性设置为 True 的业务流程接收形状。 *实例订阅*指示应将满足订阅的消息路由到的订阅服务器已在运行的实例。 创建实例订阅的示例包括具有相关接收的业务流程和等待来自 BizTalk Server 的响应的请求/响应样式的接收端口。  
  
 这两种类型的订阅在信息级别上的区别在于：实例订阅包括存储于主 MessageBox 数据库的订阅表中的唯一实例 ID。 在业务流程实例或接收端口完成处理之后，只要登记了业务流程或发送端口，就会从 MessageBox 中删除实例订阅，而激活订阅仍保持活动状态。  
  
## <a name="creating-subscriptions"></a>创建订阅  
 订阅是由 BizTalk Server 中的服务类别创建的，而这些类别在 BizTalk Server 管理数据库的 adm_ServiceClass 表中列出。 这些服务包括缓存服务；终结点管理器宿主的正在处理的和已隔离的消息，以及 XLANG 子服务宿主的业务流程/XLANG。 其中每个服务类可以创建订阅并接收已发布的消息。  
  
 订阅为多个比较语句的集合，称作谓词，它涉及消息上下文属性和专用于订阅的值。 例如，“消息类型”为消息的上下文属性，而且许多订阅均可在其自己的订阅中指定消息类型。 有关订阅的常规信息可由消息代理插入到订阅表中，而特定的谓词则进入以下任一谓词表中，具体取决于为订阅指定的操作类型：  
  
-   BitwiseANDPredicates  
  
-   EqualsPredicates  
  
-   EqualsPredicates2ndPass  
  
-   ExistsPredicates  
  
-   FirstPassPredicates  
  
-   GreaterThanOrEqualsPredicates  
  
-   GreaterThanPredicates  
  
-   LessThenOrEqualsPredicates  
  
-   LessThenPredicates  
  
-   NotEqualsPredicates  
  
 上述所有操作均可以通过调用 Bts_CreateSubscription_\<应用程序名称\>和 Bts_InsertPredicate_\<应用程序名称\>MessageBox 中的存储的过程数据库 where \<应用程序名称\>是创建订阅的 BizTalk 主机的名称。  
  
 在登记发送端口时，端口应使用上下文中该发送端口的传输 ID 为每个消息至少创建一个订阅。 这允许发送端口始终接收专门发送到该端口的消息。 在业务流程端口绑定到特定的发送端口后，该绑定的相关信息将存储在 BizTalk 管理数据库中。 在从业务流程通过绑定到物理发送端口的端口发送消息时，传输 ID 将包括在上下文中，以便该消息能够路由到正确的发送端口。 但是，请注意，此发送端口并不是可以接收发自该业务流程的消息的唯一发送端口。 在业务流程发送消息时，该消息及其所有相关的升级属性都将发布到 MessageBox 中。 由于消息的传输 ID 位于上下文中，所以可确保绑定的发送端口接收该消息的副本，虽然任何其他发送端口或业务流程也具有与该消息属性相匹配的订阅。 此外，请务必了解在将消息直接发布到 MessageBox 的任何时候，所有具有匹配的订阅的订阅服务器都将接收该消息副本。  
  
## <a name="publishing-and-routing"></a>发布和路由  
 在创建和启用订阅后，在处理消息前必须先发布该消息。 在从上述的服务之一中将消息接收到 BizTalk Server 中后，发布这些消息。 对于此路由的相关讨论，我们将侧重于通过适配器接收到 BizTalk Server 中的消息。  
  
 在消息经过接收管道处理后，其属性将升级到消息上下文中。 经过接收适配器和管道处理过的消息，在准备发布到 MessageBox 时，消息代理会首先将消息上下文中的升级属性的属性值和谓词值插入到主 MessageBox SQL Server 数据库中。 如果将这些值插入数据库中，则消息代理可进行路由选择。  
  
 下一步是消息代理请求主 MessageBox 数据库查找当前要发布的消息批的订阅。 但是请注意，此时，这些消息尚未写入数据库，只有上下文中的属性写入了数据库。 MessageBox 中的 bts_FindSubscriptions 存储过程可对上面提及的订阅和谓词表进行查询，并将这些表链接到为当前消息批存储的消息属性。  
  
 利用这些信息，消息代理通过调用 bts_InsertMessage 存储过程将消息一次性插入到每个具有订阅的 MessageBox 数据库中。 Bts_InsertMessage 存储过程首次调用替换为订阅 id。 在此第一个阶段中，存储的过程调用 int_EvaluateSubscriptions 存储过程负责查找订阅详细信息，验证消息通过检查，可满足的应用程序的安全要求谓词对于主机，和在应用程序特定队列或根据的状态的应用程序的特定挂起的队列中插入消息的引用匹配应用程序属性的消息。 消息 ID、订阅 ID、服务 ID 和其他订阅信息都将插入到为此应用程序找到的每个订阅的特定于应用程序的队列表中。 在插入这些消息后，将清除消息属性和消息谓词表中与批相关的值。  
  
 随后，为消息中的每个部分调用 bts_InsertMessage 存储过程。 在首次调用中，消息上下文传递，然后会插入到如数部件、 正文部分组成的名称和 id。 消息有关的元数据一起假脱机表 此外消息正文部分插入到部件表使用 int_InsertPart 存储过程。 随后，为每个剩余的消息部分调用 bts_InsertMessage 存储过程，其中，这些消息部分只传递到要在 PARTS 表中保留的 int_InsertPart 存储过程。  
  
 在路由消息后，通过将记录插入到下表中为每个接收特定消息实例以及消息的各个部分的服务添加引用：  
  
-   MessageRefCountLog1  
  
-   MessageRefCountLog2  
  
-   PartRefCountLog1  
  
-   PartRefCountLog2  
  
 这些引用将保护消息以及消息的各个部分不被清除作业删除，该清除作业将定期运行以防系统中无用消息的消息数据添满 MessageBox。 使用两个表可减少争用和锁定问题。  
  
 既然消息已路由到相应的队列、已存储在 SPOOL 和 PARTS 表中、并在特定于应用程序的队列中已引用该消息，则必须通过应用程序实例将这些消息从队列中提取出来。 每个主机实例都具有多个出列线程，这些出列线程将按照在 BizTalk 管理数据库的 adm_ServiceClass 表中配置的时间间隔连续轮询数据库。 此相同的表中有一列指明了要使用的出列线程的数目。 每个线程调用到 MessageBox 数据库，并调用 bts_DequeueMessages_\<应用程序名称\>存储过程适用于在运行主机应用程序。 此存储的过程使用锁定语义来确保只有一个实例，一个取消排队线程能够在给定时间在队列中的邮件上运行。 取得锁定的主机实例将获取消息，并负责将该消息传送到所需的子服务。  
  
 如果接收消息的服务为终结点管理器，则将调用发送端口（或请求/响应接收端口的响应部分），如果此服务是 XLANG/s 子服务，则可创建业务流程，或查找业务流程以为订阅提供服务，具体取决于订阅中是否存在实例 ID。 然后，此服务将释放对消息及其各个部分的引用，如果没有其他服务引用该消息，则可删除其数据。  
  
## <a name="see-also"></a>另请参阅  
 [消息传送的引擎](../core/the-messaging-engine.md)