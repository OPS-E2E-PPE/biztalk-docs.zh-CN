---
title: "如何添加 Catch 异常 Block1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions, adding Catch Exception block
- Catch Exception blocks, adding
- exception handling, Catch Exception blocks
ms.assetid: 8e4b264b-b3b0-4d83-81df-a14dc2ddeea2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7922a1527e0f6359427be992c4cc9963f8c7d93e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-catch-exception-block"></a>如何添加 Catch 异常块
**捕获异常**块代表一个异常处理程序。 **捕获异常**块附加到的末尾**作用域**中业务流程设计器形状。 你可以将作为许多附加**捕获异常**阻止根据你的需要。  
  
 你可以设置异常处理程序来处理不同种类的异常。 对每个异常处理程序，您应指定一个异常类型，该类型必须是异常或是从类 `System` 派生的对象。 如果出现了符合异常处理程序中的指定类型的异常，便会调用异常处理程序。  
  
> [!NOTE]
>  若要添加**捕获异常**阻止**作用域**形状的事务类型属性**作用域**形状必须设置为**无**或**长时间运行的**。  
  
### <a name="to-add-and-populate-a-catch-exception-block"></a>添加和填充“捕获异常”块  
  
1.  右键单击**作用域**你想要添加的形状**捕获异常**块，并依次**新异常处理程序**。  
  
     A**捕获异常**块添加到紧跟在关联的业务流程**作用域**形状。  
  
2.  在**属性**窗口中，指定的属性。  
  
     最重要的属性是“异常对象类型”；这是将要捕获的消息的类型。  
  
    |属性|Description|  
    |--------------|-----------------|  
    |异常对象名称|为异常处理程序捕获的异常对象中指定一个名称。|  
    |异常对象类型|确定此异常处理程序将要捕获的从 System.Exception 派生的对象类型。|  
  
3.  在**属性**窗口，请在**异常对象类型**列表中，选择**一般异常**。  
  
4.  内部**捕获异常**块中，添加形状来创建用于处理异常的进程。  
  
5.  右键单击以下**捕获异常**块中，依次指向**插入形状**，然后选择**构造消息**。  
  
6.  在双击**MessageAssignment**以激活文本编辑器并输入消息赋值。  
  
     例如，键入 `Message_3 = Test`。  
  
## <a name="see-also"></a>另请参阅  
 [完成的异常消息](../core/completing-the-exception-message5.md)   
 [如何添加作用域形状](../core/how-to-add-a-scope-shape2.md)   
 [使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling3.md)