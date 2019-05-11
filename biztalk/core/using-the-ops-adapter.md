---
title: 使用 Ops 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IOpsAIC interface
- Ops adapters, configuring
- Ops adapters, IOpsAIC interface
- process management solution tutorial, Ops adapters
- Ops adapters, processing
ms.assetid: 331f3614-e00b-4587-b82b-3c7bc394f361
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b219d88ec07c63baf476cc3a3bf31775e03b2b4a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246429"
---
# <a name="using-the-ops-adapter"></a><span data-ttu-id="9953b-102">使用 Ops 适配器</span><span class="sxs-lookup"><span data-stu-id="9953b-102">Using the Ops Adapter</span></span>
<span data-ttu-id="9953b-103">业务流程管理解决方案使用 Ops 适配器来处理新的错误报告功能的错误报告。</span><span class="sxs-lookup"><span data-stu-id="9953b-103">The business process management solution uses the Ops adapter to handle error reports from the new error reporting feature.</span></span> <span data-ttu-id="9953b-104">不过，可以轻松地编写自己的并在其他解决方案中使用的适配器，该解决方案包含适配器，从示例处理程序处理消息。</span><span class="sxs-lookup"><span data-stu-id="9953b-104">The solution includes a sample handler to process messages from the adapter, although you can easily write your own and use the adapter in other solutions.</span></span> <span data-ttu-id="9953b-105">有关错误报告功能的信息，请参阅[使用失败消息路由](../core/using-failed-message-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="9953b-105">For information about the error reporting feature, see [Using Failed Message Routing](../core/using-failed-message-routing.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9953b-106">尽管该解决方案将适配器用于错误报告，但不限于错误处理其使用。</span><span class="sxs-lookup"><span data-stu-id="9953b-106">Although the solution uses the adapter for error reporting, its use is not limited to error handling.</span></span> <span data-ttu-id="9953b-107">只要您想要执行的特定对象方法以响应一条消息，可以使用各种环境中的适配器。</span><span class="sxs-lookup"><span data-stu-id="9953b-107">You can use the adapter in a variety of circumstances whenever you want to execute a specific object method in response to a message.</span></span>  
  
## <a name="how-the-ops-adapter-processes-error-reports"></a><span data-ttu-id="9953b-108">Ops 适配器如何处理错误报告</span><span class="sxs-lookup"><span data-stu-id="9953b-108">How the Ops Adapter Processes Error Reports</span></span>  
 <span data-ttu-id="9953b-109">在解决方案中使用错误报告的端口最终将发送到的错误消息**BIZTALKERRORS-SP**端口。</span><span class="sxs-lookup"><span data-stu-id="9953b-109">Ports in the solution that use error reporting ultimately send the error messages to the **BizTalkErrors-SP** port.</span></span> <span data-ttu-id="9953b-110">在端口上的筛选器测试是否存在**ErrorReport.ErrorType**上下文属性。</span><span class="sxs-lookup"><span data-stu-id="9953b-110">The filter on the port tests for the existence of the **ErrorReport.ErrorType** context property.</span></span> <span data-ttu-id="9953b-111">只有错误报告消息具有此上下文属性。</span><span class="sxs-lookup"><span data-stu-id="9953b-111">Only error report messages have this context property.</span></span>  
  
 <span data-ttu-id="9953b-112">**BIZTALKERRORS-SP**发送端口通过使用 XML 组装器组件将消息放在一个信封中的管道运行错误消息。</span><span class="sxs-lookup"><span data-stu-id="9953b-112">The **BizTalkErrors-SP** send port runs the error message through a pipeline that uses an XML assembler component to put the message in an envelope.</span></span> <span data-ttu-id="9953b-113">消息随后进入 Ops 适配器。</span><span class="sxs-lookup"><span data-stu-id="9953b-113">The message then goes to the Ops adapter.</span></span>  
  
 <span data-ttu-id="9953b-114">由 ErrorEnvelope 架构定义的信封被标记为接受任何类型的消息。</span><span class="sxs-lookup"><span data-stu-id="9953b-114">The envelope, defined by the ErrorEnvelope schema, is marked to accept any type of message.</span></span> <span data-ttu-id="9953b-115">但是，"任何"是指任何消息类型定义中的 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="9953b-115">However, "any" means any message type defined in the BizTalk group.</span></span> <span data-ttu-id="9953b-116">如果解决方案接收未知类型的消息，这可能会产生挂起的消息。</span><span class="sxs-lookup"><span data-stu-id="9953b-116">This can produce suspended messages if the solution receives a message of an unknown type.</span></span> <span data-ttu-id="9953b-117">此类消息将生成错误，并将路由到**BIZTALKERRORS-SP**端口。</span><span class="sxs-lookup"><span data-stu-id="9953b-117">Such a message would produce an error and would be routed to the **BizTalkErrors-SP** port.</span></span> <span data-ttu-id="9953b-118">反过来，消息会因为它不会已知的消息类型中管道的 XML 组装器组件中生成错误。</span><span class="sxs-lookup"><span data-stu-id="9953b-118">In turn, the message would generate an error in the XML assembler component of the pipeline because it would not be a known message type.</span></span> <span data-ttu-id="9953b-119">管道错误将挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="9953b-119">The pipeline error suspends the message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9953b-120">若要处理因未知的消息类型的路由错误，必须编写一个自定义管道组件，并使用自定义管道中的组件**BIZTALKERRORS-SP**端口。</span><span class="sxs-lookup"><span data-stu-id="9953b-120">To handle routing errors due to unknown message types, you must write a custom pipeline component and use the component in a custom pipeline for the **BizTalkErrors-SP** port.</span></span> <span data-ttu-id="9953b-121">自定义组件将替换 XML 组装器组件。</span><span class="sxs-lookup"><span data-stu-id="9953b-121">The custom component replaces the XML assembler component.</span></span> <span data-ttu-id="9953b-122">自定义组件必须放**ErrorReport**信封标头中的属性并将消息添加到信封的正文。</span><span class="sxs-lookup"><span data-stu-id="9953b-122">Your custom component must put the **ErrorReport** properties in the envelope header and add the message to the body of the envelope.</span></span>  
  
 <span data-ttu-id="9953b-123">Ops 适配器是事务性的单向发送适配器。</span><span class="sxs-lookup"><span data-stu-id="9953b-123">The Ops adapter is a transactional, one-way send adapter.</span></span> <span data-ttu-id="9953b-124">当适配器处理消息时，它首先加载指定的程序集，如有必要。</span><span class="sxs-lookup"><span data-stu-id="9953b-124">When the adapter processes a message, it first loads the specified assembly, if necessary.</span></span> <span data-ttu-id="9953b-125">适配器缓存在内存中程序集，以避免加载的程序集的每个调用的开销。</span><span class="sxs-lookup"><span data-stu-id="9953b-125">The adapter caches assemblies in memory to avoid the overhead of loading the assembly for each call.</span></span> <span data-ttu-id="9953b-126">它然后创建指定类的一个实例，然后使用反射来获取该对象中实现的程序集**IOpsAIC**接口。</span><span class="sxs-lookup"><span data-stu-id="9953b-126">It then creates an instance of the specified class, and then uses reflection to get the object in the assembly implementing the **IOpsAIC** interface.</span></span> <span data-ttu-id="9953b-127">如果所有这些都是成功，适配器调用**初始化**方法，然后调用**Execute**方法，传递错误报告消息。</span><span class="sxs-lookup"><span data-stu-id="9953b-127">If all of this is successful, the adapter calls the **Initialize** method and then calls the **Execute** method, passing the error report message.</span></span>  
  
 <span data-ttu-id="9953b-128">如果错误调用**Execute**，适配器重新提交消息。</span><span class="sxs-lookup"><span data-stu-id="9953b-128">If there is an error calling **Execute**, the adapter resubmits the message.</span></span> <span data-ttu-id="9953b-129">如果指定的类不实现**IOpsAIC**界面，或者类或程序集无法找到，则适配器将挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="9953b-129">If the specified class does not implement the **IOpsAIC** interface, or the class or assembly can't be found, the adapter suspends the message.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="9953b-130">因为适配器使用反射，所以包含类的程序集必须在全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="9953b-130">Because the adapter uses reflection, the assembly containing the class must be in the Global Assembly Cache (GAC).</span></span>  
  
## <a name="the-iopsaic-interface"></a><span data-ttu-id="9953b-131">IOpsAIC 接口</span><span class="sxs-lookup"><span data-stu-id="9953b-131">The IOpsAIC Interface</span></span>  
 <span data-ttu-id="9953b-132">适配器需要实现的对象**IOpsAIC**接口。</span><span class="sxs-lookup"><span data-stu-id="9953b-132">The adapter requires an object that implements the **IOpsAIC** interface.</span></span> <span data-ttu-id="9953b-133">该接口如下所示：</span><span class="sxs-lookup"><span data-stu-id="9953b-133">The interface appears as follows:</span></span>  
  
```  
interface IOpsAIC  
{  
    void Initialize(string config);  
    void Execute(byte[] message);  
}  
```  
  
 <span data-ttu-id="9953b-134">适配器将原始消息传递到字节数组的形式**Execute**方法。</span><span class="sxs-lookup"><span data-stu-id="9953b-134">The adapter passes the original message as a byte array to the **Execute** method.</span></span>  
  
## <a name="configuring-the-adapter"></a><span data-ttu-id="9953b-135">配置适配器</span><span class="sxs-lookup"><span data-stu-id="9953b-135">Configuring the Adapter</span></span>  
 <span data-ttu-id="9953b-136">就像任何其他适配器配置适配器。</span><span class="sxs-lookup"><span data-stu-id="9953b-136">You configure the adapter just as you would any other adapter.</span></span> <span data-ttu-id="9953b-137">下表描述了适配器的配置属性：</span><span class="sxs-lookup"><span data-stu-id="9953b-137">The following table describes the adapter's configuration properties:</span></span>  
  
|<span data-ttu-id="9953b-138">显示名称</span><span class="sxs-lookup"><span data-stu-id="9953b-138">Display Name</span></span>|<span data-ttu-id="9953b-139">Description</span><span class="sxs-lookup"><span data-stu-id="9953b-139">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="9953b-140">**.NET 程序集强名称**</span><span class="sxs-lookup"><span data-stu-id="9953b-140">**.NET Assembly Strong Name**</span></span>|<span data-ttu-id="9953b-141">程序集的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="9953b-141">The fully qualified name of the assembly.</span></span>|  
|<span data-ttu-id="9953b-142">**OpsAIC 类名**</span><span class="sxs-lookup"><span data-stu-id="9953b-142">**OpsAIC Class Name**</span></span>|<span data-ttu-id="9953b-143">类中实现的程序集的名称**IOpsAIC**接口。</span><span class="sxs-lookup"><span data-stu-id="9953b-143">The name of the class within the assembly that implements the **IOpsAIC** interface.</span></span>|  
|<span data-ttu-id="9953b-144">**初始化数据**</span><span class="sxs-lookup"><span data-stu-id="9953b-144">**Initialization Data**</span></span>|<span data-ttu-id="9953b-145">作为参数传递的字符串**初始化**类的方法。</span><span class="sxs-lookup"><span data-stu-id="9953b-145">A string passed as an argument to the **Initialize** method of the class.</span></span>|  
  
 <span data-ttu-id="9953b-146">请注意，适配器需要程序集的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="9953b-146">Notice that the adapter requires the fully qualified name of the assembly.</span></span> <span data-ttu-id="9953b-147">完全限定的名称是提供给程序集时将其添加到 gac 中的名称。</span><span class="sxs-lookup"><span data-stu-id="9953b-147">The fully qualified name is the name given to an assembly when you add it to the GAC.</span></span> <span data-ttu-id="9953b-148">完全限定的名称是包含程序集的名称、 版本、 区域性和公钥标记的字符串。</span><span class="sxs-lookup"><span data-stu-id="9953b-148">The fully qualified name is a string containing the assembly's name, version, culture, and public key token.</span></span> <span data-ttu-id="9953b-149">您可以看到程序集的完全限定的名称使用全局程序集缓存工具 gacutil.exe。</span><span class="sxs-lookup"><span data-stu-id="9953b-149">You can see the fully qualified names of assemblies by using the Global Assembly Cache Tool, gacutil.exe.</span></span>  
  
 <span data-ttu-id="9953b-150">有关完全限定的程序集名称的详细信息，请参阅.NET Framework 开发人员指南中的"程序集名称"。</span><span class="sxs-lookup"><span data-stu-id="9953b-150">For more information about fully qualified assembly names, see "Assembly Names" in the .NET Framework Developer's Guide.</span></span> <span data-ttu-id="9953b-151">有关 gacutil.exe 的详细信息，请参阅"全局程序集缓存工具 (Gacutil.exe)"中[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]开发人员指南。</span><span class="sxs-lookup"><span data-stu-id="9953b-151">For more information about gacutil.exe, see "Global Assembly Cache Tool (Gacutil.exe)" in the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Developer's Guide.</span></span>  
  
 <span data-ttu-id="9953b-152">必须将命名空间提供类名。</span><span class="sxs-lookup"><span data-stu-id="9953b-152">You must provide the namespace with the class name.</span></span> <span data-ttu-id="9953b-153">例如，如果此类是**OpsHandler**中**OperationsHandler**命名空间中，您将为类名作为**OperationsHandler.OpsHandler**。</span><span class="sxs-lookup"><span data-stu-id="9953b-153">For example, if the class is **OpsHandler** in the **OperationsHandler** namespace, you would give the class name as **OperationsHandler.OpsHandler**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9953b-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="9953b-154">See Also</span></span>  
 [<span data-ttu-id="9953b-155">Ops 适配器</span><span class="sxs-lookup"><span data-stu-id="9953b-155">The Ops Adapter</span></span>](../core/the-ops-adapter.md)