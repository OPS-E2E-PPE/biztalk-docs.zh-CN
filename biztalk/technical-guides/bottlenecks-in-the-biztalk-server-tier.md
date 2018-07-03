---
title: BizTalk Server 层的瓶颈 |Microsoft Docs
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
ms.openlocfilehash: 8f8c7b4366390c040d7a4a34b473bdf4c3cfd352
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004942"
---
# <a name="bottlenecks-in-the-biztalk-server-tier"></a>BizTalk Server 层的瓶颈
BizTalk 层可分为以下功能区域：  
  
- 接收  
  
- 处理  
  
- 传输  
  
- 跟踪  
  
- 其他  
  
  对于这些区域，如果系统资源 （CPU、 内存和磁盘） 似乎趋于饱和，通过扩展平台升级服务器或缩小基于你的应用程序的特征。 如果系统资源不饱和，请执行本部分中介绍的这些步骤。  
  
## <a name="bottlenecks-in-the-receive-location"></a>接收位置中的瓶颈  
 如果消息在接收位置生成 （例如，文件接收文件夹增长大），这表示无法以足够快的速度消减数据才能跟上传入负载的系统。 这是因为内部限制。 它是 BizTalk Server 接收的速率减少到如果订阅服务器无法处理的数据快速足够导致积压累积在数据库表中的。 如果通过硬件限制所导致的瓶颈，请尝试纵向扩展。 有关向上扩展的详细信息，请参阅 BizTalk Server 2010 文档中的以下主题：  
  
