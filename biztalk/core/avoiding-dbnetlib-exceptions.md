---
title: "避免 DBNETLIB 异常 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5fbee0cf-d249-4d98-8d16-168ded32f9f1
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: decd258c5f4c965c79d9821c82671c6997ac9e3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="avoiding-dbnetlib-exceptions"></a><span data-ttu-id="3aeb4-102">避免出现 DBNETLIB 异常</span><span class="sxs-lookup"><span data-stu-id="3aeb4-102">Avoiding DBNETLIB Exceptions</span></span>
<span data-ttu-id="3aeb4-103">当 BizTalk Server 运行时无法与 MessageBox 数据库或管理数据库进行通信时，将出现 DBNetLib（数据库网络库）错误。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-103">DBNetLib (Database Network Library) errors occur when the BizTalk Server runtime is unable to communicate with either the MessageBox or Management databases.</span></span> <span data-ttu-id="3aeb4-104">出现此错误时，捕获该异常的 BizTalk Server 运行时实例将关闭，然后每分钟检查一次该数据库是否可用。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-104">When this occurs, the BizTalk Server runtime instance that catches the exception shuts down and then cycles every minute to check to see if the database is available.</span></span>  
  
 <span data-ttu-id="3aeb4-105">导致 DBNetLib 错误的最常见原因是 MessageBox 数据库服务器之一（可能是多个）变得极其繁忙，进一步尝试与之进行通信会造成超时，而超时会导致出现 DBNetLib 异常。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-105">The most common cause of a DBNetLib error is when one of the (possibly many) MessageBox database servers becomes extremely busy and further attempts to communicate with it result in a timeout, which causes a DBNetLib exception.</span></span>  
  
 <span data-ttu-id="3aeb4-106">除了 MessageBox 数据库十分繁忙的情况之外，在生产环境中，如果承载一个或多个 MessageBox 数据库的 BizTalk 数据库服务器受到 I/O（输入/输入出）限制，也会出现 DBNetLib 错误。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-106">In addition to the case where the MessageBox database is simply very busy, the DBNetLib error can occur in a production environment when BizTalk database servers hosting one of more MessageBox databases become I/O (Input/Output) bound.</span></span>  
  
 <span data-ttu-id="3aeb4-107">本主题说明可导致 DBNetLib 错误的情况和避免这些错误的建议。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-107">This topic describes conditions that can lead to DBNetLib errors and recommendations for avoiding these errors.</span></span>  
  
## <a name="cause-and-resolution-for-the-dbnetlib-error"></a><span data-ttu-id="3aeb4-108">DBNetLib 错误的原因和解决方法</span><span class="sxs-lookup"><span data-stu-id="3aeb4-108">Cause and Resolution for the DBNetLib error</span></span>  
  
### <a name="symptoms-of-a-dbnetlib-error"></a><span data-ttu-id="3aeb4-109">DBNetLib 错误的症状</span><span class="sxs-lookup"><span data-stu-id="3aeb4-109">Symptoms of a DBNetLib error</span></span>  
 <span data-ttu-id="3aeb4-110">Microsoft BizTalk Server 主机实例终止，然后自行重新启动，类似以下的错误被写入 BizTalk Server 应用程序日志：</span><span class="sxs-lookup"><span data-stu-id="3aeb4-110">A Microsoft BizTalk Server host instance terminates and then restarts itself, and errors that are similar to the following are written to the BizTalk Server Application log:</span></span>  
  
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
  
### <a name="biztalk-database-servers-hosting-messagebox-databases-becoming-io-bound"></a><span data-ttu-id="3aeb4-111">MessageBox 数据库的宿主 BizTalk 数据库服务器受到 I/O 限制</span><span class="sxs-lookup"><span data-stu-id="3aeb4-111">BizTalk database servers hosting MessageBox databases becoming I/O bound</span></span>  
 <span data-ttu-id="3aeb4-112">BizTalk 服务器直接与 MessageBox 数据库的宿主数据库服务器进行通信和交互。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-112">BizTalk servers communicate and act directly with the database servers hosting the MessageBox databases.</span></span> <span data-ttu-id="3aeb4-113">如果 MessageBox 数据库的任何宿主数据库服务器被过度占用，并受到 I/O（输入/输出）限制，它可能会停止响应。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-113">If any of the database servers hosting the MessageBox databases get too consumed and gets into an I/O (Input/Output) bound situation, then it might become unresponsive.</span></span> <span data-ttu-id="3aeb4-114">BizTalk 服务器之一随后可能与这些数据库服务器中的一个断开连接，这时将出现 DBNetLib 错误。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-114">One of the BizTalk servers might in turn lose connectivity with one of those database servers, and a DBNetLib error will occur.</span></span>  
  
 <span data-ttu-id="3aeb4-115">我们的测试显示当以下情况出现时，被高度占用的数据库服务器将受到 I/O 限制：该数据库的物理磁盘的“%Idle 时间”继续降低并达到 10% 以下。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-115">Our tests show that a highly consumed database server becomes I/O bound when its physical disk’s "%Idle time" continues to drop and reaches below 10%.</span></span> <span data-ttu-id="3aeb4-116">如果“%Idle 时间”继续降到该水平以下，这表示数据库服务器可能停止响应。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-116">If the “%Idle time” continues to drop below that level, then this is an indication that your database server is likely to become unresponsive.</span></span>  
  
