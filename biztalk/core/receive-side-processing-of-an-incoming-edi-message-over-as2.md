---
title: 接收方处理的传入 EDI 消息通过 AS2 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 118451ab-d847-4f87-80ab-3cf812d71ac3
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fc9069dddf8a8b58ad439ed915fc9afa539c2a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270061"
---
# <a name="receive-side-processing-of-an-incoming-edi-message-over-as2"></a><span data-ttu-id="7bedb-102">接收方在处理传入 EDI 消息通过 AS2</span><span class="sxs-lookup"><span data-stu-id="7bedb-102">Receive-Side Processing of an Incoming EDI Message over AS2</span></span>
<span data-ttu-id="7bedb-103">通过 AS2 传入的 EDI 消息的接收方处理包括接收 AS2 消息、发送一个 MDN、处理 EDI 负载和发送 EDI 确认（如果已启用）。</span><span class="sxs-lookup"><span data-stu-id="7bedb-103">Receive-side processing of an EDI message over AS2 includes receiving the AS2 message, sending an MDN, processing the EDI payload, and sending EDI acknowledgments (if enabled).</span></span>  
  
 <span data-ttu-id="7bedb-104">AS2EdiReceive 接收管道接收 AS2 消息、并在该消息内拆装 EDI 负载。</span><span class="sxs-lookup"><span data-stu-id="7bedb-104">The AS2EdiReceive receive pipeline receives the AS2 message, and disassembles the EDI payload within the AS2 message.</span></span> <span data-ttu-id="7bedb-105">AS2EDISend 发送管道发送一个 MDN 以响应 AS2 消息，并返回一个 EDI 确认以响应 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="7bedb-105">The AS2EDISend send pipeline sends an MDN in response to the AS2 message, and an EDI acknowledgment returned in response to the EDI message.</span></span> <span data-ttu-id="7bedb-106">可以将这些管道包含在一个 HTTP 双向要求响应发送端口中（如果 MDN 是同步的），或者包含在一个单向 HTTP 发送端口和一个单向 HTTP 接收端口中（如果 MDN 是异步的）。</span><span class="sxs-lookup"><span data-stu-id="7bedb-106">You can include these pipelines in an HTTP two-way solicit response send port (if the MDN is synchronous), or in a one-way HTTP send port and a one-way HTTP receive port (if the MDN is asynchronous).</span></span>  
  
 <span data-ttu-id="7bedb-107">若要通过 AS2 接收的 EDI 交换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7bedb-107">To receive an EDI interchange over AS2, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will perform the following steps:</span></span>  
  
-   <span data-ttu-id="7bedb-108">处理收到的 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="7bedb-108">Processing the received AS2 message</span></span>  
  
-   <span data-ttu-id="7bedb-109">发送一个 MDN</span><span class="sxs-lookup"><span data-stu-id="7bedb-109">Sending an MDN</span></span>  
  
-   <span data-ttu-id="7bedb-110">处理收到的 EDI 负载</span><span class="sxs-lookup"><span data-stu-id="7bedb-110">Processing the received EDI payload</span></span>  
  
-   <span data-ttu-id="7bedb-111">发送 EDI 确认</span><span class="sxs-lookup"><span data-stu-id="7bedb-111">Sending an EDI Acknowledgment</span></span>  
  
## <a name="processing-the-received-as2-message"></a><span data-ttu-id="7bedb-112">处理接收 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="7bedb-112">Processing the Received AS2 message</span></span>  
 <span data-ttu-id="7bedb-113">AS2EdiReceive receive 接收管道中的 AS2 解码器处理传入的 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="7bedb-113">The AS2 Decoder in the AS2EdiReceive receive pipeline processes an incoming AS2 message.</span></span> <span data-ttu-id="7bedb-114">它都使用`InboundHTTPHeaders`HTTP 适配器创建为 AS2 消息中的 HTTP 标头的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="7bedb-114">It does so using the `InboundHTTPHeaders` context property, which the HTTP adapter creates from the HTTP headers in the AS2 message.</span></span> <span data-ttu-id="7bedb-115">这些标头包括下列 AS2 标头：</span><span class="sxs-lookup"><span data-stu-id="7bedb-115">These headers include the following AS2 headers:</span></span>  
  
-   <span data-ttu-id="7bedb-116">AS2-To</span><span class="sxs-lookup"><span data-stu-id="7bedb-116">AS2-To</span></span>  
  
-   <span data-ttu-id="7bedb-117">AS2-From</span><span class="sxs-lookup"><span data-stu-id="7bedb-117">AS2-From</span></span>  
  
