---
title: 数据库可用性规划 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6aa74257-4159-46f6-b538-f7e9083d74ad
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d77ce6572ace3617308a046a422a3422b2dd8df5
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008438"
---
# <a name="planning-for-database-availability"></a>数据库可用性规划
BizTalk Server 消息引擎确保业务流程的可靠性，并通过保存持久处理到称为 BizTalk Messagebox 数据库的 SQL Server 数据库的状态和业务数据。 因为的可靠性和持久化数据的持续性仅与基础数据存储区一样好，BizTalk Server 数据库的高可用性规划是至关重要的。  
  
## <a name="hardware-considerations"></a>硬件考虑事项  
 若要确保 BizTalk 服务器数据库的高可用性，请考虑以下规划硬件时：  
  
1.  请考虑实施存储区域网络 (SAN)，以容纳 BizTalk Server 数据库。 SAN 磁盘应配置使用 RAID 1 + 0 （带区的镜像集） 如有可能的拓扑最高的性能和高可用性。 
  
2.  计划安装多个运行 SQL Server 以容纳 BizTalk Server 数据库的计算机。 运行 SQL Server 的多台计算机将需要 SQL Server 群集 （建议） 和/或存放在 （也建议使用） 的单独物理 SQL Server 实例上某些 BizTalk Server 数据库。  
  
3.  计划安装运行 SQL Server 以实现 SQL Server 日志传送以实现灾难恢复实现的一个或多个计算机。 BizTalk Server 实现数据库备用功能通过使用 SQL Server 日志传送。 SQL Server 日志传送自动化的备份和还原的数据库和事务日志文件，允许备用服务器恢复数据库处理的事件中的生产服务器失败。 有关实现 SQL Server 日志传送以实现灾难恢复实现的详细信息，请参阅[什么是 BizTalk Server 日志传送？](../technical-guides/what-is-biztalk-server-log-shipping.md)  
  
## <a name="software-considerations"></a>软件注意事项  
 若要确保 BizTalk 服务器数据库的高可用性，请规划软件时考虑以下： 打算安装的版本和版本的支持故障转移群集支持和/或 BizTalk 日志传送支持的 SQL Server。 SQL Server 各个版本支持的功能的完整列表，请参阅[版本和支持的功能](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016)。
  
## <a name="high-availability-vs-disaster-recovery"></a>高可用性 vs。灾难恢复  
 提高可用性于 BizTalk 服务器环境的两种不同方法： 提供使用容错能力和/或负载平衡，或提供使用灾难恢复的可用性的高可用性。 虽然每个方法会增加可用性，它们的主要区别是该容错能力，并且/或者负载平衡通常提供比灾难恢复速度快得多的恢复时间。 因此，一个解决方案生成容错上或负载平衡更常见想象成提供高可用性而不是仅提供可用性。 应在生产 BizTalk Server 环境中使用这两种方法。  
  
 为与 Windows 群集协同使用容错的 BizTalk Server 数据库提供高可用性。 有关为 BizTalk Server 数据库提供高可用性的详细信息，请参阅[数据库的高可用性](../technical-guides/high-availability-for-databases.md)。  
  
 提高可用性与灾难恢复使用 BizTalk Server 日志传送。 若要提高可用性与灾难恢复的 BizTalk Server 数据库，请按照本主题中的步骤[清单： 增加可用性与灾难恢复](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)。