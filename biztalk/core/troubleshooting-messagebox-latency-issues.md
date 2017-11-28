---
title: "MessageBox 延迟问题疑难解答 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9eb5789-80bd-40d4-8c27-7ae117fd9232
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e37fc970230bf218bcfd820611fb6b87322e535
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-messagebox-latency-issues"></a><span data-ttu-id="2b88a-102">MessageBox 延迟问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="2b88a-102">Troubleshooting MessageBox Latency Issues</span></span>
<span data-ttu-id="2b88a-103">理想情况下，在将消息发布到 MessageBox 数据库后，所有消息都将被处理和传送，并且 MessageBox 数据库永远不会变得过大。</span><span class="sxs-lookup"><span data-stu-id="2b88a-103">In a perfect world, all messages would be processed and delivered as soon as they were published to the MessageBox database and the MessageBox database would never grow to an excessive size.</span></span> <span data-ttu-id="2b88a-104">MessageBox 中所有不再被引用的消息将立即由定期清理 MessageBox 数据库表的 SQL 代理作业删除。</span><span class="sxs-lookup"><span data-stu-id="2b88a-104">Any messages in the MessageBox that were no longer referenced would immediately be removed by the SQL agent jobs that periodically clean up the MessageBox database tables.</span></span>  
  
 <span data-ttu-id="2b88a-105">但是在实际情况下，通常不是以可预测的线性方式来接收消息，并且 SQL 代理作业需要时间来清理 MessageBox 数据库表。</span><span class="sxs-lookup"><span data-stu-id="2b88a-105">In real world scenarios, however, messages are not typically received in a predictable, linear fashion and the SQL agent jobs require time to clean up the MessageBox database tables.</span></span>  
  
 <span data-ttu-id="2b88a-106">因此在某些情况下，MessageBox 可能会迅速变得相当大。</span><span class="sxs-lookup"><span data-stu-id="2b88a-106">Therefore, in some scenarios; the MessageBox can grow fairly large very quickly.</span></span>  
  
 <span data-ttu-id="2b88a-107">以下各项原因可能会导致 MessageBox 变得过大并因此影响整体性能：</span><span class="sxs-lookup"><span data-stu-id="2b88a-107">The following items can cause the MessageBox to grow excessively large and hinder overall performance:</span></span>  
  
-   <span data-ttu-id="2b88a-108">**"允许主机跟踪"选项设置了 Biztalk 主机实例停止**。</span><span class="sxs-lookup"><span data-stu-id="2b88a-108">**The Biztalk Host instance that has the "allow Host tracking" option set is stopped**.</span></span> <span data-ttu-id="2b88a-109">这是负责将跟踪数据从 MessageBox 数据库移至 Biztalk 跟踪数据库 (BizTalkDTADb) 的主机。</span><span class="sxs-lookup"><span data-stu-id="2b88a-109">This is the host that is responsible for moving the tracking data from the MessageBox database to the Biztalk Tracking database(BizTalkDTADb).</span></span>  
  
-   <span data-ttu-id="2b88a-110">**SQL Server 代理未运行**可能的原因是未运行负责将数据从 MessageBox 数据库移到 [随后清除已移动的数据在 MessageBox] BizTalkDTADb 数据库的 SQL 作业。</span><span class="sxs-lookup"><span data-stu-id="2b88a-110">**SQL Server Agent is not running** This can happen if the SQL jobs responsible for moving data from the MessageBox database to the BizTalkDTADb database [subsequently purging the moved data in the MessageBox] are not running.</span></span> <span data-ttu-id="2b88a-111">SQL 代理服务必须始终运行以避免出现此问题。</span><span class="sxs-lookup"><span data-stu-id="2b88a-111">It is imperative the SQL Agent Service be running all the time to avoid this problem.</span></span>  
  
-   <span data-ttu-id="2b88a-112">**SQL Server 作业被禁用**即使 SQL Server 代理正在运行，则务必无默认 SQL Server 作业被禁用。</span><span class="sxs-lookup"><span data-stu-id="2b88a-112">**SQL Server Jobs are disabled** Even if the SQL Server Agent is running, it is imperative that none of the default SQL Server jobs be disabled.</span></span>  
  
