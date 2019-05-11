---
title: 第 2 步：创建库存请求架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fa9ad9f-b815-4baf-8299-556869b8dde7
caps.latest.revision: 45
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0729083983aad67ad751aa3dd25d63c6a4c031f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392752"
---
# <a name="step-2-create-the-inventory-request-schema"></a><span data-ttu-id="adfee-102">第 2 步：创建库存请求架构</span><span class="sxs-lookup"><span data-stu-id="adfee-102">Step 2: Create the Inventory Request Schema</span></span>
<span data-ttu-id="adfee-103">![步骤 2，共 5](../core/media/step-2of5.gif "Step_2of5")</span><span class="sxs-lookup"><span data-stu-id="adfee-103">![Step 2 of 5](../core/media/step-2of5.gif "Step_2of5")</span></span>  

 <span data-ttu-id="adfee-104">**若要完成的时间：** 7 分钟</span><span class="sxs-lookup"><span data-stu-id="adfee-104">**Time to complete:** 7 minutes</span></span>  

 <span data-ttu-id="adfee-105">**目标：** 在此步骤中，定义库存补货消息的架构。</span><span class="sxs-lookup"><span data-stu-id="adfee-105">**Objective:** In this step, you define the schema of the inventory replenishment message.</span></span>  <span data-ttu-id="adfee-106">仓库系统发送此消息以请求库存补货。</span><span class="sxs-lookup"><span data-stu-id="adfee-106">The warehouse system sends this message for requesting inventory replenishment.</span></span>  <span data-ttu-id="adfee-107">这是一个必须为此项目创建的两个架构。</span><span class="sxs-lookup"><span data-stu-id="adfee-107">This is one of the two schemas you must create for this project.</span></span>  

 <span data-ttu-id="adfee-108">**目的：** XML 不仅结构和标识信息与标准化的标记代码，但也有使用架构的功能。</span><span class="sxs-lookup"><span data-stu-id="adfee-108">**Purpose:** XML not only structures and identifies information with standardized markup codes, but also has the ability to use schemas.</span></span> <span data-ttu-id="adfee-109">架构是由其他 XML 文档的 XML 文档的工作方式类似于字典和用作参考。</span><span class="sxs-lookup"><span data-stu-id="adfee-109">A schema is an XML document that works like a dictionary and is used as a reference by other XML documents.</span></span> <span data-ttu-id="adfee-110">架构代码定义 XML 元素的拼写和由这些元素括起来的数据类型。</span><span class="sxs-lookup"><span data-stu-id="adfee-110">The schema code defines the spelling of XML elements and the type of data enclosed by those elements.</span></span> <span data-ttu-id="adfee-111">使用架构为 XML 文档，并确保结构和类型的信息是正确的处理程序提供一种简便方法。</span><span class="sxs-lookup"><span data-stu-id="adfee-111">Using schemas provides an easy way for a program to process XML documents and ensures that the structure and type of information is correct.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="adfee-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="adfee-112">Prerequisites</span></span>  
 <span data-ttu-id="adfee-113">在开始此步骤之前，请注意以下要求：</span><span class="sxs-lookup"><span data-stu-id="adfee-113">Note the following requirements before you begin this step:</span></span>  

-   <span data-ttu-id="adfee-114">在开始此步骤之前，必须完成[步骤 1:创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md)。</span><span class="sxs-lookup"><span data-stu-id="adfee-114">Before you begin this step you must complete [Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md).</span></span>  

