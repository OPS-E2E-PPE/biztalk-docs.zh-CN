---
title: "如何添加 Catch 异常 Block6 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exception handling, Catch Exception block
- Catch Exception blocks
- exceptions, Catch Exception block
ms.assetid: 404312dd-773b-44fe-8b65-7de3d0af2f79
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4be60ddbe45ef4b4f293d7959dc774254e7cd3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-catch-exception-block"></a>如何添加 Catch 异常块
**捕获异常**块代表一个异常处理程序。 **捕获异常**块附加到的末尾**作用域**中业务流程设计器形状。 在 BizTalk Server 中，你可以将作为附加许多**捕获异常**阻止根据你的需要。  
  
 你可以设置异常处理程序来处理不同种类的异常。 对每个异常处理程序，您应指定一个异常类型，该类型必须是错误消息或是从类 `System.Exception` 派生的对象。 如果不指定异常类型，异常块将会被视为一般异常处理程序，可以捕获不是从 `System.Exception` 派生的异常。  
  
 如果将引发异常，异常处理程序中的指定的类型相匹配，则调用该异常处理程序。 如果某些其他异常被抛弃，它是由默认异常处理程序中进行处理。  
  
> [!NOTE]
>  若要添加**捕获异常**阻止**作用域**形状，**事务类型**属性**作用域**形状必须设置为无或长运行。  
  
## <a name="adding-and-populating-a-catch-exception-block"></a>添加和填充 Catch 异常块  
  
#### <a name="to-add-and-populate-a-catch-exception-block"></a>若要添加并填充 catch 异常块  
  
1.  右键单击**作用域**你想要添加的形状**捕获异常**阻止，并依次**新异常处理程序**。  
  
     A**捕获异常**块添加到紧跟在关联的业务流程**作用域**形状。  
  
2.  在**属性**窗口中，指定的属性。 最重要的属性是**异常对象类型**因为这是它将捕获的消息的类型。  
  
    |属性|Description|  
    |--------------|-----------------|  
    |异常对象名称|为异常处理程序捕获的异常对象中指定一个名称。|  
    |异常对象类型|确定此异常处理程序将要捕获的从 System.Exception 派生的对象类型。|  
  
3.  在**属性**窗口中，单击**异常对象类型**列表。 此列表包含适配器引发一般异常。  
  
     该名称显示为在到后端系统，例如，ps。 端口中设置的错误SQLExecute.Fault。  
  
4.  为添加名称**异常对象名称**，例如，测试。  
  
     内部**捕获异常**块中，添加形状来创建用于处理异常的进程。  
  
    1.  右键单击以下**捕获异常**，指向**插入形状**，然后选择**构造消息**。  
  
         ![](../core/media/siebeladapter-20-exceptionhandling-constructmessage.gif "SiebelAdapter_20_ExceptionHandling_ConstructMessage")  
  
    2.  在双击**MessageAssignment**以打开文本编辑器并输入消息赋值。  
  
         输入你在中设置的名称**异常对象名称**从**捕获异常**，和新创建的错误消息。  
  
         例如，键入 `Message_3 = Test`。  
  
         ![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")  
  
## <a name="see-also"></a>另请参阅  
 [如何添加作用域形状](../core/how-to-add-a-scope-shape1.md)   
 [完成的异常消息](../core/completing-the-exception-message3.md)   
 [使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling2.md)