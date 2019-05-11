---
title: ExceptionHandler 业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, systems
- errors, applications
- applications, errors
- orchestrations, errors [process management solutions]
- process management solution tutorial, errors
ms.assetid: ac154e76-9dfe-433a-948b-e098df705fe5
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3fd1a3fccf72b73271528d93bb03060aa259a39
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298745"
---
# <a name="the-exceptionhandler-orchestration"></a><span data-ttu-id="2e464-102">ExceptionHandler 业务流程</span><span class="sxs-lookup"><span data-stu-id="2e464-102">The ExceptionHandler Orchestration</span></span>
<span data-ttu-id="2e464-103">业务流程管理解决方案使用两种类型的异常： 系统异常和应用程序异常。</span><span class="sxs-lookup"><span data-stu-id="2e464-103">The Business Process Management solution uses two kinds of exceptions: system exceptions and application exceptions.</span></span> <span data-ttu-id="2e464-104">系统异常包括类似资源错误 — 失败，例如网络连接。</span><span class="sxs-lookup"><span data-stu-id="2e464-104">System exceptions include things like resource errors—a network connection failing, for example.</span></span> <span data-ttu-id="2e464-105">没有机会，这样的问题可能自动解决的时间间隔后，以便解决方案将重试造成系统异常的所有操作。</span><span class="sxs-lookup"><span data-stu-id="2e464-105">There is a chance that such a problem may resolve itself after an interval so that the solution retries all operations that produce system exceptions.</span></span> <span data-ttu-id="2e464-106">应用程序异常的错误很少以解决此类，如逻辑错误或某种形式的不一致问题。</span><span class="sxs-lookup"><span data-stu-id="2e464-106">Application exceptions are produced by things less likely to resolve themselves, such as logical errors or some form of inconsistency.</span></span> <span data-ttu-id="2e464-107">该解决方案使用**ExceptionHandlerOrch**业务流程来处理系统和应用程序错误。</span><span class="sxs-lookup"><span data-stu-id="2e464-107">The solution uses the **ExceptionHandlerOrch** orchestration to process both system and application errors.</span></span>  
  
 <span data-ttu-id="2e464-108">订单处理阶段 (**CableOrder1**， **CableOrder2**) 及其附属业务流程 (**激活**，**分析**， **取消**，**更改**，**完成**，**验证**) 所有使用**ExceptionHandlerOrch**。</span><span class="sxs-lookup"><span data-stu-id="2e464-108">The order processing stages (**CableOrder1**, **CableOrder2**) and their satellite orchestrations (**Activate**, **Analyze**, **Cancel**, **Change**, **Complete**, **Validate**) all use **ExceptionHandlerOrch**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e464-109">你可能想要阅读此部分**ExceptionHandlerOrch**业务流程在 Microsoft 中打开[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2e464-109">You may want to read this section with the **ExceptionHandlerOrch** orchestration open in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="application-errors"></a><span data-ttu-id="2e464-110">应用程序错误</span><span class="sxs-lookup"><span data-stu-id="2e464-110">Application Errors</span></span>  
 <span data-ttu-id="2e464-111">异常处理程序首先通过调用来记录错误**PostError**方法**ErrorHandler**对象中**实用程序**程序集。</span><span class="sxs-lookup"><span data-stu-id="2e464-111">The exception handler first logs the error by calling the **PostError** method of the **ErrorHandler** object in the **Utilities** assembly.</span></span> <span data-ttu-id="2e464-112">异常处理程序然后测试该错误是系统错误或应用程序错误。</span><span class="sxs-lookup"><span data-stu-id="2e464-112">The exception handler then tests whether the error was a system error or an application error.</span></span> <span data-ttu-id="2e464-113">下面的屏幕截图显示了处理应用程序异常的业务流程分支：</span><span class="sxs-lookup"><span data-stu-id="2e464-113">The following screenshot shows the orchestration branch that processes application exceptions:</span></span>  
  
 <span data-ttu-id="2e464-114">![ExceptionHandler 业务流程的应用程序分支](../core/media/applicationerrorbranchofexceptionhandler.gif "ApplicationErrorBranchofExceptionHandler")</span><span class="sxs-lookup"><span data-stu-id="2e464-114">![Application Branch of ExceptionHandler Orchestrati](../core/media/applicationerrorbranchofexceptionhandler.gif "ApplicationErrorBranchofExceptionHandler")</span></span>  
  
 <span data-ttu-id="2e464-115">对于应用程序错误，业务流程构造描述该错误并调用的字符串**ErrorHandlerOrch**业务流程。</span><span class="sxs-lookup"><span data-stu-id="2e464-115">For an application error, the orchestration constructs a string describing the error and calls the **ErrorHandlerOrch** orchestration.</span></span> <span data-ttu-id="2e464-116">此业务流程将错误发送到操作的运算符将在其中确定是修复错误还是终止操作。</span><span class="sxs-lookup"><span data-stu-id="2e464-116">This orchestration sends the error to operations where an operator decides whether to fix the error or terminate the operation.</span></span> <span data-ttu-id="2e464-117">如果运算符修复错误，将修复的消息回来的 ErrorHandlerOrch 业务流程和重试该操作。</span><span class="sxs-lookup"><span data-stu-id="2e464-117">If the operator fixes the error, the repaired message comes back from the ErrorHandlerOrch orchestration and the operation is retried.</span></span> <span data-ttu-id="2e464-118">异常处理程序将这是通过调用**Invoke**方法**Recaller**对象中**实用程序**程序集。</span><span class="sxs-lookup"><span data-stu-id="2e464-118">The exception handler does this by calling the **Invoke** method of the **Recaller** object in the **Utilities** assembly.</span></span> <span data-ttu-id="2e464-119">**Recaller**对象使用反射来调用导致了错误的代码。</span><span class="sxs-lookup"><span data-stu-id="2e464-119">The **Recaller** object uses reflection to call the code that caused the error.</span></span>  
  
 <span data-ttu-id="2e464-120">如果在调用**Invoke**成功，则异常处理程序将退出。</span><span class="sxs-lookup"><span data-stu-id="2e464-120">If the call to **Invoke** succeeds, the exception handler exits.</span></span> <span data-ttu-id="2e464-121">否则为它返回循环并尝试调用**Invoke**试。</span><span class="sxs-lookup"><span data-stu-id="2e464-121">Otherwise, it loops back and attempts the call to **Invoke** again.</span></span> <span data-ttu-id="2e464-122">有关详细信息**Recaller**对象，请参阅[Recaller 对象](../core/the-recaller-object.md)。</span><span class="sxs-lookup"><span data-stu-id="2e464-122">For more information about the **Recaller** object, see [The Recaller Object](../core/the-recaller-object.md).</span></span>  
  
