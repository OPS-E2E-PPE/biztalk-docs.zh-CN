---
title: "如何添加 Catch 异常 Block5 |Microsoft 文档"
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
ms.assetid: 4875060c-976c-40e7-830a-ffd1a47ba68a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6c045677fb2d177377725a3f11e81a5c5c70f9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-catch-exception-block"></a>如何添加 Catch 异常块
若要添加**捕获异常**阻止**作用域**形状，**事务类型**属性**作用域**形状必须设置为**无**或**长时间运行的**。  
  
### <a name="to-add-a-catch-exception-block"></a>若要添加 catch 异常块  
  
1.  右键单击**作用域**形状，并依次**新异常处理程序**。  
  
     A**捕获异常**块添加到紧跟在关联的业务流程**作用域**形状。  
  
2.  在**属性**窗口中，指定的属性。  
  
     最重要的属性是**异常对象类型**; 这是它将捕获的消息的类型。  
  
    |属性|Description|  
    |--------------|-----------------|  
    |**异常对象名称**|为异常处理程序捕获的异常对象中指定一个名称。|  
    |**异常对象类型**|确定此异常处理程序将要捕获的从 System.Exception 派生的对象类型。|  
  
3.  在**属性**窗口，请在**异常对象类型**列表中，选择**一般异常**。  
  
4.  内部**捕获异常**块中，添加形状来创建用于处理异常的进程。  
  
    1.  右键单击以下**CatchException**和指向**插入形状**，然后选择**构造消息**。  
  
    2.  在双击**MessageAssignment**以打开文本编辑器并输入消息赋值。  
  
         例如，键入 `Message_3 = Test`。  
  
## <a name="see-also"></a>另请参阅  
 [完成的异常消息](../core/completing-the-exception-message1.md)   
 [如何添加作用域形状](../core/how-to-add-a-scope-shape5.md)   
 [使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling5.md)