---
title: 突发高负载测试 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- LoadGen tool, simulating floodgate events
- performance, floodgate peaks
- floodgate events [performance]
ms.assetid: 937f2478-339b-4ae2-b107-56f3a4bfc579
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e38329066075f1e1d3dcb6acf5715b22e64b5b6e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969166"
---
# <a name="floodgate-load-test"></a><span data-ttu-id="59a77-102">突发高负载测试</span><span class="sxs-lookup"><span data-stu-id="59a77-102">Floodgate Load Test</span></span>
<span data-ttu-id="59a77-103">本主题中的信息中所述的测试是指[测量的引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md)。</span><span class="sxs-lookup"><span data-stu-id="59a77-103">The information in this topic refers to the tests explained in [Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md).</span></span>  
  
## <a name="what-causes-floodgate-events"></a><span data-ttu-id="59a77-104">什么情况下将会发生水闸事件？</span><span class="sxs-lookup"><span data-stu-id="59a77-104">What Causes Floodgate Events?</span></span>  
 <span data-ttu-id="59a77-105">有多种方案只是其中几个较大的峰值 (也称为**水闸事件**) 的消息同时到达系统每一天。</span><span class="sxs-lookup"><span data-stu-id="59a77-105">There are a number of scenarios where just a few large peaks (also known as **floodgate events**) of messages arrive at the system each day.</span></span> <span data-ttu-id="59a77-106">而在这些峰值之间，吞吐量非常低。</span><span class="sxs-lookup"><span data-stu-id="59a77-106">Between these peaks, the throughput can be very low.</span></span> <span data-ttu-id="59a77-107">这种类型的情况的示例包括：</span><span class="sxs-lookup"><span data-stu-id="59a77-107">Examples of these types of scenarios include:</span></span>  
  
- <span data-ttu-id="59a77-108">例如，在开市和闭市时的股票交易。</span><span class="sxs-lookup"><span data-stu-id="59a77-108">Equity trading, for example, at market open and market close</span></span>  
  
- <span data-ttu-id="59a77-109">例如，在一天结束时，交易对帐期间的银行系统。</span><span class="sxs-lookup"><span data-stu-id="59a77-109">Banking systems, for example, during end of day transaction reconciliation</span></span>  
  
  <span data-ttu-id="59a77-110">其他类型的事件也可导致与水闸事件相似的积压行为。</span><span class="sxs-lookup"><span data-stu-id="59a77-110">Other types of events can cause backlog behavior similar to floodgate events.</span></span> <span data-ttu-id="59a77-111">例如，如果合作伙伴的发送地址脱机，以该地址为目标的消息将可能重试并/或挂起，而这将导致增加积压量。</span><span class="sxs-lookup"><span data-stu-id="59a77-111">For example, if a partner send address goes off line so that messages destined for that address must be re-tried and/or suspended, this can result in backlog building up.</span></span> <span data-ttu-id="59a77-112">如果合作伙伴重新联机，则可能有大量挂起的消息需要恢复，而这又将导致另一种类型的水闸事件。</span><span class="sxs-lookup"><span data-stu-id="59a77-112">When the partner comes back on line, there may be a large number of suspended messages that need to be resumed, resulting in another type of floodgate event.</span></span> <span data-ttu-id="59a77-113">下面的系统测试将阐释此行为。</span><span class="sxs-lookup"><span data-stu-id="59a77-113">The following test of the system illustrates this behavior.</span></span>  
  
