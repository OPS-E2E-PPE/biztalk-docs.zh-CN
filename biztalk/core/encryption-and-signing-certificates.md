---
title: 加密和签名证书 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, security
- security, certificates
- security, messages
- certificates, encryption
- encryption certificates, messages
- messages, encryption
- messages, certificates
- security, encryption
ms.assetid: 3c3f9de5-4156-4133-8d5e-c30b142b6d61
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 633484a6c5599b9323bfd7798f621b27a501ce6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241685"
---
# <a name="encryption-and-signing-certificates"></a><span data-ttu-id="6fe14-102">加密和签名证书</span><span class="sxs-lookup"><span data-stu-id="6fe14-102">Encryption and Signing Certificates</span></span>
<span data-ttu-id="6fe14-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在很大程度上依赖证书提供的安全性。</span><span class="sxs-lookup"><span data-stu-id="6fe14-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] relies heavily on the security provided by certificates.</span></span> <span data-ttu-id="6fe14-104">通过在进行加密和数字签名时使用证书，BizTalk Server 可以发送和接收可信数据，帮助您确保所处理的数据是安全的。</span><span class="sxs-lookup"><span data-stu-id="6fe14-104">By using certificates for encryption and digital signatures, BizTalk Server can send and receive data that can be trusted, and can help ensure that the data it processes is secure.</span></span> <span data-ttu-id="6fe14-105">加密和数字签名都有一个公钥证书和一个私钥证书。</span><span class="sxs-lookup"><span data-stu-id="6fe14-105">For both encryption and digital signatures, there is a public key certificate and a private key certificate.</span></span> <span data-ttu-id="6fe14-106">对于加密，消息的发件人使用收件人的公钥证书对消息加密，而消息的收件人 (BizTalk Server) 使用其私钥对消息进行解密。</span><span class="sxs-lookup"><span data-stu-id="6fe14-106">For encryption, the sender of the message uses the receiver's public key certificate to encrypt the message, while the receiver of the message (BizTalk Server) uses its private key to decrypt the message.</span></span> <span data-ttu-id="6fe14-107">对于数字签名，消息的发件人使用私钥证书对消息进行签名，而消息的收件人 (BizTalk Server) 使用发件人的公钥证书对签名进行验证。</span><span class="sxs-lookup"><span data-stu-id="6fe14-107">For digital signatures, the sender of the message uses a private key certificate to sign the message, and the receiver of the message (BizTalk Server) uses the public key certificate of the sender to verify the signature.</span></span>  
  
 <span data-ttu-id="6fe14-108">BizTalk Server 使用公钥证书来验证入站消息的数字签名并对出站消息进行加密。</span><span class="sxs-lookup"><span data-stu-id="6fe14-108">BizTalk Server uses public key certificates to verify the digital signatures of inbound messages and for encrypting outbound messages.</span></span> <span data-ttu-id="6fe14-109">BizTalk Server 使用私钥证书来解密入站消息并对出站消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="6fe14-109">BizTalk Server uses private key certificates for decrypting inbound messages and signing outbound messages.</span></span>  
  
 <span data-ttu-id="6fe14-110">可以在 BizTalk 浏览器和 BizTalk 管理控制台中配置 BizTalk Server 使用的证书。</span><span class="sxs-lookup"><span data-stu-id="6fe14-110">You configure the certificates BizTalk Server uses in BizTalk Explorer and in the BizTalk Administration Console.</span></span>  
  
 <span data-ttu-id="6fe14-111">有关数字的证书的详细信息，请参阅 Microsoft TechNet 网站，网址[http://go.microsoft.com/fwlink/?LinkId=60508](http://go.microsoft.com/fwlink/?LinkId=60508)。</span><span class="sxs-lookup"><span data-stu-id="6fe14-111">For more information about digital certificates, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=60508](http://go.microsoft.com/fwlink/?LinkId=60508).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fe14-112">处理安全多用途 Internet 邮件扩展 (S/MIME) 消息时，可以选择让 BizTalk Server 引擎检查证书吊销列表 (CRL) 以确保证书没有过期，并且从证书直至根证书颁发机构 (CA) 的每一环节都是可信任的。</span><span class="sxs-lookup"><span data-stu-id="6fe14-112">While processing Secure Multipurpose Internet Mail Extensions (S/MIME) messages, you can choose to have the BizTalk Server engine check the Certificate Revocation List (CRL) to ensure that a certificate has not expired and that it is trusted down to a Root Certificate Authority (CA).</span></span> <span data-ttu-id="6fe14-113">当管道使用 MIME/SMIME 解码器组件处理消息时执行此验证。</span><span class="sxs-lookup"><span data-stu-id="6fe14-113">This verification occurs while the pipeline processes the message, in the MIME/SMIME decoder component.</span></span> <span data-ttu-id="6fe14-114">有关如何设置的详细信息**检查吊销列表**属性，请参阅[如何配置 MIME SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="6fe14-114">For more information about how to set **Check Revocation List** property, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6fe14-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="6fe14-115">In This Section</span></span>  
  
-   [<span data-ttu-id="6fe14-116">BizTalk Server 使用的证书存储</span><span class="sxs-lookup"><span data-stu-id="6fe14-116">Certificate Stores that BizTalk Server Uses</span></span>](../core/certificate-stores-that-biztalk-server-uses.md)  
  
-   [<span data-ttu-id="6fe14-117">BizTalk Server 用于签名的消息的证书</span><span class="sxs-lookup"><span data-stu-id="6fe14-117">Certificates that BizTalk Server Uses for Signed Messages</span></span>](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)  
  
-   [<span data-ttu-id="6fe14-118">BizTalk Server 用于加密消息的证书</span><span class="sxs-lookup"><span data-stu-id="6fe14-118">Certificates that BizTalk Server Uses for Encrypted Messages</span></span>](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)