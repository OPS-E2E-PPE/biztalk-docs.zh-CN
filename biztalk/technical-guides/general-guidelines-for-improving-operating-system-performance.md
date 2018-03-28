---
title: 一般性的指导原则，用于提高操作系统性能 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc9ca38e-1feb-4f34-a64b-d04566e85db9
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7be3f8060bba20bc0ba127443095c228f954bba
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="general-guidelines-for-improving-operating-system-performance"></a>一般性的指导原则，用于提高操作系统性能
应遵循以下常规准则，以提高操作系统性能：  
  
## <a name="install-the-latest-bios-storage-area-network-san-drivers-network-adapter-firmware-and-network-adapter-drivers"></a>安装最新的 BIOS、 存储区域网络 (SAN) 驱动程序、 网络适配器的固件和网络适配器驱动程序  
 硬件制造商定期发布可以提高性能和可用性相关联的硬件的 BIOS、 固件和驱动程序更新。 请访问硬件制造商的网站上下载并应用在 BizTalk Server 环境中的每台计算机上的以下硬件组件的更新：  
  
1.  BIOS 更新  
  
2.  SAN 驱动程序 （如果使用 SAN）  
  
3.  NIC 固件  
  
4.  网卡驱动程序  
  
## <a name="enable-the-high-performance-power-plan-on-all-biztalk-server-and-sql-server-computers"></a>启用"高性能"BizTalk Server 和 SQL Server 的所有计算机上的电源计划。  
 默认情况下，Windows Server 2008/2008 R2 设置 （推荐） 平衡电源计划，从而使能量节省，但可能会导致延迟时间增加 （对于某些任务减慢响应时间） 并导致 CPU 密集型应用程序性能问题。  
  
 若要减少延迟，你必须确保运行 BizTalk Server 的所有服务器和 SQL Server 具有 Windows**电源计划**设置为**高性能**。 有关如何切换到**高性能**电源计划，请参阅知识库文章： 2207548 [Windows Server 2008 R2 上的总体性能下降](http://go.microsoft.com/fwlink/?LinkID=219677)(http://go.microsoft.com/fwlink/?LinkID=219677)。  
  
## <a name="evaluate-the-usage-of-intel-hyper-threading-on-biztalk-server-and-sql-server-computers"></a>评估 Intel 超线程 BizTalk Server 和 SQL Server 的计算机上的使用率  
  
-   **Pre Nehalem 超线程**:  
  
    -   超线程应关闭在 BizTalk Server 计算机。 这是通常在 BIOS 设置的处理器设置中找到的 BIOS 设置。 超线程使服务器会显示为具有更多处理器/处理器内核不是它的实际作用;但是，超线程处理器通常提供性能的物理处理器核心 20-30%之间。 当 BizTalk Server 计算调整其自我调整算法的处理器数目时，超线程处理器将导致这些调整倾斜，这可能会导致负的整体性能。  
  
    -   超线程应打开在 SQL Server 计算机，因为应用程序可能会导致大量争用 （例如 BizTalk Server) 可能导致性能降低，在 SQL Server 计算机上的超线程环境中使用。  
  
-   **Nehalem 超线程**： 与不同在较旧的体系结构中启用超线程在 Intel 微体系结构"Nehalem"处理器可以提供最多几乎线性容量增加。 为获得最佳性能结果，部署"Nehalem"处理器时我们建议你启用标记增加，吞吐量 Intel 超线程 (H-T) 技术来配置计算机的 BIOS。  
  
-   **硬件虚拟化**： 在使用硬件虚拟化时，虚拟机使用虚拟处理器。 可用的 Cpu 数取决于时配置虚拟机选择的设置。 如果硬件是超线程，虚拟机无法知道它是超线程。  
  
