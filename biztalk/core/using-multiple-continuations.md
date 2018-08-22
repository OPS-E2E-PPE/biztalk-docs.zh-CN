---
title: 使用多个继续符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01a38087-71ee-40b3-a957-6a2653bd6435
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78468438dbd04583f8936bab28e80bf400e83d72
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987134"
---
# <a name="using-multiple-continuations"></a><span data-ttu-id="75f8b-102">使用多个继续符</span><span class="sxs-lookup"><span data-stu-id="75f8b-102">Using Multiple Continuations</span></span>
<span data-ttu-id="75f8b-103">在有多个活动的环境中使用跟踪配置文件编辑器 (TPE)，您需要知道在哪些情况下跟踪活动，这是为了以正确的顺序映射接收端口、业务流程和发送端口。</span><span class="sxs-lookup"><span data-stu-id="75f8b-103">Using the Tracking Profile Editor (TPE) in environments in which there are multiple activities requires that you understand the scenario in which the activities are being tracked in order to map the receive ports, orchestrations, and send ports in the proper sequence.</span></span>  
  
 <span data-ttu-id="75f8b-104">在跟踪配置文件中，TPE 自动计算活动的开始和结束时间。</span><span class="sxs-lookup"><span data-stu-id="75f8b-104">In a tracking profile, the TPE assesses the beginning and end of the activity automatically.</span></span> <span data-ttu-id="75f8b-105">活动在开始收集数据时开始，在收集完数据后结束。</span><span class="sxs-lookup"><span data-stu-id="75f8b-105">The activity starts when the first piece of data is collected and ends when the last piece is collected.</span></span>  
  
 <span data-ttu-id="75f8b-106">大多数情况下，创建单个继续符（如两个业务流程之间的继续符）对开发人员来说很简单。</span><span class="sxs-lookup"><span data-stu-id="75f8b-106">In most cases creating a single continuation, such as a continuation between two orchestrations, is a straightforward process for developers.</span></span> <span data-ttu-id="75f8b-107">在存在多个继续符的情况下，使用 TPE 将很复杂。</span><span class="sxs-lookup"><span data-stu-id="75f8b-107">Where TPE exhibits complexity is in the case of multiple continuations.</span></span> <span data-ttu-id="75f8b-108">在存在多个继续符的方案中，业务活动监视 (BAM) 活动跨越多个接收端口、业务流程和发送端口。</span><span class="sxs-lookup"><span data-stu-id="75f8b-108">A multiple continuation scenario  is where a Business Activity Monitoring (BAM) activity spans multiple receive ports, orchestrations, and send ports.</span></span> <span data-ttu-id="75f8b-109">为了将 BAM 数据收集在一个记录中，必须在所有 BizTalk Server 计划之间创建继续符。</span><span class="sxs-lookup"><span data-stu-id="75f8b-109">In order to collect the BAM data in one record, you must create continuations between all the BizTalk Server schedules.</span></span> <span data-ttu-id="75f8b-110">使用 TPE 用户界面 (UI) 完成这个过程可能很复杂。</span><span class="sxs-lookup"><span data-stu-id="75f8b-110">This process can be complex when completed through the TPE user interface (UI).</span></span>  
  
 <span data-ttu-id="75f8b-111">本主题介绍如何在不同的方案中创建单个和多个继续符。</span><span class="sxs-lookup"><span data-stu-id="75f8b-111">This topic describes how to create single and multiple continuations in different scenarios.</span></span>  
  
