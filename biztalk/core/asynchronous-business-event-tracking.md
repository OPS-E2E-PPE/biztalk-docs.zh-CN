---
title: "异步业务事件跟踪 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance, BAM
- events, tracking [BAM]
- BAM, event tracking
- BAM, performance
ms.assetid: 6d51fadf-b329-4536-9618-d982d9c17882
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7191d9b0be94b4b089a91e78dd526867171c68a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="asynchronous-business-event-tracking"></a><span data-ttu-id="ec700-102">异步业务事件跟踪</span><span class="sxs-lookup"><span data-stu-id="ec700-102">Asynchronous Business Event Tracking</span></span>
<span data-ttu-id="ec700-103">异步 (使用`BufferedEventStream`)-此模型提供了显著的性能改进。</span><span class="sxs-lookup"><span data-stu-id="ec700-103">Asynchronous (using `BufferedEventStream`) - This model offers significant performance improvements.</span></span> <span data-ttu-id="ec700-104">此模型使用的 API 与同步模型相似，只是使用不同的构造函数。</span><span class="sxs-lookup"><span data-stu-id="ec700-104">This uses a similar API to the synchronous model, using only a different constructor.</span></span> <span data-ttu-id="ec700-105">BufferedEventStream 不是将数据放入主导入数据库中，而是以二进制形式将事件数据累计在内存中，然后将其作为单个表记录插入到临时数据库 (MessageBox) 中。</span><span class="sxs-lookup"><span data-stu-id="ec700-105">Instead of pushing the data into the primary import database, BufferedEventStream accumulates the event data in memory in binary form, and then inserts it as a single table record into an interim database (MessageBox).</span></span> <span data-ttu-id="ec700-106">事件总线服务读取 MessageBox 数据库中由 BizTalk 排队的数据，将其导入到主导入数据库中。</span><span class="sxs-lookup"><span data-stu-id="ec700-106">The Event Bus service reads the data queued in the MessageBox database by BizTalk and imports it into the primary import database.</span></span>  
  
 <span data-ttu-id="ec700-107">要配置 BAM 进行异步操作，事件总线服务和调用应用程序（例如业务流程主机）应该运行在不同的计算机上。</span><span class="sxs-lookup"><span data-stu-id="ec700-107">To configure BAM for asynchronous operation, the Event Bus Service and the calling application (e.g. Orchestration Host) should run on different computers.</span></span> <span data-ttu-id="ec700-108">这样，调用应用程序就可以立即清除使用其他计算机上的 CPU 处理的事件数据。</span><span class="sxs-lookup"><span data-stu-id="ec700-108">This allows the calling application to get rid of the event data immediately to be processed using the CPU on a different computer.</span></span>  
  
 <span data-ttu-id="ec700-109">这种 BAM 拓扑结构也具有事务一致性。</span><span class="sxs-lookup"><span data-stu-id="ec700-109">This BAM topology is also transaction-consistent.</span></span> <span data-ttu-id="ec700-110">您将无法获得在调用应用程序中回滚的事务的 BAM 数据，因为事件总线服务只读取 MessageBox 数据库中已提交的数据。</span><span class="sxs-lookup"><span data-stu-id="ec700-110">You will never get BAM data for transactions that rolled back in the calling application, because the Event Bus Service only reads the committed data from the MessageBox database.</span></span> <span data-ttu-id="ec700-111">已提交的事务的 BAM 数据在一段短时延迟后即可用于查询和聚合。</span><span class="sxs-lookup"><span data-stu-id="ec700-111">The BAM data for the transactions that were committed will show up for query and aggregation with small latency.</span></span>  
  
 <span data-ttu-id="ec700-112">如果出现错误，事件总线服务将重试几次、使用超时设置并执行损坏恢复逻辑等。</span><span class="sxs-lookup"><span data-stu-id="ec700-112">If errors occur, the Event Bus Service will retry a few times, use timeouts, crash recovery logic, and so on.</span></span> <span data-ttu-id="ec700-113">如果数据的格式无效，它会在特殊表中结束。</span><span class="sxs-lookup"><span data-stu-id="ec700-113">If however the data is in an invalid format, it ends up in special tables.</span></span> <span data-ttu-id="ec700-114">事件日志中会生成一个事件以指示此情况。</span><span class="sxs-lookup"><span data-stu-id="ec700-114">An event occurs in the event log to indicate this condition.</span></span> <span data-ttu-id="ec700-115">这种附加的故障点增加了系统管理难度。</span><span class="sxs-lookup"><span data-stu-id="ec700-115">This additional failure point increases the difficulty of managing the system.</span></span>  
  
 <span data-ttu-id="ec700-116">在代码中使用异步方法非常简单，只需将 DirectEventStream 替换为 BufferedEventStream，然后将连接字符串传递到构造函数中的 MessageBox，而不是传递到 BAM 主导入数据库的 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="ec700-116">Using the asynchronous approach from code is usually as simple as replacing the DirectEventStream with BufferedEventStream, and passing the connection string to the Message Box in the constructor, instead of the one for BAM Primary Import.</span></span>  
  
 <span data-ttu-id="ec700-117">要在代码中执行异步业务事件跟踪，请遵循以下准则：</span><span class="sxs-lookup"><span data-stu-id="ec700-117">Use the following guidelines regarding asynchronous business event tracking in your code:</span></span>  
  
