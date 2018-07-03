---
title: BizTalk Server 中的安全功能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Server, security
- Master Secret server, security
- security, Master Secret server
- security, runtime
- security, data
- deploying, security
- security, configuring
- runtime, security
- security, security features
- security, messages
- security, access control
- security, about security
- access control
- security, deploying
- data, security
- messages, security
ms.assetid: 5ab15023-fa71-439e-b3aa-420fe28806fa
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d904bc842cb04bdf9c1457440c838c8a78e5c8f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992614"
---
# <a name="security-features-in-biztalk-server"></a><span data-ttu-id="07000-102">BizTalk Server 中的安全功能</span><span class="sxs-lookup"><span data-stu-id="07000-102">Security Features in BizTalk Server</span></span>
<span data-ttu-id="07000-103">Microsoft® BizTalk® Server 提供了一个标准网关以便在 Intranet 中或通过 Internet 发送和接收文档。</span><span class="sxs-lookup"><span data-stu-id="07000-103">Microsoft® BizTalk® Server provides a standard gateway for sending and receiving documents both within an intranet and through the Internet.</span></span> <span data-ttu-id="07000-104">由于发往和从 BizTalk Server 发回的消息可能是业务关键信息，因此在传输消息时以及当 BizTalk Server 处理并存储消息时，采取措施保护这些消息及其所包含信息的安全非常重要。</span><span class="sxs-lookup"><span data-stu-id="07000-104">Due to the possible business-critical nature of the messages sent to and from BizTalk Server, it is important to consider measures to help secure these messages and the information they contain both as they are in transit and while BizTalk Server processes and stores them.</span></span> <span data-ttu-id="07000-105">本部分提供了有关 BizTalk Server 安全功能的信息，并介绍如何使用这些功能来确保数据和环境的安全。</span><span class="sxs-lookup"><span data-stu-id="07000-105">This section provides information about the BizTalk Server security features, and how you can use them to help secure your data and environment.</span></span>  
  
 <span data-ttu-id="07000-106">BizTalk Server 采用以下措施来确保入站和出站消息的安全，确保运行时和配置信息的安全，以及确保与其他应用程序和系统进行安全地集成：</span><span class="sxs-lookup"><span data-stu-id="07000-106">BizTalk Server uses the following measures to help secure inbound and outbound messages, to help secure the runtime and configuration information, and to help integrate securely with other applications and systems:</span></span>  
  
 <span data-ttu-id="07000-107">**消息安全**</span><span class="sxs-lookup"><span data-stu-id="07000-107">**Message security**</span></span>  
  
- <span data-ttu-id="07000-108">对消息的发件人进行验证。</span><span class="sxs-lookup"><span data-stu-id="07000-108">Authenticating the sender of a message.</span></span> <span data-ttu-id="07000-109">BizTalk Server 能够进行身份验证 （通过证书信息或 Windows 集成的安全性） 的消息的发送方验证消息的发件人的身份。</span><span class="sxs-lookup"><span data-stu-id="07000-109">BizTalk Server can authenticate the sender of a message (either by using the certificate information or Windows integrated Security) in order to validate the identity of the sender of the message.</span></span> <span data-ttu-id="07000-110">有关详细信息，请参阅[入站消息身份验证](../core/inbound-message-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="07000-110">For more information, see [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>  
  
- <span data-ttu-id="07000-111">向消息的收件人进行授权。</span><span class="sxs-lookup"><span data-stu-id="07000-111">Authorizing of the receiver of a message.</span></span> <span data-ttu-id="07000-112">BizTalk Server 收到消息后，可确定哪些流程和用户有权接收消息。</span><span class="sxs-lookup"><span data-stu-id="07000-112">After BizTalk Server receives the message, BizTalk Server can determine what processes and users have permissions to receive the message.</span></span> <span data-ttu-id="07000-113">有关详细信息，请参阅[向消息收件人授权](../core/authorizing-the-receiver-of-a-message.md)。</span><span class="sxs-lookup"><span data-stu-id="07000-113">For more information, see [Authorizing the Receiver of a Message](../core/authorizing-the-receiver-of-a-message.md).</span></span>  
  
  <span data-ttu-id="07000-114">**运行时和配置安全**</span><span class="sxs-lookup"><span data-stu-id="07000-114">**Runtime and configuration security**</span></span>  
  
- <span data-ttu-id="07000-115">**访问控制和保护数据。**</span><span class="sxs-lookup"><span data-stu-id="07000-115">**Access control and securing data.**</span></span> <span data-ttu-id="07000-116">BizTalk Server 使用访问控制来确保 BizTalk Server 流程有适当的限制，并且对业务关键信息的访问受到了控制。</span><span class="sxs-lookup"><span data-stu-id="07000-116">BizTalk Server uses access control to ensure that BizTalk Server processes have appropriate limits and that access to business critical information is controlled.</span></span> <span data-ttu-id="07000-117">换句话说，BizTalk Server 确保用户和帐户具有完成任务所需的最小用户权限。</span><span class="sxs-lookup"><span data-stu-id="07000-117">In other words, BizTalk Server ensures that users and accounts have the least user rights possible to enable them to do their tasks.</span></span> <span data-ttu-id="07000-118">有关详细信息，请参阅[访问控制和数据安全性](../core/access-control-and-data-security.md)。</span><span class="sxs-lookup"><span data-stu-id="07000-118">For more information, see [Access Control and Data Security](../core/access-control-and-data-security.md).</span></span>  
  
  <span data-ttu-id="07000-119">**集成的安全性**</span><span class="sxs-lookup"><span data-stu-id="07000-119">**Integrated security**</span></span>  
  
- <span data-ttu-id="07000-120">企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="07000-120">Enterprise Single Sign-On.</span></span> <span data-ttu-id="07000-121">BizTalk Server 使用企业单一登录 (SSO) 确保对适配器、发送和接收位置所需的敏感配置信息进行加密，从而确保 BizTalk Server 以安全方式存储和传输此信息。</span><span class="sxs-lookup"><span data-stu-id="07000-121">BizTalk Server uses Enterprise Single Sign-On (SSO) to ensure that it encrypts the sensitive configuration information that the adapters, send, and receive locations require, thus helping to ensure that BizTalk Server stores and transmit this information in a secure manner.</span></span> <span data-ttu-id="07000-122">有关详细信息，请参阅[使用 SSO](../core/using-sso.md)。</span><span class="sxs-lookup"><span data-stu-id="07000-122">For more information, see [Using SSO](../core/using-sso.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07000-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="07000-123">See Also</span></span>  
 <span data-ttu-id="07000-124">[为 BizTalk Server 设计系统体系结构](../core/designing-the-system-architectures-for-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="07000-124">[Designing the System Architectures for BizTalk Server](../core/designing-the-system-architectures-for-biztalk-server.md) </span></span>  
 <span data-ttu-id="07000-125">[实现企业单一登录](../core/implementing-enterprise-single-sign-on.md) </span><span class="sxs-lookup"><span data-stu-id="07000-125">[Implementing Enterprise Single Sign-On](../core/implementing-enterprise-single-sign-on.md) </span></span>  
 <span data-ttu-id="07000-126">[规划消息安全性](../core/planning-message-security.md) </span><span class="sxs-lookup"><span data-stu-id="07000-126">[Planning Message Security](../core/planning-message-security.md) </span></span>  
 [<span data-ttu-id="07000-127">访问控制和数据安全性</span><span class="sxs-lookup"><span data-stu-id="07000-127">Access Control and Data Security</span></span>](../core/access-control-and-data-security.md)   