- [纵向扩展 BizTalk Server 层](http://go.microsoft.com/fwlink/?LinkId=158073)(http://go.microsoft.com/fwlink/?LinkId=158073)。  
  
- [纵向扩展 SQL Server 层](http://go.microsoft.com/fwlink/?LinkId=158077)(http://go.microsoft.com/fwlink/?LinkId=158077)。  
  
  还有可能要横向扩展通过将主机实例 （服务器） 添加到主机映射到接收处理程序。 有关向外扩展的详细信息，请参阅 BizTalk Server 2010 文档中的以下主题：  
  
- [BizTalk Server 层向外缩放](http://go.microsoft.com/fwlink/?LinkId=158076)(http://go.microsoft.com/fwlink/?LinkId=158076)。  
  
- [SQL Server 层向外缩放](http://go.microsoft.com/fwlink/?LinkId=158075)(http://go.microsoft.com/fwlink/?LinkId=158075)。  
  
  使用 Perfmon 来监视系统上的资源使用。 确认外部接收位置不是导致瓶颈的原因至关重要。 例如，确认是否远程文件共享饱和由于较高的磁盘 I/O、 远程传出队列的宿主服务器不饱和，或用于生成 HTTP 负载的客户端不会耗尽线程上。  
  
## <a name="processing-bottlenecks"></a>处理瓶颈  
 如果增加主机队列-长度性能计数器，它表明业务流程速度不够快完成。 有关详细信息，请参阅本主题中的 Perfmon 计数器表。 这可能是由于内存争用或 CPU 饱和所致。  
  
 如果业务流程服务器是瓶颈，请使用 Perfmon 来标识来源。  
  
 如果服务器受到 CPU 的约束，请考虑以下情况：  
  
-   如果在工作流复杂，请考虑将拆分到多个较小的业务流程的业务流程  
  
    > [!NOTE]  
    >  将一个业务流程拆分成多个工作流可能会导致额外的延迟并使复杂性增加。 多个工作流也会导致增加发布到和从 BizTalkMsgBoxDb，使用消息的数量数据库带来额外压力。  
  
-   如果使用复杂的映射，请考虑是否可以将它们移到接收/发送端口。 请务必验证哪个端口具有额外的带宽。  
  
-   请考虑向上扩展硬件或通过配置其他处理服务器向外扩展。  
  
## <a name="transmitting-bottlenecks"></a>传输瓶颈  
 如果承载对资源 （例如，磁盘、 内存或 CPU） 趋于饱和发送适配器的服务器，请考虑向上扩展服务器或向外扩展到其他主机服务器发送。 如果目标（位于 BizTalk 外部）接收数据的速度不够快，发送层则可能成为瓶颈。 这将会导致消息在 MessageBox 数据库（应用程序 SendHostQ）中累积。  
  
 如果所有终结点拓扑的范围内，隔离的目标处的原因。 例如，确定是否以最佳方式配置 HTTP 位置来接收负载。 如果没有，请考虑向外扩展。此外确定是否由于 BizTalk 传送了过多的输出消息增长目标。 如果是，您可能需要的维护计划来存档和清除目标消息。 目标文件夹中的文件较大数字会严重影响 BizTalk 服务的数据提交到磁盘驱动器的功能。  
  
## <a name="tracking-bottlenecks"></a>跟踪瓶颈  
 跟踪主机实例是负责将业务活动监视 (BAM) 和运行状况与活动跟踪 (HAT) 数据从 MessageBox 数据库 （TrackingData 表） 移至 BizTalk 跟踪和/或 BAM 主导入数据库表。 如果配置了多个 MessageBox 数据库，跟踪主机实例使用每个 MessageBox 数据库的四个线程。  
  
 就可以跟踪主机实例是受到 CPU 的约束。 如果是，请考虑向上扩展服务器，或通过配置主机跟踪启用与另一台服务器的横向扩展。 多个主机实例将自动进行负载平衡配置多个 MessageBox 数据库。 有关缩放的详细信息，请参阅主题[缩放你的解决方案](http://go.microsoft.com/fwlink/?LinkId=158078)(http://go.microsoft.com/fwlink/?LinkId=158078)。  
  
 如果 MessageBox 数据库中的 TrackingData 表增长大，它通常是因为 BizTalk 跟踪和/或 BAM 主导入数据库上的数据维护作业未运行经过配置之后，从而导致 BizTalk 跟踪和/或 BAM 主导的增长导入数据库。 这些数据库变得过大后它可以跟踪主机能够将数据插入 TrackingData 表产生负面影响。 这会导致在 MessageBox 数据库表中备份跟踪的数据。 TrackingData 表的增长会导致限制，以开始。  
  
 只应启用最小跟踪所需的应用程序，因为这将减少记录的数据量并降低跟踪瓶颈的风险。 有关禁用单个项，例如业务流程和发送/接收端口的跟踪设置的信息，请参阅[如何禁用跟踪](http://go.microsoft.com/fwlink/?LinkId=160064)(http://go.microsoft.com/fwlink/?LinkId=160064)。  
  
## <a name="other"></a>其他  
 配置部署拓扑结构，以使不同的功能运行在专用的独立主机实例中。 这种方式每个主机实例获取自己的资源 （例如，在 32 位系统、 2GB 虚拟内存地址空间、 句柄、 线程） 的一组。 服务器是否具有足够的 CPU 余量和内存来承载多个主机实例，则可以配置为在同一台物理计算机上运行。 如果没有，请考虑通过将功能移动到专用服务器来向外扩展。 在多个服务器上运行相同的功能也可用于提供高可用性的配置。  
  
## <a name="biztalk-system-performance-counters"></a>BizTalk 系统性能计数器  
  
|Object|实例|计数器|监视目的|  
|------------|--------------|-------------|------------------------|  
|处理器|_Total|% Processor Time|资源争用|  
|处理|BTSNTSvc|Virtual Bytes|内存泄漏/膨胀|  
|处理|BTSNTSvc|Private Bytes|内存泄漏/膨胀|  
|处理|BTSNTSvc|Handle Count|资源争用|  
|处理|BTSNTSvc|线程计数|资源争用|  
|物理磁盘|实例 （_i)|% Idle Time|资源争用|  
|物理磁盘|实例 （_i)|Average Disk Queue Length|资源争用|  
  
### <a name="cpu-contention"></a>CPU 争用  
 如果处理器趋于饱和，您可以通过将接收与发送和业务流程的片段应用程序。 若要执行此操作，创建单独的主机、 映射到特定功能 （接收/发送/业务流程/跟踪） 的主机和将专用的服务器添加到这些不同的主机。 业务流程功能通常是大量占用 CPU。 如果将系统配置以便在单独的专用服务器上执行业务流程时，这可以帮助提高系统的整体吞吐量。  
  
 如果部署了多个业务流程，您可以将其登记到不同的专用业务流程的主机。 将不同的物理服务器映射到专用业务流程主机可确保不同的业务流程是独立的并且不会争用同一物理地址空间中或在同一服务器上的共享资源。  
  
 停止未使用的主机实例。 未使用的主机实例都可竞争的 CPU 和内存资源通过定期检查要处理的消息的 MessageBox。 此外，未使用的停止接收位置、 发送端口和业务流程。  
  
### <a name="spool-table-growth"></a>后台处理表的增长  
 下游瓶颈和/或资源争用可能会导致后台处理从开始增长过并且降低整体性能。 详细信息，请参阅"后台处理表增长量"中[如何识别瓶颈在 MessageBox 数据库 1](../technical-guides/how-to-identify-bottlenecks-in-the-messagebox-database1.md)。  
  
### <a name="memory-starvation"></a>内存不足  
 高吞吐量情况可能会增加对系统内存的要求。 由于 32 位进程受到可使用的内存量，建议来分隔到单独的主机实例的接收/处理/发送功能，以便每个主机接收自己 2 GB 的地址空间。 此外，如果多个主机实例正在同一台物理服务器上运行，则可以升级到 4/8 GB 内存，以避免从实际内存到磁盘交换数据。 长时间运行的业务流程可以保存分配的内存。 这可能导致内存膨胀和限制，以开始。 大消息也会导致高内存消耗。  
  
 您可以轻松地通过降低来处理大型消息时发生的内存膨胀问题**内部消息队列大小**并**每个 CPU 的进程内消息**特定主机的值。  
  
> [!NOTE]  
>  如果延迟是一个问题，将更改为**内部消息队列大小**并**每个 CPU 的进程内消息**根据这可能会增加系统的端到端延迟进行谨慎使用。  
  
### <a name="disk-contention"></a>磁盘争用  
 如果磁盘趋于饱和 （例如，使用大量的文件 /MSMQ 传输），请考虑升级到多个心轴和条带化磁盘并用 RAID 10。 此外，无论是使用文件传输，务必确保接收和发送文件夹不会变得大于 50000 的文件。  
  
 接收文件夹可能变得大如果 BizTalk Server 将阻止传入数据进入系统。 请务必将数据从发送文件夹移动，以便在此文件夹中的增长不会影响 BizTalk Server 能够编写额外的数据。 对于非事务性 MSMQ 队列，建议远程创建接收队列，以便在 BizTalk Server 上减少磁盘争用。  
  
 远程非事务性队列配置还提供了高可用性，因为队列的宿主的远程服务器可以群集化。  
  
### <a name="other-system-resource-contention"></a>其他系统资源争用  
 根据传输的类型，可能需要配置 IIS 以实现 HTTP （例如，MaxIOThreads，MaxWorkerThreads） 等系统资源。  
  
 通过 ASP.NET 2.0 和 ASP.Net 4 中， \<processModel autoConfig ="true"\> machine.config 文件中的设置自动配置以获得最佳性能的以下设置：  
  
- 最大工作线程数  
  
- 最大 IO 线程数  
  
- httpRuntime 元素 minFreeThreads 属性  
  
- httpRuntime 元素 minLocalRequestFreeThreads 属性  
  
- maxConnection 属性\<connectionManagement\>元素 （网络设置）  
  
  有关配置影响适配器性能的参数的详细信息，请参阅[processModel 元素的 ASP.NET 配置设置](http://go.microsoft.com/fwlink/?LinkId=158080)(http://go.microsoft.com/fwlink/?LinkId=158080)。  
  
  有关可能会影响 BizTalk Server 适配器的配置设置的详细信息，请参阅[配置参数的影响适配器性能](http://go.microsoft.com/fwlink/?LinkID=154200)(http://go.microsoft.com/fwlink/?LinkID=154200)。  
  
  除了优化 BizTalk Server 应用程序，同一服务器上运行其他 ASP.NET 应用程序可以对总体性能产生影响。 请务必优化所有 ASP.NET 应用程序，以减少对系统资源需求。 有关详细信息，请参阅[ASP.NET 性能](http://go.microsoft.com/fwlink/?LinkId=158081)(http://go.microsoft.com/fwlink/?LinkId=158081)。  
  
  为最高的性能配置时，请考虑优化其他外部系统，例如消息传递引擎 （消息队列，MQSeries）、 应用程序、 数据库、 Active Directory 等的总体的 BizTalk 解决方案的一部分。 在任何这些其他外部系统中的性能瓶颈可以具有负面影响您的 BizTalk 解决方案。  
  
### <a name="downstream-bottlenecks"></a>下游瓶颈  
 如果下游系统无法接收来自 BizTalk 的速度足够快的数据，则此输出数据将备份 BizTalk 数据库中。 这导致膨胀，限制，以启动将使、 缩小接收管道中，并会影响 BizTalk 系统的整体吞吐量。 此直接指示是后台处理表的增长。 有关瓶颈和后台处理表的详细信息，请参阅[如何识别瓶颈在 MessageBox 数据库 1](../technical-guides/how-to-identify-bottlenecks-in-the-messagebox-database1.md)。  
  
### <a name="throttling-impact"></a>限制的影响  
 阻止最终会启动以保护系统免受达到不可恢复的状态。 因此，您可以使用限制来验证系统是否工作正常并发现问题的源。 确定阻止状态的瓶颈的原因后，分析其他性能计数器以确定问题根源。 例如，MessageBox 数据库上的大量争用可能是由于高 CPU 使用率，对由内存不足的情况导致的磁盘过度分页所致。 由于磁盘设备趋于饱和的高锁定争用也可能导致 MessageBox 数据库上的大量争用。 尽管偶尔限制不是性能严重的威胁，持久性阻止可以指示更重要的基本问题。 有关这些条件，BizTalk Server 将使用限制的详细信息，请参阅[如何 BizTalk Server 实现主机阻止](http://go.microsoft.com/fwlink/?LinkID=155286)(http://go.microsoft.com/fwlink/?LinkID=155286)。  
  
 有关 BizTalk 服务器的限制可以如何帮助管理可用资源的使用和最大程度减少资源争用的详细信息，请参阅[优化资源使用情况通过主机阻止](http://go.microsoft.com/fwlink/?LinkID=155770)(http://go.microsoft.com/fwlink/?LinkID=155770)。  
  
## <a name="biztalk-application-counters"></a>BizTalk 应用程序计数器  
  
|Object|实例|计数器|Description|  
|------------|--------------|-------------|-----------------|  
|BizTalk 消息传送|RxHost|Documents received/sec|传入速率|  
|BizTalk 消息传送|TxHost|Documents processed/Sec|传出速率|  
|XLANG/s 业务流程|PxHost|Orchestrations Completed/Sec.|处理速率|  
|BizTalk: MessageBox： 常规计数器|MsgBoxName|后台处理大小|所有主机队列的累积大小|  
|BizTalk: MessageBox： 常规计数器|MsgBoxName|Tracking Data Size|MessageBox 上 TrackingData 表的大小|  
|BizTalk:MessageBox:主机计数器|PxHost:MsgBoxName|Host Queue - Length|特定主机队列中的消息数|  
|BizTalk:MessageBox:主机计数器|TxHost:MsgBoxName|Host Queue - Length|特定主机队列中的消息数|  
|BizTalk：消息代理|RxHost|Database Size|发布 (PxHost) 队列的大小|  
|BizTalk：消息代理|PxHost|Database Size|发布 (TxHost) 队列的大小|  
|BizTalk：消息代理|HostName|Message delivery throttling state|影响 XLANG 和出站传输|  
|BizTalk：消息代理|HostName|消息发布阻止状态|影响 XLANG 和入站传输|  
  
### <a name="where-do-i-start"></a>应该从何处开始？  
 监视**Message Delivery Throttling State**并**Message Publishing Throttling State**对于每个主机实例是启动的好时机。 如果这些计数器的值不为零，这表明 BizTalk 系统中的阻止行为，可以进一步分析瓶颈的原因。 有关其他性能计数器的说明，请参阅[数据库层的瓶颈](../technical-guides/bottlenecks-in-the-database-tier.md)。  
  
## <a name="orchestration-engine-performance-counters"></a>业务流程引擎性能计数器  
 我们强烈建议您优化业务流程运行时设置，因为连续的业务流程 dehydration\rehydration 和持久性点可以对总体性能产生严重的影响。  测试复杂的业务流程可能包含多个持久化点和事务作用域时，必须使用以下计数器。  
  
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
  
## <a name="backlog-buildup"></a>出现积压  
 对于 1-1 部署方案 1 条消息 1 个消息接收结果的位置处理，并且传输时，如果传出速率不等于传入速率，积压工作系统中。 在这种情况下，可以监视 Spool Size。 在确定传出速率的瓶颈的原因，一次运行的单个的用例方案。 隔离业务流程、 接收位置和发送位置来分隔不同的主机。  
  
 将 biztalk: Message Box: Host Counters 添加到你要监视主机的性能监视器日志。 主机队列-长度： 计数器可跟踪特定主机队列中消息的总数。 如果一个或多个这些计数器持续不断增长，为提供特别注意这些主机执行的项目。  
  
 如果 Spool 呈线性增长，确定哪个应用程序队列导致 Spool 增长。  
  
 如果没有任何应用程序队列增长，而 Spool 持续增长，这可能意味着清除作业是无法跟上。 如果代理未运行或在 SQL Server 上的其他系统资源争用，将发生这种情况。  
  
 如果一个应用程序队列增长，诊断该增长的原因。 监视无法清空特定应用程序队列的系统上的系统资源 （例如，业务流程 HOST-Q 增长由于在服务器上的 CPU 资源不足）。 此外，验证特定主机实例的阻止计数器的值。  
  
 如果 BizTalk:Messsage 代理 Message Delivery Throttling State 和 Message Publishing Throttling State 性能计数器不为零，请检查该值以确认限流的原因 （例如，内存超出阈值，正在处理的消息计数太最高价、，等等）。  
  
## <a name="stand-alone-profiler"></a>独立 Profiler  
 性能计数器可用于检测在高级别瓶颈的位置。 但是，一旦范围缩小，你可能需要检查该问题的更多的代码紧密，以帮助简化。 使用 Visual Studio 2010 附带独立 Profiler 可以是非常有用的工具可帮助您诊断代码上花费其周期的大多数。 有关详细信息，请参阅  
  
## <a name="l2l3-cache"></a>L2/L3 缓存  
 从硬件的角度看，可以通过使用板载 CPU 高速缓存获得的最大优势。 较高的 CPU 高速缓存可增加高速缓存命中率，减少系统在内存和磁盘之间读/写数据页的需要。  
  
## <a name="64-bit-performance-bottlenecks"></a>64 位性能瓶颈  
 64 位系统的性能表现可能不如 32 位系统获得的性能。 这是可能的几个原因，最重要的一个是内存。  
  
 具有 2 GB 的内存的 32 位系统上的性能测量并比较结果为 2 gb 的内存的类似 64 位系统不比较相同的操作。 64 位系统将显示为磁盘 i/o 绑定 （低于 %磁盘空闲时间和高磁盘队列长度） 以及 CPU 限制 （最大 CPU 和高上下文切换）。 但是，这是不是因为在 64 位系统上执行文件 I/O 开销更大。  
  
 64 位系统需要更多内存密集型 （64 位寻址） 这会导致操作系统占用 2 GB 可用内存的大部分。 在此情况下，大部分的其他操作会导致对强调文件子系统的磁盘进行分页。 因此，系统花费 CPU 周期分页的内存的输入/输出这两个数据和代码，受高磁盘延迟开销。 它表现为更多的磁盘争用和更多的 CPU 占用。  
  
 若要缓解此问题的方法是来向上扩展服务器通过升级内存。 向上扩展到 8 GB 是主意，但是，添加更多的内存将无法帮助提高吞吐量，除非问题的原因是由于内存不足的情况的 CPU 资源不足。  
  
## <a name="using-bam-to-identify-bottlenecks-and-high-latency-issues"></a>使用 BAM 来查找瓶颈和高延迟问题  
 当低延迟很重要时，可以使用 BAM 来测量系统完成 BizTalk Server 系统中的每个阶段所花费的时间。 尽管可以使用 HAT 来调试消息的状态和诊断路由消息中的问题的根源，但可以使用 BAM 跟踪的消息流的各个点。 通过创建一个 BAM 跟踪配置文件用于定义带有继续符的活动，可以测量系统来帮助跟踪工作流进程中成本最高的阶段的不同部件之间的延迟。  
  
 可以使用 HAT 中业务流程调试器，查询挂起的实例，恢复处于调试模式，该实例并添加适当的断点使用技术的详细信息视图。 这些操作允许您分步跟踪活动和调试消息。  
  
 可以设置断点来跟踪以下事件：  
  
- 业务流程的启动和结束  
  
- 形状的启动和结束  
  
- 消息的发送或接收  
  
- 异常  
  
  在每个断点，您可以查看有关局部变量、消息及其属性、端口和角色链接的信息。  
  
## <a name="see-also"></a>请参阅  
 [查找并消除瓶颈](../technical-guides/finding-and-eliminating-bottlenecks.md)