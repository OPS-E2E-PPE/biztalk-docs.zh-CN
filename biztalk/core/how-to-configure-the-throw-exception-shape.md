---
title: "如何配置抛出异常形状 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Throw Exception shape [Orchestration Designer]
- orchestrations, errors
- Orchestration Designer, errors
ms.assetid: d3190f1b-db5e-4988-bff6-f7a276760ece
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07d156572484ba4fbe71533252ce4fe956136699
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-throw-exception-shape"></a>如何配置引发异常形状
您可以显式抛异常业务流程中使用**引发的异常**形状。 在引发异常时，运行时引擎将搜索最近的能处理所引发的异常类型的异常处理程序。  
  
 首先，在当前业务流程中搜索封闭作用域，然后按顺序考虑该作用域的相关异常处理程序，以查找与所引发的异常类型相应的处理程序。  
  
 如果找不到适当的异常处理程序，将在调用当前业务流程的业务流程中搜索调用当前业务流程的调用点所在的作用域。 这种搜索会持续到找到能处理当前异常的异常处理程序为止。  
  
 完全匹配异常的异常类是所引发异常的运行时类型的类或者基类。  
  
 在找到匹配的异常处理程序后，控制将被转到异常处理程序的第一个语句。  
  
 如果搜索匹配的异常处理程序失败，则业务流程将停止。 事务有助于将发生这种情况的影响降至最低。  
  
## <a name="procedure"></a>过程  
  
#### <a name="to-configure-a-throw-exception-shape"></a>配置引发异常形状  
  
-   在属性窗口中，选择要从引发的可用对象类型**异常对象**下拉列表。  
  
    > [!NOTE]
    >  选择中出现一般异常**引发的异常**形状才**引发的异常**形状在异常处理程序内，并且你想要重新引发当前异常处理程序中捕获的异常。 你将在编译期间收到错误，如果使用常规异常**引发的异常**在任何其他上下文中的形状。  
  
## <a name="see-also"></a>另请参阅  
 [异常](../core/exceptions.md)