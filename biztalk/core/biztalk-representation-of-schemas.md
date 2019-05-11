---
title: BizTalk 架构表示法 |Microsoft Docs
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
ms.openlocfilehash: 189ece3b7b79c0272a435ba7b3ef1a40b9eac883
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357963"
---
# <a name="biztalk-representation-of-schemas"></a>BizTalk 架构表示法

## <a name="overview"></a>概述
虽然 BizTalk 架构最终表示，并保留在 XML 架构定义 (XSD) 语言中，这些列表示为节点的图形化层次结构中，当 BizTalk 编辑器中使用。 在层次结构的顶层始终是**\<架构\>** 节点，然后其余类型的节点用于生成架构，使其表示通过使用 BizTalk 交换的特定消息。  

## <a name="insert-schema-node-options"></a>插入架构节点选项  
 BizTalk 编辑器提供了一种方法来构造 XSD 架构，而无需了解任何复杂的 XSD 语法。 使用时**插入 Schema 节点**命令**BizTalk**菜单或快捷菜单，要插入的节点的以下选项将出现在级联菜单。  


| 插入 Schema 节点菜单选项 |                                                                                                                                                                                                                                          Description                                                                                                                                                                                                                                          |
|--------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        **子记录**        |                                                                                                                                                           将插入**记录**节点中所选节点的序列的末尾。 有关详细信息**记录**节点，请参阅[记录节点](../core/record-nodes.md)。                                                                                                                                                            |
|   **子字段属性**    |                                                                                                                                  将插入**字段属性**末尾的所选节点**记录**或**属性组**节点。 有关详细信息**字段属性**节点，请参阅[字段属性节点](../core/field-attribute-nodes.md)。                                                                                                                                   |
|    **子字段元素**     |                                                                                                                                                           将插入**Field 元素**选定节点中的节点。 有关详细信息**Field 元素**节点，请参阅[字段元素节点](../core/field-element-nodes.md)。                                                                                                                                                           |
|       **同级记录**       |                                                                                                                                                         将插入**记录**节点包含所选的节点的序列的末尾。 有关详细信息**记录**节点，请参阅[记录节点](../core/record-nodes.md)。                                                                                                                                                          |
|  **同级字段属性**   |                                                                                                                        将插入**字段属性**末尾处的节点**记录**或**属性组**包含所选的节点的节点。 有关详细信息**字段属性**节点，请参阅[字段属性节点](../core/field-attribute-nodes.md)。                                                                                                                         |
|   **同级字段元素**    |                                                                                                                                           将插入**Field 元素**节点包含所选的节点的序列的末尾。 有关详细信息**Field 元素**节点，请参阅[字段元素节点](../core/field-element-nodes.md)。                                                                                                                                            |
|       **序列组**       |                                                                                                                           将插入**序列组**节点 (\<序列\>树视图中) 中所选节点的序列的末尾。 有关详细信息**序列组**节点，请参阅[序列组节点](../core/sequence-group-nodes.md)。                                                                                                                            |
|        **选择组**        |                                                                                                                                将插入**选择组**节点 (\<选择\>树视图中) 中所选节点的序列的末尾。 有关详细信息**选择组**节点，请参阅[所选组节点](../core/choice-group-nodes.md)。                                                                                                                                 |
|         **所有组**          | 将插入**全部组**节点 (\<所有\>在树视图中) 的唯一非属性子节点作为**记录**节点，替换默认使用的**序列**中的元素**记录**使用的节点**所有**元素。 可以插入之前**全部组**节点，则必须更改**内容类型**包含的属性**记录**节点到**ComplexContent**. 有关详细信息**全部组**节点，请参阅[组的所有节点](../core/all-group-nodes.md)。 |
|      **属性组**       |                                                                                  将插入**属性组**节点 (\<AttrGroup:attrGroup*N* \>在树视图中，其中*N*是单调递增的数字) 在所选的最终**记录**或**属性组**节点。 有关详细信息**属性组**节点，请参阅[属性组节点](../core/attribute-group-nodes.md)。                                                                                   |
|        **任何元素**         |                                                                                 将插入**Any 元素**节点 (<strong>\<</strong>任何<strong>\></strong> 树视图中) 中所选的序列末尾**记录**，**序列组**，**选择组**，或**全部组**节点。 有关详细信息**Any 元素**节点，请参阅[Any 元素节点](../core/any-element-nodes.md)。                                                                                 |
|       **任何属性**        |                                                                                         将插入**任何属性**节点 (<strong>\<</strong>AnyAttribute<strong>\></strong>树视图中) 中所选序列末尾**记录**或**属性组**节点。 有关详细信息**任何属性**节点，请参阅[Any 属性节点](../core/any-attribute-nodes.md)。                                                                                         |

 在许多情况下，添加 BizTalk 编辑器中添加的架构的相应 XSD 表示形式中的多个嵌套元素的结果中的单个节点。 因为这些嵌套的元素可能具有复杂的语法，使用 BizTalk 编辑器以图形方式排列节点是更不容易出错的方法来构造 XSD 架构比手动编辑 XSD。 要考虑的另一个因素是，始终使用 BizTalk 编辑器来构造 XSD 架构会导致更容易控制的 XSD 架构说明中正在使用子集。  

 总之，BizTalk 编辑器中组合简化的方法来构造 XSD 架构使用记录的一般概念，并具有特定 XSD 的更多显式控件的字段构造，如**序列**， **所选**，**任何**，和**anyattribute**元素。  

 每种节点类型具有一套独特的可以在 Visual Studio 属性窗口中配置的属性。 一般情况下，这些属性对应于架构的相应 XSD 表示形式中的 XSD 元素的特性。 有关节点属性的详细信息，请参阅**节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

 本部分介绍使用 BizTalk 编辑器中的节点类型，简要讨论其属性，并提供链接来参考有关其属性的信息。  

## <a name="next-steps"></a>后续步骤

-   [直接对应于消息实例数据和结构的节点](../core/nodes-that-correspond-directly-to-message-instance-data-and-structure.md)  

-   [控制实例消息结构和变体的节点](../core/nodes-that-control-instance-message-structure-and-variations.md)  

-   [简化架构创建的节点](../core/nodes-that-simplify-schema-creation.md)  

-   [提供通配符功能的节点](../core/nodes-that-provide-wildcard-capabilities.md)  

-   [节点属性](../core/node-properties.md)