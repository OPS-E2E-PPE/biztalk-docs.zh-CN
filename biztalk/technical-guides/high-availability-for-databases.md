---
title: 数据库的高可用性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63813d87-1ce4-4645-bb2a-d55e413fcace
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 841481946dd0eabd7707eb3923563741264129c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277180"
---
# <a name="high-availability-for-databases"></a>数据库的高可用性
BizTalk Server 很大程度依赖 SQL Server 上为数据存储和数据暂留。 所有其他组件和 BizTalk Server 中的主机具有特定的角色过程中集成完全不同的业务应用程序 （例如，接收、 处理或路由消息），但在数据库计算机捕获此工作并将其保存到磁盘。 例如，在 BizTalk Server 接收的传入消息，接收主机其保存到 MessageBox 数据库之前的其他主机检索业务流程处理和发送的消息。 如果您的 BizTalk 解决方案包含业务流程，BizTalk Server 会将消息路由到的主机执行业务程序 （处理主机），并在业务流程完成后，将消息保存到 MessageBox 数据库中。 发送主机然后将其发送到相应的发送适配器通过外部应用程序之前从数据库检索消息。  
  
 若要为 BizTalk Server 数据库提供高可用性，使用 Windows 群集来配置运行 SQL Server 创建服务器群集的两个或多个计算机。 此服务器群集提供冗余和容错能力的 BizTalk Server 数据库。 与负载平衡群集，不同的一组计算机共同作用以提高可用性和可伸缩性、 服务器群集通常涉及对数据库中的计算机的主动/被动配置，因此这一台计算机将提供备份对于其他资源。  
  
 下图显示了通过主动/被动服务器群集的高可用性 BizTalk Server 数据库层。  
  
 ![BizTalk Server 数据库层](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 如果主动数据库计算机遇到错误或失败，被动计算机将变为活动状态，并假定对数据库资源的控制，直到修复失败的计算机。 数据库服务故障转移和恢复到新的主动计算机的数据连接，并使 BizTalk 应用程序继续运行。  
  
## <a name="biztalk-server-databases"></a>BizTalk Server 数据库  
 Microsoft BizTalk Server 在 SQL Server 中安装多个数据库。 下表显示了 BizTalk Server 数据库的典型使用特性。  
  
|“数据库”|默认数据库名称|使用特性|  
|--------------|---------------------------|---------------------------|  
|管理数据库|BizTalkMgmtDb|此数据库句柄使用率低的读取和写入操作。|  
|MessageBox 数据库|BizTalkMsgBoxDb|此数据库句柄高使用率读取和写入操作。|  
|跟踪数据库|BizTalkDTADb|此数据库处理可能的高使用率写入操作，具体取决于您配置要跟踪的数据量和使用率低的读取操作。|  
|SSO 数据库|SSODB|此数据库句柄使用率低的读取和写入操作。|  
|BAM 分析数据库|BAMAnalysis|此 SQL Server Analysis Services 数据库处理可能的高使用率读取和写入操作，具体取决于执行监视的级别。|  
|BAM 星型架构数据库|BAMStarSchema|此 SQL Server Analysis Services 数据库处理可能的高使用率读取和写入操作，具体取决于执行监视的级别。|  
|BAM 主导入数据库|BAMPrimaryImport|此 SQL Server Analysis Services 数据库处理可能的高使用率读取和写入操作，具体取决于执行监视的级别。|  
|BAM 存档数据库|BAMArchive|此 SQL Server Analysis Services 数据库处理可能的高使用率读取和写入操作，具体取决于执行监视的级别。|  
|规则引擎数据库|BizTalkRuleEngineDb|此数据库处理可能使用率低的读取和写入操作，除非更新的规则。|  
|跟踪 Analysis Services 数据库|BizTalkAnalysisDb|此 SQL Server Analysis Services 数据库句柄高使用率读取和写入操作。|  
  
 BizTalk Server 运行时操作通常使用前四个数据库 （管理数据库、 MessageBox 数据库、 跟踪数据库和 SSO 数据库）。 具体取决于这些数据库上的流量，可以将它们放在运行 SQL Server 的不同计算机上。 根据您使用的 BizTalk Server 功能，您可能部分或所有其他数据库表中。 可以向外扩展，并根据需要群集这些数据库。  
  
 请确保遵循良好的 SQL Server 部署做法，例如，每个数据库使用不同的磁盘。  
  
 对于 BizTalk Server 数据库中，我们建议您以下：  
  
- **设置故障转移群集**。 故障转移群集，SQL Server 可自动切换到工作服务器从发生故障的服务器的 SQL Server 实例的处理。  
  
   BAM 主导入数据库收集事件数据。 发生灾难时，自上次备份后写入 BAM 主导入数据库的数据将会丢失。 因为没有方法来重新生成丢失的事件，它是启用故障转移群集在 BAM 主导入数据库上尤其重要。  
  
- **使用 SQL Server RAID 1 + 0 （独立磁盘冗余阵列）**，尤其是对于 MessageBox 数据库和 BAM 主导入数据库。  
  
  有关备份 BizTalk Server 数据库的信息，请参阅[灾难恢复最佳方案](../technical-guides/best-practices-for-disaster-recovery.md)。  
  
> [!NOTE]  
>  Microsoft SQL Server 提供了一种软件解决方案，称为数据库镜像以用于增加数据库可用的可能性。 使用 SQL Server 数据库镜像当前不支持为实现高可用性的 Microsoft BizTalk Server 数据库由于维护 BizTalk Server 数据库中的事务一致性可能存在问题的解决方案。  
>   
>  有关数据库镜像和 SQL Server 中的跨数据库事务的详细信息，请参阅[事务的可用性组和数据库镜像](https://docs.microsoft.com/sql/database-engine/availability-groups/windows/transactions-always-on-availability-and-database-mirroring)。 BizTalk Server 数据库应安装在 SQL Server 群集以确保高可用性，应为灾难恢复目的而利用日志传送。  
>   
>  有关日志传送的详细信息，请参阅[什么是 BizTalk Server 日志传送？](../technical-guides/what-is-biztalk-server-log-shipping.md)  
  
## <a name="in-this-section"></a>本节内容  
  
-   [聚类分析 BizTalk Server 数据库](../technical-guides/clustering-the-biztalk-server-databases2.md)  
  
-   [横向扩展 BizTalk Server 数据库](../technical-guides/scaling-out-the-biztalk-server-databases.md)  
  
## <a name="see-also"></a>请参阅  
 [规划高可用性](../technical-guides/planning-for-high-availability2.md)   
 [BizTalk 主机的的高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)   
 [主密钥服务器的高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)   
 [灾难恢复](../technical-guides/disaster-recovery.md)