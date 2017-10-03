---
title: "业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations
- correlations, orchestrations
- orchestrations, correlations
- orchestrations, deploying
- deploying, orchestrations
- orchestrations, about orchestrations
ms.assetid: fb01f78a-b805-46be-a7d9-2b7597daab96
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73fb7a4af3a8ef7da8e9da97047006470eb8cc18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="orchestrations"></a><span data-ttu-id="7d2f4-102">业务流程</span><span class="sxs-lookup"><span data-stu-id="7d2f4-102">Orchestrations</span></span>
<span data-ttu-id="7d2f4-103">*业务流程*是可以订阅 （接收） 的可执行业务流程和发布到 MessageBox 数据库 （发送） 消息。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-103">*Orchestrations* are executable business processes that can subscribe to (receive) and publish (send) messages through the MessageBox database.</span></span> <span data-ttu-id="7d2f4-104">此外，业务流程可以构造新的消息。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-104">In addition, orchestrations can construct new messages.</span></span> <span data-ttu-id="7d2f4-105">使用订阅接收消息和路由基础结构中所述[的一条消息的生命周期](../core/lifecycle-of-a-message.md)。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-105">Messages are received using the subscription and routing infrastructure discussed in [Lifecycle of a Message](../core/lifecycle-of-a-message.md).</span></span> <span data-ttu-id="7d2f4-106">在填入业务流程的订阅后，将激活新的实例并传送消息；对于实例订阅，如有必要，将解除对该实例的冻结，然后传送消息。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-106">When subscriptions are filled for orchestrations, a new instance is activated and the message is delivered, or in the case of instance subscriptions, the instance is rehydrated if necessary and the message is then delivered.</span></span> <span data-ttu-id="7d2f4-107">如果从业务流程发送消息，则这些消息将发布到 MessageBox，发布的方式如同消息到达接收位置，相应的属性将插入数据库以用于路由。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-107">When messages are sent from an orchestration, they are published to the MessageBox in the same manner as a message arriving on a receive location with the appropriate properties getting inserted into the database for use in routing.</span></span>  
  
 <span data-ttu-id="7d2f4-108">在业务流程中构造的消息必须放置在 MessageBox 数据库中并由业务流程实例引用，但不应发布这些消息，因为它们尚未发送。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-108">Messages that are constructed in an orchestration must be placed in the MessageBox database and referenced by the orchestration instance, but they should not be published because they have not yet been sent.</span></span> <span data-ttu-id="7d2f4-109">XLANG/s 子服务调用消息代理 API 直接插入消息。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-109">The XLANG/s subservice makes calls to the Message Agent API to insert messages directly.</span></span> <span data-ttu-id="7d2f4-110">这样，业务流程引擎就可以将消息正文插入 MessageBox，并将其直接与正在运行的业务流程实例相关联。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-110">This allows the orchestration engine to insert the message body into the MessageBox and have it directly associated with the running orchestration instance.</span></span> <span data-ttu-id="7d2f4-111">MessageBox 数据库中构造的消息的持久化与业务流程中的持久化点协调作为数据库操作的其他优化。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-111">The persistence of the constructed message in the MessageBox database is coordinated with persistence points in the orchestration as an additional optimization of database operations.</span></span>  
  
 <span data-ttu-id="7d2f4-112">业务流程中使发布和订阅作用不同的概念是绑定。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-112">The concept in orchestrations that makes the publish and subscribe seem to act differently is binding.</span></span> <span data-ttu-id="7d2f4-113">业务流程端口是说明交互的逻辑端口。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-113">Orchestration ports are logical ports that describe an interaction.</span></span> <span data-ttu-id="7d2f4-114">必须将这些逻辑端口绑定到物理端口以便消息传送，但是此绑定进程只不过是为消息路由配置订阅。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-114">You must bind these logical ports to a physical port so that messages are delivered, but this binding process is nothing more than configuring subscriptions for message routing.</span></span>  
  
 <span data-ttu-id="7d2f4-115">有四个基本选项用于绑定这些端口：</span><span class="sxs-lookup"><span data-stu-id="7d2f4-115">There are four basic options for binding these ports:</span></span>  
  
-   <span data-ttu-id="7d2f4-116">立即指定（在业务流程中直接指定端口）</span><span class="sxs-lookup"><span data-stu-id="7d2f4-116">Specify Now (specifying ports directly in the orchestration)</span></span>  
  
