---
title: 生成传出 MDN |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12d7da1c-0d3c-42d4-9388-29f499353d13
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a903cc72a41362f6843449a4d635878706f2ea1e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247949"
---
# <a name="generating-an-outgoing-mdn"></a><span data-ttu-id="fe819-102">生成传出 MDN</span><span class="sxs-lookup"><span data-stu-id="fe819-102">Generating an Outgoing MDN</span></span>
<span data-ttu-id="fe819-103">AS2 接收管道会对传入消息生成一个 MDN（消息处置通知）响应。</span><span class="sxs-lookup"><span data-stu-id="fe819-103">The AS2 receive pipelines generate an MDN (Message Disposition Notification) response for an incoming message.</span></span> <span data-ttu-id="fe819-104">这是由 AS2EDIReceive 接收管道（响应 EDI 编码的消息）中的 EDI 拆装器管道组件或 AS2Receive 接收管道中的 AS2 拆装器管道组件（响应非 EDI 编码的消息）执行的。</span><span class="sxs-lookup"><span data-stu-id="fe819-104">This is performed by the EDI Disassembler pipeline component in the AS2EDIReceive receive pipeline (in response to an EDI-encoded message) or the AS2 Disassembler pipeline component in the AS2Receive receive pipeline (in response to a non-EDI-encoded message).</span></span>  
  
## <a name="when-and-how-an-mdn-is-generated"></a><span data-ttu-id="fe819-105">何时以及如何生成 MDN</span><span class="sxs-lookup"><span data-stu-id="fe819-105">When and How an MDN is Generated</span></span>  
 <span data-ttu-id="fe819-106">MDN 一般基于原始 AS2 消息中的 AS2 标头生成，如下所述：</span><span class="sxs-lookup"><span data-stu-id="fe819-106">An MDN is normally generated based upon the AS2 headers in the original AS2 message, as follows:</span></span>  
  
-   <span data-ttu-id="fe819-107">如果 AS2 消息中具有 Disposition-Notification-To 标头，则将发送 MDN。</span><span class="sxs-lookup"><span data-stu-id="fe819-107">An MDN will be sent if the Disposition-Notification-To header is present in the AS2 message.</span></span>  
  
-   <span data-ttu-id="fe819-108">如果消息中具有 Disposition-Notification-To 和 Receipt-Delivery-Option 标头，则将异步发送 MDN。</span><span class="sxs-lookup"><span data-stu-id="fe819-108">If the Disposition-Notification-To header and the Receipt-Delivery-Option header are present in the message, the MDN will be sent asynchronously.</span></span> <span data-ttu-id="fe819-109">通过不同于原始消息所用连接的其他连接将它发送到 Receipt-Delivery-Option 标头中的 URL。</span><span class="sxs-lookup"><span data-stu-id="fe819-109">It will be sent to the URL in the Receipt-Delivery-Option header, over a different connection than the original message.</span></span>  
  
-   <span data-ttu-id="fe819-110">如果消息中具有 Disposition-Notification-To 标头，但不存在 Receipt-Delivery-Option 标头，则将通过原始消息所用同一连接同步发送 MDN。</span><span class="sxs-lookup"><span data-stu-id="fe819-110">If the Disposition-Notification-To header is present in the message, but the Receipt-Delivery-Option header is not present in the message, the MDN will be sent synchronously over the same connection as the original message.</span></span>  
  
 <span data-ttu-id="fe819-111">拆装器将从接收到的 AS2 消息中的 AS2-To 标头创建 MDN 中的 AS2-From 标头，并从接收到的 AS2 消息中的 AS2-From 标头创建 MDN 中的 AS2-To 标头。</span><span class="sxs-lookup"><span data-stu-id="fe819-111">The Disassembler creates the AS2-From header in the MDN from the AS2-To header in the received AS2 message, and it creates the AS2-To header in the MDN from the AS2-From header in the received AS2 message.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="fe819-112">使你可以覆盖这些设置，指定是否将生成 MDN 并将如何生成基于参与方的 AS2 协议属性。</span><span class="sxs-lookup"><span data-stu-id="fe819-112"> enables you to override these settings, specifying whether an MDN will be generated and how it will be generated based upon a party's AS2 agreement properties.</span></span> <span data-ttu-id="fe819-113">重写在消息中使用的 AS2 标头设置**使用验证和 MDN 的协议设置，而不是消息标头**的单向 AS2 协议选项卡中的属性**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="fe819-113">You override the AS2 header settings in the message using the **Use agreement settings for validation and MDN instead of message header** property in the one-way AS2 agreement tab of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="fe819-114">通过“替代入站消息属性”，您甚至可在 AS2 标头没有要求 MDN 时也发送 MDN；或者在 AS2 标头指定同步连接时通过异步方式发送 MDN。</span><span class="sxs-lookup"><span data-stu-id="fe819-114">This property enables you to send an MDN even if the AS2 header does not call for one, or to send the MDN asynchronously when the AS2 header specifies a synchronous connection.</span></span>  
  
 <span data-ttu-id="fe819-115">如果你设置**使用验证和 MDN 的协议设置，而不是消息标头**属性、 中的值**请求 MDN**部分**发件人 MDN 设置**页在单向 AS2 协议选项卡中的**协议属性**对话框中将用于将 MDN，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fe819-115">If you set the **Use agreement settings for validation and MDN instead of message header** property, the values in the **Request MDN** section of the **Sender MDN Settings** page in the one-way AS2 agreement tab of the **Agreement Properties** dialog box will be used for the MDN, as follows:</span></span>  
  
