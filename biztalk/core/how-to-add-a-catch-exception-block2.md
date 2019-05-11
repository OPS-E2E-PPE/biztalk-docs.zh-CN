---
title: 如何添加捕获异常块 2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Catch Exception blocks
- exceptions, Catch Exception blocks
ms.assetid: 7c8b6024-e8dc-4417-83f9-bf4032644b91
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e16fb42f9b8814ab816f64f6cf2b3a8b482fbb58
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387418"
---
# <a name="how-to-add-a-catch-exception-block"></a>如何添加捕获异常块
**捕获异常**块代表异常处理程序。 **捕获异常**块附加到的末尾**作用域**形状在业务流程设计器中的。 可以附加任意数量**捕获异常**块。  
  
 您可以将设置异常处理程序来处理不同类型的异常。 在每个异常处理程序中，指定异常类型。 这必须是异常或是从类派生的对象`System`。 如果异常引发的异常处理程序中的指定的类型相匹配，将调用该异常处理程序。  
  
> [!NOTE]
>  若要将捕获异常块添加到作用域形状，作用域形状的事务类型属性必须设置为**无**或**长期**。  
  
### <a name="to-add-and-populate-a-catch-exception-block"></a>若要添加和填充捕获异常块  
  
1.  右键单击**作用域**你想要添加的形状**捕获异常**阻止，然后依次**新建异常处理程序**。  
  
     一个**捕获异常**块添加到紧跟相关业务流程**作用域**形状。  
  
2.  在中**属性**窗口中，指定的属性。  
  
     最重要属性是**异常对象类型**; 这是将捕获的消息类型。  
  
3.  在中**属性**windows，请在**异常对象类型**列表中，选择**一般异常**。  
  
    |属性|Description|  
    |--------------|-----------------|  
    |**异常对象名称**|为指定的异常处理程序捕获的异常对象名称。|  
    |**异常对象类型**|确定对象类型 （从 System.Exception 派生的），将会捕获此异常处理程序。|  
  
4.  在捕获异常块中，添加形状以创建处理异常进程。  
  
    1.  下单击鼠标右键**CatchException** ，然后指向**插入形状**，然后选择**构造消息**。  
  
    2.  双击**MessageAssignment**以打开文本编辑器并输入消息赋值。  
  
         例如，键入 `Message_3 = Test`。  
  
## <a name="see-also"></a>请参阅  
 [完成异常消息](../core/completing-the-exception-message4.md)   
 [如何添加作用域形状](../core/how-to-add-a-scope-shape4.md)   
 [使用 BizTalk Server 的异常处理](../core/using-biztalk-server-exception-handling4.md)