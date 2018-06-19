---
title: BizTalk Server 使用的证书签名消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, signed messages
- messages, message flow [digital signatures]
- S/MIME messages
- signed messages
- digital signatures, message flow
- messages, certificates
ms.assetid: 0b521e11-73ef-424f-9e6a-4fb42dc263ff
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cce82b634fffac4af0f75cdff26c7f512a132de9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233117"
---
# <a name="certificates-that-biztalk-server-uses-for-signed-messages"></a><span data-ttu-id="00b5b-102">BizTalk Server 用于签名消息的证书</span><span class="sxs-lookup"><span data-stu-id="00b5b-102">Certificates that BizTalk Server Uses for Signed Messages</span></span>
<span data-ttu-id="00b5b-103">BizTalk Server 支持对出站消息进行签名以及对安全多用途 Internet 邮件扩展 (S/MIME) 入站消息进行签名验证。</span><span class="sxs-lookup"><span data-stu-id="00b5b-103">BizTalk Server supports signing outbound messages and signature verification for inbound Secure Multipurpose Internet Mail Extensions (S/MIME) messages.</span></span> <span data-ttu-id="00b5b-104">BizTalk Server 使用 S/MIME 版本 2 和 3 对出站消息进行签名并验证入站消息的签名。</span><span class="sxs-lookup"><span data-stu-id="00b5b-104">BizTalk Server uses S/MIME versions 2 and 3 to sign outbound messages and to validate the signature of inbound messages.</span></span> <span data-ttu-id="00b5b-105">同样，您可以将 BizTalk Server 配置为对其发送到合作伙伴的消息进行签名和加密。</span><span class="sxs-lookup"><span data-stu-id="00b5b-105">Similarly, you can configure BizTalk Server to sign and then encrypt the messages it sends to its partners.</span></span>  
  
-   <span data-ttu-id="00b5b-106">BizTalk Server 支持使用 SHA-1 和 MD5 签名算法验证数字签名。</span><span class="sxs-lookup"><span data-stu-id="00b5b-106">BizTalk Server supports the SHA-1 and MD5 signing algorithms for verifying digital signatures.</span></span> <span data-ttu-id="00b5b-107">BizTalk Server 使用 SHA-1 签名算法对出站消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="00b5b-107">BizTalk Server uses the SHA-1 signing algorithm to sign outbound messages.</span></span>  
  
-   <span data-ttu-id="00b5b-108">BizTalk Server 支持的用于签名密钥的密钥交换系统是 RSA (Rivest-Shamir-Adleman) 算法和数字签名标准 (Digital Signature Standard, DSS)。</span><span class="sxs-lookup"><span data-stu-id="00b5b-108">The key exchange systems supported by BizTalk Server for signature keys are the Rivest-Shamir-Adleman (RSA) algorithms and the Digital Signature Standard (DSS).</span></span> <span data-ttu-id="00b5b-109">BizTalk Server 不支持将高级加密标准 (Advanced Encryption Standard, AES) 交换系统用于签名密钥。</span><span class="sxs-lookup"><span data-stu-id="00b5b-109">BizTalk Server does not support the Advanced Encryption Standard (AES) exchange system for signature keys.</span></span>  
  
-   <span data-ttu-id="00b5b-110">BizTalk Server 支持的签名证书是 x.509 版本 3。</span><span class="sxs-lookup"><span data-stu-id="00b5b-110">The signing certificate supported by BizTalk Server is x.509 version 3.</span></span>  
  
 <span data-ttu-id="00b5b-111">下图显示了 BizTalk Server 接收数字签名消息并选择使用签名将合作伙伴标识解析为 BizTalk Server 环境中某个参与方时的消息流。</span><span class="sxs-lookup"><span data-stu-id="00b5b-111">The following figure shows the message flow when BizTalk Server receives a digitally signed message and optionally uses the signature to resolve the partner identity to a party in the BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="00b5b-112">![发送的签名的消息时消息流](../core/media/6fd1674d-5a21-4272-83ca-608d7b400de7.gif "6fd1674d-5a21-4272-83ca-608d7b400de7")</span><span class="sxs-lookup"><span data-stu-id="00b5b-112">![Message flow when sending a signed message](../core/media/6fd1674d-5a21-4272-83ca-608d7b400de7.gif "6fd1674d-5a21-4272-83ca-608d7b400de7")</span></span>  
  
 <span data-ttu-id="00b5b-113">BizTalk Server 接收数字签名消息时的消息流如下所示：</span><span class="sxs-lookup"><span data-stu-id="00b5b-113">The message flow when BizTalk Server receives a digitally signed message is as follows:</span></span>  
  
1.  <span data-ttu-id="00b5b-114">合作伙伴向 BizTalk Server 发送消息。</span><span class="sxs-lookup"><span data-stu-id="00b5b-114">A partner sends a message to BizTalk Server.</span></span> <span data-ttu-id="00b5b-115">合作伙伴使用其私钥证书对该消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="00b5b-115">The partner signs the message with its private key certificate.</span></span>  
  
2.  <span data-ttu-id="00b5b-116">相应的 BizTalk Server 接收处理程序接收该消息。</span><span class="sxs-lookup"><span data-stu-id="00b5b-116">The appropriate BizTalk Server receive handler receives the message.</span></span>  
  
3.  <span data-ttu-id="00b5b-117">在接收管道的执行过程中，MIME/SMIME 解码器管道组件使用合作伙伴的公钥来验证数字签名。</span><span class="sxs-lookup"><span data-stu-id="00b5b-117">During the execution of the receive pipeline, the MIME/SMIME Decoder pipeline component verifies the digital signature by using the partner's public key.</span></span>  
  
