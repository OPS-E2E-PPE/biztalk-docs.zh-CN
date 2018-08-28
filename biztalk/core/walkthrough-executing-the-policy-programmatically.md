---
title: 演练： 以编程方式执行策略 |Microsoft Docs
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6398e7af-2ed1-4596-879c-3b7d000b8de2
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 666b674e30e548489478af898d5fe88c47d21f14
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985718"
---
# <a name="walkthrough-executing-the-policy-programmatically"></a><span data-ttu-id="913a5-102">演练： 以编程方式执行策略</span><span class="sxs-lookup"><span data-stu-id="913a5-102">Walkthrough: Executing the Policy Programmatically</span></span>
<span data-ttu-id="913a5-103">本演练提供了分步过程调用中创建的策略[演练： 创建简单业务策略](../core/walkthrough-creating-a-simple-business-policy.md)演练从一个控制台应用程序以编程方式。</span><span class="sxs-lookup"><span data-stu-id="913a5-103">This walkthrough provides step-by-step procedures for invoking the policy you created in the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough from a console application programmatically.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="913a5-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="913a5-104">Prerequisites</span></span>  
 <span data-ttu-id="913a5-105">必须完成[演练： 创建简单业务策略](../core/walkthrough-creating-a-simple-business-policy.md)演练在执行本演练之前。</span><span class="sxs-lookup"><span data-stu-id="913a5-105">You must complete the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough before you perform this walkthrough.</span></span>  

## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="913a5-106">本演练概述</span><span class="sxs-lookup"><span data-stu-id="913a5-106">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="913a5-107">本概览包含两个过程，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="913a5-107">This walkthrough contains two procedures, as described in the following table.</span></span>  

|<span data-ttu-id="913a5-108">过程标题</span><span class="sxs-lookup"><span data-stu-id="913a5-108">Procedure title</span></span>|<span data-ttu-id="913a5-109">过程说明</span><span class="sxs-lookup"><span data-stu-id="913a5-109">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="913a5-110">使用 Policy.Execute 方法调用 ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="913a5-110">To invoke the ProcessPurchaseOrder policy by using the Policy.Execute method</span></span>|<span data-ttu-id="913a5-111">提供了通过使用调用策略的分步说明**Policy.Execute**方法。</span><span class="sxs-lookup"><span data-stu-id="913a5-111">Provides step-by-step instructions for invoking a policy by using the **Policy.Execute** method.</span></span>|  
|<span data-ttu-id="913a5-112">使用 RuleEngine.Execute 方法调用 ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="913a5-112">To invoke the ProcessPurchaseOrder policy by using the RuleEngine.Execute method</span></span>|<span data-ttu-id="913a5-113">提供了通过使用调用策略的分步说明**RuleEngine.Execute**方法。</span><span class="sxs-lookup"><span data-stu-id="913a5-113">Provides step-by-step instructions for invoking a policy by using the **RuleEngine.Execute** method.</span></span>|  

### <a name="to-invoke-the-processpurchaseorder-policy-by-using-the-policyexecute-method"></a><span data-ttu-id="913a5-114">使用 Policy.Execute 方法调用 ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="913a5-114">To invoke the ProcessPurchaseOrder policy by using the Policy.Execute method</span></span>  

1. <span data-ttu-id="913a5-115">启动**Microsoft Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="913a5-115">Start **Microsoft Visual Studio**.</span></span>  

2. <span data-ttu-id="913a5-116">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="913a5-116">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  