-   <span data-ttu-id="7bedb-118">AS2-Version</span><span class="sxs-lookup"><span data-stu-id="7bedb-118">AS2-Version</span></span>  
  
-   <span data-ttu-id="7bedb-119">MessageID</span><span class="sxs-lookup"><span data-stu-id="7bedb-119">MessageID</span></span>  
  
-   <span data-ttu-id="7bedb-120">OriginalMessageID（仅限 MDN）</span><span class="sxs-lookup"><span data-stu-id="7bedb-120">OriginalMessageID (for MDNs only)</span></span>  
  
-   <span data-ttu-id="7bedb-121">Disposition-Notification-To（如果请求一个 MDN）</span><span class="sxs-lookup"><span data-stu-id="7bedb-121">Disposition-Notification-To (if an MDN is requested)</span></span>  
  
-   <span data-ttu-id="7bedb-122">Receipt-Delivery-Option（如果请求一个 MDN）</span><span class="sxs-lookup"><span data-stu-id="7bedb-122">Receipt-Delivery-Option (if an MDN is requested)</span></span>  
  
-   <span data-ttu-id="7bedb-123">Signed-Receipt-MICalg（如果请求一个 MDN）</span><span class="sxs-lookup"><span data-stu-id="7bedb-123">Signed-Receipt-MICalg (if an MDN is requested)</span></span>  
  
 <span data-ttu-id="7bedb-124">AS2 解码器将把这些标头升级到消息的上下文。</span><span class="sxs-lookup"><span data-stu-id="7bedb-124">The AS2 Decoder will promote these headers to the context of the message.</span></span> <span data-ttu-id="7bedb-125">随后将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7bedb-125">It then does the following:</span></span>  
  