#### <a name="cause"></a><span data-ttu-id="3aeb4-117">原因</span><span class="sxs-lookup"><span data-stu-id="3aeb4-117">Cause</span></span>  
 <span data-ttu-id="3aeb4-118">有多种原因可导致 MessageBox 数据库的宿主数据库服务器受到 I/O 限制，下面是其中一些原因：</span><span class="sxs-lookup"><span data-stu-id="3aeb4-118">There are several reasons that can cause the database servers hosting the MessageBox databases to become I/O bound, some of these are the following:</span></span>  
  
-   <span data-ttu-id="3aeb4-119">如果承载 MessageBox 数据库的数据库计算机绑定由低硬件规范，如： 低内存、 数量和速度的处理器等。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-119">If the database machine hosting the MessageBox database is bound by low hardware specifications such as: low memory, number and speed of processors etc.</span></span>  
  
-   <span data-ttu-id="3aeb4-120">MessageBox 数据库的宿主数据库计算机的物理磁盘正由其他被高度占用的数据库共享。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-120">If the physical disk on the database machine hosting a MessageBox database is being shared by other highly consumed databases.</span></span> <span data-ttu-id="3aeb4-121">在多个数据库（包括 MessageBox）同时被高度占用的情况下，物理磁盘可能会受 I/O 限制。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-121">In cases when several databases (including the MessageBox) are being highly consumed at the same time, the physical disk can get into an I/O bound situation.</span></span>  
  
     <span data-ttu-id="3aeb4-122">此情况的示例如下：</span><span class="sxs-lookup"><span data-stu-id="3aeb4-122">An example of such a situation is the following:</span></span>  
  
     <span data-ttu-id="3aeb4-123">我们的测试显示 BizTalkDTADb 和/或 BAM 数据库的宿主数据库服务器有时会占用高百分比的物理磁盘“%Disk 读写数”。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-123">Our tests show that the database server hosting the BizTalkDTADb and/or BAM databases sometimes consume high percentages of a physical disk’s %Disk Read and Write Times.</span></span> <span data-ttu-id="3aeb4-124">如果 MessageBox 数据库的宿主数据库服务器磁盘由其他被高度占用的数据库（例如 BizTalkDTADb 或 BAM）共享，并且这两个数据库同时被高度占用，它们可能导致该数据库服务器物理磁盘受到 I/O 限制，然后停止响应。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-124">When the database server disk that hosts a MessageBox database is being shared by another highly consumed database such as BizTalkDTADb or BAM, and if both databases are highly consumed simultaneously, they might cause the database server physical disk to become I/O bound and then unresponsive.</span></span>  
  
-   <span data-ttu-id="3aeb4-125">当 BizTalkDTADb 与一个或多个 MessageBox 数据库共享数据库服务器上的同一物理磁盘时，如果不经常运行存档和清除，磁盘可能受到 I/O 限制。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-125">If BizTalkDTADb and one or more of the MessageBox databases are sharing the same physical disk on the database server, if archiving and purging is not being run frequently, the disk might become I/O bound.</span></span>  
  
#### <a name="resolution"></a><span data-ttu-id="3aeb4-126">解决方法</span><span class="sxs-lookup"><span data-stu-id="3aeb4-126">Resolution</span></span>  
 <span data-ttu-id="3aeb4-127">确保宿主 BizTalk MessageBox 的数据库服务器不会处于以下状况：被高度占用并可能停止响应。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-127">Ensure the database server(s) hosting the BizTalk MessageBox(s) do not get into a situation where they become highly consumed and possibly unresponsive.</span></span>  
  
 <span data-ttu-id="3aeb4-128">下面列出服务器磁盘被高度占用的主要原因，并给出如何减轻此问题的建议。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-128">Some of the primary causes of a server disk becoming highly consumed are listed below along with recommendations on how to mitigate this problem.</span></span>  
  
