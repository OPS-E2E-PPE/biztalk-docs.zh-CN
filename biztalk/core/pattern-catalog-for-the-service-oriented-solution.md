---
title: 面向服务的模式目录解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Calling Pipelines from Code pattern [service solutions]
- Recipient List pattern [service solutions]
- filters, design patterns
- Filter pattern [service solutions]
- caching, patterns [service solutions]
- Service Interface pattern [service solutions]
- Content-Based Routing pattern [service solutions]
- Inline Invocation of Back-End Processes pattern [service solutions]
- content-based routing, patterns [service solutions]
- messages, Translator pattern [service solutions]
- aggregations, patterns [service solutions]
- Translator pattern, service solutions
- Caching pattern [service solutions]
- Aggregation pattern [service solutions]
- patterns [service solutions], pattern types
- back-end processes
- services, interface pattern [service solutions]
ms.assetid: 5d8135c5-d5de-4e61-b3e8-2aa7f6de98c8
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e014520057a47145daeeb0ee2a1e03a4f88e1af6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291882"
---
# <a name="pattern-catalog-for-the-service-oriented-solution"></a><span data-ttu-id="7b142-102">面向服务的模式目录的解决方案</span><span class="sxs-lookup"><span data-stu-id="7b142-102">Pattern Catalog for the Service Oriented Solution</span></span>
<span data-ttu-id="7b142-103">面向服务的解决方案中的模式包括前面部分中的特定于 BizTalk Server 的编程做法模式以及企业集成模式。</span><span class="sxs-lookup"><span data-stu-id="7b142-103">The patterns in the service oriented solution include patterns of BizTalk Server-specific programming practices, as well as the enterprise integration patterns in preceding sections.</span></span> <span data-ttu-id="7b142-104">本部分中的列表包括这两种类型的模式。</span><span class="sxs-lookup"><span data-stu-id="7b142-104">The list in this section includes both kinds of patterns.</span></span>  
  
## <a name="pattern-types"></a><span data-ttu-id="7b142-105">模式类型</span><span class="sxs-lookup"><span data-stu-id="7b142-105">Pattern Types</span></span>  
 <span data-ttu-id="7b142-106">简要介绍以下主题中的条目来描述模式，并指向说明该解决方案如何使用此模式的其他主题。</span><span class="sxs-lookup"><span data-stu-id="7b142-106">Entries described in the following topics briefly describe the pattern and point to other topics that describe how the solution uses the pattern.</span></span> <span data-ttu-id="7b142-107">在常规模式，例如筛选器的情况下条目指向更多常规主题。</span><span class="sxs-lookup"><span data-stu-id="7b142-107">In the case of general patterns, such as a filter, entries point to more general topics.</span></span>  
  
### <a name="aggregation-pattern"></a><span data-ttu-id="7b142-108">聚合模式</span><span class="sxs-lookup"><span data-stu-id="7b142-108">Aggregation Pattern</span></span>  
 <span data-ttu-id="7b142-109">聚合是从多个源接收的信息，并且合并为单个消息的模式。</span><span class="sxs-lookup"><span data-stu-id="7b142-109">Aggregation is the pattern of receiving information from multiple sources and consolidating it into a single message.</span></span> <span data-ttu-id="7b142-110">面向服务的解决方案将组合到单个响应的信用额度信息来自三个不同的源。</span><span class="sxs-lookup"><span data-stu-id="7b142-110">The service oriented solution combines credit information from three different sources into a single response.</span></span> <span data-ttu-id="7b142-111">你可以执行聚合多个不同的方式，具体取决于您正在编写的解决方案的特性。</span><span class="sxs-lookup"><span data-stu-id="7b142-111">You can do aggregation several different ways, depending on the nature of the solution you're writing.</span></span> <span data-ttu-id="7b142-112">在某些情况下，可能需要等待所有响应。</span><span class="sxs-lookup"><span data-stu-id="7b142-112">In some cases, you may need to wait for all responses.</span></span> <span data-ttu-id="7b142-113">在其他情况下，例如在申请贷款时，您可能不会放弃获得响应，因此只要有一些最小数目。</span><span class="sxs-lookup"><span data-stu-id="7b142-113">In other cases, such as in loan quotes, you may be willing to forego getting a response so long as you have some minimum number.</span></span> <span data-ttu-id="7b142-114">面向服务的解决方案等待，直到它具有所有三个响应，因为它需要所有这三个以便具有返回的完整信用报告。</span><span class="sxs-lookup"><span data-stu-id="7b142-114">The service oriented solution waits until it has all three responses because it requires all three in order to have a complete credit report to return.</span></span> <span data-ttu-id="7b142-115">有关详细信息，请参阅[转换的面向服务的解决方案模式](../core/translating-the-patterns-of-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="7b142-115">For more information, see [Translating the Patterns of the Service Oriented Solution](../core/translating-the-patterns-of-the-service-oriented-solution.md).</span></span>  
  
