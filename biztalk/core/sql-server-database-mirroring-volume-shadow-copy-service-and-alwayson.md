---
title: "SQL Server 数据库镜像，卷影复制服务和 AlwaysOn |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b965cafc-cd34-4657-975d-0dedffd27333
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bea9d6063330e7af15ecb202513deb4def6571fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson"></a>SQL Server 数据库镜像、卷影复制服务和 AlwaysOn
Microsoft 提供了名为 SQL Server 的软件解决方案*数据库镜像*和 Windows 卷影复制服务 (VSS) 来增加对特定方案的高可用性。 SQL Server*数据库镜像*，卷影复制服务 (VSS) 提供了用于灾难恢复的备份和还原功能数据库时可用的可能性就越高。 使用 SQL Server*数据库镜像*或 Windows 卷影复制服务不支持用于确保 Microsoft 的高可用性解决方案[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。  
  
## <a name="using-sql-server-database-mirroring-to-provide-high-availability-for-biztalk-server-databases"></a>使用 SQL Server 数据库镜像提供 BizTalk Server 数据库的高可用性  
 使用 SQL Server*数据库镜像*目前不支持的解决方案确保高可用的 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]由于事务中保持一致性的潜在问题的数据库BizTalk Server 数据库。 有关数据库镜像和 SQL Server 中的跨数据库事务的详细信息请参阅[http://go.microsoft.com/fwlink/?LinkId=87977](http://go.microsoft.com/fwlink/?LinkId=87977)。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库应安装在 SQL Server 群集，以确保高可用性和 BizTalk 应为灾难恢复目的而使用日志传送。 有关 BizTalk 日志传送的详细信息，请参阅[日志传送](../core/log-shipping.md)。  
  
## <a name="using-the-volume-shadow-copy-service-to-provide-high-availability-for-biztalk-server-databases"></a>使用卷影复制服务为 BizTalk Server 数据库提供高可用性  
 卷影复制服务可为灾难恢复提供备份和还原功能。 因为与 Microsoft 分布式事务处理协调器 (MS DTC) 支持 VSS 仅限于本地的部署和事务协调方案 （以及还受其他限制的约束），使用 VSS 服务当前不是一个受支持的解决方案确保 Microsoft 的高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 有关与分布式事务的卷影复制服务支持的详细信息请参阅[http://go.microsoft.com/fwlink/?LinkId=139505](http://go.microsoft.com/fwlink/?LinkId=139505)。  
  
## <a name="using-sql-server-alwayson"></a>使用 SQL Server AlwaysOn 
 在单独的计算机上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 时，分布式事务协调器 (MS DTC) 处理计算机之间的事务。 
 
从 SQL Server 2016 开始，AlwaysOn 支持 MSDTC 事务。 因此，[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]时使用此 SQL Server 版本支持 AlwaysOn 功能。 与以前的 SQL Server 版本， [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] AlwaysOn 功能不支持 MSDTC 事务，因此不支持 AlwaysOn。 

请参阅[使用 SQL Server Alwayson 可用性组的高可用性](../core/high-availability-using-sql-server-always-on-availability-groups.md)。
  
## <a name="see-also"></a>另请参阅  
 [群集的 BizTalk Server 数据库](../core/clustering-the-biztalk-server-databases1.md)   
 [有关备份和还原的高级的信息](../core/advanced-information-about-backup-and-restore1.md)