## <a name="procedures"></a><span data-ttu-id="adfee-115">过程</span><span class="sxs-lookup"><span data-stu-id="adfee-115">Procedures</span></span>  
 <span data-ttu-id="adfee-116">在[步骤 1:创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md)，创建了一个新[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="adfee-116">In [Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md), you created a new [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project.</span></span>  <span data-ttu-id="adfee-117">如果您关闭[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]窗口中，您可以使用以下过程以打开该项目。</span><span class="sxs-lookup"><span data-stu-id="adfee-117">If you close the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] window, you can use the following procedure to open the project.</span></span>  <span data-ttu-id="adfee-118">否则，则可以跳过此过程中，"若要打开 Visual Studio 项目"。</span><span class="sxs-lookup"><span data-stu-id="adfee-118">Otherwise, you can skip this procedure, “To open the Visual Studio project”.</span></span>  

#### <a name="to-open-the-visual-studio-project"></a><span data-ttu-id="adfee-119">若要打开 Visual Studio 项目</span><span class="sxs-lookup"><span data-stu-id="adfee-119">To open the Visual Studio project</span></span>  

1. <span data-ttu-id="adfee-120">启动**Microsoft Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="adfee-120">Start **Microsoft Visual Studio**.</span></span>  

2. <span data-ttu-id="adfee-121">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**打开**，然后单击**项目/解决方案**。</span><span class="sxs-lookup"><span data-stu-id="adfee-121">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  

3. <span data-ttu-id="adfee-122">在中**打开项目**对话框中，浏览到**C:\BTSTutorials\EAISolution\EAISolution.sln**解决方案文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="adfee-122">In the **Open Project** dialog box, browse to the **C:\BTSTutorials\EAISolution\EAISolution.sln** solution file, and then click **Open**.</span></span>  

   <span data-ttu-id="adfee-123">在下面的过程中，向库存补货消息的项目添加新的架构文件。</span><span class="sxs-lookup"><span data-stu-id="adfee-123">In the following procedure, you add a new schema file to the project for the inventory replenishment message.</span></span>  

#### <a name="to-add-a-new-schema-to-the-project"></a><span data-ttu-id="adfee-124">若要向项目添加新架构</span><span class="sxs-lookup"><span data-stu-id="adfee-124">To add a new schema to the project</span></span>  

1. <span data-ttu-id="adfee-125">在解决方案资源管理器中右键单击**EAISchemas**项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="adfee-125">In Solution Explorer, right-click the **EAISchemas** project, point to **Add**, and then click **New Item**.</span></span>  

2. <span data-ttu-id="adfee-126">在中**添加新项-EAISchemas**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="adfee-126">In the **Add New Item - EAISchemas** dialog box, do the following:</span></span>  


   |        <span data-ttu-id="adfee-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="adfee-127">Use this</span></span>         |                   <span data-ttu-id="adfee-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="adfee-128">To do this</span></span>                   |
   |-------------------------|------------------------------------------------|
   | <span data-ttu-id="adfee-129">**已安装的模板**</span><span class="sxs-lookup"><span data-stu-id="adfee-129">**Installed Templates**</span></span> | <span data-ttu-id="adfee-130">单击**架构文件**，然后单击**架构**。</span><span class="sxs-lookup"><span data-stu-id="adfee-130">Click **Schema Files**, then click **Schema**.</span></span> |
   |        <span data-ttu-id="adfee-131">**名称**</span><span class="sxs-lookup"><span data-stu-id="adfee-131">**Name**</span></span>         |             <span data-ttu-id="adfee-132">类型**Request.xsd**。</span><span class="sxs-lookup"><span data-stu-id="adfee-132">Type **Request.xsd**.</span></span>              |


3. <span data-ttu-id="adfee-133">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="adfee-133">Click **Add**.</span></span> <span data-ttu-id="adfee-134">显示架构树和 XSD 窗格。</span><span class="sxs-lookup"><span data-stu-id="adfee-134">The schema tree and XSD pane appear.</span></span> <span data-ttu-id="adfee-135">此区域[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]称为作为 BizTalk 编辑器。</span><span class="sxs-lookup"><span data-stu-id="adfee-135">This area of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] is referred to as BizTalk Editor.</span></span> <span data-ttu-id="adfee-136">此外，新添加的架构将显示在解决方案资源管理器中的 EAISchemas 项目下。</span><span class="sxs-lookup"><span data-stu-id="adfee-136">In addition, your new schema appears in Solution Explorer below the EAISchemas project.</span></span>  

    <span data-ttu-id="adfee-137">![BizTalk 项目的不同部分](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")</span><span class="sxs-lookup"><span data-stu-id="adfee-137">![Different Parts of BizTalk Project](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")</span></span>  

#### <a name="to-add-elements-to-the-schema"></a><span data-ttu-id="adfee-138">若要将元素添加到架构</span><span class="sxs-lookup"><span data-stu-id="adfee-138">To add elements to the schema</span></span>  

