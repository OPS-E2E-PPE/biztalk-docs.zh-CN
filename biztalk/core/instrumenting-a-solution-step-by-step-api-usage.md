---
title: 检测解决方案：分步 API 使用情况 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9e027ab-1927-4905-8970-8061ac55d591
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c9d3ecd3f479729acd720a61254a6f82c655a0a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382053"
---
# <a name="instrumenting-a-solution-step-by-step-api-usage"></a><span data-ttu-id="36879-102">检测解决方案：分步 API 使用情况</span><span class="sxs-lookup"><span data-stu-id="36879-102">Instrumenting a Solution: Step-by-Step API Usage</span></span>
<span data-ttu-id="36879-103">本主题说明如何用关键的 BAM API 类检测应用程序。</span><span class="sxs-lookup"><span data-stu-id="36879-103">This topic describes how to instrument an application using the key BAM API class.</span></span> <span data-ttu-id="36879-104">在以下代码段中，我们使用常量和检测应用程序所必需的最少代码对示例代码进行了简化。</span><span class="sxs-lookup"><span data-stu-id="36879-104">In the following code snippets we have simplified the sample code by using constants and by using the minimum code necessary to instrument an application.</span></span>  
  
 <span data-ttu-id="36879-105">以下代码段演示如何创建新的 [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/Microsoft.BizTalk.Bam.EventObservation.EventStream.aspx) 对象，尤其是 [Microsoft.BizTalk.Bam.EventObservation.DirectEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx)。</span><span class="sxs-lookup"><span data-stu-id="36879-105">The following code snippet demonstrates how you create a new [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/Microsoft.BizTalk.Bam.EventObservation.EventStream.aspx) object, specifically a [Microsoft.BizTalk.Bam.EventObservation.DirectEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx).</span></span> <span data-ttu-id="36879-106">在此代码段中，第一个参数指定 BAM 主导入数据库数据存储区的连接字符串，第二个参数指定事件写入数据存储区的频率。</span><span class="sxs-lookup"><span data-stu-id="36879-106">In this snippet, the first parameter specifies the connection string to the data store of the BAM Primary Import database and the second parameter specifies the frequency with which the events are written to the data store.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36879-107">BAM 只支持与 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 数据存储区的连接。</span><span class="sxs-lookup"><span data-stu-id="36879-107">BAM supports connections only to [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] data stores.</span></span> <span data-ttu-id="36879-108">该示例连接字符串代表建立连接所需的最小连接字符串。</span><span class="sxs-lookup"><span data-stu-id="36879-108">The sample connection string represents the minimal connection string required to establish a connection.</span></span> <span data-ttu-id="36879-109">您的配置可能要求在连接字符串中指定其他参数。</span><span class="sxs-lookup"><span data-stu-id="36879-109">Your configuration may require additional parameters to be specified in the connection string.</span></span>  
  
 <span data-ttu-id="36879-110">如果 *FlushThreshold* 值为 0，则指定事件不会自动写入，你必须调用 Flush 方法来写入事件。</span><span class="sxs-lookup"><span data-stu-id="36879-110">A *FlushThreshold* value of 0 specifies that events are not automatically written and that you must call the Flush method to write the events.</span></span> <span data-ttu-id="36879-111">如果值为 1，则各事件在发生时即被写入。</span><span class="sxs-lookup"><span data-stu-id="36879-111">A value of one causes each event to be written when it occurs.</span></span> <span data-ttu-id="36879-112">如果值大于 1，则指定在发生的事件数量达到指定的批次累计数量时，写入这些事件。</span><span class="sxs-lookup"><span data-stu-id="36879-112">Values of greater than one specify that events are written when a batch of the specified accumulation has occurred.</span></span> <span data-ttu-id="36879-113">使用大于 1 的值有助于提高性能。</span><span class="sxs-lookup"><span data-stu-id="36879-113">Using a value of greater than one can be useful to enhance performance.</span></span>  
  
