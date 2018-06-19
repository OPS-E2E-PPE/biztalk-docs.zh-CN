---
title: 为发送适配器交换模式 |Microsoft 文档
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
ms.openlocfilehash: 997aaa9a92f90f30bdaaeb59cc9cecb0c454496f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248349"
---
# <a name="exchange-patterns-for-send-adapters"></a><span data-ttu-id="bc764-102">发送适配器的交换模式</span><span class="sxs-lookup"><span data-stu-id="bc764-102">Exchange Patterns for Send Adapters</span></span>
<span data-ttu-id="bc764-103">发送适配器从 BizTalk 消息引擎通过网络传输来传送消息。</span><span class="sxs-lookup"><span data-stu-id="bc764-103">Send adapters are delivered messages from the BizTalk Messaging Engine to be transmitted over the wire.</span></span> <span data-ttu-id="bc764-104">这些消息可能会发送使用的单向或双向消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="bc764-104">These messages may be sent by using a one-way or two-way message exchange pattern.</span></span> <span data-ttu-id="bc764-105">处理此双向消息交换模式的适配器调用请求-响应适配器。</span><span class="sxs-lookup"><span data-stu-id="bc764-105">An adapter that handles this two-way message exchange pattern is called a Solicit-Response adapter.</span></span>  
  
