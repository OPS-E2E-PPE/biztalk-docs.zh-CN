---
title: MLLP 接收适配器处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MLLP-encoded messages, receive adapters
- MLLP adapters, send adapters
- receive adapters
ms.assetid: 03c9a5f6-6f23-454f-8bab-e7c7b6057efa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbb5932d65bce2b17ebfca3645b8c755549b9a9c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968134"
---
# <a name="mllp-receive-adapter-processing"></a><span data-ttu-id="331c5-102">MLLP 接收适配器处理</span><span class="sxs-lookup"><span data-stu-id="331c5-102">MLLP Receive Adapter Processing</span></span>
<span data-ttu-id="331c5-103">最小的较低层协议 (MLLP) 接收适配器支持这两个单向和双向请求响应模式。</span><span class="sxs-lookup"><span data-stu-id="331c5-103">The Minimal Lower Layer Protocol (MLLP) receive adapter supports both one-way and two-way request response modes.</span></span> <span data-ttu-id="331c5-104">适配器侦听和接受连接。</span><span class="sxs-lookup"><span data-stu-id="331c5-104">The adapter listens and accepts connections.</span></span>  
  
 <span data-ttu-id="331c5-105">当 MLLP 接收适配器在双向模式下运行，适配器将不接收新消息从连接直到管道都生成确认 (ACK) 前面的消息。</span><span class="sxs-lookup"><span data-stu-id="331c5-105">When the MLLP receive adapter operates in two-way mode, the adapter will not receive a new message from the connection until the pipeline has generated the acknowledgment (ACK) for the previous message.</span></span>  
  
## <a name="configuration-parameters"></a><span data-ttu-id="331c5-106">配置参数</span><span class="sxs-lookup"><span data-stu-id="331c5-106">Configuration Parameters</span></span>  
 <span data-ttu-id="331c5-107">接收处理程序的参数进行配置的 BizTalk 主机级别，并将应用于与之关联的所有 MLLP 接收位置。</span><span class="sxs-lookup"><span data-stu-id="331c5-107">The parameters for a receive handler are configured at the BizTalk Host level, and apply to all MLLP receive locations associated with it.</span></span>  
  
|<span data-ttu-id="331c5-108">参数</span><span class="sxs-lookup"><span data-stu-id="331c5-108">Parameter</span></span>|<span data-ttu-id="331c5-109">改用</span><span class="sxs-lookup"><span data-stu-id="331c5-109">Use</span></span>|  
|---------------|---------|  
|<span data-ttu-id="331c5-110">*最大接受连接限制*</span><span class="sxs-lookup"><span data-stu-id="331c5-110">*Max Accept Connection Limit*</span></span>|<span data-ttu-id="331c5-111">限制并发接收适配器将接受的打开连接数。</span><span class="sxs-lookup"><span data-stu-id="331c5-111">Limits the number of concurrent open connections that the receive adapter will accept.</span></span>|  
  
## <a name="acknowledgments-with-the-two-way-mllp-receive-adapter"></a><span data-ttu-id="331c5-112">确认与双向 MLLP 接收适配器</span><span class="sxs-lookup"><span data-stu-id="331c5-112">Acknowledgments with the two-way MLLP receive adapter</span></span>  
 <span data-ttu-id="331c5-113">当双向 MLLP 接收适配器接收消息时，Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 可以生成以下类型的确认：</span><span class="sxs-lookup"><span data-stu-id="331c5-113">When a two-way MLLP receive adapter receives a message, Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) can generate the following types of ACKs:</span></span>  
  
- <span data-ttu-id="331c5-114">HL7 增强提交确认： 在此方案中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]同一个连接上发送了提交确认。</span><span class="sxs-lookup"><span data-stu-id="331c5-114">HL7 Enhanced Commit ACK: In this scenario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends a Commit ACK on the same connection.</span></span> <span data-ttu-id="331c5-115">它会发送出不同的发送端口上应用程序接受确认。</span><span class="sxs-lookup"><span data-stu-id="331c5-115">It sends out an Application Accept ACK on a different send port.</span></span>  
  
- <span data-ttu-id="331c5-116">应用程序接受确认： 在此方案中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]同一个连接上发送应用程序接受确认。</span><span class="sxs-lookup"><span data-stu-id="331c5-116">Application Accept ACK: In this scenario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends an Application Accept ACK on the same connection.</span></span>  
  
- <span data-ttu-id="331c5-117">静态确认： 在此方案中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]同一个连接上发送确认。</span><span class="sxs-lookup"><span data-stu-id="331c5-117">Static ACK: In this scenario, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends an ACK on the same connection.</span></span>  
  
