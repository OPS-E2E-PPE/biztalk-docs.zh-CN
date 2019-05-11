---
title: 配置签名、 压缩和 AS2 传输中的加密 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc3537a7-c065-4a33-a375-29e7902b5ffa
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9a87bb700ecddc5ae0bf9a4e6319d7b84fa55ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390744"
---
# <a name="configuring-signing-compression-and-encryption-in-as2-transport"></a><span data-ttu-id="044e0-102">配置签名、 压缩和 AS2 传输中加密</span><span class="sxs-lookup"><span data-stu-id="044e0-102">Configuring Signing, Compression, and Encryption in AS2 Transport</span></span>
<span data-ttu-id="044e0-103">你可以配置数字签名、 签名验证、 加密和解密中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="044e0-103">You can configure digital signatures, signature verification, encryption, and decryption from within the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="044e0-104">此配置需要设置 AS2 管道和 BizTalk 参与方的相应属性。</span><span class="sxs-lookup"><span data-stu-id="044e0-104">This configuration requires that you set the appropriate properties for the AS2 pipelines and BizTalk parties.</span></span>  
  
## <a name="using-as2-pipelines"></a><span data-ttu-id="044e0-105">使用 AS2 管道</span><span class="sxs-lookup"><span data-stu-id="044e0-105">Using AS2 Pipelines</span></span>  
 <span data-ttu-id="044e0-106">若要帮助保护入站的 AS2 消息，请使用 AS2 接收管道 （AS2EdiReceive 或 AS2Receive） 中将接收位置。</span><span class="sxs-lookup"><span data-stu-id="044e0-106">To help secure an inbound AS2 message, use an AS2 receive pipeline (AS2EdiReceive or AS2Receive) in your receive location.</span></span> <span data-ttu-id="044e0-107">AS2 解码器解密、 解压缩和/或 AS2 消息执行签名验证。</span><span class="sxs-lookup"><span data-stu-id="044e0-107">The AS2 Decoder decrypts, decompresses, and/or performs signature verification on AS2 messages.</span></span> <span data-ttu-id="044e0-108">有关如何执行以上的详细信息，请参阅的"AS2 解码器"部分[AS2 接收组件](../core/as2-receive-components.md)。</span><span class="sxs-lookup"><span data-stu-id="044e0-108">For more information on how it does so, see the "AS2 Decoder" section of [AS2 Receive Components](../core/as2-receive-components.md).</span></span>  
  
 <span data-ttu-id="044e0-109">若要帮助保护出站 AS2 消息，请在发送端口使用 AS2 发送管道 （AS2EdiSend 或 AS2Send）。</span><span class="sxs-lookup"><span data-stu-id="044e0-109">To help secure an outbound AS2 message, use an AS2 send pipeline (AS2EdiSend or AS2Send) in your send port.</span></span> <span data-ttu-id="044e0-110">AS2 编码器对进行签名、 压缩，并对出站 AS2 消息进行加密。</span><span class="sxs-lookup"><span data-stu-id="044e0-110">The AS2 Encoder signs, compresses, and encrypts outbound AS2 messages.</span></span> <span data-ttu-id="044e0-111">有关如何执行以上的详细信息，请参阅的"AS2 编码器"部分[AS2 发送组件](../core/as2-send-components.md)。</span><span class="sxs-lookup"><span data-stu-id="044e0-111">For more information on how it does so, see the "AS2 Encoder" section of [AS2 Send Components](../core/as2-send-components.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="044e0-112">后一条消息已签名，不得更改签名 blob。</span><span class="sxs-lookup"><span data-stu-id="044e0-112">Once a message has been signed, the signature blob must not be changed.</span></span> <span data-ttu-id="044e0-113">如果更改，则会损坏签名。</span><span class="sxs-lookup"><span data-stu-id="044e0-113">If changed, the signature would be corrupted.</span></span> <span data-ttu-id="044e0-114">可以更改边界标头，或边界标头以外的任何内容，但不得更改边界标头中的任何内容。</span><span class="sxs-lookup"><span data-stu-id="044e0-114">The boundary header, or anything outside the boundary headers, can be changed, but anything within the boundary headers must not be changed.</span></span>  
  
## <a name="setting-as2-agreement-properties"></a><span data-ttu-id="044e0-115">设置 AS2 协议属性</span><span class="sxs-lookup"><span data-stu-id="044e0-115">Setting AS2 Agreement Properties</span></span>  
 <span data-ttu-id="044e0-116">配置签名和加密处理，通过设置 AS2 协议属性，如下所示：</span><span class="sxs-lookup"><span data-stu-id="044e0-116">You configure signature and encryption processing by setting AS2 agreement properties as follows:</span></span>  
  
- <span data-ttu-id="044e0-117">若要签名、 压缩和/或加密出站消息，检查**应对消息进行签名**，**应对消息进行压缩**，并**应对消息进行加密**上的属性**验证**（对于传出的 AS2 消息） 的单向协议选项卡中的页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="044e0-117">To sign, compress, and/or encrypt an outbound message, check the **Message should be signed**, **Message should be compressed**, and **Message should be encrypted** properties on the **Validation** page of the one-way agreement tab (for the outgoing AS2 message) in the **Agreement Properties** dialog box.</span></span>  
  
- <span data-ttu-id="044e0-118">若要请求经过签名的 MDN 以响应出站消息，检查**请求 MDN**并**请求经过签名的 MDN**上的属性**确认 (Mdn)** 页单向协议选项卡**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="044e0-118">To request a signed MDN in response to an outbound message, check the **Request MDN** and **Request signed MDN** properties on the **Acknowledgements (MDNs)** page of the one-way agreement tab of the **Agreement Properties** dialog box.</span></span>  
  
- <span data-ttu-id="044e0-119">若要指定入站的消息已签名，将经过压缩和/或加密，检查**使用的验证和 MDN 的协议设置而非消息标头**属性，**应对消息进行签名**属性，**应对消息进行压缩**属性，并**应对消息进行加密**属性上的**验证**单向协议的页（适用于传入的 AS2 消息） 选项卡**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="044e0-119">To specify that an inbound message is signed, compressed, and/or encrypted, check the **Use agreement settings for validation and MDN instead of message header** property, the **Message should be signed** property, the **Message should be compressed** property, and the **Message should be encrypted** property on the **Validation** page of the one-way agreement tab (for the incoming AS2 message) in the **Agreement Properties** dialog box.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="044e0-120">当**使用的验证和 MDN 的协议设置而非消息标头**选择属性，将忽略传入消息的所有标头详细信息并根据协议设置处理该消息。</span><span class="sxs-lookup"><span data-stu-id="044e0-120">When the **Use agreement settings for validation and MDN instead of message header** property is selected, all header details of the incoming message are ignored and the message is processed based on the agreement settings.</span></span>  
  
- <span data-ttu-id="044e0-121">若要在入站的消息属性通过选择重写时，指定经过签名的 MDN 以响应入站消息，**使用的验证和 MDN 的协议设置而非消息标头**属性，检查**请求签名 MDN**属性**确认 (Mdn)** 页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="044e0-121">To specify a signed MDN in response to an inbound message, when the inbound message properties are overridden by selecting the **Use agreement settings for validation and MDN instead of message header** property, check the **Request Signed MDN** property on **Acknowledgements (MDNs)** page of the **Agreement Properties** dialog box.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="044e0-122">当**使用的验证和 MDN 的协议设置而非消息标头**选择属性，将忽略传入消息的所有标头详细信息并根据协议设置处理该消息。</span><span class="sxs-lookup"><span data-stu-id="044e0-122">When the **Use agreement settings for validation and MDN instead of message header** property is selected, all header details of the incoming message are ignored and the message is processed based on the agreement settings.</span></span>  
  
- <span data-ttu-id="044e0-123">若要指定经过签名的 MDN 以响应入站消息，入站的消息属性未重写时 (**使用的验证和 MDN 的协议设置而非消息标头**清除)，但消息标头不这样做指定进行签名，检查**请求的 MDN 签名如果处置通知选项标头不存在或已签名回执协议标头设置为可选**属性上的**接收方 MDN 设置**页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="044e0-123">To specify a signed MDN in response to an inbound message, when the inbound message properties are not overridden (the **Use agreement settings for validation and MDN instead of message header** is cleared), but the message headers do not specify signing, check the **Sign requested MDN if Disposition-Notification-Option header is not present or if Signed-Receipt-Protocol header is set to optional** property on the **Receiver MDN Settings** page of the **Agreement Properties** dialog box.</span></span>  
  
- <span data-ttu-id="044e0-124">若要指定一个传出 AS2 消息的 BizTalk 组属性中指定不同的签名证书，请选择**覆盖组签名证书**中**签名证书**页的单向协议选项卡**协议属性**对话框，然后指定签名证书。</span><span class="sxs-lookup"><span data-stu-id="044e0-124">To specify a different signing certificate than the one specified in the BizTalk Group properties for outgoing AS2 messages, select **Override Group Signature Certificate** in the **Signature Certificate** page of the one-way agreement tab of the **Agreement Properties** dialog box, and specify a signing certificate.</span></span> <span data-ttu-id="044e0-125">如果设置此属性，将使用中提供的证书签名解决协议的 AS2 消息**签名证书**页并不提供的证书为 BizTalk 组属性的一部分。</span><span class="sxs-lookup"><span data-stu-id="044e0-125">If this property is set, whichever AS2 message that resolves to the agreement will be signed using the certificate provided in the **Signature Certificate** page and not by the certificate provided as part of the BizTalk Group properties.</span></span>  
  
  <span data-ttu-id="044e0-126">有关设置参与方属性的详细信息，请参阅[配置 AS2 属性](../core/configuring-as2-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="044e0-126">For more information about setting up party properties, see [Configuring AS2 Properties](../core/configuring-as2-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="044e0-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="044e0-127">See Also</span></span>  
 <span data-ttu-id="044e0-128">[AS2 安全性](../core/as2-security.md) </span><span class="sxs-lookup"><span data-stu-id="044e0-128">[AS2 Security](../core/as2-security.md) </span></span>  
 <span data-ttu-id="044e0-129">[为 AS2 配置证书](../core/configuring-certificates-for-as2.md) </span><span class="sxs-lookup"><span data-stu-id="044e0-129">[Configuring Certificates for AS2](../core/configuring-certificates-for-as2.md) </span></span>  
 <span data-ttu-id="044e0-130">[AS2 消息](../core/as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="044e0-130">[AS2 Messages](../core/as2-messages.md) </span></span>  
 <span data-ttu-id="044e0-131">[AS2 接收组件](../core/as2-receive-components.md) </span><span class="sxs-lookup"><span data-stu-id="044e0-131">[AS2 Receive Components](../core/as2-receive-components.md) </span></span>  
 <span data-ttu-id="044e0-132">[AS2 发送组件](../core/as2-send-components.md) </span><span class="sxs-lookup"><span data-stu-id="044e0-132">[AS2 Send Components](../core/as2-send-components.md) </span></span>  
 [<span data-ttu-id="044e0-133">配置 AS2 属性</span><span class="sxs-lookup"><span data-stu-id="044e0-133">Configuring AS2 Properties</span></span>](../core/configuring-as2-properties.md)