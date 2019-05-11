---
title: 跟踪数据解码服务性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 733450b1-71b5-48a4-9ac3-cd880324440c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 944baf51a1ca10edc157f2062a6883d77ddffeb0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313899"
---
# <a name="tracking-data-decode-services-performance-counters"></a><span data-ttu-id="425bb-102">跟踪数据解码服务性能计数器</span><span class="sxs-lookup"><span data-stu-id="425bb-102">Tracking Data Decode Services Performance Counters</span></span>
<span data-ttu-id="425bb-103">性能计数器允许你监视的工作上的站点或系统服务执行的特定方面。</span><span class="sxs-lookup"><span data-stu-id="425bb-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="425bb-104">性能计数器可以帮助您确定和解决服务器性能问题。</span><span class="sxs-lookup"><span data-stu-id="425bb-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="425bb-105">以下性能计数器都可以访问每个主机实例下**biztalk: Tdds**性能对象类别：</span><span class="sxs-lookup"><span data-stu-id="425bb-105">The following performance counters are accessible for each host instance under the **BizTalk:TDDS** performance object category:</span></span>  
  
|<span data-ttu-id="425bb-106">**类别**</span><span class="sxs-lookup"><span data-stu-id="425bb-106">**Category**</span></span>|<span data-ttu-id="425bb-107">**计数器**</span><span class="sxs-lookup"><span data-stu-id="425bb-107">**Counter**</span></span>|<span data-ttu-id="425bb-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="425bb-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="425bb-109">BizTalk:TDDS</span><span class="sxs-lookup"><span data-stu-id="425bb-109">BizTalk:TDDS</span></span>|<span data-ttu-id="425bb-110">正在处理的批处理</span><span class="sxs-lookup"><span data-stu-id="425bb-110">Batches being processed</span></span>|<span data-ttu-id="425bb-111">当前 SQL 事务中要处理的批数。</span><span class="sxs-lookup"><span data-stu-id="425bb-111">The number of batches that are being processed inside the current SQL transaction.</span></span>|  
||<span data-ttu-id="425bb-112">已提交的批</span><span class="sxs-lookup"><span data-stu-id="425bb-112">Batches committed</span></span>|<span data-ttu-id="425bb-113">提交到目标数据库的批数。</span><span class="sxs-lookup"><span data-stu-id="425bb-113">The number of batches committed to the destination database.</span></span>|  
||<span data-ttu-id="425bb-114">正在处理的事件</span><span class="sxs-lookup"><span data-stu-id="425bb-114">Events being processed</span></span>|<span data-ttu-id="425bb-115">当前 SQL 事务中要处理的事件数。</span><span class="sxs-lookup"><span data-stu-id="425bb-115">The number of events that are being processed inside of the current SQL transaction.</span></span>|  
||<span data-ttu-id="425bb-116">已提交的事件</span><span class="sxs-lookup"><span data-stu-id="425bb-116">Event Committed</span></span>|<span data-ttu-id="425bb-117">这一秒内提交到目标数据库的事件数。</span><span class="sxs-lookup"><span data-stu-id="425bb-117">The number of events committed to the destination database within this second.</span></span>|  
||<span data-ttu-id="425bb-118">正在处理的记录</span><span class="sxs-lookup"><span data-stu-id="425bb-118">Records being processed</span></span>|<span data-ttu-id="425bb-119">当前 SQL 事务中要处理的记录数。</span><span class="sxs-lookup"><span data-stu-id="425bb-119">The number of records that are being processed inside the current SQL transaction.</span></span>|  
||<span data-ttu-id="425bb-120">已提交的记录</span><span class="sxs-lookup"><span data-stu-id="425bb-120">Records Committed</span></span>|<span data-ttu-id="425bb-121">这一秒内提交到目标数据库的记录数。</span><span class="sxs-lookup"><span data-stu-id="425bb-121">The number of records committed to the destination database during this second.</span></span>|  
||<span data-ttu-id="425bb-122">总批</span><span class="sxs-lookup"><span data-stu-id="425bb-122">Total Batches</span></span>|<span data-ttu-id="425bb-123">TDDS 处理的总批。</span><span class="sxs-lookup"><span data-stu-id="425bb-123">Total batches processed by TDDS.</span></span>|  
||<span data-ttu-id="425bb-124">Total Events</span><span class="sxs-lookup"><span data-stu-id="425bb-124">Total Events</span></span>|<span data-ttu-id="425bb-125">TDDS 处理的事件总数。</span><span class="sxs-lookup"><span data-stu-id="425bb-125">Total events processed by TDDS.</span></span>|  
||<span data-ttu-id="425bb-126">失败的批处理的总数</span><span class="sxs-lookup"><span data-stu-id="425bb-126">Total Failed Batches</span></span>|<span data-ttu-id="425bb-127">总批运行失败的 TDDS。</span><span class="sxs-lookup"><span data-stu-id="425bb-127">Total batches failed to run by TDDS.</span></span>|  
||<span data-ttu-id="425bb-128">失败事件总数</span><span class="sxs-lookup"><span data-stu-id="425bb-128">Total Failed Events</span></span>|<span data-ttu-id="425bb-129">无法运行的 TDDS 事件总数。</span><span class="sxs-lookup"><span data-stu-id="425bb-129">Total events failed to run by TDDS.</span></span>|  
||<span data-ttu-id="425bb-130">记录总数</span><span class="sxs-lookup"><span data-stu-id="425bb-130">Total Records</span></span>|<span data-ttu-id="425bb-131">TDDS 处理的总记录。</span><span class="sxs-lookup"><span data-stu-id="425bb-131">Total records processed by TDDS.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="425bb-132">若要访问性能计数器</span><span class="sxs-lookup"><span data-stu-id="425bb-132">To access performance counters</span></span>  
 <span data-ttu-id="425bb-133">使用以下步骤访问性能计数器。</span><span class="sxs-lookup"><span data-stu-id="425bb-133">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="425bb-134">如果您使用的 Windows 2008</span><span class="sxs-lookup"><span data-stu-id="425bb-134">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="425bb-135">单击**启动**，依次指向**管理工具**，然后单击**性能监视器**。</span><span class="sxs-lookup"><span data-stu-id="425bb-135">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="425bb-136">在中**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="425bb-136">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="425bb-137">在中**添加计数器**对话框中，从**可用的计数器**列表中，展开**biztalk: Tdds**性能计数器对象，然后选择要监视的计数器</span><span class="sxs-lookup"><span data-stu-id="425bb-137">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:TDDS** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="425bb-138">在中**选定对象的实例**列表中，选择要监视的所选的计数器，然后单击的特定实例**添加**。</span><span class="sxs-lookup"><span data-stu-id="425bb-138">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="425bb-139">若要选择的所有可用的计数器实例，请选择\<**所有实例**\>。</span><span class="sxs-lookup"><span data-stu-id="425bb-139">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="425bb-140">添加计数器之后, 单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="425bb-140">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="425bb-141">所选的性能计数器随即显示在**性能监视器**屏幕。</span><span class="sxs-lookup"><span data-stu-id="425bb-141">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="425bb-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="425bb-142">See Also</span></span>  
 <span data-ttu-id="425bb-143">[性能提示和技巧](../core/performance-tips-and-tricks.md) </span><span class="sxs-lookup"><span data-stu-id="425bb-143">[Performance Tips and Tricks](../core/performance-tips-and-tricks.md) </span></span>  
 <span data-ttu-id="425bb-144">[测量最大可承受引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="425bb-144">[Measuring Maximum Sustainable Engine Throughput](../core/measuring-maximum-sustainable-engine-throughput.md) </span></span>  
 <span data-ttu-id="425bb-145">[测量最大可承受跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="425bb-145">[Measuring Maximum Sustainable Tracking Throughput](../core/measuring-maximum-sustainable-tracking-throughput.md) </span></span>  
 [<span data-ttu-id="425bb-146">通过主机阻止优化资源使用情况</span><span class="sxs-lookup"><span data-stu-id="425bb-146">Optimizing Resource Usage Through Host Throttling</span></span>](../core/optimizing-resource-usage-through-host-throttling.md)