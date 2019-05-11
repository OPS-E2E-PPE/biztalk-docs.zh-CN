---
title: 复杂全局类型重用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d0d8018-f2c6-44cc-9330-2385ac8887eb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63d8d743878e268a0f75ff27ca5bf6842a43b10b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356776"
---
# <a name="complex-global-type-re-use"></a><span data-ttu-id="dd2b3-102">复杂全局类型重复使用</span><span class="sxs-lookup"><span data-stu-id="dd2b3-102">Complex Global Type Re-use</span></span>
<span data-ttu-id="dd2b3-103">若要使用复杂全局类型是在架构树中，另一个位置开始的方法是插入一个新**记录**在所需位置的节点。</span><span class="sxs-lookup"><span data-stu-id="dd2b3-103">To use a complex global type as is, in another location in the schema tree, begin by inserting a new **Record** node at the desired location.</span></span> <span data-ttu-id="dd2b3-104">然后设置其**Data Structure Type**属性设置为复杂全局类型的名称。</span><span class="sxs-lookup"><span data-stu-id="dd2b3-104">Then set its **Data Structure Type** property to the name of a complex global type.</span></span>  
  
 <span data-ttu-id="dd2b3-105">在以下示例中， **BillingAddress**的新插入名称**记录**节点，并**GlobalAddrType**是其采用的复杂全局类型的名称。</span><span class="sxs-lookup"><span data-stu-id="dd2b3-105">In the following example, **BillingAddress** is the name of the newly inserted **Record** node, and **GlobalAddrType** is the name of the complex global type that it adopts.</span></span> <span data-ttu-id="dd2b3-106">在架构树视图中，重复的节点结构将显示名为节点的下级**BillingAddress**、 名为节点下的相邻节点结构相同**ShippingAddress**。</span><span class="sxs-lookup"><span data-stu-id="dd2b3-106">In the schema tree view, a duplicate node structure would be displayed below the node named **BillingAddress**, identical to the adjacent node structure under the node named **ShippingAddress**.</span></span>  
  
-   <span data-ttu-id="dd2b3-107">之前，新插入的节点具有名为**BillingAddress**。</span><span class="sxs-lookup"><span data-stu-id="dd2b3-107">Before, with a newly inserted node named **BillingAddress**.</span></span>  
  
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
  
-   <span data-ttu-id="dd2b3-108">使用复杂基类型后**GlobalAddrType**、 原样。</span><span class="sxs-lookup"><span data-stu-id="dd2b3-108">After using the complex base type **GlobalAddrType**, as is.</span></span>  
  
    ```  
    <xs:schema>  
        <xs:element name="Root">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="ShippingAddress" type="GlobalAddrType" />  
                    <xs:element name="BillingAddress" type="GlobalAddrType" />  
                </xs:sequence>  
            </xs:complexType>  
        </xs:element>  
        <xs:complexType name="GlobalAddrType">  
        [Address structure defined globally here.]  
        </xs:complexType>  
    </xs:schema>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="dd2b3-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd2b3-109">See Also</span></span>  
 [<span data-ttu-id="dd2b3-110">使用复杂全局类型的方法</span><span class="sxs-lookup"><span data-stu-id="dd2b3-110">Ways to Use Complex Global Types</span></span>](../core/ways-to-use-complex-global-types.md)