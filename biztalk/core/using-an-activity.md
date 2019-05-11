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
# <a name="using-an-activity"></a><span data-ttu-id="c2a83-102">通过使用活动</span><span class="sxs-lookup"><span data-stu-id="c2a83-102">Using an Activity</span></span>
<span data-ttu-id="c2a83-103">若要使用 BAM 的最简单方法是发送显式里程碑或数据使用 BAM API。</span><span class="sxs-lookup"><span data-stu-id="c2a83-103">The simplest way to use BAM is to send explicit milestones or data using the BAM API.</span></span> <span data-ttu-id="c2a83-104">您可以将 BAM 活动作为您一直在进行中同步与实际的单元的工作的 SQL 表中的记录。</span><span class="sxs-lookup"><span data-stu-id="c2a83-104">You can think of the BAM activity as a record in a SQL table that you are keeping in synchronization with the actual unit of work.</span></span>  
  
-   <span data-ttu-id="c2a83-105">调用`BeginActivity`为每个新的工作单元。</span><span class="sxs-lookup"><span data-stu-id="c2a83-105">Call `BeginActivity` for each new unit of work.</span></span>  
  
-   <span data-ttu-id="c2a83-106">调用`EndActivity`当工作完成且希望在此工作单位的上下文中没有更多的事件。</span><span class="sxs-lookup"><span data-stu-id="c2a83-106">Call `EndActivity` when the work is complete and you expect no more events in the context of this unit of work.</span></span>  
  
-   <span data-ttu-id="c2a83-107">调用[Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx)在关键位置中的实现，若要发送的数据和里程碑对信息工作者将非常有用。</span><span class="sxs-lookup"><span data-stu-id="c2a83-107">Call [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) in critical places of the implementation, to send data and milestones that will be useful to the information worker.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c2a83-108">释放前，必须刷新事件 Stream。</span><span class="sxs-lookup"><span data-stu-id="c2a83-108">The Event Stream must be flushed before disposing.</span></span> <span data-ttu-id="c2a83-109">EventStream 对象不执行自动刷新时释放的数据。</span><span class="sxs-lookup"><span data-stu-id="c2a83-109">The EventStream object does not perform an automatic flush of the data when disposed.</span></span> <span data-ttu-id="c2a83-110">这意味着您通常会编写中，将刷新流仅在完成处理您的活动后可以导致数据丢失，如果在调用刷新之前会发生异常的代码。</span><span class="sxs-lookup"><span data-stu-id="c2a83-110">This means that code you would typically write in which you flush the stream only after you have finished processing your activities can result in data loss if an exception occurs before a call to flush.</span></span>  
>   
>  <span data-ttu-id="c2a83-111">若要避免数据丢失，我们建议您封装处理并刷新在 try/finally 块中，如下面的伪代码中所示：</span><span class="sxs-lookup"><span data-stu-id="c2a83-111">To avoid data loss, we recommend that you encapsulate the processing and flush in a try/finally block as shown in the pseudo code below:</span></span>  
  
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
  
 <span data-ttu-id="c2a83-112">下面的代码示例演示如何执行操作时的工作单元是采购订单使用 BeginActivity、 UpdateActivity 和 EndActivity。</span><span class="sxs-lookup"><span data-stu-id="c2a83-112">The following example code shows how to do use BeginActivity, UpdateActivity, and EndActivity when the unit of work is a Purchase Order.</span></span> <span data-ttu-id="c2a83-113">在示例中，我们假定字符串变量**poid**标识进程中的当前采购订单：</span><span class="sxs-lookup"><span data-stu-id="c2a83-113">In the example, we assume that the string variable **poid** identifies the current Purchase Order in process:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c2a83-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2a83-114">See Also</span></span>  
 <span data-ttu-id="c2a83-115">[与事件流实现 BAM 活动](../core/implementing-bam-activities-with-event-streams.md) </span><span class="sxs-lookup"><span data-stu-id="c2a83-115">[Implementing BAM Activities with Event Streams](../core/implementing-bam-activities-with-event-streams.md) </span></span>  
 <span data-ttu-id="c2a83-116">[活动继续符](../core/activity-continuation.md) </span><span class="sxs-lookup"><span data-stu-id="c2a83-116">[Activity Continuation](../core/activity-continuation.md) </span></span>  
 <span data-ttu-id="c2a83-117">[BAM 动态基础结构](../core/bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="c2a83-117">[BAM Dynamic Infrastructure](../core/bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="c2a83-118">BAM API（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="c2a83-118">BAM API (BizTalk Server Sample)</span></span>](../core/bam-api-biztalk-server-sample.md)