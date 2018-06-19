---
title: 授权一条消息的接收方 |Microsoft 文档
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
ms.openlocfilehash: 7317cd9c54568edd2c49df026790ee7a1e70fb2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230741"
---
# <a name="authorizing-the-receiver-of-a-message"></a><span data-ttu-id="56042-102">授权一条消息的接收方</span><span class="sxs-lookup"><span data-stu-id="56042-102">Authorizing the Receiver of a Message</span></span>
<span data-ttu-id="56042-103">使用 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以对授权接收消息的流程和参与方进行限制。</span><span class="sxs-lookup"><span data-stu-id="56042-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enables you to limit the processes and parties that you authorize to receive messages.</span></span>  
  
 <span data-ttu-id="56042-104">下图显示了 BizTalk Server 中可用于向消息的收件人进行授权的安全功能。</span><span class="sxs-lookup"><span data-stu-id="56042-104">The following figure shows the security features in BizTalk Server that you use to authorize the receiver of a message.</span></span>  
  
 <span data-ttu-id="56042-105">![授权消息接收方的安全功能](../core/media/ebiz-plan-secoverview-authz.gif "ebiz_plan_secoverview_authz")</span><span class="sxs-lookup"><span data-stu-id="56042-105">![Security features authorizing the message receiver](../core/media/ebiz-plan-secoverview-authz.gif "ebiz_plan_secoverview_authz")</span></span>  
<span data-ttu-id="56042-106">BizTalk Server 用于对消息的收件人进行授权的安全功能。</span><span class="sxs-lookup"><span data-stu-id="56042-106">Security features BizTalk Server uses to authorize the receiver of a message.</span></span>  
  
 <span data-ttu-id="56042-107">可以使用以下安全机制来建立有权接收您发送的消息的人员：</span><span class="sxs-lookup"><span data-stu-id="56042-107">You can use the following security mechanisms to establish who has permission (authorization) to receive the messages that you send:</span></span>  
  
-   <span data-ttu-id="56042-108">**解密。**</span><span class="sxs-lookup"><span data-stu-id="56042-108">**Decryption.**</span></span> <span data-ttu-id="56042-109">请确保将发送给 BizTalk Server 的消息具有的公钥证书用于加密消息它们向 BizTalk Server 发送方。</span><span class="sxs-lookup"><span data-stu-id="56042-109">Make sure the parties that send messages to BizTalk Server have the public key certificate for encrypting messages they send to BizTalk Server.</span></span> <span data-ttu-id="56042-110">BizTalk Server 使用私钥证书对消息进行解密。</span><span class="sxs-lookup"><span data-stu-id="56042-110">BizTalk Server uses the private key certificate to decrypt the message.</span></span>  
  
-   <span data-ttu-id="56042-111">**收到授权。**</span><span class="sxs-lookup"><span data-stu-id="56042-111">**Receive Authorization.**</span></span> <span data-ttu-id="56042-112">可以使用此方法来控制 BizTalk Server 环境中的哪些主机能接收给定消息。</span><span class="sxs-lookup"><span data-stu-id="56042-112">You can use this method to control which hosts within the BizTalk Server environment can receive a given message.</span></span>  
  
-   <span data-ttu-id="56042-113">**加密。**</span><span class="sxs-lookup"><span data-stu-id="56042-113">**Encryption.**</span></span> <span data-ttu-id="56042-114">通过让 BizTalk 使用来自给定参与方的公钥证书对消息进行加密，可确保只有目标参与方才能读取该消息。</span><span class="sxs-lookup"><span data-stu-id="56042-114">By using the public key certificate from a given party when BizTalk encrypts a message, you can ensure that only the intended party is able to read the message.</span></span>  
  