3. <span data-ttu-id="913a5-117">在中**新的项目**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="913a5-117">In the **New Project** dialog box, do the following:</span></span>  


   |             <span data-ttu-id="913a5-118">使用此选项</span><span class="sxs-lookup"><span data-stu-id="913a5-118">Use this</span></span>              |                             <span data-ttu-id="913a5-119">执行的操作</span><span class="sxs-lookup"><span data-stu-id="913a5-119">To do this</span></span>                              |
   |-----------------------------------|---------------------------------------------------------------------|
   |         <span data-ttu-id="913a5-120">**项目类型**</span><span class="sxs-lookup"><span data-stu-id="913a5-120">**Project types**</span></span>         |                        <span data-ttu-id="913a5-121">单击**Visual C#**。</span><span class="sxs-lookup"><span data-stu-id="913a5-121">Click **Visual C#**.</span></span>                         |
   |           <span data-ttu-id="913a5-122">**模板**</span><span class="sxs-lookup"><span data-stu-id="913a5-122">**Templates**</span></span>           |                   <span data-ttu-id="913a5-123">单击**控制台应用程序**。</span><span class="sxs-lookup"><span data-stu-id="913a5-123">Click **Console Application**.</span></span>                    |
   |             <span data-ttu-id="913a5-124">**名称**</span><span class="sxs-lookup"><span data-stu-id="913a5-124">**Name**</span></span>              |                       <span data-ttu-id="913a5-125">类型**ConsoleClient**。</span><span class="sxs-lookup"><span data-stu-id="913a5-125">Type **ConsoleClient**.</span></span>                       |
   |           <span data-ttu-id="913a5-126">**位置**</span><span class="sxs-lookup"><span data-stu-id="913a5-126">**Location**</span></span>            |     <span data-ttu-id="913a5-127">指定要保存项目文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="913a5-127">Specify a folder where you want to save the project files.</span></span>      |
   |         <span data-ttu-id="913a5-128">**解决方案名称**</span><span class="sxs-lookup"><span data-stu-id="913a5-128">**Solution Name**</span></span>         |                     <span data-ttu-id="913a5-129">类型**ConsoleClientSol**。</span><span class="sxs-lookup"><span data-stu-id="913a5-129">Type **ConsoleClientSol**.</span></span>                      |
   | <span data-ttu-id="913a5-130">**创建解决方案的目录**</span><span class="sxs-lookup"><span data-stu-id="913a5-130">**Create directory for solution**</span></span> | <span data-ttu-id="913a5-131">选中此复选框以便为解决方案文件创建目录。</span><span class="sxs-lookup"><span data-stu-id="913a5-131">Select this check box to create a directory for the solution files.</span></span> |


4. <span data-ttu-id="913a5-132">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="913a5-132">Click **OK**.</span></span> <span data-ttu-id="913a5-133">**ConsoleClient**项目应该显示在解决方案资源管理器。</span><span class="sxs-lookup"><span data-stu-id="913a5-133">The **ConsoleClient** project should appear in Solution Explorer.</span></span> <span data-ttu-id="913a5-134">如果看不到解决方案资源管理器，请单击**解决方案资源管理器**上**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="913a5-134">If you do not see Solution Explorer, click **Solution Explorer** on the **View** menu.</span></span>  

5. <span data-ttu-id="913a5-135">在解决方案资源管理器中右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="913a5-135">In Solution Explorer, right-click **References**, and then click **Add Reference**.</span></span>  

6. <span data-ttu-id="913a5-136">单击**浏览**，浏览到**\Program Files\Common Files\Microsoft BizTalk**，然后双击**Microsoft.RuleEngine.dll**。</span><span class="sxs-lookup"><span data-stu-id="913a5-136">Click **Browse**, browse to the **\Program Files\Common Files\Microsoft BizTalk**, and then double-click **Microsoft.RuleEngine.dll**.</span></span>  

7. <span data-ttu-id="913a5-137">将以下行添加到顶部**Program.cs**之后的现有文件`using`语句：</span><span class="sxs-lookup"><span data-stu-id="913a5-137">Add the following lines to the top of the **Program.cs** file after the existing `using` statements:</span></span>  

   ```  
   //To use the XmlDocument class  
   using System.Xml;  
   //To use the TypedXmlDocument and Policy classes  
   using Microsoft.RuleEngine;   
   ```  

8. <span data-ttu-id="913a5-138">将以下代码添加到**Main**函数来创建**TypedXmlDocument**对象基于 XML 文档：</span><span class="sxs-lookup"><span data-stu-id="913a5-138">Add the following code to the **Main** function to create a **TypedXmlDocument** object based on the XML document:</span></span>  

   ```  
   XmlDocument doc = new XmlDocument();  
   //Loading the XML from SamplePO.xml file.  
   //Change the directory as needed  
   doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
   TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
   ```  