```  
// Specify the DES connection string.  
const string connBAMPIT =  
   "Integrated Security=SSPI;server=.;database=BAMPrimaryImport";  
// Write the activity update data on every call.  
int flushThreshold = 1;  
// Create a DES instance  
EventStream es =   
   new DirectEventStream(connBAMPIT, flushThreshold);  
```  
  
 <span data-ttu-id="36879-114">创建 [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/Microsoft.BizTalk.Bam.EventObservation.EventStream.aspx) 对象后，即可开始活动，并可用收集的里程碑和数据来更新活动表。</span><span class="sxs-lookup"><span data-stu-id="36879-114">Once the [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/Microsoft.BizTalk.Bam.EventObservation.EventStream.aspx) object has been created, you can begin the activity and start updating the activity table with the collected milestones and data.</span></span> <span data-ttu-id="36879-115">部署 BAM 活动后，将在 BAM 主导入数据库中创建五个表。</span><span class="sxs-lookup"><span data-stu-id="36879-115">When the BAM activity was deployed, five tables were created in the BAM Primary Import database.</span></span> <span data-ttu-id="36879-116">有关开发过程的详细信息，请参阅 [Overview of the BAM Development Process](../core/overview-of-the-bam-development-process.md)。</span><span class="sxs-lookup"><span data-stu-id="36879-116">For more information about the development process, see [Overview of the BAM Development Process](../core/overview-of-the-bam-development-process.md).</span></span>  
  
 <span data-ttu-id="36879-117">调用 [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) 方法将向 bam_ PurchaseOrder_Activity 表添加一条记录。</span><span class="sxs-lookup"><span data-stu-id="36879-117">Calling the [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) method adds a record to the bam_ PurchaseOrder_Activity table.</span></span> <span data-ttu-id="36879-118">第一个参数包含要更新的活动的名称，第二个参数包含此活动实例的标识符。</span><span class="sxs-lookup"><span data-stu-id="36879-118">The first parameter contains the name of the activity being updated and the second parameter contains an identifier for this instance of the activity.</span></span> <span data-ttu-id="36879-119">标识符可以是任何字符串，但它在针对活动的记录集中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="36879-119">The identifier can be any string, but it must be unique in the record set for the activity.</span></span>  
  
 <span data-ttu-id="36879-120">此时，记录不包含任何数据。</span><span class="sxs-lookup"><span data-stu-id="36879-120">At this point the record does not contain any data.</span></span> <span data-ttu-id="36879-121">[Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) 方法使用捕获的事件数据来更新记录。</span><span class="sxs-lookup"><span data-stu-id="36879-121">The [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) method updates the record with the captured event data.</span></span> <span data-ttu-id="36879-122">您需再次指定活动和活动实例标识符。</span><span class="sxs-lookup"><span data-stu-id="36879-122">Once again you specify an activity and the activity instance identifier.</span></span> <span data-ttu-id="36879-123">你将传递数据项的 [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) 方法名称/值对，以及在活动中定义的里程碑。</span><span class="sxs-lookup"><span data-stu-id="36879-123">You pass the [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) method name value pairs of data items and milestones you defined in the activity.</span></span> <span data-ttu-id="36879-124">例如，我们的活动定义了一个 MS_Received 里程碑。</span><span class="sxs-lookup"><span data-stu-id="36879-124">For example, our activity defined a milestone MS_Received.</span></span> <span data-ttu-id="36879-125">部署此活动后，在 bam_ PurchaseOrder_Activity 表中为该里程碑创建了一列。</span><span class="sxs-lookup"><span data-stu-id="36879-125">When the activity was deployed, a column in the bam_ PurchaseOrder_Activity table was created for the milestone.</span></span> <span data-ttu-id="36879-126">调用 [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) 方法将指定 MS_Received 和 DateTime.UtcNow 的名称/值对，以用采购订单的接收日期更新活动。</span><span class="sxs-lookup"><span data-stu-id="36879-126">The call to the [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) method specifies the name value pair of MS_Received and DateTime.UtcNow to update the activity with received date for the purchase order.</span></span>  
  
