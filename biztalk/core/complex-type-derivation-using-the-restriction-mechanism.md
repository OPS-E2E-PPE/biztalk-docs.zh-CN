---
title: "使用限制机制的复杂类型派生 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3003d88-6b75-4dcb-834f-1babcf7449cb
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddbd9d8266d9c289b9b4bae9dd7060906e01ebd7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="complex-type-derivation-using-the-restriction-mechanism"></a><span data-ttu-id="16f5a-102">使用限制机制进行复杂类型派生</span><span class="sxs-lookup"><span data-stu-id="16f5a-102">Complex Type Derivation Using the Restriction Mechanism</span></span>
<span data-ttu-id="16f5a-103">在 BizTalk 编辑器功能方面，通过限制进行派生与通过扩展进行派生类似。</span><span class="sxs-lookup"><span data-stu-id="16f5a-103">Derivation by restriction is similar to derivation by extension, in terms of BizTalk Editor functionality.</span></span> <span data-ttu-id="16f5a-104">通过限制派生的复杂类型与其基本数据类型类似，只是其声明比基本数据类型中的相应声明具有更多限制性。</span><span class="sxs-lookup"><span data-stu-id="16f5a-104">A complex type derived by restriction is similar to its base data type, except that its declarations are more limited than the corresponding declarations in the base data type.</span></span> <span data-ttu-id="16f5a-105">实际上，新类型所表示的值是基本数据类型所表示的值的子集（与简单类型限制的情况一样）。</span><span class="sxs-lookup"><span data-stu-id="16f5a-105">In fact, the values represented by the new type are a subset of the values represented by the base data type (as is the case with restriction of simple types).</span></span> <span data-ttu-id="16f5a-106">使用基本数据类型的值的应用程序应当能够成功处理所有限制的类型的值。</span><span class="sxs-lookup"><span data-stu-id="16f5a-106">An application prepared for the values of the base data type ought to be able to successfully process any of the values of the restricted type.</span></span>  
  
 <span data-ttu-id="16f5a-107">有关使用限制机制派生新的复杂类型的全面信息，请参阅 W3C 网站。</span><span class="sxs-lookup"><span data-stu-id="16f5a-107">For comprehensive information about deriving new complex types by using the restriction mechanism, refer to the W3C website.</span></span> <span data-ttu-id="16f5a-108">向此服务器和其他网站的各种链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。</span><span class="sxs-lookup"><span data-stu-id="16f5a-108">For various links to this and other websites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="16f5a-109">若要从复杂全局类型派生的限制，在林中的架构的另一个位置开始的方法是插入一个新**记录**上所需的位置的节点。</span><span class="sxs-lookup"><span data-stu-id="16f5a-109">To derive from a complex global type by restriction, in another location in the schema tree, begin by inserting a new **Record** node at the desired location.</span></span> <span data-ttu-id="16f5a-110">然后设置其**基数据类型**属性设置为复杂全局类型的名称。</span><span class="sxs-lookup"><span data-stu-id="16f5a-110">Then set its **Base Data Type** property to the name of a complex global type.</span></span> <span data-ttu-id="16f5a-111">最后，更改的设置**派生源**属性从其默认值为**扩展**（至少一个基本数据类型设置时） 到**限制**。</span><span class="sxs-lookup"><span data-stu-id="16f5a-111">Finally, change the setting of the **Derived By** property from its default value of **Extension** (at least when a base data type is set) to **Restriction**.</span></span>  
  
 <span data-ttu-id="16f5a-112">在下面的示例中， **BillingAddress**是新插入的名称**记录**节点，和**GlobalAddrType**是从它的复杂全局类型的名称派生，并想要限制。</span><span class="sxs-lookup"><span data-stu-id="16f5a-112">In the following example, **BillingAddress** is the name of the newly inserted **Record** node, and **GlobalAddrType** is the name of the complex global type from which it derives, and intends to restrict.</span></span> <span data-ttu-id="16f5a-113">在架构树视图中，将名为节点下显示重复节点结构**BillingAddress**、 名为节点下的相邻节点结构一致**ShippingAddress**。</span><span class="sxs-lookup"><span data-stu-id="16f5a-113">In the schema tree view, a duplicate node structure would be displayed below the node named **BillingAddress**, identical to the adjacent node structure under the node named **ShippingAddress**.</span></span> <span data-ttu-id="16f5a-114">它们之间的区别在于**BillingAddress**节点结构都将遵循可能限制为基本数据类型**GlobalAddrType**，和**ShippingAddress**结构将保持为基本数据类型相同**GlobalAddrType**。</span><span class="sxs-lookup"><span data-stu-id="16f5a-114">The difference between them is that the **BillingAddress** node structure will be subject to possible restrictions to the base data type **GlobalAddrType**, and the **ShippingAddress** structure will remain identical to the base data type **GlobalAddrType**.</span></span>  
  
 <span data-ttu-id="16f5a-115">由于已选择限制基本数据类型，因此您不能插入任何新节点，但可以更改现有节点的属性，以便进一步限制其可能值或行为。</span><span class="sxs-lookup"><span data-stu-id="16f5a-115">Because you have chosen to restrict the base data type, you are not allowed to insert any new nodes, but you can change the properties of the existing nodes to further restrict their possible values or behavior.</span></span>  
  
-   <span data-ttu-id="16f5a-116">在这之前，与**派生源**属性仍设置为**扩展**。</span><span class="sxs-lookup"><span data-stu-id="16f5a-116">Before, with the **Derived By** property still set to **Extension**.</span></span>  
  
    ```  
    <xs:schema>  
        <xs:element name="Root">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="ShippingAddress" type="GlobalAddrType" />  
                    <xs:element name="BillingAddress">  
                        <xs:complexType>  
                            <xs:complexContent mixed="false">  
                                <xs:extension base="GlobalAddrType" />  
                            </xs:complexContent>  
                        </xs:complexType>  
                    </xs:element>  
                </xs:sequence>  
            </xs:complexType>  
        </xs:element>  
        <xs:complexType name="GlobalAddrType">  
        [Address structure defined globally here.]  
        </xs:complexType>  
    </xs:schema>  
    ```  
  
-   <span data-ttu-id="16f5a-117">切换之后**派生源**属性从**扩展**到**限制**。</span><span class="sxs-lookup"><span data-stu-id="16f5a-117">After switching the **Derived By** property from **Extension** to **Restriction**.</span></span>  
  
    ```  
    <xs:schema>  
        <xs:element name="Root">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="ShippingAddress" type="GlobalAddrType" />  
                    <xs:element name="BillingAddress">  
                        <xs:complexType>  
                            <xs:complexContent mixed="false">  
                                <xs:restriction base="GlobalAddrType">  
                   [Duplicate of address structure now appears  
                   here, ready to be restricted with additional  
                   attributes, set using the properties of the  
                   relevant nodes in the schema tree.]  
                                </xs:restriction>  
                            </xs:complexContent>  
                        </xs:complexType>  
                    </xs:element>  
                </xs:sequence>  
            </xs:complexType>  
        </xs:element>  
        <xs:complexType name="GlobalAddrType">  
        [Address structure defined globally here.]  
        </xs:complexType>  
    </xs:schema>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="16f5a-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16f5a-118">See Also</span></span>  
 [<span data-ttu-id="16f5a-119">复杂全局类型派生</span><span class="sxs-lookup"><span data-stu-id="16f5a-119">Complex Global Type Derivation</span></span>](../core/complex-global-type-derivation.md)