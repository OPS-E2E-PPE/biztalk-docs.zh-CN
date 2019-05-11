---
title: 避免出现 DBNETLIB 异常 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fbee0cf-d249-4d98-8d16-168ded32f9f1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cc51bd9e997e4cca8526f855495b1ceec9f7e81
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358711"
---
# <a name="avoiding-dbnetlib-exceptions"></a><span data-ttu-id="fe119-102">避免出现 DBNETLIB 异常</span><span class="sxs-lookup"><span data-stu-id="fe119-102">Avoiding DBNETLIB Exceptions</span></span>
<span data-ttu-id="fe119-103">当 BizTalk Server 运行时无法与 MessageBox 或管理数据库进行通信时，将出现 DBNetLib （数据库网络库） 错误。</span><span class="sxs-lookup"><span data-stu-id="fe119-103">DBNetLib (Database Network Library) errors occur when the BizTalk Server runtime is unable to communicate with either the MessageBox or Management databases.</span></span> <span data-ttu-id="fe119-104">此操作时，会捕获此异常的 BizTalk Server 运行时实例关闭，然后循环每隔一分钟进行检查，请参阅数据库是否可用。</span><span class="sxs-lookup"><span data-stu-id="fe119-104">When this occurs, the BizTalk Server runtime instance that catches the exception shuts down and then cycles every minute to check to see if the database is available.</span></span>  
  
 <span data-ttu-id="fe119-105">DBNetLib 错误的最常见原因是当其中一台 （可能是多个） MessageBox 数据库服务器变得极其繁忙，进一步与之进行通信的尝试导致超时，这会导致出现 DBNetLib 异常。</span><span class="sxs-lookup"><span data-stu-id="fe119-105">The most common cause of a DBNetLib error is when one of the (possibly many) MessageBox database servers becomes extremely busy and further attempts to communicate with it result in a timeout, which causes a DBNetLib exception.</span></span>  
  
 <span data-ttu-id="fe119-106">如果 MessageBox 数据库是十分繁忙，除了 DBNetLib 错误可以发生在生产环境中时其中一个的多个 MessageBox 数据库的宿主 BizTalk 数据库服务器受到 I/O （输入/输出） 限制。</span><span class="sxs-lookup"><span data-stu-id="fe119-106">In addition to the case where the MessageBox database is simply very busy, the DBNetLib error can occur in a production environment when BizTalk database servers hosting one of more MessageBox databases become I/O (Input/Output) bound.</span></span>  
  
 <span data-ttu-id="fe119-107">本主题描述了可能会导致 DBNetLib 错误和建议避免这些错误的情况。</span><span class="sxs-lookup"><span data-stu-id="fe119-107">This topic describes conditions that can lead to DBNetLib errors and recommendations for avoiding these errors.</span></span>  
  
## <a name="cause-and-resolution-for-the-dbnetlib-error"></a><span data-ttu-id="fe119-108">原因和 DBNetLib 错误的解决方法</span><span class="sxs-lookup"><span data-stu-id="fe119-108">Cause and Resolution for the DBNetLib error</span></span>  
  
### <a name="symptoms-of-a-dbnetlib-error"></a><span data-ttu-id="fe119-109">DBNetLib 错误的症状</span><span class="sxs-lookup"><span data-stu-id="fe119-109">Symptoms of a DBNetLib error</span></span>  
 <span data-ttu-id="fe119-110">Microsoft BizTalk Server 主机实例将终止，然后重新启动自身，并类似于以下的错误写入到 BizTalk Server 应用程序日志：</span><span class="sxs-lookup"><span data-stu-id="fe119-110">A Microsoft BizTalk Server host instance terminates and then restarts itself, and errors that are similar to the following are written to the BizTalk Server Application log:</span></span>  
  
```  
Event Type:Warning  
Event Source:BizTalk Server <version>  
Event Category:BizTalk Server <version>   
Event ID:5410  
Computer:BIZTALKSERVER  
Description:  
An error occurred that requires the BizTalk service to terminate. The most common causes are the following:  
 1) An unexpected out of memory error.  
 OR  
 2) An inability to connect or a loss of connectivity to one of the BizTalk databases.   
 The service will shutdown and auto-restart in 1 minute. If the problematic database remains unavailable, this cycle will repeat.  
  
 Error message: [DBNETLIB][ConnectionWrite (send()).]General network error. Check your network documentation.  
 Error source:    
  
 BizTalk host name: BizTalkHost  
 Windows service name: BTSSvc$BizTalkHost   
  
---------------------------------------------------------  
Event Type:Error  
Event Source:BizTalk Server <version>  
Event Category:BizTalk Server <version>   
Event ID:6913  
Computer:BIZTALKSERVER  
Description:  
An attempt to connect to "BizTalkMsgBoxDb" SQL Server database on server "SQLSERVER " failed.  
 Error: "[DBNETLIB][ConnectionWrite (send()).]General network error. Check your network documentation."  
```  
  