- <span data-ttu-id="331c5-118">生成的确认类型取决于[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]发送消息的参与方的配置资源管理器设置。</span><span class="sxs-lookup"><span data-stu-id="331c5-118">The type of ACK generated depends on the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer settings for the party sending the message.</span></span> <span data-ttu-id="331c5-119">字段 MSH 15 和 16 个的单个消息中的值来覆盖此设置。</span><span class="sxs-lookup"><span data-stu-id="331c5-119">The value in fields MSH 15 and 16 of an individual message can override this setting.</span></span> <span data-ttu-id="331c5-120">但是，对于应用程序应为静态 Ack，可以仅将配置设置通过[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="331c5-120">However, for applications expecting Static ACKs, the configuration can only be set through [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
## <a name="error-conditions"></a><span data-ttu-id="331c5-121">错误条件</span><span class="sxs-lookup"><span data-stu-id="331c5-121">Error Conditions</span></span>  
 <span data-ttu-id="331c5-122">当出现错误条件或处于非活动状态时，会发生以下事件：</span><span class="sxs-lookup"><span data-stu-id="331c5-122">The following events occur when there is an error condition or inactivity:</span></span>  
  
- <span data-ttu-id="331c5-123">如果禁用该接收位置或[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]关闭，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="331c5-123">If the receive location is disabled or [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] shuts down, the following occurs:</span></span>  
  
  - <span data-ttu-id="331c5-124">接收位置将不再接受新连接。</span><span class="sxs-lookup"><span data-stu-id="331c5-124">The receive location will no longer accept new connections.</span></span>  
  
  - <span data-ttu-id="331c5-125">对于现有连接，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]完全接收当前消息，然后关闭连接。</span><span class="sxs-lookup"><span data-stu-id="331c5-125">For existing connections, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] completely receives the current message, and then closes the connection.</span></span>  
  
- <span data-ttu-id="331c5-126">检测到处于非活动状态时 （无指定的超时内接收位置上接收有效负载数据），适配器将关闭连接。</span><span class="sxs-lookup"><span data-stu-id="331c5-126">When inactivity is detected (no payload data received on the receive location within the specified timeout), the adapter closes the connection.</span></span>  
  
- <span data-ttu-id="331c5-127">如果[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]收到不完整消息时，接收到的部分被挂起。</span><span class="sxs-lookup"><span data-stu-id="331c5-127">If [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] receives an incomplete message, the portion received is suspended.</span></span> <span data-ttu-id="331c5-128">接收一条消息 （在之前 EB/CR 和 SB 的下一条消息之间的新连接上第一个 SB) 之外的所有字节数将被忽略。</span><span class="sxs-lookup"><span data-stu-id="331c5-128">All bytes received outside of a message (before the first SB on a new connection, between EB/CR and SB of the next message) are ignored.</span></span>  
  
- <span data-ttu-id="331c5-129">如果管道无法分析该消息，消息仍传送到 MessageBox 数据库，使用提升的属性**ParseError = true**。</span><span class="sxs-lookup"><span data-stu-id="331c5-129">If the pipeline fails to parse the message, the message is still delivered to the MessageBox database, with a promoted property **ParseError=true**.</span></span>  
  
- <span data-ttu-id="331c5-130">如果一条消息失败由于没有订阅，或由于在标题中，结构化错误[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]挂起该消息以其原始的"在线"形式 （之前正在分析）。</span><span class="sxs-lookup"><span data-stu-id="331c5-130">If a message fails due to the absence of a subscription, or due to structural errors in the header, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] suspends the message in its original "wire" form (prior to being parsed).</span></span> <span data-ttu-id="331c5-131">未将任何订阅失败的常见原因是缺少的升级的属性。</span><span class="sxs-lookup"><span data-stu-id="331c5-131">A frequent reason for the no-subscription failure is the lack of promoted properties.</span></span> <span data-ttu-id="331c5-132">由于[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]挂起未分析的消息**BTS。MessageType**将为空白。</span><span class="sxs-lookup"><span data-stu-id="331c5-132">Since [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] suspends the unparsed message, the **BTS.MessageType** will be blank.</span></span>  
  
  <span data-ttu-id="331c5-133">下表列出了 MLLP 接收适配器返回的错误。</span><span class="sxs-lookup"><span data-stu-id="331c5-133">The following table lists the errors that the MLLP receive adapter returns.</span></span>  
  
