---
title: 消息注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ca466fa-426c-46f6-a400-747ff51ff8f4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9981dbce13f613afeb5c061a96d319cddd6c5c94
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298446"
---
# <a name="message-considerations"></a>消息注意事项
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供发送、 接收、 转换和处理消息的一组广泛的功能。 这些功能包括：  
  
- 若要发送和接收消息使用多个行业标准传输，如 HTTP、 SMTP、 FTP/FTPS 和 WCF 的功能。 针对发送和接收消息的传输级支持通过[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器。 集成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用各种"的业务线"消息处理 (LOB) 应用程序使用许多可用之一来完成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]加速器或适配器，如 BizTalk Accelerator for HIPAA，BizTalk Accelerator for SWIFT或 BizTalk SAP 适配器。 这些加速器和适配器符合行业标准，其中又可容纳的简单集成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与符合特定的行业标准的系统。  
  
- 处理多个消息格式，如纯文本、 XML、 二进制和其他功能。 此功能对提供的集成至关重要[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]范围广泛的贸易合作伙伴使用。  
  
- 对消息的转换或文档映射的支持。 映射可容纳不同的架构之间的数据转换。 例如，可以使用映射将接收的客户采购订单的内容转换为与发送回客户传送通知回执。  
  
- BizTalk Server 业务流程提供用于创建跨时间、 组织、 应用程序和人员的业务流程的功能。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供了业务流程设计器图形界面来开发业务流程，包括支持事务 （传统"原子"MSDTC 类型和长时间运行），异常处理、 调试、 跟踪和调用的可扩展性外部代码。  
  
  > [!NOTE]
  >  请参阅[优化业务流程性能](../technical-guides/optimizing-orchestration-performance.md)有关使用中的业务流程时应遵循最佳做法指南[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 请参阅主题[业务流程使用业务流程设计器创建](http://go.microsoft.com/fwlink/?LinkId=158997)(<http://go.microsoft.com/fwlink/?LinkId=158997>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档了解有关使用业务流程设计器的深入信息。  
  
  本主题的其余部分介绍了与 BizTalk Server 环境中处理的消息的大小、 复杂性和分发配置文件相关的性能注意事项。  
  
## <a name="message-size-considerations"></a>消息大小注意事项  
 BizTalk Server 规定了对消息大小没有限制，而实际限制和依赖项可能要求你尽量减少消息的大小，因为大型消息需要更多的处理资源。 为消息大小的增加，整体吞吐量 （每秒处理的消息） 会降低。 当设计使用方案和计划容量，请考虑平均消息大小、 消息类型和 BizTalk Server 处理的消息数。 不要使用不必要地长属性和标记名称;如果可能，请保留长度少于 50 个字符。 例如，不使用只有 1 个字节的消息大小为 200 个字符标记名称。  
  
 如果收到的消息的内存中大小超过为大消息片断大小 （可在 BizTalk Server 管理控制台中的 BizTalk 组的组属性页上配置） 指定的字节数，该消息将拆分为的片段指定的大小。 此外，这些片段写入 Messagebox Microsoft 分布式事务处理协调器 (MSDTC) 事务的上下文，如下所示：  
  
1. 如果正在现有的 MSDTC 事务上下文中发布传入消息，消息片段写入到 BizTalk MessageBox 数据库时使用此事务。 例如，如果配置为需要事务的事务性适配器正在发布传入消息，现有的事务将使用的消息片段写入 MessageBox 数据库时。  
  
2. 如果不现有的 MSDTC 事务上下文中发布传入消息，被创建一个新的 MSDTC 事务的消息片段写入 MessageBox 数据库。 在此方案中，以下注意事项适用：  
  
   -   值增加**大消息片段大小**来降低的频率与大消息被分割为碎片，并减少创建关联的 MSDTC 事务的发生率。 这样应做因为过多使用 MSDTC 事务将极大地影响系统性能。 请注意，增加此值还可以增加使用的可用内存量。  
  
   -   如果它花费的时间超过 60 分钟，可将消息写入到 MessageBox 的最大允许 MSDTC 事务超时，事务超时时，出现错误，并且写入消息的尝试失败，且不回滚。 **大消息片段大小**值应足够大才能在处理非常大的消息时避免出现此问题。 具体取决于可用内存，此值应提高到 1000000 字节的最大值。  
  
   -   在消息中的每个消息片段将创建一个或多个 SQL Server 数据库锁定对 MessageBox 数据库。 当锁的数目超过数十万时，很可能 SQL Server 将生成"内存不足"错误。 如果出现此问题，请增加的值**大消息片段大小**以减少 （这将降低对 MessageBox 数据库所做的 SQL Server 数据库锁的数目） 的片段数或考虑底座你在 64 位版本的 SQL Server 的 MessageBox 数据库。 可用锁的数目是比 SQL Server 的 32 位版本的 SQL Server 上的 64 位版本上高得多。 可以使用下面的公式估算时 MessageBox 数据库存储在 SQL Server 的 32 位版本上可用的最大的每个交换的消息数：  
  
       ```  
       200,000 / (Number of CPUs * BatchSize * MessagingThreadPoolSize)  
       ```  
  
   有关 BizTalk Server 如何处理大消息，包括处理大消息的指导原则的详细信息请参阅[如何 BizTalk Server 处理大消息](http://go.microsoft.com/fwlink/?LinkID=154680)(http://go.microsoft.com/fwlink/?LinkID=154680)。  
  
## <a name="message-type-considerations"></a>消息类型注意事项  
 BizTalk server 以两种主要格式之一接收消息：XML 文件或平面文件。 消息类型都应始终考虑到消息分发配置文件的 XML 和平面文件消息的不同资源要求。  
  
-   **XML 文件**使 BizTalk Server 之外传递路由的消息执行任何处理，消息必须为 XML 文件格式。  
  
-   **平面文件**BizTalk Server 可以执行任何处理而不是直通路由之前，必须为 XML 格式解析平面文件。 将平面文件解析到一个 XML 文件可以极大地增加文件的大小。 平面文件不包含有关其数据的描述性信息的 XML 标记。 XML 文件，但是，包装其所有数据在描述性 XML 标记。 在某些情况下，分析可以将大小增加的平面文件的文件的 XML 标记中包含的 10 个或多个，具体取决于多少描述性数据的因素。  
  
-   **平面文件文档包装在 XML 文档中的单个 CDATA 部分节点**这种类型的文档是 XML 文件和平面文件的组合，并且通常是占用大量内存的因为 BizTalk Server 必须加载整个包装到的平面文件文档在处理它之前的内存。  
  
## <a name="overload-considerations"></a>重载注意事项  
 大多数 BizTalk Server 应用程序不会收到消息以特定的常量的速率。 通常情况下，消息处理受到的高峰和低谷。 例如，联机银行业务应用程序可以处理更多的消息首先要做的事情在第二天早上，然后在中间天，并在一天结束时。 BizTalk Server 解决方案应进行测试以确保它们能够处理这些重载的方案。 若要确定 BizTalk Server 解决方案可以处理重载方案的程度，应确定 BizTalk Server 解决方案的最大可承受吞吐量 (MST)。 MST 是一个系统可以无限期地处理在生产环境中的消息流量的最高负载。 有关 MST 的详细信息，请参阅[规划可持续性能](http://go.microsoft.com/fwlink/?LinkID=158065)(<http://go.microsoft.com/fwlink/?LinkID=158065>) 和[可承受性能？](http://go.microsoft.com/fwlink/?LinkID=132304) (<http://go.microsoft.com/fwlink/?LinkID=132304>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档。  
  
## <a name="schema-complexity"></a>架构复杂性  
 架构的复杂性会影响分析 （尤其是平面文件解析） 的消息吞吐量。 随着架构复杂性的增加，总体性能下降。 在设计时架构，减少的节点名称的长度，并将升级的属性移到架构的顶部。 这可以减少检索时间，从而可以提高性能。  
  
## <a name="map-complexity"></a>映射复杂性  
 根据所映射的复杂性，映射表转换可以是需要消耗大量资源。 为映射复杂性增加，总体性能下降。 若要提高整体性能，最大程度减少链接和 functoid 在映射中，尤其是调用外部资源，例如数据库查找 functoid 的 functoid 中使用的数量。  
  
## <a name="flat-file-parsing-considerations"></a>平面文件解析注意事项  
 对平面文件分析的性能最高影响的两个因素是文件大小和架构的复杂性。 不明确的架构是包含很多可选字段的架构。 如果使用大型文件大小时，具有许多可选字段的架构会降低性能，因为较大的文件可能匹配的架构的不同分支。 架构复杂性上比对较大的文件较小的文件具有的影响更小。  
  
## <a name="see-also"></a>请参阅  
 [优化 BizTalk Server 应用程序](../technical-guides/optimizing-biztalk-server-applications.md)