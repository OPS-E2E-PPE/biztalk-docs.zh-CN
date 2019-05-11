---
title: 发布和订阅体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf90d1f0fe1ed298d42c6ed9b0cf1086abe8eb7f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398432"
---
# <a name="publish-and-subscribe-architecture"></a>发布和订阅体系结构
在发布/订阅设计中，您有三个组件：  
  
- “分发服务器属性”  
  
- 订阅服务器  
  
- 事件  
  
  发布方包括接收发布中到达的消息的端口及其接收位置，将消息发布时发布的发送端口发送消息或以异步方式启动另一个业务流程和要求/响应的业务流程在从目标应用程序或传输接收响应时的消息。  
  
  在 BizTalk Server 中，有两种主要类型的订阅： 激活和实例。 *激活订阅*是一个指定一条消息，可满足该订阅应激活，或创建订阅服务器收到后的新实例。 创建激活订阅的示例包括具有筛选器的发送端口或发送端口绑定到业务流程，和业务流程接收形状，将其激活属性设置为 true。 *实例订阅*指示应将执行订阅的消息路由到的订阅服务器已在运行的实例。 创建实例订阅的示例包括业务流程具有相关接收和请求/响应样式的接收端口等待来自 BizTalk Server 的响应。  
  
  两种类型在信息级别之间的区别是订阅的实例订阅包括存储在主 MessageBox 数据库订阅表中的唯一实例 ID。 在业务流程实例或接收端口完成处理之后，激活订阅仍保持活动状态，只要登记业务流程或发送端口时，实例订阅从 MessageBox 中删除。  
  
## <a name="creating-subscriptions"></a>创建订阅  
 通过在 BizTalk Server 中，在 BizTalk Server 管理数据库的 adm_ServiceClass 表中列出的服务类创建订阅。 这些服务包括缓存服务;进程内和独立消息传送，托管由终结点管理器中;和业务流程/XLANG 由 XLANG 子服务承载。 每个服务类可以创建订阅和接收已发布的消息。  
  
 订阅是比较语句，称为谓词，它涉及消息上下文属性和特定于订阅的值的集合。 例如，消息类型是消息和多个订阅的上下文属性在其订阅中指定的消息类型。 有关订阅的常规信息被插入到订阅表由消息代理，而特定谓词则进入以下谓词表中，具体取决于为订阅指定的操作的类型之一：  
  
- BitwiseANDPredicates  
  
- EqualsPredicates  
  
- EqualsPredicates2ndPass  
  
- ExistsPredicates  
  
- FirstPassPredicates  
  
- GreaterThanOrEqualsPredicates  
  
- GreaterThanPredicates  
  
- LessThenOrEqualsPredicates  
  
- LessThenPredicates  
  
- NotEqualsPredicates  
  
  所有这些都通过调用 Bts_CreateSubscription_\<应用程序名称\>和 Bts_InsertPredicate_\<应用程序名称\>存储的过程在 MessageBox 数据库的位置\<应用程序名称\>是创建订阅的 BizTalk 主机的名称。  
  
  当已登记的发送端口时，端口创建，至少一种订阅的任何消息，发送端口的传输 ID 的上下文中。 这样，要始终接收专门为它的消息的发送端口。 当业务流程端口绑定到特定的发送端口时，绑定的相关信息存储在 BizTalk 管理数据库。 从发送消息时通过绑定到物理端口的业务流程发送端口，传输 ID 包含在上下文，以便将消息路由到正确的发送端口。 但是，务必注意，此发送端口并不唯一发送端口可以接收发自该业务流程的消息。 当业务流程发送消息时，该消息发布到相关的升级属性的所有 MessageBox。 保证绑定的发送端口以接收消息的副本，因为传输 ID 是在上下文中，但任何其他发送端口或业务流程中，可以有也与消息属性相匹配的订阅。 它是非常重要，若要了解，一条消息直接发布到 MessageBox，任何时候具有匹配订阅的所有订阅服务器会收到该消息的副本。  
  
