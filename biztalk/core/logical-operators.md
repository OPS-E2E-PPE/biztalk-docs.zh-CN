---
title: "逻辑运算符 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8aaceb64-a5a0-462a-a0eb-8352bed999e5
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e3b3c187e353babafd86590fdeacdc19fc115b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="logical-operators"></a>逻辑运算符
业务规则框架支持在创建业务规则时使用“逻辑与”、“逻辑或”和“逻辑非”运算符。 下表介绍这些逻辑运算符。  
  
|逻辑运算符|Description|  
|----------------------|-----------------|  
|**AND**|返回**true**如果两个操作数的计算结果为**true**; 否则返回**false**。|  
|**OR**|返回**true**如果其中一个操作数的计算结果为**true**，否则返回**false**。|  
|**NOT**|返回**true**如果操作数的计算结果为**false**，否则返回**false**。|  
  
 当操作数为不同类型时，在计算表达式之前，规则引擎会将一个参数的类型转换为匹配其他参数的类型，或将两个参数类型都转换为常见类型。  
  
## <a name="to-use-a-logical-operator-in-a-business-rule"></a>在业务规则中使用逻辑运算符  
 利用以下过程可在业务规则中使用逻辑运算符。  
  
1.  在**如果**的业务规则编辑器窗格中右键单击**条件**节点，，然后选择你想要将添加到逻辑表达式的逻辑运算符。  
  
2.  右键单击该逻辑运算符，然后添加所需的谓词或嵌套逻辑运算符。  
  
## <a name="see-also"></a>另请参阅  
 [算术运算符](../core/arithmetic-operators.md)