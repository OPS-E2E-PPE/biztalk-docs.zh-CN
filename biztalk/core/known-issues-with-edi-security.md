---
title: "EDI 安全的已知问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d7f68bc-8460-4656-b9f2-955337458d78
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9517f6c5b1aeae06b5989eef12fe269f81a27c74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-edi-security"></a><span data-ttu-id="6fd2f-102">EDI 安全的已知问题</span><span class="sxs-lookup"><span data-stu-id="6fd2f-102">Known Issues with EDI Security</span></span>
<span data-ttu-id="6fd2f-103">本主题介绍 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI 和 AS2 解决方案在安全性方面存在的已知问题。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-103">This topic describes known issues with the security of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2 solutions.</span></span>  
  
## <a name="biztalk-will-not-suspend-a-signed-message-from-a-party-for-which-no-certificate-is-set"></a><span data-ttu-id="6fd2f-104">BizTalk 不会挂起来自未设置任何证书的参与方的签名消息</span><span class="sxs-lookup"><span data-stu-id="6fd2f-104">BizTalk Will Not Suspend a Signed Message from a Party for which No Certificate is Set</span></span>  
 <span data-ttu-id="6fd2f-105">如果您未对某一参与方设置签名证书（在该参与方的“参与方属性”页的“证书”节点），但是来自该参与方的传入消息已签名，BizTalk Server 不会挂起该消息，也不会就此证书缺失问题而引发异常。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-105">If you do not set a signing certificate on a party (in the Certificate node of the party's Party Properties page), but an incoming message from that party is signed, BizTalk Server will not suspend the message and throw an exception based on the absence of the certificate.</span></span>  
  
 <span data-ttu-id="6fd2f-106">如果您替代了入站消息属性（在“作为 AS2 消息发送方的参与方”页上），且清除了“应对消息进行签名”属性，则 BizTalk Server 将挂起已签名的传入消息。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-106">If you override inbound message properties (on the Party as AS2 Message Sender page), and clear the "Message should be signed" property, BizTalk Server will suspend a signed incoming message.</span></span>  
  
## <a name="access-to-program-files-folder-can-be-limited-to-prevent-file-tampering"></a><span data-ttu-id="6fd2f-107">可以对 Program Files 文件夹的访问权限进行限制以防文件被篡改。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-107">Access to Program Files Folder Can Be Limited to Prevent File Tampering</span></span>  
 <span data-ttu-id="6fd2f-108">如果 Program Files 文件夹内包含未授权用户也可访问的 BizTalk Server 可执行文件和 EDI 架构，此类文件可能会被这些用户修改。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-108">If the Program Files folder that contains BizTalk Server executables and EDI schemas is available to users who are not authenticated, those users can potentially modify those files.</span></span> <span data-ttu-id="6fd2f-109">为了防范这种危险，可以使用 Program Files 文件夹上的访问控制列表 (ACL) 来仅对可信用户授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-109">To protect against that threat, you can use Access Control Lists (ACLs) on the Program Files folder to limit access to trusted users.</span></span>  
  
## <a name="a-schema-with-a-long-field-can-be-susceptible-to-a-denial-of-service-attack"></a><span data-ttu-id="6fd2f-110">字段很长的架构容易遭受拒绝服务攻击</span><span class="sxs-lookup"><span data-stu-id="6fd2f-110">A Schema with a Long Field Can Be Susceptible to a Denial-of-Service Attack</span></span>  
 <span data-ttu-id="6fd2f-111">具有很长字段的自定义架构可能会遭到拒绝服务的攻击。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-111">A custom schema that has a field of very great length could potentially be exploited by a denial-of-service attack.</span></span> <span data-ttu-id="6fd2f-112">与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 一起提供的架构没有很长的字段，因此一般不会遭受这种攻击。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-112">Schemas that are shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] do not have fields with great lengths, and therefore are generally not susceptible to such an attack.</span></span>  
  
