---
title: "了解 DTA 跟踪性能行为 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b1a70951-bfed-435c-97f4-0b28a8e4e4dc
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 278d1e3c4b52c14c68d692ce3d3a3179d15bb10b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="understanding-dta-tracking-performance-behavior"></a><span data-ttu-id="5ef8d-102">了解 DTA 跟踪性能行为</span><span class="sxs-lookup"><span data-stu-id="5ef8d-102">Understanding DTA Tracking Performance Behavior</span></span>
<span data-ttu-id="5ef8d-103">有关跟踪的 DTA 确定最大可持续吞吐量 (MST) 的主要因素是：</span><span class="sxs-lookup"><span data-stu-id="5ef8d-103">The primary factors that determine maximum sustainable throughput (MST) for DTA tracking are:</span></span>  
  
-   <span data-ttu-id="5ef8d-104">所需的消息吞吐量，即每时间单位，系统收到的消息。</span><span class="sxs-lookup"><span data-stu-id="5ef8d-104">The desired message throughput, that is, messages received per unit time, for the system.</span></span>  
  
-   <span data-ttu-id="5ef8d-105">正在为每个消息跟踪数据量。</span><span class="sxs-lookup"><span data-stu-id="5ef8d-105">How much data is being tracked for each message.</span></span>  
  
-   <span data-ttu-id="5ef8d-106">数据在被清除前在 BizTalkDTADb 数据库中存活多长时间，即数据保留时段。</span><span class="sxs-lookup"><span data-stu-id="5ef8d-106">How long the data is to live in the BizTalkDTADb database before being purged, that is, the data retention window.</span></span>  
  
-   <span data-ttu-id="5ef8d-107">是否存档和清除 BizTalkDTADb 数据。</span><span class="sxs-lookup"><span data-stu-id="5ef8d-107">Whether or not the BizTalkDTADb data is archived as well as purged.</span></span> <span data-ttu-id="5ef8d-108">存档是可选的，但清除必须定期执行。</span><span class="sxs-lookup"><span data-stu-id="5ef8d-108">Archiving is optional but purging must be performed periodically.</span></span>  
  
 <span data-ttu-id="5ef8d-109">有一点，所有这些因素具有共同点： DTA 可以接受并处理的速度 （存档和清除） 的数据。</span><span class="sxs-lookup"><span data-stu-id="5ef8d-109">There is one thing that all of these factors have in common: the speed at which the DTA can accept and process (archive and purge) data.</span></span>  
  
## <a name="how-the-biztalkdtadb-insert-and-processing-speed-affects-your-system"></a><span data-ttu-id="5ef8d-110">BizTalkDTADb 插入和处理速度如何影响您的系统</span><span class="sxs-lookup"><span data-stu-id="5ef8d-110">How the BizTalkDTADb Insert and Processing Speed Affects Your System</span></span>  
 <span data-ttu-id="5ef8d-111">现在，让我们逐步完成跟踪程序中所述的数据通道[测量最大的可持续跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)，并对系统的各个组件的 BizTalkDTADb insert 和处理速度的影响进行评估。</span><span class="sxs-lookup"><span data-stu-id="5ef8d-111">Now, let’s walk through the tracking data pathway that is described in [Measuring Maximum Sustainable Tracking Throughput](../core/measuring-maximum-sustainable-tracking-throughput.md), and evaluate the affect of BizTalkDTADb insert and processing speed on the various components of the system.</span></span>  
  
 <span data-ttu-id="5ef8d-112">从 trackingdata 表和 spool 表开始，我们可以假设，如果在将数据从这些表移到 BizTalkDTADb 数据库的进程中，将数据插入 BizTalkDTADb 数据库的速度无法与运行时将数据插入 trackingdata 表和 spool 表的速度至少相当，则 trackingdata 表和 spool 表将开始积压。</span><span class="sxs-lookup"><span data-stu-id="5ef8d-112">Starting with the trackingdata and spool tables, we can imagine that, if the processes that move data from these tables to the BizTalkDTADb database are not able to insert data into the BizTalkDTADb database at least as fast as the runtime is inserting into the trackingdata and spool tables, then the spool and trackingdata tables will start to build up a backlog.</span></span> <span data-ttu-id="5ef8d-113">只要您知道将降低消息吞吐量以便最终消除积压，短期内上述情况不见得就是坏事。</span><span class="sxs-lookup"><span data-stu-id="5ef8d-113">This isn’t necessarily a bad thing in the short term as long as you know the message throughput will be reduced to allow the backlog to eventually drain.</span></span> <span data-ttu-id="5ef8d-114">但是，只要数据仍处于 spool 或 trackingdata 表中，就无法在 BizTalkDTADb 数据库中使用“组中心”页中的跟踪查询或任何其他工具对这些数据进行查询。</span><span class="sxs-lookup"><span data-stu-id="5ef8d-114">However, as long as the data is still sitting in the spool or trackingdata tables, it will not be available in the BizTalkDTADb database for querying by tracking queries on the Group Hub page or any other tool.</span></span>  <span data-ttu-id="5ef8d-115">因此，它对解决问题没有作用。</span><span class="sxs-lookup"><span data-stu-id="5ef8d-115">Thus it will not be useful for problem resolution.</span></span> <span data-ttu-id="5ef8d-116">因此，任何预期的积压期间都必须足够短，以便只要发生需要使用 BizTalkDTADb 数据进行调查的问题，仍可以及时地利用跟踪的信息予以解决。</span><span class="sxs-lookup"><span data-stu-id="5ef8d-116">Therefore any expected backlog periods must be short enough that the tracked information is still available in a timely fashion should a problem arise that needs to be investigated using BizTalkDTADb data.</span></span>  
  
 <span data-ttu-id="5ef8d-117">从测试，我们知道它并不将跟踪数据移动到如果积压建立，是决定因素 BizTalkDTADb 数据库 （即，TDDS 和 TrackedMessages_Copy_BizTalkMsgBoxDb） 但 BizTalkDTADb 数据库中的速度的进程接受输入。</span><span class="sxs-lookup"><span data-stu-id="5ef8d-117">From testing, we know that it isn’t the processes that move tracking data to the BizTalkDTADb database (that is, TDDS and TrackedMessages_Copy_BizTalkMsgBoxDb) that are the determining factor if a backlog builds up, but the speed of the BizTalkDTADb database in accepting the input.</span></span> <span data-ttu-id="5ef8d-118">通常，这是受到 I/O 限制的 BizTalkDTADb 数据库的数据文件。</span><span class="sxs-lookup"><span data-stu-id="5ef8d-118">Typically, it is the data file of the BizTalkDTADb database that is I/O bound.</span></span> <span data-ttu-id="5ef8d-119">即，决定因素是 BizTalkDTADb 数据库数据文件所驻留的驱动器的速度，该速度将确定 DTA 的整体速度。</span><span class="sxs-lookup"><span data-stu-id="5ef8d-119">That is, it is the speed of the drive that the BizTalkDTADb database data file resides on that will determine the speed of the DTA overall.</span></span>  
  
