---
title: 执行可用性测试 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10b543dd-ba85-40da-8c6f-485eddb59158
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a4ec699f3daf65b245dce2f2f70cd3d4daecb00
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014710"
---
# <a name="performing-availability-testing"></a>执行可用性测试
您应测试系统，以验证它能够从各种级别的故障，范围为从小规模故障 （例如网络卡故障） 到生产服务器的丢失恢复的灾难恢复。 灾难恢复测试应包括以下步骤：  
  
- **测试单个硬件组件故障。**  
  
   应测试系统能够从单个硬件组件故障，例如网络或磁盘中恢复。  
  
- **测试单一 BizTalk server 失败。**  
  
   在大多数[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生产环境中，主机进程并分散在多台计算机运行之间[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]单一的 BizTalk 组中。 什么是 BizTalk 组能够继续在事件处理的主机组中的服务器之一失败？  
  
- **测试群集节点故障转移。**  
  
   如果 Windows 聚类分析用于提供高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库或 BizTalk 主机，应验证群集节点故障转移功能。 有关使用 Windows 群集提供高可用性的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[核对清单： 提供高可用性容错或负载平衡](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)。  
  
- **测试恢复使用日志传送的 BizTalk Server 数据库。**  
  
   您应该验证的恢复[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 有关使用日志传送备份和还原的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，请参阅[什么是 BizTalk Server 日志传送？](../technical-guides/what-is-biztalk-server-log-shipping.md)本指南中或[日志传送](http://go.microsoft.com/fwlink/?LinkID=153450)(<http://go.microsoft.com/fwlink/?LinkID=153450>)。  
  
   应遵循以提高可用性的步骤的清单[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中使用灾难恢复，请参阅[核对清单： 灾难恢复与提高可用性](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)。  
  
## <a name="see-also"></a>请参阅  
 [提供高可用性 BizTalk Server](../technical-guides/increasing-availability-for-biztalk-server.md)