## <a name="system-errors"></a><span data-ttu-id="2e464-123">系统错误</span><span class="sxs-lookup"><span data-stu-id="2e464-123">System Errors</span></span>  
 <span data-ttu-id="2e464-124">下图显示了系统错误分支**ExceptionHandler**业务流程：</span><span class="sxs-lookup"><span data-stu-id="2e464-124">The following diagram shows the system error branch of the **ExceptionHandler** orchestration:</span></span>  
  
 <span data-ttu-id="2e464-125">![ExceptionHandler 业务流程的系统错误](../core/media/systemerrorbranchofexceptionhandler.gif "SystemErrorBranchofExceptionHandler")</span><span class="sxs-lookup"><span data-stu-id="2e464-125">![System Error of ExceptionHandler Orchestration](../core/media/systemerrorbranchofexceptionhandler.gif "SystemErrorBranchofExceptionHandler")</span></span>  
  
 <span data-ttu-id="2e464-126">对于系统错误，异常处理程序首先调用**CheckInterrupt**业务流程，然后等待一分钟。</span><span class="sxs-lookup"><span data-stu-id="2e464-126">For a system error, the exception handler first calls the **CheckInterrupt** orchestration and then waits for one minute.</span></span> <span data-ttu-id="2e464-127">在等待允许临时性的短期的错误，例如网络连接问题，然后重试清除。</span><span class="sxs-lookup"><span data-stu-id="2e464-127">The wait allows for temporary, short-term errors such as network connection problems, to clear before trying again.</span></span> <span data-ttu-id="2e464-128">在进行远程调用时是始终是网络问题的机会。</span><span class="sxs-lookup"><span data-stu-id="2e464-128">When making remote calls there is always the chance of a network problem.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e464-129">在可中断设计中，作为一般规则，你想要测试中断期间或之后任何等待时间以查看是否发生中断。</span><span class="sxs-lookup"><span data-stu-id="2e464-129">In an interruptible design, as a general rule, you want to test for an interrupt during or immediately after any waiting period to see if an interrupt has occurred.</span></span>  
  
 <span data-ttu-id="2e464-130">等待后的处理程序使用**Invoke**方法**Recaller**对象运行原始代码。</span><span class="sxs-lookup"><span data-stu-id="2e464-130">After the wait, the handler uses the **Invoke** method of the **Recaller** object to run the original code.</span></span> <span data-ttu-id="2e464-131">如果调用成功，该处理程序将退出。</span><span class="sxs-lookup"><span data-stu-id="2e464-131">If the call succeeds, the handler exits.</span></span> <span data-ttu-id="2e464-132">否则，该处理程序将尝试两次，运行原始代码。</span><span class="sxs-lookup"><span data-stu-id="2e464-132">Otherwise, the handler will try two more times to run the original code.</span></span> <span data-ttu-id="2e464-133">如果所有三个尝试失败，该处理程序构造错误字符串并调用**ErrorHandlerOrch**业务流程。</span><span class="sxs-lookup"><span data-stu-id="2e464-133">If all three attempts fail, the handler constructs an error string and calls the **ErrorHandlerOrch** orchestration.</span></span>  
  
 <span data-ttu-id="2e464-134">如果处理系统异常导致异常，异常块将捕获它：</span><span class="sxs-lookup"><span data-stu-id="2e464-134">If processing a system exception causes an exception, the exception block catches it:</span></span>  
  
 <span data-ttu-id="2e464-135">![异常处理程序的系统错误分支](../core/media/exceptionhandlerofsystemerrorbranch.gif "ExceptionHandlerofSystemErrorBranch")</span><span class="sxs-lookup"><span data-stu-id="2e464-135">![Exception Handler for System Error Branch](../core/media/exceptionhandlerofsystemerrorbranch.gif "ExceptionHandlerofSystemErrorBranch")</span></span>  
  
 <span data-ttu-id="2e464-136">如果它是系统异常，或设置一个标志，指示应用程序异常，异常处理程序将测试的类型的异常并可减少重试计数器。</span><span class="sxs-lookup"><span data-stu-id="2e464-136">The exception handler tests the type of the exception and either decrements the retry counter if it's a system exception, or sets a flag to indicate an application exception.</span></span>  
  
