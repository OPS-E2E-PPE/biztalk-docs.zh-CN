---
title: 步骤 5：修改 Contoso 专用业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private processes, orchestrations
- private process tutorial, modifying private process orchestration
ms.assetid: a5430db8-e5f0-48a6-abb9-e268d8ec2ec4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 298a6ab0728928347b33f65ba5819a62897511cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280855"
---
# <a name="step-5-modifying-the-contoso-private-process-orchestration"></a><span data-ttu-id="01250-102">步骤 5：修改 Contoso 专用业务流程</span><span class="sxs-lookup"><span data-stu-id="01250-102">Step 5: Modifying the Contoso Private Process Orchestration</span></span>
<span data-ttu-id="01250-103">在此步骤中，修改专用业务流程与企业资源规划 (ERP) 系统集成，为 Contoso。</span><span class="sxs-lookup"><span data-stu-id="01250-103">In this step, you modify the private process orchestration to integrate with the Enterprise Resource Planning (ERP) system for Contoso.</span></span> <span data-ttu-id="01250-104">Contoso ERP 系统使用的产品价格与可用性的内部定义的架构。</span><span class="sxs-lookup"><span data-stu-id="01250-104">The ERP system for Contoso uses internally defined schemas for product price and availability.</span></span> <span data-ttu-id="01250-105">通过自定义专用流程 3a2-价格与可用性合作伙伴接口流程 (PIP)，你将能够通过使用架构映射信息与 ERP 系统集成。</span><span class="sxs-lookup"><span data-stu-id="01250-105">By customizing the private process for the 3A2 - Price and Availability Partner Interface Process (PIP), you will be able to integrate with the ERP system by using schema-mapping information.</span></span>  
  
### <a name="to-add-a-reference-to-the-contoso-priceandavailability-and-rnpips-assemblies"></a><span data-ttu-id="01250-106">若要添加对 Contoso PriceAndAvailability 和 Rnpip 程序集的引用</span><span class="sxs-lookup"><span data-stu-id="01250-106">To add a reference to the Contoso PriceAndAvailability and RNPIPs assemblies</span></span>  
  
1. <span data-ttu-id="01250-107">Contoso 解决方案显示在解决方案资源管理器中，右键单击**PrivateResponder**项目，并单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="01250-107">With the Contoso solution displayed in Solution Explorer, right-click the **PrivateResponder** project, and then click **Add Reference**.</span></span>  
  
2. <span data-ttu-id="01250-108">在添加引用对话框中，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="01250-108">In the Add Reference dialog box, click **Browse**.</span></span> <span data-ttu-id="01250-109">将移动到*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\Bin 文件夹，然后选择以下程序集<strong>:</strong></span><span class="sxs-lookup"><span data-stu-id="01250-109">Move to *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\Bin folder, and then select the following assemblies<strong>:</strong></span></span>  
  
   -   <span data-ttu-id="01250-110">Microsoft.Solutions.BTARN.CommonTypes.dll</span><span class="sxs-lookup"><span data-stu-id="01250-110">Microsoft.Solutions.BTARN.CommonTypes.dll</span></span>  
  
   -   <span data-ttu-id="01250-111">Microsoft.Solutions.BTARN.ConfigurationManager.dll</span><span class="sxs-lookup"><span data-stu-id="01250-111">Microsoft.Solutions.BTARN.ConfigurationManager.dll</span></span>  
  
   -   <span data-ttu-id="01250-112">Microsoft.Solutions.BTARN.GlobalSchemas.dll</span><span class="sxs-lookup"><span data-stu-id="01250-112">Microsoft.Solutions.BTARN.GlobalSchemas.dll</span></span>  
  
   -   <span data-ttu-id="01250-113">Microsoft.Solutions.BTARN.PublicResponder.dll</span><span class="sxs-lookup"><span data-stu-id="01250-113">Microsoft.Solutions.BTARN.PublicResponder.dll</span></span>  
  
   -   <span data-ttu-id="01250-114">Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll</span><span class="sxs-lookup"><span data-stu-id="01250-114">Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll</span></span>  
  
   -   <span data-ttu-id="01250-115">Microsoft.Solutions.BTARN.Shared.dll</span><span class="sxs-lookup"><span data-stu-id="01250-115">Microsoft.Solutions.BTARN.Shared.dll</span></span>  
  
   -   <span data-ttu-id="01250-116">Microsoft.Solutions.BTARN.XSDClasses.GlobalSchemas.dll</span><span class="sxs-lookup"><span data-stu-id="01250-116">Microsoft.Solutions.BTARN.XSDClasses.GlobalSchemas.dll</span></span>  
  
