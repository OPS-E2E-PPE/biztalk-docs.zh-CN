---
title: 接收方处理通过 AS2 传入的 EDI 消息的 |Microsoft Docs
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
ms.openlocfilehash: c4b4d582dd2a40efd08015b6039d97a7e1bfda3a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398179"
---
# <a name="receive-side-processing-of-an-incoming-edi-message-over-as2"></a><span data-ttu-id="457b1-102">通过 AS2 传入的 EDI 消息的接收方处理</span><span class="sxs-lookup"><span data-stu-id="457b1-102">Receive-Side Processing of an Incoming EDI Message over AS2</span></span>
<span data-ttu-id="457b1-103">通过 AS2 的 EDI 消息的接收方处理包括接收 AS2 消息、 发送一个 MDN、 处理 EDI 负载和发送 EDI 确认 （如果已启用）。</span><span class="sxs-lookup"><span data-stu-id="457b1-103">Receive-side processing of an EDI message over AS2 includes receiving the AS2 message, sending an MDN, processing the EDI payload, and sending EDI acknowledgments (if enabled).</span></span>  
  
 <span data-ttu-id="457b1-104">AS2EdiReceive 接收管道接收 AS2 消息和拆装 EDI 负载的 AS2 消息中。</span><span class="sxs-lookup"><span data-stu-id="457b1-104">The AS2EdiReceive receive pipeline receives the AS2 message, and disassembles the EDI payload within the AS2 message.</span></span> <span data-ttu-id="457b1-105">AS2EDISend 发送管道发送一个 MDN 以响应 AS2 消息，并在响应 EDI 消息中返回 EDI 确认。</span><span class="sxs-lookup"><span data-stu-id="457b1-105">The AS2EDISend send pipeline sends an MDN in response to the AS2 message, and an EDI acknowledgment returned in response to the EDI message.</span></span> <span data-ttu-id="457b1-106">可以包含这些管道在一个 HTTP 双向要求响应发送端口 （如果 MDN 是同步的），或在一个单向 HTTP 发送端口和一个单向 HTTP 接收端口 （如果 MDN 是异步的）。</span><span class="sxs-lookup"><span data-stu-id="457b1-106">You can include these pipelines in an HTTP two-way solicit response send port (if the MDN is synchronous), or in a one-way HTTP send port and a one-way HTTP receive port (if the MDN is asynchronous).</span></span>  
  
 <span data-ttu-id="457b1-107">若要通过 AS2 接收 EDI 交换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="457b1-107">To receive an EDI interchange over AS2, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will perform the following steps:</span></span>  
  
-   <span data-ttu-id="457b1-108">处理所接收的 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="457b1-108">Processing the received AS2 message</span></span>  
  
-   <span data-ttu-id="457b1-109">发送一个 MDN</span><span class="sxs-lookup"><span data-stu-id="457b1-109">Sending an MDN</span></span>  
  
-   <span data-ttu-id="457b1-110">处理收到的 EDI 负载</span><span class="sxs-lookup"><span data-stu-id="457b1-110">Processing the received EDI payload</span></span>  
  
-   <span data-ttu-id="457b1-111">发送 EDI 确认</span><span class="sxs-lookup"><span data-stu-id="457b1-111">Sending an EDI Acknowledgment</span></span>  
  
## <a name="processing-the-received-as2-message"></a><span data-ttu-id="457b1-112">处理收到的 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="457b1-112">Processing the Received AS2 message</span></span>  
 <span data-ttu-id="457b1-113">AS2 解码器在 AS2EdiReceive 接收管道处理传入的 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="457b1-113">The AS2 Decoder in the AS2EdiReceive receive pipeline processes an incoming AS2 message.</span></span> <span data-ttu-id="457b1-114">它是通过使用`InboundHTTPHeaders`HTTP 适配器创建 AS2 消息中的 HTTP 标头上下文属性。</span><span class="sxs-lookup"><span data-stu-id="457b1-114">It does so using the `InboundHTTPHeaders` context property, which the HTTP adapter creates from the HTTP headers in the AS2 message.</span></span> <span data-ttu-id="457b1-115">这些标头包括下列 AS2 标头：</span><span class="sxs-lookup"><span data-stu-id="457b1-115">These headers include the following AS2 headers:</span></span>  
  
- <span data-ttu-id="457b1-116">AS2-To</span><span class="sxs-lookup"><span data-stu-id="457b1-116">AS2-To</span></span>  
  
