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
ms.openlocfilehash: cbf1c372f19232848396b610d248e98f8248a7cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299444"
---
# <a name="test-scenarios-for-measuring-mst-of-dta-tracking"></a>测量 DTA 跟踪的 MST 的测试方案
若要向所有这些都在实践中的工作原理并介绍度量最大可承受吞吐量 (MST) 跟踪的一个简单方法，我们现在将显示为其跟踪 mst 的测试方案。 我们将提供涉及的技术，不仅可以使用提供的数据用作起点以评估其他系统的跟踪性能。  
  
> [!IMPORTANT]
>  读者应了解本主题中包含的信息代表 Microsoft 对截至发布日期所讨论问题的当前观点。 因为我们必须应对不断变化的市场条件和技术，Microsoft 无法保证发布日期之后所提供的任何信息的准确性。  
  
## <a name="test-scenario-topology-and-configuration"></a>测试方案拓扑结构和配置  
 下图显示了拓扑和测试方案的配置。  它是可调的四个 MessageBox 数据库服务器、 专用的 BizTalkDTADb 数据库服务器与运行的七个服务器总共[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 请注意图中的 BAM 服务器不可用于此测试方案。  
  
 **BizTalkDTADb 可承受吞吐量**  
  
 ![跟踪性能拓扑](../core/media/trackingperformancetopology.gif "TrackingPerformanceTopology")  
  
 **硬件规格 (BizTalk Server)**  
  
- CPU:双 3 GHz (缓存：L2:512 KB/L3:1 MB)  
  
- 内存：2 GB 的 RAM  
  
- HDD:2 X 32 GB/15 K  
  
  **硬件规格 (SQL Server)**  
  
- CPU:四核 2 GHz (L2:512 KB/L3:1 MB)  
  
- 内存：4 GB 的 RAM  
  
- HDD:2 X 32 GB/15 K + SAN  
  
  下图概述的测试方案体系结构，其中  
  
- **TP** = 跟踪点，点的某些元素跟踪如事件或消息属性。  
  
- **MB** = 消息正文，跟踪跟踪消息正文的点。  
  
  下面的解决方案体系结构显示了具有三个主要配置组件的跟踪配置：  
  
- **默认 DTA 跟踪**。 所有在图中的事件跟踪点都在默认情况下当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。  
  
- **消息属性**。 入站管道中的拆装器 (DA) 组件与关联的跟踪点表示跟踪的 10 个属性从入站消息。 有关如何升级跟踪属性的详细信息，请参阅[升级属性](../core/promoting-properties.md)。  
  
- **消息正文**。 图中的两个消息正文 (MB) 点表示跟踪消息正文的点。 有关如何设置消息正文跟踪的详细信息，请参阅[配置使用 BizTalk Server 管理控制台跟踪](http://msdn.microsoft.com/49b7f9d3-60b5-41bd-ba8b-029253926bef)。  
  
  **测试方案体系结构**  
  
  ![性能方案](../core/media/performancescenarios.gif "PerformanceScenarios")  
  
## <a name="test-techniques"></a>测试技术  
 文件适配器用于接收和发送。 我们使用了负载生成工具 LoadGen 2007 将消息传递到入站的文件共享。 LoadGen 工具配置为以将文件以特定速率传送，以便我们可以搜索跟踪 MST 级别时变化负载。 有关 LoadGen 工具的详细信息，请参阅[使用 Microsoft BizTalk LoadGen 2007 工具](../core/using-the-microsoft-biztalk-loadgen-2007-tool.md)。  
  
 对于我们的测试，我们假定 BizTalkDTADb 数据库中的 24 小时保留期的要求。 也就是说，任何早于 24 小时已从数据库中清除。 存档和清除 SQL 作业设计，以便只有已存档的数据清除，以便在过程中会丢失任何数据。  
  
 若要完全测试系统满足此要求，有必要至少 25 小时运行负载，以便在至少一个存档和清除周期已包括在内。 我们选择运行整 48 小时内的 24 小时后在第一个存档以确保它是可持续监视的系统。 第一个 24 小时是为了积累足够旧到存档 （每 24 小时） 来模拟稳定状态的数据所需的。 对系统进行监控以确定所有进程 (例如，TDDS、 存档和清除) 都能够赶上吞吐量第二个 24 小时内。  
  
 绘制从我们对跟踪行为的了解，有几个关键绩效指标 (KPI)，通常需要进行监视以确定可承受能力：  
  
- **物理磁盘空闲时间 BizTalkDTADb 数据库数据文件**。 如果物理磁盘空闲时间接近 0，这是一个好迹象充斥了大量跟踪数据、 存档行为和/或清除活动 BizTalkDTADb 数据库处于满负荷状态。  
  
- **Trackingdata 表深度**。 如果 trackingdata 表开始单调增长，也就是说，将继续增长不受限制，则是清除登录，在当前吞吐率，TDDS 不能将数据插入 BizTalkDTADb 数据库足够快的速度跟不上。  
  
- **后台处理深度**。 有多种因素可能导致后台处理增长。 一个可能会导致 spool 增长的情况是如果将复制的 SQL 作业跟踪消息正文从 MessageBox 数据库到 BizTalkDTADb 数据库落后。 因为不能删除需要跟踪的消息从 MessageBox 数据库 （通过 MessageBox 清除作业） 直到它们已成功复制到 BizTalkDTADb 数据库中，如果复制作业落后，这会导致后台处理逐渐累积。  
  
  对于大多数系统时，监视负载仅这三个性能指标提供足够的信息来确定是否可承受负载。  
  
  **可承受负载的关键绩效指标**  
  
  ![跟踪数据库的性能监视](../core/media/perf-monitor-tracking-db.gif "Perf_Monitor_Tracking_db")  
  
  我们使用示例方案中，每秒接收的 20 条消息的负载，获取 48 小时的关键绩效指标中生成的 Perfmon 图所示。 请注意，从关系图，指示可承受能力的以下趋势：  
  
- **BizTalkDTADbdata 深度 （黑色线）**。 使用三个发布 MessageBox 数据库，我们可以看到，即使在 24 小时的第一个存档，trackingdata 表深度稳定并不继续向上的趋势。  
  
- **后台处理深度 （蓝色线）**。 后台处理深度是在整个运行指示的即使使用存档和清除操作正在占用资源，跟踪的消息，是每个 10 千字节的大小，复制到 BizTalkDTADb 数据库并且没有落后非常稳定的。  
  
- **BizTalkDTADb 数据库数据文件的物理磁盘空闲时间 （红色线）**。 第一个 24 小时内前面存档和清除包含任何可执行的操作，BizTalkDTADb 数据库将累积越来越多的数据，这会导致越来越多的磁盘 I/O，因为由 TDDS 插入数据。 这是清楚地表明了稳定下降的物理磁盘空闲时间。  
  
   在 24 小时的运行，I/O 空闲时间明显下降观察到，这与存档和清除有工作要做的第一个时间一致。 在首次存档后清除有工作要做每隔一分钟来清除数据保留时间超过 24 小时 （请记住，没有仍在系统上加载），这会导致接近零的空闲时间。  
  
   此处的关键一点是，发生在首次存档后，即，系统已通过第一个"活动 BizTalkDTADb 数据库数据保留期"窗口，磁盘空闲时间将非常接近于零系统达到或接近 MST 时。 这是因为 BizTalkDTADb 数据库的瓶颈几乎始终是磁盘 I/O 子系统的速度。  
  
  在许多情况下，它可以是度量 MST 跟踪与关闭作为系统的基线。 例如，在本例中，已关闭的所有跟踪的 MST 是 290 个消息 / 秒，这是与跟踪系统的 MST 已使用的功能和 DTA 数据保留时段，如以上所述的很多时候。 这告诉我们，启用了跟踪系统显著不足的。 也就是说，我们无需构建的系统，能够每秒 290 消息时跟踪的内容，我们需要跟踪 20 消息/秒的 MST 所述另一种方法，假定的 BizTalkDTADb 数据库硬件不会更改，将仅支持许多较少 BizTalk 和MessageBox 数据库服务器所需实现的吞吐量为每秒比我们在我们的方案有 20 条消息。  
  
## <a name="searching-for-maximum-sustainable-throughput"></a>搜索最大可承受吞吐量  
 现在，我们已经看到了 KPI 外观在 MST 运行的系统是什么样，让我们备份，并讨论如何达到我们 20 消息/秒的 MST 的示例方案。 它是一个简单迭代的"二进制搜索"方法，如下所示：  
  
- **选择一个起点**。 除非你已有测试或性能体验[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，您将需要利用在其他系统上获得的内容上提供的信息。  
  
   例如，我们提供了所有硬件、 配置和解决方案体系结构的本主题中的示例方案。 使用，和我们已启用 （默认值 + 10 个属性 + 10KB 消息正文） 的跟踪和我们已实现 （20 条消息/秒） 使用 24 小时 DTA 数据保留时段 MST 的类型，比较的安装程序和要求。  
  
   至少应能估计您的解决方案的 MST 将高于还是低于我们实现。 各种技术案例研究可能还会向其提供可以将您的系统进行比较。 有关示例，请提供的案例研究参阅 BizTalk Server 开发人员中心，在[ http://go.microsoft.com/fwlink/?LinkId=49339 ](http://go.microsoft.com/fwlink/?LinkId=49339)。  
  
- **运行评估的 MST 负载下，系统并监控 KPI**。 通常情况下，开始研究您的预期 MST 侧切出可缩短找到 MST 所需的时间。 通过从高端开始，您将驱动 KPI 达到饱和 （尤其是磁盘 I/O） 更少的时间比所需发现您低于 MST (即，至少一个完整的数据保持期窗口)。  
  
- **优化 MST 评估并重复**。 查看您的测试运行的结果时，优化您的 MST 评估值并重复执行测试的新的估算值。  
  
## <a name="see-also"></a>请参阅  
 [测量最大可承受跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [了解 DTA 跟踪性能行为](../core/understanding-dta-tracking-performance-behavior.md)   
 [DTA 跟踪的 Mst 的提示和技巧](../core/tips-and-tricks-for-finding-mst-of-dta-tracking.md)   
 [跟踪数据库的大小调整准则](../core/tracking-database-sizing-guidelines.md)
