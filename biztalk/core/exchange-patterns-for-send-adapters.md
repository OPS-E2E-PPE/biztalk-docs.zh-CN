---
title: 发送适配器的交换模式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ad65fb5-640d-4bd2-aabe-946210f58a22
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4cef519e4648814e1636daac7b60a42addf5111
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978366"
---
# <a name="exchange-patterns-for-send-adapters"></a><span data-ttu-id="36c2d-102">发送适配器的交换模式</span><span class="sxs-lookup"><span data-stu-id="36c2d-102">Exchange Patterns for Send Adapters</span></span>
<span data-ttu-id="36c2d-103">发送适配器传送消息从 BizTalk 消息引擎，以通过网络传输。</span><span class="sxs-lookup"><span data-stu-id="36c2d-103">Send adapters are delivered messages from the BizTalk Messaging Engine to be transmitted over the wire.</span></span> <span data-ttu-id="36c2d-104">所使用的单向或双向消息交换模式，可能会发送这些消息。</span><span class="sxs-lookup"><span data-stu-id="36c2d-104">These messages may be sent by using a one-way or two-way message exchange pattern.</span></span> <span data-ttu-id="36c2d-105">处理此双向消息交换模式的适配器称为要求-响应适配器。</span><span class="sxs-lookup"><span data-stu-id="36c2d-105">An adapter that handles this two-way message exchange pattern is called a Solicit-Response adapter.</span></span>  

