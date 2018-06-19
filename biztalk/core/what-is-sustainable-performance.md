---
title: 什么是可持续的性能？ |Microsoft 文档
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
ms.openlocfilehash: 276ce104d8667166d020b33b2f1fb4e7bfb98dbc
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "22290965"
---
# <a name="what-is-sustainable-performance"></a>什么是可持续的性能？
在规划和估计系统可持续性，考虑长远来看的可持续性至关重要。 主要考虑包括︰  
  
-   **加载配置文件和性能目标**︰ 时加载配置文件和性能目标，不能有太多的详细信息。 测试和准备情况的证书颁发将基于能够处理这些加载从长远来看。  
  
-   **其他活动和争用服务器资源的进程**︰ 并不只是关于消息负载。 有其他进程和对等数据库维护 MessageBox 查询的性能影响的服务器上发生的活动。  
  
-   **计划和非计划的系统服务中断和停机时间**: Floodgate 事件和积压工作可以更改的有效负载配置文件的消息。  
  
 在考虑生成可持续系统并执行测试以验证它们，请务必考虑以下因素帐户和它们的计划。  
  
## <a name="is-your-performance-sustainable"></a>是你的性能可持续？  
 当讨论性能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，我们定义最大可持续的性能，如下所示：  
  
-   系统可以无限期地处理在生产环境中的消息流量最高负载。  
  
 尽管这看起来简单，有许多评估-一组特定的硬件上运行的解决方案将能够支持解决方案投入生产后遇到一天而且每天在加载时必须考虑的因素。  
  
 在将解决方案投入生产前，请考虑以下因素以评估该解决方案是否可无限制处理最高消息通信负载：  
  
-   预期的性能目标和吞吐量/延迟状况。  
  
-   在同一硬件上运行的其他进程，例如：  
  
    -   常规监视和故障排除  
  
    -   操作数据库维护，例如日志传送、备份、清除、索引维护和统计信息更新。  
  
    -   其他应用程序  
  
-   计划内和计划外的系统停用，例如：  
  
    -   合作伙伴站点中断，阻止发送或接收消息  
  
    -   常规系统维护停机时间  
  
## <a name="know-your-performance-goals"></a>了解您的性能目标  
 您必须首先详细了解生产期望目标，然后才能评估解决方案的可维持性。 如果没有明确的目标，则无法评估准备情况。 一组设计良好的性能目标很关键，因为它能使您的策略以系统测试和系统证书为中心。 您的性能目标应包含以下要素：  
  
-   将性能定义为时间的函数的曲线。 这些函数可以非常简单，也可以非常复杂。  
  
-   与性能函数相关联的性能要求。  
  
-   文件大小和类型的分布。  
  
### <a name="example-1"></a>示例 1  
  
-   每天，消息从早上 8:00 的每秒 0 条消息逐渐增加到中午的每秒 80 条消息，然后在晚上 9:00 又回落到每秒 0 条消息，大体上为钟形曲线的形式。  
  
-   系统对每个消息没有具体的延迟要求，但它必须能够处理此负载，以及在不延期的情况下处理前一天的所有消息负载（例如，在发生 24 小时系统停用的情况下）。  
  
-   有三种文档类型：销售篮、延期交货订单和库存请求。 销售篮文档的大小介于 2 到 10 KB 之间，并且在任何给定时间都占消息数的 75%。 延期交货订单文档和库存请求文档的大小都始终在 1 KB 左右，在任何给定时间分别占剩余消息数的 10% 和 15%。  
  
### <a name="example-2"></a>示例 2  
  
-   每日午夜，一批 500,000 消息在到达进行处理。  
  
-   必须为 8 小时内完成处理批处理中的所有消息。  
  
-   所有消息均为相同类型和 10 到 50 千字节为单位，（含） 之间均匀分布。 此外，批处理始终包含 10 目录类型条消息，会 10 兆字节每个必须细分为单独的目录条目进行处理。  
  
### <a name="example-3"></a>示例 3  
  
-   在上午 8:00，每天早上 4000 客户服务代表登录到交互式系统和执行，一般情况下，每分钟至下午 5:00，每周 7 天的结束时间的代表每 4 的查询。  
  
-   所有查询必须在小于 2 秒内都返回结果。  
  
-   所有查询都是相同类型和大小，非独占 500 到 1000年个字节之间均匀分布。  
  
#### <a name="a-performance-requirement-associated-with-the-performance-function"></a>性能要求与性能函数相关联  
 继续上面的示例︰  
  
-   **示例 1 （续）**︰ 系统已为每个消息，没有特定的滞后时间要求，但它必须能够处理此负载，加上前一天的消息的所有加载 （例如、 发生时的 24 小时系统中断），而不获取。  
  
-   **示例 2 （续）**︰ 批处理中的所有消息必须都处理 8 小时内完成。  
  
-   **示例 3 （续）**︰ 所有查询必须在小于 2 秒内都返回结果。  
  
#### <a name="a-distribution-of-file-sizes-and-types"></a>文件大小和类型的分发  
  
