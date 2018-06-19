---
title: 演练： 创建事实创建者 |Microsoft 文档
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
ms.openlocfilehash: 9a1c91417cb58eb53e35c724513d4f955e4e6b6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290301"
---
# <a name="walkthrough-creating-a-fact-creator"></a><span data-ttu-id="b7491-102">演练： 创建事实创建者</span><span class="sxs-lookup"><span data-stu-id="b7491-102">Walkthrough: Creating a Fact Creator</span></span>
<span data-ttu-id="b7491-103">本演练提供了分步过程创建事实创建者组件， **POFactCreator**，可以用于测试**ProcessPurchaseOrder**更早版本中创建的策略演练。</span><span class="sxs-lookup"><span data-stu-id="b7491-103">This walkthrough provides step-by-step procedures for creating a fact creator component, **POFactCreator**, which you can use to test the **ProcessPurchaseOrder** policy you created in earlier walkthroughs.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b7491-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="b7491-104">Prerequisites</span></span>  
 <span data-ttu-id="b7491-105">必须完成[演练： 创建简单的业务策略](../core/walkthrough-creating-a-simple-business-policy.md)演练在执行本演练之前。</span><span class="sxs-lookup"><span data-stu-id="b7491-105">You must complete the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough before you perform this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="b7491-106">本演练的概述</span><span class="sxs-lookup"><span data-stu-id="b7491-106">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="b7491-107">本概览包含两个过程，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="b7491-107">This walkthrough contains two procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="b7491-108">过程标题</span><span class="sxs-lookup"><span data-stu-id="b7491-108">Procedure title</span></span>|<span data-ttu-id="b7491-109">过程说明</span><span class="sxs-lookup"><span data-stu-id="b7491-109">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="b7491-110">创建 POFactCreator 组件</span><span class="sxs-lookup"><span data-stu-id="b7491-110">To create the POFactCreator component</span></span>|<span data-ttu-id="b7491-111">提供有关创建事实创建者组件的分步说明**POFactCreator**。</span><span class="sxs-lookup"><span data-stu-id="b7491-111">Provides step-by-step instructions for creating a fact creator component, **POFactCreator**.</span></span>|  
|<span data-ttu-id="b7491-112">要测试使用 POFactCreator ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="b7491-112">To test the ProcessPurchaseOrder policy using POFactCreator</span></span>|<span data-ttu-id="b7491-113">提供有关使用业务规则编辑器工具测试的分步说明**ProcessPurchaseOrder**策略通过使用**POFactCreator**组件。</span><span class="sxs-lookup"><span data-stu-id="b7491-113">Provides step-by-step instructions for using the Business Rule Composer tool to test the **ProcessPurchaseOrder** policy by using the **POFactCreator** component.</span></span>|  
  
### <a name="to-create-the-pofactcreator-component"></a><span data-ttu-id="b7491-114">创建 POFactCreator 组件</span><span class="sxs-lookup"><span data-stu-id="b7491-114">To create the POFactCreator component</span></span>  
  
1.  <span data-ttu-id="b7491-115">启动**Microsoft Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="b7491-115">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="b7491-116">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]上**文件**菜单上，指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="b7491-116">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="b7491-117">在**新项目**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b7491-117">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="b7491-118">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b7491-118">Use this</span></span>|<span data-ttu-id="b7491-119">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b7491-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b7491-120">**项目类型**</span><span class="sxs-lookup"><span data-stu-id="b7491-120">**Project types**</span></span>|<span data-ttu-id="b7491-121">单击**Visual C#**。</span><span class="sxs-lookup"><span data-stu-id="b7491-121">Click **Visual C#**.</span></span>|  
    |<span data-ttu-id="b7491-122">**模板**</span><span class="sxs-lookup"><span data-stu-id="b7491-122">**Templates**</span></span>|<span data-ttu-id="b7491-123">单击**类库**。</span><span class="sxs-lookup"><span data-stu-id="b7491-123">Click **Class Library**.</span></span>|  
    |<span data-ttu-id="b7491-124">**名称**</span><span class="sxs-lookup"><span data-stu-id="b7491-124">**Name**</span></span>|<span data-ttu-id="b7491-125">类型**POFactCreatorLib**。</span><span class="sxs-lookup"><span data-stu-id="b7491-125">Type **POFactCreatorLib**.</span></span>|  
    |<span data-ttu-id="b7491-126">**位置**</span><span class="sxs-lookup"><span data-stu-id="b7491-126">**Location**</span></span>|<span data-ttu-id="b7491-127">指定**C:\BRE-Walkthroughs**作为位置。</span><span class="sxs-lookup"><span data-stu-id="b7491-127">Specify **C:\BRE-Walkthroughs** as the location.</span></span>|  
    |<span data-ttu-id="b7491-128">**解决方案名称**</span><span class="sxs-lookup"><span data-stu-id="b7491-128">**Solution Name**</span></span>|<span data-ttu-id="b7491-129">类型**POFactCreatorSol**。</span><span class="sxs-lookup"><span data-stu-id="b7491-129">Type **POFactCreatorSol**.</span></span>|  
    |<span data-ttu-id="b7491-130">**创建解决方案的目录**</span><span class="sxs-lookup"><span data-stu-id="b7491-130">**Create directory for solution**</span></span>|<span data-ttu-id="b7491-131">选中此复选框以便为解决方案文件创建目录。</span><span class="sxs-lookup"><span data-stu-id="b7491-131">Select this check box to create a directory for the solution files.</span></span>|  
  
