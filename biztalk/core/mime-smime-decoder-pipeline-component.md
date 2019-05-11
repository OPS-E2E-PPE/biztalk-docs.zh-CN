---
title: MIME-SMIME 解码器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, MIME/SMIME Decoder
- MIME/SMIME Decoder [pipeline component]
ms.assetid: ff6c963c-1b5c-4be4-9eef-3ec9a018e7fd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 593873b1d3252eed752de21fe4bb9c99dc664974
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394475"
---
# <a name="mime-smime-decoder-pipeline-component"></a><span data-ttu-id="62e04-102">MIME-SMIME 解码器管道组件</span><span class="sxs-lookup"><span data-stu-id="62e04-102">MIME-SMIME Decoder Pipeline Component</span></span>
<span data-ttu-id="62e04-103">MIME/SMIME 解码器组件提供 MIME 解码的消息的功能。</span><span class="sxs-lookup"><span data-stu-id="62e04-103">The MIME/SMIME Decoder component provides MIME decoding functionality for messages.</span></span> <span data-ttu-id="62e04-104">此管道组件可置于接收管道的解码阶段，它支持 7 位、 8 位、 二进制、 quoted printable、 UUEncode 和 base64 解码。</span><span class="sxs-lookup"><span data-stu-id="62e04-104">This pipeline component can be placed into the Decode stage of a receive pipeline, and it supports 7bit, 8bit, binary, quoted-printable, UUEncode, and base64 decoding.</span></span> <span data-ttu-id="62e04-105">本地化的数据字符集的更改不会影响解码。</span><span class="sxs-lookup"><span data-stu-id="62e04-105">Localized data character set changes will not affect the decoding.</span></span>  
  
 <span data-ttu-id="62e04-106">MIME/SMIME 解码器组件可以解密和签名验证传入消息。</span><span class="sxs-lookup"><span data-stu-id="62e04-106">The MIME/SMIME Decoder component can decrypt and sign-validate an incoming message.</span></span> <span data-ttu-id="62e04-107">在其下运行该服务的当前用户的个人证书存储中使用的解密证书。</span><span class="sxs-lookup"><span data-stu-id="62e04-107">Decryption certificates are used from the personal certificate store of the current user under which the service is running.</span></span> <span data-ttu-id="62e04-108">从本地计算机的通讯簿存储或从消息本身使用签名验证证书。</span><span class="sxs-lookup"><span data-stu-id="62e04-108">Sign-validation certificates are used from the Address Book store of the local computer or from the message itself.</span></span>  
  
 <span data-ttu-id="62e04-109">消息的解密成功，MIME/SMIME 解码器管道组件将用于对消息进行解密为消息的谓词的解密证书的指纹相关联。</span><span class="sxs-lookup"><span data-stu-id="62e04-109">On successful decryption of a message, the MIME/SMIME Decoder pipeline component associates the thumbprint of the decryption certificate used to decrypt the message as a predicate of the message.</span></span> <span data-ttu-id="62e04-110">这意味着任何订阅该消息的服务 （业务流程或发送端口） 必须与主机拥有该密钥相关联。</span><span class="sxs-lookup"><span data-stu-id="62e04-110">This means that any service (orchestration or send port) that is subscribing to that message must be associated with a host that owns that key.</span></span> <span data-ttu-id="62e04-111">作为主机的属性，可在 BizTalk 管理控制台中完成主机和密钥之间的关联。</span><span class="sxs-lookup"><span data-stu-id="62e04-111">Associations between hosts and keys can be completed in the BizTalk Administration console as a property of the host.</span></span> <span data-ttu-id="62e04-112">有关在 BizTalk 管理控制台中配置主机的详细信息，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="62e04-112">For more information about configuring the host in the BizTalk Administration console, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
 <span data-ttu-id="62e04-113">MIME/SMIME 解码器管道组件是唯一的-现成的接收管道组件处理多部分消息，包括多部分 MIME/SMIME 消息。</span><span class="sxs-lookup"><span data-stu-id="62e04-113">The MIME/SMIME Decoder pipeline component is the only out-of-the-box receive pipeline component that handles multi-part messages, including multi-part MIME/SMIME messages.</span></span> <span data-ttu-id="62e04-114">管道组件可解析该消息并创建等效的多部分 BizTalk 消息。</span><span class="sxs-lookup"><span data-stu-id="62e04-114">The pipeline component parses the message and creates an equivalent multi-part BizTalk message.</span></span> <span data-ttu-id="62e04-115">多部分 BizTalk 消息有一个名为正文部分的唯一部分。</span><span class="sxs-lookup"><span data-stu-id="62e04-115">A multi-part BizTalk message has one unique part named the body part.</span></span> <span data-ttu-id="62e04-116">所有其他管道组件，如 XML 拆装器管道组件，只处理 BizTalk 消息的正文部分。</span><span class="sxs-lookup"><span data-stu-id="62e04-116">All other pipeline components, such as the XML Disassembler pipeline component, only process the body part of the BizTalk Message.</span></span> <span data-ttu-id="62e04-117">此外与 BizTalk 正文部分对应的 MessageType 用于将消息路由到订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="62e04-117">Also the MessageType corresponding to the BizTalk body part is used for routing the message to subscribers.</span></span>  
  
 <span data-ttu-id="62e04-118">MIME/SMIME 解码器管道组件来标识对应于由多部分 MIME 消息，BizTalk 正文部分的情况下，将评估以下条件。</span><span class="sxs-lookup"><span data-stu-id="62e04-118">The following conditions are evaluated by the MIME/SMIME Decoder pipeline component to identify the BizTalk BodyPart corresponding to a multi-part MIME message.</span></span> <span data-ttu-id="62e04-119">条件计算的顺序是按如下所示：</span><span class="sxs-lookup"><span data-stu-id="62e04-119">The order of the condition evaluation is as follows:</span></span>  
  