#### <a name="base-scenario-description---multiple-receive-ports-orchestrations-and-send-ports"></a><span data-ttu-id="75f8b-112">基本方案描述 - 多个接收端口、业务流程和发送端口</span><span class="sxs-lookup"><span data-stu-id="75f8b-112">Base Scenario Description - Multiple Receive Ports, Orchestrations, and Send Ports</span></span>  
 <span data-ttu-id="75f8b-113">该方案由具有多个接收端口 (R)、业务流程 (O) 和发送端口 (S) 的 BizTalk Server 组成。</span><span class="sxs-lookup"><span data-stu-id="75f8b-113">The scenario consists of a BizTalk server that has a number of receive ports (R), orchestrations (O), and send ports (S).</span></span> <span data-ttu-id="75f8b-114">有一个常规 interchangeID 上下文属性用于链接继续符。</span><span class="sxs-lookup"><span data-stu-id="75f8b-114">There is a generic interchangeID context property that is used to link the continuations.</span></span> <span data-ttu-id="75f8b-115">您可以使用任何上下文属性，如 activityID 或其他唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="75f8b-115">You can use any context property, such as the activityID or other unique identifier.</span></span> <span data-ttu-id="75f8b-116">具体内容的选择不在这个方案的论述范围之内。</span><span class="sxs-lookup"><span data-stu-id="75f8b-116">The choice of the specific content is not germane to the discussion of the scenario.</span></span>  
  
 <span data-ttu-id="75f8b-117">此方案不论述从这些端口和业务流程跟踪的具体数据项/里程碑/上下文属性值。</span><span class="sxs-lookup"><span data-stu-id="75f8b-117">For the purposes of the scenario, discussions of the data item/milestone/context-property-value being tracked from these ports and orchestrations are not specified.</span></span> <span data-ttu-id="75f8b-118">那部分映射是特定于业务逻辑的。</span><span class="sxs-lookup"><span data-stu-id="75f8b-118">That part of the mapping is specific to the business logic.</span></span> <span data-ttu-id="75f8b-119">本方案的目的是捕获来自所有端口和业务流程的所有 BAM 数据，在已完成的活动表中将它们存入一行。</span><span class="sxs-lookup"><span data-stu-id="75f8b-119">The goal is to capture all BAM data from all the ports and orchestrations in a single row in the completed activity table.</span></span> <span data-ttu-id="75f8b-120">业务流程接收和处理消息的不同方式形成了一些有意义的挑战和解决方案。</span><span class="sxs-lookup"><span data-stu-id="75f8b-120">The different ways in which a message can be received and processed by orchestrations presents some interesting challenges and solutions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75f8b-121">可以将只有一个端口或一个业务流程的方案看作具有多个端口和多个业务流程方案的一种特例。</span><span class="sxs-lookup"><span data-stu-id="75f8b-121">The scenario of one port or one orchestration can be considered a special case of the many port and many orchestrations scenario.</span></span>  
  
#### <a name="scenario-solution-1---one-receive-port-and-one-orchestration"></a><span data-ttu-id="75f8b-122">解决方案 1 - 一个接收端口和一个业务流程</span><span class="sxs-lookup"><span data-stu-id="75f8b-122">Scenario Solution 1 - One Receive Port and One Orchestration</span></span>  
 <span data-ttu-id="75f8b-123">在此方案中，消息只发送到一个接收端口 (R1)，并且仅由一个业务流程 (O1) 处理。</span><span class="sxs-lookup"><span data-stu-id="75f8b-123">In this scenario, a message arrives at exactly one of the receive ports (R1) and is processed by exactly one of the orchestrations (O1).</span></span>  
  
 <span data-ttu-id="75f8b-124">继续符的创建过程如下：</span><span class="sxs-lookup"><span data-stu-id="75f8b-124">The process to create the continuation is as follows:</span></span>  
  
1. <span data-ttu-id="75f8b-125">在跟踪配置文件的文件夹活动树视图中创建一个继续符。</span><span class="sxs-lookup"><span data-stu-id="75f8b-125">Create a continuation in the folder activity tree view of the tracking profile.</span></span>  
  
2. <span data-ttu-id="75f8b-126">通过单击来选择上下文属性架构**选择事件源**按钮，，然后单击**选择上下文属性**菜单项。</span><span class="sxs-lookup"><span data-stu-id="75f8b-126">Choose the context property schema by clicking the **Select Event Source** button, and then clicking the **Select Context Property** menu item.</span></span>  
  
3. <span data-ttu-id="75f8b-127">找到**interchangeId 属性**中**上下文属性名称**列表，并选择它。</span><span class="sxs-lookup"><span data-stu-id="75f8b-127">Locate the **interchangeId property** in the **Context Property Name** list, and then select it.</span></span>  
  
4. <span data-ttu-id="75f8b-128">将 interchangeID 从属性架构映射到刚创建的继续符文件夹。</span><span class="sxs-lookup"><span data-stu-id="75f8b-128">From the property schema, map the interchangeID to the continuation folder that you just created.</span></span>  
  
5. <span data-ttu-id="75f8b-129">右键单击活动树中新创建的 interchangeID 节点，然后选择映射自哪些端口。</span><span class="sxs-lookup"><span data-stu-id="75f8b-129">Right-click the newly created interchangeID node in the activity tree, and then select the ports from which to map.</span></span>  
  
