---
title: 步骤 7 （在本地）： 创建业务流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c0b6d0e-cf00-4eee-9b89-28210bad46f4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b92a641252a76f4668cdf4c96c8df442c43d4719
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22280221"
---
# <a name="step-7-on-premises-create-an-orchestration"></a><span data-ttu-id="2e47c-102">步骤 7 （在本地）： 创建业务流程</span><span class="sxs-lookup"><span data-stu-id="2e47c-102">Step 7 (On Premises): Create an Orchestration</span></span>
<span data-ttu-id="2e47c-103">根据业务方案之后,[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收的销售订单消息从 Service Bus 队列，它需要检查消息中订购数量是否大于 100。</span><span class="sxs-lookup"><span data-stu-id="2e47c-103">According to the business scenario, after [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives the sales order message from the Service Bus Queue, it needs to check whether the quantity ordered in the message is greater than 100.</span></span> <span data-ttu-id="2e47c-104">如果数量大于 100，将消息插入**SalesOrder**表。</span><span class="sxs-lookup"><span data-stu-id="2e47c-104">If the quantity is greater than 100, the message is inserted into the **SalesOrder** table.</span></span> <span data-ttu-id="2e47c-105">否则会将消息发送到共享文件位置。</span><span class="sxs-lookup"><span data-stu-id="2e47c-105">Otherwise, the message is sent to a shared file location.</span></span> <span data-ttu-id="2e47c-106">Northwind 通过创建一个业务流程来实现此业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="2e47c-106">Northwind achieves this business logic by creating an orchestration.</span></span> <span data-ttu-id="2e47c-107">本主题提供如何创建该业务流程的分步指南。</span><span class="sxs-lookup"><span data-stu-id="2e47c-107">This topic provides step-by-step guidance on how to create the orchestration.</span></span>  
  
### <a name="to-add-an-orchestration-to-the-includebtsbiztalkservernoversionincludesbtsbiztalkservernoversion-mdmd-project"></a><span data-ttu-id="2e47c-108">向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目中添加业务流程的步骤</span><span class="sxs-lookup"><span data-stu-id="2e47c-108">To add an orchestration to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project</span></span>  
  
1.  <span data-ttu-id="2e47c-109">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]你已创建，右键单击项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] you already created, right-click the project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="2e47c-110">在**新项**对话框中，选择**BizTalk 业务流程**，输入映射名称为`OrderProcessing.odx`，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-110">In the **New Item** dialog box, select **BizTalk Orchestration**, enter the map name as `OrderProcessing.odx`, and then click **Add**.</span></span>  
  
## <a name="create-messages-for-the-orchestration"></a><span data-ttu-id="2e47c-111">为业务流程创建消息</span><span class="sxs-lookup"><span data-stu-id="2e47c-111">Create Messages for the Orchestration</span></span>  
 <span data-ttu-id="2e47c-112">你之前生成的架构描述了业务流程中的消息所需的“类型”。</span><span class="sxs-lookup"><span data-stu-id="2e47c-112">The schema that you generated earlier describes the “types” required for the messages in the orchestration.</span></span> <span data-ttu-id="2e47c-113">消息通常是一个变量，其类型由相应的架构定义。</span><span class="sxs-lookup"><span data-stu-id="2e47c-113">A message is typically a variable, the type for which defined by the corresponding schema.</span></span> <span data-ttu-id="2e47c-114">现在你必须为业务流程创建消息，然后将其链接到之前生成的架构。</span><span class="sxs-lookup"><span data-stu-id="2e47c-114">You must now create messages for the orchestration and link them to schemas you generated earlier.</span></span> <span data-ttu-id="2e47c-115">你需要创建以下三个消息：</span><span class="sxs-lookup"><span data-stu-id="2e47c-115">You need to create following three messages:</span></span>  
  
