---
title: 演练： 调用从业务流程的策略 |Microsoft Docs
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb2d2974-8a36-4d36-905c-799e4236ef99
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33bef51b2c702e71fcf6ef0ea0c4fd63b28fbde8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976551"
---
# <a name="walkthrough-invoking-the-policy-from-an-orchestration"></a><span data-ttu-id="34a06-102">演练： 调用的策略与业务流程</span><span class="sxs-lookup"><span data-stu-id="34a06-102">Walkthrough: Invoking the Policy from an Orchestration</span></span>
<span data-ttu-id="34a06-103">你可以通过以下方式之一从业务流程调用策略：</span><span class="sxs-lookup"><span data-stu-id="34a06-103">You can invoke a policy from an orchestration in one of the following ways:</span></span>  

- <span data-ttu-id="34a06-104">通过使用**调用规则**形状</span><span class="sxs-lookup"><span data-stu-id="34a06-104">By using the **Call Rules** shape</span></span>  

- <span data-ttu-id="34a06-105">通过使用**表达式**形状，并以编程方式调用规则引擎来执行策略 (**Policy.Execute**方法)</span><span class="sxs-lookup"><span data-stu-id="34a06-105">By using the **Expression** shape, and programmatically invoking the rule engine to execute the policy (**Policy.Execute** method)</span></span>  

  <span data-ttu-id="34a06-106">使用**调用规则**形状是最常见的方式，还从业务流程调用策略的推荐的方法。</span><span class="sxs-lookup"><span data-stu-id="34a06-106">Using the **Call Rules** shape is the most common way and also the recommended way to invoke a policy from an orchestration.</span></span> <span data-ttu-id="34a06-107">本演练提供了使用的分步过程**调用规则**形状来调用**ProcessPurchaseOrder**策略。</span><span class="sxs-lookup"><span data-stu-id="34a06-107">This walkthrough provides step-by-step procedures for using the **Call Rules** shape to invoke the **ProcessPurchaseOrder** policy.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="34a06-108">必要條件</span><span class="sxs-lookup"><span data-stu-id="34a06-108">Prerequisites</span></span>  
 <span data-ttu-id="34a06-109">必须完成[演练： 测试策略](../core/walkthrough-testing-the-policy.md)执行本演练中之前的演练。</span><span class="sxs-lookup"><span data-stu-id="34a06-109">You must complete the [Walkthrough: Testing the Policy](../core/walkthrough-testing-the-policy.md) walkthrough before performing this walkthrough.</span></span>  

## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="34a06-110">本演练概述</span><span class="sxs-lookup"><span data-stu-id="34a06-110">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="34a06-111">本演练包含七个过程，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="34a06-111">This walkthrough contains seven procedures, as described in the following table.</span></span>  

|<span data-ttu-id="34a06-112">过程标题</span><span class="sxs-lookup"><span data-stu-id="34a06-112">Procedure title</span></span>|<span data-ttu-id="34a06-113">过程说明</span><span class="sxs-lookup"><span data-stu-id="34a06-113">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="34a06-114">创建具有架构和业务流程的 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="34a06-114">To create a BizTalk project with a schema and an orchestration</span></span>|<span data-ttu-id="34a06-115">提供用于创建架构和调用的业务流程的分步说明**ProcessPurchaseOrder**策略。</span><span class="sxs-lookup"><span data-stu-id="34a06-115">Provides step-by-step instructions for creating a schema and an orchestration that invokes the **ProcessPurchaseOrder** policy.</span></span>|  
|<span data-ttu-id="34a06-116">创建消息变量</span><span class="sxs-lookup"><span data-stu-id="34a06-116">To create message variables</span></span>|<span data-ttu-id="34a06-117">提供创建在业务流程中使用的消息变量的分步说明。</span><span class="sxs-lookup"><span data-stu-id="34a06-117">Provides step-by-step instructions for creating message variables used in the orchestration.</span></span>|  
|<span data-ttu-id="34a06-118">配置形状</span><span class="sxs-lookup"><span data-stu-id="34a06-118">To configure shapes</span></span>|<span data-ttu-id="34a06-119">提供在业务流程中配置形状的分步说明。</span><span class="sxs-lookup"><span data-stu-id="34a06-119">Provides step-by-step instructions for configuring shapes in the orchestration.</span></span>|  
|<span data-ttu-id="34a06-120">若要创建端口</span><span class="sxs-lookup"><span data-stu-id="34a06-120">To create ports</span></span>|<span data-ttu-id="34a06-121">提供在业务流程中创建端口的分步说明。</span><span class="sxs-lookup"><span data-stu-id="34a06-121">Provides step-by-step instructions for creating ports in the orchestration.</span></span>|  
|<span data-ttu-id="34a06-122">将端口与形状连接</span><span class="sxs-lookup"><span data-stu-id="34a06-122">To connect ports with the shapes</span></span>|<span data-ttu-id="34a06-123">提供将端口与形状连接的分步说明。</span><span class="sxs-lookup"><span data-stu-id="34a06-123">Provides step-by-step instructions for connecting ports with the shapes.</span></span>|  
|<span data-ttu-id="34a06-124">若要生成并部署解决方案</span><span class="sxs-lookup"><span data-stu-id="34a06-124">To build and deploy the solution</span></span>|<span data-ttu-id="34a06-125">提供生成和部署解决方案的分步说明。</span><span class="sxs-lookup"><span data-stu-id="34a06-125">Provides step-by-step instructions for building and deploying the solution.</span></span>|  
|<span data-ttu-id="34a06-126">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="34a06-126">To test the solution</span></span>|<span data-ttu-id="34a06-127">提供用于测试解决方案的分步说明。</span><span class="sxs-lookup"><span data-stu-id="34a06-127">Provides step-by-step instructions for testing the solution.</span></span>|  

