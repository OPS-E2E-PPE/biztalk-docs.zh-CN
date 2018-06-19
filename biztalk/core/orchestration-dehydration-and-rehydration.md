---
title: 业务流程冻结和 Rehydration |Microsoft 文档
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
ms.openlocfilehash: f7cee568cda6c869ede94e28bce441462c0c7cdc
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710612"
---
# <a name="orchestration-dehydration-and-rehydration"></a><span data-ttu-id="eb7a0-102">业务流程冻结和 Rehydration</span><span class="sxs-lookup"><span data-stu-id="eb7a0-102">Orchestration Dehydration and Rehydration</span></span>
<span data-ttu-id="eb7a0-103">在同时运行大量长期业务流程时，内存和性能可能存在问题。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-103">When many long-running business processes are running at the same time, memory and performance are potential issues.</span></span> <span data-ttu-id="eb7a0-104">业务流程引擎通过“冻结”和“解除冻结”业务流程实例来解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-104">The orchestration engine addresses these issues by "dehydrating" and "rehydrating" orchestration instances.</span></span>  
  
 <span data-ttu-id="eb7a0-105">冻结是将业务流程的状态序列化到 SQL Server 数据库中的过程。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-105">Dehydration is the process of serializing the state of an orchestration into a SQL Server database.</span></span> <span data-ttu-id="eb7a0-106">Rehydration 是此过程的反向︰ 反序列化从数据库的业务流程的上次运行状态。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-106">Rehydration is the reverse of this process: deserializing the last running state of an orchestration from the database.</span></span> <span data-ttu-id="eb7a0-107">冻结用于通过减少必须在内存中同时实例化的业务流程数来最大程度地降低系统资源的使用。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-107">Dehydration is used to minimize the use of system resources by reducing the number of orchestrations that have to be instantiated in memory at one time.</span></span>  
  
## <a name="dehydration"></a><span data-ttu-id="eb7a0-108">冻结</span><span class="sxs-lookup"><span data-stu-id="eb7a0-108">Dehydration</span></span>  
 <span data-ttu-id="eb7a0-109">业务流程引擎可以确定某个业务流程实例已经空闲了相当长的一段时间。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-109">The orchestration engine might determine that an orchestration instance has been idle for a relatively long period of time.</span></span> <span data-ttu-id="eb7a0-110">它计算阈值来确定它将在多长时间等待各种操作做好准备，并超出这些阈值，如果它 dehydrates 实例。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-110">It calculates thresholds to determine how long it will wait for various actions to take place, and if those thresholds are exceeded, it dehydrates the instance.</span></span> <span data-ttu-id="eb7a0-111">在以下情况下会发生冻结：</span><span class="sxs-lookup"><span data-stu-id="eb7a0-111">This can occur under the following circumstances:</span></span>  
  
-   <span data-ttu-id="eb7a0-112">如果业务流程正在等待接收消息，并且等待的时间超过了引擎所确定的阈值。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-112">When the orchestration is waiting to receive a message, and the wait is longer than a threshold determined by the engine.</span></span>  
  
-   <span data-ttu-id="eb7a0-113">当业务流程"侦听"一条消息，你使用时的表现 **侦听** 形状，并没有分支触发之前由引擎确定的阈值。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-113">When the orchestration is "listening" for a message, as it does when you use a **Listen** shape, and no branch is triggered before a threshold determined by the engine.</span></span> <span data-ttu-id="eb7a0-114">唯一的例外是当 **侦听** 形状包含激活接收。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-114">The only exception to this is when the **Listen** shape contains an activation receive.</span></span>  
  
-   <span data-ttu-id="eb7a0-115">当业务流程中的延迟超过引擎所确定的阈值时。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-115">When a delay in the orchestration is longer than a threshold determined by the engine.</span></span>  
  
 <span data-ttu-id="eb7a0-116">引擎 dehydrates 实例的保存状态，并释放的实例所需的内存。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-116">The engine dehydrates the instance by saving the state, and frees up the memory required by the instance.</span></span> <span data-ttu-id="eb7a0-117">通过冻结休眠业务流程实例过程中，引擎使大量的长时间运行业务流程，以同时在同一台计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-117">By dehydrating dormant orchestration instances, the engine makes it possible for a large number of long-running business processes to run concurrently on the same computer.</span></span>  
  
 <span data-ttu-id="eb7a0-118">你可以设置 12 属性来配置 BizTalk Server 中的冻结工作原理。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-118">You can set 12 properties to configure how dehydration works in BizTalk Server.</span></span> <span data-ttu-id="eb7a0-119">此部分中的主题列出并描述了这些属性和其默认值，并且会讨论如何各种不同的值影响冻结行为。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-119">The topics in this section list and describe these properties and their default values, and discuss how various values affect dehydration behavior.</span></span>  
  
