---
title: BTARN 发送管道 |Microsoft 文档
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
ms.openlocfilehash: f566b37cc43f8aca2f0a36143d10d809c008d5cd
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007518"
---
# <a name="btarn-send-pipeline"></a><span data-ttu-id="374bd-102">BTARN 发送管道</span><span class="sxs-lookup"><span data-stu-id="374bd-102">BTARN Send Pipeline</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="374bd-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RosettaNet 实现框架 (RNIF) 消息准备 RNIFSend 管道 (RNIFSend.btp) 中的传输。</span><span class="sxs-lookup"><span data-stu-id="374bd-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] prepares a RosettaNet Implementation Framework (RNIF) message for transmission in the RNIFSend pipeline (RNIFSend.btp).</span></span> <span data-ttu-id="374bd-104">发送管道包括：</span><span class="sxs-lookup"><span data-stu-id="374bd-104">The send pipeline includes the following:</span></span>  
  
-   <span data-ttu-id="374bd-105">预处理器的 XML</span><span class="sxs-lookup"><span data-stu-id="374bd-105">XML preprocessor</span></span>  
  
-   <span data-ttu-id="374bd-106">XML 组装器</span><span class="sxs-lookup"><span data-stu-id="374bd-106">XML assembler</span></span>  
  
-   <span data-ttu-id="374bd-107">多用途 Internet 邮件扩展安全/多用途 Internet 邮件扩展 (MIME/SMIME) 编码器</span><span class="sxs-lookup"><span data-stu-id="374bd-107">Multipurpose Internet Mail Extensions/Secure Multipurpose Internet Mail Extensions (MIME/SMIME) encoder</span></span>  
  
## <a name="xml-preprocessor"></a><span data-ttu-id="374bd-108">XML 预处理器</span><span class="sxs-lookup"><span data-stu-id="374bd-108">XML Preprocessor</span></span>  
 <span data-ttu-id="374bd-109">XML 预处理器将 DOCTYPE 标头添加到消息。</span><span class="sxs-lookup"><span data-stu-id="374bd-109">The XML preprocessor adds a DOCTYPE header to the message.</span></span> <span data-ttu-id="374bd-110">标头来确定与消息关联的文档类型定义 (DTD) 架构。</span><span class="sxs-lookup"><span data-stu-id="374bd-110">The header identifies the document type definition (DTD) schema associated with the message.</span></span> <span data-ttu-id="374bd-111">RNIF 规范要求 RNIF 传输 DOCTYPE 标头。</span><span class="sxs-lookup"><span data-stu-id="374bd-111">The RNIF specification requires the presence of a DOCTYPE header for RNIF transmission.</span></span>  
  
## <a name="xml-assembler"></a><span data-ttu-id="374bd-112">XML 汇编程序</span><span class="sxs-lookup"><span data-stu-id="374bd-112">XML Assembler</span></span>  
 <span data-ttu-id="374bd-113">XML 汇编程序取决于 BizTalk Server XML 汇编程序。</span><span class="sxs-lookup"><span data-stu-id="374bd-113">The XML assembler is based on the BizTalk Server XML assembler.</span></span> <span data-ttu-id="374bd-114">它将属性从消息上下文传输回包络线和文档。</span><span class="sxs-lookup"><span data-stu-id="374bd-114">It transfers properties from the message context back into envelopes and documents.</span></span> <span data-ttu-id="374bd-115">它从其 XML 部件和附件装配消息。</span><span class="sxs-lookup"><span data-stu-id="374bd-115">It assembles the message from its XML parts and attachments.</span></span> <span data-ttu-id="374bd-116">它不执行消息验证。</span><span class="sxs-lookup"><span data-stu-id="374bd-116">It does not perform message validation.</span></span>  
  
 <span data-ttu-id="374bd-117">有关本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]XML 汇编程序，请参阅 BizTalk Server 帮助中的"XML 的汇编程序管道组件"。</span><span class="sxs-lookup"><span data-stu-id="374bd-117">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] XML assembler, see "XML Assembler Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="mimesmime-encoder"></a><span data-ttu-id="374bd-118">MIME/SMIME 编码器</span><span class="sxs-lookup"><span data-stu-id="374bd-118">MIME/SMIME Encoder</span></span>  
 <span data-ttu-id="374bd-119">MIME/SMIME 编码器取决于 BizTalk Server MIME/SMIME 编码器。</span><span class="sxs-lookup"><span data-stu-id="374bd-119">The MIME/SMIME encoder is based on the BizTalk Server MIME/SMIME Encoder.</span></span> <span data-ttu-id="374bd-120">具体取决于贸易合作伙伴协议和 BizTalk Server MIME/SMIME 编码器的设置中的协议设置[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]编码器执行以下：</span><span class="sxs-lookup"><span data-stu-id="374bd-120">Depending on the protocol settings in the trading partner agreement, and the settings of the BizTalk Server MIME/SMIME Encoder, the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] encoder performs the following:</span></span>  
  
