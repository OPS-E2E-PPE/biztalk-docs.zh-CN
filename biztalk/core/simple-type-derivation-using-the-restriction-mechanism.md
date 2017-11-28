---
title: "使用限制机制的简单类型派生 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4ca712e-9563-4917-9bfc-1033a36773e8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dda4b8ad64f1edf262446f1633eda109ba7074ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="simple-type-derivation-using-the-restriction-mechanism"></a><span data-ttu-id="ca5ce-102">使用限制机制的简单类型派生</span><span class="sxs-lookup"><span data-stu-id="ca5ce-102">Simple Type Derivation Using the Restriction Mechanism</span></span>

## <a name="overview"></a><span data-ttu-id="ca5ce-103">概述</span><span class="sxs-lookup"><span data-stu-id="ca5ce-103">Overview</span></span>
<span data-ttu-id="ca5ce-104">使用限制机制从现有简单类型派生新的简单类型时，通常将相应属性或元素值的实例消息中允许的值限制为基本简单类型所允许的那些值的子集。</span><span class="sxs-lookup"><span data-stu-id="ca5ce-104">When you derive a new simple type from an existing simple type by using the restriction mechanism, you are typically restricting the values allowed in an instance message for that attribute or element value to a subset of those values allowed by the base simple type.</span></span> <span data-ttu-id="ca5ce-105">例如，您可以将字符串类型限制为若干枚举字符串之一。</span><span class="sxs-lookup"><span data-stu-id="ca5ce-105">For example, you can restrict a string type to be one of several enumerated strings.</span></span>  
  
 <span data-ttu-id="ca5ce-106">有关使用限制机制派生新的简单类型的全面信息，请参阅 W3C 网站。</span><span class="sxs-lookup"><span data-stu-id="ca5ce-106">For comprehensive information about deriving new simple types by using the restriction mechanism, refer to the W3C website.</span></span> <span data-ttu-id="ca5ce-107">向此服务器和其他网站的各种链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。</span><span class="sxs-lookup"><span data-stu-id="ca5ce-107">For various links to this and other websites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
## <a name="field-element-and-field-attribute"></a><span data-ttu-id="ca5ce-108">字段元素和字段特性</span><span class="sxs-lookup"><span data-stu-id="ca5ce-108">Field Element and Field Attribute</span></span>
 <span data-ttu-id="ca5ce-109">若要通过限制派生简单类型，请选择相关**Field 元素**节点或**字段特性**节点在架构树中，然后在属性窗口中，从下拉列表中选择简单类型列出用于**基数据类型**属性。</span><span class="sxs-lookup"><span data-stu-id="ca5ce-109">To derive a simple type by using restriction, select the relevant **Field Element** node or **Field Attribute** node in the schema tree and then, in the Properties window, select a simple type from the drop-down list for the **Base Data Type** property.</span></span> <span data-ttu-id="ca5ce-110">你选择了此属性的值时，就会立即**派生源**属性会自动更改为其默认值从**限制**，它用作类型派生的默认值。</span><span class="sxs-lookup"><span data-stu-id="ca5ce-110">As soon as you have selected a value for this property, the **Derived By** property automatically changes from its default value to **Restriction**, which serves as the default value for type derivation.</span></span> <span data-ttu-id="ca5ce-111">此外，整个新类别的属性，调用**限制**，在属性窗口中变得可用。</span><span class="sxs-lookup"><span data-stu-id="ca5ce-111">Also, a whole new category of properties, called **Restriction**, becomes available in the Properties window.</span></span>  
  
 <span data-ttu-id="ca5ce-112">根据您选择的基本数据类型，在此新类别中可设置不同的属性。</span><span class="sxs-lookup"><span data-stu-id="ca5ce-112">Depending on the base data type you select, different properties are available to be set in this new category.</span></span> <span data-ttu-id="ca5ce-113">例如，如果基础数据类型为数值，属性**MaxFacet 类型**(时**MaxFacet 值**设置)， **MaxFacet 值**， **MinFacet 类型**(当**MinFacet 值**设置)，和**MinFacet 值**可用于定义允许的值为与或异范围。</span><span class="sxs-lookup"><span data-stu-id="ca5ce-113">For example, if the base data type is numeric, the properties **MaxFacet Type** (when **MaxFacet Value** is set), **MaxFacet Value**, **MinFacet Type** (when **MinFacet Value** is set), and **MinFacet Value** are available for defining an inclusive or exclusive range of allowed values.</span></span> <span data-ttu-id="ca5ce-114">如果基数据类型是字符串类型，**长度**，**最大长度**，和**最小长度**属性都适用于约束的字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="ca5ce-114">If the base data type is a string type, the **Length**, **Maximum Length**, and **Minimum Length** properties are available for constraining the length of the string.</span></span>  
  
 <span data-ttu-id="ca5ce-115">有关字段节点的各种限制属性的详细信息，请参阅**字段元素节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca5ce-115">For more information about the various restriction properties of field nodes, see the **Field Element Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="ca5ce-116">当你第一次更改**Field 元素**节点或**字段特性**无需具有 （从而启动简单类型派生的进程），将保留一个基本数据类型的数据类型的节点**派生的**属性设置为**限制**，并提供到允许的字符串值的基于枚举的限制，你可以观察 XSD 视图中的相应片段中的以下更改：</span><span class="sxs-lookup"><span data-stu-id="ca5ce-116">When you first change a **Field Element** node or **Field Attribute** node from having a data type to having a base data type (thereby starting the process of simple type derivation), leave the **Derived By** property set to **Restriction**, and provide an enumeration-based restriction to the allowed string values, you can observe the following changes in the corresponding fragment in the XSD view:</span></span>  
  
-   <span data-ttu-id="ca5ce-117">在这之前，使用新插入**Field 元素**节点名为**WestCoastStates**。</span><span class="sxs-lookup"><span data-stu-id="ca5ce-117">Before, with a newly inserted **Field Element** node named **WestCoastStates**.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="WestCoastStates" type="xs:string" />  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
    ```  
  
-   <span data-ttu-id="ca5ce-118">设置后**基数据类型**于"xs: string"，而不用派生默认值的属性**限制**为**派生源**属性。</span><span class="sxs-lookup"><span data-stu-id="ca5ce-118">After setting the **Base Data Type** property to "xs:string", and leaving the derivation default of **Restriction** for the **Derived By** property.</span></span>  
  
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
  
-   <span data-ttu-id="ca5ce-119">设置后**枚举**西海岸三种的美国本土其他状态的名称限制类别中的属性。</span><span class="sxs-lookup"><span data-stu-id="ca5ce-119">After setting the **Enumeration** property in the Restriction category to the names of the three states on the west coast of the continental United States.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ca5ce-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca5ce-120">See Also</span></span>  
 [<span data-ttu-id="ca5ce-121">简单类型派生</span><span class="sxs-lookup"><span data-stu-id="ca5ce-121">Simple Type Derivation</span></span>](../core/simple-type-derivation.md)