3. <span data-ttu-id="01250-117">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="01250-117">Click **Add**.</span></span>  
  
4. <span data-ttu-id="01250-118">在添加引用对话框中，单击**项目**选项卡上，选择**ContosoPriceAndAvailability**并**HeaderHelper**项目，并单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="01250-118">In the Add Reference dialog box, click the **Projects** tab, select the **ContosoPriceAndAvailability** and **HeaderHelper** projects, and then click **Add**.</span></span>  
  
5. <span data-ttu-id="01250-119">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="01250-119">Click **OK**.</span></span>  
  
6. <span data-ttu-id="01250-120">在 Microsoft 的开发环境对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="01250-120">In the Microsoft Development Environment dialog box, click **OK**.</span></span>  
  
### <a name="to-create-new-message-types"></a><span data-ttu-id="01250-121">若要创建新的消息类型</span><span class="sxs-lookup"><span data-stu-id="01250-121">To create new message types</span></span>  
  
1.  <span data-ttu-id="01250-122">在解决方案资源管理器中双击**PrivateResponder**业务流程以将其打开。</span><span class="sxs-lookup"><span data-stu-id="01250-122">In Solution Explorer, double-click the **PrivateResponder** orchestration to open it.</span></span>  
  
2.  <span data-ttu-id="01250-123">在解决方案资源管理器，单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="01250-123">In Solution Explorer, click **Orchestration View**.</span></span>  
  
3.  <span data-ttu-id="01250-124">在业务流程视图中，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="01250-124">In Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
4.  <span data-ttu-id="01250-125">在属性窗口中**标识符**框中，键入**PIP3A2RequestMessage**。</span><span class="sxs-lookup"><span data-stu-id="01250-125">In the Properties window, in the **Identifier** box, type **PIP3A2RequestMessage**.</span></span>  
  
5.  <span data-ttu-id="01250-126">在中**消息类型**框中，单击下拉箭头，展开**架构**，然后选择**\<从引用的程序集选择\>**。</span><span class="sxs-lookup"><span data-stu-id="01250-126">In the **Message Type** box, click the drop-down arrow, expand **Schemas**, and then select **\<Select from referenced assembly\>**.</span></span>  
  
6.  <span data-ttu-id="01250-127">在选择项目类型框中，选择**Microsoft.Solutions.BTARN.Schemas.RNPIPs**在左窗格中，选择 **_3A2PriceAndAvailabilityQueryMessageGuideline_v1_3**在右窗格中，并然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="01250-127">In the Select Artifact Typedialog box, select **Microsoft.Solutions.BTARN.Schemas.RNPIPs** in the left pane, select **_3A2PriceAndAvailabilityQueryMessageGuideline_v1_3** in the right pane, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="01250-128">重复步骤 3 至 6 以创建使用以下信息的解决方案的所有消息类型：</span><span class="sxs-lookup"><span data-stu-id="01250-128">Repeat steps 3 through 6 to create all the message types for the solution using the following information:</span></span>  
  
    |<span data-ttu-id="01250-129">Identifier</span><span class="sxs-lookup"><span data-stu-id="01250-129">Identifier</span></span>|<span data-ttu-id="01250-130">Assembly</span><span class="sxs-lookup"><span data-stu-id="01250-130">Assembly</span></span>|<span data-ttu-id="01250-131">消息类型</span><span class="sxs-lookup"><span data-stu-id="01250-131">Message Type</span></span>|  
    |----------------|--------------|------------------|  
    |<span data-ttu-id="01250-132">PIP3A2ResponseMessage</span><span class="sxs-lookup"><span data-stu-id="01250-132">PIP3A2ResponseMessage</span></span>|<span data-ttu-id="01250-133">Microsoft.Solutions.BTARN.</span><span class="sxs-lookup"><span data-stu-id="01250-133">Microsoft.Solutions.BTARN.</span></span><br /><span data-ttu-id="01250-134">Schemas.RNPips</span><span class="sxs-lookup"><span data-stu-id="01250-134">Schemas.RNPips</span></span>|<span data-ttu-id="01250-135">_3A2PriceAndAvailability</span><span class="sxs-lookup"><span data-stu-id="01250-135">_3A2PriceAndAvailability</span></span><br /><span data-ttu-id="01250-136">ResponseMessageGuideline_v1_3</span><span class="sxs-lookup"><span data-stu-id="01250-136">ResponseMessageGuideline_v1_3</span></span>|  
    |<span data-ttu-id="01250-137">Contoso3A2ResponseMessage</span><span class="sxs-lookup"><span data-stu-id="01250-137">Contoso3A2ResponseMessage</span></span>|<span data-ttu-id="01250-138">ContosoPriceAndAvailability</span><span class="sxs-lookup"><span data-stu-id="01250-138">ContosoPriceAndAvailability</span></span>|<span data-ttu-id="01250-139">rootPriceResponse</span><span class="sxs-lookup"><span data-stu-id="01250-139">rootPriceResponse</span></span>|  
    |<span data-ttu-id="01250-140">Contoso3A2RequestMessage</span><span class="sxs-lookup"><span data-stu-id="01250-140">Contoso3A2RequestMessage</span></span>|<span data-ttu-id="01250-141">ContosoPriceAndAvailability</span><span class="sxs-lookup"><span data-stu-id="01250-141">ContosoPriceAndAvailability</span></span>|<span data-ttu-id="01250-142">rootPriceRequest</span><span class="sxs-lookup"><span data-stu-id="01250-142">rootPriceRequest</span></span>|  
  
