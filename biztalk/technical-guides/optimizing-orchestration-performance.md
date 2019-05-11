---
title: 优化业务流程性能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 437c7325-f037-451a-8dbd-f8d8c8889e20
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 688aae3d543d93941bb356c0d6d207eb1d4be851
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291412"
---
# <a name="optimizing-orchestration-performance"></a><span data-ttu-id="6c07b-102">优化业务流程性能</span><span class="sxs-lookup"><span data-stu-id="6c07b-102">Optimizing Orchestration Performance</span></span>
<span data-ttu-id="6c07b-103">本主题介绍在 BizTalk Server 解决方案中使用业务流程的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="6c07b-103">This topic describes best practices for using orchestrations in BizTalk Server solutions.</span></span> <span data-ttu-id="6c07b-104">这包括有关建议：</span><span class="sxs-lookup"><span data-stu-id="6c07b-104">This includes recommendations for:</span></span>  
  
-   <span data-ttu-id="6c07b-105">减少使用业务流程的 BizTalk Server 解决方案的延迟</span><span class="sxs-lookup"><span data-stu-id="6c07b-105">Reducing latency of BizTalk Server solutions that use orchestrations</span></span>  
  
    -   <span data-ttu-id="6c07b-106">消除消息传送模式仅用于业务流程</span><span class="sxs-lookup"><span data-stu-id="6c07b-106">Eliminating orchestrations for messaging only patterns</span></span>  
  
    -   <span data-ttu-id="6c07b-107">利用内联从业务流程将发送</span><span class="sxs-lookup"><span data-stu-id="6c07b-107">Utilizing inline sends from orchestrations</span></span>  
  
    -   <span data-ttu-id="6c07b-108">最大程度减少业务流程持久化点</span><span class="sxs-lookup"><span data-stu-id="6c07b-108">Minimizing orchestration persistence points</span></span>  
  
-   <span data-ttu-id="6c07b-109">嵌套业务流程</span><span class="sxs-lookup"><span data-stu-id="6c07b-109">Nesting orchestrations</span></span>  
  
-   <span data-ttu-id="6c07b-110">业务流程设计模式</span><span class="sxs-lookup"><span data-stu-id="6c07b-110">Orchestration design patterns</span></span>  
  
-   <span data-ttu-id="6c07b-111">业务流程的异常处理块</span><span class="sxs-lookup"><span data-stu-id="6c07b-111">Orchestration exception handling blocks</span></span>  
  
## <a name="recommendations-for-optimizing-orchestrations-for-low-latency-scenarios"></a><span data-ttu-id="6c07b-112">有关优化的低延迟方案的业务流程的建议</span><span class="sxs-lookup"><span data-stu-id="6c07b-112">Recommendations for optimizing orchestrations for low latency scenarios</span></span>  
 <span data-ttu-id="6c07b-113">可以使用以下方法以减少使用业务流程的 BizTalk Server 解决方案的延迟。</span><span class="sxs-lookup"><span data-stu-id="6c07b-113">The following techniques can be used to reduce latency of BizTalk Server solutions that use orchestrations.</span></span>  
  
