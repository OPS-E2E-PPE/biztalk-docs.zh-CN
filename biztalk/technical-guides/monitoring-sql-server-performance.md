---
title: "监视 SQL Server 的性能 |Microsoft 文档"
description: "监视使用性能工具、 活动监视器和数据收集的 BizTalk Server 数据库"
ms.custom: 
ms.date: 11/29/2017
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
ms.openlocfilehash: 1e4f9db738298ec2a242350faae3ba5bc9da1c92
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="monitor-sql-server-performance"></a>监视 SQL Server 性能
SQL Server 提供几种工具，用于监视 SQL Server 中的事件和优化物理数据库设计。 [用于性能监视和优化工具](https://docs.microsoft.com/en-us/sql/relational-databases/performance/performance-monitoring-and-tuning-tools)介绍了这些工具。 
  
BizTalk Server 是一个需要进行大量数据库的过程。 在解决 BizTalk Server 性能问题时，它是有益的还要检查 SQL Server 性能。 以下工具可以帮助。  
  
## <a name="sql-server-activity-monitor"></a>SQL Server 活动监视器  
SQL Server 活动监视器提供有关 SQL Server 过程和了解这些进程如何影响当前的 SQL Server 实例的信息。 有关详细信息，请参阅[活动监视器](https://docs.microsoft.com/sql/relational-databases/performance-monitor/activity-monitor)，和[如何： 打开活动监视器 (SQL Server Management Studio](https://docs.microsoft.com/sql/relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio)。 
  
## <a name="sql-serverdata-collection"></a>SQL ServerData 集合  
SQL Server 提供了可用于获取和保存数据，则通过多个来源收集的数据收集器。 数据收集器，可使用使你可以确定的范围和频率的运行 SQL Server 的计算机上的数据收集的数据集合容器。 请参阅[数据收集](https://docs.microsoft.com/sql/relational-databases/data-collection/data-collection)。
  
## <a name="see-also"></a>另请参阅  
 [优化数据库性能](../technical-guides/optimizing-database-performance.md)