-   <span data-ttu-id="7bedb-126">执行协议解析，以确定要用于处理传入消息的属性。</span><span class="sxs-lookup"><span data-stu-id="7bedb-126">Performs agreement resolution to determine the properties to be used to process the incoming message.</span></span> <span data-ttu-id="7bedb-127">有关详细信息，请参阅[传入 AS2 消息的协议解析](../core/agreement-resolution-for-incoming-as2-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="7bedb-127">For more information, see [Agreement Resolution for Incoming AS2 Messages](../core/agreement-resolution-for-incoming-as2-messages.md).</span></span>  
  
-   <span data-ttu-id="7bedb-128">进行身份验证使用发件人**AS2-从**属性。</span><span class="sxs-lookup"><span data-stu-id="7bedb-128">Authenticates the sender using the **AS2-From** property.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7bedb-129">有关处理的详细信息的 AS2 接收管道执行对传入的 AS2 消息，请参阅[处理传入 AS2 消息](../core/processing-an-incoming-as2-message.md)。</span><span class="sxs-lookup"><span data-stu-id="7bedb-129">For more information about the processing that the AS2 receive pipelines perform on incoming AS2 messages, see [Processing an Incoming AS2 Message](../core/processing-an-incoming-as2-message.md).</span></span>  
  
## <a name="sending-an-mdn"></a><span data-ttu-id="7bedb-130">发送一个 MDN</span><span class="sxs-lookup"><span data-stu-id="7bedb-130">Sending an MDN</span></span>  
 <span data-ttu-id="7bedb-131">如果已启用 MDN，则 AS2EdiReceive 管道将生成一个 MDN 并将其放入 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="7bedb-131">If an MDN was enabled, the AS2EdiReceive pipeline generates an MDN and drops it into the MessageBox.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7bedb-132">有关处理的详细信息的 AS2 接收管道中在传出 Mdn 上各项中执行，请参阅[生成传出 MDN](../core/generating-an-outgoing-mdn.md)。</span><span class="sxs-lookup"><span data-stu-id="7bedb-132">For more information about the processing that the AS2 receive pipelines perform on outgoing MDNs, see [Generating an Outgoing MDN](../core/generating-an-outgoing-mdn.md).</span></span>  
  
 <span data-ttu-id="7bedb-133">**同步模式**</span><span class="sxs-lookup"><span data-stu-id="7bedb-133">**Synchronous Mode**</span></span>  
  
 <span data-ttu-id="7bedb-134">如果在同步模式下，通过 AS2 发送 EDI 消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将通过该同步连接返回 MDN，然后关闭该连接。</span><span class="sxs-lookup"><span data-stu-id="7bedb-134">If an EDI message is sent over AS2 in synchronous mode, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will return the MDN over that synchronous connection and then close the connection.</span></span> <span data-ttu-id="7bedb-135">连接已关闭，因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法通过该连接返回 EDI 确认 (997，TA1 或 CONTRL)。</span><span class="sxs-lookup"><span data-stu-id="7bedb-135">Since the connection has been closed, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot return an EDI acknowledgment (997, TA1, or CONTRL) over that connection.</span></span> <span data-ttu-id="7bedb-136">EDI 确认始终通过 AS2 异步发送。</span><span class="sxs-lookup"><span data-stu-id="7bedb-136">EDI acknowledgments are always sent asynchronously over AS2.</span></span>  
  
 <span data-ttu-id="7bedb-137">MDN 将由 AS2EDIReceive 管道生成，并由该管道路由到 MessageBox，然后由作为请求响应接收端口一部分的 AS2Send 管道自动提取。</span><span class="sxs-lookup"><span data-stu-id="7bedb-137">The MDN will be generated by the AS2EDIReceive pipeline, routed by that pipeline to the MessageBox, and then automatically picked up by the AS2Send pipeline that is part of the request response receive port.</span></span>  
  
 <span data-ttu-id="7bedb-138">**异步模式**</span><span class="sxs-lookup"><span data-stu-id="7bedb-138">**Asynchronous Mode**</span></span>  
  
 <span data-ttu-id="7bedb-139">如果 EDIINT/AS2 编码的消息通过 HTTP/HTTPS 传输发送异步模式中，你必须创建单独返回 MDN 发送端口。</span><span class="sxs-lookup"><span data-stu-id="7bedb-139">If an EDIINT/AS2-encoded message is sent over HTTP/HTTPS transport in asynchronous mode, you must create a send port to return the MDN separately.</span></span> <span data-ttu-id="7bedb-140">可以将此发送端口配置为既返回异步 MDN 也返回 EDI 确认。</span><span class="sxs-lookup"><span data-stu-id="7bedb-140">You can configure this send port to return both asynchronous MDNs and EDI acknowledgments.</span></span> <span data-ttu-id="7bedb-141">如果它是一个动态发送端口，则将使用消息标头中 Receipt-Delivery-Notification 行中的地址将该消息路由到贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="7bedb-141">If it is a dynamic send port, it will use the address in the Receipt-Delivery-Notification line in the header of the message to route the message to the trading partner.</span></span> <span data-ttu-id="7bedb-142">如果它是一个静态发送端口，则它将使用在端口属性中配置的地址。</span><span class="sxs-lookup"><span data-stu-id="7bedb-142">If it is a static send port, it will use the address configured in port properties.</span></span> <span data-ttu-id="7bedb-143">此发送端口使用 `EdiIntAS.IsAS2AsynchronousMDN==True` 筛选器表达式订阅异步 MDN。</span><span class="sxs-lookup"><span data-stu-id="7bedb-143">This send port subscribes to the asynchronous MDN by using an `EdiIntAS.IsAS2AsynchronousMDN==True` filter expression.</span></span>  
  
 <span data-ttu-id="7bedb-144">在异步处理过程中，AS2EdiReceive 管道将在 MDN 之外还生成一个 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="7bedb-144">In asynchronous processing, the AS2EdiReceive pipeline will generate an HTTP response in addition to the MDN.</span></span> <span data-ttu-id="7bedb-145">接收端口通过接收端口和发送方之间的 HTTP 连接对原始发送方返回 HTTP 响应，这将关闭该连接。</span><span class="sxs-lookup"><span data-stu-id="7bedb-145">The receive port returns the HTTP response to the original sender over the HTTP connection between the receive port and the sending party, which closes that connection.</span></span> <span data-ttu-id="7bedb-146">这是必要的，因为 MDN 不会关闭同步连接。</span><span class="sxs-lookup"><span data-stu-id="7bedb-146">This is necessary because the synchronous connection is not closed by the MDN.</span></span>  
  
 <span data-ttu-id="7bedb-147">如果 BizTalk 通过 HTTP/HTTPS 传输 EDIINT/AS2 编码的消息，但是在处理 EDI 编码的负载时失败，原始消息的发送方既会收到表示成功处理了 AS2 的 MDN 确认，也会收到表示 EDI 处理失败的 EDI 确认。</span><span class="sxs-lookup"><span data-stu-id="7bedb-147">If BizTalk transports an EDIINT/AS2-encoded message over HTTP/HTTPS, but processing of the EDI-encoded payload fails, the sender of the original message would receive both an MDN indicating successful AS2 processing and an EDI acknowledgment indicating a failure in EDI processing.</span></span> <span data-ttu-id="7bedb-148">将挂起的 EDI 编码的负载并将发布错误。</span><span class="sxs-lookup"><span data-stu-id="7bedb-148">The EDI-encoded payload would be suspended and an error would be posted.</span></span>  
  
## <a name="processing-the-received-edi-payload"></a><span data-ttu-id="7bedb-149">处理收到的 EDI 负载</span><span class="sxs-lookup"><span data-stu-id="7bedb-149">Processing the Received EDI Payload</span></span>  
 <span data-ttu-id="7bedb-150">如果**入站批处理选项**对于 EDI 协议设置为**将交换拆分**，AS2EdiReceive 接收与双向关联的管道请求响应接收位置分析对于每个 EDI 事务一个单独的 XML 消息的 EDI 消息设置。</span><span class="sxs-lookup"><span data-stu-id="7bedb-150">If the **Inbound batch processing option** for an EDI agreement is set to **Split Interchange**, the AS2EdiReceive receive pipeline associated with the two-way request response receive location parses the EDI message into a separate XML message for each EDI transaction set.</span></span> <span data-ttu-id="7bedb-151">如果**入站批处理选项**设置为**保留交换**，接收管道将不会分析 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="7bedb-151">If the **Inbound batch processing option** is set to **Preserve Interchange**, the receive pipeline will not parse the EDI message.</span></span>  
  
 <span data-ttu-id="7bedb-152">接收管道将 XML 事务集或保留 EDI 交换路由到 BizTalk MessageBox。</span><span class="sxs-lookup"><span data-stu-id="7bedb-152">The receive pipeline routes the XML transaction sets or the preserved EDI interchange to the BizTalk MessageBox.</span></span>  
  
 <span data-ttu-id="7bedb-153">如果该消息将被路由到后端应用程序，则发送端口将提取该 XML 消息并将其路由到应用程序。</span><span class="sxs-lookup"><span data-stu-id="7bedb-153">If the message is to be routed to a back-end application, a send port picks up the XML message and routes it to the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7bedb-154">此发送端口可以是任何类型。</span><span class="sxs-lookup"><span data-stu-id="7bedb-154">This send port can be of any type.</span></span>  
  
## <a name="sending-the-edi-acknowledgment"></a><span data-ttu-id="7bedb-155">发送 EDI 确认</span><span class="sxs-lookup"><span data-stu-id="7bedb-155">Sending the EDI Acknowledgment</span></span>  
 <span data-ttu-id="7bedb-156">如果已启用 EDI 确认，则 AS2EdiReceive 接收管道中的 EDI 拆装器将生成 EDI 确认（如果启用）。</span><span class="sxs-lookup"><span data-stu-id="7bedb-156">If an EDI acknowledgment was enabled, the EDI Disassembler in the AS2EdiReceive receive pipeline will generate EDI acknowledgments (if enabled).</span></span> <span data-ttu-id="7bedb-157">该 EDI 确认必须由 AS2EdiSend 发送管道使用单独的单向发送端口进行发送。</span><span class="sxs-lookup"><span data-stu-id="7bedb-157">The EDI acknowledgments must be sent by the AS2EdiSend send pipeline in a separate one-way send port.</span></span>  
  
 <span data-ttu-id="7bedb-158">如果设置了双向请求-响应接收 EDI/AS2 消息以返回同步的 MDN 或 （对于异步 MDN) 的 HTTP 响应端口**路由 ACK 发送管道请求-响应接收端口**属性 (在中设置**本地主机设置**单向 EDI 协议中的页**协议属性**对话框中) 将被忽略。</span><span class="sxs-lookup"><span data-stu-id="7bedb-158">If you set up a two-way request-response receive port for EDI/AS2 messages to return a synchronous MDN or an HTTP response (in the case of an asynchronous MDN), the **Route ACK to send pipeline on request-response receive port** property (set in the **Local Host Settings** page of the one-way EDI agreement in the **Agreement Properties** dialog box) will be ignored.</span></span> <span data-ttu-id="7bedb-159">即使选中此属性，发送管道将返回一个同步 MDN 或 HTTP 响应，而不是 EDI 确认。</span><span class="sxs-lookup"><span data-stu-id="7bedb-159">Even if this property is checked, the send pipeline will return either a synchronous MDN or an HTTP response, not an EDI acknowledgment.</span></span>  
  
 <span data-ttu-id="7bedb-160">有关详细信息，请参阅[发送 EDI 确认](../core/sending-an-edi-acknowledgment.md)。</span><span class="sxs-lookup"><span data-stu-id="7bedb-160">For more information, see [Sending an EDI Acknowledgment](../core/sending-an-edi-acknowledgment.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bedb-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7bedb-161">See Also</span></span>  
 [<span data-ttu-id="7bedb-162">BizTalk Server 接收 AS2 消息的方式</span><span class="sxs-lookup"><span data-stu-id="7bedb-162">How BizTalk Server Receives AS2 Messages</span></span>](../core/how-biztalk-server-receives-as2-messages.md)