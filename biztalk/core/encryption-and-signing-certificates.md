---
title: 加密和签名证书 |Microsoft Docs
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
ms.openlocfilehash: ee36208b232609c5a73ede9a933f692a0681827f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349543"
---
# <a name="encryption-and-signing-certificates"></a><span data-ttu-id="ce1ab-102">加密和签名证书</span><span class="sxs-lookup"><span data-stu-id="ce1ab-102">Encryption and Signing Certificates</span></span>
<span data-ttu-id="ce1ab-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]严重依赖于提供证书的安全性。</span><span class="sxs-lookup"><span data-stu-id="ce1ab-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] relies heavily on the security provided by certificates.</span></span> <span data-ttu-id="ce1ab-104">通过使用证书进行加密和数字签名，BizTalk Server 可以发送和接收数据，可以是受信任，并可帮助确保所处理的数据安全。</span><span class="sxs-lookup"><span data-stu-id="ce1ab-104">By using certificates for encryption and digital signatures, BizTalk Server can send and receive data that can be trusted, and can help ensure that the data it processes is secure.</span></span> <span data-ttu-id="ce1ab-105">对于加密和数字签名，没有公钥证书和私钥证书。</span><span class="sxs-lookup"><span data-stu-id="ce1ab-105">For both encryption and digital signatures, there is a public key certificate and a private key certificate.</span></span> <span data-ttu-id="ce1ab-106">对于加密，消息的发件人使用接收方的公钥证书对消息进行加密，而接收方的消息 (BizTalk Server) 使用其私钥对消息进行解密。</span><span class="sxs-lookup"><span data-stu-id="ce1ab-106">For encryption, the sender of the message uses the receiver's public key certificate to encrypt the message, while the receiver of the message (BizTalk Server) uses its private key to decrypt the message.</span></span> <span data-ttu-id="ce1ab-107">数字签名消息的发件人使用私钥证书对消息进行签名和消息 (BizTalk Server) 的接收方使用发件人的公钥证书来验证签名。</span><span class="sxs-lookup"><span data-stu-id="ce1ab-107">For digital signatures, the sender of the message uses a private key certificate to sign the message, and the receiver of the message (BizTalk Server) uses the public key certificate of the sender to verify the signature.</span></span>  
  
 <span data-ttu-id="ce1ab-108">BizTalk Server 使用公钥证书来验证数字签名的入站消息和出站消息进行加密。</span><span class="sxs-lookup"><span data-stu-id="ce1ab-108">BizTalk Server uses public key certificates to verify the digital signatures of inbound messages and for encrypting outbound messages.</span></span> <span data-ttu-id="ce1ab-109">BizTalk Server 使用私钥证书解密入站的消息和出站消息签名。</span><span class="sxs-lookup"><span data-stu-id="ce1ab-109">BizTalk Server uses private key certificates for decrypting inbound messages and signing outbound messages.</span></span>  
  
 <span data-ttu-id="ce1ab-110">在 BizTalk 浏览器和 BizTalk 管理控制台中配置 BizTalk Server 使用的证书。</span><span class="sxs-lookup"><span data-stu-id="ce1ab-110">You configure the certificates BizTalk Server uses in BizTalk Explorer and in the BizTalk Administration Console.</span></span>  
  
 <span data-ttu-id="ce1ab-111">有关数字证书的详细信息，请参阅 Microsoft TechNet 网站上的[ http://go.microsoft.com/fwlink/?LinkId=60508 ](http://go.microsoft.com/fwlink/?LinkId=60508)。</span><span class="sxs-lookup"><span data-stu-id="ce1ab-111">For more information about digital certificates, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=60508](http://go.microsoft.com/fwlink/?LinkId=60508).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce1ab-112">在处理安全多用途 Internet 邮件扩展 (S/MIME) 消息时，你可以选择允许 BizTalk Server 引擎检查证书吊销列表 (CRL) 以确保证书尚未过期并且受信任根下证书颁发机构 (CA)。</span><span class="sxs-lookup"><span data-stu-id="ce1ab-112">While processing Secure Multipurpose Internet Mail Extensions (S/MIME) messages, you can choose to have the BizTalk Server engine check the Certificate Revocation List (CRL) to ensure that a certificate has not expired and that it is trusted down to a Root Certificate Authority (CA).</span></span> <span data-ttu-id="ce1ab-113">管道处理中的 MIME/SMIME 解码器组件的消息时，将执行此验证。</span><span class="sxs-lookup"><span data-stu-id="ce1ab-113">This verification occurs while the pipeline processes the message, in the MIME/SMIME decoder component.</span></span> <span data-ttu-id="ce1ab-114">有关如何设置的详细信息**检查吊销列表**属性，请参阅[如何配置 MIME-SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="ce1ab-114">For more information about how to set **Check Revocation List** property, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ce1ab-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="ce1ab-115">In This Section</span></span>  
  
-   [<span data-ttu-id="ce1ab-116">BizTalk Server 使用的证书存储</span><span class="sxs-lookup"><span data-stu-id="ce1ab-116">Certificate Stores that BizTalk Server Uses</span></span>](../core/certificate-stores-that-biztalk-server-uses.md)  
  
-   [<span data-ttu-id="ce1ab-117">BizTalk Server 用于签名消息的证书</span><span class="sxs-lookup"><span data-stu-id="ce1ab-117">Certificates that BizTalk Server Uses for Signed Messages</span></span>](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)  
  
-   [<span data-ttu-id="ce1ab-118">BizTalk Server 用于加密消息的证书</span><span class="sxs-lookup"><span data-stu-id="ce1ab-118">Certificates that BizTalk Server Uses for Encrypted Messages</span></span>](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)