|            <span data-ttu-id="331c5-134">事件</span><span class="sxs-lookup"><span data-stu-id="331c5-134">Event</span></span>             |  <span data-ttu-id="331c5-135">ID</span><span class="sxs-lookup"><span data-stu-id="331c5-135">ID</span></span>  |                                                                                                          <span data-ttu-id="331c5-136">错误条件</span><span class="sxs-lookup"><span data-stu-id="331c5-136">Error Condition</span></span>                                                                                                           |
|------------------------------|------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      <span data-ttu-id="331c5-137">**ErrorListening**</span><span class="sxs-lookup"><span data-stu-id="331c5-137">**ErrorListening**</span></span>      | <span data-ttu-id="331c5-138">8448</span><span class="sxs-lookup"><span data-stu-id="331c5-138">8448</span></span> |                                                   <span data-ttu-id="331c5-139">无法绑定到本地套接字 （很可能某些其他本地应用程序使用相同的 IP 地址/端口 ID 组合）。</span><span class="sxs-lookup"><span data-stu-id="331c5-139">Could not bind to a local socket (most likely some other local application is using the same IP address/port ID combination).</span></span>                                                    |
| <span data-ttu-id="331c5-140">**ErrorAcceptingConnection**</span><span class="sxs-lookup"><span data-stu-id="331c5-140">**ErrorAcceptingConnection**</span></span> | <span data-ttu-id="331c5-141">8449</span><span class="sxs-lookup"><span data-stu-id="331c5-141">8449</span></span> | <span data-ttu-id="331c5-142">无法建立与远程方的 TCP 连接。</span><span class="sxs-lookup"><span data-stu-id="331c5-142">Could not establish a TCP connection with the remote party.</span></span> <span data-ttu-id="331c5-143">任一[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]达到最大连接限制，或者资源不足。</span><span class="sxs-lookup"><span data-stu-id="331c5-143">Either [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] reached the maximum connection limit, or the resources were insufficient.</span></span> |
|  <span data-ttu-id="331c5-144">**ErrorSubmittingMessage**</span><span class="sxs-lookup"><span data-stu-id="331c5-144">**ErrorSubmittingMessage**</span></span>  | <span data-ttu-id="331c5-145">8452</span><span class="sxs-lookup"><span data-stu-id="331c5-145">8452</span></span> |                   <span data-ttu-id="331c5-146">MessageBox 数据库不能接受该消息。</span><span class="sxs-lookup"><span data-stu-id="331c5-146">The MessageBox database could not accept the message.</span></span> <span data-ttu-id="331c5-147">任一[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]不可用或资源不足。</span><span class="sxs-lookup"><span data-stu-id="331c5-147">Either [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] was unavailable or the resources were insufficient.</span></span>                   |
|     <span data-ttu-id="331c5-148">**ErrorSendingAck**</span><span class="sxs-lookup"><span data-stu-id="331c5-148">**ErrorSendingAck**</span></span>      | <span data-ttu-id="331c5-149">8454</span><span class="sxs-lookup"><span data-stu-id="331c5-149">8454</span></span> |                                [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="331c5-150"> 由于连接不可用，无法返回确认。</span><span class="sxs-lookup"><span data-stu-id="331c5-150"> could not return the acknowledgment because the connection was not available.</span></span>                                 |
  
## <a name="performance-counters"></a><span data-ttu-id="331c5-151">性能计数器</span><span class="sxs-lookup"><span data-stu-id="331c5-151">Performance Counters</span></span>  
 <span data-ttu-id="331c5-152">下表列出了 MLLP 适配器使用的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="331c5-152">The following table lists the performance counters that the MLLP adapter uses.</span></span>  
  
|<span data-ttu-id="331c5-153">计数器</span><span class="sxs-lookup"><span data-stu-id="331c5-153">Counter</span></span>|<span data-ttu-id="331c5-154">含义</span><span class="sxs-lookup"><span data-stu-id="331c5-154">Meaning</span></span>|  
|-------------|-------------|  
|<span data-ttu-id="331c5-155">字节</span><span class="sxs-lookup"><span data-stu-id="331c5-155">Bytes</span></span>|<span data-ttu-id="331c5-156">已接收或发送的所有文档的有效负载的大小。</span><span class="sxs-lookup"><span data-stu-id="331c5-156">Size of the payload of all documents received or sent.</span></span>|  
|<span data-ttu-id="331c5-157">字节数/秒</span><span class="sxs-lookup"><span data-stu-id="331c5-157">Bytes/sec</span></span>|<span data-ttu-id="331c5-158">已接收或发送的负载的当前吞吐量。</span><span class="sxs-lookup"><span data-stu-id="331c5-158">Current throughput of the payload received or sent.</span></span>|  
|<span data-ttu-id="331c5-159">Documents processed</span><span class="sxs-lookup"><span data-stu-id="331c5-159">Documents processed</span></span>|<span data-ttu-id="331c5-160">**MLLP 接收**:</span><span class="sxs-lookup"><span data-stu-id="331c5-160">**MLLP Receive**:</span></span><br /><br /> <span data-ttu-id="331c5-161">已成功传递到 MessageBox 数据库的文档数。</span><span class="sxs-lookup"><span data-stu-id="331c5-161">Number of documents successfully delivered to the MessageBox database.</span></span><br /><br /> <span data-ttu-id="331c5-162">**MLLP 发送**:</span><span class="sxs-lookup"><span data-stu-id="331c5-162">**MLLP Send**:</span></span><br /><br /> <span data-ttu-id="331c5-163">已成功传递到远程应用程序的文档数。</span><span class="sxs-lookup"><span data-stu-id="331c5-163">Number of documents successfully delivered to the remote application.</span></span>|  
|<span data-ttu-id="331c5-164">失败的文档</span><span class="sxs-lookup"><span data-stu-id="331c5-164">Documents failed</span></span>|<span data-ttu-id="331c5-165">**MLLP 接收**:</span><span class="sxs-lookup"><span data-stu-id="331c5-165">**MLLP Receive**:</span></span><br /><br /> <span data-ttu-id="331c5-166">未成功传送到 MessageBox 数据库的文档数。</span><span class="sxs-lookup"><span data-stu-id="331c5-166">Number of documents not successfully delivered to the MessageBox database.</span></span><br /><br /> <span data-ttu-id="331c5-167">**MLLP 发送**:</span><span class="sxs-lookup"><span data-stu-id="331c5-167">**MLLP Send**:</span></span><br /><br /> <span data-ttu-id="331c5-168">未成功传递到远程应用程序的文档数。</span><span class="sxs-lookup"><span data-stu-id="331c5-168">Number of documents not successfully delivered to the remote application.</span></span>|  
|<span data-ttu-id="331c5-169">连接状态</span><span class="sxs-lookup"><span data-stu-id="331c5-169">Connection status</span></span>|<span data-ttu-id="331c5-170">连接的适配器，状态 1 或 0 (1 = 连接)。</span><span class="sxs-lookup"><span data-stu-id="331c5-170">The status of the adapter connection, 1 or 0 (1=connected).</span></span>|  
  
 <span data-ttu-id="331c5-171">性能计数器实例使用以下命名方案：</span><span class="sxs-lookup"><span data-stu-id="331c5-171">The performance counter instances use the following naming scheme:</span></span>  
  
```  
{recv|trans} : connection name : remote IP address : remote port ID  
```  
  
 <span data-ttu-id="331c5-172">MLLP 接收适配器将使用"接收"前缀和 MLLP 发送适配器将使用"事务"。</span><span class="sxs-lookup"><span data-stu-id="331c5-172">Where the MLLP receive adapter uses the "recv" prefix, and the MLLP send adapter uses "trans".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="331c5-173">用于确认由发送接收端口 （例如，在双向模式下运行的适配器） 和发送端口 （操作系统相同的套接字连接上接收的确认） 不计。</span><span class="sxs-lookup"><span data-stu-id="331c5-173">ACKs sent by receive ports (for example, an adapter operating in a two-way mode) and send ports (operating to receive ACKs on the same socket connection) are not counted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="331c5-174">请参阅</span><span class="sxs-lookup"><span data-stu-id="331c5-174">See Also</span></span>  
 <span data-ttu-id="331c5-175">[处理用 MLLP 编码的消息](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md) </span><span class="sxs-lookup"><span data-stu-id="331c5-175">[Processing MLLP-encoded Messages](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md) </span></span>  
 <span data-ttu-id="331c5-176">[配置参数，以便进行发送和接收适配器](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="331c5-176">[Configuration Parameters for Send and Receive Adapters](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md) </span></span>  
 <span data-ttu-id="331c5-177">[MLLP 发送适配器处理](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md) </span><span class="sxs-lookup"><span data-stu-id="331c5-177">[MLLP Send Adapter Processing](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md) </span></span>  
 [<span data-ttu-id="331c5-178">设置用于接收 ACK 的发送端口</span><span class="sxs-lookup"><span data-stu-id="331c5-178">Setting Up a Send Port for Receiving ACKs</span></span>](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)