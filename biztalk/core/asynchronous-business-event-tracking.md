---
title: 异步业务事件跟踪 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, BAM
- events, tracking [BAM]
- BAM, event tracking
- BAM, performance
ms.assetid: 6d51fadf-b329-4536-9618-d982d9c17882
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: daff76641e9c70cc2860aa1571b86e74d664f66e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358805"
---
# <a name="asynchronous-business-event-tracking"></a><span data-ttu-id="d8739-102">异步业务事件跟踪</span><span class="sxs-lookup"><span data-stu-id="d8739-102">Asynchronous Business Event Tracking</span></span>
<span data-ttu-id="d8739-103">异步 (使用`BufferedEventStream`)-此模型提供了显著的性能改进。</span><span class="sxs-lookup"><span data-stu-id="d8739-103">Asynchronous (using `BufferedEventStream`) - This model offers significant performance improvements.</span></span> <span data-ttu-id="d8739-104">这将使用类似的 API 与同步模型中，使用其他构造函数。</span><span class="sxs-lookup"><span data-stu-id="d8739-104">This uses a similar API to the synchronous model, using only a different constructor.</span></span> <span data-ttu-id="d8739-105">而不是将数据推送到主导入数据库，BufferedEventStream 累积以二进制形式的内存中的事件数据，然后将其作为单个表记录插入到临时数据库 (MessageBox)。</span><span class="sxs-lookup"><span data-stu-id="d8739-105">Instead of pushing the data into the primary import database, BufferedEventStream accumulates the event data in memory in binary form, and then inserts it as a single table record into an interim database (MessageBox).</span></span> <span data-ttu-id="d8739-106">事件总线服务读取数据通过 BizTalk MessageBox 数据库中排队，并将其导入到主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="d8739-106">The Event Bus service reads the data queued in the MessageBox database by BizTalk and imports it into the primary import database.</span></span>  
  
 <span data-ttu-id="d8739-107">要配置 BAM 进行异步操作，事件总线服务和调用应用程序 （例如业务流程主机） 应该运行在不同计算机上。</span><span class="sxs-lookup"><span data-stu-id="d8739-107">To configure BAM for asynchronous operation, the Event Bus Service and the calling application (e.g. Orchestration Host) should run on different computers.</span></span> <span data-ttu-id="d8739-108">这样调用应用程序中，若要消除立即要使用不同的计算机上的 CPU 处理的事件数据。</span><span class="sxs-lookup"><span data-stu-id="d8739-108">This allows the calling application to get rid of the event data immediately to be processed using the CPU on a different computer.</span></span>  
  
 <span data-ttu-id="d8739-109">这种 BAM 拓扑也是事务一致的。</span><span class="sxs-lookup"><span data-stu-id="d8739-109">This BAM topology is also transaction-consistent.</span></span> <span data-ttu-id="d8739-110">因为事件总线服务只读取已提交的数据从 MessageBox 数据库，您将无法获得调用应用程序中回滚的事务的 BAM 数据。</span><span class="sxs-lookup"><span data-stu-id="d8739-110">You will never get BAM data for transactions that rolled back in the calling application, because the Event Bus Service only reads the committed data from the MessageBox database.</span></span> <span data-ttu-id="d8739-111">已提交的事务的 BAM 数据即可用于查询和聚合与较小的延迟。</span><span class="sxs-lookup"><span data-stu-id="d8739-111">The BAM data for the transactions that were committed will show up for query and aggregation with small latency.</span></span>  
  
 <span data-ttu-id="d8739-112">如果出现错误，事件总线服务将重试几次、 使用超时设置、 损坏恢复逻辑等。</span><span class="sxs-lookup"><span data-stu-id="d8739-112">If errors occur, the Event Bus Service will retry a few times, use timeouts, crash recovery logic, and so on.</span></span> <span data-ttu-id="d8739-113">如果但是数据格式无效，它最终会接受在特殊表中。</span><span class="sxs-lookup"><span data-stu-id="d8739-113">If however the data is in an invalid format, it ends up in special tables.</span></span> <span data-ttu-id="d8739-114">事件日志，以指示这种情况中发生的事件。</span><span class="sxs-lookup"><span data-stu-id="d8739-114">An event occurs in the event log to indicate this condition.</span></span> <span data-ttu-id="d8739-115">此附加的故障点增加了系统管理难度。</span><span class="sxs-lookup"><span data-stu-id="d8739-115">This additional failure point increases the difficulty of managing the system.</span></span>  
  
 <span data-ttu-id="d8739-116">使用代码中的，异步方法是通常只需 DirectEventStream 替换为 BufferedEventStream，并将连接字符串传递给构造函数中，而不是在 BAM 主导入中的消息框。</span><span class="sxs-lookup"><span data-stu-id="d8739-116">Using the asynchronous approach from code is usually as simple as replacing the DirectEventStream with BufferedEventStream, and passing the connection string to the Message Box in the constructor, instead of the one for BAM Primary Import.</span></span>  
  
 <span data-ttu-id="d8739-117">使用异步业务事件跟踪在代码中遵循以下准则：</span><span class="sxs-lookup"><span data-stu-id="d8739-117">Use the following guidelines regarding asynchronous business event tracking in your code:</span></span>  
  
-   <span data-ttu-id="d8739-118">始终使用继续符，当活动跨多个应用程序，并且以异步方式向 BAM 发送数据，即使传播到所有组件的 ActivityID。</span><span class="sxs-lookup"><span data-stu-id="d8739-118">Always use continuation when the Activity spans multiple applications and you send the data asynchronously to BAM, even if you propagate the ActivityID to all components.</span></span> <span data-ttu-id="d8739-119">在这种情况下，唯一字符串 （例如应用程序名称） 前加上使用每个应用程序中的 activityid 各不相同。</span><span class="sxs-lookup"><span data-stu-id="d8739-119">In this case, use a different ActivityID in each application by prefixing it with a unique string (e.g. Application Name).</span></span> <span data-ttu-id="d8739-120">这是必需的因为不同的应用程序中的数据可能会到达 BAM 的随机顺序和 BAM 必须管理顺序颠倒的事件，以确保正确的查询和聚合结果。</span><span class="sxs-lookup"><span data-stu-id="d8739-120">This is necessary because the data from different applications might arrive to BAM in random order, and BAM has to manage the out-of-order events to ensure correct Query and Aggregation results.</span></span>  
  
-   <span data-ttu-id="d8739-121">事件监视 （例如 COM + 松散耦合事件或 WMI 事件） 的常规方法不适用于 BAM，因为事件数据是独立于事务。</span><span class="sxs-lookup"><span data-stu-id="d8739-121">The usual methods of event monitoring (e.g. COM+ Loosely Coupled Events or WMI Events) are not applicable for BAM because the event data is independent of the transaction.</span></span> <span data-ttu-id="d8739-122">例如，它可能看起来好像只有一个传入的采购订单的 1000 美元，但将其保存到数据库的尝试失败 10 次时收到了 10 张采购订单总计 $10,000。</span><span class="sxs-lookup"><span data-stu-id="d8739-122">For example, it may look like you received 10 purchase orders for a total of $10,000 while there was only one incoming purchase order for $1000, but the attempt to save it to the database failed 10 times.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8739-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8739-123">See Also</span></span>  

 [<span data-ttu-id="d8739-124">同步业务事件跟踪</span><span class="sxs-lookup"><span data-stu-id="d8739-124">Synchronous Business Event Tracking</span></span>](../core/synchronous-business-event-tracking.md)