8.  <span data-ttu-id="01250-143">你已创建解决方案的消息类型。</span><span class="sxs-lookup"><span data-stu-id="01250-143">You have finished creating the message types for the solution.</span></span>  
  
### <a name="to-create-new-variables"></a><span data-ttu-id="01250-144">若要创建新变量</span><span class="sxs-lookup"><span data-stu-id="01250-144">To create new variables</span></span>  
  
1.  <span data-ttu-id="01250-145">在业务流程视图中，右键单击**变量，** ，然后单击**新变量**。</span><span class="sxs-lookup"><span data-stu-id="01250-145">In Orchestration View, right-click **Variables,** and then click **New Variable**.</span></span>  
  
2.  <span data-ttu-id="01250-146">在属性窗口中**标识符**框中，键入**contosoResponseXML**。</span><span class="sxs-lookup"><span data-stu-id="01250-146">In the Properties window, in the **Identifier** box, type **contosoResponseXML**.</span></span>  
  
3.  <span data-ttu-id="01250-147">在中**类型**框中，选择 **\<.NET 类\>** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="01250-147">In the **Type** box, select **\<.NET Class\>** from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="01250-148">在选择项目中，在键入对话框中，在左窗格中，**当前项目**并**引用**节点，选择**System.Xml**，选择**XmlDocument**从列表中在右窗格中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="01250-148">In the Select Artifact Type dialog box, in the left pane, under the **Current Project** and **References** nodes, select **System.Xml**, select **XmlDocument** from the list in the right pane, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="01250-149">在中**业务流程视图**，单击**变量**，然后单击**新变量**。</span><span class="sxs-lookup"><span data-stu-id="01250-149">In **Orchestration View**, click **Variables**,and then click **New Variable**.</span></span>  
  
6.  <span data-ttu-id="01250-150">在属性窗口中**标识符**框中，键入**submitMessage**。</span><span class="sxs-lookup"><span data-stu-id="01250-150">In the Properties window, in the **Identifier** box, type **submitMessage**.</span></span>  
  
7.  <span data-ttu-id="01250-151">在中**类型**框中，选择 **\<.NET 类\>** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="01250-151">In the **Type** box, select **\<.NET Class\>** from the drop-down list.</span></span>  
  
8.  <span data-ttu-id="01250-152">在选择项目类型对话框中，在左窗格中，展开**当前项目**并**引用**节点，选择**再**，选择**SubmitRNIF**从列表中在右窗格中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="01250-152">In the Select Artifact Type dialog box, in the left pane, expand **Current Project** and **References** nodes, select **Microsoft.Solutions.BTARN.Shared**, select **SubmitRNIF** from the list in the right pane, and then click **OK**.</span></span>  
  
