---
title: 安全和隐私标准 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, privacy standards
- privacy standards
- security
- security, about security
- BizTalk Accelerator for SWIFT, security
- security, BizTalk Accelerator for SWIFT
ms.assetid: 5794b25f-8a73-4f5b-97ef-1b0f61775c4b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61daf6e28b03174af2b32a61c758a39b4cd16ff9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980598"
---
# <a name="security-and-privacy-standards"></a><span data-ttu-id="3c0fa-102">安全和隐私标准</span><span class="sxs-lookup"><span data-stu-id="3c0fa-102">Security and privacy standards</span></span>
<span data-ttu-id="3c0fa-103">使用 Microsoft 财务服务应用程序和集成解决方案开发[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]通常受本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安全功能。</span><span class="sxs-lookup"><span data-stu-id="3c0fa-103">Financial Services applications and integration solutions developed using Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] are generally secured by native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] security features.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3c0fa-104"> 使用主动的安全机制，如实际上 Internet 加密消息传送标准和传输协议，签名证书时，[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]身份验证和企业单一登录来保护[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序、 数据和运行时。</span><span class="sxs-lookup"><span data-stu-id="3c0fa-104"> uses aggressive security mechanisms such as de facto Internet encrypted messaging standards and transport protocols, signing certificates, [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Authentication, and Enterprise Single Sign-On to secure [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, data, and runtime.</span></span>  

 <span data-ttu-id="3c0fa-105">构建与 Microsoft 的解决方案[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]2000， [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，和 A4SWIFT 可以帮助你使其满足安全和隐私准则的社会全球 Interbank 金融电信 (SWIFT) 金融交易。</span><span class="sxs-lookup"><span data-stu-id="3c0fa-105">Solutions built with Microsoft [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] 2000, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], and A4SWIFT can help you to meet the security and privacy guidelines for Society for Worldwide Interbank Financial Telecommunication (SWIFT) financial transactions.</span></span>  

 <span data-ttu-id="3c0fa-106">除了本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安全功能，A4SWIFT 提供保护最终用户消息项、 修复、 批准和 SWIFT 消息提交到特定的用户级安全。</span><span class="sxs-lookup"><span data-stu-id="3c0fa-106">In addition to native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] security features, A4SWIFT provides user-level security specific to securing end-user message entry, repair, approval, and submission of SWIFT messages.</span></span> <span data-ttu-id="3c0fa-107">通过使用此安全[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]数字签名技术和通过使用 A4SWIFT 运行时服务来验证证书和数据完整性。</span><span class="sxs-lookup"><span data-stu-id="3c0fa-107">This security is achieved by using [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] digital signing technologies and by using A4SWIFT runtime services to verify certificate and data integrity.</span></span>  

 <span data-ttu-id="3c0fa-108">务必要考虑保护 SWIFT 消息和它们包含时输入或编辑由最终用户，在传输过程，以及在时的信息的度量值[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]处理，并将其存储。</span><span class="sxs-lookup"><span data-stu-id="3c0fa-108">It is important to consider measures for securing your SWIFT messages and the information they contain when they are entered or edited by end-users, in transit, and while [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] processes and stores them.</span></span>  

 <span data-ttu-id="3c0fa-109">在一起，BizTalk Server 和 A4SWIFT 提供的平台、 基础结构和工具设计、 开发和执行安全 SWIFT 消息传送和工作流自动化系统。</span><span class="sxs-lookup"><span data-stu-id="3c0fa-109">Together, BizTalk Server and A4SWIFT provide the platform, infrastructure, and tools for designing, developing, and executing secure SWIFT messaging and workflow automation systems.</span></span>  

 <span data-ttu-id="3c0fa-110">在实施安全机制，必须设计和开发多个区域。</span><span class="sxs-lookup"><span data-stu-id="3c0fa-110">When implementing security, you must design and develop many areas.</span></span> <span data-ttu-id="3c0fa-111">以下列表是这些领域的高级视图：</span><span class="sxs-lookup"><span data-stu-id="3c0fa-111">The following list is a high-level view of these areas:</span></span>  

- <span data-ttu-id="3c0fa-112">开发 IT 安全策略</span><span class="sxs-lookup"><span data-stu-id="3c0fa-112">Develop an IT security policy</span></span>  

