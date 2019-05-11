---
title: 复杂全局类型定义和命名 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5a12956-7b77-4be8-b323-38363d04fcbc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ead0eac56b44a5fe4c6488800717e76cb09a4615
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356831"
---
# <a name="complex-global-type-definition-and-naming"></a>复杂全局类型定义和命名
在 BizTalk 编辑器中，您开始通过一个全局类型将会使用的位置之后转换为全局类型, 中定义的复杂类型的第一个匹配项定义的复杂全局类型。 继续使用地址示例，你可以定义在过程中定义发货地址架构中的复杂地址类型。  
  
 复杂类型定义后，可以直接将其转换为全局复杂类型，为其提供类型名称。 选择为复杂类型，这通常会相对应的节点执行此**记录**节点，并键入新的类型名称到**Data Structure Type**该节点的属性。 虽然可见会不进行任何更改在架构树中时为此属性指定一个名称 (如**GlobalAddrType**，如以下示例中)，如果您检查架构的基础 XSD 表示形式中会发生什么情况，会看到以下 （缩写） 的更改。  
  
 在这之前，使用地址结构中首次定义的上下文**ShippingAddress**元素中，以下发生。  
  
```  
<xs:schema>  
  <xs:element name="Root">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="ShippingAddress">  
        [address structure initially defined here.]  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 之后**ShippingAddress**节点已被授予的唯一名称，其**Data Structure Type**属性，使其变得可用的复杂全局类型，可能会进行中的多个位置重复使用架构中，将发生以下情况。  
  
```  
<xs:schema>  
  <xs:element name="Root">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="ShippingAddress" type="GlobalAddrType" />  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
  <xs:complexType name="GlobalAddrType">  
  [address structure now defined globally here.]  
  </xs:complexType>  
</xs:schema>  
```  
  
## <a name="see-also"></a>请参阅  
 [类型重用和派生](../core/type-reuse-and-derivations.md)   
 [如何创建对其他节点或类型的引用](../core/how-to-create-references-to-another-node-or-type.md)