---
title: "HYPER-V 上的系统资源成本 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f25a76c-1c41-41c0-b28d-d7473dbe1cd1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 491c71a446829ddddfc4d7c55053b94dcf7fc9d1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="system-resource-costs-on-hyper-v"></a>HYPER-V 上的系统资源成本
## <a name="system-resource-costs-associated-with-running-a-guest-operating-system-on-hyper-v"></a>与 HYPER-V 上运行来宾操作系统的系统资源成本  
 与任何服务器虚拟化软件一样，没有一定量的与运行在 HYPER-V 上运行的来宾操作系统的支持所需的虚拟化代码关联的开销。 以下列表总结了 HYPER-V 虚拟机上运行来宾操作系统时，与特定资源关联的开销：  
  
### <a name="cpu-overhead"></a>CPU 开销  
 CPU 与 HYPER-V 虚拟机中运行来宾操作系统的系统开销关联找到 9 和 12%之间的范围。  例如，来宾操作系统运行的 HYPER-V 虚拟机上通常具有可用于在物理硬件上运行等效的操作系统的 CPU 资源的可用 88 91%。  
  
### <a name="memory-overhead"></a>内存开销  
 对于 HYPER-V 主机计算机，与 HYPER-V 虚拟机上运行来宾操作系统相关的内存开销观察到要用于虚拟机监控程序，大约 300 MB 加上 32 MB; 在第一个 GB 的 RAM 分配给每个虚拟机，以及另一个 8 MB为每个其他 GB 的 RAM 分配给每个虚拟机。 有关分配到 HYPER-V 虚拟机上运行的来宾操作系统的内存的详细信息，请参阅中的"优化内存性能"部分[清单： HYPER-V 上优化性能](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md)。  
  
### <a name="network-overhead"></a>网络开销  
 直接在 HYPER-V 虚拟机中运行来宾操作系统是由引起观察到的网络延迟是小于 1 ms 和来宾操作系统通常维护的网络输出队列长度小于 1。 有关测量网络输出队列长度的详细信息，请参阅中的"测量网络性能"部分[清单： HYPER-V 上的测量性能](../technical-guides/checklist-measuring-performance-on-hyper-v.md)。  
  
### <a name="disk-overhead"></a>磁盘开销  
 当在 HYPER-V 中使用的传递磁盘功能，到 6 和 8%之间的范围未找到磁盘与 HYPER-V 虚拟机中运行来宾操作系统相关的 I/O 开销。 例如，通常在 HYPER-V 上运行来宾操作系统具有磁盘 I/O 供等效操作系统在由基准测试工具 IOMeter 的开放源磁盘性能的物理硬件上运行的可用 92 94%。  
  
 有关测量磁盘延迟 HYPER-V 主机或来宾操作系统上使用性能监视器的信息，请参阅中的"磁盘 I/O 性能测量"一节[清单： HYPER-V 上的测量性能](../technical-guides/checklist-measuring-performance-on-hyper-v.md)。  
  
 本部分的其余部分提供有关 BizTalk Server 磁盘性能的背景信息、 介绍的测试配置参数使用，并提供获得的测试结果的摘要。  
  
#### <a name="disk-performance-when-running-a-biztalk-server-solution-on-hyper-v"></a>在 HYPER-V 上运行 BizTalk Server 解决方案时的磁盘性能  
 BizTalk Server 是极数据库密集型应用程序可能需要最多 13 SQL Server 数据库的创建。 BizTalk Server 仍然数据存储到磁盘存在很好的频率和此外，MSDTC 事务的上下文中执行此。 因此，数据库性能至关重要的 BizTalk Server 中的任何解决方案的总体性能。 HYPER-V 提供了合成 SCSI 控制器，这两者都提供显著的性能改进了对使用模拟的 IDE 设备如 IDE 筛选器驱动程序提供使用 Virtual Server 2005。  
  
 配置为使用 SCSI 控制器的数据卷的磁盘。 这可以保证因为而模拟的 IDE 控制器可用的而无需安装 HYPER-V 集成服务已安装 HYPER-V 集成服务情况下，才会安装 SCSI 控制器，安装了集成服务。 使用 SCSI 控制器或使用 integration services 提供的 IDE 筛选器驱动程序执行的磁盘 I/O 是明显优于磁盘输入/输出性能提供与模拟的 IDE 控制器。 因此，若要确保最佳磁盘的 HYPER-V 虚拟化环境中的数据文件的 I/O 性能，在主机和来宾操作系统上安装集成服务，并且使用合成 SCSI 控制器配置数据卷的磁盘。 对于跨多个数据驱动器的高密集型存储 I/O 工作负荷，应将每个 VHD 附加到更好的总体性能的单独合成 SCSI 控制器。 此外，每个 VHD 应存储在单独的物理磁盘或 Lun 上。  
  
