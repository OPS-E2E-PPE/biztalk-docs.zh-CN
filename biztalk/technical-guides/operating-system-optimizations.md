---
title: 操作系统优化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af2e77d0-d69b-4ae4-b689-96831fc4deed
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93222268e3d59bccfe8222e0e0e9b276e21f3dfd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242641"
---
# <a name="operating-system-optimizations"></a>操作系统优化
本主题提供有关优化性能的建议[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在生产中使用计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。 这些优化应用后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]已安装并配置。  
  
## <a name="general-guidelines-for-improving-operating-system-performance"></a>优化操作系统性能的常规指南  
 以下建议可用于提高操作系统性能：  
  
### <a name="install-the-latest-bios-storage-area-network-san-drivers-network-adapter-firmware-and-network-adapter-drivers"></a>安装最新的 BIOS、 存储区域网络 (SAN) 驱动程序、 网络适配器的固件和网络适配器驱动程序  
 硬件制造商会定期发布可以提高性能和可用性相关联的硬件的 BIOS、 固件和驱动程序更新。 请访问硬件制造商的网站来下载并应用 BizTalk Server 环境中的每台计算机上的以下硬件组件的更新：  
  
1.  BIOS 更新  
  
2.  SAN 驱动程序 （如果使用 SAN）  
  
3.  NIC 固件  
  
4.  NIC 驱动程序  
  
### <a name="assign-the-msdtc-log-file-directory-to-a-separate-dedicated-drive"></a>将 MSDTC 日志文件目录分配到单独的专用驱动器  
 在 BizTalk Server 环境使用不同的 SQL Server 计算机上的多个 MessageBox 数据库中，产生关联与 Microsoft 分布式事务处理协调器 (MSDTC) 的额外开销。 默认情况下，MSDTC 日志文件位于运行 DTC 服务的计算机的 %systemdrive%\windows\system32\msdtc 目录中。 若要降低 DTC 日志记录可能成为性能瓶颈的可能性，请考虑将 MSDTC 日志文件目录移到快速的磁盘驱动器。 若要更改 MSDTC 日志文件目录，请执行以下步骤：  
  
1.  单击**启动**，单击**运行**，然后键入**dcomcnfg**以启动**组件服务**管理控制台。  
  
2.  展开**组件服务**，展开**计算机**，右键单击**我的电脑**，然后单击**属性**。  
  
3.  在中**我的电脑属性**对话框中，单击**MSDTC**选项卡。  
  
4.  在中**位置**编辑框下的**日志信息**，键入要用 （例如 G:\Logs\DTCLog） 创建新日志的路径。  
  
5.  单击**重置日志**，并且系统将提示您为服务重新启动。 单击**确定**以重新启动 DTC 服务，然后单击**确定**以确认已重新启动 MSDTC 服务。  
  
### <a name="configure-antivirus-software-to-avoid-real-time-scanning-of-biztalk-server-executables-and-file-drops"></a>若要避免的 BizTalk Server 可执行文件的实时扫描的防病毒软件配置和丢失的文件  
 防病毒软件实时扫描的 BizTalk Server 可执行文件和任何文件夹或文件共享监视 BizTalk server 接收位置对 BizTalk Server 性能产生负面影响。 如果在 BizTalk Server 计算机上安装防病毒软件，则禁用实时扫描的非可执行文件的文件类型引用的任何 BizTalk Server 接收位置 （通常。XML，但也可以是.csv、.txt 等。)和配置 BizTalk Server 可执行文件的扫描中排除的防病毒软件  
  
### <a name="disable-intrusion-detection-network-scanning-between-computers-in-the-biztalk-server-environment"></a>禁用扫描在 BizTalk Server 环境中的计算机之间的入侵检测网络  
 入侵检测软件可以慢，或者甚至通过网络防止有效的通信。 如果安装入侵检测软件，则禁用网络扫描 BizTalk Server 计算机和外部数据存储库 (SQL Server) 计算机之间或消息传送服务 （消息队列、 WebSphere MQSeries 等） 的计算机。  
  
### <a name="defragment-all-disks-in-the-biztalk-server-environment-on-a-regular-basis"></a>对定期在 BizTalk Server 环境中的所有磁盘进行碎片都整理  
 在 BizTalk Server 环境中的过多的磁盘碎片会对性能产生负面影响。 请按照下列步骤进行碎片整理 BizTalk Server 环境中的磁盘：  
  
1.  对所有磁盘进行碎片都整理 (本地和 SAN/NAS) 定期通过计划非工作时间磁盘碎片整理。  
  
