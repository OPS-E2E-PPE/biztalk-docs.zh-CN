---
title: "发送端口和发送端口组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e57e56d05cf3b1a98bba83d0df92d52f09c6eda5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="send-ports-and-send-port-groups"></a><span data-ttu-id="bc4fe-102">发送端口和发送端口组</span><span class="sxs-lookup"><span data-stu-id="bc4fe-102">Send Ports and Send Port Groups</span></span>
<span data-ttu-id="bc4fe-103">A*发送端口*是 Microsoft BizTalk Server 将消息发送到的位置或 BizTalk Server 从中接收消息。</span><span class="sxs-lookup"><span data-stu-id="bc4fe-103">A *send port* is the location to which Microsoft BizTalk Server sends messages or from which BizTalk Server receives messages.</span></span> <span data-ttu-id="bc4fe-104">它还提供 BizTalk Server 用于实现通信操作的技术。</span><span class="sxs-lookup"><span data-stu-id="bc4fe-104">It also provides the technology that BizTalk Server uses to implement the communication action.</span></span> <span data-ttu-id="bc4fe-105">端口名称唯一标识该位置。</span><span class="sxs-lookup"><span data-stu-id="bc4fe-105">The name of the port uniquely identifies the location.</span></span>  
  
 <span data-ttu-id="bc4fe-106">只要向发送端口发送消息，就会创建一个新的发送端口服务实例。</span><span class="sxs-lookup"><span data-stu-id="bc4fe-106">Any time a message is sent to a send port a new instance of a send port service is created.</span></span> <span data-ttu-id="bc4fe-107">此实例称为服务实例，也称为发送端口实例。</span><span class="sxs-lookup"><span data-stu-id="bc4fe-107">This is called a service instance, also known as a Send Port Instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc4fe-108">只能存在一个按序送达发送端口实例。</span><span class="sxs-lookup"><span data-stu-id="bc4fe-108">There can only be one instance of an In-order delivery send port.</span></span>  
  
 <span data-ttu-id="bc4fe-109">A*发送端口组*是可用于将同一条消息发送到多个目标中的一种配置 BizTalk Server 发送端口的命名的集合。</span><span class="sxs-lookup"><span data-stu-id="bc4fe-109">A *send port group* is a named collection of send ports that BizTalk Server can use to send the same message to multiple destinations in one configuration.</span></span>  
  
 <span data-ttu-id="bc4fe-110">BizTalk Server 可直接将消息从接收位置路由至发送端口或发送端口组。</span><span class="sxs-lookup"><span data-stu-id="bc4fe-110">BizTalk Server can directly route messages from receive locations to a send port, or to a send port group.</span></span> <span data-ttu-id="bc4fe-111">BizTalk Server 将把路由至发送端口组的消息发送到该组中的所有发送端口。</span><span class="sxs-lookup"><span data-stu-id="bc4fe-111">BizTalk Server sends messages routed to a send port group to all of the send ports in that group.</span></span>  
  
 <span data-ttu-id="bc4fe-112">发送端口组中的成员发送端口按以下两种方式处理消息：</span><span class="sxs-lookup"><span data-stu-id="bc4fe-112">Send ports that are members of a send port group process messages in two ways:</span></span>  
  
-   <span data-ttu-id="bc4fe-113">以发送端口组成员的身份</span><span class="sxs-lookup"><span data-stu-id="bc4fe-113">As a member of the send port group</span></span>  
  
-   <span data-ttu-id="bc4fe-114">以 BizTalk Server 直接将消息路由至该发送端口的方式</span><span class="sxs-lookup"><span data-stu-id="bc4fe-114">As if BizTalk Server routed the messages to the send port directly</span></span>  
  
