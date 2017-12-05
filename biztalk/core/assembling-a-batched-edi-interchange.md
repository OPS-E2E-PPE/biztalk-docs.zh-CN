---
title: "组合批处理的 EDI 交换 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18f64595-935e-4d52-9ec2-5edf7c2b9e83
caps.latest.revision: "45"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c4274362e5ec8441e203d0b2b97f27e95235fd9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="assembling-a-batched-edi-interchange"></a><span data-ttu-id="e24d4-102">装配批处理的 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="e24d4-102">Assembling a Batched EDI Interchange</span></span>
<span data-ttu-id="e24d4-103">为了将各个事务集批元素组装成 EDI 交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI 和 AS2 将执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e24d4-103">To assemble individual transaction-set batch elements into an EDI interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2 does the following:</span></span>  
  
-   <span data-ttu-id="e24d4-104">标识要进行批处理的批元素</span><span class="sxs-lookup"><span data-stu-id="e24d4-104">Identifies batch elements for batching</span></span>  
  
-   <span data-ttu-id="e24d4-105">收到各个批元素后对其进行验证和缓冲</span><span class="sxs-lookup"><span data-stu-id="e24d4-105">Validates and buffers individual batch elements upon receipt</span></span>  
  
-   <span data-ttu-id="e24d4-106">检索特定批元素，如果满足发布标准，则组装批交换</span><span class="sxs-lookup"><span data-stu-id="e24d4-106">Retrieves specific batch elements and assembles a batched interchange when the release criteria is met</span></span>  
  
 <span data-ttu-id="e24d4-107">收集各个消息以组合成批的开始时间是根据批处理激活标准确定的，</span><span class="sxs-lookup"><span data-stu-id="e24d4-107">The start time for collection of individual messages to go into a batch is determined by the batch activation criteria.</span></span> <span data-ttu-id="e24d4-108">批的发布时间是根据批发布标准确定的。</span><span class="sxs-lookup"><span data-stu-id="e24d4-108">The time at which the batch is released is determined by the batch release criteria.</span></span> <span data-ttu-id="e24d4-109">有关条件这两个集的详细信息，请参阅[配置传出批处理](../core/configuring-an-outgoing-batch.md)。</span><span class="sxs-lookup"><span data-stu-id="e24d4-109">For more information about these two sets of criteria, see [Configuring an Outgoing Batch](../core/configuring-an-outgoing-batch.md).</span></span>  
  
## <a name="message-flow-for-outgoing-batched-messages"></a><span data-ttu-id="e24d4-110">传出批处理消息的消息流</span><span class="sxs-lookup"><span data-stu-id="e24d4-110">Message Flow for Outgoing Batched Messages</span></span>  
 <span data-ttu-id="e24d4-111">当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置为对传出消息进行批处理时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组件将执行下面的一系列步骤，来准备要发送的批处理消息。</span><span class="sxs-lookup"><span data-stu-id="e24d4-111">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is configured to batch an outgoing message, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] components will perform the following series of steps to prepare the batched message for sending.</span></span> <span data-ttu-id="e24d4-112">这一系列的步骤描述了这样一种情况：具有 BatchMarker 管道组件的 EDIReceive 管道处理收到的交换，这些交换包含要成批进行发送的事务集。</span><span class="sxs-lookup"><span data-stu-id="e24d4-112">This series of steps describes the case in which the EDIReceive pipeline with the BatchMarker pipeline component processes the received interchanges that contain transaction sets to be batched for sending.</span></span>  
  
1.  <span data-ttu-id="e24d4-113">EDIReceive 管道中的 BatchMarker 管道组件通过参与方属性中的 EDI 批处理筛选器设置，确定需要进行批处理的消息。</span><span class="sxs-lookup"><span data-stu-id="e24d4-113">The BatchMarker pipeline component in the EDIReceive pipeline determines which messages need to be batched from the EDI batch filter settings in the party properties.</span></span> <span data-ttu-id="e24d4-114">（该组件是唯一一个查看批处理筛选器设置并根据这些设置进行处理的批处理组件。）</span><span class="sxs-lookup"><span data-stu-id="e24d4-114">(This is the only batching component that looks at the batch filter settings and acts upon them.)</span></span>  
  
2.  <span data-ttu-id="e24d4-115">如果仅一个批配置的筛选器设置订阅消息，则 BatchMarker 组件将升级属性 `EDI.ToBeBatched = True`。</span><span class="sxs-lookup"><span data-stu-id="e24d4-115">If the filter settings of only one batch configuration subscribes to a message, the BatchMarker component will promote the property `EDI.ToBeBatched = True`.</span></span> <span data-ttu-id="e24d4-116">这样可确保批处理业务流程将提取该消息。</span><span class="sxs-lookup"><span data-stu-id="e24d4-116">This ensures that the batching orchestration will pick up the message.</span></span>  
  
3.  <span data-ttu-id="e24d4-117">如果多个批配置的筛选器设置与消息上下文匹配，则 BatchMarker 组件将升级属性 `EDI.ToBeRouted = True`，并将 `EDI.BatchIds` 属性设置为以空格分隔的匹配批 ID 列表。</span><span class="sxs-lookup"><span data-stu-id="e24d4-117">If the filter settings of more than one batch configuration match the context of a message, the BatchMarker component promotes the properties `EDI.ToBeRouted = True` and sets the `EDI.BatchIds` property to a space delimited list containing the matching batch IDs.</span></span>  <span data-ttu-id="e24d4-118">这样可确保路由业务流程将订阅该消息。</span><span class="sxs-lookup"><span data-stu-id="e24d4-118">This ensures that the routing orchestration will subscribe to the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e24d4-119">您可以在自定义接收管道或自定义业务流程中升级相应的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="e24d4-119">You can promote the appropriate context properties in a custom receive pipeline or a custom orchestration.</span></span> <span data-ttu-id="e24d4-120">自定义接收管道可使用 BatchMarker 管道组件，或者在不使用 BatchMarker 管道组件的情况下升级属性。</span><span class="sxs-lookup"><span data-stu-id="e24d4-120">The custom receive pipeline can use the BatchMarker pipeline component, or can promote the properties without using the BatchMarker pipeline component.</span></span>  
  
4.  <span data-ttu-id="e24d4-121">路由业务流程提取为其升级了 `EDI.ToBeRouted = True` 和 `EDI.BatchIds` 的任何事务集，然后创建该事务集的副本，以确保 `EDI.BatchIds` 中包含每个批 ID 的一个副本。</span><span class="sxs-lookup"><span data-stu-id="e24d4-121">The routing orchestration picks up any transaction set for which `EDI.ToBeRouted = True` and `EDI.BatchIds` is promoted, and then creates copies of the transaction set, ensuring that there is a copy for each batch ID contained in `EDI.BatchIds`.</span></span> <span data-ttu-id="e24d4-122">路由业务流程将设置 `EDI.ToBeBatched = True`，且每个事务集副本的 `EDI.BatchId` 将设置为匹配批配置的批 ID。</span><span class="sxs-lookup"><span data-stu-id="e24d4-122">The routing orchestration sets `EDI.ToBeBatched = True` and `EDI.BatchId` is set to the batch ID of the matching batch configuration for each copy of the transaction set.</span></span> <span data-ttu-id="e24d4-123">这样可确保批处理业务流程会提取事务集以便进行批处理。</span><span class="sxs-lookup"><span data-stu-id="e24d4-123">This ensures that the transaction sets will be picked up by the batching orchestration for batching.</span></span>  
  
