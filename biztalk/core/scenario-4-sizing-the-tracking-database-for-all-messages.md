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
# <a name="scenario-4-sizing-the-tracking-database-for-all-messages"></a><span data-ttu-id="44803-102">应用场景 4：为所有消息调整跟踪数据库的大小</span><span class="sxs-lookup"><span data-stu-id="44803-102">Scenario 4: Sizing the Tracking Database for all Messages</span></span>
<span data-ttu-id="44803-103">如果你有 Microsoft® BizTalk Server® 2004年实施中存在的所有三种消息方案，需要将加在一起的所有方案结果来确定 BizTalk 跟踪数据库的大小。</span><span class="sxs-lookup"><span data-stu-id="44803-103">If you had all three message scenarios present in a Microsoft® BizTalk Server® 2004 implementation, you would need to add together all of the scenario results to determine the size of the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="44803-104">从上面所示的示例：</span><span class="sxs-lookup"><span data-stu-id="44803-104">From the examples shown above:</span></span>  
  
|<span data-ttu-id="44803-105">应用场景</span><span class="sxs-lookup"><span data-stu-id="44803-105">Scenario</span></span>|<span data-ttu-id="44803-106">每年，以 gb 为单位所需的空间</span><span class="sxs-lookup"><span data-stu-id="44803-106">Space required, per year, in GB</span></span>|  
|--------------|-------------------------------------|  
|<span data-ttu-id="44803-107">简单消息</span><span class="sxs-lookup"><span data-stu-id="44803-107">Simple messages</span></span>|<span data-ttu-id="44803-108">4.78</span><span class="sxs-lookup"><span data-stu-id="44803-108">4.78</span></span>|  
|<span data-ttu-id="44803-109">业务流程中消息</span><span class="sxs-lookup"><span data-stu-id="44803-109">Messages in orchestrations</span></span>|<span data-ttu-id="44803-110">7.18</span><span class="sxs-lookup"><span data-stu-id="44803-110">7.18</span></span>|  
|<span data-ttu-id="44803-111">在业务流程发送到分发列表中的消息</span><span class="sxs-lookup"><span data-stu-id="44803-111">Messages in orchestrations sent out to distribution lists</span></span>|<span data-ttu-id="44803-112">10.8</span><span class="sxs-lookup"><span data-stu-id="44803-112">10.8</span></span>|  
|<span data-ttu-id="44803-113">**总计**</span><span class="sxs-lookup"><span data-stu-id="44803-113">**Total**</span></span>|<span data-ttu-id="44803-114">22.04</span><span class="sxs-lookup"><span data-stu-id="44803-114">22.04</span></span>|  
  
 <span data-ttu-id="44803-115">此外，如果我们打开消息正文跟踪所有三个方案，我们会得到以下结果：</span><span class="sxs-lookup"><span data-stu-id="44803-115">In addition, if we turn on message body tracking for all three scenarios, we would get the following results:</span></span>  
  
|<span data-ttu-id="44803-116">应用场景</span><span class="sxs-lookup"><span data-stu-id="44803-116">Scenario</span></span>|<span data-ttu-id="44803-117">每年，以 gb 为单位所需的空间</span><span class="sxs-lookup"><span data-stu-id="44803-117">Space required, per year, in GB</span></span>|  
|--------------|-------------------------------------|  
|<span data-ttu-id="44803-118">简单消息</span><span class="sxs-lookup"><span data-stu-id="44803-118">Simple messages</span></span>|<span data-ttu-id="44803-119">50.1</span><span class="sxs-lookup"><span data-stu-id="44803-119">50.1</span></span>|  
|<span data-ttu-id="44803-120">业务流程中消息</span><span class="sxs-lookup"><span data-stu-id="44803-120">Messages in orchestrations</span></span>|<span data-ttu-id="44803-121">50.1</span><span class="sxs-lookup"><span data-stu-id="44803-121">50.1</span></span>|  
|<span data-ttu-id="44803-122">在业务流程发送到分发列表中的消息</span><span class="sxs-lookup"><span data-stu-id="44803-122">Messages in orchestrations sent out to distribution lists</span></span>|<span data-ttu-id="44803-123">83.45</span><span class="sxs-lookup"><span data-stu-id="44803-123">83.45</span></span>|  
|<span data-ttu-id="44803-124">**总计**</span><span class="sxs-lookup"><span data-stu-id="44803-124">**Total**</span></span>|<span data-ttu-id="44803-125">183.65</span><span class="sxs-lookup"><span data-stu-id="44803-125">183.65</span></span>|  
  
 <span data-ttu-id="44803-126">这将为您提供为 205.69 GB 年增长总计对 BizTalk 跟踪数据库。</span><span class="sxs-lookup"><span data-stu-id="44803-126">This would give you a grand total of 205.69 GB per year growth on the BizTalk Tracking database.</span></span> <span data-ttu-id="44803-127">此图不包括任何意外情况。</span><span class="sxs-lookup"><span data-stu-id="44803-127">This figure does not include any contingency.</span></span> <span data-ttu-id="44803-128">如果您决定将 10%的应急添加到此总数建议，然后应计划 BizTalk 跟踪数据库每年增长 227.94 GB。</span><span class="sxs-lookup"><span data-stu-id="44803-128">If you decided to add a contingency of 10 percent to this total, as is recommended, then you should plan on the BizTalk Tracking database growing 227.94 GB per year.</span></span> <span data-ttu-id="44803-129">在此之上，则应考虑由于 SQL 索引、 存储等的开销。如有可能在测试中运行的测试方案后，应使乘法因子。</span><span class="sxs-lookup"><span data-stu-id="44803-129">On top of this, you should consider the overhead due to SQL indices, storage, etc. You should base your multiplying factor after running the test scenarios in test if possible.</span></span>  
  
