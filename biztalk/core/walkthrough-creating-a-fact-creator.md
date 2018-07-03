---
title: 演练： 创建事实创建器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 041c8f73-c72e-43fd-8446-144cecdc95ef
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbe1e856ad97d81a153828a4d5ae45795670ed1f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017318"
---
# <a name="walkthrough-creating-a-fact-creator"></a><span data-ttu-id="7e11d-102">演练： 创建事实创建器</span><span class="sxs-lookup"><span data-stu-id="7e11d-102">Walkthrough: Creating a Fact Creator</span></span>
<span data-ttu-id="7e11d-103">本演练提供了创建事实创建器组件的分步过程**POFactCreator**，这可用于测试**ProcessPurchaseOrder**先前在创建的策略演练。</span><span class="sxs-lookup"><span data-stu-id="7e11d-103">This walkthrough provides step-by-step procedures for creating a fact creator component, **POFactCreator**, which you can use to test the **ProcessPurchaseOrder** policy you created in earlier walkthroughs.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="7e11d-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="7e11d-104">Prerequisites</span></span>  
 <span data-ttu-id="7e11d-105">必须完成[演练： 创建简单业务策略](../core/walkthrough-creating-a-simple-business-policy.md)演练在执行本演练之前。</span><span class="sxs-lookup"><span data-stu-id="7e11d-105">You must complete the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough before you perform this walkthrough.</span></span>  

## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="7e11d-106">本演练概述</span><span class="sxs-lookup"><span data-stu-id="7e11d-106">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="7e11d-107">本概览包含两个过程，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="7e11d-107">This walkthrough contains two procedures, as described in the following table.</span></span>  

|<span data-ttu-id="7e11d-108">过程标题</span><span class="sxs-lookup"><span data-stu-id="7e11d-108">Procedure title</span></span>|<span data-ttu-id="7e11d-109">过程说明</span><span class="sxs-lookup"><span data-stu-id="7e11d-109">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="7e11d-110">创建 POFactCreator 组件</span><span class="sxs-lookup"><span data-stu-id="7e11d-110">To create the POFactCreator component</span></span>|<span data-ttu-id="7e11d-111">提供创建事实创建器组件的分步说明**POFactCreator**。</span><span class="sxs-lookup"><span data-stu-id="7e11d-111">Provides step-by-step instructions for creating a fact creator component, **POFactCreator**.</span></span>|  
|<span data-ttu-id="7e11d-112">若要测试使用 POFactCreator ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="7e11d-112">To test the ProcessPurchaseOrder policy using POFactCreator</span></span>|<span data-ttu-id="7e11d-113">提供使用业务规则编辑器工具来测试的分步说明**ProcessPurchaseOrder**通过使用策略**POFactCreator**组件。</span><span class="sxs-lookup"><span data-stu-id="7e11d-113">Provides step-by-step instructions for using the Business Rule Composer tool to test the **ProcessPurchaseOrder** policy by using the **POFactCreator** component.</span></span>|  

### <a name="to-create-the-pofactcreator-component"></a><span data-ttu-id="7e11d-114">创建 POFactCreator 组件</span><span class="sxs-lookup"><span data-stu-id="7e11d-114">To create the POFactCreator component</span></span>  

1. <span data-ttu-id="7e11d-115">启动**Microsoft Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="7e11d-115">Start **Microsoft Visual Studio**.</span></span>  

2. <span data-ttu-id="7e11d-116">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="7e11d-116">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  