5.  <span data-ttu-id="e24d4-124">批处理业务流程提取已升级下列属性的所有消息：</span><span class="sxs-lookup"><span data-stu-id="e24d4-124">The batching orchestration picks up all messages for which the following properties have been promoted:</span></span>  
  
    -   <span data-ttu-id="e24d4-125">与此批处理业务流程实例相关的批的 `EDI.ToBeBatched = True` 和 EDI.BatchId = 批 ID。</span><span class="sxs-lookup"><span data-stu-id="e24d4-125">`EDI.ToBeBatched = True` and EDI.BatchId = the batch id of the batch associated with this instance of the batching orchestration.</span></span>  
  
    -   <span data-ttu-id="e24d4-126">`EDI.ToBeBatched = True` 和 EDI.BatchName = 已配置批的名称，且 EDI.DestinationPartyName = 包含此批配置的参与方名称。</span><span class="sxs-lookup"><span data-stu-id="e24d4-126">`EDI.ToBeBatched = True` and EDI.BatchName = the name of the configured batch and EDI.DestinationPartyName = the party name that contains the batch configuration.</span></span>  
  
     <span data-ttu-id="e24d4-127">当具有 BatchMarker 管道组件的 EDIReceive 管道处理传入消息时，批处理业务流程将仅对 X12 或 EDIFACT 编码的事务集进行批处理。</span><span class="sxs-lookup"><span data-stu-id="e24d4-127">When the incoming messages are processed by the EDIReceive pipeline (with the BatchMarker pipeline component), the batching orchestration will batch only X12- or EDIFACT-encoded transaction sets.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e24d4-128">对于每个活动批配置，都将有一个批处理业务流程的实例，并且每个实例订阅一个特定的批 ID。</span><span class="sxs-lookup"><span data-stu-id="e24d4-128">There will be one instance of the batching orchestration for each active batch configuration, each subscribing to a specific batch ID.</span></span> <span data-ttu-id="e24d4-129">创建新的批处理配置中时自动设置批次 ID 值**标识**部分**批处理配置**的单向协议选项卡页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="e24d4-129">The batch ID value is set automatically when creating a new batch configuration in the **Identification** section of the **Batching Configuration** page of the one-way agreement tab of the **Agreement Properties** dialog box.</span></span>  
  
6.  <span data-ttu-id="e24d4-130">批处理业务流程会验证要进行批处理的每个事务集。</span><span class="sxs-lookup"><span data-stu-id="e24d4-130">The batching orchestration validates each transaction set to be batched.</span></span> <span data-ttu-id="e24d4-131">如果事务集未能通过验证，则会将 `EDI.BatchItemValidationFailure` 上下文属性设置为“True”。</span><span class="sxs-lookup"><span data-stu-id="e24d4-131">If the transaction set fails validation, it sets the `EDI.BatchItemValidationFailure` context property to "True".</span></span> <span data-ttu-id="e24d4-132">**BatchSuspend** orchestration 拾取基于该上下文属性的消息，发送错误信息，然后已挂起。</span><span class="sxs-lookup"><span data-stu-id="e24d4-132">The **BatchSuspend** orchestration picks up the message based upon that context property, posts error information, and then is suspended.</span></span>  
  
7.  <span data-ttu-id="e24d4-133">当满足批发布条件时，批处理业务流程将批元素组装为一个批，并创建信封。</span><span class="sxs-lookup"><span data-stu-id="e24d4-133">When the batch release criteria has been met, the batching orchestration assembles the batch elements into a batch and creates an envelope.</span></span>  
  
8.  <span data-ttu-id="e24d4-134">在批处理业务流程完成某个交换的批处理之后，它将升级该交换的以下属性：EDI.DestinationPartyName = %PartyName%，EDI.BatchEncodingType = X12 或 EDIFACT，并且 EDI.ToBeBatched = False。</span><span class="sxs-lookup"><span data-stu-id="e24d4-134">After the batching orchestration completes batching an interchange, it promotes the following properties on that interchange: EDI.DestinationPartyName = %PartyName%, EDI.BatchEncodingType = X12 or EDIFACT, and EDI.ToBeBatched = False.</span></span>  
  
9. <span data-ttu-id="e24d4-135">发送端口选取基于 EDI 的批处理的事务集。DestinationPartyName = \<PartyName\>，EDI。BatchEncodingType = EDIFACT 或 X12，和 EDI。ToBeBatched = False。</span><span class="sxs-lookup"><span data-stu-id="e24d4-135">A send port picks up the batched transaction sets based on EDI.DestinationPartyName = \<PartyName\>, EDI.BatchEncodingType = EDIFACT or X12, and EDI.ToBeBatched = False.</span></span>  
  
## <a name="batching-orchestration-control-messages"></a><span data-ttu-id="e24d4-136">批处理业务流程控制消息</span><span class="sxs-lookup"><span data-stu-id="e24d4-136">Batching Orchestration Control Messages</span></span>  
 <span data-ttu-id="e24d4-137">批处理业务流程由下列控制消息激活、终止或重写：</span><span class="sxs-lookup"><span data-stu-id="e24d4-137">The batching orchestration is activated, terminated, or overridden by the following control messages:</span></span>  
  
