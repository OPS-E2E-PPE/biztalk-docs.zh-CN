---
title: "如何避免磁盘 Contention2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37bdf6bd-cb34-4540-819e-908d83a22d40
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7be7a38ac3f3f6cc1d7d266c664cbb85f731c22
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-avoid-disk-contention"></a>如何避免磁盘争用
BizTalk Server 设计为永久性系统中。 对于高吞吐量方案，MessageBox 和 BizTalk 跟踪数据库可能会遇到严重的争用现象。 缓慢的磁盘速度会进一步加重这种争用状况。 如果是磁盘降低 （大于平均的平均时间Disk sec/Read 或 avg.Disk sec/Write)，它可能会导致 SQL Server 保留更长的锁 （高锁等待的时间和高锁定超时）。 此操作，反过来，可能导致 MessageBox 表 （假脱机和应用程序的队列） 不断增长，导致数据库膨胀和限制。 这种情况下最终将导致较低的总体可持续吞吐量。  
  
> [!NOTE]  
>  有关如何确定如果服务器具有磁盘瓶颈的信息，请参阅[Windows 性能监视器](http://go.microsoft.com/fwlink/?LinkID=204007)(http://go.microsoft.com/fwlink/?LinkID=204007)。 Windows 性能监视器是一个 Microsoft 管理控制台 (MMC) 管理单元，提供工具以用于分析系统性能。  
  
 若要避免磁盘争用，请执行以下操作：  
  
|步骤|参考|  
|-----------|---------------|  
|使用 Raid10 0 + 1 个磁盘配置。|[为避免瓶颈的最佳做法](../technical-guides/best-practices-for-avoiding-bottlenecks.md)|  
|如果可能，部署高速 SAN 上的数据库。 如果多个数据库共享相同的磁盘，我们建议在单独上配置它们**专用**磁盘。 此外，我们建议分隔到不同的磁盘上的 MessageBox 数据库的 MDF 和 LDF 文件。|[针对 Databases2 优化文件组](../technical-guides/optimizing-filegroups-for-the-databases2.md)|  
|因为这将显著减少磁盘争用并将负载分布到多个数据文件，请考虑为 TEMPDB 数据库中，分配多个文件。|[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|请考虑将 MessageBox 数据库分别放在独立于 BizTalk 跟踪数据库的专用服务器。|[后配置数据库 Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|将 MSDTC 日志文件目录分配给单独的专用驱动器。|[优化操作系统性能](../technical-guides/optimizing-operating-system-performance.md)|  
|如果因 PageFile 或 MSDTC 日志而在本地驱动器上出现争用情况，请尝试将 PageFile 和/或 MSDTC 日志移到不同的驱动器上。|[为避免瓶颈的最佳做法](../technical-guides/best-practices-for-avoiding-bottlenecks.md)|  
|优化写入操作的跟踪数据库。|[如何确定跟踪数据库中的瓶颈](../technical-guides/how-to-identify-bottlenecks-in-the-tracking-database.md)|  
|优化 MessageBox 数据库进行读取和写入操作。|[如何确定 MessageBox Database1 中的瓶颈](../technical-guides/how-to-identify-bottlenecks-in-the-messagebox-database1.md)|  
|如果 BizTalk 主机实例占满 CPU，请考虑分隔发送、 接收、 处理和跟踪到多个主机的功能。 这会将配置系统，以便在单独的专用服务器来提高整体系统的吞吐量上运行的业务流程功能。|[优化 BizTalk Server 性能](../technical-guides/optimizing-biztalk-server-performance.md)|  
|如果部署多个业务流程，请考虑在不同的专用的 orchestration 主机中登记它们。 这将隔离不同的业务流程，并防止在同一物理地址空间或在同一服务器上的共享资源的争用。|[优化 BizTalk Server 性能](../technical-guides/optimizing-biztalk-server-performance.md)|  
|请考虑使用 Windows 性能监视器来诊断磁盘争用问题...|[Windows 性能监视器](http://go.microsoft.com/fwlink/?LinkID=204007)|  
  
 有关磁盘性能分析的详细信息，请参阅以下资源：  
  
-   [允许磁盘密集型问题](http://go.microsoft.com/fwlink/?LinkId=120947)(超链接"http://go.microsoft.com/fwlink/?LinkId=120947"\t"_blank"http://go.microsoft.com/fwlink/?LinkId=120947)。  
  
-   [SQL 服务器预部署 I/O 最佳实践](http://go.microsoft.com/fwlink/?LinkId=120948)(http://go.microsoft.com/fwlink/?LinkId=120948)。  
  
-   "I/O 瓶颈"部分[中 SQL Server 2008 的故障排除性能问题](http://go.microsoft.com/fwlink/?LinkID=153586)(http://go.microsoft.com/fwlink/?LinkID=153586)。  
  
## <a name="see-also"></a>另请参阅  
 [数据库层中的瓶颈](../technical-guides/bottlenecks-in-the-database-tier.md)