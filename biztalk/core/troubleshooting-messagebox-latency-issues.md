---
title: MessageBox 延迟问题疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9eb5789-80bd-40d4-8c27-7ae117fd9232
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d62bbe76a618b03c4cd57d764152e250ecbc3ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295710"
---
# <a name="troubleshooting-messagebox-latency-issues"></a><span data-ttu-id="adebd-102">MessageBox 延迟问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="adebd-102">Troubleshooting MessageBox Latency Issues</span></span>
<span data-ttu-id="adebd-103">在理想情况下，所有消息将进行处理和传递只要它们所发布到 MessageBox 数据库和 MessageBox 数据库将会永远不会增长过大。</span><span class="sxs-lookup"><span data-stu-id="adebd-103">In a perfect world, all messages would be processed and delivered as soon as they were published to the MessageBox database and the MessageBox database would never grow to an excessive size.</span></span> <span data-ttu-id="adebd-104">定期清理 MessageBox 数据库表的 SQL 代理作业会立即删除不再被引用的任何消息在 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="adebd-104">Any messages in the MessageBox that were no longer referenced would immediately be removed by the SQL agent jobs that periodically clean up the MessageBox database tables.</span></span>  
  
 <span data-ttu-id="adebd-105">但是，在实际情况下，消息不会以可预测的线性方式通常接收和 SQL 代理作业需要时间来清理 MessageBox 数据库表。</span><span class="sxs-lookup"><span data-stu-id="adebd-105">In real world scenarios, however, messages are not typically received in a predictable, linear fashion and the SQL agent jobs require time to clean up the MessageBox database tables.</span></span>  
  
 <span data-ttu-id="adebd-106">因此，在某些情况下;MessageBox 可以非常快速地增长相当大。</span><span class="sxs-lookup"><span data-stu-id="adebd-106">Therefore, in some scenarios; the MessageBox can grow fairly large very quickly.</span></span>  
  
 <span data-ttu-id="adebd-107">以下各项可能会导致 MessageBox 变得过大并因此影响整体性能：</span><span class="sxs-lookup"><span data-stu-id="adebd-107">The following items can cause the MessageBox to grow excessively large and hinder overall performance:</span></span>  
  
-   <span data-ttu-id="adebd-108">**发送设置"允许主机跟踪"选项的 Biztalk 主机实例停止**。</span><span class="sxs-lookup"><span data-stu-id="adebd-108">**The Biztalk Host instance that has the "allow Host tracking" option set is stopped**.</span></span> <span data-ttu-id="adebd-109">这是负责将跟踪数据从 MessageBox 数据库移至 Biztalk 跟踪数据库 （biztalkdtadb） 的主机。</span><span class="sxs-lookup"><span data-stu-id="adebd-109">This is the host that is responsible for moving the tracking data from the MessageBox database to the Biztalk Tracking database(BizTalkDTADb).</span></span>  
  
-   <span data-ttu-id="adebd-110">**SQL Server 代理未运行**未运行的 SQL 作业负责将数据从 MessageBox 数据库移至 BizTalkDTADb 数据库 [随后清除所移动的数据在 MessageBox 中] 如果发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="adebd-110">**SQL Server Agent is not running** This can happen if the SQL jobs responsible for moving data from the MessageBox database to the BizTalkDTADb database [subsequently purging the moved data in the MessageBox] are not running.</span></span> <span data-ttu-id="adebd-111">它是命令性 SQL 代理服务运行所有的时间，若要避免此问题。</span><span class="sxs-lookup"><span data-stu-id="adebd-111">It is imperative the SQL Agent Service be running all the time to avoid this problem.</span></span>  
  
-   <span data-ttu-id="adebd-112">**SQL Server 作业被禁用**即使 SQL Server 代理正在运行，也是命令性，无默认 SQL Server 作业被禁用。</span><span class="sxs-lookup"><span data-stu-id="adebd-112">**SQL Server Jobs are disabled** Even if the SQL Server Agent is running, it is imperative that none of the default SQL Server jobs be disabled.</span></span>  
  
