---
title: "步骤 2： 创建清单请求架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fa9ad9f-b815-4baf-8299-556869b8dde7
caps.latest.revision: "45"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5199b20a75b82e12ad76b96903538487a3128668
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-the-inventory-request-schema"></a><span data-ttu-id="be063-102">步骤 2：创建库存请求架构</span><span class="sxs-lookup"><span data-stu-id="be063-102">Step 2: Create the Inventory Request Schema</span></span>
<span data-ttu-id="be063-103">![步骤 2 5](../core/media/step-2of5.gif "Step_2of5")</span><span class="sxs-lookup"><span data-stu-id="be063-103">![Step 2 of 5](../core/media/step-2of5.gif "Step_2of5")</span></span>  
  
 <span data-ttu-id="be063-104">**完成时间：** 7 分钟</span><span class="sxs-lookup"><span data-stu-id="be063-104">**Time to complete:** 7 minutes</span></span>  
  
 <span data-ttu-id="be063-105">**目标：**在此步骤中，定义库存补货消息的架构。</span><span class="sxs-lookup"><span data-stu-id="be063-105">**Objective:** In this step, you define the schema of the inventory replenishment message.</span></span>  <span data-ttu-id="be063-106">仓库系统发送此消息以请求库存补货。</span><span class="sxs-lookup"><span data-stu-id="be063-106">The warehouse system sends this message for requesting inventory replenishment.</span></span>  <span data-ttu-id="be063-107">此架构是必须为该项目创建的两个架构之一。</span><span class="sxs-lookup"><span data-stu-id="be063-107">This is one of the two schemas you must create for this project.</span></span>  
  
 <span data-ttu-id="be063-108">**用途：** XML 不仅结构和标识信息与标准化的标记代码，但也有使用架构的能力。</span><span class="sxs-lookup"><span data-stu-id="be063-108">**Purpose:** XML not only structures and identifies information with standardized markup codes, but also has the ability to use schemas.</span></span> <span data-ttu-id="be063-109">架构是一类工作方式与字典类似的 XML 文档，可供其他 XML 文档用作参考。</span><span class="sxs-lookup"><span data-stu-id="be063-109">A schema is an XML document that works like a dictionary and is used as a reference by other XML documents.</span></span> <span data-ttu-id="be063-110">架构代码定义 XML 元素的拼写以及用这些元素括起来的数据类型。</span><span class="sxs-lookup"><span data-stu-id="be063-110">The schema code defines the spelling of XML elements and the type of data enclosed by those elements.</span></span> <span data-ttu-id="be063-111">通过使用架构，程序可轻松处理 XML 文档，并确保信息的结构和类型正确。</span><span class="sxs-lookup"><span data-stu-id="be063-111">Using schemas provides an easy way for a program to process XML documents and ensures that the structure and type of information is correct.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="be063-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="be063-112">Prerequisites</span></span>  
 <span data-ttu-id="be063-113">在开始此步骤之前，请注意以下要求：</span><span class="sxs-lookup"><span data-stu-id="be063-113">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="be063-114">在开始此步骤之前必须完成[步骤 1： 创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md)。</span><span class="sxs-lookup"><span data-stu-id="be063-114">Before you begin this step you must complete [Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="be063-115">过程</span><span class="sxs-lookup"><span data-stu-id="be063-115">Procedures</span></span>  
 <span data-ttu-id="be063-116">在[步骤 1： 创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md)，你创建的新[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="be063-116">In [Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md), you created a new [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project.</span></span>  <span data-ttu-id="be063-117">如果关闭 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 窗口，可使用以下过程打开该项目。</span><span class="sxs-lookup"><span data-stu-id="be063-117">If you close the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] window, you can use the following procedure to open the project.</span></span>  <span data-ttu-id="be063-118">否则，可跳过“打开 Visual Studio 项目”这一步骤。</span><span class="sxs-lookup"><span data-stu-id="be063-118">Otherwise, you can skip this procedure, “To open the Visual Studio project”.</span></span>  
  
#### <a name="to-open-the-visual-studio-project"></a><span data-ttu-id="be063-119">打开 Visual Studio 项目</span><span class="sxs-lookup"><span data-stu-id="be063-119">To open the Visual Studio project</span></span>  
  
1.  <span data-ttu-id="be063-120">启动**Microsoft Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="be063-120">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="be063-121">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]上**文件**菜单上，指向**打开**，然后单击**项目/解决方案**。</span><span class="sxs-lookup"><span data-stu-id="be063-121">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="be063-122">在**打开项目**对话框中，浏览到**C:\BTSTutorials\EAISolution\EAISolution.sln**解决方案文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="be063-122">In the **Open Project** dialog box, browse to the **C:\BTSTutorials\EAISolution\EAISolution.sln** solution file, and then click **Open**.</span></span>  
  
 <span data-ttu-id="be063-123">在下面的过程中，针对库存补货消息向项目添加新架构文件。</span><span class="sxs-lookup"><span data-stu-id="be063-123">In the following procedure, you add a new schema file to the project for the inventory replenishment message.</span></span>  
  
#### <a name="to-add-a-new-schema-to-the-project"></a><span data-ttu-id="be063-124">向项目添加新架构</span><span class="sxs-lookup"><span data-stu-id="be063-124">To add a new schema to the project</span></span>  
  
1.  <span data-ttu-id="be063-125">在解决方案资源管理器，右键单击**EAISchemas**项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="be063-125">In Solution Explorer, right-click the **EAISchemas** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="be063-126">在**添加新项-EAISchemas**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="be063-126">In the **Add New Item - EAISchemas** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="be063-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="be063-127">Use this</span></span>|<span data-ttu-id="be063-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="be063-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="be063-129">**已安装的模板**</span><span class="sxs-lookup"><span data-stu-id="be063-129">**Installed Templates**</span></span>|<span data-ttu-id="be063-130">单击**架构文件**，然后单击**架构**。</span><span class="sxs-lookup"><span data-stu-id="be063-130">Click **Schema Files**, then click **Schema**.</span></span>|  
    |<span data-ttu-id="be063-131">**名称**</span><span class="sxs-lookup"><span data-stu-id="be063-131">**Name**</span></span>|<span data-ttu-id="be063-132">类型**Request.xsd**。</span><span class="sxs-lookup"><span data-stu-id="be063-132">Type **Request.xsd**.</span></span>|  
  
3.  <span data-ttu-id="be063-133">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="be063-133">Click **Add**.</span></span> <span data-ttu-id="be063-134">此时，将显示架构树和 XSD 窗格。</span><span class="sxs-lookup"><span data-stu-id="be063-134">The schema tree and XSD pane appear.</span></span> <span data-ttu-id="be063-135">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，此区域称为“BizTalk 编辑器”。</span><span class="sxs-lookup"><span data-stu-id="be063-135">This area of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] is referred to as BizTalk Editor.</span></span> <span data-ttu-id="be063-136">此外，新添加的架构将显示在解决方案资源管理器中的 EAISchemas 项目下。</span><span class="sxs-lookup"><span data-stu-id="be063-136">In addition, your new schema appears in Solution Explorer below the EAISchemas project.</span></span>  
  
     <span data-ttu-id="be063-137">![BizTalk 项目不同部分](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")</span><span class="sxs-lookup"><span data-stu-id="be063-137">![Different Parts of BizTalk Project](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")</span></span>  
  