### <a name="biztalk-database-servers-hosting-messagebox-databases-becoming-io-bound"></a><span data-ttu-id="fe119-111">受 I/O 的 MessageBox 数据库的宿主 BizTalk 数据库服务器绑定</span><span class="sxs-lookup"><span data-stu-id="fe119-111">BizTalk database servers hosting MessageBox databases becoming I/O bound</span></span>  
 <span data-ttu-id="fe119-112">BizTalk server 进行通信和直接与 MessageBox 数据库的宿主数据库服务器交互。</span><span class="sxs-lookup"><span data-stu-id="fe119-112">BizTalk servers communicate and act directly with the database servers hosting the MessageBox databases.</span></span> <span data-ttu-id="fe119-113">如果任何作为 MessageBox 数据库宿主的数据库服务器被过度占用，受到 I/O （输入/输出） 限制的情况下，则可能会停止响应。</span><span class="sxs-lookup"><span data-stu-id="fe119-113">If any of the database servers hosting the MessageBox databases get too consumed and gets into an I/O (Input/Output) bound situation, then it might become unresponsive.</span></span> <span data-ttu-id="fe119-114">BizTalk 服务器之一可能又会失去连接与这些数据库服务器之一，并将出现 DBNetLib 错误。</span><span class="sxs-lookup"><span data-stu-id="fe119-114">One of the BizTalk servers might in turn lose connectivity with one of those database servers, and a DBNetLib error will occur.</span></span>  
  
 <span data-ttu-id="fe119-115">我们的测试显示被高度占用的数据库服务器将受到 I/O 限制时的物理磁盘的"%idle 时间"继续降低并达到 10%以下。</span><span class="sxs-lookup"><span data-stu-id="fe119-115">Our tests show that a highly consumed database server becomes I/O bound when its physical disk’s "%Idle time" continues to drop and reaches below 10%.</span></span> <span data-ttu-id="fe119-116">如果"%idle 时间"继续降到该级别，这是你的数据库服务器是可能变得无响应的指示。</span><span class="sxs-lookup"><span data-stu-id="fe119-116">If the “%Idle time” continues to drop below that level, then this is an indication that your database server is likely to become unresponsive.</span></span>  
  
#### <a name="cause"></a><span data-ttu-id="fe119-117">原因</span><span class="sxs-lookup"><span data-stu-id="fe119-117">Cause</span></span>  
 <span data-ttu-id="fe119-118">有多种原因可导致 MessageBox 数据库受到 I/O 限制的宿主的数据库服务器，其中一些如下所示：</span><span class="sxs-lookup"><span data-stu-id="fe119-118">There are several reasons that can cause the database servers hosting the MessageBox databases to become I/O bound, some of these are the following:</span></span>  
  
-   <span data-ttu-id="fe119-119">如果 MessageBox 数据库的宿主数据库计算机绑定低的硬件规范，如： 低内存、 数量和速度的处理器等。</span><span class="sxs-lookup"><span data-stu-id="fe119-119">If the database machine hosting the MessageBox database is bound by low hardware specifications such as: low memory, number and speed of processors etc.</span></span>  
  
