---
title: 优化操作系统性能的通用指南 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc9ca38e-1feb-4f34-a64b-d04566e85db9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7674b1f7b9a24337985bcb7496c03cae88115de
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007878"
---
# <a name="general-guidelines-for-improving-operating-system-performance"></a>优化操作系统性能的通用指南
应遵循以下常规准则来提高操作系统性能：  
  
## <a name="install-the-latest-bios-storage-area-network-san-drivers-network-adapter-firmware-and-network-adapter-drivers"></a>安装最新的 BIOS、 存储区域网络 (SAN) 驱动程序、 网络适配器的固件和网络适配器驱动程序  
 硬件制造商会定期发布可以提高性能和可用性相关联的硬件的 BIOS、 固件和驱动程序更新。 请访问硬件制造商的网站来下载并应用 BizTalk Server 环境中的每台计算机上的以下硬件组件的更新：  
  
1.  BIOS 更新  
  
2.  SAN 驱动程序 （如果使用 SAN）  
  
3.  NIC 固件  
  
4.  NIC 驱动程序  
  
## <a name="enable-the-high-performance-power-plan-on-all-biztalk-server-and-sql-server-computers"></a>启用"高性能"电源计划在所有 BizTalk Server 和 SQL Server 计算机上。  
 默认情况下，Windows Server 2008/2008 R2 集 （推荐） 已平衡电源计划，从而使能源节省，但可能会导致增加延迟时间 （速度较慢的一些任务响应时间） 并导致性能问题与 CPU 密集型应用程序。  
  
 为了降低延迟，您必须确保运行 BizTalk Server 的所有服务器和 SQL Server 的 Windows**电源计划**设置为**高性能**。 有关如何切换到详细信息**高性能**电源计划，请参阅知识库文章： 2207548 [Windows Server 2008 R2 上的总体性能下降](http://go.microsoft.com/fwlink/?LinkID=219677)(http://go.microsoft.com/fwlink/?LinkID=219677)。  
  
## <a name="evaluate-the-usage-of-intel-hyper-threading-on-biztalk-server-and-sql-server-computers"></a>评估 BizTalk Server 和 SQL Server 计算机上的 Intel 超线程使用情况  
  
-   **Pre Nehalem 超线程**:  
  
    -   超线程应关闭在 BizTalk Server 计算机。 这是通常在 BIOS 设置的处理器设置中找到的 BIOS 设置。 超线程使服务器显示为具有更多处理器/处理器内核不是实际执行;但是，超线程处理器通常 20-30%的物理处理器核心的性能之间提供。 当 BizTalk Server 计算要调整其自我优化算法的处理器数目时，超线程处理器会导致这些调整要被扭曲，这可能会导致负的整体性能。  
  
    -   超线程应关闭状态在 SQL Server 计算机，因为可能会导致高水平的争用 （例如 BizTalk Server) 的应用程序可能导致性能降低在 SQL Server 计算机上的超线程环境中使用。  
  
-   **Nehalem 超线程**： 与不同在较旧体系结构中启用超线程在 Intel 微体系结构"Nehalem"处理器可提供最大容量几乎呈线性增加。 为获得最佳性能结果，在将"Nehalem"处理器时我们建议通过启用标记会增加吞吐量 Intel 超线程 (H T) 技术来配置计算机的 BIOS。  
  
-   **硬件虚拟化**： 时使用的硬件虚拟化，虚拟机使用虚拟处理器。 可用的 Cpu 数基于时配置虚拟机选择的设置。 如果硬件超线程，虚拟机不会知道它是超线程。  
  
