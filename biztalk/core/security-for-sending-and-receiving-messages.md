---
title: "用于发送和接收消息的安全 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, receiving
- messages, sending
- messages, processing
- security, messages
- security, message processing
- messages, security
ms.assetid: 9bcd01e4-245a-4f4c-b65c-89d7cd3d1b68
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1328eb98cbf94b85cda16eda431da197c6d0126
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="security-for-sending-and-receiving-messages"></a><span data-ttu-id="2002a-102">发送和接收消息过程中的安全性</span><span class="sxs-lookup"><span data-stu-id="2002a-102">Security for Sending and Receiving Messages</span></span>
<span data-ttu-id="2002a-103">下图显示了 BizTalk Server 接收、处理消息以及将消息发送到另一个应用程序或合作伙伴时，对消息执行的操作。</span><span class="sxs-lookup"><span data-stu-id="2002a-103">The following figure shows what happens to a message as BizTalk Server receives it, processes it, and sends it to another application or partner.</span></span>  
  
 <span data-ttu-id="2002a-104">![安全消息的安全功能](../core/media/ebiz-plan-secoverview.gif "ebiz_plan_secoverview")</span><span class="sxs-lookup"><span data-stu-id="2002a-104">![Security features for secure messages](../core/media/ebiz-plan-secoverview.gif "ebiz_plan_secoverview")</span></span>  
<span data-ttu-id="2002a-105">消息生存期中使用的安全功能</span><span class="sxs-lookup"><span data-stu-id="2002a-105">Security features used throughout the lifetime of a message</span></span>  
  
1.  <span data-ttu-id="2002a-106">适配器的接收位置接收消息。</span><span class="sxs-lookup"><span data-stu-id="2002a-106">The receive location for the adapter receives the message.</span></span> <span data-ttu-id="2002a-107">根据协议的具体情况，适配器在协议级别对发件人进行验证，以标识表示消息发件人的 Windows 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="2002a-107">Depending on the protocol, the adapter does protocol-level authentication of the sender to identify a Windows user account that represents the sender of the message.</span></span>  
  
