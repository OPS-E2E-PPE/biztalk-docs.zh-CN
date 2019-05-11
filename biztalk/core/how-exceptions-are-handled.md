---
title: 如何处理异常 |Microsoft Docs
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
ms.openlocfilehash: fc50f8371e5417662a8b81ef119e2a33f18e8925
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344131"
---
# <a name="how-exceptions-are-handled"></a><span data-ttu-id="d0525-102">如何处理异常</span><span class="sxs-lookup"><span data-stu-id="d0525-102">How Exceptions Are Handled</span></span>
<span data-ttu-id="d0525-103">当作用域中出现异常时，将停止执行作用域中的每个逻辑线程。</span><span class="sxs-lookup"><span data-stu-id="d0525-103">When an exception occurs within a scope, each logical thread of execution in the scope is stopped.</span></span> <span data-ttu-id="d0525-104">运行时引擎尝试为相应的异常找到异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="d0525-104">The runtime engine tries to find an exception handler for the appropriate exception.</span></span>  
  
 <span data-ttu-id="d0525-105">如果找到匹配的特定类型或其基类型之一的异常处理程序，控制权将传递给该处理程序和其代码运行。</span><span class="sxs-lookup"><span data-stu-id="d0525-105">If the exception handler is found that matches the specific type or one of its base types, control passes to that handler and its code runs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0525-106">异常类型必须派生自**System.Exception**。</span><span class="sxs-lookup"><span data-stu-id="d0525-106">The exception type must be derived from **System.Exception**.</span></span>  
  
 <span data-ttu-id="d0525-107">异常处理程序是按顺序;也就是说，它们将进行检查以便确定它们是否可以处理特定异常。</span><span class="sxs-lookup"><span data-stu-id="d0525-107">Exception handlers are sequential; that is, they will be checked in order to see if they can handle a particular exception.</span></span> <span data-ttu-id="d0525-108">若要正常工作，以便处理更具体的类型出现在最前面，随后处理更普通的类型必须放置异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="d0525-108">To work properly, exception handlers must be placed so that those handling more specific types come first, followed by those handling more general types.</span></span> <span data-ttu-id="d0525-109">这是，以便您可以确保特定类型的异常由相应的处理程序，而不是设计为处理基类型。</span><span class="sxs-lookup"><span data-stu-id="d0525-109">This is so that you can ensure that an exception of a specific type is handled by the appropriate handler, rather than one designed to handle a base type.</span></span>  
  
 <span data-ttu-id="d0525-110">如果异常处理程序正常完成，控制权将传递给周围的作用域。</span><span class="sxs-lookup"><span data-stu-id="d0525-110">If the exception handler completes normally, control passes to the surrounding scope.</span></span> <span data-ttu-id="d0525-111">如果已在周围的作用域中不引发任何异常，该业务流程将继续运行。</span><span class="sxs-lookup"><span data-stu-id="d0525-111">If no exception has been thrown in the surrounding scope, the orchestration continues to run.</span></span> <span data-ttu-id="d0525-112">如果异常处理程序结束 throw 语句，将原始异常是再次引发周围的作用域生效，除非指定你想要引发的不同异常。</span><span class="sxs-lookup"><span data-stu-id="d0525-112">If the exception handler ends with a throw statement, the original exception is thrown again for the surrounding scope to act upon, unless you specify a different exception that you want to be thrown.</span></span>  
  
 <span data-ttu-id="d0525-113">如果不可以位于任何异常处理程序，将运行默认异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="d0525-113">If no exception handler can be located, the default exception handler will run.</span></span> <span data-ttu-id="d0525-114">作用域的默认异常处理程序将调用的任何嵌套事务、 补偿，然后再次引发该异常。</span><span class="sxs-lookup"><span data-stu-id="d0525-114">The default exception handler for a scope will call the compensations for any nested transactions, and then throw the exception again.</span></span> <span data-ttu-id="d0525-115">如果您编写自己的异常处理程序，您可以选择不传播该异常。</span><span class="sxs-lookup"><span data-stu-id="d0525-115">If you write your own exception handler, you can choose not to propagate the exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0525-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0525-116">See Also</span></span>  
 [<span data-ttu-id="d0525-117">异常</span><span class="sxs-lookup"><span data-stu-id="d0525-117">Exceptions</span></span>](../core/exceptions.md)