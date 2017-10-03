---
title: "BAM 事件总线服务服务器故障转移 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f12378c8-09bb-45c1-ade1-d9b20131461f
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c1fafc3e97d9905a6efd0de8ff0f389c2a389bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="bam-event-bus-service-server-failover"></a>BAM 事件总线服务服务器故障转移
BAM 事件 Bus 服务包括故障容错逻辑，使它能够恢复并重新启动从意外的故障，而不会丢失任何数据。  
  
 当在多台计算机上启用 BAM 事件总线服务而服务失败时，故障转移逻辑会检测到 BAM 事件总线服务已终止，于是，该逻辑会自动在另一台计算机上启动 BAM 事件总线服务的新实例。  
  
 下图显示 BAM 事件总线如何通过执行简单的负载平衡来处理计算机或网络故障。 启动 BAM 事件总线服务之前，配置了两个源和一个目标。  
  
 ![](../core/media/ebiz-bam-admin-evntbuspoolfail.gif "ebiz_bam_admin_evntbuspoolfail")  
BAM 事件总线服务负载平衡原理  
  
 BAM 事件总线服务通过执行以下操作实现负载平衡：  
  
-   **答： Server1 处理 2 个源 （会话） 中的事件数据**。 在 Server2 上创建 BAM 事件总线服务的实例之前，在 Server1 上创建一个 BAM 事件总线业务流程实例。 服务器发现没有其他服务器可用，于是接管 Src1 和 Src2 两个会话。  
  
-   **B: Server2 进入联机状态和联接 BAM 事件总线池**。 在 Server2 上创建一个 BAM 事件总线服务实例后，Server1 会中断一个 BAM 事件总线服务会话，而 Server2 会接管该会话。  
  
-   **C: Server1 失败**。 Server2 加入 BAM 事件总线池后，Server1 失败。  
  
-   **D: Server2 处理 2 个源 （会话） 中的事件数据**。 Server2 接管 Src1 和 Src2 两个会话。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM 事件总线服务](../core/managing-the-bam-event-bus-service.md)   
 [BAM 安全建议](../core/bam-security-recommendations.md)   
 [业务活动监视 (BAM)](../core/business-activity-monitoring-bam.md)