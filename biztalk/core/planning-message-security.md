---
title: "规划消息安全 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- planning, security
- security, messages
- security, planning
- messages, security
ms.assetid: c0f93515-a822-425c-9155-270a179d6b61
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5826db8480d378342ee30993f67bbd60e27751d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="planning-message-security"></a><span data-ttu-id="771ae-102">规划消息安全性</span><span class="sxs-lookup"><span data-stu-id="771ae-102">Planning Message Security</span></span>
<span data-ttu-id="771ae-103">根据你的公司中的安全策略，你可能想要考虑下表来确定必须在 BizTalk Server 环境中实施的安全级别中的问题。</span><span class="sxs-lookup"><span data-stu-id="771ae-103">Based on the security policies in your company, you may want to consider the questions in the following table to determine the level of security that you must implement in your BizTalk Server environment.</span></span> <span data-ttu-id="771ae-104">这些问题的答案将确定所需的消息的安全功能。</span><span class="sxs-lookup"><span data-stu-id="771ae-104">The answers to these questions will determine the security features that you need for messaging.</span></span>  
  
|<span data-ttu-id="771ae-105">问题</span><span class="sxs-lookup"><span data-stu-id="771ae-105">Question</span></span>|<span data-ttu-id="771ae-106">BizTalk Server 安全功能</span><span class="sxs-lookup"><span data-stu-id="771ae-106">BizTalk Server Security Feature</span></span>|  
|--------------|-------------------------------------|  
|<span data-ttu-id="771ae-107">**当接收消息：**</span><span class="sxs-lookup"><span data-stu-id="771ae-107">**When receiving a message:**</span></span>||  
|<span data-ttu-id="771ae-108">如何确定消息的发送方的标识？</span><span class="sxs-lookup"><span data-stu-id="771ae-108">How do you determine the identity of the sender of the message?</span></span>|<span data-ttu-id="771ae-109">在 BizTalk 管道和签名的证书或 Windows 安全 ID (SID) 的方解析组件可用于明确标识消息的发件人。</span><span class="sxs-lookup"><span data-stu-id="771ae-109">You can use the party resolution component in the BizTalk pipeline and the signing certificate or Windows Security ID (SID) to identify the sender of a message positively.</span></span> <span data-ttu-id="771ae-110">有关详细信息，请参阅[入站消息身份验证](../core/inbound-message-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="771ae-110">For more information, see [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>|  
|<span data-ttu-id="771ae-111">你知道当事方发送消息？</span><span class="sxs-lookup"><span data-stu-id="771ae-111">Do you know the party that sent you the message?</span></span>|<span data-ttu-id="771ae-112">可以使用在 BizTalk 管道中方解析组件以确定将消息发送方是否已在你的系统贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="771ae-112">You can use the party resolution component in the BizTalk pipeline to determine whether the party that sent you the message is a trading partner already in your system.</span></span> <span data-ttu-id="771ae-113">有关详细信息，请参阅[入站消息身份验证](../core/inbound-message-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="771ae-113">For more information, see [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>|  
|<span data-ttu-id="771ae-114">你想要避免接收来自你不知道的参与方的消息？</span><span class="sxs-lookup"><span data-stu-id="771ae-114">Do you want to avoid receiving messages from parties you do not know?</span></span>|<span data-ttu-id="771ae-115">可以在端口中使用“要求验证”功能来要求 BizTalk Server 只处理来自已知参与方的消息。</span><span class="sxs-lookup"><span data-stu-id="771ae-115">You can use the authentication required feature in the port to require that BizTalk server processes only the messages from parties that you know.</span></span> <span data-ttu-id="771ae-116">有关详细信息，请参阅[入站消息身份验证](../core/inbound-message-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="771ae-116">For more information, see [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>|  
|<span data-ttu-id="771ae-117">**当发送消息：**</span><span class="sxs-lookup"><span data-stu-id="771ae-117">**When sending a message:**</span></span>||  
|<span data-ttu-id="771ae-118">如何确保传出消息的隐私？</span><span class="sxs-lookup"><span data-stu-id="771ae-118">How do you ensure the privacy of outgoing messages?</span></span>|<span data-ttu-id="771ae-119">你可以加密消息，从而确保仅预定的接收方能够读取该消息。</span><span class="sxs-lookup"><span data-stu-id="771ae-119">You can encrypt the message to ensure that only the intended party can read the message.</span></span> <span data-ttu-id="771ae-120">有关详细信息，请参阅[出站消息保护](../core/outbound-message-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="771ae-120">For more information, see [Outbound Message Protection](../core/outbound-message-protection.md).</span></span>|  
|<span data-ttu-id="771ae-121">如何阻止恶意用户的攻击者篡改该消息在传输过程？</span><span class="sxs-lookup"><span data-stu-id="771ae-121">How do you prevent malicious users from tampering with the message during transmission?</span></span>|<span data-ttu-id="771ae-122">可以使用数字签名来确保消息的完整性。</span><span class="sxs-lookup"><span data-stu-id="771ae-122">You can use digital signatures to ensure the integrity of the message.</span></span> <span data-ttu-id="771ae-123">有关详细信息，请参阅[出站消息保护](../core/outbound-message-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="771ae-123">For more information, see [Outbound Message Protection](../core/outbound-message-protection.md).</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="771ae-124">本节内容</span><span class="sxs-lookup"><span data-stu-id="771ae-124">In This Section</span></span>  
  
-   [<span data-ttu-id="771ae-125">用于发送和接收消息的安全</span><span class="sxs-lookup"><span data-stu-id="771ae-125">Security for Sending and Receiving Messages</span></span>](../core/security-for-sending-and-receiving-messages.md)  
  
-   [<span data-ttu-id="771ae-126">加密和签名证书</span><span class="sxs-lookup"><span data-stu-id="771ae-126">Encryption and Signing Certificates</span></span>](../core/encryption-and-signing-certificates.md)  
  
-   [<span data-ttu-id="771ae-127">对一条消息的发送方进行身份验证</span><span class="sxs-lookup"><span data-stu-id="771ae-127">Authenticating the Sender of a Message</span></span>](../core/authenticating-the-sender-of-a-message.md)  
  
-   [<span data-ttu-id="771ae-128">授权一条消息的接收方</span><span class="sxs-lookup"><span data-stu-id="771ae-128">Authorizing the Receiver of a Message</span></span>](../core/authorizing-the-receiver-of-a-message.md)