-   <span data-ttu-id="adebd-113">**BizTalkDTADb 数据库增长过快**如果 BizTalkDTADb 数据库变得非常大，导致插入到 BizTalkDTADb 数据库需要更长时间发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="adebd-113">**BizTalkDTADb database grows excessively** This can happen if the BizTalkDTADb database grows very large, causing inserts into the BizTalkDTADb database to take longer.</span></span> <span data-ttu-id="adebd-114">在此情况下移动数据的方式来跟踪数据传送服务 (TDDS) 速度变慢，导致 MessageBox 数据库中的积压工作逐渐累积。</span><span class="sxs-lookup"><span data-stu-id="adebd-114">When this happens the movement of data by Tracking Data Delivery Service (TDDS) slows down, causing a backlog build up in the MessageBox database.</span></span> <span data-ttu-id="adebd-115">若要避免此问题是必须运行 SQL server 存档和清除作业定期对 BizTalkDTADb 数据库。</span><span class="sxs-lookup"><span data-stu-id="adebd-115">To avoid this problem it is important to run the SQL server archive and purge jobs periodically on the BizTalkDTADb databases.</span></span>  
  
-   <span data-ttu-id="adebd-116">**过多的磁盘 I/O 延迟**如果到 MessageBox 数据库中的数据的传入速率速度比系统可以处理更快，并将数据移到 BizTalkDTADb 数据库中，会产生积压在 MessageBox 数据库中。</span><span class="sxs-lookup"><span data-stu-id="adebd-116">**Excessive Disk I/O Latency** If the incoming rate of data into the MessageBox database is faster than which the system can process and move the data to the BizTalkDTADb database, backlog can build up in the MessageBox database.</span></span> <span data-ttu-id="adebd-117">如果积压工作数据持续增加，这是很严重的问题，随着时间的推移将会降低系统性能。</span><span class="sxs-lookup"><span data-stu-id="adebd-117">If the backlog continues to grow unabated, this is a very serious problem and system performance will degrade over time.</span></span> <span data-ttu-id="adebd-118">若要缓解此问题的一种方法是安装速度更快的磁盘和/或升级硬件，以帮助确保系统能够从任何消息积压现象随着时间的推移恢复。</span><span class="sxs-lookup"><span data-stu-id="adebd-118">One way to alleviate this problem is to install faster disks and/or upgrade the hardware to help ensure that the system is capable of recovering from any message backlogs experienced over time.</span></span>  
  
## <a name="plan-for-the-future"></a><span data-ttu-id="adebd-119">规划未来</span><span class="sxs-lookup"><span data-stu-id="adebd-119">Plan for the Future</span></span>  
 <span data-ttu-id="adebd-120">即使遵循所有遵循上述最佳做法，随时间的跟踪数据量移至 BizTalkDTADb 数据库将变得很大。</span><span class="sxs-lookup"><span data-stu-id="adebd-120">Even though all the best practices above are followed, over time the volume of tracking data moved to the BizTalkDTADb database will grow very large.</span></span> <span data-ttu-id="adebd-121">请务必实施数据库维护计划以定期存档跟踪数据，以便系统可以继续以最佳方式执行。</span><span class="sxs-lookup"><span data-stu-id="adebd-121">It is important to implement a database maintenance plan to periodically archive tracking data so that the system can continue to perform optimally.</span></span>  
  
 <span data-ttu-id="adebd-122">可以保留在 BizTalkDTADb 数据库中的历史数据量取决于通过系统推送的消息量。</span><span class="sxs-lookup"><span data-stu-id="adebd-122">The amount of historical data that can be retained in the BizTalkDTADb database depends on the volume of messages pushed through the system.</span></span> <span data-ttu-id="adebd-123">对于系统，而不能用于高压力和数据库的增长速度较慢的吞吐量，并将有可能保留在 BizTalkDTADb 数据库中的多个历史数据。</span><span class="sxs-lookup"><span data-stu-id="adebd-123">For systems that are not subjected to high stress and throughput this database will grow at a slower rate and it will be possible to retain more historical data in the BizTalkDTADb database.</span></span>  
  
 <span data-ttu-id="adebd-124">建议保留在 BizTalkDTADb 数据库中的最小数据，以便运行时性能不丧失。</span><span class="sxs-lookup"><span data-stu-id="adebd-124">It is recommended to retain minimal data in the BizTalkDTADb database so that runtime performance is not sacrificed.</span></span>