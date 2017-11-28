---
title: "如何在业务流程中使用端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, adding ports
- Port Configuration Wizard [Orchestration Designer], configuring ports
- ports, operations
- operations, adding to ports
- configuring, ports
- ports, deleting
- deleting, ports
- ports, Port Configuration Wizard [Orchestration Designer]
- ports, adding to orchestrations
- ports, configuring
ms.assetid: da8665cd-ccde-4949-b5f5-01f9f8be5ce8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3edef29376d8724d93192040ee88951ced245ac3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-ports-in-orchestrations"></a><span data-ttu-id="e2e82-102">如何使用在业务流程中的端口</span><span class="sxs-lookup"><span data-stu-id="e2e82-102">How to Use Ports in Orchestrations</span></span>
<span data-ttu-id="e2e82-103">向业务流程添加端口的方式与向 Web 窗体或 Windows 窗体添加控件的方式相同。</span><span class="sxs-lookup"><span data-stu-id="e2e82-103">You add ports to an orchestration in much the same way that you add controls to a Web Form or Windows Form.</span></span> <span data-ttu-id="e2e82-104">还可以使用“业务流程视图”窗口来添加端口。</span><span class="sxs-lookup"><span data-stu-id="e2e82-104">You can also add ports by using the Orchestration View window.</span></span>  
  
### <a name="to-add-a-new-port"></a><span data-ttu-id="e2e82-105">添加新端口</span><span class="sxs-lookup"><span data-stu-id="e2e82-105">To add a new port</span></span>  
  
-   <span data-ttu-id="e2e82-106">右键单击**端口图面**或**角色链接**，然后单击**新端口**。</span><span class="sxs-lookup"><span data-stu-id="e2e82-106">Right-click a **Port Surface** or a **Role Link**, and then click **New Port**.</span></span>  
  
     <span data-ttu-id="e2e82-107">-或者-</span><span class="sxs-lookup"><span data-stu-id="e2e82-107">—Or—</span></span>  
  
     <span data-ttu-id="e2e82-108">在业务流程视图窗口中，右键单击**端口**，然后单击**新端口**。</span><span class="sxs-lookup"><span data-stu-id="e2e82-108">In the Orchestration View window, right-click **Ports** and then click **New Port**.</span></span>  
  
     <span data-ttu-id="e2e82-109">此时未完全配置的端口上将显示设计提示。</span><span class="sxs-lookup"><span data-stu-id="e2e82-109">A DesignTip appears on ports that are not yet fully configured.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="e2e82-110">您还可以拖动到端口**角色链接**。</span><span class="sxs-lookup"><span data-stu-id="e2e82-110">You can also drag ports into a **Role Link**.</span></span>  
  
### <a name="to-add-and-configure-a-new-port"></a><span data-ttu-id="e2e82-111">添加和配置新端口</span><span class="sxs-lookup"><span data-stu-id="e2e82-111">To add and configure a new port</span></span>  
  
1.  <span data-ttu-id="e2e82-112">从**BizTalk 业务流程**选项卡的工具箱拖**端口**形状拖到**端口图面**或**角色链接**。</span><span class="sxs-lookup"><span data-stu-id="e2e82-112">From the **BizTalk Orchestrations** tab of the Toolbox, drag the **Port** shape onto a **Port Surface** or a **Role Link**.</span></span>  
  
     <span data-ttu-id="e2e82-113">-或者-</span><span class="sxs-lookup"><span data-stu-id="e2e82-113">—Or—</span></span>  
  
     <span data-ttu-id="e2e82-114">右键单击**端口图面**或**角色链接**，然后单击**新配置端口**。</span><span class="sxs-lookup"><span data-stu-id="e2e82-114">Right-click a **Port Surface** or a **Role Link**, and then click **New Configured Port**.</span></span>  
  
     <span data-ttu-id="e2e82-115">-或者-</span><span class="sxs-lookup"><span data-stu-id="e2e82-115">—Or—</span></span>  
  
     <span data-ttu-id="e2e82-116">在业务流程视图窗口中，右键单击**端口**，然后单击**新配置端口**。</span><span class="sxs-lookup"><span data-stu-id="e2e82-116">In the Orchestration View window, right-click **Ports** and then click **New Configured Port**.</span></span>  
  
     <span data-ttu-id="e2e82-117">此时将出现端口配置向导。</span><span class="sxs-lookup"><span data-stu-id="e2e82-117">The Port Configuration Wizard appears.</span></span>  
  