-   **示例 1 （续）**︰ 有三种文档类型︰ 销售购物篮、 返回顺序和 Stock 请求。 销售篮文档的大小介于 2 到 10 KB 之间，并且在任何给定时间都占消息数的 75%。 延期交货订单文档和库存请求文档的大小都始终在 1 KB 左右，在任何给定时间分别占剩余消息数的 10% 和 15%。  
  
-   **示例 2 （续）**︰ 所有消息均为相同类型和 10 到 50 千字节为单位，（含） 之间均匀分布。 此外，批处理始终包含 10 目录类型条消息，会 10 兆字节每个必须细分为单独的目录条目进行处理。  
  
-   **示例 3 （续）**︰ 所有查询都是相同类型和大小，非独占 500 到 1000年个字节之间均匀分布。  
  
## <a name="accounting-for-other-processes"></a>其他进程的记帐  
 除了直接通过 BizTalk 引擎的负载配置文件，始终有争用资源的相同硬件上其他进程中。  这些其他进程将减少系统的整体可持续性能功能。 数据库维护可能是过程的最常见的这种类型的示例。  
  
 每个数据库，大或小，如需要操作的定期维护日志传送、 备份、 存档和清除。 监视和故障排除是你必须考虑到在定义并在认证要什么可持续时的操作的其他示例。 例如，查询 （例如，通过管理控制台组中心数据库页） MessageBox 若要查看过去 24 小时内已挂起的给定类型的消息数需要从 SQL Server 中无法否则已用于处理消息的资源。  
  
 下面是通常将具有最大影响总体可持续性中的活动的列表[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   **日志传送和备份**。 作为涉及 SQL Server 的大多数灾难恢复计划的一部分，您必须为所有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组数据库定期执行日志传送和备份。 有关详细信息，请参阅 [Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md)。 另请参阅[日志传送](../core/log-shipping.md)。  
  
-   **存档和清除跟踪数据**。 除了整体日志传送和备份计划，BizTalk 跟踪 (BizTalkDTADb) 数据库具有其自己存档和清除 regimes;有关详细信息，请参阅[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)。 在 BizTalk 跟踪数据库中存档和清除数据的速度尤其重要，因为在使用跟踪功能时这些操作通常会成为瓶颈。  
  
-   **系统查询**。 使用 Api 或 BizTalk Server 管理控制台用户界面对系统中运行各种类型的查询将会影响可持续的性能。  
  
-   **MessageBox 维护**。 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 核心功能中包含许多 SQL 作业，这些作业通过清除和管理已完成处理的消息和实例，对 MessageBox 数据库进行维护。 作为核心引擎的一部分，完成这些作业的速度是衡量可维持性的重要因素。 有关这些作业和其角色的详细信息，请参阅[维护 BizTalk Server1](../core/maintaining-biztalk-server1.md)。  
  
-   **解决方案部署活动**。 在部署、绑定和启动新应用程序或现有应用程序的新版本时，将会增加 BizTalk 的负载，例如对 MessageBox 数据库创建新的订阅。 部署应用程序后，正在处理的消息将争用资源，从而会影响现有应用程序的性能。  
  
 对于上述每个区域中，你需要询问︰ 什么是你的建议，这些活动的影响降至最低？ 例如，它们应打算凌晨 3 点运行它们？  
  
## <a name="considering-planned-and-unplanned-outages"></a>考虑计划内和计划外中断  
 中断对系统性能的影响将遇到服务中断，但是最常见的后果是系统而异︰  
  
-   **Floodgate 事件**。 系统关闭后，某些段时间，消息可以建立，然后可以在一次到达，处理后各系统都试功能。  例如，如果在 BizTalk 上运行的应用程序接收消息通过 MSMQ，并且该应用程序已关闭了一段时间，消息建立队列中等待拾取。 再次启动应用程序时，就像大量消息的到达"在一次。"  
  
-   **消息积压工作**。 当消息发送到的系统已关闭，没有通常是重试周期采用使用附加资源。 重试后已用尽周期，则消息通常将被挂起。 然后关闭的系统返回在行上，一种 floodgate 事件发生大量消息现在可在其中恢复和/或已成功发送。  
  
 当然任何计划内的停机 （如定期计划维护） 必须考虑到在设计和验证系统时。 建议的被认为是计划外的停机和其效果的分析。  
  
 通过标识可能发生的停用类型，按预计风险级别（即，概率乘以严重性）进行排序，并评估具有较高风险的停用情况的持续时间和影响（例如，水闸事件、挂起的消息量、积压等），可以指示发生停用情况时所需的系统性能。 任何存储转发、 基于消息的异步系统，如[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 应设计的将处理"空间"足以应对计划内和计划外停机。  
  
## <a name="see-also"></a>另请参阅  
 [引擎持久性和持久性](../core/engine-persistence-and-durability.md)   
 [项目规划阶段的建议](../core/project-planning-recommendations-by-phase.md)   
 [测量的最大可持续引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [测量的最大可持续跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [缩放您的解决方案](../core/scaling-your-solutions.md)   
 [识别性能瓶颈](../core/identifying-performance-bottlenecks.md)   
 [引擎性能和容量](../core/engine-performance-and-capacity.md)