---
title: Floodgate 负载测试 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- LoadGen tool, simulating floodgate events
- performance, floodgate peaks
- floodgate events [performance]
ms.assetid: 937f2478-339b-4ae2-b107-56f3a4bfc579
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74954d8b94207832ceee5bbb699a7de1a245f61b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246205"
---
# <a name="floodgate-load-test"></a>突发高负载测试
本主题中的信息是指中所述的测试[测试方案的引擎测量 MST](../core/test-scenarios-for-measuring-mst-of-the-engine.md)。  
  
## <a name="what-causes-floodgate-events"></a>什么情况下将会发生水闸事件？  
 有许多方案，只需几个较大的峰值 (也称为**floodgate 事件**) 的消息到达系统每一天。 而在这些峰值之间，吞吐量非常低。 这种类型的情况的示例包括：  
  
-   例如，在开市和闭市时的股票交易。  
  
-   例如，在一天结束时，交易对帐期间的银行系统。  
  
 其他类型的事件也可导致与水闸事件相似的积压行为。 例如，如果合作伙伴的发送地址脱机，以该地址为目标的消息将可能重试并/或挂起，而这将导致增加积压量。 如果合作伙伴重新联机，则可能有大量挂起的消息需要恢复，而这又将导致另一种类型的水闸事件。 下面的系统测试将阐释此行为。  
  
## <a name="simulating-a-floodgate-event"></a>模拟水闸事件  
 对于此测试，最初，系统将以最大可承受吞吐量的一半（这当然非常稳定）进行驱动。 然后，为模拟水闸事件，负载生成工具将配置为在短时间（与加速测试相同）内以大约每秒 410 条消息的速度进行发送。 下图显示了度量每秒所收到消息所生成的负载状况以及后台处理深度。  
  
 **加载 floodgate 负载测试的配置文件**  
  
 ![Floodgate 负荷的性能监视器显示](../core/media/bts06-floodgate-load.gif "BTS06_Floodgate_Load")  
  
 请注意，从图中可看出，在水闸事件期间后台处理表中的积压快速增加。 但是，由于事件的生命期相对较短，而且事件之后的接收速率低于最大可承受速率，因此可以运行清除作业，从事件中恢复到正常状况，而无需停用系统接收。 对于此具体的测试，MessageBox 存储在 SQL Server 2005 中；此测试的持续时间从开始到结束大约耗时 45 分钟。  
  
 当然，由于所用系统不尽相同，因此持续时间也各不相同。 验证可以恢复的最佳方式是：在进入生产阶段之前，应使用最具代表性的负载进行测试。  
  
## <a name="see-also"></a>另请参阅  
 [用于测量引擎 MST 测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md)   
 [设置仪表板用于 BizTalk Server 性能优化](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)   
 [Overdrive 负载测试](../core/overdrive-load-test.md)   
 [可持续的负载测试](../core/sustainable-load-test.md)