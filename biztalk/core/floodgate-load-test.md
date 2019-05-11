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
ms.openlocfilehash: b78509cc1bc2c38ab1fcf536ce71e3d14b70d500
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387961"
---
# <a name="floodgate-load-test"></a><span data-ttu-id="5ce9f-102">突发高负载测试</span><span class="sxs-lookup"><span data-stu-id="5ce9f-102">Floodgate Load Test</span></span>
<span data-ttu-id="5ce9f-103">本主题中的信息中所述的测试是指[测量的引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md)。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-103">The information in this topic refers to the tests explained in [Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md).</span></span>  
  
## <a name="what-causes-floodgate-events"></a><span data-ttu-id="5ce9f-104">哪些会发生水闸事件？</span><span class="sxs-lookup"><span data-stu-id="5ce9f-104">What Causes Floodgate Events?</span></span>  
 <span data-ttu-id="5ce9f-105">有多种方案只是其中几个较大的峰值 (也称为**水闸事件**) 的消息同时到达系统每一天。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-105">There are a number of scenarios where just a few large peaks (also known as **floodgate events**) of messages arrive at the system each day.</span></span> <span data-ttu-id="5ce9f-106">这些峰值之间，吞吐量可能会很低。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-106">Between these peaks, the throughput can be very low.</span></span> <span data-ttu-id="5ce9f-107">这些类型的方案的示例包括：</span><span class="sxs-lookup"><span data-stu-id="5ce9f-107">Examples of these types of scenarios include:</span></span>  
  
- <span data-ttu-id="5ce9f-108">证券交易，例如，在和关闭</span><span class="sxs-lookup"><span data-stu-id="5ce9f-108">Equity trading, for example, at market open and market close</span></span>  
  
- <span data-ttu-id="5ce9f-109">在结束一天交易对帐过程银行系统，例如，</span><span class="sxs-lookup"><span data-stu-id="5ce9f-109">Banking systems, for example, during end of day transaction reconciliation</span></span>  
  
  <span data-ttu-id="5ce9f-110">其他类型的事件会导致与水闸事件相似的积压行为。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-110">Other types of events can cause backlog behavior similar to floodgate events.</span></span> <span data-ttu-id="5ce9f-111">例如，如果合作伙伴的发送地址脱机，以便目标的消息的地址必须进行重试和/或挂起，这可能导致增加积压。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-111">For example, if a partner send address goes off line so that messages destined for that address must be re-tried and/or suspended, this can result in backlog building up.</span></span> <span data-ttu-id="5ce9f-112">当合作伙伴返回行上，可能有大量挂起的消息需要恢复，从而导致另一种类型的水闸事件。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-112">When the partner comes back on line, there may be a large number of suspended messages that need to be resumed, resulting in another type of floodgate event.</span></span> <span data-ttu-id="5ce9f-113">以下测试系统的阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-113">The following test of the system illustrates this behavior.</span></span>  
  
## <a name="simulating-a-floodgate-event"></a><span data-ttu-id="5ce9f-114">模拟水闸事件</span><span class="sxs-lookup"><span data-stu-id="5ce9f-114">Simulating a Floodgate Event</span></span>  
 <span data-ttu-id="5ce9f-115">对于此测试，系统将在大约半个的最大可承受吞吐量这当然非常稳定最初驱动。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-115">For this test, the system was initially driven at around half the maximum sustainable throughput which of course was very stable.</span></span> <span data-ttu-id="5ce9f-116">然后，若要模拟水闸事件，负载生成工具将配置为在短时间内每秒大约 410 中发送的时间 （加速测试相同）。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-116">Then, to simulate a floodgate event, the load generation tool was configured to send in about 410 msgs/sec for a short period of time (the same as for the overdrive test).</span></span> <span data-ttu-id="5ce9f-117">测量每个第二个和后台处理深度接收的消息的生成的负载配置文件如下所示。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-117">The resultant load profile measuring messages received per second and spool depth is displayed below.</span></span>  
  
 <span data-ttu-id="5ce9f-118">**突发高负载测试的负载状况**</span><span class="sxs-lookup"><span data-stu-id="5ce9f-118">**Load profile of floodgate load test**</span></span>  
  
 <span data-ttu-id="5ce9f-119">![突发高负载的性能监视器显示](../core/media/bts06-floodgate-load.gif "BTS06_Floodgate_Load")</span><span class="sxs-lookup"><span data-stu-id="5ce9f-119">![Performance monitor display of floodgate load](../core/media/bts06-floodgate-load.gif "BTS06_Floodgate_Load")</span></span>  
  
 <span data-ttu-id="5ce9f-120">注意该图，后台处理表快速构建了的积压工作水闸事件期间。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-120">Note from the graph that the spool tables quickly built up a backlog during the floodgate event.</span></span> <span data-ttu-id="5ce9f-121">但是，因为该事件生存期相对较短，并且事件发生后的后续接收速率未达到最大可承受速率，清理作业也能够运行，并从该事件中恢复而无需系统接收中断。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-121">However, because the event was relatively short lived and the subsequent receive rate after the event was below the maximum sustainable rate, the cleanup jobs were able to run and recover from the event without requiring a system receive outage.</span></span> <span data-ttu-id="5ce9f-122">对于此特定测试，MessageBox 存储在 SQL Server 2005;从开始到结束此测试的持续时间为大约耗时 45 分钟。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-122">For this particular test, the MessageBox was housed on SQL Server 2005; the duration of this test from beginning to end was approximately 45 minutes.</span></span>  
  
 <span data-ttu-id="5ce9f-123">当然，每个系统都不同，因此"您的选择而异。"</span><span class="sxs-lookup"><span data-stu-id="5ce9f-123">Of course, every system is different, so "your mileage will vary."</span></span> <span data-ttu-id="5ce9f-124">验证可以恢复的最佳方法是转到生产环境之前使用具代表性的负载测试。</span><span class="sxs-lookup"><span data-stu-id="5ce9f-124">The best way to verify that you can recover is to test with a representative load before going into production.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ce9f-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ce9f-125">See Also</span></span>  
 <span data-ttu-id="5ce9f-126">[测量引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span><span class="sxs-lookup"><span data-stu-id="5ce9f-126">[Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span></span>  
 <span data-ttu-id="5ce9f-127">[使用设置仪表板进行 BizTalk Server 性能优化](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) </span><span class="sxs-lookup"><span data-stu-id="5ce9f-127">[Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) </span></span>  
 <span data-ttu-id="5ce9f-128">[过载测试](../core/overdrive-load-test.md) </span><span class="sxs-lookup"><span data-stu-id="5ce9f-128">[Overdrive Load Test](../core/overdrive-load-test.md) </span></span>  
 [<span data-ttu-id="5ce9f-129">可承受负载测试</span><span class="sxs-lookup"><span data-stu-id="5ce9f-129">Sustainable Load Test</span></span>](../core/sustainable-load-test.md)