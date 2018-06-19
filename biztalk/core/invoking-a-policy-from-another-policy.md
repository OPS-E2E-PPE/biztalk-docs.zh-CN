---
title: 调用来自另一个策略的策略 |Microsoft 文档
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
ms.openlocfilehash: ac45c31ef76213e79249e96fe645ecbb5fb66ed4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973555"
---
# <a name="invoking-a-policy-from-another-policy"></a><span data-ttu-id="95309-102">从其他策略调用策略</span><span class="sxs-lookup"><span data-stu-id="95309-102">Invoking a Policy from Another Policy</span></span>
<span data-ttu-id="95309-103">您可以通过使用以下方式之一从其他策略（父策略）调用策略（子策略）：</span><span class="sxs-lookup"><span data-stu-id="95309-103">You can invoke a policy (child) from another policy (parent) by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="95309-104">调用**Policy.Execute**直接从父策略的方法</span><span class="sxs-lookup"><span data-stu-id="95309-104">Calling the **Policy.Execute** method directly from the parent policy</span></span>  
  
-   <span data-ttu-id="95309-105">调用的方法的帮助程序.NET 组件包装**Policy.Execute**从父策略的方法</span><span class="sxs-lookup"><span data-stu-id="95309-105">Calling a method of a helper .NET component that wraps the **Policy.Execute** method from the parent policy</span></span>  
  
 <span data-ttu-id="95309-106">使用第二种方法的优点是，你可以预先处理和后续处理将代码添加到**Policy.Execute**方法。</span><span class="sxs-lookup"><span data-stu-id="95309-106">The advantage of using the second method is that you can add pre-processing and post-processing code to the **Policy.Execute** method.</span></span> <span data-ttu-id="95309-107">例如，您可以在此包装程序方法中创建子策略所需的任何事实。</span><span class="sxs-lookup"><span data-stu-id="95309-107">For example, you can create any facts required from the child policy in this wrapper method.</span></span> <span data-ttu-id="95309-108">下面几部分将为每个方法提供一个示例。</span><span class="sxs-lookup"><span data-stu-id="95309-108">The following sections provide an example for each method.</span></span>  
  
## <a name="invoking-the-policyexecute-method-directly-from-the-parent-policy"></a><span data-ttu-id="95309-109">直接从父策略调用 Policy.Execute 方法</span><span class="sxs-lookup"><span data-stu-id="95309-109">Invoking the Policy.Execute Method Directly from the Parent Policy</span></span>  
 <span data-ttu-id="95309-110">本节提供使用调用的子策略与父策略的高级步骤**Policy.Execute**直接的方法。</span><span class="sxs-lookup"><span data-stu-id="95309-110">This section presents the high-level steps to invoke the child policy from the parent policy by using the **Policy.Execute** method directly.</span></span>  
  
### <a name="adding-the-policyexecute-action-to-the-parent-policy"></a><span data-ttu-id="95309-111">向父策略添加 Policy.Execute 操作</span><span class="sxs-lookup"><span data-stu-id="95309-111">Adding the Policy.Execute Action to the Parent Policy</span></span>  
 <span data-ttu-id="95309-112">以下过程包含的步骤可添加**Policy.Execute**用作一项操作的将与的事实数据的 XML 文档传递给子策略的父策略的方法。</span><span class="sxs-lookup"><span data-stu-id="95309-112">The following procedure has steps to add the **Policy.Execute** method as an action to the parent policy that passes an XML document as a fact to the child policy.</span></span>  
  
##### <a name="to-add-the-policyexecute-method-as-an-action-to-a-policy"></a><span data-ttu-id="95309-113">将 Policy.Execute 方法作为操作添加到某一策略</span><span class="sxs-lookup"><span data-stu-id="95309-113">To add the Policy.Execute method as an action to a policy</span></span>  
  
1.  <span data-ttu-id="95309-114">在事实浏览器窗口中，单击 **.NET 类**选项卡。</span><span class="sxs-lookup"><span data-stu-id="95309-114">In the Facts Explorer window, click the **.NET Classes** tab.</span></span>  
  
2.  <span data-ttu-id="95309-115">右键单击 **.NET 程序集**，然后单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="95309-115">Right-click **.NET Assemblies**, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="95309-116">选择**Microsoft.RuleEngine**从 **.NET 程序集**列表，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="95309-116">Select **Microsoft.RuleEngine** from the **.NET Assemblies** list, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="95309-117">展开**策略**。</span><span class="sxs-lookup"><span data-stu-id="95309-117">Expand **Policy**.</span></span>  
  
