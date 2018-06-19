---
title: 记录节点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43af077d-5db8-43ca-8bd0-e3a9e3ebe2b0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4486b875693827c6fed74e9293bdb68b2c3dc3b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268493"
---
# <a name="record-nodes"></a>“记录”节点
在 BizTalk 编辑器中，使用**记录**节点表示的信息，其中的各个项可以是集合：  
  
-   简单类型的信息，如字符串和数字，表示为子字段节点。 这些子字段节点可以是**Field 元素**节点或**字段特性**节点。 有关这两个类型的字段节点的其他信息，请参阅[字段元素节点](../core/field-element-nodes.md)和[字段属性节点](../core/field-attribute-nodes.md)。  
  
-   复杂类型的信息，表示为子**记录**节点或作为组节点 (**序列组**节点，**选项组**节点，或**所有组**节点)。  
  
-   任何类型检查的信息，表示为子**Any 元素**或**任何属性**节点。  
  
-   所表示的属性组的**属性组**节点。  
  
 当插入到新的子节点**记录**始终在当前的子节点的末尾插入节点、 子节点。 XML 架构定义 (XSD) 语言表示中, 新元素添加到其相应的区域，这意味着非属性元素一起添加到中的元素的末尾结束**序列**， **选择**，**所有**，或**组**元素和属性元素添加到任何其他属性的元素，它们都之后发生的末尾**序列**，**选择**，**所有**，或**组**元素。  
  
## <a name="xsd-representation"></a>XSD 表示形式  
 在第一次插入一个新的 XSD 表示**记录**节点只有三个行组成，如下面的示例中所示。  
  
```  
<xs:element name="Record">  
      <xs:complexType />  
</xs:element>  
```  
  
 当以外的三个属性节点之一的任何子节点 (**字段特性**，**属性组**，和**任何属性**) 添加到**记录**节点，默认情况下它放在**序列**中的元素**complexType**元素。 **序列**时添加，并且如果删除所有非属性子节点中删除第一个非属性子节点添加元素。 中添加的所有三种类型的属性节点**complexType**元素，但外部和之后任何**序列**元素。  
  
 **序列**元素内的非属性添加子节点也可以是**选择**或**所有**元素，如果你更改**组顺序类型 （节点所有架构的属性）** 属性的架构关系树中的相应节点**选择**或**所有**分别。  
  
 在下面的示例中，**记录**节点已被重命名的 shipTo。 中的位置**记录**添加属性和非属性节点下的节点显示在括号中。  
  
```  
<xs:element name="">  
    <xs:complexType>  
        <xs:sequence>  
            [Nonattribute child nodes of the record go here.]  
            [Always add new nonattribute child nodes to the end.]  
        </xs:sequence>  
            [Attribute child nodes of the record go here.]  
            [Always add new attribute child nodes to the end.]  
    </xs:complexType>  
</xs:element>  
  
```  
  
## <a name="see-also"></a>另请参阅  
-  [BizTalk 表示形式架构](../core/biztalk-representation-of-schemas.md)   
-  [节点属性](../core/node-properties.md)   
-  **记录节点属性**和**组顺序类型 （节点属性的所有架构的）**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
-  [如何设置节点属性](../core/how-to-set-node-properties.md)