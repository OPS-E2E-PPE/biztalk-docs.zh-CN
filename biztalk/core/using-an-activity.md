---
title: 通过使用活动 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5e218e2a-27f8-4df2-a1e0-27392112d369
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2da2176ba4573762853f44447284c6aeb73f57e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399899"
---
# <a name="using-an-activity"></a>通过使用活动
若要使用 BAM 的最简单方法是发送显式里程碑或数据使用 BAM API。 您可以将 BAM 活动作为您一直在进行中同步与实际的单元的工作的 SQL 表中的记录。  
  
-   调用`BeginActivity`为每个新的工作单元。  
  
-   调用`EndActivity`当工作完成且希望在此工作单位的上下文中没有更多的事件。  
  
-   调用[Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx)在关键位置中的实现，若要发送的数据和里程碑对信息工作者将非常有用。  
  
> [!IMPORTANT]
>  释放前，必须刷新事件 Stream。 EventStream 对象不执行自动刷新时释放的数据。 这意味着您通常会编写中，将刷新流仅在完成处理您的活动后可以导致数据丢失，如果在调用刷新之前会发生异常的代码。  
>   
>  若要避免数据丢失，我们建议您封装处理并刷新在 try/finally 块中，如下面的伪代码中所示：  
  
```  
BufferedEventStream es = new BufferedEventStream(…)  
Try  
{  
   // Do the activity processing here.  
}  
Finally  
{  
   if (es != null ) es.Flush();  
}  
```  
  
 下面的代码示例演示如何执行操作时的工作单元是采购订单使用 BeginActivity、 UpdateActivity 和 EndActivity。 在示例中，我们假定字符串变量**poid**标识进程中的当前采购订单：  
  
```  
using Microsoft.BizTalk.BAM.EventObservation;  
...   
EventStream es=new DirectEventStream(connectionString,1);  
...  
// At the beginning of the processing of a new work:  
//    Here poid is a string variable that has the current   
//    Purchase Order identifier (e.g. PO number)  
es.BeginActivity("PurchaseOrder",poid);  
es.UpdateActivity("PurchaseOrder",poid,  
    "POReceived",DateTime.UtcNow,  
    "POAmount",100,  
    "CustomerName",""Joe",  
    "CustomerCity","Seattle");  
...  
// few days later  
es.UpdateActivity("PurchaseOrder",poid,  
    "POApproved",DateTime.UtcNow,  
    "ProductName","Widget");  
...  
// and another few days later  
es. UpdateActivity("PurchaseOrder",poid,  
    "POShipped",DateTime.UtcNow);  
...  
// and finally  
es. UpdateActivity("PurchaseOrder",poid,  
    "Delivered",DateTime.UtcNow);  
es.EndActivity("PurchaseOrder",poid);  
```  
  
## <a name="see-also"></a>请参阅  
 [与事件流实现 BAM 活动](../core/implementing-bam-activities-with-event-streams.md)   
 [活动继续符](../core/activity-continuation.md)   
 [BAM 动态基础结构](../core/bam-dynamic-infrastructure.md)   
 [BAM API（BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md)