## <a name="assign-the-msdtc-log-file-directory-to-a-separate-dedicated-drive"></a>将 MSDTC 日志文件目录分配给单独的专用驱动器  
 在 BizTalk Server 环境中的 SQL Server 的单独计算机上的多个 MessageBox 数据库，产生关联与 Microsoft 分布式事务处理协调器 (MSDTC) 的其他开销。 默认情况下，MSDTC 日志文件位于运行 DTC 服务的计算机的 %systemdrive%\windows\system32\msdtc 目录中。 若要缓解 DTC 日志记录可能成为性能瓶颈的可能性，请考虑将 MSDTC 日志文件目录移到快速的磁盘驱动器。  
  
 若要更改 MSDTC 日志文件目录，请参阅[配置 DTC 日志记录](http://go.microsoft.com/fwlink/?LinkID=204107)(http://go.microsoft.com/fwlink/?LinkID=204107)。  
  
## <a name="configure-antivirus-software-to-avoid-real-time-scanning-of-biztalk-server-executables-and-file-drops"></a>配置防病毒软件，以避免的 BizTalk Server 可执行文件的实时扫描和丢失的文件  
 防病毒软件实时扫描的 BizTalk Server 可执行文件和任何文件夹或文件共享由 BizTalk Server 监视接收位置对 BizTalk 服务器性能产生负面影响。 如果在 BizTalk Server 计算机上安装防病毒软件，禁用实时扫描的非可执行文件类型引用的任何 BizTalk Server 接收位置 （通常。XML，但也可以是.csv、.txt，等等。)并配置防病毒软件扫描的 BizTalk Server 可执行文件中排除  
  
## <a name="disable-intrusion-detection-network-scanning-between-computers-in-the-biztalk-server-environment"></a>禁用扫描在 BizTalk Server 环境中的计算机之间的入侵检测网络  
 入侵检测软件可以慢，或者甚至阻止通过网络的有效的通信。 如果安装入侵检测软件后，禁用扫描 BizTalk Server 计算机和外部数据存储库 (SQL Server) 的计算机之间或消息传送服务 （如消息队列和 WebSphere MQSeries） 计算机的网络。  
  
## <a name="defragment-all-disks-in-the-biztalk-server-environment-on-a-regular-basis"></a>对在定期 BizTalk Server 环境中的所有磁盘碎片都整理  
 在 BizTalk Server 环境中的过多的磁盘碎片将对性能造成负面影响。 请按照下列步骤进行碎片整理在 BizTalk Server 环境中的磁盘：  
  
1.  对所有磁盘碎片都整理 (本地和 SAN/NAS) 定期通过计划非高峰时段磁盘碎片整理。  
  
