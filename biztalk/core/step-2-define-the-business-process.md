---
title: 步骤 2： 定义业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b37bd9f1-5ee2-434d-950a-cf12967b6fc2
caps.latest.revision: 49
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 850b8b98764bc782dc62c6ebe792ace2d80ef0a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998102"
---
# <a name="step-2-define-the-business-process"></a><span data-ttu-id="d0d16-102">步骤 2：定义业务流程</span><span class="sxs-lookup"><span data-stu-id="d0d16-102">Step 2: Define the Business Process</span></span>
<span data-ttu-id="d0d16-103">![步骤 2，共 4 步](../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="d0d16-103">![Step 2 of 4](../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  
  
 <span data-ttu-id="d0d16-104">**完成时间：** 8 分钟</span><span class="sxs-lookup"><span data-stu-id="d0d16-104">**Time to complete:** 8 minutes</span></span>  
  
 <span data-ttu-id="d0d16-105">**目标：** 在此步骤中，您使用业务流程设计器来定义您的业务流程。</span><span class="sxs-lookup"><span data-stu-id="d0d16-105">**Objective:** In this step, you use Orchestration Designer to define your business process.</span></span>  
  
 <span data-ttu-id="d0d16-106">**目的：** 业务流程的工作流表示和自动执行用于审批库存补货请求你公司的业务流程。</span><span class="sxs-lookup"><span data-stu-id="d0d16-106">**Purpose:** The workflow of the orchestration represents and automates your company's business process for approving inventory replenishment requests.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d0d16-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="d0d16-107">Prerequisites</span></span>  
 <span data-ttu-id="d0d16-108">在开始此步骤之前，请注意以下要求：</span><span class="sxs-lookup"><span data-stu-id="d0d16-108">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="d0d16-109">在开始此步骤之前，必须完成[步骤 1： 向解决方案添加 EAIOrchestration 项目](../core/step-1-add-eaiorchestration-project-to-the-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="d0d16-109">Before you begin this step you must complete [Step 1: Add EAIOrchestration Project to the Solution](../core/step-1-add-eaiorchestration-project-to-the-solution.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="d0d16-110">过程</span><span class="sxs-lookup"><span data-stu-id="d0d16-110">Procedures</span></span>  
 <span data-ttu-id="d0d16-111">开发业务流程的第一步是使用操作形状来表示业务流程。</span><span class="sxs-lookup"><span data-stu-id="d0d16-111">The first step for developing an orchestration is to use action shapes to represent the business process.</span></span>  
  
#### <a name="to-create-the-eai-business-process-workflow"></a><span data-ttu-id="d0d16-112">创建 EAI 业务流程工作流</span><span class="sxs-lookup"><span data-stu-id="d0d16-112">To create the EAI business process workflow</span></span>  
  
1. <span data-ttu-id="d0d16-113">从 Visual Studio 中，在解决方案资源管理器中双击**EAIProcess.odx**若要打开业务流程。</span><span class="sxs-lookup"><span data-stu-id="d0d16-113">From Visual Studio, in Solution Explorer, double-click **EAIProcess.odx** to open the orchestration.</span></span>  
  
2. <span data-ttu-id="d0d16-114">在业务流程设计器中，从业务流程工具箱中拖动**接收**形状，并将其之间放置**开始**（绿色圆形） 和**最终**（红色八边形） 形状。</span><span class="sxs-lookup"><span data-stu-id="d0d16-114">In Orchestration Designer, from the orchestration Toolbox, drag the **Receive** shape, and drop it between the **Begin** (green circle) and **End** (red octagon) shapes.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d0d16-115">如果工具箱未打开，请在**视图**菜单上，单击**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-115">If the Toolbox is not open, in the **View** menu, click **Toolbox**.</span></span> <span data-ttu-id="d0d16-116">若要将其停靠在屏幕上，请单击图钉图标。</span><span class="sxs-lookup"><span data-stu-id="d0d16-116">To anchor it on the screen, click the thumbtack icon.</span></span>  
  
3. <span data-ttu-id="d0d16-117">从工具箱中拖动**判定**接收形状下方的形状。</span><span class="sxs-lookup"><span data-stu-id="d0d16-117">From the toolbox, drag the **Decide** shape beneath the Receive shape.</span></span>  
  
4. <span data-ttu-id="d0d16-118">从工具箱中拖动**转换**左分支的判定形状的形状。</span><span class="sxs-lookup"><span data-stu-id="d0d16-118">From the toolbox, drag the **Transform** shape to the left branch of the Decide shape.</span></span> <span data-ttu-id="d0d16-119">“转换”形状将嵌套在“构造消息”形状的内部。</span><span class="sxs-lookup"><span data-stu-id="d0d16-119">The Transform shape is nested inside the Construct Message shape.</span></span>  
  
5. <span data-ttu-id="d0d16-120">从工具箱中拖动**发送**转换形状下方的形状。</span><span class="sxs-lookup"><span data-stu-id="d0d16-120">From the toolbox, drag the **Send** shape beneath the Transform shape.</span></span>  
  
6. <span data-ttu-id="d0d16-121">从工具箱中拖动**发送**判定形状的右分支的形状。</span><span class="sxs-lookup"><span data-stu-id="d0d16-121">From the toolbox, drag the **Send** shape to the right branch of the Decide shape.</span></span>  <span data-ttu-id="d0d16-122">在您添加操作形状之后，业务流程将如下所示：</span><span class="sxs-lookup"><span data-stu-id="d0d16-122">The orchestration looks like the following after you added the action shapes:</span></span>  
  
    <span data-ttu-id="d0d16-123">![EAI 过程](../core/media/eaiprocess.gif "EAIProcess")</span><span class="sxs-lookup"><span data-stu-id="d0d16-123">![EAI process](../core/media/eaiprocess.gif "EAIProcess")</span></span>  
  
   <span data-ttu-id="d0d16-124">下一步是定义消息变量。</span><span class="sxs-lookup"><span data-stu-id="d0d16-124">The next step is to define message variables.</span></span>  <span data-ttu-id="d0d16-125">多个操作形状具有一个需要指定的消息属性。</span><span class="sxs-lookup"><span data-stu-id="d0d16-125">Several action shapes have a message property that needs to be specified.</span></span>  
  
#### <a name="to-define-message-variables"></a><span data-ttu-id="d0d16-126">定义消息变量</span><span class="sxs-lookup"><span data-stu-id="d0d16-126">To define message variables</span></span>  
  
1.  <span data-ttu-id="d0d16-127">从 Visual Studio 中，单击**视图**菜单上，单击**其他 Windows**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-127">From Visual Studio, click the **View** menu, click **Other Windows**, and then click **Orchestration View**.</span></span>  
  
2.  <span data-ttu-id="d0d16-128">从业务流程视图中，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-128">From Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
3.  <span data-ttu-id="d0d16-129">在“属性”窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0d16-129">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="d0d16-130">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d0d16-130">Use this</span></span>|<span data-ttu-id="d0d16-131">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d0d16-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d0d16-132">**Identifier**</span><span class="sxs-lookup"><span data-stu-id="d0d16-132">**Identifier**</span></span>|<span data-ttu-id="d0d16-133">类型**RequestMessage**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-133">Type **RequestMessage**.</span></span>|  
    |<span data-ttu-id="d0d16-134">**消息类型**</span><span class="sxs-lookup"><span data-stu-id="d0d16-134">**Message Type**</span></span>|<span data-ttu-id="d0d16-135">单击**架构**，然后单击**\<选择从引用的程序集...\>**.</span><span class="sxs-lookup"><span data-stu-id="d0d16-135">Click **Schemas**, and then click **\<Select from referenced assembly …\>**.</span></span> <span data-ttu-id="d0d16-136">从选择项目类型窗口中，单击**EAISchemas**，然后单击**请求**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-136">From the Select Artifact Type window, click **EAISchemas**, and then click **Request**.</span></span> <span data-ttu-id="d0d16-137">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-137">Click **OK**</span></span>|  
  
4.  <span data-ttu-id="d0d16-138">从业务流程视图中，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-138">From Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
5.  <span data-ttu-id="d0d16-139">在“属性”窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0d16-139">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="d0d16-140">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d0d16-140">Use this</span></span>|<span data-ttu-id="d0d16-141">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d0d16-141">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d0d16-142">**Identifier**</span><span class="sxs-lookup"><span data-stu-id="d0d16-142">**Identifier**</span></span>|<span data-ttu-id="d0d16-143">类型**RequestDeclineMessage**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-143">Type **RequestDeclineMessage**.</span></span>|  
    |<span data-ttu-id="d0d16-144">**消息类型**</span><span class="sxs-lookup"><span data-stu-id="d0d16-144">**Message Type**</span></span>|<span data-ttu-id="d0d16-145">单击**架构**，然后单击**\<选择从引用的程序集...\>**.</span><span class="sxs-lookup"><span data-stu-id="d0d16-145">Click **Schemas**, and then click **\<Select from referenced assembly …\>**.</span></span> <span data-ttu-id="d0d16-146">从选择项目类型窗口中，单击**EAISchemas**，然后单击**RequestDecline**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-146">From the Select Artifact Type window, click **EAISchemas**, and then click **RequestDecline**.</span></span> <span data-ttu-id="d0d16-147">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-147">Click **OK**</span></span>|  
  
#### <a name="to-configure-the-properties-of-the-shapes"></a><span data-ttu-id="d0d16-148">若要配置形状的属性</span><span class="sxs-lookup"><span data-stu-id="d0d16-148">To configure the properties of the shapes</span></span>  
  
1.  <span data-ttu-id="d0d16-149">在设计图面上，单击**接收**形状以将其选中。</span><span class="sxs-lookup"><span data-stu-id="d0d16-149">On the design surface, click the **Receive** shape to select it.</span></span>  
  
2.  <span data-ttu-id="d0d16-150">在“属性”窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0d16-150">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="d0d16-151">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d0d16-151">Use this</span></span>|<span data-ttu-id="d0d16-152">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d0d16-152">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d0d16-153">**名称**</span><span class="sxs-lookup"><span data-stu-id="d0d16-153">**Name**</span></span>|<span data-ttu-id="d0d16-154">类型**ReceiveRequest**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-154">Type **ReceiveRequest**.</span></span>|  
    |<span data-ttu-id="d0d16-155">**Message**</span><span class="sxs-lookup"><span data-stu-id="d0d16-155">**Message**</span></span>|<span data-ttu-id="d0d16-156">选择**RequestMessage**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-156">Select **RequestMessage**.</span></span>|  
    |<span data-ttu-id="d0d16-157">**Activate**</span><span class="sxs-lookup"><span data-stu-id="d0d16-157">**Activate**</span></span>|<span data-ttu-id="d0d16-158">从下拉列表中，选择 **，则返回 True**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-158">From the drop-down list, select **True**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="d0d16-159">如果未打开，请在属性窗口**视图**菜单上，单击**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-159">If the Property window is not open, in the **View** menu, click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="d0d16-160">在设计图面上，单击**判定**形状。</span><span class="sxs-lookup"><span data-stu-id="d0d16-160">On the design surface, click the **Decide** shape.</span></span>  
  
4.  <span data-ttu-id="d0d16-161">在“属性”窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0d16-161">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="d0d16-162">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d0d16-162">Use this</span></span>|<span data-ttu-id="d0d16-163">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d0d16-163">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d0d16-164">**名称**</span><span class="sxs-lookup"><span data-stu-id="d0d16-164">**Name**</span></span>|<span data-ttu-id="d0d16-165">类型**CheckGrandTotal**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-165">Type **CheckGrandTotal**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="d0d16-166">如果未打开，请在属性窗口**视图**菜单上，单击**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-166">If the Property window is not open, in the **View** menu, click **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="d0d16-167">在设计图面上，单击**Rule_1**形状。</span><span class="sxs-lookup"><span data-stu-id="d0d16-167">On the design surface, click the **Rule_1** shape.</span></span>  
  
6.  <span data-ttu-id="d0d16-168">在“属性”窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0d16-168">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="d0d16-169">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d0d16-169">Use this</span></span>|<span data-ttu-id="d0d16-170">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d0d16-170">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d0d16-171">**名称**</span><span class="sxs-lookup"><span data-stu-id="d0d16-171">**Name**</span></span>|<span data-ttu-id="d0d16-172">类型**DeclineRule**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-172">Type **DeclineRule**.</span></span>|  
    |<span data-ttu-id="d0d16-173">**表达式**</span><span class="sxs-lookup"><span data-stu-id="d0d16-173">**Expression**</span></span>|<span data-ttu-id="d0d16-174">单击省略号 (**...**)，然后键入`RequestMessage(EAISchemas.PropertySchema.GrandTotal ) > 10000`。</span><span class="sxs-lookup"><span data-stu-id="d0d16-174">Click the ellipses (**…**), and then type `RequestMessage(EAISchemas.PropertySchema.GrandTotal ) > 10000`.</span></span> <span data-ttu-id="d0d16-175">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="d0d16-175">Click **OK**.</span></span>|  
  
7.  <span data-ttu-id="d0d16-176">在设计图面上，单击**ConstructMessage_1**形状。</span><span class="sxs-lookup"><span data-stu-id="d0d16-176">On the design surface, click the **ConstructMessage_1** shape.</span></span>  
  
8.  <span data-ttu-id="d0d16-177">在“属性”窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0d16-177">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="d0d16-178">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d0d16-178">Use this</span></span>|<span data-ttu-id="d0d16-179">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d0d16-179">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d0d16-180">**名称**</span><span class="sxs-lookup"><span data-stu-id="d0d16-180">**Name**</span></span>|<span data-ttu-id="d0d16-181">类型**ConstructRequestDeclineMessage**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-181">Type **ConstructRequestDeclineMessage**.</span></span>|  
    |<span data-ttu-id="d0d16-182">**构造的消息**</span><span class="sxs-lookup"><span data-stu-id="d0d16-182">**Messages Constructed**</span></span>|<span data-ttu-id="d0d16-183">选择**RequestDeclineMessage**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-183">Select **RequestDeclineMessage**.</span></span>|  
  
9. <span data-ttu-id="d0d16-184">在设计图面上，单击**Transform_1**形状。</span><span class="sxs-lookup"><span data-stu-id="d0d16-184">On the design surface, click the **Transform_1** shape.</span></span>  
  
10. <span data-ttu-id="d0d16-185">在“属性”窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0d16-185">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="d0d16-186">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d0d16-186">Use this</span></span>|<span data-ttu-id="d0d16-187">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d0d16-187">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d0d16-188">**名称**</span><span class="sxs-lookup"><span data-stu-id="d0d16-188">**Name**</span></span>|<span data-ttu-id="d0d16-189">类型**TransformRequestToRequestDeclineMessage**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-189">Type **TransformRequestToRequestDeclineMessage**.</span></span>|  
    |<span data-ttu-id="d0d16-190">**映射名称**</span><span class="sxs-lookup"><span data-stu-id="d0d16-190">**Map Name**</span></span>|<span data-ttu-id="d0d16-191">单击 **...**.</span><span class="sxs-lookup"><span data-stu-id="d0d16-191">Click **…**.</span></span> <span data-ttu-id="d0d16-192">从“转换配置”中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0d16-192">From Transform Configuration, do the following:</span></span><br /><br /> <span data-ttu-id="d0d16-193">输入配置信息：</span><span class="sxs-lookup"><span data-stu-id="d0d16-193">Enter the configuration information:</span></span><br /><br /> <span data-ttu-id="d0d16-194">-单击**现有的映射**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-194">- Click **Existing Map**.</span></span><br /><br /> <span data-ttu-id="d0d16-195">完全限定的映射名称：</span><span class="sxs-lookup"><span data-stu-id="d0d16-195">Fully Qualified Map Name:</span></span><br /><br /> <span data-ttu-id="d0d16-196">-选择**\<从引用的程序集中\>**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-196">- Select **\<Select from referenced assembly\>**.</span></span>  <span data-ttu-id="d0d16-197">从左窗格中，选择**EAISchemas**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-197">From the left pane, select **EAISchemas**.</span></span>  <span data-ttu-id="d0d16-198">从右侧窗格中选择“EAISchemas.MapToReqDecline”。</span><span class="sxs-lookup"><span data-stu-id="d0d16-198">From the right pane, select EAISchemas.MapToReqDecline.</span></span>  <span data-ttu-id="d0d16-199">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="d0d16-199">Click **OK**.</span></span><br /><br /> <span data-ttu-id="d0d16-200">数据源</span><span class="sxs-lookup"><span data-stu-id="d0d16-200">Source</span></span><br /><br /> <span data-ttu-id="d0d16-201">-RequestMessage</span><span class="sxs-lookup"><span data-stu-id="d0d16-201">- RequestMessage</span></span><br /><br /> <span data-ttu-id="d0d16-202">目标</span><span class="sxs-lookup"><span data-stu-id="d0d16-202">Destination</span></span><br /><br /> <span data-ttu-id="d0d16-203">-RequestDeclineMessage</span><span class="sxs-lookup"><span data-stu-id="d0d16-203">- RequestDeclineMessage</span></span>|  
  
11. <span data-ttu-id="d0d16-204">在设计图面上，单击**Send_1**形状。</span><span class="sxs-lookup"><span data-stu-id="d0d16-204">On the design surface, click the **Send_1** shape.</span></span>  
  
12. <span data-ttu-id="d0d16-205">在“属性”窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0d16-205">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="d0d16-206">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d0d16-206">Use this</span></span>|<span data-ttu-id="d0d16-207">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d0d16-207">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d0d16-208">**名称**</span><span class="sxs-lookup"><span data-stu-id="d0d16-208">**Name**</span></span>|<span data-ttu-id="d0d16-209">类型**SendRequestDecline**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-209">Type **SendRequestDecline**.</span></span>|  
    |<span data-ttu-id="d0d16-210">**Message**</span><span class="sxs-lookup"><span data-stu-id="d0d16-210">**Message**</span></span>|<span data-ttu-id="d0d16-211">选择**RequestDeclineMessage**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-211">Select **RequestDeclineMessage**.</span></span>|  
  
13. <span data-ttu-id="d0d16-212">在设计图面上，单击**Send_2**形状。</span><span class="sxs-lookup"><span data-stu-id="d0d16-212">On the design surface, click the **Send_2** shape.</span></span>  
  
14. <span data-ttu-id="d0d16-213">在“属性”窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0d16-213">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="d0d16-214">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d0d16-214">Use this</span></span>|<span data-ttu-id="d0d16-215">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d0d16-215">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d0d16-216">**名称**</span><span class="sxs-lookup"><span data-stu-id="d0d16-216">**Name**</span></span>|<span data-ttu-id="d0d16-217">类型**SendRequestToERP**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-217">Type **SendRequestToERP**.</span></span>|  
    |<span data-ttu-id="d0d16-218">**Message**</span><span class="sxs-lookup"><span data-stu-id="d0d16-218">**Message**</span></span>|<span data-ttu-id="d0d16-219">选择**RequestMessage**。</span><span class="sxs-lookup"><span data-stu-id="d0d16-219">Select **RequestMessage**.</span></span>|  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="d0d16-220">内容回顾</span><span class="sxs-lookup"><span data-stu-id="d0d16-220">What did I just do?</span></span>  
 <span data-ttu-id="d0d16-221">在此步骤中，您使用业务流程设计器定义了业务流程。</span><span class="sxs-lookup"><span data-stu-id="d0d16-221">In this step, you used Orchestration Designer to define your business process.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d0d16-222">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d0d16-222">Next Steps</span></span>  
 <span data-ttu-id="d0d16-223">在业务流程中添加逻辑端口[第 3 步： 向业务流程添加端口](../core/step-3-add-ports-to-the-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="d0d16-223">You add logical ports to the orchestration in [Step 3: Add Ports to the Orchestration](../core/step-3-add-ports-to-the-orchestration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0d16-224">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0d16-224">See Also</span></span>  
 <span data-ttu-id="d0d16-225">[步骤 1： 向解决方案中添加 EAIOrchestration 项目](../core/step-1-add-eaiorchestration-project-to-the-solution.md) </span><span class="sxs-lookup"><span data-stu-id="d0d16-225">[Step 1: Add EAIOrchestration Project to the Solution](../core/step-1-add-eaiorchestration-project-to-the-solution.md) </span></span>  
 <span data-ttu-id="d0d16-226">[步骤 3： 将端口添加到业务流程](../core/step-3-add-ports-to-the-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="d0d16-226">[Step 3: Add Ports to the Orchestration](../core/step-3-add-ports-to-the-orchestration.md) </span></span>  
 [<span data-ttu-id="d0d16-227">第 4 步：生成 EAIOrchestration 项目</span><span class="sxs-lookup"><span data-stu-id="d0d16-227">Step 4: Build the EAIOrchestration Project</span></span>](../core/step-4-build-the-eaiorchestration-project.md)