-   <span data-ttu-id="fe819-116">如果，则会发送 MDN**请求 MDN**选择属性。</span><span class="sxs-lookup"><span data-stu-id="fe819-116">An MDN will be sent if the **Request MDN** property is selected.</span></span>  
  
-   <span data-ttu-id="fe819-117">如果**请求 MDN**选定属性，则与**请求异步 MDN**选择属性，则会以异步方式发送 MDN。</span><span class="sxs-lookup"><span data-stu-id="fe819-117">If the **Request MDN** property is selected, and the **Request asynchronous MDN** property is selected, the MDN will be sent asynchronously.</span></span> <span data-ttu-id="fe819-118">MDN 将发送到的 URL，**回执送达选项 (URL)** 属性设置为中，通过不同连接比原始消息。</span><span class="sxs-lookup"><span data-stu-id="fe819-118">The MDN will be sent to the URL that the **Receipt-Delivery-Option (URL)** property is set to, over a different connection than the original message.</span></span>  
  
-   <span data-ttu-id="fe819-119">如果**请求 MDN**选择属性，但**请求异步 MDN**不选择属性后，将通过作为原始消息的相同连接以同步方式发送 MDN。</span><span class="sxs-lookup"><span data-stu-id="fe819-119">If the **Request MDN** property is selected, but the **Request asynchronous MDN** property is not selected, the MDN will be sent synchronously over the same connection as the original message.</span></span>  
  
 <span data-ttu-id="fe819-120">如果**使用验证和 MDN 的协议设置，而不是消息标头**设置属性，AS2-从消息中的属性标头将用来生成 MDN，但 AS2-到将被从协议属性和管道会对签名根据 MDN**请求签名的 MDN**属性。</span><span class="sxs-lookup"><span data-stu-id="fe819-120">If the **Use agreement settings for validation and MDN instead of message header** property is set, the AS2-From property in the message header will be used in generating the MDN, but AS2-To will be taken from the agreement properties, and the pipeline will sign the MDN according to the **Request Signed MDN** property.</span></span> <span data-ttu-id="fe819-121">AS2 标头对应于协议属性，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fe819-121">The AS2 headers correspond to the agreement properties as follows:</span></span>  
  
