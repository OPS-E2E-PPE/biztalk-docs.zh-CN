---
title: 使用业务流程调试器时的注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e3e244691d61ef27c55f606414dd08857d58f14
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998150"
---
# <a name="considerations-when-using-orchestration-debugger"></a>使用业务流程调试器时的注意事项
以下是一些需要处理业务流程调试器时，请考虑事项。  
  
## <a name="tracking-atomic-scopes"></a>跟踪原子作用域  
 业务流程可以包含原子作用域，以包括对规则引擎的调用。 当附加到业务流程调试器中的某个实例时，业务流程实例中的任何原子作用域将导致跟踪的事件列表中出现间隔。 以下两个原因发生这种情况：  
  
- 因为在作用域提交之前不会持久化原子事务中形状的事件  
  
- 调试器重新加载到列表的末尾上的事件，以便在实时会话过程中的空白保持未填充。  
  
  如果刷新视图，则可以消除间隙。  
  
> [!NOTE]
>  不能在原子作用域内的形状上设置断点。  
  
## <a name="setting-breakpoints-in-the-exception-handler-scope"></a>在异常处理程序作用域中设置断点  
 如果在设置了断点异常 catch 处理程序、 异常类型必须标记为可序列化，或业务流程调试器将在您设置的断点处停止。 这是因为，业务流程调试器会暂留在所需断点，因此，在业务流程实例状态没有非可序列化对象，将引发一个持久性异常，并且在这种情况下，你将收到DebugBreakPointFailedException 异常。  
  
## <a name="tracking-a-modified-orchestration"></a>跟踪已修改的业务流程  
 如果您跟踪在不更改版本号的情况下修改业务流程，必须重新启动该业务流程登记到的所有主机实例。 这可确保任何形状更改新部署版本中正确显示，在逐步执行业务流程调试器。  
  
## <a name="tracking-simple-types"></a>跟踪的简单类型  
 业务流程调试器仅支持简单类型。 例如，如果跟踪包含.NET 对象的多部分消息可以查看所有消息部分，但.NET 对象属性的属性。  
  
 当业务流程将开始出现在断点处的状态和业务流程调试器时，可以执行以下操作：  
  
-   使用**附加**服务选项。  
  
-   查看已完成的步骤。  
  
-   查看变量和消息的状态。  
  
-   设置其他断点。  
  
-   选择**继续服务**选项。  
  
-   重复所需的任何步骤。  
  
## <a name="see-also"></a>请参阅  
 [业务流程调试器中的交互模式](../core/interactive-mode-in-orchestration-debugger.md)   
 [调试业务流程](../core/debugging-an-orchestration.md)