---
title: "关键绩效指标 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 298d639a-7adf-4f04-b097-a17f4c77ee50
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a03bf76c725f22567d5e884ca22e3a862b15ce3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="key-performance-indicators"></a>关键绩效指标
本主题提供时使用以下的横向扩展方法，观察到 BizTalk Server 产品组的测试结果：  
  
-   当增加的数量关键绩效指标 (Kpi)[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 对于这些测试，只有一个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库配置为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 这些测试侧重于添加更多的影响仅[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机连接到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。  
  
-   Kpi 时增加的数量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]所用的 MessageBox 数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 这些测试侧重于添加更多的影响仅[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库移到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。  
  
-   Kpi 时增加的数量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]所用的 MessageBox 数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 这些测试测量的影响的同时添加[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库移到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。  
  
## <a name="analysis-of-key-performance-indicators"></a>关键绩效指标的分析  
  
### <a name="messaging-scenario-biztalk-server-scale-out--biztalk-and-sql-kpi"></a>消息传递方案，BizTalk Server 横向扩展 – BizTalk 和 SQL KPI  
 添加运行 BizTalk Server 的第二个计算机不显示对整体吞吐量显著的影响。  在 BizTalk Server CPU 上的负载减少了 25%。 SQL server CPU 稍会导致增加从 59%59.8%时运行 BizTalk Server 第二台计算机添加到 BizTalk Server 组。 超出此点，没有进一步的性能好处已获得通过增加 BizTalk 处理服务器的数量。  
  
 每个 BizTalk 主机实例定期轮询 MessageBox 中相应的队列。 消息框中的表的共享集内实际存储引用主机队列的任何消息。 如果吞吐量下降添加更多计算机运行 BizTalk Server 时，常见的原因是针对 MessageBox 数据库中共享的表的活动太多。 可以通过将这些表分配给特定的文件组创建这些表的 SQL Server 的专用的 I/O 路径。  
  
 [优化文件组为 Databases2](../technical-guides/optimizing-filegroups-for-the-databases2.md)指南提供有关如何将表分配给特定的文件组。 中包含的脚本[BizTalk Server MessageBox 数据库文件组 SQL 脚本](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md)指南的告知如何实现此目的。 跨多个文件组，并应用所有其他与 SQL 相关的优化之后分发 MessageBox 对象后，才应考虑到多个消息框配置的向外扩展。  
  
 **BizTalk Server 和 SQL Server CPU 使用率百分比**  
  
 ![&#45;SingleMsgBox](../technical-guides/media/m-singlemsgbox.gif "M SingleMsgBox")  
  
### <a name="messaging-scenario-biztalk-server-and-sql-server-scale-out--biztalk-and-sql-kpi"></a>消息传递方案中，BizTalk Server 和 SQL Server 横向扩展 – BizTalk 和 SQL KPI  
 此测试的目的是为了确定的扩展通过添加四个 MessageBox 数据库的 SQL Server 层的效率。 在此方案中，添加最多两个运行 BizTalk Server 的计算机启用 2,790 每秒的消息的最大可持续吞吐量。 使用单个消息框时，这是 118%高于最大可获得的吞吐量。 超出此点，将更高处理能力添加到 BizTalk Server 层降级到单一的 MessageBox 方案方式相似的性能。  
  
 从消息传递方案测试的主要发现是，向外扩展 BizTalk Server 是一种有效的技术来提高总体吞吐量，如果 SQL Server 上的争用不成为瓶颈。 MessageBox 数据库将成为争用点，如果首先应用中详述的优化[优化数据库性能](../technical-guides/optimizing-database-performance.md)，特别是优化脚本的文件组中所述[BizTalk ServerMessageBox 数据库文件组的 SQL 脚本](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md)将 I/O 负载。 如果仍无法获得所需的吞吐量，应考虑通过添加更多的 MessageBox 数据库向外扩展。  
  
 **BizTalk Server 和 SQL Server CPU 使用率百分比**  
  
 ![&#45;MultipleMsgBox](../technical-guides/media/m-multiplemsgbox.gif "M MultipleMsgBox")  
  
### <a name="orchestration-scenario-biztalk-server-scale-out--sql-server-and-biztalk-server-kpi"></a>业务流程方案中，BizTalk Server 横向扩展 – SQL Server 和 BizTalk Server KPI  
 添加运行 BizTalk Server 的第二个计算机不显示对整体吞吐量显著的影响。 在 BizTalk Server CPU 上的负载减少了 23%。 SQL server CPU 从 66.5%增加到 68.5%时添加运行 BizTalk Server 的其他计算机。  
  
 **BizTalk Server 和 SQL Server CPU 使用率百分比**  
  
 ![&#45;SingleMsgBox](../technical-guides/media/o-singlemsgbox.gif "O SingleMsgBox")  
  
### <a name="orchestration-scenario-biztalk-server-and-sql-server-scale-out--sql-server-and-biztalk-server-kpi"></a>业务流程方案中，BizTalk Server 和 SQL Server 向外扩展 – SQL Server 和 BizTalk Server KPI  
 此测试的目的是为了确定的层向外缩放的 BizTalk Server 和 SQL Server 通过添加更多计算机运行 BizTalk Server 和业务流程方案的更多的 MessageBox 数据库有效性。 在此方案中，添加最多两个运行 BizTalk Server 的计算机启用每秒的 1,487 业务流程的最大可持续的吞吐量。 这是 116%高于单个 MessageBox 针对最大可获得结果。 向外扩展到单独的 SQL Server 计算机上的四个 MessageBox 数据库可容纳由于额外的处理能力更高的吞吐量和能够跨多个 MessageBox 数据库分发数据库负载。 这种做法还缓解争用上共享的表，这是在单个 MessageBox 环境中的形成瓶颈。 与消息传递方案中，增加 MessageBox 数据库数目和分发这些跨专用的 SQL 实例可以添加到 BizTalk Server 组的多个 BizTalk Server 计算机。  
  
 **BizTalk Server 和 SQL Server CPU 使用率百分比**  
  
 ![&#45;MultipleMsgBox](../technical-guides/media/o-multiplemsgbox.gif "O MultipleMsgBox")  
  
## <a name="see-also"></a>另请参阅  
 [缩放生产 BizTalk Server 环境](../technical-guides/scaling-a-production-biztalk-server-environment.md)