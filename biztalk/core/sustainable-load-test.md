---
title: 可承受负载测试 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- sustainable load test
- LoadGen tool, sustainable load test
ms.assetid: a9d752ff-aff1-4445-8af5-8f84609880e2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d17d8d38323f7933c8e60cb2b87e0ec312d270c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015646"
---
# <a name="sustainable-load-test"></a><span data-ttu-id="d454d-102">可持续负载测试</span><span class="sxs-lookup"><span data-stu-id="d454d-102">Sustainable Load Test</span></span>
<span data-ttu-id="d454d-103">本主题中的信息中所述的测试是指[测量的引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md)。</span><span class="sxs-lookup"><span data-stu-id="d454d-103">The information in this topic refers to the tests explained in [Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md).</span></span>  
  
 <span data-ttu-id="d454d-104">对于第一个测试，系统将驱动到 MST，以便可以观察运行状况良好的系统。</span><span class="sxs-lookup"><span data-stu-id="d454d-104">For the first test, the system was driven to MST so that observations of a healthy system can be made.</span></span>  
  
 <span data-ttu-id="d454d-105">下图显示了使用此方法找到测试系统的最大可承受吞吐量后的关键指标。</span><span class="sxs-lookup"><span data-stu-id="d454d-105">The following graph shows key indicators after using this approach to find the maximum sustainable throughput of the test system.</span></span>  
  
 <span data-ttu-id="d454d-106">**可承受负载测试的负载状况**</span><span class="sxs-lookup"><span data-stu-id="d454d-106">**Load profile of sustainable load test**</span></span>  
  
 <span data-ttu-id="d454d-107">![性能监视器测量可承受负载](../core/media/bts06-sustainable-load.gif "BTS06_Sustainable_Load")</span><span class="sxs-lookup"><span data-stu-id="d454d-107">![Performance monitor measuring sustainable load](../core/media/bts06-sustainable-load.gif "BTS06_Sustainable_Load")</span></span>  
  
 <span data-ttu-id="d454d-108">从此图中可以看出，在测试时间内，后台处理深度非常稳定并且没有增长：</span><span class="sxs-lookup"><span data-stu-id="d454d-108">This graph shows that, for the hour of the test, the spool depth was stable and not growing:</span></span>  
  
- <span data-ttu-id="d454d-109">图顶部的黑线表示系统每秒收到的全部消息（例如，两个接收服务器）。</span><span class="sxs-lookup"><span data-stu-id="d454d-109">The black lines at the top of the graph show the total messages received per second by the system (for example, for both of the receiving servers).</span></span>  
  
- <span data-ttu-id="d454d-110">图底部的线表示每个 SQL Server 的 MessageBox 后台处理深度。</span><span class="sxs-lookup"><span data-stu-id="d454d-110">The lines at the bottom of the graph indicate the MessageBox spool depth on each of the SQL Servers.</span></span>  
  
  <span data-ttu-id="d454d-111">一旦系统驱动到最大稳定后台处理深度点，就会根据每秒收到的消息数来度量 MST。</span><span class="sxs-lookup"><span data-stu-id="d454d-111">Once the system is driven to the point of the maximum stable spool depth, MST is measured by the number of messages received per second.</span></span> <span data-ttu-id="d454d-112">对于此方案，在描述的硬件上，MST 已达到每秒 290 条消息。</span><span class="sxs-lookup"><span data-stu-id="d454d-112">For this scenario, on the hardware described, an MST of 290 messages per second was achieved.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d454d-113">如果系统驱动到某个点，在该点上后台处理深度经过一段时间后不再稳定，则说明已超出 MST。</span><span class="sxs-lookup"><span data-stu-id="d454d-113">Once the system is driven to a point where the spool depth is no longer stable over time, MST has been exceeded.</span></span> <span data-ttu-id="d454d-114">对于评估最大负载，需要基于不同的负载进行若干测试，而在此最大负载上，后台处理深度可以保持稳定，并且系统可在不产生其他消息积压的情况下处理消息积压。</span><span class="sxs-lookup"><span data-stu-id="d454d-114">Several test runs with varying load may be required to evaluate the maximum load at which spool depth remains stable and your system can handle the message backlog without incurring additional message backlog.</span></span>  
  
 <span data-ttu-id="d454d-115">所有 BizTalk 部署性能分析部分均应包括检查某些关键指标以了解资源瓶颈。</span><span class="sxs-lookup"><span data-stu-id="d454d-115">Part of any analysis of a BizTalk deployment performance should include checking some key indicators to understand resource bottlenecks.</span></span> <span data-ttu-id="d454d-116">用于运行于最大可承受吞吐量下的此部署的关键度量及其度量值如下所示：</span><span class="sxs-lookup"><span data-stu-id="d454d-116">The key measures and their values used for this deployment running under maximum sustainable throughput were as follows:</span></span>  
  
 <span data-ttu-id="d454d-117">**CPU 使用率**</span><span class="sxs-lookup"><span data-stu-id="d454d-117">**CPU Utilization**</span></span>  
  
