---
title: 什么是可维持性能？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- reliability, sustainable performance
- performance, goals
- performance, sustainable performance
- planning, performance
- performance, planning
- sustainable performance
ms.assetid: 4b18b976-7714-431f-8976-f40a1016d5f3
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a15c0d8d58e263d6c78b8b7f899a00296f70bad0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250205"
---
# <a name="what-is-sustainable-performance"></a>什么是可维持性能？
在规划和估计系统可持续发展，从长远来说会想到可持续发展至关重要。 主要考虑因素是：  
  
- **负载状况和性能目标**:对于负载状况和性能目标时，不能具有过多的详细信息。 能够处理这些负载从长远来看，将基于测试和准备情况认证。  
  
- **其他活动和争用系统资源的进程**:它不是几乎消息负载。 有其他进程，如数据库维护和 MessageBox 查询的性能影响的服务器上发生的活动。  
  
- **计划内和计划外的系统服务中断和停机时间**:水闸事件和消息积压工作可以更改的有效负载配置文件。  
  
  时考虑构建可承受的系统并执行测试以验证它们，请务必考虑以下因素帐户并为它们的计划。  
  
## <a name="is-your-performance-sustainable"></a>是可承受性能？  
 在讨论的性能时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，我们定义最大可承受性能，如下所示：  
  
- 最高的系统可以无限期地处理在生产环境中的消息通信负载。  
  
  这种方法看似简单，有许多评估-一组特定的硬件上运行的解决方案将能够支持解决方案投入生产后遇到一天中的而且每天在加载时必须考虑的因素。  
  
  你的解决方案投入生产之前，请考虑以下因素以评估是否在该解决方案可无限制处理最高消息通信负载：  
  
- 所需的性能目标和吞吐量/延迟状况。  
  
- 如在同一硬件上运行的其他进程：  
  
  -   正常的监视和故障排除  
  
  -   操作数据库维护，例如日志传送、 备份、 清除、 索引维护和更新统计信息更新。  
  
  -   其他应用程序  
  
- 计划内和计划外的系统停用，例如：  
  
  -   合作伙伴站点中断，阻止发送或接收消息  
  
  -   常规系统维护停机时间  
  
## <a name="know-your-performance-goals"></a>知道您的性能目标  
 您可以评估你的解决方案的可维持性之前，必须具有预期的生产负载的详细的知识。 不明确的目标的情况下无法评估准备情况。 一组格式正确的性能目标非常重要，因为它能使您的策略以系统测试和认证。 性能目标应包含以下元素：  
  
-   将性能定义的函数的时间为一条曲线。 这些函数的范围可以从极其简单到非常复杂。  
  
-   性能要求，与性能函数相关联。  
  
-   文件大小和类型的分布。  
  
### <a name="example-1"></a>示例 1  
  
-   每一天，消息累积 0 的消息数/秒在上午 8:00 到 80 每秒在中午，然后晚上 9:00，大致钟形曲线的形式返回到 0 的消息数/秒。  
  
-   系统具有每个消息没有具体的延迟要求，但它必须能够处理此负载，以及所有前一天的消息负载 （例如，24 小时系统中断时） 而不获取。  
  
-   有三种文档类型：销售篮、 延期交货和库存请求。 销售篮文档范围之间 2 到 10 个千字节为单位的大小，构成了在任何给定时间消息数的 75%。 后的订单和库存请求文档的大小接近 1 千字节始终是和构成了剩余的 10%和 15%的消息计数在任何给定时间分别。  
  
### <a name="example-2"></a>示例 2  
  
-   在每天午夜，一批 500,000 条消息到达时进行处理。  
  
-   必须在 8 小时内完成处理批中的所有消息。  
  
-   所有消息的相同类型和 10 到 50 个千字节为单位，非独占之间均匀分布。 此外，批处理始终包含 10 个目录类型消息的 10 兆字节每个必须再细分为单独的目录条目进行处理。  
  
### <a name="example-3"></a>示例 3  
  
-   上午 8:00，每天早上 4000 客户服务代表登录的交互式系统并执行，一般情况下，每个代表每分钟到下午 5:00，每周 7 天的结束时间的 4 个查询。  
  
-   所有查询必须在 2 秒内都返回的结果。  
  
-   所有查询具有相同的类型和大小，非独占 500 到 1000年个字节之间均匀分布。  
  
#### <a name="a-performance-requirement-associated-with-the-performance-function"></a>与性能函数相关联的性能要求  
 继续上面的示例：  
  
-   **示例 1 （续）**:系统具有每个消息没有具体的延迟要求，但它必须能够处理此负载，以及所有前一天的消息负载 （如 24 小时系统中断时） 而不获取。  
  
-   **示例 2 （续）**:必须在 8 小时内完成处理批中的所有消息。  
  
-   **示例 3 （续）**:所有查询必须在 2 秒内都返回的结果。  
  
#### <a name="a-distribution-of-file-sizes-and-types"></a>文件大小和类型的分发  
  