### <a name="to-change-the-orchestration-filter-expression"></a><span data-ttu-id="01250-153">若要更改的业务流程筛选器表达式</span><span class="sxs-lookup"><span data-stu-id="01250-153">To change the orchestration filter expression</span></span>  
  
1.  <span data-ttu-id="01250-154">在业务流程设计器中，选择**ReceiveFromPublicProcessResponder**形状。</span><span class="sxs-lookup"><span data-stu-id="01250-154">In Orchestration Designer, select the **ReceiveFromPublicProcessResponder** shape.</span></span>  
  
2.  <span data-ttu-id="01250-155">在属性窗口中**筛选器表达式**框中，单击值框，然后单击省略号按钮 (**...**) 以打开筛选器表达式对话框。</span><span class="sxs-lookup"><span data-stu-id="01250-155">In the Properties window, in the **Filter Expression** box, click the value box, and then click the ellipsis button (**...**) to open the Filter Expression dialog box.</span></span>  
  
3.  <span data-ttu-id="01250-156">在筛选器表达式对话框中，在**Group By**部分中，单击**或者**值的第一行上，然后选择**AND**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="01250-156">In the Filter Expression dialog box, in the **Group By** section, click the **OR** value on the first line, and then select **AND** from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="01250-157">在筛选器表达式对话框中，单击**单击此处可添加新行**，然后选择**Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="01250-157">In the Filter Expression dialog box, click **Click here to add a new row**, and then select **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="01250-158">在同一行中，单击**值**，然后键入 **"3A2"**。</span><span class="sxs-lookup"><span data-stu-id="01250-158">In the same row, click **Value**, and then type in **"3A2"**.</span></span>  
  
6.  <span data-ttu-id="01250-159">在同一行中，单击**AND**中**Group By**框，并选择**或**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="01250-159">In the same row, click **AND** in the **Group By** box, and then select **OR** from the drop-down list.</span></span>  
  
7.  <span data-ttu-id="01250-160">在筛选器表达式对话框中，选择刚创建的行，然后单击上的箭头按钮一次移动一次一行。</span><span class="sxs-lookup"><span data-stu-id="01250-160">In the Filter Expression dialog box, select the row that you just created, and then click the up arrow button once to move the row up once.</span></span>  
  
8.  <span data-ttu-id="01250-161">单击**单击此处可添加新行**，然后选择**Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="01250-161">Click **Click here to add a new row**, and then select **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="01250-162">在同一行中，单击**值**，然后键入 **"3A2"**。</span><span class="sxs-lookup"><span data-stu-id="01250-162">In the same row, click **Value**, and then type in **"3A2"**.</span></span>  
  
10. <span data-ttu-id="01250-163">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="01250-163">Click OK.</span></span>  
  
### <a name="to-modify-the-business-process-workflow"></a><span data-ttu-id="01250-164">若要修改业务流程工作流</span><span class="sxs-lookup"><span data-stu-id="01250-164">To modify the business process workflow</span></span>  
  
1. <span data-ttu-id="01250-165">拖动**消息赋值**形状从工具箱拖到设计图面并将其下放置**ReceiveFromPublicProcessResponder**形状。</span><span class="sxs-lookup"><span data-stu-id="01250-165">Drag a **Message Assignment** shape from the Toolbox to the design surface and drop it under the **ReceiveFromPublicProcessResponder** shape.</span></span> <span data-ttu-id="01250-166">选择**ConstructMessage_1**已创建的形状并在**属性**窗口中，在**名称**框中，键入**ConstructPIP3A2RequestMessage**.</span><span class="sxs-lookup"><span data-stu-id="01250-166">Select the **ConstructMessage_1** shape that was created and in the **Properties** window, in the **Name** box, type **ConstructPIP3A2RequestMessage**.</span></span>  
  
2. <span data-ttu-id="01250-167">拖动**转换**形状到设计图面并将其下放置**ConstructPIP3A2RequestMessage**形状。</span><span class="sxs-lookup"><span data-stu-id="01250-167">Drag a **Transform** shape to the design surface and drop it under the **ConstructPIP3A2RequestMessage** shape.</span></span> <span data-ttu-id="01250-168">选择**ConstructMessage_1**已创建的形状并在**属性**窗口中，在**名称**框中，键入**ConstructContoso3A2RequestMessage**.</span><span class="sxs-lookup"><span data-stu-id="01250-168">Select the **ConstructMessage_1** shape that was created and in the **Properties** window, in the **Name** box, type **ConstructContoso3A2RequestMessage**.</span></span>  
  
