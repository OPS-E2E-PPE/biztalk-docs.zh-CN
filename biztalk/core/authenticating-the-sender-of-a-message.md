---
title: 对消息的发件人进行身份验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parties, authenticating
- authenticating, authentication required
- messages, authenticating
- security, authenticating
- digital signatures, authenticating
- security, messages
- MessageBox database, authenticating
- authenticating, authentication trust
- messages, message flow
- authenticating, security
- authenticating, party resolution
- authenticating, digital signatures
- authenticating, messages
ms.assetid: 813a2fb9-0346-4129-9cc5-1713f72a491e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52b0e69a2799bf5b119093e4ac82773014e979b1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019083"
---
# <a name="authenticating-the-sender-of-a-message"></a><span data-ttu-id="191c5-102">对消息的发件人进行身份验证</span><span class="sxs-lookup"><span data-stu-id="191c5-102">Authenticating the Sender of a Message</span></span>
<span data-ttu-id="191c5-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用不同的机制来验证参与方和流程的真实性。</span><span class="sxs-lookup"><span data-stu-id="191c5-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses different mechanisms to verify that a party is who they claim to be, or that a process is what it claims to be.</span></span> <span data-ttu-id="191c5-104">此外，您可以指定流程是否向 BizTalk Server 通知消息的原始发件人，也可指定 BizTalk Server 是否将参与方识别为合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="191c5-104">Furthermore, you can specify whether the process can relay to BizTalk Server who the original sender of the message is, and whether BizTalk Server recognizes the party as a partner.</span></span>  
  
 <span data-ttu-id="191c5-105">下图显示了 BizTalk Server 中可用于对消息的发件人进行验证和授权的安全功能。</span><span class="sxs-lookup"><span data-stu-id="191c5-105">The following figure shows the security features in BizTalk Server that enable you to authenticate and authorize the sender of a message.</span></span>  
  
 <span data-ttu-id="191c5-106">![安全消息的安全功能](../core/media/ebiz-plan-secoverview.gif "ebiz_plan_secoverview")</span><span class="sxs-lookup"><span data-stu-id="191c5-106">![Security features for secure messages](../core/media/ebiz-plan-secoverview.gif "ebiz_plan_secoverview")</span></span>  
<span data-ttu-id="191c5-107">BizTalk Server 用于对消息的发件人进行验证和授权的安全功能</span><span class="sxs-lookup"><span data-stu-id="191c5-107">The security features that BizTalk Server uses to authenticate and authorize the send of a message</span></span>  
  
 <span data-ttu-id="191c5-108">可用于对消息的发件人进行验证的功能包括：</span><span class="sxs-lookup"><span data-stu-id="191c5-108">The features that enable you to authenticate the sender of a message are:</span></span>  
  
