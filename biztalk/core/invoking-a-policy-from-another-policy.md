---
title: 从另一个策略调用某个策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5bf658a-02a1-426a-abe5-8c9de673cf0d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39f1366ccbf199db02bc60c0caf9015aba0cfc03
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994030"
---
# <a name="invoking-a-policy-from-another-policy"></a><span data-ttu-id="ed508-102">从其他策略调用策略</span><span class="sxs-lookup"><span data-stu-id="ed508-102">Invoking a Policy from Another Policy</span></span>
<span data-ttu-id="ed508-103">您可以通过使用以下方式之一从其他策略（父策略）调用策略（子策略）：</span><span class="sxs-lookup"><span data-stu-id="ed508-103">You can invoke a policy (child) from another policy (parent) by using one of the following methods:</span></span>  
  
- <span data-ttu-id="ed508-104">调用**Policy.Execute**方法直接从父策略</span><span class="sxs-lookup"><span data-stu-id="ed508-104">Calling the **Policy.Execute** method directly from the parent policy</span></span>  
  
- <span data-ttu-id="ed508-105">调用帮助程序.NET 组件的方法包装**Policy.Execute**从父策略的方法</span><span class="sxs-lookup"><span data-stu-id="ed508-105">Calling a method of a helper .NET component that wraps the **Policy.Execute** method from the parent policy</span></span>  
  
  <span data-ttu-id="ed508-106">使用第二种方法的优点是，您可以添加预处理和后处理代码**Policy.Execute**方法。</span><span class="sxs-lookup"><span data-stu-id="ed508-106">The advantage of using the second method is that you can add pre-processing and post-processing code to the **Policy.Execute** method.</span></span> <span data-ttu-id="ed508-107">例如，您可以在此包装程序方法中创建子策略所需的任何事实。</span><span class="sxs-lookup"><span data-stu-id="ed508-107">For example, you can create any facts required from the child policy in this wrapper method.</span></span> <span data-ttu-id="ed508-108">下面几部分将为每个方法提供一个示例。</span><span class="sxs-lookup"><span data-stu-id="ed508-108">The following sections provide an example for each method.</span></span>  
  
## <a name="invoking-the-policyexecute-method-directly-from-the-parent-policy"></a><span data-ttu-id="ed508-109">直接从父策略调用 Policy.Execute 方法</span><span class="sxs-lookup"><span data-stu-id="ed508-109">Invoking the Policy.Execute Method Directly from the Parent Policy</span></span>  
 <span data-ttu-id="ed508-110">本部分介绍通过使用调用子策略从父策略的高级步骤**Policy.Execute**直接方法。</span><span class="sxs-lookup"><span data-stu-id="ed508-110">This section presents the high-level steps to invoke the child policy from the parent policy by using the **Policy.Execute** method directly.</span></span>  
  
### <a name="adding-the-policyexecute-action-to-the-parent-policy"></a><span data-ttu-id="ed508-111">向父策略添加 Policy.Execute 操作</span><span class="sxs-lookup"><span data-stu-id="ed508-111">Adding the Policy.Execute Action to the Parent Policy</span></span>  
 <span data-ttu-id="ed508-112">以下过程包含添加的步骤**Policy.Execute**方法作为操作保存到父策略，将 XML 文档作为事实传递到子策略。</span><span class="sxs-lookup"><span data-stu-id="ed508-112">The following procedure has steps to add the **Policy.Execute** method as an action to the parent policy that passes an XML document as a fact to the child policy.</span></span>  
  
##### <a name="to-add-the-policyexecute-method-as-an-action-to-a-policy"></a><span data-ttu-id="ed508-113">将 Policy.Execute 方法作为操作添加到某一策略</span><span class="sxs-lookup"><span data-stu-id="ed508-113">To add the Policy.Execute method as an action to a policy</span></span>  
  
1.  <span data-ttu-id="ed508-114">在事实浏览器窗口中，单击 **.NET 类**选项卡。</span><span class="sxs-lookup"><span data-stu-id="ed508-114">In the Facts Explorer window, click the **.NET Classes** tab.</span></span>  
  
2.  <span data-ttu-id="ed508-115">右键单击 **.NET 程序集**，然后单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="ed508-115">Right-click **.NET Assemblies**, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="ed508-116">选择**Microsoft.RuleEngine**从 **.NET 程序集**列表，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ed508-116">Select **Microsoft.RuleEngine** from the **.NET Assemblies** list, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="ed508-117">展开**策略**。</span><span class="sxs-lookup"><span data-stu-id="ed508-117">Expand **Policy**.</span></span>  
  
5.  <span data-ttu-id="ed508-118">拖动**Execute (Object facts)** 或**Execute （Object facts，IRuleSetTrackingInterceptor trackingInterceptor）** 到那么窗格。</span><span class="sxs-lookup"><span data-stu-id="ed508-118">Drag **Execute(Object facts)** or **Execute(Object facts, IRuleSetTrackingInterceptor trackingInterceptor)** to the THEN pane.</span></span>  
  
