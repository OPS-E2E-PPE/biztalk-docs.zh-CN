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
ms.openlocfilehash: d1473ef87ccab6d035799f37a44b341e58a27a04
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279951"
---
# <a name="security-features-in-biztalk-server"></a><span data-ttu-id="dea51-102">BizTalk Server 中安全功能</span><span class="sxs-lookup"><span data-stu-id="dea51-102">Security Features in BizTalk Server</span></span>
<span data-ttu-id="dea51-103">Microsoft® BizTalk® Server 提供了用于发送和接收的文档在 intranet 中或通过 Internet 的标准网关。</span><span class="sxs-lookup"><span data-stu-id="dea51-103">Microsoft® BizTalk® Server provides a standard gateway for sending and receiving documents both within an intranet and through the Internet.</span></span> <span data-ttu-id="dea51-104">由于发往和来自 BizTalk Server 的消息的可能的业务关键特性，务必要考虑措施，以帮助安全，这些消息和它们同时包含因为它们是在传输中和时 BizTalk Server 进程和存储的信息它们。</span><span class="sxs-lookup"><span data-stu-id="dea51-104">Due to the possible business-critical nature of the messages sent to and from BizTalk Server, it is important to consider measures to help secure these messages and the information they contain both as they are in transit and while BizTalk Server processes and stores them.</span></span> <span data-ttu-id="dea51-105">本部分提供有关 BizTalk Server 安全功能，以及如何使用它们来帮助保护你的数据和环境的信息。</span><span class="sxs-lookup"><span data-stu-id="dea51-105">This section provides information about the BizTalk Server security features, and how you can use them to help secure your data and environment.</span></span>  
  
 <span data-ttu-id="dea51-106">BizTalk Server 使用以下措施来保护入站和出站消息，来帮助保护的运行时和配置信息，并帮助安全地与其他应用程序和系统集成：</span><span class="sxs-lookup"><span data-stu-id="dea51-106">BizTalk Server uses the following measures to help secure inbound and outbound messages, to help secure the runtime and configuration information, and to help integrate securely with other applications and systems:</span></span>  
  
 <span data-ttu-id="dea51-107">**消息安全**</span><span class="sxs-lookup"><span data-stu-id="dea51-107">**Message security**</span></span>  
  
- <span data-ttu-id="dea51-108">对消息的发件人进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="dea51-108">Authenticating the sender of a message.</span></span> <span data-ttu-id="dea51-109">BizTalk Server 能够进行身份验证 （通过证书信息或 Windows 集成的安全性） 的消息的发送方验证消息的发件人的身份。</span><span class="sxs-lookup"><span data-stu-id="dea51-109">BizTalk Server can authenticate the sender of a message (either by using the certificate information or Windows integrated Security) in order to validate the identity of the sender of the message.</span></span> <span data-ttu-id="dea51-110">有关详细信息，请参阅[入站消息身份验证](../core/inbound-message-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="dea51-110">For more information, see [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>  
  
- <span data-ttu-id="dea51-111">授权的消息的接收方。</span><span class="sxs-lookup"><span data-stu-id="dea51-111">Authorizing of the receiver of a message.</span></span> <span data-ttu-id="dea51-112">BizTalk Server 接收消息后，BizTalk Server 可以确定哪些进程和用户有权接收消息。</span><span class="sxs-lookup"><span data-stu-id="dea51-112">After BizTalk Server receives the message, BizTalk Server can determine what processes and users have permissions to receive the message.</span></span> <span data-ttu-id="dea51-113">有关详细信息，请参阅[向消息收件人授权](../core/authorizing-the-receiver-of-a-message.md)。</span><span class="sxs-lookup"><span data-stu-id="dea51-113">For more information, see [Authorizing the Receiver of a Message](../core/authorizing-the-receiver-of-a-message.md).</span></span>  
  
  <span data-ttu-id="dea51-114">**运行时和配置安全**</span><span class="sxs-lookup"><span data-stu-id="dea51-114">**Runtime and configuration security**</span></span>  
  
- <span data-ttu-id="dea51-115">**访问控制和保护数据。**</span><span class="sxs-lookup"><span data-stu-id="dea51-115">**Access control and securing data.**</span></span> <span data-ttu-id="dea51-116">BizTalk Server 使用访问控制以确保 BizTalk Server 进程有适当的限制和控制访问的业务关键信息。</span><span class="sxs-lookup"><span data-stu-id="dea51-116">BizTalk Server uses access control to ensure that BizTalk Server processes have appropriate limits and that access to business critical information is controlled.</span></span> <span data-ttu-id="dea51-117">换而言之，BizTalk Server 确保用户和帐户具有的最低用户权限可以启用它们来执行其任务。</span><span class="sxs-lookup"><span data-stu-id="dea51-117">In other words, BizTalk Server ensures that users and accounts have the least user rights possible to enable them to do their tasks.</span></span> <span data-ttu-id="dea51-118">有关详细信息，请参阅[访问控制和数据安全性](../core/access-control-and-data-security.md)。</span><span class="sxs-lookup"><span data-stu-id="dea51-118">For more information, see [Access Control and Data Security](../core/access-control-and-data-security.md).</span></span>  
  
  <span data-ttu-id="dea51-119">**集成的安全性**</span><span class="sxs-lookup"><span data-stu-id="dea51-119">**Integrated security**</span></span>  
  
- <span data-ttu-id="dea51-120">企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="dea51-120">Enterprise Single Sign-On.</span></span> <span data-ttu-id="dea51-121">BizTalk Server 使用企业单一登录 (SSO) 以确保它对适配器，发送和接收位置的敏感配置信息进行加密要求，从而帮助确保 BizTalk Server 将存储和传输中的此信息安全的方式。</span><span class="sxs-lookup"><span data-stu-id="dea51-121">BizTalk Server uses Enterprise Single Sign-On (SSO) to ensure that it encrypts the sensitive configuration information that the adapters, send, and receive locations require, thus helping to ensure that BizTalk Server stores and transmit this information in a secure manner.</span></span> <span data-ttu-id="dea51-122">有关详细信息，请参阅[使用 SSO](../core/using-sso.md)。</span><span class="sxs-lookup"><span data-stu-id="dea51-122">For more information, see [Using SSO](../core/using-sso.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dea51-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="dea51-123">See Also</span></span>  
 <span data-ttu-id="dea51-124">[为 BizTalk Server 设计系统体系结构](../core/designing-the-system-architectures-for-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="dea51-124">[Designing the System Architectures for BizTalk Server](../core/designing-the-system-architectures-for-biztalk-server.md) </span></span>  
 <span data-ttu-id="dea51-125">[实现企业单一登录](../core/implementing-enterprise-single-sign-on.md) </span><span class="sxs-lookup"><span data-stu-id="dea51-125">[Implementing Enterprise Single Sign-On](../core/implementing-enterprise-single-sign-on.md) </span></span>  
 <span data-ttu-id="dea51-126">[规划消息安全性](../core/planning-message-security.md) </span><span class="sxs-lookup"><span data-stu-id="dea51-126">[Planning Message Security](../core/planning-message-security.md) </span></span>  
 [<span data-ttu-id="dea51-127">访问控制和数据安全性</span><span class="sxs-lookup"><span data-stu-id="dea51-127">Access Control and Data Security</span></span>](../core/access-control-and-data-security.md)   
