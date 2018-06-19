---
title: 模式的业务流程管理解决方案的目录 |Microsoft 文档
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
ms.openlocfilehash: 22b352cce73e45103437407a013691e604b7b959
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22266413"
---
# <a name="pattern-catalog-for-the-business-process-management-solution"></a>业务流程管理解决方案的模式目录
业务流程管理解决方案中的模式包括 BizTalk Server 编程的通用模式和前面部分中的企业集成模式。 本部分中的列表包括这两种类型的模式。  
  
## <a name="pattern-types"></a>模式类型  
 以下条目对模式进行了简要说明，并指向说明该解决方案如何使用此模式的其他主题。 在使用常规模式（例如筛选器）的情况下，条目将指向更多常规主题。  
  
### <a name="application-reference-patterns"></a>应用程序引用模式  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使应用程序使用同一组中的其他应用程序中的项目，通过添加对其他应用程序的引用。 业务流程管理解决方案在设计测试解决方案时和在主解决方案中使用应用程序引用。 有关在解决方案中的应用程序引用的详细信息，请参阅[业务流程管理解决方案中的某些设计原则](../core/some-design-principles-in-the-business-process-management-solution.md)。  
  
### <a name="asynchronous-reply-patterns"></a>异步答复模式  
 订单管理器与订单处理阶段之间的通信是异步进行的。 也就是说，在接收到答复之前，管理器会一直执行处理操作。 这些阶段使用自相关动态端口向管理器发送答复。 使用自相关端口可使订单管理器无需管理相关集。 端口的动态功能允许订单管理器向订单阶段发送端口地址，以便进行答复。 在解决方案中的端口的详细信息，请参阅[顺序流通过进程管理器](../core/order-flow-through-the-process-manager.md)。  
  
### <a name="canonical-message-patterns"></a>规范化消息模式  
 为了简化处理过程，解决方案通常会将外部消息翻译为内部格式。 此格式是一个规范化消息的示例。 OrderBroker 业务流程可将所有订单消息翻译为一种或多种规范化订单消息。 OrderManager 业务流程和处理阶段将使用此通用订单格式。 有关详细信息，请参阅[OrderBroker 业务流程中的处理](../core/processing-in-the-orderbroker-orchestration.md)。  
  
### <a name="code-retry-and-exception-handling-patterns"></a>代码重试和异常处理模式  
 该解决方案可集中管理其中的异常处理大部分**ExceptionHandler**业务流程。 当存在可通过重试来解决操作失败的情况时（例如网络连接中断），该解决方案将使用此业务流程。 业务流程使用**Recaller**对象重新运行失败的代码。 有关业务流程的详细信息，请参阅[业务流程管理解决方案中的异常处理](../core/exception-handling-in-the-business-process-management-solution.md)。 另请参阅[ExceptionHandler Orchestration](../core/the-exceptionhandler-orchestration.md)。 有关详细信息的使用**Recaller**对象，请参阅[Recaller Object](../core/the-recaller-object.md)。  
  
### <a name="convoy-pattern"></a>保护模式  
 OrderManager 业务流程使用保护模式来捕获和处理对正在处理的订单所做的后续更改。 有关在订单管理器中的保护模式的详细信息，请参阅"顺序更新"中[顺序流通过进程管理器](../core/order-flow-through-the-process-manager.md)。  
  
### <a name="coordination-using-delivery-notification"></a>使用送达通知进行协调  
 **OrderBroker**业务流程使用传递通知，以确保之前通过第二个订单处理阶段更新历史记录历史记录数据库中生成一个条目 (**CableOrder2**)。 有关详细信息，请参阅"协调与阶段"中[顺序流通过进程管理器](../core/order-flow-through-the-process-manager.md)。 有关传递通知的常规信息，请参阅[使用确认](../core/using-acknowledgments.md)。  
  
### <a name="custom-exceptions-pattern"></a>自定义异常模式  
 对于无法重试的异常，该解决方案将组合使用通用 BizTalk Server 异常处理和自定义异常处理。 自定义异常处理提供了更具体的异常处理功能。 它也用作嵌套作用域之间的标志，以确保回滚所有操作部分。 有关解决方案的使用自定义例外的详细信息，请参阅[自定义异常](../core/custom-exceptions.md)。 有关作用域的详细信息，请参阅[如何配置作用域形状](../core/how-to-configure-the-scope-shape.md)。  
  
