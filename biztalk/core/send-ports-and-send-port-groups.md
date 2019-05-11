---
title: 发送端口和发送端口组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, states
- send port groups
- send port groups, states
- send ports, about send ports
- send ports
- send port groups, about send port groups
- states, send ports
ms.assetid: 274bdd27-9098-46a2-8762-8b57bbfc95b8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc8adf80d30be84236d0c4252f67257cfe92cbbc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254521"
---
# <a name="send-ports-and-send-port-groups"></a><span data-ttu-id="e6a35-102">发送端口和发送端口组</span><span class="sxs-lookup"><span data-stu-id="e6a35-102">Send Ports and Send Port Groups</span></span>
<span data-ttu-id="e6a35-103">一个*发送端口*是 Microsoft BizTalk Server 将消息发送到的位置，或从其 BizTalk Server 接收消息。</span><span class="sxs-lookup"><span data-stu-id="e6a35-103">A *send port* is the location to which Microsoft BizTalk Server sends messages or from which BizTalk Server receives messages.</span></span> <span data-ttu-id="e6a35-104">它还提供了 BizTalk Server 用于实现通信操作的技术。</span><span class="sxs-lookup"><span data-stu-id="e6a35-104">It also provides the technology that BizTalk Server uses to implement the communication action.</span></span> <span data-ttu-id="e6a35-105">该端口的名称唯一标识的位置。</span><span class="sxs-lookup"><span data-stu-id="e6a35-105">The name of the port uniquely identifies the location.</span></span>  
  
 <span data-ttu-id="e6a35-106">创建一条消息发送到发送端口的发送端口服务的新实例的任何时间。</span><span class="sxs-lookup"><span data-stu-id="e6a35-106">Any time a message is sent to a send port a new instance of a send port service is created.</span></span> <span data-ttu-id="e6a35-107">这称为服务实例，也称为发送端口实例。</span><span class="sxs-lookup"><span data-stu-id="e6a35-107">This is called a service instance, also known as a Send Port Instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6a35-108">只能有一个实例的按序送达发送端口。</span><span class="sxs-lookup"><span data-stu-id="e6a35-108">There can only be one instance of an In-order delivery send port.</span></span>  
  
 <span data-ttu-id="e6a35-109">一个*发送端口组*是 BizTalk Server 可用于将同一消息发送到多个目标中的一种配置的发送端口的命名的集合。</span><span class="sxs-lookup"><span data-stu-id="e6a35-109">A *send port group* is a named collection of send ports that BizTalk Server can use to send the same message to multiple destinations in one configuration.</span></span>  
  
 <span data-ttu-id="e6a35-110">BizTalk Server 可以直接从消息路由接收到的发送端口，或发送端口组的位置。</span><span class="sxs-lookup"><span data-stu-id="e6a35-110">BizTalk Server can directly route messages from receive locations to a send port, or to a send port group.</span></span> <span data-ttu-id="e6a35-111">BizTalk Server 将消息路由到该组中的发送端口的所有发送端口组。</span><span class="sxs-lookup"><span data-stu-id="e6a35-111">BizTalk Server sends messages routed to a send port group to all of the send ports in that group.</span></span>  
  
 <span data-ttu-id="e6a35-112">发送端口的两种方式发送端口组处理消息的成员：</span><span class="sxs-lookup"><span data-stu-id="e6a35-112">Send ports that are members of a send port group process messages in two ways:</span></span>  
  
-   <span data-ttu-id="e6a35-113">为发送端口组的成员</span><span class="sxs-lookup"><span data-stu-id="e6a35-113">As a member of the send port group</span></span>  
  
-   <span data-ttu-id="e6a35-114">以 BizTalk Server 将消息路由至发送端口直接</span><span class="sxs-lookup"><span data-stu-id="e6a35-114">As if BizTalk Server routed the messages to the send port directly</span></span>  
  
## <a name="send-port-and-send-port-group-states"></a><span data-ttu-id="e6a35-115">发送端口和发送端口组的状态</span><span class="sxs-lookup"><span data-stu-id="e6a35-115">Send Port and Send Port Group States</span></span>  
 <span data-ttu-id="e6a35-116">BizTalk 管理控制台中显示发送端口和发送端口组处于以下状态之一：</span><span class="sxs-lookup"><span data-stu-id="e6a35-116">The BizTalk Administration Console displays send ports and send port groups in one of the following states:</span></span>  
  
- <span data-ttu-id="e6a35-117">**绑定**。</span><span class="sxs-lookup"><span data-stu-id="e6a35-117">**Bound**.</span></span> <span data-ttu-id="e6a35-118">使用 BizTalk Server 管理控制台，管理员将绑定的发送端口或业务流程向发送端口组。</span><span class="sxs-lookup"><span data-stu-id="e6a35-118">Using the BizTalk Server Administration Console, an administrator binds the send port or send port group to an orchestration.</span></span> <span data-ttu-id="e6a35-119">BizTalk Server 将消息路由到此发送端口或发送端口组之前，管理员必须登记和启动绑定的发送端口或发送端口组。</span><span class="sxs-lookup"><span data-stu-id="e6a35-119">Before BizTalk Server routes messages to this send port or send port group, the administrator must enlist and start the bound send port or send port group.</span></span>  
  
