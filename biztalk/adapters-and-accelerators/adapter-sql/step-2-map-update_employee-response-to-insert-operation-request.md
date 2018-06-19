---
title: 步骤 2： 映射要插入操作的请求消息的 UPDATE_EMPLOYEE 响应消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d12014a-0147-4227-88fa-0b290eff4cce
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29a7cef00860f32aa2a493cc401e5d49d223ad3a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224821"
---
# <a name="step-2-map-the-updateemployee-response-message-to-insert-operation-request-message"></a><span data-ttu-id="3d779-102">步骤 2： 映射要插入操作的请求消息的 UPDATE_EMPLOYEE 响应消息</span><span class="sxs-lookup"><span data-stu-id="3d779-102">Step 2: Map the UPDATE_EMPLOYEE Response Message to Insert Operation Request Message</span></span>
<span data-ttu-id="3d779-103">![步骤 2 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="3d779-103">![Step 2 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  
  
 <span data-ttu-id="3d779-104">**完成时间：** 10 分钟</span><span class="sxs-lookup"><span data-stu-id="3d779-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="3d779-105">**目标：** 在此步骤中，创建要在执行插入操作的请求消息**Purchase_Order**表，然后将映射的响应消息**UPDATE_EMPLOYEE**存储插入操作的请求消息的过程。</span><span class="sxs-lookup"><span data-stu-id="3d779-105">**Objective:** In this step, you create the request message to perform an Insert operation on the **Purchase_Order** table and then map the response message for the **UPDATE_EMPLOYEE** stored procedure to the request message for the Insert operation.</span></span> <span data-ttu-id="3d779-106">通过这样做，你要插入的响应消息中的值将传递**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="3d779-106">By doing so, you pass on the values in the response message to be inserted in the **Purchase_Order** table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3d779-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="3d779-107">Prerequisites</span></span>  
 <span data-ttu-id="3d779-108">你必须已完成[步骤 1： 为 Purchase_Order 表的插入操作创建请求消息](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md)。</span><span class="sxs-lookup"><span data-stu-id="3d779-108">You must have completed [Step 1: Create the Request Message for Insert Operation on Purchase_Order Table](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md).</span></span>  
  
### <a name="to-map-the-messages"></a><span data-ttu-id="3d779-109">若要将消息映射</span><span class="sxs-lookup"><span data-stu-id="3d779-109">To map the messages</span></span>  
  
1.  <span data-ttu-id="3d779-110">与现有的业务流程，在**插入**块**确定**形状下, **ReceiveUpdateResponse**形状，添加**消息分配**形状。</span><span class="sxs-lookup"><span data-stu-id="3d779-110">To the existing orchestration, in the **Insert** block of the **Decide** shape, under the **ReceiveUpdateResponse** shape, add a **Message Assignment** shape.</span></span> <span data-ttu-id="3d779-111">从工具箱中，拖动**消息分配**到空间形状指示。</span><span class="sxs-lookup"><span data-stu-id="3d779-111">From the Toolbox, drag the **Message Assignment** shape to the space indicated.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3d779-112">当删除**消息分配**形状拖到设计图面，业务流程设计器创建封闭**构造消息**为你的形状。</span><span class="sxs-lookup"><span data-stu-id="3d779-112">When you drop the **Message Assignment** shape onto the design surface, Orchestration Designer creates the enclosing **Construct Message** shape for you.</span></span>  
  
2.  <span data-ttu-id="3d779-113">在设计图面上，右键单击**ConstructMessage_1**形状，并依次**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="3d779-113">On the design surface, right-click the **ConstructMessage_1** shape, and then click **Properties Window**.</span></span>  
  
3.  <span data-ttu-id="3d779-114">在**属性**窗格**ConstructMessage_1**形状，指定以下值。</span><span class="sxs-lookup"><span data-stu-id="3d779-114">In the **Properties** pane for the **ConstructMessage_1** shape, specify the following values.</span></span>  
  
    |<span data-ttu-id="3d779-115">将此属性设置</span><span class="sxs-lookup"><span data-stu-id="3d779-115">Set this property</span></span>|<span data-ttu-id="3d779-116">为此值</span><span class="sxs-lookup"><span data-stu-id="3d779-116">To this value</span></span>|  
    |-----------------------|-------------------|  
    |<span data-ttu-id="3d779-117">**构造的消息**</span><span class="sxs-lookup"><span data-stu-id="3d779-117">**Messages Constructed**</span></span>|<span data-ttu-id="3d779-118">InsertPO</span><span class="sxs-lookup"><span data-stu-id="3d779-118">InsertPO</span></span>|  
    |<span data-ttu-id="3d779-119">**名称**</span><span class="sxs-lookup"><span data-stu-id="3d779-119">**Name**</span></span>|<span data-ttu-id="3d779-120">ConstructInsertMessage</span><span class="sxs-lookup"><span data-stu-id="3d779-120">ConstructInsertMessage</span></span>|  
  
4.  <span data-ttu-id="3d779-121">双击**MessageAssignment**形状以打开**BizTalk 表达式编辑器**。</span><span class="sxs-lookup"><span data-stu-id="3d779-121">Double-click the **MessageAssignment** shape to open the **BizTalk Expression Editor**.</span></span>  
  
5.  <span data-ttu-id="3d779-122">在**BizTalk 表达式编辑器**，添加以下：</span><span class="sxs-lookup"><span data-stu-id="3d779-122">In the **BizTalk Expression Editor**, add the following:</span></span>  
  
    ```  
    InsertPO = UpdatePOMessageCreator.UpdatePOMessageCreator.XMLMessageCreator();  
    InsertPO(WCF.Action) = "TableOp/Insert/dbo/Purchase_Order";  
    ```  
  
     <span data-ttu-id="3d779-123">在这里， **InsertPO**是你在中创建一条消息[步骤 2： 创建 BizTalk 业务流程的消息](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)发送的插入操作的请求消息**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="3d779-123">Here, **InsertPO** is the message you created in [Step 2: Create Messages for BizTalk Orchestrations](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md) for sending request messages for Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="3d779-124">在**MessageAssignment**调用形状， **UpdatePOMessageCreator**类以创建的请求消息。</span><span class="sxs-lookup"><span data-stu-id="3d779-124">In the **MessageAssignment** shape, you invoke the **UpdatePOMessageCreator** class to create a request message.</span></span> <span data-ttu-id="3d779-125">此外，你将设置请求消息的 WCF 操作。</span><span class="sxs-lookup"><span data-stu-id="3d779-125">Also, you set the WCF action for the request message.</span></span>  
  
6.  <span data-ttu-id="3d779-126">在**构造消息**形状和后**消息分配**形状，添加**转换**形状。</span><span class="sxs-lookup"><span data-stu-id="3d779-126">Within the **Construct Message** shape and after the **Message Assignment** shape, add a **Transform** shape.</span></span>  
  
7.  <span data-ttu-id="3d779-127">在**转换配置**对话框中，从左窗格中，在**转换**标签，请单击**源**。</span><span class="sxs-lookup"><span data-stu-id="3d779-127">In the **Transform Configuration** dialog box, from the left pane, under the **Transform** label, click **Source**.</span></span>  
  
8.  <span data-ttu-id="3d779-128">从**源转换**在右侧框中，单击下的空间**变量名称**，然后选择**UpdateEmployeeResponse**。</span><span class="sxs-lookup"><span data-stu-id="3d779-128">From the **Source Transform** box on the right, click the space under the **Variable Name**, and then select **UpdateEmployeeResponse**.</span></span>  
  
     <span data-ttu-id="3d779-129">![选取源架构的映射](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-source-map.gif "sql_adap_tut_05_source_map")</span><span class="sxs-lookup"><span data-stu-id="3d779-129">![Pick the source schema for the mapping](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-source-map.gif "sql_adap_tut_05_source_map")</span></span>  
  
9. <span data-ttu-id="3d779-130">在**转换配置**对话框中，从左窗格中，在**转换**标签，请单击**目标**。</span><span class="sxs-lookup"><span data-stu-id="3d779-130">In the **Transform Configuration** dialog box, from the left pane, under the **Transform** label, click **Destination**.</span></span>  
  
10. <span data-ttu-id="3d779-131">从**目标转换**在右侧框中，单击下的空间**变量名称**，然后选择**InsertPO**。</span><span class="sxs-lookup"><span data-stu-id="3d779-131">From the **Destination Transform** box on the right, click the space under the **Variable Name**, and then select **InsertPO**.</span></span>  
  
     <span data-ttu-id="3d779-132">![选取映射目标架构](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-dest-map.gif "sql_adap_tut_05_dest_map")</span><span class="sxs-lookup"><span data-stu-id="3d779-132">![Pick the destination schema for mapping](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-dest-map.gif "sql_adap_tut_05_dest_map")</span></span>  
  
11. <span data-ttu-id="3d779-133">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="3d779-133">Click **OK**.</span></span> <span data-ttu-id="3d779-134">打开该映射文件。</span><span class="sxs-lookup"><span data-stu-id="3d779-134">The map file opens.</span></span>  
  
12. <span data-ttu-id="3d779-135">展开源和目标架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="3d779-135">Expand the nodes in the source and destination schemas.</span></span>  
  
13. <span data-ttu-id="3d779-136">映射 Employee_ID 并重命名这两个架构中的字段。</span><span class="sxs-lookup"><span data-stu-id="3d779-136">Map the Employee_ID and name fields in both the schemas.</span></span>  
  
    -   <span data-ttu-id="3d779-137">映射**Employee_ID**源架构 (UPDATE_EMPLOYEEResponse) 中的节点**Employee_ID**目标架构 (Insert) 中的节点。</span><span class="sxs-lookup"><span data-stu-id="3d779-137">Map the **Employee_ID** node in the source schema (UPDATE_EMPLOYEEResponse) to the **Employee_ID** node in the destination schema (Insert).</span></span>  
  
    -   <span data-ttu-id="3d779-138">映射**名称**到源架构中的节点**Employee_Name**目标架构中。</span><span class="sxs-lookup"><span data-stu-id="3d779-138">Map the **Name** node in the source schema to the **Employee_Name** in the destination schema.</span></span>  
  
     <span data-ttu-id="3d779-139">下图显示的映射的架构。</span><span class="sxs-lookup"><span data-stu-id="3d779-139">The following figure shows the mapped schemas.</span></span>  
  
     <span data-ttu-id="3d779-140">![映射源和目标架构](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-07-dest-map.gif "sql_adap_tut_07_dest_map")</span><span class="sxs-lookup"><span data-stu-id="3d779-140">![Map the source and destination schemas](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-07-dest-map.gif "sql_adap_tut_07_dest_map")</span></span>  
  
     <span data-ttu-id="3d779-141">保存并关闭该映射。</span><span class="sxs-lookup"><span data-stu-id="3d779-141">Save and close the map.</span></span>  
  
14. <span data-ttu-id="3d779-142">下图显示正在进行中业务流程。</span><span class="sxs-lookup"><span data-stu-id="3d779-142">The following figure shows the in-progress orchestration.</span></span>  
  
     <span data-ttu-id="3d779-143">![与转换形状的协调](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-08-map-orch.gif "sql_adap_tut_08_map_orch")</span><span class="sxs-lookup"><span data-stu-id="3d779-143">![Orchestration with the transform shape](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-08-map-orch.gif "sql_adap_tut_08_map_orch")</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="3d779-144">内容回顾</span><span class="sxs-lookup"><span data-stu-id="3d779-144">What did I just do?</span></span>  
 <span data-ttu-id="3d779-145">在此步骤中，创建要插入记录合并到的消息**Purchase_Order**表，并随后将映射从响应消息**UPDATE_EMPLOYEE**存储为插入的请求消息的过程操作。</span><span class="sxs-lookup"><span data-stu-id="3d779-145">In this step, you created a message to insert records into the **Purchase_Order** table and then mapped the response message from the **UPDATE_EMPLOYEE** stored procedure to the request message for the Insert operation.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3d779-146">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3d779-146">Next Steps</span></span>  
 <span data-ttu-id="3d779-147">发送请求消息上执行插入操作**Purchase_Order**表和中所述接收响应，[步骤 3： 将请求消息发送到插入的记录和接收响应](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)。</span><span class="sxs-lookup"><span data-stu-id="3d779-147">You send the request message to perform an Insert operation on the **Purchase_Order** table and receive a response, as described in [Step 3: Send the Request Message to Insert Records and Receive a Response](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d779-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d779-148">See Also</span></span>  
 <span data-ttu-id="3d779-149">[步骤 1： 为 Purchase_Order 表上插入操作创建的请求消息](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md) </span><span class="sxs-lookup"><span data-stu-id="3d779-149">[Step 1: Create the Request Message for Insert Operation on Purchase_Order Table](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md) </span></span>  
 [<span data-ttu-id="3d779-150">第 4 课： 执行插入操作上采购订单表</span><span class="sxs-lookup"><span data-stu-id="3d779-150">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)