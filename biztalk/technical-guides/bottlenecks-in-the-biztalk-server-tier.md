---
title: BizTalk Server 层中的瓶颈 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ad36897-4e4a-43b9-9cb7-0bf22bd954fb
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd2eddf6cc88737375998237db97ca699a676170
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976771"
---
# <a name="bottlenecks-in-the-biztalk-server-tier"></a>BizTalk Server 层中的瓶颈
BizTalk 层可分为以下功能区域：  
  
-   接收  
  
-   处理  
  
-   传输  
  
-   跟踪  
  
-   其他  
  
 这些区域，如果系统资源 （CPU、 内存和磁盘） 似乎饱和，通过向上缩放平台升级服务器，或缩小基于你的应用程序的特征。 如果系统资源不饱和，请执行本部分中介绍的这些步骤。  
  
## <a name="bottlenecks-in-the-receive-location"></a>接收位置的瓶颈  
 如果消息建立在接收位置 （例如，文件接收文件夹占用多），这表明系统不能以足够快的速度消减数据以跟不上传入的负载。 这是因为内部限制。 也就是说，BizTalk Server 接收的速率减少到如果订阅服务器无法处理数据快速数据库表中的足够导致积压工作构建。 如果瓶颈由硬件限制，请尝试按比例增加。 有关向上扩展的详细信息，请参阅 BizTalk Server 2010 文档中的以下主题：  
  
