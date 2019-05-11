---
title: 活动继续符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- continuation tokens
- activities [BAM], code samples
- activities [BAM], continuation tokens
- continuations, activities [BAM]
- code samples, activities [BAM]
ms.assetid: 47d91ae6-77c1-4efb-940f-a7b3a325e5bd
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a8615dc75802b643783e3c366159180b740521a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361695"
---
# <a name="activity-continuation"></a><span data-ttu-id="cb4a9-102">活动继续符</span><span class="sxs-lookup"><span data-stu-id="cb4a9-102">Activity Continuation</span></span>
<span data-ttu-id="cb4a9-103">（也称为业务活动） 的 BAM 活动可以跨多个的异类应用程序 （例如，管道、 两个业务流程、 业务线应用程序和另一个管道）。</span><span class="sxs-lookup"><span data-stu-id="cb4a9-103">The BAM activity (also called the business activity) can span multiple heterogeneous applications (for example, a pipeline, two orchestrations, a line-of-business application, and then another pipeline).</span></span> <span data-ttu-id="cb4a9-104">BAM 基础结构可以关联来自多个应用程序的一些帮助开发人员 – 名为的概念事件"*延续*，"这在下图中所示。</span><span class="sxs-lookup"><span data-stu-id="cb4a9-104">The BAM infrastructure can correlate the events from multiple applications with a little help from the developer – a concept called "*Continuation*," which is shown in the following figure.</span></span>  
  
 <span data-ttu-id="cb4a9-105">![](../core/media/ebiz-prog-bam-fig4-app-scopes-cont-tokens.gif "ebiz_prog_bam_fig4_app_scopes_cont_tokens")</span><span class="sxs-lookup"><span data-stu-id="cb4a9-105">![](../core/media/ebiz-prog-bam-fig4-app-scopes-cont-tokens.gif "ebiz_prog_bam_fig4_app_scopes_cont_tokens")</span></span>  

## <a name="applications"></a><span data-ttu-id="cb4a9-106">应用程序</span><span class="sxs-lookup"><span data-stu-id="cb4a9-106">Applications</span></span>  
 <span data-ttu-id="cb4a9-107">活动的第一部分发生在销售应用程序中，活动的第二部分发生在打包和程序集的应用程序，并最后，发货现已推出配送应用程序。</span><span class="sxs-lookup"><span data-stu-id="cb4a9-107">The first part of the activity happens in the Sales application, the second part of the activity happens in the Packaging & Assembly application, and finally, the delivery progress is available in the Shipping application.</span></span> <span data-ttu-id="cb4a9-108">每个应用程序使用不同的 Id 为当前的工作单位： 采购订单 (PO) 编号、 销售订单数 (SO) 以及发货订单数 (UPS)。</span><span class="sxs-lookup"><span data-stu-id="cb4a9-108">Each application uses different IDs for the current work unit: purchase order number (PO), sales order number (SO), and shipping order number (UPS).</span></span> <span data-ttu-id="cb4a9-109">若要将两个不同的应用程序之间的事件相关联，必须：</span><span class="sxs-lookup"><span data-stu-id="cb4a9-109">To correlate the events between two different applications, you must:</span></span>  
  
- <span data-ttu-id="cb4a9-110">标识继续符，可供这两个应用程序 （例如，正在交换的消息的一部分） 的数据的一个唯一的。</span><span class="sxs-lookup"><span data-stu-id="cb4a9-110">Identify the continuation token – a unique piece of data that is available to both applications (for example, the part of the message being exchanged).</span></span>  
  
- <span data-ttu-id="cb4a9-111">在第一个应用程序中调用 EnableContinuation 并传递与当前 ActivityID 一起继续标记。</span><span class="sxs-lookup"><span data-stu-id="cb4a9-111">Call EnableContinuation in the first application and pass the continuation token along with the current ActivityID.</span></span>  
  
- <span data-ttu-id="cb4a9-112">请勿在第二个应用程序中调用 BeginActivity。</span><span class="sxs-lookup"><span data-stu-id="cb4a9-112">Do not call BeginActivity in the second application.</span></span>  
  
- <span data-ttu-id="cb4a9-113">通过使用继续标记而不 ActivityID 触发第二个应用程序中的所有后续事件。</span><span class="sxs-lookup"><span data-stu-id="cb4a9-113">Fire all subsequent events in the second application by using the continuation token instead of ActivityID.</span></span>  
  
  <span data-ttu-id="cb4a9-114">下面的代码示例演示如何使用三个应用程序之间的活动继续符：</span><span class="sxs-lookup"><span data-stu-id="cb4a9-114">The following code example illustrates the use of activity continuation among three applications:</span></span>  
  
  <span data-ttu-id="cb4a9-115">**采购订单应用程序**</span><span class="sxs-lookup"><span data-stu-id="cb4a9-115">**Purchase Order Application**</span></span>  
  
