---
title: 向外扩展 BizTalk Server 层 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, scaling
- scaling, planning
- scaling, load balancing
- host instances, scaling
- scaling, examples
- fault tolerance
- scaling, scaling out
- scaling, fault tolerance
- NLB system, scaling
- scaling, host instances
ms.assetid: 01d1ab20-d7a9-4d0b-a61e-65e56fe5010e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e04050f1d7346f06d8b0d0a7163ac28f8d538f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308970"
---
# <a name="scaling-out-the-biztalk-server-tier"></a>向外扩展 BizTalk Server 层
若要横向扩展 BizTalk 层，请向现有拓扑添加更多的硬件。 建议在以下方案中添加硬件：  
  
- BizTalk Server 成为瓶颈。 该瓶颈本身可能会造成以下问题之一导致:  
  
- CPU:如果本方案使用 CPU 密集型管道、 映射或业务流程，BizTalk server 将没有任何额外的 CPU 余量。  
  
- 内存和 I/O:如果现有计算机已达到其对内存和 IO 的最大限制，将资源添加的唯一方法是添加另一台物理计算机。  
  
- 向上扩展成本十分高昂。 例如，考虑其中 BizTalk CPU 已达到最大容量的 1 BizTalk Server 拓扑。 如果它是更便宜，若要添加额外的双处理器计算机，而不是双处理器升级到四核处理器，则应改为横向低于系统。  
  
- 向上扩展不能解决瓶颈。 向上扩展可能无法在以下方案中：  
  
  -   因此，您需要另一台计算机，以扩展 IO，IO 将是 BizTalk 计算机的最大级别。  
  
  -   内存是在您的操作系统的最大级别。 在此方案中，扩展您的系统的唯一方法是将额外的 BizTalk 计算机添加到拓扑。  
  
  在某些情况下，您可能希望用于接收消息、 发送消息，以及处理它们的专用的服务器。 如果具有专用的服务器，更加容易地解决问题并执行在一台计算机上的执行维护操作而不会影响其他。 您可以通过缩放添加这些计算机我们 BizTalk 层。  
  
## <a name="when-you-cant-scale-out-the-biztalk-tier"></a>时，无法横向扩展 BizTalk 层  
  
- MessageBox 数据库是瓶颈。  
  
- 适配器成为瓶颈。 例如，如果使用 SQL 适配器后增加 BizTalk 接收器的数量，锁争用现象会增加，BizTalk SQL 适配器从其请求数据的 SQL 数据库上。 这将限制你能够向外扩展 SQL 适配器。  
  
  下图显示了如何扩展 BizTalk 层的示例。  
  
  ![Scaleout BTS](../core/media/scaleoutbts.gif "ScaleOutBTS")  
  
  此图显示了向外扩展 BizTalk 拓扑，从一台 BizTalk 服务器扩展到 2 个 BizTalk server。 在一个 BizTalk server 拓扑中，三个主机实例共享 BizTalk 计算机资源。 在两个 BizTalk server 拓扑中，传输主机位于其他服务器，从而提高了吞吐量上。  
  
## <a name="considerations-when-scaling-out-the-biztalk-tier"></a>在缩放时的注意事项扩展 BizTalk 层  
 添加另一台 BizTalk Server 计算机之前，必须考虑以下问题：  
  
#### <a name="how-do-i-configure-the-system-for-load-balancing-and-fault-tolerance-when-i-scale-out-the-biztalk-tier"></a>当我向外扩展 BizTalk 层时，如何配置负载平衡和容错能力的系统？  
 负载平衡和容错技术的选择取决于在方案中使用的适配器。 对于 SOAP 和 HTTP 适配器的建议的方法是使用 NLB。 请参阅 NLB 文档的更多详细信息。  
  
#### <a name="how-do-i-refactor-the-host-instances"></a>如何重构主机实例？  
 没有一个规则以确定如何应重构主机实例时，横向扩展 BizTalk 层。 何时重构主机实例取决于方案的复杂性。 以下是一些示例如何重构主机实例。  
  