-   <span data-ttu-id="e24d4-138">**BatchActivation**： 时业务流程会收到此消息，将创建批处理的业务流程的实例并且业务流程是活动状态，以接收批处理元素 （如果它满足批激活条件）。</span><span class="sxs-lookup"><span data-stu-id="e24d4-138">**BatchActivation**: When the orchestration receives this message, an instance of the batching orchestration is created and the orchestration is active to receive batch elements (if it meets the batch activation criteria).</span></span> <span data-ttu-id="e24d4-139">通过单击发送此控件消息**启动**按钮上的批处理配置**批处理配置**的单向协议选项卡页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="e24d4-139">This control message is sent by clicking the **Start** button of a batch configuration on the **Batching Configuration** page of the one-way agreement tab of the **Agreement Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="e24d4-140">**BatchTermination**： 当业务流程收到此消息时，它创建从现有的批处理元素的一批、 将消息发布到 MessageBox，并终止。</span><span class="sxs-lookup"><span data-stu-id="e24d4-140">**BatchTermination**: When the orchestration receives this message, it creates a batch from existing batch elements, publishes the message to the MessageBox, and terminates.</span></span> <span data-ttu-id="e24d4-141">通过单击发送此控件消息**停止**按钮上的批处理配置**批处理配置**的单向协议选项卡页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="e24d4-141">This control message is sent by clicking the **Stop** button of a batch configuration on the **Batching Configuration** page of the one-way agreement tab of the **Agreement Properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e24d4-142">如果达到指定的时间，也会被终止业务流程**结束于**中的属性**终止**部分**批处理配置**页单向协议选项卡**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="e24d4-142">The orchestration is also terminated if it reaches the time specified for the **End-by** property in the **Termination** section of the **Batching Configuration** page of the one-way agreement tab of the **Agreement Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="e24d4-143">**BatchOverride**： 当业务流程收到此消息时，它创建从现有元素的一批，将消息发布到 MessageBox，，然后等待下一批消息。</span><span class="sxs-lookup"><span data-stu-id="e24d4-143">**BatchOverride**: When the orchestration receives this message, it creates a batch from existing elements, publishes the message to the MessageBox, and then waits for messages for the next batch.</span></span> <span data-ttu-id="e24d4-144">通过单击发送此控件消息**重写**按钮上的批处理配置**批处理配置**的单向协议选项卡页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="e24d4-144">This control message is sent by clicking the **Override** button of a batch configuration on the **Batching Configuration** page of the one-way agreement tab of the **Agreement Properties** dialog box.</span></span>  
  
 <span data-ttu-id="e24d4-145">批处理业务流程通过 BatchControlMessageRecvLoc 接收位置接收控制消息。</span><span class="sxs-lookup"><span data-stu-id="e24d4-145">The batching orchestration receives the control messages via the BatchControlMessageRecvLoc receive location.</span></span> <span data-ttu-id="e24d4-146">此 SQL 接收位置的轮询间隔为 30 秒的默认设置，但可以更改在**SQL 传输属性**接收位置的对话框。</span><span class="sxs-lookup"><span data-stu-id="e24d4-146">The polling interval for this SQL receive location is set by default to 30 seconds, but can be changed in the **SQL Transport Properties** dialog box for the receive location.</span></span> <span data-ttu-id="e24d4-147">缩短轮询间隔可确保 BatchControlMessageRecvLoc 接收位置将在您执行控制消息发送操作之后（如启动批处理业务流程时）会立即收到控制消息。</span><span class="sxs-lookup"><span data-stu-id="e24d4-147">Decreasing the polling interval will ensure that the BatchControlMessageRecvLoc receive location will receive a control message soon after you perform the action that sent the control message (such as when you start the batching orchestration).</span></span>  
  
 <span data-ttu-id="e24d4-148">当您启动批处理业务流程时，将执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="e24d4-148">The following steps occur when you start a batch orchestration:</span></span>  
  
1.  <span data-ttu-id="e24d4-149">当你单击**启动**按钮， [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ，该值指示你正在激活的批处理业务流程的当事方和批处理 id 表中创建一条记录。</span><span class="sxs-lookup"><span data-stu-id="e24d4-149">When you click the **Start** button, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] creates a record in a table indicating which party and batch id you are activating the batch orchestration for.</span></span>  
  
2.  <span data-ttu-id="e24d4-150">与 BatchControlMessageRecvLoc 接收位置关联的 SQL 适配器将进行轮询，以查看数据库中是否存在该记录。</span><span class="sxs-lookup"><span data-stu-id="e24d4-150">The SQL adapter associated with the BatchControlMessageRecvLoc receive location polls to see if the record exists in the database.</span></span>  
  
3.  <span data-ttu-id="e24d4-151">如果该记录存在，SQL 适配器将使用该记录中的信息生成一条控制消息。</span><span class="sxs-lookup"><span data-stu-id="e24d4-151">If the record exists, the SQL adapter builds a control message, using information in the record.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e24d4-152">通过此种方式生成控制消息可确保无效控制消息无法启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="e24d4-152">Building the control message in this way ensures that the orchestration cannot be started by an invalid control message.</span></span>  
  
4.  <span data-ttu-id="e24d4-153">BatchControlMessageRecvLoc 接收位置接收控制消息后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会激活批处理业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="e24d4-153">The BatchControlMessageRecvLoc receive location receives the control message, and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] activates a batching orchestration instance.</span></span>  
  
## <a name="batch-components"></a><span data-ttu-id="e24d4-154">批组件</span><span class="sxs-lookup"><span data-stu-id="e24d4-154">Batch Components</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e24d4-155"> EDI 使用下列组件将 XML 事务集批处理成 EDI 交换：</span><span class="sxs-lookup"><span data-stu-id="e24d4-155"> EDI batches XML transaction sets into EDI interchanges using the following components:</span></span>  
  
-   <span data-ttu-id="e24d4-156">EDI 接收管道中的 BatchMarkerReceivePipelineComponent</span><span class="sxs-lookup"><span data-stu-id="e24d4-156">BatchMarkerReceivePipelineComponent in the EDI receive pipeline</span></span>  
  
-   <span data-ttu-id="e24d4-157">路由业务流程</span><span class="sxs-lookup"><span data-stu-id="e24d4-157">Routing Orchestration</span></span>  
  
-   <span data-ttu-id="e24d4-158">批处理业务流程</span><span class="sxs-lookup"><span data-stu-id="e24d4-158">Batching Orchestration</span></span>  
  
-   <span data-ttu-id="e24d4-159">升级批处理业务流程</span><span class="sxs-lookup"><span data-stu-id="e24d4-159">Upgrade Batching Orchestration</span></span>  
  
-   <span data-ttu-id="e24d4-160">BatchSuspend 业务流程</span><span class="sxs-lookup"><span data-stu-id="e24d4-160">BatchSuspend Orchestration</span></span>  
  
-   <span data-ttu-id="e24d4-161">EDI 发送管道</span><span class="sxs-lookup"><span data-stu-id="e24d4-161">EDI Send Pipeline</span></span>  
  
 <span data-ttu-id="e24d4-162">这些组件在您安装和配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI 及 AS2 时作为 DLL 安装。</span><span class="sxs-lookup"><span data-stu-id="e24d4-162">These components are installed as DLLs when you install and configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e24d4-163">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI 和 AS2 中的批处理组件无法保证批处理中事务集的排序。</span><span class="sxs-lookup"><span data-stu-id="e24d4-163">The batching components in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2 do not guarantee the ordering of the transaction sets in a batch.</span></span>  
  