6. <span data-ttu-id="75f8b-130">在中**选择端口**将显示的对话框中选择所有**N**接收端口。</span><span class="sxs-lookup"><span data-stu-id="75f8b-130">In the **Select Ports** dialog box that is displayed, select all **N** receive ports.</span></span>  
  
7. <span data-ttu-id="75f8b-131">在文件夹活动树中创建 continuationID 文件夹。</span><span class="sxs-lookup"><span data-stu-id="75f8b-131">Create a continuationID folder in the folder activity tree.</span></span>  
  
8. <span data-ttu-id="75f8b-132">通过单击打开每个业务流程**选择事件源**按钮，，然后单击**选择业务流程计划**菜单项。</span><span class="sxs-lookup"><span data-stu-id="75f8b-132">Open each orchestration by clicking the **Select Event Source** button, and then clicking the **Select Orchestration Schedule** menu item.</span></span> <span data-ttu-id="75f8b-133">对每个业务流程，右键单击业务流程中的形状，然后将 interchangeID 上下文属性映射到新创建的 continuationID。</span><span class="sxs-lookup"><span data-stu-id="75f8b-133">From each orchestration, right-click a shape in the orchestration, and then map the interchangeID context property to the newly created continuationID.</span></span>  
  
   <span data-ttu-id="75f8b-134">在具有三个业务流程的部署中，跟踪配置文件如下所示：</span><span class="sxs-lookup"><span data-stu-id="75f8b-134">In a deployment with three orchestrations, your tracking profile would look similar to this:</span></span>  
  
   <span data-ttu-id="75f8b-135">![TPE 多继续符方案 1](../core/media/4761d680-7218-4404-a636-06739f70f344.gif "4761d680-7218-4404-a636-06739f70f344")</span><span class="sxs-lookup"><span data-stu-id="75f8b-135">![TPE multiple continuation scenario 1](../core/media/4761d680-7218-4404-a636-06739f70f344.gif "4761d680-7218-4404-a636-06739f70f344")</span></span>  
  
#### <a name="scenario-solution-2---one-receive-port-and-multiple-orchestrations"></a><span data-ttu-id="75f8b-136">解决方案 2 - 一个接收端口和多个业务流程</span><span class="sxs-lookup"><span data-stu-id="75f8b-136">Scenario Solution 2 - One Receive Port and Multiple Orchestrations</span></span>  
 <span data-ttu-id="75f8b-137">在此方案中，消息只发送到一个接收端口，然后由每个业务流程分别处理。</span><span class="sxs-lookup"><span data-stu-id="75f8b-137">In this scenario, a message arrives at exactly one of the receive ports and is processed by each and every orchestration.</span></span> <span data-ttu-id="75f8b-138">这发生在消息同时发送到每个业务流程时。</span><span class="sxs-lookup"><span data-stu-id="75f8b-138">This happens as the message is simultaneously sent to each of the orchestrations.</span></span>  
  
 <span data-ttu-id="75f8b-139">在这种情况下，我们需要为每个业务流程创建继续符和 continuationID。</span><span class="sxs-lookup"><span data-stu-id="75f8b-139">In this case, we would need a continuation and continuationID for each orchestration.</span></span> <span data-ttu-id="75f8b-140">创建继续符的过程将类似于解决方案 1 中所述的步骤。</span><span class="sxs-lookup"><span data-stu-id="75f8b-140">The process for creating the continuations would be similar to the steps outlined in scenario solution 1.</span></span> <span data-ttu-id="75f8b-141">对于三个业务流程部署，产生的跟踪配置文件如下所示：</span><span class="sxs-lookup"><span data-stu-id="75f8b-141">For a three-orchestration deployment, your resulting tracking profile looks something like this:</span></span>  
  
 <span data-ttu-id="75f8b-142">![TPE 多继续符方案 2](../core/media/3cebd82f-9192-4d52-84c7-584f24e8ecca.gif "3cebd82f-9192-4d52-84c7-584f24e8ecca")</span><span class="sxs-lookup"><span data-stu-id="75f8b-142">![TPE Multiple continuation scenario 2](../core/media/3cebd82f-9192-4d52-84c7-584f24e8ecca.gif "3cebd82f-9192-4d52-84c7-584f24e8ecca")</span></span>  
  
