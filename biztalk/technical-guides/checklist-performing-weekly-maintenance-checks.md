---
title: 清单：执行每周维护检查 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b13e43ba-4bac-4d4b-aaf8-46d60c0561bf
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 937d7976cf76a66131644a38ba057d44473e4984
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242651"
---
# <a name="checklist-performing-weekly-maintenance-checks"></a>清单：执行每周维护检查
本主题介绍在执行每周维护检查的可靠性、 管理、 安全性和性能所涉及的步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。  
  
|步骤|参考|  
|-----------|---------------|  
|请确保每个主机具有至少两个物理 BizTalk 服务器 （可靠性检查） 上运行的实例。|[BizTalk 主机的高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)|  
|确保每个接收位置是冗余的 （可靠性检查）。|[横向扩展接收主机](../technical-guides/scaling-out-receiving-hosts.md)|  
|确保 SQL Server 代理服务正在运行的 SQL server （管理检查） 上。|-   [如何：启动 SQL Server 代理](http://go.microsoft.com/fwlink/p/?LinkId=154672)(http://go.microsoft.com/fwlink/p/?LinkId=154672)。<br />-   [SQL Server 代理](http://go.microsoft.com/fwlink/p/?LinkId=106728)(http://go.microsoft.com/fwlink/p/?LinkId=106728)。|  
|确保与 BizTalk Server 相关的所有 SQL Server 作业都运行正常 （管理检查）。|[监视 SQL Server 代理作业](../technical-guides/monitoring-sql-server-agent-jobs.md)<br /><br /> 如果未运行 SQL Server 代理作业，将会随着时间的推移降低系统性能。 详细了解 SQL Server 代理作业的 BizTalk Server 提供用于管理 BizTalk Server 数据库，请参阅[数据库结构和作业](http://go.microsoft.com/fwlink/p/?LinkID=153451)(http://go.microsoft.com/fwlink/p/?LinkID=153451)。|  
|确保负责备份 BizTalk Server 数据库的 SQL Server 作业正在正常运行 （管理检查）。|-   [如何配置备份 BizTalk Server 作业](http://go.microsoft.com/fwlink/p/?LinkID=153813)(http://go.microsoft.com/fwlink/p/?LinkID=153813)<br />-   [如何安排备份 BizTalk Server 作业](http://go.microsoft.com/fwlink/p/?LinkId=154674)(http://go.microsoft.com/fwlink/p/?LinkId=154674)|  
|确保已安装最新安全更新 （安全检查）。|在 Microsoft Update 站点 [http://update.microsoft.com/microsoftupdate/v6/default.aspx](http://update.microsoft.com/microsoftupdate/v6/default.aspx)|  
|分析每周性能监视日志针对基线和阈值 （性能检查）。|-   [使用日志 (PAL) 工具的性能分析](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)<br />-   [故障排除性能 Issues3](../technical-guides/troubleshooting-performance-issues3.md)|  
|请确保系统不出现频繁地自动增长的 BizTalk Server 数据库 （性能检查）。|-   [定义数据库的自动增长设置](../technical-guides/defining-auto-growth-settings-for-databases.md)<br />-   [跟踪数据库的大小调整准则](http://go.microsoft.com/fwlink/p/?LinkId=154677)(http://go.microsoft.com/fwlink/p/?LinkId=154677)。<br />-   [标识数据库层的瓶颈](http://go.microsoft.com/fwlink/p/?LinkId=154678)(http://go.microsoft.com/fwlink/p/?LinkId=154678)。<br />-   [数据库文件初始化](http://go.microsoft.com/fwlink/p/?LinkID=101579)(http://go.microsoft.com/fwlink/p/?LinkID=101579)。<br />-   [执行 SQL Server 维护过程](~/technical-guides/checklist-configuring-sql-server.md)|  
|在高负载，以检查长时间响应时间和高资源使用率 （性能检查） 过程中运行 SQL Server Profiler。|[使用 SQL Server Profiler](http://go.microsoft.com/fwlink/p/?LinkID=106720) (http://go.microsoft.com/fwlink/p/?LinkID=106720)。|  
|请确保用于所有适配器的消息批处理是适用于资源消耗或延迟 （性能检查）。|-   [配置批处理以优化适配器性能](../technical-guides/configuring-batching-to-improve-adapter-performance.md)<br />-   [如何设计优异的适配器](http://go.microsoft.com/fwlink/p/?LinkId=154679)(http://go.microsoft.com/fwlink/p/?LinkId=154679)。|  
|确保大消息阈值适用于资源消耗 （性能检查）。|[BizTalk Server 如何处理大消息](http://go.microsoft.com/fwlink/p/p/?LinkId=154680)(http://go.microsoft.com/fwlink/p/p/?LinkId=154680)。|  
|备份文件存档，并指定合适的计算机进行备份|若要避免数据丢失，应指定一台计算机为不同于原始数据，以及的计算机的备份\<目标路径\>应指定要存储数据库日志是不同的计算机从与原始数据库日志的计算机。<br /><br /> 有关备份的最佳实践的详细信息，请参阅[备份和还原数据库的最佳实践](http://go.microsoft.com/fwlink/p/p/?LinkID=151391)(http://go.microsoft.com/fwlink/p/p/?LinkID=151391)。|  
  
## <a name="see-also"></a>请参阅  
 [例程监视任务](../technical-guides/routine-monitoring-tasks.md)