## <a name="the-errorhandlerorch-orchestration"></a><span data-ttu-id="2e464-137">ErrorHandlerOrch 业务流程</span><span class="sxs-lookup"><span data-stu-id="2e464-137">The ErrorHandlerOrch Orchestration</span></span>  
 <span data-ttu-id="2e464-138">下图显示的第一部分**ErrorHandlerOrch**业务流程：</span><span class="sxs-lookup"><span data-stu-id="2e464-138">The following diagram shows the first part of the **ErrorHandlerOrch** orchestration:</span></span>  
  
 <span data-ttu-id="2e464-139">![错误处理程序业务流程，第一部分](../core/media/errorhandlerfirstpart.gif "ErrorHandlerFirstPart")</span><span class="sxs-lookup"><span data-stu-id="2e464-139">![Error Handler Orchestration, First Part](../core/media/errorhandlerfirstpart.gif "ErrorHandlerFirstPart")</span></span>  
  
 <span data-ttu-id="2e464-140">**ErrorHandlerOrch**业务流程的第一个测试**IsBadOrder**参数，以查看该错误是订单错误 (**IsBadOrder**为 true) 或其他一些错误。</span><span class="sxs-lookup"><span data-stu-id="2e464-140">The **ErrorHandlerOrch** orchestration first tests the **IsBadOrder** parameter to see if the error is a bad order (**IsBadOrder** is true) or some other error.</span></span> <span data-ttu-id="2e464-141">如果错误是订单错误，它从原始订单返回地址分配消息的目标，并将消息发送回客户服务系统。</span><span class="sxs-lookup"><span data-stu-id="2e464-141">If the error is a bad order, it assigns the destination of the message from the original order return address and sends the message back to the customer service system.</span></span> <span data-ttu-id="2e464-142">如果该错误不是订单错误，业务流程将创建一个订单错误消息，并将其发送给操作系统。</span><span class="sxs-lookup"><span data-stu-id="2e464-142">If the error is not a bad order, the orchestration creates an order error message and sends it to the operations system.</span></span>  
  
 <span data-ttu-id="2e464-143">在任一错误之后, 该业务流程将侦听的响应消息或中断消息：</span><span class="sxs-lookup"><span data-stu-id="2e464-143">After either error, the orchestration then listens for a response message or an interrupt message:</span></span>  
  
 <span data-ttu-id="2e464-144">![错误处理程序的第二部分](../core/media/errorhandlersecondpart.gif "ErrorHandlerSecondPart")</span><span class="sxs-lookup"><span data-stu-id="2e464-144">![Error Handler Second Part](../core/media/errorhandlersecondpart.gif "ErrorHandlerSecondPart")</span></span>  
  
 <span data-ttu-id="2e464-145">如果业务流程收到响应后，它将返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="2e464-145">If the orchestration receives a response, it returns to the caller.</span></span> <span data-ttu-id="2e464-146">如果业务流程收到中断消息，它会将消息传递中断端口，并引发自定义**InterruptException**。</span><span class="sxs-lookup"><span data-stu-id="2e464-146">If the orchestration receives an interrupt message, it passes the message on to an interrupt port and throws a custom **InterruptException**.</span></span>  
  
 <span data-ttu-id="2e464-147">有关解决方案如何使用和处理中断的详细信息，请参阅[业务流程管理解决方案中的中断处理](../core/interrupt-handling-in-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="2e464-147">For more information about how the solution uses and handles interrupts, see [Interrupt Handling in the Business Process Management Solution](../core/interrupt-handling-in-the-business-process-management-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e464-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e464-148">See Also</span></span>  
 <span data-ttu-id="2e464-149">[业务流程管理解决方案中的异常处理](../core/exception-handling-in-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="2e464-149">[Exception Handling in the Business Process Management Solution](../core/exception-handling-in-the-business-process-management-solution.md) </span></span>  
 <span data-ttu-id="2e464-150">[自定义异常](../core/custom-exceptions.md) </span><span class="sxs-lookup"><span data-stu-id="2e464-150">[Custom Exceptions](../core/custom-exceptions.md) </span></span>  
 <span data-ttu-id="2e464-151">[业务流程管理解决方案中的中断处理](../core/interrupt-handling-in-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="2e464-151">[Interrupt Handling in the Business Process Management Solution](../core/interrupt-handling-in-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="2e464-152">Recaller 对象</span><span class="sxs-lookup"><span data-stu-id="2e464-152">The Recaller Object</span></span>](../core/the-recaller-object.md)