-   <span data-ttu-id="ec700-118">当活动跨多个应用程序且向 BAM 异步发送数据时，请始终使用继续符，即使将 ActivityID 传播到了所有组件，也应该如此。</span><span class="sxs-lookup"><span data-stu-id="ec700-118">Always use continuation when the Activity spans multiple applications and you send the data asynchronously to BAM, even if you propagate the ActivityID to all components.</span></span> <span data-ttu-id="ec700-119">在这种情况下，请将唯一字符串（例如应用程序名）作为 ActivityID 的前缀，使每个应用程序中的 ActivityID 各不相同。</span><span class="sxs-lookup"><span data-stu-id="ec700-119">In this case, use a different ActivityID in each application by prefixing it with a unique string (e.g. Application Name).</span></span> <span data-ttu-id="ec700-120">这很有必要，因为来自不同应用程序的数据到达 BAM 的顺序可能是随机的，BAM 必须管理顺序颠倒的事件以确保得到正确的查询和聚合结果。</span><span class="sxs-lookup"><span data-stu-id="ec700-120">This is necessary because the data from different applications might arrive to BAM in random order, and BAM has to manage the out-of-order events to ensure correct Query and Aggregation results.</span></span>  
  
-   <span data-ttu-id="ec700-121">事件监视的常规方法（例如 COM+ 松散耦合事件或 WMI 事件）不适用于 BAM，因为这些事件数据与事务无关。</span><span class="sxs-lookup"><span data-stu-id="ec700-121">The usual methods of event monitoring (e.g. COM+ Loosely Coupled Events or WMI Events) are not applicable for BAM because the event data is independent of the transaction.</span></span> <span data-ttu-id="ec700-122">例如，如果只有一个价值 $1000 的传入采购订单，但尝试将其保存到数据库时失败了 10 次，如果采用常规的事件监视方法，会使得该事件看起来好像收到了 10 张采购订单，总计 $10,000。</span><span class="sxs-lookup"><span data-stu-id="ec700-122">For example, it may look like you received 10 purchase orders for a total of $10,000 while there was only one incoming purchase order for $1000, but the attempt to save it to the database failed 10 times.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec700-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec700-123">See Also</span></span>  

 [<span data-ttu-id="ec700-124">同步业务事件跟踪</span><span class="sxs-lookup"><span data-stu-id="ec700-124">Synchronous Business Event Tracking</span></span>](../core/synchronous-business-event-tracking.md)