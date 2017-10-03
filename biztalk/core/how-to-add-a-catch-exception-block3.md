---
title: "如何添加 Catch 异常 Block3 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer], creating
- Catch Exception block [Orchestration Designer], exception handler
- Catch Exception block [Orchestration Designer], about Catch Exception blocks
- Orchestration Designer, errors
ms.assetid: 63ca4a60-b657-452a-86fd-78968ccf2933
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1040a27a5e1273d2ad80a722deb421878de36c12
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-catch-exception-block"></a>如何添加 Catch 异常块
**捕获异常**块代表一个异常处理程序。 **捕获异常**块附加到的末尾**作用域**中业务流程设计器形状。 你可以将作为许多附加**捕获异常**阻止根据你的需要。  
  
 你可以设置异常处理程序来处理不同种类的异常。 在每个异常处理程序中，您可以指定异常类型，它必须是错误消息或派生自类的对象**System.Exception**。 如果不指定异常类型，该异常块将被视为常规异常处理程序，并且可以捕获是非派生自的异常**System.Exception**。  
  
 如果出现了符合异常处理程序中的指定类型的异常，便会调用异常处理程序。 如果某些其他异常被抛弃，它将由默认异常处理程序处理。  
  
> [!NOTE]
>  若要添加**捕获异常**阻止**作用域**形状，**事务类型**属性**作用域**形状必须设置为**无**或**长时间运行的**。  
  
### <a name="to-add-a-catch-exception-block"></a>添加“捕获异常”块  
  
1.  右键单击**作用域**你想要添加的形状**捕获异常**块，并依次**新异常处理程序**。  
  
     A**捕获异常**块添加到紧跟在关联的业务流程**作用域**形状。  
  
2.  在“属性”窗口中，指定以下属性：  
  
    |属性|Description|  
    |--------------|-----------------|  
    |异常对象名称|为异常处理程序捕获的异常对象中指定一个名称。|  
    |异常对象类型|确定此异常处理程序将要捕获的从 System.Exception 派生的对象类型。|  
  
3.  内部**捕获异常**块中，添加形状来创建用于处理异常的进程。  
  
> [!NOTE]
>  如果指定一般异常**异常**对象类型，**捕获异常**块将截获任何异常，包括那些不派生自**System.Exception**. 在这种情况下，您将没有异常对象的访问权限。 在此块中，如果你使用**引发的异常**形状使用常规异常类型中，你将会有效地重新引发捕获的异常。  
  
## <a name="see-also"></a>另请参阅  
 [异常](../core/exceptions.md)