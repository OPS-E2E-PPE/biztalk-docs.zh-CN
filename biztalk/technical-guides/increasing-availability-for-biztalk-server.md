---
title: 提高了可用性，BizTalk 服务器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72d9ce5e-d775-4f8e-b1a4-bf3c7c05f571
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa48d7dada00ebadf089834f5025f3fdfdf25070
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297997"
---
# <a name="increasing-availability-for-biztalk-server"></a>BizTalk Server 用于提高可用性
本部分介绍你可以增加的可用性的方式你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。  
  
## <a name="strategies-for-increasing-availability"></a>提高可用性的策略  
 提高可用性策略包括：  
  
-   **提供使用 Windows Server 2003 服务器群集或 Windows Server 2008 故障转移群集的高可用性**。 服务器/故障转移群集是一组独立的计算机系统，称为节点，作为单个系统以确保关键应用程序和资源保持供客户端一起工作。 如果其中一个节点变为因为故障或进行维护停机时间要求而不可用，另一个节点就会立即开始提供服务 （该过程称为故障转移）。  
  
    -   服务器/故障转移群集通常适用于运行该内部的 SQL Server 的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。  
  
    -   服务器群集可能需要提供高可用性，对于某些 BizTalk 适配器。  
  
    -   服务器群集通常适用于企业单一登录的主密钥服务器。  
  
-   **提供使用某种形式的负载平衡的高可用性**。  
  
    -   网络负载平衡 (NLB)。 NLB 提供高可用性，通过将传入的网络流量重定向到正在工作 NLB 群集主机，如果某个主机故障或处于脱机状态。 与不同的是服务器群集，NLB 不需要特殊硬件。  
  
    -   BizTalk 主机负载平衡。 通过添加多个服务器运行 BizTalk 主机负载平衡提供 BizTalk 主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组中，然后配置这些服务器上运行的进程内主机的多个实例。 这可以跨主机的多个实例分发在该主机中配置的服务和项目的执行，这可增强其可用性与可伸缩性。  
  
        > [!NOTE]  
        >  可用于进程内主机仅主机负载平衡功能。  
  
    -   通过使用 SAN 或通过添加 MessageBox 的多个数据库的 SQL Server 磁盘提供负载平衡。  
  
-   提供策略**提高了可用性**。 这些策略提供更高的可用性，但通常还需要管理员执行在运行时的一个或多个操作。 因此这些策略是通常认为提供更高的可用性，而不是高可用性：  
  
    -   增加可用性使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送和灾难恢复。  
  
    -   提高可用性通过实现相应的监视和维护策略。  
  
## <a name="difference-between-clustering-and-disaster-recovery"></a>群集之间的差异和灾难恢复  
 尽管群集和灾难恢复提高可用性，它们的主要区别是群集通常提供比灾难恢复速度快得多的恢复时间。 因此在服务器/故障转移群集上生成的解决方案或负载平衡通常想象成提供高可用性而不是仅提供可用性。  
  
 灾难恢复，可恢复的失败的系统运行但通常是一个手动过程，并且需要比的高可用性实现的更多恢复时间。 因此，灾难恢复实现提供可用性，但不是需要高可用性。 您应使用通过服务器/故障转移群集和负载平衡，高可用性和灾难恢复，在生产中通过可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [提供高可用性](../technical-guides/providing-high-availability.md)  
  
-   [灾难恢复](../technical-guides/disaster-recovery.md)  
  
## <a name="see-also"></a>另请参阅  
 [清单： 会提供高可用性容错或负载平衡](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)   
 [清单： 提高可用性与灾难恢复](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)