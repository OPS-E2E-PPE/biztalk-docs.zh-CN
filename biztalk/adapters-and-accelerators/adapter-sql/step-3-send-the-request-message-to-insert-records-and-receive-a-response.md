---
title: 步骤 3：发送要插入记录，并接收响应的请求消息 |Microsoft Docs
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
ms.openlocfilehash: f0db2560d1ef8db10e68b67eeb34e6531e03afd6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367686"
---
# <a name="step-3-send-the-request-message-to-insert-records-and-receive-a-response"></a><span data-ttu-id="9b88e-102">步骤 3：发送要插入记录，并接收响应的请求消息</span><span class="sxs-lookup"><span data-stu-id="9b88e-102">Step 3: Send the Request Message to Insert Records and Receive a Response</span></span>
<span data-ttu-id="9b88e-103">![步骤 3，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="9b88e-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="9b88e-104">**若要完成的时间：** 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="9b88e-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="9b88e-105">**目标：** 在此步骤中，将发送要插入到的记录的请求消息**Purchase_Order**表并接收响应。</span><span class="sxs-lookup"><span data-stu-id="9b88e-105">**Objective:** In this step, you send the request message to insert records into the **Purchase_Order** table and receive a response.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9b88e-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="9b88e-106">Prerequisites</span></span>  
 <span data-ttu-id="9b88e-107">你必须已完成[步骤 2:将 UPDATE_EMPLOYEE 响应消息插入操作请求消息映射](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)。</span><span class="sxs-lookup"><span data-stu-id="9b88e-107">You must have completed [Step 2: Map the UPDATE_EMPLOYEE Response Message to Insert Operation Request Message](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md).</span></span>  
  
### <a name="to-send-the-request-message-and-receive-a-response"></a><span data-ttu-id="9b88e-108">若要发送的请求消息并接收响应</span><span class="sxs-lookup"><span data-stu-id="9b88e-108">To send the request message and receive a response</span></span>  
  
1.  <span data-ttu-id="9b88e-109">将以下形状添加到在业务流程**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="9b88e-109">Add the following shapes to the orchestration under the **Construct Message** shape.</span></span>  
  
    |<span data-ttu-id="9b88e-110">形状</span><span class="sxs-lookup"><span data-stu-id="9b88e-110">Shape</span></span>|<span data-ttu-id="9b88e-111">形状类型</span><span class="sxs-lookup"><span data-stu-id="9b88e-111">Shape Type</span></span>|<span data-ttu-id="9b88e-112">属性</span><span class="sxs-lookup"><span data-stu-id="9b88e-112">Properties</span></span>|  
    |-----------|----------------|----------------|  
    |<span data-ttu-id="9b88e-113">SendInsertMessage</span><span class="sxs-lookup"><span data-stu-id="9b88e-113">SendInsertMessage</span></span>|<span data-ttu-id="9b88e-114">Send</span><span class="sxs-lookup"><span data-stu-id="9b88e-114">Send</span></span>|<span data-ttu-id="9b88e-115">-设置**消息**到*InsertPO*</span><span class="sxs-lookup"><span data-stu-id="9b88e-115">-   Set **Message** to *InsertPO*</span></span><br /><span data-ttu-id="9b88e-116">-设置**名称**到*SendInsertMessage*</span><span class="sxs-lookup"><span data-stu-id="9b88e-116">-   Set **Name** to *SendInsertMessage*</span></span>|  
    |<span data-ttu-id="9b88e-117">ReceiveInsertResponse</span><span class="sxs-lookup"><span data-stu-id="9b88e-117">ReceiveInsertResponse</span></span>|<span data-ttu-id="9b88e-118">Receive</span><span class="sxs-lookup"><span data-stu-id="9b88e-118">Receive</span></span>|<span data-ttu-id="9b88e-119">-设置**激活**到*False*</span><span class="sxs-lookup"><span data-stu-id="9b88e-119">-   Set **Activate** to *False*</span></span><br /><span data-ttu-id="9b88e-120">-设置**消息**到*InsertPOResponse*</span><span class="sxs-lookup"><span data-stu-id="9b88e-120">-   Set **Message** to *InsertPOResponse*</span></span><br /><span data-ttu-id="9b88e-121">-设置**名称**到*ReceiveInsertResponse*</span><span class="sxs-lookup"><span data-stu-id="9b88e-121">-   Set **Name** to *ReceiveInsertResponse*</span></span>|  
    |<span data-ttu-id="9b88e-122">SaveInsertResponse</span><span class="sxs-lookup"><span data-stu-id="9b88e-122">SaveInsertResponse</span></span>|<span data-ttu-id="9b88e-123">Send</span><span class="sxs-lookup"><span data-stu-id="9b88e-123">Send</span></span>|<span data-ttu-id="9b88e-124">-设置**消息**到*InsertPOResponse*</span><span class="sxs-lookup"><span data-stu-id="9b88e-124">-   Set **Message** to *InsertPOResponse*</span></span><br /><span data-ttu-id="9b88e-125">-设置**名称**到*SaveInsertResponse*</span><span class="sxs-lookup"><span data-stu-id="9b88e-125">-   Set **Name** to *SaveInsertResponse*</span></span>|  
  
2.  <span data-ttu-id="9b88e-126">修改**SQLOutboundPort**中创建[步骤 2:请求消息发送到 SQL Server 并接收响应](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)。</span><span class="sxs-lookup"><span data-stu-id="9b88e-126">Modify the **SQLOutboundPort** you created in [Step 2: Send the Request Message to SQL Server and Receive Response](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md).</span></span>  
  
    1.  <span data-ttu-id="9b88e-127">右键单击业务流程设计器中中的端口，然后单击**新的操作**。</span><span class="sxs-lookup"><span data-stu-id="9b88e-127">Right-click the port in the Orchestration Designer, and then click **New Operation**.</span></span> <span data-ttu-id="9b88e-128">添加新操作，使端口形状更改**Operation_1**。</span><span class="sxs-lookup"><span data-stu-id="9b88e-128">The port shape changes to add a new operation, **Operation_1**.</span></span>  
  
    2.  <span data-ttu-id="9b88e-129">单击**Operation_1**并在属性窗口中，将更改到的标识符的值**InsertPO**。</span><span class="sxs-lookup"><span data-stu-id="9b88e-129">Click **Operation_1** and in the properties window, change the value of Identifier to **InsertPO**.</span></span>  
  
3.  <span data-ttu-id="9b88e-130">将单向发送端口添加到业务流程。</span><span class="sxs-lookup"><span data-stu-id="9b88e-130">Add a one-way send port to the orchestration.</span></span> <span data-ttu-id="9b88e-131">将使用此端口来发送响应消息的插入操作。</span><span class="sxs-lookup"><span data-stu-id="9b88e-131">You will use this port to send the response message for the Insert operation.</span></span> <span data-ttu-id="9b88e-132">设置端口的以下属性。</span><span class="sxs-lookup"><span data-stu-id="9b88e-132">Set the following properties for the port.</span></span>  
  
    |<span data-ttu-id="9b88e-133">将此属性设置</span><span class="sxs-lookup"><span data-stu-id="9b88e-133">Set this property</span></span>|<span data-ttu-id="9b88e-134">为此值</span><span class="sxs-lookup"><span data-stu-id="9b88e-134">To this value</span></span>|  
    |-----------------------|-------------------|  
    |<span data-ttu-id="9b88e-135">**通信方向**</span><span class="sxs-lookup"><span data-stu-id="9b88e-135">**Communication Direction**</span></span>|<span data-ttu-id="9b88e-136">Send</span><span class="sxs-lookup"><span data-stu-id="9b88e-136">Send</span></span>|  
    |<span data-ttu-id="9b88e-137">**通信模式**</span><span class="sxs-lookup"><span data-stu-id="9b88e-137">**Communication Pattern**</span></span>|<span data-ttu-id="9b88e-138">单向</span><span class="sxs-lookup"><span data-stu-id="9b88e-138">One-Way</span></span>|  
    |<span data-ttu-id="9b88e-139">**Identifier**</span><span class="sxs-lookup"><span data-stu-id="9b88e-139">**Identifier**</span></span>|<span data-ttu-id="9b88e-140">SaveResponsePort</span><span class="sxs-lookup"><span data-stu-id="9b88e-140">SaveResponsePort</span></span>|  
  
     <span data-ttu-id="9b88e-141">此外，更改操作名称从为 Operation_1 **InsertPO**。</span><span class="sxs-lookup"><span data-stu-id="9b88e-141">Also, change the operation name from Operation_1 to **InsertPO**.</span></span>  
  
4.  <span data-ttu-id="9b88e-142">将端口连接到操作形状。</span><span class="sxs-lookup"><span data-stu-id="9b88e-142">Connect the port to action shapes.</span></span> <span data-ttu-id="9b88e-143">在业务流程设计器中，在设计图面上，将的操作形状的端口到相应的绿色句柄的绿色箭头状手柄。</span><span class="sxs-lookup"><span data-stu-id="9b88e-143">In Orchestration Designer, on the design surface, drag the green arrow-shaped handle for the port to the corresponding green handle of the action shape.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9b88e-144">在此步骤中，使用拖放方法将端口连接到操作形状。</span><span class="sxs-lookup"><span data-stu-id="9b88e-144">In this step, you use the drag-and-drop method to connect ports to action shapes.</span></span> <span data-ttu-id="9b88e-145">您可以改用操作形状的操作属性来操作形状连接到端口。</span><span class="sxs-lookup"><span data-stu-id="9b88e-145">You could instead use the operation property of an action shape to connect the action shape to a port.</span></span>  
  
     <span data-ttu-id="9b88e-146">按如下所示连接端口和操作形状：</span><span class="sxs-lookup"><span data-stu-id="9b88e-146">Connect the ports and action shapes as follows:</span></span>  
  
    -   <span data-ttu-id="9b88e-147">连接**SendInsertMessage**到操作形状**请求**的处理**InsertPO**操作**SQLOutboundPort**。</span><span class="sxs-lookup"><span data-stu-id="9b88e-147">Connect the **SendInsertMessage** action shape to the **Request** handle of the **InsertPO** operation of the **SQLOutboundPort**.</span></span>  
  
    -   <span data-ttu-id="9b88e-148">连接**ReceiveInsertResponse**到操作形状**响应**的处理**InsertPO**操作**SQLOutboundPort**。</span><span class="sxs-lookup"><span data-stu-id="9b88e-148">Connect the **ReceiveInsertResponse** action shape to the **Response** handle of the **InsertPO** operation of the **SQLOutboundPort**.</span></span>  
  
    -   <span data-ttu-id="9b88e-149">连接**SaveInsertResponse**到操作形状**请求**的处理**SaveResponsePort**。</span><span class="sxs-lookup"><span data-stu-id="9b88e-149">Connect the **SaveInsertResponse** action shape to the **Request** handle of the **SaveResponsePort**.</span></span>  
  
5.  <span data-ttu-id="9b88e-150">下图显示了正在进行中业务流程。</span><span class="sxs-lookup"><span data-stu-id="9b88e-150">The following figure shows the in-progress orchestration.</span></span>  
  
     <span data-ttu-id="9b88e-151">![完成业务流程](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-09-comp-orch.gif "sql_adap_tut_09_comp_orch")</span><span class="sxs-lookup"><span data-stu-id="9b88e-151">![Complete orchestration](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-09-comp-orch.gif "sql_adap_tut_09_comp_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="9b88e-152">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="9b88e-152">What did I just do?</span></span>  
 <span data-ttu-id="9b88e-153">发送请求以便将记录到**Purchase_Order**表并接收响应。</span><span class="sxs-lookup"><span data-stu-id="9b88e-153">You sent the request to insert records into the **Purchase_Order** table and receive a response.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9b88e-154">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9b88e-154">Next Steps</span></span>  
 <span data-ttu-id="9b88e-155">在生成项目，如中所述[步骤 4:生成项目](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md)。</span><span class="sxs-lookup"><span data-stu-id="9b88e-155">You build the project, as described in [Step 4: Build the Project](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b88e-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b88e-156">See Also</span></span>  
 <span data-ttu-id="9b88e-157">[步骤 2：将 UPDATE_EMPLOYEE 响应消息插入操作请求消息映射](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md) </span><span class="sxs-lookup"><span data-stu-id="9b88e-157">[Step 2: Map the UPDATE_EMPLOYEE Response Message to Insert Operation Request Message](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md) </span></span>  
 <span data-ttu-id="9b88e-158">[步骤 4：生成项目](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md) </span><span class="sxs-lookup"><span data-stu-id="9b88e-158">[Step 4: Build the Project](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md) </span></span>  
 [<span data-ttu-id="9b88e-159">第 4 课：在采购订单表中执行插入操作</span><span class="sxs-lookup"><span data-stu-id="9b88e-159">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)