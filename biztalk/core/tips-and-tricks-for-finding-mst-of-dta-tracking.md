---
title: "查找 MST DTA 跟踪的提示和技巧 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d72e4ac-d952-4cff-9a65-491e20945d40
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9faaaf7ebb47ac7ec18d8df6d8cb7c6ebd48d7f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tips-and-tricks-for-finding-mst-of-dta-tracking"></a><span data-ttu-id="f03ba-102">确定 DTA 跟踪的 MST 的提示与技巧</span><span class="sxs-lookup"><span data-stu-id="f03ba-102">Tips and Tricks for Finding MST of DTA Tracking</span></span>
<span data-ttu-id="f03ba-103">按照定义，MST 是使用恒负载以可重现方式度量系统性能的基准。</span><span class="sxs-lookup"><span data-stu-id="f03ba-103">By definition, MST is a benchmark to reproducibly measure system performance using a constant load.</span></span> <span data-ttu-id="f03ba-104">在下面介绍的情形中，了解 MST 将非常有用。</span><span class="sxs-lookup"><span data-stu-id="f03ba-104">Following are situations where knowing the MST is particularly useful.</span></span>  
  
1.  <span data-ttu-id="f03ba-105">**如果需要从系统的最低延迟**。</span><span class="sxs-lookup"><span data-stu-id="f03ba-105">**When you require the lowest latency from the system**.</span></span> <span data-ttu-id="f03ba-106">超出 MST 将导致系统中出现积压，从而延长消息的延迟时间。</span><span class="sxs-lookup"><span data-stu-id="f03ba-106">Exceeding MST results in backlog in the system, which introduces increased latency for messages.</span></span> <span data-ttu-id="f03ba-107">即使积压只是暂时性的，也会立即对延迟时间产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="f03ba-107">Even if the backlog is only temporary, backlog has an immediate and deleterious effect on latency.</span></span> <span data-ttu-id="f03ba-108">因此，通过了解您的系统 MST，也就可以知道应该实现的绝对最大吞吐量，超出该吞吐量，处理单独消息的延迟时间将会显著延长（例如，根据您的配置，可能会从秒钟一级延长到分钟一级）。</span><span class="sxs-lookup"><span data-stu-id="f03ba-108">So, knowing your systems MST will tell you the absolute maximum throughput you should expect to achieve before the latency of individual message processing increases dramatically (for example, from seconds to minutes depending on your configuration).</span></span>  
  
