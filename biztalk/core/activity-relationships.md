---
title: 活动关系 |Microsoft Docs
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
ms.openlocfilehash: a3266501df57b9350e70369327fdc3142b3019d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361660"
---
# <a name="activity-relationships"></a><span data-ttu-id="1f632-102">活动关系</span><span class="sxs-lookup"><span data-stu-id="1f632-102">Activity Relationships</span></span>
<span data-ttu-id="1f632-103">当活动与一个或多个其他活动时，存在一个活动关系。</span><span class="sxs-lookup"><span data-stu-id="1f632-103">An activity relationship exists when an activity relates to one or more other activities.</span></span> <span data-ttu-id="1f632-104">此示例多个发货活动与单个采购订单活动或一个发货活动包含两个采购订单活动中的项。</span><span class="sxs-lookup"><span data-stu-id="1f632-104">An example of this is having multiple Shipment activities related to a single Purchase Order activity, or one Shipment activity containing items from two Purchase Order activities.</span></span>  
  
 <span data-ttu-id="1f632-105">若要指示两个活动将相关，需要知道它们的名称，并在内存中具有相应的 Activityid，以便调用 AddRelatedActivity。</span><span class="sxs-lookup"><span data-stu-id="1f632-105">To indicate that two activities are related, you need to know both names and have the corresponding ActivityIDs in memory in order to call AddRelatedActivity.</span></span> <span data-ttu-id="1f632-106">此 API 创建相应的活动记录之间的链接。</span><span class="sxs-lookup"><span data-stu-id="1f632-106">This API creates the link between the corresponding activity records.</span></span>  
  
 <span data-ttu-id="1f632-107">下图中突出显示的代码行说明如何在采购订单活动实例 #123 与发货活动 # 1549年、 # 1550年和 1551年之间建立关系。</span><span class="sxs-lookup"><span data-stu-id="1f632-107">In the following figure, the highlighted lines of code show how you make a relationship between Purchase Order activity instance #123, and Shipment activities #1549, 1550, and 1551.</span></span>  
  
 <span data-ttu-id="1f632-108">![](../core/media/activity-relationships-example.gif "activity_relationships_example")</span><span class="sxs-lookup"><span data-stu-id="1f632-108">![](../core/media/activity-relationships-example.gif "activity_relationships_example")</span></span>  
  
 <span data-ttu-id="1f632-109">业务最终用户将查看显示采购订单的历史记录的一个网页。</span><span class="sxs-lookup"><span data-stu-id="1f632-109">The business end user looks at one Web page that shows the history of a purchase order.</span></span> <span data-ttu-id="1f632-110">它可能指示在上午 10 点</span><span class="sxs-lookup"><span data-stu-id="1f632-110">It may indicate that at 10 A.M.</span></span> <span data-ttu-id="1f632-111">到达、 两天后，它被审批，和的页提供了指向实际文档的链接。</span><span class="sxs-lookup"><span data-stu-id="1f632-111">it arrives, two days later it receives approval, and the page provides a link to the actual documents.</span></span> <span data-ttu-id="1f632-112">由于在上图中的代码，该页面还将提供将业务最终用户转到对应发货网页的超链接。</span><span class="sxs-lookup"><span data-stu-id="1f632-112">Because of the code in the previous figure, the page will also provide hyperlinks that take the business end user to the corresponding shipment Web pages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f632-113">所有调用的`AddRelatedActivity`应执行的操作之间`BeginActivity`和`EndActivity`。</span><span class="sxs-lookup"><span data-stu-id="1f632-113">All calls to `AddRelatedActivity` should happen between `BeginActivity` and `EndActivity`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f632-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f632-114">See Also</span></span>  
  
 <span data-ttu-id="1f632-115">[活动继续符](../core/activity-continuation.md) </span><span class="sxs-lookup"><span data-stu-id="1f632-115">[Activity Continuation](../core/activity-continuation.md) </span></span>  
 <span data-ttu-id="1f632-116">[BAM 动态基础结构](../core/bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="1f632-116">[BAM Dynamic Infrastructure](../core/bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="1f632-117">[BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md) </span><span class="sxs-lookup"><span data-stu-id="1f632-117">[BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md) </span></span>  
 [<span data-ttu-id="1f632-118">业务流程表达式中的 BAM API（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="1f632-118">BAM API from an Orchestration Expression (BizTalk Server Sample)</span></span>](../core/bam-api-from-an-orchestration-expression-biztalk-server-sample.md)