|<span data-ttu-id="d454d-118">“服务器”</span><span class="sxs-lookup"><span data-stu-id="d454d-118">Server</span></span>|<span data-ttu-id="d454d-119">平均 CPU 使用率</span><span class="sxs-lookup"><span data-stu-id="d454d-119">Average CPU Utilization</span></span>|  
|------------|-----------------------------|  
|<span data-ttu-id="d454d-120">BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d454d-120">BizTalk Servers</span></span>|<span data-ttu-id="d454d-121">55%</span><span class="sxs-lookup"><span data-stu-id="d454d-121">55%</span></span>|  
|<span data-ttu-id="d454d-122">SQL Server（主 MessageBox 服务器）</span><span class="sxs-lookup"><span data-stu-id="d454d-122">SQL Server (Master MessageBox Server)</span></span>|<span data-ttu-id="d454d-123">76%</span><span class="sxs-lookup"><span data-stu-id="d454d-123">76%</span></span>|  
|<span data-ttu-id="d454d-124">SQL Server（其他 MessageBox 服务器）</span><span class="sxs-lookup"><span data-stu-id="d454d-124">SQL Server (Other MessageBox Servers)</span></span>|<span data-ttu-id="d454d-125">83%</span><span class="sxs-lookup"><span data-stu-id="d454d-125">83%</span></span>|  
  
 <span data-ttu-id="d454d-126">**物理磁盘空闲时间**</span><span class="sxs-lookup"><span data-stu-id="d454d-126">**Physical Disk Idle Time**</span></span>  
  
|<span data-ttu-id="d454d-127">“服务器”</span><span class="sxs-lookup"><span data-stu-id="d454d-127">Server</span></span>|<span data-ttu-id="d454d-128">平均磁盘空闲时间</span><span class="sxs-lookup"><span data-stu-id="d454d-128">Average Disk Idle Time</span></span>|  
|------------|----------------------------|  
|<span data-ttu-id="d454d-129">用于所有 SQL Server 的平均值</span><span class="sxs-lookup"><span data-stu-id="d454d-129">Average for all SQL Servers</span></span>|<span data-ttu-id="d454d-130">69%</span><span class="sxs-lookup"><span data-stu-id="d454d-130">69%</span></span>|  
  
 <span data-ttu-id="d454d-131">**SQL Server 上的 SQL 锁**</span><span class="sxs-lookup"><span data-stu-id="d454d-131">**SQL Locks on SQL Server**</span></span>  
  
|<span data-ttu-id="d454d-132">参数</span><span class="sxs-lookup"><span data-stu-id="d454d-132">Parameter</span></span>|<span data-ttu-id="d454d-133">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="d454d-133">Value</span></span>|  
|---------------|-----------|  
|<span data-ttu-id="d454d-134">每秒平均总锁定超时（每个 SQL Server）</span><span class="sxs-lookup"><span data-stu-id="d454d-134">Average Total Lock Timeouts per second (per SQL Server)</span></span>|<span data-ttu-id="d454d-135">1980</span><span class="sxs-lookup"><span data-stu-id="d454d-135">1980</span></span>|  
|<span data-ttu-id="d454d-136">平均总锁定等待时间（毫秒）</span><span class="sxs-lookup"><span data-stu-id="d454d-136">Average Total Lock Wait Time (ms)</span></span>|<span data-ttu-id="d454d-137">495</span><span class="sxs-lookup"><span data-stu-id="d454d-137">495</span></span>|  
  
 <span data-ttu-id="d454d-138">在此测试期间，在 BizTalk 或 SQL Server 应用程序日志中未生成任何错误。</span><span class="sxs-lookup"><span data-stu-id="d454d-138">During this test no errors were generated in the BizTalk or SQL Server application log.</span></span>  
  
 <span data-ttu-id="d454d-139">通过此数据，我们可以得出以下结论：</span><span class="sxs-lookup"><span data-stu-id="d454d-139">From this data, we can draw the following conclusions:</span></span>  
  
- <span data-ttu-id="d454d-140">在我们的系统中没有明显的资源瓶颈。</span><span class="sxs-lookup"><span data-stu-id="d454d-140">There are no obvious resource bottlenecks in our system.</span></span>  
  
- <span data-ttu-id="d454d-141">所有这些指标均处于运行状况良好的范围内。</span><span class="sxs-lookup"><span data-stu-id="d454d-141">All of these indicators are well within healthy limits.</span></span>  
  
- <span data-ttu-id="d454d-142">CPU 和磁盘空闲时间显示存在大量余量，甚至没有接近限定标准。</span><span class="sxs-lookup"><span data-stu-id="d454d-142">CPU and Disk Idle Times show that there is plenty of headroom and they are not even close to being pegged.</span></span>  
  
- <span data-ttu-id="d454d-143">SQL 锁指标美观**Lock Timeouts/sec**不会启动以会成为问题之前解决 5000 左右 （具体取决于您的 SQL Server) 并锁定等待时间在 1 秒以下也很正常。</span><span class="sxs-lookup"><span data-stu-id="d454d-143">The SQL lock indicators look good, **Lock Timeouts/sec** doesn’t start to become an issue until around 5000 or so (depending on your SQL Server) and Lock Wait times under 1 second are also healthy.</span></span>  
  
  <span data-ttu-id="d454d-144">我们已介绍了如何确定最大可承受吞吐量以及可承受、运行状况良好的系统的关键指标，现在，让我们来探讨与接收速度快于处理速度和垃圾回收速度的系统相关联的某些行为。</span><span class="sxs-lookup"><span data-stu-id="d454d-144">Now that we have shown how to find the maximum sustainable throughput and seen what the key indicators look like for a sustainable, healthy system, let’s explore some behavior associated with a system that is receiving faster than it is processing and collecting garbage.</span></span> <span data-ttu-id="d454d-145">请继续执行[据以加快负载测试](../core/overdrive-load-test.md)。</span><span class="sxs-lookup"><span data-stu-id="d454d-145">Proceed to [Overdrive Load Test](../core/overdrive-load-test.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d454d-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="d454d-146">See Also</span></span>  
 <span data-ttu-id="d454d-147">[测量引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span><span class="sxs-lookup"><span data-stu-id="d454d-147">[Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span></span>  
 [<span data-ttu-id="d454d-148">过载测试</span><span class="sxs-lookup"><span data-stu-id="d454d-148">Overdrive Load Test</span></span>](../core/overdrive-load-test.md)