---
title: "使用联合的机制的简单类型派生 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e51ae390-78f5-4fb9-9163-2a8023aea1ec
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1414fa506f824415de8e8449e8b2b27befd2fc76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="simple-type-derivation-using-the-union-mechanism"></a><span data-ttu-id="1b54c-102">使用联合机制进行简单类型派生</span><span class="sxs-lookup"><span data-stu-id="1b54c-102">Simple Type Derivation Using the Union Mechanism</span></span>
<span data-ttu-id="1b54c-103">使用联合机制从现有简单类型派生新的简单类型时，可根据所指定的类型列表，指定此属性或元素的值能够具有多种类型。</span><span class="sxs-lookup"><span data-stu-id="1b54c-103">When you derive a new simple type from an existing simple type by using the union mechanism, you are specifying that the value for this attribute or element can be of more than one type, according to a list of types that you specify.</span></span> <span data-ttu-id="1b54c-104">例如，您可以指定属性或元素值为日期、时间或日期/时间值。</span><span class="sxs-lookup"><span data-stu-id="1b54c-104">For example, you can specify that an attribute or element value is either a date, a time, or a date/time value.</span></span>  
  
 <span data-ttu-id="1b54c-105">有关使用联合机制派生新的简单类型的全面信息，请参阅 W3C 网站。</span><span class="sxs-lookup"><span data-stu-id="1b54c-105">For comprehensive information about deriving new simple types by using the union mechanism, refer to the W3C website.</span></span> <span data-ttu-id="1b54c-106">向此服务器和其他网站的各种链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。</span><span class="sxs-lookup"><span data-stu-id="1b54c-106">For various links to this and other websites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="1b54c-107">若要作为多个可能的类型的一个联合派生简单类型，请选择相关**Field 元素**节点或**字段特性**节点在架构树中，然后在属性窗口中，选择从一个简单类型下拉列表**基数据类型**属性。</span><span class="sxs-lookup"><span data-stu-id="1b54c-107">To derive a simple type as a union of several possible types, select the relevant **Field Element** node or **Field Attribute** node in the schema tree and then, in the Properties window, select a simple type from the drop-down list for the **Base Data Type** property.</span></span> <span data-ttu-id="1b54c-108">你选择了此属性的值时，就会立即**派生源**属性会自动更改为其默认值从**限制**，它用作类型派生的默认值。</span><span class="sxs-lookup"><span data-stu-id="1b54c-108">As soon as you have selected a value for this property, the **Derived By** property automatically changes from its default value to **Restriction**, which serves as the default value for type derivation.</span></span> <span data-ttu-id="1b54c-109">必须更改**派生源**属性从**限制**到**联合**，这将导致**基数据类型**属性来重命名为**成员类型**属性 （顺便说一下，将重命名的属性移到由于属性按字母顺序排序的属性列表中的不同位置）。</span><span class="sxs-lookup"><span data-stu-id="1b54c-109">You must change the **Derived By** property from **Restriction** to **Union**, which causes the **Base Data Type** property to be renamed as the **Member Types** property (incidentally, the renamed property moves to a different position in the property list due to the alphabetical sorting of the properties).</span></span>  
  
 <span data-ttu-id="1b54c-110">最后，可以使用中的复选框**成员类型**下拉清单来选择其他类型，以便实例消息中相应的值。</span><span class="sxs-lookup"><span data-stu-id="1b54c-110">Finally, you can use the check boxes in the **Member Types** drop-down checklist to select additional types to allow for corresponding values in instance messages.</span></span>  
  
 <span data-ttu-id="1b54c-111">当你第一次更改**Field 元素**节点或**字段特性**节点从具有数据类型转换为无 （从而启动简单类型派生的进程），一个基本数据类型，然后设置**派生源**属性**联合**，你可以观察到 XSD 视图中相应的片段中的以下更改。</span><span class="sxs-lookup"><span data-stu-id="1b54c-111">When you first change a **Field Element** node or **Field Attribute** node from having a data type to having a base data type (thereby starting the process of simple type derivation), and then set the **Derived By** property to **Union**, you can observe the following change in the corresponding fragment in the XSD view.</span></span>  
  
-   <span data-ttu-id="1b54c-112">在这之前，使用新插入**Field 元素**节点名为**DatesAndOrTimes**。</span><span class="sxs-lookup"><span data-stu-id="1b54c-112">Before, with a newly inserted **Field Element** node named **DatesAndOrTimes**.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
-   <span data-ttu-id="1b54c-113">设置后**基数据类型**属性**xs: date**，并设置**派生源**属性**联合**(其后**基本数据类型**属性已重命名为**成员类型**属性)，然后还选择**xs: datetime**和**xs: time**作为其他允许的类型中的**成员类型**下拉清单。</span><span class="sxs-lookup"><span data-stu-id="1b54c-113">After setting the **Base Data Type** property to **xs:date**, and setting the **Derived By** property to **Union** (after which the **Base Data Type** property is renamed to be the **Member Types** property), and then also selecting **xs:datetime** and **xs:time** as additional allowed types in the **Member Types** drop-down checklist.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1b54c-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b54c-114">See Also</span></span>  
 [<span data-ttu-id="1b54c-115">简单类型派生</span><span class="sxs-lookup"><span data-stu-id="1b54c-115">Simple Type Derivation</span></span>](../core/simple-type-derivation.md)