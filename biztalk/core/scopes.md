---
title: 作用域 |Microsoft Docs
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
ms.openlocfilehash: 67d10fa444b8bf5a427fe48c70655c233f06eef9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395535"
---
# <a name="scopes"></a><span data-ttu-id="79e35-102">作用域</span><span class="sxs-lookup"><span data-stu-id="79e35-102">Scopes</span></span>
<span data-ttu-id="79e35-103">作用域是一个框架，用于对分组操作。</span><span class="sxs-lookup"><span data-stu-id="79e35-103">A scope is a framework for grouping actions.</span></span> <span data-ttu-id="79e35-104">它主要用于事务性执行和异常处理。</span><span class="sxs-lookup"><span data-stu-id="79e35-104">It is primarily used for transactional execution and exception handling.</span></span>  
  
 <span data-ttu-id="79e35-105">一个作用域包含一个或多个块。</span><span class="sxs-lookup"><span data-stu-id="79e35-105">A scope contains one or more blocks.</span></span> <span data-ttu-id="79e35-106">它具有一个主体，并可以选择附加到其任意数量的异常处理块。</span><span class="sxs-lookup"><span data-stu-id="79e35-106">It has a body and can optionally have appended to it any number of exception-handling blocks.</span></span> <span data-ttu-id="79e35-107">它可能具有可选的补偿模块，具体取决于作用域的性质。</span><span class="sxs-lookup"><span data-stu-id="79e35-107">It may have an optional compensation block as well, depending on the nature of the scope.</span></span> <span data-ttu-id="79e35-108">某些作用域将仅用于异常处理，并且不需要进行补偿。</span><span class="sxs-lookup"><span data-stu-id="79e35-108">Some scopes will be purely for exception handling, and will not require compensation.</span></span> <span data-ttu-id="79e35-109">其他作用域将是显式事务性的并且始终具有一个默认的补偿处理程序，以及为其创建一个可选的补偿处理程序。</span><span class="sxs-lookup"><span data-stu-id="79e35-109">Other scopes will be explicitly transactional, and will always have a default compensation handler, along with an optional compensation handler that you create for it.</span></span> <span data-ttu-id="79e35-110">事务作用域也会默认异常处理程序和任意数量的其他异常处理程序为其创建。</span><span class="sxs-lookup"><span data-stu-id="79e35-110">A transactional scope will also have a default exception handler and any number of additional exception handlers that you create for it.</span></span>  
  
## <a name="synchronized-scopes"></a><span data-ttu-id="79e35-111">同步的作用域</span><span class="sxs-lookup"><span data-stu-id="79e35-111">Synchronized scopes</span></span>  
 <span data-ttu-id="79e35-112">您可以指定作用域都已同步或不同步。</span><span class="sxs-lookup"><span data-stu-id="79e35-112">You can specify that scopes are synchronized or not synchronized.</span></span> <span data-ttu-id="79e35-113">通过同步作用域，可确保通过在业务流程中的一个或多个并行操作不到编写访问其中的任何共享的数据也将它写入到另一个操作正在读取它时。</span><span class="sxs-lookup"><span data-stu-id="79e35-113">By synchronizing a scope, you ensure that any shared data that is accessed within it will not be written to by one or more parallel actions in your orchestration, nor will it be written to while another action is reading it.</span></span>  
  
 <span data-ttu-id="79e35-114">原子事务作用域始终保持同步。</span><span class="sxs-lookup"><span data-stu-id="79e35-114">Atomic transaction scopes are always synchronized.</span></span> <span data-ttu-id="79e35-115">同步的作用域中的所有操作被都视为同步的因为任何其异常处理程序中的所有操作。</span><span class="sxs-lookup"><span data-stu-id="79e35-115">All actions within a synchronized scope are considered synchronized, as are all actions in any of its exception handlers.</span></span> <span data-ttu-id="79e35-116">不同步事务的作用域的补偿处理程序中的操作。</span><span class="sxs-lookup"><span data-stu-id="79e35-116">Actions in the compensation handler for a transactional scope are not synchronized.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="79e35-117">请注意，您仍可运行死锁条件是否不会仔细设计您的流程。</span><span class="sxs-lookup"><span data-stu-id="79e35-117">Note that you can still run into a deadlock condition if you do not design your processes carefully.</span></span> <span data-ttu-id="79e35-118">例如： 业务流程 A 中并行的两个分支的访问相同的消息，以将其发送的一个，另一个用于接收它，因此这两个必须具有同步的作用域。</span><span class="sxs-lookup"><span data-stu-id="79e35-118">For example: two branches of a parallel in orchestration A access the same message, one to send it and one to receive it, so both must have a synchronized scope.</span></span> <span data-ttu-id="79e35-119">第二个业务流程接收消息，并将其发送回。</span><span class="sxs-lookup"><span data-stu-id="79e35-119">A second orchestration receives the message and sends it back.</span></span> <span data-ttu-id="79e35-120">就可以在业务流程 A 中的发送分支会收到在接收分支前的其锁，并将最终出现死锁。</span><span class="sxs-lookup"><span data-stu-id="79e35-120">It is possible that the sending branch in orchestration A will receive its locks before the receiving branch, and you will end up with a deadlock.</span></span>  
  
