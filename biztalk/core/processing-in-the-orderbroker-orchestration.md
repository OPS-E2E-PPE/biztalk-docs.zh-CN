---
title: "在 OrderBroker 业务流程处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- orchestrations, nested scopes
- nested scopes, performance
- processing, examples
- nested scopes, orchestrations
- orchestrations, performance
- performance, orchestrations
- performance, nested scopes
- examples, orchestration processing [process management solution]
- scopes, nesting
ms.assetid: c296e00c-b3ad-4161-baf7-258899185c34
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c6a6571ece3190b6195b207b4c45969ce25ddec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="processing-in-the-orderbroker-orchestration"></a>OrderBroker 业务流程中的处理
本部分介绍如何**OrderBroker**业务流程接受订单和准备进程管理器。 本部分首先介绍了该业务流程的日常工作。 随后的部分将介绍该业务流程如何处理消息。 然后，将重点介绍该业务流程如何使用原子事务来提高性能。  
  
> [!NOTE]
>  由于的长度的长度**OrderBroker**代码中，你可能想要阅读此部分与 Microsoft® Visual Studio 中打开业务流程。  
  
## <a name="why-an-order-broker"></a>为什么使用 OrderBroker？  
 用途**OrderBroker** orchestration 是预处理订单，并将它路由到正确的进程管理器。 上述预处理包括为历史记录数据库、服务系统以及确认订单的接收生成信息性消息。 **OrderBroker**还从客户服务请求创建泛型订单消息。 这种订单规范化允许订单通用于业务流程的各个元素。  
  
 订单消息是包含独立于订单信息的路由信息的多部分消息。 路由信息也是通用的，其设计为可供任何订单管理器使用。 从而，可以更方便地扩展解决方案。 多部分消息有关的信息，请参阅[如何使用多部分消息类型](../core/how-to-use-multi-part-message-types.md)。  
  
 通过将执行 Broker 功能与其他功能相隔离，您也可以将该功能移至其他 BizTalk 组。 因为**OrderBroker**将发布到 MessageBox 数据库-即，它是直接绑定-还简化了将 broker 放置在另一个组-可以移动 broker 而无需更改业务流程。 有关详细信息将放置**OrderBroker**在另一个组中，请参阅[OrderBroker 和 OrderManager 之间的通信](../core/communication-between-orderbroker-and-ordermanager.md)。  
  
> [!NOTE]
>  **OrderBroker**业务流程，因为它具有只有一个**OrderManager**能够与通信，只需将常量字符串以**OrderMgrType**字段的顺序管理器消息。 通常，在存在多个订单管理器的应用程序中，该应用程序将使用业务规则引擎来确定此字段的适当值和订单路由。 有关业务规则引擎的详细信息，请参阅[创建和使用业务规则](../core/creating-and-using-business-rules.md)。  
  
## <a name="order-processing"></a>订单处理  
 **OrderBroker** orchestration 开头两个**接收**内的形状**侦听**形状。 一个**接收**形状将消息从客户支持系统; 从供应商系统的其他消息。 来自任一来源的消息都具有相同的架构。  
  
 业务流程从消息中提取的寄信人地址并使用它来设置的动态端口地址**CSRPort**。 该业务流程使用此端口来发送确认和错误消息。  
  
 中的下一个步骤**OrderBroker**业务流程创建历史记录消息、 服务消息，确认消息中，和订单消息将发送到**OrderManager**业务流程。 业务流程使用**InsertOrderBody**实用工具函数，用于将订单消息添加到历史记录消息。  
  