## <a name="send-port-and-send-port-group-states"></a><span data-ttu-id="bc4fe-115">发送端口和发送端口组的状态</span><span class="sxs-lookup"><span data-stu-id="bc4fe-115">Send Port and Send Port Group States</span></span>  
 <span data-ttu-id="bc4fe-116">BizTalk 管理控制台按以下状态之一显示发送端口和发送端口组.：</span><span class="sxs-lookup"><span data-stu-id="bc4fe-116">The BizTalk Administration Console displays send ports and send port groups in one of the following states:</span></span>  
  
-   <span data-ttu-id="bc4fe-117">**绑定**。</span><span class="sxs-lookup"><span data-stu-id="bc4fe-117">**Bound**.</span></span> <span data-ttu-id="bc4fe-118">使用 BizTalk Server 管理控制台，管理员可以将发送端口或发送端口组绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="bc4fe-118">Using the BizTalk Server Administration Console, an administrator binds the send port or send port group to an orchestration.</span></span> <span data-ttu-id="bc4fe-119">在 BizTalk Server 将消息路由至此发送端口或发送端口组之前，管理员必须登记和启动绑定的发送端口或发送端口组。</span><span class="sxs-lookup"><span data-stu-id="bc4fe-119">Before BizTalk Server routes messages to this send port or send port group, the administrator must enlist and start the bound send port or send port group.</span></span>  
  
-   <span data-ttu-id="bc4fe-120">**启动**。</span><span class="sxs-lookup"><span data-stu-id="bc4fe-120">**Started**.</span></span> <span data-ttu-id="bc4fe-121">对此发送端口或发送端口组的订阅已存在并处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="bc4fe-121">The subscription for this send port or send port group exists and is active.</span></span> <span data-ttu-id="bc4fe-122">当发送端口或发送端口组处于“已启动”状态时，BizTalk Server 将把消息送达该发送端口或发送端口组，然后由该发送端口或发送端口组来对这些消息进行处理。</span><span class="sxs-lookup"><span data-stu-id="bc4fe-122">When the send port or send port group is in the started state, BizTalk Server delivers messages to the send port or send port group, and the send port or send port group processes them.</span></span> <span data-ttu-id="bc4fe-123">在启动发送端口或发送端口组之前，管理员必须使用 BizTalk 管理控制台来登记绑定的发送端口或发送端口组。</span><span class="sxs-lookup"><span data-stu-id="bc4fe-123">Before you can start a send port or send port group, an administrator must use the BizTalk Administration Console to enlist the bound send port or send port group.</span></span>  
  
-   <span data-ttu-id="bc4fe-124">**停止**。</span><span class="sxs-lookup"><span data-stu-id="bc4fe-124">**Stopped**.</span></span> <span data-ttu-id="bc4fe-125">发送端口或发送端口组当前未运行。</span><span class="sxs-lookup"><span data-stu-id="bc4fe-125">The send port or send port group is not currently running.</span></span> <span data-ttu-id="bc4fe-126">如果在启动发送端口或发送端口组之后将其停止，则会在工作队列中继续进行处理。</span><span class="sxs-lookup"><span data-stu-id="bc4fe-126">If you started the send port or send port group and then stopped it, processing continues in the work queue.</span></span> <span data-ttu-id="bc4fe-127">BizTalk Server 将把路由至已停止的发送端口或发送端口组的所有新消息发送到正在运行发送处理程序的主机的挂起队列中。</span><span class="sxs-lookup"><span data-stu-id="bc4fe-127">BizTalk Server sends all new messages routed to a stopped send port or send port group to the suspended queue of the host where the send handler is running.</span></span>  
  
 <span data-ttu-id="bc4fe-128">下表显示了各种状态下可用的操作以及各操作的结果：</span><span class="sxs-lookup"><span data-stu-id="bc4fe-128">The following table shows the actions available from each state, and the result of each.</span></span>  
  