##### <a name="low-hardware-specs"></a><span data-ttu-id="3aeb4-129">硬件规格较低</span><span class="sxs-lookup"><span data-stu-id="3aeb4-129">Low Hardware Specs</span></span>  
 <span data-ttu-id="3aeb4-130">我们的测试显示当服务器的硬件规格不能维持它尝试处理的负载量时，该服务器会更大程度地被占用。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-130">Our tests show that the server starts getting more consumed when its hardware specifications cannot keep up with the amount of load it’s trying to process.</span></span> <span data-ttu-id="3aeb4-131">在硬件规格较低的情况下，数据库中发生的活动量将使系统迅速瘫痪。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-131">With lower hardware specs, the system gets overwhelmed quickly by the amount of activities happening on the databases.</span></span> <span data-ttu-id="3aeb4-132">这可能导致服务器的“%Disk 读写数”继续增加，不能稳定，同时磁盘的“%Idle 时间”继续降低并达到 10% 以下，这可能导致该数据库服务器停止响应。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-132">This might cause the server’s %Disk Read and Write Times to continue increasing without stabilizing, also the disk’s %Idle time to continue to decrease and become lower than 10%, and this might cause your database server to become unresponsive.</span></span>  
  
 <span data-ttu-id="3aeb4-133">如果你发现获得期间不响应数据库服务器对高负载，具体的活动和对你的 BizTalk 部署的负载量取决于，应考虑升级你的数据库服务器中的以下部分： Cpu、 内存的数并连接到 SAN。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-133">Depending on the amount of activities and load you have on your BizTalk deployment, if you find that you are getting unresponsive database servers during to high loads, you should consider upgrading the following parts in your database servers: number of CPUs, memory, and connecting to a SAN.</span></span> <span data-ttu-id="3aeb4-134">当然，你应该进行适当的诊断，找出硬件中需要升级的瓶颈部分（内存、CPU 数量等）。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-134">Of course, you should do the proper diagnosis to figure out which part (memory, number of CPUs etc.) is the bottleneck that needs to be upgraded in your hardware.</span></span>  
  
##### <a name="sharing-one-server-or-disk-for-more-than-one-group-of-biztalk-databases"></a><span data-ttu-id="3aeb4-135">多组 BizTalk 数据库共享一个服务器或磁盘</span><span class="sxs-lookup"><span data-stu-id="3aeb4-135">Sharing one server or disk for more than one group of BizTalk databases</span></span>  
 <span data-ttu-id="3aeb4-136">正如前面提到的，MessageBox 以外的数据库，例如 BizTalk 跟踪 (BizTalkDTADb) 数据库和 BAM 数据库，可能会大量占用服务器物理磁盘的周期。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-136">As mentioned previously, databases other than MessageBoxes, such as the BizTalk Tracking (BizTalkDTADb) database and BAM databases, might consume high cycles on a server’s physical disk.</span></span> <span data-ttu-id="3aeb4-137">因此，如果这些数据库碰巧与 MessageBox 数据库共享同一物理磁盘，它们可能会阻塞该磁盘并使其停止响应，从而导致 BizTalk 服务器与 MessageBox 数据库断开连接，并因此发生 DBNetLib 错误。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-137">So, if those databases happen to share the same physical disk with the MessageBox databases, then they might choke the disk and make it unresponsive, which again might cause BizTalk servers to loose connectivity with the MessageBox databases and thus hit DBNetLib.</span></span>  
  
 <span data-ttu-id="3aeb4-138">强烈建议你将任何需要大量占用服务器物理磁盘的数据库与 BizTalk MessageBox 分开，以便让它们使用不同的物理磁盘（或将它们分别放在不同的服务器上）。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-138">It is highly recommended that you separate any database expected to have high consumption of the server’s physical disk from the BizTalk MessageBox(s), so they share different physical disks (or separate them on different servers).</span></span> <span data-ttu-id="3aeb4-139">建议将 BizTalkDTADb 和 BAM 分别放到其各自的驱动器/服务器上，与 MessageBox 分开，同时还建议将每个 MessageBox 数据库（有多个的情况下）放在其自己的磁盘上。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-139">It is recommended that you separate the BizTalkDTADb and BAM databases on their own separate drives/servers from the MessageBox(s), and it is also recommended to have each MessageBox database (in the case there is more than one) on it’s own disk.</span></span>  
  
##### <a name="archiving-and-purging"></a><span data-ttu-id="3aeb4-140">存档和清除</span><span class="sxs-lookup"><span data-stu-id="3aeb4-140">Archiving and Purging</span></span>  
 <span data-ttu-id="3aeb4-141">当 BizTalkDTADb 和 MessageBox 数据库共享同一服务器上的同一磁盘时，必须定期存档和清除 BizTalkDTADb 数据库，否则它们会无限增大。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-141">In the case when you have BizTalkDTADb and MessageBox databases sharing the same disk on the same server, you must archive and purge your BizTalkDTADb databases regularly, otherwise they will grow indefinitely.</span></span>  
  
 <span data-ttu-id="3aeb4-142">测试表明定期存档和清除是一个很好的做法，但是如果在超过正常水平的高负载下运行，你可能需要考虑更频繁地存档和清除。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-142">Testing indicates that it is good practice to archive and purge periodically, but if you run under higher loads than normal then you might want to consider archiving and purging more frequently.</span></span> <span data-ttu-id="3aeb4-143">如果没有定期针对 BizTalkDTADb 数据库的增长进行维护，则最后执行这些操作时，它们在运行期间可能会耗费相当长时间并占用大多数可用的数据库服务器资源。</span><span class="sxs-lookup"><span data-stu-id="3aeb4-143">If the BizTalkDTADb database growth is not maintained regularly, then when these actions are finally performed they may take considerable time and consume most of the available database server resources while they are running.</span></span>