---
title: 步骤 3： 发送要插入记录和接收响应的请求消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a8a8906-7c7d-437c-9f04-345ad4ac460e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db97afa0de19e15e5005e5647279365ea6ba023b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224085"
---
# <a name="step-3-send-the-request-message-to-insert-records-and-receive-a-response"></a><span data-ttu-id="79fb1-102">步骤 3： 发送要插入记录和接收响应的请求消息</span><span class="sxs-lookup"><span data-stu-id="79fb1-102">Step 3: Send the Request Message to Insert Records and Receive a Response</span></span>
<span data-ttu-id="79fb1-103">![步骤 3 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="79fb1-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="79fb1-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="79fb1-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="79fb1-105">**目标：** 在此步骤中，你将发送要插入记录合并到的请求消息**Purchase_Order**表和接收响应。</span><span class="sxs-lookup"><span data-stu-id="79fb1-105">**Objective:** In this step, you send the request message to insert records into the **Purchase_Order** table and receive a response.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="79fb1-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="79fb1-106">Prerequisites</span></span>  
 <span data-ttu-id="79fb1-107">你必须已完成[步骤 2： 将 UPDATE_EMPLOYEE 响应消息映射到插入操作请求消息](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)。</span><span class="sxs-lookup"><span data-stu-id="79fb1-107">You must have completed [Step 2: Map the UPDATE_EMPLOYEE Response Message to Insert Operation Request Message](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md).</span></span>  
  
### <a name="to-send-the-request-message-and-receive-a-response"></a><span data-ttu-id="79fb1-108">若要发送的请求消息和接收响应</span><span class="sxs-lookup"><span data-stu-id="79fb1-108">To send the request message and receive a response</span></span>  
  
1.  <span data-ttu-id="79fb1-109">向下业务流程中添加以下形状**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="79fb1-109">Add the following shapes to the orchestration under the **Construct Message** shape.</span></span>  
  
    |<span data-ttu-id="79fb1-110">形状</span><span class="sxs-lookup"><span data-stu-id="79fb1-110">Shape</span></span>|<span data-ttu-id="79fb1-111">形状类型</span><span class="sxs-lookup"><span data-stu-id="79fb1-111">Shape Type</span></span>|<span data-ttu-id="79fb1-112">属性</span><span class="sxs-lookup"><span data-stu-id="79fb1-112">Properties</span></span>|  
    |-----------|----------------|----------------|  
    |<span data-ttu-id="79fb1-113">SendInsertMessage</span><span class="sxs-lookup"><span data-stu-id="79fb1-113">SendInsertMessage</span></span>|<span data-ttu-id="79fb1-114">Send</span><span class="sxs-lookup"><span data-stu-id="79fb1-114">Send</span></span>|<span data-ttu-id="79fb1-115">-将设置**消息**到*InsertPO*</span><span class="sxs-lookup"><span data-stu-id="79fb1-115">-   Set **Message** to *InsertPO*</span></span><br /><span data-ttu-id="79fb1-116">-将设置**名称**到*SendInsertMessage*</span><span class="sxs-lookup"><span data-stu-id="79fb1-116">-   Set **Name** to *SendInsertMessage*</span></span>|  
    |<span data-ttu-id="79fb1-117">ReceiveInsertResponse</span><span class="sxs-lookup"><span data-stu-id="79fb1-117">ReceiveInsertResponse</span></span>|<span data-ttu-id="79fb1-118">Receive</span><span class="sxs-lookup"><span data-stu-id="79fb1-118">Receive</span></span>|<span data-ttu-id="79fb1-119">-将设置**激活**到*False*</span><span class="sxs-lookup"><span data-stu-id="79fb1-119">-   Set **Activate** to *False*</span></span><br /><span data-ttu-id="79fb1-120">-将设置**消息**到*InsertPOResponse*</span><span class="sxs-lookup"><span data-stu-id="79fb1-120">-   Set **Message** to *InsertPOResponse*</span></span><br /><span data-ttu-id="79fb1-121">-将设置**名称**到*ReceiveInsertResponse*</span><span class="sxs-lookup"><span data-stu-id="79fb1-121">-   Set **Name** to *ReceiveInsertResponse*</span></span>|  
    |<span data-ttu-id="79fb1-122">SaveInsertResponse</span><span class="sxs-lookup"><span data-stu-id="79fb1-122">SaveInsertResponse</span></span>|<span data-ttu-id="79fb1-123">Send</span><span class="sxs-lookup"><span data-stu-id="79fb1-123">Send</span></span>|<span data-ttu-id="79fb1-124">-将设置**消息**到*InsertPOResponse*</span><span class="sxs-lookup"><span data-stu-id="79fb1-124">-   Set **Message** to *InsertPOResponse*</span></span><br /><span data-ttu-id="79fb1-125">-将设置**名称**到*SaveInsertResponse*</span><span class="sxs-lookup"><span data-stu-id="79fb1-125">-   Set **Name** to *SaveInsertResponse*</span></span>|  
  
2.  <span data-ttu-id="79fb1-126">修改**SQLOutboundPort**中创建[步骤 2： 将请求消息发送到 SQL Server 和接收响应](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)。</span><span class="sxs-lookup"><span data-stu-id="79fb1-126">Modify the **SQLOutboundPort** you created in [Step 2: Send the Request Message to SQL Server and Receive Response](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md).</span></span>  
  
    1.  <span data-ttu-id="79fb1-127">右键单击业务流程设计器中的端口，然后单击**新操作**。</span><span class="sxs-lookup"><span data-stu-id="79fb1-127">Right-click the port in the Orchestration Designer, and then click **New Operation**.</span></span> <span data-ttu-id="79fb1-128">若要添加新操作的端口形状更改**Operation_1**。</span><span class="sxs-lookup"><span data-stu-id="79fb1-128">The port shape changes to add a new operation, **Operation_1**.</span></span>  
  
    2.  <span data-ttu-id="79fb1-129">单击**Operation_1**并在属性窗口中，将更改到的标识符的值**InsertPO**。</span><span class="sxs-lookup"><span data-stu-id="79fb1-129">Click **Operation_1** and in the properties window, change the value of Identifier to **InsertPO**.</span></span>  
  
3.  <span data-ttu-id="79fb1-130">将单向发送端口添加到业务流程。</span><span class="sxs-lookup"><span data-stu-id="79fb1-130">Add a one-way send port to the orchestration.</span></span> <span data-ttu-id="79fb1-131">你将使用此端口发送插入操作的响应消息。</span><span class="sxs-lookup"><span data-stu-id="79fb1-131">You will use this port to send the response message for the Insert operation.</span></span> <span data-ttu-id="79fb1-132">设置以下属性的端口。</span><span class="sxs-lookup"><span data-stu-id="79fb1-132">Set the following properties for the port.</span></span>  
  
    |<span data-ttu-id="79fb1-133">将此属性设置</span><span class="sxs-lookup"><span data-stu-id="79fb1-133">Set this property</span></span>|<span data-ttu-id="79fb1-134">为此值</span><span class="sxs-lookup"><span data-stu-id="79fb1-134">To this value</span></span>|  
    |-----------------------|-------------------|  
    |<span data-ttu-id="79fb1-135">**通信方向**</span><span class="sxs-lookup"><span data-stu-id="79fb1-135">**Communication Direction**</span></span>|<span data-ttu-id="79fb1-136">Send</span><span class="sxs-lookup"><span data-stu-id="79fb1-136">Send</span></span>|  
    |<span data-ttu-id="79fb1-137">**通信模式**</span><span class="sxs-lookup"><span data-stu-id="79fb1-137">**Communication Pattern**</span></span>|<span data-ttu-id="79fb1-138">单向</span><span class="sxs-lookup"><span data-stu-id="79fb1-138">One-Way</span></span>|  
    |<span data-ttu-id="79fb1-139">**Identifier**</span><span class="sxs-lookup"><span data-stu-id="79fb1-139">**Identifier**</span></span>|<span data-ttu-id="79fb1-140">SaveResponsePort</span><span class="sxs-lookup"><span data-stu-id="79fb1-140">SaveResponsePort</span></span>|  
  
     <span data-ttu-id="79fb1-141">此外，从到 Operation_1 更改操作名称**InsertPO**。</span><span class="sxs-lookup"><span data-stu-id="79fb1-141">Also, change the operation name from Operation_1 to **InsertPO**.</span></span>  
  
4.  <span data-ttu-id="79fb1-142">端口连接到操作形状。</span><span class="sxs-lookup"><span data-stu-id="79fb1-142">Connect the port to action shapes.</span></span> <span data-ttu-id="79fb1-143">业务流程设计器中，在设计图面上拖动绿色箭头调整控点的操作形状的端口到相应的绿色句柄。</span><span class="sxs-lookup"><span data-stu-id="79fb1-143">In Orchestration Designer, on the design surface, drag the green arrow-shaped handle for the port to the corresponding green handle of the action shape.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="79fb1-144">在此步骤中，使用拖放方法将端口连接到操作形状。</span><span class="sxs-lookup"><span data-stu-id="79fb1-144">In this step, you use the drag-and-drop method to connect ports to action shapes.</span></span> <span data-ttu-id="79fb1-145">您可以改用操作形状的操作属性，将操作形状连接到端口。</span><span class="sxs-lookup"><span data-stu-id="79fb1-145">You could instead use the operation property of an action shape to connect the action shape to a port.</span></span>  
  
     <span data-ttu-id="79fb1-146">连接的端口和操作形状，如下所示：</span><span class="sxs-lookup"><span data-stu-id="79fb1-146">Connect the ports and action shapes as follows:</span></span>  
  
    -   <span data-ttu-id="79fb1-147">连接**SendInsertMessage**操作形状上的与**请求**的 handle **InsertPO**操作**SQLOutboundPort**。</span><span class="sxs-lookup"><span data-stu-id="79fb1-147">Connect the **SendInsertMessage** action shape to the **Request** handle of the **InsertPO** operation of the **SQLOutboundPort**.</span></span>  
  
    -   <span data-ttu-id="79fb1-148">连接**ReceiveInsertResponse**操作形状上的与**响应**的 handle **InsertPO**操作**SQLOutboundPort**。</span><span class="sxs-lookup"><span data-stu-id="79fb1-148">Connect the **ReceiveInsertResponse** action shape to the **Response** handle of the **InsertPO** operation of the **SQLOutboundPort**.</span></span>  
  
    -   <span data-ttu-id="79fb1-149">连接**SaveInsertResponse**操作形状上的与**请求**的 handle **SaveResponsePort**。</span><span class="sxs-lookup"><span data-stu-id="79fb1-149">Connect the **SaveInsertResponse** action shape to the **Request** handle of the **SaveResponsePort**.</span></span>  
  
5.  <span data-ttu-id="79fb1-150">下图显示正在进行中业务流程。</span><span class="sxs-lookup"><span data-stu-id="79fb1-150">The following figure shows the in-progress orchestration.</span></span>  
  
     <span data-ttu-id="79fb1-151">![完成业务流程](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-09-comp-orch.gif "sql_adap_tut_09_comp_orch")</span><span class="sxs-lookup"><span data-stu-id="79fb1-151">![Complete orchestration](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-09-comp-orch.gif "sql_adap_tut_09_comp_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="79fb1-152">内容回顾</span><span class="sxs-lookup"><span data-stu-id="79fb1-152">What did I just do?</span></span>  
 <span data-ttu-id="79fb1-153">发送请求以插入记录合并到**Purchase_Order**表和接收响应。</span><span class="sxs-lookup"><span data-stu-id="79fb1-153">You sent the request to insert records into the **Purchase_Order** table and receive a response.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="79fb1-154">后续步骤</span><span class="sxs-lookup"><span data-stu-id="79fb1-154">Next Steps</span></span>  
 <span data-ttu-id="79fb1-155">中所述生成项目时，[步骤 4： 生成项目](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md)。</span><span class="sxs-lookup"><span data-stu-id="79fb1-155">You build the project, as described in [Step 4: Build the Project](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79fb1-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79fb1-156">See Also</span></span>  
 <span data-ttu-id="79fb1-157">[步骤 2： 映射要插入操作的请求消息的 UPDATE_EMPLOYEE 响应消息](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md) </span><span class="sxs-lookup"><span data-stu-id="79fb1-157">[Step 2: Map the UPDATE_EMPLOYEE Response Message to Insert Operation Request Message](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md) </span></span>  
 <span data-ttu-id="79fb1-158">[步骤 4： 生成项目](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md) </span><span class="sxs-lookup"><span data-stu-id="79fb1-158">[Step 4: Build the Project](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md) </span></span>  
 [<span data-ttu-id="79fb1-159">第 4 课： 执行插入操作上采购订单表</span><span class="sxs-lookup"><span data-stu-id="79fb1-159">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)