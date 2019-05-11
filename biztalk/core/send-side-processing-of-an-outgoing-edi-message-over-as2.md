---
title: 发送端处理通过 AS2 传出的 EDI 消息的 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dfb63b22-6e2e-4d4f-b028-301c8d4d53b0
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87e38836d22dfea2415d83fe56274099f2b36110
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254576"
---
# <a name="send-side-processing-of-an-outgoing-edi-message-over-as2"></a><span data-ttu-id="da3b1-102">通过 AS2 传出的 EDI 消息的发送端处理</span><span class="sxs-lookup"><span data-stu-id="da3b1-102">Send-Side Processing of an Outgoing EDI Message over AS2</span></span>
<span data-ttu-id="da3b1-103">通过 AS2 的 EDI 消息的发送方处理包括发送带有 EDI 负载的 AS2 消息和接收 MDN 和 EDI 确认 （如果启用）。</span><span class="sxs-lookup"><span data-stu-id="da3b1-103">Send-side processing of an EDI message over AS2 includes sending an AS2 message with the EDI payload and receiving MDN and EDI acknowledgments (if enabled).</span></span>  
  
 <span data-ttu-id="da3b1-104">AS2EDISend 发送管道通过 HTTP/HTTPS 将已组装的 EDI/AS2 消息发送到接收贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="da3b1-104">The AS2EDISend send pipeline sends an assembled EDI/AS2 message to the receiving trading partner over HTTP/HTTPS.</span></span> <span data-ttu-id="da3b1-105">AS2EDIReceive 接收管道接收 MDN 的 AS2 消息和 EDI 确认以响应 EDI 消息返回到响应中返回。</span><span class="sxs-lookup"><span data-stu-id="da3b1-105">The AS2EDIReceive receive pipeline receives an MDN returned in response to the AS2 message, and an EDI acknowledgment returned in response to the EDI message.</span></span> <span data-ttu-id="da3b1-106">每个这些管道处理 AS2 消息并处理 AS2 消息中的 EDI 负载。</span><span class="sxs-lookup"><span data-stu-id="da3b1-106">Each of these pipelines processes an AS2 message and processes the EDI payload within an AS2 message.</span></span> <span data-ttu-id="da3b1-107">可以包含这些管道在一个 HTTP 双向要求响应发送端口，或在一个单向 HTTP 发送端口和一个单向 HTTP 接收端口。</span><span class="sxs-lookup"><span data-stu-id="da3b1-107">You can include these pipelines in an HTTP two-way solicit response send port, or in a one-way HTTP send port and a one-way HTTP receive port.</span></span>  
  
 <span data-ttu-id="da3b1-108">若要通过 AS2 发送 EDI 交换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="da3b1-108">To send an EDI interchange over AS2, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will perform the following steps:</span></span>  
  
-   <span data-ttu-id="da3b1-109">处理用于发送 EDI 负载</span><span class="sxs-lookup"><span data-stu-id="da3b1-109">Processing the EDI payload for sending</span></span>  
  
-   <span data-ttu-id="da3b1-110">发送 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="da3b1-110">Sending the AS2 message</span></span>  
  
-   <span data-ttu-id="da3b1-111">接收返回的 MDN</span><span class="sxs-lookup"><span data-stu-id="da3b1-111">Receiving the returned MDN</span></span>  
  
-   <span data-ttu-id="da3b1-112">接收返回的 EDI 确认</span><span class="sxs-lookup"><span data-stu-id="da3b1-112">Receiving the returned EDI acknowledgment</span></span>  
  