|<span data-ttu-id="2e47c-116">消息名称</span><span class="sxs-lookup"><span data-stu-id="2e47c-116">Message Name</span></span>|<span data-ttu-id="2e47c-117">对应的架构</span><span class="sxs-lookup"><span data-stu-id="2e47c-117">Corresponds to schema</span></span>|  
|------------------|---------------------------|  
|<span data-ttu-id="2e47c-118">Message1_SO_Inbound</span><span class="sxs-lookup"><span data-stu-id="2e47c-118">Message1_SO_Inbound</span></span>|<span data-ttu-id="2e47c-119">此消息是的一个实例**ECommerceSalesOrder.xsd**架构。</span><span class="sxs-lookup"><span data-stu-id="2e47c-119">This message is an instance of the **ECommerceSalesOrder.xsd** schema.</span></span>|  
|<span data-ttu-id="2e47c-120">Message2_SO_Inbound</span><span class="sxs-lookup"><span data-stu-id="2e47c-120">Message2_SO_Inbound</span></span>|<span data-ttu-id="2e47c-121">此消息是一份**Message1_SO_Inbound**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-121">This message is a copy of the **Message1_SO_Inbound**.</span></span> <span data-ttu-id="2e47c-122">作为最佳实践，你必须创建该消息的副本，然后修改新的消息，使原始消息保持不变。</span><span class="sxs-lookup"><span data-stu-id="2e47c-122">As a best practice, you must create a copy of the message and then modify the new message, leaving the original message intact.</span></span> <span data-ttu-id="2e47c-123">有关详细信息，请参阅[BizTalk Server 消息](http://msdn.microsoft.com/library/aa560436)。</span><span class="sxs-lookup"><span data-stu-id="2e47c-123">For more information, see [The BizTalk Server Message](http://msdn.microsoft.com/library/aa560436).</span></span>|  
|<span data-ttu-id="2e47c-124">Message1_SO_Outbound</span><span class="sxs-lookup"><span data-stu-id="2e47c-124">Message1_SO_Outbound</span></span>|<span data-ttu-id="2e47c-125">此消息是的一个实例**TableOperations.dbo.SalesOrder (Insert)** 架构。</span><span class="sxs-lookup"><span data-stu-id="2e47c-125">This message is an instance of the **TableOperations.dbo.SalesOrder (Insert)** schema.</span></span>|  
  
#### <a name="to-create-the-messages"></a><span data-ttu-id="2e47c-126">创建消息的步骤</span><span class="sxs-lookup"><span data-stu-id="2e47c-126">To create the messages</span></span>  
  
1.  <span data-ttu-id="2e47c-127">打开**业务流程视图**BizTalk 项目，如果尚未打开的窗口。</span><span class="sxs-lookup"><span data-stu-id="2e47c-127">Open the **Orchestration View** window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="2e47c-128">若要执行此操作，请单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-128">To do so, click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
2.  <span data-ttu-id="2e47c-129">在业务流程视图中，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-129">In Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
3.  <span data-ttu-id="2e47c-130">右键单击新创建的消息中，，然后选择**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-130">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="2e47c-131">在**属性**窗格**Message_1**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2e47c-131">In the **Properties** pane for the **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="2e47c-132">属性名称</span><span class="sxs-lookup"><span data-stu-id="2e47c-132">Property name</span></span>|<span data-ttu-id="2e47c-133">执行操作</span><span class="sxs-lookup"><span data-stu-id="2e47c-133">Perform action</span></span>|  
    |-------------------|--------------------|  
    |<span data-ttu-id="2e47c-134">Identifier</span><span class="sxs-lookup"><span data-stu-id="2e47c-134">Identifier</span></span>|<span data-ttu-id="2e47c-135">输入`Message1_SO_Inbound`</span><span class="sxs-lookup"><span data-stu-id="2e47c-135">Enter `Message1_SO_Inbound`</span></span>|  
    |<span data-ttu-id="2e47c-136">消息类型</span><span class="sxs-lookup"><span data-stu-id="2e47c-136">Message Type</span></span>|<span data-ttu-id="2e47c-137">从下拉列表中，展开**架构**，然后选择*OrderProcessingDemo.ECommerceSalesOrder*，其中*OrderProcessingDemo*是你的 BizTalk 的名称项目。</span><span class="sxs-lookup"><span data-stu-id="2e47c-137">From the drop-down list, expand **Schemas**, and then select *OrderProcessingDemo.ECommerceSalesOrder*, where *OrderProcessingDemo* is the name of your BizTalk project.</span></span> <span data-ttu-id="2e47c-138">*ECommerceSalesOrder*是从服务总线队列接收的销售订单消息的架构。</span><span class="sxs-lookup"><span data-stu-id="2e47c-138">*ECommerceSalesOrder* is the schema for the sales order message received from the Service Bus Queue.</span></span>|  
  
