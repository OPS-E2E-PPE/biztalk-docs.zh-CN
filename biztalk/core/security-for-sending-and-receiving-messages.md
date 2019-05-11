---
title: 发送和接收消息的安全性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, receiving
- messages, sending
- messages, processing
- security, messages
- security, message processing
- messages, security
ms.assetid: 9bcd01e4-245a-4f4c-b65c-89d7cd3d1b68
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dfaf4b02c674995c2e60c694d439281d6d632ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280431"
---
# <a name="security-for-sending-and-receiving-messages"></a><span data-ttu-id="0c823-102">发送和接收消息的安全性</span><span class="sxs-lookup"><span data-stu-id="0c823-102">Security for Sending and Receiving Messages</span></span>
<span data-ttu-id="0c823-103">下图显示了当 BizTalk Server 接收、 处理它，并将其发送到另一个应用程序或合作伙伴，一条消息会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="0c823-103">The following figure shows what happens to a message as BizTalk Server receives it, processes it, and sends it to another application or partner.</span></span>  
  
 <span data-ttu-id="0c823-104">![安全消息的安全功能](../core/media/ebiz-plan-secoverview.gif "ebiz_plan_secoverview")</span><span class="sxs-lookup"><span data-stu-id="0c823-104">![Security features for secure messages](../core/media/ebiz-plan-secoverview.gif "ebiz_plan_secoverview")</span></span>  
<span data-ttu-id="0c823-105">一条消息的整个生存期中使用的安全功能</span><span class="sxs-lookup"><span data-stu-id="0c823-105">Security features used throughout the lifetime of a message</span></span>  
  
1.  <span data-ttu-id="0c823-106">该适配器的接收位置接收的消息。</span><span class="sxs-lookup"><span data-stu-id="0c823-106">The receive location for the adapter receives the message.</span></span> <span data-ttu-id="0c823-107">根据协议，该适配器在协议级别身份验证的发件人标识表示消息的发件人的 Windows 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="0c823-107">Depending on the protocol, the adapter does protocol-level authentication of the sender to identify a Windows user account that represents the sender of the message.</span></span>  
  
