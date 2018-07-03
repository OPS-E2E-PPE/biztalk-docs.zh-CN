---
title: 表驱动循环配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Table Looping functoids
- Table Extractor functoids, configuring
- Table Extractor functoids
- Table Extractor functoids, adding to grid
- Table Looping functoids, about Table Looping functoids
- Table Looping functoids, configuring
- Table Extractor functoids, about Table Extractor functoids
- Table Looping functoids, adding to map
ms.assetid: ecc24d9b-ebc0-4559-9746-58e3b00c02ab
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46e8368dd57b32eab98c1a1dc3432e5be2012363
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973006"
---
# <a name="table-driven-looping-configuration"></a>表驱动循环配置
按照以下步骤配置映射中的表驱动循环：  
  
- **向映射添加表循环 functoid。** 只需要一**表循环**functoid 每个表驱动循环实例。 例如，如果你使用表驱动循环派生 BillTo 和 ShipTo 信息，则需要只有一个**表循环**functoid 在映射中的。 但是，如果你使用表驱动循环派生 BillTo 和 ShipTo 信息以及 StoreName 和 StoreAddress 信息，则可能需要两个**表循环**functoid 在映射中的。  
  
- **将多个表提取程序 functoid 添加到显示的网格页。** 添加任意数量**表提取程序**functoid 作为您需要为每个**表循环**functoid。 数**表提取程序**functoid 依赖于目标架构中的字段数。 例如，如果您只需**AddressCode**在你源架构和 CompanyName、 地址、 城市、 州、 邮政编码和 AttentionName 目标架构中的，您需要添加六个**表提取程序**向显示的网格页的 functoid。  
  
- **将表循环 functoid 配置相应的输入。** 首先，链接**表循环**functoid 到输入的实例记录或元素。 同时，还要将其链接到输出实例消息中的结构。 接下来，通过配置输入**配置\<Functoid\> Functoid**对话框。 有关如何配置此属性的详细信息，请参阅[编辑 Functoid 属性和输入参数](../core/editing-functoid-properties-and-input-parameters.md)。 输入的输入列表必须是全面而完整，因为这是将用于配置的数据**表 Functoid 网格**属性。 输入参数必须按以下方式定义：  
  
  -   **第一个输入。** 第一个输入参数是指向输入实例消息记录或字段的链接。 **表循环**functoid 为每个记录或字段实例循环一次。  
  
      > [!NOTE]
      >  此参数为必填输入参数。  
  
  -   **第二个输入。** 第二个输入参数定义循环网格中的列数。 该网格最多可包含 228 列。  
  
      > [!NOTE]
      >  此参数为必填输入参数。  
  
  -   **剩余输入参数。** 剩余的输入**表循环**functoid 包含所有中可能出现的可能值的列表**表 Functoid 网格**。  
  
      > [!NOTE]
      >  标记链接非常有用。 如果没有标记，链接将显示在**表 Functoid 网格**为完全指定路径。  
  
       有关如何配置的输入的分步说明**表循环**functoid，请参阅[如何添加表循环和向映射表提取程序 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)。 具体地讲，就是步骤 3 到步骤 8。  
  
- **配置表循环 functoid 的表 Functoid 网格属性。** 使用**表 Functoid 网格**以打开**配置表循环 Functoid**对话框配置循环网格中的单元格。  
  
   有关如何配置循环网格的分步说明，请参阅[如何添加表循环和向映射表提取程序 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)。 具体地讲，就是步骤 9 到步骤 10。  
  
- **配置表提取程序 functoid。** 使用**输入参数**属性可配置**表提取程序**functoid 的输入，如下所示：  
  
  - **第一个输入。** 第一个输入的参数**表提取程序**functoid**表循环**functoid。  
  
  - **第二个输入。** 第二个输入参数指定要从行中的哪一列提取数据。  
  
    有关如何配置的分步说明**表提取程序**与关联的 functoid**表循环**functoid，请参阅[如何添加表循环和表提取程序向映射 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)。 具体而言，请参阅步骤 11 到 16。  
  
## <a name="see-also"></a>请参阅  
 [表循环 Functoid](../core/table-looping-functoid.md)   
 [表提取程序 Functoid](../core/table-extractor-functoid.md)   
 [表驱动循环示例](../core/table-driven-looping-example.md)   
 [如何添加表循环和表提取程序 Functoid 映射](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)   
 [高级的 Functoid](../core/advanced-functoids.md)   
 [索引 Functoid](../core/index-functoid.md)   
 [迭代 Functoid](../core/iteration-functoid.md)   
 [循环 Functoid](../core/looping-functoid.md)   
 [“记录计数”Functoid](../core/record-count-functoid.md)