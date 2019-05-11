---
title: 在业务流程中实现设计模式 |Microsoft Docs
description: 聚合器、 基于内容的路由、 动态路由器、 错误处理、 消息中转站和 BizTalk Server 中的多个设计模式
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
ms.openlocfilehash: 932a9563c338be0e5e29a2968ea4da52e1b65045
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332427"
---
# <a name="implement-design-patterns-in-orchestrations"></a>在业务流程中实现设计模式
本部分讨论 BizTalk Server 编程，以及企业集成模式的常见模式。 可利用单一模式或组合使用多个模式来设计您的业务流程，然后使用 BizTalk 业务流程设计器中的形状实现该设计。  
  
## <a name="design-patterns"></a>设计模式  
 以下条目简要介绍每种模式，并指向的主题或示例，用于演示如何实现使用 BizTalk 业务流程设计器的模式。  
  
### <a name="aggregator"></a>聚合器  
 聚合器是从多个源接收的信息，并且合并为单个消息的模式。 此模式的示例，请参阅中的 Aggregate.odx[聚合器 （BizTalk Server 示例）](../core/aggregator-biztalk-server-sample.md)。  
  
### <a name="calling-pipelines-from-an-orchestration"></a>从业务流程调用管道  
 可以调用发送和接收管道从你的业务流程。 这允许重用管道，并有助于保持业务流程与管道阶段的分离。 此模式的示例，请参阅中的 Aggregate.odx[聚合器 （BizTalk Server 示例）](../core/aggregator-biztalk-server-sample.md)。 另一个示例是中的 CMP.odx[组合消息处理器 （BizTalk Server 示例）](../core/composed-message-processor-biztalk-server-sample.md)。 另请参阅[如何使用表达式执行管道](../core/how-to-use-expressions-to-execute-pipelines.md)。  
  
### <a name="composed-message-processor"></a>组合的消息处理器  
 组合的消息处理器是处理中的聚合或批交换消息的各个项的模式。 此模式的示例，请参阅中的 CMP.odx[组合消息处理器 （BizTalk Server 示例）](../core/composed-message-processor-biztalk-server-sample.md)。  
  
### <a name="content-based-router"></a>基于内容的路由器  
 基于内容的路由器是确定基于消息内容的某些部分消息的收件人的模式。 此模式的示例，请参阅[CBRSample （BizTalk Server 示例）](../core/cbrsample-biztalk-server-sample.md)。  
  
### <a name="dynamic-router"></a>动态路由器  
 动态路由器是处理的确定目标地址，以及基于消息结果的传输协议的模式。 您可以使用动态发送端口或**角色链接**形状来实现此模式。 此模式的示例，请参阅参阅中的 ReceiveSend.odx [SendMail](../core/sendmail.md)。 另一个示例是中的 SupplierProcess.odx [PartyResolution （BizTalk Server 示例）](../core/partyresolution-biztalk-server-sample.md)。  
  
### <a name="error-handling"></a>错误处理  
 BizTalk Server 允许您指定的消息作为将失败消息放在挂起队列中的默认行为的替代方法传送失败进行自动的处理。 可以将失败的消息路由至订阅端口，以便进行报告或处理。 此模式的示例，请参阅参阅中的 ResubmitLogic.odx[错误处理 （BizTalk Server 示例文件夹）](../core/error-handling-biztalk-server-samples-folder.md)。  
  
### <a name="exception-handling-and-compensation"></a>异常处理和补偿  
 可以使用异常处理程序和一个**引发异常**形状或**表达式**异常处理的形状。 例如，可以将下面的代码中放置**表达式**形状引发的异常:，  
  
```  
excp = new System.Exception();  
throw(excp);  
```  
  
 可以使用补偿模块和一个**补偿**形状上已提交的事务执行补偿。 此模式的示例，请参阅中的 UpdateContact.odx[补偿 （BizTalk Server 示例）](../core/compensation-biztalk-server-sample.md)。 另一个示例是在[自定义异常](../core/custom-exceptions.md)。  
  
### <a name="message-broker"></a>消息代理  
 消息代理是确定消息的目标，同时仍维持对消息流控制的模式。 有关详细信息，请参阅[在 OrderBroker 业务流程中处理](../core/processing-in-the-orderbroker-orchestration.md)。  
  
### <a name="message-filter"></a>消息筛选器  
 消息筛选器模式可以选择符合特定处理条件的消息。 您可以通过向激活添加筛选器表达式来实现此模式**接收**形状。 有关详细信息，请参阅[使用筛选器与接收消息形状](../core/using-filters-with-the-receive-message-shape.md)。  
  
### <a name="message-translator"></a>消息转换器  
 消息转换器模式将消息从一种形式转换为另一种形式。 您可以通过使用与 BizTalk 映射实现此模式**转换**形状在业务流程中的。 此模式的示例，请参阅中的 HelloOrchestration.odx [HelloWorld （BizTalk Server 示例）](../core/helloworld-biztalk-server-sample.md)。  
  
### <a name="parallel-convoy"></a>并行保护  
 并行保护模式可以使多个单一项连接在一起以实现类似的单个项不能通过本身来完成。 一组相关项可以按任意顺序到达，但 BizTalk Server 必须在启动进程之前收到所有项。 
  
### <a name="scatter-and-gather"></a>分散与收集  
 分散与收集模式，将消息发送给多个收件人和消息，以接收来自每个收件人。 您可以通过使用拆分器模式和聚合器模式来实现此模式。 使用聚合器模式来组装使用拆分器模式得到结果并将其下放置**并行操作**形状。 
  
### <a name="sequential-convoy"></a>顺序保护  
 顺序保护模式可以使多个单一项连接在一起以实现类似的单个项不能通过本身来完成。 顺序保护是一组具有预定义的顺序的相关项。 虽然这些项不需要是完全相同，但 BizTalk Server 必须按顺序接收项。 
  
### <a name="splitter"></a>拆分器  
 拆分器模式获取一条消息，并将它拆分为多条消息。  
  
### <a name="suspend-with-retry"></a>挂起并重试  
 挂起并重试模式使业务流程错误时将消息挂起。 挂起发生在循环中，以便该业务流程挂起、 请求干预，和固定的次数然后重试该操作。  
  
## <a name="see-also"></a>请参阅  
 [设计业务流程流](../core/designing-orchestration-flow.md)