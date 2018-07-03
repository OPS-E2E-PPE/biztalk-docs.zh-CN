---
title: FRR 业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, promoted properties
- orchestrations, message subscriptions
- promoted properties, messages
- FRR, orchestrations
- subscriptions, messages
- orchestrations, reconciliation time-out
- messages, message/response correlation
- message/response correlation
- promoted properties, FIN Response Reconciliation
- orchestrations, FRR
- outbound messages
- FIN Response Reconciliation, promoted properties
- direct bindings
- reconciliation time-out
- bindings, direct
- messages, subscriptions
- subscriptions, orchestrations
- messages, outbound
- MessageBox database
ms.assetid: ea8d31c2-ac3b-44ac-8064-d008da4f7f72
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ad5d9dd1b582aefa9a440508650ecd0e653dbfe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998368"
---
# <a name="frr-orchestration"></a><span data-ttu-id="568f0-102">FRR 业务流程</span><span class="sxs-lookup"><span data-stu-id="568f0-102">FRR Orchestration</span></span>
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="568f0-103"> 实现 FRR 通过 FRR 业务流程。</span><span class="sxs-lookup"><span data-stu-id="568f0-103"> implements FRR through the FRR orchestration.</span></span> <span data-ttu-id="568f0-104">业务流程可确定的 FIN 响应的令牌相关的匹配原始消息的消息 ID。</span><span class="sxs-lookup"><span data-stu-id="568f0-104">The orchestration determines whether the Correlation Token of the FIN response matches the message ID of the original message.</span></span> <span data-ttu-id="568f0-105">与执行向 SAA，发送消息的发送端口的发送功能和执行的从 SAA 接收消息的接收位置的接收函数，它处理并行中的消息。</span><span class="sxs-lookup"><span data-stu-id="568f0-105">It processes the message in parallel with the send functions performed by the send port that sends the message to SAA, and with the receive functions performed by the receive location that receives the message from SAA.</span></span>  
  
 <span data-ttu-id="568f0-106">最高级别的业务流程实例将执行以下处理操作：</span><span class="sxs-lookup"><span data-stu-id="568f0-106">At the highest level, an instance of the orchestration does the following processing:</span></span>  
  
1. <span data-ttu-id="568f0-107">缓存原始出站消息的副本绑定 SAA 通过 MessageBox 上进行侦听。</span><span class="sxs-lookup"><span data-stu-id="568f0-107">Caches a copy of the original outbound message bound for SAA by listening on the MessageBox.</span></span>  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="568f0-108"> 创建业务流程的实例时[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]将原始消息路由到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="568f0-108"> creates an instance of the orchestration when [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] routes the original message to the MessageBox.</span></span>  
  