### <a name="to-create-a-biztalk-project-with-a-schema-and-an-orchestration"></a><span data-ttu-id="34a06-128">创建具有架构和业务流程的 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="34a06-128">To create a BizTalk project with a schema and an orchestration</span></span>  

1. <span data-ttu-id="34a06-129">启动**Microsoft Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="34a06-129">Start **Microsoft Visual Studio**.</span></span>  

2. <span data-ttu-id="34a06-130">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="34a06-130">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  

3. <span data-ttu-id="34a06-131">在中**新的项目**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="34a06-131">In the **New Project** dialog box, do the following:</span></span>  


   |             <span data-ttu-id="34a06-132">使用此选项</span><span class="sxs-lookup"><span data-stu-id="34a06-132">Use this</span></span>              |                             <span data-ttu-id="34a06-133">执行的操作</span><span class="sxs-lookup"><span data-stu-id="34a06-133">To do this</span></span>                              |
   |-----------------------------------|---------------------------------------------------------------------|
   |         <span data-ttu-id="34a06-134">**项目类型**</span><span class="sxs-lookup"><span data-stu-id="34a06-134">**Project types**</span></span>         |                     <span data-ttu-id="34a06-135">单击**BizTalk 项目**。</span><span class="sxs-lookup"><span data-stu-id="34a06-135">Click **BizTalk Projects**.</span></span>                     |
   |           <span data-ttu-id="34a06-136">**模板**</span><span class="sxs-lookup"><span data-stu-id="34a06-136">**Templates**</span></span>           |               <span data-ttu-id="34a06-137">单击**为空的 BizTalk Server 项目**。</span><span class="sxs-lookup"><span data-stu-id="34a06-137">Click **Empty BizTalk Server Project**.</span></span>               |
   |             <span data-ttu-id="34a06-138">**名称**</span><span class="sxs-lookup"><span data-stu-id="34a06-138">**Name**</span></span>              |                         <span data-ttu-id="34a06-139">类型**RuleTest**。</span><span class="sxs-lookup"><span data-stu-id="34a06-139">Type **RuleTest**.</span></span>                          |
   |           <span data-ttu-id="34a06-140">**位置**</span><span class="sxs-lookup"><span data-stu-id="34a06-140">**Location**</span></span>            |                  <span data-ttu-id="34a06-141">指定**C:\BRE-Walkthroughs**。</span><span class="sxs-lookup"><span data-stu-id="34a06-141">Specify **C:\BRE-Walkthroughs**.</span></span>                   |
   |         <span data-ttu-id="34a06-142">**解决方案名称**</span><span class="sxs-lookup"><span data-stu-id="34a06-142">**Solution Name**</span></span>         |                        <span data-ttu-id="34a06-143">类型**RuleTestSol**。</span><span class="sxs-lookup"><span data-stu-id="34a06-143">Type **RuleTestSol**.</span></span>                        |
   | <span data-ttu-id="34a06-144">**创建解决方案的目录**</span><span class="sxs-lookup"><span data-stu-id="34a06-144">**Create directory for solution**</span></span> | <span data-ttu-id="34a06-145">选中此复选框以便为解决方案文件创建目录。</span><span class="sxs-lookup"><span data-stu-id="34a06-145">Select this check box to create a directory for the solution files.</span></span> |


4. <span data-ttu-id="34a06-146">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="34a06-146">Click **OK**.</span></span> <span data-ttu-id="34a06-147">**RuleTest**项目应该显示在解决方案资源管理器。</span><span class="sxs-lookup"><span data-stu-id="34a06-147">The **RuleTest** project should appear in Solution Explorer.</span></span> <span data-ttu-id="34a06-148">如果看不到解决方案资源管理器，请单击**解决方案资源管理器**上**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="34a06-148">If you do not see Solution Explorer, click **Solution Explorer** on the **View** menu.</span></span>  

5. <span data-ttu-id="34a06-149">在解决方案资源管理器中右键单击**RuleTest**，依次指向**添加**，然后单击**现有项**。</span><span class="sxs-lookup"><span data-stu-id="34a06-149">In Solution Explorer, right-click **RuleTest**, point to **Add**, and then click **Existing Item**.</span></span>  