2.  <span data-ttu-id="0c823-108">适配器然后将消息传递到管道，其中消息级别进行身份验证，如果不出现在适配器中。</span><span class="sxs-lookup"><span data-stu-id="0c823-108">The adapter then passes the message to the pipeline, where message-level authentication takes place if it has not already happened in the adapter.</span></span>  
  
    1.  <span data-ttu-id="0c823-109">在解码阶段中，管道对消息进行解密，证书附加到消息，或从一台本地计算机其他人证书存储中配置验证签名的有效性。</span><span class="sxs-lookup"><span data-stu-id="0c823-109">In the Decode stage, the pipeline decrypts the message and verifies the validity of the signature with the certificate attached to the message, or the one configured in the Other People certificate store of the local computer.</span></span> <span data-ttu-id="0c823-110">管道对签名进行验证后，解码组件将验证由受信任的根证书颁发机构 (CA) 的证书链。</span><span class="sxs-lookup"><span data-stu-id="0c823-110">After the pipeline validates the signature, the decoding component validates the certificate chain up to a trusted root Certificate Authority (CA).</span></span> <span data-ttu-id="0c823-111">如果配置管道以 S/MIME 消息解码和发件人使用 S/MIME 消息进行了加密，则 MIME/SMIME 解码器签名验证的消息，并使用证书进行标识发件人。</span><span class="sxs-lookup"><span data-stu-id="0c823-111">If you configure the pipeline to decode S/MIME messages, and the sender encrypted the message using S/MIME, the MIME/SMIME decoder verifies the signature of the message, and uses the certificate to identify the sender.</span></span> <span data-ttu-id="0c823-112">有关如何使用 MIME/SMIME 解码器管道组件的详细信息，请参阅[实施消息安全性](../core/implementing-message-security.md)。</span><span class="sxs-lookup"><span data-stu-id="0c823-112">For more information about how to use MIME/SMIME decoder pipeline components, see [Implementing Message Security](../core/implementing-message-security.md).</span></span>  
  
    2.  <span data-ttu-id="0c823-113">在参与方解析阶段中，BizTalk Server 使用的证书信息和发件人安全 ID (SSID) 获取从协议级别身份验证来确定消息的发件人是否是系统中已知的参与方。</span><span class="sxs-lookup"><span data-stu-id="0c823-113">In the Party Resolution stage, BizTalk Server uses the certificate information and the Sender Security ID (SSID) obtained from protocol-level authentication to determine whether the sender of the message is a recognized party in the system.</span></span> <span data-ttu-id="0c823-114">发件人 SSID 是用户的由适配器身份验证的限定的名称。</span><span class="sxs-lookup"><span data-stu-id="0c823-114">The Sender SSID is the qualified name of the user authenticated by the adapter.</span></span> <span data-ttu-id="0c823-115">有关示例。</span><span class="sxs-lookup"><span data-stu-id="0c823-115">For example.</span></span> <span data-ttu-id="0c823-116">如果 BizTalk Server 接收的消息通过 HTTP 适配器使用 Windows 身份验证，则发件人 SSID 是域 \ 用户名。</span><span class="sxs-lookup"><span data-stu-id="0c823-116">If BizTalk Server receives the message by way of the HTTP adapter using Windows authentication, then the sender SSID is domain\username.</span></span> <span data-ttu-id="0c823-117">BizTalk Server 将参与方 ID (PID) 分配给消息，这是已知的参与方的参与方 ID 或来宾 id。</span><span class="sxs-lookup"><span data-stu-id="0c823-117">BizTalk Server assigns a Party ID (PID) to the message, which is either the party ID of a recognized party, or a guest ID.</span></span> <span data-ttu-id="0c823-118">有关如何使用参与方解析组件的详细信息，请参阅[使用证书进行参与方解析](../core/using-certificates-for-party-resolution.md)。</span><span class="sxs-lookup"><span data-stu-id="0c823-118">For more information about how to use party resolution component, see [Using Certificates for Party Resolution](../core/using-certificates-for-party-resolution.md).</span></span>  
  
    3.  <span data-ttu-id="0c823-119">如果配置的接收端口以要求发件人进行身份验证的已知参与方在系统中，并且 BizTalk Server 不能查找 PID 发送方的消息，则 BizTalk Server 将删除或挂起该消息根据的配置 接收端口。</span><span class="sxs-lookup"><span data-stu-id="0c823-119">If you configured the receiving port to require the sender to be authenticated to a known party in the system, and BizTalk Server is not able to find a PID for the sender of the message, then BizTalk Server drops or suspends the message depending on the configuration of the receive port.</span></span> <span data-ttu-id="0c823-120">BizTalk Server 提供此功能来规避拒绝服务攻击。</span><span class="sxs-lookup"><span data-stu-id="0c823-120">BizTalk Server provides this feature to mitigate Denial of Service attacks.</span></span> <span data-ttu-id="0c823-121">有关接收端口的身份验证选项的详细信息，请参阅[如何配置接收端口的身份验证选项](../core/how-to-configure-authentication-options-for-a-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="0c823-121">For more information about the authentication options for receive ports, see [How to Configure Authentication Options for a Receive Port](../core/how-to-configure-authentication-options-for-a-receive-port.md).</span></span>  
  
3.  <span data-ttu-id="0c823-122">管道对消息进行身份验证后，它会将消息发送到 MessageBox 数据库中。</span><span class="sxs-lookup"><span data-stu-id="0c823-122">After the pipeline authenticates the message, it sends the message to the MessageBox database.</span></span>  
  
    1.  <span data-ttu-id="0c823-123">如果未作为身份验证的受信任主机标识排入队列主机 （正在其运行该管道），MessageBox 数据库将使用来宾 ID 和与作为运行排队主机实例服务帐户的 SSID 覆盖 PID。</span><span class="sxs-lookup"><span data-stu-id="0c823-123">If you did not identify the enqueuing host (on which the pipeline is running) as an authentication trusted host, the MessageBox database overwrites the PID with the guest ID, and the SSID with the service account that the enqueuing host instance is running as.</span></span> <span data-ttu-id="0c823-124">有关受信任验证主机的详细信息，请参阅[身份验证的消息之间进程](../core/authentication-of-messages-between-processes.md)。</span><span class="sxs-lookup"><span data-stu-id="0c823-124">For more information about authentication trusted host, see [Authentication of Messages Between Processes](../core/authentication-of-messages-between-processes.md).</span></span> <span data-ttu-id="0c823-125">有关如何配置受信任的验证主机的详细信息，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="0c823-125">For more information about how to configure authentication trusted host, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
    2.  <span data-ttu-id="0c823-126">如果在其运行管道的主机标记为受信任的身份验证，MessageBox 数据库信任该 PID 和 SSID，并保持消息的上下文中的此信息，以便下游进程可以使用此信息进行身份验证和/或授权消息原始发件的人。</span><span class="sxs-lookup"><span data-stu-id="0c823-126">If the host on which the pipeline is running is marked as authentication trusted, the MessageBox database trusts the PID and SSID, and leaves this information in the context of the message so that downstream processes can use this information to authenticate and/or authorize the original sender of the message.</span></span>  
  
    3.  <span data-ttu-id="0c823-127">如果 BizTalk Server 需要接收授权，MessageBox 数据库将验证订阅该消息的主机能够接收它的授权。</span><span class="sxs-lookup"><span data-stu-id="0c823-127">If BizTalk Server requires receive authorization, the MessageBox database verifies that the hosts subscribed to the message have authorization to receive it.</span></span> <span data-ttu-id="0c823-128">有关详细信息接收授权，请参阅[向消息收件人授权](../core/authorizing-the-receiver-of-a-message.md)。</span><span class="sxs-lookup"><span data-stu-id="0c823-128">For more information about receive authorization, see [Authorizing the Receiver of a Message](../core/authorizing-the-receiver-of-a-message.md).</span></span>  
  
4.  <span data-ttu-id="0c823-129">BizTalk Server 处理消息后，出站管道了加密和/或数字对消息进行签名将在编码阶段。</span><span class="sxs-lookup"><span data-stu-id="0c823-129">After BizTalk Server processes the message, the outbound pipeline encrypts and/or digitally signs the message in the encode stage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c823-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c823-130">See Also</span></span>  
 <span data-ttu-id="0c823-131">[实现消息安全性](../core/implementing-message-security.md) </span><span class="sxs-lookup"><span data-stu-id="0c823-131">[Implementing Message Security](../core/implementing-message-security.md) </span></span>  
 [<span data-ttu-id="0c823-132">规划消息安全性</span><span class="sxs-lookup"><span data-stu-id="0c823-132">Planning Message Security</span></span>](../core/planning-message-security.md)