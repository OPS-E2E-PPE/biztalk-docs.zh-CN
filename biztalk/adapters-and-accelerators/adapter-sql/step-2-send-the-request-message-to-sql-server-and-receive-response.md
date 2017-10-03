---
title: "步骤 2： 将请求消息发送到 SQL Server，并接收响应 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 864d2174-d54b-4383-92bf-f6808a2a904b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce820ab6a1914e44239313588eaaefeb696e61d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-send-the-request-message-to-sql-server-and-receive-response"></a><span data-ttu-id="8bae2-102">步骤 2： 将请求消息发送到 SQL Server，并接收响应</span><span class="sxs-lookup"><span data-stu-id="8bae2-102">Step 2: Send the Request Message to SQL Server and Receive Response</span></span>
<span data-ttu-id="8bae2-103">![步骤 2 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")</span><span class="sxs-lookup"><span data-stu-id="8bae2-103">![Step 2 of 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")</span></span>  
  
 <span data-ttu-id="8bae2-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="8bae2-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="8bae2-105">**目标：**在此步骤中，你将发送要执行的请求消息**UPDATE_EMPLOYEE**存储过程和接收响应。</span><span class="sxs-lookup"><span data-stu-id="8bae2-105">**Objective:** In this step, you send the request message to execute the **UPDATE_EMPLOYEE** stored procedure and receive the response.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8bae2-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="8bae2-106">Prerequisites</span></span>  
 <span data-ttu-id="8bae2-107">你必须已完成[步骤 1： 为 UPDATE_EMPLOYEE 存储过程创建请求消息](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)。</span><span class="sxs-lookup"><span data-stu-id="8bae2-107">You must have completed [Step 1: Create the Request Message for UPDATE_EMPLOYEE Stored Procedure](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md).</span></span>  
  
### <a name="to-send-the-request-message-and-receive-a-response"></a><span data-ttu-id="8bae2-108">若要发送的请求消息和接收响应</span><span class="sxs-lookup"><span data-stu-id="8bae2-108">To send the request message and receive a response</span></span>  
  
1.  <span data-ttu-id="8bae2-109">与现有的业务流程下,**插入**块**确定**形状，添加**消息分配**形状。</span><span class="sxs-lookup"><span data-stu-id="8bae2-109">To the existing orchestration, under the **Insert** block of the **Decide** shape, add a **Message Assignment** shape.</span></span> <span data-ttu-id="8bae2-110">从工具箱中，拖动**消息分配**到空间形状指示。</span><span class="sxs-lookup"><span data-stu-id="8bae2-110">From the Toolbox, drag the **Message Assignment** shape to the space indicated.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8bae2-111">当删除**消息分配**形状拖到设计图面，业务流程设计器创建封闭**构造消息**为你的形状。</span><span class="sxs-lookup"><span data-stu-id="8bae2-111">When you drop the **Message Assignment** shape onto the design surface, Orchestration Designer creates the enclosing **Construct Message** shape for you.</span></span>  
  
2.  <span data-ttu-id="8bae2-112">在设计图面上，右键单击**ConstructMessage_1**形状，并依次**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="8bae2-112">On the design surface, right-click the **ConstructMessage_1** shape, and then click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="8bae2-113">在**属性**窗格**ConstructMessage_1**形状，指定以下值。</span><span class="sxs-lookup"><span data-stu-id="8bae2-113">In the **Properties** pane for the **ConstructMessage_1** shape, specify the following values.</span></span>  
  
    |<span data-ttu-id="8bae2-114">将此属性设置</span><span class="sxs-lookup"><span data-stu-id="8bae2-114">Set this property</span></span>|<span data-ttu-id="8bae2-115">为此值</span><span class="sxs-lookup"><span data-stu-id="8bae2-115">To this value</span></span>|  
    |-----------------------|-------------------|  
    |<span data-ttu-id="8bae2-116">**构造的消息**</span><span class="sxs-lookup"><span data-stu-id="8bae2-116">**Messages Constructed**</span></span>|<span data-ttu-id="8bae2-117">UpdateEmployee</span><span class="sxs-lookup"><span data-stu-id="8bae2-117">UpdateEmployee</span></span>|  
    |<span data-ttu-id="8bae2-118">**名称**</span><span class="sxs-lookup"><span data-stu-id="8bae2-118">**Name**</span></span>|<span data-ttu-id="8bae2-119">ConstructRequestMessage</span><span class="sxs-lookup"><span data-stu-id="8bae2-119">ConstructRequestMessage</span></span>|  
  
