---
title: 接收方处理的传入非 EDI 消息通过 AS2 |Microsoft 文档
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
ms.openlocfilehash: 7a313c7351f40ba3dbdaf33d15008598dac2ad73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269445"
---
# <a name="receive-side-processing-of-an-incoming-non-edi-message-over-as2"></a><span data-ttu-id="49486-102">通过 AS2 传入的非 EDI 消息的接收方处理</span><span class="sxs-lookup"><span data-stu-id="49486-102">Receive-Side Processing of an Incoming Non-EDI Message over AS2</span></span>
<span data-ttu-id="49486-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 随附的 AS2 管道可用于处理通过 AS2 传输发送的 EDI 消息或非 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="49486-103">The AS2 pipelines shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can be used to process an EDI message or a non-EDI message over AS2 transport.</span></span> <span data-ttu-id="49486-104">不同的管道可用于两种不同类型的负载。</span><span class="sxs-lookup"><span data-stu-id="49486-104">Different pipelines are used for the two different types of payloads.</span></span> <span data-ttu-id="49486-105">使用 AS2EdiReceive 管道处理通过 AS2 传入的 EDI 消息，使用 AS2Send 管道返回关联的 MDN（如果已启用）。</span><span class="sxs-lookup"><span data-stu-id="49486-105">You use the AS2EdiReceive pipeline to process an incoming EDI message over AS2, and the AS2Send pipeline to return the associated MDN (if enabled).</span></span> <span data-ttu-id="49486-106">使用 AS2Receive 管道处理通过 AS2 传入的非 EDI 消息，使用 AS2Send 管道返回关联的 MDN（如果已启用）。</span><span class="sxs-lookup"><span data-stu-id="49486-106">You use the AS2Receive pipeline to process an incoming non-EDI message over AS2, and the AS2Send pipeline to return the associated MDN (if enabled).</span></span> <span data-ttu-id="49486-107">非 EDI 消息可以是任何二进制负载。</span><span class="sxs-lookup"><span data-stu-id="49486-107">The non-EDI message can be any binary payload.</span></span>  
  
 <span data-ttu-id="49486-108">AS2Receive 接收管道对 AS2 消息进行解码，然后对 AS2 消息执行拆装。</span><span class="sxs-lookup"><span data-stu-id="49486-108">The AS2Receive receive pipeline decodes the AS2 message, and then performs disassembly on the AS2 message.</span></span> <span data-ttu-id="49486-109">AS2Send 发送管道对 MDN 进行编码。</span><span class="sxs-lookup"><span data-stu-id="49486-109">An AS2Send send pipeline encodes the MDN.</span></span> <span data-ttu-id="49486-110">可以将 AS2Receive 和 AS2Send 管道包含在一个 HTTP 双向要求响应发送端口中（如果 MDN 是同步的），或者包含在一个单向 HTTP 发送端口和一个单向 HTTP 接收端口中（如果 MDN 是异步的）。</span><span class="sxs-lookup"><span data-stu-id="49486-110">You can include the AS2Receive and AS2Send pipelines in an HTTP two-way solicit response send port (if the MDN is synchronous), or in a one-way HTTP send port and a one-way HTTP receive port (if the MDN is asynchronous).</span></span> <span data-ttu-id="49486-111">如果需要对非 EDI 负载执行拆卸，则必须在其他接收管道中执行此操作，因为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在接收管道中仅允许使用一个拆装器。</span><span class="sxs-lookup"><span data-stu-id="49486-111">If you need to perform disassembly of a non-EDI payload, you will have to do that in another receive pipeline, because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] only allows one disassembler in a receive pipeline.</span></span> <span data-ttu-id="49486-112">这将需要环回发送端口和接收位置 (请参阅[处理接收非 EDI 负载](../core/receive-side-processing-of-an-incoming-non-edi-message-over-as2.md#BKMK_NonEDI)下面一节)。</span><span class="sxs-lookup"><span data-stu-id="49486-112">This will require a loopback send port and receive location (see the [Processing the Received Non-EDI Payload](../core/receive-side-processing-of-an-incoming-non-edi-message-over-as2.md#BKMK_NonEDI) section below).</span></span>  
  
 <span data-ttu-id="49486-113">若要通过 AS2 接收非 EDI 交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="49486-113">To receive a non-EDI interchange over AS2, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will perform the following steps:</span></span>  
  
-   <span data-ttu-id="49486-114">处理收到的 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="49486-114">Processing the received AS2 message</span></span>  
  
-   <span data-ttu-id="49486-115">发送一个 MDN</span><span class="sxs-lookup"><span data-stu-id="49486-115">Sending an MDN</span></span>  
  
-   <span data-ttu-id="49486-116">处理收到的非 EDI 负载</span><span class="sxs-lookup"><span data-stu-id="49486-116">Processing the received non-EDI payload</span></span>  
  
## <a name="processing-the-received-as2-message"></a><span data-ttu-id="49486-117">处理接收 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="49486-117">Processing the Received AS2 message</span></span>  
 <span data-ttu-id="49486-118">AS2Receive 接收管道中的 AS2 解码器处理传入的 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="49486-118">The AS2 Decoder in the AS2Receive receive pipeline processes an incoming AS2 message.</span></span> <span data-ttu-id="49486-119">它都使用`InboundHTTPHeaders`HTTP 适配器创建为 AS2 消息中的 HTTP 标头的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="49486-119">It does so using the `InboundHTTPHeaders` context property, which the HTTP adapter creates from the HTTP headers in the AS2 message.</span></span> <span data-ttu-id="49486-120">这些标头包括下列 AS2 标头：</span><span class="sxs-lookup"><span data-stu-id="49486-120">These headers include the following AS2 headers:</span></span>  
  
-   <span data-ttu-id="49486-121">AS2-To</span><span class="sxs-lookup"><span data-stu-id="49486-121">AS2-To</span></span>  
  
-   <span data-ttu-id="49486-122">AS2-From</span><span class="sxs-lookup"><span data-stu-id="49486-122">AS2-From</span></span>  
  
-   <span data-ttu-id="49486-123">AS2-Version</span><span class="sxs-lookup"><span data-stu-id="49486-123">AS2-Version</span></span>  
  
-   <span data-ttu-id="49486-124">MessageID</span><span class="sxs-lookup"><span data-stu-id="49486-124">MessageID</span></span>  
  
-   <span data-ttu-id="49486-125">OriginalMessageID（仅限 MDN）</span><span class="sxs-lookup"><span data-stu-id="49486-125">OriginalMessageID (for MDNs only)</span></span>  
  
-   <span data-ttu-id="49486-126">Disposition-Notification-To（如果请求一个 MDN）</span><span class="sxs-lookup"><span data-stu-id="49486-126">Disposition-Notification-To (if an MDN is requested)</span></span>  
  
-   <span data-ttu-id="49486-127">Receipt-Delivery-Option（如果请求一个 MDN）</span><span class="sxs-lookup"><span data-stu-id="49486-127">Receipt-Delivery-Option (if an MDN is requested)</span></span>  
  
-   <span data-ttu-id="49486-128">Signed-Receipt-MICalg（如果请求一个 MDN）</span><span class="sxs-lookup"><span data-stu-id="49486-128">Signed-Receipt-MICalg (if an MDN is requested)</span></span>  
  
 <span data-ttu-id="49486-129">AS2 解码器将把这些标头升级到消息的上下文。</span><span class="sxs-lookup"><span data-stu-id="49486-129">The AS2 Decoder will promote these headers to the context of the message.</span></span> <span data-ttu-id="49486-130">随后将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="49486-130">It then does the following:</span></span>  
  
-   <span data-ttu-id="49486-131">执行协议解析，以确定要用于处理传入消息的属性。</span><span class="sxs-lookup"><span data-stu-id="49486-131">Performs agreement resolution to determine the properties to be used to process the incoming message.</span></span> <span data-ttu-id="49486-132">有关详细信息，请参阅[传入 AS2 消息的协议解析](../core/agreement-resolution-for-incoming-as2-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="49486-132">For more information, see [Agreement Resolution for Incoming AS2 Messages](../core/agreement-resolution-for-incoming-as2-messages.md).</span></span>  
  
-   <span data-ttu-id="49486-133">使用 AS2-From 和 AS2-To 属性验证发送方。</span><span class="sxs-lookup"><span data-stu-id="49486-133">Authenticates the sender using the AS2-From and AS2-To properties.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="49486-134">有关处理的详细信息的 AS2 接收管道执行对传入的 AS2 消息，请参阅[处理传入 AS2 消息](../core/processing-an-incoming-as2-message.md)。</span><span class="sxs-lookup"><span data-stu-id="49486-134">For more information about the processing that the AS2 receive pipelines perform on incoming AS2 messages, see [Processing an Incoming AS2 Message](../core/processing-an-incoming-as2-message.md).</span></span>  
  
## <a name="sending-an-mdn"></a><span data-ttu-id="49486-135">发送一个 MDN</span><span class="sxs-lookup"><span data-stu-id="49486-135">Sending an MDN</span></span>  
 <span data-ttu-id="49486-136">如果已启用 MDN，则 AS2Receive 管道将生成一个 MDN 并将其放入 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="49486-136">If an MDN was enabled, the AS2Receive pipeline generates an MDN and drops it into the MessageBox.</span></span> <span data-ttu-id="49486-137">MDN 返回给原始消息的发送方的方式取决于 AS2 传输是同步传输还是异步传输。</span><span class="sxs-lookup"><span data-stu-id="49486-137">How the MDN is returned to the sender of the original message depends upon whether the AS2 transport is synchronous or asynchronous.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49486-138">有关处理的详细信息的 AS2 接收管道中在传出 Mdn 上各项中执行，请参阅[生成传出 MDN](../core/generating-an-outgoing-mdn.md)。</span><span class="sxs-lookup"><span data-stu-id="49486-138">For more information about the processing that the AS2 receive pipelines perform on outgoing MDNs, see [Generating an Outgoing MDN](../core/generating-an-outgoing-mdn.md).</span></span>  
  
 <span data-ttu-id="49486-139">**同步模式**</span><span class="sxs-lookup"><span data-stu-id="49486-139">**Synchronous Mode**</span></span>  
  
 <span data-ttu-id="49486-140">如果非 EDI 消息是通过 AS2 以同步模式发送的，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将通过该同步连接返回 MDN，然后关闭该连接。</span><span class="sxs-lookup"><span data-stu-id="49486-140">If a non-EDI message is sent over AS2 in synchronous mode, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will return the MDN over that synchronous connection and then close the connection.</span></span> <span data-ttu-id="49486-141">MDN 将由 AS2Receive 管道生成，并由该管道路由到 MessageBox，然后由作为请求响应接收端口一部分的 AS2Send 管道自动提取。</span><span class="sxs-lookup"><span data-stu-id="49486-141">The MDN will be generated by the AS2Receive pipeline, routed by that pipeline to the MessageBox, and then automatically picked up by the AS2Send pipeline that is part of the request response receive port.</span></span>  
  
 <span data-ttu-id="49486-142">**异步模式**</span><span class="sxs-lookup"><span data-stu-id="49486-142">**Asynchronous Mode**</span></span>  
  
 <span data-ttu-id="49486-143">如果非 EDI 消息是通过 HTTP/HTTPS 传输以异步模式发送的，则必须创建一个发送端口以单独返回 MDN。</span><span class="sxs-lookup"><span data-stu-id="49486-143">If a non-EDI message is sent over HTTP/HTTPS transport in asynchronous mode, you must create a send port to return the MDN separately.</span></span> <span data-ttu-id="49486-144">如果它是一个动态发送端口，则将使用消息标头中 Receipt-Delivery-Notification 行中的地址将该消息路由到贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="49486-144">If it is a dynamic send port, it will use the address in the Receipt-Delivery-Notification line in the header of the message to route the message to the trading partner.</span></span> <span data-ttu-id="49486-145">如果它是一个静态发送端口，则它将使用在端口属性中定义的地址。</span><span class="sxs-lookup"><span data-stu-id="49486-145">If it is a static send port, it will use the address defined in port properties.</span></span> <span data-ttu-id="49486-146">此发送端口使用 `EdiIntAS.IsAS2AsynchronousMDN==True` 筛选器表达式订阅异步 MDN。</span><span class="sxs-lookup"><span data-stu-id="49486-146">This send port subscribes to the asynchronous MDN by using an `EdiIntAS.IsAS2AsynchronousMDN==True` filter expression.</span></span> <span data-ttu-id="49486-147">在异步处理过程中，AS2Receive 除生成 MDN 之外，还将生成一个 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="49486-147">In asynchronous processing, the AS2Receive pipeline will generate an HTTP response in addition to the MDN.</span></span> <span data-ttu-id="49486-148">接收端口通过接收端口和发送方之间的 HTTP 连接对原始发送方返回 HTTP 响应，这将关闭该连接。</span><span class="sxs-lookup"><span data-stu-id="49486-148">The receive port returns the HTTP response to the original sender over the HTTP connection between the receive port and the sending party, which closes that connection.</span></span> <span data-ttu-id="49486-149">这是必要的，因为 MDN 不会关闭同步连接。</span><span class="sxs-lookup"><span data-stu-id="49486-149">This is necessary because the synchronous connection is not closed by the MDN.</span></span>  
  
##  <a name="BKMK_NonEDI"></a><span data-ttu-id="49486-150">处理接收非 EDI 负载</span><span class="sxs-lookup"><span data-stu-id="49486-150">Processing the Received Non-EDI Payload</span></span>  
 <span data-ttu-id="49486-151">通过 AS2 接收非 EDI 编码的消息时，您需要对该负载执行拆装，并且必须在 AS2Receive 管道以外的其他接收管道中执行拆装。</span><span class="sxs-lookup"><span data-stu-id="49486-151">When a message that is not encoded in EDI is received over AS2, and you need to perform disassembly on the payload, you will have to do that in a different receive pipeline than the AS2Receive pipeline.</span></span> <span data-ttu-id="49486-152">这是必需的，因为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在接收管道中仅允许一个拆装器。</span><span class="sxs-lookup"><span data-stu-id="49486-152">This is required because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] only allows one disassembler in a receive pipeline.</span></span> <span data-ttu-id="49486-153">此方案将需要一个使用发送端口和接收位置的环回机制。</span><span class="sxs-lookup"><span data-stu-id="49486-153">This scenario will require a loopback mechanism using a send port and receive location.</span></span> <span data-ttu-id="49486-154">在第一次传递中，EDIReceive 管道处理 AS2 消息并以其本机格式将消息发送至 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="49486-154">In the first pass, the EDIReceive pipeline processes the AS2 message and sends the message in its native format to the MessageBox.</span></span> <span data-ttu-id="49486-155">在第二次传递中，接收管道采用消息的本机格式生成 XML。</span><span class="sxs-lookup"><span data-stu-id="49486-155">In the second pass, a receive pipeline generates XML from the message's native format.</span></span>  
  
 <span data-ttu-id="49486-156">BizTalk Server 将通过 AS2 BizTalk Server 对非 EDI 消息执行以下接收方处理：</span><span class="sxs-lookup"><span data-stu-id="49486-156">BizTalk Server will perform the following receive-side processing on a non-EDI message over AS2 BizTalk Server:</span></span>  
  
-   <span data-ttu-id="49486-157">与双向请求响应接收位置关联的 AS2Receive 接收管道解析非 EDI 消息中的 AS2 标头，然后将该非 EDI 消息路由至 BizTalk MessageBox。</span><span class="sxs-lookup"><span data-stu-id="49486-157">The AS2Receive receive pipeline associated with the two-way request response receive location parses the AS2 headers from the non-EDI message, and then routes the non-EDI message to the BizTalk MessageBox.</span></span>  
  
-   <span data-ttu-id="49486-158">环回发送端口（FILE 或 MSMQ）从 MessageBox 中提取该非 EDI 消息，因为它依据 BizTalk 属性 `IsAS2PayloadMessage == True` 执行筛选。</span><span class="sxs-lookup"><span data-stu-id="49486-158">A loopback send port (either FILE or MSMQ) picks the non-EDI message up from the MessageBox, because it filters on the BizTalk property `IsAS2PayloadMessage == True`.</span></span> <span data-ttu-id="49486-159">与此发送端口关联的 PassThruTransmit 发送管道以非 EDI 格式传递该消息，从而将该消息路由至一个文件夹或一个 MSMQ 队列。</span><span class="sxs-lookup"><span data-stu-id="49486-159">The PassThruTransmit send pipeline associated with this send port passes the message through in its non-EDI format, routing the message to either a folder or an MSMQ queue.</span></span>  
  
-   <span data-ttu-id="49486-160">环回接收位置提取该消息。</span><span class="sxs-lookup"><span data-stu-id="49486-160">A loopback receive location picks up the message.</span></span> <span data-ttu-id="49486-161">与环回接收位置关联的接收管道根据该非 EDI 消息生成一个 XML 消息，并将其路由至 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="49486-161">The receive pipeline associated with the loopback receive location generates an XML message from the non-EDI message, and routes it to the MessageBox.</span></span>  
  
-   <span data-ttu-id="49486-162">如果该消息将被路由到后端应用程序，则发送端口将提取该 XML 消息并将其路由到应用程序。</span><span class="sxs-lookup"><span data-stu-id="49486-162">If the message is to be routed to a back-end application, a send port picks up the XML message and routes it to the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49486-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49486-163">See Also</span></span>  
 <span data-ttu-id="49486-164">[BizTalk Server 接收 AS2 消息的方式](../core/how-biztalk-server-receives-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="49486-164">[How BizTalk Server Receives AS2 Messages](../core/how-biztalk-server-receives-as2-messages.md) </span></span>  
 [<span data-ttu-id="49486-165">通过 AS2 传出 EDI 消息的发送端处理</span><span class="sxs-lookup"><span data-stu-id="49486-165">Send-Side Processing of an Outgoing EDI Message over AS2</span></span>](../core/send-side-processing-of-an-outgoing-edi-message-over-as2.md)