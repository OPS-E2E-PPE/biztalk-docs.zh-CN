---
title: 使用 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services
- Web services, about Web services
- orchestrations, Web services
- Web services, orchestrations
ms.assetid: a54261e3-d8ef-4770-8d9a-147685846051
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24af6961e888f8cda21e8d280451382160e2b5af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262119"
---
# <a name="using-web-services"></a><span data-ttu-id="50928-102">使用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="50928-102">Using Web Services</span></span>
<span data-ttu-id="50928-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为 Web services 提供内置支持。</span><span class="sxs-lookup"><span data-stu-id="50928-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides built-in support for Web services.</span></span> <span data-ttu-id="50928-104">BizTalk Server，可以重用和聚合业务流程中的所有现有 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="50928-104">BizTalk Server enables the reuse and aggregation of all your existing Web services within your orchestrations.</span></span> <span data-ttu-id="50928-105">你还可以发布 （公开） 您的业务流程作为 Web 服务以单独的 Web 服务逻辑与业务流程逻辑。</span><span class="sxs-lookup"><span data-stu-id="50928-105">You can also publish (expose) your orchestrations as Web services to separate the Web service logic from the business process logic.</span></span>  
  
 <span data-ttu-id="50928-106">BizTalk Server 实现 Web 服务中的本地适配器的支持。</span><span class="sxs-lookup"><span data-stu-id="50928-106">BizTalk Server implements support for native adapters in Web services.</span></span> <span data-ttu-id="50928-107">本机适配器支持提供了可伸缩性、 容错能力和跟踪功能的 Web 服务，而无需编写一行代码。</span><span class="sxs-lookup"><span data-stu-id="50928-107">Native adapter support provides scalability, fault tolerance, and tracking capabilities for Web services without writing a single line of code.</span></span> <span data-ttu-id="50928-108">有关 SOAP 适配器的信息，请参阅[SOAP 适配器](../core/soap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="50928-108">For information about the SOAP adapter, see [SOAP Adapter](../core/soap-adapter.md).</span></span>  
  
 <span data-ttu-id="50928-109">在 BizTalk Server 中的 Web services 支持分为两类： 使用或调用 Web 服务以及发布或创建 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="50928-109">The Web services support in BizTalk Server falls into two categories: consuming or calling Web services and publishing or creating Web services.</span></span>  
  
 <span data-ttu-id="50928-110">在使用或发布 Web 服务之前，您应该了解 XML Web services 的 ASP.NET 中。</span><span class="sxs-lookup"><span data-stu-id="50928-110">Before you consume or publish a Web service, you should have an understanding of XML Web services in ASP.NET.</span></span> <span data-ttu-id="50928-111">有关 XML Web services 的基础知识，请参阅文章"XML Web Services 基础"网址[ http://go.microsoft.com/fwlink/?LinkId=193057 ](http://go.microsoft.com/fwlink/?LinkId=193057)。</span><span class="sxs-lookup"><span data-stu-id="50928-111">For information about the basics of XML Web services, see the article "XML Web Services Basics" at [http://go.microsoft.com/fwlink/?LinkId=193057](http://go.microsoft.com/fwlink/?LinkId=193057).</span></span>  
  
 <span data-ttu-id="50928-112">**使用 Web 服务**</span><span class="sxs-lookup"><span data-stu-id="50928-112">**Consuming Web services**</span></span>  
  
 <span data-ttu-id="50928-113">您可以使用 （调用） Web 服务从业务流程中。</span><span class="sxs-lookup"><span data-stu-id="50928-113">You can consume (call) Web services from within an orchestration.</span></span> <span data-ttu-id="50928-114">可以将若干 Web services 聚合成单个业务流程以完成整个业务流程。</span><span class="sxs-lookup"><span data-stu-id="50928-114">You can aggregate several Web services into single orchestration to complete an entire business process.</span></span>  
  
 <span data-ttu-id="50928-115">**发布 Web services**</span><span class="sxs-lookup"><span data-stu-id="50928-115">**Publishing Web services**</span></span>  
  
 <span data-ttu-id="50928-116">你可以发布 Web 服务使用 BizTalk Web Services 发布向导。</span><span class="sxs-lookup"><span data-stu-id="50928-116">You can publish Web services using the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="50928-117">业务流程和发送适配器可以使用这些已发布的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="50928-117">Orchestrations and send adapters can use these published Web services.</span></span>  
  
 <span data-ttu-id="50928-118">**使用 SOAP 标头**</span><span class="sxs-lookup"><span data-stu-id="50928-118">**Using SOAP headers**</span></span>  
  
 <span data-ttu-id="50928-119">BizTalk Server 定义的和未知的 SOAP 标头提供支持。</span><span class="sxs-lookup"><span data-stu-id="50928-119">BizTalk Server provides support for defined and unknown SOAP headers.</span></span> <span data-ttu-id="50928-120">BizTalk Server Web 服务中创建每个定义的 SOAP 标头上下文属性。</span><span class="sxs-lookup"><span data-stu-id="50928-120">BizTalk Server creates a context property for each defined SOAP header in the Web service.</span></span>  
  
 <span data-ttu-id="50928-121">**Web 服务标准**</span><span class="sxs-lookup"><span data-stu-id="50928-121">**Web Services standards**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="50928-122">应适用于任何 Web Services 标准发送和接收时。</span><span class="sxs-lookup"><span data-stu-id="50928-122">should work with any Web Services standards when sending and receiving.</span></span> <span data-ttu-id="50928-123">并非所有的标准进行了测试。</span><span class="sxs-lookup"><span data-stu-id="50928-123">Not all standards have been tested.</span></span> <span data-ttu-id="50928-124">通常情况下，WCF 支持的标准也受[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="50928-124">Typically, the standards supported by WCF are also supported by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="50928-125">示例标准包括：</span><span class="sxs-lookup"><span data-stu-id="50928-125">Sample standards include:</span></span>  
  
-   <span data-ttu-id="50928-126">WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="50928-126">WS-ReliableMessaging</span></span>  
  
-   <span data-ttu-id="50928-127">WS-Security</span><span class="sxs-lookup"><span data-stu-id="50928-127">WS-Security</span></span>  
  
-   <span data-ttu-id="50928-128">WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="50928-128">WS-SecureConversation</span></span>  
  
-   <span data-ttu-id="50928-129">WS-Trust</span><span class="sxs-lookup"><span data-stu-id="50928-129">WS-Trust</span></span>  
  
-   <span data-ttu-id="50928-130">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="50928-130">WS-Federation</span></span>  
  
-   <span data-ttu-id="50928-131">WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="50928-131">WS-Addressing</span></span>  
  
-   <span data-ttu-id="50928-132">WS-Policy</span><span class="sxs-lookup"><span data-stu-id="50928-132">WS-Policy</span></span>  
  
-   <span data-ttu-id="50928-133">WS-MetadataExchange</span><span class="sxs-lookup"><span data-stu-id="50928-133">WS-MetadataExchange</span></span>  
  
-   <span data-ttu-id="50928-134">WS-Coordination</span><span class="sxs-lookup"><span data-stu-id="50928-134">WS-Coordination</span></span>  
  
-   <span data-ttu-id="50928-135">WS-Atomic</span><span class="sxs-lookup"><span data-stu-id="50928-135">WS-Atomic</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="50928-136">本节内容</span><span class="sxs-lookup"><span data-stu-id="50928-136">In This Section</span></span>  
  
-   [<span data-ttu-id="50928-137">使用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="50928-137">Consuming Web Services</span></span>](../core/consuming-web-services.md)  
  
-   [<span data-ttu-id="50928-138">发布 Web 服务</span><span class="sxs-lookup"><span data-stu-id="50928-138">Publishing Web Services</span></span>](../core/publishing-web-services.md)  
  
-   [<span data-ttu-id="50928-139">使用 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="50928-139">Using SOAP Headers</span></span>](../core/using-soap-headers.md)