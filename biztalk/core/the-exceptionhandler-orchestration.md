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
# <a name="the-exceptionhandler-orchestration"></a>ExceptionHandler 业务流程
业务流程管理解决方案使用两种类型的异常： 系统异常和应用程序异常。 系统异常包括类似资源错误 — 失败，例如网络连接。 没有机会，这样的问题可能自动解决的时间间隔后，以便解决方案将重试造成系统异常的所有操作。 应用程序异常的错误很少以解决此类，如逻辑错误或某种形式的不一致问题。 该解决方案使用**ExceptionHandlerOrch**业务流程来处理系统和应用程序错误。  
  
 订单处理阶段 (**CableOrder1**， **CableOrder2**) 及其附属业务流程 (**激活**，**分析**， **取消**，**更改**，**完成**，**验证**) 所有使用**ExceptionHandlerOrch**。  
  
> [!NOTE]
>  你可能想要阅读此部分**ExceptionHandlerOrch**业务流程在 Microsoft 中打开[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
## <a name="application-errors"></a>应用程序错误  
 异常处理程序首先通过调用来记录错误**PostError**方法**ErrorHandler**对象中**实用程序**程序集。 异常处理程序然后测试该错误是系统错误或应用程序错误。 下面的屏幕截图显示了处理应用程序异常的业务流程分支：  
  
 ![ExceptionHandler 业务流程的应用程序分支](../core/media/applicationerrorbranchofexceptionhandler.gif "ApplicationErrorBranchofExceptionHandler")  
  
 对于应用程序错误，业务流程构造描述该错误并调用的字符串**ErrorHandlerOrch**业务流程。 此业务流程将错误发送到操作的运算符将在其中确定是修复错误还是终止操作。 如果运算符修复错误，将修复的消息回来的 ErrorHandlerOrch 业务流程和重试该操作。 异常处理程序将这是通过调用**Invoke**方法**Recaller**对象中**实用程序**程序集。 **Recaller**对象使用反射来调用导致了错误的代码。  
  
 如果在调用**Invoke**成功，则异常处理程序将退出。 否则为它返回循环并尝试调用**Invoke**试。 有关详细信息**Recaller**对象，请参阅[Recaller 对象](../core/the-recaller-object.md)。  
  
## <a name="system-errors"></a>系统错误  
 下图显示了系统错误分支**ExceptionHandler**业务流程：  
  
 ![ExceptionHandler 业务流程的系统错误](../core/media/systemerrorbranchofexceptionhandler.gif "SystemErrorBranchofExceptionHandler")  
  
 对于系统错误，异常处理程序首先调用**CheckInterrupt**业务流程，然后等待一分钟。 在等待允许临时性的短期的错误，例如网络连接问题，然后重试清除。 在进行远程调用时是始终是网络问题的机会。  
  
> [!NOTE]
>  在可中断设计中，作为一般规则，你想要测试中断期间或之后任何等待时间以查看是否发生中断。  
  
 等待后的处理程序使用**Invoke**方法**Recaller**对象运行原始代码。 如果调用成功，该处理程序将退出。 否则，该处理程序将尝试两次，运行原始代码。 如果所有三个尝试失败，该处理程序构造错误字符串并调用**ErrorHandlerOrch**业务流程。  
  
 如果处理系统异常导致异常，异常块将捕获它：  
  
 ![异常处理程序的系统错误分支](../core/media/exceptionhandlerofsystemerrorbranch.gif "ExceptionHandlerofSystemErrorBranch")  
  
 如果它是系统异常，或设置一个标志，指示应用程序异常，异常处理程序将测试的类型的异常并可减少重试计数器。  
  
## <a name="the-errorhandlerorch-orchestration"></a>ErrorHandlerOrch 业务流程  
 下图显示的第一部分**ErrorHandlerOrch**业务流程：  
  
 ![错误处理程序业务流程，第一部分](../core/media/errorhandlerfirstpart.gif "ErrorHandlerFirstPart")  
  
 **ErrorHandlerOrch**业务流程的第一个测试**IsBadOrder**参数，以查看该错误是订单错误 (**IsBadOrder**为 true) 或其他一些错误。 如果错误是订单错误，它从原始订单返回地址分配消息的目标，并将消息发送回客户服务系统。 如果该错误不是订单错误，业务流程将创建一个订单错误消息，并将其发送给操作系统。  
  
 在任一错误之后, 该业务流程将侦听的响应消息或中断消息：  
  
 ![错误处理程序的第二部分](../core/media/errorhandlersecondpart.gif "ErrorHandlerSecondPart")  
  
 如果业务流程收到响应后，它将返回到调用方。 如果业务流程收到中断消息，它会将消息传递中断端口，并引发自定义**InterruptException**。  
  
 有关解决方案如何使用和处理中断的详细信息，请参阅[业务流程管理解决方案中的中断处理](../core/interrupt-handling-in-the-business-process-management-solution.md)。  
  
## <a name="see-also"></a>请参阅  
 [业务流程管理解决方案中的异常处理](../core/exception-handling-in-the-business-process-management-solution.md)   
 [自定义异常](../core/custom-exceptions.md)   
 [业务流程管理解决方案中的中断处理](../core/interrupt-handling-in-the-business-process-management-solution.md)   
 [Recaller 对象](../core/the-recaller-object.md)