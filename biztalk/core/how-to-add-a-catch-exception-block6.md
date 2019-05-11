---
title: 如何添加捕获异常 Block6 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exception handling, Catch Exception block
- Catch Exception blocks
- exceptions, Catch Exception block
ms.assetid: 404312dd-773b-44fe-8b65-7de3d0af2f79
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a84b37953e05c83beff6853cd7143c7db2a36036
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387375"
---
# <a name="how-to-add-a-catch-exception-block"></a>如何添加捕获异常块
**捕获异常**块代表异常处理程序。 **捕获异常**块附加到的末尾**作用域**形状在业务流程设计器中的。 在 BizTalk Server 中，你可以附加任意数量**捕获异常**块。  
  
 您可以将设置异常处理程序来处理不同类型的异常。 在每个异常处理程序中，指定一个异常类型，该错误消息或是从类派生的对象必须是类型`System.Exception`。 如果不指定异常类型，异常块视为一般异常处理程序，并且可以捕获不是从派生的异常`System.Exception`。  
  
 如果引发异常，异常处理程序中的指定的类型相匹配，则调用该异常处理程序。 如果引发了某些其他异常，则进行处理的默认异常处理程序。  
  
> [!NOTE]
>  若要添加**捕获异常**阻止**作用域**形状，**事务类型**属性的**范围**形状必须设置为无或长正在运行。  
  
## <a name="adding-and-populating-a-catch-exception-block"></a>添加和填充捕获异常块  
  
#### <a name="to-add-and-populate-a-catch-exception-block"></a>若要添加和填充捕获异常块  
  
1.  右键单击**作用域**你想要添加的形状**捕获异常**块，然后单击**新建异常处理程序**。  
  
     一个**捕获异常**块添加到紧跟相关业务流程**作用域**形状。  
  
2.  在中**属性**窗口中，指定的属性。 最重要属性是**异常对象类型**因为这是将捕获的消息类型。  
  
    |属性|Description|  
    |--------------|-----------------|  
    |异常对象名称|为指定的异常处理程序捕获的异常对象名称。|  
    |异常对象类型|确定对象类型 （从 System.Exception 派生的），将会捕获此异常处理程序。|  
  
3.  在中**属性**窗口中，单击**异常对象类型**列表。 此列表包含常规适配器引发的异常。  
  
     名称显示为错误设置中的端口到后端系统，例如，ps。SQLExecute.Fault。  
  
4.  为添加名称**异常对象名称**，例如，测试。  
  
     内部**捕获异常**块中，添加形状以创建处理异常进程。  
  
    1.  下单击鼠标右键**捕获异常**，依次指向**插入形状**，然后选择**构造消息**。  
  
         ![](../core/media/siebeladapter-20-exceptionhandling-constructmessage.gif "SiebelAdapter_20_ExceptionHandling_ConstructMessage")  
  
    2.  双击**MessageAssignment**以打开文本编辑器并输入消息赋值。  
  
         输入中设置的名称**异常对象名称**从**捕获异常**，并为该错误创建的新消息。  
  
         例如，键入 `Message_3 = Test`。  
  
         ![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")  
  
## <a name="see-also"></a>请参阅  
 [如何添加作用域形状](../core/how-to-add-a-scope-shape1.md)   
 [完成异常消息](../core/completing-the-exception-message3.md)   
 [使用 BizTalk Server 的异常处理](../core/using-biztalk-server-exception-handling2.md)