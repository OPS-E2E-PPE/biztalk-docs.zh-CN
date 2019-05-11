---
title: 据以加快负载测试 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d16d0a8-4255-4f5a-86a2-26cc11bb9a70
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 734c0dffc64ca7efd52b6325227a26ee0387b50e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393403"
---
# <a name="overdrive-load-test"></a><span data-ttu-id="d631b-102">过载测试</span><span class="sxs-lookup"><span data-stu-id="d631b-102">Overdrive Load Test</span></span>
<span data-ttu-id="d631b-103">本主题中的信息中所述的测试是指[测量的引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md)。</span><span class="sxs-lookup"><span data-stu-id="d631b-103">The information in this topic refers to the tests explained in [Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md).</span></span>  
  
 <span data-ttu-id="d631b-104">负载生成工具 LoadGen 2007 使您可以模拟 BizTalk Server 系统上。</span><span class="sxs-lookup"><span data-stu-id="d631b-104">The Load Generation tool, LoadGen 2007, enables you to simulate heavy loads on a BizTalk Server system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d631b-105">下载[LoadGen](https://www.microsoft.com/download/details.aspx?id=14925)。</span><span class="sxs-lookup"><span data-stu-id="d631b-105">Download [LoadGen](https://www.microsoft.com/download/details.aspx?id=14925).</span></span> <span data-ttu-id="d631b-106">此工具的以前版本，BizTalk Server 2004 负载生成工具是可在下载[ http://go.microsoft.com/fwlink/?linkid=108999 ](http://go.microsoft.com/fwlink/?linkid=108999)。</span><span class="sxs-lookup"><span data-stu-id="d631b-106">The previous version of this tool, the BizTalk Server 2004 Load Generation Tool is available for download at [http://go.microsoft.com/fwlink/?linkid=108999](http://go.microsoft.com/fwlink/?linkid=108999).</span></span>  
  
 <span data-ttu-id="d631b-107">为了模拟连续的过载系统，LoadGen 2007 配置为发送每秒大约 410，120 每秒超过测量的最大可承受吞吐量。</span><span class="sxs-lookup"><span data-stu-id="d631b-107">To simulate a continuously overdriven system, LoadGen 2007 was configured to send about 410 msgs/sec, 120 msgs/sec more than the measured maximum sustainable throughput.</span></span>  
  
 <span data-ttu-id="d631b-108">为了使系统过载不仅要了解从大约 2 万条记录的后台处理积压深度中恢复需要多长时间设计测试。</span><span class="sxs-lookup"><span data-stu-id="d631b-108">The test was designed not only to overdrive the system, but also to get an idea of how long it would take to recover from a spool backlog depth of around 2 million records.</span></span>  
  
 <span data-ttu-id="d631b-109">若要实现此目的，加速驱动系统，以增加速率直到后台处理深度非常大约 2 万条记录。</span><span class="sxs-lookup"><span data-stu-id="d631b-109">To accomplish this, the system was driven at the increased rate until the spool depth was around 2 million records.</span></span> <span data-ttu-id="d631b-110">一旦后台处理深度达到所需的级别，则不能进一步生成负载。</span><span class="sxs-lookup"><span data-stu-id="d631b-110">Once the spool depth reached the desired level then no further load was generated.</span></span>  
  
 <span data-ttu-id="d631b-111">若要确保 BizTalk 阻止机制是否不会阻止接收主机会防止后台处理表积压累积， **DB 中的消息数**接收主机已从更改阻止阈值默认值 50000 为 2000000。</span><span class="sxs-lookup"><span data-stu-id="d631b-111">To ensure that the BizTalk throttling mechanism did not throttle the receive host, which would prevent the accumulation of a spool table backlog, the **Message count in DB** throttling threshold for the receive host was changed from the default value of 50000 to 2000000.</span></span> <span data-ttu-id="d631b-112">有关更改信息**DB 中的消息数**阻止阈值，请参阅[如何修改资源基于阻止设置](../core/how-to-modify-resource-based-throttling-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="d631b-112">For information on changing the **Message count in DB** throttling threshold, see [How to Modify Resource Based Throttling Settings](../core/how-to-modify-resource-based-throttling-settings.md).</span></span> <span data-ttu-id="d631b-113">有关默认主机阻止设置的信息，请参阅[使用设置仪表板进行 BizTalk Server 性能调整](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)。</span><span class="sxs-lookup"><span data-stu-id="d631b-113">For information about the default host throttling settings, see [Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md).</span></span>  
  
 <span data-ttu-id="d631b-114">下图显示了上图相同的指标。</span><span class="sxs-lookup"><span data-stu-id="d631b-114">The following graph shows the same indicators as in the graph above.</span></span>  
  
 <span data-ttu-id="d631b-115">**过载测试的负载配置文件**</span><span class="sxs-lookup"><span data-stu-id="d631b-115">**Load profile of overdrive load test**</span></span>  
  
 <span data-ttu-id="d631b-116">![过载的性能监视器显示](../core/media/bts06-overdrive-load.gif "BTS06_Overdrive_Load")</span><span class="sxs-lookup"><span data-stu-id="d631b-116">![Performance montor display of overdrive load](../core/media/bts06-overdrive-load.gif "BTS06_Overdrive_Load")</span></span>  
  
 <span data-ttu-id="d631b-117">从关系图可以看出，后台处理深度会立即开始，在高峰 200 万条记录的正上方。</span><span class="sxs-lookup"><span data-stu-id="d631b-117">As can be seen from the graph, the spool depth started building up immediately, peaking at just above 2 million records.</span></span> <span data-ttu-id="d631b-118">按照这个频率，花费几乎 2.5 小时达到目标 2 百万记录积压工作。</span><span class="sxs-lookup"><span data-stu-id="d631b-118">At this rate, it took just about 2.5 hours to get to the targeted 2 million record backlog.</span></span> <span data-ttu-id="d631b-119">负载已停止后，花费了大约 8 小时对清除作业从积压中恢复。</span><span class="sxs-lookup"><span data-stu-id="d631b-119">After the load was stopped, it took around 8 hours for the cleanup jobs to recover from the backlog.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d631b-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="d631b-120">See Also</span></span>  
 <span data-ttu-id="d631b-121">[测量引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span><span class="sxs-lookup"><span data-stu-id="d631b-121">[Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span></span>  
 <span data-ttu-id="d631b-122">[使用设置仪表板进行 BizTalk Server 性能优化](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) </span><span class="sxs-lookup"><span data-stu-id="d631b-122">[Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) </span></span>  
 [<span data-ttu-id="d631b-123">可承受负载测试</span><span class="sxs-lookup"><span data-stu-id="d631b-123">Sustainable Load Test</span></span>](../core/sustainable-load-test.md)