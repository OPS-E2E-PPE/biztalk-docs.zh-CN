---
title: SQL Server 数据库镜像、 卷影复制服务和 AlwaysOn |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b965cafc-cd34-4657-975d-0dedffd27333
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dcf7ea68871d198ddf6a796d3022fc78647f925
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401782"
---
# <a name="sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson"></a>SQL Server 数据库镜像、 卷影复制服务和 AlwaysOn
Microsoft 提供了称为 SQL Server 的软件解决方案*数据库镜像*和 Windows 卷影复制服务 (VSS) 来增加特定方案的高可用性。 SQL Server*数据库镜像*提高数据库的可用性，而卷影复制服务 (VSS) 提供了用于灾难恢复的备份和还原功能的可能性。 使用 SQL Server*数据库镜像*或 Windows 卷影复制服务不是为确保高可用性的 Microsoft 支持解决方案[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。  
  
## <a name="using-sql-server-database-mirroring-to-provide-high-availability-for-biztalk-server-databases"></a>使用 SQL Server 数据库镜像对 BizTalk Server 数据库提供高可用性  
 使用 SQL Server*数据库镜像*目前不支持的解决方案，为确保高可用性的 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]由于维护事务一致性中的可能存在问题的数据库BizTalk Server 数据库。 有关数据库镜像和 SQL Server 中的跨数据库事务的详细信息请参阅[ http://go.microsoft.com/fwlink/?LinkId=87977 ](http://go.microsoft.com/fwlink/?LinkId=87977)。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库应安装在 SQL Server 群集，以确保高可用性和 BizTalk 应为灾难恢复目的而利用日志传送。 有关 BizTalk 日志传送的详细信息，请参阅[日志传送](../core/log-shipping.md)。  
  
## <a name="using-the-volume-shadow-copy-service-to-provide-high-availability-for-biztalk-server-databases"></a>使用卷影复制服务为 BizTalk Server 数据库提供高可用性  
 卷影复制服务提供了用于灾难恢复的备份和还原功能。 因为与 Microsoft 分布式事务处理协调器 (MS DTC) VSS 支持限于本地部署和事务协调案例 （而还受其他限制），使用 VSS 服务当前不是为支持的解决方案确保高可用性的 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 有关卷影复制服务支持分布式事务的详细信息请参阅[ http://go.microsoft.com/fwlink/?LinkId=139505 ](http://go.microsoft.com/fwlink/?LinkId=139505)。  
  
## <a name="using-sql-server-alwayson"></a>使用 SQL Server AlwaysOn 
 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]安装在不同计算机，分布式事务处理协调器 (MS DTC) 句柄的计算机之间的事务。 
 
从 SQL Server 2016 开始，AlwaysOn 支持 MSDTC 事务。 因此，[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]时使用此 SQL Server 版本支持 AlwaysOn 功能。 与 SQL Server 的早期版本， [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] AlwaysOn 功能不支持 MSDTC 事务，因此不支持 AlwaysOn。 

请参阅[使用 SQL Server Always On 可用性组实现高可用性](../core/high-availability-using-sql-server-always-on-availability-groups.md)。
  
## <a name="see-also"></a>请参阅  
 [聚类分析 BizTalk Server 数据库](../core/clustering-the-biztalk-server-databases1.md)   
 [有关备份和还原的高级信息](../core/advanced-information-about-backup-and-restore1.md)