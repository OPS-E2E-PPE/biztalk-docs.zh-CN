---
title: 有序的消息传送 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, message order
- file transport, message order
- Messaging Engine, transports
- messages, performance
- dynamic send ports, message order
- BTS.SuspendAsNonResumable message context property
- performance, message order
- Messaging Engine, performance
- Messaging Engine, message order
- MessageBox database, message order
- messages, sorting
- backing up, backup transports
- adapters, custom receive adapters
- adapters, messages
- customizing, receive adapters
ms.assetid: 39e0bba6-81f5-4ae0-af92-837b225bc801
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abfb0b78065d4eb3aee022d141cc833399fc1496
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22266605"
---
# <a name="ordered-delivery-of-messages"></a><span data-ttu-id="7412d-102">有序的消息传送</span><span class="sxs-lookup"><span data-stu-id="7412d-102">Ordered Delivery of Messages</span></span>
<span data-ttu-id="7412d-103">按序送达消息可以确保按给定顺序发布到 MessageBox 数据库的消息能够以发布到 MessageBox 的相同顺序送达每个匹配的订户。</span><span class="sxs-lookup"><span data-stu-id="7412d-103">Ordered message delivery ensures that messages that are published to the MessageBox database in a given order are delivered to each matching subscriber in the same order in which they were published to the message box.</span></span>  
  
## <a name="configuring-ordered-message-delivery"></a><span data-ttu-id="7412d-104">配置按序消息送达</span><span class="sxs-lookup"><span data-stu-id="7412d-104">Configuring Ordered Message Delivery</span></span>  
 <span data-ttu-id="7412d-105">可以在以下位置配置按序消息送达：</span><span class="sxs-lookup"><span data-stu-id="7412d-105">Ordered message delivery can be configured in the following places:</span></span>  
  
-   <span data-ttu-id="7412d-106">**接收**形状中业务流程</span><span class="sxs-lookup"><span data-stu-id="7412d-106">**Receive** shape in an orchestration</span></span>  
  
-   <span data-ttu-id="7412d-107">发送端口</span><span class="sxs-lookup"><span data-stu-id="7412d-107">Send port</span></span>  
  
## <a name="ordered-delivery-with-existing-transports"></a><span data-ttu-id="7412d-108">使用现有传输实现按序送达</span><span class="sxs-lookup"><span data-stu-id="7412d-108">Ordered Delivery with Existing Transports</span></span>  
 <span data-ttu-id="7412d-109">某些传输的基础协议（例如，FILE 和 HTTP）与按序送达的概念不一致。</span><span class="sxs-lookup"><span data-stu-id="7412d-109">The protocols underlying certain transports, such as FILE and HTTP, are not consistent with the notion of ordered delivery.</span></span> <span data-ttu-id="7412d-110">但是，即使对于此类传输，如果将绑定到传输的端口标记为按序送达，BizTalk Server 也会通过确保在当前消息成功发送之后再获取下一个出站消息来强制实现按序送达。</span><span class="sxs-lookup"><span data-stu-id="7412d-110">However, even with such transports, if the port bound to the transport is marked for ordered delivery, then BizTalk Server enforces ordered delivery by ensuring that the transport does not get the next outbound message until the current one has been successfully sent.</span></span> <span data-ttu-id="7412d-111">若要达到此目的，BizTalk Server 会将每个消息放在单个批中传递给传输的适配器，并等到适配器已从 MessageBox 中成功删除消息之后，再通过另一个批将下一条消息传递给适配器。</span><span class="sxs-lookup"><span data-stu-id="7412d-111">To achieve this, BizTalk Server passes each message to the transport's adapter in a single batch and waits until the adapter has successfully deleted the message from the message box before delivering the next message, in another batch, to the adapter.</span></span>  
  
### <a name="ordered-delivery-for-custom-adapters"></a><span data-ttu-id="7412d-112">自定义适配器的按序送达</span><span class="sxs-lookup"><span data-stu-id="7412d-112">Ordered Delivery for Custom Adapters</span></span>  
 <span data-ttu-id="7412d-113">对于自定义接收适配器，有一些特殊注意事项。</span><span class="sxs-lookup"><span data-stu-id="7412d-113">There are special considerations for custom receive adapters.</span></span> <span data-ttu-id="7412d-114">如果你正在编写支持在接收时按序送达的自定义适配器，则该适配器应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7412d-114">It you are writing a custom adapter that supports ordered delivery on receive, the adapter should do the following:</span></span>  
  
