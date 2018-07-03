---
title: '附录 b: HYPER-V 体系结构和功能概述 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87b6b9a0-a470-43f7-b076-36075477cc34
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9e20add207d9e4303bd823b82b79e8fad6c07c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002142"
---
# <a name="appendix-b-hyper-v-architecture-and-feature-overview"></a>附录 b: HYPER-V 体系结构和功能概述
本主题提供了 HYPER-V 体系结构的概述，描述了 HYPER-V 的优点和缺点。  
  
## <a name="hyper-v-architecture"></a>HYPER-V 体系结构  
  
 HYPER-V 是基于虚拟机监控程序的虚拟化平台和技术可一个 Windows Server 的先进功能，实时迁移。 使用 HYPER-V，Windows Server 是能够快速迁移，可以使用仅在几秒钟的停机时间的物理主机之间移动 Vm。 通过实时迁移物理目标之间移动发生毫秒，这意味着迁移操作变得对已连接的用户不可见。 请参阅[什么是 Windows Server 上的 HYPER-V 中的新增功能](https://docs.microsoft.com/windows-server/virtualization/hyper-v/what-s-new-in-hyper-v-on-windows)。
  
 虚拟机监控程序是特定于处理器的虚拟化平台，可以托管多个虚拟机 (Vm) 的相互隔离的但通过虚拟化的处理器、 内存和 I/O 设备共享的基础硬件资源。  
  
 HYPER-V 虚拟机中运行的来宾操作系统提供性能接近物理硬件上运行的操作系统性能*如果*必要的虚拟服务器客户端 (VSC) 驱动程序和服务安装来宾操作系统上。 HYPER-V 虚拟服务器客户端 (VSC) 代码，也称为 HYPER-V 启用 I/O、 可直接访问 HYPER-V"虚拟机总线"，可在安装了 HYPER-V 集成服务。 提供 VSC 驱动程序的 HYPER-V 集成服务也已可供其他客户端操作系统。  
  
 HYPER-V 支持在一个分区方面的隔离。 分区是隔离的通过虚拟机监控程序，在其中执行操作系统支持的逻辑单元。 Microsoft 虚拟机监控程序必须具有至少一个父级，即根分区中，运行 Windows Server。 虚拟化堆栈在父分区中运行，并直接访问硬件设备。 然后，根分区创建子分区承载的来宾操作系统的。 根分区创建子分区使用 hypercall 应用程序编程接口 (API)。  
  
 分区不能访问到物理处理器，也请务必处理处理器中断。 相反，它们有一个虚拟处理器的视图，专用于每个来宾分区的虚拟内存地址区域中运行。 虚拟机监控程序处理中断处理器，并将它们重定向到相应的分区。 HYPER-V 还可以通过使用输入输出内存管理单元 (IOMMU) 进行操作独立于使用的 CPU 的内存管理硬件的各种来宾虚拟地址空间之间硬件加速的地址转换。 IOMMU 用于重新映射到的地址的子分区都使用的物理内存地址。  
  
 子分区也不具有直接访问其他硬件资源，并将表示为虚拟设备 (Vdev) 的资源的虚拟视图。 通过 VMBus 或虚拟机监控程序为父分区，处理的请求中的设备，则将重定向到虚拟设备的请求。 VMBus 是逻辑内分区通信通道。 父分区托管虚拟化服务提供商 (Vsp) 通过 VMBus 以处理来自子分区的设备访问请求进行通信。 子分区托管虚拟化服务使用者 (Vsc) 将设备请求重定向到 Vsp VMBus 通过父分区中。 整个过程是透明的来宾操作系统。  
  
 虚拟设备还可以利用 Windows Server 虚拟化功能，启用 I/O 命名的存储、 网络、 图形和输入的子系统。 已启用的 I/O 是利用 VMBus 直接绕过任何设备仿真层的高级别的通信协议 （如 SCSI) 的专用虚拟化感知实现。 这使通信更高效，但需要为虚拟机监控程序和 VMBus 注意已启用的来宾。 HYPER-V 启用 I/O 和虚拟机监控程序注意内核提供通过 HYPER-V integration services 的安装。 集成组件，其中包括虚拟服务器客户端 (VSC) 驱动程序，也已可供其他客户端操作系统。 HYPER-V 需要硬件辅助虚拟化，包括如一个处理器提供与 Intel VT 或 AMD 虚拟化 (AMD-V) 技术。  
  
 下图提供了 Windows Server 上运行的 HYPER-V 环境的体系结构的高级概述。  
  
 ![Hyper&#45;V 体系结构概述](../technical-guides/media/eadd2a84-3936-4b48-a0e2-05b94882d848.gif "eadd2a84-3936-4b48-a0e2-05b94882d848")  

  
 首字母缩写词和上面的关系图中使用的术语如下所述：  
  
- **APIC** – 高级可编程中断控制器。 允许优先级别分配给它的中断的设备输出。  
  
- **子分区**– 承载来宾操作系统的分区。 通过虚拟机总线 (VMBus) 或虚拟机监控程序提供对物理内存和通过子分区的设备的所有访问。  
  
- **Hypercall** – 与虚拟机监控程序进行通信的接口。 Hypercall 接口还包含对提供的虚拟机监控程序的优化访问。  
  
- **虚拟机监控程序**– 位于硬件和一个或多个操作系统之间的软件层。 其主要工作是提供名为分区的独立的执行环境。 虚拟机监控程序控制并进行仲裁对基础硬件的访问。  
  
- **IC** – 集成组件。 允许子分区移到与其他分区和虚拟机监控程序进行通信的组件。  
  
- **I/O 堆栈**– 输入/输出堆栈。  
  
- **MSR** – 内存服务例程。  
  
- **根分区**– 管理计算机级别的功能，如设备驱动程序、 电源管理和设备热添加/删除。 根 （或父） 分区是直接访问物理内存和设备的唯一分区。  
  
- **VID** – 虚拟化基础结构驱动程序。 提供分区管理服务、 虚拟处理器管理服务和内存管理服务的分区。  
  
- **VMBus** – 基于通道的通信机制，用于具有多个活动的虚拟化分区的系统上的分区间通信和设备枚举。 VMBus 随 HYPER-V 集成服务。  
  
- **VMMS** – 虚拟机管理服务。 负责管理子分区中的所有虚拟机的状态。  
  
- **VMWP** – 虚拟机工作进程。 虚拟化堆栈的一个用户模式组件。 工作进程提供了从父分区中的 Windows Server 实例的子分区中的来宾操作系统的虚拟机管理服务。 虚拟机管理服务生成每个正在运行的虚拟机的单独的工作的进程。  
  
- **VSC** – 虚拟化服务客户端。 合成设备实例驻留在子分区中。 Vsc 利用虚拟化服务提供商 (Vsp) 父分区中提供的硬件资源。 它们通过与通信在父分区中相应的 Vsp VMBus 满足子分区设备 I/O 请求。  
  
- **VSP** – 虚拟化服务提供程序。 驻留在根分区中，虚拟机总线 (VMBus) 通过提供综合设备支持添加到子分区。  
  
- **WinHv** – Windows 虚拟机监控程序接口库。 WinHv 是实质上是已分区的操作系统的驱动程序和虚拟机监控程序允许驱动程序，以调用使用标准 Windows 调用约定的虚拟机监控程序之间的桥梁  
  
- **WMI** – 虚拟机管理服务公开一组基于 Windows Management Instrumentation WMI 的 Api 提供用于管理和控制虚拟机。  
  
  其中大多数术语中定义[术语表](../technical-guides/glossary8.md)。  
  
> [!NOTE]  
>  [HYPER-V 技术概述](https://docs.microsoft.com/windows-server/virtualization/hyper-v/hyper-v-technology-overview)是一个好资源。 
  
## <a name="advantages"></a>优点
 在 HYPER-V 虚拟化环境中运行企业级解决方案的优点包括：  
  
1. **硬件资源的整合**-多个物理服务器可以轻松地整合到相对较少的服务器通过实现使用的 HYPER-V 虚拟化。 合并适合于已部署的硬件资源利用。 Windows Server 中的 HYPER-V 可以访问主计算机上的最多 64 个逻辑 Cpu。 此功能不仅能充分利用新的多核系统，这也意味着更高版本中每台物理主机的虚拟机的整合率。  
  
2. **易管理性**:  
  
   -   合并和集中管理的资源可简化管理。  
  
   -   实现纵向和横向扩展实现对多更容易。  
  
3. **节约成本的有效**:  
  
   -   因为一台物理计算机上运行多个虚拟机，可以显著减少了硬件成本，因此，不需要对每台计算机单独的物理计算机。  
  
   -   HYPER-V 的许可费用可能随 Windows Server 许可证成本，还可作为独立产品购买。
  
   -   通过将合并到由于减少了物理硬件"占用空间"的虚拟化的 HYPER-V 环境上的现有应用程序，可能会显著降低电源要求所需。  
  
4. **错误通过 HYPER-V 群集的容错支持**– 因为 HYPER-V 是群集感知应用程序、 Windows Server 提供了本机主机群集的 HYPER-V 虚拟化环境中创建的虚拟机的支持。  
  
5. **易于部署和管理**:  
  
   -   现有的服务器整合到更少的物理服务器简化了部署。  
  
   -   全面的 HYPER-V 管理解决方案，提供与 System Center Virtual Machine Manager。 [在 System Center VMM 的新增](https://docs.microsoft.com/system-center/vmm/whats-new?view=sc-vmm-2016)提供一些指导。
  
6. **密钥的 HYPER-V 的性能特征**:  
  
   -   **改进了的硬件共享体系结构**-Hyper V 提供改进的访问和核心资源，如磁盘、 网络、 利用率和视频时运行来宾操作系统的系统识别虚拟机监控程序的内核和其配备了必备项的虚拟服务器 （称为 HYPER-V 启用 I/O） 的客户端 (VSC) 代码。 启发方法是以帮助降低某些操作系统功能，例如内存管理的成本对操作系统所做的增强功能。 集成组件，其中包括 VSC 驱动程序，也已可供其他客户端操作系统。  
  
        磁盘性能至关重要的磁盘 I/O 密集型企业应用程序如 Microsoft BizTalk Server 和 HYPER-V 除了启用 I/O;HYPER-V 提供了"传递"的磁盘支持，从而可以提供与物理磁盘性能相媲美的磁盘性能。 请注意"传递"的磁盘支持，提供改进的性能，在较小的成本为方便起见。 "传递"磁盘是实质上是物理磁盘/Lun 附加到虚拟机且不支持的某些功能的虚拟磁盘，例如虚拟机快照。  
  
   -   **处理器硬件辅助虚拟化支持**– HYPER-V 利用完整的处理器提供最新处理器技术使用硬件辅助虚拟化支持。  
  
   -   **多核 (SMP) 来宾操作系统支持**– HYPER-V 提供了在虚拟机环境中，它允许应用程序以充分利用多线程处理功能在虚拟机支持最多四个处理器的能力计算机。  
  
   -   **32 位和 64 位来宾操作系统支持**– HYPER-V 的同时运行的不同类型的操作系统，在不同服务器平台，如 Windows，包括 32 位和 64 位系统提供广泛的支持Linux®，和其他人。  
  
7. **全面的产品支持**– 已部署并运行的 HYPER-V 中时，Microsoft 完全在 HYPER-V 中运行测试 （如 Exchange Server 和 SQL Server） 的 Microsoft 企业应用程序，因为提供这些应用程序的代码修补程序支持环境。  
  
8. **可伸缩性**– 额外处理能力、 网络带宽和存储容量，可以快速轻松地通过实现分派到来宾虚拟机从主计算机的其他可用资源。 这可能需要升级主计算机或来宾虚拟机在移动到功能更强大的主机计算机。  
  
   有关在利用虚拟化技术随 HYPER-V 一起提供的好处的深度信息的详细信息，请参阅[HYPER-V 技术概述](https://docs.microsoft.com/windows-server/virtualization/hyper-v/hyper-v-technology-overview)。 
  
## <a name="disadvantages"></a>缺点
 在 HYPER-V 虚拟化环境中运行企业级解决方案的缺点可能包括：  
  
-   **硬件要求-** 因服务器合并的需求，而 HYPER-V 虚拟机往往会占用更多 CPU 和内存，并且需要更大的磁盘 I/O 带宽比可比较的计算负载的物理服务器。 对于 64 位和所有版本的 Windows Server 仅 64 位的 HYPER-V 服务器角色才可用，因为物理硬件必须支持硬件辅助虚拟化。 这意味着必须是与 Intel VT 或 AMD 虚拟化 (AMD-V) 技术兼容的处理器、 系统 BIOS 必须支持数据执行保护 (DEP) 和必须启用 DEP。  
  
-   **软件的要求，即**时运行的 HYPER-V 虚拟机上支持大多数 Microsoft 软件，则仍要测试以确保与 HYPER-V 虚拟化环境的兼容性是某些 Microsoft 软件。 例如，大多数 Microsoft 企业级应用程序支持的 HYPER-V 上运行或正在被测试的 HYPER-V 上的支持。 有关 BizTalk Server 和 HYPER-V 上的 SQL Server 的可支持性详细信息，请参阅[附录 c: BizTalk Server 和 SQL Server 的 HYPER-V 可支持性](../technical-guides/appendix-c-biztalk-server-and-sql-server-hyper-v-supportability.md)。