4.  <span data-ttu-id="8bae2-120">双击**MessageAssignment**形状以打开**BizTalk 表达式编辑器**。</span><span class="sxs-lookup"><span data-stu-id="8bae2-120">Double-click the **MessageAssignment** shape to open the **BizTalk Expression Editor**.</span></span>  
  
5.  <span data-ttu-id="8bae2-121">在**BizTalk 表达式编辑器**，添加以下：</span><span class="sxs-lookup"><span data-stu-id="8bae2-121">In the **BizTalk Expression Editor**, add the following:</span></span>  
  
    ```  
    UpdateEmployee = UpdateEmployeeMessageCreator.UpdateEmployeeMessageCreator.XMLMessageCreator();  
    UpdateEmployee(WCF.Action) = "TypedProcedure/dbo/UPDATE_EMPLOYEE";  
    ```  
  
     <span data-ttu-id="8bae2-122">在这里， **UpdateEmployee**是你在中创建一条消息[步骤 2： 创建 BizTalk 业务流程的消息](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)的发送请求消息**UPDATE_EMPLOYEE**存储过程。</span><span class="sxs-lookup"><span data-stu-id="8bae2-122">Here, **UpdateEmployee** is the message you created in [Step 2: Create Messages for BizTalk Orchestrations](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md) for sending request messages for **UPDATE_EMPLOYEE** stored procedure.</span></span> <span data-ttu-id="8bae2-123">在**MessageAssignment**调用形状， **UpdateEmployeeMessageCreator**类以创建的请求消息。</span><span class="sxs-lookup"><span data-stu-id="8bae2-123">In the **MessageAssignment** shape, you invoke the **UpdateEmployeeMessageCreator** class to create a request message.</span></span> <span data-ttu-id="8bae2-124">此外，你将设置请求消息的 WCF 操作。</span><span class="sxs-lookup"><span data-stu-id="8bae2-124">Also, you set the WCF action for the request message.</span></span>  
  
6.  <span data-ttu-id="8bae2-125">向下业务流程中添加以下形状**消息分配**形状。</span><span class="sxs-lookup"><span data-stu-id="8bae2-125">Add the following shapes to the orchestration under the **Message Assignment** shape.</span></span>  
  
    |<span data-ttu-id="8bae2-126">形状</span><span class="sxs-lookup"><span data-stu-id="8bae2-126">Shape</span></span>|<span data-ttu-id="8bae2-127">形状类型</span><span class="sxs-lookup"><span data-stu-id="8bae2-127">Shape Type</span></span>|<span data-ttu-id="8bae2-128">属性</span><span class="sxs-lookup"><span data-stu-id="8bae2-128">Properties</span></span>|  
    |-----------|----------------|----------------|  
    |<span data-ttu-id="8bae2-129">SendUpdateMessage</span><span class="sxs-lookup"><span data-stu-id="8bae2-129">SendUpdateMessage</span></span>|<span data-ttu-id="8bae2-130">Send</span><span class="sxs-lookup"><span data-stu-id="8bae2-130">Send</span></span>|<span data-ttu-id="8bae2-131">-将设置**消息**到*UpdateEmployee*</span><span class="sxs-lookup"><span data-stu-id="8bae2-131">-   Set **Message** to *UpdateEmployee*</span></span><br /><span data-ttu-id="8bae2-132">-将设置**名称**到*SendUpdateMessage*</span><span class="sxs-lookup"><span data-stu-id="8bae2-132">-   Set **Name** to *SendUpdateMessage*</span></span>|  
    |<span data-ttu-id="8bae2-133">ReceiveUpdateResponse</span><span class="sxs-lookup"><span data-stu-id="8bae2-133">ReceiveUpdateResponse</span></span>|<span data-ttu-id="8bae2-134">Receive</span><span class="sxs-lookup"><span data-stu-id="8bae2-134">Receive</span></span>|<span data-ttu-id="8bae2-135">-将设置**激活**到*False*</span><span class="sxs-lookup"><span data-stu-id="8bae2-135">-   Set **Activate** to *False*</span></span><br /><span data-ttu-id="8bae2-136">-将设置**消息**到*UpdateEmployeeResponse*</span><span class="sxs-lookup"><span data-stu-id="8bae2-136">-   Set **Message** to *UpdateEmployeeResponse*</span></span><br /><span data-ttu-id="8bae2-137">-将设置**名称**到*ReceiveUpdateResponse*</span><span class="sxs-lookup"><span data-stu-id="8bae2-137">-   Set **Name** to *ReceiveUpdateResponse*</span></span>|  
  
