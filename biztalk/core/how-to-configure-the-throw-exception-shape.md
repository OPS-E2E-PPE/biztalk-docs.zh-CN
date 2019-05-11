---
title: 如何配置引发异常形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Throw Exception shape [Orchestration Designer]
- orchestrations, errors
- Orchestration Designer, errors
ms.assetid: d3190f1b-db5e-4988-bff6-f7a276760ece
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee24b5a6fab36e7a865f26a04e8c040141835735
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385939"
---
# <a name="how-to-configure-the-throw-exception-shape"></a>如何配置引发异常形状
您可以显式引发异常在业务流程中使用**引发异常**形状。 时引发异常，运行时引擎将搜索的最接近的异常处理程序可以处理所引发异常的类型。  
  
 首先，当前业务流程中搜索所封闭范围，并以找到相应的处理程序已引发的异常的类型被视为作用域的相关联的异常处理程序。  
  
 如果不找到任何适当的异常处理程序，则对当前业务流程的调用点的作用域搜索调用当前业务流程的业务流程。 此搜索继续，直到找到异常处理程序可以处理当前异常。  
  
 是的与相同的类的异常类或基类所引发的异常的运行时类型的异常的完全匹配项。  
  
 找到匹配的异常处理程序后，控制被转到异常处理程序的第一个语句。  
  
 如果搜索匹配的异常处理程序失败，业务流程将停止。 事务可以帮助您这种情况影响降至最低。  
  
## <a name="procedure"></a>过程  
  
#### <a name="to-configure-a-throw-exception-shape"></a>若要配置引发异常形状  
  
-   在属性窗口中，选择要从引发的可用对象类型**异常对象**下拉列表。  
  
    > [!NOTE]
    >  选择中的常规异常**引发异常**形状仅当**引发异常**形状在异常处理程序内，并且你想要重新引发当前异常处理程序中捕获到异常。 你将在编译期间收到错误，如果使用的一般异常**引发异常**在任何其他上下文中的形状。  
  
## <a name="see-also"></a>请参阅  
 [异常](../core/exceptions.md)