5.  <span data-ttu-id="2e47c-139">重复上述步骤，使用以下详细信息创建消息：</span><span class="sxs-lookup"><span data-stu-id="2e47c-139">Repeat the steps to create the messages with following details:</span></span>  
  
    |<span data-ttu-id="2e47c-140">消息名</span><span class="sxs-lookup"><span data-stu-id="2e47c-140">Message name</span></span>||  
    |------------------|-|  
    |<span data-ttu-id="2e47c-141">Message2_SO_Inbound</span><span class="sxs-lookup"><span data-stu-id="2e47c-141">Message2_SO_Inbound</span></span>|<span data-ttu-id="2e47c-142">-将设置**标识符**到`Message2_SO_Inbound`</span><span class="sxs-lookup"><span data-stu-id="2e47c-142">-   Set **Identifier** to `Message2_SO_Inbound`</span></span><br /><span data-ttu-id="2e47c-143">-将设置**消息类型**到*OrderProcessingDemo.ECommerceSalesOrder*</span><span class="sxs-lookup"><span data-stu-id="2e47c-143">-   Set **Message Type** to *OrderProcessingDemo.ECommerceSalesOrder*</span></span>|  
    |<span data-ttu-id="2e47c-144">Message1_SO_Outbound</span><span class="sxs-lookup"><span data-stu-id="2e47c-144">Message1_SO_Outbound</span></span>|<span data-ttu-id="2e47c-145">-将设置**标识符**到`Message1_SO_Outound`</span><span class="sxs-lookup"><span data-stu-id="2e47c-145">-   Set **Identifier** to `Message1_SO_Outound`</span></span><br /><span data-ttu-id="2e47c-146">-将设置**消息类型**到*OrderProcessingDemo.TableOperation_dbo_SalesOrder.Insert*</span><span class="sxs-lookup"><span data-stu-id="2e47c-146">-   Set **Message Type** to *OrderProcessingDemo.TableOperation_dbo_SalesOrder.Insert*</span></span>|  
  
## <a name="add-shapes-to-the-orchestration"></a><span data-ttu-id="2e47c-147">向业务流程添加形状</span><span class="sxs-lookup"><span data-stu-id="2e47c-147">Add Shapes to the Orchestration</span></span>  
 <span data-ttu-id="2e47c-148">业务流程形状定义 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序流。</span><span class="sxs-lookup"><span data-stu-id="2e47c-148">Orchestration shapes define the flow of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span> <span data-ttu-id="2e47c-149">在本部分中，将向业务流程添加所需形状。</span><span class="sxs-lookup"><span data-stu-id="2e47c-149">In this section, you add the required shapes to the orchestration.</span></span>  
  
#### <a name="to-add-shapes-to-the-orchestration"></a><span data-ttu-id="2e47c-150">若要将形状添加到业务流程</span><span class="sxs-lookup"><span data-stu-id="2e47c-150">To add shapes to the orchestration</span></span>  
  
1.  <span data-ttu-id="2e47c-151">开始时，必须添加**接收**形状。</span><span class="sxs-lookup"><span data-stu-id="2e47c-151">To start with, you must add a **Receive** shape.</span></span> <span data-ttu-id="2e47c-152">此形状将接收来自 Service Bus 队列的传入销售订单消息。</span><span class="sxs-lookup"><span data-stu-id="2e47c-152">This shape receives the incoming sales order message from the Service Bus Queue.</span></span> <span data-ttu-id="2e47c-153">在接收形状上设置以下属性。</span><span class="sxs-lookup"><span data-stu-id="2e47c-153">Set the following properties on the receive shape.</span></span>  
  
    1.  <span data-ttu-id="2e47c-154">设置**激活**到**True**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-154">Set **Activate** to **True**.</span></span>  
  
    2.  <span data-ttu-id="2e47c-155">设置**消息**到**Message1_SO_Inbound**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-155">Set **Message** to **Message1_SO_Inbound**.</span></span>  
  
    3.  <span data-ttu-id="2e47c-156">设置**名称**到**ReceiveOrder**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-156">Set **Name** to **ReceiveOrder**.</span></span>  
  
