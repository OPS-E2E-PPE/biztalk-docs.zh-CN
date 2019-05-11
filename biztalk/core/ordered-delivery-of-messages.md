---
title: 按序送达消息 |Microsoft Docs
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
ms.openlocfilehash: 6068d3d4e84389022a07d315b808b7005b95a88c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262596"
---
# <a name="ordered-delivery-of-messages"></a><span data-ttu-id="a60cf-102">按序送达消息</span><span class="sxs-lookup"><span data-stu-id="a60cf-102">Ordered Delivery of Messages</span></span>
<span data-ttu-id="a60cf-103">按序的消息传递可确保发布到 MessageBox 数据库中给定订单的消息将传送到每个匹配的订户所在的相同顺序仍依照其发布到 messagebox。</span><span class="sxs-lookup"><span data-stu-id="a60cf-103">Ordered message delivery ensures that messages that are published to the MessageBox database in a given order are delivered to each matching subscriber in the same order in which they were published to the message box.</span></span>  
  
## <a name="configuring-ordered-message-delivery"></a><span data-ttu-id="a60cf-104">配置按序送达的消息</span><span class="sxs-lookup"><span data-stu-id="a60cf-104">Configuring Ordered Message Delivery</span></span>  
 <span data-ttu-id="a60cf-105">可以在以下位置配置按序送达的消息：</span><span class="sxs-lookup"><span data-stu-id="a60cf-105">Ordered message delivery can be configured in the following places:</span></span>  
  
-   <span data-ttu-id="a60cf-106">**接收**业务流程中的形状</span><span class="sxs-lookup"><span data-stu-id="a60cf-106">**Receive** shape in an orchestration</span></span>  
  
-   <span data-ttu-id="a60cf-107">发送端口</span><span class="sxs-lookup"><span data-stu-id="a60cf-107">Send port</span></span>  
  
## <a name="ordered-delivery-with-existing-transports"></a><span data-ttu-id="a60cf-108">按序送达使用现有传输实现</span><span class="sxs-lookup"><span data-stu-id="a60cf-108">Ordered Delivery with Existing Transports</span></span>  
 <span data-ttu-id="a60cf-109">某些传输，如文件和 HTTP 的基础的协议不一致的按序送达的概念。</span><span class="sxs-lookup"><span data-stu-id="a60cf-109">The protocols underlying certain transports, such as FILE and HTTP, are not consistent with the notion of ordered delivery.</span></span> <span data-ttu-id="a60cf-110">但是，即使使用此类传输，如果该端口绑定到传输标记为按序送达，则 BizTalk Server 通过确保传输不会直到成功发送当前一获取下一个出站消息来强制执行按序的送达.</span><span class="sxs-lookup"><span data-stu-id="a60cf-110">However, even with such transports, if the port bound to the transport is marked for ordered delivery, then BizTalk Server enforces ordered delivery by ensuring that the transport does not get the next outbound message until the current one has been successfully sent.</span></span> <span data-ttu-id="a60cf-111">若要实现此目的，BizTalk Server 每个将消息传递到传输的适配器在单个批次并等待直到该适配器已成功删除该消息从 messagebox 中另一个批处理中的下一条消息，交付到适配器之前。</span><span class="sxs-lookup"><span data-stu-id="a60cf-111">To achieve this, BizTalk Server passes each message to the transport's adapter in a single batch and waits until the adapter has successfully deleted the message from the message box before delivering the next message, in another batch, to the adapter.</span></span>  
  
### <a name="ordered-delivery-for-custom-adapters"></a><span data-ttu-id="a60cf-112">自定义适配器按序送达</span><span class="sxs-lookup"><span data-stu-id="a60cf-112">Ordered Delivery for Custom Adapters</span></span>  
 <span data-ttu-id="a60cf-113">为自定义接收适配器，有一些特殊注意事项。</span><span class="sxs-lookup"><span data-stu-id="a60cf-113">There are special considerations for custom receive adapters.</span></span> <span data-ttu-id="a60cf-114">如果你正在编写的自定义适配器支持在按序送达接收，适配器应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a60cf-114">It you are writing a custom adapter that supports ordered delivery on receive, the adapter should do the following:</span></span>  
  
