---
title: "清单： 执行每周维护检查 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b13e43ba-4bac-4d4b-aaf8-46d60c0561bf
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4cc715db0ec4047b9625b83d457af8df3974719
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="checklist-performing-weekly-maintenance-checks"></a>清单： 执行每周维护检查
本主题介绍在每周执行的可靠性、 管理、 安全性和性能的维护检查所涉及的步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。  
  
|步骤|参考|  
|-----------|---------------|  
|确保每个主机有在至少两个物理 BizTalk 服务器 （可靠性检查） 上运行的实例。|[BizTalk 主机的高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)|  
|确保每个接收位置是冗余 （可靠性检查）。|[横向扩展接收主机](../technical-guides/scaling-out-receiving-hosts.md)|  
|确保 SQL Server 代理服务正在运行 SQL server （管理检查） 上。|-   [如何： 启动 SQL Server 代理](http://go.microsoft.com/fwlink/p/?LinkId=154672)(http://go.microsoft.com/fwlink/p/?LinkId=154672)。<br />-   [SQL Server 代理](http://go.microsoft.com/fwlink/p/?LinkId=106728)(http://go.microsoft.com/fwlink/p/?LinkId=106728)。|  
|确保与 BizTalk Server 相关的所有 SQL Server 作业是否正常都工作 （管理检查）。|[监视 SQL Server 代理作业](../technical-guides/monitoring-sql-server-agent-jobs.md)<br /><br /> 如果未运行 SQL Server 代理作业，将会随着时间的推移降低系统性能。 有关 SQL Server 代理的详细信息作业 BizTalk Server 提供了有助于管理 BizTalk Server 数据库，请参阅[数据库结构和作业](http://go.microsoft.com/fwlink/p/?LinkID=153451)(http://go.microsoft.com/fwlink/p/?LinkID=153451)。|  
|确保负责备份 BizTalk Server 数据库的 SQL Server 作业正在正常运行 （管理检查）。|-   [如何配置备份 BizTalk Server 作业](http://go.microsoft.com/fwlink/p/?LinkID=153813)(http://go.microsoft.com/fwlink/p/?LinkID=153813)<br />-   [如何安排备份 BizTalk Server 作业](http://go.microsoft.com/fwlink/p/?LinkId=154674)(http://go.microsoft.com/fwlink/p/?LinkId=154674)|  
|确保已安装最新的安全更新 （安全检查）。|在 Microsoft 更新站点[http://update.microsoft.com/microsoftupdate/v6/default.aspx](http://update.microsoft.com/microsoftupdate/v6/default.aspx)|  
|分析每周的性能监视针对基线和阈值 （性能检查） 的日志。|-   [使用日志 (PAL) 工具的性能分析](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)<br />-   [故障排除性能 Issues3](../technical-guides/troubleshooting-performance-issues3.md)|  
|确保系统不会遇到频繁地自动增长增量 BizTalk Server 数据库 （性能检查）。|-   [定义数据库的自动增长设置](../technical-guides/defining-auto-growth-settings-for-databases.md)<br />-   [跟踪数据库大小准则](http://go.microsoft.com/fwlink/p/?LinkId=154677)(http://go.microsoft.com/fwlink/p/?LinkId=154677)。<br />-   [标识数据库层中的瓶颈](http://go.microsoft.com/fwlink/p/?LinkId=154678)(http://go.microsoft.com/fwlink/p/?LinkId=154678)。<br />-   [数据库文件初始化](http://go.microsoft.com/fwlink/p/?LinkID=101579)(http://go.microsoft.com/fwlink/p/?LinkID=101579)。<br />-   [执行 SQL Server 维护过程](~/technical-guides/checklist-configuring-sql-server.md)|  
|在高负载，以检查长的响应时间和较高资源使用率 （性能检查） 过程中运行 SQL Server 事件探查器。|[使用 SQL Server 事件探查器](http://go.microsoft.com/fwlink/p/?LinkID=106720)(http://go.microsoft.com/fwlink/p/?LinkID=106720)。|  
|确保消息批处理的所有适配器是适用于资源消耗或延迟 （性能检查）。|-   [配置批处理，以便提高适配器性能](../technical-guides/configuring-batching-to-improve-adapter-performance.md)<br />-   [如何设计的高性能适配器](http://go.microsoft.com/fwlink/p/?LinkId=154679)(http://go.microsoft.com/fwlink/p/?LinkId=154679)。|  
|请确保大型消息阈值适当的资源消耗 （性能检查）。|[BizTalk Server 如何处理大消息](http://go.microsoft.com/fwlink/p/p/?LinkId=154680)(http://go.microsoft.com/fwlink/p/p/?LinkId=154680)。|  
|将备份文件存档，并指定合适的计算机进行备份|若要避免潜在的数据丢失，应指定计算机为不同于计算机的原始数据，以及你备份\<目标路径\>应指定要存储数据库日志是不同的计算机从原始的数据库日志的计算机。<br /><br /> 有关备份的最佳实践的详细信息，请参阅[Backing Up and Restoring Databases 的最佳实践](http://go.microsoft.com/fwlink/p/p/?LinkID=151391)(http://go.microsoft.com/fwlink/p/p/?LinkID=151391)。|  
  
## <a name="see-also"></a>另请参阅  
 [例程监视任务](../technical-guides/routine-monitoring-tasks.md)