#### <a name="to-add-elements-to-the-schema"></a><span data-ttu-id="be063-138">向架构添加元素</span><span class="sxs-lookup"><span data-stu-id="be063-138">To add elements to the schema</span></span>  
  
1.  <span data-ttu-id="be063-139">在架构树中，单击**根**节点。</span><span class="sxs-lookup"><span data-stu-id="be063-139">In schema tree, click the **Root** node.</span></span>  
  
2.  <span data-ttu-id="be063-140">在属性窗格中，将的值更改**节点名称**属性`Request`，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="be063-140">In the Properties pane, change the value of the **Node Name** property to `Request`, and then press ENTER.</span></span>  
  
3.  <span data-ttu-id="be063-141">在架构树中，右键单击**请求**节点，指向**插入架构节点**，然后单击**子记录**。</span><span class="sxs-lookup"><span data-stu-id="be063-141">In schema tree, right-click the **Request** node, point to **Insert Schema Node**, and then click **Child Record**.</span></span>  
  
4.  <span data-ttu-id="be063-142">类型`Header`作为子记录，然后按 enter 键的新名称。</span><span class="sxs-lookup"><span data-stu-id="be063-142">Type `Header` as the new name for the child record, and then press ENTER.</span></span>  
  
5.  <span data-ttu-id="be063-143">重复步骤 3 和 4，以创建第二个子记录**请求**节点，并将其命名`Items`。</span><span class="sxs-lookup"><span data-stu-id="be063-143">Repeat step 3 and 4 to create a second child record for the **Request** node, and name it `Items`.</span></span>  
  