4.  <span data-ttu-id="b7491-132">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b7491-132">Click **OK**.</span></span> <span data-ttu-id="b7491-133">**POFactCreatorLib**项目应显示在解决方案资源管理器中。</span><span class="sxs-lookup"><span data-stu-id="b7491-133">The **POFactCreatorLib** project should appear in Solution Explorer.</span></span> <span data-ttu-id="b7491-134">如果看不到解决方案资源管理器，请单击**解决方案资源管理器**上**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="b7491-134">If you do not see Solution Explorer, click **Solution Explorer** on the **View** menu.</span></span>  
  
5.  <span data-ttu-id="b7491-135">在属性窗口中，更改文件的名称， **Class1.cs**到**POFactCreator.cs**。</span><span class="sxs-lookup"><span data-stu-id="b7491-135">In the Properties window, change the name of the file, **Class1.cs**, to **POFactCreator.cs**.</span></span>  
  
6.  <span data-ttu-id="b7491-136">在解决方案资源管理器窗口中，右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="b7491-136">In the Solution Explorer window, right-click **References**, and then click **Add Reference**.</span></span>  
  
7.  <span data-ttu-id="b7491-137">单击**浏览**，导航到**C:\Program Files\Common Files\Microsoft BizTalk**，然后双击**Microsoft.RuleEngine.dll**。</span><span class="sxs-lookup"><span data-stu-id="b7491-137">Click **Browse**, navigate to **C:\Program Files\Common Files\Microsoft BizTalk**, and then double-click **Microsoft.RuleEngine.dll**.</span></span>  
  
8.  <span data-ttu-id="b7491-138">将以下行添加到顶部**POFactCreator.cs**后现有文件`using`语句：</span><span class="sxs-lookup"><span data-stu-id="b7491-138">Add the following lines to the top of the **POFactCreator.cs** file after the existing `using` statements:</span></span>  
  
    ```  
    //To use the XmlDocument class  
    using System.Xml;  
    //To use the TypedXmlDocument and Policy classes  
    using Microsoft.RuleEngine;   
    ```  
  
9. <span data-ttu-id="b7491-139">修改**POFactCreator**类以派生自**IFactCreator**接口：</span><span class="sxs-lookup"><span data-stu-id="b7491-139">Modify the **POFactCreator** class to derive from the **IFactCreator** interface:</span></span>  
  
    ```  
    public class POFactCreator : IFactCreator  
    {  
    }  
    ```  
  
