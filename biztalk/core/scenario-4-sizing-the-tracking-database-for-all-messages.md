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
# <a name="scenario-4-sizing-the-tracking-database-for-all-messages"></a><span data-ttu-id="f48f0-102">方案 4： 调整跟踪数据库的所有消息</span><span class="sxs-lookup"><span data-stu-id="f48f0-102">Scenario 4: Sizing the Tracking Database for all Messages</span></span>
<span data-ttu-id="f48f0-103">如果 Microsoft® BizTalk Server® 2004 实施中同时出现以上三种消息方案，则需计算所有方案结果的总和以确定 BizTalk 跟踪数据库的大小。</span><span class="sxs-lookup"><span data-stu-id="f48f0-103">If you had all three message scenarios present in a Microsoft® BizTalk Server® 2004 implementation, you would need to add together all of the scenario results to determine the size of the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="f48f0-104">根据如上所示的示例：</span><span class="sxs-lookup"><span data-stu-id="f48f0-104">From the examples shown above:</span></span>  
  
|<span data-ttu-id="f48f0-105">应用场景</span><span class="sxs-lookup"><span data-stu-id="f48f0-105">Scenario</span></span>|<span data-ttu-id="f48f0-106">每年所需的空间 (GB)</span><span class="sxs-lookup"><span data-stu-id="f48f0-106">Space required, per year, in GB</span></span>|  
|--------------|-------------------------------------|  
|<span data-ttu-id="f48f0-107">简单消息</span><span class="sxs-lookup"><span data-stu-id="f48f0-107">Simple messages</span></span>|<span data-ttu-id="f48f0-108">4.78</span><span class="sxs-lookup"><span data-stu-id="f48f0-108">4.78</span></span>|  
|<span data-ttu-id="f48f0-109">业务流程中的消息</span><span class="sxs-lookup"><span data-stu-id="f48f0-109">Messages in orchestrations</span></span>|<span data-ttu-id="f48f0-110">7.18</span><span class="sxs-lookup"><span data-stu-id="f48f0-110">7.18</span></span>|  
|<span data-ttu-id="f48f0-111">业务流程中发送给分发列表的消息</span><span class="sxs-lookup"><span data-stu-id="f48f0-111">Messages in orchestrations sent out to distribution lists</span></span>|<span data-ttu-id="f48f0-112">10.8</span><span class="sxs-lookup"><span data-stu-id="f48f0-112">10.8</span></span>|  
|<span data-ttu-id="f48f0-113">**总计**</span><span class="sxs-lookup"><span data-stu-id="f48f0-113">**Total**</span></span>|<span data-ttu-id="f48f0-114">22.04</span><span class="sxs-lookup"><span data-stu-id="f48f0-114">22.04</span></span>|  
  
 <span data-ttu-id="f48f0-115">此外，如果打开对以上三种方案的消息正文跟踪，我们将得到以下结果：</span><span class="sxs-lookup"><span data-stu-id="f48f0-115">In addition, if we turn on message body tracking for all three scenarios, we would get the following results:</span></span>  
  
|<span data-ttu-id="f48f0-116">应用场景</span><span class="sxs-lookup"><span data-stu-id="f48f0-116">Scenario</span></span>|<span data-ttu-id="f48f0-117">每年所需的空间 (GB)</span><span class="sxs-lookup"><span data-stu-id="f48f0-117">Space required, per year, in GB</span></span>|  
|--------------|-------------------------------------|  
|<span data-ttu-id="f48f0-118">简单消息</span><span class="sxs-lookup"><span data-stu-id="f48f0-118">Simple messages</span></span>|<span data-ttu-id="f48f0-119">50.1</span><span class="sxs-lookup"><span data-stu-id="f48f0-119">50.1</span></span>|  
|<span data-ttu-id="f48f0-120">业务流程中的消息</span><span class="sxs-lookup"><span data-stu-id="f48f0-120">Messages in orchestrations</span></span>|<span data-ttu-id="f48f0-121">50.1</span><span class="sxs-lookup"><span data-stu-id="f48f0-121">50.1</span></span>|  
|<span data-ttu-id="f48f0-122">业务流程中发送给分发列表的消息</span><span class="sxs-lookup"><span data-stu-id="f48f0-122">Messages in orchestrations sent out to distribution lists</span></span>|<span data-ttu-id="f48f0-123">83.45</span><span class="sxs-lookup"><span data-stu-id="f48f0-123">83.45</span></span>|  
|<span data-ttu-id="f48f0-124">**总计**</span><span class="sxs-lookup"><span data-stu-id="f48f0-124">**Total**</span></span>|<span data-ttu-id="f48f0-125">183.65</span><span class="sxs-lookup"><span data-stu-id="f48f0-125">183.65</span></span>|  
  
 <span data-ttu-id="f48f0-126">至此，我们得出 BizTalk 跟踪数据库的年增长总计为 205.69 GB。</span><span class="sxs-lookup"><span data-stu-id="f48f0-126">This would give you a grand total of 205.69 GB per year growth on the BizTalk Tracking database.</span></span> <span data-ttu-id="f48f0-127">此表不包括任何意外情况。</span><span class="sxs-lookup"><span data-stu-id="f48f0-127">This figure does not include any contingency.</span></span> <span data-ttu-id="f48f0-128">如果您决定为意外情况增加 10% 的总计空间（建议您这样做），那么，您应计划 BizTalk 跟踪数据库的年增长为 227.94 GB。</span><span class="sxs-lookup"><span data-stu-id="f48f0-128">If you decided to add a contingency of 10 percent to this total, as is recommended, then you should plan on the BizTalk Tracking database growing 227.94 GB per year.</span></span> <span data-ttu-id="f48f0-129">另外，应考虑由于 SQL 索引、 存储等的开销。如有可能在测试中运行的测试方案后，应该根据放大因子。</span><span class="sxs-lookup"><span data-stu-id="f48f0-129">On top of this, you should consider the overhead due to SQL indices, storage, etc. You should base your multiplying factor after running the test scenarios in test if possible.</span></span>  
  
