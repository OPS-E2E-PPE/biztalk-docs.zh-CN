---
title: "引擎持久性和持久性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9bd209e9-75d2-422f-b3b2-377986f41f2f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13f9f3f1a02ddfe84a963704476e867783f31042
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="engine-persistence-and-durability"></a>引擎持久性和持久性
本部分将介绍 BizTalk Server 如何通过利用 SQL Server 将流程状态保存到磁盘上来可靠地集成松散连接的业务流程。 通过利用事务以适当的次数保存状态，系统可以保证即使在硬件或软件发生故障的情况下也不会丢失任何流程状态。 这称为系统持久性。  
  
## <a name="loosely-coupled-business-process-management"></a>松散耦合的业务流程管理  
 集成现有系统以执行单个逻辑业务流程需要在现有系统外对流程状态进行管理。 为了避免由于将系统紧密连接在一起而导致自定义通信路径公开，无论是长期运行的还是生命期短的业务流程，都必须独立维护其流程状态。  
  
 显然，如果业务流程非常关键，则运行业务流程实例的状态必须十分可靠。 为确保业务流程具有可靠性和持久性，BizTalk 利用 SQL Server 事务将流程状态和业务数据保存到磁盘上称为 MessageBox 数据库的数据库中。 MessageBox 数据库有关的详细信息，请参阅[MessageBox 数据库](../core/the-messagebox-database.md)。  
  
 在处理期间，至少会将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的每个消息以及几乎最细微的业务程序实例（例如，业务流程实例）保存到 MessageBox 数据库中一次。  
  
## <a name="persistence-and-sustainability"></a>持久性和可持续性  
 BizTalk Server 仍然存在的所有消息，大多数的业务流程的事实将直接影响对中所述的可持续性[什么是可持续的性能？](../core/what-is-sustainable-performance.md) 当消息到达 MessageBox 数据库中时，它们是路由到等待订阅者 （例如，业务流程和发送端口） 和 en-排入队列，或已发布到 messagebox SQL 表等待订户中选取它们，并处理它们。 其中某些到达的消息将激活新的订户实例。 其他到达的消息则通过相关路由到已在运行的订户（例如，相关业务流程）的等待实例。  
  
 为使相关业务流程继续进行处理，到达的相关消息必须保持未阻塞状态。 为实现此条件，BizTalk 将尽力确保即使在高负载情况下也会继续接收激活和相关的消息，以便等待相关消息的订户可以完成处理，并为要运行的其他流程留出空间。 这意味着，接收消息的速度可能超过对其进行处理并将其从 MessageBox 数据库中删除的速度，从而产生消息积压。 作为一项存储并转发技术，BizTalk 自身可以提供这种类型的缓冲，但是，如果接收速度长期持续超过处理速度，则会产生大量积压，而这将会导致问题。  
  
 BizTalk Server 所接收的或在其中创建的每个消息都是不可改变的。 也就是说，在接收或创建消息后，则无法更改其内容。 此外，接收的消息可能会有多个订户。 特定消息的每个订户都引用该消息的同一个副本。 尽管此方法可以最大限度地减少存储，但仍必须保持每个消息的引用计数，并且必须定期执行维护以清除那些引用计数为 0 的消息。  
  
 如果允许在 MessageBox 数据库中产生足够大量的积压，则该数据库的维护进程（对于每个 MessageBox 数据库，该进程作为一组 SQL 作业实现）将会滞后，如果没有机会及时进行维护，则最终将导致磁盘空间不足等问题。 为避免出现此情况，BizTalk Server 提供了一种阻止机制，该机制可以在 MessageBox 数据库积压达到用户可配置的某个级别时降低消息接收速度。 有关限制的详细信息，请参阅[优化资源使用通过主机限制](../core/optimizing-resource-usage-through-host-throttling.md)。  
  
 假定所有活动和流程都会影响可维持性，则对一段时间内可维持性的主要度量是不允许积压无限增长。 换而言之，在一段时间内，高低峰值吞吐量级别之间必须保持平衡，以便 MessageBox 数据库能够维护持续的易于管理的平均积压。 积压的主要度量是后台处理表的深度，该表作为名为 BizTalk:Message Box:General Counters:Spool Size 的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 性能计数器公开。 有关此性能计数器的详细信息，请参阅[消息框性能计数器](../core/message-box-performance-counters.md)。  
  
 有关如何使用假脱机大小和其他计数器来确定系统可以承受的最大吞吐量的详细信息，请参阅[测量最大可持续引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md)。  
  
## <a name="recommendations"></a>建议  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将保存所有消息和大多数业务流程，如果不进行限制，则会造成消息积压，从而导致磁盘空间不足等问题。 积压的主要度量是 MessageBox 后台处理表的深度，该表作为名为 BizTalk:Message Box:General Counters:Spool Size 的性能计数器公开。  
  
 考虑可承受吞吐量时，后台处理大小必须在一段时间内维持稳定的平均值。 也就是说，后台处理不能继续不受限制地无限增长。 在[测量最大可持续引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md)、 此行为更详细地讨论和确定系统可以承受的最大吞吐量的方法提供它利用假脱机大小和其他性能指示器。  
  
## <a name="see-also"></a>另请参阅  
 [测量的最大可持续引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [什么是可持续的性能？](../core/what-is-sustainable-performance.md)   
 [性能提示和技巧](../core/performance-tips-and-tricks.md)   
 [消息框性能计数器](../core/message-box-performance-counters.md)