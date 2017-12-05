---
title: "属性组节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea02fae8-4e03-486a-8d9d-185ae230d3a0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31814f9bd38bd07a75be0d4a2cc3e9d8b838720e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="attribute-group-nodes"></a>属性组节点

## <a name="overview"></a>概述
在 BizTalk 编辑器中，你可以添加**属性组**节点**记录**节点或其他**属性组**节点以包含你希望使用更多的属性组个**记录**节点。 添加**属性组**到另一个节点**属性组**节点来实现的属性组嵌套。 这允许你在一个位置，可在多个定义一组属性**记录**或**属性组**节点。 对属性组的后续修改将传播到该属性组所关联的所有节点。 不论在何种节点上下文中进行修改都是如此。  
  
> [!NOTE]
>  在 BizTalk 编辑器中， **AttributeGroup**节点表示默认情况下，使用字符串\<AttribGroup:attribGroup*N* \>在架构树视图中，其中*N*是单调递增的数字。 你可以更改 attribGroup*N*通过键入新的唯一名称，在其名称一部分其**组引用**属性。  
  
 最初创建时**属性组**节点，你只需将其插入到之一**记录**或**属性组**节点，它将使用，并选择性地更改其名称在其**组引用**属性。 有两种方法要在另一个中使用相同的属性组**记录**或**属性组**节点：  
  
-   你可以复制现有**属性组**节点然后将其粘贴到该其他**记录**节点。  
  
-   你可以将插入一个新**属性组**节点到该其他**记录**节点，再然后将其设置**组引用**属性的新**属性组**节点以引用现有**属性组**节点。  
  
 此后，你可以修改**属性组**节点-例如，通过添加或删除**字段特性**节点-任何的上下文中**记录**或**属性组**粘贴到其中的节点。 更改将传播到所有其他**记录**或**属性组**属性组与之关联的节点。  
  
 它毫无添加**属性组**而无需添加至少一个相关节点，其中包括相关节点的节点**字段特性**节点，**任何属性**节点，和 （嵌套）**属性组**节点。 事实上，仅包含一个属性的属性组是有些考虑不周的，除非您计划以后将添加更多属性。  
  
 **属性组**节点可以相互嵌套，从而可以如何构造和组合属性组的更多的可能性。 **属性组**节点还可以包含**任何属性**节点，使属性组以包含通配符字符功能来处理可以适应将属性实例。  
  
## <a name="xsd-representation"></a>XSD 表示形式  
 当**属性组**首先将节点添加到**记录**节点或其他**属性组**节点中，相应的 XML 架构定义 (XSD) 的两个不同的区域语言架构表示形式会受到影响。 在下面的示例中，新**属性组**节点，在加粗，并且已添加到现有**记录**已包含的现有节点**Field 元素**节点。  
  
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
  
 请注意如何**attributeGroup**的 XSD 表示形式中的元素**记录**节点引用全局**attributeGroup**作为子级添加的元素**架构**元素。 架构的 XSD 表示形式中的此属性组全局定义允许在整个架构的多个位置引用属性组。  
  
> [!NOTE]
>  会自动提供的默认属性组名称都具有窗体 attrGroup*N*，其中*N*是单调递增的数字。 可以通过提供新的、 唯一的名称，在属性组重命名其**组引用**属性。 不能在架构树中对属性组进行重命名。  
  
## <a name="see-also"></a>另请参阅  
-  [架构的 BizTalk 表示形式](../core/biztalk-representation-of-schemas.md)   
-  [节点属性](../core/node-properties.md)   
-  **序列组节点属性**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
-  [如何设置节点属性](../core/how-to-set-node-properties.md)   
-  [“字段属性”节点](../core/field-attribute-nodes.md)   
-  [“任何属性”节点](../core/any-attribute-nodes.md)