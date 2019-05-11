---
title: SQL Server 设置不能更改 |Microsoft Docs
description: 最大并行度，自动创建统计信息自动更新统计信息和重新生成在 BizTalk Server 中的索引
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4b383bfb-c3d9-47d4-b294-f6be94302734
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cfbacbce925ae81e41467196e052d258d59124e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65278955"
---
# <a name="sql-server-settings-that-should-not-be-changed"></a>不应更改的 SQL Server 设置
设置时[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]期间的操作准备情况过程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，您应该对以下设置进行更改。  
  
## <a name="sql-server-max-degree-of-parallelism"></a>SQL Server 最大并行度  
 最大并行度 (MDOP) 的设置为"1"在配置期间[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]有关[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]个实例托管[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库。 这是[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例级别设置。 从"1"的值不应更改此设置。 此设置更改为"1"之外的任何内容可以对产生明显的负面影响[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]存储过程和性能。 如果更改的实例的并行度设置[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]将产生负面影响在其执行其他数据库应用程序上的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例，应创建一个单独的实例[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]专用于承载[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。  
  
 并行查询通常最适合于批处理和决策支持工作负荷。 它们通常不是一个事务处理环境，其中有许多较短的快速查询正在并行运行这种情况屡见不鲜。 此外，更改会导致查询性能不佳或甚至使用死锁设置有时会导致查询计划以更改，MDOP[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]查询。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]存储的过程提供正确的连接，并尽可能以尝试使查询优化器很少，将计划更改锁定提示。 这些存储的过程通过构建查询，以便查询优化器执行不相关的最大程度地提供一致的查询执行。  
  
 有关详细信息，请参阅[KB 899000:BizTalk Server 使用的 SQL Server 实例的并行度设置](https://support.microsoft.com/help/899000/the-parallelism-setting-for-the-instance-of-sql-server-when-you-config)。  
  
## <a name="sql-server-statistics-on-the-messagebox-database"></a>在 MessageBox 数据库上的 SQL Server 统计信息  
 默认情况下关闭的以下选项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库时创建它：  
  
- 自动创建统计信息  
  
- 自动更新统计信息  
  
  不要启用这些选项对 MessageBox 数据库。 启用"自动创建统计信息"和"自动更新统计信息"选项可能导致不良查询执行延迟，尤其是在高负荷环境。  
  
  此外，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]存储的过程具有完全联接和查询中指定的锁提示。 这样做是为了确保最佳查询计划可供[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中的查询[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 已知的分布区和预期的查询的结果;已知的大约行数返回。 通常不需要统计信息。  
  
  有关详细信息，请参阅以下 Microsoft 知识库文章：  
  
- **912262**—["自动更新统计信息选项的自动创建统计信息选项和作为 BizTalk Server BizTalkMsgBoxDB 数据库宿主的 SQL Server 数据库实例中关闭的并行度设置"](https://support.microsoft.com/help/912262/the-auto-update-statistics-option-the-auto-create-statistics-option-an).  
  
- **917845**—["你遇到阻止，当您尝试连接到 BizTalk Server 中在 BizTalkMsgBoxDb 数据库死锁条件或其他 SQL Server 问题"](https://support.microsoft.com/help/917845/you-experience-blocking--deadlock-conditions--or-other-sql-server-issu)。  
  
## <a name="changes-to-the-messagebox-database"></a>对 MessageBox 数据库的更改  
 MessageBox 数据库应视为非 Microsoft 应用程序源代码。 也就是说，您应不"调整"对表、 索引、 存储的过程和大多数 SQL Server 数据库设置的更改通过 MessageBox 数据库。 在 BizTalk 核心引擎的网络日志的详细信息，请参阅[和与 MessageBox 数据库服务器不能做](http://go.microsoft.com/fwlink/p/?LinkId=101577)。  
  
## <a name="default-settings-for-the-database-index-rebuilds-and-defragmentation"></a>数据库索引重新生成和碎片整理的默认设置  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不支持磁盘碎片整理的索引。 "DBCC INDEXDEFRAG"和"ALTER INDEX... 重新组织..." 不受支持，因为它们使用页锁定，这可能导致阻塞和死锁[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 执行支持数据库索引重新生成 （"DBCC DBREINDEX"和"ALTER INDEX... 重新生成..."），但它们仅应执行在维护时段时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未处理的数据。 索引重新生成时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]正在处理的数据不受支持。  
  
 有关详细信息，请参阅[KB 917845:遇到阻止，当您尝试连接到 BizTalk Server 中在 BizTalkMsgBoxDb 数据库死锁条件或其他 SQL Server 问题"](https://support.microsoft.com/help/917845/you-experience-blocking--deadlock-conditions--or-other-sql-server-issu)。  
  
 索引碎片不太多的性能问题的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]因为它将针对 DSS 系统或执行索引扫描的 OLTP 系统。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 执行极具选择性的查询和更新和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]存储的过程并不会导致表扫描或索引扫描。  
  
 
## <a name="see-also"></a>请参阅  
 [清单：配置 SQL Server](~/technical-guides/checklist-configuring-sql-server.md)
