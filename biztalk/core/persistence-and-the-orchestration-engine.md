---
title: 持久性和业务流程引擎 |Microsoft 文档
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
ms.openlocfilehash: 5e9e1c8b158d313681a6e1374a586ca957b1aa15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264925"
---
# <a name="persistence-and-the-orchestration-engine"></a><span data-ttu-id="48f7a-102">持久化和业务流程引擎</span><span class="sxs-lookup"><span data-stu-id="48f7a-102">Persistence and the Orchestration Engine</span></span>
<span data-ttu-id="48f7a-103">状态持久性、 管理和还原形成了大量基本功能的业务流程引擎的基础。</span><span class="sxs-lookup"><span data-stu-id="48f7a-103">State persistence, its management and restoration form the basis of a lot of fundamental functionalities of the orchestration engine.</span></span> <span data-ttu-id="48f7a-104">具体而言，持久性至关重要的正确运行：</span><span class="sxs-lookup"><span data-stu-id="48f7a-104">In particular, persistence is critical to the correct functioning of:</span></span>  
  
-   <span data-ttu-id="48f7a-105">冻结和 rehydration</span><span class="sxs-lookup"><span data-stu-id="48f7a-105">Dehydration and rehydration</span></span>  
  
-   <span data-ttu-id="48f7a-106">计算机不可知执行和 rehydration</span><span class="sxs-lookup"><span data-stu-id="48f7a-106">Machine agnostic execution and rehydration</span></span>  
  
-   <span data-ttu-id="48f7a-107">补偿模型</span><span class="sxs-lookup"><span data-stu-id="48f7a-107">Compensation model</span></span>  
  
-   <span data-ttu-id="48f7a-108">受控的系统关闭</span><span class="sxs-lookup"><span data-stu-id="48f7a-108">Controlled System Shutdown</span></span>  
  
-   <span data-ttu-id="48f7a-109">恢复</span><span class="sxs-lookup"><span data-stu-id="48f7a-109">Recovery</span></span>  
  
 <span data-ttu-id="48f7a-110">业务流程引擎将保存到持久性存储区的各个点，在正在运行的业务流程实例的整个状态，以便在内存中，该实例可以更高版本完全还原。</span><span class="sxs-lookup"><span data-stu-id="48f7a-110">The orchestration engine saves to persistent storage the entire state of a running orchestration instance at various points, so that the instance can later be completely restored in memory.</span></span> <span data-ttu-id="48f7a-111">状态包括：</span><span class="sxs-lookup"><span data-stu-id="48f7a-111">The state includes:</span></span>  
  
-   <span data-ttu-id="48f7a-112">引擎，包括其当前进行的内部状态。</span><span class="sxs-lookup"><span data-stu-id="48f7a-112">The internal state of the engine, including its current progress.</span></span>  
  
-   <span data-ttu-id="48f7a-113">维护状态信息和正在使用的业务流程的任何.NET 组件的状态。</span><span class="sxs-lookup"><span data-stu-id="48f7a-113">The state of any .NET components that maintain state information and are being used by the orchestration.</span></span>  
  
-   <span data-ttu-id="48f7a-114">消息和变量的值。</span><span class="sxs-lookup"><span data-stu-id="48f7a-114">Message and variable values.</span></span>  
  
## <a name="persistence-points"></a><span data-ttu-id="48f7a-115">持久性点</span><span class="sxs-lookup"><span data-stu-id="48f7a-115">Persistence Points</span></span>  
 <span data-ttu-id="48f7a-116">业务流程引擎保存在不同的时间点正在运行的业务流程实例的状态。</span><span class="sxs-lookup"><span data-stu-id="48f7a-116">The orchestration engine saves the state of a running orchestration instance at various points.</span></span> <span data-ttu-id="48f7a-117">如果它需要 rehydrate 业务流程实例、 从受控关机，启动或从意外关闭恢复，它将从最后一个持久点时，运行业务流程实例，就像其他任何内容出现。</span><span class="sxs-lookup"><span data-stu-id="48f7a-117">If it needs to rehydrate the orchestration instance, start up from a controlled shutdown, or recover from an unexpected shutdown, it will run the orchestration instance from the last persistence point, as though nothing else had occurred.</span></span> <span data-ttu-id="48f7a-118">例如，如果收到一条消息，但没有发生意外的关闭之前可以保存状态，它接收的消息，并将它再次出现在重新启动时将不会记录引擎。</span><span class="sxs-lookup"><span data-stu-id="48f7a-118">For example, if a message is received but there is an unexpected shutdown before state can be saved, the engine will not record that it has received the message, and will receive it again upon restarting.</span></span> <span data-ttu-id="48f7a-119">引擎会将业务流程的状态保存在下列情况：</span><span class="sxs-lookup"><span data-stu-id="48f7a-119">The engine will save the state of an orchestration in the following circumstances:</span></span>  
  