-   <span data-ttu-id="7412d-115">提交一批消息之后, 你自定义接收适配器应等待**BatchComplete**提交下一批之前从 BizTalk Server 回调。</span><span class="sxs-lookup"><span data-stu-id="7412d-115">After submitting a batch of messages, your custom receive adapter should wait for the **BatchComplete** callback from BizTalk Server before submitting the next batch.</span></span> <span data-ttu-id="7412d-116">有关更多详细信息，请参阅[Batch-Supported 接收适配器接口](../core/interfaces-for-a-batch-supported-receive-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="7412d-116">For more details, see [Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md).</span></span>  
  
-   <span data-ttu-id="7412d-117">如果消息在管道中失败，则应挂起该消息，最好作为不可恢复的消息。</span><span class="sxs-lookup"><span data-stu-id="7412d-117">If a message fails in the pipeline, it should be suspended, preferably as nonresumable.</span></span> <span data-ttu-id="7412d-118">使用**BTS。SuspendAsNonResumable**消息中的上下文属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]相应地标记消息。</span><span class="sxs-lookup"><span data-stu-id="7412d-118">Use the **BTS.SuspendAsNonResumable** message context property in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to flag the message appropriately.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7412d-119">如果随后恢复了挂起的消息，则可能会打乱消息顺序。</span><span class="sxs-lookup"><span data-stu-id="7412d-119">Message order can be broken if a suspended message is later resumed.</span></span> <span data-ttu-id="7412d-120">如果不想出现此行为，请将失败消息作为不可恢复消息挂起。</span><span class="sxs-lookup"><span data-stu-id="7412d-120">If you do not want this behavior, suspend failed messages as nonresumable.</span></span>  
  
 <span data-ttu-id="7412d-121">生成自定义适配器的更多详细信息，请参阅[开发自定义适配器](../core/developing-custom-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="7412d-121">For more details on building a custom adapter, see [Developing Custom Adapters](../core/developing-custom-adapters.md).</span></span>  
  
## <a name="conditions-for-end-to-end-ordered-message-processing"></a><span data-ttu-id="7412d-122">端到端按序消息处理的条件</span><span class="sxs-lookup"><span data-stu-id="7412d-122">Conditions for End-to-End Ordered Message Processing</span></span>  
 <span data-ttu-id="7412d-123">为提供端对端的按序送达功能，必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="7412d-123">To provide end-to-end ordered delivery the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="7412d-124">接收消息的适配器必须保持消息提交给 BizTalk Server 时的顺序。</span><span class="sxs-lookup"><span data-stu-id="7412d-124">Messages must be received with an adapter that preserves the order of the messages when submitting them to BizTalk Server.</span></span> <span data-ttu-id="7412d-125">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，这样的适配器的示例包括 MSMQ 和 MQSeries。</span><span class="sxs-lookup"><span data-stu-id="7412d-125">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], examples of such adapters are MSMQ and MQSeries.</span></span> <span data-ttu-id="7412d-126">此外，HTTP 或 SOAP 适配器也可以用来按序提交消息，但在该情况下，HTTP 或 SOAP 客户端需要通过每次提交一条消息来强制实现顺序提交。</span><span class="sxs-lookup"><span data-stu-id="7412d-126">In addition, HTTP or SOAP adapters can be used to submit messages in order, but in that case the HTTP or SOAP client needs to enforce the order by submitting messages one at a time.</span></span>  
  
-   <span data-ttu-id="7412d-127">您必须订阅拥有的发送端口与这些消息**按序送达**选项设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="7412d-127">You must subscribe to these messages with a send port that has the **Ordered Delivery** option set to `True`.</span></span>  
  
