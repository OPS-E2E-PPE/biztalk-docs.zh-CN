---
title: 规划数据库可用性 |Microsoft Docs
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
ms.openlocfilehash: 7b04a83c0e19c05f28a648cddd09ca8ebd4482a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394634"
---
# <a name="planning-for-database-availability"></a>规划数据库可用性
BizTalk Server 消息引擎可确保业务流程可靠和持久保留由处理到称为 BizTalk Messagebox 数据库的 SQL Server 数据库的状态和业务数据。 可靠性和持久性数据的持续性的好坏都作为基础数据存储区，因为为 BizTalk Server 数据库的高可用性规划是非常重要。  
  
## <a name="hardware-considerations"></a>硬件注意事项  
 若要确保 BizTalk Server 数据库的高可用性，请考虑以下规划硬件时：  
  
1.  请考虑实施存储区域网络 (SAN) 来存放 BizTalk Server 数据库。 SAN 磁盘应配置使用 RAID 1 + 0 （带区的镜像集） 拓扑尽可能以最大性能和高可用性。 
  
2.  计划安装多台计算机运行 SQL Server 以容纳 BizTalk Server 数据库。 需要 SQL Server 群集 （建议） 和/或外壳某些 BizTalk Server 数据库 （也建议使用） 的单独物理 SQL Server 实例上运行 SQL Server 的多台计算机。  
  
3.  计划安装一个或多个运行 SQL Server 来实现 SQL Server 日志传送出于灾难恢复的计算机。 BizTalk Server 实现数据库备用功能通过使用 SQL Server 日志传送。 SQL Server 日志传送可以自动备份和还原的数据库和事务日志文件，这样，若要恢复数据库处理在的生产服务器出现故障时备用服务器。 有关实现 SQL Server 日志传送出于灾难恢复的详细信息，请参阅[什么是 BizTalk Server 日志传送？](../technical-guides/what-is-biztalk-server-log-shipping.md)  
  
## <a name="software-considerations"></a>软件注意事项  
 若要确保 BizTalk Server 数据库的高可用性，请考虑以下规划软件时：计划安装的版本和版本的 SQL Server 支持故障转移群集的支持和/或 BizTalk 日志传送的支持。 SQL Server 各个版本支持的功能的完整列表，请参阅[各版本和支持的功能](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016)。
  
## <a name="high-availability-vs-disaster-recovery"></a>高可用性与灾难恢复  
 提高 BizTalk Server 环境的可用性的两种不同方法： 提供高可用性使用容错能力和/或负载平衡，或提供使用灾难恢复的可用性。 虽然每个方法会增加可用性，它们之间主要区别是该容错能力，和/或负载平衡通常提供比灾难恢复速度快得多的恢复时间。 因此，一种解决方案基于容错或负载平衡是更广泛被认为提供高可用性而不是只提供可用性。 应在生产 BizTalk Server 环境中使用这两种方法。  
  
 使用与 Windows 群集的容错能力的 BizTalk Server 数据库提供高可用性。 有关为 BizTalk Server 数据库提供高可用性的详细信息，请参阅[数据库的高可用性](../technical-guides/high-availability-for-databases.md)。  
  
 提高可用性与灾难恢复使用 BizTalk Server 日志传送。 若要提高了灾难恢复的 BizTalk Server 数据库的可用性，请按照本主题中的步骤[核对清单：提供高可用性灾难恢复](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)。