### <a name="batchmarkerreceivepipelinecomponent"></a><span data-ttu-id="e24d4-164">BatchMarkerReceivePipelineComponent</span><span class="sxs-lookup"><span data-stu-id="e24d4-164">BatchMarkerReceivePipelineComponent</span></span>  
 <span data-ttu-id="e24d4-165">通过 EDI 接收管道中的 BatchMarkerReceivePipelineComponent，批处理业务流程可以提取要进行批处理的消息。</span><span class="sxs-lookup"><span data-stu-id="e24d4-165">BatchMarkerReceivePipelineComponent in the EDI receive pipeline enables the batching orchestration to pick up messages to be batched.</span></span> <span data-ttu-id="e24d4-166">应用 EDI 接收管道中的拆装器之后即可应用该管道组件。</span><span class="sxs-lookup"><span data-stu-id="e24d4-166">This pipeline component is applied after the Disassembler in the EDI Receive Pipeline.</span></span> <span data-ttu-id="e24d4-167">该组件的计算结果中设置的筛选器条件**筛选器**部分**批处理配置**的单向协议选项卡页**协议属性**对话框中，以及标记事务集具有处理的路由和批处理业务流程的以下上下文属性</span><span class="sxs-lookup"><span data-stu-id="e24d4-167">The component evaluates the filter criteria set in the **Filter** section of the **Batching Configuration** page of the one-way agreement tab of the **Agreement Properties** dialog box, and marks the transaction sets with the following context properties for processing by the routing and batching orchestrations</span></span>  
  
-   <span data-ttu-id="e24d4-168">如果只有一个参与方订阅要进行批处理的消息，则它会升级 `ToBeBatched = True`，并将 BatchId 设置为匹配批配置的批 ID 值。</span><span class="sxs-lookup"><span data-stu-id="e24d4-168">If a single party subscribes to a message to be batched, it promotes `ToBeBatched = True` and BatchId is set to the value of the batch ID of the matching batch configuration.</span></span> <span data-ttu-id="e24d4-169">这样，批处理业务流程即可进行提取。</span><span class="sxs-lookup"><span data-stu-id="e24d4-169">This enables pickup by the batching orchestration.</span></span>  
  
-   <span data-ttu-id="e24d4-170">如果多个批订阅要进行批处理的消息，则它会升级 `ToBeRouted = True`，并将 `EDI.BatchIds` 属性集设置为以空格分隔的批 ID 列表。</span><span class="sxs-lookup"><span data-stu-id="e24d4-170">If multiple batches subscribe to a message to be batched, it promotes `ToBeRouted = True`, and sets the `EDI.BatchIds` property set to a space-delimited list of batch IDs.</span></span> <span data-ttu-id="e24d4-171">这样，路由业务流程即可进行提取。</span><span class="sxs-lookup"><span data-stu-id="e24d4-171">This enables pickup by the routing orchestration.</span></span>  
  
-   <span data-ttu-id="e24d4-172">如果不存在任何订阅，则不会升级上下文属性。</span><span class="sxs-lookup"><span data-stu-id="e24d4-172">If no subscriptions exist, it does not promote a context property.</span></span> <span data-ttu-id="e24d4-173">这表示不会对事务集进行批处理。</span><span class="sxs-lookup"><span data-stu-id="e24d4-173">This indicates that the transaction set is not to be batched.</span></span>  
  
 <span data-ttu-id="e24d4-174">管道组件将忽略除 XML 和具有 `ReuseEnvelope` 属性的消息（保留批）之外的消息。</span><span class="sxs-lookup"><span data-stu-id="e24d4-174">The pipeline component ignores messages other than XML and messages with the `ReuseEnvelope` property (preserved batches).</span></span> <span data-ttu-id="e24d4-175">如果不对确认进行批处理，则管道组件将忽略确认类型的消息（CONTRL、TA1 和 997）。</span><span class="sxs-lookup"><span data-stu-id="e24d4-175">If acknowledgments are not to be batched, the pipeline component will ignore the ACK message types (CONTRL, TA1, and 997).</span></span> <span data-ttu-id="e24d4-176">若要优化路由和批处理业务流程的处理过程，BatchMarkerPipelineComponent 应将消息传递到 MessageBox（如果拆装器将消息上下文属性 `MessageDestination` 设置为“SuspendedQueue”）。</span><span class="sxs-lookup"><span data-stu-id="e24d4-176">To optimize processing of the routing and batching orchestrations, the BatchMarkerPipelineComponent passes the message through to the MessageBox if the message context property `MessageDestination` is set to "SuspendedQueue" by the disassembler.</span></span>  
  
 <span data-ttu-id="e24d4-177">如果您使用的是自定义管道，而不是 EDIReceive 管道，那么您可以在自定义管道中使用 BatchMarker 组件。</span><span class="sxs-lookup"><span data-stu-id="e24d4-177">If you are using a custom pipeline, rather than the EDIReceive pipeline, you can use the BatchMarker component in your custom pipeline.</span></span> <span data-ttu-id="e24d4-178">如果您使用的不是 EDIReceive 管道，并且要发布来自业务流程的消息，则必须将 `ToBeBatched = True` 和 `BatchID` 升级到其中一个组件中的活动批 ID。</span><span class="sxs-lookup"><span data-stu-id="e24d4-178">If you are not using the EDIReceive pipeline, and are publishing messages from an orchestration, you will have to promote `ToBeBatched = True` and `BatchID` to the ID of an active batch in one of your components.</span></span>  
  
### <a name="routing-orchestration"></a><span data-ttu-id="e24d4-179">路由业务流程</span><span class="sxs-lookup"><span data-stu-id="e24d4-179">Routing Orchestration</span></span>  
 <span data-ttu-id="e24d4-180">路由业务流程订阅任何具有以下特性的消息：上下文属性 `ToBeRouted = True`，并且上下文属性 `EDI.BatchIds` 设置为以空格分隔的批 ID 列表。</span><span class="sxs-lookup"><span data-stu-id="e24d4-180">The routing orchestration subscribes to any message with the context property `ToBeRouted = True` and the context property `EDI.BatchIds` set to a space-delimited list of batch IDs.</span></span> <span data-ttu-id="e24d4-181">当多个批处理筛选器订阅要进行批处理的消息时会出现此情况。</span><span class="sxs-lookup"><span data-stu-id="e24d4-181">This occurs when multiple batch filters subscribe to a message to be batched.</span></span> <span data-ttu-id="e24d4-182">路由业务流程将为 `EDI.BatchIds` 中包含的每个批 ID 生成此消息的一个副本，</span><span class="sxs-lookup"><span data-stu-id="e24d4-182">The routing orchestration will make a copy of the message for each batch ID contained in `EDI.BatchIds`.</span></span> <span data-ttu-id="e24d4-183">并使用以下两个新上下文属性标记每个副本：</span><span class="sxs-lookup"><span data-stu-id="e24d4-183">It stamps each copy with two new context properties:</span></span>  
  
-   <span data-ttu-id="e24d4-184">`EDI.BatchID`，将此属性设置为此消息要使用的批 ID。</span><span class="sxs-lookup"><span data-stu-id="e24d4-184">`EDI.BatchID`, which is set to the ID of the batch that this message is intended for.</span></span>  
  
