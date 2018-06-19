---
title: BizTalk 表示形式架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f0460a37-1f4f-4c0b-91db-bb457f434fe9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3641e2728c29eaed0733839dcb577ae7f2aad2a9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966531"
---
# <a name="biztalk-representation-of-schemas"></a>BizTalk 架构表示法

## <a name="overview"></a>概述
虽然 BizTalk 架构最终以 XML 架构定义 (XSD) 语言表示和保存，但在 BizTalk 编辑器中使用时，它们是以节点的图形化层次结构形式表示的。 层次结构的顶层是始终**\<架构\>** 节点和剩余的节点类型用于生成架构，使其表示通过使用 BizTalk 交换某个特定消息。  

## <a name="insert-schema-node-options"></a>插入架构节点选项  
 BizTalk 编辑器提供了一种无需了解任何复杂的 XSD 语法便可构造 XSD 架构的方法。 使用时**插入架构节点**命令**BizTalk**菜单或快捷菜单，要插入的节点的选项如下的级联菜单上提供。  
  
|“插入 Schema 节点”菜单选项|Description|  
|------------------------------------|-----------------|  
|**子记录**|将插入**记录**中所选节点序列末尾的节点。 有关详细信息**记录**节点，请参阅[记录节点](../core/record-nodes.md)。|  
|**子字段特性**|将插入**字段特性**末尾的所选节点**记录**或**属性组**节点。 有关详细信息**字段特性**节点，请参阅[字段属性节点](../core/field-attribute-nodes.md)。|  
|**子 Field 元素**|将插入**Field 元素**内所选节点的节点。 有关详细信息**Field 元素**节点，请参阅[字段元素节点](../core/field-element-nodes.md)。|  
|**同级记录**|将插入**记录**包含所选的节点的序列末尾的节点。 有关详细信息**记录**节点，请参阅[记录节点](../core/record-nodes.md)。|  
|**同级字段特性**|将插入**字段特性**节点末尾**记录**或**属性组**包含所选的节点的节点。 有关详细信息**字段特性**节点，请参阅[字段属性节点](../core/field-attribute-nodes.md)。|  
|**同级 Field 元素**|将插入**Field 元素**包含所选的节点的序列末尾的节点。 有关详细信息**Field 元素**节点，请参阅[字段元素节点](../core/field-element-nodes.md)。|  
|**序列组**|将插入**序列组**节点 (\<序列\>树视图中) 中所选节点序列的末尾。 有关详细信息**序列组**节点，请参阅[序列组节点](../core/sequence-group-nodes.md)。|  
|**选择组**|将插入**选项组**节点 (\<选择\>树视图中) 中所选节点序列的末尾。 有关详细信息**选项组**节点，请参阅[选择组节点](../core/choice-group-nodes.md)。|  
|**所有组**|将插入**所有组**节点 (\<所有\>树视图中) 的唯一的非属性子节点作为**记录**节点，替换默认使用的**序列**中的元素**记录**节点使用**所有**元素。 你可以将插入之前**所有组**节点，则必须更改**内容类型**属性包含**记录**节点**ComplexContent**. 有关详细信息**所有组**节点，请参阅[组的所有节点](../core/all-group-nodes.md)。|  
|**属性组**|将插入**属性组**节点 (\<AttrGroup:attrGroup*N* \>在树视图中，其中*N*是单调递增的数字) 在所选的末尾**记录**或**属性组**节点。 有关详细信息**属性组**节点，请参阅[特性组节点](../core/attribute-group-nodes.md)。|  
|**任何元素**|将插入**Any 元素**节点 (**\<** 任何**\>** 树视图中) 中所选序列末尾**记录**，**序列组**，**选项组**，或**所有组**节点。 有关详细信息**Any 元素**节点，请参阅[任何元素节点](../core/any-element-nodes.md)。|  
|**任何属性**|将插入**任何属性**节点 (**\<** AnyAttribute **\>** 树视图中) 中所选序列末尾**记录**或**属性组**节点。 有关详细信息**任何属性**节点，请参阅[Any 属性节点](../core/any-attribute-nodes.md)。|  
  
 在许多情况下，在 BizTalk 编辑器中添加单个节点会导致在架构的相应 XSD 表示形式中添加多个嵌套元素。 因为这些嵌套元素可能具有复杂的语法，所以与手动编辑 XSD 相比，使用 BizTalk 编辑器以图形方式排列节点是更不易出错的方法。 另一个考虑因素是，始终使用 BizTalk 编辑器来构造 XSD 架构，会产生可在架构说明中使用的更容易控制的 XSD 的子集。  
  
 总体上而言，BizTalk 编辑器合并简化的方法构造 XSD 架构使用记录的一般概念，并具有特定 XSD 更多显式控件的字段构造，如**序列**， **选择**，**任何**，和**anyattribute**元素。  
  
 每一种类型的节点都具有唯一的属性集，该属性集可以在 Visual Studio 的“属性”窗口中配置。 通常，这些属性对应于架构的相应 XSD 表示形式中的 XSD 元素上的特性。 有关节点属性的详细信息，请参阅**节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
 本部分介绍了 BizTalk 编辑器中使用的节点类型，简要讨论了这些节点的属性，并提供了指向有关这些属性的参考信息的链接。  
  
## <a name="next-steps"></a>后续步骤
  
-   [直接对应于消息实例数据和结构的节点](../core/nodes-that-correspond-directly-to-message-instance-data-and-structure.md)  
  
-   [控制实例消息结构和变体的节点](../core/nodes-that-control-instance-message-structure-and-variations.md)  
  
-   [简化架构创建的节点](../core/nodes-that-simplify-schema-creation.md)  
  
-   [提供通配符功能的节点](../core/nodes-that-provide-wildcard-capabilities.md)  
  
-   [节点属性](../core/node-properties.md)