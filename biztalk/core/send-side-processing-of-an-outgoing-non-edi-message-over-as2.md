---
title: 发送端处理通过 AS2 传出的非 EDI 消息的 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f19b7df-fe6d-4105-8a44-3d6db0bba451
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 537ff8147d42bce1db7135f38b9b9c5c8f1f160e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987998"
---
# <a name="send-side-processing-of-an-outgoing-non-edi-message-over-as2"></a><span data-ttu-id="da081-102">通过 AS2 传出的非 EDI 消息的发送端处理</span><span class="sxs-lookup"><span data-stu-id="da081-102">Send-Side Processing of an Outgoing Non-EDI Message over AS2</span></span>
<span data-ttu-id="da081-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 随附的 AS2 管道可用于处理通过 AS2 传输发送的 EDI 消息或非 EDI 消息。</span><span class="sxs-lookup"><span data-stu-id="da081-103">The AS2 pipelines shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can be used to process an EDI message or a non-EDI message over AS2 transport.</span></span> <span data-ttu-id="da081-104">不同的管道可用于两种不同类型的负载。</span><span class="sxs-lookup"><span data-stu-id="da081-104">Different pipelines are used for the two different types of payloads.</span></span> <span data-ttu-id="da081-105">可以使用 AS2EdiSend 管道处理通过 AS2 传出的 EDI 消息，并使用 AS2Receive 管道接收关联的 MDN（如果已启用）。</span><span class="sxs-lookup"><span data-stu-id="da081-105">You use the AS2EdiSend pipeline to process an outgoing EDI message over AS2, and the AS2Receive pipeline to receive the associated MDN (if enabled).</span></span> <span data-ttu-id="da081-106">可以使用 AS2Send 管道处理通过 AS2 传出的非 EDI 消息，并使用 AS2Receive 管道接收关联的 MDN（如果已启用）。</span><span class="sxs-lookup"><span data-stu-id="da081-106">You use the AS2Send pipeline to process an outgoing non-EDI message over AS2, and the AS2Receive pipeline to receive the associated MDN (if enabled).</span></span> <span data-ttu-id="da081-107">非 EDI 消息可以是任何二进制负载。</span><span class="sxs-lookup"><span data-stu-id="da081-107">The non-EDI message can be any binary payload.</span></span>  
  
 <span data-ttu-id="da081-108">AS2Send 发送管道可对非 EDI 负载进行组装并对 AS2 消息进行编码。</span><span class="sxs-lookup"><span data-stu-id="da081-108">The AS2Send send pipeline assembles the non-EDI payload and encodes the AS2 message.</span></span> <span data-ttu-id="da081-109">AS2Receive 接收管道可对 MDN 响应进行解码。</span><span class="sxs-lookup"><span data-stu-id="da081-109">The AS2Receive receive pipeline decodes the MDN response.</span></span> <span data-ttu-id="da081-110">可以将这些管道包含在一个 HTTP 双向要求响应发送端口中（对于同步 MDN），或者包含在一个单向 HTTP 发送端口和一个单向 HTTP 接收端口中（对于异步 MDN）。</span><span class="sxs-lookup"><span data-stu-id="da081-110">You can include these pipelines in an HTTP two-way solicit response send port (for synchronous MDNs), or in a one-way HTTP send port and a one-way HTTP receive port (for asynchronous MDNs).</span></span>  
  
 <span data-ttu-id="da081-111">若要通过 AS2 发送 EDI 交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="da081-111">To send an EDI interchange over AS2, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will perform the following steps:</span></span>  
  
-   <span data-ttu-id="da081-112">处理用于发送的非 EDI 负载</span><span class="sxs-lookup"><span data-stu-id="da081-112">Processing the non-EDI payload for sending</span></span>  
  
-   <span data-ttu-id="da081-113">发送 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="da081-113">Sending the AS2 message</span></span>  
  
-   <span data-ttu-id="da081-114">接收返回的 MDN</span><span class="sxs-lookup"><span data-stu-id="da081-114">Receiving the returned MDN</span></span>  
  
## <a name="processing-the-non-edi-payload-for-sending"></a><span data-ttu-id="da081-115">处理用于发送非 EDI 负载</span><span class="sxs-lookup"><span data-stu-id="da081-115">Processing the Non-EDI Payload for Sending</span></span>  
 <span data-ttu-id="da081-116">创建 AS2 消息之前，发送端口必须提取非 EDI 负载，并使用适当的筛选器表达式订阅消息。</span><span class="sxs-lookup"><span data-stu-id="da081-116">Before creating the AS2 message, a send port must pick up the non-EDI payload, using an appropriate filter expression to subscribe to the messages.</span></span> <span data-ttu-id="da081-117">可以使用双向发送端口或单向发送端口，具体取决于 MDN 将同步还是异步。</span><span class="sxs-lookup"><span data-stu-id="da081-117">You can use a two-way send port or a one-way send port, depending upon whether the MDN will be synchronous or asynchronous.</span></span> <span data-ttu-id="da081-118">然后，AS2Send 管道将非 EDI 负载处理成 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="da081-118">The AS2Send pipeline will then process the non-EDI payload into an AS2 message.</span></span>  
  
