---
title: 确定 BizTalk 层的瓶颈 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f38ade78-8af3-4485-9b2a-5e4cdba965d2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57e2a3df681b4ccfe00f5b16f0059d17d7471f75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382893"
---
# <a name="identifying-bottlenecks-in-the-biztalk-tier"></a>确定 BizTalk 层的瓶颈
BizTalk 层可分为以下功能区域：  
  
- 接收  
  
- 处理  
  
- 传输  
  
- 跟踪  
  
- 其他  
  
  对于这些区域，如果系统资源 （CPU、 内存和磁盘） 似乎趋于饱和，升级服务器通过纵向扩展。 如果不饱和的系统资源，请执行本节中所述的步骤。  
  
## <a name="bottlenecks-in-the-receive-location"></a>中的瓶颈接收位置  
 如果消息开始构建在接收位置 （例如，文件接收文件夹增长大或传出队列不被速度不够快耗尽） 指示系统不能将 absorb 数据才能跟上传入的足够快的速度增长加载由于内部限制 (BizTalk 降低接收速率，如果订阅服务器无法处理的数据快速足够导致积压累积在数据库表中的)。 在由于硬件限制所导致的瓶颈的情况下请尝试纵向扩展。 还有可能要横向扩展通过将主机实例 （服务器） 添加到主机映射到接收处理程序。 使用 Perfmon 来监视系统上的资源利用率。 务必确认外部接收位置不是瓶颈的原因。 例如，远程文件共享饱和高速磁盘 IO 导致远程传出队列的宿主服务器不饱和或用于生成 HTTP/SOAP 负载的客户端不会耗尽线程上。  
  
## <a name="processing-bottlenecks"></a>处理瓶颈  
 如果主机队列-长度计数 （请参阅下面的 Perfmon 计数器表） 正在增加，它表明业务流程速度不够快完成。 这可能是由于内存争用或 CPU 饱和所致。  
  
 如果业务流程服务器是瓶颈，使用 Perfmon 来标识源。  
  
 如果服务器是受到 CPU 的约束，考虑以下方面：  
  
-   如果在工作流复杂，请考虑将拆分到多个较小的业务流程的业务流程  
  
    > [!NOTE]
    >  拆分到多个工作流的业务流程可能会导致额外的延迟，并会增加复杂性。  
  
-   如果使用复杂的映射，请考虑是否可以将它们移到接收/发送端口 （验证哪个端口具有额外的带宽）。  
  
-   请考虑向上扩展硬件或如果可能，请考虑通过将额外的处理服务器配置横向扩展。  
  
## <a name="transmitting-bottlenecks"></a>传输瓶颈  
 如果传输服务器上资源 （例如，磁盘、 内存、 CPU） 趋于饱和，请考虑向上扩展服务器，或如果可能，请考虑向外扩展到其他发送宿主服务器。 如果目标 （BizTalk 外部） 不能以足够快的速度接收数据，发送层则可能成为瓶颈。 这将导致消息累积到 MessageBox 数据库 (应用程序 SendHostQ) 中。  
  
 如果在所有终结点都在拓扑的范围，请考虑隔离的目标处的原因。 例如，HTTP/SOAP 位置以最佳方式配置为接收负载或可能是向外扩展？ 是目标增长过多的输出消息由于 BizTalk 传送了？ 如果是，请考虑维护计划来存档和清除目标消息。 例如，大量的目标文件夹中的文件会严重影响 BizTalk 服务的数据提交到磁盘驱动器的功能。  
  