9. <span data-ttu-id="913a5-139">将以下代码添加到**Main**函数以执行策略：</span><span class="sxs-lookup"><span data-stu-id="913a5-139">Add the following code to the **Main** function to execute the policy:</span></span>  

    ```  
    //Create a policy object based on the name, ProcessPurchaseOrder  
    Policy policy = new Policy("ProcessPurchaseOrder");  
    //Execute the policy by invoking Policy.Execute method and   
    //by passing the typed xml document as a fact.   
    policy.Execute(txd);   
    ```  

10. <span data-ttu-id="913a5-140">打印的值的输出 XML 以确认**状态**字段设置为**Approved**。</span><span class="sxs-lookup"><span data-stu-id="913a5-140">Print the output XML to confirm that the value of the **Status** field is set to **Approved**.</span></span> <span data-ttu-id="913a5-141">请注意，与不同的业务规则编辑器中，调用**Policy.Execute**方法不会更改原始文档。</span><span class="sxs-lookup"><span data-stu-id="913a5-141">Note that unlike the Business Rule Composer, invoking the **Policy.Execute** method does not change the original document.</span></span>  

    ```  
    //Print the output document  
    Console.WriteLine(txd.Document.OuterXml);   
    ```  

11. <span data-ttu-id="913a5-142">上**构建**菜单上，单击**生成 ConsoleClient**。</span><span class="sxs-lookup"><span data-stu-id="913a5-142">On the **Build** menu, click **Build ConsoleClient**.</span></span>  

12. <span data-ttu-id="913a5-143">按 CTRL+F5 执行此应用程序。</span><span class="sxs-lookup"><span data-stu-id="913a5-143">Press CTRL+F5 to execute the application.</span></span> <span data-ttu-id="913a5-144">确认的值**状态**字段设置为**Approved**。</span><span class="sxs-lookup"><span data-stu-id="913a5-144">Confirm that the value of the **Status** field is set to **Approved**.</span></span>  

### <a name="to-invoke-the-processpurchaseorder-policy-by-using-the-ruleengineexecute-method"></a><span data-ttu-id="913a5-145">使用 RuleEngine.Execute 方法调用 ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="913a5-145">To invoke the ProcessPurchaseOrder policy by using the RuleEngine.Execute method</span></span>  

1.  <span data-ttu-id="913a5-146">在解决方案资源管理器中右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="913a5-146">In Solution Explorer, right-click **References**, and then click **Add Reference**.</span></span>  

2.  <span data-ttu-id="913a5-147">单击**浏览**，浏览到**\Program Files\Common Files\Microsoft BizTalk**，然后双击**Microsoft.BizTalk.RuleEngineExtensions.dll**。</span><span class="sxs-lookup"><span data-stu-id="913a5-147">Click **Browse**, browse to **\Program Files\Common Files\Microsoft BizTalk**, and then double-click **Microsoft.BizTalk.RuleEngineExtensions.dll**.</span></span>  

3.  <span data-ttu-id="913a5-148">注释掉以下行中**Program.cs**文件：</span><span class="sxs-lookup"><span data-stu-id="913a5-148">Comment out the following lines in the **Program.cs** file:</span></span>  

    ```  
    //Create a policy object based on the name, ProcessPurchaseOrder  
    Policy policy = new Policy("ProcessPurchaseOrder");  
    //Execute the policy by invoking Policy.Execute method and   
    //by passing the typed xml document as a fact.   
    policy.Execute(txd);   
    ```  

4.  <span data-ttu-id="913a5-149">在注释掉的代码后面添加下列代码，以访问规则引擎数据库：</span><span class="sxs-lookup"><span data-stu-id="913a5-149">Add the following code after the commented-out code to get access to the Rule Engine database:</span></span>  

    ```  
    //Get access to the SQL rule store   
    Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
    dd = new Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver();  
    SqlRuleStore sqlRuleStore = (SqlRuleStore)dd.GetRuleStore();  
    ```  

5.  <span data-ttu-id="913a5-150">添加以下代码以访问**RuleSetInfoCollection** ProcessPurchaseOrder 策略：</span><span class="sxs-lookup"><span data-stu-id="913a5-150">Add the following code to get access to **RuleSetInfoCollection** for the ProcessPurchaseOrder policy:</span></span>  

    ```  
    //Get access to RuleSetInfoCollection for the   
    //ProcessPurchaseOrder policy  
    RuleSetInfoCollection rsic = sqlRuleStore.GetRuleSets("ProcessPurchaseOrder", RuleStore.Filter.All);  
    ```  