3. <span data-ttu-id="7e11d-117">在中**新的项目**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7e11d-117">In the **New Project** dialog box, do the following:</span></span>  


   |             <span data-ttu-id="7e11d-118">使用此选项</span><span class="sxs-lookup"><span data-stu-id="7e11d-118">Use this</span></span>              |                             <span data-ttu-id="7e11d-119">执行的操作</span><span class="sxs-lookup"><span data-stu-id="7e11d-119">To do this</span></span>                              |
   |-----------------------------------|---------------------------------------------------------------------|
   |         <span data-ttu-id="7e11d-120">**项目类型**</span><span class="sxs-lookup"><span data-stu-id="7e11d-120">**Project types**</span></span>         |                        <span data-ttu-id="7e11d-121">单击**Visual C#**。</span><span class="sxs-lookup"><span data-stu-id="7e11d-121">Click **Visual C#**.</span></span>                         |
   |           <span data-ttu-id="7e11d-122">**模板**</span><span class="sxs-lookup"><span data-stu-id="7e11d-122">**Templates**</span></span>           |                      <span data-ttu-id="7e11d-123">单击**类库**。</span><span class="sxs-lookup"><span data-stu-id="7e11d-123">Click **Class Library**.</span></span>                       |
   |             <span data-ttu-id="7e11d-124">**名称**</span><span class="sxs-lookup"><span data-stu-id="7e11d-124">**Name**</span></span>              |                     <span data-ttu-id="7e11d-125">类型**POFactCreatorLib**。</span><span class="sxs-lookup"><span data-stu-id="7e11d-125">Type **POFactCreatorLib**.</span></span>                      |
   |           <span data-ttu-id="7e11d-126">**位置**</span><span class="sxs-lookup"><span data-stu-id="7e11d-126">**Location**</span></span>            |          <span data-ttu-id="7e11d-127">指定**C:\BRE-Walkthroughs**作为位置。</span><span class="sxs-lookup"><span data-stu-id="7e11d-127">Specify **C:\BRE-Walkthroughs** as the location.</span></span>           |
   |         <span data-ttu-id="7e11d-128">**解决方案名称**</span><span class="sxs-lookup"><span data-stu-id="7e11d-128">**Solution Name**</span></span>         |                     <span data-ttu-id="7e11d-129">类型**POFactCreatorSol**。</span><span class="sxs-lookup"><span data-stu-id="7e11d-129">Type **POFactCreatorSol**.</span></span>                      |
   | <span data-ttu-id="7e11d-130">**创建解决方案的目录**</span><span class="sxs-lookup"><span data-stu-id="7e11d-130">**Create directory for solution**</span></span> | <span data-ttu-id="7e11d-131">选中此复选框以便为解决方案文件创建目录。</span><span class="sxs-lookup"><span data-stu-id="7e11d-131">Select this check box to create a directory for the solution files.</span></span> |


4. <span data-ttu-id="7e11d-132">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="7e11d-132">Click **OK**.</span></span> <span data-ttu-id="7e11d-133">**POFactCreatorLib**项目应该显示在解决方案资源管理器。</span><span class="sxs-lookup"><span data-stu-id="7e11d-133">The **POFactCreatorLib** project should appear in Solution Explorer.</span></span> <span data-ttu-id="7e11d-134">如果看不到解决方案资源管理器，请单击**解决方案资源管理器**上**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="7e11d-134">If you do not see Solution Explorer, click **Solution Explorer** on the **View** menu.</span></span>  

5. <span data-ttu-id="7e11d-135">在属性窗口中更改文件的名称**Class1.cs**给**POFactCreator.cs**。</span><span class="sxs-lookup"><span data-stu-id="7e11d-135">In the Properties window, change the name of the file, **Class1.cs**, to **POFactCreator.cs**.</span></span>  

6. <span data-ttu-id="7e11d-136">在解决方案资源管理器窗口中，右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="7e11d-136">In the Solution Explorer window, right-click **References**, and then click **Add Reference**.</span></span>  

7. <span data-ttu-id="7e11d-137">单击**浏览**，导航到**C:\Program Files\Common Files\Microsoft BizTalk**，然后双击**Microsoft.RuleEngine.dll**。</span><span class="sxs-lookup"><span data-stu-id="7e11d-137">Click **Browse**, navigate to **C:\Program Files\Common Files\Microsoft BizTalk**, and then double-click **Microsoft.RuleEngine.dll**.</span></span>  

8. <span data-ttu-id="7e11d-138">将以下行添加到顶部**POFactCreator.cs**之后的现有文件`using`语句：</span><span class="sxs-lookup"><span data-stu-id="7e11d-138">Add the following lines to the top of the **POFactCreator.cs** file after the existing `using` statements:</span></span>  

   ```  
   //To use the XmlDocument class  
   using System.Xml;  
   //To use the TypedXmlDocument and Policy classes  
   using Microsoft.RuleEngine;   
   ```  

9. <span data-ttu-id="7e11d-139">修改**POFactCreator**类进行派生**IFactCreator**接口：</span><span class="sxs-lookup"><span data-stu-id="7e11d-139">Modify the **POFactCreator** class to derive from the **IFactCreator** interface:</span></span>  

    ```  
    public class POFactCreator : IFactCreator  
    {  
    }  
    ```  