2.  <span data-ttu-id="f03ba-109">**将与其他系统进行比较时**。</span><span class="sxs-lookup"><span data-stu-id="f03ba-109">**When comparing to other systems**.</span></span> <span data-ttu-id="f03ba-110">例如，如果您想要验证与其他系统（例如，本主题中的情形、案例研究或您的环境中的其他系统）相比是否实现了预期的 MST；使用稳定的输入度量 MST 将提供可重现的、明确的比较标准。</span><span class="sxs-lookup"><span data-stu-id="f03ba-110">For example, if you want to validate that you are achieving the expected MST compared to another system (for example, the scenario in this topic, a case study, or another system in your environment); measuring MST using a steady input offers a reproducible, unambiguous standard for comparison.</span></span>  
  
 <span data-ttu-id="f03ba-111">但无论如何，度量 MST 可能很耗时。</span><span class="sxs-lookup"><span data-stu-id="f03ba-111">Needless to say, however, it can be time consuming to measure MST.</span></span> <span data-ttu-id="f03ba-112">因此，在您花很大气力去进行度量之前，应该权衡利益。</span><span class="sxs-lookup"><span data-stu-id="f03ba-112">Therefore, before you embark on a lengthy exercise to measure it, you should evaluate the benefits.</span></span> <span data-ttu-id="f03ba-113">大多数生产系统都不会经历按 MST 度量的稳定的输入，其负载而是常常随时间变化。</span><span class="sxs-lookup"><span data-stu-id="f03ba-113">Most production systems will not experience a steady input such as that measured by MST, but rather a load that changes over time.</span></span> <span data-ttu-id="f03ba-114">必须在生产前对此负载状况进行最后测试以对系统进行验证。</span><span class="sxs-lookup"><span data-stu-id="f03ba-114">It is this load profile that must ultimately be tested to certify a system prior to production.</span></span> <span data-ttu-id="f03ba-115">幸运的是，您可以使用用于度量 MST 的相同技术来评估您的生产负载状况的可持续性。</span><span class="sxs-lookup"><span data-stu-id="f03ba-115">Fortunately, you can use the same technique that is used to measure MST to evaluate the sustainability of your production load profile.</span></span> <span data-ttu-id="f03ba-116">只需将负载状况保持足够长的时间，以便包括一个或两个 BizTalkDTADb 数据库数据保留时段，然后观察关键性能指标 (KPI)。</span><span class="sxs-lookup"><span data-stu-id="f03ba-116">Simply run your load profile long enough to include one or more BizTalkDTADb database data retention windows and observe the key performance indicators (KPI).</span></span>  
  
 <span data-ttu-id="f03ba-117">特别要注意的是，应该使用一个空的 BizTalkDTADb 数据库来开始执行您的测试，无论是针对 MST 还是负载状况。</span><span class="sxs-lookup"><span data-stu-id="f03ba-117">It is important to start your test runs, whether MST or load profiles, with an empty BizTalkDTADb database.</span></span> <span data-ttu-id="f03ba-118">在 BizTalkDTADb 数据库中存储的数据是时间敏感数据；并且，如果数据不是每次测试一开始就再次获取的，则可能会导致测试结果出现偏差。</span><span class="sxs-lookup"><span data-stu-id="f03ba-118">The data that is stored in the BizTalkDTADb database is time sensitive and if it is not re-acquired from scratch for each test run, it can skew your results.</span></span> <span data-ttu-id="f03ba-119">根据您的数据保留时段，这可能会大幅增加确定 MST 所用的时间。</span><span class="sxs-lookup"><span data-stu-id="f03ba-119">Depending on your data retention window, this can significantly increase the time it takes to find MST.</span></span> <span data-ttu-id="f03ba-120">为了缓解这一问题，在执行测试期间实时调整负载可能有助于更快地关注 MST。</span><span class="sxs-lookup"><span data-stu-id="f03ba-120">To mitigate this, adjusting load "on the fly" during test runs can be useful in more quickly zeroing in on MST.</span></span>  
  
 <span data-ttu-id="f03ba-121">例如，如果您发现经过了第一个保留时段后，KPI 指示您的系统还有余量来承受更高的吞吐量（例如，磁盘空闲时间仍高于零），则可以渐次增加您的负载并观察结果。</span><span class="sxs-lookup"><span data-stu-id="f03ba-121">For example, if you find that you have passed your first retention window time and the KPIs indicate you have headroom for higher throughput left (for example, disk idle time is still above zero), you can incrementally increase your load and observe the effect.</span></span> <span data-ttu-id="f03ba-122">但在通过此方法优化您的 MST 评估后，务必要执行以空的 BizTalkDTADb 数据库开始的测试来验证您的评估。</span><span class="sxs-lookup"><span data-stu-id="f03ba-122">After you have refined your MST estimate in this way, however, it is important that you perform a test run starting with an empty BizTalkDTADb database to validate your estimate.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="f03ba-123">建议</span><span class="sxs-lookup"><span data-stu-id="f03ba-123">Recommendations</span></span>  
 <span data-ttu-id="f03ba-124">跟踪中的系统体系结构[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]能够跟踪各种信息，并且必须管理和密切监视。</span><span class="sxs-lookup"><span data-stu-id="f03ba-124">The tracking system architecture in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is capable of tracking a wide variety of information and must be managed and monitored carefully.</span></span> <span data-ttu-id="f03ba-125">MST 所指示的影响系统性能的最重要因素包括：</span><span class="sxs-lookup"><span data-stu-id="f03ba-125">The factors that will most affect the performance of your system, as indicated by MST, are as follows:</span></span>  
  
-   <span data-ttu-id="f03ba-126">系统的预期吞吐量。</span><span class="sxs-lookup"><span data-stu-id="f03ba-126">The desired throughput for the system.</span></span>  
  
-   <span data-ttu-id="f03ba-127">为系统中每个消息和服务实例跟踪的信息量。</span><span class="sxs-lookup"><span data-stu-id="f03ba-127">The volume of information tracked for each message and service instance in the system.</span></span> <span data-ttu-id="f03ba-128">这将确定 BizTalkDTADb 数据库大小增加的速度，并且最终确定必须清除 BizTalkDTADb 数据库以避免速度过慢的频率。</span><span class="sxs-lookup"><span data-stu-id="f03ba-128">This will determine how quickly the size of the BizTalkDTADb database increases, and ultimately how often the BizTalkDTADb database must be purged to avoid falling behind.</span></span>  
  
