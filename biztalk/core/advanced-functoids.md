---
title: 高级 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82bf2547-5e44-45f8-b577-97e5760a0339
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0e906b7e1c4d7ca71f952441cd22542e9637399
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360507"
---
# <a name="advanced-functoids"></a>高级的 Functoid

## <a name="overview"></a>概述
高级的 functoid 根据用途分为五个组：  
  
-   **管理循环记录。** **索引**，**迭代**，**循环**， **Nil 值**，**记录计数**，**表提取程序**，并**表循环**functoid 使用在各种组合中输入的实例消息包含具有不可预测的部分数由循环重复元素，源架构中的记录。  
  
-   **条件映射。** **值映射**并**值映射 （平展）** functoid 用于提供从输入的实例消息到输出实例消息的条件映射。 当其第一个输入的参数为 true 时，第二个输入的参数被放置到指定的元素或属性在输出实例消息中;否则，该元素或属性不被创建的输出实例消息中。  
  
-   **任意脚本。** **脚本**functoid 用于运行任意脚本或编译代码时的输入的实例消息映射到输出实例消息。 可以创建此类脚本或已编译的代码，以便它接受来自已配置的常量值，从另一个 functoid 或它们的某种组合的输出的源实例消息中的输入的参数。  
  
-   **简单映射。** **批量复制**functoid 可用于复制的整个元素，从输入的实例消息到输出实例消息到任意深度，包括及其子元素。  
  
-   **故障排除**。 **Assert** functoid 可用于测试有关元素值的假设。  
  
## <a name="available-functoids"></a>可用的 functoid
  
 **高级**functoid 包括： 

* 添加 Functoid
* 索引 Functoid 
* 迭代 Functoid 
* 循环 Functoid 
* 批量复制 Functoid 
* 零值 Functoid
* “记录计数”Functoid 
* 脚本 Functoid 
* 表循环和表提取程序 Functoid
* 值映射 Functoid
* “值映射(平展)”Functoid

这些 functoid 的详细信息位于**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="next-steps"></a>后续步骤
  
-   [“添加”Functoid](../core/assert-functoid.md)  
  
-   [“索引”Functoid](../core/index-functoid.md)  
  
-   [“迭代”Functoid](../core/iteration-functoid.md)  
  
-   [循环 Functoid](../core/looping-functoid.md)  
  
-   [“批量复制”Functoid](../core/mass-copy-functoid.md)  
  
-   [“零值”Functoid](../core/nil-value-functoid.md)  
  
-   [“记录计数”Functoid](../core/record-count-functoid.md)  
  
-   [“表循环”和“表提取程序”Functoid](../core/table-looping-and-table-extractor-functoids.md)  
  
-   [“值映射”Functoid](../core/value-mapping-functoid.md)  
  
-   [“值映射（平展）”Functoid](../core/value-mapping-flattening-functoid.md)  
  
-   [“脚本编写”Functoid](../core/scripting-functoid.md)