### <a name="decoupled-orchestration-patterns"></a>分离业务流程模式  
 业务流程管理解决方案的设计会最大限度地尽可能分离业务流程。 通过分离业务流程，可以更方便地对业务流程各个部分的版本进行控制，从而简化将业务流程各个部分移动到其他服务器或组的操作。 有关顺序 broker 和订单管理器之间的关系的详细信息，请参阅[OrderBroker 业务流程中的处理](../core/processing-in-the-orderbroker-orchestration.md)和[顺序流通过进程管理器](../core/order-flow-through-the-process-manager.md)。  
  
### <a name="error-routing-pattern"></a>错误路由模式  
 该解决方案使用新的 BizTalk Server 错误报告功能。 此功能会将失败的消息路由至订阅端口，以便进行报告或处理。 有关错误报告的常规信息，请参阅[使用失败消息路由](../core/using-failed-message-routing.md)。  
  
### <a name="filter-pattern"></a>筛选器模式  
 筛选模式可以选择符合特定处理条件的消息。 在 BizTalk 中，筛选模式几乎总是以端口的筛选器表达式的形式来实现。 有关端口上的筛选器的详细信息，请参阅[使用筛选器与接收消息 Shape](../core/using-filters-with-the-receive-message-shape.md)。  
  
### <a name="interruptible-orchestration-pattern"></a>可中断业务流程模式  
 在处理订单更新或取消之前，该解决方案将首先中断当前的订单。 该解决方案中的业务流程使用 Interrupt 业务流程来处理中断。 有关详细信息，请参阅[中断业务流程管理解决方案中的处理](../core/interrupt-handling-in-the-business-process-management-solution.md)。  
  
### <a name="inverse-direct-partner-binding-pattern"></a>反转直接合作伙伴绑定模式  
 该解决方案可反转对直接绑定的使用，以将订单处理阶段与订单管理器分离开。 有关反直接绑定的详细信息，请参阅[逆直接合作伙伴绑定](../core/inverse-direct-partner-binding.md)。  
  
### <a name="message-broker-pattern"></a>消息代理模式  
 Message Broker 模式允许由解决方案确定消息的目标，而发件人无需了解目标。 业务流程管理解决方案实现使用消息代理**OrderBroker**业务流程。 **OrderBroker** orchestration 获得订单时，确定所订购的服务的类型并将顺序路由到正确的顺序管理器。 有关消息中协调**OrderBroker**，请参阅[OrderBroker 业务流程中的处理](../core/processing-in-the-orderbroker-orchestration.md)。  
  
### <a name="nested-scopes-pattern"></a>嵌套作用域模式  
 **OrderBroker**业务流程使用嵌套的作用域以尽量减少持久性点，因此，若要提高效率。 有关详细信息，请参阅"提高性能与嵌套作用域"中[OrderBroker 业务流程中的处理](../core/processing-in-the-orderbroker-orchestration.md)。  
  
### <a name="per-instance-pipeline-configuration"></a>每个实例管道配置  
 尽管该解决方案使用默认的管道，但它还是广泛使用新的基于实例的管道配置来为消息指定信封。 有关详细信息，请参阅[如何部署管道](../core/how-to-deploy-pipelines.md)和[的业务流程管理解决方案的组件](../core/components-of-the-business-process-management-solution.md)。  
  
### <a name="process-manager-pattern"></a>流程管理器模式  
 该解决方案使用相对通用的订单管理器来控制通过各个订单处理阶段的流程。 这有助于将业务逻辑与订单流程管理分离开。 有关如何 OrderManager 业务流程充当一个进程管理器的详细信息，请参阅[过程管理器逻辑](../core/process-manager-logic.md)。  
  
### <a name="terminate-shape-at-end-of-orchestration"></a>业务流程末尾的终止形状  
 尽管业务流程通常是在业务流程末尾结束，但某些业务流程仍会在出现错误时使用终止形状来结束。 使用终止形状可以跟踪失败的实例和错误。 有关详细信息，请参阅[自定义异常](../core/custom-exceptions.md)。  
  
### <a name="translator-pattern"></a>转换器模式  
 转换器的企业模式-即，转换消息从一个窗体另一种形式-通常将转换为 BizTalk 映射。 有关 BizTalk 映射的常规信息，请参阅[创建映射使用 BizTalk 映射程序](../core/creating-maps-using-biztalk-mapper.md)。  
  
### <a name="versioning-patterns"></a>版本控制模式  
 业务流程管理解决方案是为简化解决方案组件的版本控制而设计的，它通过分离业务流程和在架构命名空间中使用版本编号来实现此目的。 有关详细信息，请参阅[版本控制业务流程管理解决方案](../core/versioning-the-business-process-management-solution.md)。  
  
## <a name="see-also"></a>另请参阅  
 [业务流程管理解决方案中的模式](../core/patterns-in-the-business-process-management-solution.md)