#### <a name="scenario-solution-3---content-based-routing"></a><span data-ttu-id="75f8b-143">解决方案 3 - 基于内容的路由</span><span class="sxs-lookup"><span data-stu-id="75f8b-143">Scenario Solution 3 - Content Based Routing</span></span>  
 <span data-ttu-id="75f8b-144">此方案定义基于内容的路由 (CBR) 解决方案。</span><span class="sxs-lookup"><span data-stu-id="75f8b-144">This scenario defines a content based routing (CBR) solution.</span></span> <span data-ttu-id="75f8b-145">消息只发送到一个接收端口，并且仅由一个发送端口发送。</span><span class="sxs-lookup"><span data-stu-id="75f8b-145">A message arrives at exactly one of the receive ports and is sent to exactly one of the send ports.</span></span> <span data-ttu-id="75f8b-146">此路由基于消息中的上下文属性值来执行。</span><span class="sxs-lookup"><span data-stu-id="75f8b-146">This routing happens based on a context property value in the message.</span></span> <span data-ttu-id="75f8b-147">在这种情况下，需要一个继续符。</span><span class="sxs-lookup"><span data-stu-id="75f8b-147">In this case, we would need one continuation.</span></span> <span data-ttu-id="75f8b-148">映射如下所示：</span><span class="sxs-lookup"><span data-stu-id="75f8b-148">The mapping looks something like this:</span></span>  
  
 <span data-ttu-id="75f8b-149">![连续 CBR 方案。](../core/media/4459a73d-515f-4d6d-a68f-b18eee072df8.gif "4459a73d-515f-4d6d-a68f-b18eee072df8")</span><span class="sxs-lookup"><span data-stu-id="75f8b-149">![Continuation CBR scenario.](../core/media/4459a73d-515f-4d6d-a68f-b18eee072df8.gif "4459a73d-515f-4d6d-a68f-b18eee072df8")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75f8b-150">上面的映射还对只发送到一个接收端口并由所有发送端口发送的消息有效。</span><span class="sxs-lookup"><span data-stu-id="75f8b-150">The above mapping is also valid for a message that arrives at exactly one of the receive ports and is sent to all of the send ports.</span></span>  
  
#### <a name="scenario-solution-4---one-orchestration-multiple-send-ports"></a><span data-ttu-id="75f8b-151">解决方案 4 - 一个业务流程，多个发送端口</span><span class="sxs-lookup"><span data-stu-id="75f8b-151">Scenario Solution 4 - One Orchestration, Multiple Send Ports</span></span>  
 <span data-ttu-id="75f8b-152">在此方案中，有多个发送。</span><span class="sxs-lookup"><span data-stu-id="75f8b-152">In this scenario, there are multiple send.</span></span> <span data-ttu-id="75f8b-153">端口。</span><span class="sxs-lookup"><span data-stu-id="75f8b-153">ports.</span></span> <span data-ttu-id="75f8b-154">由一个业务流程，它由处理规则，并发送到所有发送端口处理消息。</span><span class="sxs-lookup"><span data-stu-id="75f8b-154">A message is processed by exactly one of the orchestrations, which is determined by the processing rules, and is sent to all of the send ports.</span></span> <span data-ttu-id="75f8b-155">在这种情况下，需要一个继续符。</span><span class="sxs-lookup"><span data-stu-id="75f8b-155">In this case, we would need one continuation.</span></span> <span data-ttu-id="75f8b-156">映射如下所示：</span><span class="sxs-lookup"><span data-stu-id="75f8b-156">The mapping looks something like this:</span></span>  
  
 <span data-ttu-id="75f8b-157">![继续符方案 4](../core/media/3ab10b51-d306-4ad1-acb6-6731e23394ac.gif "3ab10b51-d306-4ad1-acb6-6731e23394ac")</span><span class="sxs-lookup"><span data-stu-id="75f8b-157">![Coninuation Scenario 4](../core/media/3ab10b51-d306-4ad1-acb6-6731e23394ac.gif "3ab10b51-d306-4ad1-acb6-6731e23394ac")</span></span>  
  
