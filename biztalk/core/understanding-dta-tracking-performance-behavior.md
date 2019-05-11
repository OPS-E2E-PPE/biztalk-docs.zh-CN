---
title: 了解 DTA 跟踪性能行为 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b1a70951-bfed-435c-97f4-0b28a8e4e4dc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 409138a38b75aebdd4e2df63d23e301dae483738
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292677"
---
# <a name="understanding-dta-tracking-performance-behavior"></a><span data-ttu-id="f8e8f-102">了解 DTA 跟踪性能行为</span><span class="sxs-lookup"><span data-stu-id="f8e8f-102">Understanding DTA Tracking Performance Behavior</span></span>
<span data-ttu-id="f8e8f-103">确定 DTA 跟踪的最大可承受吞吐量 (MST) 的主要因素是：</span><span class="sxs-lookup"><span data-stu-id="f8e8f-103">The primary factors that determine maximum sustainable throughput (MST) for DTA tracking are:</span></span>  
  
- <span data-ttu-id="f8e8f-104">所需的消息吞吐量，即，每时间单位，系统收到的消息。</span><span class="sxs-lookup"><span data-stu-id="f8e8f-104">The desired message throughput, that is, messages received per unit time, for the system.</span></span>  
  
- <span data-ttu-id="f8e8f-105">正在为每个消息跟踪数据量。</span><span class="sxs-lookup"><span data-stu-id="f8e8f-105">How much data is being tracked for each message.</span></span>  
  
- <span data-ttu-id="f8e8f-106">多长时间，数据将被清除前，即，数据保留时段 live BizTalkDTADb 数据库中。</span><span class="sxs-lookup"><span data-stu-id="f8e8f-106">How long the data is to live in the BizTalkDTADb database before being purged, that is, the data retention window.</span></span>  
  
- <span data-ttu-id="f8e8f-107">该值指示是否将 BizTalkDTADb 数据是存档，以及清除。</span><span class="sxs-lookup"><span data-stu-id="f8e8f-107">Whether or not the BizTalkDTADb data is archived as well as purged.</span></span> <span data-ttu-id="f8e8f-108">存档是可选的但必须定期执行清除。</span><span class="sxs-lookup"><span data-stu-id="f8e8f-108">Archiving is optional but purging must be performed periodically.</span></span>  
  
  <span data-ttu-id="f8e8f-109">还有一件事，所有这些因素具有共同点： DTA 可以接受和处理的速度 （存档和清除） 数据。</span><span class="sxs-lookup"><span data-stu-id="f8e8f-109">There is one thing that all of these factors have in common: the speed at which the DTA can accept and process (archive and purge) data.</span></span>  
  
## <a name="how-the-biztalkdtadb-insert-and-processing-speed-affects-your-system"></a><span data-ttu-id="f8e8f-110">BizTalkDTADb 插入和处理速度如何影响您的系统</span><span class="sxs-lookup"><span data-stu-id="f8e8f-110">How the BizTalkDTADb Insert and Processing Speed Affects Your System</span></span>  
 <span data-ttu-id="f8e8f-111">现在，让我们逐步跟踪程序中所述的数据通道[测量的最大可承受跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)，并评估系统的各个组件的 BizTalkDTADb 插入和处理速度的影响。</span><span class="sxs-lookup"><span data-stu-id="f8e8f-111">Now, let’s walk through the tracking data pathway that is described in [Measuring Maximum Sustainable Tracking Throughput](../core/measuring-maximum-sustainable-tracking-throughput.md), and evaluate the affect of BizTalkDTADb insert and processing speed on the various components of the system.</span></span>  
  
 <span data-ttu-id="f8e8f-112">从 trackingdata 和后台处理表开始，我们可以想象，如果将数据从这些表移至 BizTalkDTADb 数据库的进程不能将数据插入 BizTalkDTADb 数据库至少尽可能快地运行时将插入到trackingdata 和后台处理表，然后在后台处理和 trackingdata 表将开始积压。</span><span class="sxs-lookup"><span data-stu-id="f8e8f-112">Starting with the trackingdata and spool tables, we can imagine that, if the processes that move data from these tables to the BizTalkDTADb database are not able to insert data into the BizTalkDTADb database at least as fast as the runtime is inserting into the trackingdata and spool tables, then the spool and trackingdata tables will start to build up a backlog.</span></span> <span data-ttu-id="f8e8f-113">这不一定是坏事在短期内，只要您知道将降低消息吞吐量以便积压工作以最终耗尽。</span><span class="sxs-lookup"><span data-stu-id="f8e8f-113">This isn’t necessarily a bad thing in the short term as long as you know the message throughput will be reduced to allow the backlog to eventually drain.</span></span> <span data-ttu-id="f8e8f-114">但是，只要数据仍处于 spool 或 trackingdata 表，它将不能用于查询中的任何其他工具或组中心页上跟踪查询 BizTalkDTADb 数据库中。</span><span class="sxs-lookup"><span data-stu-id="f8e8f-114">However, as long as the data is still sitting in the spool or trackingdata tables, it will not be available in the BizTalkDTADb database for querying by tracking queries on the Group Hub page or any other tool.</span></span>  <span data-ttu-id="f8e8f-115">因此它不会解决问题的方法很有用。</span><span class="sxs-lookup"><span data-stu-id="f8e8f-115">Thus it will not be useful for problem resolution.</span></span> <span data-ttu-id="f8e8f-116">因此任何预期的积压期间必须足够短，被跟踪的信息是及时中仍然可用但应出现问题时需要使用 BizTalkDTADb 数据进行调查。</span><span class="sxs-lookup"><span data-stu-id="f8e8f-116">Therefore any expected backlog periods must be short enough that the tracked information is still available in a timely fashion should a problem arise that needs to be investigated using BizTalkDTADb data.</span></span>  
  
 <span data-ttu-id="f8e8f-117">从测试中，我们知道，这并不将跟踪数据移到 BizTalkDTADb 数据库 （即，TDDS 和 TrackedMessages_Copy_BizTalkMsgBoxDb） 的决定因素如果积压累积了，但在 BizTalkDTADb 数据库的速度的进程接受输入。</span><span class="sxs-lookup"><span data-stu-id="f8e8f-117">From testing, we know that it isn’t the processes that move tracking data to the BizTalkDTADb database (that is, TDDS and TrackedMessages_Copy_BizTalkMsgBoxDb) that are the determining factor if a backlog builds up, but the speed of the BizTalkDTADb database in accepting the input.</span></span> <span data-ttu-id="f8e8f-118">通常情况下，它是受到 I/O 限制的 BizTalkDTADb 数据库数据文件。</span><span class="sxs-lookup"><span data-stu-id="f8e8f-118">Typically, it is the data file of the BizTalkDTADb database that is I/O bound.</span></span> <span data-ttu-id="f8e8f-119">也就是说，它是驱动器的 BizTalkDTADb 数据库数据文件所驻留的速度将确定 DTA 的整体速度。</span><span class="sxs-lookup"><span data-stu-id="f8e8f-119">That is, it is the speed of the drive that the BizTalkDTADb database data file resides on that will determine the speed of the DTA overall.</span></span>  
  
