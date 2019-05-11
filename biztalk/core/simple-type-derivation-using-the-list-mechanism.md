---
title: 使用列表机制进行简单类型派生 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14f3c7b7-7585-4297-9177-2deaef8355f0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 318a58f0e0f1aed836bdf7a866a42c7df3941b9a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393162"
---
# <a name="simple-type-derivation-using-the-list-mechanism"></a><span data-ttu-id="32199-102">使用列表机制进行简单类型派生</span><span class="sxs-lookup"><span data-stu-id="32199-102">Simple Type Derivation Using the List Mechanism</span></span>
<span data-ttu-id="32199-103">当使用列表机制从现有简单类型派生新的简单类型时，并指定此属性或元素的值可以指定类型的值以空格分隔的列表。</span><span class="sxs-lookup"><span data-stu-id="32199-103">When you derive a new simple type from an existing simple type by using the list mechanism, you are specifying that the value for this attribute or element can be a space-separated list of values of the specified type.</span></span> <span data-ttu-id="32199-104">例如，可以指定属性或元素值是以空格分隔的整数列表。</span><span class="sxs-lookup"><span data-stu-id="32199-104">For example, you can specify that an attribute or element value is a space-separated list of integers.</span></span>  
  
 <span data-ttu-id="32199-105">有关通过使用列表机制派生新的简单类型的全面信息，请参阅 W3C 网站。</span><span class="sxs-lookup"><span data-stu-id="32199-105">For comprehensive information about deriving new simple types by using the list mechanism, refer to the W3C Web site.</span></span> <span data-ttu-id="32199-106">向此服务器和其他网站的各种链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。</span><span class="sxs-lookup"><span data-stu-id="32199-106">For various links to this and other Web sites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="32199-107">若要为该类型的列表派生简单类型，则请选择相关**Field 元素**节点或**字段属性**节点在架构树中，然后在属性窗口中，从下拉列表中选择一种简单类型用于列出**Base Data Type**属性。</span><span class="sxs-lookup"><span data-stu-id="32199-107">To derive a simple type as a list of that type, select the relevant **Field Element** node or **Field Attribute** node in the schema tree and then, in the Properties window, select a simple type from the drop-down list for the **Base Data Type** property.</span></span> <span data-ttu-id="32199-108">选择此属性的值时，就立即**Derived By**属性将自动更改为其默认值从**限制**，它用作类型派生的默认值。</span><span class="sxs-lookup"><span data-stu-id="32199-108">As soon as you select a value for this property, the **Derived By** property automatically changes from its default value to **Restriction**, which serves as the default value for type derivation.</span></span> <span data-ttu-id="32199-109">必须更改**Derived By**属性从**限制**到**列表**，这将导致**Base Data Type**属性被重命名为**项类型**属性 （顺便说一下，已重命名的属性将移至由于属性按字母顺序排序的属性列表中的其他位置）。</span><span class="sxs-lookup"><span data-stu-id="32199-109">You must change the **Derived By** property from **Restriction** to **List**, which causes the **Base Data Type** property to be renamed as the **Item Type** property (incidentally, the renamed property moves to a different position in the property list due to the alphabetical sorting of the properties).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32199-110">您可以将限制与列表机制一起，通过使用限制机制，然后使用，为项创建一个命名的简单类型派生中使用列表机制进行的另一个简单类型派生的类型。</span><span class="sxs-lookup"><span data-stu-id="32199-110">You can use the restriction and list mechanisms together, creating a named simple type derivation by using the restriction mechanism, and then using that as the item type in another simple type derivation by using the list mechanism.</span></span> <span data-ttu-id="32199-111">这可能导致，例如，一个值，仅限于属于一组特定枚举的字符串以空格分隔字符串的列表。</span><span class="sxs-lookup"><span data-stu-id="32199-111">This can result, for example, in a value that is constrained to be a list of space-separated strings belonging to a particular enumerated set of strings.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="32199-112">当所选的项类型本身允许空格，如字符串时，使用列表机制进行简单类型派生可能十分复杂。</span><span class="sxs-lookup"><span data-stu-id="32199-112">Using the list mechanism for simple type derivation can be complicated when the item type you choose is one that itself allows spaces, such as strings.</span></span> <span data-ttu-id="32199-113">这是类型的因为列表机制使用空格分隔的列表中允许的值。</span><span class="sxs-lookup"><span data-stu-id="32199-113">This is because the list mechanism uses spaces to separate values of the allowed type in the list.</span></span>  
  
 <span data-ttu-id="32199-114">当你首次更改**Field 元素**节点或**字段属性**节点从具有数据类型为具有某一基本数据类型 （因此开始简单类型派生的过程），并将**Derived By**属性设置为**列表**，可以观察 XSD 视图中的相应片断中的以下更改：</span><span class="sxs-lookup"><span data-stu-id="32199-114">When you first change a **Field Element** node or **Field Attribute** node from having a data type to having a base data type (thereby starting the process of simple type derivation), and then set the **Derived By** property to **List**, you can observe the following change in the corresponding fragment in the XSD view:</span></span>  
  
-   <span data-ttu-id="32199-115">在这之前，与新插入**Field 元素**名为节点**ZipCodeList**。</span><span class="sxs-lookup"><span data-stu-id="32199-115">Before, with a newly inserted **Field Element** node named **ZipCodeList**.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="ZipCodeList" type="xs:string" />  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
-   <span data-ttu-id="32199-116">设置后**Base Data Type**属性设置为 xs: integer，并设置**Derived By**属性设置为**列表**(在其后**Base Data Type**属性将重命名为**项类型**属性)。</span><span class="sxs-lookup"><span data-stu-id="32199-116">After setting the **Base Data Type** property to xs:integer, and setting the **Derived By** property to **List** (after which the **Base Data Type** property is renamed to be the **Item Type** property).</span></span>  
  
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
>  <span data-ttu-id="32199-117">在实际的架构中，它会先定义并命名将整数限制为五位数字的整数的简单类型派生更好，然后以派生**ZipCodeList**有效地将列表限制为该类型的元素具有五位数字的整数。</span><span class="sxs-lookup"><span data-stu-id="32199-117">In a real-life schema, it would be better to first define and name a simple type derivation of integer that restricts the integer to five digits, and then to derive the **ZipCodeList** element from that type, effectively limiting the list to integers having five digits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32199-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="32199-118">See Also</span></span>  
 [<span data-ttu-id="32199-119">简单类型派生</span><span class="sxs-lookup"><span data-stu-id="32199-119">Simple Type Derivation</span></span>](../core/simple-type-derivation.md)