### <a name="eliminate-orchestrations-for-messaging-only-patterns"></a><span data-ttu-id="6c07b-114">消除消息传送模式仅用于业务流程</span><span class="sxs-lookup"><span data-stu-id="6c07b-114">Eliminate orchestrations for messaging only patterns</span></span>  
 <span data-ttu-id="6c07b-115">尽可能最小化使用业务流程来提高总体吞吐量并减少的业务流程的延迟。</span><span class="sxs-lookup"><span data-stu-id="6c07b-115">When possible minimize the use of orchestrations to increase overall throughput and reduce the latency of business processes.</span></span> <span data-ttu-id="6c07b-116">如果存在无需运行长时间运行的事务，并且无需调用为每个请求的多个系统，请考虑消除业务流程和将业务逻辑移到接收和发送端口，以减少往返的总金额BizTalkMsgBoxDb 和减少延迟，因为数据库访问权限。</span><span class="sxs-lookup"><span data-stu-id="6c07b-116">If there is no need to run long running transactions and there is no need to invoke several systems for each request, then consider eliminating orchestrations and moving business logic to Receive and Send Ports to reduce the total amount of roundtrips to the BizTalkMsgBoxDb and decrease the latency due to database access.</span></span> <span data-ttu-id="6c07b-117">在这种情况下，实现自定义管道和重复使用以前已从业务流程调用的帮助程序类。</span><span class="sxs-lookup"><span data-stu-id="6c07b-117">In this case, implement custom pipelines and reuse helper classes that were previously invoked from orchestrations.</span></span> <span data-ttu-id="6c07b-118">使用业务流程仅在万不得已时实现设计模式的散点图和收集或保护。</span><span class="sxs-lookup"><span data-stu-id="6c07b-118">Use orchestrations only when strictly needed to implement design patterns as Scatter and Gather or Convoys.</span></span> <span data-ttu-id="6c07b-119">有关业务流程设计模式的详细信息，请参阅主题[业务流程中实现设计模式](http://go.microsoft.com/fwlink/?LinkId=140042)(http://go.microsoft.com/fwlink/?LinkId=140042) BizTalk Server 文档中。</span><span class="sxs-lookup"><span data-stu-id="6c07b-119">For more information about Orchestration Design Patterns, see the topic [Implementing Design Patterns in Orchestrations](http://go.microsoft.com/fwlink/?LinkId=140042) (http://go.microsoft.com/fwlink/?LinkId=140042) in the BizTalk Server documentation.</span></span>  
  
### <a name="use-inline-sends-from-orchestrations-to-accommodate-low-latency-scenarios"></a><span data-ttu-id="6c07b-120">使用内联形式从发送业务流程以适应较低的延迟情况</span><span class="sxs-lookup"><span data-stu-id="6c07b-120">Use inline sends from orchestrations to accommodate low latency scenarios</span></span>  
 <span data-ttu-id="6c07b-121">只要有可能，尽量减少使用的业务流程，并倾向于仅消息传递模式来提高总体吞吐量并减少的业务流程的延迟。</span><span class="sxs-lookup"><span data-stu-id="6c07b-121">Whenever possible, minimize the use of orchestrations and favor messaging-only patterns to increase the overall throughput and reduce the latency of the business processes.</span></span> <span data-ttu-id="6c07b-122">如果长时间运行的事务不需要且无需为业务逻辑来调用多个系统，然后考虑移动业务逻辑来接收和发送端口并消除使用业务流程。</span><span class="sxs-lookup"><span data-stu-id="6c07b-122">If there is no need for long-running transactions and there is no need for business logic to invoke several systems, then consider moving business logic to receive and send Ports and eliminating the use of orchestrations.</span></span> <span data-ttu-id="6c07b-123">这种方法可以实现包含自定义管道，并且其中重复使用以前已从业务流程调用的帮助程序类。</span><span class="sxs-lookup"><span data-stu-id="6c07b-123">This approach can be implemented with custom pipelines and which reuse the helper classes that were previously invoked from orchestrations.</span></span> <span data-ttu-id="6c07b-124">若要实现更好的性能低延迟方案，采用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="6c07b-124">In order to achieve better performance in low latency scenarios, adopt one of the following approaches:</span></span>  
  
-   <span data-ttu-id="6c07b-125">消除不必要的业务流程，采用仅消息传递模式，以减少到 BizTalk MessageBox 数据库之间的往返次数的总金额。</span><span class="sxs-lookup"><span data-stu-id="6c07b-125">Eliminate unnecessary orchestrations and adopt messaging-only patterns to reduce the total amount of roundtrips to the BizTalk MessageBox database.</span></span> <span data-ttu-id="6c07b-126">这种方法可容纳较低的延迟，因为内联发送绕过 BizTalk 消息引擎和关联的开销。</span><span class="sxs-lookup"><span data-stu-id="6c07b-126">This approach accommodates low latency because inline sends bypass the BizTalk messaging engine and the associated overhead.</span></span> <span data-ttu-id="6c07b-127">业务流程内联发送功能提供 BizTalk Server 2006 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="6c07b-127">Orchestration inline send functionality is provided with BizTalk Server 2006 and later.</span></span>  
  
-   <span data-ttu-id="6c07b-128">在业务流程，消除逻辑端口绑定到物理端口，并使用在其位置的行中发送。</span><span class="sxs-lookup"><span data-stu-id="6c07b-128">Inside orchestrations, eliminate logical ports bound to physical ports and use in-line sends in their place.</span></span> <span data-ttu-id="6c07b-129">例如，内联发送无法用于创建 WCF 代理类来调用下游 Web 服务或 ADO.NET 组件来访问 SQL Server 数据库的实例。</span><span class="sxs-lookup"><span data-stu-id="6c07b-129">For example, an inline send could be used to create an instance of a  WCF proxy class to invoke a downstream Web service or an ADO.NET component to access a SQL Server database.</span></span> <span data-ttu-id="6c07b-130">在下图中，当业务流程实例化业务组件，可在内部使用 WCF 执行内联发送代理对象来直接调用下游 Web 服务：</span><span class="sxs-lookup"><span data-stu-id="6c07b-130">In the following diagram, an inline send is performed when the orchestration instantiates a business component, which internally makes use of a WCF  proxy object to directly invoke a downstream Web service:</span></span>  
  
     <span data-ttu-id="6c07b-131">![BizTalk 业务流程内联发送的描述](../technical-guides/media/inlinesend.gif "InlineSend")</span><span class="sxs-lookup"><span data-stu-id="6c07b-131">![Depiction of BizTalk Orchestration Inline Send](../technical-guides/media/inlinesend.gif "InlineSend")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c07b-132">使用从业务流程内联发送将显著减少延迟，尽管存在一些限制到这种方法。</span><span class="sxs-lookup"><span data-stu-id="6c07b-132">Although using inline sends from orchestrations will significantly reduce latency, there are limitations to this approach.</span></span> <span data-ttu-id="6c07b-133">由于内联发送绕过 BizTalk 消息引擎，提供与消息引擎的以下功能不可用：</span><span class="sxs-lookup"><span data-stu-id="6c07b-133">Because inline sends bypass the BizTalk messaging engine, the following functionality provided with the messaging engine is not available:</span></span>  
> 
> - <span data-ttu-id="6c07b-134">事务性管道</span><span class="sxs-lookup"><span data-stu-id="6c07b-134">Transactional pipelines</span></span>  
>   -   <span data-ttu-id="6c07b-135">可恢复管道</span><span class="sxs-lookup"><span data-stu-id="6c07b-135">Recoverable pipelines</span></span>  
>   -   <span data-ttu-id="6c07b-136">调用 BAM 侦听器 API 的管道</span><span class="sxs-lookup"><span data-stu-id="6c07b-136">Pipelines that call the BAM interceptor API</span></span>  
>   -   <span data-ttu-id="6c07b-137">BizTalk Server 适配器支持</span><span class="sxs-lookup"><span data-stu-id="6c07b-137">BizTalk Server adapter support</span></span>  
>   -   <span data-ttu-id="6c07b-138">批处理</span><span class="sxs-lookup"><span data-stu-id="6c07b-138">Batching</span></span>  
>   -   <span data-ttu-id="6c07b-139">重试次数</span><span class="sxs-lookup"><span data-stu-id="6c07b-139">Retries</span></span>  
>   -   <span data-ttu-id="6c07b-140">相关集初始化</span><span class="sxs-lookup"><span data-stu-id="6c07b-140">Correlation set initialization</span></span>  
>   -   <span data-ttu-id="6c07b-141">声明性配置</span><span class="sxs-lookup"><span data-stu-id="6c07b-141">Declarative configuration</span></span>  
>   -   <span data-ttu-id="6c07b-142">辅助传输</span><span class="sxs-lookup"><span data-stu-id="6c07b-142">Secondary transports</span></span>  
>   -   <span data-ttu-id="6c07b-143">跟踪</span><span class="sxs-lookup"><span data-stu-id="6c07b-143">Tracking</span></span>  
>   -   <span data-ttu-id="6c07b-144">BAM 的声明性使用</span><span class="sxs-lookup"><span data-stu-id="6c07b-144">Declarative use of BAM</span></span>  
  
 <span data-ttu-id="6c07b-145">有关不能从业务流程中执行的管道的类型的详细信息，请参阅本主题的"限制"部分[如何使用表达式来执行管道](http://go.microsoft.com/fwlink/?LinkId=158008)(http://go.microsoft.com/fwlink/?LinkId=158008) BizTalk Server 中2010 的文档。</span><span class="sxs-lookup"><span data-stu-id="6c07b-145">For more information about the types of pipelines that cannot be executed from within an orchestration, see the “Restrictions” section of the topic [How to Use Expressions to Execute Pipelines](http://go.microsoft.com/fwlink/?LinkId=158008) (http://go.microsoft.com/fwlink/?LinkId=158008) in the BizTalk Server 2010 documentation.</span></span>  
  
### <a name="optimize-orchestration-latency-by-reducing-the-number-of-persistence-points-if-possible"></a><span data-ttu-id="6c07b-146">通过尽可能减少持久化点的数量来优化业务流程的延迟</span><span class="sxs-lookup"><span data-stu-id="6c07b-146">Optimize orchestration latency by reducing the number of persistence points, if possible</span></span>  
 <span data-ttu-id="6c07b-147">业务流程作用域只需将其标记为"长时间运行的事务"如果你想要使用补偿或作用域超时。</span><span class="sxs-lookup"><span data-stu-id="6c07b-147">An orchestration scope only needs to be marked as “long-running transactional” if you want to use compensation or scope timeouts.</span></span> <span data-ttu-id="6c07b-148">长时间运行的事务作用域会导致末尾的作用域，一个额外的持久性点，因此它们不需要使用补偿或作用域超时时应避免使用。</span><span class="sxs-lookup"><span data-stu-id="6c07b-148">A long-running transactional scope causes an extra persistence point at the end of the scope, so they should be avoided when you don’t need to use compensation or scope timeouts.</span></span> <span data-ttu-id="6c07b-149">原子作用域将导致暂留点末尾的范围，但还可确保不暂留点会在原子作用域内。</span><span class="sxs-lookup"><span data-stu-id="6c07b-149">An atomic scope causes a persistence point at the end of the scope, but also guarantees that no persistence points will occur inside the atomic scope.</span></span> <span data-ttu-id="6c07b-150">（执行多个发送时，例如），有时可以对你来说批处理持久化点使用该范围中没有持久性此副作用。</span><span class="sxs-lookup"><span data-stu-id="6c07b-150">This side-effect of no persistence inside the scope can sometimes be used to your advantage to batch persistence points (when doing multiple sends, for example).</span></span> <span data-ttu-id="6c07b-151">一般情况下，不过，我们建议尽量避免原子作用域。</span><span class="sxs-lookup"><span data-stu-id="6c07b-151">In general, though, we recommend avoiding atomic scopes if possible.</span></span> <span data-ttu-id="6c07b-152">业务流程引擎将保存到持久性存储区的不同位置，正在运行的业务流程实例的整个状态，以便实例更高版本可以还原在内存中并执行到完成。</span><span class="sxs-lookup"><span data-stu-id="6c07b-152">The orchestration engine saves to persistent storage the entire state of a running orchestration instance at various points, so that the instance can later be restored in memory and carried out to completion.</span></span>   
<span data-ttu-id="6c07b-153">**在业务流程中的暂留点数目是影响源源不断地流经整个业务流程的消息的延迟的关键因素之一**。</span><span class="sxs-lookup"><span data-stu-id="6c07b-153">**The number of persistence points in an orchestration is one of the key factors influencing the latency of messages flowing through orchestrations**.</span></span> <span data-ttu-id="6c07b-154">引擎遇到持久点时，每次运行的业务流程的内部状态是序列化保存到 MessageBox 和此操作所产生的延迟开销。</span><span class="sxs-lookup"><span data-stu-id="6c07b-154">Each time the engine hits a persistence point, the internal state of a running orchestration is serialized and saved to the MessageBox and this operation incurs a latency cost.</span></span> <span data-ttu-id="6c07b-155">序列化的内部状态包括的所有消息和实例化但尚未发布业务流程中的变量。</span><span class="sxs-lookup"><span data-stu-id="6c07b-155">The serialization of the internal state includes all messages and variables instantiated and not yet released in the orchestration.</span></span> <span data-ttu-id="6c07b-156">较大的消息和变量和其中的越多，就越长以保持业务流程的内部状态。</span><span class="sxs-lookup"><span data-stu-id="6c07b-156">The larger the messages and variables and the greater the number of these, the longer it will take to persist the internal state of an orchestration.</span></span> <span data-ttu-id="6c07b-157">持久化点的次数过多可能会导致性能明显下降。</span><span class="sxs-lookup"><span data-stu-id="6c07b-157">An excessive number of persistence points can lead to significant performance degradation.</span></span> <span data-ttu-id="6c07b-158">出于此原因，我们建议通过减少事务作用域的数量来消除不必要的持久化点从业务流程和发送形状。</span><span class="sxs-lookup"><span data-stu-id="6c07b-158">For this reason, we recommend eliminating unnecessary persistence points from orchestrations by reducing the number of transactional scopes and Send shapes.</span></span> <span data-ttu-id="6c07b-159">此方法允许减少提高整体可伸缩性，并降低了业务流程延迟业务流程冻结和解除冻结，由于 MessageBox 上的争用现象。</span><span class="sxs-lookup"><span data-stu-id="6c07b-159">This approach allows decreasing the contention on the MessageBox due to orchestration dehydration and rehydration, increasing the overall scalability, and reducing orchestration latency.</span></span>   
<span data-ttu-id="6c07b-160">另一条建议是始终保持业务流程的内部状态越小越好。</span><span class="sxs-lookup"><span data-stu-id="6c07b-160">Another recommendation is to always keep the internal state of an orchestration as small as possible.</span></span> <span data-ttu-id="6c07b-161">此技术可以显著减少 XLANG 引擎序列化、 保存和还原业务流程持久化点时的内部状态所用的时间。</span><span class="sxs-lookup"><span data-stu-id="6c07b-161">This technique can significantly reduce the time spent by the XLANG Engine serializing, persisting and restoring the internal state of an orchestration in case of persistence point.</span></span> <span data-ttu-id="6c07b-162">若要实现此目的的一种方法是尽可能创建变量和晚消息并发布它们尽早尽可能;例如引入了在您的业务流程内的非事务性作用域，并声明变量和这些内部作用域，而不是在最顶层级别声明它们中的消息。</span><span class="sxs-lookup"><span data-stu-id="6c07b-162">One way to achieve this is to create variables and messages as late as possible and release them as early as possible; for example introduce non transactional scopes inside your orchestrations and declare variables and messages within these inner scopes instead of declaring them at the top-most level.</span></span> <span data-ttu-id="6c07b-163">最大程度减少业务流程持久化点的详细信息，请参阅 BizTalk Server 2010 文档中的以下主题：</span><span class="sxs-lookup"><span data-stu-id="6c07b-163">For more information about minimizing orchestration persistence points, see the following topics in the BizTalk Server  2010 documentation:</span></span>  
  
-   <span data-ttu-id="6c07b-164">[持久化和业务流程引擎](http://go.microsoft.com/fwlink/?LinkID=155292)(http://go.microsoft.com/fwlink/?LinkID=155292)。</span><span class="sxs-lookup"><span data-stu-id="6c07b-164">[Persistence and the Orchestration Engine](http://go.microsoft.com/fwlink/?LinkID=155292) (http://go.microsoft.com/fwlink/?LinkID=155292).</span></span>  
  
-   <span data-ttu-id="6c07b-165">[业务流程冻结和解除冻结](http://go.microsoft.com/fwlink/?LinkID=155284)(http://go.microsoft.com/fwlink/?LinkID=155292)。</span><span class="sxs-lookup"><span data-stu-id="6c07b-165">[Orchestration Dehydration and Rehydration](http://go.microsoft.com/fwlink/?LinkID=155284) (http://go.microsoft.com/fwlink/?LinkID=155292).</span></span>  
  
## <a name="guidelines-for-using-promoted-properties-to-access-message-tags-or-attributes-from-an-orchestration"></a><span data-ttu-id="6c07b-166">使用指南的已提升属性访问消息标记或属性从业务流程</span><span class="sxs-lookup"><span data-stu-id="6c07b-166">Guidelines for using promoted properties to access message tags or attributes from an orchestration</span></span>  
 <span data-ttu-id="6c07b-167">如果您确实需要升级属性，将提升用于消息路由、 筛选器和消息关联的那些属性。</span><span class="sxs-lookup"><span data-stu-id="6c07b-167">If you do need to promote properties, promote only those properties that are used for message routing, filters, and message correlation.</span></span> <span data-ttu-id="6c07b-168">每个属性的升级要求的拆装器组件 （XML、 平面的自定义） 来确认文档类型以及从使用 XPath 表达式从相对的批注的 XSD 的文档类型定义中包含的消息中检索数据。</span><span class="sxs-lookup"><span data-stu-id="6c07b-168">The promotion of each property requires the disassembler component (XML, Flat, custom) to recognize the document type and to retrieve data from the message using the XPath expression from the relative annotation contained in the XSD that defines the document type.</span></span> <span data-ttu-id="6c07b-169">此外，每个属性升级会导致单独 bts_InsertProperty 存储过程的调用时消息代理将消息发布到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="6c07b-169">In addition, each property promotion causes a separate call of the bts_InsertProperty stored procedure when the Message Agent publishes the message to the MessageBox database.</span></span> <span data-ttu-id="6c07b-170">如果业务流程需要访问的特定元素或特性所包含的 XML 文档，请使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="6c07b-170">If an orchestration needs to access a particular element or attribute contained by an XML document, use one of the following techniques:</span></span>  
  
- <span data-ttu-id="6c07b-171">减少写入和升级的属性数目并消除那些不是必需的。</span><span class="sxs-lookup"><span data-stu-id="6c07b-171">Reduce the number of written and promoted properties and eliminate those that are not strictly necessary.</span></span>  
  
- <span data-ttu-id="6c07b-172">消除不必要的可分辨的字段。</span><span class="sxs-lookup"><span data-stu-id="6c07b-172">Eliminate unnecessary distinguished fields.</span></span> <span data-ttu-id="6c07b-173">可分辨的字段将写入上下文属性，它们可轻松地会占用很多空间，如其名称等于用于检索数据的 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="6c07b-173">The distinguished fields are written context properties and they can easily occupy significant space as their name is equal to the XPath expression that is used to retrieve data.</span></span> <span data-ttu-id="6c07b-174">可分辨的属性定义为中定义的文档类型的 XSD 的批注。</span><span class="sxs-lookup"><span data-stu-id="6c07b-174">The distinguished property is defined as annotations in the XSD that defines the document type.</span></span> <span data-ttu-id="6c07b-175">拆装器组件使用相同的方法应用于升级的属性，并使用定义的可分辨的字段中查找传入文档中的 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="6c07b-175">The disassembler component uses the same approach adopted for promoted properties and uses the XPath expression that defines a distinguished field to find it within in the incoming document.</span></span> <span data-ttu-id="6c07b-176">然后，拆装器组件将属性写入上下文中其中：</span><span class="sxs-lookup"><span data-stu-id="6c07b-176">Then, the disassembler component writes a property in the context where:</span></span>  
  
  - <span data-ttu-id="6c07b-177">**名称**：在批注中定义的 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="6c07b-177">**Name**: XPath Expression defined in the annotation.</span></span>  
  
  - <span data-ttu-id="6c07b-178">“值”：通过传入文档中的 XPath 表达式标识的元素的值。</span><span class="sxs-lookup"><span data-stu-id="6c07b-178">**Value**: Value of the element identified by the XPath expression within an incoming document.</span></span>  
  
    <span data-ttu-id="6c07b-179">XPath 表达式可以是很长，尤其是当涉及的元素是非常深的文档架构中。</span><span class="sxs-lookup"><span data-stu-id="6c07b-179">The XPath Expressions can be very long, especially when the element in question is very deep in the document schema.</span></span> <span data-ttu-id="6c07b-180">因此，更可分辨字段，可查看大上下文大小。</span><span class="sxs-lookup"><span data-stu-id="6c07b-180">So, the more distinguished fields, the larger the context size.</span></span> <span data-ttu-id="6c07b-181">这进而产生负面影响的整体性能。</span><span class="sxs-lookup"><span data-stu-id="6c07b-181">This in turn adversely affects the overall performance.</span></span>  
  
- <span data-ttu-id="6c07b-182">使用业务流程运行时提供的内置 XPath 函数。</span><span class="sxs-lookup"><span data-stu-id="6c07b-182">Use the XPath built-in function provided by the orchestration runtime.</span></span>  
  
- <span data-ttu-id="6c07b-183">如果消息非常小 （几个千字节为单位） 和 XML 格式，可以取消消息序列化为.NET 类实例，并使用公共字段和属性。</span><span class="sxs-lookup"><span data-stu-id="6c07b-183">If messages are quite small (a few kilobytes) and XML-formatted, you can de-serialize the message into a .NET class instance and work with public fields and properties.</span></span> <span data-ttu-id="6c07b-184">如果消息需要复杂的细化 （自定义代码、 业务规则引擎策略等） 使用.NET 类的实例公开的属性来访问数据将快得多，使用 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="6c07b-184">If the message needs a complex elaboration (custom code, Business Rule Engine policies, etc.) accessing data using the properties exposed by an instance of a .NET class is much faster using XPath expressions.</span></span> <span data-ttu-id="6c07b-185">完成后调用的业务流程的业务逻辑，可以返回到 BizTalk 消息序列化实体对象。</span><span class="sxs-lookup"><span data-stu-id="6c07b-185">When the business logic invoked by the orchestration has completed, the entity object can be serialized back into a BizTalk message.</span></span> <span data-ttu-id="6c07b-186">可以从 XML 架构，使用以下工具之一创建.NET 类：XSD 工具 (.NET Framework 2.0) 或 SVCUTIL (.NET Framework 3.0)。</span><span class="sxs-lookup"><span data-stu-id="6c07b-186">You can create .NET classes from an XML schema using one of the following tools: XSD tool (.NET Framework 2.0) or SVCUTIL (.NET Framework 3.0).</span></span>  
  
- <span data-ttu-id="6c07b-187">启用从业务流程的帮助器组件。</span><span class="sxs-lookup"><span data-stu-id="6c07b-187">Enable a helper component from an orchestration.</span></span> <span data-ttu-id="6c07b-188">此方法有其优点使用可分辨的字段。</span><span class="sxs-lookup"><span data-stu-id="6c07b-188">This technique has an advantage over using distinguished fields.</span></span> <span data-ttu-id="6c07b-189">实际上，业务流程可以读取的 XPath 表达式从配置存储 （配置文件、 SSO 配置存储区、 自定义 Db 等），因此时必须更改 XPath 表达式，无需更改和重新部署架构，你应为升级的属性和 distinguished 字段。</span><span class="sxs-lookup"><span data-stu-id="6c07b-189">In fact, an orchestration may read the XPath expression from a config store (config file, SSO Config Store, custom Db, and so on) so, when you have to change the XPath expression, you do not have to change and redeploy a schema, as you should do for promoted properties and distinguished fields.</span></span> <span data-ttu-id="6c07b-190">下面的代码示例提供帮助器组件的示例。</span><span class="sxs-lookup"><span data-stu-id="6c07b-190">The following code sample provides an example of a helper component.</span></span> <span data-ttu-id="6c07b-191">该组件使用 BizTalk 运行时提供的 XPathReader 类。</span><span class="sxs-lookup"><span data-stu-id="6c07b-191">The component uses the XPathReader class that is provided by the BizTalk runtime.</span></span> <span data-ttu-id="6c07b-192">这使得代码可以读取整个文档流，直到找到 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="6c07b-192">This allows the code to read through the document stream until the XPath expression is found.</span></span>  
  
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
  
## <a name="minimize-orchestration-complexity-to-improve-performance"></a><span data-ttu-id="6c07b-193">最小化业务流程的复杂性以提高性能</span><span class="sxs-lookup"><span data-stu-id="6c07b-193">Minimize orchestration complexity to improve performance</span></span>  
 <span data-ttu-id="6c07b-194">业务流程的复杂性对性能有重大影响。</span><span class="sxs-lookup"><span data-stu-id="6c07b-194">The complexity of orchestrations has a significant impact on performance.</span></span> <span data-ttu-id="6c07b-195">随着业务流程的复杂性的增加，总体性能下降。</span><span class="sxs-lookup"><span data-stu-id="6c07b-195">As orchestration complexity increases, overall performance decreases.</span></span> <span data-ttu-id="6c07b-196">业务流程可以采用几近无限的各种方案，以及每个方案可能涉及的复杂程度各异的业务流程。</span><span class="sxs-lookup"><span data-stu-id="6c07b-196">Orchestrations can be used in an almost infinite variety of scenarios, and each scenario might involve orchestrations of varying complexity.</span></span> <span data-ttu-id="6c07b-197">避免复杂的业务流程在可能的情况以支持模块化方法。</span><span class="sxs-lookup"><span data-stu-id="6c07b-197">Avoid complex orchestrations when possible in favor of a modular approach.</span></span> <span data-ttu-id="6c07b-198">换而言之，将您的业务逻辑拆分为多个可重复使用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="6c07b-198">In other words, split your business logic into multiple, reusable orchestrations.</span></span>  
  
 <span data-ttu-id="6c07b-199">如果需要实现复杂的业务流程，定义消息和变量到内部作用域，只要有可能，而不是在根级别。</span><span class="sxs-lookup"><span data-stu-id="6c07b-199">If you do need to implement a complex orchestration, define messages and variables into inner scopes whenever possible rather than at the root level.</span></span> <span data-ttu-id="6c07b-200">此方法会保持在内存中为每个业务流程更小空间，因为变量和消息时，将释放的流离开已定义的变量和消息的作用域。</span><span class="sxs-lookup"><span data-stu-id="6c07b-200">This technique maintains a smaller footprint in memory for each orchestration because variables and messages are disposed of when the flow leaves the scope where the variables and messages were defined.</span></span> <span data-ttu-id="6c07b-201">如果业务流程将保存到 MessageBox 持久化点时，此方法非常尤为有益。</span><span class="sxs-lookup"><span data-stu-id="6c07b-201">This approach is particularly beneficial when orchestrations are saved to the MessageBox at persistence points.</span></span>  
  
## <a name="use-the-call-orchestration-shape-versus-the-start-orchestration-shape-to-improve-performance"></a><span data-ttu-id="6c07b-202">使用与启动业务流程形状调用业务流程形状可提高性能</span><span class="sxs-lookup"><span data-stu-id="6c07b-202">Use the Call Orchestration shape versus the Start Orchestration shape to improve performance</span></span>  
 <span data-ttu-id="6c07b-203">避免**启动业务流程**形状，然后使用**调用业务流程**形状执行嵌套的业务流程。</span><span class="sxs-lookup"><span data-stu-id="6c07b-203">Avoid the **Start Orchestration** shape and use the **Call Orchestration** shape to execute a nested orchestration.</span></span> <span data-ttu-id="6c07b-204">事实上，**调用业务流程**形状可用于同步调用另一个项目中引用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="6c07b-204">In fact, The **Call Orchestration** shape can be used to synchronously call an orchestration that is referenced in another project.</span></span> <span data-ttu-id="6c07b-205">此方法以供重复使用的常见业务流程工作流模式允许多个 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="6c07b-205">This approach allows for reuse of common orchestration workflow patterns across BizTalk projects.</span></span> <span data-ttu-id="6c07b-206">调用以同步方式与另一个嵌套的业务流程时**调用业务流程**形状，封闭的业务流程将等待嵌套的业务流程完成后才能继续。</span><span class="sxs-lookup"><span data-stu-id="6c07b-206">When you invoke another nested orchestration synchronously with the **Call Orchestration** shape, the enclosing orchestration waits for the nested orchestration to finish before continuing.</span></span> <span data-ttu-id="6c07b-207">嵌套的业务流程调用业务流程运行在同一线程上执行。</span><span class="sxs-lookup"><span data-stu-id="6c07b-207">The nested orchestration is executed on the same thread that runs the calling orchestration.</span></span>  
  
 <span data-ttu-id="6c07b-208">**启动业务流程**形状是类似于**调用业务流程**形状，但在这种情况下以异步方式调用嵌套的业务流程： 中调用的控制流业务流程将继续调用，而无需等待调用的业务流程完成其工作。</span><span class="sxs-lookup"><span data-stu-id="6c07b-208">The **Start Orchestration** shape is similar to the **Call Orchestration** shape, but in this case the nested orchestration is called in an asynchronous manner: the flow of control in the invoking orchestration proceeds beyond the invocation, without waiting for the invoked orchestration to finish its work.</span></span> <span data-ttu-id="6c07b-209">为了实现之间调用方和被调用的业务流程，这种分离**启动业务流程**通过发布到 BizTalk Messagebox 的消息实现的。</span><span class="sxs-lookup"><span data-stu-id="6c07b-209">In order to implement this decoupling between the caller and the called orchestrations, the **Start Orchestration** is implemented via publication of a message to the BizTalk Messagebox.</span></span> <span data-ttu-id="6c07b-210">然后，执行嵌套的业务流程的进程内 BizTalk 主机实例可使用此消息。</span><span class="sxs-lookup"><span data-stu-id="6c07b-210">This message is then consumed by an in-process BizTalk host instance which executes the nested orchestration.</span></span> <span data-ttu-id="6c07b-211">如果可能，请使用**调用业务流程**，特别是当调用业务流程需要等待才能继续处理从嵌套的业务流程的结果。</span><span class="sxs-lookup"><span data-stu-id="6c07b-211">When possible, use **Call Orchestration**, especially if the calling orchestration needs to wait for a result from the nested orchestration in order to continue processing.</span></span>  <span data-ttu-id="6c07b-212">有关使用调用业务流程形状的详细信息，请参阅 BizTalk Server 2010 文档中的以下主题：</span><span class="sxs-lookup"><span data-stu-id="6c07b-212">For more information about using the Call Orchestration shape, see the following topics in the BizTalk Server 2010 documentation:</span></span>  
  
-   <span data-ttu-id="6c07b-213">[使用在业务流程直接绑定端口](http://go.microsoft.com/fwlink/?LinkId=139902)(http://go.microsoft.com/fwlink/?LinkId=139902)。</span><span class="sxs-lookup"><span data-stu-id="6c07b-213">[Working with Direct Bound Ports in Orchestrations](http://go.microsoft.com/fwlink/?LinkId=139902) (http://go.microsoft.com/fwlink/?LinkId=139902).</span></span>  
  
-   <span data-ttu-id="6c07b-214">[嵌套业务流程](http://go.microsoft.com/fwlink/?LinkId=139903)(http://go.microsoft.com/fwlink/?LinkId=139903)。</span><span class="sxs-lookup"><span data-stu-id="6c07b-214">[Nesting Orchestrations](http://go.microsoft.com/fwlink/?LinkId=139903) (http://go.microsoft.com/fwlink/?LinkId=139903).</span></span>  
  
## <a name="use-xmlreader-with-xlangmessage-versus-using-xmlreader-with-xmldocument-to-improve-orchestration-performance"></a><span data-ttu-id="6c07b-215">XmlReader 使用 XLANGMessage 与使用和 XmlDocument XmlReader 来提高业务流程性能</span><span class="sxs-lookup"><span data-stu-id="6c07b-215">Use XmlReader with XLANGMessage versus using XmlReader with XmlDocument to improve orchestration performance</span></span>  
 <span data-ttu-id="6c07b-216">若要提高.NET 方法从业务流程调用的业务流程性能，请将 XmlReader 使用 XLANGMessage，不 XmlDocument。</span><span class="sxs-lookup"><span data-stu-id="6c07b-216">To improve orchestration performance for .NET methods called from an orchestration, use XmlReader with XLANGMessage, not XmlDocument.</span></span> <span data-ttu-id="6c07b-217">下面的代码示例说明了此功能。</span><span class="sxs-lookup"><span data-stu-id="6c07b-217">The following code example illustrates this functionality.</span></span>  
  
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
  
 <span data-ttu-id="6c07b-218">另一种方法就是创建基于架构的.NET 类。</span><span class="sxs-lookup"><span data-stu-id="6c07b-218">Another method would be to create a .NET class based on the schema.</span></span> <span data-ttu-id="6c07b-219">这会占用较少内存比加载到文档**XmlDocument**对象，以及面向.NET 开发人员提供轻松访问的架构元素。</span><span class="sxs-lookup"><span data-stu-id="6c07b-219">This takes less memory than loading the document into an **XmlDocument** object, as well as providing easy access to the schema elements for .NET developers.</span></span> <span data-ttu-id="6c07b-220">若要生成基于 BizTalk 架构的类，可以使用 xsd.exe 工具随 Visual Studio 一起提供。</span><span class="sxs-lookup"><span data-stu-id="6c07b-220">To generate a class based on a BizTalk schema, you can use the xsd.exe tool provided with Visual Studio.</span></span> <span data-ttu-id="6c07b-221">例如，运行**xsd.exe \<schema.xsd\> /classes** ItemB，ItemC，将针对简单架构，其中包含名为 ItemA 的字段，生成下面的类。</span><span class="sxs-lookup"><span data-stu-id="6c07b-221">For example, running **xsd.exe \<schema.xsd\> /classes** against a simple schema containing fields named ItemA, ItemB, ItemC, will produce the following class.</span></span>  
  
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
  
 <span data-ttu-id="6c07b-222">此类，可以引用.NET 程序集才能访问消息元素，并返回的对象可以直接分配到一条消息。</span><span class="sxs-lookup"><span data-stu-id="6c07b-222">This class can then be referenced in your .NET assembly in order to access the message elements, and the returned object can be directly assigned to a message.</span></span> <span data-ttu-id="6c07b-223">下面是类的上述生成的示例用法。</span><span class="sxs-lookup"><span data-stu-id="6c07b-223">The following is an example use of the class generated above.</span></span>  
  
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
  
 <span data-ttu-id="6c07b-224">此技术，可处理消息时使用的面向对象的方法。</span><span class="sxs-lookup"><span data-stu-id="6c07b-224">This technique allows you to use an object-oriented approach when processing messages.</span></span> <span data-ttu-id="6c07b-225">此方法应主要用于相对较小的消息。</span><span class="sxs-lookup"><span data-stu-id="6c07b-225">This technique should be used primarily with relatively small messages.</span></span> <span data-ttu-id="6c07b-226">这是因为即使此方法使用少得多的内存比时加载到的消息**XmlDocument**对象，整个消息，仍将加载到内存。</span><span class="sxs-lookup"><span data-stu-id="6c07b-226">This is because even though this technique uses considerably less memory than when loading the message into an **XmlDocument** object, the entire message is still loaded into memory.</span></span> <span data-ttu-id="6c07b-227">在处理较大的消息时，使用**XmlReader**类，以读取消息并**XmlWriter**类将消息写入。</span><span class="sxs-lookup"><span data-stu-id="6c07b-227">When processing larger messages, use the **XmlReader** class to read messages and the **XmlWriter** class to write messages.</span></span> <span data-ttu-id="6c07b-228">使用时**XmlReader**并**XmlWriter**，该消息包含在**为 VirtualStream**对象。</span><span class="sxs-lookup"><span data-stu-id="6c07b-228">When using **XmlReader** and **XmlWriter**, the message is contained in a **VirtualStream** object.</span></span> <span data-ttu-id="6c07b-229">如果消息大小超出了为指定的值**大消息阈值 （字节）** 公开 BizTalk 组属性配置页上，将消息写入到文件系统。</span><span class="sxs-lookup"><span data-stu-id="6c07b-229">If the message size exceeds the value specified for **Large message threshold (bytes)** that is exposed on the BizTalk Group Properties configuration page, the message is written to the file system.</span></span> <span data-ttu-id="6c07b-230">这会降低整体性能，但可以避免内存不足异常。</span><span class="sxs-lookup"><span data-stu-id="6c07b-230">This decreases overall performance, but avoids out of memory exceptions.</span></span>  
  
## <a name="improve-performance-by-minimizing-the-use-of-logical-ports-bound-to-physical-ports"></a><span data-ttu-id="6c07b-231">通过最小化的逻辑端口绑定到物理端口的使用来提高性能</span><span class="sxs-lookup"><span data-stu-id="6c07b-231">Improve performance by minimizing the use of logical ports bound to physical ports</span></span>  
 <span data-ttu-id="6c07b-232">可以通过尽量少使用的逻辑端口绑定到使用以下适配器的物理端口来提高性能：</span><span class="sxs-lookup"><span data-stu-id="6c07b-232">You can increase performance by minimizing the use of logical ports bound to physical ports that use the following adapters:</span></span>  
  
- <span data-ttu-id="6c07b-233">SQL Server、 Oracle</span><span class="sxs-lookup"><span data-stu-id="6c07b-233">SQL Server, Oracle</span></span>  
  
- <span data-ttu-id="6c07b-234">WSE，HTTP，WCF</span><span class="sxs-lookup"><span data-stu-id="6c07b-234">WSE, HTTP, WCF</span></span>  
  
- <span data-ttu-id="6c07b-235">MSMQ, MQSeries</span><span class="sxs-lookup"><span data-stu-id="6c07b-235">MSMQ, MQSeries</span></span>  
  
  <span data-ttu-id="6c07b-236">在 BizTalk Server 2010 中，发送和接收管道可以从业务流程使用 XLANGPipelineManager 类包含在 Microsoft.XLANGs.Pipeline.dll 直接调用。</span><span class="sxs-lookup"><span data-stu-id="6c07b-236">In BizTalk Server 2010, send and receive pipelines can be directly invoked from an orchestration using the XLANGPipelineManager class contained in the Microsoft.XLANGs.Pipeline.dll.</span></span> <span data-ttu-id="6c07b-237">因此，管道处理可以在端口间移动业务流程;具有表达式形状，调用给定的.NET 类的实例 （例如，使用 ADO.NET 数据访问组件），才能替代业务流程中的逻辑端口。</span><span class="sxs-lookup"><span data-stu-id="6c07b-237">Thus, the processing of pipelines can be moved from ports to orchestrations; logical ports in an orchestration can be substituted with an Expression shape, which invokes an instance of a given .NET class (for example, a Data Access component using ADO.NET).</span></span> <span data-ttu-id="6c07b-238">采用这种技术之前, 应注意，如果不使用适配器和物理端口，您会失去能够充分利用其函数，如批处理、 重试次数、 声明性配置和辅助传输。</span><span class="sxs-lookup"><span data-stu-id="6c07b-238">Before adopting this technique, you should be aware that if you do not use adapters and physical ports, you lose the ability to leverage their functions, such as batching, retries, declarative configuration, and secondary transports.</span></span>  
  
## <a name="orchestration-design-patterns"></a><span data-ttu-id="6c07b-239">业务流程设计模式</span><span class="sxs-lookup"><span data-stu-id="6c07b-239">Orchestration Design Patterns</span></span>  
 <span data-ttu-id="6c07b-240">业务流程设计器允许开发人员实现范围广泛的企业集成模式。</span><span class="sxs-lookup"><span data-stu-id="6c07b-240">The Orchestration Designer allows developers to implement a wide range of enterprise integration patterns.</span></span> <span data-ttu-id="6c07b-241">一些常见模式包括聚合器、 异常处理和补偿、 消息中转站、 散点图和收集，并按顺序和并行保护。</span><span class="sxs-lookup"><span data-stu-id="6c07b-241">Some common patterns include Aggregator, Exception Handling and Compensation, Message Broker, Scatter and Gather, and Sequential and Parallel Convoy.</span></span> <span data-ttu-id="6c07b-242">可以利用这些模式开发复杂的企业应用程序集成 (EAI)、 面向服务体系结构 (SOA) 和业务流程管理 (BPM) 解决方案与 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="6c07b-242">Those patterns can be utilized to develop complex Enterprise Application Integration (EAI), Service-Oriented Architecture (SOA), and Business Process Management (BPM) solutions with BizTalk Server.</span></span> <span data-ttu-id="6c07b-243">有关业务流程设计模式的详细信息，请参阅主题[业务流程中实现设计模式](http://go.microsoft.com/fwlink/?LinkId=140042)(http://go.microsoft.com/fwlink/?LinkId=140042) BizTalk Server 文档中和[模式和最佳实践企业集成](http://go.microsoft.com/fwlink/?LinkId=140043)(http://go.microsoft.com/fwlink/?LinkId=140043)。</span><span class="sxs-lookup"><span data-stu-id="6c07b-243">For more information about Orchestration Design Patterns, see the topic [Implementing Design Patterns in Orchestrations](http://go.microsoft.com/fwlink/?LinkId=140042) (http://go.microsoft.com/fwlink/?LinkId=140042) in the BizTalk Server documentation and [Patterns and Best Practices for Enterprise Integration](http://go.microsoft.com/fwlink/?LinkId=140043) (http://go.microsoft.com/fwlink/?LinkId=140043).</span></span>  
  
## <a name="make-appropriate-use-of-net-classes-in-orchestrations-to-maximize-performance"></a><span data-ttu-id="6c07b-244">在业务流程来使性能最大化中进行适当使用.NET 类</span><span class="sxs-lookup"><span data-stu-id="6c07b-244">Make appropriate use of .NET classes in orchestrations to maximize performance</span></span>  
 <span data-ttu-id="6c07b-245">一般情况下，在业务流程内部使用的.NET 类可以分为两个不同类别：</span><span class="sxs-lookup"><span data-stu-id="6c07b-245">In general, the .NET classes used inside an orchestration can be divided into two distinct categories:</span></span>  
  
-   <span data-ttu-id="6c07b-246">**帮助程序和服务-** 这些类提供常见服务添加到业务流程，例如跟踪、 错误处理、 缓存和序列化/反序列化。</span><span class="sxs-lookup"><span data-stu-id="6c07b-246">**Helpers and services -** These classes provide common services to orchestrations such as tracing, error handling, caching, and serialization/deserialization.</span></span> <span data-ttu-id="6c07b-247">大多数这些类可以作为与没有内部状态和多个公共静态方法的静态类实现。</span><span class="sxs-lookup"><span data-stu-id="6c07b-247">Most of these classes can be implemented as static classes with no internal state and multiple public static methods.</span></span> <span data-ttu-id="6c07b-248">此方法可避免在不同的业务流程运行在同一时间，有助于减少主机进程的工作空间，并节省内存中创建的同一个类的多个对象。</span><span class="sxs-lookup"><span data-stu-id="6c07b-248">This approach avoids creating multiple objects of the same class in different orchestrations running at the same time, which helps to reduce the working space of host processes and save memory.</span></span> <span data-ttu-id="6c07b-249">无状态的类有助于减少必须序列化和业务流程会被冻结时保存到 BizTalk MessageBox 的内部状态的总体大小。</span><span class="sxs-lookup"><span data-stu-id="6c07b-249">A class that is stateless helps to reduce the overall size of the internal state that must be serialized and persisted to the BizTalk MessageBox when an orchestration is dehydrated.</span></span>  
  
-   <span data-ttu-id="6c07b-250">**实体和业务对象-** 可以使用这些类来管理实体，例如订单、 订单项和客户。</span><span class="sxs-lookup"><span data-stu-id="6c07b-250">**Entities and Business Objects -** You can use these classes to manage entities, such as orders, order items, and customers.</span></span> <span data-ttu-id="6c07b-251">单个业务流程可以在内部创建和管理多个相同类型的实例。</span><span class="sxs-lookup"><span data-stu-id="6c07b-251">A single orchestration can internally create and manage multiple instances of the same type.</span></span> <span data-ttu-id="6c07b-252">这些类通常有状态，并公开公共字段和/或属性及方法来修改该对象的内部状态。</span><span class="sxs-lookup"><span data-stu-id="6c07b-252">These classes are typically stateful, and expose public fields and/or properties along with methods to modify the internal state of the object.</span></span> <span data-ttu-id="6c07b-253">这些类的实例可以动态创建的反 XLANGMessage 部分序列化为.NET 对象，通过使用**XmlSerializer**或**DataContractSerializer**类或通过使用**XLANGPart.RetrieveAs**方法。</span><span class="sxs-lookup"><span data-stu-id="6c07b-253">Instances of these classes can be dynamically created by deserializing an XLANGMessage part into a .NET object by using the **XmlSerializer** or the **DataContractSerializer** classes or by using the **XLANGPart.RetrieveAs** method.</span></span> <span data-ttu-id="6c07b-254">您应构建业务流程使用有状态的类的实例的创建尽可能晚和不再需要后，即可释放方式中的非事务性作用域。</span><span class="sxs-lookup"><span data-stu-id="6c07b-254">You should structure an orchestration using non-transactional scopes in such a way that instances of stateful classes are created as late as possible and released as soon as they are no longer needed.</span></span> <span data-ttu-id="6c07b-255">这种方法可以减少主机进程的工作空间并最小化的序列化并保存到 MessageBox 数据库中已冻结业务流程时的内部状态的总体大小。</span><span class="sxs-lookup"><span data-stu-id="6c07b-255">This approach reduces the working space of host processes and minimizes the overall size of the internal state that is serialized and persisted to the MessageBox database when an orchestration is dehydrated.</span></span> <span data-ttu-id="6c07b-256">有关 BizTalk Server 中使用业务流程的详细信息，请参阅文章[BizTalk Server 业务流程的常见问题解答](http://go.microsoft.com/fwlink/?LinkID=116886)(http://go.microsoft.com/fwlink/?LinkID=116886)。</span><span class="sxs-lookup"><span data-stu-id="6c07b-256">For more information about using orchestrations in BizTalk Server, see the article [FAQ for BizTalk Server Orchestrations](http://go.microsoft.com/fwlink/?LinkID=116886) (http://go.microsoft.com/fwlink/?LinkID=116886).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6c07b-257">尽管这篇文章编写的 BizTalk Server 2004 和 BizTalk Server 2006 中，介绍的概念也适用于 BizTalk Server 2010 的业务流程。</span><span class="sxs-lookup"><span data-stu-id="6c07b-257">While this article is written for BizTalk Server 2004 and BizTalk Server 2006, the concepts presented also apply to BizTalk Server 2010 orchestrations.</span></span>  
  
## <a name="orchestration-exception-handler-blocks"></a><span data-ttu-id="6c07b-258">业务流程的异常处理程序块</span><span class="sxs-lookup"><span data-stu-id="6c07b-258">Orchestration Exception Handler Blocks</span></span>  
 <span data-ttu-id="6c07b-259">使用业务流程的异常处理程序块时，在一个或多个作用域 （非事务性作用域应尽可能） 中包含所有业务流程形状，并至少创建以下异常处理程序块：</span><span class="sxs-lookup"><span data-stu-id="6c07b-259">When using Orchestration exception Handler blocks, include all orchestration shapes in one or multiple scopes (non transactional scopes whenever possible) and create at least the following exception handler blocks:</span></span>  
  
- <span data-ttu-id="6c07b-260">异常处理程序块用于处理一般的 System.Exception 错误。</span><span class="sxs-lookup"><span data-stu-id="6c07b-260">An exception handler block for handling a generic System.Exception error.</span></span>  
  
- <span data-ttu-id="6c07b-261">异常处理程序块用于处理常规异常以捕获和处理可能的非托管的错误，例如 COM 异常。</span><span class="sxs-lookup"><span data-stu-id="6c07b-261">An exception handler block for handling a general exception in order to catch and handle possible unmanaged errors, such as COM exceptions.</span></span>  
  
  <span data-ttu-id="6c07b-262">有关使用业务流程的异常处理块的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="6c07b-262">For more information about using Orchestration exception handling blocks, see the following articles:</span></span>  
  
- <span data-ttu-id="6c07b-263">[使用 BizTalk Server 异常处理](http://msdn.microsoft.com/library/aa561229.aspx)(http://msdn.microsoft.com/library/aa561229.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6c07b-263">[Using BizTalk Server Exception Handling](http://msdn.microsoft.com/library/aa561229.aspx) (http://msdn.microsoft.com/library/aa561229.aspx).</span></span>  
  
- <span data-ttu-id="6c07b-264">[Charles Young 博客，BizTalk Server 2006:补偿模型](http://go.microsoft.com/fwlink/?LinkId=158017)(http://go.microsoft.com/fwlink/?LinkId=158017)。</span><span class="sxs-lookup"><span data-stu-id="6c07b-264">[Charles Young Blog, BizTalk Server 2006: The Compensation Model](http://go.microsoft.com/fwlink/?LinkId=158017) (http://go.microsoft.com/fwlink/?LinkId=158017).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="6c07b-265">虽然此博客编写使用[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]的一点是，在博客中介绍的原则也适用于 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="6c07b-265">While this blog was written with [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] in mind, the principles described in the blog also apply to BizTalk Server.</span></span>  
  
## <a name="considerations-when-using-maps-in-orchestrations"></a><span data-ttu-id="6c07b-266">在业务流程中使用映射时的注意事项</span><span class="sxs-lookup"><span data-stu-id="6c07b-266">Considerations when using maps in orchestrations</span></span>  
 <span data-ttu-id="6c07b-267">在业务流程中使用映射时，应考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="6c07b-267">The following considerations apply when using maps in orchestrations:</span></span>  
  
-   <span data-ttu-id="6c07b-268">如果使用映射来提取或设置与一起使用的属性在业务流程中的业务逻辑使用可分辨的字段，或升级的属性。</span><span class="sxs-lookup"><span data-stu-id="6c07b-268">If you are using a map to extract or set properties used with business logic in an orchestration, use distinguished fields or promoted properties.</span></span> <span data-ttu-id="6c07b-269">应遵循这种做法，因为如果提取或设置文档的一个带有地图的值加载到内存但是时使用的可分辨字段或升级的属性，则业务流程引擎将访问消息上下文并不会加载到内存中的文档。</span><span class="sxs-lookup"><span data-stu-id="6c07b-269">This practice should be followed because when extracting or setting values with a map the document is loaded into memory however when using distinguished fields or promoted properties, the orchestration engine accesses the message context and does not load the document into memory.</span></span>  
  
-   <span data-ttu-id="6c07b-270">如果您使用映射将多个字段聚合为一个字段，请使用可分辨的字段或升级的属性与业务流程变量累积的结果集。</span><span class="sxs-lookup"><span data-stu-id="6c07b-270">If you are using a map to aggregate several fields into one field, use distinguished fields or promoted properties with an orchestration variable to accumulate the result set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c07b-271">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c07b-271">See Also</span></span>  
 [<span data-ttu-id="6c07b-272">优化性能</span><span class="sxs-lookup"><span data-stu-id="6c07b-272">Optimizing Performance</span></span>](../technical-guides/optimizing-performance.md)