-   <span data-ttu-id="f03ba-129">您希望将数据在 BizTalkDTADb 数据库中保留多长时间，即，数据保留时段。</span><span class="sxs-lookup"><span data-stu-id="f03ba-129">How long you wish to retain data in the BizTalkDTADb database, that is, the data retention window.</span></span> <span data-ttu-id="f03ba-130">该时段越长，BizTalkDTADb 数据库就会增长得越大，并且对吞吐量造成影响。</span><span class="sxs-lookup"><span data-stu-id="f03ba-130">The longer the window, the larger the BizTalkDTADb database will grow, affecting throughput.</span></span>  
  
-   <span data-ttu-id="f03ba-131">您是将 BizTalkDTADb 数据库中的数据存档并且清除，还是只清除以保持 BizTalkDTADb 数据库大小。</span><span class="sxs-lookup"><span data-stu-id="f03ba-131">Whether you archive BizTalkDTADb database data as well as purge, or just purge to maintain BizTalkDTADb database size.</span></span>  
  
 <span data-ttu-id="f03ba-132">查找对其进行跟踪的最大可持续吞吐量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]涉及三个关键绩效指标：</span><span class="sxs-lookup"><span data-stu-id="f03ba-132">The process of finding the maximum sustainable throughput for tracking in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] involves three key performance indicators:</span></span>  
  
-   <span data-ttu-id="f03ba-133">DTAdb 数据文件磁盘子系统的物理磁盘空闲时间。</span><span class="sxs-lookup"><span data-stu-id="f03ba-133">Physical Disk Idle Time for the DTAdb data file disk subsystem.</span></span>  
  
-   <span data-ttu-id="f03ba-134">后台处理深度</span><span class="sxs-lookup"><span data-stu-id="f03ba-134">Spool depth</span></span>  
  
-   <span data-ttu-id="f03ba-135">BizTalkDTADbData 深度</span><span class="sxs-lookup"><span data-stu-id="f03ba-135">BizTalkDTADbData depth</span></span>  
  
 <span data-ttu-id="f03ba-136">通过监控这三个关键性能指标以便了解以下情况，确定您的系统的 MST 或者您的生产状况吞吐量：</span><span class="sxs-lookup"><span data-stu-id="f03ba-136">Find either your systems’ MST or validate your production profile throughput by monitoring these three key performance indicators looking for:</span></span>  
  
-   <span data-ttu-id="f03ba-137">稳定的后台处理和 trackingdata 表深度。</span><span class="sxs-lookup"><span data-stu-id="f03ba-137">Stable spool and trackingdata table depth.</span></span>  
  