## <a name="other-factors-affecting-biztalk-tracking-database-size"></a><span data-ttu-id="44803-130">其他因素影响 BizTalk 跟踪数据库大小</span><span class="sxs-lookup"><span data-stu-id="44803-130">Other factors affecting BizTalk Tracking database size</span></span>  
 <span data-ttu-id="44803-131">有其他项，例如业务流程中所使用的形状，也会影响 BizTalk 跟踪数据库的大小。</span><span class="sxs-lookup"><span data-stu-id="44803-131">There are other items, such as the shapes used within an orchestration that also affect the size of the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="44803-132">如果业务流程调试器选项开启，它默认情况下，即在业务流程中每个形状的状态将保存到 BizTalk 跟踪数据库。</span><span class="sxs-lookup"><span data-stu-id="44803-132">If the orchestration debugger option is turned on, which it is by default, the status of each shape in the orchestration is saved to the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="44803-133">若要确定跟踪形状状态所需大小的公式为：</span><span class="sxs-lookup"><span data-stu-id="44803-133">The formula to determine the size needed to track shape status is:</span></span>  
  
```  
[(# of object shapes ] * 76 bytes  
```  
  
 <span data-ttu-id="44803-134">例如，在下图中，您将使用下面的公式来确定 BizTalk 跟踪大小：</span><span class="sxs-lookup"><span data-stu-id="44803-134">For example, in the following figure, you would use the following formula to determine the BizTalk Tracking size:</span></span>  
  
```  
((4) * 76 bytes = 304 bytes  
```  
  
 <span data-ttu-id="44803-135">![业务流程示例](../core/media/sample-orchestration.gif "Sample_orchestration")</span><span class="sxs-lookup"><span data-stu-id="44803-135">![Orchestration Example](../core/media/sample-orchestration.gif "Sample_orchestration")</span></span>  
  
 <span data-ttu-id="44803-136">如果我们假定此业务流程处理 350 万条消息，以跟踪此业务流程所需的额外空间为：</span><span class="sxs-lookup"><span data-stu-id="44803-136">If we assume that this orchestration processes 3.5 million messages, the additional space needed to track this orchestration would be:</span></span>  
  
```  
304 bytes * 3,500,000/1024/1024 = 1015 MB ~ 0.99 GB.  
```  
  
 <span data-ttu-id="44803-137">您需要考虑每个业务流程具有业务流程调试器设置为"打开"以获取 BizTalk 跟踪数据库的近似大小。</span><span class="sxs-lookup"><span data-stu-id="44803-137">You will need to account for each orchestration that has the orchestration debugger set to "on" to get an approximate size for the BizTalk Tracking database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44803-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="44803-138">See Also</span></span>  
 <span data-ttu-id="44803-139">[使用消息变量调整跟踪数据库的大小](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="44803-139">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="44803-140">[调整跟踪数据库来跟踪消息正文大小](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="44803-140">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="44803-141">[方案 1：为简单 BizTalk 消息调整跟踪数据库的大小](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="44803-141">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="44803-142">[方案 2：为业务流程中消息调整跟踪数据库的大小](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="44803-142">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="44803-143">方案 3:为发送到分发列表的消息调整跟踪数据库的大小</span><span class="sxs-lookup"><span data-stu-id="44803-143">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)