|<span data-ttu-id="fe819-122">协议属性</span><span class="sxs-lookup"><span data-stu-id="fe819-122">Agreement Property</span></span>|<span data-ttu-id="fe819-123">消息中的 AS2 标头</span><span class="sxs-lookup"><span data-stu-id="fe819-123">AS2 Header in the Message</span></span>|  
|------------------------|-------------------------------|  
|<span data-ttu-id="fe819-124">生成 MDN</span><span class="sxs-lookup"><span data-stu-id="fe819-124">Generate MDN</span></span>|<span data-ttu-id="fe819-125">Disposition-Notification-To</span><span class="sxs-lookup"><span data-stu-id="fe819-125">Disposition-Notification-To</span></span>|  
|<span data-ttu-id="fe819-126">对 MDN 签名</span><span class="sxs-lookup"><span data-stu-id="fe819-126">Sign MDN</span></span>|<span data-ttu-id="fe819-127">Signed-Receipt-Protocol</span><span class="sxs-lookup"><span data-stu-id="fe819-127">Signed-Receipt-Protocol</span></span>|  
|<span data-ttu-id="fe819-128">Receipt-Delivery-Option</span><span class="sxs-lookup"><span data-stu-id="fe819-128">Receipt-Delivery-Option</span></span>|<span data-ttu-id="fe819-129">Receipt-Delivery-Option</span><span class="sxs-lookup"><span data-stu-id="fe819-129">Receipt-Delivery-Option</span></span>|  
  
 <span data-ttu-id="fe819-130">如果已启用 MDN，接收管道将升级下列上下文属性：</span><span class="sxs-lookup"><span data-stu-id="fe819-130">If an MDN is enabled, the receive pipeline will promote the following context properties:</span></span>  
  
-   `EdiIntAS.DispositionMode`  
  
