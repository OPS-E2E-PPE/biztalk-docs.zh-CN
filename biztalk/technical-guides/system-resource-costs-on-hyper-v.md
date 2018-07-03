---
title: Hyper V 上的系统资源成本 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f25a76c-1c41-41c0-b28d-d7473dbe1cd1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6be288e21657d447dd21bff06b5c3294f6f4a2c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003702"
---
# <a name="system-resource-costs-on-hyper-v"></a>Hyper V 上的系统资源成本
## <a name="system-resource-costs-associated-with-running-a-guest-operating-system-on-hyper-v"></a>与 HYPER-V 上运行来宾操作系统相关联的系统资源成本  
 与任何服务器虚拟化软件一样，没有一定的开销与运行支持的 HYPER-V 上运行的来宾操作系统所需的虚拟化代码相关联。 以下列表汇总了当 HYPER-V 虚拟机上运行的来宾操作系统与特定资源相关的开销：  
  
### <a name="cpu-overhead"></a>CPU 开销  
 CPU 与 HYPER-V 虚拟机中运行来宾操作系统的系统开销关联找到 9 和 12%之间的范围。  例如，通常运行的 HYPER-V 虚拟机上的来宾操作系统必须在物理硬件上运行等效的操作系统可用的 CPU 资源的可用 88 91%。  
  
### <a name="memory-overhead"></a>内存开销  
 对于 HYPER-V 主机计算机，与 HYPER-V 虚拟机上运行来宾操作系统相关的内存开销观察到为大约 300 MB 的虚拟机监控程序，加上 32 MB 的第一个 GB 的 RAM 分配给每个虚拟机，再加上另一台 8 MB对于每个其他 GB 的 RAM 分配给每个虚拟机。 有关分配内存的 HYPER-V 虚拟机上运行的来宾操作系统的详细信息，请参阅中的"优化内存性能"一节[清单： 优化 HYPER-V 上的性能](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md)。  
  
### <a name="network-overhead"></a>网络开销  
 直接观察到的 HYPER-V 虚拟机中运行来宾操作系统是由引起了网络延迟为不超过 1 毫秒和来宾操作系统通常维护的网络输出队列长度小于 1。 有关测量网络输出队列长度的详细信息，请参阅中的"测量网络性能"一节[清单： 度量 HYPER-V 上的性能](../technical-guides/checklist-measuring-performance-on-hyper-v.md)。  
  
### <a name="disk-overhead"></a>磁盘开销  
 当在 HYPER-V 中使用的传递磁盘功能，磁盘 I/O 开销与在 HYPER-V 虚拟机中运行来宾操作系统找到介于 6 和 8%。 例如，通常运行的 HYPER-V 上的来宾操作系统必须可用 92 94%的磁盘 I/O 供等效操作系统由开放源磁盘性能基准测试工具 IOMeter 的物理硬件上运行。  
  
 有关测量磁盘延迟的 HYPER-V 主机或来宾操作系统上使用性能监视器的信息，请参阅中的"衡量磁盘 I/O 性能"一节[清单： 度量 HYPER-V 上的性能](../technical-guides/checklist-measuring-performance-on-hyper-v.md)。  
  
 本部分的其余部分在 BizTalk Server 上的磁盘性能提供了背景信息，描述测试配置参数使用，并提供获得的测试结果的摘要。  
  
#### <a name="disk-performance-when-running-a-biztalk-server-solution-on-hyper-v"></a>HYPER-V 上运行 BizTalk Server 解决方案时的磁盘性能  
 BizTalk Server 是极其数据库密集型应用程序可能需要创建的 SQL Server 中的最多 13 个数据库。 BizTalk Server 将数据保存到磁盘很好的频率和此外，MSDTC 事务的上下文中执行此操作。 因此，数据库性能至关重要的任何 BizTalk Server 解决方案的整体性能。 HYPER-V 提供了综合的 SCSI 控制器和 Virtual Server 2005 提供的 IDE 筛选器驱动程序的这两个通过使用仿真的 IDE 设备，如提供显著的性能优势。  
  
 配置为使用 SCSI 控制器的数据卷的磁盘。 这将保证安装集成服务，因为如果安装 HYPER-V 集成服务，而无需安装 HYPER-V 集成服务中，模拟的 IDE 控制器可用，可以仅安装 SCSI 控制器。 使用 SCSI 控制器或使用 integration services 提供的 IDE 筛选器驱动程序执行的磁盘 I/O 是明显优于磁盘 I/O 性能提供与仿真的 IDE 控制器。 因此，若要确保获得最佳磁盘 I/O 性能的 HYPER-V 虚拟化环境中的数据文件，主机和来宾操作系统上安装集成服务并将数据卷的磁盘合成 SCSI 控制器的配置。 对于跨多个数据驱动器的高密集型存储 I/O 工作负荷，每个 VHD 应附加到单独的合成 SCSI 控制器以提高整体性能。 此外，每个 VHD 应存储在单独的物理磁盘或 Lun 上。  
  
