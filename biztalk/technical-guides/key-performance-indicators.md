---
title: 关键绩效指标 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 298d639a-7adf-4f04-b097-a17f4c77ee50
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fc0d89c7d6bb72cf68611d1a6eaccffa11dbe0d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395839"
---
# <a name="key-performance-indicators"></a>关键绩效指标
本主题提供使用以下扩展方法时，观察到的 BizTalk Server 产品组的测试结果：  
  
- 关键绩效指标 (Kpi) 时增加的数量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 对于这些测试，只有一个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库中配置的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 这些测试只侧重于添加更多的影响[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机连接到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。  
  
- Kpi 时增加的数量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用的 MessageBox 数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 这些测试只侧重于添加更多的影响[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库移到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。  
  
- Kpi 时增加的数目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用的 MessageBox 数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 这些测试度量的同时添加影响[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库移到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。  
  
## <a name="analysis-of-key-performance-indicators"></a>关键绩效指标的分析  
  
### <a name="messaging-scenario-biztalk-server-scale-out--biztalk-and-sql-kpi"></a>消息传送方案，BizTalk Server 向外缩放 – BizTalk 和 SQL KPI  
 添加第二个计算机运行 BizTalk Server 不显示对整体吞吐量显著的影响。  在 BizTalk Server CPU 负载降低 25%。 适用于 SQL Server CPU 略微增加从 59%到 59.8%时运行 BizTalk Server 的第二个计算机添加到 BizTalk Server 组。 超出了目前为止，任何进一步的性能好处已获得不了通过增加 BizTalk 处理服务器的数量。  
  
 每个 BizTalk 主机实例定期轮询 MessageBox 中相应的队列。 主机队列引用的任何消息实际上存储在 MessageBox 中的表的共享集。 如果吞吐量下降到添加更多运行 BizTalk Server 的计算机时，一个常见原因是针对 MessageBox 数据库中的共享表的活动太多。 可以通过将这些表分配给特定的文件组创建这些表的 SQL Server 的专用的 I/O 路径。  
  
 [优化文件组的数据库 2](../technical-guides/optimizing-filegroups-for-the-databases2.md)指南提供有关如何将表分配给特定的文件组。 中包含的脚本[BizTalk Server MessageBox 数据库文件组 SQL 脚本](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md)指南的告知如何实现此目的。 跨多个文件组，并应用所有其他与 SQL 相关的优化后分发 MessageBox 对象后，才应考虑向外的扩展到多个 MessageBox 配置。  
  
 **BizTalk Server 和 SQL Server CPU 使用率百分比**  
  
 ![M&#45;SingleMsgBox](../technical-guides/media/m-singlemsgbox.gif "M SingleMsgBox")  
  
### <a name="messaging-scenario-biztalk-server-and-sql-server-scale-out--biztalk-and-sql-kpi"></a>消息传递方案中，BizTalk Server 和 SQL Server 扩展-BizTalk 和 SQL KPI  
 已执行此测试，以确定通过添加四个 MessageBox 数据库向外扩展 SQL Server 层的效率。 在此方案中，添加最多两个运行 BizTalk Server 的计算机启用 2,790 消息数 / 秒的最大可承受吞吐量。 使用单个消息框时，这是比最大可获得的吞吐量更高版本 118%。 不在此点，将更多处理能力添加到 BizTalk Server 层已降级以类似的方式与单个 MessageBox 方案的性能。  
  
 从消息传送方案中测试的主要发现是，向外扩展 BizTalk Server 是一种有效的技术以提高总体吞吐量，如果 SQL Server 上的争用不成为瓶颈。 如果 MessageBox 数据库将成为争用点，首先应用中详细介绍的优化[优化数据库性能](../technical-guides/optimizing-database-performance.md)，尤其是文件组优化脚本中所述[BizTalk ServerMessageBox 数据库文件组 SQL 脚本](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md)将 I/O 负载。 如果仍无法获得所需的吞吐量，应考虑通过添加多个 MessageBox 数据库向外扩展。  
  
 **BizTalk Server 和 SQL Server CPU 使用率百分比**  
  
 ![M&#45;MultipleMsgBox](../technical-guides/media/m-multiplemsgbox.gif "M-MultipleMsgBox")  
  
### <a name="orchestration-scenario-biztalk-server-scale-out--sql-server-and-biztalk-server-kpi"></a>业务流程方案中，BizTalk Server 向外缩放-SQL Server 和 BizTalk Server KPI  
 添加第二个计算机运行 BizTalk Server 不显示对整体吞吐量显著的影响。 在 BizTalk Server CPU 上的负载可降低的 23%。 适用于 SQL Server CPU 从 66.5%增加到 68.5%添加运行 BizTalk Server 的其他计算机时。  
  
 **BizTalk Server 和 SQL Server CPU 使用率百分比**  
  
 ![O&#45;SingleMsgBox](../technical-guides/media/o-singlemsgbox.gif "O SingleMsgBox")  
  
### <a name="orchestration-scenario-biztalk-server-and-sql-server-scale-out--sql-server-and-biztalk-server-kpi"></a>业务流程方案中，BizTalk Server 和 SQL Server 扩展-SQL Server 和 BizTalk Server KPI  
 已执行此测试，以确定通过添加更多的计算机运行 BizTalk Server 业务流程方案的多个 MessageBox 数据库向外扩展 BizTalk Server 和 SQL Server 层的效率。 在此方案中，添加最多两个运行 BizTalk Server 的计算机启用了每秒 1,487 业务流程的最大可承受吞吐量。 这是 116%高于针对单个 MessageBox 的最大可获得结果。 向外扩展到不同的 SQL Server 计算机上的四个 MessageBox 数据库还包含由于额外的处理能力更高的吞吐量以及将数据库负载分发到多个 MessageBox 数据库的能力。 这种做法还使共享表上的争用是单个 MessageBox 环境中的瓶颈。 与消息传送方案中，增加的 MessageBox 数据库的数量和分发这些跨专用的 SQL 实例启用多个 BizTalk Server 计算机连接到 BizTalk Server 组添加。  
  
 **BizTalk Server 和 SQL Server CPU 使用率百分比**  
  
 ![O&#45;MultipleMsgBox](../technical-guides/media/o-multiplemsgbox.gif "O-MultipleMsgBox")  
  
## <a name="see-also"></a>请参阅  
 [缩放 BizTalk Server 生产环境](../technical-guides/scaling-a-production-biztalk-server-environment.md)