-   <span data-ttu-id="e24d4-185">`EDI.ToBeBatched`，将此属性设置为 True。</span><span class="sxs-lookup"><span data-stu-id="e24d4-185">`EDI.ToBeBatched`, which is set to True.</span></span>  
  
 <span data-ttu-id="e24d4-186">然后再将副本路由到 MessageBox，以供批处理业务流程提取。</span><span class="sxs-lookup"><span data-stu-id="e24d4-186">It then routes the copies to the MessageBox to be picked up by the batching orchestration.</span></span> <span data-ttu-id="e24d4-187">每个目标批 ID 使用同一业务流程的单个实例，并在具体批 ID 上包含一个筛选器。</span><span class="sxs-lookup"><span data-stu-id="e24d4-187">Each destination batch ID use a singleton instance of the same orchestration, with a filter on the specific batch ID.</span></span>  
  
### <a name="batching-orchestration"></a><span data-ttu-id="e24d4-188">批处理业务流程</span><span class="sxs-lookup"><span data-stu-id="e24d4-188">Batching Orchestration</span></span>  
 <span data-ttu-id="e24d4-189">批处理业务流程是具有状态的服务，它在一段时间内缓冲批元素（事务集），将其组装为交换，然后再根据发布标准将交换发布到发送管道。</span><span class="sxs-lookup"><span data-stu-id="e24d4-189">The batching orchestration is a stateful service that buffers batch elements (transaction sets) over a period of time, assembles them into an interchange, and then releases the interchange to the send pipeline based upon the release criteria.</span></span>  
  
 <span data-ttu-id="e24d4-190">正在激活后，批处理的业务流程的实例可以启动对特定的编码类型到给定方的消息进行批处理 (如果**启动**日期时间已过)。</span><span class="sxs-lookup"><span data-stu-id="e24d4-190">After being activated, an instance of the batching orchestration can start batching messages of a particular encoding type to a given party (if the **Start** datetime has passed).</span></span> <span data-ttu-id="e24d4-191">在任何时候，每个参与方都可以有许多批处理业务流程实例，每个活动批配置有一个实例。</span><span class="sxs-lookup"><span data-stu-id="e24d4-191">At any one time there can be many instances of the batching orchestration for each party, one per active batch configuration.</span></span> <span data-ttu-id="e24d4-192">一个批处理业务流程实例可以为一个批配置发布多个批。</span><span class="sxs-lookup"><span data-stu-id="e24d4-192">A single instance of the batching orchestration can release multiple batches for a single  batch configuration.</span></span> <span data-ttu-id="e24d4-193">符合结束标准后，批处理业务流程实例将终止。</span><span class="sxs-lookup"><span data-stu-id="e24d4-193">After the end criteria is met, the batching orchestration instance will terminate.</span></span> <span data-ttu-id="e24d4-194">批处理的业务流程的新实例将需要手动从贸易合作伙伴管理 (TPM) 中创建使用**启动**按钮。</span><span class="sxs-lookup"><span data-stu-id="e24d4-194">A new instance of the batching orchestration will need to be created manually from the Trading Partner Management (TPM) using the **Start** button.</span></span>  
  
 <span data-ttu-id="e24d4-195">如果批处理业务流程将启动早于开始日期中所示的日期时间**激活**部分上的**批处理配置**的单向协议选项卡页**协议属性**对话框中，它将仅收到激活范围中指定的消息。</span><span class="sxs-lookup"><span data-stu-id="e24d4-195">If the batch orchestration starts before the start date time shown in the **Activation** section on the of the **Batching Configuration** page of the one-way agreement tab of the **Agreement Properties** dialog box, it will only receive messages that are specified in the activation range.</span></span> <span data-ttu-id="e24d4-196">而不会接收在此开始日期时间之前发送的消息。</span><span class="sxs-lookup"><span data-stu-id="e24d4-196">It will not receive messages sent before the start date time.</span></span>  
  
 <span data-ttu-id="e24d4-197">批处理业务流程可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e24d4-197">The batching orchestration does the following:</span></span>  
  
-   <span data-ttu-id="e24d4-198">订阅具有以下上下文属性的 XML 批元素：`EDI.ToBeBatched = True` 和 `EDI.BatchId` = 批配置 ID；或者 `EDI.ToBeBatched = True` 和 EDI.BatchName = 已配置批的名称，且 EDI.DestinationPartyName = 包含此批配置的参与方名称。</span><span class="sxs-lookup"><span data-stu-id="e24d4-198">Subscribes to XML batch elements with the context properties `EDI.ToBeBatched = True` and `EDI.BatchId` the ID of the batch configuration, or `EDI.ToBeBatched = True` and EDI.BatchName = the name of the configured batch and EDI.DestinationPartyName = the party name that contains the batch configuration.</span></span> <span data-ttu-id="e24d4-199">收到批处理元素使用**接收**操作在循环中的操作。</span><span class="sxs-lookup"><span data-stu-id="e24d4-199">It receives batch elements using a **Receive** action operation in a loop.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e24d4-200">批处理的业务流程不批处理事务集基于设置的筛选器部分中的筛选器条件**批处理配置**的单向协议选项卡页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="e24d4-200">The batching orchestration does not batch transaction sets based upon the filter criteria set in the Filter section of the **Batching Configuration** page of the one-way agreement tab of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="e24d4-201">该业务流程会订阅设置了上述上下文属性的事务集。</span><span class="sxs-lookup"><span data-stu-id="e24d4-201">It subscribes to transaction sets that have the above context properties set on them.</span></span> <span data-ttu-id="e24d4-202">BatchMarker 管道组件根据参与方属性中的筛选器设置来设置和升级这些上下文属性。</span><span class="sxs-lookup"><span data-stu-id="e24d4-202">The BatchMarker pipeline component sets and promotes those context properties based upon the filter settings in the party properties.</span></span>  
  
-   <span data-ttu-id="e24d4-203">为 `BatchId` 上下文属性中标识的参与方检索批处理的配置设置。</span><span class="sxs-lookup"><span data-stu-id="e24d4-203">Retrieves the batch configuration settings for the party identified in the `BatchId` context property.</span></span>  
  
-   <span data-ttu-id="e24d4-204">根据参与方设置验证批元素（事务集）。</span><span class="sxs-lookup"><span data-stu-id="e24d4-204">Validates the batch element (transaction set) based on party settings.</span></span>  
  
-   <span data-ttu-id="e24d4-205">如果批元素发生错误，则批处理业务流程将升级该事务集的以下属性： `EDI.BatchItemValidationFailure = True`。</span><span class="sxs-lookup"><span data-stu-id="e24d4-205">If there is an error in a batch element, the batching orchestration will promoted the following property on that transaction set: `EDI.BatchItemValidationFailure = True`.</span></span> <span data-ttu-id="e24d4-206">**BatchElementSuspend** orchestration 订阅为已提升此属性设置的任何事务。</span><span class="sxs-lookup"><span data-stu-id="e24d4-206">The **BatchElementSuspend** orchestration subscribes to any transaction set for which this property has been promoted.</span></span> <span data-ttu-id="e24d4-207">此业务流程将提供在批处理交换中遇到的第一个错误的详细错误信息。</span><span class="sxs-lookup"><span data-stu-id="e24d4-207">This orchestration will provide detailed error information for the first error encountered in batching the interchange.</span></span>  
  