6.  <span data-ttu-id="ed508-119">单击**XML 架构**节点。</span><span class="sxs-lookup"><span data-stu-id="ed508-119">Click the **XML Schemas** node.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ed508-120">在此示例方案中，将作为事实提交到父策略的 XML 文档作为事实传递到子策略。</span><span class="sxs-lookup"><span data-stu-id="ed508-120">In this sample scenario, an XML document that is submitted as a fact to the parent policy is passed as a fact to the child policy.</span></span> <span data-ttu-id="ed508-121">您可以调用为子策略创建事实的 .NET 方法。</span><span class="sxs-lookup"><span data-stu-id="ed508-121">Instead, you can invoke a .NET method that creates the facts for the child policy.</span></span>  
  
7.  <span data-ttu-id="ed508-122">右键单击**架构**，然后单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="ed508-122">Right-click **Schemas**, and then click **Browse**.</span></span>  
  
8.  <span data-ttu-id="ed508-123">选择你想要将作为事实传递，然后单击 XML 文档的架构**打开**。</span><span class="sxs-lookup"><span data-stu-id="ed508-123">Select the schema for the XML document you want to pass as a fact, and then click **Open**.</span></span>  
  
9. <span data-ttu-id="ed508-124">拖动*\<架构名称\>* 的第一个参数为.xsd **Policy.Execute**方法将传递到子策略事实作为传递到父策略的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="ed508-124">Drag *\<Schema name\>*.xsd to the first argument of the **Policy.Execute** method to pass the XML document that is passed to the parent policy as a fact to the child policy.</span></span>  
  
10. <span data-ttu-id="ed508-125">如果您使用**Execute**方法不采用**IRuleSetTrackingInterceptor**作为第二个参数，请跳过以下步骤。</span><span class="sxs-lookup"><span data-stu-id="ed508-125">If you use the **Execute** method that does not take the **IRuleSetTrackingInterceptor** as the second argument, skip the following steps.</span></span>  
  
11. <span data-ttu-id="ed508-126">单击 **.NET 类**选项卡。</span><span class="sxs-lookup"><span data-stu-id="ed508-126">Click the **.NET Classes** tab.</span></span>  
  
12. <span data-ttu-id="ed508-127">拖动**DebugTrackingInterceptor**中**Microsoft.RuleEngine**到的第二个参数**Policy.Execute**方法。</span><span class="sxs-lookup"><span data-stu-id="ed508-127">Drag **DebugTrackingInterceptor** in **Microsoft.RuleEngine** to the second argument of the **Policy.Execute** method.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ed508-128">如果你执行此操作，客户端必须传递的实例**DebugTrackingInterceptor**类作为事实到父策略，再将该实例作为事实传递到子策略。</span><span class="sxs-lookup"><span data-stu-id="ed508-128">If you perform this action, the client must pass an instance of the **DebugTrackingInterceptor** class as a fact to the parent policy, which in turn passes the instance as a fact to the child policy.</span></span> <span data-ttu-id="ed508-129">您可以拖动的构造函数**DebugTrackingInterceptor**类，以便为你自动创建该实例。</span><span class="sxs-lookup"><span data-stu-id="ed508-129">Instead you could drag the constructor of the **DebugTrackingInterceptor** class so that the instance is automatically created for you.</span></span>  
  
### <a name="modifying-the-client-application-that-invokes-the-parent-policy"></a><span data-ttu-id="ed508-130">修改调用父策略的客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="ed508-130">Modifying the Client Application that Invokes the Parent Policy</span></span>  
 <span data-ttu-id="ed508-131">调用父策略的客户端创建的实例**策略**类子策略名称作为参数并将其作为事实传递到父策略与其他事实一起。</span><span class="sxs-lookup"><span data-stu-id="ed508-131">The client that invokes the parent policy creates an instance of the **Policy** class with the child policy name as a parameter and passes it as a fact to the parent policy along with other facts.</span></span> <span data-ttu-id="ed508-132">下列示例代码阐释了这一操作：</span><span class="sxs-lookup"><span data-stu-id="ed508-132">The following sample code illustrates this action:</span></span>  
  
```  
DebugTrackingInterceptor dti = new DebugTrackingInterceptor("PolicyTracking.txt");  
Policy policy = new Policy("ParentPolicy");  
object[] facts = new object[3];  
facts[0] = txd;  
facts[1] = new Policy("ChildPolicy");  
facts[2] = new DebugTrackingInterceptor("PolicyTracking2.txt");  
policy.Execute(facts, dti);  
policy.Dispose();  
```  
  
 <span data-ttu-id="ed508-133">如果客户端是 BizTalk 业务流程，可能需要放置代码以创建事实**表达式**形状，然后事实作为参数传递给**调用规则**形状。</span><span class="sxs-lookup"><span data-stu-id="ed508-133">If the client is a BizTalk orchestration, you may need to place the code to create facts in an **Expression** shape, and then pass the facts as parameters to the **Call Rules** shape.</span></span>  
  
