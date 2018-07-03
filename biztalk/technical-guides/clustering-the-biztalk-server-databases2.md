---
title: 群集数据库 |Microsoft Docs
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
ms.openlocfilehash: bcdc4c2c628a031ab235ce5821c01b56e5f86851
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991502"
---
# <a name="clustering-the-biztalk-server-databases"></a>聚类分析 BizTalk Server 数据库
如果 BizTalk Server 数据库变得不可用，BizTalk Server 环境将不能正常工作。 若要提供高可用性，可以创建 BizTalk Server 数据库的 Microsoft SQL Server 群集，如下图中所示。  
  
 ![BizTalk Server 数据库层](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 若要创建 BizTalk Server 数据库的高度可用的解决方案，必须具有至少两个群集中运行 SQL Server 和一个共享的磁盘阵列的计算机。  
  
## <a name="clustering-options"></a>聚类分析选项  
 确定 BizTalk Server 数据库来满足业务需求的最佳群集配置。 下面是选项的列表：  
  
-   **主动/被动**。 BizTalk Server 数据库的高可用性通常由在主动/被动服务器群集配置中配置的两个或多个数据库计算机组成。 这些计算机共享公共的磁盘资源 (例如 RAID 1 + 0 SCSI 磁盘阵列或存储区域网络) 并使用 Windows 群集提供备份冗余和容错功能。  
  
-   **主动/主动**。 Windows 群集和 SQL Server 允许您在主动/主动模式下运行 SQL Server 的群集的每个节点都是"活动"并运行一个或多个 SQL Server 实例。 例如，这将允许您在其他节点上具有一个节点和所有其他 BizTalk Server 数据库上的 MessageBox 数据库。 这使您可以最大程度提高群集的硬件的使用情况，但应谨慎使用主动/主动 SQL Server 配置。  
  
     可以每个节点同时处理的所有 SQL Server 实例的负载在 SQL Server 群集节点故障转移方案期间？ 是否有足够的 CPU 资源？ 是否有足够的内存？ 网络带宽如何呢？ 如何为磁盘 I/O 争用？  
  
     它们只是为了确定是否适合您的 BizTalk 应用程序的主动/被动 SQL Server 群集必须回答的问题的一部分。 如果确定一个节点不能处理故障转移方案中的所有 SQL Server 实例，一种替代方法是使用主动/主动/被动群集。  
  
-   **主动/主动/被动**。 运行时进程写入到 BizTalk 管理数据库、 MessageBox 数据库、 跟踪 Analysis Services 数据库、 BAM 分析数据库、 BAM 星型架构数据库、 BAM 主导入数据库和 BAM 存档数据库。 因此，这些数据库是尤为重要，如果在灾难发生，并且确定哪些数据库移到群集时，必须具有更高的优先级。 只有用户或工具写入其他数据库。 对于 MessageBox 数据库中，可以考虑要最大程度减少所需的硬件的主动/主动/被动或主动/主动/主动/被动配置。  
  
> [!NOTE]  
>  SQL Server Standard Edition 支持 2 节点故障转移群集。 如果您决定使用 SQL Server 上的主动/主动/被动配置，则必须使用 Enterprise Edition。  
  
## <a name="procedures-for-clustering-the-databases"></a>聚类分析数据库的过程  
 请确保您满足以下先决条件，才能启动群集 BizTalk Server 数据库。  
  
-   BizTalk Server 环境中创建域组时，必须创建域全局帐户。  
  
-   安装和配置 BizTalk Server 之前，请配置 SQL Server 群集。 请参阅[Windows Server 故障转移群集 (WSFC) 与 SQL Server](https://docs.microsoft.com/sql/sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server)或[Alwayson 故障转移群集实例 (SQL Server)](https://docs.microsoft.com/sql/sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server)。  
  
-   如果您要群集主密钥服务器，请首先配置该服务器。 请参阅[主密钥服务器的高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)。  
  
#### <a name="run-biztalk-configuration"></a>运行 BizTalk 配置  
  
1. 在运行时服务器上安装 BizTalk Server。  
  
2. 打开“BizTalk Server 配置”。  
  
3. 若要应用自定义配置，请参阅[导入和导出 BizTalk Server 配置](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)。 若要指定 SQL Server 群集在 BizTalk Server 数据库输入中的 SQL Server 群集的名称**数据库**配置的对话框。  
  
4. 完成 BizTalk Server 配置使用[自定义配置](../install-and-config-guides/configure-biztalk-server.md)。
  
   有关群集 BizTalk Server 数据库的详细信息，请参阅[通过使用 Windows Server 2008 故障转移群集或 Windows Server 2003 服务器群集的 BizTalk Server 中改进容错能力](https://www.microsoft.com/download/details.aspx?id=2290)。  
  
## <a name="behavior-of-biztalk-host-instances-during-sql-server-failover"></a>SQL Server 故障转移期间 BizTalk 主机实例的行为  
 有关详细信息行为 BizTalk 主机实例的 SQL Server 故障转移期间，请参阅[行为的 BizTalk Server 主机实例 SQL Server 故障转移期间](../core/behavior-of-biztalk-server-host-instances-during-sql-server-failover.md)。  
  
## <a name="using-sql-server-database-mirroring"></a>使用 SQL Server 数据库镜像  
 有关使用 SQL Server 数据库镜像相对于 BizTalk Server 数据库的聚类分析的详细信息，请参阅[SQL Server 数据库镜像、 卷影复制服务和 AlwaysOn](../core/sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson.md)。  
  
## <a name="see-also"></a>请参阅  
 [横向扩展 BizTalk Server 数据库](../technical-guides/scaling-out-the-biztalk-server-databases.md)