#### <a name="measuring-passthrough-disk-performance"></a>度量传递磁盘性能  
 在任何合并练习务必使最充分地利用可用资源。 如前文所述，SQL 数据卷上的存储 I/O 在 BizTalk Server 解决方案的整体性能中扮演的重要部分。 因此，本指南中的 HYPER-V 中的传递磁盘性能的物理磁盘的相对性能进行了测试。 MessageBox 数据的相对性能中 Physical_SQL01 的驱动器和 Virtual_SQL01 测量使用的 IOMeter 开放源代码工具最初由 Intel Corporation 和现在维护的开放源开发实验室 (OSDL)。 IOMeter 有关详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=122412 ](http://go.microsoft.com/fwlink/?LinkId=122412)。  
  
 下表描述了在测试环境、 使用 IOMeter 配置选项、 已运行的测试的说明和结果的摘要中使用的物理和虚拟硬件配置。  
  
#### <a name="configuration-used-for-testing"></a>用于测试的配置  
  
### <a name="physicalsql01"></a>Physical_SQL01  
  
|||  
|-|-|  
|**Model**|HP DL580|  
|**处理器**|四核处理器，四核 Intel Xeon 2.4 Ghz|  
|**内存**|8 GB|  
|**网络**|HP NC3T3i 多功能千兆位 Server 适配器|  
|**SAN 配置**|直连的 SAN 存储 （请参阅下表）|  
  
### <a name="physicalsql01--san-configuration"></a>Physical_SQL01 – SAN 配置  
  
|驱动器号|Description|LUN 的大小|RAID 配置|  
|------------------|-----------------|--------------|------------------------|  
|G:|Data_Sys|10|RAID 0 + 1|  
|H:|Logs_Sys|10|RAID 0 + 1|  
|实现：|Data_TempDb|50|RAID 0 + 1|  
|J:|Logs_TempDb|50|RAID 0 + 1|  
|K:|Data_BtsMsgBox|300|RAID 0 + 1|  
|L:|Logs_BtsMsgBox|100|RAID 0 + 1|  
|M:|MSDTC|5|RAID 0 + 1|  
  
### <a name="hyper-vhostsql01"></a>Hyper-V_Host_SQL01  
  
|||  
|-|-|  
|**Model**|HP DL580|  
|**处理器**|四核处理器，四核 Intel Xeon 2.4 Ghz|  
|**内存**|32 GB|  
|**网络**|Broadcom BCM5708C NetXtreme II GigEHP DL380 G5|  
  
### <a name="virtualsql01---virtual-machine-configuration"></a>Virtual_SQL01-虚拟机配置  
  
|||  
|-|-|  
|**虚拟处理器**|分配 4|  
|**内存**|8 GB|  
|**网络**|虚拟机的网络连接到：<br />Broadcom BCM5708C NetXtreme II GigE|  
|**硬盘配置**|**IDE 控制器**– 30 GB 的操作系统为固定 vhd<br />**SCSI 控制器**-7 直接连接 （请参阅下表） 的传递 SAN Lun|  
  
### <a name="virtualsql01--san-configuration"></a>Virtual_SQL01 – SAN 配置  
  
|驱动器号|Description|LUN 的大小|RAID 配置|  
|------------------|-----------------|--------------|------------------------|  
|G:|Data_Sys|10|RAID 0 + 1|  
|H:|Logs_Sys|10|RAID 0 + 1|  
|实现：|Data_TempDb|50|RAID 0 + 1|  
|J:|Logs_TempDb|50|RAID 0 + 1|  
|K:|Data_BtsMsgBox|300|RAID 0 + 1|  
|L:|Logs_BtsMsgBox|100|RAID 0 + 1|  
|M:|MSDTC|5|RAID 0 + 1|  
  
#### <a name="iometer-configuration"></a>IOMeter 配置  
 IOMeter 工具可以用作基准和故障排除工具通过复制应用程序的读/写性能。 IOMeter 是性能的一个可配置的工具，可用于模拟许多不同类型。 对于此测试方案，IOMeter 配置参数已设置为在下表描述这两个物理[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]进行了测试的计算机和运行来宾操作系统上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]中的 HYPER-V 虚拟机:  
  
