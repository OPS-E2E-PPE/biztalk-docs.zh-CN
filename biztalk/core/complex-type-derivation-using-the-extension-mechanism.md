---
title: "使用扩展机制的复杂类型派生 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7125fb5b-f77a-47c9-8000-f2332940df89
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5d36778b5ad99a0273e6199f59bdd337429a74b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="complex-type-derivation-using-the-extension-mechanism"></a>使用扩展机制进行复杂类型派生
由扩展派生的复杂类型是其基本数据类型的功能超集。 顾名思义，其基本数据类型是要定义的类型的基础，与基本数据类型的差异体现在附加的内容中。 本主题提供了在其中一个示例的两个元素**ShippingAddress**和**BillingAddress**基于复杂全局类型**GlobalAddrType**。 **ShippingAddress**只是被定义为类型**GlobalAddrType**，而**BillingAddress**被定义为扩展类型**GlobalAddrType**。 在示例结束时，附加的元素添加到**BillingAddress**命名**部门**、 与字符串类型的默认值为 Accounts Payable。  
  
 有关使用扩展机制派生新的复杂类型的全面信息，请参阅 W3C 网站。 向此服务器和其他网站的各种链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。  
  
 若要从复杂全局类型派生通过扩展，在林中的架构的另一个位置开始的方法是插入一个新**记录**上所需的位置的节点。 然后设置其**基数据类型**属性设置为复杂全局类型的名称。  
  
 在下面的示例中， **BillingAddress**是新插入的名称**记录**节点，和**GlobalAddrType**是从它的复杂全局类型的名称派生，并想要扩展。 在架构树视图中之后,**基数据类型**已设置为**GlobalAddrType**，将名为节点下显示重复节点结构**BillingAddress**，与名为节点下的相邻节点结构相同**ShippingAddress**。 它们之间的区别在于**BillingAddress**节点结构将具有超越基本数据类型可扩展性**GlobalAddrType**，和**ShippingAddress**结构将保持为基本数据类型相同**GlobalAddrType**。  
  
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
  
-   后从复杂基类型派生**GlobalAddrType**，通过扩展。  
  
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
  
 通过插入到的节点指定为基本数据类型的扩展名**BillingAddress**架构树中的节点。 以下 XSD 片段显示了空的扩展元素如何扩展时**序列组**作为新的子级插入节点**BillingAddress**节点，然后**Field 元素**节点，名为**PaymentType**，作为子节点的插入**序列组**节点。  
  
```  
<xs:extension base="GlobalAddrType">  
    <xs:sequence>  
        <xs:element default="Accounts Payable"  
            name="Department" type="xs:string" />  
    </xs:sequence>  
</xs:extension>  
```  
  
## <a name="see-also"></a>另请参阅  
 [复杂全局类型派生](../core/complex-global-type-derivation.md)