10. <span data-ttu-id="b7491-140">右键单击**IFactCreator**，指向**实现接口**，然后单击**实现接口**。</span><span class="sxs-lookup"><span data-stu-id="b7491-140">Right-click **IFactCreator**, point to **Implement Interface**, and then click **Implement Interface**.</span></span>  
  
     <span data-ttu-id="b7491-141">![BRE &#45;演练 &#45; ImplementInterface](../core/media/ca1ae06c-ad24-4eac-94c3-5a06ad0f7305.gif "ca1ae06c-ad24-4eac-94c3-5a06ad0f7305")</span><span class="sxs-lookup"><span data-stu-id="b7491-141">![BRE&#45;Walkthrough&#45;ImplementInterface](../core/media/ca1ae06c-ad24-4eac-94c3-5a06ad0f7305.gif "ca1ae06c-ad24-4eac-94c3-5a06ad0f7305")</span></span>  
  
11. <span data-ttu-id="b7491-142">添加到一个公共构造函数**POFactCreator**类如下所示：</span><span class="sxs-lookup"><span data-stu-id="b7491-142">Add a public constructor to the **POFactCreator** class as shown below:</span></span>  
  
    ```  
    public POFactCreator()  
    {  
    }  
    ```  
  
12. <span data-ttu-id="b7491-143">删除中的唯一语句**CreateFacts**方法。</span><span class="sxs-lookup"><span data-stu-id="b7491-143">Remove the lone statement in the **CreateFacts** method.</span></span>  
  
13. <span data-ttu-id="b7491-144">以下代码添加到**CreateFacts**方法来创建**TypedXmlDocument**对象基于**SamplePO.xml**文档：</span><span class="sxs-lookup"><span data-stu-id="b7491-144">Add the following code to the **CreateFacts** method to create a **TypedXmlDocument** object based on the **SamplePO.xml** document:</span></span>  
  
    ```  
    XmlDocument doc = new XmlDocument();  
    //Loading the XML from SamplePO.xml file.  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
    ```  
  
14. <span data-ttu-id="b7491-145">添加以下代码创建的事实数据与数组**TypedXmlDocument**对象作为的唯一一个事实：</span><span class="sxs-lookup"><span data-stu-id="b7491-145">Add the following code to create an array of facts with the **TypedXmlDocument** object as the only fact:</span></span>  
  
    ```  
    object[] facts = new object[1];  
    facts[0] = txd;   
    ```  
  
15. <span data-ttu-id="b7491-146">返回数组事实**CreateFacts**方法：</span><span class="sxs-lookup"><span data-stu-id="b7491-146">Return the facts array from the **CreateFacts** method:</span></span>  
  
    ```  
    return facts;  
    ```  
  
16. <span data-ttu-id="b7491-147">验证中的完整代码**CreateFacts**方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="b7491-147">Verify that the complete code in the **CreateFacts** method looks like the following:</span></span>  
  
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
  
17. <span data-ttu-id="b7491-148">删除中的唯一语句**GetFactTypes**方法。</span><span class="sxs-lookup"><span data-stu-id="b7491-148">Remove the lone statement in the **GetFactTypes** method.</span></span>  
  
18. <span data-ttu-id="b7491-149">以下代码添加到**GetFactTypes**方法返回的类型包含的类型的数组**TypedXmlDocument**类：</span><span class="sxs-lookup"><span data-stu-id="b7491-149">Add the following code to the **GetFactTypes** method to return an array of types containing the type of the **TypedXmlDocument** class:</span></span>  
  
    ```  
    Type[] t = new Type[1];  
    t[0] = typeof(TypedXmlDocument);  
    return t;  
    ```  
  
19. <span data-ttu-id="b7491-150">启动**Visual Studio 命令提示**。</span><span class="sxs-lookup"><span data-stu-id="b7491-150">Start **Visual Studio Command Prompt**.</span></span>  
  
20. <span data-ttu-id="b7491-151">将目录更改为**C:\BRE-Walkthroughs\POFactCreatorSol**，然后执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b7491-151">Change the directory to **C:\BRE-Walkthroughs\POFactCreatorSol**, and then execute the following command:</span></span>  
  
     <span data-ttu-id="b7491-152">**Sn-k POFactCreator.snk**</span><span class="sxs-lookup"><span data-stu-id="b7491-152">**Sn -k POFactCreator.snk**</span></span>  
  
21. <span data-ttu-id="b7491-153">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器，展开**属性**，然后双击**AssemblyInfo.cs**。</span><span class="sxs-lookup"><span data-stu-id="b7491-153">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], in Solution Explorer, expand **Properties**, and then double-click **AssemblyInfo.cs**.</span></span>  
  
22. <span data-ttu-id="b7491-154">添加以下语句到**AssemblyInfo.cs**结尾的文件：</span><span class="sxs-lookup"><span data-stu-id="b7491-154">Add the following statement to the **AssemblyInfo.cs** file at the end:</span></span>  
  
    ```  
    [assembly: AssemblyKeyFile(@"C:\BRE-Walkthroughs\POFactCreatorSol\POFactCreator.snk")]  
    ```  
  
23. <span data-ttu-id="b7491-155">在解决方案资源管理器窗口中，右键单击**POFactCreatorLib**，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="b7491-155">In the Solution Explorer window, right-click **POFactCreatorLib**, and then click **Build**.</span></span>  
  
