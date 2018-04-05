---
title: 活动关系 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], relationships
ms.assetid: da7c7205-18c6-44df-af03-3140214c84e6
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3709ad02ed082595665c68485502847b52e5a1d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="activity-relationships"></a><span data-ttu-id="8effa-102">活动关系</span><span class="sxs-lookup"><span data-stu-id="8effa-102">Activity Relationships</span></span>
<span data-ttu-id="8effa-103">当活动与一个或多个其他活动关联时，则存在活动关系。</span><span class="sxs-lookup"><span data-stu-id="8effa-103">An activity relationship exists when an activity relates to one or more other activities.</span></span> <span data-ttu-id="8effa-104">例如，多个发货活动与单个采购订单活动相关，或者一个发货活动包含来自两个采购订单活动中的项。</span><span class="sxs-lookup"><span data-stu-id="8effa-104">An example of this is having multiple Shipment activities related to a single Purchase Order activity, or one Shipment activity containing items from two Purchase Order activities.</span></span>  
  
 <span data-ttu-id="8effa-105">若要指出两个活动相关，需要知道它们的名称及其对应的内存中 ActivityID，以便调用 AddRelatedActivity。</span><span class="sxs-lookup"><span data-stu-id="8effa-105">To indicate that two activities are related, you need to know both names and have the corresponding ActivityIDs in memory in order to call AddRelatedActivity.</span></span> <span data-ttu-id="8effa-106">此 API 在对应的活动记录之间创建链接。</span><span class="sxs-lookup"><span data-stu-id="8effa-106">This API creates the link between the corresponding activity records.</span></span>  
  
 <span data-ttu-id="8effa-107">在下图中，突出显示的代码行说明如何在采购订单活动实例 #123 与发货活动 #1549、#1550 和 #1551 之间建立关系。</span><span class="sxs-lookup"><span data-stu-id="8effa-107">In the following figure, the highlighted lines of code show how you make a relationship between Purchase Order activity instance #123, and Shipment activities #1549, 1550, and 1551.</span></span>  
  
 ![](../core/media/activity-relationships-example.gif "activity_relationships_example")  
  
 <span data-ttu-id="8effa-108">业务最终用户将查看显示采购订单历史记录的网页。</span><span class="sxs-lookup"><span data-stu-id="8effa-108">The business end user looks at one Web page that shows the history of a purchase order.</span></span> <span data-ttu-id="8effa-109">这可能表明，在上午 10 点</span><span class="sxs-lookup"><span data-stu-id="8effa-109">It may indicate that at 10 A.M.</span></span> <span data-ttu-id="8effa-110">其到达时、 两天后收到批准、 和页提供对实际文档的链接。</span><span class="sxs-lookup"><span data-stu-id="8effa-110">it arrives, two days later it receives approval, and the page provides a link to the actual documents.</span></span> <span data-ttu-id="8effa-111">上述代码还使该页提供能够将业务最终用户连接到对应发货网页的超链接。</span><span class="sxs-lookup"><span data-stu-id="8effa-111">Because of the code in the previous figure, the page will also provide hyperlinks that take the business end user to the corresponding shipment Web pages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8effa-112">对所有调用`AddRelatedActivity`应执行的操作之间`BeginActivity`和`EndActivity`。</span><span class="sxs-lookup"><span data-stu-id="8effa-112">All calls to `AddRelatedActivity` should happen between `BeginActivity` and `EndActivity`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8effa-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8effa-113">See Also</span></span>  
  
 <span data-ttu-id="8effa-114">[活动延续](../core/activity-continuation.md) </span><span class="sxs-lookup"><span data-stu-id="8effa-114">[Activity Continuation](../core/activity-continuation.md) </span></span>  
 <span data-ttu-id="8effa-115">[BAM 动态基础结构](../core/bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="8effa-115">[BAM Dynamic Infrastructure](../core/bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="8effa-116">[BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md) </span><span class="sxs-lookup"><span data-stu-id="8effa-116">[BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md) </span></span>  
 [<span data-ttu-id="8effa-117">BAM API 从 Orchestration 表达式 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="8effa-117">BAM API from an Orchestration Expression (BizTalk Server Sample)</span></span>](../core/bam-api-from-an-orchestration-expression-biztalk-server-sample.md)