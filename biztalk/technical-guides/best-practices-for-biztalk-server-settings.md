---
title: BizTalk Server 设置的最佳实践 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e62024e1-f502-45a8-932f-edd8460bcf5f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 461e2e1a4256d79112e4eec94047c25df34a4511
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001113"
---
# <a name="best-practices-for-biztalk-server-settings"></a><span data-ttu-id="25d69-102">BizTalk Server 设置的最佳方案</span><span class="sxs-lookup"><span data-stu-id="25d69-102">Best Practices for BizTalk Server Settings</span></span>
<span data-ttu-id="25d69-103">本主题列出了执行的操作准备情况过程应遵循的最佳做法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="25d69-103">This topic lists best practices that you should follow as you perform operational readiness procedures for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="25d69-104">**配置消息批处理以提高适配器性能**</span><span class="sxs-lookup"><span data-stu-id="25d69-104">**Configure message batching to increase adapter performance**</span></span>  
  
- <span data-ttu-id="25d69-105">通过组合多个到单个批处理操作由适配器执行的事务的数量降至最低。</span><span class="sxs-lookup"><span data-stu-id="25d69-105">Minimize the number of transactions performed by an adapter by combining more than one operation into a single batch.</span></span>  
  
- <span data-ttu-id="25d69-106">限制基于总消息计数除了在批处理中的字节数的批大小。</span><span class="sxs-lookup"><span data-stu-id="25d69-106">Limit the batch size based on the total number of bytes in the batch, in addition to message count.</span></span> <span data-ttu-id="25d69-107">有关限制批处理大小的详细信息，请参阅[提高适配器性能配置批处理](../technical-guides/configuring-batching-to-improve-adapter-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="25d69-107">For more information about limiting the batch size, see [Configuring Batching to Improve Adapter Performance](../technical-guides/configuring-batching-to-improve-adapter-performance.md).</span></span>  
  
  <span data-ttu-id="25d69-108">**调整大消息阈值**</span><span class="sxs-lookup"><span data-stu-id="25d69-108">**Adjust the large message threshold**</span></span>  
  
- <span data-ttu-id="25d69-109">若要增加吞吐量，增加大消息阈值，这样就降低了大型进行缓冲的消息数为在映射期间的磁盘。</span><span class="sxs-lookup"><span data-stu-id="25d69-109">To improve throughput, increase the large message threshold, which lowers the number of large messages that are buffered to disk during mapping.</span></span>  
  
  <span data-ttu-id="25d69-110">**确定您需要在规划期间跟踪的信息**</span><span class="sxs-lookup"><span data-stu-id="25d69-110">**Determine the information you need to track during planning**</span></span>  
  
- <span data-ttu-id="25d69-111">应在规划阶段确定需要跟踪的信息。这样一来，部署该项目之后, 您可以设置跟踪选项并限制跟踪的数据为你提供所需的信息的量。</span><span class="sxs-lookup"><span data-stu-id="25d69-111">You should decide during the planning stages which information you need to track. This way, after you deploy the project, you can set the tracking options and limit the amount of tracked data to give you only the information you need.</span></span>  
  
  > [!NOTE]  
  >  <span data-ttu-id="25d69-112">有关与跟踪相关的最佳做法的详细信息，请参阅[规划跟踪](../technical-guides/planning-for-tracking.md)本指南中并[运行状况与活动跟踪](http://go.microsoft.com/fwlink/p/?LinkId=154187)(http://go.microsoft.com/fwlink/p/?LinkId=154187)。</span><span class="sxs-lookup"><span data-stu-id="25d69-112">For more information about best practices related to tracking, see [Planning for Tracking](../technical-guides/planning-for-tracking.md) in this guide and [Health and Activity Tracking](http://go.microsoft.com/fwlink/p/?LinkId=154187) (http://go.microsoft.com/fwlink/p/?LinkId=154187).</span></span>  
  
  <span data-ttu-id="25d69-113">**不要跟踪所有消息**</span><span class="sxs-lookup"><span data-stu-id="25d69-113">**Do not track all messages**</span></span>  
  
- <span data-ttu-id="25d69-114">我们建议不跟踪所有消息。</span><span class="sxs-lookup"><span data-stu-id="25d69-114">We recommend that you not track all messages.</span></span> <span data-ttu-id="25d69-115">这是消息的因为每次访问消息，BizTalk Server 将生成的另一个副本。</span><span class="sxs-lookup"><span data-stu-id="25d69-115">This is because each time a message is touched, BizTalk Server makes another copy of the message.</span></span> <span data-ttu-id="25d69-116">而是可以通过跟踪特定端口来缩小范围。</span><span class="sxs-lookup"><span data-stu-id="25d69-116">You can instead narrow the scope by tracking only a specific port.</span></span> <span data-ttu-id="25d69-117">这可以帮助您的系统性能最大化和保持数据库整洁。</span><span class="sxs-lookup"><span data-stu-id="25d69-117">This helps to maximize the performance of your system and to keep the databases uncluttered.</span></span>  
  
  <span data-ttu-id="25d69-118">**将发送端口上设置跟踪和接收管道上的而不是端口**</span><span class="sxs-lookup"><span data-stu-id="25d69-118">**Set tracking on send ports and receive ports instead of on a pipeline**</span></span>  
  
- <span data-ttu-id="25d69-119">如果设置管道的跟踪选项，则还将设置为使用的管道的每个端口全局跟踪选项。</span><span class="sxs-lookup"><span data-stu-id="25d69-119">If you set tracking options on pipelines, you will also set the tracking options globally for every port that uses the pipeline.</span></span> <span data-ttu-id="25d69-120">反过来，这可能会在导致被跟踪比你预期，这将降低系统性能的更多数据。</span><span class="sxs-lookup"><span data-stu-id="25d69-120">This in turn may result in far more data being tracked than you intend, which will slow system performance.</span></span> <span data-ttu-id="25d69-121">相反，您可以设置跟踪选项上的发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="25d69-121">Instead, you can set tracking options on send ports and receive ports.</span></span>  
  
  <span data-ttu-id="25d69-122">**调整基于资源使用率的阻止功能**</span><span class="sxs-lookup"><span data-stu-id="25d69-122">**Adjust throttling based on resource utilization**</span></span>  
  
- <span data-ttu-id="25d69-123">中的阻止行为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]默认提供良好的保护系统配置。</span><span class="sxs-lookup"><span data-stu-id="25d69-123">Throttling in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is configured by default to provide good protection for the system.</span></span> <span data-ttu-id="25d69-124">监视限制状态，以查看是否限制发生的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="25d69-124">Monitor the performance counters for throttling states to see if throttling is taking place.</span></span> <span data-ttu-id="25d69-125">然后自行衡量阻止行为的资源为基础 （例如，数据库大小或内存使用率） 处于过利用。</span><span class="sxs-lookup"><span data-stu-id="25d69-125">Then gauge for yourself if the resource on which throttling is based (for example, database size or memory usage) is under or over utilized.</span></span> <span data-ttu-id="25d69-126">接下来，调整阻止阈值相应地增减。</span><span class="sxs-lookup"><span data-stu-id="25d69-126">Next, adjust the throttling thresholds up or down accordingly.</span></span> <span data-ttu-id="25d69-127">有关详细信息，请参阅[调整阻止阈值： 时间和原因](http://go.microsoft.com/fwlink/p/?LinkId=154188)(<http://go.microsoft.com/fwlink/p/?LinkId=154188>)。</span><span class="sxs-lookup"><span data-stu-id="25d69-127">For more information, see [Adjusting Throttling Thresholds: When and Why](http://go.microsoft.com/fwlink/p/?LinkId=154188) (<http://go.microsoft.com/fwlink/p/?LinkId=154188>).</span></span>  
  
  <span data-ttu-id="25d69-128">**如果可能，请使用 PassThruTransmit 管道**</span><span class="sxs-lookup"><span data-stu-id="25d69-128">**Use the PassThruTransmit pipeline if possible**</span></span>  
  
- <span data-ttu-id="25d69-129">如果消息发送到其目标之前不需要处理任何文档，而不是 XML 发送管道使用 PassThruTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="25d69-129">If no document processing is required before sending a message to its destination, use the PassThruTransmit pipeline instead of the XML send pipeline.</span></span>  
  
  <span data-ttu-id="25d69-130">**最小化使用的业务流程"形状开始和结束"跟踪事件**</span><span class="sxs-lookup"><span data-stu-id="25d69-130">**Minimize usage of orchestration “Shape start and end” tracking events**</span></span>  
  
- <span data-ttu-id="25d69-131">虽然跟踪的业务流程形状的业务流程调试明显的优势，它具有性能和可伸缩性的影响。</span><span class="sxs-lookup"><span data-stu-id="25d69-131">While orchestration shape tracking has obvious benefits for orchestration debugging, it has performance and scalability implications.</span></span> <span data-ttu-id="25d69-132">**形状开始和结束**跟踪事件可能会导致很大的开销。</span><span class="sxs-lookup"><span data-stu-id="25d69-132">The **Shape start and end** tracking event can cause significant overhead.</span></span> <span data-ttu-id="25d69-133">最好是尽量减少在较高的吞吐量是必要的生产环境中其使用情况。</span><span class="sxs-lookup"><span data-stu-id="25d69-133">It is best to minimize its usage in production environments where high throughput is necessary.</span></span>  
  
  > [!NOTE]  
  >  <span data-ttu-id="25d69-134">**形状开始和结束**默认情况下对所有业务流程启用跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="25d69-134">**Shape start and end** tracking events are ENABLED by default on all orchestrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25d69-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="25d69-135">See Also</span></span>  
 [<span data-ttu-id="25d69-136">清单：配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="25d69-136">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)