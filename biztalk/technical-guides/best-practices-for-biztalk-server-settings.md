---
title: "BizTalk Server 设置的最佳实践 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e62024e1-f502-45a8-932f-edd8460bcf5f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf1f89ced33be6f10ceaae37ccb2c899c4e01eac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-biztalk-server-settings"></a><span data-ttu-id="2f398-102">BizTalk Server 设置的最佳操作</span><span class="sxs-lookup"><span data-stu-id="2f398-102">Best Practices for BizTalk Server Settings</span></span>
<span data-ttu-id="2f398-103">本主题列出了执行的操作的准备情况过程时应遵循的最佳实践[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2f398-103">This topic lists best practices that you should follow as you perform operational readiness procedures for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="2f398-104">**配置消息批处理，以便提高适配器性能**</span><span class="sxs-lookup"><span data-stu-id="2f398-104">**Configure message batching to increase adapter performance**</span></span>  
  
-   <span data-ttu-id="2f398-105">最小化适配器由的组合为一个批处理的多个操作的事务的数。</span><span class="sxs-lookup"><span data-stu-id="2f398-105">Minimize the number of transactions performed by an adapter by combining more than one operation into a single batch.</span></span>  
  
-   <span data-ttu-id="2f398-106">限制基于总批处理，除了邮件计数中的字节数的批次大小。</span><span class="sxs-lookup"><span data-stu-id="2f398-106">Limit the batch size based on the total number of bytes in the batch, in addition to message count.</span></span> <span data-ttu-id="2f398-107">有关限制的批次大小的详细信息，请参阅[配置批处理提高适配器性能](../technical-guides/configuring-batching-to-improve-adapter-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="2f398-107">For more information about limiting the batch size, see [Configuring Batching to Improve Adapter Performance](../technical-guides/configuring-batching-to-improve-adapter-performance.md).</span></span>  
  
 <span data-ttu-id="2f398-108">**调整大型消息阈值**</span><span class="sxs-lookup"><span data-stu-id="2f398-108">**Adjust the large message threshold**</span></span>  
  
-   <span data-ttu-id="2f398-109">若要增加吞吐量，增加大消息阈值，这样就降低了大型进行缓冲的消息数为在映射中磁盘。</span><span class="sxs-lookup"><span data-stu-id="2f398-109">To improve throughput, increase the large message threshold, which lowers the number of large messages that are buffered to disk during mapping.</span></span>  
  
 <span data-ttu-id="2f398-110">**确定需要跟踪在规划过程的信息**</span><span class="sxs-lookup"><span data-stu-id="2f398-110">**Determine the information you need to track during planning**</span></span>  
  
-   <span data-ttu-id="2f398-111">应在规划阶段决定你需要跟踪的信息。这样一来，在部署项目后, 你可以设置跟踪选项并限制跟踪的数据为你提供所需的信息的量。</span><span class="sxs-lookup"><span data-stu-id="2f398-111">You should decide during the planning stages which information you need to track. This way, after you deploy the project, you can set the tracking options and limit the amount of tracked data to give you only the information you need.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2f398-112">有关与跟踪相关的最佳做法的详细信息，请参阅[规划跟踪](../technical-guides/planning-for-tracking.md)本指南中和[运行状况和活动跟踪](http://go.microsoft.com/fwlink/p/?LinkId=154187)(http://go.microsoft.com/fwlink/p/?LinkId=154187)。</span><span class="sxs-lookup"><span data-stu-id="2f398-112">For more information about best practices related to tracking, see [Planning for Tracking](../technical-guides/planning-for-tracking.md) in this guide and [Health and Activity Tracking](http://go.microsoft.com/fwlink/p/?LinkId=154187) (http://go.microsoft.com/fwlink/p/?LinkId=154187).</span></span>  
  
 <span data-ttu-id="2f398-113">**不跟踪所有消息**</span><span class="sxs-lookup"><span data-stu-id="2f398-113">**Do not track all messages**</span></span>  
  
-   <span data-ttu-id="2f398-114">我们建议你不跟踪所有消息。</span><span class="sxs-lookup"><span data-stu-id="2f398-114">We recommend that you not track all messages.</span></span> <span data-ttu-id="2f398-115">这是因为每次都需要一条消息，BizTalk Server 使该消息的另一个副本。</span><span class="sxs-lookup"><span data-stu-id="2f398-115">This is because each time a message is touched, BizTalk Server makes another copy of the message.</span></span> <span data-ttu-id="2f398-116">通过跟踪特定端口，而是可以缩小范围。</span><span class="sxs-lookup"><span data-stu-id="2f398-116">You can instead narrow the scope by tracking only a specific port.</span></span> <span data-ttu-id="2f398-117">这有助于你的系统的性能最大化，并以使数据库整洁。</span><span class="sxs-lookup"><span data-stu-id="2f398-117">This helps to maximize the performance of your system and to keep the databases uncluttered.</span></span>  
  
 <span data-ttu-id="2f398-118">**在发送端口上设置跟踪和接收管道上的而不是端口**</span><span class="sxs-lookup"><span data-stu-id="2f398-118">**Set tracking on send ports and receive ports instead of on a pipeline**</span></span>  
  
-   <span data-ttu-id="2f398-119">如果你设置跟踪选项卡上的管道，你还将设置使用管道的每个端口全局跟踪选项。</span><span class="sxs-lookup"><span data-stu-id="2f398-119">If you set tracking options on pipelines, you will also set the tracking options globally for every port that uses the pipeline.</span></span> <span data-ttu-id="2f398-120">反过来，这可能会在导致被跟踪比你预期，这将降低系统性能的更多数据。</span><span class="sxs-lookup"><span data-stu-id="2f398-120">This in turn may result in far more data being tracked than you intend, which will slow system performance.</span></span> <span data-ttu-id="2f398-121">相反，你可以将端口设置跟踪选项卡上的发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="2f398-121">Instead, you can set tracking options on send ports and receive ports.</span></span>  
  
 <span data-ttu-id="2f398-122">**调整限制基于资源使用率**</span><span class="sxs-lookup"><span data-stu-id="2f398-122">**Adjust throttling based on resource utilization**</span></span>  
  
-   <span data-ttu-id="2f398-123">限制在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置默认情况下提供系统的有效保护方式。</span><span class="sxs-lookup"><span data-stu-id="2f398-123">Throttling in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is configured by default to provide good protection for the system.</span></span> <span data-ttu-id="2f398-124">监视限制状态以查看限制是否正在进行的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="2f398-124">Monitor the performance counters for throttling states to see if throttling is taking place.</span></span> <span data-ttu-id="2f398-125">然后仪表亲自，如果基于上限制的资源 （例如，数据库大小或内存使用率） 低于或高于利用。</span><span class="sxs-lookup"><span data-stu-id="2f398-125">Then gauge for yourself if the resource on which throttling is based (for example, database size or memory usage) is under or over utilized.</span></span> <span data-ttu-id="2f398-126">接下来，调整，限制阈值正常运行或相应地关闭。</span><span class="sxs-lookup"><span data-stu-id="2f398-126">Next, adjust the throttling thresholds up or down accordingly.</span></span> <span data-ttu-id="2f398-127">有关详细信息，请参阅[调整限制阈值： 何时和为何](http://go.microsoft.com/fwlink/p/?LinkId=154188)(http://go.microsoft.com/fwlink/p/?LinkId=154188)。</span><span class="sxs-lookup"><span data-stu-id="2f398-127">For more information, see [Adjusting Throttling Thresholds: When and Why](http://go.microsoft.com/fwlink/p/?LinkId=154188) (http://go.microsoft.com/fwlink/p/?LinkId=154188).</span></span>  
  
 <span data-ttu-id="2f398-128">**如有可能使用 PassThruTransmit 管道**</span><span class="sxs-lookup"><span data-stu-id="2f398-128">**Use the PassThruTransmit pipeline if possible**</span></span>  
  
-   <span data-ttu-id="2f398-129">如果在将消息发送到其目标之前需要没有文档处理，而不是 XML 发送管道使用 PassThruTransmit 管道。</span><span class="sxs-lookup"><span data-stu-id="2f398-129">If no document processing is required before sending a message to its destination, use the PassThruTransmit pipeline instead of the XML send pipeline.</span></span>  
  
 <span data-ttu-id="2f398-130">**最小化"形状开始和结束"的业务流程的使用情况跟踪事件**</span><span class="sxs-lookup"><span data-stu-id="2f398-130">**Minimize usage of orchestration “Shape start and end” tracking events**</span></span>  
  
-   <span data-ttu-id="2f398-131">虽然跟踪的业务流程形状具有的业务流程调试的明显优势，但其性能和可伸缩性的影响。</span><span class="sxs-lookup"><span data-stu-id="2f398-131">While orchestration shape tracking has obvious benefits for orchestration debugging, it has performance and scalability implications.</span></span> <span data-ttu-id="2f398-132">**形状开始和结束**跟踪事件可能会导致很大的开销。</span><span class="sxs-lookup"><span data-stu-id="2f398-132">The **Shape start and end** tracking event can cause significant overhead.</span></span> <span data-ttu-id="2f398-133">最好是尽量减少在较高的吞吐量是必要的生产环境中其使用情况。</span><span class="sxs-lookup"><span data-stu-id="2f398-133">It is best to minimize its usage in production environments where high throughput is necessary.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2f398-134">**调整开始和结束**默认情况下，所有的业务流程上启用跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="2f398-134">**Shape start and end** tracking events are ENABLED by default on all orchestrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f398-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f398-135">See Also</span></span>  
 [<span data-ttu-id="2f398-136">清单： 配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="2f398-136">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)