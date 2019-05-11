---
title: 步骤 3：向业务流程添加端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 245df16e-d327-4c79-be85-004134d5ea6f
caps.latest.revision: 45
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 310c9b5640d8b975e2f11f7ab52d314236c0d43e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392697"
---
# <a name="step-3-add-ports-to-the-orchestration"></a><span data-ttu-id="5a896-102">步骤 3：向业务流程添加端口</span><span class="sxs-lookup"><span data-stu-id="5a896-102">Step 3: Add Ports to the Orchestration</span></span>
<span data-ttu-id="5a896-103">![步骤 3，共 4 步](../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="5a896-103">![Step 3 of 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="5a896-104">**若要完成的时间：** 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="5a896-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="5a896-105">**目标：** 在此步骤中，将向 EAIProcess 业务流程添加三个端口和配置它们。</span><span class="sxs-lookup"><span data-stu-id="5a896-105">**Objective:** In this step, you add three ports to the EAIProcess orchestration and configure them.</span></span>  
  
 <span data-ttu-id="5a896-106">**目的：** 端口指定如何将消息发送到您的业务流程和从其他业务流程接收消息。</span><span class="sxs-lookup"><span data-stu-id="5a896-106">**Purpose:** Ports specify how your orchestration will send messages to and receive messages from other business processes.</span></span> <span data-ttu-id="5a896-107">每个端口都具有一个类型、 方向和绑定，它们共同确定通信、 通信模式、 位置或从其发送或接收消息和如何进行通信的方向。</span><span class="sxs-lookup"><span data-stu-id="5a896-107">Each port has a type, a direction, and a binding, which together determine the direction of communication, the pattern of communication, the location to or from which the message is sent or received, and how the communication takes place.</span></span> <span data-ttu-id="5a896-108">创建和配置在此步骤中的三个端口实现以下角色：</span><span class="sxs-lookup"><span data-stu-id="5a896-108">The three ports you create and configure in this step fulfill the following roles:</span></span>  
  
- <span data-ttu-id="5a896-109">**ReceiveRequestPort**从仓库接收库存补货请求消息。</span><span class="sxs-lookup"><span data-stu-id="5a896-109">**ReceiveRequestPort** receives inventory replenishment request messages from the warehouse.</span></span>  
  
- <span data-ttu-id="5a896-110">**SendToERP**将转发到 ERP 系统的请求消息。</span><span class="sxs-lookup"><span data-stu-id="5a896-110">**SendToERP** forwards the request messages to the ERP system.</span></span>  
  
- <span data-ttu-id="5a896-111">**SendDeclinePort**将请求拒绝消息回仓库。</span><span class="sxs-lookup"><span data-stu-id="5a896-111">**SendDeclinePort** sends request decline messages back to the warehouse.</span></span>  
  
  <span data-ttu-id="5a896-112">有关详细信息，请参阅[业务流程中使用端口](../core/using-ports-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="5a896-112">For more information, see [Using Ports in Orchestrations](../core/using-ports-in-orchestrations.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5a896-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="5a896-113">Prerequisites</span></span>  
 <span data-ttu-id="5a896-114">在开始此步骤之前，请注意以下要求：</span><span class="sxs-lookup"><span data-stu-id="5a896-114">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="5a896-115">在开始此步骤之前，必须完成[步骤 2:定义业务流程](../core/step-2-define-the-business-process.md)。</span><span class="sxs-lookup"><span data-stu-id="5a896-115">Before you begin this step you must complete [Step 2: Define the Business Process](../core/step-2-define-the-business-process.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="5a896-116">过程</span><span class="sxs-lookup"><span data-stu-id="5a896-116">Procedures</span></span>  
  
#### <a name="to-create-and-configure-receiverequestport"></a><span data-ttu-id="5a896-117">若要创建和配置 ReceiveRequestPort</span><span class="sxs-lookup"><span data-stu-id="5a896-117">To create and configure ReceiveRequestPort</span></span>  
  
1.  <span data-ttu-id="5a896-118">在解决方案资源管理器中双击**EAIProcess.odx**。</span><span class="sxs-lookup"><span data-stu-id="5a896-118">In Solution Explorer, double-click **EAIProcess.odx**.</span></span>  
  
2.  <span data-ttu-id="5a896-119">在业务流程设计器中，从业务流程工具箱中拖动**端口**形状添加到左侧**端口图面**并行**ReceiveRequest**形状。</span><span class="sxs-lookup"><span data-stu-id="5a896-119">In Orchestration Designer, from the orchestration Toolbox, drag the **Port** shape to the left-side **Port Surface**, parallel to the **ReceiveRequest** shape.</span></span> <span data-ttu-id="5a896-120">端口配置向导会自动启动。</span><span class="sxs-lookup"><span data-stu-id="5a896-120">The Port Configuration Wizard starts automatically.</span></span>  
  
3.  <span data-ttu-id="5a896-121">在“欢迎使用端口配置向导”  页上，单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="5a896-121">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="5a896-122">上**端口属性**页上，执行以下操作，并单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="5a896-122">On the **Port Properties** page, do the following, and then click **Next**.</span></span>  
  
    |<span data-ttu-id="5a896-123">使用此选项</span><span class="sxs-lookup"><span data-stu-id="5a896-123">Use this</span></span>|<span data-ttu-id="5a896-124">执行的操作</span><span class="sxs-lookup"><span data-stu-id="5a896-124">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5a896-125">**名称**</span><span class="sxs-lookup"><span data-stu-id="5a896-125">**Name**</span></span>|<span data-ttu-id="5a896-126">类型**ReceiveRequestPort**。</span><span class="sxs-lookup"><span data-stu-id="5a896-126">Type **ReceiveRequestPort**.</span></span>|  
  
5.  <span data-ttu-id="5a896-127">上**选择端口类型**页上，执行以下操作，并单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="5a896-127">On the **Select a Port Type** page, do the following, and then click **Next**.</span></span>  
  
    |<span data-ttu-id="5a896-128">使用此选项</span><span class="sxs-lookup"><span data-stu-id="5a896-128">Use this</span></span>|<span data-ttu-id="5a896-129">执行的操作</span><span class="sxs-lookup"><span data-stu-id="5a896-129">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5a896-130">**选择要用于此端口的端口类型**</span><span class="sxs-lookup"><span data-stu-id="5a896-130">**Select the port type to be used for this port**</span></span>|<span data-ttu-id="5a896-131">选择**创建新的端口类型**选项。</span><span class="sxs-lookup"><span data-stu-id="5a896-131">Select the **Create a new Port Type** option.</span></span>|  
    |<span data-ttu-id="5a896-132">**端口类型名称：**</span><span class="sxs-lookup"><span data-stu-id="5a896-132">**Port Type Name:**</span></span>|<span data-ttu-id="5a896-133">类型**ReceiveRequestPortType**。</span><span class="sxs-lookup"><span data-stu-id="5a896-133">Type **ReceiveRequestPortType**.</span></span>|  
    |<span data-ttu-id="5a896-134">**通信模式**</span><span class="sxs-lookup"><span data-stu-id="5a896-134">**Communication Pattern**</span></span>|<span data-ttu-id="5a896-135">选择**单向**。</span><span class="sxs-lookup"><span data-stu-id="5a896-135">Select **One-Way**.</span></span>|  
    |<span data-ttu-id="5a896-136">**访问限制**</span><span class="sxs-lookup"><span data-stu-id="5a896-136">**Access Restrictions**</span></span>|<span data-ttu-id="5a896-137">选择**内部-仅限于此项目**。</span><span class="sxs-lookup"><span data-stu-id="5a896-137">Select **Internal - limited to this project**.</span></span>|  
  
6.  <span data-ttu-id="5a896-138">上**端口绑定**页上，执行以下操作，并单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="5a896-138">On the **Port Binding** page, do the following, and then click **Next**.</span></span>  
  
    |<span data-ttu-id="5a896-139">使用此选项</span><span class="sxs-lookup"><span data-stu-id="5a896-139">Use this</span></span>|<span data-ttu-id="5a896-140">执行的操作</span><span class="sxs-lookup"><span data-stu-id="5a896-140">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5a896-141">**端口通信方向**</span><span class="sxs-lookup"><span data-stu-id="5a896-141">**Port direction of communication**</span></span>|<span data-ttu-id="5a896-142">选择**我将始终接收此端口上的消息**。</span><span class="sxs-lookup"><span data-stu-id="5a896-142">Select **I'll always be receiving messages on this port**.</span></span>|  
    |<span data-ttu-id="5a896-143">**端口绑定**</span><span class="sxs-lookup"><span data-stu-id="5a896-143">**Port binding**</span></span>|<span data-ttu-id="5a896-144">在中，选择**以后指定**。</span><span class="sxs-lookup"><span data-stu-id="5a896-144">From select **Specify later**.</span></span>|  
  
7.  <span data-ttu-id="5a896-145">上**完成端口向导**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="5a896-145">On the **Completing the Port Wizard** page, click **Finish**.</span></span>  
  
#### <a name="to-create-and-configure-senddeclineport"></a><span data-ttu-id="5a896-146">若要创建和配置 SendDeclinePort</span><span class="sxs-lookup"><span data-stu-id="5a896-146">To create and configure SendDeclinePort</span></span>  
  
1.  <span data-ttu-id="5a896-147">从业务流程工具箱中拖动**端口**形状添加到左侧**端口图面**并行**SendRequestDecline**形状。</span><span class="sxs-lookup"><span data-stu-id="5a896-147">From the orchestration Toolbox, drag the **Port** shape to the left-side **Port Surface**, parallel to the **SendRequestDecline** shape.</span></span>  
  
2.  <span data-ttu-id="5a896-148">使用下表中的信息来创建**SendDeclinePort**发送端口。</span><span class="sxs-lookup"><span data-stu-id="5a896-148">Use the information in the following table to create the **SendDeclinePort** send port.</span></span>  
  
    |<span data-ttu-id="5a896-149">属性</span><span class="sxs-lookup"><span data-stu-id="5a896-149">Property</span></span>|<span data-ttu-id="5a896-150">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="5a896-150">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="5a896-151">**名称**</span><span class="sxs-lookup"><span data-stu-id="5a896-151">**Name**</span></span>|<span data-ttu-id="5a896-152">类型**SendDeclinePort**。</span><span class="sxs-lookup"><span data-stu-id="5a896-152">Type **SendDeclinePort**.</span></span>|  
    |<span data-ttu-id="5a896-153">**选择要用于此端口的端口类型**</span><span class="sxs-lookup"><span data-stu-id="5a896-153">**Select the port type to be used for this port**</span></span>|<span data-ttu-id="5a896-154">选择**创建新的端口类型**。</span><span class="sxs-lookup"><span data-stu-id="5a896-154">Select **Create a new Port Type**.</span></span>|  
    |<span data-ttu-id="5a896-155">**端口类型名称**</span><span class="sxs-lookup"><span data-stu-id="5a896-155">**Port Type Name**</span></span>|<span data-ttu-id="5a896-156">类型**SendDeclinePortType**。</span><span class="sxs-lookup"><span data-stu-id="5a896-156">Type **SendDeclinePortType**.</span></span>|  
    |<span data-ttu-id="5a896-157">**通信模式**</span><span class="sxs-lookup"><span data-stu-id="5a896-157">**Communication Pattern**</span></span>|<span data-ttu-id="5a896-158">选择**单向**。</span><span class="sxs-lookup"><span data-stu-id="5a896-158">Select **One-Way**.</span></span>|  
    |<span data-ttu-id="5a896-159">**访问限制**</span><span class="sxs-lookup"><span data-stu-id="5a896-159">**Access Restrictions**</span></span>|<span data-ttu-id="5a896-160">选择**内部-仅限于此项目**。</span><span class="sxs-lookup"><span data-stu-id="5a896-160">Select **Internal - limited to this project**.</span></span>|  
    |<span data-ttu-id="5a896-161">**端口通信方向**</span><span class="sxs-lookup"><span data-stu-id="5a896-161">**Port direction of communication**</span></span>|<span data-ttu-id="5a896-162">从下拉列表中，选择**我将始终在消息端口上发送此**。</span><span class="sxs-lookup"><span data-stu-id="5a896-162">From the drop-down list, select **I'll always be sending messages on this port**.</span></span>|  
    |<span data-ttu-id="5a896-163">**端口绑定**</span><span class="sxs-lookup"><span data-stu-id="5a896-163">**Port bindings**</span></span>|<span data-ttu-id="5a896-164">从下拉列表中，选择**以后指定**。</span><span class="sxs-lookup"><span data-stu-id="5a896-164">From the drop-down list, select **Specify later**.</span></span>|  
  
#### <a name="to-create-and-configure-sendtoerpport"></a><span data-ttu-id="5a896-165">若要创建和配置 SendToERPPort</span><span class="sxs-lookup"><span data-stu-id="5a896-165">To create and configure SendToERPPort</span></span>  
  
1.  <span data-ttu-id="5a896-166">从业务流程工具箱中拖动**端口**形状添加到右侧**端口图面**并行**SendToERP**形状。</span><span class="sxs-lookup"><span data-stu-id="5a896-166">From the orchestration Toolbox, drag the **Port** shape to the right-side **Port Surface**, parallel to the **SendToERP** shape.</span></span>  
  
2.  <span data-ttu-id="5a896-167">使用下表中的信息以完成端口配置向导**SendToERP**发送端口。</span><span class="sxs-lookup"><span data-stu-id="5a896-167">Use the information in the following table to complete the Port Configuration Wizard for the **SendToERP** send port.</span></span>  
  
    |<span data-ttu-id="5a896-168">属性</span><span class="sxs-lookup"><span data-stu-id="5a896-168">Property</span></span>|<span data-ttu-id="5a896-169">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="5a896-169">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="5a896-170">**名称**</span><span class="sxs-lookup"><span data-stu-id="5a896-170">**Name**</span></span>|<span data-ttu-id="5a896-171">类型**SendToERPPort**。</span><span class="sxs-lookup"><span data-stu-id="5a896-171">Type **SendToERPPort**.</span></span>|  
    |<span data-ttu-id="5a896-172">**选择要用于此端口的端口类型**</span><span class="sxs-lookup"><span data-stu-id="5a896-172">**Select the port type to be used for this port**</span></span>|<span data-ttu-id="5a896-173">选择**创建新的端口类型**。</span><span class="sxs-lookup"><span data-stu-id="5a896-173">Select **Create a new Port Type**.</span></span>|  
    |<span data-ttu-id="5a896-174">**端口类型名称**</span><span class="sxs-lookup"><span data-stu-id="5a896-174">**Port Type Name**</span></span>|<span data-ttu-id="5a896-175">类型**SendToERPPortType**。</span><span class="sxs-lookup"><span data-stu-id="5a896-175">Type **SendToERPPortType**.</span></span>|  
    |<span data-ttu-id="5a896-176">**通信模式**</span><span class="sxs-lookup"><span data-stu-id="5a896-176">**Communication Pattern**</span></span>|<span data-ttu-id="5a896-177">选择**单向**选项。</span><span class="sxs-lookup"><span data-stu-id="5a896-177">Select the **One-Way** option.</span></span>|  
    |<span data-ttu-id="5a896-178">**访问限制**</span><span class="sxs-lookup"><span data-stu-id="5a896-178">**Access Restrictions**</span></span>|<span data-ttu-id="5a896-179">选择**内部-仅限于此项目**选项。</span><span class="sxs-lookup"><span data-stu-id="5a896-179">Select the **Internal - limited to this project** option.</span></span>|  
    |<span data-ttu-id="5a896-180">**端口通信方向**</span><span class="sxs-lookup"><span data-stu-id="5a896-180">**Port direction of communication**</span></span>|<span data-ttu-id="5a896-181">从下拉列表中，选择**我将始终在消息端口上发送此**。</span><span class="sxs-lookup"><span data-stu-id="5a896-181">From the drop-down list, select **I'll always be sending messages on this port**.</span></span>|  
    |<span data-ttu-id="5a896-182">**端口绑定**</span><span class="sxs-lookup"><span data-stu-id="5a896-182">**Port binding**</span></span>|<span data-ttu-id="5a896-183">从下拉列表中，选择**以后指定**。</span><span class="sxs-lookup"><span data-stu-id="5a896-183">From the drop-down list, select **Specify later**.</span></span>|  
  
#### <a name="to-connect-the-ports-to-the-action-shapes"></a><span data-ttu-id="5a896-184">若要将端口连接到操作形状</span><span class="sxs-lookup"><span data-stu-id="5a896-184">To connect the ports to the action shapes</span></span>  
  
-   <span data-ttu-id="5a896-185">在业务流程设计器中，在设计图面上，将操作形状的每个端口到相应的绿色控点的绿色箭头状手柄:</span><span class="sxs-lookup"><span data-stu-id="5a896-185">In Orchestration Designer, on the design surface, drag the green arrow-shaped handle for each port to the corresponding green handle of the action shape:</span></span>  
  
    |<span data-ttu-id="5a896-186">此端口连接</span><span class="sxs-lookup"><span data-stu-id="5a896-186">Connect this port</span></span>|<span data-ttu-id="5a896-187">至此操作形状</span><span class="sxs-lookup"><span data-stu-id="5a896-187">To this action shape</span></span>|  
    |-----------------------|--------------------------|  
    |<span data-ttu-id="5a896-188">**ReceiveReqPort**</span><span class="sxs-lookup"><span data-stu-id="5a896-188">**ReceiveReqPort**</span></span>|<span data-ttu-id="5a896-189">**Receive_Request**</span><span class="sxs-lookup"><span data-stu-id="5a896-189">**Receive_Request**</span></span>|  
    |<span data-ttu-id="5a896-190">**SendDeclinePort**</span><span class="sxs-lookup"><span data-stu-id="5a896-190">**SendDeclinePort**</span></span>|<span data-ttu-id="5a896-191">**Send_ReqDenied**</span><span class="sxs-lookup"><span data-stu-id="5a896-191">**Send_ReqDenied**</span></span>|  
    |<span data-ttu-id="5a896-192">**SendToERP**</span><span class="sxs-lookup"><span data-stu-id="5a896-192">**SendToERP**</span></span>|<span data-ttu-id="5a896-193">**Send_ReqToERP**</span><span class="sxs-lookup"><span data-stu-id="5a896-193">**Send_ReqToERP**</span></span>|  
  
     <span data-ttu-id="5a896-194">下图显示了所有连接的端口的 EAIProcess 业务流程。</span><span class="sxs-lookup"><span data-stu-id="5a896-194">The following figure shows the EAIProcess orchestration with all of the ports connected.</span></span>  
  
     <span data-ttu-id="5a896-195">![具有已连接端口的 EAIProcess 业务流程。](../core/media/tut1-eaiprocessportsconnected.gif "Tut1_EAIProcessPortsConnected")</span><span class="sxs-lookup"><span data-stu-id="5a896-195">![EAIProcess orchestration with connected ports.](../core/media/tut1-eaiprocessportsconnected.gif "Tut1_EAIProcessPortsConnected")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="5a896-196">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="5a896-196">What did I just do?</span></span>  
 <span data-ttu-id="5a896-197">在此步骤中，将向 EAIProcess 业务流程添加了三个端口和配置它们。</span><span class="sxs-lookup"><span data-stu-id="5a896-197">In this step, you added three ports to the EAIProcess orchestration and configured them.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5a896-198">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5a896-198">Next Steps</span></span>  
 <span data-ttu-id="5a896-199">生成项目[步骤 4:生成 EAIOrchestration 项目](../core/step-4-build-the-eaiorchestration-project.md)。</span><span class="sxs-lookup"><span data-stu-id="5a896-199">You build the project in [Step 4: Build the EAIOrchestration Project](../core/step-4-build-the-eaiorchestration-project.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a896-200">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a896-200">See Also</span></span>  
 <span data-ttu-id="5a896-201">[步骤 1：向解决方案中添加 EAIOrchestration 项目](../core/step-1-add-eaiorchestration-project-to-the-solution.md) </span><span class="sxs-lookup"><span data-stu-id="5a896-201">[Step 1: Add EAIOrchestration Project to the Solution](../core/step-1-add-eaiorchestration-project-to-the-solution.md) </span></span>  
 <span data-ttu-id="5a896-202">[步骤 2：定义业务流程](../core/step-2-define-the-business-process.md) </span><span class="sxs-lookup"><span data-stu-id="5a896-202">[Step 2: Define the Business Process](../core/step-2-define-the-business-process.md) </span></span>  
 [<span data-ttu-id="5a896-203">步骤 4：生成 EAIOrchestration 项目</span><span class="sxs-lookup"><span data-stu-id="5a896-203">Step 4: Build the EAIOrchestration Project</span></span>](../core/step-4-build-the-eaiorchestration-project.md)