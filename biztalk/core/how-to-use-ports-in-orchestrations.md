---
title: 如何在业务流程中使用端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c076195aa9893dc4bb1c42a9b6a659422e3ec263
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333274"
---
# <a name="how-to-use-ports-in-orchestrations"></a><span data-ttu-id="8b291-102">如何使用业务流程中的端口</span><span class="sxs-lookup"><span data-stu-id="8b291-102">How to Use Ports in Orchestrations</span></span>
<span data-ttu-id="8b291-103">你将端口添加到业务流程相同的方式向 Web 窗体或 Windows 窗体添加控件。</span><span class="sxs-lookup"><span data-stu-id="8b291-103">You add ports to an orchestration in much the same way that you add controls to a Web Form or Windows Form.</span></span> <span data-ttu-id="8b291-104">此外可以通过使用业务流程视图窗口来添加端口。</span><span class="sxs-lookup"><span data-stu-id="8b291-104">You can also add ports by using the Orchestration View window.</span></span>  
  
### <a name="to-add-a-new-port"></a><span data-ttu-id="8b291-105">若要添加新的端口</span><span class="sxs-lookup"><span data-stu-id="8b291-105">To add a new port</span></span>  
  
-   <span data-ttu-id="8b291-106">右键单击**端口图面**或**角色链接**，然后单击**新建端口**。</span><span class="sxs-lookup"><span data-stu-id="8b291-106">Right-click a **Port Surface** or a **Role Link**, and then click **New Port**.</span></span>  
  
     <span data-ttu-id="8b291-107">-或-</span><span class="sxs-lookup"><span data-stu-id="8b291-107">—Or—</span></span>  
  
     <span data-ttu-id="8b291-108">在业务流程视图窗口中，右键单击**端口**，然后单击**新端口**。</span><span class="sxs-lookup"><span data-stu-id="8b291-108">In the Orchestration View window, right-click **Ports** and then click **New Port**.</span></span>  
  
     <span data-ttu-id="8b291-109">此时将显示尚未完全配置的端口上。</span><span class="sxs-lookup"><span data-stu-id="8b291-109">A DesignTip appears on ports that are not yet fully configured.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="8b291-110">您还可以拖动到的端口**角色链接**。</span><span class="sxs-lookup"><span data-stu-id="8b291-110">You can also drag ports into a **Role Link**.</span></span>  
  
### <a name="to-add-and-configure-a-new-port"></a><span data-ttu-id="8b291-111">若要添加和配置新端口</span><span class="sxs-lookup"><span data-stu-id="8b291-111">To add and configure a new port</span></span>  
  
1.  <span data-ttu-id="8b291-112">从**BizTalk 业务流程**选项卡的工具箱拖动**端口**形状拖至**端口图面**或者**角色链接**。</span><span class="sxs-lookup"><span data-stu-id="8b291-112">From the **BizTalk Orchestrations** tab of the Toolbox, drag the **Port** shape onto a **Port Surface** or a **Role Link**.</span></span>  
  
     <span data-ttu-id="8b291-113">-或-</span><span class="sxs-lookup"><span data-stu-id="8b291-113">—Or—</span></span>  
  
     <span data-ttu-id="8b291-114">右键单击**端口图面**或**角色链接**，然后单击**新建配置的端口**。</span><span class="sxs-lookup"><span data-stu-id="8b291-114">Right-click a **Port Surface** or a **Role Link**, and then click **New Configured Port**.</span></span>  
  
     <span data-ttu-id="8b291-115">-或-</span><span class="sxs-lookup"><span data-stu-id="8b291-115">—Or—</span></span>  
  
     <span data-ttu-id="8b291-116">在业务流程视图窗口中，右键单击**端口**，然后单击**新建配置的端口**。</span><span class="sxs-lookup"><span data-stu-id="8b291-116">In the Orchestration View window, right-click **Ports** and then click **New Configured Port**.</span></span>  
  
     <span data-ttu-id="8b291-117">端口配置向导将显示。</span><span class="sxs-lookup"><span data-stu-id="8b291-117">The Port Configuration Wizard appears.</span></span>  
  
2.  <span data-ttu-id="8b291-118">按照向导可配置的端口中的步骤。</span><span class="sxs-lookup"><span data-stu-id="8b291-118">Follow the steps in the wizard to configure the port.</span></span> <span data-ttu-id="8b291-119">有关详细信息，请参阅[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)。</span><span class="sxs-lookup"><span data-stu-id="8b291-119">For more information, see [How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md).</span></span>  
  
