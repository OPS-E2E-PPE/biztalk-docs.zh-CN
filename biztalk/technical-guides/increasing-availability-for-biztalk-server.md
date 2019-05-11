---
title: BizTalk Server 提供高可用性 |Microsoft Docs
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
ms.openlocfilehash: 9d8d3b74fe8c0389093b9525be7ad7adbad5638f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395845"
---
# <a name="increasing-availability-for-biztalk-server"></a>BizTalk Server 提供高可用性
本部分介绍可提升的可用性的方法在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。  
  
## <a name="strategies-for-increasing-availability"></a>用于提高可用性的策略  
 用于提高可用性的策略包括：  
  
- **提供使用 Windows Server 2003 服务器群集或 Windows Server 2008 故障转移群集实现高可用性**。 服务器/故障转移群集是一组独立的计算机系统，名为节点，作为单个系统以确保关键应用程序和资源始终可由客户端一起工作。 如果某个节点由于故障或维护停机时间要求而不可用，另一个节点就会立即开始提供服务 （该过程称为故障转移）。  
  
  - 对于运行用于容装的 SQL Server 的计算机通常建议服务器/故障转移群集，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。  
  
  - 服务器群集可能需要某些 BizTalk 适配器提供高可用性。  
  
  - 服务器群集通常建议使用企业单一登录主密钥服务器。  
  
- **提供使用窗体的负载均衡的高可用性**。  
  
  - 网络负载平衡 (NLB)。 NLB 将传入网络流量重定向到使用 NLB 群集主机，如果主机发生故障或处于脱机状态，以提供高可用性。 与不同的服务器群集，NLB 不需要特殊硬件。  
  
  - BizTalk 主机负载平衡。 BizTalk 主机提供负载平衡的 BizTalk 主机添加多个服务器运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组，然后配置这些服务器上运行的进程内主机的多个实例。 这将分配服务和项目在该主机中配置增强了其可用性和可伸缩性的主机的多个实例的执行。  
  
    > [!NOTE]  
    >  对于进程内主机提供主机负载平衡功能。  
  
  - 通过使用 SAN 或通过添加多个 MessageBox 数据库的 SQL Server 磁盘提供负载平衡。  
  
- 提供的策略**提高了可用性**。 这些策略提供更高的可用性，但通常也需要管理员执行在运行时的一个或多个操作。 因此这些策略是通常认为提供更高的可用性，而不是高可用性：  
  
  - 增加可用性使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送和灾难恢复。  
  
  - 提高可用性通过实现相应的监视和维护的策略。  
  
## <a name="difference-between-clustering-and-disaster-recovery"></a>聚类分析之间的差异和灾难恢复  
 虽然群集和灾难恢复这两种提高可用性，它们之间的主要差异是群集通常提供比灾难恢复速度快得多的恢复时间。 因此服务器/故障转移群集上生成解决方案或负载平衡广泛被认为提供高可用性而不是只提供可用性。  
  
 灾难恢复，可恢复操作失败的系统，但通常是一个手动过程并且需要比高可用性实现的更多恢复时间。 因此，灾难恢复实现提供可用性，但不是需要高可用性。 通过服务器/故障转移群集和负载均衡的高可用性和灾难恢复，在生产环境中的可用性，应使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [提供高可用性](../technical-guides/providing-high-availability.md)  
  
-   [灾难恢复](../technical-guides/disaster-recovery.md)  
  
## <a name="see-also"></a>请参阅  
 [清单：提供高可用性容错或负载平衡](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)   
 [清单：提供高可用性灾难恢复](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)