## <a name="invoking-a-net-wrapper-method-from-the-parent-policy"></a><span data-ttu-id="ed508-134">从父策略调用 .NET 包装程序方法</span><span class="sxs-lookup"><span data-stu-id="ed508-134">Invoking a .NET Wrapper Method from the Parent Policy</span></span>  
 <span data-ttu-id="ed508-135">本部分介绍调用包装到调用的.NET 方法的概要步骤**Policy.Execute**从父策略的方法。</span><span class="sxs-lookup"><span data-stu-id="ed508-135">This section presents the high-level steps to invoke a .NET method that wraps the call to the **Policy.Execute** method from the parent policy.</span></span>  
  
### <a name="creating-the-utility-net-class"></a><span data-ttu-id="ed508-136">创建实用程序 .NET 类</span><span class="sxs-lookup"><span data-stu-id="ed508-136">Creating the Utility .NET Class</span></span>  
  
##### <a name="to-create-the-utility-class"></a><span data-ttu-id="ed508-137">创建实用程序类</span><span class="sxs-lookup"><span data-stu-id="ed508-137">To create the utility class</span></span>  
  
1.  <span data-ttu-id="ed508-138">创建一个 .NET 类库项目，然后向该项目添加某一类。</span><span class="sxs-lookup"><span data-stu-id="ed508-138">Create a .NET class library project, and then add a class to the project.</span></span>  
  
2.  <span data-ttu-id="ed508-139">调用的静态方法添加**Policy.Execute**方法调用策略的名称作为参数进行传递，如下面的示例代码中所示：</span><span class="sxs-lookup"><span data-stu-id="ed508-139">Add a static method that calls the **Policy.Execute** method to invoke the policy whose name is passed as a parameter, as shown in the following sample code:</span></span>  
  
    ```  
    public static void Execute(string policyName, TypedXmlDocument txd)  
    {  
        DebugTrackingInterceptor dti = new   DebugTrackingInterceptor("PolicyTracking.txt");  
        Policy policy = new Policy("ParentPolicy");  
        object[] facts = new object[3];  
        facts[0] = txd;  
        facts[1] = new Policy("ChildPolicy");  
        facts[2] = new DebugTrackingInterceptor("PolicyTracking2.txt");  
        policy.Execute(facts, dti);  
        policy.Dispose();  
    }   
    ```  
  
3.  <span data-ttu-id="ed508-140">请确保**StaticSupport**注册表项设置为 1 或 2。</span><span class="sxs-lookup"><span data-stu-id="ed508-140">Make sure that the **StaticSupport** registry key is set to 1 or 2.</span></span> <span data-ttu-id="ed508-141">有关该注册表项的详细信息，请参阅[类的调用静态成员](../core/invoking-static-members-of-a-class.md)。</span><span class="sxs-lookup"><span data-stu-id="ed508-141">For more information about the registry key, see [Invoking Static Members of a Class](../core/invoking-static-members-of-a-class.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ed508-142">您可以使用某一实例方法来代替静态方法。</span><span class="sxs-lookup"><span data-stu-id="ed508-142">You can use an instance method instead of a static method.</span></span> <span data-ttu-id="ed508-143">请记住，如果您使用某一实例方法，则客户端必须将帮助程序 .NET 类的实例作为事实传递到父策略。</span><span class="sxs-lookup"><span data-stu-id="ed508-143">Remember that, if you use an instance method, the client must pass an instance of the helper .NET class as a fact to the parent policy.</span></span>  
  
### <a name="modifying-the-client-application"></a><span data-ttu-id="ed508-144">修改客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="ed508-144">Modifying the Client Application</span></span>  
 <span data-ttu-id="ed508-145">客户端调用父策略，并且父策略所调用的帮助程序方法将调用子策略。</span><span class="sxs-lookup"><span data-stu-id="ed508-145">The client invokes the parent policy, and the parent policy invokes the helper method that invokes the child policy.</span></span> <span data-ttu-id="ed508-146">该客户端的示例代码如下：</span><span class="sxs-lookup"><span data-stu-id="ed508-146">The sample code for the client is as follows:</span></span>  
  
```  
facts[0] = txd;  
facts[1] = new PolicyExecutor(txd);  
//call the first or parent policy  
Policy policy = new Policy(policyName);  
DebugTrackingInterceptor dti = new DebugTrackingInterceptor("PolicyTracking.txt");  
policy.Execute(facts, dti);  
policy.Dispose();  
```  
  
> [!NOTE]
>  <span data-ttu-id="ed508-147">如果该方法是一个实例方法，则客户端必须创建帮助程序 .NET 类的一个实例，并且将该实例作为事实传递到父策略。</span><span class="sxs-lookup"><span data-stu-id="ed508-147">If the method is an instance method, the client must create an instance of the helper .NET class, and pass it as a fact to the parent policy.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed508-148">如果客户端是 BizTalk 业务流程，可能需要放置代码以创建事实**表达式**形状，然后事实作为参数传递给**调用规则**形状。</span><span class="sxs-lookup"><span data-stu-id="ed508-148">If the client is a BizTalk orchestration, you may need to place the code to create facts in an **Expression** shape, and then pass the facts as parameters to the **Call Rules** shape.</span></span>