- <span data-ttu-id="191c5-109">**数字签名验证。**</span><span class="sxs-lookup"><span data-stu-id="191c5-109">**Digital Signature Validation.**</span></span> <span data-ttu-id="191c5-110">如果消息带有数字签名，则 BizTalk Server 会使用该签名验证发件人的身份。</span><span class="sxs-lookup"><span data-stu-id="191c5-110">If the message has a digital signature, BizTalk Server uses it to verify the identity of the sender.</span></span> <span data-ttu-id="191c5-111">有关如何配置数字签名验证的详细信息，请参阅[如何配置为接收签名消息的 BizTalk Server](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="191c5-111">For more information about how to configure digital signature validation, see [How to Configure BizTalk Server for Receiving Signed Messages](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md).</span></span>  
  
- <span data-ttu-id="191c5-112">**参与方解析。**</span><span class="sxs-lookup"><span data-stu-id="191c5-112">**Party Resolution.**</span></span> <span data-ttu-id="191c5-113">MessageBox 数据库中的所有消息（无论是从 BizTalk Server 内部还是外部发起）都包含一个参与方 ID (PID)，它是通过数字证书或 Windows 帐户与 PID 之间的映射来确定的。</span><span class="sxs-lookup"><span data-stu-id="191c5-113">All messages inserted into the MessageBox database, whether originating inside or outside of BizTalk Server, carry a Party ID (PID) that is determined through either the mapping of a digital certificate or a Windows Account to a PID.</span></span> <span data-ttu-id="191c5-114">有关如何配置参与方解析组件的详细信息，请参阅[使用证书进行参与方解析](../core/using-certificates-for-party-resolution.md)。</span><span class="sxs-lookup"><span data-stu-id="191c5-114">For more information about how to configure party resolution component, see [Using Certificates for Party Resolution](../core/using-certificates-for-party-resolution.md).</span></span>  
  
- <span data-ttu-id="191c5-115">**所需的身份验证。**</span><span class="sxs-lookup"><span data-stu-id="191c5-115">**Authentication required.**</span></span> <span data-ttu-id="191c5-116">如果接收端口无法确定消息的发件人，则 BizTalk 主机可以将该消息作为“来宾”消息接受，或者完全忽略该消息。</span><span class="sxs-lookup"><span data-stu-id="191c5-116">If the receive port is not able to determine the sender of the message, a BizTalk Host can either accept it as a "guest" message, or disregard it altogether.</span></span> <span data-ttu-id="191c5-117">使用此功能可以使来自未知参与方的消息不被处理或存储在跟踪数据库中，因此能够防止您的系统遭到拒绝服务攻击。</span><span class="sxs-lookup"><span data-stu-id="191c5-117">This feature enables you to protect your system from Denial of Service attacks, as messages from unknown parties will not be processed or stored in the tracking database.</span></span> <span data-ttu-id="191c5-118">有关接收端口的身份验证选项的详细信息，请参阅[如何配置接收端口的身份验证选项](../core/how-to-configure-authentication-options-for-a-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="191c5-118">For more information about the authentication options for receive ports, see [How to Configure Authentication Options for a Receive Port](../core/how-to-configure-authentication-options-for-a-receive-port.md).</span></span>  
  
- <span data-ttu-id="191c5-119">**受信任验证。**</span><span class="sxs-lookup"><span data-stu-id="191c5-119">**Authentication Trust.**</span></span> <span data-ttu-id="191c5-120">如果 MessageBox 数据库接收到来自未标识为受信任验证的主机的消息，则 MessageBox 数据库将用来宾 ID 覆盖 PID，用运行该主机实例的服务帐户覆盖 SSID。</span><span class="sxs-lookup"><span data-stu-id="191c5-120">If the MessageBox database receives a message from a host that you did not identify as authentication trusted, the MessageBox database will overwrite the PID with the guest ID, and the SSID with the service account that the host instance is running as.</span></span> <span data-ttu-id="191c5-121">BizTalk Server 将主机标识为受信任验证来表明受信任主机排队到 MessageBox 数据库的消息的发件人是一个实体而不是受信任主机本身。</span><span class="sxs-lookup"><span data-stu-id="191c5-121">BizTalk Server enables hosts identified as authentication trusted to indicate that the sender of a message that the trusted host is queuing to the MessageBox database is an entity other than the trusted host itself.</span></span> <span data-ttu-id="191c5-122">受信任验证的主要目的在于使管道能够解析出 PID，然后将该 PID 传递给授权和出站参与方解析中使用的服务，以及将发件人的 Windows 安全 ID (SSID) 传输到业务流程操作授权中使用的服务。</span><span class="sxs-lookup"><span data-stu-id="191c5-122">The primary purposes of authentication trust are to enable pipelines to resolve to a PID and pass that PID along to consuming services for use in authorization and outbound party resolution, and to enable the transmission of the sender Windows Security ID (SSID) along to consuming services for use in orchestration action authorization.</span></span> <span data-ttu-id="191c5-123">有关受信任验证主机的详细信息，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="191c5-123">For more information about authentication trusted host, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span> <span data-ttu-id="191c5-124">有关如何使用 BizTalk Server 业务流程与参与方解析结合使用的详细信息，请参阅[PartyResolution （BizTalk Server 示例）](../core/partyresolution-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="191c5-124">For more information about how to use BizTalk Server orchestrations in conjunction with party resolution, see [PartyResolution (BizTalk Server Sample)](../core/partyresolution-biztalk-server-sample.md).</span></span>  
  
  <span data-ttu-id="191c5-125">根据是否需要知道是谁向您发送了此消息（即消息的原始发件人），或者消息的收件人或查看人，可以使用图中显示的部分或所有功能。</span><span class="sxs-lookup"><span data-stu-id="191c5-125">Depending upon whether you need to know from whom you received this message, the original sender of the message, or the recipient or viewer of your message, you can use some or all of the features shown in the figure.</span></span>  
  
  <span data-ttu-id="191c5-126">如果对于合作伙伴来说，有必要了解消息确实来自您处并且在传输过程中其他任何人都无法阅读这些消息，则应考虑采用以下技术来确保只有指定的收件人和收件人应用程序才能够接收这些消息：</span><span class="sxs-lookup"><span data-stu-id="191c5-126">If it is important for your partners to know with certainty that messages are from you and that nobody else can read them while they are in transit, you should consider using the following techniques to help ensure that only the specified recipients and recipient applications receive the messages:</span></span>  
  
- <span data-ttu-id="191c5-127">在出站消息中使用数字签名，以便您的合作伙伴能够验证您就是消息的发件人。</span><span class="sxs-lookup"><span data-stu-id="191c5-127">Use digital signatures for outbound messages so that your partner can verify that you are the sender of the message.</span></span>  
  
- <span data-ttu-id="191c5-128">对出站消息进行加密，以确保在传输消息时未经授权的参与方无法查看该消息。</span><span class="sxs-lookup"><span data-stu-id="191c5-128">Encrypt outbound messages to help ensure that unauthorized parties cannot view the message while it is in transit.</span></span>  
  
  <span data-ttu-id="191c5-129">如果有必要确定向您公司发送消息的发件人，并确定在消息发送过程中其他任何人都未阅读该消息，则应考虑采用以下技术来确保只有指定的收件人和收件人应用程序才能够接收这些消息：</span><span class="sxs-lookup"><span data-stu-id="191c5-129">If it is important to determine who sent your company a message and that nobody else read it while it was in transit, you should consider using the following techniques to help ensure that only the specified recipients and recipient applications receive the messages:</span></span>  
  
- <span data-ttu-id="191c5-130">请确保 BizTalk Server 只接受带有数字签名的消息，以便了解是谁发送的消息。</span><span class="sxs-lookup"><span data-stu-id="191c5-130">Make sure BizTalk Server only accepts messages with digital signatures so that you know who sent the message.</span></span>  
  
- <span data-ttu-id="191c5-131">请确保向您的合作伙伴发送公钥证书，该证书用于对发送给 BizTalk Server 的消息进行加密。</span><span class="sxs-lookup"><span data-stu-id="191c5-131">Make sure you send your partners the public key certificate for encrypting the messages they send to BizTalk Server.</span></span> <span data-ttu-id="191c5-132">通过使用加密，可以确保在传输消息时未经授权的参与方无法查看该消息。</span><span class="sxs-lookup"><span data-stu-id="191c5-132">By using encryption, you can help ensure that unauthorized parties cannot view the message while it is in transit.</span></span>  
  
- <span data-ttu-id="191c5-133">在接收端口中使用“要求验证”属性以确保消息来自已知参与方。</span><span class="sxs-lookup"><span data-stu-id="191c5-133">Use the authentication required property in the receive port to ensure the message is from a known party.</span></span>  
  
  <span data-ttu-id="191c5-134">多个主机对消息进行处理后，可能弄不清楚消息的原始发件人是谁。</span><span class="sxs-lookup"><span data-stu-id="191c5-134">After more than one host processes the message, it may not be clear who the original sender of the message is.</span></span> <span data-ttu-id="191c5-135">在必须知道的标识的原始发件人，例如，授予访问权限来发送或接收消息时的情况下[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供了一种安全机制来验证传播通过多个主机的原始发件人标识对下游主机基于该标识访问权限。</span><span class="sxs-lookup"><span data-stu-id="191c5-135">In cases where you must know the identity of the original sender, for example, when granting access to send or receive a message, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides a security mechanism for propagating the identity of the original sender through many hosts in order to validate access to downstream hosts based on that identity.</span></span> <span data-ttu-id="191c5-136">在 BizTalk Server 中，这种安全机制称为流程受信任验证。</span><span class="sxs-lookup"><span data-stu-id="191c5-136">In BizTalk Server, this calls process Authentication trust.</span></span> <span data-ttu-id="191c5-137">有关详细信息，请参阅[身份验证的消息之间进程](../core/authentication-of-messages-between-processes.md)。</span><span class="sxs-lookup"><span data-stu-id="191c5-137">For more information, see [Authentication of Messages Between Processes](../core/authentication-of-messages-between-processes.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="191c5-138">本节内容</span><span class="sxs-lookup"><span data-stu-id="191c5-138">In This Section</span></span>  
  
-   [<span data-ttu-id="191c5-139">入站消息认证</span><span class="sxs-lookup"><span data-stu-id="191c5-139">Inbound Message Authentication</span></span>](../core/inbound-message-authentication.md)  
  
-   [<span data-ttu-id="191c5-140">进程间的消息验证</span><span class="sxs-lookup"><span data-stu-id="191c5-140">Authentication of Messages Between Processes</span></span>](../core/authentication-of-messages-between-processes.md)  
  
-   [<span data-ttu-id="191c5-141">出站消息保护</span><span class="sxs-lookup"><span data-stu-id="191c5-141">Outbound Message Protection</span></span>](../core/outbound-message-protection.md)