-   [BizTalk Server 层向上扩展](http://go.microsoft.com/fwlink/?LinkId=158073)(http://go.microsoft.com/fwlink/?LinkId=158073)。  
  
-   [按比例增加 SQL Server 层](http://go.microsoft.com/fwlink/?LinkId=158077)(http://go.microsoft.com/fwlink/?LinkId=158077)。  
  
 还有可能要横向扩展通过将主机实例 （服务器） 添加到主机映射到接收处理程序。 有关向外扩展的详细信息，请参阅 BizTalk Server 2010 文档中的以下主题：  
  
-   [BizTalk Server 层向外缩放](http://go.microsoft.com/fwlink/?LinkId=158076)(http://go.microsoft.com/fwlink/?LinkId=158076)。  
  
-   [SQL Server 层向外缩放](http://go.microsoft.com/fwlink/?LinkId=158075)(http://go.microsoft.com/fwlink/?LinkId=158075)。  
  
 使用性能监视器来监视系统上的资源使用。 确认外部接收位置不是导致瓶颈的原因至关重要。 例如，确认是否由于高的磁盘 I/O 饱和远程文件共享、 承载远程传出队列的服务器未达到饱和，或客户端用来生成 HTTP 负载不会耗尽在线程上。  
  
## <a name="processing-bottlenecks"></a>处理瓶颈  
 如果主机队列 – Length 性能计数器攀升到 5，则指示不足够快的速度完成业务流程。 有关详细信息，请参阅本主题中的 Perfmon 计数器表。 这可能是由于内存争用或 CPU 饱和所致。  
  
 如果业务流程服务器是瓶颈，请使用 Perfmon 来标识来源。  
  
 如果服务器受到 CPU 的约束，请考虑以下情况：  
  
-   如果复杂工作流，请考虑将拆分到多个较小的业务流程业务流程  
  
    > [!NOTE]  
    >  将一个业务流程拆分成多个工作流可能会导致额外的延迟并使复杂性增加。 多个工作流也会导致增加在发布到和从 BizTalkMsgBoxDb，使用的消息数对数据库带来额外的压力。  
  
-   如果你使用复杂的地图，请考虑是否可以将它们移到接收/发送端口。 请务必验证哪些端口可以额外的带宽。  
  
-   请考虑按比例增加硬件或通过配置额外的处理服务器向外扩展。  
  
## <a name="transmitting-bottlenecks"></a>传输瓶颈  
 如果服务器承载发送适配器饱和对资源 （例如，磁盘、 内存或 CPU），请考虑向上扩展的服务器或向外缩放到其他主机服务器发送。 如果目标（位于 BizTalk 外部）接收数据的速度不够快，发送层则可能成为瓶颈。 这将会导致消息在 MessageBox 数据库（应用程序 SendHostQ）中累积。  
  
 如果所有终结点的拓扑的范围内，找出在目标位置的原因。 例如，确定 HTTP 位置是否以最佳方式配置为接收负载。 如果没有，请考虑向外扩展。此外确定是否由于过多输出消息传递方式 BizTalk 增长目标。 如果是，你可能需要用于存档和清除目标消息的维护计划。 大量的目标文件夹中的文件会严重影响 BizTalk 服务能够将数据提交到磁盘驱动器。  
  
## <a name="tracking-bottlenecks"></a>跟踪瓶颈  
 跟踪主机实例负责将从 MessageBox 数据库 （TrackingData 表） 的业务活动监视 (BAM) 和运行状况和活动跟踪 (HAT) 数据移到 BizTalk 跟踪和/或 BAM 主导入数据库表。 如果配置了多个 MessageBox 数据库，跟踪托管实例使用每个 MessageBox 数据库的四个线程。  
  
 很有可能跟踪主机实例是 CPU 绑定。 如果是，请考虑向上扩展服务器，或通过配置一台服务器与主机跟踪启用横向扩展。 多个主机实例将自动加载平衡多个消息框配置的数据库。 有关缩放的详细信息，请参阅主题[缩放你的解决方案](http://go.microsoft.com/fwlink/?LinkId=158078)(http://go.microsoft.com/fwlink/?LinkId=158078)。  
  
 如果 MessageBox 数据库中的 TrackingData 表增长大，它通常是因为经过配置之后，导致的 BizTalk 跟踪和/或 BAM 主增长 BizTalk 跟踪和/或 BAM 主导入数据库上的数据维护作业未运行导入数据库。 这些数据库增长得太大后它可以在跟踪主机能够将数据插入 TrackingData 表上产生负面影响。 这将导致要备份的 MessageBox 数据库表中的跟踪的数据。 TrackingData 表的增长会导致限制，以启动。  
  
 你应仅启用最小跟踪所需的应用程序，因为这将减少记录的数据量，并降低跟踪瓶颈的风险。 有关禁用跟踪设置，如业务流程和发送/接收端口的各项的信息，请参阅[如何禁用跟踪](http://go.microsoft.com/fwlink/?LinkId=160064)(http://go.microsoft.com/fwlink/?LinkId=160064)。  
  
## <a name="other"></a>其他  
 配置部署拓扑结构，以使不同的功能运行在专用的独立主机实例中。 这种方式每个主机实例获取自己的 （例如上一个 32 位系统、 2 GB 虚拟内存地址空间、 句柄、 线程）, 的资源集。 该服务器是否具有足够的 CPU 预留空间和内存来承载多个主机实例，可以将它们配置为在同一台物理计算机上运行。 如果没有，请考虑通过将功能移动到专用的服务器向外扩展。 在多个服务器上运行相同的功能也可用于提供高可用性的配置。  
  
## <a name="biztalk-system-performance-counters"></a>BizTalk 系统性能计数器  
  
|对象|实例|计数器|监视目的|  
|------------|--------------|-------------|------------------------|  
|处理器|_Total|% Processor Time|资源争用|  
|处理|BTSNTSvc|Virtual Bytes|内存泄漏/膨胀|  
|处理|BTSNTSvc|Private Bytes|内存泄漏/膨胀|  
|处理|BTSNTSvc|Handle Count|资源争用|  
|处理|BTSNTSvc|线程计数|资源争用|  
|物理磁盘|_ 实例|% Idle Time|资源争用|  
|物理磁盘|_ 实例|Average Disk Queue Length|资源争用|  
  
### <a name="cpu-contention"></a>CPU 争用  
 如果处理器已饱和; 你可以通过将接收从发送成员和业务流程分离片段应用程序。 若要执行此操作，创建单独的主机、 映射到特定功能 （接收/发送/业务流程/跟踪） 主机和将专用的服务器添加到这些单独的主机。 业务流程功能通常是大量占用 CPU。 如果你配置系统，以便在单独的专用服务器上执行业务流程，这可以帮助提高总体系统的吞吐量。  
  
 如果部署多个业务流程，可以将它们登记到不同的专用的 orchestration 主机。 将不同的物理服务器映射到专用的业务流程主机可确保不同业务流程隔离，并不会在同一物理地址空间或在同一服务器上的共享资源。  
  
 停止未使用的主机实例。 未使用的主机实例可以通过定期检查要处理的邮件 MessageBox 争用 CPU 和内存资源。 此外，未使用的停止接收位置、 发送端口和业务流程。  
  
### <a name="spool-table-growth"></a>假脱机表增长  
 下游瓶颈和/或资源争用可能导致假脱机启动过度增长，并降低总体性能。 有关详细信息，请参阅"假脱机表增长"[如何标识 MessageBox Database1 的瓶颈](../technical-guides/how-to-identify-bottlenecks-in-the-messagebox-database1.md)。  
  
### <a name="memory-starvation"></a>内存资源不足  
 高吞吐量情况可能会增加对系统内存的要求。 由于受限制的 32 位进程可以使用的内存量，建议分隔到单独的主机实例的接收/进程/发送功能，以便每个主机接收其自己的 2 GB 地址空间。 此外，如果在同一台物理服务器上运行多个主机实例，你可以升级到 4/8 GB 内存，以避免从实际内存交换到磁盘的数据。 长时间运行的业务流程可以存放到分配的内存更长。 这可能导致内存膨胀和限制，以启动。 大型消息也会导致高内存消耗。  
  
 你可以轻松地通过降低处理大消息时发生内存膨胀问题**内部消息队列大小**和**每个 CPU 进程内消息**特定主机的值。  
  
> [!NOTE]  
>  如果延迟是个问题，将更改为**内部消息队列大小**和**每个 CPU 进程内消息**根据这可能会增加系统的端到端延迟进行多加小心。  
  
### <a name="disk-contention"></a>磁盘争用  
 如果磁盘发生饱和问题 （例如，大量的文件/MSMQ 传输），请考虑升级到多个轴和条带化 RAID 10 具有的磁盘。 此外，无论是使用文件传输，务必确保接收和发送文件夹执行不增长到超过 50000 文件。  
  
 接收文件夹会变得大如果 BizTalk 服务器还会传入数据限制到系统。 请务必将数据从发送文件夹移动，以便此文件夹中的增长不会影响 BizTalk Server 用于编写额外的数据的功能。 对于非事务性 MSMQ 队列，它被建议远程创建接收队列，以便在 BizTalk Server 上有所减少的磁盘争用。  
  
 远程非事务性队列配置还提供了高可用性驻留此队列的远程服务器可以群集化。  
  
### <a name="other-system-resource-contention"></a>其他系统资源争用  
 根据传输的类型，可能需要配置系统资源，如为 HTTP （例如，MaxIOThreads，MaxWorkerThreads） 的 IIS。  
  
 使用 ASP.NET 2.0 和 ASP.Net 4 中， \<processModel autoConfig ="true"\> machine.config 文件中的设置将自动配置为获得最佳性能的以下设置：  
  
-   最大工作线程  
  
-   最大 IO 线程  
  
-   httpRuntime 元素 minFreeThreads 特性  
  
-   httpRuntime 元素 minLocalRequestFreeThreads 特性  
  
-   maxConnection 属性\<connectionManagement\>元素 （网络设置）  
  
 有关配置会影响适配器性能的参数的详细信息，请参阅[ASP.NET processModel 元素的配置设置](http://go.microsoft.com/fwlink/?LinkId=158080)(http://go.microsoft.com/fwlink/?LinkId=158080)。  
  
 有关可能会影响 BizTalk Server 适配器的配置设置的详细信息，请参阅[配置参数会影响适配器性能](http://go.microsoft.com/fwlink/?LinkID=154200)(http://go.microsoft.com/fwlink/?LinkID=154200)。  
  
 除了优化你的 BizTalk Server 应用程序，在同一台服务器上运行其他 ASP.NET 应用程序可以对总体性能产生影响。 请务必优化所有 ASP.NET 应用程序，为了减少系统资源的需求。 有关详细信息，请参阅[ASP.NET 性能](http://go.microsoft.com/fwlink/?LinkId=158081)(http://go.microsoft.com/fwlink/?LinkId=158081)。  
  
 为最高的性能配置时，请考虑优化其他外部系统，如消息传递引擎 （消息队列，MQSeries）、 应用程序、 数据库、 Active Directory 等的总体 BizTalk 解决方案的一部分。 在任何其他这些外部系统的性能瓶颈可以产生负面影响对 BizTalk 解决方案。  
  
### <a name="downstream-bottlenecks"></a>下游瓶颈  
 如果下游系统不能从 BizTalk 接收数据速度不够快，则此输出数据将备份 BizTalk 数据库中。 这导致膨胀、 导致限制，以启动、 收缩接收管道中，和影响 BizTalk 系统的整体吞吐量。 此直接指示是假脱机表增长。 有关瓶颈和假脱机表的详细信息，请参阅[如何标识 MessageBox Database1 的瓶颈](../technical-guides/how-to-identify-bottlenecks-in-the-messagebox-database1.md)。  
  
### <a name="throttling-impact"></a>限制的影响  
 限制将最终开始保护系统免受到达不可恢复的状态。 因此，你可以使用限制验证系统是否运行正常并发现问题的源。 确定从限制状态瓶颈的原因后，分析的其他性能计数器以确定问题的源。 例如，在 MessageBox 数据库上的大量争用可能由于高 CPU 使用率，引起过度分页到磁盘上由内存不足情况引起的。 在 MessageBox 数据库上的大量争用还可能引起由于饱和磁盘驱动器的高锁争用。 虽然偶尔限制并不严重的威胁： 性能时，持久限制可以指示更重要的基本问题。 有关将在其中 BizTalk Server 使用限制这些条件的详细信息，请参阅[如何 BizTalk Server 实现主机限制](http://go.microsoft.com/fwlink/?LinkID=155286)(http://go.microsoft.com/fwlink/?LinkID=155286)。  
  
 了解 BizTalk Server 限制可以如何帮助管理可用资源的使用和最大程度减少资源争用的详细信息，请参阅[优化资源使用通过主机限制](http://go.microsoft.com/fwlink/?LinkID=155770)(http://go.microsoft.com/fwlink/?LinkID=155770)。  
  
## <a name="biztalk-application-counters"></a>BizTalk 应用程序计数器  
  
|对象|实例|计数器|Description|  
|------------|--------------|-------------|-----------------|  
|BizTalk 消息传送|RxHost|Documents received/sec|传入速率|  
|BizTalk 消息传送|TxHost|Documents processed/Sec|传出速率|  
|XLANG/s 业务流程|PxHost|Orchestrations Completed/Sec.|处理速率|  
|BizTalk: MessageBox： 常规计数器|MsgBoxName|假脱机大小|所有主机队列的累积大小|  
|BizTalk: MessageBox： 常规计数器|MsgBoxName|Tracking Data Size|MessageBox 上 TrackingData 表的大小|  
|BizTalk:MessageBox:主机计数器|PxHost:MsgBoxName|Host Queue - Length|特定主机队列中的消息数|  
|BizTalk:MessageBox:主机计数器|TxHost:MsgBoxName|Host Queue - Length|特定主机队列中的消息数|  
|BizTalk：消息代理|RxHost|Database Size|发布 (PxHost) 队列的大小|  
|BizTalk：消息代理|PxHost|Database Size|发布 (TxHost) 队列的大小|  
|BizTalk：消息代理|HostName|Message delivery throttling state|影响 XLANG 和出站传输|  
|BizTalk：消息代理|HostName|限制状态消息发布|影响 XLANG 和入站传输|  
  
### <a name="where-do-i-start"></a>应该从何处开始？  
 监视**消息传递限制状态**和**消息发布限制状态**对于每个主机实例是启动的好时机。 如果这些计数器的值不为零，这表明限制 BizTalk 系统中，你可以进一步分析瓶颈的原因。 有关的其他性能计数器的说明，请参阅[数据库层中的瓶颈](../technical-guides/bottlenecks-in-the-database-tier.md)。  
  
## <a name="orchestration-engine-performance-counters"></a>业务流程引擎性能计数器  
 我们强烈建议你精细优化业务流程运行时设置，因为连续业务流程 dehydration\rehydration 和持久性点可以产生严重影响整体性能。  测试可能包含多个持久性点和事务的作用域的复杂业务流程时，必须使用以下计数器。  
  
|计数器|注释|  
|-------------|--------------|  
|Orchestrations dehydrated/sec|平均每秒冻结的业务流程数。|  
|Orchestrations rehydrated/sec|平均每秒解除冻结的业务流程数。|  
|Persistence points/sec|平均每秒持久化业务流程实例的次数。|  
|Orchestrations resident in memory|当前以主机实例为宿主的业务流程实例的数量。|  
|Orchestrations completed/sec|平均每秒完成的业务流程数。|  
|Orchestrations suspended/sec|平均每秒挂起的业务流程数。|  
|Transactional scopes committed/sec|平均每秒提交的事务作用域数。|  
|Transactional scopes aborted/sec|平均每秒中止的事务作用域数。|  
|Transactional scopes compensated/sec|平均每秒补偿的事务作用域数。|  
  
## <a name="backlog-buildup"></a>积压工作构建  
 1-1 部署对于方案 1 的消息 1 的消息中接收结果的位置处理和传输时，如果传出速率不等于的传入速率，没有囤积系统中。 在此情况下，你可以监视假脱机大小。 在确定传出速率瓶颈的原因，每次运行单一的用例方案。 隔离业务流程，接收位置，并发送到单独的主机的位置。  
  
 将 BizTalk:Message 框： 主机计数器添加到你要监视一台主机的性能监视器日志。 主机队列的长度： 计数器可跟踪的特定主机队列中的消息总数。 如果一个或多个这些计数器将继续增长段时间后，让特别注意的这些主机执行的项目。  
  
 如果假脱机以线性方式增长，确定哪些应用程序队列负责假脱机增长。  
  
 如果没有任何应用程序队列增长和假脱机将不断变大，这可能意味着清除作业是否无法保持同步。 如果代理未运行或没有 SQL Server 上的其他系统资源争用，将发生这种情况。  
  
 如果应用程序队列之一在不断增长，诊断这种增长的原因。 监视无法清空特定的应用程序队列的系统上的系统资源 （例如，业务流程主机-Q 增长由于服务器上的 CPU 资源不足）。 此外，请验证的特定主机实例的限制计数器的值。  
  
 如果 BizTalk:Messsage 代理 Message Delivery Throttling State 和消息发布限制状态性能计数器不为零，则检查此值以确认限制的原因 （例如，内存超过了阈值，正在进行的消息计数太最高价、，依此类推）。  
  
## <a name="stand-alone-profiler"></a>独立探查器  
 你可以使用性能计数器检测在高级别瓶颈的位置。 但是，一旦缩小，你可能需要检查多个代码密切来帮助简化问题。 独立探查器附带使用 Visual Studio 2010 可以是一个非常有帮助的工具，以帮助诊断代码其中花费大部分其周期。 有关详细信息，请参阅  
  
## <a name="l2l3-cache"></a>L2/L3 缓存  
 从硬件的角度看，可以通过使用板载 CPU 缓存中获得的最大优势。 较高的 CPU 高速缓存可增加高速缓存命中率，减少系统在内存和磁盘之间读/写数据页的需要。  
  
## <a name="64-bit-performance-bottlenecks"></a>64 位性能瓶颈  
 64 位系统的性能表现可能不如 32 位系统获得的性能。 这是可能出于几个原因，最重要的一个是内存。  
  
 具有 2 GB 的内存的 32 位系统上的性能测量和比较的结果具有 2 GB 的内存的类似 64 位系统不比较相同的操作。 64 位系统将显示为磁盘 i/o 绑定 （低 %磁盘空闲时间和高的磁盘队列长度） 和 CPU 限制 （最大 CPU 和高上下文切换）。 但是，这是不是因为在 64 位系统上执行文件 I/O 开销更大。  
  
 64 位系统是更多内存密集型 （64 位寻址） 这将导致占用的大部分 2 GB 的可用内存的操作系统。 在此情况下，大多数其他操作会导致分页到磁盘的强调文件子系统。 因此，系统花费 CPU 周期分页的内存的输入/输出这两个数据和它的代码，并且受成本高的磁盘延迟。 它表现为更多的磁盘争用和更多的 CPU 占用。  
  
 为了解决此问题的方法是来向上扩展服务器通过升级内存。 向上扩展到 8 GB 是主意，但是，添加更多的内存将不会帮助提高吞吐量，除非源的问题是由于内存不足造成的 CPU 资源不足。  
  
## <a name="using-bam-to-identify-bottlenecks-and-high-latency-issues"></a>使用 BAM 确定瓶颈和高延迟问题  
 重要延迟较低时，你可以使用 BAM 以测量系统完成 BizTalk Server 系统中的每个阶段所花费的时间。 你可以使用 HAT 调试消息的状态和诊断的路由的消息中的问题的根源，但可以使用 BAM 来跟踪各种点通过消息流。 通过创建跟踪配置文件用于定义与延续的活动 BAM，您可以衡量系统来帮助跟踪工作流进程中成本最高的阶段的不同部分之间的延迟。  
  
 可以使用中 HAT Orchestration 调试器查询的挂起的实例，恢复在调试模式下，实例并添加适当的断点使用技术的详细信息视图。 这些操作允许您分步跟踪活动和调试消息。  
  
 可以设置断点来跟踪以下事件：  
  
-   业务流程的启动和结束  
  
-   形状的启动和结束  
  
-   消息的发送或接收  
  
-   异常  
  
 在每个断点，您可以查看有关局部变量、消息及其属性、端口和角色链接的信息。  
  
## <a name="see-also"></a>另请参阅  
 [查找并消除瓶颈](../technical-guides/finding-and-eliminating-bottlenecks.md)