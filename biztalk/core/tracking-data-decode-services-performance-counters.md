---
title: "跟踪数据解码服务性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 733450b1-71b5-48a4-9ac3-cd880324440c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99ec03138e455c671e9ccb69aa8bc4c5588d287c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tracking-data-decode-services-performance-counters"></a><span data-ttu-id="d2054-102">跟踪数据解码服务性能计数器</span><span class="sxs-lookup"><span data-stu-id="d2054-102">Tracking Data Decode Services Performance Counters</span></span>
<span data-ttu-id="d2054-103">使用性能计数器可以监视服务在站点或系统上执行的工作的特定方面。</span><span class="sxs-lookup"><span data-stu-id="d2054-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="d2054-104">性能计数器能够帮助您标识和解决有关服务器性能的问题。</span><span class="sxs-lookup"><span data-stu-id="d2054-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="d2054-105">以下性能计数器进行访问每个主机实例下**BizTalk:TDDS**性能对象类别：</span><span class="sxs-lookup"><span data-stu-id="d2054-105">The following performance counters are accessible for each host instance under the **BizTalk:TDDS** performance object category:</span></span>  
  
|<span data-ttu-id="d2054-106">**类别**</span><span class="sxs-lookup"><span data-stu-id="d2054-106">**Category**</span></span>|<span data-ttu-id="d2054-107">**计数器**</span><span class="sxs-lookup"><span data-stu-id="d2054-107">**Counter**</span></span>|<span data-ttu-id="d2054-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="d2054-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="d2054-109">BizTalk:TDDS</span><span class="sxs-lookup"><span data-stu-id="d2054-109">BizTalk:TDDS</span></span>|<span data-ttu-id="d2054-110">Batches being processed</span><span class="sxs-lookup"><span data-stu-id="d2054-110">Batches being processed</span></span>|<span data-ttu-id="d2054-111">当前 SQL 事务中要处理的批次数量。</span><span class="sxs-lookup"><span data-stu-id="d2054-111">The number of batches that are being processed inside the current SQL transaction.</span></span>|  
||<span data-ttu-id="d2054-112">Batches committed</span><span class="sxs-lookup"><span data-stu-id="d2054-112">Batches committed</span></span>|<span data-ttu-id="d2054-113">提交给目标数据库的批次数量。</span><span class="sxs-lookup"><span data-stu-id="d2054-113">The number of batches committed to the destination database.</span></span>|  
||<span data-ttu-id="d2054-114">Events being processed</span><span class="sxs-lookup"><span data-stu-id="d2054-114">Events being processed</span></span>|<span data-ttu-id="d2054-115">当前 SQL 事务中要处理的事件数量。</span><span class="sxs-lookup"><span data-stu-id="d2054-115">The number of events that are being processed inside of the current SQL transaction.</span></span>|  
||<span data-ttu-id="d2054-116">Event Committed</span><span class="sxs-lookup"><span data-stu-id="d2054-116">Event Committed</span></span>|<span data-ttu-id="d2054-117">此秒内提交给目标数据库的事件数。</span><span class="sxs-lookup"><span data-stu-id="d2054-117">The number of events committed to the destination database within this second.</span></span>|  
||<span data-ttu-id="d2054-118">Records being processed</span><span class="sxs-lookup"><span data-stu-id="d2054-118">Records being processed</span></span>|<span data-ttu-id="d2054-119">当前 SQL 事务中要处理的记录数量。</span><span class="sxs-lookup"><span data-stu-id="d2054-119">The number of records that are being processed inside the current SQL transaction.</span></span>|  
||<span data-ttu-id="d2054-120">Records Committed</span><span class="sxs-lookup"><span data-stu-id="d2054-120">Records Committed</span></span>|<span data-ttu-id="d2054-121">此秒内提交给目标数据库的记录数。</span><span class="sxs-lookup"><span data-stu-id="d2054-121">The number of records committed to the destination database during this second.</span></span>|  
||<span data-ttu-id="d2054-122">Total Batches</span><span class="sxs-lookup"><span data-stu-id="d2054-122">Total Batches</span></span>|<span data-ttu-id="d2054-123">TDDS 处理的总批数。</span><span class="sxs-lookup"><span data-stu-id="d2054-123">Total batches processed by TDDS.</span></span>|  
||<span data-ttu-id="d2054-124">Total Events</span><span class="sxs-lookup"><span data-stu-id="d2054-124">Total Events</span></span>|<span data-ttu-id="d2054-125">TDDS 处理的总事件数。</span><span class="sxs-lookup"><span data-stu-id="d2054-125">Total events processed by TDDS.</span></span>|  
||<span data-ttu-id="d2054-126">Total Failed Batches</span><span class="sxs-lookup"><span data-stu-id="d2054-126">Total Failed Batches</span></span>|<span data-ttu-id="d2054-127">TDDS 无法运行的总批数。</span><span class="sxs-lookup"><span data-stu-id="d2054-127">Total batches failed to run by TDDS.</span></span>|  
||<span data-ttu-id="d2054-128">Total Failed Events</span><span class="sxs-lookup"><span data-stu-id="d2054-128">Total Failed Events</span></span>|<span data-ttu-id="d2054-129">TDDS 无法运行的总事件数。</span><span class="sxs-lookup"><span data-stu-id="d2054-129">Total events failed to run by TDDS.</span></span>|  
||<span data-ttu-id="d2054-130">Total Records</span><span class="sxs-lookup"><span data-stu-id="d2054-130">Total Records</span></span>|<span data-ttu-id="d2054-131">TDDS 处理的总记录数。</span><span class="sxs-lookup"><span data-stu-id="d2054-131">Total records processed by TDDS.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="d2054-132">访问性能计数器</span><span class="sxs-lookup"><span data-stu-id="d2054-132">To access performance counters</span></span>  
 <span data-ttu-id="d2054-133">依照下述步骤访问性能计数器。</span><span class="sxs-lookup"><span data-stu-id="d2054-133">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="d2054-134">如果您使用的是 Windows 2008</span><span class="sxs-lookup"><span data-stu-id="d2054-134">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="d2054-135">单击**启动**，指向**管理工具**，然后单击**性能监视器**。</span><span class="sxs-lookup"><span data-stu-id="d2054-135">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="d2054-136">在**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="d2054-136">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="d2054-137">在**添加计数器**对话框中，从**可用计数器**列表中，展开**BizTalk:TDDS**性能计数器对象，然后选择要监视的计数器</span><span class="sxs-lookup"><span data-stu-id="d2054-137">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:TDDS** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="d2054-138">在**实例的所选对象**列表中，选择要监视的所选计数器，然后单击的特定实例**添加**。</span><span class="sxs-lookup"><span data-stu-id="d2054-138">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="d2054-139">若要选择的所有可用的计数器实例，选择\<**所有实例**>。</span><span class="sxs-lookup"><span data-stu-id="d2054-139">To select all available counter instances, select \<**All instances**>.</span></span>  
  