5.  <span data-ttu-id="95309-118">拖动**Execute （对象事实）** 或**Execute （对象事实，IRuleSetTrackingInterceptor trackingInterceptor）** 到然后窗格。</span><span class="sxs-lookup"><span data-stu-id="95309-118">Drag **Execute(Object facts)** or **Execute(Object facts, IRuleSetTrackingInterceptor trackingInterceptor)** to the THEN pane.</span></span>  
  
6.  <span data-ttu-id="95309-119">单击**XML 架构**节点。</span><span class="sxs-lookup"><span data-stu-id="95309-119">Click the **XML Schemas** node.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95309-120">在此示例方案中，将作为事实提交到父策略的 XML 文档作为事实传递到子策略。</span><span class="sxs-lookup"><span data-stu-id="95309-120">In this sample scenario, an XML document that is submitted as a fact to the parent policy is passed as a fact to the child policy.</span></span> <span data-ttu-id="95309-121">您可以调用为子策略创建事实的 .NET 方法。</span><span class="sxs-lookup"><span data-stu-id="95309-121">Instead, you can invoke a .NET method that creates the facts for the child policy.</span></span>  
  
7.  <span data-ttu-id="95309-122">右键单击**架构**，然后单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="95309-122">Right-click **Schemas**, and then click **Browse**.</span></span>  
  
8.  <span data-ttu-id="95309-123">选择你想要将一个事实中，作为传递，然后单击的 XML 文档的架构**打开**。</span><span class="sxs-lookup"><span data-stu-id="95309-123">Select the schema for the XML document you want to pass as a fact, and then click **Open**.</span></span>  
  
9. <span data-ttu-id="95309-124">拖动*\<架构名称\>* 到的第一个参数的.xsd **Policy.Execute**方法可以传递到子策略事实作为传递到父策略的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="95309-124">Drag *\<Schema name\>*.xsd to the first argument of the **Policy.Execute** method to pass the XML document that is passed to the parent policy as a fact to the child policy.</span></span>  
  
10. <span data-ttu-id="95309-125">如果你使用**执行**方法不采用**IRuleSetTrackingInterceptor**作为第二个自变量，跳过以下步骤。</span><span class="sxs-lookup"><span data-stu-id="95309-125">If you use the **Execute** method that does not take the **IRuleSetTrackingInterceptor** as the second argument, skip the following steps.</span></span>  
  
11. <span data-ttu-id="95309-126">单击 **.NET 类**选项卡。</span><span class="sxs-lookup"><span data-stu-id="95309-126">Click the **.NET Classes** tab.</span></span>  
  
12. <span data-ttu-id="95309-127">拖动**DebugTrackingInterceptor**中**Microsoft.RuleEngine**到的第二个参数**Policy.Execute**方法。</span><span class="sxs-lookup"><span data-stu-id="95309-127">Drag **DebugTrackingInterceptor** in **Microsoft.RuleEngine** to the second argument of the **Policy.Execute** method.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95309-128">如果你执行此操作，客户端必须传递的实例**DebugTrackingInterceptor**与父策略，这反过来将与的事实数据的实例传递给子策略的事实数据的类。</span><span class="sxs-lookup"><span data-stu-id="95309-128">If you perform this action, the client must pass an instance of the **DebugTrackingInterceptor** class as a fact to the parent policy, which in turn passes the instance as a fact to the child policy.</span></span> <span data-ttu-id="95309-129">而是可以拖动的构造函数**DebugTrackingInterceptor**类，以便为你自动创建的实例。</span><span class="sxs-lookup"><span data-stu-id="95309-129">Instead you could drag the constructor of the **DebugTrackingInterceptor** class so that the instance is automatically created for you.</span></span>  
  
### <a name="modifying-the-client-application-that-invokes-the-parent-policy"></a><span data-ttu-id="95309-130">修改调用父策略的客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="95309-130">Modifying the Client Application that Invokes the Parent Policy</span></span>  
 <span data-ttu-id="95309-131">调用父策略的客户端创建的实例**策略**类子策略名称作为参数并将其与的事实数据传递到父策略以及其他事实。</span><span class="sxs-lookup"><span data-stu-id="95309-131">The client that invokes the parent policy creates an instance of the **Policy** class with the child policy name as a parameter and passes it as a fact to the parent policy along with other facts.</span></span> <span data-ttu-id="95309-132">下列示例代码阐释了这一操作：</span><span class="sxs-lookup"><span data-stu-id="95309-132">The following sample code illustrates this action:</span></span>  
  
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
  
 <span data-ttu-id="95309-133">如果客户端是 BizTalk 业务流程，则可能需要将代码以创建在事实**表达式**调整，然后事实数据作为参数传递给**调用规则**形状。</span><span class="sxs-lookup"><span data-stu-id="95309-133">If the client is a BizTalk orchestration, you may need to place the code to create facts in an **Expression** shape, and then pass the facts as parameters to the **Call Rules** shape.</span></span>  
  