## <a name="publishing-and-routing"></a>发布和路由  
 创建订阅并将其启用后，任何处理之前，必须发布一条消息。 它们被接收到 BizTalk Server 从前面提到的服务之一时，发布消息。 有关路由的此讨论，我们将重点介绍通过适配器接收到 BizTalk Server 中的消息。  
  
 在消息经过接收管道处理，属性将升级到消息上下文。 一条消息已准备好接收适配器和管道处理后发布到 MessageBox 后，第一件事是消息代理将升级的属性的属性值和谓词值插入从消息到主 MessageBox SQL Server 数据库的上下文。 将这些值插入数据库中，则消息代理做出路由决策。  
  
 下一步是为消息代理请求主 MessageBox 数据库，若要查找当前要发布的消息批的订阅。 请记住，这些消息尚未尚未写入到数据库，仅从上下文属性。 Bts_FindSubscriptions 存储过程在 MessageBox 查询中的订阅和谓词表，以上所示将其链接到存储的当前消息批的消息属性。  
  
 使用此信息，消息代理将消息插入一次通过调用 bts_InsertMessage 存储过程具有订阅的每个 MessageBox 数据库。 使用订阅 id。 首先调用 bts_InsertMessage 存储过程 在此第一个阶段中，存储的过程调用 int_EvaluateSubscriptions 存储过程负责查找订阅详细信息，验证消息通过检查符合的应用程序的安全要求消息谓词与应用程序属性匹配的主机，并在应用程序特定队列或根据状态应用程序特定的挂起的队列中插入到消息的引用。 消息 ID、 订阅 ID、 服务 ID 和其他订阅信息插入到每个订阅已发现的此应用程序的应用程序特定队列表。 插入消息后，消息属性和消息谓词表清除的批处理相关的值。  
  
 随后的消息中的每个部分调用 bts_InsertMessage 存储过程。 在首次调用中，消息上下文传递，然后插入到数部分、 正文部分名称和 id。 如消息有关的元数据以及后台处理表 除了消息正文部分插入到 PARTS 表使用 int_InsertPart 存储过程。 然后，他们只需传递给要在 PARTS 表中保留的 int_InsertPart 存储过程的剩余消息部分的每个调用 bts_InsertMessage 存储过程。  
  
 在路由消息后, 接收的消息，并且其各个部分的特定实例将记录插入到以下表的每个服务添加引用：  
  
- MessageRefCountLog1  
  
- MessageRefCountLog2  
  
- PartRefCountLog1  
  
- PartRefCountLog2  
  
  这些引用将保护消息和部分定期运行，以防止 MessageBox 添满不再是系统中的消息的消息数据的清除作业被删除。 两个表用于减少争用和锁定问题。  
  
  现在，已将消息路由到相应的队列，存储在 Spool 和 Parts 表中，且在应用程序特定队列，被引用的消息必须将请求从队列的应用程序实例。 每个主机实例已在 BizTalk 管理数据库的 adm_ServiceClass 表中配置的时间间隔连续轮询数据库的出列线程的数目。 此相同的表有一个列，指示要使用的出列线程的数目。 每个线程调用到 MessageBox 数据库，并调用 bts_DequeueMessages_\<应用程序名称\>存储过程适用于主机应用程序中运行。 此存储的过程使用锁定语义来确保只有一个实例并且一个出列线程能够在给定时间中队列的消息进行操作。 获取该锁的主机实例获取的消息，随后负责将该消息传送到所针对的子服务。  
  
  如果接收消息的服务终结点管理器，然后调用发送端口 （或请求/响应的响应部分接收端口），并且它是 XLANG/s 子服务，业务流程是创建，或定位到服务的订阅具体取决于订阅中没有实例 ID。 服务然后释放对消息和其部分的引用，因此，如果没有其他服务引用的可以删除消息数据。  
  
## <a name="see-also"></a>请参阅  
 [消息引擎 ](../core/the-messaging-engine.md)