-   <span data-ttu-id="374bd-121">将一个 8 字节的二进制标头添加到消息中，根据需要为 RNIF 1.1 消息。</span><span class="sxs-lookup"><span data-stu-id="374bd-121">Adds an 8-byte binary header to the message, as required for RNIF 1.1 messages.</span></span>  
  
-   <span data-ttu-id="374bd-122">编码的消息部分，并计算摘要。</span><span class="sxs-lookup"><span data-stu-id="374bd-122">Encodes the message parts, and calculates the digest.</span></span>  
  
-   <span data-ttu-id="374bd-123">将加密的负载 （服务内容加附件）、 或负载容器 （服务内容加服务标头加附件）。</span><span class="sxs-lookup"><span data-stu-id="374bd-123">Encrypts the payload (service content plus attachments), or the payload container (service content plus service header plus attachments).</span></span> <span data-ttu-id="374bd-124">如果设置了**编码所有端口**上设置**协议**到贸易合作伙伴协议的选项卡`False`，编码器将加密只对负载。</span><span class="sxs-lookup"><span data-stu-id="374bd-124">If you have set the **Encode all ports** setting on the **Protocol** tab of the trading partner agreement to `False`, the encoder will encrypt only the payload.</span></span> <span data-ttu-id="374bd-125">如果设置了**编码所有端口**将设置为`True`，编码器将加密负载容器。</span><span class="sxs-lookup"><span data-stu-id="374bd-125">If you have set the **Encode all ports** setting to `True`, the encoder will encrypt the payload container.</span></span>  
  
 <span data-ttu-id="374bd-126">有关本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MIME/SMIME 编码器，请参阅 BizTalk Server 帮助中的"MIME/SMIME 的编码器管道组件"。</span><span class="sxs-lookup"><span data-stu-id="374bd-126">For more information about the native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] MIME/SMIME Encoder, see "MIME/SMIME Encoder Pipeline Component" in BizTalk Server Help.</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="374bd-127">消息流</span><span class="sxs-lookup"><span data-stu-id="374bd-127">Message Flow</span></span>  
 <span data-ttu-id="374bd-128">消息流通过 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 发送管道的步骤如下：</span><span class="sxs-lookup"><span data-stu-id="374bd-128">The message flow through the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] send pipeline is as follows:</span></span>  
  
1.  <span data-ttu-id="374bd-129">如果设置了**将所有部分都编码**设置到贸易合作伙伴协议的`True`，MIME / SMIME 编码器将对所有消息部分进行都都编码。</span><span class="sxs-lookup"><span data-stu-id="374bd-129">If you have set the **Encode all parts** setting of the trading partner agreement to `True`, the MIME/SMIME encoder will encode all message parts.</span></span> <span data-ttu-id="374bd-130">它将使用在中设置的编码方法`Encoding`协议的属性。</span><span class="sxs-lookup"><span data-stu-id="374bd-130">It will use the encoding method set in the `Encoding` property of the agreement.</span></span>  
  
2.  <span data-ttu-id="374bd-131">有关 RNIF 2.01，如果消息已操作消息并且没有附件，编码器将执行以下操作为每个附件：</span><span class="sxs-lookup"><span data-stu-id="374bd-131">For RNIF 2.01, if the message is an action message and there is an attachment, the encoder will do the following for each attachment:</span></span>  
  
    1.  <span data-ttu-id="374bd-132">如果附件是二进制的编码器将对其进行编码。</span><span class="sxs-lookup"><span data-stu-id="374bd-132">If the attachment is binary, the encoder will encode it.</span></span>  
  
    2.  <span data-ttu-id="374bd-133">编码器将生成附件的内容 ID。</span><span class="sxs-lookup"><span data-stu-id="374bd-133">The encoder will generate a content ID for the attachment.</span></span>  
  
    3.  <span data-ttu-id="374bd-134">编码器将创建附件的 MIME 部分。</span><span class="sxs-lookup"><span data-stu-id="374bd-134">The encoder will create a MIME part for the attachment.</span></span>  
  
