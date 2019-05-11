---
title: 如何添加捕获异常 Block5 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions, adding Catch Exception block
- Catch Exception blocks, adding
ms.assetid: 4875060c-976c-40e7-830a-ffd1a47ba68a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60e2674823ff92b1ffe59a304b8cbe766c8e7e0d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343940"
---
# <a name="how-to-add-a-catch-exception-block"></a>如何添加捕获异常块
若要添加**捕获异常**阻止**作用域**形状，**事务类型**属性的**范围**形状必须设置为**None**或**长时间运行的**。  
  
### <a name="to-add-a-catch-exception-block"></a>若要添加捕获异常块  
  
1.  右键单击**作用域**形状，然后依次**新建异常处理程序**。  
  
     一个**捕获异常**块添加到紧跟相关业务流程**作用域**形状。  
  
2.  在中**属性**窗口中，指定的属性。  
  
     最重要属性是**异常对象类型**; 这是将捕获的消息类型。  
  
    |属性|Description|  
    |--------------|-----------------|  
    |**异常对象名称**|为指定的异常处理程序捕获的异常对象名称。|  
    |**异常对象类型**|确定对象类型 （从 System.Exception 派生的），将会捕获此异常处理程序。|  
  
3.  在中**属性**窗口，请在**异常对象类型**列表中，选择**一般异常**。  
  
4.  内部**捕获异常**块中，添加形状以创建处理异常进程。  
  
    1.  下单击鼠标右键**CatchException** ，然后指向**插入形状**，然后选择**构造消息**。  
  
    2.  双击**MessageAssignment**以打开文本编辑器并输入消息赋值。  
  
         例如，键入 `Message_3 = Test`。  
  
## <a name="see-also"></a>请参阅  
 [完成异常消息](../core/completing-the-exception-message1.md)   
 [如何添加作用域形状](../core/how-to-add-a-scope-shape5.md)   
 [使用 BizTalk Server 的异常处理](../core/using-biztalk-server-exception-handling5.md)