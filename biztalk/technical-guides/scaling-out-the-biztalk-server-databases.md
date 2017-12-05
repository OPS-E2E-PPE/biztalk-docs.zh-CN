---
title: "缩放 BizTalk Server 数据库的扩展 |Microsoft 文档"
ms.custom: 
ms.date: 11/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18853ceb-7975-4c30-878f-6b162005f795
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6df08cf225bde08d05a746ee2f0dcddd7cdddfb0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="scaling-out-the-biztalk-server-databases"></a>向外扩展 BizTalk Server Database
若要为 BizTalk Server 数据库提供高可用性，配置 Windows 群集中运行 SQL Server 的两台计算机。 这些计算机可以运行在主动/主动、 主动/被动或 （需要三台计算机） 的主动/主动/被动冗余配置并可以将数据存储在共享的驱动器 (如 RAID 1 + 0 SCSI 磁盘阵列) 或存储区域网络 (SAN)。  
  
如果 SQL Server 服务由于某种原因不可用，则数据库群集会将资源从主动计算机传输到被动计算机。 在此故障转移过程中，BizTalk Server 服务实例会遇到数据库连接失败，这些实例将自动重新启动以重新连接到数据库。 采用故障转移期间传输的资源后，正在运行的数据库计算机（即前面提到的被动计算机）将开始处理数据库连接。  
  
群集的 BizTalk Server 数据库已在[群集 BizTalk Server Databases2](../technical-guides/clustering-the-biztalk-server-databases2.md)。 本部分重点介绍向外扩展 BizTalk Server database 以提供高可用性。  
  
## <a name="providing-high-availability-for-the-biztalk-messagebox-database"></a>BizTalk MessageBox 数据库提供高可用性  
 本部分提供有关如何配置以实现高可用性的 BizTalk MessageBox 数据库信息。  
  
### <a name="running-multiple-messagebox-databases"></a>运行多个 MessageBox 数据库  
若要增强的可伸缩性的 BizTalk Server 数据库和地址 MessageBox 数据库 SQL Server 计算机上的高 CPU 利用率，你可以配置 BizTalk Server 来跨多个 MessageBox 数据库中存储数据。 运行配置向导时创建第一个 MessageBox 数据库。 此 MessageBox 数据库为主 MessageBox 数据库。 BizTalk Server 部署中只能有一个主 MessageBox 数据库。 主 MessageBox 数据库包含主订阅信息，并将消息路由到相应的 MessageBox 数据库。 通常情况下，你想要专门 master 的 MessageBox 数据库，以实现仅用于路由，并且让其他 MessageBox 数据库进行处理。 为了 MessageBox 数据库来实现仅用于路由，请选择**禁用新消息发布**从 BizTalk 管理控制台中的 MessageBox 属性。  
  
 处理流程的 MessageBox 数据库的一个示例是，如下所示：  
  
1.  当主 MessageBox 数据库接收到新的激活消息（业务流程的崭新实例或订阅消息）时，主 MessageBox 数据库会将该激活消息分发给下一个可用的 MessageBox 数据库。 例如，如果您有一个主 MessageBox 数据库和两个 MessageBox 数据库，主 MessageBox 数据库会将第一个激活消息路由到 MessageBox 数据库 1、将第二个激活消息路由到 MessageBox 数据库 2、将第三个激活消息路由到 MessageBox 数据库 1，然后按循环法模式依此类推。 主 MessageBox 数据库使用内置逻辑来提供负载平衡，因此不需要其他的负载平衡机制。  
  
2.  当主 MessageBox 数据库将激活消息路由到特定 MessageBox 数据库（例如，MessageBox 数据库 1）后，业务流程将进入内存并运行。  
  
3.  如果业务流程必须等待一条消息，并且等待时间的长度超过几秒钟，业务流程将保留回 MessageBox 数据库 1。 业务流程正在等待相关消息。  
  
4.  在相关消息到达 master MessageBox 数据库时，消息引擎将执行包含的相关消息 （在此示例中，MessageBox 1） 的状态的 MessageBox 数据库在数据库中的查找操作。 Master MessageBox 数据库将邮件传递到 MessageBox 数据库包含业务流程。  
  
