---
title: "处理事务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d360742-e969-4651-b364-9edc6a93b8d4
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 954d0e91e078c7f973bddc22961c760aa4080941
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="handling-transactions"></a><span data-ttu-id="139b1-102">处理事务</span><span class="sxs-lookup"><span data-stu-id="139b1-102">Handling Transactions</span></span>
## <a name="transacted-receivers"></a><span data-ttu-id="139b1-103">事务性接收器</span><span class="sxs-lookup"><span data-stu-id="139b1-103">Transacted Receivers</span></span>  
 <span data-ttu-id="139b1-104">事务处理接收方和 nontransacted 接收方之间的主要区别是事务处理接收方创建和使用显式的 MSDTC 事务来确保其数据源之间的原子性和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="139b1-104">The main difference between transacted receivers and nontransacted receivers is that transacted receivers create and use an explicit MSDTC transaction to ensure atomicity between their data source and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox database.</span></span> <span data-ttu-id="139b1-105">通常，适配器的其他方面均相同。</span><span class="sxs-lookup"><span data-stu-id="139b1-105">In general every other aspect of the adapter is the same.</span></span>  
  
 <span data-ttu-id="139b1-106">应该注意的是，请求-响应接收适配器仅使用某一事务来将原始请求消息提交给消息引擎。</span><span class="sxs-lookup"><span data-stu-id="139b1-106">It should be noted that a request-response receive adapter only uses a transaction for submitting the original request message to the Messaging Engine.</span></span> <span data-ttu-id="139b1-107">为将从消息引擎发送的响应传输到适配器，需要不同的事务。</span><span class="sxs-lookup"><span data-stu-id="139b1-107">A different transaction is needed for the transmission of the response sent from the Messaging Engine to the adapter.</span></span> <span data-ttu-id="139b1-108">其原因在于，第一个事务的作用域在适配器和 MessageBox 数据库之间。</span><span class="sxs-lookup"><span data-stu-id="139b1-108">This is because the scope of the first transaction is between the adapter and the MessageBox database.</span></span> <span data-ttu-id="139b1-109">在原始请求消息的事务提交前，后续的请求消息不会从消息引擎发送到适配器。</span><span class="sxs-lookup"><span data-stu-id="139b1-109">The subsequent request message is not sent to the adapter from the Messaging Engine until the transaction for the original request message commits.</span></span>  
  
 <span data-ttu-id="139b1-110">下面的对象交互图描述了在传入消息的事务性提交过程中适配器和消息引擎之间的交互。</span><span class="sxs-lookup"><span data-stu-id="139b1-110">The following object interaction diagram illustrates the interaction between the adapter and the Messaging Engine during a transactional submission of incoming messages.</span></span> <span data-ttu-id="139b1-111">在该示例中，将按照以下顺序进行交互：</span><span class="sxs-lookup"><span data-stu-id="139b1-111">In this example, the following sequence of interactions takes place:</span></span>  
  
1.  <span data-ttu-id="139b1-112">适配器从引擎中获取新批。</span><span class="sxs-lookup"><span data-stu-id="139b1-112">The adapter gets a new batch from the engine.</span></span>  
  
2.  <span data-ttu-id="139b1-113">适配器创建新的 MSDTC 事务。</span><span class="sxs-lookup"><span data-stu-id="139b1-113">The adapter creates a new MSDTC transaction.</span></span>  
  
3.  <span data-ttu-id="139b1-114">适配器从其已在事务中登记的数据源进行破坏性读取。</span><span class="sxs-lookup"><span data-stu-id="139b1-114">The adapter does a destructive read from its data source that has been enlisted in the transaction.</span></span>  
  
4.  <span data-ttu-id="139b1-115">适配器提交消息。</span><span class="sxs-lookup"><span data-stu-id="139b1-115">The adapter submits the message.</span></span>  
  