#### <a name="measuring-passthrough-disk-performance"></a>测量的传递磁盘性能  
 在任何合并练习很重要，若要最大利用可用资源。 如前文所述，SQL 数据卷上的存储 I/O 在 BizTalk Server 解决方案的总体性能中扮演的重要部分。 因此作为本指南的一部分进行了测试对性能的 HYPER-V 中的传递磁盘的物理磁盘的相对性能。 MessageBox 数据的相对性能中 Physical_SQL01 的驱动器和 Virtual_SQL01 测量使用开放源代码工具最初由 Intel Corporation 开发和现在维护 IOMeter 通过开放源开发实验室 (OSDL)。 有关 IOMeter 的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=122412](http://go.microsoft.com/fwlink/?LinkId=122412)。  
  
 下表描述了在测试环境、 已使用的 IOMeter 配置选项、 已运行的测试的说明和结果的摘要中使用的物理和虚拟硬件配置。  
  
#### <a name="configuration-used-for-testing"></a>用于测试的配置  
  
### <a name="physicalsql01"></a>Physical_SQL01  
  
|||  
|-|-|  
|**Model**|HP DL580|  
|**处理器**|四核处理器，双核 Intel Xeon 2.4 Ghz|  
|**内存**|8 GB|  
|**网络**|HP NC3T3i 多功能千兆 Server 适配器|  
|**SAN 配置**|直连的 SAN 存储 （请参见下表）|  
  
### <a name="physicalsql01--san-configuration"></a>Physical_SQL01 – SAN 配置  
  
|驱动器号|Description|LUN 的大小|RAID 配置|  
|------------------|-----------------|--------------|------------------------|  
|G:|Data_Sys|10|RAID 0 + 1|  
|H:|Logs_Sys|10|RAID 0 + 1|  
|I:|Data_TempDb|50|RAID 0 + 1|  
|J:|Logs_TempDb|50|RAID 0 + 1|  
|K:|Data_BtsMsgBox|300|RAID 0 + 1|  
|L:|Logs_BtsMsgBox|100|RAID 0 + 1|  
|M:|MSDTC|5|RAID 0 + 1|  
  
### <a name="hyper-vhostsql01"></a>Hyper V_Host_SQL01  
  
|||  
|-|-|  
|**Model**|HP DL580|  
|**处理器**|四核处理器，双核 Intel Xeon 2.4 Ghz|  
|**内存**|32 GB|  
|**网络**|Broadcom BCM5708C NetXtreme II GigEHP DL380 G5|  
  
### <a name="virtualsql01---virtual-machine-configuration"></a>Virtual_SQL01-虚拟机配置  
  
|||  
|-|-|  
|**虚拟处理器**|分配的 4|  
|**内存**|8 GB|  
|**网络**|虚拟机网络连接到：<br />Broadcom BCM5708C NetXtreme II GigE|  
|**硬盘配置**|**IDE 控制器**– 30 GB 的操作系统为固定 vhd<br />**SCSI 控制器**-7 直接连接 （请参见下表） 的传递 SAN Lun|  
  
### <a name="virtualsql01--san-configuration"></a>Virtual_SQL01 – SAN 配置  
  
|驱动器号|Description|LUN 的大小|RAID 配置|  
|------------------|-----------------|--------------|------------------------|  
|G:|Data_Sys|10|RAID 0 + 1|  
|H:|Logs_Sys|10|RAID 0 + 1|  
|I:|Data_TempDb|50|RAID 0 + 1|  
|J:|Logs_TempDb|50|RAID 0 + 1|  
|K:|Data_BtsMsgBox|300|RAID 0 + 1|  
|L:|Logs_BtsMsgBox|100|RAID 0 + 1|  
|M:|MSDTC|5|RAID 0 + 1|  
  
#### <a name="iometer-configuration"></a>IOMeter 配置  
 IOMeter 工具可以用作基准和故障排除工具通过复制应用程序的读/写性能。 IOMeter 是性能的一个可配置的工具，可用于模拟许多不同类型。 对于此测试方案，IOMeter 配置参数被设置为在下表描述这两个物理[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]已测试的计算机和运行来宾操作系统上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]在 HYPER-V 虚拟机:  
  
