---
title: 出站消息保护 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- processing, outbound messages
- outbound messages
- security, messages
- authenticating, warnings
- messages, outbound
ms.assetid: 839d3b44-bb44-454b-817c-67b7c8cd74c9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c451fd13e780c6530fcad7848b11528af3bc1968
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393439"
---
# <a name="outbound-message-protection"></a><span data-ttu-id="63521-102">出站消息保护</span><span class="sxs-lookup"><span data-stu-id="63521-102">Outbound Message Protection</span></span>
<span data-ttu-id="63521-103">下图显示了用于帮助保护免受未经授权方读取的出站消息的 BizTalk Server 中的安全功能。</span><span class="sxs-lookup"><span data-stu-id="63521-103">The following figure shows the security features in BizTalk Server that you use to help protect outbound messages from being read by unauthorized parties.</span></span>  
  
 <span data-ttu-id="63521-104">![保护出站消息的安全功能](../core/media/ebiz-plan-secoverview-auth-outbound.gif "ebiz_plan_secoverview_auth_outbound")</span><span class="sxs-lookup"><span data-stu-id="63521-104">![Security features protecting outbound messages](../core/media/ebiz-plan-secoverview-auth-outbound.gif "ebiz_plan_secoverview_auth_outbound")</span></span>  
<span data-ttu-id="63521-105">BizTalk Server 的安全功能用于保护出站消息。</span><span class="sxs-lookup"><span data-stu-id="63521-105">Security features BizTalk Server uses to protect outbound messages.</span></span>  
  
 <span data-ttu-id="63521-106">当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送消息，它执行以下步骤以帮助确保其安全地发送消息和接收方可以确定消息发件人：</span><span class="sxs-lookup"><span data-stu-id="63521-106">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends a message, it takes the following steps to help ensure that it sends the message securely, and that the receiving party can determine the message sender:</span></span>  
  
1.  <span data-ttu-id="63521-107">如果发送管道中含有配置为对所有出站消息进行签名的编码组件 （例如 S/MIME)，从在其下的主机实例服务帐户的个人证书存储检索 BizTalk 组的签名证书管道运行，并对消息进行签名使用与证书关联的私钥。</span><span class="sxs-lookup"><span data-stu-id="63521-107">If the send pipeline contains an encoding component (such as S/MIME) that is configured to sign all outbound messages, the signing certificate for the BizTalk group is retrieved from the personal certificate store for the host instance service account under which the pipeline is running, and the message is signed using the private key associated with the certificate.</span></span>  
  
2.  <span data-ttu-id="63521-108">如果发送管道中含有配置为对所有出站消息进行加密的编码组件 （例如 S/MIME)，用于从其他人证书存储，并在消息中检索公钥证书的加密证书指纹使用该证书进行加密。</span><span class="sxs-lookup"><span data-stu-id="63521-108">If the send pipeline contains an encoding component (such as S/MIME) that is configured to encrypt all outbound messages, the encryption certificate thumbprint is used to retrieve the public key certificate from the Other People certificate store, and the message is encrypted using that certificate.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="63521-109">尽管您在 BizTalk 环境中的所有发送管道使用一个签名证书，你必须确保此签名证书可在发送管道的主机的每个主机实例的服务帐户的证书存储中正在运行。</span><span class="sxs-lookup"><span data-stu-id="63521-109">Although you use one signing certificate for all the send pipelines in your BizTalk environment, you must ensure this signing certificate is available in the certificate store of the service account of each host instance of the hosts where the send pipelines are running.</span></span>  
  
 <span data-ttu-id="63521-110">有关如何发送签名的消息的详细信息，请参阅[如何配置为发送签名消息的 BizTalk Server](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="63521-110">For more information about how to send signed messages, see [How to Configure BizTalk Server for Sending Signed Messages](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63521-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="63521-111">See Also</span></span>  
 <span data-ttu-id="63521-112">[入站的消息身份验证](../core/inbound-message-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="63521-112">[Inbound Message Authentication](../core/inbound-message-authentication.md) </span></span>  
 <span data-ttu-id="63521-113">[进程间的消息身份验证](../core/authentication-of-messages-between-processes.md) </span><span class="sxs-lookup"><span data-stu-id="63521-113">[Authentication of Messages Between Processes](../core/authentication-of-messages-between-processes.md) </span></span>  
 <span data-ttu-id="63521-114">[对消息的发件人进行身份验证](../core/authenticating-the-sender-of-a-message.md) </span><span class="sxs-lookup"><span data-stu-id="63521-114">[Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md) </span></span>  
 <span data-ttu-id="63521-115">[向消息收件人授权](../core/authorizing-the-receiver-of-a-message.md) </span><span class="sxs-lookup"><span data-stu-id="63521-115">[Authorizing the Receiver of a Message](../core/authorizing-the-receiver-of-a-message.md) </span></span>  
 [<span data-ttu-id="63521-116">BizTalk Server 用于签名消息的证书</span><span class="sxs-lookup"><span data-stu-id="63521-116">Certificates that BizTalk Server Uses for Signed Messages</span></span>](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)