## <a name="how-the-amount-of-data-in-biztalkdtadb-affects-io-speed"></a><span data-ttu-id="f8e8f-120">BizTalkDTADb 中的数据量如何影响 I/O 速度</span><span class="sxs-lookup"><span data-stu-id="f8e8f-120">How the Amount of Data in BizTalkDTADb Affects I/O Speed</span></span>  
 <span data-ttu-id="f8e8f-121">与 I/O 速度相关的另一个关键因素是 BizTalkDTADb 数据库中的数据量： 为跟踪中的数据量 BizTalkDTADb 数据库增加而增加，BizTalkDTADb 数据库的输入和处理速度将下降，因为只需更多的数据若要插入新数据，以及这会影响每个插入所需的 I/O 量，对通过进行排序。</span><span class="sxs-lookup"><span data-stu-id="f8e8f-121">Another key factor related to the I/O speed is the amount of data in the BizTalkDTADb database: as the amount of tracked data in the BizTalkDTADb database increases, the input and processing speed of the BizTalkDTADb database decreases since there is simply more data to sort through as new data is inserted, and this affects the amount of I/O required for each insert.</span></span>  
  
 <span data-ttu-id="f8e8f-122">这是在其中存档和清除输入图片由于它是这些进程使得 BizTalkDTADb 数据库增长得太大，无法跟上。</span><span class="sxs-lookup"><span data-stu-id="f8e8f-122">This is where archiving and purging enter the picture since it is these processes that keep the BizTalkDTADb database from growing too large to keep up.</span></span> <span data-ttu-id="f8e8f-123">基本理念是确保 BizTalkDTADb 数据库大小保留内容开始备份中的后台处理和 trackingdata 表级别之下。</span><span class="sxs-lookup"><span data-stu-id="f8e8f-123">The basic idea is to make sure that the BizTalkDTADb database size is kept below the level at which things begin to backup in the spool and trackingdata tables.</span></span> <span data-ttu-id="f8e8f-124">但是，在 DTA 清除和存档 (BizTalkDTADb) SQL 作业中实现的清除和存档进程也需要资源 （CPU、 内存和尤其是 I/O） 从度量 MST 时必须考虑到 BizTalkDTADb 数据库服务器跟踪。</span><span class="sxs-lookup"><span data-stu-id="f8e8f-124">However, the purge and archive processes implemented in the DTA Purge and Archive (BizTalkDTADb) SQL Job also require resources (CPU, Memory, and especially I/O) from the BizTalkDTADb database server, which must be taken into account when measuring MST with tracking.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8e8f-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8e8f-125">See Also</span></span>  
 <span data-ttu-id="f8e8f-126">[测量最大可承受跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md) </span><span class="sxs-lookup"><span data-stu-id="f8e8f-126">[Measuring Maximum Sustainable Tracking Throughput](../core/measuring-maximum-sustainable-tracking-throughput.md) </span></span>  
 <span data-ttu-id="f8e8f-127">[测量 DTA 跟踪的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md) </span><span class="sxs-lookup"><span data-stu-id="f8e8f-127">[Test Scenarios for Measuring MST of DTA Tracking](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md) </span></span>  
 <span data-ttu-id="f8e8f-128">[DTA 跟踪的 Mst 的提示和技巧](../core/tips-and-tricks-for-finding-mst-of-dta-tracking.md) </span><span class="sxs-lookup"><span data-stu-id="f8e8f-128">[Tips and Tricks for Finding MST of DTA Tracking](../core/tips-and-tricks-for-finding-mst-of-dta-tracking.md) </span></span>  
 [<span data-ttu-id="f8e8f-129">跟踪数据库的大小调整准则</span><span class="sxs-lookup"><span data-stu-id="f8e8f-129">Tracking Database Sizing Guidelines</span></span>](../core/tracking-database-sizing-guidelines.md)