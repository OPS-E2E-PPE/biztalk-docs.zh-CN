---
title: 进程之间的消息的身份验证 |Microsoft 文档
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
ms.openlocfilehash: 1c54fb463353ed6551dcbf5764fae05e63fdb778
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231301"
---
# <a name="authentication-of-messages-between-processes"></a><span data-ttu-id="22b41-102">进程之间的消息的身份验证</span><span class="sxs-lookup"><span data-stu-id="22b41-102">Authentication of Messages Between Processes</span></span>
<span data-ttu-id="22b41-103">下图显示了 BizTalk Server 中可用于在不同 BizTalk 主机之间验证消息的安全功能。</span><span class="sxs-lookup"><span data-stu-id="22b41-103">The following figure shows the security features in BizTalk Server that enable you to authenticate messages between different BizTalk hosts.</span></span>  
  
 <span data-ttu-id="22b41-104">![对消息进行身份验证的安全功能](../core/media/ebiz-plan-secoverview-auth-process.gif "ebiz_plan_secoverview_auth_process")</span><span class="sxs-lookup"><span data-stu-id="22b41-104">![Security features authenticating messages](../core/media/ebiz-plan-secoverview-auth-process.gif "ebiz_plan_secoverview_auth_process")</span></span>  
<span data-ttu-id="22b41-105">BizTalk Server 用于在进程之间验证消息的安全功能。</span><span class="sxs-lookup"><span data-stu-id="22b41-105">Security features BizTalk Server uses to authenticate messages between processes.</span></span>  
  
 <span data-ttu-id="22b41-106">BizTalk Server 收到某个消息，对它进行解密和验证，然后使用有效的参与方 ID (PID) 和证书确定该消息的发件人后，MessageBox 数据库可以验证与该消息匹配的订阅，接着将消息发送到另一个主机进一步进行处理。</span><span class="sxs-lookup"><span data-stu-id="22b41-106">After BizTalk Server receives a message, decrypts and validates the message, and has a valid party ID (PID) and certificate to identity the sender of the message, the MessageBox database is ready to verify the subscriptions that the message matches, and to send this message to other hosts for further processing.</span></span>  
  
 <span data-ttu-id="22b41-107">在消息从一个进程传递到另一个进程时，通常需要将消息原始发件人的标识传递到处理授权、参与方解析以及与发件人相关的业务逻辑的下游进程。</span><span class="sxs-lookup"><span data-stu-id="22b41-107">As a message flows from one process to another, it is often necessary to pass the identity of the original sender of the message to downstream processes for authorization, party resolution, and business logic relating to the sender.</span></span> <span data-ttu-id="22b41-108">但是，若要在未采取某种安全措施或信任机制的情况下在所有主机中传递此信息，将极大地增加对检验所有用户对象和代码（如业务流程、适配器、管道组件和 functoid）是否可信的需求。</span><span class="sxs-lookup"><span data-stu-id="22b41-108">However, enabling all hosts to flow this information without some type of security or trust mechanism would greatly increase the need to verify that all user objects and code (for example, orchestrations, adapters, pipeline components, functoids) are trustworthy.</span></span>  
  
 <span data-ttu-id="22b41-109">为了区分用户对象和代码的信任级别的方法，BizTalk Server 提供“受信任验证”作为主机的一个属性。</span><span class="sxs-lookup"><span data-stu-id="22b41-109">To provide the means to differentiate the level of trust for user objects and code, BizTalk Server provides Authentication Trust as a property of hosts.</span></span> <span data-ttu-id="22b41-110">如果 MessageBox 数据库收到未设置为受信任验证的主机发来的消息，则 MessageBox 数据库将使用来宾 ID 覆盖 PID，并使用运行该主机实例的服务帐户覆盖 SSID。</span><span class="sxs-lookup"><span data-stu-id="22b41-110">When the MessageBox database receives a message from a host that has not been set as authentication trusted, the MessageBox database overwrites the PID with the guest ID, and overwrites the SSID with the service account that the host instance is running as.</span></span> <span data-ttu-id="22b41-111">当主机被标记为受信任验证时，BizTalk 允许该主机在排队进入 MessageBox 数据库的消息上指定任何发件人 SID (SSID) 和参与方 ID (PID)。</span><span class="sxs-lookup"><span data-stu-id="22b41-111">When a host is marked as authentication trusted, BizTalk enables the host to specify any sender SID (SSID) and any party ID (PID) on messages that it queues to the MessageBox database.</span></span>  
  
 <span data-ttu-id="22b41-112">通过指定哪些主机可信哪些主机不可信，可以定义衡量用户对象和代码可信或不可信的安全边界。</span><span class="sxs-lookup"><span data-stu-id="22b41-112">By specifying which hosts are trusted and which are not, you can define security boundaries in which user objects and code can be trusted or not trusted.</span></span> <span data-ttu-id="22b41-113">即，部署到已设置为“受信任验证”主机中的用户对象和代码需要比部署到未设置为“受信任验证”主机中的用户对象和代码更加可靠。</span><span class="sxs-lookup"><span data-stu-id="22b41-113">That is, user objects and code deployed into hosts that have been set to Authentication Trusted need to be more trustworthy than user objects and code deployed to hosts that have not been set to Authentication Trusted.</span></span> <span data-ttu-id="22b41-114">有关如何配置身份验证信任的主机的详细信息，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="22b41-114">For more information about how to configure authentication trusted host, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
 <span data-ttu-id="22b41-115">在 MessageBox 数据库接收消息时，BizTalk Server 将采取以下步骤强制对将该消息发送到 MessageBox 数据库的主机实例进行受信任验证：</span><span class="sxs-lookup"><span data-stu-id="22b41-115">When the MessageBox database receives a message, BizTalk Server takes the following steps to enforce the authentication trust of the host instance sending the message to the MessageBox database:</span></span>  
  
