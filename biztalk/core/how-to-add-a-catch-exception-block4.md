---
title: 如何添加 Catch 异常 Block4 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Catch Exception blocks, adding
- exception handling, Catch Exception blocks
ms.assetid: 632fa089-a1af-4126-b32b-68d4d8942387
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b409f25fc32c609bb4c1a80c0582cdb1c363e965
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246821"
---
# <a name="how-to-add-a-catch-exception-block"></a>如何添加 Catch 异常块
**捕获异常**块代表一个异常处理程序。 **捕获异常**块附加到的末尾**作用域**中业务流程设计器形状。 你可以将作为许多附加**捕获异常**阻止根据你的需要。  
  
 你可以设置异常处理程序来处理不同种类的异常。 对每个异常处理程序，您应指定一个异常类型，该类型必须是异常或是从类 System 派生的对象。 如果将引发异常，异常处理程序中的指定的类型相匹配，则调用该异常处理程序。  
  
> [!NOTE]
>  若要添加**捕获异常**阻止**作用域**形状的事务类型属性**作用域**形状必须设置为**无**或**长时间运行的**。  
  
|添加和填充捕获异常块|  
|---------------------------------------------------|  
|1.右键单击**作用域**你想要添加的形状**捕获异常**块，并单击**新异常处理程序**。<br />     A**捕获异常**块添加到紧跟在关联的业务流程**作用域**形状。<br />2.在**属性**窗口中，指定的属性。 最重要的是**异常对象类型**; 这是它将捕获的消息的类型。<br />     **异常对象名称**<br />     -将名称分配给异常处理程序捕获的异常对象。<br />     **异常对象类型**<br />     -确定 （从 System.Exception 派生） 的对象类型，将捕获此异常处理程序。<br />3.在**属性**窗口中，打开**异常对象类型**列表。 此列表包含**一般异常**。<br />4.内部**捕获异常**块中，添加形状来创建用于处理异常的进程。<br />5.右键单击以下**捕获异常**，指向**插入形状**，然后选择**构造消息**。<br />6.在双击**MessageAssignment**以激活文本编辑器中，并输入消息赋值。<br />     例如，键入 Message_3 = Test。<br />     ![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")|  
  
## <a name="see-also"></a>另请参阅  
 [完成的异常消息](../core/completing-the-exception-message2.md)   
 [如何添加作用域形状](../core/how-to-add-a-scope-shape3.md)   
 [使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling1.md)