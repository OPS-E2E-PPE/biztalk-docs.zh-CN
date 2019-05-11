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
# <a name="simple-type-derivation-using-the-union-mechanism"></a>使用联合机制进行简单类型派生
时通过使用联合机制从现有简单类型派生新的简单类型，可指定此属性或元素的值可以为多个类型，根据你指定的类型的列表。 例如，可以指定属性或元素值是日期、 时间或日期/时间值。  
  
 有关使用联合机制派生新的简单类型的全面信息，请参阅 W3C 网站。 向此服务器和其他网站的各种链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。  
  
 若要为多个可能的类型的联合派生简单类型，请选择相关**Field 元素**节点或**字段属性**节点在架构树中，然后在属性窗口中，选择从简单类型下拉列表**Base Data Type**属性。 一旦选择了此属性的值**Derived By**属性将自动更改为其默认值从**限制**，它用作类型派生的默认值。 必须更改**Derived By**属性从**限制**到**联合**，这将导致**Base Data Type**属性被重命名为**成员类型**属性 （顺便说一下，已重命名的属性将移至由于属性按字母顺序排序的属性列表中的其他位置）。  
  
 最后，可以使用中的复选框**成员类型**下拉检查表来选择要允许实例消息中的相应值的其他类型。  
  
 当你首次更改**Field 元素**节点或**字段属性**节点从具有数据类型为具有某一基本数据类型 （因此开始简单类型派生的过程），并将**Derived By**属性设置为**Union**，可以观察 XSD 视图中的相应片断中的以下更改。  
  
-   在这之前，与新插入**Field 元素**名为节点**DatesAndOrTimes**。  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
-   设置后**Base Data Type**属性设置为**xs: date**，并设置**Derived By**属性设置为**联合**(此后**Base Data Type**属性将重命名为**成员类型**属性)，然后还选择**xs: datetime**并**xs: time**作为其他允许的类型中的**成员类型**下拉检查表。  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
## <a name="see-also"></a>请参阅  
 [简单类型派生](../core/simple-type-derivation.md)