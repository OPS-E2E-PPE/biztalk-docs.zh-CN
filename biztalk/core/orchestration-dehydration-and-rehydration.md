---
title: 业务流程冻结和解除冻结 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57d7c0bf-a707-4ebd-afab-e75dd80c3c34
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1906d2d09485c56075fedf0d709cc1bdbbb2dba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973518"
---
# <a name="orchestration-dehydration-and-rehydration"></a><span data-ttu-id="bfd84-102">业务流程冻结和解除冻结</span><span class="sxs-lookup"><span data-stu-id="bfd84-102">Orchestration Dehydration and Rehydration</span></span>
<span data-ttu-id="bfd84-103">在同时运行大量长期业务流程时，内存和性能可能存在问题。</span><span class="sxs-lookup"><span data-stu-id="bfd84-103">When many long-running business processes are running at the same time, memory and performance are potential issues.</span></span> <span data-ttu-id="bfd84-104">业务流程引擎通过“冻结”和“解除冻结”业务流程实例来解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="bfd84-104">The orchestration engine addresses these issues by "dehydrating" and "rehydrating" orchestration instances.</span></span>  
  
 <span data-ttu-id="bfd84-105">冻结是将业务流程的状态序列化到 SQL Server 数据库中的过程。</span><span class="sxs-lookup"><span data-stu-id="bfd84-105">Dehydration is the process of serializing the state of an orchestration into a SQL Server database.</span></span> <span data-ttu-id="bfd84-106">解除冻结是此过程的相反： 反序列化数据库从业务流程的最后运行状态。</span><span class="sxs-lookup"><span data-stu-id="bfd84-106">Rehydration is the reverse of this process: deserializing the last running state of an orchestration from the database.</span></span> <span data-ttu-id="bfd84-107">冻结用于通过减少必须在内存中同时实例化的业务流程数来最大程度地降低系统资源的使用。</span><span class="sxs-lookup"><span data-stu-id="bfd84-107">Dehydration is used to minimize the use of system resources by reducing the number of orchestrations that have to be instantiated in memory at one time.</span></span>  
  
## <a name="dehydration"></a><span data-ttu-id="bfd84-108">冻结</span><span class="sxs-lookup"><span data-stu-id="bfd84-108">Dehydration</span></span>  
 <span data-ttu-id="bfd84-109">业务流程引擎可以确定某个业务流程实例已经空闲了相当长的一段时间。</span><span class="sxs-lookup"><span data-stu-id="bfd84-109">The orchestration engine might determine that an orchestration instance has been idle for a relatively long period of time.</span></span> <span data-ttu-id="bfd84-110">它计算阈值以确定它适用于各种操作，需要将等待多长，如果超过这些阈值，它将冻结该实例。</span><span class="sxs-lookup"><span data-stu-id="bfd84-110">It calculates thresholds to determine how long it will wait for various actions to take place, and if those thresholds are exceeded, it dehydrates the instance.</span></span> <span data-ttu-id="bfd84-111">在以下情况下会发生冻结：</span><span class="sxs-lookup"><span data-stu-id="bfd84-111">This can occur under the following circumstances:</span></span>  
  
- <span data-ttu-id="bfd84-112">如果业务流程正在等待接收消息，并且等待的时间超过了引擎所确定的阈值。</span><span class="sxs-lookup"><span data-stu-id="bfd84-112">When the orchestration is waiting to receive a message, and the wait is longer than a threshold determined by the engine.</span></span>  
  
- <span data-ttu-id="bfd84-113">当业务流程"侦听"的消息时使用的表现**侦听**形状，并没有分支将触发之前由引擎所确定的阈值。</span><span class="sxs-lookup"><span data-stu-id="bfd84-113">When the orchestration is "listening" for a message, as it does when you use a **Listen** shape, and no branch is triggered before a threshold determined by the engine.</span></span> <span data-ttu-id="bfd84-114">唯一的例外是何时**侦听**形状包含激活接收。</span><span class="sxs-lookup"><span data-stu-id="bfd84-114">The only exception to this is when the **Listen** shape contains an activation receive.</span></span>  
  