## <a name="other-factors-affecting-biztalk-tracking-database-size"></a><span data-ttu-id="f48f0-130">影响 BizTalk 跟踪数据库大小的其他因素</span><span class="sxs-lookup"><span data-stu-id="f48f0-130">Other factors affecting BizTalk Tracking database size</span></span>  
 <span data-ttu-id="f48f0-131">还有其他一些因素也会影响 BizTalk 跟踪数据库的大小，例如业务流程内所使用的形状。</span><span class="sxs-lookup"><span data-stu-id="f48f0-131">There are other items, such as the shapes used within an orchestration that also affect the size of the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="f48f0-132">如果已打开业务流程调试器选项（默认情况下为打开状态），则业务流程中每个形状的状态将保存到 BizTalk 跟踪数据库中。</span><span class="sxs-lookup"><span data-stu-id="f48f0-132">If the orchestration debugger option is turned on, which it is by default, the status of each shape in the orchestration is saved to the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="f48f0-133">用于确定跟踪形状状态所需的空间大小的公式如下所示：</span><span class="sxs-lookup"><span data-stu-id="f48f0-133">The formula to determine the size needed to track shape status is:</span></span>  
  
```  
[(# of object shapes ] * 76 bytes  
```  
  
 <span data-ttu-id="f48f0-134">例如，在下图中，您将使用以下公式来确定 BizTalk 跟踪大小：</span><span class="sxs-lookup"><span data-stu-id="f48f0-134">For example, in the following figure, you would use the following formula to determine the BizTalk Tracking size:</span></span>  
  
```  
((4) * 76 bytes = 304 bytes  
```  
  
 <span data-ttu-id="f48f0-135">![业务流程示例](../core/media/sample-orchestration.gif "Sample_orchestration")</span><span class="sxs-lookup"><span data-stu-id="f48f0-135">![Orchestration Example](../core/media/sample-orchestration.gif "Sample_orchestration")</span></span>  
  
 <span data-ttu-id="f48f0-136">如果假定此业务流程处理 350 万条消息，则跟踪此业务流程所需的额外空间为：</span><span class="sxs-lookup"><span data-stu-id="f48f0-136">If we assume that this orchestration processes 3.5 million messages, the additional space needed to track this orchestration would be:</span></span>  
  
```  
304 bytes * 3,500,000/1024/1024 = 1015 MB ~ 0.99 GB.  
```  
  
 <span data-ttu-id="f48f0-137">您需要考虑将业务流程调试器设置为“开启”的每个业务流程，以获取 BizTalk 跟踪数据库的近似大小。</span><span class="sxs-lookup"><span data-stu-id="f48f0-137">You will need to account for each orchestration that has the orchestration debugger set to "on" to get an approximate size for the BizTalk Tracking database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f48f0-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f48f0-138">See Also</span></span>  
 <span data-ttu-id="f48f0-139">[使用消息变量来调整跟踪数据库的大小](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="f48f0-139">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="f48f0-140">[大小调整跟踪数据库来跟踪消息正文](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="f48f0-140">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="f48f0-141">[方案 1： 调整跟踪数据库的简单 BizTalk 消息](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="f48f0-141">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="f48f0-142">[方案 2： 调整跟踪数据库的业务流程中的消息](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="f48f0-142">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="f48f0-143">方案 3： 调整跟踪数据库的消息发送到通讯组列表</span><span class="sxs-lookup"><span data-stu-id="f48f0-143">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)