-   <span data-ttu-id="7412d-128">如果业务流程用于的处理应使用的消息，仅业务流程的单个实例，应将业务流程配置为使用顺序保护和**按序送达**属性业务流程的接收端口应设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="7412d-128">If an orchestration is used to process the messages, only a single instance of the orchestration should be used, the orchestration should be configured to use a sequential convoy, and the **Ordered Delivery** property of the orchestration's receive port should be set to `True`.</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="7412d-129">限制</span><span class="sxs-lookup"><span data-stu-id="7412d-129">Restrictions</span></span>  
 <span data-ttu-id="7412d-130">在以下情况下不支持按序送达消息：</span><span class="sxs-lookup"><span data-stu-id="7412d-130">Ordered delivery of messages is not supported for the following:</span></span>  
  
-   <span data-ttu-id="7412d-131">动态发送端口中[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]和早期版本</span><span class="sxs-lookup"><span data-stu-id="7412d-131">Dynamic send ports in [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] and previous versions</span></span>

- <span data-ttu-id="7412d-132">动态发送端口中[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]（和任何更高版本） 的这些适配器类型**不**有序传送静态发送端口上的支持</span><span class="sxs-lookup"><span data-stu-id="7412d-132">Dynamic send ports in [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] (and any newer versions) for those adapter types that **don't** support ordered delivery on static send ports</span></span>
  
-   <span data-ttu-id="7412d-133">备份传输</span><span class="sxs-lookup"><span data-stu-id="7412d-133">Backup transports</span></span>  

  
## <a name="interactions"></a><span data-ttu-id="7412d-134">交互</span><span class="sxs-lookup"><span data-stu-id="7412d-134">Interactions</span></span>  
 <span data-ttu-id="7412d-135">为发送端口配置按序送达后，应注意以下与 BizTalk Server 中的其他配置行为的交互：</span><span class="sxs-lookup"><span data-stu-id="7412d-135">When ordered delivery is configured for a send port, be aware of the following interactions with other configured behaviors in BizTalk Server:</span></span>  
  
-   <span data-ttu-id="7412d-136">对于同一发送端口上的“当前消息失败后停止发送随后的消息”设置：</span><span class="sxs-lookup"><span data-stu-id="7412d-136">For the "Stop sending subsequent messages on current message failure" setting on the same send port:</span></span>  
  
    -   <span data-ttu-id="7412d-137">**如果为 false。**</span><span class="sxs-lookup"><span data-stu-id="7412d-137">**False.**</span></span> <span data-ttu-id="7412d-138">仅挂起失败消息（不可恢复），将继续处理随后的所有消息。</span><span class="sxs-lookup"><span data-stu-id="7412d-138">Only the failed message is suspended (as not resumable) and all subsequent messages continue to be processed.</span></span> <span data-ttu-id="7412d-139">这样可以保留未失败消息的顺序，但在序列中会存在中断的情况。</span><span class="sxs-lookup"><span data-stu-id="7412d-139">This preserves the ordering of the non-failed messages but can result in gaps in the sequence.</span></span> <span data-ttu-id="7412d-140">例如，如果收到订单 101、102 和 103，并且订单 102 被挂起，则订单 101 和 103 将继续按序处理。</span><span class="sxs-lookup"><span data-stu-id="7412d-140">For example, if orders 101, 102, and 103 are received and order 102 is suspended, orders 101 and 103 will continue to be processed in order.</span></span>  
  
    -   <span data-ttu-id="7412d-141">**为 true。**</span><span class="sxs-lookup"><span data-stu-id="7412d-141">**True.**</span></span> <span data-ttu-id="7412d-142">如果对任何消息的处理失败，都将挂起发送端口实例。</span><span class="sxs-lookup"><span data-stu-id="7412d-142">The send port instance is suspended if any of the messages fails processing.</span></span> <span data-ttu-id="7412d-143">这会导致按序排列的消息集中随后的所有消息都被挂起。</span><span class="sxs-lookup"><span data-stu-id="7412d-143">This causes all subsequent messages in the ordered set of messages to be suspended.</span></span> <span data-ttu-id="7412d-144">通过防止在送达失败消息之前送达随后的消息，这样可以保留消息顺序。</span><span class="sxs-lookup"><span data-stu-id="7412d-144">This preserves message order by preventing delivery of subsequent messages before delivery of the failed message.</span></span>  
  
