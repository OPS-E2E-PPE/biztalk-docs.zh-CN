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
ms.openlocfilehash: d059f7f2aa29be68ea87d72d9357d01601d2c958
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321775"
---
# <a name="sustainable-load-test"></a><span data-ttu-id="f25a6-102">可承受负载测试</span><span class="sxs-lookup"><span data-stu-id="f25a6-102">Sustainable Load Test</span></span>
<span data-ttu-id="f25a6-103">本主题中的信息中所述的测试是指[测量的引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md)。</span><span class="sxs-lookup"><span data-stu-id="f25a6-103">The information in this topic refers to the tests explained in [Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md).</span></span>  
  
 <span data-ttu-id="f25a6-104">第一个测试时，系统驱动到 MST，以便可以进行观察系统正常运行。</span><span class="sxs-lookup"><span data-stu-id="f25a6-104">For the first test, the system was driven to MST so that observations of a healthy system can be made.</span></span>  
  
 <span data-ttu-id="f25a6-105">下图显示了使用这种方法来查找测试系统的最大可承受吞吐量后的关键指标。</span><span class="sxs-lookup"><span data-stu-id="f25a6-105">The following graph shows key indicators after using this approach to find the maximum sustainable throughput of the test system.</span></span>  
  
 <span data-ttu-id="f25a6-106">**可承受负载测试的负载状况**</span><span class="sxs-lookup"><span data-stu-id="f25a6-106">**Load profile of sustainable load test**</span></span>  
  
 <span data-ttu-id="f25a6-107">![性能监视器测量可承受负载](../core/media/bts06-sustainable-load.gif "BTS06_Sustainable_Load")</span><span class="sxs-lookup"><span data-stu-id="f25a6-107">![Performance monitor measuring sustainable load](../core/media/bts06-sustainable-load.gif "BTS06_Sustainable_Load")</span></span>  
  
 <span data-ttu-id="f25a6-108">此图显示，以小时为单位的测试，后台处理深度非常稳定并且没有增长：</span><span class="sxs-lookup"><span data-stu-id="f25a6-108">This graph shows that, for the hour of the test, the spool depth was stable and not growing:</span></span>  
  
- <span data-ttu-id="f25a6-109">在关系图的顶部的黑线显示每秒接收的系统 （例如，对于这两个接收服务器） 的消息总数。</span><span class="sxs-lookup"><span data-stu-id="f25a6-109">The black lines at the top of the graph show the total messages received per second by the system (for example, for both of the receiving servers).</span></span>  
  
- <span data-ttu-id="f25a6-110">在关系图底部的线指示每个 SQL 服务器上的 MessageBox 后台处理深度。</span><span class="sxs-lookup"><span data-stu-id="f25a6-110">The lines at the bottom of the graph indicate the MessageBox spool depth on each of the SQL Servers.</span></span>  
  
  <span data-ttu-id="f25a6-111">一旦系统驱动到最大稳定后台处理深度点，是每秒接收的消息数来度量 MST。</span><span class="sxs-lookup"><span data-stu-id="f25a6-111">Once the system is driven to the point of the maximum stable spool depth, MST is measured by the number of messages received per second.</span></span> <span data-ttu-id="f25a6-112">对于此方案，如所述，在硬件上每秒 290 个消息的 MST 是来实现的。</span><span class="sxs-lookup"><span data-stu-id="f25a6-112">For this scenario, on the hardware described, an MST of 290 messages per second was achieved.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f25a6-113">一旦系统驱动到某个点的后台处理深度不再稳定随着时间的推移，说明已超出 MST。</span><span class="sxs-lookup"><span data-stu-id="f25a6-113">Once the system is driven to a point where the spool depth is no longer stable over time, MST has been exceeded.</span></span> <span data-ttu-id="f25a6-114">与基于不同的负载的多个测试运行可能需要评估在哪个后台处理深度可以保持稳定的最大负载，您的系统可以处理的消息积压，而不会产生更多的消息积压工作。</span><span class="sxs-lookup"><span data-stu-id="f25a6-114">Several test runs with varying load may be required to evaluate the maximum load at which spool depth remains stable and your system can handle the message backlog without incurring additional message backlog.</span></span>  
  
 <span data-ttu-id="f25a6-115">所有 BizTalk 部署性能分析的一部分应包括检查某些关键指标以了解资源瓶颈。</span><span class="sxs-lookup"><span data-stu-id="f25a6-115">Part of any analysis of a BizTalk deployment performance should include checking some key indicators to understand resource bottlenecks.</span></span> <span data-ttu-id="f25a6-116">关键度量值和最大可承受吞吐量下运行此部署使用其值是按如下所示：</span><span class="sxs-lookup"><span data-stu-id="f25a6-116">The key measures and their values used for this deployment running under maximum sustainable throughput were as follows:</span></span>  
  
 <span data-ttu-id="f25a6-117">**CPU 使用率**</span><span class="sxs-lookup"><span data-stu-id="f25a6-117">**CPU Utilization**</span></span>  
  
