---
title: 持久化和业务流程引擎 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration engine, persistence
- persistence
- orchestration engine, serialization
ms.assetid: 088230ef-13b3-440b-9875-6449f29dd5c6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d61d6665ba0828fb6cf24ef71ffb04fbcb94d5e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022515"
---
# <a name="persistence-and-the-orchestration-engine"></a><span data-ttu-id="05cdd-102">持久化和业务流程引擎</span><span class="sxs-lookup"><span data-stu-id="05cdd-102">Persistence and the Orchestration Engine</span></span>
<span data-ttu-id="05cdd-103">状态持久性、 其管理和还原构成大量的业务流程引擎的基本功能的基础。</span><span class="sxs-lookup"><span data-stu-id="05cdd-103">State persistence, its management and restoration form the basis of a lot of fundamental functionalities of the orchestration engine.</span></span> <span data-ttu-id="05cdd-104">具体而言，持久性至关重要的正确运行：</span><span class="sxs-lookup"><span data-stu-id="05cdd-104">In particular, persistence is critical to the correct functioning of:</span></span>  
  
- <span data-ttu-id="05cdd-105">冻结和解除冻结</span><span class="sxs-lookup"><span data-stu-id="05cdd-105">Dehydration and rehydration</span></span>  
  
- <span data-ttu-id="05cdd-106">计算机不可知执行和解除冻结</span><span class="sxs-lookup"><span data-stu-id="05cdd-106">Machine agnostic execution and rehydration</span></span>  
  
- <span data-ttu-id="05cdd-107">补偿模型</span><span class="sxs-lookup"><span data-stu-id="05cdd-107">Compensation model</span></span>  
  
- <span data-ttu-id="05cdd-108">受控的系统关闭</span><span class="sxs-lookup"><span data-stu-id="05cdd-108">Controlled System Shutdown</span></span>  
  
- <span data-ttu-id="05cdd-109">恢复</span><span class="sxs-lookup"><span data-stu-id="05cdd-109">Recovery</span></span>  
  
  <span data-ttu-id="05cdd-110">业务流程引擎将保存到持久性存储区的不同位置，正在运行的业务流程实例的整个状态，以便在内存中，该实例可以更高版本完全还原。</span><span class="sxs-lookup"><span data-stu-id="05cdd-110">The orchestration engine saves to persistent storage the entire state of a running orchestration instance at various points, so that the instance can later be completely restored in memory.</span></span> <span data-ttu-id="05cdd-111">状态包括：</span><span class="sxs-lookup"><span data-stu-id="05cdd-111">The state includes:</span></span>  
  
- <span data-ttu-id="05cdd-112">引擎，包括其当前进度的内部状态。</span><span class="sxs-lookup"><span data-stu-id="05cdd-112">The internal state of the engine, including its current progress.</span></span>  
  
- <span data-ttu-id="05cdd-113">维护状态信息和正在使用的业务流程的任何.NET 组件的状态。</span><span class="sxs-lookup"><span data-stu-id="05cdd-113">The state of any .NET components that maintain state information and are being used by the orchestration.</span></span>  
  
- <span data-ttu-id="05cdd-114">消息和变量的值。</span><span class="sxs-lookup"><span data-stu-id="05cdd-114">Message and variable values.</span></span>  
  
## <a name="persistence-points"></a><span data-ttu-id="05cdd-115">持久性点</span><span class="sxs-lookup"><span data-stu-id="05cdd-115">Persistence Points</span></span>  
 <span data-ttu-id="05cdd-116">业务流程引擎保存在不同点正在运行的业务流程实例的状态。</span><span class="sxs-lookup"><span data-stu-id="05cdd-116">The orchestration engine saves the state of a running orchestration instance at various points.</span></span> <span data-ttu-id="05cdd-117">如果需要解除冻结的业务流程实例、 从受控的关闭、 启动或从意外关机恢复，它将从最后一个持久点时，运行业务流程实例，像其他任何内容发生。</span><span class="sxs-lookup"><span data-stu-id="05cdd-117">If it needs to rehydrate the orchestration instance, start up from a controlled shutdown, or recover from an unexpected shutdown, it will run the orchestration instance from the last persistence point, as though nothing else had occurred.</span></span> <span data-ttu-id="05cdd-118">例如，如果收到一条消息，但没有意外的关机可以保存状态之前，该引擎不会记录它已经收到消息，并将其再次出现在重新启动。</span><span class="sxs-lookup"><span data-stu-id="05cdd-118">For example, if a message is received but there is an unexpected shutdown before state can be saved, the engine will not record that it has received the message, and will receive it again upon restarting.</span></span> <span data-ttu-id="05cdd-119">在以下情况下，引擎将保存业务流程的状态：</span><span class="sxs-lookup"><span data-stu-id="05cdd-119">The engine will save the state of an orchestration in the following circumstances:</span></span>  
  