6. <span data-ttu-id="34a06-150">浏览并添加**PO.xsd**中创建的架构文件[演练： 创建简单业务策略](../core/walkthrough-creating-a-simple-business-policy.md)演练。</span><span class="sxs-lookup"><span data-stu-id="34a06-150">Browse and add the **PO.xsd** schema file you created in the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough.</span></span> <span data-ttu-id="34a06-151">Visual Studio，可以一份**PO.xsd**文件，并将其添加到项目。</span><span class="sxs-lookup"><span data-stu-id="34a06-151">Visual Studio makes a copy of the **PO.xsd** file and adds it to the project.</span></span>  

7. <span data-ttu-id="34a06-152">在解决方案资源管理器中右键单击**RuleTest**，依次指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="34a06-152">In Solution Explorer, right-click **RuleTest**, point to **Add**, and then click **New Item**.</span></span>  

8. <span data-ttu-id="34a06-153">在中**添加新项**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="34a06-153">In the **Add New Item** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="34a06-154">使用此选项</span><span class="sxs-lookup"><span data-stu-id="34a06-154">Use this</span></span>    |            <span data-ttu-id="34a06-155">执行的操作</span><span class="sxs-lookup"><span data-stu-id="34a06-155">To do this</span></span>            |
   |----------------|----------------------------------|
   | <span data-ttu-id="34a06-156">**类别**</span><span class="sxs-lookup"><span data-stu-id="34a06-156">**Categories**</span></span> |  <span data-ttu-id="34a06-157">单击**业务流程文件**。</span><span class="sxs-lookup"><span data-stu-id="34a06-157">Click **Orchestration Files**.</span></span>  |
   | <span data-ttu-id="34a06-158">**模板**</span><span class="sxs-lookup"><span data-stu-id="34a06-158">**Templates**</span></span>  | <span data-ttu-id="34a06-159">单击**BizTalk 业务流程**。</span><span class="sxs-lookup"><span data-stu-id="34a06-159">Click **BizTalk Orchestration**.</span></span> |
   |    <span data-ttu-id="34a06-160">**名称**</span><span class="sxs-lookup"><span data-stu-id="34a06-160">**Name**</span></span>    |      <span data-ttu-id="34a06-161">类型**RuleTest.odx**。</span><span class="sxs-lookup"><span data-stu-id="34a06-161">Type **RuleTest.odx**.</span></span>      |


9. <span data-ttu-id="34a06-162">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="34a06-162">Click **Add**.</span></span>  

10. <span data-ttu-id="34a06-163">右键单击**从工具箱中删除形状**，依次指向**插入形状**，然后单击**接收**。</span><span class="sxs-lookup"><span data-stu-id="34a06-163">Right-click **Drop a shape from the toolbox here**, point to **Insert Shape**, and then click **Receive**.</span></span>  

11. <span data-ttu-id="34a06-164">在属性窗口中，将名称更改**接收**形状变为**ReceivePO**，并将值设置**激活**属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="34a06-164">In the Properties window, change the name of the **Receive** shape to **ReceivePO**, and set the value of the **Activate** property to `true`.</span></span>  

12. <span data-ttu-id="34a06-165">在工具箱中，在**BizTalk 业务流程**选项卡上，拖动**调用规则**形状下方的连接线**接收**形状。</span><span class="sxs-lookup"><span data-stu-id="34a06-165">In the Toolbox, on the **BizTalk Orchestrations** tab, drag the **Call Rules** shape onto a connecting line below the **Receive** shape.</span></span>  

13. <span data-ttu-id="34a06-166">在属性窗口中，将名称更改**调用规则**形状变为**CallProcessPOPolicy**。</span><span class="sxs-lookup"><span data-stu-id="34a06-166">In the Properties window, change the name of the **Call Rules** shape to **CallProcessPOPolicy**.</span></span>  

14. <span data-ttu-id="34a06-167">下单击鼠标右键**调用规则**形状中，依次指向**插入形状**，然后单击**发送**。</span><span class="sxs-lookup"><span data-stu-id="34a06-167">Right-click below the **Call Rules** shape, point to **Insert Shape**, and then click **Send**.</span></span>  