-   <span data-ttu-id="2b88a-113">**BizTalkDTADb 数据库增长过**可能的原因是 BizTalkDTADb 数据库增长过大，导致插入到 BizTalkDTADb 数据库需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="2b88a-113">**BizTalkDTADb database grows excessively** This can happen if the BizTalkDTADb database grows very large, causing inserts into the BizTalkDTADb database to take longer.</span></span> <span data-ttu-id="2b88a-114">发生这种情况时，通过跟踪数据传送服务 (TDDS) 移动数据的速度会减慢，从而导致在 MessageBox 数据库中产生积压。</span><span class="sxs-lookup"><span data-stu-id="2b88a-114">When this happens the movement of data by Tracking Data Delivery Service (TDDS) slows down, causing a backlog build up in the MessageBox database.</span></span> <span data-ttu-id="2b88a-115">要避免出现这种问题，SQL Server 必须定期对 BizTalkDTADb 数据库执行存档和清除作业。</span><span class="sxs-lookup"><span data-stu-id="2b88a-115">To avoid this problem it is important to run the SQL server archive and purge jobs periodically on the BizTalkDTADb databases.</span></span>  
  
-   <span data-ttu-id="2b88a-116">**过多的磁盘 I/O 延迟**如果到 MessageBox 数据库的数据的传入速率速度快于系统可以处理并将数据移到 BizTalkDTADb 数据库积压工作可以建立 MessageBox 数据库中。</span><span class="sxs-lookup"><span data-stu-id="2b88a-116">**Excessive Disk I/O Latency** If the incoming rate of data into the MessageBox database is faster than which the system can process and move the data to the BizTalkDTADb database, backlog can build up in the MessageBox database.</span></span> <span data-ttu-id="2b88a-117">如果积压的数据持续增加，则这将是一个很严重的问题，并且系统性能将随着时间推移而下降。</span><span class="sxs-lookup"><span data-stu-id="2b88a-117">If the backlog continues to grow unabated, this is a very serious problem and system performance will degrade over time.</span></span> <span data-ttu-id="2b88a-118">一种缓解此问题的方法是安装速度较快的磁盘和/或升级硬件，以帮助确保系统能够消除随着时间的推移而产生的任何消息积压现象。</span><span class="sxs-lookup"><span data-stu-id="2b88a-118">One way to alleviate this problem is to install faster disks and/or upgrade the hardware to help ensure that the system is capable of recovering from any message backlogs experienced over time.</span></span>  
  
## <a name="plan-for-the-future"></a><span data-ttu-id="2b88a-119">未来规划</span><span class="sxs-lookup"><span data-stu-id="2b88a-119">Plan for the Future</span></span>  
 <span data-ttu-id="2b88a-120">即使按照上述所有的最佳实践执行操作，随着时间的推移，移至 BizTalkDTADb 数据库的跟踪数据量也将变得很大。</span><span class="sxs-lookup"><span data-stu-id="2b88a-120">Even though all the best practices above are followed, over time the volume of tracking data moved to the BizTalkDTADb database will grow very large.</span></span> <span data-ttu-id="2b88a-121">实施数据库维护计划以定期存档跟踪数据是非常重要的，以使系统的执行性能保持最佳。</span><span class="sxs-lookup"><span data-stu-id="2b88a-121">It is important to implement a database maintenance plan to periodically archive tracking data so that the system can continue to perform optimally.</span></span>  
  
 <span data-ttu-id="2b88a-122">可在 BizTalkDTADb 数据库中保留的历史数据量取决于通过系统推送的消息量。</span><span class="sxs-lookup"><span data-stu-id="2b88a-122">The amount of historical data that can be retained in the BizTalkDTADb database depends on the volume of messages pushed through the system.</span></span> <span data-ttu-id="2b88a-123">对于工作负担不重和吞吐量不高的系统，数据库的增长速度会较慢，并且可以将更多的历史数据保留在 BizTalkDTADb 数据库中。</span><span class="sxs-lookup"><span data-stu-id="2b88a-123">For systems that are not subjected to high stress and throughput this database will grow at a slower rate and it will be possible to retain more historical data in the BizTalkDTADb database.</span></span>  
  
 <span data-ttu-id="2b88a-124">建议在 BizTalkDTADb 数据库中保留尽可能少的数据，以免影响运行时性能。</span><span class="sxs-lookup"><span data-stu-id="2b88a-124">It is recommended to retain minimal data in the BizTalkDTADb database so that runtime performance is not sacrificed.</span></span>