---
title: "使用列表机制的简单类型派生 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14f3c7b7-7585-4297-9177-2deaef8355f0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aafc6a540e9595f426858bc16fedfb1f8fe0bc8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="simple-type-derivation-using-the-list-mechanism"></a>使用列表机制进行简单类型派生
使用列表机制从现有简单类型派生新的简单类型时，可以指定此属性或元素的值可为以空格分隔的指定类型值的列表。 例如，可以指定属性或元素值为以空格分隔的整数列表。  
  
 有关使用列表机制派生新的简单类型的全面信息，请参阅 W3C 网站。 向此服务器和其他网站的各种链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。  
  
 若要为该类型的列表派生简单类型，请选择相关**Field 元素**节点或**字段特性**节点在架构树中，然后在属性窗口中，从下拉列表中选择简单类型列出用于**基数据类型**属性。 选择此属性的值时，就会立即**派生源**属性会自动更改为其默认值从**限制**，它用作类型派生的默认值。 必须更改**派生源**属性从**限制**到**列表**，这将导致**基数据类型**属性来重命名为**项类型**属性 （顺便说一下，将重命名的属性移到由于属性按字母顺序排序的属性列表中的不同位置）。  
  
> [!NOTE]
>  可以将限制与列表机制一起使用，从而使用限制机制来创建命名的简单类型派生，然后使用列表机制将该派生用作其他简单类型派生中的项类型。 例如，这样将会导致将某个值约束为属于特定的字符串枚举集并以空格分隔的字符串的列表。  
  
> [!CAUTION]
>  如果所选的项类型本身允许使用空格（例如，字符串），则将列表机制用于简单类型派生可能十分复杂。 这是因为列表机制使用空格来分隔该列表中允许类型的值。  
  
 当你第一次更改**Field 元素**节点或**字段特性**节点从具有数据类型转换为无 （从而启动简单类型派生的进程），一个基本数据类型，然后设置**派生源**属性**列表**，你可以观察到 XSD 视图中相应的片段中的以下更改：  
  
-   在这之前，使用新插入**Field 元素**节点名为**ZipCodeList**。  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="ZipCodeList" type="xs:string" />  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
-   设置后**基数据类型**xs:integer，和设置的属性**派生源**属性**列表**(其后**基数据类型**属性已重命名为**项类型**属性)。  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="ZipCodeList">  
                    <xs:simpleType>  
               <xs:list itemType="xs:integer" />   
                       </xs:simpleType>  
                </xs:element>  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
> [!NOTE]
>  在现实世界架构中，它将会更好首先定义和命名的简单类型派生类型的整数，将整数限制为五位数字，然后派生**ZipCodeList**从该类型，有效地限制到列表的元素具有五位数字的整数。  
  
## <a name="see-also"></a>另请参阅  
 [简单类型派生](../core/simple-type-derivation.md)