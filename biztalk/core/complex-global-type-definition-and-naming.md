---
title: 复杂全局类型定义和命名 |Microsoft 文档
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
ms.openlocfilehash: afe00c68f22dde956279f2dd5ac06d03bf9cb84d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231621"
---
# <a name="complex-global-type-definition-and-naming"></a><span data-ttu-id="5fa2b-102">复杂全局类型定义和命名</span><span class="sxs-lookup"><span data-stu-id="5fa2b-102">Complex Global Type Definition and Naming</span></span>
<span data-ttu-id="5fa2b-103">在 BizTalk 编辑器中，定义复杂全局类型的第一步是将第一个出现的复杂类型转换为全局类型后，在使用该全局类型的位置之一进行定义。</span><span class="sxs-lookup"><span data-stu-id="5fa2b-103">Within BizTalk Editor, you begin to define a complex global type by defining the first occurrence of the complex type in one of the locations where the global type will be used, after it has been converted to a global type.</span></span> <span data-ttu-id="5fa2b-104">现在，以地址示例继续进行说明，在架构中定义发货地址时，定义复杂地址类型。</span><span class="sxs-lookup"><span data-stu-id="5fa2b-104">Continuing with the address example, you might define the complex address type in the course of defining a shipping address within the schema.</span></span>  
  
 <span data-ttu-id="5fa2b-105">在定义复杂类型后，您可以通过为其指定类型名称来将其转换为全局复杂类型。</span><span class="sxs-lookup"><span data-stu-id="5fa2b-105">After the complex type is defined, you can convert it to a global complex type by giving it a type name.</span></span> <span data-ttu-id="5fa2b-106">通过选择节点对应于复杂类型，通常会执行此操作**记录**节点，，然后键入新的类型名称到**数据结构类型**该节点的属性。</span><span class="sxs-lookup"><span data-stu-id="5fa2b-106">You do this by selecting the node that corresponds to the complex type, which will generally be a **Record** node, and then typing a new type name into the **Data Structure Type** property of that node.</span></span> <span data-ttu-id="5fa2b-107">尽管可见会不发生任何更改架构树中时为此属性指定一个名称 (例如， **GlobalAddrType**，下面的示例所示)，如果你检查内基础 XSD 架构的表示形式，会发生什么情况你将看到以下 （缩写） 更改。</span><span class="sxs-lookup"><span data-stu-id="5fa2b-107">Although no visible changes occur in the schema tree when you give this property a name (such as, **GlobalAddrType**, as in the following example), if you examine what happens within the underlying XSD representation of the schema, you would see the following (abbreviated) change.</span></span>  
  
 <span data-ttu-id="5fa2b-108">在这之前，使用地址结构首先定义的上下文中**ShippingAddress**元素，以下发生。</span><span class="sxs-lookup"><span data-stu-id="5fa2b-108">Before, with the address structure first defined within the context of the **ShippingAddress** element, the following occurred.</span></span>  
  
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
  
 <span data-ttu-id="5fa2b-109">后**ShippingAddress**节点已被授予一个唯一的名称，其**数据结构类型**导致它为复杂全局类型，可能会进行重复使用在多个位置中可用的属性架构，将发生以下情况。</span><span class="sxs-lookup"><span data-stu-id="5fa2b-109">After the **ShippingAddress** node has been given a unique name in its **Data Structure Type** property, causing it to become available as a complex global type and subject to reuse in multiple places within the schema, the following occurs.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5fa2b-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5fa2b-110">See Also</span></span>  
 <span data-ttu-id="5fa2b-111">[类型重用和派生](../core/type-reuse-and-derivations.md) </span><span class="sxs-lookup"><span data-stu-id="5fa2b-111">[Type Reuse and Derivations](../core/type-reuse-and-derivations.md) </span></span>  
 [<span data-ttu-id="5fa2b-112">如何创建对另一个节点或类型的引用</span><span class="sxs-lookup"><span data-stu-id="5fa2b-112">How to Create References to Another Node or Type</span></span>](../core/how-to-create-references-to-another-node-or-type.md)