5.  <span data-ttu-id="139b1-116">适配器调用**完成**批次，在其 MSDTC 事务中传递并将其**BatchComplete**回调指针。</span><span class="sxs-lookup"><span data-stu-id="139b1-116">The adapter calls **Done** on the batch, passing in its MSDTC transaction and its **BatchComplete** callback pointer.</span></span> <span data-ttu-id="139b1-117">引擎会返回**IBTDTCCommitConfirm**接口。</span><span class="sxs-lookup"><span data-stu-id="139b1-117">The engine returns an **IBTDTCCommitConfirm** interface.</span></span>  
  
6.  <span data-ttu-id="139b1-118">引擎处理该批、 适配器回调上其**BatchComplete**实现，并传送到适配器处理其消息的状态。</span><span class="sxs-lookup"><span data-stu-id="139b1-118">The engine processes the batch, calls the adapter back on its **BatchComplete** implementation, and conveys the status of its message processing to the adapter.</span></span>  
  
7.  <span data-ttu-id="139b1-119">适配器如果批处理成功提交的事务和调用**IBTDTCCommitConfirm.DTCCommitConfirm** API`true`表明提交的值。</span><span class="sxs-lookup"><span data-stu-id="139b1-119">If the batch was successful the adapter commits the transaction and calls the **IBTDTCCommitConfirm.DTCCommitConfirm** API with a `true` value signifying commit.</span></span>  
  
 ![](../core/media/transactedreceiver.gif "TransactedReceiver")  
  
## <a name="transacted-transmitters"></a><span data-ttu-id="139b1-120">事务性发送器</span><span class="sxs-lookup"><span data-stu-id="139b1-120">Transacted Transmitters</span></span>  
 <span data-ttu-id="139b1-121">事务性适配器在很大程度上与非事务性适配器十分相似。</span><span class="sxs-lookup"><span data-stu-id="139b1-121">Transacted adapters are for the most part very similar to nontransacted adapters.</span></span> <span data-ttu-id="139b1-122">主要差别在于，事务性适配器将消息中的数据发送到已在 MSDTC 事务中登记的资源。</span><span class="sxs-lookup"><span data-stu-id="139b1-122">The main difference is that the transacted adapter sends the data in the message to a resource that it has enlisted in an MSDTC transaction.</span></span>  
  
 <span data-ttu-id="139b1-123">**实现提示：**对于事务处理发送适配器应使用相同的 MSDTC 事务将数据写入到目标和删除它通过**IBTTransportBatch.DeleteMessage**方法调用。</span><span class="sxs-lookup"><span data-stu-id="139b1-123">**Implementation Tip:** For transacted sends, the adapter should use the same MSDTC transaction for writing the data to the destination and for deleting it through the **IBTTransportBatch.DeleteMessage** method call.</span></span> <span data-ttu-id="139b1-124">只有这两个操作需要进行事务处理。</span><span class="sxs-lookup"><span data-stu-id="139b1-124">Only these two operations need to be transacted.</span></span> <span data-ttu-id="139b1-125">任何其他操作，如**IBTTransportBatch.Resubmit**， **IBTTransportBatch.MoveToNextTransport**，和**IBTTransportBatch.MoveToSuspendQ**不需要为事务处理。</span><span class="sxs-lookup"><span data-stu-id="139b1-125">Any other operations, such as **IBTTransportBatch.Resubmit**, **IBTTransportBatch.MoveToNextTransport**, and **IBTTransportBatch.MoveToSuspendQ** do not need to be transacted.</span></span> <span data-ttu-id="139b1-126">原因在于：引擎隐式使用事务，并且就目标而言，这些类型的操作无需是原子的。</span><span class="sxs-lookup"><span data-stu-id="139b1-126">This is because the engine implicitly uses a transaction and these types of operations do not need to be atomic with respect to the destination.</span></span>  
  
 <span data-ttu-id="139b1-127">下面的对象交互图说明了适配器和引擎之间的交互。</span><span class="sxs-lookup"><span data-stu-id="139b1-127">The following object interaction diagram illustrates the interactions between the adapter and the engine.</span></span> <span data-ttu-id="139b1-128">这些事件的顺序如下：</span><span class="sxs-lookup"><span data-stu-id="139b1-128">The sequence of events is as follows:</span></span>  
  