```  
// When a purchase order is received, you call the  
// BeginActivity method in the receive application.  
// You can then capture the event data by calling   
// the UpdateActivity method.  
es.BeginActivity ("PurchaseOrder", "PO123");  
es.UpdateActivity ("PurchaseOrder", "PO123",  
                    "MS_Received", DateTime.UtcNow,   
                    "T_Customer", "Joe");  
```  
  
 <span data-ttu-id="36879-127">在此示例中，我们继续执行第二个活动。</span><span class="sxs-lookup"><span data-stu-id="36879-127">In this sample we continue to a second activity.</span></span> <span data-ttu-id="36879-128">有关继续的详细信息，请参阅 [Activity Continuation](../core/activity-continuation.md)。</span><span class="sxs-lookup"><span data-stu-id="36879-128">For more information about continuations, see [Activity Continuation](../core/activity-continuation.md).</span></span>  
  
 <span data-ttu-id="36879-129">若要启用其他被检测的应用程序来更新 PurchaseOrder 活动，可包含一个对 [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="36879-129">To enable other instrumented applications to update the PurchaseOrder activity, you include a call to the [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) method.</span></span> <span data-ttu-id="36879-130">此调用指定其他应用程序可参与的活动、被跟踪活动实例的标识符以及其他应用程序用于更新活动的继续符。</span><span class="sxs-lookup"><span data-stu-id="36879-130">The call specifies the activity to which other applications can contribute, the identifier for the instance of the activity being tracked, and the continuation token that other applications will use to update the activity.</span></span> <span data-ttu-id="36879-131">将在 bam_ PurchaseOrder_continuations 表中写入一条记录，以跟踪继续符的状态。</span><span class="sxs-lookup"><span data-stu-id="36879-131">A record is written to the bam_ PurchaseOrder_continuations table to track the status of the continuation.</span></span> <span data-ttu-id="36879-132">如果活动继续执行其他进程，则使用唯一的继续标记为 [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) 方法的每次调用写入一条记录。</span><span class="sxs-lookup"><span data-stu-id="36879-132">If the activity continues to other processes, a record is written for each call to the [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) method with a unique continuation token.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="36879-133">继续方案中的每个代码段必须有自己的 [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) 方法调用。</span><span class="sxs-lookup"><span data-stu-id="36879-133">Every code segment in a continuation scenario must have its own [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) method call.</span></span> <span data-ttu-id="36879-134">否则将导致虚的/孤立的活动记录。</span><span class="sxs-lookup"><span data-stu-id="36879-134">Failing to do so will result in a dangling/orphaned activity record.</span></span>  
>   
>  <span data-ttu-id="36879-135">但是，只有（使用实际活动 ID 的）第一个段具有 [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) 方法；（使用各自唯一标记 ID 的）所有其他段均不得调用 [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) 方法。</span><span class="sxs-lookup"><span data-stu-id="36879-135">However, only the first segment (that uses the actual activity ID) has the [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) method; all the other segments (that use their own unique token ID) must not call the [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) method.</span></span>  
  
 <span data-ttu-id="36879-136">调用 [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) 方法后，其他组件可以使用指定继续标记而非活动 ID 的 [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) 来更新采购订单活动。</span><span class="sxs-lookup"><span data-stu-id="36879-136">After the [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) method is called, other components can update the purchase order activity using [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) specifying the continuation token instead of the activity ID.</span></span> <span data-ttu-id="36879-137">当其他组件已完成其任务时，每个组件必须使用继续标记来调用 [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) 以通知 BAM 基础结构已没有更多的事件。</span><span class="sxs-lookup"><span data-stu-id="36879-137">When the other components have completed their tasks, each of the components must call [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) with the continuation token to inform the BAM infrastructure that no more events are expected.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="36879-138">调用 [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) 方法后，如果在其中继续执行活动的进程从未使用继续标记调用 [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) 方法，则活动可能会变为孤立活动。</span><span class="sxs-lookup"><span data-stu-id="36879-138">Once the [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) method is called, it is possible for an activity to become orphaned if the process in which the activity is continued never calls an [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) method with the continuation token.</span></span>  
  
```  
// Continue the activity to the next process that has been  
// instrumented to handle the continuation.  
es.EnableContinuation("PurchaseOrder", “PO123”, “AP123”);  
```  
  
 <span data-ttu-id="36879-139">最后，通过调用指定活动名称和活动标识符的 [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) 方法来结束活动。</span><span class="sxs-lookup"><span data-stu-id="36879-139">Finally, the activity is finalized by calling the [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) method specifying the activity name and the activity identifier.</span></span> <span data-ttu-id="36879-140">如果没有未完成的继续符，则活动将被移动到 bam_ PurchaseOrder _completed 表中。</span><span class="sxs-lookup"><span data-stu-id="36879-140">If there are no unfinished continuations, the activity is moved to the bam_ PurchaseOrder _completed table.</span></span> <span data-ttu-id="36879-141">如果继续符活动未能完成，则活动可能变为孤立活动。</span><span class="sxs-lookup"><span data-stu-id="36879-141">It is possible for activities to become orphaned if continuation activities fail to complete.</span></span>  
  
```  
// Activity from this segment (PO submission) is completed  
es.EndActivity("PurchaseOrder", “PO123”);  
```  
  
 <span data-ttu-id="36879-142">当活动继续不同的进程时，将检测应用程序以更新活动表，方法是：调用 [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) ，并指定活动名称和在 [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) 方法调用中声明的继续标记。</span><span class="sxs-lookup"><span data-stu-id="36879-142">When the activity continues to separate process, the application is instrumented to update the activity table by calling [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) specifying the activity name and the continuation token declared in the [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) method call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36879-143">处理继续执行的活动的进程不调用 [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) 方法。</span><span class="sxs-lookup"><span data-stu-id="36879-143">The process handling the continued activity does not call the [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) method.</span></span> <span data-ttu-id="36879-144">[Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) 方法通过在 BAM 主导入数据库中创建表来创建一个活动实例。</span><span class="sxs-lookup"><span data-stu-id="36879-144">The [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) method creates an instance of the activity by creating the tables in the BAM Primary Import database.</span></span> <span data-ttu-id="36879-145">继续执行活动的进程将更新已存在的活动的实例。</span><span class="sxs-lookup"><span data-stu-id="36879-145">The process to which the activity is continued is updating the instance of the already existing activity.</span></span>  
  
```  
// update when the order is approved  
es.UpdateActivity ("PurchaseOrder", “AP123”, "MS_Approved",  
                    DateTime.UtcNow, "T_Product", "Widget");  
  
// update when the product is ready for shipment  
es.UpdateActivity ("PurchaseOrder", “AP123”,  
                   "MS_Ready", DateTime.UtcNow);  
```  
  
 <span data-ttu-id="36879-146">在本示例的部分工作流中，代码将指定一个引用，在此情况下为特定类型的引用，即相关活动。</span><span class="sxs-lookup"><span data-stu-id="36879-146">Part of the workflow for this sample the code specifies a reference, in this case a specific type of reference - a related activity.</span></span> <span data-ttu-id="36879-147">通过指定一个相关活动，可创建从主活动到在 BAM 门户中查看活动的用户所关心的其他活动的链接。</span><span class="sxs-lookup"><span data-stu-id="36879-147">By specifying a related activity you create a link from your primary activity to other activities that are of interest to a user viewing the activity in the BAM portal.</span></span>  
  
 <span data-ttu-id="36879-148">调用 [Microsoft.BizTalk.Bam.EventObservation.EventStream.AddRelatedActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.addrelatedactivity.aspx) 方法将把记录写入链接活动的 bam_ PurchaseOrder_ActiveRelationships 中。</span><span class="sxs-lookup"><span data-stu-id="36879-148">The call to the [Microsoft.BizTalk.Bam.EventObservation.EventStream.AddRelatedActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.addrelatedactivity.aspx) method writes a record to the bam_ PurchaseOrder_ActiveRelationships linking the activities.</span></span>  
  
```  
// These are shipped in two shipments.  
// Relates the current purchase order   
// instance to two shippings.  
// Note: only one direction  
es.AddRelatedActivity ("PurchaseOrder", “AP123”,  
                       "Shipping", “UPS101”);  
es.AddRelatedActivity ("PurchaseOrder", “AP123”,  
                       "Shipping", “UPS102”);  
```  
  
 <span data-ttu-id="36879-149">若要结束继续的活动，请调用为要结束的继续操作指定继续标记的 [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) 方法。</span><span class="sxs-lookup"><span data-stu-id="36879-149">To end the continued activity you call the [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) method specifying the continuation token for the continuation that is ending.</span></span> <span data-ttu-id="36879-150">如果没有其他未完成的继续符，则采购订单活动将移动到已完成表中。</span><span class="sxs-lookup"><span data-stu-id="36879-150">If there are no other unfinished continuations, the purchase order activity is moved to the completed table.</span></span>  
  
```  
// Activity from this segment (ApprovalProcess) is completed  
es.EndActivity("PurchaseOrder", “AP123”);  
```  
  
## <a name="complete-code-sample"></a><span data-ttu-id="36879-151">完整的代码示例</span><span class="sxs-lookup"><span data-stu-id="36879-151">Complete Code Sample</span></span>  
  
```  
//---------------------------------------------------------------------  
// File:BAMMinimalSample.cs  
//   
// Summary: Demonstrates how to instrument an application   
//using BAM APIs to track useful information.  
//  
// Sample: BAM Api Sample  
//  
//---------------------------------------------------------------------  
// This file is part of the Microsoft BizTalk Server SDK  
//  
// Copyright (c) Microsoft Corporation. All rights reserved.  
//  
// This source code is intended only as a supplement to Microsoft   
// BizTalk Server release and/or on-line documentation. See   
// these other materials for detailed information regarding Microsoft // code samples.  
//  
// THIS CODE AND INFORMATION ARE PROVIDED "AS IS" WITHOUT WARRANTY OF  
// ANY KIND, WHETHER EXPRESSED OR IMPLIED, INCLUDING BUT NOT LIMITED TO // THE IMPLIED WARRANTIES OF MERCHANTABILITY AND/OR FITNESS FOR A   
// PARTICULAR PURPOSE.  
//---------------------------------------------------------------------  
// This sample requires that you add the     
// Microsoft.BizTalk.Bam.EventObservation.dll to the   
// references in the Visual Studio Solution.  
  
using System;  
using System.Text;  
using Microsoft.BizTalk.Bam.EventObservation;  
  
namespace EventStreamSample  
{  
  
    static void Main(string[] args)  
    {  
        //   
  // The following code would appear in a purchase order  
   // receipt application.  
        //  
  
        // Specify the DES connection string.  
        const string connBAMPIT =  
            "Integrated Security=SSPI;server=.;database=BAMPrimaryImport";  
  
        // Write the activity update data on every call.  
        int flushThreshold = 1;  
  
        // Create an instance of the DirectEventStream.  
        EventStream es =   
               new DirectEventStream(connBAMPIT, flushThreshold);  
  
        // When a purchase order is received, you call the  
       // BeginActivity method in the receive application.  
  // You can then capture the event data by calling   
        // the UpdateActivity method.  
        es.BeginActivity ("PurchaseOrder", "PO123");  
        es.UpdateActivity ("PurchaseOrder", "PO123",  
                    "MS_Received", DateTime.UtcNow,   
                    "T_Customer", "Joe");  
  
   // Continue the activity to the next process that has been  
   // instrumented to handle the continuation.  
        es.EnableContinuation("PurchaseOrder", “PO123”, “AP123”);  
  
        // Activity from this segment (PO submission) is completed  
        // end activity is synonymous to IsCompleted = 1  
        es.EndActivity("PurchaseOrder", “PO123”);  
  
        //  
        // The following code would typically appear in a separate   
        // application that monitors the approval process  
        // (ApprovalProcess.exe)  
        //  
  
        // update when the order is approved  
        es.UpdateActivity ("PurchaseOrder", “AP123”, "MS_Approved",  
                            DateTime.UtcNow, "T_Product", "Widget");  
  
        // update when the product is ready for shipment  
        es.UpdateActivity ("PurchaseOrder", “AP123”,  
                            "MS_Ready", DateTime.UtcNow);  
  
        // These are shipped in two shipments.  
        // Relates the current purchase order  
        // instance to two shippings.  
        // Note: only one direction  
        es.AddRelatedActivity ("PurchaseOrder", “AP123”,  
                                "Shipping", “UPS101”);  
        es.AddRelatedActivity ("PurchaseOrder", “AP123”,  
                                "Shipping", “UPS102”);  
  
        // Activity from this segment (ApprovalProcess) is completed  
        es.EndActivity("PurchaseOrder", “AP123”);  
  
        // In another Shipping application, two shipments with  
            ID’s UPS101 and UPS102 will be created.  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="36879-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="36879-152">See Also</span></span>  
 [<span data-ttu-id="36879-153">与事件流实现 BAM 活动</span><span class="sxs-lookup"><span data-stu-id="36879-153">Implementing BAM Activities with Event Streams</span></span>](../core/implementing-bam-activities-with-event-streams.md)