---
title: 系统级瓶颈 |Microsoft Docs
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0bdff435-76eb-495f-9fb6-1f1acef3921e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c736cb7de384edadac1c7b4c0fd840e8d4e7cac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400681"
---
# <a name="system-level-bottlenecks"></a>系统级瓶颈
本主题介绍如何解决常见的系统级瓶颈可能会影响 BizTalk Server 解决方案的性能。  
  
## <a name="creating-a-snapshot-of-the-baseline-configuration"></a>创建基线配置的快照  
 收集以下信息可以为您提供可用于帮助更正系统级瓶颈中的基线配置的快照。  
  
### <a name="gather-documentation"></a>收集文档  
 查看体系结构和方案的基础结构的文档。  
  
### <a name="run-the-baseline-security-analyzer"></a>运行基准安全分析器  
 请执行以下步骤来运行基准安全分析器：  
  
1.  下载[Microsoft Baseline Security Analyzer 2.2](http://go.microsoft.com/fwlink/?LinKID=204006) (http://go.microsoft.com/fwlink/?LinkId=204006)。  
  
2.  使用域管理员帐户，登录到承载 BizTalk Server 和 SQL Server 计算机在同一网络上的计算机。  
  
3.  在当前计算机 （例如，一个 BizTalk Server 计算机或单独的计算机） 上安装 Microsoft Baseline Security Analyzer。  
  
4.  执行单独的扫描 (**开始扫描**)，指定为参数的名称或每个 BizTalk Server 和 SQL Server 计算机的 IP 地址。  
  
5.  %Userprofile%\SecurityScans 目录中复制每个安全报告 （.mbsa 文件）。  
  
### <a name="run-the-biztalk-server-best-practices-analyzer"></a>运行 BizTalk Server 最佳实践分析工具  
 请执行以下步骤来运行 BizTalk Server 最佳做法分析器：  
  
1.  下载[BizTalk Server 的最佳做法分析器 v1.2](http://go.microsoft.com/fwlink/?LinkID=83317) (http://go.microsoft.com/fwlink/?LinkID=83317)。  
  
2.  使用 BizTalk Server 管理员安全组的成员的用户帐户，登录到 BizTalk Server 节点。  
  
3.  在当前计算机上安装 BizTalk Server Best Practices Analyzer。  
  
4.  运行该工具并保存报表。  
  
### <a name="run-msinfo32-and-save-the-results"></a>运行 MSInfo32 并保存结果  
 请按照以下步骤来运行 MSInfo32 操作：  
  
1.  使用域或本地管理员帐户，登录到每个 BizTalk Server 和 SQL Server 计算机。  
  
2.  启动命令提示符处，并将目录更改到的计算机的 %windir%\system32 目录。  
  
3.  从命令提示符下运行 MSinfo32.exe。  
  
4.  单击**文件**菜单，然后选择**导出**菜单项以导出以保存计算机配置。  
  
### <a name="export-the-biztalk-server-and-sql-server-computer-tcpip-registry-setting-"></a>导出 BizTalk Server 和 SQL Server 计算机 TCP/IP 注册表设置-  
 请按照下列步骤以保存 BizTalk Server 和 SQL Server TCP/IP 注册表设置：  
  
1.  启动命令提示符处，并将目录更改到的计算机的 %windir%\system32 目录。  
  
2.  在命令提示符下运行 Regedit.exe。  
  
3.  导航到注册表中的以下项：  
  
    ```  
    [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters] (network settings)  
    ```  
  
4.  右键单击此项，然后选择**导出**将注册表项导出到文件。  
  
### <a name="collect-the-biztalk-configuration-files"></a>收集 BizTalk 配置文件  
 每个 BizTalk Server 在节点上，收集 BizTalk Server 配置文件中，BTSNTSvc.exe.config 文件 （或 BTSNTSvc64.exe.config 的 64 位主机），位于 BizTalk Server 安装文件夹 (例如 C:\Program Files\Microsoft BizTalk Server 2010)。  
  
### <a name="collect-the-net-configuration-files"></a>收集.NET 配置文件  
 每个 BizTalk Server 在节点上，收集在 machine.config 和 web.config 的.NET Framework 4.0 配置文件。 您可以在以下位置找到配置文件：  
  
-   适用于 32 位： %windir%\Microsoft.NET\Framework\v4.0.30319\CONFIG 文件夹  
  
-   对于 64 位： %windir%\Microsoft.NET\Framework64\v4.0.30319\CONFIG 文件夹  
  
### <a name="use-the-biztalk-msgboxviewer-tool-to-collect-information-about-the-messagebox-database"></a>使用 BizTalk MsgBoxViewer 工具收集有关 MessageBox 数据库的信息  
 请按照下列步骤来收集有关使用 BizTalk MsgBoxViewer 工具在 MessageBox 数据库信息：  
  
1.  下载[BizTalk MsgBoxViewer 工具](http://go.microsoft.com/fwlink/?LinkID=117289)(http://go.microsoft.com/fwlink/?LinkID=117289)。  
  
2.  登录到 BizTalk Server 管理员安全组的成员的用户帐户与 BizTalk Server 计算机上。  
  
3.  将 MsgBoxViewer.exe 复制到 BizTalk Server 计算机。  
  
4.  启动该工具。  
  
5.  单击**要收集的可选信息**选项卡，然后依次**选择的所有信息**。  
  
6.  单击**开始收集**。  
  
7.  状态标签将显示当**最终集合**消息，切换到包含 MsgBoxViewer.exe 可执行文件的文件夹和复制生成的报表 (.htm) 和日志文件。  
  
### <a name="collect-and-store-the-source-code-for-all-components-used-in-the-solution"></a>收集和存储解决方案中使用的所有组件的源代码  
 在单独的文件共享上存储的所有组件 （例如业务流程、 自定义管道组件和帮助程序组件代码） 的源代码。  
  
## <a name="initial-troubleshooting"></a>初始故障排除  
 不存在的 BizTalk Server 解决方案，如果未启用，将导致性能问题，而不考虑总大小的某些组件或 BizTalk 解决方案的设计。 排除具有吸引力的 BizTalk 解决方案的详尽瓶颈分析之前的"常见原因"一些，应完成以下初步故障排除任务。  
  
-   **验证是否正在运行的跟踪主机实例-** 跟踪主机实例是负责将 BAM 和 HAT 数据从 MessageBox 数据库的 TrackingData 表移至 BizTalkDTADb 和/或 BAMPrimaryImport 数据库表。 如果跟踪主机实例未运行，则跟踪数据将会在 MessageBox 数据库中累积并对 BizTalk Server 解决方案的性能产生负面影响。  
  
-   **验证企业单一登录 (ENTSSO) 服务是否正在运行所有 BizTalk Server 计算机-上**BizTalk 主机实例将保留 ENTSSO 服务的本地运行实例上的依赖项。 如果 ENTSSO 服务未运行 BizTalk Server 上，在服务器上的主机实例将无法运行。  
  
-   **验证 SQL Server 代理服务是否正在运行 SQL Server 的所有计算机的上**必须按顺序执行的 BizTalk SQL Server 代理作业运行 SQL Server 代理服务。 这些作业执行重要功能，以使服务器正常操作和运行。  
  
-   **验证 BizTalk SQL Server 代理作业是否已启用并运行而没有异常-** 即使 SQL Server 代理服务正在运行，也是强制性的所有默认 BizTalk SQL Server 代理作业启用并正在运行成功。  
  
-   **检查 BizTalk Server 和 SQL Server 事件日志-** 对 BizTalk Server 或 SQL Server 事件日志的粗略检查可能会泄漏，否则可能需要大量的时间以诊断并解决问题。  
  
-   **运行 BizTalk Server Best Practices Analyzer-** BizTalk Server Best Practices Analyzer 会检查 BizTalk Server 部署，并生成与最佳做法标准相关的问题的列表。 该工具通过不同的信息源，如 Windows Management Instrumentation (WMI) 类、 SQL Server 数据库和注册表项中的数据收集执行配置级别验证。 数据然后用于评估部署配置。 该工具读取和仅报告并不会修改任何系统设置，并不是一个自我调整工具。 下载 BizTalk Server 的最佳做法分析器从 v1.2 [BizTalk Server 的最佳做法分析器 v1.2](http://go.microsoft.com/fwlink/?LinkID=83317) (http://go.microsoft.com/fwlink/?LinkID=83317)。  
  
## <a name="high-level-system-bottlenecks"></a>高级系统瓶颈  
 本部分介绍可能会出现在 BizTalk Server 解决方案和可能的缓解策略的系统级瓶颈。  
  
### <a name="disk-io-bottlenecks"></a>磁盘 I/O 瓶颈  
 磁盘 I/O 是指读取和写入操作执行的物理磁盘上的应用程序或安装在服务器中的多个磁盘的数量。 可能会导致磁盘 I/O 和相关的瓶颈的常见活动包括长时间运行文件 I/O 操作、 数据加密和解密，从数据库表和足够的物理内存，这可能会产生了过度分页导致读取不必要的数据活动。 磁盘速度是评估磁盘 I/O 瓶颈; 时要考虑的另一个因素更快速的磁盘提供更高的性能并帮助减少磁盘 I/O 瓶颈。  
  
 下表提供了规划 BizTalk Server 解决方案的磁盘子系统时应考虑的因素。  
  
|磁盘子系统身份|详细信息|  
|---------------------------|-------------|  
|磁盘内存缓存和可用物理内存|由于内存缓存到磁盘的物理内存变得有限，因此请确保有足够的可用内存。 内存不足时，编写更多的页面到磁盘，从而导致增加的磁盘活动。 此外，请确保将页面文件设置为适当的大小。 更多的磁盘内存缓存可帮助在磁盘 I/O 请求中的偏移量的高峰。 但是，但应注意的大型磁盘内存缓存很少能解决问题没有足够的心轴，并具有足够的心轴可以不用为大规模的磁盘内存缓存。 有关配置 Windows 页面文件以获得最佳性能的信息，请参阅主题中的"配置 Windows 页面文件以获得最佳性能"一节[优化操作系统性能](~/technical-guides/optimizing-operating-system-performance.md)。|  
|存储控制器类型|如果你有电池供电的缓存，启用写入缓存以提高数据库卷和事务日志文件卷上的磁盘写入性能。 写入缓存提供的响应时间是 2 毫秒的写入 I/O 请求，而不是 10 到 20 毫秒，而无需启用写入缓存的响应时间。 启用写入缓存极大地提高了客户端写入请求的响应能力。 读取缓存无法提高在 BizTalk Server 方案的性能，因为它才有用实现顺序磁盘读取，只发生在事务日志文件。<br /><br /> 仅当它们播放时从读取事务日志文件，此类后将数据库还原或的服务器时未正确关闭。 更大的缓存允许更多的数据进行缓冲，这意味着可以容纳的饱和度值更长时间。 如果你的控制器允许你配置的缓存页大小，应将其设置为 4 KB。 更大的大小，例如 8 KB，会导致缓存浪费，因为 4 KB 的 I/O 请求将占用整个缓存页 8 kb，从而导致在可用缓存减少一半。|  
|心轴|轴是比容量，更重要，如果轴支持大量的随机 I/O 请求的 BizTalk Server 性能得到改进。 规划不超过 80%的总利用率，以确保足够的 I/O 可用，甚至在心轴出现故障的情况下。|  
|Raid|所用的 RAID 解决方案应基于成本和性能之间做出取舍适用于你的环境。 因此，可能会为特定的数据存储要求建议的 RAID 解决方案的多个类型。 一般建议是，如下所示：<br /><br /> -使用 Raid-1 + 0 为 BizTalk Server 数据库 （镜像组中的带区集）。<br />-对于事务日志文件卷使用 Raid 1 （无奇偶校验的镜像集）。<br />-在一般情况下，不建议 Raid 5 （带分布式奇偶校验的带区集），如 Raid 5 不提供最佳的可靠性、 可用性和性能相比其他 Raid 配置。<br />-由于向可能的数据永久丢失，永远不应在 BizTalk Server 生产环境中使用 Raid 0 （无奇偶校验的带区集） 配置。|  
|总线类型|更高的吞吐量提供了更好的性能。 一般情况下，SCSI 总线提供了更好的吞吐量和可伸缩性，比 IDE 或 ATA 总线。 下面的公式可用于确定理论上的吞吐量限制为你的总线类型：<br /><br /> (总线速度 （以位为单位） / 8 位 / 字节)X 操作系统速度 （以 mhz 为单位） = 吞吐量 （以 MB/秒）<br /><br /> 此外可以通过将多个驱动器放置在单独 I/O 总线上提高磁盘 I/O 性能。|  
  
#### <a name="performance-counters-for-measuring-disk-io-bottlenecks"></a>衡量磁盘 I/O 瓶颈的性能计数器  
  
> [!NOTE]
>  在尝试分析磁盘性能瓶颈时，应始终使用物理磁盘计数器。 但是，如果你使用软件 RAID，应使用逻辑磁盘计数器。 逻辑磁盘和物理磁盘计数器，在每个计数器对象提供了相同的计数器。 逻辑磁盘数据跟踪的卷管理器 （或经理） 和物理磁盘数据跟踪的分区管理器。  
  
 应使用以下性能计数器以确定您的系统是否遇到磁盘 I/O 相关的瓶颈：  
  
-   **PhysicalDisk\Avg.磁盘队列长度**  
  
    -   阈值：不应大于心轴数加两个。  
  
    -   重要性：此计数器指示的这两个读取的平均数目，并将采样间隔期间为所选磁盘排队的请求。 此计数器可用于收集并发数据，包括数据激增，峰值负载。 这些值表示正在进行下面执行统计信息的驱动程序的请求数。 这意味着请求不一定排队，但实际上可能是在服务中或已完成并的方式将备份路径。 可能正在进行的位置包括：  
  
        -   SCSIport 或 Storport 队列  
  
        -   OEM 驱动程序队列  
  
        -   磁盘控制器队列  
  
        -   硬盘队列  
  
        -   主动接收从硬盘  
  
-   **PhysicalDisk\Avg.磁盘读取队列长度**  
  
    -   阈值：应为不超过两个。  
  
    -   重要性：此计数器指示在采样间隔期间为所选磁盘排队的读取请求的平均数。  
  
-   **PhysicalDisk\Avg.磁盘写入队列长度**  
  
    -   阈值：应为不超过两个。  
  
    -   重要性：此计数器指示在采样间隔期间为所选磁盘排队的写入请求的平均数。  
  
-   **PhysicalDisk\Avg.Disk sec/Read**  
  
    -   阈值：没有特定的值。  
  
        -   小于 10 毫秒 (ms) = 状态良好  
  
        -   15 和 25 毫秒之间 = 公平  
  
        -   大于 25 毫秒 = 差  
  
    -   重要性：此计数器表示的平均时间，以秒为单位从磁盘读取操作的数据。 如果数字大于 25 毫秒 (ms)，这意味着磁盘系统从磁盘读取时遇到延迟。 对于关键任务服务器承载 BizTalk Server，可接受的阈值是低得多，大约 10 毫秒。  
  
-   **PhysicalDisk\Avg.Disk sec/Write**  
  
    -   阈值：没有特定的值。  
  
        -   小于 10 毫秒 (ms) = 状态良好  
  
        -   15 和 25 毫秒之间 = 公平  
  
        -   大于 25 毫秒 = 差  
  
    -   重要性：此计数器表示的平均时间，以秒为单位，数据的向磁盘写入操作。 如果数字大于 25 ms，磁盘系统发生了延迟时写入的磁盘。 对于关键任务服务器承载 BizTalk Server，可接受的阈值是低得多，大约 10 毫秒。  
  
-   **PhysicalDisk\Avg.Disk sec/Transfer**  
  
    -   阈值：不应超过 18 个毫秒为单位。  
  
    -   重要性：此计数器表示的时间，以秒为单位的平均磁盘传输的。 这可能指示大量的磁盘碎片、 慢速磁盘或磁盘故障。 将的值相乘**Physical disk\avg.Disk sec/Transfer**并**Memory\Pages/sec**计数器。 如果这些计数器的乘积超过 0.1，表示分页占用了超过 10%的磁盘访问时间，因此您需要更多的物理内存可用。  
  
-   **PhysicalDisk\Disk Writes/sec**  
  
    -   阈值：依赖于制造商的规范。  
  
    -   重要性：此计数器表示磁盘上的写入操作的速率。  
  
-   **处理器\\%DPC Time、 %Interrupt Time 和 %Privileged Time-** 如果 Interrupt Time 和延迟过程调用 (DPC) 时间会有很大一部分 Privileged Time、 内核花费大量时间处理 I/O 请求。 在某些情况下，通过在多处理器系统上配置中断和 DPC 关联为很小的 Cpu 可以提高性能，这可以提高缓存区域。 在其他情况下，它最适合分配中断和 Dpc 在多个 Cpu，以便防止中断和 DPC 活动成为性能瓶颈。 使用中断筛选器配置工具以将网络适配器中断绑定到多处理器计算机上的特定处理器的信息，请参阅"使用中断筛选器配置工具以将网络适配器中断绑定到特定的部分多处理器计算机上的"中处理器[优化操作系统性能](~/technical-guides/optimizing-operating-system-performance.md)。  
  
-   **Processor\DPCs 排队数 / 秒-** 测量如何 Dpc 正在占用 CPU 时间和内核资源。  
  
-   **Processor\Interrupts 数 / 秒-** 另一个度量值的方式中断正在占用 CPU 时间和内核资源。 现代的磁盘控制器通常组合或 coalesce 中断，以便单个中断导致的多个 I/O 完成处理。 当然，没有延迟中断 （和完成项） 和 economizing CPU 处理时间之间进行权衡。  
  
#### <a name="disk-io-tuning-options"></a>磁盘 I/O 优化选项  
 如果你确定磁盘 I/O 是您的环境中的瓶颈，可能使用以下方法来缓解瓶颈：  
  
-   **对你的磁盘-进行碎片整理**使用在可用[PageDefrag 实用程序](http://go.microsoft.com/fwlink/?LinkId=108976)(http://go.microsoft.com/fwlink/?LinkId=108976)进行碎片整理 Windows 分页文件和预分配主文件表。  
  
-   **使用条带集的多个磁盘的同时处理 I/O 请求**使用镜像的卷提供容错并提高 I/O 性能。 如果不需要容错能力，用于实现带区集快速读取和写入和改进的存储容量。 当使用带区集时，每个磁盘利用率被减少，因为工作分布在卷，并增加整体吞吐量。 如果您根据需要添加更多的磁盘的条带中设置您的系统可能会遇到瓶颈，因为由磁盘控制器的磁盘之间的争用则不会增加吞吐量。 在这种情况下，将添加一个额外的磁盘控制器将有助于分散负载并提高性能。  
  
-   **将分发在多个驱动器的工作负荷**Windows 群集和分布式文件系统提供的多个磁盘驱动器进行负载均衡解决方案。  
  
-   **限制使用文件压缩或加密-** 文件压缩和加密是 O 密集型操作。 仅应使用它们在绝对必要时。  
  
-   **禁用的短名称-创建**如果你不支持 MS-DOS 的 Windows 3.x 客户端，则禁用短名称，以提高性能。 有关禁用的短名称创建的详细信息，请参阅"禁用短文件名 (8.3) 生成"一节中[优化操作系统性能](~/technical-guides/optimizing-operating-system-performance.md)。  
  
-   **禁用最后一次访问更新-** 默认情况下，NTFS 更新目录的上次访问日期和时间戳，每当该代码遍历目录。 对于大型的 NTFS 卷，此更新过程可能会降低性能。 有关禁用上次访问更新的详细信息，请参阅部分中的"禁用 NTFS 上次访问更新"[优化操作系统性能](~/technical-guides/optimizing-operating-system-performance.md)。  
  
    > [!CAUTION]
    >  某些应用程序，例如增量备份实用程序，依赖于 NTFS 更新信息并没有它将无法正常工作。  
  
-   **保留相应的主文件表中的空间**外**NtfsMftZoneReservation**具体通常存储在 NTFS 卷的文件数取决于注册表项。 时将此条目添加到注册表时，系统将保留主文件表的卷上的空间。 保留空间以这种方式允许以最佳方式增长的主文件表。 如果你的 NTFS 卷通常存储相对几个文件，将此注册表项的值设置为默认值为 1。 通常，如果 NTFS 卷存储适中数量的文件，并使用值为 4 （最大），如果 NTFS 卷往往包含相对较大文件数，您可以使用值为 2 或 3。 但是，请确保用于测试大于 2，任何设置，因为这些更高的值会导致系统保留更大一部分的主文件表的磁盘。 有关添加详细信息**NtfsMftZoneReservation**到注册表，请参阅部分"增加中的可用空间的主文件表"[优化操作系统性能](~/technical-guides/optimizing-operating-system-performance.md)。  
  
-   **使用可用的最有效的磁盘系统**除了使用的物理磁盘，请考虑将使用的磁盘控制器和电缆线路类型。 有效的磁盘子系统还应提供支持中断裁决或中断避免来缓解引起的磁盘 I/O 处理器中断活动的驱动程序。  
  
-   **确保使用适当的 RAID 配置-** 使用 RAID 10 （条带化和镜像） 的最佳性能和容错能力。 其不利的一面是，使用 RAID 10 是昂贵。 避免使用 RAID 5 具有大量写入操作时。 有关在 BizTalk Server 环境中实现 RAID 的详细信息，请参阅"磁盘基础结构"一节中[BizTalk Server 数据库优化白皮书](http://go.microsoft.com/fwlink/?LinkID=101578)(http://go.microsoft.com/fwlink/?LinkID=101578)。  
  
-   **请考虑使用数据库分区-** 如果数据库瓶颈，请考虑使用数据库的分区，并将磁盘映射到特定的表和事务日志。 分区的主要目的是解决大型表的磁盘瓶颈。 如果具有大量的行的表，并且你确定它是瓶颈的根源，请考虑使用分区。 对于 SQL Server，可以使用文件组来提高 I/O 性能。 可以将表与文件组相关联，然后将文件组具有特定硬盘相关联。 有关使用 BizTalk Server 数据库的优化文件组的详细信息，请参阅[优化文件组的数据库](~/technical-guides/optimizing-filegroups-for-the-databases2.md)。  
  
-   **请考虑添加物理内存，如果有过多的页面错误-** 的较高值**内存：每秒页数**性能计数器表示这会增加磁盘过多分页我 / 0。 如果发生这种情况，请考虑添加物理内存来减少磁盘 I/O 和提高性能。  
  
-   **请考虑使用更高版本的 RPM 评估或使用存储区域网络 (SAN) 中使用的磁盘设备-** RPM 评级更高的磁盘提供改进的性能与较低的 RPM 分级对磁盘进行比较。 SAN 设备通常提供顶层的性能，但在价格优惠。  
  
-   请按照中的建议[优化数据库性能](~/technical-guides/optimizing-database-performance.md)。 本主题提供有关优化数据库性能之前和之后配置 BizTalk Server 的多个建议。  
  
### <a name="cpu-bottlenecks"></a>CPU 瓶颈  
 在服务器运行每个应用程序获取 CPU 时间的切片。 CPU 可能能够有效地处理所有的计算机上，运行的进程或可能超载。 通过检查处理器活动和活动的单独进程包括创建线程、 线程切换和上下文切换，您可以深入了解处理器工作负荷和性能。  
  
#### <a name="you-may-have-a-cpu-bottleneck-if"></a>如果，可能出现了 CPU 瓶颈...  
  
-   值**处理器\\%Processor Time**性能计数器通常超过 75%。  
  
-   值**System\ Processor Queue Length**性能计数器为 2 或更多的时间段。  
  
-   值**处理器\\%特权时间**或**System\Context Switches/sec**都非常高的性能计数器。  
  
     如果的值**Processor\ %Processor Time**性能计数器值较高，则会出现队列，并在大多数情况下的值**System\ Processor Queue Length**也很高。  
  
#### <a name="performance-counters-for-measuring-cpu-bottlenecks"></a>用于测量 CPU 瓶颈的性能计数器  
 应使用以下性能计数器以确定您的系统是否遇到 CPU 相关的瓶颈：  
  
-   **处理器\\处理器时间百分比**  
  
    -   阈值：应为小于 85%。  
  
    -   重要性：此计数器是处理器活动的主要指示器。 很多的较高值不一定是错误。 但是，如果越来越多的其他与处理器相关的计数器以线性方式如下所述**处理器\\%特权时间**或**System\Processor Queue Length**，高 CPU 利用率可能值得调查。  
  
-   **处理器\\%特权时间**  
  
    -   阈值：始终大于 75%图指示了瓶颈。  
  
    -   重要性：此计数器指示线程在特权模式下运行的时间的百分比。 当你的应用程序调用时 （例如，可执行文件或网络 I/O 或分配内存） 的操作系统功能时，这些操作系统函数在特权模式下执行。  
  
-   **处理器\\中断时间百分比**  
  
    -   阈值：取决于处理器。  
  
    -   重要性：此计数器表示处理器用于接收和服务硬件中断的时间百分比。 此值是活动的生成中断，例如网络适配器的设备的间接指示器。 显著提高此计数器指示潜在硬件问题。  
  
-   **System\Processor Queue Length**  
  
    -   阈值：平均值始终高于 2 指示瓶颈。  
  
    -   重要性：如果有更多的任务准备好运行比处理器，线程排队等候。 处理器队列是准备就绪，但不能由处理器执行，因为另一个线程当前正在执行的线程的集合。 两个以上的线程的持续或重复发生队列是明确表示处理器瓶颈。 通过减少并行度，在这些情况下，可能会收到更大的吞吐量。  
  
         可以结合使用此计数器**处理器\\%Processor Time**计数器以确定你的应用程序可以受益更多的 Cpu。 没有单个队列的处理器时间，即使在多处理器计算机上。 因此，在多处理器计算机中，除以处理器队列长度 (PQL) 值的处理工作负载的处理器数。  
  
         如果 CPU 非常忙 （90%或更高的利用率） 且 PQL 平均值高于一致地为每个处理器的 2，可能存在处理器瓶颈，可受益于添加 Cpu。 或者，你可能会减少线程和队列应用程序级别的更多的数量。 这会减少上下文切换中，适用于减少 CPU 负载，从而减少上下文切换。 PQL 值为 2 或更高 CPU 使用率低下的常见原因是对处理器时间的请求到达随机和线程需要不定期大量处理器时间。 这意味着处理器不是瓶颈，但应改进应用程序的线程逻辑。  
  
-   **System\Context Switches/sec**  
  
    -   阈值：作为一般规则，上下文切换速率小于每个处理器每秒 5,000 是不值得担心。 如果上下文切换的速率超过 15,000 每个处理器每秒，然后上下文切换可能成为瓶颈。  
  
    -   重要性：较高优先级线程抢先于较低的优先级线程当前正在运行或较高优先级的线程时阻止其他线程时，会发生上下文切换。 当多个线程共享相同的优先级别，会发生上下文切换的高级别。 这通常表示有过多的线程在系统上处理器的竞争。 如果处理器利用率和上下文切换级别较低，这通常是指示线程被阻止。  
  
#### <a name="resolving-cpu-bottlenecks"></a>解决 CPU 瓶颈  
 第一步是确定哪些进程正在消耗过多的处理器时间。 使用 Windows**任务管理器**若要确定哪个进程正在消耗大量 CPU 通过查看**CPU**上的列**进程**页。 您还可以通过监视来确定这**进程\\%Processor Time**性能监视器并选择你想要监视的进程中。  
  
 确定哪些进程正在消耗过多的 CPU 时间的另一种功能强大的工具是 Visual Studio Team System Profiler 提供使用 Visual Studio Team System (VSTS) 套件。 有关使用 Visual Studio Team System Profiler 的详细信息，请参阅 Visual Studio Team System 文档。  
  
 确定你的 CPU 是瓶颈后有多个选项，包括以下：  
  
-   如果有多线程应用程序，添加多个处理器。 请考虑升级到更强大的处理器，如果你的应用程序是单线程。  
  
-   如果发现上下文切换的速率很高，请考虑增加的处理器数之前减少您的进程的线程计数。  
  
-   分析和优化会导致高 CPU 使用率的应用程序。 可以通过使用 ADPLUS 实用程序来转储正在运行的进程，并使用 Windbg 分析原因。 这些实用程序是 Windows 调试工具包的一部分。 您可以下载这些工具从[有关 Windows 调试工具](http://go.microsoft.com/fwlink/?LinkID=106624)(http://go.microsoft.com/fwlink/?LinkID=106624)。  
  
-   分析检测日志生成的应用程序隔离正在执行的时间的最长的子系统。 确定是否可能更有利比只优化 BizTalk Server 环境的代码评审。  
  
> [!NOTE]
>  尽管您可以通过更改应用程序的进程优先级级别**任务管理器**或从命令提示符下，通常应避免这样做。  
  
### <a name="memory-bottlenecks"></a>内存瓶颈  
 评估时与内存相关的瓶颈，请考虑不必要的分配、 清理、 效率低且不适合缓存和状态管理机制。 若要解决与内存相关的瓶颈，优化您的代码以消除这些问题，然后调整分配给你的应用程序的内存量。 如果你确定在优化期间发生内存争用和分页过多，可能需要向服务器添加额外的物理内存。 内存不足会导致增加对的应用程序的虚拟地址空间与磁盘进行分页。 如果分页变得过多，磁盘 I/O 将增加，并对总体系统性能产生负面影响。  
  
#### <a name="you-might-have-a-memory-bottleneck-if"></a>如果，则可能存在内存瓶颈...  
  
-   值**Memory\Available MBytes**性能计数器较低，是由于系统内存限制或没有释放内存的应用程序。 监视的值**进程 \ 工作集**运行每个进程的性能计数器。 如果值为**进程 \ 工作集**高即使进程未处于活动状态，这可能表示该过程没有释放内存，它应该保持。  
  
-   值**Memory\Pages/sec**性能计数器值较高。 平均值**Memory\Pages Input/sec**除以的平均值**Memory\Page Reads/sec**提供的每磁盘读取的页数。 此值不应通常超过每秒 5 个页面。 大于每秒 5 个页面的值指示系统花费太多时间分页，并且需要更多的内存 （假设已优化应用程序）。  
  
#### <a name="performance-counters-for-measuring-memory-bottlenecks"></a>用于测量内存瓶颈的性能计数器  
 应使用以下性能计数器以确定您的系统是否遇到内存相关的瓶颈：  
  
-   **Memory\Available Mbytes**  
  
    -   阈值：小于 20 到 25%的已安装的 RAM 的一致的值是相对值的指示内存不足。  
  
    -   重要性：这表示可在计算机上运行的进程的物理内存量。 请注意，此计数器显示上次观测的值仅。 它不是平均值。  
  
-   **Memory\Page Reads/sec**  
  
    -   阈值：持续的五个值表示大量的读取请求的页面错误。  
  
    -   重要性：此计数器指示进程的工作集太大，这会导致内存分页到磁盘的可用物理内存。 它显示读取操作，而不考虑在每个操作中检索到的页面数数。 较高的值指示内存瓶颈。  
  
         较低的页读取操作率是否与高值**物理磁盘\\%Disk Time**和**Physical disk\avg.磁盘队列长度**，磁盘 I/O 瓶颈条件可能会存在。 如果页面读取速率降低不附带的队列长度的增加，内存瓶颈存在物理内存不足。  
  
-   **Memory\Pages/sec**  
  
    -   阈值：持续超过五个值表示瓶颈。  
  
    -   重要性：此计数器表示读取或写入磁盘为解决强制分页错误页的速率。 将的值相乘**Physical disk\avg.Disk sec/Transfer**并**Memory\Pages/sec**性能计数器。 如果这些值的乘积超过**0.1**，分页利用多个磁盘访问时间，表示有足够的物理内存的 10%。  
  
-   **Memory\Pool Nonpaged 的 Bytes**  
  
    -   阈值：观看的值**Memory\Pool Nonpaged Bytes**的 10%或更多在系统启动时其值的增加。  
  
    -   重要性：增加 10%或更多在启动时的值可能指示内存泄漏。  
  
-   **Server\Pool Nonpaged 的失败**  
  
    -   阈值：正则非零值指示的瓶颈。  
  
    -   重要性：此计数器表示从非分页池的分配失败次数。 非分页池包含从进程的虚拟地址空间不会换出到磁盘，如处理内核对象表上的页面文件的页。 非分页池的可用性确定多少进程、 线程和其他可以创建此类对象。 当从非分页池的分配失败时，这可能导致内存泄漏在进程中，尤其是当未相应地增加处理器使用情况。  
  
-   **Server\Pool 分页失败**  
  
    -   阈值：没有特定的值。  
  
    -   重要性：此计数器表示从页面缓冲池的分配失败次数。 此计数器为正值这表明计算机具有足够的物理内存或 Windows 分页文件太小。  
  
-   **Server\Pool Nonpaged 的峰值**  
  
    -   阈值：没有特定的值。  
  
    -   重要性：这是最大中服务器保留在任何点使用的非分页池字节数。 它指示计算机应该具有的物理内存量。 因为非分页池必须是驻留在物理内存，因为必须有留下的其他操作，作为经验法则计算机部分内存应已安装物理内存，这是此计数器指示值的 4 倍。  
  
-   **Memory\Cache Bytes**  
  
    -   阈值：没有特定的值。  
  
    -   重要性：监视在不同的负载条件下的缓存的大小。 此性能计数器的此值指示静态文件缓存的大小。 默认情况下，此计数器使用大约 50%的可用内存，但减少，如果可用内存逐渐缩小，这会影响系统性能。  
  
-   **Memory\Cache Faults/sec**  
  
    -   阈值：没有特定的值。  
  
    -   重要性：此计数器表示何种频率操作系统查找文件系统缓存中的数据，但无法找到它。 此值应尽可能低。  
  
-   **Cache\MDL 读取命中 %**  
  
    -   阈值：较高这价值，文件系统缓存的性能就越好。 值应接近 100%尽可能。  
  
    -   重要性：此计数器提供百分比的内存描述符列表 (MDL) 读取文件系统缓存，其中缓存返回的对象直接请求，而无需从硬盘读取。  
  
-   **Process\Working Set**  
  
    -   阈值：没有特定的值。  
  
    -   重要性：工作集是当前加载到内存 （物理和虚拟） 中的内存页的集合。 如果系统有足够的内存，它可以维护足够的空间中的工作集，以便它不需要执行将内存分页到磁盘的磁盘操作。 但是，如果没有足够的内存，系统会尝试减少工作集中的灵活度从进程的内存，这会导致页错误的增加。 当页面错误的速率增加时，系统会尝试增加进程工作集。 如果你观察宽波动的工作集，则可能指示内存不足。 更高版本中的工作集值也可能是由于应用程序中的多个程序集。 您可以提高工作集通过使用在全局程序集缓存中共享的程序集。  
  
#### <a name="resolving-memory-bottlenecks"></a>解决内存瓶颈  
 如果确定该内存是在 BizTalk Server 环境中，使用一个或多个以下方法来解决瓶颈的瓶颈：  
  
-   优化分配如果您可以控制分配的内存量。 例如，您可以调整此 BizTalk Server、 ASP.NET 和 SQL Server。  
  
-   Windows 页面文件的大小增加，并按照中的"配置 Windows 页面文件以获得最佳性能"部分的步骤[优化操作系统性能](~/technical-guides/optimizing-operating-system-performance.md)。  
  
-   关闭未使用的服务。 停止不经常使用的服务节省内存并提高系统性能。 有关详细信息，请参阅的"禁用不必要的服务"部分[优化操作系统性能](~/technical-guides/optimizing-operating-system-performance.md)。  
  
-   删除不必要的协议和驱动程序。 甚至空闲协议使用中的分页和非分页内存池空间。 驱动程序还使用内存，因此应删除不必要的。 有关详细信息，请参阅的"删除不必要的网络协议"部分[优化操作系统性能](~/technical-guides/optimizing-operating-system-performance.md)。  
  
-   在 BizTalk Server 环境中的计算机上安装额外的物理内存。  
  
> [!NOTE]
>  在 32 位系统上，BizTalk 可使用的最大 2 gb 的内存，如果使用 /3GB 开关，则将限制增加到 3 GB，BizTalk Server 2010 和更高版本。 有关内存使用情况的详细信息，请参阅[Windows 版本的内存限制](http://go.microsoft.com/fwlink/?LinkId=118349)(http://go.microsoft.com/fwlink/?LinkId=118349)。  
  
### <a name="network-io-bottlenecks"></a>网络 I/O 瓶颈  
  
#### <a name="you-might-have-a-network-io-bottleneck-if"></a>如果，则可能存在网络 I/O 瓶颈...  
  
-   值**Network Interface\Bytes Total/sec**性能计数器超过 80%的可用网络带宽。  
  
-   值**Server\Bytes Total/sec**性能计数器大于 50%的可用网络带宽。  
  
#### <a name="performance-counters-for-measuring-network-io-bottlenecks"></a>用于测量网络 I/O 瓶颈的性能计数器  
 应使用以下性能计数器来测量网络 I/O 和确定系统是否遇到了网络 I/O 相关的瓶颈：  
  
-   **Network Interface\Bytes Total/sec**  
  
    -   阈值：持续的 80%以上的网络容量值。  
  
    -   重要性：此计数器表示发送和每个网络适配器上接收字节的速率。 此计数器可帮助确定网络适配器处于满负荷状态以及是否应将添加一个或多个网络适配器，以增加可用的网络带宽。  
  
-   **Network Interface\Bytes Received/sec**  
  
    -   阈值：没有特定的值。  
  
    -   重要性：此计数器指示每个网络适配器上接收字节的速率。 使用此计数器的值来计算总的可用带宽的百分比的传入数据的速率。 这将有助于确定是否在客户端将数据发送到 BizTalk Server 或如果应在 BizTalk Server 计算机本身上增加网络带宽，则应增加网络带宽。  
  
-   **Network Interface\Bytes Sent/sec**  
  
    -   阈值：没有特定的值。  
  
    -   重要性：此计数器指示每个网络适配器上发送字节的速率。 使用此计数器的值来计算总的可用带宽的百分比的传出数据的速率。 这将有助于确定是否应在 BizTalk Server 将数据发送到客户端上提高网络带宽，或从 BizTalk Server 的客户端计算机接收数据，则应增加网络带宽。  
  
-   **Server\Bytes Total/sec**  
  
    -   阈值：持续的数超过 50%的网络容量。  
  
    -   重要性：此计数器表示发送和通过网络接收的字节数。 较高的值指示网络 I/O 瓶颈。 如果总和**Bytes Total/sec**为与你的网络的最大传输速率大致相同的所有服务器，请考虑子网的网络，以提高性能。 有关子网的网络，以提高性能的详细信息，请参阅**子网**一部分[BizTalk Server 数据库优化白皮书](http://go.microsoft.com/fwlink/?LinkID=101578)(http://go.microsoft.com/fwlink/?LinkID=101578)。  
  
#### <a name="resolving-network-io-bottlenecks"></a>解决网络 I/O 瓶颈  
 如果您确定网络 I/O 是您的环境中的瓶颈，请使用一个或多个以下方法来解决瓶颈问题：  
  
-   请遵循中的"提高网络性能的常规指南"部分建议[优化网络性能](~/technical-guides/optimizing-network-performance.md)。  
  
-   运行 Windows Powershell 网络优化脚本主题所述[优化网络性能](~/technical-guides/optimizing-network-performance.md)BizTalk Server 环境中的每台计算机上。  
  
## <a name="see-also"></a>请参阅  
 [查找并消除瓶颈](~/technical-guides/finding-and-eliminating-bottlenecks.md)