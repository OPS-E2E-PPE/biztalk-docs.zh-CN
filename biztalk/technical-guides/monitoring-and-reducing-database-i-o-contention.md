---
title: "监视和减少数据库 I/O 争用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd6d3343-3fa3-469a-9772-e94f22fdf558
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 446a4b512b4f38869637cb3968305fad1e869dae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-and-reducing-database-io-contention"></a><span data-ttu-id="91459-102">监视和减少数据库 I/O 争用</span><span class="sxs-lookup"><span data-stu-id="91459-102">Monitoring and Reducing Database I/O Contention</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="91459-103">性能通常预测时[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]性能方面，这反过来通常预测时磁盘 I/O 性能。</span><span class="sxs-lookup"><span data-stu-id="91459-103"> performance is often predicated upon [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] performance, which in turn is often predicated upon disk I/O performance.</span></span> <span data-ttu-id="91459-104">因此，你应监视和性能调整运行的计算机上的磁盘 I/O[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]该 house[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="91459-104">Therefore, you should monitor and performance-tune disk I/O on the computers running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] that house the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
## <a name="monitoring-disk-io"></a><span data-ttu-id="91459-105">监视磁盘 I/O</span><span class="sxs-lookup"><span data-stu-id="91459-105">Monitoring Disk I/O</span></span>  
 <span data-ttu-id="91459-106">需要进行大量数据库的性质，因此[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 磁盘 I/O 可以轻松地成为上 MessageBox 瓶颈和 BizTalk 跟踪数据库; 这是 true 即使磁盘 I/O 以前尚未中的数据库文件瓶颈你[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="91459-106">Because of the database-intensive nature of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], disk I/O can easily become a bottleneck on the MessageBox and BizTalk Tracking databases; this is true even if disk I/O has not previously been a bottleneck for the database files in your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] environment.</span></span> <span data-ttu-id="91459-107">因此，我们建议你主动测量存放的数据和事务日志文件的磁盘的磁盘 I/O 性能。</span><span class="sxs-lookup"><span data-stu-id="91459-107">Thus, we recommend that you proactively measure disk I/O performance for the disks that house the data and transaction log files.</span></span> <span data-ttu-id="91459-108">有关监视使用系统监视器的磁盘 I/O 性能的详细信息，请参阅[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]文章["预部署 I/O 最佳实践"](http://go.microsoft.com/fwlink/?LinkId=104829) (http://go.microsoft.com/fwlink/?LinkId=104829)。</span><span class="sxs-lookup"><span data-stu-id="91459-108">For more information about monitoring disk I/O performance using System Monitor, see the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] article ["Predeployment I/O Best Practices"](http://go.microsoft.com/fwlink/?LinkId=104829) (http://go.microsoft.com/fwlink/?LinkId=104829).</span></span> <span data-ttu-id="91459-109">如果使用 SAN，你可能还需要从 SAN 硬件制造商联系，以测量磁盘输入/输出性能的特定工具。</span><span class="sxs-lookup"><span data-stu-id="91459-109">If you are using a SAN, you may also need specific tools from the SAN hardware manufacturer to measure disk I/O performance.</span></span>  
  
## <a name="separating-the-messagebox-and-biztalk-tracking-dta-databases-and-log-files"></a><span data-ttu-id="91459-110">分隔的 MessageBox 和 BizTalk 跟踪 (DTA) 数据库和日志文件</span><span class="sxs-lookup"><span data-stu-id="91459-110">Separating the MessageBox and BizTalk Tracking (DTA) Databases and Log Files</span></span>  
 <span data-ttu-id="91459-111">由于 MessageBox 和 BizTalk 跟踪数据库中最活跃的我们建议你将数据文件和事务日志文件放置于其中每种上专用的驱动器，以减少磁盘 I/O 争用问题的可能性。</span><span class="sxs-lookup"><span data-stu-id="91459-111">Since the MessageBox and BizTalk Tracking databases are the most active, we recommend that you place the data files and transaction log files for each of these on dedicated drives to reduce the likelihood of problems with disk I/O contention.</span></span> <span data-ttu-id="91459-112">例如，将需要四个驱动器的 MessageBox 和 BizTalk 跟踪数据库文件;为每个以下的一个驱动器：</span><span class="sxs-lookup"><span data-stu-id="91459-112">For example, you would need four drives for the MessageBox and BizTalk Tracking database files; one drive for each of the following:</span></span>  
  
-   <span data-ttu-id="91459-113">MessageBox 数据文件</span><span class="sxs-lookup"><span data-stu-id="91459-113">MessageBox data files</span></span>  
  
-   <span data-ttu-id="91459-114">MessageBox 事务日志文件</span><span class="sxs-lookup"><span data-stu-id="91459-114">MessageBox transaction log files</span></span>  
  
-   <span data-ttu-id="91459-115">BizTalk 跟踪数据文件</span><span class="sxs-lookup"><span data-stu-id="91459-115">BizTalk Tracking data files</span></span>  
  
-   <span data-ttu-id="91459-116">BizTalk 跟踪事务日志文件</span><span class="sxs-lookup"><span data-stu-id="91459-116">BizTalk Tracking transaction log files</span></span>  
  
 <span data-ttu-id="91459-117">分隔 MessageBox 和 BizTalk 跟踪数据库和分离数据库文件和事务日志文件在不同的物理磁盘上被视为减少磁盘 I/O 争用的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="91459-117">Separating the MessageBox and BizTalk Tracking databases and separating the database files and transaction log files on different physical disks are considered best practices for reducing disk I/O contention.</span></span> <span data-ttu-id="91459-118">请尝试以尽可能跨多个物理磁盘轴磁盘 I/O。</span><span class="sxs-lookup"><span data-stu-id="91459-118">Try to spread the disk I/O across as many physical spindles as possible.</span></span> <span data-ttu-id="91459-119">有关如何避免磁盘争用情况的详细信息，请参阅[如何避免磁盘争用](http://go.microsoft.com/fwlink/?LinkId=158809)(http://go.microsoft.com/fwlink/?LinkId=158809) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能优化指南。</span><span class="sxs-lookup"><span data-stu-id="91459-119">For more information about avoiding disk contention, see [How to Avoid Disk Contention](http://go.microsoft.com/fwlink/?LinkId=158809) (http://go.microsoft.com/fwlink/?LinkId=158809) in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Performance Optimization Guide.</span></span>  
  
 <span data-ttu-id="91459-120">你应该在配置后手动将文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="91459-120">You should separate the files manually after configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="91459-121">有关详细信息，请参阅[BizTalk Server 数据库优化白皮书](http://go.microsoft.com/fwlink/?LinkId=101578)(http://go.microsoft.com/fwlink/?LinkId=101578)。</span><span class="sxs-lookup"><span data-stu-id="91459-121">For more information, see the [BizTalk Server Database Optimization white paper](http://go.microsoft.com/fwlink/?LinkId=101578) (http://go.microsoft.com/fwlink/?LinkId=101578).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91459-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91459-122">See Also</span></span>  
 [<span data-ttu-id="91459-123">使用日志 (PAL) 工具的性能分析</span><span class="sxs-lookup"><span data-stu-id="91459-123">Using the Performance Analysis of Logs (PAL) Tool</span></span>](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)