-   <span data-ttu-id="05cdd-120">结束事务作用域。</span><span class="sxs-lookup"><span data-stu-id="05cdd-120">The end of a transactional scope is reached.</span></span>  
  
    -   <span data-ttu-id="05cdd-121">引擎保存事务作用域结束时的状态，以便明确，定义业务流程应继续执行的点，并补偿可执行正确如有必要。</span><span class="sxs-lookup"><span data-stu-id="05cdd-121">The engine saves state at the end of a transactional scope so that the point at which the orchestration should resume is defined unambiguously, and so that compensation can be carried out correctly if necessary.</span></span>  
  
    -   <span data-ttu-id="05cdd-122">业务流程将继续暂留成功; 如果运行从范围的结束否则，将调用相应的异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="05cdd-122">The orchestration will continue to run from the end of the scope if persistence was successful; otherwise, the appropriate exception handler will be invoked.</span></span>  
  
    -   <span data-ttu-id="05cdd-123">如果该范围位于事务和原子，引擎将保存在原子作用域结束时的状态时提交。</span><span class="sxs-lookup"><span data-stu-id="05cdd-123">If the scope is transactional and atomic, the engine will save state at the end of the atomic scope when it commits.</span></span>  
  
    -   <span data-ttu-id="05cdd-124">如果作用域是事务性的且长时间运行，则引擎将生成一个新事务并保持运行时的完成状态时完成的作用域。</span><span class="sxs-lookup"><span data-stu-id="05cdd-124">If the scope is transactional and long-running, the engine will generate a new transaction and persist the complete state of the runtime when the scope completes.</span></span>  
  
-   <span data-ttu-id="05cdd-125">达到调试断点。</span><span class="sxs-lookup"><span data-stu-id="05cdd-125">A debugging breakpoint is reached.</span></span>  
  
-   <span data-ttu-id="05cdd-126">发送的消息。</span><span class="sxs-lookup"><span data-stu-id="05cdd-126">A message is sent.</span></span> <span data-ttu-id="05cdd-127">唯一的例外是原子事务作用域内从发送消息。</span><span class="sxs-lookup"><span data-stu-id="05cdd-127">The only exception to this is when a message is sent from within an atomic transaction scope.</span></span>  
  
-   <span data-ttu-id="05cdd-128">业务流程将启动另一个业务流程以异步方式如同**启动业务流程**形状。</span><span class="sxs-lookup"><span data-stu-id="05cdd-128">The orchestration starts another orchestration asynchronously, as with the **Start Orchestration** shape.</span></span>  
  
-   <span data-ttu-id="05cdd-129">业务流程实例已挂起。</span><span class="sxs-lookup"><span data-stu-id="05cdd-129">The orchestration instance is suspended.</span></span>  
  
-   <span data-ttu-id="05cdd-130">当业务流程引擎要求关闭的情况下时，它将尝试保存控件的信息，以及所有正在运行的业务流程实例的当前状态，以便它可以继续重新启动时运行它们。</span><span class="sxs-lookup"><span data-stu-id="05cdd-130">When the orchestration engine is asked to shut down, it will try to save control information as well as the current state of all running orchestration instances, so that it can resume running them when it is started again.</span></span> <span data-ttu-id="05cdd-131">如果引擎中保存当前状态不成功，引擎将继续从最后一个持久点在关闭之前发生的业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="05cdd-131">If the engine is unsuccessful in saving the current state, the engine will resume the orchestration instance from the last persistence point that occurred before the shutdown.</span></span> <span data-ttu-id="05cdd-132">这适用于在受控的条件，以及异常终止系统关闭。</span><span class="sxs-lookup"><span data-stu-id="05cdd-132">This applies to the system shutdown in controlled condition as well as abnormal termination.</span></span>  
  
-   <span data-ttu-id="05cdd-133">在引擎确定应已冻结实例。</span><span class="sxs-lookup"><span data-stu-id="05cdd-133">The engine determines that the instance should be dehydrated.</span></span>  
  
-   <span data-ttu-id="05cdd-134">业务流程实例已完成。</span><span class="sxs-lookup"><span data-stu-id="05cdd-134">The orchestration instance is finished.</span></span>  
  
## <a name="serialization"></a><span data-ttu-id="05cdd-135">序列化</span><span class="sxs-lookup"><span data-stu-id="05cdd-135">Serialization</span></span>  
 <span data-ttu-id="05cdd-136">您的业务流程直接或间接引用的所有对象实例 （如通过其他对象） 必须是可序列化的业务流程状态持久保存。</span><span class="sxs-lookup"><span data-stu-id="05cdd-136">All object instances that your orchestration refers to directly or indirectly (as through other objects) must be serializable for your orchestration state to be persisted.</span></span> <span data-ttu-id="05cdd-137">有以下两种例外情况：</span><span class="sxs-lookup"><span data-stu-id="05cdd-137">There are two exceptions:</span></span>  
  
