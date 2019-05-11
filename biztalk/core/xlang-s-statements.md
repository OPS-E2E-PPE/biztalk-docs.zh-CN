---
title: Xlang-s 语句 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 620d0452-a8da-4285-b8b2-5a932ffcde28
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d8abe5514d34bb8fdeb8e465c4c3f30278c4c6b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244096"
---
# <a name="xlang-s-statements"></a><span data-ttu-id="05984-102">Xlang-s 语句</span><span class="sxs-lookup"><span data-stu-id="05984-102">XLANG-s Statements</span></span>
<span data-ttu-id="05984-103">XLANG/s 语句通常分为两个类别之一： 简单语句，对其自身，例如**接收**或**发送**，并包含或组是简单的语句的复杂语句或其他复杂语句，如**作用域**，**并行**，并**侦听**。</span><span class="sxs-lookup"><span data-stu-id="05984-103">XLANG/s statements generally fall into one of two categories: simple statements that act on their own, such as **receive** or **send**, and complex statements that contain or group either simple statements or other complex statements, such as **scope**, **parallel**, and **listen**.</span></span> <span data-ttu-id="05984-104">每个语句对应于在 BizTalk 业务流程设计器中的业务流程形状。</span><span class="sxs-lookup"><span data-stu-id="05984-104">Each statement is corresponding to an orchestration shape in the BizTalk Orchestration Designer.</span></span> <span data-ttu-id="05984-105">XLANG/s 定义了以下语句：</span><span class="sxs-lookup"><span data-stu-id="05984-105">XLANG/s defines the following statements:</span></span>  
  
-   <span data-ttu-id="05984-106">**group.**</span><span class="sxs-lookup"><span data-stu-id="05984-106">**group.**</span></span> <span data-ttu-id="05984-107">为了方便使用将操作分组为单个可折叠或展开的单元。</span><span class="sxs-lookup"><span data-stu-id="05984-107">Used to group operations into a single collapsible and expandable unit for visual convenience.</span></span>  
  
-   <span data-ttu-id="05984-108">**send.**</span><span class="sxs-lookup"><span data-stu-id="05984-108">**send.**</span></span> <span data-ttu-id="05984-109">使用指定的消息发送到指定的端口。</span><span class="sxs-lookup"><span data-stu-id="05984-109">Used to send a specified message to a specified port.</span></span>  
  
-   <span data-ttu-id="05984-110">**receive.**</span><span class="sxs-lookup"><span data-stu-id="05984-110">**receive.**</span></span> <span data-ttu-id="05984-111">用于等待接收来自指定端口指定的消息。</span><span class="sxs-lookup"><span data-stu-id="05984-111">Used to wait for the receipt of a specified message from a specified port.</span></span>  
  
-   <span data-ttu-id="05984-112">**端口。**</span><span class="sxs-lookup"><span data-stu-id="05984-112">**port.**</span></span> <span data-ttu-id="05984-113">定义位置和方式传输消息。</span><span class="sxs-lookup"><span data-stu-id="05984-113">Defines where and how messages are transmitted.</span></span>  
  
-   <span data-ttu-id="05984-114">**角色链接。**</span><span class="sxs-lookup"><span data-stu-id="05984-114">**role link.**</span></span> <span data-ttu-id="05984-115">用来创建与同一个逻辑合作伙伴，可能通过不同的传输或终结点进行通信的端口的集合</span><span class="sxs-lookup"><span data-stu-id="05984-115">Used to create a collection of ports that communicate with the same logical partner, perhaps through different transports or endpoints</span></span>  
  
-   <span data-ttu-id="05984-116">**转换。**</span><span class="sxs-lookup"><span data-stu-id="05984-116">**transform.**</span></span> <span data-ttu-id="05984-117">用于将字段从现有消息映射到新消息。</span><span class="sxs-lookup"><span data-stu-id="05984-117">Used to map the fields from existing messages into new messages.</span></span>  
  
