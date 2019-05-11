---
title: 表循环 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Table Looping functoids
- Table Looping functoids, about Table Looping functoids
ms.assetid: 6189a789-afe7-4e72-a778-2b0374db8f69
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 140d173f9aa037174190d03bffad181423dfab5d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291677"
---
# <a name="table-looping-functoid"></a>表循环 Functoid
**表循环**functoid，您可以创建包含可用于创建输出实例消息的输出值的表。 表中的数据可以包含链接和常数。 第一个输入的参数**表循环**functoid 配置作用域，或多少次都将循环记录。 第二个输入参数**表循环**functoid 确定多少列在表中，和的剩余输入顺序不分先后定义表的可能单元格值。 有关使用这些属性的详细信息，请参阅[Table-Driven 循环配置](../core/table-driven-looping-configuration.md)。 另请参阅[Table-Driven 循环示例](../core/table-driven-looping-example.md)。  
  
> [!NOTE]
>  **表循环**functoid 重复处理连接到的循环记录。 在每次迭代，它将循环后每个表循环网格中的行，生成多个输出循环。  
  
## <a name="see-also"></a>请参阅  
 [表提取程序 Functoid](../core/table-extractor-functoid.md)   
 [如何添加表循环和表提取程序 Functoid 映射](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)   
 [高级的 Functoid](../core/advanced-functoids.md)   
 [索引 Functoid](../core/index-functoid.md)   
 [迭代 Functoid](../core/iteration-functoid.md)   
 [循环 Functoid](../core/looping-functoid.md)   
 [记录计数 Functoid](../core/record-count-functoid.md)