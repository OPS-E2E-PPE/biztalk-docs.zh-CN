---
title: 复杂全局类型重用 |Microsoft 文档
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
ms.openlocfilehash: 492d1c345b1ac540bc2410c554be29996fc52dd6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231765"
---
# <a name="complex-global-type-re-use"></a>复杂全局类型重复使用
若要使用一种复杂全局类型原样，在林中的架构的另一个位置开始的方法是插入一个新**记录**上所需的位置的节点。 然后设置其**数据结构类型**属性设置为复杂全局类型的名称。  
  
 在下面的示例中， **BillingAddress**是新插入的名称**记录**节点，和**GlobalAddrType**是它采用的复杂全局类型的名称。 在架构树视图中，将名为节点下显示重复节点结构**BillingAddress**、 名为节点下的相邻节点结构一致**ShippingAddress**。  
  
-   在这之前，使用新插入的节点，名为**BillingAddress**。  
  
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
  
-   使用复杂基类型之后**GlobalAddrType**，如是。  
  
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
  
## <a name="see-also"></a>另请参阅  
 [如何使用复杂全局类型](../core/ways-to-use-complex-global-types.md)