1.  <span data-ttu-id="139b1-129">引擎从适配器获取新批。</span><span class="sxs-lookup"><span data-stu-id="139b1-129">The engine gets a new batch from the adapter.</span></span>  
  
2.  <span data-ttu-id="139b1-130">引擎将两个消息添加到这个新批。</span><span class="sxs-lookup"><span data-stu-id="139b1-130">The engine adds two messages to the new batch.</span></span>  
  
3.  <span data-ttu-id="139b1-131">引擎调用**完成**批次，从而导致其线程池发布到其内部传输队列中已得到处理批处理的适配器。</span><span class="sxs-lookup"><span data-stu-id="139b1-131">The engine calls **Done** on the batch, causing the adapter to post the batch to its internal transmit queue that is serviced by its thread pool.</span></span>  
  
4.  <span data-ttu-id="139b1-132">适配器创建新的 MSDTC 事务。</span><span class="sxs-lookup"><span data-stu-id="139b1-132">The adapter creates a new MSDTC transaction.</span></span>  
  
5.  <span data-ttu-id="139b1-133">适配器传输在 MSDTC 事务中登记目标的消息。</span><span class="sxs-lookup"><span data-stu-id="139b1-133">The adapter transmits the messages enlisting the destination in the MSDTC transaction.</span></span> <span data-ttu-id="139b1-134">例如，这可能会写入到[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="139b1-134">For example, this could be writing to a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database.</span></span>  
  
6.  <span data-ttu-id="139b1-135">在传输后，适配器从引擎获取新批。</span><span class="sxs-lookup"><span data-stu-id="139b1-135">After transmission, the adapter gets a new batch from the engine.</span></span>  
  
7.  <span data-ttu-id="139b1-136">适配器调用**DeleteMessage**已成功传输的消息。</span><span class="sxs-lookup"><span data-stu-id="139b1-136">The adapter calls **DeleteMessage** for the messages that it has successfully transmitted.</span></span>  
  
8.  <span data-ttu-id="139b1-137">适配器调用**完成**批次传递其 DTC 事务中。</span><span class="sxs-lookup"><span data-stu-id="139b1-137">The adapter calls **Done** on the batch passing in its DTC transaction.</span></span> <span data-ttu-id="139b1-138">引擎会返回**IBTDTCCommitConfirm**接口。</span><span class="sxs-lookup"><span data-stu-id="139b1-138">The engine returns an **IBTDTCCommitConfirm** interface.</span></span>  
  
9. <span data-ttu-id="139b1-139">引擎处理该批，并且从应用程序队列删除消息。</span><span class="sxs-lookup"><span data-stu-id="139b1-139">The engine processes the batch, deleting the messages from the application queue.</span></span>  
  
10. <span data-ttu-id="139b1-140">引擎回调的适配器**IBTBatchCallback**成功的其删除操作的信息的接口。</span><span class="sxs-lookup"><span data-stu-id="139b1-140">The engine calls back the adapter's **IBTBatchCallback** interface with information on the success of its deletion operations.</span></span>  
  
11. <span data-ttu-id="139b1-141">如果该批成功，适配器将提交事务。</span><span class="sxs-lookup"><span data-stu-id="139b1-141">If the batch was successful, the adapter commits the transactions.</span></span>  
  
12. <span data-ttu-id="139b1-142">适配器调用**IBTDTCCommitConfirm.DTCCommitConfirm**以通知引擎已成功提交事务。</span><span class="sxs-lookup"><span data-stu-id="139b1-142">The adapter calls **IBTDTCCommitConfirm.DTCCommitConfirm** to inform the engine that the transaction was successfully committed.</span></span>  
  
 ![](../core/media/transactedtransmitter.gif "Transactedtransmitter")  
  
### <a name="transacted-solicit-response-adapters"></a><span data-ttu-id="139b1-143">事务性要求-响应适配器</span><span class="sxs-lookup"><span data-stu-id="139b1-143">Transacted Solicit-Response Adapters</span></span>  
 <span data-ttu-id="139b1-144">与双向接收不同，可以通过使用相同的 DTC 事务执行双向发送。</span><span class="sxs-lookup"><span data-stu-id="139b1-144">Unlike two-way receives, two-way sends may be performed by using the same DTC transaction.</span></span> <span data-ttu-id="139b1-145">事务处理的请求作出响应适配器应使用相同**IBTTransportBatch**为**SubmitResponseMessage**和**DeleteMessage**操作。</span><span class="sxs-lookup"><span data-stu-id="139b1-145">Transacted solicit-response adapters should use the same **IBTTransportBatch** for the **SubmitResponseMessage** and **DeleteMessage** operations.</span></span> <span data-ttu-id="139b1-146">此批应使用用于收发要求-响应消息对的相同 MSDTC 事务。</span><span class="sxs-lookup"><span data-stu-id="139b1-146">This batch should use the same MSDTC transaction that is used to send and receive the solicit-response message pair.</span></span> <span data-ttu-id="139b1-147">这确保要求-响应消息交换的原子性。</span><span class="sxs-lookup"><span data-stu-id="139b1-147">This ensures atomicity for the solicit-response message exchange.</span></span>  
  
## <a name="service-components-and-byot"></a><span data-ttu-id="139b1-148">服务组件和 BYOT</span><span class="sxs-lookup"><span data-stu-id="139b1-148">Service Components and BYOT</span></span>  
 <span data-ttu-id="139b1-149">消息引擎 API 要求提供 MSDTC 事务。</span><span class="sxs-lookup"><span data-stu-id="139b1-149">The Messaging Engine APIs require an MSDTC transaction to be supplied.</span></span> <span data-ttu-id="139b1-150">但是，某些 .NET 组件设计为用于服务组件，不允许以编程方式提交或中止事务。</span><span class="sxs-lookup"><span data-stu-id="139b1-150">However some .NET components are designed to be used as serviced components and do not allow the transaction to be programmatically committed or aborted.</span></span> <span data-ttu-id="139b1-151">事务而是由该平台上的 COM+ 运行库自动提交。</span><span class="sxs-lookup"><span data-stu-id="139b1-151">Instead, the transaction is automatically committed by the COM+ runtime on that platform.</span></span>  
  
 <span data-ttu-id="139b1-152">对于这些情况，适配器应使用 BYOT（Bring Your Own Transaction，生成您自己的事务）。</span><span class="sxs-lookup"><span data-stu-id="139b1-152">For these scenarios, the adapter should use Bring Your Own Transaction (BYOT).</span></span> <span data-ttu-id="139b1-153">这允许适配器创建 MSDTC 事务，实例化使用该事务的 .NET 组件，以及允许该组件继承已创建的事务，而非创建它自己的事务。</span><span class="sxs-lookup"><span data-stu-id="139b1-153">This allows the adapter to create an MSDTC transaction, instantiate the .NET component that uses the transaction, and allow that component to inherit the created transaction rather than create its own transaction.</span></span> <span data-ttu-id="139b1-154">.NET Framework 提供了**System.EnterpriseServices.BYOT**为此目的。</span><span class="sxs-lookup"><span data-stu-id="139b1-154">The .NET Framework provides **System.EnterpriseServices.BYOT** for this purpose.</span></span> <span data-ttu-id="139b1-155">SDK BaseAdapter 提供一个帮助器类， **BYOTTransaction**，为此目的。</span><span class="sxs-lookup"><span data-stu-id="139b1-155">The SDK BaseAdapter provides a helper class, **BYOTTransaction**, for this purpose.</span></span>  
  
## <a name="avoiding-race-conditions"></a><span data-ttu-id="139b1-156">避免争用情况</span><span class="sxs-lookup"><span data-stu-id="139b1-156">Avoiding Race Conditions</span></span>  
 <span data-ttu-id="139b1-157">当你编写的适配器，创建事务对象，并为到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，表明你接受负责编写的代码，执行下列任务：</span><span class="sxs-lookup"><span data-stu-id="139b1-157">When you write an adapter that creates a transaction object and hands it to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you are accepting responsibility for writing code that does the following:</span></span>  
  
-   <span data-ttu-id="139b1-158">解决消息中与批相关联的错误。</span><span class="sxs-lookup"><span data-stu-id="139b1-158">Resolves errors in messages associated with the batch.</span></span>  
  
-   <span data-ttu-id="139b1-159">确定与批操作相关联的事务的最终结果。</span><span class="sxs-lookup"><span data-stu-id="139b1-159">Decides the final outcome of the transaction associated with the batch operation.</span></span>  
  
 <span data-ttu-id="139b1-160">适配器必须通知[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]关于事务来维护其内部的最终结果跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="139b1-160">The adapter must inform [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] about the final outcome of the transaction to maintain its internal tracking data.</span></span> <span data-ttu-id="139b1-161">适配器通知[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过调用的结果的**DTCConfirmCommit**。</span><span class="sxs-lookup"><span data-stu-id="139b1-161">The adapter informs [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] of the outcome by calling **DTCConfirmCommit**.</span></span> <span data-ttu-id="139b1-162">如果适配器没有这样做，则会发生重大内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="139b1-162">If the adapter does not do this, a significant memory leak occurs.</span></span>  
  
 <span data-ttu-id="139b1-163">上述两个任务（解决错误和确定最终结果）看似非常简单，但实际上，它们依赖于来自不同线程的信息：</span><span class="sxs-lookup"><span data-stu-id="139b1-163">The two tasks listed above (resolve errors and decide the final outcome) seem simple enough, but in fact they rely on information from different threads:</span></span>  
  
-   <span data-ttu-id="139b1-164">适配器来处理基于信息由传递的错误[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到**BatchComplete**适配器中的回调。</span><span class="sxs-lookup"><span data-stu-id="139b1-164">The adapter processes errors based on information passed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the **BatchComplete** callback in the adapter.</span></span> <span data-ttu-id="139b1-165">此回调针对适配器的线程。</span><span class="sxs-lookup"><span data-stu-id="139b1-165">This callback is on the adapter's thread.</span></span>  
  
-   <span data-ttu-id="139b1-166">**DTCConfirmCommit**上是一种方法**IBTDTCCommitConfirm**对象。</span><span class="sxs-lookup"><span data-stu-id="139b1-166">**DTCConfirmCommit** is a method on the **IBTDTCCommitConfirm** object.</span></span> <span data-ttu-id="139b1-167">实例**IBTDTCCommitConfirm**对象返回批处理**IBTTransportBatch::Done**调用。</span><span class="sxs-lookup"><span data-stu-id="139b1-167">An instance of the **IBTDTCCommitConfirm** object is returned by the batch **IBTTransportBatch::Done** call.</span></span> <span data-ttu-id="139b1-168">此实例位于相同的线程上**IBTTransportBatch::Done**调用，即不同于适配器的线程。</span><span class="sxs-lookup"><span data-stu-id="139b1-168">This instance is on the same thread as the **IBTTransportBatch::Done** call, which is different from the adapter's thread.</span></span>  
  
-   <span data-ttu-id="139b1-169">适配器对每次调用**IBTTransportBatch::Done**没有对应的回调， **BatchComplete**，即消息传送引擎调用另一个线程中报告的结果批次提交。</span><span class="sxs-lookup"><span data-stu-id="139b1-169">For every call that the adapter makes to **IBTTransportBatch::Done** there is a corresponding callback, **BatchComplete**, that is called by the Messaging Engine in a separate thread to report the result of the batch submission.</span></span> <span data-ttu-id="139b1-170">在**BatchComplete**批处理适配器需要提交或回滚事务基于是否通过或失败。</span><span class="sxs-lookup"><span data-stu-id="139b1-170">In **BatchComplete** the adapter needs to commit or roll back the transaction based on whether the batch passed or failed.</span></span> <span data-ttu-id="139b1-171">在任一情况下，适配器然后应调用**DTCConfirmCommit**报告到 the Messaging Engine 事务的状态。</span><span class="sxs-lookup"><span data-stu-id="139b1-171">In either case, the adapter should then call **DTCConfirmCommit** to report the status of the transaction to the Messaging Engine.</span></span>  
  
 <span data-ttu-id="139b1-172">可能的争用情况存在因为适配器的实现**BatchComplete**可以假设**IBTDTCCommitConfirm**返回对象**IBTTransportBatch::Done**始终可用，是何时**BatchComplete**执行。</span><span class="sxs-lookup"><span data-stu-id="139b1-172">A possible race condition exists because the adapter’s implementation of **BatchComplete** can assume that the **IBTDTCCommitConfirm** object returned by **IBTTransportBatch::Done** is always available when **BatchComplete** executes.</span></span> <span data-ttu-id="139b1-173">但是， **BatchComplete**可以在单独的消息传送引擎线程，即使之前调用**IBTTransportBatch::Done**返回。</span><span class="sxs-lookup"><span data-stu-id="139b1-173">However, **BatchComplete** can be called in a separate Messaging Engine thread, even before **IBTTransportBatch::Done** returns.</span></span> <span data-ttu-id="139b1-174">可能的适配器尝试访问**IBTDTCCommitConfirm**对象作为的一部分**BatchComplete**实现中，没有访问冲突。</span><span class="sxs-lookup"><span data-stu-id="139b1-174">It is possible that when the adapter tries to access the **IBTDTCCommitConfirm** object as a part of the **BatchComplete** implementation, there is an access violation.</span></span>  
  
 <span data-ttu-id="139b1-175">在以下示例中，通过使用事件来解决该问题。</span><span class="sxs-lookup"><span data-stu-id="139b1-175">The problem is solved with an event in the following example.</span></span> <span data-ttu-id="139b1-176">在这里，通过使用事件的属性来访问接口指针。</span><span class="sxs-lookup"><span data-stu-id="139b1-176">Here the interface pointer is accessed through a property that uses the event.</span></span> <span data-ttu-id="139b1-177">get 总是等待 set。</span><span class="sxs-lookup"><span data-stu-id="139b1-177">The get always waits for the set.</span></span>  
  
```  
protected IBTDTCCommitConfirm CommitConfirm  
{  
   set  
   {  
       this.commitConfirm = value;  
       this.commitConfirmEvent.Set();  
   }  
   get  
   {  
       this.commitConfirmEvent.WaitOne();  
       return this.commitConfirm;  
   }  
}  
protected IBTDTCCommitConfirm commitConfirm = null;  
private ManualResetEvent commitConfirmEvent = new ManualResetEvent(false);  
```  
  
 <span data-ttu-id="139b1-178">现在将分配中的返回值**IBTTransportBatch::Done**到此属性，并使用它在**BatchComplete**调用。</span><span class="sxs-lookup"><span data-stu-id="139b1-178">Now assign the return value from **IBTTransportBatch::Done** to this property and use it in the **BatchComplete** call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="139b1-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="139b1-179">See Also</span></span>  
 [<span data-ttu-id="139b1-180">事务性消息批</span><span class="sxs-lookup"><span data-stu-id="139b1-180">Transactional Message Batches</span></span>](../core/transactional-message-batches.md)