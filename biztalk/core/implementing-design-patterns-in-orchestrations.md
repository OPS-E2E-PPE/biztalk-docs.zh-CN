---
title: 在业务流程中实现的设计模式 |Microsoft 文档
description: 聚合器，基于内容的路由、 动态路由器、 错误处理、 消息代理和 BizTalk Server 中的多个设计模式
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f62ba955-018a-40e7-b303-497acc906019
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 290b31e8d5494c7a00eb02517e910fc877da9124
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014244"
---
# <a name="implement-design-patterns-in-orchestrations"></a>在业务流程中的实现设计模式
本部分讨论 BizTalk Server 编程的通用模式以及企业集成模式。 您可以利用单一模式或组合多个模式来设计您的业务流程，然后使用 BizTalk 业务流程设计器中的形状实现该设计。  
  
## <a name="design-patterns"></a>设计模式  
 以下条目对每个模式进行了简要说明，并提供了说明如何使用 BizTalk 业务流程设计器实现这些模式的相关主题或示例的链接。  
  
### <a name="aggregator"></a>聚合器  
 聚合器是接收来自多个源的信息并将其合并为单个消息的模式。 有关此模式的示例，请参阅中的 Aggregate.odx[聚合器 （BizTalk Server 示例）](../core/aggregator-biztalk-server-sample.md)。  
  
### <a name="calling-pipelines-from-an-orchestration"></a>从业务流程调用管道  
 您可以从业务流程中调用发送和接收管道。 通过这种办法可以重用管道，并且有助于保持业务流程与管道阶段的分离状态。 有关此模式的示例，请参阅中的 Aggregate.odx[聚合器 （BizTalk Server 示例）](../core/aggregator-biztalk-server-sample.md)。 另一个示例是在 CMP.odx[撰写消息处理器 （BizTalk Server 示例）](../core/composed-message-processor-biztalk-server-sample.md)。 另请参阅[如何使用表达式来执行管道](../core/how-to-use-expressions-to-execute-pipelines.md)。  
  
### <a name="composed-message-processor"></a>组合消息处理器  
 组合消息处理器是处理来自聚合或批交换消息中的各个项的模式。 有关此模式的示例，请参阅中的 CMP.odx[撰写消息处理器 （BizTalk Server 示例）](../core/composed-message-processor-biztalk-server-sample.md)。  
  
### <a name="content-based-router"></a>基于内容的路由器  
 基于内容的路由器是根据消息内容的某个部分来确定该消息的收件人的模式。 有关此模式的示例，请参阅[CBRSample （BizTalk Server 示例）](../core/cbrsample-biztalk-server-sample.md)。  
  
### <a name="dynamic-router"></a>动态路由器  
 动态路由器是基于消息处理结果来确定目标地址和传输协议的模式。 你可以使用动态发送端口或**角色链接**形状来实现此模式。 有关此模式的示例，请参阅中的 ReceiveSend.odx [SendMail](../core/sendmail.md)。 另一个示例是在 SupplierProcess.odx [PartyResolution （BizTalk Server 示例）](../core/partyresolution-biztalk-server-sample.md)。  
  
### <a name="error-handling"></a>错误处理  
 BizTalk Server 允许您指定对消息传送失败进行自动处理，以此作为将失败消息放在挂起队列中的默认行为的替代方案。 您可以将失败的消息路由至订阅端口，以便进行报告或处理。 有关此模式的示例，请参阅中的 ResubmitLogic.odx[错误处理 （BizTalk Server 示例文件夹中）](../core/error-handling-biztalk-server-samples-folder.md)。  
  
### <a name="exception-handling-and-compensation"></a>异常处理和补偿  
 你可以使用异常处理程序和**引发的异常**形状或**表达式**用于异常处理的形状。 例如，可以将下面的代码**表达式**形状引发的异常:，  
  
```  
excp = new System.Exception();  
throw(excp);  
```  
  
 你可以使用补偿块和一个**Compensate**形状上已提交的事务执行补偿。 有关此模式的示例，请参阅中的 UpdateContact.odx[补偿 （BizTalk Server 示例）](../core/compensation-biztalk-server-sample.md)。 另一个例子就是在[自定义异常](../core/custom-exceptions.md)。  
  
### <a name="message-broker"></a>Message Broker  
 Message Broker 模式可确定消息的目标，同时仍维持对消息流的控制。 有关详细信息，请参阅[OrderBroker 业务流程中的处理](../core/processing-in-the-orderbroker-orchestration.md)。  
  
### <a name="message-filter"></a>消息筛选器  
 消息筛选器模式可以选择符合特定处理条件的消息。 你可以通过将筛选器表达式添加到已激活实现此模式**接收**形状。 有关详细信息，请参阅[使用筛选器与接收消息 Shape](../core/using-filters-with-the-receive-message-shape.md)。  
  
### <a name="message-translator"></a>消息转换器  
 消息转换器模式可以将消息从一种形式转换为另一种形式。 你可以使用与 BizTalk 映射来实现此模式**转换**形状中业务流程。 有关此模式的示例，请参阅中的 HelloOrchestration.odx [HelloWorld （BizTalk Server 示例）](../core/helloworld-biztalk-server-sample.md)。  
  
### <a name="parallel-convoy"></a>并行的队列  
 并行保护模式可以使多个单一项连接在一起来得出所需的结果，而这一结果是无法通过单个项本身来完成的。 一组相关项可以按任意顺序到达，但 BizTalk Server 必须在收到所有项之后才能启动流程。 
  
### <a name="scatter-and-gather"></a>分散与收集  
 分散与收集模式可以将消息发送至多个收件人，然后接收来自每个收件人的消息。 您可以通过使用拆分器模式和聚合器模式来实现此模式。 你使用聚合器模式来汇集使用拆分器模式中的结果并将其下放**并行操作**形状。 
  
### <a name="sequential-convoy"></a>顺序保护  
 顺序保护模式可以使多个单一项连接在一起来得出所需的结果，而这一结果是无法通过单个项本身来完成的。 顺序保护是一组具有预定义顺序的相关项。 虽然这些项不必完全相同，但 BizTalk Server 必须按一定顺序接收它们。 
  
### <a name="splitter"></a>拆分器  
 拆分器模式获取单个消息并将其拆分为多个消息。  
  
### <a name="suspend-with-retry"></a>挂起并重试  
 挂起并重试模式可以使业务流程在出现错误时将消息挂起。 挂起发生在循环中，这样，业务流程将挂起、请求干预，然后按固定的次数重试操作。  
  
## <a name="see-also"></a>另请参阅  
 [设计业务流程流](../core/designing-orchestration-flow.md)