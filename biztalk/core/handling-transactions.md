---
title: 处理事务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d360742-e969-4651-b364-9edc6a93b8d4
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea7601fdb2a11927cee0a9ffcbcb00b5c689e70b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387587"
---
# <a name="handling-transactions"></a><span data-ttu-id="0abc7-102">处理事务</span><span class="sxs-lookup"><span data-stu-id="0abc7-102">Handling Transactions</span></span>
## <a name="transacted-receivers"></a><span data-ttu-id="0abc7-103">事务性的接收器</span><span class="sxs-lookup"><span data-stu-id="0abc7-103">Transacted Receivers</span></span>  
 <span data-ttu-id="0abc7-104">事务性的接收器和非事务性的接收器之间的主要区别是事务性的接收器创建和使用显式 MSDTC 事务以确保其数据源之间的原子性和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="0abc7-104">The main difference between transacted receivers and nontransacted receivers is that transacted receivers create and use an explicit MSDTC transaction to ensure atomicity between their data source and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox database.</span></span> <span data-ttu-id="0abc7-105">一般情况下，适配器的其他方面是相同。</span><span class="sxs-lookup"><span data-stu-id="0abc7-105">In general every other aspect of the adapter is the same.</span></span>  
  
 <span data-ttu-id="0abc7-106">应注意的是请求-响应接收适配器仅用于事务提交到消息引擎的原始请求消息。</span><span class="sxs-lookup"><span data-stu-id="0abc7-106">It should be noted that a request-response receive adapter only uses a transaction for submitting the original request message to the Messaging Engine.</span></span> <span data-ttu-id="0abc7-107">从消息引擎发送到适配器的响应的传输需要不同的事务。</span><span class="sxs-lookup"><span data-stu-id="0abc7-107">A different transaction is needed for the transmission of the response sent from the Messaging Engine to the adapter.</span></span> <span data-ttu-id="0abc7-108">这是因为第一个事务的作用域是在适配器和 MessageBox 数据库之间。</span><span class="sxs-lookup"><span data-stu-id="0abc7-108">This is because the scope of the first transaction is between the adapter and the MessageBox database.</span></span> <span data-ttu-id="0abc7-109">后续的请求消息才会向适配器从消息引擎为原始请求消息的事务提交之前。</span><span class="sxs-lookup"><span data-stu-id="0abc7-109">The subsequent request message is not sent to the adapter from the Messaging Engine until the transaction for the original request message commits.</span></span>  
  
 <span data-ttu-id="0abc7-110">以下对象交互图说明了适配器和消息引擎之间的传入消息事务性提交过程的交互。</span><span class="sxs-lookup"><span data-stu-id="0abc7-110">The following object interaction diagram illustrates the interaction between the adapter and the Messaging Engine during a transactional submission of incoming messages.</span></span> <span data-ttu-id="0abc7-111">在此示例中，以下一系列交互会发生：</span><span class="sxs-lookup"><span data-stu-id="0abc7-111">In this example, the following sequence of interactions takes place:</span></span>  
  
1. <span data-ttu-id="0abc7-112">适配器从引擎获取新批。</span><span class="sxs-lookup"><span data-stu-id="0abc7-112">The adapter gets a new batch from the engine.</span></span>  
  
2. <span data-ttu-id="0abc7-113">适配器创建新的 MSDTC 事务。</span><span class="sxs-lookup"><span data-stu-id="0abc7-113">The adapter creates a new MSDTC transaction.</span></span>  
  
3. <span data-ttu-id="0abc7-114">适配器从其已在事务中登记的数据源执行破坏性读取。</span><span class="sxs-lookup"><span data-stu-id="0abc7-114">The adapter does a destructive read from its data source that has been enlisted in the transaction.</span></span>  
  
4. <span data-ttu-id="0abc7-115">适配器提交消息。</span><span class="sxs-lookup"><span data-stu-id="0abc7-115">The adapter submits the message.</span></span>  
  