2.  <span data-ttu-id="2002a-108">然后适配器将消息传递到管道，如果在适配器中还没有执行消息级别的验证，则此时在管道中执行该验证。</span><span class="sxs-lookup"><span data-stu-id="2002a-108">The adapter then passes the message to the pipeline, where message-level authentication takes place if it has not already happened in the adapter.</span></span>  
  
    1.  <span data-ttu-id="2002a-109">在解码阶段，管道将对消息进行解密，然后使用消息附带的证书或者本地计算机的“其他人”证书存储中配置的证书，来验证签名的有效性。</span><span class="sxs-lookup"><span data-stu-id="2002a-109">In the Decode stage, the pipeline decrypts the message and verifies the validity of the signature with the certificate attached to the message, or the one configured in the Other People certificate store of the local computer.</span></span> <span data-ttu-id="2002a-110">管道对签名进行验证后，解码组件将对证书链进行验证，直至到达受信任根证书颁发机构 (CA)。</span><span class="sxs-lookup"><span data-stu-id="2002a-110">After the pipeline validates the signature, the decoding component validates the certificate chain up to a trusted root Certificate Authority (CA).</span></span> <span data-ttu-id="2002a-111">如果将管道配置为对 S/MIME 消息进行解码，并且发件人使用 S/MIME 对消息进行了加密，则 MIME/SMIME 解码器将验证消息的签名，然后使用证书识别发件人。</span><span class="sxs-lookup"><span data-stu-id="2002a-111">If you configure the pipeline to decode S/MIME messages, and the sender encrypted the message using S/MIME, the MIME/SMIME decoder verifies the signature of the message, and uses the certificate to identify the sender.</span></span> <span data-ttu-id="2002a-112">有关如何使用 MIME/SMIME 解码器管道组件的详细信息，请参阅[实现消息安全](../core/implementing-message-security.md)。</span><span class="sxs-lookup"><span data-stu-id="2002a-112">For more information about how to use MIME/SMIME decoder pipeline components, see [Implementing Message Security](../core/implementing-message-security.md).</span></span>  
  
    2.  <span data-ttu-id="2002a-113">在参与方解析阶段，BizTalk Server 将使用从协议级别验证获取的证书信息和发件人安全 ID (SSID) 来确定消息的发件人是否是系统中已知的参与方。</span><span class="sxs-lookup"><span data-stu-id="2002a-113">In the Party Resolution stage, BizTalk Server uses the certificate information and the Sender Security ID (SSID) obtained from protocol-level authentication to determine whether the sender of the message is a recognized party in the system.</span></span> <span data-ttu-id="2002a-114">发件人 SSID 是由适配器验证的用户限定名。</span><span class="sxs-lookup"><span data-stu-id="2002a-114">The Sender SSID is the qualified name of the user authenticated by the adapter.</span></span> <span data-ttu-id="2002a-115">例如，</span><span class="sxs-lookup"><span data-stu-id="2002a-115">For example.</span></span> <span data-ttu-id="2002a-116">如果 BizTalk Server 通过 HTTP 适配器使用 Windows 验证接收消息，则发件人 SSID 为“域\用户名”格式。</span><span class="sxs-lookup"><span data-stu-id="2002a-116">If BizTalk Server receives the message by way of the HTTP adapter using Windows authentication, then the sender SSID is domain\username.</span></span> <span data-ttu-id="2002a-117">BizTalk Server 将方 ID (PID) 分配给消息，这是识别方，当事方 ID 或来宾 id。</span><span class="sxs-lookup"><span data-stu-id="2002a-117">BizTalk Server assigns a Party ID (PID) to the message, which is either the party ID of a recognized party, or a guest ID.</span></span> <span data-ttu-id="2002a-118">有关如何使用方解析组件的详细信息，请参阅[使用证书的参与方解析](../core/using-certificates-for-party-resolution.md)。</span><span class="sxs-lookup"><span data-stu-id="2002a-118">For more information about how to use party resolution component, see [Using Certificates for Party Resolution](../core/using-certificates-for-party-resolution.md).</span></span>  
  
    3.  <span data-ttu-id="2002a-119">如果将接收端口配置为要求验证发件人是系统中的已知参与方，而 BizTalk Server 找不到消息发件人的 PID，则 BizTalk Server 会根据接收端口的配置丢弃或挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="2002a-119">If you configured the receiving port to require the sender to be authenticated to a known party in the system, and BizTalk Server is not able to find a PID for the sender of the message, then BizTalk Server drops or suspends the message depending on the configuration of the receive port.</span></span> <span data-ttu-id="2002a-120">BizTalk Server 提供此功能来规避拒绝服务攻击的威胁。</span><span class="sxs-lookup"><span data-stu-id="2002a-120">BizTalk Server provides this feature to mitigate Denial of Service attacks.</span></span> <span data-ttu-id="2002a-121">接收端口的身份验证选项有关的详细信息，请参阅[如何将身份验证选项配置为接收端口](../core/how-to-configure-authentication-options-for-a-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="2002a-121">For more information about the authentication options for receive ports, see [How to Configure Authentication Options for a Receive Port](../core/how-to-configure-authentication-options-for-a-receive-port.md).</span></span>  
  
3.  <span data-ttu-id="2002a-122">管道对消息进行验证后，会将该消息发送到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="2002a-122">After the pipeline authenticates the message, it sends the message to the MessageBox database.</span></span>  
  
    1.  <span data-ttu-id="2002a-123">如果排队的主机（运行管道的主机）未标识为受信任验证主机，则 MessageBox 数据库将用来宾 ID 覆盖 PID，用运行排队主机实例的服务帐户覆盖 SSID。</span><span class="sxs-lookup"><span data-stu-id="2002a-123">If you did not identify the enqueuing host (on which the pipeline is running) as an authentication trusted host, the MessageBox database overwrites the PID with the guest ID, and the SSID with the service account that the enqueuing host instance is running as.</span></span> <span data-ttu-id="2002a-124">有关身份验证信任的主机的详细信息，请参阅[身份验证的消息之间进程](../core/authentication-of-messages-between-processes.md)。</span><span class="sxs-lookup"><span data-stu-id="2002a-124">For more information about authentication trusted host, see [Authentication of Messages Between Processes](../core/authentication-of-messages-between-processes.md).</span></span> <span data-ttu-id="2002a-125">有关如何配置身份验证信任的主机的详细信息，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="2002a-125">For more information about how to configure authentication trusted host, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
    2.  <span data-ttu-id="2002a-126">如果运行管道的主机标记为受信任验证，则 MessageBox 数据库信任该 PID 和 SSID，并将此信息留在消息的上下文中，以便下游流程能使用此信息对消息的原始发件人进行验证和/或授权。</span><span class="sxs-lookup"><span data-stu-id="2002a-126">If the host on which the pipeline is running is marked as authentication trusted, the MessageBox database trusts the PID and SSID, and leaves this information in the context of the message so that downstream processes can use this information to authenticate and/or authorize the original sender of the message.</span></span>  
  
    3.  <span data-ttu-id="2002a-127">如果 BizTalk Server 需要接收授权，则 MessageBox 数据库将验证订阅消息的主机有接收该消息的授权。</span><span class="sxs-lookup"><span data-stu-id="2002a-127">If BizTalk Server requires receive authorization, the MessageBox database verifies that the hosts subscribed to the message have authorization to receive it.</span></span> <span data-ttu-id="2002a-128">有关详细信息收到授权，请参阅[授权一条消息的接收方](../core/authorizing-the-receiver-of-a-message.md)。</span><span class="sxs-lookup"><span data-stu-id="2002a-128">For more information about receive authorization, see [Authorizing the Receiver of a Message](../core/authorizing-the-receiver-of-a-message.md).</span></span>  
  
4.  <span data-ttu-id="2002a-129">BizTalk Server 对消息进行处理后，出站管道将在编码阶段对消息进行加密和/或数字签名。</span><span class="sxs-lookup"><span data-stu-id="2002a-129">After BizTalk Server processes the message, the outbound pipeline encrypts and/or digitally signs the message in the encode stage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2002a-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2002a-130">See Also</span></span>  
 <span data-ttu-id="2002a-131">[实现消息安全性](../core/implementing-message-security.md) </span><span class="sxs-lookup"><span data-stu-id="2002a-131">[Implementing Message Security](../core/implementing-message-security.md) </span></span>  
 [<span data-ttu-id="2002a-132">规划消息安全</span><span class="sxs-lookup"><span data-stu-id="2002a-132">Planning Message Security</span></span>](../core/planning-message-security.md)