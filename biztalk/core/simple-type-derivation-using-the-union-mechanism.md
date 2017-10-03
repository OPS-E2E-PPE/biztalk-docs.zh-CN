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
# <a name="simple-type-derivation-using-the-union-mechanism"></a>使用联合机制进行简单类型派生
使用联合机制从现有简单类型派生新的简单类型时，可根据所指定的类型列表，指定此属性或元素的值能够具有多种类型。 例如，您可以指定属性或元素值为日期、时间或日期/时间值。  
  
 有关使用联合机制派生新的简单类型的全面信息，请参阅 W3C 网站。 向此服务器和其他网站的各种链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。  
  
 若要作为多个可能的类型的一个联合派生简单类型，请选择相关**Field 元素**节点或**字段特性**节点在架构树中，然后在属性窗口中，选择从一个简单类型下拉列表**基数据类型**属性。 你选择了此属性的值时，就会立即**派生源**属性会自动更改为其默认值从**限制**，它用作类型派生的默认值。 必须更改**派生源**属性从**限制**到**联合**，这将导致**基数据类型**属性来重命名为**成员类型**属性 （顺便说一下，将重命名的属性移到由于属性按字母顺序排序的属性列表中的不同位置）。  
  
 最后，可以使用中的复选框**成员类型**下拉清单来选择其他类型，以便实例消息中相应的值。  
  
 当你第一次更改**Field 元素**节点或**字段特性**节点从具有数据类型转换为无 （从而启动简单类型派生的进程），一个基本数据类型，然后设置**派生源**属性**联合**，你可以观察到 XSD 视图中相应的片段中的以下更改。  
  
-   在这之前，使用新插入**Field 元素**节点名为**DatesAndOrTimes**。  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
-   设置后**基数据类型**属性**xs: date**，并设置**派生源**属性**联合**(其后**基本数据类型**属性已重命名为**成员类型**属性)，然后还选择**xs: datetime**和**xs: time**作为其他允许的类型中的**成员类型**下拉清单。  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [简单类型派生](../core/simple-type-derivation.md)