-   <span data-ttu-id="7d2f4-117">以后指定（在部署时指定端口）</span><span class="sxs-lookup"><span data-stu-id="7d2f4-117">Specify Later (specifying ports at deployment time)</span></span>  
  
-   <span data-ttu-id="7d2f4-118">使用动态发送端口，其中地址在业务流程代码中设置</span><span class="sxs-lookup"><span data-stu-id="7d2f4-118">Using a dynamic send port where the address is set in the orchestration code</span></span>  
  
-   <span data-ttu-id="7d2f4-119">创建从业务流程到 MessageBox 数据库或其他业务流程的直接绑定</span><span class="sxs-lookup"><span data-stu-id="7d2f4-119">Creating a direct binding from the orchestration to either the MessageBox database or to another orchestration</span></span>  
  
## <a name="deploying-orchestrations"></a><span data-ttu-id="7d2f4-120">部署业务流程</span><span class="sxs-lookup"><span data-stu-id="7d2f4-120">Deploying Orchestrations</span></span>  
 <span data-ttu-id="7d2f4-121">如果在设计时指定绑定，则在部署业务流程时，将创建与该业务流程中所配置参数相匹配的物理端口。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-121">When a binding is specified at design time, the physical port that matches the parameters configured in the orchestration is created when the orchestration is deployed.</span></span> <span data-ttu-id="7d2f4-122">如果在部署时配置绑定，则满足逻辑端口要求的任何端口都能绑定到业务流程端口。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-122">When the binding is configured at deployment time, any port that matches the requirements of the logical port can be bound to the orchestration port.</span></span> <span data-ttu-id="7d2f4-123">对于动态绑定，就像使用“立即指定”选项一样创建物理端口，但是该端口是没有配置地址信息的动态发送端口。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-123">For dynamic binding, a physical port is created just as with the Specify Now option, but the port is a dynamic send port that has no address information configured.</span></span>  
  
 <span data-ttu-id="7d2f4-124">容易混淆的一个概念是：尽管业务流程中的端口绑定到物理发送端口，但这并不会阻止消息送达到其他订户。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-124">A confusing concept is that while a send port in an orchestration is bound to a physical send port, this does not preclude that message from getting delivered to other subscribers.</span></span> <span data-ttu-id="7d2f4-125">即，如果另一个发送端口恰好具有发送到绑定端口的消息的订阅（通过其筛选器），则两个发送端口都接收该消息。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-125">That is, if another send port happens to have a subscription, through its filters, for the message being sent to the bound port, both send ports receive the message.</span></span> <span data-ttu-id="7d2f4-126">绑定仅创建订阅，以便从业务流程发送的消息始终与绑定发送端口的条件相匹配。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-126">Binding simply creates the subscription such that the message sent from the orchestration always matches the criteria for the bound send port.</span></span> <span data-ttu-id="7d2f4-127">同样，绑定到接收端口业务流程端口创建相应的订阅基于消息类型和接收端口 id。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-127">Likewise, the orchestration port bound to a receive port creates the appropriate subscription based on message type and receive port ID.</span></span> <span data-ttu-id="7d2f4-128">订阅保证进出业务流程的消息会发送到的绑定的端口，但消息仍经过相同的发布和订阅机制前面所述。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-128">The subscriptions guarantee that the messages going in and out of the orchestration get delivered to the bound ports, but the messages still go through the same publish and subscribe mechanism described earlier.</span></span>  
  
 <span data-ttu-id="7d2f4-129">可能最常被误解、误用和未充分利用的绑定选项是直接绑定选项。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-129">Probably the most misunderstood, and misused or underused binding option is the Direct binding option.</span></span> <span data-ttu-id="7d2f4-130">直接绑定允许业务流程使用不同的路由属性将消息发布到 MessageBox 数据库，很像消息是由接收位置发布的。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-130">Direct binding allows an orchestration to publish messages to the MessageBox database with varying routing properties much like messages are published by receive locations.</span></span> <span data-ttu-id="7d2f4-131">在简单直接消息传送中，与接收到 BizTalk Server 中的任何其他已发布消息的路由方式一样，使用升级属性将消息发布到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-131">In simple direct messaging, the message is published to the MessageBox with its promoted properties to be routed like any other published message received into BizTalk Server.</span></span> <span data-ttu-id="7d2f4-132">这样，任何订户都可以接收此消息，但是要求至少存在一个订户，否则业务流程将收到路由故障错误。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-132">This enables any subscriber to receive this message, but requires that at least one subscriber exist or the orchestration will receive a routing failure error.</span></span>  
  
 <span data-ttu-id="7d2f4-133">直接绑定的另一个选项是使用自相关端口。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-133">Another option for direct binding is to use self-correlating ports.</span></span> <span data-ttu-id="7d2f4-134">自相关端口是这样的端口：创建唯一相关标记并在实例之间将消息相关时独立使用该标记。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-134">Self-correlating ports are ports that create a unique correlation token and use that token alone in correlating messages between instances.</span></span> <span data-ttu-id="7d2f4-135">自相关端口最常用于调用或启动传入端口参数的业务流程。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-135">The most common use of a self-correlating port is to call or start an orchestration passing in a port parameter.</span></span> <span data-ttu-id="7d2f4-136">在调用的业务流程中，该端口可用于发送消息；而在调用业务流程中，相同的端口可用于接收消息。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-136">In the called orchestration, the port can be used to send a message, while in the calling orchestration the same port can be used to receive a message.</span></span> <span data-ttu-id="7d2f4-137">由于端口具有唯一的相关标记，因此消息将路由回调用业务流程。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-137">Because the port has a unique correlation token, the message is routed back to the calling orchestration.</span></span> <span data-ttu-id="7d2f4-138">自相关端口充当业务流程实例之间的专用通信信道。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-138">Self-correlation ports act as private communication channels between orchestration instances.</span></span>  
  
 <span data-ttu-id="7d2f4-139">最后一个选项是使用合作伙伴业务流程，其中（在调用业务流程和调用的业务流程中），使用相同的共享端口类型配置端口，在端口配置中选择相同的端口。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-139">The final option is to use a partner orchestration in which, in both the calling orchestration and the called orchestration, the port is configured using the same shared port type and in the port configuration, the same port is selected.</span></span> <span data-ttu-id="7d2f4-140">例如，在 Orch1 和 Orch2 中都选定 Orch2.MyDirectPort。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-140">For example, in both Orch1 and Orch2, Orch2.MyDirectPort is selected.</span></span> <span data-ttu-id="7d2f4-141">此类型的绑定基于发送业务流程类型、端口名称和操作名称为接收业务流程设置订阅。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-141">This type of binding sets up a subscription for the receiving orchestration based on the sending orchestration type, the port name, and the operation name.</span></span> <span data-ttu-id="7d2f4-142">这样再次确保消息路由至正确的实例。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-142">This again ensures that the messages get routed to the correct instance.</span></span>  
  
 <span data-ttu-id="7d2f4-143">所有的直接消息传送选项都使用基本的发布和订阅模型。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-143">All of the direct messaging options use the underlying publish and subscribe model.</span></span> <span data-ttu-id="7d2f4-144">这些选项之间的差别在于，创建订阅和路由的选项不同，以及选项针对的使用情况有所不同。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-144">The difference between these options is in the properties that are used for creating subscriptions and routing, and in the use cases they help solve.</span></span>  
  
 <span data-ttu-id="7d2f4-145">在业务流程中使用直接绑定端口的一个常见问题是：业务流程可能发布被订阅的消息。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-145">One common problem encountered when using direct bound ports in orchestrations is that an orchestration may publish a message that it is also subscribed to.</span></span> <span data-ttu-id="7d2f4-146">例如，某个业务流程配置为由 PurchaseOrder 消息激活。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-146">For example, an orchestration is configured to be activated by a PurchaseOrder message.</span></span> <span data-ttu-id="7d2f4-147">此业务流程使用直接端口将 PurchaseOrder 消息发布到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-147">This orchestration uses a direct port to publish the PurchaseOrder message to the MessageBox.</span></span> <span data-ttu-id="7d2f4-148">但是，除了按预期方式接收消息外，将启动另一个业务流程实例，因为该业务流程也具有 PurchaseOrder 消息的订阅。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-148">However, in addition to receiving the message as expected, another instance of an orchestration is started because it too had a subscription for PurchaseOrder messages.</span></span> <span data-ttu-id="7d2f4-149">该处理进入无穷循环，开发人员可能需要花费一些时间来判断发生的情况。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-149">The processing gets into an endless loop and it may take some time for a developer to figure out what has happened.</span></span>  
  
