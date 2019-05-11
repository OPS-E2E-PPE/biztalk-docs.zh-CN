---
title: BizTalk Server 性能故障排除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dbf21fb9-1ae1-48b5-a65a-e96839b23945
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec29254a43a86f29a16ddb5babe5d3c607689f68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401874"
---
# <a name="troubleshooting-biztalk-server-performance"></a>BizTalk Server 性能故障排除
本部分包含有关诊断和解决与 BizTalk 消息引擎相关的性能问题的常规指导原则。  
  
## <a name="estimating-document-processing-requirements"></a>评估文档处理要求  
 计划和测试以确定消息引擎性能需求之前将解决方案部署到生产环境。 这将帮助您适当地构建您的 BizTalk Server 和 SQL Server 环境。  
  
1.  计划相关的开销的任何容错、 备份和恢复需求  
  
    -   将 SQL Server 磁盘配置为 RAID 阵列？  
  
    -   将 Windows 群集使用适用于 BizTalk 主机、 SQL Server 或企业单一登录？ 有关详细信息请参阅[以实现高可用性规划](../core/planning-for-high-availability3.md)。  
  
    -   将使用网络负载平衡？  
  
    -   环境的备份和恢复要求有哪些？ 有关详细信息，请参阅[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)。  
  
2.  遵循中的准则[规划可持续性能](../core/planning-for-sustained-performance.md)计划、 测试和缩放你的 BizTalk Server 和 SQL Server 环境。  
  
3.  遵循中的准则[跟踪性能特征](../core/tracking-performance-characteristics.md)规划与文档跟踪要求相关联的开销。  
  
## <a name="optimizing-an-existing-biztalk-server-environment"></a>优化现有 BizTalk Server 环境  
 请执行以下步骤优化现有 BizTalk Server 环境：  
  
1.  遵循中的准则[识别性能瓶颈](../core/identifying-performance-bottlenecks.md)以查明 BizTalk Server 环境中可能的瓶颈。  
  
2.  遵循中的准则[优化资源使用情况通过主机阻止](../core/optimizing-resource-usage-through-host-throttling.md)以使 BizTalk Server 环境的文档吞吐量最大化。  
  
3.  请考虑修改中所述的参数[配置参数会影响适配器性能的](../core/configuration-parameters-that-affect-adapter-performance.md)以最大程度提高某些方案中的适配器性能。  
  
4.  遵循中的准则[如何 BizTalk Server 处理大消息](../core/how-biztalk-server-processes-large-messages.md)优化消息引擎性能时处理大消息 (超过 100 MB)。  
  
5.  创建单独的主机和主机实例，以便发送适配器，接收适配器和业务流程。 这将使每个适配器的单独的主机实例中运行，并确保该适配器不产生不利影响另一个。 由于在主机级别配置的主机阻止设置，处理逻辑分为不同的主机的分离还允许您配置基于每个主机的处理要求的限制设置。  
  
## <a name="diagnosing-performance-problems-in-an-existing-biztalk-server-environment"></a>诊断现有 BizTalk Server 环境中的性能问题  
 通常为 BizTalk Server 环境的以下组件之一被缩小性能问题：  
  
- 接收适配器或适配器正在接收来自文档的系统。 例如，如果文档在接收 HTTP 适配器以非最优的速率，则问题可能是使用 HTTP 获得适配器或发布到 HTTP 适配器的客户端。  
  
- 业务流程服务实例。  
  
- 包含 Microsoft SQL server 的性能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。  
  
- 发送适配器或适配器正在发送到的文档的系统。 例如，如果该问题可能是与 SQL 发送适配器或运行的计算机，然后费率非最优 SQL 适配器发送文档[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]更新 SQL 适配器。  
  
  使用以下准则来帮助识别的各组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]较差的环境：  
  
- 捕获的任何警告或错误中生成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]事件查看器。  
  
- 按照中的步骤[识别性能瓶颈](../core/identifying-performance-bottlenecks.md)来帮助确定性能瓶颈。  
  
  一旦确定差的组件，请执行相应的准则来帮助解决此问题：  
  
  **解决相关来发送和接收适配器的性能问题的准则**  
  
- 请参阅[故障排除 BizTalk Server 适配器](../core/troubleshooting-biztalk-server-adapters.md)问题的疑难解答的一般信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器。 本部分包含常规故障排除信息，包括有关如何设置日志记录对于某些适配器的信息和可用的信息诊断网络问题，问题与 MSDTC、 注册表、 文件出现问题的问题系统，并使用 IIS 的问题。  
  
- 请参阅的相应部分[故障排除的 BizTalk Server 依赖项](../core/troubleshooting-biztalk-server-dependencies.md)解决与 MSDTC、 证书、 企业单一登录，问题的常规信息和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。  
  
  **解决与业务流程相关的性能问题的准则**  
  
- 修改 BTSNTSvc.exe.config 文件中所述的相应部分[业务流程引擎配置](../core/orchestration-engine-configuration.md)。  
  
  **解决与 SQL Server 相关的性能问题的准则**  
  
- SQL Server Profiler 可用于捕获发送到 SQL Server 的 TRANSACT-SQL 语句和 SQL Server 结果集从这些语句。 由于 BizTalk Server 与 SQL Server 紧密集成，SQL Server 配置文件跟踪分析可以是用于分析在 BizTalk Server 中读取和写入到 SQL Server 数据库时可能发生的问题的有用工具。 有关如何使用 SQL Server Profiler 的信息请参阅 SQL Server 文档。  
  
- SQL Server 查询编辑器可以用于直接对 SQL Server 数据库执行 SQL 语句。 此功能可能对于查询 BizTalk Server 数据库，或者在某些情况下 BizTalk Server 数据库更新。 有关查询编辑器的详细信息请参阅 SQL Server 文档。  
  
- 审阅[故障排除 SQL Server](../core/troubleshooting-sql-server.md)有关其他信息。  
  
## <a name="see-also"></a>请参阅  
 [故障排除](../core/troubleshooting.md)