---
title: "使用活动 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e218e2a-27f8-4df2-a1e0-27392112d369
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13b56424e06bdb8fad043acd92c22a88ca19f478
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-an-activity"></a>使用活动
使用 BAM 的最简单的方式是使用 BAM API 发送显式里程碑或数据。 您可以将 BAM 活动看作 SQL 表中与实际工作单位保持同步的记录。  
  
-   调用`BeginActivity`为每个新的工作单元。  
  
-   调用`EndActivity`在工作完成且希望查看此工作单元中的上下文中没有更多的事件。  
  
-   调用[Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx)在关键位置中的实现，若要发送的数据并对信息工作者将非常有用的里程碑。  
  
> [!IMPORTANT]
>  在释放之前，必须刷新事件流。 在释放 EventStream 对象时，不会执行自动刷新数据的操作。 通常情况下您编写的代码只在已处理完活动后才刷新事件流，这意味着如果在调用刷新操作之前发生了异常，则可能导致数据丢失。  
>   
>  为了避免数据丢失，建议您将处理过程和刷新操作封装在 try/finally 块中，如下面的伪代码所示：  
  
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
  
 下面的示例代码显示了当工作单位为采购订单时如何使用 BeginActivity、UpdateActivity 和 EndActivity。 在示例中，我们假定字符串变量**poid**标识进程中当前的采购订单：  
  
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
  
## <a name="see-also"></a>另请参阅  
 [实现事件流 BAM 活动](../core/implementing-bam-activities-with-event-streams.md)   
 [活动延续](../core/activity-continuation.md)   
 [BAM 动态基础结构](../core/bam-dynamic-infrastructure.md)   
 [BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md)