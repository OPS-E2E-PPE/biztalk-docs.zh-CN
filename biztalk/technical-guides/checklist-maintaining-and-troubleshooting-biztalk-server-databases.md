---
title: 清单：维护和故障排除 BizTalk Server 数据库 |Microsoft Docs
description: 请参阅帮助维护你的 BizTalk Server 数据库，包括自动更新统计信息，最大并行度，请重新生成索引的最佳做法、 查找锁和块，检查数据库的大小，使用跟踪、 启用 SQL Server 代理作业、 检查挂起的实例，并检查磁盘性能。 有关 BizTalk 终止符工具还读取。
ms.custom: ''
ms.date: 06/11/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58931faf-fc84-46fe-8359-506da94c3756
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a52e16eb86215ca977ff05b87a3c1baf556b0982
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65294803"
---
# <a name="checklist-maintaining-and-troubleshooting-biztalk-server-databases"></a>清单：维护和故障排除 BizTalk Server 数据库
BizTalk Server 数据库和它们的运行状况对于成功的 BizTalk Server 数据库邮件环境而言非常重要。 本主题列出了维护或故障排除 BizTalk Server 数据库时必须遵循的步骤。  
  
-   [维护 BizTalk Server 数据库](../technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md#BKMK_MaintainDB)  
  
-   [BizTalk Server 数据库进行故障排除](../technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md#BKMK_Troubleshoot)  
  
<a name="BKMK_MaintainDB"></a>   
## <a name="maintaining-biztalk-server-databases"></a>维护 BizTalk Server 数据库  
  
|步骤|参考|  
|---|---|  
|禁用**自动更新统计信息**并**自动创建统计信息**选项 （仅适用于 BizTalk Server MessageBox 数据库）。 | **注意：** 默认情况下为 BizTalk Server 配置的一部分完成这些设置。 不应该对这些设置进行更改。 <br/><br/> 若要查看这些设置将被禁用，请在 SQL Server 中执行以下存储的过程：<br/><br/> SELECT DATABASEPROPERTYEX('BizTalkMsgBoxDB', 'IsAutoCreateStatistics') AS IsAutoCreateStatistics<br/>SELECT DATABASEPROPERTYEX('BizTalkMsgBoxDB', 'IsAutoUpdateStatistics') AS IsAutoUpdateStatistics<br/><br/>返回的值应为**0**以指示设置处于禁用状态。 如果**0**是未返回，通过执行以下命令在 SQL Server 中禁用该设置：<br/><br/>ALTER DATABASE BizTalkMsgBoxDB SET AUTO_CREATE_STATISTICS OFF<br/>ALTER DATABASE BizTalkMsgBoxDB SET AUTO_UPDATE_STATISTICS OFF<br/><br/> 有关这些设置的详细信息，请参阅：<br/><br/> -   **917845**—["你遇到阻止，当您尝试连接到 BizTalk Server 中在 BizTalkMsgBoxDb 数据库死锁条件或其他 SQL Server 问题"](http://go.microsoft.com/fwlink/?LinkId=153429)<br />-   **912262**—["自动更新统计信息选项的自动创建统计信息选项和作为 BizTalk Server BizTalkMsgBoxDB 数据库宿主的 SQL Server 数据库实例中关闭的并行度设置"](http://go.microsoft.com/fwlink/?LinkId=153430)|  
|设置最大并行度属性|**注意：** 默认情况下为 BizTalk Server 配置的一部分完成这些设置。 不应该对这些设置进行更改。 <br /><br /> 设置最大并行度**run_value**并**config_value**值一 (1) 上承载 BizTalk Server Messagebox 数据库的 SQL Server 实例的属性。 若要检查最大并行度设置，请执行以下存储过程针对主 SQL Server 数据库中：<br /><br /> exec sp_configure 'max degree of parallelism'<br /><br /> 如果**run_value**并**config_value**是未设置为值一 (1)，在 SQL Server 中执行以下存储的过程：<br /><br /> exec sp_configure 'max degree of parallelism'、 '1' 的重新配置的重写<br /><br /> 最大并行度设置如何影响 BizTalk Server 的详细信息，请参阅以下 Microsoft 知识库文章：<br /><br /> -   **899000**—["配置 BizTalk Server 时的 SQL server 实例的并行度设置"](http://go.microsoft.com/fwlink/?LinkId=153432) (http://go.microsoft.com/fwlink/?LinkId=153432)。<br />-   **917845**—["你遇到阻止，死锁条件或其他 SQL Server 问题，当您尝试连接到 BizTalk Server 中在 BizTalkMsgBoxDb 数据库"](http://go.microsoft.com/fwlink/?LinkId=153429) (http://go.microsoft.com/fwlink/?LinkId=153429)。|  
|确定当重新生成 BizTalk Server 索引|群集化大部分 BizTalk Server 数据库中的索引 (索引 ID:1). DBCC SHOWCONTIG 命令可以用于显示 BizTalk Server 数据库中表的碎片信息。 这些索引是基于 GUID 的是正常的碎片发生。 DBCC SHOWCONTIG 的扫描密度值是否小于 30%，可以在停机期间重新生成索引。 在 BizTalk Server 数据库中的多个表包含使用数据类型定义不能执行联机索引的列。 因此，BizTalk Server 数据库中的表应永远不会重新生成索引时 BizTalk 正在处理的数据。 有关如何重新生成 BizTalk 索引的详细信息，请参阅以下 Microsoft 知识库文章：<br /><br /> -   **917845**—["你遇到阻止，死锁条件或其他 SQL Server 问题，当您尝试连接到 BizTalk Server 中在 BizTalkMsgBoxDb 数据库"](http://go.microsoft.com/fwlink/?LinkId=153429) (http://go.microsoft.com/fwlink/?LinkId=153429)。<br /><br /> **注意：** Sys.dm_db_index_physical_stats 函数还可用于查找 SQL Server 中的碎片信息。 有关详细信息，请参阅[sys.dm_db_index_physical_stats (TRANSACT-SQL)](https://docs.microsoft.com/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql)。|  
|监视数据库的锁、 块或死锁|它是锁和块以使用 BizTalk Server 的 SQL Server 数据库上发生的预期的行为。 但是，它不需要具有这些锁或要持续长时间内的块。 扩展阻塞和死锁的 SQL Server 使用的 BizTalk Server 数据库进行的潜在问题的指示器。 当前的已知原因死锁和阻止在 BizTalk Server 使用的 SQL Server 数据库上，查看以下 Microsoft 知识库文章：<br /><br /> -   **917845**—["你遇到阻止，死锁条件或其他 SQL Server 问题，当您尝试连接到 BizTalk Server 中在 BizTalkMsgBoxDb 数据库"](http://go.microsoft.com/fwlink/?LinkId=153429) (http://go.microsoft.com/fwlink/?LinkId=153429)。|  
|监视数据库和表的大小|BizTalk Server Messagebox 数据库的大小通常应不超过大约为 5 GB。  在 BizTalkMsgBoxDb 数据库不应包含任何数据，并应被视为一个缓冲区，直到处理或移至 BizTalkDTADb 数据库数据。 具有一个功能强大的 SQL Server 后端以及大量长时间运行的业务流程的环境可能具有 BizTalkMsgBoxDb 数据库大小超过 5 GB。 任何长时间运行的业务流程的大容量环境应具有 BizTalk Server Messagebox 数据库远小于 5 GB。 BizTalk Server 跟踪数据库可能大不相同的大小，但如果查询性能会显著降低，然后跟踪数据库可能是太大。 根据经验，BizTalk Server 跟踪数据库大小超过 15 到 20 GB 被视为太大，可能会对性能产生不利影响。 以下问题可能是由 BizTalk Server 数据库过大引起：<br /><br /> BizTalk Server Messagebox 数据库会不断增大时 （而不仅仅是日志文件） 的数据大小仍然很大。 BizTalk Server 需要更长的时间比平时要处理甚至简单的消息流方案。<br />组中心查询需要比平时更长时间，可能甚至会超时。<br />-数据库日志文件永远不会被截断。<br />-BizTalk SQL 代理作业运行速度慢于正常运行。<br />-某些表是相当大或过多的行比较正常状态。<br /><br /> BizTalk Server 数据库会变得大几个原因：<br /><br /> BizTalk SQL 代理作业未运行<br />-过多挂起的消息或服务实例<br />-磁盘故障<br />的高级别的跟踪<br />BizTalk 服务器的限制<br />的 SQL Server 性能不佳<br />-网络延迟问题<br /><br /> 同样，您可以在表中具有过多的行。 没有任何组过多的行数。 此外，此数量的行的表中存储的数据类型而异。 例如， *dta_DebugTrace*可能有超过 1 百万个行的表具有过多的行。 一个*HostNameQ_Suspended*可能具有多个 200,000 个行的表具有过多的行。<br /><br /> 请确保您知道预期在您的环境来确定是否发生数据问题。|  
|启用 BizTalk Server 主机上的跟踪|默认情况下，默认主机上启用跟踪。 BizTalk 要求**允许主机跟踪**检查一台主机上的选项。 跟踪数据解码服务 (TDDS) 启用跟踪后，将跟踪移动到 BizTalk Server 跟踪数据库的事件数据从 BizTalk Server Messagebox 数据库。 如果没有 BizTalk Server 主机配置为具有选项**允许主机跟踪**或如果跟踪主机已停止，则 TDDS 将不会运行并且 BizTalk Server Messagebox 数据库中的 TrackingData_x_x 表将增长未选中状态。 因此，应将专用的 BizTalk Server 主机配置选项**允许主机跟踪**。 有关配置专用的跟踪主机的详细信息请参阅[配置专用跟踪主机](~/technical-guides/configuring-a-dedicated-tracking-host.md)。 **注意：** 若要允许 TDDS 维护在大容量方案中的新跟踪事件，可以创建一个跟踪主机的多个实例，但不是超过一台主机应该配置对其进行跟踪。|  
|使用正确的 BizTalk SQL Server 代理作业|BizTalk Server SQL 代理作业的执行是用于管理 BizTalk Server 数据库以及保持最佳性能至关重要。<br /><br /> -**备份 BizTalk Server** SQL Server 代理作业是唯一受支持的方法，BizTalk Server 数据库备份。 此作业需要将所有 BizTalk Server 数据库都设置为使用完整恢复模式。 你应配置 BizTalk Server 环境中正常运行此作业。 SQL Server 方法可用于备份 BizTalk Server 数据库，只有 SQL Server 服务已停止，并且所有 BizTalk Server 进程已都停止。 **注意：**     有关配置 SQL 代理备份 BizTalk Server 作业时使用 SQL Server 完整恢复模式的详细信息，请参阅[日志传送](http://go.microsoft.com/fwlink/?LinkId=153450)(http://go.microsoft.com/fwlink/?LinkId=153450)或[备份完整恢复模式下的](http://go.microsoft.com/fwlink/?LinkId=156509)(http://go.microsoft.com/fwlink/?LinkId=156509).<br />- **MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb**旨在无限期地运行 SQL Server 代理作业。 因此 SQL 代理作业历史记录可能不表示此 SQL 代理作业已成功完成;此行为是默认设置。 如果故障，该作业将在 1 分钟内重新启动并继续运行减弱。 因此，通常可以忽略此作业的失败通知。 如果 MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb SQL Server 代理作业的作业历史记录指示是不断失败并重新启动此作业的失败/重新启动循环的原因的进一步调查可能需要。<br />- **MessageBox_Message_Cleanup_BizTalkMsgBoxDb** SQL Server 代理作业是唯一不应手动启用因为它由 MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb 作业启动的作业。<br />- **DTA 清除和存档**SQL Server 代理作业通过清除和存档跟踪的消息来维护 BizTalk Server 跟踪数据库。 此作业读取表中的每一行，并将每个行，以确定是否应删除该记录的时间戳进行比较。 **注意：** 故障排除时 BizTalk Server SQL Server 代理作业，请验证 MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb 除外的所有 SQL 代理作业都完成未出现错误。 <br /><br /> 有关在 SQL Server 中使用 BizTalk Server SQL 代理作业的详细信息：<br /><br /> -请参阅[数据库结构和作业](http://go.microsoft.com/fwlink/?LinkId=153451)(http://go.microsoft.com/fwlink/?LinkId=153451)。<br />-请参阅[在 BizTalk Server 中的说明的 SQL Server 代理作业](http://go.microsoft.com/fwlink/?LinkId=153452)(http://go.microsoft.com/fwlink/?LinkId=153452)。|  
|监视和终止挂起的实例|服务实例可能已挂起 （可恢复） 或挂起 （不可恢复）。 这些服务实例可以是消息传送、 业务流程或端口。 BizTalk Server 通过使用组中心页，在 BizTalk Server 管理控制台或通过使用 Terminate.vbs 脚本将要终止和删除这些实例。 有关 Terminate.vbs 脚本的详细信息，请参阅[删除挂起的服务实例](http://go.microsoft.com/fwlink/?LinkId=153453)(http://go.microsoft.com/fwlink/?LinkId=153453)。 **提示：** 终止符工具还可用于删除挂起的实例。 [终止符工具](http://go.microsoft.com/fwlink/?LinkId=151931)位于[ http://go.microsoft.com/fwlink/?LinkId=151931 ](http://go.microsoft.com/fwlink/?LinkId=151931)。 使用此工具不受 Microsoft，因此 Microsoft 不保证此程序的适用性。 使用此程序是完全由您自己承担。 <br /><br /> 术语"孤立"和"僵尸电脑"通常互换使用。 孤立或僵停消息是不具有关联的服务实例，通常由于服务实例已终止之前收到了消息的消息。 孤立或僵停服务是一种服务，没有任何关联的消息。 请参阅有关僵停消息和服务的详细信息了解在 BizTalk Server 中的实例[BizTalk Server 中的僵停](http://go.microsoft.com/fwlink/?LinkId=153454)(http://go.microsoft.com/fwlink/?LinkId=153454)。|  
|监视的性能计数器**PhysicalDisk**性能对象|BizTalk Server 在一分钟内对 SQL 服务器发出大量的较短的非常快速的事务。 如果 SQL Server 不能承受此活动，可能会遇到 BizTalk Server 性能问题。 监视器**avg.Disk sec/Read**， **avg.Disk sec/Transfer**，和**avg.Disk sec/Write**中的性能监视器计数器**PhysicalDisk**性能对象。 最佳值是小于 10 毫秒 （毫秒）。 一个或更大的 20 毫秒的值被视为性能不佳。<br /><br />-对于 BizTalk Server 数据库的高可用性的详细信息，请参阅[的 BizTalk Server 数据库提供高可用性](../core/providing-high-availability-for-biztalk-server-databases.md)。|  
|执行 BizTalk Server 数据库的最佳方案。|请参阅[维护 BizTalk Server 数据库的最佳实践](~/technical-guides/best-practices-for-maintaining-biztalk-server-databases.md)。|  
  
<a name="BKMK_Troubleshoot"></a>   
## <a name="troubleshooting-biztalk-server-databases"></a>BizTalk Server 数据库进行故障排除  
 执行以下任务来排查与 BizTalk Server 数据库的任何问题。  
  
|步骤|参考|  
|-----------|---------------|  
|确保所有必需的 BizTalk SQL Server 代理作业已启用并正在运行|所有 BizTalk SQL Server 代理都作业除外**MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb**作业应已成功为启用并正在运行。 请勿禁用任何其他作业。<br /><br /> 如果发生故障，使用**查看历史记录**查看错误信息，并相应地进行解决失败的 SQL Server 中的选项。 请记住， **MessageBox _Message_ManageRefCountLog_BizTalkMsgBoxDb** SQL Server 代理作业将无限期运行。 因此，您只应考虑如果作业历史记录报告的作业不断失败并重新启动。|  
|使用 MsgBoxViewer 工具来分析 BizTalk MessageBox 和其他数据库|**重要提示：** 使用此工具不受 Microsoft，因此 Microsoft 不保证此程序的适用性。 使用此程序是完全由您自己承担。 <br /><br /> MsgBoxViewer 工具是可从[ http://go.microsoft.com/fwlink/?LinkId=151930 ](http://go.microsoft.com/fwlink/?LinkId=151930) (http://go.microsoft.com/fwlink/?LinkId=151930)。 MsgBoxViewer 工具可用于故障排除，因为它提供了 HTML 报表，其中提供了详细表的大小和行计数信息。 报表还可以帮助确定是否限制 BizTalk Server。 此外，该工具提供了 BizTalk Server 数据库和 BizTalk Server 配置的快照。<br /><br /> 当 BizTalk Server 运行时比平常慢，运行 MsgBoxViewer 工具中，单击在上选择的所有查询**可选查询**选项卡，然后查看生成的 HTML 报告的任何问题。 **摘要报表**部分列出了中以红色的黄色和潜在问题的警告。<br /><br /> 此外，可以使用 MsgBoxViewer 工具来确定哪些表的最大，并且具有大多数记录。 通常发展中的表的列表以及有关如何管理这些表的说明，请参阅[不断增长的大型 BizTalk Server 数据库表](~/technical-guides/large-growing-biztalk-server-database-tables.md)。|  
|使用终结器工具来解决问题，如果任何，标识由 MsgBoxViewer 工具|**重要提示：** 使用此工具不受 Microsoft，因此 Microsoft 不保证此程序的适用性。 使用此程序是完全由您自己承担。 <br /><br /> 运行终结器工具，网址[终止符](http://go.microsoft.com/fwlink/?LinkId=151931)(http://go.microsoft.com/fwlink/?LinkId=151931)。 此工具使用户能够轻松地解决由 BizTalk MsgBoxViewer 工具标识的任何问题。 有关如何与 BizTalk MsgBoxViewer 工具集成终止符工具的详细信息，请参阅[使用 BizTalk 终止符，以解决问题由 BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932) (http://go.microsoft.com/fwlink/?LinkId=151932)。|  
|调查死锁方案|在死锁方案中，启用 SQL Server 上的 DBCC 跟踪死锁信息写入到 SQLERROR 日志。<br /><br /> 在 SQL Server 中，执行以下语句以启用对死锁情况的 DBCC 跟踪：<br /><br /> DBCC TRACEON (1222，-1)<br /><br /> 您还可以使用 PSSDIAG 实用工具上收集数据**Lock: Deadlock**事件并**Lock: Deadlock Chain**事件。 有关 PSSDIAG 实用工具的详细信息，请参阅[PSSDIAG 数据收集实用程序](http://go.microsoft.com/fwlink/?LinkId=153627)(http://go.microsoft.com/fwlink/?LinkId=153627)。<br /><br /> 在 BizTalkMsgBoxDB 数据库是大容量和高事务的联机事务处理 (OLTP) 数据库。 使用此类数据库中，某些死锁，但此死锁由 BizTalk Server 引擎在内部处理。 在这种情况，在错误日志中不列出了任何错误。 当研究死锁情况时，必须与事件日志中的死锁错误相关正在调查的输出中死锁。|  
|查找阻塞的进程|可以使用 SQL Server 中的活动监视器获取锁定的系统进程的服务器进程标识符 (SPID)。 然后，可以运行 SQL Profiler，以确定在锁定 SPID 中执行的 SQL 语句。 PSSDIAG 实用工具可用于对 SQL Server 中的锁定和阻塞问题进行故障排除。 该实用工具捕获具有阻止脚本已启用的所有 TRANSACT-SQL 事件。 有关 PSSDIAG 实用工具的详细信息，请参阅[PSSDIAG 数据收集实用程序](http://go.microsoft.com/fwlink/?LinkId=153627)(http://go.microsoft.com/fwlink/?LinkId=153627)。<br /><br /> 在 SQL Server，您可以指定**阻塞的进程阈值**设置，以确定时间超过指定阈值时阻塞 SPID 或 Spid 的进程。 Blocked 的 process threshold 选项的详细信息，请参阅[阻塞的进程阈值选项](http://go.microsoft.com/fwlink/?LinkId=153628)(http://go.microsoft.com/fwlink/?LinkId=153628)。 **注意：** 遇到锁定时或在 SQL Server 中的存在阻塞性问题，我们建议你与 Microsoft 客户支持服务联系。 Microsoft 客户支持服务可以帮助你配置了正确的 PSSDiag 实用程序选项。|  
|删除所有不需要的数据|如果数据库已成熟到可以变得太大，并且在数据库中包含的数据将不需要过更长，首选的方法是删除数据。 **注意：** 不要使用此方法在任何环境中数据的业务关键或如果需要的数据。 <br /><br /> **若要清除 BizTalkMsgBox 数据库**<br /> 1.下载并安装在该终结器工具[Biztalk 终止符](http://go.microsoft.com/fwlink/?LinkId=220869)(http://go.microsoft.com/fwlink/?LinkId=220869)。<br />2.按照本主题中的步骤[如何从 MessageBox 数据库的测试环境中手动清除数据](http://go.microsoft.com/fwlink/?LinkID=158064)(http://go.microsoft.com/fwlink/?LinkID=158064) BizTalk MessageBox 数据库中创建 bts_CleanupMsgbox 存储过程。<br />3.使用终止符工具执行 bts_CleanupMsgbox 存储过程，并清除 BizTalk MessageBox 数据库。 警告：    不要运行 BizTalk Server 在生产服务器上运行 bts_CleanupMsgbox 存储过程。 只应在测试环境中运行 bts_CleanupMsgbox 存储过程。 不支持运行 bts_CleanupMsgbox 存储的过程在生产环境中。<br />4.重新启动所有主机和 BizTalk Server 服务。<br /><br /> **若要清除 BizTalkDTADb 数据库**<br /> <ul><li>**方法 1**<br /><br /> <ol><li>备份所有 BizTalk Server 数据库。</li><li>执行**dtasp_PurgeAllCompletedTrackingData**存储过程。 有关该存储过程的详细信息，请参阅[如何从 BizTalk 跟踪数据库手动清除数据](http://go.microsoft.com/fwlink/?LinkId=153635)(http://go.microsoft.com/fwlink/?LinkId=153635)。</li></ol></li><li>**方法 2**。 仅当 BizTalkDTADb 数据库包含多个未完成的实例，则必须删除使用此选项。<br /><br /> <ol><li>备份所有 BizTalk Server 数据库。</li><li>停止所有 BizTalk 主机、 服务和自定义独立的适配器。 如果使用 HTTP 或 SOAP 适配器后，重新启动 IIS 服务。</li><li>执行**dtasp_CleanHMData** BizTalkDTADb 数据库中存储过程。</li><li>重新启动所有主机和 BizTalk Server 服务。</li></ol></li></ul> **注意：** 如果必须必须跟踪数据，备份 BizTalkDTADb 数据库中，将数据库还原到另一个 SQL Server，，然后清除原始 BizTalkDTADb 数据库。|  
  
 如果需要分析 MsgBoxViewer 数据或 PSSDIAG 输出的帮助，请联系 Microsoft 客户支持服务。 请联系客户支持服务部门之前，压缩 MsgBoxViewer 数据、 PSSDIAG 输出和已更新的事件日志 （.evt 文件）。 您可能需要将发送这些文件复制到 BizTalk Server 支持工程师。
  
## <a name="next"></a>Next
  
-   [维护 BizTalk Server 数据库的最佳做法](~/technical-guides/best-practices-for-maintaining-biztalk-server-databases.md)  
  
-   [大量增长的 BizTalk Server 数据库表](~/technical-guides/large-growing-biztalk-server-database-tables.md)  
  
-   [用于故障排除的工具和实用程序](../technical-guides/tools-and-utilities-for-troubleshooting.md)  
  
## <a name="see-also"></a>请参阅  
 [不可更改的 SQL Server 设置](~/technical-guides/sql-server-settings-that-should-not-be-changed.md)
