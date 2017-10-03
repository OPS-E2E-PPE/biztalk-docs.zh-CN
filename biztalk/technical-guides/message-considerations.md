---
title: "消息注意事项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ca466fa-426c-46f6-a400-747ff51ff8f4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5499c9535ff822dfec8097185ef17d8d7999e1f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-considerations"></a>消息注意事项
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供一套全面的功能发送、 接收、 转换和处理消息。 这些功能包括：  
  
-   能够发送和接收使用多个行业标准传输，如 HTTP、 SMTP、 FTP/FTPS 和 WCF 的消息。 使用完成针对发送和接收消息的传输级支持[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器。 集成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用各种"业务线"处理的消息 (LOB) 应用程序使用许多可用之一来完成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]加速器或多个适配器，如 HIPAA、 BizTalk Accelerator for SWIFT，BizTalk 快捷键或 BizTalk SAP 适配器。 这些快捷键和适配器符合行业标准其中反过来可容纳的简单集成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与符合特定的行业标准的系统。  
  
-   能够处理多个消息格式，如纯文本、 XML、 二进制和其他人。 此功能至关重要提供集成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]具有广泛的贸易合作伙伴。  
  
-   支持的消息转换或文档映射。 映射能够适应不同的架构之间的数据的转换。 例如，映射无法用于将接收的客户采购订单的内容转换为与传送通知的发送回客户回执。  
  
