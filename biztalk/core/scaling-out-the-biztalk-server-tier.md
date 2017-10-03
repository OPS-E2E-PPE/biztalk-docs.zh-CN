---
title: "BizTalk Server 层向外缩放 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35674e89d8f8104a35718531f2a87f95e8bc67e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scaling-out-the-biztalk-server-tier"></a>向外扩展 BizTalk Server 层
为扩展 BizTalk 层，应向现有拓扑结构添加其他硬件。 如果出现以下情况，则建议您添加硬件：  
  
-   BizTalk Server 成为瓶颈。 该瓶颈本身可能是由于以下问题之一而导致的：  
  
-   CPU： 如果本方案使用 CPU 密集型管道、 地图或业务流程，BizTalk 服务器将不具有任何额外的 CPU 预留空间。  
  
-   内存和 I/O：如果现有计算机已达到其对内存和 IO 的最大限制，则添加资源的唯一方法是添加其他物理计算机。  
  
-   向上扩展的成本十分高昂。 例如，假设一个 BizTalk Server 拓扑结构中 BizTalk CPU 已达到其最高容量。 如果添加额外的双处理器计算机的成本低于将双处理器升级到四处理器的成本，则应当改为扩展您的系统。  
  
-   向上扩展没有解决瓶颈。 在以下情况中，向上扩展可能不起作用：  
  
    -   IO 达到 BizTalk 计算机允许的最大级别，因此需要其他计算机以扩展 IO。  
  
    -   内存达到操作系统允许的最大级别。 在这种情况下，扩展系统的唯一方法是向拓扑结构添加额外的 BizTalk 计算机。  
  
 在某些情况下，您可能需要专用的服务器来分别进行消息接收、消息发送和消息处理。 如果具有专用的服务器，则可以更容易地解决问题并在不影响其他计算机的情况下维护计算机。 您可以通过扩展 BizTalk 层来添加这些计算机。  
  
## <a name="when-you-cant-scale-out-the-biztalk-tier"></a>当你不能向外缩放 BizTalk 层  
  
-   MessageBox 数据库是瓶颈。  
  
-   适配器成为瓶颈。 例如，如果使用的是 SQL 适配器，则在增加 BizTalk 接收器的数目后，BizTalk SQL 适配器从其请求数据的 SQL 数据库上的锁争用现象会增加。 这样限制了扩展 SQL 适配器的能力。  
  
 下图显示了如何扩展 BizTalk 层的示例：  
  
 ![向外缩放 BTS](../core/media/scaleoutbts.gif "ScaleOutBTS")  
  
 此图显示了一个经过扩展的 BizTalk 拓扑结构，该拓扑结构从一个 BizTalk Server 扩展到 2 个 BizTalk Server。 在由一个 BizTalk Server 构成的拓扑结构中，三个主机实例共享 BizTalk 计算机资源。 在由两个 BizTalk Server 构成的拓扑结构中，传输主机位于其他服务器上，从而提高了吞吐量。  
  
## <a name="considerations-when-scaling-out-the-biztalk-tier"></a>在缩放时的注意事项 Out BizTalk 层  
 在添加其他 BizTalk Server 计算机之前，必须考虑以下问题：  
  
#### <a name="how-do-i-configure-the-system-for-load-balancing-and-fault-tolerance-when-i-scale-out-the-biztalk-tier"></a>在扩展 BizTalk 层时，如何对系统进行配置以实现负载平衡和容错？  
 负载平衡和容错技术的选择取决于具体情况下要使用的适配器。 对于 SOAP 和 HTTP 适配器，建议使用 NLB。 有关详细信息，请参阅 NLB 文档。  
  
#### <a name="how-do-i-refactor-the-host-instances"></a>如何重构主机实例？  
 没有统一的规则可确定在扩展 BizTalk 层时应重构主机实例的方式。 何时重构主机实例，这取决于具体情况的复杂度。 下面是一些如何重构主机实例的示例。  
  
##### <a name="scenario-1"></a>方案 1  
 一个 BizTalk server 配置，并接收和发送实例位于同一台计算机的主机。  
  
 假定存在 CPU 瓶颈。 如果将另一台相同的 BizTalk 计算机添加到该组中以进行扩展，您可以通过两种方法来重构主机实例。  
  
 下面列出了此问题的两个解决方案：  
  