- <span data-ttu-id="457b1-117">AS2-从</span><span class="sxs-lookup"><span data-stu-id="457b1-117">AS2-From</span></span>  
  
- <span data-ttu-id="457b1-118">AS2 版本</span><span class="sxs-lookup"><span data-stu-id="457b1-118">AS2-Version</span></span>  
  
- <span data-ttu-id="457b1-119">MessageID</span><span class="sxs-lookup"><span data-stu-id="457b1-119">MessageID</span></span>  
  
- <span data-ttu-id="457b1-120">OriginalMessageID (仅限 Mdn)</span><span class="sxs-lookup"><span data-stu-id="457b1-120">OriginalMessageID (for MDNs only)</span></span>  
  
- <span data-ttu-id="457b1-121">处理设置-通知-向 （如果请求一个 MDN）</span><span class="sxs-lookup"><span data-stu-id="457b1-121">Disposition-Notification-To (if an MDN is requested)</span></span>  
  
- <span data-ttu-id="457b1-122">回执送达选项 （如果请求一个 MDN）</span><span class="sxs-lookup"><span data-stu-id="457b1-122">Receipt-Delivery-Option (if an MDN is requested)</span></span>  
  
- <span data-ttu-id="457b1-123">签名的回执-MICalg （如果请求一个 MDN）</span><span class="sxs-lookup"><span data-stu-id="457b1-123">Signed-Receipt-MICalg (if an MDN is requested)</span></span>  
  
  <span data-ttu-id="457b1-124">AS2 解码器将升级到消息上下文的这些标头。</span><span class="sxs-lookup"><span data-stu-id="457b1-124">The AS2 Decoder will promote these headers to the context of the message.</span></span> <span data-ttu-id="457b1-125">它然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="457b1-125">It then does the following:</span></span>  
  