## <a name="simulating-a-floodgate-event"></a><span data-ttu-id="59a77-114">模拟水闸事件</span><span class="sxs-lookup"><span data-stu-id="59a77-114">Simulating a Floodgate Event</span></span>  
 <span data-ttu-id="59a77-115">对于此测试，最初，系统将以最大可承受吞吐量的一半（这当然非常稳定）进行驱动。</span><span class="sxs-lookup"><span data-stu-id="59a77-115">For this test, the system was initially driven at around half the maximum sustainable throughput which of course was very stable.</span></span> <span data-ttu-id="59a77-116">然后，为模拟水闸事件，负载生成工具将配置为在短时间（与加速测试相同）内以大约每秒 410 条消息的速度进行发送。</span><span class="sxs-lookup"><span data-stu-id="59a77-116">Then, to simulate a floodgate event, the load generation tool was configured to send in about 410 msgs/sec for a short period of time (the same as for the overdrive test).</span></span> <span data-ttu-id="59a77-117">下图显示了度量每秒所收到消息所生成的负载状况以及后台处理深度。</span><span class="sxs-lookup"><span data-stu-id="59a77-117">The resultant load profile measuring messages received per second and spool depth is displayed below.</span></span>  
  
 <span data-ttu-id="59a77-118">**突发高负载测试的负载状况**</span><span class="sxs-lookup"><span data-stu-id="59a77-118">**Load profile of floodgate load test**</span></span>  
  
 <span data-ttu-id="59a77-119">![突发高负载的性能监视器显示](../core/media/bts06-floodgate-load.gif "BTS06_Floodgate_Load")</span><span class="sxs-lookup"><span data-stu-id="59a77-119">![Performance monitor display of floodgate load](../core/media/bts06-floodgate-load.gif "BTS06_Floodgate_Load")</span></span>  
  
 <span data-ttu-id="59a77-120">请注意，从图中可看出，在水闸事件期间后台处理表中的积压快速增加。</span><span class="sxs-lookup"><span data-stu-id="59a77-120">Note from the graph that the spool tables quickly built up a backlog during the floodgate event.</span></span> <span data-ttu-id="59a77-121">但是，由于事件的生命期相对较短，而且事件之后的接收速率低于最大可承受速率，因此可以运行清除作业，从事件中恢复到正常状况，而无需停用系统接收。</span><span class="sxs-lookup"><span data-stu-id="59a77-121">However, because the event was relatively short lived and the subsequent receive rate after the event was below the maximum sustainable rate, the cleanup jobs were able to run and recover from the event without requiring a system receive outage.</span></span> <span data-ttu-id="59a77-122">对于此具体的测试，MessageBox 存储在 SQL Server 2005 中；此测试的持续时间从开始到结束大约耗时 45 分钟。</span><span class="sxs-lookup"><span data-stu-id="59a77-122">For this particular test, the MessageBox was housed on SQL Server 2005; the duration of this test from beginning to end was approximately 45 minutes.</span></span>  
  
 <span data-ttu-id="59a77-123">当然，由于所用系统不尽相同，因此持续时间也各不相同。</span><span class="sxs-lookup"><span data-stu-id="59a77-123">Of course, every system is different, so "your mileage will vary."</span></span> <span data-ttu-id="59a77-124">验证可以恢复的最佳方式是：在进入生产阶段之前，应使用最具代表性的负载进行测试。</span><span class="sxs-lookup"><span data-stu-id="59a77-124">The best way to verify that you can recover is to test with a representative load before going into production.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59a77-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="59a77-125">See Also</span></span>  
 <span data-ttu-id="59a77-126">[测量引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span><span class="sxs-lookup"><span data-stu-id="59a77-126">[Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span></span>  
 <span data-ttu-id="59a77-127">[使用设置仪表板进行 BizTalk Server 性能优化](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) </span><span class="sxs-lookup"><span data-stu-id="59a77-127">[Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) </span></span>  
 <span data-ttu-id="59a77-128">[过载测试](../core/overdrive-load-test.md) </span><span class="sxs-lookup"><span data-stu-id="59a77-128">[Overdrive Load Test](../core/overdrive-load-test.md) </span></span>  
 [<span data-ttu-id="59a77-129">可承受负载测试</span><span class="sxs-lookup"><span data-stu-id="59a77-129">Sustainable Load Test</span></span>](../core/sustainable-load-test.md)