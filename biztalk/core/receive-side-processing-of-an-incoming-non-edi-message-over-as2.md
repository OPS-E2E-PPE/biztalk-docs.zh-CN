---
title: 接收方处理通过 AS2 传入的非 EDI 消息的 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fee10cba-8b1a-4d2c-b9d9-efbb74c3f461
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9d37479d66001eb073cb29a47b1fb8f56b0af8f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398194"
---
# <a name="receive-side-processing-of-an-incoming-non-edi-message-over-as2"></a><span data-ttu-id="f608d-102">通过 AS2 传入的非 EDI 消息的接收方处理</span><span class="sxs-lookup"><span data-stu-id="f608d-102">Receive-Side Processing of an Incoming Non-EDI Message over AS2</span></span>
<span data-ttu-id="f608d-103">AS2 管道附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可用于处理通过 AS2 传输发送的 EDI 消息或非 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="f608d-103">The AS2 pipelines shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can be used to process an EDI message or a non-EDI message over AS2 transport.</span></span> <span data-ttu-id="f608d-104">不同的管道用于两个不同类型的有效负载。</span><span class="sxs-lookup"><span data-stu-id="f608d-104">Different pipelines are used for the two different types of payloads.</span></span> <span data-ttu-id="f608d-105">使用 AS2EdiReceive 管道处理通过 AS2 传入的 EDI 消息和 AS2Send 管道返回关联的 MDN （如果已启用）。</span><span class="sxs-lookup"><span data-stu-id="f608d-105">You use the AS2EdiReceive pipeline to process an incoming EDI message over AS2, and the AS2Send pipeline to return the associated MDN (if enabled).</span></span> <span data-ttu-id="f608d-106">使用 AS2Receive 管道处理通过 AS2 传入的非 EDI 消息和 AS2Send 管道返回关联的 MDN （如果已启用）。</span><span class="sxs-lookup"><span data-stu-id="f608d-106">You use the AS2Receive pipeline to process an incoming non-EDI message over AS2, and the AS2Send pipeline to return the associated MDN (if enabled).</span></span> <span data-ttu-id="f608d-107">非 EDI 消息可以是任何二进制负载。</span><span class="sxs-lookup"><span data-stu-id="f608d-107">The non-EDI message can be any binary payload.</span></span>  
  
 <span data-ttu-id="f608d-108">AS2Receive 接收管道对 AS2 消息进行解码，然后对 AS2 消息执行拆装。</span><span class="sxs-lookup"><span data-stu-id="f608d-108">The AS2Receive receive pipeline decodes the AS2 message, and then performs disassembly on the AS2 message.</span></span> <span data-ttu-id="f608d-109">AS2Send 发送管道对 MDN 进行编码。</span><span class="sxs-lookup"><span data-stu-id="f608d-109">An AS2Send send pipeline encodes the MDN.</span></span> <span data-ttu-id="f608d-110">可以包括 AS2Receive 和 AS2Send 管道在一个 HTTP 双向要求响应发送端口 （如果 MDN 是同步的），或在一个单向 HTTP 发送端口和一个单向 HTTP 接收端口 （如果 MDN 是异步的）。</span><span class="sxs-lookup"><span data-stu-id="f608d-110">You can include the AS2Receive and AS2Send pipelines in an HTTP two-way solicit response send port (if the MDN is synchronous), or in a one-way HTTP send port and a one-way HTTP receive port (if the MDN is asynchronous).</span></span> <span data-ttu-id="f608d-111">如果需要执行的非 EDI 负载的反汇编，您将必须执行该操作在另一个接收管道中，因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在接收管道中仅允许一个拆装器。</span><span class="sxs-lookup"><span data-stu-id="f608d-111">If you need to perform disassembly of a non-EDI payload, you will have to do that in another receive pipeline, because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] only allows one disassembler in a receive pipeline.</span></span> <span data-ttu-id="f608d-112">这将需要环回发送端口和接收位置 (请参阅[处理接收非 EDI 负载](../core/receive-side-processing-of-an-incoming-non-edi-message-over-as2.md#BKMK_NonEDI)下面一节)。</span><span class="sxs-lookup"><span data-stu-id="f608d-112">This will require a loopback send port and receive location (see the [Processing the Received Non-EDI Payload](../core/receive-side-processing-of-an-incoming-non-edi-message-over-as2.md#BKMK_NonEDI) section below).</span></span>  
  
 <span data-ttu-id="f608d-113">若要通过 AS2 接收非 EDI 交换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f608d-113">To receive a non-EDI interchange over AS2, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will perform the following steps:</span></span>  
  
-   <span data-ttu-id="f608d-114">处理所接收的 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="f608d-114">Processing the received AS2 message</span></span>  
  
-   <span data-ttu-id="f608d-115">发送一个 MDN</span><span class="sxs-lookup"><span data-stu-id="f608d-115">Sending an MDN</span></span>  
  
-   <span data-ttu-id="f608d-116">处理收到的非 EDI 负载</span><span class="sxs-lookup"><span data-stu-id="f608d-116">Processing the received non-EDI payload</span></span>  
  
## <a name="processing-the-received-as2-message"></a><span data-ttu-id="f608d-117">处理收到的 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="f608d-117">Processing the Received AS2 message</span></span>  
 <span data-ttu-id="f608d-118">AS2 解码器在 AS2Receive 接收管道处理传入的 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="f608d-118">The AS2 Decoder in the AS2Receive receive pipeline processes an incoming AS2 message.</span></span> <span data-ttu-id="f608d-119">它是通过使用`InboundHTTPHeaders`HTTP 适配器创建 AS2 消息中的 HTTP 标头上下文属性。</span><span class="sxs-lookup"><span data-stu-id="f608d-119">It does so using the `InboundHTTPHeaders` context property, which the HTTP adapter creates from the HTTP headers in the AS2 message.</span></span> <span data-ttu-id="f608d-120">这些标头包括下列 AS2 标头：</span><span class="sxs-lookup"><span data-stu-id="f608d-120">These headers include the following AS2 headers:</span></span>  
  
- <span data-ttu-id="f608d-121">AS2-To</span><span class="sxs-lookup"><span data-stu-id="f608d-121">AS2-To</span></span>  
  
- <span data-ttu-id="f608d-122">AS2-从</span><span class="sxs-lookup"><span data-stu-id="f608d-122">AS2-From</span></span>  
  
- <span data-ttu-id="f608d-123">AS2 版本</span><span class="sxs-lookup"><span data-stu-id="f608d-123">AS2-Version</span></span>  
  
- <span data-ttu-id="f608d-124">MessageID</span><span class="sxs-lookup"><span data-stu-id="f608d-124">MessageID</span></span>  
  
- <span data-ttu-id="f608d-125">OriginalMessageID (仅限 Mdn)</span><span class="sxs-lookup"><span data-stu-id="f608d-125">OriginalMessageID (for MDNs only)</span></span>  
  
- <span data-ttu-id="f608d-126">处理设置-通知-向 （如果请求一个 MDN）</span><span class="sxs-lookup"><span data-stu-id="f608d-126">Disposition-Notification-To (if an MDN is requested)</span></span>  
  
- <span data-ttu-id="f608d-127">回执送达选项 （如果请求一个 MDN）</span><span class="sxs-lookup"><span data-stu-id="f608d-127">Receipt-Delivery-Option (if an MDN is requested)</span></span>  
  
- <span data-ttu-id="f608d-128">签名的回执-MICalg （如果请求一个 MDN）</span><span class="sxs-lookup"><span data-stu-id="f608d-128">Signed-Receipt-MICalg (if an MDN is requested)</span></span>  
  
  <span data-ttu-id="f608d-129">AS2 解码器将升级到消息上下文的这些标头。</span><span class="sxs-lookup"><span data-stu-id="f608d-129">The AS2 Decoder will promote these headers to the context of the message.</span></span> <span data-ttu-id="f608d-130">它然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f608d-130">It then does the following:</span></span>  
  
- <span data-ttu-id="f608d-131">执行协议解析，以确定要用来处理传入的消息的属性。</span><span class="sxs-lookup"><span data-stu-id="f608d-131">Performs agreement resolution to determine the properties to be used to process the incoming message.</span></span> <span data-ttu-id="f608d-132">有关详细信息，请参阅[传入 AS2 消息的协议解析](../core/agreement-resolution-for-incoming-as2-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="f608d-132">For more information, see [Agreement Resolution for Incoming AS2 Messages](../core/agreement-resolution-for-incoming-as2-messages.md).</span></span>  
  
- <span data-ttu-id="f608d-133">使用 AS2 发送方进行身份验证-从和 AS2 的属性。</span><span class="sxs-lookup"><span data-stu-id="f608d-133">Authenticates the sender using the AS2-From and AS2-To properties.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="f608d-134">AS2 接收管道处理的详细信息执行对传入的 AS2 消息，请参阅[处理传入 AS2 消息](../core/processing-an-incoming-as2-message.md)。</span><span class="sxs-lookup"><span data-stu-id="f608d-134">For more information about the processing that the AS2 receive pipelines perform on incoming AS2 messages, see [Processing an Incoming AS2 Message](../core/processing-an-incoming-as2-message.md).</span></span>  
  
## <a name="sending-an-mdn"></a><span data-ttu-id="f608d-135">发送一个 MDN</span><span class="sxs-lookup"><span data-stu-id="f608d-135">Sending an MDN</span></span>  
 <span data-ttu-id="f608d-136">如果已启用 MDN，则 AS2Receive 管道生成 MDN 并将其放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="f608d-136">If an MDN was enabled, the AS2Receive pipeline generates an MDN and drops it into the MessageBox.</span></span> <span data-ttu-id="f608d-137">MDN 返回到原始消息的发件人的方式取决于 AS2 传输是同步还是异步。</span><span class="sxs-lookup"><span data-stu-id="f608d-137">How the MDN is returned to the sender of the original message depends upon whether the AS2 transport is synchronous or asynchronous.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f608d-138">对传出 Mdn 执行有关 AS2 接收管道处理的详细信息，请参阅[生成传出 MDN](../core/generating-an-outgoing-mdn.md)。</span><span class="sxs-lookup"><span data-stu-id="f608d-138">For more information about the processing that the AS2 receive pipelines perform on outgoing MDNs, see [Generating an Outgoing MDN](../core/generating-an-outgoing-mdn.md).</span></span>  
  
 <span data-ttu-id="f608d-139">**同步模式**</span><span class="sxs-lookup"><span data-stu-id="f608d-139">**Synchronous Mode**</span></span>  
  
 <span data-ttu-id="f608d-140">如果在同步模式下，通过 AS2 发送非 EDI 消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将通过该同步连接返回 MDN，然后关闭该连接。</span><span class="sxs-lookup"><span data-stu-id="f608d-140">If a non-EDI message is sent over AS2 in synchronous mode, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will return the MDN over that synchronous connection and then close the connection.</span></span> <span data-ttu-id="f608d-141">MDN 将由 AS2Receive 管道生成的、 由该管道路由到 MessageBox，然后自动提取请求的一部分的 AS2Send 管道响应接收端口。</span><span class="sxs-lookup"><span data-stu-id="f608d-141">The MDN will be generated by the AS2Receive pipeline, routed by that pipeline to the MessageBox, and then automatically picked up by the AS2Send pipeline that is part of the request response receive port.</span></span>  
  
 <span data-ttu-id="f608d-142">**异步模式**</span><span class="sxs-lookup"><span data-stu-id="f608d-142">**Asynchronous Mode**</span></span>  
  
 <span data-ttu-id="f608d-143">如果非 EDI 消息通过 HTTP/HTTPS 传输以异步模式发送的您必须创建发送端口以单独返回 MDN。</span><span class="sxs-lookup"><span data-stu-id="f608d-143">If a non-EDI message is sent over HTTP/HTTPS transport in asynchronous mode, you must create a send port to return the MDN separately.</span></span> <span data-ttu-id="f608d-144">如果它是一个动态发送端口，它将使用消息标头中的回执送达通知行中的地址将消息路由到贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="f608d-144">If it is a dynamic send port, it will use the address in the Receipt-Delivery-Notification line in the header of the message to route the message to the trading partner.</span></span> <span data-ttu-id="f608d-145">如果它是一个静态发送端口，它将使用在端口属性中定义的地址。</span><span class="sxs-lookup"><span data-stu-id="f608d-145">If it is a static send port, it will use the address defined in port properties.</span></span> <span data-ttu-id="f608d-146">此发送端口使用订阅异步 MDN`EdiIntAS.IsAS2AsynchronousMDN==True`筛选表达式。</span><span class="sxs-lookup"><span data-stu-id="f608d-146">This send port subscribes to the asynchronous MDN by using an `EdiIntAS.IsAS2AsynchronousMDN==True` filter expression.</span></span> <span data-ttu-id="f608d-147">在异步处理中，AS2Receive 管道将生成在 MDN 之外还 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="f608d-147">In asynchronous processing, the AS2Receive pipeline will generate an HTTP response in addition to the MDN.</span></span> <span data-ttu-id="f608d-148">接收端口接收端口和发送方，这会关闭该连接之间通过 HTTP 连接返回到原始发送方的 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="f608d-148">The receive port returns the HTTP response to the original sender over the HTTP connection between the receive port and the sending party, which closes that connection.</span></span> <span data-ttu-id="f608d-149">这是必需的因为 MDN 不会关闭同步连接。</span><span class="sxs-lookup"><span data-stu-id="f608d-149">This is necessary because the synchronous connection is not closed by the MDN.</span></span>  
  
##  <a name="BKMK_NonEDI"></a> <span data-ttu-id="f608d-150">处理收到的非 EDI 负载</span><span class="sxs-lookup"><span data-stu-id="f608d-150">Processing the Received Non-EDI Payload</span></span>  
 <span data-ttu-id="f608d-151">当未以 EDI 编码的消息接收通过 AS2，并且需要对负载执行拆装时，必须在 AS2Receive 管道以外的其他接收管道在执行该操作。</span><span class="sxs-lookup"><span data-stu-id="f608d-151">When a message that is not encoded in EDI is received over AS2, and you need to perform disassembly on the payload, you will have to do that in a different receive pipeline than the AS2Receive pipeline.</span></span> <span data-ttu-id="f608d-152">这是必需的因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在接收管道中仅允许一个拆装器。</span><span class="sxs-lookup"><span data-stu-id="f608d-152">This is required because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] only allows one disassembler in a receive pipeline.</span></span> <span data-ttu-id="f608d-153">这种情况下将需要环回机制使用的发送端口和接收位置。</span><span class="sxs-lookup"><span data-stu-id="f608d-153">This scenario will require a loopback mechanism using a send port and receive location.</span></span> <span data-ttu-id="f608d-154">在第一个阶段中，EDIReceive 管道处理 AS2 消息，并将消息以其本机格式发送到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="f608d-154">In the first pass, the EDIReceive pipeline processes the AS2 message and sends the message in its native format to the MessageBox.</span></span> <span data-ttu-id="f608d-155">在第二个阶段中，接收管道生成的 XML 消息的本机格式。</span><span class="sxs-lookup"><span data-stu-id="f608d-155">In the second pass, a receive pipeline generates XML from the message's native format.</span></span>  
  
 <span data-ttu-id="f608d-156">BizTalk Server 将执行以下接收端处理通过 AS2 BizTalk Server 上的非 EDI 消息：</span><span class="sxs-lookup"><span data-stu-id="f608d-156">BizTalk Server will perform the following receive-side processing on a non-EDI message over AS2 BizTalk Server:</span></span>  
  
-   <span data-ttu-id="f608d-157">AS2Receive 接收管道关联与双向请求响应接收位置分析从非 EDI 消息的 AS2 标头，然后将非 EDI 消息路由到 BizTalk MessageBox。</span><span class="sxs-lookup"><span data-stu-id="f608d-157">The AS2Receive receive pipeline associated with the two-way request response receive location parses the AS2 headers from the non-EDI message, and then routes the non-EDI message to the BizTalk MessageBox.</span></span>  
  
-   <span data-ttu-id="f608d-158">环回发送端口 （FILE 或 MSMQ） 中提取该非 EDI 消息从 MessageBox，因为它依据 BizTalk 属性筛选`IsAS2PayloadMessage == True`。</span><span class="sxs-lookup"><span data-stu-id="f608d-158">A loopback send port (either FILE or MSMQ) picks the non-EDI message up from the MessageBox, because it filters on the BizTalk property `IsAS2PayloadMessage == True`.</span></span> <span data-ttu-id="f608d-159">与此发送端口关联的 PassThruTransmit 发送管道以非 EDI 格式，该消息路由到一个文件夹或一个 MSMQ 队列将消息传递。</span><span class="sxs-lookup"><span data-stu-id="f608d-159">The PassThruTransmit send pipeline associated with this send port passes the message through in its non-EDI format, routing the message to either a folder or an MSMQ queue.</span></span>  
  
-   <span data-ttu-id="f608d-160">环回接收位置从其中提取消息。</span><span class="sxs-lookup"><span data-stu-id="f608d-160">A loopback receive location picks up the message.</span></span> <span data-ttu-id="f608d-161">与环回接收位置关联的接收管道生成的 XML 消息从非 EDI 消息，并将其路由到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="f608d-161">The receive pipeline associated with the loopback receive location generates an XML message from the non-EDI message, and routes it to the MessageBox.</span></span>  
  
-   <span data-ttu-id="f608d-162">如果该消息将路由到后端应用程序，发送端口提取 XML 消息，并将其路由到该应用程序。</span><span class="sxs-lookup"><span data-stu-id="f608d-162">If the message is to be routed to a back-end application, a send port picks up the XML message and routes it to the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f608d-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="f608d-163">See Also</span></span>  
 <span data-ttu-id="f608d-164">[BizTalk Server 如何接收 AS2 消息](../core/how-biztalk-server-receives-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="f608d-164">[How BizTalk Server Receives AS2 Messages](../core/how-biztalk-server-receives-as2-messages.md) </span></span>  
 [<span data-ttu-id="f608d-165">通过 AS2 传出的 EDI 消息的发送方处理</span><span class="sxs-lookup"><span data-stu-id="f608d-165">Send-Side Processing of an Outgoing EDI Message over AS2</span></span>](../core/send-side-processing-of-an-outgoing-edi-message-over-as2.md)