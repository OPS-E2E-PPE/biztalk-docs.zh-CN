---
title: 向外扩展的数据库 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, databases [BAM]
- databases [BAM], high availability
- Archive database [BAM]
- Analysis database [BAM], high availability
- high availability, databases [BAM]
- MessageBox database, master database
- scaling, databases [BAM]
- scaling, BizTalk Server
- MessageBox database, multiple databases
- MessageBox database, clustering
- databases [BAM], scaling
- MessageBox database, routing
- Tracking database, scaling
- Primary Import database [BAM], clustering
- high availability, MessageBox database
- databases [BAM], performance
- Star Schema database [BAM]
- MessageBox database, high availability
- messages, disabling
- MSMQT adapters, See MSMQ adapters
- clustering, Analysis database [BAM]
- Windows Message Queuing
- MessageBox database
- Analysis database [BAM], clustering
- DTS packages, scheduling
ms.assetid: e02edc0d-1c51-4b97-be04-0feb787089ac
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0af465c1cd77bfb96cc44e1a3209757ee13129be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22272077"
---
# <a name="scaled-out-databases"></a>向外扩展的数据库
若要确保 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库具有高度可用性，请在 Windows 群集中配置两台运行 SQL Server 的计算机。 这两台计算机可以使用主动/主动配置或主动/被动配置运行以便实现冗余，还可以在共享驱动器（例如 RAID 1+0 SCSI 磁盘阵列）或存储区域网络 (SAN) 上存储数据。  
  
 如果 SQL Server 服务由于某种原因不可用，则数据库群集会将资源从主动计算机传输到被动计算机。 在此故障转移过程中，BizTalk Server 服务实例会遇到数据库连接失败，这些实例将自动重新启动以重新连接到数据库。 采用故障转移期间传输的资源后，正在运行的数据库计算机（即前面提到的被动计算机）将开始处理数据库连接。  
  
## <a name="running-multiple-messagebox-databases"></a>运行多个 MessageBox 数据库  
 若要增强的可伸缩性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，你可以配置 BizTalk Server 来跨多个 MessageBox 数据库中存储数据。 运行配置向导时创建第一个 MessageBox 数据库。 此 MessageBox 数据库为主 MessageBox 数据库。 BizTalk Server 部署中只能有一个主 MessageBox 数据库。 主 MessageBox 数据库包含主订阅信息，并将消息路由到相应的 MessageBox 数据库。 通常情况下，你想要专门进行路由仅 master 的 MessageBox (选择**禁用新消息发布**)，并让其他 MessageBox 数据库进行处理。  
  
 当主 MessageBox 数据库接收到新的激活消息（业务流程的崭新实例或订阅消息）时，主 MessageBox 数据库会将该激活消息分发给下一个可用的 MessageBox 数据库。 例如，如果您有一个主 MessageBox 数据库和两个 MessageBox 数据库，主 MessageBox 数据库会将第一个激活消息路由到 MessageBox 数据库 1、将第二个激活消息路由到 MessageBox 数据库 2、将第三个激活消息路由到 MessageBox 数据库 1，然后按循环法模式依此类推。 主 MessageBox 数据库使用内置逻辑来提供负载平衡，因此不需要其他的负载平衡机制。  
  
 当主 MessageBox 数据库将激活消息路由到特定 MessageBox 数据库（例如，MessageBox 数据库 1）后，业务流程将进入内存并运行。 如果业务流程必须等待一条消息，并且等待时间的长度超过几秒钟，业务流程将保留回 MessageBox 数据库 1。 业务流程正在等待相关消息。 当相关消息到达主 MessageBox 数据库后，该消息将在数据库中对包含相关消息状态的 MessageBox 数据库（在此示例中，即 MessageBox 1）执行查找操作。 然后，主 MessageBox 数据库将该消息传送到包含相应业务流程的 MessageBox 数据库。 之后，该业务流程将返回到内存中继续进行处理，直至该流程完成或必须等待其他相关消息。  
  
 BizTalk Server 将所有状态存储在 MessageBox 数据库中，其中每个 MessageBox 数据库包含不同业务流程的状态信息。 为实现可靠性，必须群集所有 MessageBox 数据库，包括主 MessageBox 数据库和辅助 MessageBox 数据库。  
  
 若要配置多个 MessageBox 数据库，你使用 BizTalk 管理控制台将运行 SQL Server 的计算机。 从管理角度来看，您只需添加新的 MessageBox 数据库。 BizTalk Server 将自动处理激活消息的循环分发，并将相关消息发送给相应的 MessageBox 数据库。  
  
 如果在环境中配置了多个 MessageBox 数据库，则应为 BizTalk Server 组仅创建最少三个 MessageBox 数据库，并禁止主 MessageBox 上发布新消息。 我们之所以提出此建议，是因为添加额外的 MessageBox 数据库会导致主 MessageBox 数据库在 MessageBox 数据库之间路由消息时的系统开销。 如果只配置两个 MessageBox 数据库，那么另一个 MessageBox 数据库所获得的大部分好处将与主 MessageBox 数据库路由消息时的系统开销抵销。  
  
## <a name="providing-high-availability-for-multiple-messagebox-databases"></a>取保多个 MessageBox 数据库高度可用  
 添加到 MessageBox 数据库时你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署能够提高可伸缩性，它不提供高可用性，因为每个 MessageBox 数据库是唯一且独立的并且可能是单点故障的 BizTalk Server环境。 若要添加冗余，则需要为每个 MessageBox 数据库配置一个服务器群集。 BizTalk Server 跨多个 MessageBox 数据库分发数据，因此，这些数据库不共享数据，也不在未进行服务器群集的情况下提供冗余。  
  
