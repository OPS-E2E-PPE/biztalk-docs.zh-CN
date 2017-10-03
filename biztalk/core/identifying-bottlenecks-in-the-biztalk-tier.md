---
title: "识别 BizTalk 层中的瓶颈 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f38ade78-8af3-4485-9b2a-5e4cdba965d2
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5dd356ac3b8563d207e3534fc503711f11a9c8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="identifying-bottlenecks-in-the-biztalk-tier"></a>识别瓶颈 BizTalk 层中
BizTalk 层可分为以下功能区域：  
  
-   接收  
  
-   处理  
  
-   传输  
  
-   跟踪  
  
-   其他  
  
 对于这些区域，如果系统资源（CPU、内存和磁盘）似乎趋于饱和，请通过向上扩展来升级服务器。 如果系统资源不饱和，请执行本部分中介绍的这些步骤。  
  
## <a name="bottlenecks-in-the-receive-location"></a>接收位置中的瓶颈  
 如果消息在接收位置开始累积（例如，文件接收文件夹不断增大或传出队列没有很快清空），则说明可能由于内部受阻而导致系统处理数据的速率不够快，无法跟上传入负载的速率（如果订户无法足够快速地处理数据而导致数据库表中出现积压，BizTalk 将会降低接收速率）。 如果是由于硬件限制所导致的瓶颈，请尝试向上扩展。 通过向映射到接收处理程序的主机添加主机实例（服务器）也能够得到扩展。 使用 Perfmon 来监视系统资源的利用率。 确认外部接收位置不是导致瓶颈的原因至关重要。 例如，高速磁盘 IO 导致远程文件共享饱和，远程传出队列的宿主服务器不饱和，或者线程中用于生成 HTTP/SOAP 负载的客户端饱和。  
  
## <a name="processing-bottlenecks"></a>处理瓶颈  
 如果“主机队列 - 长度”计数（请参阅下面的 Perfmon 计数器表）正在增加，它表明业务流程的完成速度不够快。 这可能是由于内存争用或 CPU 饱和所致。  
  
 如果业务流程服务器是瓶颈，请使用 Perfmon 来标识来源。  
  
 如果服务器受到 CPU 的约束，请考虑以下情况：  
  
-   如果工作流复杂，请考虑将业务流程拆分成多个较小的业务流程  
  
    > [!NOTE]
    >  将一个业务流程拆分成多个工作流可能会导致额外的延迟并使复杂性增加。  
  
-   如果使用了一些复杂的映射，则请考虑是否可以将它们移动到发送/接收端口（验证哪个端口具有额外的带宽）。  
  
-   请考虑向上扩展硬件；如果可能，请考虑配置其他处理服务器来实现向外扩展。  
  
## <a name="transmitting-bottlenecks"></a>传输瓶颈  
 如果传输服务器的资源（例如磁盘、内存和 CPU）趋于饱和，请考虑向上扩展服务器。如果可能，请考虑向外扩展到其他发送宿主服务器。 如果目标（位于 BizTalk 外部）接收数据的速度不够快，发送层则可能成为瓶颈。 这将会导致消息在 MessageBox 数据库（应用程序 SendHostQ）中累积。  
  
 如果所有的终结点都在拓扑结构的范围内，请考虑在目标处隔离导致问题的原因。 例如，HTTP/SOAP 位置是否经过优化配置以接收负载，或者是否能够向外扩展？ 目标增长是否是由于 BizTalk 传送了过多的输出消息所致？ 如果是，请考虑通过维护计划来存档和清除目标消息。 例如，目标文件夹中的大量文件可能严重影响 BizTalk 服务将数据提交到磁盘驱动器的能力。  
  
## <a name="tracking-bottlenecks"></a>跟踪瓶颈  
 跟踪主机实例负责将 BAM 以及跟踪的消息事件和服务实例数据从 MessageBox 数据库（TrackingData 表）移至 BizTalkDTADb 和/或 BAMPrimaryImport 数据库表。 如果配置了多个 MessageBox 数据库，跟踪主机实例将对每个 MessageBox 使用四个线程。  
  
 此主机实例可能会受到 CPU 的约束。 如果的确是这种情况，请考虑向上扩展服务器，或者将其他服务器配置为启用主机跟踪以实现向外扩展。 多个主机实例将自动平衡多个配置的 MessageBox 的负载。  
  
 如果 MessageBox 数据库的 TrackingData 表开始备份，这通常是由于在 BizTalkDTADb 和/或 BAMPrimaryImport 数据库上的数据维护作业没有按照配置来运行，导致 BizTalkDTADb 和/或 BAMPrimaryImport 数据库的增大所致。 一旦这些数据库变得过大，将会对跟踪主机将数据插入这些表的能力产生负面影响，并导致在 MessageBox 数据库表中备份跟踪数据。 MessageBox 的增长-> TrackingData 表将导致限制进行计划。  
  
