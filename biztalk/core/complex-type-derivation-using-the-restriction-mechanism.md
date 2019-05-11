---
title: 使用限制机制进行复杂类型派生 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3003d88-6b75-4dcb-834f-1babcf7449cb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9b1b4234f4bb39da70f1e59719e1f145440a0b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356810"
---
# <a name="complex-type-derivation-using-the-restriction-mechanism"></a>使用限制机制进行复杂类型派生
通过限制派生是类似于通过扩展 BizTalk 编辑器功能方面进行派生。 通过限制派生的复杂类型等同于其基本数据类型，不过，其声明是比基本数据类型中的相应声明的限制更多。 事实上，表示新类型的值是表示基本数据类型 （按原样使用简单类型限制的情况下） 的值的子集。 应用程序的基本数据类型的值应该能够成功地处理任何受限制类型的值。  
  
 有关使用限制机制派生新的复杂类型的全面信息，请参阅 W3C 网站。 向此服务器和其他网站的各种链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。  
  
 若要在架构树中，另一个位置中，通过限制从复杂全局类型派生首先插入一个新的**记录**在所需位置的节点。 然后设置其**Base Data Type**属性设置为复杂全局类型的名称。 最后，更改的设置**Derived By**属性从其默认值为**扩展**（至少一个基本数据类型设置时） 到**限制**。  
  
 在以下示例中， **BillingAddress**的新插入名称**记录**节点，并**GlobalAddrType**是从它的复杂全局类型的名称派生而来，并要限制。 在架构树视图中，重复的节点结构将显示名为节点的下级**BillingAddress**、 名为节点下的相邻节点结构相同**ShippingAddress**。 它们之间的区别在于**BillingAddress**节点结构将受到可能限制为基本数据类型**GlobalAddrType**，和**ShippingAddress**结构将保持与基本数据类型**GlobalAddrType**。  
  
 因为您已选择限制基本数据类型，不允许插入任何新节点，但你可以进一步限制其可能的值或行为的现有节点的属性。  
  
-   在这之前，使用**Derived By**属性仍设置为**扩展**。  
  
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
  
-   切换后**Derived By**属性从**扩展**到**限制**。  
  
    ```  
    <xs:schema>  
        <xs:element name="Root">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="ShippingAddress" type="GlobalAddrType" />  
                    <xs:element name="BillingAddress">  
                        <xs:complexType>  
                            <xs:complexContent mixed="false">  
                                <xs:restriction base="GlobalAddrType">  
                   [Duplicate of address structure now appears  
                   here, ready to be restricted with additional  
                   attributes, set using the properties of the  
                   relevant nodes in the schema tree.]  
                                </xs:restriction>  
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
  
## <a name="see-also"></a>请参阅  
 [复杂全局类型派生](../core/complex-global-type-derivation.md)