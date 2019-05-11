---
title: 逻辑运算符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8aaceb64-a5a0-462a-a0eb-8352bed999e5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 940f9a1c3604108de58a44aa6998dcdd82e86abb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380572"
---
# <a name="logical-operators"></a>逻辑运算符
使用逻辑 AND、 逻辑或业务规则框架支持和逻辑 NOT 运算符在创建业务规则。 下表描述的逻辑运算符。  
  
|逻辑运算符|Description|  
|----------------------|-----------------|  
|**AND**|返回 **，则返回 true**如果两个操作数的计算结果为**true**; 否则返回**false**。|  
|**OR**|返回 **，则返回 true**如果其中一个操作数计算结果为**true**，否则将返回**false**。|  
|**NOT**|返回 **，则返回 true**如果操作数计算结果为**false**，否则将返回**false**。|  
  
 不同类型的操作数时，规则引擎将转换一个要与其他参数，则转换的类型为通用类型的两个参数的类型匹配之前对表达式求值的参数的类型。  
  
## <a name="to-use-a-logical-operator-in-a-business-rule"></a>若要在业务规则中使用逻辑运算符  
 使用以下过程在业务规则中使用逻辑运算符。  
  
1.  在中**IF**窗格中的业务规则编辑器中，右键单击**条件**节点，并选择你想要添加到逻辑表达式的逻辑运算符。  
  
2.  右键单击该逻辑运算符，并添加谓词或你想要添加的嵌套逻辑运算符。  
  
## <a name="see-also"></a>请参阅  
 [算术运算符](../core/arithmetic-operators.md)