##### <a name="scenario-1"></a>方案 1  
 一个 BizTalk server 配置，并接收和传输的主机实例是同一台计算机。  
  
 假定存在 CPU 瓶颈。 将另一台相同的 BizTalk 计算机添加到该组中以横向扩展，为您提供两种方法来重构主机实例。  
  
 下面是此问题的两个解决方案：  
  
- **解决方案 1**:在此方案中分解的最简单的方法是克隆将主机实例结构从第一台计算机到第二台计算机。 因此，第二台计算机是第一个完全相同的副本在这样的功能。它还可以同时具有接收和发送主机。 假定不没有其他任何瓶颈，如 CPU 资源会增加一倍可能会收到扩展因子为 2。  
  
- **解决方案 2**:另一种方法来重构主机实例是隔离的接收和发送到不同的计算机上的函数。 因此，BizTalk 服务器之一是专用于接收和发送其他。  
  
  **比较解决方案 1 和 2 的解决方案**  
  
  在解决方案 1 中，主机实例数的增加一倍从 bts 构成的配置。 这意味着 SQL 服务器上的锁争用现象将增加。 锁争用现象的增加量将确定扩展因子。 如果锁争用成为瓶颈的限制范围内良好，可以看到扩展因子为 2。  
  
  解决方案 2 的优点是有只有两个主机实例，以便在 SQL server 上的锁争用现象应少于解决方案 1。 但是，扩展因子完全取决于接收的复杂性和发送主机实例。 请考虑以下情况中的解决方案 2:  
  
  假定这两个接收和传输主机实例在同样密集型的它们都在一个 BizTalk server 拓扑使用 50%的 CPU。 在两个 BizTalk server 拓扑中，将传输主机实例移到其他计算机上，并且现在都接收和传输获得双倍的资源。 这会提供扩展因子为 2，假定不没有其他任何瓶颈。 因为只有两个主机实例，从而减少了锁争用，这种情况下是优于解决方案 1。  
  
  假定的传输方式多于接收所占用和一个 BizTalk server 拓扑中使用 80%的 CPU 资源。 通过将传输主机实例移动到另一台计算机，您将了解只有 20%的 CPU 资源，因此最大扩展因子将为 1.2。 此外，具有接收主机实例的计算机将仅 20-30%的 CPU 资源，因此向外扩展的优点是要少得多。  
  
  请考虑下图中包含四个 BizTalk server。 每台计算机都收件人和发件人，为您提供的每种类型的四个主机实例的总计 （接收和传输）。  
  
  ![Re&#45;重构主机实例](../core/media/refactoringhostinstances.gif "RefactoringHostinstances")  
  
  此拓扑可能不是最可能一个可能的。 您还应测试其他重构排列，具体取决于方案的复杂性。 例如：  
  
- 将专用于接收的两台计算机和两个用于传输。 这将使您最可能的缩放，这两个接收和发送是同样密集型时。  
  
- 将专用三个三台接收，另一个用于传输，如果接收是比传输更密集。  
  
- 将专用一台计算机用于接收和传输如果传输为多于接收更密集的三个。  
  
  在所有情况下，建议尽量减少每个主机的主机实例的数量，以便减少 MessageBox 数据库上的争用，并在相同时使用的计算机资源是最充分地使用。 最佳的重构排列取决于方案和瓶颈类型的复杂程度。 始终对重构进行测试之前最终确定排列。  
  
## <a name="see-also"></a>请参阅  
 [纵向扩展 BizTalk Server 层](../core/scaling-up-the-biztalk-server-tier.md)   
 [纵向扩展 SQL Server 层](../core/scaling-up-the-sql-server-tier.md)   
 [SQL Server 层向外缩放](../core/scaling-out-the-sql-server-tier.md)   
 [向外扩展接收主机](../core/scaled-out-receiving-hosts.md)   
 [向外扩展处理主机](../core/scaled-out-processing-hosts.md)   
 [向外扩展发送主机](../core/scaled-out-sending-hosts.md)   
 [使用 Windows Server 群集为 BizTalk Server 主机 2 提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [向外扩展数据库](../core/scaled-out-databases.md)   
 [聚类分析 BizTalk Server 数据库](../core/clustering-the-biztalk-server-databases1.md)