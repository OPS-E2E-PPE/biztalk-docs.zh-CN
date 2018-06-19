---
title: 执行可用性测试 |Microsoft 文档
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
ms.openlocfilehash: e6f0d9b1cb7b38ab8a1173ee227a8202812048f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298301"
---
# <a name="performing-availability-testing"></a>执行可用性测试
你应测试系统，以验证其能够从不同级别的失败，范围从小规模故障 （如网络卡故障） 到生产服务器的丢失将恢复的灾难恢复。 灾难恢复测试应包括以下步骤：  
  
-   **测试单个硬件组件失败。**  
  
     你应测试系统能够从单个硬件组件故障，例如网络或磁盘中恢复。  
  
-   **测试单个 BizTalk server 失败。**  
  
     在大多数[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生产环境中，主机处理并分散在多个计算机中运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]单个的 BizTalk 组中。 什么是 BizTalk 组能够继续在事件处理的主机组中的服务器之一失败？  
  
-   **测试群集节点故障转移。**  
  
     如果 Windows 群集用于提供的高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库或 BizTalk 主机，应验证群集节点故障转移功能。 有关使用 Windows 群集提供的高可用性的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[清单： 具有容错能力或负载平衡提供高可用性](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)。  
  
-   **测试使用日志传送的 BizTalk Server 数据库的恢复。**  
  
     你应验证的恢复[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 有关使用日志传送备份和还原的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，请参阅[什么是 BizTalk Server 日志传送？](../technical-guides/what-is-biztalk-server-log-shipping.md)本指南中或[日志传送](http://go.microsoft.com/fwlink/?LinkID=153450)(http://go.microsoft.com/fwlink/?LinkID=153450)。  
  
     你应遵循的增加的可用性的步骤的清单[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境使用灾难恢复，请参阅[清单： 增加可用性与灾难恢复](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 用于提高可用性](../technical-guides/increasing-availability-for-biztalk-server.md)