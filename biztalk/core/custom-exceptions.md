---
title: 自定义异常 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, compensation blocks
- compensation blocks, process management solutions
- process management solution tutorial, custom exceptions
- Terminate shape [Orchestration Designer], called orchestrations
- process management solution tutorial, errors
ms.assetid: 0c923303-82ad-4a20-9c7c-5e38c477993a
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfead2aadc237d27e0fb8ed28a776dd1e4f5c6f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240133"
---
# <a name="custom-exceptions"></a><span data-ttu-id="9937b-102">自定义异常</span><span class="sxs-lookup"><span data-stu-id="9937b-102">Custom Exceptions</span></span>
<span data-ttu-id="9937b-103">对于存在不可恢复的错误的情况，业务流程管理解决方案将组合使用异常处理程序和自定义异常。</span><span class="sxs-lookup"><span data-stu-id="9937b-103">For situations where there is an unrecoverable error, the Business Process Management solution uses a combination of exception handlers and custom exceptions.</span></span>  
  
## <a name="handling-exceptions"></a><span data-ttu-id="9937b-104">处理异常</span><span class="sxs-lookup"><span data-stu-id="9937b-104">Handling Exceptions</span></span>  
 <span data-ttu-id="9937b-105">而不是使用**终止**在调用业务流程中的形状可以使用引发由根业务流程处理的异常的模式。</span><span class="sxs-lookup"><span data-stu-id="9937b-105">Rather than using **Terminate** shapes in called orchestrations you can use the pattern of throwing exceptions that are handled by the root orchestration.</span></span> <span data-ttu-id="9937b-106">这样，就可以由对上下文了解最全面的业务流程来决定如何处理异常。</span><span class="sxs-lookup"><span data-stu-id="9937b-106">This allows the orchestration with the widest knowledge of context to make the decision about handling the exception.</span></span> <span data-ttu-id="9937b-107">通过让从属业务流程引发自定义异常，使您能够将更具体的信息传递给根业务流程。</span><span class="sxs-lookup"><span data-stu-id="9937b-107">Having the subordinate orchestrations throw custom exceptions enables you to communicate more specific information to the root orchestration.</span></span>  
  
 <span data-ttu-id="9937b-108">业务流程管理解决方案将使用此模式。</span><span class="sxs-lookup"><span data-stu-id="9937b-108">The business process management solution follows this pattern.</span></span> <span data-ttu-id="9937b-109">有四个根，或在解决方案中的使用未调用，业务流程： **OrderBroker**， **OrderManager**， **CableOrder1**，和**CableOrder2**.</span><span class="sxs-lookup"><span data-stu-id="9937b-109">There are four root, or uncalled, orchestrations in the solution: **OrderBroker**, **OrderManager**, **CableOrder1**, and **CableOrder2**.</span></span> <span data-ttu-id="9937b-110">三个根业务流程接收和处理自定义异常： **OrderManager**， **CableOrder1**，和**CableOrder2**。</span><span class="sxs-lookup"><span data-stu-id="9937b-110">Three of the root orchestrations receive and handle custom exceptions: **OrderManager**, **CableOrder1**, and **CableOrder2**.</span></span>  
  
 <span data-ttu-id="9937b-111">请注意，某些根业务流程使用**终止**形状，**终止**形状显示的业务流程正常的终结点之前。</span><span class="sxs-lookup"><span data-stu-id="9937b-111">Note that some of the root orchestrations use the **Terminate** shape and that the **Terminate** shape appears just before the normal end point of the orchestration.</span></span> <span data-ttu-id="9937b-112">业务流程仍使用**终止**调整发生错误时，以便业务流程被记录为终止，而不是为已完成，但并显示错误消息。</span><span class="sxs-lookup"><span data-stu-id="9937b-112">The orchestration still uses the **Terminate** shape in case of an error so that the orchestration is recorded as terminated, rather than as completed but with an error message.</span></span> <span data-ttu-id="9937b-113">这样，解决方案除了可以记录错误之外，还可以轻松跟踪失败的实例。</span><span class="sxs-lookup"><span data-stu-id="9937b-113">This allows the solution to track failed instances easily in addition to recording the error.</span></span>  
  
 <span data-ttu-id="9937b-114">有关详细信息**终止**形状，请参阅[如何配置终止形状](../core/how-to-configure-the-terminate-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="9937b-114">For more information about the **Terminate** shape, see [How to Configure the Terminate Shape](../core/how-to-configure-the-terminate-shape.md).</span></span> <span data-ttu-id="9937b-115">有关详细信息**ThrowException**形状，请参阅[如何配置引发异常形状](../core/how-to-configure-the-throw-exception-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="9937b-115">For more information about the **ThrowException** shape, see [How to Configure the Throw Exception Shape](../core/how-to-configure-the-throw-exception-shape.md).</span></span>  
  
## <a name="the-custom-exceptions"></a><span data-ttu-id="9937b-116">自定义异常</span><span class="sxs-lookup"><span data-stu-id="9937b-116">The Custom Exceptions</span></span>  
 <span data-ttu-id="9937b-117">以下三个自定义异常都使用相同的模式。</span><span class="sxs-lookup"><span data-stu-id="9937b-117">Each of the following three custom exceptions follows the same pattern.</span></span> <span data-ttu-id="9937b-118">使用不同类型是为了便于代码区分不同的异常。</span><span class="sxs-lookup"><span data-stu-id="9937b-118">Having distinct types allows the code to distinguish different exceptions.</span></span>  
  
|<span data-ttu-id="9937b-119">异常</span><span class="sxs-lookup"><span data-stu-id="9937b-119">Exception</span></span>|<span data-ttu-id="9937b-120">引发者（业务流程）</span><span class="sxs-lookup"><span data-stu-id="9937b-120">Thrown By (Orchestration)</span></span>|  
|---------------|---------------------------------|  
|<span data-ttu-id="9937b-121">**ActivateException**</span><span class="sxs-lookup"><span data-stu-id="9937b-121">**ActivateException**</span></span>|<span data-ttu-id="9937b-122">**更改**</span><span class="sxs-lookup"><span data-stu-id="9937b-122">**Change**</span></span>|  
|<span data-ttu-id="9937b-123">**CableOrderException**</span><span class="sxs-lookup"><span data-stu-id="9937b-123">**CableOrderException**</span></span>|<span data-ttu-id="9937b-124">**激活**， **CableOrder1**</span><span class="sxs-lookup"><span data-stu-id="9937b-124">**Activate**, **CableOrder1**</span></span>|  
|<span data-ttu-id="9937b-125">**InterruptException**</span><span class="sxs-lookup"><span data-stu-id="9937b-125">**InterruptException**</span></span>|<span data-ttu-id="9937b-126">**CableOrder1**， **CheckInterrupt**， **ErrorHandlerOrch**</span><span class="sxs-lookup"><span data-stu-id="9937b-126">**CableOrder1**, **CheckInterrupt**, **ErrorHandlerOrch**</span></span>|  
  
 <span data-ttu-id="9937b-127">在中定义的所有异常的自定义**实用工具**程序集。</span><span class="sxs-lookup"><span data-stu-id="9937b-127">All of the custom exceptions are defined in the **Utilities** assembly.</span></span> <span data-ttu-id="9937b-128">自定义异常全部都是 .NET 类。</span><span class="sxs-lookup"><span data-stu-id="9937b-128">The custom exceptions are all .NET classes.</span></span> <span data-ttu-id="9937b-129">从.NET 中的所有自定义异常类继承**ApplicationException**类又继承自**System.Exception**类。</span><span class="sxs-lookup"><span data-stu-id="9937b-129">All of the custom exception classes inherit from the .NET **ApplicationException** class which in turn inherits from the **System.Exception** class.</span></span> <span data-ttu-id="9937b-130">由于异常有可能被冻结（序列化并存储在数据库中），因此异常必须实现反序列化构造函数。</span><span class="sxs-lookup"><span data-stu-id="9937b-130">Because there is a possibility that the exception may be dehydrated (serialized and stored in the database), the exceptions must implement a deserialization constructor.</span></span> <span data-ttu-id="9937b-131">反序列化构造函数是采用两个参数的构造函数： 一个 SerializationInfo 和 StreamingContext 对象。</span><span class="sxs-lookup"><span data-stu-id="9937b-131">A deserialization constructor is a constructor that takes two arguments: a SerializationInfo object, and a StreamingContext object.</span></span> <span data-ttu-id="9937b-132">在解除异常冻结过程中，将使用反序列化构造函数。</span><span class="sxs-lookup"><span data-stu-id="9937b-132">The deserialization constructor will be used during rehydration of the exception.</span></span> <span data-ttu-id="9937b-133">因为**ApplicationException**类已经实现反序列化构造函数，自定义异常的构造函数只是调用基 (ApplicationException) 反序列化构造函数。</span><span class="sxs-lookup"><span data-stu-id="9937b-133">Because the **ApplicationException** class already implements a deserialization constructor, the constructor for the custom exception simply invokes the base (ApplicationException) deserialization constructor.</span></span> <span data-ttu-id="9937b-134">例如， **InterruptException**包括以下构造函数：</span><span class="sxs-lookup"><span data-stu-id="9937b-134">For example, the **InterruptException** includes the following constructor:</span></span>  
  
```  
// "info" is the object holding the serialized object data.  
// "context" is the contextual information about the source  
// or destination.  
public InterruptException(SerializationInfo info,  
                  StreamingContext context) : base(info, context) { }  
```  
  
 <span data-ttu-id="9937b-135">有关自定义序列化的详细信息，请参阅 [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] 开发人员指南中的“自定义序列化”。</span><span class="sxs-lookup"><span data-stu-id="9937b-135">For more detailed information about custom serialization, see Custom Serialization in the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Developer's Guide.</span></span>  
  
## <a name="nested-exception-handlers-and-compensation-blocks"></a><span data-ttu-id="9937b-136">嵌套异常处理程序和补偿模块</span><span class="sxs-lookup"><span data-stu-id="9937b-136">Nested Exception Handlers and Compensation Blocks</span></span>  
 <span data-ttu-id="9937b-137">除了充当特殊异常之外，一些位置的自定义异常还充当排序标志。</span><span class="sxs-lookup"><span data-stu-id="9937b-137">In addition to serving as specialized exceptions, the custom exceptions in several places also serve as a sort flag.</span></span> <span data-ttu-id="9937b-138">在**更改**业务流程，取消操作必须回滚的两个地方。</span><span class="sxs-lookup"><span data-stu-id="9937b-138">In the **Change** orchestration, there are two places that the Cancel operation must be rolled back.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9937b-139">你可能想要读取此节**更改**业务流程在 Visual Studio 中打开。</span><span class="sxs-lookup"><span data-stu-id="9937b-139">You may want to read this section with the **Change** orchestration open in Visual Studio.</span></span>  
  
 <span data-ttu-id="9937b-140">顶部的业务流程，如果调用**取消**业务流程失败， **CancelCompensation**块执行，并回滚**取消**事务。</span><span class="sxs-lookup"><span data-stu-id="9937b-140">At the top of the orchestration, if the call to the **Cancel** orchestration fails, the **CancelCompensation** block executes and rolls back the **Cancel** transaction.</span></span> <span data-ttu-id="9937b-141">如果一切运行正常，然后，业务流程将调用**激活**业务流程。</span><span class="sxs-lookup"><span data-stu-id="9937b-141">If all goes well, the orchestration then calls the **Activate** orchestration.</span></span>  
  
 <span data-ttu-id="9937b-142">如果**激活**操作失败，**取消**事务必须也被回滚。</span><span class="sxs-lookup"><span data-stu-id="9937b-142">If the **Activate** operation fails, the **Cancel** transaction must also be rolled back.</span></span> <span data-ttu-id="9937b-143">但是，异常处理程序调用**激活**不知道有关**取消**事务。</span><span class="sxs-lookup"><span data-stu-id="9937b-143">However, the exception handler for the call to **Activate** knows nothing about the **Cancel** transaction.</span></span> <span data-ttu-id="9937b-144">为了处理这种情况，提供了一个针对整个业务流程的异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="9937b-144">To handle this, there is an exception handler for the entire orchestration.</span></span> <span data-ttu-id="9937b-145">此处理程序，因为它包含**取消**范围，就会了解有关**取消**事务。</span><span class="sxs-lookup"><span data-stu-id="9937b-145">This handler, because it contains the **Cancel** scope, knows about the **Cancel** transaction.</span></span> <span data-ttu-id="9937b-146">处理程序捕获异常从引发**激活**作用域 ( **ActivateException**)，回滚**取消**事务，然后再次引发异常和以便调用的业务流程的**更改**业务流程可以执行任何其他处理。</span><span class="sxs-lookup"><span data-stu-id="9937b-146">The handler catches the exception thrown from the **Activate** scope (the **ActivateException**), rolls back the **Cancel** transaction, and then throws the exception again so that the orchestration that called the **Change** orchestration can perform any additional processing.</span></span>  
  
 <span data-ttu-id="9937b-147">请注意，此设计仅补偿**取消**如果**激活**失败。</span><span class="sxs-lookup"><span data-stu-id="9937b-147">Notice that this design only compensates the **Cancel** if the **Activate** fails.</span></span> <span data-ttu-id="9937b-148">如果**取消**失败并引发异常，**取消**永远不会发生的时间和不应进行补偿。</span><span class="sxs-lookup"><span data-stu-id="9937b-148">If the **Cancel** fails and throws an exception, the **Cancel** never took place and should not be compensated.</span></span>  
  
 <span data-ttu-id="9937b-149">有关补偿基块的详细信息和**Compensate**形状，请参阅[如何配置补偿形状](../core/how-to-configure-the-compensate-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="9937b-149">For more information about compensation blocks and the **Compensate** shape, see [How to Configure the Compensate Shape](../core/how-to-configure-the-compensate-shape.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9937b-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9937b-150">See Also</span></span>  
 <span data-ttu-id="9937b-151">[业务流程管理解决方案中的异常处理](../core/exception-handling-in-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="9937b-151">[Exception Handling in the Business Process Management Solution](../core/exception-handling-in-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="9937b-152">ExceptionHandler 业务流程</span><span class="sxs-lookup"><span data-stu-id="9937b-152">The ExceptionHandler Orchestration</span></span>](../core/the-exceptionhandler-orchestration.md)