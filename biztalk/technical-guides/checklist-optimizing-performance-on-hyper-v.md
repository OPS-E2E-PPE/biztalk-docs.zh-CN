---
title: "清单： HYPER-V 上优化性能 |Microsoft 文档"
ms.custom: 
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 942a61eb-0fdd-4c8b-b0ad-d32951f0f631
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db0afbdc9d89296f8aaff94db057bf2e9c072392
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="checklist-optimizing-performance-on-hyper-v"></a>清单： HYPER-V 上优化性能
下列注意事项适用时运行 BizTalk Server 和/或[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]BizTalk Server 数据库对 HYPER-V 虚拟机的实例。  
  
## <a name="allocate-110125-of-cpu-and-disk-resources-to-the-hyper-v-virtual-machines"></a>分配给 HYPER-V 虚拟机的 110%– 125%的 CPU 和磁盘资源  
 计划分配 110%到 125%的 CPU 资源和 105%-110%的解决方案使用 HYPER-V 虚拟机的物理硬件解决方案所需的磁盘资源。 通过配置 HYPER-V 虚拟机提供更多资源，将确保它可以提供可与相媲美物理硬件的性能，同时容纳任何所需的 HYPER-V 虚拟化技术的开销。  
  
|步骤|参考|  
|----------|---------------|  
|作用域的硬件要求[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案。|-按照中的"Planning the 环境的 BizTalk Server"部分的指导[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]操作指南，网址[http://go.microsoft.com/fwlink/?LinkId=122399](http://go.microsoft.com/fwlink/?LinkId=122399)确定解决方案的硬件要求的范围。<br />-到作用域的版本和数量的解决方案将所需的 BizTalk 服务器查看在规划注意事项"规划 BizTalk Server 层"中所述的 BizTalk Server [http://go.microsoft.com/fwlink/?LinkId=122401](http://go.microsoft.com/fwlink/?LinkId=122401)。<br />-到作用域的版本和数量[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]解决方案，将所需的计算机在查看的规划注意事项"规划数据库层"中所述的数据库[http://go.microsoft.com/fwlink/?LinkId = 122402](http://go.microsoft.com/fwlink/?LinkId=122402)和可用在"运行 SQL Server 2008 in a HYPER-V 环境最佳实践和性能注意事项"白皮书"性能开销的运行 SQL Server 中 HYPER-V"部分[http://go.microsoft.com/fwlink/？LinkId = 144622](http://go.microsoft.com/fwlink/?LinkId=144622)。<br />-若要完成规划用于开发、 测试、 过渡和生产环境查看"计划开发、 测试、 过渡和生产环境"在[http://go.microsoft.com/fwlink/?LinkId=122403](http://go.microsoft.com/fwlink/?LinkId=122403)。|  
|在范围之外的 BizTalk Server 解决方案的硬件要求之后, 计划配置为 HYPER-V 机**110%– 125%**的 CPU 和磁盘资源如有可能。|例如，如果解决方案所使用的物理 BizTalk Server 计算机的硬件要求被确定为 2 GB RAM，运行 2 GHZ 和 2 x 500 GB 的物理磁盘的双核 CPU 那么理想情况下，解决方案所使用的 HYPER-V 虚拟机将配置了 2 个或更多虚拟处理器运行 > = 2.2 GHZ 和更快地物理磁盘 （通常通过增加主轴数，或使用更快的磁盘）。|  
  
## <a name="optimize-hyper-v-performance"></a>优化 HYPER-V 性能  
 使用以下常规准则来配置 HYPER-V 以获得最佳性能。  
  
|步骤|参考|  
|----------|---------------|  
|应用的性能优化的虚拟化服务器推荐的指导。 **注意：**为测试方案中所述[测试 BizTalk 服务器虚拟化性能](~/technical-guides/testing-biztalk-server-virtualization-performance.md)，在"物理基础结构详细信息"中描述了已应用这些配置选项和"虚拟化详细信息"部分的[测试方案概述](~/technical-guides/test-scenario-overview.md)主题。|在"性能优化准则的 Windows Server 2008 R2"文档"的虚拟化服务器的性能优化"部分[http://go.microsoft.com/fwlink/?LinkID=202087](http://go.microsoft.com/fwlink/?LinkID=202087)。|  
|关闭不会使用任何虚拟机连接窗口。|当双击 HYPER-V 管理器中的虚拟机名称时，显示虚拟机连接窗口占用无法否则使用的资源。|  
|关闭或最小化的 HYPER-V 管理器。|HYPER-V 管理器会通过不断轮询每个运行的虚拟机的 CPU 使用率和正常运行时间占用资源。 关闭或最小化的 HYPER-V 管理器将释放这些资源。|  
  
## <a name="optimize-performance-of-disk-memory-network-and-processor-in-a-hyper-v-environment"></a>优化的磁盘、 内存、 网络和在 HYPER-V 环境中的处理器的性能  
 使用以下准则来优化磁盘、 内存、 网络和 HYPER-V 虚拟环境中的处理器的性能。  
  
### <a name="optimize-processor-performance"></a>优化处理器性能  
 请遵循以下准则来优化的 HYPER-V 虚拟环境中运行的来宾操作系统的处理器性能：  
  
-   **配置虚拟处理器分配给可用的逻辑处理器，以获得最佳性能的 1 对 1 分配**运行 CPU 密集型应用程序，最佳的配置时，到的来宾操作系统中的虚拟处理器 1 到 1 的比例逻辑处理器可供主机操作系统中。 任何其他配置如 2:1 或 1:2 做效率较低。 下图阐释了到逻辑处理器可供主机操作系统的来宾操作系统中的虚拟处理器内核的 1 对 1 分配：  
  
     ![一对一物理到虚拟处理器比率](../technical-guides/media/90f98f0d-a223-404c-b419-81369dc92970.gif "一对一物理到虚拟处理器比率")  
虚拟与逻辑处理器比率  
  
-   **请注意的不同的来宾操作系统的虚拟处理器限制并相应地-计划**可供 HYPER-V 虚拟机中运行的来宾操作系统的处理器内核数可能会影响整体托管的应用程序的性能。 因此，考虑应将有关哪些来宾操作系统将安装在 HYPER-V 虚拟机，以托管 BizTalk Server 和/或[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]承载 BizTalk Server 数据库的实例。 HYPER-V 可以适应下列指定的来宾操作系统的虚拟处理器数：  
  
|操作系统|虚拟处理器限制|  
|----------------------|-----------------------------|  
|[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。 所有版本的[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]都只能是 64 位。|4|  
|[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]64 位|4|  
|[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]32 位|4|  
|64 位 Windows 7|4|  
|32 位 Windows 7|4|  
|64 位 Windows Vista|2|  
|Windows Vista 32 位|2|  
  
> [!NOTE]
>  在 HYPER-V 上支持的来宾操作系统的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkID=118347](http://go.microsoft.com/fwlink/?LinkID=118347)。  
  
### <a name="optimize-disk-performance"></a>优化磁盘性能  
 请遵循以下准则来优化磁盘性能的 HYPER-V 虚拟环境中运行的来宾操作系统：  
  
|步骤|参考|  
|----------|---------------|  
|与使用固定大小虚拟硬盘 (VHD) 选项的 HYPER-V 虚拟机配置为使用的虚拟磁盘。 固定大小 VHD 提供接近，如聚类分析的支持以及快照磁盘支持的功能的灵活性以及物理磁盘的性能。|在 HYPER-V 环境中的磁盘存储是通过虚拟 IDE 控制器或虚拟 SCSI 控制器可访问。 与以前版本的 Microsoft 虚拟化技术，访问虚拟硬盘时使用的虚拟 IDE 控制器或虚拟 SCSI 控制器之间没有性能差异。 还提供在 HYPER-V 环境中使用以下的磁盘存储选项：<br /><br /> -   **固定大小磁盘-**固定大小虚拟硬盘 (VHD) 是一个数据块都将在基于在创建时定义的最大磁盘大小的物理磁盘上预先分配。 例如，如果你创建 100 GB 固定大小的 VHD，HYPER-V 将分配所有 100 GB 的数据块存储，除了创建新的 VHD 时所需的 VHD 页眉和页脚的开销。<br />-   **动态扩展磁盘-**动态扩展的 VHD 是为其初始虚拟硬盘包含任何数据块。 而是数据写入到该 VHD，直到达到最大大小创建 VHD 时指定动态分配空间。 例如，100 GB 动态扩展磁盘最初包含仅 VHD 标头，并且需要小于 2 MB 的物理存储空间。 虚拟机的情况下，新数据写入到动态扩展的 VHD，其他物理数据块被分配的在 2 MB 到 VHD 文件，最多为 100 GB 的增量。<br />-   **差异磁盘-**差异磁盘是特殊类型的动态扩展与"父"VHD 关联的 VHD 文件。 在此父/子存储拓扑中，父磁盘保持不变并对差异磁盘仅"子"所做的任何写入操作。 对差异磁盘，以查看是否已更新的内容写入到差异磁盘; 首先检查任何读取的操作如果内容不在差异磁盘，然后从父 VHD 读取内容。 差异磁盘可用于方案，你需要维护特定基准配置和想要能够轻松地测试，然后回滚更改为基线。 适用于测试通过差异磁盘提供的父/子存储拓扑的灵活性时，这不是性能的最佳配置在于，存在与维护父/子拓扑相关联的开销在使用差异磁盘时需要。<br />-   **传递磁盘，即**传递磁盘功能，来宾操作系统能够绕过 HYPER-V 主机的文件系统并直接访问磁盘。 都提供给来宾操作系统可通过传递磁盘必须设置为"脱机"将确保，主机和来宾操作系统请不要尝试同时访问该磁盘的 HYPER-V 主机中。 传递磁盘确实提供相比其他磁盘的边际性能优势存储选项，但不支持的虚拟磁盘，例如虚拟机快照和聚类分析支持某些功能。 因此的传递磁盘功能的建议不要使用在 BizTalk 或 SQL Server 环境中由于边际性能优势是多个是通过所缺少的功能偏移量。<br /><br /> 有关磁盘存储选项中的 HYPER-V 提供的相对性能的详细信息，请参阅博客条目"HYPER-V 存储分析"，在[http://go.microsoft.com/fwlink/?LinkID=132848](http://go.microsoft.com/fwlink/?LinkID=132848)。|  
|配置为使用 SCSI 控制器的数据卷的磁盘|此建议，因为已安装 HYPER-V 集成服务，而无需安装 HYPER-V 集成服务中，模拟的 IDE 控制器可用情况下，才会安装 SCSI 控制器。 使用提供使用 integration services 的 IDE 筛选器驱动程序执行的磁盘 I/O 是明显优于磁盘输入/输出性能提供与模拟的 IDE 控制器。 因此，若要确保最佳磁盘的 HYPER-V 虚拟化环境中的数据文件的 I/O 性能，在主机和来宾操作系统上安装集成服务，并且使用合成 SCSI 控制器配置数据卷的磁盘。 对于跨多个数据驱动器的高密集型存储 I/O 工作负荷，应将每个 VHD 附加到更好的总体性能的单独合成 SCSI 控制器。 此外，每个 VHD 应存储在单独的物理磁盘上。 **重要说明：**不要将系统磁盘连接到 SCSI 控制器。 包含操作系统虚拟硬盘必须连接到 IDE 控制器。|  
  
### <a name="optimize-memory-performance"></a>优化内存性能  
 请遵循以下准则来优化的 HYPER-V 虚拟环境中运行的来宾操作系统的内存性能：  
  
|步骤|参考|  
|----------|---------------|  
|请确保有足够的内存在的物理计算机的托管 HYPER-V 虚拟机上安装|可用物理内存通常是 HYPER-V 虚拟机上运行的 BizTalk Server 性能的最重要因素。 这是因为每个虚拟机必须位于非分页池的内存或不能分页到磁盘的内存。 因为非页面缓冲池内存不能分页到磁盘，承载虚拟机的物理计算机应具有可用的物理内存的内存总和等于为分配每个虚拟机还包括以下：<br />     用于虚拟机监控程序的 300 MB 加上 32 MB; 在第一个 GB 的 RAM 分配给每个虚拟机加上另一台 8 MB 的每个其他 GB 的 RAM 分配给每个虚拟机以及主机 512 MB运行在根分区上的操作系统<br />     例如，如果 HYPER-V 虚拟机分配有 2 GB 的内存在 HYPER-V 管理器，在运行 HYPER-V 虚拟机将大约 2388 MB 时使用的实际物理内存 (为虚拟机的虚拟机监控程序的 300 MB + 2 GB 分配 +32 MB + 8 MB = 2388 MB)。 由于虚拟机监控程序仅需要加载一次，初始化的后续虚拟机不会产生与加载虚拟机监控程序关联的 300 MB 开销。 因此，如果两个 HYPER-V 虚拟机是每个已分配的 2 GB 的内存在 HYPER-V 管理器中，使用这些 HYPER-V 虚拟机运行时的实际物理内存可能大约 4476 MB （虚拟机监控程序的 300 MB + 4 GB 已分配虚拟机 + 64 MB + 16 MB = 4476 MB)。 **注意：**作为一个常规的经验法则，规划分配为根分区提供服务例如 I/O 虚拟化和快照文件支持，且子分区管理至少 512 MB 内存。<br />-   **使用 64 位来宾操作系统尽可能**– 请考虑使用为每个来宾操作系统的 64 位操作系统。 应因为默认情况下，32 位 Windows 操作系统可以仅地址最多为 2 GB 的每个进程的虚拟地址空间完成此操作。 64 位操作系统安装允许应用程序充分利用托管 HYPER-V 虚拟机的物理计算机上安装的内存。|  
  
### <a name="optimize-network-performance"></a>优化网络性能  
 HYPER-V 虚拟机中支持合成和模拟的网络适配器，但合成设备提供显著提高性能并减少 CPU 开销。 其中每个适配器连接到虚拟网络交换机，如果需要外部网络连接可以连接到物理网络适配器。 请遵循本部分中的建议，以优化网络性能的 HYPER-V 虚拟环境中运行的来宾操作系统。  
  
> [!NOTE]
>  从"性能优化准则的 Windows Server 2008 R2"白皮书下载的"性能优化的虚拟化服务器"部分的这些建议适用[http://go.microsoft.com/fwlink/?LinkID=202087](http://go.microsoft.com/fwlink/?LinkID=202087)。 有关如何优化在根分区中，包括中断裁决的网络适配器，请参阅本指南的"性能优化的网络子系统"部分。 应该应用该节中的 TCP tunings，如有必要，子分区到。  
  
|步骤|参考|  
|----------|---------------|  
|配置在同一个 HYPER-V 主机计算机用于专用虚拟网络运行的 HYPER-V 虚拟机|请遵循中的"配置在相同的 HYPER-V 上运行 HYPER-V 虚拟机宿主计算机以使用专用虚拟网络"部分建议[网络优化](~/technical-guides/network-optimizations.md)。|  
|禁用 TCP 卸载虚拟机网卡|请遵循中的"禁用 TCP 卸载的虚拟机网卡"部分建议[网络优化](~/technical-guides/network-optimizations.md)。|  
|配置来宾操作系统为使用 HYPER-V 合成网络适配器。|相比到仿真的网络适配器，以模拟现有硬件，专为虚拟机以实现显著设计的合成网络适配器能减少 CPU 开销的 HYPER-V 功能将网络 I/O。 合成网络适配器通过使用更高效的数据传输的共享的内存 VMBus 的子域和根分区之间进行通信。 <br />仿真的网络适配器应通过的 VM 的设置对话框删除并替换的合成网络适配器。 来宾要求安装 VM 集成服务。|  
|如果可用，请启用根分区中的物理网络适配器驱动程序的卸载功能。|因为本机的方案中，卸载与物理网络适配器中的功能减少 VM 方案中的网络 I/o 的 CPU 使用率。 HYPER-V 当前使用 LSOv1 和 TCPv4 校验和卸载。 必须在根分区中的物理网络适配器的驱动程序中启用卸载功能。 有关在网络适配器卸载功能的详细信息，请参阅"选择网络适配器"的部分可用于"性能优化准则的 Windows Server 2008 R2"白皮书"性能优化的虚拟化服务器"部分在下载[http://go.microsoft.com/fwlink/?LinkID=202087](http://go.microsoft.com/fwlink/?LinkID=202087)。<br />驱动程序对于某些网络适配器禁用 LSOv1，但默认情况下启用 LSOv2。 使用驱动程序，系统管理员必须显式启用 LSOv1**属性**对话框在设备管理器。|  
|配置网络交换机拓扑，以使多个网络适配器使用。|HYPER-V 支持创建多个虚拟网络交换机，其中每个可以将附加到物理网络适配器，如果需要。 在 VM 中的每个网络适配器可以连接到虚拟网络交换机。 如果物理服务器具有多个网络适配器，可以受益具有网络密集型负载的虚拟机连接到不同的虚拟交换机，以更好地使用物理网络适配器。|  
|如果多个物理网卡的 HYPER-V 主机计算机上，每个网络都为一个逻辑处理器的绑定设备中断安装。|在某些工作负荷，绑定到一个逻辑处理器的单个网络适配器的设备中断操作可以提高性能的 HYPER-V。 我们建议此高级优化，只是为了解决中完全使用网络带宽的特定问题。 系统管理员可以使用 IntPolicy 工具以将设备中断绑定到特定的处理器。 有关 IntPolicy 工具的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkID=129773](http://go.microsoft.com/fwlink/?LinkID=129773)。|  
|如果可能，请启用 VLAN 标记为 HYPER-V 合成网络适配器。|HYPER-V 合成网络适配器支持 VLAN 标记。 如果物理网络适配器支持的 NDIS_ENCAPSULATION_IEEE_802_3_P_AND_Q_IN_OOB 封装的大量发送和校验和卸载，它可以提供显著提高网络性能。 此支持，HYPER-V 无法用于需要 VLAN 标记的数据包的硬件卸载功能而无需可以减少网络性能。|  
|在 HYPER-V 主机计算机上安装的高速网络适配器和配置以获得最佳性能。|请考虑在 HYPER-V 主机计算机上安装 1 GB 网络适配器和配置网络适配器具有固定速度而不是使用"自动协商"-它是非常重要的网络速度、 双工、 和流控制参数设置为对应交换机上的设置到其连接到。|  
|遵循有关优化网络性能的最佳做法。|主题[网络优化](~/technical-guides/network-optimizations.md)提供了有关优化网络性能的常规指南。 虽然本主题不提供有关优化性能的特定建议[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]时的技术在 HYPER-V 虚拟化环境中，是适用于任何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案，是否在物理硬件上或 HYPER-V 上运行虚拟化的环境。|  
  
## <a name="optimize-sql-server-performance"></a>优化 SQL Server 性能  
 请按照本主题中的建议[SQL Server 优化](~/technical-guides/sql-server-optimizations.md)以优化 BizTalk Server 解决方案的 SQL Server 性能。 虽然本主题不提供有关优化性能的特定建议[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]时的技术在 HYPER-V 虚拟化环境中，是适用于任何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案，是否在物理硬件上或 HYPER-V 上运行虚拟化的环境。  
  
## <a name="optimize-biztalk-server-solution"></a>优化 BizTalk 服务器解决方案  
 请按照本主题中的建议[BizTalk Server 优化](~/technical-guides/biztalk-server-optimizations.md)以优化性能的 BizTalk Server 解决方案。 虽然本主题不提供有关优化性能的特定建议[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]时的技术在 HYPER-V 虚拟化环境中，是适用于任何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案，是否在物理硬件上或 HYPER-V 上运行虚拟化的环境。