|<span data-ttu-id="f25a6-118">“服务器”</span><span class="sxs-lookup"><span data-stu-id="f25a6-118">Server</span></span>|<span data-ttu-id="f25a6-119">平均 CPU 利用率</span><span class="sxs-lookup"><span data-stu-id="f25a6-119">Average CPU Utilization</span></span>|  
|------------|-----------------------------|  
|<span data-ttu-id="f25a6-120">BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f25a6-120">BizTalk Servers</span></span>|<span data-ttu-id="f25a6-121">55%</span><span class="sxs-lookup"><span data-stu-id="f25a6-121">55%</span></span>|  
|<span data-ttu-id="f25a6-122">SQL Server (Master MessageBox Server)</span><span class="sxs-lookup"><span data-stu-id="f25a6-122">SQL Server (Master MessageBox Server)</span></span>|<span data-ttu-id="f25a6-123">76%</span><span class="sxs-lookup"><span data-stu-id="f25a6-123">76%</span></span>|  
|<span data-ttu-id="f25a6-124">SQL Server （其他 MessageBox 服务器）</span><span class="sxs-lookup"><span data-stu-id="f25a6-124">SQL Server (Other MessageBox Servers)</span></span>|<span data-ttu-id="f25a6-125">83%</span><span class="sxs-lookup"><span data-stu-id="f25a6-125">83%</span></span>|  
  
 <span data-ttu-id="f25a6-126">**物理磁盘空闲时间**</span><span class="sxs-lookup"><span data-stu-id="f25a6-126">**Physical Disk Idle Time**</span></span>  
  
|<span data-ttu-id="f25a6-127">“服务器”</span><span class="sxs-lookup"><span data-stu-id="f25a6-127">Server</span></span>|<span data-ttu-id="f25a6-128">平均磁盘空闲时间</span><span class="sxs-lookup"><span data-stu-id="f25a6-128">Average Disk Idle Time</span></span>|  
|------------|----------------------------|  
|<span data-ttu-id="f25a6-129">所有 SQL Server 的平均值</span><span class="sxs-lookup"><span data-stu-id="f25a6-129">Average for all SQL Servers</span></span>|<span data-ttu-id="f25a6-130">69%</span><span class="sxs-lookup"><span data-stu-id="f25a6-130">69%</span></span>|  
  
 <span data-ttu-id="f25a6-131">**SQL Server 上的 SQL 锁**</span><span class="sxs-lookup"><span data-stu-id="f25a6-131">**SQL Locks on SQL Server**</span></span>  
  