### <a name="iometer--passthrough-disk-comparison-test-configuration"></a>IOMeter – 传递磁盘比较测试配置  
  
|                             |                     |
|-----------------------------|---------------------|
|       **测试长度**       |     10 分钟。      |
|      **技能强化时间**       |     30 秒      |
|    **工作线程数**    |          4          |
|  **传输请求大小**  |        2 KB         |
| **读/写分发** | 66%的读取，33%写入 |
|      **突发长度**       |       1 I/o        |
|      **目标驱动器**       |         K:\         |
  
#### <a name="test-description"></a>测试说明  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]服务已停止两个服务器以确保 IOMeter 是对磁盘执行 I/O 的唯一进程上。 使用 LUN 的此测试中都位于同一个 SAN 这专用于此实验室环境上。 针对 SAN 上测试以确保结果不倾斜期间不执行任何其他 I/O 活动。 然后通过从每个本地执行 IOMeter 工具运行测试时[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]和收集以下性能监视器计数器：  
  
 **收集从 Virtual_SQL01 和 Physical_SQL01**:  
  
- \LogicalDisk(*)\\\*  
  
- \PhysicalDisk(*)\\\*  
  
  **收集从虚拟机超 V_02**:  
  
- \Hyper-V 虚拟存储设备\\*  
  
### <a name="results"></a>结果  
 传递磁盘是吞吐量的可以重复使用超过 90%的直接连接到 Physical_SQL01 SAN LUN。  总、 读取和写入相同的每秒传输的总 MB 每秒 I/o 是所有都在 10%。  对于正常磁盘响应时间应介于 1-15 毫秒的读取和写入。 平均 I/O 响应时间是小于 4 毫秒，这两个磁盘上。 随机读取响应时间为 5.4 毫秒在物理上和 5.7 ms 传递磁盘上。 写入响应时间为小于 0.5 毫秒的物理和虚拟环境。  
  
 结果表明使用已启用的 SCSI 控制器的传递磁盘，可以提供超过 90%的直接连接的物理磁盘的性能。 I/O 子系统的性能至关重要的有效的 BizTalk Server 操作，通过提供出色的吞吐量和响应时间的 HYPER-V 适用的最佳候选项合并 BizTalk Server 环境。 下表提供了比较的传递磁盘的物理磁盘性能时，观察到的磁盘测试结果摘要：  
  
|度量值|Physical_SQL01 （物理磁盘）|Virtual_SQL01 （直通）|为物理磁盘的传递磁盘的相对性能|  
|-----------------|---------------------------------------|------------------------------------|-----------------------------------------------------------------|  
|每秒的总 i/o 数|269.73|250.47|92.86%|  
|每秒读取 i/o 数|180.73|167.60|92.74%|  
|每秒写入 I/o|89.00|82.87|93.11%|  
|总 Mb / 秒|0.53|0.49|92.45%|  
|平均读取响应时间 （毫秒）|5.4066|5.7797|93.54%|  
|平均写入响应时间 （毫秒）|0.2544|0.3716|68.42%**注意：** 虽然的传递磁盘平均写入响应时间的相对性能 68.42%的物理磁盘的性能，但仍也在已传递磁盘的平均写入响应时间建立可接受的限制为 10 毫秒。|  
|平均 I/O 响应时间 （毫秒）|3.7066|3.9904|93.89%|  
  
> [!NOTE]  
>  通过将传递磁盘的相应物理磁盘值的值来计算每秒的总 i/o 数、 每秒读取 i/o 数、 每秒写入 I/o 和总 Mb / 秒的百分比值。  
>   
>  平均值的百分比值读取响应时间 （毫秒），平均写入响应时间 （毫秒），并通过将物理磁盘对值进行相应的传递磁盘值来计算平均 I/O 响应时间 （毫秒）。