- <span data-ttu-id="e6a35-120">**启动**。</span><span class="sxs-lookup"><span data-stu-id="e6a35-120">**Started**.</span></span> <span data-ttu-id="e6a35-121">为此发送端口或发送端口组的订阅存在并处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="e6a35-121">The subscription for this send port or send port group exists and is active.</span></span> <span data-ttu-id="e6a35-122">当发送端口或发送端口组处于启动状态时，BizTalk Server 将消息传送到发送端口或发送端口组，并发送端口或发送端口组处理订单。</span><span class="sxs-lookup"><span data-stu-id="e6a35-122">When the send port or send port group is in the started state, BizTalk Server delivers messages to the send port or send port group, and the send port or send port group processes them.</span></span> <span data-ttu-id="e6a35-123">开始发送端口或发送端口组之前，管理员必须使用 BizTalk 管理控制台来登记绑定的发送端口或发送端口组。</span><span class="sxs-lookup"><span data-stu-id="e6a35-123">Before you can start a send port or send port group, an administrator must use the BizTalk Administration Console to enlist the bound send port or send port group.</span></span>  
  
- <span data-ttu-id="e6a35-124">**停止**。</span><span class="sxs-lookup"><span data-stu-id="e6a35-124">**Stopped**.</span></span> <span data-ttu-id="e6a35-125">当前未运行的发送端口或发送端口组。</span><span class="sxs-lookup"><span data-stu-id="e6a35-125">The send port or send port group is not currently running.</span></span> <span data-ttu-id="e6a35-126">如果启动发送端口或发送端口组，然后停止了它在工作队列中继续进行处理。</span><span class="sxs-lookup"><span data-stu-id="e6a35-126">If you started the send port or send port group and then stopped it, processing continues in the work queue.</span></span> <span data-ttu-id="e6a35-127">BizTalk Server 发送路由到已停止的所有新消息的发送端口或发送端口组到主机的挂起队列的发送处理程序在何处运行。</span><span class="sxs-lookup"><span data-stu-id="e6a35-127">BizTalk Server sends all new messages routed to a stopped send port or send port group to the suspended queue of the host where the send handler is running.</span></span>  
  
  <span data-ttu-id="e6a35-128">下表显示了每个州和每个结果可用的操作。</span><span class="sxs-lookup"><span data-stu-id="e6a35-128">The following table shows the actions available from each state, and the result of each.</span></span>  
  
||<span data-ttu-id="e6a35-129">绑定</span><span class="sxs-lookup"><span data-stu-id="e6a35-129">Bound</span></span>|<span data-ttu-id="e6a35-130">已停止</span><span class="sxs-lookup"><span data-stu-id="e6a35-130">Stopped</span></span>|<span data-ttu-id="e6a35-131">Started</span><span class="sxs-lookup"><span data-stu-id="e6a35-131">Started</span></span>|  
|------|-----------|-------------|-------------|  
|<span data-ttu-id="e6a35-132">**登记**</span><span class="sxs-lookup"><span data-stu-id="e6a35-132">**Enlist**</span></span>|<span data-ttu-id="e6a35-133">已停止</span><span class="sxs-lookup"><span data-stu-id="e6a35-133">Stopped</span></span>|<span data-ttu-id="e6a35-134">不可用</span><span class="sxs-lookup"><span data-stu-id="e6a35-134">Not available</span></span>|<span data-ttu-id="e6a35-135">不可用</span><span class="sxs-lookup"><span data-stu-id="e6a35-135">Not available</span></span>|  
|<span data-ttu-id="e6a35-136">**开始**</span><span class="sxs-lookup"><span data-stu-id="e6a35-136">**Start**</span></span>|<span data-ttu-id="e6a35-137">Started</span><span class="sxs-lookup"><span data-stu-id="e6a35-137">Started</span></span>|<span data-ttu-id="e6a35-138">Started</span><span class="sxs-lookup"><span data-stu-id="e6a35-138">Started</span></span>|<span data-ttu-id="e6a35-139">不可用</span><span class="sxs-lookup"><span data-stu-id="e6a35-139">Not available</span></span>|  
|<span data-ttu-id="e6a35-140">**停止**</span><span class="sxs-lookup"><span data-stu-id="e6a35-140">**Stop**</span></span>|<span data-ttu-id="e6a35-141">不可用</span><span class="sxs-lookup"><span data-stu-id="e6a35-141">Not available</span></span>|<span data-ttu-id="e6a35-142">不可用</span><span class="sxs-lookup"><span data-stu-id="e6a35-142">Not available</span></span>|<span data-ttu-id="e6a35-143">已停止</span><span class="sxs-lookup"><span data-stu-id="e6a35-143">Stopped</span></span>|  
|<span data-ttu-id="e6a35-144">**取消登记**</span><span class="sxs-lookup"><span data-stu-id="e6a35-144">**Unenlist**</span></span>|<span data-ttu-id="e6a35-145">不可用</span><span class="sxs-lookup"><span data-stu-id="e6a35-145">Not available</span></span>|<span data-ttu-id="e6a35-146">绑定</span><span class="sxs-lookup"><span data-stu-id="e6a35-146">Bound</span></span>|<span data-ttu-id="e6a35-147">绑定</span><span class="sxs-lookup"><span data-stu-id="e6a35-147">Bound</span></span>|  
  
 <span data-ttu-id="e6a35-148">发送端口和它所属的发送端口组的组合的状态确定是否发送端口或发送端口组处理消息或不。</span><span class="sxs-lookup"><span data-stu-id="e6a35-148">The combined state of a send port and the send port group it belongs to determines if the send port or the send port group processes a message or not.</span></span>  
  
 <span data-ttu-id="e6a35-149">下表描述了可能的状态组合为发送端口和发送端口组。</span><span class="sxs-lookup"><span data-stu-id="e6a35-149">The following table describes the possible state combinations for send ports and send port groups.</span></span>  
  
