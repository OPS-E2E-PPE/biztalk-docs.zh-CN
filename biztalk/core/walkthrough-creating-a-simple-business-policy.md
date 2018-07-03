---
title: 演练： 创建简单业务策略 |Microsoft Docs
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 02d35735-dce2-4ee2-965e-dae307a125b0
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cecf7078592d322f9cc9777aeb530759c5ecf4c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023857"
---
# <a name="walkthrough-creating-a-simple-business-policy"></a><span data-ttu-id="68288-102">演练： 创建简单业务策略</span><span class="sxs-lookup"><span data-stu-id="68288-102">Walkthrough: Creating a Simple Business Policy</span></span>
<span data-ttu-id="68288-103">本演练提供使用业务规则编辑器创建一个名为的简单业务策略的分步过程**ProcessPurchaseOrder**包含一个名为规则**ApprovedRule**。</span><span class="sxs-lookup"><span data-stu-id="68288-103">This walkthrough provides step-by-step procedures for using the Business Rule Composer to create a simple business policy named **ProcessPurchaseOrder** containing a rule named **ApprovedRule**.</span></span> <span data-ttu-id="68288-104">**ApprovedRule**规则需要用户以提交 XML 文档作为事实，并设置的值**状态**到文档中字段**已批准**如果的值**Quantity**字段是否小于或等于**500**。</span><span class="sxs-lookup"><span data-stu-id="68288-104">The **ApprovedRule** rule expects the user to submit an XML document as a fact, and sets the value of the **Status** field in the document to **Approved** if the value of the **Quantity** field is less than or equal to **500**.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="68288-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="68288-105">Prerequisites</span></span>  
 <span data-ttu-id="68288-106">您必须熟悉要执行本演练的业务规则框架的基础知识。</span><span class="sxs-lookup"><span data-stu-id="68288-106">You must be familiar with the basics of the Business Rules Framework to perform this walkthrough.</span></span> <span data-ttu-id="68288-107">如果您不熟悉业务规则框架，我们建议你阅读在业务规则框架的体系结构概述[业务规则引擎](../core/business-rules-engine.md)执行本演练之前。</span><span class="sxs-lookup"><span data-stu-id="68288-107">If you are new to the Business Rules Framework, we recommend that you read the architecture overview of the Business Rules Framework at [Business Rules Engine](../core/business-rules-engine.md) before performing this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="68288-108">本演练概述</span><span class="sxs-lookup"><span data-stu-id="68288-108">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="68288-109">本概览包含两个过程，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="68288-109">This walkthrough contains two procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="68288-110">过程标题</span><span class="sxs-lookup"><span data-stu-id="68288-110">Procedure title</span></span>|<span data-ttu-id="68288-111">过程说明</span><span class="sxs-lookup"><span data-stu-id="68288-111">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="68288-112">若要创建采购订单架构文件</span><span class="sxs-lookup"><span data-stu-id="68288-112">To create the PO schema file</span></span>|<span data-ttu-id="68288-113">提供了创建文档的架构的分步说明**ProcessPurchaseOrder**策略使用。</span><span class="sxs-lookup"><span data-stu-id="68288-113">Provides step-by-step instructions for creating the schema for the document that the **ProcessPurchaseOrder** policy uses.</span></span>|  
|<span data-ttu-id="68288-114">若要创建 ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="68288-114">To create the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="68288-115">提供创建的分步说明**ProcessPurchaseOrder**策略通过使用业务规则编辑器。</span><span class="sxs-lookup"><span data-stu-id="68288-115">Provides step-by-step instructions for creating the **ProcessPurchaseOrder** policy by using the Business Rule Composer.</span></span>|  
  
### <a name="to-create-the-po-schema-file"></a><span data-ttu-id="68288-116">若要创建采购订单架构文件</span><span class="sxs-lookup"><span data-stu-id="68288-116">To create the PO schema file</span></span>  
  
