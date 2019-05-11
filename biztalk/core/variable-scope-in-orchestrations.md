---
title: 业务流程中的变量范围 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
ms.assetid: 5856cdca-0ebd-4e16-8739-7bd50753b9f9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebe6e3e4116a2b5c250e642d5bc78d828b07656c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292581"
---
# <a name="variable-scope-in-orchestrations"></a>业务流程中的变量范围
有几个要点，若要了解有关可见性和状态的变量和您的业务流程，包括异常处理程序和补偿模块内不同位置中的业务流程参数。  
  
-   业务流程参数中都可见的业务流程也主体及其补偿模块。  
  
-   作用域级别的变量是可见的作用域的正文中以及所有异常处理程序和补偿模块中。 在异常处理程序，因为它是不确定是否为给定的处理程序引发的异常发生之前或之后在正文中的任何初始化被视为未初始化变量。 出于此原因，如果作用域中声明一个变量，并在正文中对其进行初始化，无法从其读取在异常处理程序，或你将收到编译器错误消息。 在长时间运行事务的情况下存在为此，一种解决方法。 下面的示例演示了如何使用 succeeded （） 运算符确保正确的运行时行为：  
  
    > [!NOTE]
    >  下面的代码是描述逻辑进程; 的伪代码此代码不能使用在业务流程表达式形状内。  
  
    ```  
    scope longrunning transaction L  
    {  
       System.Int32 i;  
       System.Int32 v;  
       body  
       {  
          i = 3;  
          scope longrunning transaction T  
          {  
             body  
             {  
                i = 5;  
             }  
          }  
       }  
       exceptions  
       {  
          catch  
          {  
             if(succeeded(T))  
             {  
                v = i;  // OK to read from it here — no compiler errors!  
             }  
          }  
       }  
    }  
    ```  
  
-   在补偿模块中，所有变量都均使用提交作用域主体时具有的值。 请注意，作用域的补偿模块永远不会运行其主体完成; 后立即将始终存在干预代码。 如果任何干预代码更新某些作用域外变量，然后将运行补偿模块，这些更新将不会看到在补偿模块内。 改为变量将会暂时恢复到它们在提交拥有该补偿的作用域时具有的值。  
  
-   当事务嵌套在一个循环中时，将根据循环执行多次补偿事务。 在每次迭代的补偿模块，作用域外变量假定它们在提交事务迭代时具有的值。  
  
-   对作用域外变量所做的任何更新或内部作用域的补偿模块内的业务流程参数的补偿模块完成后将不可见。 换句话说，补偿模块不能用于直接修改作用域外变量的值。  
  
## <a name="see-also"></a>请参阅  
 [XLANG-s 数据类型](../core/xlang-s-data-types.md)