-   <span data-ttu-id="fe119-120">如果 MessageBox 数据库的宿主数据库计算机上的物理磁盘是共享由其他高度占用的数据库。</span><span class="sxs-lookup"><span data-stu-id="fe119-120">If the physical disk on the database machine hosting a MessageBox database is being shared by other highly consumed databases.</span></span> <span data-ttu-id="fe119-121">在情况下时 （包括 MessageBox） 的多个数据库同时被高度占用一次物理磁盘会处于 I/O 绑定情况。</span><span class="sxs-lookup"><span data-stu-id="fe119-121">In cases when several databases (including the MessageBox) are being highly consumed at the same time, the physical disk can get into an I/O bound situation.</span></span>  
  
     <span data-ttu-id="fe119-122">以下是此情况的一个示例：</span><span class="sxs-lookup"><span data-stu-id="fe119-122">An example of such a situation is the following:</span></span>  
  
     <span data-ttu-id="fe119-123">我们有时会承载 BizTalkDTADb 和/或 BAM 数据库的数据库服务器占用高百分比的物理磁盘 %disk 读和写数的测试显示。</span><span class="sxs-lookup"><span data-stu-id="fe119-123">Our tests show that the database server hosting the BizTalkDTADb and/or BAM databases sometimes consume high percentages of a physical disk’s %Disk Read and Write Times.</span></span> <span data-ttu-id="fe119-124">当承载 MessageBox 数据库的数据库服务器磁盘是正在由另一个高度占用的共享数据库，例如 BizTalkDTADb 或 BAM，并且如果这两个数据库同时被高度占用，则可能会导致数据库服务器的物理磁盘受到 I/O绑定，然后停止响应。</span><span class="sxs-lookup"><span data-stu-id="fe119-124">When the database server disk that hosts a MessageBox database is being shared by another highly consumed database such as BizTalkDTADb or BAM, and if both databases are highly consumed simultaneously, they might cause the database server physical disk to become I/O bound and then unresponsive.</span></span>  
  
-   <span data-ttu-id="fe119-125">如果 BizTalkDTADb 与一个或多个 MessageBox 数据库共享相同的物理磁盘的数据库服务器上，如果存档和清除不经常运行，该磁盘可能受到 I/O 限制。</span><span class="sxs-lookup"><span data-stu-id="fe119-125">If BizTalkDTADb and one or more of the MessageBox databases are sharing the same physical disk on the database server, if archiving and purging is not being run frequently, the disk might become I/O bound.</span></span>  
  
#### <a name="resolution"></a><span data-ttu-id="fe119-126">解决方法</span><span class="sxs-lookup"><span data-stu-id="fe119-126">Resolution</span></span>  
 <span data-ttu-id="fe119-127">请确保承载 BizTalk MessageBox(s) 的数据库服务器不要进入这样的情况下，被高度占用并可能停止响应。</span><span class="sxs-lookup"><span data-stu-id="fe119-127">Ensure the database server(s) hosting the BizTalk MessageBox(s) do not get into a situation where they become highly consumed and possibly unresponsive.</span></span>  
  
 <span data-ttu-id="fe119-128">服务器磁盘被高度占用的主要原因下面列出了一些以及如何缓解此问题的建议。</span><span class="sxs-lookup"><span data-stu-id="fe119-128">Some of the primary causes of a server disk becoming highly consumed are listed below along with recommendations on how to mitigate this problem.</span></span>  
  
##### <a name="low-hardware-specs"></a><span data-ttu-id="fe119-129">硬件规格较低</span><span class="sxs-lookup"><span data-stu-id="fe119-129">Low Hardware Specs</span></span>  
 <span data-ttu-id="fe119-130">我们的测试表明，该服务器会更多使用时的硬件规格无法跟上它正在尝试处理的负载量。</span><span class="sxs-lookup"><span data-stu-id="fe119-130">Our tests show that the server starts getting more consumed when its hardware specifications cannot keep up with the amount of load it’s trying to process.</span></span> <span data-ttu-id="fe119-131">硬件规格较低，系统通过在数据库上发生的活动量迅速瘫痪。</span><span class="sxs-lookup"><span data-stu-id="fe119-131">With lower hardware specs, the system gets overwhelmed quickly by the amount of activities happening on the databases.</span></span> <span data-ttu-id="fe119-132">这可能会导致服务器的 %disk 读和写数继续增加，不能稳定，还磁盘的空闲时间百分比继续降低并达到 10%，这可能会导致你的数据库服务器停止响应。</span><span class="sxs-lookup"><span data-stu-id="fe119-132">This might cause the server’s %Disk Read and Write Times to continue increasing without stabilizing, also the disk’s %Idle time to continue to decrease and become lower than 10%, and this might cause your database server to become unresponsive.</span></span>  
  
 <span data-ttu-id="fe119-133">根据活动和对 BizTalk 部署的负载量，如果您发现您听到负载较高的期间无响应的数据库服务器，则应考虑升级数据库服务器中的以下部分： Cpu、 内存的数目并连接到 SAN。</span><span class="sxs-lookup"><span data-stu-id="fe119-133">Depending on the amount of activities and load you have on your BizTalk deployment, if you find that you are getting unresponsive database servers during to high loads, you should consider upgrading the following parts in your database servers: number of CPUs, memory, and connecting to a SAN.</span></span> <span data-ttu-id="fe119-134">当然，您应该为适当的诊断，找出哪些部分 （内存、 Cpu 数量等） 是需要升级硬件中的瓶颈。</span><span class="sxs-lookup"><span data-stu-id="fe119-134">Of course, you should do the proper diagnosis to figure out which part (memory, number of CPUs etc.) is the bottleneck that needs to be upgraded in your hardware.</span></span>  
  
