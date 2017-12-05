---
title: "操作系统优化 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af2e77d0-d69b-4ae4-b689-96831fc4deed
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15ef1c8d5860b6e9bd3683551096c947de8c7a42
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="operating-system-optimizations"></a>操作系统优化
本主题提供有关优化性能的建议[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在生产中使用计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。 这些优化应用后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]已安装并配置。  
  
## <a name="general-guidelines-for-improving-operating-system-performance"></a>提高操作系统性能的一般准则  
 可以使用以下建议以提高操作系统性能：  
  
### <a name="install-the-latest-bios-storage-area-network-san-drivers-network-adapter-firmware-and-network-adapter-drivers"></a>安装最新的 BIOS、 存储区域网络 (SAN) 驱动程序、 网络适配器的固件和网络适配器驱动程序  
 硬件制造商定期发布可以提高性能和可用性相关联的硬件的 BIOS、 固件和驱动程序更新。 请访问硬件制造商的网站上下载并应用在 BizTalk Server 环境中的每台计算机上的以下硬件组件的更新：  
  
1.  BIOS 更新  
  
2.  SAN 驱动程序 （如果使用 SAN）  
  
3.  NIC 固件  
  
4.  网卡驱动程序  
  
### <a name="assign-the-msdtc-log-file-directory-to-a-separate-dedicated-drive"></a>将 MSDTC 日志文件目录分配给单独的专用驱动器  
 在 BizTalk Server 环境中的 SQL Server 的单独计算机上的多个 MessageBox 数据库，产生关联与 Microsoft 分布式事务处理协调器 (MSDTC) 的其他开销。 默认情况下，MSDTC 日志文件位于运行 DTC 服务的计算机的 %systemdrive%\windows\system32\msdtc 目录中。 若要缓解 DTC 日志记录可能成为性能瓶颈的可能性，请考虑将 MSDTC 日志文件目录移到快速的磁盘驱动器。 若要更改 MSDTC 日志文件目录，请按照下列步骤：  
  
1.  单击**启动**，单击**运行**，和类型**dcomcnfg**以启动**组件服务**管理控制台。  
  
2.  展开**组件服务**，展开**计算机**，右键单击**我的电脑**，然后单击**属性**。  
  
3.  在**我的电脑属性**对话框中，单击**MSDTC**选项卡。  
  
4.  在**位置**编辑框下的**日志信息**，键入你希望创建新的日志 （例如 G:\Logs\DTCLog） 的路径。  
  
5.  单击**重置日志**，并且系统将提示你为服务重启。 单击**确定**以重新启动 DTC 服务，然后单击**确定**以确认已重新启动 MSDTC 服务。  
  
### <a name="configure-antivirus-software-to-avoid-real-time-scanning-of-biztalk-server-executables-and-file-drops"></a>配置防病毒软件，以避免的 BizTalk Server 可执行文件的实时扫描和丢失的文件  
 防病毒软件实时扫描的 BizTalk Server 可执行文件和任何文件夹或文件共享由 BizTalk Server 监视接收位置可以对 BizTalk 服务器性能产生负面影响。 如果在 BizTalk Server 计算机上安装防病毒软件，禁用实时扫描的非可执行文件类型引用的任何 BizTalk Server 接收位置 （通常。XML，但也可以是.csv、.txt，等等。)并配置防病毒软件扫描的 BizTalk Server 可执行文件中排除  
  
### <a name="disable-intrusion-detection-network-scanning-between-computers-in-the-biztalk-server-environment"></a>禁用扫描在 BizTalk Server 环境中的计算机之间的入侵检测网络  
 入侵检测软件可以慢，或者甚至阻止通过网络的有效的通信。 如果安装入侵检测软件后，禁用网络扫描 BizTalk Server 计算机和外部数据存储库 (SQL Server) 的计算机之间或消息传送服务 （消息队列、 WebSphere MQSeries 等） 的计算机。  
  
### <a name="defragment-all-disks-in-the-biztalk-server-environment-on-a-regular-basis"></a>对在定期 BizTalk Server 环境中的所有磁盘碎片都整理  
 在 BizTalk Server 环境中的过多的磁盘碎片将会对性能产生负面影响。 请按照下列步骤进行碎片整理在 BizTalk Server 环境中的磁盘：  
  
1.  对所有磁盘碎片都整理 (本地和 SAN/NAS) 定期通过计划非高峰时段磁盘碎片整理。  
  
