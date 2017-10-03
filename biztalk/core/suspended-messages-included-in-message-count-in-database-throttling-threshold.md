---
title: "挂起的消息都包含在数据库限制阈值中的消息计数 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9eb708bb-6d6d-4494-8b8d-67aa44800a20
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f8ea0643ccf2d6206ba86bc56b5dd54c0d51115
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="suspended-messages-are-included-in-the-message-count-in-database-throttling-threshold"></a><span data-ttu-id="b76d0-102">挂起消息包括在数据库中的消息数阻止阈值</span><span class="sxs-lookup"><span data-stu-id="b76d0-102">Suspended Messages are Included in the Message Count in Database Throttling Threshold</span></span>
<span data-ttu-id="b76d0-103">默认情况下，主机**消息在数据库中的计数**限制阈值设置为值为 50000，就会触发在下列情况下的限制条件：</span><span class="sxs-lookup"><span data-stu-id="b76d0-103">By default the host **Message count in DB** throttling threshold is set to a value of 50,000, which will trigger a throttling condition under the following circumstances:</span></span>  
  
-   <span data-ttu-id="b76d0-104">主机实例发布到订阅主机的工作、状态和已挂起队列的消息总数超过 50,000。</span><span class="sxs-lookup"><span data-stu-id="b76d0-104">The total number of messages published by the host instance to the work, state, and suspended queues of the subscribing hosts exceeds 50,000.</span></span>  
  
-   <span data-ttu-id="b76d0-105">假脱机表或跟踪表中的消息数超过 500,000 消息。</span><span class="sxs-lookup"><span data-stu-id="b76d0-105">The number of messages in the spool table or the tracking tables exceeds 500,000 messages.</span></span>  
  
 <span data-ttu-id="b76d0-106">因为挂起的消息都将纳入**消息在数据库中的计数**计算，即使 BizTalk server 遇到低，会发生发布的消息或无负载的限制。</span><span class="sxs-lookup"><span data-stu-id="b76d0-106">Since suspended messages are included in the **Message count in DB** calculation, throttling of message publishing can occur even if the BizTalk server is experiencing low or no load.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="b76d0-107">建议</span><span class="sxs-lookup"><span data-stu-id="b76d0-107">Recommendations</span></span>  
  
-   <span data-ttu-id="b76d0-108">如果你希望你可能有大量的挂起的消息，请考虑增加的默认值为**消息在数据库中的计数**考虑到包含的 SQL 服务器的空间要求的阈值BizTalk 数据库。</span><span class="sxs-lookup"><span data-stu-id="b76d0-108">If you anticipate that you may have a large number of suspended messages, consider increasing the default value for the **Message count in DB** threshold taking into consideration the space requirements of the SQL server that contains the BizTalk databases.</span></span> <span data-ttu-id="b76d0-109">此外可以考虑提高**假脱机乘数**和**跟踪数据乘数**值，以允许在假脱机表中使用其他积压工作。</span><span class="sxs-lookup"><span data-stu-id="b76d0-109">Also consider increasing the **Spool multiplier** and **Tracking data multiplier** values to allow additional backlog in the Spool table.</span></span>  
  
     <span data-ttu-id="b76d0-110">有关这些值的详细信息，请参阅[如何修改资源基于限制设置](../core/how-to-modify-resource-based-throttling-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="b76d0-110">For more information about these values, see [How to Modify Resource Based Throttling Settings](../core/how-to-modify-resource-based-throttling-settings.md).</span></span>  
  
-   <span data-ttu-id="b76d0-111">使用**限制状态消息发布**与关联的性能监视器计数器**BizTalk:MessageAgent**性能对象类别来测量当前限制状态。</span><span class="sxs-lookup"><span data-stu-id="b76d0-111">Use the **Message publishing throttling state** Performance Monitor counter associated with **BizTalk:MessageAgent** performance object category to measure the current throttling state.</span></span> <span data-ttu-id="b76d0-112">如果此计数器返回的值为 6，请检查挂起实例，根据需要终止或恢复挂起实例。</span><span class="sxs-lookup"><span data-stu-id="b76d0-112">If this counter returns a value of 6, then check for suspended instances and terminate or resume suspended instances as needed.</span></span>  
  
     <span data-ttu-id="b76d0-113">有关主机限制性能计数器的详细信息，请参阅[主机限制性能计数器](../core/host-throttling-performance-counters.md)。</span><span class="sxs-lookup"><span data-stu-id="b76d0-113">For more information about the host throttling performance counters, see [Host Throttling Performance Counters](../core/host-throttling-performance-counters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b76d0-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b76d0-114">See Also</span></span>  
 [<span data-ttu-id="b76d0-115">限制的设计建议</span><span class="sxs-lookup"><span data-stu-id="b76d0-115">Throttling Design Recommendations</span></span>](../core/throttling-design-recommendations.md)