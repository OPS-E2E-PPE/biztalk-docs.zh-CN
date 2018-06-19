---
title: 作用域 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scopes, exception handling
- Scope shape [Orchestration Designer], nesting
- scopes, variables
- scopes, Scope shape [Orchestration Designer]
- Scope shape [Orchestration Designer], exception handling
- scopes, transactions
- scopes, synchronization
- scopes, nesting
- Scope shape [Orchestration Designer], transactions
ms.assetid: 51d81ce4-0034-4415-b6ab-4c952737c1bd
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bc4d1b5d926540477293591ade8123126be1b84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269773"
---
# <a name="scopes"></a><span data-ttu-id="fbc61-102">作用域</span><span class="sxs-lookup"><span data-stu-id="fbc61-102">Scopes</span></span>
<span data-ttu-id="fbc61-103">作用域是用于对操作进行分组的一种框架。</span><span class="sxs-lookup"><span data-stu-id="fbc61-103">A scope is a framework for grouping actions.</span></span> <span data-ttu-id="fbc61-104">作用域主要用于事务性执行和异常处理。</span><span class="sxs-lookup"><span data-stu-id="fbc61-104">It is primarily used for transactional execution and exception handling.</span></span>  
  
 <span data-ttu-id="fbc61-105">一个作用域包含一个或多个块。</span><span class="sxs-lookup"><span data-stu-id="fbc61-105">A scope contains one or more blocks.</span></span> <span data-ttu-id="fbc61-106">作用域具有正文并且可以选择附加任意数目的异常处理块。</span><span class="sxs-lookup"><span data-stu-id="fbc61-106">It has a body and can optionally have appended to it any number of exception-handling blocks.</span></span> <span data-ttu-id="fbc61-107">它也可以具有可选的补偿模块，这由该作用域的特性决定。</span><span class="sxs-lookup"><span data-stu-id="fbc61-107">It may have an optional compensation block as well, depending on the nature of the scope.</span></span> <span data-ttu-id="fbc61-108">某些作用域将仅用于异常处理，不要求补偿。</span><span class="sxs-lookup"><span data-stu-id="fbc61-108">Some scopes will be purely for exception handling, and will not require compensation.</span></span> <span data-ttu-id="fbc61-109">其他一些作用域将是显式事务性的，并且将始终具有默认的补偿处理程序以及您为它创建的可选的补偿处理程序。</span><span class="sxs-lookup"><span data-stu-id="fbc61-109">Other scopes will be explicitly transactional, and will always have a default compensation handler, along with an optional compensation handler that you create for it.</span></span> <span data-ttu-id="fbc61-110">事务性作用域也将具有默认的异常处理程序以及您为它创建的任意数目的附加异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="fbc61-110">A transactional scope will also have a default exception handler and any number of additional exception handlers that you create for it.</span></span>  
  
## <a name="synchronized-scopes"></a><span data-ttu-id="fbc61-111">同步的作用域</span><span class="sxs-lookup"><span data-stu-id="fbc61-111">Synchronized scopes</span></span>  
 <span data-ttu-id="fbc61-112">您可以指定作用域是同步的还是非同步的。</span><span class="sxs-lookup"><span data-stu-id="fbc61-112">You can specify that scopes are synchronized or not synchronized.</span></span> <span data-ttu-id="fbc61-113">通过同步某个作用域，您将确保在该作用域中访问的任何共享数据都不会被一个或多个并行操作写入您的业务流程，也不会在其他操作正在读取它时写入业务流程。</span><span class="sxs-lookup"><span data-stu-id="fbc61-113">By synchronizing a scope, you ensure that any shared data that is accessed within it will not be written to by one or more parallel actions in your orchestration, nor will it be written to while another action is reading it.</span></span>  
  
 <span data-ttu-id="fbc61-114">原子事务作用域始终是同步的。</span><span class="sxs-lookup"><span data-stu-id="fbc61-114">Atomic transaction scopes are always synchronized.</span></span> <span data-ttu-id="fbc61-115">同步的作用域中的所有操作都被视为同步的，其任何异常处理程序中的所有操作也都被视为同步的。</span><span class="sxs-lookup"><span data-stu-id="fbc61-115">All actions within a synchronized scope are considered synchronized, as are all actions in any of its exception handlers.</span></span> <span data-ttu-id="fbc61-116">事务作用域的补偿处理程序中的操作是非同步的。</span><span class="sxs-lookup"><span data-stu-id="fbc61-116">Actions in the compensation handler for a transactional scope are not synchronized.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="fbc61-117">请注意，如果不认真设计您的流程，仍可能会遇到死锁情况。</span><span class="sxs-lookup"><span data-stu-id="fbc61-117">Note that you can still run into a deadlock condition if you do not design your processes carefully.</span></span> <span data-ttu-id="fbc61-118">例如：业务流程 A 中并行的两个分支都访问同一消息，一个要发送该消息，一个要接收该消息，因此，这两个分支必须具有同步的作用域。</span><span class="sxs-lookup"><span data-stu-id="fbc61-118">For example: two branches of a parallel in orchestration A access the same message, one to send it and one to receive it, so both must have a synchronized scope.</span></span> <span data-ttu-id="fbc61-119">第二个业务流程接收该消息并发送回该消息。</span><span class="sxs-lookup"><span data-stu-id="fbc61-119">A second orchestration receives the message and sends it back.</span></span> <span data-ttu-id="fbc61-120">业务流程 A 中的发送分支有可能在接收分支前收到对其的锁定，因此您将以死锁结束。</span><span class="sxs-lookup"><span data-stu-id="fbc61-120">It is possible that the sending branch in orchestration A will receive its locks before the receiving branch, and you will end up with a deadlock.</span></span>  
  
