---
title: 向消息收件人授权 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, messages
- messages, receive authorization
- receive authorization
- messages, security
ms.assetid: c0cdb3ef-ee8e-40a1-9362-13cd26495951
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ca2b0b6474421bc474cf30ae8c8817bc5f8e10d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358753"
---
# <a name="authorizing-the-receiver-of-a-message"></a><span data-ttu-id="f8012-102">向消息收件人授权</span><span class="sxs-lookup"><span data-stu-id="f8012-102">Authorizing the Receiver of a Message</span></span>
<span data-ttu-id="f8012-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使您能够限制流程和授权接收消息的参与方。</span><span class="sxs-lookup"><span data-stu-id="f8012-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enables you to limit the processes and parties that you authorize to receive messages.</span></span>  
  
 <span data-ttu-id="f8012-104">下图显示了 BizTalk Server 中可使用一条消息的收件人进行授权的安全功能。</span><span class="sxs-lookup"><span data-stu-id="f8012-104">The following figure shows the security features in BizTalk Server that you use to authorize the receiver of a message.</span></span>  
  
 <span data-ttu-id="f8012-105">![向消息收件人授权的安全功能](../core/media/ebiz-plan-secoverview-authz.gif "ebiz_plan_secoverview_authz")</span><span class="sxs-lookup"><span data-stu-id="f8012-105">![Security features authorizing the message receiver](../core/media/ebiz-plan-secoverview-authz.gif "ebiz_plan_secoverview_authz")</span></span>  
<span data-ttu-id="f8012-106">BizTalk Server 的安全功能使用消息的收件人进行授权。</span><span class="sxs-lookup"><span data-stu-id="f8012-106">Security features BizTalk Server uses to authorize the receiver of a message.</span></span>  
  
 <span data-ttu-id="f8012-107">可以使用以下安全机制来建立哪些人拥有权限 （授权） 以接收您发送的消息：</span><span class="sxs-lookup"><span data-stu-id="f8012-107">You can use the following security mechanisms to establish who has permission (authorization) to receive the messages that you send:</span></span>  
  
-   <span data-ttu-id="f8012-108">**解密。**</span><span class="sxs-lookup"><span data-stu-id="f8012-108">**Decryption.**</span></span> <span data-ttu-id="f8012-109">请确保发送到 BizTalk Server 消息具有的公钥证书用于加密消息他们将发送到 BizTalk Server 参与方。</span><span class="sxs-lookup"><span data-stu-id="f8012-109">Make sure the parties that send messages to BizTalk Server have the public key certificate for encrypting messages they send to BizTalk Server.</span></span> <span data-ttu-id="f8012-110">BizTalk Server 使用私钥证书对消息进行解密。</span><span class="sxs-lookup"><span data-stu-id="f8012-110">BizTalk Server uses the private key certificate to decrypt the message.</span></span>  
  
-   <span data-ttu-id="f8012-111">**接收授权。**</span><span class="sxs-lookup"><span data-stu-id="f8012-111">**Receive Authorization.**</span></span> <span data-ttu-id="f8012-112">可以使用此方法来控制在 BizTalk Server 环境中的哪些主机能接收给定的消息。</span><span class="sxs-lookup"><span data-stu-id="f8012-112">You can use this method to control which hosts within the BizTalk Server environment can receive a given message.</span></span>  
  
-   <span data-ttu-id="f8012-113">**加密。**</span><span class="sxs-lookup"><span data-stu-id="f8012-113">**Encryption.**</span></span> <span data-ttu-id="f8012-114">通过使用来自给定参与方的公钥证书时 BizTalk 对消息进行加密，可以确保只有预期的参与方是能够读取该消息。</span><span class="sxs-lookup"><span data-stu-id="f8012-114">By using the public key certificate from a given party when BizTalk encrypts a message, you can ensure that only the intended party is able to read the message.</span></span>  
  
