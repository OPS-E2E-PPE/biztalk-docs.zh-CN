---
title: "清单： 配置 Windows Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ebd7ea95-cc73-4c98-a796-193f394fb5b8
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bffa095c4ed5834f93b3a8634915214ac7b9530
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-configuring-windows-server"></a>清单： 配置 Windows Server
本主题列出在生产中使用准备 Windows Server 时应遵循的步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  
  
##  <a name="BKMK_Win2k8"></a>配置 Windows Server  
  
|步骤|参考|  
|-----------|---------------|  
|配置为 MSDTC [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。|-请参阅[如何启用 BizTalk 服务器上的 MSDTC](http://go.microsoft.com/fwlink/?LinkId=153236) (http://go.microsoft.com/fwlink/?LinkId=153236)。<br />-请参阅[疑难 MSDTC](http://go.microsoft.com/fwlink/?LinkId=153237) (http://go.microsoft.com/fwlink/?LinkId=153237)。|  
|配置防火墙的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 **注意：**此步骤才是必需的一个或多个防火墙如果都在位置中你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。|-请参阅[BizTalk 服务器所需端口](http://go.microsoft.com/fwlink/?LinkId=153238)(http://go.microsoft.com/fwlink/?LinkId=153238)。<br />-请参阅 Microsoft 知识库文章 154596， ["如何配置与防火墙一起使用的 RPC 动态端口分配"](http://go.microsoft.com/fwlink/?LinkId=153239) (http://go.microsoft.com/fwlink/?LinkId=153239)。|  
|请关闭所有运行的计算机上的超线程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。|-它是关键对于运行的计算机关闭该超线程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 这是通常在 BIOS 设置的处理器设置中找到的 BIOS 设置。 超线程使服务器会显示为具有更多处理器/处理器内核不是它的实际作用;但是，超线程处理器通常介于 20%和 30%的物理处理器核心的性能之间提供。 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计数以调整其自我调整算法，超线程处理器的处理器数会导致这些调整倾斜，这是对总体性能造成不利影响。<br />的应为关闭超线程[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机因为可能会导致大量争用的应用程序 (如[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]) 可能会致使超线程环境中的性能降低[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。|  
|确保 Windows Server 处理器计划设置为"后台服务"。|确保在你的环境中运行 Windows Server 的所有计算机上设置此配置选项将提高总体系统性能。 请按照以下步骤来确保 Windows Server 配置为倾向于后台服务操作：<br /><br /> 1.单击**启动**，单击**运行**，然后键入**sysdm.cpl**中**运行**框。<br />2.在**系统属性**对话框中，单击**高级**选项卡上，并依次**设置**下**性能**。<br />3.在**性能选项**对话框中，单击**高级**选项卡上，请确保**后台服务**下选项被选中**处理器计划**，单击**确定**，然后单击**确定**以关闭**系统属性**对话框。|  
|Windows 分页文件放置在单独的本地物理驱动器。|将分页文件移动到非操作系统的单独物理卷运行 Windows Server 的计算机上减少磁盘争用，从而提高了性能。<br /><br /> 请按照下列步骤将分页文件移动到非操作系统的单独物理卷：<br /><br /> 1.单击**启动**，单击**运行**，然后键入**sysdm.cpl**中**打开**框。<br />2.单击**高级**选项卡上，并依次**设置**下**性能**。<br />3.单击**高级**选项卡上，单击**更改**下**虚拟内存**、 指定分页文件的选项，请单击**确定**，然后单击**确定**以关闭系统属性。 **注意：**必须重新启动计算机，使新设置才会生效。|  
|磁盘碎片整理所有磁盘 (本地和 SAN/NAS) 定期通过计划非高峰时段磁盘碎片整理。<br />磁盘碎片整理 Windows 分页文件和预分配主文件表中每个磁盘的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境以提升总体系统性能。|使用[PageDefrag 实用工具](http://go.microsoft.com/fwlink/?LinkId=108976)(http://go.microsoft.com/fwlink/?LinkId=108976) 要整理 Windows 分页文件和预分配主文件表。|  
|如果运行的计算机上安装防病毒软件[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，禁用的数据和事务的文件 （.mdf、.ndf、.ldf、.mdb） 的实时扫描。|实时扫描[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据和事务文件可增加磁盘 I/O 争用并减少[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]性能。|  
|如果运行的计算机上安装防病毒软件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，禁用任何引用的非可执行文件类型的实时扫描[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置 （通常。XML，但也可以是.csv、.txt，等等。)。|引用的非可执行文件的实时扫描[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置可以提高在这些文件的 I/O 争用并减小[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能。|  
|如果安装入侵检测软件，则禁用扫描运行的计算机之间的网络[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和外部数据存储库 ([!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]) 或消息传送服务 （如消息队列和 WebSphere MQSeries）。|入侵检测软件可以慢，或者甚至阻止通过网络的有效的通信。|  
|网络中的所有计算机上的卡 (NIC) 驱动程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境应针对性能优化。|调整网络设备驱动程序，以最大化传入和传出数据包缓冲，可用的内存量。 也最大化缓冲区计数，尤其是传输缓冲区和合并缓冲区。 默认值为这些参数，并是否即使提供，制造商和驱动程序版本之间的不同。 目标是以最大化网络接口卡硬件，通过完成的工作并允许网络操作，以减少网络流量高峰和关联的拥塞的最大可能会发生缓冲区空间。|  
|设置为固定的速度和双工的网络卡|使用固定的速度和双工 (1 千兆或更高版本与完整的双工) BizTalk 和 SQL 服务器上的网络连接。 这将确保，网络接口不自动协商的较低速度或双工设置，有些企业交换机问题已在过去。 此外，在大容量环境中，则最好具有千兆位网络。|  
|停止或禁用任何不是绝对必需 （如打印后台处理程序和索引服务） 的 Windows 服务中的所有计算机上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。|在生产服务器上运行不必要的服务使用系统资源，否则无法由使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。|  
  
## <a name="in-this-section"></a>本节内容  
  
-   [安装 COM + 修补程序汇总包](../technical-guides/installing-com-hotfix-rollup-packages.md)  
  
## <a name="see-also"></a>另请参阅  
 [操作清单](../technical-guides/operations-checklists.md)