## <a name="providing-high-availability-for-the-biztalk-tracking-database"></a>确保 BizTalk 跟踪数据库高度可用  
 根据特定部署的不同要求，您可能希望通过将 BizTalk 跟踪数据库隔离到单独的 SQL Server 计算机上并创建专用于主机跟踪的单独 BizTalk 主机来增强跟踪性能。 如果部署需要高吞吐量并且需要为这些消息跟踪大量数据，则跟踪系统开销可能会消耗运行 SQL Server 的计算机上的大量资源。 如果出现这种情况而且以后继续传入消息的速率很高，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]达到某个点时，它无法处理新消息，因为跟踪消息所需的资源比运行其他 BizTalk Server 所需的资源组件 （如接收消息并将它们保存到 MessageBox 数据库）。  
  
 为了提高性能和安全性，建议您将一台不包含其他任何项目（例如接收位置、业务流程或管道）的主机专用于跟踪，并且禁止从接收主机、处理主机和发送主机进行跟踪。 若要确保跟踪主机高度可用，请创建跟踪主机的多个主机实例。  
  
 对于每个 MessageBox 数据库，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用只有一个跟踪要将消息从 MessageBox 数据库移到 BizTalk 跟踪数据库 (BizTalkDTADb) 的主机实例。 如果其他计算机运行该跟踪主机的实例，则 BizTalk Server 会自动将每个 MessageBox 数据库的处理扩展到该跟踪主机的单独实例。 如果 MessageBox 数据库数大于跟踪主机实例数，则一个或多个跟踪主机实例将为多个 MessageBox 数据库提供服务。  
  
 若要确保 BizTalk 跟踪数据库具有高可用性，请使用 Windows 群集来配置两台使用主动/被动配置运行 SQL Server 的数据库计算机。  
  
## <a name="providing-high-availability-for-the-bam-databases"></a>确保 BAM 数据库高度可用  
 使用业务活动监视 (BAM)，您可以对独立于 IT 实施或跨异类 IT 实施的业务流程一目了然。 BAM SQL Server 数据库（BAM 星型架构数据库、BAM 主导入数据库和 BAM 存档数据库）和 BAM 分析数据库存储了不同于操作监视数据的业务活动数据。 为确保 BAM 基础结构高度可用，执行以下操作：  
  
-   **群集 BAM 主导入数据库和 BAM 分析数据库。** BAM 主导入数据库是业务活动监视系统的中心。 因此，通过使用 Windows 群集来确保此数据库高度可用并遵循以下两条建议以防止此数据库被填满是十分重要的。 BAM 分析数据库是存储业务分析员用于生成活动聚合和 OLAP 多维数据集的数据的 Analysis Services 数据库。因此，此数据库的任何故障都会影响业务分析员的工作效率。 尽管不必群集 BAM 存档数据库，我们仍建议您在运行数据转换服务 (DTS) 包时监视错误的事件日志以确保数据已成功传输并同时监视数据库的大小以便在数据库被填满前将其替换。  
  
-   **定义联机窗口。** 为提高性能并避免故障，BAM 根据完成活动时的时间戳将 BAM 主导入数据库中的数据划分到多个表中。 BAM 通过定期将另一个相同格式的空表与已完成的表进行交换来实现此操作。 BAM 完成此操作后，尽管 BAM 会在联机时段中定义的时间内保留旧分区，但其他已完成的活动将进入新分区（表）。 必须定义联机时段以确保 BAM 主导入数据库中的分区数不会变得过大。 有关安排联机时段的详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的“存档主导入数据库数据”。  
  
-   **计划定期运行的 DTS 包。** 定义联机时段可确保 BAM 主导入数据库不会被旧活动分区填满。 您还必须安排 DTS 包定期运行，以便为活动数据创建新的分区并将 BAM 主导入数据库内旧分区中的数据移至 BAM 存档数据库中。 有关安排 DTS 包的详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的“安排 DTS 包”。  
  
-   **小心地选择小型集的数据项 （检查点），并避免定义活动时包括不必要的数据的项目。**  
  
-   **了解计划和实时聚合设计你的聚合时权衡。** 实时聚合由 SQL Server 触发器自动进行维护并且没有延迟。 对于某些需要延迟时间短的关键方案，实时聚合是理想之选，但在向 BAM 主导入数据库中写入事件时该聚合会带来性能开销。 计划聚合依赖于计划的多维数据集 DTS 包来更新其聚合数据。 其延迟时间等于或大于 DTS 计划时间间隔，但大体上该聚合对 BAM 主导入数据库的性能影响较小。  
  
-   **如果你选择计划的聚合，请确保您计划 cubing DTS 比存档 DTS 更频繁地运行。** 这是因为存档 DTS 不会将已为计划聚合处理的活动数据移至 BAM 存档数据库中。  
  
-   **启用 BAM 事件总线服务在多台计算机中获取故障转移功能。**  
  
## <a name="providing-high-availability-for-the-other-biztalk-server-databases"></a>确保其他 BizTalk Server 数据库高度可用  
 若要确保其它 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库的高度可用性，请在 Windows 群集中配置两台运行 SQL Server 的计算机。 这两台计算机可以使用主动/主动配置或主动/被动配置运行以便实现冗余，还可以在共享驱动器（例如 RAID 1+0 SCSI 磁盘阵列）或存储区域网络 (SAN) 上存储数据。  
  
## <a name="see-also"></a>另请参阅  
 [为 BizTalk 主机提供高可用性](../core/providing-high-availability-for-biztalk-hosts.md)   
 [为 BizTalk Server 数据库提供高可用性](../core/providing-high-availability-for-biztalk-server-databases.md)   
 [示例 BizTalk Server 高可用性方案](../core/sample-biztalk-server-high-availability-scenarios.md)