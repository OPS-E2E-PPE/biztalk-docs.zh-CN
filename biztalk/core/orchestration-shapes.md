---
title: "业务流程形状 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Delay shape [Orchestration Designer]
- Loop shape [Orchestration Designer]
- Throw Exception shape [Orchestration Designer]
- Expression shape [Orchestration Designer]
- Decide shape [Orchestration Designer]
- Receive shape [Orchestration Designer]
- Compensate shape [Orchestration Designer]
- orchestrations, shapes
- Suspend shape [Orchestration Designer]
- Send shape [Orchestration Designer]
- Group shape [Orchestration Designer]
- Listen shape [Orchestration Designer]
- shapes, about shapes
- Construct Message shape [Orchestration Designer]
- Parallel Actions shape [Orchestration Designer]
- Call Rules shape [Orchestration Designer]
- Start Orchestration shape [Orchestration Designer]
- Transform shape [Orchestration Designer]
- Message Assignment shape [Orchestration Designer]
- Role Link shape [Orchestration Designer]
- Call Orchestration shape [Orchestration Designer]
- Port shape [Orchestration Designer]
- shapes
- Scope shape [Orchestration Designer]
- Terminate shape [Orchestration Designer]
- Orchestration Designer, shapes
- Insufficient Configuration Smart Tag [Orchestration Designer]
ms.assetid: a1d03baa-a267-499d-94fc-700b3e959458
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 181656208b757c595feb9d19ee786fe91f1b78f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-shapes"></a><span data-ttu-id="3eeb8-102">业务流程形状</span><span class="sxs-lookup"><span data-stu-id="3eeb8-102">Orchestration Shapes</span></span>
<span data-ttu-id="3eeb8-103">业务流程设计器是用于创建业务流程的可视工具。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-103">Orchestration Designer is a visual tool for creating orchestrations.</span></span> <span data-ttu-id="3eeb8-104">它提供了一些形状，可放在设计图面上作为底层操作的可视表示形式，这些形状可以帮助你有效地设计和实施业务流程。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-104">It provides several shapes that you can place on the design surface as visual representations of underlying actions, and they can help you to efficiently design and implement an orchestration.</span></span>  
  
 <span data-ttu-id="3eeb8-105">**缺少配置操作**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-105">**Insufficient Configuration Action**</span></span>  
  
 ![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")  
  
> [!NOTE]
>  <span data-ttu-id="3eeb8-106">当业务流程设计器检测到相关联的形状没有完全配置时，“不完全的配置操作”就会显示在业务流程设计器中。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-106">The Insufficient Configuration Action is displayed in the Orchestration designer when the Orchestration Designer detects that the associated shape is not completely configured.</span></span> <span data-ttu-id="3eeb8-107">如果业务流程中的形状没有完全配置，则关联的业务流程将不进行编译。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-107">If a shape in an Orchestration is not completely configured then the associated Orchestration will not compile.</span></span>  
  
 <span data-ttu-id="3eeb8-108">下表列出了可用形状，并提供了每个形状的功能的简要说明。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-108">The following table lists the available shapes, along with a brief description of the function of each shape.</span></span>  
  
|<span data-ttu-id="3eeb8-109">形状</span><span class="sxs-lookup"><span data-stu-id="3eeb8-109">Shape</span></span>|<span data-ttu-id="3eeb8-110">形状名称</span><span class="sxs-lookup"><span data-stu-id="3eeb8-110">Shape Name</span></span>|<span data-ttu-id="3eeb8-111">用途</span><span class="sxs-lookup"><span data-stu-id="3eeb8-111">Purpose</span></span>|  
|-----------|----------------|-------------|  
|![](../core/media/ebiz-orch-callorchestrat.gif "ebiz_orch_callorchestrat")|<span data-ttu-id="3eeb8-112">**调用业务流程**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-112">**Call Orchestration**</span></span>|<span data-ttu-id="3eeb8-113">允许业务流程同步调用其他业务流程。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-113">Enables your orchestration to call another orchestration synchronously.</span></span>|  
|![](../core/media/ebiz-orch-call-rules.gif "ebiz_orch_call_rules")|<span data-ttu-id="3eeb8-114">**调用规则**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-114">**Call Rules**</span></span>|<span data-ttu-id="3eeb8-115">允许你配置要在业务流程中执行的业务规则策略。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-115">Enables you to configure a Business Rules policy to be executed in your orchestration.</span></span>|  
|![](../core/media/ebiz-orch-compensate.gif "ebiz_orch_compensate")|<span data-ttu-id="3eeb8-116">**补偿**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-116">**Compensate**</span></span>|<span data-ttu-id="3eeb8-117">允许你调用代码以在发生错误时对业务流程已执行的操作进行撤消或补偿。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-117">Enables you to call code to undo or compensate for operations already performed by the orchestration when an error occurs.</span></span>|  
|![](../core/media/ebiz-orch-constructmsg.gif "ebiz_orch_constructmsg")|<span data-ttu-id="3eeb8-118">**构造消息**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-118">**Construct Message**</span></span>|<span data-ttu-id="3eeb8-119">允许构造消息。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-119">Enables you to construct a message.</span></span>|  
|![](../core/media/ebiz-orch-decide.gif "ebiz_orch_decide")|<span data-ttu-id="3eeb8-120">**决定**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-120">**Decide**</span></span>|<span data-ttu-id="3eeb8-121">允许你在业务流程中有条件地进行分支。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-121">Enables you to conditionally branch in your orchestration.</span></span>|  
|![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")|<span data-ttu-id="3eeb8-122">**延迟**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-122">**Delay**</span></span>|<span data-ttu-id="3eeb8-123">允许你根据超时间隔在业务流程中设置延迟。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-123">Enables you to build delays in your orchestration based on a time-out interval.</span></span>|  
|![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")|<span data-ttu-id="3eeb8-124">**表达式**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-124">**Expression**</span></span>|<span data-ttu-id="3eeb8-125">允许你将值赋给变量或进行 .NET 调用。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-125">Enables you to assign values to variables or make .NET calls.</span></span>|  
|![](../core/media/ebiz-orch-group.gif "ebiz_orch_group")|<span data-ttu-id="3eeb8-126">**分组**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-126">**Group**</span></span>|<span data-ttu-id="3eeb8-127">允许你将操作分组为单个可折叠或展开的单元，以便于查看。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-127">Enables you to group operations into a single collapsible and expandable unit for visual convenience.</span></span>|  
|![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")|<span data-ttu-id="3eeb8-128">**侦听**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-128">**Listen**</span></span>|<span data-ttu-id="3eeb8-129">允许业务流程根据收到的消息或超时到期情况有条件地进行分支。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-129">Enables your orchestration to conditionally branch depending on messages received or the expiration of a timeout period.</span></span>|  
|![](../core/media/ebiz-orch-loop.gif "ebiz_orch_loop")|<span data-ttu-id="3eeb8-130">**循环**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-130">**Loop**</span></span>|<span data-ttu-id="3eeb8-131">允许业务流程在满足条件之前进行循环。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-131">Enables your orchestration to loop until a condition is met.</span></span>|  
|![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")|<span data-ttu-id="3eeb8-132">**消息赋值**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-132">**Message Assignment**</span></span>|<span data-ttu-id="3eeb8-133">允许分配消息值。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-133">Enables you to assign message values.</span></span>|  
|![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")|<span data-ttu-id="3eeb8-134">**并行操作**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-134">**Parallel Actions**</span></span>|<span data-ttu-id="3eeb8-135">允许业务流程相互独立地执行两个或更多操作。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-135">Enables your orchestration to perform two or more operations independently of each other.</span></span>|  
|![](../core/media/ebiz-orch-port.gif "ebiz_orch_port")|<span data-ttu-id="3eeb8-136">**端口**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-136">**Port**</span></span>|<span data-ttu-id="3eeb8-137">定义传输消息的位置和方式。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-137">Defines where and how messages are transmitted.</span></span>|  
|![](../core/media/ebiz-orch-receive.gif "ebiz_orch_receive")|<span data-ttu-id="3eeb8-138">**接收**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-138">**Receive**</span></span>|<span data-ttu-id="3eeb8-139">允许你在业务流程中接收消息。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-139">Enables you to receive a message in your orchestration.</span></span>|  
|![](../core/media/ebiz-orch-rolelink.gif "ebiz_orch_rolelink")|<span data-ttu-id="3eeb8-140">**角色链接**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-140">**Role Link**</span></span>|<span data-ttu-id="3eeb8-141">允许你创建一个端口集合，以与同一个逻辑合作伙伴进行通信（可能通过不同的传输或端点）。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-141">Enables you to create a collection of ports that communicate with the same logical partner, perhaps through different transports or endpoints.</span></span>|  
|![](../core/media/ebiz-orch-scope.gif "ebiz_orch_scope")|<span data-ttu-id="3eeb8-142">**范围**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-142">**Scope**</span></span>|<span data-ttu-id="3eeb8-143">为事务和异常处理提供框架。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-143">Provides a framework for transactions and exception handling.</span></span>|  
|![](../core/media/ebiz-orch-send.gif "ebiz_orch_send")|<span data-ttu-id="3eeb8-144">**发送**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-144">**Send**</span></span>|<span data-ttu-id="3eeb8-145">允许你从业务流程发送消息。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-145">Enables you to send a message from your orchestration.</span></span>|  
|![](../core/media/ebiz-orch-strtorchestrat.gif "ebiz_orch_strtorchestrat")|<span data-ttu-id="3eeb8-146">**启动业务流程**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-146">**Start Orchestration**</span></span>|<span data-ttu-id="3eeb8-147">允许业务流程异步调用其他业务流程。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-147">Enables your orchestration to call another orchestration asynchronously.</span></span>|  
|![](../core/media/ebiz-orch-suspend.gif "ebiz_orch_suspend")|<span data-ttu-id="3eeb8-148">**挂起**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-148">**Suspend**</span></span>|<span data-ttu-id="3eeb8-149">挂起业务流程的操作，以便在出现某个错误条件时可以进行干预。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-149">Suspends the operation of your orchestration to enable intervention in the event of some error condition.</span></span>|  
|![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")|<span data-ttu-id="3eeb8-150">**终止**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-150">**Terminate**</span></span>|<span data-ttu-id="3eeb8-151">允许你在出现某个错误条件时立即结束业务流程的操作。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-151">Enables you to immediately end the operation of your orchestration in the event of some error condition.</span></span>|  
|![](../core/media/ebiz-orch-throwexcept.gif "ebiz_orch_throwexcept")|<span data-ttu-id="3eeb8-152">**引发异常**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-152">**Throw Exception**</span></span>|<span data-ttu-id="3eeb8-153">允许你在错误事件中显式引发异常。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-153">Enables you to explicitly throw an exception in the event of an error.</span></span>|  
|![](../core/media/ebiz-orch-transform.gif "ebiz_orch_transform")|<span data-ttu-id="3eeb8-154">**转换**</span><span class="sxs-lookup"><span data-stu-id="3eeb8-154">**Transform**</span></span>|<span data-ttu-id="3eeb8-155">允许你将字段从现有消息映射到新消息。</span><span class="sxs-lookup"><span data-stu-id="3eeb8-155">Enables you to map the fields from existing messages into new messages.</span></span>|