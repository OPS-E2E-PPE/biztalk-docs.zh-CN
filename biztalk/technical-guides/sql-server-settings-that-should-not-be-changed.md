---
title: "不应更改的 SQL Server 设置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4b383bfb-c3d9-47d4-b294-f6be94302734
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2fb6e2553c005d3ba8651c860ff844e8cc74106
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sql-server-settings-that-should-not-be-changed"></a>不应更改的 SQL Server 设置
设置时[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]期间的操作的准备情况过程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，你不应更改为下列设置。  
  
## <a name="sql-server-max-degree-of-parallelism"></a>SQL Server 最大并行度  
 最大程度的并行度 (MDOP) 设置为"1"在配置期间[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]instance(s) 该主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库。 这是[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例级别设置。 从"1"的值不应更改此设置。 将此设置更改为"1"之外的任何内容会对严重的负面影响[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]存储过程和性能。 如果更改的实例的并行度设置[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]会造成负面影响在其执行其他数据库应用程序上的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例，应创建单独的实例[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]专用于承载[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。  
  
 并行查询通常最适合于批处理和决策支持工作负荷。 它们通常不是在有许多较短的快速查询正在并行事务处理环境中所需。 此外，更改设置有时原因查询计划更改，这会导致查询性能不佳或甚至死锁与 MDOP[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]查询。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]存储的过程提供正确的连接和锁定提示，只要有可能为了尝试以防止执行极大的工作和更改计划的查询优化器。 这些存储的过程通过构造查询，以便查询优化器清除出图尽可能多地提供一致的查询执行。  
  
 有关详细信息，请参阅 Microsoft 知识库文章 899000， ["的实例的 SQL Server 配置 BizTalk Server 时的并行度设置"](http://go.microsoft.com/fwlink/?LinkId=153432) (http://go.microsoft.com/fwlink/?LinkId=153432)。  
  
## <a name="sql-server-statistics-on-the-messagebox-database"></a>在 MessageBox 数据库上的 SQL Server 统计信息  
 以下选项处于关闭状态在默认情况下[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库创建时：  
  
-   自动创建统计信息  
  
-   自动更新统计信息  
  
 不要启用 MessageBox 数据库上的这些选项。 启用"自动创建统计信息"和"自动更新统计信息"选项可能导致意外的查询执行延迟，特别是在高负荷环境。  
  
 此外，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]存储的过程具有完全联接和在查询中指定的锁提示。 这样做是为了确保最佳查询计划可供[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中的查询[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 已知的分发和预期的结果的查询;已知返回的行的大致数目。 通常不需要统计信息。  
  
 有关详细信息，请参阅以下 Microsoft 知识库文章：  
  
-   **912262**-["自动更新统计信息选项的自动创建统计信息选项和并行度设置处于关闭状态中承载 BizTalk Server BizTalkMsgBoxDB 数据库的 SQL Server 数据库实例"](http://go.microsoft.com/fwlink/?LinkId=153430)(http://go.microsoft.com/fwlink/?LinkId=153430)。  
  
-   **917845**-["你遇到阻止，死锁条件或其他 SQL Server 问题，当你尝试连接到 BizTalk Server 中的 BizTalkMsgBoxDb 数据库时"](http://go.microsoft.com/fwlink/?LinkId=153429) (http://go.microsoft.com/fwlink/?LinkId=153429)。  
  
## <a name="changes-to-the-messagebox-database"></a>对 MessageBox 数据库的更改  
 MessageBox 数据库应被视为非 Microsoft 应用程序源代码。 也就是说，你应不"调整"MessageBox 数据库通过对表、 索引、 存储的过程和大多数 SQL Server 数据库设置的更改。 有关详细信息，请在 BizTalk 核心引擎日志，请参阅输入["什么可以并不能执行与 MessageBox 数据库服务器"](http://go.microsoft.com/fwlink/?LinkId=101577) (http://go.microsoft.com/fwlink/?LinkId=101577)。  
  
## <a name="default-settings-for-the-database-index-rebuilds-and-defragmentation"></a>数据库索引重新生成和碎片整理的默认设置  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不支持磁盘碎片整理的索引。 "DBCC INDEXDEFRAG"和"ALTER INDEX... 重新组织..." 因为它们使用的页锁定，可能会导致阻塞和死锁与不支持[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]执行支持数据库重新生成索引后 （"DBCC DBREINDEX"和"ALTER INDEX... 重新生成..."），但它们应该仅可以在维护时段时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未处理数据。 索引重新生成时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]正在处理不支持数据。  
  
 有关详细信息，请参阅 Microsoft 知识库文章 917845 ["你遇到阻止，死锁条件或其他 SQL Server 问题，当你尝试连接到 BizTalk Server 中的 BizTalkMsgBoxDb 数据库时"](http://go.microsoft.com/fwlink/?LinkId=153429) (http://go.microsoft.com/fwlink/？LinkId = 153429)。  
  
 索引碎片不是尽可能多的性能问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]因为它处于 DSS 系统或执行索引扫描的 OLTP 系统。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]执行非常选择性的查询和更新和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]存储的过程不应导致表扫描或索引扫描。  
  
 有关索引碎片和工作负荷类型的详细信息，请参阅["Microsoft SQL Server 2000 索引碎片整理最佳实践"](http://go.microsoft.com/fwlink/?LinkId=101580) (http://go.microsoft.com/fwlink/?LinkId=101580)。 文章引号：  
  
 "中图 1 所示，存在很少之间区别是之前和之后对进行碎片整理的存储过程的性能。 通过这些存储过程发出的基础查询处理的数据非常选择性部分，因为工作负荷性能已不产生负面影响碎片的索引。"  
  
> [!NOTE]  
>  文章的内容也适用于[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]和[!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)]。  
  
## <a name="see-also"></a>另请参阅  
 [清单： 配置 SQL Server](~/technical-guides/checklist-configuring-sql-server.md)