-   <span data-ttu-id="05cdd-138">您可以在原子事务内声明的不可序列化对象。</span><span class="sxs-lookup"><span data-stu-id="05cdd-138">You can have a nonserializable object declared inside an atomic transaction.</span></span> <span data-ttu-id="05cdd-139">可以这样做是因为原子作用域不包含持久化点。</span><span class="sxs-lookup"><span data-stu-id="05cdd-139">You can do this because atomic scopes do not contain persistence points.</span></span>  
  
-   <span data-ttu-id="05cdd-140">不是可序列化的类; System.Xml.XmlDocument。它作为一种特殊情况进行处理，并可以在任意位置。</span><span class="sxs-lookup"><span data-stu-id="05cdd-140">System.Xml.XmlDocument is not a serializable class; it is handled as a special case and can be used anywhere.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="05cdd-141">为了使要保留的.NET 对象，它必须标记为可序列化。</span><span class="sxs-lookup"><span data-stu-id="05cdd-141">In order for a .NET object to be persisted, it must be marked as serializable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05cdd-142">不能使用标准.NET 序列化过程持续 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="05cdd-142">COM objects cannot be persisted using standard .NET serialization procedures.</span></span> <span data-ttu-id="05cdd-143">如果你想要调用原子事务外的 COM 对象，必须是可序列化的.NET 并知道如何保持和还原的 COM 对象的状态的.NET 对象中包装的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="05cdd-143">If you want to call a COM object outside of an atomic transaction, you must wrap the COM object in a .NET object that is .NET serializable and knows how to persist and restore the state of the COM object.</span></span>  
  
## <a name="system-shutdown"></a><span data-ttu-id="05cdd-144">系统关闭</span><span class="sxs-lookup"><span data-stu-id="05cdd-144">System Shutdown</span></span>  
 <span data-ttu-id="05cdd-145">当业务流程引擎要求关闭的情况下时，它将尝试保存控件的信息，以及所有正在运行的业务流程实例的当前状态，以便它可以继续重新启动时运行它们。</span><span class="sxs-lookup"><span data-stu-id="05cdd-145">When the orchestration engine is asked to shut down, it will try to save control information as well as the current state of all running orchestration instances, so that it can resume running them when it is started again.</span></span> <span data-ttu-id="05cdd-146">如果引擎中保存当前状态不成功，引擎将继续从最后一个持久点在关闭之前发生的业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="05cdd-146">If the engine is unsuccessful in saving the current state, the engine will resume the orchestration instance from the last persistence point that occurred before the shutdown.</span></span> <span data-ttu-id="05cdd-147">这适用于在受控的条件，以及异常终止系统关闭。</span><span class="sxs-lookup"><span data-stu-id="05cdd-147">This applies to the system shutdown in controlled condition as well as abnormal termination.</span></span>  
  
## <a name="recovery"></a><span data-ttu-id="05cdd-148">恢复</span><span class="sxs-lookup"><span data-stu-id="05cdd-148">Recovery</span></span>  
 <span data-ttu-id="05cdd-149">引擎定期保存到持久存储状态信息的业务流程实例，并且它还将保存发生系统关闭时的状态。</span><span class="sxs-lookup"><span data-stu-id="05cdd-149">The engine regularly saves to persistent storage the state information of an orchestration instance, and it also saves state in the event of a system shutdown.</span></span>  
  
 <span data-ttu-id="05cdd-150">当业务流程实例由于任何原因失败异常时，可以从上次保持的状态恢复该实例，它可以继续运行就好像不会中断。</span><span class="sxs-lookup"><span data-stu-id="05cdd-150">When an orchestration instance fails abnormally for whatever reason, the instance can be recovered from the last persisted state, and it can continue to run as if there were no interruption.</span></span> <span data-ttu-id="05cdd-151">即使超出服务由于某种原因; 原始服务器实例上运行的是，则返回 true实例可以只需恢复单独的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="05cdd-151">This is true even if the original server that the instance ran on goes out of service for some reason; the instance can simply resume running on a separate machine.</span></span> <span data-ttu-id="05cdd-152">由于此多服务器恢复模型，您不再需要群集。</span><span class="sxs-lookup"><span data-stu-id="05cdd-152">Because of this multi-server recovery model, you no longer need clustering.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05cdd-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="05cdd-153">See Also</span></span>  
 [<span data-ttu-id="05cdd-154">业务流程冻结和解除冻结</span><span class="sxs-lookup"><span data-stu-id="05cdd-154">Orchestration Dehydration and Rehydration</span></span>](../core/orchestration-dehydration-and-rehydration.md)