## <a name="rehydration"></a><span data-ttu-id="eb7a0-120">Rehydration</span><span class="sxs-lookup"><span data-stu-id="eb7a0-120">Rehydration</span></span>  
 <span data-ttu-id="eb7a0-121">可以触发业务流程引擎，以便在消息接收后或在延迟形状中指定的超时到期后解除冻结某一业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-121">The orchestration engine can be triggered to rehydrate an orchestration instance by the receipt of a message or by the expiration of a time-out specified in a Delay shape.</span></span> <span data-ttu-id="eb7a0-122">然后将已保存业务流程实例加载到内存，将还原其状态，并从它暂停的点运行它。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-122">It then loads the saved orchestration instance into memory, restores its state, and runs it from the point where it left off.</span></span> <span data-ttu-id="eb7a0-123">有关使用形状中业务流程的详细信息，请参阅[Orchestration 形状](../core/orchestration-shapes.md)。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-123">For more information about using shapes in orchestrations, see [Orchestration Shapes](../core/orchestration-shapes.md).</span></span>  
  
 <span data-ttu-id="eb7a0-124">可以配置业务流程以便在多台服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-124">An orchestration can be configured to run on more than one server.</span></span> <span data-ttu-id="eb7a0-125">在冻结某一业务流程实例后，可以在其中任何服务器上解除对该实例的冻结。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-125">After an orchestration instance has been dehydrated, it can be rehydrated on any of these servers.</span></span> <span data-ttu-id="eb7a0-126">如果一台服务器出现故障，引擎将继续在不同服务器上，在从以前的状态继续运行业务流程。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-126">If one server goes down, the engine continues to run the orchestration on a different server, continuing from its previous state.</span></span> <span data-ttu-id="eb7a0-127">该引擎还可利用此功能，以实现跨服务器的负载平衡。</span><span class="sxs-lookup"><span data-stu-id="eb7a0-127">The engine also takes advantage of this feature to implement load balancing across servers.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="eb7a0-128">后续步骤</span><span class="sxs-lookup"><span data-stu-id="eb7a0-128">Next steps</span></span>
  
-   [<span data-ttu-id="eb7a0-129">冻结默认属性</span><span class="sxs-lookup"><span data-stu-id="eb7a0-129">Dehydration Default Properties</span></span>](../core/dehydration-default-properties.md)  
  
-   [<span data-ttu-id="eb7a0-130">如何计算冻结</span><span class="sxs-lookup"><span data-stu-id="eb7a0-130">How to Calculate Dehydration</span></span>](../core/how-to-calculate-dehydration.md)  
  
-   [<span data-ttu-id="eb7a0-131">示例冻结计算</span><span class="sxs-lookup"><span data-stu-id="eb7a0-131">Sample Dehydration Calculation</span></span>](../core/sample-dehydration-calculation.md)  
  
-   [<span data-ttu-id="eb7a0-132">业务流程冻结性能计数器</span><span class="sxs-lookup"><span data-stu-id="eb7a0-132">Orchestration Dehydration Performance Counters</span></span>](../core/orchestration-dehydration-performance-counters.md)  
  
-   [<span data-ttu-id="eb7a0-133">BTSNTSvc.exe.config 文件</span><span class="sxs-lookup"><span data-stu-id="eb7a0-133">BTSNTSvc.exe.config File</span></span>](../core/btsntsvc-exe-config-file.md)  
  
-   [<span data-ttu-id="eb7a0-134">可影响冻结行为的其他活动</span><span class="sxs-lookup"><span data-stu-id="eb7a0-134">Other Activities That Can Affect Dehydration Behavior</span></span>](../core/other-activities-that-can-affect-dehydration-behavior.md)