-   <span data-ttu-id="7412d-145">如果要求响应发送端口的“当前消息失败后停止发送随后的消息”属性设置为 `true`，并且为响应的接收管道的拆装阶段配置了可恢复的交换处理，那么，如果在拆装响应的过程中存在可恢复的错误，则发送端口不会停止发送消息（即实例不会挂起）。</span><span class="sxs-lookup"><span data-stu-id="7412d-145">If a solicit-response send port has the "Stop sending subsequent messages on current message failure" property set to `true`, and if recoverable interchange processing is configured for the disassembly stage of the receive pipeline for the response, then the send port does not stop sending messages (that is, the instance is not suspended) if there is a recoverable error in disassembling the response.</span></span>  
  
-   <span data-ttu-id="7412d-146">在删除按序发送端口之前，请确保没有与其关联的实例。</span><span class="sxs-lookup"><span data-stu-id="7412d-146">Before deleting an ordered send port, ensure that there are no instances associated with it.</span></span> <span data-ttu-id="7412d-147">如果存在关联的实例，则应在删除发送端口之前先终止这些实例。</span><span class="sxs-lookup"><span data-stu-id="7412d-147">If there are associated instances, you should terminate them before deleting the send port.</span></span>  
  
## <a name="ordered-delivery-to-file-transport"></a><span data-ttu-id="7412d-148">按序送达到文件传输</span><span class="sxs-lookup"><span data-stu-id="7412d-148">Ordered Delivery to File Transport</span></span>  
 <span data-ttu-id="7412d-149">消息将按顺序到达文件适配器。</span><span class="sxs-lookup"><span data-stu-id="7412d-149">Messages arrive at the File adapter in sequence.</span></span> <span data-ttu-id="7412d-150">文件适配器可能将消息附加到单个文件中或编写一个文件序列，其结果如下：</span><span class="sxs-lookup"><span data-stu-id="7412d-150">The File adapter may append messages to a single file or write out a sequence of files, with the following results:</span></span>  
  
-   <span data-ttu-id="7412d-151">如果将消息数据附加到单个文件中，则各个消息将按序附加。</span><span class="sxs-lookup"><span data-stu-id="7412d-151">If message data is appended to a single file, individual messages are appended in order.</span></span> <span data-ttu-id="7412d-152">使用 FILE 适配器的发送端口的“按序送达”选项只有在发送传输以附加模式工作时才有意义。</span><span class="sxs-lookup"><span data-stu-id="7412d-152">The ordered delivery option on a send port that uses the FILE adapter only makes sense if the send transport works in append mode</span></span>  
  
-   <span data-ttu-id="7412d-153">如果将消息写入各个文件中，则顺序将反映在文件名中，即按序命名。</span><span class="sxs-lookup"><span data-stu-id="7412d-153">If messages are written to individual files, the order is reflected in the file names, which are sequentially named.</span></span> <span data-ttu-id="7412d-154">在这种情况下，对于由适配器编写的文件，与时间信息（例如，文件创建时间或修改时间）相关的文件系统属性不必反映消息的到达顺序。</span><span class="sxs-lookup"><span data-stu-id="7412d-154">In this case, for files written by the adapter, file system properties relating to chronology (for example, file creation time or modification time) do not necessarily reflect the message arrival sequence.</span></span>  
  