2.  <span data-ttu-id="2e47c-157">如前所述，你必须为接收到业务流程中的原始销售订单消息创建一个副本。</span><span class="sxs-lookup"><span data-stu-id="2e47c-157">As mentioned earlier, you must create a copy of the original sales order message that is received into the orchestration.</span></span>  
  
    1.  <span data-ttu-id="2e47c-158">拖放**构造消息**下调整**ReceiveOrder**形状。</span><span class="sxs-lookup"><span data-stu-id="2e47c-158">Drag-and-drop a **Construct Message** shape under the **ReceiveOrder** shape.</span></span> <span data-ttu-id="2e47c-159">因为你可以使用此形状来构造一条消息的类型 Message2_SO_Inbound，设置**消息构造**属性**Message2_SO_Inbound**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-159">Because you use this shape to construct a message of type Message2_SO_Inbound, set the **Messages Constructed** property to **Message2_SO_Inbound**.</span></span>  
  
    2.  <span data-ttu-id="2e47c-160">添加**消息分配**中调整**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="2e47c-160">Add a **Message Assignment** shape within the **Construct Message** shape.</span></span> <span data-ttu-id="2e47c-161">双击该形状以打开表达式编辑器，然后添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="2e47c-161">Double-click the shape to open the Expression Editor, and add the following:</span></span>  
  
        ```  
        Message2_SO_Inbound = Message1_SO_Inbound; //copy the message  
        Message2_SO_Inbound(*) = Message1_SO_Inbound(*); //copy the context properties on the message  
        ```  
  
         <span data-ttu-id="2e47c-162">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-162">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="2e47c-163">根据本业务方案，必须根据已订购货品的数量将该消息发送到不同目标。</span><span class="sxs-lookup"><span data-stu-id="2e47c-163">According to the business scenario, the message must be sent to different destinations based on the quantity of ordered items.</span></span> <span data-ttu-id="2e47c-164">因此，你必须现在从传入的销售订单消息中提取出数量值。</span><span class="sxs-lookup"><span data-stu-id="2e47c-164">So, you must now extract the quantity value from the incoming sales order message.</span></span>  
  
    1.  <span data-ttu-id="2e47c-165">**数量**入站消息 (ECommerceSalesOrder.xsd) 中的元素包含的值的有序的数量。</span><span class="sxs-lookup"><span data-stu-id="2e47c-165">The **Quantity** element in the inbound message (ECommerceSalesOrder.xsd) contains the value of the ordered quantity.</span></span> <span data-ttu-id="2e47c-166">你必须升级该属性，以便将此元素用在业务流程中的表达式中。</span><span class="sxs-lookup"><span data-stu-id="2e47c-166">You must promote that property so that the element can be used within the expressions in the orchestration.</span></span> <span data-ttu-id="2e47c-167">若要升级的属性，打开**ECommerceSalesOrder.xsd**架构中，右键单击**数量**，指向**Promote**，然后单击**快速提升**.</span><span class="sxs-lookup"><span data-stu-id="2e47c-167">To promote the property, open the **ECommerceSalesOrder.xsd** schema, right-click **Quantity**, point to **Promote**, and then click **Quick Promotions**.</span></span>  
  
    2.  <span data-ttu-id="2e47c-168">创建用于存储数量值的变量。</span><span class="sxs-lookup"><span data-stu-id="2e47c-168">Create a variable to store the quantity value.</span></span> <span data-ttu-id="2e47c-169">若要创建一个变量，从**业务流程视图**，右键单击**变量**，然后单击**新变量**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-169">To create a variable, from the **Orchestration View**, right-click **Variables**, and then click **New Variable**.</span></span> <span data-ttu-id="2e47c-170">为变量设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="2e47c-170">Set the following properties for the variable:</span></span>  
  
        |<span data-ttu-id="2e47c-171">属性名称</span><span class="sxs-lookup"><span data-stu-id="2e47c-171">Property name</span></span>|<span data-ttu-id="2e47c-172">值</span><span class="sxs-lookup"><span data-stu-id="2e47c-172">Value</span></span>|  
        |-------------------|-----------|  
        |<span data-ttu-id="2e47c-173">Identifier</span><span class="sxs-lookup"><span data-stu-id="2e47c-173">Identifier</span></span>|<span data-ttu-id="2e47c-174">输入`quantityOrdered`</span><span class="sxs-lookup"><span data-stu-id="2e47c-174">Enter `quantityOrdered`</span></span>|  
        |<span data-ttu-id="2e47c-175">类型</span><span class="sxs-lookup"><span data-stu-id="2e47c-175">Type</span></span>|<span data-ttu-id="2e47c-176">选择**Int32**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-176">Select **Int32**.</span></span>|  
  
    3.  <span data-ttu-id="2e47c-177">你现在必须将分配中的值**数量**元素**quantityOrdered**变量。</span><span class="sxs-lookup"><span data-stu-id="2e47c-177">You must now assign the value in the **Quantity** element to the **quantityOrdered** variable.</span></span> <span data-ttu-id="2e47c-178">拖放**表达式编辑器**后**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="2e47c-178">Drag-and-drop an **Expression Editor** after the **Construct Message** shape.</span></span> <span data-ttu-id="2e47c-179">打开该编辑器，然后输入以下表达式：</span><span class="sxs-lookup"><span data-stu-id="2e47c-179">Open the editor and enter the following expression:</span></span>  
  
        ```  
        quantityOrdered = Message2_SO_Inbound.Quantity;  
        ```  
  
         <span data-ttu-id="2e47c-180">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-180">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="2e47c-181">提取出订购数量后，现在你需要创建一个判定块，以便在该判定块上布置消息流将采取的两个单独路线。</span><span class="sxs-lookup"><span data-stu-id="2e47c-181">After extracting the order quantity, you now need to create a decision block where you layout two separate paths the message flow takes.</span></span> <span data-ttu-id="2e47c-182">通过添加业务流程中创建的决策块**确定**形状。</span><span class="sxs-lookup"><span data-stu-id="2e47c-182">You create the decision block in an orchestration by adding a **Decide** shape.</span></span>  
  
    1.  <span data-ttu-id="2e47c-183">拖放式**确定**后调整**表达式编辑器**形状。</span><span class="sxs-lookup"><span data-stu-id="2e47c-183">Drag and drop a **Decide** shape after the **Expression Editor** shape.</span></span>  
  
    2.  <span data-ttu-id="2e47c-184">选择**Rule_1**形状并在**属性**窗口中，指定下列各项：</span><span class="sxs-lookup"><span data-stu-id="2e47c-184">Select the **Rule_1** shape and in the **Properties** window, specify the following:</span></span>  
  
        |<span data-ttu-id="2e47c-185">属性名称</span><span class="sxs-lookup"><span data-stu-id="2e47c-185">Property name</span></span>|<span data-ttu-id="2e47c-186">值</span><span class="sxs-lookup"><span data-stu-id="2e47c-186">Value</span></span>|  
        |-------------------|-----------|  
        |<span data-ttu-id="2e47c-187">Identifier</span><span class="sxs-lookup"><span data-stu-id="2e47c-187">Identifier</span></span>|<span data-ttu-id="2e47c-188">输入`Yes`。</span><span class="sxs-lookup"><span data-stu-id="2e47c-188">Enter `Yes`.</span></span> <span data-ttu-id="2e47c-189">**注意：** 其他路由是默认情况下名为**Else**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-189">**Note:**  The other route is by default named **Else**.</span></span>|  
        |<span data-ttu-id="2e47c-190">表达式</span><span class="sxs-lookup"><span data-stu-id="2e47c-190">Expression</span></span>|<span data-ttu-id="2e47c-191">输入`quantityOrdered > 100`。</span><span class="sxs-lookup"><span data-stu-id="2e47c-191">Enter `quantityOrdered > 100`.</span></span>|  
  
         <span data-ttu-id="2e47c-192">现在你有两条路线可用。</span><span class="sxs-lookup"><span data-stu-id="2e47c-192">You now have two routes available.</span></span> <span data-ttu-id="2e47c-193">如果中的值**quantityOrdered**变量大于 100，消息将**是**路由。</span><span class="sxs-lookup"><span data-stu-id="2e47c-193">If the value in the **quantityOrdered** variable is greater than 100, the message takes the **Yes** route.</span></span> <span data-ttu-id="2e47c-194">否则，它采用**Else**路由。</span><span class="sxs-lookup"><span data-stu-id="2e47c-194">Otherwise, it takes the **Else** route.</span></span> <span data-ttu-id="2e47c-195">现在你必须定义要在每个路线中执行的操作。</span><span class="sxs-lookup"><span data-stu-id="2e47c-195">You must now define the actions to be performed within each route.</span></span>  
  