5.  业务流程将恢复到内存中以便继续处理直到完成或它必须等待另一个相关消息。  
  
 BizTalk Server 将所有状态存储在 MessageBox 数据库中，其中每个 MessageBox 数据库包含不同业务流程的状态信息。 为实现可靠性，必须群集所有 MessageBox 数据库，包括主 MessageBox 数据库和辅助 MessageBox 数据库。  
  
 若要配置多个 MessageBox 数据库，你使用 BizTalk Server 管理控制台以添加正在运行 SQL Server 的计算机。 从管理角度来看，您只需添加新的 MessageBox 数据库。 BizTalk Server 将自动处理激活消息的循环分发，并将相关消息发送给相应的 MessageBox 数据库。  
  
 如果在你的环境中配置多个 MessageBox 数据库应为你的 BizTalk Server 组中创建三个 MessageBox 数据库的最少，并且应禁用在 master 数据库中的 MessageBox 消息发布。 此建议进行因为添加其他 MessageBox 数据库可能会产生开销 MessageBox 数据库之间路由消息的主 MessageBox 数据库。 如果仅配置两个 MessageBox 数据库然后大部分其他 MessageBox 数据库中获得的好处是通过使用的邮件路由的主 MessageBox 数据库的开销偏移量。  
  
> [!IMPORTANT]  
>  BizTalk Server 将所有状态存储在 MessageBox 数据库中，其中每个 MessageBox 数据库包含不同业务流程的状态信息。 为实现可靠性，必须群集所有 MessageBox 数据库，包括主 MessageBox 数据库和辅助 MessageBox 数据库。  
  
### <a name="providing-high-availability-for-multiple-messagebox-databases"></a>取保多个 MessageBox 数据库高度可用  
 同时将 MessageBox 数据库添加到你的 BizTalk Server 部署还可以提高可伸缩性，它不因为每个 MessageBox 数据库是唯一且独立的并且可能是单点故障的 BizTalk Server 提供高可用性环境。 若要添加冗余，则需要为每个 MessageBox 数据库配置一个服务器群集。 BizTalk Server 跨多个 MessageBox 数据库分发数据，因此，这些数据库不共享数据，也不在未进行服务器群集的情况下提供冗余。  
  
## <a name="providing-high-availability-for-the-biztalk-tracking-database"></a>确保 BizTalk 跟踪数据库高度可用  
 根据特定部署的不同要求，您可能希望通过将 BizTalk 跟踪数据库隔离到单独的 SQL Server 计算机上并创建专用于主机跟踪的单独 BizTalk 主机来增强跟踪性能。 下图显示了两个主机实例和群集的数据库的专用的跟踪主机。  
  
 ![向外扩展跟踪 database](../technical-guides/media/4fc1d448-2a6c-4cea-ac17-96c1263dfb68.gif "4fc1d448-2a6c-4cea-ac17-96c1263dfb68")  
  
 如果部署需要高吞吐量并且需要为这些消息跟踪大量数据，则跟踪系统开销可能会消耗运行 SQL Server 的计算机上的大量资源。 如果出现这种情况并继续执行传入消息的速率很高，BizTalk Server 到达其中它无法处理新消息，因为所需的资源来跟踪的点的消息是大于运行其他 BizTalk Server 所需的资源组件 （如接收消息并将它们保存到 MessageBox 数据库）。  
  
 为了提高性能和安全性，建议您将一台不包含其他任何项目（例如接收位置、业务流程或管道）的主机专用于跟踪，并且禁止从接收主机、处理主机和发送主机进行跟踪。 若要确保跟踪主机高度可用，请创建跟踪主机的多个主机实例。 请参阅[创建新的主机](../core/how-to-create-a-new-host.md)。
  
 对于每个 MessageBox 数据库中，BizTalk Server 使用只有一个跟踪要将消息从 MessageBox 数据库移到 BizTalk 跟踪数据库 (BizTalkDTADb) 的主机实例。 如果其他计算机运行该跟踪主机的实例，则 BizTalk Server 会自动将每个 MessageBox 数据库的处理扩展到该跟踪主机的单独实例。 如果 MessageBox 数据库数大于跟踪主机实例数，则一个或多个跟踪主机实例将为多个 MessageBox 数据库提供服务。  
  
 若要确保 BizTalk 跟踪数据库具有高可用性，请使用 Windows 群集来配置两台使用主动/被动配置运行 SQL Server 的数据库计算机。  
  
