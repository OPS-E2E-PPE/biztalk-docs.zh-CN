---
title: 方案 4： 调整跟踪数据库的所有消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: db1126c7-0b86-4635-bfdc-3b69a82cc64b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 327953843b2d9b70f500796f43302320924a330c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-4-sizing-the-tracking-database-for-all-messages"></a>方案 4： 调整跟踪数据库的所有消息
如果 Microsoft® BizTalk Server® 2004 实施中同时出现以上三种消息方案，则需计算所有方案结果的总和以确定 BizTalk 跟踪数据库的大小。  
  
 根据如上所示的示例：  
  
|应用场景|每年所需的空间 (GB)|  
|--------------|-------------------------------------|  
|简单消息|4.78|  
|业务流程中的消息|7.18|  
|业务流程中发送给分发列表的消息|10.8|  
|**总计**|22.04|  
  
 此外，如果打开对以上三种方案的消息正文跟踪，我们将得到以下结果：  
  
|应用场景|每年所需的空间 (GB)|  
|--------------|-------------------------------------|  
|简单消息|50.1|  
|业务流程中的消息|50.1|  
|业务流程中发送给分发列表的消息|83.45|  
|**总计**|183.65|  
  
 至此，我们得出 BizTalk 跟踪数据库的年增长总计为 205.69 GB。 此表不包括任何意外情况。 如果您决定为意外情况增加 10% 的总计空间（建议您这样做），那么，您应计划 BizTalk 跟踪数据库的年增长为 227.94 GB。 另外，应考虑由于 SQL 索引、 存储等的开销。如有可能在测试中运行的测试方案后，应该根据放大因子。  
  
## <a name="other-factors-affecting-biztalk-tracking-database-size"></a>影响 BizTalk 跟踪数据库大小的其他因素  
 还有其他一些因素也会影响 BizTalk 跟踪数据库的大小，例如业务流程内所使用的形状。  
  
 如果已打开业务流程调试器选项（默认情况下为打开状态），则业务流程中每个形状的状态将保存到 BizTalk 跟踪数据库中。  
  
 用于确定跟踪形状状态所需的空间大小的公式如下所示：  
  
```  
[(# of object shapes ] * 76 bytes  
```  
  
 例如，在下图中，您将使用以下公式来确定 BizTalk 跟踪大小：  
  
```  
((4) * 76 bytes = 304 bytes  
```  
  
 ![业务流程示例](../core/media/sample-orchestration.gif "Sample_orchestration")  
  
 如果假定此业务流程处理 350 万条消息，则跟踪此业务流程所需的额外空间为：  
  
```  
304 bytes * 3,500,000/1024/1024 = 1015 MB ~ 0.99 GB.  
```  
  
 您需要考虑将业务流程调试器设置为“开启”的每个业务流程，以获取 BizTalk 跟踪数据库的近似大小。  
  
## <a name="see-also"></a>另请参阅  
 [使用消息变量来调整跟踪数据库的大小](../core/using-message-variables-to-size-the-tracking-database.md)   
 [大小调整跟踪数据库来跟踪消息正文](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [方案 1： 调整跟踪数据库的简单 BizTalk 消息](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [方案 2： 调整跟踪数据库的业务流程中的消息](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [方案 3： 调整跟踪数据库的消息发送到通讯组列表](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)