---
title: 进程间的消息身份验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PID
- security, warnings
- processing, messages
- processing, security
- messages, processing
- security, messages
- MessageBox database, authenticating
- SSID
- authenticating, warnings
ms.assetid: fa746ee3-fc22-4e63-a5cc-8bc0cbeb536b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0491946d3e8398fa56914b9f9ff4aaa89edb9228
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358766"
---
# <a name="authentication-of-messages-between-processes"></a><span data-ttu-id="2f7ec-102">进程间的消息身份验证</span><span class="sxs-lookup"><span data-stu-id="2f7ec-102">Authentication of Messages Between Processes</span></span>
<span data-ttu-id="2f7ec-103">下图显示了 BizTalk Server，可用于不同的 BizTalk 主机之间验证消息中的安全功能。</span><span class="sxs-lookup"><span data-stu-id="2f7ec-103">The following figure shows the security features in BizTalk Server that enable you to authenticate messages between different BizTalk hosts.</span></span>  
  
 <span data-ttu-id="2f7ec-104">![验证消息的安全功能](../core/media/ebiz-plan-secoverview-auth-process.gif "ebiz_plan_secoverview_auth_process")</span><span class="sxs-lookup"><span data-stu-id="2f7ec-104">![Security features authenticating messages](../core/media/ebiz-plan-secoverview-auth-process.gif "ebiz_plan_secoverview_auth_process")</span></span>  
<span data-ttu-id="2f7ec-105">BizTalk Server 的安全功能使用进程之间验证消息。</span><span class="sxs-lookup"><span data-stu-id="2f7ec-105">Security features BizTalk Server uses to authenticate messages between processes.</span></span>  
  
 <span data-ttu-id="2f7ec-106">BizTalk Server 接收消息、 解密和验证消息，并具有有效的参与方 ID (PID) 和证书确定该消息的发件人后，MessageBox 数据库就可以以验证订阅该消息匹配，并发送此到其他主机进行进一步处理的消息。</span><span class="sxs-lookup"><span data-stu-id="2f7ec-106">After BizTalk Server receives a message, decrypts and validates the message, and has a valid party ID (PID) and certificate to identity the sender of the message, the MessageBox database is ready to verify the subscriptions that the message matches, and to send this message to other hosts for further processing.</span></span>  
  
 <span data-ttu-id="2f7ec-107">当消息从一个进程流到另一个，它通常是需要将消息的原始发件人的标识传递给授权、 参与方解析和发件人相关的业务逻辑的下游进程。</span><span class="sxs-lookup"><span data-stu-id="2f7ec-107">As a message flows from one process to another, it is often necessary to pass the identity of the original sender of the message to downstream processes for authorization, party resolution, and business logic relating to the sender.</span></span> <span data-ttu-id="2f7ec-108">但是，若要传递此信息而无需某种类型的安全措施或信任机制在所有主机将极大地增加需验证所有用户对象和代码 (例如，业务流程、 适配器、 管道组件和 functoid) 是可信任.</span><span class="sxs-lookup"><span data-stu-id="2f7ec-108">However, enabling all hosts to flow this information without some type of security or trust mechanism would greatly increase the need to verify that all user objects and code (for example, orchestrations, adapters, pipeline components, functoids) are trustworthy.</span></span>  
  
 <span data-ttu-id="2f7ec-109">若要提供区分用户对象和代码的信任级别的方法，BizTalk Server 作为主机的一个属性提供身份验证信任。</span><span class="sxs-lookup"><span data-stu-id="2f7ec-109">To provide the means to differentiate the level of trust for user objects and code, BizTalk Server provides Authentication Trust as a property of hosts.</span></span> <span data-ttu-id="2f7ec-110">MessageBox 数据库从尚未设置为受信任验证主机收到一条消息，MessageBox 数据库将用来宾 ID 覆盖 PID，并使用作为运行主机实例的服务帐户覆盖 SSID。</span><span class="sxs-lookup"><span data-stu-id="2f7ec-110">When the MessageBox database receives a message from a host that has not been set as authentication trusted, the MessageBox database overwrites the PID with the guest ID, and overwrites the SSID with the service account that the host instance is running as.</span></span> <span data-ttu-id="2f7ec-111">在主机标记为受信任的身份验证，BizTalk 允许该主机指定任何发件人 SID (SSID) 和消息在排队进入 MessageBox 数据库参与方 ID (PID)。</span><span class="sxs-lookup"><span data-stu-id="2f7ec-111">When a host is marked as authentication trusted, BizTalk enables the host to specify any sender SID (SSID) and any party ID (PID) on messages that it queues to the MessageBox database.</span></span>  
  
 <span data-ttu-id="2f7ec-112">通过指定哪些主机可信，哪些不能，可以定义用户对象和代码可信或不受信任的安全边界。</span><span class="sxs-lookup"><span data-stu-id="2f7ec-112">By specifying which hosts are trusted and which are not, you can define security boundaries in which user objects and code can be trusted or not trusted.</span></span> <span data-ttu-id="2f7ec-113">也就是说，用户对象和代码部署到已设置为身份验证受信任的主机需要用户对象和代码部署到未设置为受信任验证主机比更值得信任。</span><span class="sxs-lookup"><span data-stu-id="2f7ec-113">That is, user objects and code deployed into hosts that have been set to Authentication Trusted need to be more trustworthy than user objects and code deployed to hosts that have not been set to Authentication Trusted.</span></span> <span data-ttu-id="2f7ec-114">有关如何配置受信任的验证主机的详细信息，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="2f7ec-114">For more information about how to configure authentication trusted host, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
 <span data-ttu-id="2f7ec-115">在 MessageBox 数据库接收一条消息，BizTalk Server 将采取以下步骤以强制实施将消息发送到 MessageBox 数据库的主机实例的受信任验证：</span><span class="sxs-lookup"><span data-stu-id="2f7ec-115">When the MessageBox database receives a message, BizTalk Server takes the following steps to enforce the authentication trust of the host instance sending the message to the MessageBox database:</span></span>  
  
