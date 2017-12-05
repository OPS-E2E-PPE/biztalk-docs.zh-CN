---
title: "安装和配置 HYPER-V 虚拟机，以使用与 BizTalk Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86add392-3cde-432d-95d6-c81d68716537
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b973053d3afa9c6d0b61de111d9da1c4fb7a0fb1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="installing-and-configuring-a-hyper-v-virtual-machine-for-use-with-biztalk-server"></a>安装和配置 HYPER-V 虚拟机，以使用与 BizTalk Server
本主题提供有关安装和配置在 HYPER-V 环境中，包括有关安装和配置 HYPER-V 虚拟机的建议和建议在上安装 BizTalk Server 的 BizTalk Server 建议HYPER-V 虚拟机。  
  
## <a name="installing-and-configuring-hyper-v"></a>安装和配置 HYPER-V  
 在安装之前 HYPER-V，请参阅[What's New in Windows Server 2008 R2 中 HYPER-V](http://go.microsoft.com/fwlink/?LinkID=202427)。 "Microsoft HYPER-V Server 2008 R2 入门"指南提供有关如何安装和配置详细信息[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]HYPER-V。 该指南可以在[http://go.microsoft.com/fwlink/?LinkID=202431](http://go.microsoft.com/fwlink/?LinkID=202431)。  
  
 "性能优化准则适用于 Windows Server 2008 R2"文档提供了详细信息优化[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]和包含专门侧重于 HYPER-V 的部分。 文档位于[http://go.microsoft.com/fwlink/?LinkID=202087](http://go.microsoft.com/fwlink/?LinkID=202087)。  
  
### <a name="hyper-v-platform-prerequisites"></a>HYPER-V 平台必备组件  
 HYPER-V 是可用于 64 位和的所有版本的服务器角色[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]都只能是 64 位。 此外，物理硬件必须支持硬件辅助虚拟化。 这意味着必须是具有 Intel 虚拟化技术 (Intel VT) 或 AMD 虚拟化 (AMD-V) 技术兼容的处理器、 系统 BIOS 必须支持数据执行保护 (DEP)，并且必须支持 DEP。 具体而言，必须启用 Intel XD 位 （执行禁用位） 或 AMD NX 位 （无执行位）。  
  
> [!NOTE]  
>  启用在系统 BIOS 中的这些选项后, 完全关闭计算机，然后重新启动计算机，以确保这些设置将应用。  
  
#### <a name="determining-hardware-requirements"></a>确定硬件要求  
 由于服务器合并的需求，HYPER-V 服务器倾向于使用更多的 CPU 和内存，并且需要更大的磁盘 I/O 带宽比具有可比较的计算负载的物理服务器。 为了部署环境，以符合预期要求，请考虑下面确定你的服务器的确切的硬件要求的因素。  
  
##### <a name="storage-configuration-options"></a>存储配置选项  
 存储硬件应提供足够的 I/O 带宽和存储容量，以满足你打算承载虚拟机的当前和未来需求。 选择 HYPER-V 之间容量使用情况和性能它可以提供的存储配置时，进行权衡。  
  
 在规划存储配置时，请考虑要设置的环境的要求。 生产、 预生产中和开发环境的要求可能相差很大。  
  
 如果要部署的生产型 HYPER-V 上的 BizTalk Server 环境，性能将一项关键要求。 若要避免磁盘 I/O 争用繁忙的生产系统上，在主机和来宾操作系统上安装集成服务，并使用合成 SCSI 控制器配置数据卷的磁盘。 对于跨多个数据驱动器的高密集型存储 I/O 工作负荷，应将每个 VHD 附加到更好的总体性能的单独合成 SCSI 控制器。 此外，每个 VHD 应存储在单独的物理磁盘上。 有关配置的数据磁盘的详细信息与综合的 SCSI 控制器的卷，请参阅主题的"优化磁盘性能"部分[清单： HYPER-V 上优化性能](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md)。  
  
 通常情况下，开发环境不具有严格的性能要求，因为最大化资源利用率往往是主要的优先级。 对于开发环境提供承载在单个物理驱动器上的多个 VHD 文件时的性能是通常可接受的。  
  
 HYPER-V 支持多种不同类型的存储磁盘选项。 到计算机，可以通过 IDE 或 SCSI 控制器附加每个存储选项。 使用上的 IDE 控制器的 SCSI 控制器的潜在优点是，它将仅正常工作如果在来宾虚拟机上安装了操作系统集成组件的正确版本。 这是确保来宾操作系统上安装了正确的操作系统的集成组件的一种简单的方法。  
  
> [!NOTE]  
>  与以前版本的 Microsoft 虚拟化技术，访问虚拟硬盘时使用的虚拟 IDE 控制器或虚拟 SCSI 控制器之间没有性能差异。  
  
 对于密集型的读写活动，如承载[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库，传递磁盘选项提供增量性能优于固定虚拟硬盘 (VHD) 磁盘。 传递选项允许虚拟机能够直接访问的物理磁盘和绕过 NTFS 文件系统根分区中的，但不支持某些功能的虚拟磁盘，例如虚拟机快照和群集支持。 因此的传递磁盘功能的建议不要使用在 BizTalk 或 SQL Server 环境中由于边际性能优势是多个是通过所缺少的功能偏移量。  
  
 下表总结了可用的 HYPER-V 存储选项的优缺点:。  
  
|**HYPER-V 的存储类型**|**专业人员**|**Cons**|**BizTalk Server 的注意事项**|  
|-------------------------------|--------------|--------------|-------------------------------------------|  
|**固定的大小磁盘**|因为在其最大可能大小初始化 VHD 文件，在物理硬盘上创建时的性能优于动态 VHD。<br /><br /> 这使碎片小于可能和，因此，可以降低一个单一的 I/O 被分成多个 I/o 的方案。 这具有 VHD 类型的最低 CPU 开销，因为读取和写入不需要查找的块的映射。|需要完整的前期的磁盘空间量分配。|操作系统卷上使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 **重要说明：** HYPER-V 来宾分区的启动磁盘必须连接到 IDE 控制器。|  
|**动态扩展磁盘**|VHD 文件的大小增加到更多的数据存储在虚拟机本身上时创建磁盘、 指定的大小。 这样就能适应可用存储空间最有效的使用。|不执行以及固定大小的 VHD。 这是因为在磁盘中的块开始状态均为零的块，但不是由任何 VHD 文件中的实际空间。 返回此类块中读取零的块。 第一个块时写入到中，虚拟化堆栈必须分配块的 VHD 文件内的空间，然后更新相应的元数据。 除了这每次引用现有块的块映射必须查找元数据中。 这会增加读取的数，并且这反过来会导致写入活动增加 CPU 使用率。<br /><br /> 动态增长还需要服务器管理员监视磁盘容量，以确保有足够的磁盘存储作为存储需求的增长。|不执行以及固定大小的 VHD。<br /><br /> 如果性能并不是问题，例如在开发环境中，这可能是操作系统的硬盘驱动器的合适选项。<br /><br /> 会导致额外的 CPU 开销，由于块映射查找。|  
|**差异磁盘**|这其中差异磁盘存储相对于基本 VHD 和基本 VHD 的所有更改的父-子配置保持不变。 因此它们是不同于其父块需要存储差异 VHD 的子级。|因为读/写需要访问形式固定/动态父 VHD 和差异磁盘，则可能会降低性能。 这会增加 CPU 使用率和磁盘 I/O 开销。|大量的机特定配置，才能使用 BizTalk Server 安装和子 VHD 文件可能会变得大体上这将最小化使用此磁盘配置的优点。 读取从多个 VHD 的在此方案中会产生额外的 CPU 和磁盘 I/O 开销。|  
|**传递磁盘**|这些是物理磁盘设置为*脱机*中的根分区和启用 HYPER-V 可具有独占写入物理磁盘的读写访问权限。|以使其以分配给虚拟机需要一个完全专用的磁盘或 LUN。<br /><br /> 物理磁盘的难度以比 VHD 文件在计算机之间移动。|如果你[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例在 HYPER-V 上运行，则您可能通过使用用于 BizTalk Server 数据卷的固定虚拟硬盘 (VHD) 使用传递磁盘获取增量性能改进。<br /><br /> 如果您要承载本地文件接收 BizTalk 服务器上的位置，或在处理过程中磁盘的大型消息流式处理，则可能会获得通过使用固定虚拟硬盘 (VHD) 使用传递磁盘的增量性能改进。|  
  
 有关实现磁盘和存储与 HYPER-V 使用的详细信息请参阅[实现磁盘和存储](http://go.microsoft.com/fwlink/?LinkID=142362)(http://go.microsoft.com/fwlink/?LinkID=142362)。  
  
##### <a name="networking"></a>网络  
 BizTalk Server 往往会表现出较高网络使用率。 因此，如果网络性能问题，请考虑为每个虚拟机分配单独的物理网卡。  
  
 配置虚拟机，确保而不是旧版网络适配器使用网络适配器。 旧版网络适配器适用于不支持集成组件的操作系统。  
  
 若要测量网络性能使用**"\Network 接口 \Bytes Total/sec"**和**\Network 接口 (\*) \Output 队列长度**主机操作系统上的性能监视器计数器要测量的网络卡的总体性能的系统。 如果物理网络已被标识为忙，使用**"\Hyper-V 虚拟网络适配器 (\*) \Bytes/sec"**在主机操作系统以确定哪些虚拟机网络接口适配器上的计数器是生成高负载。  
  
 有关评估在 HYPER-V 环境中的网络性能的详细信息请参阅**测量网络性能**部分[清单： HYPER-V 上的测量性能](../technical-guides/checklist-measuring-performance-on-hyper-v.md)。  
  
##### <a name="cpu"></a>CPU  
 HYPER-V 支持为不同的来宾操作系统; 不同数量的虚拟处理器下表中进行了总结。 若要为 BizTalk Server 中分配的最大 CPU 资源，请将其安装在[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]来宾操作系统，支持每个虚拟机的四个虚拟处理器。  
  
 配置虚拟处理器的 1-1 分配到逻辑处理器可供主机操作系统，以防止过多的上下文切换的来宾操作系统中。 过多的上下文切换处理器之间会导致性能下降。 有关分配虚拟处理器到逻辑处理器的详细信息，请参阅主题的"优化处理器性能"部分[清单： HYPER-V 上优化性能](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md)。  
  
 "虚拟机监控程序逻辑 processor （_total) \Hyper-V\\%总运行时间"性能监视器计数器测量的所有来宾计算机和 HYPER-V 主机上的虚拟机监控程序的总体资源使用率。 如果此值高于 90%，以最大容量; 运行服务器在此方案中的虚拟机分配额外的虚拟处理器可能会降低整体系统性能，应当避免。 有关使用 HyperV 性能计数器的详细信息，请参阅[的 BizTalk Server 性能评估 HYPER-V](../technical-guides/evaluating-biztalk-server-performance-on-hyper-v.md)本指南的部分。  
  
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
  
##### <a name="memory"></a>内存  
 物理服务器根分区和在服务器上运行任何虚拟机需要足够的内存。 在测试期间，至少 2 gb 的内存已分配给根分区和**内存/可用兆字节数**性能监视器计数器监视以确保没有内存压力，就会出现。  
  
 应该分配给 BizTalk 服务器环境中每个虚拟机的内存量取决于工作负荷，并将执行的处理类型。 有许多因素会影响的 BizTalk Server 包括内存要求：  
  
-   处理的消息的大小  
  
-   消息吞吐量  
  
-   业务流程设计  
  
-   管道处理  
  
-   你打算运行虚拟机中的 BizTalk 主机数  
  
 有关影响内存的因素的完整列表，请参阅"性能因素"部分的 BizTalk Server 性能优化指南在[http://go.microsoft.com/fwlink/?LinkId=122587](http://go.microsoft.com/fwlink/?LinkId=122587)。  
  
 主动监视**内存/可用兆字节数**计数器从每个虚拟机和根分区本身中。 从以下准则[清单： HYPER-V 上的测量性能](../technical-guides/checklist-measuring-performance-on-hyper-v.md)应该用于确定是否有足够的可用物理内存的虚拟机和根分区：  
  
-   可用内存的 50%或更 = 正常  
  
-   25%的可用内存 = 监视器  
  
-   可用内存的 10%= 警告  
  
-   小于 5%的可用内存 = 严重，性能将会受到不利影响  
  
#### <a name="choosing-root-operating-system-version"></a>选择根操作系统版本  
 HYPER-V 支持服务器核心完全安装的上[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。 若要根分区的开销降到最低，请安装 HYPER-V 的服务器核心安装上[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。 可以从不同的系统上的 HYPER-V 管理器远程管理 HYPER-V 角色。 服务器核心提供了一个小磁盘和内存配置文件，因此，将保留可用于虚拟机的更多资源。 有关可用于的服务器核心安装选项的详细信息[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]，请参阅[http://go.microsoft.com/fwlink/?LinkID=202439](http://go.microsoft.com/fwlink/?LinkID=202439)。  
  
 如果你选择使用完全安装的[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]，确保根分区专用于 HYPER-V 服务器角色。 运行其他服务器角色将会占用内存、 磁盘、 处理器和网络资源，将降低性能。  
  
#### <a name="creating-your-virtual-machines"></a>创建虚拟机  
 已安装并配置 HYPER-V 服务器角色之后，你需要创建虚拟机。 之前执行此操作，它可用于回答以下问题：  
  
-   将使用何种存储配置？  
  
-   来宾操作系统支持虚拟处理器数量？  
  
-   将到虚拟机分配多少内存？  
  
-   在我的 HYPER-V 服务器上可以运行多少个虚拟机？  
  
-   如何将安装到计算机的操作系统？  
  
 有关如何创建和配置虚拟机的详细信息，请参阅[创建虚拟机](http://go.microsoft.com/fwlink/?LinkID=202440)。  
  
##### <a name="installing-the-base-operating-system"></a>安装基本操作系统  
 在 HYPER-V 中有可供物理服务器安装的所有选项。 可启动 CD/DVD-ROM 媒体或 ISO 映像可用于执行的手动安装。 如果已使用连接到与承载 ISO 映像的服务器位于同一网络的网络适配器配置虚拟机，可以执行的网络安装。  
  
> [!IMPORTANT]  
>  选择任何一种安装方法，出于性能原因很重要操作系统集成组件安装在 HYPER-V 中运行每个虚拟机。 集成组件提供驱动程序和服务的支持的来宾计算机，通过使用合成设备来执行一的组。 合成设备避免对模拟的设备，这在不支持集成组件的操作系统上使用的需求。 模拟的设备会产生更大的系统开销相比合成设备。  
  
 若要安装和配置本实验室中使用的计算机，初始的基本映像已创建固定大小的 VHD。 这涉及到的手动安装[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。 一旦已安装所有合适的更新基的虚拟机进行映像使用 sysprep 实用工具 %WINDIR%\system32\sysprep 目录中随 Windows Server 2008 一起安装。  
  
> [!NOTE]  
>  可以通过使用 Sysprep 应答文件和与 BizTalk Server 附带提供的脚本完成之后 BizTalk Server 已安装并配置服务器上运行 Sysprep。 与 BizTalk Server 上安装这些示例脚本旨在用于[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。 有关详细信息请参阅 BizTalk Server 联机文档。  
  
## <a name="installing-and-configuring-biztalk-server"></a>安装和配置 BizTalk Server  
  
-   若要最小化安装虚拟机所需的时间，创建基本映像只包含来宾操作系统和软件必备项。 使用 SysPrep 准备的 VHD 映像以供重复使用，，然后的所有虚拟机 (Vm) 都基础此 VHD。  
  
    > [!NOTE]  
    >  使用 BizTalk Server 中，就可能对基本映像运行 Sysprep*后*已安装并在服务器上配置 BizTalk Server。 这可以通过使用 Sysprep 应答文件和与 BizTalk Server 附带提供的脚本来完成。 与 BizTalk Server 上安装这些示例脚本旨在用于[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。 有关详细信息请参阅 BizTalk Server 联机文档。  
    >   
    >  无人参与 Windows 安装参考位于[http://go.microsoft.com/fwlink/?LinkId=142364](http://go.microsoft.com/fwlink/?LinkId=142364)。  
  
-   请按照"时安装和配置 BizTalk Server …"中的建议 主题的部分[清单： 安装和配置 HYPER-V 上的 BizTalk Server 最佳做法](../technical-guides/checklist-best-practices-to-install-and-configure-biztalk-server-on-hyper-v.md)。  
  
-   有关信息的可支持性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]在 HYPER-V 环境中，请参阅[附录 c: BizTalk Server 和 SQL Server HYPER-V 可支持性](../technical-guides/appendix-c-biztalk-server-and-sql-server-hyper-v-supportability.md)。