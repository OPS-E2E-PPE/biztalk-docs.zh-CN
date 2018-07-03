---
title: BTARN 发送管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Assembler
- send pipelines, message flow
- DOCTYPE headers
- MIME/SMIME Encoder
- send pipelines, BTARN
- BTARN, send pipelines
- XML Preprocessor
- messages, message flow
ms.assetid: 88562132-0ea4-4b5a-9445-b69f6c84e5ea
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0791ab4714e1e8a9de847a60d17d14e38f095ecf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011630"
---
# <a name="btarn-send-pipeline"></a><span data-ttu-id="3e731-102">BTARN 发送管道</span><span class="sxs-lookup"><span data-stu-id="3e731-102">BTARN Send Pipeline</span></span>
<span data-ttu-id="3e731-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]做好 RNIFSend 管道 (RNIFSend.btp) 中的传输 RosettaNet 实现框架 (RNIF) 消息。</span><span class="sxs-lookup"><span data-stu-id="3e731-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] prepares a RosettaNet Implementation Framework (RNIF) message for transmission in the RNIFSend pipeline (RNIFSend.btp).</span></span> <span data-ttu-id="3e731-104">发送管道包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="3e731-104">The send pipeline includes the following:</span></span>  
  
-   <span data-ttu-id="3e731-105">XML 预处理器</span><span class="sxs-lookup"><span data-stu-id="3e731-105">XML preprocessor</span></span>  
  
-   <span data-ttu-id="3e731-106">XML 组装器</span><span class="sxs-lookup"><span data-stu-id="3e731-106">XML assembler</span></span>  
  
-   <span data-ttu-id="3e731-107">多用途 Internet 邮件扩展插件/安全多用途 Internet 邮件扩展 (MIME/SMIME) 编码器</span><span class="sxs-lookup"><span data-stu-id="3e731-107">Multipurpose Internet Mail Extensions/Secure Multipurpose Internet Mail Extensions (MIME/SMIME) encoder</span></span>  
  
## <a name="xml-preprocessor"></a><span data-ttu-id="3e731-108">XML 预处理器</span><span class="sxs-lookup"><span data-stu-id="3e731-108">XML Preprocessor</span></span>  
 <span data-ttu-id="3e731-109">XML 预处理器将 DOCTYPE 标头添加到消息。</span><span class="sxs-lookup"><span data-stu-id="3e731-109">The XML preprocessor adds a DOCTYPE header to the message.</span></span> <span data-ttu-id="3e731-110">标头标识与消息关联的文档类型定义 (DTD) 架构。</span><span class="sxs-lookup"><span data-stu-id="3e731-110">The header identifies the document type definition (DTD) schema associated with the message.</span></span> <span data-ttu-id="3e731-111">RNIF 规范以便进行 RNIF 传输需要 DOCTYPE 标头的存在。</span><span class="sxs-lookup"><span data-stu-id="3e731-111">The RNIF specification requires the presence of a DOCTYPE header for RNIF transmission.</span></span>  
  
## <a name="xml-assembler"></a><span data-ttu-id="3e731-112">XML 组装器</span><span class="sxs-lookup"><span data-stu-id="3e731-112">XML Assembler</span></span>  
 <span data-ttu-id="3e731-113">XML 组装器基于 BizTalk Server XML 组装器。</span><span class="sxs-lookup"><span data-stu-id="3e731-113">The XML assembler is based on the BizTalk Server XML assembler.</span></span> <span data-ttu-id="3e731-114">它将属性从消息上下文传输回信封和文档。</span><span class="sxs-lookup"><span data-stu-id="3e731-114">It transfers properties from the message context back into envelopes and documents.</span></span> <span data-ttu-id="3e731-115">它从其 XML 部件和附件组装消息。</span><span class="sxs-lookup"><span data-stu-id="3e731-115">It assembles the message from its XML parts and attachments.</span></span> <span data-ttu-id="3e731-116">它不执行消息验证。</span><span class="sxs-lookup"><span data-stu-id="3e731-116">It does not perform message validation.</span></span>  
  
 <span data-ttu-id="3e731-117">详细了解本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]XML 组装器，请参阅 BizTalk Server 帮助中的"XML 的组装器管道组件"。</span><span class="sxs-lookup"><span data-stu-id="3e731-117">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] XML assembler, see "XML Assembler Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="mimesmime-encoder"></a><span data-ttu-id="3e731-118">MIME/SMIME 编码器</span><span class="sxs-lookup"><span data-stu-id="3e731-118">MIME/SMIME Encoder</span></span>  
 <span data-ttu-id="3e731-119">MIME/SMIME 编码器基于 BizTalk Server MIME/SMIME 编码器。</span><span class="sxs-lookup"><span data-stu-id="3e731-119">The MIME/SMIME encoder is based on the BizTalk Server MIME/SMIME Encoder.</span></span> <span data-ttu-id="3e731-120">具体取决于贸易合作伙伴协议和 BizTalk Server MIME/SMIME 编码器的设置中的协议设置[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]编码器执行以下：</span><span class="sxs-lookup"><span data-stu-id="3e731-120">Depending on the protocol settings in the trading partner agreement, and the settings of the BizTalk Server MIME/SMIME Encoder, the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] encoder performs the following:</span></span>  
  