## <a name="blocking-vs-non-blocking-transmissions"></a><span data-ttu-id="36c2d-106">阻止 vs。非阻塞传输</span><span class="sxs-lookup"><span data-stu-id="36c2d-106">Blocking vs. Non-Blocking Transmissions</span></span>  
 <span data-ttu-id="36c2d-107">消息引擎将消息传送到发送适配器，通过使用**IBTTransmitter.TransmitMessage**方法或**IBTTransmitterBatch.TransmitMessage**方法，具体取决于可识别批的适配器。</span><span class="sxs-lookup"><span data-stu-id="36c2d-107">The Messaging Engine delivers messages to the send adapter by using either the **IBTTransmitter.TransmitMessage** method or the **IBTTransmitterBatch.TransmitMessage** method, depending on whether the adapter is batch-aware.</span></span> <span data-ttu-id="36c2d-108">这两个版本的方法有一个布尔返回值，该值指示适配器如何传输该消息。</span><span class="sxs-lookup"><span data-stu-id="36c2d-108">Both versions of the method have a Boolean return value that indicates how the adapter transmitted the message.</span></span> <span data-ttu-id="36c2d-109">如果适配器返回 `true`，则在返回前它已发送完消息。</span><span class="sxs-lookup"><span data-stu-id="36c2d-109">If the adapter returns `true`, it has completely sent the message before returning.</span></span> <span data-ttu-id="36c2d-110">在这种情况下，消息引擎从 MessageBox 数据库代表适配器删除消息。</span><span class="sxs-lookup"><span data-stu-id="36c2d-110">In this case the Messaging Engine deletes the message from the MessageBox database on behalf of the adapter.</span></span> <span data-ttu-id="36c2d-111">如果适配器返回 `false`，则适配器已开始传送消息，但是在传送未完成之前就返回了。</span><span class="sxs-lookup"><span data-stu-id="36c2d-111">If the adapter returns `false`, it started message transmission and returned before the transmission completed.</span></span> <span data-ttu-id="36c2d-112">在这种情况下，适配器负责不仅用于删除从其应用程序队列发送消息，但还用于处理需要要传输的重试或挂起的消息传输失败。</span><span class="sxs-lookup"><span data-stu-id="36c2d-112">In this case, the adapter is responsible not only for deleting the message from its application queue but also for handling transmission failures that require the message to be retried for transmission or suspended.</span></span>  

 <span data-ttu-id="36c2d-113">适配器返回`false`是非阻塞调用，这表示**TransmitMessage**实现代码不会阻止消息引擎调用线程。</span><span class="sxs-lookup"><span data-stu-id="36c2d-113">The adapter returning `false` is a nonblocking call, meaning that the **TransmitMessage** implementation code does not block the calling thread of the Messaging Engine.</span></span> <span data-ttu-id="36c2d-114">适配器只需将消息添加到准备要传输的内存中队列，然后返回。</span><span class="sxs-lookup"><span data-stu-id="36c2d-114">The adapter simply adds the message to an in-memory queue ready to be transmitted and then returns.</span></span> <span data-ttu-id="36c2d-115">适配器应具有自己的线程池的服务的内存中队列、 传输消息，并随后通知传输结果的引擎。</span><span class="sxs-lookup"><span data-stu-id="36c2d-115">The adapter should have its own thread pool that services the in-memory queue, transmits the message, and then notifies the engine of the outcome of the transmission.</span></span>  

 <span data-ttu-id="36c2d-116">消息引擎线程是通常更多的 CPU 绑定用于通过网络发送数据的线程。</span><span class="sxs-lookup"><span data-stu-id="36c2d-116">The Messaging Engine’s threads are typically more CPU bound than the threads used to send data over the wire.</span></span> <span data-ttu-id="36c2d-117">混合使用这两种类型的线程对性能有负面影响。</span><span class="sxs-lookup"><span data-stu-id="36c2d-117">Mixing these two types of threads has a negative impact on performance.</span></span> <span data-ttu-id="36c2d-118">非阻塞发送启用分离这两种类型的线程，并阻止调用产生显著的性能改善。</span><span class="sxs-lookup"><span data-stu-id="36c2d-118">Non-blocking sends enable the decoupling of these two types of threads and yield a significant performance improvement over blocking calls.</span></span>  

 <span data-ttu-id="36c2d-119">下图显示了适配器的线程池，其中可以往往会受 I/O 操作。</span><span class="sxs-lookup"><span data-stu-id="36c2d-119">The following diagram shows the adapter's thread pool which can tend to be bound by I/O operations.</span></span> <span data-ttu-id="36c2d-120">BizTalk Server 消息引擎的线程池是多个由 CPU 处理绑定。</span><span class="sxs-lookup"><span data-stu-id="36c2d-120">The BizTalk Server Messaging Engine's thread pool is more bound by the CPU processing.</span></span> <span data-ttu-id="36c2d-121">通过使两个不同的线程池并不混合使用相同类型的线程系统可以更有效地运行。</span><span class="sxs-lookup"><span data-stu-id="36c2d-121">By keeping two different thread pools and not mixing the same type of threads the system can operate more efficiently.</span></span>  

 <span data-ttu-id="36c2d-122">![](../core/media/io-cpu-bound-threadpools.gif "Io_cpu_bound_threadpools")</span><span class="sxs-lookup"><span data-stu-id="36c2d-122">![](../core/media/io-cpu-bound-threadpools.gif "Io_cpu_bound_threadpools")</span></span>  

 <span data-ttu-id="36c2d-123">**性能提示：** 为了获得最佳性能，发送适配器应该非阻止性并且能够识别批。</span><span class="sxs-lookup"><span data-stu-id="36c2d-123">**Performance Tip:** For the best performance, send adapters should be nonblocking and batch aware.</span></span> <span data-ttu-id="36c2d-124">BizTalk 文件适配器从阻塞和非批处理识别已更改时为非阻止性和批处理注意，已实现了三倍的性能提升。</span><span class="sxs-lookup"><span data-stu-id="36c2d-124">When the BizTalk File adapter was changed from blocking and non-batch aware to nonblocking and batch aware, a threefold performance gain was realized.</span></span>  

 <span data-ttu-id="36c2d-125">**故障排除提示：** 阻塞传输可能会导致整个主机实例的性能下降。</span><span class="sxs-lookup"><span data-stu-id="36c2d-125">**Troubleshooting Tip:** Blocking transmits can cause a performance degradation of an entire host instance.</span></span> <span data-ttu-id="36c2d-126">如果适配器造成过多阻塞**TransmitMessage**将阻止引擎线程将消息传递到其他适配器。</span><span class="sxs-lookup"><span data-stu-id="36c2d-126">If the adapter does excessive blocking in **TransmitMessage** it will prevent engine threads from delivering messages to other adapters.</span></span>  