## <a name="message-processing-will-be-aborted-if-a-control-number-exceeds-its-maximum-length"></a><span data-ttu-id="6fd2f-113">如果控制编号超过了最大长度的限制，消息处理将会中止</span><span class="sxs-lookup"><span data-stu-id="6fd2f-113">Message Processing Will Be Aborted If a Control Number Exceeds Its Maximum Length</span></span>  
 <span data-ttu-id="6fd2f-114">交换、组或者事务集控制编号都存在最大长度限制。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-114">An interchange, group, or transaction set control number has a limited maximum length.</span></span> <span data-ttu-id="6fd2f-115">如果此类控制编号的其中一个编号的长度超出了最大长度限制，则对单个参与方的所有该编码类型消息的处理将中止。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-115">If the length of one of these control numbers exceeds the maximum length, the processing of all messages of that encoding type for a single party will be aborted.</span></span> <span data-ttu-id="6fd2f-116">其他编码类型（如，是 EDIFACT 而不是 X12）的消息将不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-116">A message of another encoding type (EDIFACT instead of X12, for example) will not be affected.</span></span> <span data-ttu-id="6fd2f-117">这样可能产生安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-117">This could represent a security vulnerability.</span></span>  
  
 <span data-ttu-id="6fd2f-118">如果某序列号的长度超出了最大长度限制，用户必须在相应参与方的 EDI 属性中重新设置该序列号。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-118">If the length of a sequence number exceeds the maximum length, the user has to reset the sequence number in the EDI Property for the party affected.</span></span> <span data-ttu-id="6fd2f-119">重新设置该序列号后，该编码类型的所有消息便立即可以重新进行处理。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-119">After the number has been reset, all messages of that encoding type can once again be processed.</span></span>  
  
 <span data-ttu-id="6fd2f-120">对于 X12 消息，控制编号的最大长度为九位。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-120">For X12 messages, the maximum length of a control number is nine digits.</span></span> <span data-ttu-id="6fd2f-121">对于 EDIFACT 消息，控制编号的最大长度为三个字段 14 位。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-121">For EDIFACT message, the maximum length of a control number is 14 digits over three fields.</span></span>  
  
## <a name="using-the-edi-receive-pipeline-with-an-http-adapter-will-leave-the-connection-open-if-no-ack-is-sent"></a><span data-ttu-id="6fd2f-122">使用带 HTTP 适配器的 EDI 接收管道时，如果没有发送任何确认，连接将处于打开状态</span><span class="sxs-lookup"><span data-stu-id="6fd2f-122">Using the EDI Receive Pipeline with an HTTP Adapter Will Leave the Connection Open If No ACK Is Sent</span></span>  
 <span data-ttu-id="6fd2f-123">如果创建的接收位置使用 EDIReceive 管道，但采用 HTTP 传输类型，则可能会导致安全问题。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-123">A security issue could occur if you create a receive location that uses the EDIReceive pipeline and has a transport type of HTTP.</span></span> <span data-ttu-id="6fd2f-124">EdiReceive 管道将不生成 HTTP“200 OK”确认。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-124">The EdiReceive pipeline will not generate an HTTP "200 OK" acknowledgment.</span></span> <span data-ttu-id="6fd2f-125">如果未返回 EDI 确认，连接将以非正常方式终止，但仍保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-125">If no EDI acknowledgment is returned, the connection will not be terminated gracefully, but will remain open.</span></span> <span data-ttu-id="6fd2f-126">当超时期过后，该连接将超时。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-126">The connection will time out when the time-out period has expired.</span></span>  
  
 <span data-ttu-id="6fd2f-127">而 AS2EdiREceive 管道不会出现这种问题。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-127">This is not an issue with the AS2EdiREceive pipeline.</span></span>  
  