1. <span data-ttu-id="adfee-139">在架构树中，单击**根**节点。</span><span class="sxs-lookup"><span data-stu-id="adfee-139">In schema tree, click the **Root** node.</span></span>  

2. <span data-ttu-id="adfee-140">在属性窗格中的值更改**节点名称**属性设置为`Request`，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="adfee-140">In the Properties pane, change the value of the **Node Name** property to `Request`, and then press ENTER.</span></span>  

3. <span data-ttu-id="adfee-141">在架构树中，右键单击**请求**节点，指向**插入 Schema 节点**，然后单击**子记录**。</span><span class="sxs-lookup"><span data-stu-id="adfee-141">In schema tree, right-click the **Request** node, point to **Insert Schema Node**, and then click **Child Record**.</span></span>  

4. <span data-ttu-id="adfee-142">类型`Header`作为子记录，然后按 ENTER 键的新名称。</span><span class="sxs-lookup"><span data-stu-id="adfee-142">Type `Header` as the new name for the child record, and then press ENTER.</span></span>  

5. <span data-ttu-id="adfee-143">重复步骤 3 和 4，以创建另一个子记录**请求**节点，并将其命名`Items`。</span><span class="sxs-lookup"><span data-stu-id="adfee-143">Repeat step 3 and 4 to create a second child record for the **Request** node, and name it `Items`.</span></span>  

6. <span data-ttu-id="adfee-144">在架构树中，右键单击**标头**节点，指向**插入 Schema 节点**，然后单击**子字段元素**。</span><span class="sxs-lookup"><span data-stu-id="adfee-144">In schema tree, right-click the **Header** node, point to **Insert Schema Node**, and then click **Child Field Element**.</span></span>  

7. <span data-ttu-id="adfee-145">类型`ReqID`作为以及该元素，然后按 ENTER 键的新名称。</span><span class="sxs-lookup"><span data-stu-id="adfee-145">Type `ReqID` as the new name for the element, and then press ENTER.</span></span>  

8. <span data-ttu-id="adfee-146">重复步骤 6 和 7，创建另一个子字段元素**标头**节点，并将其命名`OrderDate`。</span><span class="sxs-lookup"><span data-stu-id="adfee-146">Repeat step 6 and 7 to create a second child field element for the **Header** node, and name it `OrderDate`.</span></span>

9. <span data-ttu-id="adfee-147">重复步骤 6 和 7，以创建第三个子字段元素**标头**节点，并将其命名`GrandTotal`。</span><span class="sxs-lookup"><span data-stu-id="adfee-147">Repeat step 6 and 7 to create a third child field element for the **Header** node, and name it `GrandTotal`.</span></span>

10. <span data-ttu-id="adfee-148">在架构树中，右键单击**项**节点，指向**插入 Schemas 节点**，然后单击**子记录**。</span><span class="sxs-lookup"><span data-stu-id="adfee-148">In schema tree, right-click the **Items** node, point to **Insert Schemas Node**, and then click **Child Record**.</span></span>  

11. <span data-ttu-id="adfee-149">类型`Item`作为子记录，然后按 ENTER 键的新名称。</span><span class="sxs-lookup"><span data-stu-id="adfee-149">Type `Item` as the new name for the child record, and then press ENTER.</span></span>  

12. <span data-ttu-id="adfee-150">在架构树中，右键单击**项**节点，并添加下列子字段元素：</span><span class="sxs-lookup"><span data-stu-id="adfee-150">In schema tree, right-click the **Item** node, and add the following child field elements:</span></span>  

    - `Description`  

    - `Quantity`  

    - `UnitPrice`  

      <span data-ttu-id="adfee-151">已完成的 Request.xsd 应类似于下图。</span><span class="sxs-lookup"><span data-stu-id="adfee-151">The completed Request.xsd should look similar to the following figure.</span></span>  

      <span data-ttu-id="adfee-152">![使用请求架构的解决方案资源管理器](../core/media/solutionexplorerwiththerequestschema.gif "SolutionExplorerwiththeRequestSchema")</span><span class="sxs-lookup"><span data-stu-id="adfee-152">![Solution Explorer with the Request Schema](../core/media/solutionexplorerwiththerequestschema.gif "SolutionExplorerwiththeRequestSchema")</span></span>  

    <span data-ttu-id="adfee-153">时将节点添加到架构，BizTalk 编辑器提供一组默认值为其属性。</span><span class="sxs-lookup"><span data-stu-id="adfee-153">When you add nodes to a schema, BizTalk Editor gives a set of default values for their properties.</span></span>  <span data-ttu-id="adfee-154">必须将它们根据要求配置。</span><span class="sxs-lookup"><span data-stu-id="adfee-154">You must configure them based on the requirements.</span></span>  