|<span data-ttu-id="f25a6-132">参数</span><span class="sxs-lookup"><span data-stu-id="f25a6-132">Parameter</span></span>|<span data-ttu-id="f25a6-133">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="f25a6-133">Value</span></span>|  
|---------------|-----------|  
|<span data-ttu-id="f25a6-134">平均总锁定超时每个第二个 （每个 SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f25a6-134">Average Total Lock Timeouts per second (per SQL Server)</span></span>|<span data-ttu-id="f25a6-135">1980</span><span class="sxs-lookup"><span data-stu-id="f25a6-135">1980</span></span>|  
|<span data-ttu-id="f25a6-136">平均总锁定等待时间 （毫秒）</span><span class="sxs-lookup"><span data-stu-id="f25a6-136">Average Total Lock Wait Time (ms)</span></span>|<span data-ttu-id="f25a6-137">495</span><span class="sxs-lookup"><span data-stu-id="f25a6-137">495</span></span>|  
  
 <span data-ttu-id="f25a6-138">在此测试期间未在 BizTalk 或 SQL Server 应用程序日志中不生成任何错误。</span><span class="sxs-lookup"><span data-stu-id="f25a6-138">During this test no errors were generated in the BizTalk or SQL Server application log.</span></span>  
  
 <span data-ttu-id="f25a6-139">通过此数据，我们可以得出以下结论：</span><span class="sxs-lookup"><span data-stu-id="f25a6-139">From this data, we can draw the following conclusions:</span></span>  
  
- <span data-ttu-id="f25a6-140">在我们的系统没有明显的资源瓶颈。</span><span class="sxs-lookup"><span data-stu-id="f25a6-140">There are no obvious resource bottlenecks in our system.</span></span>  
  
- <span data-ttu-id="f25a6-141">所有这些指标是正常的限制范围内良好。</span><span class="sxs-lookup"><span data-stu-id="f25a6-141">All of these indicators are well within healthy limits.</span></span>  
  
- <span data-ttu-id="f25a6-142">CPU 和磁盘空闲时间显示没有充足的空间，它们甚至没有接近限定标准。</span><span class="sxs-lookup"><span data-stu-id="f25a6-142">CPU and Disk Idle Times show that there is plenty of headroom and they are not even close to being pegged.</span></span>  
  
- <span data-ttu-id="f25a6-143">SQL 锁指标美观**Lock Timeouts/sec**不会启动以会成为问题之前解决 5000 左右 （具体取决于您的 SQL Server) 并锁定等待时间在 1 秒以下也很正常。</span><span class="sxs-lookup"><span data-stu-id="f25a6-143">The SQL lock indicators look good, **Lock Timeouts/sec** doesn’t start to become an issue until around 5000 or so (depending on your SQL Server) and Lock Wait times under 1 second are also healthy.</span></span>  
  
  <span data-ttu-id="f25a6-144">现在，我们已展示了如何查找最大可承受吞吐量并可承受、 运行正常的系统的关键指标的如下所示，我们来探讨一些速度超过它正在处理和收集接收的系统相关联的行为垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="f25a6-144">Now that we have shown how to find the maximum sustainable throughput and seen what the key indicators look like for a sustainable, healthy system, let’s explore some behavior associated with a system that is receiving faster than it is processing and collecting garbage.</span></span> <span data-ttu-id="f25a6-145">请继续执行[据以加快负载测试](../core/overdrive-load-test.md)。</span><span class="sxs-lookup"><span data-stu-id="f25a6-145">Proceed to [Overdrive Load Test](../core/overdrive-load-test.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f25a6-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="f25a6-146">See Also</span></span>  
 <span data-ttu-id="f25a6-147">[测量引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span><span class="sxs-lookup"><span data-stu-id="f25a6-147">[Test Scenarios for Measuring MST of the Engine](../core/test-scenarios-for-measuring-mst-of-the-engine.md) </span></span>  
 [<span data-ttu-id="f25a6-148">过载测试</span><span class="sxs-lookup"><span data-stu-id="f25a6-148">Overdrive Load Test</span></span>](../core/overdrive-load-test.md)