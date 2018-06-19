---
title: 字段属性节点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e964c07-53e5-473f-84f2-05af4796cbbe
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 701acadc9d1612cc5b05a05970fc2c1b92bfbb9a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246029"
---
# <a name="field-attribute-nodes"></a>“字段属性”节点

## <a name="overview"></a>概述
在 BizTalk 编辑器中，使用**字段特性**节点来描述信息的简单的性质，如字符串和数字的项。 此外，它们时，使用问题的信息显示为一条消息，而不是显示为 XML 元素的内容的实际实例中的属性的值。 有关存储为元素内容的信息的其他信息，请参阅[字段元素节点](../core/field-element-nodes.md)。  
  
 虽然最简单利用**字段特性**作为的子节点的节点是**记录**节点，它们还可作为的子节点**属性组**节点。 在后一种情况下，**字段特性**节点的子级的**属性组**节点都可用作属性的任何**记录**包括该的节点**属性组**节点。 有关详细信息**属性组**节点，请参阅[特性组节点](../core/attribute-group-nodes.md)。  
  
> [!NOTE]
>  在 BizTalk 编辑器中，元素和属性元素可以通过表示**字段**节点，但它们具有不同架构树视图中，在 XSD 窗口中，不同的 XML 表示形式中与其关联的图标和在 Visual Studio 属性窗口中的不同属性。  
  
 对于任何给定项的 XML 消息，其中的信息项表示一个单个的离散简单类型，例如字符串或数字中的信息有始终是一个有关是否应作为元素，或作为该属性表示该信息的问题该元素的子元素。 作为一般规则、 表示一条信息项，如属性往往是更合适时可能的值为离散、 几个在编号、 和往往会修改该元素本身的语义。 子元素往往是更合适时可能的值可以重复变量次数，代表一条信息项很可能会有更广泛范围值、 可能会很长，如下所示的长字符串，和是几个同级值之一，其顺序并相关。 如果你创建现有类型的 XML 架构文档，你选择使用**Field 元素**节点或**字段特性**已为你进行特定项的信息的节点和你必须使用 XML 与匹配的节点。  
  
> [!NOTE]
>  根节点可能没有**字段**属性。 **字段**属性附加到**根**节点不会保存具有架构。  
  
## <a name="xsd-representation"></a>XSD 表示形式  
 当**字段特性**节点插入到**记录**节点，它将在任何其他子节点的末尾插入**记录**节点。 这包括正在之后插入**序列**，**选择**，或**所有**元素，其中包含的任何非属性节点，和任何以前的属性节点之后插入。 下面的示例演示一个新**字段特性**节点，以粗体显示，在末尾插入**记录**节点 （带有名为以阐明其标识的节点）。  
  
```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="FieldElement" type="xs:string" />  
            <xs:element name="EmptyNestedRecord">  
                <xs:complexType />  
            </xs:element>  
        </xs:sequence>  
        <xs:attribute name="ExistingFieldAttribute" type="xs:string" />  
  
    </xs:complexType>  
</xs:element>  
  
```  
  
## <a name="see-also"></a>另请参阅  
-  [BizTalk 表示形式架构](../core/biztalk-representation-of-schemas.md)   
-  [节点属性](../core/node-properties.md)   
-  **字段元素节点属性**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
-  [如何设置节点属性](../core/how-to-set-node-properties.md)   
-  [属性组节点](../core/attribute-group-nodes.md)