-   <span data-ttu-id="e24d4-208">如果批元素中没有任何错误，则会保留对该批元素的引用。</span><span class="sxs-lookup"><span data-stu-id="e24d4-208">If there is no error in a batch element, holds a reference to that batch element.</span></span>  
  
-   <span data-ttu-id="e24d4-209">当接收到相应的控件消息或满足批处理版本条件时，将中断外**接收**操作循环，从消息框中，检索所有批处理元素和组装交换。</span><span class="sxs-lookup"><span data-stu-id="e24d4-209">When the appropriate control message is received or the batching release criteria is met, breaks out of the **Receive** action loop, retrieves all batch elements from the MessageBox, and assembles the interchange.</span></span>  
  
-   <span data-ttu-id="e24d4-210">对交换的上下文属性进行如下设置：`ToBeBatched = False`，且 DestinationPartyName = %PartyName%，其中 %PartyName% 是消息面向的参与方的名称。</span><span class="sxs-lookup"><span data-stu-id="e24d4-210">Sets the context property `ToBeBatched = False` for the interchange and the context property DestinationPartyName = %PartyName% where %PartyName% is the name of the party for which the message is intended.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e24d4-211">如果发送端口订阅属性 `EDI.ToBeBatched = False` 和 EDI.DestinationPartyName = %PartyName% 中的一个，或者同时订阅两个属性，该发送端口可提取批交换。</span><span class="sxs-lookup"><span data-stu-id="e24d4-211">If a send port subscribes to either or both of the properties `EDI.ToBeBatched = False` and EDI.DestinationPartyName = %PartyName%, that send port can pick up the batched interchange.</span></span> <span data-ttu-id="e24d4-212">请确保配置发送端口的筛选器，使该筛选器仅提取应提取的批交换。</span><span class="sxs-lookup"><span data-stu-id="e24d4-212">Make sure that a send port's filters are configured such that the send port picks up only those batched interchanges that it is intended to pick up.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e24d4-213">批处理业务流程放到 MessageBox 中的交换只将属性 `EDI.ToBeBatched = False`、EDI.DestinationPartyName = %PartyName% 和 EDI.BatchEncodingType = "X12" 或 "EDIFACT" 升级到上下文。</span><span class="sxs-lookup"><span data-stu-id="e24d4-213">Interchanges dropped by the batching orchestration into the MessageBox have only the properties `EDI.ToBeBatched = False`, EDI.DestinationPartyName = %PartyName%, and EDI.BatchEncodingType = "X12" or "EDIFACT" promoted to the context.</span></span> <span data-ttu-id="e24d4-214">原始事务集的所有上下文属性将丢失。</span><span class="sxs-lookup"><span data-stu-id="e24d4-214">All context properties from the original transaction sets are lost.</span></span>  
  
-   <span data-ttu-id="e24d4-215">对于 X12 编码的交换，请向信封应用下列属性：</span><span class="sxs-lookup"><span data-stu-id="e24d4-215">For an X12-encoded interchange, applies the following properties to the envelope:</span></span>  
  
    -   <span data-ttu-id="e24d4-216">ISA6：交换发送方 ID</span><span class="sxs-lookup"><span data-stu-id="e24d4-216">ISA6: Interchange Sender ID</span></span>  
  
    -   <span data-ttu-id="e24d4-217">ISA8：交换接收方 ID</span><span class="sxs-lookup"><span data-stu-id="e24d4-217">ISA8: Interchange Receiver ID</span></span>  
  
    -   <span data-ttu-id="e24d4-218">ISA15：用法指示符</span><span class="sxs-lookup"><span data-stu-id="e24d4-218">ISA15: Usage indicator</span></span>  
  
    -   <span data-ttu-id="e24d4-219">ISA_Blob（写入到上下文）</span><span class="sxs-lookup"><span data-stu-id="e24d4-219">ISA_Blob (written to context)</span></span>  
  
-   <span data-ttu-id="e24d4-220">对于 EDIFACT 编码的交换，请向信封应用下列属性：</span><span class="sxs-lookup"><span data-stu-id="e24d4-220">For an EDIFACT-encoded interchange, applies the following properties to the envelope:</span></span>  
  
    -   <span data-ttu-id="e24d4-221">UNB2.1：交换发送方 ID</span><span class="sxs-lookup"><span data-stu-id="e24d4-221">UNB2.1: Interchange Sender ID</span></span>  
  
    -   <span data-ttu-id="e24d4-222">UNB3.1：交换接收方 ID</span><span class="sxs-lookup"><span data-stu-id="e24d4-222">UNB3.1: Interchange Recipient ID</span></span>  
  
    -   <span data-ttu-id="e24d4-223">UNB2.3：反向路由的地址</span><span class="sxs-lookup"><span data-stu-id="e24d4-223">UNB2.3: Address for Reverse Routing</span></span>  
  
    -   <span data-ttu-id="e24d4-224">UNB11：用法指示符</span><span class="sxs-lookup"><span data-stu-id="e24d4-224">UNB11: Usage indicator</span></span>  
  
    -   <span data-ttu-id="e24d4-225">UNA_Blob（写入到上下文）</span><span class="sxs-lookup"><span data-stu-id="e24d4-225">UNA_Blob (written to context)</span></span>  
  
    -   <span data-ttu-id="e24d4-226">UNB_Blob（写入到上下文）</span><span class="sxs-lookup"><span data-stu-id="e24d4-226">UNB_Blob (written to context)</span></span>  
  
-   <span data-ttu-id="e24d4-227">将批交换传送给 MessageBox，以供 EDI 发送管道提取。</span><span class="sxs-lookup"><span data-stu-id="e24d4-227">Delivers the batched interchange to the MessageBox for pickup by the EDI send pipeline.</span></span>  
  
