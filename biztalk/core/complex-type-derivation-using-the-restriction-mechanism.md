---
title: 使用限制机制进行复杂类型派生 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3003d88-6b75-4dcb-834f-1babcf7449cb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9b1b4234f4bb39da70f1e59719e1f145440a0b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356810"
---
# <a name="complex-type-derivation-using-the-restriction-mechanism"></a><span data-ttu-id="7dc5e-102">使用限制机制进行复杂类型派生</span><span class="sxs-lookup"><span data-stu-id="7dc5e-102">Complex Type Derivation Using the Restriction Mechanism</span></span>
<span data-ttu-id="7dc5e-103">通过限制派生是类似于通过扩展 BizTalk 编辑器功能方面进行派生。</span><span class="sxs-lookup"><span data-stu-id="7dc5e-103">Derivation by restriction is similar to derivation by extension, in terms of BizTalk Editor functionality.</span></span> <span data-ttu-id="7dc5e-104">通过限制派生的复杂类型等同于其基本数据类型，不过，其声明是比基本数据类型中的相应声明的限制更多。</span><span class="sxs-lookup"><span data-stu-id="7dc5e-104">A complex type derived by restriction is similar to its base data type, except that its declarations are more limited than the corresponding declarations in the base data type.</span></span> <span data-ttu-id="7dc5e-105">事实上，表示新类型的值是表示基本数据类型 （按原样使用简单类型限制的情况下） 的值的子集。</span><span class="sxs-lookup"><span data-stu-id="7dc5e-105">In fact, the values represented by the new type are a subset of the values represented by the base data type (as is the case with restriction of simple types).</span></span> <span data-ttu-id="7dc5e-106">应用程序的基本数据类型的值应该能够成功地处理任何受限制类型的值。</span><span class="sxs-lookup"><span data-stu-id="7dc5e-106">An application prepared for the values of the base data type ought to be able to successfully process any of the values of the restricted type.</span></span>  
  
 <span data-ttu-id="7dc5e-107">有关使用限制机制派生新的复杂类型的全面信息，请参阅 W3C 网站。</span><span class="sxs-lookup"><span data-stu-id="7dc5e-107">For comprehensive information about deriving new complex types by using the restriction mechanism, refer to the W3C website.</span></span> <span data-ttu-id="7dc5e-108">向此服务器和其他网站的各种链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。</span><span class="sxs-lookup"><span data-stu-id="7dc5e-108">For various links to this and other websites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="7dc5e-109">若要在架构树中，另一个位置中，通过限制从复杂全局类型派生首先插入一个新的**记录**在所需位置的节点。</span><span class="sxs-lookup"><span data-stu-id="7dc5e-109">To derive from a complex global type by restriction, in another location in the schema tree, begin by inserting a new **Record** node at the desired location.</span></span> <span data-ttu-id="7dc5e-110">然后设置其**Base Data Type**属性设置为复杂全局类型的名称。</span><span class="sxs-lookup"><span data-stu-id="7dc5e-110">Then set its **Base Data Type** property to the name of a complex global type.</span></span> <span data-ttu-id="7dc5e-111">最后，更改的设置**Derived By**属性从其默认值为**扩展**（至少一个基本数据类型设置时） 到**限制**。</span><span class="sxs-lookup"><span data-stu-id="7dc5e-111">Finally, change the setting of the **Derived By** property from its default value of **Extension** (at least when a base data type is set) to **Restriction**.</span></span>  
  
 <span data-ttu-id="7dc5e-112">在以下示例中， **BillingAddress**的新插入名称**记录**节点，并**GlobalAddrType**是从它的复杂全局类型的名称派生而来，并要限制。</span><span class="sxs-lookup"><span data-stu-id="7dc5e-112">In the following example, **BillingAddress** is the name of the newly inserted **Record** node, and **GlobalAddrType** is the name of the complex global type from which it derives, and intends to restrict.</span></span> <span data-ttu-id="7dc5e-113">在架构树视图中，重复的节点结构将显示名为节点的下级**BillingAddress**、 名为节点下的相邻节点结构相同**ShippingAddress**。</span><span class="sxs-lookup"><span data-stu-id="7dc5e-113">In the schema tree view, a duplicate node structure would be displayed below the node named **BillingAddress**, identical to the adjacent node structure under the node named **ShippingAddress**.</span></span> <span data-ttu-id="7dc5e-114">它们之间的区别在于**BillingAddress**节点结构将受到可能限制为基本数据类型**GlobalAddrType**，和**ShippingAddress**结构将保持与基本数据类型**GlobalAddrType**。</span><span class="sxs-lookup"><span data-stu-id="7dc5e-114">The difference between them is that the **BillingAddress** node structure will be subject to possible restrictions to the base data type **GlobalAddrType**, and the **ShippingAddress** structure will remain identical to the base data type **GlobalAddrType**.</span></span>  
  
 <span data-ttu-id="7dc5e-115">因为您已选择限制基本数据类型，不允许插入任何新节点，但你可以进一步限制其可能的值或行为的现有节点的属性。</span><span class="sxs-lookup"><span data-stu-id="7dc5e-115">Because you have chosen to restrict the base data type, you are not allowed to insert any new nodes, but you can change the properties of the existing nodes to further restrict their possible values or behavior.</span></span>  
  
-   <span data-ttu-id="7dc5e-116">在这之前，使用**Derived By**属性仍设置为**扩展**。</span><span class="sxs-lookup"><span data-stu-id="7dc5e-116">Before, with the **Derived By** property still set to **Extension**.</span></span>  
  
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
  
-   <span data-ttu-id="7dc5e-117">切换后**Derived By**属性从**扩展**到**限制**。</span><span class="sxs-lookup"><span data-stu-id="7dc5e-117">After switching the **Derived By** property from **Extension** to **Restriction**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7dc5e-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="7dc5e-118">See Also</span></span>  
 [<span data-ttu-id="7dc5e-119">复杂全局类型派生</span><span class="sxs-lookup"><span data-stu-id="7dc5e-119">Complex Global Type Derivation</span></span>](../core/complex-global-type-derivation.md)