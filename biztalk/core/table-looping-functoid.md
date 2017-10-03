---
title: "表循环 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Table Looping functoids
- Table Looping functoids, about Table Looping functoids
ms.assetid: 6189a789-afe7-4e72-a778-2b0374db8f69
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c5e5f2967fb48bfe896c26246db1630266812f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="table-looping-functoid"></a>“表循环”Functoid
**表循环**functoid 使你能够创建要在创建输出实例消息中使用的输出值的表。 该表中的数据可以由链接和常数组成。 第一个输入的参数**表循环**functoid 配置作用域，或次数将循环记录。 第二个输入参数**表循环**functoid 确定多少列是在表中，并且剩余输入定义为表的可能的单元格值顺序不分先后。 有关使用这些属性的详细信息，请参阅[Table-Driven 循环配置](../core/table-driven-looping-configuration.md)。 另请参阅[Table-Driven 循环示例](../core/table-driven-looping-example.md)。  
  
> [!NOTE]
>  **表循环**functoid 重复与它连接到的循环记录。 在每次迭代中，对于表循环网格中的每一行该 functoid 都将循环一次，从而生成多个输出循环。  
  
## <a name="see-also"></a>另请参阅  
 [表提取程序 Functoid](../core/table-extractor-functoid.md)   
 [如何添加表循环以及到地图表提取程序 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)   
 [高级的 Functoid](../core/advanced-functoids.md)   
 [索引 Functoid](../core/index-functoid.md)   
 [迭代 Functoid](../core/iteration-functoid.md)   
 [循环 Functoid](../core/looping-functoid.md)   
 [记录计数 Functoid](../core/record-count-functoid.md)