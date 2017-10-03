---
title: "数据库可用性规划 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6aa74257-4159-46f6-b538-f7e9083d74ad
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea5aa21ad9db78236d7b1e5335053b7c9ce28770
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-database-availability"></a>数据库可用性规划
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务流程的可靠性和通过保存持久处理到的状态和业务数据，可确保消息引擎[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]称为 BizTalk Messagebox 数据库的数据库。 高可用性规划的可靠性和持久化数据的持续性仅与基础数据存储区一样好，因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库至关重要。  
  
## <a name="hardware-considerations"></a>硬件考虑事项  
 若要确保高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，请考虑以下规划硬件时：  
  
1.  请考虑实施存储区域网络 (SAN) 到内部[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 SAN 磁盘应配置使用 RAID 1 + 0 （带区的镜像集） 如有可能的拓扑最高的性能和高可用性。 有关发现家中使用 SAN 的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，请参阅[BizTalk Server 数据库优化](http://go.microsoft.com/fwlink/?LinkID=101578)白皮书 ([http://go.microsoft.com/fwlink/?LinkID=101578](http://go.microsoft.com/fwlink/?LinkID=101578))。  
  
2.  在安装运行的多台计算机上计划[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]到内部[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 运行的多台计算机[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]需要[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集 （推荐） 和/或外壳某些[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上单独的物理数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]（也建议使用） 的实例。  
  
3.  在安装运行的一个或多个计算机上的计划[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实现[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]日志传送为实现灾难恢复。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]实现数据库的使用的备用容量[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]日志传送。 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]日志传送自动化的备份和还原的数据库和事务日志文件，允许备用服务器恢复数据库处理的事件中的生产服务器失败。 有关实现详细信息[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]日志传送灾难恢复目的，请参阅[什么是 BizTalk Server 日志传送？](../technical-guides/what-is-biztalk-server-log-shipping.md)  
  
## <a name="software-considerations"></a>软件注意事项  
 若要确保高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，请考虑以下规划软件时： 计划安装的版本和版本的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]支持故障转移群集支持和/或 BizTalk 日志传送支持。 有关的各个版本支持的功能的完整列表[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]，请参阅[支持的 SQL Server 2008 的版本功能](http://go.microsoft.com/fwlink/?LinkId=151940)([http://go.microsoft.com/fwlink/?LinkId = 151940](http://go.microsoft.com/fwlink/?LinkId=151940)) 中[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]文档。  
  
## <a name="high-availability-vs-disaster-recovery"></a>高可用性 vs。灾难恢复  
 有两个不同方法来提高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境： 提供使用容错能力和/或负载平衡，或提供使用灾难恢复的可用性的高可用性。 虽然每个方法会增加可用性，它们的主要区别是该容错能力，并且/或者负载平衡通常提供比灾难恢复速度快得多的恢复时间。 因此，一个解决方案生成容错上或负载平衡更常见想象成提供高可用性而不是仅提供可用性。 这两种方法应在生产中采用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  
  
 提供的高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与 Windows 群集协同使用容错的数据库。 有关提供的高可用性的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，请参阅[数据库的高可用性](../technical-guides/high-availability-for-databases.md)。  
  
 提高可用性与灾难恢复使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送。 若要增加可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与灾难恢复的数据库遵循主题中的步骤[清单： 增加可用性与灾难恢复](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)。