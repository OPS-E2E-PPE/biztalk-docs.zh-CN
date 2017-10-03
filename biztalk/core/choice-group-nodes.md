---
title: "选择组节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 466b525d-4d8c-4b8e-830d-eee27845c0dc
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec6edafcb01e2c0ce155585e4fbe2f9d61b1cf1c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="choice-group-nodes"></a>“选择组”节点
在 BizTalk 编辑器中，你可以插入**选项组**节点包含其他节点 （或整个子树的节点），只有一个可以出现在实例消息中。 给定的实例消息（如果有效）将仅显示这些选择之一。 包含的节点必须是与 XML 元素对应的节点，但不能是与 XML 属性对应的节点。  
  
> [!NOTE]
>  在 BizTalk 编辑器中，**选项组**节点表示以字符串\<选择 > 架构树视图中。 如果引用设置为**选项组**节点，如 x，则它会表示为\<组： x > 架构树视图中。  
  
## <a name="xsd-representation"></a>XSD 表示形式  
 当**选项组**节点插入到**记录**节点，它将在任何其他子节点的末尾插入**序列**，**选择**，或**所有**中的元素**记录**节点。 下面的示例显示，粗体类型如何新**选项组**节点表示 XML 架构定义 (XSD) 语言**选择**末尾插入元素**序列**中的元素**记录**节点 （带有名为以阐明其标识的节点）。  
  
```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  
  
```  
  
 默认情况下，**选择**给定元素**minOccurs**属性值为零 (0)，表示的选项需要出现。 你可以更改此值在 Visual Studio 属性窗口中的时**选项组**架构树视图中选择节点。  
  
 下面的示例演示如何将相同**选择**的 xsd 元素**元素**元素对应于两个从属**记录**节点。  
  
```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
            <xs:choice minOccurs="1" maxOccurs="1">  
                <xs:element name="usAddress">  
                    <xs:complexType>  
                        <xs:sequence>  
                        </xs:sequence>  
                    </xs:complexType>  
                </xs:element>  
                <xs:element name="foreignAddress">  
                    <xs:complexType>  
                        <xs:sequence>  
                        </xs:sequence>  
                    </xs:complexType>  
                </xs:element>  
            </xs:choice>  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  
```  
  
 在此示例中，两个同级**记录**节点用于描述这一事实，实例消息将具有在其中，美国地址信息的记录或在其中的全球范围内的地址信息的记录。 此外， **minOccurs**和**maxOccurs**属性**选项组**节点都已设置为一 (1) 在 Visual Studio 属性窗口中，从而导致*minOccurs*和*maxOccurs*属性**选择**被设置为一 (1) 中的 XSD 表示的元素。  
  
## <a name="see-also"></a>另请参阅  
-  [BizTalk 表示形式架构](../core/biztalk-representation-of-schemas.md)   
-  [节点属性](../core/node-properties.md)   
-  **序列组节点属性**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]     
-  [如何设置节点属性](../core/how-to-set-node-properties.md)