-   <span data-ttu-id="f03ba-138">BizTalkDTADb 数据库数据文件磁盘物理空闲时间接近（但不持续稳定在）零。</span><span class="sxs-lookup"><span data-stu-id="f03ba-138">BizTalkDTADb database data file disk physical idle time near, but not continuously "pegged" at, zero.</span></span>  
  
 <span data-ttu-id="f03ba-139">使用 DTA 跟踪功能具有相关的性能影响。</span><span class="sxs-lookup"><span data-stu-id="f03ba-139">Using the DTA tracking features has an associated performance impact.</span></span>  <span data-ttu-id="f03ba-140">默认跟踪不仅仅可以跟踪在生产中使用解决方案所需的内容，还可以通过提供丰富的问题解决信息，使开发以及初始测试和调试更容易。</span><span class="sxs-lookup"><span data-stu-id="f03ba-140">Default tracking may track more than is needed once a solution is in production, but can make development and initial testing and debugging easier by providing ample problem resolution information.</span></span> <span data-ttu-id="f03ba-141">因此，我们建议将默认跟踪放在开发和初始测试期间进行。</span><span class="sxs-lookup"><span data-stu-id="f03ba-141">Therefore, we recommend that default tracking be left on during development and initial testing.</span></span> <span data-ttu-id="f03ba-142">一旦在 BizTalk 上部署的解决方案稳定并可供生产验证（包括性能测试）后，建议您仔细检查生产中需要跟踪的信息量，以及信息需要保留在 BizTalkDTADb 数据库中的时间长度并相应调整。</span><span class="sxs-lookup"><span data-stu-id="f03ba-142">Once a solution deployed on BizTalk is stable and ready for production certification, including performance testing, it is recommended that you carefully examine the amount of information that needs to be tracked in production, and the length of time it needs to be kept in the BizTalkDTADb database and adjust accordingly.</span></span>  
  
 <span data-ttu-id="f03ba-143">例如，如果无需出于不可否认目的或问题解决目的跟踪消息正文，则不要启用消息正文跟踪。</span><span class="sxs-lookup"><span data-stu-id="f03ba-143">For example, if message bodies do not need to be tracked for either non-repudiation or problem resolution purposes, then do not turn on message body tracking.</span></span> <span data-ttu-id="f03ba-144">为了说明这一点，在示例方案中所述[测量 MST DTA 跟踪的测试方案](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md)，当消息正文跟踪的跟踪配置的组件已消除，MST 已增加了一倍到 40 个消息/秒。</span><span class="sxs-lookup"><span data-stu-id="f03ba-144">To illustrate this point, in the example scenario described in [Test Scenarios for Measuring MST of DTA Tracking](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md), when the message body tracking component of the tracking configuration was eliminated, the MST was doubled to 40 messages/second.</span></span>  
  
 <span data-ttu-id="f03ba-145">此外，需要注意的是，即使发生问题，在许多情况下（但绝非全部情况），无需跟踪消息正文，消息在 MessageBox 数据库中就会被挂起并且可被检索和检查。</span><span class="sxs-lookup"><span data-stu-id="f03ba-145">Also, keep in mind that even when problems do occur, in many (but by no means all) cases, messages are suspended in the MessageBox database and can be retrieved and inspected without needing to track message bodies.</span></span>  
  
 <span data-ttu-id="f03ba-146">关注系统负载的可持续性：</span><span class="sxs-lookup"><span data-stu-id="f03ba-146">Focus on the sustainability of the load you place on the system:</span></span>  
  
-   <span data-ttu-id="f03ba-147">您的系统是否足以不受限制地承受生产负载状况，即使是在一般的维护活动下？</span><span class="sxs-lookup"><span data-stu-id="f03ba-147">Can your system sustain the production load profile indefinitely even with normal maintenance activities?</span></span>  
  
-   <span data-ttu-id="f03ba-148">如果发生导致系统要承受积压（例如计划内或计划外 BizTalkDTADb 数据库中断）的情况将怎么办？</span><span class="sxs-lookup"><span data-stu-id="f03ba-148">What if something happens that causes the system to sustain a backlog, such as a planned or unplanned BizTalkDTADb database outage?</span></span>  
  
 <span data-ttu-id="f03ba-149">最好基于最坏情况的方案设置目标并针对这些目标进行测试。</span><span class="sxs-lookup"><span data-stu-id="f03ba-149">It is a good idea to set goals based on worst case scenarios and test to those goals.</span></span> <span data-ttu-id="f03ba-150">例如，如果您知道存在定期计划的维护周期并在该期间中 BizTalkDTADb 数据库将脱机，则在执行测试期间模拟这一中断，评估系统能否从导致的积压中恢复。</span><span class="sxs-lookup"><span data-stu-id="f03ba-150">For example, if you know that there is a periodic planned maintenance cycle that will take the BizTalkDTADb database off line, emulate this outage during a test run to evaluate the ability of the system to recover from the resulting backlog.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f03ba-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f03ba-151">See Also</span></span>  
 <span data-ttu-id="f03ba-152">[测量的最大可持续跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="f03ba-152">[Measuring Maximum Sustainable Tracking Throughput](../core/measuring-maximum-sustainable-tracking-throughput.md) </span></span>  
 <span data-ttu-id="f03ba-153">[了解 DTA 跟踪性能行为](../core/understanding-dta-tracking-performance-behavior.md) </span><span class="sxs-lookup"><span data-stu-id="f03ba-153">[Understanding DTA Tracking Performance Behavior](../core/understanding-dta-tracking-performance-behavior.md) </span></span>  
 <span data-ttu-id="f03ba-154">[用于测量 MST DTA 跟踪测试方案](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md) </span><span class="sxs-lookup"><span data-stu-id="f03ba-154">[Test Scenarios for Measuring MST of DTA Tracking](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md) </span></span>  
 [<span data-ttu-id="f03ba-155">跟踪数据库的大小调整准则</span><span class="sxs-lookup"><span data-stu-id="f03ba-155">Tracking Database Sizing Guidelines</span></span>](../core/tracking-database-sizing-guidelines.md)