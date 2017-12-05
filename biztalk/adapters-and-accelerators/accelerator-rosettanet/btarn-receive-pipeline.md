---
title: "BTARN 接收管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BTARN, receive pipelines
- RNMimeDecoder component
- ReceiveMessageNonRepudiate component
- RNDAsm component
- receive pipelines, message flow
- RNPartyRes component
- receive pipelines, BTARN
- MessageUpdater component
- messages, message flow
ms.assetid: 811f2a6a-ddd2-49cc-a00b-4c9d0110a0d1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db4bc69348cfb99b5e7cebb07c65e05a0513cd0e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="btarn-receive-pipeline"></a><span data-ttu-id="d17a3-102">BTARN 接收管道</span><span class="sxs-lookup"><span data-stu-id="d17a3-102">BTARN Receive Pipeline</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="d17a3-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]执行 RosettaNet 实现框架 (RNIF) 与 RNIFReceive 管道 (RNIFReceive.btp) 都接收到消息。</span><span class="sxs-lookup"><span data-stu-id="d17a3-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] performs RosettaNet Implementation Framework (RNIF) message reception with the RNIFReceive pipeline (RNIFReceive.btp).</span></span> <span data-ttu-id="d17a3-104">接收管道包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="d17a3-104">The receive pipeline includes the following components:</span></span>  
  
-   <span data-ttu-id="d17a3-105">ReceiveMessageNonRepudiate</span><span class="sxs-lookup"><span data-stu-id="d17a3-105">ReceiveMessageNonRepudiate</span></span>  
  
-   <span data-ttu-id="d17a3-106">RNMimeDecoder（MIME 预处理器/解码器）</span><span class="sxs-lookup"><span data-stu-id="d17a3-106">RNMimeDecoder (MIME Preprocessor/Decoder)</span></span>  
  
-   <span data-ttu-id="d17a3-107">RNDAsm（XML 拆装器）</span><span class="sxs-lookup"><span data-stu-id="d17a3-107">RNDAsm (XML Disassembler)</span></span>  
  
-   <span data-ttu-id="d17a3-108">RNPartyRes（参与方解析组件）</span><span class="sxs-lookup"><span data-stu-id="d17a3-108">RNPartyRes (Party Resolution component)</span></span>  
  
-   <span data-ttu-id="d17a3-109">MessageUpdater</span><span class="sxs-lookup"><span data-stu-id="d17a3-109">MessageUpdater</span></span>  
  
## <a name="receivemessagenonrepudiate"></a><span data-ttu-id="d17a3-110">ReceiveMessageNonRepudiate</span><span class="sxs-lookup"><span data-stu-id="d17a3-110">ReceiveMessageNonRepudiate</span></span>  
 <span data-ttu-id="d17a3-111">此组件 MessageStorageIn 表中存储对收到的消息。</span><span class="sxs-lookup"><span data-stu-id="d17a3-111">This component stores the received message in the MessageStorageIn table.</span></span> <span data-ttu-id="d17a3-112">此组件执行由 RNIF 标准所需的不可否认性处理。</span><span class="sxs-lookup"><span data-stu-id="d17a3-112">This component performs the non-repudiation processing required by the RNIF standards.</span></span>  
  
## <a name="rnmimedecoder"></a><span data-ttu-id="d17a3-113">RNMimeDecoder</span><span class="sxs-lookup"><span data-stu-id="d17a3-113">RNMimeDecoder</span></span>  
 <span data-ttu-id="d17a3-114">此组件基于上本机 BizTalk Server MIME 预处理器/解码器。</span><span class="sxs-lookup"><span data-stu-id="d17a3-114">This component is based on the native BizTalk Server MIME Preprocessor/Decoder.</span></span> <span data-ttu-id="d17a3-115">RNMimeDecoder 添加 RNIF 处理的以下功能：</span><span class="sxs-lookup"><span data-stu-id="d17a3-115">RNMimeDecoder adds the following functionality for RNIF processing:</span></span>  
  
-   <span data-ttu-id="d17a3-116">有关 RNIF 2.01 解密的服务内容和附件，如果它们存在。</span><span class="sxs-lookup"><span data-stu-id="d17a3-116">For RNIF 2.01, decrypts the service content and attachments, if they are present.</span></span>  
  