### <a name="calling-pipelines-from-code-pattern"></a><span data-ttu-id="7b142-116">通过代码模式调用管道</span><span class="sxs-lookup"><span data-stu-id="7b142-116">Calling Pipelines from Code Pattern</span></span>  
 <span data-ttu-id="7b142-117">现在可以从您的代码和业务流程调用管道。</span><span class="sxs-lookup"><span data-stu-id="7b142-117">You can now call pipelines from your code and orchestrations.</span></span> <span data-ttu-id="7b142-118">这允许重复使用的管道，并有助于保持业务流程与管道阶段的分离。</span><span class="sxs-lookup"><span data-stu-id="7b142-118">This allows the re-use of pipelines and helps maintain the decoupling of an orchestration from the pipeline stages.</span></span> <span data-ttu-id="7b142-119">有关详细信息，请参阅[从面向服务的解决方案使用管道](../core/using-pipelines-from-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="7b142-119">For more information, see [Using Pipelines from the Service Oriented Solution](../core/using-pipelines-from-the-service-oriented-solution.md).</span></span>  
  
### <a name="caching-pattern"></a><span data-ttu-id="7b142-120">缓存模式</span><span class="sxs-lookup"><span data-stu-id="7b142-120">Caching Pattern</span></span>  
 <span data-ttu-id="7b142-121">缓存是存储信息而不必每次请求时从数据存储区检索的常规策略。</span><span class="sxs-lookup"><span data-stu-id="7b142-121">Caching is a general strategy of storing information rather than retrieving it from a data store every time it is requested.</span></span> <span data-ttu-id="7b142-122">从企业单一登录系统中检索引用或配置数据被证明是解决方案中的限制因素。</span><span class="sxs-lookup"><span data-stu-id="7b142-122">Retrieving reference or configuration data from the Enterprise Single Sign-On system proved to be a limiting factor in the solution.</span></span> <span data-ttu-id="7b142-123">该解决方案将缓存的信息，并定期刷新缓存。</span><span class="sxs-lookup"><span data-stu-id="7b142-123">The solution caches the information and periodically refreshes the cache.</span></span> <span data-ttu-id="7b142-124">有关详细信息，请参阅[面向服务的解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="7b142-124">For more information, see [Using SSO Efficiently in the Service Oriented Solution](../core/using-sso-efficiently-in-the-service-oriented-solution.md).</span></span> <span data-ttu-id="7b142-125">业务流程管理解决方案也缓存 SSO 信息，但它使用过程略有不同。</span><span class="sxs-lookup"><span data-stu-id="7b142-125">The Business Process Management solution also caches the SSO information, though it uses a slightly different process.</span></span> <span data-ttu-id="7b142-126">有关详细信息，请参阅[业务流程管理解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="7b142-126">For more information, see [Using SSO Efficiently in the Business Process Management Solution](../core/using-sso-efficiently-in-the-business-process-management-solution.md).</span></span>  
  
### <a name="content-based-routing-pattern"></a><span data-ttu-id="7b142-127">基于内容的路由模式</span><span class="sxs-lookup"><span data-stu-id="7b142-127">Content-Based Routing Pattern</span></span>  
 <span data-ttu-id="7b142-128">在企业集成模式，基于内容的路由是 BizTalk 比更为广泛地考虑。</span><span class="sxs-lookup"><span data-stu-id="7b142-128">In enterprise integration patterns, content-based routing is more broadly conceived than in BizTalk.</span></span> <span data-ttu-id="7b142-129">在企业集成模式中，基于内容的路由确定基于消息的内容的某些部分消息的收件人。</span><span class="sxs-lookup"><span data-stu-id="7b142-129">In enterprise integration patterns, content-based routing is determining the recipient of a message based on the some part of the content of the message.</span></span> <span data-ttu-id="7b142-130">面向服务的解决方案使用非常简单的基于内容的路由形式 — 在业务流程中的单个决策形状将发送的消息的两个位置之一。</span><span class="sxs-lookup"><span data-stu-id="7b142-130">The service oriented solution uses a very simple form of content-based routing—a single decision shape in an orchestration sends the message one of two places.</span></span> <span data-ttu-id="7b142-131">有关详细信息，请参阅"将转换组件到业务流程形状"中[转换的面向服务的解决方案模式](../core/translating-the-patterns-of-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="7b142-131">For more information, see "Translating the Components into Orchestration Shapes" in [Translating the Patterns of the Service Oriented Solution](../core/translating-the-patterns-of-the-service-oriented-solution.md).</span></span>  
  
### <a name="filter-pattern"></a><span data-ttu-id="7b142-132">筛选器模式</span><span class="sxs-lookup"><span data-stu-id="7b142-132">Filter Pattern</span></span>  
 <span data-ttu-id="7b142-133">筛选器模式可以选择符合特定处理条件的消息。</span><span class="sxs-lookup"><span data-stu-id="7b142-133">The filter pattern selects messages meeting particular criteria for processing.</span></span> <span data-ttu-id="7b142-134">在 BizTalk Server 中，筛选模式几乎总是会变为端口上的筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="7b142-134">In BizTalk Server, the filter pattern almost always becomes a filter expression on a port.</span></span> <span data-ttu-id="7b142-135">有关端口的筛选器的详细信息，请参阅[使用筛选器与接收消息形状](../core/using-filters-with-the-receive-message-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="7b142-135">For more information about filters on ports, see [Using Filters With the Receive Message Shape](../core/using-filters-with-the-receive-message-shape.md).</span></span>  
  
### <a name="inline-invocation-of-back-end-processes-pattern"></a><span data-ttu-id="7b142-136">后端进程模式的内联调用</span><span class="sxs-lookup"><span data-stu-id="7b142-136">Inline Invocation of Back-end Processes Pattern</span></span>  
 <span data-ttu-id="7b142-137">该解决方案的内联版本使用通过自定义程序集的后端进程的内联调用。</span><span class="sxs-lookup"><span data-stu-id="7b142-137">The inline version of the solution uses inline invocation of the back-end processes through custom assemblies.</span></span> <span data-ttu-id="7b142-138">这样做的好处的极大地提高性能。</span><span class="sxs-lookup"><span data-stu-id="7b142-138">This has the benefit of greatly improved performance.</span></span> <span data-ttu-id="7b142-139">它需要付出一定代价，但是的紧密连接的传输协议的业务流程。</span><span class="sxs-lookup"><span data-stu-id="7b142-139">It comes at the cost, however, of tightly coupling the orchestration to the transport protocol.</span></span> <span data-ttu-id="7b142-140">有关详细信息，请参阅[内联后端调用](../core/inlining-back-end-invocation.md)。</span><span class="sxs-lookup"><span data-stu-id="7b142-140">For more information, see [Inlining Back-end Invocation](../core/inlining-back-end-invocation.md).</span></span>  
  
### <a name="recipient-list-pattern"></a><span data-ttu-id="7b142-141">收件人列表模式</span><span class="sxs-lookup"><span data-stu-id="7b142-141">Recipient List Pattern</span></span>  
 <span data-ttu-id="7b142-142">在抽象意义上，面向服务的解决方案，它将消息发送到三个不同的系统实现收件人列表。</span><span class="sxs-lookup"><span data-stu-id="7b142-142">In an abstract sense, the service oriented solution implements a recipient list in that it sends messages to three different systems.</span></span> <span data-ttu-id="7b142-143">实际上，部署的应用程序通过将逻辑端口映射到特定位置来确定收件人。</span><span class="sxs-lookup"><span data-stu-id="7b142-143">In practical terms, the deployed application determines the recipients by mapping the logical ports to specific locations.</span></span> <span data-ttu-id="7b142-144">对于内联版本的应用程序，通过 SSO 中的配置信息进行连接。</span><span class="sxs-lookup"><span data-stu-id="7b142-144">In the case of the inline version of the application, the connections are made through the configuration information in SSO.</span></span> <span data-ttu-id="7b142-145">有关详细信息，请参阅[转换的面向服务的解决方案模式](../core/translating-the-patterns-of-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="7b142-145">For more information, see [Translating the Patterns of the Service Oriented Solution](../core/translating-the-patterns-of-the-service-oriented-solution.md).</span></span>  
  
### <a name="service-interface-pattern"></a><span data-ttu-id="7b142-146">服务接口模式</span><span class="sxs-lookup"><span data-stu-id="7b142-146">Service Interface Pattern</span></span>  
 <span data-ttu-id="7b142-147">面向服务的解决方案自身都表示为 Web 服务，实现服务的多种方式之一。</span><span class="sxs-lookup"><span data-stu-id="7b142-147">The service oriented solution presents itself as a Web service, only one of many ways a service may be done.</span></span> <span data-ttu-id="7b142-148">有关使用业务流程作为 Web 服务的详细信息，请参阅[使用 Web 服务的](../core/using-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="7b142-148">For more information about using orchestrations as Web services, see [Using Web Services](../core/using-web-services.md).</span></span>  
  
### <a name="translator-pattern"></a><span data-ttu-id="7b142-149">转换器模式</span><span class="sxs-lookup"><span data-stu-id="7b142-149">Translator Pattern</span></span>  
 <span data-ttu-id="7b142-150">转换器的企业模式 — 即的一条消息从一个格式转换为另一种形式 — 经常翻译为 BizTalk Server 映射。</span><span class="sxs-lookup"><span data-stu-id="7b142-150">The enterprise pattern of a translator—that is, the conversion of a message from one form to another form—most often translates into a BizTalk Server map.</span></span> <span data-ttu-id="7b142-151">有关 BizTalk Server 映射的常规信息，请参阅[创建映射使用 BizTalk 映射器](../core/creating-maps-using-biztalk-mapper.md)。</span><span class="sxs-lookup"><span data-stu-id="7b142-151">For general information about BizTalk Server maps, see [Creating Maps Using BizTalk Mapper](../core/creating-maps-using-biztalk-mapper.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b142-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b142-152">See Also</span></span>  
 [<span data-ttu-id="7b142-153">面向服务的解决方案中的模式</span><span class="sxs-lookup"><span data-stu-id="7b142-153">Patterns in the Service Oriented Solution</span></span>](../core/patterns-in-the-service-oriented-solution.md)