## <a name="how-the-amount-of-data-in-biztalkdtadb-affects-io-speed"></a><span data-ttu-id="5ef8d-120">BizTalkDTADb 中的数据量如何影响 I/O 速度</span><span class="sxs-lookup"><span data-stu-id="5ef8d-120">How the Amount of Data in BizTalkDTADb Affects I/O Speed</span></span>  
 <span data-ttu-id="5ef8d-121">与 I/O 速度相关的另一个关键因素是 BizTalkDTADb 数据库中的数据量： 为跟踪中的数据量 BizTalkDTADb 数据库增加，BizTalkDTADb 数据库的输入和处理速度降低由于没有只需更多的数据若要插入新数据，以及这会影响的每个插入所需的 I/O 数量，对通过进行排序。</span><span class="sxs-lookup"><span data-stu-id="5ef8d-121">Another key factor related to the I/O speed is the amount of data in the BizTalkDTADb database: as the amount of tracked data in the BizTalkDTADb database increases, the input and processing speed of the BizTalkDTADb database decreases since there is simply more data to sort through as new data is inserted, and this affects the amount of I/O required for each insert.</span></span>  
  
 <span data-ttu-id="5ef8d-122">这就是为什么要考虑存档和清除操作，因为就是这些进程使得 BizTalkDTADb 数据库增长得过大，以致难以维护。</span><span class="sxs-lookup"><span data-stu-id="5ef8d-122">This is where archiving and purging enter the picture since it is these processes that keep the BizTalkDTADb database from growing too large to keep up.</span></span> <span data-ttu-id="5ef8d-123">因此，基本思路就是：确保 BizTalkDTADb 数据库大小保持在较低的级别，其级别要低于不得不开始在 spool 表和 trackingdata 表中进行备份的级别。</span><span class="sxs-lookup"><span data-stu-id="5ef8d-123">The basic idea is to make sure that the BizTalkDTADb database size is kept below the level at which things begin to backup in the spool and trackingdata tables.</span></span> <span data-ttu-id="5ef8d-124">但是，在 DTA 清除和存档 (BizTalkDTADb) SQL 作业中实现的清除和存档进程也要求来自 BizTalkDTADb 数据库服务器的资源（CPU、内存，尤其是 I/O），在度量与跟踪有关的 MST 时必须将此考虑在内。</span><span class="sxs-lookup"><span data-stu-id="5ef8d-124">However, the purge and archive processes implemented in the DTA Purge and Archive (BizTalkDTADb) SQL Job also require resources (CPU, Memory, and especially I/O) from the BizTalkDTADb database server, which must be taken into account when measuring MST with tracking.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ef8d-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ef8d-125">See Also</span></span>  
 <span data-ttu-id="5ef8d-126">[测量的最大可持续跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="5ef8d-126">[Measuring Maximum Sustainable Tracking Throughput](../core/measuring-maximum-sustainable-tracking-throughput.md) </span></span>  
 <span data-ttu-id="5ef8d-127">[用于测量 MST DTA 跟踪测试方案](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md) </span><span class="sxs-lookup"><span data-stu-id="5ef8d-127">[Test Scenarios for Measuring MST of DTA Tracking](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md) </span></span>  
 <span data-ttu-id="5ef8d-128">[查找的跟踪的 DTA MST 的提示和技巧](../core/tips-and-tricks-for-finding-mst-of-dta-tracking.md) </span><span class="sxs-lookup"><span data-stu-id="5ef8d-128">[Tips and Tricks for Finding MST of DTA Tracking](../core/tips-and-tricks-for-finding-mst-of-dta-tracking.md) </span></span>  
 [<span data-ttu-id="5ef8d-129">跟踪数据库的大小调整准则</span><span class="sxs-lookup"><span data-stu-id="5ef8d-129">Tracking Database Sizing Guidelines</span></span>](../core/tracking-database-sizing-guidelines.md)