-   <span data-ttu-id="05984-118">**消息赋值。**</span><span class="sxs-lookup"><span data-stu-id="05984-118">**message assignment.**</span></span> <span data-ttu-id="05984-119">使用指定的消息发送到指定的端口。</span><span class="sxs-lookup"><span data-stu-id="05984-119">Used to send a specified message to a specified port.</span></span>  
  
-   <span data-ttu-id="05984-120">**构造消息。**</span><span class="sxs-lookup"><span data-stu-id="05984-120">**construct message.**</span></span> <span data-ttu-id="05984-121">定义其中一条消息是创建和初始化的 XLANG/s 代码的块。</span><span class="sxs-lookup"><span data-stu-id="05984-121">Defines a block of XLANG/s code where a message is created and initialized.</span></span> <span data-ttu-id="05984-122">现有的消息可以发送到 XLANG/s 程序，但不能构造外创建。</span><span class="sxs-lookup"><span data-stu-id="05984-122">Existing messages can be sent to an XLANG/s program, but cannot be created outside of a construct.</span></span> <span data-ttu-id="05984-123">此机制提供消息分发和提供丰富的消息跟踪，因为在所有已知消息状态时间。</span><span class="sxs-lookup"><span data-stu-id="05984-123">This mechanism provides for message distribution and rich message tracking, because a message state is known at all times.</span></span>  
  
-   <span data-ttu-id="05984-124">**调用业务流程。**</span><span class="sxs-lookup"><span data-stu-id="05984-124">**call orchestration.**</span></span> <span data-ttu-id="05984-125">以同步方式从一个业务流程调用另一个业务流程。</span><span class="sxs-lookup"><span data-stu-id="05984-125">Synchronously calls from one orchestration to another orchestration.</span></span> <span data-ttu-id="05984-126">可以传递参数，并将其返回。</span><span class="sxs-lookup"><span data-stu-id="05984-126">Parameters can be passed and returned.</span></span>  
  
-   <span data-ttu-id="05984-127">**启动业务流程。**</span><span class="sxs-lookup"><span data-stu-id="05984-127">**start orchestration.**</span></span> <span data-ttu-id="05984-128">用于启用您的业务流程以异步方式调用其他业务流程。</span><span class="sxs-lookup"><span data-stu-id="05984-128">Used to enable your orchestration to call another orchestration asynchronously.</span></span>  
  
-   <span data-ttu-id="05984-129">**调用规则。**</span><span class="sxs-lookup"><span data-stu-id="05984-129">**call rules.**</span></span> <span data-ttu-id="05984-130">可以配置业务规则策略以在您的业务流程中执行。</span><span class="sxs-lookup"><span data-stu-id="05984-130">Enables you to configure a Business Rules policy to be executed in your orchestration.</span></span>  
  
-   <span data-ttu-id="05984-131">**expression.**</span><span class="sxs-lookup"><span data-stu-id="05984-131">**expression.**</span></span> <span data-ttu-id="05984-132">XLANG/s 支持丰富的表达式语法，以支持各种使用方案所需的协议定义。</span><span class="sxs-lookup"><span data-stu-id="05984-132">XLANG/s supports rich expression syntax to support the wide variety of usage scenarios required for protocol definition.</span></span> <span data-ttu-id="05984-133">此语句用于分配端口属性、 服务链接属性、 消息、 变量和对象，并调用方法、 属性或静态数据字段。</span><span class="sxs-lookup"><span data-stu-id="05984-133">This statement is used to assign port properties, service-link properties, messages, variables, and objects, and to invoke methods, properties, or static data fields.</span></span>  
  
-   <span data-ttu-id="05984-134">**decide.**</span><span class="sxs-lookup"><span data-stu-id="05984-134">**decide.**</span></span> <span data-ttu-id="05984-135">用于有条件地执行多个路径的执行，具体取决于其关联的条件的值之一。</span><span class="sxs-lookup"><span data-stu-id="05984-135">Used to conditionally execute one of several paths of execution, depending on the value of its associated conditions.</span></span>  
  
