---
title: 向外扩展数据库 |Microsoft Docs
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
ms.openlocfilehash: 6ca93333f1588a91df6b62641c30c684ac977237
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309367"
---
# <a name="scaled-out-databases"></a>向外扩展数据库
若要提供高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，配置 Windows 群集中运行 SQL Server 的两台计算机。 这些计算机可以运行在主动/主动或主动/被动配置中以实现冗余和数据存储在共享驱动器 (例如 RAID 1 + 0 SCSI 磁盘阵列) 或存储区域网络 (SAN)。  
  
 如果出于任何原因，SQL Server 服务将变得不可用，则数据库群集会将资源从主动计算机传输到被动计算机。 在此故障转移过程中，BizTalk Server 服务实例遇到数据库连接失败，并自动重新启动以重新连接到数据库。 正常运行的数据库计算机 （以前的被动计算机） 开始处理故障转移期间假设资源后的数据库连接。  
  
## <a name="running-multiple-messagebox-databases"></a>运行多个 MessageBox 数据库  
 若要增强的可伸缩性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，可以配置 BizTalk Server 跨多个 MessageBox 数据库中存储数据。 当您运行配置向导时创建的第一个 MessageBox 数据库。 此 MessageBox 数据库是主 MessageBox 数据库。 在 BizTalk Server 部署中没有一个主 MessageBox 数据库。 主 MessageBox 数据库包含主订阅信息，并将消息路由到相应的 MessageBox 数据库。 通常情况下，你想要将专用主 MessageBox，以执行仅路由 (选择**禁止发布新消息**)，并让其他 MessageBox 数据库进行处理。  
  
 当主 MessageBox 数据库接收到新的激活消息，业务流程或订阅消息的新实例，主 MessageBox 数据库将分发到下一个可用的 MessageBox 数据库的激活消息。 例如，如果您有一个主 MessageBox 数据库和两个 MessageBox 数据库，主 MessageBox 数据库将第一个激活消息路由到 MessageBox 数据库 1、 第二个激活消息到 MessageBox 数据库 2、 第三个激活消息到 MessageBox 数据库 1，轮循机制模式中，依此类推。 主 MessageBox 数据库使用内置逻辑来进行负载平衡，并且无需其他负载平衡机制。  
  
 主 MessageBox 数据库将激活消息路由到特定的 MessageBox 数据库 （例如，MessageBox 数据库 1） 后，业务流程将进入内存并运行。 如果业务流程必须等待一条消息，并且等待时间超过几秒钟，业务流程保存回 MessageBox 数据库 1。 业务流程正在等待相关消息。 相关消息到达主 MessageBox 数据库，该消息执行查找操作数据库中包含的相关消息 （在此示例中，MessageBox 1） 的状态的 MessageBox 数据库。 然后，主 MessageBox 数据库将消息传送到包含业务流程的 MessageBox 数据库。 业务流程将返回到内存中以继续处理直到它完成或必须等待另一个相关消息。  
  
 BizTalk Server MessageBox 数据库中存储的所有状态和每个 MessageBox 数据库包含不同的业务流程的状态信息。 出于可靠性考虑，您必须群集所有 MessageBox 数据库，包括主和辅助 MessageBox 数据库。  
  
 若要配置多个 MessageBox 数据库，您使用 BizTalk 管理控制台来添加运行 SQL Server 的计算机。 从管理角度看，只需添加新的 MessageBox 数据库。 BizTalk Server 自动处理激活消息的轮循机制分布，并将相关消息发送到相应的 MessageBox 数据库。  
  
 如果在环境中配置多个 MessageBox 数据库应为你的 BizTalk Server 组中创建 3 个 MessageBox 数据库的最小值和应禁止主 MessageBox 上的发布消息。 此建议是因为，添加其他 MessageBox 数据库可能会产生开销通过 MessageBox 数据库之间路由消息的主 MessageBox 数据库。 如果只配置 2 个 MessageBox 数据库按主 MessageBox 的消息路由的系统开销偏移大部分其他 MessageBox 数据库所获得的权益。  
  
## <a name="providing-high-availability-for-multiple-messagebox-databases"></a>为多个 MessageBox 数据库提供高可用性  
 添加到 MessageBox 数据库时你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署提高了可伸缩性，它不提供高可用性，因为每个 MessageBox 数据库是唯一和独立和可能是单点为 BizTalk Server 的故障环境。 若要添加冗余包括： 配置每个 MessageBox 数据库的服务器群集。 BizTalk Server 将数据分发跨多个 MessageBox 数据库，因此数据库不共享数据或情况下没有服务器群集提供冗余。  
  