## <a name="sending-the-as2-message"></a><span data-ttu-id="da081-119">发送 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="da081-119">Sending the AS2 Message</span></span>  
 <span data-ttu-id="da081-120">AS2 发送管道中的 AS2 编码器首先执行协议解析，以确定将要用于处理传出消息的协议属性。</span><span class="sxs-lookup"><span data-stu-id="da081-120">The AS2 Encoder in the AS2 send pipeline first performs agreement resolution to determine the agreement properties to be used to process the outgoing message.</span></span> <span data-ttu-id="da081-121">有关详细信息，请参阅[传出 AS2 消息的协议解析](../core/agreement-resolution-for-outgoing-as2-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="da081-121">For more information, see [Agreement Resolution for Outgoing AS2 Messages](../core/agreement-resolution-for-outgoing-as2-messages.md).</span></span>  
  
 <span data-ttu-id="da081-122">AS2 编码器可生成发送 AS2 消息所需的 HTTP 标头集。</span><span class="sxs-lookup"><span data-stu-id="da081-122">The AS2 Encoder builds the set of HTTP headers required to send an AS2 message.</span></span> <span data-ttu-id="da081-123">它将这些标头添加到 `HTTP.UserHttpHeaders` 上下文属性中，该属性是标头值的单个字符串。</span><span class="sxs-lookup"><span data-stu-id="da081-123">It adds these headers to the `HTTP.UserHttpHeaders` context property, which is a single string of header values.</span></span> <span data-ttu-id="da081-124">AS2 编码器将在 HTTP.UserHttpHeaders 中生成以下 AS2 标头。</span><span class="sxs-lookup"><span data-stu-id="da081-124">The AS2 Encoder builds the following AS2 headers in HTTP.UserHttpHeaders.</span></span> <span data-ttu-id="da081-125">这些标头必须包含在 AS2 消息中。</span><span class="sxs-lookup"><span data-stu-id="da081-125">These headers must be in the AS2 messages.</span></span>  
  
- <span data-ttu-id="da081-126">AS2-To</span><span class="sxs-lookup"><span data-stu-id="da081-126">AS2-To</span></span>  
  
- <span data-ttu-id="da081-127">AS2-From</span><span class="sxs-lookup"><span data-stu-id="da081-127">AS2-From</span></span>  
  
- <span data-ttu-id="da081-128">AS2-Version</span><span class="sxs-lookup"><span data-stu-id="da081-128">AS2-Version</span></span>  
  
- <span data-ttu-id="da081-129">MessageID</span><span class="sxs-lookup"><span data-stu-id="da081-129">MessageID</span></span>  
  
- <span data-ttu-id="da081-130">OriginalMessageID（仅限 MDN）</span><span class="sxs-lookup"><span data-stu-id="da081-130">OriginalMessageID (for MDNs only)</span></span>  
  
  <span data-ttu-id="da081-131">如果**请求 MDN**属性后，管道会将处置-到通知、 回执送达选项和 Signed-receipt-micalg 即用的 AS2 标头中的相应属性; 和它的值将消息中设置如果将设置为"pcks7 签名"的签名回执协议 AS2 标头**请求经过签名的 MDN**属性处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="da081-131">If the **Request MDN** property is checked, the pipeline will set the Disposition-Notification-To, Receipt-Delivery-Option, and Signed-Receipt-MICalg AS2 headers in the message to the values in the corresponding properties; and it will set the Signed-Receipt-Protocol AS2 header to "pcks7-signature" if the **Request signed MDN** property is checked.</span></span>  
  
  <span data-ttu-id="da081-132">如果 `HTTP.UserHttpHeaders` 上下文属性不存在，则 AS2 编码器将创建该属性。</span><span class="sxs-lookup"><span data-stu-id="da081-132">If the `HTTP.UserHttpHeaders` context property does not exist, the AS2 Encoder will create it.</span></span> <span data-ttu-id="da081-133">如果 `HTTP.UserHttpHeaders` 已存在，则 AS2 编码器将使用它，而不是创建它。</span><span class="sxs-lookup"><span data-stu-id="da081-133">If `HTTP.UserHttpHeaders` already exists, the AS2 Encoder will use it, rather than creating it.</span></span> <span data-ttu-id="da081-134">如果创建 `HTTP.UserHttpHeaders` 并将标头写入该属性，然后将该属性写入消息的上下文，AS2 编码器将使用这些标头，并且这些标头的优先级将高于其他源中的标头。</span><span class="sxs-lookup"><span data-stu-id="da081-134">If you create `HTTP.UserHttpHeaders`, write headers to it, and then write it to the context of the message, the AS2 Encoder will use those headers, and they will take priority over headers from other sources.</span></span> <span data-ttu-id="da081-135">但 AS2-From 标头是一个例外，它始终来自协议属性。</span><span class="sxs-lookup"><span data-stu-id="da081-135">The exception to that is the AS2-From header, which is always taken from the agreement properties.</span></span>  
  
  <span data-ttu-id="da081-136">如果 AS2 标头不在 `HTTP.UserHttpHeaders` 中，则 AS2 编码器会从单个上下文属性添加该标头。</span><span class="sxs-lookup"><span data-stu-id="da081-136">If an AS2 header is not in `HTTP.UserHttpHeaders`, the AS2 Encoder will add it from single context properties.</span></span> <span data-ttu-id="da081-137">也就是说，您可以通过将属性升级或写入消息的上下文来添加 AS2 标头（如果这些标头尚不在 `HTTP.UserHttpHeaders` 中）。</span><span class="sxs-lookup"><span data-stu-id="da081-137">This means that you can add AS2 headers by promoting or writing them to the context of the message (if they are not already in `HTTP.UserHttpHeaders`).</span></span> <span data-ttu-id="da081-138">如果 AS2 标头既不在 `HTTP.UserHttpHeaders` 中，也没有作为属性存在于上下文中，则 AS2 编码器会从协议属性将该标头添加到 `HTTP.UserHttpHeaders` 中。</span><span class="sxs-lookup"><span data-stu-id="da081-138">If an AS2 header is neither in `HTTP.UserHttpHeaders`, nor present as a property in the context, the AS2 Encoder will add it from agreement properties into `HTTP.UserHttpHeaders`.</span></span>  
  
  <span data-ttu-id="da081-139">AS2 编码器在 `HTTP.UserHttpHeaders` 属性中生成标头后，它会将该属性写入消息的上下文。</span><span class="sxs-lookup"><span data-stu-id="da081-139">After the AS2 Encoder builds the headers in the `HTTP.UserHttpHeaders` property, it writes it to the context of the message.</span></span> <span data-ttu-id="da081-140">HTTP 适配器提取 `HTTP.UserHttpHeaders`，并将 `HTTP.UserHttpHeaders` 中的标头值预置到消息中。</span><span class="sxs-lookup"><span data-stu-id="da081-140">The HTTP Adapter picks up `HTTP.UserHttpHeaders`, and prepends the header values from `HTTP.UserHttpHeaders` into the message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da081-141">AS2 传输仅用于 HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="da081-141">AS2 transport is intended to work only with the HTTP adapter.</span></span> <span data-ttu-id="da081-142">然而，如果您手动设置了相应的上下文属性，则可以使用 FILE 适配器传输 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="da081-142">However, if you manually set the appropriate context properties, you can use the FILE Adapter to transport AS2 messages.</span></span> <span data-ttu-id="da081-143">有关详细信息，请参阅[通过 FILE 发送端口发送 AS2 消息](../core/sending-an-as2-message-over-a-file-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="da081-143">For more information, see [Sending an AS2 Message over a FILE Send Port](../core/sending-an-as2-message-over-a-file-send-port.md).</span></span>  
  
## <a name="processing-the-returned-mdn"></a><span data-ttu-id="da081-144">处理返回的 MDN</span><span class="sxs-lookup"><span data-stu-id="da081-144">Processing the Returned MDN</span></span>  
 <span data-ttu-id="da081-145">如果 MDN 已启用，则与双向发送端口相关联的接收管道将从接收 AS2 消息的参与方接收 MDN。</span><span class="sxs-lookup"><span data-stu-id="da081-145">If an MDN is enabled, the receive pipeline associated with the two-way send port receives the MDN from the party that receives the AS2 message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da081-146">有关 AS2 发送管道对传入的 Mdn 执行处理的详细信息，请参阅[发送传出的 MDN](../core/sending-an-outgoing-mdn.md)。</span><span class="sxs-lookup"><span data-stu-id="da081-146">For more information about the processing that the AS2 send pipelines perform on incoming MDNs, see [Sending an Outgoing MDN](../core/sending-an-outgoing-mdn.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da081-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="da081-147">See Also</span></span>  
 [<span data-ttu-id="da081-148">BizTalk Server 如何发送 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="da081-148">How BizTalk Server Sends AS2 Messages</span></span>](../core/how-biztalk-server-sends-as2-messages.md)