---
title: 测量 DTA 跟踪的 MST 的测试方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 303dc1d8-baac-4b54-92c8-95c0ce640a76
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1386c7113c534c2491bed447fdcc0ba970881bac
ms.sourcegitcommit: ed9590dbcd97c12a1fe5ce2cdf8d826492cccdff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "39640145"
---
# <a name="test-scenarios-for-measuring-mst-of-dta-tracking"></a>测量 DTA 跟踪的 MST 的测试方案
为了说明实践中的工作方式以及介绍用于度量跟踪的最大可承受吞吐量 (MST) 的简单技术，我们现在将针对度量跟踪 MST 提供一个测试方案。 我们不仅将提供涉及的技术，而且您还可以将提供的数据用作起点，评估其他系统的跟踪性能。  
  
> [!IMPORTANT]
>  读者应了解本主题所包含的信息代表了 Microsoft 在文档发布之日对所讨论的问题的当前观点。 由于我们必须对市场条件和技术的更改作出响应，所以 Microsoft 无法确保数据发布后的所有信息的准确性。  
  
## <a name="test-scenario-topology-and-configuration"></a>测试方案拓扑结构和配置  
 下图显示了测试方案的拓扑结构和配置。  它是可调的四个 MessageBox 数据库服务器、 专用的 BizTalkDTADb 数据库服务器与运行的七个服务器总共[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 请注意，图中的 BAM 服务器没有用于此测试方案。  
  
 **BizTalkDTADb 可承受吞吐量**  
  
 ![跟踪性能拓扑](../core/media/trackingperformancetopology.gif "TrackingPerformanceTopology")  
  
 **硬件规格 (BizTalk Server)**  
  
- CPU： 双 3 GHz (缓存： L2: 512 KB/L3: 1 MB)  
  
- 内存： 2 GB 的 RAM  
  
- HDD: 2 X 32 GB/15K  
  
  **硬件规格 (SQL Server)**  
  
- CPU： 四核 2 GHz (L2: 512 KB/L3: 1 MB)  
  
- 内存： 4 GB 的 RAM  
  
- HDD: 2 X 32 GB/15 K + SAN  
  
  下图概述了这一测试方案结构，其中：  
  
- **TP** = 跟踪点，点的某些元素跟踪如事件或消息属性。  
  
- **MB** = 消息正文，跟踪跟踪消息正文的点。  
  
  下面的解决方案结构显示具有三个主要配置组件的跟踪配置：  
  
- **默认 DTA 跟踪**。 所有在图中的事件跟踪点都在默认情况下当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。  
  
- **消息属性**。 与入站管道中的拆装器 (DA) 组件相关联的跟踪点表示跟踪来自入站消息的 10 个属性。 有关如何升级跟踪属性的详细信息，请参阅[升级属性](../core/promoting-properties.md)。  
  
- **消息正文**。 图中的两个消息正文 (MB) 点表示跟踪消息正文的点。 有关如何设置消息正文跟踪的详细信息，请参阅[配置使用 BizTalk Server 管理控制台跟踪](http://msdn.microsoft.com/49b7f9d3-60b5-41bd-ba8b-029253926bef)。  
  
  **测试方案体系结构**  
  
  ![性能方案](../core/media/performancescenarios.gif "PerformanceScenarios")  
  
## <a name="test-techniques"></a>测试技术  
 文件适配器既用于接收，又用于发送。 我们使用了负载生成工具 LoadGen 2007 将消息传送到入站文件共享。 该 LoadGen 工具配置为以特定速率传送文件，以便我们可以在搜索跟踪 MST 级别时变化负载。 有关 LoadGen 工具的详细信息，请参阅[使用 Microsoft BizTalk LoadGen 2007 工具](../core/using-the-microsoft-biztalk-loadgen-2007-tool.md)。  
  
 出于测试目的，我们假定要求数据在 BizTalkDTADb 数据库中保留 24 小时。 即，任何早于 24 小时的内容都将从数据库中清除。 存档和清除 SQL 作业设计为只清除已存档的数据，以便在这一过程中不会丢失任何数据。  
  
 为了按此要求完全测试系统，负载必须至少运行 25 小时，以便包括至少一个存档和清除周期。 我们选择运行整 48 小时，以便在第一个存档后监控系统 24 小时，确保其可承受。 要求第一个 24 小时是为了积累足够旧到存档（每 24 小时）的数据，以便模拟稳定的状态。 在第二个 24 小时期间对系统进行监控，以便确定所有进程（例如 TDDS、存档和清除）能够赶上吞吐量。  
  
 基于我们对跟踪行为的理解，通常只需对以下几个关键性能指标 (KPI) 进行监控以确定可承受能力：  
  
- **物理磁盘空闲时间 BizTalkDTADb 数据库数据文件**。 如果该物理磁盘空闲时间接近 0，则表明 BizTalkDTADb 数据库因充斥了大量跟踪数据、存档行为和/或清除行为而趋于饱和。  
  
- **Trackingdata 表深度**。 如果 trackingdata 表开始单调增长，即无限制地持续增长，则表明基于当前吞吐率，TDDS 将数据插入 BizTalkDTADb 数据库的速度太快了，以致它跟不上。  
  
- **后台处理深度**。 有多种因素可能导致后台处理增长。 可能导致后台处理增长的情形之一是：将跟踪消息正文从 MessageBox 数据库复制到 BizTalkDTADb 数据库的 SQL 作业落后了。 因为需要跟踪的消息在成功复制到 BizTalkDTADb 数据库之前不能从 MessageBox 数据库删除（通过 MessageBox 清除作业），所以，如果该复制作业落后，则会导致后台处理逐渐累积。  
  
  对于大多数系统，只监控上述三个负载性能指标，所获得的信息就足以确定负载是否可承受了。  
  
  **可承受负载的关键绩效指标**  
  
  ![跟踪数据库的性能监视](../core/media/perf-monitor-tracking-db.gif "Perf_Monitor_Tracking_db")  
  
  使用示例方案，在每秒收到 20 个消息的负载下，我们得到了有价值的 48 小时的关键性能指标，如生成的 Perfmon 图所示。 请注意该图上指示可承受能力的以下趋势：  
  
- **BizTalkDTADbdata 深度 （黑色线）**。 使用我们的三个发布的 MessageBox 数据库，可以看到，即使在 24 小时上的第一次存档后，trackingdata 表的深度也依然保持稳定，没有继续增长。  
  
- **后台处理深度 （蓝色线）**。 后台处理深度在整个运行中非常稳定，这指出即使存档和清除操作正在占用资源，但跟踪消息（每个消息的大小为 10 kb）仍复制到 BizTalkDTADb 数据库并且没有落后。  
  
- **BizTalkDTADb 数据库数据文件的物理磁盘空闲时间 （红色线）**。 对于要进行存档和清除操作之前的第一个 24 小时，BizTalkDTADb 数据库将累积越来越多的数据，导致随着 TDDS 不断插入数据，磁盘 I/O 也越来越繁忙。 物理磁盘空闲时间的稳步下降清楚地表明了这一趋势。  
  
   在 24 小时的运行，I/O 空闲时间明显下降观察到，这与存档和清除有工作要做的第一个时间一致。 在首次存档后清除有工作要做每隔一分钟来清除数据保留时间超过 24 小时 （请记住，没有仍在系统上加载），这会导致接近零的空闲时间。  
  
   这里的一个关键点就是在发生首次存档后，也就是说，在系统经过了第一个“活动 BizTalkDTADb 数据库数据保留”时段后，在系统达到或接近 MST 时磁盘空闲时间将非常接近于零。 这是因为，磁盘 I/O 子系统的速度在大多数情况下是 BizTalkDTADb 数据库的瓶颈。  
  
  在许多情况下，最好将关闭了跟踪功能的 MST 作为系统的度量基准。 例如，在我们的例子中，关闭了所有跟踪的 MST 是每秒 290 个消息，是上述具有相关功能和 DTA 数据保留时段的启用了跟踪功能的系统 MST 的许多倍。 这表明，一旦系统启用了跟踪功能，其利用率会显著降低。 也就是说，在我们需要跟踪的内容仅支持 20 个消息/秒的 MST 时，我们不需要具备 290 个消息/秒的系统能力。换言之，假定 BizTalkDTADb 数据库硬件不更改，要实现每秒 20 个消息的吞吐量，所需的 BizTalk 和 MessageBox 数据库服务器可以比方案中所示数目少得多。  
  
## <a name="searching-for-maximum-sustainable-throughput"></a>搜索最大可承受吞吐量  
 现在，我们已看到以 MST 运行的系统的 KPI 的情况，让我们补充讨论如何达到示例方案的 20 个消息/秒的 MST。 它是一个如下所示的简单迭代“二进制搜索”方法：  
  
- **选择一个起点**。 除非你已有测试或性能体验[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，您将需要利用在其他系统上获得的内容上提供的信息。  
  
   例如，我们已经为本主题中的示例方案提供了所有的硬件、配置和解决方案结构。 使用这一结构、我们已启用的跟踪类型（默认值 + 10 个属性 + 10KB 的消息正文）和我们已实现的 MST（20 个消息/秒）以及 24 小时的 DTA 数据保留时段，将它们与您的设置和要求进行比较。  
  
   您应该至少能够评估您的解决方案的 MST 是高于还是低于我们实现的 MST。 我们还提供了不同的技术案例研究供您与您的系统进行比较。 有关示例，请提供的案例研究参阅 BizTalk Server 开发人员中心，在[ http://go.microsoft.com/fwlink/?LinkId=49339 ](http://go.microsoft.com/fwlink/?LinkId=49339)。  
  
- **运行评估的 MST 负载下，系统并监控 KPI**。 通常，从您的预期 MST 的高端开始可缩短找到 MST 所用的时间。 通过从高端开始，将用比发现您低于 MST（即，至少一个完整数据保留时段）更少的时间驱动 KPI 达到饱和（尤其是磁盘 I/O）。  
  
- **优化 MST 评估并重复**。 根据您的测试运行结果，优化您的 MST 评估值并使用新评估值重复执行该测试。  
  
## <a name="see-also"></a>请参阅  
 [测量最大可承受跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [了解 DTA 跟踪性能行为](../core/understanding-dta-tracking-performance-behavior.md)   
 [DTA 跟踪的 Mst 的提示和技巧](../core/tips-and-tricks-for-finding-mst-of-dta-tracking.md)   
 [跟踪数据库的大小调整准则](../core/tracking-database-sizing-guidelines.md)