### <a name="iometer--passthrough-disk-comparison-test-configuration"></a>IOMeter – 传递磁盘比较测试配置  
  
|||  
|-|-|  
|**测试长度**|10 分钟。|  
|**加速时间**|30 秒|  
|**辅助进程数**|4|  
|**传输请求大小**|2 KB|  
|**读/写分发**|66%读取，33%写入|  
|**迸发长度**|1 I/o|  
|**目标驱动器**|K:\|  
  
#### <a name="test-description"></a>测试说明  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]服务已停止两个服务器以确保 IOMeter 是仅对磁盘执行 I/O 的进程上。 LUN 的使用在此测试中都位于相同的专用于此实验室环境的 SAN 上。 针对 SAN 上以确保结果的不倾斜在测试期间不执行任何其他 I/O 活动。 通过从每个本地执行 IOMeter 工具然后运行测试[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]和收集以下性能监视器计数器：  
  
 **收集从 Virtual_SQL01 和 Physical_SQL01**:  
  
-   \LogicalDisk(*)\\\*  
  
-   \PhysicalDisk(*)\\\*  
  
 **收集从虚拟机超 V_02**:  
  
-   \Hyper-V 虚拟存储设备\\*  
  
### <a name="results"></a>结果  
 传递磁盘时能够获得超过 90%的直接连接到 Physical_SQL01 的 SAN LUN 的吞吐量。  总，读取和写入相同的每秒传输的总 MB，每秒 I/o 已都处于 10%。  正常的磁盘的响应时间应介于 1-15 毫秒的时间让读取和写入。 平均 I/O 响应时间是小于 4 毫秒，这两个磁盘上。 随机读取响应时间为 5.4 ms 在物理上和传递磁盘上的 5.7 ms。 写入响应时间是小于 0.5 毫秒上物理和虚拟环境。  
  
 结果指示使用启用的 SCSI 控制器的传递磁盘，可以提供超过 90%的直接连接的物理磁盘的性能。 I/O 子系统性能至关重要高效 BizTalk Server 操作，通过提供极好的吞吐量和响应时间 HYPER-V 适用的最佳候选项整合 BizTalk Server 环境。 下表提供了到物理磁盘的传递磁盘的性能进行比较时，观察到的磁盘测试结果摘要：  
  
|度量|Physical_SQL01 （物理磁盘）|Virtual_SQL01 （传递）|传递磁盘的物理磁盘的相对性能|  
|-----------------|---------------------------------------|------------------------------------|-----------------------------------------------------------------|  
|每秒的总 I/o|269.73|250.47|92.86%|  
|每秒读取 I/o|180.73|167.60|92.74%|  
|每秒写入 I/o|89.00|82.87|93.11%|  
|总 Mb / 秒|0.53|0.49|92.45%|  
|平均读取响应时间 （毫秒）|5.4066|5.7797|93.54%|  
|平均写入响应时间 （毫秒）|0.2544|0.3716|68.42%**注意：**虽然的传递磁盘平均写入响应时间的相对性能已 68.42%的物理磁盘的性能，传递磁盘的平均写入响应时间为仍很好地内建立可接受的限制的 10 毫秒。|  
|平均 I/O 响应时间 （毫秒）|3.7066|3.9904|93.89%|  
  
> [!NOTE]  
>  每秒的总 I/o、 每秒读取 I/o、 写入每秒的 i/o 数和总 Mb / 秒的百分比值除以传递磁盘值的相应的物理磁盘值计算。  
>   
>  平均值的百分比值读取响应时间 （毫秒），平均写入响应时间 （毫秒），并除以物理磁盘的相应的传递磁盘值的值计算平均 I/O 响应时间 （毫秒）。