## <a name="other"></a>其他  
 配置部署拓扑结构，以使不同的功能运行在专用的独立主机实例中。 这样，每个主机实例将获得自己的资源集（在 32 位系统中、2GB 虚拟内存地址空间、句柄和线程）。 如果服务器足够强大（足够的 CPU 余量、内存）并能够承载多个主机实例，则可以将它们全部配置为在相同的物理计算机上运行。 如果不是，也可通过将功能移动到专用服务器上以方便向外扩展。 在多个服务器上运行相同的功能也可用于提供高可用性的配置。  
  
## <a name="biztalk-system-performance-counters"></a>BizTalk 系统性能计数器  
  
|对象|实例|计数器|监视目的|  
|------------|--------------|-------------|------------------------|  
|处理器|_Total|% Processor Time|资源争用|  
|处理|BTSNTSvc|Virtual Bytes|内存泄漏/膨胀|  
|处理|BTSNTSvc|Private Bytes|内存泄漏/膨胀|  
|处理|BTSNTSvc|Handle Count|资源争用|  
|处理|BTSNTSvc|线程计数|资源争用|  
|物理磁盘|_Total|% Idle Time|资源争用|  
|物理磁盘|_Total|Current Disk Queue Length|资源争用|  
  
### <a name="cpu-contention"></a>CPU 争用  
 如果处理器趋于饱和，请考虑将接收与发送和业务流程分开以将应用程序分为多个部分。 所使用的方法是：首先创建不同的主机，然后将这些主机映射到特定功能（接收/发送/业务流程/跟踪）并将专用服务器添加到这些不同的主机中。 通常，业务流程功能需要占用大量 CPU 资源，因此将系统配置为在单独的专用服务器执行业务流程将有助于提高系统的整体吞吐率。  
  
 如果部署了多个业务流程，可以将业务流程登记到不同的专用业务流程主机上。 将不同的物理服务器映射到专用业务流程主机，将确保不同的业务流程独立并且不会争用同一物理地址空间或同一服务器上的共享资源。  
  
### <a name="memory-starvation"></a>内存资源不足  
 高吞吐量情况可能会增加对系统内存的要求。 由于 32 位进程受到可使用的内存数量的限制，建议将接收/处理/发送功能分别放在单独的主机实例中，以使每个主机接收自己的 2GB 地址空间。 此外，如果多个主机实例运行在相同的物理服务器上，则升级到 4/8GB 内存将非常有用，这样可避免在实际内存到磁盘之间进行不必要的数据交换。 长时间运行的业务流程可以存放到分配的内存再导致内存膨胀和因此限制进行计划。 大型消息也会导致高内存消耗。  
  
 可以通过降低处理大消息时克服此内存膨胀问题**内部消息队列大小**和**每个 CPU 进程内消息**特定主机的值。  
  
### <a name="disk-contention"></a>磁盘争用  
 如果磁盘饱和 （例如，文件/MSMQ 传输） 请考虑升级到多个轴和条带化磁盘具有 RAID 1 + 0。 此外每当使用文件传输时务必要确保 （接收和发送） 的文件夹不执行增长得太大 (> 50000 文件)。  
  
 如果 BizTalk Server 由于以下提到的各种原因而选择阻止传入数据进入系统，则接收文件夹可能变得很大。 将数据从发送文件夹中移出也是十分重要的，这使得该文件夹的增大不会影响 BizTalk Server 写入其他数据的能力。 对于非事务性 MSMQ 队列，建议远程创建接收队列，以便减少 BizTalk Server 上的磁盘争用。  
  
 该配置（远程非事务性队列）还具有一个优点，即高可用性，这是因为队列的宿主远程服务器可以群集。  
  
### <a name="other-system-resource-contention"></a>其他系统资源争用  
 根据所配置的传输的性质，可能需要针对 HTTP/SOAP 配置系统资源，如 IIS（例如，MaxIOThreads 和 MaxWorkerThreads）。  
  
### <a name="downstream-bottlenecks"></a>下游瓶颈  
 如果下游系统从 BizTalk 接收数据的速度不够快，则将在 BizTalk 数据库中备份此输出数据并导致膨胀，从而导致触发阻止功能并缩小接收管道，进而影响 BizTalk 系统的总体吞吐量。 这一问题的直接表现将是后台处理的增加。  
  