-   BizTalk Server 业务流程提供用于创建跨时间、 组织、 应用程序和人员的业务流程的功能。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供用于开发包括支持事务 （传统"原子"MSDTC 类型和长时间运行） 的业务流程的业务流程设计器图形界面异常处理、 调试、 跟踪和调用扩展性外部代码。  
  
    > [!NOTE]  
    >  请参阅[优化业务流程性能](../technical-guides/optimizing-orchestration-performance.md)有关使用中的业务流程时应遵循最佳做法指南[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 请参阅主题[创建业务流程使用 Orchestration 设计器](http://go.microsoft.com/fwlink/?LinkId=158997)(http://go.microsoft.com/fwlink/?LinkId=158997) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档了解有关使用 Orchestration 设计器的深入信息。  
  
 本主题的其余部分介绍了与在中处理的消息的大小、 复杂性和分发配置文件相关的性能注意事项[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]环境。  
  
## <a name="message-size-considerations"></a>消息大小考虑事项  
 BizTalk Server 规定了对消息大小没有限制，而实际限制和依赖项可能要求你为了尽量减少你的消息的大小，因为大消息需要更多的处理资源。 按消息大小增加，总体吞吐量 （每秒处理的消息） 会降低。 当设计你的方案和规划容量，请考虑平均消息大小、 消息类型和 BizTalk 服务器处理的消息数。 不要使用不必要地长属性和标记名称;如果可能，使时长保持在 50 个字符。 例如，不使用仅有 1 个字节的消息大小的 200 个字符标记名称。  
  
 如果收到的消息的内存中大小超过 （可配置 BizTalk Server 管理控制台中的 BizTalk 组的组属性页上） 最大的消息片段大小为指定的字节数，消息拆分为片段指定的大小。 此外，片段写入 Messagebox 的 Microsoft 分布式事务处理协调器 (MSDTC) 事务上下文，如下所示：  
  
1.  如果现有 MSDTC 事务的上下文中发布的传入消息后，BizTalk MessageBox 数据库中写入的消息片段时，则使用此事务。 例如，如果由事务适配器配置为需要事务发布的传入消息后，现有的事务将使用的消息片段写入 MessageBox 数据库时。  
  
2.  如果传入的消息未发布的现有 MSDTC 事务的上下文中，会创建一个新的 MSDTC 事务的消息片段写入 MessageBox 数据库。 在此方案中，下列注意事项适用：  
  
    -   值增加**大型消息片段大小**以减少大型消息已分段且减少创建关联的 MSDTC 事务的发生的频率。 因此应该增大此值，因为过多使用 MSDTC 事务将极大地影响系统性能。 请注意，增大此值还可能增加要使用的可用内存量。  
  
    -   如果所用时间长于 60 分钟将消息写入到 MessageBox 的最大允许 MSDTC 事务超时，事务将会超时，发生错误，并且尝试将消息写入失败且不回滚。 **大型消息片段大小**值应增加足以处理非常大的消息时避免此问题。 根据可用内存的大小，可将此值提高到 1000000 字节的最大值。  
  
    -   消息中的每个消息片段都可针对 MessageBox 数据库创建一个或多个 SQL Server 数据库锁定。 当锁的数目超过几个几十万时，有可能，SQL Server 将生成"超出锁"错误。 如果出现此问题，增加的值**大型消息片段大小**以减少碎片数 （这将降低对 MessageBox 数据库的 SQL Server 数据库锁的数目） 或请考虑住房你MessageBox 64 位版本的 SQL Server 上的数据库。 可用锁的数目是明显更高，比 SQL server 上的 SQL Server 的 32 位版本的 64 位版本上。 可以使用以下公式来估计每交换消息的最大数 MessageBox 数据库驻留在 32 位版本的 SQL Server 时：  
  
        ```  
        200,000 / (Number of CPUs * BatchSize * MessagingThreadPoolSize)  
        ```  
  
 BizTalk Server 如何处理大消息，包括用于处理大消息的指南的详细信息请参阅[如何 BizTalk 服务器进程大消息](http://go.microsoft.com/fwlink/?LinkID=154680)(http://go.microsoft.com/fwlink/?LinkID=154680)。  
  
## <a name="message-type-considerations"></a>消息类型注意事项  
 到 BizTalk Server 中两个主要格式之一接收消息： XML 文件或平面文件。 消息类型应始终体现消息分布配置文件由于 XML 以及平面文件消息的资源要求不尽相同。  
  
-   **XML 文件**顺序 BizTalk Server 来执行任何处理以外传递路由的消息，消息必须为 XML 文件格式。  
  
-   **平面文件**BizTalk Server 才能执行传递路由以外的任何处理平面文件必须解析为 XML 格式。 将平面文件解析为 XML 文件将极大地增加文件大小。 因为平面文件不包含带有关于其数据的描述性信息的 XML 标记。 另一方面，XML 文件还在描述性 XML 标记中包装了其所有数据。 在某些情况下，分析可以增加平面文件的大小的 10 个或多个，具体取决于多少描述性的数据包含在该文件的 XML 标记的因素。  
  
-   **平面文件文档包装在 XML 文档中的单个 CDATA 部分节点**这种类型的文档为 XML 和平面文件的组合，并且通常是占用大量内存的则整个由于 BizTalk Server 必须加载包装到平面文件文档在处理它之前的内存。  
  
## <a name="overload-considerations"></a>重载注意事项  
 大多数 BizTalk 服务器应用程序不会收到消息的特定的常量的速率。 通常情况下，消息处理受到高峰和低谷。 例如，联机银行应用程序可能处理更多消息的第一波在清晨，然后在中间天，然后在一天结束。 BizTalk Server 解决方案应进行测试以确保它们都将能够处理这些重载方案。 若要确定解决方案可以处理与 BizTalk Server 重载方案的程度，应确定 BizTalk Server 解决方案的最大可持续吞吐量 (MST)。 MST 是一个系统可以无限期地处理在生产环境中的消息流量的最高负载。 有关 MST 的详细信息，请参阅[持续性能规划](http://go.microsoft.com/fwlink/?LinkID=158065)(http://go.microsoft.com/fwlink/?LinkID=158065) 和[什么是可持续的性能？](http://go.microsoft.com/fwlink/?LinkID=132304) (http://go.microsoft.com/fwlink/?LinkID=132304) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档。  
  
## <a name="schema-complexity"></a>架构复杂性  
 分析 （尤其是平面文件分析） 的消息吞吐量受影响的架构的复杂性。 随着架构复杂性增加，总体性能会降低。 在设计时架构，减少节点名称的长度，并将升级的属性移到架构的顶部。 这可以减少检索时间并从而提高性能。  
  
## <a name="map-complexity"></a>映射复杂性  
 根据映射的复杂性，映射表转换可能占用大量资源。 作为映射复杂性增加，总体性能下降。 若要提高整体性能，尽量减少链接和 functoid 在你的映射，尤其是调用数据库查找 functoid 等外部资源的 functoid 中使用的数。  
  
## <a name="flat-file-parsing-considerations"></a>平面文件分析注意事项  
 对分析平面文件的性能影响最大的两个因素是文件大小和架构复杂性。 不明确的架构是架构包含多个可选字段。 大文件大小使用时，具有可选的多个字段的架构会降低性能，因为较大的文件可能匹配的架构的不同分支。 架构复杂性对较小的文件，比上较大的文件的影响更小。  
  
## <a name="see-also"></a>另请参阅  
 [优化 BizTalk Server 应用程序](../technical-guides/optimizing-biztalk-server-applications.md)