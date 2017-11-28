---
title: "配置签名、 压缩和 AS2 传输中的加密 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc3537a7-c065-4a33-a375-29e7902b5ffa
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88309f17e335708b6e73109972c6c02d75ee483c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-signing-compression-and-encryption-in-as2-transport"></a><span data-ttu-id="90d87-102">配置 AS2 传输中的签名、压缩和加密</span><span class="sxs-lookup"><span data-stu-id="90d87-102">Configuring Signing, Compression, and Encryption in AS2 Transport</span></span>
<span data-ttu-id="90d87-103">可以从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台内配置数字签名、签名验证、加密和解密。</span><span class="sxs-lookup"><span data-stu-id="90d87-103">You can configure digital signatures, signature verification, encryption, and decryption from within the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="90d87-104">该配置需要设置 AS2 管道和 BizTalk 参与方的相应属性。</span><span class="sxs-lookup"><span data-stu-id="90d87-104">This configuration requires that you set the appropriate properties for the AS2 pipelines and BizTalk parties.</span></span>  
  
## <a name="using-as2-pipelines"></a><span data-ttu-id="90d87-105">使用 AS2 管道</span><span class="sxs-lookup"><span data-stu-id="90d87-105">Using AS2 Pipelines</span></span>  
 <span data-ttu-id="90d87-106">若要确保入站 AS2 消息的安全，请在接收位置使用 AS2 接收管道（AS2EdiReceive 或 AS2Receive）。</span><span class="sxs-lookup"><span data-stu-id="90d87-106">To help secure an inbound AS2 message, use an AS2 receive pipeline (AS2EdiReceive or AS2Receive) in your receive location.</span></span> <span data-ttu-id="90d87-107">AS2 解码器对 AS2 消息进行解密、解压缩和/或执行签名验证。</span><span class="sxs-lookup"><span data-stu-id="90d87-107">The AS2 Decoder decrypts, decompresses, and/or performs signature verification on AS2 messages.</span></span> <span data-ttu-id="90d87-108">有关如何执行操作的详细信息，请参阅的"AS2 解码器"部分[AS2 接收组件](../core/as2-receive-components.md)。</span><span class="sxs-lookup"><span data-stu-id="90d87-108">For more information on how it does so, see the "AS2 Decoder" section of [AS2 Receive Components](../core/as2-receive-components.md).</span></span>  
  
 <span data-ttu-id="90d87-109">若要确保出站 AS2 消息的安全，请在发送端口使用 AS2 发送管道（AS2EdiSend 或 AS2Send）。</span><span class="sxs-lookup"><span data-stu-id="90d87-109">To help secure an outbound AS2 message, use an AS2 send pipeline (AS2EdiSend or AS2Send) in your send port.</span></span> <span data-ttu-id="90d87-110">AS2 编码器对出站 AS2 消息进行签名、压缩和加密。</span><span class="sxs-lookup"><span data-stu-id="90d87-110">The AS2 Encoder signs, compresses, and encrypts outbound AS2 messages.</span></span> <span data-ttu-id="90d87-111">有关如何执行操作的详细信息，请参阅的"AS2 编码器"部分[AS2 发送组件](../core/as2-send-components.md)。</span><span class="sxs-lookup"><span data-stu-id="90d87-111">For more information on how it does so, see the "AS2 Encoder" section of [AS2 Send Components](../core/as2-send-components.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="90d87-112">在对消息进行签名之后，不得对签名 blob 进行更改。</span><span class="sxs-lookup"><span data-stu-id="90d87-112">Once a message has been signed, the signature blob must not be changed.</span></span> <span data-ttu-id="90d87-113">如果将其更改，则签名会受损。</span><span class="sxs-lookup"><span data-stu-id="90d87-113">If changed, the signature would be corrupted.</span></span> <span data-ttu-id="90d87-114">可以更改边界标头和边界标头以外的对象，但不得更改边界标头以内的对象。</span><span class="sxs-lookup"><span data-stu-id="90d87-114">The boundary header, or anything outside the boundary headers, can be changed, but anything within the boundary headers must not be changed.</span></span>  
  
## <a name="setting-as2-agreement-properties"></a><span data-ttu-id="90d87-115">设置 AS2 协议属性</span><span class="sxs-lookup"><span data-stu-id="90d87-115">Setting AS2 Agreement Properties</span></span>  
 <span data-ttu-id="90d87-116">可以通过设置 AS2 协议属性来配置签名和加密处理，如下所示：</span><span class="sxs-lookup"><span data-stu-id="90d87-116">You configure signature and encryption processing by setting AS2 agreement properties as follows:</span></span>  
  
-   <span data-ttu-id="90d87-117">若要登录、 压缩，和/或加密出站消息，检查**应对消息进行签名**，**应对消息进行压缩**，和**应对消息进行加密**上的属性**验证**的单向协议选项卡 （对于传出的 AS2 消息） 中的页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="90d87-117">To sign, compress, and/or encrypt an outbound message, check the **Message should be signed**, **Message should be compressed**, and **Message should be encrypted** properties on the **Validation** page of the one-way agreement tab (for the outgoing AS2 message) in the **Agreement Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="90d87-118">若要请求对出站消息的响应签名的 MDN，检查**请求 MDN**和**请求经过签名的 MDN**属性**确认 (Mdn)**页单向协议选项卡**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="90d87-118">To request a signed MDN in response to an outbound message, check the **Request MDN** and **Request signed MDN** properties on the **Acknowledgements (MDNs)** page of the one-way agreement tab of the **Agreement Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="90d87-119">若要指定的入站的消息进行签名，压缩，和/或加密，请检查**使用验证和 MDN 的协议设置，而不是消息标头**属性，**应对消息进行签名**属性，**应对消息进行压缩**属性，与**应对消息进行加密**属性**验证**的单向协议页（有关为传入 AS2 消息） 选项卡中**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="90d87-119">To specify that an inbound message is signed, compressed, and/or encrypted, check the **Use agreement settings for validation and MDN instead of message header** property, the **Message should be signed** property, the **Message should be compressed** property, and the **Message should be encrypted** property on the **Validation** page of the one-way agreement tab (for the incoming AS2 message) in the **Agreement Properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="90d87-120">当**使用验证和 MDN 的协议设置，而不是消息标头**选择属性，则传入消息的所有标头详细信息将被忽略，消息处理基于的协议设置。</span><span class="sxs-lookup"><span data-stu-id="90d87-120">When the **Use agreement settings for validation and MDN instead of message header** property is selected, all header details of the incoming message are ignored and the message is processed based on the agreement settings.</span></span>  
  
-   <span data-ttu-id="90d87-121">若要在入站的消息属性通过选择重写时，以响应传入消息，指定签名的 MDN**使用验证和 MDN 的协议设置，而不是消息标头**属性，检查**请求签名的 MDN**属性**确认 (Mdn)**页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="90d87-121">To specify a signed MDN in response to an inbound message, when the inbound message properties are overridden by selecting the **Use agreement settings for validation and MDN instead of message header** property, check the **Request Signed MDN** property on **Acknowledgements (MDNs)** page of the **Agreement Properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="90d87-122">当**使用验证和 MDN 的协议设置，而不是消息标头**选择属性，则传入消息的所有标头详细信息将被忽略，消息处理基于的协议设置。</span><span class="sxs-lookup"><span data-stu-id="90d87-122">When the **Use agreement settings for validation and MDN instead of message header** property is selected, all header details of the incoming message are ignored and the message is processed based on the agreement settings.</span></span>  
  
-   <span data-ttu-id="90d87-123">若要在入站的消息属性不重写时，以响应传入消息，指定签名的 MDN (**使用验证和 MDN 的协议设置，而不是消息标头**处于未选中状态)，但消息标头不返回指定签名，检查**登录请求 MDN 如果处置通知选项标头不存在或已签名回执协议标头设置为可选**属性**收件人 MDN 设置**页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="90d87-123">To specify a signed MDN in response to an inbound message, when the inbound message properties are not overridden (the **Use agreement settings for validation and MDN instead of message header** is cleared), but the message headers do not specify signing, check the **Sign requested MDN if Disposition-Notification-Option header is not present or if Signed-Receipt-Protocol header is set to optional** property on the **Receiver MDN Settings** page of the **Agreement Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="90d87-124">若要指定与传出的 AS2 消息的 BizTalk 组属性中指定的一个不同的签名证书，请选择**覆盖组签名证书**中**签名证书**的单向协议选项卡页**协议属性**对话框框中，并指定签名证书。</span><span class="sxs-lookup"><span data-stu-id="90d87-124">To specify a different signing certificate than the one specified in the BizTalk Group properties for outgoing AS2 messages, select **Override Group Signature Certificate** in the **Signature Certificate** page of the one-way agreement tab of the **Agreement Properties** dialog box, and specify a signing certificate.</span></span> <span data-ttu-id="90d87-125">如果设置此属性，将使用提供的证书签名无论解析为协议的 AS2 消息**签名证书**页上，不由证书提供作为 BizTalk 组属性的一部分。</span><span class="sxs-lookup"><span data-stu-id="90d87-125">If this property is set, whichever AS2 message that resolves to the agreement will be signed using the certificate provided in the **Signature Certificate** page and not by the certificate provided as part of the BizTalk Group properties.</span></span>  
  
 <span data-ttu-id="90d87-126">有关设置参与方属性的详细信息，请参阅[配置 AS2 属性](../core/configuring-as2-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="90d87-126">For more information about setting up party properties, see [Configuring AS2 Properties](../core/configuring-as2-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90d87-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90d87-127">See Also</span></span>  
 <span data-ttu-id="90d87-128">[AS2 安全](../core/as2-security.md) </span><span class="sxs-lookup"><span data-stu-id="90d87-128">[AS2 Security](../core/as2-security.md) </span></span>  
 <span data-ttu-id="90d87-129">[AS2 适用于配置证书](../core/configuring-certificates-for-as2.md) </span><span class="sxs-lookup"><span data-stu-id="90d87-129">[Configuring Certificates for AS2](../core/configuring-certificates-for-as2.md) </span></span>  
 <span data-ttu-id="90d87-130">[AS2 消息](../core/as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="90d87-130">[AS2 Messages](../core/as2-messages.md) </span></span>  
 <span data-ttu-id="90d87-131">[AS2 接收组件](../core/as2-receive-components.md) </span><span class="sxs-lookup"><span data-stu-id="90d87-131">[AS2 Receive Components](../core/as2-receive-components.md) </span></span>  
 <span data-ttu-id="90d87-132">[AS2 发送组件](../core/as2-send-components.md) </span><span class="sxs-lookup"><span data-stu-id="90d87-132">[AS2 Send Components](../core/as2-send-components.md) </span></span>  
 [<span data-ttu-id="90d87-133">配置 AS2 属性</span><span class="sxs-lookup"><span data-stu-id="90d87-133">Configuring AS2 Properties</span></span>](../core/configuring-as2-properties.md)