---
title: 引擎持久性和持续性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9bd209e9-75d2-422f-b3b2-377986f41f2f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 929047264eb395636ee7d2a5793642f12ac7e5e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349400"
---
# <a name="engine-persistence-and-durability"></a>引擎持久性和持续性
本部分说明 BizTalk Server 如何可靠地集成松散耦合的业务流程通过将流程状态保存到磁盘通过 SQL Server。 在适当时间，利用事务保持状态的系统可保证任何流程状态是甚至发生硬件或软件发生故障时丢失。 这称为系统持久性。  
  
## <a name="loosely-coupled-business-process-management"></a>松散耦合的业务流程管理  
 集成现有系统以执行单个逻辑业务流程需要现有系统外对流程状态的管理。 业务流程是长时间运行或短生存期，必须保持独立进程状态以避免产生的系统紧密连接在一起的自定义通信路径的爆炸式增长。  
  
 很明显，正在运行的状态必须是可靠如果业务流程非常关键的业务流程实例。 若要确保业务流程具有可靠性和持久性，BizTalk 利用 SQL Server 事务将保留处理到称为 MessageBox 数据库的数据库中的磁盘的状态和业务数据。 有关 MessageBox 数据库的详细信息，请参阅[MessageBox 数据库](../core/the-messagebox-database.md)。  
  
 每条消息以及几乎最细微的业务流程实例 （例如，业务流程实例） 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]至少一次在处理期间保留在 MessageBox 数据库中。  
  
## <a name="persistence-and-sustainability"></a>持久性和可持续发展  
 BizTalk Server 保存所有消息和大多数业务流程的事实会直接影响上同时实现可持续性中所述[可承受性能？](../core/what-is-sustainable-performance.md) 当消息到达 MessageBox 数据库中，它们是路由到等待的订户 （例如，业务流程和发送端口） 和排队，或已发布到 messagebox SQL 表以等待订户提取它们，并处理它们。 其中某些到达的消息激活新订阅服务器实例。 其他消息到达和路由，通过相关，如相关业务流程已在运行订阅服务器上的等待实例。  
  
 为了使相关业务流程可继续进行处理，到达的相关的消息必须保持未阻塞状态。 若要实现此目的，BizTalk 会尽力确保消息 （激活和相关） 会继续接收，即使在高负载下，以便等待相关消息的订户可以完成，并为多个进程运行留出空间。 这意味着可以快于可以处理并从 MessageBox 数据库，从而生成了消息积压工作中删除接收消息。 正在存储和转发技术，它是 biztalk 以提供此类型的缓冲，但是，它可能会导致问题的接收速率是否比处理速度，从而导致大量积压一致地更快。  
  
 接收的或中创建的每条消息，BizTalk Server 不可变。 也就是说，一旦它接收到的或已创建，不能更改其内容。 此外，接收的消息可能具有多个订阅服务器。 特定消息的每个订阅服务器引用该消息的同一个副本。 虽然这种方法最小化存储，必须为每个消息保留引用计数和必须定期执行维护以消除具有引用计数为 0 的那些消息。  
  
 如果允许足够大的积压工作来构建在 MessageBox 数据库中，（作为一组用于每个 MessageBox 数据库的 SQL 作业实现） 的数据库的维护过程将会滞后，如果没有机会赶上，最终会导致磁盘空间不足等问题。 若要避免这种情况下，BizTalk Server 提供了一种阻止机制，降低消息接收速率时 MessageBox 数据库积压达到为一些用户可配置的级别。 有关限制的详细信息，请参阅[优化资源使用情况通过主机阻止](../core/optimizing-resource-usage-through-host-throttling.md)。  
  
 给定的所有活动和流程都会影响可维持性，随着时间的推移可持续发展的主要度量都是，不允许积压无限增长。 换而言之，随着时间推移，必须有一种平衡之间的高低峰值吞吐量级别，以便 MessageBox 数据库是无法保持常量和可管理的平均积压工作。 积压工作的主要度量是后台处理表，该表作为公开的深度[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能计数器名为 biztalk: Message Box: General Counters: Spool Size。 有关此性能计数器的详细信息，请参阅[消息框性能计数器](../core/message-box-performance-counters.md)。  
  
 有关如何使用后台处理大小和其他计数器来确定系统可承受的最大吞吐量的详细信息，请参阅[测量最大可承受引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md)。  
  
## <a name="recommendations"></a>建议  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 保存所有消息和大多数业务流程，并可以保留未选中，开发可能会导致的磁盘空间不足等问题的消息积压。 积压工作的主要度量是 messagebox 后台处理表，该表作为名为性能计数器公开的深度：Biztalk: Message Box: General Counters: Spool Size。  
  
 当考虑可承受吞吐量，后台处理大小必须随着时间的推移维持稳定的平均值。 也就是说，后台处理不能继续无限地增长未选中。 在中[测量最大可承受引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md)，更详细地讨论此行为并确定系统可承受的最大吞吐量的方法提供利用后台处理大小和其他性能指示器。  
  
## <a name="see-also"></a>请参阅  
 [测量最大可承受引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [什么是可维持性能？](../core/what-is-sustainable-performance.md)   
 [性能提示和技巧](../core/performance-tips-and-tricks.md)   
 [MessageBox 性能计数器](../core/message-box-performance-counters.md)