---
title: 业务流程冻结和解除冻结 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57d7c0bf-a707-4ebd-afab-e75dd80c3c34
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e9ad8bfb4747ad632da3c992f38a6fce866035d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323438"
---
# <a name="orchestration-dehydration-and-rehydration"></a>业务流程冻结和解除冻结
在同时运行多长时间运行的业务流程，内存和性能时，可能出现的问题。 业务流程引擎通过"冻结"和"解除冻结"业务流程实例来解决这些问题。  
  
 冻结是序列化到 SQL Server 数据库的业务流程的状态的过程。 解除冻结是此过程的相反： 反序列化数据库从业务流程的最后运行状态。 冻结用于通过减少必须被实例化在内存中一次的业务流程的系统资源的使用降至最低。  
  
## <a name="dehydration"></a>冻结  
 业务流程引擎可以确定，业务流程实例已处于空闲状态一段较长时间。 它计算阈值以确定它适用于各种操作，需要将等待多长，如果超过这些阈值，它将冻结该实例。 这可以在下列情况下发生：  
  
- 当业务流程正在等待接收一条消息，并且等待的时间超过引擎所确定的阈值。  
  
- 当业务流程"侦听"的消息时使用的表现**侦听**形状，并没有分支将触发之前由引擎所确定的阈值。 唯一的例外是何时**侦听**形状包含激活接收。  
  
- 当业务流程中的延迟的长度超过引擎所确定的阈值。  
  
  引擎保存状态来冻结实例，并释放该实例所占用的内存。 通过冻结休眠的业务流程实例，该引擎使得大量长时间运行的业务流程，以同时在同一台计算机上运行。  
  
  可以设置 12 属性以配置冻结在 BizTalk Server 中的工作方式。 在本部分中的主题列出并描述了这些属性和其默认值，并讨论各种值如何影响冻结行为。  
  
## <a name="rehydration"></a>解除冻结  
 可以触发业务流程引擎以便解除冻结业务流程实例收到消息或延迟形状中指定的超时过期。 然后将已保存业务流程实例加载到内存，还原其状态，并运行从离开的位置的点。 有关在业务流程中使用形状的详细信息，请参阅[业务流程形状](../core/orchestration-shapes.md)。  
  
 业务流程可以配置为在多台服务器上运行。 业务流程实例已被冻结后，它可以在任何这些服务器上解除冻结。 如果一台服务器出现故障，引擎将继续在不同服务器上，从其以前的状态继续运行业务流程。 该引擎还会利用此功能以实现跨服务器的负载平衡。  
  
## <a name="next-steps"></a>后续步骤
  
-   [冻结默认属性](../core/dehydration-default-properties.md)  
  
-   [如何计算冻结](../core/how-to-calculate-dehydration.md)  
  
-   [示例冻结计算](../core/sample-dehydration-calculation.md)  
  
-   [业务流程冻结性能计数器](../core/orchestration-dehydration-performance-counters.md)  
  
-   [BTSNTSvc.exe.config 文件](../core/btsntsvc-exe-config-file.md)  
  
-   [可影响冻结行为的其他活动](../core/other-activities-that-can-affect-dehydration-behavior.md)