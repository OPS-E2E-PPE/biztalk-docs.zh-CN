---
title: "据以加快负载测试 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d16d0a8-4255-4f5a-86a2-26cc11bb9a70
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cff4592c58dd165a85d63666958721231cfcbd4c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="overdrive-load-test"></a><span data-ttu-id="d107f-102">Overdrive 负载测试</span><span class="sxs-lookup"><span data-stu-id="d107f-102">Overdrive Load Test</span></span>
<span data-ttu-id="d107f-103">本主题中的信息是指中所述的测试[测试方案的引擎测量 MST](../core/test-scenarios-for-measuring-mst-of-the-engine.md)。</span><span class="sxs-lookup"><span data-stu-id="d107f-103">The information in this topic refers to the tests explained in [Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md).</span></span>  
  
 <span data-ttu-id="d107f-104">使用负载生成工具 Loadgen 2007，你可以模拟 BizTalk Server 系统过载时的情况。</span><span class="sxs-lookup"><span data-stu-id="d107f-104">The Load Generation tool, LoadGen 2007, enables you to simulate heavy loads on a BizTalk Server system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d107f-105">下载[LoadGen](https://www.microsoft.com/download/details.aspx?id=14925)。</span><span class="sxs-lookup"><span data-stu-id="d107f-105">Download [LoadGen](https://www.microsoft.com/download/details.aspx?id=14925).</span></span> <span data-ttu-id="d107f-106">此工具的以前版本，BizTalk Server 2004 负载生成工具是可在下载[http://go.microsoft.com/fwlink/?linkid=108999](http://go.microsoft.com/fwlink/?linkid=108999)。</span><span class="sxs-lookup"><span data-stu-id="d107f-106">The previous version of this tool, the BizTalk Server 2004 Load Generation Tool is available for download at [http://go.microsoft.com/fwlink/?linkid=108999](http://go.microsoft.com/fwlink/?linkid=108999).</span></span>  
  
 <span data-ttu-id="d107f-107">为了模拟连续的过载系统，将 LoadGen 2007 配置为每秒大约发送 410 条消息，比测量的最大可承受吞吐量每秒多出 120 条消息。</span><span class="sxs-lookup"><span data-stu-id="d107f-107">To simulate a continuously overdriven system, LoadGen 2007 was configured to send about 410 msgs/sec, 120 msgs/sec more than the measured maximum sustainable throughput.</span></span>  
  
 <span data-ttu-id="d107f-108">该测试不仅是为了使系统过载运行，而且还要了解从大约二百万条记录的后台处理积压深度中恢复需要多长时间。</span><span class="sxs-lookup"><span data-stu-id="d107f-108">The test was designed not only to overdrive the system, but also to get an idea of how long it would take to recover from a spool backlog depth of around 2 million records.</span></span>  
  
 <span data-ttu-id="d107f-109">为了达到此积压深度，需要加速驱动系统，直到后台处理深度达到大约二百万条记录。</span><span class="sxs-lookup"><span data-stu-id="d107f-109">To accomplish this, the system was driven at the increased rate until the spool depth was around 2 million records.</span></span> <span data-ttu-id="d107f-110">一旦后台处理深度达到所需级别，则不再进一步生成负载。</span><span class="sxs-lookup"><span data-stu-id="d107f-110">Once the spool depth reached the desired level then no further load was generated.</span></span>  
  
 <span data-ttu-id="d107f-111">若要确保限制机制 BizTalk 未限制接收主机，可能会妨碍的假脱机表积压工作的累积，**消息在数据库中的计数**接收主机已从更改为限制阈值默认值为 2000000 50000。</span><span class="sxs-lookup"><span data-stu-id="d107f-111">To ensure that the BizTalk throttling mechanism did not throttle the receive host, which would prevent the accumulation of a spool table backlog, the **Message count in DB** throttling threshold for the receive host was changed from the default value of 50000 to 2000000.</span></span> <span data-ttu-id="d107f-112">有关更改信息**消息在数据库中的计数**限制阈值，请参阅[如何修改资源基于限制设置](../core/how-to-modify-resource-based-throttling-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="d107f-112">For information on changing the **Message count in DB** throttling threshold, see [How to Modify Resource Based Throttling Settings](../core/how-to-modify-resource-based-throttling-settings.md).</span></span> <span data-ttu-id="d107f-113">有关限制设置的默认主机的信息，请参阅[BizTalk Server 性能优化使用设置仪表板](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)。</span><span class="sxs-lookup"><span data-stu-id="d107f-113">For information about the default host throttling settings, see [Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md).</span></span>  
  
 <span data-ttu-id="d107f-114">下图显示了与上图相同的指标。</span><span class="sxs-lookup"><span data-stu-id="d107f-114">The following graph shows the same indicators as in the graph above.</span></span>  
  
 <span data-ttu-id="d107f-115">**Overdrive 负载测试的负载配置文件**</span><span class="sxs-lookup"><span data-stu-id="d107f-115">**Load profile of overdrive load test**</span></span>  
  
 <span data-ttu-id="d107f-116">![Overdrive 负荷的性能 montor 显示](../core/media/bts06-overdrive-load.gif "BTS06_Overdrive_Load")</span><span class="sxs-lookup"><span data-stu-id="d107f-116">![Performance montor display of overdrive load](../core/media/bts06-overdrive-load.gif "BTS06_Overdrive_Load")</span></span>  
  
 <span data-ttu-id="d107f-117">从图中可以看出，后台处理深度会立即开始增加，在正好超过二百万条记录后达到峰值。</span><span class="sxs-lookup"><span data-stu-id="d107f-117">As can be seen from the graph, the spool depth started building up immediately, peaking at just above 2 million records.</span></span> <span data-ttu-id="d107f-118">以此速度，它正好用了大约 2.5 小时达到二百万条的目标记录积压量。</span><span class="sxs-lookup"><span data-stu-id="d107f-118">At this rate, it took just about 2.5 hours to get to the targeted 2 million record backlog.</span></span> <span data-ttu-id="d107f-119">在停止增加负载后，清理作业从积压中恢复大约用了 8 小时。</span><span class="sxs-lookup"><span data-stu-id="d107f-119">After the load was stopped, it took around 8 hours for the cleanup jobs to recover from the backlog.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d107f-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d107f-120">See Also</span></span>  
 <span data-ttu-id="d107f-121">[用于测量引擎 MST 测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span><span class="sxs-lookup"><span data-stu-id="d107f-121">[Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span></span>  
 <span data-ttu-id="d107f-122">[设置仪表板用于 BizTalk Server 性能优化](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) </span><span class="sxs-lookup"><span data-stu-id="d107f-122">[Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) </span></span>  
 [<span data-ttu-id="d107f-123">可承受负载测试</span><span class="sxs-lookup"><span data-stu-id="d107f-123">Sustainable Load Test</span></span>](../core/sustainable-load-test.md)