5.  <span data-ttu-id="2e47c-196">根据本业务方案，如果订购数量大于 100，则必须将消息插入到 SalesOrder 表中。</span><span class="sxs-lookup"><span data-stu-id="2e47c-196">According to the business scenario, if the order quantity is greater than 100, the message must be inserted into the SalesOrder table.</span></span> <span data-ttu-id="2e47c-197">因此，在**是**路由，必须转换 ECommerceSalesOrder.xsd 架构与 TableOperations.SalesOrder.Insert 架构。</span><span class="sxs-lookup"><span data-stu-id="2e47c-197">So, in the **Yes** route, you must transform the ECommerceSalesOrder.xsd schema to the TableOperations.SalesOrder.Insert schema.</span></span> <span data-ttu-id="2e47c-198">主题中创建插入架构[步骤 5 （在本地）： 生成插入消息 inito SalesOrder 表的架构](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md)。</span><span class="sxs-lookup"><span data-stu-id="2e47c-198">You created the Insert schema in the topic [Step 5 (On Premises): Generate the Schema for Inserting a Message inito SalesOrder Table](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md).</span></span> <span data-ttu-id="2e47c-199">转换该架构后，必须将消息发送到 SQL Server 数据库表以外的消息中。</span><span class="sxs-lookup"><span data-stu-id="2e47c-199">After transforming the schema, you must send the message to the message out to the SQL Server database table.</span></span>  
  
    1.  <span data-ttu-id="2e47c-200">在**是**路由、 拖动和删除**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="2e47c-200">Within the **Yes** route, drag and drop a **Construct Message** shape.</span></span> <span data-ttu-id="2e47c-201">设置**消息构造**属性到形状**Message1_SO_Outbound**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-201">Set the **Messages Constructed** property for the shape to **Message1_SO_Outbound**.</span></span>  
  
    2.  <span data-ttu-id="2e47c-202">在**构造消息**形状添加**转换**形状。</span><span class="sxs-lookup"><span data-stu-id="2e47c-202">Within the **Construct Message** shape add a **Transform** shape.</span></span> <span data-ttu-id="2e47c-203">双击要打开的形状**转换配置**对话框。</span><span class="sxs-lookup"><span data-stu-id="2e47c-203">Double-click the shape to open the **Transform Configuration** dialog box.</span></span> <span data-ttu-id="2e47c-204">请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2e47c-204">Do the following:</span></span>  
  
        1.  <span data-ttu-id="2e47c-205">选择**现有映射**选项。</span><span class="sxs-lookup"><span data-stu-id="2e47c-205">Select the **Existing Map** option.</span></span>  
  
        2.  <span data-ttu-id="2e47c-206">从**完全限定的映射名称**下拉列表中，选择**OrderProcessingDemo.SalesOrder_SQL**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-206">From the **Fully Qualified Map Name** drop-down, select **OrderProcessingDemo.SalesOrder_SQL**.</span></span>  
  
        3.  <span data-ttu-id="2e47c-207">有关**源**，选择**Message2_SO_Inbound**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-207">For **Source**, select **Message2_SO_Inbound**.</span></span>  
  
        4.  <span data-ttu-id="2e47c-208">有关**目标**，选择**Message1_SO_Outound**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-208">For **Destination**, select **Message1_SO_Outound**.</span></span>  
  
    3.  <span data-ttu-id="2e47c-209">后**构造消息**形状、 拖动和删除**发送**的形状，然后设置**消息**属性到形状`Message1_SO_Outbound`。</span><span class="sxs-lookup"><span data-stu-id="2e47c-209">After the **Construct Message** shape, drag and drop a **Send** shape and set the **Message** property for the shape to `Message1_SO_Outbound`.</span></span>  
  