2. <span data-ttu-id="568f0-109">等待[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]发布到 MessageBox SAA FIN 响应。</span><span class="sxs-lookup"><span data-stu-id="568f0-109">Waits for [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to publish a FIN response from SAA to the MessageBox.</span></span>  
  
3. <span data-ttu-id="568f0-110">集的已提升属性的具体的性质 FIN 响应取决于原始消息的副本。</span><span class="sxs-lookup"><span data-stu-id="568f0-110">Sets promoted properties of the copy of the original message depending upon the nature of the FIN response.</span></span>  
  
4. <span data-ttu-id="568f0-111">将原始消息的副本发布回 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="568f0-111">Publishes the copy of the original message back to the MessageBox.</span></span> <span data-ttu-id="568f0-112">自定义处理程序然后可以订阅以，检索，并处理所需的消息。</span><span class="sxs-lookup"><span data-stu-id="568f0-112">Custom handlers can then subscribe to, retrieve, and handle the message as required.</span></span>  
  
## <a name="subscription-to-outbound-messages"></a><span data-ttu-id="568f0-113">出站消息的订阅</span><span class="sxs-lookup"><span data-stu-id="568f0-113">Subscription to Outbound Messages</span></span>  
 <span data-ttu-id="568f0-114">FRR 业务流程直接绑定到 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="568f0-114">The FRR orchestration is directly bound to the MessageBox.</span></span> <span data-ttu-id="568f0-115">FRR 业务流程订阅的所有出站消息绑定的 SWIFT 网络不包含验证错误，通过订阅到以下属性：</span><span class="sxs-lookup"><span data-stu-id="568f0-115">The FRR orchestration subscribes to all outbound messages bound for the SWIFT network that do not contain validation errors, by subscribing to the following properties:</span></span>  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="568f0-116">_Failed （所设置的 SWIFT 反汇编程序验证过程） = = false</span><span class="sxs-lookup"><span data-stu-id="568f0-116">_Failed==False (as set by the SWIFT Disassembler validation process)</span></span>  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="568f0-117">_Swiftbound （所设置的 SWIFT 反汇编程序配置过程） = = true</span><span class="sxs-lookup"><span data-stu-id="568f0-117">_Swiftbound==True (as set by the SWIFT Disassembler configuration process)</span></span>  
  
## <a name="messageresponse-correlation"></a><span data-ttu-id="568f0-118">消息/响应相关</span><span class="sxs-lookup"><span data-stu-id="568f0-118">Message/Response Correlation</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="568f0-119"> 关联到入站 FIN 响应消息原始的出站 FIN 消息通过比较以下属性：</span><span class="sxs-lookup"><span data-stu-id="568f0-119"> correlates the original outbound FIN message to the inbound FIN response message by comparing the following properties:</span></span>  
  
- <span data-ttu-id="568f0-120">FIN 响应 MQMD_CorrelID 上下文属性</span><span class="sxs-lookup"><span data-stu-id="568f0-120">The MQMD_CorrelID context property of the FIN response</span></span>  
  
- <span data-ttu-id="568f0-121">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRCorrelationToken 出站的 MTXYY 消息属性。</span><span class="sxs-lookup"><span data-stu-id="568f0-121">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRCorrelationToken property of the outbound MTXYY message.</span></span> <span data-ttu-id="568f0-122">接收管道的参与方解析阶段升级此属性。</span><span class="sxs-lookup"><span data-stu-id="568f0-122">This property is promoted by the party-resolution stage of the receive pipeline.</span></span>  
  
  <span data-ttu-id="568f0-123">这些属性的值必须相同。</span><span class="sxs-lookup"><span data-stu-id="568f0-123">The values of these properties must be identical.</span></span> <span data-ttu-id="568f0-124">SWIFT 将传出消息的 MQMD_MsgID 属性设置为的值绑定的消息的发送管道的编码器阶段[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRCorrelationToken 属性。</span><span class="sxs-lookup"><span data-stu-id="568f0-124">The encoder stage of the send pipeline for messages bound for SWIFT sets the MQMD_MsgID property of the outgoing message to the value of the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRCorrelationToken property.</span></span> <span data-ttu-id="568f0-125">SAA 将响应消息的 MQMD_CorrelID 属性设置为的 MQMD_MsgID 值。</span><span class="sxs-lookup"><span data-stu-id="568f0-125">SAA sets the MQMD_CorrelID property of the response message to the value of MQMD_MsgID.</span></span>  
  
## <a name="setting-of-promoted-properties"></a><span data-ttu-id="568f0-126">设置的已提升属性</span><span class="sxs-lookup"><span data-stu-id="568f0-126">Setting of Promoted Properties</span></span>  
 <span data-ttu-id="568f0-127">在接收 FIN 响应和关联到原始消息的副本之后, FRR 业务流程将根据响应的性质，原始消息的副本的以下升级的属性：</span><span class="sxs-lookup"><span data-stu-id="568f0-127">After receiving a FIN response and correlating it to the copy of the original message, the FRR orchestration sets the following promoted properties of the copy of the original message according to the nature of the response:</span></span>  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="568f0-128">为 true; 如果响应是 ACK 或 False，如果响应已发送 NAK _FRRFailed</span><span class="sxs-lookup"><span data-stu-id="568f0-128">_FRRFailed to True if the response was an ACK or False if the response was a NAK</span></span>  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="568f0-129">为以下值，如果响应已发送 NAK _FRRFailedReason:</span><span class="sxs-lookup"><span data-stu-id="568f0-129">_FRRFailedReason to the one of the following values, if the response was a NAK:</span></span>  
  
  -   <span data-ttu-id="568f0-130">*\<ErrorCode\>*  （从 MTS21_FIN_ACKNAK 否定确认消息的 405 字段）</span><span class="sxs-lookup"><span data-stu-id="568f0-130">*\<ErrorCode\>* (from the 405 field of the MTS21_FIN_ACKNAK negative-acknowledgment message)</span></span>  
  
  -   <span data-ttu-id="568f0-131">TransportError （从 MQ 系列平移/NAN 消息）</span><span class="sxs-lookup"><span data-stu-id="568f0-131">TransportError (from an MQ Series PAN/NAN message)</span></span>  
  
  -   <span data-ttu-id="568f0-132">DelayedNAK （从 MT015 (DNK) 消息）</span><span class="sxs-lookup"><span data-stu-id="568f0-132">DelayedNAK (from an MT015 (DNK) message)</span></span>  
  
  -   <span data-ttu-id="568f0-133">AbortReceived (从 MT019 （中止通知） 消息)</span><span class="sxs-lookup"><span data-stu-id="568f0-133">AbortReceived (from an MT019 (Abort Notification) message)</span></span>  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="568f0-134">为 TimedOut _FRRFailedReason 如果[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]超时期限内未收到响应。</span><span class="sxs-lookup"><span data-stu-id="568f0-134">_FRRFailedReason to TimedOut if [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] did not receive a response within the timeout period.</span></span> <span data-ttu-id="568f0-135">有关 FRR 延迟超时的详细信息，请参阅下面的"对帐超时"部分或[设置 FRR 延迟超时](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md)。</span><span class="sxs-lookup"><span data-stu-id="568f0-135">For more information about the FRR Delay Time-out, see the "Reconciliation Time-Out" section below or [Setting the FRR Delay Time-Out](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md).</span></span>  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="568f0-136">到 _SendingServiceType [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span><span class="sxs-lookup"><span data-stu-id="568f0-136">_SendingServiceType to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span></span>  
  
- <span data-ttu-id="568f0-137">BTS。消息响应的类型相对应的值的操作。</span><span class="sxs-lookup"><span data-stu-id="568f0-137">BTS.Operation to the value corresponding to the type of message response.</span></span> <span data-ttu-id="568f0-138">有关详细信息，请参阅[为发送到自定义处理程序创建 FRR 发送端口](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)。</span><span class="sxs-lookup"><span data-stu-id="568f0-138">For more information, see [Creating the FRR Send Ports for Sending to the Custom Handlers](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).</span></span>  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="568f0-139">_FrrSendTransport MQ 系列平移/NAN 消息 (MQ Series 传输级 ACK/NAK)</span><span class="sxs-lookup"><span data-stu-id="568f0-139">_FrrSendTransport for an MQ Series PAN/NAN message (MQ Series transport-level ACK/NAK)</span></span>  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="568f0-140">_FrrSend010NDW MT010 消息 （非传递警告）</span><span class="sxs-lookup"><span data-stu-id="568f0-140">_FrrSend010NDW for an MT010 message (Non-Delivery Warning)</span></span>  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="568f0-141">_FrrSend011Delivered MT011 消息 （送达通知）</span><span class="sxs-lookup"><span data-stu-id="568f0-141">_FrrSend011Delivered for an MT011 message (Delivery Notification)</span></span>  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="568f0-142">_FrrSend012SenderACK MT012 消息 （发件人通知）</span><span class="sxs-lookup"><span data-stu-id="568f0-142">_FrrSend012SenderACK for an MT012 message (Sender Notification)</span></span>  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="568f0-143">_FrrSend015DNK MT015 消息 （DNK 或延迟 NAK）</span><span class="sxs-lookup"><span data-stu-id="568f0-143">_FrrSend015DNK for an MT015 message (DNK, or Delayed NAK)</span></span>  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="568f0-144">_FrrSend019Abort MT019 消息 （中止通知）</span><span class="sxs-lookup"><span data-stu-id="568f0-144">_FrrSend019Abort for an MT019 message (Abort Notification)</span></span>  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="568f0-145">_FrrSendS21ACK MTS21_FIN_ACKNAK 确认消息 (ACK 的发送 T 的 FIN 消息)</span><span class="sxs-lookup"><span data-stu-id="568f0-145">_FrrSendS21ACK for an MTS21_FIN_ACKNAK acknowledgment message (ACK of a FIN message sent by an LT)</span></span>  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="568f0-146">_FrrSendS21NAK MTS21_FIN_ACKNAK 否定确认消息 (NAK LT 发送 FIN 消息)</span><span class="sxs-lookup"><span data-stu-id="568f0-146">_FrrSendS21NAK for an MTS21_FIN_ACKNAK negative-acknowledgment message (NAK of a FIN message sent by an LT)</span></span>  
  
## <a name="direct-binding"></a><span data-ttu-id="568f0-147">直接绑定</span><span class="sxs-lookup"><span data-stu-id="568f0-147">Direct Binding</span></span>  
 <span data-ttu-id="568f0-148">接收输入的业务流程定义的业务流程利用到 MessageBox 的订阅。</span><span class="sxs-lookup"><span data-stu-id="568f0-148">Receive inputs for the orchestration are defined by subscriptions that the orchestration makes to the MessageBox.</span></span> <span data-ttu-id="568f0-149">上下文属性和值提升业务流程定义业务流程将发布到 MessageBox 的消息的发送输出。</span><span class="sxs-lookup"><span data-stu-id="568f0-149">Context properties and values promoted by the orchestration define the send outputs for a message that the orchestration publishes to the MessageBox.</span></span> <span data-ttu-id="568f0-150">由于此直接绑定到 MessageBox 中，就会从以下分离业务流程：</span><span class="sxs-lookup"><span data-stu-id="568f0-150">Because of this direct binding to the MessageBox, the orchestration is decoupled from the following:</span></span>  
  
- <span data-ttu-id="568f0-151">物理接收位置接收来自后端应用程序路由到 SAA 的出站消息</span><span class="sxs-lookup"><span data-stu-id="568f0-151">The physical receive locations that receive outbound messages from the back-end application for routing to SAA</span></span>  
  
- <span data-ttu-id="568f0-152">发送端口发送出站 FIN 消息从[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]到 SWIFT 联盟访问 (SAA)</span><span class="sxs-lookup"><span data-stu-id="568f0-152">The send ports that send outbound FIN messages from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to the SWIFT Alliance Access (SAA)</span></span>  
  
- <span data-ttu-id="568f0-153">从 SAA 接收传入 FIN 响应消息的接收位置</span><span class="sxs-lookup"><span data-stu-id="568f0-153">The receive locations that receive incoming FIN response messages from SAA</span></span>  
  
- <span data-ttu-id="568f0-154">FIN 响应通过 SAA 的存入其中物理 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="568f0-154">The physical MQSeries queues where FIN responses are deposited by SAA</span></span>  
  
## <a name="reconciliation-time-out"></a><span data-ttu-id="568f0-155">对帐超时</span><span class="sxs-lookup"><span data-stu-id="568f0-155">Reconciliation Time-Out</span></span>  
 <span data-ttu-id="568f0-156">当[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]创建 FRR 业务流程，该业务流程启动时将等待 FIN 响应的新实例。</span><span class="sxs-lookup"><span data-stu-id="568f0-156">When [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] creates a new instance of the FRR orchestration, the orchestration starts waiting for FIN responses.</span></span> <span data-ttu-id="568f0-157">在运行时，必须配置某些时间段后超时的业务流程，以便它将不响应无限期等待。</span><span class="sxs-lookup"><span data-stu-id="568f0-157">At run time, you must configure the orchestration to time out after some duration, so that it will not wait for the response indefinitely.</span></span> <span data-ttu-id="568f0-158">FRR 业务流程时超时持续时间到期，将升级[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRFailedReason 属性并将其设置为 TimedOut。</span><span class="sxs-lookup"><span data-stu-id="568f0-158">When the time-out duration expires, the FRR orchestration promotes the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRFailedReason property and sets it to TimedOut.</span></span> <span data-ttu-id="568f0-159">然后，将发出消息发布到 MessageBox，并终止。</span><span class="sxs-lookup"><span data-stu-id="568f0-159">It then publishes messages out to the MessageBox, and terminates.</span></span> <span data-ttu-id="568f0-160">如果超时，相关性 ID 是消失了。</span><span class="sxs-lookup"><span data-stu-id="568f0-160">If you time out, the correlation ID is gone.</span></span>  
  
 <span data-ttu-id="568f0-161">可以创建一个自定义处理程序来处理超时消息 （原始出站消息的副本）。</span><span class="sxs-lookup"><span data-stu-id="568f0-161">You can create a custom handler to process timed-out messages (the copy of the original outbound message).</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="568f0-162"> 实现此任务使用侦听形状在业务流程中。</span><span class="sxs-lookup"><span data-stu-id="568f0-162"> would accomplish this by using a Listen shape in the orchestration.</span></span> <span data-ttu-id="568f0-163">有关详细信息，请参阅[设置 FRR 延迟超时](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md)。</span><span class="sxs-lookup"><span data-stu-id="568f0-163">For more information, see [Setting the FRR Delay Time-Out](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md).</span></span>