-   <span data-ttu-id="48f7a-120">结束一个事务范围。</span><span class="sxs-lookup"><span data-stu-id="48f7a-120">The end of a transactional scope is reached.</span></span>  
  
    -   <span data-ttu-id="48f7a-121">引擎保存在一个事务范围末尾的状态，以便明确，定义应从该处恢复业务流程的点并以便补偿可以执行正确如有必要。</span><span class="sxs-lookup"><span data-stu-id="48f7a-121">The engine saves state at the end of a transactional scope so that the point at which the orchestration should resume is defined unambiguously, and so that compensation can be carried out correctly if necessary.</span></span>  
  
    -   <span data-ttu-id="48f7a-122">业务流程将继续运行后面的作用域，如果持久性成功;否则，将调用相应的异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="48f7a-122">The orchestration will continue to run from the end of the scope if persistence was successful; otherwise, the appropriate exception handler will be invoked.</span></span>  
  
    -   <span data-ttu-id="48f7a-123">如果在作用域是事务性的且原子，引擎将时它会将提交保存末尾的原子作用域的状态。</span><span class="sxs-lookup"><span data-stu-id="48f7a-123">If the scope is transactional and atomic, the engine will save state at the end of the atomic scope when it commits.</span></span>  
  
    -   <span data-ttu-id="48f7a-124">如果作用域是事务性的且长时间运行，则引擎将生成一个新的事务，并将完成状态的运行时保存范围完成时。</span><span class="sxs-lookup"><span data-stu-id="48f7a-124">If the scope is transactional and long-running, the engine will generate a new transaction and persist the complete state of the runtime when the scope completes.</span></span>  
  
-   <span data-ttu-id="48f7a-125">调试断点为止。</span><span class="sxs-lookup"><span data-stu-id="48f7a-125">A debugging breakpoint is reached.</span></span>  
  
-   <span data-ttu-id="48f7a-126">发送的消息。</span><span class="sxs-lookup"><span data-stu-id="48f7a-126">A message is sent.</span></span> <span data-ttu-id="48f7a-127">唯一的例外是在原子事务范围内从发送消息时。</span><span class="sxs-lookup"><span data-stu-id="48f7a-127">The only exception to this is when a message is sent from within an atomic transaction scope.</span></span>  
  
-   <span data-ttu-id="48f7a-128">业务流程以异步方式启动另一个业务流程与**启动 Orchestration**形状。</span><span class="sxs-lookup"><span data-stu-id="48f7a-128">The orchestration starts another orchestration asynchronously, as with the **Start Orchestration** shape.</span></span>  
  
-   <span data-ttu-id="48f7a-129">业务流程实例处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="48f7a-129">The orchestration instance is suspended.</span></span>  
  
-   <span data-ttu-id="48f7a-130">当系统询问业务流程引擎若要关闭的情况下时，它将尝试保存控制信息，以及所有运行的业务流程实例的当前状态，以便才能继续执行时再次启动时运行它们。</span><span class="sxs-lookup"><span data-stu-id="48f7a-130">When the orchestration engine is asked to shut down, it will try to save control information as well as the current state of all running orchestration instances, so that it can resume running them when it is started again.</span></span> <span data-ttu-id="48f7a-131">如果引擎都不能成功保存的当前状态，引擎将恢复发生之前关闭最后一个持久点中的业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="48f7a-131">If the engine is unsuccessful in saving the current state, the engine will resume the orchestration instance from the last persistence point that occurred before the shutdown.</span></span> <span data-ttu-id="48f7a-132">这适用于在受控的条件以及异常终止系统关闭。</span><span class="sxs-lookup"><span data-stu-id="48f7a-132">This applies to the system shutdown in controlled condition as well as abnormal termination.</span></span>  
  
-   <span data-ttu-id="48f7a-133">引擎确定，应已冻结实例。</span><span class="sxs-lookup"><span data-stu-id="48f7a-133">The engine determines that the instance should be dehydrated.</span></span>  
  
-   <span data-ttu-id="48f7a-134">业务流程实例已完成。</span><span class="sxs-lookup"><span data-stu-id="48f7a-134">The orchestration instance is finished.</span></span>  
  
## <a name="serialization"></a><span data-ttu-id="48f7a-135">序列化</span><span class="sxs-lookup"><span data-stu-id="48f7a-135">Serialization</span></span>  
 <span data-ttu-id="48f7a-136">您的业务流程直接或间接引用的所有对象实例 （通过其他对象一样） 必须是可序列化你的业务流程的状态要保留的。</span><span class="sxs-lookup"><span data-stu-id="48f7a-136">All object instances that your orchestration refers to directly or indirectly (as through other objects) must be serializable for your orchestration state to be persisted.</span></span> <span data-ttu-id="48f7a-137">有以下两种例外情况：</span><span class="sxs-lookup"><span data-stu-id="48f7a-137">There are two exceptions:</span></span>  
  