### <a name="to-remove-a-port"></a><span data-ttu-id="8b291-120">若要删除端口</span><span class="sxs-lookup"><span data-stu-id="8b291-120">To remove a port</span></span>  
  
-   <span data-ttu-id="8b291-121">右键单击要删除，然后单击端口**删除**。</span><span class="sxs-lookup"><span data-stu-id="8b291-121">Right-click the port to remove, and then click **Delete**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8b291-122">已连接到后删除端口**发送**或**接收**编译之后，业务流程形状上的端口操作形状中将不会删除，并且你将收到错误时您尝试编译。</span><span class="sxs-lookup"><span data-stu-id="8b291-122">If you delete a port after it has been connected to a **Send** or **Receive** shape in an orchestration that has been compiled, the port operations on the shape will not be deleted, and you will receive errors when you try to compile.</span></span> <span data-ttu-id="8b291-123">将该形状连接到另一个端口并重新配置的端口操作。</span><span class="sxs-lookup"><span data-stu-id="8b291-123">Connect the shape to another port and reconfigure the port operations.</span></span>  
  
### <a name="to-configure-a-port-by-using-the-port-configuration-wizard"></a><span data-ttu-id="8b291-124">若要使用端口配置向导配置端口</span><span class="sxs-lookup"><span data-stu-id="8b291-124">To configure a port by using the Port Configuration Wizard</span></span>  
  
1.  <span data-ttu-id="8b291-125">右键单击要配置，然后单击端口**配置端口**。</span><span class="sxs-lookup"><span data-stu-id="8b291-125">Right-click the port to configure, and then click **Configure Port**.</span></span>  
  
2.  <span data-ttu-id="8b291-126">按照端口配置向导，可配置的端口中的步骤。</span><span class="sxs-lookup"><span data-stu-id="8b291-126">Follow the steps in the Port Configuration Wizard to configure the port.</span></span> <span data-ttu-id="8b291-127">有关详细信息，请参阅[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)。</span><span class="sxs-lookup"><span data-stu-id="8b291-127">For more information, see [How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md).</span></span>  
  
### <a name="to-configure-a-port-manually-by-using-the-properties-window"></a><span data-ttu-id="8b291-128">若要通过使用属性窗口手动配置端口</span><span class="sxs-lookup"><span data-stu-id="8b291-128">To configure a port manually by using the Properties window</span></span>  
  
1.  <span data-ttu-id="8b291-129">选择要配置的端口。</span><span class="sxs-lookup"><span data-stu-id="8b291-129">Select the port to configure.</span></span>  
  
