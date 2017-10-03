---
title: "使用事务和处理异常 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab32729aa6b4f12aada623587f52728c6bd23240
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-transactions-and-handling-exceptions"></a>使用事务和处理异常
在您设计某一业务流程时，应该仔细考虑可能发生问题的地方以及如何最好地处理这些问题。 许多业务流程都存在若干潜在的故障点。 问题可能出自许多方面；例如，服务器可能停机，或者消息的格式可能不正确。  
  
 对于长期或复杂业务流程尤其重要的是，应该跟踪其状态并且在错误发生时报告错误，以便您可以轻松、准确地解决问题。 对于业务流程同样重要的是，需要维护一组密切相关的操作的完整性，以便如果事务的某一部分执行，而另一部分未执行，整个事务都可以回滚到从未发生任何事务时的状态。  
  
 通过 BizTalk 业务流程，您可以确保工作的原子性；也就是说，甚至在外部系统参与事务时，也能够确保相关操作的完整性。 它为您提供各种工具来处理错误，维护业务流程的状态，以及通过事务、补偿和异常处理在发生问题时解决问题。  
  
 业务流程设计器提供一个框架，用于事务和异常处理，作为**作用域**形状。 作用域可以具有事务类型、补偿和任意数目的异常处理程序。  
  
 设置事务和异常处理的步骤如下：  
  
-   创建一个范围。  
  
-   标识所需事务的类型。  
  
-   确定需要补偿的内容。  
  
-   标识潜在错误。  
  
-   添加适当的异常处理程序和补偿代码。  
  
## <a name="examples-of-using-transactions-exception-handlings-and-compensations"></a>使用事务、异常处理和补偿的示例  
  
-   [错误处理 （BizTalk Server 示例文件夹中）](../core/error-handling-biztalk-server-samples-folder.md)  
  
-   [补偿 （BizTalk Server 示例）](../core/compensation-biztalk-server-sample.md)  
  
-   从下载 SDK 示例"原子事务与 COM + 服务组件中业务流程" [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
-   从下载 SDK 示例"使用 SQL 适配器与原子事务中业务流程" [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
-   从下载 SDK 示例"使用长时间运行事务中业务流程" [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
-   从下载 SDK 示例"异常处理中业务流程" [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [作用域](../core/scopes.md)  
  
-   [如何配置作用域形状](../core/how-to-configure-the-scope-shape.md)  
  
-   [使业务流程事务](../core/making-orchestrations-transactional.md)  
  
-   [异常](../core/exceptions.md)  
  
-   [补偿](../core/compensation.md)  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk 消息传送引擎](../core/using-the-biztalk-messaging-engine.md)