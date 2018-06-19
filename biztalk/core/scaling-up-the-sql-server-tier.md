---
title: SQL Server 层向上缩放 |Microsoft 文档
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
ms.openlocfilehash: 6c654c4a3b1bba166ae8a49918f6ef31827cf041
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269677"
---
# <a name="scaling-up-the-sql-server-tier"></a>SQL Server 层向上扩展
在此模式中，将根据吞吐量或延迟要求对现有 SQL MessageBox 数据库进行升级以实现扩展。  
  
 下图显示了一种将主 MessageBox 数据库从 4 处理器服务器升级到 8 处理器服务器的方案：  
  
 ![缩放 &#45; 向上 MSGBOX](../core/media/scaleupmsgbox2.gif "ScaleUpMsgBox2")  
  
## <a name="when-to-scale-up-the-sql-tier"></a>何时向上扩展 SQL 层  
  
-   当可向上扩展主 MessageBox 数据库时。  
  
-   当主 MessageBox 数据库成为瓶颈时。 可以是那些瓶颈：  
  
    -   **CPU**发生非常昂贵且复杂的业务流程方案中，消息框占用大量 CPU 资源。 通过添加更多的 CPU 来向上扩展 SQL 服务器可以对此方案进行扩展。  
  
    -   **内存或 I/O**内存或 I/O 可能形成瓶颈和可升级。  
  
-   当向上扩展比向外扩展成本更低，并且向上扩展可以解决瓶颈问题时。 例如，如果主 MessageBox 数据库存在 SQL 锁争用问题，此问题无法通过向上扩展来解决。  
  
## <a name="when-do-you-decide-sql-cannot-scale-up"></a>何时确定 SQL 无法向上扩展？  
 向上扩展无法解决 SQL 层上的锁争用瓶颈。 如果遇到这些类型的瓶颈，向外扩展是比向上扩展更好的选择。  
  
## <a name="strategies-and-considerations-for-scaling-up-the-sql-tier"></a>策略和 SQL 层向上扩展的注意事项  
  
-   首先向上扩展主 MessageBox 数据库，然后向外扩展。  
  
-   Master MessageBox 数据库最终将瓶颈。 因此，主 MessageBox 数据库应更快、更大（例如，采用基于 Itanium 的 64 位或基于 x64 的双核计算机）。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 层向外缩放](../core/scaling-out-the-biztalk-server-tier.md)   
 [BizTalk Server 层向上扩展](../core/scaling-up-the-biztalk-server-tier.md)   
 [SQL Server 层向外缩放](../core/scaling-out-the-sql-server-tier.md)   
 [向外扩展接收主机](../core/scaled-out-receiving-hosts.md)   
 [向外扩展的处理主机](../core/scaled-out-processing-hosts.md)   
 [向外扩展的发送主机](../core/scaled-out-sending-hosts.md)   
 [Windows Server 群集用于 BizTalk Server Hosts2 为提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [向外扩展的数据库](../core/scaled-out-databases.md)   
 [群集的 BizTalk Server 数据库](../core/clustering-the-biztalk-server-databases1.md)