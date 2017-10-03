---
title: "向外扩展处理主机 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- high availability
- hosts, processing
- hosts, high availability
- scaling, hosts
- hosts, planning
- hosts, scaling
- clustering
ms.assetid: c72ce8fc-7593-4700-8398-23d1a20515c3
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01ee36777a5c64713fd31e86fe6ef2a1886b3348
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scaled-out-processing-hosts"></a>扩展的处理主机
向外扩展的处理主机会改进性能，并通过隔离两个或多个单独的主机计算机上安装的业务流程功能提供高可用性。 这种隔离，可以将多台计算机添加给处理主机以实现冗余。 在 Microsoft 中的处理主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行一个或多个主机实例各种业务流程，并创建业务流程的编程对象的实例的相应的坐标。  
  
 下图显示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过在两台计算机正在运行的处理主机实例处理主机提供高可用性的部署。 请注意，在此图中接收和发送主机不具备高可用性。  
  
 ![向外扩展处理主机](../core/media/tdi-ha-scaleprocess.gif "TDI_HA_ScaleProcess")  
  
 在此配置中，处理业务流程的工作进行负载平衡之间两个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理主机的实例并运行单独的计算机。 如果一台计算机时遇到错误或失败，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会自动使用在另一台计算机上的主机实例以处理剩余的业务流程。  
  
## <a name="maintaining-orchestration-state"></a>保持业务流程状态  
 BizTalk Server 维护集中在 Microsoft 中的业务流程状态[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，和不是本地每个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。 通过保存在 MessageBox 数据库中，状态[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]克服了依赖于单个处理主机实例，以处理该业务流程的限制，并且允许处理业务流程的任何处理主机实例。 如果发生错误时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的业务流程，同一处理主机的另一个实例的进程可以完成最后保存的状态从业务流程。  
  
## <a name="see-also"></a>另请参阅  
 [为 BizTalk 主机提供高可用性](../core/providing-high-availability-for-biztalk-hosts.md)