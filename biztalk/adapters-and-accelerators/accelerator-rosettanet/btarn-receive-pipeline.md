---
title: BTARN 接收管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53a9b9dd410a6a136b37ef506c9bc975f563a11a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284920"
---
# <a name="btarn-receive-pipeline"></a><span data-ttu-id="be077-102">BTARN 接收管道</span><span class="sxs-lookup"><span data-stu-id="be077-102">BTARN Receive Pipeline</span></span>
<span data-ttu-id="be077-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]执行使用 RNIFReceive 管道 (RNIFReceive.btp) 接收到 RosettaNet 实现框架 (RNIF) 消息。</span><span class="sxs-lookup"><span data-stu-id="be077-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] performs RosettaNet Implementation Framework (RNIF) message reception with the RNIFReceive pipeline (RNIFReceive.btp).</span></span> <span data-ttu-id="be077-104">接收管道包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="be077-104">The receive pipeline includes the following components:</span></span>  
  
-   <span data-ttu-id="be077-105">ReceiveMessageNonRepudiate</span><span class="sxs-lookup"><span data-stu-id="be077-105">ReceiveMessageNonRepudiate</span></span>  
  
-   <span data-ttu-id="be077-106">RNMimeDecoder (MIME Preprocessor/Decoder)</span><span class="sxs-lookup"><span data-stu-id="be077-106">RNMimeDecoder (MIME Preprocessor/Decoder)</span></span>  
  
-   <span data-ttu-id="be077-107">RNDAsm （XML 拆装器）</span><span class="sxs-lookup"><span data-stu-id="be077-107">RNDAsm (XML Disassembler)</span></span>  
  
-   <span data-ttu-id="be077-108">RNPartyRes （参与方解析组件）</span><span class="sxs-lookup"><span data-stu-id="be077-108">RNPartyRes (Party Resolution component)</span></span>  
  
-   <span data-ttu-id="be077-109">MessageUpdater</span><span class="sxs-lookup"><span data-stu-id="be077-109">MessageUpdater</span></span>  
  
## <a name="receivemessagenonrepudiate"></a><span data-ttu-id="be077-110">ReceiveMessageNonRepudiate</span><span class="sxs-lookup"><span data-stu-id="be077-110">ReceiveMessageNonRepudiate</span></span>  
 <span data-ttu-id="be077-111">此组件将接收到的消息存储在 MessageStorageIn 表中。</span><span class="sxs-lookup"><span data-stu-id="be077-111">This component stores the received message in the MessageStorageIn table.</span></span> <span data-ttu-id="be077-112">此组件在执行所需的 RNIF 标准的不可否认处理。</span><span class="sxs-lookup"><span data-stu-id="be077-112">This component performs the non-repudiation processing required by the RNIF standards.</span></span>  
  
## <a name="rnmimedecoder"></a><span data-ttu-id="be077-113">RNMimeDecoder</span><span class="sxs-lookup"><span data-stu-id="be077-113">RNMimeDecoder</span></span>  
 <span data-ttu-id="be077-114">此组件为基础上本机 BizTalk Server MIME 预处理器/解码器。</span><span class="sxs-lookup"><span data-stu-id="be077-114">This component is based on the native BizTalk Server MIME Preprocessor/Decoder.</span></span> <span data-ttu-id="be077-115">RNMimeDecoder 添加 RNIF 处理的以下功能：</span><span class="sxs-lookup"><span data-stu-id="be077-115">RNMimeDecoder adds the following functionality for RNIF processing:</span></span>  
  
- <span data-ttu-id="be077-116">对于 RNIF 2.01 解密服务内容和附件，它们是否存在。</span><span class="sxs-lookup"><span data-stu-id="be077-116">For RNIF 2.01, decrypts the service content and attachments, if they are present.</span></span>  
  
- <span data-ttu-id="be077-117">对于 RNIF 1.1 处理 8 字节标头和有效负载的末尾的分离的签名标头。</span><span class="sxs-lookup"><span data-stu-id="be077-117">For RNIF 1.1, handles the 8-byte header and the detached signature header at the end of the payload.</span></span>  
  
  <span data-ttu-id="be077-118">详细了解本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]预处理器/解码器，请参阅"MIME/SMIME 解码器管道组件"部分中 BizTalk Server 帮助。</span><span class="sxs-lookup"><span data-stu-id="be077-118">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] preprocessor/decoder, see "MIME/SMIME Decoder Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="rndasm"></a><span data-ttu-id="be077-119">RNDAsm</span><span class="sxs-lookup"><span data-stu-id="be077-119">RNDAsm</span></span>  
 <span data-ttu-id="be077-120">此组件基于本机 BizTalk Server XML 拆装器。</span><span class="sxs-lookup"><span data-stu-id="be077-120">This component is based on the native BizTalk Server XML Disassembler.</span></span> <span data-ttu-id="be077-121">RNDAsm 添加 RNIF 处理的以下功能：</span><span class="sxs-lookup"><span data-stu-id="be077-121">RNDAsm adds the following functionality for RNIF processing:</span></span>  
  
