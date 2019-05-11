---
title: 在 OrderBroker 业务流程中处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d21d91cb8d03adadbd93296f1875efb681b674b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255199"
---
# <a name="processing-in-the-orderbroker-orchestration"></a>OrderBroker 业务流程中处理
本部分介绍如何**OrderBroker**业务流程获取订单并做好准备，进程管理器。 本部分首先讨论该业务流程的日常工作。 下一部分讨论该业务流程如何处理一条消息。 它然后突出显示了业务流程如何使用原子事务来提高性能。  
  
> [!NOTE]
>  由于的长度的长度**OrderBroker**代码中，你可能想要阅读此部分与 Microsoft® Visual Studio 中打开业务流程。  
  
## <a name="why-an-order-broker"></a>为什么使用 Orderbroker？  
 目的**OrderBroker**业务流程是预处理订单并将其路由到正确的进程管理器。 预处理包括生成的历史记录数据库、 服务系统以及确认订单的接收的信息性消息。 **OrderBroker**还从客户服务请求创建通用的订单消息。 此订单规范化允许订单的泛型消耗由业务流程的元素。  
  
 订单消息是分开的订单信息的路由信息的多部分消息。 路由信息也是泛型，旨在供任何订单管理器。 这进而使更方便地扩展解决方案。 有关多部分消息的信息，请参阅[如何使用多部分消息类型](../core/how-to-use-multi-part-message-types.md)。  
  
 隔离中转函数还可将其移到另一个 BizTalk 组。 因为**OrderBroker**将发布到 MessageBox 数据库 — 也就是说，它是直接绑定，还可以轻松将 broker 放在另一个组中即可移动 broker 而无需更改业务流程。 有关放置的详细信息**OrderBroker**中另一个组，请参阅[OrderBroker 和 OrderManager 之间的通信](../core/communication-between-orderbroker-and-ordermanager.md)。  
  
> [!NOTE]
>  **OrderBroker**业务流程，因为它具有只有一个**OrderManager**与进行通信，只需将分配一个常量字符串到**OrderMgrType**字段的顺序管理器消息。 通常情况下，在应用程序方面存在多个订单管理器，该应用程序将使用业务规则引擎来确定此字段和订单路由的正确值。 有关业务规则引擎的详细信息，请参阅[创建和使用业务规则](../core/creating-and-using-business-rules.md)。  
  
## <a name="order-processing"></a>订单处理  
 **OrderBroker**具有两个业务流程首先**接收**形状内**侦听**形状。 一个**接收**形状将消息从客户支持系统; 从供应商系统的其他消息。 来自任一来源的消息具有相同的架构。  
  
 业务流程从消息中提取返回地址，并使用它来设置动态端口地址**csrport 的地址**。 业务流程使用此端口来发送确认和错误消息。  
  
 下一步中的步骤**OrderBroker**业务流程创建历史记录消息、 服务消息、 确认消息和订单消息将发送到**OrderManager**业务流程。 该业务流程使用**InsertOrderBody**实用工具函数将订单消息添加到历史记录消息。  
  
> [!NOTE]
>  在某些情况下该解决方案可能会产生已传送但未使用的消息。 Orderbroker 业务流程使用发送端口以将信息插入历史记录数据库中。 此发送端口使用送达通知。 配置将发送端口映射到包含两个端口的发送端口组，一个用于测试配置端口 (**测试-HISTORYINSERT-SP**)，一个常规配置 (**HISTORYINSERT-SP**)。 如果将这两个端口中运行的组，该解决方案在这两个端口上发送消息。 因此，请求两个送达通知，但仅处理其中一个。  
>   
>  若要避免这种情况下，取消登记测试端口 (**测试-HISTORYINSERT-SP**)，或停止该应用程序的测试版本**BTSScn.BPM.OrderBrokerApp.Test**。 有关送达通知的详细信息，请参阅[使用确认](../core/using-acknowledgments.md)。  
  
 构造要发送到的消息时**OrderManager**业务流程， **OrderBroker**业务流程包含两个部分创建多部分消息。 一部分包含路由信息;另一个，本身的顺序。 该消息的路由部分**OrderMgrMsg.Routing**，使用的架构定义的C#类**SchemaClasses**程序集。 代理会将视为通用的消息的一部分或类型不明确的顺序、 XML 文档 (**System.Xml.XmlDocument**) 并将它分配给**OrderMgrMsg.Order**。  
  
 路由信息中尤其重要的订单管理器的两个字段 **: OrderMgrMsg.Routing.OrderMgrType**并**OrderMgrMsg.Routing.Status**。 Broker 集**OrderMgrType**到是要处理订单的订单管理器的类型。 在解决方案中，只有一个订单管理器和字段设置为 CABLEORDER。 Broker 还设置**状态**字段已接受。 这是告诉该消息为新订单的订单管理器的值。 在解决方案中，订单管理器**OrderManager**业务流程，使用**接收**筛选等于 CABLEORDER 和等于 ACCEPTED 的状态的订单类型的形状。  
  
 中的其余步骤**OrderBroker**业务流程将不同的消息发送到相应的端口。  
  
## <a name="improving-performance-with-nested-scopes"></a>使用嵌套作用域提高性能  
 有关值得注意的地方之一**OrderBroker**业务流程是其使用的嵌套作用域。 嵌套作用域有，部分，通过限制持久化点来提高性能。  
  
 业务流程引擎定期保存整个业务流程在称为持久化点的执行点的状态。 业务流程引擎自动将多个业务流程形状，包括**发送**形状视为持久化点。 有关持久化点和相关的详细信息的列表，请参阅[持久化和业务流程引擎](../core/persistence-and-the-orchestration-engine.md)。  
  
 具有五个**发送**形状**OrderBroker**该业务流程具有五个持久化点。 但是，分组**发送**原子事务作用域内的形状，则引擎将认为它只需要为作用域的一个持久化点。 因为这四个**发送**形状中**OrderBroker**业务流程不属于异常处理程序和无需完成在发送后，他们就可以访问在原子事务作用域中。 这样可以减少持久化点。 有关原子事务的详细信息，请参阅[原子事务](../core/atomic-transactions.md)。  
  
 此外，业务流程引擎将如果在同一时间结束所有事务的嵌套事务中使用单个持久化点。 因此，方式**OrderBroker**业务流程嵌套事务进一步减少暂留点： 业务流程只具有一个持久化点由于使用了**作用域**形状。  
  
> [!TIP]
>  可以通过尽量减少的业务流程中的持久化点来提高性能。 可以对其进行分组**发送**形状中的原子事务，以生成单个持久化点的所有**发送**形状。 结束嵌套的事务的范围限定在同一时间会生成单个持久化点的事务。  
  
 原子事务作用域不能具有异常处理程序。 因此，业务流程将嵌套在长时间运行事务的原子作用域。 此外部事务可以具有异常处理程序，并且该处理程序处理的异常**发送**形状。  
  
> [!TIP]
>  原子事务嵌套在长时间运行事务内是一种常见的模式，以允许进行异常处理。  
  
## <a name="see-also"></a>请参阅  
 [在业务流程管理解决方案中处理](../core/processing-in-the-business-process-management-solution.md)   
 [进程管理器逻辑](../core/process-manager-logic.md)   
 [业务流程管理解决方案中的中断处理](../core/interrupt-handling-in-the-business-process-management-solution.md)   
 [ExceptionHandler 业务流程](../core/the-exceptionhandler-orchestration.md)