7.  <span data-ttu-id="8bae2-138">将请求-响应发送端口添加到业务流程。</span><span class="sxs-lookup"><span data-stu-id="8bae2-138">Add a request-response send port to the orchestration.</span></span> <span data-ttu-id="8bae2-139">你将使用此端口将请求消息发送到 SQL Server 和接收响应。</span><span class="sxs-lookup"><span data-stu-id="8bae2-139">You will use this port to send request messages to the SQL Server and receive response.</span></span> <span data-ttu-id="8bae2-140">设置以下属性的端口。</span><span class="sxs-lookup"><span data-stu-id="8bae2-140">Set the following properties for the port.</span></span>  
  
    |<span data-ttu-id="8bae2-141">将此属性设置</span><span class="sxs-lookup"><span data-stu-id="8bae2-141">Set this property</span></span>|<span data-ttu-id="8bae2-142">为此值</span><span class="sxs-lookup"><span data-stu-id="8bae2-142">To this value</span></span>|  
    |-----------------------|-------------------|  
    |<span data-ttu-id="8bae2-143">**通信方向**</span><span class="sxs-lookup"><span data-stu-id="8bae2-143">**Communication Direction**</span></span>|<span data-ttu-id="8bae2-144">发送-接收</span><span class="sxs-lookup"><span data-stu-id="8bae2-144">Send-Receive</span></span>|  
    |<span data-ttu-id="8bae2-145">**通信模式**</span><span class="sxs-lookup"><span data-stu-id="8bae2-145">**Communication Pattern**</span></span>|<span data-ttu-id="8bae2-146">请求-响应</span><span class="sxs-lookup"><span data-stu-id="8bae2-146">Request-Response</span></span>|  
    |<span data-ttu-id="8bae2-147">**Identifier**</span><span class="sxs-lookup"><span data-stu-id="8bae2-147">**Identifier**</span></span>|<span data-ttu-id="8bae2-148">SQLOutboundPort</span><span class="sxs-lookup"><span data-stu-id="8bae2-148">SQLOutboundPort</span></span>|  
  
     <span data-ttu-id="8bae2-149">此外，从到 Operation_1 更改操作名称**UpdateEmp**。</span><span class="sxs-lookup"><span data-stu-id="8bae2-149">Also, change the operation name from Operation_1 to **UpdateEmp**.</span></span>  
  
