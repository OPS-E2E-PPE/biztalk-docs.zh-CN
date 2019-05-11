---
title: 应用场景 4：为所有消息调整跟踪数据库的大小 |Microsoft Docs
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
ms.openlocfilehash: 123423003377d199ebd2aea54674fe820d8debff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308568"
---
# <a name="scenario-4-sizing-the-tracking-database-for-all-messages"></a>应用场景 4：为所有消息调整跟踪数据库的大小
如果你有 Microsoft® BizTalk Server® 2004年实施中存在的所有三种消息方案，需要将加在一起的所有方案结果来确定 BizTalk 跟踪数据库的大小。  
  
 从上面所示的示例：  
  
|应用场景|每年，以 gb 为单位所需的空间|  
|--------------|-------------------------------------|  
|简单消息|4.78|  
|业务流程中消息|7.18|  
|在业务流程发送到分发列表中的消息|10.8|  
|**总计**|22.04|  
  
 此外，如果我们打开消息正文跟踪所有三个方案，我们会得到以下结果：  
  
|应用场景|每年，以 gb 为单位所需的空间|  
|--------------|-------------------------------------|  
|简单消息|50.1|  
|业务流程中消息|50.1|  
|在业务流程发送到分发列表中的消息|83.45|  
|**总计**|183.65|  
  
 这将为您提供为 205.69 GB 年增长总计对 BizTalk 跟踪数据库。 此图不包括任何意外情况。 如果您决定将 10%的应急添加到此总数建议，然后应计划 BizTalk 跟踪数据库每年增长 227.94 GB。 在此之上，则应考虑由于 SQL 索引、 存储等的开销。如有可能在测试中运行的测试方案后，应使乘法因子。  
  
## <a name="other-factors-affecting-biztalk-tracking-database-size"></a>其他因素影响 BizTalk 跟踪数据库大小  
 有其他项，例如业务流程中所使用的形状，也会影响 BizTalk 跟踪数据库的大小。  
  
 如果业务流程调试器选项开启，它默认情况下，即在业务流程中每个形状的状态将保存到 BizTalk 跟踪数据库。  
  
 若要确定跟踪形状状态所需大小的公式为：  
  
```  
[(# of object shapes ] * 76 bytes  
```  
  
 例如，在下图中，您将使用下面的公式来确定 BizTalk 跟踪大小：  
  
```  
((4) * 76 bytes = 304 bytes  
```  
  
 ![业务流程示例](../core/media/sample-orchestration.gif "Sample_orchestration")  
  
 如果我们假定此业务流程处理 350 万条消息，以跟踪此业务流程所需的额外空间为：  
  
```  
304 bytes * 3,500,000/1024/1024 = 1015 MB ~ 0.99 GB.  
```  
  
 您需要考虑每个业务流程具有业务流程调试器设置为"打开"以获取 BizTalk 跟踪数据库的近似大小。  
  
## <a name="see-also"></a>请参阅  
 [使用消息变量调整跟踪数据库的大小](../core/using-message-variables-to-size-the-tracking-database.md)   
 [调整跟踪数据库来跟踪消息正文大小](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [方案 1：为简单 BizTalk 消息调整跟踪数据库的大小](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [方案 2：为业务流程中消息调整跟踪数据库的大小](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [方案 3:为发送到分发列表的消息调整跟踪数据库的大小](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)