-   `EdiIntAS.DispositionType`  
  
 <span data-ttu-id="fe819-131">若要生成 MDN，必须同时升级这两个上下文属性。</span><span class="sxs-lookup"><span data-stu-id="fe819-131">Both of these context properties must be promoted in order for the MDN to be generated.</span></span> <span data-ttu-id="fe819-132">有关这些上下文属性的详细信息，请参阅[AS2 上下文属性](../core/as2-context-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="fe819-132">For more information about these context properties, see [AS2 Context Properties](../core/as2-context-properties.md).</span></span>  
  
 <span data-ttu-id="fe819-133">如果传入消息中的配置设置和标头不一致，则管道将生成一个负值 MDN。</span><span class="sxs-lookup"><span data-stu-id="fe819-133">If the configuration settings and the headers in the incoming message are inconsistent, the pipeline will generate a negative MDN.</span></span>  
  
 <span data-ttu-id="fe819-134">如果在协议属性中请求 MDN，则即使在 AS2 处理过程中出现错误，接收管道也会尝试发送一个 MDN。</span><span class="sxs-lookup"><span data-stu-id="fe819-134">If the MDN is requested in the agreement properties, the receive pipeline will attempt to send an MDN even if an error occurs in AS2 processing.</span></span>  
  
## <a name="how-the-receive-pipeline-processes-a-generated-mdn"></a><span data-ttu-id="fe819-135">接收管道如何处理生成的 MDN</span><span class="sxs-lookup"><span data-stu-id="fe819-135">How the Receive Pipeline Processes a Generated MDN</span></span>  
 <span data-ttu-id="fe819-136">如果是根据上述规则生成的 MDN，则 AS2EDIReceive 或 AS2Receive 接收管道将按如下所述处理 MDN：</span><span class="sxs-lookup"><span data-stu-id="fe819-136">If an MDN is generated according to the above rules, the AS2EDIReceive or AS2Receive receive pipeline will process the MDN as follows:</span></span>  
  
-   <span data-ttu-id="fe819-137">创建 MDN 的副本（以传输格式）并将其存储在不可否认数据库中（如果在单向 AS2 协议属性中启用了相应选项）。</span><span class="sxs-lookup"><span data-stu-id="fe819-137">Makes a copy of the MDN (in wire format), and stores it in the non-repudiation database, if enabled in the one-way AS2 agreement properties.</span></span>  
  
-   <span data-ttu-id="fe819-138">执行 MIME 处理，其中包括应用数字签名（如果在单向 AS2 协议属性中启用了相应选项）。</span><span class="sxs-lookup"><span data-stu-id="fe819-138">Performs MIME processing, including applying a digital signature, if enabled in the one-way AS2 agreement properties.</span></span>  
  
-   <span data-ttu-id="fe819-139">计算 MIC AS2 消息负载 （消息完整性检查），并将其追加到 MDN 的接收时间内容 MIC 扩展字段。</span><span class="sxs-lookup"><span data-stu-id="fe819-139">Calculates the MIC (Message Integrity Check) for the AS2 message payload and appends it to the Received-content-MIC extension field of the MDN.</span></span> <span data-ttu-id="fe819-140">要应用的 MIC 由传入的消息的签名回执 micalg 标头的算法或**签名算法**属性**发件人 MDN 设置**的单向页协议选项卡**协议属性**（时的入站的消息属性被重写） 的对话框。</span><span class="sxs-lookup"><span data-stu-id="fe819-140">The algorithm to be applied for the MIC is determined by the signed-receipt-micalg header of the incoming message or the **Signing Algorithm** property on the **Sender MDN Settings** page of the one-way agreement tab of the **Agreement Properties** dialog box (when the inbound message properties are overridden).</span></span> <span data-ttu-id="fe819-141">它可以是 SHA1 或 MD5。</span><span class="sxs-lookup"><span data-stu-id="fe819-141">It can be either SHA1 or MD5.</span></span> <span data-ttu-id="fe819-142">该算法的值还包含在 MDN 中。</span><span class="sxs-lookup"><span data-stu-id="fe819-142">The value of the algorithm is also included in the MDN.</span></span>  
  
-   <span data-ttu-id="fe819-143">在不可否认数据库中创建相关条目。</span><span class="sxs-lookup"><span data-stu-id="fe819-143">Makes correlation entries in the non-repudiation database.</span></span>  
  
-   <span data-ttu-id="fe819-144">创建 MDN 消息的副本。</span><span class="sxs-lookup"><span data-stu-id="fe819-144">Makes a copy of the MDN message.</span></span>  
  
-   <span data-ttu-id="fe819-145">如果要以同步方式传输 MDN，管道将设置`EdiIntAS.IsAS2AsynchronousMDN`属性设置为 False; 如果以异步方式，它将属性设置为 True。</span><span class="sxs-lookup"><span data-stu-id="fe819-145">If the MDN is to be transmitted synchronously, the pipeline sets the `EdiIntAS.IsAS2AsynchronousMDN` property to False; if asynchronously, it sets the property to True.</span></span>  
  
-   <span data-ttu-id="fe819-146">与双向关联 AS2Send 发送管道 MDN 是以同步方式传输，如果接收的端口会选取基于 MDN`EdiIntAS.IsAS2AsynchronousMDN`属性 （设置为 False） 和相关令牌。</span><span class="sxs-lookup"><span data-stu-id="fe819-146">If the MDN is to be transmitted synchronously, the AS2Send send pipeline associated with the two-way receive port will pick up the MDN based upon the `EdiIntAS.IsAS2AsynchronousMDN` property (set to False) and the correlation tokens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fe819-147">您还可设置用于订阅传出同步 MDN 的发送端口。</span><span class="sxs-lookup"><span data-stu-id="fe819-147">You can also set up a send port that subscribes to the outgoing synchronous MDN.</span></span> <span data-ttu-id="fe819-148">要执行此操作，请将发送端口筛选器设置为`EdiIntAS.IsAS2MdnResponseMessage==True`。</span><span class="sxs-lookup"><span data-stu-id="fe819-148">To do so, set the send port filter to `EdiIntAS.IsAS2MdnResponseMessage==True`.</span></span>  
  
-   <span data-ttu-id="fe819-149">如果异步传输该 MDN，则接收管道将把该 MDN 路由到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="fe819-149">If the MDN is to be transmitted asynchronously, the receive pipeline routes the MDN to the MessageBox.</span></span> <span data-ttu-id="fe819-150">你必须设置发送端口以订阅 MDN，将发送端口筛选器设置为`IsAS2AsynchronousMdn==True`。</span><span class="sxs-lookup"><span data-stu-id="fe819-150">You must set up a send port to subscribe to the MDN, setting the send port filter to `IsAS2AsynchronousMdn==True`.</span></span> <span data-ttu-id="fe819-151">AS2Send 发送管道将基于该属性和相关标记提取消息。</span><span class="sxs-lookup"><span data-stu-id="fe819-151">The AS2Send send pipeline picks up the message based upon that property and the correlation tokens.</span></span> <span data-ttu-id="fe819-152">如果发送端口是动态的，它将基于消息标头的 Receipt-Delivery-Notification 行中的地址路由该 MDN。</span><span class="sxs-lookup"><span data-stu-id="fe819-152">If the send port is dynamic, it will route the MDN based to the address in the Receipt-Delivery-Notification line in the header of the message.</span></span> <span data-ttu-id="fe819-153">如果发送端口是静态的它将基于发送端口的传输 URI 属性将消息进行路由。</span><span class="sxs-lookup"><span data-stu-id="fe819-153">If the send port is static, it will route the message based upon Transport URI property of the send port.</span></span>  
  
## <a name="mdn-generation-rules"></a><span data-ttu-id="fe819-154">MDN 生成规则</span><span class="sxs-lookup"><span data-stu-id="fe819-154">MDN Generation Rules</span></span>  
 <span data-ttu-id="fe819-155">生成 MDN 时将应用以下规则：</span><span class="sxs-lookup"><span data-stu-id="fe819-155">The following rules apply to MDN generation:</span></span>  
  
-   <span data-ttu-id="fe819-156">当消息发送方特别请求签名回执，但处理该消息的内容过程中出现错误时，消息接收方仍必须返回签名回执，即使事务自身可能无效。</span><span class="sxs-lookup"><span data-stu-id="fe819-156">When a message sender specifically requests a signed receipt, but there is error in processing the contents of the message, the message receiver must still return a signed receipt, even though the transaction itself may not be valid.</span></span> <span data-ttu-id="fe819-157">处理消息内容时的出错原因必须在“disposition-field”中进行设置。</span><span class="sxs-lookup"><span data-stu-id="fe819-157">The reason for the error in processing the contents of the message must be set in the "disposition-field".</span></span>  
  
-   <span data-ttu-id="fe819-158">请求 MDN 回执时，如果显式指定应对该回执签名，但原始消息的接收方无法支持请求的协议格式或请求的 MIC 算法，则应返回签名或未签名的回执。</span><span class="sxs-lookup"><span data-stu-id="fe819-158">When the request for the MDN receipt explicitly specifies that the receipt be signed, but the receiver of the original message cannot support either the requested protocol format or the requested MIC algorithm, then either a signed or unsigned receipt should be returned.</span></span>  
  
-   <span data-ttu-id="fe819-159">如果未显式请求签名，或者，如果接收方的协议无法识别签名回执请求参数，则接收方可能会返回未签名回执、签名回执或无回执。</span><span class="sxs-lookup"><span data-stu-id="fe819-159">When a signature is not explicitly requested, or if the signed receipt request parameter is not recognized by the agreement for the receiving party, then the receiving party may return an unsigned receipt, a signed receipt, or no receipt.</span></span>  
  
## <a name="mic-generation"></a><span data-ttu-id="fe819-160">MIC 生成</span><span class="sxs-lookup"><span data-stu-id="fe819-160">MIC Generation</span></span>  
 <span data-ttu-id="fe819-161">需要一个 MDN 时，原始消息的接收方将生成一个 MIC（消息完整性检查）并将其添加到该 MDN。</span><span class="sxs-lookup"><span data-stu-id="fe819-161">When an MDN is required, the receiver of the original message generates an MIC (Message Integrity Check) and adds it to the MDN.</span></span> <span data-ttu-id="fe819-162">当 EDI 交换是多部分 MIME 内容类型的一部分时，必须在整个多部分内容（包括 EDI 交换和 MIME 标头）中计算该 MIC。</span><span class="sxs-lookup"><span data-stu-id="fe819-162">When the EDI interchange is part of a multi-part MIME content-type, the MIC must be calculated across the entire multi-part content, including the EDI interchange and the MIME headers.</span></span> <span data-ttu-id="fe819-163">对于已加密但未签名的消息，将返回的 MIC 是根据已解密的 MIME 标头和内容计算出来的。</span><span class="sxs-lookup"><span data-stu-id="fe819-163">For encrypted, unsigned messages, the MIC to be returned is calculated on the decrypted MIME header and content.</span></span> <span data-ttu-id="fe819-164">对于未签名且未加密的消息，必须根据无 MIME 标头的消息内容计算该 MIC。</span><span class="sxs-lookup"><span data-stu-id="fe819-164">For unsigned, unencrypted messages, the MIC must be calculated over the message contents without the MIME headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe819-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe819-165">See Also</span></span>  
 [<span data-ttu-id="fe819-166">BizTalk Server 接收 AS2 消息的方式</span><span class="sxs-lookup"><span data-stu-id="fe819-166">How BizTalk Server Receives AS2 Messages</span></span>](../core/how-biztalk-server-receives-as2-messages.md)