6.  <span data-ttu-id="be063-144">在架构树中，右键单击**标头**节点，指向**插入架构节点**，然后单击**子字段元素**。</span><span class="sxs-lookup"><span data-stu-id="be063-144">In schema tree, right-click the **Header** node, point to **Insert Schema Node**, and then click **Child Field Element**.</span></span>  
  
7.  <span data-ttu-id="be063-145">类型`ReqID`作为以及该元素，然后按 enter 键的新名称。</span><span class="sxs-lookup"><span data-stu-id="be063-145">Type `ReqID` as the new name for the element, and then press ENTER.</span></span>  
  
8.  <span data-ttu-id="be063-146">重复步骤 6 和 7，以创建第二个子字段元素**标头**节点，并将其命名`OrderDate`。</span><span class="sxs-lookup"><span data-stu-id="be063-146">Repeat step 6 and 7 to create a second child field element for the **Header** node, and name it `OrderDate`.</span></span>  
  
9. <span data-ttu-id="be063-147">在架构树中，右键单击**项**节点，指向**插入架构节点**，然后单击**子记录**。</span><span class="sxs-lookup"><span data-stu-id="be063-147">In schema tree, right-click the **Items** node, point to **Insert Schemas Node**, and then click **Child Record**.</span></span>  
  
10. <span data-ttu-id="be063-148">类型`Item`作为子记录，然后按 enter 键的新名称。</span><span class="sxs-lookup"><span data-stu-id="be063-148">Type `Item` as the new name for the child record, and then press ENTER.</span></span>  
  
11. <span data-ttu-id="be063-149">在架构树中，右键单击**项**节点，并添加以下子字段元素：</span><span class="sxs-lookup"><span data-stu-id="be063-149">In schema tree, right-click the **Item** node, and add the following child field elements:</span></span>  
  
    -   `Description`  
  
    -   `Quantity`  
  
    -   `UnitPrice`  
  
     <span data-ttu-id="be063-150">完成的 Request.xsd 应类似于下图：</span><span class="sxs-lookup"><span data-stu-id="be063-150">The completed Request.xsd should look similar to the following figure.</span></span>  
  
     <span data-ttu-id="be063-151">![解决方案资源管理器的请求架构与](../core/media/solutionexplorerwiththerequestschema.gif "SolutionExplorerwiththeRequestSchema")</span><span class="sxs-lookup"><span data-stu-id="be063-151">![Solution Explorer with the Request Schema](../core/media/solutionexplorerwiththerequestschema.gif "SolutionExplorerwiththeRequestSchema")</span></span>  
  
 <span data-ttu-id="be063-152">在向架构添加节点时，BizTalk 编辑器会为这些节点的属性分配一组默认值。</span><span class="sxs-lookup"><span data-stu-id="be063-152">When you add nodes to a schema, BizTalk Editor gives a set of default values for their properties.</span></span>  <span data-ttu-id="be063-153">必须按照要求配置它们。</span><span class="sxs-lookup"><span data-stu-id="be063-153">You must configure them based on the requirements.</span></span>  
  