1.  <span data-ttu-id="2f7ec-116">MessageBox 数据库首先确定发送该消息的主机是否已设置为检查 SSID 受信任的主机的主机实例服务帐户的受信任验证。</span><span class="sxs-lookup"><span data-stu-id="2f7ec-116">The MessageBox database first determines whether the host sending the message has been set as authentication trusted by checking that the SSID is that of a host instance service account for a trusted host.</span></span>  
  
2.  <span data-ttu-id="2f7ec-117">如果主机的是将消息发送到 MessageBox 数据库是受信任验证，MessageBox 数据库将保留在"按原样，"的消息上下文的 SSID 和 PID 除非它们为空。</span><span class="sxs-lookup"><span data-stu-id="2f7ec-117">If the host that is sending the message to the MessageBox database is authentication trusted, the MessageBox database leaves the SSID and PID in the message context "as is," unless they are empty.</span></span> <span data-ttu-id="2f7ec-118">如果 SSID 为空，MessageBox 数据库使用填充它调用的过程中，也称为主机 SID (HSID）) 的 SID。</span><span class="sxs-lookup"><span data-stu-id="2f7ec-118">If the SSID is empty, the MessageBox database populates it with the SID of the calling process, also known as the host SID (HSID).</span></span> <span data-ttu-id="2f7ec-119">如果 PID 为空，将其设为来宾 id。</span><span class="sxs-lookup"><span data-stu-id="2f7ec-119">If the PID is empty, it sets the PID to the guest ID.</span></span>  
  
3.  <span data-ttu-id="2f7ec-120">如果使用 HSID 和 PID 填充发送到 MessageBox 数据库邮件尚未设置为受信任，验证 SSID 的主机而不考虑是否已填充这些字段已设置为 Guest。</span><span class="sxs-lookup"><span data-stu-id="2f7ec-120">If the host that is sending the message to the MessageBox database has not been set as authentication trusted, the SSID is populated with the HSID, and the PID is set to Guest, regardless of whether these fields were already populated.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2f7ec-121">如果你想要知道的 SSID 和 PID 的消息的原始发件人的下游进程，则必须设置为受信任验证传递的消息的所有主机。</span><span class="sxs-lookup"><span data-stu-id="2f7ec-121">If you want a downstream process to know the SSID and PID of the original sender of the message, you must set all hosts that the message passes through as authentication trusted.</span></span> <span data-ttu-id="2f7ec-122">此外，在情况下如上时接收到消息，将其随后用于构造在业务流程中的出站消息，接收的 SSID 和 PID 的入站的消息必须显式添加为属性才能继续传递这些出站消息标识。</span><span class="sxs-lookup"><span data-stu-id="2f7ec-122">In addition, in cases such as when the message is received and subsequently used to construct outbound messages in an orchestration, the SSID and PID received on inbound messages must be explicitly added as a property to outbound messages in order to flow these identities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2f7ec-123">如果配置为受信任验证运行管道的主机，BizTalk Server 会认为该管道是受信任的环境。</span><span class="sxs-lookup"><span data-stu-id="2f7ec-123">If you configured the host where a pipeline is running as authentication trusted, BizTalk Server considers the pipeline to be a trusted environment.</span></span> <span data-ttu-id="2f7ec-124">因此，它是非常重要的是受信任验证主机正在运行的 BizTalk 管道中包含任何自定义组件也是受信任验证。</span><span class="sxs-lookup"><span data-stu-id="2f7ec-124">Therefore, it is extremely important that you verify that any custom components that are included in a BizTalk pipeline that is running on a host that is authentication trusted are also trusted.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f7ec-125">受信任验证主机和不受信任验证主机，不能使用相同的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="2f7ec-125">You cannot use the same service account for hosts that are authentication trusted and for hosts that are not authentication trusted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f7ec-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="2f7ec-126">See Also</span></span>  
 <span data-ttu-id="2f7ec-127">[入站的消息身份验证](../core/inbound-message-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="2f7ec-127">[Inbound Message Authentication](../core/inbound-message-authentication.md) </span></span>  
 <span data-ttu-id="2f7ec-128">[出站消息保护](../core/outbound-message-protection.md) </span><span class="sxs-lookup"><span data-stu-id="2f7ec-128">[Outbound Message Protection](../core/outbound-message-protection.md) </span></span>  
 <span data-ttu-id="2f7ec-129">[对消息的发件人进行身份验证](../core/authenticating-the-sender-of-a-message.md) </span><span class="sxs-lookup"><span data-stu-id="2f7ec-129">[Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md) </span></span>  
 [<span data-ttu-id="2f7ec-130">向消息收件人授权</span><span class="sxs-lookup"><span data-stu-id="2f7ec-130">Authorizing the Receiver of a Message</span></span>](../core/authorizing-the-receiver-of-a-message.md)