##### <a name="sharing-one-server-or-disk-for-more-than-one-group-of-biztalk-databases"></a><span data-ttu-id="fe119-135">共享一个服务器或多个组 BizTalk 数据库的磁盘</span><span class="sxs-lookup"><span data-stu-id="fe119-135">Sharing one server or disk for more than one group of BizTalk databases</span></span>  
 <span data-ttu-id="fe119-136">正如前面提到，以外 Messagebox 中，例如 BizTalk 跟踪 (BizTalkDTADb) 数据库和 BAM 数据库的数据库可能会占用服务器的物理磁盘上的高周期。</span><span class="sxs-lookup"><span data-stu-id="fe119-136">As mentioned previously, databases other than MessageBoxes, such as the BizTalk Tracking (BizTalkDTADb) database and BAM databases, might consume high cycles on a server’s physical disk.</span></span> <span data-ttu-id="fe119-137">因此，如果这些数据库碰巧与 MessageBox 数据库中，共享相同的物理磁盘，则它们可能会阻塞该磁盘并使其停止响应，从而导致 BizTalk server 与 MessageBox 数据库的连接并因此发生 dbnetlib 错误。</span><span class="sxs-lookup"><span data-stu-id="fe119-137">So, if those databases happen to share the same physical disk with the MessageBox databases, then they might choke the disk and make it unresponsive, which again might cause BizTalk servers to loose connectivity with the MessageBox databases and thus hit DBNetLib.</span></span>  
  
 <span data-ttu-id="fe119-138">强烈建议您分隔应具有大量占用服务器的物理磁盘从 BizTalk MessageBox(s)，因此它们共享不同的物理磁盘 （或将它们分不同的服务器上） 的任何数据库。</span><span class="sxs-lookup"><span data-stu-id="fe119-138">It is highly recommended that you separate any database expected to have high consumption of the server’s physical disk from the BizTalk MessageBox(s), so they share different physical disks (or separate them on different servers).</span></span> <span data-ttu-id="fe119-139">建议在其自己单独的驱动器/服务器上的 BizTalkDTADb 和 BAM 数据库分开 MessageBox(s)，并还建议将每个 MessageBox 数据库 （在这种情况，有多个） 在其自己的磁盘上。</span><span class="sxs-lookup"><span data-stu-id="fe119-139">It is recommended that you separate the BizTalkDTADb and BAM databases on their own separate drives/servers from the MessageBox(s), and it is also recommended to have each MessageBox database (in the case there is more than one) on it’s own disk.</span></span>  
  
##### <a name="archiving-and-purging"></a><span data-ttu-id="fe119-140">存档和清除</span><span class="sxs-lookup"><span data-stu-id="fe119-140">Archiving and Purging</span></span>  
 <span data-ttu-id="fe119-141">在这种情况有 BizTalkDTADb 和 MessageBox 数据库共享同一服务器上的同一磁盘时您必须存档和清除 BizTalkDTADb 数据库定期，否则为它们会无限增大。</span><span class="sxs-lookup"><span data-stu-id="fe119-141">In the case when you have BizTalkDTADb and MessageBox databases sharing the same disk on the same server, you must archive and purge your BizTalkDTADb databases regularly, otherwise they will grow indefinitely.</span></span>  
  
 <span data-ttu-id="fe119-142">测试表明它是很好的做法，定期存档和清除，但如果在比平时更高的负载下运行然后您可能需要考虑存档和更频繁地清除。</span><span class="sxs-lookup"><span data-stu-id="fe119-142">Testing indicates that it is good practice to archive and purge periodically, but if you run under higher loads than normal then you might want to consider archiving and purging more frequently.</span></span> <span data-ttu-id="fe119-143">如果 BizTalkDTADb 数据库的增长速度不会保留定期，则最后执行这些操作时它们可能需要很长时间，并在运行时占用了大部分可用的数据库服务器资源。</span><span class="sxs-lookup"><span data-stu-id="fe119-143">If the BizTalkDTADb database growth is not maintained regularly, then when these actions are finally performed they may take considerable time and consume most of the available database server resources while they are running.</span></span>