## <a name="assign-the-msdtc-log-file-directory-to-a-separate-dedicated-drive"></a>将 MSDTC 日志文件目录分配到单独的专用驱动器  
 在 BizTalk Server 环境使用不同的 SQL Server 计算机上的多个 MessageBox 数据库中，产生关联与 Microsoft 分布式事务处理协调器 (MSDTC) 的额外开销。 默认情况下，MSDTC 日志文件位于运行 DTC 服务的计算机的 %systemdrive%\windows\system32\msdtc 目录中。 若要降低 DTC 日志记录可能成为性能瓶颈的可能性，请考虑将 MSDTC 日志文件目录移到快速的磁盘驱动器。  
  
 若要更改 MSDTC 日志文件目录，请参阅[配置 DTC 日志记录](http://go.microsoft.com/fwlink/?LinkID=204107)(http://go.microsoft.com/fwlink/?LinkID=204107)。  
  
## <a name="configure-antivirus-software-to-avoid-real-time-scanning-of-biztalk-server-executables-and-file-drops"></a>若要避免的 BizTalk Server 可执行文件的实时扫描的防病毒软件配置和丢失的文件  
 防病毒软件实时扫描的 BizTalk Server 可执行文件和任何文件夹或文件共享监视 BizTalk server 接收位置 BizTalk Server 性能产生负面影响。 如果 BizTalk Server 计算机上安装防病毒软件，禁用实时扫描的非可执行文件的文件类型引用的任何 BizTalk Server 接收位置 （通常。XML，但也可以是.csv、.txt 等。)和配置 BizTalk Server 可执行文件的扫描中排除的防病毒软件  
  
## <a name="disable-intrusion-detection-network-scanning-between-computers-in-the-biztalk-server-environment"></a>禁用扫描在 BizTalk Server 环境中的计算机之间的入侵检测网络  
 入侵检测软件可以慢，或者甚至通过网络防止有效的通信。 如果安装入侵检测软件，则禁用网络扫描 BizTalk Server 计算机和外部数据存储库 (SQL Server) 计算机之间或消息传送服务 （如消息队列和 WebSphere MQSeries） 的计算机。  
  
## <a name="defragment-all-disks-in-the-biztalk-server-environment-on-a-regular-basis"></a>对定期在 BizTalk Server 环境中的所有磁盘进行碎片都整理  
 在 BizTalk Server 环境中的过多的磁盘碎片会对性能产生负面影响。 请按照下列步骤进行碎片整理 BizTalk Server 环境中的磁盘：  
  
1.  对所有磁盘进行碎片都整理 (本地和 SAN/NAS) 定期通过计划非工作时间磁盘碎片整理。  
  