5. <span data-ttu-id="0abc7-116">适配器调用**完成**上的批处理，传入其 MSDTC 事务并将其**BatchComplete**回调指针。</span><span class="sxs-lookup"><span data-stu-id="0abc7-116">The adapter calls **Done** on the batch, passing in its MSDTC transaction and its **BatchComplete** callback pointer.</span></span> <span data-ttu-id="0abc7-117">引擎将返回**IBTDTCCommitConfirm**接口。</span><span class="sxs-lookup"><span data-stu-id="0abc7-117">The engine returns an **IBTDTCCommitConfirm** interface.</span></span>  
  
6. <span data-ttu-id="0abc7-118">引擎处理该批，适配器回调在其**BatchComplete**实现中，并传达其消息处理到适配器的状态。</span><span class="sxs-lookup"><span data-stu-id="0abc7-118">The engine processes the batch, calls the adapter back on its **BatchComplete** implementation, and conveys the status of its message processing to the adapter.</span></span>  
  
7. <span data-ttu-id="0abc7-119">如果该批成功，则适配器将提交该事务并调用**IBTDTCCommitConfirm.DTCCommitConfirm** API 使用`true`提交的值。</span><span class="sxs-lookup"><span data-stu-id="0abc7-119">If the batch was successful the adapter commits the transaction and calls the **IBTDTCCommitConfirm.DTCCommitConfirm** API with a `true` value signifying commit.</span></span>  
  
   <span data-ttu-id="0abc7-120">![](../core/media/transactedreceiver.gif "TransactedReceiver")</span><span class="sxs-lookup"><span data-stu-id="0abc7-120">![](../core/media/transactedreceiver.gif "TransactedReceiver")</span></span>  
  
## <a name="transacted-transmitters"></a><span data-ttu-id="0abc7-121">事务性的发送器</span><span class="sxs-lookup"><span data-stu-id="0abc7-121">Transacted Transmitters</span></span>  
 <span data-ttu-id="0abc7-122">事务性的适配器在大多数情况下非常类似于非事务的适配器。</span><span class="sxs-lookup"><span data-stu-id="0abc7-122">Transacted adapters are for the most part very similar to nontransacted adapters.</span></span> <span data-ttu-id="0abc7-123">主要区别在于，事务性的适配器将数据发送消息中对它已在 MSDTC 事务中登记的资源。</span><span class="sxs-lookup"><span data-stu-id="0abc7-123">The main difference is that the transacted adapter sends the data in the message to a resource that it has enlisted in an MSDTC transaction.</span></span>  
  
 <span data-ttu-id="0abc7-124">**实现提示：** 对于事务性发送，适配器应使用相同的 MSDTC 事务来将数据写入到目标和用于删除通过**IBTTransportBatch.DeleteMessage**方法调用。</span><span class="sxs-lookup"><span data-stu-id="0abc7-124">**Implementation Tip:** For transacted sends, the adapter should use the same MSDTC transaction for writing the data to the destination and for deleting it through the **IBTTransportBatch.DeleteMessage** method call.</span></span> <span data-ttu-id="0abc7-125">仅这两个操作需要进行事务处理。</span><span class="sxs-lookup"><span data-stu-id="0abc7-125">Only these two operations need to be transacted.</span></span> <span data-ttu-id="0abc7-126">任何其他操作，如**IBTTransportBatch.Resubmit**， **IBTTransportBatch.MoveToNextTransport**，并**IBTTransportBatch.MoveToSuspendQ**不一定要事务处理。</span><span class="sxs-lookup"><span data-stu-id="0abc7-126">Any other operations, such as **IBTTransportBatch.Resubmit**, **IBTTransportBatch.MoveToNextTransport**, and **IBTTransportBatch.MoveToSuspendQ** do not need to be transacted.</span></span> <span data-ttu-id="0abc7-127">这是因为引擎隐式使用事务，并且这些类型的操作不需要是原子就目标而言。</span><span class="sxs-lookup"><span data-stu-id="0abc7-127">This is because the engine implicitly uses a transaction and these types of operations do not need to be atomic with respect to the destination.</span></span>  
  
 <span data-ttu-id="0abc7-128">以下对象交互图说明了适配器和引擎之间的交互。</span><span class="sxs-lookup"><span data-stu-id="0abc7-128">The following object interaction diagram illustrates the interactions between the adapter and the engine.</span></span> <span data-ttu-id="0abc7-129">事件序列如下所示：</span><span class="sxs-lookup"><span data-stu-id="0abc7-129">The sequence of events is as follows:</span></span>  
  