3.  <span data-ttu-id="374bd-135">管道加密消息部分，并生成 RNIF 消息，具体取决于的设置为 RNIF 2.01**是否要求永久保密**（作为在过程配置设置中设置）：</span><span class="sxs-lookup"><span data-stu-id="374bd-135">For RNIF 2.01, the pipeline will encrypt message parts and build the RNIF message depending on the setting of **Is Persistent Confidentiality Required** (as set in the process configuration settings):</span></span>  
  
    1.  <span data-ttu-id="374bd-136">如果设置了**是否要求永久保密**到**负载**，编码器将加密服务内容和附件。</span><span class="sxs-lookup"><span data-stu-id="374bd-136">If you have set **Is Persistent Confidentiality Required** to **Payload**, the encoder will encrypt the service content and the attachments.</span></span> <span data-ttu-id="374bd-137">服务标头、 传递标头和前导码构造最终 RNIF 消息，然后将添加汇编程序。</span><span class="sxs-lookup"><span data-stu-id="374bd-137">The assembler will then add the service header, delivery header, and preamble to construct the final RNIF message.</span></span>  
  
    2.  <span data-ttu-id="374bd-138">如果设置了**是否要求永久保密**到**负载容器**，编码器将加密服务标头、 服务内容和附件。</span><span class="sxs-lookup"><span data-stu-id="374bd-138">If you have set **Is Persistent Confidentiality Required** to **Payload Container**, the encoder will encrypt the service header, service content, and the attachments.</span></span> <span data-ttu-id="374bd-139">传递标头和前导码构造最终 RNIF 消息，然后将添加汇编程序。</span><span class="sxs-lookup"><span data-stu-id="374bd-139">The assembler will then add the delivery header and preamble to construct the final RNIF message.</span></span>  
  
    3.  <span data-ttu-id="374bd-140">如果设置了**是否要求永久保密**到**无**，汇编程序对服务内容和 （不带附件中添加服务标头、 传递标头和前导码加密） 构造最终 RNIF 消息。</span><span class="sxs-lookup"><span data-stu-id="374bd-140">If you have set **Is Persistent Confidentiality Required** to **None**, the assembler will add the service header, delivery header, and preamble to the service content and the attachments (without encryption) to construct the final RNIF message.</span></span>  
  
4.  <span data-ttu-id="374bd-141">对于 RNIF 1.1 汇编程序将构造不加密最后一 RNIF 条消息。</span><span class="sxs-lookup"><span data-stu-id="374bd-141">For RNIF 1.1, the assembler will construct the final RNIF message without encryption.</span></span>  
  
5.  <span data-ttu-id="374bd-142">编码器将在下面的示例对消息进行签名：</span><span class="sxs-lookup"><span data-stu-id="374bd-142">The encoder will sign the message in the following case:</span></span>  
  
    1.  <span data-ttu-id="374bd-143">消息是信号消息，与**不可否认性所需**属性 （在过程配置设置） 是`True`。</span><span class="sxs-lookup"><span data-stu-id="374bd-143">The message is a signal message, and the **Non-Repudiation Required** property (in the process configuration settings) is `True`.</span></span>  
  
    2.  <span data-ttu-id="374bd-144">此消息是操作消息中，与**的起点和内容的不可否认性**属性 （在过程配置设置） 是`True`。</span><span class="sxs-lookup"><span data-stu-id="374bd-144">The message is an action message, and the **Non-Repudiation of Origin and Content** property (in the process configuration settings) is `True`.</span></span>  
  
6.  <span data-ttu-id="374bd-145">有关 RNIF 2.01，编码器将计算的 MIME 消息，第一个正文部分的摘要，并保留了摘要。</span><span class="sxs-lookup"><span data-stu-id="374bd-145">For RNIF 2.01, the encoder will calculate the digest on the first body part of the MIME message, and persist the digest.</span></span> <span data-ttu-id="374bd-146">它将计算使用在中设置的方法的摘要`Digest`贸易合作伙伴协议 （sha-1 或 MD5） 中的方法属性。</span><span class="sxs-lookup"><span data-stu-id="374bd-146">It will calculate the digest using the method set in the `Digest` method property in the trading partner agreement (SHA-1 or MD5).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="374bd-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="374bd-147">See Also</span></span>  
 [<span data-ttu-id="374bd-148">BTARN 中的消息处理</span><span class="sxs-lookup"><span data-stu-id="374bd-148">Message Processing in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)