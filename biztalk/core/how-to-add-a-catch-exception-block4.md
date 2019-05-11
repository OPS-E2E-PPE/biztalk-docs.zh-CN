---
title: 如何添加捕获异常 Block4 |Microsoft Docs
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
ms.openlocfilehash: 9cf27fd031f5887eed499eb1b10418fa911a127c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387370"
---
# <a name="how-to-add-a-catch-exception-block"></a>如何添加捕获异常块
**捕获异常**块代表异常处理程序。 **捕获异常**块附加到的末尾**作用域**形状在业务流程设计器中的。 可以附加任意数量**捕获异常**块。  
  
 您可以将设置异常处理程序来处理不同类型的异常。 在每个异常处理程序中，指定一个异常类型，它必须是异常或是从类 System 派生的对象。 如果引发异常，异常处理程序中的指定的类型相匹配，则调用该异常处理程序。  
  
> [!NOTE]
>  若要添加**捕获异常**阻止**作用域**形状的事务类型属性**作用域**形状必须设置为**无**或**长时间运行的**。  
  
|添加和填充捕获异常块|  
|---------------------------------------------------|  
|1.右键单击**作用域**你想要添加的形状**捕获异常**阻止对，然后单击**新建异常处理程序**。<br />     一个**捕获异常**块添加到紧跟相关业务流程**作用域**形状。<br />2.在中**属性**窗口中，指定的属性。 最重要的是**异常对象类型**; 这是将捕获的消息类型。<br />     **异常对象名称**<br />     -为指定的异常处理程序捕获的异常对象名称。<br />     **异常对象类型**<br />     -确定 （从 System.Exception 派生） 的对象类型，将会捕获此异常处理程序。<br />3.在中**属性**窗口中，打开**异常对象类型**列表。 此列表包含**一般异常**。<br />4.内部**捕获异常**块中，添加形状以创建处理异常进程。<br />5.下单击鼠标右键**捕获异常**，依次指向**插入形状**，然后选择**构造消息**。<br />6.双击**MessageAssignment**以激活文本编辑器中，并输入消息赋值。<br />     例如，键入 Message_3 = Test。<br />     ![](../core/media/siebeladapter-21-exceptionhandling-message3test.gif "SiebelAdapter_21_ExceptionHandling_Message3Test")|  
  
## <a name="see-also"></a>请参阅  
 [完成异常消息](../core/completing-the-exception-message2.md)   
 [如何添加作用域形状](../core/how-to-add-a-scope-shape3.md)   
 [使用 BizTalk Server 的异常处理](../core/using-biztalk-server-exception-handling1.md)