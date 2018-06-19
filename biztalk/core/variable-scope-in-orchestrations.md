---
title: 在业务流程中的变量范围 |Microsoft 文档
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
ms.openlocfilehash: 82803cd7f2b0beb8349e978fdd7b9e453dca31ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288117"
---
# <a name="variable-scope-in-orchestrations"></a>在业务流程中的变量范围
有关业务流程内不同位置中变量和业务流程参数的可见性和状态（包括异常处理程序和补偿模块），您需要充分了解其中的一些要点。  
  
-   业务流程参数在整个业务流程主体及其补偿模块中是可见的。  
  
-   作用域级变量在作用域的主体及其所有异常处理程序和补偿模块中都是可见的。 在异常处理程序中，由于主体中引发给定处理程序的异常是发生在任何初始化之前还是之后是不确定的，所以总是将变量视为未初始化。 因此，如果在作用域中声明一个变量并在主体中对其进行初始化，则将无法在异常处理程序中读取该变量，或者将出现编译器错误。 对于长期事务存在解决上述问题的方法。 以下示例显示了如何使用 succeeded() 运算符确保正确的运行时行为：  
  
    > [!NOTE]
    >  以下代码为用于描述逻辑进程的伪代码；此代码不能用于业务流程表达式形状。  
  
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
  
-   在补偿模块中，所有变量均使用提交作用域主体时具有的值。 请注意，作用域的补偿模块永远不会在其主体完成后立即运行；将始终存在干预代码。 如果任何干预代码更新某些作用域外的变量，则将运行补偿模块，在补偿模块内将看不到这些更新。 而这些变量将会暂时恢复为在提交拥有该补偿的作用域时具有的值。  
  
-   当事务嵌套于循环中时，将按循环执行的次数补偿事务。 在每一迭代的补偿模块中，作用域外变量将使用在提交事务迭代时具有的值。  
  
-   在补偿模块完成后，内部作用域的补偿模块内对作用域外变量或业务流程参数所做的所有更新将不可见。 换句话说，补偿模块将无法用于直接修改作用域外变量的值。  
  
## <a name="see-also"></a>另请参阅  
 [XLANG-s 数据类型](../core/xlang-s-data-types.md)