- <span data-ttu-id="be077-122">如果传入文档 DOCTYPE 标头，此组件将从其生成命名空间，并将传入文档中的所有节点都移动到该命名空间。</span><span class="sxs-lookup"><span data-stu-id="be077-122">If an incoming document has a DOCTYPE header, this component generates a namespace from it and moves all nodes in the incoming document to that namespace.</span></span>  
  
- <span data-ttu-id="be077-123">执行消息关联，以确定传入消息是否重复，并且如果消息是一个重复，将生成一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="be077-123">Performs message correlation to determine whether an incoming message is a duplicate, and generates an error message if the message is a duplicate.</span></span>  
  
- <span data-ttu-id="be077-124">将附件存储为消息的其他部分。</span><span class="sxs-lookup"><span data-stu-id="be077-124">Stores attachments as additional parts of the message.</span></span>  
  
- <span data-ttu-id="be077-125">升级消息属性。</span><span class="sxs-lookup"><span data-stu-id="be077-125">Promotes message properties.</span></span>  
  
  <span data-ttu-id="be077-126">详细了解本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]拆装器，请参阅 BizTalk Server 帮助中的"XML 的拆装器管道组件"。</span><span class="sxs-lookup"><span data-stu-id="be077-126">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Disassembler, see "XML Disassembler Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="rnpartyres"></a><span data-ttu-id="be077-127">RNPartyRes</span><span class="sxs-lookup"><span data-stu-id="be077-127">RNPartyRes</span></span>  
 <span data-ttu-id="be077-128">此组件基于本机的 BizTalk Server 参与方解析组件。</span><span class="sxs-lookup"><span data-stu-id="be077-128">This component is based on the native BizTalk Server Party Resolution component.</span></span> <span data-ttu-id="be077-129">RNPartyRes 添加 RNIF 处理的以下功能：</span><span class="sxs-lookup"><span data-stu-id="be077-129">RNPartyRes adds the following functionality for RNIF processing:</span></span>  
  
- <span data-ttu-id="be077-130">如果传入消息进行签名到 BizTalk 参与方，映射发件人证书。</span><span class="sxs-lookup"><span data-stu-id="be077-130">Maps the sender certificate if the incoming message is signed to a BizTalk party.</span></span> <span data-ttu-id="be077-131">如果未签名的传入消息，并且贸易合作伙伴协议允许这样做，此组件检索发送方从传递头为 RNIF 2.01 或服务头 RNIF 1.1。</span><span class="sxs-lookup"><span data-stu-id="be077-131">If the incoming message is not signed, and the trading partner agreement allows for it, this component retrieves the sender party from the Delivery header for RNIF 2.01 or the Service header for RNIF 1.1.</span></span>  
  
- <span data-ttu-id="be077-132">验证存在发件人和发件人已与本组织的贸易合作伙伴协议。</span><span class="sxs-lookup"><span data-stu-id="be077-132">Validates that the sender exists and that the sender has a trading partner agreement with the home organization.</span></span>  
  
  <span data-ttu-id="be077-133">详细了解本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]参与方解析组件，请参阅 BizTalk Server 帮助中的"参与方的解析管道组件"。</span><span class="sxs-lookup"><span data-stu-id="be077-133">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] party resolution component, see "Party Resolution Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="messageupdater"></a><span data-ttu-id="be077-134">MessageUpdater</span><span class="sxs-lookup"><span data-stu-id="be077-134">MessageUpdater</span></span>  
 <span data-ttu-id="be077-135">此组件将添加为 RNIF 处理的以下功能：</span><span class="sxs-lookup"><span data-stu-id="be077-135">This component adds the following functionality for RNIF processing:</span></span>  
  