- <span data-ttu-id="3e731-121">将 8 字节二进制标头添加到消息，根据需要为 RNIF 1.1 消息。</span><span class="sxs-lookup"><span data-stu-id="3e731-121">Adds an 8-byte binary header to the message, as required for RNIF 1.1 messages.</span></span>  
  
- <span data-ttu-id="3e731-122">编码的消息部分，并计算摘要。</span><span class="sxs-lookup"><span data-stu-id="3e731-122">Encodes the message parts, and calculates the digest.</span></span>  
  
- <span data-ttu-id="3e731-123">将加密的有效负载 （服务内容以及附件） 或负载容器 （服务内容、 服务头和附件）。</span><span class="sxs-lookup"><span data-stu-id="3e731-123">Encrypts the payload (service content plus attachments), or the payload container (service content plus service header plus attachments).</span></span> <span data-ttu-id="3e731-124">如果设置了**所有端口都编码**上设置**协议**到贸易合作伙伴协议的选项卡`False`，编码器将对只对负载进行加密。</span><span class="sxs-lookup"><span data-stu-id="3e731-124">If you have set the **Encode all ports** setting on the **Protocol** tab of the trading partner agreement to `False`, the encoder will encrypt only the payload.</span></span> <span data-ttu-id="3e731-125">如果设置了**所有端口都编码**将设置为`True`，编码器将对负载容器进行加密。</span><span class="sxs-lookup"><span data-stu-id="3e731-125">If you have set the **Encode all ports** setting to `True`, the encoder will encrypt the payload container.</span></span>  
  
  <span data-ttu-id="3e731-126">详细了解本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MIME/SMIME 编码器，请参阅"MIME/SMIME 编码器管道组件"部分中 BizTalk Server 帮助。</span><span class="sxs-lookup"><span data-stu-id="3e731-126">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] MIME/SMIME Encoder, see "MIME/SMIME Encoder Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="3e731-127">消息流</span><span class="sxs-lookup"><span data-stu-id="3e731-127">Message Flow</span></span>  
 <span data-ttu-id="3e731-128">消息流通过 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 发送管道的步骤如下：</span><span class="sxs-lookup"><span data-stu-id="3e731-128">The message flow through the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] send pipeline is as follows:</span></span>  
  
1.  <span data-ttu-id="3e731-129">如果设置了**所有部分都编码**设置为贸易合作伙伴协议的`True`，MIME / SMIME 编码器将对所有消息部分进行都都编码。</span><span class="sxs-lookup"><span data-stu-id="3e731-129">If you have set the **Encode all parts** setting of the trading partner agreement to `True`, the MIME/SMIME encoder will encode all message parts.</span></span> <span data-ttu-id="3e731-130">它将使用在中设置的编码方法`Encoding`协议的属性。</span><span class="sxs-lookup"><span data-stu-id="3e731-130">It will use the encoding method set in the `Encoding` property of the agreement.</span></span>  
  
2.  <span data-ttu-id="3e731-131">对于 RNIF 2.01，如果消息是操作消息，并且没有附件，编码器将执行以下操作为每个附件：</span><span class="sxs-lookup"><span data-stu-id="3e731-131">For RNIF 2.01, if the message is an action message and there is an attachment, the encoder will do the following for each attachment:</span></span>  
  
    1.  <span data-ttu-id="3e731-132">如果附件是二进制，编码器将对其进行编码。</span><span class="sxs-lookup"><span data-stu-id="3e731-132">If the attachment is binary, the encoder will encode it.</span></span>  
  
    2.  <span data-ttu-id="3e731-133">编码器将生成的附件的内容 ID。</span><span class="sxs-lookup"><span data-stu-id="3e731-133">The encoder will generate a content ID for the attachment.</span></span>  
  
    3.  <span data-ttu-id="3e731-134">编码器将创建附件的 MIME 部分。</span><span class="sxs-lookup"><span data-stu-id="3e731-134">The encoder will create a MIME part for the attachment.</span></span>  
  