## <a name="blocking-vs-non-blocking-transmissions"></a><span data-ttu-id="bc764-106">阻止 vs。非阻塞传输</span><span class="sxs-lookup"><span data-stu-id="bc764-106">Blocking vs. Non-Blocking Transmissions</span></span>  
 <span data-ttu-id="bc764-107">The Messaging Engine 将消息传送到发送适配器，通过使用**IBTTransmitter.TransmitMessage**方法或**IBTTransmitterBatch.TransmitMessage**方法，具体取决于是否适配器是批处理感知。</span><span class="sxs-lookup"><span data-stu-id="bc764-107">The Messaging Engine delivers messages to the send adapter by using either the **IBTTransmitter.TransmitMessage** method or the **IBTTransmitterBatch.TransmitMessage** method, depending on whether the adapter is batch-aware.</span></span> <span data-ttu-id="bc764-108">这两个版本的方法具有返回值，该值指示适配器传输消息的方式一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="bc764-108">Both versions of the method have a Boolean return value that indicates how the adapter transmitted the message.</span></span> <span data-ttu-id="bc764-109">如果适配器返回 `true`，则在返回前它已发送完消息。</span><span class="sxs-lookup"><span data-stu-id="bc764-109">If the adapter returns `true`, it has completely sent the message before returning.</span></span> <span data-ttu-id="bc764-110">在这种情况下消息引擎从 MessageBox 数据库代表适配器中删除消息。</span><span class="sxs-lookup"><span data-stu-id="bc764-110">In this case the Messaging Engine deletes the message from the MessageBox database on behalf of the adapter.</span></span> <span data-ttu-id="bc764-111">如果适配器返回 `false`，则适配器已开始传送消息，但是在传送未完成之前就返回了。</span><span class="sxs-lookup"><span data-stu-id="bc764-111">If the adapter returns `false`, it started message transmission and returned before the transmission completed.</span></span> <span data-ttu-id="bc764-112">在这种情况下，不仅对删除来自其应用程序队列的消息也用于处理需要传输重试或挂起的消息的传输失败，则适配器负责。</span><span class="sxs-lookup"><span data-stu-id="bc764-112">In this case, the adapter is responsible not only for deleting the message from its application queue but also for handling transmission failures that require the message to be retried for transmission or suspended.</span></span>  
  
 <span data-ttu-id="bc764-113">返回的适配器`false`非阻止调用，这意味着， **TransmitMessage**实现代码不会阻止调用线程的消息传送引擎。</span><span class="sxs-lookup"><span data-stu-id="bc764-113">The adapter returning `false` is a nonblocking call, meaning that the **TransmitMessage** implementation code does not block the calling thread of the Messaging Engine.</span></span> <span data-ttu-id="bc764-114">适配器只需将消息添加到准备要传输的内存中队列，然后返回。</span><span class="sxs-lookup"><span data-stu-id="bc764-114">The adapter simply adds the message to an in-memory queue ready to be transmitted and then returns.</span></span> <span data-ttu-id="bc764-115">适配器应具有其自己的线程池，为内存中队列提供服务、 传输消息，然后通知传输的结果的引擎。</span><span class="sxs-lookup"><span data-stu-id="bc764-115">The adapter should have its own thread pool that services the in-memory queue, transmits the message, and then notifies the engine of the outcome of the transmission.</span></span>  
  
 <span data-ttu-id="bc764-116">消息传送引擎的线程是通常更多的 CPU 绑定用于通过网络发送数据的线程。</span><span class="sxs-lookup"><span data-stu-id="bc764-116">The Messaging Engine’s threads are typically more CPU bound than the threads used to send data over the wire.</span></span> <span data-ttu-id="bc764-117">混合使用这两种类型的线程对性能有负面影响。</span><span class="sxs-lookup"><span data-stu-id="bc764-117">Mixing these two types of threads has a negative impact on performance.</span></span> <span data-ttu-id="bc764-118">非阻塞发送启用分离线程这两种类型和通过阻止调用产生显著的性能改善。</span><span class="sxs-lookup"><span data-stu-id="bc764-118">Non-blocking sends enable the decoupling of these two types of threads and yield a significant performance improvement over blocking calls.</span></span>  
  
 <span data-ttu-id="bc764-119">下图显示适配器的线程池，其中往往会受 I/O 操作。</span><span class="sxs-lookup"><span data-stu-id="bc764-119">The following diagram shows the adapter's thread pool which can tend to be bound by I/O operations.</span></span> <span data-ttu-id="bc764-120">BizTalk Server 消息传送引擎的线程池是多个受 CPU 处理。</span><span class="sxs-lookup"><span data-stu-id="bc764-120">The BizTalk Server Messaging Engine's thread pool is more bound by the CPU processing.</span></span> <span data-ttu-id="bc764-121">通过使两个不同的线程池并不混用相同的线程类型系统可以更有效地运行。</span><span class="sxs-lookup"><span data-stu-id="bc764-121">By keeping two different thread pools and not mixing the same type of threads the system can operate more efficiently.</span></span>  
  
 ![](../core/media/io-cpu-bound-threadpools.gif "Io_cpu_bound_threadpools")  
  
 <span data-ttu-id="bc764-122">**性能提示：** 以实现最佳性能，将发送适配器都应锁定和感知的批处理。</span><span class="sxs-lookup"><span data-stu-id="bc764-122">**Performance Tip:** For the best performance, send adapters should be nonblocking and batch aware.</span></span> <span data-ttu-id="bc764-123">当 BizTalk 文件适配器已从阻止和非批处理感知更改为非阻止和批处理感知，实现了三倍的性能提升了。</span><span class="sxs-lookup"><span data-stu-id="bc764-123">When the BizTalk File adapter was changed from blocking and non-batch aware to nonblocking and batch aware, a threefold performance gain was realized.</span></span>  
  
 <span data-ttu-id="bc764-124">**故障排除提示：** 阻止传输可能会导致性能降低的整个主机实例。</span><span class="sxs-lookup"><span data-stu-id="bc764-124">**Troubleshooting Tip:** Blocking transmits can cause a performance degradation of an entire host instance.</span></span> <span data-ttu-id="bc764-125">如果适配器执行过多阻塞**TransmitMessage**将阻止引擎线程将消息传送到其他适配器。</span><span class="sxs-lookup"><span data-stu-id="bc764-125">If the adapter does excessive blocking in **TransmitMessage** it will prevent engine threads from delivering messages to other adapters.</span></span>  
  
