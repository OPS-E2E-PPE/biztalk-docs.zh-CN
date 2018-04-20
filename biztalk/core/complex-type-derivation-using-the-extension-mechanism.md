---
title: 使用扩展机制的复杂类型派生 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7125fb5b-f77a-47c9-8000-f2332940df89
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5d36778b5ad99a0273e6199f59bdd337429a74b
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="complex-type-derivation-using-the-extension-mechanism"></a><span data-ttu-id="275e7-102">使用扩展机制进行复杂类型派生</span><span class="sxs-lookup"><span data-stu-id="275e7-102">Complex Type Derivation Using the Extension Mechanism</span></span>
<span data-ttu-id="275e7-103">由扩展派生的复杂类型是其基本数据类型的功能超集。</span><span class="sxs-lookup"><span data-stu-id="275e7-103">A complex type derived by extension is a functional superset of its base data type.</span></span> <span data-ttu-id="275e7-104">顾名思义，其基本数据类型是要定义的类型的基础，与基本数据类型的差异体现在附加的内容中。</span><span class="sxs-lookup"><span data-stu-id="275e7-104">As the name implies, its base data type is the basis for the type being defined, where the differences from the base type are additive.</span></span> <span data-ttu-id="275e7-105">本主题提供了在其中一个示例的两个元素 **ShippingAddress** 和 **BillingAddress** 基于复杂全局类型 **GlobalAddrType**。</span><span class="sxs-lookup"><span data-stu-id="275e7-105">This topic provides an example in which the two elements **ShippingAddress** and **BillingAddress** are based on the complex global type **GlobalAddrType**.</span></span> <span data-ttu-id="275e7-106">**ShippingAddress** 只是被定义为类型 **GlobalAddrType**, ，而 **BillingAddress** 被定义为扩展类型 **GlobalAddrType**。</span><span class="sxs-lookup"><span data-stu-id="275e7-106">**ShippingAddress** is simply defined to be of type **GlobalAddrType**, whereas **BillingAddress** is defined to extend the type **GlobalAddrType**.</span></span> <span data-ttu-id="275e7-107">在示例结束时，附加的元素添加到 **BillingAddress**, 命名 **部门**, 、 与字符串类型的默认值为 Accounts Payable。</span><span class="sxs-lookup"><span data-stu-id="275e7-107">At the end of the example, an additional element is added to **BillingAddress**, named **Department**, with a type of string and a default value of Accounts Payable.</span></span>  
  
 <span data-ttu-id="275e7-108">有关使用扩展机制派生新的复杂类型的全面信息，请参阅 W3C 网站。</span><span class="sxs-lookup"><span data-stu-id="275e7-108">For comprehensive information about deriving new complex types by using the extension mechanism, refer to the W3C website.</span></span> <span data-ttu-id="275e7-109">向此服务器和其他网站的各种链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。</span><span class="sxs-lookup"><span data-stu-id="275e7-109">For various links to this and other websites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="275e7-110">若要从复杂全局类型派生通过扩展，在林中的架构的另一个位置开始的方法是插入一个新 **记录** 上所需的位置的节点。</span><span class="sxs-lookup"><span data-stu-id="275e7-110">To derive from a complex global type by extension, in another location in the schema tree, begin by inserting a new **Record** node at the desired location.</span></span> <span data-ttu-id="275e7-111">然后设置其 **基数据类型** 属性设置为复杂全局类型的名称。</span><span class="sxs-lookup"><span data-stu-id="275e7-111">Then set its **Base Data Type** property to the name of a complex global type.</span></span>  
  
 <span data-ttu-id="275e7-112">在下面的示例中， **BillingAddress** 是新插入的名称 **记录** 节点，和 **GlobalAddrType** 是从其派生，和想要扩展复杂的全局类型的名称。</span><span class="sxs-lookup"><span data-stu-id="275e7-112">In the following example, **BillingAddress** is the name of the newly inserted **Record** node, and **GlobalAddrType** is the name of the complex global type from which it derives, and intends to extend.</span></span> <span data-ttu-id="275e7-113">在架构树视图中之后, **基数据类型** 已设置为 **GlobalAddrType**, ，将名为节点下显示重复节点结构 **BillingAddress**, 、 名为节点下的相邻节点结构相同 **ShippingAddress**。</span><span class="sxs-lookup"><span data-stu-id="275e7-113">In the schema tree view, after **Base Data Type** has been set to **GlobalAddrType**, a duplicate node structure would be displayed below the node named **BillingAddress**, identical to the adjacent node structure under the node named **ShippingAddress**.</span></span> <span data-ttu-id="275e7-114">它们之间的区别在于 **BillingAddress** 节点结构将具有超越基本数据类型可扩展性 **GlobalAddrType**, ，和 **ShippingAddress** 结构将保持为基本数据类型相同 **GlobalAddrType**。</span><span class="sxs-lookup"><span data-stu-id="275e7-114">The difference between them is that the **BillingAddress** node structure will be extensible beyond the base data type **GlobalAddrType**, and the **ShippingAddress** structure will remain identical to the base data type **GlobalAddrType**.</span></span>  
  
-   <span data-ttu-id="275e7-115">在这之前，使用新插入的节点，名为 **BillingAddress**。</span><span class="sxs-lookup"><span data-stu-id="275e7-115">Before, with a newly inserted node named **BillingAddress**.</span></span>  
  
    ```  
    <xs:schema>  
        <xs:element name="Root">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="ShippingAddress" type="GlobalAddrType" />  
                    <xs:element name="BillingAddress">  
                        <xs:sequence />  
                    </xs:element>  
                </xs:sequence>  
            </xs:complexType>  
        </xs:element>  
        <xs:complexType name="GlobalAddrType">  
        [Address structure defined globally here.]  
        </xs:complexType>  
    </xs:schema>  
    ```  
  
-   <span data-ttu-id="275e7-116">后从复杂基类型派生 **GlobalAddrType**, ，通过扩展。</span><span class="sxs-lookup"><span data-stu-id="275e7-116">After deriving from the complex base type **GlobalAddrType**, by extension.</span></span>  
  
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
  
 <span data-ttu-id="275e7-117">通过插入到的节点指定为基本数据类型的扩展名 **BillingAddress** 架构树中的节点。</span><span class="sxs-lookup"><span data-stu-id="275e7-117">You specify extensions to the base data type by inserting nodes into the **BillingAddress** node in the schema tree.</span></span> <span data-ttu-id="275e7-118">以下 XSD 片段显示了空的扩展元素如何扩展时 **序列组** 作为新的子级插入节点 **BillingAddress** 节点，然后 **Field 元素** 节点，名为 **PaymentType**, ，作为子节点的插入 **序列组** 节点。</span><span class="sxs-lookup"><span data-stu-id="275e7-118">The following XSD fragment shows how the empty extension element is expanded when a **Sequence Group** node is inserted as a new child of the **BillingAddress** node and then a **Field Element** node, named **PaymentType**, is inserted as a child node of the **Sequence Group** node.</span></span>  
  
```  
<xs:extension base="GlobalAddrType">  
    <xs:sequence>  
        <xs:element default="Accounts Payable"  
            name="Department" type="xs:string" />  
    </xs:sequence>  
</xs:extension>  
```  
  
## <a name="see-also"></a><span data-ttu-id="275e7-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="275e7-119">See Also</span></span>  
 [<span data-ttu-id="275e7-120">复杂全局类型派生</span><span class="sxs-lookup"><span data-stu-id="275e7-120">Complex Global Type Derivation</span></span>](../core/complex-global-type-derivation.md)