24. <span data-ttu-id="b7491-156">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，将目录更改为**C:\BRE-Walkthroughs\POFactCreatorSol\POFactCreatorLib\Bin\Debug**，然后执行以下命令以注册**POFactCreator** GAC （全局程序集缓存） 组件。</span><span class="sxs-lookup"><span data-stu-id="b7491-156">At the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command Prompt, change the directory to **C:\BRE-Walkthroughs\POFactCreatorSol\POFactCreatorLib\Bin\Debug**, and then execute the following command to register the **POFactCreator** component with the GAC (global assembly cache).</span></span> <span data-ttu-id="b7491-157">如果没有打开命令提示，请按照步骤 19 的方法打开它。</span><span class="sxs-lookup"><span data-stu-id="b7491-157">If you do not have the command prompt open, follow step 19 to open it.</span></span>  
  
     <span data-ttu-id="b7491-158">**Gacutil-i POFactCreatorLib.dll**</span><span class="sxs-lookup"><span data-stu-id="b7491-158">**Gacutil -i POFactCreatorLib.dll**</span></span>  
  
### <a name="to-test-the-processpurchaseorder-policy-using-pofactcreator"></a><span data-ttu-id="b7491-159">要测试使用 POFactCreator ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="b7491-159">To test the ProcessPurchaseOrder policy using POFactCreator</span></span>  
  
1.  <span data-ttu-id="b7491-160">上**启动**菜单上，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="b7491-160">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Business Rule Composer**.</span></span> <span data-ttu-id="b7491-161">如果已打开业务规则编辑器，请按 F5 刷新。</span><span class="sxs-lookup"><span data-stu-id="b7491-161">If you have the Business Rule Composer already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b7491-162">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="b7491-162">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="b7491-163">要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="b7491-163">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="b7491-164">在策略资源管理器窗口中，展开**策略**，展开**ProcessPurchaseOrder**，最新版本中，右键单击，然后单击**测试策略**。</span><span class="sxs-lookup"><span data-stu-id="b7491-164">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click the latest version, and then click **Test Policy**.</span></span>  
  
     <span data-ttu-id="b7491-165">![业务规则编辑器 &#45;TestPolicyMenu](../core/media/af63c437-aeba-4e6a-a772-3346e7babee5.gif "af63c437-aeba-4e6a-a772-3346e7babee5")</span><span class="sxs-lookup"><span data-stu-id="b7491-165">![Business Rule Composer&#45;TestPolicyMenu](../core/media/af63c437-aeba-4e6a-a772-3346e7babee5.gif "af63c437-aeba-4e6a-a772-3346e7babee5")</span></span>  
  
3.  <span data-ttu-id="b7491-166">在对话框的底部，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="b7491-166">At the bottom of the dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="b7491-167">在 **.NET 程序集**对话框中，选择**POFactCreatorLib**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b7491-167">In the **.NET Assemblies** dialog box, select **POFactCreatorLib**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="b7491-168">在**选择绑定**对话框中，单击**POFactCreator**中**POFactCreatorLib，10.0.0**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b7491-168">In the **Select Binding** dialog box, click **POFactCreator** in **POFactCreatorLib, 10.0.0**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="b7491-169">单击**测试**。</span><span class="sxs-lookup"><span data-stu-id="b7491-169">Click **Test**.</span></span>  
  
7.  <span data-ttu-id="b7491-170">验证**ApprovalRule**激发输出窗口中。</span><span class="sxs-lookup"><span data-stu-id="b7491-170">Verify that the **ApprovalRule** is fired in the Output window.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="b7491-171">注释</span><span class="sxs-lookup"><span data-stu-id="b7491-171">Comments</span></span>  
  
-   <span data-ttu-id="b7491-172">若要借助业务规则编辑器来测试使用 .NET 类的非静态方法的策略，你必须创建一个事实创建器组件。</span><span class="sxs-lookup"><span data-stu-id="b7491-172">To test a policy that uses non-static methods of a .NET class by using the Business Rule Composer, you must create a fact creator component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7491-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7491-173">See Also</span></span>  
 [<span data-ttu-id="b7491-174">如何创建事实检索器</span><span class="sxs-lookup"><span data-stu-id="b7491-174">How to Create a Fact Retriever</span></span>](../core/how-to-create-a-fact-retriever.md)