---
title: SQL Server 层向外缩放 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scaling, MessageBox database
- scaling, scaling out
- SQL Server, scaling
- MessageBox database, scaling
- scaling, strategies
ms.assetid: d5b2ebba-401e-4fde-8818-407fa626043a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c49a6bd83b6647170574106dd06825e2e5aba75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309023"
---
# <a name="scaling-out-the-sql-server-tier"></a>SQL Server 层向外缩放
对于每个 BizTalk 组，您将添加一个主 MessageBox 数据库。 所有后续 MessageBox 数据库，您将添加称为辅助 Messagebox。 主 MessageBox 处理所有订阅和消息路由。 它还可以发布消息。 辅助 MessageBox 数据库仅将发布消息时专门配置，以执行此操作。  
  
## <a name="how-to-add-a-secondary-messagebox-database"></a>如何添加辅助 MessageBox 数据库  
 有两种方法来添加辅助 MessageBox 数据库：  
  
- 在同一物理服务器上添加辅助 MessageBox 数据库。  
  
   如果现有 MessageBox 物理服务器具有足够的 CPU 和 I/O 资源，并且仅遇到锁争用瓶颈，则执行此操作。 不同的 IO 驱动器上创建辅助 MessageBox 数据库。  
  
   优点：  
  
  -   另一个消息框通过利用额外的 CPU 余量  
  
  -   所需较少的 SQL server 许可证  
  
  -   消除的网络跃点  
  
- 不同的物理服务器上添加辅助 MessageBox 数据库  
  
   在这种情况下，专用物理服务器与自己的 IO 使用作为额外的 MessageBox 数据库。  
  
  下图显示了其中 SQL 层向外扩展从一个 MessageBox 数据库到三个 MessageBoxes 数据库的方案。  
  
  ![向外扩展 MSGBOX](../core/media/scaleoutmsgbox.gif "ScaleOutMSGBOX")  
  
## <a name="when-to-scale-out-the-messagebox-database"></a>当向外扩展 MessageBox 数据库  
  
-   MessageBox 数据库成为瓶颈。 可以是这些瓶颈：  
  
    -   **CPU**非常昂贵且复杂的业务流程方案中，如果 MessageBox 数据库会占用大量 CPU 资源。 添加其他发布 MessageBox 数据库应有助于增加吞吐量。  
  
    -   **锁争用**具有多个主机实例或业务流程的复杂方案往往会在 MessageBox 数据库上创建锁争用。 同样，添加其他发布 MessageBox 数据库应有助于增加吞吐量。  
  
-   向上扩展没有解决瓶颈问题。 例如，如果主 MessageBox 数据库出现锁争用，向外扩展是唯一的选项。  
  
-   向上扩展成本十分高昂。 例如，如果将现有 4 处理器服务器升级到 8 路服务器比添加另一个 4 处理器开销更大，向外扩展是更好的选择。  
  
## <a name="when-you-cant-scale-out-the-sql-tier"></a>不能向外扩展 SQL 层  
 从理论上讲，应无限期地只要主 MessageBox 数据库不是瓶颈扩展 SQL 层。 若要实现此目的，请考虑使主 MessageBox 数据库成为非发布数据库，以便它仅执行路由。 但是，一旦主锁争用出现瓶颈，不能缩放任何更多扩展 SQL 层。  
  
## <a name="scale-out-strategies-and-considerations"></a>向外缩放策略和注意事项  
  
-   首先向上扩展主 MessageBox 数据库，然后向外扩展。  
  
-   向外扩展从 1 到 3 个 SQL MessageBox 数据库，而不是 1 到 2。 请考虑在上图中所示 1 的 SQL server 拓扑标题为"4 个 BizTalk Server，1 的 SQL Server 拓扑，"并认为 SQL server 是 CPU 绑定，换句话说，CPU 处理为瓶颈。 将只有一个 MessageBox 数据库添加到此拓扑中，如果主 Messagebox 仍将为 CPU 绑定且辅助 MessageBox 数据库将处于未充分利用。 因此，扩展因子是几乎为 1。 如果在主 MessageBox 数据库上禁用发布，并且将专用主 MessageBox 数据库仅用于进行路由，则辅助 MessageBox 数据库将执行发布。 这并不能增加总体吞吐量，但因为辅助 MessageBox 数据库只用作发布服务器并仍会成为瓶颈。 因此，添加 2 个辅助 MessageBox 数据库和主 MessageBox 数据库上禁用发布将在此方案中的横向扩展的建议的方法。  
  
-   主 MessageBox 数据库最终将成为瓶颈。 因此，承载主 MessageBox 数据库的物理计算机应更快、 更大。  
  
-   若要最小化发送的数据通过网络 （和关联的 DTC 开销），请考虑将多个 MessageBox 数据库放置在同一台物理计算机具有专用驱动器上。 在同一时间，请确保，拥有这些多个数据库的计算机不会出现瓶颈的资源由多个 MessageBox 数据库共享。  
  
-   所有辅助 MessageBox 数据库应使用相同的硬件，因为在发布 MessageBox 数据库之间均匀分布工作。  
  
-   由于只要主 MessageBox 数据库没有瓶颈问题，可以横向扩展辅助 MessageBox 数据库，辅助 MessageBox 数据库可以运行具有较少的 CPU 资源所需的主 MessageBox 数据库服务器的计算机上。  
  
## <a name="see-also"></a>请参阅  
 [向外扩展 BizTalk Server 层](../core/scaling-out-the-biztalk-server-tier.md)   
 [纵向扩展 BizTalk Server 层](../core/scaling-up-the-biztalk-server-tier.md)   
 [纵向扩展 SQL Server 层](../core/scaling-up-the-sql-server-tier.md)   
 [向外扩展接收主机](../core/scaled-out-receiving-hosts.md)   
 [向外扩展处理主机](../core/scaled-out-processing-hosts.md)   
 [向外扩展发送主机](../core/scaled-out-sending-hosts.md)   
 [使用 Windows Server 群集为 BizTalk Server 主机 2 提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [向外扩展数据库](../core/scaled-out-databases.md)   
 [聚类分析 BizTalk Server 数据库](../core/clustering-the-biztalk-server-databases1.md)