## <a name="tracking-bottlenecks"></a>跟踪瓶颈  
 跟踪主机实例是负责将 BAM 以及跟踪的消息事件和服务实例数据从 MessageBox 数据库 （TrackingData 表） 移至 BizTalkDTADb 和/或 BAMPrimaryImport 数据库表。 如果配置了多个 MessageBox 数据库跟踪主机实例使用每个 MessageBox 的四个线程。  
  
 很可能此主机实例可能受到 CPU 的约束。 如果出现这种情况，请考虑向上扩展服务器或横向扩展配置的另一台服务器与主机跟踪已启用。 多个主机实例将自动配置的多个 Messagebox 的平衡负载。  
  
 如果 MessageBox 数据库中的 TrackingData 表开始备份，它通常是因为配置导致的 BizTalkDTADb 和/或 BAMPrimaryImport 增长 BizTalkDTADb 和/或 BAMPrimaryImport 数据库上的数据维护作业未运行数据库。 一旦这些数据库变得太大，它可以跟踪主机能够将数据插入到 MessageBox 数据库表中的备份导致所跟踪的数据的这些表上产生负面影响。 MessageBox 的增长-> TrackingData 表将会导致限流。  
  
## <a name="other"></a>其他  
 配置的部署拓扑，以便在专用的独立主机实例中运行不同的功能。 这种方式每个主机实例获取自己的 （上一个 32 位系统、 2GB 虚拟内存地址空间、 句柄、 线程） 的资源集。 如果服务器是功能强大配置足够 （足够的 CPU 余量、 内存） 来承载多个主机实例，它们可以全部在同一台物理计算机上运行。 如果没有，这还使得它易于通过将功能移动到专用服务器来进行扩展。 多个服务器上运行相同的功能也可用于提供高度可用的配置。  
  
## <a name="biztalk-system-performance-counters"></a>BizTalk 系统性能计数器  
  
|Object|实例|计数器|监视目的|  
|------------|--------------|-------------|------------------------|  
|处理器|_Total|处理器时间百分比|资源争用|  
|Process|BTSNTSvc|虚拟字节数|内存泄漏/膨胀|  
|Process|BTSNTSvc|专用字节数|内存泄漏/膨胀|  
|Process|BTSNTSvc|句柄计数|资源争用|  
|Process|BTSNTSvc|线程计数|资源争用|  
|物理磁盘|_Total|空闲时间百分比|资源争用|  
|物理磁盘|_Total|Current Disk Queue Length|资源争用|  
  
### <a name="cpu-contention"></a>CPU 争用  
 如果处理器趋于饱和，请考虑通过将接收与发送和业务流程来分段应用程序。 若要实现此目的的方法是通过创建单独的主机，映射到特定功能 （接收/发送/业务流程/跟踪） 这些主机和添加专用服务器添加到这些不同的主机。 业务流程功能通常用来识别为 CPU 需求很大，因此配置系统，以便在单独的专用服务器上执行业务流程可帮助提高系统的整体吞吐量。  
  
 如果部署了多个业务流程，就可以登记到不同的专用业务流程主机。 将不同的物理服务器映射到专用业务流程主机可确保不同的业务流程是独立的并且不会争用同一物理地址空间中或在同一服务器上的共享资源。  
  
### <a name="memory-starvation"></a>内存不足  
 高吞吐量情况可能会增加系统内存的需求。 由于 32 位进程受到可使用的内存量，建议来分隔到单独的主机实例的接收/处理/发送功能，以便每个主机接收自己 2 GB 的地址空间。 此外，如果同一台物理服务器上运行多个主机实例是升级到 4/8 GB 内存，为了避免必须从实际内存到磁盘交换数据很有用。 长时间运行的业务流程可容纳再导致内存膨胀和限流分配的内存。 大消息也会导致高内存消耗。  
  
 可以通过降低来处理大消息时解决此内存膨胀问题**内部消息队列大小**并**每 CPU 进程内消息**特定主机的值。  
  
