---
title: 如何处理异常 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, handlers
- scopes, errors
- errors, scopes
- handlers [adapters], errors
ms.assetid: 30b88d8a-8737-4700-b856-1b49fdf6b6d0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc50f8371e5417662a8b81ef119e2a33f18e8925
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344131"
---
# <a name="how-exceptions-are-handled"></a>如何处理异常
当作用域中出现异常时，将停止执行作用域中的每个逻辑线程。 运行时引擎尝试为相应的异常找到异常处理程序。  
  
 如果找到匹配的特定类型或其基类型之一的异常处理程序，控制权将传递给该处理程序和其代码运行。  
  
> [!NOTE]
>  异常类型必须派生自**System.Exception**。  
  
 异常处理程序是按顺序;也就是说，它们将进行检查以便确定它们是否可以处理特定异常。 若要正常工作，以便处理更具体的类型出现在最前面，随后处理更普通的类型必须放置异常处理程序。 这是，以便您可以确保特定类型的异常由相应的处理程序，而不是设计为处理基类型。  
  
 如果异常处理程序正常完成，控制权将传递给周围的作用域。 如果已在周围的作用域中不引发任何异常，该业务流程将继续运行。 如果异常处理程序结束 throw 语句，将原始异常是再次引发周围的作用域生效，除非指定你想要引发的不同异常。  
  
 如果不可以位于任何异常处理程序，将运行默认异常处理程序。 作用域的默认异常处理程序将调用的任何嵌套事务、 补偿，然后再次引发该异常。 如果您编写自己的异常处理程序，您可以选择不传播该异常。  
  
## <a name="see-also"></a>请参阅  
 [异常](../core/exceptions.md)