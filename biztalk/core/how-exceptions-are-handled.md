---
title: 异常的处理方式 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, handlers
- scopes, errors
- errors, scopes
- handlers [adapters], errors
ms.assetid: 30b88d8a-8737-4700-b856-1b49fdf6b6d0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 004e4f29bcfc292edb33bae816a52b588a89771c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246661"
---
# <a name="how-exceptions-are-handled"></a><span data-ttu-id="20277-102">如何处理异常</span><span class="sxs-lookup"><span data-stu-id="20277-102">How Exceptions Are Handled</span></span>
<span data-ttu-id="20277-103">在某一作用域内发生异常时，该作用域内执行的每个逻辑线程都将停止。</span><span class="sxs-lookup"><span data-stu-id="20277-103">When an exception occurs within a scope, each logical thread of execution in the scope is stopped.</span></span> <span data-ttu-id="20277-104">运行时引擎将尝试为相应的异常找到异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="20277-104">The runtime engine tries to find an exception handler for the appropriate exception.</span></span>  
  
 <span data-ttu-id="20277-105">如果找到了与特定类型或其基本类型之一相符的异常处理程序，控制将传递到该处理程序并且其代码将运行。</span><span class="sxs-lookup"><span data-stu-id="20277-105">If the exception handler is found that matches the specific type or one of its base types, control passes to that handler and its code runs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20277-106">异常类型必须派生自**System.Exception**。</span><span class="sxs-lookup"><span data-stu-id="20277-106">The exception type must be derived from **System.Exception**.</span></span>  
  
 <span data-ttu-id="20277-107">异常处理程序是顺序的；也就是说，将对它们进行检查以便确定它们是否可以处理特定异常。</span><span class="sxs-lookup"><span data-stu-id="20277-107">Exception handlers are sequential; that is, they will be checked in order to see if they can handle a particular exception.</span></span> <span data-ttu-id="20277-108">为了正常工作，必须按一定的顺序放置异常处理程序，以便它们首先处理更具体的类型，随后处理更普通的类型。</span><span class="sxs-lookup"><span data-stu-id="20277-108">To work properly, exception handlers must be placed so that those handling more specific types come first, followed by those handling more general types.</span></span> <span data-ttu-id="20277-109">这样，就可以确保由适当的处理程序处理特定类型的异常，而不是由设计为处理基本类型的处理程序执行。</span><span class="sxs-lookup"><span data-stu-id="20277-109">This is so that you can ensure that an exception of a specific type is handled by the appropriate handler, rather than one designed to handle a base type.</span></span>  
  
 <span data-ttu-id="20277-110">如果该异常处理程序正常完成，则控制将传递给周围的作用域。</span><span class="sxs-lookup"><span data-stu-id="20277-110">If the exception handler completes normally, control passes to the surrounding scope.</span></span> <span data-ttu-id="20277-111">如果在周围的作用域中没有引发任何异常，则业务流程将继续运行。</span><span class="sxs-lookup"><span data-stu-id="20277-111">If no exception has been thrown in the surrounding scope, the orchestration continues to run.</span></span> <span data-ttu-id="20277-112">如果该异常处理程序由 throw 语句结束，则再次引发原始的异常，以使周围的作用域生效，除非您指定要引发的不同异常。</span><span class="sxs-lookup"><span data-stu-id="20277-112">If the exception handler ends with a throw statement, the original exception is thrown again for the surrounding scope to act upon, unless you specify a different exception that you want to be thrown.</span></span>  
  
 <span data-ttu-id="20277-113">如果无法定位任何异常处理程序，则默认的异常处理程序将运行。</span><span class="sxs-lookup"><span data-stu-id="20277-113">If no exception handler can be located, the default exception handler will run.</span></span> <span data-ttu-id="20277-114">作用域的默认异常处理程序将为任何嵌套的事务调用补偿，然后再次引发该异常。</span><span class="sxs-lookup"><span data-stu-id="20277-114">The default exception handler for a scope will call the compensations for any nested transactions, and then throw the exception again.</span></span> <span data-ttu-id="20277-115">如果您编写自己的异常处理程序，则可以选择不传播该异常。</span><span class="sxs-lookup"><span data-stu-id="20277-115">If you write your own exception handler, you can choose not to propagate the exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20277-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20277-116">See Also</span></span>  
 [<span data-ttu-id="20277-117">异常</span><span class="sxs-lookup"><span data-stu-id="20277-117">Exceptions</span></span>](../core/exceptions.md)