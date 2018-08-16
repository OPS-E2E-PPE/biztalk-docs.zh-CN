---
title: 安装和配置的 HYPER-V 虚拟机以使用与 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 86add392-3cde-432d-95d6-c81d68716537
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f350c34949d0cc4f5dd454119b68e488cd0924ba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977302"
---
# <a name="installing-and-configuring-a-hyper-v-virtual-machine-for-use-with-biztalk-server"></a>安装和配置的 HYPER-V 虚拟机以使用与 BizTalk Server
本主题提供有关安装和配置 BizTalk Server 中的 HYPER-V 环境，包括关于安装和配置的 HYPER-V 虚拟机的建议和建议在安装 BizTalk Server 的建议HYPER-V 虚拟机。  

## <a name="installing-and-configuring-hyper-v"></a>安装和配置的 HYPER-V  
 在安装之前的 HYPER-V，请参阅[What's New in Windows Server 2008 R2 中的 HYPER-V](http://go.microsoft.com/fwlink/?LinkID=202427)。 Microsoft HYPER-V Server 2008 R2 入门指南提供了有关如何安装和配置详细信息[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]的 HYPER-V。 本指南将位于[ http://go.microsoft.com/fwlink/?LinkID=202431 ](http://go.microsoft.com/fwlink/?LinkID=202431)。  

 "适用于 Windows Server 2008 R2 性能优化准则"文档提供有关优化的详细信息[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]并包括专门侧重于 HYPER-V 的部分。 该文档位于[ http://go.microsoft.com/fwlink/?LinkID=202087 ](http://go.microsoft.com/fwlink/?LinkID=202087)。  

### <a name="hyper-v-platform-prerequisites"></a>HYPER-V 平台必备组件  
 HYPER-V 是一种服务器角色适用于 64 位和所有版本的[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]只有 64 位。 此外，在物理硬件必须支持硬件辅助虚拟化。 这意味着必须是具有 Intel 虚拟化技术 (Intel VT) 或 AMD 虚拟化 (AMD-V) 技术兼容的处理器、 系统 BIOS 必须支持数据执行保护 (DEP) 和必须启用 DEP。 具体而言，必须启用 Intel XD 位 （执行禁用位） 或 AMD NX 位 （无执行位）。  

> [!NOTE]  
>  启用系统 BIOS 中的这些选项后, 完全关闭计算机，然后重新启动计算机，以确保这些设置将应用。  

#### <a name="determining-hardware-requirements"></a>确定硬件要求  
 由于服务器合并的需求，而 HYPER-V 服务器往往会占用更多 CPU 和内存，并且需要更大的磁盘 I/O 带宽比可比较的计算负载的物理服务器。 若要部署的环境将达到预期要求，请考虑下面以确定你的服务器的确切的硬件要求的因素。  

##### <a name="storage-configuration-options"></a>存储配置选项  
 存储硬件应该提供足够的 I/O 带宽和存储容量，以满足你打算承载虚拟机的当前和未来需求。 选择容量使用情况和它可以提供性能之间的 HYPER-V 的存储配置时需要进行权衡。  

 在规划存储配置，请考虑要在预配的环境的要求。 显著的生产、 预生产和开发环境的要求可能不同。  

 如果要部署生产 HYPER-V 上的 BizTalk Server 环境，性能将是一项关键要求。 若要避免磁盘在繁忙的生产系统上的 I/O 争用，主机和来宾操作系统上安装集成服务并将数据卷的磁盘合成 SCSI 控制器的配置。 对于跨多个数据驱动器的高密集型存储 I/O 工作负荷，每个 VHD 应附加到单独的合成 SCSI 控制器以提高整体性能。 此外，每个 VHD 应存储在单独的物理磁盘上。 有关配置的数据磁盘详细信息与合成 SCSI 控制器的卷，请参阅本主题的"优化磁盘性能"部分[清单： 优化 HYPER-V 上的性能](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md)。  

 通常情况下，开发环境并不具有严格的性能要求，因为最大化资源利用率往往是主要的优先级。 适用于开发环境提供托管在单个物理驱动器上的多个 VHD 文件时的性能是通常可接受的。  

 HYPER-V 支持多种不同类型的存储磁盘选项。 到计算机，可以通过 IDE 或 SCSI 控制器附加每个存储选项。 通过 IDE 控制器使用 SCSI 控制器的潜在好处是，它将仅正常工作如果来宾虚拟机上安装了正确版本的操作系统集成组件。 这是用于确保来宾操作系统上安装了正确的操作系统集成组件的简单方法。  

> [!NOTE]  
>  与以前版本的 Microsoft 虚拟化技术，是访问虚拟硬盘时，使用虚拟 IDE 控制器或虚拟 SCSI 控制器之间没有性能差异。  

 对于密集型读写活动，如托管[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库，传递磁盘选项提供增量性能优于固定虚拟硬盘 (VHD) 磁盘。 通过选项允许虚拟机能够直接访问物理磁盘和绕过 NTFS 文件系统根分区中的，但不支持的虚拟磁盘，例如虚拟机快照和聚类分析的特定功能支持。 因此使用的传递磁盘功能建议不要在 BizTalk 或 SQL Server 环境中因为边际性能优势会超过偏移量为缺少的功能。  

 下表总结了可用的 HYPER-V 存储选项的优缺点:。  


|    **HYPER-V 存储类型**     |                                                                                                                                                                                                      **专业人员**                                                                                                                                                                                                       |                                                                                                                                                                                                                                                                                                                                                                                              **缺点**                                                                                                                                                                                                                                                                                                                                                                                              |                                                                                                                                                                                                                                                     **BizTalk Server 的注意事项**                                                                                                                                                                                                                                                      |
|---------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      **固定的大小磁盘**       | 因为物理硬盘上创建时，在其最大可能大小初始化的 VHD 文件的执行性能优于动态 VHD。<br /><br /> 这个问题，碎片算可能和，因此，缓解了一个单一的 I/O 被分成多个 I/o 的方案。 这具有 VHD 类型的最小 CPU 开销，因为读取和写入不需要查找块的映射。 |                                                                                                                                                                                                                                                                                                                                                                   需要完整的前期的磁盘空间量的分配。                                                                                                                                                                                                                                                                                                                                                                   |                                                                                                                   操作系统卷上使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 **重要说明：** 启动磁盘的 HYPER-V 来宾分区必须附加到 IDE 控制器。                                                                                                                   |
| **动态扩展磁盘** |                                                                                                        VHD 文件的大小增加到更多的数据存储在虚拟机本身上创建磁盘时指定的大小。 这适合于可用的存储最有效地使用。                                                                                                        | 不执行以及固定大小的 VHD。 这是因为在磁盘中的块清零块以启动但不是受任何 VHD 文件中的实际空间。 返回此类块中读取零的块。 第一个块时写入到中，虚拟化堆栈必须将 VHD 文件中的空间分配的块，然后更新相应的元数据。 除了这每次引用现有的块的块映射必须查找元数据中。 这会增加读取和写入活动，从而导致增加 CPU 使用率。<br /><br /> 动态增长，还需要服务器管理员监视磁盘容量，以确保有足够的磁盘存储作为存储需求的增长。 |                                                                                                                               不执行以及固定大小的 VHD。<br /><br /> 如果性能不是一个问题，例如在开发环境中，这可能是操作系统的硬盘驱动器的合适选项。<br /><br /> 导致块映射查找由于的额外 CPU 开销。                                                                                                                                |
|     **差异磁盘**      |                                                                               此差异磁盘存储相对于基本 VHD 和基本虚拟硬盘的所有更改的位置的父-子配置保持不变。 因此从父不同的块需要存储在差异 VHD 的子级。                                                                               |                                                                                                                                                                                                                                                                                                          因为需要访问固定/动态父 VHD，以及差异磁盘读/写，则可能会降低性能。 这会增加 CPU 使用率和磁盘 I/O 开销。                                                                                                                                                                                                                                                                                                           |                                                                                                                     BizTalk Server 安装需要大量的计算机特定的配置，子 VHD 文件可以增长显著的可尽量减少使用此磁盘配置的好处。 读取从多个 VHD 的在此方案中会产生额外的 CPU 和磁盘 I/O 开销。                                                                                                                     |
|      **传递磁盘**      |                                                                                                                               这些是物理磁盘设置为*脱机*在根分区和启用的 HYPER-V 和物理磁盘的独占读写访问。                                                                                                                                |                                                                                                                                                                                                                                                                                                        为了使它并将其分配到虚拟机需要完全专用的磁盘或 LUN。<br /><br /> 物理磁盘是比 VHD 文件在计算机之间移动的难度。                                                                                                                                                                                                                                                                                                         | 如果你[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例正在运行的 HYPER-V 上，可能会通过用于 BizTalk Server 数据卷使用固定虚拟硬盘 (VHD) 使用传递磁盘获得增量性能改进。<br /><br /> 如果要在托管本地文件接收位置在 BizTalk Server 上的或流式处理大消息处理期间磁盘，则可能会获得通过使用固定虚拟硬盘 (VHD) 使用传递磁盘的增量性能改进。 |

 有关实现磁盘和存储的 HYPER-V 的详细信息请参阅[实现磁盘和存储](http://go.microsoft.com/fwlink/?LinkID=142362)(http://go.microsoft.com/fwlink/?LinkID=142362)。  

##### <a name="networking"></a>网络  
 BizTalk Server 通常会表现出较高网络利用率。 因此，网络性能问题时，请考虑为每个虚拟机分配单独的物理网卡。  

 在配置虚拟机，请确保使用网络适配器，而不是旧版网络适配器。 旧版网络适配器适用于不支持集成组件的操作系统。  

 若要测量网络性能，请使用 **"\Network 接口 \Bytes 总数/秒"** 和**\Network 接口 (\*) \Output 队列长度**主机操作系统上的性能监视器计数器要测量的网络卡的整体性能的系统。 如果物理网络已被标识为处于忙碌，使用 **"\Hyper-V 虚拟网络适配器 (\*) \Bytes/sec"** 要识别哪些虚拟机网络适配器的主机操作系统上的计数器是正在生成高负载。  

 有关评估 HYPER-V 环境的网络性能的详细信息请参阅**测量网络性能**一部分[核对清单： 度量 HYPER-V 上的性能](../technical-guides/checklist-measuring-performance-on-hyper-v.md)。  

##### <a name="cpu"></a>CPU  
 HYPER-V 支持不同数量的虚拟处理器的不同的来宾操作系统：下表中进行了总结。 若要为 BizTalk Server 中分配的最大 CPU 资源，请将其安装在[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]来宾操作系统，支持每个虚拟机的四个虚拟处理器。  

 配置虚拟处理器的 1-1 分配到逻辑处理器可供主机操作系统，以防止过多的上下文切换的来宾操作系统中。 过多的处理器之间进行切换的上下文将导致性能下降。 有关分配虚拟处理器到逻辑处理器的详细信息，请参阅本主题的"优化处理器性能"部分[清单： 优化 HYPER-V 上的性能](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md)。  

 "虚拟机监控程序逻辑 processor （_total) \Hyper-V\\%总运行时间"性能监视器计数器测量的所有来宾计算机和虚拟机监控程序上的 HYPER-V 主机的整体资源利用率。 如果此值大于 90%，服务器正在运行以最大容量;在此方案中的虚拟机分配额外的虚拟处理器可能会降低整体系统性能，应当避免。 有关使用 HyperV 性能计数器的详细信息，请参阅[的 BizTalk Server 性能评估 HYPER-V](../technical-guides/evaluating-biztalk-server-performance-on-hyper-v.md)本指南的部分。  


|                                                                      操作系统                                                                       | 虚拟处理器限制 |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------|
| [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]的用户。 所有版本的[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]只有 64 位。 |            4            |
|                                               [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 64 位                                               |            4            |
|                                               [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 32 位                                               |            4            |
|                                                                      Windows 7 64 位                                                                       |            4            |
|                                                                      Windows 7 32 位                                                                       |            4            |
|                                                                    64 位 Windows Vista                                                                     |            2            |
|                                                                    Windows Vista 32 位                                                                    |            2            |

> [!NOTE]  
>  有关 HYPER-V 支持的来宾操作系统的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkID=118347 ](http://go.microsoft.com/fwlink/?LinkID=118347)。  

##### <a name="memory"></a>内存  
 物理服务器需要足够的内存为根分区和在服务器上运行任何虚拟机。 在测试期间，至少 2 GB 的内存已分配到根分区并**可用内存兆字节**性能监视器计数器进行监控，以确保没有内存压力，就会出现。  

 应分配给 BizTalk Server 环境中每个虚拟机的内存量取决于工作负荷，并将执行的处理的类型。 有许多因素会影响内存需求的 BizTalk Server 包括：  

- 处理的消息的大小  

- 消息的吞吐量  

- 业务流程设计  

- 管道处理  

- 你打算运行虚拟机中的 BizTalk 主机的数目  

  因素会影响内存的完整列表，请参阅"性能因素"部分中的 BizTalk Server 性能优化指南，网址[ http://go.microsoft.com/fwlink/?LinkId=122587 ](http://go.microsoft.com/fwlink/?LinkId=122587)。  

  主动监视**可用内存兆字节**计数器从每个虚拟机和根分区本身中。 从以下指导原则[清单： 度量 HYPER-V 上的性能](../technical-guides/checklist-measuring-performance-on-hyper-v.md)应该用于确定是否有足够的可用物理内存的虚拟机并为根分区：  

- 内存可用的 50%或更多 = 正常  

- 25%的内存可用 = 监视  

- 10%的内存可用 = 警告  

- 小于 5%的内存可用 = 关键，性能将受到负面影响  

#### <a name="choosing-root-operating-system-version"></a>选择根操作系统版本  
 有关服务器核心，以及在完整安装的支持的 HYPER-V [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。 若要在根分区的开销降到最低，安装 HYPER-V 的服务器核心安装上[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。 可以从不同的系统上的 HYPER-V 管理器远程管理的 HYPER-V 角色。 服务器核心提供了一个较小磁盘和内存配置文件，因此，会让更多资源可用于虚拟机。 有关服务器核心安装选项可用于详细信息[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]，请参阅[ http://go.microsoft.com/fwlink/?LinkID=202439 ](http://go.microsoft.com/fwlink/?LinkID=202439)。  

 如果您选择使用完整安装的[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]，请确保根分区专用于 HYPER-V 服务器角色。 运行其他服务器角色会占用内存、 磁盘、 处理器和网络资源，将会降低性能。  

#### <a name="creating-your-virtual-machines"></a>创建虚拟机  
 已安装并配置 HYPER-V 服务器角色之后，您需要创建虚拟机。 在此之前，最好回答以下问题：  

- 将使用哪些存储配置？  

- 来宾操作系统支持虚拟处理器数目？  

- 将到虚拟机分配多少内存？  

- 在我的 HYPER-V 服务器上可以运行多少个虚拟机？  

- 如何将安装到计算机上的操作系统？  

  有关如何创建和配置虚拟机的详细信息，请参阅[创建虚拟机](http://go.microsoft.com/fwlink/?LinkID=202440)。  

##### <a name="installing-the-base-operating-system"></a>安装基本操作系统  
 可用于在物理服务器上安装的所有选项都都可用的 HYPER-V 中。 可启动 CD/DVD-ROM 媒体或 ISO 映像可用于执行手动安装。 如果已使用连接到承载的 ISO 映像的服务器所在的同一网络的网络适配器配置虚拟机，可以执行网络安装。  

> [!IMPORTANT]  
>  无论安装哪种方法是选择，出于性能原因很重要的操作系统集成组件安装在 HYPER-V 下运行每个虚拟机。 集成组件提供驱动程序和服务，可让来宾机器使用合成设备执行的一的组。 合成设备避免需要模拟设备，不支持集成组件的操作系统使用。 模拟的设备会产生更大的系统开销相比合成设备。  

 若要安装和配置本实验室中使用的计算机，初始的基本映像已创建固定大小的 VHD。 这涉及到手动安装[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。 一旦已安装所有合适的更新基础虚拟机进行映像使用 sysprep 实用工具 %WINDIR%\system32\sysprep 目录中与 Windows Server 2008 一起安装。  

> [!NOTE]
>  运行 Sysprep 后已安装并在服务器上配置 BizTalk Server 可以通过使用 Sysprep 应答文件和 BizTalk Server 提供的脚本来完成。 向 BizTalk Server 上安装这些示例脚本专供[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。 有关详细信息，请参阅 BizTalk Server 联机文档。  

## <a name="installing-and-configuring-biztalk-server"></a>安装和配置 BizTalk Server  

- 若要最小化安装虚拟机所需的时间，创建基本映像仅包含来宾操作系统和软件先决条件。 使用 SysPrep 来准备的 VHD 映像以供重复使用，，然后使此 VHD 上的所有虚拟机 (Vm)。  

  > [!NOTE]
  >  使用 BizTalk Server，则可以对基本映像运行 Sysprep*后*已安装并在服务器上配置 BizTalk Server。 这可以通过使用 Sysprep 应答文件和脚本提供与 BizTalk Server 来实现。 向 BizTalk Server 上安装这些示例脚本专供[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。 有关详细信息，请参阅 BizTalk Server 联机文档。  
  > 
  >  无人参与 Windows 安装程序参考位于[ http://go.microsoft.com/fwlink/?LinkId=142364 ](http://go.microsoft.com/fwlink/?LinkId=142364)。  

- 请按照"时安装和配置 BizTalk Server..."中的建议 主题的部分[清单： 安装和配置 HYPER-V 上的 BizTalk Server 的最佳实践](../technical-guides/checklist-best-practices-to-install-and-configure-biztalk-server-on-hyper-v.md)。  

- 有关信息的可支持性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]并[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]在 HYPER-V 环境中，请参阅[附录 c: BizTalk Server 和 SQL Server 的 HYPER-V 可支持性](../technical-guides/appendix-c-biztalk-server-and-sql-server-hyper-v-supportability.md)。