### <a name="disk-contention"></a>磁盘争用  
 如果磁盘趋于饱和 （例如，文件 /MSMQ 传输），请考虑升级到多个心轴和条带化磁盘并用 RAID 1 + 0。 此外一旦使用文件传输是必须确保该文件夹 （接收和发送） 不会变得过大 (> 50,000 文件)。  
  
 接收文件夹可能变得大如果 BizTalk Server 选择阻止传入数据进入出于下面所述的各种原因而系统。 务必也在将数据从发送文件夹移动，以便在此文件夹中的增长不会影响 BizTalk Server 能够编写额外的数据。 对于非事务性 MSMQ 队列，建议远程创建接收队列，以便在 BizTalk server 上减少磁盘争用。  
  
 此配置 （远程非事务性队列） 还提供了高可用性的好处，如队列的宿主的远程服务器可以群集化。  
  
### <a name="other-system-resource-contention"></a>其他系统资源争用  
 根据配置的传输的性质可能需要配置系统资源，如 IIS HTTP/SOAP （例如，MaxIOThreads，MaxWorkerThreads）。  
  
### <a name="downstream-bottlenecks"></a>下游瓶颈  
 如果下游系统接收数据快速足够从 BizTalk 此输出数据将导致膨胀，从而导致限流缩小接收管道，进而影响 BizTalk 的整体吞吐量在 BizTalk 数据库备份系统。 此直接指示将后台处理增长。  
  
### <a name="throttling-impact"></a>限制的影响  
 阻止最终将触发以保护系统免受达到不可恢复的状态。 因此限流是验证系统是否工作正常并发现问题根源的好时机。 通过限流状态确定了瓶颈的原因之后，分析其他性能计数器，以向下钻取到此问题的源。  
  
 例如，MessageBox 数据库上的大量争用可能是由于 CPU 使用率过高，这可能由于对磁盘可能由于内存不足而导致过度分页所致。 MessageBox 上的大量争用也可能引起高锁争用可能是造成磁盘设备趋于饱和。  
  
## <a name="biztalk-application-counters"></a>BizTalk 应用程序计数器  
  
|Object|实例|计数器|Description|  
|------------|--------------|-------------|-----------------|  
|BizTalk 消息传送|RxHost|Documents Received/Sec|传入速率|  
|BizTalk 消息传送|TxHost|处理的文档数/秒|传出速率|  
|XLANG/s 业务流程|PxHost|业务流程完成数/秒。|处理速率|  
|BizTalk:MessageBox:常规计数器|MsgBoxName|后台处理大小|所有主机队列的累积大小|  
|BizTalk:MessageBox:常规计数器|MsgBoxName|跟踪数据大小|MessageBox 上 TrackingData 表的大小|  
|BizTalk:MessageBox:Host 计数器|PxHost:MsgBoxName|主机队列-长度|特定主机队列中的消息数|  
|BizTalk:MessageBox:Host 计数器|TxHost:MsgBoxName|主机队列-长度|特定主机队列中的消息数|  
|Biztalk: Message Agent|RxHost|数据库大小|发布 (PxHost) 队列的大小|  
|Biztalk: Message Agent|PxHost|数据库大小|发布 (TxHost) 队列的大小|  
|Biztalk: Message Agent|HostName|Message Delivery Throttling State|影响 XLANG 和出站传输|  
|Biztalk: Message Agent|HostName|消息发布阻止状态|影响 XLANG 和入站传输|  
  
