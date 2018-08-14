---
title: 监视 SQL Server 的性能 |Microsoft Docs
description: 监视 BizTalk Server 数据库使用的性能工具、 活动监视器和数据收集
ms.custom: ''
ms.date: 11/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 020fa764-968e-467c-b146-d069f5606a0f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 730896dc1cf0a465f68965f812da7311dd8664ab
ms.sourcegitcommit: ed9590dbcd97c12a1fe5ce2cdf8d826492cccdff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "39640113"
---
# <a name="monitor-sql-server-performance"></a>监视 SQL Server 性能
SQL Server 提供了几个工具，用于监视 SQL Server 中的事件和优化物理数据库设计。 [适用于性能监视和优化工具](https://docs.microsoft.com/sql/relational-databases/performance/performance-monitoring-and-tuning-tools)介绍了这些工具。 
  
BizTalk Server 是一个占用大量数据库的过程。 故障排除时 BizTalk Server 性能问题，可能非常有益，则亦检查 SQL Server 性能。 以下工具可帮助。  
  
## <a name="sql-server-activity-monitor"></a>SQL Server 活动监视器  
SQL Server 活动监视器提供了有关 SQL Server 进程以及这些进程如何影响 SQL Server 的当前实例的信息。 有关详细信息，请参阅[活动监视器](https://docs.microsoft.com/sql/relational-databases/performance-monitor/activity-monitor)，并[如何： 打开活动监视器 (SQL Server Management Studio](https://docs.microsoft.com/sql/relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio)。 
  
## <a name="sql-serverdata-collection"></a>SQL 服务器数据集合  
SQL Server 提供了一个数据收集器，可用于获取和保存从多个源收集的数据。 数据收集器，可使用数据收集容器，使您能够确定作用域和运行 SQL Server 的计算机上的数据收集的频率。 请参阅[数据收集](https://docs.microsoft.com/sql/relational-databases/data-collection/data-collection)。
  
## <a name="see-also"></a>请参阅  
 [优化数据库性能](../technical-guides/optimizing-database-performance.md)
