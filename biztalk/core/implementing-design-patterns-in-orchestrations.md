---
title: "在业务流程中实现设计模式 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Aggregator pattern, orchestrations
- Error Handling pattern [orchestrations]
- patterns, orchestrations
- designing, orchestrations
- orchestrations, designing
- Exception Handling and Compensation pattern [orchestrations]
- Parallel Convoy pattern [orchestrations]
- Dynamic Router pattern [orchestrations]
- orchestrations, patterns
- patterns
- Composed Message Processor pattern [orchestrations]
- Suspend with Retry pattern, orchestrations
- Calling Pipelines from Orchestration pattern [orchestrations]
- Message Filter pattern [orchestrations]
- Message Broker pattern [orchestrations]
- Content-Based Router pattern [orchestrations]
- Sequential Convoy pattern [orchestrations]
- Scatter and Gather pattern [orchestrations]
- Splitter pattern, orchestrations
- Message Translator pattern [orchestrations]
ms.assetid: f62ba955-018a-40e7-b303-497acc906019
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a4837ddf1199425a76a6fa82bbfd6e44615b6c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-design-patterns-in-orchestrations"></a><span data-ttu-id="e3381-102">在业务流程中的实现设计模式</span><span class="sxs-lookup"><span data-stu-id="e3381-102">Implementing Design Patterns in Orchestrations</span></span>
<span data-ttu-id="e3381-103">本部分讨论 BizTalk Server 编程的通用模式以及企业集成模式。</span><span class="sxs-lookup"><span data-stu-id="e3381-103">This section discusses the common patterns of BizTalk Server programming as well as enterprise integration patterns.</span></span> <span data-ttu-id="e3381-104">您可以利用单一模式或组合多个模式来设计您的业务流程，然后使用 BizTalk 业务流程设计器中的形状实现该设计。</span><span class="sxs-lookup"><span data-stu-id="e3381-104">You can leverage a single pattern or combine multiple patterns to design your business process and then implement the design by using shapes in BizTalk Orchestration Designer.</span></span>  
  
## <a name="design-patterns"></a><span data-ttu-id="e3381-105">设计模式</span><span class="sxs-lookup"><span data-stu-id="e3381-105">Design Patterns</span></span>  
 <span data-ttu-id="e3381-106">以下条目对每个模式进行了简要说明，并提供了说明如何使用 BizTalk 业务流程设计器实现这些模式的相关主题或示例的链接。</span><span class="sxs-lookup"><span data-stu-id="e3381-106">The following entries briefly describe each pattern and point to the topics or samples that show how to implement the patterns using BizTalk Orchestration Designer.</span></span>  
  