### <a name="upgradebatching-orchestration"></a><span data-ttu-id="e24d4-228">UpgradeBatching 业务流程</span><span class="sxs-lookup"><span data-stu-id="e24d4-228">UpgradeBatching Orchestration</span></span>  
 <span data-ttu-id="e24d4-229">UpgradeBatching 业务流程处理 `EDI.ToBeBatched` 属性设置为 True，但是没有设置 `EDI.BatchID` 属性的消息。</span><span class="sxs-lookup"><span data-stu-id="e24d4-229">The UpgradeBatching orchestration handles messages that are have the `EDI.ToBeBatched` property set to true, but do not have the `EDI.BatchID` property set.</span></span>  
  
 <span data-ttu-id="e24d4-230">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的早期版本中，每个参与方只能有一个批配置。</span><span class="sxs-lookup"><span data-stu-id="e24d4-230">In previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], each party could have only one batch configuration.</span></span>  <span data-ttu-id="e24d4-231">当处理 `EDI.ToBeBatched` 设置为 True 的消息时，`EDI.DestinationPartyId` 用于确定参与方，然后从协议属性读取批配置。</span><span class="sxs-lookup"><span data-stu-id="e24d4-231">When processing messages that had `EDI.ToBeBatched` set to true, the `EDI.DestinationPartyId` was used to determine the party and then the batch configuration was read from the agreement properties.</span></span>  
  
 <span data-ttu-id="e24d4-232">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，每个参与方可以有多个关联的批配置，因此 `EDI.DestinationPartyId` 不会提供足够的信息用于确定应该使用哪个批配置。</span><span class="sxs-lookup"><span data-stu-id="e24d4-232">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], each party can have multiple batch configurations associated with it, so the `EDI.DestinationPartyId` does not provide enough information to determine which batch configuration should be used.</span></span>  <span data-ttu-id="e24d4-233">当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 收到消息时，`EDI.BatchId` 属性将用于识别处理消息时具体应该使用哪个批配置。</span><span class="sxs-lookup"><span data-stu-id="e24d4-233">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives messages, the `EDI.BatchId` property is used to identify which specific batch configuration should be used when processing a message.</span></span>  
  
 <span data-ttu-id="e24d4-234">升级到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 以后，您仍然有使用 `EDI.DestinationPartyId` 属性指定参与方配置的自定义管道。</span><span class="sxs-lookup"><span data-stu-id="e24d4-234">After upgrading to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you may still have custom pipelines that use the `EDI.DestinationPartyId` property to specify the party configuration.</span></span> <span data-ttu-id="e24d4-235">当收到将 `EDI.ToBeBatched` 设置为 True 的消息，且设置了 `EDI.DestinationPartyID` 而不是 EDI.BatchID 时，UpgradeBatching 业务流程会尝试确定应该使用哪个批配置。</span><span class="sxs-lookup"><span data-stu-id="e24d4-235">When a message is received that has `EDI.ToBeBatched` set to true, and has `EDI.DestinationPartyID` set instead of EDI.BatchID, the UpgradeBatching orchestration attempts to determine which batch configuration should be used.</span></span>  
  
 <span data-ttu-id="e24d4-236">UpgradeBatching 业务流程使用以下订阅筛选器来订阅标记为批处理，但未指定批 ID 的文档：</span><span class="sxs-lookup"><span data-stu-id="e24d4-236">The UpgradeBatching orchestration uses the following subscription filters to subscribe to documents that are marked for batching, but do not specify a batch ID:</span></span>  
  
-   `EDI.ToBeBatched=True`  
  
-   <span data-ttu-id="e24d4-237">`EDI.EncodingType` exists</span><span class="sxs-lookup"><span data-stu-id="e24d4-237">`EDI.EncodingType` exists</span></span>  
  
-   <span data-ttu-id="e24d4-238">`EDI.DestinationPartyId` exists</span><span class="sxs-lookup"><span data-stu-id="e24d4-238">`EDI.DestinationPartyId` exists</span></span>  
  
 <span data-ttu-id="e24d4-239">当业务流程收到消息时，它会尝试使用参与方名称和编码类型为此消息查找匹配的批设置。</span><span class="sxs-lookup"><span data-stu-id="e24d4-239">When the orchestration receives a message, it will try to find a matching batch configuration for the message by using the party name and encoding type.</span></span>  <span data-ttu-id="e24d4-240">`EDI.DestinationPartyID`属性用于确定当事方名称，并随后业务流程查找相匹配的批处理名称\<PartyName\>+\<EncodingType\>+ 默认。</span><span class="sxs-lookup"><span data-stu-id="e24d4-240">The `EDI.DestinationPartyID` property is used to determine the party name, and then the orchestration looks for a batch name that matches \<PartyName\>+\<EncodingType\>+Default.</span></span>  <span data-ttu-id="e24d4-241">例如，如果参与方名称为 Contoso，且 `EDI.EncodingType` 的值为 X12，则业务流程将查找名为 ContosoX12Default 的批。</span><span class="sxs-lookup"><span data-stu-id="e24d4-241">For example if the party name is Contoso, and the value of `EDI.EncodingType` is X12, then the orchestration will look for a batch named ContosoX12Default.</span></span>  
  
 <span data-ttu-id="e24d4-242">如果找到匹配的批配置，则会将此消息以及下列属性放回消息框：</span><span class="sxs-lookup"><span data-stu-id="e24d4-242">If a matching batch configuration is found, the message is placed back in the message box with the following properties:</span></span>  
  
-   `EDI.ToBeBatched = True`  
  
-   `EDI.ToBeRouted = False`  
  
-   <span data-ttu-id="e24d4-243">EDI.BatchId = 匹配批的批 ID</span><span class="sxs-lookup"><span data-stu-id="e24d4-243">EDI.BatchId = the batch ID for the matching batch</span></span>  
  
 <span data-ttu-id="e24d4-244">然后，批处理业务流程将处理该消息</span><span class="sxs-lookup"><span data-stu-id="e24d4-244">The batching orchestration will then process the message</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e24d4-245">如果没有找到匹配的批，则会出现以下情况：</span><span class="sxs-lookup"><span data-stu-id="e24d4-245">If no matching batch is found, then the following will happen:</span></span>  
>   
>  -   <span data-ttu-id="e24d4-246">不会将此消息发送给 BatchSuspend 业务流程。</span><span class="sxs-lookup"><span data-stu-id="e24d4-246">The message will not be sent to the BatchSuspend orchestration.</span></span>  
> -   <span data-ttu-id="e24d4-247">UpgradeBatching 业务流程实例和消息将被挂起。</span><span class="sxs-lookup"><span data-stu-id="e24d4-247">The UpgradeBatching orchestration instance and message will be suspended.</span></span>  
> -   <span data-ttu-id="e24d4-248">事件日志中将记录一个错误，说明找不到批。</span><span class="sxs-lookup"><span data-stu-id="e24d4-248">An error will be logged to the event log stating that a batch was not found.</span></span>  
  