-   <span data-ttu-id="48f7a-138">你可以在原子事务声明的不可序列化对象。</span><span class="sxs-lookup"><span data-stu-id="48f7a-138">You can have a nonserializable object declared inside an atomic transaction.</span></span> <span data-ttu-id="48f7a-139">因为原子作用域不包含持久性点时，可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="48f7a-139">You can do this because atomic scopes do not contain persistence points.</span></span>  
  
-   <span data-ttu-id="48f7a-140">不是可序列化的类; System.Xml.XmlDocument。它作为一种特殊情况进行处理，并可以使用任意位置。</span><span class="sxs-lookup"><span data-stu-id="48f7a-140">System.Xml.XmlDocument is not a serializable class; it is handled as a special case and can be used anywhere.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="48f7a-141">为了使要持久化.NET 对象，它必须标记为可序列化。</span><span class="sxs-lookup"><span data-stu-id="48f7a-141">In order for a .NET object to be persisted, it must be marked as serializable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48f7a-142">不能使用标准.NET 序列化过程持续 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="48f7a-142">COM objects cannot be persisted using standard .NET serialization procedures.</span></span> <span data-ttu-id="48f7a-143">如果你想要调用 COM 对象在原子事务之外，你必须在.NET 对象，即.NET 可序列化并且知道如何保存和还原的 COM 对象的状态中包装的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="48f7a-143">If you want to call a COM object outside of an atomic transaction, you must wrap the COM object in a .NET object that is .NET serializable and knows how to persist and restore the state of the COM object.</span></span>  
  
## <a name="system-shutdown"></a><span data-ttu-id="48f7a-144">系统关闭</span><span class="sxs-lookup"><span data-stu-id="48f7a-144">System Shutdown</span></span>  
 <span data-ttu-id="48f7a-145">当系统询问业务流程引擎若要关闭的情况下时，它将尝试保存控制信息，以及所有运行的业务流程实例的当前状态，以便才能继续执行时再次启动时运行它们。</span><span class="sxs-lookup"><span data-stu-id="48f7a-145">When the orchestration engine is asked to shut down, it will try to save control information as well as the current state of all running orchestration instances, so that it can resume running them when it is started again.</span></span> <span data-ttu-id="48f7a-146">如果引擎都不能成功保存的当前状态，引擎将恢复发生之前关闭最后一个持久点中的业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="48f7a-146">If the engine is unsuccessful in saving the current state, the engine will resume the orchestration instance from the last persistence point that occurred before the shutdown.</span></span> <span data-ttu-id="48f7a-147">这适用于在受控的条件以及异常终止系统关闭。</span><span class="sxs-lookup"><span data-stu-id="48f7a-147">This applies to the system shutdown in controlled condition as well as abnormal termination.</span></span>  
  
## <a name="recovery"></a><span data-ttu-id="48f7a-148">恢复</span><span class="sxs-lookup"><span data-stu-id="48f7a-148">Recovery</span></span>  
 <span data-ttu-id="48f7a-149">引擎定期将保存到持久性存储区的状态信息的业务流程实例，并将保存发生系统关闭时的状态。</span><span class="sxs-lookup"><span data-stu-id="48f7a-149">The engine regularly saves to persistent storage the state information of an orchestration instance, and it also saves state in the event of a system shutdown.</span></span>  
  
 <span data-ttu-id="48f7a-150">当业务流程实例出于任何原因失败异常时，可以从上次保持的状态恢复实例，并且它可以继续运行，好像没有中断。</span><span class="sxs-lookup"><span data-stu-id="48f7a-150">When an orchestration instance fails abnormally for whatever reason, the instance can be recovered from the last persisted state, and it can continue to run as if there were no interruption.</span></span> <span data-ttu-id="48f7a-151">这是 true，即使原始服务器实例上运行超出出于某种原因; 的服务实例可以只需恢复在单独的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="48f7a-151">This is true even if the original server that the instance ran on goes out of service for some reason; the instance can simply resume running on a separate machine.</span></span> <span data-ttu-id="48f7a-152">由于此多服务器恢复模型，你不再需要群集。</span><span class="sxs-lookup"><span data-stu-id="48f7a-152">Because of this multi-server recovery model, you no longer need clustering.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48f7a-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48f7a-153">See Also</span></span>  
 [<span data-ttu-id="48f7a-154">业务流程冻结和 Rehydration</span><span class="sxs-lookup"><span data-stu-id="48f7a-154">Orchestration Dehydration and Rehydration</span></span>](../core/orchestration-dehydration-and-rehydration.md)