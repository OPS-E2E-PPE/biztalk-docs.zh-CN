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
# <a name="complex-global-type-re-use"></a>复杂全局类型重复使用
若要使用复杂全局类型是在架构树中，另一个位置开始的方法是插入一个新**记录**在所需位置的节点。 然后设置其**Data Structure Type**属性设置为复杂全局类型的名称。  
  
 在以下示例中， **BillingAddress**的新插入名称**记录**节点，并**GlobalAddrType**是其采用的复杂全局类型的名称。 在架构树视图中，重复的节点结构将显示名为节点的下级**BillingAddress**、 名为节点下的相邻节点结构相同**ShippingAddress**。  
  
-   之前，新插入的节点具有名为**BillingAddress**。  
  
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
  
-   使用复杂基类型后**GlobalAddrType**、 原样。  
  
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
  
## <a name="see-also"></a>请参阅  
 [使用复杂全局类型的方法](../core/ways-to-use-complex-global-types.md)