6.  <span data-ttu-id="2e47c-210">根据本业务方案，如果订购数量小于 100，则必须将消息发送到共享文件位置。</span><span class="sxs-lookup"><span data-stu-id="2e47c-210">According to the business scenario, if the order quantity is less than 100, the message must be sent to a shared file location.</span></span> <span data-ttu-id="2e47c-211">因此，在**Else**必须添加发送形状的路由。</span><span class="sxs-lookup"><span data-stu-id="2e47c-211">So, in the **Else** route you must add a send shape.</span></span>  
  
    1.  <span data-ttu-id="2e47c-212">在**Else**路由、 拖动和删除**发送**形状，并设置**消息**属性到形状`Message2_SO_Inbound`。</span><span class="sxs-lookup"><span data-stu-id="2e47c-212">Within the **Else** route, drag and drop a **Send** shape, and set the **Message** property for the shape to `Message2_SO_Inbound`.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="2e47c-213">你将“消息”设置为 Message2_SO_Inbound，是因为从 Service Bus 队列收到的同一消息将发送到此文件位置，而不做任何处理。</span><span class="sxs-lookup"><span data-stu-id="2e47c-213">You set the Message to Message2_SO_Inbound because the same message that is received from the Service Bus Queue is sent to the file location, without any processing.</span></span> <span data-ttu-id="2e47c-214">Message2_SO_Inbound 表示由 Service Bus 队列接收的消息。</span><span class="sxs-lookup"><span data-stu-id="2e47c-214">Message2_SO_Inbound represents the message that is received by the Service Bus Queue.</span></span>  
  
