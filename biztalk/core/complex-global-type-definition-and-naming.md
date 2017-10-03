---
title: "复杂全局类型定义和命名 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5a12956-7b77-4be8-b323-38363d04fcbc
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afe00c68f22dde956279f2dd5ac06d03bf9cb84d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="complex-global-type-definition-and-naming"></a>复杂全局类型定义和命名
在 BizTalk 编辑器中，定义复杂全局类型的第一步是将第一个出现的复杂类型转换为全局类型后，在使用该全局类型的位置之一进行定义。 现在，以地址示例继续进行说明，在架构中定义发货地址时，定义复杂地址类型。  
  
 在定义复杂类型后，您可以通过为其指定类型名称来将其转换为全局复杂类型。 通过选择节点对应于复杂类型，通常会执行此操作**记录**节点，，然后键入新的类型名称到**数据结构类型**该节点的属性。 尽管可见会不发生任何更改架构树中时为此属性指定一个名称 (例如， **GlobalAddrType**，下面的示例所示)，如果你检查内基础 XSD 架构的表示形式，会发生什么情况你将看到以下 （缩写） 更改。  
  
 在这之前，使用地址结构首先定义的上下文中**ShippingAddress**元素，以下发生。  
  
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
  
 后**ShippingAddress**节点已被授予一个唯一的名称，其**数据结构类型**导致它为复杂全局类型，可能会进行重复使用在多个位置中可用的属性架构，将发生以下情况。  
  
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
  
## <a name="see-also"></a>另请参阅  
 [类型重用和派生](../core/type-reuse-and-derivations.md)   
 [如何创建对另一个节点或类型的引用](../core/how-to-create-references-to-another-node-or-type.md)