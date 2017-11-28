---
title: "ExceptionHandler 业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors, systems
- errors, applications
- applications, errors
- orchestrations, errors [process management solutions]
- process management solution tutorial, errors
ms.assetid: ac154e76-9dfe-433a-948b-e098df705fe5
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1b79a1c6d9e6fada206ba0298913fe8f369783c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-exceptionhandler-orchestration"></a><span data-ttu-id="be33e-102">ExceptionHandler 业务流程</span><span class="sxs-lookup"><span data-stu-id="be33e-102">The ExceptionHandler Orchestration</span></span>
<span data-ttu-id="be33e-103">业务流程管理解决方案使用两种类型的异常：系统异常和应用程序异常。</span><span class="sxs-lookup"><span data-stu-id="be33e-103">The Business Process Management solution uses two kinds of exceptions: system exceptions and application exceptions.</span></span> <span data-ttu-id="be33e-104">系统异常包括类似资源错误（例如，网络连接故障）的事项。</span><span class="sxs-lookup"><span data-stu-id="be33e-104">System exceptions include things like resource errors—a network connection failing, for example.</span></span> <span data-ttu-id="be33e-105">此类问题可能在经过一段时间后会自行解决，从而，解决方案将重试造成系统异常的所有操作。</span><span class="sxs-lookup"><span data-stu-id="be33e-105">There is a chance that such a problem may resolve itself after an interval so that the solution retries all operations that produce system exceptions.</span></span> <span data-ttu-id="be33e-106">而导致应用程序异常的错误很少能自行解决，这些错误包括逻辑错误或某些格式不一致的问题等。</span><span class="sxs-lookup"><span data-stu-id="be33e-106">Application exceptions are produced by things less likely to resolve themselves, such as logical errors or some form of inconsistency.</span></span> <span data-ttu-id="be33e-107">此解决方案使用**ExceptionHandlerOrch**业务流程来处理系统和应用程序错误。</span><span class="sxs-lookup"><span data-stu-id="be33e-107">The solution uses the **ExceptionHandlerOrch** orchestration to process both system and application errors.</span></span>  
  
 <span data-ttu-id="be33e-108">订单处理阶段 (**CableOrder1**， **CableOrder2**) 和其附属业务流程 (**激活**，**分析**， **取消**，**更改**，**完成**，**验证**) 所有使用**ExceptionHandlerOrch**。</span><span class="sxs-lookup"><span data-stu-id="be33e-108">The order processing stages (**CableOrder1**, **CableOrder2**) and their satellite orchestrations (**Activate**, **Analyze**, **Cancel**, **Change**, **Complete**, **Validate**) all use **ExceptionHandlerOrch**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be33e-109">你可能想要读取此节**ExceptionHandlerOrch**在 Microsoft 中的业务流程打开[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="be33e-109">You may want to read this section with the **ExceptionHandlerOrch** orchestration open in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="application-errors"></a><span data-ttu-id="be33e-110">应用程序错误</span><span class="sxs-lookup"><span data-stu-id="be33e-110">Application Errors</span></span>  
 <span data-ttu-id="be33e-111">异常处理程序首先会将错误记录通过调用**PostError**方法**ErrorHandler**对象在**实用工具**程序集。</span><span class="sxs-lookup"><span data-stu-id="be33e-111">The exception handler first logs the error by calling the **PostError** method of the **ErrorHandler** object in the **Utilities** assembly.</span></span> <span data-ttu-id="be33e-112">然后，异常处理程序将测试该错误是系统错误还是应用程序错误。</span><span class="sxs-lookup"><span data-stu-id="be33e-112">The exception handler then tests whether the error was a system error or an application error.</span></span> <span data-ttu-id="be33e-113">以下屏幕快照显示了处理应用程序异常的业务流程分支：</span><span class="sxs-lookup"><span data-stu-id="be33e-113">The following screenshot shows the orchestration branch that processes application exceptions:</span></span>  
  
 <span data-ttu-id="be33e-114">![应用程序分支 ExceptionHandler Orchestrati](../core/media/applicationerrorbranchofexceptionhandler.gif "ApplicationErrorBranchofExceptionHandler")</span><span class="sxs-lookup"><span data-stu-id="be33e-114">![Application Branch of ExceptionHandler Orchestrati](../core/media/applicationerrorbranchofexceptionhandler.gif "ApplicationErrorBranchofExceptionHandler")</span></span>  
  
 <span data-ttu-id="be33e-115">对于应用程序错误，业务流程构造描述错误并调用一个字符串**ErrorHandlerOrch**业务流程。</span><span class="sxs-lookup"><span data-stu-id="be33e-115">For an application error, the orchestration constructs a string describing the error and calls the **ErrorHandlerOrch** orchestration.</span></span> <span data-ttu-id="be33e-116">此业务流程将该错误发送到操作，其中的运算符将确定是修复该错误还是终止操作。</span><span class="sxs-lookup"><span data-stu-id="be33e-116">This orchestration sends the error to operations where an operator decides whether to fix the error or terminate the operation.</span></span> <span data-ttu-id="be33e-117">如果运算符修复错误，则修复后的消息将从 ErrorHandlerOrch 业务流程返回，并且重试该操作。</span><span class="sxs-lookup"><span data-stu-id="be33e-117">If the operator fixes the error, the repaired message comes back from the ErrorHandlerOrch orchestration and the operation is retried.</span></span> <span data-ttu-id="be33e-118">异常处理程序将这是通过调用**Invoke**方法**Recaller**对象在**实用工具**程序集。</span><span class="sxs-lookup"><span data-stu-id="be33e-118">The exception handler does this by calling the **Invoke** method of the **Recaller** object in the **Utilities** assembly.</span></span> <span data-ttu-id="be33e-119">**Recaller**对象使用反射来调用导致错误的代码。</span><span class="sxs-lookup"><span data-stu-id="be33e-119">The **Recaller** object uses reflection to call the code that caused the error.</span></span>  
  
 <span data-ttu-id="be33e-120">如果调用**Invoke**成功，异常处理程序退出。</span><span class="sxs-lookup"><span data-stu-id="be33e-120">If the call to **Invoke** succeeds, the exception handler exits.</span></span> <span data-ttu-id="be33e-121">否则为它循环，且尝试调用**Invoke**试。</span><span class="sxs-lookup"><span data-stu-id="be33e-121">Otherwise, it loops back and attempts the call to **Invoke** again.</span></span> <span data-ttu-id="be33e-122">有关详细信息**Recaller**对象，请参阅[Recaller Object](../core/the-recaller-object.md)。</span><span class="sxs-lookup"><span data-stu-id="be33e-122">For more information about the **Recaller** object, see [The Recaller Object](../core/the-recaller-object.md).</span></span>  
  
