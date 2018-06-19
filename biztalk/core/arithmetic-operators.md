---
title: 算术运算符 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d73e153c-aac1-4cea-92d8-af4a1bea6e6a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b3d66a990437929176835228efa1a74a5fa8683
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230517"
---
# <a name="arithmetic-operators"></a>算术运算符
业务规则框架支持在创建业务规则时使用加、减、乘、除和余数（模）运算符。 下表对这些算术运算符进行了说明。  
  
|算术运算符|Description|  
|-------------------------|-----------------|  
|**添加**|表示加法运算符（arg1 加上 arg2）。|  
|**减去**|表示减法运算符（arg2 减去 arg1）。|  
|**乘**|表示乘法运算符（arg1 乘以 arg2）。|  
|**Divide**|表示除法运算符（arg1 除以 arg2）。|  
|**余数**|表示余数运算符（arg1 对 arg2 求模）。|  
  
 如果操作数类型不同，则会自动进行数值升级，较小的操作数类型将会被转换为较大的操作数类型。 例如，如果**添加**运算符用于的第一个操作数**int**类型和第二个操作数的**长**类型，第一个操作数的类型转换为**长**之前执行**添加**操作。 如果两个操作数可升级为同一类型，则规则引擎还支持双升级。 例如，如果**添加**运算符用于的第一个操作数**int**类型和第二个操作数的**uint**类型，这两个操作数的类型转换为**长**之前执行**添加**操作。  
  
## <a name="to-use-a-logical-operator-in-a-business-rule"></a>在业务规则中使用逻辑运算符  
 利用以下过程可在业务规则中使用逻辑运算符。  
  
1.  在事实浏览器窗口中，单击**词汇**选项卡。  
  
2.  展开**词汇**，展开**函数**，展开**版本 1.0-发布**，然后拖动**添加/减/乘/除/余数**到条件窗格/操作窗格。  
  
3.  为左操作数和右操作数指定值。  
  
## <a name="see-also"></a>另请参阅  
 [逻辑运算符](../core/logical-operators.md)