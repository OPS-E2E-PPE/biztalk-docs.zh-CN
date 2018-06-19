---
title: 使用性能分析的日志 (PAL) 工具 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d563aa7d-102d-4fe6-a892-66794feaf83b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f289cdf157100dc69feb468f789a9ebb76764a1
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "26010710"
---
# <a name="using-the-performance-analysis-of-logs-pal-tool"></a>使用日志 (PAL) 工具的性能分析
PAL （性能分析的日志） 工具读取性能监视器计数器日志 （任何已知格式） 中，并使用复杂，但已知阈值 （提供） 进行分析。 该工具生成基于 HTML 报告，以图形方式图表重要的性能计数器，并引发警报时超出阈值。 阈值最初根据阈值定义的 Microsoft 产品团队包括[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，和成员的 Microsoft 支持。 此工具不是传统的性能分析的替代，但它可自动执行的性能计数器日志足够来帮助您节省大量时间的分析。 PAL 工具中：  
  
-   分析阈值的性能计数器日志  
  
-   适用于下列大型 Perfmon 日志  
  
-   标识[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和通过分析阈值的操作系统性能计数器瓶颈  
  
-   可以扩展以对任何性能计数器进行分析  
  
-   可以用于帮助编写你自己的计数器  
  
 PAL 是可用作在免费下载[ http://go.microsoft.com/fwlink/?linkid=98098 ](http://go.microsoft.com/fwlink/?linkid=98098)。 它需要 Microsoft Log Parser。 Log Parser 是一个功能强大、 通用的工具，如事件日志、 注册表、 文件系统和活动 Windows 操作系统上提供对基于文本的数据，例如日志文件、 XML 文件，CSV 文件，以及密钥的数据源的通用查询访问权限Directory® 目录服务。 你可能想要使用此工具来查询占用大量的日志记录信息。 你可以下载的 Log Parser 工具在[ http://go.microsoft.com/fwlink/?linkid=85574 ](http://go.microsoft.com/fwlink/?linkid=85574)。  
  
## <a name="using-pal-with-performance-counter-logs-in-different-languages"></a>在不同语言中与性能计数器一起使用 PAL 日志  
 PAL 工具将分析仅在英语语言中的性能计数器日志。 若要使用其他语言中的性能计数器日志 PAL 工具，必须首先将日志传输到英语语言的转换。 你可以使用**Perfmon 日志转换器**工具，可在[ http://go.microsoft.com/fwlink/?LinkId=158802 ](http://go.microsoft.com/fwlink/?LinkId=158802)翻译为英语原始性能计数器日志文件。  
  
## <a name="understanding-the-pal-tool-report-for-microsoft-biztalk-server-2010"></a>了解 Microsoft BizTalk Server 2010 PAL 工具报告  
 PAL 工具为 Windows 操作系统的 Microsoft SQL Server 提供 Perfmon 日志分析的阈值和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 本部分介绍大部分 BizTalk Server 阈值报表中 PAL 工具分析。  
  
> [!NOTE]  
>  本主题是长，以便可以在一个位置以方便参考包含有关 PAL 工具的完整信息。  
  
 以下的分析和阈值由 PAL 工具进行报告。  
  
|分析类型和名称|分析说明|  
|----------------------------|--------------------------|  
|核心转储的磁盘： 磁盘可用空间|此分析将检查以确保要转储到磁盘的所有内存的操作系统的可用磁盘空间不足。 如果可用磁盘空间不足，然后系统将无法创建 memory.dmp，即分析内核转储的根本原因所需的文件。|  
|磁盘： 逻辑/物理磁盘接口分析|此分析中查找的每个物理磁盘的空闲时间。 越空闲磁盘已，越低从中使用该磁盘。 在逻辑磁盘中使用一个磁盘时，最好使用此计数器。 "%空闲时间"报告的示例间隔期间磁盘空闲时间百分比。<br /><br /> 参考： 排除了在磁盘密集型问题 [http://go.microsoft.com/fwlink/?linkid=50669](http://go.microsoft.com/fwlink/?linkid=50669)|  
|磁盘： 逻辑/物理磁盘读取/写入延迟分析|Windows 检测磁盘性能瓶颈的最可靠方法是通过测量其响应时间。 如果响应时间大于.025 （25 毫秒为单位），就是一个保守的阈值，然后可能发生明显减慢速度和影响用户的性能问题。 详细信息，请参阅本主题中的逻辑/物理磁盘读取/写入延迟分析到。|  
|磁盘： 逻辑磁盘传输次数/秒|"Disk Transfers/sec"是读取的速率和写入磁盘上的操作。 此分析检查以查看是否有任何逻辑磁盘的阈值展示较差的响应时间 （大于 25 秒 I/O 操作的响应时间）。 如果是这样，每秒磁盘传输应在或更高版本 80。 如果没有，则磁盘体系结构需要进行调查。 不佳的磁盘 I/O 的最常见原因是重载 SAN 上的 LUN。 有关详细信息，请参阅本主题中的逻辑 Disk Transfers/sec。|  
|磁盘： 逻辑磁盘可用空间百分比|"%可用空间"是已在所选逻辑磁盘驱动器上可用的总可用空间的百分比。 小于 30%的可用磁盘驱动器空间之前，应不会影响性能。 当使用磁盘驱动器的 70%时，剩余的可用空间位于更靠近到磁盘的主轴，在磁盘驱动器，在较低的性能级别运行的中心。 可用磁盘空间不足可能导致严重磁盘性能。<br /><br /> 参考： NT 服务器和在磁盘子系统性能 [http://go.microsoft.com/fwlink/?linkid=106783](http://go.microsoft.com/fwlink/?linkid=106783)|  
|磁盘： 处理 IO Data Operations/sec 和处理 IO 其他操作数/秒分析|这些计数器计数生成的包括文件、 网络和设备 I/o 的过程的所有 I/O 活动。 进程正在 1,000 多个我 / O 每秒的并将其标记为警告时，将检查这些分析。 这些分析最与其他分析 （如磁盘分析） 相关联时用于确定哪些进程可能会涉及到的 I/O 活动中。|  
|内存： 可用内存|此分析检查的总的可用内存是否不足 – 10%可用处出现警告和在 5%可用的关键。 下降趋势的 10 MB 的每小时检测到时，并可表示潜在的即将到来的内存不足情况，警告也会得到通知。 物理内存不足可能导致增加特权模式下 CPU 和系统延迟。 详细信息，请参阅本主题中的可用 MemoryAnalysis 到。|  
|内存： 可用系统页表项|可用系统页表项 (PTE) 是当前未使用的系统页表条目数。 此分析将决定是否系统用完 PTE 的通过检查是否有少于 5000 免费 PTE 的伴有警告是否少于 10,000 免费 PTE 的。 缺乏足够 PTE 可能会导致系统范围内挂起。 此外请注意，3 GB 切换将大幅降低免费 PTE 的量。 详细信息，请参阅本主题中的可用系统页表条目分析。|  
|内存： 内存泄漏检测|此分析将决定是否任何进程正在消耗大量的系统的内存，且是否在内存消耗，随着时间的推移增加过程。 使用大量的内存的进程没什么，只要该过程将返回到系统内存。 查找增加图表的趋势。 上升趋势长的一段时间内无法指示内存泄漏。 "Private Bytes"是内存的当前大小 （字节），此进程已分配不能与其他进程共享。 此分析检查 10 MB 的每小时和 5 MB 的每小时增加趋势。 与 PAL 中的可用内存分析相关联时使用此分析。 详细信息，请参阅本主题中的内存泄漏检测分析到。|  
|内存： 句柄泄漏检测|此分析检查的所有进程以确定多少处理每个已打开，以确定是否可以句柄泄漏怀疑不当。 具有大量的句柄和/或主动上升趋势的进程可能表示句柄泄漏，这通常会导致内存泄漏。 此进程当前打开的句柄的总数等于此进程中的每个线程当前打开的句柄总数。<br /><br /> 参考： 调试诊断工具在的 1.1 版 [http://go.microsoft.com/fwlink/?linkid=106784](http://go.microsoft.com/fwlink/?linkid=106784)|  
|内存： 内存 Pages Input/sec|"页 Input/sec"是从磁盘为解决强制分页错误读取页的速率。 如果进程引用不在其工作集或其他位置在物理内存中，并且必须从磁盘检索的虚拟内存中的页，将发生硬页面错误。 此分析将检查是否有 10 个以上页文件的读取次数 / 秒。|  
|Memory: Memory Pages/sec|此分析检查"页/秒"是否为高 （超过 1,000 个）。 如果高，然后系统可能内存不足尝试进行分页到磁盘的内存。 "页/秒"是从读取或写入磁盘为解决强制分页错误页的速率。 此计数器是导致系统范围延迟的错误种类的主要指示器。  可用内存分析和 PAL 中的内存泄漏检测分析与相关联时使用此分析。 如果所有这些分析在同一时间引发警报，，这可能表示系统内存不足和可疑的进程涉及和执行分析 PAL 中的内存泄漏检测分析中所述的步骤。<br /><br /> 有关详细信息，请参阅本主题中的内存页/秒分析。|  
|内存： 内存系统缓存驻留字节数|"系统缓存驻留字节数"是的大小，以字节为单位，在文件系统缓存中的可分页操作系统代码。 此值只包括当前物理页面，并且不包括任何当前未驻留的虚拟内存页面。 此值是一个组件的"内存\\\System 代码驻留字节数"表示所有当前正在物理内存的可分页操作系统代码。 此计数器显示上次观测的值仅;它不是平均值。 此分析检查上升趋势的 10 MB 的每小时。 承受负载时，服务器可能使用的系统缓存，以便缓存如磁盘 I/O 活动。 将相关联时使用与过程 IO Data Operations/sec 和进程 IO 其他操作数/秒 PAL 中的分析。<br /><br /> 参考： 文件缓存性能和优化在 [http://go.microsoft.com/fwlink/?linkid=106786](http://go.microsoft.com/fwlink/?linkid=106786)|  
|内存： 池非分页字节数|"池非分页字节数"是的大小，以字节为单位，无法写入到的对象的系统内存区域的非分页池的磁盘、 但一旦分配就必须保留在物理内存中。 此分析将检查以查看是否系统即将接近最大池非分页内存大小。 这是通过估计考虑到的池大小/3 GB、 物理内存大小和 32 位/64 位，然后确定的值是否高于 60%的估计的池大小。 如果系统变得接近最大大小时，然后系统可能会遇到系统宽挂起。<br /><br /> Boot.ini 文件中的 3 GB 交换机选项大大降低了此内存池的大小。<br /><br /> 详细信息，请参阅本主题中的 Pool Non-Paged 字节分析。|  
|内存： 池分页字节数|此分析将检查以查看是否系统即将接近最大池分页内存大小。 这是通过估计考虑到的池大小/3 GB、 物理内存大小和 32 位/64 位，然后确定的值是否高于 60%的估计的池大小。 如果系统变得接近最大大小时，然后系统可能会遇到系统宽挂起。<br /><br /> Boot.ini 文件中的 3 GB 交换机选项大大降低了此内存池的大小。<br /><br /> 详细信息，请参阅本主题中的池分页字节分析。|  
|内存： 进程线程计数|此分析检查的所有进程来确定进程是否具有 500 多个线程，且由每小时 50 线程如果增加线程数。 具有大量的线程和/或主动上升趋势的进程无法指示线程泄漏这通常会导致内存泄漏或高上下文切换。 高上下文切换将导致高特权模式下 CPU。|  
|内存： 进程工作集|"工作集"是当前大小 （字节），此过程的工作集。 工作集是的进程中的线程最近使用过的内存页的集合。 如果计算机中的可用内存高于阈值，页会保留在某一进程工作集，即使它们未被使用。 如果可用内存降到阈值以下，将从工作集中削减页。 如果需要它们将会软恢复到的工作集在离开主内存之前。 此分析检查的 10 MB 上升趋势达到或超过每个进程。 PAL 中的可用内存分析的使用相关联时使用。<br /><br /> 参考： 检测在内存瓶颈 [http://go.microsoft.com/fwlink/?linkid=106787](http://go.microsoft.com/fwlink/?linkid=106787)|  
|网络： 网络输出队列长度分析|此分析检查多少线程在等待网络适配器。 如果多个线程在等待上的网络适配器，然后系统可能占满网络 I/O 由于网络滞后或网络带宽。 "Output Queue Length"是 （以数据包） 的输出数据包队列的长度。 指示延迟如果这是长度大于 2，和瓶颈应找出并消除，如有可能。 网络输出队列的典型原因包括大量的小型网络请求和网络延迟。|  
|网络： 网络使用率分析|"Bytes Total/sec"是发送和接收每个网络适配器，包括组帧字符字节的速率。 "Network Interface\Bytes Received/sec"是"Network Interface\Bytes Received/sec"和"Network Interface\Bytes Sent/sec"的和。 此计数器可帮助你知道在你的网络适配器的流量是否已饱和以及是否需要添加另一个网络适配器。 可以确定问题的速度取决于类型的网络必须以及是否与其他应用程序共享带宽。 此分析将"Bytes Total/sec"转换为位，并将它与计算网络利用率的网络适配器的当前带宽进行比较。 接下来，它会检查 50%以上的使用率。<br /><br /> 参考： 测量在.NET 应用程序性能 [http://go.microsoft.com/fwlink/?linkid=106788](http://go.microsoft.com/fwlink/?linkid=106788)|  
|分页文件： 分页文件使用率 %和 %使用高峰|在 %中使用的页文件实例的量。 另请参阅"过程\\\Page 文件字节数"。 此分析检查是否大于 70%的使用率的百分比。|  
|处理器： 处理器使用率分析和进程的过多的处理器使用率|此计数器是处理器活动的主要指示器，并显示在采样间隔期间观察到的忙碌时间的平均百分比。 它被通过监视服务处于非活动状态的时间，然后从 100%减去该值。 此分析检查大于每个处理器上的 60%的利用率。 如果是这样，确定它是否是高用户模式 CPU 或高特权模式。 如果高特权模式下 CPU 怀疑有问题，请参阅 PAL 中的特权模式 CPU 分析。 如果怀疑用户模式下处理器瓶颈，则可以考虑使用进程探查器分析导致高 CPU 使用的函数。|  
|处理器： 处理器队列长度|此分析将决定是否平均处理器队列长度超过处理器的数目。 如果是这样，则这可能表示处理器瓶颈。 通过 PAL 中的过程分析特权模式 CPU 分析和过多的处理器使用的相关中使用此分析。 详细信息，请参阅本主题中的处理器队列长度分析。|  
|处理器： 特权模式下 CPU 分析|此计数器指示在特权模式下运行的线程的时间的百分比。 当你的应用程序调用时 （例如，可执行文件或网络 I/O 或分配内存） 的操作系统功能时，这些操作系统功能在特权模式下执行。 此分析将检查以查看特权模式下 CPU 是否占用了超过 30%的总 CPU。 如果这样，则可能的 CPU 消耗是才导致的网络、 内存或磁盘 I/O 等处理器以外的另一个瓶颈。 与处理器相关联时使用: %Interrupt Time 和处理器： PAL 中的高上下文切换分析。 详细信息，请参阅本主题中的特权模式 CPU 分析。|  
|处理器： 中断时间|"%中断时间"是处理器用于接收和服务硬件中断采样间隔期间的时间。 此值是活动的生成中断，例如系统时钟、 鼠标、 磁盘驱动程序、 数据通讯线路、 网络接口卡和其他外围设备的设备的间接指示器。 这些设备通常会中断处理器，在已经完成了任务或需要关注时。 中断期间是暂挂正常线程执行。 大多数系统时钟每隔 10 毫秒，创建中断活动的背景就会中断处理器。 大幅度提高此计数器指示潜在硬件问题。 此分析检查"%中断时间"大于 30%。 如果发生这种情况，请考虑更新与此警报关联的硬件的设备驱动程序。<br /><br /> 参考： 测量在.NET 应用程序性能 [http://go.microsoft.com/fwlink/?linkid=106788](http://go.microsoft.com/fwlink/?linkid=106788)|  
|处理器： 高上下文切换|较高优先级的线程会抢占较低的优先级线程当前正在运行或高优先级的线程块时，会发生情况的上下文切换。 当多个线程共享相同的优先级级别，则会发生的上下文切换的高级别。 这通常指示线程过多在争夺系统上的处理器。 一般情况下，上下文切换速率小于每个处理器每秒 5,000 的不是值得担心。 如果上下文切换率超过每个处理器每秒的 15000，则一个约束。 详细信息，请参阅本主题中的高上下文切换分析。|  
|冻结过程中业务流程的 Microsof BizTalk Server: BizTalk|当同时运行多长时间运行的业务流程时，可能会出现内存和性能问题。 业务流程引擎通过“冻结”和“解除冻结”业务流程实例来解决这些问题。 冻结是将业务流程的状态序列化到 SQL Server 数据库中的过程。 Rehydration 是此过程的反向︰ 反序列化从数据库的业务流程的上次运行状态。 冻结用于通过减少必须在内存中同时实例化的业务流程数来最大程度地降低系统资源的使用。 因此，dehyrations 节省内存消耗，但代价相对较大要执行的操作。 此分析检查 dehydrations 10 或更多。 如果是这样，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可能内存不足 （虚拟或物理），较高的业务流程数在等待消息，或未正确设置冻结设置。<br /><br /> 参考： Orchestration 冻结和在 Rehydration  [http://go.microsoft.com/fwlink/?LinkId=155284](http://go.microsoft.com/fwlink/?LinkId=155284)|  
|Microsoft BizTalk Server: BizTalk 高数据库会话|此计数器都有两个可能值： 正常 (0) 或超出了阈值 (1)。 此分析检查的值为 1。 如果是这样，BizTalk 超过了允许的数据库会话数的阈值。 此值由 BizTalk 主机限制设置中的"每个 CPU 的数据库连接"值控制。 "数据库连接每个 CPU"是最大并发数据库会话数 （每个 CPU) 限制开始之前允许。 通过使用 BizTalk:Message Agent 性能对象类别下的 Database session 性能计数器，可以监视活动数据库连接数。 此参数只影响出站消息阻止功能。 有关详细信息，请参考 BizTalk 高数据库会话分析中本主题。|  
|Microsoft BizTalk Server: BizTalk 高数据库大小|为数据库阈值中的消息计数列出的条件之一时，此计数器将设置为值为 1。 默认情况下，主机消息限制阈值的数据库中的计数设置为值为 50000，就会触发在下列情况下的限制条件：<br /><br /> 的发布到工作、 状态和挂起的队列的订阅的主机的主机实例的消息总数超过了 50000。<br />-假脱机表或跟踪表中的消息的数量超过 500,000 消息。<br /><br /> 如果发生这种情况，请考虑将减少在数据库中的消息数的操作过程。 例如，确保中的 SQL Server 作业[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]正在正常运行并使用中的组中心数据库页面[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，以确定是否将消息生成向上引起的大量的挂起的消息。 有关详细信息，请参考 BizTalk 高数据库大小分析中本主题。|  
|Microsoft BizTalk Server: BizTalk 高进程内消息计数|此分析检查的进程内消息计数高计数器以确定是否发生这种类型的限制。 如果是这样，请考虑调整"每 CPU 邮件进程内"设置。 此参数只影响出站消息阻止功能。 在禁用限制基于每个 CPU 进程内消息数"进程内消息每个 CPU"设置中输入的值为 0。 "进程内消息每个 CPU"设置的默认值为 1000。 请注意，修改此值还可以影响在低延迟的消息和/或 BizTalk 资源的效率。 详细信息，请参阅本主题中的 BizTalk 高进程内消息计数分析。|  
|Microsoft BizTalk Server: BizTalk 高消息传送速率|此分析检查的值为 1 中的高的消息传送速率计数器。 高的消息传送速率可能引起高处理复杂性、 慢速的出站适配器或暂时的系统资源不足。 详细信息，请参阅本主题中的 BizTalk 高消息传送速率分析。|  
|Microsoft BizTalk Server: BizTalk 高消息发布速率|限制，也称为消息发布限制中的入站的主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，应用于包含的主机实例接收适配器或将消息发布到 MessageBox 数据库的业务流程。 此分析检查的值为 1 中发布的高消息速率计数器。 如果发生这种情况，然后数据库无法跟上的消息的发布速率到 BizTalk MessageBox 数据库。<br /><br /> 引用：<br /><br /> -主机限制的性能计数器，在 [http://go.microsoft.com/fwlink/?LinkId=155285](http://go.microsoft.com/fwlink/?LinkId=155285)<br />-如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]实现在限制的主机 [http://go.microsoft.com/fwlink/?LinkId=155286](http://go.microsoft.com/fwlink/?LinkId=155286)<br />消息发布限制在的设置对话框 [http://go.microsoft.com/fwlink/?LinkId=155287](http://go.microsoft.com/fwlink/?LinkId=155287)<br />-什么是主机限制？在 [http://go.microsoft.com/fwlink/?LinkID=154694](http://go.microsoft.com/fwlink/?LinkID=154694)|  
|Microsoft BizTalk Server: BizTalk 高进程内存|限制阈值设置的 BizTalk 进程内存使用量是内存的相比工作集大小和进程的总可用虚拟内存的总和，如果输入从 1 到 100 之间的值所使用百分比。 在指定百分比值时，将按固定的时间间隔来重新计算进程内存阈值。 此分析检查 1 中的高进程内存计数器的值。 详细信息，请参阅本主题中的到 BizTalk 高进程内存分析。|  
|Microsoft BizTalk Server: BizTalk 高系统内存|BizTalk 物理内存使用情况限制阈值设置为输入相比从 1 到 100 之间的可用物理内存的值如果总量的内存消耗的百分比。 如果输入大于 100 的值，此设置也可以在兆字节为单位的可用物理内存的总量。 输入值 0 可以禁用基于物理内存使用率的阻止功能。 默认值为 0。 详细信息，请参阅本主题中的到 BizTalk 高的系统内存分析。|  
|Microsoft BizTalk Server: BizTalk 高线程计数|"每个 CPU 线程数"是宿主进程包括由适配器使用的线程中的线程总数。 如果超出此阈值，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将尝试减小 EPM 线程池和消息代理线程池的大小。 如果高负载可能导致创建大量线程，则在这种情况下，应启用基于线程的阻止功能。 此参数同时影响入站和出站阻止功能。 默认情况下，禁用基于线程限制。 详细信息，请参阅本主题中的 BizTalk 高线程计数分析。|  
|Microsoft BizTalk Server: BizTalk 主机队列长度|BizTalk 主机队列长度跟踪特定主机队列中的邮件总数。 可以使用长度大小 （即，BizTalk:MessageBox:HostCounters:Host 队列 – 长度） 来提供更详细的视图的正在排队内部通过显示各个主机的队列深度的消息数。 此计数器可确定是否遇到瓶颈特定主机。 假定唯一主机使用的每个传输协议，这可以帮助确定潜在传输瓶颈。 此分析检查平均队列长度大于 1。 目标主机上的情况下，主机队列长度是通过聚合所有队列 (工作 Q，状态 Q 挂起 Q) 的记录计数的加权的队列长度。<br /><br /> 参考： BizTalk Server 2006： 管理在一个成功性能实验室[ http://go.microsoft.com/fwlink/?linkid=104152 ](http://go.microsoft.com/fwlink/?linkid=104152) **注意：** 这份白皮书也是适用于 BizTalk Server。|  
|Microsoft BizTalk Server: BizTalk 主机挂起消息队列长度|此计数器跟踪特定主机的挂起的消息总数。 将挂起的消息是消息或业务流程的一个实例，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]已停止处理因出错而系统或消息中。 通常，根据系统问题的解决办法，由系统错误导致的挂起实例是可恢复的。 通常情况下，由于消息问题而挂起的实例不是可恢复，并且必须修复和重新提交到消息本身[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。<br /><br /> 挂起的消息队列是一个包含工作项，为其错误或失败期间遇到处理的队列。 挂起队列将一直存储这些消息，直到它们被纠正、重新处理或被删除。 此分析检查挂起的任何的消息匹配项。 上升趋势可能表示严重处理错误。<br /><br /> 参考： BizTalk Server 2004： 监视和在故障排除 [http://go.microsoft.com/fwlink/?linkid=108771](http://go.microsoft.com/fwlink/?linkid=108771)|  
|BizTalk Server: BizTalk 空闲业务流程|当前以主机实例为宿主的空闲业务流程实例的数量。 此计数器是指业务流程，不需要进度但不是可冻结。 业务流程被阻止时，发生这种情况，可以等待接收，侦听或原子事务的延迟时间。 如果大量的非可冻结业务流程会累积，BizTalk 可能用尽内存。<br /><br /> 冻结是将业务流程的状态序列化到 SQL Server 数据库中的过程。 Rehydration 是此过程的反向︰ 反序列化从数据库的业务流程的上次运行状态。 冻结用于通过减少必须在内存中同时实例化的业务流程数来最大程度地降低系统资源的使用。 引擎 dehydrates 实例的保存状态，并释放的实例所需的内存。 通过冻结休眠业务流程实例过程中，引擎使大量的长时间运行业务流程，以同时在同一台计算机上运行。 此分析检查每小时一个空闲的业务流程的上升趋势。<br /><br /> 参考： Orchestration 冻结和在 Rehydration  [http://go.microsoft.com/fwlink/?LinkId=155284](http://go.microsoft.com/fwlink/?LinkId=155284)|  
|BizTalk Server： 入站 BizTalk 延迟|平均延迟消息引擎文档从接收适配器之前发布到 MessageBox 的时间 （毫秒）。 减少延迟是重要的 BizTalk，某些用户因此跟踪时间文档在入站适配器中的花费多少是很重要。 详细信息，请参阅本主题中的 BizTalk 入站延迟分析。|  
|BizTalk Server: BizTalk 消息传递延迟|这是对每个消息传递批处理 （如果要中止消息传递时适用） 的当前延迟以毫秒 (ms) 为单位。 有关限制，延迟应用中发布或处理消息，具体取决于消息是入站或出站。 延迟期成正比的重要程度限制条件。 限制条件的更高严重性将启动比限制条件的低严重性再限制期。 随着阻止条件的变化，将根据阻止机制在特定范围内延长和缩短此延迟时间。 通过消息传递的延迟 (ms) 和消息发布与 BizTalk:Message 代理性能对象类别关联的延迟 (ms) 性能计数器公开当前延迟期。 此分析检查消息传递延迟大于 5 秒。 长消息传递延迟可能表示由于高负载而进行大量控制。<br /><br /> 参考： 如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]实现在限制的主机 [http://go.microsoft.com/fwlink/?LinkId=155286](http://go.microsoft.com/fwlink/?LinkId=155286)|  
|BizTalk Server: BizTalk 消息传递限制状态|BizTalk 消息传递限制状态是之一的限制的主要指示器。 它是一个标志，指示系统是否限制 （影响 XLANG 消息处理和出站传输协议） 的消息传递。 由计数器的数值表示限制条件。 有关详细信息，请参阅本主题中的 BizTalk 消息传递限制状态分析。|  
|BizTalk Server: BizTalk 消息发布延迟|有关限制的消息发布每个符合条件批次中插入的延迟时间。 有关限制，延迟应用中发布或处理消息，具体取决于消息是入站或出站。 延迟期成正比的重要程度限制条件。 限制条件的更高严重性将启动比限制条件的低严重性再限制期。 随着阻止条件的变化，将根据阻止机制在特定范围内延长和缩短此延迟时间。 通过消息传递的延迟 (ms) 和消息发布与 BizTalk:Message 代理性能对象类别关联的延迟 (ms) 性能计数器公开当前延迟期。 此分析将检查发布的大于 5 秒的延迟的消息。 长消息传递延迟可能表示由于高负载而进行大量控制。<br /><br /> 参考： 如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]实现在限制的主机 [http://go.microsoft.com/fwlink/?LinkId=155286](http://go.microsoft.com/fwlink/?LinkId=155286)|  
|BizTalk Server: BizTalk MessageBox 数据库连接失败|此性能计数器是自主机实例启动以来失败的尝试的数据库连接数。 如果出于任何原因，SQL Server 服务承载 BizTalk 数据库将变得不可用，数据库群集会将资源从活动的计算机传输到被动的计算机。 在此故障转移过程中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务实例遇到数据库连接失败，并自动重新启动以重新连接到数据库。 采用故障转移期间传输的资源后，正在运行的数据库计算机（即前面提到的被动计算机）将开始处理数据库连接。 详细信息，请参阅本主题中的到 BizTalk MessageBox 数据库连接故障分析。|  
|BizTalk Server: BizTalk 延迟消息传送： 请求响应延迟时间|自消息引擎从适配器接收到请求文档到将响应文档返回到适配器的平均延迟时间（以毫秒计）。 请参阅显示延迟本主题中的测量 BizTalk 入站延迟分析图表。 此分析假设低延迟环境，检查请求响应延迟大于 5 秒。 这可能表示入站的适配器和出站适配器之间的处理延迟。<br /><br /> 引用：<br /><br /> -请求/响应消息传递在 [http://go.microsoft.com/fwlink/?LinkId=155288](http://go.microsoft.com/fwlink/?LinkId=155288)<br />-BizTalk Server 2006： 在 BizTalk Server 2006 在中使用的 SOAP 适配器的可伸缩性案例研究 [http://go.microsoft.com/fwlink/?linkid=108774](http://go.microsoft.com/fwlink/?linkid=108774)|  
|BizTalk Server: BizTalk 消息传送发布限制状态|发布限制状态 BizTalk 消息是一个限制的主要指示器。 它是一个标志，指示系统是否限制 （影响 XLANG 消息处理和入站传输协议） 的消息发布。 详细信息，请参阅本主题中的 BizTalk 消息传送发布限制状态分析。|  
|BizTalk Server: BizTalk 业务流程已挂起/秒|将挂起的消息是消息或业务流程的一个实例，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]已停止处理因出错而系统或消息中。 通常，根据系统问题的解决办法，由系统错误导致的挂起实例是可恢复的。 通常情况下，由于消息问题而挂起的实例不是可恢复，并且必须修复和重新提交到消息本身[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。 此分析检查任何挂起消息/业务流程。<br /><br /> 参考： BizTalk Server 2004： 监视和在故障排除 [http://go.microsoft.com/fwlink/?linkid=108771](http://go.microsoft.com/fwlink/?linkid=108771)|  
|BizTalk Server: BizTalk 业务流程已完成/秒|这是已完成的 BizTalk 业务流程数每秒。 这是处理 BizTalk 多少吞吐量很好的指示器。 此分析提供仅限统计信息。<br /><br /> 参考： BizTalk Server 2006： 在 BizTalk Server 2006 中使用的 SOAP 适配器的可伸缩性案例研究 <br />[http://go.microsoft.com/fwlink/?linkid=108774](http://go.microsoft.com/fwlink/?linkid=108774)|  
|BizTalk Server: BizTalk 业务流程丢弃|自从主机实例启动以来，内存中被丢弃的业务流程实例的数量。 如果引擎未能持久化某个业务流程的状态，则会将其丢弃。 此分析将检查有任何丢弃消息。<br /><br /> 参考： BizTalk 核心引擎博客<br />[http://go.microsoft.com/fwlink/?linkid=108775](http://go.microsoft.com/fwlink/?linkid=108775)|  
|BizTalk Server: BizTalk 业务流程驻留在内存中|当前以主机实例为宿主的业务流程实例的数量。 此分析检查在驻留在内存和是否超过 50%的驻留在内存中的业务流程不是可冻结业务流程中上升趋势。 有关详细信息，请参阅 BizTalk 业务流程驻留在内存分析。|  
|BizTalk Server: BizTalk 出站适配器延迟|这是从当适配器文档从获取消息的引擎适配器发送的时间之前的秒数的平均延迟。 请参阅显示延迟本主题中的测量 BizTalk 入站延迟分析图表。 假设低延迟环境，这种分析检查延迟大于 5 秒的出站适配器中的平均值。 这可能表示通过此主机实例中的出站适配器的消息传输的处理延迟。 如果此主机实例中存在多个出站适配器，请考虑将它们分散到其自己的主机，以确定哪个出站的适配器的高延迟。<br /><br /> 引用：<br /><br /> -请求/响应消息传递在 [http://go.microsoft.com/fwlink/?LinkId=155288](http://go.microsoft.com/fwlink/?LinkId=155288)<br />-BizTalk Server 2006： 在 BizTalk Server 2006 在中使用的 SOAP 适配器的可伸缩性案例研究 [http://go.microsoft.com/fwlink/?linkid=108774](http://go.microsoft.com/fwlink/?linkid=108774)<br />的在 BizTalk 层中发现瓶颈 [http://go.microsoft.com/fwlink/?LinkId=155289](http://go.microsoft.com/fwlink/?LinkId=155289)<br />-BizTalk Server 2004： 性能优化的低延迟的消息传送在 [http://go.microsoft.com/fwlink/?linkid=108777](http://go.microsoft.com/fwlink/?linkid=108777)|  
|BizTalk Server: BizTalk 挂起消息|接收到 MessageBox 接收到未被确认的消息数。 挂起的消息的消息，已拉入内存传递到 XLANG 业务流程，但尚未被处理。 没有任何这种情况下如何处理数据丢失。  将一条消息传送到业务流程是一个多步骤过程，只需驻留在数据库中的假脱机表中的消息的实例。 这些挂起消息计数为处理这些消息;因此，具有大量它们在内存中，这种情况可能会导致内存限制系统上。 调整的内部消息队列大小设置无法帮助控制的挂起消息数。 每个 CPU 进程内消息设置产生影响限制将时调用了大量的挂起消息发生时。 这些设置位于 BizTalk 管理控制台中的主机属性。 此分析检查此计数器仅显示统计。<br /><br /> 在参考： 业务流程引擎性能计数器 [http://go.microsoft.com/fwlink/?LinkId=155290](http://go.microsoft.com/fwlink/?LinkId=155290)|  
|BizTalk Server: BizTalk 持久性点/秒|平均每秒持久化业务流程实例的次数。 业务流程引擎保存在不同的时间点正在运行的业务流程实例的状态。 如果它需要 rehydrate 业务流程实例、 从受控关机，启动或从意外关闭恢复，它将从最后一个持久点运行业务流程实例。 才能持久地保存业务流程实例，所有对象直接或间接指您的业务流程的实例 （通过其他对象一样） 必须是可序列化。 随着消息持久性频率 （需要持久保留数据的时间数） 将增加，总体性能下降。 实际上，每个持久性点是到数据库的往返行程，因此只要有可能减少通过避免或整合持久性点的持久性点的频率。 请参阅下面有关持久性点发生时的详细信息的引用。 此分析检查以 10 个以上持久性点每秒平均。 这是一个常规的起始点。<br /><br /> 引用：<br /><br /> 的在业务流程中持久性 [http://go.microsoft.com/fwlink/?LinkId=155291](http://go.microsoft.com/fwlink/?LinkId=155291)<br />-持久性和在业务流程引擎 [http://go.microsoft.com/fwlink/?LinkId=155292](http://go.microsoft.com/fwlink/?LinkId=155292)|  
|BizTalk Server: BizTalk 专用字节数|这是分配的专用内存的主机实例和类似于"\Process （*） \Private 字节数"性能计数器的兆字节。 此分析将决定是否任何主机实例消耗的系统内存的大小，并在主机实例是否在内存消耗，随着时间的推移增加。 有关详细信息的本主题中，请参阅 BizTalk 专用字节分析。|  
|BizTalk Server: BizTalk 假脱机表大小|MessageBox 假脱机表包含在系统中的每个消息的记录 (活动或者正等着进行"垃圾回收")。 监视此表中的行数和系统负载增加可以轻松地查找最大可持续吞吐量时，每秒接收的消息数。 只需增加输入的负载，直至任一 1） 假脱机表开始无限增加或 2） 的每个第二个 plateaus、 准，并且该父级是最大可持续吞吐量接收的消息数。 总起来说，而不考虑其他指示符，此度量值将为你提供快速轻松地以评估是否或不在输出过度你的系统。 如果 BizTalk 假脱机表大小为 on 上升趋势，然后限制由于失衡的消息传送速率 （输入的率超过输出率） 或者由于数据库大小限制可能会发生。 此分析检查上升趋势 BizTalk 假脱机表大小。<br /><br /> 引用：<br /><br /> -了解 BizTalk Server 2004 SP1 吞吐量和容量 [http://go.microsoft.com/fwlink/?linkid=108781](http://go.microsoft.com/fwlink/?linkid=108781)<br />-在可持续的负载测试 [http://go.microsoft.com/fwlink/?LinkId=155293](http://go.microsoft.com/fwlink/?LinkId=155293)<br />-建议在测试时引擎的性能 [http://go.microsoft.com/fwlink/?LinkID=155294](http://go.microsoft.com/fwlink/?LinkID=155294)|  
|BizTalk Server: BizTalk 跟踪数据的大小|BizTalk Server 处理越来越多的数据，你的系统上，BizTalk 跟踪数据库 (BizTalkDTADb) 就会继续增大。 不受控制的增长将会降低系统性能，并可能导致跟踪数据传送服务 (TDDS) 出错。 除了一般的跟踪数据之外，跟踪的消息也会在 MessageBox 数据库中累积，导致磁盘性能下降。 此分析检查上升趋势超过 5 MB 的每小时跟踪中的数据大小。<br /><br /> 参考：<br /><br /> 存档和清除跟踪数据库在 BizTalk  [http://go.microsoft.com/fwlink/?LinkID=153816](http://go.microsoft.com/fwlink/?LinkID=153816)|  
|BizTalk Server: BizTalk 事务作用域已中止|这是自主机实例启动后已中止的长时间运行或原子作用域数。 事务范围中止是发生在事务范围内业务流程失败。 请务必了解，都会调用作用域的补偿处理程序，仅当作用域已成功完成，但然后必须是撤消，因为确定周边范围 （由于更高版本中的过程可能会发生的故障） 而中止。 此外，如果事务中止发生的状态没有"自动"回滚。 你可以实现这一目的以编程方式通过异常和补偿处理程序。 事务范围中止不应该通常发生在生产环境中;因此，此分析将检查任何中止的事务作用域的匹配项。<br /><br /> 参考：<br /><br /> 在 BizTalk Server 2004 跨事务 [http://go.microsoft.com/fwlink/?linkid=108784](http://go.microsoft.com/fwlink/?linkid=108784)|  
|BizTalk Server: BizTalk 事务作用域补偿|补偿可视为已成功提交到的某些错误条件的响应中的工作的逻辑撤消。 请务必了解，都会调用作用域的补偿处理程序，仅当作用域已成功完成，但然后必须是撤消，因为确定周边范围 （由于更高版本中的过程可能会发生的故障） 而中止。 此外，如果事务中止发生的状态没有"自动"回滚。 这种回滚可以通过编写异常处理程序和补偿处理程序来实现。 事务范围补偿不应该通常发生在生产环境中;因此，此分析将检查任何中止的事务作用域的匹配项。<br /><br /> 在 BizTalk Server 2004 跨的引用： 事务 [http://go.microsoft.com/fwlink/?linkid=108784](http://go.microsoft.com/fwlink/?linkid=108784)|  
|BizTalk Server: BizTalk 虚拟字节|这是适用于主机实例的虚拟内存保留的兆字节。 此分析将决定是否任何主机实例正在消耗大量的系统内存，且是否随时间推移的内存消耗中增加的主机实例。 详细信息，请参阅本主题中的 BizTalk 虚拟字节分析。|  
|BizTalk Server: BizTalk 消息代理数据库会话限制|这是到 MessageBox 相比限制设置其各自 BizTalk 打开数据库连接数。 "数据库连接每个 CPU"是最大并发数据库会话数 （每个 CPU) 限制开始之前允许。 详细信息，请参阅本主题中的为 BizTalk 消息代理数据库会话限制分析。|  
|BizTalk Server: BizTalk 消息代理数据库会话限制阈值|这是到 MessageBox 的打开的数据库连接数的当前阈值。 "数据库连接每个 CPU"是最大并发数据库会话数 （每个 CPU) 限制开始之前允许。 详细信息，请参阅本主题中的为 BizTalk 消息代理数据库会话限制阈值分析。|  
|BizTalk Server: BizTalk 消息代理进程内消息计数限制|这是处理服务类的并发消息数。 在主机限制设置的"进程内消息每个 CPU"设置是最大的未处理的消息传递到的终结点管理器 (EPM) 或 XLANG 数。 有关详细信息，请参阅本主题中的 BizTalk 消息代理进程内消息计数限制分析。|  
|BizTalk Server: BizTalk 消息代理进程内消息计数限制阈值|这是处理服务类的并发消息数的当前阈值。 在主机限制设置的"进程内消息每个 CPU"设置是最大的未处理的消息传递到的终结点管理器 (EPM) 或 XLANG 数。 有关详细信息，请参阅 BizTalk 消息代理进程内消息计数限制阈值分析本主题中。|  
|BizTalk Server: BizTalk 消息代理进程内存使用率 (MB) 限制|这是当前进程 (MB) 的内存使用率。 BizTalk 进程内存限制可能要发布的批有陡峭的内存需求，或如果线程过多所处理的消息时发生。 有关详细信息，请参阅本主题中的 BizTalk 消息代理进程内存使用率 (MB) 限制分析。|  
|限制阈值的 BizTalk Server: BizTalk 消息代理进程内存使用率 (MB)|这是当前进程 (MB) 的内存使用量的当前阈值。 可能根据实际的此过程，并且其内存消耗模式的可用内存量动态调整阈值。 BizTalk 进程内存限制可能要发布的批有陡峭的内存需求，或如果线程过多所处理的消息时发生。 有关详细信息，请参阅 BizTalk 消息代理进程内存使用率 (MB) 限制阈值分析本主题中。|  
|BizTalk Server: BizTalk 消息代理线程计数限制|BizTalk 进程中线程的总数。 "每个 CPU 线程数"是宿主进程包括由适配器使用的线程中的线程总数。 如果超过此阈值，则 BizTalk Server 将尝试减小 EPM 线程池和消息代理线程池的大小。 如果高负载可能导致创建大量线程，则在这种情况下，应启用基于线程的阻止功能。 此参数同时影响入站和出站阻止功能。 默认情况下，禁用基于线程限制。 此分析将检查是否 BizTalk 线程计数大于 80%的限制阈值的值，该值指示可能的限制条件。<br /><br /> 引用：<br /><br /> -主机限制的性能计数器，在 [http://go.microsoft.com/fwlink/?LinkId=155285](http://go.microsoft.com/fwlink/?LinkId=155285)<br />-如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]实现在限制的主机 [http://go.microsoft.com/fwlink/?LinkId=155286](http://go.microsoft.com/fwlink/?LinkId=155286)<br />-如何修改限制在设置的默认主机 [http://go.microsoft.com/fwlink/?LinkId=155296](http://go.microsoft.com/fwlink/?LinkId=155296)<br />会影响适配器的性能的配置参数 [http://go.microsoft.com/fwlink/?LinkID=154200](http://go.microsoft.com/fwlink/?LinkID=154200)<br />-线程，数据库会话和限制在 [http://go.microsoft.com/fwlink/?linkid=106793](http://go.microsoft.com/fwlink/?linkid=106793)|  
|BizTalk Server: BizTalk 消息代理线程计数限制阈值|这是当前进程中的线程的总数的阈值。 "每个 CPU 线程数"是宿主进程包括由适配器使用的线程中的线程总数。 如果超过此阈值，则 BizTalk Server 将尝试减小 EPM 线程池和消息代理线程池的大小。 在高负载可能导致大量的线程创建的情况下，应启用基于线程的限制。 此参数同时影响入站和出站阻止功能。<br /><br /> 此分析检查是否将此限制设置设置为非默认值。 默认情况下，禁用基于线程限制。<br /><br /> 引用：<br /><br /> -主机限制的性能计数器，在 [http://go.microsoft.com/fwlink/?LinkId=155285](http://go.microsoft.com/fwlink/?LinkId=155285)<br />-如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]实现在限制的主机 [http://go.microsoft.com/fwlink/?LinkId=155286](http://go.microsoft.com/fwlink/?LinkId=155286)<br />-如何修改限制在设置的默认主机 [http://go.microsoft.com/fwlink/?LinkId=155296](http://go.microsoft.com/fwlink/?LinkId=155296)<br />会影响适配器的性能的配置参数 [http://go.microsoft.com/fwlink/?LinkID=154200](http://go.microsoft.com/fwlink/?LinkID=154200)<br />-线程，数据库会话和限制在 [http://go.microsoft.com/fwlink/?linkid=106793](http://go.microsoft.com/fwlink/?linkid=106793)|  
  
## <a name="logicalphysical-disk-readwrite-latency-analysis"></a>逻辑/物理磁盘读取/写入延迟分析  
 Windows 检测磁盘性能瓶颈的最可靠方法是通过测量其响应时间。 如果响应时间大于.025 （25 毫秒为单位），就是一个保守的阈值，然后可能发生明显减慢速度和影响用户的性能问题。  
  
 不佳的磁盘延迟的常见原因是磁盘碎片，性能缓存，在饱和 SAN，和太多的磁盘上的负载。 使用 SPA 工具来帮助确定前的文件和使用的磁盘的进程。 也检查"过程 IO Data Operations/sec"和"过程 IO 其他 Operations/sec"以查看哪些进程消耗最多磁盘我 / O 的 请记住，性能监视器计数器不能指定涉及哪些文件。  
  
### <a name="references"></a>References  
  
-   排除了在磁盘密集型问题 [http://go.microsoft.com/fwlink/?linkid=50669](http://go.microsoft.com/fwlink/?linkid=50669)  
  
-   如何识别磁盘性能瓶颈使用在 Microsoft 服务器性能审查程序 (SPA) 工具 [http://go.microsoft.com/fwlink/?linkid=98096](http://go.microsoft.com/fwlink/?linkid=98096)  
  
-   下载 Microsoft 服务性能审查程序 (SPA) 在详细信息： [http://go.microsoft.com/fwlink/?linkid=57769](http://go.microsoft.com/fwlink/?linkid=57769)  
  
## <a name="logical-disk-transferssec"></a>逻辑磁盘传输/次数/秒  
 "Disk Transfers/sec"是读取的速率和写入磁盘上的操作。 虽然磁盘传输并不是直接关联磁盘我 / O，它们请告知我们正在执行多少磁盘操作。 如果你的平均顺序我 / O 的和随机我 / O，则你最终会得到约为 80 个我 / O 每秒作为常规的经验法则。 因此，我们应该期望 SAN 驱动器来执行多个 80 我/O 每下的第二个时加载。 此分析检查以查看是否有任何逻辑磁盘的阈值展示较差的响应时间 （大于 25 秒 I/O 操作的响应时间）。 如果是这样，我们应该知道每秒的时间来将达到或超过 80 个磁盘传输。 如果没有，则磁盘体系结构需要进行调查。 不佳的磁盘 I/O 的最常见原因是重载 SAN – 这意味着多个 LUN 正在使用小的物理磁盘阵列的位置的条件上的逻辑单元号 (LUN)。  
  
### <a name="reference"></a>參考  
 NT 服务器和磁盘子系统性能 [http://go.microsoft.com/fwlink/?linkid=106783](http://go.microsoft.com/fwlink/?linkid=106783)  
  
## <a name="available-memory-analysis"></a>可用内存分析  
 "Available Mbytes"是可用兆字节为单位的计算机上运行的进程的物理内存量。 虚拟内存管理器不断调整用在物理内存和磁盘上维护最小为操作系统和进程的可用字节数的空间。 当可用字节数不多、 虚拟内存管理器会让进程工作集的增长或使它们通过删除每个新页面添加一个旧页稳定。 几个可用字节时，虚拟内存管理器必须 trim 要维护的最低要求的进程的工作集。  
  
 此分析将检查以确定总可用内存是否不足 – 10%可用处出现警告和在 5%可用的关键。 下降趋势的 10 MB 的每小时检测到，指示潜在的即将到来的内存不足情况时，警告也会得到通知。 物理内存不足可能导致增加特权模式下 CPU 和系统延迟。  
  
### <a name="references"></a>References  
  
-   在检测内存瓶颈 [http://go.microsoft.com/fwlink/?linkid=106787](http://go.microsoft.com/fwlink/?linkid=106787)  
  
-   排除了在内存密集型问题 [http://go.microsoft.com/fwlink/?linkid=62575](http://go.microsoft.com/fwlink/?linkid=62575)  
  
## <a name="memory-leak-detection-analysis"></a>内存泄漏检测分析  
 此分析将决定是否任何进程正在消耗大量的系统的内存，且是否在内存消耗，随着时间的推移增加过程。 使用大量的内存的进程没什么关系，只要该过程将返回到系统内存。 查找增加图表的趋势。 上升趋势长的一段时间内无法指示内存泄漏。 专用字节数是内存的当前大小 （字节），此进程已分配不能与其他进程共享。 此分析检查 10 MB 的每小时和 5 MB 的每小时增加趋势。 可用内存分析与相关联时使用此分析。  
  
 此外，请注意，新启动的进程将最初显示为内存泄漏时只需正常启动行为。 进程继续占用内存并长的一段时间，不会释放内存时发生内存泄漏。  
  
 如果您怀疑存在内存泄漏条件，然后安装并使用调试诊断工具。 调试诊断工具的详细信息，请参阅引用部分。  
  
### <a name="reference"></a>參考  
 调试诊断工具在的 1.1 版 [http://go.microsoft.com/fwlink/?linkid=106784](http://go.microsoft.com/fwlink/?linkid=106784)  
  
## <a name="memory-pagessec-analysis"></a>内存 Pages/sec 分析  
 此分析检查"页/秒"是否为高。 如果高，然后系统可能内存不足尝试进行分页到磁盘的内存。 "页/秒"是从读取或写入磁盘为解决强制分页错误页的速率。 此计数器是导致系统范围延迟的错误种类的主要指示器。  它是"Memory\Pages Input/sec"和"Memory\Pages Output/sec"的总和。 则将计页数，因此它可以与其他页面，例如"Memory\Page Faults/sec"的计数进行比较。  
  
 此计数器始终应低于 1,000。 此分析检查超过 1,000 个的值。 可用内存分析和内存泄漏检测分析与相关联时使用此分析。 如果所有分析在同一时间都引发警报，这可能表示系统内存不足。 请按照本主题中的其他信息有关内存泄漏检测分析中所述的分析步骤。  
  
### <a name="reference"></a>參考  
 排除了在内存密集型问题 [http://go.microsoft.com/fwlink/?linkid=62575](http://go.microsoft.com/fwlink/?linkid=62575)  
  
## <a name="memory-system-cache-resident-bytes-analysis"></a>内存系统缓存驻留字节数分析  
 "系统缓存驻留字节数"是的大小，以字节为单位，在文件系统缓存中的可分页操作系统代码。 此值只包括当前物理页面，并且不包括任何当前未驻留的虚拟内存页面。 它就是显示在任务管理器中的系统缓存值。 因此，此值可能小于的实际使用的文件系统缓存中的虚拟内存量。 此值是一个组件的"内存\\\System 代码驻留字节数"，它表示所有当前正在物理内存的可分页操作系统代码。 此计数器显示上次观测的值仅;它不是平均值。  
  
 此分析检查上升趋势的 10 MB 的每小时。 承受负载时，服务器可能使用的系统缓存，以便缓存如磁盘 I/O 活动。 将相关联时使用与过程 IO Data Operations/sec 和进程 IO 其他操作数/秒分析。  
  
## <a name="processor-utilization-analysis-and-excessive-processor-use-by-processes"></a>处理器利用率分析和进程过多的处理器使用  
 "%Processor Time"是处理器执行非闲置线程所花的运行时间的百分比。 它是通过测量采样间隔期间，空闲线程处于活动状态的持续时间然后时间然后减去间隔持续时间计算的。 （每个处理器有占用时钟周期当没有其他线程准备好运行的空闲线程）。此计数器是处理器活动的主要指示器，并显示在采样间隔期间观察到的忙碌时间的平均百分比。 它被通过监视服务处于非活动状态的时间，然后从 100%减去该值。  
  
 此分析检查大于每个单个处理器上的 60%的利用率。 如果是这样，确定它是否是高用户模式 CPU 或高特权模式。 如果高特权模式下 CPU 怀疑有问题，请参阅"特权模式 CPU 分析"。 如果怀疑用户模式下处理器瓶颈，则可以考虑使用进程探查器分析导致高 CPU 使用的函数。 请参阅"如何为： 标识导致高用户模式 CPU 瓶颈的出现针对服务器应用程序在生产环境中的函数"的详细信息的参考部分中的文章。  
  
## <a name="processor-queue-length-analysis"></a>处理器队列长度分析  
 "处理器队列长度"是处理器队列中的线程数。 与磁盘计数器，此计数器只显示就绪线程，不正在运行的线程。  没有单个队列的处理器时间百分比甚至具有多个处理器的计算机上。 因此，如果计算机具有多个处理器，需要此值除以处理工作负载的处理器数。 每个处理器少于 10 个线程的持续的处理器队列是通常可接受，取决于工作负荷。  
  
 此分析将决定是否平均处理器队列长度超过处理器的数目。 如果是这样，则这可能表示处理器瓶颈。 与特权模式 CPU 分析和由进程过多的处理器使用相关联时使用此分析。 处理器队列为是准备好，但不是能够执行的处理器，因为当前正在执行另一个活动线程的线程的集合。 持续或重复的更多的处理器数目是处理器瓶颈更好地指示线程的队列。  
  
 你可以结合使用此计数器"处理器\\%Processor Time"计数器以确定你的应用程序是否可以受益于更多的 Cpu。 没有单个队列的处理器时间，即使是在多处理器计算机上。 因此，在多处理器计算机中，将"处理器队列长度"(PQL) 值除以处理工作负载的处理器数  
  
 如果 CPU 非常繁忙 （90%和更高的利用率） 和 PQL 平均值高于一致的处理器数，则可能存在处理器瓶颈，无法受益于更多的 Cpu。 或者，你可能会减少的线程和应用程序级别的队列数。 这将导致减少上下文切换，这很好的降低 CPU 负载。 低 CPU 使用率高 PQL 的常见原因是时间的处理器时间的请求到达随机，和线程要求异常长从处理器。 这意味着处理器不成为瓶颈。 相反，工作线程处理逻辑，需要能够改进。  
  
 如果怀疑用户模式下处理器瓶颈，则可以考虑使用进程探查器分析导致高 CPU 使用的函数。 请参阅"如何为： 标识导致高用户模式 CPU 瓶颈的出现针对服务器应用程序在生产环境中的函数"的详细信息的参考部分中的文章。  
  
## <a name="privileged-mode-cpu-analysis"></a>特权模式下 CPU 分析  
 此计数器指示在特权模式下运行的线程的时间的百分比。 当你的应用程序调用时 （例如，可执行文件或网络 I/O 或分配内存） 的操作系统功能时，这些操作系统功能在特权模式下执行。  
  
 高特权模式下 CPU 指示计算机花费在与实际 （用户模式） 的系统 I/O 工作中太多时间。 "%Privileged Time"是进程线程在特权模式下执行代码所用的运行时间的百分比。  当调用 Windows 系统服务时，服务将通常运行在特权模式下，若要获取对系统专有数据的访问权限。 此类数据不会发生访问由在用户模式下执行的线程。 对系统的调用可以显式或隐式的如页错误或中断。 不像某些早期的操作系统，Windows 使用进程边界对于除了传统的保护的用户和特权的模式的子系统保护。 代表应用程序通过 Windows 某些工作可能会出现在过程中的特权时间除了其他子系统进程中。  
  
 此分析将检查以查看特权模式下 CPU 是否占用了超过 30%的总 CPU。 如果这样，则可能的 CPU 消耗是才导致的网络、 内存或磁盘 I/O 等处理器以外的另一个瓶颈。 使用相关联时使用 %Interrupt Time 和高上下文切换分析。  
  
## <a name="high-context-switching-analysis"></a>高上下文切换分析  
 较高优先级的线程会抢占较低的优先级线程当前正在运行或高优先级的线程块时，会发生情况的上下文切换。 当多个线程共享相同的优先级级别，则会发生的上下文切换的高级别。 这通常指示线程过多在争夺系统上的处理器。 如果你看不到更处理器利用率，请参阅非常低级别的上下文切换，则可能表示线程被阻止。  
  
 高特权模式下，CPU 和总体 CPU 时应仅调查高上下文切换。 一般情况下，上下文切换速率小于每个处理器每秒 5,000 的不是值得担心。 如果上下文切换率超过每个处理器每秒的 15000，则一个约束。  
  
 此分析检查高 CPU、 高特权模式下 CPU 和高 （大于为每个处理器的 5,000） 系统上下文切换每秒在同一时间发生的所有。 如果出现高上下文切换，然后减少线程和系统上运行的进程的数。  
  
## <a name="biztalk-high-database-sessions-analysis"></a>BizTalk 高数据库会话分析  
 此计数器有两个可能的值即正常 (0)，或超出了 (1)。 此分析检查的值为 1。 如果是这样，BizTalk 超过了允许的数据库会话数的阈值。 此值由 BizTalk 主机限制设置中的"每个 CPU 的数据库连接"值控制。  
  
 "数据库连接每个 CPU"是最大并发数据库会话数 （每个 CPU) 限制开始之前允许。 此计数不包括通用的每主机会话池中的空闲数据库会话数，并且只对主机实例实际使用的会话数进行此检查。 默认情况下; 禁用此选项通常情况下，此设置应仅启用如果数据库服务器是瓶颈或低端的数据库服务器在 BizTalk Server 系统中。 可以通过使用 BizTalk:Message 代理性能对象类别下的数据库会话性能计数器来监视活动数据库连接数。 此参数只影响出站消息阻止功能。 输入值 0 可以禁用基于数据库会话数的阻止功能。 默认值为 0。  
  
> [!NOTE]  
>  "MaxWorkerThreads"注册表项会影响到 BizTalk 可用线程的数目，并且有助于如果 BizTalk 线程中的大部分均忙于数据库连接。  
  
### <a name="references"></a>References  
  
-   限制在性能计数器的主机 [http://go.microsoft.com/fwlink/?LinkID=155285](http://go.microsoft.com/fwlink/?LinkID=155285)  
  
-   线程、 DB 会话和限制在 [http://go.microsoft.com/fwlink/?linkid=106793](http://go.microsoft.com/fwlink/?linkid=106793)  
  
-   会影响适配器的性能的配置参数 [http://go.microsoft.com/fwlink/?LinkID=154200](http://go.microsoft.com/fwlink/?LinkID=154200)  
  
-   如何修改限制在设置的默认主机 [http://go.microsoft.com/fwlink/?LinkID=155296](http://go.microsoft.com/fwlink/?LinkID=155296)  
  
## <a name="biztalk-high-database-size-analysis"></a>BizTalk 高数据库大小分析  
 此计数器是指此进程已发布的数据库队列中的消息数。 此值按所有主机队列表中的项数以及后台处理表和跟踪表中的项数来衡量。 队列包括工作队列、 状态队列和挂起的队列。 如果要将某一进程发布到多个队列，则此计数器将反映所有队列的加权平均值。  
  
 如果重新启动该主机，则内存中保留的统计信息将丢失。 由于涉及一些开销，请将恢复 BizTalk Server，仅当有至少 100 发布，5%的总发布重新启动的主机进程内收集统计信息。  
  
 为数据库阈值中的消息计数列出的条件之一时，此计数器将设置为值为 1。 此阈值记录在该主题如何修改默认主机限制设置下面引用。 默认情况下，主机消息限制阈值的数据库中的计数设置为值为 50000，就会触发在下列情况下的限制条件：  
  
-   主机实例发布到订阅主机的工作、状态和已挂起队列的消息总数超过 50,000。  
  
-   后台处理表或跟踪表中的消息数超过 500,000。  
  
 在计算中使用数据库邮件计数中包括挂起的消息，因为限制的消息发布即使 BizTalk server 遇到低或没有负载会发生。  
  
 此分析检查的值为 1。 如果发生这种情况，请考虑将减少在数据库中的消息数的操作过程。 例如，确保 BizTalk SQL Server 作业运行正常并使用 BizTalk 管理控制台中的组中心数据库来确定是否将消息生成向上引起的大量的挂起的消息。  
  
### <a name="references"></a>References  
  
-   挂起的消息都包含在数据库限制阈值中的消息计数 [http://go.microsoft.com/fwlink/?LinkId=155304](http://go.microsoft.com/fwlink/?LinkId=155304)  
  
-   如何修改限制在设置的默认主机 [http://go.microsoft.com/fwlink/?LinkID=155296](http://go.microsoft.com/fwlink/?LinkID=155296)  
  
-   限制在性能计数器的主机 [http://go.microsoft.com/fwlink/?LinkID=155285](http://go.microsoft.com/fwlink/?LinkID=155285)  
  
## <a name="biztalk-high-in-process-message-count-analysis"></a>BizTalk 高进程内消息计数分析  
 在主机限制设置的"进程内消息每个 CPU"设置是最大的未处理的消息传递到的终结点管理器 (EPM) 或 XLANG 数。 此数字不包括从但仍等待中内存中队列的传递的数据库中检索的消息。 可以通过使用 BizTalk:Message 代理性能对象类别下的进程内消息计数性能计数器来监视进程内消息数。 在考虑限制条件时，此参数提供的限制机制提示。 实际阈值可能会自我优化。 你可以通过监视的进程内消息计数性能计数器来验证实际阈值。  
  
 此参数可以设置为较小的值对于大型消息方案，其中的平均消息大小较高，或消息的处理可能需要大量的消息。 这将是很明显，如果一个方案遇到过于频繁基于内存的限制和内存阈值获取自动调整为大体上低的值。 这样将指示出站传输应降低同时处理的消息数以避免占用过高内存。 此外，如果适配器一次处理多个消息（例如在向限制并行连接数的服务器发送消息时）可获得更高效率，则可以将此参数优化为低于默认值的值。  
  
 此分析检查的进程内消息计数高计数器以确定是否发生这种类型的限制。 如果是这样，请考虑调整"每 CPU 邮件进程内"设置。 此参数只影响出站消息阻止功能。 在禁用限制基于每个 CPU 进程内消息数"进程内消息每个 CPU"设置中输入的值为 0。 "进程内消息每个 CPU"设置的默认值为 1000。 请注意，修改此值还可以影响在低延迟的消息和/或 BizTalk 资源的效率。  
  
### <a name="references"></a>References  
  
-   如何修改限制在设置的默认主机 [http://go.microsoft.com/fwlink/?LinkID=155296](http://go.microsoft.com/fwlink/?LinkID=155296)  
  
-   限制在性能计数器的主机 [http://go.microsoft.com/fwlink/?LinkID=155285](http://go.microsoft.com/fwlink/?LinkID=155285)  
  
## <a name="biztalk-high-message-delivery-rate-analysis"></a>BizTalk 高邮件传递速率分析  
 对于出站 （发送） 的消息，BizTalk Server 限制的消息传送，如果主机实例的消息传递传入速率超过传出速率消息传递 * 指定的速率 overdrive 因子 （%） 的值。 在消息处理限制设置对话框上，速率 overdrive 因素 （百分比） 参数是可配置。 基于速率限制的出站消息是主要通过将从内存中队列中删除消息，并将消息传递到的终结点管理器 (EPM) 或业务流程引擎会为处理前的延迟实现的。 不执行任何其他操作来完成基于速率限制的出站消息。  
  
 出站阻止可能导致消息送达延迟，消息可能会在内存中队列中堆积，并可能导致出列线程被阻止，直到阻止条件得以缓解。 当取消排队线程被阻止，从消息框中放入内存中队列进行出站传递提取任何额外的消息。  
  
 此分析检查的值为 1 中的高的消息传送速率计数器。 高的消息传送速率可能引起高处理复杂性、 慢速的出站适配器或暂时的系统资源不足。  
  
### <a name="references"></a>References  
  
-   限制在性能计数器的主机 [http://go.microsoft.com/fwlink/?LinkID=155285](http://go.microsoft.com/fwlink/?LinkID=155285)  
  
-   BizTalk Server 如何实现在限制的主机 [http://go.microsoft.com/fwlink/?LinkID=155286](http://go.microsoft.com/fwlink/?LinkID=155286)  
  
-   如何修改限制在设置的默认主机 [http://go.microsoft.com/fwlink/?LinkID=155296](http://go.microsoft.com/fwlink/?LinkID=155296)  
  
## <a name="biztalk-high-process-memory-analysis"></a>BizTalk 高进程内存分析  
 限制阈值设置的 BizTalk 进程内存使用量是内存的相比工作集大小和进程的总可用虚拟内存的总和，如果输入从 1 到 100 之间的值所使用百分比。 默认情况下，BizTalk 进程内存使用情况限制设置为 25。 在指定百分比值时，将按固定的时间间隔来重新计算进程内存阈值。 如果用户指定一个百分比值，它是根据计算为提交和当前的进程内存使用量的可用内存。  
  
 此分析检查 1 中的高进程内存计数器的值。 如果发生这种情况，然后尝试通过使用调试诊断确定内存增加的原因 （请参阅在内存泄漏检测分析中的引用）。 请注意，是正常的进程在启动和这期间使用的内存很大一部分它可能最初显示为内存泄漏，但进程无法释放它不再需要从而减少的可用我的内存，则会发生了真正的内存泄漏随着时间的推移 mory。 有关如何以一般方式分析 BizTalk 中的进程内存泄漏，请参阅下面的"如何为捕获内存转储的进程，是泄露内存"引用和/或"内存泄漏检测"分析 PAL 中的有关详细信息。  
  
 如果要发布的批具有陡峭的内存要求高的进程内存限制可能发生或线程过多所处理的消息。  如果系统看起来过度限制，请考虑增加主机进程内存使用情况阈值与关联的值，并验证主机实例不会生成"内存不足"错误。 如果通过增加进程内存使用情况阈值引发"内存不足"错误，请考虑减少内部消息队列大小的值，并且进程内每个 CPU 阈值的消息。 此策略特别适用于大型消息处理方案。 此外，此值应设置为具有较大内存要求每个消息的方案的低值。 设置较低的值将在早期限制开始运作，并使进程内的内存分解。  
  
 如果你的 BizTalk server 定期运行虚拟内存不足时，请考虑 BizTalk Server 64 位。 在 64 位服务器上的每个进程可以解决最高支持 4 TB 的虚拟内存与在 32 位 2 GB。 一般情况下，强烈建议 BizTalk 64 位和 64 位 SQL Server。 请参阅有关详细信息"BizTalk Server 64 位支持"参考。  
  
### <a name="references"></a>References  
  
-   BizTalk Server 如何实现在限制的主机 [http://go.microsoft.com/fwlink/?LinkID=155286](http://go.microsoft.com/fwlink/?LinkID=155286)  
  
-   如何修改限制在设置的默认主机 [http://go.microsoft.com/fwlink/?LinkID=155296](http://go.microsoft.com/fwlink/?LinkID=155296)  
  
-   如何捕获在泄漏内存的进程内存转储 [http://go.microsoft.com/fwlink/?LinkId=155305](http://go.microsoft.com/fwlink/?LinkId=155305)  
  
-   在 BizTalk Server 64 位支持 [http://go.microsoft.com/fwlink/?LinkId=155306](http://go.microsoft.com/fwlink/?LinkId=155306)  
  
## <a name="biztalk-high-system-memory-analysis"></a>BizTalk 高系统内存分析  
 BizTalk 物理内存使用情况限制阈值设置为输入相比从 1 到 100 之间的可用物理内存的值如果总量的内存消耗的百分比。 如果输入大于 100 的值，此设置也可以在兆字节为单位的可用物理内存的总量。 输入值 0 可以禁用基于物理内存使用率的阻止功能。 默认值为 0。  
  
 此分析检查 1 中的较高的系统内存计数器的值。 由于这样将度量系统内存总量，因此如果非 BizTalk Server 进程占用过多的系统内存，则可能会触发阻止条件。 因此如果发生这种情况，最好的方法是确定哪些进程使用在大多数物理内存和/或向服务器添加额外的物理内存。 此外，请考虑减少 EPM 线程池的默认大小和/或适配器批的大小，从而减少负载。 有关详细信息，请参阅 PAL 中的内存泄漏检测分析。  
  
### <a name="references"></a>References  
  
-   限制在性能计数器的主机 [http://go.microsoft.com/fwlink/?LinkID=155285](http://go.microsoft.com/fwlink/?LinkID=155285)  
  
-   如何修改限制在设置的默认主机 [http://go.microsoft.com/fwlink/?LinkID=155296](http://go.microsoft.com/fwlink/?LinkID=155296)  
  
-   BizTalk Server 如何实现在限制的主机 [http://go.microsoft.com/fwlink/?LinkID=155286](http://go.microsoft.com/fwlink/?LinkID=155286)  
  
## <a name="biztalk-high-thread-count-analysis"></a>BizTalk 高线程计数分析  
 "每个 CPU 线程数"是宿主进程包括由适配器使用的线程中的线程总数。 如果超出此阈值，BizTalk Server 将尝试减小 EPM 线程池和消息代理线程池的大小。 如果高负载可能导致创建大量线程，则在这种情况下，应启用基于线程的阻止功能。 此参数同时影响入站和出站阻止功能。 默认情况下，禁用基于线程限制。  
  
> [!NOTE]  
>  用户指定的值用作一项准则，并且主机动态自行调整此阈值基于内存使用模式和线程要求的过程。  
  
 此分析检查值为高线程计数计数器中的 1。 考虑调整不同线程池的大小，以确保系统不会创建大量线程。 每第二个分析，以确定是否操作系统已经饱和与线程过多，但在大多数情况下，高线程计数原因比的后端数据库上的 BizTalk server 的详细争用，可以使用上下文切换关联此分析。 有关修改线程池大小的详细信息请参阅如何修改默认主机限制中的设置的引用。  
  
### <a name="references"></a>References  
  
-   限制在性能计数器的主机 [http://go.microsoft.com/fwlink/?LinkID=155285](http://go.microsoft.com/fwlink/?LinkID=155285)  
  
-   BizTalk Server 如何实现在限制的主机 [http://go.microsoft.com/fwlink/?LinkID=155286](http://go.microsoft.com/fwlink/?LinkID=155286)  
  
-   如何修改限制在设置的默认主机 [http://go.microsoft.com/fwlink/?LinkID=155296](http://go.microsoft.com/fwlink/?LinkID=155296)  
  
-   会影响适配器的性能的配置参数 [http://go.microsoft.com/fwlink/?LinkID=154200](http://go.microsoft.com/fwlink/?LinkID=154200)  
  
-   线程、 DB 会话和限制在 [http://go.microsoft.com/fwlink/?linkid=106793](http://go.microsoft.com/fwlink/?linkid=106793)  
  
 BizTalk 入站延迟 AnalysisAverage 延迟消息引擎文档从接收适配器之前发布到消息框的时间 （毫秒）。 减少延迟是重要的 BizTalk，某些用户因此跟踪时间文档在入站适配器中的花费多少是很重要。  
  
 下面是一个图，显示延迟的衡量标准。  
  
|1|2|3|4|5|6|  
|-------|-------|-------|-------|-------|-------|  
|适配器接收消息，并提交在这些性能计数器中捕获它与引擎之前消息提供不引擎适配器中完成的工作|引擎从适配器接收消息，执行接收管道、 映射、 订阅计算，保留在数据库中的消息。|业务流程或请求-响应端口将运行并生成响应消息。|响应消息取消排队消息引擎中，执行发送管道，映射。|消息传递引擎赋予适配器的响应消息。|适配器通知引擎消息就可全部完成。|  
||I|||||  
||RR|RR|RR|||  
||||O|O|O|  
|||||OA|OA|  
  
 我 = 入站的延迟  
  
 RR = 请求的响应延迟时间  
  
 O = 出站延迟  
  
 OA = 出站适配器延迟  
  
 假设低延迟环境，这种分析检查是否文档所用的入站适配器中的时间超过 5 秒。 这可能表示通过此主机实例中的入站适配器的消息传输的处理延迟。 如果此主机实例中存在多个入站的适配器，请考虑将它们分散到其自己的主机，以确定哪个入站的适配器的高延迟。  
  
### <a name="references"></a>References  
  
-   BizTalk Server 数据库优化  
    [http://go.microsoft.com/fwlink/?linkid=104427](http://go.microsoft.com/fwlink/?linkid=104427)  
  
-   请求/响应消息传送  
    [http://go.microsoft.com/fwlink/?LinkID=155288](http://go.microsoft.com/fwlink/?LinkID=155288)  
  
-   识别瓶颈 BizTalk 层中  
    [http://go.microsoft.com/fwlink/?LinkID=155289](http://go.microsoft.com/fwlink/?LinkID=155289)  
  
## <a name="biztalk-message-delivery-throttling-state-analysis"></a>BizTalk 消息传递限制状态分析  
 BizTalk 消息传递限制状态是之一的限制的主要指示器。 它是一个标志，指示系统是否限制 （影响 XLANG 消息处理和出站传输协议） 的消息传递。 由计数器的数值表示限制条件。 下面是值和及其各自的含义的列表：  
  
|||  
|-|-|  
|0|不限制|  
|1|由于消息送达速率不匹配（输入速率超出输出速率）而阻止|  
|3|由于进程内消息数过高而阻止|  
|4|由于进程内存压力而阻止|  
|5|由于系统内存压力而阻止|  
|9|由于线程数过高而阻止|  
|10|由于送达时的用户替代而阻止|  
  
 此分析检查其中每个值，并为每个具有特定的警报。  
  
### <a name="references"></a>References  
  
-   限制在性能计数器的主机 [http://go.microsoft.com/fwlink/?LinkID=155285](http://go.microsoft.com/fwlink/?LinkID=155285)  
  
-   BizTalk Server 如何实现在限制的主机 [http://go.microsoft.com/fwlink/?LinkID=155286](http://go.microsoft.com/fwlink/?LinkID=155286)  
  
## <a name="biztalk-messagebox-database-connection-failures-analysis"></a>BizTalk MessageBox 数据库连接故障分析  
 此性能计数器是自主机实例启动以来失败的尝试的数据库连接数。 如果出于任何原因，SQL Server 服务承载 BizTalk 数据库将变得不可用，数据库群集会将资源从活动的计算机传输到被动的计算机。 在此故障转移过程中，BizTalk Server 服务实例会遇到数据库连接失败，这些实例将自动重新启动以重新连接到数据库。 采用故障转移期间传输的资源后，正在运行的数据库计算机（即前面提到的被动计算机）将开始处理数据库连接。  
  
 当 BizTalk Server 运行时不能与 MessageBox 或管理数据库进行通信时，将发生 DBNetLib （数据库网络库） 错误。 当发生这种情况时，捕获异常的 BizTalk Server 运行时实例关闭，然后循环每隔一分钟来检查数据库是否可用。 有关此主题，请参阅引用部分以了解更多信息。  
  
 当客户端启动到服务器的 TCP/IP 套接字连接时，客户端通常连接到服务器上的特定端口，并请求服务器通过临时（或暂时）TCP 或 UDP 端口进行响应。 在 Windows Server 2003 和 Windows XP，由客户端应用程序使用的临时端口的默认范围是从 1025 到 5000。 在某些情况下，很可能将耗尽默认范围内的可用端口。 有关此主题，请参阅引用部分以了解更多信息。  
  
 此分析检查数据库连接失败的任何匹配项。 数据库连接故障十分重要，因为 BizTalk 无法函数没有数据库。 如果数据库连接失败的原因是未知的然后请考虑下面列出的引用和/或联系 Microsoft 支持部门确定连接故障的性质。  
  
### <a name="references"></a>References  
  
-   向外扩展的数据库  
    [http://go.microsoft.com/fwlink/?LinkId=155307](http://go.microsoft.com/fwlink/?LinkId=155307)  
  
-   避免出现 DBNETLIB 异常  
    [http://go.microsoft.com/fwlink/?LinkId=155308](http://go.microsoft.com/fwlink/?LinkId=155308)  
  
-   避免 TCP/IP 端口耗尽  
    [http://go.microsoft.com/fwlink/?LinkId=155309](http://go.microsoft.com/fwlink/?LinkId=155309)  
  
## <a name="biztalk-messaging-publishing-throttling-state-analysis"></a>BizTalk 消息传送发布限制状态分析  
 发布限制状态 BizTalk 消息是一个限制的主要指示器。 它是一个标志，指示系统是否限制 （影响 XLANG 消息处理和入站传输协议） 的消息发布。由计数器的数值表示限制条件。 下面是值和及其各自的含义的列表：  
  
|||  
|-|-|  
|0|不限制|  
|2|由于消息发布速率不匹配（输入速率超出输出速率）而阻止|  
|4|由于进程内存压力而阻止|  
|5|由于系统内存压力而阻止|  
|6|由于数据库增长而阻止|  
|8|由于会话数过高而阻止|  
|9|由于线程数过高而阻止|  
|11|由于发布时的用户替代而阻止|  
  
 此分析检查其中每个值，并为每个具有特定的警报。  
  
### <a name="references"></a>References  
  
-   限制在性能计数器的主机 [http://go.microsoft.com/fwlink/?LinkID=155285](http://go.microsoft.com/fwlink/?LinkID=155285)  
  
-   BizTalk Server 如何实现在限制的主机 [http://go.microsoft.com/fwlink/?LinkID=155286](http://go.microsoft.com/fwlink/?LinkID=155286)  
  
## <a name="biztalk-orchestrations-resident-in-memory"></a>BizTalk 业务流程驻留在内存中  
 当前以主机实例为宿主的业务流程实例的数量。 峰值或爆发的业务流程驻留在内存中可能被视为正常，而上升趋势可能表示"积累"在内存中的业务流程。 当 BizTalk 无法冻结消息/业务流程实例时，可能会出现随着时间的推移上升趋势。 尝试将此计数器与"XLANG/s Orchestrations(?) 相关联\Dehydratable 业务流程"问号 （？） 所在相同作为此计数器的计数器实例。  
  
 如果大量的业务流程都驻留在内存中的，并且如果业务流程的数量较少是否可冻结，然后你的业务流程很可能在内存中处于空闲状态，并可能导致内存泄漏情况。 如果存在，请选择与"\XLANG/s 业务流程 （*） \Idle 业务流程"相关联时使用此分析。 在 BizTalk 空闲业务流程中的上升趋势是更好由于冻结业务流程实例的内存泄漏的指标。  
  
 此分析检查在驻留在内存和如果超过 50%的驻留在内存中的业务流程不可冻结业务流程中上升趋势。  
  
### <a name="references"></a>References  
  
-   业务流程引擎性能计数器  
    [http://go.microsoft.com/fwlink/?LinkID=155290](http://go.microsoft.com/fwlink/?LinkID=155290)  
  
-   业务流程冻结和 Rehydration  
    [http://go.microsoft.com/fwlink/?LinkID=155284](http://go.microsoft.com/fwlink/?LinkID=155284)  
  
## <a name="biztalk-private-bytes-analysis"></a>BizTalk 专用字节分析  
 这是分配的专用内存的主机实例和类似于"\Process （*） \Private 字节数"性能计数器的兆字节。 专用字节数是内存的当前的大小，以字节为单位的进程已分配不能与其他进程共享。 此分析将决定是否任何主机实例消耗的系统内存的大小，并在主机实例是否在内存消耗，随着时间的推移增加。 使用大量的内存的主机实例没什么，只要它返回到系统内存。 查找增加图表的趋势。 上升趋势长的一段时间内无法指示内存泄漏。  
  
 此分析检查 10 MB 每小时上升趋势。 可用内存分析和内存泄漏分析与相关联时使用此分析。 此外，请记住，新启动实例将最初显示为内存泄漏时只需正常启动行为的主机。 当进程继续使用内存，以及长的一段时间没有释放内存，内存泄漏。 如果你怀疑存在内存泄漏条件，请阅读下面引用"BizTalk 消息的内存增长"中的文章。 否则为安装并使用调试诊断工具。 调试诊断工具的详细信息，请参阅引用部分。  
  
### <a name="references"></a>References  
  
-   调试诊断工具 1.1 版  
    [http://go.microsoft.com/fwlink/?linkid=106784](http://go.microsoft.com/fwlink/?linkid=106784)  
  
-   BizTalk 消息传送中的内存增长  
    [http://go.microsoft.com/fwlink/?linkid=108788](http://go.microsoft.com/fwlink/?linkid=108788)  
  
## <a name="biztalk-virtual-bytes-analysis"></a>BizTalk 虚拟字节分析  
 这是适用于主机实例的虚拟内存保留的兆字节。 此分析将决定是否任何主机实例正在消耗大量的系统内存，且是否随时间推移的内存消耗中增加的主机实例。 使用大量的内存的主机实例没什么，只要它返回到系统内存。 查找增加图表的趋势。 上升趋势长的一段时间内无法指示内存泄漏。  
  
 此分析检查以虚拟字节为单位按小时 10 MB 的上升趋势。 可用内存分析和内存泄漏分析与相关联时使用此分析。 此外，请记住，新启动实例将最初显示为内存泄漏时只需正常启动行为的主机。 当进程继续使用内存，以及长的一段时间没有释放内存，内存泄漏。 如果您怀疑存在内存泄漏条件，然后阅读下面"BizTalk 消息的内存增长"中的文章。 否则为安装并使用调试诊断工具。 调试诊断工具的详细信息，请参阅引用部分。  
  
### <a name="references"></a>References  
  
-   调试诊断工具 1.1 版  
    [http://go.microsoft.com/fwlink/?linkid=106784](http://go.microsoft.com/fwlink/?linkid=106784)  
  
-   BizTalk 消息传送中的内存增长  
    [http://go.microsoft.com/fwlink/?linkid=108788](http://go.microsoft.com/fwlink/?linkid=108788)  
  
## <a name="biztalk-message-agent-database-session-throttling-analysis"></a>BizTalk 消息代理数据库会话限制分析  
 这是到 MessageBox 相比限制设置其各自 BizTalk 打开数据库连接数。 "数据库连接每个 CPU"是最大并发数据库会话数 （每个 CPU) 限制开始之前允许。 此计数不包括通用的每主机会话池中的空闲数据库会话数，并且只对主机实例实际使用的会话数进行此检查。 默认情况下，此选项为禁用状态；通常，只有当数据库服务器成为 BizTalk Server 系统的瓶颈时才应启用此设置。 可以通过使用 BizTalk:Message 代理性能对象类别下的数据库会话性能计数器来监视活动数据库连接数。 此参数只影响出站消息阻止功能。 输入值 0 可以禁用基于数据库会话数的阻止功能。 默认值为 0。  
  
 MaxWorkerThreads 注册表项已影响到 BizTalk 可用线程的数目，并可帮助在大部分 BizTalk 的线程都是忙于处理数据库连接的情况下。 此分析检查到 MessageBox 的打开的数据库连接数是否大于 80%的数据库会话限制，设置，这表明可能限制条件。  
  
### <a name="references"></a>References  
  
-   限制在性能计数器的主机 [http://go.microsoft.com/fwlink/?LinkID=155285](http://go.microsoft.com/fwlink/?LinkID=155285)  
  
-   会影响适配器的性能的配置参数 [http://go.microsoft.com/fwlink/?LinkID=154200](http://go.microsoft.com/fwlink/?LinkID=154200)  
  
-   线程、 DB 会话和限制在 [http://go.microsoft.com/fwlink/?linkid=106793](http://go.microsoft.com/fwlink/?linkid=106793)  
  
## <a name="biztalk-message-agent-database-session-throttling-threshold-analysis"></a>BizTalk 消息代理数据库会话限制阈值分析  
 这是到 MessageBox 的打开的数据库连接数的当前阈值。 "数据库连接每个 CPU"是最大并发数据库会话数 （每个 CPU) 限制开始之前允许。 此计数不包括通用的每主机会话池中的空闲数据库会话数，并且只对主机实例实际使用的会话数进行此检查。 默认情况下，此选项为禁用状态；通常，只有当数据库服务器成为 BizTalk Server 系统的瓶颈时才应启用此设置。 可以通过使用 BizTalk:Message 代理性能对象类别下的数据库会话性能计数器来监视活动数据库连接数。 此参数只影响出站消息阻止功能。 输入值 0 可以禁用基于数据库会话数的阻止功能。 默认值为 0。  
  
 MaxWorkerThreads 注册表项已影响到 BizTalk 可用线程的数目，并可帮助在大部分 BizTalk 的线程都是忙于处理数据库连接的情况下。 此分析检查此值，以确定是否它进行修改得到了其默认设置。 默认情况下，此设置是 0，表示针对数据库会话限制处于禁用状态。  
  
### <a name="references"></a>References  
  
-   限制在性能计数器的主机 [http://go.microsoft.com/fwlink/?LinkID=155285](http://go.microsoft.com/fwlink/?LinkID=155285)  
  
-   会影响适配器的性能的配置参数 [http://go.microsoft.com/fwlink/?LinkID=154200](http://go.microsoft.com/fwlink/?LinkID=154200)  
  
-   线程、 DB 会话和限制在 [http://go.microsoft.com/fwlink/?linkid=106793](http://go.microsoft.com/fwlink/?linkid=106793)  
  
## <a name="biztalk-message-agent-in-process-message-count-throttling-analysis"></a>BizTalk 消息代理进程内消息计数限制分析  
 这是处理服务类的并发消息数。 在主机限制设置的"进程内消息每个 CPU"设置是最大的未处理的消息传递到的终结点管理器 (EPM) 或 XLANG 数。 这不包括从数据库中检索，但仍在等待中内存中队列的传递的消息。 可以通过使用 BizTalk:Message 代理性能对象类别下的进程内消息计数性能计数器来监视进程内消息数。 此参数提供了阻止机制提示以便您考虑阻止条件。 实际阈值可能会自我优化。 通过监视 In-process message count 性能计数器，可以验证实际的阈值。  
  
 对于大型消息方案 （其中的平均消息大小较高，或消息的处理可能需要大量的消息），此参数可以设置为较小的值。 如果基于内存的限制过于频繁发生，并且内存阈值获取自动调整为大体上低的值，指示大型消息方案。 这样将指示出站传输应降低同时处理的消息数以避免占用过高内存。 此外，如果适配器一次处理多个消息（例如在向限制并行连接数的服务器发送消息时）可获得更高效率，则可以将此参数优化为低于默认值的值。 此分析将检查以确定它是否大于 80%的同一名称的其限制设置，它指示限制条件已可能的高的进程内消息 Count 计数器。  
  
### <a name="references"></a>References  
  
-   限制在性能计数器的主机 [http://go.microsoft.com/fwlink/?LinkID=155285](http://go.microsoft.com/fwlink/?LinkID=155285)  
  
-   如何修改限制在设置的默认主机 [http://go.microsoft.com/fwlink/?LinkID=155296](http://go.microsoft.com/fwlink/?LinkID=155296)  
  
## <a name="biztalkmessage-agent-in-process-message-count-throttling-threshold-analysis"></a>限制阈值分析 BizTalk:Message 代理进程内消息计数  
 这是处理服务类的并发消息数的当前阈值。 在主机限制设置的"进程内消息每个 CPU"设置是最大的未处理的消息传递到的终结点管理器 (EPM) 或 XLANG 数。 这不包括从数据库中检索，但仍在等待中内存中队列的传递的消息。 可以通过使用 BizTalk:Message 代理性能对象类别下的进程内消息计数性能计数器来监视进程内消息数。 此参数提供了阻止机制提示以便您考虑阻止条件。 实际阈值可能会自我优化。 通过监视 In-process message count 性能计数器，可以验证实际的阈值。  
  
 对于大型消息方案 （其中的平均消息大小较高，或消息的处理可能需要大量的消息），此参数可以设置为较小的值。 如果基于内存的限制过于频繁发生，并且内存阈值获取自动调整为大体上低的值，指示大型消息方案。 这样将指示出站传输应降低同时处理的消息数以避免占用过高内存。 此外，如果适配器一次处理多个消息（例如在向限制并行连接数的服务器发送消息时）可获得更高效率，则可以将此参数优化为低于默认值的值。 此分析检查高进程内消息计数限制为非默认值的阈值。  
  
### <a name="references"></a>References  
  
-   限制在性能计数器的主机 [http://go.microsoft.com/fwlink/?LinkID=155285](http://go.microsoft.com/fwlink/?LinkID=155285)  
  
-   如何修改限制在设置的默认主机 [http://go.microsoft.com/fwlink/?LinkID=155296](http://go.microsoft.com/fwlink/?LinkID=155296)  
  
## <a name="biztalk-message-agent-process-memory-usage-mb-throttling-analysis"></a>BizTalk 消息代理进程内存使用率 (MB) 限制分析  
 这是当前进程 (MB) 的内存使用率。 BizTalk 进程内存限制可能要发布的批有陡峭的内存需求，或如果线程过多所处理的消息时发生。  如果系统看起来过度限制，请考虑增加主机进程内存使用情况阈值与关联的值，并验证主机实例不会生成"内存不足"错误。 如果通过增加进程内存使用情况阈值引发"内存不足"错误，请考虑减少内部消息队列大小的值，并且进程内每个 CPU 阈值的消息。 此策略特别适用于大型消息处理方案。  
  
 如果你的 BizTalk server 定期运行虚拟内存不足时，请考虑 BizTalk Server 64 位。 在 64 位服务器上的每个进程可以解决最高支持 4 TB 的虚拟内存与在 32 位 2 GB。 一般情况下，强烈建议 BizTalk 64 位和 64 位 SQL Server。 请参阅有关详细信息"BizTalk Server 64 位支持"参考。 此分析检查的进程内存使用量是否大于 80%的具有相同名称的其各自限制阈值。 默认情况下，BizTalk 进程内存使用情况限制设置是可用于进程的虚拟内存的 25%。 /3GB 开关不起对此设置。  
  
### <a name="references"></a>References  
  
-   BizTalk Server 如何实现在限制的主机 [http://go.microsoft.com/fwlink/?LinkID=155286](http://go.microsoft.com/fwlink/?LinkID=155286)  
  
-   如何修改限制在设置的默认主机 [http://go.microsoft.com/fwlink/?LinkID=155296](http://go.microsoft.com/fwlink/?LinkID=155296)  
  
-   如何捕获在泄漏内存的进程内存转储 [http://go.microsoft.com/fwlink/?LinkId=155305](http://go.microsoft.com/fwlink/?LinkId=155305)  
  
-   在 BizTalk Server 64 位支持 [http://go.microsoft.com/fwlink/?LinkId=155306](http://go.microsoft.com/fwlink/?LinkId=155306)  
  
## <a name="biztalkmessage-agent-process-memory-usage-mb-throttling-threshold-analysis"></a>BizTalk:Message 代理进程内存使用率 (MB) 限制阈值分析  
 这是当前进程 (MB) 的内存使用量的当前阈值。 可能根据实际的此过程，并且其内存消耗模式的可用内存量动态调整阈值。 BizTalk 进程内存限制可能要发布的批有陡峭的内存需求，或如果线程过多所处理的消息时发生。 如果系统看起来过度限制，请考虑增加主机进程内存使用情况阈值与关联的值，并验证主机实例不会生成"内存不足"错误。 如果通过增加进程内存使用情况阈值引发"内存不足"错误，请考虑减少内部消息队列大小的值，并且进程内每个 CPU 阈值的消息。 此策略特别适用于大型消息处理方案。  
  
 如果你的 BizTalk server 定期运行虚拟内存不足时，请考虑 BizTalk Server 64 位。 在 64 位服务器上的每个进程可以解决最高支持 4 TB 的虚拟内存与在 32 位 2 GB。 一般情况下，强烈建议 BizTalk 64 位和 64 位 SQL Server。 请参阅有关详细信息"BizTalk Server 64 位支持"参考。 此分析检查是否将进程内存限制设置为非默认值。  
  
### <a name="references"></a>References  
  
-   BizTalk Server 如何实现在限制的主机 [http://go.microsoft.com/fwlink/?LinkID=155286](http://go.microsoft.com/fwlink/?LinkID=155286)  
  
-   如何修改限制在设置的默认主机 [http://go.microsoft.com/fwlink/?LinkID=155296](http://go.microsoft.com/fwlink/?LinkID=155296)  
  
-   如何捕获在泄漏内存的进程内存转储 [http://go.microsoft.com/fwlink/?LinkId=155305](http://go.microsoft.com/fwlink/?LinkId=155305)  
  
-   在 BizTalk Server 64 位支持 [http://go.microsoft.com/fwlink/?LinkId=155306](http://go.microsoft.com/fwlink/?LinkId=155306)