6.  <span data-ttu-id="913a5-151">添加以下代码以创建**RuleSet**对象基于 ProcessPurchaseOrder 策略的规则集信息：</span><span class="sxs-lookup"><span data-stu-id="913a5-151">Add the following code to create a **RuleSet** object based on the rule set information for the ProcessPurchaseOrder policy:</span></span>  

    ```  
    //Create a RuleSet object based on the rule set information   
    //for the ProcessPurchaseOrder policy  
    RuleSet rs = sqlRuleStore.GetRuleSet(rsic[0]);  
    ```  

7.  <span data-ttu-id="913a5-152">添加以下代码以创建**RuleEngine**对象：</span><span class="sxs-lookup"><span data-stu-id="913a5-152">Add the following code to create the **RuleEngine** object:</span></span>  

    ```  
    //Create the RuleEngine object  
    Microsoft.RuleEngine.RuleEngine engine = new Microsoft.RuleEngine.RuleEngine(rs);  
    ```  

8.  <span data-ttu-id="913a5-153">添加以下代码以声明**TypedXmlDocument**到规则引擎工作内存的对象：</span><span class="sxs-lookup"><span data-stu-id="913a5-153">Add the following code to assert the **TypedXmlDocument** object into the working memory of the rule engine:</span></span>  

    ```  
    //Assert the TypedXmlDocument object into working memory  
    //of the rule engine  
    engine.Assert(txd);  
    ```  

9. <span data-ttu-id="913a5-154">现在，添加代码以使用执行策略**RuleEngine.Execute**方法：</span><span class="sxs-lookup"><span data-stu-id="913a5-154">Now add the code to execute the policy by using the **RuleEngine.Execute** method:</span></span>  

    ```  
    //Execute the policy by invoking RuleEngine.Execute method  
    engine.Execute();  
    ```  

10. <span data-ttu-id="913a5-155">请确保**Console.WriteLine**语句是中的最后一个语句**Main**函数。</span><span class="sxs-lookup"><span data-stu-id="913a5-155">Make sure that the **Console.WriteLine** statement is the last statement in the **Main** function.</span></span>  

11. <span data-ttu-id="913a5-156">上**构建**菜单上，单击**生成 ConsoleClient**。</span><span class="sxs-lookup"><span data-stu-id="913a5-156">On the **Build** menu, click **Build ConsoleClient**.</span></span>  

12. <span data-ttu-id="913a5-157">按 CTRL+F5 执行此应用程序。</span><span class="sxs-lookup"><span data-stu-id="913a5-157">Press CTRL+F5 to execute the application.</span></span> <span data-ttu-id="913a5-158">确认的值**状态**字段设置为**Approved**。</span><span class="sxs-lookup"><span data-stu-id="913a5-158">Confirm that the value of the **Status** field is set to **Approved**.</span></span>  

## <a name="comments"></a><span data-ttu-id="913a5-159">注释</span><span class="sxs-lookup"><span data-stu-id="913a5-159">Comments</span></span>  

-   <span data-ttu-id="913a5-160">完整代码**Main**函数通过使用执行 ProcessPurchaseOrder 策略**Policy.Execute**方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="913a5-160">Complete code for the **Main** function to execute the ProcessPurchaseOrder policy by using the **Policy.Execute** method is as follows:</span></span>  

    ```  
    static void Main(string[] args)  
    {  
    XmlDocument doc = new XmlDocument();  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
    Policy policy = new Policy("ProcessPurchaseOrder");  
    policy.Execute(txd);  
    Console.WriteLine(txd.Document.OuterXml);   
    }  
    ```  

