---
title: 自定义异常 |Microsoft Docs
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
ms.openlocfilehash: 5118de4dc75d65f328838d9e7cecf4d51875db1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353398"
---
# <a name="custom-exceptions"></a><span data-ttu-id="5c3ab-102">自定义异常</span><span class="sxs-lookup"><span data-stu-id="5c3ab-102">Custom Exceptions</span></span>
<span data-ttu-id="5c3ab-103">情况下业务流程管理解决方案对于不可恢复的错误情况，使用异常处理程序和自定义异常的组合。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-103">For situations where there is an unrecoverable error, the Business Process Management solution uses a combination of exception handlers and custom exceptions.</span></span>  
  
## <a name="handling-exceptions"></a><span data-ttu-id="5c3ab-104">处理异常</span><span class="sxs-lookup"><span data-stu-id="5c3ab-104">Handling Exceptions</span></span>  
 <span data-ttu-id="5c3ab-105">而不是使用**Terminate**中调用的业务流程形状可以使用引发由根业务流程处理的异常的模式。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-105">Rather than using **Terminate** shapes in called orchestrations you can use the pattern of throwing exceptions that are handled by the root orchestration.</span></span> <span data-ttu-id="5c3ab-106">这允许上下文来决定如何处理异常的业务流程与尽可能最广泛的知识。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-106">This allows the orchestration with the widest knowledge of context to make the decision about handling the exception.</span></span> <span data-ttu-id="5c3ab-107">具有从属业务流程引发自定义异常，可更具体的信息传递给根业务流程。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-107">Having the subordinate orchestrations throw custom exceptions enables you to communicate more specific information to the root orchestration.</span></span>  
  
 <span data-ttu-id="5c3ab-108">业务流程管理解决方案采用这种模式。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-108">The business process management solution follows this pattern.</span></span> <span data-ttu-id="5c3ab-109">有四个根，或在解决方案中的使用未调用，业务流程：**OrderBroker**， **OrderManager**， **CableOrder1**，并且**CableOrder2**。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-109">There are four root, or uncalled, orchestrations in the solution: **OrderBroker**, **OrderManager**, **CableOrder1**, and **CableOrder2**.</span></span> <span data-ttu-id="5c3ab-110">三个根业务流程接收和处理自定义异常：**OrderManager**， **CableOrder1**，和**CableOrder2**。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-110">Three of the root orchestrations receive and handle custom exceptions: **OrderManager**, **CableOrder1**, and **CableOrder2**.</span></span>  
  
 <span data-ttu-id="5c3ab-111">请注意，某些根业务流程使用**Terminate**形状和该**终止**形状就显示业务流程的正常的终结点之前。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-111">Note that some of the root orchestrations use the **Terminate** shape and that the **Terminate** shape appears just before the normal end point of the orchestration.</span></span> <span data-ttu-id="5c3ab-112">该业务流程仍使用**Terminate**形状发生错误时，以便该业务流程记录为已终止，而不是已完成但有一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-112">The orchestration still uses the **Terminate** shape in case of an error so that the orchestration is recorded as terminated, rather than as completed but with an error message.</span></span> <span data-ttu-id="5c3ab-113">这样，解决方案后，以跟踪轻松除了将错误记录的失败的实例。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-113">This allows the solution to track failed instances easily in addition to recording the error.</span></span>  
  
 <span data-ttu-id="5c3ab-114">有关详细信息**Terminate**形状中，请参阅[如何配置终止形状](../core/how-to-configure-the-terminate-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-114">For more information about the **Terminate** shape, see [How to Configure the Terminate Shape](../core/how-to-configure-the-terminate-shape.md).</span></span> <span data-ttu-id="5c3ab-115">有关详细信息**ThrowException**形状中，请参阅[如何配置引发异常形状](../core/how-to-configure-the-throw-exception-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-115">For more information about the **ThrowException** shape, see [How to Configure the Throw Exception Shape](../core/how-to-configure-the-throw-exception-shape.md).</span></span>  
  
## <a name="the-custom-exceptions"></a><span data-ttu-id="5c3ab-116">自定义异常</span><span class="sxs-lookup"><span data-stu-id="5c3ab-116">The Custom Exceptions</span></span>  
 <span data-ttu-id="5c3ab-117">以下三个自定义异常的每个遵循相同的模式。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-117">Each of the following three custom exceptions follows the same pattern.</span></span> <span data-ttu-id="5c3ab-118">具有不同类型允许区分不同的异常代码。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-118">Having distinct types allows the code to distinguish different exceptions.</span></span>  
  
|<span data-ttu-id="5c3ab-119">异常</span><span class="sxs-lookup"><span data-stu-id="5c3ab-119">Exception</span></span>|<span data-ttu-id="5c3ab-120">引发者 （业务流程）</span><span class="sxs-lookup"><span data-stu-id="5c3ab-120">Thrown By (Orchestration)</span></span>|  
|---------------|---------------------------------|  
|<span data-ttu-id="5c3ab-121">**ActivateException**</span><span class="sxs-lookup"><span data-stu-id="5c3ab-121">**ActivateException**</span></span>|<span data-ttu-id="5c3ab-122">**更改**</span><span class="sxs-lookup"><span data-stu-id="5c3ab-122">**Change**</span></span>|  
|<span data-ttu-id="5c3ab-123">**CableOrderException**</span><span class="sxs-lookup"><span data-stu-id="5c3ab-123">**CableOrderException**</span></span>|<span data-ttu-id="5c3ab-124">**Activate**, **CableOrder1**</span><span class="sxs-lookup"><span data-stu-id="5c3ab-124">**Activate**, **CableOrder1**</span></span>|  
|<span data-ttu-id="5c3ab-125">**InterruptException**</span><span class="sxs-lookup"><span data-stu-id="5c3ab-125">**InterruptException**</span></span>|<span data-ttu-id="5c3ab-126">**CableOrder1**， **CheckInterrupt**， **ErrorHandlerOrch**</span><span class="sxs-lookup"><span data-stu-id="5c3ab-126">**CableOrder1**, **CheckInterrupt**, **ErrorHandlerOrch**</span></span>|  
  
 <span data-ttu-id="5c3ab-127">中定义的所有自定义异常**实用程序**程序集。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-127">All of the custom exceptions are defined in the **Utilities** assembly.</span></span> <span data-ttu-id="5c3ab-128">自定义例外情况是所有.NET 类。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-128">The custom exceptions are all .NET classes.</span></span> <span data-ttu-id="5c3ab-129">所有自定义异常类继承自.NET **ApplicationException**类，该类又继承自**System.Exception**类。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-129">All of the custom exception classes inherit from the .NET **ApplicationException** class which in turn inherits from the **System.Exception** class.</span></span> <span data-ttu-id="5c3ab-130">因为可能导致此异常可能被冻结 （序列化和存储在数据库中），因此异常必须实现反序列化构造函数。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-130">Because there is a possibility that the exception may be dehydrated (serialized and stored in the database), the exceptions must implement a deserialization constructor.</span></span> <span data-ttu-id="5c3ab-131">反序列化构造函数是采用两个参数的构造函数： 一个 SerializationInfo 对象和一个 StreamingContext 对象。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-131">A deserialization constructor is a constructor that takes two arguments: a SerializationInfo object, and a StreamingContext object.</span></span> <span data-ttu-id="5c3ab-132">在解除异常冻结期间，将使用反序列化构造函数。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-132">The deserialization constructor will be used during rehydration of the exception.</span></span> <span data-ttu-id="5c3ab-133">因为**ApplicationException**类已经实现反序列化构造函数、 自定义异常的构造函数只是调用基本 (ApplicationException) 反序列化构造函数。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-133">Because the **ApplicationException** class already implements a deserialization constructor, the constructor for the custom exception simply invokes the base (ApplicationException) deserialization constructor.</span></span> <span data-ttu-id="5c3ab-134">例如， **InterruptException**包括以下构造函数：</span><span class="sxs-lookup"><span data-stu-id="5c3ab-134">For example, the **InterruptException** includes the following constructor:</span></span>  
  
```  
// "info" is the object holding the serialized object data.  
// "context" is the contextual information about the source  
// or destination.  
public InterruptException(SerializationInfo info,  
                  StreamingContext context) : base(info, context) { }  
```  
  
 <span data-ttu-id="5c3ab-135">详细了解自定义序列化的详细信息，请参阅中的自定义序列化[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]开发人员指南。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-135">For more detailed information about custom serialization, see Custom Serialization in the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Developer's Guide.</span></span>  
  
## <a name="nested-exception-handlers-and-compensation-blocks"></a><span data-ttu-id="5c3ab-136">嵌套的异常处理程序和补偿模块</span><span class="sxs-lookup"><span data-stu-id="5c3ab-136">Nested Exception Handlers and Compensation Blocks</span></span>  
 <span data-ttu-id="5c3ab-137">除了充当特殊异常，多个位置中的自定义异常还充当排序标志。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-137">In addition to serving as specialized exceptions, the custom exceptions in several places also serve as a sort flag.</span></span> <span data-ttu-id="5c3ab-138">在中**更改**业务流程中，有两个位置的取消操作必须回滚。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-138">In the **Change** orchestration, there are two places that the Cancel operation must be rolled back.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c3ab-139">你可能想要阅读此部分**更改**Visual Studio 中打开业务流程。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-139">You may want to read this section with the **Change** orchestration open in Visual Studio.</span></span>  
  
 <span data-ttu-id="5c3ab-140">顶部的业务流程中，如果在调用**取消**业务流程失败**CancelCompensation**块执行和回滚**取消**事务。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-140">At the top of the orchestration, if the call to the **Cancel** orchestration fails, the **CancelCompensation** block executes and rolls back the **Cancel** transaction.</span></span> <span data-ttu-id="5c3ab-141">如果一切正常，则该业务流程将调用**激活**业务流程。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-141">If all goes well, the orchestration then calls the **Activate** orchestration.</span></span>  
  
 <span data-ttu-id="5c3ab-142">如果**激活**操作将失败，**取消**事务必须还被回滚。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-142">If the **Activate** operation fails, the **Cancel** transaction must also be rolled back.</span></span> <span data-ttu-id="5c3ab-143">但是，在调用的异常处理程序**激活**的相关信息一无所知**取消**事务。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-143">However, the exception handler for the call to **Activate** knows nothing about the **Cancel** transaction.</span></span> <span data-ttu-id="5c3ab-144">为了处理此问题，提供了整个业务流程的异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-144">To handle this, there is an exception handler for the entire orchestration.</span></span> <span data-ttu-id="5c3ab-145">此处理程序，因为它包含**取消**范围，知道**取消**事务。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-145">This handler, because it contains the **Cancel** scope, knows about the **Cancel** transaction.</span></span> <span data-ttu-id="5c3ab-146">处理程序捕获引发的异常**激活**作用域 ( **ActivateException**)，将回滚**取消**事务，然后再次引发异常和以便业务流程调用的函数**更改**业务流程可以执行任何其他处理。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-146">The handler catches the exception thrown from the **Activate** scope (the **ActivateException**), rolls back the **Cancel** transaction, and then throws the exception again so that the orchestration that called the **Change** orchestration can perform any additional processing.</span></span>  
  
 <span data-ttu-id="5c3ab-147">请注意，此设计只会补偿**取消**如果**激活**失败。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-147">Notice that this design only compensates the **Cancel** if the **Activate** fails.</span></span> <span data-ttu-id="5c3ab-148">如果**取消**失败并引发异常，**取消**永远不会成功，不应进行补偿。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-148">If the **Cancel** fails and throws an exception, the **Cancel** never took place and should not be compensated.</span></span>  
  
 <span data-ttu-id="5c3ab-149">有关补偿模块详细信息和**Compensate**形状中，请参阅[如何配置补偿形状](../core/how-to-configure-the-compensate-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="5c3ab-149">For more information about compensation blocks and the **Compensate** shape, see [How to Configure the Compensate Shape](../core/how-to-configure-the-compensate-shape.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c3ab-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c3ab-150">See Also</span></span>  
 <span data-ttu-id="5c3ab-151">[业务流程管理解决方案中的异常处理](../core/exception-handling-in-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="5c3ab-151">[Exception Handling in the Business Process Management Solution](../core/exception-handling-in-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="5c3ab-152">ExceptionHandler 业务流程</span><span class="sxs-lookup"><span data-stu-id="5c3ab-152">The ExceptionHandler Orchestration</span></span>](../core/the-exceptionhandler-orchestration.md)