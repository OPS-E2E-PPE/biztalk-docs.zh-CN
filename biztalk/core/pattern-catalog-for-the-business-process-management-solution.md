---
title: 模式的业务流程管理解决方案的目录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Canonical Message pattern [process management solutions]
- Nested Scopes pattern [process management solutions]
- Filter pattern [process management solutions]
- Per-Instance Pipeline Configuration pattern [process management solutions]
- Translator pattern, process management solutions
- patterns [process management solutions], pattern types
- Interruptible Orchestration pattern [process management solutions]
- Decoupled Orchestration pattern [process management solutions]
- Code Retry and Exception Handling pattern [process management solutions]
- Process Manager pattern [process management solutions]
- Asynchronous Reply pattern [process management solutions]
- Custom Exceptions pattern [process management solutions]
- Message Broker pattern [process management solutions]
- Coordination Using Delivery Notification pattern [process management solutions]
- Convoy pattern [process management solutions]
- Versioning pattern [process management solutions]
- Error Routing pattern [process management solutions]
- Application Reference pattern [process management solutions]
- Inverse Direct Partner Binding pattern [process management solutions]
ms.assetid: 246b109e-6006-404d-88b9-e6324ce3473c
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed13b415b0bb026f9c948cafbd48c1fa3e73a3cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291899"
---
# <a name="pattern-catalog-for-the-business-process-management-solution"></a>业务流程管理解决方案的模式目录
在业务流程管理解决方案中的模式包括 BizTalk Server，以及在前面部分中的企业集成模式编程通用的模式。 本部分中的列表包括这两种类型的模式。  
  
## <a name="pattern-types"></a>模式类型  
 以下条目简要介绍一下这个模式，并指向说明该解决方案如何使用此模式的其他主题。 在常规模式，例如筛选器的情况下条目指向更多常规主题。  
  
### <a name="application-reference-patterns"></a>应用程序引用模式  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使应用程序能够通过添加对其他应用程序的引用在同一组中的另一个应用程序中使用的项目。 业务流程管理解决方案的测试解决方案时和在主解决方案设计中使用应用程序的引用。 在解决方案中的应用程序引用的详细信息，请参阅[业务流程管理解决方案中的某些设计原则](../core/some-design-principles-in-the-business-process-management-solution.md)。  
  
### <a name="asynchronous-reply-patterns"></a>异步答复模式  
 订单管理器与订单处理阶段之间的通信是异步的。 也就是说，该管理器将继续处理直到接收答复。 阶段使用自相关动态端口发送到管理器的答复。 自相关端口无需为订单管理器来管理相关集。 该端口的动态功能允许订单管理器将向订单阶段发送答复的端口地址。 在解决方案中的端口的详细信息，请参阅[订单流通过进程管理器](../core/order-flow-through-the-process-manager.md)。  
  
### <a name="canonical-message-patterns"></a>规范化消息模式  
 若要简化处理解决方案通常将为内部格式转换外部的消息。 此格式是一个规范化消息的示例。 Orderbroker 业务流程将所有订单消息都转换成一个或多个规范化订单消息。 订单管理器业务流程和处理阶段使用此通用订单格式。 有关详细信息，请参阅[在 OrderBroker 业务流程中处理](../core/processing-in-the-orderbroker-orchestration.md)。  
  
### <a name="code-retry-and-exception-handling-patterns"></a>代码重试和异常处理模式  
 该解决方案可集中管理其异常处理中的大部分**ExceptionHandler**业务流程。 该解决方案使用整个此业务流程有机会时，与已删除的网络连接，如果重试该操作可能成功的一样。 该业务流程使用**Recaller**对象重新运行失败的代码。 有关业务流程的详细信息，请参阅[业务流程管理解决方案中的异常处理](../core/exception-handling-in-the-business-process-management-solution.md)。 另请参阅[ExceptionHandler 业务流程](../core/the-exceptionhandler-orchestration.md)。 有关使用的详细信息**Recaller**对象，请参阅[Recaller 对象](../core/the-recaller-object.md)。  
  
### <a name="convoy-pattern"></a>保护模式  
 订单管理器业务流程 OrderManager，使用保护模式来捕获和处理对正在处理的订单的后续更改。 有关订单管理器中的保护模式的详细信息，请参阅"订单更新"中[订单流通过进程管理器](../core/order-flow-through-the-process-manager.md)。  
  
### <a name="coordination-using-delivery-notification"></a>协调使用送达通知  
 **OrderBroker**业务流程使用送达通知来确保之前第二个订单处理阶段更新历史记录历史记录数据库中生成一个条目 (**CableOrder2**)。 详细信息，请参阅"协调阶段"中[订单流通过进程管理器](../core/order-flow-through-the-process-manager.md)。 有关送达通知的常规信息，请参阅[使用确认](../core/using-acknowledgments.md)。  
  
