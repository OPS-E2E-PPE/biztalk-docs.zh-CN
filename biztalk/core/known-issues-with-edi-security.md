---
title: EDI 安全的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d7f68bc-8460-4656-b9f2-955337458d78
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2d4afab871dc34e3249d2ea3ed7d531b18472a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380676"
---
# <a name="known-issues-with-edi-security"></a><span data-ttu-id="0ec99-102">EDI 安全的已知的问题</span><span class="sxs-lookup"><span data-stu-id="0ec99-102">Known Issues with EDI Security</span></span>
<span data-ttu-id="0ec99-103">本主题介绍了在安全方面的已知的问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI 和 AS2 解决方案。</span><span class="sxs-lookup"><span data-stu-id="0ec99-103">This topic describes known issues with the security of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2 solutions.</span></span>  
  
## <a name="biztalk-will-not-suspend-a-signed-message-from-a-party-for-which-no-certificate-is-set"></a><span data-ttu-id="0ec99-104">BizTalk 不会挂起来自未设置任何证书的参与方的签名消息</span><span class="sxs-lookup"><span data-stu-id="0ec99-104">BizTalk Will Not Suspend a Signed Message from a Party for which No Certificate is Set</span></span>  
 <span data-ttu-id="0ec99-105">如果在参与方 （在参与方的参与方属性页的证书节点中），未设置签名证书，但来自该参与方的传入消息进行签名，BizTalk Server 将不会挂起消息，并引发异常的证书缺失问题.</span><span class="sxs-lookup"><span data-stu-id="0ec99-105">If you do not set a signing certificate on a party (in the Certificate node of the party's Party Properties page), but an incoming message from that party is signed, BizTalk Server will not suspend the message and throw an exception based on the absence of the certificate.</span></span>  
  
 <span data-ttu-id="0ec99-106">如果您替代入站的消息属性 （在上的参与方作为 AS2 消息发送方页），并清除"应对消息进行签名"属性，BizTalk Server 将挂起已签名的传入消息。</span><span class="sxs-lookup"><span data-stu-id="0ec99-106">If you override inbound message properties (on the Party as AS2 Message Sender page), and clear the "Message should be signed" property, BizTalk Server will suspend a signed incoming message.</span></span>  
  
## <a name="access-to-program-files-folder-can-be-limited-to-prevent-file-tampering"></a><span data-ttu-id="0ec99-107">程序文件文件夹的访问权限可以进行限制以防文件被篡改。</span><span class="sxs-lookup"><span data-stu-id="0ec99-107">Access to Program Files Folder Can Be Limited to Prevent File Tampering</span></span>  
 <span data-ttu-id="0ec99-108">如果未经过身份验证的用户提供包含 BizTalk Server 可执行文件和 EDI 架构的 Program Files 文件夹，这些用户可能会修改这些文件。</span><span class="sxs-lookup"><span data-stu-id="0ec99-108">If the Program Files folder that contains BizTalk Server executables and EDI schemas is available to users who are not authenticated, those users can potentially modify those files.</span></span> <span data-ttu-id="0ec99-109">为避免出现该威胁，您可以使用访问控制列表 (Acl) 上的 Program Files 文件夹来限制对受信任的用户访问。</span><span class="sxs-lookup"><span data-stu-id="0ec99-109">To protect against that threat, you can use Access Control Lists (ACLs) on the Program Files folder to limit access to trusted users.</span></span>  
  
## <a name="a-schema-with-a-long-field-can-be-susceptible-to-a-denial-of-service-attack"></a><span data-ttu-id="0ec99-110">具有长字段的架构可以很容易受到拒绝服务攻击</span><span class="sxs-lookup"><span data-stu-id="0ec99-110">A Schema with a Long Field Can Be Susceptible to a Denial-of-Service Attack</span></span>  
 <span data-ttu-id="0ec99-111">自定义的架构具有很长的字段可能会遭到拒绝服务攻击。</span><span class="sxs-lookup"><span data-stu-id="0ec99-111">A custom schema that has a field of very great length could potentially be exploited by a denial-of-service attack.</span></span> <span data-ttu-id="0ec99-112">架构的附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]没有很长的字段，因此通常不是易受攻击。</span><span class="sxs-lookup"><span data-stu-id="0ec99-112">Schemas that are shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] do not have fields with great lengths, and therefore are generally not susceptible to such an attack.</span></span>  
  