15. <span data-ttu-id="34a06-168">在属性窗口中，将名称更改**发送**形状变为**SendPO**。</span><span class="sxs-lookup"><span data-stu-id="34a06-168">In the Properties window, change the name of the **Send** shape to **SendPO**.</span></span> <span data-ttu-id="34a06-169">业务流程如下图所示。</span><span class="sxs-lookup"><span data-stu-id="34a06-169">The orchestration should look like the following figure.</span></span>  

     <span data-ttu-id="34a06-170">![BRE&#45;演练&#45;UnconfiguredOrch](../core/media/1f3502ac-82a9-40bf-ae31-6e8356a283e2.gif "1f3502ac-82a9-40bf-ae31-6e8356a283e2")</span><span class="sxs-lookup"><span data-stu-id="34a06-170">![BRE&#45;Walkthrough&#45;UnconfiguredOrch](../core/media/1f3502ac-82a9-40bf-ae31-6e8356a283e2.gif "1f3502ac-82a9-40bf-ae31-6e8356a283e2")</span></span>  

### <a name="to-create-message-variables"></a><span data-ttu-id="34a06-171">创建消息变量</span><span class="sxs-lookup"><span data-stu-id="34a06-171">To create message variables</span></span>  

1.  <span data-ttu-id="34a06-172">在业务流程视图窗口中，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="34a06-172">In the Orchestration View window, right-click **Messages**, and then click **New Message**.</span></span> <span data-ttu-id="34a06-173">如果看不到业务流程视图窗口，请单击**视图**菜单，依次指向**其他 Windows**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="34a06-173">If you do not see the Orchestration View window, click the **View** menu, point to **Other Windows**, and then click **Orchestration View**.</span></span> <span data-ttu-id="34a06-174">通常，“业务流程视图”窗口显示在“解决方案资源管理器”选项卡的旁边。默认情况下，命名为新的消息**Message_1**。</span><span class="sxs-lookup"><span data-stu-id="34a06-174">Typically, the Orchestration View window is on the tab next to the Solution Explorer tab. By default, the new message is named **Message_1**.</span></span>  

     <span data-ttu-id="34a06-175">![BRE&#45;演练&#45;OrchViewNewMsg](../core/media/a0b7fee3-af90-4c01-9464-146f0ca449e5.gif "a0b7fee3-af90-4c01-9464-146f0ca449e5")</span><span class="sxs-lookup"><span data-stu-id="34a06-175">![BRE&#45;Walkthrough&#45;OrchViewNewMsg](../core/media/a0b7fee3-af90-4c01-9464-146f0ca449e5.gif "a0b7fee3-af90-4c01-9464-146f0ca449e5")</span></span>  

2.  <span data-ttu-id="34a06-176">在业务流程视图窗口中，单击**Message_1**。</span><span class="sxs-lookup"><span data-stu-id="34a06-176">In the Orchestration View window, click **Message_1**.</span></span>  

3.  <span data-ttu-id="34a06-177">在“属性”窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="34a06-177">In the Properties window, do the following:</span></span>  

    |<span data-ttu-id="34a06-178">使用此选项</span><span class="sxs-lookup"><span data-stu-id="34a06-178">Use this</span></span>|<span data-ttu-id="34a06-179">执行的操作</span><span class="sxs-lookup"><span data-stu-id="34a06-179">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="34a06-180">**Identifier**</span><span class="sxs-lookup"><span data-stu-id="34a06-180">**Identifier**</span></span>|<span data-ttu-id="34a06-181">类型**POInst**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="34a06-181">Type **POInst**, and then press ENTER.</span></span>|  
    |<span data-ttu-id="34a06-182">**消息类型**</span><span class="sxs-lookup"><span data-stu-id="34a06-182">**Message Type**</span></span>|<span data-ttu-id="34a06-183">从下拉列表中，展开**架构**，然后选择**RuleTest.PO**。</span><span class="sxs-lookup"><span data-stu-id="34a06-183">From the drop-down list, expand **Schemas**, and then select **RuleTest.PO**.</span></span>|  

     <span data-ttu-id="34a06-184">![BRE&#45;Walkthrough&#45;MsgProps](../core/media/c82cfb67-63f6-4133-95bf-daadac0e213a.gif "c82cfb67-63f6-4133-95bf-daadac0e213a")</span><span class="sxs-lookup"><span data-stu-id="34a06-184">![BRE&#45;Walkthrough&#45;MsgProps](../core/media/c82cfb67-63f6-4133-95bf-daadac0e213a.gif "c82cfb67-63f6-4133-95bf-daadac0e213a")</span></span>  

### <a name="to-configure-shapes"></a><span data-ttu-id="34a06-185">配置形状</span><span class="sxs-lookup"><span data-stu-id="34a06-185">To configure shapes</span></span>  

1. <span data-ttu-id="34a06-186">选择**接收**形状在业务流程设计器中的。</span><span class="sxs-lookup"><span data-stu-id="34a06-186">Select the **Receive** shape in Orchestration Designer.</span></span>  

2. <span data-ttu-id="34a06-187">在属性窗口中，选择**POInst**有关**消息**属性。</span><span class="sxs-lookup"><span data-stu-id="34a06-187">In the Properties window, select **POInst** for the **Message** property.</span></span>  

3. <span data-ttu-id="34a06-188">双击**调用规则**形状在业务流程设计器中的。</span><span class="sxs-lookup"><span data-stu-id="34a06-188">Double-click the **Call Rules** shape in Orchestration Designer.</span></span>  

4. <span data-ttu-id="34a06-189">在中**调用规则策略配置**对话框中，选择**ProcessPurchaseOrder**策略。</span><span class="sxs-lookup"><span data-stu-id="34a06-189">In the **Call Rules policy configuration** dialog box, select **ProcessPurchaseOrder** for the policy.</span></span>  

5. <span data-ttu-id="34a06-190">旁边**\\**<em>下文 \* \* 参数名称</em><em>，然后选择 \**POInst</em>* 作为策略的参数。</span><span class="sxs-lookup"><span data-stu-id="34a06-190">Click next to **\\**<em>, below \*\*Parameter Name</em><em>, and select \**POInst</em>* as a parameter to the policy.</span></span>  

    <span data-ttu-id="34a06-191">![BRE&#45;演练&#45;ConfigureCallRules](../core/media/0e7dab04-41db-433b-bbf5-b13901033b41.gif "0e7dab04-41db-433b-bbf5-b13901033b41")</span><span class="sxs-lookup"><span data-stu-id="34a06-191">![BRE&#45;Walkthrough&#45;ConfigureCallRules](../core/media/0e7dab04-41db-433b-bbf5-b13901033b41.gif "0e7dab04-41db-433b-bbf5-b13901033b41")</span></span>  

6. <span data-ttu-id="34a06-192">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="34a06-192">Click **OK**.</span></span>  

7. <span data-ttu-id="34a06-193">选择**发送**形状在业务流程中的。</span><span class="sxs-lookup"><span data-stu-id="34a06-193">Select the **Send** shape in the orchestration.</span></span>  

8. <span data-ttu-id="34a06-194">在属性窗口中设置的值**消息类型**属性设置为**POInst**。</span><span class="sxs-lookup"><span data-stu-id="34a06-194">In the Properties window, set the value of the **Message Type** property to **POInst**.</span></span>  

### <a name="to-create-ports"></a><span data-ttu-id="34a06-195">若要创建端口</span><span class="sxs-lookup"><span data-stu-id="34a06-195">To create ports</span></span>  

1.  <span data-ttu-id="34a06-196">创建两个文件夹**输入**并**输出**，C:\BRE-Walkthroughs\RuleTestSol 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="34a06-196">Create two folders, **Input** and **Output**, in the C:\BRE-Walkthroughs\RuleTestSol folder.</span></span>  

2.  <span data-ttu-id="34a06-197">右键单击该业务流程的左侧的端口图面，然后单击**新建配置的端口**。</span><span class="sxs-lookup"><span data-stu-id="34a06-197">Right-click the left port surface of the orchestration, and then click **New Configured Port**.</span></span>  

3.  <span data-ttu-id="34a06-198">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="34a06-198">Click **Next**.</span></span> <span data-ttu-id="34a06-199">类型**ReceivePOPrt**为端口名称。</span><span class="sxs-lookup"><span data-stu-id="34a06-199">Type **ReceivePOPrt** for the port name.</span></span>  

4.  <span data-ttu-id="34a06-200">单击**下一步**两次。</span><span class="sxs-lookup"><span data-stu-id="34a06-200">Click **Next** twice.</span></span>  

5.  <span data-ttu-id="34a06-201">选择**立即指定**有关**端口绑定**。</span><span class="sxs-lookup"><span data-stu-id="34a06-201">Select **Specify Now** for the **port binding**.</span></span>  

6.  <span data-ttu-id="34a06-202">指定**文件**有关**传输**，然后键入输入目录的名称**C:\BRE-Walkthroughs\RuleTestSol\Input\\\*.xml**文件掩码以及 (**\*.xml**) uri。</span><span class="sxs-lookup"><span data-stu-id="34a06-202">Specify **FILE** for the **transport**, and type the name of the input directory as **C:\BRE-Walkthroughs\RuleTestSol\Input\\\*.xml** along with the file mask (**\*.xml**) for the URI.</span></span>  

7.  <span data-ttu-id="34a06-203">单击“下一步” ，然后单击“完成” 。</span><span class="sxs-lookup"><span data-stu-id="34a06-203">Click **Next**, and then click **Finish**.</span></span>  

8.  <span data-ttu-id="34a06-204">右键单击该业务流程的右侧端口图面，然后单击**新建配置端口**。</span><span class="sxs-lookup"><span data-stu-id="34a06-204">Right-click the right port surface of the orchestration, and then click **New Configuration Port**.</span></span>  

9. <span data-ttu-id="34a06-205">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="34a06-205">Click **Next**.</span></span> <span data-ttu-id="34a06-206">类型**SendPOPort**为端口名称。</span><span class="sxs-lookup"><span data-stu-id="34a06-206">Type **SendPOPort** for the port name.</span></span>  

10. <span data-ttu-id="34a06-207">单击**下一步**两次。</span><span class="sxs-lookup"><span data-stu-id="34a06-207">Click **Next** twice.</span></span>  

11. <span data-ttu-id="34a06-208">更改**端口通信方向**到**我始终在发送消息此端口上**。</span><span class="sxs-lookup"><span data-stu-id="34a06-208">Change the **Port direction of communication** to **I'll always be sending messages on this port**.</span></span>  

12. <span data-ttu-id="34a06-209">选择**立即指定**有关**端口绑定**。</span><span class="sxs-lookup"><span data-stu-id="34a06-209">Select **Specify Now** for the **port binding**.</span></span>  

13. <span data-ttu-id="34a06-210">指定**文件**有关**传输**，并键入输出目录的名称**C:\BRE-Walkthroughs\RuleTestSol\Output**，和 %MessageID%.xml 与输出文件名称。</span><span class="sxs-lookup"><span data-stu-id="34a06-210">Specify **FILE** for the **transport**, and type the name of the output directory as **C:\BRE-Walkthroughs\RuleTestSol\Output**,and %MessageID%.xml as the output file name.</span></span>  

14. <span data-ttu-id="34a06-211">单击“下一步” ，然后单击“完成” 。</span><span class="sxs-lookup"><span data-stu-id="34a06-211">Click **Next**, and then click **Finish**.</span></span>  

### <a name="to-connect-ports-with-the-shapes"></a><span data-ttu-id="34a06-212">将端口与形状连接</span><span class="sxs-lookup"><span data-stu-id="34a06-212">To connect ports with the shapes</span></span>  

1.  <span data-ttu-id="34a06-213">连接**ReceivePOPrt**到端口**ReceivePO**形状。</span><span class="sxs-lookup"><span data-stu-id="34a06-213">Connect the **ReceivePOPrt** port to the **ReceivePO** shape.</span></span> <span data-ttu-id="34a06-214">（将端口图面上 ReceivePOPrt 端口右侧的箭头拖到 ReceivePO 形状上的框。）</span><span class="sxs-lookup"><span data-stu-id="34a06-214">(Drag the arrow to the right of ReceivePOPrt port on the port surface to the box on the ReceivePO shape.)</span></span>  

     <span data-ttu-id="34a06-215">![BRE&#45;Walkthrough&#45;ConnectRP](../core/media/75bdf79e-ca98-43bb-8ff6-5f46005a6490.gif "75bdf79e-ca98-43bb-8ff6-5f46005a6490")</span><span class="sxs-lookup"><span data-stu-id="34a06-215">![BRE&#45;Walkthrough&#45;ConnectRP](../core/media/75bdf79e-ca98-43bb-8ff6-5f46005a6490.gif "75bdf79e-ca98-43bb-8ff6-5f46005a6490")</span></span>  

2.  <span data-ttu-id="34a06-216">连接**SendPO**形状变为**SendPOPrt**端口。</span><span class="sxs-lookup"><span data-stu-id="34a06-216">Connect the **SendPO** shape to the **SendPOPrt** port.</span></span>  

     <span data-ttu-id="34a06-217">![BRE&#45;Walkthrough&#45;ConnectSP](../core/media/7513f52b-2782-4357-b8eb-1874dec33869.gif "7513f52b-2782-4357-b8eb-1874dec33869")</span><span class="sxs-lookup"><span data-stu-id="34a06-217">![BRE&#45;Walkthrough&#45;ConnectSP](../core/media/7513f52b-2782-4357-b8eb-1874dec33869.gif "7513f52b-2782-4357-b8eb-1874dec33869")</span></span>  

### <a name="to-build-and-deploy-the-solution"></a><span data-ttu-id="34a06-218">若要生成并部署解决方案</span><span class="sxs-lookup"><span data-stu-id="34a06-218">To build and deploy the solution</span></span>  

1. <span data-ttu-id="34a06-219">启动**Microsoft Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="34a06-219">Start **Microsoft Visual Studio**.</span></span>  

2. <span data-ttu-id="34a06-220">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器中右键单击**RuleTest**项目，然后依次**属性**。</span><span class="sxs-lookup"><span data-stu-id="34a06-220">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], in Solution Explorer, right-click the **RuleTest** project, and then click **Properties**.</span></span>  

3. <span data-ttu-id="34a06-221">在项目设计器 （在中心窗格） 中，单击**签名**。</span><span class="sxs-lookup"><span data-stu-id="34a06-221">In Project Designer (in the center pane), click **Signing**.</span></span>  

4. <span data-ttu-id="34a06-222">在签名选项卡上，选中**为程序集签名**的复选框。在下拉列表**选择强名称密钥文件**，单击**新建**;在中**密钥文件名称**字段中，输入规则测试;在中**密码**字段 （可选）、 设置密码，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="34a06-222">In Signing tab, Check **Sign the assembly** checkbox; In the dropdown list **Choose a strong name key file**, click **New**; In the **Key File name** field, enter Rule Test; In the **Password** field (Optional),  set Password, and then click **OK**.</span></span>  

5. <span data-ttu-id="34a06-223">在项目设计器中，单击**部署**切换到部署选项卡。</span><span class="sxs-lookup"><span data-stu-id="34a06-223">In Project Designer, click **Deployment** to switch to the Deployment tab.</span></span>  

6. <span data-ttu-id="34a06-224">指定**RuleTestApp**作为应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="34a06-224">Specify **RuleTestApp** as the application name.</span></span>  

    <span data-ttu-id="34a06-225">![BRE&#45;演练&#45;RuleTestApp](../core/media/b153e5b0-ca46-4d27-bfa1-9ad4e58e9787.gif "b153e5b0-ca46-4d27-bfa1-9ad4e58e9787")</span><span class="sxs-lookup"><span data-stu-id="34a06-225">![BRE&#45;Walkthrough&#45;RuleTestApp](../core/media/b153e5b0-ca46-4d27-bfa1-9ad4e58e9787.gif "b153e5b0-ca46-4d27-bfa1-9ad4e58e9787")</span></span>  

7. <span data-ttu-id="34a06-226">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="34a06-226">Click **OK**.</span></span>  

8. <span data-ttu-id="34a06-227">右键单击**RuleTest**项目，并单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="34a06-227">Right-click the **RuleTest** project, and then click **Build**.</span></span>  

9. <span data-ttu-id="34a06-228">右键单击**RuleTest**项目，并单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="34a06-228">Right-click the **RuleTest** project, and then click **Deploy**.</span></span>  

### <a name="to-test-the-solution"></a><span data-ttu-id="34a06-229">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="34a06-229">To test the solution</span></span>  

1. <span data-ttu-id="34a06-230">在业务规则编辑器中，展开**策略**，展开**ProcessPurchaseOrder**，右键单击**版本 1.0**，然后单击**发布**.</span><span class="sxs-lookup"><span data-stu-id="34a06-230">In Business Rule Composer, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.0**, and then click **Publish**.</span></span>  

2. <span data-ttu-id="34a06-231">右键单击**版本 1.0-已发布**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="34a06-231">Right-click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  

3. <span data-ttu-id="34a06-232">在中**启动**菜单中，打开**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="34a06-232">In the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="34a06-233">如果 BizTalk Server 管理控制台已经打开，则按下 F5 键以便刷新它。</span><span class="sxs-lookup"><span data-stu-id="34a06-233">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  

4. <span data-ttu-id="34a06-234">展开**控制台根节点**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="34a06-234">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and then expand **Applications**.</span></span>  

5. <span data-ttu-id="34a06-235">右键单击**RuleTestApp**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="34a06-235">Right-click **RuleTestApp**, and then click **Configure**.</span></span>  

6. <span data-ttu-id="34a06-236">单击**Orchestration_1**，并指定**BizTalkServerApplication**作为主机。</span><span class="sxs-lookup"><span data-stu-id="34a06-236">Click **Orchestration_1**, and specify **BizTalkServerApplication** as the host.</span></span>  

    <span data-ttu-id="34a06-237">![BRE&#45;演练&#45;AppHost](../core/media/ba348a98-661f-4e71-8b9b-b8c5fadf035a.gif "ba348a98-661f-4e71-8b9b-b8c5fadf035a")</span><span class="sxs-lookup"><span data-stu-id="34a06-237">![BRE&#45;Walkthrough&#45;AppHost](../core/media/ba348a98-661f-4e71-8b9b-b8c5fadf035a.gif "ba348a98-661f-4e71-8b9b-b8c5fadf035a")</span></span>  

7. <span data-ttu-id="34a06-238">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="34a06-238">Click **OK**.</span></span>  

8. <span data-ttu-id="34a06-239">右键单击**RuleTestApp**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="34a06-239">Right-click **RuleTestApp**, and then click **Start**.</span></span>  

9. <span data-ttu-id="34a06-240">在中**启动 'RuleTestApp' 应用程序**对话框中，单击**启动**，，然后等到已成功启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="34a06-240">In the **Start 'RuleTestApp' Application** dialog box, click **Start**, and then wait until the application is started successfully.</span></span>  

10. <span data-ttu-id="34a06-241">打开**SamplePO.xml**并**SamplePO2.xml**在记事本中，将的值更改**状态**字段**XYZ**。</span><span class="sxs-lookup"><span data-stu-id="34a06-241">Open **SamplePO.xml** and **SamplePO2.xml** in Notepad and change the value of the **Status** field to **XYZ**.</span></span>  

11. <span data-ttu-id="34a06-242">复制**SamplePO.xml**文件从 C:\BRE-Walkthroughs 目录的 C:\BRE-Walkthroughs\RuleTestSol\Input 目录到业务流程。</span><span class="sxs-lookup"><span data-stu-id="34a06-242">Copy the **SamplePO.xml** file from the C:\BRE-Walkthroughs directory to the C:\BRE-Walkthroughs\RuleTestSol\Input directory for the orchestration.</span></span>  

12. <span data-ttu-id="34a06-243">你应该在业务流程的 C:\BRE-Walkthroughs\RuleTestSol\Output 目录中看到输出文件。</span><span class="sxs-lookup"><span data-stu-id="34a06-243">You should see an output file in the C:\BRE-Walkthroughs\RuleTestSol\Output directory for the orchestration.</span></span> <span data-ttu-id="34a06-244">打开输出 XML 文件，可以看到的值**状态**字段设置为**Approved**。</span><span class="sxs-lookup"><span data-stu-id="34a06-244">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  

13. <span data-ttu-id="34a06-245">重复步骤 11 和 12 个**SamplePO2.xml**，您会发现的值**状态**输出文档中的字段是与输入文档中的相同 (**xyz**)。</span><span class="sxs-lookup"><span data-stu-id="34a06-245">Repeat steps 11 and 12 with **SamplePO2.xml**, and notice that the value of the **Status** field in the output document is the same as in the input document (**xyz**).</span></span>  

## <a name="comments"></a><span data-ttu-id="34a06-246">注释</span><span class="sxs-lookup"><span data-stu-id="34a06-246">Comments</span></span>  

-   <span data-ttu-id="34a06-247">在此业务流程中，为了向业务流程添加形状，你没有使用工具栏中的形状。</span><span class="sxs-lookup"><span data-stu-id="34a06-247">In this walkthrough, to add the shapes to the orchestration, you did not use the shapes from the Toolbox.</span></span> <span data-ttu-id="34a06-248">相反，你单击了鼠标右键，并选择了要插入的形状。</span><span class="sxs-lookup"><span data-stu-id="34a06-248">Instead, you clicked the right mouse button and selected the shape that you wanted to insert.</span></span>  

-   <span data-ttu-id="34a06-249">配置**调用规则**形状的外观保存的最新版本时确定使用的类型。</span><span class="sxs-lookup"><span data-stu-id="34a06-249">The configuration for the **Call Rules** shape looks at the latest saved version when determining the types used.</span></span> <span data-ttu-id="34a06-250">运行时，将使用部署的最新版本。</span><span class="sxs-lookup"><span data-stu-id="34a06-250">At run time, the latest deployed version will be used.</span></span>  

-   <span data-ttu-id="34a06-251">如果你打算使用策略版本，而不是最新的已部署版本，则应使用**表达式**形状，并调用规则引擎以编程方式来执行该特定版本的策略。</span><span class="sxs-lookup"><span data-stu-id="34a06-251">If you plan to use a policy version other than the latest deployed version, you should use an **Expression** shape, and invoke the rule engine programmatically to execute the policy of that specific version.</span></span> <span data-ttu-id="34a06-252">有关详细信息，请参阅[如何执行策略](../core/how-to-execute-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="34a06-252">For more information, see [How to Execute Policies](../core/how-to-execute-policies.md).</span></span>  

-   <span data-ttu-id="34a06-253">**调用规则**形状重新构造消息，如同使用**构造消息**形状，因而可能导致消息丢失的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="34a06-253">The **Call Rules** shape reconstructs the message, as if using a **Construct Message** shape, which in turn may cause context properties of the message to be lost.</span></span>  

-   <span data-ttu-id="34a06-254">策略在发布之后不能修改。</span><span class="sxs-lookup"><span data-stu-id="34a06-254">A policy cannot be modified after it is published.</span></span>  

-   <span data-ttu-id="34a06-255">客户端应用程序只能访问已部署的策略。</span><span class="sxs-lookup"><span data-stu-id="34a06-255">The client applications can access only the deployed policies.</span></span> <span data-ttu-id="34a06-256">如果客户端应用程序调用未部署的策略，规则引擎将生成**RuleEngineDeploymentNotDeployedException**异常。</span><span class="sxs-lookup"><span data-stu-id="34a06-256">If a client application invokes a policy that is not deployed, the rule engine generates a **RuleEngineDeploymentNotDeployedException** exception.</span></span> <span data-ttu-id="34a06-257">在应用程序事件日志中可看到详细的错误消息。</span><span class="sxs-lookup"><span data-stu-id="34a06-257">You can see the detailed error message in the application event log.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="34a06-258">后续步骤</span><span class="sxs-lookup"><span data-stu-id="34a06-258">Next Steps</span></span>  
 <span data-ttu-id="34a06-259">现在，已完成本演练中，执行[演练： 创建和使用策略中的某一词汇](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md)演练中，为您提供用于创建词汇和使用词汇的分步说明**ProcessPurchaseOrder**策略。</span><span class="sxs-lookup"><span data-stu-id="34a06-259">Now that you have completed this walkthrough, perform the [Walkthrough: Creating and Using a Vocabulary in the Policy](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md) walkthrough, which gives you step-by-step instructions for creating a vocabulary and using the vocabulary in the **ProcessPurchaseOrder** policy.</span></span>  

## <a name="see-also"></a><span data-ttu-id="34a06-260">请参阅</span><span class="sxs-lookup"><span data-stu-id="34a06-260">See Also</span></span>  
 <span data-ttu-id="34a06-261">[条件评估和操作执行](../core/condition-evaluation-and-action-execution.md) </span><span class="sxs-lookup"><span data-stu-id="34a06-261">[Condition Evaluation and Action Execution](../core/condition-evaluation-and-action-execution.md) </span></span>  
 <span data-ttu-id="34a06-262">[议程和优先级](../core/agenda-and-priority.md) </span><span class="sxs-lookup"><span data-stu-id="34a06-262">[Agenda and Priority](../core/agenda-and-priority.md) </span></span>  
 [<span data-ttu-id="34a06-263">在业务流程中调用业务规则</span><span class="sxs-lookup"><span data-stu-id="34a06-263">Invoking Business Rules in Orchestrations</span></span>](../core/invoking-business-rules-in-orchestrations.md)