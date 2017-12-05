---
title: "数据库的高可用性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63813d87-1ce4-4645-bb2a-d55e413fcace
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24e17afbf9e33f3e12553d7ded5068370d8ca085
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="high-availability-for-databases"></a>数据库的高可用性
BizTalk Server 十分依赖 SQL Server 数据存储和数据持久性。 在将完全不同的业务应用程序（例如，接收、处理或路由消息）相集成的过程中，BizTalk Server 中的其他所有组件和主机都具有特定的角色，只有数据库计算机会捕获此工作并将其保存到磁盘。 例如，当 BizTalk Server 接收传入消息，接收主机将其保存到 MessageBox 数据库之前的其他主机检索业务流程处理和发送的消息。 如果你的 BizTalk 解决方案涉及业务流程，BizTalk Server 会将消息路由到执行业务流程 （处理主机），并将该消息保存到 MessageBox 数据库，业务流程完成后的主机。 随后，发送主机将从该数据库中检索消息，再通过相应的发送适配器将该消息发送到外部应用程序。  
  
 若要为 BizTalk Server 数据库提供高可用性，使用 Windows 群集配置两个或多个运行 SQL Server 创建服务器群集的计算机。 此服务器群集提供冗余和容错的 BizTalk Server 数据库。 与负载平衡群集（其中一组计算机共同作用以提高可用性和可伸缩性）不同，服务器群集通常只包含两台采用主动/被动配置的数据库计算机，以便其中一台计算机可为另一台计算机提供备份资源。  
  
 下图显示了通过主动/被动服务器群集确保其高度可用的 BizTalk Server 数据库层。  
  
 ![BizTalk Server 数据库层](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 如果主动数据库计算机遇到错误或失败，则被动计算机将变为主动并承担对数据库资源的控制，直至修复该出错的计算机。 数据库服务故障转移和还原到新活动的计算机的数据连接，并使 BizTalk 应用程序以继续正常工作。  
  
## <a name="biztalk-server-databases"></a>BizTalk Server 数据库  
 Microsoft BizTalk Server 在 SQL Server 中安装了若干数据库。 下表显示了 BizTalk Server 数据库的典型用法特征。  
  
|数据库|默认数据库名称|使用特性|  
|--------------|---------------------------|---------------------------|  
|管理数据库|BizTalkMgmtDb|此数据库句柄使用率低的读取和写入操作。|  
|MessageBox 数据库|BizTalkMsgBoxDb|此数据库句柄高使用率读取和写入操作。|  
|跟踪数据库|BizTalkDTADb|此数据库处理可能的高使用率写操作，具体取决于你配置要跟踪的数据量和使用率低的读取操作。|  
|SSO 数据库|SSODB|此数据库句柄使用率低的读取和写入操作。|  
|BAM 分析数据库|BAMAnalysis|此 SQL Server Analysis Services 数据库处理可能的高使用率读取和写入操作，具体取决于监视执行级别。|  
|BAM 星型架构数据库|BAMStarSchema|此 SQL Server Analysis Services 数据库处理可能的高使用率读取和写入操作，具体取决于监视执行级别。|  
|BAM 主导入数据库|BAMPrimaryImport|此 SQL Server Analysis Services 数据库处理可能的高使用率读取和写入操作，具体取决于监视执行级别。|  
|BAM 存档数据库|BAMArchive|此 SQL Server Analysis Services 数据库处理可能的高使用率读取和写入操作，具体取决于监视执行级别。|  
|规则引擎数据库|BizTalkRuleEngineDb|此数据库处理可能使用率低的读取和写入操作，除非更新规则。|  
|跟踪 Analysis Services 数据库|BizTalkAnalysisDb|此 SQL Server Analysis Services 数据库句柄高使用率读取和写入操作。|  
  
 BizTalk Server 运行时操作通常使用的前四个数据库 （管理数据库、 MessageBox 数据库、 跟踪数据库和 SSO 数据库）。 具体取决于在这些数据库上的流量，可以将它们放在运行 SQL Server 的不同计算机上。 根据您使用的 BizTalk Server 功能的不同，此表中可能包含其他某些或所有数据库。 可以向外扩展，还可以根据需要群集这些数据库。  
  
 请确保遵循良好的 SQL Server 部署做法，例如，每个数据库使用不同的磁盘。  
  
 BizTalk Server 数据库中，我们建议你以下：  
  
-   **设置故障转移群集**。 故障转移群集支持 SQL Server 自动切换到工作服务器从发生故障的服务器的 SQL Server 实例的处理。  
  
     BAM 主导入数据库收集事件数据。 在系统发生灾难时，自上次备份后写入 BAM 主导入数据库的数据将会丢失。 没有要重新生成丢失的事件的方法，因为它一点尤其重要，启用故障转移群集上 BAM 主导入数据库。  
  
-   **使用 SQL Server RAID 1 + 0 （独立磁盘冗余阵列）**，尤其是对于 MessageBox 数据库和 BAM 主导入数据库。  
  
 有关备份 BizTalk Server 数据库的信息，请参阅[灾难恢复最佳方案](../technical-guides/best-practices-for-disaster-recovery.md)。  
  
> [!NOTE]  
>  Microsoft SQL Server 提供名为数据库镜像提高数据库可用的概率的软件解决方案。 使用 SQL Server 数据库镜像当前不是由于潜在问题维护在 BizTalk Server 数据库的事务一致性确保 Microsoft BizTalk Server 数据库的高可用性支持的解决方案。  
>   
>  有关数据库镜像和 SQL Server 中的跨数据库事务的详细信息，请参阅[事务的可用性组和数据库镜像](https://docs.microsoft.com/sql/database-engine/availability-groups/windows/transactions-always-on-availability-and-database-mirroring)。 BizTalk Server 数据库应该安装在 SQL Server 群集，以确保高可用性和应可供实现灾难恢复使用日志传送。  
>   
>  关于日志传送的详细信息，请参阅[什么是 BizTalk Server 日志传送？](../technical-guides/what-is-biztalk-server-log-shipping.md)  
  
## <a name="in-this-section"></a>本节内容  
  
-   [聚类分析 BizTalk Server 数据库](../technical-guides/clustering-the-biztalk-server-databases2.md)  
  
-   [横向扩展 BizTalk Server 数据库](../technical-guides/scaling-out-the-biztalk-server-databases.md)  
  
## <a name="see-also"></a>另请参阅  
 [高可用性规划](../technical-guides/planning-for-high-availability2.md)   
 [BizTalk 主机的高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)   
 [主密钥服务器的高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)   
 [灾难恢复](../technical-guides/disaster-recovery.md)