4.  <span data-ttu-id="00b5b-118">如果配置了参与方解析组件，则在接收管道参与方解析组件的执行过程中，合作伙伴的公钥证书将用于标识 BizTalk Server 系统中的参与方。</span><span class="sxs-lookup"><span data-stu-id="00b5b-118">If party resolution component is configured, the partner's public key certificate is used to identify the party in the BizTalk Server system during the execution of the receive pipeline party resolution component.</span></span>  
  
5.  <span data-ttu-id="00b5b-119">进行其他处理。</span><span class="sxs-lookup"><span data-stu-id="00b5b-119">Additional processing occurs.</span></span>  
  
 <span data-ttu-id="00b5b-120">下图显示了 BizTalk Server 发送数字签名消息时的消息流。</span><span class="sxs-lookup"><span data-stu-id="00b5b-120">The following figure shows the message flow when BizTalk Server sends a digitally signed message.</span></span>  
  
 ![](../core/media/bts-bpi-sp-msgsec-outboundsigning-r2c.gif "bts_BPI_SP_MSGSEC_OutboundSigning_R2c")  
  
 <span data-ttu-id="00b5b-121">BizTalk Server 向合作伙伴发送数字签名消息时的消息流如下所示：</span><span class="sxs-lookup"><span data-stu-id="00b5b-121">The message flow when BizTalk Server sends a digitally signed message to a partner is as follows:</span></span>  
  
1.  <span data-ttu-id="00b5b-122">相应的 BizTalk Server 发送处理程序将消息发送给合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="00b5b-122">The appropriate BizTalk Server send handler sends a message to the partner.</span></span>  
  
2.  <span data-ttu-id="00b5b-123">在发送管道的执行过程中，MIME/SMIME 编码器管道组件使用 BizTalk Server 私钥对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="00b5b-123">During the execution of the send pipeline, the MIME/SMIME Encoder pipeline component signs the message by using the BizTalk Server private key.</span></span>  
  
3.  <span data-ttu-id="00b5b-124">合作伙伴接收来自 BizTalk Server 的消息。</span><span class="sxs-lookup"><span data-stu-id="00b5b-124">The partner receives the message from BizTalk Server.</span></span> <span data-ttu-id="00b5b-125">合作伙伴使用 BizTalk Server 公钥验证数字签名。</span><span class="sxs-lookup"><span data-stu-id="00b5b-125">The partner uses the BizTalk Server public key to verify the digital signature.</span></span>  
  
 <span data-ttu-id="00b5b-126">BizTalk Server 验证通过验证的证书颁发机构 (CA) 信任链的证书和通过验证证书未过期的传入签名消息关联的证书的有效性。</span><span class="sxs-lookup"><span data-stu-id="00b5b-126">BizTalk Server verifies the validity of the certificates associated with the incoming signed messages by validating the certification authority (CA) trust chain for the certificate and by verifying that the certificate has not expired.</span></span> <span data-ttu-id="00b5b-127">验证 CA 信任链的过程涉及遍历证书上的信任链，直至到达根证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="00b5b-127">The process of validating the CA trust chain involves traversing the chain of trust on certificates until a root certification authority is reached.</span></span> <span data-ttu-id="00b5b-128">这样可检验用于对消息进行签名的证书是否确实来自标识的参与方。</span><span class="sxs-lookup"><span data-stu-id="00b5b-128">This validates that the certificate used to sign a message is indeed from the identified party.</span></span> <span data-ttu-id="00b5b-129">在运行时将对每个签名的消息进行此验证。</span><span class="sxs-lookup"><span data-stu-id="00b5b-129">This validation occurs at runtime for each and every signed message.</span></span>  
  
 <span data-ttu-id="00b5b-130">此外，BizTalk Server 还可以验证证书颁发机构是否尚未吊销用于对消息进行签名或加密的证书。</span><span class="sxs-lookup"><span data-stu-id="00b5b-130">In addition, BizTalk Server can verify that the certification authority has not revoked the certificate used to sign or encrypt the message.</span></span> <span data-ttu-id="00b5b-131">为此，必须从证书颁发机构下载证书吊销列表 (CRL)，然后使用 Windows 资源管理器进行安装。</span><span class="sxs-lookup"><span data-stu-id="00b5b-131">To do this, you must download the certificate revocation list (CRL) from the certification authority and install it using Windows Explorer.</span></span> <span data-ttu-id="00b5b-132">有关如何验证证书的详细信息，请参阅[如何配置 MIME SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="00b5b-132">For more information about how to validate a certificate, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00b5b-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00b5b-133">See Also</span></span>  
 <span data-ttu-id="00b5b-134">[BizTalk Server 用于加密消息的证书](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span><span class="sxs-lookup"><span data-stu-id="00b5b-134">[Certificates that BizTalk Server Uses for Encrypted Messages](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span></span>  
 <span data-ttu-id="00b5b-135">[BizTalk Server 使用的证书存储](../core/certificate-stores-that-biztalk-server-uses.md) </span><span class="sxs-lookup"><span data-stu-id="00b5b-135">[Certificate Stores that BizTalk Server Uses](../core/certificate-stores-that-biztalk-server-uses.md) </span></span>  
 <span data-ttu-id="00b5b-136">[加密和签名证书](../core/encryption-and-signing-certificates.md) </span><span class="sxs-lookup"><span data-stu-id="00b5b-136">[Encryption and Signing Certificates](../core/encryption-and-signing-certificates.md) </span></span>  
 [<span data-ttu-id="00b5b-137">发送和接收签名消息</span><span class="sxs-lookup"><span data-stu-id="00b5b-137">Sending and Receiving Signed Messages</span></span>](../core/sending-and-receiving-signed-messages.md)