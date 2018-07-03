---
title: 如何避免磁盘 Contention2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37bdf6bd-cb34-4540-819e-908d83a22d40
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 867ea9be9d9e2cae0e167ec8c958d7d004730af8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007534"
---
# <a name="how-to-avoid-disk-contention"></a>如何避免磁盘争用
BizTalk Server 设计为永久性系统。 对于高吞吐量方案中，MessageBox 和 BizTalk 跟踪数据库可能会遇到严重的争用现象。 缓慢的磁盘速度会进一步加重这种争用状况。 如果是磁盘速度缓慢 （大于平均的平均时间Disk sec/Read 和平均值。Disk sec/Write)，它可能会导致 SQL Server 保存锁定更长 （高锁定等待时间和高锁定超时）。 此操作，反过来，可能导致 MessageBox 表 （Spool 和应用程序队列） 不断增长，引起数据库膨胀和限制。 这种情况下会最终导致较低的整体稳定吞吐量。  
  
> [!NOTE]  
>  有关如何确定服务器是否存在磁盘瓶颈的信息，请参阅[Windows 性能监视器](http://go.microsoft.com/fwlink/?LinkID=204007)(http://go.microsoft.com/fwlink/?LinkID=204007)。 Windows 性能监视器是 Microsoft 管理控制台 (MMC) 管理单元提供用于分析系统性能的工具。  
  
 若要避免磁盘争用，请执行以下操作：  
  
|步骤|参考|  
|-----------|---------------|  
|使用 Raid10 0 + 1 个磁盘配置。|[避免瓶颈的最佳做法](../technical-guides/best-practices-for-avoiding-bottlenecks.md)|  
|如果可能，将部署在高速 SAN 上的数据库。 如果多个数据库共享相同的磁盘，我们建议在单独的上配置它们**专用**磁盘。 此外，我们建议将分离到不同的磁盘上的 MessageBox 数据库的 MDF 和 LDF 文件。|[优化文件组的数据库 2](../technical-guides/optimizing-filegroups-for-the-databases2.md)|  
|请考虑为 TEMPDB 数据库中，分配多个文件，这是因为这将显著减少磁盘争用并跨多个数据文件分散负载。|[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|请考虑将 MessageBox 数据库是独立于 BizTalk 跟踪数据库的专用服务器上。|[配置后数据库 Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|将 MSDTC 日志文件目录分配到单独的专用驱动器。|[优化操作系统性能](../technical-guides/optimizing-operating-system-performance.md)|  
|如果因 PageFile 或 MSDTC 日志而在本地驱动器上出现争用情况，请尝试将 PageFile 和/或 MSDTC 日志移到不同的驱动器上。|[避免瓶颈的最佳做法](../technical-guides/best-practices-for-avoiding-bottlenecks.md)|  
|优化写入操作的跟踪数据库。|[如何找出跟踪数据库数据库的瓶颈](../technical-guides/how-to-identify-bottlenecks-in-the-tracking-database.md)|  
|优化 MessageBox 数据库进行读取和写入操作。|[如何找出 MessageBox 数据库 1 的瓶颈](../technical-guides/how-to-identify-bottlenecks-in-the-messagebox-database1.md)|  
|如果 BizTalk 主机实例使 CPU 负载饱和，请考虑将发送、 接收、 处理和跟踪到多个主机的功能。 这会配置系统，以便在单独的专用服务器来提高系统的整体吞吐量上运行的业务流程功能。|[优化 BizTalk Server 性能](../technical-guides/optimizing-biztalk-server-performance.md)|  
|如果部署了多个业务流程，请考虑在不同的专用业务流程主机中登记它们。 这将不同的业务流程隔离开来，并防止争用同一物理地址空间中或在同一服务器上的共享资源。|[优化 BizTalk Server 性能](../technical-guides/optimizing-biztalk-server-performance.md)|  
|请考虑使用 Windows 性能监视器诊断磁盘争用问题...|[Windows 性能监视器](http://go.microsoft.com/fwlink/?LinkID=204007)|  
  
 有关磁盘性能分析的详细信息，请参阅以下资源：  
  
- [绑定磁盘问题不再](http://go.microsoft.com/fwlink/?LinkId=120947)(超链接"<http://go.microsoft.com/fwlink/?LinkId=120947>"\t"_blank"<http://go.microsoft.com/fwlink/?LinkId=120947>)。  
  
- [SQL Server 预部署 I/O 最佳实践](http://go.microsoft.com/fwlink/?LinkId=120948)(http://go.microsoft.com/fwlink/?LinkId=120948)。  
  
- "I/O 瓶颈"一节[排查 SQL Server 2008 中的性能问题](http://go.microsoft.com/fwlink/?LinkID=153586)(http://go.microsoft.com/fwlink/?LinkID=153586)。  
  
## <a name="see-also"></a>请参阅  
 [数据库层的瓶颈](../technical-guides/bottlenecks-in-the-database-tier.md)