## <a name="add-ports-to-the-orchestration"></a><span data-ttu-id="2e47c-215">向业务流程添加端口</span><span class="sxs-lookup"><span data-stu-id="2e47c-215">Add Ports to the Orchestration</span></span>  
 <span data-ttu-id="2e47c-216">端口表示有关业务流程的消息的输入和输出媒介。</span><span class="sxs-lookup"><span data-stu-id="2e47c-216">Ports represent the input and output mediums of the message with respect to an orchestration.</span></span> <span data-ttu-id="2e47c-217">消息由业务流程使用接收端口处理，然后使用发送端口送出。</span><span class="sxs-lookup"><span data-stu-id="2e47c-217">Messages are consumed by an orchestration using a receive port and are sent out using a send port.</span></span> <span data-ttu-id="2e47c-218">在本业务方案中，将从一种媒介（Service Bus 队列）接收消息，然后基于消息处理将其发送到两个不同的位置（SQL Server 数据库或文件共享位置）。</span><span class="sxs-lookup"><span data-stu-id="2e47c-218">In the business scenario, a message is received from one medium (Service Bus Queue) and then sent out to two different locations (SQL Server database or a file share location) based on message processing.</span></span> <span data-ttu-id="2e47c-219">因此，必须创建一个接收端口和两个发送端口作为业务流程的一部分。</span><span class="sxs-lookup"><span data-stu-id="2e47c-219">So, you must create one receive port and two send ports as part of the orchestration.</span></span>  
  
#### <a name="to-add-ports"></a><span data-ttu-id="2e47c-220">添加端口的步骤</span><span class="sxs-lookup"><span data-stu-id="2e47c-220">To add ports</span></span>  
  
1.  <span data-ttu-id="2e47c-221">拖放式**端口**形状变为**端口图面**窗格**业务流程设计器**以启动**端口配置向导**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-221">Drag and drop a **Port** shape to the **Port Surface** pane of the **Orchestration Designer** to launch the **Port Configuration Wizard**.</span></span> <span data-ttu-id="2e47c-222">上**欢迎**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-222">On the **Welcome** page, click **Next**.</span></span>  
  
2.  <span data-ttu-id="2e47c-223">在**端口属性**页上，将该端口用作`ReceiveSO`，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-223">In the **Port Properties** page, name the port as `ReceiveSO` and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="2e47c-224">在**选择端口类型**页上，选择**创建新的端口类型**选项中，选择**单向**通信模式，保留有关访问限制，默认值，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-224">In the **Select a Port Type** page, select **Create a new port type** option, select the **One-Way** communication pattern, leave the default for access restrictions, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="2e47c-225">在**端口绑定**页上，选择的端口方向**我将始终接收此端口上的消息**，保留为默认值端口候机，然后单击**下一步**.</span><span class="sxs-lookup"><span data-stu-id="2e47c-225">In the **Port Binding** page, for the port direction, select **I’ll always be receiving messages on this port**, leave the port biding to the default value, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="2e47c-226">在最后一页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="2e47c-226">On the last page, click **Finish**.</span></span>  
  
6.  <span data-ttu-id="2e47c-227">重复上述步骤以创建两个发送端口。</span><span class="sxs-lookup"><span data-stu-id="2e47c-227">Repeat the steps to create the two send ports.</span></span> <span data-ttu-id="2e47c-228">在创建端口的同时指定以下值。</span><span class="sxs-lookup"><span data-stu-id="2e47c-228">Specify the following values while creating the ports.</span></span>  
  
    |<span data-ttu-id="2e47c-229">端口名称</span><span class="sxs-lookup"><span data-stu-id="2e47c-229">Port Name</span></span>|<span data-ttu-id="2e47c-230">属性</span><span class="sxs-lookup"><span data-stu-id="2e47c-230">Properties</span></span>|  
    |---------------|----------------|  
    |<span data-ttu-id="2e47c-231">SendToSQL</span><span class="sxs-lookup"><span data-stu-id="2e47c-231">SendToSQL</span></span>|<span data-ttu-id="2e47c-232">-将设置**名称**到**SendToSQL**</span><span class="sxs-lookup"><span data-stu-id="2e47c-232">-   Set **Name** to **SendToSQL**</span></span><br /><span data-ttu-id="2e47c-233">-选择**创建新的端口类型**</span><span class="sxs-lookup"><span data-stu-id="2e47c-233">-   Select **Create a new port type**</span></span><br /><span data-ttu-id="2e47c-234">集通信模式与**单向**</span><span class="sxs-lookup"><span data-stu-id="2e47c-234">-   Set communication pattern to **One-way**</span></span><br /><span data-ttu-id="2e47c-235">-将端口方向设置为**我将始终发送消息上此端口**</span><span class="sxs-lookup"><span data-stu-id="2e47c-235">-   Set port direction to **I’ll always be sending messages on this port**</span></span>|  
    |<span data-ttu-id="2e47c-236">SendToFile</span><span class="sxs-lookup"><span data-stu-id="2e47c-236">SendToFile</span></span>|<span data-ttu-id="2e47c-237">-将设置**名称**到**SendToFile**</span><span class="sxs-lookup"><span data-stu-id="2e47c-237">-   Set **Name** to **SendToFile**</span></span><br /><span data-ttu-id="2e47c-238">-选择**创建新的端口类型**</span><span class="sxs-lookup"><span data-stu-id="2e47c-238">-   Select **Create a new port type**</span></span><br /><span data-ttu-id="2e47c-239">集通信模式与**单向**</span><span class="sxs-lookup"><span data-stu-id="2e47c-239">-   Set communication pattern to **One-way**</span></span><br /><span data-ttu-id="2e47c-240">-将端口方向设置为**我将始终发送消息上此端口**</span><span class="sxs-lookup"><span data-stu-id="2e47c-240">-   Set port direction to **I’ll always be sending messages on this port**</span></span>|  
  
