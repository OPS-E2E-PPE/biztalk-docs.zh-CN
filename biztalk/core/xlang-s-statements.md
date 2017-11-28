---
title: "XLANG-s 语句 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 620d0452-a8da-4285-b8b2-5a932ffcde28
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50f2ea904d134d22f08d86b1d600fdb3133a9c45
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="xlang-s-statements"></a><span data-ttu-id="0f3f2-102">XLANG-s 语句</span><span class="sxs-lookup"><span data-stu-id="0f3f2-102">XLANG-s Statements</span></span>
<span data-ttu-id="0f3f2-103">XLANG/s 语句通常分为两个类别之一： 如作用于其自己的简单语句**接收**或**发送**，和复杂语句包含或任一简单语句组合或其他复杂的语句，如**作用域**，**并行**，和**侦听**。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-103">XLANG/s statements generally fall into one of two categories: simple statements that act on their own, such as **receive** or **send**, and complex statements that contain or group either simple statements or other complex statements, such as **scope**, **parallel**, and **listen**.</span></span> <span data-ttu-id="0f3f2-104">每个语句都与 BizTalk 业务流程设计器中的一个业务流程形状相对应。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-104">Each statement is corresponding to an orchestration shape in the BizTalk Orchestration Designer.</span></span> <span data-ttu-id="0f3f2-105">XLANG/s 定义了以下语句：</span><span class="sxs-lookup"><span data-stu-id="0f3f2-105">XLANG/s defines the following statements:</span></span>  
  
-   <span data-ttu-id="0f3f2-106">**组。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-106">**group.**</span></span> <span data-ttu-id="0f3f2-107">将操作分组到单个可折叠和展开单元用于观看方便。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-107">Used to group operations into a single collapsible and expandable unit for visual convenience.</span></span>  
  
-   <span data-ttu-id="0f3f2-108">**发送。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-108">**send.**</span></span> <span data-ttu-id="0f3f2-109">用于向指定端口发送指定消息。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-109">Used to send a specified message to a specified port.</span></span>  
  
-   <span data-ttu-id="0f3f2-110">**接收。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-110">**receive.**</span></span> <span data-ttu-id="0f3f2-111">用于等待接收来自指定端口的指定消息。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-111">Used to wait for the receipt of a specified message from a specified port.</span></span>  
  
-   <span data-ttu-id="0f3f2-112">**端口。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-112">**port.**</span></span> <span data-ttu-id="0f3f2-113">定义传输消息的位置和方式。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-113">Defines where and how messages are transmitted.</span></span>  
  
-   <span data-ttu-id="0f3f2-114">**角色链接。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-114">**role link.**</span></span> <span data-ttu-id="0f3f2-115">用于创建与同一逻辑合作伙伴，可能是通过不同的传输或终结点进行通信的端口的集合</span><span class="sxs-lookup"><span data-stu-id="0f3f2-115">Used to create a collection of ports that communicate with the same logical partner, perhaps through different transports or endpoints</span></span>  
  
-   <span data-ttu-id="0f3f2-116">**转换。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-116">**transform.**</span></span> <span data-ttu-id="0f3f2-117">用于将现有消息中的字段映射到新消息。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-117">Used to map the fields from existing messages into new messages.</span></span>  
  
-   <span data-ttu-id="0f3f2-118">**消息赋值。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-118">**message assignment.**</span></span> <span data-ttu-id="0f3f2-119">用于向指定端口发送指定消息。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-119">Used to send a specified message to a specified port.</span></span>  
  
-   <span data-ttu-id="0f3f2-120">**构造消息。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-120">**construct message.**</span></span> <span data-ttu-id="0f3f2-121">定义一个创建和初始化消息的 XLANG/s 代码块。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-121">Defines a block of XLANG/s code where a message is created and initialized.</span></span> <span data-ttu-id="0f3f2-122">已有消息可发送至 XLANG/s 程序，但不能在构造外创建消息。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-122">Existing messages can be sent to an XLANG/s program, but cannot be created outside of a construct.</span></span> <span data-ttu-id="0f3f2-123">这种机制可用于消息分发和提供丰富的消息跟踪功能，因为消息状态在任何时候都是可知的。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-123">This mechanism provides for message distribution and rich message tracking, because a message state is known at all times.</span></span>  
  
