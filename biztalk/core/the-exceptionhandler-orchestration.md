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
# <a name="the-exceptionhandler-orchestration"></a>ExceptionHandler 业务流程
业务流程管理解决方案使用两种类型的异常：系统异常和应用程序异常。 系统异常包括类似资源错误（例如，网络连接故障）的事项。 此类问题可能在经过一段时间后会自行解决，从而，解决方案将重试造成系统异常的所有操作。 而导致应用程序异常的错误很少能自行解决，这些错误包括逻辑错误或某些格式不一致的问题等。 此解决方案使用**ExceptionHandlerOrch**业务流程来处理系统和应用程序错误。  
  
 订单处理阶段 (**CableOrder1**， **CableOrder2**) 和其附属业务流程 (**激活**，**分析**， **取消**，**更改**，**完成**，**验证**) 所有使用**ExceptionHandlerOrch**。  
  
> [!NOTE]
>  你可能想要读取此节**ExceptionHandlerOrch**在 Microsoft 中的业务流程打开[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
## <a name="application-errors"></a>应用程序错误  
 异常处理程序首先会将错误记录通过调用**PostError**方法**ErrorHandler**对象在**实用工具**程序集。 然后，异常处理程序将测试该错误是系统错误还是应用程序错误。 以下屏幕快照显示了处理应用程序异常的业务流程分支：  
  
 ![应用程序分支 ExceptionHandler Orchestrati](../core/media/applicationerrorbranchofexceptionhandler.gif "ApplicationErrorBranchofExceptionHandler")  
  
 对于应用程序错误，业务流程构造描述错误并调用一个字符串**ErrorHandlerOrch**业务流程。 此业务流程将该错误发送到操作，其中的运算符将确定是修复该错误还是终止操作。 如果运算符修复错误，则修复后的消息将从 ErrorHandlerOrch 业务流程返回，并且重试该操作。 异常处理程序将这是通过调用**Invoke**方法**Recaller**对象在**实用工具**程序集。 **Recaller**对象使用反射来调用导致错误的代码。  
  
 如果调用**Invoke**成功，异常处理程序退出。 否则为它循环，且尝试调用**Invoke**试。 有关详细信息**Recaller**对象，请参阅[Recaller Object](../core/the-recaller-object.md)。  
  
## <a name="system-errors"></a>系统错误  
 下图显示的系统错误分支**ExceptionHandler**业务流程：  
  
 ![ExceptionHandler 业务流程的系统错误](../core/media/systemerrorbranchofexceptionhandler.gif "SystemErrorBranchofExceptionHandler")  
  
 对于系统错误，异常处理程序首先调用**CheckInterrupt**业务流程，然后等待一分钟。 通过等待，短期的暂时性错误（例如，网络连接问题）可在重试前清除。 在进行远程调用时，始终可能存在网络问题。  
  
> [!NOTE]
>  在可中断设计中，通用规则为：应在任何等待期间或之后立刻测试中断，以查看是否发生了中断。  
  
 在等待之后, 该处理程序使用**Invoke**方法**Recaller**运行的原始代码的对象。 如果调用成功，则该异常处理程序将退出。 否则，该处理程序将尝试两次以上，以运行原始代码。 如果所有三个尝试都失败，该处理程序构造错误字符串和调用**ErrorHandlerOrch**业务流程。  
  
 如果对系统异常的处理引发异常，则异常块将捕获它：  
  
 ![异常处理程序系统错误分支](../core/media/exceptionhandlerofsystemerrorbranch.gif "ExceptionHandlerofSystemErrorBranch")  
  
 异常处理程序可测试异常的类型，并可减少重试计数（如果该异常为系统异常），或设置标志以指示该异常为应用程序异常。  
  
## <a name="the-errorhandlerorch-orchestration"></a>ErrorHandlerOrch 业务流程  
 下图显示的第一部分**ErrorHandlerOrch**业务流程：  
  
 ![错误处理程序业务流程，第一部分](../core/media/errorhandlerfirstpart.gif "ErrorHandlerFirstPart")  
  
 **ErrorHandlerOrch** orchestration 第一个测试**IsBadOrder**参数，以查看错误是否错误顺序 (**IsBadOrder**为 true) 或一某些其他错误。 如果该错误为订单错误，则该业务流程将指定原始订单返回地址中消息的目标，并将该消息发送回客户服务系统。 如果不是订单错误，则该业务流程将创建一个订单错误消息，并将其发送给操作系统。  
  
 在上述任何一种错误后，该业务流程将侦听响应消息或中断消息：  
  
 ![错误处理程序的第二部分](../core/media/errorhandlersecondpart.gif "ErrorHandlerSecondPart")  
  
 如果业务流程收到响应，则它将返回到调用方。 如果业务流程收到中断消息，它将消息传递到中断端口，并引发一个自定义**InterruptException**。  
  
 有关如何解决方案使用和处理中断的详细信息，请参阅[中断业务流程管理解决方案中的处理](../core/interrupt-handling-in-the-business-process-management-solution.md)。  
  
## <a name="see-also"></a>另请参阅  
 [业务流程管理解决方案中的异常处理](../core/exception-handling-in-the-business-process-management-solution.md)   
 [自定义异常](../core/custom-exceptions.md)   
 [中断业务流程管理解决方案中的处理](../core/interrupt-handling-in-the-business-process-management-solution.md)   
 [Recaller 对象](../core/the-recaller-object.md)