## <a name="processing-the-edi-payload-for-sending"></a><span data-ttu-id="da3b1-113">处理用于发送 EDI 负载</span><span class="sxs-lookup"><span data-stu-id="da3b1-113">Processing the EDI Payload for Sending</span></span>  
 <span data-ttu-id="da3b1-114">之前创建的 AS2 消息，AS2EdiSend 管道必须处理 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="da3b1-114">Before creating an AS2 message, the AS2EdiSend pipeline must process the EDI interchange.</span></span> <span data-ttu-id="da3b1-115">如果启用出站批处理时，将批处理事务集，如中所述[装配批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。</span><span class="sxs-lookup"><span data-stu-id="da3b1-115">If outbound batching is enabled, transaction sets will be batched as described in [Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md).</span></span> <span data-ttu-id="da3b1-116">EDI 组装器将创建 EDI 交换中所述[EDI 组装器的工作原理](../core/how-the-edi-assembler-works.md)。</span><span class="sxs-lookup"><span data-stu-id="da3b1-116">The EDI Assembler will create the EDI interchange as described in [How the EDI Assembler Works](../core/how-the-edi-assembler-works.md).</span></span>  
  
## <a name="sending-the-as2-message"></a><span data-ttu-id="da3b1-117">发送 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="da3b1-117">Sending the AS2 Message</span></span>  
 <span data-ttu-id="da3b1-118">AS2 发送管道中的 AS2 编码器首先执行协议解析，以确定要用来处理传出的消息的协议属性。</span><span class="sxs-lookup"><span data-stu-id="da3b1-118">The AS2 Encoder in the AS2 send pipeline first performs agreement resolution to determine the agreement properties to be used to process the outgoing message.</span></span> <span data-ttu-id="da3b1-119">有关详细信息，请参阅[传出 AS2 消息的协议解析](../core/agreement-resolution-for-outgoing-as2-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="da3b1-119">For more information, see [Agreement Resolution for Outgoing AS2 Messages](../core/agreement-resolution-for-outgoing-as2-messages.md).</span></span>  
  
 <span data-ttu-id="da3b1-120">AS2 编码器生成发送 AS2 消息所需的 HTTP 标头的集合。</span><span class="sxs-lookup"><span data-stu-id="da3b1-120">The AS2 Encoder builds the set of HTTP headers required to send an AS2 message.</span></span> <span data-ttu-id="da3b1-121">它将添加到这些标头`HTTP.UserHttpHeaders`上下文属性，它是单个字符串的标头值。</span><span class="sxs-lookup"><span data-stu-id="da3b1-121">It adds these headers to the `HTTP.UserHttpHeaders` context property, which is a single string of header values.</span></span> <span data-ttu-id="da3b1-122">AS2 编码器生成以下 AS2 标头`HTTP.UserHttpHeaders`。</span><span class="sxs-lookup"><span data-stu-id="da3b1-122">The AS2 Encoder builds the following AS2 headers in `HTTP.UserHttpHeaders`.</span></span> <span data-ttu-id="da3b1-123">这些标头必须包含 AS2 消息中。</span><span class="sxs-lookup"><span data-stu-id="da3b1-123">These headers must be in the AS2 messages.</span></span>  
  
- <span data-ttu-id="da3b1-124">AS2-To</span><span class="sxs-lookup"><span data-stu-id="da3b1-124">AS2-To</span></span>  
  
- <span data-ttu-id="da3b1-125">AS2-从</span><span class="sxs-lookup"><span data-stu-id="da3b1-125">AS2-From</span></span>  
  
- <span data-ttu-id="da3b1-126">AS2 版本</span><span class="sxs-lookup"><span data-stu-id="da3b1-126">AS2-Version</span></span>  
  
- <span data-ttu-id="da3b1-127">MessageID</span><span class="sxs-lookup"><span data-stu-id="da3b1-127">MessageID</span></span>  
  
- <span data-ttu-id="da3b1-128">OriginalMessageID (仅限 Mdn)</span><span class="sxs-lookup"><span data-stu-id="da3b1-128">OriginalMessageID (for MDNs only)</span></span>  
  
  <span data-ttu-id="da3b1-129">如果**请求 MDN**属性后，管道会将处置-到通知、 回执送达选项和 Signed-receipt-micalg 即用的 AS2 标头中的相应属性; 和它的值将消息中设置如果将设置为"pcks7 签名"的签名回执协议 AS2 标头**请求经过签名的 MDN**属性处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="da3b1-129">If the **Request MDN** property is checked, the pipeline will set the Disposition-Notification-To, Receipt-Delivery-Option, and Signed-Receipt-MICalg AS2 headers in the message to the values in the corresponding properties; and it will set the Signed-Receipt-Protocol AS2 header to "pcks7-signature" if the **Request signed MDN** property is checked.</span></span>  
  
  <span data-ttu-id="da3b1-130">如果`HTTP.UserHttpHeaders`上下文属性不存在，则 AS2 编码器将创建它。</span><span class="sxs-lookup"><span data-stu-id="da3b1-130">If the `HTTP.UserHttpHeaders` context property does not exist, the AS2 Encoder will create it.</span></span> <span data-ttu-id="da3b1-131">如果`HTTP.UserHttpHeaders`已存在，则 AS2 编码器将使用它，而不是创建它。</span><span class="sxs-lookup"><span data-stu-id="da3b1-131">If `HTTP.UserHttpHeaders` already exists, the AS2 Encoder will use it, rather than creating it.</span></span> <span data-ttu-id="da3b1-132">如果您创建`HTTP.UserHttpHeaders`和标头写入它，然后将其写入到消息上下文，AS2 编码器将使用这些标头，并且它们将优先于标头从其他源。</span><span class="sxs-lookup"><span data-stu-id="da3b1-132">If you create `HTTP.UserHttpHeaders`, write headers to it, and then write it to the context of the message, the AS2 Encoder will use those headers, and they will take priority over headers from other sources.</span></span> <span data-ttu-id="da3b1-133">是一个例外 AS2-From 标头，它始终来自协议属性。</span><span class="sxs-lookup"><span data-stu-id="da3b1-133">The exception to that is the AS2-From header, which is always taken from the agreement properties.</span></span>  
  
  <span data-ttu-id="da3b1-134">如果 AS2 标头不在`HTTP.UserHttpHeaders`，AS2 编码器会将其添加从单个上下文属性。</span><span class="sxs-lookup"><span data-stu-id="da3b1-134">If an AS2 header is not in `HTTP.UserHttpHeaders`, the AS2 Encoder will add it from single context properties.</span></span> <span data-ttu-id="da3b1-135">这意味着，您可以通过升级或写入到消息的上下文来添加 AS2 标头 (如果它们尚不在`HTTP.UserHttpHeaders`)。</span><span class="sxs-lookup"><span data-stu-id="da3b1-135">This means that you can add AS2 headers by promoting or writing them to the context of the message (if they are not already in `HTTP.UserHttpHeaders`).</span></span> <span data-ttu-id="da3b1-136">如果 AS2 标头既不在`HTTP.UserHttpHeaders`，也不作为属性存在于上下文，AS2 编码器会将其添加到的协议属性`HTTP.UserHttpHeaders`。</span><span class="sxs-lookup"><span data-stu-id="da3b1-136">If an AS2 header is neither in `HTTP.UserHttpHeaders`, nor present as a property in the context, the AS2 Encoder will add it from agreement properties into `HTTP.UserHttpHeaders`.</span></span>  
  
  <span data-ttu-id="da3b1-137">AS2 编码器生成标头后`HTTP.UserHttpHeaders`属性，它将其写入消息的上下文。</span><span class="sxs-lookup"><span data-stu-id="da3b1-137">After the AS2 Encoder builds the headers in the `HTTP.UserHttpHeaders` property, it writes it to the context of the message.</span></span> <span data-ttu-id="da3b1-138">HTTP 适配器提取`HTTP.UserHttpHeaders`，并将前面添加的标头值`HTTP.UserHttpHeaders`到消息。</span><span class="sxs-lookup"><span data-stu-id="da3b1-138">The HTTP Adapter picks up `HTTP.UserHttpHeaders`, and prepends the header values from `HTTP.UserHttpHeaders` into the message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da3b1-139">AS2 传输协议应仅对 HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="da3b1-139">AS2 transport is intended to work only with the HTTP adapter.</span></span> <span data-ttu-id="da3b1-140">但是，如果你手动设置相应的上下文属性，您可以使用文件适配器传输 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="da3b1-140">However, if you manually set the appropriate context properties, you can use the FILE Adapter to transport AS2 messages.</span></span> <span data-ttu-id="da3b1-141">有关详细信息，请参阅[通过 FILE 发送端口发送 AS2 消息](../core/sending-an-as2-message-over-a-file-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="da3b1-141">For more information, see [Sending an AS2 Message over a FILE Send Port](../core/sending-an-as2-message-over-a-file-send-port.md).</span></span>  
  
## <a name="processing-the-returned-mdn"></a><span data-ttu-id="da3b1-142">处理返回的 MDN</span><span class="sxs-lookup"><span data-stu-id="da3b1-142">Processing the Returned MDN</span></span>  
 <span data-ttu-id="da3b1-143">如果启用了 MDN，则与双向发送端口关联的接收管道从接收 AS2 消息的参与方接收 MDN。</span><span class="sxs-lookup"><span data-stu-id="da3b1-143">If an MDN is enabled, the receive pipeline associated with the two-way send port receives the MDN from the party that receives the AS2 message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da3b1-144">有关 AS2 发送管道对传入的 Mdn 执行处理的详细信息，请参阅[发送传出的 MDN](../core/sending-an-outgoing-mdn.md)。</span><span class="sxs-lookup"><span data-stu-id="da3b1-144">For more information about the processing that the AS2 send pipelines perform on incoming MDNs, see [Sending an Outgoing MDN](../core/sending-an-outgoing-mdn.md).</span></span>  
  
## <a name="processing-the-returned-edi-acknowledgment"></a><span data-ttu-id="da3b1-145">处理返回的 EDI 确认</span><span class="sxs-lookup"><span data-stu-id="da3b1-145">Processing the Returned EDI Acknowledgment</span></span>  
 <span data-ttu-id="da3b1-146">如果启用 EDI 确认，则与双向发送端口关联的接收管道还会收到一个 EDI 确认从 EDI 消息的接收方 （因为它将筛选对 BizTalk EDI 确认消息类型）。</span><span class="sxs-lookup"><span data-stu-id="da3b1-146">If an EDI acknowledgment is enabled, the receive pipeline associated with the two-way send port also receives an EDI acknowledgment from the receiver of the EDI message (because it filters on the BizTalk EDI ACK message type).</span></span> <span data-ttu-id="da3b1-147">有关详细信息，请参阅[处理收到的确认](../core/processing-a-received-acknowledgment.md)。</span><span class="sxs-lookup"><span data-stu-id="da3b1-147">For more information, see [Processing a Received Acknowledgment](../core/processing-a-received-acknowledgment.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da3b1-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="da3b1-148">See Also</span></span>  
 [<span data-ttu-id="da3b1-149">BizTalk Server 如何发送 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="da3b1-149">How BizTalk Server Sends AS2 Messages</span></span>](../core/how-biztalk-server-sends-as2-messages.md)