8.  <span data-ttu-id="8bae2-150">端口连接到操作形状。</span><span class="sxs-lookup"><span data-stu-id="8bae2-150">Connect the port to action shapes.</span></span> <span data-ttu-id="8bae2-151">业务流程设计器中，在设计图面上拖动绿色箭头调整控点的操作形状的端口到相应的绿色句柄。</span><span class="sxs-lookup"><span data-stu-id="8bae2-151">In Orchestration Designer, on the design surface, drag the green arrow-shaped handle for the port to the corresponding green handle of the action shape.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8bae2-152">在此步骤中，使用拖放方法将端口连接到操作形状。</span><span class="sxs-lookup"><span data-stu-id="8bae2-152">In this step, you use the drag-and-drop method to connect ports to action shapes.</span></span> <span data-ttu-id="8bae2-153">您可以改用操作形状的操作属性，将操作形状连接到端口。</span><span class="sxs-lookup"><span data-stu-id="8bae2-153">You could instead use the operation property of an action shape to connect the action shape to a port.</span></span>  
  
     <span data-ttu-id="8bae2-154">连接的端口和操作形状，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8bae2-154">Connect the ports and action shapes as follows:</span></span>  
  
    -   <span data-ttu-id="8bae2-155">连接**SendUpdateMessage**操作形状上的与**请求**的 handle **SQLOutboundPort**。</span><span class="sxs-lookup"><span data-stu-id="8bae2-155">Connect the **SendUpdateMessage** action shape to the **Request** handle of the **SQLOutboundPort**.</span></span>  
  
    -   <span data-ttu-id="8bae2-156">连接**ReceiveUpdateResponse**操作形状上的与**响应**的 handle **SQLOutboundPort**。</span><span class="sxs-lookup"><span data-stu-id="8bae2-156">Connect the **ReceiveUpdateResponse** action shape to the **Response** handle of the **SQLOutboundPort**.</span></span>  
  
9. <span data-ttu-id="8bae2-157">下图显示正在进行中业务流程。</span><span class="sxs-lookup"><span data-stu-id="8bae2-157">The following figure shows the in-progress orchestration.</span></span>  
  
     <span data-ttu-id="8bae2-158">![更新业务流程能够发送更新消息](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-04-update-msg-orch.gif "sql_adap_tut_04_update_msg_orch")</span><span class="sxs-lookup"><span data-stu-id="8bae2-158">![Updated orchestration to send update message](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-04-update-msg-orch.gif "sql_adap_tut_04_update_msg_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="8bae2-159">内容回顾</span><span class="sxs-lookup"><span data-stu-id="8bae2-159">What did I just do?</span></span>  
 <span data-ttu-id="8bae2-160">你可以在此步骤中，来更新通过添加业务流程**MessageAssignment**形状，**发送**和**接收**形状和一个端口。</span><span class="sxs-lookup"><span data-stu-id="8bae2-160">In this step, you updated the orchestration by adding a **MessageAssignment** shape, **Send** and **Receive** shapes, and a port.</span></span> <span data-ttu-id="8bae2-161">连接形状，端口以将请求消息执行 UDPATE_EMPLOYEE 发送请求消息和接收响应。</span><span class="sxs-lookup"><span data-stu-id="8bae2-161">You connected the shapes and ports to send request message to execute the UDPATE_EMPLOYEE request message and receive the response.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8bae2-162">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8bae2-162">Next Steps</span></span>  
 <span data-ttu-id="8bae2-163">在下一步的步骤中，添加要调用插入操作的业务流程形状**Purchase_Order**表中所述[第 4 课： 执行采购订单表上的插入操作](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)。</span><span class="sxs-lookup"><span data-stu-id="8bae2-163">In the next step, you add orchestration shapes to invoke the Insert operation on the **Purchase_Order** table, as described in [Lesson 4: Perform an Insert Operation on the Purchase Order Table](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bae2-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8bae2-164">See Also</span></span>  
 <span data-ttu-id="8bae2-165">[步骤 1： 为 UPDATE_EMPLOYEE 创建请求消息存储过程](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="8bae2-165">[Step 1: Create the Request Message for UPDATE_EMPLOYEE Stored Procedure](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md) </span></span>  
 [<span data-ttu-id="8bae2-166">第 3 课： 执行存储的过程以选择新添加的员工</span><span class="sxs-lookup"><span data-stu-id="8bae2-166">Lesson 3: Execute a Stored Procedure to Select New Employees Added</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)