3. <span data-ttu-id="01250-169">拖动**发送**形状到设计图面并将其下放置**ConstructContoso3A2RequestMessage**形状。</span><span class="sxs-lookup"><span data-stu-id="01250-169">Drag a **Send** shape to the design surface and drop it under the **ConstructContoso3A2RequestMessage** shape.</span></span>  
  
4. <span data-ttu-id="01250-170">拖动**接收**形状到设计图面并将其下放置**Send_1**形状。</span><span class="sxs-lookup"><span data-stu-id="01250-170">Drag a **Receive** shape to the design surface and drop it under the **Send_1** shape.</span></span>  
  
5. <span data-ttu-id="01250-171">在业务流程设计图面上，单击空白区域。</span><span class="sxs-lookup"><span data-stu-id="01250-171">On the orchestration design surface, click an empty area.</span></span>  
  
6. <span data-ttu-id="01250-172">在属性窗口中，选择**事务类型**属性，，然后单击**长期**。</span><span class="sxs-lookup"><span data-stu-id="01250-172">In the Properties window, select the **Transaction Type** property, and then click **Long Running**.</span></span>  
  
7. <span data-ttu-id="01250-173">拖动**作用域**形状到设计图面并将其下放置**Receive_1**形状。</span><span class="sxs-lookup"><span data-stu-id="01250-173">Drag a **Scope** shape to the design surface and drop it under the **Receive_1** shape.</span></span>  
  
8. <span data-ttu-id="01250-174">在属性窗口中，从**事务类型**属性下拉列表中，选择**原子**有关**范围**形状。</span><span class="sxs-lookup"><span data-stu-id="01250-174">In the Properties window, from the **Transaction Type** property drop-down list, select **Atomic** for the **Scope** shape.</span></span>  
  
9. <span data-ttu-id="01250-175">拖动**调用规则**至设计图面上形状，然后将其放上显示的标签**从工具箱中删除形状**内部**范围**形状。</span><span class="sxs-lookup"><span data-stu-id="01250-175">Drag a **Call Rules** shape to the design surface and drop it on the label that says **Drop a shape from the toolbox here** inside the **Scope** shape.</span></span> <span data-ttu-id="01250-176">中的属性窗口**调用规则**形状，在**名称**框中，键入**Execute3A2Vocabulary**。</span><span class="sxs-lookup"><span data-stu-id="01250-176">In the Properties window for the **Call Rules** shape, in the **Name** box, type **Execute3A2Vocabulary**.</span></span>  
  
10. <span data-ttu-id="01250-177">拖动**转换**形状到设计图面并将其下放置**Scope_1**形状。</span><span class="sxs-lookup"><span data-stu-id="01250-177">Drag a **Transform** shape to the design surface and drop it under the **Scope_1** shape.</span></span> <span data-ttu-id="01250-178">单击**ConstructMessage_1**形状。</span><span class="sxs-lookup"><span data-stu-id="01250-178">Click the **ConstructMessage_1** shape.</span></span> <span data-ttu-id="01250-179">在属性窗口中**名称**框中，键入**Construct3A2ResponseMessage**。</span><span class="sxs-lookup"><span data-stu-id="01250-179">In the Properties window, in the **Name** box, type **Construct3A2ResponseMessage**.</span></span>  
  
11. <span data-ttu-id="01250-180">拖动**表达式**形状到设计图面并将其下放置**Construct3A2ResponseMessageTransform**形状。</span><span class="sxs-lookup"><span data-stu-id="01250-180">Drag an **Expression** shape to the design surface and drop it under the **Construct3A2ResponseMessageTransform** shape.</span></span>  
  
12. <span data-ttu-id="01250-181">在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后在**文件**，单击**全部保存**以保存项目。</span><span class="sxs-lookup"><span data-stu-id="01250-181">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File**, click **Save All** to save the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01250-182">请参阅</span><span class="sxs-lookup"><span data-stu-id="01250-182">See Also</span></span>  
 [<span data-ttu-id="01250-183">步骤 6：配置业务流程形状 (Contoso)</span><span class="sxs-lookup"><span data-stu-id="01250-183">Step 6: Configuring Orchestration Shapes (Contoso)</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-configuring-orchestration-shapes-contoso.md)