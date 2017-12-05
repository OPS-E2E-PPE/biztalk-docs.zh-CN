---
title: "安全和隐私标准 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, privacy standards
- privacy standards
- security
- security, about security
- BizTalk Accelerator for SWIFT, security
- security, BizTalk Accelerator for SWIFT
ms.assetid: 5794b25f-8a73-4f5b-97ef-1b0f61775c4b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be03cce0c0d482563ac12bbd3b60cead04b2ccfa
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="security-and-privacy-standards"></a><span data-ttu-id="fa02d-102">安全和隐私标准</span><span class="sxs-lookup"><span data-stu-id="fa02d-102">Security and privacy standards</span></span>
<span data-ttu-id="fa02d-103">使用财务服务应用程序和集成解决方案开发[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]通常受本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安全功能。</span><span class="sxs-lookup"><span data-stu-id="fa02d-103">Financial Services applications and integration solutions developed using [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] are generally secured by native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] security features.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="fa02d-104">使用严格的安全机制，如事实上 Internet 加密消息的标准和传输协议，签名证书，[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]身份验证，并使用企业单一登录来保护[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序、 数据和运行时。</span><span class="sxs-lookup"><span data-stu-id="fa02d-104"> uses aggressive security mechanisms such as de facto Internet encrypted messaging standards and transport protocols, signing certificates, [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Authentication, and Enterprise Single Sign-On to secure [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, data, and runtime.</span></span>  
  
 <span data-ttu-id="fa02d-105">使用生成的解决方案[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] 2000， [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，并且 A4SWIFT 可以帮助你为全球 Interbank 财务电信 (SWIFT) 金融交易互联网协会满足的安全和隐私的准则。</span><span class="sxs-lookup"><span data-stu-id="fa02d-105">Solutions built with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] 2000, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], and A4SWIFT can help you to meet the security and privacy guidelines for Society for Worldwide Interbank Financial Telecommunication (SWIFT) financial transactions.</span></span>  
  
 <span data-ttu-id="fa02d-106">除了本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安全功能，A4SWIFT 提供特定于保护最终用户消息项、 修复、 批准和提交 SWIFT 消息用户级安全。</span><span class="sxs-lookup"><span data-stu-id="fa02d-106">In addition to native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] security features, A4SWIFT provides user-level security specific to securing end-user message entry, repair, approval, and submission of SWIFT messages.</span></span> <span data-ttu-id="fa02d-107">通过使用此安全[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]进行数字签名技术以及通过使用 A4SWIFT 运行时服务来验证证书和数据完整性。</span><span class="sxs-lookup"><span data-stu-id="fa02d-107">This security is achieved by using [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] digital signing technologies and by using A4SWIFT runtime services to verify certificate and data integrity.</span></span>  
  
 <span data-ttu-id="fa02d-108">务必要考虑保护 SWIFT 消息和它们包含在输入或最终用户，在传输过程，以及在时编辑时的信息的度量值[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]处理并存储它们。</span><span class="sxs-lookup"><span data-stu-id="fa02d-108">It is important to consider measures for securing your SWIFT messages and the information they contain when they are entered or edited by end-users, in transit, and while [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] processes and stores them.</span></span>  
  
 <span data-ttu-id="fa02d-109">在一起，BizTalk Server 和 A4SWIFT 提供平台、 基础结构，以及用于设计、 开发和执行消息传送的安全 SWIFT 和工作流自动化系统工具。</span><span class="sxs-lookup"><span data-stu-id="fa02d-109">Together, BizTalk Server and A4SWIFT provide the platform, infrastructure, and tools for designing, developing, and executing secure SWIFT messaging and workflow automation systems.</span></span>  
  
 <span data-ttu-id="fa02d-110">在实施安全机制，你必须在设计和开发许多区域。</span><span class="sxs-lookup"><span data-stu-id="fa02d-110">When implementing security, you must design and develop many areas.</span></span> <span data-ttu-id="fa02d-111">下面的列表是这些区域的高级视图：</span><span class="sxs-lookup"><span data-stu-id="fa02d-111">The following list is a high-level view of these areas:</span></span>  
  
-   <span data-ttu-id="fa02d-112">开发 IT 安全策略</span><span class="sxs-lookup"><span data-stu-id="fa02d-112">Develop an IT security policy</span></span>  
  
-   <span data-ttu-id="fa02d-113">设计和实现的防御策略</span><span class="sxs-lookup"><span data-stu-id="fa02d-113">Design and implement a defense strategy</span></span>  
  
-   <span data-ttu-id="fa02d-114">设计和实现服务器锁定策略</span><span class="sxs-lookup"><span data-stu-id="fa02d-114">Design and implement a server lockdown strategy</span></span>  
  
-   <span data-ttu-id="fa02d-115">设计和实现防病毒策略</span><span class="sxs-lookup"><span data-stu-id="fa02d-115">Design and implement an antivirus strategy</span></span>  
  
-   <span data-ttu-id="fa02d-116">设计和实现备份和还原策略</span><span class="sxs-lookup"><span data-stu-id="fa02d-116">Design and implement a backup and restore strategy</span></span>  
  
-   <span data-ttu-id="fa02d-117">设计和实现更新管理策略</span><span class="sxs-lookup"><span data-stu-id="fa02d-117">Design and implement an update management strategy</span></span>  
  
-   <span data-ttu-id="fa02d-118">设计和实施审核和入侵检测策略</span><span class="sxs-lookup"><span data-stu-id="fa02d-118">Design and implement an auditing and intrusion detection strategy</span></span>  
  
-   <span data-ttu-id="fa02d-119">设计事件响应计划</span><span class="sxs-lookup"><span data-stu-id="fa02d-119">Design an incident response plan</span></span>  
  
 <span data-ttu-id="fa02d-120">本主题中提供的信息不包含上面的列表中的所有信息，也不提供财务服务合规的解决方案。</span><span class="sxs-lookup"><span data-stu-id="fa02d-120">The information provided in this topic does not cover all the information in the preceding list or deliver a financial services-compliant solution.</span></span> <span data-ttu-id="fa02d-121">此主题的目的是方法的提供很好的起点，并有助于下划线使用结构化和全面进行安全的重要性。</span><span class="sxs-lookup"><span data-stu-id="fa02d-121">The purpose of this topic is to provide a good starting point and to help underscore the importance of a structured and comprehensive approach to security.</span></span>  
  
 <span data-ttu-id="fa02d-122">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="fa02d-122">This section contains:</span></span>  
  
-   [<span data-ttu-id="fa02d-123">BizTalk Server 安全功能</span><span class="sxs-lookup"><span data-stu-id="fa02d-123">BizTalk Server Security Features</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-server-security-features.md)  
  
-   [<span data-ttu-id="fa02d-124">A4SWIFT 消息修复和新提交的安全功能</span><span class="sxs-lookup"><span data-stu-id="fa02d-124">A4SWIFT Security Features for Message Repair and New Submission</span></span>](../../adapters-and-accelerators/accelerator-swift/a4swift-security-features-for-message-repair-and-new-submission.md)  
  
-   [<span data-ttu-id="fa02d-125">InfoPath 安全性</span><span class="sxs-lookup"><span data-stu-id="fa02d-125">InfoPath Security</span></span>](../../adapters-and-accelerators/accelerator-swift/infopath-security.md)  
  
-   [<span data-ttu-id="fa02d-126">服务器运行时安全性</span><span class="sxs-lookup"><span data-stu-id="fa02d-126">Server Runtime Security</span></span>](../../adapters-and-accelerators/accelerator-swift/server-runtime-security.md)  
  
-   [<span data-ttu-id="fa02d-127">Windows SharePoint Services 安全性</span><span class="sxs-lookup"><span data-stu-id="fa02d-127">Windows SharePoint Services Security</span></span>](../../adapters-and-accelerators/accelerator-swift/windows-sharepoint-services-security.md)  
  
-   [<span data-ttu-id="fa02d-128">A4SWIFT Web 服务安全性</span><span class="sxs-lookup"><span data-stu-id="fa02d-128">A4SWIFT Web Service Security</span></span>](../../adapters-and-accelerators/accelerator-swift/a4swift-web-service-security.md)  
  
-   [<span data-ttu-id="fa02d-129">安全性摘要</span><span class="sxs-lookup"><span data-stu-id="fa02d-129">Security Summary</span></span>](../../adapters-and-accelerators/accelerator-swift/security-summary.md)