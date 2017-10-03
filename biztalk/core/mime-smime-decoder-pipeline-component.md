---
title: "MIME SMIME 解码器管道组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, MIME/SMIME Decoder
- MIME/SMIME Decoder [pipeline component]
ms.assetid: ff6c963c-1b5c-4be4-9eef-3ec9a018e7fd
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d85fe099cb876156410ba86c5f204a154dfbac36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mime-smime-decoder-pipeline-component"></a><span data-ttu-id="b96f3-102">MIME SMIME 解码器管道组件</span><span class="sxs-lookup"><span data-stu-id="b96f3-102">MIME-SMIME Decoder Pipeline Component</span></span>
<span data-ttu-id="b96f3-103">MIME/SMIME 解码器组件可为消息提供 MIME 解码功能。</span><span class="sxs-lookup"><span data-stu-id="b96f3-103">The MIME/SMIME Decoder component provides MIME decoding functionality for messages.</span></span> <span data-ttu-id="b96f3-104">此管道组件可置于接收管道的解码阶段中，它支持 7 位、8 位、二进制、Quoted-Printable、UUEncode 和 Base64 解码。</span><span class="sxs-lookup"><span data-stu-id="b96f3-104">This pipeline component can be placed into the Decode stage of a receive pipeline, and it supports 7bit, 8bit, binary, quoted-printable, UUEncode, and base64 decoding.</span></span> <span data-ttu-id="b96f3-105">本地化数据字符集的更改将不会影响解码。</span><span class="sxs-lookup"><span data-stu-id="b96f3-105">Localized data character set changes will not affect the decoding.</span></span>  
  
 <span data-ttu-id="b96f3-106">MIME/SMIME 解码器组件可以对传入消息进行解密和签名验证。</span><span class="sxs-lookup"><span data-stu-id="b96f3-106">The MIME/SMIME Decoder component can decrypt and sign-validate an incoming message.</span></span> <span data-ttu-id="b96f3-107">使用的解密证书来自运行服务的当前用户的个人证书存储。</span><span class="sxs-lookup"><span data-stu-id="b96f3-107">Decryption certificates are used from the personal certificate store of the current user under which the service is running.</span></span> <span data-ttu-id="b96f3-108">使用的签名验证证书来自本地计算机的通讯簿存储或消息本身。</span><span class="sxs-lookup"><span data-stu-id="b96f3-108">Sign-validation certificates are used from the Address Book store of the local computer or from the message itself.</span></span>  
  
 <span data-ttu-id="b96f3-109">一旦消息解密成功，MIME/SMIME 解码器管道组件就会关联用于将消息解密为消息谓词的解密证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="b96f3-109">On successful decryption of a message, the MIME/SMIME Decoder pipeline component associates the thumbprint of the decryption certificate used to decrypt the message as a predicate of the message.</span></span> <span data-ttu-id="b96f3-110">这意味着所有订阅该消息的服务（业务流程或发送端口）都必须与拥有其密钥的主机相关联。</span><span class="sxs-lookup"><span data-stu-id="b96f3-110">This means that any service (orchestration or send port) that is subscribing to that message must be associated with a host that owns that key.</span></span> <span data-ttu-id="b96f3-111">主机和密钥之间的关联可作为主机的一个属性在 BizTalk 管理控制台中完成设置。</span><span class="sxs-lookup"><span data-stu-id="b96f3-111">Associations between hosts and keys can be completed in the BizTalk Administration console as a property of the host.</span></span> <span data-ttu-id="b96f3-112">在 BizTalk 管理控制台中配置主机的详细信息，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="b96f3-112">For more information about configuring the host in the BizTalk Administration console, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
 <span data-ttu-id="b96f3-113">MIME/SMIME 解码器管道组件是唯一的即时可用的接收管道组件，该组件可以处理多部分消息，包括多部分 MIME/SMIME 消息。</span><span class="sxs-lookup"><span data-stu-id="b96f3-113">The MIME/SMIME Decoder pipeline component is the only out-of-the-box receive pipeline component that handles multi-part messages, including multi-part MIME/SMIME messages.</span></span> <span data-ttu-id="b96f3-114">该管道组件可解析消息，并创建等效的多部分 BizTalk 消息。</span><span class="sxs-lookup"><span data-stu-id="b96f3-114">The pipeline component parses the message and creates an equivalent multi-part BizTalk message.</span></span> <span data-ttu-id="b96f3-115">多部分 BizTalk 消息只有一个称为正文部分的部分。</span><span class="sxs-lookup"><span data-stu-id="b96f3-115">A multi-part BizTalk message has one unique part named the body part.</span></span> <span data-ttu-id="b96f3-116">所有其他管道组件（如 XML 拆装器管道组件）只处理 BizTalk 消息的正文部分。</span><span class="sxs-lookup"><span data-stu-id="b96f3-116">All other pipeline components, such as the XML Disassembler pipeline component, only process the body part of the BizTalk Message.</span></span> <span data-ttu-id="b96f3-117">另外，可使用 BizTalk 正文部分所对应的 MessageType 将消息路由到订户。</span><span class="sxs-lookup"><span data-stu-id="b96f3-117">Also the MessageType corresponding to the BizTalk body part is used for routing the message to subscribers.</span></span>  
  
 <span data-ttu-id="b96f3-118">MIME/SMIME 解码器管道组件将评估以下条件，以标识与多部分 MIME 消息相对应的 BizTalk 正文部分。</span><span class="sxs-lookup"><span data-stu-id="b96f3-118">The following conditions are evaluated by the MIME/SMIME Decoder pipeline component to identify the BizTalk BodyPart corresponding to a multi-part MIME message.</span></span> <span data-ttu-id="b96f3-119">条件评估的顺序如下：</span><span class="sxs-lookup"><span data-stu-id="b96f3-119">The order of the condition evaluation is as follows:</span></span>  
  
