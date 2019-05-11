---
title: 业务流程形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ad225737b806991a0633019dcf91b683f726bca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322632"
---
# <a name="orchestration-shapes"></a><span data-ttu-id="dfb5b-102">业务流程形状</span><span class="sxs-lookup"><span data-stu-id="dfb5b-102">Orchestration Shapes</span></span>
<span data-ttu-id="dfb5b-103">业务流程设计器是一种可视化工具用于创建业务流程。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-103">Orchestration Designer is a visual tool for creating orchestrations.</span></span> <span data-ttu-id="dfb5b-104">它提供了多个形状，可以将它们放在设计图面上作为底层操作的可视表示形式，它们可帮助您可以有效地设计和实现业务流程。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-104">It provides several shapes that you can place on the design surface as visual representations of underlying actions, and they can help you to efficiently design and implement an orchestration.</span></span>  
  
 <span data-ttu-id="dfb5b-105">**缺少配置的操作**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-105">**Insufficient Configuration Action**</span></span>  
  
 <span data-ttu-id="dfb5b-106">![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-106">![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfb5b-107">当业务流程设计器检测到相关联的形状没有完全配置时，将在业务流程设计器中显示完全的配置操作。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-107">The Insufficient Configuration Action is displayed in the Orchestration designer when the Orchestration Designer detects that the associated shape is not completely configured.</span></span> <span data-ttu-id="dfb5b-108">如果业务流程中的形状没有完全配置关联的业务流程将不编译。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-108">If a shape in an Orchestration is not completely configured then the associated Orchestration will not compile.</span></span>  
  
 <span data-ttu-id="dfb5b-109">下表列出了可用形状，以及每个形状的函数的简要说明。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-109">The following table lists the available shapes, along with a brief description of the function of each shape.</span></span>  
  
|<span data-ttu-id="dfb5b-110">形状</span><span class="sxs-lookup"><span data-stu-id="dfb5b-110">Shape</span></span>|<span data-ttu-id="dfb5b-111">形状的名称</span><span class="sxs-lookup"><span data-stu-id="dfb5b-111">Shape Name</span></span>|<span data-ttu-id="dfb5b-112">用途</span><span class="sxs-lookup"><span data-stu-id="dfb5b-112">Purpose</span></span>|  
|-----------|----------------|-------------|  
|<span data-ttu-id="dfb5b-113">![](../core/media/ebiz-orch-callorchestrat.gif "ebiz_orch_callorchestrat")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-113">![](../core/media/ebiz-orch-callorchestrat.gif "ebiz_orch_callorchestrat")</span></span>|<span data-ttu-id="dfb5b-114">**调用业务流程**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-114">**Call Orchestration**</span></span>|<span data-ttu-id="dfb5b-115">允许业务流程同步调用另一个业务流程。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-115">Enables your orchestration to call another orchestration synchronously.</span></span>|  
|<span data-ttu-id="dfb5b-116">![](../core/media/ebiz-orch-call-rules.gif "ebiz_orch_call_rules")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-116">![](../core/media/ebiz-orch-call-rules.gif "ebiz_orch_call_rules")</span></span>|<span data-ttu-id="dfb5b-117">**调用规则**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-117">**Call Rules**</span></span>|<span data-ttu-id="dfb5b-118">可以配置业务规则策略以在您的业务流程中执行。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-118">Enables you to configure a Business Rules policy to be executed in your orchestration.</span></span>|  
|<span data-ttu-id="dfb5b-119">![](../core/media/ebiz-orch-compensate.gif "ebiz_orch_compensate")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-119">![](../core/media/ebiz-orch-compensate.gif "ebiz_orch_compensate")</span></span>|<span data-ttu-id="dfb5b-120">**补偿**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-120">**Compensate**</span></span>|<span data-ttu-id="dfb5b-121">可以调用撤消或补偿发生错误时由业务流程已执行的操作的代码。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-121">Enables you to call code to undo or compensate for operations already performed by the orchestration when an error occurs.</span></span>|  
|<span data-ttu-id="dfb5b-122">![](../core/media/ebiz-orch-constructmsg.gif "ebiz_orch_constructmsg")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-122">![](../core/media/ebiz-orch-constructmsg.gif "ebiz_orch_constructmsg")</span></span>|<span data-ttu-id="dfb5b-123">**构造消息**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-123">**Construct Message**</span></span>|<span data-ttu-id="dfb5b-124">使您可以构造一条消息。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-124">Enables you to construct a message.</span></span>|  
|<span data-ttu-id="dfb5b-125">![](../core/media/ebiz-orch-decide.gif "ebiz_orch_decide")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-125">![](../core/media/ebiz-orch-decide.gif "ebiz_orch_decide")</span></span>|<span data-ttu-id="dfb5b-126">**决定**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-126">**Decide**</span></span>|<span data-ttu-id="dfb5b-127">可以在业务流程中有条件地分支。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-127">Enables you to conditionally branch in your orchestration.</span></span>|  
|<span data-ttu-id="dfb5b-128">![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-128">![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")</span></span>|<span data-ttu-id="dfb5b-129">**Delay**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-129">**Delay**</span></span>|<span data-ttu-id="dfb5b-130">可以根据超时间隔在业务流程中设置延迟。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-130">Enables you to build delays in your orchestration based on a time-out interval.</span></span>|  
|<span data-ttu-id="dfb5b-131">![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-131">![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")</span></span>|<span data-ttu-id="dfb5b-132">**表达式**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-132">**Expression**</span></span>|<span data-ttu-id="dfb5b-133">可以将值分配给变量或进行.NET 调用。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-133">Enables you to assign values to variables or make .NET calls.</span></span>|  
|<span data-ttu-id="dfb5b-134">![](../core/media/ebiz-orch-group.gif "ebiz_orch_group")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-134">![](../core/media/ebiz-orch-group.gif "ebiz_orch_group")</span></span>|<span data-ttu-id="dfb5b-135">**分组**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-135">**Group**</span></span>|<span data-ttu-id="dfb5b-136">可以将操作分组为单个可折叠或展开的单元以便于查看。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-136">Enables you to group operations into a single collapsible and expandable unit for visual convenience.</span></span>|  
|<span data-ttu-id="dfb5b-137">![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-137">![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")</span></span>|<span data-ttu-id="dfb5b-138">**Listen**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-138">**Listen**</span></span>|<span data-ttu-id="dfb5b-139">允许业务流程到有条件地根据收到的消息的分支或超时期限过期。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-139">Enables your orchestration to conditionally branch depending on messages received or the expiration of a timeout period.</span></span>|  
|<span data-ttu-id="dfb5b-140">![](../core/media/ebiz-orch-loop.gif "ebiz_orch_loop")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-140">![](../core/media/ebiz-orch-loop.gif "ebiz_orch_loop")</span></span>|<span data-ttu-id="dfb5b-141">**Loop**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-141">**Loop**</span></span>|<span data-ttu-id="dfb5b-142">允许业务流程以循环播放，直到满足某个条件。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-142">Enables your orchestration to loop until a condition is met.</span></span>|  
|<span data-ttu-id="dfb5b-143">![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-143">![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")</span></span>|<span data-ttu-id="dfb5b-144">**消息赋值**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-144">**Message Assignment**</span></span>|<span data-ttu-id="dfb5b-145">可以分配消息值。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-145">Enables you to assign message values.</span></span>|  
|<span data-ttu-id="dfb5b-146">![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-146">![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")</span></span>|<span data-ttu-id="dfb5b-147">**并行操作**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-147">**Parallel Actions**</span></span>|<span data-ttu-id="dfb5b-148">允许业务流程执行各自独立的两个或多个操作。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-148">Enables your orchestration to perform two or more operations independently of each other.</span></span>|  
|<span data-ttu-id="dfb5b-149">![](../core/media/ebiz-orch-port.gif "ebiz_orch_port")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-149">![](../core/media/ebiz-orch-port.gif "ebiz_orch_port")</span></span>|<span data-ttu-id="dfb5b-150">**端口**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-150">**Port**</span></span>|<span data-ttu-id="dfb5b-151">定义位置和方式传输消息。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-151">Defines where and how messages are transmitted.</span></span>|  
|<span data-ttu-id="dfb5b-152">![](../core/media/ebiz-orch-receive.gif "ebiz_orch_receive")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-152">![](../core/media/ebiz-orch-receive.gif "ebiz_orch_receive")</span></span>|<span data-ttu-id="dfb5b-153">**Receive**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-153">**Receive**</span></span>|<span data-ttu-id="dfb5b-154">可以在业务流程中收到一条消息。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-154">Enables you to receive a message in your orchestration.</span></span>|  
|<span data-ttu-id="dfb5b-155">![](../core/media/ebiz-orch-rolelink.gif "ebiz_orch_rolelink")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-155">![](../core/media/ebiz-orch-rolelink.gif "ebiz_orch_rolelink")</span></span>|<span data-ttu-id="dfb5b-156">**角色链接**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-156">**Role Link**</span></span>|<span data-ttu-id="dfb5b-157">可以使用同一个逻辑合作伙伴，可能通过不同的传输或终结点创建的端口进行通信的集合。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-157">Enables you to create a collection of ports that communicate with the same logical partner, perhaps through different transports or endpoints.</span></span>|  
|<span data-ttu-id="dfb5b-158">![](../core/media/ebiz-orch-scope.gif "ebiz_orch_scope")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-158">![](../core/media/ebiz-orch-scope.gif "ebiz_orch_scope")</span></span>|<span data-ttu-id="dfb5b-159">**范围**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-159">**Scope**</span></span>|<span data-ttu-id="dfb5b-160">用于事务和异常处理提供了一个框架。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-160">Provides a framework for transactions and exception handling.</span></span>|  
|<span data-ttu-id="dfb5b-161">![](../core/media/ebiz-orch-send.gif "ebiz_orch_send")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-161">![](../core/media/ebiz-orch-send.gif "ebiz_orch_send")</span></span>|<span data-ttu-id="dfb5b-162">**Send**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-162">**Send**</span></span>|<span data-ttu-id="dfb5b-163">可以从您的业务流程发送消息。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-163">Enables you to send a message from your orchestration.</span></span>|  
|<span data-ttu-id="dfb5b-164">![](../core/media/ebiz-orch-strtorchestrat.gif "ebiz_orch_strtorchestrat")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-164">![](../core/media/ebiz-orch-strtorchestrat.gif "ebiz_orch_strtorchestrat")</span></span>|<span data-ttu-id="dfb5b-165">**启动业务流程**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-165">**Start Orchestration**</span></span>|<span data-ttu-id="dfb5b-166">允许业务流程以异步方式调用其他业务流程。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-166">Enables your orchestration to call another orchestration asynchronously.</span></span>|  
|<span data-ttu-id="dfb5b-167">![](../core/media/ebiz-orch-suspend.gif "ebiz_orch_suspend")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-167">![](../core/media/ebiz-orch-suspend.gif "ebiz_orch_suspend")</span></span>|<span data-ttu-id="dfb5b-168">**挂起**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-168">**Suspend**</span></span>|<span data-ttu-id="dfb5b-169">挂起业务流程以便能够出现某些错误条件时进行干预的操作。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-169">Suspends the operation of your orchestration to enable intervention in the event of some error condition.</span></span>|  
|<span data-ttu-id="dfb5b-170">![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-170">![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")</span></span>|<span data-ttu-id="dfb5b-171">**终止**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-171">**Terminate**</span></span>|<span data-ttu-id="dfb5b-172">使您能够立即结束出现某些错误条件时业务流程的操作。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-172">Enables you to immediately end the operation of your orchestration in the event of some error condition.</span></span>|  
|<span data-ttu-id="dfb5b-173">![](../core/media/ebiz-orch-throwexcept.gif "ebiz_orch_throwexcept")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-173">![](../core/media/ebiz-orch-throwexcept.gif "ebiz_orch_throwexcept")</span></span>|<span data-ttu-id="dfb5b-174">**引发异常**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-174">**Throw Exception**</span></span>|<span data-ttu-id="dfb5b-175">可以显式引发异常发生错误时。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-175">Enables you to explicitly throw an exception in the event of an error.</span></span>|  
|<span data-ttu-id="dfb5b-176">![](../core/media/ebiz-orch-transform.gif "ebiz_orch_transform")</span><span class="sxs-lookup"><span data-stu-id="dfb5b-176">![](../core/media/ebiz-orch-transform.gif "ebiz_orch_transform")</span></span>|<span data-ttu-id="dfb5b-177">**转换**</span><span class="sxs-lookup"><span data-stu-id="dfb5b-177">**Transform**</span></span>|<span data-ttu-id="dfb5b-178">可以将字段从现有消息映射到新消息。</span><span class="sxs-lookup"><span data-stu-id="dfb5b-178">Enables you to map the fields from existing messages into new messages.</span></span>|