-   **解决方案 1**： 在此方案中分解的最简单方法是克隆主机实例将分解从第一台计算机到另一台计算机。 因此，在功能方面，第二台计算机是第一台计算机的完整副本；它也可以同时具有接收主机和发送主机。 假设不存在其他任何瓶颈，则可以获得扩展因子 2，因为 CPU 资源增加了一倍。  
  
-   **解决方案 2**： 考虑主机实例的另一种方法是来隔离接收和发送函数拖放到不同的计算机。 因此，其中一个 BizTalk Server 将专用于接收，另一个 BizTalk Server 则专用于发送。  
  
 **比较解决方案 1 和解决方案 2**  
  
 在解决方案 1 中，主机实例数是由一个 BTS 构成的配置的两倍。 这意味着 SQL 服务器上的锁争用现象将增加。 锁争用现象的增加量将确定扩展因子。 如果锁争用尚未超过成为瓶颈的限制，则扩展因子为 2。  
  
 解决方案 2 的优点是，你拥有只有两个主机实例，以便在 SQL server 上的锁争用应小于相比解决方案 1。 但是，缩放因子完全依赖于接收的复杂性和发送主机实例。 假设在解决方案 2 中存在以下情况：  
  
 假设接收主机实例和传输主机实例占用同样多的系统资源，在由一个 BizTalk Server 构成的拓扑结构中它们分别使用 50% 的 CPU。 在由两个 BizTalk Server 构成的拓扑结构中，您将传输主机实例移至其他计算机上，现在，传输和接收都将获得双倍的资源。 这样，假设不存在其他任何瓶颈，则扩展因子应为 2。 这种情况优于解决方案 1，因为只存在两个主机实例，从而减少了锁争用。  
  
 假设传输占用的系统资源多于接收所占用的资源，在由一个 BizTalk Server 构成的拓扑结构中传输使用了 80% 的 CPU 资源。 通过将传输主机实例移至其他计算机，只能获得其他 20% 的 CPU 资源，因此，最大扩展因子将为 1.2。 此外，具有接收主机实例的计算机将只使用 20-30% 的 CPU 资源，这样，扩展的优势将大为减少。  
  
 假设下图中包含四个 BizTalk Server。 每台计算机既是接收方也是发送方，总共为您提供了每种类型（接收和传输）的四个主机实例。  
  
 ![报告 （&） #45; 分解的主机实例](../core/media/refactoringhostinstances.gif "RefactoringHostinstances")  
  
 此拓扑结构可能不是最佳的结构。 根据具体情况的复杂度，还应测试其他重构排列方案。 例如：  
  
-   将两台计算机专用于接收，其他两台计算机专用于传输。 如果接收和发送占用同样多的系统资源，则这样可提供可能的最佳扩展。  
  
-   如果接收占用的系统资源多于传输所占用的资源，则将三台计算机专用于接收，另一台计算机专用于传输。  
  
-   如果传输占用的系统资源多于接收所占用的资源，则将一台计算机专用于接收，其他三台计算机专用于传输。  
  
 在所有情况下，都建议您将每个主机的主机实例数降至最低，以便减少 MessageBox 数据库上的争用现象，同时最大限度地利用计算机资源。 最佳的重构排列方案取决于具体情况的复杂度和瓶颈类型。 在最终确定排列方案前，应始终对重构进行测试。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 层向上扩展](../core/scaling-up-the-biztalk-server-tier.md)   
 [SQL Server 层向上扩展](../core/scaling-up-the-sql-server-tier.md)   
 [SQL Server 层向外缩放](../core/scaling-out-the-sql-server-tier.md)   
 [向外扩展接收主机](../core/scaled-out-receiving-hosts.md)   
 [向外扩展的处理主机](../core/scaled-out-processing-hosts.md)   
 [向外扩展的发送主机](../core/scaled-out-sending-hosts.md)   
 [Windows Server 群集用于 BizTalk Server Hosts2 为提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [向外扩展的数据库](../core/scaled-out-databases.md)   
 [群集的 BizTalk Server 数据库](../core/clustering-the-biztalk-server-databases1.md)