-   <span data-ttu-id="05984-136">**delay.**</span><span class="sxs-lookup"><span data-stu-id="05984-136">**delay.**</span></span> <span data-ttu-id="05984-137">用于等待，直到达到一个绝对时间或相对时间。</span><span class="sxs-lookup"><span data-stu-id="05984-137">Used to wait until an absolute time is reached or a relative time is reached.</span></span>  
  
-   <span data-ttu-id="05984-138">**listen.**</span><span class="sxs-lookup"><span data-stu-id="05984-138">**listen.**</span></span> <span data-ttu-id="05984-139">如同**并行**语句**侦听**语句具有多个分支执行路径。</span><span class="sxs-lookup"><span data-stu-id="05984-139">As with a **parallel** statement, the **listen** statement has multiple paths of execution branches.</span></span> <span data-ttu-id="05984-140">但是，分支必须以开头**延迟**语句或**接收**语句。</span><span class="sxs-lookup"><span data-stu-id="05984-140">However, the branches must begin with a **delay** statement or a **receive** statement.</span></span> <span data-ttu-id="05984-141">执行接收第一次调用的分支。</span><span class="sxs-lookup"><span data-stu-id="05984-141">The branch that receives the first invocation is executed.</span></span> <span data-ttu-id="05984-142">其他分支**侦听**永远不会执行语句。</span><span class="sxs-lookup"><span data-stu-id="05984-142">The other branches of the **listen** statement are never executed.</span></span>  
  
-   <span data-ttu-id="05984-143">**并行操作。**</span><span class="sxs-lookup"><span data-stu-id="05984-143">**parallel actions.**</span></span> <span data-ttu-id="05984-144">同时执行多个分支的业务流程。</span><span class="sxs-lookup"><span data-stu-id="05984-144">Executes multiple branches of a business process concurrently.</span></span> <span data-ttu-id="05984-145">所有分支都处理并行语句后面的任何语句执行之前都完成。</span><span class="sxs-lookup"><span data-stu-id="05984-145">All branches must complete processing before any statements following the parallel statement are executed.</span></span>  
  
-   <span data-ttu-id="05984-146">**loop.**</span><span class="sxs-lookup"><span data-stu-id="05984-146">**loop.**</span></span> <span data-ttu-id="05984-147">重复执行，而其关联的条件将保持为 true。</span><span class="sxs-lookup"><span data-stu-id="05984-147">Repeatedly executes while its associated condition remains true.</span></span>  
  
-   <span data-ttu-id="05984-148">**scope.**</span><span class="sxs-lookup"><span data-stu-id="05984-148">**scope.**</span></span> <span data-ttu-id="05984-149">定义变量和将应用于该代码块中的事务性语义的代码块提供上下文。</span><span class="sxs-lookup"><span data-stu-id="05984-149">Provides a context for a block of code that defines variables and transactional semantics that apply to that block of code.</span></span> <span data-ttu-id="05984-150">变量的生存期可限制为该作用域。</span><span class="sxs-lookup"><span data-stu-id="05984-150">Variable lifetime can be restricted to that scope.</span></span> <span data-ttu-id="05984-151">事务性语义，如长时间运行，原子的或都不可以应用于一个作用域以影响其行为。</span><span class="sxs-lookup"><span data-stu-id="05984-151">Transactional semantics, such as long-running, atomic, or none can be applied to a scope to affect its behavior.</span></span>  
  
-   <span data-ttu-id="05984-152">**引发异常。**</span><span class="sxs-lookup"><span data-stu-id="05984-152">**throw exception.**</span></span> <span data-ttu-id="05984-153">用于显式调用当前代码块中的异常/错误处理程序。</span><span class="sxs-lookup"><span data-stu-id="05984-153">Used to explicitly invoke an exception/fault handler in the current code block.</span></span>  
  