### <a name="custom-exceptions-pattern"></a>自定义异常模式  
 对于无法重试的异常，该解决方案使用常用的 BizTalk Server 异常处理和自定义异常处理。 自定义异常处理提供了更具体的异常处理。 它还用作嵌套作用域，以确保所有操作部分都回滚之间的标志。 有关该解决方案使用自定义异常的详细信息，请参阅[自定义异常](../core/custom-exceptions.md)。 有关作用域的详细信息，请参阅[如何配置作用域形状](../core/how-to-configure-the-scope-shape.md)。  
  
### <a name="decoupled-orchestration-patterns"></a>分离业务流程模式  
 在业务流程管理解决方案的设计分离到可能的最大限度的业务流程。 分离业务流程，使其更易于解决方案的版本部分并简化部分移动到其他服务器或组解决方案。 有关 orderbroker 和 ordermanager 之间的关系的详细信息，请参阅[在 OrderBroker 业务流程中处理](../core/processing-in-the-orderbroker-orchestration.md)并[订单流通过进程管理器](../core/order-flow-through-the-process-manager.md)。  
  
### <a name="error-routing-pattern"></a>错误路由模式  
 该解决方案使用新的 BizTalk Server 错误报告功能。 此功能失败消息路由给订阅端口，以便进行报告或处理。 有关错误报告的常规信息，请参阅[使用失败消息路由](../core/using-failed-message-routing.md)。  
  
### <a name="filter-pattern"></a>筛选器模式  
 筛选器模式可以选择符合特定处理条件的消息。 在 BizTalk 中，筛选模式几乎总是会变为一个端口上的某个筛选器表达式。 有关端口的筛选器的详细信息，请参阅[使用筛选器与接收消息形状](../core/using-filters-with-the-receive-message-shape.md)。  
  
### <a name="interruptible-orchestration-pattern"></a>可中断业务流程模式  
 该解决方案首先中断当前订单处理订单更新或取消。 在解决方案中的业务流程使用 Interrupt 业务流程来处理中断。 有关详细信息，请参阅[业务流程管理解决方案中的中断处理](../core/interrupt-handling-in-the-business-process-management-solution.md)。  
  
### <a name="inverse-direct-partner-binding-pattern"></a>反转直接合作伙伴绑定模式  
 该解决方案可反转直接绑定使分离订单处理的订单管理器中的各个阶段使用。 有关反转直接绑定的详细信息，请参阅[反转直接合作伙伴绑定](../core/inverse-direct-partner-binding.md)。  
  
### <a name="message-broker-pattern"></a>Message Broker 模式  
 Message broker 模式允许由解决方案确定消息的目标，以便发送方不需要知道目标。 业务流程管理解决方案来实现的 message broker **OrderBroker**业务流程。 **OrderBroker**业务流程获取订单，确定所订购的服务的类型并将订单路由到正确的顺序管理器。 有关详细信息中执行 message broker **OrderBroker**，请参阅[在 OrderBroker 业务流程中处理](../core/processing-in-the-orderbroker-orchestration.md)。  
  
### <a name="nested-scopes-pattern"></a>嵌套作用域模式  
 **OrderBroker**业务流程使用嵌套作用域来最大程度减少持久化点，因此，为了提高效率。 详细信息，请参阅"使用嵌套作用域提高性能"中[在 OrderBroker 业务流程中处理](../core/processing-in-the-orderbroker-orchestration.md)。  
  
### <a name="per-instance-pipeline-configuration"></a>每个实例的管道配置  
 尽管该解决方案使用默认管道，它可以广泛使用新的每个实例管道配置来指定信封的消息。 有关详细信息，请参阅[如何部署管道](../core/how-to-deploy-pipelines.md)并[业务流程管理解决方案的组件](../core/components-of-the-business-process-management-solution.md)。  
  
### <a name="process-manager-pattern"></a>进程管理器模式  
 该解决方案使用相对通用的订单管理器来控制通过各个订单处理阶段流。 这有助于将业务逻辑与订单流程的管理分开。 有关 OrderManager 业务流程如何用作流程管理器的详细信息，请参阅[进程管理器逻辑](../core/process-manager-logic.md)。  
  
### <a name="terminate-shape-at-end-of-orchestration"></a>终止业务流程末尾的形状  
 多个业务流程使用终止形状来结束发生错误时，即使该业务流程将具有通常在该点结束。 终止形状可以跟踪失败的实例和错误。 有关详细信息，请参阅[自定义异常](../core/custom-exceptions.md)。  
  
### <a name="translator-pattern"></a>转换器模式  
 转换器的企业模式 — 即的一条消息从一个格式转换为另一种形式 — 经常翻译为 BizTalk 映射。 有关 BizTalk 映射的常规信息，请参阅[创建映射使用 BizTalk 映射器](../core/creating-maps-using-biztalk-mapper.md)。  
  
### <a name="versioning-patterns"></a>版本控制模式  
 业务流程管理解决方案旨在简化解决方案组件通过分离业务流程和使用版本编号架构命名空间中的版本控制。 有关详细信息，请参阅[业务流程管理解决方案进行版本控制](../core/versioning-the-business-process-management-solution.md)。  
  
## <a name="see-also"></a>请参阅  
 [业务流程管理解决方案中的模式](../core/patterns-in-the-business-process-management-solution.md)