-   <span data-ttu-id="0f3f2-124">**调用业务流程。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-124">**call orchestration.**</span></span> <span data-ttu-id="0f3f2-125">从一个业务流程同步调用另一个业务流程。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-125">Synchronously calls from one orchestration to another orchestration.</span></span> <span data-ttu-id="0f3f2-126">可传递和返回参数。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-126">Parameters can be passed and returned.</span></span>  
  
-   <span data-ttu-id="0f3f2-127">**启动业务流程。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-127">**start orchestration.**</span></span> <span data-ttu-id="0f3f2-128">用于启用您的业务流程，以异步方式调用另一个业务流程。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-128">Used to enable your orchestration to call another orchestration asynchronously.</span></span>  
  
-   <span data-ttu-id="0f3f2-129">**调用的规则。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-129">**call rules.**</span></span> <span data-ttu-id="0f3f2-130">允许你配置要在业务流程中执行的业务规则策略。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-130">Enables you to configure a Business Rules policy to be executed in your orchestration.</span></span>  
  
-   <span data-ttu-id="0f3f2-131">**表达式。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-131">**expression.**</span></span> <span data-ttu-id="0f3f2-132">XLANG/s 支持丰富的表达式语法，以支持协议定义所要求的各种使用方案。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-132">XLANG/s supports rich expression syntax to support the wide variety of usage scenarios required for protocol definition.</span></span> <span data-ttu-id="0f3f2-133">此语句用于分配端口属性、服务链接属性、消息、变量和对象，以及用于调用方法、属性或静态数据字段。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-133">This statement is used to assign port properties, service-link properties, messages, variables, and objects, and to invoke methods, properties, or static data fields.</span></span>  
  
-   <span data-ttu-id="0f3f2-134">**决定。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-134">**decide.**</span></span> <span data-ttu-id="0f3f2-135">用于根据相关条件的值，有条件地执行多个执行路径之一。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-135">Used to conditionally execute one of several paths of execution, depending on the value of its associated conditions.</span></span>  
  
-   <span data-ttu-id="0f3f2-136">**延迟。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-136">**delay.**</span></span> <span data-ttu-id="0f3f2-137">用于等待一段时间，该时间可以是绝对时间，也可以是相对时间。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-137">Used to wait until an absolute time is reached or a relative time is reached.</span></span>  
  
-   <span data-ttu-id="0f3f2-138">**侦听。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-138">**listen.**</span></span> <span data-ttu-id="0f3f2-139">与**并行**语句，**侦听**语句具有多个执行分支的路径。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-139">As with a **parallel** statement, the **listen** statement has multiple paths of execution branches.</span></span> <span data-ttu-id="0f3f2-140">但是，分支必须以开头**延迟**语句或**接收**语句。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-140">However, the branches must begin with a **delay** statement or a **receive** statement.</span></span> <span data-ttu-id="0f3f2-141">只有接收第一个调用的分支将被执行。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-141">The branch that receives the first invocation is executed.</span></span> <span data-ttu-id="0f3f2-142">其他分支的**侦听**永远不会执行语句。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-142">The other branches of the **listen** statement are never executed.</span></span>  
  
-   <span data-ttu-id="0f3f2-143">**并行操作。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-143">**parallel actions.**</span></span> <span data-ttu-id="0f3f2-144">同时执行业务程序的多个分支。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-144">Executes multiple branches of a business process concurrently.</span></span> <span data-ttu-id="0f3f2-145">仅当所有分支都处理完成后，才执行 parallel 后面的语句。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-145">All branches must complete processing before any statements following the parallel statement are executed.</span></span>  
  
-   <span data-ttu-id="0f3f2-146">**循环。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-146">**loop.**</span></span> <span data-ttu-id="0f3f2-147">只要相关条件为 True，就不断重复执行。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-147">Repeatedly executes while its associated condition remains true.</span></span>  
  