- <span data-ttu-id="bfd84-115">当业务流程中的延迟超过引擎所确定的阈值时。</span><span class="sxs-lookup"><span data-stu-id="bfd84-115">When a delay in the orchestration is longer than a threshold determined by the engine.</span></span>  
  
  <span data-ttu-id="bfd84-116">引擎保存状态来冻结实例，并释放该实例所占用的内存。</span><span class="sxs-lookup"><span data-stu-id="bfd84-116">The engine dehydrates the instance by saving the state, and frees up the memory required by the instance.</span></span> <span data-ttu-id="bfd84-117">通过冻结休眠的业务流程实例，该引擎使得大量长时间运行的业务流程，以同时在同一台计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="bfd84-117">By dehydrating dormant orchestration instances, the engine makes it possible for a large number of long-running business processes to run concurrently on the same computer.</span></span>  
  
  <span data-ttu-id="bfd84-118">可以设置 12 属性以配置冻结在 BizTalk Server 中的工作方式。</span><span class="sxs-lookup"><span data-stu-id="bfd84-118">You can set 12 properties to configure how dehydration works in BizTalk Server.</span></span> <span data-ttu-id="bfd84-119">在本部分中的主题列出并描述了这些属性和其默认值，并讨论各种值如何影响冻结行为。</span><span class="sxs-lookup"><span data-stu-id="bfd84-119">The topics in this section list and describe these properties and their default values, and discuss how various values affect dehydration behavior.</span></span>  
  
## <a name="rehydration"></a><span data-ttu-id="bfd84-120">解除冻结</span><span class="sxs-lookup"><span data-stu-id="bfd84-120">Rehydration</span></span>  
 <span data-ttu-id="bfd84-121">可以触发业务流程引擎，以便在消息接收后或在延迟形状中指定的超时到期后解除冻结某一业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="bfd84-121">The orchestration engine can be triggered to rehydrate an orchestration instance by the receipt of a message or by the expiration of a time-out specified in a Delay shape.</span></span> <span data-ttu-id="bfd84-122">然后将已保存业务流程实例加载到内存，还原其状态，并运行从离开的位置的点。</span><span class="sxs-lookup"><span data-stu-id="bfd84-122">It then loads the saved orchestration instance into memory, restores its state, and runs it from the point where it left off.</span></span> <span data-ttu-id="bfd84-123">有关在业务流程中使用形状的详细信息，请参阅[业务流程形状](../core/orchestration-shapes.md)。</span><span class="sxs-lookup"><span data-stu-id="bfd84-123">For more information about using shapes in orchestrations, see [Orchestration Shapes](../core/orchestration-shapes.md).</span></span>  
  
 <span data-ttu-id="bfd84-124">可以配置业务流程以便在多台服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="bfd84-124">An orchestration can be configured to run on more than one server.</span></span> <span data-ttu-id="bfd84-125">在冻结某一业务流程实例后，可以在其中任何服务器上解除对该实例的冻结。</span><span class="sxs-lookup"><span data-stu-id="bfd84-125">After an orchestration instance has been dehydrated, it can be rehydrated on any of these servers.</span></span> <span data-ttu-id="bfd84-126">如果一台服务器出现故障，引擎将继续在不同服务器上，从其以前的状态继续运行业务流程。</span><span class="sxs-lookup"><span data-stu-id="bfd84-126">If one server goes down, the engine continues to run the orchestration on a different server, continuing from its previous state.</span></span> <span data-ttu-id="bfd84-127">该引擎还会利用此功能以实现跨服务器的负载平衡。</span><span class="sxs-lookup"><span data-stu-id="bfd84-127">The engine also takes advantage of this feature to implement load balancing across servers.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bfd84-128">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bfd84-128">Next steps</span></span>
  
-   [<span data-ttu-id="bfd84-129">冻结默认属性</span><span class="sxs-lookup"><span data-stu-id="bfd84-129">Dehydration Default Properties</span></span>](../core/dehydration-default-properties.md)  
  
-   [<span data-ttu-id="bfd84-130">如何计算冻结</span><span class="sxs-lookup"><span data-stu-id="bfd84-130">How to Calculate Dehydration</span></span>](../core/how-to-calculate-dehydration.md)  
  
-   [<span data-ttu-id="bfd84-131">示例冻结计算</span><span class="sxs-lookup"><span data-stu-id="bfd84-131">Sample Dehydration Calculation</span></span>](../core/sample-dehydration-calculation.md)  
  
-   [<span data-ttu-id="bfd84-132">业务流程冻结性能计数器</span><span class="sxs-lookup"><span data-stu-id="bfd84-132">Orchestration Dehydration Performance Counters</span></span>](../core/orchestration-dehydration-performance-counters.md)  
  
-   [<span data-ttu-id="bfd84-133">BTSNTSvc.exe.config 文件</span><span class="sxs-lookup"><span data-stu-id="bfd84-133">BTSNTSvc.exe.config File</span></span>](../core/btsntsvc-exe-config-file.md)  
  
-   [<span data-ttu-id="bfd84-134">可影响冻结行为的其他活动</span><span class="sxs-lookup"><span data-stu-id="bfd84-134">Other Activities That Can Affect Dehydration Behavior</span></span>](../core/other-activities-that-can-affect-dehydration-behavior.md)