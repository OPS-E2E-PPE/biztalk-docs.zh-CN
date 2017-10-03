---
title: "规划高可用性和灾难恢复 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7efba36-6d9c-4ae0-a4f5-893eb5d62a05
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 742073de6f0e992e5fd0155b1939f0680fa7b3bc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-high-availability-and-disaster-recovery"></a>规划高可用性和灾难恢复
使用开发的解决方案[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通常是执行关键任务的企业级应用程序需要最高的可用性。 这些解决方案都放到生产环境后，可以用每秒千美元估算停机时间与关联的成本。 为此，你应采用的特定策略，以便最大化的高可用性和灾难恢复功能附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]依赖软件和支持所需的硬件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
## <a name="hardware-considerations"></a>硬件考虑事项  
 若要确保高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，硬件规划时考虑以下方面：  
  
-   规划在 BizTalk 组，以容纳跨组中的 BizTalk 服务器运行多个 BizTalk 主机实例中运行多个 （至少两个） BizTalk 服务器。 这将容纳主机实例中运行的进程的负载平衡和故障的容错。  
  
-   请考虑实施存储区域网络 (SAN) 到内部[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 SAN 磁盘应配置使用 RAID 1 + 0 （带区的镜像集） 如有可能的拓扑最高的性能和高可用性。 有关发现家中使用 SAN 的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，请参阅[BizTalk Server 数据库优化白皮书](http://go.microsoft.com/fwlink/?LinkID=101578)(http://go.microsoft.com/fwlink/?LinkID=101578)。  
  
-   计划安装多个 SQL server 以容纳[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 多个 SQL server 所需的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集 （推荐） 和/或外壳某些[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上单独的物理数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]（也建议使用） 的实例。  
  
-   请考虑使用虚拟环境来控制硬件成本。 Microsoft 提供了一系列如 Microsoft Virtual Server 2005 R2、 Windows Server 2008 HYPER-V 和 Microsoft HYPER-V Server 2008 的虚拟化产品。 有关使用建议[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在虚拟环境中，请参阅[BizTalk Server 2009 HYPER-V 指南](http://go.microsoft.com/fwlink/?LinkId=151834)(http://go.microsoft.com/fwlink/?LinkId=151834)。  
  
-   规划在要提供与 Internet 相关服务为你的组织的外围网络域中安装一个或多个 Windows 服务器。 配置外围网络域使用的网络负载平衡 (NLB) 解决方案中的多个 Windows 服务器。 有关详细信息，请参阅[网络负载平衡部署指南](http://go.microsoft.com/fwlink/?LinkId=153139)(http://go.microsoft.com/fwlink/?LinkId=153139)。  
  
     在外围网络中安装服务器的详细信息，请参阅[配置你域时公开传输到 Internet](../technical-guides/planning-for-sending-and-receiving.md#BKMK_InternetTrans)。  
  
    > [!NOTE]  
    >  外围网络是也称为 DMZ、 外围安全区域和外围子网。  
  
## <a name="software-considerations"></a>软件注意事项  
 若要确保高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境，请考虑以下规划软件时：  
  
-   请考虑在 Enterprise Edition 中的投资[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以适应，会带来好处的 BizTalk 主机群集或从此运行多个 MessageBox 数据库受益的情况。 通常情况下，你应群集 BizTalk 主机的唯一原因是某些 BizTalk 适配器提供高可用性。 有关为使用主机群集的 BizTalk 适配器提供高可用性的详细信息，请参阅[在群集主机内运行适配器处理程序的注意事项](http://go.microsoft.com/fwlink/?LinkID=151284)(http://go.microsoft.com/fwlink/?LinkID=151284)。  
  
-   实现 Windows Server 群集到内部计划[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库和企业单一登录的主密钥服务器。 有关更多有关使用 Windows Server 群集的信息以提供高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库和企业单一登录主密钥服务器，请参阅[数据库的高可用性](../technical-guides/high-availability-for-databases.md)和[主密钥服务器的高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)。  
  
## <a name="high-availability-vs-disaster-recovery"></a>高可用性 vs。灾难恢复  
 有两个规定的方法来提高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境： 提供使用容错能力和/或负载平衡，或提供使用灾难恢复的提高的可用性的高可用性。 虽然每个方法会增加可用性，它们的主要区别是该容错能力，并且/或者负载平衡通常提供比灾难恢复速度快得多的恢复时间。 容错能力和/或负载平衡提供**高可用性**而灾难恢复提供了**提高了可用性**。 有关实现灾难恢复的详细信息，请参阅[清单： 增加可用性与灾难恢复](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)和[灾难恢复](../technical-guides/disaster-recovery.md)。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 用于提高可用性](../technical-guides/increasing-availability-for-biztalk-server.md)   
 [清单： 会提供高可用性容错或负载平衡](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)