---
title: 选择组节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 466b525d-4d8c-4b8e-830d-eee27845c0dc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 226a0197f1f66313de994269039107b47ed03b9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002054"
---
# <a name="choice-group-nodes"></a>“选择组”节点
在 BizTalk 编辑器中，可以插入**选择组**节点以包含其他节点 （或整个子树中的节点），其中只有一个可以显示在实例消息。 给定的实例消息（如果有效）将仅显示这些选择之一。 包含的节点必须是与 XML 元素对应的节点，但不能是与 XML 属性对应的节点。  

> [!NOTE]
>  在 BizTalk 编辑器中，**选择组**节点表示的字符串\<选择\>架构树视图中。 如果引用设置为**选择组**节点，如 x，它将表示为\<Group: x\>架构树视图中。  

## <a name="xsd-representation"></a>XSD 表示形式  
 当**选择组**节点插入到**记录**节点中的其他所有子节点结尾处插入该实体**序列**，**选择**，或**所有**中的元素**记录**节点。 下面的示例显示，以粗体类型如何新**选择组**节点以 XML 架构定义 (XSD) 语言表示**选择**元素的末尾插入**序列**中的元素**记录**节点，其中对节点进行了命名以说明其标识）。  

```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  

```  

 默认情况下**选**给定元素**minOccurs**属性值为零 (0) 表示没有任何选择需要出现。 您可以更改此值在 Visual Studio 属性窗口中的时**选择组**架构树视图中选择节点。  

 下面的示例演示相同**选**元素的 xsd**元素**元素对应于两个从属**记录**节点。  

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

 在此示例中，两个同级**记录**节点用于描述这一事实，实例消息将包含一条记录的美国地址信息或具有全球范围内的地址信息的记录。 此外， **minOccurs**并**maxOccurs**的属性**选择组**节点都已设置为一 (1) 在 Visual Studio 属性窗口中，从而导致*minOccurs*并*maxOccurs*的属性**选择**元素设置为一 (1) 中的 XSD 表示形式。  

## <a name="see-also"></a>请参阅  
- [架构的 BizTalk 表示形式](../core/biztalk-representation-of-schemas.md)   
- [节点属性](../core/node-properties.md)   
- **序列组节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]     
- [如何设置节点属性](../core/how-to-set-node-properties.md)