1.  <span data-ttu-id="b96f3-120">第一个 MIME/SMIME 部分的内容说明标头设置为“body”（不区分大小写）。</span><span class="sxs-lookup"><span data-stu-id="b96f3-120">The first MIME/SMIME part that has the Content-Description header set to "body" (case-insensitive).</span></span>  
  
2.  <span data-ttu-id="b96f3-121">第一个 MIME/SMIME 部分的内容类型标头设置为“text/xml”（不区分大小写）。</span><span class="sxs-lookup"><span data-stu-id="b96f3-121">The first MIME/SMIME part that has the Content-Type header set to "text/xml"(case-insensitive).</span></span>  
  
3.  <span data-ttu-id="b96f3-122">第一个 MIME/SMIME 部分的内容类型标头设置为“text/”（不区分大小写）。</span><span class="sxs-lookup"><span data-stu-id="b96f3-122">The first MIME/SMIME part that has the Content-Type header set to "text/" (case-insensitive).</span></span>  
  
4.  <span data-ttu-id="b96f3-123">第一个 MIME/SMIME 部分。</span><span class="sxs-lookup"><span data-stu-id="b96f3-123">The first MIME/SMIME part.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b96f3-124">输出 BizTalk 消息中的部分顺序与 MIME/SMIME 消息中 MIME/SMIME 部分的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="b96f3-124">The order of the parts in the output BizTalk message is same as the order of MIME/SMIME parts in the MIME/SMIME message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b96f3-125">如果多部分 BizTalk 消息正由业务流程订阅或使用，则消息中的部分数必须与激活该业务流程的消息中的部分数一致。</span><span class="sxs-lookup"><span data-stu-id="b96f3-125">If the multi-part BizTalk message is being subscribed or consumed by an orchestration, the number of parts in the message has to match the number of parts in the message that activates the orchestration.</span></span>  
  
 <span data-ttu-id="b96f3-126">有关配置 MIME/SMIME 解码器管道组件的信息，请参阅[如何配置 MIME SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="b96f3-126">For information about configuring the MIME/SMIME Decoder pipeline component, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span> <span data-ttu-id="b96f3-127">有关 BizTalk Server 支持解密、 登录验证和证书的使用情况的详细信息，请参阅[发送和接收消息的安全性](../core/security-for-sending-and-receiving-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="b96f3-127">For more information about BizTalk Server support for decryption, sign-validation, and usage of certificates, see [Security for Sending and Receiving Messages](../core/security-for-sending-and-receiving-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b96f3-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b96f3-128">See Also</span></span>  
 <span data-ttu-id="b96f3-129">[管道组件](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="b96f3-129">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 <span data-ttu-id="b96f3-130">[MIME SMIME 属性架构和属性](../core/mime-smime-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="b96f3-130">[MIME-SMIME Property Schema and Properties](../core/mime-smime-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="b96f3-131">MIME （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="b96f3-131">MIME (BizTalk Server Sample)</span></span>](../core/mime-biztalk-server-sample.md)