## <a name="nesting-of-scopes"></a><span data-ttu-id="79e35-121">作用域嵌套</span><span class="sxs-lookup"><span data-stu-id="79e35-121">Nesting of scopes</span></span>  
 <span data-ttu-id="79e35-122">可以嵌套**作用域**内其他形状**作用域**形状。</span><span class="sxs-lookup"><span data-stu-id="79e35-122">You can nest **Scope** shapes inside other **Scope** shapes.</span></span> <span data-ttu-id="79e35-123">嵌套作用域的规则如下所示：</span><span class="sxs-lookup"><span data-stu-id="79e35-123">The rules for nesting scopes are as follows:</span></span>  
  
-   <span data-ttu-id="79e35-124">不能在同步作用域，包括同步的作用域的异常处理程序内嵌套事务性和/或同步作用域。</span><span class="sxs-lookup"><span data-stu-id="79e35-124">Transactional and/or synchronized scopes cannot be nested inside synchronized scopes, including the exception handlers of synchronized scopes.</span></span>  
  
-   <span data-ttu-id="79e35-125">原子事务作用域不能在其内部嵌套的其他任何事务的作用域。</span><span class="sxs-lookup"><span data-stu-id="79e35-125">Atomic transaction scopes cannot have any other transactional scopes nested inside them.</span></span>  
  
-   <span data-ttu-id="79e35-126">事务作用域不能嵌套在非事务性作用域或业务流程中。</span><span class="sxs-lookup"><span data-stu-id="79e35-126">Transactional scopes cannot be nested inside nontransactional scopes or orchestrations.</span></span>  
  
-   <span data-ttu-id="79e35-127">您可以嵌套达 21 级深度的作用域。</span><span class="sxs-lookup"><span data-stu-id="79e35-127">You can nest scopes up to 21 levels deep.</span></span>  
  
-   <span data-ttu-id="79e35-128">**调用业务流程**形状可以包括在作用域内，但调用的业务流程都被看作相同与任何其他嵌套事务，并将应用相同的规则。</span><span class="sxs-lookup"><span data-stu-id="79e35-128">**Call Orchestration** shapes can be included inside scopes, but the called orchestrations are treated the same as any other nested transaction, and the same rules apply.</span></span>  
  
-   <span data-ttu-id="79e35-129">**启动业务流程**形状可以包括在作用域内。</span><span class="sxs-lookup"><span data-stu-id="79e35-129">**Start Orchestration** shapes can be included inside scopes.</span></span> <span data-ttu-id="79e35-130">嵌套的限制不适用于启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="79e35-130">Nesting limitations do not apply to started orchestrations.</span></span>  
  
## <a name="scope-variables"></a><span data-ttu-id="79e35-131">作用域变量</span><span class="sxs-lookup"><span data-stu-id="79e35-131">Scope variables</span></span>  
 <span data-ttu-id="79e35-132">您可以声明变量，例如消息和相关集在作用域级别。</span><span class="sxs-lookup"><span data-stu-id="79e35-132">You can declare variables such as messages and correlation sets at the scope level.</span></span> <span data-ttu-id="79e35-133">然而，不能使用相同的名称与业务流程变量，作用域变量不允许名称隐藏。</span><span class="sxs-lookup"><span data-stu-id="79e35-133">You cannot use the same name for a scope variable as for an orchestration variable, however; name hiding is not allowed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79e35-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="79e35-134">See Also</span></span>  
 <span data-ttu-id="79e35-135">[使用事务和处理异常](../core/using-transactions-and-handling-exceptions.md) </span><span class="sxs-lookup"><span data-stu-id="79e35-135">[Using Transactions and Handling Exceptions](../core/using-transactions-and-handling-exceptions.md) </span></span>  
 [<span data-ttu-id="79e35-136">原子事务</span><span class="sxs-lookup"><span data-stu-id="79e35-136">Atomic Transactions</span></span>](../core/atomic-transactions.md)