2.  碎片整理 Windows 页面文件和预分配在 BizTalk Server 环境中的每个磁盘的主机文件表，以提升总体系统性能。  
  
    > [!NOTE]  
    >  若要预分配主文件表，请参阅知识库文章 961095， ["有关主文件表区域保留在 Windows Vista 和 Windows Server 2008"](http://go.microsoft.com/fwlink/?LinkID=204563) (http://go.microsoft.com/fwlink/?LinkID=204563)。  
  
## <a name="if-antivirus-software-is-installed-on-the-sql-server-computer-disable-real-time-scanning-of-data-and-transaction-files"></a>如果在 SQL Server 计算机上安装防病毒软件，禁用实时的数据和事务文件扫描  
 SQL Server 数据和事务文件 （.mdf、.ndf、.ldf、.mdb） 的实时扫描可以提高磁盘 I/O 争用，并降低 SQL 服务器的性能。 请注意，BizTalk Server 环境之间的 SQL Server 数据和事务文件的名称可能会有所不同。 有关创建与默认 BizTalk 服务器配置的数据和事务文件的详细信息，请参阅[Databases2 优化文件组](../technical-guides/optimizing-filegroups-for-the-databases2.md)。  
  
## <a name="configure-msdtc-for-biztalk-server-and-sql-server"></a>BizTalk Server 和 SQL Server 配置 MSDTC  
 若要简化 SQL Server 和 BizTalk Server 之间的事务，必须启用 Microsoft 分布式事务处理协调器 (MSDTC)。  
  
#### <a name="to-configure-distributed-transaction-coordinator-dtc"></a>若要配置分布式事务处理协调器 (DTC)  
  
1.  单击**启动**，单击**运行**，类型**dcomcnfg**，然后单击**确定**以打开**组件服务**.  
  
2.  在控制台树中，依次展开“组件服务”、“计算机”、“我的计算机”、“分布式事务处理协调器”，然后单击“本地 DTC”。  
  
3.  右键单击**本地 DTC**，然后单击**属性**以显示**本地 DTC 属性**对话框。  
  
4.  上**跟踪**选项卡上，在**输出选项**部分中，清除**跟踪输出**框。  
  
5.  单击 **“安全性”** 选项卡。  
  
6.  确保以下四个选项均处于选中状态，且清除所有其他选项：  
  
    -   **网络 DTC 访问**  
  
    -   **允许入站**  
  
    -   **允许出站**  
  
    -   **不要求进行验证**  
  
7.  单击**确定**关闭**本地 DTC 属性**对话框。 如果系统提示您重新启动 MSDTC 服务，请单击**是**。  
  
8.  关闭“组件服务”。  
  
9. 单击**启动**，指向**管理工具**，然后单击**高级安全 Windows 防火墙**。  
  
10. 在高级安全 Windows 防火墙中，单击**入站规则**。  
  
11. 在**入站规则**窗格中，右键单击**分布式事务处理协调器*** （根据需要），然后单击**启用规则**。  
  
12. 在高级安全 Windows 防火墙中，单击**出站规则**。  
  
13. 在**出站规则**窗格中，右键单击**分布式事务处理协调器*** （根据需要），然后单击**启用规则**。  
  
14. 上**控制面板**，双击**管理工具**。  
  
15. 在右侧窗格中，双击**服务**。  
  
16. 在右侧窗格中的**服务 （本地）**，右键单击**COM + 应用程序系统**，单击**重新启动**，并等待服务重新启动。  
  
17. 右键单击并重启“分布式事务处理协调器”服务。  
  
18. 右键单击并重启“SQL Server (MSSQLSERVER)”服务。  
  
19. 关闭“服务(本地)”，然后关闭“管理工具”。  
  
## <a name="configure-firewalls-for-biztalk-server"></a>为 BizTalk Server 中配置防火墙  
  
> [!NOTE]  
>  此步骤才是必需的一个或多个防火墙如果都在你的 BizTalk 服务器环境中的位置。  
  
 查看以下信息来为 BizTalk Server 中配置防火墙：  
  
-   [BizTalk Server 所需端口](http://go.microsoft.com/fwlink/?LinkID=153238)(http://go.microsoft.com/fwlink/?LinkID=153238)。  
  
-   若要配置与防火墙一起使用的 RPC 动态端口分配，请参阅知识库文章 929851， ["在 Windows Vista 和 Windows Server 2008 中，已更改了 TCP/IP 的默认动态端口范围"](http://go.microsoft.com/fwlink/?LinkID=204568) (超链接"http://go.microsoft.com/fwlink/?LinkID=204568"http://go.microsoft.com/fwlink/?LinkID=204568). 有关如何配置 Windows 防火墙，以容纳所需的端口的信息，请参阅[Windows 防火墙和 IPsec 策略部署分步指南](http://go.microsoft.com/fwlink/?LinkID=204569)(http://go.microsoft.com/fwlink/?LinkID=204569)。  
  
## <a name="install-appropriate-com-and-msdtc-hotfix-rollup-packages"></a>安装相应的 COM + 和 MSDTC 修补程序汇总包  
 查看以下信息来安装相应的 COM + 和 MS DTC 修补程序汇总包：  
  
-   MS DTC 修补程序可在 Microsoft 知识库文章 article978476 ["在 Windows Server 2008 R2 MS DTC 修补程序汇总包 1 中修复了 MS DTC 问题"](http://go.microsoft.com/fwlink/?LinkID=204109) (http://go.microsoft.com/fwlink/?LinkID=204109)。  
  
-   可以通过搜索找到最新的 DTC 修补程序汇总包 KB 文章[ http://support.microsoft.com ](http://go.microsoft.com/fwlink/?LinkID=96185) (http://go.microsoft.com/fwlink/?LinkID=96185)短语 （包括引号）：  
  
    ```  
    "MS DTC Hotfix Rollup Package"  
    ```  
  
     下面的查询执行此搜索。 选择的最新项目：   
    [http://support.microsoft.com/search/default.aspx?query="MS+DTC+Hotfix+Rollup+Package"](http://support.microsoft.com/search/default.aspx?query="MS+DTC+Hotfix+Rollup+Package")  
  
## <a name="use-the-interrupt-affinity-policy-tool-to-bind-network-adapter-interrupts-to-specific-processors-on-multiprocessor-computers"></a>使用中断地缘策略工具将网络适配器中断绑定到多处理器计算机上的特定处理器  
 中断地缘策略 (IntPolicy) 是一个工具，可将"绑定"或更改的中断对给定的设备 （如网络适配器） 的 CPU 相关性具有特定处理器或多处理器计算机上的处理器。 此绑定也称为分区。 来自特定网络适配器与多处理器计算机上的特定处理器的中断的绑定强制实施运行延缓的过程调用 (Dpc) 和指定的处理器上的网络适配器的中断服务例程 (Isr)。 请注意，不能在单个处理器的计算机上配置中断相关性。  
  
> [!NOTE]  
>  DPC 被指排队通常将在以后执行的内核模式函数调用。 ISR 被指其目的是生成中断时服务设备的例程。 有关延缓的过程调用和中断服务例程的详细信息，请参阅[Windows 驱动程序工具包文档](http://go.microsoft.com/fwlink/?LinkId=84418)(http://go.microsoft.com/fwlink/?LinkId=84418)。  
  
 ![中断&#45;地缘策略工具](../technical-guides/media/interrupt-affinitypolicytool.gif "中断 AffinityPolicyTool")  
中断-关联策略工具  
  
 基于 Windows Server 2008 多处理器计算机上中断控制器的默认行为是将设备中断分配给任何可用的处理器。 当网络连接和文件服务器会话的给定的网络适配器是绑定/分区以在一组特定的处理器上运行而不是任何可用的处理器、 性能以及关联的网络处理的可伸缩性得到了改进。 BizTalk Server 中的大型解决方案通常采用使用多处理器 SQL Server 计算机具有多个网络适配器中断绑定可能特别有益的。   
中断绑定使用 IntPolicy 应始终评估在测试环境然后再在生产环境中使用。 硬件、 操作系统和应用程序配置的测试环境应尽可能接近生产环境。 这将允许你以测试各种屏蔽的中断绑定，并确定程度该中断绑定将提高性能。  
 我们建议你禁用超线程支持超线程使用 Cpu 的计算机上配置 IntPolicy 之前。 这将确保中断分配给物理处理器，而不是逻辑处理器。 分配到引用相同的物理处理器的逻辑处理器的中断地缘将不会提高性能，并甚至可能会降低系统性能。    超链接"The"[中断地缘策略工具](http://go.microsoft.com/fwlink/?LinkID=204111)(http://go.microsoft.com/fwlink/?LinkID=204111)从 WHDC 网站下载。  
  
## <a name="use-the-ntfs-file-system-on-all-volumes"></a>使用上的所有卷的 NTFS 文件系统  
 Windows Server 来格式化驱动器，包括 NTFS、 FAT 和 FAT32 提供多个文件系统类型。 NTFS 应始终为文件系统的服务器的选择。  
NTFS 针对 FAT 和 FAT32 文件系统中有很大的性能优点，并应在 Windows 服务器上以独占方式使用。 此外，NTFS 通过 FAT 和 FAT32 提供许多安全性、 可伸缩性、 稳定性和可恢复性的好处。  
在以前版本的 Windows，FAT 和 FAT32 上通常实现较小的卷 (例如 < 500 MB)，因为其正通常在这种情况下更快。 相对成本较低今天的磁盘存储和操作系统和应用程序将驱动器容量推送到最多，它不太小的卷，此类将使用。 FAT32 伸缩性比 FAT 更好，较大卷上，但仍不适当的文件系统的 Windows 服务器。  
FAT 和 FAT32 通常实现了在过去如它们已被视为更轻松地可恢复和可使用与卷问题的情况下的本机 DOS 工具来管理。 现在，使用各种 NTFS 可恢复性工具生成同时本机到操作系统，但可用作第三方实用程序可用，应不再有未使用 NTFS 文件系统的有效参数。  
  
## <a name="do-not-use-ntfs-file-compression"></a>不会使用 NTFS 文件压缩  
 虽然使用 NTFS 文件系统压缩是减少空间卷上的简单办法，但它不是适用于企业的文件服务器。 实现压缩在 CPU 中的所有磁盘操作上将不必要的开销，并最好避免使用。 考虑用于添加更多的磁盘的选项、 近线存储或请考虑将数据存档在认真考虑文件系统压缩之前。  
  
## <a name="review-disk-controller-stripe-size-and-volume-allocation-units"></a>查看磁盘控制器条带大小和卷分配单元。  
 当配置驱动器数组和硬件驱动器控制器中的逻辑驱动器，并确保你匹配控制器条带大小，将使用格式化卷的分配单元大小。 这将确保磁盘读取和写入已获得最佳性能，提供更好的整体服务器性能。  
配置更大的分配单元 （或群集或块） 的大小将会导致效率较低，使用的磁盘空间，但还将提供更高的磁盘 I/O 性能磁头可以在每个读取活动期间读取更多数据。  
若要确定最佳的设置以配置控制器，然后使用磁盘进行格式化，应确定具有类似的文件系统特征的服务器的磁盘子系统上的磁盘的平均传输大小。 使用 Windows 性能监视器工具来监视逻辑磁盘对象计数器的 avg.Disk Bytes/Read 和 avg.正常的活动，以帮助确定要使用的最佳值一段时间内磁盘字节数/写入。  
尽管较小的分配单元大小可能很多小的文件或记录，如果将访问系统合理，为 64 KB 分配单元大小将具有声音的性能和在大多数情况下的 I/O 吞吐量。 改进的性能优化的分配单元大小特别说明，可在磁盘负载增加时。  
  
> [!NOTE]  
>  该格式命令行工具或磁盘管理工具需要格式化卷时指定分配单元大小大于 4096 个字节 (4 KB)。 Windows 资源管理器只能将最多此阈值设置格式。 CHKDSK 命令可以用于确认卷的当前分配单元大小，但需要扫描整个卷之前所需的信息将显示 （显示为字节每个分配单元中）。  
  
## <a name="monitor-drive-space-utilization"></a>监视驱动器空间利用率  
 较少的数据磁盘上的已，它将运行得越快。 这是磁盘的因为在很好地碎片驱动器上，尽可能靠近的外边缘写入数据尽可能，因为这是磁盘的其中的磁盘的速度最快旋转并实现最佳性能。  
磁盘寻道时间通常显著超过读取或写入活动。 如上所述，数据最初是写入外边缘的磁盘。 因为减少了对磁盘存储增加和可用空间的要求，更接近将数据写入磁盘的中心。 磁盘查找增大的定位数据作为头移动离开边缘，并且在发现时间，它将需要更长时间才能读取，影响磁盘 I/O 性能。  
这意味着，监视磁盘空间利用率非常重要不只是出于容量原因而是为了性能还。  
根据经验，逐步目标是保持磁盘可用空间之间 20%到 25%的总磁盘空间。 如果可用磁盘空间下降到低于此阈值，则磁盘输入/输出性能将受到负面影响。  
  
## <a name="implement-a-strategy-to-avoid-disk-fragmentation"></a>实现策略以避免磁盘碎片整理  
 你在磁盘上，包括根驱动器，以防止性能下降定期运行的碎片整理程序实用。 执行此每周忙磁盘上。 磁盘碎片整理程序随 Windows 安装，并可以从一项计划任务按照指定间隔运行。  
  
## <a name="optimize-windows-server-performance-for-background-services"></a>优化后台服务的 Windows Server 性能  
 BizTalk Server 过程 (BTSNTSVC.exe) 作为后台服务运行。   
Windows Server 2008 使用抢先式多任务来确定优先级将受 CPU 就读到的进程线程。 Preemptive 多任务是凭此进程的执行将暂停，启动另一个进程时，操作系统自行一个方法。 此方案可防止单个线程占据 CPU。  
切换到下一个进程内执行从 CPU 被称为上下文切换。 Windows 操作系统的系统包括确定多长时间允许各个线程之前上下文切换时，处理下一个线程在 CPU 上运行的设置。 此时间量称为量程。 此设置允许你选择处理器量程前台程序和后台服务之间共享的方式。 通常为服务器不需要允许前台程序具有比后台服务分配给它的更多 CPU 时间。 也就是说，所有应用程序，它们在服务器上运行的进程，应考虑相等 CPU 时间。  
 若要增加为等 BizTalk 主机实例的后台服务的性能，请按照下列步骤：  
  
1.  单击**启动**，单击**控制面板**，然后单击**系统**。  
  
2.  单击**高级**选项卡上，并依次**设置**下**性能**。  
  
3.  单击**高级**选项卡上，单击**后台服务**，然后单击**确定**两次。  
  
## <a name="disable-non-essential-services"></a>禁用不必要的服务  
 Windows Server 2008 的默认安装启用 BizTalk Server 环境中可能不需要的多个服务。 每个正在运行的服务使用系统资源，因此不必要的服务应被禁用，从而改善整体性能。  
禁用服务时应小心。 彻底研究再禁用该服务，因为 Windows Server 需要某些服务正在运行的服务的目的。 如果所需的 Windows Server 2008 服务被禁用，操作系统可能无法运行，甚至无法启动。  
若要禁用不需要专用的 BizTalk Server 的 Windows Server 2008 服务，请按照下列步骤：  
  
1.  单击 **启动**, ，指向 **管理工具**, ，然后单击 **计算机管理**。  
  
2.  下**计算机管理 （本地）**，展开**服务和应用程序**，然后单击**服务**。  
    在**状态**列中，每个正在运行的服务标记为"已启动。" 停止并禁用任何不必要地，启动的服务，例如，以下服务不需要专用 BizTalk 服务器上：  
  
    -   警报  
  
    -   ClipBook  
  
    -   DHCP Server  
  
    -   传真服务  
  
    -   文件复制  
  
    -   红外的监视器  
  
    -   Internet 连接共享  
  
    -   Messenger  
  
    -   NetMeeting 远程桌面共享  
  
    -   网络 DDE  
  
    -   网络 DDE DSDM  
  
    -   NWLink NetBIOS  
  
    -   NWLink IPX/SP  
  
    -   打印后台处理程序  
  
    -   电话服务  
  
    -   Telnet  
  
    -   不间断电源  
  
3.  请注意取决于你想要禁用每个服务的服务。 为此，请按照下列步骤进行操作：  
  
    1.  双击你想要禁用的服务。  
  
    2.  单击 **依赖关系** 选项卡。  
  
    3.  在**此服务依赖于以下的系统组件**列表中，记下此服务依赖于该服务。  
  
    4.  在**以下系统组件依赖于此服务**列表中，记下该服务，无法启动而不进行此服务，然后单击**确定**。  
  
4.  一次一个地禁用所选每个服务。 为此，请按照下列步骤进行操作：  
  
    1.  右键单击你想要禁用，，然后单击的服务**属性**。  
  
    2.  在**启动类型**列表中，单击**禁用**。  
  
    3.  如果你想要立即停止服务，请单击**停止**。  
  
         如果**停止其他服务**对话框出现时，请注意其他相关服务将也停止，然后单击**是**，然后单击**确定**。  
  
5.  重复步骤 4，以禁用不重要的其他服务。  
  
> [!NOTE]  
>  禁用每个服务以确保未禁用您想要继续使用的服务后，请测试正确的操作的服务器。   
> 如果服务器是 BizTalk 服务器通常是，Windows Server 2008 域的成员必须将 TCP/IP helper 服务对您的系统以正确应用于此计算机的组策略。   
> 当禁用 DHCP 客户端时，DHCP 客户端停止 DNS 动态更新协议注册，并且需要手动为此客户端添加到 DNS 服务器的 DNS 记录。  
  
## <a name="manually-load-microsoft-certificate-revocation-lists"></a>手动加载 Microsoft 证书吊销列表  
 在开始时的.NET 应用程序，.NET Framework 将尝试下载的证书吊销列表 (CRL) 的任何签名的程序集。 如果你的系统没有直接访问 Internet，或者被限制访问 Microsoft.com 域，这可能会延迟启动 BizTalk Server。 若要避免在应用程序启动此延迟，可以使用以下步骤手动下载并安装代码签名你的系统上的证书吊销列表。  
  
1.  下载中的最新 CRL 更新[ http://crl.microsoft.com/pki/crl/products/CodeSignPCA.crl ](http://go.microsoft.com/fwlink/?LinkID=117794) (http://go.microsoft.com/fwlink/?LinkID=117794)和[ http://crl.microsoft.com/pki/crl/products/CodeSignPCA2.crl ](http://go.microsoft.com/fwlink/?LinkId=117795) (http://go.microsoft.com/fwlink/?LinkId=117795)。  
  
2.  将的 CodeSignPCA.crl 和 CodeSignPCA2.crl 文件移到独立的系统。  
  
3.  从命令提示符处，输入以下命令以使用 certutil 实用程序来使用 CRL 在步骤 1 中下载更新的本地证书存储区：  
  
     certutil – addstore CA c:\CodeSignPCA.crl  
  
 CRL 文件将定期更新，因此您应该考虑设置的重复任务的下载和安装 CRL 更新。 若要查看的下一步的更新时间、 双击.crl 文件并查看的值**下一步更新**字段。  
  
## <a name="synchronize-time-on-all-servers"></a>将所有服务器上的时间同步  
 许多操作涉及票证，回执和日志记录依赖于正在准确的本地系统时钟。 这是在分布式环境中，其中系统之间的时间差异可能会导致日志要同步的或由一个系统被拒绝由另一个为过期颁发票证尤其如此或尚未生效。  
  
 服务器配置为自动同步时间的详细信息，请参阅[配置自动域时间同步的客户端计算机](http://go.microsoft.com/fwlink/?LinkId=99420)(http://go.microsoft.com/fwlink/?LinkId=99420)。  
  
## <a name="configure-the-windows-pagefile-for-optimal-performance"></a>配置 Windows 页面文件以获得最佳性能  
 为了获得最佳性能，请遵循以下准则来配置 Windows 页面文件 （分页文件）：  
  
1.  **将分页文件移动到不同的操作系统安装以减少磁盘争用和提高磁盘性能的物理驱动器物理卷**-BizTalk Server 在计算机上，与移动相关的性能提升分页文件的文档处理负载而异。 在 SQL Server 计算机上将页面文件移动到单独的卷被视为由于 SQL Server 的磁盘密集型特性的所有方案中的最佳做法。  
  
2.  **隔离到一个或多个专用物理驱动器配置为 RAID 0 （条带化） 或 raid-1 （镜像） 的数组，或在没有 RAID 的单个磁盘上分页文件**-通过使用专用的磁盘或驱动器数组其中页面文件。SYS 是整个卷上唯一的文件、 分页文件将不会变得零碎，因而也提高了性能。 与大多数磁盘的数组，数组的性能得到改进由于数组中的物理磁盘数已增加。 如果分页文件中的磁盘阵列的多个物理驱动器上的多个卷之间分布，分页文件大小应为数组中每个驱动器上相同的大小。 在配置磁盘阵列，也建议使用具有相同的容量和速度的物理驱动器。 请注意冗余不通常需要分页文件。  
  
3.  **未配置 RAID 5 阵列上的分页文件**-建议不要在 RAID 5 阵列上分页文件的配置，因为分页文件活动编写需要进行大量和 RAID 5 数组更好地适用于读取性能不是写入性能。  
  
4.  **如果你没有资源来将分页文件移动到物理卷中，而不是操作系统安装上，配置要作为操作系统相同的逻辑卷上驻留的分页文件**-配置可驻留在分页文件这将在同一个物理磁盘上，因为操作系统将增加磁盘的另一个逻辑卷查找时间和降低系统性能，因为磁盘驱动器盘磁头将不断卷，或者访问页面文件之间移动操作系统文件、 应用程序文件和数据文件。 此外，通常是通常与最近外边缘的物理磁盘的物理磁盘的第一个分区上安装操作系统以及其中磁盘速度是，关联性能最适合的磁盘。  
  
    > [!IMPORTANT]  
    >  如果你删除分页文件从启动分区，Windows 无法创建故障转储文件 （内存。DMP) 在其中写入调试信息的事件中内核模式下停止发生错误。 如果你需要故障转储文件，则您将别无选择但若要将保留至少的页面文件大小的物理内存 + 1 MB 上启动分区。  
  
5.  **手动设置页面文件的大小**– 手动设置页面文件的大小通常提供更好的性能比允许自动调整大小的服务器或根本没有分页文件。 优化最佳做法是设置的初始 （最低配置） 和分页文件的最大大小设置为相同的值。 这可不确保任何处理资源丢失页面文件，可能是密集型操作的动态调整大小。 假设已变得约束系统上的内存资源时，通常会发生此大小调整的活动，也是如此。 设置值还确保磁盘上的分页区域是一个单独的、 临近的区域，提高磁盘的相同的最小和最大页面文件大小查找时间。 Windows Server 2008 自动建议总页面文件大小等于已安装 RAM 量的 1.5 倍。 在服务器上具有足够磁盘空间，结合使用的所有磁盘上分页文件应配置最多两次以获得最佳性能的物理内存。  
  
## <a name="remove-cpu-intensive-screen-savers"></a>删除大量占用 CPU 的屏幕保护程序  
 三维或 OpenGL 屏幕保护程序都已知进行大量占用 CPU 的并在运行时会使用重要的系统资源。 最好是避免作为服务器生成时，选项安装这些一起删除，或将其删除，如果已安装。 基本"Windows Server 2008"或空白的屏幕保护程序是使用大量占用 CPU 的屏幕保护程序的绝佳替代方法。  
  
## <a name="see-also"></a>另请参阅  
 [优化操作系统性能](../technical-guides/optimizing-operating-system-performance.md)