## <a name="providing-high-availability-for-the-bam-databases"></a>确保 BAM 数据库高度可用  
 *业务活动监视*(BAM) 提供到独立的 IT 实现或跨异类 IT 实现的业务流程的可见性。 BAM SQL Server 数据库（BAM 星型架构数据库、BAM 主导入数据库和 BAM 存档数据库）和 BAM 分析数据库存储了不同于操作监视数据的业务活动数据。 下图显示 BAM 数据库基础结构。  
  
 ![BAM 数据库基础结构](../technical-guides/media/769c3b7c-fe16-4260-967e-6af003c4f08d.gif "769c3b7c-fe16-4260-967e-6af003c4f08d")  
  
 为确保 BAM 基础结构高度可用，执行以下操作：  
  
-   **群集 BAM 主导入数据库和 BAM 分析数据库。** BAM 主导入数据库是业务活动监视系统的中心。 因此，通过使用 Windows 群集来确保此数据库高度可用并遵循以下两条建议以防止此数据库被填满是十分重要的。 BAM 分析数据库是存储业务分析员用于生成活动聚合和 OLAP 多维数据集的数据的 Analysis Services 数据库。因此，此数据库的任何故障都会影响业务分析员的工作效率。 虽然不需要群集 BAM 存档数据库，但我们建议你监视事件日志中的错误，当 SQL Server Integration Services (SSIS) 包运行以确保已成功，传输数据和监视数据库的大小以便你可将其替换在它之前填充向上。  
  
-   **定义联机窗口。** 要允许更好的性能并避免停机时间，BAM 分区 BAM 主导入数据库中的数据到表时此活动已完成基于时间戳。 BAM 通过定期将另一个相同格式的空表与已完成的表进行交换来实现此操作。 BAM 完成此操作后，尽管 BAM 会在联机时段中定义的时间内保留旧分区，但其他已完成的活动将进入新分区（表）。 必须定义联机时段以确保 BAM 主导入数据库中的分区数不会变得过大。 有关计划联机 windows 的详细信息，请参阅[存档主导入数据库数据](../core/archiving-primary-import-database-data.md)。
  
-   **计划定期运行的 SSIS 包。** 定义联机时段可确保 BAM 主导入数据库不会被旧活动分区填满。 您还必须安排 SSIS 包来定期运行以创建新分区的活动数据并将数据从 BAM 主导入数据库中旧的分区移动到 BAM 存档数据库。 有关计划 SSIS 包的详细信息，请参阅[计划 SQL Server Integration Services 包](../core/scheduling-sql-server-integration-services-packages.md)。
  
-   **小心地选择小型集的数据项 （检查点），并避免定义活动时包括不必要的数据的项目。**  
  
-   **了解计划和实时聚合设计你的聚合时权衡。** 实时聚合由 SQL Server 触发器自动进行维护并且没有延迟。 它们非常适合用于某些任务关键型低延迟方案中，但它们会产生一定的性能开销每当事件正在写入到 BAM 主导入数据库。 计划的聚合依赖于计划立方 SSIS 程序包来更新其聚合数据。 其延迟是等于或大于 SSIS 计划间隔，但是总体它们具有较小的性能影响 BAM 主导入数据库。  
  
-   **如果你选择计划的聚合，请确保您计划 cubing SSIS 比存档 SSIS 更频繁地运行。** 这是因为存档 SSIS 将不会移动并且已针对计划聚合到 BAM 存档数据库处理的活动数据。  
  
-   **启用 BAM 事件总线服务中获取故障转移功能的多台计算机。**  
  
## <a name="providing-high-availability-for-the-other-biztalk-server-databases"></a>确保其他 BizTalk Server 数据库高度可用  
 若要为其他 BizTalk Server 数据库提供高可用性，配置 Windows 群集中运行 SQL Server 的两台计算机。 这些计算机可以运行冗余的主动/主动或主动/被动配置中，可以在共享的驱动器上存储数据 (如 RAID 1 + 0 SCSI 磁盘阵列) 或存储区域网络 (SAN)。  
  
## <a name="see-also"></a>另请参阅  
 [群集 BizTalk Server Databases2](../technical-guides/clustering-the-biztalk-server-databases2.md)