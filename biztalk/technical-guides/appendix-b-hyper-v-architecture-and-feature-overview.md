---
title: "附录 b: HYPER-V 体系结构和功能概述 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87b6b9a0-a470-43f7-b076-36075477cc34
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e6282b6f5a5784b80d58a1a1737389ee23e01e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="appendix-b-hyper-v-architecture-and-feature-overview"></a>附录 b: HYPER-V 体系结构和功能概述
本主题提供了 HYPER-V 体系结构的概述，描述 HYPER-V 的优点和缺点。  
  
## <a name="hyper-v-architecture"></a>HYPER-V 体系结构  
  
 HYPER-V 是基于虚拟机监控程序的虚拟化平台和之一项使能技术[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]的先进功能，实时迁移。 与 HYPER-V 版本 1.0，Windows Server 2008 时能够快速迁移，无法使用仅为几秒钟的停机时间的物理主机之间移动虚拟机。 使用实时迁移，物理目标之间移动发生毫秒，这意味着迁移操作变得对连接的用户不可见。 若要了解中新功能和改进[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]HYPER-V，请参阅[What's New in Windows Server 2008 R2 中 HYPER-V](http://go.microsoft.com/fwlink/?LinkID=202427)。  
  
 虚拟机监控程序是特定于处理器的虚拟化平台，可以托管多个虚拟机 (Vm)，相互隔离，但通过虚拟化的处理器、 内存和输入/输出设备共享基础硬件资源。  
  
 HYPER-V 虚拟机中运行的来宾操作系统提供性能接近在物理硬件上运行的操作系统性能*如果*必要的虚拟服务器客户端 (VSC) 驱动程序和服务来宾操作系统上安装。 HYPER-V 虚拟服务器客户端 (VSC) 代码，也称为 HYPER-V 启用 I/O，支持对 HYPER-V"虚拟机总线"直接访问以及可在安装了 HYPER-V 集成服务。 同时[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]和[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]支持 HYPER-V 启用 I/O 与 HYPER-V 集成服务。 提供 VSC 驱动程序的 HYPER-V 集成服务也已可用于其他客户端操作系统的系统。  
  
 HYPER-V 支持按分区隔离。 分区是隔离的由虚拟机监控程序，执行操作系统的支持的逻辑单元。 Microsoft 虚拟机监控程序必须至少一个父级或根，分区，运行[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。 虚拟化堆栈在父分区中运行，并直接访问硬件设备。 然后，根分区创建子分区中的承载于来宾操作系统。 根分区创建子分区使用 hypercall 应用程序编程接口 (API)。  
  
 分区的确可以访问物理处理器，也不它们处理处理器中断。 相反，它们有一个虚拟处理器的视图，专用于每个来宾分区的虚拟内存地址区域中运行。 虚拟机监控程序处理对处理器的中断操作，并将他们重定向到相应的分区。 此外可以 HYPER-V 硬件加速的地址转换之间通过输入输出内存管理单元 (IOMMU) 进行操作独立于使用的 CPU 内存管理硬件的各种来宾虚拟地址空间。 IOMMU 用于重新映射到子分区都使用的地址的物理内存地址。  
  
 子分区也并不一定直接访问其他硬件资源的资源的虚拟视图显示为虚拟设备 (Vdev)。 通过 VMBus 或虚拟机监控程序在父分区中，处理请求的设备，则将重定向到虚拟设备的请求。 VMBus 是一个逻辑间分区通信通道。 父分区承载虚拟化服务提供程序 (Vsp) 通过 VMBus 以处理来自子分区的设备访问请求进行通信。 子分区承载虚拟化服务使用方 (Vsc) 将设备请求重定向到 Vsp 通过 VMBus 的父分区中。 此整个过程是透明的来宾操作系统。  
  
 虚拟设备还可以利用一个名为存储、 网络、 图形和输入的子系统的启用 I/O 的 Windows Server 虚拟化功能。 启用的 I/O 是利用 VMBus 直接，绕过任何设备仿真层的高级别的通信协议 （如 SCSI) 的专用的虚拟化感知实现。 这使得通信更加有效，但需要是虚拟机监控程序和 VMBus 感知的启用的来宾。 HYPER-V 启用 I/O 和虚拟机监控程序感知内核提供通过 HYPER-V integration services 的安装。 集成组件，包括虚拟服务器客户端 (VSC) 驱动程序，也是可用的其他客户端操作系统的系统。 HYPER-V 需要一个处理器，包括硬件辅助虚拟化，如提供具有 Intel VT 或 AMD 虚拟化 (AMD-V) 技术。  
  
 下图提供 Windows Server 2008 上运行的 HYPER-V 环境的体系结构的高级概述。  
  
 ![Hyper &#45;V 体系结构概述](../technical-guides/media/eadd2a84-3936-4b48-a0e2-05b94882d848.gif "eadd2a84-3936-4b48-a0e2-05b94882d848")  
HYPER-V 体系结构的概述  
  
 首字母缩略和上面的关系图中使用的术语如下所述：  
  
-   **APIC** – 高级可编程中断控制器。 将输出允许优先级级别分配给它的中断的设备。  
  
-   **子分区**– 承载来宾操作系统的分区。 对物理内存和按子分区的设备的所有访问可通过虚拟机总线 (VMBus) 或虚拟机监控程序都提供。  
  
-   **Hypercall** – 虚拟机监控程序与进行通信的接口。 Hypercall 接口还包含对提供的虚拟机监控程序的优化访问。  
  
-   **虚拟机监控程序**– 一个位于之间的硬件要求和一个或多个操作系统的软件层。 其主要任务是提供隔离的执行环境调用分区。 虚拟机监控程序控制，并且仲裁访问基础硬件。  
  
-   **IC** – 集成组件。 允许子分区移到与其他分区和虚拟机监控程序的通信的组件。  
  
-   **I/O 堆栈**– 输入/输出堆栈。  
  
-   **MSR** – 内存服务例程。  
  
-   **根分区**– 管理设备驱动程序、 电源管理和设备热添加/删除等的计算机级函数。 根域 （或父） 分区是直接访问物理内存和设备的唯一分区。  
  
-   **VID** – 虚拟化基础结构驱动程序。 提供分区管理服务、 虚拟处理器管理服务和内存管理服务的分区。  
  
-   **VMBus** – 基于通道的通信机制，用于在具有多个活动的虚拟化分区系统上的分区间通信和设备枚举。 与 HYPER-V 集成服务，并安装 VMBus。  
  
-   **VMMS** – 虚拟机管理服务。 负责管理子分区中的所有虚拟机的状态。  
  
-   **VMWP** – 虚拟机工作进程。 虚拟化堆栈某个用户模式组件。 工作进程提供从虚拟机管理服务[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]在父分区中的子分区的来宾操作系统的实例。 虚拟机管理服务生成每个正在运行的虚拟机的单独的辅助进程。  
  
-   **VSC** – 虚拟化服务客户端。 合成设备实例，该实例驻留在子分区。 Vsc 利用提供的虚拟化服务提供程序 (Vsp) 父分区中的硬件资源。 它们通过与通信在父分区相应 Vsp VMBus 以满足子分区设备 I/O 请求。  
  
-   **VSP** – 虚拟化服务提供程序。 驻留在根分区中，虚拟机总线 (VMBus) 通过提供综合设备支持添加到子分区。  
  
-   **WinHv** – Windows 虚拟机监控程序接口库。 WinHv 是实质上是分区的操作系统的驱动程序和虚拟机监控程序这样驱动程序以调用虚拟机监控程序使用标准 Windows 调用约定之间的桥梁  
  
-   **WMI** – 虚拟机管理服务公开一组基于 Windows Management Instrumentation WMI Api 来管理和控制虚拟机。  
  
 在中定义其中的大多数术语[Glossary8](../technical-guides/glossary8.md)。  
  
> [!NOTE]  
>  有关详细信息[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]HYPER-V，请参阅[http://go.microsoft.com/fwlink/?LinkID=121187](http://go.microsoft.com/fwlink/?LinkID=121187)。  
  
## <a name="advantages-of-hyper-v"></a>Hyper V 的优点  
 在 HYPER-V 虚拟化环境中运行企业级解决方案的优点包括：  
  
1.  **硬件资源合并**-多个物理服务器可轻松地合并到相对较少服务器通过实现与 HYPER-V 虚拟化。 合并能够适应充分利用已部署的硬件资源。 Windows Server 2008 R2 中 HYPER-V 现在可以访问的主机计算机上的最多为 64 逻辑 Cpu。 此功能不仅充分利用新的多核系统，它还意味着更高的虚拟机整合率，每个物理主机。  
  
2.  **易管理性**:  
  
    -   合并的资源的集中，可以简化管理。  
  
    -   向上缩放和向外的扩展的实现被容纳多更易于使用。  
  
3.  **有效方面可节省成本**:  
  
    -   显著降低硬件成本，因为多个虚拟机可以在单个物理计算机上运行，因此，不需要为每台计算机单独的物理计算机。  
  
    -   HYPER-V 许可成本所含的许可成本[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。 此外可以用作独立的产品，可以安装在购买 HYPER-V[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]服务器核心。  
  
    -   通过将合并到虚拟化 HYPER-V 环境由于减少了物理硬件"占用空间"的现有应用程序，可能会显著降低 power 要求所需。  
  
4.  **错误通过 HYPER-V 群集的容差支持**– 因为 HYPER-V 是群集感知应用程序，[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]提供本机主机群集在 HYPER-V 虚拟化环境中创建的虚拟机的支持。  
  
5.  **易于部署和管理**:  
  
    -   现有服务器合并到较少的物理服务器可以简化部署。  
  
    -   与 System Center Virtual Machine Manager 中提供了全面的 HYPER-V 管理解决方案。 有关 System Center Virtual Machine Manager 的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkID=111303](http://go.microsoft.com/fwlink/?LinkID=111303)。  
  
6.  **密钥 HYPER-V 性能特征**:  
  
    -   **共享体系结构的改进的硬件**-Hyper V 提供提高访问权限和核心资源，例如磁盘、 网络、 利用率和视频时运行来宾操作系统的系统的虚拟机监控程序感知内核和配有必备项的虚拟服务器客户端 (VSC) 代码 （称为 HYPER-V 启用 I/O）。 启蒙为以减少某些操作系统功能，例如内存管理成本对操作系统所做的增强功能。 目前，同时[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]和[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]支持 HYPER-V 启用 I/O 和虚拟机监控程序感知内核通过 HYPER-V integration services 的安装。 集成组件，包括 VSC 驱动程序，也是可用的其他客户端操作系统的系统。  
  
         磁盘性能至关重要的磁盘 I/O 密集型企业应用程序，如 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和除了 HYPER-V 启用 I/O;HYPER-V 提供的"传递"磁盘支持，从而提供可与物理磁盘性能相媲美的磁盘性能。 请注意"传递"磁盘支持，提供改进的性能，以较小的成本，为方便起见。 "传递"的磁盘是实质上是物理磁盘/Lun，它们附加到虚拟机并不支持某些功能的虚拟磁盘，例如虚拟机快照。  
  
    -   **处理器硬件辅助虚拟化支持**– HYPER-V 充分利用适用于最新的处理器技术的处理器硬件辅助虚拟化支持。  
  
    -   **多核 (SMP) 来宾操作系统支持**– HYPER-V 提供了在虚拟机环境中，它允许应用程序中的虚拟充分利用多线程处理功能支持最多四个处理器的能力机。  
  
    -   **32 位和 64 位来宾操作系统支持**– HYPER-V 提供广泛支持同时运行的不同类型的操作系统，包括跨不同的服务器平台，例如 Windows 的 32 位和 64 位系统Linux®，和其他人。  
  
7.  **经验证的跟踪记录**-密钥 Microsoft Web 站点 MSDN ([http://msdn.microsoft.com](http://go.microsoft.com/fwlink/?LinkId=122019)) 和 TechNet ([http://technet.microsoft.com](http://go.microsoft.com/fwlink/?LinkID=64380)) 在 HYPER-V 环境中托管。  
  
8.  **全面的产品支持**– Microsoft Microsoft 企业应用程序 （例如 Exchange Server 和 SQL Server） 进行完全测试在 HYPER-V 中运行，因为已部署和运行在 HYPER-V 中时在这些应用程序提供了代码修复支持环境。  
  
9. **可伸缩性**– 其他处理电源、 网络带宽和存储容量，可以快速轻松地通过实现分派到来宾虚拟机从主计算机的其他可用资源。 这可能需要升级主机或来宾虚拟机在移动到功能更强大的主机计算机。  
  
 有关详细信息的有关的好处的利用随 HYPER-V 一起提供的虚拟化技术的深入信息，请参阅[虚拟化优势](http://go.microsoft.com/fwlink/?LinkID=202419)的[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。  
  
## <a name="disadvantages-of-hyper-v"></a>Hyper V 的缺点  
 在 HYPER-V 虚拟化环境中运行企业级解决方案的一些缺点可能包括：  
  
-   **硬件要求 –**由于服务器合并的需求，HYPER-V 虚拟机倾向于使用更多的 CPU 和内存，并且需要更大的磁盘 I/O 带宽比具有可比较的计算负载的物理服务器。 由于 HYPER-V 服务器角色可用的仅为 64 位和所有版本的 Windows Server 2008 R2 只有 64 位物理硬件必须支持硬件辅助虚拟化。 这意味着必须是具有 Intel VT 或 AMD 虚拟化 (AMD-V) 技术兼容的处理器、 系统 BIOS 必须支持数据执行保护 (DEP)，并且必须支持 DEP。  
  
-   **软件要求 –**尽管大多数 Microsoft 软件支持 HYPER-V 虚拟机上运行，某些 Microsoft 软件正在仍然正在进行测试以确保与 HYPER-V 虚拟化环境的兼容性。 例如，大多数 Microsoft 企业级应用程序支持在 HYPER-V 上运行或正在要测试其 HYPER-V 上的支持。 所有版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]由于[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]支持在 HYPER-V 上运行。 有关详细信息的可支持性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]上 HYPER-V，请参阅[附录 c: BizTalk Server 和 SQL Server HYPER-V 可支持性](../technical-guides/appendix-c-biztalk-server-and-sql-server-hyper-v-supportability.md)。