### <a name="throttling-impact"></a>触发阻止功能的影响  
 最终将触发阻止功能以保护系统不要进入不可恢复的状态。 因此限流是验证系统是否工作正常并发现问题根源的好时机。 通过限流状态找到导致瓶颈的原因之后，请分析其他性能计数器以深入查找问题的根源。  
  
 例如，MessageBox 数据库上的大量争用可能是由于大量使用 CPU 所致，大量使用 CPU 则可能是由于对磁盘进行过度分页所致，而对磁盘过度分页则可能是因为内存不足所致。 MessageBox 上的大量争用也可能是由于较高的锁争用所致，此锁争用则可能是由于磁盘设备趋于饱和所致。  
  
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
 监视**消息传递限制状态**和**消息发布限制状态**对于每个主机实例通常是启动的好时机。 如果这些计数器的值不为零，则表示 BizTalk 系统内正发生限流，并可进一步分析导致瓶颈的原因。 有关的其他性能计数器的说明，请参阅[标识数据库层中的瓶颈](http://msdn.microsoft.com/library/f1dc58b5-73b0-41b5-9a1e-c0698485c732)。  
  
## <a name="backlog-buildup"></a>出现积压  
 对于 1-1 部署方案，接收 1 个消息将导致处理并传输 1 个消息，如果传出速率不等于传入速率，积压将在系统中的某处累积。 在这种情况下，可以监视 Spool Size。  
  
 如果 Spool 呈线性增长，则可以进一步深入探查以确认是哪个应用程序队列导致 Spool 增长。  
  
 如果应用程序队列都没有增长，而 Spool 持续增长，这可能表明由于代理未运行或 SQL 服务器上其他系统资源的争用导致了作业无法及时清除。  
  
 如果某一应用程序队列增长，则诊断该增长的原因就尤为重要了。 监视无法清空特定应用程序队列的系统上的系统资源（例如，由于服务器上 CPU 资源紧张而导致业务流程 Host-Q 不断增长）。 此外还要验证特定主机实例的阻止计数器的值。  
  
 如果送达/发布状态不为零，请检查该值以确认限流的原因（例如，超过内存阈值、正在处理的消息数过多等）。  
  
## <a name="f1-profiler"></a>F1 事件探查器  
 使用性能计数器，可以快速深入地检测瓶颈位置。 然而，一旦范围缩小，则可能需要进一步对代码进行深入探查以帮助缓解此问题。 Visual Studio 附带的 F1 事件探查器是非常有用的工具，它可帮助诊断代码在哪些地方花费了大量时间。  
  
 符号对帮助创建更多有意义的堆栈（特别对非托管代码）非常重要。 例如，F1 事件探查器可帮助查明调用数和返回 API 调用所需的时间。 进一步深入探查堆栈，可能检测到高延迟时间的根本原因。 它可能是一个对数据库查询的阻止调用或仅是一个等待事件的调用。  
  
## <a name="l2l3-cache"></a>L2/L3 缓存  
 从硬件方面来看，使用 CPU 上的高速缓存可以获得最大益处。 较高的 CPU 高速缓存可增加高速缓存命中率，减少系统在内存和磁盘之间读/写数据页的需要。  
  
## <a name="64-bit-performance-bottlenecks"></a>64 位性能瓶颈  
 64 位系统的性能表现可能不如 32 位系统获得的性能。 这可能是由于若干原因造成的，最重要的原因就是内存。  
  
 对内存都为 2 GB 的 32 位系统和 64 位系统进行性能比较，并不是真正的同类型比较。 64 位系统看起来受到 disk-IO 限制（较低的磁盘空闲时间百分比和较长的磁盘队列长度）以及 CPU 限制（最大的 CPU 占用率和大量的上下文切换）。 然而，这并不是因为在 64 位系统上执行文件 IO 开销更大的缘故。  
  
 64 位系统需要更多内存（64 位寻址），而这会导致操作系统占用 2 GB 可用内存中的大部分内存。 一旦发生这种情况，大部分的其他操作将导致对磁盘进行分页，这将给文件子系统造成压力。 此时，系统不仅占用多个 CPU 周期以将数据和代码页从内存调入/调出，而且受到大量的磁盘延迟开销的影响。 它表现为更多的磁盘争用和更多的 CPU 占用。  
  
 缓解此问题的方法是：通过升级内存（最好为 8 GB）来向上扩展服务器。 然而，增加更多的内存并不会帮助提高吞吐量，除非导致该问题的根本原因是由于内存较小从而导致 CPU 资源紧张的缘故。  
  
## <a name="using-bam-to-identify-bottlenecks-and-high-latency-issues"></a>使用 BAM 来查找瓶颈和高延迟问题  
 在低延迟非常重要的情况下，可以使用 BAM 来测量系统完成 BizTalk 系统内的每个阶段所花费的时间。 虽然跟踪的消息事件和服务实例数据可用于调试路由消息中的消息状态并诊断问题的根源，但 BAM 可用于跟踪消息流上的各个点。 通过创建一个 BAM 跟踪配置文件（定义一个带有继续符的活动），可以测量系统不同部分之间的延迟，以帮助跟踪工作流进程中成本最高的阶段。