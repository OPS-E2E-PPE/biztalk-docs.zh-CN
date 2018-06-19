---
title: 系统级瓶颈 |Microsoft 文档
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
ms.openlocfilehash: 058fd60e1c38a3045197b4a36bdcc81250ab5be5
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
ms.locfileid: "22302981"
---
# <a name="system-level-bottlenecks"></a>系统级瓶颈
本主题介绍如何解决常见的系统级瓶颈，从而可以影响 BizTalk Server 解决方案的性能。  
  
## <a name="creating-a-snapshot-of-the-baseline-configuration"></a>创建基线配置的快照  
 收集以下信息可以提供可用于帮助在更正系统级瓶颈的基线配置的快照。  
  
### <a name="gather-documentation"></a>收集文档  
 查看的体系结构和方案的基础结构的文档。  
  
### <a name="run-the-baseline-security-analyzer"></a>运行基准安全分析器  
 请执行以下步骤来运行基准安全分析器：  
  
1.  下载[Microsoft Baseline Security Analyzer 2.2](http://go.microsoft.com/fwlink/?LinKID=204006) (http://go.microsoft.com/fwlink/?LinkId=204006)。  
  
2.  使用域管理员帐户，登录到承载 BizTalk Server 和 SQL Server 计算机相同网络上的计算机。  
  
3.  在当前计算机 （例如，一个 BizTalk Server 计算机或单独计算机） 上安装 Microsoft Baseline Security Analyzer。  
  
4.  执行单独的扫描 (**启动扫描**)，作为参数指定的名称或每个 BizTalk Server 和 SQL Server 计算机的 IP 地址。  
  
5.  %Userprofile%\SecurityScans 目录中复制每个安全报告 （.mbsa 文件）。  
  
### <a name="run-the-biztalk-server-best-practices-analyzer"></a>运行 BizTalk Server 最佳做法分析器  
 请执行以下步骤来运行 BizTalk Server 最佳做法分析器：  
  
1.  下载[BizTalk Server 最佳做法分析器 v1.2](http://go.microsoft.com/fwlink/?LinkID=83317) (http://go.microsoft.com/fwlink/?LinkID=83317)。  
  
2.  使用 BizTalk Server 管理员安全组的一部分的用户帐户，登录到 BizTalk Server 节点。  
  
3.  在当前计算机上安装 BizTalk Server 最佳做法分析器。  
  
4.  运行该工具，并将保存报表。  
  
### <a name="run-msinfo32-and-save-the-results"></a>运行 MSInfo32 并保存结果  
 请按照以下步骤来运行 MSInfo32 操作：  
  
1.  使用域或本地管理员帐户，登录到每个 BizTalk Server 和 SQL Server 计算机。  
  
2.  启动命令提示符，并将目录更改为计算机的 %windir%\system32 目录。  
  
3.  从命令提示符运行 MSinfo32.exe。  
  
4.  单击**文件**菜单，然后选择**导出**菜单项以导出以保存计算机配置。  
  
### <a name="export-the-biztalk-server-and-sql-server-computer-tcpip-registry-setting-"></a>导出的 BizTalk Server 和 SQL Server 的计算机 TCP/IP 注册表设置-  
 请按照下列步骤以保存 BizTalk Server 和 SQL Server TCP/IP 注册表设置：  
  
1.  启动命令提示符，并将目录更改为计算机的 %windir%\system32 目录。  
  
2.  从命令提示符运行 Regedit.exe。  
  
3.  导航到注册表中的以下项：  
  
    ```  
    [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters] (network settings)  
    ```  
  
4.  右键单击此项，然后选择**导出**将注册表项导出到文件。  
  
### <a name="collect-the-biztalk-configuration-files"></a>收集 BizTalk 配置文件  
 在 BizTalk Server 每个节点上，收集 BizTalk Server 配置文件、 BTSNTSvc.exe.config 文件 （或 64 位主机 BTSNTSvc64.exe.config），位于 BizTalk Server 安装文件夹 (例如 C:\Program Files\Microsoft BizTalk Server 2010)。  
  
### <a name="collect-the-net-configuration-files"></a>收集.NET 配置文件  
 在 BizTalk Server 每个节点上，收集 machine.config 和 web.config.NET Framework 4.0 的配置文件。 你可以在以下位置找到配置文件：  
  
-   适用于 32 位： %windir%\Microsoft.NET\Framework\v4.0.30319\CONFIG 文件夹  
  
-   适用于 64 位： %windir%\Microsoft.NET\Framework64\v4.0.30319\CONFIG 文件夹  
  
### <a name="use-the-biztalk-msgboxviewer-tool-to-collect-information-about-the-messagebox-database"></a>使用 BizTalk MsgBoxViewer 工具来收集有关 MessageBox 数据库的信息  
 请按照下列步骤来收集有关 MessageBox 数据库使用 BizTalk MsgBoxViewer 工具的信息：  
  
1.  下载[BizTalk MsgBoxViewer 工具](http://go.microsoft.com/fwlink/?LinkID=117289)(http://go.microsoft.com/fwlink/?LinkID=117289)。  
  
2.  登录到 BizTalk Server 计算机时使用的是 BizTalk 服务器管理员安全组的一部分的用户帐户。  
  
3.  将 MsgBoxViewer.exe 复制到 BizTalk Server 计算机。  
  
4.  启动该工具。  
  
5.  单击**要收集的可选信息**选项卡上，并依次**选择的所有信息**。  
  
6.  单击**开始收集**。  
  
7.  当状态标签会显示**结束集合**消息，切换到包含 MsgBoxViewer.exe 可执行文件的文件夹和复制生成的报表 (.htm) 和日志文件。  
  
### <a name="collect-and-store-the-source-code-for-all-components-used-in-the-solution"></a>收集和存储为解决方案中使用的所有组件的源代码  
 存储在单独的文件共享上的所有组件 （例如业务流程、 自定义管道组件和帮助程序组件代码） 的源代码。  
  
## <a name="initial-troubleshooting"></a>初始故障排除  
 如果未启用，将导致性能问题的总体大小无论的 BizTalk Server 解决方案的某些组件或 BizTalk 解决方案的设计有。 应完成以下初步的故障排除任务，以参与详尽瓶颈分析了 BizTalk 解决方案之前查看一些"常用怀疑"规则。  
  
-   **验证是否正在运行跟踪主机实例-** 跟踪主机实例负责将 BAM 和 HAT 数据从 MessageBox 数据库的 TrackingData 表移动到 BizTalkDTADb 和/或 BAMPrimaryImport 数据库表。 如果跟踪托管实例未运行，则跟踪数据将堆积在 MessageBox 数据库并对 BizTalk Server 解决方案的性能产生负面影响。  
  
-   **验证企业单一登录 (ENTSSO) 服务是否正在运行 BizTalk Server 的所有计算机的上**BizTalk 主机实例保留在本地运行的 ENTSSO 服务实例上的一个依赖项。 如果 ENTSSO 服务未运行 BizTalk Server 上，在服务器上的主机实例将无法运行。  
  
-   **验证 SQL Server 代理服务是否正在运行 SQL Server 的所有计算机的上**必须按顺序执行 BizTalk SQL Server 代理作业运行 SQL Server 代理服务。 这些作业执行重要的功能使你的服务器操作和正常运行。  
  
-   **验证已启用 BizTalk SQL Server 代理作业并正在运行并且无例外-** 即使正在运行的 SQL Server 代理服务，它是命令性的所有默认 BizTalk SQL Server 代理作业是否已启用并正在运行成功。  
  
-   **检查 BizTalk Server 和 SQL Server 事件日志-** BizTalk Server 或 SQL Server 事件日志的粗略检查可能会泄漏，否则可能也需要很长时间以诊断并解决问题。  
  
-   **运行 BizTalk Server 最佳做法分析器-** BizTalk Server 最佳做法分析器检查 BizTalk Server 部署，并生成与最佳做法标准相关的问题的列表。 该工具执行配置级别验证从不同的信息源，例如 Windows Management Instrumentation (WMI) 类、 SQL Server 数据库和注册表项收集数据。 数据然后用于评估部署配置。 该工具读取和仅限报告并不会修改任何系统设置，并不是自我调整工具。 下载 BizTalk Server 最佳做法分析器 v1.2 从[BizTalk Server 最佳做法分析器 v1.2](http://go.microsoft.com/fwlink/?LinkID=83317) (http://go.microsoft.com/fwlink/?LinkID=83317)。  
  
## <a name="high-level-system-bottlenecks"></a>高级系统瓶颈  
 本部分介绍可在 BizTalk Server 解决方案和可能的缓解措施策略中呈现的系统级瓶颈。  
  
### <a name="disk-io-bottlenecks"></a>磁盘 I/O 瓶颈  
 磁盘 I/O 是指的读取和写入操作执行的物理磁盘上的应用程序或安装在你的服务器的多个磁盘数。 可能会导致磁盘 I/O 和相关的瓶颈的常见活动包括长时间运行文件 I/O 操作、 数据加密和解密，从数据库表和足够的物理内存，这会导致过多分页读取不必要的数据活动。 磁盘速度时评估磁盘 I/O 瓶颈; 要考虑的另一个因素更快的磁盘提供更高的性能和减少磁盘 I/O 瓶颈。  
  
 下表提供了在规划磁盘子系统的 BizTalk Server 解决方案时应考虑的因素。  
  
|磁盘子系统因素|详细信息|  
|---------------------------|-------------|  
|磁盘内存缓存和可用的物理内存|由于内存缓存到磁盘的物理内存变得有限，因此请确保您具有足够的可用内存量。 内存不足时，多个页面写入到磁盘，从而导致增加的磁盘活动。 此外，请务必将分页文件设置为适当的大小。 更多的磁盘内存缓存将帮助磁盘输入/输出请求中的偏移量的峰值。 但是，它应注意，大容量磁盘内存缓存很少解决了不具有足够的心轴，问题，并具有足够的心轴可以不需要大容量磁盘内存缓存。 有关配置 Windows 页面文件以获得最佳性能的信息，请参阅主题中的"配置 Windows 页面文件以获得最佳性能"部分[优化操作系统性能](~/technical-guides/optimizing-operating-system-performance.md)。|  
|存储控制器类型|如果你有电池供电的缓存，启用写入缓存以提高磁盘写入性能的事务日志文件卷上和数据库卷上。 写入缓存提供的响应时间是 2 ms 对于写入 I/O 请求，而不是 10 到 20 毫秒，而无需启用写入缓存的响应时间。 启用写入缓存极大地提高客户端写入请求的响应能力。 读取缓存不改进在 BizTalk Server 方案中的性能，因为它是仅有用只发生在事务日志文件的顺序磁盘读取的。<br /><br /> 仅当它们会在播放时，才从读取事务日志文件，如在数据库还原或的服务器时不正确关闭。 更大的缓存允许更多的数据进行缓冲，这意味着可以容纳的饱和度更长时间。 如果你的控制器允许你配置缓存页大小，应将其设置为 4 KB。 更大的大小，例如 8 KB，会导致缓存浪费，因为 4 KB 的 I/O 请求会占用整个缓存页 8 kb，从而导致你可用缓存减少一半。|  
|轴|轴是比容量，更重要，如果主轴支持大量的随机 I/O 请求的 BizTalk Server 性能得到改进。 规划不超过 80%的总利用率，以确保足够的 I/O 可用，甚至在主轴失败的情况下。|  
|Raid|你使用的 RAID 解决方案应基于成本和性能之间的权衡选择作适用于你的环境。 因此，多个类型的 RAID 解决方案可能会建议针对特定数据存储需求。 一般建议如下所示：<br /><br /> -使用 Raid-1 + 0 BizTalk Server 数据库 （镜像集中的带区集）。<br />-对于事务日志文件卷使用 Raid 1 （无奇偶校验的镜像集）。<br />-一般情况下，不建议 Raid 5 （带分布式奇偶校验的带区集），如 Raid 5 不提供最佳的可靠性、 可用性和性能相比其他 Raid 配置。<br />截止到永久性的数据丢失的可能性，永远不应在 BizTalk Server 生产环境中使用 Raid 0 （无奇偶校验的带区集） 配置。|  
|总线类型|更高的吞吐量提供更好的性能。 一般情况下，SCSI 总线提供更好的吞吐量和可伸缩性，比 IDE 或 ATA 总线。 可以使用以下公式为总线类型确定理论吞吐量限制：<br /><br /> (总线速度 （以位为单位） / 每个字节的 8 位)X 操作系统速度 （以 mhz 为单位） = 吞吐量 （以 MB/秒）<br /><br /> 您还可以通过在独立的 I/O 总线上放置多个驱动器改善磁盘输入/输出性能。|  
  
#### <a name="performance-counters-for-measuring-disk-io-bottlenecks"></a>用于测量磁盘 I/O 瓶颈的性能计数器  
  
> [!NOTE]
>  当尝试分析磁盘性能瓶颈，应始终使用物理磁盘计数器。 但是，如果你使用软件 RAID，你应使用逻辑磁盘计数器。 与逻辑磁盘和物理磁盘计数器，在每个这些计数器对象提供了相同的计数器。 逻辑磁盘数据跟踪的卷管理器 （或管理器） 和物理磁盘数据跟踪的分区管理器。  
  
 若要确定你的系统是否遇到磁盘 I/O 相关的瓶颈，应使用以下性能计数器：  
  
-   **PhysicalDisk\Avg.磁盘队列长度**  
  
    -   阈值： 不应高于数主轴加上两个。  
  
    -   基数： 此计数器指示的两个读取的平均数目，并将采样间隔期间为选择的磁盘排队的请求。 此计数器可用于收集并发数据，包括数据高峰和峰值负载。 这些值表示执行统计的驱动程序之下的传输的请求的数。 这意味着请求不一定排队但实际上可能是在服务中，或已完成并进行备份路径。 可能正在进行的位置如下所示：  
  
        -   SCSIport 或 Storport 队列  
  
        -   OEM 驱动程序队列  
  
        -   磁盘控制器队列  
  
        -   硬盘队列  
  
        -   主动接收从硬盘  
  
-   **PhysicalDisk\Avg.磁盘读取队列长度**  
  
    -   阈值： 应小于两个。  
  
    -   基数： 此计数器指示在采样间隔期间为选择的磁盘排队的读取请求的平均数。  
  
-   **PhysicalDisk\Avg.磁盘写入队列长度**  
  
    -   阈值： 应小于两个。  
  
    -   基数： 此计数器指示在采样间隔期间为选择的磁盘排队的写入请求的平均数。  
  
-   **PhysicalDisk\Avg.Disk sec/Read**  
  
    -   阈值： 没有特定值。  
  
        -   毫秒 (ms) 为少于 10 个单位 = 好  
  
        -   之间 15 和月 25 日 ms = 公平  
  
        -   大于 25 ms = 差  
  
    -   基数： 此计数器指示的平均时间，以秒为单位，从磁盘读取操作的数据。 如果数字为大于 25 毫秒 (ms)，这意味着磁盘系统从磁盘读取时遇到延迟。 对于任务关键型服务器承载 BizTalk Server，可接受的阈值是低得多，大约 10 毫秒。  
  
-   **PhysicalDisk\Avg.Disk sec/Write**  
  
    -   阈值： 没有特定值。  
  
        -   毫秒 (ms) 为少于 10 个单位 = 好  
  
        -   之间 15 和月 25 日 ms = 公平  
  
        -   大于 25 ms = 差  
  
    -   基数： 此计数器表示的平均时间，以秒为单位的数据向磁盘写入操作。 如果数字为大于 25 ms，磁盘系统将写入到磁盘时遇到延迟。 对于任务关键型服务器承载 BizTalk Server，可接受的阈值是低得多，大约 10 毫秒。  
  
-   **PhysicalDisk\Avg.Disk sec/Transfer**  
  
    -   阈值： 不应超过 18 的毫秒。  
  
    -   基数： 此计数器表示的时间，以秒为单位的平均磁盘传输的。 这可能表示大量的磁盘碎片、 慢速磁盘或磁盘故障。 将的值相乘**Physical disk\avg.。Disk sec/Transfer**和**Memory\Pages/sec**计数器。 如果这些计数器的乘积超过 0.1，表示分页占用了超过 10%的磁盘访问时间，因此你需要更多的物理内存可用。  
  
-   **PhysicalDisk\Disk Writes/sec**  
  
    -   阈值： 取决于制造商的规范。  
  
    -   基数： 此计数器指示在磁盘上的写入操作的速率。  
  
-   **处理器\\%DPC Time、 %Interrupt Time 和 %Privileged Time-** 如果 Interrupt Time 和延迟过程调用 (DPC) 时间是大部分 Privileged Time、 内核花费很长的时间来处理输入/输出请求。 在某些情况下，通过在多处理器系统上配置中断和 DPC 地缘成数量较少的 Cpu 可以提高性能，这可以提高缓存区域。 在其他情况下，它最适合要分发的中断和 Dpc 之间的 cpu 数量，以便防止中断和 DPC 活动成为性能瓶颈。 使用中断筛选器配置工具将网络适配器中断绑定到多处理器计算机上的特定处理器的信息，请参阅"使用中断筛选器配置工具以将网络适配器中断绑定到特定的部分中的处理器多处理器计算机上"[优化操作系统性能](~/technical-guides/optimizing-operating-system-performance.md)。  
  
-   **Processor\DPCs 排队 / 秒-** 测量 Dpc 消耗 CPU 时间和内核资源的方式。  
  
-   **Processor\Interrupts / 秒-** 的中断消耗 CPU 时间和内核资源的方式的另一个度量值。 现代磁盘控制器通常组合或合并中断，以便单个中断导致的多个 I/O 完成处理。 当然，没有延迟中断 （和完成功能） 和 economizing CPU 处理时间之间进行权衡。  
  
#### <a name="disk-io-tuning-options"></a>磁盘 I/O 优化选项  
 如果你确定磁盘 I/O 操作成为你的环境中的瓶颈，可能使用以下方法以缓解瓶颈：  
  
-   **碎片整理你的磁盘-** 使用可用在[PageDefrag 实用工具](http://go.microsoft.com/fwlink/?LinkId=108976)(http://go.microsoft.com/fwlink/?LinkId=108976)以对 Windows 分页文件进行碎片整理和预分配主文件表。  
  
-   **使用带区集通过多个磁盘的同时处理输入/输出请求**使用镜像的卷来提供容错和提高 I/O 性能。 如果不需要容错功能，为实现带区集快速读取和写入和改进的存储容量。 当使用带区集时，每个磁盘使用率减少，因为工作分布在这些卷，并提高总体吞吐量。 如果你添加更多的磁盘的条带中设置你的系统可能会遇到由于由磁盘控制器的磁盘之间的争用瓶颈，然后不会增加吞吐量。 在这种情况下，将添加一个额外的磁盘控制器将有助于分散负载并提高性能。  
  
-   **分发在多个驱动器的之间的工作负荷**Windows 群集和分布式文件系统提供多个磁盘驱动器上的负载平衡解决方案。  
  
-   **限制使用文件压缩或加密-** 文件压缩和加密是较 O 高的操作。 仅应使用它们在绝对必要时。  
  
-   **禁用的短名称-创建**如果你不支持 MS-DOS for Windows 3.x 客户端，禁用短名称，以提高性能。 有关禁用创建短名称的详细信息，请参阅"禁用短文件名 (8.3) 生成"一节中[优化操作系统性能](~/technical-guides/optimizing-operating-system-performance.md)。  
  
-   **禁用上次访问更新的**默认情况下，NTFS 更新目录的上次访问日期和时间戳，只要它遍历目录。 对于大型的 NTFS 卷，此更新过程可能会影响性能。 有关禁用上次访问更新的详细信息，请参阅部分中的"禁用上次访问更新的 NTFS"[优化操作系统性能](~/technical-guides/optimizing-operating-system-performance.md)。  
  
    > [!CAUTION]
    >  某些应用程序，如增量备份实用程序，依赖于 NTFS 更新信息，否则将无法正常工作。  
  
-   **保留的主文件表中的适当的空间**添加**NtfsMftZoneReservation**具体取决于通常存储在 NTFS 卷的文件数目注册表项。 当向注册表添加此条目时，系统将保留主文件表的卷上的空间。 保留空间以这种方式允许主文件表增长以最佳方式。 如果你的 NTFS 卷通常存储相对几个文件，请设置此注册表项的值为 1 的默认值。 通常，如果 NTFS 卷存储适中数量的文件，并使用的值为 4 （最大值），如果你的 NTFS 卷往往会包含一个相对较大文件数，则可以使用值为 2 或 3。 但是，请确保用于测试大于 2，任何设置，因为这些更高的值会导致系统保留更大一部分的主文件表的磁盘。 有关添加详细信息**NtfsMftZoneReservation**到注册表中，请参阅部分"增加主文件表"上的可用空间[优化操作系统性能](~/technical-guides/optimizing-operating-system-performance.md)。  
  
-   **使用最高效的磁盘系统用-** 除了使用的物理磁盘，请考虑的磁盘控制器和电缆，将使用的类型。 高效的磁盘子系统还应提供支持中断裁决或中断避免以缓解引起的磁盘 I/O 的处理器中断活动的驱动程序。  
  
-   **确保您使用合适的 RAID 配置-** 使用 RAID 10 （条带化和镜像） 的最佳性能和容错能力。 折中也是使用 RAID 10 将占用大量资源。 避免使用 RAID 5，如果具有大量写入操作。 有关 BizTalk Server 环境中实现 RAID 的详细信息，请参阅"磁盘基础结构"一节中[BizTalk Server 数据库优化白皮书](http://go.microsoft.com/fwlink/?LinkID=101578)(http://go.microsoft.com/fwlink/?LinkID=101578)。  
  
-   **请考虑使用数据库分区-** 如果你有数据库瓶颈，请考虑使用数据库分区并将磁盘映射到特定表和事务日志。 分区的主要目的是克服大型表的磁盘瓶颈。 如果你有具有大量行的表，并且你确定它是瓶颈的根源，请考虑使用分区。 对于 SQL Server，你可以使用文件组以提高 I/O 性能。 可以将表与文件组相关联，然后将文件组与特定硬盘相关联。 有关使用 BizTalk Server 数据库进行的优化文件组的详细信息，请参阅[优化的数据库的文件组](~/technical-guides/optimizing-filegroups-for-the-databases2.md)。  
  
-   **请考虑添加物理内存中，如果你有过多的页面错误-** 的高值**内存： Pages/sec**性能计数器可能表示这会增加磁盘分页过多我 / 0。 如果发生这种情况，请考虑添加物理内存来减少磁盘 i/o 操作并提高性能。  
  
-   **请考虑使用更高版本的 RPM 评级或使用存储区域网络 (SAN) 的磁盘设备-** 磁盘具有更高版本的 RPM 评级提供改进的性能与较低的 RPM 分级，对磁盘进行比较。 SAN 设备通常能提供顶层性能但价格高级层。  
  
-   请按照中的建议[优化数据库性能](~/technical-guides/optimizing-database-performance.md)。 本主题提供有关优化数据库性能之前和之后配置 BizTalk Server 中的几点建议。  
  
### <a name="cpu-bottlenecks"></a>CPU 瓶颈  
 每个服务器运行的应用程序获取 CPU 时间片。 CPU 可能能够有效地处理所有的计算机上，运行的进程，或可能已重载。 通过检查处理器活动和活动的单个进程包括线程创建、 线程切换和上下文切换，你可以深入了解处理器工作负荷和性能。  
  
#### <a name="you-may-have-a-cpu-bottleneck-if"></a>如果，你可能具有 CPU 瓶颈...  
  
-   值**处理器\\%Processor Time**性能计数器通常超过 75%。  
  
-   值**System\ Processor Queue Length**性能计数器是 2 或更多的时间很长一段。  
  
-   值**处理器\\%Privileged Time**或**System\Context Switches/sec**了异常高的性能计数器。  
  
     如果值**Processor\ %Processor Time**性能计数器值较高，则队列发生，并且在大多数情况下的值**System\ Processor Queue Length**也将高。  
  
#### <a name="performance-counters-for-measuring-cpu-bottlenecks"></a>用于测量 CPU 瓶颈的性能计数器  
 若要确定你的系统是否遇到 CPU 相关的瓶颈，应使用以下性能计数器：  
  
-   **处理器\\处理器时间百分比**  
  
    -   阈值： 应为小于 85%。  
  
    -   基数： 此计数器是处理器活动的主要指示器。 高值许多不一定已损坏。 但是，如果越来越多的其他处理器相关的计数器以线性方式如**处理器\\%Privileged Time**或**System\Processor Queue Length**，高 CPU 使用率可能值得调查。  
  
-   **处理器\\%Privileged Time**  
  
    -   阈值： 图，它将一直超过 75%指示瓶颈。  
  
    -   基数： 此计数器指示在特权模式下运行的线程的时间的百分比。 当你的应用程序调用时 （例如，可执行文件或网络 I/O 或分配内存） 的操作系统功能时，这些操作系统功能在特权模式下执行。  
  
-   **处理器\\中断时间百分比**  
  
    -   阈值： 取决于处理器。  
  
    -   基数： 此计数器指示的处理器在接收和服务硬件中断方面所花费的时间的百分比。 此值是活动的生成中断，如网络适配器的设备的间接指示器。 大幅度提高此计数器指示潜在硬件问题。  
  
-   **System\Processor Queue Length**  
  
    -   阈值： 一致地大于 2 的平均值指示瓶颈。  
  
    -   基数： 如果有多个任务准备好运行多于处理器，线程排队等候。 处理器队列为是准备好，但不是能够执行的处理器，因为当前正在执行另一个线程的线程的集合。 持续或循环的两个以上线程队列是处理器瓶颈的清除指示。 通过减少并行度，在这些情况下，可能会更大的吞吐量。  
  
         你可以结合使用此计数器**处理器\\%Processor Time**计数器以确定你的应用程序是否可以从更多的 Cpu 中受益。 没有单个队列的处理器时间，即使是在多处理器计算机上。 因此，在多处理器计算机中，处理器队列长度 (PQL) 值除以处理工作负载的处理器数。  
  
         如果 CPU 非常繁忙 （90%或更高的利用率） 且 PQL 平均值高于一致地为每个处理器的 2，则可能存在处理器瓶颈，无法受益于添加 Cpu。 或者，你无法减少的线程和队列应用程序级别的更多数量。 这将导致减少上下文切换，并减少上下文切换适合用于降低 CPU 负载。 PQL 值 2 或更低的 CPU 利用率较高的常见原因是时间的处理器时间的请求到达随机和线程要求异常长从处理器。 这意味着处理器不成为瓶颈，但应改进应用程序线程处理逻辑。  
  
-   **System\Context Switches/sec**  
  
    -   阈值： 作为一般规则，上下文切换速率小于每个处理器每秒 5,000 不显得很有价值去关注。 如果上下文切换率超过每个处理器每秒的 15000，然后上下文切换可能成为瓶颈。  
  
    -   基数： 上下文切换时发生较高优先级的线程会抢占较低的优先级线程的当前正在运行或高优先级的线程时阻止其他线程。 当多个线程共享相同的优先级级别，则会发生的上下文切换的高级别。 这通常表示有争夺系统上的处理器的线程过多。 如果处理器使用率和上下文切换级别较低，这通常是相对值线程被阻止。  
  
#### <a name="resolving-cpu-bottlenecks"></a>解决 CPU 瓶颈  
 第一步是确定哪个进程正在消耗过多的处理器时间。 使用 Windows**任务管理器**以确定哪个进程正在消耗大量 CPU，通过查看**CPU**列**进程**页。 你还可以通过监视确定这**过程\\%Processor Time**性能监视器和选择你想要监视的进程中。  
  
 确定哪些进程消耗过多的 CPU 时间的另一种功能强大的工具是 Visual Studio 团队系统探查器可与 Visual Studio Team System (VSTS) 套件。 有关使用 Visual Studio 团队系统探查器的详细信息，请参阅 Visual Studio Team System 文档。  
  
 在确定你的 CPU 是瓶颈之后可以几个选项，其中包括：  
  
-   如果具有多线程应用程序，请添加多个处理器。 请考虑升级到更强大的处理器，如果你的应用程序是单线程。  
  
-   如果你观察上下文切换的比率太高，请考虑增加的处理器数之前减少用于您的进程的线程计数。  
  
-   分析和优化的应用程序导致高 CPU 使用率。 你可以通过使用 ADPLUS 实用工具来转储正在运行的进程，并使用 Windbg 分析可能的原因。 这些实用程序是 Windows 调试工具包的一部分。 你可以下载这些工具从[Windows 调试工具](http://go.microsoft.com/fwlink/?LinkID=106624)(http://go.microsoft.com/fwlink/?LinkID=106624)。  
  
-   分析生成你的应用程序隔离正在执行的时间的最大量的子系统的检测日志。 确定是否将更有优势比只优化 BizTalk Server 环境代码评审。  
  
> [!NOTE]
>  尽管您可以通过更改应用程序的进程优先级**任务管理器**或从命令提示符处，通常应避免这样。  
  
### <a name="memory-bottlenecks"></a>内存瓶颈  
 在评估与内存相关的瓶颈，请考虑不必要的分配、 清理、 低效、 也不适合缓存和状态管理机制。 若要解决与内存相关的瓶颈，优化你的代码以消除这些问题，然后调整分配给你的应用程序的内存量。 如果你确定在优化期间发生的内存争用和分页过多，你可能需要向服务器添加额外的物理内存。 内存不足会导致应用程序的虚拟地址空间与其他磁盘增加分页。 如果分页变得过多，磁盘 I/O 将增加和总体系统性能带来负面影响。  
  
#### <a name="you-might-have-a-memory-bottleneck-if"></a>如果，则可能存在内存瓶颈...  
  
-   值**Memory\Available MBytes**性能计数器较低，是由于系统内存限制或的应用程序没有释放内存。 监视的值**进程 \ 工作集**运行每个进程的性能计数器。 如果值**进程 \ 工作集**保持高即使进程处于不活动状态，这可能是指示进程没有释放内存，它也应如此。  
  
-   值**Memory\Pages/sec**性能计数器值较高。 平均值**Memory\Pages Input/sec**除以平均值**Memory\Page Reads/sec**提供的每个磁盘读取的页数。 此值不应通常超过每秒的 5 个页面。 大于每秒的 5 个页面的值指示系统花费太多时间分页，并且需要更多的内存 （假设已优化应用程序）。  
  
#### <a name="performance-counters-for-measuring-memory-bottlenecks"></a>用于测量内存瓶颈的性能计数器  
 若要确定你的系统是否遇到内存相关的瓶颈，应使用以下性能计数器：  
  
-   **Memory\Available Mbytes**  
  
    -   阈值： 小于 20 到 25%的已安装 RAM 的一致的值是相对值的指示内存不足。  
  
    -   基数： 这表示可用于在计算机上运行的进程的物理内存量。 请注意此计数器显示上次观测的值仅。 它不是平均值。  
  
-   **Memory\Page Reads/sec**  
  
    -   阈值： 的五个以上的持续的值表示大量的读取请求的页面错误。  
  
    -   基数： 此计数器指示某一进程工作集是太大，导致内存分页到磁盘的可用物理内存。 它显示读取操作，而不考虑每个操作中检索的页面数的数目。 较高值指示内存瓶颈。  
  
         较低的页读取操作率是否与高值**物理磁盘\\%Disk Time**和**Physical disk\avg.。磁盘队列长度**，可能存在的磁盘 I/O 瓶颈条件。 如果是递减的页读取速率不附带的队列长度增加，内存瓶颈存在物理内存不足。  
  
-   **Memory\Pages/sec**  
  
    -   阈值： 持续的数超过五指示瓶颈。  
  
    -   基数： 此计数器指示从读取或写入磁盘为解决强制分页错误页的速率。 将的值相乘**Physical disk\avg.。Disk sec/Transfer**和**Memory\Pages/sec**性能计数器。 如果这些值的乘积超过**0.1**，分页利用多个 10%的指示足够的物理内存可用的磁盘访问时间。  
  
-   **Memory\Pool Nonpaged 的 Bytes**  
  
    -   阈值： 监视其值的**Memory\Pool Nonpaged Bytes**的 10%或更多与它在系统启动的值的增加。  
  
    -   基数： 增加 10%或更多的值在启动时从可能的内存泄漏指示。  
  
-   **Server\Pool Nonpaged 的失败**  
  
    -   阈值： 正则非零值指示瓶颈。  
  
    -   基数： 此计数器指示从非分页池的分配失败次数。 非分页池包含从进程的虚拟地址空间不会换出到磁盘，如进程内核对象表上的页文件的页。 非分页池的可用性确定多少进程、 线程和其他可以创建此类对象。 当从非分页池的分配失败时，这可能是由于在过程中，内存泄漏中，尤其是当处理器使用率未相应地增加。  
  
-   **Server\Pool 分页失败**  
  
    -   阈值： 没有特定值。  
  
    -   基数： 此计数器指示从页面缓冲池分配已失败的次数。 此计数器是正数值是指示计算机是否具有足够的物理内存，或者 Windows 分页文件太小。  
  
-   **Server\Pool Nonpaged 的峰值**  
  
    -   阈值： 没有特定值。  
  
    -   基数： 这是最大服务器保留供使用的任意一点的非分页池中的字节数。 它指示计算机应该有多少物理内存。 因为非分页池必须是驻留在物理内存，因为必须有留下的其他操作，作为一条经验法则计算机一些内存应已安装是此计数器指示值的 4 倍的物理内存。  
  
-   **Memory\Cache Bytes**  
  
    -   阈值： 没有特定值。  
  
    -   基数： 监视在不同的负载条件下的缓存的大小。 此性能计数器的此值指示静态文件缓存的大小。 默认情况下，此计数器使用大约有 50%的可用内存，但降低时，如果可用内存收缩，这会影响系统性能。  
  
-   **Memory\Cache Faults/sec**  
  
    -   阈值： 没有特定值。  
  
    -   基数： 此计数器指示操作系统查找文件系统缓存中的数据的频率，但无法找到它。 此值应尽可能低。  
  
-   **Cache\MDL 读取命中 %**  
  
    -   阈值： 越高此值，文件系统缓存的性能就越好。 值应接近 100%尽可能。  
  
    -   基数： 此计数器提供百分比的内存描述符列表 (MDL) 读取到文件系统缓存，其中缓存返回的对象直接请求而无需从硬盘读取。  
  
-   **进程 \ 工作集**  
  
    -   阈值： 没有特定值。  
  
    -   基数： 工作集是的当前加载到内存 （物理 + 虚拟） 的内存页的集合。 如果系统有足够的内存，它可以维护足够的空间中的工作集，以便它不需要执行将内存分页到磁盘的磁盘操作。 但是，如果没有足够的内存，系统会尝试减少设置占用从进程的内存，这会导致页错误中增加的工作。 当上升而变化的页面错误的速率时，系统会尝试增加进程工作集。 如果你观察宽波动的工作集，则可能指示内存不足。 较大值的工作集也可能是由于应用程序中的多个程序集。 你可以提高工作集通过使用在全局程序集缓存中共享的程序集。  
  
#### <a name="resolving-memory-bottlenecks"></a>解决内存瓶颈  
 如果你确定该内存是在 BizTalk Server 环境中，使用一个或多个下列方法来解决瓶颈瓶颈：  
  
-   优化分配如果，可以控制分配的内存量。 例如，你可以调整此用于 BizTalk Server、 ASP.NET 和 SQL Server。  
  
-   增加 Windows 页面文件的大小，然后按照中的"配置 Windows 页面文件以获得最佳性能"部分的步骤[优化操作系统性能](~/technical-guides/optimizing-operating-system-performance.md)。  
  
-   关闭不使用的服务。 停止不经常使用的服务节省内存，并提高系统性能。 有关详细信息，请参阅的"禁用不必要的服务"部分[优化操作系统性能](~/technical-guides/optimizing-operating-system-performance.md)。  
  
-   删除不必要的协议和驱动程序。 即使空闲协议中的分页和非分页内存池使用的空间。 驱动程序还使用内存，因此你应删除不必要的。 有关详细信息，请参阅的"删除不必要的网络协议"部分[优化操作系统性能](~/technical-guides/optimizing-operating-system-performance.md)。  
  
-   在 BizTalk Server 环境中的计算机上安装额外的物理内存。  
  
> [!NOTE]
>  在 32 位系统中，BizTalk 可使用最多 2 gb 的内存，限制增加到 3 GB BizTalk Server 2010 和更高版本中，如果使用 /3GB 开关。 有关内存使用量的详细信息，请参阅[Windows 版本的内存限制](http://go.microsoft.com/fwlink/?LinkId=118349)(http://go.microsoft.com/fwlink/?LinkId=118349)。  
  
### <a name="network-io-bottlenecks"></a>网络 I/O 瓶颈  
  
#### <a name="you-might-have-a-network-io-bottleneck-if"></a>如果，则可能存在网络 I/O 瓶颈...  
  
-   值**Network Interface\Bytes Total/sec**性能计数器超过 80%的可用网络带宽。  
  
-   值**Server\Bytes Total/sec**性能计数器大于 50%的可用网络带宽。  
  
#### <a name="performance-counters-for-measuring-network-io-bottlenecks"></a>用于测量网络 I/O 瓶颈的性能计数器  
 应使用以下性能计数器，测量网络输入/输出，并确定你的系统是否遇到网络 I/O 相关的瓶颈：  
  
-   **Network Interface\Bytes Total/sec**  
  
    -   阈值： 持续的 80%以上的网络容量值。  
  
    -   基数： 此计数器指示发送和接收每个网络适配器字节的速率。 此计数器有助于确定是否已饱和的网络适配器，以及是否应添加一个或多个网络适配器，以增加可用的网络带宽。  
  
-   **网络 Interface\Bytes Received/sec**  
  
    -   阈值： 没有特定值。  
  
    -   基数： 此计数器指示在每个网络适配器上接收字节的速率。 此计数器的值用于计算总的可用带宽的百分比的传入数据的速率。 这将帮助确定如果网络带宽应增加客户端发送数据到 BizTalk Server 或如果应在 BizTalk Server 计算机本身上增加网络带宽。  
  
-   **网络 Interface\Bytes Sent/sec**  
  
    -   阈值： 没有特定值。  
  
    -   基数： 此计数器指示每个网络适配器中发送字节的速率。 此计数器的值用于计算总的可用带宽的百分比的传出数据的速率。 这将帮助确定是否应在 BizTalk Server 发送数据到客户端上增加网络带宽，或如果网络带宽应增加对 BizTalk Server 中的客户端计算机接收数据。  
  
-   **Server\Bytes Total/sec**  
  
    -   阈值： 持续超过 50%的网络容量值。  
  
    -   基数： 此计数器指示发送和通过网络接收的字节数。 较高值指示网络 I/O 瓶颈。 如果的总和**Bytes Total/sec**所有服务器是你的网络的最大传输速率大致相同，请考虑划分子网网络来提高性能。 有关划分子网的网络，以提高性能的详细信息，请参阅**子网**部分[BizTalk Server 数据库优化白皮书](http://go.microsoft.com/fwlink/?LinkID=101578)(http://go.microsoft.com/fwlink/?LinkID=101578)。  
  
#### <a name="resolving-network-io-bottlenecks"></a>解决网络 I/O 瓶颈  
 如果你确定网络 I/O 是成为你的环境中的瓶颈，请使用一个或多个以下方法来解决瓶颈：  
  
-   请遵循的"用于提高网络性能的常规指南"一节中的建议[优化网络性能](~/technical-guides/optimizing-network-performance.md)。  
  
-   运行本主题所述的 Windows Powershell 网络优化脚本[优化网络性能](~/technical-guides/optimizing-network-performance.md)在 BizTalk Server 环境中的每台计算机上。  
  
## <a name="see-also"></a>另请参阅  
 [查找并消除瓶颈](~/technical-guides/finding-and-eliminating-bottlenecks.md)