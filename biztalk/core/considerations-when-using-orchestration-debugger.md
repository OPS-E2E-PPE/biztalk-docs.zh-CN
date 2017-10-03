---
title: "使用业务流程调试器时的注意事项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Orchestration Debugger, modified orchestrations
- Orchestration Debugger, planning
- atomic scopes
- planning, Orchestration Debugger
- Orchestration Debugger, atomic scopes
- Orchestration Debugger, simple types
- orchestrations, modifying
ms.assetid: 55bfef48-08bd-48bb-abd5-7264e683da46
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2815da55bc74d822cb5fe2540347855db75b3a8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-when-using-orchestration-debugger"></a>使用业务流程调试器时的注意事项
以下是要考虑业务流程调试器中处理时的一些事项。  
  
## <a name="tracking-atomic-scopes"></a>跟踪原子作用域  
 业务流程可以包含原子作用域，以包括对规则引擎调用。 当附加到业务流程调试器中的某个实例时，业务流程实例中的所有原子作用域将导致显示在跟踪的事件列表的差距。 有两个原因发生这种情况：  
  
-   因为范围提交后，才执行不保存在原子事务内部形状的事件  
  
-   调试器将重新加载到列表中，末尾的事件，因此任何缺口实时会话期间保持未填充。  
  
 如果您刷新视图，则可以消除缺口。  
  
> [!NOTE]
>  不能在原子作用域内的形状上设置断点。  
  
## <a name="setting-breakpoints-in-the-exception-handler-scope"></a>异常处理程序作用域中设置断点  
 如果在设置断点异常 catch 处理程序、 异常类型必须标记为可序列化，或业务流程调试器不会在你设置的断点处停止。 这是由于，业务流程调试器时，会暂留在所需断点，因此，不可序列化对象中存在的业务流程实例状态，将引发一个持久性异常，并且在这种情况下，您也会收到DebugBreakPointFailedException 异常。  
  
## <a name="tracking-a-modified-orchestration"></a>跟踪修改后的业务流程  
 如果跟踪未更改版本号的情况下修改一个业务流程，您必须重新启动业务流程登记到的所有主机实例。 这将确保任何形状更改新部署的版本中正确显示，逐步执行业务流程调试器。  
  
## <a name="tracking-simple-types"></a>跟踪简单类型  
 业务流程调试器仅支持简单类型。 例如，如果跟踪包含.NET 对象的多部分消息可以查看所有消息部分，除了.NET 对象属性的属性。  
  
 当业务流程出现在断点处状态和业务流程调试器启动时，你可以执行以下操作：  
  
-   使用**附加**服务选项。  
  
-   查看已完成的步骤。  
  
-   查看变量和消息的状态。  
  
-   设置其他断点。  
  
-   选择**继续服务**选项。  
  
-   重复根据需要的任何步骤。  
  
## <a name="see-also"></a>另请参阅  
 [在调试器中业务流程交互模式](../core/interactive-mode-in-orchestration-debugger.md)   
 [调试业务流程](../core/debugging-an-orchestration.md)