-   <span data-ttu-id="d17a3-117">针对 RNIF 1.1 处理 8 字节标头和负载末尾的分离的签名标头。</span><span class="sxs-lookup"><span data-stu-id="d17a3-117">For RNIF 1.1, handles the 8-byte header and the detached signature header at the end of the payload.</span></span>  
  
 <span data-ttu-id="d17a3-118">有关本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]预处理器/解码器，请参阅 BizTalk Server 帮助中的"MIME/SMIME 的解码器管道组件"。</span><span class="sxs-lookup"><span data-stu-id="d17a3-118">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] preprocessor/decoder, see "MIME/SMIME Decoder Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="rndasm"></a><span data-ttu-id="d17a3-119">RNDAsm</span><span class="sxs-lookup"><span data-stu-id="d17a3-119">RNDAsm</span></span>  
 <span data-ttu-id="d17a3-120">此组件基于本机的 BizTalk Server XML 反汇编程序。</span><span class="sxs-lookup"><span data-stu-id="d17a3-120">This component is based on the native BizTalk Server XML Disassembler.</span></span> <span data-ttu-id="d17a3-121">RNDAsm 添加 RNIF 处理的以下功能：</span><span class="sxs-lookup"><span data-stu-id="d17a3-121">RNDAsm adds the following functionality for RNIF processing:</span></span>  
  
-   <span data-ttu-id="d17a3-122">如果传入的文档的 DOCTYPE 标头，此组件将从其生成命名空间，并将传入的文档中的所有节点都移至该命名空间。</span><span class="sxs-lookup"><span data-stu-id="d17a3-122">If an incoming document has a DOCTYPE header, this component generates a namespace from it and moves all nodes in the incoming document to that namespace.</span></span>  
  
-   <span data-ttu-id="d17a3-123">执行消息关联，以确定传入消息是否有重复，并生成错误消息，如果消息已重复。</span><span class="sxs-lookup"><span data-stu-id="d17a3-123">Performs message correlation to determine whether an incoming message is a duplicate, and generates an error message if the message is a duplicate.</span></span>  
  
-   <span data-ttu-id="d17a3-124">将附件存储为消息的其他部分。</span><span class="sxs-lookup"><span data-stu-id="d17a3-124">Stores attachments as additional parts of the message.</span></span>  
  
-   <span data-ttu-id="d17a3-125">提升消息属性。</span><span class="sxs-lookup"><span data-stu-id="d17a3-125">Promotes message properties.</span></span>  
  
 <span data-ttu-id="d17a3-126">有关本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]反汇编程序，请参阅 BizTalk Server 帮助中的"XML 的反汇编程序管道组件"。</span><span class="sxs-lookup"><span data-stu-id="d17a3-126">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Disassembler, see "XML Disassembler Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="rnpartyres"></a><span data-ttu-id="d17a3-127">RNPartyRes</span><span class="sxs-lookup"><span data-stu-id="d17a3-127">RNPartyRes</span></span>  
 <span data-ttu-id="d17a3-128">此组件基于本机的 BizTalk Server 参与方解析组件。</span><span class="sxs-lookup"><span data-stu-id="d17a3-128">This component is based on the native BizTalk Server Party Resolution component.</span></span> <span data-ttu-id="d17a3-129">RNPartyRes 添加 RNIF 处理的以下功能：</span><span class="sxs-lookup"><span data-stu-id="d17a3-129">RNPartyRes adds the following functionality for RNIF processing:</span></span>  
  
-   <span data-ttu-id="d17a3-130">如果传入的消息登录到 BizTalk 方会将发件人证书映射。</span><span class="sxs-lookup"><span data-stu-id="d17a3-130">Maps the sender certificate if the incoming message is signed to a BizTalk party.</span></span> <span data-ttu-id="d17a3-131">如果传入的消息未进行签名，并为其允许的贸易合作伙伴协议，该组件检索发件人方从传递标头 RNIF 2.01 或服务标头 RNIF 1.1。</span><span class="sxs-lookup"><span data-stu-id="d17a3-131">If the incoming message is not signed, and the trading partner agreement allows for it, this component retrieves the sender party from the Delivery header for RNIF 2.01 or the Service header for RNIF 1.1.</span></span>  
  
-   <span data-ttu-id="d17a3-132">验证发件人存在和发件人已与主组织贸易合作伙伴协议。</span><span class="sxs-lookup"><span data-stu-id="d17a3-132">Validates that the sender exists and that the sender has a trading partner agreement with the home organization.</span></span>  
  
 <span data-ttu-id="d17a3-133">有关本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]方解析组件，请参阅 BizTalk Server 帮助中的"方的解析管道组件"。</span><span class="sxs-lookup"><span data-stu-id="d17a3-133">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] party resolution component, see "Party Resolution Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="messageupdater"></a><span data-ttu-id="d17a3-134">MessageUpdater</span><span class="sxs-lookup"><span data-stu-id="d17a3-134">MessageUpdater</span></span>  
 <span data-ttu-id="d17a3-135">此组件将添加 RNIF 处理的以下功能：</span><span class="sxs-lookup"><span data-stu-id="d17a3-135">This component adds the following functionality for RNIF processing:</span></span>  
  