2.  对 Windows 页面文件进行碎片整理和预分配在 BizTalk Server 环境中每个磁盘的主文件表，以提升总体系统性能。  
  
    > [!NOTE]  
    >  使用 PageDefrag 实用程序可在[ http://go.microsoft.com/fwlink/?LinkId=108976 ](http://go.microsoft.com/fwlink/?LinkId=108976)进行碎片整理 Windows 页面文件和预分配主文件表。  
  
### <a name="if-antivirus-software-is-installed-on-the-sql-server-computers-disable-real-time-scanning-of-data-and-transaction-files"></a>如果在 SQL Server 计算机上安装防病毒软件，则禁用实时扫描的数据和事务文件  
 SQL Server 数据和事务文件 （.mdf、.ndf、.ldf、.mdb） 的实时扫描可以提高磁盘 I/O 争用，并减少 SQL Server 的性能。 请注意，BizTalk Server 环境之间的 SQL Server 数据和事务文件的名称可能会有所不同。 有关使用默认 BizTalk Server 配置创建的数据和事务的详细信息，请参阅[优化文件组的数据库](http://msdn.microsoft.com/library/ee377060\(v=bts.70\).aspx)。  
  
### <a name="configure-msdtc-for-biztalk-server"></a>为 BizTalk Server 配置 MSDTC  
 查看要为 BizTalk Server 配置 MSDTC 的以下信息：  
  
-   若要在 BizTalk Server 上配置 MSDTC，请参阅"启用 DTC 在本地主机服务器上"部分中的 BizTalk Server 2010 安装指南[ http://go.microsoft.com/fwlink/?LinkID=191321 ](http://go.microsoft.com/fwlink/?LinkID=191321)。  
  
-   "解决 MSDTC 问题的"，网址[ http://go.microsoft.com/fwlink/?LinkID=202142 ](http://go.microsoft.com/fwlink/?LinkID=202142)。  
  
### <a name="configure-firewalls-for-biztalk-server"></a>为 BizTalk Server 配置防火墙  
  
> [!NOTE]  
>  此步骤才是必需的如果一个或多个防火墙，则在 BizTalk Server 环境中的位置。  
  
 请查看以下信息为 BizTalk Server 配置防火墙：  
  
-   "必需的端口为 BizTalk Server"处[ http://go.microsoft.com/fwlink/?LinkId=101607 ](http://go.microsoft.com/fwlink/?LinkId=101607)。  
  
-   "如何配置 RPC 动态端口分配，以使用防火墙"在[ http://go.microsoft.com/fwlink/?LinkID=76145 ](http://go.microsoft.com/fwlink/?LinkID=76145)。  
  
### <a name="use-the-ntfs-file-system-on-all-volumes"></a>使用 NTFS 文件系统上的所有卷  
 [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 提供用于格式化驱动器，包括 NTFS、 FAT 和 FAT32 的多个文件系统类型。 NTFS 应始终为所选的服务器的文件系统。[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]  
  
 NTFS FAT 和 FAT32 文件系统相比，提供很大的性能优势，因此应以独占方式在 Windows 服务器上。 此外，NTFS 提供针对许多安全性、 可伸缩性、 稳定性和可恢复性优势 FAT 和 FAT32。  
  
 在以前版本的 Windows，FAT 和 FAT32 通常上实现较小的卷 (例如 < 500 MB) 因为它们通常在这种情况下更快。 磁盘存储价格相对便宜今天和操作系统和应用程序推送到最多的驱动器的容量，不太可能此类小的卷，将使用。 FAT32 伸缩性比 FAT 更好，更大的卷上，但仍不适当的文件系统的 Windows 服务器。  
  
 FAT 和 FAT32 通常已实现过去它们是为更轻松地可恢复和可使用本机 DOS 工具出现问题与使用的卷时所示。 目前，各种 NTFS 可恢复性与生成的工具，同时以本机模式到操作系统，并可用作第三方实用程序可用，应不再有未使用 NTFS 文件系统的有效参数。  
  
### <a name="do-not-use-ntfs-file-compression"></a>不使用 NTFS 文件压缩  
 虽然使用 NTFS 文件系统压缩是减少空间卷上的简单方法，但它不是适用于企业的文件服务器。 实现压缩磁盘的所有操作在 CPU 上会不必要的开销，最好避免使用。 考虑添加更多的磁盘的选项、 近线存储或将数据存档在认真考虑文件系统压缩之前，请考虑。  
  
### <a name="review-disk-controller-stripe-size-and-volume-allocation-units"></a>查看磁盘控制器条带大小和卷分配单元。  
 时配置驱动器阵列和逻辑驱动器中硬件驱动器控制器，请确保您与匹配与将使用格式化卷的分配单元大小控制器条带大小。 这将确保磁盘读取和写入已获得最佳性能，并提供更好的总体服务器性能。  
  
 配置更大的分配单元 （或群集或块） 大小会导致磁盘空间来使用效率较低，但还会提供更高版本磁盘 I/O 性能，因为磁盘头期间读取的每个活动可以读取更多数据。  
  
 若要确定的最佳设置： 若要配置控制器和使用的磁盘进行格式化，应确定具有类似的文件系统特征的服务器的磁盘子系统上的磁盘的平均传输大小。 使用[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]性能监视器工具来监视平均的逻辑磁盘对象计数器Disk Bytes/Read 和 avg.磁盘字节数/写入的正常活动的期间内以帮助确定要使用的最佳值。  
  
 尽管较小的分配单元大小可能合理许多小文件或记录，如果将访问系统，为 64 KB 分配单元大小提供声音性能和大多数情况下的 I/O 吞吐量。 中的优化的分配单元大小与性能的改进可以特别注意的是磁盘负载增加时。  
  
> [!NOTE]  
>  格式命令行工具或磁盘管理工具需要格式化卷时，指定分配单元大小大于 4096 个字节 (4 KB)。 Windows 资源管理器将仅由此阈值设置格式。 CHKDSK 命令可以用于确认卷的当前分配单元大小，但是它需要扫描整个卷之前 （以字节显示在每个分配单元中） 显示的所需的信息。  
  
### <a name="monitor-drive-space-utilization"></a>监视驱动器空间利用率  
 更少数据磁盘上的，更快地运行。 这是磁盘的因为也经过碎片整理的驱动器上数据将写入的外边缘尽可能接近由于这是磁盘的磁盘位置旋转的速度最快和实现最佳性能。  
  
 磁盘寻道时间是通常相当长的时间比读取或写入活动。 如上文所述，数据最初是写入磁盘的外边缘。 当对磁盘存储的提高和可用空间的需求减少时，更接近将数据写入磁盘的中心。 磁盘寻道时间增加的头移动数量从边缘，作为查找数据和找到时，所花费的时间阅读，妨碍磁盘 I/O 性能。  
  
 这意味着，监视磁盘空间利用率很重要不只是出于容量原因，但性能还。  
  
 根据经验，工作完成保持磁盘可用空间介于 20%到 25%的总磁盘空间的一个目标。 如果可用磁盘空间下降到低于此阈值，则磁盘 I/O 性能将受到负面影响。  
  
### <a name="implement-a-strategy-to-avoid-disk-fragmentation"></a>实施策略，以避免磁盘碎片  
 在你的磁盘，包括根驱动器，用于防止性能下降上定期运行碎片整理程序实用工具。 执行此每周在繁忙的磁盘上。 磁盘碎片整理程序随 Windows Server 安装，并可以从计划任务在指定的时间间隔运行。  
  
### <a name="optimize-windows-server-performance-for-background-services"></a>优化后台服务的 Windows Server 的性能  
 BizTalk Server 进程 (BTSNTSVC.exe) 作为后台服务运行。 默认情况下，[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]配置为调整为获得最佳性能的应用程序的程序而不是针对后台服务。  
  
 [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 使用抢先式多任务来确定将为参加由 CPU 的进程线程的优先级。 抢先式多任务处理是一种方法来暂停进程的执行和启动另一个进程时，操作系统的决定。 此方案可防止单个线程在支配 CPU。  
  
 切换到下一个进程内执行从 CPU 被称为上下文切换。 Windows 操作系统包括确定多长时间允许各个线程发生上下文切换和下一个线程已得到处理之前，在 CPU 上运行的设置。 此时间量称为量程。 此设置允许您选择处理器量程前台程序和后台服务之间的共享方式。 通常为服务器不需要以允许前台程序具有比后台服务分配给它的更多 CPU 时间。 也就是说，所有应用程序和其在服务器上运行的进程应考虑相等的 CPU 时间。  
  
 若要增加为 BizTalk 主机实例等的后台服务的性能，请执行以下步骤：  
  
1.  单击**启动**，单击**控制面板**，然后单击**系统**。  
  
2.  单击**高级**选项卡，然后依次**设置**下**性能**。  
  
3.  单击**高级**选项卡上，单击**后台服务**，然后单击**确定**两次。  
  
### <a name="manually-load-microsoft-certificate-revocation-lists"></a>手动加载 Microsoft 证书吊销列表  
 在启动时的.NET 应用程序，.NET Framework 将尝试下载的证书吊销列表 (CRL) 适用于任何已签名的程序集。 如果您的系统不具有直接访问 Internet，或受限制而无法访问 Microsoft.com 域，这可能会延迟启动 BizTalk Server。 若要避免这种延迟在应用程序启动时，可以使用以下步骤来手动下载并安装在系统上签名证书吊销列表的代码。  
  
1. 下载最新的 CRL 更新从[ http://crl.microsoft.com/pki/crl/products/CodeSignPCA.crl ](http://go.microsoft.com/fwlink/?LinkID=117794)并[ http://crl.microsoft.com/pki/crl/products/CodeSignPCA2.crl ](http://go.microsoft.com/fwlink/?LinkId=117795)。  
  
2. 将 CodeSignPCA.crl 和 CodeSignPCA2.crl 文件移动到独立的系统。  
  
3. 从命令提示符下输入以下命令以使用 certutil 实用程序以使用在步骤 1 中下载 CRL 更新本地证书存储区：  
  
    certutil –addstore CA c:\CodeSignPCA.crl  
  
   CRL 文件将定期更新，因此您应该考虑设置重复的任务的下载和安装 CRL 更新。 若要查看下一步的更新时间，双击.crl 文件以及查看的值**下一步更新**字段。  
  
### <a name="synchronize-time-on-all-servers"></a>同步所有服务器上的时间  
 涉及票证的许多操作，回执和日志记录将被准确的本地系统时钟。 这是在分布式环境中，系统之间的时间差异可能导致的日志，以同步的或由为已过期拒绝的另一个系统颁发票证尤其如此或尚未生效。  
  
 服务器配置为自动同步时间的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=99420 ](http://go.microsoft.com/fwlink/?LinkId=99420)。  
  
### <a name="configure-the-windows-pagefile-for-optimal-performance"></a>配置 Windows 页面文件以获得最佳性能  
 为了获得最佳性能，请遵循以下准则来配置 Windows 页面文件 （分页文件）：  
  
1.  **将页面文件移到独立于操作系统安装以减少磁盘争用并提高磁盘性能的物理驱动器的物理卷**-BizTalk Server 在计算机上，与移动相关的性能提升分页文件的文档处理负载而异。 SQL Server 计算机上将页面文件移动到一个单独的卷被认为在所有方案中由于磁盘密集型特性的 SQL Server 最佳实践。  
  
2.  **隔离一个或多个专用物理驱动器上配置为 RAID 0 （带区） 或 RAID 1 （镜像） 数组，或在没有 RAID 的单个磁盘上分页文件**-通过使用专用的磁盘或驱动器阵列的页面文件。SYS 是整个卷上唯一的文件、 分页文件不会变成碎片，这还可以提高性能。 与大多数磁盘的阵列，该数组的性能得到改进由于数组中的物理磁盘的数量已增加。 如果页面文件磁盘阵列中的多个物理驱动器上的多个卷之间分布，分页文件大小应为数组中每个驱动器上的相同大小。 在配置磁盘阵列，它也被建议使用具有相同的容量和速度的物理驱动器。 请注意冗余不是通常所需的分页文件。  
  
3.  **未配置 RAID 5 阵列上的分页文件**-不建议在 RAID 5 阵列上分页文件的配置，因为分页文件活动写入密集型和 RAID 5 阵列更好地适合于读取性能不是写入性能。  
  
4.  **如果还没有资源，以将页面文件移动到物理卷，而不在安装操作系统，配置要与操作系统相同的逻辑卷上驻留的分页文件**-配置页面文件，使其位于另一个逻辑卷位于同一物理磁盘，因为操作系统将增加磁盘寻道时间并降低系统性能，因为磁盘驱动器的盘片磁头将不断移动之间的卷，或者访问的页面文件操作系统文件、 应用程序文件和数据文件。 此外，通常最接近于物理磁盘的外边缘的物理磁盘的第一个分区通常安装操作系统，其中磁盘速度是，关联的性能最适合于该磁盘。  
  
    > [!IMPORTANT]  
    >  如果你从启动分区删除分页文件，Windows 无法创建崩溃转储文件 （的内存。DMP) 用来在的内核模式下停止写入调试信息时发生错误。 如果你需要的崩溃转储文件，则您将别无选择，只能离开至少为页面文件大小的物理内存 + 1 MB 的引导分区上。  
  
5.  **手动设置的页面文件大小**– 手动设置分页文件的大小通常提供更好的性能比这样，服务器可以自动调整大小或根本无分页文件。 优化最佳做法是设置初始 （最低配置） 和页面文件的最大大小设置为相同的值。 这可确保没有处理资源丢失到分页文件，可能是操作的动态调整大小。 考虑到此大小调整活动通常发生在系统上的内存资源成为约束时，也是如此。 设置相同的最小值和最大页面文件大小值还可在磁盘上的分页区域是一个单一的连续未分配区域中，确保提高磁盘寻道时间。