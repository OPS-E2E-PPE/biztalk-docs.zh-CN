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
# <a name="complex-global-type-definition-and-naming"></a><span data-ttu-id="328d9-102">复杂全局类型定义和命名</span><span class="sxs-lookup"><span data-stu-id="328d9-102">Complex Global Type Definition and Naming</span></span>
<span data-ttu-id="328d9-103">在 BizTalk 编辑器中，您开始通过一个全局类型将会使用的位置之后转换为全局类型, 中定义的复杂类型的第一个匹配项定义的复杂全局类型。</span><span class="sxs-lookup"><span data-stu-id="328d9-103">Within BizTalk Editor, you begin to define a complex global type by defining the first occurrence of the complex type in one of the locations where the global type will be used, after it has been converted to a global type.</span></span> <span data-ttu-id="328d9-104">继续使用地址示例，你可以定义在过程中定义发货地址架构中的复杂地址类型。</span><span class="sxs-lookup"><span data-stu-id="328d9-104">Continuing with the address example, you might define the complex address type in the course of defining a shipping address within the schema.</span></span>  
  
 <span data-ttu-id="328d9-105">复杂类型定义后，可以直接将其转换为全局复杂类型，为其提供类型名称。</span><span class="sxs-lookup"><span data-stu-id="328d9-105">After the complex type is defined, you can convert it to a global complex type by giving it a type name.</span></span> <span data-ttu-id="328d9-106">选择为复杂类型，这通常会相对应的节点执行此**记录**节点，并键入新的类型名称到**Data Structure Type**该节点的属性。</span><span class="sxs-lookup"><span data-stu-id="328d9-106">You do this by selecting the node that corresponds to the complex type, which will generally be a **Record** node, and then typing a new type name into the **Data Structure Type** property of that node.</span></span> <span data-ttu-id="328d9-107">虽然可见会不进行任何更改在架构树中时为此属性指定一个名称 (如**GlobalAddrType**，如以下示例中)，如果您检查架构的基础 XSD 表示形式中会发生什么情况，会看到以下 （缩写） 的更改。</span><span class="sxs-lookup"><span data-stu-id="328d9-107">Although no visible changes occur in the schema tree when you give this property a name (such as, **GlobalAddrType**, as in the following example), if you examine what happens within the underlying XSD representation of the schema, you would see the following (abbreviated) change.</span></span>  
  
 <span data-ttu-id="328d9-108">在这之前，使用地址结构中首次定义的上下文**ShippingAddress**元素中，以下发生。</span><span class="sxs-lookup"><span data-stu-id="328d9-108">Before, with the address structure first defined within the context of the **ShippingAddress** element, the following occurred.</span></span>  
  
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
  
 <span data-ttu-id="328d9-109">之后**ShippingAddress**节点已被授予的唯一名称，其**Data Structure Type**属性，使其变得可用的复杂全局类型，可能会进行中的多个位置重复使用架构中，将发生以下情况。</span><span class="sxs-lookup"><span data-stu-id="328d9-109">After the **ShippingAddress** node has been given a unique name in its **Data Structure Type** property, causing it to become available as a complex global type and subject to reuse in multiple places within the schema, the following occurs.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="328d9-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="328d9-110">See Also</span></span>  
 <span data-ttu-id="328d9-111">[类型重用和派生](../core/type-reuse-and-derivations.md) </span><span class="sxs-lookup"><span data-stu-id="328d9-111">[Type Reuse and Derivations](../core/type-reuse-and-derivations.md) </span></span>  
 [<span data-ttu-id="328d9-112">如何创建对其他节点或类型的引用</span><span class="sxs-lookup"><span data-stu-id="328d9-112">How to Create References to Another Node or Type</span></span>](../core/how-to-create-references-to-another-node-or-type.md)