-   <span data-ttu-id="be077-136">使用 PIP 代码、 PIP 版本、 源参与方、 目标参与方和消息跟踪 ID 的网络消息，则 ReceiveMessageNonRepudiate 组件将由存储有关的详细信息更新 MessageStorageIn 表。</span><span class="sxs-lookup"><span data-stu-id="be077-136">Updates the MessageStorageIn table with details about the PIP Code, PIP Version, Source Party, Destination Party, and Message Tracking ID of the wire message that was stored by the ReceiveMessageNonRepudiate component.</span></span>  
  
-   <span data-ttu-id="be077-137">如果 PIP 不要求不可否认，将标记为删除，设置记录`ToBePurged = True`。</span><span class="sxs-lookup"><span data-stu-id="be077-137">If the PIP does not require non-repudiation, marks the record for deletion, setting `ToBePurged = True`.</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="be077-138">消息流</span><span class="sxs-lookup"><span data-stu-id="be077-138">Message Flow</span></span>  
 <span data-ttu-id="be077-139">消息流通过[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]接收管道是按如下所示：</span><span class="sxs-lookup"><span data-stu-id="be077-139">The message flow through the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] receive pipeline is as follows:</span></span>  
  
1. <span data-ttu-id="be077-140">HTTP 适配器接收 RNIF 1.1 对象或通过 HTTP POST 的 RNIF 2.01 业务消息。</span><span class="sxs-lookup"><span data-stu-id="be077-140">The HTTP adapter receives an RNIF 1.1 object or an RNIF 2.01 business message through HTTP POST.</span></span>  
  
2. <span data-ttu-id="be077-141">如果适配器已成功接收消息，适配器将提取 RosettaNet 对象或业务消息，并将其路由到接收管道。</span><span class="sxs-lookup"><span data-stu-id="be077-141">If the adapter successfully receives the message, the adapter extracts the RosettaNet object or business message, and routes it to the receive pipeline.</span></span>  
  
3. <span data-ttu-id="be077-142">如果对象或业务消息已签名，MIME 预处理器/解码器将删除签名。</span><span class="sxs-lookup"><span data-stu-id="be077-142">If the object or business message is signed, the MIME Preprocessor/Decoder removes the signature.</span></span>  
  
4. <span data-ttu-id="be077-143">如果签名有效，拆装器将读取该前导码。</span><span class="sxs-lookup"><span data-stu-id="be077-143">If the signature is valid, the disassembler reads the preamble.</span></span>  
  
5. <span data-ttu-id="be077-144">如果消息是操作消息，并且是必需的不可否认性 (**和内容的不可否认**流程配置设置中的设置是`True`)，则解码器计算并持久保留该摘要。</span><span class="sxs-lookup"><span data-stu-id="be077-144">If the message is an action message, and non-repudiation is required (the **Non-Repudiation of Origin and Content** setting in the process configuration settings is `True`), the Decoder calculates and persists the digest.</span></span>  
  
6. <span data-ttu-id="be077-145">拆装器将验证该前导码 （使用消息 （消息） 指南和全局变量中的前导头架构）。</span><span class="sxs-lookup"><span data-stu-id="be077-145">The disassembler validates the preamble (with message (MSG) guidelines and the preamble schema in the global variables).</span></span>  
  
7. <span data-ttu-id="be077-146">对于 RNIF 2.01，拆装器读取传递头中，并验证在全局变量中使用消息的指导原则和交付标头架构的标头。</span><span class="sxs-lookup"><span data-stu-id="be077-146">For RNIF 2.01, the disassembler reads the delivery header, and validates the header using the MSG guidelines and the delivery header schema in the global variables.</span></span>  
  
8. <span data-ttu-id="be077-147">对于 RNIF 2.01，拆装器从传递头中提取合作伙伴信息并检查要验证属于合作伙伴的签名。</span><span class="sxs-lookup"><span data-stu-id="be077-147">For RNIF 2.01, the disassembler extracts the partner information from the delivery header, and examines the signature to verify that it belongs to the partner.</span></span>  
  
9. <span data-ttu-id="be077-148">对于 RNIF 2.01 负载进行加密，如果解码器解密负载容器。</span><span class="sxs-lookup"><span data-stu-id="be077-148">For RNIF 2.01, if the payload is encrypted, the decoder decrypts the payload container.</span></span>  
  
10. <span data-ttu-id="be077-149">拆装器读取服务头中，并验证在全局变量中使用消息的指导原则和服务头架构的标头。</span><span class="sxs-lookup"><span data-stu-id="be077-149">The disassembler reads the service header, and validates the header using the MSG guidelines and the service header schema in the global variables.</span></span>  
  