## <a name="non-batched-sends"></a><span data-ttu-id="36c2d-127">非批处理发送</span><span class="sxs-lookup"><span data-stu-id="36c2d-127">Non-Batched Sends</span></span>  
 <span data-ttu-id="36c2d-128">不能识别批的适配器应该实现**IBTTransmitter**中所述[异步发送适配器的接口](../core/interfaces-for-an-asynchronous-send-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="36c2d-128">Adapters that are not batch aware should implement **IBTTransmitter** as detailed in [Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md).</span></span> <span data-ttu-id="36c2d-129">为每条消息，适配器需要传送消息引擎调用**IBTTransmitter.TransmitMessage**。</span><span class="sxs-lookup"><span data-stu-id="36c2d-129">For each message that the adapter needs to transmit the Messaging Engine calls **IBTTransmitter.TransmitMessage**.</span></span> <span data-ttu-id="36c2d-130">下面的对象交互图详细说明了典型的方法以传输消息，其中包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="36c2d-130">The object interaction diagram below details the typical approach for transmitting messages, which consists of the following steps:</span></span>  

1. <span data-ttu-id="36c2d-131">该引擎的消息传递到适配器。</span><span class="sxs-lookup"><span data-stu-id="36c2d-131">The engine delivers the message to the adapter.</span></span>  

2. <span data-ttu-id="36c2d-132">适配器将准备要传输的内存中队列消息中。</span><span class="sxs-lookup"><span data-stu-id="36c2d-132">The adapter enqueues the message to an in-memory queue ready to be transmitted.</span></span>  

3. <span data-ttu-id="36c2d-133">从适配器的线程池线程取消排队的消息从队列中读取消息，配置，并通过网络传输消息。</span><span class="sxs-lookup"><span data-stu-id="36c2d-133">A thread from the adapter's thread pool dequeues the message from the queue, reads the configuration for the message, and transmits the message over the wire.</span></span>  

4. <span data-ttu-id="36c2d-134">适配器从引擎中获取新批。</span><span class="sxs-lookup"><span data-stu-id="36c2d-134">The adapter gets a new batch from the engine.</span></span>  

5. <span data-ttu-id="36c2d-135">适配器调用**DeleteMessage** batch，传入刚刚传输的消息上。</span><span class="sxs-lookup"><span data-stu-id="36c2d-135">The adapter calls **DeleteMessage** on the batch, passing in the message that it has just transmitted.</span></span>  

6. <span data-ttu-id="36c2d-136">适配器调用**完成**对批。</span><span class="sxs-lookup"><span data-stu-id="36c2d-136">The adapter calls **Done** on the batch.</span></span>  

7. <span data-ttu-id="36c2d-137">引擎处理该批，并从应用程序队列中删除消息。</span><span class="sxs-lookup"><span data-stu-id="36c2d-137">The engine processes the batch and deletes the message from the application queue.</span></span>  

8. <span data-ttu-id="36c2d-138">引擎回调适配器，以通知它的结果**DeleteMessage**操作。</span><span class="sxs-lookup"><span data-stu-id="36c2d-138">The engine calls back the adapter to notify it of the outcome of the **DeleteMessage** operation.</span></span>  

   <span data-ttu-id="36c2d-139">![](../core/media/deleting-from-message-queue.gif "Deleting_from_message_queue")</span><span class="sxs-lookup"><span data-stu-id="36c2d-139">![](../core/media/deleting-from-message-queue.gif "Deleting_from_message_queue")</span></span>  

   <span data-ttu-id="36c2d-140">前面的对象交互图显示了从应用程序队列中删除一条消息的适配器。</span><span class="sxs-lookup"><span data-stu-id="36c2d-140">The preceding object interaction diagram shows the adapter deleting a single message from the application queue.</span></span> <span data-ttu-id="36c2d-141">理想情况下提高而不是上一条消息一次操作消息操作适配器批。</span><span class="sxs-lookup"><span data-stu-id="36c2d-141">Ideally the adapter batches up message operations as opposed to operating on a single message at a time.</span></span>  

## <a name="batched-sends"></a><span data-ttu-id="36c2d-142">成批的发送</span><span class="sxs-lookup"><span data-stu-id="36c2d-142">Batched Sends</span></span>  
 <span data-ttu-id="36c2d-143">可识别批的适配器应该实现**IBTBatchTransmitter**并**IBTTransmitterBatch**中所述[发送适配器的接口](../core/interfaces-for-send-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="36c2d-143">Adapters that are batch aware should implement **IBTBatchTransmitter** and **IBTTransmitterBatch** as detailed in [Interfaces for Send Adapters](../core/interfaces-for-send-adapters.md).</span></span> <span data-ttu-id="36c2d-144">当引擎具有适配器传输的消息时，引擎通过调用从适配器获取新批**IBTBatchTransmitter.GetBatch**。</span><span class="sxs-lookup"><span data-stu-id="36c2d-144">When the engine has messages for the adapter to transmit, the engine gets a new batch from the adapter by calling **IBTBatchTransmitter.GetBatch**.</span></span> <span data-ttu-id="36c2d-145">适配器返回一个新的 batch 对象实现**IBTTransmitterBatch**。</span><span class="sxs-lookup"><span data-stu-id="36c2d-145">The adapter returns a new batch object that implements **IBTTransmitterBatch**.</span></span> <span data-ttu-id="36c2d-146">然后，引擎通过调用启动批处理**IBTTransmitterBatch.BeginBatch**。</span><span class="sxs-lookup"><span data-stu-id="36c2d-146">The engine then starts the batch by calling **IBTTransmitterBatch.BeginBatch**.</span></span> <span data-ttu-id="36c2d-147">此 API 具有输出参数，使适配器对批中指定它将接收的消息最大数目。</span><span class="sxs-lookup"><span data-stu-id="36c2d-147">This API has an out parameter that allows the adapter to specify the maximum number of messages that it will accept on the batch.</span></span> <span data-ttu-id="36c2d-148">该适配器可能会选择性地返回 DTC 事务。</span><span class="sxs-lookup"><span data-stu-id="36c2d-148">The adapter may optionally return a DTC transaction.</span></span> <span data-ttu-id="36c2d-149">引擎随后会调用**IBTTransmitterBatch.TransmitMessage**每条传出消息添加到批的一次。</span><span class="sxs-lookup"><span data-stu-id="36c2d-149">The engine then calls **IBTTransmitterBatch.TransmitMessage** once for each outgoing message to be added to the batch.</span></span> <span data-ttu-id="36c2d-150">这称为次数大于零，但小于或等于由适配器批的最大大小。</span><span class="sxs-lookup"><span data-stu-id="36c2d-150">The number of times this is called is greater than zero but less than or equal to the maximum size of the batch as indicated by the adapter.</span></span> <span data-ttu-id="36c2d-151">当所有消息都已都添加到批时，适配器调用**IBTTransmitterBatch.Done**。</span><span class="sxs-lookup"><span data-stu-id="36c2d-151">When all the messages have been added to the batch, the adapter calls **IBTTransmitterBatch.Done**.</span></span> <span data-ttu-id="36c2d-152">现在适配器通常排入队列中批处理层到其内存中队列的所有消息。</span><span class="sxs-lookup"><span data-stu-id="36c2d-152">At this point the adapter typically enqueues all the messages in the batch to its in-memory queue.</span></span> <span data-ttu-id="36c2d-153">适配器传输来自非可识别批的适配器一样其自身线程池中的线程或线程的消息。</span><span class="sxs-lookup"><span data-stu-id="36c2d-153">The adapter transmits the messages from a thread or threads in its own thread pool as in the case of non-batch-aware adapters.</span></span> <span data-ttu-id="36c2d-154">适配器然后通知传输结果的引擎。</span><span class="sxs-lookup"><span data-stu-id="36c2d-154">The adapter then notifies the engine of the outcome of the transmission.</span></span>  

 <span data-ttu-id="36c2d-155">以下对象交互图说明了两个消息的成批的发送适配器的传输。</span><span class="sxs-lookup"><span data-stu-id="36c2d-155">The following object interaction diagram illustrates the transmission of two messages by a batched send adapter.</span></span>  

 <span data-ttu-id="36c2d-156">![](../core/media/batchedsends.gif "BatchedSends")</span><span class="sxs-lookup"><span data-stu-id="36c2d-156">![](../core/media/batchedsends.gif "BatchedSends")</span></span>  

## <a name="handling-transmission-failures"></a><span data-ttu-id="36c2d-157">处理传输失败</span><span class="sxs-lookup"><span data-stu-id="36c2d-157">Handling Transmission Failures</span></span>  
 <span data-ttu-id="36c2d-158">在下图说明了传输失败所建议的语义。</span><span class="sxs-lookup"><span data-stu-id="36c2d-158">The recommended semantics for transmission failures are illustrated in the figure below.</span></span> <span data-ttu-id="36c2d-159">这些仅仅是建议，不会强制执行由消息引擎。</span><span class="sxs-lookup"><span data-stu-id="36c2d-159">These are only recommendations and are not enforced by the Messaging Engine.</span></span> <span data-ttu-id="36c2d-160">你可以开发偏离这些准则，如果有理由需要执行此操作，但你应小心这种情况下的适配器。</span><span class="sxs-lookup"><span data-stu-id="36c2d-160">You can develop an adapter that deviates from these guidelines if there are valid reasons for doing so but you should be careful in this case.</span></span> <span data-ttu-id="36c2d-161">例如，一般情况下适配器应始终将消息移到备份传输后已用完所有重试。</span><span class="sxs-lookup"><span data-stu-id="36c2d-161">For example, in general an adapter should always move messages to the backup transport after all retries have been exhausted.</span></span>  

 <span data-ttu-id="36c2d-162">更常见的传输可能需要使用比配置的多个重试。</span><span class="sxs-lookup"><span data-stu-id="36c2d-162">More commonly a transport may need to use more retries than are configured.</span></span> <span data-ttu-id="36c2d-163">虽然这是略有不同帐户被视为可接受，因为要增加传输层的恢复能力。</span><span class="sxs-lookup"><span data-stu-id="36c2d-163">While this is slightly different it is considered acceptable because the resilience of the transport layer is being increased.</span></span> <span data-ttu-id="36c2d-164">一般情况下，消息引擎通过公开的 Api 旨在使适配器最大控制，在可能的情况。</span><span class="sxs-lookup"><span data-stu-id="36c2d-164">In general the APIs exposed by the Messaging Engine are designed to give the adapter maximum control where possible.</span></span> <span data-ttu-id="36c2d-165">此控件，提供了更高级别的责任。</span><span class="sxs-lookup"><span data-stu-id="36c2d-165">With this control comes a greater level of responsibility.</span></span>  

 <span data-ttu-id="36c2d-166">![](../core/media/handlingerrors.gif "HandlingErrors")</span><span class="sxs-lookup"><span data-stu-id="36c2d-166">![](../core/media/handlingerrors.gif "HandlingErrors")</span></span>  

 <span data-ttu-id="36c2d-167">适配器可以通过检查系统上下文属性来确定可用于消息的重试次数**RetryCount**。</span><span class="sxs-lookup"><span data-stu-id="36c2d-167">The adapter determines the number of retries available on a message by checking the system context property **RetryCount**.</span></span> <span data-ttu-id="36c2d-168">适配器调用**重新提交**API 一次为每个重试尝试，并传入要重新提交的消息。</span><span class="sxs-lookup"><span data-stu-id="36c2d-168">The adapter calls the **Resubmit** API once for each retry attempt and passes in the message to be resubmitted.</span></span> <span data-ttu-id="36c2d-169">与消息一起传递，该值指示当引擎应将消息传递回适配器时的时间戳。</span><span class="sxs-lookup"><span data-stu-id="36c2d-169">Along with the message it passes the time stamp indicating when the engine should deliver the message back to the adapter.</span></span> <span data-ttu-id="36c2d-170">此值通常应为当前时间加上的值**RetryInterval**。</span><span class="sxs-lookup"><span data-stu-id="36c2d-170">This value should typically be the current time plus the value of **RetryInterval**.</span></span> <span data-ttu-id="36c2d-171">**RetryInterval**是系统上下文属性，单位是分钟。</span><span class="sxs-lookup"><span data-stu-id="36c2d-171">**RetryInterval** is a system context property whose units are minutes.</span></span> <span data-ttu-id="36c2d-172">这两个**RetryCount**并**RetryInterval**在消息上下文是在发送端口配置的值。</span><span class="sxs-lookup"><span data-stu-id="36c2d-172">Both the **RetryCount** and **RetryInterval** in the message context are the values that are configured on the send port.</span></span> <span data-ttu-id="36c2d-173">请考虑在向外扩展部署中使用的相同的多台计算机上部署的 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="36c2d-173">Consider a scaled-out deployment with instances of the same BizTalk Host deployed on multiple computers.</span></span> <span data-ttu-id="36c2d-174">如果重试时间间隔到期后，传递消息，消息可能会被传送到任何它们已配置为运行的计算机上的主机实例的任何一个。</span><span class="sxs-lookup"><span data-stu-id="36c2d-174">If the message is delivered after the retry interval has expired, the message may be delivered to the any one of the host instances on any of the computers where they are configured to run.</span></span> <span data-ttu-id="36c2d-175">为此适配器不应阻止与要使用重试上一条消息关联的任何状态尝试由于并不保证同一适配器的实例将负责在更高版本时传输。</span><span class="sxs-lookup"><span data-stu-id="36c2d-175">For this reason the adapter should not hold any state associated with a message to be used on the retry attempt because there is no guarantee that same instance of the adapter will be responsible for the transmission at a later time.</span></span>  

 <span data-ttu-id="36c2d-176">适配器应仅尝试将消息移到备份传输后重试计数小于或等于零。</span><span class="sxs-lookup"><span data-stu-id="36c2d-176">The adapter should only attempt to move the message to the backup transport after the retry count is less than or equal to zero.</span></span> <span data-ttu-id="36c2d-177">如果没有为端口配置备份传输，尝试将消息移到备份传输将失败。</span><span class="sxs-lookup"><span data-stu-id="36c2d-177">An attempt to move the message to the backup transport will fail if there is no backup transport configured for the port.</span></span> <span data-ttu-id="36c2d-178">在这种情况下应挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="36c2d-178">In this case the message should be suspended.</span></span>  

 <span data-ttu-id="36c2d-179">下面的代码段演示了如何确定重试计数和从消息上下文和后续重新提交间隔或移动到备份传输。</span><span class="sxs-lookup"><span data-stu-id="36c2d-179">The following code fragment illustrates how to determine the retry count and interval from the message context, and the subsequent resubmit or move to the backup transport.</span></span>  

```  
using Microsoft.XLANGs.BaseTypes;  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.BizTalk.TransportProxy.Interop;  
 …  
// RetryCount and RetyInterval are system context properties...  
private static readonly PropertyBase RetryCountProperty =   
 new BTS.RetryCount();  
private static readonly PropertyBase RetryIntervalProperty =   
 new BTS.RetryInterval();  

public void HandleRetry(IBaseMessage msg, IBTTransportBatch batch)  
{  
int retryCount = 0;  
int retryInterval = 0;  

// Get the RetryCount and RetryInterval off the msg ctx...  
 GetMessageRetryState(msg, out retryCount, out retryInterval);  

// If we have retries available resubmit, else move to   
 // backup transport...  
 if ( retryCount > 0 )  
batch.Resubmit(  
 msg, DateTime.Now.AddMinutes(retryInterval));  
else  
batch.MoveToNextTransport(msg);  
}  

public void GetMessageRetryState(  
 IBaseMessage msg,   
 out int retryCount,   
 out int retryInterval )  
{  
retryCount = 0;  
retryInterval = 0;  

object obj =  msg.Context.Read(  
RetryCountProperty.Name.Name,    
RetryCountProperty.Name.Namespace);   

if ( null != obj )  
retryCount = (int)obj;  

obj =  msg.Context.Read(  
RetryIntervalProperty.Name.Name,    
RetryIntervalProperty.Name.Namespace);   

if ( null != obj )  
retryInterval = (int)obj;  
}  
```  

## <a name="throwing-an-exception-from-transmitmessage"></a><span data-ttu-id="36c2d-180">从 TransmitMessage 引发异常</span><span class="sxs-lookup"><span data-stu-id="36c2d-180">Throwing an Exception from TransmitMessage</span></span>  
 <span data-ttu-id="36c2d-181">如果适配器在任何 Api 时引发异常**IBTTransmitter.TransmitMessage**， **IBTTransmitterBatch.TransmitMessage**， **IBTTransmitterBatch.Done**、引擎处理所涉及的消息传输看作失败传输，并采取相应的措施的消息，如中所述[如何处理适配器故障](../core/how-to-handle-adapter-failures.md)。</span><span class="sxs-lookup"><span data-stu-id="36c2d-181">If the adapter throws an exception on any of the APIs **IBTTransmitter.TransmitMessage**, **IBTTransmitterBatch.TransmitMessage**, **IBTTransmitterBatch.Done**, the engine treats the transmission of the messages involved as transmission failures and takes the appropriate action for the message, as detailed in [How to Handle Adapter Failures](../core/how-to-handle-adapter-failures.md).</span></span>  

 <span data-ttu-id="36c2d-182">可识别批的发送适配器引发异常的 TransmitMessage API 会导致整个要清除的批处理和默认传输失败操作正在执行该批处理中的所有消息。</span><span class="sxs-lookup"><span data-stu-id="36c2d-182">For batch-aware send adapters, throwing an exception on the TransmitMessage API results in the entire batch being cleared and the default transmit failure actions being performed for all messages in that batch.</span></span>  

## <a name="solicit-response"></a><span data-ttu-id="36c2d-183">要求-响应</span><span class="sxs-lookup"><span data-stu-id="36c2d-183">Solicit-Response</span></span>  
 <span data-ttu-id="36c2d-184">双向发送适配器通常支持单向和双向传输。</span><span class="sxs-lookup"><span data-stu-id="36c2d-184">Two-way send adapters typically support both one-way and two-way transmissions.</span></span> <span data-ttu-id="36c2d-185">发送适配器可以确定是否应将消息作为单向或双向发送传输通过检查**IsSolicitResponse**系统上下文属性在消息上下文。</span><span class="sxs-lookup"><span data-stu-id="36c2d-185">The send adapter determines whether the message should be transmitted as a one-way or two-way send by inspecting the **IsSolicitResponse** system context property in the message context.</span></span>  

 <span data-ttu-id="36c2d-186">以下代码段演示了这一操作：</span><span class="sxs-lookup"><span data-stu-id="36c2d-186">The following code fragment demonstrates this:</span></span>  

```  
private bool portIsTwoWay = false;  
private static readonly PropertyBase IsSolicitResponseProperty= new BTS.IsSolicitResponse();  

...  

 // Port is one way or two way...  
 object obj =  this.message.Context.Read(  
 IsSolicitResponseProperty.Name.Name,    
 IsSolicitResponseProperty.Name.Namespace);   

if ( null != obj )  
 this.portIsTwoWay = (bool)obj;  
```  

 <span data-ttu-id="36c2d-187">在要求-响应传输过程适配器传输要求消息。</span><span class="sxs-lookup"><span data-stu-id="36c2d-187">During a solicit-response transmission the adapter transmits the solicit message.</span></span> <span data-ttu-id="36c2d-188">之后此工作完成后它将提交相关联的响应和通知消息引擎从 MessageBox 数据库中删除原始的要求消息。</span><span class="sxs-lookup"><span data-stu-id="36c2d-188">After this completed it submits the associated response and tells the Messaging Engine to delete the original solicit message from the MessageBox database.</span></span> <span data-ttu-id="36c2d-189">在应用程序队列删除消息的操作应执行与响应消息提交相同的传输代理批。</span><span class="sxs-lookup"><span data-stu-id="36c2d-189">The action of deleting the message from the application queue should be performed in the same transport proxy batch as the submission of the response message.</span></span> <span data-ttu-id="36c2d-190">这可确保删除操作的原子性和提交的响应。</span><span class="sxs-lookup"><span data-stu-id="36c2d-190">This ensures atomicity of the deletion and submission of the response.</span></span> <span data-ttu-id="36c2d-191">对于完整原子性适配器应使用 DTC 事务，由此识别事务的资源，提交响应消息，要求消息的传输和删除要求消息都在同一 DTC 的上下文事务。</span><span class="sxs-lookup"><span data-stu-id="36c2d-191">For complete atomicity the adapter should use a DTC transaction whereby the transmission of the solicit message to a transaction-aware resource, submission of the response message, and deletion of the solicit message are all in the context of the same DTC transaction.</span></span> <span data-ttu-id="36c2d-192">与往常一样，我们建议使用非阻塞发送传输请求消息。</span><span class="sxs-lookup"><span data-stu-id="36c2d-192">As always, we recommend that the solicit message is transmitted using a non-blocking send.</span></span>  

 <span data-ttu-id="36c2d-193">下面的代码段演示了双向发送的主要方面。</span><span class="sxs-lookup"><span data-stu-id="36c2d-193">The following code fragment illustrates the main aspects of a two-way send.</span></span> <span data-ttu-id="36c2d-194">当引擎调用**IBTTransmitter.TransmitMessage**适配器排入队列传输到内存中队列的消息。</span><span class="sxs-lookup"><span data-stu-id="36c2d-194">When the engine calls **IBTTransmitter.TransmitMessage** the adapter enqueues the message to be transmitted to an in-memory queue.</span></span> <span data-ttu-id="36c2d-195">适配器返回 `false`，指示它在执行非阻塞发送。</span><span class="sxs-lookup"><span data-stu-id="36c2d-195">The adapter returns `false` to indicate that it is performing a non-blocking send.</span></span> <span data-ttu-id="36c2d-196">适配器的线程池 (**WorkerThreadThunk**) 为内存中队列提供服务并将消息以将其提交给帮助器方法。</span><span class="sxs-lookup"><span data-stu-id="36c2d-196">The adapter's thread pool (**WorkerThreadThunk**) services the in-memory queue and dequeues a message to hand it off to a helper method.</span></span> <span data-ttu-id="36c2d-197">此方法负责发送要求消息和接收响应消息。</span><span class="sxs-lookup"><span data-stu-id="36c2d-197">This method is responsible for sending the solicit message and receiving the response message.</span></span> <span data-ttu-id="36c2d-198">（此帮助器方法的实现。 本主题的讨论范围内）响应消息提交到引擎，并从应用程序队列中删除要求消息。</span><span class="sxs-lookup"><span data-stu-id="36c2d-198">(The implementation of this helper method is outside the scope of this topic.) The response message is submitted into the engine, and the solicit message is deleted from the application queue.</span></span>  

```  
using System.Collections;  
using Microsoft.XLANGs.BaseTypes;  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.BizTalk.TransportProxy.Interop;  

     static private Queue _transmitQueue = new Queue();  
  static private IBTTransportProxy _transportProxy = null;   
// IBTTransmitter...  
 public bool TransmitMessage(IBaseMessage msg)  
{  
// Add message to the transmit queue...  
lock(_transmitQueue.SyncRoot)  
 {  
_transmitQueue.Enqueue(msg);  
 }  

 return false;  
}  

 // Threadpool worker thread...   
private void WorkerThreadThunk()  
{  
try  
{  
 IBaseMessage solicitMsg = null;  

 lock(_transmitQueue.SyncRoot)  
 {  
 solicitMsg =   
 (IBaseMessage)_transmitQueue.Dequeue();  
}  

 IBaseMessage responseMsg = SendSolicitResponse(   
 solicitMsg );  
Callback cb = new Callback();  

IBTTransportBatch batch = _transportProxy.GetBatch(  
 cb, null);  
batch.SubmitResponseMessage( solicitMsg, responseMsg );  
batch.DeleteMessage( solicitMsg );  
batch.Done(null);  
}  
catch(Exception)  
{  
// Handle failure....  
}  
}  

static private IBaseMessage SendSolicitResponse(  
 IBaseMessage solicitMsg )  
{  
// Helper method to send solicit message and receive   
 // response message...  
IBaseMessage responseMsg = null;  
return responseMsg;  
}  
```  

## <a name="dynamic-sends"></a><span data-ttu-id="36c2d-199">动态发送</span><span class="sxs-lookup"><span data-stu-id="36c2d-199">Dynamic Sends</span></span>  
 <span data-ttu-id="36c2d-200">动态发送端口不具有与其关联的适配器配置。</span><span class="sxs-lookup"><span data-stu-id="36c2d-200">Dynamic send ports do not have adapter configuration associated with them.</span></span> <span data-ttu-id="36c2d-201">而是他们使用处理程序配置的任何默认属性，适配器需要传送动态端口上的消息。</span><span class="sxs-lookup"><span data-stu-id="36c2d-201">Instead they use handler configuration for any default properties that the adapter needs to transmit messages on a dynamic port.</span></span> <span data-ttu-id="36c2d-202">例如，HTTP 适配器可能需要使用代理服务器并需要提供凭据。</span><span class="sxs-lookup"><span data-stu-id="36c2d-202">For example, an HTTP adapter may need to use a proxy and need to provide credentials.</span></span> <span data-ttu-id="36c2d-203">用户名、 密码和端口无法指定处理程序配置中适配器缓存在运行时。</span><span class="sxs-lookup"><span data-stu-id="36c2d-203">The user name, password, and port could be specified in the handler configuration that the adapter caches at run time.</span></span>  

 <span data-ttu-id="36c2d-204">要确定动态消息是，通过发送传输的引擎**OutboundTransportLocation**与适配器的别名作为前缀。</span><span class="sxs-lookup"><span data-stu-id="36c2d-204">For the engine to determine the transport that a dynamic message is to be sent over, the **OutboundTransportLocation** is prefixed with the adapter's alias.</span></span> <span data-ttu-id="36c2d-205">在安装时，适配器可在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中注册一个或多个别名。</span><span class="sxs-lookup"><span data-stu-id="36c2d-205">An adapter can register one or more aliases with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] at install time.</span></span> <span data-ttu-id="36c2d-206">该引擎将分析**OutboundTransportLocation**在运行时查找匹配项。</span><span class="sxs-lookup"><span data-stu-id="36c2d-206">The engine parses the **OutboundTransportLocation** at run time to find a match.</span></span> <span data-ttu-id="36c2d-207">适配器负责处理**OutboundTransportLocation**无论其前面的别名。</span><span class="sxs-lookup"><span data-stu-id="36c2d-207">The adapter is responsible for handling the **OutboundTransportLocation** with or without the alias prepended to it.</span></span> <span data-ttu-id="36c2d-208">下表显示了已注册的开箱 BizTalk 适配器的别名的一些示例。</span><span class="sxs-lookup"><span data-stu-id="36c2d-208">The following table shows some examples of aliases registered for out-of-the-box BizTalk adapters.</span></span>  


| <span data-ttu-id="36c2d-209">适配器别名</span><span class="sxs-lookup"><span data-stu-id="36c2d-209">Adapter alias</span></span> | <span data-ttu-id="36c2d-210">适配器</span><span class="sxs-lookup"><span data-stu-id="36c2d-210">Adapter</span></span> |   <span data-ttu-id="36c2d-211">OutboundTransportLocation 示例</span><span class="sxs-lookup"><span data-stu-id="36c2d-211">OutboundTransportLocation example</span></span>    |
|---------------|---------|----------------------------------------|
|    <span data-ttu-id="36c2d-212">HTTP://</span><span class="sxs-lookup"><span data-stu-id="36c2d-212">HTTP://</span></span>    |  <span data-ttu-id="36c2d-213">HTTP</span><span class="sxs-lookup"><span data-stu-id="36c2d-213">HTTP</span></span>   |     <span data-ttu-id="36c2d-214">http://www 的用户。</span><span class="sxs-lookup"><span data-stu-id="36c2d-214">http://www.</span></span> <span data-ttu-id="36c2d-215">MyCompany.com/bar</span><span class="sxs-lookup"><span data-stu-id="36c2d-215">MyCompany.com/bar</span></span>      |
|   <span data-ttu-id="36c2d-216">HTTPS://</span><span class="sxs-lookup"><span data-stu-id="36c2d-216">HTTPS://</span></span>    |  <span data-ttu-id="36c2d-217">HTTP</span><span class="sxs-lookup"><span data-stu-id="36c2d-217">HTTP</span></span>   |     <span data-ttu-id="36c2d-218">https://www 的用户。</span><span class="sxs-lookup"><span data-stu-id="36c2d-218">https://www.</span></span> <span data-ttu-id="36c2d-219">MyCompany.com/bar</span><span class="sxs-lookup"><span data-stu-id="36c2d-219">MyCompany.com/bar</span></span>     |
|    <span data-ttu-id="36c2d-220">mailto:</span><span class="sxs-lookup"><span data-stu-id="36c2d-220">mailto:</span></span>    |  <span data-ttu-id="36c2d-221">SMTP</span><span class="sxs-lookup"><span data-stu-id="36c2d-221">SMTP</span></span>   |      mailto:A.User@MyCompany.com       |
|    <span data-ttu-id="36c2d-222">FILE://</span><span class="sxs-lookup"><span data-stu-id="36c2d-222">FILE://</span></span>    |  <span data-ttu-id="36c2d-223">FILE</span><span class="sxs-lookup"><span data-stu-id="36c2d-223">FILE</span></span>   | <span data-ttu-id="36c2d-224">FILE://C:\MyCompany \\%MessageID%.xml</span><span class="sxs-lookup"><span data-stu-id="36c2d-224">FILE://C:\ MyCompany \\%MessageID%.xml</span></span> |

