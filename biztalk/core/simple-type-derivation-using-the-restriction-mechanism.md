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
# <a name="simple-type-derivation-using-the-restriction-mechanism"></a>使用限制机制进行简单类型派生

## <a name="overview"></a>概述
当通过使用限制机制从现有简单类型派生新的简单类型时，您通常要限定这些基简单类型所允许的值的子集到该属性或元素值的实例消息中允许的值。 例如，可以限制为若干枚举字符串之一的字符串类型。  
  
 有关使用限制机制派生新的简单类型的全面信息，请参阅 W3C 网站。 向此服务器和其他网站的各种链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。  
  
## <a name="field-element-and-field-attribute"></a>字段元素和字段属性
 若要通过使用限制派生简单类型，选择相关**Field 元素**节点或**字段属性**节点在架构树中，然后在属性窗口中，从下拉列表中选择一种简单类型用于列出**Base Data Type**属性。 一旦选择了此属性的值**Derived By**属性将自动更改为其默认值从**限制**，它用作类型派生的默认值。 此外，全新类别的属性，称为**限制**，在属性窗口中变为可用。  
  
 根据你选择的基本数据类型，即可在此新类别中设置的不同的属性。 例如，如果基本数据类型为数值，属性**MaxFacet Type** (当**MaxFacet Value**设置)， **MaxFacet Value**， **MinFacet Type**(当**MinFacet Value**设置)，并**MinFacet Value**可用于定义允许的值的非独占或排他范围。 如果基本数据类型为字符串类型，**长度**，**最大长度**，并**最小长度**属性是可用于约束字符串的长度。  
  
 有关字段节点的各种限制属性的详细信息，请参阅**字段元素节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
 当你首次更改**字段元素**节点或**Field 特性**节点从具有某一数据类型为具有某一基本数据类型 （因此开始简单类型派生的过程），将保留**通过派生**属性设置为**限制**，并提供基于枚举的限制为允许的字符串值，可以观察 XSD 视图中的相应片断中的以下更改：  
  
-   在这之前，与新插入**Field 元素**名为节点**WestCoastStates**。  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="WestCoastStates" type="xs:string" />  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
    ```  
  
-   设置后**Base Data Type**属性设置为"xs: string"，并会使派生默认值为**限制**有关**Derived By**属性。  
  
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
  
-   设置后**枚举**美国大陆西海岸的三个状态的名称将 Restriction 类别中的属性。  
  
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
  
## <a name="see-also"></a>请参阅  
 [简单类型派生](../core/simple-type-derivation.md)