## <a name="message-processing-will-be-aborted-if-a-control-number-exceeds-its-maximum-length"></a><span data-ttu-id="0ec99-113">如果控制编号超过了其最大长度，将中止消息处理</span><span class="sxs-lookup"><span data-stu-id="0ec99-113">Message Processing Will Be Aborted If a Control Number Exceeds Its Maximum Length</span></span>  
 <span data-ttu-id="0ec99-114">交换、 组或事务集控制编号具有最大长度限制。</span><span class="sxs-lookup"><span data-stu-id="0ec99-114">An interchange, group, or transaction set control number has a limited maximum length.</span></span> <span data-ttu-id="0ec99-115">如果其中一个控制数字的长度超过最大长度，将中止某一参与方的所有消息的该编码类型的处理。</span><span class="sxs-lookup"><span data-stu-id="0ec99-115">If the length of one of these control numbers exceeds the maximum length, the processing of all messages of that encoding type for a single party will be aborted.</span></span> <span data-ttu-id="0ec99-116">另一种编码类型 (而不是 X12，例如 EDIFACT) 的消息不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="0ec99-116">A message of another encoding type (EDIFACT instead of X12, for example) will not be affected.</span></span> <span data-ttu-id="0ec99-117">这可能表示存在安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="0ec99-117">This could represent a security vulnerability.</span></span>  
  
 <span data-ttu-id="0ec99-118">如果序列号的长度超过最大长度，用户必须重置受影响的参与方的 EDI 属性中的序列号。</span><span class="sxs-lookup"><span data-stu-id="0ec99-118">If the length of a sequence number exceeds the maximum length, the user has to reset the sequence number in the EDI Property for the party affected.</span></span> <span data-ttu-id="0ec99-119">重置数目后，可以再次处理该编码类型的所有消息。</span><span class="sxs-lookup"><span data-stu-id="0ec99-119">After the number has been reset, all messages of that encoding type can once again be processed.</span></span>  
  
 <span data-ttu-id="0ec99-120">对于 X12 消息，一个控件的最大长度数字为九位。</span><span class="sxs-lookup"><span data-stu-id="0ec99-120">For X12 messages, the maximum length of a control number is nine digits.</span></span> <span data-ttu-id="0ec99-121">对于 EDIFACT 消息，控制编号的最大长度是三个字段 14 位数字。</span><span class="sxs-lookup"><span data-stu-id="0ec99-121">For EDIFACT message, the maximum length of a control number is 14 digits over three fields.</span></span>  
  
## <a name="using-the-edi-receive-pipeline-with-an-http-adapter-will-leave-the-connection-open-if-no-ack-is-sent"></a><span data-ttu-id="0ec99-122">如果没有发送任何确认使用 EDI 接收管道，其中包含 HTTP 适配器将保留连接打开</span><span class="sxs-lookup"><span data-stu-id="0ec99-122">Using the EDI Receive Pipeline with an HTTP Adapter Will Leave the Connection Open If No ACK Is Sent</span></span>  
 <span data-ttu-id="0ec99-123">如果您创建的接收位置使用 EDIReceive 管道，并且具有 HTTP 传输类型，则可能出现安全问题。</span><span class="sxs-lookup"><span data-stu-id="0ec99-123">A security issue could occur if you create a receive location that uses the EDIReceive pipeline and has a transport type of HTTP.</span></span> <span data-ttu-id="0ec99-124">EdiReceive 管道将不会生成 HTTP"200 确定"确认。</span><span class="sxs-lookup"><span data-stu-id="0ec99-124">The EdiReceive pipeline will not generate an HTTP "200 OK" acknowledgment.</span></span> <span data-ttu-id="0ec99-125">如果不返回任何 EDI 确认，则连接将不正常终止，但将保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="0ec99-125">If no EDI acknowledgment is returned, the connection will not be terminated gracefully, but will remain open.</span></span> <span data-ttu-id="0ec99-126">超时期限已过期时，该连接将超时时间。</span><span class="sxs-lookup"><span data-stu-id="0ec99-126">The connection will time out when the time-out period has expired.</span></span>  
  
 <span data-ttu-id="0ec99-127">这不是使用 AS2EdiREceive 管道的问题。</span><span class="sxs-lookup"><span data-stu-id="0ec99-127">This is not an issue with the AS2EdiREceive pipeline.</span></span>  
  
