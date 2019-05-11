---
title: 使用列表机制进行简单类型派生 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14f3c7b7-7585-4297-9177-2deaef8355f0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 318a58f0e0f1aed836bdf7a866a42c7df3941b9a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393162"
---
# <a name="simple-type-derivation-using-the-list-mechanism"></a>使用列表机制进行简单类型派生
当使用列表机制从现有简单类型派生新的简单类型时，并指定此属性或元素的值可以指定类型的值以空格分隔的列表。 例如，可以指定属性或元素值是以空格分隔的整数列表。  
  
 有关通过使用列表机制派生新的简单类型的全面信息，请参阅 W3C 网站。 向此服务器和其他网站的各种链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。  
  
 若要为该类型的列表派生简单类型，则请选择相关**Field 元素**节点或**字段属性**节点在架构树中，然后在属性窗口中，从下拉列表中选择一种简单类型用于列出**Base Data Type**属性。 选择此属性的值时，就立即**Derived By**属性将自动更改为其默认值从**限制**，它用作类型派生的默认值。 必须更改**Derived By**属性从**限制**到**列表**，这将导致**Base Data Type**属性被重命名为**项类型**属性 （顺便说一下，已重命名的属性将移至由于属性按字母顺序排序的属性列表中的其他位置）。  
  
> [!NOTE]
>  您可以将限制与列表机制一起，通过使用限制机制，然后使用，为项创建一个命名的简单类型派生中使用列表机制进行的另一个简单类型派生的类型。 这可能导致，例如，一个值，仅限于属于一组特定枚举的字符串以空格分隔字符串的列表。  
  
> [!CAUTION]
>  当所选的项类型本身允许空格，如字符串时，使用列表机制进行简单类型派生可能十分复杂。 这是类型的因为列表机制使用空格分隔的列表中允许的值。  
  
 当你首次更改**Field 元素**节点或**字段属性**节点从具有数据类型为具有某一基本数据类型 （因此开始简单类型派生的过程），并将**Derived By**属性设置为**列表**，可以观察 XSD 视图中的相应片断中的以下更改：  
  
-   在这之前，与新插入**Field 元素**名为节点**ZipCodeList**。  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="ZipCodeList" type="xs:string" />  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
-   设置后**Base Data Type**属性设置为 xs: integer，并设置**Derived By**属性设置为**列表**(在其后**Base Data Type**属性将重命名为**项类型**属性)。  
  
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
>  在实际的架构中，它会先定义并命名将整数限制为五位数字的整数的简单类型派生更好，然后以派生**ZipCodeList**有效地将列表限制为该类型的元素具有五位数字的整数。  
  
## <a name="see-also"></a>请参阅  
 [简单类型派生](../core/simple-type-derivation.md)