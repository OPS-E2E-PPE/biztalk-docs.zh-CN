---
title: "BizTalk Server 使用的证书加密消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, message flow [encrypted messages]
- encrypted messages
- messages, encryption
ms.assetid: 44b06488-4ecd-436d-af3d-b95e285ecb3e
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f2dbd51506da7b505f66b3001b8bdc6fa0a58ac
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="certificates-that-biztalk-server-uses-for-encrypted-messages"></a><span data-ttu-id="48a43-102">BizTalk Server 用于加密消息的证书</span><span class="sxs-lookup"><span data-stu-id="48a43-102">Certificates that BizTalk Server Uses for Encrypted Messages</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="48a43-103">支持的基于安全多用途 Internet 邮件扩展 (S/MIME) 的入站邮件的出站消息的公共密钥加密和解密。</span><span class="sxs-lookup"><span data-stu-id="48a43-103"> supports public key encryption of outbound messages and decryption of inbound messages based on Secure Multipurpose Internet Mail Extensions (S/MIME).</span></span> <span data-ttu-id="48a43-104">BizTalk Server 使用 S/MIME 版本 3 对出站消息进行加密，使用 S/MIME 版本 2 和 3 对入站消息进行解密。</span><span class="sxs-lookup"><span data-stu-id="48a43-104">BizTalk Server uses S/MIME version 3 for encryption of outbound messages, and S/MIME versions 2 and 3 for decryption of inbound messages.</span></span>  
  
-   <span data-ttu-id="48a43-105">BizTalk Server 支持 RSA 和 Diffie Hellman 加密证书。</span><span class="sxs-lookup"><span data-stu-id="48a43-105">BizTalk Server supports RSA and Diffie Hellman encryption certificates.</span></span>  
  
-   <span data-ttu-id="48a43-106">BizTalk Server 支持数据加密标准 (DES)、3DES 和 RC2 加密算法。</span><span class="sxs-lookup"><span data-stu-id="48a43-106">BizTalk Server supports Data Encryption Standard (DES), 3DES, and RC2 encryption algorithms.</span></span>  
  
 <span data-ttu-id="48a43-107">下图显示了 BizTalk Server 接收加密消息时的消息流。</span><span class="sxs-lookup"><span data-stu-id="48a43-107">The following figure shows the message flow when BizTalk Server receives an encrypted message.</span></span>  
  
 <span data-ttu-id="48a43-108">![在收到加密的消息时消息流](../core/media/bpi-sp-msgsec-inboundencryption.gif "BPI_SP_MSGSEC_InboundEncryption")</span><span class="sxs-lookup"><span data-stu-id="48a43-108">![Message flow when receiving an encrypted message](../core/media/bpi-sp-msgsec-inboundencryption.gif "BPI_SP_MSGSEC_InboundEncryption")</span></span>  
  
 <span data-ttu-id="48a43-109">BizTalk Server 接收加密消息时的消息流如下所示：</span><span class="sxs-lookup"><span data-stu-id="48a43-109">The message flow when BizTalk Server receives an encrypted message is as follows:</span></span>  
  
1.  <span data-ttu-id="48a43-110">合作伙伴向 BizTalk Server 发送消息。</span><span class="sxs-lookup"><span data-stu-id="48a43-110">A partner sends a message to BizTalk Server.</span></span> <span data-ttu-id="48a43-111">合作伙伴使用 BizTalk Server 公钥对消息进行加密。</span><span class="sxs-lookup"><span data-stu-id="48a43-111">The partner encrypts the message with the BizTalk Server public key.</span></span>  
  
2.  <span data-ttu-id="48a43-112">相应的 BizTalk Server 接收处理程序接收该消息。</span><span class="sxs-lookup"><span data-stu-id="48a43-112">The appropriate BizTalk Server receive handler receives the message.</span></span>  
  