5.  <span data-ttu-id="d2054-140">添加计数器后, 单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d2054-140">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="d2054-141">所选的性能计数器显示在**性能监视器**屏幕。</span><span class="sxs-lookup"><span data-stu-id="d2054-141">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2054-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2054-142">See Also</span></span>  
 <span data-ttu-id="d2054-143">[性能提示和技巧](../core/performance-tips-and-tricks.md) </span><span class="sxs-lookup"><span data-stu-id="d2054-143">[Performance Tips and Tricks](../core/performance-tips-and-tricks.md) </span></span>  
 <span data-ttu-id="d2054-144">[测量的最大可持续引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="d2054-144">[Measuring Maximum Sustainable Engine Throughput](../core/measuring-maximum-sustainable-engine-throughput.md) </span></span>  
 <span data-ttu-id="d2054-145">[测量的最大可持续跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="d2054-145">[Measuring Maximum Sustainable Tracking Throughput](../core/measuring-maximum-sustainable-tracking-throughput.md) </span></span>  
 [<span data-ttu-id="d2054-146">通过主机限制的优化资源使用情况</span><span class="sxs-lookup"><span data-stu-id="d2054-146">Optimizing Resource Usage Through Host Throttling</span></span>](../core/optimizing-resource-usage-through-host-throttling.md)