## <a name="non-batched-sends"></a><span data-ttu-id="bc764-126">非成批发送</span><span class="sxs-lookup"><span data-stu-id="bc764-126">Non-Batched Sends</span></span>  
 <span data-ttu-id="bc764-127">不感知的批处理的适配器应实现**IBTTransmitter**详见[异步发送适配器的接口](../core/interfaces-for-an-asynchronous-send-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="bc764-127">Adapters that are not batch aware should implement **IBTTransmitter** as detailed in [Interfaces for an Asynchronous Send Adapter](../core/interfaces-for-an-asynchronous-send-adapter.md).</span></span> <span data-ttu-id="bc764-128">为每条消息，该适配器需要传输 the Messaging Engine 调用**IBTTransmitter.TransmitMessage**。</span><span class="sxs-lookup"><span data-stu-id="bc764-128">For each message that the adapter needs to transmit the Messaging Engine calls **IBTTransmitter.TransmitMessage**.</span></span> <span data-ttu-id="bc764-129">以下对象交互示意图详细说明的典型方法以传输消息，其中包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="bc764-129">The object interaction diagram below details the typical approach for transmitting messages, which consists of the following steps:</span></span>  
  
1.  <span data-ttu-id="bc764-130">引擎将该消息传送到适配器。</span><span class="sxs-lookup"><span data-stu-id="bc764-130">The engine delivers the message to the adapter.</span></span>  
  
2.  <span data-ttu-id="bc764-131">适配器将排到内存中队列准备要传输的消息。</span><span class="sxs-lookup"><span data-stu-id="bc764-131">The adapter enqueues the message to an in-memory queue ready to be transmitted.</span></span>  
  
3.  <span data-ttu-id="bc764-132">适配器的线程池中的线程中取消排队的消息从队列中读取消息，配置，并通过网络传输消息。</span><span class="sxs-lookup"><span data-stu-id="bc764-132">A thread from the adapter's thread pool dequeues the message from the queue, reads the configuration for the message, and transmits the message over the wire.</span></span>  
  
4.  <span data-ttu-id="bc764-133">适配器从引擎中获取新批。</span><span class="sxs-lookup"><span data-stu-id="bc764-133">The adapter gets a new batch from the engine.</span></span>  
  
5.  <span data-ttu-id="bc764-134">适配器调用**DeleteMessage**批次，它只是已传输的消息中传递。</span><span class="sxs-lookup"><span data-stu-id="bc764-134">The adapter calls **DeleteMessage** on the batch, passing in the message that it has just transmitted.</span></span>  
  
6.  <span data-ttu-id="bc764-135">适配器调用**完成**批次。</span><span class="sxs-lookup"><span data-stu-id="bc764-135">The adapter calls **Done** on the batch.</span></span>  
  
7.  <span data-ttu-id="bc764-136">引擎处理批处理，并从应用程序队列中删除消息。</span><span class="sxs-lookup"><span data-stu-id="bc764-136">The engine processes the batch and deletes the message from the application queue.</span></span>  
  
8.  <span data-ttu-id="bc764-137">引擎回调通知它的结果的适配器**DeleteMessage**操作。</span><span class="sxs-lookup"><span data-stu-id="bc764-137">The engine calls back the adapter to notify it of the outcome of the **DeleteMessage** operation.</span></span>  
  
 ![](../core/media/deleting-from-message-queue.gif "Deleting_from_message_queue")  
  
 <span data-ttu-id="bc764-138">前面的对象交互图显示从应用程序队列中删除一条消息的适配器。</span><span class="sxs-lookup"><span data-stu-id="bc764-138">The preceding object interaction diagram shows the adapter deleting a single message from the application queue.</span></span> <span data-ttu-id="bc764-139">理想情况下适配器的批次而不是一次运行上一条消息的消息操作。</span><span class="sxs-lookup"><span data-stu-id="bc764-139">Ideally the adapter batches up message operations as opposed to operating on a single message at a time.</span></span>  
  
## <a name="batched-sends"></a><span data-ttu-id="bc764-140">成批的发送</span><span class="sxs-lookup"><span data-stu-id="bc764-140">Batched Sends</span></span>  
 <span data-ttu-id="bc764-141">批处理感知适配器应实现**IBTBatchTransmitter**和**IBTTransmitterBatch**详见[发送适配器的接口](../core/interfaces-for-send-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="bc764-141">Adapters that are batch aware should implement **IBTBatchTransmitter** and **IBTTransmitterBatch** as detailed in [Interfaces for Send Adapters](../core/interfaces-for-send-adapters.md).</span></span> <span data-ttu-id="bc764-142">当引擎具有的适配器以传输消息时，引擎将获取一批新的适配器通过调用**IBTBatchTransmitter.GetBatch**。</span><span class="sxs-lookup"><span data-stu-id="bc764-142">When the engine has messages for the adapter to transmit, the engine gets a new batch from the adapter by calling **IBTBatchTransmitter.GetBatch**.</span></span> <span data-ttu-id="bc764-143">适配器返回一个新的 batch 对象实现**IBTTransmitterBatch**。</span><span class="sxs-lookup"><span data-stu-id="bc764-143">The adapter returns a new batch object that implements **IBTTransmitterBatch**.</span></span> <span data-ttu-id="bc764-144">引擎然后通过调用启动批处理**IBTTransmitterBatch.BeginBatch**。</span><span class="sxs-lookup"><span data-stu-id="bc764-144">The engine then starts the batch by calling **IBTTransmitterBatch.BeginBatch**.</span></span> <span data-ttu-id="bc764-145">此 API 具有输出参数，它将接受的消息的最大数指定批次的适配器。</span><span class="sxs-lookup"><span data-stu-id="bc764-145">This API has an out parameter that allows the adapter to specify the maximum number of messages that it will accept on the batch.</span></span> <span data-ttu-id="bc764-146">适配器 （可选） 可能会返回一个 DTC 事务。</span><span class="sxs-lookup"><span data-stu-id="bc764-146">The adapter may optionally return a DTC transaction.</span></span> <span data-ttu-id="bc764-147">则引擎会调用**IBTTransmitterBatch.TransmitMessage**一次针对每个传出消息添加到批处理。</span><span class="sxs-lookup"><span data-stu-id="bc764-147">The engine then calls **IBTTransmitterBatch.TransmitMessage** once for each outgoing message to be added to the batch.</span></span> <span data-ttu-id="bc764-148">这称为次数是大于零，但小于或等于到适配器所述的批处理的最大大小。</span><span class="sxs-lookup"><span data-stu-id="bc764-148">The number of times this is called is greater than zero but less than or equal to the maximum size of the batch as indicated by the adapter.</span></span> <span data-ttu-id="bc764-149">在所有消息都添加到批处理后，调用该适配器**IBTTransmitterBatch.Done**。</span><span class="sxs-lookup"><span data-stu-id="bc764-149">When all the messages have been added to the batch, the adapter calls **IBTTransmitterBatch.Done**.</span></span> <span data-ttu-id="bc764-150">此时的适配器通常将排到内存中队列批处理中的所有消息。</span><span class="sxs-lookup"><span data-stu-id="bc764-150">At this point the adapter typically enqueues all the messages in the batch to its in-memory queue.</span></span> <span data-ttu-id="bc764-151">适配器传输的消息从一个线程或在非批处理感知适配器如同其自己线程池中的线程。</span><span class="sxs-lookup"><span data-stu-id="bc764-151">The adapter transmits the messages from a thread or threads in its own thread pool as in the case of non-batch-aware adapters.</span></span> <span data-ttu-id="bc764-152">适配器然后通知传输的结果的引擎。</span><span class="sxs-lookup"><span data-stu-id="bc764-152">The adapter then notifies the engine of the outcome of the transmission.</span></span>  
  
 <span data-ttu-id="bc764-153">以下对象交互图说明了两条消息由成批的发送适配器传输。</span><span class="sxs-lookup"><span data-stu-id="bc764-153">The following object interaction diagram illustrates the transmission of two messages by a batched send adapter.</span></span>  
  
 ![](../core/media/batchedsends.gif "BatchedSends")  
  
## <a name="handling-transmission-failures"></a><span data-ttu-id="bc764-154">处理传输故障</span><span class="sxs-lookup"><span data-stu-id="bc764-154">Handling Transmission Failures</span></span>  
 <span data-ttu-id="bc764-155">在下图说明了传输失败的建议的语义。</span><span class="sxs-lookup"><span data-stu-id="bc764-155">The recommended semantics for transmission failures are illustrated in the figure below.</span></span> <span data-ttu-id="bc764-156">这些是仅为建议，不会强制执行消息传送引擎。</span><span class="sxs-lookup"><span data-stu-id="bc764-156">These are only recommendations and are not enforced by the Messaging Engine.</span></span> <span data-ttu-id="bc764-157">你可以开发偏离这些准则，如果有这样的有效原因，但你应注意这种情况下的适配器。</span><span class="sxs-lookup"><span data-stu-id="bc764-157">You can develop an adapter that deviates from these guidelines if there are valid reasons for doing so but you should be careful in this case.</span></span> <span data-ttu-id="bc764-158">例如，一般情况下适配器应始终将消息移到备份传输耗尽所有重试后。</span><span class="sxs-lookup"><span data-stu-id="bc764-158">For example, in general an adapter should always move messages to the backup transport after all retries have been exhausted.</span></span>  
  
 <span data-ttu-id="bc764-159">更常见传输可能需要使用比配置的多个重试。</span><span class="sxs-lookup"><span data-stu-id="bc764-159">More commonly a transport may need to use more retries than are configured.</span></span> <span data-ttu-id="bc764-160">虽然这是略有不同帐户被视为可接受，因为已增加的传输层的灵活性。</span><span class="sxs-lookup"><span data-stu-id="bc764-160">While this is slightly different it is considered acceptable because the resilience of the transport layer is being increased.</span></span> <span data-ttu-id="bc764-161">一般情况下由 the Messaging Engine 公开的 Api 旨在尽可能让适配器能够最大控制。</span><span class="sxs-lookup"><span data-stu-id="bc764-161">In general the APIs exposed by the Messaging Engine are designed to give the adapter maximum control where possible.</span></span> <span data-ttu-id="bc764-162">伴随此控件的更大程度的责任。</span><span class="sxs-lookup"><span data-stu-id="bc764-162">With this control comes a greater level of responsibility.</span></span>  
  
 ![](../core/media/handlingerrors.gif "HandlingErrors")  
  
 <span data-ttu-id="bc764-163">适配器通过检查系统上下文属性确定可在上找到一条消息的重试次数**RetryCount**。</span><span class="sxs-lookup"><span data-stu-id="bc764-163">The adapter determines the number of retries available on a message by checking the system context property **RetryCount**.</span></span> <span data-ttu-id="bc764-164">适配器调用**重新提交**API 一次每个重试尝试，并传入要重新提交的消息。</span><span class="sxs-lookup"><span data-stu-id="bc764-164">The adapter calls the **Resubmit** API once for each retry attempt and passes in the message to be resubmitted.</span></span> <span data-ttu-id="bc764-165">与消息一起传递用于指示当引擎应将消息传递回适配器时的时间戳。</span><span class="sxs-lookup"><span data-stu-id="bc764-165">Along with the message it passes the time stamp indicating when the engine should deliver the message back to the adapter.</span></span> <span data-ttu-id="bc764-166">此值通常应当前时间加上的值**RetryInterval**。</span><span class="sxs-lookup"><span data-stu-id="bc764-166">This value should typically be the current time plus the value of **RetryInterval**.</span></span> <span data-ttu-id="bc764-167">**RetryInterval**是系统的上下文属性的单位为分钟。</span><span class="sxs-lookup"><span data-stu-id="bc764-167">**RetryInterval** is a system context property whose units are minutes.</span></span> <span data-ttu-id="bc764-168">这两个**RetryCount**和**RetryInterval**消息上下文中是在发送端口配置的值。</span><span class="sxs-lookup"><span data-stu-id="bc764-168">Both the **RetryCount** and **RetryInterval** in the message context are the values that are configured on the send port.</span></span> <span data-ttu-id="bc764-169">请考虑具有的相同的多台计算机上部署 BizTalk 主机实例的向外扩展的部署。</span><span class="sxs-lookup"><span data-stu-id="bc764-169">Consider a scaled-out deployment with instances of the same BizTalk Host deployed on multiple computers.</span></span> <span data-ttu-id="bc764-170">如果消息传送后重试间隔已过期，则可能对任何其中它们配置为运行的计算机上的主机实例的任一传递消息。</span><span class="sxs-lookup"><span data-stu-id="bc764-170">If the message is delivered after the retry interval has expired, the message may be delivered to the any one of the host instances on any of the computers where they are configured to run.</span></span> <span data-ttu-id="bc764-171">为此适配器应保持与消息重试后使用关联的任何状态尝试由于并不保证同一实例的适配器将负责在更高版本时传输。</span><span class="sxs-lookup"><span data-stu-id="bc764-171">For this reason the adapter should not hold any state associated with a message to be used on the retry attempt because there is no guarantee that same instance of the adapter will be responsible for the transmission at a later time.</span></span>  
  
 <span data-ttu-id="bc764-172">适配器应仅尝试将消息移到备份传输后重试计数小于或等于零。</span><span class="sxs-lookup"><span data-stu-id="bc764-172">The adapter should only attempt to move the message to the backup transport after the retry count is less than or equal to zero.</span></span> <span data-ttu-id="bc764-173">如果没有备份传输的端口配置，以便将消息移到备份传输尝试将失败。</span><span class="sxs-lookup"><span data-stu-id="bc764-173">An attempt to move the message to the backup transport will fail if there is no backup transport configured for the port.</span></span> <span data-ttu-id="bc764-174">在这种情况下应挂起消息。</span><span class="sxs-lookup"><span data-stu-id="bc764-174">In this case the message should be suspended.</span></span>  
  
 <span data-ttu-id="bc764-175">下面的代码段演示如何确定重试计数和从消息上下文中和后续的重新提交间隔或将移动到备份传输。</span><span class="sxs-lookup"><span data-stu-id="bc764-175">The following code fragment illustrates how to determine the retry count and interval from the message context, and the subsequent resubmit or move to the backup transport.</span></span>  
  
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
  
## <a name="throwing-an-exception-from-transmitmessage"></a><span data-ttu-id="bc764-176">从 TransmitMessage 引发异常</span><span class="sxs-lookup"><span data-stu-id="bc764-176">Throwing an Exception from TransmitMessage</span></span>  
 <span data-ttu-id="bc764-177">在适配器上的任何 Api 引发的异常**IBTTransmitter.TransmitMessage**， **IBTTransmitterBatch.TransmitMessage**， **IBTTransmitterBatch.Done**，引擎将涉及的消息传输视为传输失败，并执行适当的操作对于消息，如所述[如何处理适配器故障影响](../core/how-to-handle-adapter-failures.md)。</span><span class="sxs-lookup"><span data-stu-id="bc764-177">If the adapter throws an exception on any of the APIs **IBTTransmitter.TransmitMessage**, **IBTTransmitterBatch.TransmitMessage**, **IBTTransmitterBatch.Done**, the engine treats the transmission of the messages involved as transmission failures and takes the appropriate action for the message, as detailed in [How to Handle Adapter Failures](../core/how-to-handle-adapter-failures.md).</span></span>  
  
 <span data-ttu-id="bc764-178">批处理感知发送适配器引发 TransmitMessage api 异常会导致整个批处理正在清除和默认传输失败操作正在执行该批处理中的所有消息。</span><span class="sxs-lookup"><span data-stu-id="bc764-178">For batch-aware send adapters, throwing an exception on the TransmitMessage API results in the entire batch being cleared and the default transmit failure actions being performed for all messages in that batch.</span></span>  
  
## <a name="solicit-response"></a><span data-ttu-id="bc764-179">要求-响应</span><span class="sxs-lookup"><span data-stu-id="bc764-179">Solicit-Response</span></span>  
 <span data-ttu-id="bc764-180">双向发送适配器通常支持单向和双向传输。</span><span class="sxs-lookup"><span data-stu-id="bc764-180">Two-way send adapters typically support both one-way and two-way transmissions.</span></span> <span data-ttu-id="bc764-181">发送适配器确定是否应通过检查传输为单向或双向发送消息**IsSolicitResponse**消息上下文中的系统上下文属性。</span><span class="sxs-lookup"><span data-stu-id="bc764-181">The send adapter determines whether the message should be transmitted as a one-way or two-way send by inspecting the **IsSolicitResponse** system context property in the message context.</span></span>  
  
 <span data-ttu-id="bc764-182">以下代码段演示了这一操作：</span><span class="sxs-lookup"><span data-stu-id="bc764-182">The following code fragment demonstrates this:</span></span>  
  
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
  
 <span data-ttu-id="bc764-183">在请求-响应传输过程中适配器传输请求消息。</span><span class="sxs-lookup"><span data-stu-id="bc764-183">During a solicit-response transmission the adapter transmits the solicit message.</span></span> <span data-ttu-id="bc764-184">此完成之后它提交了关联的响应，告知要从 MessageBox 数据库中删除原始请求消息的消息传送引擎。</span><span class="sxs-lookup"><span data-stu-id="bc764-184">After this completed it submits the associated response and tells the Messaging Engine to delete the original solicit message from the MessageBox database.</span></span> <span data-ttu-id="bc764-185">应为响应消息的提交相同的传输代理批处理中执行的应用程序队列中删除消息的操作。</span><span class="sxs-lookup"><span data-stu-id="bc764-185">The action of deleting the message from the application queue should be performed in the same transport proxy batch as the submission of the response message.</span></span> <span data-ttu-id="bc764-186">这可确保原子性的删除和提交的响应。</span><span class="sxs-lookup"><span data-stu-id="bc764-186">This ensures atomicity of the deletion and submission of the response.</span></span> <span data-ttu-id="bc764-187">对于完整的原子性适配器应使用一个 DTC 事务，由此识别事务的资源，响应消息中，提交该请求消息的传输和删除请求消息都在同一个 DTC 的上下文事务。</span><span class="sxs-lookup"><span data-stu-id="bc764-187">For complete atomicity the adapter should use a DTC transaction whereby the transmission of the solicit message to a transaction-aware resource, submission of the response message, and deletion of the solicit message are all in the context of the same DTC transaction.</span></span> <span data-ttu-id="bc764-188">与往常一样，我们建议使用非阻止发送传输请求消息。</span><span class="sxs-lookup"><span data-stu-id="bc764-188">As always, we recommend that the solicit message is transmitted using a non-blocking send.</span></span>  
  
 <span data-ttu-id="bc764-189">下面的代码段演示了双向发送的主要方面。</span><span class="sxs-lookup"><span data-stu-id="bc764-189">The following code fragment illustrates the main aspects of a two-way send.</span></span> <span data-ttu-id="bc764-190">在引擎调用**IBTTransmitter.TransmitMessage**适配器将排要将传输到内存中队列的消息。</span><span class="sxs-lookup"><span data-stu-id="bc764-190">When the engine calls **IBTTransmitter.TransmitMessage** the adapter enqueues the message to be transmitted to an in-memory queue.</span></span> <span data-ttu-id="bc764-191">适配器返回 `false`，指示它在执行非阻塞发送。</span><span class="sxs-lookup"><span data-stu-id="bc764-191">The adapter returns `false` to indicate that it is performing a non-blocking send.</span></span> <span data-ttu-id="bc764-192">适配器的线程池 (**WorkerThreadThunk**) 为内存中队列提供服务和一条消息，将其提交给一个帮助器方法中取消排队。</span><span class="sxs-lookup"><span data-stu-id="bc764-192">The adapter's thread pool (**WorkerThreadThunk**) services the in-memory queue and dequeues a message to hand it off to a helper method.</span></span> <span data-ttu-id="bc764-193">此方法负责发送请求消息和接收响应消息。</span><span class="sxs-lookup"><span data-stu-id="bc764-193">This method is responsible for sending the solicit message and receiving the response message.</span></span> <span data-ttu-id="bc764-194">（此帮助器方法的实现不在本主题的范围。）响应消息提交到引擎，并从应用程序队列中删除请求消息。</span><span class="sxs-lookup"><span data-stu-id="bc764-194">(The implementation of this helper method is outside the scope of this topic.) The response message is submitted into the engine, and the solicit message is deleted from the application queue.</span></span>  
  
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
  
## <a name="dynamic-sends"></a><span data-ttu-id="bc764-195">动态发送</span><span class="sxs-lookup"><span data-stu-id="bc764-195">Dynamic Sends</span></span>  
 <span data-ttu-id="bc764-196">动态发送端口没有与之关联的适配器配置。</span><span class="sxs-lookup"><span data-stu-id="bc764-196">Dynamic send ports do not have adapter configuration associated with them.</span></span> <span data-ttu-id="bc764-197">它们改用处理程序配置任何适配器需要将动态端口上的消息传输的默认属性。</span><span class="sxs-lookup"><span data-stu-id="bc764-197">Instead they use handler configuration for any default properties that the adapter needs to transmit messages on a dynamic port.</span></span> <span data-ttu-id="bc764-198">例如，HTTP 适配器可能需要使用代理，需要提供凭据。</span><span class="sxs-lookup"><span data-stu-id="bc764-198">For example, an HTTP adapter may need to use a proxy and need to provide credentials.</span></span> <span data-ttu-id="bc764-199">用户名、 密码和端口可指定的处理程序配置适配器缓存在运行时。</span><span class="sxs-lookup"><span data-stu-id="bc764-199">The user name, password, and port could be specified in the handler configuration that the adapter caches at run time.</span></span>  
  
 <span data-ttu-id="bc764-200">要确定动态消息是通过，发送的传输的引擎**OutboundTransportLocation**前缀为适配器的别名。</span><span class="sxs-lookup"><span data-stu-id="bc764-200">For the engine to determine the transport that a dynamic message is to be sent over, the **OutboundTransportLocation** is prefixed with the adapter's alias.</span></span> <span data-ttu-id="bc764-201">在安装时，适配器可在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中注册一个或多个别名。</span><span class="sxs-lookup"><span data-stu-id="bc764-201">An adapter can register one or more aliases with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] at install time.</span></span> <span data-ttu-id="bc764-202">引擎分析**OutboundTransportLocation**在运行时查找匹配项。</span><span class="sxs-lookup"><span data-stu-id="bc764-202">The engine parses the **OutboundTransportLocation** at run time to find a match.</span></span> <span data-ttu-id="bc764-203">适配器负责处理**OutboundTransportLocation**无论其前面预置的别名。</span><span class="sxs-lookup"><span data-stu-id="bc764-203">The adapter is responsible for handling the **OutboundTransportLocation** with or without the alias prepended to it.</span></span> <span data-ttu-id="bc764-204">下表显示别名的现成可用 BizTalk 适配器已注册的一些示例。</span><span class="sxs-lookup"><span data-stu-id="bc764-204">The following table shows some examples of aliases registered for out-of-the-box BizTalk adapters.</span></span>  
  
|<span data-ttu-id="bc764-205">适配器别名</span><span class="sxs-lookup"><span data-stu-id="bc764-205">Adapter alias</span></span>|<span data-ttu-id="bc764-206">适配器</span><span class="sxs-lookup"><span data-stu-id="bc764-206">Adapter</span></span>|<span data-ttu-id="bc764-207">OutboundTransportLocation 示例</span><span class="sxs-lookup"><span data-stu-id="bc764-207">OutboundTransportLocation example</span></span>|  
|-------------------|-------------|---------------------------------------|  
|<span data-ttu-id="bc764-208">HTTP://</span><span class="sxs-lookup"><span data-stu-id="bc764-208">HTTP://</span></span>|<span data-ttu-id="bc764-209">HTTP</span><span class="sxs-lookup"><span data-stu-id="bc764-209">HTTP</span></span>|<span data-ttu-id="bc764-210">http://www。</span><span class="sxs-lookup"><span data-stu-id="bc764-210">http://www.</span></span> <span data-ttu-id="bc764-211">MyCompany.com/bar</span><span class="sxs-lookup"><span data-stu-id="bc764-211">MyCompany.com/bar</span></span>|  
|<span data-ttu-id="bc764-212">HTTPS://</span><span class="sxs-lookup"><span data-stu-id="bc764-212">HTTPS://</span></span>|<span data-ttu-id="bc764-213">HTTP</span><span class="sxs-lookup"><span data-stu-id="bc764-213">HTTP</span></span>|<span data-ttu-id="bc764-214">https://www。</span><span class="sxs-lookup"><span data-stu-id="bc764-214">https://www.</span></span> <span data-ttu-id="bc764-215">MyCompany.com/bar</span><span class="sxs-lookup"><span data-stu-id="bc764-215">MyCompany.com/bar</span></span>|  
|<span data-ttu-id="bc764-216">mailto:</span><span class="sxs-lookup"><span data-stu-id="bc764-216">mailto:</span></span>|<span data-ttu-id="bc764-217">SMTP</span><span class="sxs-lookup"><span data-stu-id="bc764-217">SMTP</span></span>|mailto:A.User@MyCompany.com|  
|<span data-ttu-id="bc764-218">FILE://</span><span class="sxs-lookup"><span data-stu-id="bc764-218">FILE://</span></span>|<span data-ttu-id="bc764-219">FILE</span><span class="sxs-lookup"><span data-stu-id="bc764-219">FILE</span></span>|<span data-ttu-id="bc764-220">FILE://C:\MyCompany \\%MessageID%.xml</span><span class="sxs-lookup"><span data-stu-id="bc764-220">FILE://C:\ MyCompany \\%MessageID%.xml</span></span>|