3.  <span data-ttu-id="3e731-135">管道将加密消息部分并生成 RNIF 消息，具体取决于设置为 RNIF 2.01**是否要求永久保密**（按照流程配置设置中）：</span><span class="sxs-lookup"><span data-stu-id="3e731-135">For RNIF 2.01, the pipeline will encrypt message parts and build the RNIF message depending on the setting of **Is Persistent Confidentiality Required** (as set in the process configuration settings):</span></span>  
  
    1.  <span data-ttu-id="3e731-136">如果设置了**是否要求永久保密**到**负载**，编码器将加密的服务内容和附件。</span><span class="sxs-lookup"><span data-stu-id="3e731-136">If you have set **Is Persistent Confidentiality Required** to **Payload**, the encoder will encrypt the service content and the attachments.</span></span> <span data-ttu-id="3e731-137">然后，在组装器将服务头、 传递头和前导码来构造最终的 RNIF 消息。</span><span class="sxs-lookup"><span data-stu-id="3e731-137">The assembler will then add the service header, delivery header, and preamble to construct the final RNIF message.</span></span>  
  
    2.  <span data-ttu-id="3e731-138">如果设置了**是否要求永久保密**到**负载容器**，编码器将加密的服务头、 服务内容和附件。</span><span class="sxs-lookup"><span data-stu-id="3e731-138">If you have set **Is Persistent Confidentiality Required** to **Payload Container**, the encoder will encrypt the service header, service content, and the attachments.</span></span> <span data-ttu-id="3e731-139">然后，在组装器将传递头和前导码来构造最终的 RNIF 消息。</span><span class="sxs-lookup"><span data-stu-id="3e731-139">The assembler will then add the delivery header and preamble to construct the final RNIF message.</span></span>  
  
    3.  <span data-ttu-id="3e731-140">如果设置了**是否要求永久保密**到**None**，组装器会将服务头、 传递头和前导头添加到服务内容和附件中的 （不加密） 来构造最终的 RNIF 消息。</span><span class="sxs-lookup"><span data-stu-id="3e731-140">If you have set **Is Persistent Confidentiality Required** to **None**, the assembler will add the service header, delivery header, and preamble to the service content and the attachments (without encryption) to construct the final RNIF message.</span></span>  
  
4.  <span data-ttu-id="3e731-141">对于 RNIF 1.1，则组装器将构造最终的 RNIF 消息未加密。</span><span class="sxs-lookup"><span data-stu-id="3e731-141">For RNIF 1.1, the assembler will construct the final RNIF message without encryption.</span></span>  
  
5.  <span data-ttu-id="3e731-142">编码器将在以下情况下对消息进行签名：</span><span class="sxs-lookup"><span data-stu-id="3e731-142">The encoder will sign the message in the following case:</span></span>  
  
    1.  <span data-ttu-id="3e731-143">该消息是信号消息，并**要求不可否认**属性 （在流程配置设置中） 是`True`。</span><span class="sxs-lookup"><span data-stu-id="3e731-143">The message is a signal message, and the **Non-Repudiation Required** property (in the process configuration settings) is `True`.</span></span>  
  
    2.  <span data-ttu-id="3e731-144">该消息是操作消息，并**和内容的不可否认**属性 （在流程配置设置中） 是`True`。</span><span class="sxs-lookup"><span data-stu-id="3e731-144">The message is an action message, and the **Non-Repudiation of Origin and Content** property (in the process configuration settings) is `True`.</span></span>  
  
6.  <span data-ttu-id="3e731-145">为 RNIF 2.01，编码器将计算在 MIME 消息的第一个正文部分的摘要，并保留该摘要。</span><span class="sxs-lookup"><span data-stu-id="3e731-145">For RNIF 2.01, the encoder will calculate the digest on the first body part of the MIME message, and persist the digest.</span></span> <span data-ttu-id="3e731-146">它将计算使用的方法中设置的摘要`Digest`贸易合作伙伴协议 （sha-1 或 MD5） 中的方法属性。</span><span class="sxs-lookup"><span data-stu-id="3e731-146">It will calculate the digest using the method set in the `Digest` method property in the trading partner agreement (SHA-1 or MD5).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e731-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e731-147">See Also</span></span>  
 [<span data-ttu-id="3e731-148">BTARN 中的消息处理</span><span class="sxs-lookup"><span data-stu-id="3e731-148">Message Processing in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)