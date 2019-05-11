---
title: 使用限制机制进行简单类型派生 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4ca712e-9563-4917-9bfc-1033a36773e8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46cfded2bd9995e99972108f46aa53c883fffc99
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393071"
---
# <a name="simple-type-derivation-using-the-restriction-mechanism"></a><span data-ttu-id="4b970-102">使用限制机制进行简单类型派生</span><span class="sxs-lookup"><span data-stu-id="4b970-102">Simple Type Derivation Using the Restriction Mechanism</span></span>

## <a name="overview"></a><span data-ttu-id="4b970-103">概述</span><span class="sxs-lookup"><span data-stu-id="4b970-103">Overview</span></span>
<span data-ttu-id="4b970-104">当通过使用限制机制从现有简单类型派生新的简单类型时，您通常要限定这些基简单类型所允许的值的子集到该属性或元素值的实例消息中允许的值。</span><span class="sxs-lookup"><span data-stu-id="4b970-104">When you derive a new simple type from an existing simple type by using the restriction mechanism, you are typically restricting the values allowed in an instance message for that attribute or element value to a subset of those values allowed by the base simple type.</span></span> <span data-ttu-id="4b970-105">例如，可以限制为若干枚举字符串之一的字符串类型。</span><span class="sxs-lookup"><span data-stu-id="4b970-105">For example, you can restrict a string type to be one of several enumerated strings.</span></span>  
  
 <span data-ttu-id="4b970-106">有关使用限制机制派生新的简单类型的全面信息，请参阅 W3C 网站。</span><span class="sxs-lookup"><span data-stu-id="4b970-106">For comprehensive information about deriving new simple types by using the restriction mechanism, refer to the W3C website.</span></span> <span data-ttu-id="4b970-107">向此服务器和其他网站的各种链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。</span><span class="sxs-lookup"><span data-stu-id="4b970-107">For various links to this and other websites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
## <a name="field-element-and-field-attribute"></a><span data-ttu-id="4b970-108">字段元素和字段属性</span><span class="sxs-lookup"><span data-stu-id="4b970-108">Field Element and Field Attribute</span></span>
 <span data-ttu-id="4b970-109">若要通过使用限制派生简单类型，选择相关**Field 元素**节点或**字段属性**节点在架构树中，然后在属性窗口中，从下拉列表中选择一种简单类型用于列出**Base Data Type**属性。</span><span class="sxs-lookup"><span data-stu-id="4b970-109">To derive a simple type by using restriction, select the relevant **Field Element** node or **Field Attribute** node in the schema tree and then, in the Properties window, select a simple type from the drop-down list for the **Base Data Type** property.</span></span> <span data-ttu-id="4b970-110">一旦选择了此属性的值**Derived By**属性将自动更改为其默认值从**限制**，它用作类型派生的默认值。</span><span class="sxs-lookup"><span data-stu-id="4b970-110">As soon as you have selected a value for this property, the **Derived By** property automatically changes from its default value to **Restriction**, which serves as the default value for type derivation.</span></span> <span data-ttu-id="4b970-111">此外，全新类别的属性，称为**限制**，在属性窗口中变为可用。</span><span class="sxs-lookup"><span data-stu-id="4b970-111">Also, a whole new category of properties, called **Restriction**, becomes available in the Properties window.</span></span>  
  
 <span data-ttu-id="4b970-112">根据你选择的基本数据类型，即可在此新类别中设置的不同的属性。</span><span class="sxs-lookup"><span data-stu-id="4b970-112">Depending on the base data type you select, different properties are available to be set in this new category.</span></span> <span data-ttu-id="4b970-113">例如，如果基本数据类型为数值，属性**MaxFacet Type** (当**MaxFacet Value**设置)， **MaxFacet Value**， **MinFacet Type**(当**MinFacet Value**设置)，并**MinFacet Value**可用于定义允许的值的非独占或排他范围。</span><span class="sxs-lookup"><span data-stu-id="4b970-113">For example, if the base data type is numeric, the properties **MaxFacet Type** (when **MaxFacet Value** is set), **MaxFacet Value**, **MinFacet Type** (when **MinFacet Value** is set), and **MinFacet Value** are available for defining an inclusive or exclusive range of allowed values.</span></span> <span data-ttu-id="4b970-114">如果基本数据类型为字符串类型，**长度**，**最大长度**，并**最小长度**属性是可用于约束字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="4b970-114">If the base data type is a string type, the **Length**, **Maximum Length**, and **Minimum Length** properties are available for constraining the length of the string.</span></span>  
  
 <span data-ttu-id="4b970-115">有关字段节点的各种限制属性的详细信息，请参阅**字段元素节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="4b970-115">For more information about the various restriction properties of field nodes, see the **Field Element Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="4b970-116">当你首次更改**字段元素**节点或**Field 特性**节点从具有某一数据类型为具有某一基本数据类型 （因此开始简单类型派生的过程），将保留**通过派生**属性设置为**限制**，并提供基于枚举的限制为允许的字符串值，可以观察 XSD 视图中的相应片断中的以下更改：</span><span class="sxs-lookup"><span data-stu-id="4b970-116">When you first change a **Field Element** node or **Field Attribute** node from having a data type to having a base data type (thereby starting the process of simple type derivation), leave the **Derived By** property set to **Restriction**, and provide an enumeration-based restriction to the allowed string values, you can observe the following changes in the corresponding fragment in the XSD view:</span></span>  
  
-   <span data-ttu-id="4b970-117">在这之前，与新插入**Field 元素**名为节点**WestCoastStates**。</span><span class="sxs-lookup"><span data-stu-id="4b970-117">Before, with a newly inserted **Field Element** node named **WestCoastStates**.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="WestCoastStates" type="xs:string" />  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
    ```  
  
-   <span data-ttu-id="4b970-118">设置后**Base Data Type**属性设置为"xs: string"，并会使派生默认值为**限制**有关**Derived By**属性。</span><span class="sxs-lookup"><span data-stu-id="4b970-118">After setting the **Base Data Type** property to "xs:string", and leaving the derivation default of **Restriction** for the **Derived By** property.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="WestCoastStates" >  
                    <xs:simpleType>  
                        <xs:restriction base="xs:string" />  
                    </xs:simpleType>  
                </xs:element>  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
    ```  
  
-   <span data-ttu-id="4b970-119">设置后**枚举**美国大陆西海岸的三个状态的名称将 Restriction 类别中的属性。</span><span class="sxs-lookup"><span data-stu-id="4b970-119">After setting the **Enumeration** property in the Restriction category to the names of the three states on the west coast of the continental United States.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="WestCoastStates">  
                    <xs:simpleType>  
                        <xs:restriction base="xs:string" />  
                            <xs:enumeration value="Washington" />  
                            <xs:enumeration value="Oregon" />  
                            <xs:enumeration value="California" />  
                        </xs:restriction>  
                    </xs:simpleType>  
                </xs:element>  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4b970-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b970-120">See Also</span></span>  
 [<span data-ttu-id="4b970-121">简单类型派生</span><span class="sxs-lookup"><span data-stu-id="4b970-121">Simple Type Derivation</span></span>](../core/simple-type-derivation.md)