#### <a name="to-configure-the-elements"></a><span data-ttu-id="be063-154">若要配置的元素</span><span class="sxs-lookup"><span data-stu-id="be063-154">To configure the elements</span></span>  
  
1.  <span data-ttu-id="be063-155">在架构树中，单击**OrderDate**以将其选中。</span><span class="sxs-lookup"><span data-stu-id="be063-155">In schema tree, click **OrderDate** to select it.</span></span>  
  
2.  <span data-ttu-id="be063-156">在属性窗格中，更改**数据类型**到**xs: datetime**。</span><span class="sxs-lookup"><span data-stu-id="be063-156">In the Properties pane, change **Data Type** to **xs:dateTime**.</span></span>  
  
3.  <span data-ttu-id="be063-157">重复步骤 1 和 2 来配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="be063-157">Repeat step 1 and 2 to configure the following properties:</span></span>  
  
    |<span data-ttu-id="be063-158">元素</span><span class="sxs-lookup"><span data-stu-id="be063-158">Element</span></span>|<span data-ttu-id="be063-159">属性</span><span class="sxs-lookup"><span data-stu-id="be063-159">Property</span></span>|<span data-ttu-id="be063-160">值</span><span class="sxs-lookup"><span data-stu-id="be063-160">Value</span></span>|  
    |-------------|--------------|-----------|  
    |<span data-ttu-id="be063-161">**GrandTotal**</span><span class="sxs-lookup"><span data-stu-id="be063-161">**GrandTotal**</span></span>|<span data-ttu-id="be063-162">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="be063-162">**Data Type**</span></span>|<span data-ttu-id="be063-163">**Xs: decimal**</span><span class="sxs-lookup"><span data-stu-id="be063-163">**Xs:decimal**</span></span>|  
    |<span data-ttu-id="be063-164">**项**</span><span class="sxs-lookup"><span data-stu-id="be063-164">**Item**</span></span>|<span data-ttu-id="be063-165">**最大出现次数**</span><span class="sxs-lookup"><span data-stu-id="be063-165">**Max Occurs**</span></span>|<span data-ttu-id="be063-166">**不受限制**</span><span class="sxs-lookup"><span data-stu-id="be063-166">**Unbounded**</span></span>|  
    |<span data-ttu-id="be063-167">**项**</span><span class="sxs-lookup"><span data-stu-id="be063-167">**Item**</span></span>|<span data-ttu-id="be063-168">**最小出现次数**</span><span class="sxs-lookup"><span data-stu-id="be063-168">**Min Occurs**</span></span>|<span data-ttu-id="be063-169">**1**</span><span class="sxs-lookup"><span data-stu-id="be063-169">**1**</span></span>|  
    |<span data-ttu-id="be063-170">**数量**</span><span class="sxs-lookup"><span data-stu-id="be063-170">**Quantity**</span></span>|<span data-ttu-id="be063-171">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="be063-171">**Data Type**</span></span>|<span data-ttu-id="be063-172">**xs:unsignedInt**</span><span class="sxs-lookup"><span data-stu-id="be063-172">**xs:unsignedInt**</span></span>|  
  
 <span data-ttu-id="be063-173">虽然一个架构可包含多个元素，但应用程序可能只需要使用其中的几个元素来处理数据。</span><span class="sxs-lookup"><span data-stu-id="be063-173">A schema can have many elements, but your application may only require that you use a few of them for your data processing.</span></span> <span data-ttu-id="be063-174">为了节约计算机资源，BizTalk Server 不自动读取每个架构元素。</span><span class="sxs-lookup"><span data-stu-id="be063-174">To save computer resources, BizTalk Server doesn't automatically read each schema element.</span></span> <span data-ttu-id="be063-175">如果你希望 BizTalk Server 读取来自某个特定元素的数据，则必须使用 BizTalk 编辑器标识该元素以升级其属性。</span><span class="sxs-lookup"><span data-stu-id="be063-175">If you want BizTalk Server to read data from a specific element, you must identify that element by using BizTalk Editor to promote its properties.</span></span>  
  
 <span data-ttu-id="be063-176">我们将在创建业务流程[第 2 课： 定义业务流程](../core/lesson-2-define-the-business-process.md)将基于则 GrandTotal 字段设置为将消息路由。</span><span class="sxs-lookup"><span data-stu-id="be063-176">The orchestration that we will create in [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md) will base on the GrandTotal field to route messages.</span></span>  <span data-ttu-id="be063-177">因此，必须升级 GrandTotal 字段。</span><span class="sxs-lookup"><span data-stu-id="be063-177">So we must promote the GrandTotal field.</span></span>  
  
