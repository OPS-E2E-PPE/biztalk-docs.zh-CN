---
title: "大型增长数据库表 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f30372f7-ab90-4ebb-9022-ac3ae3309459
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1253f57a38ea0658d15e536a4f7b614cc52aed7f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="large-growing-biztalk-server-database-tables"></a>大型增长 BizTalk Server 数据库表
下表列出[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通常增长最大的表。 可以使用此数据以确定其中可能存在的潜在问题。  

## <a name="tables-list"></a>表列表
|表|Description|注释|  
|-----------|-----------------|--------------|  
|*HostNameQ*_Suspended 表|此表包含与特定主机的挂起的实例关联的消息假脱机表中的引用。 此表是 BizTalkMsgBoxDb 数据库中。|如果*HostNameQ*_Suspended 表具有多个记录，表可以包含有效挂起的实例出现在**组中心数据库**页。 你可以终止这些实例。 如果这些实例不会出现在**组中心数据库**，实例可能缓存实例或孤立路由故障报告。 终止挂起的实例时，你清除此表中的项和假脱机和实例表中的其关联的行。|  
|*HostNameQ*表|此表包含对与特定主机相关联，并且不会挂起的消息假脱机表中的引用。 此表是 BizTalkMsgBoxDb 数据库中。|如果*HostNameQ*表具有多个记录，则可能存在以下类型的实例：<br /><br /> 已准备的运行实例<br />-活动实例<br />-已冻结实例<br /><br /> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]需要时间来"追赶"和处理实例。 此表可以增长时处理的传入速率 outpaces 传出处理速度。 这种情况下也可能导致大型 BizTalkDTADb 数据库或 SQL Server 磁盘延迟。|  
|假脱机、 部件，即和片段表|这些表 BizTalkMsgBoxDb 数据库中存储实际消息数据。|冻结，或挂起，具有多个记录意味着是大量消息的假脱机、 部件和片段表是当前处于活动状态。 根据大小、 的部分，数和这些表中的碎片设置，一条消息可能会生成所有这些表。 每个消息具有假脱机表中的恰好一个行和部件表中的至少有一行。|  
|实例表|此表存储 BizTalkMsgBoxDb 数据库中的所有实例和其当前状态。|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员不应允许多个已挂起的实例保持实例表中。 如果业务逻辑需要长时间运行业务流程，仅应保留多个已冻结的实例。 请记住，一个服务实例可能与假脱机表中的许多消息。|  
|TrackingData*_x_x*表|此表 BizTalkMsgBoxDb 数据库的跟踪数据解码服务 (TDDS) 将事件移到 BizTalkDTADb 数据库中存储的跟踪的事件。|如果 TrackingData_*x_x*表非常大，任一 TDDS 未运行或未成功运行。 如果 TDDS 正在运行，查看事件日志和 BizTalkDTADb 数据库中的错误信息中的 TDDS_FailedTrackingData 表。|  
|Tracking_Fragments*x*，Tracking_Parts*x*，Tracking_Spool*x*表|其中每个表的两个是 BizTalkMsgBoxDb 和 BizTalkDTADb 数据库中。 一个处于联机状态，并且另处于脱机状态。|**TrackedMessages_Copy_BizTalkMsgBoxDb** SQL Server 代理作业的跟踪的消息正文直接移到 BizTalkDTADb 数据库中的这些表。|  
|dta_ServiceInstances 表|此表的 BizTalkDTADb 数据库中存储服务实例的跟踪的的事件。|如果此表非常庞大，则可能大 BizTalkDTADb 数据库。|  
|dta_DebugTrace 表|此表的 BizTalkDTADb 数据库中存储的业务流程调试器事件。|如果 dta_DebugTrace 表具有多个记录，业务流程形状跟踪正在使用或正在使用。 如果业务流程调试不是常规操作所必需的则禁用跟踪所有业务流程的业务流程形状。 如果已禁用跟踪的业务流程形状并且 BizTalkMsgBoxDb 数据库中存在的积压工作，dta_DebugTrace 表可能会继续增大，因为 TDDS 继续将此数据移动到 dta_DebugTrace 表。<br /><br /> 若要控制 BizTalkDTADb 跟踪数据库的大小，你可以选择禁用全局跟踪。 请参阅[如何关闭全局跟踪](../core/how-to-turn-off-global-tracking.md)和[跟踪数据库大小准则](../core/tracking-database-sizing-guidelines.md)。|  
|dta_MessageInOutEvents 表|此表将跟踪的事件消息存储在 BizTalkDTADb 数据库。 这些跟踪的事件消息包括消息上下文信息。|如果 dta_DebugTrace 表和 BizTalkTrackingDb 数据库中的 dta_MessageInOutEvents 表来说太大，你可以在停止跟踪主机之后手动截断表。 有关说明如何截断表，请参阅中的"dta_DebugTrace table"详细信息[KB 952555： 如何维护和故障排除 BizTalk Server 数据库](https://support.microsoft.com/help/952555/how-to-maintain-and-troubleshoot-biztalk-server-databases)。|  
|dta_ServiceInstanceExceptions 表|此表 BizTalkDTADb 数据库中存储信息的任何挂起的服务实例时出错。|Dta_ServiceInstanceExceptions 表通常变大定期已挂起实例的环境中。|
