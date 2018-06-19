---
title: 创建数据库群集 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b68bc3f-c0c4-4050-8ca3-df6dd1927637
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e978c66f903049e566c25f9baf727b6621cbbf2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009470"
---
# <a name="clustering-the-biztalk-server-databases"></a>群集的 BizTalk Server 数据库
如果 BizTalk Server 数据库变得不可用，BizTalk Server 环境将无法正常运行。 若要提供高可用性，可以创建 BizTalk Server 数据库中，Microsoft SQL Server 群集下, 图中所示。  
  
 ![BizTalk Server 数据库层](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 若要创建用于 BizTalk Server 数据库的高可用性解决方案，你必须在群集中运行 SQL Server 和共享的磁盘阵列的至少两台计算机。  
  
## <a name="clustering-options"></a>聚类分析选项  
 确定你的业务需求的 BizTalk Server 数据库的最佳群集配置。 下面是选项的列表：  
  
-   **主动/被动**。 BizTalk Server 数据库的高可用性通常由在主动/被动服务器群集配置中配置的两个或多个数据库计算机组成。 这些计算机共享公共的磁盘资源 (如 RAID 1 + 0 SCSI 磁盘阵列或存储区域网络) 和使用 Windows 群集提供备份的冗余和容错能力。  
  
-   **主动/主动**。 Windows 群集和 SQL Server，可以在主动/主动模式下运行 SQL Server 的群集的每个节点都是"活动"和正在运行一个或多个 SQL Server 实例。 例如，这将允许你在上一个节点和所有其他 BizTalk Server 数据库的 MessageBox 数据库上另一个节点。 这样您就可以最大化群集的硬件使用情况，但应谨慎使用主动/主动 SQL Server 配置。  
  
     可以每个节点同时处理的负载的所有 SQL Server 实例的 SQL Server 群集节点故障转移方案期间？ 是否有足够的 CPU 资源？ 是否有足够的内存？ 有关网络带宽的新增功能？ 如何为磁盘 I/O 争用？  
  
     这些是仅有一些需要回答的精选以便确定主动/被动 SQL Server 群集是否适合你的 BizTalk 应用程序的问题。 如果确定，一个节点不能处理在故障转移方案中的所有 SQL Server 实例，一种替代方法是使用主动/主动/被动群集。  
  
-   **主动/主动/被动**。 运行时进程写入到 BizTalk 管理数据库、 MessageBox 数据库、 跟踪 Analysis Services 数据库、 BAM 分析数据库、 BAM 星型架构数据库、 BAM 主导入数据库和 BAM 存档数据库。 因此，这些数据库是特别重要，如果灾难发生，并且确定群集的数据库时，必须具有更高的优先级。 仅用户或工具写入其他数据库。 对于 MessageBox 数据库中，你可以考虑具有主动/主动/被动或主动/主动/主动/被动配置，以便最大程度减少所需的硬件。  
  
> [!NOTE]  
>  SQL Server Standard Edition 支持 2 节点故障转移群集。 如果你决定使用 SQL Server 上的主动/主动/被动配置，您必须使用企业版。  
  
## <a name="procedures-for-clustering-the-databases"></a>群集数据库的过程  
 请确保在开始群集 BizTalk Server 数据库之前满足以下先决条件。  
  
-   当为您的 BizTalk Server 环境中创建域组时，必须创建全局域帐户。  
  
-   安装和配置 BizTalk Server 之前，请配置 SQL Server 群集。 请参阅[Windows Server 故障转移群集 (WSFC) 与 SQL Server](https://docs.microsoft.com/sql/sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server)或[Always On 故障转移群集实例 (SQL Server)](https://docs.microsoft.com/sql/sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server)。  
  
-   如果你要创建群集的主密钥服务器，请首先配置该服务器。 请参阅[主密钥服务器的高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)。  
  
#### <a name="run-biztalk-configuration"></a>运行 BizTalk 配置  
  
1.  在运行时服务器上安装 BizTalk Server。  
  
2. 打开“BizTalk Server 配置”。  
  
3.  若要应用自定义配置，请参阅[导入和导出 BizTalk Server 配置](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)。 若要为 BizTalk Server 数据库输入中的 SQL Server 群集的名称指定 SQL Server 群集**数据库**配置的对话框。  
  
4.  BizTalk Server 配置使用完成[自定义配置](../install-and-config-guides/configure-biztalk-server.md)。
  
 有关群集 BizTalk Server 数据库的详细信息，请参阅[通过使用 Windows Server 2008 故障转移群集或 Windows Server 2003 服务器群集的 BizTalk Server 中改进容错功能](https://www.microsoft.com/download/details.aspx?id=2290)。  
  
## <a name="behavior-of-biztalk-host-instances-during-sql-server-failover"></a>在 SQL Server 故障转移期间的 BizTalk 主机实例的行为  
 有关详细信息行为 BizTalk 主机实例的 SQL Server 故障转移期间，请参阅[行为的 BizTalk Server 主机实例在 SQL Server 故障转移期间](../core/behavior-of-biztalk-server-host-instances-during-sql-server-failover.md)。  
  
## <a name="using-sql-server-database-mirroring"></a>使用 SQL Server 数据库镜像  
 有关使用 SQL Server 数据库镜像与 BizTalk Server 数据库群集的详细信息，请参阅[SQL Server 数据库镜像，卷影复制服务和 AlwaysOn](../core/sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson.md)。  
  
## <a name="see-also"></a>另请参阅  
 [横向扩展 BizTalk Server 数据库](../technical-guides/scaling-out-the-biztalk-server-databases.md)