11. <span data-ttu-id="be077-150">对于 RNIF 1.1，拆装器从服务头中提取合作伙伴信息并检查要验证属于合作伙伴的签名。</span><span class="sxs-lookup"><span data-stu-id="be077-150">For RNIF 1.1, the disassembler extracts the partner information from the service header, and examines the signature to verify that it belongs to the partner.</span></span>  
  
12. <span data-ttu-id="be077-151">拆装器将检查合作伙伴是否已获得 PIP 的授权。</span><span class="sxs-lookup"><span data-stu-id="be077-151">The disassembler checks whether the partner is authorized for the PIP.</span></span> <span data-ttu-id="be077-152">如果没有，拆装器将回复 HTTP POST HTTP 403 状态消息，如有必要，并发布错误。</span><span class="sxs-lookup"><span data-stu-id="be077-152">If not, the disassembler will reply an HTTP POST with an HTTP 403 status message, if necessary, and post an error.</span></span>  
  
13. <span data-ttu-id="be077-153">如果消息是签名的操作消息和**和内容的不可否认**设置为`True`，则 ReceiveMessageNonRepudiate 组件将仍然存在 MessageStorageIn 表中的原始消息。</span><span class="sxs-lookup"><span data-stu-id="be077-153">If the message is a signed action message and **Non-Repudiation of Origin and Content** is set to `True`, the ReceiveMessageNonRepudiate component persists the original message in the MessageStorageIn table.</span></span>  
  
14. <span data-ttu-id="be077-154">如果消息是签名的信号消息并**要求不可否认**设置为`True`，则 ReceiveMessageNonRepudiate 组件将仍然存在 MessageStorageIn 表中的信号消息。</span><span class="sxs-lookup"><span data-stu-id="be077-154">If the message is a signed signal message and **Non-Repudiation Required** is set to `True`, the ReceiveMessageNonRepudiate component persists the signal message in the MessageStorageIn table.</span></span>  
  
15. <span data-ttu-id="be077-155">如果消息已在不可否认的 MessageStorageIn 表中保持不变，MessageUpdater 使用消息的过程配置的属性更新 MessageStorageIn 表。</span><span class="sxs-lookup"><span data-stu-id="be077-155">If the message was persisted in the MessageStorageIn table for non-repudiation, the MessageUpdater updates the MessageStorageIn table with properties of the process configuration of the message.</span></span>  
  
16. <span data-ttu-id="be077-156">如果消息是与以前处理过的操作消息时，重复的操作消息[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将发布一个错误。</span><span class="sxs-lookup"><span data-stu-id="be077-156">If the message is an action message that is a duplicate of a previously processed action message, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] will post an error.</span></span>  
  
17. <span data-ttu-id="be077-157">为 RNIF 2.01 解码器将解密有效负载，如果对操作消息进行加密，并且没有匹配的 HTTP 的同步和 PIP 的同步要求。</span><span class="sxs-lookup"><span data-stu-id="be077-157">For RNIF 2.01, the decoder will decrypt the payload if the action message is encrypted and there is a match between the HTTP synchronicity and PIP synchronicity requirements.</span></span>  
  
18. <span data-ttu-id="be077-158">拆装器读取服务内容，并对它使用消息的指导原则和架构进行验证。</span><span class="sxs-lookup"><span data-stu-id="be077-158">The disassembler reads the service content, and validates it using the MSG guidelines and the schema.</span></span>  
  
19. <span data-ttu-id="be077-159">对于 RNIF 2.01，该清单是有效和存在的内容 ID，则将验证拆装器。</span><span class="sxs-lookup"><span data-stu-id="be077-159">For RNIF 2.01, the disassembler verifies that the manifest is valid and the content ID is present.</span></span>  
  
20. <span data-ttu-id="be077-160">对于 RNIF 2.01，拆装器将读取任何附件。</span><span class="sxs-lookup"><span data-stu-id="be077-160">For RNIF 2.01, the disassembler will read any attachments.</span></span>  
  
21. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="be077-161">将路由 RosettaNet 标头、 服务内容和附件到公用流程。</span><span class="sxs-lookup"><span data-stu-id="be077-161">routes the RosettaNet headers, service content, and attachments to the public process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be077-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="be077-162">See Also</span></span>  
 [<span data-ttu-id="be077-163">BTARN 中的消息处理</span><span class="sxs-lookup"><span data-stu-id="be077-163">Message Processing in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)