```  
string oID="PO#123";  
string soID="SO#265";  
es.BeginActivity("PurchaseOrder",poID);  
es.UpdateActivity("PurchaseOrder",poID,  
    "POReceived",DateTime.UtcNow,  
    "POAmount",100,  
"CustomerCity","Seattle");  
es.EnableContinuation(  
   "PurchaseOrder",poId,soID);  
es.EndActivity("PurchaseOrder",poID);  
```  
  
 <span data-ttu-id="cb4a9-116">**执行应用程序**</span><span class="sxs-lookup"><span data-stu-id="cb4a9-116">**Fulfillment Application**</span></span>  
  
```  
string soID="SO#265";  
string upsID="UPS#97892";  
es.UpdateActivity("PurchaseOrder",soID,  
    "POApproved",DateTime.UtcNow,  
    "ProductName","ProductA");  
es.EnableContinuation(  
   "PurchaseOrder",soID,upsID);  
es.EndActivity("PurchaseOrder",soID);  
```  
  
 <span data-ttu-id="cb4a9-117">**发货应用程序**</span><span class="sxs-lookup"><span data-stu-id="cb4a9-117">**Shipping Application**</span></span>  
  
```  
string upsID="UPS#97892"  
es.UpdateActivity("PurchaseOrder", upsID,  
"POShipped",DateTime.UtcNow);  
es.EndActivity("PurchaseOrder",upsID)  
  
```  
  
 <span data-ttu-id="cb4a9-118">请遵循这些准则在代码中使用活动继续符：</span><span class="sxs-lookup"><span data-stu-id="cb4a9-118">Follow these guidelines to use activity continuation in your code:</span></span>  
  
-   <span data-ttu-id="cb4a9-119">当最终用户必须将不同的应用程序的工作视为同一活动的一部分时，仅使用继续符。</span><span class="sxs-lookup"><span data-stu-id="cb4a9-119">Only use continuation when the end user must treat the work of different applications as part of the same activity.</span></span> <span data-ttu-id="cb4a9-120">每个应用程序使用单独的活动并创建活动关系，如果最终用户视图中有意义的活动的每个应用程序的工作。</span><span class="sxs-lookup"><span data-stu-id="cb4a9-120">Use separate activities for each application and create an activity relationship if the end user views the work in each applications as meaningful activities.</span></span>  
  
-   <span data-ttu-id="cb4a9-121">如果应用程序中的工作单位不具有一对一的关系，您可以使用活动关系而不是继续符，例如，销售订单涉及多次发货存在时。</span><span class="sxs-lookup"><span data-stu-id="cb4a9-121">If the work units in the applications do not have a one-to-one relationship, you can use activity relationships but not continuation, for example, when multiple shipments exist for a sales order.</span></span>  
  
-   <span data-ttu-id="cb4a9-122">如果以同步方式将数据发送到 BAM （使用 DirectEventStream） 和 ActivityID 传播到所有涉及的组件，则不需要使用继续符。</span><span class="sxs-lookup"><span data-stu-id="cb4a9-122">If you send data to BAM synchronously (using DirectEventStream) and the ActivityID is propagated to all involved components, then you do not need to use continuation.</span></span>  
  
-   <span data-ttu-id="cb4a9-123">如果以异步方式将数据发送到 BAM (使用 BufferedEventStream 或通过业务流程)，则即使向所有组件传播 ActivityID，必须使用继续符。</span><span class="sxs-lookup"><span data-stu-id="cb4a9-123">If you send data to BAM asynchronously (using BufferedEventStream or from orchestrations), then you must use continuation even if the ActivityID is propagated to all components.</span></span> <span data-ttu-id="cb4a9-124">在这种情况下，需要通过前缀使用唯一字符串 （例如，应用程序名称） 在每个应用程序中使用 activityid 各不相同。</span><span class="sxs-lookup"><span data-stu-id="cb4a9-124">In this case, you need to use a different ActivityID in each application by prefixing it with a unique string (for example, Application Name).</span></span> <span data-ttu-id="cb4a9-125">这是必需的因为不同的应用程序中的数据可能会到达 BAM 的随机顺序，BAM 必须隐藏顺序颠倒的事件，以确保正确的查询和聚合结果。</span><span class="sxs-lookup"><span data-stu-id="cb4a9-125">This is necessary because the data from different applications may arrive to BAM in random order and BAM has to hide the out-of-order events to ensure correct query and aggregation results.</span></span>  
  
-   <span data-ttu-id="cb4a9-126">延续任务不需要重新编写您的应用程序交换更多数据。</span><span class="sxs-lookup"><span data-stu-id="cb4a9-126">Continuation does not require rewriting your applications to exchange more data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb4a9-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb4a9-127">See Also</span></span>  
  
 <span data-ttu-id="cb4a9-128">[BAM 动态基础结构](../core/bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="cb4a9-128">[BAM Dynamic Infrastructure](../core/bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="cb4a9-129">[BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md) </span><span class="sxs-lookup"><span data-stu-id="cb4a9-129">[BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md) </span></span>  
 [<span data-ttu-id="cb4a9-130">BAM 端对端（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="cb4a9-130">BAM End-to-End (BizTalk Server Sample)</span></span>](../core/bam-end-to-end-biztalk-server-sample.md)