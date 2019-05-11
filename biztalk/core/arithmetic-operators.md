---
title: 算术运算符 |Microsoft Docs
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
ms.openlocfilehash: d9e56d48f6c49107923541d5095fe0b1019f6afa
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528817"
---
# <a name="arithmetic-operators"></a>算术运算符
业务规则框架支持使用加法、 减法、 乘法、 除法和余数 （取模） 中创建业务规则的运算符。 下表介绍的算术运算符。  
  
|算术运算符|Description|  
|-------------------------|-----------------|  
|**“添加”**|表示加法运算符 (arg1 加上 arg2)。|  
|**Subtract**|表示减法运算符 (arg2 减去 arg1)。|  
|**Multiply**|表示乘法运算符 (arg1 乘以 arg2)。|  
|**Divide**|表示除法运算符 (arg1 除以 arg2)。|  
|**其余部分**|表示余数运算符 (arg1 对 arg2 取模)。|  
  
 不同类型的操作数时，自动进行数值升级使用较小的操作数类型转换为更大的操作数类型。 例如，如果**外**操作符的第一个操作数为**int**类型和第二个操作数**长**类型，第一个操作数的类型转换为**长**执行之前**添加**操作。 如果这两个操作数可升级为通用类型，规则引擎还支持双升级。 例如，如果**外**操作符的第一个操作数为**int**类型和第二个操作数**uint**类型，这两个操作数的类型转换为**长**执行之前**添加**操作。  
  
## <a name="to-use-a-logical-operator-in-a-business-rule"></a>若要在业务规则中使用逻辑运算符  
 使用以下过程在业务规则中使用逻辑运算符。  
  
1.  在事实浏览器窗口中，单击**词汇**选项卡。  
  
2.  展开**词汇**，展开**函数**，展开**版本 1.0-已发布**，然后将拖**添加/减/乘/除/余数**到条件窗格/操作窗格。  
  
3.  指定的左侧和右侧运算符的值。  
  
## <a name="see-also"></a>请参阅  
 [逻辑运算符](../core/logical-operators.md)