- <span data-ttu-id="457b1-126">执行协议解析，以确定要用来处理传入的消息的属性。</span><span class="sxs-lookup"><span data-stu-id="457b1-126">Performs agreement resolution to determine the properties to be used to process the incoming message.</span></span> <span data-ttu-id="457b1-127">有关详细信息，请参阅[传入 AS2 消息的协议解析](../core/agreement-resolution-for-incoming-as2-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="457b1-127">For more information, see [Agreement Resolution for Incoming AS2 Messages](../core/agreement-resolution-for-incoming-as2-messages.md).</span></span>  
  
- <span data-ttu-id="457b1-128">对使用发件人进行身份验证**AS2-从**属性。</span><span class="sxs-lookup"><span data-stu-id="457b1-128">Authenticates the sender using the **AS2-From** property.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="457b1-129">AS2 接收管道处理的详细信息执行对传入的 AS2 消息，请参阅[处理传入 AS2 消息](../core/processing-an-incoming-as2-message.md)。</span><span class="sxs-lookup"><span data-stu-id="457b1-129">For more information about the processing that the AS2 receive pipelines perform on incoming AS2 messages, see [Processing an Incoming AS2 Message](../core/processing-an-incoming-as2-message.md).</span></span>  
  
## <a name="sending-an-mdn"></a><span data-ttu-id="457b1-130">发送一个 MDN</span><span class="sxs-lookup"><span data-stu-id="457b1-130">Sending an MDN</span></span>  
 <span data-ttu-id="457b1-131">如果已启用 MDN，则 AS2EdiReceive 管道生成 MDN 并将其放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="457b1-131">If an MDN was enabled, the AS2EdiReceive pipeline generates an MDN and drops it into the MessageBox.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="457b1-132">对传出 Mdn 执行有关 AS2 接收管道处理的详细信息，请参阅[生成传出 MDN](../core/generating-an-outgoing-mdn.md)。</span><span class="sxs-lookup"><span data-stu-id="457b1-132">For more information about the processing that the AS2 receive pipelines perform on outgoing MDNs, see [Generating an Outgoing MDN](../core/generating-an-outgoing-mdn.md).</span></span>  
  
 <span data-ttu-id="457b1-133">**同步模式**</span><span class="sxs-lookup"><span data-stu-id="457b1-133">**Synchronous Mode**</span></span>  
  
 <span data-ttu-id="457b1-134">如果在同步模式下，通过 AS2 发送 EDI 消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将通过该同步连接返回 MDN，然后关闭该连接。</span><span class="sxs-lookup"><span data-stu-id="457b1-134">If an EDI message is sent over AS2 in synchronous mode, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will return the MDN over that synchronous connection and then close the connection.</span></span> <span data-ttu-id="457b1-135">因为连接已关闭，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法通过该连接返回 EDI 确认 (997、 TA1 或 CONTRL)。</span><span class="sxs-lookup"><span data-stu-id="457b1-135">Since the connection has been closed, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot return an EDI acknowledgment (997, TA1, or CONTRL) over that connection.</span></span> <span data-ttu-id="457b1-136">EDI 确认始终通过 AS2 异步发送。</span><span class="sxs-lookup"><span data-stu-id="457b1-136">EDI acknowledgments are always sent asynchronously over AS2.</span></span>  
  
 <span data-ttu-id="457b1-137">MDN 将由 AS2EDIReceive 管道生成的、 由该管道路由到 MessageBox，然后自动提取请求的一部分的 AS2Send 管道响应接收端口。</span><span class="sxs-lookup"><span data-stu-id="457b1-137">The MDN will be generated by the AS2EDIReceive pipeline, routed by that pipeline to the MessageBox, and then automatically picked up by the AS2Send pipeline that is part of the request response receive port.</span></span>  
  
 <span data-ttu-id="457b1-138">**异步模式**</span><span class="sxs-lookup"><span data-stu-id="457b1-138">**Asynchronous Mode**</span></span>  
  
 <span data-ttu-id="457b1-139">如果 EDIINT/AS2 编码的消息通过 HTTP/HTTPS 传输以异步模式发送的您必须创建发送端口以单独返回 MDN。</span><span class="sxs-lookup"><span data-stu-id="457b1-139">If an EDIINT/AS2-encoded message is sent over HTTP/HTTPS transport in asynchronous mode, you must create a send port to return the MDN separately.</span></span> <span data-ttu-id="457b1-140">可以配置此发送端口返回异步 Mdn 和 EDI 确认。</span><span class="sxs-lookup"><span data-stu-id="457b1-140">You can configure this send port to return both asynchronous MDNs and EDI acknowledgments.</span></span> <span data-ttu-id="457b1-141">如果它是一个动态发送端口，它将使用消息标头中的回执送达通知行中的地址将消息路由到贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="457b1-141">If it is a dynamic send port, it will use the address in the Receipt-Delivery-Notification line in the header of the message to route the message to the trading partner.</span></span> <span data-ttu-id="457b1-142">如果它是一个静态发送端口，它将使用在端口属性中配置的地址。</span><span class="sxs-lookup"><span data-stu-id="457b1-142">If it is a static send port, it will use the address configured in port properties.</span></span> <span data-ttu-id="457b1-143">此发送端口使用订阅异步 MDN`EdiIntAS.IsAS2AsynchronousMDN==True`筛选表达式。</span><span class="sxs-lookup"><span data-stu-id="457b1-143">This send port subscribes to the asynchronous MDN by using an `EdiIntAS.IsAS2AsynchronousMDN==True` filter expression.</span></span>  
  
 <span data-ttu-id="457b1-144">在异步处理过程，则 AS2EdiReceive 管道将生成在 MDN 之外还 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="457b1-144">In asynchronous processing, the AS2EdiReceive pipeline will generate an HTTP response in addition to the MDN.</span></span> <span data-ttu-id="457b1-145">接收端口接收端口和发送方，这会关闭该连接之间通过 HTTP 连接返回到原始发送方的 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="457b1-145">The receive port returns the HTTP response to the original sender over the HTTP connection between the receive port and the sending party, which closes that connection.</span></span> <span data-ttu-id="457b1-146">这是必需的因为 MDN 不会关闭同步连接。</span><span class="sxs-lookup"><span data-stu-id="457b1-146">This is necessary because the synchronous connection is not closed by the MDN.</span></span>  
  
 <span data-ttu-id="457b1-147">如果 BizTalk 通过 HTTP/HTTPS 传输 EDIINT/AS2 编码的消息，但 EDI 编码的负载的处理失败，原始消息的发件人会收到表示成功处理了 AS2 和 EDI 确认，它指示这两个的 MDN在 EDI 处理中失败。</span><span class="sxs-lookup"><span data-stu-id="457b1-147">If BizTalk transports an EDIINT/AS2-encoded message over HTTP/HTTPS, but processing of the EDI-encoded payload fails, the sender of the original message would receive both an MDN indicating successful AS2 processing and an EDI acknowledgment indicating a failure in EDI processing.</span></span> <span data-ttu-id="457b1-148">EDI 编码的负载将被挂起，并会发出错误。</span><span class="sxs-lookup"><span data-stu-id="457b1-148">The EDI-encoded payload would be suspended and an error would be posted.</span></span>  
  
## <a name="processing-the-received-edi-payload"></a><span data-ttu-id="457b1-149">处理收到的 EDI 负载</span><span class="sxs-lookup"><span data-stu-id="457b1-149">Processing the Received EDI Payload</span></span>  
 <span data-ttu-id="457b1-150">如果**入站批处理选项**对于 EDI 协议设置为**将交换拆分**，AS2EdiReceive 接收管道关联与双向请求响应接收位置分析设置 EDI 消息转换为每个 EDI 事务单独的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="457b1-150">If the **Inbound batch processing option** for an EDI agreement is set to **Split Interchange**, the AS2EdiReceive receive pipeline associated with the two-way request response receive location parses the EDI message into a separate XML message for each EDI transaction set.</span></span> <span data-ttu-id="457b1-151">如果**入站批处理选项**设置为**保留交换**，接收管道将不解析 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="457b1-151">If the **Inbound batch processing option** is set to **Preserve Interchange**, the receive pipeline will not parse the EDI message.</span></span>  
  
 <span data-ttu-id="457b1-152">接收管道将 XML 事务集或保留的 EDI 交换路由到 BizTalk MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="457b1-152">The receive pipeline routes the XML transaction sets or the preserved EDI interchange to the BizTalk MessageBox.</span></span>  
  
 <span data-ttu-id="457b1-153">如果该消息将路由到后端应用程序，发送端口提取 XML 消息，并将其路由到该应用程序。</span><span class="sxs-lookup"><span data-stu-id="457b1-153">If the message is to be routed to a back-end application, a send port picks up the XML message and routes it to the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="457b1-154">此发送端口可以是任何类型。</span><span class="sxs-lookup"><span data-stu-id="457b1-154">This send port can be of any type.</span></span>  
  
## <a name="sending-the-edi-acknowledgment"></a><span data-ttu-id="457b1-155">发送 EDI 确认</span><span class="sxs-lookup"><span data-stu-id="457b1-155">Sending the EDI Acknowledgment</span></span>  
 <span data-ttu-id="457b1-156">如果已启用 EDI 确认，EDI 拆装器在 AS2EdiReceive 接收管道将生成 EDI 确认 （如果启用）。</span><span class="sxs-lookup"><span data-stu-id="457b1-156">If an EDI acknowledgment was enabled, the EDI Disassembler in the AS2EdiReceive receive pipeline will generate EDI acknowledgments (if enabled).</span></span> <span data-ttu-id="457b1-157">必须在单独的单向发送端口中的 AS2EdiSend 发送管道发送 EDI 确认。</span><span class="sxs-lookup"><span data-stu-id="457b1-157">The EDI acknowledgments must be sent by the AS2EdiSend send pipeline in a separate one-way send port.</span></span>  
  
 <span data-ttu-id="457b1-158">如果设置了一个双向请求-响应接收端口返回同步 MDN 或 HTTP 响应 （对于异步 MDN)，将 EDI/AS2 消息**将确认路由到发送管道请求-响应接收端口**属性 (在中设置**本地主机设置**单向 EDI 协议中的页**协议属性**对话框) 将被忽略。</span><span class="sxs-lookup"><span data-stu-id="457b1-158">If you set up a two-way request-response receive port for EDI/AS2 messages to return a synchronous MDN or an HTTP response (in the case of an asynchronous MDN), the **Route ACK to send pipeline on request-response receive port** property (set in the **Local Host Settings** page of the one-way EDI agreement in the **Agreement Properties** dialog box) will be ignored.</span></span> <span data-ttu-id="457b1-159">即使选中此属性，发送管道将返回同步 MDN 或 HTTP 响应，不是 EDI 确认。</span><span class="sxs-lookup"><span data-stu-id="457b1-159">Even if this property is checked, the send pipeline will return either a synchronous MDN or an HTTP response, not an EDI acknowledgment.</span></span>  
  
 <span data-ttu-id="457b1-160">有关详细信息，请参阅[发送 EDI 确认](../core/sending-an-edi-acknowledgment.md)。</span><span class="sxs-lookup"><span data-stu-id="457b1-160">For more information, see [Sending an EDI Acknowledgment](../core/sending-an-edi-acknowledgment.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="457b1-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="457b1-161">See Also</span></span>  
 [<span data-ttu-id="457b1-162">BizTalk Server 如何接收 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="457b1-162">How BizTalk Server Receives AS2 Messages</span></span>](../core/how-biztalk-server-receives-as2-messages.md)