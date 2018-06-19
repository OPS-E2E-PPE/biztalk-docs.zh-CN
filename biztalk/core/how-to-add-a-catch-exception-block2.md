---
title: 如何添加 Catch 异常 Block2 |Microsoft 文档
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
ms.openlocfilehash: 1e48ce1e6f0646acdf63ed33582f382f1baed797
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246837"
---
# <a name="how-to-add-a-catch-exception-block"></a>如何添加 Catch 异常块
**捕获异常**块代表一个异常处理程序。 **捕获异常**块附加到的末尾**作用域**中业务流程设计器形状。 你可以将作为许多附加**捕获异常**阻止根据你的需要。  
  
 你可以设置异常处理程序来处理不同种类的异常。 在每个异常处理程序中，指定一个异常类型。 此类型必须是从 `System` 类派生的异常或对象。 如果出现了符合异常处理程序中的指定类型的异常，便会调用异常处理程序。  
  
> [!NOTE]
>  若要将捕获异常块添加到作用域形状，作用域形状的事务类型属性必须设置为**无**或**运行长时间**。  
  
### <a name="to-add-and-populate-a-catch-exception-block"></a>添加和填充“捕获异常”块  
  
1.  右键单击**作用域**你想要添加的形状**捕获异常**块，并依次**新异常处理程序**。  
  
     A**捕获异常**块添加到紧跟在关联的业务流程**作用域**形状。  
  
2.  在**属性**窗口中，指定的属性。  
  
     最重要的属性是**异常对象类型**; 这是它将捕获的消息的类型。  
  
3.  在**属性**windows，请在**异常对象类型**列表中，选择**一般异常**。  
  
    |属性|Description|  
    |--------------|-----------------|  
    |**异常对象名称**|为异常处理程序捕获的异常对象中指定一个名称。|  
    |**异常对象类型**|确定此异常处理程序将要捕获的从 System.Exception 派生的对象类型。|  
  
4.  在“捕获异常”块内，添加形状以创建处理异常的流程。  
  
    1.  右键单击以下**CatchException**和指向**插入形状**，然后选择**构造消息**。  
  
    2.  在双击**MessageAssignment**以打开文本编辑器并输入消息赋值。  
  
         例如，键入 `Message_3 = Test`。  
  
## <a name="see-also"></a>另请参阅  
 [完成的异常消息](../core/completing-the-exception-message4.md)   
 [如何添加作用域形状](../core/how-to-add-a-scope-shape4.md)   
 [使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling4.md)