## <a name="system-errors"></a><span data-ttu-id="be33e-123">系统错误</span><span class="sxs-lookup"><span data-stu-id="be33e-123">System Errors</span></span>  
 <span data-ttu-id="be33e-124">下图显示的系统错误分支**ExceptionHandler**业务流程：</span><span class="sxs-lookup"><span data-stu-id="be33e-124">The following diagram shows the system error branch of the **ExceptionHandler** orchestration:</span></span>  
  
 <span data-ttu-id="be33e-125">![ExceptionHandler 业务流程的系统错误](../core/media/systemerrorbranchofexceptionhandler.gif "SystemErrorBranchofExceptionHandler")</span><span class="sxs-lookup"><span data-stu-id="be33e-125">![System Error of ExceptionHandler Orchestration](../core/media/systemerrorbranchofexceptionhandler.gif "SystemErrorBranchofExceptionHandler")</span></span>  
  
 <span data-ttu-id="be33e-126">对于系统错误，异常处理程序首先调用**CheckInterrupt**业务流程，然后等待一分钟。</span><span class="sxs-lookup"><span data-stu-id="be33e-126">For a system error, the exception handler first calls the **CheckInterrupt** orchestration and then waits for one minute.</span></span> <span data-ttu-id="be33e-127">通过等待，短期的暂时性错误（例如，网络连接问题）可在重试前清除。</span><span class="sxs-lookup"><span data-stu-id="be33e-127">The wait allows for temporary, short-term errors such as network connection problems, to clear before trying again.</span></span> <span data-ttu-id="be33e-128">在进行远程调用时，始终可能存在网络问题。</span><span class="sxs-lookup"><span data-stu-id="be33e-128">When making remote calls there is always the chance of a network problem.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be33e-129">在可中断设计中，通用规则为：应在任何等待期间或之后立刻测试中断，以查看是否发生了中断。</span><span class="sxs-lookup"><span data-stu-id="be33e-129">In an interruptible design, as a general rule, you want to test for an interrupt during or immediately after any waiting period to see if an interrupt has occurred.</span></span>  
  
 <span data-ttu-id="be33e-130">在等待之后, 该处理程序使用**Invoke**方法**Recaller**运行的原始代码的对象。</span><span class="sxs-lookup"><span data-stu-id="be33e-130">After the wait, the handler uses the **Invoke** method of the **Recaller** object to run the original code.</span></span> <span data-ttu-id="be33e-131">如果调用成功，则该异常处理程序将退出。</span><span class="sxs-lookup"><span data-stu-id="be33e-131">If the call succeeds, the handler exits.</span></span> <span data-ttu-id="be33e-132">否则，该处理程序将尝试两次以上，以运行原始代码。</span><span class="sxs-lookup"><span data-stu-id="be33e-132">Otherwise, the handler will try two more times to run the original code.</span></span> <span data-ttu-id="be33e-133">如果所有三个尝试都失败，该处理程序构造错误字符串和调用**ErrorHandlerOrch**业务流程。</span><span class="sxs-lookup"><span data-stu-id="be33e-133">If all three attempts fail, the handler constructs an error string and calls the **ErrorHandlerOrch** orchestration.</span></span>  
  
 <span data-ttu-id="be33e-134">如果对系统异常的处理引发异常，则异常块将捕获它：</span><span class="sxs-lookup"><span data-stu-id="be33e-134">If processing a system exception causes an exception, the exception block catches it:</span></span>  
  
 <span data-ttu-id="be33e-135">![异常处理程序系统错误分支](../core/media/exceptionhandlerofsystemerrorbranch.gif "ExceptionHandlerofSystemErrorBranch")</span><span class="sxs-lookup"><span data-stu-id="be33e-135">![Exception Handler for System Error Branch](../core/media/exceptionhandlerofsystemerrorbranch.gif "ExceptionHandlerofSystemErrorBranch")</span></span>  
  
 <span data-ttu-id="be33e-136">异常处理程序可测试异常的类型，并可减少重试计数（如果该异常为系统异常），或设置标志以指示该异常为应用程序异常。</span><span class="sxs-lookup"><span data-stu-id="be33e-136">The exception handler tests the type of the exception and either decrements the retry counter if it's a system exception, or sets a flag to indicate an application exception.</span></span>  
  