1.  <span data-ttu-id="22b41-116">MessageBox 数据库首先检查 SSID 是否是受信任主机的主机实例服务帐户的 SSID，确定发送消息的主机是否已设置为受信任验证。</span><span class="sxs-lookup"><span data-stu-id="22b41-116">The MessageBox database first determines whether the host sending the message has been set as authentication trusted by checking that the SSID is that of a host instance service account for a trusted host.</span></span>  
  
2.  <span data-ttu-id="22b41-117">如果向 MessageBox 数据库发送消息的主机已设置为受信任验证，则 MessageBox 数据库会将 SSID 和 PID 原样留在消息上下文中，除非消息上下文中的 SID 和 PID 为空。</span><span class="sxs-lookup"><span data-stu-id="22b41-117">If the host that is sending the message to the MessageBox database is authentication trusted, the MessageBox database leaves the SSID and PID in the message context "as is," unless they are empty.</span></span> <span data-ttu-id="22b41-118">如果 SSID 为空，则 MessageBox 数据库会使用调用进程的 SID（也称为主机 SID (HSID)）填充它。</span><span class="sxs-lookup"><span data-stu-id="22b41-118">If the SSID is empty, the MessageBox database populates it with the SID of the calling process, also known as the host SID (HSID).</span></span> <span data-ttu-id="22b41-119">如果 PID 为空，MessageBox 数据库会将其设为来宾 ID。</span><span class="sxs-lookup"><span data-stu-id="22b41-119">If the PID is empty, it sets the PID to the guest ID.</span></span>  
  
3.  <span data-ttu-id="22b41-120">如果向 MessageBox 数据库发送消息的主机未设置为受信任验证，则 SSID 将被 HSID 取代，PID 将被设为“来宾”，而不论这些字段是否已有值。</span><span class="sxs-lookup"><span data-stu-id="22b41-120">If the host that is sending the message to the MessageBox database has not been set as authentication trusted, the SSID is populated with the HSID, and the PID is set to Guest, regardless of whether these fields were already populated.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="22b41-121">如果要让下游进程知道消息原始发件人的 SSID 和 PID，必须将传递消息的所有主机都设为受信任验证。</span><span class="sxs-lookup"><span data-stu-id="22b41-121">If you want a downstream process to know the SSID and PID of the original sender of the message, you must set all hosts that the message passes through as authentication trusted.</span></span> <span data-ttu-id="22b41-122">此外，如果在某个业务流程中接收的消息随即用于构建出站消息，则在入站消息中接收的 SSID 和 PID 必须作为一个属性显式添加到出站消息，才能继续传递这些标识。</span><span class="sxs-lookup"><span data-stu-id="22b41-122">In addition, in cases such as when the message is received and subsequently used to construct outbound messages in an orchestration, the SSID and PID received on inbound messages must be explicitly added as a property to outbound messages in order to flow these identities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="22b41-123">如果将运行管道的主机配置为受信任验证，则 BizTalk Server 会认为该管道是受信任环境。</span><span class="sxs-lookup"><span data-stu-id="22b41-123">If you configured the host where a pipeline is running as authentication trusted, BizTalk Server considers the pipeline to be a trusted environment.</span></span> <span data-ttu-id="22b41-124">因此，请一定要检验受信任验证主机上运行的 BizTalk 管道中包含的所有自定义组件是否也是受信任的。</span><span class="sxs-lookup"><span data-stu-id="22b41-124">Therefore, it is extremely important that you verify that any custom components that are included in a BizTalk pipeline that is running on a host that is authentication trusted are also trusted.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22b41-125">不能将一个服务帐户同时用于受信任验证主机和不受信任验证主机。</span><span class="sxs-lookup"><span data-stu-id="22b41-125">You cannot use the same service account for hosts that are authentication trusted and for hosts that are not authentication trusted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22b41-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22b41-126">See Also</span></span>  
 <span data-ttu-id="22b41-127">[入站的消息身份验证](../core/inbound-message-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="22b41-127">[Inbound Message Authentication](../core/inbound-message-authentication.md) </span></span>  
 <span data-ttu-id="22b41-128">[出站消息保护](../core/outbound-message-protection.md) </span><span class="sxs-lookup"><span data-stu-id="22b41-128">[Outbound Message Protection](../core/outbound-message-protection.md) </span></span>  
 <span data-ttu-id="22b41-129">[对一条消息的发送方进行身份验证](../core/authenticating-the-sender-of-a-message.md) </span><span class="sxs-lookup"><span data-stu-id="22b41-129">[Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md) </span></span>  
 [<span data-ttu-id="22b41-130">授权一条消息的接收方</span><span class="sxs-lookup"><span data-stu-id="22b41-130">Authorizing the Receiver of a Message</span></span>](../core/authorizing-the-receiver-of-a-message.md)