10. <span data-ttu-id="7e11d-140">右键单击**IFactCreator**，依次指向**实现接口**，然后单击**实现接口**。</span><span class="sxs-lookup"><span data-stu-id="7e11d-140">Right-click **IFactCreator**, point to **Implement Interface**, and then click **Implement Interface**.</span></span>  

     <span data-ttu-id="7e11d-141">![BRE&#45;演练&#45;ImplementInterface](../core/media/ca1ae06c-ad24-4eac-94c3-5a06ad0f7305.gif "ca1ae06c-ad24-4eac-94c3-5a06ad0f7305")</span><span class="sxs-lookup"><span data-stu-id="7e11d-141">![BRE&#45;Walkthrough&#45;ImplementInterface](../core/media/ca1ae06c-ad24-4eac-94c3-5a06ad0f7305.gif "ca1ae06c-ad24-4eac-94c3-5a06ad0f7305")</span></span>  

11. <span data-ttu-id="7e11d-142">添加到一个公共构造函数**POFactCreator**类，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7e11d-142">Add a public constructor to the **POFactCreator** class as shown below:</span></span>  

    ```  
    public POFactCreator()  
    {  
    }  
    ```  

12. <span data-ttu-id="7e11d-143">删除中的单个语句**CreateFacts**方法。</span><span class="sxs-lookup"><span data-stu-id="7e11d-143">Remove the lone statement in the **CreateFacts** method.</span></span>  

13. <span data-ttu-id="7e11d-144">将以下代码添加到**CreateFacts**方法来创建**TypedXmlDocument**对象基于**SamplePO.xml**文档：</span><span class="sxs-lookup"><span data-stu-id="7e11d-144">Add the following code to the **CreateFacts** method to create a **TypedXmlDocument** object based on the **SamplePO.xml** document:</span></span>  

    ```  
    XmlDocument doc = new XmlDocument();  
    //Loading the XML from SamplePO.xml file.  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
    ```  

14. <span data-ttu-id="7e11d-145">添加以下代码以创建一个与事实数组**TypedXmlDocument**对象作为其唯一事实：</span><span class="sxs-lookup"><span data-stu-id="7e11d-145">Add the following code to create an array of facts with the **TypedXmlDocument** object as the only fact:</span></span>  

    ```  
    object[] facts = new object[1];  
    facts[0] = txd;   
    ```  

15. <span data-ttu-id="7e11d-146">返回事实数组**CreateFacts**方法：</span><span class="sxs-lookup"><span data-stu-id="7e11d-146">Return the facts array from the **CreateFacts** method:</span></span>  

    ```  
    return facts;  
    ```  

16. <span data-ttu-id="7e11d-147">验证中的完整代码**CreateFacts**方法看起来如下所示：</span><span class="sxs-lookup"><span data-stu-id="7e11d-147">Verify that the complete code in the **CreateFacts** method looks like the following:</span></span>  

    ```  
    public object[] CreateFacts(RuleSetInfo ruleSetInfo)  
    {  
    XmlDocument doc = new XmlDocument();  
    //Loading the XML from SamplePO.xml file.  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  

    object[] facts = new object[1];  
    facts[0] = txd;  
    return facts;  
    }  
    ```  

17. <span data-ttu-id="7e11d-148">删除中的单个语句**GetFactTypes**方法。</span><span class="sxs-lookup"><span data-stu-id="7e11d-148">Remove the lone statement in the **GetFactTypes** method.</span></span>  

18. <span data-ttu-id="7e11d-149">将以下代码添加到**GetFactTypes**方法以返回一个类型包含的类型的数组**TypedXmlDocument**类：</span><span class="sxs-lookup"><span data-stu-id="7e11d-149">Add the following code to the **GetFactTypes** method to return an array of types containing the type of the **TypedXmlDocument** class:</span></span>  

    ```  
    Type[] t = new Type[1];  
    t[0] = typeof(TypedXmlDocument);  
    return t;  
    ```  

19. <span data-ttu-id="7e11d-150">启动**Visual Studio 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="7e11d-150">Start **Visual Studio Command Prompt**.</span></span>  

20. <span data-ttu-id="7e11d-151">将目录更改为**C:\BRE-Walkthroughs\POFactCreatorSol**，然后执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="7e11d-151">Change the directory to **C:\BRE-Walkthroughs\POFactCreatorSol**, and then execute the following command:</span></span>  

     <span data-ttu-id="7e11d-152">**Sn-k POFactCreator.snk**</span><span class="sxs-lookup"><span data-stu-id="7e11d-152">**Sn -k POFactCreator.snk**</span></span>  

21. <span data-ttu-id="7e11d-153">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器，展开**属性**，然后双击**AssemblyInfo.cs**。</span><span class="sxs-lookup"><span data-stu-id="7e11d-153">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], in Solution Explorer, expand **Properties**, and then double-click **AssemblyInfo.cs**.</span></span>  

22. <span data-ttu-id="7e11d-154">添加以下语句到**AssemblyInfo.cs**文件的末尾：</span><span class="sxs-lookup"><span data-stu-id="7e11d-154">Add the following statement to the **AssemblyInfo.cs** file at the end:</span></span>  

    ```  
    [assembly: AssemblyKeyFile(@"C:\BRE-Walkthroughs\POFactCreatorSol\POFactCreator.snk")]  
    ```  

23. <span data-ttu-id="7e11d-155">在解决方案资源管理器窗口中，右键单击**POFactCreatorLib**，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="7e11d-155">In the Solution Explorer window, right-click **POFactCreatorLib**, and then click **Build**.</span></span>  

