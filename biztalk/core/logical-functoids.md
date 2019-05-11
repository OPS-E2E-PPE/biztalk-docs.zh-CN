---
title: 判断 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e37cdfc3-66de-4333-84eb-a8765afa8407
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b4fd7b2a38a5a5b4a8bbeb64ffd248502dcdb61
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65328310"
---
# <a name="logical-functoids"></a>判断 Functoid

## <a name="overview"></a>概述
**逻辑**functoid 用于执行以下类型的操作：  

- 执行特定的逻辑测试，在运行时。 **逻辑或**，**逻辑非**并**逻辑和**functoid 可用于确定是否在目标实例消息中，如下所示创建一条记录：  

   如果 ShipTo**或**orderedby 存在，创建 BillTo 地址记录。  

   此外可以结合使用这些 functoid**循环**functoid 配置记录的循环的次数。  

- 控制在运行时是否创建目标实例消息中包含的特定记录。 如 Functoid **IsNil**，**数判断**，**小于**，以及**大于**可以用于控制是否创建一条记录。  

   如果一个这些判断 functoid 的结果是 **，则返回 True**，生成的目标实例消息中相应记录中。 如果结果为**False**，不生成目标实例消息中的相应记录中。  

  这些 functoid **IsNil**，**逻辑日期**，**存在判断**，**逻辑非**，**逻辑数值**，并**字符串判断**只接受一个参数。 这些 functoid**相等**，**大于**，**大于或等于**，**小于**，**小于或等于**，并**不等于**接受两个输入参数。 而，则**逻辑和**并**逻辑或**functoid 接受 2 到 100 之间的输入的参数。  

  输出**逻辑**functoid 还可以接受作为映射中其他 functoid 的输入。 如果这两个**逻辑**functoid 和循环 functoid 链接在一起，并链接到目标架构中记录，然后，使用循环 functoid 时，才**逻辑**functoid 输出是**True**。  

  此外可以使用**逻辑**functoid 一起**值映射**或**值映射 （平展）** functoid，以控制是否在目标实例消息中的记录创建。  

> [!IMPORTANT]
>  如果两个记录或源架构中的字段链接到两个不同**逻辑**functoid，然后将每个链接**逻辑**functoid 到目标架构中的相同记录仅在首**逻辑**functoid 用于在生成可扩展样式表语言转换 (XSLT)。 第二个链接，从第二个**逻辑**functoid，将被忽略。  

> [!NOTE]
>  比较两个字符串时，判断 functoid 是区分大小写。 例如，"Abc"和"abc"不相等。 此规则的例外是何时**逻辑**functoid 比较表示布尔值的字符串**True**并**False**。 例如，"True"和"true"相等。  

## <a name="available-functoids"></a>可用的 functoid  
 **逻辑**functoid 包括： 

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

这些函数的更多详细信息是[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

## <a name="see-also"></a>请参阅  
- [如何向映射添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)   
- **判断 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
