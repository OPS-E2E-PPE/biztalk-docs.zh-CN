---
title: 记录节点 |Microsoft Docs
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
ms.openlocfilehash: beb676565b539f813062e9083265903350724a09
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398051"
---
# <a name="record-nodes"></a>记录节点
在 BizTalk 编辑器中，使用**记录**节点，用于表示集合的信息，其中的各个项可以是：  

- 简单类型的信息，如字符串和数字，表示为子字段节点。 这些子字段节点可以是**Field 元素**节点或**字段属性**节点。 有关字段节点这两种类型的其他信息，请参阅[字段元素节点](../core/field-element-nodes.md)并[字段属性节点](../core/field-attribute-nodes.md)。  

- 复杂类型的信息，表示为子**记录**节点或一个组节点 (**序列组**节点，**选择组**节点，或**全部组**节点)。  

- 任何未检查的类型的信息，表示为子**Any 元素**或**任何属性**节点。  

- 所表示的属性组的**属性组**节点。  

  插入到新的子节点时**记录**节点、 子节点始终插入到当前的子节点的末尾。 在 XML 架构定义 (XSD) 语言表示形式，将新元素添加到其相应的区域，这意味着非属性元素都添加到中的元素末尾的最终**序列**， **所选**，**所有**，或**组**元素和属性元素添加到任何其他属性元素，所有这些之后发生的末尾**序列**，**选**，**所有**，或**组**元素。  

## <a name="xsd-representation"></a>XSD 表示形式  
 当第一次插入的一个新的 XSD 表示形式**记录**节点只有三个行组成，如下面的示例中所示。  

```  
<xs:element name="Record">  
      <xs:complexType />  
</xs:element>  
```  

 当三个属性节点以外的任何子节点 (**字段属性**，**属性组**，并**任何属性**) 添加到**记录**节点，放在默认情况下**序列**元素内的**complexType**元素。 **序列**时添加，并且如果删除所有非属性子节点中删除第一个非属性子节点添加元素。 中添加的所有三种类型的属性节点**complexType**元素，但之外及之后任何**序列**元素。  

 **序列**中的非属性子节点将被添加的元素也可以是**选**或**所有**元素，如果更改**Group Order Type （节点所有架构的属性）** 相应的架构树中节点的属性**选**或**所有**分别。  

 在以下示例中，**记录**节点已重命名为的 shipTo。 中的位置**记录**其中添加属性和非属性节点的节点显示在方括号中。  

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

## <a name="see-also"></a>请参阅  
- [架构的 BizTalk 表示形式](../core/biztalk-representation-of-schemas.md)   
- [节点属性](../core/node-properties.md)   
- **记录节点属性**和**组顺序类型 （所有架构的节点属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
- [如何设置节点属性](../core/how-to-set-node-properties.md)
