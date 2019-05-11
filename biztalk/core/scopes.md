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
# <a name="scopes"></a>作用域
作用域是一个框架，用于对分组操作。 它主要用于事务性执行和异常处理。  
  
 一个作用域包含一个或多个块。 它具有一个主体，并可以选择附加到其任意数量的异常处理块。 它可能具有可选的补偿模块，具体取决于作用域的性质。 某些作用域将仅用于异常处理，并且不需要进行补偿。 其他作用域将是显式事务性的并且始终具有一个默认的补偿处理程序，以及为其创建一个可选的补偿处理程序。 事务作用域也会默认异常处理程序和任意数量的其他异常处理程序为其创建。  
  
## <a name="synchronized-scopes"></a>同步的作用域  
 您可以指定作用域都已同步或不同步。 通过同步作用域，可确保通过在业务流程中的一个或多个并行操作不到编写访问其中的任何共享的数据也将它写入到另一个操作正在读取它时。  
  
 原子事务作用域始终保持同步。 同步的作用域中的所有操作被都视为同步的因为任何其异常处理程序中的所有操作。 不同步事务的作用域的补偿处理程序中的操作。  
  
> [!CAUTION]
>  请注意，您仍可运行死锁条件是否不会仔细设计您的流程。 例如： 业务流程 A 中并行的两个分支的访问相同的消息，以将其发送的一个，另一个用于接收它，因此这两个必须具有同步的作用域。 第二个业务流程接收消息，并将其发送回。 就可以在业务流程 A 中的发送分支会收到在接收分支前的其锁，并将最终出现死锁。  
  
## <a name="nesting-of-scopes"></a>作用域嵌套  
 可以嵌套**作用域**内其他形状**作用域**形状。 嵌套作用域的规则如下所示：  
  
-   不能在同步作用域，包括同步的作用域的异常处理程序内嵌套事务性和/或同步作用域。  
  
-   原子事务作用域不能在其内部嵌套的其他任何事务的作用域。  
  
-   事务作用域不能嵌套在非事务性作用域或业务流程中。  
  
-   您可以嵌套达 21 级深度的作用域。  
  
-   **调用业务流程**形状可以包括在作用域内，但调用的业务流程都被看作相同与任何其他嵌套事务，并将应用相同的规则。  
  
-   **启动业务流程**形状可以包括在作用域内。 嵌套的限制不适用于启动业务流程。  
  
## <a name="scope-variables"></a>作用域变量  
 您可以声明变量，例如消息和相关集在作用域级别。 然而，不能使用相同的名称与业务流程变量，作用域变量不允许名称隐藏。  
  
## <a name="see-also"></a>请参阅  
 [使用事务和处理异常](../core/using-transactions-and-handling-exceptions.md)   
 [原子事务](../core/atomic-transactions.md)