## <a name="connect-ports-and-message-shapes"></a><span data-ttu-id="2e47c-241">连接端口和消息形状</span><span class="sxs-lookup"><span data-stu-id="2e47c-241">Connect Ports and Message Shapes</span></span>  
 <span data-ttu-id="2e47c-242">现在，你必须连接端口和消息形状以完成业务流程。</span><span class="sxs-lookup"><span data-stu-id="2e47c-242">You must now connect the ports and the message shapes to complete the orchestration.</span></span> <span data-ttu-id="2e47c-243">接收此消息时，业务流程将启动**ReceiveOrder**形状和业务流程退出由两个发送形状发送消息。</span><span class="sxs-lookup"><span data-stu-id="2e47c-243">The orchestration starts when the message is received by the **ReceiveOrder** shape and the orchestration exits when the message is sent out by the two Send shapes.</span></span> <span data-ttu-id="2e47c-244">你必须使用此标准来连接端口与消息形状</span><span class="sxs-lookup"><span data-stu-id="2e47c-244">You must use this criterion to connect the ports and the message shapes</span></span>  
  
#### <a name="to-connect-ports-with-message-shapes"></a><span data-ttu-id="2e47c-245">连接端口与消息形状的步骤</span><span class="sxs-lookup"><span data-stu-id="2e47c-245">To connect ports with message shapes</span></span>  
  
1.  <span data-ttu-id="2e47c-246">连接**ReceiveSO**接收到的端口**ReceiveOrder**形状。</span><span class="sxs-lookup"><span data-stu-id="2e47c-246">Connect the **ReceiveSO** receive port to the **ReceiveOrder** shape.</span></span>  
  
2.  <span data-ttu-id="2e47c-247">连接下的发送形状**是**将路由到**SendToSQL**发送端口。</span><span class="sxs-lookup"><span data-stu-id="2e47c-247">Connect the Send shape under the **Yes** route to the **SendToSQL** send port.</span></span> <span data-ttu-id="2e47c-248">这表示如果消息进入此路由 (**quantityOrdered** > 100)，它将发送到**SalesOrder** SQL Server 数据库中的表。</span><span class="sxs-lookup"><span data-stu-id="2e47c-248">This denotes that if a message enters this route (**quantityOrdered** > 100), it’ll be sent to the **SalesOrder** table in the SQL Server database.</span></span>  
  
3.  <span data-ttu-id="2e47c-249">连接下的发送形状**Else**将路由到**SendToFile**发送端口。</span><span class="sxs-lookup"><span data-stu-id="2e47c-249">Connect the Send shape under the **Else** route to the **SendToFile** send port.</span></span> <span data-ttu-id="2e47c-250">这表示如果消息进入此路由 (**quantityOrdered** < = 100)，它将发送到指定的文件位置。</span><span class="sxs-lookup"><span data-stu-id="2e47c-250">This denotes that if a message enters this route (**quantityOrdered** <= 100), it’ll be sent to a specified file location.</span></span>  
  
     <span data-ttu-id="2e47c-251">业务流程必须类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="2e47c-251">The orchestration must resemble the following:</span></span>  
  
     <span data-ttu-id="2e47c-252">![业务流程](../core/media/bts2010r2-tut1-orch.jpg "BTS2010R2_Tut1_Orch")</span><span class="sxs-lookup"><span data-stu-id="2e47c-252">![Orchestration](../core/media/bts2010r2-tut1-orch.jpg "BTS2010R2_Tut1_Orch")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e47c-253">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e47c-253">See Also</span></span>  
 [<span data-ttu-id="2e47c-254">教程 4： 创建使用 BizTalk Server 2013 的混合应用程序</span><span class="sxs-lookup"><span data-stu-id="2e47c-254">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)