2.  <span data-ttu-id="e2e82-118">按照该向导中的步骤进行端口配置。</span><span class="sxs-lookup"><span data-stu-id="e2e82-118">Follow the steps in the wizard to configure the port.</span></span> <span data-ttu-id="e2e82-119">有关详细信息，请参阅[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)。</span><span class="sxs-lookup"><span data-stu-id="e2e82-119">For more information, see [How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md).</span></span>  
  
### <a name="to-remove-a-port"></a><span data-ttu-id="e2e82-120">删除端口</span><span class="sxs-lookup"><span data-stu-id="e2e82-120">To remove a port</span></span>  
  
-   <span data-ttu-id="e2e82-121">右键单击要删除，，然后单击的端口**删除**。</span><span class="sxs-lookup"><span data-stu-id="e2e82-121">Right-click the port to remove, and then click **Delete**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e2e82-122">如果你已连接到后删除端口**发送**或**接收**形状中业务流程已编译形状上的端口操作不会被删除，并将收到错误时您尝试编译。</span><span class="sxs-lookup"><span data-stu-id="e2e82-122">If you delete a port after it has been connected to a **Send** or **Receive** shape in an orchestration that has been compiled, the port operations on the shape will not be deleted, and you will receive errors when you try to compile.</span></span> <span data-ttu-id="e2e82-123">应将该形状连接到其他端口并重新配置端口操作。</span><span class="sxs-lookup"><span data-stu-id="e2e82-123">Connect the shape to another port and reconfigure the port operations.</span></span>  
  
### <a name="to-configure-a-port-by-using-the-port-configuration-wizard"></a><span data-ttu-id="e2e82-124">使用端口配置向导配置端口</span><span class="sxs-lookup"><span data-stu-id="e2e82-124">To configure a port by using the Port Configuration Wizard</span></span>  
  
1.  <span data-ttu-id="e2e82-125">右键单击要配置，，然后单击的端口**配置端口**。</span><span class="sxs-lookup"><span data-stu-id="e2e82-125">Right-click the port to configure, and then click **Configure Port**.</span></span>  
  
2.  <span data-ttu-id="e2e82-126">按照端口配置向导中的步骤进行端口配置。</span><span class="sxs-lookup"><span data-stu-id="e2e82-126">Follow the steps in the Port Configuration Wizard to configure the port.</span></span> <span data-ttu-id="e2e82-127">有关详细信息，请参阅[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)。</span><span class="sxs-lookup"><span data-stu-id="e2e82-127">For more information, see [How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md).</span></span>  
  
### <a name="to-configure-a-port-manually-by-using-the-properties-window"></a><span data-ttu-id="e2e82-128">使用“属性”窗口手动配置端口</span><span class="sxs-lookup"><span data-stu-id="e2e82-128">To configure a port manually by using the Properties window</span></span>  
  
1.  <span data-ttu-id="e2e82-129">选择要配置的端口。</span><span class="sxs-lookup"><span data-stu-id="e2e82-129">Select the port to configure.</span></span>  
  
