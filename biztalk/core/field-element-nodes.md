---
title: "字段元素节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65b5e1f6-283f-4172-9bc2-f04a0ea6753d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74c3732ee315ad307f49760e367449216c3e01da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="field-element-nodes"></a>“字段元素”节点

## <a name="overview"></a>概述
在 BizTalk 编辑器中，使用**Field 元素**节点来描述信息的简单的性质，如字符串和数字的项。 此外，它们时，使用问题的信息显示为一条消息，而不是显示为一个 XML 元素与关联属性的值的实际实例中的 XML 元素的内容。 有关存储作为特性值的信息的其他信息，请参阅[字段属性节点](../core/field-attribute-nodes.md)。  
  
> [!NOTE]
>  在 BizTalk 编辑器中，元素和属性元素可以通过表示**字段**节点，但它们具有不同架构树视图中，在 XSD 窗口中，不同的 XML 表示形式中与其关联的图标和在 Visual Studio 属性窗口中的不同属性。  
  
 对于任何给定项的 XML 消息，其中的信息项表示一个单个的离散简单类型，例如字符串或数字中的信息有始终是一个有关是否应作为元素，或作为该属性表示该信息的问题该元素的子元素。 作为一般规则、 表示一条信息项，如属性往往是更合适时可能的值为离散、 几个在编号、 和往往会修改该元素本身的语义。 子元素往往是更合适时可能的值可以重复变量次数，代表一条信息项很可能会有更广泛范围值、 可能会很长，如下所示的长字符串，和是几个同级值之一，其顺序并相关。 如果你只需创建的现有类型的 XML 架构文档，你选择使用**Field 元素**节点或**字段特性**已为你进行特定项的信息的节点并且，你必须使用 XML 与匹配的节点。  
  
## <a name="xsd-representation"></a>XSD 表示形式  
 当**Field 元素**节点插入到**记录**节点，它将在任何其他子节点的末尾插入**序列**中的元素**记录**节点。 下面的示例演示一个新**Field 元素**节点，以粗体显示，在末尾插入**序列**中的元素**记录**节点 （带有名为以阐明其标识的节点).  
  
```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
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