## <a name="providing-high-availability-for-the-biztalk-tracking-database"></a>为 BizTalk 跟踪数据库提供高可用性  
 具体取决于您的特定部署的要求，你可能想要隔离到单独的 SQL Server 计算机上的 BizTalk 跟踪数据库，从而增强跟踪性能并通过创建单独的 BizTalk 主机专用于跟踪的主机。 如果你的部署具有高吞吐量，并且涉及到跟踪大量数据的这些消息，则跟踪系统开销可能会使用运行 SQL Server 的计算机上的大量资源。 如果出现这种情况，并且传入消息的速率很高继续[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到达的点，它无法处理新消息，因为跟踪消息所需的资源比运行其他 BizTalk Server 所需的资源组件 （如接收消息并将其保存到 MessageBox 数据库）。  
  
 若要提高性能和安全性，建议将专门用于跟踪不包含任何其他项 （如接收位置、 业务流程或管道） 的主机和处理和发送主机禁用从接收的跟踪。 若要为跟踪主机提供高可用性，创建多个跟踪主机的主机实例。  
  
 对于每个 MessageBox 数据库，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]只使用一个跟踪主机实例将消息从 MessageBox 数据库移至 BizTalk 跟踪数据库 (BizTalkDTADb)。 如果其他计算机运行的跟踪主机实例，BizTalk Server 将会自动向外的每个 MessageBox 数据库跟踪主机的单独实例的处理。 如果 MessageBox 数据库的数量大于许多跟踪主机实例、 一个或多个跟踪主机实例将服务多个 MessageBox 数据库。  
  
 若要为 BizTalk 跟踪数据库提供高可用性，使用 Windows 群集配置中的主动/被动配置运行 SQL Server 的两台数据库计算机。  
  
## <a name="providing-high-availability-for-the-bam-databases"></a>为 BAM 数据库提供高可用性  
 业务活动监视 (BAM) 提供了独立于 IT 实施或跨异类 IT 实施的业务流程的可见性。 BAM SQL Server 数据库 （BAM 星型架构数据库、 BAM 主导入数据库和 BAM 存档数据库） 和 BAM 分析数据库存储不同于操作监视数据的业务活动数据。 若要确保 BAM 基础结构是高可用，请执行以下操作：  
  
- **群集 BAM 主导入数据库和 BAM 分析数据库。** BAM 主导入数据库是业务活动监视系统的中心。 因此是重要，确保此数据库高度可用通过使用 Windows 群集，请按照下面的两个建议，以防止此数据库被填满。 BAM 分析数据库是存储业务分析员使用来生成活动聚合和 OLAP 多维数据集的数据的 Analysis Services 数据库，因此此数据库的任何停机时间会影响他们的工作效率。 尽管不必群集 BAM 存档数据库，我们建议你监视事件日志错误，以确保数据已传输成功，并因此监视数据库的大小，Data Transformation Services (DTS) 包运行时可以替换它之前它填充了。  
  
- **定义联机时段。** 若要为更高的性能并避免故障，BAM BAM 主导入数据库中的数据到表时活动的完成基于时间戳。 BAM 来实现此通过定期交换已完成的表与另一个空表的格式完全相同。 BAM 完成此操作后，其他已完成的活动会进入新分区 （表），而 BAM 将保留旧分区中的联机时段定义的时间。 必须定义联机时段以确保 BAM 主导入数据库中的分区数变得不太大。 有关安排联机时段的详细信息，请参阅"存档主导入数据库数据"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
- **安排 DTS 包定期运行。** 定义联机时段可确保 BAM 主导入数据库不会填满旧活动分区。 此外必须安排 DTS 包定期运行，若要创建新分区的活动数据，并将数据从 BAM 主导入数据库中的旧分区移到 BAM 存档数据库。 有关安排 DTS 包的详细信息，请参阅"安排 DTS 包"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
- **请仔细选择几小组数据项 （检查点），并避免包括不必要的数据的项定义某个活动时。**  
  
- **了解在设计聚合时的计划扫描和实时聚合之间权衡。** 实时聚合由 SQL Server 触发器自动维护，并且没有延迟。 它非常适合于某些关键的低延迟方案，但它会导致性能成本每当事件被写入到 BAM 主导入数据库。 计划的聚合依赖于计划的多维数据集 DTS 包，以更新其聚合数据。 其延迟时间等于或大于 DTS 计划时间间隔，但整体对 BAM 主导入数据库的性能影响更小。  
  
- **如果您选择计划的聚合，请确保计划频率高于存档 DTS 运行多维数据集 DTS。** 这是因为存档 DTS 不会移动到 BAM 存档数据库的计划聚合处理的活动数据。  
  
- **启用 BAM 事件总线服务在多台计算机中获取故障转移功能。**  
  
## <a name="providing-high-availability-for-the-other-biztalk-server-databases"></a>为其他 BizTalk Server 数据库提供高可用性  
 若要为其他提供高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，配置 Windows 群集中运行 SQL Server 的两台计算机。 这些计算机可以运行在主动/主动或主动/被动配置中以实现冗余和数据存储在共享驱动器 (例如 RAID 1 + 0 SCSI 磁盘阵列) 或存储区域网络 (SAN)。  
  
## <a name="see-also"></a>请参阅  
 [为 BizTalk 主机提供高可用性](../core/providing-high-availability-for-biztalk-hosts.md)   
 [为 BizTalk Server 数据库提供高可用性](../core/providing-high-availability-for-biztalk-server-databases.md)   
 [BizTalk Server 高可用性示例方案](../core/sample-biztalk-server-high-availability-scenarios.md)