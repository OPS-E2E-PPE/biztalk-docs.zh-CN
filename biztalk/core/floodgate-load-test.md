---
title: 突发高负载测试 |Microsoft Docs
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
ms.openlocfilehash: b78509cc1bc2c38ab1fcf536ce71e3d14b70d500
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387961"
---
# <a name="floodgate-load-test"></a>突发高负载测试
本主题中的信息中所述的测试是指[测量的引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md)。  
  
## <a name="what-causes-floodgate-events"></a>哪些会发生水闸事件？  
 有多种方案只是其中几个较大的峰值 (也称为**水闸事件**) 的消息同时到达系统每一天。 这些峰值之间，吞吐量可能会很低。 这些类型的方案的示例包括：  
  
- 证券交易，例如，在和关闭  
  
- 在结束一天交易对帐过程银行系统，例如，  
  
  其他类型的事件会导致与水闸事件相似的积压行为。 例如，如果合作伙伴的发送地址脱机，以便目标的消息的地址必须进行重试和/或挂起，这可能导致增加积压。 当合作伙伴返回行上，可能有大量挂起的消息需要恢复，从而导致另一种类型的水闸事件。 以下测试系统的阐释了这一点。  
  
## <a name="simulating-a-floodgate-event"></a>模拟水闸事件  
 对于此测试，系统将在大约半个的最大可承受吞吐量这当然非常稳定最初驱动。 然后，若要模拟水闸事件，负载生成工具将配置为在短时间内每秒大约 410 中发送的时间 （加速测试相同）。 测量每个第二个和后台处理深度接收的消息的生成的负载配置文件如下所示。  
  
 **突发高负载测试的负载状况**  
  
 ![突发高负载的性能监视器显示](../core/media/bts06-floodgate-load.gif "BTS06_Floodgate_Load")  
  
 注意该图，后台处理表快速构建了的积压工作水闸事件期间。 但是，因为该事件生存期相对较短，并且事件发生后的后续接收速率未达到最大可承受速率，清理作业也能够运行，并从该事件中恢复而无需系统接收中断。 对于此特定测试，MessageBox 存储在 SQL Server 2005;从开始到结束此测试的持续时间为大约耗时 45 分钟。  
  
 当然，每个系统都不同，因此"您的选择而异。" 验证可以恢复的最佳方法是转到生产环境之前使用具代表性的负载测试。  
  
## <a name="see-also"></a>请参阅  
 [测量引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md)   
 [使用设置仪表板进行 BizTalk Server 性能优化](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)   
 [过载测试](../core/overdrive-load-test.md)   
 [可承受负载测试](../core/sustainable-load-test.md)