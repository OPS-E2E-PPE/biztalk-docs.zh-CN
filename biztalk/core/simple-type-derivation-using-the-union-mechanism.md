---
title: 使用联合机制进行简单类型派生 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e51ae390-78f5-4fb9-9163-2a8023aea1ec
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b178b8ee6bf0e09877cc14ac72f30f569162166
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393048"
---
# <a name="simple-type-derivation-using-the-union-mechanism"></a><span data-ttu-id="11fde-102">使用联合机制进行简单类型派生</span><span class="sxs-lookup"><span data-stu-id="11fde-102">Simple Type Derivation Using the Union Mechanism</span></span>
<span data-ttu-id="11fde-103">时通过使用联合机制从现有简单类型派生新的简单类型，可指定此属性或元素的值可以为多个类型，根据你指定的类型的列表。</span><span class="sxs-lookup"><span data-stu-id="11fde-103">When you derive a new simple type from an existing simple type by using the union mechanism, you are specifying that the value for this attribute or element can be of more than one type, according to a list of types that you specify.</span></span> <span data-ttu-id="11fde-104">例如，可以指定属性或元素值是日期、 时间或日期/时间值。</span><span class="sxs-lookup"><span data-stu-id="11fde-104">For example, you can specify that an attribute or element value is either a date, a time, or a date/time value.</span></span>  
  
 <span data-ttu-id="11fde-105">有关使用联合机制派生新的简单类型的全面信息，请参阅 W3C 网站。</span><span class="sxs-lookup"><span data-stu-id="11fde-105">For comprehensive information about deriving new simple types by using the union mechanism, refer to the W3C website.</span></span> <span data-ttu-id="11fde-106">向此服务器和其他网站的各种链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。</span><span class="sxs-lookup"><span data-stu-id="11fde-106">For various links to this and other websites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="11fde-107">若要为多个可能的类型的联合派生简单类型，请选择相关**Field 元素**节点或**字段属性**节点在架构树中，然后在属性窗口中，选择从简单类型下拉列表**Base Data Type**属性。</span><span class="sxs-lookup"><span data-stu-id="11fde-107">To derive a simple type as a union of several possible types, select the relevant **Field Element** node or **Field Attribute** node in the schema tree and then, in the Properties window, select a simple type from the drop-down list for the **Base Data Type** property.</span></span> <span data-ttu-id="11fde-108">一旦选择了此属性的值**Derived By**属性将自动更改为其默认值从**限制**，它用作类型派生的默认值。</span><span class="sxs-lookup"><span data-stu-id="11fde-108">As soon as you have selected a value for this property, the **Derived By** property automatically changes from its default value to **Restriction**, which serves as the default value for type derivation.</span></span> <span data-ttu-id="11fde-109">必须更改**Derived By**属性从**限制**到**联合**，这将导致**Base Data Type**属性被重命名为**成员类型**属性 （顺便说一下，已重命名的属性将移至由于属性按字母顺序排序的属性列表中的其他位置）。</span><span class="sxs-lookup"><span data-stu-id="11fde-109">You must change the **Derived By** property from **Restriction** to **Union**, which causes the **Base Data Type** property to be renamed as the **Member Types** property (incidentally, the renamed property moves to a different position in the property list due to the alphabetical sorting of the properties).</span></span>  
  
 <span data-ttu-id="11fde-110">最后，可以使用中的复选框**成员类型**下拉检查表来选择要允许实例消息中的相应值的其他类型。</span><span class="sxs-lookup"><span data-stu-id="11fde-110">Finally, you can use the check boxes in the **Member Types** drop-down checklist to select additional types to allow for corresponding values in instance messages.</span></span>  
  
 <span data-ttu-id="11fde-111">当你首次更改**Field 元素**节点或**字段属性**节点从具有数据类型为具有某一基本数据类型 （因此开始简单类型派生的过程），并将**Derived By**属性设置为**Union**，可以观察 XSD 视图中的相应片断中的以下更改。</span><span class="sxs-lookup"><span data-stu-id="11fde-111">When you first change a **Field Element** node or **Field Attribute** node from having a data type to having a base data type (thereby starting the process of simple type derivation), and then set the **Derived By** property to **Union**, you can observe the following change in the corresponding fragment in the XSD view.</span></span>  
  
-   <span data-ttu-id="11fde-112">在这之前，与新插入**Field 元素**名为节点**DatesAndOrTimes**。</span><span class="sxs-lookup"><span data-stu-id="11fde-112">Before, with a newly inserted **Field Element** node named **DatesAndOrTimes**.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
-   <span data-ttu-id="11fde-113">设置后**Base Data Type**属性设置为**xs: date**，并设置**Derived By**属性设置为**联合**(此后**Base Data Type**属性将重命名为**成员类型**属性)，然后还选择**xs: datetime**并**xs: time**作为其他允许的类型中的**成员类型**下拉检查表。</span><span class="sxs-lookup"><span data-stu-id="11fde-113">After setting the **Base Data Type** property to **xs:date**, and setting the **Derived By** property to **Union** (after which the **Base Data Type** property is renamed to be the **Member Types** property), and then also selecting **xs:datetime** and **xs:time** as additional allowed types in the **Member Types** drop-down checklist.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="11fde-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="11fde-114">See Also</span></span>  
 [<span data-ttu-id="11fde-115">简单类型派生</span><span class="sxs-lookup"><span data-stu-id="11fde-115">Simple Type Derivation</span></span>](../core/simple-type-derivation.md)