2.  <span data-ttu-id="e2e82-130">在“属性”窗口中，指定以下属性：</span><span class="sxs-lookup"><span data-stu-id="e2e82-130">In the Properties window, specify the following properties:</span></span>  
  
    |<span data-ttu-id="e2e82-131">属性</span><span class="sxs-lookup"><span data-stu-id="e2e82-131">Property</span></span>|<span data-ttu-id="e2e82-132">Description</span><span class="sxs-lookup"><span data-stu-id="e2e82-132">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="e2e82-133">端口类型</span><span class="sxs-lookup"><span data-stu-id="e2e82-133">Port Type</span></span>|<span data-ttu-id="e2e82-134">确定与端口相关的通信模式、操作和多部分消息类型。</span><span class="sxs-lookup"><span data-stu-id="e2e82-134">Determines the communication pattern, operations, and multi-part message types associated with a port.</span></span>|  
    |<span data-ttu-id="e2e82-135">通信方向</span><span class="sxs-lookup"><span data-stu-id="e2e82-135">Communication Direction</span></span>|<span data-ttu-id="e2e82-136">确定此业务流程是通信的发送方还是接收方。</span><span class="sxs-lookup"><span data-stu-id="e2e82-136">Determines whether this orchestration is the sender or the receiver for this communication.</span></span>|  
    |<span data-ttu-id="e2e82-137">通信模式</span><span class="sxs-lookup"><span data-stu-id="e2e82-137">Communication Pattern</span></span>|<span data-ttu-id="e2e82-138">确定此端口是用于请求-响应还是单向通信。</span><span class="sxs-lookup"><span data-stu-id="e2e82-138">Determines if this port is used for request-response or one-way communication.</span></span> <span data-ttu-id="e2e82-139">(此属性由**端口类型**属性是只读的和。)</span><span class="sxs-lookup"><span data-stu-id="e2e82-139">(This property is determined by the **Port Type** property and is read-only.)</span></span>|  
    |<span data-ttu-id="e2e82-140">Binding</span><span class="sxs-lookup"><span data-stu-id="e2e82-140">Binding</span></span>|<span data-ttu-id="e2e82-141">确定消息如何到达目的地：</span><span class="sxs-lookup"><span data-stu-id="e2e82-141">Determines how a message gets to its destination:</span></span><br /><br /> <span data-ttu-id="e2e82-142">直接-与另一个业务流程进行通信。</span><span class="sxs-lookup"><span data-stu-id="e2e82-142">Direct—Communication is with another orchestration.</span></span><br /><br /> <span data-ttu-id="e2e82-143">动态-在运行时确定的终结点进行通信。</span><span class="sxs-lookup"><span data-stu-id="e2e82-143">Dynamic—Communication is with an endpoint that is determined at run time.</span></span><br /><br /> <span data-ttu-id="e2e82-144">指定更高版本-由管理员在配置时的终结点进行通信。</span><span class="sxs-lookup"><span data-stu-id="e2e82-144">Specify later—Communication is with an endpoint that is determined by an administrator at configuration time.</span></span><br /><br /> <span data-ttu-id="e2e82-145">立即指定 — 通过设计时就已知的终结点传递通信。</span><span class="sxs-lookup"><span data-stu-id="e2e82-145">Specify now—Communication is with an endpoint that is known at design time.</span></span>|  
    |<span data-ttu-id="e2e82-146">Identifier</span><span class="sxs-lookup"><span data-stu-id="e2e82-146">Identifier</span></span>|<span data-ttu-id="e2e82-147">此端口在业务流程中的名称。</span><span class="sxs-lookup"><span data-stu-id="e2e82-147">The name used for this port in the orchestration.</span></span>|  
    |<span data-ttu-id="e2e82-148">按序送达</span><span class="sxs-lookup"><span data-stu-id="e2e82-148">Ordered Delivery</span></span>|<span data-ttu-id="e2e82-149">对于接收端口，请确保将按给定顺序发布到 MessageBox 数据库的消息仍依照其发布顺序送往每个匹配的订户。</span><span class="sxs-lookup"><span data-stu-id="e2e82-149">For receive ports, ensures that messages that are published to the MessageBox database in a given order are delivered to each matching subscriber in the same order in which they were published to the message box.</span></span> <span data-ttu-id="e2e82-150">有关详细信息，请参阅[有序的消息的传递](../core/ordered-delivery-of-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="e2e82-150">For more information, see [Ordered Delivery of Messages](../core/ordered-delivery-of-messages.md).</span></span>|  
    |<span data-ttu-id="e2e82-151">传递通知</span><span class="sxs-lookup"><span data-stu-id="e2e82-151">Delivery Notification</span></span>|<span data-ttu-id="e2e82-152">对于发送端口，确定是否要在消息成功发送后接收确认。</span><span class="sxs-lookup"><span data-stu-id="e2e82-152">For send ports, determines whether want to receive an acknowledgment when a message is sent successfully.</span></span> <span data-ttu-id="e2e82-153">有关详细信息，请参阅"传递通知"[如何配置发送形状](../core/how-to-configure-the-send-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="e2e82-153">For more information, see "Delivery Notification" in [How to Configure the Send Shape](../core/how-to-configure-the-send-shape.md).</span></span>|  
  
3.  <span data-ttu-id="e2e82-154">剩余的属性，以指定由**绑定**属性：</span><span class="sxs-lookup"><span data-stu-id="e2e82-154">The remaining properties to specify are determined by the **Binding** property:</span></span>  
  
    -   <span data-ttu-id="e2e82-155">直接绑定-与另一个业务流程直接通信时使用。</span><span class="sxs-lookup"><span data-stu-id="e2e82-155">Direct binding—Used when communicating directly with another orchestration.</span></span>  
  
        |<span data-ttu-id="e2e82-156">属性</span><span class="sxs-lookup"><span data-stu-id="e2e82-156">Property</span></span>|<span data-ttu-id="e2e82-157">Description</span><span class="sxs-lookup"><span data-stu-id="e2e82-157">Description</span></span>|  
        |--------------|-----------------|  
        |<span data-ttu-id="e2e82-158">合作伙伴业务流程端口</span><span class="sxs-lookup"><span data-stu-id="e2e82-158">Partner Orchestration Port</span></span>|<span data-ttu-id="e2e82-159">确定合作伙伴业务流程直接绑定到的端口。</span><span class="sxs-lookup"><span data-stu-id="e2e82-159">Determines to which port the partner orchestrations will be directly bound.</span></span>|  
  
    -   <span data-ttu-id="e2e82-160">动态绑定-在运行时确定的终结点通信时使用。</span><span class="sxs-lookup"><span data-stu-id="e2e82-160">Dynamic binding—Used when communicating with an endpoint that is determined at run time.</span></span>  
  
        |<span data-ttu-id="e2e82-161">属性</span><span class="sxs-lookup"><span data-stu-id="e2e82-161">Property</span></span>|<span data-ttu-id="e2e82-162">Description</span><span class="sxs-lookup"><span data-stu-id="e2e82-162">Description</span></span>|  
        |--------------|-----------------|  
        |<span data-ttu-id="e2e82-163">接收管道</span><span class="sxs-lookup"><span data-stu-id="e2e82-163">Receive Pipeline</span></span>|<span data-ttu-id="e2e82-164">确定传入消息使用的管道。</span><span class="sxs-lookup"><span data-stu-id="e2e82-164">Determines which pipeline to use for incoming messages.</span></span>|  
        |<span data-ttu-id="e2e82-165">发送管道</span><span class="sxs-lookup"><span data-stu-id="e2e82-165">Send Pipeline</span></span>|<span data-ttu-id="e2e82-166">确定传出消息使用的管道。</span><span class="sxs-lookup"><span data-stu-id="e2e82-166">Determines which pipeline to use for outgoing messages.</span></span>|  
  
    -   <span data-ttu-id="e2e82-167">指定更高版本-与由管理员配置的终结点通信时使用。</span><span class="sxs-lookup"><span data-stu-id="e2e82-167">Specify later—Used when communicating with an endpoint that is configured by an administrator.</span></span>  
  
    -   <span data-ttu-id="e2e82-168">现在指定 — 在设计时已知的终结点通信时使用。</span><span class="sxs-lookup"><span data-stu-id="e2e82-168">Specify now—Used when communicating with an endpoint that is known at design time.</span></span>  
  
        |<span data-ttu-id="e2e82-169">属性</span><span class="sxs-lookup"><span data-stu-id="e2e82-169">Property</span></span>|<span data-ttu-id="e2e82-170">Description</span><span class="sxs-lookup"><span data-stu-id="e2e82-170">Description</span></span>|  
        |--------------|-----------------|  
        |<span data-ttu-id="e2e82-171">接收管道</span><span class="sxs-lookup"><span data-stu-id="e2e82-171">Receive Pipeline</span></span>|<span data-ttu-id="e2e82-172">确定传入消息使用的管道。</span><span class="sxs-lookup"><span data-stu-id="e2e82-172">Determines which pipeline to use for incoming messages.</span></span>|  
        |<span data-ttu-id="e2e82-173">发送管道</span><span class="sxs-lookup"><span data-stu-id="e2e82-173">Send Pipeline</span></span>|<span data-ttu-id="e2e82-174">确定传出消息使用的管道。</span><span class="sxs-lookup"><span data-stu-id="e2e82-174">Determines which pipeline to use for outgoing messages.</span></span>|  
        |<span data-ttu-id="e2e82-175">Transport</span><span class="sxs-lookup"><span data-stu-id="e2e82-175">Transport</span></span>|<span data-ttu-id="e2e82-176">确定发送消息使用的传输。</span><span class="sxs-lookup"><span data-stu-id="e2e82-176">Determines which transport to use for sending messages.</span></span>|  
        |<span data-ttu-id="e2e82-177">URI</span><span class="sxs-lookup"><span data-stu-id="e2e82-177">URI</span></span>|<span data-ttu-id="e2e82-178">确定消息的送达目的地。</span><span class="sxs-lookup"><span data-stu-id="e2e82-178">Determines where to send messages.</span></span>|  
  
### <a name="to-add-a-port-operation"></a><span data-ttu-id="e2e82-179">添加端口操作</span><span class="sxs-lookup"><span data-stu-id="e2e82-179">To add a port operation</span></span>  
  
-   <span data-ttu-id="e2e82-180">右键单击你想要添加某一操作，，然后单击的端口**新操作**。</span><span class="sxs-lookup"><span data-stu-id="e2e82-180">Right-click the port to which you want to add an operation, and then click **New Operation**.</span></span>  
  
### <a name="to-remove-a-port-operation"></a><span data-ttu-id="e2e82-181">删除端口操作</span><span class="sxs-lookup"><span data-stu-id="e2e82-181">To remove a port operation</span></span>  
  
-   <span data-ttu-id="e2e82-182">右键单击要删除，，然后单击的端口操作**删除**。</span><span class="sxs-lookup"><span data-stu-id="e2e82-182">Right-click the port operation to remove, and then click **Delete**.</span></span>