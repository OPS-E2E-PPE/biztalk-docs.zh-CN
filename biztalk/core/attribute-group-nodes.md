---
title: 属性组节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea02fae8-4e03-486a-8d9d-185ae230d3a0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11bfc51f2a7ec1d4b8c7a856028e4d6b00ba8d22
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359120"
---
# <a name="attribute-group-nodes"></a>属性组节点

## <a name="overview"></a>概述
在 BizTalk 编辑器中，可以添加**属性组**节点到节点**记录**节点或另一个**属性组**要包含的一组您希望在详细信息中使用的属性节点高于**记录**节点。 添加**属性组**到另一个节点**属性组**节点来实现的属性组嵌套。 这允许你在一个位置，可在多个定义的一组属性**记录**或**属性组**节点。 属性组的后续修改将传播到所有该属性组与之关联的节点。 这是而不考虑节点上下文进行了修改，则返回 true。  

> [!NOTE]
>  在 BizTalk 编辑器中， **AttributeGroup**节点的表示方法的字符串的默认\<AttribGroup:attribGroup*N* \>在架构树视图中，其中*N*是单调递增的数字。 您可以更改 attribGroup*N*通过键入新的唯一名称在其名称的部分及其**组参考**属性。  

 最初创建时**属性组**节点，您只需将其插入到之一**记录**或**属性组**节点，它将使用，并选择性地更改其名称在其**组参考**属性。 有两种方法要在另一个中使用相同的属性组**记录**或**属性组**节点：  

- 您可以将复制的现有**属性组**节点，然后将其粘贴到该其他**记录**节点。  

- 您可以插入一个新**属性组**到该其他节点**记录**节点，然后设置**组参考**属性的新**属性组**节点以引用现有**属性组**节点。  

  此后，您可以修改**属性组**节点 — 例如，通过添加或删除**字段属性**节点，在任何上下文中**记录**或**属性组**粘贴到其中的节点。 更改将传播到所有其他**记录**或**属性组**属性组与之关联的节点。  

  它是无意义的添加**属性组**节点，而无需添加至少一个相关节点，其中包括**Field 特性**节点，**任何属性**节点，和 （嵌套）**属性组**节点。 事实上，仅包含单个属性的属性组是有些构思有问题，除非要进行的规划添加更多属性在将来的点。  

  **属性组**节点可以相互嵌套，从而在如何构造和组合的属性组中的更多可能性。 **属性组**节点还可以包含**任何属性**节点，使属性组以包含有关的特性实例，它可以包含通配符功能。  

## <a name="xsd-representation"></a>XSD 表示形式  
 当**属性组**首先将节点添加到**记录**节点或另一个**属性组**节点、 两个区域的相应 XML 架构定义 (XSD)语言架构表示形式会受到影响。 在以下示例中，一个新**属性组**节点，在加粗，并且已添加到现有**记录**已包含的现有节点**字段元素**节点。  

```  
        ...  
        <xs:element name="ExistingRecord">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="ExistingFieldElement" type="xs:string" />  
                </xs:sequence>  
                <xs:attributeGroup ref="attrGroup0" />  
            </xs:complexType>  
        </xs:element>  
        ...   
    <xs:attributeGroup name="attrGroup0" />  
</xs:schema>  
```  

 请注意如何**attributeGroup**元素中的 XSD 表示形式**记录**节点引用全局**attributeGroup**作为子级添加的元素**架构**元素。 架构的 XSD 表示形式中的属性组的全局定义允许在整个架构的多个位置中只能引用属性组。  

> [!NOTE]
>  会自动提供的默认属性组名称具有窗体 attrGroup*N*，其中*N*是单调递增的数字。 可以通过提供一个新的唯一名称，在重命名某一属性组及其**组参考**属性。 在架构树中的位置，不能重命名某一属性组。  

## <a name="see-also"></a>请参阅  
- [架构的 BizTalk 表示形式](../core/biztalk-representation-of-schemas.md)   
- [节点属性](../core/node-properties.md)   
- **序列组节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
- [如何设置节点属性](../core/how-to-set-node-properties.md)   
- [“字段属性”节点](../core/field-attribute-nodes.md)   
- [“任何属性”节点](../core/any-attribute-nodes.md)