||<span data-ttu-id="bc4fe-129">已绑定</span><span class="sxs-lookup"><span data-stu-id="bc4fe-129">Bound</span></span>|<span data-ttu-id="bc4fe-130">已停止</span><span class="sxs-lookup"><span data-stu-id="bc4fe-130">Stopped</span></span>|<span data-ttu-id="bc4fe-131">Started</span><span class="sxs-lookup"><span data-stu-id="bc4fe-131">Started</span></span>|  
|------|-----------|-------------|-------------|  
|<span data-ttu-id="bc4fe-132">**登记**</span><span class="sxs-lookup"><span data-stu-id="bc4fe-132">**Enlist**</span></span>|<span data-ttu-id="bc4fe-133">已停止</span><span class="sxs-lookup"><span data-stu-id="bc4fe-133">Stopped</span></span>|<span data-ttu-id="bc4fe-134">不可用</span><span class="sxs-lookup"><span data-stu-id="bc4fe-134">Not available</span></span>|<span data-ttu-id="bc4fe-135">不可用</span><span class="sxs-lookup"><span data-stu-id="bc4fe-135">Not available</span></span>|  
|<span data-ttu-id="bc4fe-136">**开始**</span><span class="sxs-lookup"><span data-stu-id="bc4fe-136">**Start**</span></span>|<span data-ttu-id="bc4fe-137">Started</span><span class="sxs-lookup"><span data-stu-id="bc4fe-137">Started</span></span>|<span data-ttu-id="bc4fe-138">Started</span><span class="sxs-lookup"><span data-stu-id="bc4fe-138">Started</span></span>|<span data-ttu-id="bc4fe-139">不可用</span><span class="sxs-lookup"><span data-stu-id="bc4fe-139">Not available</span></span>|  
|<span data-ttu-id="bc4fe-140">**停止**</span><span class="sxs-lookup"><span data-stu-id="bc4fe-140">**Stop**</span></span>|<span data-ttu-id="bc4fe-141">不可用</span><span class="sxs-lookup"><span data-stu-id="bc4fe-141">Not available</span></span>|<span data-ttu-id="bc4fe-142">不可用</span><span class="sxs-lookup"><span data-stu-id="bc4fe-142">Not available</span></span>|<span data-ttu-id="bc4fe-143">已停止</span><span class="sxs-lookup"><span data-stu-id="bc4fe-143">Stopped</span></span>|  
|<span data-ttu-id="bc4fe-144">**取消登记**</span><span class="sxs-lookup"><span data-stu-id="bc4fe-144">**Unenlist**</span></span>|<span data-ttu-id="bc4fe-145">不可用</span><span class="sxs-lookup"><span data-stu-id="bc4fe-145">Not available</span></span>|<span data-ttu-id="bc4fe-146">已绑定</span><span class="sxs-lookup"><span data-stu-id="bc4fe-146">Bound</span></span>|<span data-ttu-id="bc4fe-147">已绑定</span><span class="sxs-lookup"><span data-stu-id="bc4fe-147">Bound</span></span>|  
  
 <span data-ttu-id="bc4fe-148">将发送端口的状态与其所属发送端口组的状态进行组合，可确定发送端口或发送端口组是否处理消息。</span><span class="sxs-lookup"><span data-stu-id="bc4fe-148">The combined state of a send port and the send port group it belongs to determines if the send port or the send port group processes a message or not.</span></span>  
  
 <span data-ttu-id="bc4fe-149">下表介绍了发送端口和发送端口组可能的状态组合：</span><span class="sxs-lookup"><span data-stu-id="bc4fe-149">The following table describes the possible state combinations for send ports and send port groups.</span></span>  
  