24. <span data-ttu-id="7e11d-156">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，将目录更改为**C:\BRE-Walkthroughs\POFactCreatorSol\POFactCreatorLib\Bin\Debug**，然后执行以下命令以注册**POFactCreator**组件向 GAC （全局程序集缓存）。</span><span class="sxs-lookup"><span data-stu-id="7e11d-156">At the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command Prompt, change the directory to **C:\BRE-Walkthroughs\POFactCreatorSol\POFactCreatorLib\Bin\Debug**, and then execute the following command to register the **POFactCreator** component with the GAC (global assembly cache).</span></span> <span data-ttu-id="7e11d-157">如果没有打开命令提示，请按照步骤 19 的方法打开它。</span><span class="sxs-lookup"><span data-stu-id="7e11d-157">If you do not have the command prompt open, follow step 19 to open it.</span></span>  

     <span data-ttu-id="7e11d-158">**Gacutil-i POFactCreatorLib.dll**</span><span class="sxs-lookup"><span data-stu-id="7e11d-158">**Gacutil -i POFactCreatorLib.dll**</span></span>  

### <a name="to-test-the-processpurchaseorder-policy-using-pofactcreator"></a><span data-ttu-id="7e11d-159">若要测试使用 POFactCreator ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="7e11d-159">To test the ProcessPurchaseOrder policy using POFactCreator</span></span>  

1. <span data-ttu-id="7e11d-160">上**启动**菜单，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="7e11d-160">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Business Rule Composer**.</span></span> <span data-ttu-id="7e11d-161">如果已打开业务规则编辑器，请按 F5 刷新。</span><span class="sxs-lookup"><span data-stu-id="7e11d-161">If you have the Business Rule Composer already open, press F5 to refresh it.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="7e11d-162">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="7e11d-162">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="7e11d-163">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="7e11d-163">To do this, right-click the application, and then select **Run as administrator**.</span></span>  

2. <span data-ttu-id="7e11d-164">在策略浏览器窗口中，展开**策略**，展开**ProcessPurchaseOrder**，右键单击最新版本，然后单击**测试策略**。</span><span class="sxs-lookup"><span data-stu-id="7e11d-164">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click the latest version, and then click **Test Policy**.</span></span>  

    <span data-ttu-id="7e11d-165">![业务规则编辑器&#45;TestPolicyMenu](../core/media/af63c437-aeba-4e6a-a772-3346e7babee5.gif "af63c437-aeba-4e6a-a772-3346e7babee5")</span><span class="sxs-lookup"><span data-stu-id="7e11d-165">![Business Rule Composer&#45;TestPolicyMenu](../core/media/af63c437-aeba-4e6a-a772-3346e7babee5.gif "af63c437-aeba-4e6a-a772-3346e7babee5")</span></span>  

3. <span data-ttu-id="7e11d-166">在对话框的底部，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="7e11d-166">At the bottom of the dialog box, click **Add**.</span></span>  

4. <span data-ttu-id="7e11d-167">在中 **.NET 程序集**对话框中，选择**POFactCreatorLib**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7e11d-167">In the **.NET Assemblies** dialog box, select **POFactCreatorLib**, and then click **OK**.</span></span>  

5. <span data-ttu-id="7e11d-168">在中**选择绑定**对话框中，单击**POFactCreator**中**POFactCreatorLib，10.0.0**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7e11d-168">In the **Select Binding** dialog box, click **POFactCreator** in **POFactCreatorLib, 10.0.0**, and then click **OK**.</span></span>  

6. <span data-ttu-id="7e11d-169">单击**测试**。</span><span class="sxs-lookup"><span data-stu-id="7e11d-169">Click **Test**.</span></span>  

7. <span data-ttu-id="7e11d-170">确认**ApprovalRule**激发输出窗口中。</span><span class="sxs-lookup"><span data-stu-id="7e11d-170">Verify that the **ApprovalRule** is fired in the Output window.</span></span>  

## <a name="comments"></a><span data-ttu-id="7e11d-171">注释</span><span class="sxs-lookup"><span data-stu-id="7e11d-171">Comments</span></span>  

-   <span data-ttu-id="7e11d-172">若要借助业务规则编辑器来测试使用 .NET 类的非静态方法的策略，你必须创建一个事实创建器组件。</span><span class="sxs-lookup"><span data-stu-id="7e11d-172">To test a policy that uses non-static methods of a .NET class by using the Business Rule Composer, you must create a fact creator component.</span></span>  

## <a name="see-also"></a><span data-ttu-id="7e11d-173">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e11d-173">See Also</span></span>  
 [<span data-ttu-id="7e11d-174">如何创建事实检索器</span><span class="sxs-lookup"><span data-stu-id="7e11d-174">How to Create a Fact Retriever</span></span>](../core/how-to-create-a-fact-retriever.md)