#### <a name="to-promote-an-element"></a><span data-ttu-id="be063-178">升级元素</span><span class="sxs-lookup"><span data-stu-id="be063-178">To promote an element</span></span>  
  
1.  <span data-ttu-id="be063-179">在架构树中，右键单击**GrandTotal**，指向**Promote**，然后单击**快速提升**。</span><span class="sxs-lookup"><span data-stu-id="be063-179">In Schema tree, right-click **GrandTotal**, point to **Promote**, and then click **Quick Promotions**.</span></span>  
  
2.  <span data-ttu-id="be063-180">单击**确定**以确认添加属性架构。</span><span class="sxs-lookup"><span data-stu-id="be063-180">Click **OK** to acknowledge adding a property schema.</span></span>  
  
3.  <span data-ttu-id="be063-181">在“文件”  菜单上，单击“全部保存” 。</span><span class="sxs-lookup"><span data-stu-id="be063-181">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="be063-182">内容回顾</span><span class="sxs-lookup"><span data-stu-id="be063-182">What did I just do?</span></span>  
 <span data-ttu-id="be063-183">在此步骤中，定义了仓库库存补货消息架构。</span><span class="sxs-lookup"><span data-stu-id="be063-183">In this step, you defined the warehouse inventory replenishment message schema.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="be063-184">后续步骤</span><span class="sxs-lookup"><span data-stu-id="be063-184">Next Steps</span></span>  
 <span data-ttu-id="be063-185">定义请求拒绝消息架构。</span><span class="sxs-lookup"><span data-stu-id="be063-185">You define the request decline message schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be063-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be063-186">See Also</span></span>  
 <span data-ttu-id="be063-187">[步骤 1： 创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="be063-187">[Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md) </span></span>  
 <span data-ttu-id="be063-188">[步骤 3： 创建请求拒绝架构](../core/step-3-create-the-request-decline-schema.md) </span><span class="sxs-lookup"><span data-stu-id="be063-188">[Step 3: Create the Request Decline Schema](../core/step-3-create-the-request-decline-schema.md) </span></span>  
 <span data-ttu-id="be063-189">[步骤 4： 创建代码图](../core/step-4-create-the-map.md) </span><span class="sxs-lookup"><span data-stu-id="be063-189">[Step 4: Create the Map](../core/step-4-create-the-map.md) </span></span>  
 <span data-ttu-id="be063-190">[步骤 5： 生成 EAISchemas 项目](../core/step-5-build-the-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="be063-190">[Step 5: Build the EAISchemas Project](../core/step-5-build-the-eaischemas-project.md) </span></span>  
 <span data-ttu-id="be063-191">[创建使用 BizTalk 编辑器的架构](../core/creating-schemas-using-biztalk-editor.md) </span><span class="sxs-lookup"><span data-stu-id="be063-191">[Creating Schemas Using BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md) </span></span>  
 [<span data-ttu-id="be063-192">有关 BizTalk 消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="be063-192">About BizTalk Message Context Properties</span></span>](../core/about-biztalk-message-context-properties.md)