#### <a name="to-configure-the-elements"></a><span data-ttu-id="adfee-155">若要配置的元素</span><span class="sxs-lookup"><span data-stu-id="adfee-155">To configure the elements</span></span>  

1. <span data-ttu-id="adfee-156">在架构树中，单击**OrderDate**以将其选中。</span><span class="sxs-lookup"><span data-stu-id="adfee-156">In schema tree, click **OrderDate** to select it.</span></span>  

2. <span data-ttu-id="adfee-157">在属性窗格中更改**数据类型**到**xs: datetime**。</span><span class="sxs-lookup"><span data-stu-id="adfee-157">In the Properties pane, change **Data Type** to **xs:dateTime**.</span></span>  

3. <span data-ttu-id="adfee-158">重复步骤 1 和 2 来配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="adfee-158">Repeat step 1 and 2 to configure the following properties:</span></span>  

   |<span data-ttu-id="adfee-159">元素</span><span class="sxs-lookup"><span data-stu-id="adfee-159">Element</span></span>|<span data-ttu-id="adfee-160">属性</span><span class="sxs-lookup"><span data-stu-id="adfee-160">Property</span></span>|<span data-ttu-id="adfee-161">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="adfee-161">Value</span></span>|  
   |-------------|--------------|-----------|  
   |<span data-ttu-id="adfee-162">**GrandTotal**</span><span class="sxs-lookup"><span data-stu-id="adfee-162">**GrandTotal**</span></span>|<span data-ttu-id="adfee-163">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="adfee-163">**Data Type**</span></span>|<span data-ttu-id="adfee-164">**Xs:decimal**</span><span class="sxs-lookup"><span data-stu-id="adfee-164">**Xs:decimal**</span></span>|  
   |<span data-ttu-id="adfee-165">**项**</span><span class="sxs-lookup"><span data-stu-id="adfee-165">**Item**</span></span>|<span data-ttu-id="adfee-166">**最大出现次数**</span><span class="sxs-lookup"><span data-stu-id="adfee-166">**Max Occurs**</span></span>|<span data-ttu-id="adfee-167">**不受限制**</span><span class="sxs-lookup"><span data-stu-id="adfee-167">**Unbounded**</span></span>|  
   |<span data-ttu-id="adfee-168">**项**</span><span class="sxs-lookup"><span data-stu-id="adfee-168">**Item**</span></span>|<span data-ttu-id="adfee-169">**最小出现次数**</span><span class="sxs-lookup"><span data-stu-id="adfee-169">**Min Occurs**</span></span>|<span data-ttu-id="adfee-170">**1**</span><span class="sxs-lookup"><span data-stu-id="adfee-170">**1**</span></span>|  
   |<span data-ttu-id="adfee-171">**数量**</span><span class="sxs-lookup"><span data-stu-id="adfee-171">**Quantity**</span></span>|<span data-ttu-id="adfee-172">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="adfee-172">**Data Type**</span></span>|<span data-ttu-id="adfee-173">**xs:unsignedInt**</span><span class="sxs-lookup"><span data-stu-id="adfee-173">**xs:unsignedInt**</span></span>|  

   <span data-ttu-id="adfee-174">架构可以具有多个元素，但你的应用程序可能只需进行数据处理使用其中几个。</span><span class="sxs-lookup"><span data-stu-id="adfee-174">A schema can have many elements, but your application may only require that you use a few of them for your data processing.</span></span> <span data-ttu-id="adfee-175">若要保存的计算机资源，BizTalk Server 不自动读取每个架构元素。</span><span class="sxs-lookup"><span data-stu-id="adfee-175">To save computer resources, BizTalk Server doesn't automatically read each schema element.</span></span> <span data-ttu-id="adfee-176">如果你想要从特定元素中读取数据的 BizTalk Server，必须通过使用 BizTalk 编辑器以升级其属性来标识该元素。</span><span class="sxs-lookup"><span data-stu-id="adfee-176">If you want BizTalk Server to read data from a specific element, you must identify that element by using BizTalk Editor to promote its properties.</span></span>  

   <span data-ttu-id="adfee-177">我们将在中创建的业务流程[第 2 课：定义业务流程](../core/lesson-2-define-the-business-process.md)会基于 GrandTotal 字段来路由消息。</span><span class="sxs-lookup"><span data-stu-id="adfee-177">The orchestration that we will create in [Lesson 2: Define the Business Process](../core/lesson-2-define-the-business-process.md) will base on the GrandTotal field to route messages.</span></span>  <span data-ttu-id="adfee-178">因此，必须升级 GrandTotal 字段。</span><span class="sxs-lookup"><span data-stu-id="adfee-178">So we must promote the GrandTotal field.</span></span>  