|<span data-ttu-id="e6a35-150">发送消息</span><span class="sxs-lookup"><span data-stu-id="e6a35-150">Message Sent</span></span>|<span data-ttu-id="e6a35-151">发送端口组的状态</span><span class="sxs-lookup"><span data-stu-id="e6a35-151">State of Send Port Group</span></span>|<span data-ttu-id="e6a35-152">发送端口的状态</span><span class="sxs-lookup"><span data-stu-id="e6a35-152">State of Send Port</span></span>|<span data-ttu-id="e6a35-153">结果</span><span class="sxs-lookup"><span data-stu-id="e6a35-153">Outcome</span></span>|  
|------------------|------------------------------|------------------------|-------------|  
|<span data-ttu-id="e6a35-154">直接向发送端口</span><span class="sxs-lookup"><span data-stu-id="e6a35-154">Directly to the send port</span></span>|<span data-ttu-id="e6a35-155">任何状态</span><span class="sxs-lookup"><span data-stu-id="e6a35-155">Any state</span></span>|<span data-ttu-id="e6a35-156">Started</span><span class="sxs-lookup"><span data-stu-id="e6a35-156">Started</span></span>|<span data-ttu-id="e6a35-157">处理消息</span><span class="sxs-lookup"><span data-stu-id="e6a35-157">Message is processed</span></span>|  
|<span data-ttu-id="e6a35-158">直接向发送端口</span><span class="sxs-lookup"><span data-stu-id="e6a35-158">Directly to the send port</span></span>|<span data-ttu-id="e6a35-159">任何状态</span><span class="sxs-lookup"><span data-stu-id="e6a35-159">Any state</span></span>|<span data-ttu-id="e6a35-160">已停止</span><span class="sxs-lookup"><span data-stu-id="e6a35-160">Stopped</span></span>|<span data-ttu-id="e6a35-161">消息被挂起</span><span class="sxs-lookup"><span data-stu-id="e6a35-161">Message is suspended</span></span>|  
|<span data-ttu-id="e6a35-162">发送到发送端口通过发送端口组</span><span class="sxs-lookup"><span data-stu-id="e6a35-162">To the send port by means of a send port group</span></span>|<span data-ttu-id="e6a35-163">Started</span><span class="sxs-lookup"><span data-stu-id="e6a35-163">Started</span></span>|<span data-ttu-id="e6a35-164">Started</span><span class="sxs-lookup"><span data-stu-id="e6a35-164">Started</span></span>|<span data-ttu-id="e6a35-165">处理消息</span><span class="sxs-lookup"><span data-stu-id="e6a35-165">Message is processed</span></span>|  
|<span data-ttu-id="e6a35-166">发送到发送端口通过发送端口组</span><span class="sxs-lookup"><span data-stu-id="e6a35-166">To the send port by means of a send port group</span></span>|<span data-ttu-id="e6a35-167">任何状态</span><span class="sxs-lookup"><span data-stu-id="e6a35-167">Any state</span></span>|<span data-ttu-id="e6a35-168">已停止</span><span class="sxs-lookup"><span data-stu-id="e6a35-168">Stopped</span></span>|<span data-ttu-id="e6a35-169">消息被挂起</span><span class="sxs-lookup"><span data-stu-id="e6a35-169">Message is suspended</span></span>|  
|<span data-ttu-id="e6a35-170">发送到发送端口通过发送端口组</span><span class="sxs-lookup"><span data-stu-id="e6a35-170">To the send port by means of a send port group</span></span>|<span data-ttu-id="e6a35-171">已停止</span><span class="sxs-lookup"><span data-stu-id="e6a35-171">Stopped</span></span>|<span data-ttu-id="e6a35-172">任何状态</span><span class="sxs-lookup"><span data-stu-id="e6a35-172">Any state</span></span>|<span data-ttu-id="e6a35-173">消息被挂起</span><span class="sxs-lookup"><span data-stu-id="e6a35-173">Message is suspended</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e6a35-174">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6a35-174">See Also</span></span>  
 [<span data-ttu-id="e6a35-175">项目</span><span class="sxs-lookup"><span data-stu-id="e6a35-175">Artifacts</span></span>](../core/artifacts.md)