## <a name="receive-authorization"></a><span data-ttu-id="56042-115">接收授权</span><span class="sxs-lookup"><span data-stu-id="56042-115">Receive Authorization</span></span>  
 <span data-ttu-id="56042-116">接收授权是可用于控制哪些主机能接收（订阅）给定消息的方法。</span><span class="sxs-lookup"><span data-stu-id="56042-116">Receive authorization is the method you can use to control which hosts can receive (subscribe for) a given message.</span></span> <span data-ttu-id="56042-117">BizTalk Server 使用的证书信息，如对消息的订阅属性以匹配谓词： MessageBox 数据库将标记为具有该消息解密证书的主机所需身份验证的消息仅路由。</span><span class="sxs-lookup"><span data-stu-id="56042-117">BizTalk Server uses the certificate information as a subscription property to match predicates on the message: the MessageBox database only routes messages marked as authorization required to the hosts that have the decryption certificate for that message.</span></span> <span data-ttu-id="56042-118">要说明该流程，请考虑以下情况：</span><span class="sxs-lookup"><span data-stu-id="56042-118">To illustrate the process, consider the following scenarios:</span></span>  
  
-   <span data-ttu-id="56042-119">**未加密的消息路由：** 时 BizTalk Server 接收一条消息，发送方未进行加密，关于 BizTalk 将消息的路由没有解密限制。</span><span class="sxs-lookup"><span data-stu-id="56042-119">**Routing an un-encrypted message:** When BizTalk Server receives a message that the sender did not encrypt, there is no decryption limitation as to how BizTalk routes the message.</span></span> <span data-ttu-id="56042-120">有或者没有配置接收授权证书的主机都可以接收该消息。</span><span class="sxs-lookup"><span data-stu-id="56042-120">Both hosts with and hosts without receive authorization certificates configured can receive the message.</span></span>  
  
-   <span data-ttu-id="56042-121">**路由加密的消息：** 当加密的消息到达时，接收管道必须包含解密消息解码组件。</span><span class="sxs-lookup"><span data-stu-id="56042-121">**Routing an encrypted message:** When an encrypted message arrives, the receiving pipeline must contain a decoding component that decrypts the message.</span></span> <span data-ttu-id="56042-122">当 BizTalk Server 路由解密后的消息时，BizTalk 会将用于解密该消息的证书指纹作为 MessageBox 数据库订阅机制中的证据，并且只有配置了该证书的主机才能接收该消息。</span><span class="sxs-lookup"><span data-stu-id="56042-122">When BizTalk Server routes a message after it is decrypted, BizTalk uses the certificate thumbprint used to decrypt the message as evidence in the MessageBox database subscription mechanism, and only those hosts configured with that certificate receive the message.</span></span>  
  
 <span data-ttu-id="56042-123">如果要使用接收授权，必须提供要向其授权接收消息的主机的属性中的解密证书指纹。</span><span class="sxs-lookup"><span data-stu-id="56042-123">If you want to use receive authorization, you must provide the thumbprint of the decryption certificate in the properties of the host that you want to authorize to receive the message.</span></span> <span data-ttu-id="56042-124">有关详细信息收到授权，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="56042-124">For more information about receive authorization, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56042-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56042-125">See Also</span></span>  
 <span data-ttu-id="56042-126">[入站的消息身份验证](../core/inbound-message-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="56042-126">[Inbound Message Authentication](../core/inbound-message-authentication.md) </span></span>  
 <span data-ttu-id="56042-127">[进程之间的消息的身份验证](../core/authentication-of-messages-between-processes.md) </span><span class="sxs-lookup"><span data-stu-id="56042-127">[Authentication of Messages Between Processes](../core/authentication-of-messages-between-processes.md) </span></span>  
 <span data-ttu-id="56042-128">[出站消息保护](../core/outbound-message-protection.md) </span><span class="sxs-lookup"><span data-stu-id="56042-128">[Outbound Message Protection](../core/outbound-message-protection.md) </span></span>  
 <span data-ttu-id="56042-129">[对一条消息的发送方进行身份验证](../core/authenticating-the-sender-of-a-message.md) </span><span class="sxs-lookup"><span data-stu-id="56042-129">[Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md) </span></span>  
 [<span data-ttu-id="56042-130">规划消息安全</span><span class="sxs-lookup"><span data-stu-id="56042-130">Planning Message Security</span></span>](../core/planning-message-security.md)