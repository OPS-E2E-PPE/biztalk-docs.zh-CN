---
title: "SQL Server 层向外缩放 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scaling, MessageBox database
- scaling, scaling out
- SQL Server, scaling
- MessageBox database, scaling
- scaling, strategies
ms.assetid: d5b2ebba-401e-4fde-8818-407fa626043a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 702c253a0135c1dc4af4cea15a9b47c77792586f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scaling-out-the-sql-server-tier"></a>向外扩展 SQL Server 层
对于每个 BizTalk 组，添加一个主 MessageBox 数据库。 随后添加的所有 MessageBox 数据库称为辅助 MessageBox。 主 MessageBox 处理所有订阅和消息路由。 它还可以发布消息。 辅助 MessageBox 数据库只有在专门将其配置为发布消息时才能执行此操作。  
  
## <a name="how-to-add-a-secondary-messagebox-database"></a>如何添加辅助 MessageBox 数据库  
 可以通过以下两种方式添加辅助 MessageBox 数据库：  
  
-   在同一物理服务器上添加辅助 MessageBox 数据库。  
  
     如果现有 MessageBox 物理服务器具有足够的 CPU 和 I/O 资源，并且仅由于锁争用造成瓶颈，则可以使用这种方式。 在单独的 IO 驱动器上创建辅助 MessageBox 数据库。  
  
     优点：  
  
    -   其他 MessageBox 可以使用额外的 CPU 余量  
  
    -   只需要较少的 SQL Server 许可证  
  
    -   消除了网络跃点  
  
-   在不同的物理服务器上添加辅助 MessageBox 数据库。  
  
     在这种情况下，将具有自己的 IO 的专用物理服务器用作额外 MessageBox 数据库。  
  
 下图显示了将 SQL 层从一个 MessageBox 数据库向外扩展到三个 MessageBoxes 数据库的方案：  
  
 ![横向扩展 MSGBOX](../core/media/scaleoutmsgbox.gif "ScaleOutMSGBOX")  
  
## <a name="when-to-scale-out-the-messagebox-database"></a>何时向外扩展 MessageBox 数据库  
  
-   MessageBox 数据库成为瓶颈。 可以是那些瓶颈：  
  
    -   **CPU**非常昂贵且复杂的业务流程的情况下，如果 MessageBox 数据库占用大量 CPU 资源。 添加其他发布 MessageBox 数据库应有助于增加吞吐量。  
  
    -   **锁争用，**具有多个主机实例或业务流程的复杂方案，往往会在 MessageBox 数据库上创建锁争用。 同样，添加其他发布 MessageBox 数据库应有助于增加吞吐量。  
  
-   向上扩展不能解决瓶颈问题。 例如，如果主 MessageBox 数据库上出现锁争用，向外扩展是唯一的选择。  
  
-   向上扩展是过于昂贵。 例如，如果将现有 4 处理器服务器升级到 8 向服务器的成本比添加另一个 4 处理器服务器昂贵，则向外扩展是更好的选择。  
  
## <a name="when-you-cant-scale-out-the-sql-tier"></a>不能向外扩展 SQL 层的情况  
 理论上，只要主 MessageBox 数据库不是瓶颈，SQL 层就可能无限扩展。 为此，考虑使主 MessageBox 数据库成为非发布数据库，这样它仅执行路由。 但是，主 MessageBox 数据库由于锁争用出现瓶颈后，您就不能再向外扩展 SQL 层。  
  
## <a name="scale-out-strategies-and-considerations"></a>向外扩展的策略和注意事项  
  
-   第一次的向上缩放 Master MessageBox 数据库，然后向外扩展。  
  
-   向外缩放从 1 到 3 个 SQL MessageBox 数据库而不是 1 到 2。 考虑在上图中所示 1 的 SQL server 拓扑标题为"4 BizTalk Server，1 SQL 服务器拓扑中，"，并假定，SQL server 是 CPU 绑定，换而言之，CPU 处理是瓶颈。 如果只将一个 MessageBox 数据库添加到此拓扑结构中，则主 Messagebox 仍将为 CPU 绑定且辅助 MessageBox 数据库将不能得到充分利用。 因此的缩放因子是几乎 1。 如果你禁用主 MessageBox 数据库上的发布，并且将专用于 Master MessageBox 数据库只是为了进行路由，辅助 MessageBox 数据库将执行发布。 这并不能增加总体吞吐量，尽管辅助 MessageBox 数据库只用作发布服务器，但它仍会成为瓶颈。 因此，这种情况下建议的向外扩展方式为：添加 2 个辅助 MessageBox 数据库并在主 MessageBox 数据库上禁用发布。  
  
-   主 MessageBox 数据库最终将成为瓶颈。 因此，作为主 MessageBox 数据库宿主的物理计算机应更快和更大。  
  
-   为了最大程度地减少通过网络发送数据（和关联的 DTC 开销），请考虑将多个 MessageBox 数据库放置于具有专用驱动器的同一物理计算机上。 同时，确保多个 MessageBox 数据库共享资源时，存放这些数据库的计算机不会出现瓶颈。  
  
-   由于工作是在发布 MessageBox 数据库之间平均分配的，故所有的辅助 MessageBox 数据库应使用相同的硬件。  
  
-   由于只要主 MessageBox 数据库没有瓶颈问题就可以向外扩展辅助 MessageBox 数据库，因此辅助 MessageBox 数据库可运行在其 CPU 资源少于主 MessageBox 数据库服务器所需资源的计算机上。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 层向外缩放](../core/scaling-out-the-biztalk-server-tier.md)   
 [BizTalk Server 层向上扩展](../core/scaling-up-the-biztalk-server-tier.md)   
 [SQL Server 层向上扩展](../core/scaling-up-the-sql-server-tier.md)   
 [向外扩展接收主机](../core/scaled-out-receiving-hosts.md)   
 [向外扩展的处理主机](../core/scaled-out-processing-hosts.md)   
 [向外扩展的发送主机](../core/scaled-out-sending-hosts.md)   
 [Windows Server 群集用于 BizTalk Server Hosts2 为提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [向外扩展的数据库](../core/scaled-out-databases.md)   
 [群集的 BizTalk Server 数据库](../core/clustering-the-biztalk-server-databases1.md)