## <a name="an-x12-encoded-message-is-suspended-if-port-based-authentication-is-enabled-and-biztalk-server-does-not-have-access-to-the-authorization-and-security-information"></a><span data-ttu-id="0ec99-128">如果启用了基于端口的身份验证，并且 BizTalk Server 不具有访问授权和安全信息的 X12 编码消息被挂起</span><span class="sxs-lookup"><span data-stu-id="0ec99-128">An X12-Encoded Message Is Suspended If Port-Based Authentication Is Enabled and BizTalk Server Does Not Have Access to the Authorization and Security Information</span></span>  
 <span data-ttu-id="0ec99-129">**症状**</span><span class="sxs-lookup"><span data-stu-id="0ec99-129">**Symptom**</span></span>  
  
 <span data-ttu-id="0ec99-130">通过用于已启用的身份验证，并发送不能确定该消息的参与方的接收端口收到一条消息时，BizTalk Server 将挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="0ec99-130">When a message is received over a receive port for which authentication is enabled, and the party that sent the message cannot be determined, BizTalk Server will suspend the message.</span></span>  
  
 <span data-ttu-id="0ec99-131">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="0ec99-131">**Possible Cause**</span></span>  
  
 <span data-ttu-id="0ec99-132">BizTalk Server 的接收端口 （接收端口的"无身份验证"属性被清除） 启用身份验证，如果需要设置为"ISA1-2 （授权限定符和信息）"和"ISA3-4 （安全限定符和信息）"若要处理的交换的属性。</span><span class="sxs-lookup"><span data-stu-id="0ec99-132">If authentication is enabled for a receive port (the "No Authentication" property for the receive port is cleared), BizTalk Server requires settings for the "ISA1-2 (Authorization qualifier and information)" and "ISA3-4 (Security qualifier and information)" properties in order to process the interchange.</span></span> <span data-ttu-id="0ec99-133">这些属性设置为 X12 中的参与方作为交换发送方的参与方的交换处理属性页。</span><span class="sxs-lookup"><span data-stu-id="0ec99-133">These properties are set for a party in the X12 Interchange Processing Properties page for the party as an interchange sender.</span></span> <span data-ttu-id="0ec99-134">如果 BizTalk Server 无法确定这些属性的值，它将挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="0ec99-134">If BizTalk Server cannot determine the values of these properties, it will suspend the message.</span></span>  
  
 <span data-ttu-id="0ec99-135">这可能通过两种方式。</span><span class="sxs-lookup"><span data-stu-id="0ec99-135">This can occur in two ways.</span></span> <span data-ttu-id="0ec99-136">在第一种情况下，如果 BizTalk Server 无法确定参与方发送消息，它将使用 EDI 全局属性并不会访问授权和安全设置。</span><span class="sxs-lookup"><span data-stu-id="0ec99-136">In the first case, if BizTalk Server cannot determine the party that sent the message, it will use the EDI global properties and will not have access to the authorization and security settings.</span></span> <span data-ttu-id="0ec99-137">因此，它将挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="0ec99-137">As a result, it will suspend the message.</span></span> <span data-ttu-id="0ec99-138">在第二种情况下，如果 BizTalk Server 确定参与方，但未配置的参与方 ISA1-2 和 ISA3-4 属性，BizTalk Server 也无权访问授权和安全信息并将挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="0ec99-138">In the second case, if BizTalk Server determines the party, but the ISA1-2 and ISA3-4 properties for the party are not configured, BizTalk Server will again not have access to authorization and security information and will suspend the message.</span></span>  
  
 <span data-ttu-id="0ec99-139">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="0ec99-139">**Resolution**</span></span>  
  
 <span data-ttu-id="0ec99-140">请确保可以识别的消息发送方和 ISA1-2 和 ISA3-4 属性参与方协议中定义。</span><span class="sxs-lookup"><span data-stu-id="0ec99-140">Make sure that the sending party for the message can be identified and that the ISA1-2 and ISA3-4 properties are defined in the party agreement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ec99-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ec99-141">See Also</span></span>  
 [<span data-ttu-id="0ec99-142">EDI 和 AS2 解决方案的疑难解答</span><span class="sxs-lookup"><span data-stu-id="0ec99-142">Troubleshooting EDI and AS2 Solutions</span></span>](../core/troubleshooting-edi-and-as2-solutions.md)