#### <a name="to-promote-an-element"></a><span data-ttu-id="adfee-179">若要升级元素</span><span class="sxs-lookup"><span data-stu-id="adfee-179">To promote an element</span></span>  

1.  <span data-ttu-id="adfee-180">在架构树中，右键单击**GrandTotal**，依次指向**Promote**，然后单击**快速升级**。</span><span class="sxs-lookup"><span data-stu-id="adfee-180">In Schema tree, right-click **GrandTotal**, point to **Promote**, and then click **Quick Promotions**.</span></span>  

2.  <span data-ttu-id="adfee-181">单击**确定**以确认添加属性架构。</span><span class="sxs-lookup"><span data-stu-id="adfee-181">Click **OK** to acknowledge adding a property schema.</span></span>  

3.  <span data-ttu-id="adfee-182">在“文件”  菜单上，单击“全部保存” 。</span><span class="sxs-lookup"><span data-stu-id="adfee-182">On the **File** menu, click **Save All**.</span></span>  

## <a name="what-did-i-just-do"></a><span data-ttu-id="adfee-183">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="adfee-183">What did I just do?</span></span>  
 <span data-ttu-id="adfee-184">在此步骤中，您将定义仓库库存补货消息架构。</span><span class="sxs-lookup"><span data-stu-id="adfee-184">In this step, you defined the warehouse inventory replenishment message schema.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="adfee-185">后续步骤</span><span class="sxs-lookup"><span data-stu-id="adfee-185">Next Steps</span></span>  
 <span data-ttu-id="adfee-186">定义请求拒绝消息架构。</span><span class="sxs-lookup"><span data-stu-id="adfee-186">You define the request decline message schema.</span></span>  

## <a name="see-also"></a><span data-ttu-id="adfee-187">请参阅</span><span class="sxs-lookup"><span data-stu-id="adfee-187">See Also</span></span>  
 <span data-ttu-id="adfee-188">[步骤 1：创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="adfee-188">[Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md) </span></span>  
 <span data-ttu-id="adfee-189">[步骤 3：创建请求拒绝架构](../core/step-3-create-the-request-decline-schema.md) </span><span class="sxs-lookup"><span data-stu-id="adfee-189">[Step 3: Create the Request Decline Schema](../core/step-3-create-the-request-decline-schema.md) </span></span>  
 <span data-ttu-id="adfee-190">[步骤 4：创建映射](../core/step-4-create-the-map.md) </span><span class="sxs-lookup"><span data-stu-id="adfee-190">[Step 4: Create the Map](../core/step-4-create-the-map.md) </span></span>  
 <span data-ttu-id="adfee-191">[步骤 5：生成 EAISchemas 项目](../core/step-5-build-the-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="adfee-191">[Step 5: Build the EAISchemas Project](../core/step-5-build-the-eaischemas-project.md) </span></span>  
 <span data-ttu-id="adfee-192">[使用 BizTalk 编辑器创建架构](../core/creating-schemas-using-biztalk-editor.md) </span><span class="sxs-lookup"><span data-stu-id="adfee-192">[Creating Schemas Using BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md) </span></span>  
 [<span data-ttu-id="adfee-193">关于 BizTalk 消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="adfee-193">About BizTalk Message Context Properties</span></span>](../core/about-biztalk-message-context-properties.md)