## <a name="an-x12-encoded-message-is-suspended-if-port-based-authentication-is-enabled-and-biztalk-server-does-not-have-access-to-the-authorization-and-security-information"></a><span data-ttu-id="6fd2f-128">如果已启用基于端口的身份验证而 BizTalk Server 却无权访问授权和安全信息，X12 编码的消息将挂起</span><span class="sxs-lookup"><span data-stu-id="6fd2f-128">An X12-Encoded Message Is Suspended If Port-Based Authentication Is Enabled and BizTalk Server Does Not Have Access to the Authorization and Security Information</span></span>  
 <span data-ttu-id="6fd2f-129">**症状**</span><span class="sxs-lookup"><span data-stu-id="6fd2f-129">**Symptom**</span></span>  
  
 <span data-ttu-id="6fd2f-130">如果某消息是通过已启用身份验证的接收端口接收的，而又无法确定发送该消息的参与方，BizTalk Server 将挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-130">When a message is received over a receive port for which authentication is enabled, and the party that sent the message cannot be determined, BizTalk Server will suspend the message.</span></span>  
  
 <span data-ttu-id="6fd2f-131">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="6fd2f-131">**Possible Cause**</span></span>  
  
 <span data-ttu-id="6fd2f-132">如果已为某接收端口启用了身份验证（清除了该接收端口的“无验证”属性），则 BizTalk Server 需要获得“ISA1-2 (授权限定符和信息)”和“ISA3-4 (安全限定符和信息)”属性的设置才能处理相应的交换。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-132">If authentication is enabled for a receive port (the "No Authentication" property for the receive port is cleared), BizTalk Server requires settings for the "ISA1-2 (Authorization qualifier and information)" and "ISA3-4 (Security qualifier and information)" properties in order to process the interchange.</span></span> <span data-ttu-id="6fd2f-133">这些属性是在作为交换发送方的参与方的“X12 交换处理属性”页为相应参与方设置的。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-133">These properties are set for a party in the X12 Interchange Processing Properties page for the party as an interchange sender.</span></span> <span data-ttu-id="6fd2f-134">如果 BizTalk Server 不能确定这些属性的值，它将挂起相应消息。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-134">If BizTalk Server cannot determine the values of these properties, it will suspend the message.</span></span>  
  
 <span data-ttu-id="6fd2f-135">这一问题分为两种情况：</span><span class="sxs-lookup"><span data-stu-id="6fd2f-135">This can occur in two ways.</span></span> <span data-ttu-id="6fd2f-136">第一种情况，如果 BizTalk Server 无法确定发送相应消息的参与方，它将使用 EDI 全局属性，并且将无权访问授权和安全设置。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-136">In the first case, if BizTalk Server cannot determine the party that sent the message, it will use the EDI global properties and will not have access to the authorization and security settings.</span></span> <span data-ttu-id="6fd2f-137">因此，它将挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-137">As a result, it will suspend the message.</span></span> <span data-ttu-id="6fd2f-138">第二种情况，如果 BizTalk Server 已确定了相应的参与方，但是该参与方的 ISA1-2 和 ISA3-4 属性并没有进行配置，则 BizTalk Server 也无权访问授权和安全信息，因而将挂起相应消息。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-138">In the second case, if BizTalk Server determines the party, but the ISA1-2 and ISA3-4 properties for the party are not configured, BizTalk Server will again not have access to authorization and security information and will suspend the message.</span></span>  
  
 <span data-ttu-id="6fd2f-139">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="6fd2f-139">**Resolution**</span></span>  
  
 <span data-ttu-id="6fd2f-140">确保可以识别发送消息的参与方，且已在参与方协议中定义 ISA1-2 和 ISA3-4 属性。</span><span class="sxs-lookup"><span data-stu-id="6fd2f-140">Make sure that the sending party for the message can be identified and that the ISA1-2 and ISA3-4 properties are defined in the party agreement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fd2f-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6fd2f-141">See Also</span></span>  
 [<span data-ttu-id="6fd2f-142">EDI 和 AS2 解决方案疑难解答</span><span class="sxs-lookup"><span data-stu-id="6fd2f-142">Troubleshooting EDI and AS2 Solutions</span></span>](../core/troubleshooting-edi-and-as2-solutions.md)