-   **示例 1 （续）**:有三种文档类型：销售篮、 延期交货和库存请求。 销售篮文档范围之间 2 到 10 个千字节为单位的大小，构成了在任何给定时间消息数的 75%。 后的订单和库存请求文档的大小接近 1 千字节始终是和构成了剩余的 10%和 15%的消息计数在任何给定时间分别。  
  
-   **示例 2 （续）**:所有消息的相同类型和 10 到 50 个千字节为单位，非独占之间均匀分布。 此外，批处理始终包含 10 个目录类型消息的 10 兆字节每个必须再细分为单独的目录条目进行处理。  
  
-   **示例 3 （续）**:所有查询具有相同的类型和大小，非独占 500 到 1000年个字节之间均匀分布。  
  
## <a name="accounting-for-other-processes"></a>其他进程记帐  
 除了直接通过 BizTalk 引擎传递了负载配置文件，始终有争用资源的相同硬件上的其他进程中。  这些其他进程将减少系统的整体可维持性能功能。 数据库维护可能是进程的这种类型的最常见示例。  
  
 每个数据库，大或小，需要定期操作维护，例如日志传送、 备份、 存档和清除。 监视和故障排除操作必须考虑到帐户时定义和认证的新增可承受的其他示例。 例如，查询 （例如，通过管理控制台上组中心页） MessageBox，以查看过去 24 小时内已挂起消息数给定类型的要求可能否则使用的 SQL 服务器中的资源处理消息。  
  
 下面是一系列活动，通常具有很大影响上中的整体可维持性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
- **日志传送和备份**。 为大多数灾难恢复的一部分计划涉及 SQL Server，您必须执行日志传送和备份定期的所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组数据库。 有关详细信息，请参阅[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)。 另请参阅[日志传送](../core/log-shipping.md)。  
  
- **存档和清除跟踪数据**。 除了整体日志传送和备份计划，BizTalk 跟踪 (BizTalkDTADb) 数据库具有自己的存档和清除策略;有关详细信息，请参阅[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)。 速度的数据可以存档和清除 BizTalk 跟踪数据库中是因为尤其重要，清除 BizTalk 跟踪数据库的通常是瓶颈跟踪时正在使用中。  
  
- **系统查询**。 使用 Api 或 BizTalk Server 管理控制台 UI 对系统运行各种类型的查询将影响可维持性能。  
  
- **MessageBox 维护**。 有多种一部分的核心功能的 SQL 作业[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进行维护的清理工作消息和实例已完成处理的 MessageBox 数据库。 作为核心引擎的一部分，这些作业可完成的速度是衡量可维持性的关键因素。 有关这些作业及其角色的详细信息，请参阅[维护 BizTalk Server1](../core/maintaining-biztalk-server1.md)。  
  
- **解决方案部署活动**。 在部署时，绑定和启动新的应用程序或新版本的现有应用程序，额外的负载放置 BizTalk 例如对 MessageBox 数据库的新订阅的创建。 应用程序的部署后，正在处理的消息将争用资源，从而会影响现有应用程序的性能。  
  
  对于每个方面，需要要求：什么是建议这些活动的影响降至最低？ 例如，它们应打算在凌晨 3 点运行它们？  
  
## <a name="considering-planned-and-unplanned-outages"></a>考虑计划内和计划外中断  
 对系统性能的服务中断的影响将遇到服务中断，但最常用的后果是系统而异：  
  
- **水闸事件**。 当系统中断的某些时间的时间，消息可以构建，然后到达，一次性处理后的系统是再次正常工作。  例如，如果在 BizTalk 上运行的应用程序接收消息通过 MSMQ，并且段时间，该应用程序已关闭，消息累积等待选取队列中。 当再次启动该应用程序时，它是像大量消息到达"一次性全部。"  
  
- **消息积压工作**。 当消息发送到的系统已关闭，没有通常是一个重试周期所采用的使用的其他资源。 后重试周期用尽，则通常会挂起消息。 然后关闭的系统返回在一行，现在可以是大量的消息类型的水闸事件发生恢复和/或已成功发送。  
  
  当然，任何计划的中断，如定期计划维护必须纳入考虑范围设计和认证系统时。 此外建议考虑计划外的停机和它们的影响的分析。  
  
  标识类型的服务中断可能发生的最弱的顺序按预计风险级别 （即，概率乘以严重性），并估计持续时间和更高风险服务中断的影响 （例如，水闸事件、 挂起的消息量、 积压等）将指示所需的系统功能应发生在服务中断的位置。 任何存储转发、 基于消息的异步系统，如[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，应设计的将处理"余量"足以应对计划内和计划外停机。  
  
## <a name="see-also"></a>请参阅  
 [引擎持久性和持续性](../core/engine-persistence-and-durability.md)   
 [分阶段描述的项目规划建议](../core/project-planning-recommendations-by-phase.md)   
 [测量最大可承受引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [测量最大可承受跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [缩放你的解决方案](../core/scaling-your-solutions.md)   
 [确定性能瓶颈](../core/identifying-performance-bottlenecks.md)   
 [引擎性能和容量](../core/engine-performance-and-capacity.md)