### <a name="where-do-i-start"></a>如何开始？  
 监视**Message Delivery Throttling State**并**Message Publishing Throttling State**对于每个主机实例通常是启动的好时机。 如果这些计数器的值不为零，则表示 BizTalk 系统内正发生限流，并可以进一步分析瓶颈的原因。 有关其他性能计数器的说明，请参阅[标识数据库层的瓶颈](http://msdn.microsoft.com/library/f1dc58b5-73b0-41b5-9a1e-c0698485c732)。  
  
## <a name="backlog-buildup"></a>出现积压  
 对于 1-1 部署方案 1 条消息 1 个消息接收结果的位置处理和传输时，如果传出速率不等于传入速率，积压是某处累积系统中。 此类情况下就可以监视 Spool Size。  
  
 如果 Spool 呈线性增长，就可以进一步向下钻取到通过验证哪个应用程序队列导致 Spool 增长。  
  
 如果没有任何应用程序队列增长，而 Spool 持续增长，它可能意味着清除作业无法跟上由于代理未运行或在 SQL server 上的其他系统资源争用。  
  
 如果一个应用程序队列增长，则务必诊断该增长的原因。 监视无法清空特定应用程序队列的系统上的系统资源 （例如，业务流程 HOST-Q 增长由于在服务器上的 CPU 资源不足）。 除了验证特定主机实例的阻止计数器的值。  
  
 如果送达/发布状态不为零，检查该值以确认限流 （有关示例、 超过内存阈值、 正在处理的消息数过多等。） 的原因。  
  
## <a name="f1-profiler"></a>F1 Profiler  
 通过使用性能计数器，是能够快速检测瓶颈位置到较高层面。 但是，一旦范围缩小，它可能需要向下钻取进一步深入到代码以帮助缓解此问题。 使用 Visual Studio 附带 F1 Profiler 可以是非常有用的工具可帮助您诊断代码上花费其周期的大多数。  
  
 符号是重要，可帮助创建更有意义的堆栈 （特别是对于非托管代码）。 例如，F1 Profiler 可帮助查明调用数和 API 调用所返回的时间量。 钻取更多堆栈的下层，可能会能够检测到高延迟的根本原因。 它可能是对数据库查询是阻塞调用还是只需等待的事件的调用。  
  
## <a name="l2l3-cache"></a>L2/L3 缓存  
 （从硬件角度看） 可以获得最大的好处是通过利用板载 CPU 缓存。 更高 CPU 缓存可帮助增加高速缓存命中率减少系统的需求对数据传入和传出内存到磁盘进行分页。  
  
## <a name="64-bit-performance-bottlenecks"></a>64 位性能瓶颈  
 在 64 位系统上的性能可能不如 32 位系统上可以获得的内容。 这可能是由于多种原因，最重要的一个是内存。  
  
 具有 2 GB 的内存并将结果与具有 2 GB 的类似 64 位系统上可以获得的内容进行比较的 32 位系统上的测量性能不是内存的 true 的同类型比较。 64 位系统看起来是 DISK-IO 限制 （低于 %磁盘空闲时间和高磁盘队列长度） 以及 CPU 限制 （最大 CPU 和大量的上下文切换）。 但是，这是不是因为在 64 位系统上执行文件 IO 开销更大。  
  
 64 位系统需要更多内存 （64 位寻址） 这会导致操作系统占用 2 GB 可用内存的大多数。 一旦发生这种情况大部分的其他操作会导致对强调文件子系统的磁盘进行分页。 系统现在不仅花费 CPU 周期，这两个数据都分页/内存不足，并且代码但仍受影响的高磁盘延迟开销。 它表现为更多的磁盘争用和更高的 CPU 占用率。  
  
 若要缓解此问题的方法是来向上扩展服务器通过升级内存 (理想情况下为 8 GB)。 但是，添加更多的内存并无帮助提高吞吐量，除非问题的原因是由于内存不足的情况的 CPU 资源不足。  
  
## <a name="using-bam-to-identify-bottlenecks-and-high-latency-issues"></a>使用 BAM 来查找瓶颈和高延迟问题  
 在低延迟非常重要的情况下，可以使用 BAM 来测量系统完成 BizTalk 系统中的每个阶段所花费的时间。 虽然跟踪的消息事件和服务实例数据可用于调试的消息状态和诊断路由消息中的问题的根源，但 BAM 可用于跟踪的消息流的各个点。 通过创建一个 BAM 跟踪配置文件 （定义继续符的活动），可以测量系统来帮助跟踪工作流进程中成本最高的阶段的不同部件之间的延迟。