1.  <span data-ttu-id="62e04-120">第一个 MIME/SMIME 部分设置为"body"（不区分大小写） 的内容说明标头。</span><span class="sxs-lookup"><span data-stu-id="62e04-120">The first MIME/SMIME part that has the Content-Description header set to "body" (case-insensitive).</span></span>  
  
2.  <span data-ttu-id="62e04-121">第一个 MIME/SMIME 部分的 Content-type 标头设置为"text/xml"(case-insensitive)。</span><span class="sxs-lookup"><span data-stu-id="62e04-121">The first MIME/SMIME part that has the Content-Type header set to "text/xml"(case-insensitive).</span></span>  
  
3.  <span data-ttu-id="62e04-122">第一个 MIME/SMIME 部分的 Content-type 标头设置为"text /"（不区分大小写）。</span><span class="sxs-lookup"><span data-stu-id="62e04-122">The first MIME/SMIME part that has the Content-Type header set to "text/" (case-insensitive).</span></span>  
  
4.  <span data-ttu-id="62e04-123">第一个 MIME/SMIME 部分。</span><span class="sxs-lookup"><span data-stu-id="62e04-123">The first MIME/SMIME part.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62e04-124">顺序 BizTalk 消息的输出中的部分是与 MIME/SMIME 消息中 MIME/SMIME 部分的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="62e04-124">The order of the parts in the output BizTalk message is same as the order of MIME/SMIME parts in the MIME/SMIME message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62e04-125">如果多部分 BizTalk 消息正由业务流程或订阅，消息中的部分数必须匹配在激活该业务流程的消息中的部分数。</span><span class="sxs-lookup"><span data-stu-id="62e04-125">If the multi-part BizTalk message is being subscribed or consumed by an orchestration, the number of parts in the message has to match the number of parts in the message that activates the orchestration.</span></span>  
  
 <span data-ttu-id="62e04-126">有关配置 MIME/SMIME 解码器管道组件的信息，请参阅[如何配置 MIME-SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="62e04-126">For information about configuring the MIME/SMIME Decoder pipeline component, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span> <span data-ttu-id="62e04-127">有关 BizTalk Server 支持解密、 签名验证和使用证书的详细信息，请参阅[发送和接收消息的安全性](../core/security-for-sending-and-receiving-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="62e04-127">For more information about BizTalk Server support for decryption, sign-validation, and usage of certificates, see [Security for Sending and Receiving Messages](../core/security-for-sending-and-receiving-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62e04-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="62e04-128">See Also</span></span>  
 <span data-ttu-id="62e04-129">[管道组件](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="62e04-129">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 <span data-ttu-id="62e04-130">[MIME-SMIME 属性架构和属性](../core/mime-smime-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="62e04-130">[MIME-SMIME Property Schema and Properties](../core/mime-smime-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="62e04-131">MIME（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="62e04-131">MIME (BizTalk Server Sample)</span></span>](../core/mime-biztalk-server-sample.md)