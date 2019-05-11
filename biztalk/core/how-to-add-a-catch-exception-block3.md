---
title: 如何添加捕获异常 Block3 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer], creating
- Catch Exception block [Orchestration Designer], exception handler
- Catch Exception block [Orchestration Designer], about Catch Exception blocks
- Orchestration Designer, errors
ms.assetid: 63ca4a60-b657-452a-86fd-78968ccf2933
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35746e0bc8e9bbadb8deffb5287943a95fd77e77
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343948"
---
# <a name="how-to-add-a-catch-exception-block"></a>如何添加捕获异常块
**捕获异常**块代表异常处理程序。 **捕获异常**块附加到的末尾**作用域**形状在业务流程设计器中的。 可以附加任意数量**捕获异常**块。  
  
 您可以将设置异常处理程序来处理不同类型的异常。 在每个异常处理程序中，指定一个异常类型，该错误消息或是从类派生的对象必须是类型**System.Exception**。 如果不指定异常类型，异常块将被视为一般异常处理程序，并且可以捕获不是从派生的异常**System.Exception**。  
  
 如果异常引发的异常处理程序中的指定的类型相匹配，将调用该异常处理程序。 如果引发了某些其他异常，它将由默认异常处理程序处理。  
  
> [!NOTE]
>  若要添加**捕获异常**阻止**作用域**形状，**事务类型**属性的**范围**形状必须设置为**None**或**长时间运行的**。  
  
### <a name="to-add-a-catch-exception-block"></a>若要添加捕获异常块  
  
1.  右键单击**作用域**你想要添加的形状**捕获异常**阻止，然后依次**新建异常处理程序**。  
  
     一个**捕获异常**块添加到紧跟相关业务流程**作用域**形状。  
  
2.  在属性窗口中，指定以下属性：  
  
    |属性|Description|  
    |--------------|-----------------|  
    |异常对象名称|为指定的异常处理程序捕获的异常对象名称。|  
    |异常对象类型|确定对象类型 （从 System.Exception 派生的），将会捕获此异常处理程序。|  
  
3.  内部**捕获异常**块中，添加形状以创建处理异常进程。  
  
> [!NOTE]
>  如果指定为常规异常**异常**对象类型，**捕获异常**块将会截获所有异常，包括那些不派生自**System.Exception**. 在这种情况下，您将没有异常对象的访问权限。 在此块中，如果您使用**引发异常**形状与常规异常类型，您将会重新引发已捕获的异常。  
  
## <a name="see-also"></a>请参阅  
 [异常](../core/exceptions.md)