- <span data-ttu-id="a60cf-115">在提交一批消息之后, 您的自定义接收适配器应等待**BatchComplete**从 BizTalk Server 提交下一批之前的回调。</span><span class="sxs-lookup"><span data-stu-id="a60cf-115">After submitting a batch of messages, your custom receive adapter should wait for the **BatchComplete** callback from BizTalk Server before submitting the next batch.</span></span> <span data-ttu-id="a60cf-116">有关更多详细信息，请参阅[Batch-Supported 接收适配器的接口](../core/interfaces-for-a-batch-supported-receive-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="a60cf-116">For more details, see [Interfaces for a Batch-Supported Receive Adapter](../core/interfaces-for-a-batch-supported-receive-adapter.md).</span></span>  
  
- <span data-ttu-id="a60cf-117">如果消息在管道中失败，则应挂起，最好作为不可恢复。</span><span class="sxs-lookup"><span data-stu-id="a60cf-117">If a message fails in the pipeline, it should be suspended, preferably as nonresumable.</span></span> <span data-ttu-id="a60cf-118">使用**BTS。SuspendAsNonResumable**消息上下文属性中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来适当地标记消息。</span><span class="sxs-lookup"><span data-stu-id="a60cf-118">Use the **BTS.SuspendAsNonResumable** message context property in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to flag the message appropriately.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a60cf-119">如果以后恢复挂起的消息，消息顺序可能会中断。</span><span class="sxs-lookup"><span data-stu-id="a60cf-119">Message order can be broken if a suspended message is later resumed.</span></span> <span data-ttu-id="a60cf-120">如果不希望此行为，挂起失败的消息作为不可恢复。</span><span class="sxs-lookup"><span data-stu-id="a60cf-120">If you do not want this behavior, suspend failed messages as nonresumable.</span></span>  
  
 <span data-ttu-id="a60cf-121">构建自定义适配器的详细信息，请参阅[开发自定义适配器](../core/developing-custom-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="a60cf-121">For more details on building a custom adapter, see [Developing Custom Adapters](../core/developing-custom-adapters.md).</span></span>  
  
## <a name="conditions-for-end-to-end-ordered-message-processing"></a><span data-ttu-id="a60cf-122">条件的端到端按序消息处理</span><span class="sxs-lookup"><span data-stu-id="a60cf-122">Conditions for End-to-End Ordered Message Processing</span></span>  
 <span data-ttu-id="a60cf-123">若要提供端到端按序的送达必须满足以下条件:</span><span class="sxs-lookup"><span data-stu-id="a60cf-123">To provide end-to-end ordered delivery the following conditions must be met:</span></span>  
  
- <span data-ttu-id="a60cf-124">必须与适配器提交给 BizTalk Server 时保留消息的顺序接收消息。</span><span class="sxs-lookup"><span data-stu-id="a60cf-124">Messages must be received with an adapter that preserves the order of the messages when submitting them to BizTalk Server.</span></span> <span data-ttu-id="a60cf-125">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，这样的适配器的示例包括 MSMQ 和 MQSeries。</span><span class="sxs-lookup"><span data-stu-id="a60cf-125">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], examples of such adapters are MSMQ and MQSeries.</span></span> <span data-ttu-id="a60cf-126">此外，可以使用 HTTP 或 SOAP 适配器提交消息的顺序，但在这种情况下 HTTP 或 SOAP 客户端需要通过一次提交一个消息来强制实现顺序。</span><span class="sxs-lookup"><span data-stu-id="a60cf-126">In addition, HTTP or SOAP adapters can be used to submit messages in order, but in that case the HTTP or SOAP client needs to enforce the order by submitting messages one at a time.</span></span>  
  
- <span data-ttu-id="a60cf-127">您必须订阅这些消息与发送端口都**按序送达**选项设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="a60cf-127">You must subscribe to these messages with a send port that has the **Ordered Delivery** option set to `True`.</span></span>  
  
- <span data-ttu-id="a60cf-128">如果业务流程来的处理消息，只能运行一个业务流程实例应使用，该业务流程应配置为使用顺序保护，并**按序送达**属性业务流程的接收端口应设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="a60cf-128">If an orchestration is used to process the messages, only a single instance of the orchestration should be used, the orchestration should be configured to use a sequential convoy, and the **Ordered Delivery** property of the orchestration's receive port should be set to `True`.</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="a60cf-129">限制</span><span class="sxs-lookup"><span data-stu-id="a60cf-129">Restrictions</span></span>  
 <span data-ttu-id="a60cf-130">以下不支持按序的送达消息：</span><span class="sxs-lookup"><span data-stu-id="a60cf-130">Ordered delivery of messages is not supported for the following:</span></span>  
  
- <span data-ttu-id="a60cf-131">动态发送端口中[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]和以前的版本</span><span class="sxs-lookup"><span data-stu-id="a60cf-131">Dynamic send ports in [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] and previous versions</span></span>

- <span data-ttu-id="a60cf-132">动态发送端口中[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]（和任何更高版本） 的适配器类型**不**支持静态发送端口按序送达</span><span class="sxs-lookup"><span data-stu-id="a60cf-132">Dynamic send ports in [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] (and any newer versions) for those adapter types that **don't** support ordered delivery on static send ports</span></span>
  
- <span data-ttu-id="a60cf-133">备份传输</span><span class="sxs-lookup"><span data-stu-id="a60cf-133">Backup transports</span></span>  

  
## <a name="interactions"></a><span data-ttu-id="a60cf-134">交互</span><span class="sxs-lookup"><span data-stu-id="a60cf-134">Interactions</span></span>  
 <span data-ttu-id="a60cf-135">为发送端口配置按序的送达后，应注意与 BizTalk Server 中的其他配置行为之间的以下交互：</span><span class="sxs-lookup"><span data-stu-id="a60cf-135">When ordered delivery is configured for a send port, be aware of the following interactions with other configured behaviors in BizTalk Server:</span></span>  
  
-   <span data-ttu-id="a60cf-136">用于上相同的"停止发送随后的消息在当前消息失败时"设置发送端口：</span><span class="sxs-lookup"><span data-stu-id="a60cf-136">For the "Stop sending subsequent messages on current message failure" setting on the same send port:</span></span>  
  
    -   <span data-ttu-id="a60cf-137">**如果为 false。**</span><span class="sxs-lookup"><span data-stu-id="a60cf-137">**False.**</span></span> <span data-ttu-id="a60cf-138">失败的消息已挂起 （作为不可恢复），所有后续消息继续处理。</span><span class="sxs-lookup"><span data-stu-id="a60cf-138">Only the failed message is suspended (as not resumable) and all subsequent messages continue to be processed.</span></span> <span data-ttu-id="a60cf-139">这会保留未失败消息的顺序，但可能会导致序列中的空白。</span><span class="sxs-lookup"><span data-stu-id="a60cf-139">This preserves the ordering of the non-failed messages but can result in gaps in the sequence.</span></span> <span data-ttu-id="a60cf-140">例如，如果收到订单 101、 102 和 103，并且订单 102 被挂起，则订单 101 和 103 将继续按顺序处理。</span><span class="sxs-lookup"><span data-stu-id="a60cf-140">For example, if orders 101, 102, and 103 are received and order 102 is suspended, orders 101 and 103 will continue to be processed in order.</span></span>  
  
    -   <span data-ttu-id="a60cf-141">**为 true。**</span><span class="sxs-lookup"><span data-stu-id="a60cf-141">**True.**</span></span> <span data-ttu-id="a60cf-142">如果任何消息处理失败，则挂起发送端口实例。</span><span class="sxs-lookup"><span data-stu-id="a60cf-142">The send port instance is suspended if any of the messages fails processing.</span></span> <span data-ttu-id="a60cf-143">这会导致消息被挂起的有序集的所有后续消息。</span><span class="sxs-lookup"><span data-stu-id="a60cf-143">This causes all subsequent messages in the ordered set of messages to be suspended.</span></span> <span data-ttu-id="a60cf-144">这通过防止在送达失败的消息传递之前的后续消息保留消息顺序。</span><span class="sxs-lookup"><span data-stu-id="a60cf-144">This preserves message order by preventing delivery of subsequent messages before delivery of the failed message.</span></span>  
  
-   <span data-ttu-id="a60cf-145">如果要求响应发送端口具有"停止发送随后的消息在当前消息失败时"属性设置为`true`，以及是否可恢复交换处理配置的接收管道的拆装阶段的响应，然后发送端口不会停止发送消息 （即实例不会挂起） 如果在拆装响应可恢复的错误。</span><span class="sxs-lookup"><span data-stu-id="a60cf-145">If a solicit-response send port has the "Stop sending subsequent messages on current message failure" property set to `true`, and if recoverable interchange processing is configured for the disassembly stage of the receive pipeline for the response, then the send port does not stop sending messages (that is, the instance is not suspended) if there is a recoverable error in disassembling the response.</span></span>  
  
-   <span data-ttu-id="a60cf-146">之前删除按序发送端口，请确保有与之关联的实例。</span><span class="sxs-lookup"><span data-stu-id="a60cf-146">Before deleting an ordered send port, ensure that there are no instances associated with it.</span></span> <span data-ttu-id="a60cf-147">如果有关联的实例，应删除发送端口之前终止它们。</span><span class="sxs-lookup"><span data-stu-id="a60cf-147">If there are associated instances, you should terminate them before deleting the send port.</span></span>  
  
## <a name="ordered-delivery-to-file-transport"></a><span data-ttu-id="a60cf-148">按序送达文件传输</span><span class="sxs-lookup"><span data-stu-id="a60cf-148">Ordered Delivery to File Transport</span></span>  
 <span data-ttu-id="a60cf-149">消息按顺序到达文件适配器。</span><span class="sxs-lookup"><span data-stu-id="a60cf-149">Messages arrive at the File adapter in sequence.</span></span> <span data-ttu-id="a60cf-150">文件适配器可能会将消息附加到单个文件，或写出一系列文件，其结果如下：</span><span class="sxs-lookup"><span data-stu-id="a60cf-150">The File adapter may append messages to a single file or write out a sequence of files, with the following results:</span></span>  
  
-   <span data-ttu-id="a60cf-151">如果消息数据附加到单个文件，则各个消息将按序附加。</span><span class="sxs-lookup"><span data-stu-id="a60cf-151">If message data is appended to a single file, individual messages are appended in order.</span></span> <span data-ttu-id="a60cf-152">使用文件适配器的发送端口上的按序的送达选项仅在发送传输以附加模式工作时才有意义</span><span class="sxs-lookup"><span data-stu-id="a60cf-152">The ordered delivery option on a send port that uses the FILE adapter only makes sense if the send transport works in append mode</span></span>  
  
-   <span data-ttu-id="a60cf-153">如果消息将写入到单个文件中，顺序将反映在文件名称，即按序命名。</span><span class="sxs-lookup"><span data-stu-id="a60cf-153">If messages are written to individual files, the order is reflected in the file names, which are sequentially named.</span></span> <span data-ttu-id="a60cf-154">在这种情况下，对于由适配器编写的文件，与编年表 （例如，文件创建时间或修改时间） 相关的文件系统属性不一定反映消息的到达顺序。</span><span class="sxs-lookup"><span data-stu-id="a60cf-154">In this case, for files written by the adapter, file system properties relating to chronology (for example, file creation time or modification time) do not necessarily reflect the message arrival sequence.</span></span>  
  
## <a name="performance-impact-of-ordered-delivery"></a><span data-ttu-id="a60cf-155">按序送达对性能的影响</span><span class="sxs-lookup"><span data-stu-id="a60cf-155">Performance Impact of Ordered Delivery</span></span>  
 <span data-ttu-id="a60cf-156">若要实现按序的送达，BizTalk Server 必须序列化消息路径各个点的有序消息的处理。</span><span class="sxs-lookup"><span data-stu-id="a60cf-156">To achieve ordered delivery, BizTalk Server must serialize processing of ordered messages at various points along the message pathway.</span></span> <span data-ttu-id="a60cf-157">此扩展适用于横向扩展技术，例如，消息的并行处理多个主机实例使用。</span><span class="sxs-lookup"><span data-stu-id="a60cf-157">This works against scale-out techniques, such as the use of multiple host instances for parallel processing of messages.</span></span> <span data-ttu-id="a60cf-158">在使用按序的送达，甚至端口配置为运行在多个主机实例上运行仅在单个主机实例以确保按序的送达。</span><span class="sxs-lookup"><span data-stu-id="a60cf-158">When using ordered delivery, even ports configured to run on multiple host instances run only on a single host instance to ensure ordered delivery.</span></span> <span data-ttu-id="a60cf-159">但是，在此情况下，可用性组仍将保留因为正在处理的主机实例失败按序送达消息中的另一个可用的主机实例上的失败消息重新处理的结果。</span><span class="sxs-lookup"><span data-stu-id="a60cf-159">However, in this situation, high availability is still maintained because the failure of a host instance that is processing ordered delivery of messages results in reprocessing of the failed message on another available host instance.</span></span>  
  
 <span data-ttu-id="a60cf-160">启用按序送达时，默认值**重试间隔**为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="a60cf-160">When Ordered Delivery is enabled, the default **Retry Interval** is 5 minutes.</span></span> <span data-ttu-id="a60cf-161">若要提高性能，设置为最低值，该值为 1 分钟重试间隔。</span><span class="sxs-lookup"><span data-stu-id="a60cf-161">To improve performance, set the Retry Interval to the lowest value, which is 1 minute.</span></span> <span data-ttu-id="a60cf-162">**重试间隔**属性可接受值为零 (0)，但零 (0) 无效。</span><span class="sxs-lookup"><span data-stu-id="a60cf-162">The **Retry Interval** property may accept a value of zero (0) but zero (0) is not valid.</span></span> <span data-ttu-id="a60cf-163">**重试计数**也可以进行调整到所需的重试次数。</span><span class="sxs-lookup"><span data-stu-id="a60cf-163">The **Retry Count** can also be tuned to the number of retries needed.</span></span> <span data-ttu-id="a60cf-164">例如，如果您知道请求应处理在 < 1 分钟和发送端口目标始终是可访问，将这两个值设置为 1。</span><span class="sxs-lookup"><span data-stu-id="a60cf-164">For example, if you know the request should process in <1 minute and the send port destination is always accessible, set both values to 1.</span></span>  
  
 <span data-ttu-id="a60cf-165">若要更改重试值，请转到[如何配置传输高级选项的发送端口](http://go.microsoft.com/fwlink/p/?LinkID=267697)。</span><span class="sxs-lookup"><span data-stu-id="a60cf-165">To change the Retry values, go to [How to Configure Transport Advanced Options for a Send Port](http://go.microsoft.com/fwlink/p/?LinkID=267697).</span></span>  
  
 <span data-ttu-id="a60cf-166">有关按序送达的其他信息，请参阅以下：</span><span class="sxs-lookup"><span data-stu-id="a60cf-166">For additional information on Ordered Delivery, refer to the following:</span></span>  
  
 [<span data-ttu-id="a60cf-167">BizTalk:端到端按序消息处理选项</span><span class="sxs-lookup"><span data-stu-id="a60cf-167">BizTalk: End-to-End Ordered Message Processing Options</span></span>](http://social.technet.microsoft.com/wiki/contents/articles/12887.biztalk-end-to-end-ordered-message-processing-options.aspx)  
  
 [<span data-ttu-id="a60cf-168">BizTalk:按序的送达</span><span class="sxs-lookup"><span data-stu-id="a60cf-168">BizTalk: Ordered Delivery</span></span>](http://social.technet.microsoft.com/wiki/contents/articles/6681.biztalk-ordered-delivery.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="a60cf-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="a60cf-169">See Also</span></span>  
 <span data-ttu-id="a60cf-170">[按序送达消息使用 MSMQ 适配器](../core/ordered-delivery-of-messages-with-the-msmq-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a60cf-170">[Ordered Delivery of Messages with the MSMQ Adapter](../core/ordered-delivery-of-messages-with-the-msmq-adapter.md) </span></span>  
 [<span data-ttu-id="a60cf-171">使用 MQSeries 适配器按序送达消息</span><span class="sxs-lookup"><span data-stu-id="a60cf-171">Ordered Delivery of Messages with the MQSeries Adapter</span></span>](../core/ordered-delivery-of-messages-with-the-mqseries-adapter.md)