-   <span data-ttu-id="d17a3-136">使用 PIP 代码、 PIP 版本、 源方、 目标方和已存储的 ReceiveMessageNonRepudiate 组件的网络消息的消息跟踪 ID 有关的详细信息更新 MessageStorageIn 表。</span><span class="sxs-lookup"><span data-stu-id="d17a3-136">Updates the MessageStorageIn table with details about the PIP Code, PIP Version, Source Party, Destination Party, and Message Tracking ID of the wire message that was stored by the ReceiveMessageNonRepudiate component.</span></span>  
  
-   <span data-ttu-id="d17a3-137">如果 PIP 不要求不可否认性，则将相应记录标记为删除，设置 `ToBePurged = True`。</span><span class="sxs-lookup"><span data-stu-id="d17a3-137">If the PIP does not require non-repudiation, marks the record for deletion, setting `ToBePurged = True`.</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="d17a3-138">消息流</span><span class="sxs-lookup"><span data-stu-id="d17a3-138">Message Flow</span></span>  
 <span data-ttu-id="d17a3-139">消息流通过 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 接收管道的步骤如下：</span><span class="sxs-lookup"><span data-stu-id="d17a3-139">The message flow through the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] receive pipeline is as follows:</span></span>  
  
1.  <span data-ttu-id="d17a3-140">HTTP 适配器接收 RNIF 1.1 对象或通过 HTTP POST RNIF 2.01 业务消息。</span><span class="sxs-lookup"><span data-stu-id="d17a3-140">The HTTP adapter receives an RNIF 1.1 object or an RNIF 2.01 business message through HTTP POST.</span></span>  
  
2.  <span data-ttu-id="d17a3-141">如果适配器成功接收消息时，适配器提取 RosettaNet 对象或业务消息，并将它路由到接收管道。</span><span class="sxs-lookup"><span data-stu-id="d17a3-141">If the adapter successfully receives the message, the adapter extracts the RosettaNet object or business message, and routes it to the receive pipeline.</span></span>  
  
3.  <span data-ttu-id="d17a3-142">如果将对象或业务消息进行签名，MIME 预处理器/解码器中删除签名。</span><span class="sxs-lookup"><span data-stu-id="d17a3-142">If the object or business message is signed, the MIME Preprocessor/Decoder removes the signature.</span></span>  
  
4.  <span data-ttu-id="d17a3-143">如果签名有效，拆装器会读取该前导码。</span><span class="sxs-lookup"><span data-stu-id="d17a3-143">If the signature is valid, the disassembler reads the preamble.</span></span>  
  
5.  <span data-ttu-id="d17a3-144">如果消息已操作消息，并且需要不可否认性 (**的起点和内容的不可否认性**过程配置设置中的设置是`True`)，解码器计算并仍然存在摘要。</span><span class="sxs-lookup"><span data-stu-id="d17a3-144">If the message is an action message, and non-repudiation is required (the **Non-Repudiation of Origin and Content** setting in the process configuration settings is `True`), the Decoder calculates and persists the digest.</span></span>  
  
6.  <span data-ttu-id="d17a3-145">反汇编程序验证该前导码 （与消息 （消息） 的指导原则和全局变量中的前导码架构）。</span><span class="sxs-lookup"><span data-stu-id="d17a3-145">The disassembler validates the preamble (with message (MSG) guidelines and the preamble schema in the global variables).</span></span>  
  
7.  <span data-ttu-id="d17a3-146">有关 RNIF 2.01 反汇编程序读取传递标头，并验证在全局变量中使用的消息准则和传递标头架构的标头。</span><span class="sxs-lookup"><span data-stu-id="d17a3-146">For RNIF 2.01, the disassembler reads the delivery header, and validates the header using the MSG guidelines and the delivery header schema in the global variables.</span></span>  
  
8.  <span data-ttu-id="d17a3-147">有关 RNIF 2.01 反汇编程序从传递头中提取的合作伙伴信息，并检查要验证属于合作伙伴的签名。</span><span class="sxs-lookup"><span data-stu-id="d17a3-147">For RNIF 2.01, the disassembler extracts the partner information from the delivery header, and examines the signature to verify that it belongs to the partner.</span></span>  
  
9. <span data-ttu-id="d17a3-148">有关 RNIF 2.01 负载进行加密，如果解码器解密负载容器。</span><span class="sxs-lookup"><span data-stu-id="d17a3-148">For RNIF 2.01, if the payload is encrypted, the decoder decrypts the payload container.</span></span>  
  