2.  <span data-ttu-id="8b291-130">在属性窗口中，指定以下属性：</span><span class="sxs-lookup"><span data-stu-id="8b291-130">In the Properties window, specify the following properties:</span></span>  
  
    |<span data-ttu-id="8b291-131">属性</span><span class="sxs-lookup"><span data-stu-id="8b291-131">Property</span></span>|<span data-ttu-id="8b291-132">Description</span><span class="sxs-lookup"><span data-stu-id="8b291-132">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="8b291-133">端口类型</span><span class="sxs-lookup"><span data-stu-id="8b291-133">Port Type</span></span>|<span data-ttu-id="8b291-134">确定通信模式、 操作和多部分消息类型与端口相关联。</span><span class="sxs-lookup"><span data-stu-id="8b291-134">Determines the communication pattern, operations, and multi-part message types associated with a port.</span></span>|  
    |<span data-ttu-id="8b291-135">通信方向</span><span class="sxs-lookup"><span data-stu-id="8b291-135">Communication Direction</span></span>|<span data-ttu-id="8b291-136">确定此业务流程为发送方或接收方为此通信。</span><span class="sxs-lookup"><span data-stu-id="8b291-136">Determines whether this orchestration is the sender or the receiver for this communication.</span></span>|  
    |<span data-ttu-id="8b291-137">通信模式</span><span class="sxs-lookup"><span data-stu-id="8b291-137">Communication Pattern</span></span>|<span data-ttu-id="8b291-138">确定此端口用于请求-响应还是单向通信。</span><span class="sxs-lookup"><span data-stu-id="8b291-138">Determines if this port is used for request-response or one-way communication.</span></span> <span data-ttu-id="8b291-139">(此属性由**端口类型**属性是只读的。)</span><span class="sxs-lookup"><span data-stu-id="8b291-139">(This property is determined by the **Port Type** property and is read-only.)</span></span>|  
    |<span data-ttu-id="8b291-140">Binding</span><span class="sxs-lookup"><span data-stu-id="8b291-140">Binding</span></span>|<span data-ttu-id="8b291-141">确定消息如何到达其目标：</span><span class="sxs-lookup"><span data-stu-id="8b291-141">Determines how a message gets to its destination:</span></span><br /><br /> <span data-ttu-id="8b291-142">直接 — 与其他业务流程是通信。</span><span class="sxs-lookup"><span data-stu-id="8b291-142">Direct—Communication is with another orchestration.</span></span><br /><br /> <span data-ttu-id="8b291-143">动态 — 通信是在运行时确定的终结点。</span><span class="sxs-lookup"><span data-stu-id="8b291-143">Dynamic—Communication is with an endpoint that is determined at run time.</span></span><br /><br /> <span data-ttu-id="8b291-144">以后指定 — 通信是由管理员在配置时的终结点。</span><span class="sxs-lookup"><span data-stu-id="8b291-144">Specify later—Communication is with an endpoint that is determined by an administrator at configuration time.</span></span><br /><br /> <span data-ttu-id="8b291-145">立即指定 — 通信是在设计时已知的终结点。</span><span class="sxs-lookup"><span data-stu-id="8b291-145">Specify now—Communication is with an endpoint that is known at design time.</span></span>|  
    |<span data-ttu-id="8b291-146">Identifier</span><span class="sxs-lookup"><span data-stu-id="8b291-146">Identifier</span></span>|<span data-ttu-id="8b291-147">此端口在业务流程中使用的名称。</span><span class="sxs-lookup"><span data-stu-id="8b291-147">The name used for this port in the orchestration.</span></span>|  
    |<span data-ttu-id="8b291-148">按序的送达</span><span class="sxs-lookup"><span data-stu-id="8b291-148">Ordered Delivery</span></span>|<span data-ttu-id="8b291-149">对于接收端口，可确保发布到 MessageBox 数据库中给定订单的消息将传送到按相同顺序发布到消息框中的每个匹配的订户。</span><span class="sxs-lookup"><span data-stu-id="8b291-149">For receive ports, ensures that messages that are published to the MessageBox database in a given order are delivered to each matching subscriber in the same order in which they were published to the message box.</span></span> <span data-ttu-id="8b291-150">有关详细信息，请参阅[的消息按序送达](../core/ordered-delivery-of-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="8b291-150">For more information, see [Ordered Delivery of Messages](../core/ordered-delivery-of-messages.md).</span></span>|  
    |<span data-ttu-id="8b291-151">送达通知</span><span class="sxs-lookup"><span data-stu-id="8b291-151">Delivery Notification</span></span>|<span data-ttu-id="8b291-152">对于发送端口，确定是否想要接收确认已成功发送消息。</span><span class="sxs-lookup"><span data-stu-id="8b291-152">For send ports, determines whether want to receive an acknowledgment when a message is sent successfully.</span></span> <span data-ttu-id="8b291-153">详细信息，请参阅"送达通知"中[如何配置发送形状](../core/how-to-configure-the-send-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="8b291-153">For more information, see "Delivery Notification" in [How to Configure the Send Shape](../core/how-to-configure-the-send-shape.md).</span></span>|  
  
3.  <span data-ttu-id="8b291-154">剩余的属性来指定由**绑定**属性：</span><span class="sxs-lookup"><span data-stu-id="8b291-154">The remaining properties to specify are determined by the **Binding** property:</span></span>  
  
    -   <span data-ttu-id="8b291-155">直接绑定 — 与另一个业务流程直接通信时使用。</span><span class="sxs-lookup"><span data-stu-id="8b291-155">Direct binding—Used when communicating directly with another orchestration.</span></span>  
  
        |<span data-ttu-id="8b291-156">属性</span><span class="sxs-lookup"><span data-stu-id="8b291-156">Property</span></span>|<span data-ttu-id="8b291-157">Description</span><span class="sxs-lookup"><span data-stu-id="8b291-157">Description</span></span>|  
        |--------------|-----------------|  
        |<span data-ttu-id="8b291-158">合作伙伴业务流程端口</span><span class="sxs-lookup"><span data-stu-id="8b291-158">Partner Orchestration Port</span></span>|<span data-ttu-id="8b291-159">确定哪一个端口到合作伙伴业务流程直接绑定。</span><span class="sxs-lookup"><span data-stu-id="8b291-159">Determines to which port the partner orchestrations will be directly bound.</span></span>|  
  
    -   <span data-ttu-id="8b291-160">动态绑定 — 在运行时确定的终结点进行通信时使用。</span><span class="sxs-lookup"><span data-stu-id="8b291-160">Dynamic binding—Used when communicating with an endpoint that is determined at run time.</span></span>  
  
        |<span data-ttu-id="8b291-161">属性</span><span class="sxs-lookup"><span data-stu-id="8b291-161">Property</span></span>|<span data-ttu-id="8b291-162">Description</span><span class="sxs-lookup"><span data-stu-id="8b291-162">Description</span></span>|  
        |--------------|-----------------|  
        |<span data-ttu-id="8b291-163">接收管道</span><span class="sxs-lookup"><span data-stu-id="8b291-163">Receive Pipeline</span></span>|<span data-ttu-id="8b291-164">确定使用传入消息的管道。</span><span class="sxs-lookup"><span data-stu-id="8b291-164">Determines which pipeline to use for incoming messages.</span></span>|  
        |<span data-ttu-id="8b291-165">发送管道</span><span class="sxs-lookup"><span data-stu-id="8b291-165">Send Pipeline</span></span>|<span data-ttu-id="8b291-166">确定管道用于传出消息。</span><span class="sxs-lookup"><span data-stu-id="8b291-166">Determines which pipeline to use for outgoing messages.</span></span>|  
  
    -   <span data-ttu-id="8b291-167">以后指定 — 由管理员配置的终结点进行通信时使用。</span><span class="sxs-lookup"><span data-stu-id="8b291-167">Specify later—Used when communicating with an endpoint that is configured by an administrator.</span></span>  
  
    -   <span data-ttu-id="8b291-168">立即指定 — 在设计时已知的终结点进行通信时使用。</span><span class="sxs-lookup"><span data-stu-id="8b291-168">Specify now—Used when communicating with an endpoint that is known at design time.</span></span>  
  
        |<span data-ttu-id="8b291-169">属性</span><span class="sxs-lookup"><span data-stu-id="8b291-169">Property</span></span>|<span data-ttu-id="8b291-170">Description</span><span class="sxs-lookup"><span data-stu-id="8b291-170">Description</span></span>|  
        |--------------|-----------------|  
        |<span data-ttu-id="8b291-171">接收管道</span><span class="sxs-lookup"><span data-stu-id="8b291-171">Receive Pipeline</span></span>|<span data-ttu-id="8b291-172">确定使用传入消息的管道。</span><span class="sxs-lookup"><span data-stu-id="8b291-172">Determines which pipeline to use for incoming messages.</span></span>|  
        |<span data-ttu-id="8b291-173">发送管道</span><span class="sxs-lookup"><span data-stu-id="8b291-173">Send Pipeline</span></span>|<span data-ttu-id="8b291-174">确定管道用于传出消息。</span><span class="sxs-lookup"><span data-stu-id="8b291-174">Determines which pipeline to use for outgoing messages.</span></span>|  
        |<span data-ttu-id="8b291-175">Transport</span><span class="sxs-lookup"><span data-stu-id="8b291-175">Transport</span></span>|<span data-ttu-id="8b291-176">确定要用于发送消息的传输。</span><span class="sxs-lookup"><span data-stu-id="8b291-176">Determines which transport to use for sending messages.</span></span>|  
        |<span data-ttu-id="8b291-177">URI</span><span class="sxs-lookup"><span data-stu-id="8b291-177">URI</span></span>|<span data-ttu-id="8b291-178">确定将消息发送到何处。</span><span class="sxs-lookup"><span data-stu-id="8b291-178">Determines where to send messages.</span></span>|  
  
### <a name="to-add-a-port-operation"></a><span data-ttu-id="8b291-179">若要添加端口操作</span><span class="sxs-lookup"><span data-stu-id="8b291-179">To add a port operation</span></span>  
  
-   <span data-ttu-id="8b291-180">右键单击你想要添加一个操作，然后单击的端口**新的操作**。</span><span class="sxs-lookup"><span data-stu-id="8b291-180">Right-click the port to which you want to add an operation, and then click **New Operation**.</span></span>  
  
### <a name="to-remove-a-port-operation"></a><span data-ttu-id="8b291-181">若要删除端口操作</span><span class="sxs-lookup"><span data-stu-id="8b291-181">To remove a port operation</span></span>  
  
-   <span data-ttu-id="8b291-182">右键单击端口操作以删除，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="8b291-182">Right-click the port operation to remove, and then click **Delete**.</span></span>