## <a name="the-errorhandlerorch-orchestration"></a><span data-ttu-id="be33e-137">ErrorHandlerOrch 业务流程</span><span class="sxs-lookup"><span data-stu-id="be33e-137">The ErrorHandlerOrch Orchestration</span></span>  
 <span data-ttu-id="be33e-138">下图显示的第一部分**ErrorHandlerOrch**业务流程：</span><span class="sxs-lookup"><span data-stu-id="be33e-138">The following diagram shows the first part of the **ErrorHandlerOrch** orchestration:</span></span>  
  
 <span data-ttu-id="be33e-139">![错误处理程序业务流程，第一部分](../core/media/errorhandlerfirstpart.gif "ErrorHandlerFirstPart")</span><span class="sxs-lookup"><span data-stu-id="be33e-139">![Error Handler Orchestration, First Part](../core/media/errorhandlerfirstpart.gif "ErrorHandlerFirstPart")</span></span>  
  
 <span data-ttu-id="be33e-140">**ErrorHandlerOrch** orchestration 第一个测试**IsBadOrder**参数，以查看错误是否错误顺序 (**IsBadOrder**为 true) 或一某些其他错误。</span><span class="sxs-lookup"><span data-stu-id="be33e-140">The **ErrorHandlerOrch** orchestration first tests the **IsBadOrder** parameter to see if the error is a bad order (**IsBadOrder** is true) or some other error.</span></span> <span data-ttu-id="be33e-141">如果该错误为订单错误，则该业务流程将指定原始订单返回地址中消息的目标，并将该消息发送回客户服务系统。</span><span class="sxs-lookup"><span data-stu-id="be33e-141">If the error is a bad order, it assigns the destination of the message from the original order return address and sends the message back to the customer service system.</span></span> <span data-ttu-id="be33e-142">如果不是订单错误，则该业务流程将创建一个订单错误消息，并将其发送给操作系统。</span><span class="sxs-lookup"><span data-stu-id="be33e-142">If the error is not a bad order, the orchestration creates an order error message and sends it to the operations system.</span></span>  
  
 <span data-ttu-id="be33e-143">在上述任何一种错误后，该业务流程将侦听响应消息或中断消息：</span><span class="sxs-lookup"><span data-stu-id="be33e-143">After either error, the orchestration then listens for a response message or an interrupt message:</span></span>  
  
 <span data-ttu-id="be33e-144">![错误处理程序的第二部分](../core/media/errorhandlersecondpart.gif "ErrorHandlerSecondPart")</span><span class="sxs-lookup"><span data-stu-id="be33e-144">![Error Handler Second Part](../core/media/errorhandlersecondpart.gif "ErrorHandlerSecondPart")</span></span>  
  
 <span data-ttu-id="be33e-145">如果业务流程收到响应，则它将返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="be33e-145">If the orchestration receives a response, it returns to the caller.</span></span> <span data-ttu-id="be33e-146">如果业务流程收到中断消息，它将消息传递到中断端口，并引发一个自定义**InterruptException**。</span><span class="sxs-lookup"><span data-stu-id="be33e-146">If the orchestration receives an interrupt message, it passes the message on to an interrupt port and throws a custom **InterruptException**.</span></span>  
  
 <span data-ttu-id="be33e-147">有关如何解决方案使用和处理中断的详细信息，请参阅[中断业务流程管理解决方案中的处理](../core/interrupt-handling-in-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="be33e-147">For more information about how the solution uses and handles interrupts, see [Interrupt Handling in the Business Process Management Solution](../core/interrupt-handling-in-the-business-process-management-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be33e-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be33e-148">See Also</span></span>  
 <span data-ttu-id="be33e-149">[业务流程管理解决方案中的异常处理](../core/exception-handling-in-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="be33e-149">[Exception Handling in the Business Process Management Solution](../core/exception-handling-in-the-business-process-management-solution.md) </span></span>  
 <span data-ttu-id="be33e-150">[自定义异常](../core/custom-exceptions.md) </span><span class="sxs-lookup"><span data-stu-id="be33e-150">[Custom Exceptions](../core/custom-exceptions.md) </span></span>  
 <span data-ttu-id="be33e-151">[中断业务流程管理解决方案中的处理](../core/interrupt-handling-in-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="be33e-151">[Interrupt Handling in the Business Process Management Solution](../core/interrupt-handling-in-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="be33e-152">Recaller 对象</span><span class="sxs-lookup"><span data-stu-id="be33e-152">The Recaller Object</span></span>](../core/the-recaller-object.md)