---
title: "清单： 安装和配置 HYPER-V 上的 BizTalk Server 的最佳实践 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b5ddbb5-3752-4294-ae6a-c14363b3ddc9
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edfc6a24053579ca7dfdd4d0ad64173b962d3c0b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-best-practices-for-installing-and-configuring-biztalk-server-on-hyper-v"></a>清单： 安装和配置 HYPER-V 上的 BizTalk Server 的最佳做法
下面的部分是安装的摘要和中所述的配置要求[HYPER-V 上部署 BizTalk Server](../technical-guides/deploying-biztalk-server-on-hyper-v.md)本指南的部分。 应将这些用作时安装、 配置和部署的快速参考[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 HYPER-V 环境中。 有关详细信息提供了指向相关部分。  
  
## <a name="before-installing-hyper-v"></a>然后才能安装 HYPER-V...  
  
|步骤|参考|  
|----------|---------------|  
|HYPER-V 是可用于 64 位和的所有版本的服务器角色[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]都只能是 64 位。|请参阅主题**HYPER-V 安装先决条件**在[http://go.microsoft.com/fwlink/?LinkId=142350](http://go.microsoft.com/fwlink/?LinkId=142350)。|  
|确保你的处理器支持硬件辅助虚拟化和数据执行保护 (DEP)，并且这些功能已启用。 这需要具有 Intel 虚拟化技术 (Intel VT) 或 AMD 虚拟化 (AMD-V) 兼容的处理器。|请参阅主题**HYPER-V 安装先决条件**在[http://go.microsoft.com/fwlink/?LinkId=142350](http://go.microsoft.com/fwlink/?LinkId=142350)。|  
|使用[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]根分区的核心版。 这将服务器开销降到最低并提高 HYPER-V 性能。|请参阅主题**在 Server Core 安装的 Windows Server 2008 R2 上安装 HYPER-V 角色**在[http://go.microsoft.com/fwlink/?LinkID=202131](http://go.microsoft.com/fwlink/?LinkID=202131)。|  
|在根分区上运行 HYPER-V 的服务器角色。|从**性能优化的虚拟化服务器**部分**性能优化准则的 Windows Server 2008 R2**白皮书下载[http://go.microsoft.com/fwlink/？LinkID = 202087](http://go.microsoft.com/fwlink/?LinkID=202087):<br />**专用的服务器角色**<br />根分区应将专用于虚拟化服务器角色。 其他服务器角色可以产生不良影响的虚拟化服务器的性能，尤其是如果它们使用大量的 CPU、 内存或 I/O 带宽。 最小化根分区中的服务器角色中还有其他好处，如减少攻击面和更新的频率。 根分区中安装哪个软件，因为某些软件可能会与虚拟化服务器的总体性能产生负面影响，系统管理员应仔细考虑。|  
  
## <a name="when-creating-hyper-v-virtual-machines"></a>创建 HYPER-V 虚拟机时...  
  
|步骤|参考|  
|----------|---------------|  
|使用固定的大小虚拟硬盘 (VHD) 提供相比为操作系统驱动器动态调整大小的 Vhd 的改进的性能。|从**性能优化的虚拟化服务器**部分**性能优化准则的 Windows Server 2008 R2**白皮书下载[http://go.microsoft.com/fwlink/？LinkID = 202087](http://go.microsoft.com/fwlink/?LinkID=202087): <br />**固定大小的 VHD**<br />创建 VHD 文件时，首先分配为 VHD 的空间。 这种类型的 VHD 是不太 apt 拆分，这将降低 I/O 吞吐量，当一个单一的 I/O 被拆分为多个 I/o。 它具有三种的 VHD 类型的最低 CPU 开销，因为读取和写入不需要查找的块的映射。|  
|使用固定大小虚拟硬盘 (VHD) 磁盘进行高的磁盘 I/O 活动并配置为使用 SCSI 控制器的数据卷的磁盘。 对于跨多个数据驱动器的高密集型存储 I/O 工作负荷，应将每个 VHD 附加到更好的总体性能的单独合成 SCSI 控制器。 此外，每个 VHD 应存储在单独的物理磁盘上。|从**性能优化的虚拟化服务器**部分**性能优化准则的 Windows Server 2008 R2**白皮书下载[http://go.microsoft.com/fwlink/？LinkID = 202087](http://go.microsoft.com/fwlink/?LinkID=202087):<br />**合成 SCSI 控制器**<br />综合存储控制器上减少 CPU 开销低于模拟的 IDE 设备使用的存储 I/o 提供显著提高性能。 VM 集成服务包括启用为此存储设备驱动程序和所需的来宾操作系统可以检测到它。 必须在 IDE 设备要正常，启动的操作系统上安装操作系统磁盘，但 VM 集成服务加载到综合存储设备的 IDE 设备 i/0，则重新确定筛选器驱动程序。<br />我们强烈建议你装载直接到综合的 SCSI 控制器的数据驱动器，因为该配置已减少 CPU 开销。 如果其预期的 I/O 率很高，你还应装载日志文件和操作系统分页文件直接到综合的 SCSI 控制器。<br />对于跨多个数据驱动器的高密集型存储 I/O 工作负荷，应将每个 VHD 附加到更好的总体性能的单独合成 SCSI 控制器。 此外，每个 VHD 应存储在单独的物理磁盘上。|  
|SCSI 控制器用于将 VHD 磁盘用于高 I/O 行为，如附加 SQL Server 数据和日志文件。 **注意：**不要将系统磁盘连接到 SCSI 控制器。 包含操作系统虚拟硬盘必须连接到 IDE 控制器。|即使 HYPER-V IDE 控制器和 SCSI 控制器提供水平相当的性能，如果已安装 HYPER-V 集成服务，可以仅将安装的 SCSI 控制器。 因此，附加传递磁盘的 SCSI 控制器的使用将确保 HYPER-V 集成服务安装这反过来将确保最佳磁盘 I/O 性能。|  
|配置虚拟机的网络时，请使用网络适配器而不是旧版网络适配器。 旧版网络适配器用于不支持集成组件的操作系统。|从**性能优化的虚拟化服务器**部分**性能优化准则的 Windows Server 2008 R2**白皮书下载[http://go.microsoft.com/fwlink/？LinkID = 202087](http://go.microsoft.com/fwlink/?LinkID=202087):<br />**合成网络适配器**<br />相比到仿真的网络适配器，以模拟现有硬件，专为虚拟机以实现显著设计的合成网络适配器能减少 CPU 开销的 HYPER-V 功能将网络 I/O。 合成网络适配器之间的子和根分区通过 VMBus 通过使用共享的内存更高效的数据传输进行通信。 仿真的网络适配器应通过的 VM 的设置对话框删除并替换的合成网络适配器。 来宾要求安装 VM 集成服务。|  
|确保 integration services 在任何启用的来宾操作系统上安装和验证安装了集成服务的最新版本。 若要检查的最新版本的 integration services，连接到[http://go.microsoft.com/fwlink/?LinkID=202449](http://go.microsoft.com/fwlink/?LinkID=202449)或运行**Windows Update**从**启动**菜单。|从**性能优化的虚拟化服务器**部分**性能优化准则的 Windows Server 2008 R2**白皮书下载[http://go.microsoft.com/fwlink/？LinkID = 202087](http://go.microsoft.com/fwlink/?LinkID=202087):<br />**启用的来宾**<br />在操作系统内核[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]， [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]，功能启蒙优化 Vm 其操作。 为了获得最佳性能，我们建议你使用[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]作为来宾操作系统。 启蒙降低在 VM 中运行的 Windows 的 CPU 开销。 集成服务提供其他启蒙针对 I/O。 具体取决于服务器负载，则可以适当是托管服务器应用程序在 Windows Server 2008 的来宾即可获得更好的性能。|  
|只要有可能，配置到可用的逻辑处理器的虚拟处理器的 1-1 分配。|有关配置虚拟处理器分配给可用的逻辑处理器的 1 对 1 分配的详细信息，请参阅中的"优化处理器性能"部分[清单： HYPER-V 上优化性能](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md)。|  
|转换或将 Microsoft Virtual PC、 Microsoft Virtual Server 或在 HYPER-V 上运行的 VMWare ESX Server 上运行的虚拟机迁移。|使用 System Center Virtual Machine Manager 2008 R2，将转换或迁移虚拟机以在 HYPER-V 上运行。 有关详细信息，请参阅 》 在主题"V2V:: 转换虚拟机到 VMM 虚拟机" [http://go.microsoft.com/fwlink/?LinkId=146342](http://go.microsoft.com/fwlink/?LinkId=146342)。<br />-如果需要，可以手动执行将转换 Microsoft Virtual PC 或 Microsoft 虚拟服务器上运行的虚拟机的过程。 有关详细信息，请参阅 》 在主题"虚拟机迁移指南:: 如何为迁移从虚拟服务器到 HYPER-V" [http://go.microsoft.com/fwlink/?LinkID=137258](http://go.microsoft.com/fwlink/?LinkID=137258)。<br />-该示例工具**VMC2Hyper V**还用于迁移到 HYPER-V Microsoft Virtual PC 或 Microsoft 虚拟服务器上运行的虚拟机。 有关 VMC2Hyper V 示例工具的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkID=135683](http://go.microsoft.com/fwlink/?LinkID=135683)。 **注意：** Microsoft，不支持使用此工具和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。|  
  
## <a name="when-installing-and-configuring-biztalk-server"></a>安装和配置 BizTalk Server 时...  
 在安装时[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]在虚拟环境中，相同的做法，应遵循与物理环境。 安装和配置期间，应使用以下资源[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]:  
  
|步骤|参考|  
|----------|---------------|  
|有关如何安装的说明[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]上来宾操作系统，请参阅[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]安装指南。|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装指南位于[http://go.microsoft.com/fwlink/?LinkID=191321](http://go.microsoft.com/fwlink/?LinkID=191321)。|  
|运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上完成的最佳做法分析器 (BPA) 工具[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]安装。|在 BPA 工具位于[http://go.microsoft.com/fwlink/?LinkID=196491](http://go.microsoft.com/fwlink/?LinkID=196491)。|  
|如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库要驻留在[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]，运行[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]上的最佳做法分析器 (BPA) 工具[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]之前配置的实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。|[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]最佳做法分析器位于[http://go.microsoft.com/fwlink/?LinkID=202133](http://go.microsoft.com/fwlink/?LinkID=202133)。|  
|Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]操作指南提供的操作的准备情况清单可以用于确保已安装所有必需的必备软件。 这些清单提供[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]针对作为的一部分所需的所有组件提供的特定的配置信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包括操作系统、 IIS 和 SQL Server 的堆栈。 此外，有关如何配置 BizTalk Server 的高可用性提供指导。|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]操作指南位于[http://go.microsoft.com/fwlink/?LinkId=110533](http://go.microsoft.com/fwlink/?LinkId=110533)。|  
|请按照指南的"优化性能"部分中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能优化指南来优化性能的你[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]安装。|超链接"http://msdn.microsoft.com/en-us/library/cc296643.aspx"[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]超链接"http://msdn.microsoft.com/en-us/library/cc558617.aspx"性能优化指南位于[http://go.microsoft.com/fwlink/?LinkId=122579](http://go.microsoft.com/fwlink/?LinkId=122579)。|  
|请考虑安装和运行 BizTalk MsgBoxViewer 实用程序来分析和验证 BizTalk Server MessageBox 数据库的配置。|BizTalk MsgBoxViewer 实用工具位于[http://go.microsoft.com/fwlink/?LinkID=117289](http://go.microsoft.com/fwlink/?LinkID=117289)。 **注意：** Microsoft，不支持使用此工具和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。|  
|验证 CPU 在 HYPER-V 中运行的来宾操作系统正在正确分配。|在"测量处理器性能"部分[清单： HYPER-V 上的测量性能](../technical-guides/checklist-measuring-performance-on-hyper-v.md)。|