2.  对 Windows 页面文件进行碎片整理和预分配在 BizTalk Server 环境中每个磁盘的主文件表，以提升总体系统性能。  
  
    > [!NOTE]  
    >  若要预分配主文件表，请参阅知识库文章 961095， ["主文件表有关区域在 Windows Vista 和 Windows Server 2008 中的预订"](http://go.microsoft.com/fwlink/?LinkID=204563) (http://go.microsoft.com/fwlink/?LinkID=204563)。  
  
## <a name="if-antivirus-software-is-installed-on-the-sql-server-computer-disable-real-time-scanning-of-data-and-transaction-files"></a>如果 SQL Server 计算机上安装防病毒软件，请禁止对实时扫描的数据和事务文件  
 SQL Server 数据和事务文件 （.mdf、.ndf、.ldf、.mdb） 的实时扫描可以提高磁盘 I/O 争用，并减少 SQL Server 的性能。 请注意，BizTalk Server 环境之间的 SQL Server 数据和事务文件的名称可能会有所不同。 有关使用默认 BizTalk Server 配置创建的数据和事务的详细信息，请参阅[优化文件组的数据库 2](../technical-guides/optimizing-filegroups-for-the-databases2.md)。  
  
## <a name="configure-msdtc-for-biztalk-server-and-sql-server"></a>为 BizTalk Server 和 SQL Server 配置 MSDTC  
 若要简化 SQL Server 和 BizTalk Server 之间的事务，必须启用 Microsoft 分布式事务处理协调器 (MSDTC)。  
  
#### <a name="to-configure-distributed-transaction-coordinator-dtc"></a>若要配置分布式事务处理协调器 (DTC)  
  
1.  单击**启动**，单击**运行**，类型**dcomcnfg**，然后单击**确定**打开**组件服务**.  
  
2.  在控制台树中，依次展开“组件服务”、“计算机”、“我的计算机”、“分布式事务处理协调器”，然后单击“本地 DTC”。  
  
3.  右键单击**本地 DTC**，然后单击**属性**以显示**本地 DTC 属性**对话框。  
  
4.  上**跟踪**选项卡上，在**输出选项**部分中，清除**跟踪输出**框。  
  
5.  单击 **“安全性”** 选项卡。  
  
6.  确保以下四个选项均处于选中状态，且清除所有其他选项：  
  
    -   **网络 DTC 访问**  
  
    -   **允许入站**  
  
    -   **允许出站**  
  
    -   **不要求进行验证**  
  
7.  单击**确定**以关闭**本地 DTC 属性**对话框。 如果系统提示您重新启动 MSDTC 服务，请单击**是**。  
  
8.  关闭“组件服务”。  
  
9. 单击**启动**，依次指向**管理工具**，然后单击**高级安全 Windows 防火墙**。  
  
10. 在高级安全 Windows 防火墙中，单击**入站规则**。  
  
11. 在中**入站规则**窗格中，右键单击**分布式事务处理协调器*** （根据需要），然后单击**启用规则**。  
  
12. 在高级安全 Windows 防火墙中，单击**出站规则**。  
  
13. 在中**出站规则**窗格中，右键单击**分布式事务处理协调器*** （根据需要），然后单击**启用规则**。  
  
14. 上**Control Panel**，双击**管理工具**。  
  
15. 在右侧窗格中，双击**Services**。  
  
16. 在右侧窗格中的**服务 （本地）**，右键单击**COM + 系统应用程序**，单击**重启**，并等待服务重新启动。  
  
17. 右键单击并重启“分布式事务处理协调器”服务。  
  
18. 右键单击并重启“SQL Server (MSSQLSERVER)”服务。  
  
19. 关闭“服务(本地)”，然后关闭“管理工具”。  
  
## <a name="configure-firewalls-for-biztalk-server"></a>为 BizTalk Server 配置防火墙  
  
> [!NOTE]  
>  此步骤才是必需的如果一个或多个防火墙，则在 BizTalk Server 环境中的位置。  
  
 请查看以下信息为 BizTalk Server 配置防火墙：  
  
- [BizTalk Server 所需端口](http://go.microsoft.com/fwlink/?LinkID=153238)(http://go.microsoft.com/fwlink/?LinkID=153238)。  
  
- 若要配置与防火墙一起使用的 RPC 动态端口分配，请参阅知识库文章 929851， ["在 Windows Vista 和 Windows Server 2008 中已更改 TCP/IP 的默认动态端口范围"](http://go.microsoft.com/fwlink/?LinkID=204568) (超链接"<http://go.microsoft.com/fwlink/?LinkID=204568>"<http://go.microsoft.com/fwlink/?LinkID=204568>). 有关如何配置 Windows 防火墙以适应所需的端口的信息，请参阅[Windows 防火墙和 IPsec 策略部署分步指南](http://go.microsoft.com/fwlink/?LinkID=204569)(<http://go.microsoft.com/fwlink/?LinkID=204569>)。  
  
## <a name="install-appropriate-com-and-msdtc-hotfix-rollup-packages"></a>安装相应的 COM + 和 MSDTC 修补程序汇总包  
 请查看以下信息来安装相应的 COM + 和 MS DTC 修补程序汇总包：  
  
-   MS DTC 修补程序可在 Microsoft 知识库文章 article978476 ["在 Windows Server 2008 R2 MS DTC 修补程序汇总包 1 中修复 MS DTC 问题"](http://go.microsoft.com/fwlink/?LinkID=204109) (http://go.microsoft.com/fwlink/?LinkID=204109)。  
  
-   可以通过搜索找到最新的 DTC 修补程序汇总包 KB 文章[ http://support.microsoft.com ](http://go.microsoft.com/fwlink/?LinkID=96185) (http://go.microsoft.com/fwlink/?LinkID=96185)短语 （包括引号）：  
  
    ```  
    "MS DTC Hotfix Rollup Package"  
    ```  
  
     下面的查询执行此搜索。 选择最新版本：   
    [http://support.microsoft.com/search/default.aspx?query="MS+DTC+Hotfix+Rollup+Package"](http://support.microsoft.com/search/default.aspx?query="MS+DTC+Hotfix+Rollup+Package")  
  
## <a name="use-the-interrupt-affinity-policy-tool-to-bind-network-adapter-interrupts-to-specific-processors-on-multiprocessor-computers"></a>中断-关联策略工具用于绑定到多处理器计算机上的特定处理器的网络适配器中断  
 中断-关联策略 (IntPolicy) 是一个工具，允许您"绑定"或更改的中断 （例如网络适配器） 为给定设备的 CPU 关联到特定的处理器或多处理器计算机上的处理器。 此绑定也称为分区。 从特定网络适配器与多处理器计算机上的特定处理器的中断的绑定会强制执行正在运行的延缓的过程调用 (Dpc) 和中断服务例程 (Isr) 指定的处理器上的网络适配器。 请注意，不能在单处理器计算机上配置中断关联。  
  
> [!NOTE]  
>  DPC 被指对通常将在以后执行内核模式函数的排队调用。 ISR 被指其目的是生成中断时服务设备的例程。 有关延迟的过程调用和中断服务例程的详细信息，请参阅[Windows 驱动程序工具包文档](http://go.microsoft.com/fwlink/?LinkId=84418)(http://go.microsoft.com/fwlink/?LinkId=84418)。  
  
 ![中断&#45;关联策略工具](../technical-guides/media/interrupt-affinitypolicytool.gif "中断 AffinityPolicyTool")  
中断-关联策略工具  
  
 基于 Windows Server 2008 多处理器计算机上中断控制器的默认行为是将设备中断分配给任何可用的处理器。 当网络连接和文件服务器会话的给定的网络适配器是绑定/分区以运行上一组特定的处理器，而不是改进了任何可用的处理器、 性能和可伸缩性关联的网络处理。 大型 BizTalk Server 解决方案通常会采用使用多处理器 SQL Server 计算机具有多个网络适配器中断绑定可能尤为有益的。   
中断绑定使用 IntPolicy 应始终评估测试环境中然后再在生产环境中使用。 硬件、 操作系统和应用程序配置的测试环境应尽可能地接近生产环境。 这将允许你测试各种屏蔽的中断绑定并且确定范围中断绑定将会提高性能。  
 我们建议你禁用超线程支持超线程使用 Cpu 的计算机上配置 IntPolicy 之前。 这将确保，中断将分配给物理处理器而不是逻辑处理器。 分配中断关联到逻辑引用同一个物理处理器的处理器不会提高性能，并甚至可能会降低系统性能。    超链接"The"[中断-关联策略工具](http://go.microsoft.com/fwlink/?LinkID=204111)(http://go.microsoft.com/fwlink/?LinkID=204111)可供从 WHDC 网站的下载。  
  
## <a name="use-the-ntfs-file-system-on-all-volumes"></a>使用 NTFS 文件系统上的所有卷  
 Windows Server 为设置驱动器，包括 NTFS、 FAT 和 FAT32 格式提供了多个文件系统类型。 NTFS 应始终为所选的服务器的文件系统。  
NTFS FAT 和 FAT32 文件系统相比，提供很大的性能优势，因此应以独占方式在 Windows 服务器上。 此外，NTFS 提供针对许多安全性、 可伸缩性、 稳定性和可恢复性优势 FAT 和 FAT32。  
在以前版本的 Windows，FAT 和 FAT32 通常上实现较小的卷 (例如 < 500 MB) 因为它们通常在这种情况下更快。 磁盘存储价格相对便宜今天和操作系统和应用程序推送到最多的驱动器的容量，不太可能此类小的卷，将使用。 FAT32 伸缩性比 FAT 更好，更大的卷上，但仍不适当的文件系统的 Windows 服务器。  
FAT 和 FAT32 通常已实现过去它们是为更轻松地可恢复和可使用本机 DOS 工具出现问题与使用的卷时所示。 目前，各种 NTFS 可恢复性与生成的工具，同时以本机模式到操作系统，并可用作第三方实用程序可用，应不再有未使用 NTFS 文件系统的有效参数。  
  
## <a name="do-not-use-ntfs-file-compression"></a>不使用 NTFS 文件压缩  
 虽然使用 NTFS 文件系统压缩是减少空间卷上的简单方法，但它不是适用于企业的文件服务器。 实现压缩磁盘的所有操作在 CPU 上会不必要的开销，最好避免使用。 考虑添加更多的磁盘的选项、 近线存储或将数据存档在认真考虑文件系统压缩之前，请考虑。  
  
## <a name="review-disk-controller-stripe-size-and-volume-allocation-units"></a>查看磁盘控制器条带大小和卷分配单元。  
 时配置驱动器阵列和逻辑驱动器中硬件驱动器控制器，请确保您与匹配与将使用格式化卷的分配单元大小控制器条带大小。 这将确保磁盘读取和写入已获得最佳性能，并提供更好的总体服务器性能。  
配置更大的分配单元 （或群集或块） 大小会导致磁盘空间来使用效率较低，但还会提供更高版本磁盘 I/O 性能，因为磁盘头期间读取的每个活动可以读取更多数据。  
若要确定的最佳设置： 若要配置控制器和使用的磁盘进行格式化，应确定具有类似的文件系统特征的服务器的磁盘子系统上的磁盘的平均传输大小。 使用 Windows 性能监视器工具来监视平均的逻辑磁盘对象计数器Disk Bytes/Read 和 avg.磁盘字节数/写入的正常活动的期间内以帮助确定要使用的最佳值。  
尽管较小的分配单元大小可能合理许多小文件或记录，如果将访问系统，为 64 KB 分配单元大小提供声音性能和大多数情况下的 I/O 吞吐量。 中的优化的分配单元大小与性能的改进可以特别注意的是磁盘负载增加时。  
  
> [!NOTE]  
>  格式命令行工具或磁盘管理工具需要格式化卷时，指定分配单元大小大于 4096 个字节 (4 KB)。 Windows 资源管理器将仅由此阈值设置格式。 CHKDSK 命令可以用于确认卷的当前分配单元大小，但是它需要扫描整个卷之前 （以字节显示在每个分配单元中） 显示的所需的信息。  
  
## <a name="monitor-drive-space-utilization"></a>监视驱动器空间利用率  
 较少的数据磁盘的它将运行得越快。 这是磁盘的因为也经过碎片整理的驱动器上接近的外边缘写入数据，因为这是磁盘的磁盘位置旋转的速度最快和实现最佳性能。  
磁盘寻道时间是通常相当长的时间比读取或写入活动。 如上文所述，数据最初是写入磁盘的外边缘。 当对磁盘存储的提高和可用空间的需求减少时，更接近将数据写入磁盘的中心。 磁盘寻道时间增加的头移动数量从边缘，作为查找数据和找到时，所花费的时间阅读，妨碍磁盘 I/O 性能。  
这意味着，监视磁盘空间利用率很重要不只是出于容量原因，但性能还。  
根据经验，工作完成保持磁盘可用空间介于 20%到 25%的总磁盘空间的一个目标。 如果可用磁盘空间下降到低于此阈值，则磁盘 I/O 性能将受到负面影响。  
  
## <a name="implement-a-strategy-to-avoid-disk-fragmentation"></a>实施策略，以避免磁盘碎片  
 在你的磁盘，包括根驱动器，用于防止性能下降上定期运行碎片整理程序实用工具。 执行此每周在繁忙的磁盘上。 磁盘碎片整理程序随 Windows 一起安装，并在指定的时间间隔可以从计划任务运行。  
  
## <a name="optimize-windows-server-performance-for-background-services"></a>优化后台服务的 Windows Server 的性能  
 BizTalk Server 进程 (BTSNTSVC.exe) 作为后台服务运行。   
Windows Server 2008 使用强占式多任务来确定将为参加由 CPU 的进程线程的优先级。 抢先式多任务处理是一种方法来暂停进程的执行和启动另一个进程时，操作系统的决定。 此方案可防止单个线程在支配 CPU。  
切换到下一个进程内执行从 CPU 被称为上下文切换。 Windows 操作系统包括确定多长时间允许各个线程发生上下文切换和下一个线程已得到处理之前，在 CPU 上运行的设置。 此时间量称为量程。 此设置允许您选择处理器量程前台程序和后台服务之间的共享方式。 通常为服务器不需要以允许前台程序具有比后台服务分配给它的更多 CPU 时间。 也就是说，所有应用程序和其在服务器上运行的进程应考虑相等的 CPU 时间。  
 若要增加为 BizTalk 主机实例等的后台服务的性能，请执行以下步骤：  
  
1.  单击**启动**，单击**控制面板**，然后单击**系统**。  
  
2.  单击**高级**选项卡，然后依次**设置**下**性能**。  
  
3.  单击**高级**选项卡上，单击**后台服务**，然后单击**确定**两次。  
  
## <a name="disable-non-essential-services"></a>禁用不必要的服务  
 Windows Server 2008 的默认安装启用 BizTalk Server 环境中可能不需要的多个服务。 每个正在运行的服务会占用系统资源，因此不需要的服务应禁用以提高整体性能。  
禁用服务时应小心。 因为某些服务正在运行 Windows Server 需要禁用该服务之前充分研究服务的用途。 如果所需的 Windows Server 2008 服务将被禁用，操作系统可能会无法运行，甚至无法启动。  
若要禁用不需要专用的 BizTalk Server 的 Windows Server 2008 服务，请按照下列步骤：  
  
1.  单击**启动**，依次指向**管理工具**，然后单击**计算机管理**。  
  
2.  下**计算机管理 （本地）**，展开**服务和应用程序**，然后单击**Services**。  
    在中**状态**列中，每个服务正在运行的标记为"已启动。" 停止并禁用任何服务，就会发生误报，例如，以下服务不需要专用的 BizTalk Server 上：  
  
    -   Alerter  
  
    -   剪贴簿  
  
    -   DHCP 服务器  
  
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
  
    2.  单击**依赖项**选项卡。  
  
    3.  在中**此服务依赖于以下的系统组件**列表中，记下此服务依赖于该服务。  
  
    4.  在中**以下系统组件依赖于此服务**列表中，记下该服务，不能启动而无需此服务，然后单击**确定**。  
  
4.  一次一个地禁用所选的每个服务。 为此，请按照下列步骤进行操作：  
  
    1.  右键单击你想要禁用，，然后单击的服务**属性**。  
  
    2.  在中**启动类型**列表中，单击**禁用**。  
  
    3.  如果你想要立即停止该服务，请单击**停止**。  
  
         如果**停止其他服务**出现对话框，请注意其他从属服务，将停止，，然后单击**是**，然后单击**确定**。  
  
5.  重复步骤 4，以禁用不重要的其他服务。  
  
> [!NOTE]  
>  禁用每个服务，以确保未禁用你想要继续使用的服务后，请测试服务器以执行正确的操作。   
> 如果服务器是成员的 Windows Server 2008 域，这通常是 BizTalk Server，你必须以正确地应用于此计算机的组策略在系统上具有 TCP/IP helper 服务。   
> 如果禁用 DHCP 客户端，DHCP 客户端停止 DNS 动态更新协议注册，并且需要手动为此客户端添加到 DNS 服务器的 DNS 记录。  
  
## <a name="manually-load-microsoft-certificate-revocation-lists"></a>手动加载 Microsoft 证书吊销列表  
 在启动时的.NET 应用程序，.NET Framework 将尝试下载的证书吊销列表 (CRL) 适用于任何已签名的程序集。 如果您的系统不具有直接访问 Internet，或受限制而无法访问 Microsoft.com 域，这可能会延迟启动 BizTalk Server。 若要避免这种延迟在应用程序启动时，可以使用以下步骤来手动下载并安装在系统上签名证书吊销列表的代码。  
  
1. 下载最新的 CRL 更新从[ http://crl.microsoft.com/pki/crl/products/CodeSignPCA.crl ](http://go.microsoft.com/fwlink/?LinkID=117794) (http://go.microsoft.com/fwlink/?LinkID=117794)并[ http://crl.microsoft.com/pki/crl/products/CodeSignPCA2.crl ](http://go.microsoft.com/fwlink/?LinkId=117795) (http://go.microsoft.com/fwlink/?LinkId=117795)。  
  
2. 将 CodeSignPCA.crl 和 CodeSignPCA2.crl 文件移动到独立的系统。  
  
3. 从命令提示符下输入以下命令以使用 certutil 实用程序以使用在步骤 1 中下载 CRL 更新本地证书存储区：  
  
    certutil – addstore CA c:\CodeSignPCA.crl  
  
   CRL 文件将定期更新，因此您应该考虑设置重复的任务的下载和安装 CRL 更新。 若要查看下一步的更新时间，双击.crl 文件以及查看的值**下一步更新**字段。  
  
## <a name="synchronize-time-on-all-servers"></a>同步所有服务器上的时间  
 涉及票证的许多操作，回执和日志记录将被准确的本地系统时钟。 这是在分布式环境中，系统之间的时间差异可能导致的日志，以同步的或由为已过期拒绝的另一个系统颁发票证尤其如此或尚未生效。  
  
 服务器配置为自动同步时间的详细信息，请参阅[配置自动域时间同步的客户端计算机](http://go.microsoft.com/fwlink/?LinkId=99420)(http://go.microsoft.com/fwlink/?LinkId=99420)。  
  
## <a name="configure-the-windows-pagefile-for-optimal-performance"></a>配置 Windows 页面文件以获得最佳性能  
 为了获得最佳性能，请遵循以下准则来配置 Windows 页面文件 （分页文件）：  
  
1.  **将页面文件移到独立于操作系统安装以减少磁盘争用并提高磁盘性能的物理驱动器的物理卷**-BizTalk Server 在计算机上，与移动相关的性能提升分页文件的文档处理负载而异。 SQL Server 计算机上将页面文件移动到一个单独的卷被认为在所有方案中由于磁盘密集型特性的 SQL Server 最佳实践。  
  
2.  **隔离一个或多个专用物理驱动器上配置为 RAID 0 （带区） 或 RAID 1 （镜像） 数组，或在没有 RAID 的单个磁盘上分页文件**-通过使用专用的磁盘或驱动器阵列的页面文件。SYS 是整个卷上唯一的文件、 分页文件不会变成碎片，这还可以提高性能。 与大多数磁盘的阵列，该数组的性能得到改进由于数组中的物理磁盘的数量已增加。 如果页面文件磁盘阵列中的多个物理驱动器上的多个卷之间分布，分页文件大小应为数组中每个驱动器上的相同大小。 在配置磁盘阵列，它也被建议使用具有相同的容量和速度的物理驱动器。 请注意冗余不是通常所需的分页文件。  
  
3.  **未配置 RAID 5 阵列上的分页文件**-不建议在 RAID 5 阵列上分页文件的配置，因为分页文件活动写入密集型和 RAID 5 阵列更好地适合于读取性能不是写入性能。  
  
4.  **如果还没有资源，以将页面文件移动到物理卷，而不在安装操作系统，配置要与操作系统相同的逻辑卷上驻留的分页文件**-配置页面文件，使其位于另一个逻辑卷位于同一物理磁盘，因为操作系统将增加磁盘寻道时间并降低系统性能，因为磁盘驱动器的盘片磁头将不断移动之间的卷，或者访问的页面文件操作系统文件、 应用程序文件和数据文件。 此外，通常最接近于物理磁盘的外边缘的物理磁盘的第一个分区通常安装操作系统，其中磁盘速度是，关联的性能最适合于该磁盘。  
  
    > [!IMPORTANT]  
    >  如果你从启动分区删除分页文件，Windows 无法创建崩溃转储文件 （的内存。DMP) 用来在的内核模式下停止写入调试信息时发生错误。 如果你需要的崩溃转储文件，则您将别无选择，只能离开至少为页面文件大小的物理内存 + 1 MB 的引导分区上。  
  
5.  **手动设置的页面文件大小**– 手动设置分页文件的大小通常提供更好的性能比这样，服务器可以自动调整大小或根本无分页文件。 优化最佳做法是设置初始 （最低配置） 和页面文件的最大大小设置为相同的值。 这可确保没有处理资源丢失到分页文件，可能是操作的动态调整大小。 考虑到此大小调整活动通常发生在系统上的内存资源成为约束时，也是如此。 值还确保磁盘上的分页区域是一个单一的连续未分配区域，从而提高磁盘的相同的最小值和最大页面文件大小寻道时间的设置。 Windows Server 2008 会自动推荐总页面文件大小等于已安装的 RAM 量的 1.5 倍。 在服务器上有足够磁盘空间，结合使用的所有磁盘上的分页文件应配置最多两次以获得最佳性能的物理内存。  
  
## <a name="remove-cpu-intensive-screen-savers"></a>删除大量占用 CPU 的屏幕保护程序  
 3D 或 OpenGL 屏幕保护程序已知会耗费大量的 CPU 和运行时使用的重要系统资源。 最好是避免在服务器内部版本时，选择安装这些参数，或将其删除，如果已安装。 基本"Windows Server 2008"或空白屏幕保护程序将优先于使用大量占用 CPU 的屏幕保护程序。  
  
## <a name="see-also"></a>请参阅  
 [优化操作系统性能](../technical-guides/optimizing-operating-system-performance.md)