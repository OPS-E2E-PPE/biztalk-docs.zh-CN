---
title: "优化业务流程性能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 437c7325-f037-451a-8dbd-f8d8c8889e20
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cbd45901afb229cf884390c2a5120deac0daa90d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-orchestration-performance"></a><span data-ttu-id="68821-102">优化业务流程性能</span><span class="sxs-lookup"><span data-stu-id="68821-102">Optimizing Orchestration Performance</span></span>
<span data-ttu-id="68821-103">本主题介绍在 BizTalk Server 解决方案中使用业务流程的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="68821-103">This topic describes best practices for using orchestrations in BizTalk Server solutions.</span></span> <span data-ttu-id="68821-104">这包括有关建议：</span><span class="sxs-lookup"><span data-stu-id="68821-104">This includes recommendations for:</span></span>  
  
-   <span data-ttu-id="68821-105">减少延迟的使用业务流程的 BizTalk Server 解决方案</span><span class="sxs-lookup"><span data-stu-id="68821-105">Reducing latency of BizTalk Server solutions that use orchestrations</span></span>  
  
    -   <span data-ttu-id="68821-106">消除消息仅模式的业务流程</span><span class="sxs-lookup"><span data-stu-id="68821-106">Eliminating orchestrations for messaging only patterns</span></span>  
  
    -   <span data-ttu-id="68821-107">利用内联发送从业务流程</span><span class="sxs-lookup"><span data-stu-id="68821-107">Utilizing inline sends from orchestrations</span></span>  
  
    -   <span data-ttu-id="68821-108">最小化业务流程持久性点</span><span class="sxs-lookup"><span data-stu-id="68821-108">Minimizing orchestration persistence points</span></span>  
  
-   <span data-ttu-id="68821-109">嵌套业务流程</span><span class="sxs-lookup"><span data-stu-id="68821-109">Nesting orchestrations</span></span>  
  
-   <span data-ttu-id="68821-110">业务流程设计模式</span><span class="sxs-lookup"><span data-stu-id="68821-110">Orchestration design patterns</span></span>  
  
-   <span data-ttu-id="68821-111">业务流程异常处理块</span><span class="sxs-lookup"><span data-stu-id="68821-111">Orchestration exception handling blocks</span></span>  
  
## <a name="recommendations-for-optimizing-orchestrations-for-low-latency-scenarios"></a><span data-ttu-id="68821-112">有关优化为低延迟方案的业务流程的建议</span><span class="sxs-lookup"><span data-stu-id="68821-112">Recommendations for optimizing orchestrations for low latency scenarios</span></span>  
 <span data-ttu-id="68821-113">可以使用以下方法以减少延迟的使用业务流程的 BizTalk Server 解决方案。</span><span class="sxs-lookup"><span data-stu-id="68821-113">The following techniques can be used to reduce latency of BizTalk Server solutions that use orchestrations.</span></span>  
  