### <a name="aggregator"></a><span data-ttu-id="e3381-107">聚合器</span><span class="sxs-lookup"><span data-stu-id="e3381-107">Aggregator</span></span>  
 <span data-ttu-id="e3381-108">聚合器是接收来自多个源的信息并将其合并为单个消息的模式。</span><span class="sxs-lookup"><span data-stu-id="e3381-108">Aggregator is the pattern of receiving information from multiple sources and consolidating it into a single message.</span></span> <span data-ttu-id="e3381-109">有关此模式的示例，请参阅中的 Aggregate.odx[聚合器 （BizTalk Server 示例）](../core/aggregator-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="e3381-109">For an example of this pattern, see Aggregate.odx in [Aggregator (BizTalk Server Sample)](../core/aggregator-biztalk-server-sample.md).</span></span>  
  
### <a name="calling-pipelines-from-an-orchestration"></a><span data-ttu-id="e3381-110">从业务流程调用管道</span><span class="sxs-lookup"><span data-stu-id="e3381-110">Calling Pipelines from an Orchestration</span></span>  
 <span data-ttu-id="e3381-111">您可以从业务流程中调用发送和接收管道。</span><span class="sxs-lookup"><span data-stu-id="e3381-111">You can call send and receive pipelines from your orchestrations.</span></span> <span data-ttu-id="e3381-112">通过这种办法可以重用管道，并且有助于保持业务流程与管道阶段的分离状态。</span><span class="sxs-lookup"><span data-stu-id="e3381-112">This allows the reuse of pipelines and helps maintain the decoupling of an orchestration from the pipeline stages.</span></span> <span data-ttu-id="e3381-113">有关此模式的示例，请参阅中的 Aggregate.odx[聚合器 （BizTalk Server 示例）](../core/aggregator-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="e3381-113">For an example of this pattern, see Aggregate.odx in [Aggregator (BizTalk Server Sample)](../core/aggregator-biztalk-server-sample.md).</span></span> <span data-ttu-id="e3381-114">另一个示例是在 CMP.odx[撰写消息处理器 （BizTalk Server 示例）](../core/composed-message-processor-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="e3381-114">Another example is CMP.odx in [Composed Message Processor (BizTalk Server Sample)](../core/composed-message-processor-biztalk-server-sample.md).</span></span> <span data-ttu-id="e3381-115">另请参阅[如何使用表达式来执行管道](../core/how-to-use-expressions-to-execute-pipelines.md)。</span><span class="sxs-lookup"><span data-stu-id="e3381-115">See also [How to Use Expressions to Execute Pipelines](../core/how-to-use-expressions-to-execute-pipelines.md).</span></span>  
  
### <a name="composed-message-processor"></a><span data-ttu-id="e3381-116">组合消息处理器</span><span class="sxs-lookup"><span data-stu-id="e3381-116">Composed Message Processor</span></span>  
 <span data-ttu-id="e3381-117">组合消息处理器是处理来自聚合或批交换消息中的各个项的模式。</span><span class="sxs-lookup"><span data-stu-id="e3381-117">Composed Message Processor is the pattern of processing individual items from an aggregated or batched interchange message.</span></span> <span data-ttu-id="e3381-118">有关此模式的示例，请参阅中的 CMP.odx[撰写消息处理器 （BizTalk Server 示例）](../core/composed-message-processor-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="e3381-118">For an example of this pattern, see CMP.odx in [Composed Message Processor (BizTalk Server Sample)](../core/composed-message-processor-biztalk-server-sample.md).</span></span>  
  
### <a name="content-based-router"></a><span data-ttu-id="e3381-119">基于内容的路由器</span><span class="sxs-lookup"><span data-stu-id="e3381-119">Content-Based Router</span></span>  
 <span data-ttu-id="e3381-120">基于内容的路由器是根据消息内容的某个部分来确定该消息的收件人的模式。</span><span class="sxs-lookup"><span data-stu-id="e3381-120">Content-Based Router is the pattern of determining the recipient of a message based on some part of the message content.</span></span> <span data-ttu-id="e3381-121">有关此模式的示例，请参阅[CBRSample （BizTalk Server 示例）](../core/cbrsample-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="e3381-121">For an example of this pattern, see [CBRSample (BizTalk Server Sample)](../core/cbrsample-biztalk-server-sample.md).</span></span>  
  
### <a name="dynamic-router"></a><span data-ttu-id="e3381-122">动态路由器</span><span class="sxs-lookup"><span data-stu-id="e3381-122">Dynamic Router</span></span>  
 <span data-ttu-id="e3381-123">动态路由器是基于消息处理结果来确定目标地址和传输协议的模式。</span><span class="sxs-lookup"><span data-stu-id="e3381-123">Dynamic Router is the pattern of determining the destination address as well as the transport protocol based on the result of message processing.</span></span> <span data-ttu-id="e3381-124">你可以使用动态发送端口或**角色链接**形状来实现此模式。</span><span class="sxs-lookup"><span data-stu-id="e3381-124">You can use a dynamic send port or a **Role Link** shape to implement this pattern.</span></span> <span data-ttu-id="e3381-125">有关此模式的示例，请参阅中的 ReceiveSend.odx [SendMail](../core/sendmail.md)。</span><span class="sxs-lookup"><span data-stu-id="e3381-125">For an example of this pattern, see ReceiveSend.odx in [SendMail](../core/sendmail.md).</span></span> <span data-ttu-id="e3381-126">另一个示例是在 SupplierProcess.odx [PartyResolution （BizTalk Server 示例）](../core/partyresolution-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="e3381-126">Another example is SupplierProcess.odx in [PartyResolution (BizTalk Server Sample)](../core/partyresolution-biztalk-server-sample.md).</span></span>  
  
### <a name="error-handling"></a><span data-ttu-id="e3381-127">错误处理</span><span class="sxs-lookup"><span data-stu-id="e3381-127">Error Handling</span></span>  
 <span data-ttu-id="e3381-128">BizTalk Server 允许您指定对消息传送失败进行自动处理，以此作为将失败消息放在挂起队列中的默认行为的替代方案。</span><span class="sxs-lookup"><span data-stu-id="e3381-128">BizTalk Server allows you to designate automated handling of messaging failures as an alternative to the default behavior of placing failed messages in the Suspended queue.</span></span> <span data-ttu-id="e3381-129">您可以将失败的消息路由至订阅端口，以便进行报告或处理。</span><span class="sxs-lookup"><span data-stu-id="e3381-129">You can route failed messages to a subscribing port for reporting or processing.</span></span> <span data-ttu-id="e3381-130">有关此模式的示例，请参阅中的 ResubmitLogic.odx[错误处理 （BizTalk Server 示例文件夹中）](../core/error-handling-biztalk-server-samples-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="e3381-130">For an example of this pattern, see ResubmitLogic.odx in [Error Handling (BizTalk Server Samples Folder)](../core/error-handling-biztalk-server-samples-folder.md).</span></span>  
  
### <a name="exception-handling-and-compensation"></a><span data-ttu-id="e3381-131">异常处理和补偿</span><span class="sxs-lookup"><span data-stu-id="e3381-131">Exception Handling and Compensation</span></span>  
 <span data-ttu-id="e3381-132">你可以使用异常处理程序和**引发的异常**形状或**表达式**用于异常处理的形状。</span><span class="sxs-lookup"><span data-stu-id="e3381-132">You can use an exception handler and a **Throw Exception** shape or an **Expression** shape for exception handling.</span></span> <span data-ttu-id="e3381-133">例如，可以将下面的代码**表达式**形状引发的异常:，</span><span class="sxs-lookup"><span data-stu-id="e3381-133">For example, you can place the following code in the **Expression** shape to throw the exception:,</span></span>  
  
```  
excp = new System.Exception();  
throw(excp);  
```  
  
 <span data-ttu-id="e3381-134">你可以使用补偿块和一个**Compensate**形状上已提交的事务执行补偿。</span><span class="sxs-lookup"><span data-stu-id="e3381-134">You can use a compensation block and a **Compensate** shape to perform the compensation on the transactions that have been committed.</span></span> <span data-ttu-id="e3381-135">有关此模式的示例，请参阅中的 UpdateContact.odx[补偿 （BizTalk Server 示例）](../core/compensation-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="e3381-135">For an example of this pattern, see UpdateContact.odx in [Compensation (BizTalk Server Sample)](../core/compensation-biztalk-server-sample.md).</span></span> <span data-ttu-id="e3381-136">另一个例子就是在[自定义异常](../core/custom-exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="e3381-136">Another example is in [Custom Exceptions](../core/custom-exceptions.md).</span></span>  
  
### <a name="message-broker"></a><span data-ttu-id="e3381-137">Message Broker</span><span class="sxs-lookup"><span data-stu-id="e3381-137">Message Broker</span></span>  
 <span data-ttu-id="e3381-138">Message Broker 模式可确定消息的目标，同时仍维持对消息流的控制。</span><span class="sxs-lookup"><span data-stu-id="e3381-138">Message Broker is the pattern of determining the destination of a message and still maintaining control over the message flow.</span></span> <span data-ttu-id="e3381-139">有关详细信息，请参阅[OrderBroker 业务流程中的处理](../core/processing-in-the-orderbroker-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="e3381-139">For more, see  [Processing in the OrderBroker Orchestration](../core/processing-in-the-orderbroker-orchestration.md).</span></span>  
  
### <a name="message-filter"></a><span data-ttu-id="e3381-140">消息筛选器</span><span class="sxs-lookup"><span data-stu-id="e3381-140">Message Filter</span></span>  
 <span data-ttu-id="e3381-141">消息筛选器模式可以选择符合特定处理条件的消息。</span><span class="sxs-lookup"><span data-stu-id="e3381-141">The Message Filter pattern selects messages meeting particular criteria for processing.</span></span> <span data-ttu-id="e3381-142">你可以通过将筛选器表达式添加到已激活实现此模式**接收**形状。</span><span class="sxs-lookup"><span data-stu-id="e3381-142">You can implement this pattern by adding the filter expression to an activated **Receive** shape.</span></span> <span data-ttu-id="e3381-143">有关详细信息，请参阅[使用筛选器与接收消息 Shape](../core/using-filters-with-the-receive-message-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="e3381-143">For more information, see [Using Filters With the Receive Message Shape](../core/using-filters-with-the-receive-message-shape.md).</span></span>  
  
### <a name="message-translator"></a><span data-ttu-id="e3381-144">消息转换器</span><span class="sxs-lookup"><span data-stu-id="e3381-144">Message Translator</span></span>  
 <span data-ttu-id="e3381-145">消息转换器模式可以将消息从一种形式转换为另一种形式。</span><span class="sxs-lookup"><span data-stu-id="e3381-145">The Message Translator pattern converts a message from one form to another form.</span></span> <span data-ttu-id="e3381-146">你可以使用与 BizTalk 映射来实现此模式**转换**形状中业务流程。</span><span class="sxs-lookup"><span data-stu-id="e3381-146">You can implement this pattern by using a BizTalk map with a **Transform** shape in an orchestration.</span></span> <span data-ttu-id="e3381-147">有关此模式的示例，请参阅中的 HelloOrchestration.odx [HelloWorld （BizTalk Server 示例）](../core/helloworld-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="e3381-147">For an example of this pattern, see HelloOrchestration.odx in [HelloWorld (BizTalk Server Sample)](../core/helloworld-biztalk-server-sample.md).</span></span>  
  
### <a name="parallel-convoy"></a><span data-ttu-id="e3381-148">并行的队列</span><span class="sxs-lookup"><span data-stu-id="e3381-148">Parallel Convoy</span></span>  
 <span data-ttu-id="e3381-149">并行保护模式可以使多个单一项连接在一起来得出所需的结果，而这一结果是无法通过单个项本身来完成的。</span><span class="sxs-lookup"><span data-stu-id="e3381-149">The Parallel Convoy pattern enables multiple single items to join together to achieve something that an individual item cannot accomplish by itself.</span></span> <span data-ttu-id="e3381-150">一组相关项可以按任意顺序到达，但 BizTalk Server 必须在收到所有项之后才能启动流程。</span><span class="sxs-lookup"><span data-stu-id="e3381-150">The set of related items can arrive in any order, but BizTalk Server must receive all of them before starting the process.</span></span> <span data-ttu-id="e3381-151">有关此模式的示例，请参阅[http://go.microsoft.com/fwlink/?LinkId=56035](http://go.microsoft.com/fwlink/?LinkId=56035)。</span><span class="sxs-lookup"><span data-stu-id="e3381-151">For an example of this pattern, see [http://go.microsoft.com/fwlink/?LinkId=56035](http://go.microsoft.com/fwlink/?LinkId=56035).</span></span>  
  
### <a name="scatter-and-gather"></a><span data-ttu-id="e3381-152">分散与收集</span><span class="sxs-lookup"><span data-stu-id="e3381-152">Scatter and Gather</span></span>  
 <span data-ttu-id="e3381-153">分散与收集模式可以将消息发送至多个收件人，然后接收来自每个收件人的消息。</span><span class="sxs-lookup"><span data-stu-id="e3381-153">The Scatter and Gather pattern enables messages to be sent to multiple recipients and messages to be received back from each recipient.</span></span> <span data-ttu-id="e3381-154">您可以通过使用拆分器模式和聚合器模式来实现此模式。</span><span class="sxs-lookup"><span data-stu-id="e3381-154">You can implement this pattern by using the Splitter pattern and the Aggregator pattern.</span></span> <span data-ttu-id="e3381-155">你使用聚合器模式来汇集使用拆分器模式中的结果并将其下放**并行操作**形状。</span><span class="sxs-lookup"><span data-stu-id="e3381-155">You use the Aggregator pattern to assemble the results from using the Splitter pattern and put them under a **Parallel Actions** shape.</span></span> <span data-ttu-id="e3381-156">拆分模式的示例，请参阅 SDK 示例命名实现散点图和收集模式时[http://go.microsoft.com/fwlink/?LinkId=65185](http://go.microsoft.com/fwlink/?LinkId=65185)。</span><span class="sxs-lookup"><span data-stu-id="e3381-156">For an example of the Splitter pattern, see SDK sample named Implementing Scatter and Gather Pattern at [http://go.microsoft.com/fwlink/?LinkId=65185](http://go.microsoft.com/fwlink/?LinkId=65185).</span></span>  
  
### <a name="sequential-convoy"></a><span data-ttu-id="e3381-157">顺序保护</span><span class="sxs-lookup"><span data-stu-id="e3381-157">Sequential Convoy</span></span>  
 <span data-ttu-id="e3381-158">顺序保护模式可以使多个单一项连接在一起来得出所需的结果，而这一结果是无法通过单个项本身来完成的。</span><span class="sxs-lookup"><span data-stu-id="e3381-158">The Sequential Convoy pattern enables multiple single items to join together to achieve something that an individual item cannot accomplish by itself.</span></span> <span data-ttu-id="e3381-159">顺序保护是一组具有预定义顺序的相关项。</span><span class="sxs-lookup"><span data-stu-id="e3381-159">A sequential convoy is a set of related items that have a predefined order.</span></span> <span data-ttu-id="e3381-160">虽然这些项不必完全相同，但 BizTalk Server 必须按一定顺序接收它们。</span><span class="sxs-lookup"><span data-stu-id="e3381-160">Although the items do not have to be exactly the same, BizTalk Server must receive the items in a sequential order.</span></span> <span data-ttu-id="e3381-161">有关此模式的示例，请参阅[http://go.microsoft.com/fwlink/?LinkId=56035](http://go.microsoft.com/fwlink/?LinkId=56035)。</span><span class="sxs-lookup"><span data-stu-id="e3381-161">For an example of this pattern, see [http://go.microsoft.com/fwlink/?LinkId=56035](http://go.microsoft.com/fwlink/?LinkId=56035).</span></span>  
  
### <a name="splitter"></a><span data-ttu-id="e3381-162">拆分器</span><span class="sxs-lookup"><span data-stu-id="e3381-162">Splitter</span></span>  
 <span data-ttu-id="e3381-163">拆分器模式获取单个消息并将其拆分为多个消息。</span><span class="sxs-lookup"><span data-stu-id="e3381-163">The Splitter pattern takes a single message and splits it into multiple messages.</span></span>  
  
### <a name="suspend-with-retry"></a><span data-ttu-id="e3381-164">挂起并重试</span><span class="sxs-lookup"><span data-stu-id="e3381-164">Suspend with Retry</span></span>  
 <span data-ttu-id="e3381-165">挂起并重试模式可以使业务流程在出现错误时将消息挂起。</span><span class="sxs-lookup"><span data-stu-id="e3381-165">The Suspend with Retry pattern enables the orchestration to suspend a message when there is an error.</span></span> <span data-ttu-id="e3381-166">挂起发生在循环中，这样，业务流程将挂起、请求干预，然后按固定的次数重试操作。</span><span class="sxs-lookup"><span data-stu-id="e3381-166">The suspension occurs within a loop so that the orchestration suspends, asks for intervention, and then retries the operation a fixed number of times.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3381-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3381-167">See Also</span></span>  
 [<span data-ttu-id="e3381-168">设计业务流程流</span><span class="sxs-lookup"><span data-stu-id="e3381-168">Designing Orchestration Flow</span></span>](../core/designing-orchestration-flow.md)