- <span data-ttu-id="3c0fa-113">设计和实现的防御策略</span><span class="sxs-lookup"><span data-stu-id="3c0fa-113">Design and implement a defense strategy</span></span>  

- <span data-ttu-id="3c0fa-114">设计和实现服务器锁定策略</span><span class="sxs-lookup"><span data-stu-id="3c0fa-114">Design and implement a server lockdown strategy</span></span>  

- <span data-ttu-id="3c0fa-115">设计和实施防病毒策略</span><span class="sxs-lookup"><span data-stu-id="3c0fa-115">Design and implement an antivirus strategy</span></span>  

- <span data-ttu-id="3c0fa-116">设计和实现备份和还原策略</span><span class="sxs-lookup"><span data-stu-id="3c0fa-116">Design and implement a backup and restore strategy</span></span>  

- <span data-ttu-id="3c0fa-117">设计和实现更新管理策略</span><span class="sxs-lookup"><span data-stu-id="3c0fa-117">Design and implement an update management strategy</span></span>  

- <span data-ttu-id="3c0fa-118">设计和实施审核和入侵检测策略</span><span class="sxs-lookup"><span data-stu-id="3c0fa-118">Design and implement an auditing and intrusion detection strategy</span></span>  

- <span data-ttu-id="3c0fa-119">设计事件响应计划</span><span class="sxs-lookup"><span data-stu-id="3c0fa-119">Design an incident response plan</span></span>  

  <span data-ttu-id="3c0fa-120">本主题中提供的信息不包含上述列表中的所有信息，也不提供财务服务兼容的解决方案。</span><span class="sxs-lookup"><span data-stu-id="3c0fa-120">The information provided in this topic does not cover all the information in the preceding list or deliver a financial services-compliant solution.</span></span> <span data-ttu-id="3c0fa-121">本主题的目的是提供很好的起点并帮助下划线安全的结构化和全面方法的重要性。</span><span class="sxs-lookup"><span data-stu-id="3c0fa-121">The purpose of this topic is to provide a good starting point and to help underscore the importance of a structured and comprehensive approach to security.</span></span>  

  <span data-ttu-id="3c0fa-122">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="3c0fa-122">This section contains:</span></span>  

- [<span data-ttu-id="3c0fa-123">BizTalk Server 安全功能</span><span class="sxs-lookup"><span data-stu-id="3c0fa-123">BizTalk Server Security Features</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-server-security-features.md)  

- [<span data-ttu-id="3c0fa-124">消息修复和新提交的 A4SWIFT 安全功能</span><span class="sxs-lookup"><span data-stu-id="3c0fa-124">A4SWIFT Security Features for Message Repair and New Submission</span></span>](../../adapters-and-accelerators/accelerator-swift/a4swift-security-features-for-message-repair-and-new-submission.md)  

- [<span data-ttu-id="3c0fa-125">InfoPath 安全性</span><span class="sxs-lookup"><span data-stu-id="3c0fa-125">InfoPath Security</span></span>](../../adapters-and-accelerators/accelerator-swift/infopath-security.md)  

- [<span data-ttu-id="3c0fa-126">服务器运行时安全性</span><span class="sxs-lookup"><span data-stu-id="3c0fa-126">Server Runtime Security</span></span>](../../adapters-and-accelerators/accelerator-swift/server-runtime-security.md)  

- [<span data-ttu-id="3c0fa-127">Windows SharePoint Services 安全性</span><span class="sxs-lookup"><span data-stu-id="3c0fa-127">Windows SharePoint Services Security</span></span>](../../adapters-and-accelerators/accelerator-swift/windows-sharepoint-services-security.md)  

- [<span data-ttu-id="3c0fa-128">A4SWIFT Web 服务安全性</span><span class="sxs-lookup"><span data-stu-id="3c0fa-128">A4SWIFT Web Service Security</span></span>](../../adapters-and-accelerators/accelerator-swift/a4swift-web-service-security.md)  

- [<span data-ttu-id="3c0fa-129">安全性摘要</span><span class="sxs-lookup"><span data-stu-id="3c0fa-129">Security Summary</span></span>](../../adapters-and-accelerators/accelerator-swift/security-summary.md)
