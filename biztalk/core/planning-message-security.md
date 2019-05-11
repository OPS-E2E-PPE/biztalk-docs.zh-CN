---
title: 规划消息安全性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- planning, security
- security, messages
- security, planning
- messages, security
ms.assetid: c0f93515-a822-425c-9155-270a179d6b61
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 847c53e7e07b4985f5cf2ad1756e3343c335348b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395627"
---
# <a name="planning-message-security"></a><span data-ttu-id="cbbec-102">规划消息安全性</span><span class="sxs-lookup"><span data-stu-id="cbbec-102">Planning Message Security</span></span>
<span data-ttu-id="cbbec-103">根据你的公司中的安全策略，你可能想要考虑下表来确定必须将 BizTalk Server 环境中实现的安全级别中的问题。</span><span class="sxs-lookup"><span data-stu-id="cbbec-103">Based on the security policies in your company, you may want to consider the questions in the following table to determine the level of security that you must implement in your BizTalk Server environment.</span></span> <span data-ttu-id="cbbec-104">这些问题的答案将确定所需的消息传送的安全功能。</span><span class="sxs-lookup"><span data-stu-id="cbbec-104">The answers to these questions will determine the security features that you need for messaging.</span></span>  
  
|<span data-ttu-id="cbbec-105">问题</span><span class="sxs-lookup"><span data-stu-id="cbbec-105">Question</span></span>|<span data-ttu-id="cbbec-106">BizTalk Server 安全功能</span><span class="sxs-lookup"><span data-stu-id="cbbec-106">BizTalk Server Security Feature</span></span>|  
|--------------|-------------------------------------|  
|<span data-ttu-id="cbbec-107">**当接收消息：**</span><span class="sxs-lookup"><span data-stu-id="cbbec-107">**When receiving a message:**</span></span>||  
|<span data-ttu-id="cbbec-108">如何确定消息的发件人标识？</span><span class="sxs-lookup"><span data-stu-id="cbbec-108">How do you determine the identity of the sender of the message?</span></span>|<span data-ttu-id="cbbec-109">BizTalk 管道和签名的证书或 Windows 安全 ID (SID) 中的参与方解析组件可用于正确标识消息的发件人。</span><span class="sxs-lookup"><span data-stu-id="cbbec-109">You can use the party resolution component in the BizTalk pipeline and the signing certificate or Windows Security ID (SID) to identify the sender of a message positively.</span></span> <span data-ttu-id="cbbec-110">有关详细信息，请参阅[入站消息身份验证](../core/inbound-message-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="cbbec-110">For more information, see [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>|  
|<span data-ttu-id="cbbec-111">您是否知道发送消息的参与方？</span><span class="sxs-lookup"><span data-stu-id="cbbec-111">Do you know the party that sent you the message?</span></span>|<span data-ttu-id="cbbec-112">可以使用 BizTalk 管道中的参与方解析组件以确定发送该消息的参与方是否已在系统中的贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="cbbec-112">You can use the party resolution component in the BizTalk pipeline to determine whether the party that sent you the message is a trading partner already in your system.</span></span> <span data-ttu-id="cbbec-113">有关详细信息，请参阅[入站消息身份验证](../core/inbound-message-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="cbbec-113">For more information, see [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>|  
|<span data-ttu-id="cbbec-114">若要避免接收消息从参与方不知道吗？</span><span class="sxs-lookup"><span data-stu-id="cbbec-114">Do you want to avoid receiving messages from parties you do not know?</span></span>|<span data-ttu-id="cbbec-115">可以使用在端口中的身份验证所需的功能需要 BizTalk server 处理仅从已知参与方的消息。</span><span class="sxs-lookup"><span data-stu-id="cbbec-115">You can use the authentication required feature in the port to require that BizTalk server processes only the messages from parties that you know.</span></span> <span data-ttu-id="cbbec-116">有关详细信息，请参阅[入站消息身份验证](../core/inbound-message-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="cbbec-116">For more information, see [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>|  
|<span data-ttu-id="cbbec-117">**如果发送的消息：**</span><span class="sxs-lookup"><span data-stu-id="cbbec-117">**When sending a message:**</span></span>||  
|<span data-ttu-id="cbbec-118">如何确保传出消息的隐私？</span><span class="sxs-lookup"><span data-stu-id="cbbec-118">How do you ensure the privacy of outgoing messages?</span></span>|<span data-ttu-id="cbbec-119">可以对要确保只有预期的参与方可以读取该消息的消息进行加密。</span><span class="sxs-lookup"><span data-stu-id="cbbec-119">You can encrypt the message to ensure that only the intended party can read the message.</span></span> <span data-ttu-id="cbbec-120">有关详细信息，请参阅[出站消息保护](../core/outbound-message-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="cbbec-120">For more information, see [Outbound Message Protection](../core/outbound-message-protection.md).</span></span>|  
|<span data-ttu-id="cbbec-121">如何防止恶意用户的攻击者篡改该消息在传输过程？</span><span class="sxs-lookup"><span data-stu-id="cbbec-121">How do you prevent malicious users from tampering with the message during transmission?</span></span>|<span data-ttu-id="cbbec-122">可以使用数字签名来确保消息的完整性。</span><span class="sxs-lookup"><span data-stu-id="cbbec-122">You can use digital signatures to ensure the integrity of the message.</span></span> <span data-ttu-id="cbbec-123">有关详细信息，请参阅[出站消息保护](../core/outbound-message-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="cbbec-123">For more information, see [Outbound Message Protection](../core/outbound-message-protection.md).</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="cbbec-124">本节内容</span><span class="sxs-lookup"><span data-stu-id="cbbec-124">In This Section</span></span>  
  
-   [<span data-ttu-id="cbbec-125">发送和接收消息过程中的安全性</span><span class="sxs-lookup"><span data-stu-id="cbbec-125">Security for Sending and Receiving Messages</span></span>](../core/security-for-sending-and-receiving-messages.md)  
  
-   [<span data-ttu-id="cbbec-126">加密和签名证书</span><span class="sxs-lookup"><span data-stu-id="cbbec-126">Encryption and Signing Certificates</span></span>](../core/encryption-and-signing-certificates.md)  
  
-   [<span data-ttu-id="cbbec-127">对消息的发件人进行身份验证</span><span class="sxs-lookup"><span data-stu-id="cbbec-127">Authenticating the Sender of a Message</span></span>](../core/authenticating-the-sender-of-a-message.md)  
  
-   [<span data-ttu-id="cbbec-128">向消息收件人授权</span><span class="sxs-lookup"><span data-stu-id="cbbec-128">Authorizing the Receiver of a Message</span></span>](../core/authorizing-the-receiver-of-a-message.md)