## <a name="invoking-a-net-wrapper-method-from-the-parent-policy"></a><span data-ttu-id="95309-134">从父策略调用 .NET 包装程序方法</span><span class="sxs-lookup"><span data-stu-id="95309-134">Invoking a .NET Wrapper Method from the Parent Policy</span></span>  
 <span data-ttu-id="95309-135">本节提供的高级步骤来调用包装到调用.NET 方法**Policy.Execute**从父策略的方法。</span><span class="sxs-lookup"><span data-stu-id="95309-135">This section presents the high-level steps to invoke a .NET method that wraps the call to the **Policy.Execute** method from the parent policy.</span></span>  
  
### <a name="creating-the-utility-net-class"></a><span data-ttu-id="95309-136">创建实用程序 .NET 类</span><span class="sxs-lookup"><span data-stu-id="95309-136">Creating the Utility .NET Class</span></span>  
  
##### <a name="to-create-the-utility-class"></a><span data-ttu-id="95309-137">创建实用程序类</span><span class="sxs-lookup"><span data-stu-id="95309-137">To create the utility class</span></span>  
  
1.  <span data-ttu-id="95309-138">创建一个 .NET 类库项目，然后向该项目添加某一类。</span><span class="sxs-lookup"><span data-stu-id="95309-138">Create a .NET class library project, and then add a class to the project.</span></span>  
  
2.  <span data-ttu-id="95309-139">添加一个静态方法来调用**Policy.Execute**方法来调用该策略，其名称作为参数进行传递，如下面的示例代码中所示：</span><span class="sxs-lookup"><span data-stu-id="95309-139">Add a static method that calls the **Policy.Execute** method to invoke the policy whose name is passed as a parameter, as shown in the following sample code:</span></span>  
  
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
  
3.  <span data-ttu-id="95309-140">请确保**StaticSupport**注册表项设置为 1 或 2。</span><span class="sxs-lookup"><span data-stu-id="95309-140">Make sure that the **StaticSupport** registry key is set to 1 or 2.</span></span> <span data-ttu-id="95309-141">有关该注册表项的详细信息，请参阅[调用的类的静态成员](../core/invoking-static-members-of-a-class.md)。</span><span class="sxs-lookup"><span data-stu-id="95309-141">For more information about the registry key, see [Invoking Static Members of a Class](../core/invoking-static-members-of-a-class.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95309-142">您可以使用某一实例方法来代替静态方法。</span><span class="sxs-lookup"><span data-stu-id="95309-142">You can use an instance method instead of a static method.</span></span> <span data-ttu-id="95309-143">请记住，如果您使用某一实例方法，则客户端必须将帮助程序 .NET 类的实例作为事实传递到父策略。</span><span class="sxs-lookup"><span data-stu-id="95309-143">Remember that, if you use an instance method, the client must pass an instance of the helper .NET class as a fact to the parent policy.</span></span>  
  
### <a name="modifying-the-client-application"></a><span data-ttu-id="95309-144">修改客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="95309-144">Modifying the Client Application</span></span>  
 <span data-ttu-id="95309-145">客户端调用父策略，并且父策略所调用的帮助程序方法将调用子策略。</span><span class="sxs-lookup"><span data-stu-id="95309-145">The client invokes the parent policy, and the parent policy invokes the helper method that invokes the child policy.</span></span> <span data-ttu-id="95309-146">该客户端的示例代码如下：</span><span class="sxs-lookup"><span data-stu-id="95309-146">The sample code for the client is as follows:</span></span>  
  
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
>  <span data-ttu-id="95309-147">如果该方法是一个实例方法，则客户端必须创建帮助程序 .NET 类的一个实例，并且将该实例作为事实传递到父策略。</span><span class="sxs-lookup"><span data-stu-id="95309-147">If the method is an instance method, the client must create an instance of the helper .NET class, and pass it as a fact to the parent policy.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95309-148">如果客户端是 BizTalk 业务流程，则可能需要将代码以创建在事实**表达式**调整，然后事实数据作为参数传递给**调用规则**形状。</span><span class="sxs-lookup"><span data-stu-id="95309-148">If the client is a BizTalk orchestration, you may need to place the code to create facts in an **Expression** shape, and then pass the facts as parameters to the **Call Rules** shape.</span></span>