### <a name="eliminate-orchestrations-for-messaging-only-patterns"></a><span data-ttu-id="68821-114">消除消息仅模式的业务流程</span><span class="sxs-lookup"><span data-stu-id="68821-114">Eliminate orchestrations for messaging only patterns</span></span>  
 <span data-ttu-id="68821-115">尽可能最小化使用业务流程来提高总体吞吐量并减少业务流程的延迟。</span><span class="sxs-lookup"><span data-stu-id="68821-115">When possible minimize the use of orchestrations to increase overall throughput and reduce the latency of business processes.</span></span> <span data-ttu-id="68821-116">如果存在无需运行长时间运行事务，并且没有无需调用为每个请求的多个系统，请考虑消除业务流程和转向接收和发送端口，可以减少到往返总的业务逻辑BizTalkMsgBoxDb 和减少延迟，因为数据库访问。</span><span class="sxs-lookup"><span data-stu-id="68821-116">If there is no need to run long running transactions and there is no need to invoke several systems for each request, then consider eliminating orchestrations and moving business logic to Receive and Send Ports to reduce the total amount of roundtrips to the BizTalkMsgBoxDb and decrease the latency due to database access.</span></span> <span data-ttu-id="68821-117">在这种情况下，实现自定义管道，重复使用以前已从业务流程调用的帮助程序类。</span><span class="sxs-lookup"><span data-stu-id="68821-117">In this case, implement custom pipelines and reuse helper classes that were previously invoked from orchestrations.</span></span> <span data-ttu-id="68821-118">使用仅在严格需要时的业务流程来实现的散点图和收集或保护的设计模式。</span><span class="sxs-lookup"><span data-stu-id="68821-118">Use orchestrations only when strictly needed to implement design patterns as Scatter and Gather or Convoys.</span></span> <span data-ttu-id="68821-119">有关业务流程设计模式的详细信息，请参阅主题[实现在业务流程中的设计模式](http://go.microsoft.com/fwlink/?LinkId=140042)(http://go.microsoft.com/fwlink/?LinkId=140042) BizTalk Server 文档中。</span><span class="sxs-lookup"><span data-stu-id="68821-119">For more information about Orchestration Design Patterns, see the topic [Implementing Design Patterns in Orchestrations](http://go.microsoft.com/fwlink/?LinkId=140042) (http://go.microsoft.com/fwlink/?LinkId=140042) in the BizTalk Server documentation.</span></span>  
  
### <a name="use-inline-sends-from-orchestrations-to-accommodate-low-latency-scenarios"></a><span data-ttu-id="68821-120">使用内联支持业务流程的将发送以适应较低的延迟的情况</span><span class="sxs-lookup"><span data-stu-id="68821-120">Use inline sends from orchestrations to accommodate low latency scenarios</span></span>  
 <span data-ttu-id="68821-121">只要有可能，尽量少使用的业务流程和倾向于仅用于消息传送模式来提高总体吞吐量并减少业务流程的延迟。</span><span class="sxs-lookup"><span data-stu-id="68821-121">Whenever possible, minimize the use of orchestrations and favor messaging-only patterns to increase the overall throughput and reduce the latency of the business processes.</span></span> <span data-ttu-id="68821-122">如果无需为长时间运行事务，并且没有无需业务逻辑来调用多个系统，请考虑移动的业务逻辑来接收和发送端口和消除使用业务流程。</span><span class="sxs-lookup"><span data-stu-id="68821-122">If there is no need for long-running transactions and there is no need for business logic to invoke several systems, then consider moving business logic to receive and send Ports and eliminating the use of orchestrations.</span></span> <span data-ttu-id="68821-123">可以使用自定义管道实现这种方法，该重复使用以前已从业务流程调用的帮助器类。</span><span class="sxs-lookup"><span data-stu-id="68821-123">This approach can be implemented with custom pipelines and which reuse the helper classes that were previously invoked from orchestrations.</span></span> <span data-ttu-id="68821-124">为了实现更好的性能低延迟方案，采用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="68821-124">In order to achieve better performance in low latency scenarios, adopt one of the following approaches:</span></span>  
  
-   <span data-ttu-id="68821-125">消除不必要的业务流程，并采用仅消息传送模式，以减少到 BizTalk MessageBox 数据库总之间的往返次数。</span><span class="sxs-lookup"><span data-stu-id="68821-125">Eliminate unnecessary orchestrations and adopt messaging-only patterns to reduce the total amount of roundtrips to the BizTalk MessageBox database.</span></span> <span data-ttu-id="68821-126">此方法还包含较低的延迟，因为内联发送绕过 BizTalk 消息传递引擎和关联的开销。</span><span class="sxs-lookup"><span data-stu-id="68821-126">This approach accommodates low latency because inline sends bypass the BizTalk messaging engine and the associated overhead.</span></span> <span data-ttu-id="68821-127">业务流程内联发送功能提供 BizTalk Server 2006 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="68821-127">Orchestration inline send functionality is provided with BizTalk Server 2006 and later.</span></span>  
  
-   <span data-ttu-id="68821-128">内部业务流程，消除了绑定到的物理端口的逻辑端口，并在行内使用发送在它们的位置。</span><span class="sxs-lookup"><span data-stu-id="68821-128">Inside orchestrations, eliminate logical ports bound to physical ports and use in-line sends in their place.</span></span> <span data-ttu-id="68821-129">例如，内联发送无法用于创建一个 WCF 代理类来调用下游 Web 服务或 ADO.NET 组件以访问 SQL Server 数据库的实例。</span><span class="sxs-lookup"><span data-stu-id="68821-129">For example, an inline send could be used to create an instance of a  WCF proxy class to invoke a downstream Web service or an ADO.NET component to access a SQL Server database.</span></span> <span data-ttu-id="68821-130">在下图中，当业务流程实例化在业务组件，可在内部使用 WCF 执行内联发送代理对象来直接调用下游 Web 服务：</span><span class="sxs-lookup"><span data-stu-id="68821-130">In the following diagram, an inline send is performed when the orchestration instantiates a business component, which internally makes use of a WCF  proxy object to directly invoke a downstream Web service:</span></span>  
  
     <span data-ttu-id="68821-131">![BizTalk 业务流程内联发送描述](../technical-guides/media/inlinesend.gif "InlineSend")</span><span class="sxs-lookup"><span data-stu-id="68821-131">![Depiction of BizTalk Orchestration Inline Send](../technical-guides/media/inlinesend.gif "InlineSend")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68821-132">尽管使用内联发送从业务流程将显著减少延迟，有一些限制到这种方法。</span><span class="sxs-lookup"><span data-stu-id="68821-132">Although using inline sends from orchestrations will significantly reduce latency, there are limitations to this approach.</span></span> <span data-ttu-id="68821-133">由于内联发送绕过 BizTalk 消息引擎，请使用消息传递引擎提供的以下功能不可用：</span><span class="sxs-lookup"><span data-stu-id="68821-133">Because inline sends bypass the BizTalk messaging engine, the following functionality provided with the messaging engine is not available:</span></span>  
>   
>  -   <span data-ttu-id="68821-134">事务性管道</span><span class="sxs-lookup"><span data-stu-id="68821-134">Transactional pipelines</span></span>  
> -   <span data-ttu-id="68821-135">可恢复管道</span><span class="sxs-lookup"><span data-stu-id="68821-135">Recoverable pipelines</span></span>  
> -   <span data-ttu-id="68821-136">调用 BAM 拦截器 API 的管道</span><span class="sxs-lookup"><span data-stu-id="68821-136">Pipelines that call the BAM interceptor API</span></span>  
> -   <span data-ttu-id="68821-137">BizTalk Server 适配器支持</span><span class="sxs-lookup"><span data-stu-id="68821-137">BizTalk Server adapter support</span></span>  
> -   <span data-ttu-id="68821-138">批处理</span><span class="sxs-lookup"><span data-stu-id="68821-138">Batching</span></span>  
> -   <span data-ttu-id="68821-139">重试次数</span><span class="sxs-lookup"><span data-stu-id="68821-139">Retries</span></span>  
> -   <span data-ttu-id="68821-140">相关集初始化</span><span class="sxs-lookup"><span data-stu-id="68821-140">Correlation set initialization</span></span>  
> -   <span data-ttu-id="68821-141">声明性配置</span><span class="sxs-lookup"><span data-stu-id="68821-141">Declarative configuration</span></span>  
> -   <span data-ttu-id="68821-142">辅助传输</span><span class="sxs-lookup"><span data-stu-id="68821-142">Secondary transports</span></span>  
> -   <span data-ttu-id="68821-143">跟踪</span><span class="sxs-lookup"><span data-stu-id="68821-143">Tracking</span></span>  
> -   <span data-ttu-id="68821-144">声明方式使用 BAM</span><span class="sxs-lookup"><span data-stu-id="68821-144">Declarative use of BAM</span></span>  
  
 <span data-ttu-id="68821-145">无法从内部业务流程执行的管道的类型的详细信息，请参阅主题的"限制"部分[如何使用表达式到执行管道](http://go.microsoft.com/fwlink/?LinkId=158008)(http://go.microsoft.com/fwlink/?LinkId = 158008) BizTalk Server 2010 文档中。</span><span class="sxs-lookup"><span data-stu-id="68821-145">For more information about the types of pipelines that cannot be executed from within an orchestration, see the “Restrictions” section of the topic [How to Use Expressions to Execute Pipelines](http://go.microsoft.com/fwlink/?LinkId=158008) (http://go.microsoft.com/fwlink/?LinkId=158008) in the BizTalk Server 2010 documentation.</span></span>  
  
### <a name="optimize-orchestration-latency-by-reducing-the-number-of-persistence-points-if-possible"></a><span data-ttu-id="68821-146">尽可能减少持久性点的数量，从而优化业务流程延迟</span><span class="sxs-lookup"><span data-stu-id="68821-146">Optimize orchestration latency by reducing the number of persistence points, if possible</span></span>  
 <span data-ttu-id="68821-147">业务流程作用域仅需要标记为"长时间运行的事务"如果你想要使用补偿或作用域超时。</span><span class="sxs-lookup"><span data-stu-id="68821-147">An orchestration scope only needs to be marked as “long-running transactional” if you want to use compensation or scope timeouts.</span></span> <span data-ttu-id="68821-148">一个长时间运行的事务范围导致末尾的作用域，一个额外的持久性点，因此如果你不需要使用补偿或作用域超时，应避免它们。</span><span class="sxs-lookup"><span data-stu-id="68821-148">A long-running transactional scope causes an extra persistence point at the end of the scope, so they should be avoided when you don’t need to use compensation or scope timeouts.</span></span> <span data-ttu-id="68821-149">原子作用域可使暂留点末尾的范围，但还可保证没有持久性点会在原子作用域内。</span><span class="sxs-lookup"><span data-stu-id="68821-149">An atomic scope causes a persistence point at the end of the scope, but also guarantees that no persistence points will occur inside the atomic scope.</span></span> <span data-ttu-id="68821-150">在范围内没有持久性此副作用有时可对你批处理持久性点用 （在执行多个发送，例如） 时。</span><span class="sxs-lookup"><span data-stu-id="68821-150">This side-effect of no persistence inside the scope can sometimes be used to your advantage to batch persistence points (when doing multiple sends, for example).</span></span> <span data-ttu-id="68821-151">通常情况下，不过，我们建议尽可能避免原子作用域。</span><span class="sxs-lookup"><span data-stu-id="68821-151">In general, though, we recommend avoiding atomic scopes if possible.</span></span> <span data-ttu-id="68821-152">业务流程引擎将保存到持久性存储区的各个点，在正在运行的业务流程实例的整个状态，以便实例更高版本可以还原在内存中并执行完成。</span><span class="sxs-lookup"><span data-stu-id="68821-152">The orchestration engine saves to persistent storage the entire state of a running orchestration instance at various points, so that the instance can later be restored in memory and carried out to completion.</span></span>   
<span data-ttu-id="68821-153">**业务流程中的持久性点数目是影响消息流经业务流程的延迟的关键因素之一**。</span><span class="sxs-lookup"><span data-stu-id="68821-153">**The number of persistence points in an orchestration is one of the key factors influencing the latency of messages flowing through orchestrations**.</span></span> <span data-ttu-id="68821-154">引擎达到某个持久点时，每次并是此操作会产生延迟成本序列化正在运行业务流程内部状态并将其保存到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="68821-154">Each time the engine hits a persistence point, the internal state of a running orchestration is serialized and saved to the MessageBox and this operation incurs a latency cost.</span></span> <span data-ttu-id="68821-155">序列化的内部状态包括所有消息以及实例化，但尚未发布业务流程中的变量。</span><span class="sxs-lookup"><span data-stu-id="68821-155">The serialization of the internal state includes all messages and variables instantiated and not yet released in the orchestration.</span></span> <span data-ttu-id="68821-156">更大的消息和变量和这些越多，将越长以保留的内部业务流程的状态。</span><span class="sxs-lookup"><span data-stu-id="68821-156">The larger the messages and variables and the greater the number of these, the longer it will take to persist the internal state of an orchestration.</span></span> <span data-ttu-id="68821-157">过多的持久性点可能导致性能明显下降。</span><span class="sxs-lookup"><span data-stu-id="68821-157">An excessive number of persistence points can lead to significant performance degradation.</span></span> <span data-ttu-id="68821-158">为此，我们建议通过减少事务的作用域数消除不必要的持久性点从业务流程，并发送形状。</span><span class="sxs-lookup"><span data-stu-id="68821-158">For this reason, we recommend eliminating unnecessary persistence points from orchestrations by reducing the number of transactional scopes and Send shapes.</span></span> <span data-ttu-id="68821-159">此方法允许减少上提高总体可伸缩性，并降低了业务流程延迟由于业务流程冻结和 rehydration，MessageBox 的争用现象。</span><span class="sxs-lookup"><span data-stu-id="68821-159">This approach allows decreasing the contention on the MessageBox due to orchestration dehydration and rehydration, increasing the overall scalability, and reducing orchestration latency.</span></span>   
<span data-ttu-id="68821-160">另一个建议是始终保留的内部状态的业务流程越小越好。</span><span class="sxs-lookup"><span data-stu-id="68821-160">Another recommendation is to always keep the internal state of an orchestration as small as possible.</span></span> <span data-ttu-id="68821-161">这种技术可以显著减少 XLANG 引擎序列化、 保持及还原发生持久性点时的业务流程的内部状态所用的时间。</span><span class="sxs-lookup"><span data-stu-id="68821-161">This technique can significantly reduce the time spent by the XLANG Engine serializing, persisting and restoring the internal state of an orchestration in case of persistence point.</span></span> <span data-ttu-id="68821-162">实现此目的的一种方法是尽可能创建变量和消息尽可能晚并释放这些尽早尽可能;例如引入了非事务性作用域内你的业务流程和声明变量和而不是在最顶层级别声明它们这些内部范围内的消息。</span><span class="sxs-lookup"><span data-stu-id="68821-162">One way to achieve this is to create variables and messages as late as possible and release them as early as possible; for example introduce non transactional scopes inside your orchestrations and declare variables and messages within these inner scopes instead of declaring them at the top-most level.</span></span> <span data-ttu-id="68821-163">有关最小化业务流程持久性点的详细信息，请参阅 BizTalk Server 2010 文档中的以下主题：</span><span class="sxs-lookup"><span data-stu-id="68821-163">For more information about minimizing orchestration persistence points, see the following topics in the BizTalk Server  2010 documentation:</span></span>  
  
-   <span data-ttu-id="68821-164">[持久性和业务流程引擎](http://go.microsoft.com/fwlink/?LinkID=155292)(http://go.microsoft.com/fwlink/?LinkID=155292)。</span><span class="sxs-lookup"><span data-stu-id="68821-164">[Persistence and the Orchestration Engine](http://go.microsoft.com/fwlink/?LinkID=155292) (http://go.microsoft.com/fwlink/?LinkID=155292).</span></span>  
  
-   <span data-ttu-id="68821-165">[业务流程冻结和 Rehydration](http://go.microsoft.com/fwlink/?LinkID=155284) (http://go.microsoft.com/fwlink/?LinkID=155292)。</span><span class="sxs-lookup"><span data-stu-id="68821-165">[Orchestration Dehydration and Rehydration](http://go.microsoft.com/fwlink/?LinkID=155284) (http://go.microsoft.com/fwlink/?LinkID=155292).</span></span>  
  
## <a name="guidelines-for-using-promoted-properties-to-access-message-tags-or-attributes-from-an-orchestration"></a><span data-ttu-id="68821-166">使用的指导原则提升到访问消息标记或属性从业务流程的属性</span><span class="sxs-lookup"><span data-stu-id="68821-166">Guidelines for using promoted properties to access message tags or attributes from an orchestration</span></span>  
 <span data-ttu-id="68821-167">如果你确实需要升级的属性，将提升用于消息路由、 筛选器，以及消息关联的那些属性。</span><span class="sxs-lookup"><span data-stu-id="68821-167">If you do need to promote properties, promote only those properties that are used for message routing, filters, and message correlation.</span></span> <span data-ttu-id="68821-168">在升级每个属性需要反汇编程序组件 （XML，平面，自定义） 来识别的文档类型，以及从使用从定义的文档类型的 XSD 中包含的相对批注的 XPath 表达式的消息中检索数据。</span><span class="sxs-lookup"><span data-stu-id="68821-168">The promotion of each property requires the disassembler component (XML, Flat, custom) to recognize the document type and to retrieve data from the message using the XPath expression from the relative annotation contained in the XSD that defines the document type.</span></span> <span data-ttu-id="68821-169">此外，每个属性提升在消息代理将消息发布到 MessageBox 数据库将导致 bts_InsertProperty 存储过程的一个单独的调用。</span><span class="sxs-lookup"><span data-stu-id="68821-169">In addition, each property promotion causes a separate call of the bts_InsertProperty stored procedure when the Message Agent publishes the message to the MessageBox database.</span></span> <span data-ttu-id="68821-170">如果业务流程需要访问的特定元素或属性包含的 XML 文档，使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="68821-170">If an orchestration needs to access a particular element or attribute contained by an XML document, use one of the following techniques:</span></span>  
  
-   <span data-ttu-id="68821-171">减少写入和提升属性的数量并消除不需要严格。</span><span class="sxs-lookup"><span data-stu-id="68821-171">Reduce the number of written and promoted properties and eliminate those that are not strictly necessary.</span></span>  
  
-   <span data-ttu-id="68821-172">消除不必要的可分辨的字段。</span><span class="sxs-lookup"><span data-stu-id="68821-172">Eliminate unnecessary distinguished fields.</span></span> <span data-ttu-id="68821-173">可分辨的字段将写入上下文属性，它们可以轻松地占用大量的空间，因为其名称为等于可用于检索数据的 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="68821-173">The distinguished fields are written context properties and they can easily occupy significant space as their name is equal to the XPath expression that is used to retrieve data.</span></span> <span data-ttu-id="68821-174">可分辨的属性被定义为中定义的文档类型的 XSD 批注。</span><span class="sxs-lookup"><span data-stu-id="68821-174">The distinguished property is defined as annotations in the XSD that defines the document type.</span></span> <span data-ttu-id="68821-175">拆装器组件使用相同的方法采用的提升的属性，并使用定义的可分辨的字段，以查找在传入的文档中的 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="68821-175">The disassembler component uses the same approach adopted for promoted properties and uses the XPath expression that defines a distinguished field to find it within in the incoming document.</span></span> <span data-ttu-id="68821-176">然后，拆装器组件将属性写入的上下文中其中：</span><span class="sxs-lookup"><span data-stu-id="68821-176">Then, the disassembler component writes a property in the context where:</span></span>  
  
    -   <span data-ttu-id="68821-177">**名称**： 在批注中定义的 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="68821-177">**Name**: XPath Expression defined in the annotation.</span></span>  
  
    -   <span data-ttu-id="68821-178">**值**： 通过传入文档中的 XPath 表达式标识的元素的值。</span><span class="sxs-lookup"><span data-stu-id="68821-178">**Value**: Value of the element identified by the XPath expression within an incoming document.</span></span>  
  
     <span data-ttu-id="68821-179">尤其是在非常深的文档架构中所述元素时，则可能会很长，XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="68821-179">The XPath Expressions can be very long, especially when the element in question is very deep in the document schema.</span></span> <span data-ttu-id="68821-180">因此，越区分字段，较大的上下文大小。</span><span class="sxs-lookup"><span data-stu-id="68821-180">So, the more distinguished fields, the larger the context size.</span></span> <span data-ttu-id="68821-181">这反过来产生负面影响的整体性能。</span><span class="sxs-lookup"><span data-stu-id="68821-181">This in turn adversely affects the overall performance.</span></span>  
  
-   <span data-ttu-id="68821-182">使用业务流程运行时提供的内置 XPath 函数。</span><span class="sxs-lookup"><span data-stu-id="68821-182">Use the XPath built-in function provided by the orchestration runtime.</span></span>  
  
-   <span data-ttu-id="68821-183">如果消息是相当微小 （几千字节为单位） 和 XML 格式，可以取消消息序列化为.NET 类实例，并使用公共字段和属性。</span><span class="sxs-lookup"><span data-stu-id="68821-183">If messages are quite small (a few kilobytes) and XML-formatted, you can de-serialize the message into a .NET class instance and work with public fields and properties.</span></span> <span data-ttu-id="68821-184">如果消息需要复杂的细化 （自定义代码、 业务规则引擎策略等） 使用.NET 类的实例公开的属性来访问数据是快得多，使用 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="68821-184">If the message needs a complex elaboration (custom code, Business Rule Engine policies, etc.) accessing data using the properties exposed by an instance of a .NET class is much faster using XPath expressions.</span></span> <span data-ttu-id="68821-185">完成后调用的业务流程的业务逻辑，可以恢复到 BizTalk 消息序列化实体对象。</span><span class="sxs-lookup"><span data-stu-id="68821-185">When the business logic invoked by the orchestration has completed, the entity object can be serialized back into a BizTalk message.</span></span> <span data-ttu-id="68821-186">你可以从 XML 架构使用以下工具之一中创建.NET 类： XSD 工具 (.NET Framework 2.0) 或 SVCUTIL (.NET Framework 3.0)。</span><span class="sxs-lookup"><span data-stu-id="68821-186">You can create .NET classes from an XML schema using one of the following tools: XSD tool (.NET Framework 2.0) or SVCUTIL (.NET Framework 3.0).</span></span>  
  
-   <span data-ttu-id="68821-187">启用业务流程的帮助程序组件。</span><span class="sxs-lookup"><span data-stu-id="68821-187">Enable a helper component from an orchestration.</span></span> <span data-ttu-id="68821-188">此方法具有通过使用可分辨的字段优点。</span><span class="sxs-lookup"><span data-stu-id="68821-188">This technique has an advantage over using distinguished fields.</span></span> <span data-ttu-id="68821-189">事实上，业务流程可以读取的 XPath 表达式从配置存储 （配置文件、 SSO 配置存储区，自定义数据库等），因此你必须更改 XPath 表达式，则不需要更改和重新部署架构，当你在升级的属性和 d 的情况下应该执行操作istinguished 字段。</span><span class="sxs-lookup"><span data-stu-id="68821-189">In fact, an orchestration may read the XPath expression from a config store (config file, SSO Config Store, custom Db, and so on) so, when you have to change the XPath expression, you do not have to change and redeploy a schema, as you should do for promoted properties and distinguished fields.</span></span> <span data-ttu-id="68821-190">下面的代码示例提供了帮助程序组件的一个示例。</span><span class="sxs-lookup"><span data-stu-id="68821-190">The following code sample provides an example of a helper component.</span></span> <span data-ttu-id="68821-191">该组件使用 BizTalk 运行时提供的 XPathReader 类。</span><span class="sxs-lookup"><span data-stu-id="68821-191">The component uses the XPathReader class that is provided by the BizTalk runtime.</span></span> <span data-ttu-id="68821-192">这使得代码阅读文档流，直到找到 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="68821-192">This allows the code to read through the document stream until the XPath expression is found.</span></span>  
  
```  
#region Copyright  
//===  
//Microsoft Windows Server AppFabric Customer Advisory Team (CAT)   
//  
// This sample is supplemental to the technical guidance published on the community  
// blog.  
//   
// Author: Paolo Salvatori.  
//===  
// Copyright © 2010 Microsoft Corporation. All rights reserved.  
//   
// THIS CODE AND INFORMATION IS PROVIDED "AS IS" WITHOUT WARRANTY OF ANY KIND, EITHER   
// EXPRESSED OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE IMPLIED WARRANTIES OF   
// MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE. YOU BEAR THE RISK OF USING IT.  
//===  
#endregion  
#region Using Directives  
using System;  
using System.Collections.Generic;  
using System.IO;  
using System.Xml;  
using System.Linq;  
using System.Text;  
using System.Globalization;  
using Microsoft.XLANGs.BaseTypes;   
using Microsoft.BizTalk.Streaming;  
using Microsoft.BizTalk.XPath;  
#endregion  
namespace Microsoft.AppFabric.CAT.Samples.DuplexMEP.Helpers  
{  
public class XPathHelper  
{  
#region Private Constants   
private const string MessageCannotBeNull = "[XPathReader] The message cannot be null.";  
#endregion  
#region Public Static Methods  
public static string GetValue(XLANGMessage message, int partIndex, string xpath)  
{  
try  
{  
if (message == null)  
{  
throw new ApplicationException(MessageCannotBeNull);  
}  
using (Stream stream = message[partIndex].RetrieveAs(typeof(Stream)) as Stream)  
{  
XmlTextReader xmlTextReader = new XmlTextReader(stream);  
XPathCollection xPathCollection = new XPathCollection();  
XPathReader xPathReader = new XPathReader(xmlTextReader, xPathCollection);  
xPathCollection.Add(xpath);  
while (xPathReader.Read())  
{  
if (xPathReader.HasAttributes)  
{  
for (int i = 0; i < xPathReader.AttributeCount; i++)  
{  
xPathReader.MoveToAttribute(i);  
if (xPathReader.Match(xPathCollection[0]))  
{  
return xPathReader.GetAttribute(i);  
}  
}  
}  
if (xPathReader.Match(xPathCollection[0]))  
{  
return xPathReader.ReadString();  
}  
}  
}  
}  
finally  
{  
message.Dispose();  
}  
return string.Empty;  
}  
#endregion  
}  
}  
```  
  
## <a name="minimize-orchestration-complexity-to-improve-performance"></a><span data-ttu-id="68821-193">最小化 orchestration 复杂性以提高性能</span><span class="sxs-lookup"><span data-stu-id="68821-193">Minimize orchestration complexity to improve performance</span></span>  
 <span data-ttu-id="68821-194">业务流程的复杂性对性能有显著的影响。</span><span class="sxs-lookup"><span data-stu-id="68821-194">The complexity of orchestrations has a significant impact on performance.</span></span> <span data-ttu-id="68821-195">随着业务流程复杂性增加，总体性能会降低。</span><span class="sxs-lookup"><span data-stu-id="68821-195">As orchestration complexity increases, overall performance decreases.</span></span> <span data-ttu-id="68821-196">几乎无限的各种方案，可用于业务流程和每个方案可能涉及的复杂程度各异的业务流程。</span><span class="sxs-lookup"><span data-stu-id="68821-196">Orchestrations can be used in an almost infinite variety of scenarios, and each scenario might involve orchestrations of varying complexity.</span></span> <span data-ttu-id="68821-197">避免复杂的业务流程时可能考虑的模块化方法。</span><span class="sxs-lookup"><span data-stu-id="68821-197">Avoid complex orchestrations when possible in favor of a modular approach.</span></span> <span data-ttu-id="68821-198">换而言之，将你的业务逻辑拆分为多个可重用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="68821-198">In other words, split your business logic into multiple, reusable orchestrations.</span></span>  
  
 <span data-ttu-id="68821-199">如果需要实现复杂的业务流程，可以定义消息和变量，内部作用域，只要有可能到而不是在根级别。</span><span class="sxs-lookup"><span data-stu-id="68821-199">If you do need to implement a complex orchestration, define messages and variables into inner scopes whenever possible rather than at the root level.</span></span> <span data-ttu-id="68821-200">此方法会保持在内存中为每个业务流程更小的空间，因为变量和消息时，将释放的流离开已定义的变量和消息的范围。</span><span class="sxs-lookup"><span data-stu-id="68821-200">This technique maintains a smaller footprint in memory for each orchestration because variables and messages are disposed of when the flow leaves the scope where the variables and messages were defined.</span></span> <span data-ttu-id="68821-201">当业务流程将保存到持久性点 MessageBox 时，这种方法是特别有益。</span><span class="sxs-lookup"><span data-stu-id="68821-201">This approach is particularly beneficial when orchestrations are saved to the MessageBox at persistence points.</span></span>  
  
## <a name="use-the-call-orchestration-shape-versus-the-start-orchestration-shape-to-improve-performance"></a><span data-ttu-id="68821-202">使用与启动 Orchestration 形状调用业务流程形状来提高性能</span><span class="sxs-lookup"><span data-stu-id="68821-202">Use the Call Orchestration shape versus the Start Orchestration shape to improve performance</span></span>  
 <span data-ttu-id="68821-203">避免**启动 Orchestration**调整和使用**调用 Orchestration**形状以执行嵌套的业务流程。</span><span class="sxs-lookup"><span data-stu-id="68821-203">Avoid the **Start Orchestration** shape and use the **Call Orchestration** shape to execute a nested orchestration.</span></span> <span data-ttu-id="68821-204">事实上，**调用 Orchestration**形状可以用于以同步方式调用另一个项目中引用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="68821-204">In fact, The **Call Orchestration** shape can be used to synchronously call an orchestration that is referenced in another project.</span></span> <span data-ttu-id="68821-205">此方法允许在 BizTalk 项目之间的重复使用的常见业务流程工作流模式。</span><span class="sxs-lookup"><span data-stu-id="68821-205">This approach allows for reuse of common orchestration workflow patterns across BizTalk projects.</span></span> <span data-ttu-id="68821-206">当调用另一个嵌套的业务流程的情况下同步**调用 Orchestration**形状，等待嵌套业务流程中，若要完成后才能继续的封闭的业务流程。</span><span class="sxs-lookup"><span data-stu-id="68821-206">When you invoke another nested orchestration synchronously with the **Call Orchestration** shape, the enclosing orchestration waits for the nested orchestration to finish before continuing.</span></span> <span data-ttu-id="68821-207">在运行调用业务流程的相同线程上执行嵌套的业务流程。</span><span class="sxs-lookup"><span data-stu-id="68821-207">The nested orchestration is executed on the same thread that runs the calling orchestration.</span></span>  
  
 <span data-ttu-id="68821-208">**启动 Orchestration**形状是类似于**调用 Orchestration**形状，但在这种情况下以异步方式调用嵌套业务流程： 中调用的控制流业务流程继续执行后续调用，而无需等待调用的业务流程，以完成其工作。</span><span class="sxs-lookup"><span data-stu-id="68821-208">The **Start Orchestration** shape is similar to the **Call Orchestration** shape, but in this case the nested orchestration is called in an asynchronous manner: the flow of control in the invoking orchestration proceeds beyond the invocation, without waiting for the invoked orchestration to finish its work.</span></span> <span data-ttu-id="68821-209">为了实现此调用方和被调用的业务流程，间的分离**启动 Orchestration**实现通过发布到 BizTalk Messagebox 的消息。</span><span class="sxs-lookup"><span data-stu-id="68821-209">In order to implement this decoupling between the caller and the called orchestrations, the **Start Orchestration** is implemented via publication of a message to the BizTalk Messagebox.</span></span> <span data-ttu-id="68821-210">而执行嵌套的业务流程的进程内 BizTalk 主机实例然后使用此消息。</span><span class="sxs-lookup"><span data-stu-id="68821-210">This message is then consumed by an in-process BizTalk host instance which executes the nested orchestration.</span></span> <span data-ttu-id="68821-211">如果可能，请使用**调用 Orchestration**，特别是当调用的业务流程需要等待才能继续处理嵌套的业务流程的结果。</span><span class="sxs-lookup"><span data-stu-id="68821-211">When possible, use **Call Orchestration**, especially if the calling orchestration needs to wait for a result from the nested orchestration in order to continue processing.</span></span>  <span data-ttu-id="68821-212">有关使用调用业务流程形状的详细信息，请参阅 BizTalk Server 2010 文档中的以下主题：</span><span class="sxs-lookup"><span data-stu-id="68821-212">For more information about using the Call Orchestration shape, see the following topics in the BizTalk Server 2010 documentation:</span></span>  
  
-   <span data-ttu-id="68821-213">[使用在业务流程中的直接绑定端口](http://go.microsoft.com/fwlink/?LinkId=139902)(http://go.microsoft.com/fwlink/?LinkId=139902)。</span><span class="sxs-lookup"><span data-stu-id="68821-213">[Working with Direct Bound Ports in Orchestrations](http://go.microsoft.com/fwlink/?LinkId=139902) (http://go.microsoft.com/fwlink/?LinkId=139902).</span></span>  
  
-   <span data-ttu-id="68821-214">[嵌套业务流程](http://go.microsoft.com/fwlink/?LinkId=139903)(http://go.microsoft.com/fwlink/?LinkId=139903)。</span><span class="sxs-lookup"><span data-stu-id="68821-214">[Nesting Orchestrations](http://go.microsoft.com/fwlink/?LinkId=139903) (http://go.microsoft.com/fwlink/?LinkId=139903).</span></span>  
  
## <a name="use-xmlreader-with-xlangmessage-versus-using-xmlreader-with-xmldocument-to-improve-orchestration-performance"></a><span data-ttu-id="68821-215">XmlReader 使用 XLANGMessage 与使用 XmlReader XmlDocument 来改善业务流程</span><span class="sxs-lookup"><span data-stu-id="68821-215">Use XmlReader with XLANGMessage versus using XmlReader with XmlDocument to improve orchestration performance</span></span>  
 <span data-ttu-id="68821-216">要提高.NET 调用的方法从业务流程的业务流程性能，请使用带有 XLANGMessage，不 XmlDocument XmlReader。</span><span class="sxs-lookup"><span data-stu-id="68821-216">To improve orchestration performance for .NET methods called from an orchestration, use XmlReader with XLANGMessage, not XmlDocument.</span></span> <span data-ttu-id="68821-217">下面的代码示例说明了此功能。</span><span class="sxs-lookup"><span data-stu-id="68821-217">The following code example illustrates this functionality.</span></span>  
  
```csharp  
// As a general rule, use XmlReader with XLANGMessage, not XmlDocument.   
// This is illustrated in the parameter passed into the following code.   
// The XLANG/s compiler doesn't allow a return value of XmlReader   
// so documents must be initially constructed as XmlDocument()  
public static XmlDocument FromMsg(XLANGMessage old)  
{  
    //get at the data  
    XmlDocument ret = new XmlDocument();  
  
    try{  
        XmlReader reader = (XmlReader)old[0].RetrieveAs(typeof(XmlReader));  
        //construct new message from old  
        //read property  
        object msgid = old.GetPropertyValue(typeof(BTS.MessageID));  
    }  
    finally {  
        // Call Dispose on the XLANGMessage object   
        // because the message doesn't belong to the   
        // .NET runtime - it belongs to the Messagebox database   
        old.Dispose();  
    }  
    return ret;  
}  
```  
  
 <span data-ttu-id="68821-218">另一种方法就是创建基于架构的.NET 类。</span><span class="sxs-lookup"><span data-stu-id="68821-218">Another method would be to create a .NET class based on the schema.</span></span> <span data-ttu-id="68821-219">这将使较少的内存比加载到文档**XmlDocument**对象，以及为.NET 开发人员提供轻松访问的架构元素。</span><span class="sxs-lookup"><span data-stu-id="68821-219">This takes less memory than loading the document into an **XmlDocument** object, as well as providing easy access to the schema elements for .NET developers.</span></span> <span data-ttu-id="68821-220">若要生成基于 BizTalk 架构的类，可以使用与 Visual Studio 提供的 xsd.exe 工具。</span><span class="sxs-lookup"><span data-stu-id="68821-220">To generate a class based on a BizTalk schema, you can use the xsd.exe tool provided with Visual Studio.</span></span> <span data-ttu-id="68821-221">例如，运行**xsd.exe \<schema.xsd >/类**ItemB，ItemC，将针对简单架构包含名为 ItemA 的字段，生成下面的类。</span><span class="sxs-lookup"><span data-stu-id="68821-221">For example, running **xsd.exe \<schema.xsd> /classes** against a simple schema containing fields named ItemA, ItemB, ItemC, will produce the following class.</span></span>  
  
```csharp  
//------------------------------------------------------------------------------  
// <auto-generated>  
//     This code was generated by a tool.  
//     Runtime Version:2.0.50727.1433  
//  
//     Changes to this file may cause incorrect behavior and will be lost if  
//     the code is regenerated.  
// </auto-generated>  
//------------------------------------------------------------------------------  
  
using System.Xml.Serialization;  
  
//   
// This source code was auto-generated by xsd, Version=2.0.50727.42.  
//  
  
/// <remarks/>  
[System.CodeDom.Compiler.GeneratedCodeAttribute("xsd", "2.0.50727.42")]  
[System.SerializableAttribute()]  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.ComponentModel.DesignerCategoryAttribute("code")]  
[System.Xml.Serialization.XmlTypeAttribute(AnonymousType=true, Namespace="http://Schemas.MySchema")]  
[System.Xml.Serialization.XmlRootAttribute(Namespace="http://Schemas.MySchema", IsNullable=false)]  
public partial class MySchemaRoot {  
  
    private string itemAField;  
  
    private string itemBField;  
  
    private string itemCField;  
  
    /// <remarks/>  
    [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified)]  
    public string ItemA {  
        get {  
            return this.itemAField;  
        }  
        set {  
            this.itemAField = value;  
        }  
    }  
  
    /// <remarks/>  
    [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified)]  
    public string ItemB {  
        get {  
            return this.itemBField;  
        }  
        set {  
            this.itemBField = value;  
        }  
    }  
  
    /// <remarks/>  
    [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified)]  
    public string ItemC {  
        get {  
            return this.itemCField;  
        }  
        set {  
            this.itemCField = value;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="68821-222">此类然后中.NET 程序集才能访问消息元素中，引用和返回的对象可以直接分配给消息。</span><span class="sxs-lookup"><span data-stu-id="68821-222">This class can then be referenced in your .NET assembly in order to access the message elements, and the returned object can be directly assigned to a message.</span></span> <span data-ttu-id="68821-223">下面是类的生成上面的一个用法示例。</span><span class="sxs-lookup"><span data-stu-id="68821-223">The following is an example use of the class generated above.</span></span>  
  
```csharp  
public static Root SetValues(Microsoft.XLANGs.BaseTypes.XLANGMessage msg)  
{  
   try  
   {  
   MySchemaRoot rootObj=(MySchemaRoot)msg[0].RetrieveAs(typeof(MySchemaRoot);  
   rootObj.ItemA="value a";  
   rootObj.ItemB="value b";  
   rootObj.ItemC="value c";  
   }  
    finally {  
        msg.Dispose();  
            }  
  
   return rootObj;  
}  
```  
  
 <span data-ttu-id="68821-224">此方法允许你在处理消息时使用的面向对象的方法。</span><span class="sxs-lookup"><span data-stu-id="68821-224">This technique allows you to use an object-oriented approach when processing messages.</span></span> <span data-ttu-id="68821-225">此方法应主要用于相对较小的消息。</span><span class="sxs-lookup"><span data-stu-id="68821-225">This technique should be used primarily with relatively small messages.</span></span> <span data-ttu-id="68821-226">这是因为即使此方法使用少得多的内存比时加载到消息**XmlDocument**对象，整个消息，则仍加载到内存。</span><span class="sxs-lookup"><span data-stu-id="68821-226">This is because even though this technique uses considerably less memory than when loading the message into an **XmlDocument** object, the entire message is still loaded into memory.</span></span> <span data-ttu-id="68821-227">当处理更大的消息时，使用**XmlReader**类来读取消息和**XmlWriter**类将消息写入。</span><span class="sxs-lookup"><span data-stu-id="68821-227">When processing larger messages, use the **XmlReader** class to read messages and the **XmlWriter** class to write messages.</span></span> <span data-ttu-id="68821-228">使用时**XmlReader**和**XmlWriter**，消息包含在**VirtualStream**对象。</span><span class="sxs-lookup"><span data-stu-id="68821-228">When using **XmlReader** and **XmlWriter**, the message is contained in a **VirtualStream** object.</span></span> <span data-ttu-id="68821-229">如果消息大小超过指定的值**大型消息阈值 （字节）** ，则公开的 BizTalk 组属性配置页上，将消息写入到文件系统。</span><span class="sxs-lookup"><span data-stu-id="68821-229">If the message size exceeds the value specified for **Large message threshold (bytes)** that is exposed on the BizTalk Group Properties configuration page, the message is written to the file system.</span></span> <span data-ttu-id="68821-230">这会降低整体性能，但是避免内存不足异常。</span><span class="sxs-lookup"><span data-stu-id="68821-230">This decreases overall performance, but avoids out of memory exceptions.</span></span>  
  
## <a name="improve-performance-by-minimizing-the-use-of-logical-ports-bound-to-physical-ports"></a><span data-ttu-id="68821-231">通过使用绑定到的物理端口的逻辑端口最大限度提高性能</span><span class="sxs-lookup"><span data-stu-id="68821-231">Improve performance by minimizing the use of logical ports bound to physical ports</span></span>  
 <span data-ttu-id="68821-232">可以通过将绑定到使用以下适配器的物理端口的逻辑端口的使用降至最低来提高性能：</span><span class="sxs-lookup"><span data-stu-id="68821-232">You can increase performance by minimizing the use of logical ports bound to physical ports that use the following adapters:</span></span>  
  
-   <span data-ttu-id="68821-233">SQL Server、 Oracle</span><span class="sxs-lookup"><span data-stu-id="68821-233">SQL Server, Oracle</span></span>  
  
-   <span data-ttu-id="68821-234">WSE，HTTP，WCF</span><span class="sxs-lookup"><span data-stu-id="68821-234">WSE, HTTP, WCF</span></span>  
  
-   <span data-ttu-id="68821-235">MSMQ MQSeries</span><span class="sxs-lookup"><span data-stu-id="68821-235">MSMQ, MQSeries</span></span>  
  
 <span data-ttu-id="68821-236">在 BizTalk Server 2010 中，发送和接收管道可以直接从业务流程使用 Microsoft.XLANGs.Pipeline.dll 中包含的 XLANGPipelineManager 类调用。</span><span class="sxs-lookup"><span data-stu-id="68821-236">In BizTalk Server 2010, send and receive pipelines can be directly invoked from an orchestration using the XLANGPipelineManager class contained in the Microsoft.XLANGs.Pipeline.dll.</span></span> <span data-ttu-id="68821-237">因此，管道处理可以变为从端口业务流程;业务流程中的逻辑端口可以替换调用给定的.NET 类的实例 （例如，使用 ADO.NET 数据访问组件） 是表达式形状。</span><span class="sxs-lookup"><span data-stu-id="68821-237">Thus, the processing of pipelines can be moved from ports to orchestrations; logical ports in an orchestration can be substituted with an Expression shape, which invokes an instance of a given .NET class (for example, a Data Access component using ADO.NET).</span></span> <span data-ttu-id="68821-238">在采用此方法之前, 应该注意，如果不使用适配器和物理端口，你会失去利用其函数，如批处理、 重试次数、 声明性配置和辅助传输协议的能力。</span><span class="sxs-lookup"><span data-stu-id="68821-238">Before adopting this technique, you should be aware that if you do not use adapters and physical ports, you lose the ability to leverage their functions, such as batching, retries, declarative configuration, and secondary transports.</span></span>  
  
## <a name="orchestration-design-patterns"></a><span data-ttu-id="68821-239">业务流程设计模式</span><span class="sxs-lookup"><span data-stu-id="68821-239">Orchestration Design Patterns</span></span>  
 <span data-ttu-id="68821-240">业务流程设计器允许开发人员实现范围广泛的企业集成模式。</span><span class="sxs-lookup"><span data-stu-id="68821-240">The Orchestration Designer allows developers to implement a wide range of enterprise integration patterns.</span></span> <span data-ttu-id="68821-241">一些常见模式包括聚合器、 异常处理和补偿、 消息代理、 散点图和收集，并按顺序和并行的队列。</span><span class="sxs-lookup"><span data-stu-id="68821-241">Some common patterns include Aggregator, Exception Handling and Compensation, Message Broker, Scatter and Gather, and Sequential and Parallel Convoy.</span></span> <span data-ttu-id="68821-242">可以利用这些模式来开发复杂的企业应用程序集成 (EAI)、 面向服务体系结构 (SOA) 和业务流程管理 (BPM) 解决方案与 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="68821-242">Those patterns can be utilized to develop complex Enterprise Application Integration (EAI), Service-Oriented Architecture (SOA), and Business Process Management (BPM) solutions with BizTalk Server.</span></span> <span data-ttu-id="68821-243">有关业务流程设计模式的详细信息，请参阅主题[实现在业务流程中的设计模式](http://go.microsoft.com/fwlink/?LinkId=140042)(http://go.microsoft.com/fwlink/?LinkId = 140042) BizTalk Server 文档中和[模式和最佳实践企业集成](http://go.microsoft.com/fwlink/?LinkId=140043)(http://go.microsoft.com/fwlink/?LinkId = 140043)。</span><span class="sxs-lookup"><span data-stu-id="68821-243">For more information about Orchestration Design Patterns, see the topic [Implementing Design Patterns in Orchestrations](http://go.microsoft.com/fwlink/?LinkId=140042) (http://go.microsoft.com/fwlink/?LinkId=140042) in the BizTalk Server documentation and [Patterns and Best Practices for Enterprise Integration](http://go.microsoft.com/fwlink/?LinkId=140043) (http://go.microsoft.com/fwlink/?LinkId=140043).</span></span>  
  
## <a name="make-appropriate-use-of-net-classes-in-orchestrations-to-maximize-performance"></a><span data-ttu-id="68821-244">在业务流程来最大化性能中请适当地使用.NET 类</span><span class="sxs-lookup"><span data-stu-id="68821-244">Make appropriate use of .NET classes in orchestrations to maximize performance</span></span>  
 <span data-ttu-id="68821-245">一般情况下，使用内部业务流程的.NET 类可以划分为两个不同类别：</span><span class="sxs-lookup"><span data-stu-id="68821-245">In general, the .NET classes used inside an orchestration can be divided into two distinct categories:</span></span>  
  
-   <span data-ttu-id="68821-246">**帮助程序和服务-**这些类提供对业务流程，例如跟踪、 错误处理、 缓存和序列化/反序列化的公共服务。</span><span class="sxs-lookup"><span data-stu-id="68821-246">**Helpers and services -** These classes provide common services to orchestrations such as tracing, error handling, caching, and serialization/deserialization.</span></span> <span data-ttu-id="68821-247">大多数这些类可以作为与任何内部状态和多个公共静态方法的静态类实现。</span><span class="sxs-lookup"><span data-stu-id="68821-247">Most of these classes can be implemented as static classes with no internal state and multiple public static methods.</span></span> <span data-ttu-id="68821-248">此方法可避免在不同的业务流程运行在同一时间，这有助于减少主机进程的工作空间和保存内存中创建多个对象的同一个类。</span><span class="sxs-lookup"><span data-stu-id="68821-248">This approach avoids creating multiple objects of the same class in different orchestrations running at the same time, which helps to reduce the working space of host processes and save memory.</span></span> <span data-ttu-id="68821-249">无状态的类可帮助减少必须序列化和业务流程是已冻结时保留到 BizTalk MessageBox 的内部状态的总体大小。</span><span class="sxs-lookup"><span data-stu-id="68821-249">A class that is stateless helps to reduce the overall size of the internal state that must be serialized and persisted to the BizTalk MessageBox when an orchestration is dehydrated.</span></span>  
  
-   <span data-ttu-id="68821-250">**实体和业务对象-**可以使用这些类以管理实体，例如订单、 订单项和客户。</span><span class="sxs-lookup"><span data-stu-id="68821-250">**Entities and Business Objects -** You can use these classes to manage entities, such as orders, order items, and customers.</span></span> <span data-ttu-id="68821-251">单个业务流程内部可以创建和管理多个相同类型的实例。</span><span class="sxs-lookup"><span data-stu-id="68821-251">A single orchestration can internally create and manage multiple instances of the same type.</span></span> <span data-ttu-id="68821-252">这些类是通常有状态的并公开公共字段和/或方法，以便修改对象的内部状态以及属性。</span><span class="sxs-lookup"><span data-stu-id="68821-252">These classes are typically stateful, and expose public fields and/or properties along with methods to modify the internal state of the object.</span></span> <span data-ttu-id="68821-253">这些类的实例可以通过反 XLANGMessage 部分序列化为.NET 对象，通过使用动态创建**XmlSerializer**或**DataContractSerializer**类或通过使用**XLANGPart.RetrieveAs**方法。</span><span class="sxs-lookup"><span data-stu-id="68821-253">Instances of these classes can be dynamically created by deserializing an XLANGMessage part into a .NET object by using the **XmlSerializer** or the **DataContractSerializer** classes or by using the **XLANGPart.RetrieveAs** method.</span></span> <span data-ttu-id="68821-254">您构建业务流程使用有状态的类的实例的创建尽可能后期和不再需要后立即释放方式中的非事务性作用域。</span><span class="sxs-lookup"><span data-stu-id="68821-254">You should structure an orchestration using non-transactional scopes in such a way that instances of stateful classes are created as late as possible and released as soon as they are no longer needed.</span></span> <span data-ttu-id="68821-255">此方法减少主机进程的工作空间，并最大程度减少已冻结业务流程时持久化到 MessageBox 数据库的序列化的内部状态的总体大小。</span><span class="sxs-lookup"><span data-stu-id="68821-255">This approach reduces the working space of host processes and minimizes the overall size of the internal state that is serialized and persisted to the MessageBox database when an orchestration is dehydrated.</span></span> <span data-ttu-id="68821-256">有关使用 BizTalk Server 中的业务流程的详细信息，请参阅文章[适用的 BizTalk Server 业务流程的常见问题](http://go.microsoft.com/fwlink/?LinkID=116886)(http://go.microsoft.com/fwlink/?LinkID=116886)。</span><span class="sxs-lookup"><span data-stu-id="68821-256">For more information about using orchestrations in BizTalk Server, see the article [FAQ for BizTalk Server Orchestrations](http://go.microsoft.com/fwlink/?LinkID=116886) (http://go.microsoft.com/fwlink/?LinkID=116886).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="68821-257">虽然此文章 BizTalk Server 2004 和 BizTalk Server 2006 编写的介绍的概念将还适用于 BizTalk Server 2010 业务流程中。</span><span class="sxs-lookup"><span data-stu-id="68821-257">While this article is written for BizTalk Server 2004 and BizTalk Server 2006, the concepts presented also apply to BizTalk Server 2010 orchestrations.</span></span>  
  
## <a name="orchestration-exception-handler-blocks"></a><span data-ttu-id="68821-258">业务流程异常处理程序块</span><span class="sxs-lookup"><span data-stu-id="68821-258">Orchestration Exception Handler Blocks</span></span>  
 <span data-ttu-id="68821-259">使用业务流程异常处理程序块时，包含在一个或多个作用域 （非事务作用域尽可能） 的所有业务流程形状，并至少创建以下异常处理程序块：</span><span class="sxs-lookup"><span data-stu-id="68821-259">When using Orchestration exception Handler blocks, include all orchestration shapes in one or multiple scopes (non transactional scopes whenever possible) and create at least the following exception handler blocks:</span></span>  
  
-   <span data-ttu-id="68821-260">异常处理程序块中处理泛型 System.Exception 错误。</span><span class="sxs-lookup"><span data-stu-id="68821-260">An exception handler block for handling a generic System.Exception error.</span></span>  
  
-   <span data-ttu-id="68821-261">异常处理程序块中处理了一般异常，以便捕获和处理可能的非托管的错误，例如 COM 异常。</span><span class="sxs-lookup"><span data-stu-id="68821-261">An exception handler block for handling a general exception in order to catch and handle possible unmanaged errors, such as COM exceptions.</span></span>  
  
 <span data-ttu-id="68821-262">有关使用 Orchestration 异常处理块的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="68821-262">For more information about using Orchestration exception handling blocks, see the following articles:</span></span>  
  
-   <span data-ttu-id="68821-263">[使用 BizTalk Server 异常处理](http://msdn.microsoft.com/library/aa561229.aspx)(http://msdn.microsoft.com/library/aa561229.aspx)。</span><span class="sxs-lookup"><span data-stu-id="68821-263">[Using BizTalk Server Exception Handling](http://msdn.microsoft.com/library/aa561229.aspx) (http://msdn.microsoft.com/library/aa561229.aspx).</span></span>  
  
-   <span data-ttu-id="68821-264">[Charles Young 博客，BizTalk Server 2006： 补偿模型](http://go.microsoft.com/fwlink/?LinkId=158017)(http://go.microsoft.com/fwlink/?LinkId=158017)。</span><span class="sxs-lookup"><span data-stu-id="68821-264">[Charles Young Blog, BizTalk Server 2006: The Compensation Model](http://go.microsoft.com/fwlink/?LinkId=158017) (http://go.microsoft.com/fwlink/?LinkId=158017).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="68821-265">而使用编写的此博客[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]记住，博客中所述的原则也适用于[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="68821-265">While this blog was written with [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] in mind, the principles described in the blog also apply to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span></span>  
  
## <a name="considerations-when-using-maps-in-orchestrations"></a><span data-ttu-id="68821-266">在业务流程中使用地图时的注意事项</span><span class="sxs-lookup"><span data-stu-id="68821-266">Considerations when using maps in orchestrations</span></span>  
 <span data-ttu-id="68821-267">在业务流程中使用地图时，应考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="68821-267">The following considerations apply when using maps in orchestrations:</span></span>  
  
-   <span data-ttu-id="68821-268">如果使用映射要提取或设置与使用的属性中业务流程，业务逻辑使用可分辨的字段，或升级的属性。</span><span class="sxs-lookup"><span data-stu-id="68821-268">If you are using a map to extract or set properties used with business logic in an orchestration, use distinguished fields or promoted properties.</span></span> <span data-ttu-id="68821-269">应遵循这种做法，因为如果提取或设置文档的与映射的值加载到内存但是当使用区分字段，或升级的属性，则业务流程引擎将访问消息上下文并不会加载文档读入内存。</span><span class="sxs-lookup"><span data-stu-id="68821-269">This practice should be followed because when extracting or setting values with a map the document is loaded into memory however when using distinguished fields or promoted properties, the orchestration engine accesses the message context and does not load the document into memory.</span></span>  
  
-   <span data-ttu-id="68821-270">如果正在使用映射将多个字段聚合为一个字段，请将可分辨字段或升级属性与业务流程变量结合使用，以累计结果集。</span><span class="sxs-lookup"><span data-stu-id="68821-270">If you are using a map to aggregate several fields into one field, use distinguished fields or promoted properties with an orchestration variable to accumulate the result set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68821-271">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68821-271">See Also</span></span>  
 [<span data-ttu-id="68821-272">优化性能</span><span class="sxs-lookup"><span data-stu-id="68821-272">Optimizing Performance</span></span>](../technical-guides/optimizing-performance.md)