> [!NOTE]
>  在某些情况下，解决方案可能会生成已传送但未使用的消息。 OrderBroker 业务流程使用发送端口将信息插入历史记录数据库中。 此发送端口使用送达通知。 配置将发送端口映射到包含两个端口的发送端口组-一个用于测试配置端口 (**HistoryInsert 测试 SP**)，一个用于常规配置 (**HistoryInsert SP**)。 如果将该组中的两个端口都保持运行状态，则解决方案将在这两个端口上发送消息。 因而，该解决方案将请求两个送达通知，但仅处理其中一个通知。  
>   
>  若要避免这种情况下，取消登记测试端口 (**HistoryInsert 测试 SP**)，或停止测试版本的应用程序， **BTSScn.BPM.OrderBrokerApp.Test**。 有关传递通知的详细信息，请参阅[使用确认](../core/using-acknowledgments.md)。  
  
 构造要发送到的消息时**OrderManager**业务流程、 **OrderBroker**业务流程创建包含两个部分的多个部分的消息。 其中一个部分包含路由信息，另一个部分包含订单自身。 该消息的路由部分**OrderMgrMsg.Routing**，使用由 C# 类中定义了架构**SchemaClasses**程序集。 为泛型时，消息的一部分或类型不可知的顺序，XML 文档，则代理会将 (**System.Xml.XmlDocument**) 并将它分配给**OrderMgrMsg.Order**。  
  
 路由的信息对顺序管理器中，尤其是重要的两个字段**OrderMgrMsg.Routing.OrderMgrType**和**OrderMgrMsg.Routing.Status**。 Broker 集**OrderMgrType**为是处理顺序的顺序管理器的类型。 在该解决方案中只有一个订单管理器，并且该字段设置为 CABLEORDER。 代理还将设置**状态**字段已接受。 此字段是用于通知订单管理器该消息为新订单的值。 在解决方案中，订单管理器**OrderManager**业务流程，使用**接收**筛选器的步骤顺序类型等于 CABLEORDER 和等于已接受的状态的形状。  
  
 中的其余步骤**OrderBroker**业务流程将不同的消息发送到相应的端口。  
  
## <a name="improving-performance-with-nested-scopes"></a>使用嵌套的作用域提高性能  
 有关值得注意的要点之一**OrderBroker** orchestration 是其使用嵌套的作用域。 嵌套作用域的部分用途是通过限制持久化点来提高性能。  
  
 业务流程引擎将定期保存整个业务流程在称为持久化点的执行点时的状态。 业务流程引擎会自动将多个业务流程形状，包括**发送**形状，作为持久性点。 持久性点和有关它们的详细信息的列表，请参阅[持久性和业务流程引擎](../core/persistence-and-the-orchestration-engine.md)。  
  
 具有五个**发送**形状， **OrderBroker** orchestration 应具有五个持久性点。 但是，当组**发送**在原子事务范围内的形状，引擎能够识别，只需一个持久点的范围。 因为这四个**发送**中的形状**OrderBroker**业务流程不是异常处理程序的一部分，并且无需完成后发送，他们就可以在原子事务范围内。 这样将会减少持久化点数。 有关原子事务的详细信息，请参阅[原子事务](../core/atomic-transactions.md)。  
  
 此外，如果嵌套事务都在同一时间结束，则业务流程引擎将为这些事务使用单个持久化点。 因此的方式**OrderBroker** orchestration 嵌套事务进一步减少持久性点： 该业务流程没有单个暂留点由于使用了**作用域**形状。  
  
> [!TIP]
>  可以通过最大限度地减少业务流程中的持久化点来提高性能。 你可以分组**发送**形状在原子事务以生成单个暂留点的所有**发送**形状。 如果同时结束嵌套事务作用域，将会为这些事务生成单个持久化点。  
  
 原子事务作用域不能具有异常处理程序。 因此，该业务流程将原子作用域嵌套在长期事务中。 此外部事务可以异常处理程序，并且它是此处理程序处理中的发生异常**发送**形状。  
  
> [!TIP]
>  将原子事务嵌套在长期事务中是允许进行异常处理的通用模式。  
  
## <a name="see-also"></a>另请参阅  
 [在业务流程管理解决方案中进行处理](../core/processing-in-the-business-process-management-solution.md)   
 [过程管理器逻辑](../core/process-manager-logic.md)   
 [中断业务流程管理解决方案中的处理](../core/interrupt-handling-in-the-business-process-management-solution.md)   
 [ExceptionHandler 业务流程](../core/the-exceptionhandler-orchestration.md)