10. <span data-ttu-id="d17a3-149">反汇编程序读取服务标头，并验证在全局变量中使用的消息准则和服务标头架构的标头。</span><span class="sxs-lookup"><span data-stu-id="d17a3-149">The disassembler reads the service header, and validates the header using the MSG guidelines and the service header schema in the global variables.</span></span>  
  
11. <span data-ttu-id="d17a3-150">RNIF 1.1，拆装器提取合作伙伴信息从服务标头，并检查要验证属于合作伙伴的签名。</span><span class="sxs-lookup"><span data-stu-id="d17a3-150">For RNIF 1.1, the disassembler extracts the partner information from the service header, and examines the signature to verify that it belongs to the partner.</span></span>  
  
12. <span data-ttu-id="d17a3-151">拆装器检查是否得到的 PIP 授权合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="d17a3-151">The disassembler checks whether the partner is authorized for the PIP.</span></span> <span data-ttu-id="d17a3-152">如果没有，拆装器将答复 HTTP 自检 HTTP 403 条状态消息，如有必要，并会产生错误。</span><span class="sxs-lookup"><span data-stu-id="d17a3-152">If not, the disassembler will reply an HTTP POST with an HTTP 403 status message, if necessary, and post an error.</span></span>  
  
13. <span data-ttu-id="d17a3-153">如果消息已签名的操作消息和**的起点和内容的不可否认性**设置为`True`，ReceiveMessageNonRepudiate 组件仍然存在 MessageStorageIn 表中的原始消息。</span><span class="sxs-lookup"><span data-stu-id="d17a3-153">If the message is a signed action message and **Non-Repudiation of Origin and Content** is set to `True`, the ReceiveMessageNonRepudiate component persists the original message in the MessageStorageIn table.</span></span>  
  
14. <span data-ttu-id="d17a3-154">如果消息已签名的信号消息和**不可否认性所需**设置为`True`，ReceiveMessageNonRepudiate 组件仍然存在 MessageStorageIn 表中的信号消息。</span><span class="sxs-lookup"><span data-stu-id="d17a3-154">If the message is a signed signal message and **Non-Repudiation Required** is set to `True`, the ReceiveMessageNonRepudiate component persists the signal message in the MessageStorageIn table.</span></span>  
  
15. <span data-ttu-id="d17a3-155">如果消息已不可否认性 MessageStorageIn 表中保持不变，MessageUpdater 使用消息的过程配置的属性更新 MessageStorageIn 表。</span><span class="sxs-lookup"><span data-stu-id="d17a3-155">If the message was persisted in the MessageStorageIn table for non-repudiation, the MessageUpdater updates the MessageStorageIn table with properties of the process configuration of the message.</span></span>  
  
16. <span data-ttu-id="d17a3-156">如果重复收到了以前处理过的操作消息，则 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将发布出错信息。</span><span class="sxs-lookup"><span data-stu-id="d17a3-156">If the message is an action message that is a duplicate of a previously processed action message, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] will post an error.</span></span>  
  
17. <span data-ttu-id="d17a3-157">有关 RNIF 2.01 解码器将解密负载，如果操作消息进行加密，并且没有之间的 HTTP 的同步和 PIP 的同步要求匹配。</span><span class="sxs-lookup"><span data-stu-id="d17a3-157">For RNIF 2.01, the decoder will decrypt the payload if the action message is encrypted and there is a match between the HTTP synchronicity and PIP synchronicity requirements.</span></span>  
  
18. <span data-ttu-id="d17a3-158">反汇编程序读取服务内容，并对它使用消息的指导原则和架构进行验证。</span><span class="sxs-lookup"><span data-stu-id="d17a3-158">The disassembler reads the service content, and validates it using the MSG guidelines and the schema.</span></span>  
  
19. <span data-ttu-id="d17a3-159">有关 RNIF 2.01 拆装器验证清单有效的内容 ID 存在。</span><span class="sxs-lookup"><span data-stu-id="d17a3-159">For RNIF 2.01, the disassembler verifies that the manifest is valid and the content ID is present.</span></span>  
  
20. <span data-ttu-id="d17a3-160">对于 RNIF 2.01 拆装器将读取的任何附件。</span><span class="sxs-lookup"><span data-stu-id="d17a3-160">For RNIF 2.01, the disassembler will read any attachments.</span></span>  
  
21. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="d17a3-161"> 将 RosettaNet 头、服务内容和附件路由到公用流程。</span><span class="sxs-lookup"><span data-stu-id="d17a3-161"> routes the RosettaNet headers, service content, and attachments to the public process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d17a3-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d17a3-162">See Also</span></span>  
 [<span data-ttu-id="d17a3-163">BTARN 中的消息处理</span><span class="sxs-lookup"><span data-stu-id="d17a3-163">Message Processing in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)