|<span data-ttu-id="bc4fe-150">消息发送方式</span><span class="sxs-lookup"><span data-stu-id="bc4fe-150">Message Sent</span></span>|<span data-ttu-id="bc4fe-151">发送端口组的状态</span><span class="sxs-lookup"><span data-stu-id="bc4fe-151">State of Send Port Group</span></span>|<span data-ttu-id="bc4fe-152">发送端口的状态</span><span class="sxs-lookup"><span data-stu-id="bc4fe-152">State of Send Port</span></span>|<span data-ttu-id="bc4fe-153">结果</span><span class="sxs-lookup"><span data-stu-id="bc4fe-153">Outcome</span></span>|  
|------------------|------------------------------|------------------------|-------------|  
|<span data-ttu-id="bc4fe-154">直接发送到发送端口</span><span class="sxs-lookup"><span data-stu-id="bc4fe-154">Directly to the send port</span></span>|<span data-ttu-id="bc4fe-155">任何状态</span><span class="sxs-lookup"><span data-stu-id="bc4fe-155">Any state</span></span>|<span data-ttu-id="bc4fe-156">Started</span><span class="sxs-lookup"><span data-stu-id="bc4fe-156">Started</span></span>|<span data-ttu-id="bc4fe-157">消息已处理</span><span class="sxs-lookup"><span data-stu-id="bc4fe-157">Message is processed</span></span>|  
|<span data-ttu-id="bc4fe-158">直接发送到发送端口</span><span class="sxs-lookup"><span data-stu-id="bc4fe-158">Directly to the send port</span></span>|<span data-ttu-id="bc4fe-159">任何状态</span><span class="sxs-lookup"><span data-stu-id="bc4fe-159">Any state</span></span>|<span data-ttu-id="bc4fe-160">已停止</span><span class="sxs-lookup"><span data-stu-id="bc4fe-160">Stopped</span></span>|<span data-ttu-id="bc4fe-161">消息被挂起</span><span class="sxs-lookup"><span data-stu-id="bc4fe-161">Message is suspended</span></span>|  
|<span data-ttu-id="bc4fe-162">通过发送端口组发送到发送端口</span><span class="sxs-lookup"><span data-stu-id="bc4fe-162">To the send port by means of a send port group</span></span>|<span data-ttu-id="bc4fe-163">Started</span><span class="sxs-lookup"><span data-stu-id="bc4fe-163">Started</span></span>|<span data-ttu-id="bc4fe-164">Started</span><span class="sxs-lookup"><span data-stu-id="bc4fe-164">Started</span></span>|<span data-ttu-id="bc4fe-165">消息已处理</span><span class="sxs-lookup"><span data-stu-id="bc4fe-165">Message is processed</span></span>|  
|<span data-ttu-id="bc4fe-166">通过发送端口组发送到发送端口</span><span class="sxs-lookup"><span data-stu-id="bc4fe-166">To the send port by means of a send port group</span></span>|<span data-ttu-id="bc4fe-167">任何状态</span><span class="sxs-lookup"><span data-stu-id="bc4fe-167">Any state</span></span>|<span data-ttu-id="bc4fe-168">已停止</span><span class="sxs-lookup"><span data-stu-id="bc4fe-168">Stopped</span></span>|<span data-ttu-id="bc4fe-169">消息被挂起</span><span class="sxs-lookup"><span data-stu-id="bc4fe-169">Message is suspended</span></span>|  
|<span data-ttu-id="bc4fe-170">通过发送端口组发送到发送端口</span><span class="sxs-lookup"><span data-stu-id="bc4fe-170">To the send port by means of a send port group</span></span>|<span data-ttu-id="bc4fe-171">已停止</span><span class="sxs-lookup"><span data-stu-id="bc4fe-171">Stopped</span></span>|<span data-ttu-id="bc4fe-172">任何状态</span><span class="sxs-lookup"><span data-stu-id="bc4fe-172">Any state</span></span>|<span data-ttu-id="bc4fe-173">消息被挂起</span><span class="sxs-lookup"><span data-stu-id="bc4fe-173">Message is suspended</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bc4fe-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc4fe-174">See Also</span></span>  
 [<span data-ttu-id="bc4fe-175">项目</span><span class="sxs-lookup"><span data-stu-id="bc4fe-175">Artifacts</span></span>](../core/artifacts.md)