## <a name="performance-impact-of-ordered-delivery"></a><span data-ttu-id="7412d-155">按序送达对性能的影响</span><span class="sxs-lookup"><span data-stu-id="7412d-155">Performance Impact of Ordered Delivery</span></span>  
 <span data-ttu-id="7412d-156">为了实现按序送达，BizTalk Server 必须对消息路径各个点上按序分布的消息的处理进行序列化。</span><span class="sxs-lookup"><span data-stu-id="7412d-156">To achieve ordered delivery, BizTalk Server must serialize processing of ordered messages at various points along the message pathway.</span></span> <span data-ttu-id="7412d-157">这对扩展技术（例如，使用多个主机实例实现对消息的并行处理）非常有效。</span><span class="sxs-lookup"><span data-stu-id="7412d-157">This works against scale-out techniques, such as the use of multiple host instances for parallel processing of messages.</span></span> <span data-ttu-id="7412d-158">在使用按序送达时，甚至配置为在多个主机实例上运行的端口也只运行在单个主机实例上，以确保按序送达。</span><span class="sxs-lookup"><span data-stu-id="7412d-158">When using ordered delivery, even ports configured to run on multiple host instances run only on a single host instance to ensure ordered delivery.</span></span> <span data-ttu-id="7412d-159">但在此情况下仍然能保持高可用性，因为如果正在处理按序送达消息的主机实例发生故障，将会在另一个可用主机实例上重新处理失败消息。</span><span class="sxs-lookup"><span data-stu-id="7412d-159">However, in this situation, high availability is still maintained because the failure of a host instance that is processing ordered delivery of messages results in reprocessing of the failed message on another available host instance.</span></span>  
  
 <span data-ttu-id="7412d-160">启用按序送达后，则默认**重试间隔**为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="7412d-160">When Ordered Delivery is enabled, the default **Retry Interval** is 5 minutes.</span></span> <span data-ttu-id="7412d-161">为了改进性能，请将“重试间隔”设置为最小值，即 1 分钟。</span><span class="sxs-lookup"><span data-stu-id="7412d-161">To improve performance, set the Retry Interval to the lowest value, which is 1 minute.</span></span> <span data-ttu-id="7412d-162">**重试间隔**属性可接受值为零 (0)，但零 (0) 无效。</span><span class="sxs-lookup"><span data-stu-id="7412d-162">The **Retry Interval** property may accept a value of zero (0) but zero (0) is not valid.</span></span> <span data-ttu-id="7412d-163">**重试计数**也可以进行调整到所需的重试次数。</span><span class="sxs-lookup"><span data-stu-id="7412d-163">The **Retry Count** can also be tuned to the number of retries needed.</span></span> <span data-ttu-id="7412d-164">例如，如果你知道应在不到 1 分钟之内处理请求且发送端口目标始终可以访问，则应将这两个值都设置为 1。</span><span class="sxs-lookup"><span data-stu-id="7412d-164">For example, if you know the request should process in <1 minute and the send port destination is always accessible, set both values to 1.</span></span>  
  
 <span data-ttu-id="7412d-165">若要更改的重试值，请转到[如何配置传输高级选项发送端口](http://go.microsoft.com/fwlink/p/?LinkID=267697)。</span><span class="sxs-lookup"><span data-stu-id="7412d-165">To change the Retry values, go to [How to Configure Transport Advanced Options for a Send Port](http://go.microsoft.com/fwlink/p/?LinkID=267697).</span></span>  
  
 <span data-ttu-id="7412d-166">有关“按序送达”的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="7412d-166">For additional information on Ordered Delivery, refer to the following:</span></span>  
  
 [<span data-ttu-id="7412d-167">BizTalk： 端到端有序消息处理选项</span><span class="sxs-lookup"><span data-stu-id="7412d-167">BizTalk: End-to-End Ordered Message Processing Options</span></span>](http://social.technet.microsoft.com/wiki/contents/articles/12887.biztalk-end-to-end-ordered-message-processing-options.aspx)  
  
 [<span data-ttu-id="7412d-168">BizTalk： 有序的传递</span><span class="sxs-lookup"><span data-stu-id="7412d-168">BizTalk: Ordered Delivery</span></span>](http://social.technet.microsoft.com/wiki/contents/articles/6681.biztalk-ordered-delivery.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="7412d-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7412d-169">See Also</span></span>  
 <span data-ttu-id="7412d-170">[与 MSMQ 适配器的消息的有序传送](../core/ordered-delivery-of-messages-with-the-msmq-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="7412d-170">[Ordered Delivery of Messages with the MSMQ Adapter](../core/ordered-delivery-of-messages-with-the-msmq-adapter.md) </span></span>  
 [<span data-ttu-id="7412d-171">与 MQSeries 适配器的消息的有序传送</span><span class="sxs-lookup"><span data-stu-id="7412d-171">Ordered Delivery of Messages with the MQSeries Adapter</span></span>](../core/ordered-delivery-of-messages-with-the-mqseries-adapter.md)