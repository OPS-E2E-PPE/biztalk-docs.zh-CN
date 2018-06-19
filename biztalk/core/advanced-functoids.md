---
title: 高级 Functoid |Microsoft 文档
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
ms.openlocfilehash: 5002b639df79ece1019c2d013c128f615517ae5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230389"
---
# <a name="advanced-functoids"></a>高级的 Functoid

## <a name="overview"></a>概述
高级 functoid 根据用途可分为五组：  
  
-   **管理循环记录。** **索引**，**迭代**，**循环**， **Nil 值**，**记录计数**，**表提取程序**，和**表循环**时输入的实例消息包含与不可预测的各节 functoid 各种组合中使用的重复元素所表示的循环数源架构中的记录。  
  
-   **条件映射。** **值映射**和**值映射 （平展）** functoid 用于提供从输入的实例消息到输出实例消息的条件映射。 如果它们的第一个输入参数为 True，则第二个输入参数将放入输出实例消息的指定元素或属性中；否则，将不会在输出实例消息中创建该元素或属性。  
  
-   **任意脚本。** **脚本**functoid 用于运行任意脚本或已编译代码时输入的实例消息正在映射到输出实例消息。 此类脚本或编译代码可创建为从源实例消息、已配置的常数值、其他 functoid 的输出或它们的组合接受输入参数。  
  
-   **简单的映射。** **大容量复制**functoid 可以用于复制的整个元素，包括从一个到输出实例消息的输入的实例消息及其子元素的任意深度。  
  
-   **故障排除**。 **断言**functoid 可以用于测试你的假设有关元素值。  
  
## <a name="available-functoids"></a>可用的 functoid
  
 **高级**functoid 均： 

* “添加”Functoid
* “索引”Functoid 
* 迭代 Functoid 
* “循环”Functoid 
* “批量复制”functoid 
* “零值”Functoid
* “记录计数”Functoid 
* “脚本”Functoid 
* 表循环和表提取程序 Functoid
* “值映射”Functoid
* “值映射(平展)”Functoid

这些 functoid 更多详细信息位于**Functoid 引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="next-steps"></a>后续步骤
  
-   [断言 Functoid](../core/assert-functoid.md)  
  
-   [索引 Functoid](../core/index-functoid.md)  
  
-   [迭代 Functoid](../core/iteration-functoid.md)  
  
-   [循环 Functoid](../core/looping-functoid.md)  
  
-   [大容量复制 Functoid](../core/mass-copy-functoid.md)  
  
-   [Nil 值 Functoid](../core/nil-value-functoid.md)  
  
-   [记录计数 Functoid](../core/record-count-functoid.md)  
  
-   [表循环和表提取程序 Functoid](../core/table-looping-and-table-extractor-functoids.md)  
  
-   [值映射 Functoid](../core/value-mapping-functoid.md)  
  
-   [映射 （拼合） Functoid 的值](../core/value-mapping-flattening-functoid.md)  
  
-   [脚本 Functoid](../core/scripting-functoid.md)