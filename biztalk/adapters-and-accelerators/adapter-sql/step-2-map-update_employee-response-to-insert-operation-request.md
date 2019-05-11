---
title: 第 2 步：将 UPDATE_EMPLOYEE 响应消息插入操作请求消息映射 |Microsoft Docs
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
ms.openlocfilehash: 825eea8ba60d6b7767f9ea9b7536f8ed65470928
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367789"
---
# <a name="step-2-map-the-updateemployee-response-message-to-insert-operation-request-message"></a><span data-ttu-id="91b95-102">第 2 步：将 UPDATE_EMPLOYEE 响应消息插入操作请求消息映射</span><span class="sxs-lookup"><span data-stu-id="91b95-102">Step 2: Map the UPDATE_EMPLOYEE Response Message to Insert Operation Request Message</span></span>
<span data-ttu-id="91b95-103">![步骤 2，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="91b95-103">![Step 2 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  

 <span data-ttu-id="91b95-104">**若要完成的时间：** 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="91b95-104">**Time to complete:** 10 minutes</span></span>  

 <span data-ttu-id="91b95-105">**目标：** 在此步骤中，创建要在执行插入操作的请求消息**Purchase_Order**表，然后将映射的响应消息**UPDATE_EMPLOYEE**存储到请求的过程用于插入操作的消息。</span><span class="sxs-lookup"><span data-stu-id="91b95-105">**Objective:** In this step, you create the request message to perform an Insert operation on the **Purchase_Order** table and then map the response message for the **UPDATE_EMPLOYEE** stored procedure to the request message for the Insert operation.</span></span> <span data-ttu-id="91b95-106">这样做之后，您传递响应消息中要插入的值**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="91b95-106">By doing so, you pass on the values in the response message to be inserted in the **Purchase_Order** table.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="91b95-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="91b95-107">Prerequisites</span></span>  
 <span data-ttu-id="91b95-108">你必须已完成[步骤 1:为在 Purchase_Order 表的插入操作创建请求消息](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md)。</span><span class="sxs-lookup"><span data-stu-id="91b95-108">You must have completed [Step 1: Create the Request Message for Insert Operation on Purchase_Order Table](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md).</span></span>  

### <a name="to-map-the-messages"></a><span data-ttu-id="91b95-109">若要将消息映射</span><span class="sxs-lookup"><span data-stu-id="91b95-109">To map the messages</span></span>  

1. <span data-ttu-id="91b95-110">向现有业务流程中**插入**块**判定**形状，在**ReceiveUpdateResponse**形状中，添加**消息赋值**形状。</span><span class="sxs-lookup"><span data-stu-id="91b95-110">To the existing orchestration, in the **Insert** block of the **Decide** shape, under the **ReceiveUpdateResponse** shape, add a **Message Assignment** shape.</span></span> <span data-ttu-id="91b95-111">从工具箱拖动**消息赋值**到空间形状表示。</span><span class="sxs-lookup"><span data-stu-id="91b95-111">From the Toolbox, drag the **Message Assignment** shape to the space indicated.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="91b95-112">放置**消息赋值**形状拖到设计图面上，业务流程设计器创建封闭**构造消息**为你的形状。</span><span class="sxs-lookup"><span data-stu-id="91b95-112">When you drop the **Message Assignment** shape onto the design surface, Orchestration Designer creates the enclosing **Construct Message** shape for you.</span></span>  

2. <span data-ttu-id="91b95-113">在设计图面上，右键单击**ConstructMessage_1**形状，然后依次**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="91b95-113">On the design surface, right-click the **ConstructMessage_1** shape, and then click **Properties Window**.</span></span>  

3. <span data-ttu-id="91b95-114">在中**属性**窗格**ConstructMessage_1**形状中，指定以下值。</span><span class="sxs-lookup"><span data-stu-id="91b95-114">In the **Properties** pane for the **ConstructMessage_1** shape, specify the following values.</span></span>  


   |    <span data-ttu-id="91b95-115">将此属性设置</span><span class="sxs-lookup"><span data-stu-id="91b95-115">Set this property</span></span>     |     <span data-ttu-id="91b95-116">为此值</span><span class="sxs-lookup"><span data-stu-id="91b95-116">To this value</span></span>      |
   |--------------------------|------------------------|
   | <span data-ttu-id="91b95-117">**构造的消息**</span><span class="sxs-lookup"><span data-stu-id="91b95-117">**Messages Constructed**</span></span> |        <span data-ttu-id="91b95-118">InsertPO</span><span class="sxs-lookup"><span data-stu-id="91b95-118">InsertPO</span></span>        |
   |         <span data-ttu-id="91b95-119">**名称**</span><span class="sxs-lookup"><span data-stu-id="91b95-119">**Name**</span></span>         | <span data-ttu-id="91b95-120">ConstructInsertMessage</span><span class="sxs-lookup"><span data-stu-id="91b95-120">ConstructInsertMessage</span></span> |


4. <span data-ttu-id="91b95-121">双击**MessageAssignment**形状以打开**BizTalk 表达式编辑器**。</span><span class="sxs-lookup"><span data-stu-id="91b95-121">Double-click the **MessageAssignment** shape to open the **BizTalk Expression Editor**.</span></span>  

5. <span data-ttu-id="91b95-122">在中**BizTalk 表达式编辑器**，添加以下：</span><span class="sxs-lookup"><span data-stu-id="91b95-122">In the **BizTalk Expression Editor**, add the following:</span></span>  

   ```  
   InsertPO = UpdatePOMessageCreator.UpdatePOMessageCreator.XMLMessageCreator();  
   InsertPO(WCF.Action) = "TableOp/Insert/dbo/Purchase_Order";  
   ```  

    <span data-ttu-id="91b95-123">在这里， **InsertPO**是你在中创建的消息[步骤 2:为 BizTalk 业务流程创建消息](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)发送的插入操作的请求消息**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="91b95-123">Here, **InsertPO** is the message you created in [Step 2: Create Messages for BizTalk Orchestrations](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md) for sending request messages for Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="91b95-124">在中**MessageAssignment**形状中，调用**UpdatePOMessageCreator**类，以创建请求消息。</span><span class="sxs-lookup"><span data-stu-id="91b95-124">In the **MessageAssignment** shape, you invoke the **UpdatePOMessageCreator** class to create a request message.</span></span> <span data-ttu-id="91b95-125">此外，您设置请求消息的 WCF 操作。</span><span class="sxs-lookup"><span data-stu-id="91b95-125">Also, you set the WCF action for the request message.</span></span>  

6. <span data-ttu-id="91b95-126">内**构造消息**形状及**消息赋值**形状中，添加**转换**形状。</span><span class="sxs-lookup"><span data-stu-id="91b95-126">Within the **Construct Message** shape and after the **Message Assignment** shape, add a **Transform** shape.</span></span>  

7. <span data-ttu-id="91b95-127">在中**转换配置**对话框中，从左窗格中，在**转换**标记中，单击**源**。</span><span class="sxs-lookup"><span data-stu-id="91b95-127">In the **Transform Configuration** dialog box, from the left pane, under the **Transform** label, click **Source**.</span></span>  

8. <span data-ttu-id="91b95-128">从**源转换**在右侧框中，单击下的空间**变量的名称**，然后选择**UpdateEmployeeResponse**。</span><span class="sxs-lookup"><span data-stu-id="91b95-128">From the **Source Transform** box on the right, click the space under the **Variable Name**, and then select **UpdateEmployeeResponse**.</span></span>  

    <span data-ttu-id="91b95-129">![选择用于映射的源架构](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-source-map.gif "sql_adap_tut_05_source_map")</span><span class="sxs-lookup"><span data-stu-id="91b95-129">![Pick the source schema for the mapping](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-source-map.gif "sql_adap_tut_05_source_map")</span></span>  

9. <span data-ttu-id="91b95-130">在中**转换配置**对话框中，从左窗格中，在**转换**标记中，单击**目标**。</span><span class="sxs-lookup"><span data-stu-id="91b95-130">In the **Transform Configuration** dialog box, from the left pane, under the **Transform** label, click **Destination**.</span></span>  

10. <span data-ttu-id="91b95-131">从**目标转换**在右侧框中，单击下的空间**变量的名称**，然后选择**InsertPO**。</span><span class="sxs-lookup"><span data-stu-id="91b95-131">From the **Destination Transform** box on the right, click the space under the **Variable Name**, and then select **InsertPO**.</span></span>  

     <span data-ttu-id="91b95-132">![选择用于映射的目标架构](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-dest-map.gif "sql_adap_tut_05_dest_map")</span><span class="sxs-lookup"><span data-stu-id="91b95-132">![Pick the destination schema for mapping](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-dest-map.gif "sql_adap_tut_05_dest_map")</span></span>  

11. <span data-ttu-id="91b95-133">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="91b95-133">Click **OK**.</span></span> <span data-ttu-id="91b95-134">打开该映射文件。</span><span class="sxs-lookup"><span data-stu-id="91b95-134">The map file opens.</span></span>  

12. <span data-ttu-id="91b95-135">展开的源和目标架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="91b95-135">Expand the nodes in the source and destination schemas.</span></span>  

13. <span data-ttu-id="91b95-136">映射 Employee_ID 并命名为这两个架构中的字段。</span><span class="sxs-lookup"><span data-stu-id="91b95-136">Map the Employee_ID and name fields in both the schemas.</span></span>  

    - <span data-ttu-id="91b95-137">地图**Employee_ID**源架构 (UPDATE_EMPLOYEEResponse) 中的节点**Employee_ID**目标架构 (Insert) 中的节点。</span><span class="sxs-lookup"><span data-stu-id="91b95-137">Map the **Employee_ID** node in the source schema (UPDATE_EMPLOYEEResponse) to the **Employee_ID** node in the destination schema (Insert).</span></span>  

    - <span data-ttu-id="91b95-138">地图**名称**到源架构中的节点**Employee_Name**目标架构中。</span><span class="sxs-lookup"><span data-stu-id="91b95-138">Map the **Name** node in the source schema to the **Employee_Name** in the destination schema.</span></span>  

      <span data-ttu-id="91b95-139">下图显示了映射的架构。</span><span class="sxs-lookup"><span data-stu-id="91b95-139">The following figure shows the mapped schemas.</span></span>  

      <span data-ttu-id="91b95-140">![映射源和目标架构](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-07-dest-map.gif "sql_adap_tut_07_dest_map")</span><span class="sxs-lookup"><span data-stu-id="91b95-140">![Map the source and destination schemas](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-07-dest-map.gif "sql_adap_tut_07_dest_map")</span></span>  

      <span data-ttu-id="91b95-141">保存并关闭该映射。</span><span class="sxs-lookup"><span data-stu-id="91b95-141">Save and close the map.</span></span>  

14. <span data-ttu-id="91b95-142">下图显示了正在进行中业务流程。</span><span class="sxs-lookup"><span data-stu-id="91b95-142">The following figure shows the in-progress orchestration.</span></span>  

     <span data-ttu-id="91b95-143">![具有转换形状的业务流程](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-08-map-orch.gif "sql_adap_tut_08_map_orch")</span><span class="sxs-lookup"><span data-stu-id="91b95-143">![Orchestration with the transform shape](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-08-map-orch.gif "sql_adap_tut_08_map_orch")</span></span>  

## <a name="what-did-i-just-do"></a><span data-ttu-id="91b95-144">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="91b95-144">What did I just do?</span></span>  
 <span data-ttu-id="91b95-145">在此步骤中，创建要插入到的记录的消息**Purchase_Order**表并已进行映射的响应消息**UPDATE_EMPLOYEE**为插入存储过程的请求消息操作。</span><span class="sxs-lookup"><span data-stu-id="91b95-145">In this step, you created a message to insert records into the **Purchase_Order** table and then mapped the response message from the **UPDATE_EMPLOYEE** stored procedure to the request message for the Insert operation.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="91b95-146">后续步骤</span><span class="sxs-lookup"><span data-stu-id="91b95-146">Next Steps</span></span>  
 <span data-ttu-id="91b95-147">发送请求消息上执行插入操作**Purchase_Order**表并接收响应，如中所述[步骤 3:发送要插入记录，并接收响应的请求消息](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)。</span><span class="sxs-lookup"><span data-stu-id="91b95-147">You send the request message to perform an Insert operation on the **Purchase_Order** table and receive a response, as described in [Step 3: Send the Request Message to Insert Records and Receive a Response](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="91b95-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="91b95-148">See Also</span></span>  
 <span data-ttu-id="91b95-149">[步骤 1：为在 Purchase_Order 表的插入操作创建请求消息](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md) </span><span class="sxs-lookup"><span data-stu-id="91b95-149">[Step 1: Create the Request Message for Insert Operation on Purchase_Order Table](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md) </span></span>  
 [<span data-ttu-id="91b95-150">第 4 课：在采购订单表中执行插入操作</span><span class="sxs-lookup"><span data-stu-id="91b95-150">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)