-   <span data-ttu-id="913a5-161">使用执行 ProcessPurchaseOrder 策略的完整代码**RuleEngine.Execute**方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="913a5-161">Complete code for executing the ProcessPurchaseOrder policy by using the **RuleEngine.Execute** method is as follows:</span></span>  

    ```  
    static void Main(string[] args)  
    {  
    XmlDocument doc = new XmlDocument();  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
    Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
    dd = new Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver();  
    SqlRuleStore sqlRuleStore = (SqlRuleStore)dd.GetRuleStore();  
    RuleSetInfoCollection rsic = sqlRuleStore.GetRuleSets("ProcessPurchaseOrder", RuleStore.Filter.All);  
    RuleSet rs = sqlRuleStore.GetRuleSet(rsic[0]);  
    Microsoft.RuleEngine.RuleEngine engine = new Microsoft.RuleEngine.RuleEngine(rs);  
    engine.Assert(txd);  
    engine.Execute();  
    Console.WriteLine(txd.Document.OuterXml);   
    }  
    ```  

-   <span data-ttu-id="913a5-162">您可能想要添加**console.readline （)** 末尾处的语句**Main**函数，以便应用程序等候你来终止该应用程序。</span><span class="sxs-lookup"><span data-stu-id="913a5-162">You may want to add a **Console.ReadLine()** statement at the end of the **Main** function so that the application waits for you to terminate the application.</span></span>  

-   <span data-ttu-id="913a5-163">在本演练中，客户端只向 ProcessPurchaseOrder 策略提交一个事实。</span><span class="sxs-lookup"><span data-stu-id="913a5-163">In this walkthrough, the client submits only one fact to the ProcessPurchaseOrder policy.</span></span> <span data-ttu-id="913a5-164">如果客户端需要提交到策略的多个事实，则需要创建一个事实数组并使用重载**Execute**将数组作为参数的方法。</span><span class="sxs-lookup"><span data-stu-id="913a5-164">If the client needs to submit more than one fact to a policy, it needs to create an array of facts and use the overloaded **Execute** method that takes an array as a parameter.</span></span> <span data-ttu-id="913a5-165">下列示例代码演示了具体做法：</span><span class="sxs-lookup"><span data-stu-id="913a5-165">The following sample code shows how to do that:</span></span>  

    ```  
    Policy policy = new Policy("PolicyName");  
    object[] facts = new object[2];  
    facts[0] = txd;  
    facts[1] = new MyClass();  
    policy.Execute(facts);  
    policy.Dispose();  
    ```  

-   <span data-ttu-id="913a5-166">第一个参数**TypedXmlDocument**在代码中的构造函数是用来生成策略的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="913a5-166">The first parameter to the **TypedXmlDocument** constructor in the code is the name of the type you used to build the policy.</span></span>  

-   <span data-ttu-id="913a5-167">**Policy.Execute**方法基本上是周围的包装**RuleEngine.Execute**方法。</span><span class="sxs-lookup"><span data-stu-id="913a5-167">The **Policy.Execute** method is basically a wrapper around the **RuleEngine.Execute** method.</span></span> <span data-ttu-id="913a5-168">因此，使用**Policy.Execute**如您所见本演练中，方法是调用某个策略的最简单的方法。</span><span class="sxs-lookup"><span data-stu-id="913a5-168">Therefore, using the **Policy.Execute** method is the easiest way of invoking a policy, as you have seen in this walkthrough.</span></span>  

-   <span data-ttu-id="913a5-169">更好地执行策略的控制，你可能想要使用**RuleEngine.Execute**而不是使用方法**Policy.Execute**。</span><span class="sxs-lookup"><span data-stu-id="913a5-169">For more control over the execution of the policy, you may want to use the **RuleEngine.Execute** method instead of using **Policy.Execute**.</span></span> <span data-ttu-id="913a5-170">例如，你可以暂时停止引擎通过使用**暂停**函数，并使用来然后恢复**Execute**函数。</span><span class="sxs-lookup"><span data-stu-id="913a5-170">For example, you can halt the engine temporarily by using the **Halt** function, and then resume it by using the **Execute** function.</span></span> <span data-ttu-id="913a5-171">有关详细信息，请参阅[暂停](../core/halt.md)。</span><span class="sxs-lookup"><span data-stu-id="913a5-171">For more information, see [Halt](../core/halt.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="913a5-172">请参阅</span><span class="sxs-lookup"><span data-stu-id="913a5-172">See Also</span></span>  
 [<span data-ttu-id="913a5-173">如何执行策略</span><span class="sxs-lookup"><span data-stu-id="913a5-173">How to Execute Policies</span></span>](../core/how-to-execute-policies.md)