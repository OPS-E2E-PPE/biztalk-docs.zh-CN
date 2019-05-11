---
title: 纵向扩展 SQL Server 层 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, scaling
- scaling, examples
- SQL Server, scaling
- scaling, scaling up
- scaling, strategies
ms.assetid: 4352c4af-6861-43d9-b433-9ca25668b439
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7642b09a9380dd33231fce7be85caee19e31a5fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308708"
---
# <a name="scaling-up-the-sql-server-tier"></a>纵向扩展 SQL Server 层
在此模式下，现有 SQL MessageBox 数据库都将升级到根据吞吐量或延迟中要求的规模。  
  
 下图显示了主 MessageBox 数据库从 4 处理器服务器升级到 8 处理器服务器的方案。  
  
 ![缩放&#45;向上 MSGBOX](../core/media/scaleupmsgbox2.gif "ScaleUpMsgBox2")  
  
## <a name="when-to-scale-up-the-sql-tier"></a>何时向上扩展 SQL 层  
  
-   当您可以扩展主 MessageBox 数据库。  
  
-   当主 MessageBox 数据库成为瓶颈。 可以是这些瓶颈：  
  
    -   **CPU**非常昂贵且复杂的业务流程方案，在消息框会占用大量 CPU 资源。 向上扩展 SQL server 通过添加更多的 Cpu 应缩放方案。  
  
    -   **内存或 I/O**内存或 I/O 可能是瓶颈，并且可以升级。  
  
-   当向上扩展是比向外扩展更便宜，向上扩展可以解决瓶颈问题。 例如，如果主 MessageBox 数据库存在 SQL 锁争用问题，无法通过向上扩展来解决此问题。  
  
## <a name="when-do-you-decide-sql-cannot-scale-up"></a>何时确定 SQL 无法向上扩展？  
 向上扩展不能解决 SQL 层上的锁争用瓶颈。 如果命中这些类型的瓶颈，向外扩展是比向上扩展更好的选择。  
  
## <a name="strategies-and-considerations-for-scaling-up-the-sql-tier"></a>策略和纵向扩展 SQL 层的注意事项  
  
-   向上扩展主 MessageBox 数据库第一次，然后向外扩展。  
  
-   主 MessageBox 数据库最终会成为瓶颈。 因此，主 MessageBox 数据库应更快、 更大 （例如，基于 Itanium 的 64 位或基于 x64 的双核计算机）。  
  
## <a name="see-also"></a>请参阅  
 [向外扩展 BizTalk Server 层](../core/scaling-out-the-biztalk-server-tier.md)   
 [纵向扩展 BizTalk Server 层](../core/scaling-up-the-biztalk-server-tier.md)   
 [SQL Server 层向外缩放](../core/scaling-out-the-sql-server-tier.md)   
 [向外扩展接收主机](../core/scaled-out-receiving-hosts.md)   
 [向外扩展处理主机](../core/scaled-out-processing-hosts.md)   
 [向外扩展发送主机](../core/scaled-out-sending-hosts.md)   
 [使用 Windows Server 群集为 BizTalk Server 主机 2 提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [向外扩展数据库](../core/scaled-out-databases.md)   
 [聚类分析 BizTalk Server 数据库](../core/clustering-the-biztalk-server-databases1.md)