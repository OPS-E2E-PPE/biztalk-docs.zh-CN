---
title: "监视 SQL Server 性能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 020fa764-968e-467c-b146-d069f5606a0f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a5abdc3054576e03f28967017767112cea652f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-sql-server-performance"></a>监视 SQL Server 的性能
[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]提供多个工具来监视中的事件[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]和优化物理数据库设计。 主题中介绍这些工具[用于性能监视和优化工具](http://go.microsoft.com/fwlink/?LinkId=146357)(http://go.microsoft.com/fwlink/?LinkId=146357) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]联机丛书。 有关特定工具用于信息[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]下面提供的性能监视和优化。  
  
## <a name="sql-server-performance-monitoring-tools"></a>SQL Server 性能监视工具  
 因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是一个此类需要进行大量数据库的过程，很有帮助来看看什么中正在运行的 SQL Server 进行故障排除时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能问题。 本主题的其余部分介绍了性能监视工具可用于查看实时和存档数据上[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]和[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]。  
  
### <a name="sql-server-2008-r2-activity-monitor"></a>SQL Server 2008 R2 活动监视器  
 [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]活动监视器相关信息提供[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]进程并了解这些进程如何影响的当前实例[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 有关详细信息[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]活动监视器，请参阅[活动监视器](http://go.microsoft.com/fwlink/?LinkId=146355)(http://go.microsoft.com/fwlink/?LinkId=146355) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]联机丛书。 有关如何打开活动监视器信息[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio，请参阅[如何： 打开活动监视器 (SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=135094) (http://go.microsoft.com/fwlink/?LinkId=135094) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]联机丛书。  
  
### <a name="sql-server-2008-r2-data-collection"></a>SQL Server 2008 R2 数据收集  
 [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] 提供了一个数据收集器，您可以用它来获取和保存从多个源收集的数据。 通过数据收集器，您可以使用数据收集容器，这样便可确定对运行 [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] 的计算机进行数据收集的范围和频率。 有关实现详细信息[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]数据收集，请参阅[数据收集](http://go.microsoft.com/fwlink/?LinkId=146356)(http://go.microsoft.com/fwlink/?LinkId=146356) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]联机丛书。  
  
## <a name="see-also"></a>另请参阅  
 [优化数据库性能](../technical-guides/optimizing-database-performance.md)