## <a name="nesting-of-scopes"></a><span data-ttu-id="fbc61-121">作用域嵌套</span><span class="sxs-lookup"><span data-stu-id="fbc61-121">Nesting of scopes</span></span>  
 <span data-ttu-id="fbc61-122">可以嵌套**作用域**内其他形状**作用域**形状。</span><span class="sxs-lookup"><span data-stu-id="fbc61-122">You can nest **Scope** shapes inside other **Scope** shapes.</span></span> <span data-ttu-id="fbc61-123">嵌套作用域的规则如下：</span><span class="sxs-lookup"><span data-stu-id="fbc61-123">The rules for nesting scopes are as follows:</span></span>  
  
-   <span data-ttu-id="fbc61-124">事务作用域和/或同步的作用域不能嵌套在同步的作用域内，包括同步的作用域的异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="fbc61-124">Transactional and/or synchronized scopes cannot be nested inside synchronized scopes, including the exception handlers of synchronized scopes.</span></span>  
  
-   <span data-ttu-id="fbc61-125">原子事务作用域不能在其内部嵌套任何其他事务作用域。</span><span class="sxs-lookup"><span data-stu-id="fbc61-125">Atomic transaction scopes cannot have any other transactional scopes nested inside them.</span></span>  
  
-   <span data-ttu-id="fbc61-126">事务作用域不能嵌套在非事务作用域或业务流程内。</span><span class="sxs-lookup"><span data-stu-id="fbc61-126">Transactional scopes cannot be nested inside nontransactional scopes or orchestrations.</span></span>  
  
-   <span data-ttu-id="fbc61-127">你可嵌套最大深度 21 级的作用域。</span><span class="sxs-lookup"><span data-stu-id="fbc61-127">You can nest scopes up to 21 levels deep.</span></span>  
  
-   <span data-ttu-id="fbc61-128">**调用 Orchestration**形状可以包括在作用域，但调用业务流程将被视为与任何其他相同嵌套事务，并应用相同的规则。</span><span class="sxs-lookup"><span data-stu-id="fbc61-128">**Call Orchestration** shapes can be included inside scopes, but the called orchestrations are treated the same as any other nested transaction, and the same rules apply.</span></span>  
  
-   <span data-ttu-id="fbc61-129">**启动业务流程**形状可以包括在作用域内。</span><span class="sxs-lookup"><span data-stu-id="fbc61-129">**Start Orchestration** shapes can be included inside scopes.</span></span> <span data-ttu-id="fbc61-130">对嵌套的限制并不适用于已启动的业务流程。</span><span class="sxs-lookup"><span data-stu-id="fbc61-130">Nesting limitations do not apply to started orchestrations.</span></span>  
  
## <a name="scope-variables"></a><span data-ttu-id="fbc61-131">作用域变量</span><span class="sxs-lookup"><span data-stu-id="fbc61-131">Scope variables</span></span>  
 <span data-ttu-id="fbc61-132">可以在作用域一级上声明消息或相关集之类的变量。</span><span class="sxs-lookup"><span data-stu-id="fbc61-132">You can declare variables such as messages and correlation sets at the scope level.</span></span> <span data-ttu-id="fbc61-133">但是，作用域变量的名称不能与业务流程变量的名称同名；不允许名称隐藏。</span><span class="sxs-lookup"><span data-stu-id="fbc61-133">You cannot use the same name for a scope variable as for an orchestration variable, however; name hiding is not allowed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbc61-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fbc61-134">See Also</span></span>  
 <span data-ttu-id="fbc61-135">[使用事务和处理异常](../core/using-transactions-and-handling-exceptions.md) </span><span class="sxs-lookup"><span data-stu-id="fbc61-135">[Using Transactions and Handling Exceptions](../core/using-transactions-and-handling-exceptions.md) </span></span>  
 [<span data-ttu-id="fbc61-136">原子事务</span><span class="sxs-lookup"><span data-stu-id="fbc61-136">Atomic Transactions</span></span>](../core/atomic-transactions.md)