---
title: "逻辑 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e37cdfc3-66de-4333-84eb-a8765afa8407
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7907d1045fde39d5ece963bd78e00d027e8a9da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="logical-functoids"></a>“判断”Functoid

## <a name="overview"></a>概述
**逻辑**functoid 用于执行以下类型的操作：  
  
-   在运行时执行特定的逻辑测试。 **逻辑或**，**不逻辑**和**逻辑和**functoid 可以用于确定是否创建一条记录中的目标实例消息，如下所示：  
  
     如果 ShipTo**或**OrderedBy 是否存在后，创建帐单寄往地址记录。  
  
     此外可以结合使用这些 functoid**循环**functoid 配置记录循环的次数。  
  
-   控制在运行时是否在目标实例消息中创建特定记录。 如 Functoid **IsNil**，**逻辑数值**，**小于**，和**大于**可以用于控制是否创建一条记录。  
  
     如果这些逻辑 functoid 之一的结果是**True**，生成的目标实例消息中的相应记录。 如果结果为**False**，目标实例消息中的相应记录不会生成。  
  
 Functoid **IsNil**，**逻辑日期**，**逻辑是否存在**，**不逻辑**，**逻辑数值**，和**逻辑字符串**接受只有一个参数。 Functoid**相等**，**大于**，**大于或等于**，**小于**，**小于或等于**，和**不等于**接受两个输入参数。 而、**逻辑和**和**逻辑或**functoid 接受介于 2 和 100 之间的输入的参数。  
  
 输出**逻辑**functoid 还可以接受作为其他 functoid 映射中的输入。 如果这两个**逻辑**functoid 和循环 functoid 是链接在一起，，然后链接到目标架构中的记录，则使用循环 functoid 仅当**逻辑**functoid 输出，则**True**。  
  
 你还可以使用**逻辑**与 functoid**值映射**或**值映射 （平展）** functoid 来控制是否在目标实例消息中的记录创建。  
  
> [!IMPORTANT]
>  如果你将两个记录或源架构中的域链接到两个不同**逻辑**functoid，然后将每个链接**逻辑**functoid 对同一记录在目标架构中，只有第一个**逻辑**functoid 使用中生成可扩展样式表语言转换 (XSLT)。 第二个链接，从第二个**逻辑**functoid，将被忽略。  
  
> [!NOTE]
>  “判断”functoid 在比较两个字符串时区分大小写。 例如，“Abc”和“abc”并不等效。 此规则的例外是当**逻辑**functoid 比较表示布尔值的字符串**True**和**False**。 例如，“True”和“true”是等效的。  

## <a name="available-functoids"></a>可用的 functoid  
 **逻辑**functoid 均： 

* 等于
* 大于
* 大于或等于
* IsNil
* 小于
* 小于或等于
* 逻辑与
* 日期判断
* 存在判断
* 逻辑非
* 数判断
* 逻辑或
* 字符串判断
* 不等于

这些函数的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="see-also"></a>另请参阅  
-  [如何在向地图添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)   
-  **逻辑 Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]