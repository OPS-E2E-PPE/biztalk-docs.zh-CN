---
title: "使用 Web 服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services
- Web services, about Web services
- orchestrations, Web services
- Web services, orchestrations
ms.assetid: a54261e3-d8ef-4770-8d9a-147685846051
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 236acb42c010effe5c3d45cde1daaf9a7097ede5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-web-services"></a><span data-ttu-id="73ba2-102">使用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="73ba2-102">Using Web Services</span></span>
<span data-ttu-id="73ba2-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为 Web 服务提供内置支持。</span><span class="sxs-lookup"><span data-stu-id="73ba2-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides built-in support for Web services.</span></span> <span data-ttu-id="73ba2-104">BizTalk Server 支持所有现有 Web Services 在业务流程中的重用和聚合。</span><span class="sxs-lookup"><span data-stu-id="73ba2-104">BizTalk Server enables the reuse and aggregation of all your existing Web services within your orchestrations.</span></span> <span data-ttu-id="73ba2-105">你还可以将业务流程发布（公开）为 Web Services，以将 Web Services 逻辑与业务流程逻辑分开。</span><span class="sxs-lookup"><span data-stu-id="73ba2-105">You can also publish (expose) your orchestrations as Web services to separate the Web service logic from the business process logic.</span></span>  
  
 <span data-ttu-id="73ba2-106">BizTalk Server 实现了对 Web Services 中的本机适配器的支持。</span><span class="sxs-lookup"><span data-stu-id="73ba2-106">BizTalk Server implements support for native adapters in Web services.</span></span> <span data-ttu-id="73ba2-107">本机适配器支持为 Web Services 提供了可伸缩性、容错功能和跟踪功能，且无需为此编写代码。</span><span class="sxs-lookup"><span data-stu-id="73ba2-107">Native adapter support provides scalability, fault tolerance, and tracking capabilities for Web services without writing a single line of code.</span></span> <span data-ttu-id="73ba2-108">有关 SOAP 适配器的信息，请参阅[SOAP 适配器](../core/soap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="73ba2-108">For information about the SOAP adapter, see [SOAP Adapter](../core/soap-adapter.md).</span></span>  
  
 <span data-ttu-id="73ba2-109">BizTalk Server 中的 Web 服务支持划分为两个类别： 使用或调用 Web 服务和发布或创建 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="73ba2-109">The Web services support in BizTalk Server falls into two categories: consuming or calling Web services and publishing or creating Web services.</span></span>  
  
 <span data-ttu-id="73ba2-110">使用或发布 Web 服务之前，你应会在 ASP.NET 中的 XML Web 服务的了解。</span><span class="sxs-lookup"><span data-stu-id="73ba2-110">Before you consume or publish a Web service, you should have an understanding of XML Web services in ASP.NET.</span></span> <span data-ttu-id="73ba2-111">XML Web 服务的基础知识的信息，请参阅文章"XML Web Services 基础知识"在[http://go.microsoft.com/fwlink/?LinkId=193057](http://go.microsoft.com/fwlink/?LinkId=193057)。</span><span class="sxs-lookup"><span data-stu-id="73ba2-111">For information about the basics of XML Web services, see the article "XML Web Services Basics" at [http://go.microsoft.com/fwlink/?LinkId=193057](http://go.microsoft.com/fwlink/?LinkId=193057).</span></span>  
  
 <span data-ttu-id="73ba2-112">**使用 Web 服务**</span><span class="sxs-lookup"><span data-stu-id="73ba2-112">**Consuming Web services**</span></span>  
  
 <span data-ttu-id="73ba2-113">可以从业务流程中使用（调用）Web Services。</span><span class="sxs-lookup"><span data-stu-id="73ba2-113">You can consume (call) Web services from within an orchestration.</span></span> <span data-ttu-id="73ba2-114">可以将若干 Web Services 聚合成单个业务流程以完成整个业务流程。</span><span class="sxs-lookup"><span data-stu-id="73ba2-114">You can aggregate several Web services into single orchestration to complete an entire business process.</span></span>  
  
 <span data-ttu-id="73ba2-115">**发布 Web 服务**</span><span class="sxs-lookup"><span data-stu-id="73ba2-115">**Publishing Web services**</span></span>  
  
 <span data-ttu-id="73ba2-116">可以使用 Web Services 发布向导发布 Web Services。</span><span class="sxs-lookup"><span data-stu-id="73ba2-116">You can publish Web services using the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="73ba2-117">业务流程和发送适配器可以使用这些已发布 Web Services。</span><span class="sxs-lookup"><span data-stu-id="73ba2-117">Orchestrations and send adapters can use these published Web services.</span></span>  
  
 <span data-ttu-id="73ba2-118">**使用 SOAP 标头**</span><span class="sxs-lookup"><span data-stu-id="73ba2-118">**Using SOAP headers**</span></span>  
  
 <span data-ttu-id="73ba2-119">BizTalk Server 支持已定义的和未知的 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="73ba2-119">BizTalk Server provides support for defined and unknown SOAP headers.</span></span> <span data-ttu-id="73ba2-120">BizTalk Server 为 Web Services 中的每个已定义的 SOAP 标头创建一个上下文属性。</span><span class="sxs-lookup"><span data-stu-id="73ba2-120">BizTalk Server creates a context property for each defined SOAP header in the Web service.</span></span>  
  
 <span data-ttu-id="73ba2-121">**Web 服务标准**</span><span class="sxs-lookup"><span data-stu-id="73ba2-121">**Web Services standards**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="73ba2-122"> 应使用任何 Web Services 标准发送和接收。</span><span class="sxs-lookup"><span data-stu-id="73ba2-122"> should work with any Web Services standards when sending and receiving.</span></span> <span data-ttu-id="73ba2-123">并非所有的标准都进行了测试。</span><span class="sxs-lookup"><span data-stu-id="73ba2-123">Not all standards have been tested.</span></span> <span data-ttu-id="73ba2-124">通常情况下，WCF 支持的标准也受 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 支持。</span><span class="sxs-lookup"><span data-stu-id="73ba2-124">Typically, the standards supported by WCF are also supported by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="73ba2-125">示例标准包括：</span><span class="sxs-lookup"><span data-stu-id="73ba2-125">Sample standards include:</span></span>  
  
-   <span data-ttu-id="73ba2-126">WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="73ba2-126">WS-ReliableMessaging</span></span>  
  
-   <span data-ttu-id="73ba2-127">WS-安全性</span><span class="sxs-lookup"><span data-stu-id="73ba2-127">WS-Security</span></span>  
  
-   <span data-ttu-id="73ba2-128">WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="73ba2-128">WS-SecureConversation</span></span>  
  
-   <span data-ttu-id="73ba2-129">WS-Trust</span><span class="sxs-lookup"><span data-stu-id="73ba2-129">WS-Trust</span></span>  
  
-   <span data-ttu-id="73ba2-130">WS 联合身份验证</span><span class="sxs-lookup"><span data-stu-id="73ba2-130">WS-Federation</span></span>  
  
-   <span data-ttu-id="73ba2-131">WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="73ba2-131">WS-Addressing</span></span>  
  
-   <span data-ttu-id="73ba2-132">WS-Policy</span><span class="sxs-lookup"><span data-stu-id="73ba2-132">WS-Policy</span></span>  
  
-   <span data-ttu-id="73ba2-133">WS-MetadataExchange</span><span class="sxs-lookup"><span data-stu-id="73ba2-133">WS-MetadataExchange</span></span>  
  
-   <span data-ttu-id="73ba2-134">WS-Coordination</span><span class="sxs-lookup"><span data-stu-id="73ba2-134">WS-Coordination</span></span>  
  
-   <span data-ttu-id="73ba2-135">WS-Atomic</span><span class="sxs-lookup"><span data-stu-id="73ba2-135">WS-Atomic</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="73ba2-136">本节内容</span><span class="sxs-lookup"><span data-stu-id="73ba2-136">In This Section</span></span>  
  
-   [<span data-ttu-id="73ba2-137">使用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="73ba2-137">Consuming Web Services</span></span>](../core/consuming-web-services.md)  
  
-   [<span data-ttu-id="73ba2-138">发布 Web 服务</span><span class="sxs-lookup"><span data-stu-id="73ba2-138">Publishing Web Services</span></span>](../core/publishing-web-services.md)  
  
-   [<span data-ttu-id="73ba2-139">使用 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="73ba2-139">Using SOAP Headers</span></span>](../core/using-soap-headers.md)