### <a name="batchsuspend-orchestration"></a><span data-ttu-id="e24d4-249">BatchSuspend 业务流程</span><span class="sxs-lookup"><span data-stu-id="e24d4-249">BatchSuspend Orchestration</span></span>  
 <span data-ttu-id="e24d4-250">BatchSuspend 业务流程处理批处理业务流程收到的无效消息。</span><span class="sxs-lookup"><span data-stu-id="e24d4-250">The BatchSuspend orchestration handles invalid messages received by the batching orchestration.</span></span> <span data-ttu-id="e24d4-251">需要 BatchSuspend 业务流程的原因是：无法在不停止执行业务流程实例的情况下直接挂起业务流程（在本示例中为批处理业务流程）中的消息。</span><span class="sxs-lookup"><span data-stu-id="e24d4-251">The BatchSuspend orchestration is needed because there is no direct way to suspend a message from an orchestration (in this case, the batching orchestration) without stopping the execution of the instance of the orchestration.</span></span>  
  
 <span data-ttu-id="e24d4-252">当批处理业务流程实例收到消息时，会尝试验证该消息。</span><span class="sxs-lookup"><span data-stu-id="e24d4-252">When an instance of the batching orchestration receives a message, it attempts to validate it.</span></span> <span data-ttu-id="e24d4-253">如果消息验证失败，批处理业务流程将创建一个 BatchSuspend 业务流程实例，并将 `EDI.BatchItemValidationFailure` 上下文属性设置为 True。</span><span class="sxs-lookup"><span data-stu-id="e24d4-253">If the message fails validation, the batching orchestration creates an instance of the BatchSuspend orchestration, and sets the `EDI.BatchItemValidationFailure` context property to True.</span></span> <span data-ttu-id="e24d4-254">BatchSuspend 业务流程订阅该上下文属性设置为 True 的所有消息。</span><span class="sxs-lookup"><span data-stu-id="e24d4-254">The BatchSuspend orchestration subscribes to all messages with that context property set to True.</span></span> <span data-ttu-id="e24d4-255">在将无效事务集路由到 BatchSuspend 业务流程后，BatchSuspend 业务流程实例将挂起。</span><span class="sxs-lookup"><span data-stu-id="e24d4-255">After the invalid transaction set is routed to the BatchSuspend orchestration, the BatchSuspend orchestration instance is suspended.</span></span>  
  
 <span data-ttu-id="e24d4-256">此 BatchSuspend 业务流程将提供遇到的第一个错误的详细错误信息。</span><span class="sxs-lookup"><span data-stu-id="e24d4-256">Detailed error information for the first error encountered is provided by the BatchSuspend orchestration.</span></span>  
  
 <span data-ttu-id="e24d4-257">您可以创建自定义业务流程，使用筛选器中的 `EDI.BatchElementValidationFailure` 属性处理未通过批处理业务流程验证的事务集。</span><span class="sxs-lookup"><span data-stu-id="e24d4-257">You can create a custom orchestration to handle transaction sets that fail validation by the batching orchestration, by using the `EDI.BatchElementValidationFailure` property in a filter.</span></span>  
  
### <a name="edi-send-pipeline"></a><span data-ttu-id="e24d4-258">EDI 发送管道</span><span class="sxs-lookup"><span data-stu-id="e24d4-258">EDI Send Pipeline</span></span>  
 <span data-ttu-id="e24d4-259">从批处理业务流程收到批交换后，EDI 发送管道将执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e24d4-259">After receiving a batched interchange from the batching orchestration, the EDI send pipeline does the following:</span></span>  
  
-   <span data-ttu-id="e24d4-260">对于 X12 编码的交换，发送管道会向信封应用下列属性：</span><span class="sxs-lookup"><span data-stu-id="e24d4-260">For an X12-encoded interchange, the send pipeline applies the following properties to the envelope:</span></span>  
  
    -   <span data-ttu-id="e24d4-261">ISA2：授权信息</span><span class="sxs-lookup"><span data-stu-id="e24d4-261">ISA2: Authorization Information</span></span>  
  
    -   <span data-ttu-id="e24d4-262">ISA4：安全信息</span><span class="sxs-lookup"><span data-stu-id="e24d4-262">ISA4: Security Information</span></span>  
  
    -   <span data-ttu-id="e24d4-263">ISA9：交换日期</span><span class="sxs-lookup"><span data-stu-id="e24d4-263">ISA9: Interchange Date</span></span>  
  
    -   <span data-ttu-id="e24d4-264">ISA10：交换时间</span><span class="sxs-lookup"><span data-stu-id="e24d4-264">ISA10: Interchange Time</span></span>  
  
    -   <span data-ttu-id="e24d4-265">ISA13：交换控制编号</span><span class="sxs-lookup"><span data-stu-id="e24d4-265">ISA13: Interchange Control Number</span></span>  
  
    -   <span data-ttu-id="e24d4-266">GS4：日期</span><span class="sxs-lookup"><span data-stu-id="e24d4-266">GS4: Date</span></span>  
  
    -   <span data-ttu-id="e24d4-267">GS5：时间</span><span class="sxs-lookup"><span data-stu-id="e24d4-267">GS5: Time</span></span>  
  
    -   <span data-ttu-id="e24d4-268">GS6：组控制编号</span><span class="sxs-lookup"><span data-stu-id="e24d4-268">GS6: Group Control Number</span></span>  
  
    -   <span data-ttu-id="e24d4-269">ST2：事务集控制编号</span><span class="sxs-lookup"><span data-stu-id="e24d4-269">ST2: Transaction Set Control Number</span></span>  
  
-   <span data-ttu-id="e24d4-270">对于 EDIFACT 编码的交换，发送管道会向信封应用下列属性：</span><span class="sxs-lookup"><span data-stu-id="e24d4-270">For an EDIFACT-encoded interchange, the send pipeline applies the following properties to the envelope:</span></span>  
  
    -   <span data-ttu-id="e24d4-271">UNB4.1：日期</span><span class="sxs-lookup"><span data-stu-id="e24d4-271">UNB4.1: Date</span></span>  
  
    -   <span data-ttu-id="e24d4-272">UNB4.2：时间</span><span class="sxs-lookup"><span data-stu-id="e24d4-272">UNB4.2: Time</span></span>  
  
    -   <span data-ttu-id="e24d4-273">UNB5：交换控制参考</span><span class="sxs-lookup"><span data-stu-id="e24d4-273">UNB5: Interchange Control Reference</span></span>  
  
    -   <span data-ttu-id="e24d4-274">UNB6.1：收件人引用密码</span><span class="sxs-lookup"><span data-stu-id="e24d4-274">UNB6.1: Recipient Reference Password</span></span>  
  
    -   <span data-ttu-id="e24d4-275">UNG4.1：日期</span><span class="sxs-lookup"><span data-stu-id="e24d4-275">UNG4.1: Date</span></span>  
  
    -   <span data-ttu-id="e24d4-276">UNG4.2：时间</span><span class="sxs-lookup"><span data-stu-id="e24d4-276">UNG4.2: Time</span></span>  
  
    -   <span data-ttu-id="e24d4-277">UNG5：功能组参考</span><span class="sxs-lookup"><span data-stu-id="e24d4-277">UNG5: Functional Group Reference</span></span>  
  
    -   <span data-ttu-id="e24d4-278">UNG8：应用程序密码</span><span class="sxs-lookup"><span data-stu-id="e24d4-278">UNG8: Application Password</span></span>  
  
-   <span data-ttu-id="e24d4-279">通过关联适配器传送消息</span><span class="sxs-lookup"><span data-stu-id="e24d4-279">Delivers the message via the associated adapter</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e24d4-280">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e24d4-280">See Also</span></span>  
 [<span data-ttu-id="e24d4-281">对传出 EDI 消息进行批处理</span><span class="sxs-lookup"><span data-stu-id="e24d4-281">Batching Outgoing EDI Messages</span></span>](../core/batching-outgoing-edi-messages.md)