#### <a name="scenario-solution-5---sequential-orchestrations"></a><span data-ttu-id="75f8b-158">解决方案 5 - 序列化业务流程</span><span class="sxs-lookup"><span data-stu-id="75f8b-158">Scenario Solution 5 - Sequential Orchestrations</span></span>  
 <span data-ttu-id="75f8b-159">在此方案中，消息由每个业务流程一个接一个地按顺序处理，通过继续符传递给下一个业务流程。</span><span class="sxs-lookup"><span data-stu-id="75f8b-159">In this scenario, a message is processed by each orchestration in sequence, one by one, and is passed to the next orchestration via the continuation.</span></span> <span data-ttu-id="75f8b-160">映射如下所示：</span><span class="sxs-lookup"><span data-stu-id="75f8b-160">The mapping looks something like this:</span></span>  
  
 <span data-ttu-id="75f8b-161">![继续符方案 5](../core/media/563cacee-104c-4f8a-9836-da90aecb7487.gif "563cacee-104c-4f8a-9836-da90aecb7487")</span><span class="sxs-lookup"><span data-stu-id="75f8b-161">![Continuation scenario 5](../core/media/563cacee-104c-4f8a-9836-da90aecb7487.gif "563cacee-104c-4f8a-9836-da90aecb7487")</span></span>  
  
### <a name="collecting-data-in-an-asynchronous-environment"></a><span data-ttu-id="75f8b-162">在异步环境中收集数据</span><span class="sxs-lookup"><span data-stu-id="75f8b-162">Collecting Data in an Asynchronous Environment</span></span>  
 <span data-ttu-id="75f8b-163">在设置继续符后，BAM 等待数据到来。</span><span class="sxs-lookup"><span data-stu-id="75f8b-163">When you set up continuations, BAM expects the data to arrive.</span></span> <span data-ttu-id="75f8b-164">但在异步环境中可能接收不到后端进程的响应。</span><span class="sxs-lookup"><span data-stu-id="75f8b-164">In an asynchronous environment you may not receive a response from a backend process.</span></span>  
  
 <span data-ttu-id="75f8b-165">如果没有收到响应数据，则活动实例无限期等待。</span><span class="sxs-lookup"><span data-stu-id="75f8b-165">If you do not receive the response data, the activity instance waits indefinitely.</span></span> <span data-ttu-id="75f8b-166">该活动永不结束，活动记录会一直保留在 BAM 主导入数据库的表中。</span><span class="sxs-lookup"><span data-stu-id="75f8b-166">The activity will never complete and the records remain in the tables in the BAM Primary Import database.</span></span> <span data-ttu-id="75f8b-167">如果是长期事务，则没有办法断定剩余数据何时到达。</span><span class="sxs-lookup"><span data-stu-id="75f8b-167">Consider the case of long-running transactions, where there is no way to tell when the remaining data will arrive.</span></span> <span data-ttu-id="75f8b-168">由于数据的到达由业务逻辑或流程决定，因此不会发生使活动标记为完成的超时。</span><span class="sxs-lookup"><span data-stu-id="75f8b-168">There is no time-out, as data arrival will depend on business logic or processes, after which the activity is marked as complete.</span></span> <span data-ttu-id="75f8b-169">数据可能在当天到达，极端情况下可能是明年。</span><span class="sxs-lookup"><span data-stu-id="75f8b-169">The data could arrive the same day, or in extreme cases, the following year.</span></span>  
  
 <span data-ttu-id="75f8b-170">该解决方案使用相关活动。</span><span class="sxs-lookup"><span data-stu-id="75f8b-170">The solution is to use related activities.</span></span>  
  
 <span data-ttu-id="75f8b-171">将您的活动分为两个活动。</span><span class="sxs-lookup"><span data-stu-id="75f8b-171">Split your activity into two activities.</span></span> <span data-ttu-id="75f8b-172">将这两个活动相关联，然后将响应关联到原始活动。</span><span class="sxs-lookup"><span data-stu-id="75f8b-172">Relate the two activities, and relate the response to the original activity.</span></span>  
  
 <span data-ttu-id="75f8b-173">有关相关活动的详细信息，请参阅[活动关系](../core/activity-relationships.md)。</span><span class="sxs-lookup"><span data-stu-id="75f8b-173">For more information about related activities, see [Activity Relationships](../core/activity-relationships.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75f8b-174">请参阅</span><span class="sxs-lookup"><span data-stu-id="75f8b-174">See Also</span></span>  
 [<span data-ttu-id="75f8b-175">跟踪配置文件编辑器</span><span class="sxs-lookup"><span data-stu-id="75f8b-175">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)