2.  碎片整理 Windows 页面文件和预分配在 BizTalk Server 环境中的每个磁盘的主机文件表，以提升总体系统性能。  
  
    > [!NOTE]  
    >  使用在 PageDefrag 实用工具[http://go.microsoft.com/fwlink/?LinkId=108976](http://go.microsoft.com/fwlink/?LinkId=108976)以对 Windows 页面文件进行碎片整理和预分配主文件表。  
  
### <a name="if-antivirus-software-is-installed-on-the-sql-server-computers-disable-real-time-scanning-of-data-and-transaction-files"></a>如果在 SQL Server 计算机上安装防病毒软件，禁用实时的数据和事务文件扫描  
 SQL Server 数据和事务文件 （.mdf、.ndf、.ldf、.mdb） 的实时扫描可以提高磁盘 I/O 争用，并降低 SQL 服务器的性能。 请注意，BizTalk Server 环境之间的 SQL Server 数据和事务文件的名称可能会有所不同。 有关创建与默认 BizTalk 服务器配置的数据和事务文件的详细信息，请参阅[优化的数据库的文件组](http://msdn.microsoft.com/library/ee377060\(v=bts.70\).aspx)。  
  
### <a name="configure-msdtc-for-biztalk-server"></a>为 BizTalk Server 中配置 MSDTC  
 查看以下信息来为 BizTalk Server 中配置 MSDTC:  
  
-   若要在 BizTalk Server 上配置 MSDTC，请参阅"启用 DTC 本地主机服务器上"部分中的 BizTalk Server 2010 安装指南[http://go.microsoft.com/fwlink/?LinkID=191321](http://go.microsoft.com/fwlink/?LinkID=191321)。  
  
-   在的"疑难解答问题与 MSDTC" [http://go.microsoft.com/fwlink/?LinkID=202142](http://go.microsoft.com/fwlink/?LinkID=202142)。  
  
### <a name="configure-firewalls-for-biztalk-server"></a>为 BizTalk Server 中配置防火墙  
  
> [!NOTE]  
>  此步骤才是必需的一个或多个防火墙如果都在你的 BizTalk 服务器环境中的位置。  
  
 查看以下信息来为 BizTalk Server 中配置防火墙：  
  
-   "所需端口 BizTalk Server"在[http://go.microsoft.com/fwlink/?LinkId=101607](http://go.microsoft.com/fwlink/?LinkId=101607)。  
  
-   "如何配置 RPC 动态端口分配要使用防火墙"在[http://go.microsoft.com/fwlink/?LinkID=76145](http://go.microsoft.com/fwlink/?LinkID=76145)。  
  
### <a name="use-the-ntfs-file-system-on-all-volumes"></a>使用上的所有卷的 NTFS 文件系统  
 [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]提供用于设置驱动器，包括 NTFS、 FAT 和 FAT32 格式的多个文件系统类型。 NTFS 应始终为文件系统的服务器的选择。[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]  
  
 NTFS 针对 FAT 和 FAT32 文件系统中有很大的性能优点，并应在 Windows 服务器上以独占方式使用。 此外，NTFS 通过 FAT 和 FAT32 提供许多安全性、 可伸缩性、 稳定性和可恢复性的好处。  
  
 在以前版本的 Windows，FAT 和 FAT32 上通常实现较小的卷 (例如 < 500 MB)，因为其正通常在这种情况下更快。 相对成本较低今天的磁盘存储和操作系统和应用程序将驱动器容量推送到最多，它不太小的卷，此类将使用。 FAT32 伸缩性比 FAT 更好，较大卷上，但仍不适当的文件系统的 Windows 服务器。  
  
 FAT 和 FAT32 通常实现了在过去如它们已被视为更轻松地可恢复和可使用与卷问题的情况下的本机 DOS 工具来管理。 现在，使用各种 NTFS 可恢复性工具生成同时本机到操作系统，但可用作第三方实用程序可用，应不再有未使用 NTFS 文件系统的有效参数。  
  
### <a name="do-not-use-ntfs-file-compression"></a>不会使用 NTFS 文件压缩  
 虽然使用 NTFS 文件系统压缩是减少空间卷上的简单办法，但它不是适用于企业的文件服务器。 实现压缩在 CPU 中的所有磁盘操作上将不必要的开销，并最好避免使用。 考虑用于添加更多的磁盘的选项、 近线存储或请考虑将数据存档在认真考虑文件系统压缩之前。  
  
### <a name="review-disk-controller-stripe-size-and-volume-allocation-units"></a>查看磁盘控制器条带大小和卷分配单元。  
 当配置驱动器数组和硬件驱动器控制器中的逻辑驱动器，并确保你匹配控制器条带大小，将使用格式化卷的分配单元大小。 这将确保磁盘读取和写入已获得最佳性能，提供更好的整体服务器性能。  
  
 配置更大的分配单元 （或群集或块） 的大小将会导致效率较低，使用的磁盘空间，但还将提供更高的磁盘 I/O 性能磁头可以在每个读取活动期间读取更多数据。  
  
 若要确定最佳的设置以配置控制器，然后使用磁盘进行格式化，应确定具有类似的文件系统特征的服务器的磁盘子系统上的磁盘的平均传输大小。 使用[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]性能监视器工具，用于监视的平均逻辑磁盘对象计数器Disk Bytes/Read 和 avg.正常的活动，以帮助确定要使用的最佳值一段时间内磁盘字节数/写入。  
  
 尽管较小的分配单元大小可能很多小的文件或记录，如果将访问系统合理，为 64 KB 分配单元大小将具有声音的性能和在大多数情况下的 I/O 吞吐量。 改进的性能优化的分配单元大小特别说明，可在磁盘负载增加时。  
  
> [!NOTE]  
>  该格式命令行工具或磁盘管理工具需要格式化卷时指定分配单元大小大于 4096 个字节 (4 KB)。 Windows 资源管理器只能将最多此阈值设置格式。 CHKDSK 命令可以用于确认卷的当前分配单元大小，但需要扫描整个卷之前所需的信息将显示 （显示为字节每个分配单元中）。  
  
### <a name="monitor-drive-space-utilization"></a>监视驱动器空间利用率  
 磁盘上的更少数据，得越快它将进行操作。 这是因为很好地碎片驱动器上的数据将写入接近的外边缘的尽可能磁盘因为这是其中的磁盘的速度最快旋转并实现最佳性能。  
  
 磁盘寻道时间通常显著超过读取或写入活动。 如上所述，数据最初是写入外边缘的磁盘。 因为减少了对磁盘存储增加和可用空间的要求，更接近将数据写入磁盘的中心。 磁盘查找增大的定位数据作为头移动离开边缘，并且在发现时间，它将需要更长时间才能读取，影响磁盘 I/O 性能。  
  
 这意味着，监视磁盘空间利用率非常重要不只是出于容量原因而是为了性能还。  
  
 根据经验，逐步目标是保持磁盘可用空间之间 20%到 25%的总磁盘空间。 如果可用磁盘空间下降到低于此阈值，则磁盘输入/输出性能将受到负面影响。  
  
### <a name="implement-a-strategy-to-avoid-disk-fragmentation"></a>实现策略以避免磁盘碎片整理  
 你在磁盘上，包括根驱动器，以防止性能下降定期运行的碎片整理程序实用。 执行此每周忙磁盘上。 磁盘碎片整理程序随 Windows Server 安装，并可以从一项计划任务按照指定间隔运行。  
  
### <a name="optimize-windows-server-performance-for-background-services"></a>优化后台服务的 Windows Server 性能  
 BizTalk Server 过程 (BTSNTSVC.exe) 作为后台服务运行。 默认情况下，[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]配置为调整为获得最佳性能的应用程序而不是针对后台服务。  
  
 [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]使用抢先式多任务来确定将受 CPU 就读到的进程线程的优先级。 Preemptive 多任务是凭此进程的执行将暂停，启动另一个进程时，操作系统自行一个方法。 此方案可防止单个线程占据 CPU。  
  
 切换到下一个进程内执行从 CPU 被称为上下文切换。 Windows 操作系统的系统包括确定多长时间允许各个线程之前上下文切换时，处理下一个线程在 CPU 上运行的设置。 此时间量称为量程。 此设置允许你选择处理器量程前台程序和后台服务之间共享的方式。 通常为服务器不需要允许前台程序具有比后台服务分配给它的更多 CPU 时间。 也就是说，所有应用程序，它们在服务器上运行的进程，应考虑相等 CPU 时间。  
  
 若要增加为等 BizTalk 主机实例的后台服务的性能，请按照下列步骤：  
  
1.  单击**启动**，单击**控制面板**，然后单击**系统**。  
  
2.  单击**高级**选项卡上，并依次**设置**下**性能**。  
  
3.  单击**高级**选项卡上，单击**后台服务**，然后单击**确定**两次。  
  
### <a name="manually-load-microsoft-certificate-revocation-lists"></a>手动加载 Microsoft 证书吊销列表  
 在开始时的.NET 应用程序，.NET Framework 将尝试下载的证书吊销列表 (CRL) 的任何签名的程序集。 如果你的系统没有直接访问 Internet，或者被限制访问 Microsoft.com 域，这可能会延迟启动 BizTalk Server。 若要避免在应用程序启动此延迟，可以使用以下步骤手动下载并安装代码签名你的系统上的证书吊销列表。  
  
1.  下载中的最新 CRL 更新[http://crl.microsoft.com/pki/crl/products/CodeSignPCA.crl](http://go.microsoft.com/fwlink/?LinkID=117794)和[http://crl.microsoft.com/pki/crl/products/CodeSignPCA2.crl](http://go.microsoft.com/fwlink/?LinkId=117795)。  
  
2.  将的 CodeSignPCA.crl 和 CodeSignPCA2.crl 文件移到独立的系统。  
  
3.  从命令提示符处，输入以下命令以使用 certutil 实用程序来使用 CRL 在步骤 1 中下载更新的本地证书存储区：  
  
     certutil – addstore CA c:\CodeSignPCA.crl  
  
 CRL 文件将定期更新，因此您应该考虑设置的重复任务的下载和安装 CRL 更新。 若要查看的下一步的更新时间、 双击.crl 文件并查看的值**下一步更新**字段。  
  
### <a name="synchronize-time-on-all-servers"></a>将所有服务器上的时间同步  
 许多操作涉及票证，回执和日志记录依赖于正在准确的本地系统时钟。 这是在分布式环境中，其中系统之间的时间差异可能会导致日志要同步的或由一个系统被拒绝由另一个为过期颁发票证尤其如此或尚未生效。  
  
 服务器配置为自动同步时间的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=99420](http://go.microsoft.com/fwlink/?LinkId=99420)。  
  
### <a name="configure-the-windows-pagefile-for-optimal-performance"></a>配置 Windows 页面文件以获得最佳性能  
 为了获得最佳性能，请遵循以下准则来配置 Windows 页面文件 （分页文件）：  
  
1.  **将分页文件移动到不同的操作系统安装以减少磁盘争用和提高磁盘性能的物理驱动器物理卷**-BizTalk Server 在计算机上，与移动相关的性能提升分页文件的文档处理负载而异。 在 SQL Server 计算机上将页面文件移动到单独的卷被视为由于 SQL Server 的磁盘密集型特性的所有方案中的最佳做法。  
  
2.  **隔离到一个或多个专用物理驱动器配置为 RAID 0 （条带化） 或 raid-1 （镜像） 的数组，或在没有 RAID 的单个磁盘上分页文件**-通过使用专用的磁盘或驱动器数组其中页面文件。SYS 是整个卷上唯一的文件、 分页文件将不会变得零碎，因而也提高了性能。 与大多数磁盘的数组，数组的性能得到改进由于数组中的物理磁盘数已增加。 如果分页文件中的磁盘阵列的多个物理驱动器上的多个卷之间分布，分页文件大小应为数组中每个驱动器上相同的大小。 在配置磁盘阵列，也建议使用具有相同的容量和速度的物理驱动器。 请注意冗余不通常需要分页文件。  
  
3.  **未配置 RAID 5 阵列上的分页文件**-建议不要在 RAID 5 阵列上分页文件的配置，因为分页文件活动编写需要进行大量和 RAID 5 数组更好地适用于读取性能不是写入性能。  
  
4.  **如果你没有资源来将分页文件移动到物理卷中，而不是操作系统安装上，配置要作为操作系统相同的逻辑卷上驻留的分页文件**-配置可驻留在分页文件这将在同一个物理磁盘上，因为操作系统将增加磁盘的另一个逻辑卷查找时间和降低系统性能，因为磁盘驱动器盘磁头将不断卷，或者访问页面文件之间移动操作系统文件、 应用程序文件和数据文件。 此外，通常是通常与最近外边缘的物理磁盘的物理磁盘的第一个分区上安装操作系统以及其中磁盘速度是，关联性能最适合的磁盘。  
  
    > [!IMPORTANT]  
    >  如果你删除分页文件从启动分区，Windows 无法创建故障转储文件 （内存。DMP) 在其中写入调试信息的事件中内核模式下停止发生错误。 如果你需要故障转储文件，则您将别无选择但若要将保留至少的页面文件大小的物理内存 + 1 MB 上启动分区。  
  
5.  **手动设置页面文件的大小**– 手动设置页面文件的大小通常提供更好的性能比允许自动调整大小的服务器或根本没有分页文件。 优化最佳做法是设置的初始 （最低配置） 和分页文件的最大大小设置为相同的值。 这可不确保任何处理资源丢失页面文件，可能是密集型操作的动态调整大小。 假设已变得约束系统上的内存资源时，通常会发生此大小调整的活动，也是如此。 设置相同的最小和最大页面文件大小值还可以在磁盘上的分页区域是一个单独的、 临近区域中，确保提高磁盘查找时间。