1.  <span data-ttu-id="68288-117">上**启动**菜单中，打开**记事本**。</span><span class="sxs-lookup"><span data-stu-id="68288-117">On the **Start** menu, open **Notepad**.</span></span>  
  
2.  <span data-ttu-id="68288-118">在 **“文件”** 菜单上，指向 **“新建”**，然后单击 **“文件”**。</span><span class="sxs-lookup"><span data-stu-id="68288-118">On the **File** menu, point to **New**, and then click **File**.</span></span>  
  
3.  <span data-ttu-id="68288-119">将以下 XML 文本复制到编辑器：</span><span class="sxs-lookup"><span data-stu-id="68288-119">Copy the following XML text to the editor:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-16"?>  
    <xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="http://EAISolution.PurchaseOrder" targetNamespace="http://EAISolution.PurchaseOrder" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
      <xs:element name="PurchaseOrder">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="Header">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="ReqID" type="xs:string" />  
                  <xs:element name="Date" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
            <xs:element name="Item">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="Description" type="xs:string" />  
                  <xs:element name="Quantity" type="xs:int" />  
                  <xs:element name="UnitPrice" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
            <xs:element name="Status" type="xs:string" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:schema>  
    ```  
  
4.  <span data-ttu-id="68288-120">上**文件**菜单上，单击**TextFile1.txt 保存为**。</span><span class="sxs-lookup"><span data-stu-id="68288-120">On the **File** menu, click **Save TextFile1.txt As**.</span></span>  
  
5.  <span data-ttu-id="68288-121">更改的值**另存为类型**从**文本文档 (\*.txt)** 到**的所有文件**。</span><span class="sxs-lookup"><span data-stu-id="68288-121">Change the value for **Save As type** from **Text Documents(\*.txt)** to **All Files**.</span></span>  
  
6.  <span data-ttu-id="68288-122">类型**PO.xsd**中**文件名**文字框中，将目录更改为**C:\BRE-Walkthroughs**，更改的值**编码**到**Unicode** ，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="68288-122">Type **PO.xsd** in the **File name** text box, change the directory to **C:\BRE-Walkthroughs**, change the value of **Encoding** to **Unicode** and then click **Save**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="68288-123">创建目录**BRE 演练**下**c:\\** 如果其不存在，，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="68288-123">Create the directory **BRE-Walkthroughs** under **C:\\** if it does not exist, and then click **Save**.</span></span>  
  
7.  <span data-ttu-id="68288-124">关闭记事本。</span><span class="sxs-lookup"><span data-stu-id="68288-124">Close Notepad.</span></span>  
  
### <a name="to-create-the-processpurchaseorder-business-policy"></a><span data-ttu-id="68288-125">若要创建 ProcessPurchaseOrder 业务策略</span><span class="sxs-lookup"><span data-stu-id="68288-125">To create the ProcessPurchaseOrder business policy</span></span>  
  
1. <span data-ttu-id="68288-126">上**启动**菜单中，打开**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="68288-126">On the **Start** menu, open **Business Rule Composer**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="68288-127">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="68288-127">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="68288-128">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="68288-128">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="68288-129">业务规则编辑器将显示**打开规则存储**对话框中的计算机上首次打开时。</span><span class="sxs-lookup"><span data-stu-id="68288-129">The Business Rule Composer displays the **Open Rule Store** dialog box when it is opened for the first time on a computer.</span></span> <span data-ttu-id="68288-130">如果您看到**打开规则存储**对话框中，单击**确定**后验证的 SQL server 名称和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="68288-130">If you see the **Open Rule Store** dialog box, click **OK** after verifying the SQL server name and database name.</span></span>  
  
2. <span data-ttu-id="68288-131">在策略浏览器窗口中，右键单击**策略**，然后单击**添加新策略**。</span><span class="sxs-lookup"><span data-stu-id="68288-131">In the Policy Explorer window, right-click **Policies**, and then click **Add New Policy**.</span></span>  
  
3. <span data-ttu-id="68288-132">编辑的策略，策略名称**Policy1**给**ProcessPurchaseOrder**然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="68288-132">Edit the name of the policy, **Policy1**, to **ProcessPurchaseOrder** and press ENTER.</span></span> <span data-ttu-id="68288-133">你可以在策略的名称**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="68288-133">You can also change the name of the policy in the **Properties** window.</span></span>  
  
4. <span data-ttu-id="68288-134">右键单击**版本 1.0**，然后单击**AddNewRule**。</span><span class="sxs-lookup"><span data-stu-id="68288-134">Right-click **Version 1.0**, and then click **AddNewRule**.</span></span>  
  
5. <span data-ttu-id="68288-135">编辑规则的名称**Rule1**到**ApprovalRule**然后按 ENTER<strong>。</strong></span><span class="sxs-lookup"><span data-stu-id="68288-135">Edit the name of the rule from **Rule1** to **ApprovalRule** and press ENTER<strong>.</strong></span></span> <span data-ttu-id="68288-136">你可以在规则的名称**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="68288-136">You can also change the name of the rule in the **Properties** window.</span></span>  
  
6. <span data-ttu-id="68288-137">在事实浏览器窗口中，单击**XML 架构**选项卡。</span><span class="sxs-lookup"><span data-stu-id="68288-137">In the Facts Explorer window, click the **XML Schemas** tab.</span></span>  
  
7. <span data-ttu-id="68288-138">右键单击**架构**，单击**浏览**，然后选择**PO.xsd**前面创建的文件。</span><span class="sxs-lookup"><span data-stu-id="68288-138">Right-click **Schemas**, click **Browse**, and then select the **PO.xsd** file that you created earlier.</span></span>  
  
8. <span data-ttu-id="68288-139">在属性窗口中的值更改**文档类型**属性从**PO**到**RuleTest.PO**。</span><span class="sxs-lookup"><span data-stu-id="68288-139">In the properties window, change the value of the **Document Type** property from **PO** to **RuleTest.PO**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="68288-140">您将创建一个名为的 BizTalk 项目**RuleTest**后面[演练： 从业务流程调用策略](../core/walkthrough-invoking-the-policy-from-an-orchestration.md)演练。</span><span class="sxs-lookup"><span data-stu-id="68288-140">You will be creating a BizTalk project named **RuleTest** later in the [Walkthrough: Invoking the Policy from an Orchestration](../core/walkthrough-invoking-the-policy-from-an-orchestration.md) walkthrough.</span></span> <span data-ttu-id="68288-141">中的演练中，您将添加**PO.xsd**到项目文件中，创建调用业务流程**ProcessPurchaseOrder**策略，然后测试策略。</span><span class="sxs-lookup"><span data-stu-id="68288-141">In that walkthrough, you will add the **PO.xsd** file to the project, create an orchestration that invokes the **ProcessPurchaseOrder** policy, and then test the policy.</span></span> <span data-ttu-id="68288-142">若要测试的策略与业务流程，您需要确保您更改**文档类型**属性设置为**\<项目名称\>。\<SchemaName\>**，即**RuleTest.PO**这种情况下。</span><span class="sxs-lookup"><span data-stu-id="68288-142">To test the policy from the orchestration, you need to make sure that you change the **Document Type** property to **\<Project Name\>.\<SchemaName\>**, which is **RuleTest.PO** in this case.</span></span>  
  
    <span data-ttu-id="68288-143">![BRE&#45;演练&#45;ChangeDocType](../core/media/e9a370fd-d9b2-48f0-ad0e-85a5428a9c21.gif "e9a370fd-d9b2-48f0-ad0e-85a5428a9c21")</span><span class="sxs-lookup"><span data-stu-id="68288-143">![BRE&#45;Walkthrough&#45;ChangeDocType](../core/media/e9a370fd-d9b2-48f0-ad0e-85a5428a9c21.gif "e9a370fd-d9b2-48f0-ad0e-85a5428a9c21")</span></span>  
  
9. <span data-ttu-id="68288-144">在事实浏览器窗口中，展开**PurchaseOrder**，然后展开**项**。</span><span class="sxs-lookup"><span data-stu-id="68288-144">In the Facts Explorer window, expand **PurchaseOrder**, and then expand **Item**.</span></span>  
  
10. <span data-ttu-id="68288-145">在如果窗格 （顶部） 在右侧，右击**条件**，单击**谓词**，然后单击**小于或等于**。</span><span class="sxs-lookup"><span data-stu-id="68288-145">In the IF pane (top) on the right, right-click **Conditions**, click **Predicates**, and then click **LessThanEqual**.</span></span>  
  
     <span data-ttu-id="68288-146">![业务规则编辑器&#45;小于或等于](../core/media/1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7.gif "1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7")</span><span class="sxs-lookup"><span data-stu-id="68288-146">![Business Rule Composer &#45; Less Than or Equal](../core/media/1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7.gif "1e6418a6-5e5b-4f77-8b7e-dd31d0a753e7")</span></span>  
  
11. <span data-ttu-id="68288-147">拖动**Quantity**节点从事实浏览器窗口**argument1**如果窗格中。</span><span class="sxs-lookup"><span data-stu-id="68288-147">Drag the **Quantity** node from the Facts Explorer window to **argument1** in the IF pane.</span></span>  
  
     <span data-ttu-id="68288-148">![业务规则编辑器&#45;DragQuantity](../core/media/4742eca6-4a8a-401d-8989-cab4e8025fb3.gif "4742eca6-4a8a-401d-8989-cab4e8025fb3")</span><span class="sxs-lookup"><span data-stu-id="68288-148">![Business Rule Composer &#45; DragQuantity](../core/media/4742eca6-4a8a-401d-8989-cab4e8025fb3.gif "4742eca6-4a8a-401d-8989-cab4e8025fb3")</span></span>  
  
     <span data-ttu-id="68288-149">![业务规则编辑器&#45;UseQuantity](../core/media/ee4f61b1-0f15-4329-b0b5-9badd21dcd61.gif "ee4f61b1-0f15-4329-b0b5-9badd21dcd61")</span><span class="sxs-lookup"><span data-stu-id="68288-149">![Business Rule Composer&#45;UseQuantity](../core/media/ee4f61b1-0f15-4329-b0b5-9badd21dcd61.gif "ee4f61b1-0f15-4329-b0b5-9badd21dcd61")</span></span>  
  
12. <span data-ttu-id="68288-150">在如果窗格中，单击**argument2**，类型`500`，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="68288-150">In the IF pane, click **argument2**, type `500`, and then press ENTER.</span></span>  
  
13. <span data-ttu-id="68288-151">拖动**状态**节点从事实浏览器窗口的业务规则编辑器右下侧那么窗格。</span><span class="sxs-lookup"><span data-stu-id="68288-151">Drag the **Status** node from the Facts Explorer window to the THEN pane at the bottom-right side of Business Rule Composer.</span></span>  
  
     <span data-ttu-id="68288-152">![业务规则编辑器&#45;DragStatus](../core/media/3617251a-a192-4aec-9474-81f6290c0832.gif "3617251a-a192-4aec-9474-81f6290c0832")</span><span class="sxs-lookup"><span data-stu-id="68288-152">![Business Rule Composer&#45;DragStatus](../core/media/3617251a-a192-4aec-9474-81f6290c0832.gif "3617251a-a192-4aec-9474-81f6290c0832")</span></span>  
  
14. <span data-ttu-id="68288-153">在那么窗格中，单击**\<输入值\>** ，然后键入**已批准**。</span><span class="sxs-lookup"><span data-stu-id="68288-153">In the THEN pane, click **\<Enter a value\>** and then type **Approved**.</span></span>  
  
15. <span data-ttu-id="68288-154">在策略浏览器窗口中，右键单击**版本 1.0 （未保存）**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="68288-154">In the Policy Explorer window, right-click **Version 1.0 (not saved)**, and then click **Save**.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="68288-155">注释</span><span class="sxs-lookup"><span data-stu-id="68288-155">Comments</span></span>  
  
-   <span data-ttu-id="68288-156">一个策略可拥有一个或多个规则。</span><span class="sxs-lookup"><span data-stu-id="68288-156">A policy can have one or more rules.</span></span> <span data-ttu-id="68288-157">你将添加另一个规则**DeniedRule**，在[演练： 向策略添加规则](../core/walkthrough-adding-a-rule-to-the-policy.md)演练。</span><span class="sxs-lookup"><span data-stu-id="68288-157">You will be adding another rule, **DeniedRule**, in the [Walkthrough: Adding a Rule to the Policy](../core/walkthrough-adding-a-rule-to-the-policy.md) walkthrough.</span></span>  
  
-   <span data-ttu-id="68288-158">当策略处于“已保存”状态时，您可以修改策略以添加更多规则及更改条件和操作。</span><span class="sxs-lookup"><span data-stu-id="68288-158">You can modify the policy to add more rules, change conditions, and change actions when the policy is in the Saved state.</span></span>  
  
-   <span data-ttu-id="68288-159">可以通过指定优先级的规则执行**优先级**上业务规则编辑器中的规则的属性。</span><span class="sxs-lookup"><span data-stu-id="68288-159">You can prioritize execution of rules by specifying the **Priority** property on rules in Business Rule Composer.</span></span> <span data-ttu-id="68288-160">例如，如果您单击**ApprovedRule**策略浏览器窗口中的节点，您可以看到**优先级**属性窗口中的属性。</span><span class="sxs-lookup"><span data-stu-id="68288-160">For example, if you click the **ApprovedRule** node in the Policy Explorer window, you can see the **Priority** property in the Properties window.</span></span> <span data-ttu-id="68288-161">数字越大，规则优先级越高。</span><span class="sxs-lookup"><span data-stu-id="68288-161">The larger the number, the higher the rule priority.</span></span>  
  
-   <span data-ttu-id="68288-162">您可以使用 XML 架构、 数据库或.NET 程序集作为数据源的策略。</span><span class="sxs-lookup"><span data-stu-id="68288-162">You can use an XML schema, a database, or a .NET assembly as a data source for the policy.</span></span> <span data-ttu-id="68288-163">在本演练中，使用 XML 架构作为数据源。</span><span class="sxs-lookup"><span data-stu-id="68288-163">In this walkthrough, you used an XML schema as a data source.</span></span> <span data-ttu-id="68288-164">应将该架构的 XML 文档实例作为规则引擎以执行策略的事实提交。</span><span class="sxs-lookup"><span data-stu-id="68288-164">You should submit an XML document instance of the schema as a fact to the rule engine to execute the policy.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="68288-165">后续步骤</span><span class="sxs-lookup"><span data-stu-id="68288-165">Next Steps</span></span>  
 <span data-ttu-id="68288-166">现在，已完成本演练中，执行[演练： 测试策略](../core/walkthrough-testing-the-policy.md)演练中，为您提供用于测试的分步说明**ProcessPurchaseOrder**策略，在本演练中创建。</span><span class="sxs-lookup"><span data-stu-id="68288-166">Now that you have completed this walkthrough, perform the [Walkthrough: Testing the Policy](../core/walkthrough-testing-the-policy.md) walkthrough, which gives you step-by-step instructions for testing the **ProcessPurchaseOrder** policy you created in this walkthrough.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68288-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="68288-167">See Also</span></span>  
 [<span data-ttu-id="68288-168">关于业务规则</span><span class="sxs-lookup"><span data-stu-id="68288-168">About Business Rules</span></span>](../core/about-business-rules.md)