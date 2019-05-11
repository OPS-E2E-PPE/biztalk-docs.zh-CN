---
title: 向外扩展处理主机 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93959c75a786d9f6df69913aa233205d414ee5b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309342"
---
# <a name="scaled-out-processing-hosts"></a>向外扩展处理主机
向外扩展处理主机可以提高性能，并隔离到两个或多个单独的主机计算机上的业务流程功能，从而提供高可用性。 这种隔离可让你将多台计算机添加到冗余的处理主机。 在 Microsoft 中的处理主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行一个或多个主机实例的坐标各种业务流程并创建为业务流程的编程对象的实例。  
  
 下图显示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过在两台计算机上运行的处理主机实例的处理主机提供高可用性的部署。 请注意，在此图中的接收和发送主机并不高度可用。  
  
 ![向外扩展处理主机](../core/media/tdi-ha-scaleprocess.gif "TDI_HA_ScaleProcess")  
  
 在此配置中，用于处理业务流程的工作是两个之间的负载平衡[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]具有处理主机的实例，均可独立运行的计算机。 如果一台计算机遇到错误或失败，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]自动使用在另一台计算机上的主机实例来处理剩余的业务流程。  
  
## <a name="maintaining-orchestration-state"></a>维护业务流程的状态  
 BizTalk Server 业务流程中维护状态集中 Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，并不是本地上每个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。 通过保持在 MessageBox 数据库中，状态[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从而克服了依赖于单个处理主机实例来处理该业务流程的限制，并允许处理业务流程的任何处理主机实例。 如果发生错误时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]某一业务流程，相同的处理主机的另一个实例的进程可以完成最后保存的状态从业务流程。  
  
## <a name="see-also"></a>请参阅  
 [为 BizTalk 主机提供高可用性](../core/providing-high-availability-for-biztalk-hosts.md)