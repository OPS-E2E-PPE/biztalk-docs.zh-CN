---
title: 长时间运行的事务 |Microsoft Docs
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
ms.openlocfilehash: 99fb048c158b758e125d82f50ce2771bf0ede94f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330394"
---
# <a name="long-running-transactions"></a>长时间运行的事务
长时间运行的事务是 BizTalk 业务流程中的重要的是，常用构造。 它们为您提供用于自定义基于作用域的补偿、 自定义基于作用域的异常处理，以及嵌套的事务，所有这些为您提供很灵活地设计可靠的事务体系结构功能的功能。  
  
 如果事务可能需要长时间运行并且不需要完整的 ACID 属性，可以使用一个长时间运行的事务 （即，您不需要与其他事务保证的数据隔离）。 一个长时间运行的事务可能很长一段非活动状态，通常由于等待外部消息到达。  
  
 长时间运行的事务拥有一致性和持久性，但不是原子性和隔离。 一个长时间运行的事务内的数据不被锁定则其他进程或应用程序可以修改它。 因为是不切实际的了很长时间持有锁不会保留状态更新的隔离属性。  
  
 原子事务的提交不同于长时间运行事务的承诺。 没有针对结果 （仅在单个业务流程实例中存在一个长时间运行的事务） 的分布式协调的隐式假定。 而是一个长时间运行的事务被视为已提交的最后一个语句完成时。 没有任何"auto"回滚事务中止的情况下的状态。 通过异常和补偿处理程序可以以编程方式实现此目的。  
  
 作用域可以通过声明变量、 消息和.NET 组件来定义其自己的状态。 一个长时间运行的事务有权访问自己的作用域、 封闭它的任何作用域和业务流程内全局定义的任何状态信息的状态信息。 它并没有访问不封闭它的所有作用域的状态信息。  
  
## <a name="nesting"></a>嵌套  
 长时间运行的事务可以包含原子事务或其他长时间运行的事务。 它们可以嵌套到任意深度。 例如，您的事务可能包含两个其他长时间运行的事务，其中每个可以包含原子事务。  
  
 嵌套将很有用，当一个或多个组件的整体事务需要是原子的而整体事务需要长时间运行。 请考虑接收和履行采购订单的示例。 采购订单可以在任何时候，到达和履行订单的不同步骤可能需要时间才能完成，但仍想要将视为一个事务的整个过程。 整体事务在这种情况下明确需要长时间运行，但个别步骤，例如确认付款，可能需要是原子性。  
  
> [!NOTE]
>  不能嵌套事务性作用域内的作用域或不是事务性的业务流程。 封闭作用域或不是事务性的业务流程将不管理状态，因为它必须能够正确处理其中任何作用域的状态管理。  
  
> [!NOTE]
>  同步的事务不能包括任何其他事务或同步的作用域。  
  
## <a name="compensation"></a>补偿  
 一个长时间运行的事务可以指定将调用以补偿该事务的活动后提交的补偿模块。 它可能只需撤消事务，如果可行，或执行某些其他功能，例如通知，帮助减轻以某种方式事务的影响。 如果不添加你自己的补偿代码，运行时引擎将默认情况下调用的内部事务运行时间较长，原子的补偿模块按相反的顺序，与上次提交的事务开始和完成的第一个提交的事务。  
  
> [!NOTE]
>  补偿只能对已成功提交的事务。  
  
## <a name="fault-tolerance"></a>容错  
 事务支持容错，从恢复内部错误 （例如机器故障和软件故障） 以及外部错误 （例如取消消息）。 长时间运行的事务内的部分更新将不会回滚自动当发生事务失败，因为它们位于 ACID 事务。  
  
 在发生错误时调用长时间运行事务的异常代码块。 异常代码块包含一组您编写的任何事务执行期间可能出现的错误处理的错误处理程序。 您可以借助消息、 变量和对象处理错误的最后一个已知状态。  
  
 您通常希望异常处理程序评估在发生异常时业务流程的状态、 执行任何必要的操作，根据该状态，以及在调用任何嵌套事务的补偿。  
  
 在发生错误时中断长时间运行事务的执行。 发生错误后无法恢复它。  
  
## <a name="see-also"></a>请参阅  
 [使用长时间运行事务的方案](../core/scenarios-using-long-running-transactions.md)   
 [原子事务](../core/atomic-transactions.md)   
 [使用事务和处理异常](../core/using-transactions-and-handling-exceptions.md)