-   <span data-ttu-id="0f3f2-148">**作用域。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-148">**scope.**</span></span> <span data-ttu-id="0f3f2-149">提供代码块的上下文，在该上下文中定义了应用到该代码块变量和事务性语义。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-149">Provides a context for a block of code that defines variables and transactional semantics that apply to that block of code.</span></span> <span data-ttu-id="0f3f2-150">变量的生存期可限制在该作用域内。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-150">Variable lifetime can be restricted to that scope.</span></span> <span data-ttu-id="0f3f2-151">可以将事务性语义（例如长期、原子或无）应用于作用域以影响其行为。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-151">Transactional semantics, such as long-running, atomic, or none can be applied to a scope to affect its behavior.</span></span>  
  
-   <span data-ttu-id="0f3f2-152">**引发异常。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-152">**throw exception.**</span></span> <span data-ttu-id="0f3f2-153">用于显式调用当前代码段中的异常/错误处理程序。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-153">Used to explicitly invoke an exception/fault handler in the current code block.</span></span>  
  
-   <span data-ttu-id="0f3f2-154">**补偿。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-154">**compensate.**</span></span> <span data-ttu-id="0f3f2-155">用于显式调用与给定作用域相关联的补偿模块。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-155">Used to explicitly invoke a compensation block associated with a given scope.</span></span> <span data-ttu-id="0f3f2-156">A**作用域**语句可能具有与之关联的一个或多个补偿块。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-156">A **scope** statement may have one or more compensation blocks associated with it.</span></span> <span data-ttu-id="0f3f2-157">**补偿**语句将重定向到所选的补偿块的执行。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-157">The **compensate** statement directs execution to the selected compensation block.</span></span>  
  
-   <span data-ttu-id="0f3f2-158">**挂起。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-158">**suspend.**</span></span> <span data-ttu-id="0f3f2-159">暂停进程的执行，但操作人员或应用程序可重新启动该进程。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-159">Temporarily halts execution of a process, but can be restarted by an operator or application.</span></span> <span data-ttu-id="0f3f2-160">与相关联的字符串表达式**终止**语句也会提供给运算符/管理员通过相应的日志，或通过用户界面。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-160">A string expression associated with the **terminate** statement is made available to operators/administrators through appropriate logs or through a user interface.</span></span>  
  
-   <span data-ttu-id="0f3f2-161">**终止。**</span><span class="sxs-lookup"><span data-stu-id="0f3f2-161">**terminate.**</span></span> <span data-ttu-id="0f3f2-162">强制停止计划中的所有处理任务，并且不可恢复。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-162">Forcibly and irrevocably stops all processing in a schedule.</span></span> <span data-ttu-id="0f3f2-163">与相关联的字符串表达式**终止**语句也会提供给操作员和管理员通过相应的日志，或通过用户界面。</span><span class="sxs-lookup"><span data-stu-id="0f3f2-163">A string expression associated with the **terminate** statement is made available to operators and administrators through appropriate logs or through a user interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f3f2-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f3f2-164">See Also</span></span>  
 <span data-ttu-id="0f3f2-165">[业务流程形状](../core/orchestration-shapes.md) </span><span class="sxs-lookup"><span data-stu-id="0f3f2-165">[Orchestration Shapes](../core/orchestration-shapes.md) </span></span>  
 <span data-ttu-id="0f3f2-166">[XLANG-s 数据类型](../core/xlang-s-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="0f3f2-166">[XLANG-s Data Types](../core/xlang-s-data-types.md) </span></span>  
 <span data-ttu-id="0f3f2-167">[XLANG-s 变量和运算符](../core/xlang-s-variables-and-operators.md) </span><span class="sxs-lookup"><span data-stu-id="0f3f2-167">[XLANG-s Variables and Operators](../core/xlang-s-variables-and-operators.md) </span></span>  
 <span data-ttu-id="0f3f2-168">[XLANG-s 表达式](../core/xlang-s-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="0f3f2-168">[XLANG-s Expressions](../core/xlang-s-expressions.md) </span></span>  
 <span data-ttu-id="0f3f2-169">[XLANG-s 保留字](../core/xlang-s-reserved-words.md) </span><span class="sxs-lookup"><span data-stu-id="0f3f2-169">[XLANG-s Reserved Words](../core/xlang-s-reserved-words.md) </span></span>  
 [<span data-ttu-id="0f3f2-170">XLANG-s 的 BPEL4WS 类型转换</span><span class="sxs-lookup"><span data-stu-id="0f3f2-170">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)