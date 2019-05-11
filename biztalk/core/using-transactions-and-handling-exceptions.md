---
title: 使用事务和处理异常 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transactions, orchestrations
- orchestrations, transactions
- orchestrations, errors
- transactions
- errors, orchestrations
- transactions, BizTalk Server Orchestration Engine
- errors, Scope shape [Orchestration Designer]
- Scope shape [Orchestration Designer], errors
- Scope shape [Orchestration Designer], transactions
ms.assetid: bb38f5eb-6641-4e7c-8e2a-c474fc739999
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eac1ae71e9ff176156691fbb30a79c9d423b58da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396750"
---
# <a name="using-transactions-and-handling-exceptions"></a>使用事务和处理异常
在设计业务流程时，应仔细考虑可能会出现问题和如何最好地处理它们。 许多业务流程具有多个潜在的故障点。 为任意数量的其他原因; 可能会出现问题例如，服务器可能停机或一条消息的格式可能是错误。  
  
 它是努力的对的运行时间较长或复杂的业务流程，了解跟踪其状态，并报告错误，因为它们发生，以便您可以准确地使用很少解决问题尤其重要。 它是业务流程就可以保持一组密切相关的操作的完整性同等重要，以便像永远不会发生，如果事务的一部分执行，而另一个却没有，可以回滚整个事务。  
  
 BizTalk 业务流程使您能够保证工作的原子性，也就是说，相关操作的完整性，即使外部系统参与事务。 它提供用于处理错误，维护业务流程的状态并解决问题，在发生通过事务、 补偿和异常处理的工具。  
  
 作为用于事务和异常处理框架，业务流程设计器提供了**作用域**形状。 作用域可以具有事务类型、 补偿和任意数量的异常处理程序。  
  
 设置事务和异常处理的步骤如下：  
  
-   创建一个作用域。  
  
-   标识所需的事务的类型。  
  
-   确定将需要什么来进行补偿。  
  
-   识别潜在的错误。  
  
-   添加相应的异常处理程序和补偿代码。  
  
## <a name="examples-of-using-transactions-exception-handlings-and-compensations"></a>使用事务、 异常处理和补偿的示例  
  
-   [错误处理（BizTalk Server 示例文件夹）](../core/error-handling-biztalk-server-samples-folder.md)  
  
-   [补偿（BizTalk Server 示例）](../core/compensation-biztalk-server-sample.md)  
  
-   从下载 SDK 示例"原子事务与 COM + 服务组件中业务流程" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
-   从下载 SDK 示例"使用 SQL 适配器与原子事务在业务流程" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
-   从下载 SDK 示例"使用长时间运行的事务在业务流程" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
-   从下载 SDK 示例"异常处理在业务流程" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [作用域](../core/scopes.md)  
  
-   [如何配置作用域形状](../core/how-to-configure-the-scope-shape.md)  
  
-   [使业务流程成为事务性业务流程](../core/making-orchestrations-transactional.md)  
  
-   [异常](../core/exceptions.md)  
  
-   [补偿](../core/compensation.md)  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk 消息引擎](../core/using-the-biztalk-messaging-engine.md)