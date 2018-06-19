---
title: 长时间运行事务 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- long-running transactions, about long-running transactions
- atomic transactions, long-running transactions
- long-running transactions, orchestrations
- long-running transactions, nesting
- scopes, examples
- orchestrations, transactions
- compensations, long-running transactions
- compensations, customizing
- transactions, long-running
- transactions, compensation blocks
- long-running transactions
- long-running transactions, timeouts
- compensations, examples
- fault tolerance, long-running transactions
- transactions, examples
- orchestrations, long-running transactions
- transactions, atomic
- transactions, fault tolerance
- scopes, long-running transactions
- long-running transactions, fault tolerance
- transactions, nesting
- examples, scopes
ms.assetid: 4bf4d0c8-903a-411f-963b-bd4cfdfc2958
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86c419c79b9de6287a0361dfe4e2e6b9dc555153
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262773"
---
# <a name="long-running-transactions"></a>长时间运行的事务
长期事务是 BizTalk 业务流程中常用的重要构造。 它们提供的功能可帮助您实现自定义的基于作用域的补偿、自定义的基于作用域的异常处理以及嵌套事务，因此，您可以很灵活地设计可靠的事务结构。  
  
 如果事务可能需要长时间运行并且不需要完整的 ACID 属性（即，不需要确保数据与其他事务隔离），则可以使用长期事务。 长期事务可能具有较长的不活动时间，通常是由于等待外部消息到达造成的。  
  
 长期事务拥有一致性和持久性，但不具备原子性和隔离。 长期事务内的数据不锁定；其他进程或应用程序可以对数据进行修改。 不保持状态更新的隔离属性，因为保持长期锁定不现实。  
  
 长期事务的提交不同于原子事务的提交。 没有针对结果的分布式协调的隐式假定（长期事务仅存在于单个业务流程实例中）。 而是在长期事务中的最后一个语句完成时，代表该事务已提交。 事务中止的情况下，不会“自动”回滚状态。 这种回滚可以通过编写异常处理程序和补偿处理程序来实现。  
  
 作用域可通过声明变量、消息和 .NET 组件，定义自己的状态。 长期事务能够访问自己的作用域的状态信息、封闭它的任何作用域以及在业务流程内全局定义的任何状态信息。 长期事务不能够访问不封闭它的任何作用域的状态信息。  
  
## <a name="nesting"></a>嵌套  
 长期事务可以包含原子事务或其他长期事务。 它们可以嵌套到任意深度。 例如，您的事务可以包含两个其他的长期事务，这两个事务又可以包含原子事务。  
  
 如果整体事务的一个或多个组件需要是原子的，而该整体事务又需要是长期的，则嵌套将很有用。 让我们看一下一个接收和履行采购订单的例子。 该采购订单可能会在任何时候到达，并且履行订单的不同步骤可能需要一定时间才能完成，但您仍想要将整个过程作为一个事务处理。 显然，此例子中的整体事务需要是长期事务，但对于个别步骤，例如确认付款，可能需要是原子的。  
  
> [!NOTE]
>  不能在并非事务性的作用域或业务流程内嵌套事务性作用域。 并非事务性的封闭作用域或业务流程将不会管理状态，因为它必须正确处理其中任何作用域的状态管理。  
  
> [!NOTE]
>  同步的事务不能包括任何其他事务或同步的作用域。  
  
## <a name="compensation"></a>补偿  
 长期事务可以指定某一补偿模块，此补偿模块将在事务提交后被调用以补偿该事务的活动。 它可能只是撤消事务（如果可能），或者执行以某种方式帮助减轻事务影响的某些其他功能（例如通知）。 如果您没有添加自己的补偿代码，则默认情况下运行时引擎将调用内部事务的补偿模块，长期事务和原子事务都采用相反顺序，即以最后提交的事务开始、以最先提交的事务结束。  
  
> [!NOTE]
>  补偿只能对已成功提交的事务进行。  
  
## <a name="fault-tolerance"></a>容错  
 事务支持容错，以便从内部错误（例如机器故障和软件错误）和外部错误（例如取消消息）恢复。 在发生事务错误时，并不自动回滚长期事务内的部分更新，因为它们位于 ACID 事务中。  
  
 在发生错误时将调用长期事务的异常代码块。 异常代码块包含一组您编写的错误处理程序，用于处理在事务执行期间可能导致的任何错误。 您可以借助消息、变量和对象的最后已知状态来处理错误。  
  
 通常，您将希望异常处理程序评估在发生异常时业务流程的状态，基于该状态采取任何必要措施，并且调用任何嵌套事务的补偿。  
  
 在发生错误时，将中断长期事务的执行。 长期事务不能在发生错误后恢复。  
  
## <a name="see-also"></a>另请参阅  
 [使用长时间运行事务的方案](../core/scenarios-using-long-running-transactions.md)   
 [原子事务](../core/atomic-transactions.md)   
 [使用事务和处理异常](../core/using-transactions-and-handling-exceptions.md)