-   <span data-ttu-id="05984-154">**补偿。**</span><span class="sxs-lookup"><span data-stu-id="05984-154">**compensate.**</span></span> <span data-ttu-id="05984-155">用于显式调用与给定作用域相关联的补偿模块。</span><span class="sxs-lookup"><span data-stu-id="05984-155">Used to explicitly invoke a compensation block associated with a given scope.</span></span> <span data-ttu-id="05984-156">一个**作用域**语句可能拥有与之关联的一个或多个补偿模块。</span><span class="sxs-lookup"><span data-stu-id="05984-156">A **scope** statement may have one or more compensation blocks associated with it.</span></span> <span data-ttu-id="05984-157">**补偿**语句将执行定向到所选的补偿模块。</span><span class="sxs-lookup"><span data-stu-id="05984-157">The **compensate** statement directs execution to the selected compensation block.</span></span>  
  
-   <span data-ttu-id="05984-158">**suspend.**</span><span class="sxs-lookup"><span data-stu-id="05984-158">**suspend.**</span></span> <span data-ttu-id="05984-159">暂时停止执行进程，但可以通过运算符或应用程序重新启动。</span><span class="sxs-lookup"><span data-stu-id="05984-159">Temporarily halts execution of a process, but can be restarted by an operator or application.</span></span> <span data-ttu-id="05984-160">与关联的字符串表达式**终止**语句可人员/管理员通过适当的日志或通过用户界面。</span><span class="sxs-lookup"><span data-stu-id="05984-160">A string expression associated with the **terminate** statement is made available to operators/administrators through appropriate logs or through a user interface.</span></span>  
  
-   <span data-ttu-id="05984-161">**终止。**</span><span class="sxs-lookup"><span data-stu-id="05984-161">**terminate.**</span></span> <span data-ttu-id="05984-162">强制，且不可撤销停止计划中的所有处理。</span><span class="sxs-lookup"><span data-stu-id="05984-162">Forcibly and irrevocably stops all processing in a schedule.</span></span> <span data-ttu-id="05984-163">与关联的字符串表达式**终止**语句可向操作员和管理员通过适当的日志或通过用户界面。</span><span class="sxs-lookup"><span data-stu-id="05984-163">A string expression associated with the **terminate** statement is made available to operators and administrators through appropriate logs or through a user interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05984-164">请参阅</span><span class="sxs-lookup"><span data-stu-id="05984-164">See Also</span></span>  
 <span data-ttu-id="05984-165">[业务流程形状](../core/orchestration-shapes.md) </span><span class="sxs-lookup"><span data-stu-id="05984-165">[Orchestration Shapes](../core/orchestration-shapes.md) </span></span>  
 <span data-ttu-id="05984-166">[Xlang-s 数据类型](../core/xlang-s-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="05984-166">[XLANG-s Data Types](../core/xlang-s-data-types.md) </span></span>  
 <span data-ttu-id="05984-167">[Xlang-s 变量和运算符](../core/xlang-s-variables-and-operators.md) </span><span class="sxs-lookup"><span data-stu-id="05984-167">[XLANG-s Variables and Operators](../core/xlang-s-variables-and-operators.md) </span></span>  
 <span data-ttu-id="05984-168">[Xlang-s 表达式](../core/xlang-s-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="05984-168">[XLANG-s Expressions](../core/xlang-s-expressions.md) </span></span>  
 <span data-ttu-id="05984-169">[Xlang-s 保留字](../core/xlang-s-reserved-words.md) </span><span class="sxs-lookup"><span data-stu-id="05984-169">[XLANG-s Reserved Words](../core/xlang-s-reserved-words.md) </span></span>  
 [<span data-ttu-id="05984-170">XLANG-s 到 BPEL4WS 的类型转换</span><span class="sxs-lookup"><span data-stu-id="05984-170">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)