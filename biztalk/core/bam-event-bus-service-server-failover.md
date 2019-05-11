---
title: BAM 事件总线服务服务器故障转移 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f12378c8-09bb-45c1-ade1-d9b20131461f
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca99e507e5f0344f7991a6e6b3c7798fb309dad4
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530593"
---
# <a name="bam-event-bus-service-server-failover"></a>BAM 事件总线服务服务器故障转移
BAM 事件总线服务包括故障容错逻辑，使它能够恢复并重新启动从意外故障而不会丢失任何数据。  
  
 如果启用多台计算机上的 BAM 事件总线服务或服务失败，故障转移逻辑将检测到 BAM 事件总线服务已终止，并将逻辑会自动在另一台计算机上启动 BAM 事件总线服务的新实例。  
  
 下图显示 BAM 事件总线处理计算机的方式或通过执行简单的网络故障的负载均衡。 BAM 事件总线服务启动之前已配置两个源和一个目标。  
  
 ![](../core/media/ebiz-bam-admin-evntbuspoolfail.gif "ebiz_bam_admin_evntbuspoolfail")  
如何实现 BAM 事件总线服务负载平衡  
  
 BAM 事件总线服务负载平衡通过执行以下：  
  
-   **答：Server1 处理 2 个源 （会话） 的事件数据**。 在 Server2 上创建 BAM 事件总线服务的实例之前，在 Server1 上创建 BAM 事件总线业务流程实例。 服务器发现有任何其他服务器可用，并因此接管 Src1 和 Src2 两个会话。  
  
-   **B:Server2 进入联机状态，并加入 BAM 事件总线池**。 在 Server2 上创建 BAM 事件总线服务的实例后，Server1 会中断一个 BAM 事件总线服务会话，Server2 会接管该。  
  
-   **C:Server1 失败**。 Server2 加入 BAM 事件总线池后，Server1 失败。  
  
-   **D:Server2 处理 2 个源 （会话） 的事件数据**。 Server2 接管 Src1 和 Src2 提取这两个会话。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 事件总线服务](../core/managing-the-bam-event-bus-service.md)   
 [BAM 安全建议](../core/bam-security-recommendations.md)   
 [业务活动监视 (BAM)](../core/business-activity-monitoring-bam.md)