3.  <span data-ttu-id="48a43-113">在接收管道的执行过程中，MIME/SMIME 解码器管道组件使用 BizTalk Server 私钥对消息进行解密。</span><span class="sxs-lookup"><span data-stu-id="48a43-113">During the receive pipeline execution, the MIME/SMIME Decoder pipeline component decrypts the message by using the BizTalk Server private key.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="48a43-114">对于在 IIS 7.0 的计算机上成功的管道解密，请确保为 IIS 应用程序池帐户和与接收处理程序关联的主机实例所使用的帐户是相同，并且此帐户是的成员\<machineName\>\IIS_WPG 组。</span><span class="sxs-lookup"><span data-stu-id="48a43-114">For pipeline decryption to succeed on an IIS 7.0 computer, ensure that the account for the IIS application pool and the account used by the host instance associated with the receive handler are the same and that this account is a member of the \<machineName\>\IIS_WPG group.</span></span> <span data-ttu-id="48a43-115">有关详细信息设置 IIS 进程有关 IIS 7.0，请参阅的标识[解决 IIS 权限问题的指导原则](../core/guidelines-for-resolving-iis-permissions-problems.md)。</span><span class="sxs-lookup"><span data-stu-id="48a43-115">For more information on setting IIS process identity for IIS 7.0 see [Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md).</span></span> <span data-ttu-id="48a43-116">这些进程必须以相同的帐户运行，以便确保加载的帐户配置文件还加载了在管道中执行解密所需的注册表项。</span><span class="sxs-lookup"><span data-stu-id="48a43-116">These processes must run under the same account to ensure that the account profile is loaded which in turns loads the registry keys required to perform decryption in the pipeline.</span></span> <span data-ttu-id="48a43-117">出于性能原因，IIS 7.0 在启动关联的 w3wp.exe 进程时不加载帐户配置文件，因此，必须使用相同的帐户配置 BizTalk 主机实例，以便 BizTalk 能够一起加载帐户配置文件和注册表项。</span><span class="sxs-lookup"><span data-stu-id="48a43-117">For performance reasons, IIS 7.0 does not load the account profile when starting the associated w3wp.exe process so the BizTalk host instance must be configured with the same account so that BizTalk will load the account profile and registry keys.</span></span>  
  
4.  <span data-ttu-id="48a43-118">进行其他处理。</span><span class="sxs-lookup"><span data-stu-id="48a43-118">Additional processing occurs.</span></span>  
  
 <span data-ttu-id="48a43-119">下图显示了 BizTalk Server 发送加密消息时的消息流。</span><span class="sxs-lookup"><span data-stu-id="48a43-119">The following figure shows the message flow when BizTalk Server sends an encrypted message.</span></span>  
  
 <span data-ttu-id="48a43-120">![发送加密的消息时消息流](../core/media/bpi-sp-msgsec-outboundencryption.gif "BPI_SP_MSGSEC_OutboundEncryption")</span><span class="sxs-lookup"><span data-stu-id="48a43-120">![Message flow when sending an encrypted message](../core/media/bpi-sp-msgsec-outboundencryption.gif "BPI_SP_MSGSEC_OutboundEncryption")</span></span>  
  
 <span data-ttu-id="48a43-121">BizTalk Server 向合作伙伴发送加密消息时的消息流如下所示：</span><span class="sxs-lookup"><span data-stu-id="48a43-121">The message flow when BizTalk Server sends an encrypted message to a partner is as follows:</span></span>  
  
1.  <span data-ttu-id="48a43-122">相应的 BizTalk Server 发送处理程序将消息发送给合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="48a43-122">The appropriate BizTalk Server send handler sends a message to the partner.</span></span>  
  
2.  <span data-ttu-id="48a43-123">在发送管道的执行过程中，MIME/SMIME 编码器管道组件使用合作伙伴的公钥对消息进行加密。</span><span class="sxs-lookup"><span data-stu-id="48a43-123">During the send pipeline execution, the MIME/SMIME Encoder pipeline component encrypts the message by using the partner's public key.</span></span>  
  
3.  <span data-ttu-id="48a43-124">合作伙伴接收来自 BizTalk Server 的消息。</span><span class="sxs-lookup"><span data-stu-id="48a43-124">The partner receives the message from BizTalk Server.</span></span> <span data-ttu-id="48a43-125">合作伙伴使用其私钥对消息进行解密。</span><span class="sxs-lookup"><span data-stu-id="48a43-125">The partner uses its private key to decrypt the message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48a43-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48a43-126">See Also</span></span>  
 <span data-ttu-id="48a43-127">[BizTalk Server 用于签名的消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="48a43-127">[Certificates that BizTalk Server Uses for Signed Messages](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span></span>  
 <span data-ttu-id="48a43-128">[BizTalk Server 使用的证书存储](../core/certificate-stores-that-biztalk-server-uses.md) </span><span class="sxs-lookup"><span data-stu-id="48a43-128">[Certificate Stores that BizTalk Server Uses](../core/certificate-stores-that-biztalk-server-uses.md) </span></span>  
 <span data-ttu-id="48a43-129">[加密和签名证书](../core/encryption-and-signing-certificates.md) </span><span class="sxs-lookup"><span data-stu-id="48a43-129">[Encryption and Signing Certificates](../core/encryption-and-signing-certificates.md) </span></span>  
 [<span data-ttu-id="48a43-130">发送和接收加密消息</span><span class="sxs-lookup"><span data-stu-id="48a43-130">Sending and Receiving Encrypted Messages</span></span>](../core/sending-and-receiving-encrypted-messages.md)