1. <span data-ttu-id="0abc7-130">引擎从适配器获取新批。</span><span class="sxs-lookup"><span data-stu-id="0abc7-130">The engine gets a new batch from the adapter.</span></span>  
  
2. <span data-ttu-id="0abc7-131">该引擎将两个消息添加到新的批。</span><span class="sxs-lookup"><span data-stu-id="0abc7-131">The engine adds two messages to the new batch.</span></span>  
  
3. <span data-ttu-id="0abc7-132">引擎将调用**完成**对批，导致适配器将该批发送到提供服务的内部传输队列由其线程池。</span><span class="sxs-lookup"><span data-stu-id="0abc7-132">The engine calls **Done** on the batch, causing the adapter to post the batch to its internal transmit queue that is serviced by its thread pool.</span></span>  
  
4. <span data-ttu-id="0abc7-133">适配器创建新的 MSDTC 事务。</span><span class="sxs-lookup"><span data-stu-id="0abc7-133">The adapter creates a new MSDTC transaction.</span></span>  
  
5. <span data-ttu-id="0abc7-134">适配器传输在 MSDTC 事务中登记目标的消息。</span><span class="sxs-lookup"><span data-stu-id="0abc7-134">The adapter transmits the messages enlisting the destination in the MSDTC transaction.</span></span> <span data-ttu-id="0abc7-135">例如，这可能会写入到[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="0abc7-135">For example, this could be writing to a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database.</span></span>  
  
6. <span data-ttu-id="0abc7-136">在传输后，适配器从引擎获取新批。</span><span class="sxs-lookup"><span data-stu-id="0abc7-136">After transmission, the adapter gets a new batch from the engine.</span></span>  
  
7. <span data-ttu-id="0abc7-137">适配器调用**DeleteMessage**它已成功传输的消息。</span><span class="sxs-lookup"><span data-stu-id="0abc7-137">The adapter calls **DeleteMessage** for the messages that it has successfully transmitted.</span></span>  
  
8. <span data-ttu-id="0abc7-138">适配器调用**完成**上传入其 DTC 事务的批处理。</span><span class="sxs-lookup"><span data-stu-id="0abc7-138">The adapter calls **Done** on the batch passing in its DTC transaction.</span></span> <span data-ttu-id="0abc7-139">引擎将返回**IBTDTCCommitConfirm**接口。</span><span class="sxs-lookup"><span data-stu-id="0abc7-139">The engine returns an **IBTDTCCommitConfirm** interface.</span></span>  
  
9. <span data-ttu-id="0abc7-140">引擎处理该批，从应用程序队列中删除消息。</span><span class="sxs-lookup"><span data-stu-id="0abc7-140">The engine processes the batch, deleting the messages from the application queue.</span></span>  
  
10. <span data-ttu-id="0abc7-141">引擎回调适配器**IBTBatchCallback**上成功的删除操作的信息的接口。</span><span class="sxs-lookup"><span data-stu-id="0abc7-141">The engine calls back the adapter's **IBTBatchCallback** interface with information on the success of its deletion operations.</span></span>  
  
11. <span data-ttu-id="0abc7-142">如果该批成功，则适配器提交事务。</span><span class="sxs-lookup"><span data-stu-id="0abc7-142">If the batch was successful, the adapter commits the transactions.</span></span>  
  
12. <span data-ttu-id="0abc7-143">适配器调用**IBTDTCCommitConfirm.DTCCommitConfirm**以便通知引擎已成功提交事务。</span><span class="sxs-lookup"><span data-stu-id="0abc7-143">The adapter calls **IBTDTCCommitConfirm.DTCCommitConfirm** to inform the engine that the transaction was successfully committed.</span></span>  
  
    <span data-ttu-id="0abc7-144">![](../core/media/transactedtransmitter.gif "Transactedtransmitter")</span><span class="sxs-lookup"><span data-stu-id="0abc7-144">![](../core/media/transactedtransmitter.gif "Transactedtransmitter")</span></span>  
  
### <a name="transacted-solicit-response-adapters"></a><span data-ttu-id="0abc7-145">事务性要求-响应适配器</span><span class="sxs-lookup"><span data-stu-id="0abc7-145">Transacted Solicit-Response Adapters</span></span>  
 <span data-ttu-id="0abc7-146">与双向接收不同，可能会使用相同的 DTC 事务执行双向发送。</span><span class="sxs-lookup"><span data-stu-id="0abc7-146">Unlike two-way receives, two-way sends may be performed by using the same DTC transaction.</span></span> <span data-ttu-id="0abc7-147">事务性要求-响应适配器应使用相同**IBTTransportBatch**有关**SubmitResponseMessage**并**DeleteMessage**操作。</span><span class="sxs-lookup"><span data-stu-id="0abc7-147">Transacted solicit-response adapters should use the same **IBTTransportBatch** for the **SubmitResponseMessage** and **DeleteMessage** operations.</span></span> <span data-ttu-id="0abc7-148">此批应使用用于收发要求-响应消息对的相同 MSDTC 事务。</span><span class="sxs-lookup"><span data-stu-id="0abc7-148">This batch should use the same MSDTC transaction that is used to send and receive the solicit-response message pair.</span></span> <span data-ttu-id="0abc7-149">这可确保要求-响应消息交换的原子性。</span><span class="sxs-lookup"><span data-stu-id="0abc7-149">This ensures atomicity for the solicit-response message exchange.</span></span>  
  
## <a name="service-components-and-byot"></a><span data-ttu-id="0abc7-150">服务组件和 BYOT</span><span class="sxs-lookup"><span data-stu-id="0abc7-150">Service Components and BYOT</span></span>  
 <span data-ttu-id="0abc7-151">消息引擎 Api 要求提供 MSDTC 事务。</span><span class="sxs-lookup"><span data-stu-id="0abc7-151">The Messaging Engine APIs require an MSDTC transaction to be supplied.</span></span> <span data-ttu-id="0abc7-152">但是某些.NET 组件设计用于为服务组件，并且不允许以编程方式提交或中止的事务。</span><span class="sxs-lookup"><span data-stu-id="0abc7-152">However some .NET components are designed to be used as serviced components and do not allow the transaction to be programmatically committed or aborted.</span></span> <span data-ttu-id="0abc7-153">相反，该平台上的 COM + 运行时自动提交事务。</span><span class="sxs-lookup"><span data-stu-id="0abc7-153">Instead, the transaction is automatically committed by the COM+ runtime on that platform.</span></span>  
  
 <span data-ttu-id="0abc7-154">对于这种情况，适配器应使用自带您自己事务 (BYOT)。</span><span class="sxs-lookup"><span data-stu-id="0abc7-154">For these scenarios, the adapter should use Bring Your Own Transaction (BYOT).</span></span> <span data-ttu-id="0abc7-155">这允许适配器创建 MSDTC 事务，实例化使用该事务的.NET 组件并使该组件继承创建的事务，而不是创建其自己的事务。</span><span class="sxs-lookup"><span data-stu-id="0abc7-155">This allows the adapter to create an MSDTC transaction, instantiate the .NET component that uses the transaction, and allow that component to inherit the created transaction rather than create its own transaction.</span></span> <span data-ttu-id="0abc7-156">.NET Framework 提供了**System.EnterpriseServices.BYOT**实现此目的。</span><span class="sxs-lookup"><span data-stu-id="0abc7-156">The .NET Framework provides **System.EnterpriseServices.BYOT** for this purpose.</span></span> <span data-ttu-id="0abc7-157">SDK BaseAdapter 提供帮助器类**BYOTTransaction**，实现此目的。</span><span class="sxs-lookup"><span data-stu-id="0abc7-157">The SDK BaseAdapter provides a helper class, **BYOTTransaction**, for this purpose.</span></span>  
  
## <a name="avoiding-race-conditions"></a><span data-ttu-id="0abc7-158">避免争用情况</span><span class="sxs-lookup"><span data-stu-id="0abc7-158">Avoiding Race Conditions</span></span>  
 <span data-ttu-id="0abc7-159">当你编写的适配器的创建事务对象，并将其到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，表明您接受负责编写代码，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0abc7-159">When you write an adapter that creates a transaction object and hands it to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you are accepting responsibility for writing code that does the following:</span></span>  
  
- <span data-ttu-id="0abc7-160">解析与批处理相关联的消息中的错误。</span><span class="sxs-lookup"><span data-stu-id="0abc7-160">Resolves errors in messages associated with the batch.</span></span>  
  
- <span data-ttu-id="0abc7-161">确定与批操作相关联的事务的最终结果。</span><span class="sxs-lookup"><span data-stu-id="0abc7-161">Decides the final outcome of the transaction associated with the batch operation.</span></span>  
  
  <span data-ttu-id="0abc7-162">适配器必须通知[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]要维护其内部的事务的最终结果跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="0abc7-162">The adapter must inform [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] about the final outcome of the transaction to maintain its internal tracking data.</span></span> <span data-ttu-id="0abc7-163">适配器通知[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的结果通过调用**DTCConfirmCommit**。</span><span class="sxs-lookup"><span data-stu-id="0abc7-163">The adapter informs [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] of the outcome by calling **DTCConfirmCommit**.</span></span> <span data-ttu-id="0abc7-164">如果适配器不会执行此操作，会发生重大内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="0abc7-164">If the adapter does not do this, a significant memory leak occurs.</span></span>  
  
  <span data-ttu-id="0abc7-165">上面列出的两个任务 （解决错误和确定最终结果） 看似非常简单，但实际上它们依赖于来自不同线程的信息：</span><span class="sxs-lookup"><span data-stu-id="0abc7-165">The two tasks listed above (resolve errors and decide the final outcome) seem simple enough, but in fact they rely on information from different threads:</span></span>  
  
- <span data-ttu-id="0abc7-166">适配器处理错误时，基于传递的信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到**BatchComplete**在适配器中的回调。</span><span class="sxs-lookup"><span data-stu-id="0abc7-166">The adapter processes errors based on information passed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the **BatchComplete** callback in the adapter.</span></span> <span data-ttu-id="0abc7-167">此回叫是适配器的线程上。</span><span class="sxs-lookup"><span data-stu-id="0abc7-167">This callback is on the adapter's thread.</span></span>  
  
- <span data-ttu-id="0abc7-168">**DTCConfirmCommit**上是一种方法**IBTDTCCommitConfirm**对象。</span><span class="sxs-lookup"><span data-stu-id="0abc7-168">**DTCConfirmCommit** is a method on the **IBTDTCCommitConfirm** object.</span></span> <span data-ttu-id="0abc7-169">实例**IBTDTCCommitConfirm**对象返回的批处理**ibttransportbatch:: Done**调用。</span><span class="sxs-lookup"><span data-stu-id="0abc7-169">An instance of the **IBTDTCCommitConfirm** object is returned by the batch **IBTTransportBatch::Done** call.</span></span> <span data-ttu-id="0abc7-170">此实例是作为在同一线程上**ibttransportbatch:: Done**调用，这是不同于适配器的线程。</span><span class="sxs-lookup"><span data-stu-id="0abc7-170">This instance is on the same thread as the **IBTTransportBatch::Done** call, which is different from the adapter's thread.</span></span>  
  
- <span data-ttu-id="0abc7-171">对于适配器对每个调用**ibttransportbatch:: Done**没有相应的回调**BatchComplete**，也就是说，消息引擎调用在单独的线程以报告的结果中的批提交。</span><span class="sxs-lookup"><span data-stu-id="0abc7-171">For every call that the adapter makes to **IBTTransportBatch::Done** there is a corresponding callback, **BatchComplete**, that is called by the Messaging Engine in a separate thread to report the result of the batch submission.</span></span> <span data-ttu-id="0abc7-172">在中**BatchComplete**批的适配器需要提交或回滚该事务基于是否通过或失败。</span><span class="sxs-lookup"><span data-stu-id="0abc7-172">In **BatchComplete** the adapter needs to commit or roll back the transaction based on whether the batch passed or failed.</span></span> <span data-ttu-id="0abc7-173">在任一情况下，适配器应然后调用**DTCConfirmCommit**报告给消息引擎该事务的状态。</span><span class="sxs-lookup"><span data-stu-id="0abc7-173">In either case, the adapter should then call **DTCConfirmCommit** to report the status of the transaction to the Messaging Engine.</span></span>  
  
  <span data-ttu-id="0abc7-174">因为不存在可能出现的争用条件的适配器的实现**BatchComplete**可以假设**IBTDTCCommitConfirm**返回对象**ibttransportbatch:: Done**时，才始终可用**BatchComplete**执行。</span><span class="sxs-lookup"><span data-stu-id="0abc7-174">A possible race condition exists because the adapter’s implementation of **BatchComplete** can assume that the **IBTDTCCommitConfirm** object returned by **IBTTransportBatch::Done** is always available when **BatchComplete** executes.</span></span> <span data-ttu-id="0abc7-175">但是， **BatchComplete**可以在单独的消息引擎线程，即使之前调用**ibttransportbatch:: Done**返回。</span><span class="sxs-lookup"><span data-stu-id="0abc7-175">However, **BatchComplete** can be called in a separate Messaging Engine thread, even before **IBTTransportBatch::Done** returns.</span></span> <span data-ttu-id="0abc7-176">可以当适配器尝试访问**IBTDTCCommitConfirm**对象的一部分**BatchComplete**实现中，没有访问冲突。</span><span class="sxs-lookup"><span data-stu-id="0abc7-176">It is possible that when the adapter tries to access the **IBTDTCCommitConfirm** object as a part of the **BatchComplete** implementation, there is an access violation.</span></span>  
  
  <span data-ttu-id="0abc7-177">使用下面的示例中的事件解决此问题。</span><span class="sxs-lookup"><span data-stu-id="0abc7-177">The problem is solved with an event in the following example.</span></span> <span data-ttu-id="0abc7-178">此处可通过使用事件属性访问的接口指针。</span><span class="sxs-lookup"><span data-stu-id="0abc7-178">Here the interface pointer is accessed through a property that uses the event.</span></span> <span data-ttu-id="0abc7-179">Get 总是等待 set。</span><span class="sxs-lookup"><span data-stu-id="0abc7-179">The get always waits for the set.</span></span>  
  
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
  
 <span data-ttu-id="0abc7-180">现在，从返回的值将分配**ibttransportbatch:: Done**给此属性，并将其**BatchComplete**调用。</span><span class="sxs-lookup"><span data-stu-id="0abc7-180">Now assign the return value from **IBTTransportBatch::Done** to this property and use it in the **BatchComplete** call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0abc7-181">请参阅</span><span class="sxs-lookup"><span data-stu-id="0abc7-181">See Also</span></span>  
 [<span data-ttu-id="0abc7-182">事务性消息批</span><span class="sxs-lookup"><span data-stu-id="0abc7-182">Transactional Message Batches</span></span>](../core/transactional-message-batches.md)