## <a name="receive-authorization"></a><span data-ttu-id="f8012-115">接收授权</span><span class="sxs-lookup"><span data-stu-id="f8012-115">Receive Authorization</span></span>  
 <span data-ttu-id="f8012-116">接收授权是方法，可以使用来控制哪些主机能接收 （订阅） 给定的消息。</span><span class="sxs-lookup"><span data-stu-id="f8012-116">Receive authorization is the method you can use to control which hosts can receive (subscribe for) a given message.</span></span> <span data-ttu-id="f8012-117">BizTalk Server 使用的证书信息，如订阅属性，以匹配消息谓词： MessageBox 数据库仅将标记为具有该消息的解密证书的主机，为所需身份验证的消息路由。</span><span class="sxs-lookup"><span data-stu-id="f8012-117">BizTalk Server uses the certificate information as a subscription property to match predicates on the message: the MessageBox database only routes messages marked as authorization required to the hosts that have the decryption certificate for that message.</span></span> <span data-ttu-id="f8012-118">若要说明该过程，请考虑以下方案：</span><span class="sxs-lookup"><span data-stu-id="f8012-118">To illustrate the process, consider the following scenarios:</span></span>  
  
- <span data-ttu-id="f8012-119">**路由未加密的消息：** 在 BizTalk Server 接收一条消息，发送方未进行加密，没有任何解密限制 BizTalk 如何路由消息。</span><span class="sxs-lookup"><span data-stu-id="f8012-119">**Routing an un-encrypted message:** When BizTalk Server receives a message that the sender did not encrypt, there is no decryption limitation as to how BizTalk routes the message.</span></span> <span data-ttu-id="f8012-120">使用的主机和主机，而无需接收授权配置的证书可以接收该消息。</span><span class="sxs-lookup"><span data-stu-id="f8012-120">Both hosts with and hosts without receive authorization certificates configured can receive the message.</span></span>  
  
- <span data-ttu-id="f8012-121">**路由加密的消息：** 当加密的消息到达时，接收管道必须含有对消息进行解密的解码组件。</span><span class="sxs-lookup"><span data-stu-id="f8012-121">**Routing an encrypted message:** When an encrypted message arrives, the receiving pipeline must contain a decoding component that decrypts the message.</span></span> <span data-ttu-id="f8012-122">当 BizTalk Server 将消息路由后被解密，只有配置了该证书的主机接收和 BizTalk 使用用来作为证据在 MessageBox 数据库订阅机制中，对消息进行解密的证书指纹消息。</span><span class="sxs-lookup"><span data-stu-id="f8012-122">When BizTalk Server routes a message after it is decrypted, BizTalk uses the certificate thumbprint used to decrypt the message as evidence in the MessageBox database subscription mechanism, and only those hosts configured with that certificate receive the message.</span></span>  
  
  <span data-ttu-id="f8012-123">如果想要使用接收授权，则必须提供你想要授权接收消息的主机的属性中的解密证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="f8012-123">If you want to use receive authorization, you must provide the thumbprint of the decryption certificate in the properties of the host that you want to authorize to receive the message.</span></span> <span data-ttu-id="f8012-124">有关详细信息接收授权，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="f8012-124">For more information about receive authorization, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8012-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8012-125">See Also</span></span>  
 <span data-ttu-id="f8012-126">[入站的消息身份验证](../core/inbound-message-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="f8012-126">[Inbound Message Authentication](../core/inbound-message-authentication.md) </span></span>  
 <span data-ttu-id="f8012-127">[进程间的消息身份验证](../core/authentication-of-messages-between-processes.md) </span><span class="sxs-lookup"><span data-stu-id="f8012-127">[Authentication of Messages Between Processes](../core/authentication-of-messages-between-processes.md) </span></span>  
 <span data-ttu-id="f8012-128">[出站消息保护](../core/outbound-message-protection.md) </span><span class="sxs-lookup"><span data-stu-id="f8012-128">[Outbound Message Protection](../core/outbound-message-protection.md) </span></span>  
 <span data-ttu-id="f8012-129">[对消息的发件人进行身份验证](../core/authenticating-the-sender-of-a-message.md) </span><span class="sxs-lookup"><span data-stu-id="f8012-129">[Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md) </span></span>  
 [<span data-ttu-id="f8012-130">规划消息安全性</span><span class="sxs-lookup"><span data-stu-id="f8012-130">Planning Message Security</span></span>](../core/planning-message-security.md)