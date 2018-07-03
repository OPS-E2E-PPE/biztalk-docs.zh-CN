---
title: 挂起的消息包括在数据库限制阈值中的消息计数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9eb708bb-6d6d-4494-8b8d-67aa44800a20
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6aa3f26d8456836700f0e855329eaa8178f49df4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007070"
---
# <a name="suspended-messages-are-included-in-the-message-count-in-database-throttling-threshold"></a><span data-ttu-id="a1fd5-102">挂起消息包括在数据库中的消息数阻止阈值</span><span class="sxs-lookup"><span data-stu-id="a1fd5-102">Suspended Messages are Included in the Message Count in Database Throttling Threshold</span></span>
<span data-ttu-id="a1fd5-103">默认情况下主机**DB 中的消息数**阻止阈值设置为 50000，会触发在下列情况下的在触发阻止条件的值：</span><span class="sxs-lookup"><span data-stu-id="a1fd5-103">By default the host **Message count in DB** throttling threshold is set to a value of 50,000, which will trigger a throttling condition under the following circumstances:</span></span>  
  
- <span data-ttu-id="a1fd5-104">主机实例发布到订阅主机的工作、状态和已挂起队列的消息总数超过 50,000。</span><span class="sxs-lookup"><span data-stu-id="a1fd5-104">The total number of messages published by the host instance to the work, state, and suspended queues of the subscribing hosts exceeds 50,000.</span></span>  
  
- <span data-ttu-id="a1fd5-105">后台处理表或跟踪表中的消息数超过 500,000 条消息。</span><span class="sxs-lookup"><span data-stu-id="a1fd5-105">The number of messages in the spool table or the tracking tables exceeds 500,000 messages.</span></span>  
  
  <span data-ttu-id="a1fd5-106">由于挂起的消息包括在**DB 中的消息数**计算，即使 BizTalk 服务器很低，会出现发布的消息或没有负载的限制。</span><span class="sxs-lookup"><span data-stu-id="a1fd5-106">Since suspended messages are included in the **Message count in DB** calculation, throttling of message publishing can occur even if the BizTalk server is experiencing low or no load.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="a1fd5-107">建议</span><span class="sxs-lookup"><span data-stu-id="a1fd5-107">Recommendations</span></span>  
  
-   <span data-ttu-id="a1fd5-108">如果你希望你可能有大量挂起消息，请考虑增加的默认值为**DB 中的消息数**考虑到包含 SQL server 的空间要求的阈值BizTalk 数据库。</span><span class="sxs-lookup"><span data-stu-id="a1fd5-108">If you anticipate that you may have a large number of suspended messages, consider increasing the default value for the **Message count in DB** threshold taking into consideration the space requirements of the SQL server that contains the BizTalk databases.</span></span> <span data-ttu-id="a1fd5-109">还要考虑增加**后台乘数**并**跟踪数据乘数**值，以允许后台处理表中的更多的积压。</span><span class="sxs-lookup"><span data-stu-id="a1fd5-109">Also consider increasing the **Spool multiplier** and **Tracking data multiplier** values to allow additional backlog in the Spool table.</span></span>  
  
     <span data-ttu-id="a1fd5-110">有关这些值的详细信息，请参阅[如何修改资源基于阻止设置](../core/how-to-modify-resource-based-throttling-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="a1fd5-110">For more information about these values, see [How to Modify Resource Based Throttling Settings](../core/how-to-modify-resource-based-throttling-settings.md).</span></span>  
  
-   <span data-ttu-id="a1fd5-111">使用**消息发布阻止状态**与关联的性能监视器计数器**biztalk: Messageagent**性能对象类别来测量当前阻止状态。</span><span class="sxs-lookup"><span data-stu-id="a1fd5-111">Use the **Message publishing throttling state** Performance Monitor counter associated with **BizTalk:MessageAgent** performance object category to measure the current throttling state.</span></span> <span data-ttu-id="a1fd5-112">如果此计数器返回的值为 6，请检查挂起实例，根据需要终止或恢复挂起实例。</span><span class="sxs-lookup"><span data-stu-id="a1fd5-112">If this counter returns a value of 6, then check for suspended instances and terminate or resume suspended instances as needed.</span></span>  
  
     <span data-ttu-id="a1fd5-113">有关主机阻止性能计数器的详细信息，请参阅[主机阻止性能计数器](../core/host-throttling-performance-counters.md)。</span><span class="sxs-lookup"><span data-stu-id="a1fd5-113">For more information about the host throttling performance counters, see [Host Throttling Performance Counters](../core/host-throttling-performance-counters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1fd5-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1fd5-114">See Also</span></span>  
 [<span data-ttu-id="a1fd5-115">限制设计建议</span><span class="sxs-lookup"><span data-stu-id="a1fd5-115">Throttling Design Recommendations</span></span>](../core/throttling-design-recommendations.md)