## <a name="correlation"></a><span data-ttu-id="7d2f4-150">Correlation</span><span class="sxs-lookup"><span data-stu-id="7d2f4-150">Correlation</span></span>  
 <span data-ttu-id="7d2f4-151">*相关*在业务流程中是用于接收到同一个正在运行的业务流程实例的相关的消息的机制。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-151">*Correlation* in orchestrations is the mechanism for receiving related messages into the same running orchestration instance.</span></span> <span data-ttu-id="7d2f4-152">在业务流程设计器中，开发人员按照以下通用步骤使用相关：</span><span class="sxs-lookup"><span data-stu-id="7d2f4-152">In the Orchestration Designer a developer follows these general steps to use a correlation:</span></span>  
  
-   <span data-ttu-id="7d2f4-153">定义包含升级属性、用于将消息相关的相关类型。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-153">Defines a correlation type that includes the promoted properties that are used to relate messages.</span></span>  
  
-   <span data-ttu-id="7d2f4-154">定义相关集（刚定义的相关类型的实例）。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-154">Defines a correlation set that is an instance of the correlation type just defined.</span></span>  
  
-   <span data-ttu-id="7d2f4-155">对于发送和接收端口，指定是否初始化或沿用给定相关集。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-155">For the send and receive ports, specifies whether they initiate or follow a given correlation set.</span></span>  
  
 <span data-ttu-id="7d2f4-156">实例订阅在初始化相关集时开始起作用，如同为所有沿用此相关集接收消息的端口创建订阅时一样。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-156">Instance subscriptions come into play when a correlation set is initiated, as this is when subscriptions are created for all of those ports that follow this correlation set to receive messages.</span></span> <span data-ttu-id="7d2f4-157">由于相关类型定义用于相关的属性，因此业务流程引擎可以从初始化操作发送或接收的消息中提取这些属性。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-157">Because the correlation type defines the properties to be used for correlation, the orchestration engine can extract these properties from the message being sent or received by the initiating action.</span></span> <span data-ttu-id="7d2f4-158">然后将这些值用于为沿用此相关集的所有剩余操作定义订阅。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-158">These values are then used to define subscriptions for all of the remaining actions which follow this correlation set.</span></span>  
  
 <span data-ttu-id="7d2f4-159">务必正确定义接收到 BizTalk Server 并用于相关的消息的升级属性，并将属性升级到消息上下文。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-159">It is important that messages received into BizTalk Server and intended for use in a correlation have their promoted properties correctly defined and promoted to the message context.</span></span> <span data-ttu-id="7d2f4-160">大多数属性在管道中的拆装器组件提取值（在最初接收消息时）时被升级。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-160">Most properties get promoted when a disassembler component in a pipeline extracts the values when the message is initially received.</span></span> <span data-ttu-id="7d2f4-161">因此，不能使用直通接收管道来接收必须与正在运行的业务流程实例相关的消息。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-161">For this reason, it is not possible to use the PassThrough receive pipeline to receive messages that must be correlated to a running instance of an orchestration.</span></span> <span data-ttu-id="7d2f4-162">在使用 SOAP 接收适配器接收相关消息时会出现此问题，因为直通管道是使用 Web Services 发布向导时接收管道的默认值。</span><span class="sxs-lookup"><span data-stu-id="7d2f4-162">This issue arises when you use the SOAP receive adapter to receive correlated messages, because the PassThrough pipeline is the default value for the receive pipeline when using the Web Services Publishing Wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d2f4-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d2f4-163">See Also</span></span>  
 <span data-ttu-id="7d2f4-164">[项目](../core/artifacts.md) </span><span class="sxs-lookup"><span data-stu-id="7d2f4-164">[Artifacts](../core/artifacts.md) </span></span>  
 [<span data-ttu-id="7d2f4-165">创建使用业务流程设计器的业务流程</span><span class="sxs-lookup"><span data-stu-id="7d2f4-165">Creating Orchestrations Using Orchestration Designer</span></span>](../core/creating-orchestrations-using-orchestration-designer.md)