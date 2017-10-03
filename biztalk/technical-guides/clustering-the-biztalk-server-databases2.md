---
title: "群集 BizTalk Server Databases2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b68bc3f-c0c4-4050-8ca3-df6dd1927637
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c84f8f6ef26c567a1bbac44df078f2df58ca9da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="clustering-the-biztalk-server-databases"></a>群集的 BizTalk Server 数据库
如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库不可用，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境将无法正常运行。 若要提供高可用性，你可以创建的 Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]适用于群集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，如下图中所示。  
  
 ![BizTalk Server 数据库层](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 若要创建高度可用的解决方案，以便[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，你必须具有至少两台计算机运行[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]和群集上的共享的磁盘阵列。  
  
## <a name="clustering-options"></a>聚类分析选项  
 确定最佳的群集配置为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来满足业务需求的数据库。 下面是选项的列表：  
  
-   **主动/被动**。 高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库通常包含在主动/被动服务器群集配置中配置的两个或多个数据库计算机。 这些计算机共享公共的磁盘资源 (如 RAID 1 + 0 SCSI 磁盘阵列或存储区域网络) 和使用 Windows 群集提供备份的冗余和容错能力。  
  
-   **主动/主动**。 Windows 群集和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]让你运行[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]在主动/主动模式下的群集的每个节点都是"活动"并正在运行一个或多个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。 例如，这将使你能够上一个节点和所有其他的 MessageBox 数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]另一个节点上的数据库。 这样您就可以最大化群集硬件使用率，但主动/主动[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]配置应谨慎使用。  
  
     可以每个节点同时处理的负载的所有[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例期间[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集节点故障转移方案？ 是否有足够的 CPU 资源？ 是否有足够的内存？ 有关网络带宽的新增功能？ 如何为磁盘 I/O 争用？  
  
     这些是需要以确定如果主动/主动回答的问题的一些[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集最适合你的 BizTalk 应用程序。 如果确定，一个节点不能处理所有[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例故障转移方案中的，一种替代方法是使用主动/主动/被动群集。  
  
-   **主动/主动/被动**。 运行时进程写入到 BizTalk 管理数据库、 MessageBox 数据库、 跟踪 Analysis Services 数据库、 BAM 分析数据库、 BAM 星型架构数据库、 BAM 主导入数据库和 BAM 存档数据库。 因此，这些数据库是特别重要，如果灾难发生，并且确定群集的数据库时，必须具有更高的优先级。 仅用户或工具写入其他数据库。 对于 MessageBox 数据库中，你可以考虑具有主动/主动/被动或主动/主动/主动/被动配置，以便最大程度减少所需的硬件。  
  
> [!NOTE]  
>  [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]和[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]Standard Edition 支持 2 节点故障转移群集。 如果你决定使用上的主动/主动/被动配置[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]或[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]，您必须使用的企业版[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。  
  
## <a name="procedures-for-clustering-the-databases"></a>群集数据库的过程  
 请确保在开始群集之前满足以下先决条件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。  
  
-   当你创建的域组你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，你必须创建全局域帐户。  
  
-   配置[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集安装和配置之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 有关群集的详细信息[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]，请参阅[Getting Started with SQL Server 2008 R2 故障转移群集](http://go.microsoft.com/fwlink/?LinkId=156820)(http://go.microsoft.com/fwlink/?LinkId=156820)。  
  
-   如果你要创建群集的主密钥服务器，请首先配置该服务器。 为企业单一登录高可用性的详细信息，请参阅[主密钥服务器的高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)。  
  
#### <a name="to-run-the-biztalk-server-configuration-wizard"></a>运行 BizTalk Server 配置向导  
  
1.  在运行时服务器上安装 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]。  
  
2.  启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置程序。 单击**启动**，指向**程序**，指向**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** ，然后单击**BizTalk Server 配置**。  
  
3.  若要应用自定义配置，请按照本文[使用自定义配置管理器](http://go.microsoft.com/fwlink/?LinkId=156822)(http://go.microsoft.com/fwlink/?LinkId=156822) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。 若要为 BizTalk Server 数据库输入中的 SQL Server 群集的名称指定 SQL Server 群集**数据库**配置的对话框。  
  
4.  完成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]按照中的说明配置[自定义配置](http://go.microsoft.com/fwlink/?LinkId=156823)(http://go.microsoft.com/fwlink/?LinkId=156823) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
 有关群集的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，请参阅[通过使用 Windows Server 2008 故障转移群集或 Windows Server 2003 服务器群集的 BizTalk Server 中改进容错功能](http://go.microsoft.com/fwlink/?LinkId=156819)(http://go.microsoft.com/fwlink/?LinkId=156819)。  
  
## <a name="behavior-of-biztalk-host-instances-during-sql-server-failover"></a>在 SQL Server 故障转移期间的 BizTalk 主机实例的行为  
 有关详细信息行为 BizTalk 主机实例的 SQL Server 故障转移期间，请参阅[行为的 BizTalk Server 主机实例在 SQL Server 故障转移期间](http://go.microsoft.com/fwlink/?LinkId=151287)(http://go.microsoft.com/fwlink/?LinkId=151287)。  
  
## <a name="using-sql-server-database-mirroring"></a>使用 SQL Server 数据库镜像  
 有关使用 SQL Server 数据库镜像与 BizTalk Server 数据库群集的详细信息，请参阅[使用的 SQL Server 数据库镜像或卷影复制服务](http://go.microsoft.com/fwlink/?LinkId=151288)(http://go.microsoft.com/fwlink/?LinkId = 151288) 在 BizTalk Server 帮助中。  
  
## <a name="see-also"></a>另请参阅  
 [向外扩展 BizTalk Server Database](../technical-guides/scaling-out-the-biztalk-server-databases.md)