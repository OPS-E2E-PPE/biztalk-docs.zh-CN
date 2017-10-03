---
title: "使用列表机制的简单类型派生 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14f3c7b7-7585-4297-9177-2deaef8355f0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aafc6a540e9595f426858bc16fedfb1f8fe0bc8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="simple-type-derivation-using-the-list-mechanism"></a><span data-ttu-id="07892-102">使用列表机制进行简单类型派生</span><span class="sxs-lookup"><span data-stu-id="07892-102">Simple Type Derivation Using the List Mechanism</span></span>
<span data-ttu-id="07892-103">使用列表机制从现有简单类型派生新的简单类型时，可以指定此属性或元素的值可为以空格分隔的指定类型值的列表。</span><span class="sxs-lookup"><span data-stu-id="07892-103">When you derive a new simple type from an existing simple type by using the list mechanism, you are specifying that the value for this attribute or element can be a space-separated list of values of the specified type.</span></span> <span data-ttu-id="07892-104">例如，可以指定属性或元素值为以空格分隔的整数列表。</span><span class="sxs-lookup"><span data-stu-id="07892-104">For example, you can specify that an attribute or element value is a space-separated list of integers.</span></span>  
  
 <span data-ttu-id="07892-105">有关使用列表机制派生新的简单类型的全面信息，请参阅 W3C 网站。</span><span class="sxs-lookup"><span data-stu-id="07892-105">For comprehensive information about deriving new simple types by using the list mechanism, refer to the W3C Web site.</span></span> <span data-ttu-id="07892-106">向此服务器和其他网站的各种链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。</span><span class="sxs-lookup"><span data-stu-id="07892-106">For various links to this and other Web sites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="07892-107">若要为该类型的列表派生简单类型，请选择相关**Field 元素**节点或**字段特性**节点在架构树中，然后在属性窗口中，从下拉列表中选择简单类型列出用于**基数据类型**属性。</span><span class="sxs-lookup"><span data-stu-id="07892-107">To derive a simple type as a list of that type, select the relevant **Field Element** node or **Field Attribute** node in the schema tree and then, in the Properties window, select a simple type from the drop-down list for the **Base Data Type** property.</span></span> <span data-ttu-id="07892-108">选择此属性的值时，就会立即**派生源**属性会自动更改为其默认值从**限制**，它用作类型派生的默认值。</span><span class="sxs-lookup"><span data-stu-id="07892-108">As soon as you select a value for this property, the **Derived By** property automatically changes from its default value to **Restriction**, which serves as the default value for type derivation.</span></span> <span data-ttu-id="07892-109">必须更改**派生源**属性从**限制**到**列表**，这将导致**基数据类型**属性来重命名为**项类型**属性 （顺便说一下，将重命名的属性移到由于属性按字母顺序排序的属性列表中的不同位置）。</span><span class="sxs-lookup"><span data-stu-id="07892-109">You must change the **Derived By** property from **Restriction** to **List**, which causes the **Base Data Type** property to be renamed as the **Item Type** property (incidentally, the renamed property moves to a different position in the property list due to the alphabetical sorting of the properties).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07892-110">可以将限制与列表机制一起使用，从而使用限制机制来创建命名的简单类型派生，然后使用列表机制将该派生用作其他简单类型派生中的项类型。</span><span class="sxs-lookup"><span data-stu-id="07892-110">You can use the restriction and list mechanisms together, creating a named simple type derivation by using the restriction mechanism, and then using that as the item type in another simple type derivation by using the list mechanism.</span></span> <span data-ttu-id="07892-111">例如，这样将会导致将某个值约束为属于特定的字符串枚举集并以空格分隔的字符串的列表。</span><span class="sxs-lookup"><span data-stu-id="07892-111">This can result, for example, in a value that is constrained to be a list of space-separated strings belonging to a particular enumerated set of strings.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="07892-112">如果所选的项类型本身允许使用空格（例如，字符串），则将列表机制用于简单类型派生可能十分复杂。</span><span class="sxs-lookup"><span data-stu-id="07892-112">Using the list mechanism for simple type derivation can be complicated when the item type you choose is one that itself allows spaces, such as strings.</span></span> <span data-ttu-id="07892-113">这是因为列表机制使用空格来分隔该列表中允许类型的值。</span><span class="sxs-lookup"><span data-stu-id="07892-113">This is because the list mechanism uses spaces to separate values of the allowed type in the list.</span></span>  
  
 <span data-ttu-id="07892-114">当你第一次更改**Field 元素**节点或**字段特性**节点从具有数据类型转换为无 （从而启动简单类型派生的进程），一个基本数据类型，然后设置**派生源**属性**列表**，你可以观察到 XSD 视图中相应的片段中的以下更改：</span><span class="sxs-lookup"><span data-stu-id="07892-114">When you first change a **Field Element** node or **Field Attribute** node from having a data type to having a base data type (thereby starting the process of simple type derivation), and then set the **Derived By** property to **List**, you can observe the following change in the corresponding fragment in the XSD view:</span></span>  
  
-   <span data-ttu-id="07892-115">在这之前，使用新插入**Field 元素**节点名为**ZipCodeList**。</span><span class="sxs-lookup"><span data-stu-id="07892-115">Before, with a newly inserted **Field Element** node named **ZipCodeList**.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="ZipCodeList" type="xs:string" />  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
-   <span data-ttu-id="07892-116">设置后**基数据类型**xs:integer，和设置的属性**派生源**属性**列表**(其后**基数据类型**属性已重命名为**项类型**属性)。</span><span class="sxs-lookup"><span data-stu-id="07892-116">After setting the **Base Data Type** property to xs:integer, and setting the **Derived By** property to **List** (after which the **Base Data Type** property is renamed to be the **Item Type** property).</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="ZipCodeList">  
                    <xs:simpleType>  
               <xs:list itemType="xs:integer" />   
                       </xs:simpleType>  
                </xs:element>  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="07892-117">在现实世界架构中，它将会更好首先定义和命名的简单类型派生类型的整数，将整数限制为五位数字，然后派生**ZipCodeList**从该类型，有效地限制到列表的元素具有五位数字的整数。</span><span class="sxs-lookup"><span data-stu-id="07892-117">In a real-life schema, it would be better to first define and name a simple type derivation of integer that restricts the integer to five digits, and then to derive the **ZipCodeList** element from that type, effectively limiting the list to integers having five digits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07892-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07892-118">See Also</span></span>  
 [<span data-ttu-id="07892-119">简单类型派生</span><span class="sxs-lookup"><span data-stu-id="07892-119">Simple Type Derivation</span></span>](../core/simple-type-derivation.md)